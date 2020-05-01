Collecting Cycles
-----------------

Traditionally, reference counting memory mechanisms, such as that used
previously by PHP, fail to address circular reference memory leaks;
however, as of 5.3.0, PHP implements the synchronous algorithm from the
<a href="http://researcher.watson.ibm.com/researcher/files/us-bacon/Bacon01Concurrent.pdf" class="link external">» Concurrent Cycle Collection in Reference Counted Systems</a>
paper which addresses that issue.

A full explanation of how the algorithm works would be slightly beyond
the scope of this section, but the basics are explained here. First of
all, we have to establish a few ground rules. If a refcount is
increased, it's still in use and therefore, not garbage. If the refcount
is decreased and hits zero, the zval can be freed. This means that
garbage cycles can only be created when a refcount argument is decreased
to a non-zero value. Secondly, in a garbage cycle, it is possible to
discover which parts are garbage by checking whether it is possible to
decrease their refcount by one, and then checking which of the zvals
have a refcount of zero.

<img src="images/12f37b1c6963c1c5c18f30495416a197-gc-algorithm.png" width="614" height="814" alt="Garbage collection algorithm" />

To avoid having to call the checking of garbage cycles with every
possible decrease of a refcount, the algorithm instead puts all possible
roots (zvals) in the "root buffer" (marking them "purple"). It also
makes sure that each possible garbage root ends up in the buffer only
once. Only when the root buffer is full does the collection mechanism
start for all the different zvals inside. See step A in the figure
above.

In step B, the algorithm runs a depth-first search on all possible roots
to decrease by one the refcounts of each zval it finds, making sure not
to decrease a refcount on the same zval twice (by marking them as
"grey"). In step C, the algorithm again runs a depth-first search from
each root node, to check the refcount of each zval again. If it finds
that the refcount is zero, the zval is marked "white" (blue in the
figure). If it's larger than zero, it reverts the decreasing of the
refcount by one with a depth-first search from that point on, and they
are marked "black" again. In the last step (D), the algorithm walks over
the root buffer removing the zval roots from there, and meanwhile,
checks which zvals have been marked "white" in the previous step. Every
zval marked as "white" will be freed.

Now that you have a basic understanding of how the algorithm works, we
will look back at how this integrates with PHP. By default, PHP's
garbage collector is turned on. There is, however, a `php.ini` setting
that allows you to change this:
<a href="/info/setup.html#" class="link">zend.enable_gc</a>.

When the garbage collector is turned on, the cycle-finding algorithm as
described above is executed whenever the root buffer runs full. The root
buffer has a fixed size of 10,000 possible roots (although you can alter
this by changing the *GC\_ROOT\_BUFFER\_MAX\_ENTRIES* constant in
*Zend/zend\_gc.c* in the PHP source code, and re-compiling PHP). When
the garbage collector is turned off, the cycle-finding algorithm will
never run. However, possible roots will always be recorded in the root
buffer, no matter whether the garbage collection mechanism has been
activated with this configuration setting.

If the root buffer becomes full with possible roots while the garbage
collection mechanism is turned off, further possible roots will simply
not be recorded. Those possible roots that are not recorded will never
be analyzed by the algorithm. If they were part of a circular reference
cycle, they would never be cleaned up and would create a memory leak.

The reason why possible roots are recorded even if the mechanism has
been disabled is because it's faster to record possible roots than to
have to check whether the mechanism is turned on every time a possible
root could be found. The garbage collection and analysis mechanism
itself, however, can take a considerable amount of time.

Besides changing the
<a href="/info/setup.html#" class="link">zend.enable_gc</a>
configuration setting, it is also possible to turn the garbage
collecting mechanism on and off by calling <span
class="function">gc\_enable</span> or <span
class="function">gc\_disable</span> respectively. Calling those
functions has the same effect as turning on or off the mechanism with
the configuration setting. It is also possible to force the collection
of cycles even if the possible root buffer is not full yet. For this,
you can use the <span class="function">gc\_collect\_cycles</span>
function. This function will return how many cycles were collected by
the algorithm.

The rationale behind the ability to turn the mechanism on and off, and
to initiate cycle collection yourself, is that some parts of your
application could be highly time-sensitive. In those cases, you might
not want the garbage collection mechanism to kick in. Of course, by
turning off the garbage collection for certain parts of your
application, you do risk creating memory leaks because some possible
roots might not fit into the limited root buffer. Therefore, it is
probably wise to call <span class="function">gc\_collect\_cycles</span>
just before you call <span class="function">gc\_disable</span> to free
up the memory that could be lost through possible roots that are already
recorded in the root buffer. This then leaves an empty buffer so that
there is more space for storing possible roots while the cycle
collecting mechanism is turned off.

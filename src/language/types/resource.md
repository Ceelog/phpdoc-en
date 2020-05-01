Resources
---------

A <span class="type">resource</span> is a special variable, holding a
reference to an external resource. Resources are created and used by
special functions. See the
<a href="/resource.html" class="link">appendix</a> for a listing of all
these functions and the corresponding <span class="type">resource</span>
types.

See also the <span class="function">get\_resource\_type</span> function.

### Converting to resource

As <span class="type">resource</span> variables hold special handles to
opened files, database connections, image canvas areas and the like,
converting to a <span class="type">resource</span> makes no sense.

### Freeing resources

Thanks to the reference-counting system being part of Zend Engine, a
<span class="type">resource</span> with no more references to it is
detected automatically, and it is freed by the garbage collector. For
this reason, it is rarely necessary to free the memory manually.

> **Note**: <span class="simpara"> Persistent database links are an
> exception to this rule. They are *not* destroyed by the garbage
> collector. See the
> <a href="/features/persistent-connections.html" class="link">persistent connections</a>
> section for more information. </span>

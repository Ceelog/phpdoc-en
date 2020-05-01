pthreads is an object-orientated API that provides all of the tools
needed for multi-threading in PHP. PHP applications can create, read,
write, execute and synchronize with Threads, Workers and Threaded
objects.

**Tip**

Consider using <a href="/book/parallel.html" class="link">parallel</a>
instead.

**Warning**

The pthreads extension cannot be used in a web server environment.
Threading in PHP is therefore restricted to CLI-based applications only.

**Warning**

pthreads (v3) can only be used with PHP 7.2+: This is due to ZTS mode
being unsafe in 7.0 and 7.1.

The <span class="classname">Threaded</span> class forms the basis of the
functionality that allows pthreads to operate. It exposes
synchronization methods and some useful interfaces for the programmer.

The <span class="classname">Thread</span> class enables for threads to
be created by simply extending it and implementing a *run* method. Any
members can be written to and read by any context with a reference to
the thread. Any context can also execute any public and protected
methods. The body of the run method will be executed in a separate
thread when the <span class="methodname">Thread::start</span> method of
the implementation is called from the context that created it. Only the
context that creates a thread can start and join it.

The <span class="classname">Worker</span> class has a persistent state,
and will be available from the call to <span
class="methodname">Thread::start</span> (an inherited method) until the
object goes out of scope, or is explicitly shutdown (via <span
class="methodname">Worker::shutdown</span>). Any context with a
reference to the worker object can stack tasks onto the Worker (via
<span class="methodname">Worker::stack</span>), where these tasks will
be executed by the worker in a separate thread. The *run* method of a
worker object will be executed before any objects on the worker's stack,
enabling for resources to be initialized that the objects to be executed
may need.

The <span class="classname">Pool</span> class is used to create a group
of workers to distribute <span class="classname">Threaded</span> objects
amongst them. It is the easiest and most efficient way of using multiple
threads in PHP applications.

**Caution**

The <span class="classname">Pool</span> class does not extend the <span
class="classname">Threaded</span> class, and so pool-based objects are
considered a normal PHP objects. As such, its instances of it should not
be shared amongst different contexts.

The <span class="classname">Volatile</span> class is new to pthreads v3.
It is used to denote mutable <span class="classname">Threaded</span>
properties of <span class="classname">Threaded</span> classes (since
these are now immutable by default). It is also used to store PHP arrays
in <span class="classname">Threaded</span> contexts.

Synchronization is an important ability when threading. All of the
objects that pthreads creates have built in synchronization in the
(which will be familiar to java programmers) form of <span
class="methodname">Threaded::wait</span> and <span
class="methodname">Threaded::notify</span>. Calling <span
class="methodname">Threaded::wait</span> on an object will cause the
context to wait for another context to call <span
class="methodname">Threaded::notify</span> on the same object. This
mechanism allows for powerful synchronization between <span
class="classname">Threaded</span> objects in PHP.

**Caution**

Any objects that are intended for use in the multi-threaded parts of
your application should extend <span class="classname">Threaded</span>.

Data Storage: As a rule of thumb, any data type that can be serialized
can be used as a member of a Threaded object, it can be read and written
from any context with a reference to the Threaded Object. Not every type
of data is stored serially, basic types are stored in their true form.
Complex types, Arrays, and Objects that are not Threaded are stored
serially; they can be read and written to the Threaded Object from any
context with a reference. With the exception of Threaded Objects any
reference used to set a member of a Threaded Object is separated from
the reference in the Threaded Object; the same data can be read directly
from the Threaded Object at any time by any context with a reference to
the Threaded Object.

Static Members: When a new context is created ( Thread or Worker ), they
are generally copied, but resources and objects with internal state are
nullified (for safety reasons). This allows them to function as a kind
of thread local storage. For example, upon starting the context, a class
whose static members include connection information for a database
server, and the connection itself, will only have the simple connection
information copied, not the connection. Allowing the new context to
initiate a connection in the same way as the context that created it,
storing the connection in the same place without affecting the original
context.

**Caution**

When print\_r, var\_dump and other object debug functions are executed,
they do not include recursion protection.

> **Note**:
>
> Resources: The extensions and functionality that define resources in
> PHP are completely unprepared for this kind of environment; pthreads
> makes provisions for Resources to be shared among contexts, however,
> for most types of resource it should be considered unsafe. Extreme
> caution and care should be used when sharing resources among contexts.

**Caution**

In the environment which pthreads executes, some restrictions and
limitations are necessary in order to provide a stable environment.

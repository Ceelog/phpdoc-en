Sync
====

**Table of Contents**

-   [Introduction](/intro/sync.html)
-   [Installing/Configuring](/sync/setup.html)
    -   [Requirements](/sync/setup.html#Requirements)
    -   [Installation](/sync/setup.html#Installation)
    -   [Runtime
        Configuration](/sync/setup.html#Runtime%20Configuration)
    -   [Resource Types](/sync/setup.html#Resource%20Types)
-   [Predefined Constants](/sync/constants.html)
-   [SyncMutex](/class/syncmutex.html) — The SyncMutex class
    -   [SyncMutex::\_\_construct](/class/syncmutex.html#SyncMutex::__construct)
        — Constructs a new SyncMutex object
    -   [SyncMutex::lock](/class/syncmutex.html#SyncMutex::lock) — Waits
        for an exclusive lock
    -   [SyncMutex::unlock](/class/syncmutex.html#SyncMutex::unlock) —
        Unlocks the mutex
-   [SyncSemaphore](/class/syncsemaphore.html) — The SyncSemaphore class
    -   [SyncSemaphore::\_\_construct](/class/syncsemaphore.html#SyncSemaphore::__construct)
        — Constructs a new SyncSemaphore object
    -   [SyncSemaphore::lock](/class/syncsemaphore.html#SyncSemaphore::lock)
        — Decreases the count of the semaphore or waits
    -   [SyncSemaphore::unlock](/class/syncsemaphore.html#SyncSemaphore::unlock)
        — Increases the count of the semaphore
-   [SyncEvent](/class/syncevent.html) — The SyncEvent class
    -   [SyncEvent::\_\_construct](/class/syncevent.html#SyncEvent::__construct)
        — Constructs a new SyncEvent object
    -   [SyncEvent::fire](/class/syncevent.html#SyncEvent::fire) —
        Fires/sets the event
    -   [SyncEvent::reset](/class/syncevent.html#SyncEvent::reset) —
        Resets a manual event
    -   [SyncEvent::wait](/class/syncevent.html#SyncEvent::wait) — Waits
        for the event to be fired/set
-   [SyncReaderWriter](/class/syncreaderwriter.html) — The
    SyncReaderWriter class
    -   [SyncReaderWriter::\_\_construct](/class/syncreaderwriter.html#SyncReaderWriter::__construct)
        — Constructs a new SyncReaderWriter object
    -   [SyncReaderWriter::readlock](/class/syncreaderwriter.html#SyncReaderWriter::readlock)
        — Waits for a read lock
    -   [SyncReaderWriter::readunlock](/class/syncreaderwriter.html#SyncReaderWriter::readunlock)
        — Releases a read lock
    -   [SyncReaderWriter::writelock](/class/syncreaderwriter.html#SyncReaderWriter::writelock)
        — Waits for an exclusive write lock
    -   [SyncReaderWriter::writeunlock](/class/syncreaderwriter.html#SyncReaderWriter::writeunlock)
        — Releases a write lock
-   [SyncSharedMemory](/class/syncsharedmemory.html) — The
    SyncSharedMemory class
    -   [SyncSharedMemory::\_\_construct](/class/syncsharedmemory.html#SyncSharedMemory::__construct)
        — Constructs a new SyncSharedMemory object
    -   [SyncSharedMemory::first](/class/syncsharedmemory.html#SyncSharedMemory::first)
        — Check to see if the object is the first instance system-wide
        of named shared memory
    -   [SyncSharedMemory::read](/class/syncsharedmemory.html#SyncSharedMemory::read)
        — Copy data from named shared memory
    -   [SyncSharedMemory::size](/class/syncsharedmemory.html#SyncSharedMemory::size)
        — Returns the size of the named shared memory
    -   [SyncSharedMemory::write](/class/syncsharedmemory.html#SyncSharedMemory::write)
        — Copy data to named shared memory

Introduction
------------

A cross-platform, native implementation of named and unnamed countable
mutex objects.

A mutex is a mutual exclusion object that restricts access to a shared
resource (e.g. a file) to a single instance. Countable mutexes acquire
the mutex a single time and internally track the number of times the
mutex is locked. The mutex is unlocked as soon as it goes out of scope
or is unlocked the same number of times that it was locked.

Class synopsis
--------------

**SyncMutex**

<span class="ooclass"> class **SyncMutex** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">lock</span> (\[ <span class="methodparam"><span
class="type">int</span> `$wait`<span class="initializer"> =
-1</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unlock</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$all`<span
class="initializer"> = **`FALSE`**</span></span> \] )

}

SyncMutex::\_\_construct
========================

Constructs a new SyncMutex object

### Description

<span class="modifier">public</span> <span
class="methodname">SyncMutex::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

Constructs a named or unnamed countable mutex.

### Parameters

`name`  
The name of the mutex if this is a named mutex object.

> **Note**:
>
> If the name already exists, it must be able to be opened by the
> current user that the process is running as or an exception will be
> thrown with a meaningless error message.

### Return Values

The new SyncMutex object. An exception is thrown if the mutex cannot be
created or opened.

### Examples

**Example \#1 <span class="function">SyncMutex::\_\_construct</span>
named mutex with lock timeout example**

``` php
<?php
$mutex = new SyncMutex("UniqueName");

if (!$mutex->lock(3000))
{
    echo "Unable to lock mutex.";

    exit();
}

/* ... */

$mutex->unlock();
?>
```

**Example \#2 <span class="function">SyncMutex::\_\_construct</span>
unnamed mutex example**

``` php
<?php
$mutex = new SyncMutex();

$mutex->lock();

/* ... */

$mutex->unlock();
?>
```

### See Also

-   <span class="methodname">SyncMutex::lock</span>
-   <span class="methodname">SyncMutex::unlock</span>

SyncMutex::lock
===============

Waits for an exclusive lock

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncMutex::lock</span> (\[ <span
class="methodparam"><span class="type">int</span> `$wait`<span
class="initializer"> = -1</span></span> \] )

Obtains an exclusive lock on a SyncMutex object. If the lock is already
acquired, then this increments an internal counter.

### Parameters

`wait`  
The number of milliseconds to wait for the exclusive lock. A value of -1
is infinite.

### Return Values

A boolean of TRUE if the lock was obtained, FALSE otherwise.

### Examples

**Example \#1 <span class="function">SyncMutex::lock</span> example**

``` php
<?php
$mutex = new SyncMutex("UniqueName");

if (!$mutex->lock(3000))
{
    echo "Unable to lock mutex.";

    exit();
}

/* ... */

$mutex->unlock();
?>
```

### See Also

-   <span class="methodname">SyncMutex::unlock</span>

SyncMutex::unlock
=================

Unlocks the mutex

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncMutex::unlock</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$all`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Decreases the internal counter of a SyncMutex object. When the internal
counter reaches zero, the actual lock on the object is released.

### Parameters

`all`  
Specifies whether or not to set the internal counter to zero and
therefore release the lock.

### Return Values

A boolean of TRUE if the unlock operation was successful, FALSE
otherwise.

### Examples

**Example \#1 <span class="function">SyncMutex::unlock</span> example**

``` php
<?php
$mutex = new SyncMutex("UniqueName");

$mutex->lock();

/* ... */

$mutex->unlock();
?>
```

### See Also

-   <span class="methodname">SyncMutex::lock</span>

Introduction
------------

A cross-platform, native implementation of named and unnamed semaphore
objects.

A semaphore restricts access to a limited resource to a limited number
of instances. Semaphores differ from mutexes in that they can allow more
than one instance to access a resource at one time while a mutex only
allows one instance at a time.

Class synopsis
--------------

**SyncSemaphore**

<span class="ooclass"> class **SyncSemaphore** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$initialval`<span class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$autounlock`<span
class="initializer"> = **`TRUE`**</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">lock</span> (\[ <span class="methodparam"><span
class="type">int</span> `$wait`<span class="initializer"> =
-1</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unlock</span> (\[ <span
class="methodparam"><span class="type">int</span> `&$prevcount`</span>
\] )

}

SyncSemaphore::\_\_construct
============================

Constructs a new SyncSemaphore object

### Description

<span class="modifier">public</span> <span
class="methodname">SyncSemaphore::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$initialval`<span class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$autounlock`<span
class="initializer"> = **`TRUE`**</span></span> \]\]\] )

Constructs a named or unnamed semaphore.

### Parameters

`name`  
The name of the semaphore if this is a named semaphore object.

> **Note**:
>
> If the name already exists, it must be able to be opened by the
> current user that the process is running as or an exception will be
> thrown with a meaningless error message.

`initialval`  
The initial value of the semaphore. This is the number of locks that may
be obtained.

`autounlock`  
Specifies whether or not to automatically unlock the semaphore at the
conclusion of the PHP script.

**Warning**
If an object is: A named semaphore with an autounlock of FALSE, the
object is locked, and the PHP script concludes before the object is
unlocked, then the underlying semaphore will end up in an inconsistent
state.

### Return Values

The new SyncSemaphore object. An exception is thrown if the semaphore
cannot be created or opened.

### Examples

**Example \#1 <span class="function">SyncSemaphore::\_\_construct</span>
example**

``` php
<?php
$semaphore = new SyncSemaphore("LimitedResource_2clients", 2);

if (!$semaphore->lock(3000))
{
    echo "Unable to lock semaphore.";

    exit();
}

/* ... */

$semaphore->unlock();
?>
```

### See Also

-   <span class="methodname">SyncSemaphore::lock</span>
-   <span class="methodname">SyncSemaphore::unlock</span>

SyncSemaphore::lock
===================

Decreases the count of the semaphore or waits

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncSemaphore::lock</span> (\[ <span
class="methodparam"><span class="type">int</span> `$wait`<span
class="initializer"> = -1</span></span> \] )

Decreases the count of a SyncSemaphore object or waits until the
semaphore becomes non-zero.

### Parameters

`wait`  
The number of milliseconds to wait for the semaphore. A value of -1 is
infinite.

### Return Values

A boolean of TRUE if the lock operation was successful, FALSE otherwise.

### Examples

**Example \#1 <span class="function">SyncSemaphore::lock</span>
example**

``` php
<?php
$semaphore = new SyncSemaphore("LimitedResource_2clients", 2);

if (!$semaphore->lock(3000))
{
    echo "Unable to lock semaphore.";

    exit();
}

/* ... */

$semaphore->unlock();
?>
```

### See Also

-   <span class="methodname">SyncSemaphore::unlock</span>

SyncSemaphore::unlock
=====================

Increases the count of the semaphore

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncSemaphore::unlock</span> (\[ <span
class="methodparam"><span class="type">int</span> `&$prevcount`</span>
\] )

Increases the count of a SyncSemaphore object.

### Parameters

`prevcount`  
Returns the previous count of the semaphore.

### Return Values

A boolean of TRUE if the unlock operation was successful, FALSE
otherwise.

### Examples

**Example \#1 <span class="function">SyncSemaphore::unlock</span>
example**

``` php
<?php
$semaphore = new SyncSemaphore("LimitedResource_2clients", 2);

if (!$semaphore->lock(3000))
{
    echo "Unable to lock semaphore.";

    exit();
}

/* ... */

$semaphore->unlock();
?>
```

### See Also

-   <span class="methodname">SyncSemaphore::lock</span>

Introduction
------------

A cross-platform, native implementation of named and unnamed event
objects. Both automatic and manual event objects are supported.

An event object waits, without polling, for the object to be fired/set.
One instance waits on the event object while another instance fires/sets
the event. Event objects are useful wherever a long-running process
would otherwise poll a resource (e.g. checking to see if uploaded data
needs to be processed).

Class synopsis
--------------

**SyncEvent**

<span class="ooclass"> class **SyncEvent** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$manual`<span
class="initializer"> = **`FALSE`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$prefire`<span
class="initializer"> = **`FALSE`**</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">fire</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">reset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">wait</span> (\[ <span class="methodparam"><span
class="type">int</span> `$wait`<span class="initializer"> =
-1</span></span> \] )

}

SyncEvent::\_\_construct
========================

Constructs a new SyncEvent object

### Description

<span class="modifier">public</span> <span
class="methodname">SyncEvent::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$manual`<span
class="initializer"> = **`FALSE`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$prefire`<span
class="initializer"> = **`FALSE`**</span></span> \]\]\] )

Constructs a named or unnamed event object.

### Parameters

`name`  
The name of the event if this is a named event object.

> **Note**:
>
> If the name already exists, it must be able to be opened by the
> current user that the process is running as or an exception will be
> thrown with a meaningless error message.

`manual`  
Specifies whether or not the event object must be reset manually.

> **Note**:
>
> Manual reset event objects allow all waiting processes through until
> the object is reset.

`prefire`  
Specifies whether or not to prefire (signal) the event object.

> **Note**:
>
> Only has impact if the calling process/thread is the first to create
> the object.

### Return Values

The new SyncEvent object. An exception is thrown if the event object
cannot be created or opened.

### Examples

**Example \#1 <span class="function">SyncEvent::\_\_construct</span>
example**

``` php
<?php
// In a web application:
$event = new SyncEvent("GetAppReport");
$event->fire();

// In a cron job:
$event = new SyncEvent("GetAppReport");
$event->wait();
?>
```

### Changelog

| Version | Description      |
|---------|------------------|
| 1.1.0   | Added `prefire`. |

### See Also

-   <span class="methodname">SyncEvent::fire</span>
-   <span class="methodname">SyncEvent::reset</span>
-   <span class="methodname">SyncEvent::wait</span>

SyncEvent::fire
===============

Fires/sets the event

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncEvent::fire</span> ( <span
class="methodparam">void</span> )

Fires/sets a SyncEvent object. Lets multiple threads through that are
waiting if the event object was created with a manual value of TRUE.

### Parameters

This function has no parameters.

### Return Values

A boolean of TRUE if the event was fired, FALSE otherwise.

### Examples

**Example \#1 <span class="function">SyncEvent::fire</span> example**

``` php
<?php
// In a web application:
$event = new SyncEvent("GetAppReport");
$event->fire();

// In a cron job:
$event = new SyncEvent("GetAppReport");
$event->wait();
?>
```

### See Also

-   <span class="methodname">SyncEvent::reset</span>
-   <span class="methodname">SyncEvent::wait</span>

SyncEvent::reset
================

Resets a manual event

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncEvent::reset</span> ( <span
class="methodparam">void</span> )

Resets a SyncEvent object that has been fired/set. Only valid for manual
event objects.

### Parameters

This function has no parameters.

### Return Values

A boolean value of TRUE if the object was successfully reset, FALSE
otherwise.

### Examples

**Example \#1 <span class="function">SyncEvent::reset</span> example**

``` php
<?php
// In a web application:
$event = new SyncEvent("DemoApplication", true);
$event->wait();

// In a cron job:
$event = new SyncEvent("DemoApplication", true);
$event->reset();
/* ... Do some maintenance task(s) ... */
$event->fire();
?>
```

### See Also

-   <span class="methodname">SyncEvent::fire</span>
-   <span class="methodname">SyncEvent::reset</span>
-   <span class="methodname">SyncEvent::wait</span>

SyncEvent::wait
===============

Waits for the event to be fired/set

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncEvent::wait</span> (\[ <span
class="methodparam"><span class="type">int</span> `$wait`<span
class="initializer"> = -1</span></span> \] )

Waits for the SyncEvent object to be fired.

### Parameters

`wait`  
The number of milliseconds to wait for the event to be fired. A value of
-1 is infinite.

### Return Values

A boolean of TRUE if the event was fired, FALSE otherwise.

### Examples

**Example \#1 <span class="function">SyncEvent::wait</span> example**

``` php
<?php
// In a web application:
$event = new SyncEvent("GetAppReport");
$event->fire();

// In a cron job:
$event = new SyncEvent("GetAppReport");
$event->wait();
?>
```

### See Also

-   <span class="methodname">SyncEvent::fire</span>

Introduction
------------

A cross-platform, native implementation of named and unnamed
reader-writer objects.

A reader-writer object allows many readers or one writer to access a
resource. This is an efficient solution for managing resources where
access will primarily be read-only but exclusive write access is
occasionally necessary.

Class synopsis
--------------

**SyncReaderWriter**

<span class="ooclass"> class **SyncReaderWriter** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$autounlock`<span class="initializer"> = **`TRUE`**</span></span> \]\]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">readlock</span> (\[ <span
class="methodparam"><span class="type">int</span> `$wait`<span
class="initializer"> = -1</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">readunlock</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">writelock</span> (\[ <span
class="methodparam"><span class="type">int</span> `$wait`<span
class="initializer"> = -1</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">writeunlock</span> ( <span
class="methodparam">void</span> )

}

SyncReaderWriter::\_\_construct
===============================

Constructs a new SyncReaderWriter object

### Description

<span class="modifier">public</span> <span
class="methodname">SyncReaderWriter::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$autounlock`<span class="initializer"> = **`TRUE`**</span></span> \]\]
)

Constructs a named or unnamed reader-writer object.

### Parameters

`name`  
The name of the reader-writer if this is a named reader-writer object.

> **Note**:
>
> If the name already exists, it must be able to be opened by the
> current user that the process is running as or an exception will be
> thrown with a meaningless error message.

`autounlock`  
Specifies whether or not to automatically unlock the reader-writer at
the conclusion of the PHP script.

**Warning**
If an object is: A named reader-writer with an autounlock of FALSE, the
object is locked for either reading or writing, and the PHP script
concludes before the object is unlocked, then the underlying objects
will end up in an inconsistent state.

### Return Values

The new SyncReaderWriter object. An exception is thrown if the
reader-writer cannot be created or opened.

### Examples

**Example \#1 <span
class="function">SyncReaderWriter::\_\_construct</span> example**

``` php
<?php
$readwrite = new SyncReaderWriter("FileCacheLock");
$readwrite->readlock();
/* ... */
$readwrite->readunlock();

$readwrite->writelock();
/* ... */
$readwrite->writeunlock();
?>
```

### See Also

-   <span class="methodname">SyncReaderWriter::readlock</span>
-   <span class="methodname">SyncReaderWriter::readunlock</span>
-   <span class="methodname">SyncReaderWriter::writelock</span>
-   <span class="methodname">SyncReaderWriter::writeunlock</span>

SyncReaderWriter::readlock
==========================

Waits for a read lock

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncReaderWriter::readlock</span> (\[ <span
class="methodparam"><span class="type">int</span> `$wait`<span
class="initializer"> = -1</span></span> \] )

Obtains a read lock on a SyncReaderWriter object.

### Parameters

`wait`  
The number of milliseconds to wait for a lock. A value of -1 is
infinite.

### Return Values

A boolean of TRUE if the lock was obtained, FALSE otherwise.

### Examples

**Example \#1 <span class="function">SyncReaderWriter::readlock</span>
example**

``` php
<?php
$readwrite = new SyncReaderWriter("FileCacheLock");
$readwrite->readlock();
/* ... */
$readwrite->readunlock();
?>
```

### See Also

-   <span class="methodname">SyncReaderWriter::readunlock</span>

SyncReaderWriter::readunlock
============================

Releases a read lock

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncReaderWriter::readunlock</span> ( <span
class="methodparam">void</span> )

Releases a read lock on a SyncReaderWriter object.

### Parameters

This function has no parameters.

### Return Values

A boolean of TRUE if the unlock operation was successful, FALSE
otherwise.

### Examples

**Example \#1 <span class="function">SyncReaderWriter::readunlock</span>
example**

``` php
<?php
$readwrite = new SyncReaderWriter("FileCacheLock");
$readwrite->readlock();
/* ... */
$readwrite->readunlock();
?>
```

### See Also

-   <span class="methodname">SyncReaderWriter::readlock</span>

SyncReaderWriter::writelock
===========================

Waits for an exclusive write lock

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncReaderWriter::writelock</span> (\[ <span
class="methodparam"><span class="type">int</span> `$wait`<span
class="initializer"> = -1</span></span> \] )

Obtains an exclusive write lock on a SyncReaderWriter object.

### Parameters

`wait`  
The number of milliseconds to wait for a lock. A value of -1 is
infinite.

### Return Values

A boolean of TRUE if the lock was obtained, FALSE otherwise.

### Examples

**Example \#1 <span class="function">SyncReaderWriter::writelock</span>
example**

``` php
<?php
$readwrite = new SyncReaderWriter("FileCacheLock");
$readwrite->writelock();
/* ... */
$readwrite->writeunlock();
?>
```

### See Also

-   <span class="methodname">SyncReaderWriter::writeunlock</span>

SyncReaderWriter::writeunlock
=============================

Releases a write lock

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncReaderWriter::writeunlock</span> ( <span
class="methodparam">void</span> )

Releases a write lock on a SyncReaderWriter object.

### Parameters

This function has no parameters.

### Return Values

A boolean of TRUE if the unlock operation was successful, FALSE
otherwise.

### Examples

**Example \#1 <span
class="function">SyncReaderWriter::writeunlock</span> example**

``` php
<?php
$readwrite = new SyncReaderWriter("FileCacheLock");
$readwrite->writelock();
/* ... */
$readwrite->writeunlock();
?>
```

### See Also

-   <span class="methodname">SyncReaderWriter::writelock</span>

Introduction
------------

A cross-platform, native, consistent implementation of named shared
memory objects.

Shared memory lets two separate processes communicate without the need
for complex pipes or sockets. There are several integer-based shared
memory implementations for PHP. Named shared memory is an alternative.

Synchronization objects (e.g. SyncMutex) are still required to protect
most uses of shared memory.

Class synopsis
--------------

**SyncSharedMemory**

<span class="ooclass"> class **SyncSharedMemory** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$size`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">first</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">read</span> (\[ <span class="methodparam"><span
class="type">int</span> `$start`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">size</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">write</span> (\[ <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$start`<span
class="initializer"> = 0</span></span> \]\] )

}

SyncSharedMemory::\_\_construct
===============================

Constructs a new SyncSharedMemory object

### Description

<span class="modifier">public</span> <span
class="methodname">SyncSharedMemory::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$size`</span> )

Constructs a named shared memory object.

### Parameters

`name`  
The name of the shared memory object.

> **Note**:
>
> If the name already exists, it must be able to be opened by the
> current user that the process is running as or an exception will be
> thrown with a meaningless error message.

`size`  
The size, in bytes, of shared memory to reserve.

> **Note**:
>
> The amount of memory cannot be resized later. Request sufficient
> storage up front.

### Return Values

The new SyncSharedMemory object. An exception is thrown if the shared
memory object cannot be created or opened.

### Examples

**Example \#1 <span
class="function">SyncSharedMemory::\_\_construct</span> example**

``` php
<?php
// You will probably need to protect shared memory with other synchronization objects.
// Shared memory goes away when the last reference to it disappears.
$mem = new SyncSharedMemory("AppReportName", 1024);
if ($mem->first())
{
    // Do first time initialization work here.
}

$result = $mem->write(json_encode(array("name" => "my_report.txt")));
?>
```

### See Also

-   <span class="methodname">SyncSharedMemory::first</span>
-   <span class="methodname">SyncSharedMemory::size</span>
-   <span class="methodname">SyncSharedMemory::write</span>
-   <span class="methodname">SyncSharedMemory::read</span>

SyncSharedMemory::first
=======================

Check to see if the object is the first instance system-wide of named
shared memory

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncSharedMemory::first</span> ( <span
class="methodparam">void</span> )

Retrieves the system-wide first instance status of a SyncSharedMemory
object.

### Parameters

This function has no parameters.

### Return Values

A boolean of TRUE if the object is the first instance system-wide, FALSE
otherwise.

### Examples

**Example \#1 <span class="function">SyncSharedMemory::first</span>
example**

``` php
<?php
$mem = new SyncSharedMemory("AppReportName", 1024);
if ($mem->first())
{
    // Do first time initialization work here.
}

var_dump($mem->first());

$mem2 = new SyncSharedMemory("AppReportName", 1024);

var_dump($mem2->first());
?>
```

The above example will output something similar to:

    bool(true)
    bool(false)

### See Also

-   <span class="methodname">SyncSharedMemory::write</span>
-   <span class="methodname">SyncSharedMemory::read</span>

SyncSharedMemory::read
======================

Copy data from named shared memory

### Description

<span class="modifier">public</span> <span
class="methodname">SyncSharedMemory::read</span> (\[ <span
class="methodparam"><span class="type">int</span> `$start`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$length`</span> \]\]
)

Copies data from named shared memory.

### Parameters

`start`  
The start/offset, in bytes, to begin reading.

> **Note**:
>
> If the value is negative, the starting position will begin at the
> specified number of bytes from the end of the shared memory segment.

`length`  
The number of bytes to read.

> **Note**:
>
> If unspecified, reading will stop at the end of the shared memory
> segment.
>
> If the value is negative, reading will stop the specified number of
> bytes from the end of the shared memory segment.

### Return Values

A string containing the data read from shared memory.

### Examples

**Example \#1 <span
class="function">SyncSharedMemory::\_\_construct</span> example**

``` php
<?php
// You will probably need to protect shared memory with other synchronization objects.
// Shared memory goes away when the last reference to it disappears.
$mem = new SyncSharedMemory("AppReportName", 1024);
if ($mem->first())
{
    // Do first time initialization work here.
}

$result = $mem->write("report.txt");

$result = $mem->read(3, -4);
var_dump($result);
?>
```

The above example will output something similar to:

    string(3) "ort"

### See Also

-   <span class="methodname">SyncSharedMemory::\_\_construct</span>
-   <span class="methodname">SyncSharedMemory::first</span>
-   <span class="methodname">SyncSharedMemory::write</span>
-   <span class="methodname">SyncSharedMemory::read</span>

SyncSharedMemory::size
======================

Returns the size of the named shared memory

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SyncSharedMemory::size</span> ( <span
class="methodparam">void</span> )

Retrieves the shared memory size of a SyncSharedMemory object.

### Parameters

This function has no parameters.

### Return Values

An integer containing the size of the shared memory. This will be the
same size that was passed to the constructor.

### Examples

**Example \#1 <span class="function">SyncSharedMemory::size</span>
example**

``` php
<?php
$mem = new SyncSharedMemory("AppReportName", 1024);
var_dump($mem->size());
?>
```

The above example will output something similar to:

    int(1024)

### See Also

-   <span class="methodname">SyncSharedMemory::\_\_construct</span>
-   <span class="methodname">SyncSharedMemory::write</span>
-   <span class="methodname">SyncSharedMemory::read</span>

SyncSharedMemory::write
=======================

Copy data to named shared memory

### Description

<span class="modifier">public</span> <span
class="methodname">SyncSharedMemory::write</span> (\[ <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$start`<span class="initializer"> = 0</span></span> \]\] )

Copies data to named shared memory.

### Parameters

`string`  
The data to write to shared memoy.

> **Note**:
>
> If the size of the data exceeds the size of the shared memory, the
> number of bytes written returned will be less than the length of the
> input.

`start`  
The start/offset, in bytes, to begin writing.

> **Note**:
>
> If the value is negative, the starting position will begin at the
> specified number of bytes from the end of the shared memory segment.

### Return Values

An integer containing the number of bytes written to shared memory.

### Examples

**Example \#1 <span class="function">SyncSharedMemory::write</span>
example**

``` php
<?php
// You will probably need to protect shared memory with other synchronization objects.
// Shared memory goes away when the last reference to it disappears.
$mem = new SyncSharedMemory("AppReportName", 1024);
if ($mem->first())
{
    // Do first time initialization work here.
}

$result = $mem->write("report.txt");
var_dump($result);

$result = $mem->write("report.txt", -3);
var_dump($result);
?>
```

The above example will output something similar to:

    int(10)
    int(3)

### See Also

-   <span class="methodname">SyncSharedMemory::\_\_construct</span>
-   <span class="methodname">SyncSharedMemory::first</span>
-   <span class="methodname">SyncSharedMemory::write</span>
-   <span class="methodname">SyncSharedMemory::read</span>

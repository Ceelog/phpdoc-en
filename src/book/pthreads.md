pthreads
========

**Table of Contents**

-   [Introduction](/intro/pthreads.html)
-   [Installing/Configuring](/pthreads/setup.html)
    -   [Requirements](/pthreads/setup.html#Requirements)
    -   [Installation](/pthreads/setup.html#Installation)
    -   [Runtime
        Configuration](/pthreads/setup.html#Runtime%20Configuration)
-   [Predefined Constants](/pthreads/constants.html)
-   [Threaded](/class/threaded.html) — The Threaded class
    -   [Threaded::chunk](/class/threaded.html#Threaded::chunk) —
        Manipulation
    -   [Threaded::count](/class/threaded.html#Threaded::count) —
        Manipulation
    -   [Threaded::extend](/class/threaded.html#Threaded::extend) —
        Runtime Manipulation
    -   [Threaded::from](/class/threaded.html#Threaded::from) — Creation
    -   [Threaded::getTerminationInfo](/class/threaded.html#Threaded::getTerminationInfo)
        — Error Detection
    -   [Threaded::isRunning](/class/threaded.html#Threaded::isRunning)
        — State Detection
    -   [Threaded::isTerminated](/class/threaded.html#Threaded::isTerminated)
        — State Detection
    -   [Threaded::isWaiting](/class/threaded.html#Threaded::isWaiting)
        — State Detection
    -   [Threaded::lock](/class/threaded.html#Threaded::lock) —
        Synchronization
    -   [Threaded::merge](/class/threaded.html#Threaded::merge) —
        Manipulation
    -   [Threaded::notify](/class/threaded.html#Threaded::notify) —
        Synchronization
    -   [Threaded::notifyOne](/class/threaded.html#Threaded::notifyOne)
        — Synchronization
    -   [Threaded::pop](/class/threaded.html#Threaded::pop) —
        Manipulation
    -   [Threaded::run](/class/threaded.html#Threaded::run) — Execution
    -   [Threaded::shift](/class/threaded.html#Threaded::shift) —
        Manipulation
    -   [Threaded::synchronized](/class/threaded.html#Threaded::synchronized)
        — Synchronization
    -   [Threaded::unlock](/class/threaded.html#Threaded::unlock) —
        Synchronization
    -   [Threaded::wait](/class/threaded.html#Threaded::wait) —
        Synchronization
-   [Thread](/class/thread.html) — The Thread class
    -   [Thread::detach](/class/thread.html#Thread::detach) — Execution
    -   [Thread::getCreatorId](/class/thread.html#Thread::getCreatorId)
        — Identification
    -   [Thread::getCurrentThread](/class/thread.html#Thread::getCurrentThread)
        — Identification
    -   [Thread::getCurrentThreadId](/class/thread.html#Thread::getCurrentThreadId)
        — Identification
    -   [Thread::getThreadId](/class/thread.html#Thread::getThreadId) —
        Identification
    -   [Thread::globally](/class/thread.html#Thread::globally) —
        Execution
    -   [Thread::isJoined](/class/thread.html#Thread::isJoined) — State
        Detection
    -   [Thread::isStarted](/class/thread.html#Thread::isStarted) —
        State Detection
    -   [Thread::join](/class/thread.html#Thread::join) —
        Synchronization
    -   [Thread::kill](/class/thread.html#Thread::kill) — Execution
    -   [Thread::start](/class/thread.html#Thread::start) — Execution
-   [Worker](/class/worker.html) — The Worker class
    -   [Worker::collect](/class/worker.html#Worker::collect) — Collect
        references to completed tasks
    -   [Worker::getStacked](/class/worker.html#Worker::getStacked) —
        Gets the remaining stack size
    -   [Worker::isShutdown](/class/worker.html#Worker::isShutdown) —
        State Detection
    -   [Worker::isWorking](/class/worker.html#Worker::isWorking) —
        State Detection
    -   [Worker::shutdown](/class/worker.html#Worker::shutdown) —
        Shutdown the worker
    -   [Worker::stack](/class/worker.html#Worker::stack) — Stacking
        work
    -   [Worker::unstack](/class/worker.html#Worker::unstack) —
        Unstacking work
-   [Collectable](/class/collectable.html) — The Collectable interface
    -   [Collectable::isGarbage](/class/collectable.html#Collectable::isGarbage)
        — Determine whether an object has been marked as garbage
    -   [Collectable::setGarbage](/class/collectable.html#Collectable::setGarbage)
        — Mark an object as garbage
-   [Modifiers](/pthreads/modifiers.html) — Method Modifiers
-   [Pool](/class/pool.html) — The Pool class
    -   [Pool::collect](/class/pool.html#Pool::collect) — Collect
        references to completed tasks
    -   [Pool::\_\_construct](/class/pool.html#Pool::__construct) —
        Creates a new Pool of Workers
    -   [Pool::resize](/class/pool.html#Pool::resize) — Resize the Pool
    -   [Pool::shutdown](/class/pool.html#Pool::shutdown) — Shutdown all
        workers
    -   [Pool::submit](/class/pool.html#Pool::submit) — Submits an
        object for execution
    -   [Pool::submitTo](/class/pool.html#Pool::submitTo) — Submits a
        task to a specific worker for execution
-   [Mutex](/class/mutex.html) — The Mutex class
    -   [Mutex::create](/class/mutex.html#Mutex::create) — Create a
        Mutex
    -   [Mutex::destroy](/class/mutex.html#Mutex::destroy) — Destroy
        Mutex
    -   [Mutex::lock](/class/mutex.html#Mutex::lock) — Acquire Mutex
    -   [Mutex::trylock](/class/mutex.html#Mutex::trylock) — Attempt to
        Acquire Mutex
    -   [Mutex::unlock](/class/mutex.html#Mutex::unlock) — Release Mutex
-   [Cond](/class/cond.html) — The Cond class
    -   [Cond::broadcast](/class/cond.html#Cond::broadcast) — Broadcast
        a Condition
    -   [Cond::create](/class/cond.html#Cond::create) — Create a
        Condition
    -   [Cond::destroy](/class/cond.html#Cond::destroy) — Destroy a
        Condition
    -   [Cond::signal](/class/cond.html#Cond::signal) — Signal a
        Condition
    -   [Cond::wait](/class/cond.html#Cond::wait) — Wait for Condition
-   [Volatile](/class/volatile.html) — The Volatile class

Introduction
------------

Threaded objects form the basis of pthreads ability to execute user code
in parallel; they expose synchronization methods and various useful
interfaces.

Threaded objects, most importantly, provide implicit safety for the
programmer; all operations on the object scope are safe.

Class synopsis
--------------

**Threaded**

<span class="ooclass"> class **Threaded** </span> <span
class="oointerface">implements <span
class="interfacename">Collectable</span> </span> <span
class="oointerface">, <span class="interfacename">Traversable</span>
</span> <span class="oointerface">, <span
class="interfacename">Countable</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">chunk</span> ( <span class="methodparam"><span
class="type">int</span> `$size`</span> , <span class="methodparam"><span
class="type">bool</span> `$preserve`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">extend</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> )

<span class="modifier">public</span> <span class="type">Threaded</span>
<span class="methodname">from</span> ( <span class="methodparam"><span
class="type">Closure</span> `$run`</span> \[, <span
class="methodparam"><span class="type">Closure</span>
`$construct`</span> \[, <span class="methodparam"><span
class="type">array</span> `$args`</span> \]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getTerminationInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isRunning</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isTerminated</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isWaiting</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">lock</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">merge</span> ( <span class="methodparam"><span
class="type">mixed</span> `$from`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$overwrite`</span>
\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">notify</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">notifyOne</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">pop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">run</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">shift</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">synchronized</span> ( <span
class="methodparam"><span class="type">Closure</span> `$block`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$...`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unlock</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">wait</span> (\[ <span class="methodparam"><span
class="type">int</span> `$timeout`</span> \] )

}

Threaded::chunk
===============

Manipulation

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Threaded::chunk</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> , <span
class="methodparam"><span class="type">bool</span> `$preserve`</span> )

Fetches a chunk of the objects property table of the given size,
optionally preserving keys

### Parameters

`size`  
The number of items to fetch

`preserve`  
Preserve the keys of members, by default false

### Return Values

An array of items from the objects property table

### Examples

**Example \#1 Fetch a chunk of the property table**

``` php
<?php
$safe = new Threaded();

while (count($safe) < 10) {
    $safe[] = count($safe);
}

var_dump($safe->chunk(5));
?>
```

The above example will output:

    array(5) {
      [0]=>
      int(0)
      [1]=>
      int(1)
      [2]=>
      int(2)
      [3]=>
      int(3)
      [4]=>
      int(4)
    }

Threaded::count
===============

Manipulation

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Threaded::count</span> ( <span
class="methodparam">void</span> )

Returns the number of properties for this object

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 Counting the properties of an object**

``` php
<?php
$safe = new Threaded();

while (count($safe) < 10) {
    $safe[] = count($safe);
}

var_dump(count($safe));
?>
```

The above example will output:

    int(10)

Threaded::extend
================

Runtime Manipulation

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::extend</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> )

Makes thread safe standard class at runtime

### Parameters

`class`  
The class to extend

### Return Values

A boolean indication of success

### Examples

**Example \#1 Runtime inheritance**

``` php
<?php
class My {}

Threaded::extend(My::class);

$my = new My();

var_dump($my instanceof Threaded);
?>
```

The above example will output:

    bool(true)

Threaded::from
==============

Creation

**Warning**

This method has been removed in pthreads v3. With the introduction of
<a href="/language/oop5/anonymous.html" class="link">anonymous classes</a>
in PHP 7, these can now be used instead.

### Description

<span class="modifier">public</span> <span class="type">Threaded</span>
<span class="methodname">Threaded::from</span> ( <span
class="methodparam"><span class="type">Closure</span> `$run`</span> \[,
<span class="methodparam"><span class="type">Closure</span>
`$construct`</span> \[, <span class="methodparam"><span
class="type">array</span> `$args`</span> \]\] )

Creates an anonymous Threaded object from closures

### Parameters

`run`  
The closure to use for ::run

`construct`  
The constructor to use for anonymous object

`args`  
The arguments to pass to constructor

### Return Values

A new anonymous Threaded object

### Examples

**Example \#1 Thread safe objects from closures**

``` php
<?php
$pool = new Pool(4);
$pool->submit(Collectable::from(function(){
    echo "Hello World";
    $this->setGarbage();
}));
/* ... */
$pool->shutdown();
?>
```

The above example will output:

    Hello World

Threaded::getTerminationInfo
============================

Error Detection

**Warning**

This method has been removed in pthreads v3. Instead, the body of <span
class="methodname">Threaded::run</span> can be wrapped in a try...catch
block to detect errors (since most errors in PHP 7 have been converted
to exceptions).

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Threaded::getTerminationInfo</span> ( <span
class="methodparam">void</span> )

Retrieves terminal error information from the referenced object

### Parameters

This function has no parameters.

### Return Values

array containing the termination conditions of the referenced object

### Examples

**Example \#1 Detecting fatal errors in Threads**

``` php
<?php
class My extends Thread {
    public function run() {
        @not_found();
    }
}

$my = new My();
$my->start();
$my->join();

var_dump($my->isTerminated(), $my->getTerminationInfo());
?>
```

The above example will output:

    bool(true)
    array(4) {
      ["scope"]=>
      string(2) "My"
      ["function"]=>
      string(3) "run"
      ["file"]=>
      string(29) "/usr/src/pthreads/sandbox.php"
      ["line"]=>
      int(4)
    }

Threaded::isRunning
===================

State Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isRunning</span> ( <span
class="methodparam">void</span> )

Tell if the referenced object is executing

### Parameters

This function has no parameters.

### Return Values

A boolean indication of state

> **Note**:
>
> A object is considered running while executing the run method

### Examples

**Example \#1 Detect the state of the referenced object**

``` php
<?php
class My extends Thread {
    public function run() {
        $this->synchronized(function($thread){
            if (!$thread->done)
                $thread->wait();
        }, $this);
    }
}
$my = new My();
$my->start();
var_dump($my->isRunning());
$my->synchronized(function($thread){
    $thread->done = true;
    $thread->notify();
}, $my);
?>
```

The above example will output:

    bool(true)

Threaded::isTerminated
======================

State Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isTerminated</span> ( <span
class="methodparam">void</span> )

Tell if the referenced object was terminated during execution; suffered
fatal errors, or threw uncaught exceptions

### Parameters

This function has no parameters.

### Return Values

A boolean indication of state

### Examples

**Example \#1 Detect the state of the referenced object**

``` php
<?php
class My extends Thread {
    public function run() {
        i_do_not_exist();
    }
}
$my = new My();
$my->start();
$my->join();
var_dump($my->isTerminated());
?>
```

The above example will output:

    bool(true)

Threaded::isWaiting
===================

State Detection

**Warning**

This method has been removed in pthreads v3.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isWaiting</span> ( <span
class="methodparam">void</span> )

Tell if the referenced object is waiting for notification

### Parameters

This function has no parameters.

### Return Values

A boolean indication of state

### Examples

**Example \#1 Detect the state of the referenced object**

``` php
<?php
class My extends Thread {
    public function run() {
        $this->synchronized(function($thread){
            if (!$this->done)
                $thread->wait();
        }, $this);
    }
    
    protected $done;
}
$my = new My();
$my->start();
$my->synchronized(function($thread){
    var_dump(
        $thread->isWaiting());
    $thread->done = true;
    $thread->notify();
}, $my);
?>
```

The above example will output:

    bool(true)

Threaded::lock
==============

Synchronization

**Warning**

This method has been removed in pthreads v3. The <span
class="methodname">Threaded::synchronized</span> method should now be
used.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::lock</span> ( <span
class="methodparam">void</span> )

Lock the referenced objects property table

### Parameters

This function has no parameters.

### Return Values

A boolean indication of success

### Examples

**Example \#1 Locking Object Properties**

``` php
<?php
class My extends Thread {
    public function run() {
        var_dump($this->lock());
        /** nobody can read or write **/
        var_dump($this->unlock());
        /** reading / writing resumed for all other contexts */
    }
}
$my = new My();
$my->start();
?>
```

The above example will output:

    bool(true)
    bool(true)

Threaded::merge
===============

Manipulation

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::merge</span> ( <span
class="methodparam"><span class="type">mixed</span> `$from`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$overwrite`</span> \] )

Merges data into the current object

### Parameters

`from`  
The data to merge

`overwrite`  
Overwrite existing keys, by default true

### Return Values

A boolean indication of success

### Examples

**Example \#1 Merging into the property table of a threaded object**

``` php
<?php
$array = [];

while (count($array) < 10)
    $array[] = count($array);

$stdClass = new stdClass();
$stdClass->foo = "foo";
$stdClass->bar = "bar";
$stdClass->baz = "baz";

$safe = new Threaded();
$safe->merge($array);

$safe->foo = "bar";
$safe->merge($stdClass, false);

var_dump($safe);
?>
```

The above example will output:

    object(Threaded)#2 (13) {
      ["0"]=>
      int(0)
      ["1"]=>
      int(1)
      ["2"]=>
      int(2)
      ["3"]=>
      int(3)
      ["4"]=>
      int(4)
      ["5"]=>
      int(5)
      ["6"]=>
      int(6)
      ["7"]=>
      int(7)
      ["8"]=>
      int(8)
      ["9"]=>
      int(9)
      ["foo"]=>
      string(3) "bar"
      ["bar"]=>
      string(3) "bar"
      ["baz"]=>
      string(3) "baz"
    }

Threaded::notify
================

Synchronization

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::notify</span> ( <span
class="methodparam">void</span> )

Send notification to the referenced object

### Parameters

This function has no parameters.

### Return Values

A boolean indication of success

### Examples

**Example \#1 Notifications and Waiting**

``` php
<?php
class My extends Thread {
    public function run() {
        /** cause this thread to wait **/
        $this->synchronized(function($thread){
            if (!$thread->done)
                $thread->wait();
        }, $this);
    }
}
$my = new My();
$my->start();
/** send notification to the waiting thread **/
$my->synchronized(function($thread){
    $thread->done = true;
    $thread->notify();
}, $my);
var_dump($my->join());
?>
```

The above example will output:

    bool(true)

Threaded::notifyOne
===================

Synchronization

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::notifyOne</span> ( <span
class="methodparam">void</span> )

Send notification to the referenced object. This unblocks at least one
of the blocked threads (as opposed to unblocking all of them, as seen
with <span class="methodname">Threaded::notify</span>).

### Parameters

This function has no parameters.

### Return Values

A boolean indication of success

### Examples

**Example \#1 Notifications and Waiting**

``` php
<?php
class My extends Thread {
    public function run() {
        /** cause this thread to wait **/
        $this->synchronized(function($thread){
            if (!$thread->done)
                $thread->wait();
        }, $this);
    }
}
$my = new My();
$my->start();
/** send notification to the waiting thread **/
$my->synchronized(function($thread){
    $thread->done = true;
    $thread->notifyOne();
}, $my);
var_dump($my->join());
?>
```

The above example will output:

    bool(true)

Threaded::pop
=============

Manipulation

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::pop</span> ( <span
class="methodparam">void</span> )

Pops an item from the objects property table

### Return Values

The last item from the objects property table

### Examples

**Example \#1 Popping the last item from the property table of a
threaded object**

``` php
<?php
$safe = new Threaded();

while (count($safe) < 10)
    $safe[] = count($safe);

var_dump($safe->pop());
?>
```

The above example will output:

    int(9)

Threaded::run
=============

Execution

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Threaded::run</span> ( <span
class="methodparam">void</span> )

The programmer should always implement the run method for objects that
are intended for execution.

### Parameters

This function has no parameters.

### Return Values

The methods return value, if used, will be ignored

Threaded::shift
===============

Manipulation

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Threaded::shift</span> ( <span
class="methodparam">void</span> )

Shifts an item from the objects property table

### Return Values

The first item from the objects property table

### Examples

**Example \#1 Shifting the first item from the property table of a
threaded object**

``` php
<?php
$safe = new Threaded();

while (count($safe) < 10)
    $safe[] = count($safe);

var_dump($safe->shift());
?>
```

The above example will output:

    int(0)

Threaded::synchronized
======================

Synchronization

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Threaded::synchronized</span> ( <span
class="methodparam"><span class="type">Closure</span> `$block`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$...`</span> \] )

Executes the block while retaining the referenced objects
synchronization lock for the calling context

### Parameters

`block`  
The block of code to execute

`...`  
Variable length list of arguments to use as function arguments to the
block

### Return Values

The return value from the block

### Examples

**Example \#1 Synchronizing**

``` php
<?php
class My extends Thread {
    public function run() {
        $this->synchronized(function($thread){
            if (!$thread->done)
                $thread->wait();
        }, $this);
    }
}
$my = new My();
$my->start();
$my->synchronized(function($thread){
    $thread->done = true;
    $thread->notify();
}, $my);
var_dump($my->join());
?>
```

The above example will output:

    bool(true)

Threaded::unlock
================

Synchronization

**Warning**

This method has been removed in pthreads v3. The <span
class="methodname">Threaded::synchronized</span> method should now be
used.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::unlock</span> ( <span
class="methodparam">void</span> )

Unlock the referenced objects storage for the calling context

### Parameters

This function has no parameters.

### Return Values

A boolean indication of success

### Examples

**Example \#1 Locking the property table of a threaded object**

``` php
<?php
class My extends Thread {
    public function run() {
        var_dump($this->lock());
        /** nobody can read or write **/
        var_dump($this->unlock());
        /** reading / writing resumed for all other contexts */
    }
}
$my = new My();
$my->start();
?>
```

The above example will output:

    bool(true)
    bool(true)

Threaded::wait
==============

Synchronization

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::wait</span> (\[ <span
class="methodparam"><span class="type">int</span> `$timeout`</span> \] )

Will cause the calling context to wait for notification from the
referenced object

### Parameters

`timeout`  
An optional timeout in microseconds

### Return Values

A boolean indication of success

### Examples

**Example \#1 Notifications and Waiting**

``` php
<?php
class My extends Thread {
    public function run() {
        /** cause this thread to wait **/
        $this->synchronized(function($thread){
            if (!$thread->done)
                $thread->wait();
        }, $this);
    }
}
$my = new My();
$my->start();
/** send notification to the waiting thread **/
$my->synchronized(function($thread){
    $thread->done = true;
    $thread->notify();
}, $my);
var_dump($my->join());
?>
```

The above example will output:

    bool(true)

Introduction
------------

When the start method of a Thread is invoked, the run method code will
be executed in separate Thread, in parallel.

After the run method is executed the Thread will exit immediately, it
will be joined with the creating Thread at the appropriate time.

**Warning**

Relying on the engine to determine when a Thread should join may cause
undesirable behaviour; the programmer should be explicit, where
possible.

Class synopsis
--------------

**Thread**

<span class="ooclass"> class **Thread** </span> <span class="ooclass">
<span class="modifier">extends</span> **Threaded** </span> <span
class="oointerface">implements <span
class="interfacename">Countable</span> </span> <span
class="oointerface">, <span class="interfacename">Traversable</span>
</span> <span class="oointerface">, <span
class="interfacename">ArrayAccess</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">detach</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getCreatorId</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">Thread</span> <span
class="methodname">getCurrentThread</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">getCurrentThreadId</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getThreadId</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">globally</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isJoined</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isStarted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">join</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">kill</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">start</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`</span> \] )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Threaded::chunk</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> , <span
class="methodparam"><span class="type">bool</span> `$preserve`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Threaded::count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::extend</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> )

<span class="modifier">public</span> <span class="type">Threaded</span>
<span class="methodname">Threaded::from</span> ( <span
class="methodparam"><span class="type">Closure</span> `$run`</span> \[,
<span class="methodparam"><span class="type">Closure</span>
`$construct`</span> \[, <span class="methodparam"><span
class="type">array</span> `$args`</span> \]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Threaded::getTerminationInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isRunning</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isTerminated</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isWaiting</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::lock</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::merge</span> ( <span
class="methodparam"><span class="type">mixed</span> `$from`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$overwrite`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::notify</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::notifyOne</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::pop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Threaded::run</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Threaded::shift</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Threaded::synchronized</span> ( <span
class="methodparam"><span class="type">Closure</span> `$block`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$...`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::unlock</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::wait</span> (\[ <span
class="methodparam"><span class="type">int</span> `$timeout`</span> \] )

}

Thread::detach
==============

Execution

**Warning**

This method has been removed in pthreads v3.

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Thread::detach</span> ( <span
class="methodparam">void</span> )

Detaches the referenced Thread from the calling context, dangerous!

**Warning**

This method can cause undefined, unsafe behaviour. It should not usually
be used, it is present for completeness and advanced use cases.

### Parameters

This function has no parameters.

### Return Values

Thread::getCreatorId
====================

Identification

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Thread::getCreatorId</span> ( <span
class="methodparam">void</span> )

Will return the identity of the Thread that created the referenced
Thread

### Parameters

This function has no parameters.

### Return Values

A numeric identity

### Examples

**Example \#1 Return the identity of the Thread or Process that created
the referenced Thread**

``` php
<?php
class My extends Thread {
    public function run() {
        printf("%s created by Thread #%lu\n", __CLASS__, $this->getCreatorId());
    }
}
$my = new My();
$my->start();
?>
```

The above example will output:

    My created by Thread #123456778899

Thread::getCurrentThread
========================

Identification

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">Thread</span> <span
class="methodname">Thread::getCurrentThread</span> ( <span
class="methodparam">void</span> )

Return a reference to the currently executing Thread

### Parameters

This function has no parameters.

### Return Values

An object representing the currently executing Thread

### Examples

**Example \#1 Return the currently executing Thread**

``` php
<?php
class My extends Thread {
    public function run() {
        var_dump(Thread::getCurrentThread());
    }
}
$my = new My();
$my->start();
?>
```

The above example will output:

    object(My)#2 (0) {
    }

Thread::getCurrentThreadId
==========================

Identification

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Thread::getCurrentThreadId</span> ( <span
class="methodparam">void</span> )

Will return the identity of the currently executing Thread

### Parameters

This function has no parameters.

### Return Values

A numeric identity

### Examples

**Example \#1 Return the identity of the currently executing Thread**

``` php
<?php
class My extends Thread {
    public function run() {
        printf("%s is Thread #%lu\n", __CLASS__, Thread::getCurrentThreadId());
    }
}
$my = new My();
$my->start();
?>
```

The above example will output:

    My is Thread #123456778899

Thread::getThreadId
===================

Identification

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Thread::getThreadId</span> ( <span
class="methodparam">void</span> )

Will return the identity of the referenced Thread

### Parameters

This function has no parameters.

### Return Values

A numeric identity

### Examples

**Example \#1 Return the identity of the referenced Thread**

``` php
<?php
class My extends Thread {
    public function run() {
        printf("%s is Thread #%lu\n", __CLASS__, $this->getThreadId());
    }
}
$my = new My();
$my->start();
?>
```

The above example will output:

    My is Thread #123456778899

Thread::globally
================

Execution

**Warning**

This method has been removed in pthreads v3.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">Thread::globally</span> ( <span
class="methodparam">void</span> )

Will execute a Callable in the global scope

### Parameters

This function has no parameters.

### Return Values

The return value of the Callable

### Examples

**Example \#1 Execute in the global scope**

``` php
<?php
class My extends Thread {
    public function run() {
        global $std;
        
        Thread::globally(function(){
            $std = new stdClass;
        });
        
        var_dump($std);
    }
}
$my = new My();
$my->start();
?>
```

The above example will output:

    object(stdClass)#3 (0) {
    }

Thread::isJoined
================

State Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Thread::isJoined</span> ( <span
class="methodparam">void</span> )

Tell if the referenced Thread has been joined

### Parameters

This function has no parameters.

### Return Values

A boolean indication of state

### Examples

**Example \#1 Detect the state of the referenced Thread**

``` php
<?php
class My extends Thread {
    public function run() {
        $this->synchronized(function($thread){
            if (!$thread->done)
                $thread->wait();
        }, $this);
    }
}
$my = new My();
$my->start();
var_dump($my->isJoined());
$my->synchronized(function($thread){
    $thread->done = true;
    $thread->notify();
}, $my);
?>
```

The above example will output:

    bool(false)

Thread::isStarted
=================

State Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Thread::isStarted</span> ( <span
class="methodparam">void</span> )

Tell if the referenced Thread was started

### Parameters

This function has no parameters.

### Return Values

boolean indication of state

### Examples

**Example \#1 Tell if the referenced Thread was started**

``` php
<?php
$worker = new Worker();
$worker->start();
var_dump($worker->isStarted());
?>
```

The above example will output:

    bool(true)

Thread::join
============

Synchronization

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Thread::join</span> ( <span
class="methodparam">void</span> )

Causes the calling context to wait for the referenced Thread to finish
executing

### Parameters

This function has no parameters.

### Return Values

A boolean indication of success

### Examples

**Example \#1 Join with the referenced Thread**

``` php
<?php
class My extends Thread {
    public function run() {
        /* ... */
    }
}
$my = new My();
$my->start();
/* ... */
var_dump($my->join());
/* ... */
?>
```

The above example will output:

    bool(true)

Thread::kill
============

Execution

**Warning**

This method has been removed in pthreads v3.

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Thread::kill</span> ( <span
class="methodparam">void</span> )

Forces the referenced Thread to terminate

**Warning**

The programmer should not ordinarily kill Threads by force

### Parameters

This function has no parameters.

### Return Values

A boolean indication of success

### Examples

**Example \#1 Kill the referenced Thread**

``` php
<?php
class T extends Thread {
    public function run() {
        $stdin = fopen("php://stdin", "r");
        while(($line = fgets($stdin))) {
            echo $line;
        }
    }
}

$t = new T();
$t->start();

var_dump($t->kill());
?>
```

The above example will output:

    bool(true)

Thread::start
=============

Execution

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Thread::start</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`</span> \] )

Will start a new Thread to execute the implemented run method

### Parameters

`options`  
An optional mask of inheritance constants, by default
PTHREADS\_INHERIT\_ALL

### Return Values

A boolean indication of success

### Examples

**Example \#1 Starting Threads**

``` php
<?php
class My extends Thread {
    public function run() {
        /** ... **/
    }
}
$my = new My();
var_dump($my->start());
?>
```

The above example will output:

    bool(true)

Introduction
------------

Worker Threads have a persistent context, as such should be used over
Threads in most cases.

When a Worker is started, the run method will be executed, but the
Thread will not leave until one of the following conditions are met:

-   the Worker goes out of scope (no more references remain)

-   the programmer calls shutdown

-   the script dies

This means the programmer can reuse the context throughout execution;
placing objects on the stack of the Worker will cause the Worker to
execute the stacked objects run method.

Class synopsis
--------------

**Worker**

<span class="ooclass"> class **Worker** </span> <span class="ooclass">
<span class="modifier">extends</span> **Thread** </span> <span
class="oointerface">implements <span
class="interfacename">Traversable</span> </span> <span
class="oointerface">, <span class="interfacename">Countable</span>
</span> <span class="oointerface">, <span
class="interfacename">ArrayAccess</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">collect</span> (\[ <span class="methodparam"><span
class="type">Callable</span> `$collector`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStacked</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isShutdown</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isWorking</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">shutdown</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">stack</span> ( <span class="methodparam"><span
class="type">Threaded</span> `&$work`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">unstack</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Thread::detach</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Thread::getCreatorId</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">Thread</span> <span
class="methodname">Thread::getCurrentThread</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Thread::getCurrentThreadId</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Thread::getThreadId</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">Thread::globally</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Thread::isJoined</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Thread::isStarted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Thread::join</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Thread::kill</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Thread::start</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`</span> \] )

}

Worker::collect
===============

Collect references to completed tasks

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Worker::collect</span> (\[ <span
class="methodparam"><span class="type">Callable</span>
`$collector`</span> \] )

Allows the worker to collect references determined to be garbage by the
optionally given collector.

### Parameters

`collector`  
A Callable collector that returns a boolean on whether the task can be
collected or not. Only in rare cases should a custom collector need to
be used.

### Return Values

The number of remaining tasks on the worker's stack to be collected.

### Examples

**Example \#1 A basic example of <span
class="methodname">Worker::collect</span>**

``` php
<?php
$worker = new Worker();

echo "There are currently {$worker->collect()} tasks on the stack to be collected\n";

for ($i = 0; $i < 15; ++$i) {
    $worker->stack(new class extends Threaded {});
}

echo "There are {$worker->collect()} tasks remaining on the stack to be collected\n";

$worker->start();

while ($worker->collect()); // blocks until all tasks have finished executing

echo "There are now {$worker->collect()} tasks on the stack to be collected\n";

$worker->shutdown();
```

The above example will output:

    There are currently 0 tasks on the stack to be collected
    There are 15 tasks remaining on the stack to be collected
    There are now 0 tasks on the stack to be collected

Worker::getStacked
==================

Gets the remaining stack size

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Worker::getStacked</span> ( <span
class="methodparam">void</span> )

Returns the number of tasks left on the stack

### Parameters

This function has no parameters.

### Return Values

Returns the number of tasks currently waiting to be executed by the
worker

### Examples

**Example \#1 A basic example of <span
class="classname">Worker::getStacked</span>**

``` php
<?php
$worker = new Worker();

for ($i = 0; $i < 5; ++$i) {
    $worker->stack(new class extends Threaded {});
}

echo "There are {$worker->getStacked()} stacked tasks\n";
```

The above example will output:

    There are 5 stacked tasks

Worker::isShutdown
==================

State Detection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Worker::isShutdown</span> ( <span
class="methodparam">void</span> )

Whether the worker has been shutdown or not.

### Parameters

This function has no parameters.

### Return Values

Returns whether the worker has been shutdown or not.

### Examples

**Example \#1 Detect the state of a worker**

``` php
<?php
$worker = new Worker();
$worker->start();

var_dump($worker->isShutdown());

$worker->shutdown();

var_dump($worker->isShutdown());
```

The above example will output:

    bool(false)
    bool(true)

Worker::isWorking
=================

State Detection

**Warning**

This method has been removed in pthreads v3. The <span
class="methodname">Worker::getStacked</span> method should be used to
see if the worker still has tasks to execute.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Worker::isWorking</span> ( <span
class="methodparam">void</span> )

Tell if a Worker is executing Stackables

### Parameters

This function has no parameters.

### Return Values

A boolean indication of state

### Examples

**Example \#1 Detect the state of a Worker**

``` php
<?php
$my = new Worker();
$my->start();
/* ... */
if ($my->isWorking()) {
    /* ... the Worker is busy executing another object */
}
?>
```

Worker::shutdown
================

Shutdown the worker

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Worker::shutdown</span> ( <span
class="methodparam">void</span> )

Shuts down the worker after executing all of the stacked tasks.

### Parameters

This function has no parameters.

### Return Values

Whether the worker was successfully shutdown or not.

### Examples

**Example \#1 Shutdown the referenced worker**

``` php
<?php
$my = new Worker();
$my->start();
/* stack/execute tasks */
var_dump($my->shutdown());
```

The above example will output:

    bool(true)

Worker::stack
=============

Stacking work

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Worker::stack</span> ( <span
class="methodparam"><span class="type">Threaded</span> `&$work`</span> )

Appends the new work to the stack of the referenced worker.

### Parameters

`work`  
A <span class="classname">Threaded</span> object to be executed by the
worker.

### Return Values

The new size of the stack.

### Examples

**Example \#1 Stacking a task for execution onto a worker**

``` php
<?php
$worker = new Worker();
$work = new class extends Threaded {};

var_dump($worker->stack($work));
```

The above example will output:

    int(1)

Worker::unstack
===============

Unstacking work

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Worker::unstack</span> ( <span
class="methodparam">void</span> )

Removes the first task (the oldest one) in the stack.

### Parameters

This function has no parameters.

### Return Values

The new size of the stack.

### Changelog

| Version | Description                                                                                                      |
|---------|------------------------------------------------------------------------------------------------------------------|
| v3      | The parameter to specify the task to unstack has been removed. Now, only the first task in the stack is removed. |

### Examples

**Example \#1 Removing objects from the stack of Workers**

``` php
<?php
$my = new Worker();
$work = new class extends Threaded {};

var_dump($my->stack($work));
var_dump($my->unstack());
```

The above example will output:

    int(1)
    int(0)

Introduction
------------

**Caution**

<span class="classname">Collectable</span> was previously a class (in
pthreads v2 and below). Now, it is an interface in pthreads v3 that is
implemented by the <span class="classname">Threaded</span> class.

Represents a garbage-collectable object.

Interface synopsis
------------------

**Collectable**

<span class="ooclass"> class **Collectable** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isGarbage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setGarbage</span> ( <span
class="methodparam">void</span> )

}

Collectable::isGarbage
======================

Determine whether an object has been marked as garbage

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Collectable::isGarbage</span> ( <span
class="methodparam">void</span> )

Can be called in <span class="methodname">Pool::collect</span> to
determine if this object is garbage.

### See Also

-   <span class="methodname">Pool::collect</span>

Collectable::setGarbage
=======================

Mark an object as garbage

**Warning**

This method has been removed in pthreads v3.

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Collectable::setGarbage</span> ( <span
class="methodparam">void</span> )

Should be called once per object when the object is finished being
executed or referenced.

### See Also

-   <span class="methodname">Collectable::isGarbage</span>

Introduction
------------

A Pool is a container for, and controller of, an adjustable number of
Workers.

Pooling provides a higher level abstraction of the Worker functionality,
including the management of references in the way required by pthreads.

Class synopsis
--------------

**Pool**

<span class="ooclass"> class **Pool** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$size` ;

<span class="modifier">protected</span> `$class` ;

<span class="modifier">protected</span> `$workers` ;

<span class="modifier">protected</span> `$ctor` ;

<span class="modifier">protected</span> `$last` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">collect</span> (\[ <span class="methodparam"><span
class="type">Callable</span> `$collector`</span> \] )

<span class="modifier">public</span> <span class="type">Pool</span>
<span class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$class`</span> \[, <span class="methodparam"><span
class="type">array</span> `$ctor`</span> \]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">resize</span> ( <span class="methodparam"><span
class="type">int</span> `$size`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">shutdown</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">submit</span> ( <span class="methodparam"><span
class="type">Threaded</span> `$task`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">submitTo</span> ( <span class="methodparam"><span
class="type">int</span> `$worker`</span> , <span
class="methodparam"><span class="type">Threaded</span> `$task`</span> )

}

Properties
----------

`size`  
maximum number of Workers this Pool can use

`class`  
the class of the Worker

`workers`  
references to Workers

`ctor`  
the arguments for constructor of new Workers

`last`  
offset in workers of the last Worker used

Pool::collect
=============

Collect references to completed tasks

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Pool::collect</span> (\[ <span
class="methodparam"><span class="type">Callable</span>
`$collector`</span> \] )

Allows the pool to collect references determined to be garbage by the
optionally given collector.

### Parameters

`collector`  
A Callable collector that returns a boolean on whether the task can be
collected or not. Only in rare cases should a custom collector need to
be used.

### Return Values

The number of remaining tasks in the pool to be collected.

### Changelog

| Version | Description                                                                |
|---------|----------------------------------------------------------------------------|
| v3      | An integer is now returned, and the `collector` parameter is now optional. |

### Examples

**Example \#1 A basic example of <span
class="methodname">Pool::collect</span>**

``` php
<?php
$pool = new Pool(4);

for ($i = 0; $i < 15; ++$i) {
    $pool->submit(new class extends Threaded {});
}

while ($pool->collect()); // blocks until all tasks have finished executing

$pool->shutdown();
```

Pool::\_\_construct
===================

Creates a new Pool of Workers

### Description

<span class="modifier">public</span> <span class="type">Pool</span>
<span class="methodname">Pool::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$class`</span> \[, <span class="methodparam"><span
class="type">array</span> `$ctor`</span> \]\] )

Construct a new pool of workers. Pools lazily create their threads,
which means new threads will only be spawned when they are required to
execute tasks.

### Parameters

`size`  
The maximum number of workers for this pool to create

`class`  
The class for new Workers. If no class is given, then it defaults to the
<span class="classname">Worker</span> class.

`ctor`  
An array of arguments to be passed to new workers' constructors

### Return Values

The new pool

### Examples

**Example \#1 Creating Pools**

``` php
<?php
class MyWorker extends Worker {
    
    public function __construct(Something $something) {
        $this->something = $something;
    }
    
    public function run() {
        /** ... **/
    }
}

$pool = new Pool(8, \MyWorker::class, [new Something()]);

var_dump($pool);
?>
```

The above example will output:

    object(Pool)#1 (6) {
      ["size":protected]=>
      int(8)
      ["class":protected]=>
      string(8) "MyWorker"
      ["workers":protected]=>
      NULL
      ["work":protected]=>
      NULL
      ["ctor":protected]=>
      array(1) {
        [0]=>
        object(Something)#2 (0) {
        }
      }
      ["last":protected]=>
      int(0)
    }

Pool::resize
============

Resize the Pool

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Pool::resize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

Resize the Pool

### Parameters

`size`  
The maximum number of Workers this Pool can create

### Return Values

void

Pool::shutdown
==============

Shutdown all workers

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Pool::shutdown</span> ( <span
class="methodparam">void</span> )

Shuts down all of the workers in the pool. This will block until all
submitted tasks have been executed.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 Shutting down a pool**

``` php
<?php
class Task extends Threaded
{
    public function run()
    {
        usleep(500000);
    }
}

$pool = new Pool(4);

for ($i = 0; $i < 10; ++$i) {
    $pool->submit(new Task());
}

$pool->shutdown(); // blocks until all submitted tasks have finished executing
```

Pool::submit
============

Submits an object for execution

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Pool::submit</span> ( <span class="methodparam"><span
class="type">Threaded</span> `$task`</span> )

Submit the task to the next Worker in the Pool

### Parameters

`task`  
The task for execution

### Return Values

the identifier of the Worker executing the object

### Examples

**Example \#1 Submitting Tasks**

``` php
<?php
class MyWork extends Threaded {
    
    public function run() {
        /* ... */
    }
}

class MyWorker extends Worker {
    
    public function __construct(Something $something) {
        $this->something = $something;
    }
    
    public function run() {
        /** ... **/
    }
}

$pool = new Pool(8, \MyWorker::class, [new Something()]);
$pool->submit(new MyWork());
var_dump($pool);
?>
```

The above example will output:

    object(Pool)#1 (6) {
      ["size":protected]=>
      int(8)
      ["class":protected]=>
      string(8) "MyWorker"
      ["workers":protected]=>
      array(1) {
        [0]=>
        object(MyWorker)#4 (1) {
          ["something"]=>
          object(Something)#5 (0) {
          }
        }
      }
      ["work":protected]=>
      array(1) {
        [0]=>
        object(MyWork)#3 (1) {
          ["worker"]=>
          object(MyWorker)#5 (1) {
            ["something"]=>
            object(Something)#6 (0) {
            }
          }
        }
      }
      ["ctor":protected]=>
      array(1) {
        [0]=>
        object(Something)#2 (0) {
        }
      }
      ["last":protected]=>
      int(1)
    }

Pool::submitTo
==============

Submits a task to a specific worker for execution

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Pool::submitTo</span> ( <span
class="methodparam"><span class="type">int</span> `$worker`</span> ,
<span class="methodparam"><span class="type">Threaded</span>
`$task`</span> )

Submit a task to the specified worker in the pool. The workers are
indexed from 0, and will only exist if the pool has needed to create
them (since threads are lazily spawned).

### Parameters

`worker`  
The worker to stack the task onto, indexed from *0*.

`task`  
The task for execution.

### Return Values

The identifier of the worker that accepted the task.

### Examples

**Example \#1 Submitting tasks to a specific worker**

``` php
<?php
class Task extends Threaded {
    public function run() {
        var_dump(Thread::getCurrentThreadID());
    }
}

$pool = new Pool(2);

$pool->submit(new Task());

for ($i = 0; $i < 5; ++$i) {
    $pool->submitTo(0, new Task()); // stack all tasks onto the first worker
}

$pool->submitTo(1, new Task()); // cannot stack the task onto the second worker due to it not existing yet

$pool->shutdown();
```

The above example will output:

    int(4475011072)
    int(4475011072)
    int(4475011072)
    int(4475011072)
    int(4475011072)
    int(4475011072)

    Fatal error: Uncaught Exception: The selected worker (1) does not exist in %s:%d

Introduction
------------

**Warning**

The <span class="classname">Mutex</span> class has been removed in
pthreads v3.

The static methods contained in the Mutex class provide direct access to
Posix Mutex functionality.

Class synopsis
--------------

**Mutex**

<span class="ooclass"> class **Mutex** </span> {

/\* Methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">int</span> <span
class="methodname">create</span> (\[ <span class="methodparam"> <span
class="type">bool</span> `$lock` </span> \] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">destroy</span> ( <span class="methodparam">
<span class="type">int</span> `$mutex` </span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">lock</span> ( <span class="methodparam"> <span
class="type">int</span> `$mutex` </span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">trylock</span> ( <span class="methodparam">
<span class="type">int</span> `$mutex` </span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">unlock</span> ( <span class="methodparam">
<span class="type">int</span> `$mutex` </span> \[, <span
class="methodparam"> <span class="type">bool</span> `$destroy` </span>
\] )

}

Mutex::create
=============

Create a Mutex

**Warning**

The <span class="classname">Mutex</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Mutex::create</span> (\[ <span class="methodparam">
<span class="type">bool</span> `$lock` </span> \] )

Create, and optionally lock a new Mutex for the caller

### Parameters

`lock`  
Setting lock to true will lock the Mutex for the caller before returning
the handle

### Return Values

A newly created and optionally locked Mutex handle

### Examples

**Example \#1 Mutex Creation and Destruction**

``` php
<?php
/** You cannot use the "new" keyword, a Mutex is not a PHP object **/
$mutex = Mutex::create();
/** You have the physical address of the Mutex **/
var_dump($mutex);
/** Always destroy mutex you have created **/
Mutex::destroy($mutex);
?>
```

The above example will output:

    int(40096976)

Mutex::destroy
==============

Destroy Mutex

**Warning**

The <span class="classname">Mutex</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">Mutex::destroy</span> ( <span
class="methodparam"> <span class="type">int</span> `$mutex` </span> )

Destroying Mutex handles must be carried out explicitly by the
programmer when they are finished with the Mutex handle.

### Parameters

`mutex`  
A handle returned by a previous call to <span
class="function">Mutex::create</span>. The handle should not be locked
by any Thread when <span class="function">Mutex::destroy</span> is
called.

### Return Values

A boolean indication of success

### Examples

**Example \#1 Mutex Creation and Destruction**

``` php
<?php
/** You cannot use the "new" keyword, a Mutex is not a PHP object **/
$mutex = Mutex::create();
/** You have the physical address of the Mutex **/
var_dump($mutex);
/** Always destroy mutex you have created **/
Mutex::destroy($mutex);
?>
```

The above example will output:

    int(40096976)

Mutex::lock
===========

Acquire Mutex

**Warning**

The <span class="classname">Mutex</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">Mutex::lock</span> ( <span class="methodparam">
<span class="type">int</span> `$mutex` </span> )

Attempt to lock the Mutex for the caller.

An attempt to lock a Mutex owned (locked) by another Thread will result
in blocking.

### Parameters

`mutex`  
A handle returned by a previous call to <span
class="function">Mutex::create</span>.

### Return Values

A boolean indication of success.

### Examples

**Example \#1 Mutex Locking and Unlocking**

``` php
<?php
/** You cannot use the "new" keyword, a Mutex is not a PHP object **/
$mutex = Mutex::create();
/** You can now lock the mutex in any context **/
var_dump(Mutex::lock($mutex));
/** It is invalid to attempt to destroy a locked Mutex **/
var_dump(Mutex::unlock($mutex));
/** Always destroy mutex you have created **/
Mutex::destroy($mutex);
?>
```

The above example will output:

    bool(true)
    bool(true)

Mutex::trylock
==============

Attempt to Acquire Mutex

**Warning**

The <span class="classname">Mutex</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">Mutex::trylock</span> ( <span
class="methodparam"> <span class="type">int</span> `$mutex` </span> )

Attempt to lock the Mutex for the caller without blocking if the Mutex
is owned (locked) by another Thread.

### Parameters

`mutex`  
A handle returned by a previous call to <span
class="function">Mutex::create</span>.

### Return Values

A boolean indication of success.

### Examples

**Example \#1 Mutex Locking and Unlocking**

``` php
<?php
/** You cannot use the "new" keyword, a Mutex is not a PHP object **/
$mutex = Mutex::create();
/** You can now try to lock the mutex in any context **/
var_dump(Mutex::trylock($mutex));
/** It is invalid to attempt to destroy a locked Mutex **/
var_dump(Mutex::unlock($mutex));
/** Always destroy mutex you have created **/
Mutex::destroy($mutex);
?>
```

The above example will output:

    bool(true)
    bool(true)

Mutex::unlock
=============

Release Mutex

**Warning**

The <span class="classname">Mutex</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">Mutex::unlock</span> ( <span
class="methodparam"> <span class="type">int</span> `$mutex` </span> \[,
<span class="methodparam"> <span class="type">bool</span> `$destroy`
</span> \] )

Attempts to unlock the Mutex for the caller, optionally destroying the
Mutex handle. The calling thread should own the Mutex at the time of the
call.

### Parameters

`mutex`  
A handle returned by a previous call to <span
class="function">Mutex::create</span>.

`destroy`  
When true pthreads will destroy the Mutex after a successful unlock.

### Return Values

A boolean indication of success.

### Examples

**Example \#1 Mutex Locking and Unlocking**

``` php
<?php
/** You cannot use the "new" keyword, a Mutex is not a PHP object **/
$mutex = Mutex::create();
/** You can now lock the mutex in any context **/
var_dump(Mutex::lock($mutex));
/** It is invalid to attempt to destroy a locked Mutex **/
var_dump(Mutex::unlock($mutex));
/** Always destroy mutex you have created **/
Mutex::destroy($mutex);
?>
```

The above example will output:

    bool(true)
    bool(true)

Introduction
------------

**Warning**

The <span class="classname">Cond</span> class has been removed in
pthreads v3.

The static methods contained in the Cond class provide direct access to
Posix Condition Variables.

Class synopsis
--------------

**Cond**

<span class="ooclass"> class **Cond** </span> {

/\* Methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">broadcast</span> ( <span class="methodparam">
<span class="type">int</span> `$condition` </span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">int</span> <span
class="methodname">create</span> ( <span class="methodparam">void</span>
)

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">destroy</span> ( <span class="methodparam">
<span class="type">int</span> `$condition` </span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">signal</span> ( <span class="methodparam">
<span class="type">int</span> `$condition` </span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">wait</span> ( <span class="methodparam"> <span
class="type">int</span> `$condition` </span> , <span
class="methodparam"> <span class="type">int</span> `$mutex` </span> \[,
<span class="methodparam"> <span class="type">int</span> `$timeout`
</span> \] )

}

Cond::broadcast
===============

Broadcast a Condition

**Warning**

The <span class="classname">Cond</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">Cond::broadcast</span> ( <span
class="methodparam"> <span class="type">int</span> `$condition` </span>
)

Broadcast to all Threads blocking on a call to <span
class="function">Cond::wait</span>.

### Parameters

`condition`  
A handle to a Condition Variable returned by a previous call to <span
class="function">Cond::create</span>

### Return Values

A boolean indication of success.

### Examples

**Example \#1 Condition Broadcasting**

``` php
<?php
/** You cannot use the "new" keyword, a Cond is not a PHP object **/
$cond = Cond::create();
/** The caller must lock the associated Mutex before a call to broadcast **/
var_dump(Cond::broadcast($cond));
/** Always destroy Cond you have created **/
Cond::destroy($cond);
?>
```

The above example will output:

    bool(true)

Cond::create
============

Create a Condition

**Warning**

The <span class="classname">Cond</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Cond::create</span> ( <span
class="methodparam">void</span> )

Creates a new Condition Variable for the caller.

### Parameters

This function has no parameters.

### Return Values

A handle to a Condition Variable

### Examples

**Example \#1 Condition Creation and Destruction**

``` php
<?php
/** You cannot use the "new" keyword, a Cond is not a PHP object **/
$cond = Cond::create();
/** You can now use the Cond in any context **/
var_dump($cond);
/** Always destroy Cond you have created **/
Cond::destroy($cond);
?>
```

The above example will output:

    int(4540682)

Cond::destroy
=============

Destroy a Condition

**Warning**

The <span class="classname">Cond</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">Cond::destroy</span> ( <span
class="methodparam"> <span class="type">int</span> `$condition` </span>
)

Destroying Condition Variable handles must be carried out explicitly by
the programmer when they are finished with the Condition Variable. No
Threads should be blocking on a call to <span
class="function">Cond::wait</span> when the call to <span
class="function">Cond::destroy</span> takes place.

### Parameters

`condition`  
A handle to a Condition Variable returned by a previous call to <span
class="function">Cond::create</span>

### Return Values

A boolean indication of success.

### Examples

**Example \#1 Condition Creation and Destruction**

``` php
<?php
/** You cannot use the "new" keyword, a Cond is not a PHP object **/
$cond = Cond::create();
/** You can now use the Cond in any context **/
var_dump($cond);
/** Always destroy Cond you have created **/
Cond::destroy($cond);
?>
```

The above example will output:

    int(4540682)

Cond::signal
============

Signal a Condition

**Warning**

The <span class="classname">Cond</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">Cond::signal</span> ( <span
class="methodparam"> <span class="type">int</span> `$condition` </span>
)

### Parameters

`condition`  
A handle returned by a previous call to <span
class="function">Cond::create</span>

### Return Values

A boolean indication of success.

### Examples

**Example \#1 Condition Signalling**

``` php
<?php
/** You cannot use the "new" keyword, a Cond is not a PHP object **/
$cond = Cond::create();
/** The caller must lock the associated Mutex before a call to broadcast **/
var_dump(Cond::signal($cond));
/** Always destroy Cond you have created **/
Cond::destroy($cond);
?>
```

The above example will output:

    bool(true)

Cond::wait
==========

Wait for Condition

**Warning**

The <span class="classname">Cond</span> class has been removed in
pthreads v3.

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">bool</span>
<span class="methodname">Cond::wait</span> ( <span class="methodparam">
<span class="type">int</span> `$condition` </span> , <span
class="methodparam"> <span class="type">int</span> `$mutex` </span> \[,
<span class="methodparam"> <span class="type">int</span> `$timeout`
</span> \] )

Wait for a signal on a Condition Variable, optionally specifying a
timeout to limit waiting time.

### Parameters

`condition`  
A handle returned by a previous call to <span
class="function">Cond::create</span>.

`mutex`  
A handle returned by a previous call to <span
class="function">Mutex::create</span> and owned (locked) by the caller.

`timeout`  
An optional timeout, in microseconds ( millionths of a second ).

### Return Values

A boolean indication of success.

### Examples

**Example \#1 Waiting for Conditions**

``` php
<?php
/** PLEASE NOTE THIS EXAMPLE WILL CAUSE THE PROCESS TO HANG **/
$mutex = Mutex::create(true);
/** You cannot use the "new" keyword, a Cond is not a PHP object **/
$cond = Cond::create();
/** The caller must lock the associated Mutex before a call to broadcast **/
var_dump(Cond::wait($cond, $mutex));
/** Always destroy Cond you have created **/
Cond::destroy($cond);
Mutex::unlock($mutex);
Mutex::destroy($mutex);
?>
```

The above example will output:

    int(49685473)

Introduction
------------

The <span class="classname">Volatile</span> class is new to pthreads v3.
Its introduction is a consequence of the new immutability semantics of
<span class="classname">Threaded</span> members of <span
class="classname">Threaded</span> classes. The <span
class="classname">Volatile</span> class enables for mutability of its
<span class="classname">Threaded</span> members, and is also used to
store PHP arrays in <span class="classname">Threaded</span> contexts.

Class synopsis
--------------

**Volatile**

<span class="ooclass"> class **Volatile** </span> <span class="ooclass">
<span class="modifier">extends</span> **Threaded** </span> <span
class="oointerface">implements <span
class="interfacename">Collectable</span> </span> <span
class="oointerface">, <span class="interfacename">Traversable</span>
</span> {

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Threaded::chunk</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> , <span
class="methodparam"><span class="type">bool</span> `$preserve`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Threaded::count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::extend</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> )

<span class="modifier">public</span> <span class="type">Threaded</span>
<span class="methodname">Threaded::from</span> ( <span
class="methodparam"><span class="type">Closure</span> `$run`</span> \[,
<span class="methodparam"><span class="type">Closure</span>
`$construct`</span> \[, <span class="methodparam"><span
class="type">array</span> `$args`</span> \]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Threaded::getTerminationInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isRunning</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isTerminated</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::isWaiting</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::lock</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::merge</span> ( <span
class="methodparam"><span class="type">mixed</span> `$from`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$overwrite`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::notify</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::notifyOne</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::pop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Threaded::run</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Threaded::shift</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Threaded::synchronized</span> ( <span
class="methodparam"><span class="type">Closure</span> `$block`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$...`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::unlock</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Threaded::wait</span> (\[ <span
class="methodparam"><span class="type">int</span> `$timeout`</span> \] )

}

Examples
--------

**Example \#1 New immutability semantics of Threaded**

``` php
<?php

class Task extends Threaded
{
    public function __construct()
    {
        $this->data = new Threaded();

        // attempt to overwrite a Threaded property of a Threaded class (invalid)
        $this->data = new StdClass();
    }
}

var_dump((new Task())->data);
```

The above example will output something similar to:

    RuntimeException: Threaded members previously set to Threaded objects are immutable, cannot overwrite data in %s:%d

**Example \#2 Volatile use-case**

``` php
<?php

class Task extends Volatile
{
    public function __construct()
    {
        $this->data = new Threaded();

        // attempt to overwrite a Threaded property of a Volatile class (valid)
        $this->data = new StdClass();
    }
}

var_dump((new Task())->data);
```

The above example will output something similar to:

    object(stdClass)#3 (0) {
    }

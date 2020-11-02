Predefined Interfaces and Classes
=================================

**Table of Contents**

-   [Traversable](/class/traversable.html) — The Traversable interface
-   [Iterator](/class/iterator.html) — The Iterator interface
    -   [Iterator::current](/iterator/current.html) — Return the current
        element
    -   [Iterator::key](/iterator/key.html) — Return the key of the
        current element
    -   [Iterator::next](/iterator/next.html) — Move forward to next
        element
    -   [Iterator::rewind](/iterator/rewind.html) — Rewind the Iterator
        to the first element
    -   [Iterator::valid](/iterator/valid.html) — Checks if current
        position is valid
-   [IteratorAggregate](/class/iteratoraggregate.html) — The
    IteratorAggregate interface
    -   [IteratorAggregate::getIterator](/iteratoraggregate/getiterator.html)
        — Retrieve an external iterator
-   [Throwable](/class/throwable.html) — Throwable
    -   [Throwable::getMessage](/throwable/getmessage.html) — Gets the
        message
    -   [Throwable::getCode](/throwable/getcode.html) — Gets the
        exception code
    -   [Throwable::getFile](/throwable/getfile.html) — Gets the file in
        which the object was created
    -   [Throwable::getLine](/throwable/getline.html) — Gets the line on
        which the object was instantiated
    -   [Throwable::getTrace](/throwable/gettrace.html) — Gets the stack
        trace
    -   [Throwable::getTraceAsString](/throwable/gettraceasstring.html)
        — Gets the stack trace as a string
    -   [Throwable::getPrevious](/throwable/getprevious.html) — Returns
        the previous Throwable
    -   [Throwable::\_\_toString](/throwable/tostring.html) — Gets a
        string representation of the thrown object
-   [ArrayAccess](/class/arrayaccess.html) — The ArrayAccess interface
    -   [ArrayAccess::offsetExists](/arrayaccess/offsetexists.html) —
        Whether an offset exists
    -   [ArrayAccess::offsetGet](/arrayaccess/offsetget.html) — Offset
        to retrieve
    -   [ArrayAccess::offsetSet](/arrayaccess/offsetset.html) — Assign a
        value to the specified offset
    -   [ArrayAccess::offsetUnset](/arrayaccess/offsetunset.html) —
        Unset an offset
-   [Serializable](/class/serializable.html) — The Serializable
    interface
    -   [Serializable::serialize](/serializable/serialize.html) — String
        representation of object
    -   [Serializable::unserialize](/serializable/unserialize.html) —
        Constructs the object
-   [Closure](/class/closure.html) — The Closure class
    -   [Closure::\_\_construct](/closure/construct.html) — Constructor
        that disallows instantiation
    -   [Closure::bind](/closure/bind.html) — Duplicates a closure with
        a specific bound object and class scope
    -   [Closure::bindTo](/closure/bindto.html) — Duplicates the closure
        with a new bound object and class scope
    -   [Closure::call](/closure/call.html) — Binds and calls the
        closure
    -   [Closure::fromCallable](/closure/fromcallable.html) — Converts a
        callable into a closure
-   [Generator](/class/generator.html) — The Generator class
    -   [Generator::current](/generator/current.html) — Get the yielded
        value
    -   [Generator::getReturn](/generator/getreturn.html) — Get the
        return value of a generator
    -   [Generator::key](/generator/key.html) — Get the yielded key
    -   [Generator::next](/generator/next.html) — Resume execution of
        the generator
    -   [Generator::rewind](/generator/rewind.html) — Rewind the
        iterator
    -   [Generator::send](/generator/send.html) — Send a value to the
        generator
    -   [Generator::throw](/generator/throw.html) — Throw an exception
        into the generator
    -   [Generator::valid](/generator/valid.html) — Check if the
        iterator has been closed
    -   [Generator::\_\_wakeup](/generator/wakeup.html) — Serialize
        callback
-   [WeakReference](/class/weakreference.html) — The WeakReference class
    -   [WeakReference::\_\_construct](/weakreference/construct.html) —
        Constructor that disallows instantiation
    -   [WeakReference::create](/weakreference/create.html) — Create a
        new weak reference
    -   [WeakReference::get](/weakreference/get.html) — Get a weakly
        referenced Object

See also the
<a href="/spl/interfaces.html" class="link">SPL Interfaces</a> and
<a href="/reserved/classes.html" class="link">reserved classes</a>.

Introduction
------------

Interface to detect if a class is traversable using
<a href="/control-structures/foreach.html" class="link">foreach</a>.

Abstract base interface that cannot be implemented alone. Instead it
must be implemented by either <span
class="interfacename">IteratorAggregate</span> or <span
class="interfacename">Iterator</span>.

> **Note**:
>
> Internal (built-in) classes that implement this interface can be used
> in a
> <a href="/control-structures/foreach.html" class="link">foreach</a>
> construct and do not need to implement <span
> class="interfacename">IteratorAggregate</span> or <span
> class="interfacename">Iterator</span>.

> **Note**:
>
> This is an internal engine interface which cannot be implemented in
> PHP scripts. Either <span
> class="interfacename">IteratorAggregate</span> or <span
> class="interfacename">Iterator</span> must be used instead. When
> implementing an interface which extends Traversable, make sure to list
> <span class="interfacename">IteratorAggregate</span> or <span
> class="interfacename">Iterator</span> before its name in the
> implements clause.

Interface synopsis
------------------

**Traversable**

<span class="ooclass"> class **Traversable** </span> {

}

This interface has no methods, its only purpose is to be the base
interface for all traversable classes.

Introduction
------------

Interface for external iterators or objects that can be iterated
themselves internally.

Interface synopsis
------------------

**Iterator**

<span class="ooclass"> class **Iterator** </span> <span class="ooclass">
<span class="modifier">extends</span> **Traversable** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">scalar</span> <span
class="methodname">key</span> ( <span class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">next</span> ( <span class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">rewind</span> ( <span class="methodparam">void</span>
)

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">valid</span> ( <span class="methodparam">void</span>
)

}

Predefined iterators
--------------------

PHP already provides a number of iterators for many day to day tasks.
See <a href="/spl/iterators.html" class="link">SPL iterators</a> for a
list.

Examples
--------

**Example \#1 Basic usage**

This example demonstrates in which order methods are called when using
<a href="/control-structures/foreach.html" class="link">foreach</a> with
an iterator.

``` php
<?php
class myIterator implements Iterator {
    private $position = 0;
    private $array = array(
        "firstelement",
        "secondelement",
        "lastelement",
    );  

    public function __construct() {
        $this->position = 0;
    }

    public function rewind() {
        var_dump(__METHOD__);
        $this->position = 0;
    }

    public function current() {
        var_dump(__METHOD__);
        return $this->array[$this->position];
    }

    public function key() {
        var_dump(__METHOD__);
        return $this->position;
    }

    public function next() {
        var_dump(__METHOD__);
        ++$this->position;
    }

    public function valid() {
        var_dump(__METHOD__);
        return isset($this->array[$this->position]);
    }
}

$it = new myIterator;

foreach($it as $key => $value) {
    var_dump($key, $value);
    echo "\n";
}
?>
```

The above example will output something similar to:

    string(18) "myIterator::rewind"
    string(17) "myIterator::valid"
    string(19) "myIterator::current"
    string(15) "myIterator::key"
    int(0)
    string(12) "firstelement"

    string(16) "myIterator::next"
    string(17) "myIterator::valid"
    string(19) "myIterator::current"
    string(15) "myIterator::key"
    int(1)
    string(13) "secondelement"

    string(16) "myIterator::next"
    string(17) "myIterator::valid"
    string(19) "myIterator::current"
    string(15) "myIterator::key"
    int(2)
    string(11) "lastelement"

    string(16) "myIterator::next"
    string(17) "myIterator::valid"

Introduction
------------

Interface to create an external Iterator.

Interface synopsis
------------------

**IteratorAggregate**

<span class="ooclass"> class **IteratorAggregate** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Traversable**
</span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">Traversable</span>
<span class="methodname">getIterator</span> ( <span
class="methodparam">void</span> )

}

**Example \#1 Basic usage**

``` php
<?php
class myData implements IteratorAggregate {
    public $property1 = "Public property one";
    public $property2 = "Public property two";
    public $property3 = "Public property three";

    public function __construct() {
        $this->property4 = "last property";
    }

    public function getIterator() {
        return new ArrayIterator($this);
    }
}

$obj = new myData;

foreach($obj as $key => $value) {
    var_dump($key, $value);
    echo "\n";
}
?>
```

The above example will output something similar to:

    string(9) "property1"
    string(19) "Public property one"

    string(9) "property2"
    string(19) "Public property two"

    string(9) "property3"
    string(21) "Public property three"

    string(9) "property4"
    string(13) "last property"

Introduction
------------

<span class="classname">Throwable</span> is the base interface for any
object that can be thrown via a
<a href="/language/exceptions.html" class="link"><em>throw</em></a>
statement, including <span class="classname">Error</span> and <span
class="classname">Exception</span>.

> **Note**:
>
> PHP classes cannot implement the <span
> class="classname">Throwable</span> interface directly, and must
> instead extend <span class="classname">Exception</span>.

Interface synopsis
------------------

**Throwable**

<span class="ooclass"> class **Throwable** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">Throwable</span> <span
class="methodname">getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Interface to provide accessing objects as arrays.

Interface synopsis
------------------

**ArrayAccess**

<span class="ooclass"> class **ArrayAccess** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">offsetExists</span> ( <span class="methodparam"><span
class="type">mixed</span> `$offset`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">offsetGet</span> ( <span class="methodparam"><span
class="type">mixed</span> `$offset`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">offsetSet</span> ( <span class="methodparam"><span
class="type">mixed</span> `$offset`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">offsetUnset</span> ( <span class="methodparam"><span
class="type">mixed</span> `$offset`</span> )

}

**Example \#1 Basic usage**

``` php
<?php
class Obj implements ArrayAccess {
    private $container = array();

    public function __construct() {
        $this->container = array(
            "one"   => 1,
            "two"   => 2,
            "three" => 3,
        );
    }

    public function offsetSet($offset, $value) {
        if (is_null($offset)) {
            $this->container[] = $value;
        } else {
            $this->container[$offset] = $value;
        }
    }

    public function offsetExists($offset) {
        return isset($this->container[$offset]);
    }

    public function offsetUnset($offset) {
        unset($this->container[$offset]);
    }

    public function offsetGet($offset) {
        return isset($this->container[$offset]) ? $this->container[$offset] : null;
    }
}

$obj = new Obj;

var_dump(isset($obj["two"]));
var_dump($obj["two"]);
unset($obj["two"]);
var_dump(isset($obj["two"]));
$obj["two"] = "A value";
var_dump($obj["two"]);
$obj[] = 'Append 1';
$obj[] = 'Append 2';
$obj[] = 'Append 3';
print_r($obj);
?>
```

The above example will output something similar to:

    bool(true)
    int(2)
    bool(false)
    string(7) "A value"
    obj Object
    (
        [container:obj:private] => Array
            (
                [one] => 1
                [three] => 3
                [two] => A value
                [0] => Append 1
                [1] => Append 2
                [2] => Append 3
            )

    )

Introduction
------------

Interface for customized serializing.

Classes that implement this interface no longer support
<a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
and
<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>.
The method serialize is called whenever an instance needs to be
serialized. This does not invoke \_\_destruct() or have any other side
effect unless programmed inside the method. When the data is
unserialized the class is known and the appropriate unserialize() method
is called as a constructor instead of calling \_\_construct(). If you
need to execute the standard constructor you may do so in the method.

Interface synopsis
------------------

**Serializable**

<span class="ooclass"> class **Serializable** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">unserialize</span> ( <span class="methodparam"><span
class="type">string</span> `$serialized`</span> )

}

**Example \#1 Basic usage**

``` php
<?php
class obj implements Serializable {
    private $data;
    public function __construct() {
        $this->data = "My private data";
    }
    public function serialize() {
        return serialize($this->data);
    }
    public function unserialize($data) {
        $this->data = unserialize($data);
    }
    public function getData() {
        return $this->data;
    }
}

$obj = new obj;
$ser = serialize($obj);

var_dump($ser);

$newobj = unserialize($ser);

var_dump($newobj->getData());
?>
```

The above example will output something similar to:

    string(38) "C:3:"obj":23:{s:15:"My private data";}"
    string(15) "My private data"

Introduction
------------

Class used to represent
<a href="/functions/anonymous.html" class="link">anonymous functions</a>.

Anonymous functions yield objects of this type. This class has methods
that allow further control of the anonymous function after it has been
created.

Besides the methods listed here, this class also has an *\_\_invoke*
method. This is for consistency with other classes that implement
<a href="/language/oop5/magic.html#language.oop5.magic.invoke" class="link">calling magic</a>,
as this method is not used for calling the function.

Class synopsis
--------------

**Closure**

<span class="ooclass"> class **Closure** </span> {

/\* Methods \*/

<span class="modifier">private</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">Closure</span><span class="type">false</span></span> <span
class="methodname">bind</span> ( <span class="methodparam"><span
class="type">Closure</span> `$closure`</span> , <span
class="methodparam"><span class="type">object</span> `$newthis`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$newscope` <span class="initializer"> = "static"</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">Closure</span><span class="type">false</span></span> <span
class="methodname">bindTo</span> ( <span class="methodparam"><span
class="type">object</span> `$newthis`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$newscope` <span
class="initializer"> = "static"</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">call</span> ( <span class="methodparam"><span
class="type">object</span> `$newthis`</span> , <span
class="methodparam"><span class="type">mixed</span> `$values`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">Closure</span> <span
class="methodname">fromCallable</span> ( <span class="methodparam"><span
class="type">callable</span> `$callable`</span> )

}

Introduction
------------

<span class="classname">Generator</span> objects are returned from
<a href="/language/generators.html" class="link">generators</a>.

**Caution**

<span class="classname">Generator</span> objects cannot be instantiated
via
<a href="/language/oop5/basic.html#language.oop5.basic.new" class="link">new</a>.

Class synopsis
--------------

**Generator**

<span class="ooclass"> class **Generator** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getReturn</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">send</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">throw</span> ( <span class="methodparam"><span
class="type">Throwable</span> `$exception`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_wakeup</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Weak references allow the programmer to retain a reference to an object
which does not prevent the object from being destroyed. They are useful
for implementing cache like structures.

> **Note**:
>
> The class <span class="classname">WeakReference</span> is not to be
> confused with the class <span class="classname">WeakRef</span> of the
> <a href="/class/weakref.html" class="link">Weakref</a> extension.

<span class="classname">WeakReference</span>s cannot be serialized.

Class synopsis
--------------

**WeakReference**

<span class="ooclass"> class **WeakReference** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">WeakReference</span>
<span class="methodname">create</span> ( <span class="methodparam"><span
class="type">object</span> `$referent`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">object</span><span class="type">null</span></span> <span
class="methodname">get</span> ( <span class="methodparam">void</span> )

}

WeakReference Examples
----------------------

**Example \#1 Basic WeakReference Usage**

``` php
<?php
$obj = new stdClass;
$weakref = WeakReference::create($obj);
var_dump($weakref->get());
unset($obj);
var_dump($weakref->get());
?>
```

The above example will output something similar to:

    object(stdClass)#1 (0) {
    }
    NULL

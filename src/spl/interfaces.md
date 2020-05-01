Interfaces
==========

**Table of Contents**

-   [Countable](/spl/interfaces.html#Countable) — The Countable
    interface
    -   [Countable::count](/spl/interfaces.html#Countable::count) —
        Count elements of an object
-   [OuterIterator](/spl/interfaces.html#OuterIterator) — The
    OuterIterator interface
    -   [OuterIterator::getInnerIterator](/spl/interfaces.html#OuterIterator::getInnerIterator)
        — Returns the inner iterator for the current entry
-   [RecursiveIterator](/spl/interfaces.html#RecursiveIterator) — The
    RecursiveIterator interface
    -   [RecursiveIterator::getChildren](/spl/interfaces.html#RecursiveIterator::getChildren)
        — Returns an iterator for the current entry
    -   [RecursiveIterator::hasChildren](/spl/interfaces.html#RecursiveIterator::hasChildren)
        — Returns if an iterator can be created for the current entry
-   [SeekableIterator](/spl/interfaces.html#SeekableIterator) — The
    SeekableIterator interface
    -   [SeekableIterator::seek](/spl/interfaces.html#SeekableIterator::seek)
        — Seeks to a position

SPL provides a set of interfaces.

See also the
<a href="/reserved/interfaces.html" class="xref">Predefined Interfaces and Classes</a>

Interface list
--------------

-   <span class="classname">Countable</span>
-   <span class="classname">OuterIterator</span>
-   <span class="classname">RecursiveIterator</span>
-   <span class="classname">SeekableIterator</span>
-   <span class="classname">SplObserver</span>
-   <span class="classname">SplSubject</span>

Introduction
------------

Classes implementing <span class="classname">Countable</span> can be
used with the <span class="function">count</span> function.

Interface synopsis
------------------

**Countable**

<span class="ooclass"> class **Countable** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

}

Countable::count
================

Count elements of an object

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Countable::count</span> ( <span
class="methodparam">void</span> )

This method is executed when using the <span
class="function">count</span> function on an object implementing <span
class="classname">Countable</span>.

### Parameters

This function has no parameters.

### Return Values

The custom count as an <span class="type">integer</span>.

> **Note**:
>
> The return value is cast to an <span class="type">integer</span>.

### Examples

**Example \#1 <span class="function">Countable::count</span> example**

``` php
<?php
class myCounter implements Countable {
    private $count = 0;
    public function count() {
        return ++$this->count;
    }
}

$counter = new myCounter;

for($i=0; $i<10; ++$i) {
    echo "I have been count()ed " . count($counter) . " times\n";
}
?>
```

The above example will output something similar to:

    I have been count()ed 1 times
    I have been count()ed 2 times
    I have been count()ed 3 times
    I have been count()ed 4 times
    I have been count()ed 5 times
    I have been count()ed 6 times
    I have been count()ed 7 times
    I have been count()ed 8 times
    I have been count()ed 9 times
    I have been count()ed 10 times

Introduction
------------

Classes implementing <span class="classname">OuterIterator</span> can be
used to iterate over iterators.

Interface synopsis
------------------

**OuterIterator**

<span class="ooclass"> class **OuterIterator** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Iterator**
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">Iterator</span>
<span class="methodname">getInnerIterator</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">Iterator::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">scalar</span> <span
class="methodname">Iterator::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Iterator::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Iterator::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Iterator::valid</span> ( <span
class="methodparam">void</span> )

}

OuterIterator::getInnerIterator
===============================

Returns the inner iterator for the current entry

### Description

<span class="modifier">public</span> <span class="type">Iterator</span>
<span class="methodname">OuterIterator::getInnerIterator</span> ( <span
class="methodparam">void</span> )

Returns the inner iterator for the current iterator entry.

### Parameters

This function has no parameters.

### Return Values

The inner iterator for the current entry.

Introduction
------------

Classes implementing <span class="classname">RecursiveIterator</span>
can be used to iterate over iterators recursively.

Interface synopsis
------------------

**RecursiveIterator**

<span class="ooclass"> class **RecursiveIterator** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Iterator**
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">RecursiveIterator</span> <span
class="methodname">getChildren</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasChildren</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">Iterator::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">scalar</span> <span
class="methodname">Iterator::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Iterator::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Iterator::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Iterator::valid</span> ( <span
class="methodparam">void</span> )

}

RecursiveIterator::getChildren
==============================

Returns an iterator for the current entry

### Description

<span class="modifier">public</span> <span
class="type">RecursiveIterator</span> <span
class="methodname">RecursiveIterator::getChildren</span> ( <span
class="methodparam">void</span> )

Returns an iterator for the current iterator entry.

### Parameters

This function has no parameters.

### Return Values

An iterator for the current entry.

### See Also

-   <span class="function">RecursiveIterator::hasChildren</span>

RecursiveIterator::hasChildren
==============================

Returns if an iterator can be created for the current entry

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">RecursiveIterator::hasChildren</span> ( <span
class="methodparam">void</span> )

Returns if an iterator can be created for the current entry. <span
class="methodname">RecursiveIterator::getChildren</span>.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the current entry can be iterated over, otherwise
returns **`FALSE`**.

### See Also

-   <span class="function">RecursiveIterator::getChildren</span>

Introduction
------------

The Seekable iterator.

Interface synopsis
------------------

**SeekableIterator**

<span class="ooclass"> class **SeekableIterator** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Iterator**
</span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">seek</span> ( <span class="methodparam"><span
class="type">int</span> `$position`</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">Iterator::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">scalar</span> <span
class="methodname">Iterator::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Iterator::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Iterator::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Iterator::valid</span> ( <span
class="methodparam">void</span> )

}

**Example \#1 Basic usage**

This example demonstrates creating a custom <span
class="classname">SeekableIterator</span>, seeking to a position and
handling an invalid position.

``` php
<?php
class MySeekableIterator implements SeekableIterator {

    private $position;

    private $array = array(
        "first element",
        "second element",
        "third element",
        "fourth element"
    );

    /* Method required for SeekableIterator interface */

    public function seek($position) {
      if (!isset($this->array[$position])) {
          throw new OutOfBoundsException("invalid seek position ($position)");
      }

      $this->position = $position;
    }

    /* Methods required for Iterator interface */
    
    public function rewind() {
        $this->position = 0;
    }

    public function current() {
        return $this->array[$this->position];
    }

    public function key() {
        return $this->position;
    }

    public function next() {
        ++$this->position;
    }

    public function valid() {
        return isset($this->array[$this->position]);
    }
}

try {

    $it = new MySeekableIterator;
    echo $it->current(), "\n";
    
    $it->seek(2);
    echo $it->current(), "\n";
    
    $it->seek(1);
    echo $it->current(), "\n";
    
    $it->seek(10);
    
} catch (OutOfBoundsException $e) {
    echo $e->getMessage();
}
?>
```

The above example will output something similar to:

    first element
    third element
    second element
    invalid seek position (10)

SeekableIterator::seek
======================

Seeks to a position

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">SeekableIterator::seek</span> ( <span
class="methodparam"><span class="type">int</span> `$position`</span> )

Seeks to a given position in the iterator.

### Parameters

`position`  
The position to seek to.

### Return Values

No value is returned.

### Errors/Exceptions

Implementations should throw an <span
class="classname">OutOfBoundsException</span> if the `position` is not
seekable.

### Examples

**Example \#1 <span class="methodname">SeekableIterator::seek</span>
example**

Seek to the item at position 3 in the iterator (<span
class="classname">ArrayIterator</span> implements <span
class="classname">SeekableIterator</span>).

``` php
<?php
$array = array("apple", "banana", "cherry", "damson", "elderberry");
$iterator = new ArrayIterator($array);
$iterator->seek(3);
echo $iterator->current();
?>
```

The above example will output something similar to:

    damson

### See Also

-   <span class="classname">SeekableIterator</span>
-   <span class="classname">Iterator</span>

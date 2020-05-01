Datastructures
==============

**Table of Contents**

-   [SplDoublyLinkedList](/spl/datastructures.html#SplDoublyLinkedList)
    — The SplDoublyLinkedList class
    -   [SplDoublyLinkedList::add](/spl/datastructures.html#SplDoublyLinkedList::add)
        — Add/insert a new value at the specified index
    -   [SplDoublyLinkedList::bottom](/spl/datastructures.html#SplDoublyLinkedList::bottom)
        — Peeks at the node from the beginning of the doubly linked list
    -   [SplDoublyLinkedList::\_\_construct](/spl/datastructures.html#SplDoublyLinkedList::__construct)
        — Constructs a new doubly linked list
    -   [SplDoublyLinkedList::count](/spl/datastructures.html#SplDoublyLinkedList::count)
        — Counts the number of elements in the doubly linked list
    -   [SplDoublyLinkedList::current](/spl/datastructures.html#SplDoublyLinkedList::current)
        — Return current array entry
    -   [SplDoublyLinkedList::getIteratorMode](/spl/datastructures.html#SplDoublyLinkedList::getIteratorMode)
        — Returns the mode of iteration
    -   [SplDoublyLinkedList::isEmpty](/spl/datastructures.html#SplDoublyLinkedList::isEmpty)
        — Checks whether the doubly linked list is empty
    -   [SplDoublyLinkedList::key](/spl/datastructures.html#SplDoublyLinkedList::key)
        — Return current node index
    -   [SplDoublyLinkedList::next](/spl/datastructures.html#SplDoublyLinkedList::next)
        — Move to next entry
    -   [SplDoublyLinkedList::offsetExists](/spl/datastructures.html#SplDoublyLinkedList::offsetExists)
        — Returns whether the requested $index exists
    -   [SplDoublyLinkedList::offsetGet](/spl/datastructures.html#SplDoublyLinkedList::offsetGet)
        — Returns the value at the specified $index
    -   [SplDoublyLinkedList::offsetSet](/spl/datastructures.html#SplDoublyLinkedList::offsetSet)
        — Sets the value at the specified $index to $newval
    -   [SplDoublyLinkedList::offsetUnset](/spl/datastructures.html#SplDoublyLinkedList::offsetUnset)
        — Unsets the value at the specified $index
    -   [SplDoublyLinkedList::pop](/spl/datastructures.html#SplDoublyLinkedList::pop)
        — Pops a node from the end of the doubly linked list
    -   [SplDoublyLinkedList::prev](/spl/datastructures.html#SplDoublyLinkedList::prev)
        — Move to previous entry
    -   [SplDoublyLinkedList::push](/spl/datastructures.html#SplDoublyLinkedList::push)
        — Pushes an element at the end of the doubly linked list
    -   [SplDoublyLinkedList::rewind](/spl/datastructures.html#SplDoublyLinkedList::rewind)
        — Rewind iterator back to the start
    -   [SplDoublyLinkedList::serialize](/spl/datastructures.html#SplDoublyLinkedList::serialize)
        — Serializes the storage
    -   [SplDoublyLinkedList::setIteratorMode](/spl/datastructures.html#SplDoublyLinkedList::setIteratorMode)
        — Sets the mode of iteration
    -   [SplDoublyLinkedList::shift](/spl/datastructures.html#SplDoublyLinkedList::shift)
        — Shifts a node from the beginning of the doubly linked list
    -   [SplDoublyLinkedList::top](/spl/datastructures.html#SplDoublyLinkedList::top)
        — Peeks at the node from the end of the doubly linked list
    -   [SplDoublyLinkedList::unserialize](/spl/datastructures.html#SplDoublyLinkedList::unserialize)
        — Unserializes the storage
    -   [SplDoublyLinkedList::unshift](/spl/datastructures.html#SplDoublyLinkedList::unshift)
        — Prepends the doubly linked list with an element
    -   [SplDoublyLinkedList::valid](/spl/datastructures.html#SplDoublyLinkedList::valid)
        — Check whether the doubly linked list contains more nodes
-   [SplStack](/spl/datastructures.html#SplStack) — The SplStack class
    -   [SplStack::\_\_construct](/spl/datastructures.html#SplStack::__construct)
        — Constructs a new stack implemented using a doubly linked list
    -   [SplStack::setIteratorMode](/spl/datastructures.html#SplStack::setIteratorMode)
        — Sets the mode of iteration
-   [SplQueue](/spl/datastructures.html#SplQueue) — The SplQueue class
    -   [SplQueue::\_\_construct](/spl/datastructures.html#SplQueue::__construct)
        — Constructs a new queue implemented using a doubly linked list
    -   [SplQueue::dequeue](/spl/datastructures.html#SplQueue::dequeue)
        — Dequeues a node from the queue
    -   [SplQueue::enqueue](/spl/datastructures.html#SplQueue::enqueue)
        — Adds an element to the queue
    -   [SplQueue::setIteratorMode](/spl/datastructures.html#SplQueue::setIteratorMode)
        — Sets the mode of iteration
-   [SplHeap](/spl/datastructures.html#SplHeap) — The SplHeap class
    -   [SplHeap::compare](/spl/datastructures.html#SplHeap::compare) —
        Compare elements in order to place them correctly in the heap
        while sifting up
    -   [SplHeap::\_\_construct](/spl/datastructures.html#SplHeap::__construct)
        — Constructs a new empty heap
    -   [SplHeap::count](/spl/datastructures.html#SplHeap::count) —
        Counts the number of elements in the heap
    -   [SplHeap::current](/spl/datastructures.html#SplHeap::current) —
        Return current node pointed by the iterator
    -   [SplHeap::extract](/spl/datastructures.html#SplHeap::extract) —
        Extracts a node from top of the heap and sift up
    -   [SplHeap::insert](/spl/datastructures.html#SplHeap::insert) —
        Inserts an element in the heap by sifting it up
    -   [SplHeap::isCorrupted](/spl/datastructures.html#SplHeap::isCorrupted)
        — Tells if the heap is in a corrupted state
    -   [SplHeap::isEmpty](/spl/datastructures.html#SplHeap::isEmpty) —
        Checks whether the heap is empty
    -   [SplHeap::key](/spl/datastructures.html#SplHeap::key) — Return
        current node index
    -   [SplHeap::next](/spl/datastructures.html#SplHeap::next) — Move
        to the next node
    -   [SplHeap::recoverFromCorruption](/spl/datastructures.html#SplHeap::recoverFromCorruption)
        — Recover from the corrupted state and allow further actions on
        the heap
    -   [SplHeap::rewind](/spl/datastructures.html#SplHeap::rewind) —
        Rewind iterator back to the start (no-op)
    -   [SplHeap::top](/spl/datastructures.html#SplHeap::top) — Peeks at
        the node from the top of the heap
    -   [SplHeap::valid](/spl/datastructures.html#SplHeap::valid) —
        Check whether the heap contains more nodes
-   [SplMaxHeap](/spl/datastructures.html#SplMaxHeap) — The SplMaxHeap
    class
    -   [SplMaxHeap::compare](/spl/datastructures.html#SplMaxHeap::compare)
        — Compare elements in order to place them correctly in the heap
        while sifting up
-   [SplMinHeap](/spl/datastructures.html#SplMinHeap) — The SplMinHeap
    class
    -   [SplMinHeap::compare](/spl/datastructures.html#SplMinHeap::compare)
        — Compare elements in order to place them correctly in the heap
        while sifting up
-   [SplPriorityQueue](/spl/datastructures.html#SplPriorityQueue) — The
    SplPriorityQueue class
    -   [SplPriorityQueue::compare](/spl/datastructures.html#SplPriorityQueue::compare)
        — Compare priorities in order to place elements correctly in the
        heap while sifting up
    -   [SplPriorityQueue::\_\_construct](/spl/datastructures.html#SplPriorityQueue::__construct)
        — Constructs a new empty queue
    -   [SplPriorityQueue::count](/spl/datastructures.html#SplPriorityQueue::count)
        — Counts the number of elements in the queue
    -   [SplPriorityQueue::current](/spl/datastructures.html#SplPriorityQueue::current)
        — Return current node pointed by the iterator
    -   [SplPriorityQueue::extract](/spl/datastructures.html#SplPriorityQueue::extract)
        — Extracts a node from top of the heap and sift up
    -   [SplPriorityQueue::getExtractFlags](/spl/datastructures.html#SplPriorityQueue::getExtractFlags)
        — Get the flags of extraction
    -   [SplPriorityQueue::insert](/spl/datastructures.html#SplPriorityQueue::insert)
        — Inserts an element in the queue by sifting it up
    -   [SplPriorityQueue::isCorrupted](/spl/datastructures.html#SplPriorityQueue::isCorrupted)
        — Tells if the priority queue is in a corrupted state
    -   [SplPriorityQueue::isEmpty](/spl/datastructures.html#SplPriorityQueue::isEmpty)
        — Checks whether the queue is empty
    -   [SplPriorityQueue::key](/spl/datastructures.html#SplPriorityQueue::key)
        — Return current node index
    -   [SplPriorityQueue::next](/spl/datastructures.html#SplPriorityQueue::next)
        — Move to the next node
    -   [SplPriorityQueue::recoverFromCorruption](/spl/datastructures.html#SplPriorityQueue::recoverFromCorruption)
        — Recover from the corrupted state and allow further actions on
        the queue
    -   [SplPriorityQueue::rewind](/spl/datastructures.html#SplPriorityQueue::rewind)
        — Rewind iterator back to the start (no-op)
    -   [SplPriorityQueue::setExtractFlags](/spl/datastructures.html#SplPriorityQueue::setExtractFlags)
        — Sets the mode of extraction
    -   [SplPriorityQueue::top](/spl/datastructures.html#SplPriorityQueue::top)
        — Peeks at the node from the top of the queue
    -   [SplPriorityQueue::valid](/spl/datastructures.html#SplPriorityQueue::valid)
        — Check whether the queue contains more nodes
-   [SplFixedArray](/spl/datastructures.html#SplFixedArray) — The
    SplFixedArray class
    -   [SplFixedArray::\_\_construct](/spl/datastructures.html#SplFixedArray::__construct)
        — Constructs a new fixed array
    -   [SplFixedArray::count](/spl/datastructures.html#SplFixedArray::count)
        — Returns the size of the array
    -   [SplFixedArray::current](/spl/datastructures.html#SplFixedArray::current)
        — Return current array entry
    -   [SplFixedArray::fromArray](/spl/datastructures.html#SplFixedArray::fromArray)
        — Import a PHP array in a SplFixedArray instance
    -   [SplFixedArray::getSize](/spl/datastructures.html#SplFixedArray::getSize)
        — Gets the size of the array
    -   [SplFixedArray::key](/spl/datastructures.html#SplFixedArray::key)
        — Return current array index
    -   [SplFixedArray::next](/spl/datastructures.html#SplFixedArray::next)
        — Move to next entry
    -   [SplFixedArray::offsetExists](/spl/datastructures.html#SplFixedArray::offsetExists)
        — Returns whether the requested index exists
    -   [SplFixedArray::offsetGet](/spl/datastructures.html#SplFixedArray::offsetGet)
        — Returns the value at the specified index
    -   [SplFixedArray::offsetSet](/spl/datastructures.html#SplFixedArray::offsetSet)
        — Sets a new value at a specified index
    -   [SplFixedArray::offsetUnset](/spl/datastructures.html#SplFixedArray::offsetUnset)
        — Unsets the value at the specified $index
    -   [SplFixedArray::rewind](/spl/datastructures.html#SplFixedArray::rewind)
        — Rewind iterator back to the start
    -   [SplFixedArray::setSize](/spl/datastructures.html#SplFixedArray::setSize)
        — Change the size of an array
    -   [SplFixedArray::toArray](/spl/datastructures.html#SplFixedArray::toArray)
        — Returns a PHP array from the fixed array
    -   [SplFixedArray::valid](/spl/datastructures.html#SplFixedArray::valid)
        — Check whether the array contains more elements
    -   [SplFixedArray::\_\_wakeup](/spl/datastructures.html#SplFixedArray::__wakeup)
        — Reinitialises the array after being unserialised
-   [SplObjectStorage](/spl/datastructures.html#SplObjectStorage) — The
    SplObjectStorage class
    -   [SplObjectStorage::addAll](/spl/datastructures.html#SplObjectStorage::addAll)
        — Adds all objects from another storage
    -   [SplObjectStorage::attach](/spl/datastructures.html#SplObjectStorage::attach)
        — Adds an object in the storage
    -   [SplObjectStorage::contains](/spl/datastructures.html#SplObjectStorage::contains)
        — Checks if the storage contains a specific object
    -   [SplObjectStorage::count](/spl/datastructures.html#SplObjectStorage::count)
        — Returns the number of objects in the storage
    -   [SplObjectStorage::current](/spl/datastructures.html#SplObjectStorage::current)
        — Returns the current storage entry
    -   [SplObjectStorage::detach](/spl/datastructures.html#SplObjectStorage::detach)
        — Removes an object from the storage
    -   [SplObjectStorage::getHash](/spl/datastructures.html#SplObjectStorage::getHash)
        — Calculate a unique identifier for the contained objects
    -   [SplObjectStorage::getInfo](/spl/datastructures.html#SplObjectStorage::getInfo)
        — Returns the data associated with the current iterator entry
    -   [SplObjectStorage::key](/spl/datastructures.html#SplObjectStorage::key)
        — Returns the index at which the iterator currently is
    -   [SplObjectStorage::next](/spl/datastructures.html#SplObjectStorage::next)
        — Move to the next entry
    -   [SplObjectStorage::offsetExists](/spl/datastructures.html#SplObjectStorage::offsetExists)
        — Checks whether an object exists in the storage
    -   [SplObjectStorage::offsetGet](/spl/datastructures.html#SplObjectStorage::offsetGet)
        — Returns the data associated with an object
    -   [SplObjectStorage::offsetSet](/spl/datastructures.html#SplObjectStorage::offsetSet)
        — Associates data to an object in the storage
    -   [SplObjectStorage::offsetUnset](/spl/datastructures.html#SplObjectStorage::offsetUnset)
        — Removes an object from the storage
    -   [SplObjectStorage::removeAll](/spl/datastructures.html#SplObjectStorage::removeAll)
        — Removes objects contained in another storage from the current
        storage
    -   [SplObjectStorage::removeAllExcept](/spl/datastructures.html#SplObjectStorage::removeAllExcept)
        — Removes all objects except for those contained in another
        storage from the current storage
    -   [SplObjectStorage::rewind](/spl/datastructures.html#SplObjectStorage::rewind)
        — Rewind the iterator to the first storage element
    -   [SplObjectStorage::serialize](/spl/datastructures.html#SplObjectStorage::serialize)
        — Serializes the storage
    -   [SplObjectStorage::setInfo](/spl/datastructures.html#SplObjectStorage::setInfo)
        — Sets the data associated with the current iterator entry
    -   [SplObjectStorage::unserialize](/spl/datastructures.html#SplObjectStorage::unserialize)
        — Unserializes a storage from its string representation
    -   [SplObjectStorage::valid](/spl/datastructures.html#SplObjectStorage::valid)
        — Returns if the current iterator entry is valid

SPL provides a set of standard datastructures. They are grouped here by
their underlying implementation which usually defines their general
field of application.

Doubly Linked Lists
-------------------

A Doubly Linked List (DLL) is a list of nodes linked in both directions
to each other. Iterator's operations, access to both ends, addition or
removal of nodes have a cost of O(1) when the underlying structure is a
DLL. It hence provides a decent implementation for stacks and queues.

-   <span class="simpara"><span
    class="classname">SplDoublyLinkedList</span></span>
    -   <span class="simpara"><span
        class="classname">SplStack</span></span>
    -   <span class="simpara"><span
        class="classname">SplQueue</span></span>

Heaps
-----

Heaps are tree-like structures that follow the heap-property: each node
is greater than or equal to its children, when compared using the
implemented compare method which is global to the heap.

-   <span class="simpara"><span class="classname">SplHeap</span></span>
    -   <span class="simpara"><span
        class="classname">SplMaxHeap</span></span>
    -   <span class="simpara"><span
        class="classname">SplMinHeap</span></span>
-   <span class="simpara"><span
    class="classname">SplPriorityQueue</span></span>

Arrays
------

Arrays are structures that store the data in a continuous way,
accessible via indexes. Don't confuse them with PHP arrays: PHP arrays
are in fact implemented as ordered hashtables.

-   <span class="simpara"><span
    class="classname">SplFixedArray</span></span>

Map
---

A map is a datastructure holding key-value pairs. PHP arrays can be seen
as maps from integers/strings to values. SPL provides a map from objects
to data. This map can also be used as an object set.

-   <span class="simpara"><span
    class="classname">SplObjectStorage</span></span>

Introduction
------------

The SplDoublyLinkedList class provides the main functionalities of a
doubly linked list.

Class synopsis
--------------

**SplDoublyLinkedList**

<span class="ooclass"> class **SplDoublyLinkedList** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> <span class="oointerface">, <span
class="interfacename">Countable</span> </span> <span
class="oointerface">, <span class="interfacename">Serializable</span>
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">integer</span>
`SplDoublyLinkedList::IT_MODE_LIFO` <span class="initializer"> =
2</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplDoublyLinkedList::IT_MODE_FIFO` <span class="initializer"> =
0</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplDoublyLinkedList::IT_MODE_DELETE` <span class="initializer"> =
1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplDoublyLinkedList::IT_MODE_KEEP` <span class="initializer"> =
0</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">mixed</span> `$index`</span> , <span
class="methodparam"><span class="type">mixed</span> `$newval`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">bottom</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getIteratorMode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isEmpty</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">pop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">prev</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">push</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setIteratorMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">shift</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">top</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">unshift</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

Iteration Direction
-------------------

**`SplDoublyLinkedList::IT_MODE_LIFO`**  
The list will be iterated in a last in, first out order, like a stack.

**`SplDoublyLinkedList::IT_MODE_FIFO`**  
The list will be iterated in a first in, first out order, like a queue.

Iteration Behavior
------------------

**`SplDoublyLinkedList::IT_MODE_DELETE`**  
Iteration will remove the iterated elements.

**`SplDoublyLinkedList::IT_MODE_KEEP`**  
Iteration will not remove the iterated elements.

SplDoublyLinkedList::add
========================

Add/insert a new value at the specified index

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::add</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

Insert the value `newval` at the specified `index`, shuffling the
previous value at that index (and all subsequent values) up through the
list.

### Parameters

`index`  
The index where the new value is to be inserted.

`newval`  
The new value for the `index`.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">OutOfRangeException</span> when `index`
is out of bounds or when `index` cannot be parsed as an integer.

SplDoublyLinkedList::bottom
===========================

Peeks at the node from the beginning of the doubly linked list

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::bottom</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The value of the first node.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when the
data-structure is empty.

SplDoublyLinkedList::\_\_construct
==================================

Constructs a new doubly linked list

### Description

<span class="modifier">public</span> <span
class="methodname">SplDoublyLinkedList::\_\_construct</span> ( <span
class="methodparam">void</span> )

This constructs a new empty doubly linked list.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">SplDoublyLinkedList::\_\_construct</span> example**

``` php
<?php
$dll = new SplDoublyLinkedList();

$dll->push(2);
$dll->push(3);
$dll->unshift(5);

var_dump($dll);
?>
```

The above example will output:

    object(SplDoublyLinkedList)#1 (2) {
      ["flags":"SplDoublyLinkedList":private]=>
      int(0)
      ["dllist":"SplDoublyLinkedList":private]=>
      array(3) {
        [0]=>
        int(5)
        [1]=>
        int(2)
        [2]=>
        int(3)
      }
    }

SplDoublyLinkedList::count
==========================

Counts the number of elements in the doubly linked list

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplDoublyLinkedList::count</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the number of elements in the doubly linked list.

SplDoublyLinkedList::current
============================

Return current array entry

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::current</span> ( <span
class="methodparam">void</span> )

Get the current doubly linked list node.

### Parameters

This function has no parameters.

### Return Values

The current node value.

SplDoublyLinkedList::getIteratorMode
====================================

Returns the mode of iteration

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplDoublyLinkedList::getIteratorMode</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the different modes and flags that affect the iteration.

SplDoublyLinkedList::isEmpty
============================

Checks whether the doubly linked list is empty

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::isEmpty</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns whether the doubly linked list is empty.

SplDoublyLinkedList::key
========================

Return current node index

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::key</span> ( <span
class="methodparam">void</span> )

This function returns the current node index

### Parameters

This function has no parameters.

### Return Values

The current node index.

SplDoublyLinkedList::next
=========================

Move to next entry

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::next</span> ( <span
class="methodparam">void</span> )

Move the iterator to the next node.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplDoublyLinkedList::offsetExists
=================================

Returns whether the requested $index exists

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::offsetExists</span> (
<span class="methodparam"><span class="type">mixed</span>
`$index`</span> )

### Parameters

`index`  
The index being checked.

### Return Values

**`TRUE`** if the requested `index` exists, otherwise **`FALSE`**

SplDoublyLinkedList::offsetGet
==============================

Returns the value at the specified $index

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::offsetGet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

### Parameters

`index`  
The index with the value.

### Return Values

The value at the specified `index`.

### Errors/Exceptions

Throws <span class="classname">OutOfRangeException</span> when `index`
is out of bounds or when `index` cannot be parsed as an integer.

SplDoublyLinkedList::offsetSet
==============================

Sets the value at the specified $index to $newval

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

Sets the value at the specified `index` to `newval`.

### Parameters

`index`  
The index being set.

`newval`  
The new value for the `index`.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">OutOfRangeException</span> when `index`
is out of bounds or when `index` cannot be parsed as an integer.

SplDoublyLinkedList::offsetUnset
================================

Unsets the value at the specified $index

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::offsetUnset</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

Unsets the value at the specified index.

### Parameters

`index`  
The index being unset.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">OutOfRangeException</span> when `index`
is out of bounds or when `index` cannot be parsed as an integer.

SplDoublyLinkedList::pop
========================

Pops a node from the end of the doubly linked list

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::pop</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The value of the popped node.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when the
data-structure is empty.

SplDoublyLinkedList::prev
=========================

Move to previous entry

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::prev</span> ( <span
class="methodparam">void</span> )

Move the iterator to the previous node.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplDoublyLinkedList::push
=========================

Pushes an element at the end of the doubly linked list

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::push</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Pushes `value` at the end of the doubly linked list.

### Parameters

`value`  
The value to push.

### Return Values

No value is returned.

SplDoublyLinkedList::rewind
===========================

Rewind iterator back to the start

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::rewind</span> ( <span
class="methodparam">void</span> )

This rewinds the iterator to the beginning.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplDoublyLinkedList::serialize
==============================

Serializes the storage

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplDoublyLinkedList::serialize</span> ( <span
class="methodparam">void</span> )

Serializes the storage.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The serialized string.

### See Also

-   <span class="methodname">SplDoublyLinkedList::unserialize</span>

SplDoublyLinkedList::setIteratorMode
====================================

Sets the mode of iteration

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::setIteratorMode</span> (
<span class="methodparam"><span class="type">int</span> `$mode`</span> )

### Parameters

`mode`  
There are two orthogonal sets of modes that can be set:

-   <span class="simpara">The direction of the iteration (either one or
    the other):</span>
    -   <span class="simpara">**`SplDoublyLinkedList::IT_MODE_LIFO`**
        (Stack style)</span>
    -   <span class="simpara">**`SplDoublyLinkedList::IT_MODE_FIFO`**
        (Queue style)</span>
-   <span class="simpara">The behavior of the iterator (either one or
    the other):</span>
    -   <span class="simpara">**`SplDoublyLinkedList::IT_MODE_DELETE`**
        (Elements are deleted by the iterator)</span>
    -   <span class="simpara">**`SplDoublyLinkedList::IT_MODE_KEEP`**
        (Elements are traversed by the iterator)</span>

The default mode is: **`SplDoublyLinkedList::IT_MODE_FIFO`** \|
**`SplDoublyLinkedList::IT_MODE_KEEP`**

### Return Values

No value is returned.

SplDoublyLinkedList::shift
==========================

Shifts a node from the beginning of the doubly linked list

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::shift</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The value of the shifted node.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when the
data-structure is empty.

SplDoublyLinkedList::top
========================

Peeks at the node from the end of the doubly linked list

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::top</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The value of the last node.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when the
data-structure is empty.

SplDoublyLinkedList::unserialize
================================

Unserializes the storage

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

Unserializes the storage, from <span
class="methodname">SplDoublyLinkedList::serialize</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`serialized`  
The serialized string.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">SplDoublyLinkedList::serialize</span>

SplDoublyLinkedList::unshift
============================

Prepends the doubly linked list with an element

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::unshift</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Prepends `value` at the beginning of the doubly linked list.

### Parameters

`value`  
The value to unshift.

### Return Values

No value is returned.

SplDoublyLinkedList::valid
==========================

Check whether the doubly linked list contains more nodes

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::valid</span> ( <span
class="methodparam">void</span> )

Checks if the doubly linked list contains any more nodes.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the doubly linked list contains any more nodes,
**`FALSE`** otherwise.

Introduction
------------

The SplStack class provides the main functionalities of a stack
implemented using a doubly linked list.

Class synopsis
--------------

**SplStack**

<span class="ooclass"> class **SplStack** </span> <span class="ooclass">
<span class="modifier">extends</span> **SplDoublyLinkedList** </span>
<span class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> <span class="oointerface">, <span
class="interfacename">Countable</span> </span> {

/\* Methods \*/

<span class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="type">void</span> <span
class="methodname">setIteratorMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::add</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::bottom</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplDoublyLinkedList::count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplDoublyLinkedList::getIteratorMode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::isEmpty</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::offsetExists</span> (
<span class="methodparam"><span class="type">mixed</span>
`$index`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::offsetGet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::offsetUnset</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::pop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::prev</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::push</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplDoublyLinkedList::serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::setIteratorMode</span> (
<span class="methodparam"><span class="type">int</span> `$mode`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::shift</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::top</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::unshift</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::valid</span> ( <span
class="methodparam">void</span> )

}

SplStack::\_\_construct
=======================

Constructs a new stack implemented using a doubly linked list

### Description

<span class="methodname">SplStack::\_\_construct</span> ( <span
class="methodparam">void</span> )

This constructs a new empty stack.

> **Note**:
>
> This method automatically sets the iterator mode to
> SplDoublyLinkedList::IT\_MODE\_LIFO.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplStack::\_\_construct</span>
example**

``` php
<?php
$q = new SplStack();

$q[] = 1;
$q[] = 2;
$q[] = 3;

foreach ($q as $elem)  {
 echo $elem."\n";
}
?>
```

The above example will output:

    3
    2
    1

SplStack::setIteratorMode
=========================

Sets the mode of iteration

### Description

<span class="type">void</span> <span
class="methodname">SplStack::setIteratorMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

### Parameters

`mode`  
There is only one iteration parameter you can modify.

-   <span class="simpara">The behavior of the iterator (either one or
    the other):</span>
    -   <span class="simpara">SplDoublyLinkedList::IT\_MODE\_DELETE
        (Elements are deleted by the iterator)</span>
    -   <span class="simpara">SplDoublyLinkedList::IT\_MODE\_KEEP
        (Elements are traversed by the iterator)</span>

The default mode is 0x2 : SplDoublyLinkedList::IT\_MODE\_LIFO \|
SplDoublyLinkedList::IT\_MODE\_KEEP

**Warning**
The direction of iteration can no longer be changed for SplStacks.
Trying to do so will result in a <span
class="classname">RuntimeException</span> being thrown.

### Return Values

No value is returned.

Introduction
------------

The SplQueue class provides the main functionalities of a queue
implemented using a doubly linked list.

Class synopsis
--------------

**SplQueue**

<span class="ooclass"> class **SplQueue** </span> <span class="ooclass">
<span class="modifier">extends</span> **SplDoublyLinkedList** </span>
<span class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> <span class="oointerface">, <span
class="interfacename">Countable</span> </span> {

/\* Methods \*/

<span class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="type">mixed</span> <span class="methodname">dequeue</span>
( <span class="methodparam">void</span> )

<span class="type">void</span> <span class="methodname">enqueue</span> (
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="type">void</span> <span
class="methodname">setIteratorMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::add</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::bottom</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplDoublyLinkedList::count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplDoublyLinkedList::getIteratorMode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::isEmpty</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::offsetExists</span> (
<span class="methodparam"><span class="type">mixed</span>
`$index`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::offsetGet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::offsetUnset</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::pop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::prev</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::push</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplDoublyLinkedList::serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::setIteratorMode</span> (
<span class="methodparam"><span class="type">int</span> `$mode`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::shift</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplDoublyLinkedList::top</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplDoublyLinkedList::unshift</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplDoublyLinkedList::valid</span> ( <span
class="methodparam">void</span> )

}

SplQueue::\_\_construct
=======================

Constructs a new queue implemented using a doubly linked list

### Description

<span class="methodname">SplQueue::\_\_construct</span> ( <span
class="methodparam">void</span> )

This constructs a new empty queue.

> **Note**:
>
> This method automatically sets the iterator mode to
> SplDoublyLinkedList::IT\_MODE\_FIFO.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplQueue::\_\_construct</span>
example**

``` php
<?php
$q = new SplQueue();

$q[] = 1;
$q[] = 2;
$q[] = 3;

foreach ($q as $elem)  {
 echo $elem."\n";
}
?>
```

The above example will output:

    1
    2
    3

**Example \#2 Efficiently handling tasks with <span
class="classname">SplQueue</span>**

``` php
<?php
$q = new SplQueue();
$q->setIteratorMode(SplQueue::IT_MODE_DELETE);

// ... enqueue some tasks on the queue ...

// process them
foreach ($q as $task) {
    // ... process $task ...

    // add new tasks on the queue
    $q[] = $newTask;
    // ...
}
?>
```

SplQueue::dequeue
=================

Dequeues a node from the queue

### Description

<span class="type">mixed</span> <span
class="methodname">SplQueue::dequeue</span> ( <span
class="methodparam">void</span> )

Dequeues `value` from the top of the queue.

> **Note**:
>
> <span class="methodname">SplQueue::dequeue</span> is an alias of <span
> class="methodname">SplDoublyLinkedList::shift</span>.

### Parameters

This function has no parameters.

### Return Values

The value of the dequeued node.

SplQueue::enqueue
=================

Adds an element to the queue

### Description

<span class="type">void</span> <span
class="methodname">SplQueue::enqueue</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Enqueues `value` at the end of the queue.

> **Note**:
>
> <span class="methodname">SplQueue::enqueue</span> is an alias of <span
> class="methodname">SplDoublyLinkedList::push</span>.

### Parameters

`value`  
The value to enqueue.

### Return Values

No value is returned.

SplQueue::setIteratorMode
=========================

Sets the mode of iteration

### Description

<span class="type">void</span> <span
class="methodname">SplQueue::setIteratorMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

### Parameters

`mode`  
There is only one iteration parameter you can modify.

-   <span class="simpara">The behavior of the iterator (either one or
    the other):</span>
    -   <span class="simpara">**`SplDoublyLinkedList::IT_MODE_DELETE`**
        (Elements are deleted by the iterator)</span>
    -   <span class="simpara">**`SplDoublyLinkedList::IT_MODE_KEEP`**
        (Elements are traversed by the iterator)</span>

The default mode is: **`SplDoublyLinkedList::IT_MODE_FIFO`** \|
**`SplDoublyLinkedList::IT_MODE_KEEP`**

**Warning**
The direction of iteration can not be changed for SplQueues, it is
always **`SplDoublyLinkedList::IT_MODE_FIFO`**.

### Return Values

No value is returned.

### Errors/Exceptions

Throws a <span class="classname">RuntimeException</span> on trying to
change the direction of iteration by using
**`SplDoublyLinkedList::IT_MODE_LIFO`**.

Introduction
------------

The SplHeap class provides the main functionalities of a Heap.

Class synopsis
--------------

**SplHeap**

<span class="ooclass"> <span class="modifier">abstract</span> class
**SplHeap** </span> <span class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">Countable</span>
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">protected</span> <span class="type">int</span> <span
class="methodname">compare</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value1`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value2`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">extract</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">insert</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isCorrupted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isEmpty</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">recoverFromCorruption</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">top</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

SplHeap::compare
================

Compare elements in order to place them correctly in the heap while
sifting up

### Description

<span class="modifier">abstract</span> <span
class="modifier">protected</span> <span class="type">int</span> <span
class="methodname">SplHeap::compare</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value2`</span> )

Compare `value1` with `value2`.

**Warning**

Throwing exceptions in <span class="methodname">SplHeap::compare</span>
can corrupt the Heap and place it in a blocked state. You can unblock it
by calling <span
class="methodname">SplHeap::recoverFromCorruption</span>. However, some
elements might not be placed correctly and it may hence break the
heap-property.

### Parameters

`value1`  
The value of the first node being compared.

`value2`  
The value of the second node being compared.

### Return Values

Result of the comparison, positive integer if `value1` is greater than
`value2`, 0 if they are equal, negative integer otherwise.

> **Note**:
>
> Having multiple elements with the same value in a Heap is not
> recommended. They will end up in an arbitrary relative position.

SplHeap::\_\_construct
======================

Constructs a new empty heap

### Description

<span class="modifier">public</span> <span
class="methodname">SplHeap::\_\_construct</span> ( <span
class="methodparam">void</span> )

This constructs a new empty heap.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplHeap::count
==============

Counts the number of elements in the heap

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplHeap::count</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the number of elements in the heap.

SplHeap::current
================

Return current node pointed by the iterator

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::current</span> ( <span
class="methodparam">void</span> )

Get the current datastructure node.

### Parameters

This function has no parameters.

### Return Values

The current node value.

SplHeap::extract
================

Extracts a node from top of the heap and sift up

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::extract</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The value of the extracted node.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when the
data-structure is empty.

SplHeap::insert
===============

Inserts an element in the heap by sifting it up

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::insert</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Insert `value` in the heap.

### Parameters

`value`  
The value to insert.

### Return Values

No value is returned.

SplHeap::isCorrupted
====================

Tells if the heap is in a corrupted state

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::isCorrupted</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the heap is corrupted, **`FALSE`** otherwise.

SplHeap::isEmpty
================

Checks whether the heap is empty

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::isEmpty</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns whether the heap is empty.

SplHeap::key
============

Return current node index

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::key</span> ( <span
class="methodparam">void</span> )

This function returns the current node index

### Parameters

This function has no parameters.

### Return Values

The current node index.

SplHeap::next
=============

Move to the next node

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::next</span> ( <span
class="methodparam">void</span> )

Move to the next node. This will delete the top node of the heap.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplHeap::recoverFromCorruption
==============================

Recover from the corrupted state and allow further actions on the heap

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::recoverFromCorruption</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplHeap::rewind
===============

Rewind iterator back to the start (no-op)

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::rewind</span> ( <span
class="methodparam">void</span> )

This rewinds the iterator to the beginning. This is a no-op for heaps as
the iterator is virtual and in fact never moves from the top of the
heap.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplHeap::top
============

Peeks at the node from the top of the heap

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::top</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The value of the node on the top.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when the
data-structure is empty.

SplHeap::valid
==============

Check whether the heap contains more nodes

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::valid</span> ( <span
class="methodparam">void</span> )

Checks if the heap contains any more nodes.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the heap contains any more nodes, **`FALSE`**
otherwise.

Introduction
------------

The SplMaxHeap class provides the main functionalities of a heap,
keeping the maximum on the top.

Class synopsis
--------------

**SplMaxHeap**

<span class="ooclass"> class **SplMaxHeap** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SplHeap**
</span> <span class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">Countable</span>
</span> {

/\* Methods \*/

<span class="modifier">protected</span> <span class="type">int</span>
<span class="methodname">compare</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value2`</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">protected</span> <span class="type">int</span> <span
class="methodname">SplHeap::compare</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value2`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplHeap::count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::extract</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::insert</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::isCorrupted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::isEmpty</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::recoverFromCorruption</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::top</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::valid</span> ( <span
class="methodparam">void</span> )

}

SplMaxHeap::compare
===================

Compare elements in order to place them correctly in the heap while
sifting up

### Description

<span class="modifier">protected</span> <span class="type">int</span>
<span class="methodname">SplMaxHeap::compare</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value2`</span> )

Compare `value1` with `value2`.

### Parameters

`value1`  
The value of the first node being compared.

`value2`  
The value of the second node being compared.

### Return Values

Result of the comparison, positive integer if `value1` is greater than
`value2`, 0 if they are equal, negative integer otherwise.

> **Note**:
>
> Having multiple elements with the same value in a Heap is not
> recommended. They will end up in an arbitrary relative position.

Introduction
------------

The SplMinHeap class provides the main functionalities of a heap,
keeping the minimum on the top.

Class synopsis
--------------

**SplMinHeap**

<span class="ooclass"> class **SplMinHeap** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SplHeap**
</span> <span class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">Countable</span>
</span> {

/\* Methods \*/

<span class="modifier">protected</span> <span class="type">int</span>
<span class="methodname">compare</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value2`</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">protected</span> <span class="type">int</span> <span
class="methodname">SplHeap::compare</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value2`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplHeap::count</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::extract</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::insert</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::isCorrupted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::isEmpty</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::recoverFromCorruption</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplHeap::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplHeap::top</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplHeap::valid</span> ( <span
class="methodparam">void</span> )

}

SplMinHeap::compare
===================

Compare elements in order to place them correctly in the heap while
sifting up

### Description

<span class="modifier">protected</span> <span class="type">int</span>
<span class="methodname">SplMinHeap::compare</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value2`</span> )

Compare `value1` with `value2`.

### Parameters

`value1`  
The value of the first node being compared.

`value2`  
The value of the second node being compared.

### Return Values

Result of the comparison, positive integer if `value1` is lower than
`value2`, 0 if they are equal, negative integer otherwise.

> **Note**:
>
> Having multiple elements with the same value in a Heap is not
> recommended. They will end up in an arbitrary relative position.

Introduction
------------

The SplPriorityQueue class provides the main functionalities of a
prioritized queue, implemented using a max heap.

> **Note**: <span class="simpara"> The order of elements with identical
> priority is *undefined*. It may differ from the order in which they
> have been inserted. </span>

Class synopsis
--------------

**SplPriorityQueue**

<span class="ooclass"> class **SplPriorityQueue** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">Countable</span>
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">compare</span> ( <span class="methodparam"><span
class="type">mixed</span> `$priority1`</span> , <span
class="methodparam"><span class="type">mixed</span> `$priority2`</span>
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">extract</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getExtractFlags</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">insert</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value`</span> , <span
class="methodparam"><span class="type">mixed</span> `$priority`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isCorrupted</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isEmpty</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">recoverFromCorruption</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setExtractFlags</span> ( <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">top</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

SplPriorityQueue::compare
=========================

Compare priorities in order to place elements correctly in the heap
while sifting up

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplPriorityQueue::compare</span> ( <span
class="methodparam"><span class="type">mixed</span> `$priority1`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$priority2`</span> )

Compare `priority1` with `priority2`.

### Parameters

`priority1`  
The priority of the first node being compared.

`priority2`  
The priority of the second node being compared.

### Return Values

Result of the comparison, positive integer if `priority1` is greater
than `priority2`, 0 if they are equal, negative integer otherwise.

> **Note**:
>
> Multiple elements with the same priority will get dequeued in no
> particular order.

SplPriorityQueue::\_\_construct
===============================

Constructs a new empty queue

### Description

<span class="modifier">public</span> <span
class="methodname">SplPriorityQueue::\_\_construct</span> ( <span
class="methodparam">void</span> )

This constructs a new empty queue.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplPriorityQueue::count
=======================

Counts the number of elements in the queue

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplPriorityQueue::count</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the number of elements in the queue.

SplPriorityQueue::current
=========================

Return current node pointed by the iterator

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplPriorityQueue::current</span> ( <span
class="methodparam">void</span> )

Get the current datastructure node.

### Parameters

This function has no parameters.

### Return Values

The value or priority (or both) of the current node, depending on the
extract flag.

SplPriorityQueue::extract
=========================

Extracts a node from top of the heap and sift up

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplPriorityQueue::extract</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The value or priority (or both) of the extracted node, depending on the
extract flag.

SplPriorityQueue::getExtractFlags
=================================

Get the flags of extraction

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplPriorityQueue::getExtractFlags</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

SplPriorityQueue::insert
========================

Inserts an element in the queue by sifting it up

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplPriorityQueue::insert</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$priority`</span> )

Insert `value` with the priority `priority` in the queue.

### Parameters

`value`  
The value to insert.

`priority`  
The associated priority.

### Return Values

Returns **`TRUE`**.

SplPriorityQueue::isCorrupted
=============================

Tells if the priority queue is in a corrupted state

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplPriorityQueue::isCorrupted</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the priority queue is corrupted, **`FALSE`**
otherwise.

SplPriorityQueue::isEmpty
=========================

Checks whether the queue is empty

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplPriorityQueue::isEmpty</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns whether the queue is empty.

SplPriorityQueue::key
=====================

Return current node index

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplPriorityQueue::key</span> ( <span
class="methodparam">void</span> )

This function returns the current node index

### Parameters

This function has no parameters.

### Return Values

The current node index.

SplPriorityQueue::next
======================

Move to the next node

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplPriorityQueue::next</span> ( <span
class="methodparam">void</span> )

Extracts the top node from the queue.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplPriorityQueue::recoverFromCorruption
=======================================

Recover from the corrupted state and allow further actions on the queue

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplPriorityQueue::recoverFromCorruption</span>
( <span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplPriorityQueue::rewind
========================

Rewind iterator back to the start (no-op)

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplPriorityQueue::rewind</span> ( <span
class="methodparam">void</span> )

This rewinds the iterator to the beginning. This is a no-op for heaps as
the iterator is virtual and in fact never moves from the top of the
heap.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplPriorityQueue::setExtractFlags
=================================

Sets the mode of extraction

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplPriorityQueue::setExtractFlags</span> (
<span class="methodparam"><span class="type">int</span> `$flags`</span>
)

### Parameters

`flags`  
Defines what is extracted by <span
class="methodname">SplPriorityQueue::current</span>, <span
class="methodname">SplPriorityQueue::top</span> and <span
class="methodname">SplPriorityQueue::extract</span>.

-   <span class="simpara">**`SplPriorityQueue::EXTR_DATA`**
    (0x00000001): Extract the data</span>
-   <span class="simpara">**`SplPriorityQueue::EXTR_PRIORITY`**
    (0x00000002): Extract the priority</span>
-   <span class="simpara">**`SplPriorityQueue::EXTR_BOTH`**
    (0x00000003): Extract an array containing both</span>

The default mode is **`SplPriorityQueue::EXTR_DATA`**.

### Return Values

No value is returned.

SplPriorityQueue::top
=====================

Peeks at the node from the top of the queue

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplPriorityQueue::top</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The value or priority (or both) of the top node, depending on the
extract flag.

SplPriorityQueue::valid
=======================

Check whether the queue contains more nodes

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplPriorityQueue::valid</span> ( <span
class="methodparam">void</span> )

Checks if the queue contains any more nodes.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the queue contains any more nodes, **`FALSE`**
otherwise.

Introduction
------------

The SplFixedArray class provides the main functionalities of array. The
main differences between a SplFixedArray and a normal PHP array is that
the SplFixedArray is of fixed length and allows only integers within the
range as indexes. The advantage is that it uses less memory than a
standard <span class="type">array</span>.

Class synopsis
--------------

**SplFixedArray**

<span class="ooclass"> class **SplFixedArray** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> <span class="oointerface">, <span
class="interfacename">Countable</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$size`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">SplFixedArray</span>
<span class="methodname">fromArray</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$save_indexes`<span class="initializer"> = **`TRUE`**</span></span> \]
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">key</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">toArray</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_wakeup</span> ( <span
class="methodparam">void</span> )

}

Examples
--------

**Example \#1 <span class="classname">SplFixedArray</span> usage
example**

``` php
<?php
// Initialize the array with a fixed length
$array = new SplFixedArray(5);

$array[1] = 2;
$array[4] = "foo";

var_dump($array[0]); // NULL
var_dump($array[1]); // int(2)

var_dump($array["4"]); // string(3) "foo"

// Increase the size of the array to 10
$array->setSize(10);

$array[9] = "asdf";

// Shrink the array to a size of 2
$array->setSize(2);

// The following lines throw a RuntimeException: Index invalid or out of range
try {
    var_dump($array["non-numeric"]);
} catch(RuntimeException $re) {
    echo "RuntimeException: ".$re->getMessage()."\n";
}

try {
    var_dump($array[-1]);
} catch(RuntimeException $re) {
    echo "RuntimeException: ".$re->getMessage()."\n";
}

try {
    var_dump($array[5]);
} catch(RuntimeException $re) {
    echo "RuntimeException: ".$re->getMessage()."\n";
}
?>
```

The above example will output:

    NULL
    int(2)
    string(3) "foo"
    RuntimeException: Index invalid or out of range
    RuntimeException: Index invalid or out of range
    RuntimeException: Index invalid or out of range

SplFixedArray::\_\_construct
============================

Constructs a new fixed array

### Description

<span class="modifier">public</span> <span
class="methodname">SplFixedArray::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$size`<span
class="initializer"> = 0</span></span> \] )

Initializes a fixed array with a number of **`NULL`** values equal to
`size`.

### Parameters

`size`  
The size of the fixed array. This expects a number between *0* and
**`PHP_INT_MAX`**.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">InvalidArgumentException</span> when
`size` is a negative number.

Raises **`E_WARNING`** when `size` cannot be parsed as a number.

### Examples

**Example \#1 <span class="function">SplFixedArray::\_\_construct</span>
example**

``` php
<?php
$array = new SplFixedArray(5);

$array[1] = 2;
$array[4] = "foo";

foreach($array as $v) {
  var_dump($v);
}
?>
```

The above example will output:

    NULL
    int(2)
    NULL
    NULL
    string(3) "foo"

SplFixedArray::count
====================

Returns the size of the array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFixedArray::count</span> ( <span
class="methodparam">void</span> )

Returns the size of the array.

### Parameters

This function has no parameters.

### Return Values

Returns the size of the array.

### Examples

**Example \#1 <span class="methodname">SplFixedArray::count</span>
example**

``` php
<?php
$array = new SplFixedArray(5);
echo $array->count() . "\n";
echo count($array) . "\n";
?>
```

The above example will output:

    5
    5

### Notes

> **Note**:
>
> This method is functionally equivalent to <span
> class="methodname">SplFixedArray::getSize</span>.

> **Note**:
>
> The count of elements is always equal to the set size because all
> values are initially initialized with **`NULL`**.

### See Also

-   <span class="methodname">SplFixedArray::getSize</span>

SplFixedArray::current
======================

Return current array entry

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplFixedArray::current</span> ( <span
class="methodparam">void</span> )

Get the current array element.

### Parameters

This function has no parameters.

### Return Values

The current element value.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when the internal
array pointer points to an invalid index or is out of bounds.

SplFixedArray::fromArray
========================

Import a PHP array in a <span class="classname">SplFixedArray</span>
instance

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">SplFixedArray</span>
<span class="methodname">SplFixedArray::fromArray</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$save_indexes`<span class="initializer"> = **`TRUE`**</span></span> \]
)

Import the PHP array `array` in a new <span
class="classname">SplFixedArray</span> instance

### Parameters

`array`  
The array to import.

`save_indexes`  
Try to save the numeric indexes used in the original array.

### Return Values

Returns an instance of <span class="classname">SplFixedArray</span>
containing the array content.

### Examples

**Example \#1 <span class="function">SplFixedArray::fromArray</span>
example**

``` php
<?php
$fa = SplFixedArray::fromArray(array(1 => 1, 0 => 2, 3 => 3));

var_dump($fa);

$fa = SplFixedArray::fromArray(array(1 => 1, 0 => 2, 3 => 3), false);

var_dump($fa);
?>
```

The above example will output:

    object(SplFixedArray)#1 (4) {
      [0]=>
      int(2)
      [1]=>
      int(1)
      [2]=>
      NULL
      [3]=>
      int(3)
    }
    object(SplFixedArray)#2 (3) {
      [0]=>
      int(1)
      [1]=>
      int(2)
      [2]=>
      int(3)
    }

SplFixedArray::getSize
======================

Gets the size of the array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFixedArray::getSize</span> ( <span
class="methodparam">void</span> )

Gets the size of the array.

### Parameters

This function has no parameters.

### Return Values

Returns the size of the array, as an <span class="type">integer</span>.

### Examples

**Example \#1 <span class="methodname">SplFixedArray::getSize</span>
example**

``` php
<?php
$array = new SplFixedArray(5);
echo $array->getSize()."\n";
$array->setSize(10);
echo $array->getSize()."\n";
?>
```

The above example will output:

    5
    10

### Notes

> **Note**:
>
> This method is functionally equivalent to <span
> class="methodname">SplFixedArray::count</span>

### See Also

-   <span class="methodname">SplFixedArray::count</span>

SplFixedArray::key
==================

Return current array index

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFixedArray::key</span> ( <span
class="methodparam">void</span> )

Returns the current array index.

### Parameters

This function has no parameters.

### Return Values

The current array index.

SplFixedArray::next
===================

Move to next entry

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFixedArray::next</span> ( <span
class="methodparam">void</span> )

Move the iterator to the next array entry.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplFixedArray::offsetExists
===========================

Returns whether the requested index exists

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFixedArray::offsetExists</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Checks whether the requested index `index` exists.

### Parameters

`index`  
The index being checked.

### Return Values

**`TRUE`** if the requested `index` exists, otherwise **`FALSE`**

SplFixedArray::offsetGet
========================

Returns the value at the specified index

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplFixedArray::offsetGet</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Returns the value at the index `index`.

### Parameters

`index`  
The index with the value.

### Return Values

The value at the specified `index`.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when `index` is
outside the defined size of the array or when `index` cannot be parsed
as an integer.

SplFixedArray::offsetSet
========================

Sets a new value at a specified index

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFixedArray::offsetSet</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

Sets the value at the specified `index` to `newval`.

### Parameters

`index`  
The index being set.

`newval`  
The new value for the `index`.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when `index` is
outside the defined size of the array or when `index` cannot be parsed
as an integer.

SplFixedArray::offsetUnset
==========================

Unsets the value at the specified $index

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFixedArray::offsetUnset</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Unsets the value at the specified index.

### Parameters

`index`  
The index being unset.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> when `index` is
outside the defined size of the array or when `index` cannot be parsed
as an integer.

SplFixedArray::rewind
=====================

Rewind iterator back to the start

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFixedArray::rewind</span> ( <span
class="methodparam">void</span> )

Rewinds the iterator to the beginning.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

SplFixedArray::setSize
======================

Change the size of an array

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFixedArray::setSize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

Change the size of an array to the new size of `size`. If `size` is less
than the current array size, any values after the new size will be
discarded. If `size` is greater than the current array size, the array
will be padded with **`NULL`** values.

### Parameters

`size`  
The new array size. This should be a value between *0* and
**`PHP_INT_MAX`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

Throws <span class="classname">InvalidArgumentException</span> when
`size` is less than zero.

Raises **`E_WARNING`** when `size` cannot be used as a number.

### Examples

**Example \#1 <span class="function">SplFixedArray::setSize</span>
example**

``` php
<?php
   $array = new SplFixedArray(5);
   echo $array->getSize()."\n";
   $array->setSize(10);
   echo $array->getSize()."\n";
?>
```

The above example will output:

    5
    10

SplFixedArray::toArray
======================

Returns a PHP array from the fixed array

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplFixedArray::toArray</span> ( <span
class="methodparam">void</span> )

Returns a PHP array from the fixed array.

### Parameters

This function has no parameters.

### Return Values

Returns a PHP <span class="type">array</span>, similar to the fixed
array.

### Examples

**Example \#1 <span class="function">SplFixedArray::toArray</span>
example**

``` php
<?php
$fa = new SplFixedArray(3);
$fa[0] = 0;
$fa[2] = 2;
var_dump($fa->toArray());
?>
```

The above example will output:

    array(3) {
      [0]=>
      int(0)
      [1]=>
      NULL
      [2]=>
      int(2)
    }

SplFixedArray::valid
====================

Check whether the array contains more elements

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFixedArray::valid</span> ( <span
class="methodparam">void</span> )

Checks if the array contains any more elements.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the array contains any more elements, **`FALSE`**
otherwise.

SplFixedArray::\_\_wakeup
=========================

Reinitialises the array after being unserialised

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFixedArray::\_\_wakeup</span> ( <span
class="methodparam">void</span> )

Reinitialises the array after being unserialised.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Introduction
------------

The SplObjectStorage class provides a map from objects to data or, by
ignoring data, an object set. This dual purpose can be useful in many
cases involving the need to uniquely identify objects.

Class synopsis
--------------

**SplObjectStorage**

<span class="ooclass"> class **SplObjectStorage** </span> <span
class="oointerface">implements <span
class="interfacename">Countable</span> </span> <span
class="oointerface">, <span class="interfacename">Iterator</span>
</span> <span class="oointerface">, <span
class="interfacename">Serializable</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">addAll</span> ( <span class="methodparam"><span
class="type">SplObjectStorage</span> `$storage`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">attach</span> ( <span class="methodparam"><span
class="type">object</span> `$object`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$data`<span
class="initializer"> = **`NULL`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">contains</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">detach</span> ( <span class="methodparam"><span
class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getHash</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">key</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$data`<span class="initializer"> = **`NULL`**</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">removeAll</span> ( <span
class="methodparam"><span class="type">SplObjectStorage</span>
`$storage`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">removeAllExcept</span> ( <span
class="methodparam"><span class="type">SplObjectStorage</span>
`$storage`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setInfo</span> ( <span
class="methodparam"><span class="type">mixed</span> `$data`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

Examples
--------

**Example \#1 <span class="classname">SplObjectStorage</span> as a set**

``` php
<?php
// As an object set
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;
$o3 = new StdClass;

$s->attach($o1);
$s->attach($o2);

var_dump($s->contains($o1));
var_dump($s->contains($o2));
var_dump($s->contains($o3));

$s->detach($o2);

var_dump($s->contains($o1));
var_dump($s->contains($o2));
var_dump($s->contains($o3));
?>
```

The above example will output:

    bool(true)
    bool(true)
    bool(false)
    bool(true)
    bool(false)
    bool(false)

**Example \#2 <span class="classname">SplObjectStorage</span> as a map**

``` php
<?php
// As a map from objects to data
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;
$o3 = new StdClass;

$s[$o1] = "data for object 1";
$s[$o2] = array(1,2,3);

if (isset($s[$o2])) {
    var_dump($s[$o2]);
}
?>
```

The above example will output:

    array(3) {
      [0]=>
      int(1)
      [1]=>
      int(2)
      [2]=>
      int(3)
    }

SplObjectStorage::addAll
========================

Adds all objects from another storage

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::addAll</span> ( <span
class="methodparam"><span class="type">SplObjectStorage</span>
`$storage`</span> )

Adds all objects-data pairs from a different storage in the current
storage.

### Parameters

`storage`  
The storage you want to import.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplObjectStorage::addAll</span>
example**

``` php
<?php
$o = new StdClass;
$a = new SplObjectStorage();
$a[$o] = "hello";

$b = new SplObjectStorage();
$b->addAll($a);
echo $b[$o]."\n";
?>
```

The above example will output something similar to:

    hello

### See Also

-   <span class="methodname">SplObjectStorage::removeAll</span>

SplObjectStorage::attach
========================

Adds an object in the storage

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::attach</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$data`<span class="initializer"> = **`NULL`**</span></span> \] )

Adds an <span class="type">object</span> inside the storage, and
optionally associate it to some data.

### Parameters

`object`  
The <span class="type">object</span> to add.

`data`  
The data to associate with the <span class="type">object</span>.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplObjectStorage::attach</span>
example**

``` php
<?php
$o1 = new StdClass;
$o2 = new StdClass;
$s = new SplObjectStorage();
$s->attach($o1); // similar to $s[$o1] = NULL;
$s->attach($o2, "hello"); // similar to $s[$o2] = "hello";

var_dump($s[$o1]);
var_dump($s[$o2]);

?>
```

The above example will output something similar to:

    NULL
    string(5) "hello"

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 5.3.0   | Added the `data` parameter. |

### See Also

-   <span class="methodname">SplObjectStorage::detach</span>
-   <span class="methodname">SplObjectStorage::offsetSet</span>

SplObjectStorage::contains
==========================

Checks if the storage contains a specific object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplObjectStorage::contains</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

Checks if the storage contains the <span class="type">object</span>
provided.

### Parameters

`object`  
The <span class="type">object</span> to look for.

### Return Values

Returns **`TRUE`** if the <span class="type">object</span> is in the
storage, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">SplObjectStorage::contains</span>
example**

``` php
<?php
$o1 = new StdClass;
$o2 = new StdClass;

$s = new SplObjectStorage();

$s[$o1] = "hello";
var_dump($s->contains($o1));
var_dump($s->contains($o2));
?>
```

The above example will output something similar to:

    bool(true)
    bool(false)

### See Also

-   <span class="methodname">SplObjectStorage::offsetExists</span>

SplObjectStorage::count
=======================

Returns the number of objects in the storage

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplObjectStorage::count</span> ( <span
class="methodparam">void</span> )

Counts the number of objects in the storage.

### Parameters

This function has no parameters.

### Return Values

The number of objects in the storage.

### Examples

**Example \#1 <span class="function">SplObjectStorage::count</span>
example**

``` php
<?php
$s = new SplObjectStorage();
$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1);
$s->attach($o2);
$s->attach($o1);
var_dump($s->count());
var_dump(count($s));
?>
```

The above example will output something similar to:

    int(2)
    int(2)

### See Also

-   <span class="methodname">SplObjectStorage::attach</span>
-   <span class="methodname">SplObjectStorage::detach</span>

SplObjectStorage::current
=========================

Returns the current storage entry

### Description

<span class="modifier">public</span> <span class="type">object</span>
<span class="methodname">SplObjectStorage::current</span> ( <span
class="methodparam">void</span> )

Returns the current storage entry.

### Parameters

This function has no parameters.

### Return Values

The <span class="type">object</span> at the current iterator position.

### Examples

**Example \#1 <span class="function">SplObjectStorage::current</span>
example**

``` php
<?php
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1, "d1");
$s->attach($o2, "d2");

$s->rewind();
while($s->valid()) {
    $index  = $s->key();
    $object = $s->current(); // similar to current($s)
    $data   = $s->getInfo();

    var_dump($object);
    var_dump($data);
    $s->next();
}
?>
```

The above example will output something similar to:

    object(stdClass)#2 (0) {
    }
    string(2) "d1"
    object(stdClass)#3 (0) {
    }
    string(2) "d2"

### See Also

-   <span class="methodname">SplObjectStorage::rewind</span>
-   <span class="methodname">SplObjectStorage::key</span>
-   <span class="methodname">SplObjectStorage::next</span>
-   <span class="methodname">SplObjectStorage::valid</span>
-   <span class="methodname">SplObjectStorage::getInfo</span>

SplObjectStorage::detach
========================

Removes an <span class="type">object</span> from the storage

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::detach</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

Removes the <span class="type">object</span> from the storage.

### Parameters

`object`  
The <span class="type">object</span> to remove.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplObjectStorage::detach</span>
example**

``` php
<?php
$o = new StdClass;
$s = new SplObjectStorage();
$s->attach($o);
var_dump(count($s));
$s->detach($o);
var_dump(count($s));
?>
```

The above example will output something similar to:

    int(1)
    int(0)

### See Also

-   <span class="methodname">SplObjectStorage::attach</span>
-   <span class="methodname">SplObjectStorage::removeAll</span>

SplObjectStorage::getHash
=========================

Calculate a unique identifier for the contained objects

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplObjectStorage::getHash</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

This method calculates an identifier for the objects added to an <span
class="classname">SplObjectStorage</span> object.

The implementation in <span class="classname">SplObjectStorage</span>
returns the same value as <span
class="function">spl\_object\_hash</span>.

The storage object will never contain more than one object with the same
identifier. As such, it can be used to implement a set (a collection of
unique values) where the quality of an object being unique is determined
by the value returned by this function being unique.

### Parameters

`object`  
The object whose identifier is to be calculated.

### Return Values

A <span class="type">string</span> with the calculated identifier.

### Errors/Exceptions

A <span class="classname">RuntimeException</span> is thrown when the
returned value is not a <span class="type">string</span>.

### Examples

**Example \#1 <span class="function">SplObjectStorage::getHash</span>
example**

``` php
<?php
class OneSpecimenPerClassStorage extends SplObjectStorage {
    public function getHash($o) {
        return get_class($o);
    }
}
class A {}

$s = new OneSpecimenPerClassStorage;
$o1 = new stdClass;
$o2 = new stdClass;
$o3 = new A;

$s[$o1] = 1;
//$o2 is considered equal to $o1 so the value is replaced
$s[$o2] = 2;
$s[$o3] = 3;

//these are considered equal to the objects before
//so they can be used to access the values stored under them
$p1 = new stdClass;
$p2 = new A;
echo $s[$p1], "\n";
echo $s[$p2], "\n";
?>
```

The above example will output something similar to:

    2
    3

### See Also

-   <span class="function">spl\_object\_hash</span>

SplObjectStorage::getInfo
=========================

Returns the data associated with the current iterator entry

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplObjectStorage::getInfo</span> ( <span
class="methodparam">void</span> )

Returns the data, or info, associated with the object pointed by the
current iterator position.

### Parameters

This function has no parameters.

### Return Values

The data associated with the current iterator position.

### Examples

**Example \#1 <span class="function">SplObjectStorage::getInfo</span>
example**

``` php
<?php
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1, "d1");
$s->attach($o2, "d2");

$s->rewind();
while($s->valid()) {
    $index  = $s->key();
    $object = $s->current(); // similar to current($s)
    $data   = $s->getInfo();

    var_dump($object);
    var_dump($data);
    $s->next();
}
?>
```

The above example will output something similar to:

    object(stdClass)#2 (0) {
    }
    string(2) "d1"
    object(stdClass)#3 (0) {
    }
    string(2) "d2"

### See Also

-   <span class="methodname">SplObjectStorage::current</span>
-   <span class="methodname">SplObjectStorage::rewind</span>
-   <span class="methodname">SplObjectStorage::key</span>
-   <span class="methodname">SplObjectStorage::next</span>
-   <span class="methodname">SplObjectStorage::valid</span>
-   <span class="methodname">SplObjectStorage::setInfo</span>

SplObjectStorage::key
=====================

Returns the index at which the iterator currently is

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplObjectStorage::key</span> ( <span
class="methodparam">void</span> )

Returns the index at which the iterator currently is.

### Parameters

This function has no parameters.

### Return Values

The index corresponding to the position of the iterator.

### Examples

**Example \#1 <span class="function">SplObjectStorage::key</span>
example**

``` php
<?php
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1, "d1");
$s->attach($o2, "d2");

$s->rewind();
while($s->valid()) {
    $index  = $s->key();
    $object = $s->current(); // similar to current($s)

    var_dump($index);
    var_dump($object);
    $s->next();
}
?>
```

The above example will output something similar to:

    int(0)
    object(stdClass)#2 (0) {
    }
    int(1)
    object(stdClass)#3 (0) {
    }

### See Also

-   <span class="methodname">SplObjectStorage::rewind</span>
-   <span class="methodname">SplObjectStorage::current</span>
-   <span class="methodname">SplObjectStorage::next</span>
-   <span class="methodname">SplObjectStorage::valid</span>

SplObjectStorage::next
======================

Move to the next entry

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::next</span> ( <span
class="methodparam">void</span> )

Moves the iterator to the next <span class="type">object</span> in the
storage.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplObjectStorage::next</span>
example**

``` php
<?php
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1, "d1");
$s->attach($o2, "d2");

$s->rewind();
while($s->valid()) {
    $index  = $s->key();
    $object = $s->current(); // similar to current($s)

    var_dump($index);
    var_dump($object);
    $s->next();
}
?>
```

The above example will output something similar to:

    int(0)
    object(stdClass)#2 (0) {
    }
    int(1)
    object(stdClass)#3 (0) {
    }

### See Also

-   <span class="methodname">SPLObjectStorage::rewind</span>

SplObjectStorage::offsetExists
==============================

Checks whether an object exists in the storage

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplObjectStorage::offsetExists</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

Checks whether an <span class="type">object</span> exists in the
storage.

> **Note**:
>
> <span class="methodname">SplObjectStorage::offsetExists</span> is an
> alias of <span class="methodname">SplObjectStorage::contains</span>.

### Parameters

`object`  
The <span class="type">object</span> to look for.

### Return Values

Returns **`TRUE`** if the <span class="type">object</span> exists in the
storage, and **`FALSE`** otherwise.

### Examples

**Example \#1 <span
class="function">SplObjectStorage::offsetExists</span> example**

``` php
<?php
$s = new SplObjectStorage;
$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1);

var_dump($s->offsetExists($o1)); // Similar to isset($s[$o1])
var_dump($s->offsetExists($o2)); // Similar to isset($s[$o2])
?>
```

The above example will output something similar to:

    bool(true)
    bool(false)

### See Also

-   <span class="methodname">SplObjectStorage::offsetSet</span>
-   <span class="methodname">SplObjectStorage::offsetGet</span>
-   <span class="methodname">SplObjectStorage::offsetUnset</span>

SplObjectStorage::offsetGet
===========================

Returns the data associated with an <span class="type">object</span>

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplObjectStorage::offsetGet</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

Returns the data associated with an <span class="type">object</span> in
the storage.

### Parameters

`object`  
The <span class="type">object</span> to look for.

### Return Values

The data previously associated with the <span class="type">object</span>
in the storage.

### Errors/Exceptions

Throws <span class="classname">UnexpectedValueException</span> when
`object` could not be found.

### Examples

**Example \#1 <span class="function">SplObjectStorage::offsetGet</span>
example**

``` php
<?php
$s = new SplObjectStorage;

$o1 = new StdClass;
$o2 = new StdClass;

$s[$o1] = "hello";
$s->attach($o2);


var_dump($s->offsetGet($o1)); // Similar to $s[$o1]
var_dump($s->offsetGet($o2)); // Similar to $s[$o2]
?>
```

The above example will output something similar to:

    string(5) "hello"
    NULL

### See Also

-   <span class="methodname">SplObjectStorage::offsetSet</span>
-   <span class="methodname">SplObjectStorage::offsetExists</span>
-   <span class="methodname">SplObjectStorage::offsetUnset</span>

SplObjectStorage::offsetSet
===========================

Associates data to an object in the storage

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::offsetSet</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$data`<span class="initializer"> = **`NULL`**</span></span> \] )

Associate data to an <span class="type">object</span> in the storage.

> **Note**:
>
> <span class="methodname">SplObjectStorage::offsetSet</span> is an
> alias of <span class="methodname">SplObjectStorage::attach</span>.

### Parameters

`object`  
The <span class="type">object</span> to associate data with.

`data`  
The data to associate with the <span class="type">object</span>.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplObjectStorage::offsetSet</span>
example**

``` php
<?php
$s = new SplObjectStorage;

$o1 = new StdClass;

$s->offsetSet($o1, "hello"); // Similar to $s[$o1] = "hello";

var_dump($s[$o1]);
?>
```

The above example will output something similar to:

    string(5) "hello"

### See Also

-   <span class="methodname">SplObjectStorage::attach</span>
-   <span class="methodname">SplObjectStorage::offsetGet</span>
-   <span class="methodname">SplObjectStorage::offsetExists</span>
-   <span class="methodname">SplObjectStorage::offsetUnset</span>

SplObjectStorage::offsetUnset
=============================

Removes an object from the storage

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::offsetUnset</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

Removes an <span class="type">object</span> from the storage.

> **Note**:
>
> <span class="methodname">SplObjectStorage::offsetUnset</span> is an
> alias of <span class="methodname">SplObjectStorage::detach</span>.

### Parameters

`object`  
The <span class="type">object</span> to remove.

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">SplObjectStorage::offsetUnset</span> example**

``` php
<?php
$o = new StdClass;
$s = new SplObjectStorage();
$s->attach($o);
var_dump(count($s));
$s->offsetUnset($o); // Similar to unset($s[$o])
var_dump(count($s));
?>
```

The above example will output something similar to:

    int(1)
    int(0)

### See Also

-   <span class="methodname">SplObjectStorage::offsetGet</span>
-   <span class="methodname">SplObjectStorage::offsetSet</span>
-   <span class="methodname">SplObjectStorage::offsetExists</span>

SplObjectStorage::removeAll
===========================

Removes objects contained in another storage from the current storage

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::removeAll</span> ( <span
class="methodparam"><span class="type">SplObjectStorage</span>
`$storage`</span> )

Removes objects contained in another storage from the current storage.

### Parameters

`storage`  
The storage containing the elements to remove.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplObjectStorage::removeAll</span>
example**

``` php
<?php
$o1 = new StdClass;
$o2 = new StdClass;
$a = new SplObjectStorage();
$a[$o1] = "foo";

$b = new SplObjectStorage();
$b[$o1] = "bar";
$b[$o2] = "gee";

var_dump(count($b));
$b->removeAll($a);
var_dump(count($b));
?>
```

The above example will output something similar to:

    int(2)
    int(1)

### See Also

-   <span class="methodname">SplObjectStorage::addAll</span>

SplObjectStorage::removeAllExcept
=================================

Removes all objects except for those contained in another storage from
the current storage

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::removeAllExcept</span> (
<span class="methodparam"><span class="type">SplObjectStorage</span>
`$storage`</span> )

Removes all objects except for those contained in another storage from
the current storage.

### Parameters

`storage`  
The storage containing the elements to retain in the current storage.

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">SplObjectStorage::removeAllExcept</span> example**

``` php
<?php
$a = (object) 'a'; 
$b = (object) 'b'; 
$c = (object) 'c'; 

$foo = new SplObjectStorage;
$foo->attach($a);
$foo->attach($b);

$bar = new SplObjectStorage;
$bar->attach($b);
$bar->attach($c);

$foo->removeAllExcept($bar);
var_dump($foo->contains($a));
var_dump($foo->contains($b));
?>
```

The above example will output something similar to:

    bool(false)
    bool(true)

SplObjectStorage::rewind
========================

Rewind the iterator to the first storage element

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::rewind</span> ( <span
class="methodparam">void</span> )

Rewind the iterator to the first storage element.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplObjectStorage::rewind</span>
example**

``` php
<?php
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1, "d1");
$s->attach($o2, "d2");

$s->rewind();
while($s->valid()) {
    $index  = $s->key();
    $object = $s->current(); // similar to current($s)
    $data   = $s->getInfo();

    var_dump($object);
    var_dump($data);
    $s->next();
}
?>
```

The above example will output something similar to:

    int(1)
    int(0)

### See Also

-   <span class="methodname">SplObjectStorage::next</span>

SplObjectStorage::serialize
===========================

Serializes the storage

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplObjectStorage::serialize</span> ( <span
class="methodparam">void</span> )

Returns a string representation of the storage.

### Parameters

This function has no parameters.

### Return Values

A string representing the storage.

### Examples

**Example \#1 <span class="function">SplObjectStorage::serialize</span>
example**

``` php
<?php
$s = new SplObjectStorage;
$o = new StdClass;
$s[$o] = "data";

echo $s->serialize()."\n";
?>
```

The above example will output something similar to:

    x:i:1;O:8:"stdClass":0:{},s:4:"data";;m:a:0:{}

### See Also

-   <span class="methodname">SplObjectStorage::unserialize</span>

SplObjectStorage::setInfo
=========================

Sets the data associated with the current iterator entry

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::setInfo</span> ( <span
class="methodparam"><span class="type">mixed</span> `$data`</span> )

Associates data, or info, with the object currently pointed to by the
iterator.

### Parameters

`data`  
The data to associate with the current iterator entry.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplObjectStorage::setInfo</span>
example**

``` php
<?php
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1, "d1");
$s->attach($o2, "d2");

$s->rewind();
while($s->valid()) {
    $s->setInfo("new");
    $s->next();
}
var_dump($s[$o1]);
var_dump($s[$o2]);
?>
```

The above example will output something similar to:

    string(3) "new"
    string(3) "new"

### See Also

-   <span class="methodname">SplObjectStorage::current</span>
-   <span class="methodname">SplObjectStorage::rewind</span>
-   <span class="methodname">SplObjectStorage::key</span>
-   <span class="methodname">SplObjectStorage::next</span>
-   <span class="methodname">SplObjectStorage::valid</span>
-   <span class="methodname">SplObjectStorage::getInfo</span>

SplObjectStorage::unserialize
=============================

Unserializes a storage from its string representation

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplObjectStorage::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

Unserializes storage entries and attach them to the current storage.

### Parameters

`serialized`  
The serialized representation of a storage.

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">SplObjectStorage::unserialize</span> example**

``` php
<?php
$s1 = new SplObjectStorage;
$s2 = new SplObjectStorage;
$o = new StdClass;
$s1[$o] = "data";

$s2->unserialize($s1->serialize());

var_dump(count($s2));
?>
```

The above example will output something similar to:

    int(1)

### See Also

-   <span class="methodname">SplObjectStorage::serialize</span>

SplObjectStorage::valid
=======================

Returns if the current iterator entry is valid

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplObjectStorage::valid</span> ( <span
class="methodparam">void</span> )

Returns if the current iterator entry is valid.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the iterator entry is valid, **`FALSE`**
otherwise.

### Examples

**Example \#1 <span class="function">SplObjectStorage::valid</span>
example**

``` php
<?php
$s = new SplObjectStorage();

$o1 = new StdClass;
$o2 = new StdClass;

$s->attach($o1, "d1");
$s->attach($o2, "d2");

$s->rewind();
while($s->valid()) {
    echo $s->key()."\n";
    $s->next();
}
?>
```

The above example will output something similar to:

    0
    1

### See Also

-   <span class="methodname">SplObjectStorage::current</span>
-   <span class="methodname">SplObjectStorage::getInfo</span>

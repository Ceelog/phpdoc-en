Judy Arrays
===========

**Table of Contents**

-   [Introduction](/intro/judy.html)
-   [Installing/Configuring](/judy/setup.html)
    -   [Requirements](/judy/setup.html#Requirements)
    -   [Installation](/judy/setup.html#Installation)
    -   [Runtime
        Configuration](/judy/setup.html#Runtime%20Configuration)
    -   [Resource Types](/judy/setup.html#Resource%20Types)
-   [Judy](/class/judy.html) — The Judy class
    -   [Judy::byCount](/class/judy.html#Judy::byCount) — Locate the Nth
        index present in the Judy array
    -   [Judy::\_\_construct](/class/judy.html#Judy::__construct) —
        Construct a new Judy object
    -   [Judy::count](/class/judy.html#Judy::count) — Count the number
        of elements in the Judy array
    -   [Judy::\_\_destruct](/class/judy.html#Judy::__destruct) —
        Destruct a Judy object
    -   [Judy::first](/class/judy.html#Judy::first) — Search for the
        first index in the Judy array
    -   [Judy::firstEmpty](/class/judy.html#Judy::firstEmpty) — Search
        for the first absent index in the Judy array
    -   [Judy::free](/class/judy.html#Judy::free) — Free the entire Judy
        array
    -   [Judy::getType](/class/judy.html#Judy::getType) — Return the
        type of the current Judy array
    -   [Judy::last](/class/judy.html#Judy::last) — Search for the last
        index in the Judy array
    -   [Judy::lastEmpty](/class/judy.html#Judy::lastEmpty) — Search for
        the last absent index in the Judy array
    -   [Judy::memoryUsage](/class/judy.html#Judy::memoryUsage) — Return
        the memory used by the Judy array
    -   [Judy::next](/class/judy.html#Judy::next) — Search for the next
        index in the Judy array
    -   [Judy::nextEmpty](/class/judy.html#Judy::nextEmpty) — Search for
        the next absent index in the Judy array
    -   [Judy::offsetExists](/class/judy.html#Judy::offsetExists) —
        Whether a offset exists
    -   [Judy::offsetGet](/class/judy.html#Judy::offsetGet) — Offset to
        retrieve
    -   [Judy::offsetSet](/class/judy.html#Judy::offsetSet) — Offset to
        set
    -   [Judy::offsetUnset](/class/judy.html#Judy::offsetUnset) — Offset
        to unset
    -   [Judy::prev](/class/judy.html#Judy::prev) — Search for the
        previous index in the Judy array
    -   [Judy::prevEmpty](/class/judy.html#Judy::prevEmpty) — Search for
        the previous absent index in the Judy array
    -   [Judy::size](/class/judy.html#Judy::size) — Return the size of
        the current Judy array
-   [Judy Functions](/ref/judy.html)
    -   [judy\_type](/ref/judy.html#judy_type) — Return the type of a
        Judy array
    -   [judy\_version](/ref/judy.html#judy_version) — Return or print
        the current PHP Judy version

Introduction
------------

The Judy class implements the
<a href="/class/arrayaccess.html" class="link">ArrayAccess</a> interface
and the <a href="/class/iterator.html" class="link">Iterator</a>
interface. This class, once instantiated, can be accessed like a PHP
<a href="/book/array.html" class="link">array</a>.

A PHP Judy object (or Judy Array) can be one of the following type :

-   <a href="/class/judy.html#" class="link">Judy::BITSET</a>
-   <a href="/class/judy.html#" class="link">Judy::INT_TO_INT</a>
-   <a href="/class/judy.html#" class="link">Judy::INT_TO_MIXED</a>
-   <a href="/class/judy.html#" class="link">Judy::STRING_TO_INT</a>
-   <a href="/class/judy.html#" class="link">Judy::STRING_TO_MIXED</a>

**Example \#1 Judy array example**

``` php
<?php
    $judy = new Judy(Judy::INT_TO_MIXED);
    $judy[1] = "one";
    $judy[2] = array('a', 'b', 'c');
    $judy[3] = new Judy(Judy::BITSET);
?>
```

Class synopsis
--------------

**Judy**

<span class="ooclass"> class **Judy** </span> <span
class="oointerface">implements <span
class="interfacename">ArrayAccess</span> </span> <span
class="oointerface">, <span class="interfacename">Iterator</span>
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`Judy::BITSET` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`Judy::INT_TO_INT` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`Judy::INT_TO_MIXED` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`Judy::STRING_TO_INT` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`Judy::STRING_TO_MIXED` <span class="initializer"> = 5</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">byCount</span> ( <span class="methodparam"><span
class="type">int</span> `$nth_index`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$judy_type`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> (\[ <span class="methodparam"><span
class="type">int</span> `$index_start`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$index_end`<span class="initializer"> =
-1</span></span> \]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">first</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$index`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">firstEmpty</span> (\[ <span class="methodparam"><span
class="type">mixed</span> `$index`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">free</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">last</span> (\[ <span class="methodparam"><span
class="type">string</span> `$index`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">lastEmpty</span> (\[ <span class="methodparam"><span
class="type">int</span> `$index`<span class="initializer"> =
-1</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">memoryUsage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">next</span> ( <span class="methodparam"><span
class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">nextEmpty</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">prev</span> ( <span class="methodparam"><span
class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">prevEmpty</span> ( <span class="methodparam"><span
class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">size</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`Judy::BITSET`**  
Define the Judy Array as a Bitset with keys as Integer and Values as a
Boolean

**`Judy::INT_TO_INT`**  
Define the Judy Array with key/values as Integer, and Integer only.

**`Judy::INT_TO_MIXED`**  
Define the Judy Array with keys as Integer and Values of any type.

**`Judy::STRING_TO_INT`**  
Define the Judy Array with keys as a String and Values as Integer, and
Integer only.

**`Judy::STRING_TO_MIXED`**  
Define the Judy Array with keys as a String and Values of any type.

Judy::byCount
=============

Locate the Nth index present in the <span class="classname">Judy</span>
array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::byCount</span> ( <span
class="methodparam"><span class="type">int</span> `$nth_index`</span> )

Locate the Nth index present in the <span class="classname">Judy</span>
array.

### Parameters

`nth_index`  
Nth index to return. If nth\_index equal 1, then it will return the
first index in the array.

### Return Values

Return the index at the given Nth position.

Judy::\_\_construct
===================

Construct a new <span class="classname">Judy</span> object

### Description

<span class="modifier">public</span> <span
class="methodname">Judy::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$judy_type`</span> )

Construct a new Judy object. A Judy object can be accessed like a PHP
Array.

### Parameters

`judy_type`  
The Judy <a href="/class/judy.html#" class="link">type</a> to be used.

### Return Values

Return the new Judy instance.

Judy::count
===========

Count the number of elements in the <span class="classname">Judy</span>
array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::count</span> (\[ <span
class="methodparam"><span class="type">int</span> `$index_start`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$index_end`<span
class="initializer"> = -1</span></span> \]\] )

Count the number of elements in the <span class="classname">Judy</span>
array.

### Parameters

`index_start`  
Start counting from the given index. Default is first index.

`index_end`  
Stop counting when reaching this index. Default is last index.

### Return Values

Return the number of elements.

Judy::\_\_destruct
==================

Destruct a Judy object

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Judy::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Destruct a Judy object.

### Parameters

This function has no parameters.

### Return Values

Judy::first
===========

Search for the first index in the <span class="classname">Judy</span>
array

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Judy::first</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$index`</span> \] )

Search (inclusive) for the first index present that is equal to or
greater than the passed Index.

### Parameters

`index`  
The index can be an integer or a string corresponding to the index where
to start the search.

### Return Values

Return the corresponding index in the array.

Judy::firstEmpty
================

Search for the first absent index in the <span
class="classname">Judy</span> array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::firstEmpty</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$index`<span
class="initializer"> = 0</span></span> \] )

Search (inclusive) for the first absent index that is equal to or
greater than the passed Index.

### Parameters

`index`  
The index can be an integer or a string corresponding to the index where
to start the search.

### Return Values

Return the corresponding index in the array.

Judy::free
==========

Free the entire <span class="classname">Judy</span> array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::free</span> ( <span
class="methodparam">void</span> )

Free the entire <span class="classname">Judy</span> array.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Judy::getType
=============

Return the type of the current <span class="classname">Judy</span> array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::getType</span> ( <span
class="methodparam">void</span> )

Return an integer corresponding to the Judy
<a href="/class/judy.html#" class="link">type</a> of the current object.

### Parameters

This function has no parameters.

### Return Values

Return an integer corresponding to a Judy
<a href="/class/judy.html#" class="link">type</a>.

Judy::last
==========

Search for the last index in the <span class="classname">Judy</span>
array

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Judy::last</span> (\[ <span
class="methodparam"><span class="type">string</span> `$index`</span> \]
)

Search (inclusive) for the last index present that is equal to or less
than the passed Index.

### Parameters

`index`  
The index can be an integer or a string corresponding to the index where
to start the search.

### Return Values

Return the corresponding index in the array.

Judy::lastEmpty
===============

Search for the last absent index in the <span
class="classname">Judy</span> array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::lastEmpty</span> (\[ <span
class="methodparam"><span class="type">int</span> `$index`<span
class="initializer"> = -1</span></span> \] )

Search (inclusive) for the last absent index that is equal to or less
than the passed Index.

### Parameters

`index`  
The index can be an integer or a string corresponding to the index where
to start the search.

### Return Values

Return the corresponding index in the array.

Judy::memoryUsage
=================

Return the memory used by the <span class="classname">Judy</span> array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::memoryUsage</span> ( <span
class="methodparam">void</span> )

Return the memory used by the <span class="classname">Judy</span> array.

### Parameters

This function has no parameters.

### Return Values

Return the memory used in bytes.

Judy::next
==========

Search for the next index in the <span class="classname">Judy</span>
array

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Judy::next</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

Search (exclusive) for the next index present that is greater than the
passed Index.

### Parameters

`index`  
The index can be an integer or a string corresponding to the index where
to start the search.

### Return Values

Return the corresponding index in the array.

Judy::nextEmpty
===============

Search for the next absent index in the <span
class="classname">Judy</span> array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::nextEmpty</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Search (exclusive) for the next absent index that is greater than the
passed Index.

### Parameters

`index`  
The index can be an integer or a string corresponding to the index where
to start the search.

### Return Values

Return the corresponding index in the array.

Judy::offsetExists
==================

Whether a offset exists

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Judy::offsetExists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> )

Whether or not an offset exists.

### Parameters

`offset`  
An offset to check for.

### Return Values

Returns **`true`** on success or **`false`** on failure.

Judy::offsetGet
===============

Offset to retrieve

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Judy::offsetGet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> )

Returns the value at specified offset.

### Parameters

`offset`  
The offset to retrieve.

### Return Values

Can return all value types.

Judy::offsetSet
===============

Offset to set

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Judy::offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

Assigns a value to the specified offset.

### Parameters

`offset`  
The offset to assign the value to.

`value`  
The value to set.

### Return Values

No value is returned.

Judy::offsetUnset
=================

Offset to unset

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Judy::offsetUnset</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> )

Unsets an offset.

### Parameters

`offset`  
The offset to unset.

### Return Values

No value is returned.

Judy::prev
==========

Search for the previous index in the <span class="classname">Judy</span>
array

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Judy::prev</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

Search (exclusive) for the previous index present that is less than the
passed Index.

### Parameters

`index`  
The index can be an integer or a string corresponding to the index where
to start the search.

### Return Values

Return the corresponding index in the array.

Judy::prevEmpty
===============

Search for the previous absent index in the <span
class="classname">Judy</span> array

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Judy::prevEmpty</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

Search (exclusive) for the previous index absent that is less than the
passed Index.

### Parameters

`index`  
The index can be an integer or a string corresponding to the index where
to start the search.

### Return Values

Return the corresponding index in the array.

Judy::size
==========

Return the size of the current <span class="classname">Judy</span> array

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Judy::size</span> ( <span
class="methodparam">void</span> )

This method is an alias of: <span class="methodname">Judy::count</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Return an integer.

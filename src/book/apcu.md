APC User Cache
==============

**Table of Contents**

-   [Introduction](/intro/apcu.html)
-   [Installing/Configuring](/apcu/setup.html)
    -   [Requirements](/apcu/setup.html#Requirements)
    -   [Installation](/apcu/setup.html#Installation)
    -   [Runtime
        Configuration](/apcu/setup.html#Runtime%20Configuration)
    -   [Resource Types](/apcu/setup.html#Resource%20Types)
-   [Predefined Constants](/apcu/constants.html)
-   [APCu Functions](/ref/apcu.html)
    -   [apcu\_add](/ref/apcu.html#apcu_add) — Cache a new variable in
        the data store
    -   [apcu\_cache\_info](/ref/apcu.html#apcu_cache_info) — Retrieves
        cached information from APCu's data store
    -   [apcu\_cas](/ref/apcu.html#apcu_cas) — Updates an old value with
        a new value
    -   [apcu\_clear\_cache](/ref/apcu.html#apcu_clear_cache) — Clears
        the APCu cache
    -   [apcu\_dec](/ref/apcu.html#apcu_dec) — Decrease a stored number
    -   [apcu\_delete](/ref/apcu.html#apcu_delete) — Removes a stored
        variable from the cache
    -   [apcu\_enabled](/ref/apcu.html#apcu_enabled) — Whether APCu is
        usable in the current environment
    -   [apcu\_entry](/ref/apcu.html#apcu_entry) — Atomically fetch or
        generate a cache entry
    -   [apcu\_exists](/ref/apcu.html#apcu_exists) — Checks if entry
        exists
    -   [apcu\_fetch](/ref/apcu.html#apcu_fetch) — Fetch a stored
        variable from the cache
    -   [apcu\_inc](/ref/apcu.html#apcu_inc) — Increase a stored number
    -   [apcu\_sma\_info](/ref/apcu.html#apcu_sma_info) — Retrieves APCu
        Shared Memory Allocation information
    -   [apcu\_store](/ref/apcu.html#apcu_store) — Cache a variable in
        the data store
-   [APCUIterator](/class/apcuiterator.html) — The APCUIterator class
    -   [APCUIterator::\_\_construct](/class/apcuiterator.html#APCUIterator::__construct)
        — Constructs an APCUIterator iterator object
    -   [APCUIterator::current](/class/apcuiterator.html#APCUIterator::current)
        — Get current item
    -   [APCUIterator::getTotalCount](/class/apcuiterator.html#APCUIterator::getTotalCount)
        — Get total count
    -   [APCUIterator::getTotalHits](/class/apcuiterator.html#APCUIterator::getTotalHits)
        — Get total cache hits
    -   [APCUIterator::getTotalSize](/class/apcuiterator.html#APCUIterator::getTotalSize)
        — Get total cache size
    -   [APCUIterator::key](/class/apcuiterator.html#APCUIterator::key)
        — Get iterator key
    -   [APCUIterator::next](/class/apcuiterator.html#APCUIterator::next)
        — Move pointer to next item
    -   [APCUIterator::rewind](/class/apcuiterator.html#APCUIterator::rewind)
        — Rewinds iterator
    -   [APCUIterator::valid](/class/apcuiterator.html#APCUIterator::valid)
        — Checks if current position is valid

Introduction
------------

The <span class="classname">APCUIterator</span> class makes it easier to
iterate over large APCu caches. This is helpful as it allows iterating
over large caches in steps, while grabbing a defined number of entries
per lock instance, so it frees the cache locks for other activities
rather than hold up the entire cache to grab 100 (the default) entries.
Also, using regular expression matching is more efficient as it's been
moved to the C level.

Class synopsis
--------------

**APCUIterator**

<span class="ooclass"> class **APCUIterator** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$search`<span
class="initializer"> = **`NULL`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$format`<span
class="initializer"> = APC\_ITER\_ALL</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$chunk_size`<span
class="initializer"> = 100</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$list`<span
class="initializer"> = APC\_LIST\_ACTIVE</span></span> \]\]\]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTotalCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">getTotalHits</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTotalSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">key</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

APCUIterator::\_\_construct
===========================

Constructs an APCUIterator iterator object

### Description

<span class="modifier">public</span> <span
class="methodname">APCUIterator::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$search`<span
class="initializer"> = **`NULL`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$format`<span
class="initializer"> = APC\_ITER\_ALL</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$chunk_size`<span
class="initializer"> = 100</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$list`<span
class="initializer"> = APC\_LIST\_ACTIVE</span></span> \]\]\]\] )

Constructs an <span class="classname">APCUIterator</span> <span
class="type">object</span>.

### Parameters

`search`  
A <a href="/book/pcre.html" class="link">PCRE</a> regular expression
that matches against APCu key names, either as a <span
class="type">string</span> for a single regular expression, or as an
<span class="type">array</span> of regular expressions. Or, optionally
pass in **`NULL`** to skip the search.

`format`  
The desired format, as configured with one or more of the
<a href="/apcu/constants.html" class="link">APC_ITER_*</a> constants.

`chunk_size`  
The chunk size. Must be a value greater than 0. The default value
is 100.

`list`  
The type to list. Either pass in **`APC_LIST_ACTIVE`** or
**`APC_LIST_DELETED`**.

### Return Values

An <span class="classname">APCUIterator</span> <span
class="type">object</span> on success, or **`NULL`** on failure.

### Examples

**Example \#1 A <span
class="function">APCUIterator::\_\_construct</span> example**

``` php
<?php
foreach (new APCUIterator('/^counter\./') as $counter) {
    echo "$counter[key]: $counter[value]\n";
    apc_dec($counter['key'], $counter['value']);
}
?>
```

### See Also

-   <span class="function">apcu\_exists</span>
-   <span class="function">apcu\_cache\_info</span>

APCUIterator::current
=====================

Get current item

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">APCUIterator::current</span> ( <span
class="methodparam">void</span> )

Gets the current item from the <span
class="classname">APCUIterator</span> stack.

### Parameters

This function has no parameters.

### Return Values

Returns the current item on success, or **`FALSE`** if no more items or
exist, or on failure.

### See Also

-   <span class="methodname">APCUIterator::next</span>
-   <span class="methodname">Iterator::current</span>

APCUIterator::getTotalCount
===========================

Get total count

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">APCUIterator::getTotalCount</span> ( <span
class="methodparam">void</span> )

Get the total count.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The total count.

### See Also

-   <span class="methodname">APCUIterator::getTotalHits</span>
-   <span class="methodname">APCUIterator::getTotalSize</span>
-   <span class="function">apcu\_cache\_info</span>

APCUIterator::getTotalHits
==========================

Get total cache hits

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">APCUIterator::getTotalHits</span> ( <span
class="methodparam">void</span> )

Gets the total number of cache hits.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The number of hits on success, or **`FALSE`** on failure.

### See Also

-   <span class="methodname">APCUIterator::getTotalCount</span>
-   <span class="methodname">APCUIterator::getTotalSize</span>
-   <span class="function">apcu\_cache\_info</span>

APCUIterator::getTotalSize
==========================

Get total cache size

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">APCUIterator::getTotalSize</span> ( <span
class="methodparam">void</span> )

Gets the total cache size.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The total cache size.

### See Also

-   <span class="methodname">APCUIterator::getTotalCount</span>
-   <span class="methodname">APCUIterator::getTotalHits</span>
-   <span class="function">apc\_cache\_info</span>

APCUIterator::key
=================

Get iterator key

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">APCUIterator::key</span> ( <span
class="methodparam">void</span> )

Gets the current iterator key.

### Parameters

This function has no parameters.

### Return Values

Returns the key on success, or **`FALSE`** upon failure.

### See Also

-   <span class="methodname">APCUIterator::current</span>
-   <span class="methodname">Iterator::key</span>

APCUIterator::next
==================

Move pointer to next item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">APCUIterator::next</span> ( <span
class="methodparam">void</span> )

Moves the iterator pointer to the next element.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">APCUIterator::current</span>
-   <span class="methodname">APCUIterator::rewind</span>
-   <span class="methodname">Iterator::next</span>

APCUIterator::rewind
====================

Rewinds iterator

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">APCUIterator::rewind</span> ( <span
class="methodparam">void</span> )

Rewinds back the iterator to the first element.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">APCUIterator::next</span>
-   <span class="methodname">Iterator::next</span>

APCUIterator::valid
===================

Checks if current position is valid

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">APCUIterator::valid</span> ( <span
class="methodparam">void</span> )

Checks if the current iterator position is valid.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the current iterator position is valid, otherwise
**`FALSE`**.

### See Also

-   <span class="methodname">APCUIterator::current</span>
-   <span class="methodname">Iterator::valid</span>

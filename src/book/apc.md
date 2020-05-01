Alternative PHP Cache
=====================

**Table of Contents**

-   [Introduction](/intro/apc.html)
-   [Installing/Configuring](/apc/setup.html)
    -   [Requirements](/apc/setup.html#Requirements)
    -   [Installation](/apc/setup.html#Installation)
    -   [Runtime Configuration](/apc/setup.html#Runtime%20Configuration)
    -   [Resource Types](/apc/setup.html#Resource%20Types)
-   [Predefined Constants](/apc/constants.html)
-   [APC Functions](/ref/apc.html)
    -   [apc\_add](/ref/apc.html#apc_add) — Cache a new variable in the
        data store
    -   [apc\_bin\_dump](/ref/apc.html#apc_bin_dump) — Get a binary dump
        of the given files and user variables
    -   [apc\_bin\_dumpfile](/ref/apc.html#apc_bin_dumpfile) — Output a
        binary dump of cached files and user variables to a file
    -   [apc\_bin\_load](/ref/apc.html#apc_bin_load) — Load a binary
        dump into the APC file/user cache
    -   [apc\_bin\_loadfile](/ref/apc.html#apc_bin_loadfile) — Load a
        binary dump from a file into the APC file/user cache
    -   [apc\_cache\_info](/ref/apc.html#apc_cache_info) — Retrieves
        cached information from APC's data store
    -   [apc\_cas](/ref/apc.html#apc_cas) — Updates an old value with a
        new value
    -   [apc\_clear\_cache](/ref/apc.html#apc_clear_cache) — Clears the
        APC cache
    -   [apc\_compile\_file](/ref/apc.html#apc_compile_file) — Stores a
        file in the bytecode cache, bypassing all filters
    -   [apc\_dec](/ref/apc.html#apc_dec) — Decrease a stored number
    -   [apc\_define\_constants](/ref/apc.html#apc_define_constants) —
        Defines a set of constants for retrieval and mass-definition
    -   [apc\_delete\_file](/ref/apc.html#apc_delete_file) — Deletes
        files from the opcode cache
    -   [apc\_delete](/ref/apc.html#apc_delete) — Removes a stored
        variable from the cache
    -   [apc\_exists](/ref/apc.html#apc_exists) — Checks if APC key
        exists
    -   [apc\_fetch](/ref/apc.html#apc_fetch) — Fetch a stored variable
        from the cache
    -   [apc\_inc](/ref/apc.html#apc_inc) — Increase a stored number
    -   [apc\_load\_constants](/ref/apc.html#apc_load_constants) — Loads
        a set of constants from the cache
    -   [apc\_sma\_info](/ref/apc.html#apc_sma_info) — Retrieves APC's
        Shared Memory Allocation information
    -   [apc\_store](/ref/apc.html#apc_store) — Cache a variable in the
        data store
-   [APCIterator](/class/apciterator.html) — The APCIterator class
    -   [APCIterator::\_\_construct](/class/apciterator.html#APCIterator::__construct)
        — Constructs an APCIterator iterator object
    -   [APCIterator::current](/class/apciterator.html#APCIterator::current)
        — Get current item
    -   [APCIterator::getTotalCount](/class/apciterator.html#APCIterator::getTotalCount)
        — Get total count
    -   [APCIterator::getTotalHits](/class/apciterator.html#APCIterator::getTotalHits)
        — Get total cache hits
    -   [APCIterator::getTotalSize](/class/apciterator.html#APCIterator::getTotalSize)
        — Get total cache size
    -   [APCIterator::key](/class/apciterator.html#APCIterator::key) —
        Get iterator key
    -   [APCIterator::next](/class/apciterator.html#APCIterator::next) —
        Move pointer to next item
    -   [APCIterator::rewind](/class/apciterator.html#APCIterator::rewind)
        — Rewinds iterator
    -   [APCIterator::valid](/class/apciterator.html#APCIterator::valid)
        — Checks if current position is valid

Introduction
------------

The <span class="classname">APCIterator</span> class makes it easier to
iterate over large APC caches. This is helpful as it allows iterating
over large caches in steps, while grabbing a defined number of entries
per lock instance, so it frees the cache locks for other activities
rather than hold up the entire cache to grab 100 (the default) entries.
Also, using regular expression matching is more efficient as it's been
moved to the C level.

Class synopsis
--------------

**APCIterator**

<span class="ooclass"> class **APCIterator** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$cache`</span> \[,
<span class="methodparam"><span class="type">mixed</span> `$search`<span
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

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTotalHits</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTotalSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

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

APCIterator::\_\_construct
==========================

Constructs an APCIterator iterator object

### Description

<span class="modifier">public</span> <span
class="methodname">APCIterator::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$cache`</span> \[,
<span class="methodparam"><span class="type">mixed</span> `$search`<span
class="initializer"> = **`NULL`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$format`<span
class="initializer"> = APC\_ITER\_ALL</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$chunk_size`<span
class="initializer"> = 100</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$list`<span
class="initializer"> = APC\_LIST\_ACTIVE</span></span> \]\]\]\] )

Constructs an <span class="classname">APCIterator</span> <span
class="type">object</span>.

### Parameters

`cache`  
The cache type, which will be *user* or *file*.

`search`  
A <a href="/book/pcre.html" class="link">PCRE</a> regular expression
that matches against APC key names, either as a <span
class="type">string</span> for a single regular expression, or as an
<span class="type">array</span> of regular expressions. Or, optionally
pass in **`NULL`** to skip the search.

`format`  
The desired format, as configured with one or more of the
<a href="/apc/constants.html" class="link">APC_ITER_*</a> constants.

`chunk_size`  
The chunk size. Must be a value greater than 0. The default value
is 100.

`list`  
The type to list. Either pass in **`APC_LIST_ACTIVE`** or
**`APC_LIST_DELETED`**.

### Return Values

An <span class="classname">APCIterator</span> <span
class="type">object</span> on success, or **`NULL`** on failure.

### Examples

**Example \#1 A <span class="function">APCIterator::\_\_construct</span>
example**

``` php
<?php
foreach (new APCIterator('user', '/^counter\./') as $counter) {
    echo "$counter[key]: $counter[value]\n";
    apc_dec($counter['key'], $counter['value']);
}
?>
```

### See Also

-   <span class="function">apc\_exists</span>
-   <span class="function">apc\_cache\_info</span>

APCIterator::current
====================

Get current item

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">APCIterator::current</span> ( <span
class="methodparam">void</span> )

Gets the current item from the <span
class="classname">APCIterator</span> stack.

### Parameters

This function has no parameters.

### Return Values

Returns the current item on success, or **`FALSE`** if no more items or
exist, or on failure.

### See Also

-   <span class="methodname">APCIterator::next</span>
-   <span class="methodname">Iterator::current</span>

APCIterator::getTotalCount
==========================

Get total count

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">APCIterator::getTotalCount</span> ( <span
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

-   <span class="methodname">APCIterator::getTotalHits</span>
-   <span class="methodname">APCIterator::getTotalSize</span>
-   <span class="function">apc\_cache\_info</span>

APCIterator::getTotalHits
=========================

Get total cache hits

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">APCIterator::getTotalHits</span> ( <span
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

-   <span class="methodname">APCIterator::getTotalCount</span>
-   <span class="methodname">APCIterator::getTotalSize</span>
-   <span class="function">apc\_cache\_info</span>

APCIterator::getTotalSize
=========================

Get total cache size

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">APCIterator::getTotalSize</span> ( <span
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

-   <span class="methodname">APCIterator::getTotalCount</span>
-   <span class="methodname">APCIterator::getTotalHits</span>
-   <span class="function">apc\_cache\_info</span>

APCIterator::key
================

Get iterator key

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">APCIterator::key</span> ( <span
class="methodparam">void</span> )

Gets the current iterator key.

### Parameters

This function has no parameters.

### Return Values

Returns the key on success, or **`FALSE`** upon failure.

### See Also

-   <span class="methodname">APCIterator::current</span>
-   <span class="methodname">Iterator::key</span>

APCIterator::next
=================

Move pointer to next item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">APCIterator::next</span> ( <span
class="methodparam">void</span> )

Moves the iterator pointer to the next element.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">APCIterator::current</span>
-   <span class="methodname">APCIterator::rewind</span>
-   <span class="methodname">Iterator::next</span>

APCIterator::rewind
===================

Rewinds iterator

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">APCIterator::rewind</span> ( <span
class="methodparam">void</span> )

Rewinds back the iterator to the first element.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">APCIterator::next</span>
-   <span class="methodname">Iterator::next</span>

APCIterator::valid
==================

Checks if current position is valid

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">APCIterator::valid</span> ( <span
class="methodparam">void</span> )

Checks if the current iterator position is valid.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the current iterator position is valid, otherwise
**`FALSE`**.

### See Also

-   <span class="methodname">APCIterator::current</span>
-   <span class="methodname">Iterator::valid</span>

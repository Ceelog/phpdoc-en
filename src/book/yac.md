Yac
===

**Table of Contents**

-   [Introduction](/intro/yac.html)
-   [Installing/Configuring](/yac/setup.html)
    -   [Requirements](/yac/setup.html#Requirements)
    -   [Installation](/yac/setup.html#Installation)
    -   [Runtime Configuration](/yac/setup.html#Runtime%20Configuration)
    -   [Resource Types](/yac/setup.html#Resource%20Types)
-   [Predefined Constants](/yac/constants.html)
-   [Yac](/class/yac.html) — The Yac class
    -   [Yac::add](/class/yac.html#Yac::add) — Store into cache
    -   [Yac::\_\_construct](/class/yac.html#Yac::__construct) —
        Constructor
    -   [Yac::delete](/class/yac.html#Yac::delete) — Remove items from
        cache
    -   [Yac::dump](/class/yac.html#Yac::dump) — Dump cache
    -   [Yac::flush](/class/yac.html#Yac::flush) — Flush the cache
    -   [Yac::get](/class/yac.html#Yac::get) — Retrieve values from
        cache
    -   [Yac::\_\_get](/class/yac.html#Yac::__get) — Getter
    -   [Yac::info](/class/yac.html#Yac::info) — Status of cache
    -   [Yac::set](/class/yac.html#Yac::set) — Store into cache
    -   [Yac::\_\_set](/class/yac.html#Yac::__set) — Setter

Introduction
------------

Class synopsis
--------------

**Yac**

<span class="ooclass"> class **Yac** </span> {

/\* Properties \*/

<span class="modifier">protected</span> `$_prefix` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$prefix`<span
class="initializer"> = ""</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">string</span> `$keys`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">array</span> `$key_vals`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">delete</span> ( <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">array</span></span> `$keys`</span> \[, <span
class="methodparam"><span class="type">int</span> `$ttl`</span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">dump</span> ( <span class="methodparam"><span
class="type">int</span> `$$num`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">flush</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">get</span> ( <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">array</span></span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `&$cas`<span
class="initializer"> = **`NULL`**</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">info</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">set</span> ( <span class="methodparam"><span
class="type">string</span> `$keys`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">array</span> `$key_vals`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$keys`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

}

Properties
----------

`_prefix`  

Yac::add
========

Store into cache

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yac::add</span> ( <span
class="methodparam"><span class="type">string</span> `$keys`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$ttl`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yac::add</span> ( <span
class="methodparam"><span class="type">array</span> `$key_vals`</span> )

Added a item into cache.

### Parameters

`keys`  
<span class="type">string</span> key

`value`  
mixed value, All php value type could be stored except
<a href="/language/types/resource.html" class="link">resource</a>

`ttl`  
expire time

### Return Values

<span class="type">bool</span>, **`TRUE`** on success, **`FALSE`** on
failure

> **Note**:
>
> <span class="methodname">Yac::add</span> may fail if cas lock could
> not obtain, so, if you need the value to be stored properly, you may
> write codes like:
>
> **Example \#1 Make sure the item is stored**
>
> ``` php
> while(!$yac->set("key", "vale));
> ```

Yac::\_\_construct
==================

Constructor

### Description

<span class="modifier">public</span> <span
class="methodname">Yac::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$prefix`<span
class="initializer"> = ""</span></span> \] )

prefix is used to prepended to keys, this could be used to avoiding
conflicts between apps.

### Parameters

`prefix`  
<span class="type">string</span> prefix

Yac::delete
===========

Remove items from cache

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yac::delete</span> ( <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">array</span></span>
`$keys`</span> \[, <span class="methodparam"><span
class="type">int</span> `$ttl`</span> \] )

remove items from cache

### Parameters

`keys`  
string key, or array of multiple keys to be removed

`ttl`  
if delay is set, delete will mark the items to be invalid in ttl second.

### Return Values

Yac::dump
=========

Dump cache

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yac::dump</span> ( <span
class="methodparam"><span class="type">int</span> `$$num`</span> )

Dump values stored in cache

### Parameters

`num`  
Maximum number of items should be returned

### Return Values

mixed

Yac::flush
==========

Flush the cache

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yac::flush</span> ( <span
class="methodparam">void</span> )

Remove all cached values

### Parameters

This function has no parameters.

### Return Values

bool, always true

Yac::get
========

Retrieve values from cache

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yac::get</span> ( <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">array</span></span>
`$key`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$cas`<span class="initializer"> =
**`NULL`**</span></span> \] )

Retrieve values from cache

### Parameters

`key`  
<span class="type">string</span> keys, or <span
class="type">array</span> of multiple keys.

`cas`  
if not **`NULL`**, it will be set to the retrieved item's cas.

### Return Values

mixed on success, false on failure

Yac::\_\_get
============

Getter

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yac::\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

Retrieve values from cache

### Parameters

`key`  
<span class="type">string</span> key

### Return Values

mixed on success, **`NULL`** on failure

Yac::info
=========

Status of cache

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Yac::info</span> ( <span
class="methodparam">void</span> )

Get status of cache system

### Parameters

This function has no parameters.

### Return Values

Return an array, consistent with: "memory\_size", "slots\_memory\_size",
"values\_memory\_size", "segment\_size", "segment\_num", "miss", "hits",
"fails", "kicks", "recycles", "slots\_size", "slots\_used"

Yac::set
========

Store into cache

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yac::set</span> ( <span
class="methodparam"><span class="type">string</span> `$keys`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$ttl`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Yac::add</span> ( <span
class="methodparam"><span class="type">array</span> `$key_vals`</span> )

Add a item into cache, it the key is already exists, override it.

### Parameters

`keys`  
<span class="type">string</span> key

`value`  
mixed value, All php value type could be stored except
<a href="/language/types/resource.html" class="link">resource</a>

`ttl`  
expire time

### Return Values

the value self

Yac::\_\_set
============

Setter

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Yac::\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$keys`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

store a item into cache

### Parameters

`keys`  
<span class="type">string</span> key

`value`  
mixed value, All php value type could be stored except
<a href="/language/types/resource.html" class="link">resource</a>

### Return Values

Always return the value self

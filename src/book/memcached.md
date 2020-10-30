Memcached
=========

**Table of Contents**

-   [Introduction](/intro/memcached.html)
-   [Installing/Configuring](/memcached/setup.html)
    -   [Requirements](/memcached/setup.html#Requirements)
    -   [Installation](/memcached/setup.html#Installation)
    -   [Runtime
        Configuration](/memcached/setup.html#Runtime%20Configuration)
    -   [Resource Types](/memcached/setup.html#Resource%20Types)
-   [Predefined Constants](/memcached/constants.html)
-   [Expiration Times](/memcached/expiration.html)
-   [Callbacks](/memcached/callbacks.html)
    -   [Result callbacks](/memcached/callbacks.html#Result%20callbacks)
    -   [Read-through cache
        callbacks](/memcached/callbacks.html#Read-through%20cache%20callbacks)
-   [Sessions support](/memcached/sessions.html)
-   [Memcached](/class/memcached.html) — The Memcached class
    -   [Memcached::add](/class/memcached.html#Memcached::add) — Add an
        item under a new key
    -   [Memcached::addByKey](/class/memcached.html#Memcached::addByKey)
        — Add an item under a new key on a specific server
    -   [Memcached::addServer](/class/memcached.html#Memcached::addServer)
        — Add a server to the server pool
    -   [Memcached::addServers](/class/memcached.html#Memcached::addServers)
        — Add multiple servers to the server pool
    -   [Memcached::append](/class/memcached.html#Memcached::append) —
        Append data to an existing item
    -   [Memcached::appendByKey](/class/memcached.html#Memcached::appendByKey)
        — Append data to an existing item on a specific server
    -   [Memcached::cas](/class/memcached.html#Memcached::cas) — Compare
        and swap an item
    -   [Memcached::casByKey](/class/memcached.html#Memcached::casByKey)
        — Compare and swap an item on a specific server
    -   [Memcached::\_\_construct](/class/memcached.html#Memcached::__construct)
        — Create a Memcached instance
    -   [Memcached::decrement](/class/memcached.html#Memcached::decrement)
        — Decrement numeric item's value
    -   [Memcached::decrementByKey](/class/memcached.html#Memcached::decrementByKey)
        — Decrement numeric item's value, stored on a specific server
    -   [Memcached::delete](/class/memcached.html#Memcached::delete) —
        Delete an item
    -   [Memcached::deleteByKey](/class/memcached.html#Memcached::deleteByKey)
        — Delete an item from a specific server
    -   [Memcached::deleteMulti](/class/memcached.html#Memcached::deleteMulti)
        — Delete multiple items
    -   [Memcached::deleteMultiByKey](/class/memcached.html#Memcached::deleteMultiByKey)
        — Delete multiple items from a specific server
    -   [Memcached::fetch](/class/memcached.html#Memcached::fetch) —
        Fetch the next result
    -   [Memcached::fetchAll](/class/memcached.html#Memcached::fetchAll)
        — Fetch all the remaining results
    -   [Memcached::flush](/class/memcached.html#Memcached::flush) —
        Invalidate all items in the cache
    -   [Memcached::get](/class/memcached.html#Memcached::get) —
        Retrieve an item
    -   [Memcached::getAllKeys](/class/memcached.html#Memcached::getAllKeys)
        — Gets the keys stored on all the servers
    -   [Memcached::getByKey](/class/memcached.html#Memcached::getByKey)
        — Retrieve an item from a specific server
    -   [Memcached::getDelayed](/class/memcached.html#Memcached::getDelayed)
        — Request multiple items
    -   [Memcached::getDelayedByKey](/class/memcached.html#Memcached::getDelayedByKey)
        — Request multiple items from a specific server
    -   [Memcached::getMulti](/class/memcached.html#Memcached::getMulti)
        — Retrieve multiple items
    -   [Memcached::getMultiByKey](/class/memcached.html#Memcached::getMultiByKey)
        — Retrieve multiple items from a specific server
    -   [Memcached::getOption](/class/memcached.html#Memcached::getOption)
        — Retrieve a Memcached option value
    -   [Memcached::getResultCode](/class/memcached.html#Memcached::getResultCode)
        — Return the result code of the last operation
    -   [Memcached::getResultMessage](/class/memcached.html#Memcached::getResultMessage)
        — Return the message describing the result of the last operation
    -   [Memcached::getServerByKey](/class/memcached.html#Memcached::getServerByKey)
        — Map a key to a server
    -   [Memcached::getServerList](/class/memcached.html#Memcached::getServerList)
        — Get the list of the servers in the pool
    -   [Memcached::getStats](/class/memcached.html#Memcached::getStats)
        — Get server pool statistics
    -   [Memcached::getVersion](/class/memcached.html#Memcached::getVersion)
        — Get server pool version info
    -   [Memcached::increment](/class/memcached.html#Memcached::increment)
        — Increment numeric item's value
    -   [Memcached::incrementByKey](/class/memcached.html#Memcached::incrementByKey)
        — Increment numeric item's value, stored on a specific server
    -   [Memcached::isPersistent](/class/memcached.html#Memcached::isPersistent)
        — Check if a persitent connection to memcache is being used
    -   [Memcached::isPristine](/class/memcached.html#Memcached::isPristine)
        — Check if the instance was recently created
    -   [Memcached::prepend](/class/memcached.html#Memcached::prepend) —
        Prepend data to an existing item
    -   [Memcached::prependByKey](/class/memcached.html#Memcached::prependByKey)
        — Prepend data to an existing item on a specific server
    -   [Memcached::quit](/class/memcached.html#Memcached::quit) — Close
        any open connections
    -   [Memcached::replace](/class/memcached.html#Memcached::replace) —
        Replace the item under an existing key
    -   [Memcached::replaceByKey](/class/memcached.html#Memcached::replaceByKey)
        — Replace the item under an existing key on a specific server
    -   [Memcached::resetServerList](/class/memcached.html#Memcached::resetServerList)
        — Clears all servers from the server list
    -   [Memcached::set](/class/memcached.html#Memcached::set) — Store
        an item
    -   [Memcached::setByKey](/class/memcached.html#Memcached::setByKey)
        — Store an item on a specific server
    -   [Memcached::setMulti](/class/memcached.html#Memcached::setMulti)
        — Store multiple items
    -   [Memcached::setMultiByKey](/class/memcached.html#Memcached::setMultiByKey)
        — Store multiple items on a specific server
    -   [Memcached::setOption](/class/memcached.html#Memcached::setOption)
        — Set a Memcached option
    -   [Memcached::setOptions](/class/memcached.html#Memcached::setOptions)
        — Set Memcached options
    -   [Memcached::setSaslAuthData](/class/memcached.html#Memcached::setSaslAuthData)
        — Set the credentials to use for authentication
    -   [Memcached::touch](/class/memcached.html#Memcached::touch) — Set
        a new expiration on an item
    -   [Memcached::touchByKey](/class/memcached.html#Memcached::touchByKey)
        — Set a new expiration on an item on a specific server
-   [MemcachedException](/class/memcachedexception.html) — The
    MemcachedException class

Introduction
------------

Represents a connection to a set of memcached servers.

Class synopsis
--------------

**Memcached**

<span class="ooclass"> class **Memcached** </span> {

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$persistent_id`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addServer</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$weight`<span class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addServers</span> ( <span
class="methodparam"><span class="type">array</span> `$servers`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">append</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">appendByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">cas</span> ( <span class="methodparam"><span
class="type">float</span> `$cas_token`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">casByKey</span> ( <span
class="methodparam"><span class="type">float</span> `$cas_token`</span>
, <span class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">decrement</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$initial_value`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$expiry`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">decrementByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$initial_value`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$expiry`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">delete</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$time`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deleteByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$time`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">deleteMulti</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">int</span> `$time`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deleteMultiByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">array</span> `$keys`</span> \[, <span
class="methodparam"><span class="type">int</span> `$time`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">fetch</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">fetchAll</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">flush</span> (\[ <span
class="methodparam"><span class="type">int</span> `$delay`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">get</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$cache_cb`</span> \[, <span class="methodparam"><span
class="type">int</span> `$$flags`</span> \]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getAllKeys</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$cache_cb`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getDelayed</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$with_cas`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$value_cb`</span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getDelayedByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">array</span> `$keys`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$with_cas`</span>
\[, <span class="methodparam"><span class="type">callable</span>
`$value_cb`</span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getMulti</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getMultiByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">array</span> `$keys`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getOption</span> ( <span
class="methodparam"><span class="type">int</span> `$option`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getResultCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getResultMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getServerByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getServerList</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">getStats</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getVersion</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">increment</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$initial_value`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$expiry`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">incrementByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$initial_value`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$expiry`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPersistent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPristine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">prepend</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">prependByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">quit</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">replace</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">replaceByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">resetServerList</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">set</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setMulti</span> ( <span
class="methodparam"><span class="type">array</span> `$items`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setMultiByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">array</span> `$items`</span> \[, <span
class="methodparam"><span class="type">int</span> `$expiration`</span>
\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setOption</span> ( <span
class="methodparam"><span class="type">int</span> `$option`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setOptions</span> ( <span
class="methodparam"><span class="type">array</span> `$options`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setSaslAuthData</span> ( <span
class="methodparam"><span class="type">string</span> `$username`</span>
, <span class="methodparam"><span class="type">string</span>
`$password`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">touch</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">int</span> `$expiration`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">touchByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">int</span> `$expiration`</span> )

}

Memcached::add
==============

Add an item under a new key

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::add</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$expiration`</span> \] )

<span class="function">Memcached::add</span> is similar to <span
class="methodname">Memcached::set</span>, but the operation fails if the
`key` already exists on the server.

### Parameters

`key`  
The key under which to store the value.

`value`  
The value to store.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTSTORED`** if the key already exists.

### See Also

-   <span class="methodname">Memcached::addByKey</span>
-   <span class="methodname">Memcached::set</span>
-   <span class="methodname">Memcached::replace</span>

Memcached::addByKey
===================

Add an item under a new key on a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::addByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="function">Memcached::addByKey</span> is functionally
equivalent to <span class="methodname">Memcached::add</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server. This is useful if you need to keep a bunch of related
keys on a certain server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key under which to store the value.

`value`  
The value to store.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTSTORED`** if the key already exists.

### See Also

-   <span class="methodname">Memcached::add</span>
-   <span class="methodname">Memcached::set</span>
-   <span class="methodname">Memcached::replace</span>

Memcached::addServer
====================

Add a server to the server pool

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::addServer</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$weight`<span class="initializer"> = 0</span></span> \] )

<span class="function">Memcached::addServer</span> adds the specified
server to the server pool. No connection is established to the server at
this time, but if you are using consistent key distribution option (via
**`Memcached::DISTRIBUTION_CONSISTENT`** or
**`Memcached::OPT_LIBKETAMA_COMPATIBLE`**), some of the internal data
structures will have to be updated. Thus, if you need to add multiple
servers, it is better to use <span
class="methodname">Memcached::addServers</span> as the update then
happens only once.

The same server may appear multiple times in the server pool, because no
duplication checks are made. This is not advisable; instead, use the
`weight` option to increase the selection weighting of this server.

### Parameters

`host`  
The hostname of the memcache server. If the hostname is invalid,
data-related operations will set
**`Memcached::RES_HOST_LOOKUP_FAILURE`** result code. As of version
2.0.0b1, this parameter may also specify the path of a unix socket
filepath ex. */path/to/memcached.sock* to use UNIX domain sockets, in
this case `port` must also be set to *0*.

`port`  
The port on which memcache is running. Usually, this is *11211*. As of
version 2.0.0b1, set this parameter to *0* when using UNIX domain
sockets.

`weight`  
The weight of the server relative to the total weight of all the servers
in the pool. This controls the probability of the server being selected
for operations. This is used only with consistent distribution option
and usually corresponds to the amount of memory available to memcache on
that server.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">Memcached::addServer</span>
example**

``` php
<?php
$m = new Memcached();

/* Add 2 servers, so that the second one
   is twice as likely to be selected. */
$m->addServer('mem1.domain.com', 11211, 33);
$m->addServer('mem2.domain.com', 11211, 67);
?>
```

### See Also

-   <span class="methodname">Memcached::addServers</span>
-   <span class="methodname">Memcached::resetServerList</span>

Memcached::addServers
=====================

Add multiple servers to the server pool

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::addServers</span> ( <span
class="methodparam"><span class="type">array</span> `$servers`</span> )

<span class="function">Memcached::addServers</span> adds `servers` to
the server pool. Each entry in `servers` is supposed to be an array
containing hostname, port, and, optionally, weight of the server. No
connection is established to the servers at this time.

The same server may appear multiple times in the server pool, because no
duplication checks are made. This is not advisable; instead, use the
`weight` option to increase the selection weighting of this server.

### Parameters

`array`  
Array of the servers to add to the pool.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">Memcached::addServers</span>
example**

``` php
<?php
$m = new Memcached();

$servers = array(
    array('mem1.domain.com', 11211, 33),
    array('mem2.domain.com', 11211, 67)
);
$m->addServers($servers);
?>
```

### See Also

-   <span class="methodname">Memcached::addServer</span>
-   <span class="methodname">Memcached::resetServerList</span>

Memcached::append
=================

Append data to an existing item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::append</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="function">Memcached::append</span> appends the given
`value` string to the value of an existing item. The reason that `value`
is forced to be a string is that appending mixed types is not
well-defined.

> **Note**:
>
> If the **`Memcached::OPT_COMPRESSION`** is enabled, the operation will
> fail and a warning will be issued, because appending compressed data
> to a value that is potentially already compressed is not possible.

### Parameters

`key`  
The key under which to store the value.

`value`  
The string to append.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTSTORED`** if the key does not exist.

### Examples

**Example \#1 <span class="function">Memcached::append</span> example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);
$m->setOption(Memcached::OPT_COMPRESSION, false);

$m->set('foo', 'abc');
$m->append('foo', 'def');
var_dump($m->get('foo'));
?>
```

The above example will output:

    string(6) "abcdef"

### See Also

-   <span class="methodname">Memcached::appendByKey</span>
-   <span class="methodname">Memcached::prepend</span>

Memcached::appendByKey
======================

Append data to an existing item on a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::appendByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="function">Memcached::appendByKey</span> is functionally
equivalent to <span class="methodname">Memcached::append</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key under which to store the value.

`value`  
The string to append.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTSTORED`** if the key does not exist.

### See Also

-   <span class="methodname">Memcached::append</span>
-   <span class="methodname">Memcached::prepend</span>

Memcached::cas
==============

Compare and swap an item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::cas</span> ( <span
class="methodparam"><span class="type">float</span> `$cas_token`</span>
, <span class="methodparam"><span class="type">string</span>
`$key`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> \[, <span
class="methodparam"><span class="type">int</span> `$expiration`</span>
\] )

<span class="function">Memcached::cas</span> performs a "check and set"
operation, so that the item will be stored only if no other client has
updated it since it was last fetched by this client. The check is done
via the `cas_token` parameter which is a unique 64-bit value assigned to
the existing item by memcache. See the documentation for <span
class="methodname">Memcached::get\*</span> methods for how to obtain
this token. Note that the token is represented as a double due to the
limitations of PHP's integer space.

### Parameters

`cas_token`  
Unique value associated with the existing item. Generated by memcache.

`key`  
The key under which to store the value.

`value`  
The value to store.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_DATA_EXISTS`** if the item you are trying to store has
been modified since you last fetched it.

### Examples

**Example \#1 <span class="function">Memcached::cas</span> example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

do {
    /* fetch IP list and its token */
    $ips = $m->get('ip_block', null, $cas);
    /* if list doesn't exist yet, create it and do
       an atomic add which will fail if someone else already added it */
    if ($m->getResultCode() == Memcached::RES_NOTFOUND) {
        $ips = array($_SERVER['REMOTE_ADDR']);
        $m->add('ip_block', $ips);
    /* otherwise, add IP to the list and store via compare-and-swap
       with the token, which will fail if someone else updated the list */
    } else { 
        $ips[] = $_SERVER['REMOTE_ADDR'];
        $m->cas($cas, 'ip_block', $ips);
    }   
} while ($m->getResultCode() != Memcached::RES_SUCCESS);

?>
```

### See Also

-   <span class="methodname">Memcached::casByKey</span>

Memcached::casByKey
===================

Compare and swap an item on a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::casByKey</span> ( <span
class="methodparam"><span class="type">float</span> `$cas_token`</span>
, <span class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="function">Memcached::casByKey</span> is functionally
equivalent to <span class="methodname">Memcached::cas</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server. This is useful if you need to keep a bunch of related
keys on a certain server.

### Parameters

`cas_token`  
Unique value associated with the existing item. Generated by memcache.

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key under which to store the value.

`value`  
The value to store.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_DATA_EXISTS`** if the item you are trying to store has
been modified since you last fetched it.

### See Also

-   <span class="methodname">Memcached::cas</span>

Memcached::\_\_construct
========================

Create a Memcached instance

### Description

<span class="modifier">public</span> <span
class="methodname">Memcached::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$persistent_id`</span> \] )

Creates a Memcached instance representing the connection to the memcache
servers.

### Parameters

`persistent_id`  
By default the Memcached instances are destroyed at the end of the
request. To create an instance that persists between requests, use
`persistent_id` to specify a unique ID for the instance. All instances
created with the same `persistent_id` will share the same connection.

### Return Values

A Memcached object.

### Examples

**Example \#1 Creating a Memcached object**

``` php
<?php
/* Create a regular instance */
$m = new Memcached();
echo get_class($m);

/* Create a persistent instance */
$m2 = new Memcached('story_pool');
$m3 = new Memcached('story_pool');

/* now $m2 and $m3 share the same connection */
?>
```

Memcached::decrement
====================

Decrement numeric item's value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Memcached::decrement</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$initial_value`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$expiry`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="function">Memcached::decrement</span> decrements a numeric
item's value by the specified `offset`. If the item's value is not
numeric, an error will result. If the operation would decrease the value
below 0, the new value will be 0. <span
class="function">Memcached::decrement</span> will set the item to the
`initial_value` parameter if the key doesn't exist.

### Parameters

`key`  
The key of the item to decrement.

`offset`  
The amount by which to decrement the item's value.

`initial_value`  
The value to set the item to if it doesn't currently exist.

`expiry`  
The expiry time to set on the item.

### Return Values

Returns item's new value on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">Memcached::decrement</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->set('counter', 5);
$n = $m->decrement('counter');
var_dump($n);

$n = $m->decrement('counter', 10);
var_dump($n);

var_dump($m->get('counter'));

$m->set('counter', 'abc');
$n = $m->increment('counter');
// ^ will fail due to item value not being numeric
var_dump($n);
?>
```

The above example will output:

    int(4)
    int(0)
    int(0)
    bool(false)

### See Also

-   <span class="methodname">Memcached::increment</span>
-   <span class="methodname">Memcached::incrementByKey</span>
-   <span class="methodname">Memcached::decrementByKey</span>

Memcached::decrementByKey
=========================

Decrement numeric item's value, stored on a specific server

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Memcached::decrementByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$initial_value`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$expiry`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="function">Memcached::decrementByKey</span> decrements a
numeric item's value by the specified `offset`. If the item's value is
not numeric, an error will result. If the operation would decrease the
value below 0, the new value will be 0. <span
class="function">Memcached::decrementByKey</span> will set the item to
the `initial_value` parameter if the key doesn't exist.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key of the item to decrement.

`offset`  
The amount by which to decrement the item's value.

`initial_value`  
The value to set the item to if it doesn't currently exist.

`expiry`  
The expiry time to set on the item.

### Return Values

Returns item's new value on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">Memcached::decrement</span>
-   <span class="methodname">Memcached::increment</span>
-   <span class="methodname">Memcached::incrementByKey</span>

Memcached::delete
=================

Delete an item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::delete</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">int</span> `$time`<span
class="initializer"> = 0</span></span> \] )

<span class="function">Memcached::delete</span> deletes the `key` from
the server. The `time` parameter is the amount of time in seconds (or
Unix time until which) the client wishes the server to refuse *add* and
*replace* commands for this key. For this amount of time, the item is
put into a delete queue, which means that it won't possible to retrieve
it by the *get* command, but *add* and *replace* command with this key
will also fail (the *set* command will succeed, however). After the time
passes, the item is finally deleted from server memory. The parameter
`time` defaults to 0 (which means that the item will be deleted
immediately and further storage commands with this key will succeed).

### Parameters

`key`  
The key to be deleted.

`time`  
The amount of time the server will wait to delete the item.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTFOUND`** if the key does not exist.

### Examples

**Example \#1 <span class="function">Memcached::delete</span> example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->delete('key1');
?>
```

### See Also

-   <span class="methodname">Memcached::deleteByKey</span>
-   <span class="methodname">Memcached::deleteMulti</span>

Memcached::deleteByKey
======================

Delete an item from a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::deleteByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$time`<span
class="initializer"> = 0</span></span> \] )

<span class="function">Memcached::deleteByKey</span> is functionally
equivalent to <span class="methodname">Memcached::delete</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key to be deleted.

`time`  
The amount of time the server will wait to delete the item.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTFOUND`** if the key does not exist.

### See Also

-   <span class="methodname">Memcached::delete</span>
-   <span class="methodname">Memcached::deleteMulti</span>
-   <span class="methodname">Memcached::deleteMultiByKey</span>

Memcached::deleteMulti
======================

Delete multiple items

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Memcached::deleteMulti</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">int</span> `$time`<span
class="initializer"> = 0</span></span> \] )

<span class="function">Memcached::deleteMulti</span> deletes the array
of `keys` from the server. The `time` parameter is the amount of time in
seconds (or Unix time until which) the client wishes the server to
refuse *add* and *replace* commands for these keys. For this amount of
time, the item is put into a delete queue, which means that it won't be
possible to retrieve it by the *get* command, but *add* and *replace*
command with these keys will also fail (the *set* command will succeed,
however). After the time passes, the item is finally deleted from server
memory. The parameter `time` defaults to 0 (which means that the item
will be deleted immediately and further storage commands with these keys
will succeed).

### Parameters

`keys`  
The keys to be deleted.

`time`  
The amount of time the server will wait to delete the items.

### Return Values

Returns array indexed by `keys` and where values are indicating whether
operation succeeded or not. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTFOUND`** if the key does not exist.

### See Also

-   <span class="methodname">Memcached::delete</span>
-   <span class="methodname">Memcached::deleteByKey</span>
-   <span class="methodname">Memcached::deleteMultiByKey</span>

Memcached::deleteMultiByKey
===========================

Delete multiple items from a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::deleteMultiByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">array</span> `$keys`</span> \[, <span
class="methodparam"><span class="type">int</span> `$time`<span
class="initializer"> = 0</span></span> \] )

<span class="function">Memcached::deleteMultiByKey</span> is
functionally equivalent to <span
class="methodname">Memcached::deleteMulti</span>, except that the
free-form `server_key` can be used to map the `keys` to a specific
server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`keys`  
The keys to be deleted.

`time`  
The amount of time the server will wait to delete the items.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTFOUND`** if the key does not exist.

### See Also

-   <span class="methodname">Memcached::delete</span>
-   <span class="methodname">Memcached::deleteByKey</span>
-   <span class="methodname">Memcached::deleteMulti</span>

Memcached::fetch
================

Fetch the next result

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Memcached::fetch</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::fetch</span> retrieves the next result
from the last request.

### Parameters

This function has no parameters.

### Return Values

Returns the next result or **`FALSE`** otherwise. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_END`** if result set is exhausted.

### Examples

**Example \#1 <span class="function">Memcached::fetch</span> example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->set('int', 99);
$m->set('string', 'a simple string');
$m->set('array', array(11, 12));

$m->getDelayed(array('int', 'array'), true);
while ($result = $m->fetch()) {
    var_dump($result);
}
?>
```

The above example will output something similar to:

    array(3) {
      ["key"]=>
      string(3) "int"
      "value"]=>
      int(99)
      ["cas"]=>
      float(2363)
    }
    array(3) {
      ["key"]=>
      string(5) "array"
      ["value"]=>
      array(2) {
        [0]=>
        int(11)
        [1]=>
        int(12)
      }
      ["cas"]=>
      float(2365)
    }

### See Also

-   <span class="methodname">Memcached::fetchAll</span>
-   <span class="methodname">Memcached::getDelayed</span>

Memcached::fetchAll
===================

Fetch all the remaining results

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Memcached::fetchAll</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::fetchAll</span> retrieves all the
remaining results from the last request.

### Parameters

This function has no parameters.

### Return Values

Returns the results or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Examples

**Example \#1 <span class="function">Memcached::getDelayed</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->set('int', 99);
$m->set('string', 'a simple string');
$m->set('array', array(11, 12));

$m->getDelayed(array('int', 'array'), true);
var_dump($m->fetchAll());
?>
```

The above example will output:

    array(2) {
      [0]=>
      array(3) {
        ["key"]=>
        string(3) "int"
        ["value"]=>
        int(99)
        ["cas"]=>
        float(2363)
      }
      [1]=>
      array(3) {
        ["key"]=>
        string(5) "array"
        ["value"]=>
        array(2) {
          [0]=>
          int(11)
          [1]=>
          int(12)
        }
        ["cas"]=>
        float(2365)
      }
    }

### See Also

-   <span class="methodname">Memcached::fetch</span>
-   <span class="methodname">Memcached::getDelayed</span>

Memcached::flush
================

Invalidate all items in the cache

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::flush</span> (\[ <span
class="methodparam"><span class="type">int</span> `$delay`<span
class="initializer"> = 0</span></span> \] )

<span class="function">Memcached::flush</span> invalidates all existing
cache items immediately (by default) or after the `delay` specified.
After invalidation none of the items will be returned in response to a
retrieval command (unless it's stored again under the same key after
<span class="function">Memcached::flush</span> has invalidated the
items). The flush does not actually free all the memory taken up by the
existing items; that will happen gradually as new items are stored.

### Parameters

`delay`  
Number of seconds to wait before invalidating the items.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Examples

**Example \#1 <span class="function">Memcached::flush</span> example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

/* flush all items in 10 seconds */
$m->flush(10);
?>
```

Memcached::get
==============

Retrieve an item

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Memcached::get</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$cache_cb`</span> \[, <span class="methodparam"><span
class="type">int</span> `$$flags`</span> \]\] )

<span class="function">Memcached::get</span> returns the item that was
previously stored under the `key`. If the item is found and the `flags`
is given **`Memcached::GET_EXTENDED`**, it will also return the CAS
token value for the item. See <span
class="methodname">Memcached::cas</span> for how to use CAS tokens.
<a href="/memcached/callbacks.html" class="link">Read-through caching callback</a>
may be specified via `cache_cb` parameter.

### Parameters

`key`  
The key of the item to retrieve.

`cache_cb`  
Read-through caching callback or **`NULL`**.

`flags`  
Flags to control the returned result. When **`Memcached::GET_EXTENDED`**
is given, the function will also return the CAS token.

### Return Values

Returns the value stored in the cache or **`FALSE`** otherwise. If the
`flags` is set to **`Memcached::GET_EXTENDED`**, an array containing the
value and the CAS token is returned instead of only the value. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTFOUND`** if the key does not exist.

### Examples

**Example \#1 <span class="function">Memcached::get</span> example \#1**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->set('foo', 100);
var_dump($m->get('foo'));
?>
```

The above example will output:

    int(100)

**Example \#2 <span class="function">Memcached::get</span> example \#2**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

if (!($ip = $m->get('ip_block'))) {
    if ($m->getResultCode() == Memcached::RES_NOTFOUND) {
        $ip = array();
        $m->set('ip_block', $ip);
    } else {
        /* log error */
        /* ...       */
    }
}
?>
```

### Changelog

| Version              | Description                                                                                                                                                                   |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL memcached 3.0.0 | The `&cas_token` parameter was removed. Instead `flags` was added and when it is given the value of **`Memcached::GET_EXTENDED`** it will ensure the CAS token to be fetched. |

### See Also

-   <span class="methodname">Memcached::getByKey</span>
-   <span class="methodname">Memcached::getMulti</span>
-   <span class="methodname">Memcached::getDelayed</span>

Memcached::getAllKeys
=====================

Gets the keys stored on all the servers

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Memcached::getAllKeys</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::getAllKeys</span> queries each
memcache server and retrieves an array of all keys stored on them at
that point in time. This is not an atomic operation, so it isn't a truly
consistent snapshot of the keys at point in time. As memcache doesn't
guarantee to return all keys you also cannot assume that all keys have
been returned.

### Parameters

This function has no parameters.

### Return Values

Returns the keys stored on all the servers on success or **`FALSE`** on
failure.

Memcached::getByKey
===================

Retrieve an item from a specific server

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Memcached::getByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$cache_cb`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \]\] )

<span class="function">Memcached::getByKey</span> is functionally
equivalent to <span class="methodname">Memcached::get</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key of the item to fetch.

`cache_cb`  
Read-through caching callback or **`NULL`**

`flags`  
Flags to control the returned result. When value of
**`Memcached::GET_EXTENDED`** is given will return the CAS token.

### Return Values

Returns the value stored in the cache or **`FALSE`** otherwise. The
<span class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTFOUND`** if the key does not exist.

### Changelog

| Version              | Description                                                                                                                                                                   |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL memcached 3.0.0 | The `&cas_token` parameter was removed. Instead `flags` was added and when it is given the value of **`Memcached::GET_EXTENDED`** it will ensure the CAS token to be fetched. |

### See Also

-   <span class="methodname">Memcached::get</span>
-   <span class="methodname">Memcached::getMulti</span>
-   <span class="methodname">Memcached::getDelayed</span>

Memcached::getDelayed
=====================

Request multiple items

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::getDelayed</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$with_cas`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$value_cb`</span> \]\] )

<span class="function">Memcached::getDelayed</span> issues a request to
memcache for multiple items the keys of which are specified in the
`keys` array. The method does not wait for response and returns right
away. When you are ready to collect the items, call either <span
class="methodname">Memcached::fetch</span> or <span
class="methodname">Memcached::fetchAll</span>. If `with_cas` is true,
the CAS token values will also be requested.

Instead of fetching the results explicitly, you can specify a
<a href="/memcached/callbacks.html" class="link">result callback</a> via
`value_cb` parameter.

### Parameters

`keys`  
Array of keys to request.

`with_cas`  
Whether to request CAS token values also.

`value_cb`  
The result callback or **`NULL`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Examples

**Example \#1 <span class="function">Memcached::getDelayed</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->set('int', 99);
$m->set('string', 'a simple string');
$m->set('array', array(11, 12));

$m->getDelayed(array('int', 'array'), true);
var_dump($m->fetchAll());
?>
```

The above example will output:

    array(2) {
      [0]=>
      array(3) {
        ["key"]=>
        string(3) "int"
        ["value"]=>
        int(99)
        ["cas"]=>
        float(2363)
      }
      [1]=>
      array(3) {
        ["key"]=>
        string(5) "array"
        ["value"]=>
        array(2) {
          [0]=>
          int(11)
          [1]=>
          int(12)
        }
        ["cas"]=>
        float(2365)
      }
    }

### See Also

-   <span class="methodname">Memcached::getDelayedByKey</span>
-   <span class="methodname">Memcached::fetch</span>
-   <span class="methodname">Memcached::fetchAll</span>

Memcached::getDelayedByKey
==========================

Request multiple items from a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::getDelayedByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">array</span> `$keys`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$with_cas`</span>
\[, <span class="methodparam"><span class="type">callable</span>
`$value_cb`</span> \]\] )

<span class="function">Memcached::getDelayedByKey</span> is functionally
equivalent to <span class="methodname">Memcached::getDelayed</span>,
except that the free-form `server_key` can be used to map the `keys` to
a specific server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`keys`  
Array of keys to request.

`with_cas`  
Whether to request CAS token values also.

`value_cb`  
The result callback or **`NULL`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### See Also

-   <span class="methodname">Memcached::getDelayed</span>
-   <span class="methodname">Memcached::fetch</span>
-   <span class="methodname">Memcached::fetchAll</span>

Memcached::getMulti
===================

Retrieve multiple items

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Memcached::getMulti</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

<span class="function">Memcached::getMulti</span> is similar to <span
class="methodname">Memcached::get</span>, but instead of a single key
item, it retrieves multiple items the keys of which are specified in the
`keys` array.

> **Note**:
>
> Before v3.0 a second argument `&cas_tokens` was in use. It was filled
> with the CAS token values for the found items. The `&cas_tokens`
> parameter was removed in v3.0 of the extension. It was replaced with a
> new flag **`Memcached::GET_EXTENDED`** that needs is to be used as the
> value for `flags`.

The `flags` parameter can be used to specify additional options for
<span class="function">Memcached::getMulti</span>.
**`Memcached::GET_PRESERVE_ORDER`** ensures that the keys are returned
in the same order as they were requested in.
**`Memcached::GET_EXTENDED`** ensures that the CAS tokens will be
fetched too.

### Parameters

`keys`  
Array of keys to retrieve.

`flags`  
The flags for the get operation.

### Return Values

Returns the array of found items or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Examples

**Example \#1 <span class="function">Memcached::getMulti</span> example
for Memcached v3**

``` php
<?php
// Valid for v3 of the extension

$m = new Memcached();
$m->addServer('localhost', 11211);

$items = array(
    'key1' => 'value1',
    'key2' => 'value2',
    'key3' => 'value3'
);
$m->setMulti($items);
$result = $m->getMulti(array('key1', 'key3', 'badkey'));
var_dump($result);
?>
```

The above example will output something similar to:

    array(2) {
      ["key1"]=>
      string(6) "value1"
      ["key3"]=>
      string(6) "value3"
    }

**Example \#2 <span class="function">Memcached::getMulti</span> example
for Memcached v1 and v2**

``` php
<?php
// Valid for v1 and v2 of the extension

$m = new Memcached();
$m->addServer('localhost', 11211);

$items = array(
    'key1' => 'value1',
    'key2' => 'value2',
    'key3' => 'value3'
);
$m->setMulti($items);
$result = $m->getMulti(array('key1', 'key3', 'badkey'), $cas);
var_dump($result, $cas);
?>
```

The above example will output something similar to:

    array(2) {
      ["key1"]=>
      string(6) "value1"
      ["key3"]=>
      string(6) "value3"
    }
    array(2) {
      ["key1"]=>
      float(2360)
      ["key3"]=>
      float(2362)
    }

**Example \#3 **`Memcached::GET_PRESERVE_ORDER`** example for Memcached
v3**

``` php
<?php
// Valid for v3 of the extension

$m = new Memcached();
$m->addServer('localhost', 11211);

$data = array(
    'foo' => 'foo-data',
    'bar' => 'bar-data',
    'baz' => 'baz-data',
    'lol' => 'lol-data',
    'kek' => 'kek-data',
);

$m->setMulti($data, 3600);

$keys = array_keys($data);
$keys[] = 'zoo';
$got = $m->getMulti($keys, Memcached::GET_PRESERVE_ORDER);

foreach ($got as $k => $v) {
    echo "$k $v\n";
}
?>
```

The above example will output something similar to:

    foo foo-data
    bar bar-data
    baz baz-data
    lol lol-data
    kek kek-data
    zoo 

**Example \#4 **`Memcached::GET_PRESERVE_ORDER`** example for Memcached
v1 and v2**

``` php
<?php
// Valid for v1 and v2 of the extension

$m = new Memcached();
$m->addServer('localhost', 11211);

$data = array(
    'foo' => 'foo-data',
    'bar' => 'bar-data',
    'baz' => 'baz-data',
    'lol' => 'lol-data',
    'kek' => 'kek-data',
);

$m->setMulti($data, 3600);

$null = null;
$keys = array_keys($data);
$keys[] = 'zoo';
$got = $m->getMulti($keys, $null, Memcached::GET_PRESERVE_ORDER);

foreach ($got as $k => $v) {
    echo "$k $v\n";
}
?>
```

The above example will output something similar to:

    foo foo-data
    bar bar-data
    baz baz-data
    lol lol-data
    kek kek-data
    zoo 

### Changelog

| Version              | Description                                                                                                                                             |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL memcached 3.0.0 | The `&cas_tokens` parameter was removed. The **`Memcached::GET_EXTENDED`** was added and when passed as a flag it ensures the CAS tokens to be fetched. |

### See Also

-   <span class="methodname">Memcached::getMultiByKey</span>
-   <span class="methodname">Memcached::get</span>
-   <span class="methodname">Memcached::getDelayed</span>

Memcached::getMultiByKey
========================

Retrieve multiple items from a specific server

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Memcached::getMultiByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">array</span> `$keys`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

<span class="function">Memcached::getMultiByKey</span> is functionally
equivalent to <span class="methodname">Memcached::getMulti</span>,
except that the free-form `server_key` can be used to map the `keys` to
a specific server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`keys`  
Array of keys to retrieve.

`flags`  
The flags for the get operation.

### Return Values

Returns the array of found items or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Changelog

| Version              | Description                                                                                                                                             |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL memcached 3.0.0 | The `&cas_tokens` parameter was removed. The **`Memcached::GET_EXTENDED`** was added and when passed as a flag it ensures the CAS tokens to be fetched. |

### See Also

-   <span class="methodname">Memcached::getMulti</span>
-   <span class="methodname">Memcached::get</span>
-   <span class="methodname">Memcached::getDelayed</span>

Memcached::getOption
====================

Retrieve a Memcached option value

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Memcached::getOption</span> ( <span
class="methodparam"><span class="type">int</span> `$option`</span> )

This method returns the value of a Memcached `option`. Some options
correspond to the ones defined by libmemcached, and some are specific to
the extension. See
<a href="/memcached/constants.html" class="link">Memcached Constants</a>
for more information.

### Parameters

`option`  
One of the *Memcached::OPT\_\** constants.

### Return Values

Returns the value of the requested option, or **`FALSE`** on error.

### Examples

**Example \#1 Retrieving Memcached options**

``` php
<?php
$m = new Memcached();
var_dump($m->getOption(Memcached::OPT_COMPRESSION));
var_dump($m->getOption(Memcached::OPT_POLL_TIMEOUT));
?>
```

The above example will output something similar to:

    bool(true)
    int(1000)

### See Also

-   <span class="methodname">Memcached::getOption</span>
-   <span class="methodname">Memcached::setOption</span>
-   <a href="/memcached/constants.html" class="link">Memcached Constants</a>

Memcached::getResultCode
========================

Return the result code of the last operation

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Memcached::getResultCode</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::getResultCode</span> returns one of
the **`Memcached::RES_*`** constants that is the result of the last
executed Memcached method.

### Parameters

This function has no parameters.

### Return Values

Result code of the last Memcached operation.

### Examples

**Example \#1 <span class="function">Memcached::getResultCode</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->add('foo', 'bar');
if ($m->getResultCode() == Memcached::RES_NOTSTORED) {
    /* ... */
}
?>
```

Memcached::getResultMessage
===========================

Return the message describing the result of the last operation

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Memcached::getResultMessage</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::getResultMessage</span> returns a
string that describes the result code of the last executed Memcached
method.

### Parameters

This function has no parameters.

### Return Values

Message describing the result of the last Memcached operation.

### Examples

**Example \#1 <span class="function">Memcached::getResultMessage</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->add('foo', 'bar'); // first time should succeed
$m->add('foo', 'bar');
echo $m->getResultMessage(),"\n";
?>
```

The above example will output:

    NOT STORED

Memcached::getServerByKey
=========================

Map a key to a server

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Memcached::getServerByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> )

<span class="function">Memcached::getServerByKey</span> returns the
server that would be selected by a particular `server_key` in all the
<span class="function">Memcached::\*ByKey</span> operations.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

### Return Values

Returns an array containing three keys of *host*, *port*, and *weight*
on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Examples

**Example \#1 <span class="function">Memcached::getServerByKey</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServers(array(
    array('mem1.domain.com', 11211, 40),
    array('mem2.domain.com', 11211, 40),
    array('mem3.domain.com', 11211, 20),
));

$m->setOption(Memcached::OPT_LIBKETAMA_COMPATIBLE, true);

var_dump($m->getServerByKey('user'));
var_dump($m->getServerByKey('log'));
var_dump($m->getServerByKey('ip'));
?>
```

The above example will output something similar to:

    array(3) {
      ["host"]=>
      string(15) "mem3.domain.com"
      ["port"]=>
      int(11211)
      ["weight"]=>
      int(20)
    }
    array(3) {
      ["host"]=>
      string(15) "mem2.domain.com"
      ["port"]=>
      int(11211)
      ["weight"]=>
      int(40)
    }
    array(3) {
      ["host"]=>
      string(15) "mem2.domain.com"
      ["port"]=>
      int(11211)
      ["weight"]=>
      int(40)
    }

Memcached::getServerList
========================

Get the list of the servers in the pool

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Memcached::getServerList</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::getServerList</span> returns the list
of all servers that are in its server pool.

### Parameters

This function has no parameters.

### Return Values

The list of all servers in the server pool.

### Examples

**Example \#1 <span class="function">Memcached::getServerList</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServers(array(
    array('mem1.domain.com', 11211, 20),
    array('mem2.domain.com', 11311, 80),
));
var_dump($m->getServerList());
?>
```

The above example will output:

    array(2) {
      [0]=>
      array(3) {
        ["host"]=>
        string(15) "mem1.domain.com"
        ["port"]=>
        int(11211)
        ["weight"]=>
        int(20)
      }
      [1]=>
      array(3) {
        ["host"]=>
        string(15) "mem2.domain.com"
        ["port"]=>
        int(11311)
        ["weight"]=>
        int(80)
      }
    }

Memcached::getStats
===================

Get server pool statistics

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">Memcached::getStats</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::getStats</span> returns an array
containing the state of all available memcache servers. See
<a href="http://code.sixapart.com/svn/memcached/trunk/server/doc/protocol.txt" class="link external">» memcache protocol</a>
specification for details on these statistics.

### Parameters

This function has no parameters.

### Return Values

Array of server statistics, one entry per server, or **`FALSE`** on
failure.

### Examples

**Example \#1 <span class="function">Memcached::getStats</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

print_r($m->getStats());
?>
```

The above example will output something similar to:

    Array
    (
        [localhost:11211] => Array
            (
                [pid] => 4933
                [uptime] => 786123
                [threads] => 1
                [time] => 1233868010
                [pointer_size] => 32
                [rusage_user_seconds] => 0
                [rusage_user_microseconds] => 140000
                [rusage_system_seconds] => 23
                [rusage_system_microseconds] => 210000
                [curr_items] => 145
                [total_items] => 2374
                [limit_maxbytes] => 67108864
                [curr_connections] => 2
                [total_connections] => 151
                [connection_structures] => 3
                [bytes] => 20345
                [cmd_get] => 213343
                [cmd_set] => 2381
                [get_hits] => 204223
                [get_misses] => 9120
                [evictions] => 0
                [bytes_read] => 9092476
                [bytes_written] => 15420512
                [version] => 1.2.6
            )

    )

Memcached::getVersion
=====================

Get server pool version info

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Memcached::getVersion</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::getVersion</span> returns an array
containing the version info for all available memcache servers.

### Parameters

This function has no parameters.

### Return Values

Array of server versions, one entry per server.

### Examples

**Example \#1 <span class="function">Memcached::getVersion</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

print_r($m->getVersion());
?>
```

The above example will output something similar to:

    Array
    (
        [localhost:11211] => 1.2.6
    )

Memcached::increment
====================

Increment numeric item's value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Memcached::increment</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$initial_value`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$expiry`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="function">Memcached::increment</span> increments a numeric
item's value by the specified `offset`. If the item's value is not
numeric, an error will result. <span
class="function">Memcached::increment</span> will set the item to the
`initial_value` parameter if the key doesn't exist.

### Parameters

`key`  
The key of the item to increment.

`offset`  
The amount by which to increment the item's value.

`initial_value`  
The value to set the item to if it doesn't currently exist.

`expiry`  
The expiry time to set on the item.

### Return Values

Returns new item's value on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">Memcached::increment</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->set('counter', 0);
$m->increment('counter');
$n = $m->increment('counter', 10);
var_dump($n);

$m->set('counter', 'abc');
$n = $m->increment('counter');
// ^ will fail due to item value not being numeric
var_dump($n);
?>
```

The above example will output:

    int(11)
    bool(false)

### See Also

-   <span class="methodname">Memcached::decrement</span>
-   <span class="methodname">Memcached::decrementByKey</span>
-   <span class="methodname">Memcached::incrementByKey</span>

Memcached::incrementByKey
=========================

Increment numeric item's value, stored on a specific server

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Memcached::incrementByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$initial_value`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$expiry`<span
class="initializer"> = 0</span></span> \]\]\] )

<span class="function">Memcached::incrementByKey</span> increments a
numeric item's value by the specified `offset`. If the item's value is
not numeric, an error will result. <span
class="function">Memcached::incrementByKey</span> will set the item to
the `initial_value` parameter if the key doesn't exist.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key of the item to increment.

`offset`  
The amount by which to increment the item's value.

`initial_value`  
The value to set the item to if it doesn't currently exist.

`expiry`  
The expiry time to set on the item.

### Return Values

Returns new item's value on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">Memcached::decrement</span>
-   <span class="methodname">Memcached::decrementByKey</span>
-   <span class="methodname">Memcached::increment</span>

Memcached::isPersistent
=======================

Check if a persitent connection to memcache is being used

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::isPersistent</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::isPersistent</span> checks if the
connections to the memcache servers are persistent connections.

### Parameters

This function has no parameters.

### Return Values

Returns true if Memcache instance uses a persistent connection, false
otherwise.

### See Also

-   <span class="methodname">Memcached::isPristine</span>

Memcached::isPristine
=====================

Check if the instance was recently created

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::isPristine</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::isPristine</span> checks if the
Memcache instance was recently created.

### Parameters

This function has no parameters.

### Return Values

Returns the true if instance is recently created, false otherwise.

### See Also

-   <span class="methodname">Memcached::isPersistent</span>

Memcached::prepend
==================

Prepend data to an existing item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::prepend</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="function">Memcached::prepend</span> prepends the given
`value` string to the value of an existing item. The reason that `value`
is forced to be a string is that prepending mixed types is not
well-defined.

> **Note**:
>
> If the **`Memcached::OPT_COMPRESSION`** is enabled, the operation will
> fail and a warning will be issued, because prepending compressed data
> to a value that is potentially already compressed is not possible.

### Parameters

`key`  
The key of the item to prepend the data to.

`value`  
The string to prepend.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTSTORED`** if the key does not exist.

### Examples

**Example \#1 <span class="function">Memcached::prepend</span> example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);
$m->setOption(Memcached::OPT_COMPRESSION, false);

$m->set('foo', 'abc');
$m->prepend('foo', 'def');
var_dump($m->get('foo'));
?>
```

The above example will output:

    string(6) "defabc"

### See Also

-   <span class="methodname">Memcached::prependByKey</span>
-   <span class="methodname">Memcached::append</span>

Memcached::prependByKey
=======================

Prepend data to an existing item on a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::prependByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="function">Memcached::prependByKey</span> is functionally
equivalent to <span class="methodname">Memcached::prepend</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key of the item to prepend the data to.

`value`  
The string to prepend.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTSTORED`** if the key does not exist.

### See Also

-   <span class="methodname">Memcached::prepend</span>
-   <span class="methodname">Memcached::append</span>

Memcached::quit
===============

Close any open connections

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::quit</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::quit</span> closes any open
connections to the memcache servers.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

Memcached::replace
==================

Replace the item under an existing key

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::replace</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$expiration`</span> \] )

<span class="function">Memcached::replace</span> is similar to <span
class="methodname">Memcached::set</span>, but the operation fails if the
`key` does not exist on the server.

### Parameters

`key`  
The key under which to store the value.

`value`  
The value to store.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTSTORED`** if the key does not exist.

### See Also

-   <span class="methodname">Memcached::replaceByKey</span>
-   <span class="methodname">Memcached::set</span>
-   <span class="methodname">Memcached::add</span>

Memcached::replaceByKey
=======================

Replace the item under an existing key on a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::replaceByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="function">Memcached::replaceByKey</span> is functionally
equivalent to <span class="methodname">Memcached::replace</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server. This is useful if you need to keep a bunch of related
keys on a certain server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key under which to store the value.

`value`  
The value to store.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The <span
class="methodname">Memcached::getResultCode</span> will return
**`Memcached::RES_NOTSTORED`** if the key does not exist.

### See Also

-   <span class="methodname">Memcached::replace</span>
-   <span class="methodname">Memcached::set</span>
-   <span class="methodname">Memcached::add</span>

Memcached::resetServerList
==========================

Clears all servers from the server list

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::resetServerList</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcached::resetserverlist</span> removes all
memcache servers from the known server list, resetting it back to empty.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">Memcached::addServer</span>
-   <span class="methodname">Memcached::addServers</span>

Memcached::set
==============

Store an item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::set</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$expiration`</span> \] )

<span class="function">Memcached::set</span> stores the `value` on a
memcache server under the specified `key`. The `expiration` parameter
can be used to control when the value is considered expired.

The value can be any valid PHP type except for resources, because those
cannot be represented in a serialized form. If the
**`Memcached::OPT_COMPRESSION`** option is turned on, the serialized
value will also be compressed before storage.

### Parameters

`key`  
The key under which to store the value.

`value`  
The value to store.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Examples

**Example \#1 <span class="function">Memcached::set</span> example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$m->set('int', 99);
$m->set('string', 'a simple string');
$m->set('array', array(11, 12));
/* expire 'object' key in 5 minutes */
$m->set('object', new stdclass, time() + 300);


var_dump($m->get('int'));
var_dump($m->get('string'));
var_dump($m->get('array'));
var_dump($m->get('object'));
?>
```

The above example will output something similar to:

    int(99)
    string(15) "a simple string"
    array(2) {
      [0]=>
      int(11)
      [1]=>
      int(12)
    }
    object(stdClass)#1 (0) {
    }

### See Also

-   <span class="methodname">Memcached::setByKey</span>
-   <span class="methodname">Memcached::add</span>
-   <span class="methodname">Memcached::replace</span>

Memcached::setByKey
===================

Store an item on a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::setByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="function">Memcached::setByKey</span> is functionally
equivalent to <span class="methodname">Memcached::set</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server. This is useful if you need to keep a bunch of related
keys on a certain server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key under which to store the value.

`value`  
The value to store.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Examples

**Example \#1 <span class="function">Memcached::setByKey</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

/* keep IP blocks on a certain server */
$m->setByKey('api-cache', 'block-ip:169.254.253.252', 1);
$m->setByKey('api-cache', 'block-ip:169.127.127.202', 1);
?>
```

### See Also

-   <span class="methodname">Memcached::set</span>

Memcached::setMulti
===================

Store multiple items

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::setMulti</span> ( <span
class="methodparam"><span class="type">array</span> `$items`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> \] )

<span class="function">Memcached::setMulti</span> is similar to <span
class="methodname">Memcached::set</span>, but instead of a single
key/value item, it works on multiple items specified in `items`. The
`expiration` time applies to all the items at once.

### Parameters

`items`  
An array of key/value pairs to store on the server.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### Examples

**Example \#1 <span class="function">Memcached::setMulti</span>
example**

``` php
<?php
$m = new Memcached();
$m->addServer('localhost', 11211);

$items = array(
    'key1' => 'value1',
    'key2' => 'value2',
    'key3' => 'value3'
);
$m->setMulti($items, time() + 300);
?>
```

### See Also

-   <span class="methodname">Memcached::setMultiByKey</span>
-   <span class="methodname">Memcached::set</span>

Memcached::setMultiByKey
========================

Store multiple items on a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::setMultiByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">array</span> `$items`</span> \[, <span
class="methodparam"><span class="type">int</span> `$expiration`</span>
\] )

<span class="function">Memcached::setMultiByKey</span> is functionally
equivalent to <span class="methodname">Memcached::setMulti</span>,
except that the free-form `server_key` can be used to map the keys from
`items` to a specific server. This is useful if you need to keep a bunch
of related keys on a certain server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`items`  
An array of key/value pairs to store on the server.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### See Also

-   <span class="methodname">Memcached::setMulti</span>
-   <span class="methodname">Memcached::set</span>

Memcached::setOption
====================

Set a Memcached option

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::setOption</span> ( <span
class="methodparam"><span class="type">int</span> `$option`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

This method sets the value of a Memcached `option`. Some options
correspond to the ones defined by libmemcached, and some are specific to
the extension. See
<a href="/memcached/constants.html" class="link">Memcached Constants</a>
for more information.

The options listed below require values specified via constants.

-   *Memcached::OPT\_HASH* requires *Memcached::HASH\_\** values.

-   *Memcached::OPT\_DISTRIBUTION* requires
    *Memcached::DISTRIBUTION\_\** values.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Setting a Memcached option**

``` php
<?php
$m = new Memcached();
var_dump($m->getOption(Memcached::OPT_HASH) == Memcached::HASH_DEFAULT);
$m->setOption(Memcached::OPT_HASH, Memcached::HASH_MURMUR);
$m->setOption(Memcached::OPT_PREFIX_KEY, "widgets");
echo "Prefix key is now: ", $m->getOption(Memcached::OPT_PREFIX_KEY), "\n";
?>
```

The above example will output:

    bool(true)
    Prefix key is now: widgets

### See Also

-   <span class="methodname">Memcached::getOption</span>
-   <span class="methodname">Memcached::setOptions</span>
-   <a href="/memcached/constants.html" class="link">Memcached Constants</a>

Memcached::setOptions
=====================

Set Memcached options

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::setOptions</span> ( <span
class="methodparam"><span class="type">array</span> `$options`</span> )

<span class="function">Memcached::setOptions</span> is a variation of
the <span class="methodname">Memcached::setOption</span> that takes an
array of options to be set.

### Parameters

`options`  
An associative array of options where the key is the option to set and
the value is the new value for the option.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Setting Memcached options**

``` php
<?php
$m = new Memcached();
var_dump($m->getOption(Memcached::OPT_HASH) == Memcached::HASH_DEFAULT);

$m->setOptions(array(Memcached::OPT_HASH => Memcached::HASH_MURMUR, Memcached::OPT_PREFIX_KEY => "widgets"));

var_dump($m->getOption(Memcached::OPT_HASH) == Memcached::HASH_DEFAULT);
echo "Prefix key is now: ", $m->getOption(Memcached::OPT_PREFIX_KEY), "\n";
?>
```

The above example will output:

    bool(true)
    bool(false)
    Prefix key is now: widgets

### See Also

-   <span class="methodname">Memcached::getOption</span>
-   <span class="methodname">Memcached::setOption</span>
-   <a href="/memcached/constants.html" class="link">Memcached Constants</a>

Memcached::setSaslAuthData
==========================

Set the credentials to use for authentication

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Memcached::setSaslAuthData</span> ( <span
class="methodparam"><span class="type">string</span> `$username`</span>
, <span class="methodparam"><span class="type">string</span>
`$password`</span> )

<span class="function">Memcached::setSaslAuthData</span> sets the
username and password that should be used for SASL authentication with
the memcache servers.

*This method is only available when the memcached extension is built
with SASL support.* Please refer to
<a href="/memcached/setup.html" class="link">Memcached setup</a> for how
to do this.

### Parameters

`username`  
The username to use for authentication.

`password`  
The password to use for authentication.

### Return Values

No value is returned.

Memcached::touch
================

Set a new expiration on an item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::touch</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">int</span>
`$expiration`</span> )

<span class="function">Memcached::touch</span> sets a new expiration
value on the given key.

### Parameters

`key`  
The key under which to store the value.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### See Also

-   <span class="methodname">Memcached::touchByKey</span>

Memcached::touchByKey
=====================

Set a new expiration on an item on a specific server

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Memcached::touchByKey</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_key`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">int</span> `$expiration`</span> )

<span class="function">Memcached::touchByKey</span> is functionally
equivalent to <span class="methodname">Memcached::touch</span>, except
that the free-form `server_key` can be used to map the `key` to a
specific server.

### Parameters

`server_key`  
The key identifying the server to store the value on or retrieve it
from. Instead of hashing on the actual key for the item, we hash on the
server key when deciding which memcached server to talk to. This allows
related items to be grouped together on a single server for efficiency
with multi operations.

`key`  
The key under which to store the value.

`expiration`  
The expiration time, defaults to 0. See
<a href="/memcached/expiration.html" class="link">Expiration Times</a>
for more info.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Use <span
class="methodname">Memcached::getResultCode</span> if necessary.

### See Also

-   <span class="methodname">Memcached::touch</span>

Introduction
------------

Class synopsis
--------------

**MemcachedException**

<span class="ooclass"> class **MemcachedException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**RuntimeException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Memcache
========

**Table of Contents**

-   [Introduction](/intro/memcache.html)
-   [Installing/Configuring](/memcache/setup.html)
    -   [Requirements](/memcache/setup.html#Requirements)
    -   [Installation](/memcache/setup.html#Installation)
    -   [Runtime
        Configuration](/memcache/setup.html#Runtime%20Configuration)
    -   [Resource Types](/memcache/setup.html#Resource%20Types)
-   [Predefined Constants](/memcache/constants.html)
-   [Examples](/memcache/examples.html)
    -   [Basic usage](/memcache/examples.html#Basic%20usage)
-   [Memcache](/class/memcache.html) — The Memcache class
    -   [Memcache::add](/class/memcache.html#Memcache::add) — Add an
        item to the server
    -   [Memcache::addServer](/class/memcache.html#Memcache::addServer)
        — Add a memcached server to connection pool
    -   [Memcache::close](/class/memcache.html#Memcache::close) — Close
        memcached server connection
    -   [Memcache::connect](/class/memcache.html#Memcache::connect) —
        Open memcached server connection
    -   [Memcache::decrement](/class/memcache.html#Memcache::decrement)
        — Decrement item's value
    -   [Memcache::delete](/class/memcache.html#Memcache::delete) —
        Delete item from the server
    -   [Memcache::flush](/class/memcache.html#Memcache::flush) — Flush
        all existing items at the server
    -   [Memcache::get](/class/memcache.html#Memcache::get) — Retrieve
        item from the server
    -   [Memcache::getExtendedStats](/class/memcache.html#Memcache::getExtendedStats)
        — Get statistics from all servers in pool
    -   [Memcache::getServerStatus](/class/memcache.html#Memcache::getServerStatus)
        — Returns server status
    -   [Memcache::getStats](/class/memcache.html#Memcache::getStats) —
        Get statistics of the server
    -   [Memcache::getVersion](/class/memcache.html#Memcache::getVersion)
        — Return version of the server
    -   [Memcache::increment](/class/memcache.html#Memcache::increment)
        — Increment item's value
    -   [Memcache::pconnect](/class/memcache.html#Memcache::pconnect) —
        Open memcached server persistent connection
    -   [Memcache::replace](/class/memcache.html#Memcache::replace) —
        Replace value of the existing item
    -   [Memcache::set](/class/memcache.html#Memcache::set) — Store data
        at the server
    -   [Memcache::setCompressThreshold](/class/memcache.html#Memcache::setCompressThreshold)
        — Enable automatic compression of large values
    -   [Memcache::setServerParams](/class/memcache.html#Memcache::setServerParams)
        — Changes server parameters and status at runtime
-   [Memcache Functions](/ref/memcache.html)
    -   [memcache\_debug](/ref/memcache.html#memcache_debug) — Turn
        debug output on/off

Introduction
------------

Represents a connection to a set of memcache servers.

Class synopsis
--------------

**Memcache**

<span class="ooclass"> class **Memcache** </span> {

<span class="type">bool</span> <span class="methodname">add</span> (
<span class="methodparam"><span class="type">string</span> `$key`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$var`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flag`</span> \[, <span
class="methodparam"><span class="type">int</span> `$expire`</span> \]\]
)

<span class="type">bool</span> <span class="methodname">addServer</span>
( <span class="methodparam"><span class="type">string</span>
`$host`</span> \[, <span class="methodparam"><span
class="type">int</span> `$port`<span class="initializer"> =
11211</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$persistent`</span> \[, <span
class="methodparam"><span class="type">int</span> `$weight`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$timeout`</span> \[, <span class="methodparam"><span
class="type">int</span> `$retry_interval`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$status`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$failure_callback`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeoutms`</span> \]\]\]\]\]\]\]\] )

<span class="type">bool</span> <span class="methodname">close</span> (
<span class="methodparam">void</span> )

<span class="type">bool</span> <span class="methodname">connect</span> (
<span class="methodparam"><span class="type">string</span>
`$host`</span> \[, <span class="methodparam"><span
class="type">int</span> `$port`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`</span> \]\]
)

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">decrement</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$value`<span
class="initializer"> = 1</span></span> \] )

<span class="type">bool</span> <span class="methodname">delete</span> (
<span class="methodparam"><span class="type">string</span> `$key`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$timeout`<span class="initializer"> = 0</span></span> \] )

<span class="type">bool</span> <span class="methodname">flush</span> (
<span class="methodparam">void</span> )

<span class="type">string</span> <span class="methodname">get</span> (
<span class="methodparam"><span class="type">string</span> `$key`</span>
\[, <span class="methodparam"><span class="type">int</span>
`&$flags`</span> \] )

<span class="type">array</span> <span
class="methodname">getExtendedStats</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`</span> \[,
<span class="methodparam"><span class="type">int</span> `$slabid`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$limit`<span class="initializer"> = 100</span></span> \]\]\] )

<span class="type">int</span> <span
class="methodname">getServerStatus</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 11211</span></span> \] )

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">getStats</span> (\[ <span class="methodparam"><span
class="type">string</span> `$type`</span> \[, <span
class="methodparam"><span class="type">int</span> `$slabid`</span> \[,
<span class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = 100</span></span> \]\]\] )

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">getVersion</span> ( <span
class="methodparam">void</span> )

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">increment</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$value`<span
class="initializer"> = 1</span></span> \] )

<span class="type">mixed</span> <span class="methodname">pconnect</span>
( <span class="methodparam"><span class="type">string</span>
`$host`</span> \[, <span class="methodparam"><span
class="type">int</span> `$port`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`</span> \]\]
)

<span class="type">bool</span> <span class="methodname">replace</span> (
<span class="methodparam"><span class="type">string</span> `$key`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$var`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flag`</span> \[, <span
class="methodparam"><span class="type">int</span> `$expire`</span> \]\]
)

<span class="type">bool</span> <span class="methodname">set</span> (
<span class="methodparam"><span class="type">string</span> `$key`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$var`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flag`</span> \[, <span
class="methodparam"><span class="type">int</span> `$expire`</span> \]\]
)

<span class="type">bool</span> <span
class="methodname">setCompressThreshold</span> ( <span
class="methodparam"><span class="type">int</span> `$threshold`</span>
\[, <span class="methodparam"><span class="type">float</span>
`$min_savings`</span> \] )

<span class="type">bool</span> <span
class="methodname">setServerParams</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 11211</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$retry_interval`<span class="initializer"> = **`false`**</span></span>
\[, <span class="methodparam"><span class="type">bool</span>
`$status`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$failure_callback`</span> \]\]\]\]\] )

}

Memcache::add
=============

Add an item to the server

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::add</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flag`</span> \[, <span class="methodparam"><span
class="type">int</span> `$expire`</span> \]\] )

<span class="function">Memcache::add</span> stores variable `var` with
`key` only if such key doesn't exist at the server yet. Also you can use
<span class="function">memcache\_add</span> function.

### Parameters

`key`  
The key that will be associated with the item.

`var`  
The variable to store. Strings and integers are stored as is, other
types are stored serialized.

`flag`  
Use **`MEMCACHE_COMPRESSED`** to store the item compressed (uses zlib).

`expire`  
Expiration time of the item. If it's equal to zero, the item will never
expire. You can also use Unix timestamp or a number of seconds starting
from current time, but in the latter case the number of seconds may not
exceed 2592000 (30 days).

### Return Values

Returns **`true`** on success or **`false`** on failure. Returns
**`false`** if such key already exist. For the rest <span
class="function">Memcache::add</span> behaves similarly to <span
class="function">Memcache::set</span>.

### Examples

**Example \#1 <span class="function">Memcache::add</span> example**

``` php
<?php

$memcache_obj = memcache_connect("localhost", 11211);

/* procedural API */
memcache_add($memcache_obj, 'var_key', 'test variable', false, 30);

/* OO API */
$memcache_obj->add('var_key', 'test variable', false, 30);

?>
```

### See Also

-   <span class="function">Memcache::set</span>
-   <span class="function">Memcache::replace</span>

Memcache::addServer
===================

Add a memcached server to connection pool

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::addServer</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 11211</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$persistent`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$weight`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeout`</span> \[, <span
class="methodparam"><span class="type">int</span>
`$retry_interval`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$status`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$failure_callback`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeoutms`</span> \]\]\]\]\]\]\]\] )

<span class="function">Memcache::addServer</span> adds a server to the
connection pool. You can also use the <span
class="function">memcache\_add\_server</span> function.

When using this method (as opposed to <span
class="function">Memcache::connect</span> and <span
class="function">Memcache::pconnect</span>) the network connection is
not established until actually needed. Thus there is no overhead in
adding a large number of servers to the pool, even though they might not
all be used.

Failover may occur at any stage in any of the methods, as long as other
servers are available the request the user won't notice. Any kind of
socket or Memcached server level errors (except out-of-memory) may
trigger the failover. Normal client errors such as adding an existing
key will not trigger a failover.

> **Note**:
>
> This function has been added to Memcache version 2.0.0.

### Parameters

`host`  
Point to the host where memcached is listening for connections. This
parameter may also specify other transports like
*unix:///path/to/memcached.sock* to use UNIX domain sockets, in this
case `port` must also be set to *0*.

`port`  
Point to the port where memcached is listening for connections. Set this
parameter to *0* when using UNIX domain sockets.

Please note: `port` defaults to
<a href="/memcache/setup.html#" class="link">memcache.default_port</a>
if not specified. For this reason it is wise to specify the port
explicitly in this method call.

`persistent`  
Controls the use of a persistent connection. Default to **`true`**.

`weight`  
Number of buckets to create for this server which in turn control its
probability of it being selected. The probability is relative to the
total weight of all servers.

`timeout`  
Value in seconds which will be used for connecting to the daemon. Think
twice before changing the default value of 1 second - you can lose all
the advantages of caching if your connection is too slow.

`retry_interval`  
Controls how often a failed server will be retried, the default value is
15 seconds. Setting this parameter to -1 disables automatic retry.
Neither this nor the `persistent` parameter has any effect when the
extension is loaded dynamically via <span class="function">dl</span>.

Each failed connection struct has its own timeout and before it has
expired the struct will be skipped when selecting backends to serve a
request. Once expired the connection will be successfully reconnected or
marked as failed for another `retry_interval` seconds. The typical
effect is that each web server child will retry the connection about
every `retry_interval` seconds when serving a page.

`status`  
Controls if the server should be flagged as online. Setting this
parameter to **`false`** and `retry_interval` to -1 allows a failed
server to be kept in the pool so as not to affect the key distribution
algorithm. Requests for this server will then failover or fail
immediately depending on the `memcache.allow_failover` setting. Default
to **`true`**, meaning the server should be considered online.

`failure_callback`  
Allows the user to specify a callback function to run upon encountering
an error. The callback is run before failover is attempted. The function
takes two parameters, the hostname and port of the failed server.

`timeoutms`  

### Notes

**Warning**

When the `port` is unspecified, this method defaults to the value set of
the PHP ini directive
<a href="/memcache/setup.html#" class="link">memcache.default_port</a>
If this value was changed elsewhere in your application it might lead to
unexpected results: for this reason it is wise to always specify the
port explicitly in this method call.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::addServer</span>
example**

``` php
<?php

/* OO API */

$memcache = new Memcache;
$memcache->addServer('memcache_host', 11211);
$memcache->addServer('memcache_host2', 11211);

/* procedural API */

$memcache_obj = memcache_connect('memcache_host', 11211);
memcache_add_server($memcache_obj, 'memcache_host2', 11211);

?>
```

### See Also

-   <span class="function">Memcache::connect</span>
-   <span class="function">Memcache::pconnect</span>
-   <span class="function">Memcache::close</span>
-   <span class="function">Memcache::setServerParams</span>
-   <span class="function">Memcache::getServerStatus</span>

Memcache::close
===============

Close memcached server connection

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::close</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcache::close</span> closes connection to
memcached server. This function doesn't close persistent connections,
which are closed only during web-server shutdown/restart. Also you can
use <span class="function">memcache\_close</span> function.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::close</span> example**

``` php
<?php

/* procedural API */
$memcache_obj = memcache_connect('memcache_host', 11211);
/* 
do something here ..
*/
memcache_close($memcache_obj);

/* OO API */
$memcache_obj = new Memcache;
$memcache_obj->connect('memcache_host', 11211);
/* 
do something here ..
*/
$memcache_obj->close();

?>
```

### See Also

-   <span class="function">Memcache::connect</span>
-   <span class="function">Memcache::pconnect</span>

Memcache::connect
=================

Open memcached server connection

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$timeout`</span> \]\] )

<span class="function">Memcache::connect</span> establishes a connection
to the memcached server. The connection, which was opened using <span
class="function">Memcache::connect</span> will be automatically closed
at the end of script execution. Also you can close it with <span
class="function">Memcache::close</span>. Also you can use <span
class="function">memcache\_connect</span> function.

### Parameters

`host`  
Point to the host where memcached is listening for connections. This
parameter may also specify other transports like
*unix:///path/to/memcached.sock* to use UNIX domain sockets, in this
case `port` must also be set to *0*.

`port`  
Point to the port where memcached is listening for connections. Set this
parameter to *0* when using UNIX domain sockets.

Please note: `port` defaults to
<a href="/memcache/setup.html#" class="link">memcache.default_port</a>
if not specified. For this reason it is wise to specify the port
explicitly in this method call.

`timeout`  
Value in seconds which will be used for connecting to the daemon. Think
twice before changing the default value of 1 second - you can lose all
the advantages of caching if your connection is too slow.

### Notes

**Warning**

When the `port` is unspecified, this method defaults to the value set of
the PHP ini directive
<a href="/memcache/setup.html#" class="link">memcache.default_port</a>
If this value was changed elsewhere in your application it might lead to
unexpected results: for this reason it is wise to always specify the
port explicitly in this method call.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::connect</span> example**

``` php
<?php

/* procedural API */

$memcache_obj = memcache_connect('memcache_host', 11211);

/* OO API */

$memcache = new Memcache;
$memcache->connect('memcache_host', 11211);

?>
```

### See Also

-   <span class="function">Memcache::pconnect</span>
-   <span class="function">Memcache::close</span>

Memcache::decrement
===================

Decrement item's value

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">Memcache::decrement</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">int</span> `$value`<span
class="initializer"> = 1</span></span> \] )

<span class="function">Memcache::decrement</span> decrements value of
the item by `value`. Similarly to <span
class="function">Memcache::increment</span>, current value of the item
is being converted to numerical and after that `value` is subtracted.

> **Note**:
>
> New item's value will not be less than zero.

> **Note**:
>
> Do not use <span class="function">Memcache::decrement</span> with
> item, which was stored compressed, because consequent call to <span
> class="function">Memcache::get</span> will fail.

<span class="function">Memcache::decrement</span> *does not* create an
item if it didn't exist. Also you can use <span
class="function">memcache\_decrement</span> function.

### Parameters

`key`  
Key of the item do decrement.

`value`  
Decrement the item by `value`.

### Return Values

Returns item's new value on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::decrement</span>
example**

``` php
<?php

/* procedural API */
$memcache_obj = memcache_connect('memcache_host', 11211);
/* decrement item by 2 */
$new_value = memcache_decrement($memcache_obj, 'test_item', 2);

/* OO API */
$memcache_obj = new Memcache;
$memcache_obj->connect('memcache_host', 11211);
/* decrement item by 3 */
$new_value = $memcache_obj->decrement('test_item', 3);
?>
```

### See Also

-   <span class="function">Memcache::increment</span>
-   <span class="function">Memcache::replace</span>

Memcache::delete
================

Delete item from the server

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::delete</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 0</span></span> \] )

<span class="function">Memcache::delete</span> deletes an item with the
`key`.

### Parameters

`key`  
The key associated with the item to delete.

`timeout`  
This deprecated parameter is not supported, and defaults to *0* seconds.
Do not use this parameter.

### Changelog

| Version | Description                                                                                                                                                                                                       |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Unknown | It's not recommended to use the `timeout` parameter. The behavior differs between memcached versions, but setting to *0* is safe. Other values for this deprecated feature may cause the memcache delete to fail. |

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::delete</span> example**

``` php
<?php

/* procedural API */
$memcache_obj = memcache_connect('memcache_host', 11211);

/* item will be deleted by the server */
memcache_delete($memcache_obj, 'key_to_delete');

/* OO API */
$memcache_obj = new Memcache;
$memcache_obj->connect('memcache_host', 11211);

$memcache_obj->delete('key_to_delete');

?>
```

### See Also

-   <span class="function">Memcache::set</span>
-   <span class="function">Memcache::replace</span>

Memcache::flush
===============

Flush all existing items at the server

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::flush</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcache::flush</span> immediately invalidates
all existing items. <span class="function">Memcache::flush</span>
doesn't actually free any resources, it only marks all the items as
expired, so occupied memory will be overwritten by new items. Also you
can use <span class="function">memcache\_flush</span> function.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::flush</span> example**

``` php
<?php

/* procedural API */
$memcache_obj = memcache_connect('memcache_host', 11211);

memcache_flush($memcache_obj);

/* OO API */

$memcache_obj = new Memcache;
$memcache_obj->connect('memcache_host', 11211);

$memcache_obj->flush();

?>
```

Memcache::get
=============

Retrieve item from the server

### Description

<span class="type">string</span> <span
class="methodname">Memcache::get</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">int</span> `&$flags`</span>
\] )

<span class="type">array</span> <span
class="methodname">Memcache::get</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">array</span>
`&$flags`</span> \] )

<span class="function">Memcache::get</span> returns previously stored
data of an item, if such `key` exists on the server at this moment.

You can pass array of keys to <span
class="function">Memcache::get</span> to get array of values. The result
array will contain only found key-value pairs.

### Parameters

`key`  
The key or array of keys to fetch.

`flags`  
If present, flags fetched along with the values will be written to this
parameter. These flags are the same as the ones given to for example
<span class="function">Memcache::set</span>. The lowest byte of the int
is reserved for pecl/memcache internal usage (e.g. to indicate
compression and serialization status).

### Return Values

Returns the value associated with the `key` or an array of found
key-value pairs when `key` is an <span class="type">array</span>.
Returns **`false`** on failure, `key` is not found or `key` is an empty
<span class="type">array</span>.

### Examples

**Example \#1 <span class="function">Memcache::get</span> example**

``` php
<?php

/* procedural API */
$memcache_obj = memcache_connect('memcache_host', 11211);
$var = memcache_get($memcache_obj, 'some_key');

/* OO API */
$memcache_obj = new Memcache;
$memcache_obj->connect('memcache_host', 11211);
$var = $memcache_obj->get('some_key');

/* 
You also can use array of keys as a parameter.
If such item wasn't found at the server, the result
array simply will not include such key.
*/

/* procedural API */
$memcache_obj = memcache_connect('memcache_host', 11211);
$var = memcache_get($memcache_obj, Array('some_key', 'another_key'));

/* OO API */
$memcache_obj = new Memcache;
$memcache_obj->connect('memcache_host', 11211);
$var = $memcache_obj->get(Array('some_key', 'second_key'));

?>
```

Memcache::getExtendedStats
==========================

Get statistics from all servers in pool

### Description

<span class="type">array</span> <span
class="methodname">Memcache::getExtendedStats</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`</span> \[,
<span class="methodparam"><span class="type">int</span> `$slabid`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$limit`<span class="initializer"> = 100</span></span> \]\]\] )

<span class="function">Memcache::getExtendedStats</span> returns a
two-dimensional associative array with server statistics. Array keys
correspond to host:port of server and values contain the individual
server statistics. A failed server will have its corresponding entry set
to **`false`**. You can also use the <span
class="function">memcache\_get\_extended\_stats</span> function.

> **Note**:
>
> This function has been added to Memcache version 2.0.0.

### Parameters

`type`  
The type of statistics to fetch. Valid values are {reset, malloc, maps,
cachedump, slabs, items, sizes}. According to the memcached protocol
spec these additional arguments "are subject to change for the
convenience of memcache developers".

`slabid`  
Used in conjunction with `type` set to cachedump to identify the slab to
dump from. The cachedump command ties up the server and is strictly to
be used for debugging purposes.

`limit`  
Used in conjunction with `type` set to cachedump to limit the number of
entries to dump.

**Warning**

The cachedump stat type has been removed from the memcached daemon due
to security reasons.

### Return Values

Returns a two-dimensional associative array of server statistics or
**`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::getExtendedStats</span>
example**

``` php
<?php
    $memcache_obj = new Memcache;
    $memcache_obj->addServer('memcache_host', 11211);
    $memcache_obj->addServer('failed_host', 11211);
    
    $stats = $memcache_obj->getExtendedStats();
    print_r($stats);
?>
```

The above example will output:

    Array
    (
        [memcache_host:11211] => Array
            (
                [pid] => 3756
                [uptime] => 603011
                [time] => 1133810435
                [version] => 1.1.12
                [rusage_user] => 0.451931
                [rusage_system] => 0.634903
                [curr_items] => 2483
                [total_items] => 3079
                [bytes] => 2718136
                [curr_connections] => 2
                [total_connections] => 807
                [connection_structures] => 13
                [cmd_get] => 9748
                [cmd_set] => 3096
                [get_hits] => 5976
                [get_misses] => 3772
                [bytes_read] => 3448968
                [bytes_written] => 2318883
                [limit_maxbytes] => 33554432
            )

        [failed_host:11211] => false
    )

### See Also

-   <span class="function">Memcache::getVersion</span>
-   <span class="function">Memcache::getStats</span>

Memcache::getServerStatus
=========================

Returns server status

### Description

<span class="type">int</span> <span
class="methodname">Memcache::getServerStatus</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 11211</span></span> \] )

<span class="function">Memcache::getServerStatus</span> returns a the
servers online/offline status. You can also use <span
class="function">memcache\_get\_server\_status</span> function.

> **Note**:
>
> This function has been added to Memcache version 2.1.0.

### Parameters

`host`  
Point to the host where memcached is listening for connections.

`port`  
Point to the port where memcached is listening for connections.

### Return Values

Returns a the servers status. 0 if server is failed, non-zero otherwise

### Examples

**Example \#1 <span class="function">Memcache::getServerStatus</span>
example**

``` php
<?php

/* OO API */
$memcache = new Memcache;
$memcache->addServer('memcache_host', 11211);
echo $memcache->getServerStatus('memcache_host', 11211);

/* procedural API */
$memcache = memcache_connect('memcache_host', 11211);
echo memcache_get_server_status($memcache, 'memcache_host', 11211);

?>
```

### See Also

-   <span class="function">Memcache::addServer</span>
-   <span class="function">Memcache::setServerParams</span>

Memcache::getStats
==================

Get statistics of the server

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">Memcache::getStats</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`</span> \[,
<span class="methodparam"><span class="type">int</span> `$slabid`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$limit`<span class="initializer"> = 100</span></span> \]\]\] )

<span class="function">Memcache::getStats</span> returns an associative
array with server's statistics. Array keys correspond to stats
parameters and values to parameter's values. Also you can use <span
class="function">memcache\_get\_stats</span> function.

### Parameters

`type`  
The type of statistics to fetch. Valid values are {reset, malloc, maps,
cachedump, slabs, items, sizes}. According to the memcached protocol
spec these additional arguments "are subject to change for the
convenience of memcache developers".

`slabid`  
Used in conjunction with `type` set to cachedump to identify the slab to
dump from. The cachedump command ties up the server and is strictly to
be used for debugging purposes.

`limit`  
Used in conjunction with `type` set to cachedump to limit the number of
entries to dump.

### Return Values

Returns an associative array of server statistics or **`false`** on
failure.

### See Also

-   <span class="function">Memcache::getVersion</span>
-   <span class="function">Memcache::getExtendedStats</span>

Memcache::getVersion
====================

Return version of the server

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">Memcache::getVersion</span> ( <span
class="methodparam">void</span> )

<span class="function">Memcache::getVersion</span> returns a string with
server's version number. Also you can use <span
class="function">memcache\_get\_version</span> function.

### Return Values

Returns a string of server version number or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::getVersion</span>
example**

``` php
<?php

/* OO API */
$memcache = new Memcache;
$memcache->connect('memcache_host', 11211);
echo $memcache->getVersion();

/* procedural API */
$memcache = memcache_connect('memcache_host', 11211);
echo memcache_get_version($memcache);

?>
```

### See Also

-   <span class="function">Memcache::getExtendedStats</span>
-   <span class="function">Memcache::getStats</span>

Memcache::increment
===================

Increment item's value

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">Memcache::increment</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">int</span> `$value`<span
class="initializer"> = 1</span></span> \] )

<span class="function">Memcache::increment</span> increments value of an
item by the specified `value`. If item specified by `key` was not
numeric and cannot be converted to a number, it will change its value to
`value`. <span class="function">Memcache::increment</span> *does not*
create an item if it doesn't already exist.

> **Note**:
>
> Do not use <span class="function">Memcache::increment</span> with
> items that have been stored compressed because subsequent calls to
> <span class="function">Memcache::get</span> will fail.

Also you can use <span class="function">memcache\_increment</span>
function.

### Parameters

`key`  
Key of the item to increment.

`value`  
Increment the item by `value`.

### Return Values

Returns new items value on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::increment</span>
example**

``` php
<?php

/* procedural API */
$memcache_obj = memcache_connect('memcache_host', 11211);
/* increment counter by 2 */
$current_value = memcache_increment($memcache_obj, 'counter', 2);

/* OO API */
$memcache_obj = new Memcache;
$memcache_obj->connect('memcache_host', 11211);
/* increment counter by 3 */
$current_value = $memcache_obj->increment('counter', 3);

?>
```

### See Also

-   <span class="function">Memcache::decrement</span>
-   <span class="function">Memcache::replace</span>

Memcache::pconnect
==================

Open memcached server persistent connection

### Description

<span class="type">mixed</span> <span
class="methodname">Memcache::pconnect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$timeout`</span> \]\] )

<span class="function">Memcache::pconnect</span> is similar to <span
class="function">Memcache::connect</span> with the difference, that the
connection it establishes is persistent. This connection is not closed
after the end of script execution and by <span
class="function">Memcache::close</span> function. Also you can use <span
class="function">memcache\_pconnect</span> function.

### Parameters

`host`  
Point to the host where memcached is listening for connections. This
parameter may also specify other transports like
*unix:///path/to/memcached.sock* to use UNIX domain sockets, in this
case `port` must also be set to *0*.

`port`  
Point to the port where memcached is listening for connections. Set this
parameter to *0* when using UNIX domain sockets.

`timeout`  
Value in seconds which will be used for connecting to the daemon. Think
twice before changing the default value of 1 second - you can lose all
the advantages of caching if your connection is too slow.

### Return Values

Returns a Memcache object or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::pconnect</span> example**

``` php
<?php

/* procedural API */
$memcache_obj = memcache_pconnect('memcache_host', 11211);

/* OO API */

$memcache_obj = new Memcache;
$memcache_obj->pconnect('memcache_host', 11211);

?>
```

### See Also

-   <span class="function">Memcache::connect</span>

Memcache::replace
=================

Replace value of the existing item

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::replace</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flag`</span> \[, <span class="methodparam"><span
class="type">int</span> `$expire`</span> \]\] )

<span class="function">Memcache::replace</span> should be used to
replace value of existing item with `key`. In case if item with such key
doesn't exists, <span class="function">Memcache::replace</span> returns
**`false`**. For the rest <span
class="function">Memcache::replace</span> behaves similarly to <span
class="function">Memcache::set</span>. Also you can use <span
class="function">memcache\_replace</span> function.

### Parameters

`key`  
The key that will be associated with the item.

`var`  
The variable to store. Strings and integers are stored as is, other
types are stored serialized.

`flag`  
Use **`MEMCACHE_COMPRESSED`** to store the item compressed (uses zlib).

`expire`  
Expiration time of the item. If it's equal to zero, the item will never
expire. You can also use Unix timestamp or a number of seconds starting
from current time, but in the latter case the number of seconds may not
exceed 2592000 (30 days).

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::replace</span> example**

``` php
<?php

$memcache_obj = memcache_connect('memcache_host', 11211);

/* procedural API */
memcache_replace($memcache_obj, "test_key", "some variable", false, 30);

/* OO API */
$memcache_obj->replace("test_key", "some variable", false, 30);

?>
```

### See Also

-   <span class="function">Memcache::set</span>
-   <span class="function">Memcache::add</span>

Memcache::set
=============

Store data at the server

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::set</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flag`</span> \[, <span class="methodparam"><span
class="type">int</span> `$expire`</span> \]\] )

<span class="function">Memcache::set</span> stores an item `var` with
`key` on the memcached server. Parameter `expire` is expiration time in
seconds. If it's 0, the item never expires (but memcached server doesn't
guarantee this item to be stored all the time, it could be deleted from
the cache to make place for other items). You can use
**`MEMCACHE_COMPRESSED`** constant as `flag` value if you want to use
on-the-fly compression (uses zlib).

> **Note**:
>
> Remember that resource variables (i.e. file and connection
> descriptors) cannot be stored in the cache, because they cannot be
> adequately represented in serialized state.

Also you can use <span class="function">memcache\_set</span> function.

### Parameters

`key`  
The key that will be associated with the item.

`var`  
The variable to store. Strings and integers are stored as is, other
types are stored serialized.

`flag`  
Use **`MEMCACHE_COMPRESSED`** to store the item compressed (uses zlib).

`expire`  
Expiration time of the item. If it's equal to zero, the item will never
expire. You can also use Unix timestamp or a number of seconds starting
from current time, but in the latter case the number of seconds may not
exceed 2592000 (30 days).

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::set</span> example**

``` php
<?php
/* procedural API */

/* connect to memcached server */
$memcache_obj = memcache_connect('memcache_host', 11211);

/*
set value of item with key 'var_key'
using 0 as flag value, compression is not used
expire time is 30 seconds
*/
memcache_set($memcache_obj, 'var_key', 'some variable', 0, 30);

echo memcache_get($memcache_obj, 'var_key');

?>
```

**Example \#2 <span class="function">Memcache::set</span> example**

``` php
<?php
/* OO API */

$memcache_obj = new Memcache;

/* connect to memcached server */
$memcache_obj->connect('memcache_host', 11211);

/*
set value of item with key 'var_key', using on-the-fly compression
expire time is 50 seconds
*/
$memcache_obj->set('var_key', 'some really big variable', MEMCACHE_COMPRESSED, 50);

echo $memcache_obj->get('var_key');

?>
```

### See Also

-   <span class="function">Memcache::add</span>
-   <span class="function">Memcache::replace</span>

Memcache::setCompressThreshold
==============================

Enable automatic compression of large values

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::setCompressThreshold</span> ( <span
class="methodparam"><span class="type">int</span> `$threshold`</span>
\[, <span class="methodparam"><span class="type">float</span>
`$min_savings`</span> \] )

<span class="function">Memcache::setCompressThreshold</span> enables
automatic compression of large values. You can also use the <span
class="function">memcache\_set\_compress\_threshold</span> function.

> **Note**:
>
> This function has been added to Memcache version 2.0.0.

### Parameters

`threshold`  
Controls the minimum value length before attempting to compress
automatically.

`min_saving`  
Specifies the minimum amount of savings to actually store the value
compressed. The supplied value must be between 0 and 1. Default value is
0.2 giving a minimum 20% compression savings.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span
class="function">Memcache::setCompressThreshold</span> example**

``` php
<?php

/* OO API */

$memcache_obj = new Memcache;
$memcache_obj->addServer('memcache_host', 11211);
$memcache_obj->setCompressThreshold(20000, 0.2);

/* procedural API */

$memcache_obj = memcache_connect('memcache_host', 11211);
memcache_set_compress_threshold($memcache_obj, 20000, 0.2);

?>
```

Memcache::setServerParams
=========================

Changes server parameters and status at runtime

### Description

<span class="type">bool</span> <span
class="methodname">Memcache::setServerParams</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 11211</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$retry_interval`<span class="initializer"> = **`false`**</span></span>
\[, <span class="methodparam"><span class="type">bool</span>
`$status`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$failure_callback`</span> \]\]\]\]\] )

<span class="function">Memcache::setServerParams</span> changes server
parameters at runtime. You can also use the <span
class="function">memcache\_set\_server\_params</span> function.

> **Note**:
>
> This function has been added to Memcache version 2.1.0.

### Parameters

`host`  
Point to the host where memcached is listening for connections.

`port`  
Point to the port where memcached is listening for connections.

`timeout`  
Value in seconds which will be used for connecting to the daemon. Think
twice before changing the default value of 1 second - you can lose all
the advantages of caching if your connection is too slow.

`retry_interval`  
Controls how often a failed server will be retried, the default value is
15 seconds. Setting this parameter to -1 disables automatic retry.
Neither this nor the `persistent` parameter has any effect when the
extension is loaded dynamically via <span class="function">dl</span>.

`status`  
Controls if the server should be flagged as online. Setting this
parameter to **`false`** and `retry_interval` to -1 allows a failed
server to be kept in the pool so as not to affect the key distribution
algorithm. Requests for this server will then failover or fail
immediately depending on the `memcache.allow_failover` setting. Default
to **`true`**, meaning the server should be considered online.

`failure_callback`  
Allows the user to specify a callback function to run upon encountering
an error. The callback is run before failover is attempted. The function
takes two parameters, the hostname and port of the failed server.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">Memcache::setServerParams</span>
example**

``` php
<?php

function _callback_memcache_failure($host, $port) {
    print "memcache '$host:$port' failed";
}

/* OO API */

$memcache = new Memcache;

// Add the server in offline mode
$memcache->addServer('memcache_host', 11211, false, 1, 1, -1, false);

// Bring the server back online
$memcache->setServerParams('memcache_host', 11211, 1, 15, true, '_callback_memcache_failure');

/* procedural API */

$memcache_obj = memcache_connect('memcache_host', 11211);
memcache_set_server_params($memcache_obj, 'memcache_host', 11211, 1, 15, true, '_callback_memcache_failure');

?>
```

### See Also

-   <span class="function">Memcache::addServer</span>
-   <span class="function">Memcache::getServerStatus</span>

yp\_all
=======

Traverse the map and call a function on each entry

### Description

<span class="type">void</span> <span class="methodname">yp\_all</span> (
<span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$map`</span> , <span
class="methodparam"><span class="type">string</span> `$callback`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`domain`  
The NIS domain name.

`map`  
The NIS map.

`callback`  

### Return Values

No value is returned.

yp\_cat
=======

Return an array containing the entire map

### Description

<span class="type">array</span> <span class="methodname">yp\_cat</span>
( <span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$map`</span> )

Returns all map entries.

### Parameters

`domain`  
The NIS domain name.

`map`  
The NIS map.

### Return Values

Returns an array of all map entries, the maps key values as array
indices and the maps entries as array data.

yp\_err\_string
===============

Returns the error string associated with the given error code

### Description

<span class="type">string</span> <span
class="methodname">yp\_err\_string</span> ( <span
class="methodparam"><span class="type">int</span> `$errorcode`</span> )

Returns the error message associated with the given error code. Useful
to indicate what exactly went wrong.

### Parameters

`errorcode`  
The error code.

### Return Values

Returns the error message, as a string.

### Examples

**Example \#1 Example for NIS errors**

``` php
<?php
echo "Error: " . yp_err_string(yp_errno());
?>
```

### See Also

-   <span class="function">yp\_errno</span>

yp\_errno
=========

Returns the error code of the previous operation

### Description

<span class="type">int</span> <span class="methodname">yp\_errno</span>
( <span class="methodparam">void</span> )

Returns the error code of the previous operation.

### Return Values

Returns one of the *YPERR\_XXX* error constants.

### See Also

-   <span class="function">yp\_err\_string</span>

yp\_first
=========

Returns the first key-value pair from the named map

### Description

<span class="type">array</span> <span
class="methodname">yp\_first</span> ( <span class="methodparam"><span
class="type">string</span> `$domain`</span> , <span
class="methodparam"><span class="type">string</span> `$map`</span> )

Gets the first key-value pair from the named `map` in the named
`domain`.

### Parameters

`domain`  
The NIS domain name.

`map`  
The NIS map.

### Return Values

Returns the first key-value pair as an array on success, or **`FALSE`**
on errors.

### Examples

**Example \#1 Example for the NIS first**

``` php
<?php
$entry = yp_first($domain, "passwd.byname");

$key = key($entry);
$value = $entry[$key];

echo "First entry in this map has key " . $key . " and value " . $value;
?>
```

### See Also

-   <span class="function">yp\_next</span>
-   <span class="function">yp\_get\_default\_domain</span>

yp\_get\_default\_domain
========================

Fetches the machine's default NIS domain

### Description

<span class="type">string</span> <span
class="methodname">yp\_get\_default\_domain</span> ( <span
class="methodparam">void</span> )

Returns the default domain of the node. Can be used as the domain
parameter for successive NIS calls.

A NIS domain can be described a group of NIS maps. Every host that needs
to look up information binds itself to a certain domain. Refer to the
documents mentioned at the beginning for more detailed information.

### Return Values

Returns the default domain of the node or **`FALSE`**. Can be used as
the domain parameter for successive NIS calls.

### Examples

**Example \#1 Example for the default domain**

``` php
<?php
$domain = yp_get_default_domain();
echo "Default NIS domain is: " . $domain;
?>
```

yp\_master
==========

Returns the machine name of the master NIS server for a map

### Description

<span class="type">string</span> <span
class="methodname">yp\_master</span> ( <span class="methodparam"><span
class="type">string</span> `$domain`</span> , <span
class="methodparam"><span class="type">string</span> `$map`</span> )

Returns the machine name of the master NIS server for a `map`.

### Parameters

`domain`  
The NIS domain name.

`map`  
The NIS map.

### Return Values

### Examples

**Example \#1 Example for the NIS master**

``` php
<?php
$number = yp_master($domain, $mapname);
echo "Master for this map is: " . $master;
?>
```

### See Also

-   <span class="function">yp\_get\_default\_domain</span>

yp\_match
=========

Returns the matched line

### Description

<span class="type">string</span> <span
class="methodname">yp\_match</span> ( <span class="methodparam"><span
class="type">string</span> `$domain`</span> , <span
class="methodparam"><span class="type">string</span> `$map`</span> ,
<span class="methodparam"><span class="type">string</span> `$key`</span>
)

Returns the value associated with the passed `key` out of the specified
`map`.

### Parameters

`domain`  
The NIS domain name.

`map`  
The NIS map.

`key`  
This key must be exact.

### Return Values

Returns the value, or **`FALSE`** on errors.

### Examples

**Example \#1 Example for NIS match**

``` php
<?php
$entry = yp_match($domain, "passwd.byname", "joe");
echo "Matched entry is: " . $entry;
?>
```

The above example will output something similar to:

    joe:##joe:11111:100:Joe User:/home/j/joe:/usr/local/bin/bash

### See Also

-   <span class="function">yp\_get\_default\_domain</span>

yp\_next
========

Returns the next key-value pair in the named map

### Description

<span class="type">array</span> <span class="methodname">yp\_next</span>
( <span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$map`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> )

Returns the next key-value pair in the named `map` after the specified
`key`.

### Parameters

`domain`  

`map`  

`key`  

### Return Values

Returns the next key-value pair as an array, or **`FALSE`** on errors.

### Examples

**Example \#1 Example for NIS next**

``` php
<?php
$entry = yp_next($domain, "passwd.byname", "joe");

if (!$entry) {
    echo "No more entries found\n";
    echo "<!--" . yp_errno() . ": " . yp_err_string() . "-->";
}

$key = key($entry);

echo "The next entry after joe has key " . $key
      . " and value " . $entry[$key];
?>
```

### See Also

-   <span class="function">yp\_first</span>
-   <span class="function">yp\_get\_default\_domain</span>

yp\_order
=========

Returns the order number for a map

### Description

<span class="type">int</span> <span class="methodname">yp\_order</span>
( <span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$map`</span> )

Gets the order number for a map.

### Parameters

`domain`  

`map`  

### Return Values

Returns the order number for a map or **`FALSE`** on error.

### Examples

**Example \#1 Example for the NIS order**

``` php
<?php
    $number = yp_order($domain, $mapname);
    echo "Order number for this map is: " . $number;
?>
```

### See Also

-   <span class="function">yp\_get\_default\_domain</span>

**Table of Contents**

-   [yp\_all](/ref/nis.html#yp_all) — Traverse the map and call a
    function on each entry
-   [yp\_cat](/ref/nis.html#yp_cat) — Return an array containing the
    entire map
-   [yp\_err\_string](/ref/nis.html#yp_err_string) — Returns the error
    string associated with the given error code
-   [yp\_errno](/ref/nis.html#yp_errno) — Returns the error code of the
    previous operation
-   [yp\_first](/ref/nis.html#yp_first) — Returns the first key-value
    pair from the named map
-   [yp\_get\_default\_domain](/ref/nis.html#yp_get_default_domain) —
    Fetches the machine's default NIS domain
-   [yp\_master](/ref/nis.html#yp_master) — Returns the machine name of
    the master NIS server for a map
-   [yp\_match](/ref/nis.html#yp_match) — Returns the matched line
-   [yp\_next](/ref/nis.html#yp_next) — Returns the next key-value pair
    in the named map
-   [yp\_order](/ref/nis.html#yp_order) — Returns the order number for a
    map

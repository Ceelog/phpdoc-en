apcu\_add
=========

Cache a new variable in the data store

### Description

<span class="type">bool</span> <span class="methodname">apcu\_add</span>
( <span class="methodparam"><span class="type">string</span>
`$key`</span> , <span class="methodparam"><span
class="type">mixed</span> `$var`</span> \[, <span
class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \] )

<span class="type">array</span> <span
class="methodname">apcu\_add</span> ( <span class="methodparam"><span
class="type">array</span> `$values`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$unused`<span
class="initializer"> = NULL</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \]\] )

Caches a variable in the data store, only if it's not already stored.

> **Note**: <span class="simpara"> Unlike many other mechanisms in PHP,
> variables stored using <span class="function">apcu\_add</span> will
> persist between requests (until the value is removed from the cache).
> </span>

### Parameters

`key`  
Store the variable using this name. `key`s are cache-unique, so
attempting to use <span class="function">apcu\_add</span> to store data
with a key that already exists will not overwrite the existing data, and
will instead return **`false`**. (This is the only difference between
<span class="function">apcu\_add</span> and <span
class="function">apcu\_store</span>.)

`var`  
The variable to store

`ttl`  
Time To Live; store `var` in the cache for `ttl` seconds. After the
`ttl` has passed, the stored variable will be expunged from the cache
(on the next request). If no `ttl` is supplied (or if the `ttl` is *0*),
the value will persist until it is removed from the cache manually, or
otherwise fails to exist in the cache (clear, restart, etc.).

`values`  
Names in key, variables in value.

### Return Values

Returns TRUE if something has effectively been added into the cache,
FALSE otherwise. Second syntax returns array with error keys.

### Examples

**Example \#1 A <span class="function">apcu\_add</span> example**

``` php
<?php
$bar = 'BAR';
apcu_add('foo', $bar);
var_dump(apcu_fetch('foo'));
echo "\n";
$bar = 'NEVER GETS SET';
apcu_add('foo', $bar);
var_dump(apcu_fetch('foo'));
echo "\n";
?>
```

The above example will output:

    string(3) "BAR"
    string(3) "BAR"

### See Also

-   <span class="function">apcu\_store</span>
-   <span class="function">apcu\_fetch</span>
-   <span class="function">apcu\_delete</span>

apcu\_cache\_info
=================

Retrieves cached information from APCu's data store

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">apcu\_cache\_info</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$limited`<span
class="initializer"> = **`false`**</span></span> \] )

Retrieves cached information and meta-data from APC's data store.

### Parameters

`limited`  
If `limited` is **`true`**, the return value will exclude the individual
list of cache entries. This is useful when trying to optimize calls for
statistics gathering.

### Return Values

Array of cached data (and meta-data) or **`false`** on failure

> **Note**: <span class="simpara"> <span
> class="function">apcu\_cache\_info</span> will raise a warning if it
> is unable to retrieve APC cache data. This typically occurs when APC
> is not enabled. </span>

### Changelog

| Version          | Description                                                            |
|------------------|------------------------------------------------------------------------|
| PECL apcu 3.0.11 | The `limited` parameter was introduced.                                |
| PECL apcu 3.0.16 | The "*filehits*" option for the `cache_type` parameter was introduced. |

### Examples

**Example \#1 A <span class="function">apcu\_cache\_info</span>
example**

``` php
<?php
print_r(apcu_cache_info());
?>
```

The above example will output something similar to:

    Array
    (
        [num_slots] => 2000
        [ttl] => 0
        [num_hits] => 9
        [num_misses] => 3
        [start_time] => 1123958803
        [cache_list] => Array
            (
                [0] => Array
                    (
                        [filename] => /path/to/apcu_test.php
                        [device] => 29954
                        [inode] => 1130511
                        [type] => file
                        [num_hits] => 1
                        [mtime] => 1123960686
                        [creation_time] => 1123960696
                        [deletion_time] => 0
                        [access_time] => 1123962864
                        [ref_count] => 1
                        [mem_size] => 677
                    )
                [1] => Array (...iterates for each cached file)
    )

### See Also

-   <a href="/apcu/setup.html#Runtime%20Configuration" class="link">APCu configuration directives</a>
-   <span class="methodname">APCUIterator::getTotalSize</span>
-   <span class="methodname">APCUIterator::getTotalHits</span>
-   <span class="methodname">APCUIterator::getTotalCount</span>

apcu\_cas
=========

Updates an old value with a new value

### Description

<span class="type">bool</span> <span class="methodname">apcu\_cas</span>
( <span class="methodparam"><span class="type">string</span>
`$key`</span> , <span class="methodparam"><span class="type">int</span>
`$old`</span> , <span class="methodparam"><span class="type">int</span>
`$new`</span> )

<span class="function">apcu\_cas</span> updates an already existing
integer value if the `old` parameter matches the currently stored value
with the value of the `new` parameter.

### Parameters

`key`  
The key of the value being updated.

`old`  
The old value (the value currently stored).

`new`  
The new value to update to.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">apcu\_cas</span> example**

``` php
<?php
apcu_store('foobar', 2);
echo '$foobar = 2', PHP_EOL;
echo '$foobar == 1 ? 2 : 1 = ', (apcu_cas('foobar', 1, 2) ? 'ok' : 'fail'), PHP_EOL;
echo '$foobar == 2 ? 1 : 2 = ', (apcu_cas('foobar', 2, 1) ? 'ok' : 'fail'), PHP_EOL;

echo '$foobar = ', apcu_fetch('foobar'), PHP_EOL;

echo '$f__bar == 1 ? 2 : 1 = ', (apcu_cas('f__bar', 1, 2) ? 'ok' : 'fail'), PHP_EOL;

apcu_store('perfection', 'xyz');
echo '$perfection == 2 ? 1 : 2 = ', (apcu_cas('perfection', 2, 1) ? 'ok' : 'epic fail'), PHP_EOL;

echo '$foobar = ', apcu_fetch('foobar'), PHP_EOL;
?>
```

The above example will output something similar to:

    $foobar = 2
    $foobar == 1 ? 2 : 1 = fail
    $foobar == 2 ? 1 : 2 = ok
    $foobar = 1
    $f__bar == 1 ? 2 : 1 = fail
    $perfection == 2 ? 1 : 2 = epic fail
    $foobar = 1

### See Also

-   <span class="function">apcu\_dec</span>
-   <span class="function">apcu\_store</span>

apcu\_clear\_cache
==================

Clears the APCu cache

### Description

<span class="type">bool</span> <span
class="methodname">apcu\_clear\_cache</span> ( <span
class="methodparam">void</span> )

Clears the cache.

### Parameters

This function has no parameters.

### Return Values

Returns **`true`** always

### See Also

-   <span class="function">apcu\_cache\_info</span>

apcu\_dec
=========

Decrease a stored number

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">apcu\_dec</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$step`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `&$success`</span>
\[, <span class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \]\]\] )

Decreases a stored integer value.

### Parameters

`key`  
The key of the value being decreased.

`step`  
The step, or value to decrease.

`success`  
Optionally pass the success or fail boolean value to this referenced
variable.

`ttl`  
TTL to use if the operation inserts a new value (rather than
decrementing an existing one).

### Return Values

Returns the current value of `key`'s value on success, or **`false`** on
failure

### Changelog

| Version | Description                         |
|---------|-------------------------------------|
| 5.1.12  | The `ttl` parameter has been added. |

### Examples

**Example \#1 <span class="function">apcu\_dec</span> example**

``` php
<?php
echo "Let's do something with success", PHP_EOL;

apcu_store('anumber', 42);

echo apcu_fetch('anumber'), PHP_EOL;

echo apcu_dec('anumber'), PHP_EOL;
echo apcu_dec('anumber', 10), PHP_EOL;
echo apcu_dec('anumber', 10, $success), PHP_EOL;

var_dump($success);

echo "Now, let's fail", PHP_EOL, PHP_EOL;

apcu_store('astring', 'foo');

$ret = apcu_dec('astring', 1, $fail);

var_dump($ret);
var_dump($fail);
?>
```

The above example will output something similar to:

    Let's do something with success
    42
    41
    31
    21
    bool(true)
    Now, let's fail

    bool(false)
    bool(false)

### See Also

-   <span class="function">apcu\_inc</span>

apcu\_delete
============

Removes a stored variable from the cache

### Description

<span class="type">mixed</span> <span
class="methodname">apcu\_delete</span> ( <span class="methodparam"><span
class="type">mixed</span> `$key`</span> )

Removes a stored variable from the cache.

### Parameters

`key`  
A `key` used to store the value as a <span class="type">string</span>
for a single key, or as an <span class="type">array</span> of strings
for several keys, or as an <span class="classname">APCUIterator</span>
<span class="type">object</span>.

### Return Values

If `key` is an <span class="type">array</span>, an indexed <span
class="type">array</span> of the keys is returned. Otherwise **`true`**
is returned on success, or **`false`** on failure.

### Examples

**Example \#1 A <span class="function">apcu\_delete</span> example**

``` php
<?php
$bar = 'BAR';
apcu_store('foo', $bar);
apcu_delete('foo');
// this is obviously useless in this form

// Alternatively delete multiple keys.
apcu_delete(['foo', 'bar', 'baz']);

// Or use an Iterator with a regular expression.
apcu_delete(new APCUIterator('#^myprefix_#'));
?>
```

### See Also

-   <span class="function">apcu\_store</span>
-   <span class="function">apcu\_fetch</span>
-   <span class="function">apcu\_clear\_cache</span>
-   <span class="classname">APCUIterator</span>

apcu\_enabled
=============

Whether APCu is usable in the current environment

### Description

<span class="type">bool</span> <span
class="methodname">apcu\_enabled</span> ( <span
class="methodparam">void</span> )

Returns whether APCu is usable in the current environment.

### Parameters

This function has no parameters.

### Return Values

Returns **`true`** when APCu is usable in the current environment,
**`false`** otherwise.

apcu\_entry
===========

Atomically fetch or generate a cache entry

### Description

<span class="type">mixed</span> <span
class="methodname">apcu\_entry</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">callable</span>
`$generator`</span> \[, <span class="methodparam"><span
class="type">int</span> `$ttl`<span class="initializer"> =
0</span></span> \] )

Atomically attempts to find `key` in the cache, if it cannot be found
`generator` is called, passing `key` as the only argument. The return
value of the call is then cached with the optionally specified `ttl`,
and returned.

> **Note**: <span class="simpara"> When control enters <span
> class="function">apcu\_entry</span> the lock for the cache is acquired
> exclusively, it is released when control leaves <span
> class="function">apcu\_entry</span>: In effect, this turns the body of
> `generator` into a critical section, disallowing two processes from
> executing the same code paths concurrently. In addition, it prohibits
> the concurrent execution of any other APCu functions, since they will
> acquire the same lock. </span>

**Warning**

The only APCu function that can be called safely by `generator` is <span
class="function">apcu\_entry</span>.

### Parameters

`key`  
Identity of cache entry

`generator`  
A callable that accepts `key` as the only argument and returns the value
to cache.

`ttl`  
Time To Live; store `var` in the cache for `ttl` seconds. After the
`ttl` has passed, the stored variable will be expunged from the cache
(on the next request). If no `ttl` is supplied (or if the `ttl` is *0*),
the value will persist until it is removed from the cache manually, or
otherwise fails to exist in the cache (clear, restart, etc.).

### Return Values

Returns the cached value

### Examples

**Example \#1 An <span class="function">apcu\_entry</span> example**

``` php
<?php
$config = apcu_entry("config", function($key) {
 return [
   "fruit" => apcu_entry("config.fruit", function($key){
     return [
       "apples",
       "pears"
     ];
   }), 
   "people" => apcu_entry("config.people", function($key){
     return [
      "bob",
      "joe",
      "niki"
     ];
   })
 ];
});

var_dump($config);
?>
```

The above example will output:

    array(2) {
      ["fruit"]=>
      array(2) {
        [0]=>
        string(6) "apples"
        [1]=>
        string(5) "pears"
      }
      ["people"]=>
      array(3) {
        [0]=>
        string(3) "bob"
        [1]=>
        string(3) "joe"
        [2]=>
        string(4) "niki"
      }
    }

### See Also

-   <span class="function">apcu\_store</span>
-   <span class="function">apcu\_fetch</span>
-   <span class="function">apcu\_delete</span>

apcu\_exists
============

Checks if entry exists

### Description

<span class="type">mixed</span> <span
class="methodname">apcu\_exists</span> ( <span class="methodparam"><span
class="type">mixed</span> `$keys`</span> )

Checks if one or more APCu entries exist.

### Parameters

`keys`  
A <span class="type">string</span>, or an <span
class="type">array</span> of strings, that contain keys.

### Return Values

Returns **`true`** if the key exists, otherwise **`false`** Or if an
<span class="type">array</span> was passed to `keys`, then an array is
returned that contains all existing keys, or an empty array if none
exist.

### Examples

**Example \#1 <span class="function">apcu\_exists</span> example**

``` php
<?php
$fruit  = 'apple';
$veggie = 'carrot';

apcu_store('foo', $fruit);
apcu_store('bar', $veggie);

if (apcu_exists('foo')) {
    echo "Foo exists: ";
    echo apcu_fetch('foo');
} else {
    echo "Foo does not exist";
}

echo PHP_EOL;
if (apcu_exists('baz')) {
    echo "Baz exists.";
} else {
    echo "Baz does not exist";
}

echo PHP_EOL;

$ret = apcu_exists(array('foo', 'donotexist', 'bar'));
var_dump($ret);

?>
```

The above example will output something similar to:

    Foo exists: apple
    Baz does not exist
    array(2) {
      ["foo"]=>
      bool(true)
      ["bar"]=>
      bool(true)
    }

### See Also

-   <span class="function">apcu\_cache\_info</span>
-   <span class="function">apcu\_fetch</span>

apcu\_fetch
===========

Fetch a stored variable from the cache

### Description

<span class="type">mixed</span> <span
class="methodname">apcu\_fetch</span> ( <span class="methodparam"><span
class="type">mixed</span> `$key`</span> \[, <span
class="methodparam"><span class="type">bool</span> `&$success`</span> \]
)

Fetches an entry from the cache.

### Parameters

`key`  
The `key` used to store the value (with <span
class="function">apcu\_store</span>). If an array is passed then each
element is fetched and returned.

`success`  
Set to **`true`** in success and **`false`** in failure.

### Return Values

The stored variable or array of variables on success; **`false`** on
failure

### Examples

**Example \#1 A <span class="function">apcu\_fetch</span> example**

``` php
<?php
$bar = 'BAR';
apcu_store('foo', $bar);
var_dump(apcu_fetch('foo'));
?>
```

The above example will output:

    string(3) "BAR"

### Changelog

| Version          | Description                        |
|------------------|------------------------------------|
| PECL apcu 3.0.17 | The `success` parameter was added. |

### See Also

-   <span class="function">apcu\_store</span>
-   <span class="function">apcu\_delete</span>
-   <span class="classname">APCUIterator</span>

apcu\_inc
=========

Increase a stored number

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">apcu\_inc</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$step`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `&$success`</span>
\[, <span class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \]\]\] )

Increases a stored number.

### Parameters

`key`  
The key of the value being increased.

`step`  
The step, or value to increase.

`success`  
Optionally pass the success or fail boolean value to this referenced
variable.

`ttl`  
TTL to use if the operation inserts a new value (rather than
incrementing an existing one).

### Return Values

Returns the current value of `key`'s value on success, or **`false`** on
failure

### Changelog

| Version | Description                         |
|---------|-------------------------------------|
| 5.1.12  | The `ttl` parameter has been added. |

### Examples

**Example \#1 <span class="function">apcu\_inc</span> example**

``` php
<?php
echo "Let's do something with success", PHP_EOL;

apcu_store('anumber', 42);

echo apcu_fetch('anumber'), PHP_EOL;

echo apcu_inc('anumber'), PHP_EOL;
echo apcu_inc('anumber', 10), PHP_EOL;
echo apcu_inc('anumber', 10, $success), PHP_EOL;

var_dump($success);

echo "Now, let's fail", PHP_EOL, PHP_EOL;

apcu_store('astring', 'foo');

$ret = apcu_inc('astring', 1, $fail);

var_dump($ret);
var_dump($fail);
?>
```

The above example will output something similar to:

    Let's do something with success
    42
    43
    53
    63
    bool(true)
    Now, let's fail

    bool(false)
    bool(false)

### See Also

-   <span class="function">apcu\_dec</span>

apcu\_key\_info
===============

Get detailed information about the cache key

### Description

<span class="type">array</span> <span
class="methodname">apcu\_key\_info</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

Get detailed information about the cache key

### Parameters

`key`  
Get detailed information about the cache key

### Return Values

null or array info

### Examples

**Example \#1 A <span class="function">apcu\_key\_info</span> example**

``` php
<?php
apcu_add('a','b');
var_dump(apcu_key_info('a'));
?>
```

The above example will output:

    array(7) {
      ["hits"]=>
      int(0)
      ["access_time"]=>
      int(1606701783)
      ["mtime"]=>
      int(1606701783)
      ["creation_time"]=>
      int(1606701783)
      ["deletion_time"]=>
      int(0)
      ["ttl"]=>
      int(0)
      ["refs"]=>
      int(0)
    }

### See Also

-   <span class="function">apcu\_store</span>
-   <span class="function">apcu\_fetch</span>
-   <span class="function">apcu\_delete</span>

apcu\_sma\_info
===============

Retrieves APCu Shared Memory Allocation information

### Description

<span class="type">array</span> <span
class="methodname">apcu\_sma\_info</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$limited`<span
class="initializer"> = **`false`**</span></span> \] )

Retrieves APCu Shared Memory Allocation information.

### Parameters

`limited`  
When set to **`false`** (default) <span
class="function">apcu\_sma\_info</span> will return a detailed
information about each segment.

### Return Values

Array of Shared Memory Allocation data; **`false`** on failure.

### Examples

**Example \#1 A <span class="function">apcu\_sma\_info</span> example**

``` php
<?php
print_r(apcu_sma_info());
?>
```

The above example will output something similar to:

    Array
    (
        [num_seg] => 1
        [seg_size] => 31457280
        [avail_mem] => 31448408
        [block_lists] => Array
            (
                [0] => Array
                    (
                        [0] => Array
                            (
                                [size] => 31448408
                                [offset] => 8864
                            )

                    )

            )

    )

### See Also

-   <a href="/apcu/setup.html#Runtime%20Configuration" class="link">APCu configuration directives</a>

apcu\_store
===========

Cache a variable in the data store

### Description

<span class="type">bool</span> <span
class="methodname">apcu\_store</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$var`</span> \[,
<span class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \] )

<span class="type">array</span> <span
class="methodname">apcu\_store</span> ( <span class="methodparam"><span
class="type">array</span> `$values`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$unused`<span
class="initializer"> = NULL</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \]\] )

Cache a variable in the data store.

> **Note**: <span class="simpara"> Unlike many other mechanisms in PHP,
> variables stored using <span class="function">apcu\_store</span> will
> persist between requests (until the value is removed from the cache).
> </span>

### Parameters

`key`  
Store the variable using this name. `key`s are cache-unique, so storing
a second value with the same `key` will overwrite the original value.

`var`  
The variable to store

`ttl`  
Time To Live; store `var` in the cache for `ttl` seconds. After the
`ttl` has passed, the stored variable will be expunged from the cache
(on the next request). If no `ttl` is supplied (or if the `ttl` is *0*),
the value will persist until it is removed from the cache manually, or
otherwise fails to exist in the cache (clear, restart, etc.).

`values`  
Names in key, variables in value.

### Return Values

Returns **`true`** on success or **`false`** on failure. Second syntax
returns array with error keys.

### Examples

**Example \#1 A <span class="function">apcu\_store</span> example**

``` php
<?php
$bar = 'BAR';
apcu_store('foo', $bar);
var_dump(apcu_fetch('foo'));
?>
```

The above example will output:

    string(3) "BAR"

### See Also

-   <span class="function">apcu\_add</span>
-   <span class="function">apcu\_fetch</span>
-   <span class="function">apcu\_delete</span>

**Table of Contents**

-   [apcu\_add](/ref/apcu.html#apcu_add) — Cache a new variable in the
    data store
-   [apcu\_cache\_info](/ref/apcu.html#apcu_cache_info) — Retrieves
    cached information from APCu's data store
-   [apcu\_cas](/ref/apcu.html#apcu_cas) — Updates an old value with a
    new value
-   [apcu\_clear\_cache](/ref/apcu.html#apcu_clear_cache) — Clears the
    APCu cache
-   [apcu\_dec](/ref/apcu.html#apcu_dec) — Decrease a stored number
-   [apcu\_delete](/ref/apcu.html#apcu_delete) — Removes a stored
    variable from the cache
-   [apcu\_enabled](/ref/apcu.html#apcu_enabled) — Whether APCu is
    usable in the current environment
-   [apcu\_entry](/ref/apcu.html#apcu_entry) — Atomically fetch or
    generate a cache entry
-   [apcu\_exists](/ref/apcu.html#apcu_exists) — Checks if entry exists
-   [apcu\_fetch](/ref/apcu.html#apcu_fetch) — Fetch a stored variable
    from the cache
-   [apcu\_inc](/ref/apcu.html#apcu_inc) — Increase a stored number
-   [apcu\_key\_info](/ref/apcu.html#apcu_key_info) — Get detailed
    information about the cache key
-   [apcu\_sma\_info](/ref/apcu.html#apcu_sma_info) — Retrieves APCu
    Shared Memory Allocation information
-   [apcu\_store](/ref/apcu.html#apcu_store) — Cache a variable in the
    data store

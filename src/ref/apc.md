apc\_add
========

Cache a new variable in the data store

### Description

<span class="type">bool</span> <span class="methodname">apc\_add</span>
( <span class="methodparam"><span class="type">string</span>
`$key`</span> , <span class="methodparam"><span
class="type">mixed</span> `$var`</span> \[, <span
class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \] )

<span class="type">array</span> <span class="methodname">apc\_add</span>
( <span class="methodparam"><span class="type">array</span>
`$values`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$unused`<span class="initializer"> =
NULL</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$ttl`<span class="initializer"> =
0</span></span> \]\] )

Caches a variable in the data store, only if it's not already stored.

> **Note**: <span class="simpara"> Unlike many other mechanisms in PHP,
> variables stored using <span class="function">apc\_add</span> will
> persist between requests (until the value is removed from the cache).
> </span>

### Parameters

`key`  
Store the variable using this name. `key`s are cache-unique, so
attempting to use <span class="function">apc\_add</span> to store data
with a key that already exists will not overwrite the existing data, and
will instead return **`FALSE`**. (This is the only difference between
<span class="function">apc\_add</span> and <span
class="function">apc\_store</span>.)

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

**Example \#1 A <span class="function">apc\_add</span> example**

``` php
<?php
$bar = 'BAR';
apc_add('foo', $bar);
var_dump(apc_fetch('foo'));
echo "\n";
$bar = 'NEVER GETS SET';
apc_add('foo', $bar);
var_dump(apc_fetch('foo'));
echo "\n";
?>
```

The above example will output:

    string(3) "BAR"
    string(3) "BAR"

### See Also

-   <span class="function">apc\_store</span>
-   <span class="function">apc\_fetch</span>
-   <span class="function">apc\_delete</span>

apc\_bin\_dump
==============

Get a binary dump of the given files and user variables

### Description

<span class="type">string</span> <span
class="methodname">apc\_bin\_dump</span> (\[ <span
class="methodparam"><span class="type">array</span> `$files`<span
class="initializer"> = NULL</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$user_vars`<span
class="initializer"> = NULL</span></span> \]\] )

Returns a binary dump of the given files and user variables from the APC
cache. A **`NULL`** for files or user\_vars signals a dump of every
entry, whereas array() will dump nothing.

### Parameters

`files`  
The files. Passing in **`NULL`** signals a dump of every entry, while
passing in <span class="function">array</span> will dump nothing.

`user_vars`  
The user vars. Passing in **`NULL`** signals a dump of every entry,
while passing in <span class="function">array</span> will dump nothing.

### Return Values

Returns a binary dump of the given files and user variables from the APC
cache, **`FALSE`** if APC is not enabled, or **`NULL`** if an unknown
error is encountered.

### See Also

-   <span class="function">apc\_bin\_dumpfile</span>
-   <span class="function">apc\_bin\_load</span>

apc\_bin\_dumpfile
==================

Output a binary dump of cached files and user variables to a file

### Description

<span class="type">int</span> <span
class="methodname">apc\_bin\_dumpfile</span> ( <span
class="methodparam"><span class="type">array</span> `$files`</span> ,
<span class="methodparam"><span class="type">array</span>
`$user_vars`</span> , <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`<span
class="initializer"> = NULL</span></span> \]\] )

Outputs a binary dump of the given files and user variables from the APC
cache to the named file.

### Parameters

`files`  
The file names being dumped.

`user_vars`  
The user variables being dumped.

`filename`  
The filename where the dump is being saved.

`flags`  
Flags passed to the `filename` stream. See the <span
class="function">file\_put\_contents</span> documentation for details.

`context`  
The context passed to the `filename` stream. See the <span
class="function">file\_put\_contents</span> documentation for details.

### Return Values

The number of bytes written to the file, otherwise **`FALSE`** if APC is
not enabled, `filename` is an invalid file name, `filename` can't be
opened, the file dump can't be completed (e.g., the hard drive is out of
disk space), or an unknown error was encountered.

### See Also

-   <span class="function">apc\_bin\_dump</span>
-   <span class="function">apc\_bin\_load</span>

apc\_bin\_load
==============

Load a binary dump into the APC file/user cache

### Description

<span class="type">bool</span> <span
class="methodname">apc\_bin\_load</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \] )

Loads the given binary dump into the APC file/user cache.

### Parameters

`data`  
The binary dump being loaded, likely from <span
class="function">apc\_bin\_dump</span>.

`flags`  
Either **`APC_BIN_VERIFY_CRC32`**, **`APC_BIN_VERIFY_MD5`**, or both.

### Return Values

Returns **`TRUE`** if the binary dump `data` was loaded with success,
otherwise **`FALSE`** is returned. **`FALSE`** is returned if APC is not
enabled, or if the `data` is not a valid APC binary dump (e.g.,
unexpected size).

### Examples

**Example \#1 <span class="function">apc\_bin\_load</span> example**

``` php
<?php
$data = apc_bin_dump(NULL, NULL);
apc_bin_load($data, APC_BIN_VERIFY_MD5 | APC_BIN_VERIFY_CRC32);
?>
```

### See Also

-   <span class="function">apc\_bin\_dump</span>
-   <span class="function">apc\_bin\_loadfile</span>

apc\_bin\_loadfile
==================

Load a binary dump from a file into the APC file/user cache

### Description

<span class="type">bool</span> <span
class="methodname">apc\_bin\_loadfile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">resource</span>
`$context`<span class="initializer"> = NULL</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \]\] )

Loads a binary dump from a file into the APC file/user cache.

### Parameters

`filename`  
The file name containing the dump, likely from <span
class="function">apc\_bin\_dumpfile</span>.

`context`  
The files context.

`flags`  
Either **`APC_BIN_VERIFY_CRC32`**, **`APC_BIN_VERIFY_MD5`**, or both.

### Return Values

Returns **`TRUE`** on success, otherwise **`FALSE`** Reasons it may
return **`FALSE`** include APC is not enabled, `filename` is an invalid
file name or empty, `filename` can't be opened, the file dump can't be
completed, or if the `data` is not a valid APC binary dump (e.g.,
unexpected size).

### See Also

-   <span class="function">apc\_bin\_dumpfile</span>
-   <span class="function">apc\_bin\_load</span>

apc\_cache\_info
================

Retrieves cached information from APC's data store

### Description

<span class="type">array</span> <span
class="methodname">apc\_cache\_info</span> (\[ <span
class="methodparam"><span class="type">string</span> `$cache_type`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$limited`<span
class="initializer"> = **`FALSE`**</span></span> \]\] )

Retrieves cached information and meta-data from APC's data store.

### Parameters

`cache_type`  
If `cache_type` is "*user*", information about the user cache will be
returned.

If `cache_type` is "*filehits*", information about which files have been
served from the bytecode cache for the current request will be returned.
This feature must be enabled at compile time using
**--enable-filehits**.

If an invalid or no `cache_type` is specified, information about the
system cache (cached files) will be returned.

`limited`  
If `limited` is **`TRUE`**, the return value will exclude the individual
list of cache entries. This is useful when trying to optimize calls for
statistics gathering.

### Return Values

Array of cached data (and meta-data) or **`FALSE`** on failure

> **Note**: <span class="simpara"> <span
> class="function">apc\_cache\_info</span> will raise a warning if it is
> unable to retrieve APC cache data. This typically occurs when APC is
> not enabled. </span>

### Changelog

| Version | Description                                                            |
|---------|------------------------------------------------------------------------|
| 3.0.11  | The `limited` parameter was introduced.                                |
| 3.0.16  | The "*filehits*" option for the `cache_type` parameter was introduced. |

### Examples

**Example \#1 A <span class="function">apc\_cache\_info</span> example**

``` php
<?php
print_r(apc_cache_info());
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
                        [filename] => /path/to/apc_test.php
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

-   <a href="/apc/setup.html#Runtime%20Configuration" class="link">APC configuration directives</a>
-   <span class="methodname">APCIterator::getTotalSize</span>
-   <span class="methodname">APCIterator::getTotalHits</span>
-   <span class="methodname">APCIterator::getTotalCount</span>

apc\_cas
========

Updates an old value with a new value

### Description

<span class="type">bool</span> <span class="methodname">apc\_cas</span>
( <span class="methodparam"><span class="type">string</span>
`$key`</span> , <span class="methodparam"><span class="type">int</span>
`$old`</span> , <span class="methodparam"><span class="type">int</span>
`$new`</span> )

<span class="function">apc\_cas</span> updates an already existing
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

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">apc\_cas</span> example**

``` php
<?php
apc_store('foobar', 2);
echo '$foobar = 2', PHP_EOL;
echo '$foobar == 1 ? 2 : 1 = ', (apc_cas('foobar', 1, 2) ? 'ok' : 'fail'), PHP_EOL;
echo '$foobar == 2 ? 1 : 2 = ', (apc_cas('foobar', 2, 1) ? 'ok' : 'fail'), PHP_EOL;

echo '$foobar = ', apc_fetch('foobar'), PHP_EOL;

echo '$f__bar == 1 ? 2 : 1 = ', (apc_cas('f__bar', 1, 2) ? 'ok' : 'fail'), PHP_EOL;

apc_store('perfection', 'xyz');
echo '$perfection == 2 ? 1 : 2 = ', (apc_cas('perfection', 2, 1) ? 'ok' : 'epic fail'), PHP_EOL;

echo '$foobar = ', apc_fetch('foobar'), PHP_EOL;
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

-   <span class="function">apc\_dec</span>
-   <span class="function">apc\_store</span>

apc\_clear\_cache
=================

Clears the APC cache

### Description

<span class="type">bool</span> <span
class="methodname">apc\_clear\_cache</span> (\[ <span
class="methodparam"><span class="type">string</span> `$cache_type`<span
class="initializer"> = ""</span></span> \] )

Clears the user/system cache.

### Parameters

`cache_type`  
If `cache_type` is "*user*", the user cache will be cleared; otherwise,
the system cache (cached files) will be cleared.

### Return Values

Returns **`TRUE`** always

### See Also

-   <span class="function">apc\_cache\_info</span>

apc\_compile\_file
==================

Stores a file in the bytecode cache, bypassing all filters

### Description

<span class="type">mixed</span> <span
class="methodname">apc\_compile\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$atomic`<span class="initializer"> = **`TRUE`**</span></span> \] )

Stores a file in the bytecode cache, bypassing all filters.

### Parameters

`filename`  
Full or relative path to a PHP file that will be compiled and stored in
the bytecode cache.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">apc\_bin\_dumpfile</span>
-   <span class="function">apc\_bin\_loadfile</span>

apc\_dec
========

Decrease a stored number

### Description

<span class="type">int</span> <span class="methodname">apc\_dec</span> (
<span class="methodparam"><span class="type">string</span> `$key`</span>
\[, <span class="methodparam"><span class="type">int</span> `$step`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `&$success`</span>
\]\] )

Decreases a stored integer value.

### Parameters

`key`  
The key of the value being decreased.

`step`  
The step, or value to decrease.

`success`  
Optionally pass the success or fail boolean value to this referenced
variable.

### Return Values

Returns the current value of `key`'s value on success, or **`FALSE`** on
failure

### Examples

**Example \#1 <span class="function">apc\_dec</span> example**

``` php
<?php
echo "Let's do something with success", PHP_EOL;

apc_store('anumber', 42);

echo apc_fetch('anumber'), PHP_EOL;

echo apc_dec('anumber'), PHP_EOL;
echo apc_dec('anumber', 10), PHP_EOL;
echo apc_dec('anumber', 10, $success), PHP_EOL;

var_dump($success);

echo "Now, let's fail", PHP_EOL, PHP_EOL;

apc_store('astring', 'foo');

$ret = apc_dec('astring', 1, $fail);

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

-   <span class="function">apc\_inc</span>

apc\_define\_constants
======================

Defines a set of constants for retrieval and mass-definition

### Description

<span class="type">bool</span> <span
class="methodname">apc\_define\_constants</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">array</span>
`$constants`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$case_sensitive`<span class="initializer"> =
**`TRUE`**</span></span> \] )

<span class="function">define</span> is notoriously slow. Since the main
benefit of APC is to increase the performance of scripts/applications,
this mechanism is provided to streamline the process of mass constant
definition. However, this function does not perform as well as
anticipated.

For a better-performing solution, try the
<a href="https://pecl.php.net/package/hidef" class="link external">» hidef</a>
extension from PECL.

> **Note**: <span class="simpara"> To remove a set of stored constants
> (without clearing the entire cache), an empty array may be passed as
> the `constants` parameter, effectively clearing the stored value(s).
> </span>

### Parameters

`key`  
The `key` serves as the name of the constant set being stored. This
`key` is used to retrieve the stored constants in <span
class="function">apc\_load\_constants</span>.

`constants`  
An associative array of *constant\_name =\> value* pairs. The
*constant\_name* must follow the normal
<a href="/language/constants.html" class="link">constant</a> naming
rules. *value* must evaluate to a scalar value.

`case_sensitive`  
The default behaviour for constants is to be declared case-sensitive;
i.e. *CONSTANT* and *Constant* represent different values. If this
parameter evaluates to **`FALSE`** the constants will be declared as
case-insensitive symbols.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">apc\_define\_constants</span>
example**

``` php
<?php
$constants = array(
    'ONE'   => 1,
    'TWO'   => 2,
    'THREE' => 3,
);
apc_define_constants('numbers', $constants);
echo ONE, TWO, THREE;
?>
```

The above example will output:

    123

### See Also

-   <span class="function">apc\_load\_constants</span>
-   <span class="function">define</span>
-   <span class="function">constant</span>
-   Or
    <a href="/language/constants.html" class="link">the PHP constants reference</a>

apc\_delete\_file
=================

Deletes files from the opcode cache

### Description

<span class="type">mixed</span> <span
class="methodname">apc\_delete\_file</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

Deletes the given files from the opcode cache.

### Parameters

`keys`  
The files to be deleted. Accepts a <span class="type">string</span>,
<span class="type">array</span> of strings, or an <span
class="classname">APCIterator</span> <span class="type">object</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Or if `keys` is
an <span class="type">array</span>, then an empty array is returned on
success, or an array of failed files is returned.

### Examples

**Example \#1 <span class="function">apc\_delete\_file</span> example**

``` php
<?php
$filename = 'file.php';

if (apc_compile_file($filename)) {

    if (apc_delete_file($filename)) {
        echo "Successfully deleted file $filename from APC cache.", PHP_EOL;
    }
}

if (apc_compile_file($filename)) {

    if ($good = apc_delete_file(array($filename, 'donotexist.php'))) {
        var_dump($good);
    }
}

$bad = apc_delete_file('donotexist.php');
var_dump($bad);
?>
```

The above example will output something similar to:

    Successfully deleted file file.php from APC cache.
    [Mon May 24 09:30:33 2010] [apc-warning] Could not stat file donotexist.php, unable to delete from cache. in /tmp/test.php on line 13.
    array(1) {
      [0]=>
      string(14) "donotexist.php"
    }
    [Mon May 24 09:30:33 2010] [apc-warning] Could not stat file donotexist.php, unable to delete from cache. in /tmp/test.php on line 18.
    bool(false)

### See Also

-   <span class="function">apc\_clear\_cache</span>
-   <span class="function">apc\_delete</span>
-   <span class="function">apc\_exists</span>

apc\_delete
===========

Removes a stored variable from the cache

### Description

<span class="type">mixed</span> <span
class="methodname">apc\_delete</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> )

Removes a stored variable from the cache.

### Parameters

`key`  
The `key` used to store the value (with <span
class="function">apc\_store</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">apc\_delete</span> example**

``` php
<?php
$bar = 'BAR';
apc_store('foo', $bar);
apc_delete('foo');
// this is obviously useless in this form
?>
```

### See Also

-   <span class="function">apc\_store</span>
-   <span class="function">apc\_fetch</span>

apc\_exists
===========

Checks if APC key exists

### Description

<span class="type">mixed</span> <span
class="methodname">apc\_exists</span> ( <span class="methodparam"><span
class="type">mixed</span> `$keys`</span> )

Checks if one or more APC keys exist.

### Parameters

`keys`  
A <span class="type">string</span>, or an <span
class="type">array</span> of strings, that contain keys.

### Return Values

Returns **`TRUE`** if the key exists, otherwise **`FALSE`** Or if an
<span class="type">array</span> was passed to `keys`, then an array is
returned that contains all existing keys, or an empty array if none
exist.

### Examples

**Example \#1 <span class="function">apc\_exists</span> example**

``` php
<?php
$fruit  = 'apple';
$veggie = 'carrot';

apc_store('foo', $fruit);
apc_store('bar', $veggie);

if (apc_exists('foo')) {
    echo "Foo exists: ";
    echo apc_fetch('foo');
} else {
    echo "Foo does not exist";
}

echo PHP_EOL;
if (apc_exists('baz')) {
    echo "Baz exists.";
} else {
    echo "Baz does not exist";
}

echo PHP_EOL;

$ret = apc_exists(array('foo', 'donotexist', 'bar'));
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

-   <span class="function">apc\_cache\_info</span>
-   <span class="function">apc\_fetch</span>

apc\_fetch
==========

Fetch a stored variable from the cache

### Description

<span class="type">mixed</span> <span
class="methodname">apc\_fetch</span> ( <span class="methodparam"><span
class="type">mixed</span> `$key`</span> \[, <span
class="methodparam"><span class="type">bool</span> `&$success`</span> \]
)

Fetches a stored variable from the cache.

### Parameters

`key`  
The `key` used to store the value (with <span
class="function">apc\_store</span>). If an array is passed then each
element is fetched and returned.

`success`  
Set to **`TRUE`** in success and **`FALSE`** in failure.

### Return Values

The stored variable or array of variables on success; **`FALSE`** on
failure

### Examples

**Example \#1 A <span class="function">apc\_fetch</span> example**

``` php
<?php
$bar = 'BAR';
apc_store('foo', $bar);
var_dump(apc_fetch('foo'));
?>
```

The above example will output:

    string(3) "BAR"

### Changelog

| Version | Description                        |
|---------|------------------------------------|
| 3.0.17  | The `success` parameter was added. |

### See Also

-   <span class="function">apc\_store</span>
-   <span class="function">apc\_delete</span>
-   <span class="classname">APCIterator</span>

apc\_inc
========

Increase a stored number

### Description

<span class="type">int</span> <span class="methodname">apc\_inc</span> (
<span class="methodparam"><span class="type">string</span> `$key`</span>
\[, <span class="methodparam"><span class="type">int</span> `$step`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `&$success`</span>
\]\] )

Increases a stored number.

### Parameters

`key`  
The key of the value being increased.

`step`  
The step, or value to increase.

`success`  
Optionally pass the success or fail boolean value to this referenced
variable.

### Return Values

Returns the current value of `key`'s value on success, or **`FALSE`** on
failure

### Examples

**Example \#1 <span class="function">apc\_inc</span> example**

``` php
<?php
echo "Let's do something with success", PHP_EOL;

apc_store('anumber', 42);

echo apc_fetch('anumber'), PHP_EOL;

echo apc_inc('anumber'), PHP_EOL;
echo apc_inc('anumber', 10), PHP_EOL;
echo apc_inc('anumber', 10, $success), PHP_EOL;

var_dump($success);

echo "Now, let's fail", PHP_EOL, PHP_EOL;

apc_store('astring', 'foo');

$ret = apc_inc('astring', 1, $fail);

var_dump($ret);
var_dump($fail);
?>
```

The above example will output something similar to:

    42
    43
    53
    63
    bool(true)
    Now, let's fail

    bool(false)
    bool(false)

### See Also

-   <span class="function">apc\_dec</span>

apc\_load\_constants
====================

Loads a set of constants from the cache

### Description

<span class="type">bool</span> <span
class="methodname">apc\_load\_constants</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$case_sensitive`<span class="initializer"> = **`TRUE`**</span></span>
\] )

Loads a set of constants from the cache.

### Parameters

`key`  
The name of the constant set (that was stored with <span
class="function">apc\_define\_constants</span>) to be retrieved.

`case_sensitive`  
The default behaviour for constants is to be declared case-sensitive;
i.e. *CONSTANT* and *Constant* represent different values. If this
parameter evaluates to **`FALSE`** the constants will be declared as
case-insensitive symbols.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">apc\_load\_constants</span>
example**

``` php
<?php
$constants = array(
    'ONE'   => 1,
    'TWO'   => 2,
    'THREE' => 3,
);
apc_define_constants('numbers', $constants);
apc_load_constants('numbers');
echo ONE, TWO, THREE;
?>
```

The above example will output:

    123

### See Also

-   <span class="function">apc\_define\_constants</span>
-   <span class="function">define</span>
-   <span class="function">constant</span>
-   Or
    <a href="/language/constants.html" class="link">the PHP constants reference</a>

apc\_sma\_info
==============

Retrieves APC's Shared Memory Allocation information

### Description

<span class="type">array</span> <span
class="methodname">apc\_sma\_info</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$limited`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Retrieves APC's Shared Memory Allocation information.

### Parameters

`limited`  
When set to **`FALSE`** (default) <span
class="function">apc\_sma\_info</span> will return a detailed
information about each segment.

### Return Values

Array of Shared Memory Allocation data; **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">apc\_sma\_info</span> example**

``` php
<?php
print_r(apc_sma_info());
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

-   <a href="/apc/setup.html#Runtime%20Configuration" class="link">APC configuration directives</a>

apc\_store
==========

Cache a variable in the data store

### Description

<span class="type">bool</span> <span
class="methodname">apc\_store</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$var`</span> \[,
<span class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \] )

<span class="type">array</span> <span
class="methodname">apc\_store</span> ( <span class="methodparam"><span
class="type">array</span> `$values`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$unused`<span
class="initializer"> = NULL</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$ttl`<span
class="initializer"> = 0</span></span> \]\] )

Cache a variable in the data store.

> **Note**: <span class="simpara"> Unlike many other mechanisms in PHP,
> variables stored using <span class="function">apc\_store</span> will
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

Returns **`TRUE`** on success or **`FALSE`** on failure. Second syntax
returns array with error keys.

### Examples

**Example \#1 A <span class="function">apc\_store</span> example**

``` php
<?php
$bar = 'BAR';
apc_store('foo', $bar);
var_dump(apc_fetch('foo'));
?>
```

The above example will output:

    string(3) "BAR"

### See Also

-   <span class="function">apc\_add</span>
-   <span class="function">apc\_fetch</span>
-   <span class="function">apc\_delete</span>

**Table of Contents**

-   [apc\_add](/ref/apc.html#apc_add) — Cache a new variable in the data
    store
-   [apc\_bin\_dump](/ref/apc.html#apc_bin_dump) — Get a binary dump of
    the given files and user variables
-   [apc\_bin\_dumpfile](/ref/apc.html#apc_bin_dumpfile) — Output a
    binary dump of cached files and user variables to a file
-   [apc\_bin\_load](/ref/apc.html#apc_bin_load) — Load a binary dump
    into the APC file/user cache
-   [apc\_bin\_loadfile](/ref/apc.html#apc_bin_loadfile) — Load a binary
    dump from a file into the APC file/user cache
-   [apc\_cache\_info](/ref/apc.html#apc_cache_info) — Retrieves cached
    information from APC's data store
-   [apc\_cas](/ref/apc.html#apc_cas) — Updates an old value with a new
    value
-   [apc\_clear\_cache](/ref/apc.html#apc_clear_cache) — Clears the APC
    cache
-   [apc\_compile\_file](/ref/apc.html#apc_compile_file) — Stores a file
    in the bytecode cache, bypassing all filters
-   [apc\_dec](/ref/apc.html#apc_dec) — Decrease a stored number
-   [apc\_define\_constants](/ref/apc.html#apc_define_constants) —
    Defines a set of constants for retrieval and mass-definition
-   [apc\_delete\_file](/ref/apc.html#apc_delete_file) — Deletes files
    from the opcode cache
-   [apc\_delete](/ref/apc.html#apc_delete) — Removes a stored variable
    from the cache
-   [apc\_exists](/ref/apc.html#apc_exists) — Checks if APC key exists
-   [apc\_fetch](/ref/apc.html#apc_fetch) — Fetch a stored variable from
    the cache
-   [apc\_inc](/ref/apc.html#apc_inc) — Increase a stored number
-   [apc\_load\_constants](/ref/apc.html#apc_load_constants) — Loads a
    set of constants from the cache
-   [apc\_sma\_info](/ref/apc.html#apc_sma_info) — Retrieves APC's
    Shared Memory Allocation information
-   [apc\_store](/ref/apc.html#apc_store) — Cache a variable in the data
    store

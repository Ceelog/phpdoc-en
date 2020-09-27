assert\_options
===============

Set/get the various assert flags

### Description

<span class="type">mixed</span> <span
class="methodname">assert\_options</span> ( <span
class="methodparam"><span class="type">int</span> `$what`</span> \[,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> \] )

Set the various <span class="function">assert</span> control options or
just query their current settings.

> **Note**: <span class="simpara"> As of PHP 7.0.0, the use of <span
> class="function">assert\_options</span> is discouraged in favor of
> setting and getting the `php.ini` directives
> <a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a>
> and <a href="/info/setup.html#" class="link">assert.exception</a> with
> <span class="function">ini\_set</span> and <span
> class="function">ini\_get</span>, respectively. </span>

### Parameters

`what`  
| Option              | INI Setting        | Default value | Description                                                     |
|---------------------|--------------------|---------------|-----------------------------------------------------------------|
| ASSERT\_ACTIVE      | assert.active      | 1             | enable <span class="function">assert</span> evaluation          |
| ASSERT\_WARNING     | assert.warning     | 1             | issue a PHP warning for each failed assertion                   |
| ASSERT\_BAIL        | assert.bail        | 0             | terminate execution on failed assertions                        |
| ASSERT\_QUIET\_EVAL | assert.quiet\_eval | 0             | disable error\_reporting during assertion expression evaluation |
| ASSERT\_CALLBACK    | assert.callback    | (**`NULL`**)  | Callback to call on failed assertions                           |

`value`  
An optional new value for the option.

The callback function set via **`ASSERT_CALLBACK`** or assert.callback
should have the following signature:

<span class="type">void</span> <span
class="methodname">assert\_callback</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> ,
<span class="methodparam"><span class="type">int</span> `$line`</span> ,
<span class="methodparam"><span class="type">string</span>
`$assertion`</span> \[, <span class="methodparam"><span
class="type">string</span> `$description`</span> \] )

`file`  
<span class="simpara"> The file where <span
class="function">assert</span> has been called. </span>

`line`  
<span class="simpara"> The line where <span
class="function">assert</span> has been called. </span>

`assertion`  
<span class="simpara"> The assertion that has been passed to <span
class="function">assert</span>, converted to a string. </span>

`description`  
<span class="simpara"> The description that has been passed to <span
class="function">assert</span>. </span>

Passing an empty string as `value` resets the assert callback.

### Return Values

Returns the original setting of any option or **`FALSE`** on errors.

### Examples

**Example \#1 <span class="function">assert\_options</span> example**

``` php
<?php
// This is our function to handle 
// assert failures
function assert_failure($file, $line, $assertion, $message)
{
    echo "The assertion $assertion in $file on line $line has failed: $message";
}

// This is our test function
function test_assert($parameter)
{
    assert(is_bool($parameter));
}

// Set our assert options
assert_options(ASSERT_ACTIVE,   true);
assert_options(ASSERT_BAIL,     true);
assert_options(ASSERT_WARNING,  false);
assert_options(ASSERT_CALLBACK, 'assert_failure');

// Make an assert that would fail
test_assert(1);

// This is never reached due to ASSERT_BAIL 
// being true
echo 'Never reached';
?>
```

### See Also

-   <span class="function">assert</span>

assert
======

Checks if assertion is **`FALSE`**

### Description

PHP 5 and 7

<span class="type">bool</span> <span class="methodname">assert</span> (
<span class="methodparam"><span class="type">mixed</span>
`$assertion`</span> \[, <span class="methodparam"><span
class="type">string</span> `$description`</span> \] )

PHP 7

<span class="type">bool</span> <span class="methodname">assert</span> (
<span class="methodparam"><span class="type">mixed</span>
`$assertion`</span> \[, <span class="methodparam"><span
class="type">Throwable</span> `$exception`</span> \] )

<span class="function">assert</span> will check the given `assertion`
and take appropriate action if its result is **`FALSE`**.

#### Traditional assertions (PHP 5 and 7)

If the `assertion` is given as a string it will be evaluated as PHP code
by <span class="function">assert</span>. If you pass a boolean condition
as `assertion`, this condition will not show up as parameter to the
assertion function which you may have defined with <span
class="function">assert\_options</span>. The condition is converted to a
string before calling that handler function, and the boolean **`FALSE`**
is converted as the empty string.

Assertions should be used as a debugging feature only. You may use them
for sanity-checks that test for conditions that should always be
**`TRUE`** and that indicate some programming errors if not or to check
for the presence of certain features like extension functions or certain
system limits and features.

Assertions should not be used for normal runtime operations like input
parameter checks. As a rule of thumb your code should always be able to
work correctly if assertion checking is not activated.

The behavior of <span class="function">assert</span> may be configured
by <span class="function">assert\_options</span> or by .ini-settings
described in that functions manual page.

The <span class="function">assert\_options</span> function and/or
**`ASSERT_CALLBACK`** configuration directive allow a callback function
to be set to handle failed assertions.

<span class="function">assert</span> callbacks are particularly useful
for building automated test suites because they allow you to easily
capture the code passed to the assertion, along with information on
where the assertion was made. While this information can be captured via
other methods, using assertions makes it much faster and easier!

The callback function should accept three arguments. The first argument
will contain the file the assertion failed in. The second argument will
contain the line the assertion failed on and the third argument will
contain the expression that failed (if any — literal values such as 1 or
"two" will not be passed via this argument). Users of PHP 5.4.8 and
later may also provide a fourth optional argument, which will contain
the `description` given to <span class="function">assert</span>, if it
was set.

#### Expectations (PHP 7 only)

<span class="function">assert</span> is a language construct in PHP 7,
allowing for the definition of expectations: assertions that take effect
in development and testing environments, but are optimised away to have
zero cost in production.

While <span class="function">assert\_options</span> can still be used to
control behaviour as described above for backward compatibility reasons,
PHP 7 only code should use the two new configuration directives to
control the behaviour of <span class="function">assert</span> and not
call <span class="function">assert\_options</span>.

<table>
<caption> <strong>PHP 7 configuration directives for <span class="function">assert</span></strong> </caption>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Directive</th>
<th>Default value</th>
<th>Possible values</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a></td>
<td><em>1</em></td>
<td><ul>
<li><em>1</em>: generate and execute code (development mode)</li>
<li><em>0</em>: generate code but jump around it at runtime</li>
<li><em>-1</em>: do not generate code (production mode)</li>
</ul></td>
</tr>
<tr class="even">
<td><a href="/info/setup.html#" class="link">assert.exception</a></td>
<td><em>0</em></td>
<td><ul>
<li><em>1</em>: throw when the assertion fails, either by throwing the object provided as the <code class="parameter">exception</code> or by throwing a new <span class="classname">AssertionError</span> object if <code class="parameter">exception</code> wasn't provided</li>
<li><em>0</em>: use or generate a <span class="classname">Throwable</span> as described above, but only generate a warning based on that object rather than throwing it (compatible with PHP 5 behaviour)</li>
</ul></td>
</tr>
</tbody>
</table>

### Parameters

`assertion`  
The assertion. In PHP 5, this must be either a <span
class="type">string</span> to be evaluated or a <span
class="type">boolean</span> to be tested. In PHP 7, this may also be any
expression that returns a value, which will be executed and the result
used to indicate whether the assertion succeeded or failed.

**Warning**
Using <span class="type">string</span> as the `assertion` is
*DEPRECATED* as of PHP 7.2.

`description`  
An optional description that will be included in the failure message if
the `assertion` fails. From PHP 7, if no description is provided, a
default description equal to the source code for the invocation of <span
class="function">assert</span> is provided.

`exception`  
In PHP 7, the second parameter can be a <span
class="classname">Throwable</span> object instead of a descriptive <span
class="type">string</span>, in which case this is the object that will
be thrown if the assertion fails and the
<a href="/info/setup.html#" class="link">assert.exception</a>
configuration directive is enabled.

### Return Values

**`FALSE`** if the assertion is false, **`TRUE`** otherwise.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                            |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | Usage of a <span class="type">string</span> as the `assertion` became deprecated. It now emits an **`E_DEPRECATED`** notice when both <a href="/info/setup.html#" class="link">assert.active</a> and <a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a> are set to *1*.                     |
| 7.0.0   | <span class="function">assert</span> is now a language construct and not a function. `assertion` can now be an expression. The second parameter is now interpreted either as an `exception` (if a <span class="classname">Throwable</span> object is given), or as the `description` supported from PHP 5.4.8 onwards. |

### Examples

#### Traditional assertions (PHP 5 and 7)

**Example \#1 Handle a failed assertion with a custom handler**

``` php
<?php
// Active assert and make it quiet
assert_options(ASSERT_ACTIVE, 1);
assert_options(ASSERT_WARNING, 0);
assert_options(ASSERT_QUIET_EVAL, 1);

// Create a handler function
function my_assert_handler($file, $line, $code)
{
    echo "<hr>Assertion Failed:
        File '$file'<br />
        Line '$line'<br />
        Code '$code'<br /><hr />";
}

// Set up the callback
assert_options(ASSERT_CALLBACK, 'my_assert_handler');

// Make an assertion that should fail
assert('mysql_query("")');
?>
```

**Example \#2 Using a custom handler to print a description**

``` php
<?php
// Active assert and make it quiet
assert_options(ASSERT_ACTIVE, 1);
assert_options(ASSERT_WARNING, 0);
assert_options(ASSERT_QUIET_EVAL, 1);

// Create a handler function
function my_assert_handler($file, $line, $code, $desc = null)
{
    echo "Assertion failed at $file:$line: $code";
    if ($desc) {
        echo ": $desc";
    }
    echo "\n";
}

// Set up the callback
assert_options(ASSERT_CALLBACK, 'my_assert_handler');

// Make an assertion that should fail
assert('2 < 1');
assert('2 < 1', 'Two is less than one');
?>
```

The above example will output:

     Assertion failed at test.php:21: 2 < 1
     Assertion failed at test.php:22: 2 < 1: Two is less than one
     

#### Expectations (PHP 7 only)

**Example \#3 Expectations without a custom exception**

``` php
<?php
assert(true == false);
echo 'Hi!';
?>
```

With
<a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a>
set to 0, the above example will output:

    Hi!

With
<a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a>
set to 1 and
<a href="/info/setup.html#" class="link">assert.exception</a> set to 0,
the above example will output:

    Warning: assert(): assert(true == false) failed in - on line 2
    Hi!

With
<a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a>
set to 1 and
<a href="/info/setup.html#" class="link">assert.exception</a> set to 1,
the above example will output:

    Fatal error: Uncaught AssertionError: assert(true == false) in -:2
    Stack trace:
    #0 -(2): assert(false, 'assert(true == ...')
    #1 {main}
      thrown in - on line 2

**Example \#4 Expectations with a custom exception**

``` php
<?php
class CustomError extends AssertionError {}

assert(true == false, new CustomError('True is not false!'));
echo 'Hi!';
?>
```

With
<a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a>
set to 0, the above example will output:

    Hi!

With
<a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a>
set to 1 and
<a href="/info/setup.html#" class="link">assert.exception</a> set to 0,
the above example will output:

    Warning: assert(): CustomError: True is not false! in -:4
    Stack trace:
    #0 {main} failed in - on line 4
    Hi!

With
<a href="/ini/core.html#ini.zend.assertions" class="link">zend.assertions</a>
set to 1 and
<a href="/info/setup.html#" class="link">assert.exception</a> set to 1,
the above example will output:

    Fatal error: Uncaught CustomError: True is not false! in -:4
    Stack trace:
    #0 {main}
      thrown in - on line 4

### See Also

-   <span class="function">assert\_options</span>

cli\_get\_process\_title
========================

Returns the current process title

### Description

<span class="type">string</span> <span
class="methodname">cli\_get\_process\_title</span> ( <span
class="methodparam">void</span> )

Returns the current process title, as set by <span
class="function">cli\_set\_process\_title</span>. Note that this may not
exactly match what is shown in **ps** or **top**, depending on your
operating system.

This function is available only in
<a href="/features/commandline.html" class="link">CLI</a> mode.

### Parameters

This function has no parameters.

### Return Values

Return a string with the current process title or **`NULL`** on error.

### Errors/Exceptions

An **`E_WARNING`** will be generated if the operating system is
unsupported.

### Examples

**Example \#1 <span class="function">cli\_get\_process\_title</span>
example**

``` php
<?php
echo "Process title: " . cli_get_process_title() . "\n";
?>
```

### See Also

-   <span class="function">cli\_set\_process\_title</span>

cli\_set\_process\_title
========================

Sets the process title

### Description

<span class="type">bool</span> <span
class="methodname">cli\_set\_process\_title</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> )

Sets the process title visible in tools such as **top** and **ps**. This
function is available only in
<a href="/features/commandline.html" class="link">CLI</a> mode.

### Parameters

`title`  
The new title.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

An **`E_WARNING`** will be generated if the operating system is
unsupported.

### Examples

**Example \#1 <span class="function">cli\_set\_process\_title</span>
example**

``` php
<?php
$title = "My Amazing PHP Script";
$pid = getmypid(); // you can use this to see your process title in ps

if (!cli_set_process_title($title)) {
    echo "Unable to set process title for PID $pid...\n";
    exit(1);
} else {
    echo "The process title '$title' for PID $pid has been set for your process!\n";
    sleep(5);
}
?>
```

### See Also

-   <span class="function">cli\_get\_process\_title</span>
-   <span class="function">setproctitle</span>

dl
==

Loads a PHP extension at runtime

### Description

<span class="type">bool</span> <span class="methodname">dl</span> (
<span class="methodparam"><span class="type">string</span>
`$library`</span> )

Loads the PHP extension given by the parameter `library`.

Use <span class="function">extension\_loaded</span> to test whether a
given extension is already available or not. This works on both built-in
extensions and dynamically loaded ones (either through `php.ini` or
<span class="function">dl</span>).

**Warning**

This function was removed from most SAPIs in PHP 5.3.0, and was removed
from PHP-FPM in PHP 7.0.0.

### Parameters

`library`  
This parameter is *only* the filename of the extension to load which
also depends on your platform. For example, the
<a href="/ref/sockets.html" class="link">sockets</a> extension (if
compiled as a shared module, not the default!) would be called
`sockets.so` on Unix platforms whereas it is called `php_sockets.dll` on
the Windows platform.

The directory where the extension is loaded from depends on your
platform:

Windows - If not explicitly set in the `php.ini`, the extension is
loaded from `C:\php5\` by default.

Unix - If not explicitly set in the `php.ini`, the default extension
directory depends on

-   <span class="simpara"> whether PHP has been built with
    *--enable-debug* or not </span>
-   <span class="simpara"> whether PHP has been built with
    (experimental) ZTS (Zend Thread Safety) support or not </span>
-   <span class="simpara"> the current internal *ZEND\_MODULE\_API\_NO*
    (Zend internal module API number, which is basically the date on
    which a major module API change happened, e.g. *20010901*) </span>

Taking into account the above, the directory then defaults to
*\<install-dir\>/lib/php/extensions/
\<debug-or-not\>-\<zts-or-not\>-ZEND\_MODULE\_API\_NO*, e.g.
`/usr/local/php/lib/php/extensions/debug-non-zts-20010901` or
`/usr/local/php/lib/php/extensions/no-debug-zts-20010901`.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. If the
functionality of loading modules is not available or has been disabled
(either by setting
<a href="/info/setup.html#" class="link">enable_dl</a> off or by
enabling
<a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>
in `php.ini`) an **`E_ERROR`** is emitted and execution is stopped. If
<span class="function">dl</span> fails because the specified library
couldn't be loaded, in addition to **`FALSE`** an **`E_WARNING`**
message is emitted.

### Examples

**Example \#1 <span class="function">dl</span> examples**

``` php
<?php
// Example loading an extension based on OS
if (!extension_loaded('sqlite')) {
    if (strtoupper(substr(PHP_OS, 0, 3)) === 'WIN') {
        dl('php_sqlite.dll');
    } else {
        dl('sqlite.so');
    }
}

// Or using PHP_SHLIB_SUFFIX constant
if (!extension_loaded('sqlite')) {
    $prefix = (PHP_SHLIB_SUFFIX === 'dll') ? 'php_' : '';
    dl($prefix . 'sqlite.' . PHP_SHLIB_SUFFIX);
}
?>
```

### Notes

> **Note**:
>
> <span class="function">dl</span> is *not* supported when PHP is built
> with ZTS support. Use the
> <a href="/ini/core.html#ini.extension" class="link">Extension Loading Directives</a>
> instead.

> **Note**:
>
> <span class="function">dl</span> is case sensitive on Unix platforms.

> **Note**: <span class="simpara">This function is disabled when PHP is
> running in
> <a href="/features/safe-mode.html" class="link">safe mode</a>.</span>

### See Also

-   <a href="/ini/core.html#ini.extension" class="link">Extension Loading Directives</a>
-   <span class="function">extension\_loaded</span>

extension\_loaded
=================

Find out whether an extension is loaded

### Description

<span class="type">bool</span> <span
class="methodname">extension\_loaded</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Finds out whether the extension is loaded.

### Parameters

`name`  
The extension name. This parameter is case-insensitive.

You can see the names of various extensions by using <span
class="function">phpinfo</span> or if you're using the *CGI* or *CLI*
version of PHP you can use the **-m** switch to list all available
extensions:

    $ php -m
    [PHP Modules]
    xml
    tokenizer
    standard
    sockets
    session
    posix
    pcre
    overload
    mysql
    mbstring
    ctype

    [Zend Modules]

### Return Values

Returns **`TRUE`** if the extension identified by `name` is loaded,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">extension\_loaded</span> example**

``` php
<?php
if (!extension_loaded('gd')) {
    if (!dl('gd.so')) {
        exit;
    }
}
?>
```

### See Also

-   <span class="function">get\_loaded\_extensions</span>
-   <span class="function">get\_extension\_funcs</span>
-   <span class="function">phpinfo</span>
-   <span class="function">dl</span>
-   <span class="function">function\_exists</span>

gc\_collect\_cycles
===================

Forces collection of any existing garbage cycles

### Description

<span class="type">int</span> <span
class="methodname">gc\_collect\_cycles</span> ( <span
class="methodparam">void</span> )

Forces collection of any existing garbage cycles.

### Parameters

This function has no parameters.

### Return Values

Returns number of collected cycles.

### See Also

-   <a href="/features/gc.html" class="link">Garbage Collection</a>

gc\_disable
===========

Deactivates the circular reference collector

### Description

<span class="type">void</span> <span
class="methodname">gc\_disable</span> ( <span
class="methodparam">void</span> )

Deactivates the circular reference collector, setting
<a href="/info/setup.html#" class="link">zend.enable_gc</a> to *0*.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### See Also

-   <a href="/features/gc.html" class="link">Garbage Collection</a>

gc\_enable
==========

Activates the circular reference collector

### Description

<span class="type">void</span> <span
class="methodname">gc\_enable</span> ( <span
class="methodparam">void</span> )

Activates the circular reference collector, setting
<a href="/info/setup.html#" class="link">zend.enable_gc</a> to *1*.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### See Also

-   <a href="/features/gc.html" class="link">Garbage Collection</a>

gc\_enabled
===========

Returns status of the circular reference collector

### Description

<span class="type">bool</span> <span
class="methodname">gc\_enabled</span> ( <span
class="methodparam">void</span> )

Returns status of the circular reference collector.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the garbage collector is enabled, **`FALSE`**
otherwise.

### Examples

**Example \#1 A <span class="function">gc\_enabled</span> example**

``` php
<?php
if(gc_enabled()) gc_collect_cycles();
?>
```

### See Also

-   <a href="/features/gc.html" class="link">Garbage Collection</a>

gc\_mem\_caches
===============

Reclaims memory used by the Zend Engine memory manager

### Description

<span class="type">int</span> <span
class="methodname">gc\_mem\_caches</span> ( <span
class="methodparam">void</span> )

Reclaims memory used by the Zend Engine memory manager.

### Parameters

This function has no parameters.

### Return Values

Returns the number of bytes freed.

### See Also

-   <a href="/features/gc.html" class="link">Garbage Collection</a>

gc\_status
==========

Gets information about the garbage collector

### Description

<span class="type">array</span> <span
class="methodname">gc\_status</span> ( <span
class="methodparam">void</span> )

Gets information about the current state of the garbage collector.

### Parameters

This function has no parameters.

### Return Values

Returns an associative array with the following elements:

-   <span class="simpara"> *"runs"* </span>
-   <span class="simpara"> *"collected"* </span>
-   <span class="simpara"> *"threshold"* </span>
-   <span class="simpara"> *"roots"* </span>

### Examples

**Example \#1 <span class="function">gc\_status</span> Usage**

``` php
<?php

// create object tree that needs gc collection
$a = new stdClass();
$a->b = [];
for ($i = 0; $i < 100000; $i++) {
    $b = new stdClass();
    $b->a = $a;
    $a->b[] = $b;
}
unset($a);
unset($b);
gc_collect_cycles();

var_dump(gc_status());
```

The above example will output something similar to:

    array(4) {
      ["runs"]=>
      int(5)
      ["collected"]=>
      int(100002)
      ["threshold"]=>
      int(50001)
      ["roots"]=>
      int(0)
    }

### See Also

-   <a href="/features/gc.html" class="link">Garbage Collection</a>

get\_cfg\_var
=============

Gets the value of a PHP configuration option

### Description

<span class="type">mixed</span> <span
class="methodname">get\_cfg\_var</span> ( <span
class="methodparam"><span class="type">string</span> `$option`</span> )

Gets the value of a PHP configuration `option`.

This function will not return configuration information set when the PHP
was compiled, or read from an Apache configuration file.

To check whether the system is using a
<a href="/configuration/file.html" class="link">configuration file</a>,
try retrieving the value of the cfg\_file\_path configuration setting.
If this is available, a configuration file is being used.

### Parameters

`option`  
The configuration option name.

### Return Values

Returns the current value of the PHP configuration variable specified by
`option`, or **`FALSE`** if an error occurs.

### See Also

-   <span class="function">ini\_get</span>
-   <span class="function">ini\_get\_all</span>

get\_current\_user
==================

Gets the name of the owner of the current PHP script

### Description

<span class="type">string</span> <span
class="methodname">get\_current\_user</span> ( <span
class="methodparam">void</span> )

Returns the name of the owner of the current PHP script.

### Return Values

Returns the username as a string.

### Examples

**Example \#1 <span class="function">get\_current\_user</span> example**

``` php
<?php
echo 'Current script owner: ' . get_current_user();
?>
```

The above example will output something similar to:

    Current script owner: SYSTEM

### See Also

-   <span class="function">getmyuid</span>
-   <span class="function">getmygid</span>
-   <span class="function">getmypid</span>
-   <span class="function">getmyinode</span>
-   <span class="function">getlastmod</span>

get\_defined\_constants
=======================

Returns an associative array with the names of all the constants and
their values

### Description

<span class="type">array</span> <span
class="methodname">get\_defined\_constants</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$categorize`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Returns the names and values of all the constants currently defined.
This includes those created by extensions as well as those created with
the <span class="function">define</span> function.

### Parameters

`categorize`  
Causing this function to return a multi-dimensional array with
categories in the keys of the first dimension and constants and their
values in the second dimension.

``` php
<?php
define("MY_CONSTANT", 1);
print_r(get_defined_constants(true));
?>
```

The above example will output something similar to:

    Array
    (
        [Core] => Array
            (
                [E_ERROR] => 1
                [E_WARNING] => 2
                [E_PARSE] => 4
                [E_NOTICE] => 8
                [E_CORE_ERROR] => 16
                [E_CORE_WARNING] => 32
                [E_COMPILE_ERROR] => 64
                [E_COMPILE_WARNING] => 128
                [E_USER_ERROR] => 256
                [E_USER_WARNING] => 512
                [E_USER_NOTICE] => 1024
                [E_ALL] => 2047
                [TRUE] => 1
            )

        [pcre] => Array
            (
                [PREG_PATTERN_ORDER] => 1
                [PREG_SET_ORDER] => 2
                [PREG_OFFSET_CAPTURE] => 256
                [PREG_SPLIT_NO_EMPTY] => 1
                [PREG_SPLIT_DELIM_CAPTURE] => 2
                [PREG_SPLIT_OFFSET_CAPTURE] => 4
                [PREG_GREP_INVERT] => 1
            )

        [user] => Array
            (
                [MY_CONSTANT] => 1
            )

    )

### Return Values

Returns an array of constant name =\> constant value array, optionally
groupped by extension name registering the constant.

### Examples

**Example \#1 <span class="function">get\_defined\_constants</span>
Example**

``` php
<?php
print_r(get_defined_constants());
?>
```

The above example will output something similar to:

    Array
    (
        [E_ERROR] => 1
        [E_WARNING] => 2
        [E_PARSE] => 4
        [E_NOTICE] => 8
        [E_CORE_ERROR] => 16
        [E_CORE_WARNING] => 32
        [E_COMPILE_ERROR] => 64
        [E_COMPILE_WARNING] => 128
        [E_USER_ERROR] => 256
        [E_USER_WARNING] => 512
        [E_USER_NOTICE] => 1024
        [E_ALL] => 2047
        [TRUE] => 1
    )

### See Also

-   <span class="function">defined</span>
-   <span class="function">get\_loaded\_extensions</span>
-   <span class="function">get\_defined\_functions</span>
-   <span class="function">get\_defined\_vars</span>

get\_extension\_funcs
=====================

Returns an array with the names of the functions of a module

### Description

<span class="type">array</span> <span
class="methodname">get\_extension\_funcs</span> ( <span
class="methodparam"><span class="type">string</span>
`$module_name`</span> )

This function returns the names of all the functions defined in the
module indicated by `module_name`.

### Parameters

`module_name`  
The module name.

> **Note**:
>
> This parameter must be in *lowercase*.

### Return Values

Returns an array with all the functions, or **`FALSE`** if `module_name`
is not a valid extension.

### Examples

**Example \#1 Prints the XML functions**

``` php
<?php
print_r(get_extension_funcs("xml"));
?>
```

The above example will output something similar to:

    Array
    (
        [0] => xml_parser_create
        [1] => xml_parser_create_ns
        [2] => xml_set_object
        [3] => xml_set_element_handler
        [4] => xml_set_character_data_handler
        [5] => xml_set_processing_instruction_handler
        [6] => xml_set_default_handler
        [7] => xml_set_unparsed_entity_decl_handler
        [8] => xml_set_notation_decl_handler
        [9] => xml_set_external_entity_ref_handler
        [10] => xml_set_start_namespace_decl_handler
        [11] => xml_set_end_namespace_decl_handler
        [12] => xml_parse
        [13] => xml_parse_into_struct
        [14] => xml_get_error_code
        [15] => xml_error_string
        [16] => xml_get_current_line_number
        [17] => xml_get_current_column_number
        [18] => xml_get_current_byte_index
        [19] => xml_parser_free
        [20] => xml_parser_set_option
        [21] => xml_parser_get_option
        [22] => utf8_encode
        [23] => utf8_decode
    )

### See Also

-   <span class="function">get\_loaded\_extensions</span>
-   <span class="methodname">ReflectionExtension::getFunctions</span>

get\_include\_path
==================

Gets the current include\_path configuration option

### Description

<span class="type">string</span> <span
class="methodname">get\_include\_path</span> ( <span
class="methodparam">void</span> )

Gets the current
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
configuration option value.

### Return Values

Returns the path, as a string.

### Examples

**Example \#1 <span class="function">get\_include\_path</span> example**

``` php
<?php
echo get_include_path();

// Or using ini_get()
echo ini_get('include_path');
?>
```

### See Also

-   <span class="function">ini\_get</span>
-   <span class="function">restore\_include\_path</span>
-   <span class="function">set\_include\_path</span>
-   <span class="function">include</span>

get\_included\_files
====================

Returns an array with the names of included or required files

### Description

<span class="type">array</span> <span
class="methodname">get\_included\_files</span> ( <span
class="methodparam">void</span> )

Gets the names of all files that have been included using <span
class="function">include</span>, <span
class="function">include\_once</span>, <span
class="function">require</span> or <span
class="function">require\_once</span>.

### Return Values

Returns an array of the names of all files.

The script originally called is considered an "included file," so it
will be listed together with the files referenced by <span
class="function">include</span> and family.

Files that are included or required multiple times only show up once in
the returned array.

### Examples

**Example \#1 <span class="function">get\_included\_files</span>
example**

``` php
<?php
// This file is abc.php

include 'test1.php';
include_once 'test2.php';
require 'test3.php';
require_once 'test4.php';

$included_files = get_included_files();

foreach ($included_files as $filename) {
    echo "$filename\n";
}

?>
```

The above example will output:

    /path/to/abc.php
    /path/to/test1.php
    /path/to/test2.php
    /path/to/test3.php
    /path/to/test4.php

### See Also

-   <span class="function">include</span>
-   <span class="function">include\_once</span>
-   <span class="function">require</span>
-   <span class="function">require\_once</span>
-   <span class="function">get\_required\_files</span>

get\_loaded\_extensions
=======================

Returns an array with the names of all modules compiled and loaded

### Description

<span class="type">array</span> <span
class="methodname">get\_loaded\_extensions</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$zend_extensions`<span class="initializer"> = **`FALSE`**</span></span>
\] )

This function returns the names of all the modules compiled and loaded
in the PHP interpreter.

### Parameters

`zend_extensions`  
Only return Zend extensions, if not then regular extensions, like mysqli
are listed. Defaults to **`FALSE`** (return regular extensions).

### Return Values

Returns an indexed array of all the modules names.

### Examples

**Example \#1 <span class="function">get\_loaded\_extensions</span>
Example**

``` php
<?php
print_r(get_loaded_extensions());
?>
```

The above example will output something similar to:

    Array
    (
       [0] => xml
       [1] => wddx
       [2] => standard
       [3] => session
       [4] => posix
       [5] => pgsql
       [6] => pcre
       [7] => gd
       [8] => ftp
       [9] => db
       [10] => calendar
       [11] => bcmath
    )

### See Also

-   <span class="function">get\_extension\_funcs</span>
-   <span class="function">extension\_loaded</span>
-   <span class="function">dl</span>
-   <span class="function">phpinfo</span>

get\_magic\_quotes\_gpc
=======================

Gets the current configuration setting of magic\_quotes\_gpc

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">get\_magic\_quotes\_gpc</span> ( <span
class="methodparam">void</span> )

Returns the current configuration setting of
<a href="/info/setup.html#" class="link">magic_quotes_gpc</a>

Keep in mind that attempting to set
<a href="/info/setup.html#" class="link">magic_quotes_gpc</a> at runtime
will not work.

For more information about magic\_quotes, see this
<a href="/security/magicquotes.html" class="link">security section</a>.

### Return Values

Returns 0 if magic\_quotes\_gpc is off, 1 otherwise. Or always returns
**`FALSE`** as of PHP 5.4.0.

### Changelog

| Version | Description                        |
|---------|------------------------------------|
| 7.4.0   | This function has been deprecated. |

### Examples

**Example \#1 <span class="function">get\_magic\_quotes\_gpc</span>
example**

``` php
<?php
// If magic quotes are enabled
echo $_POST['lastname'];             // O\'reilly
echo addslashes($_POST['lastname']); // O\\\'reilly

// Usage across all PHP versions
if (get_magic_quotes_gpc()) {
    $lastname = stripslashes($_POST['lastname']);
}
else {
    $lastname = $_POST['lastname'];
}

// If using MySQL
$lastname = mysql_real_escape_string($lastname);

echo $lastname; // O\'reilly
$sql = "INSERT INTO lastnames (lastname) VALUES ('$lastname')";
?>
```

### See Also

-   <span class="function">addslashes</span>
-   <span class="function">stripslashes</span>
-   <span class="function">get\_magic\_quotes\_runtime</span>
-   <span class="function">ini\_get</span>

get\_magic\_quotes\_runtime
===========================

Gets the current active configuration setting of magic\_quotes\_runtime

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">get\_magic\_quotes\_runtime</span> ( <span
class="methodparam">void</span> )

Returns the current active configuration setting of
<a href="/info/setup.html#" class="link">magic_quotes_runtime</a>.

### Return Values

Returns 0 if magic\_quotes\_runtime is off, 1 otherwise. Or always
returns **`FALSE`** as of PHP 5.4.0.

### Changelog

| Version | Description                        |
|---------|------------------------------------|
| 7.4.0   | This function has been deprecated. |

### Examples

**Example \#1 <span class="function">get\_magic\_quotes\_runtime</span>
example**

``` php
<?php
// Check if magic_quotes_runtime is active
if(get_magic_quotes_runtime())
{
    // Deactivate
    set_magic_quotes_runtime(false);
}
?>
```

### See Also

-   <span class="function">get\_magic\_quotes\_gpc</span>
-   <span class="function">set\_magic\_quotes\_runtime</span>

get\_required\_files
====================

Alias of <span class="function">get\_included\_files</span>

### Description

This function is an alias of: <span
class="function">get\_included\_files</span>.

get\_resources
==============

Returns active resources

### Description

<span class="type">array</span> <span
class="methodname">get\_resources</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`</span> \] )

Returns an array of all currently active <span
class="type">resource</span>s, optionally filtered by resource type.

### Parameters

`type`  
If defined, this will cause <span class="function">get\_resources</span>
to only return resources of the given type.
<a href="/resource.html" class="link">A list of resource types is available.</a>

If the <span class="type">string</span> *Unknown* is provided as the
type, then only resources that are of an unknown type will be returned.

If omitted, all resources will be returned.

### Return Values

Returns an <span class="type">array</span> of currently active
resources, indexed by resource number.

### Examples

**Example \#1 Unfiltered <span class="function">get\_resources</span>**

``` php
<?php
$fp = tmpfile();
var_dump(get_resources());
?>
```

The above example will output something similar to:

    array(1) {
      [1]=>
      resource(1) of type (stream)
    }

**Example \#2 Filtered <span class="function">get\_resources</span>**

``` php
<?php
$fp = tmpfile();
var_dump(get_resources('stream'));
var_dump(get_resources('curl'));
?>
```

The above example will output something similar to:

    array(1) {
      [1]=>
      resource(1) of type (stream)
    }
    array(0) {
    }

### See Also

-   <span class="function">get\_loaded\_extensions</span>
-   <span class="function">get\_defined\_constants</span>
-   <span class="function">get\_defined\_functions</span>
-   <span class="function">get\_defined\_vars</span>

getenv
======

Gets the value of an environment variable

### Description

<span class="type">string</span> <span class="methodname">getenv</span>
( <span class="methodparam"><span class="type">string</span>
`$varname`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$local_only`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="type">array</span> <span class="methodname">getenv</span> (
<span class="methodparam">void</span> )

Gets the value of an environment variable.

You can see a list of all the environmental variables by using <span
class="function">phpinfo</span>. Many of these variables are listed
within
<a href="http://www.faqs.org/rfcs/rfc3875" class="link external">» RFC 3875</a>,
specifically section 4.1, "Request Meta-Variables".

### Parameters

`varname`  
The variable name.

`local_only`  
Set to true to only return local environment variables (set by the
operating system or putenv).

### Return Values

Returns the value of the environment variable `varname`, or **`FALSE`**
if the environment variable `varname` does not exist. If `varname` is
omitted, all environment variables are returned as associative <span
class="type">array</span>.

### Changelog

| Version               | Description                                                                                                               |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------|
| 7.1.0                 | The `varname` can now be omitted to retrieve an associative <span class="type">array</span> of all environment variables. |
| 5.5.38, 5.6.24, 7.0.9 | The `local_only` parameter has been added.                                                                                |

### Notes

**Warning**

If PHP is running in a SAPI such as Fast CGI, this function will always
return the value of an environment variable set by the SAPI, even if
<span class="function">putenv</span> has been used to set a local
environment variable of the same name. Use the `local_only` parameter to
return the value of locally-set environment variables.

### Examples

**Example \#1 <span class="function">getenv</span> Example**

``` php
<?php
// Example use of getenv()
$ip = getenv('REMOTE_ADDR');

// Or simply use a Superglobal ($_SERVER or $_ENV)
$ip = $_SERVER['REMOTE_ADDR'];

// Safely get the value of an environment variable, ignoring whether 
// or not it was set by a SAPI or has been changed with putenv
$ip = getenv('REMOTE_ADDR', true) ?: getenv('REMOTE_ADDR')
?>
```

### See Also

-   <span class="function">putenv</span>
-   <span class="function">apache\_getenv</span>
-   <a href="/language/variables/superglobals.html" class="link">Superglobals</a>

getlastmod
==========

Gets time of last page modification

### Description

<span class="type">int</span> <span class="methodname">getlastmod</span>
( <span class="methodparam">void</span> )

Gets the time of the last modification of the main script of execution.

If you're interested in getting the last modification time of a
different file, consider using <span class="function">filemtime</span>.

### Return Values

Returns the time of the last modification of the current page. The value
returned is a Unix timestamp, suitable for feeding to <span
class="function">date</span>. Returns **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">getlastmod</span> example**

``` php
<?php
// outputs e.g. 'Last modified: March 04 1998 20:43:59.'
echo "Last modified: " . date ("F d Y H:i:s.", getlastmod());
?>
```

### See Also

-   <span class="function">date</span>
-   <span class="function">getmyuid</span>
-   <span class="function">getmygid</span>
-   <span class="function">get\_current\_user</span>
-   <span class="function">getmyinode</span>
-   <span class="function">getmypid</span>
-   <span class="function">filemtime</span>

getmygid
========

Get PHP script owner's GID

### Description

<span class="type">int</span> <span class="methodname">getmygid</span> (
<span class="methodparam">void</span> )

Gets the group ID of the current script.

### Return Values

Returns the group ID of the current script, or **`FALSE`** on error.

### See Also

-   <span class="function">getmyuid</span>
-   <span class="function">getmypid</span>
-   <span class="function">get\_current\_user</span>
-   <span class="function">getmyinode</span>
-   <span class="function">getlastmod</span>

getmyinode
==========

Gets the inode of the current script

### Description

<span class="type">int</span> <span class="methodname">getmyinode</span>
( <span class="methodparam">void</span> )

Gets the inode of the current script.

### Return Values

Returns the current script's inode as an integer, or **`FALSE`** on
error.

### See Also

-   <span class="function">getmygid</span>
-   <span class="function">getmyuid</span>
-   <span class="function">getmypid</span>
-   <span class="function">get\_current\_user</span>
-   <span class="function">getlastmod</span>

getmypid
========

Gets PHP's process ID

### Description

<span class="type">int</span> <span class="methodname">getmypid</span> (
<span class="methodparam">void</span> )

Gets the current PHP process ID.

### Return Values

Returns the current PHP process ID, or **`FALSE`** on error.

### Notes

**Warning**

Process IDs are not unique, thus they are a weak entropy source. We
recommend against relying on pids in security-dependent contexts.

### See Also

-   <span class="function">getmygid</span>
-   <span class="function">getmyuid</span>
-   <span class="function">get\_current\_user</span>
-   <span class="function">getmyinode</span>
-   <span class="function">getlastmod</span>

getmyuid
========

Gets PHP script owner's UID

### Description

<span class="type">int</span> <span class="methodname">getmyuid</span> (
<span class="methodparam">void</span> )

Gets the user ID of the current script.

### Return Values

Returns the user ID of the current script, or **`FALSE`** on error.

### See Also

-   <span class="function">getmygid</span>
-   <span class="function">getmypid</span>
-   <span class="function">get\_current\_user</span>
-   <span class="function">getmyinode</span>
-   <span class="function">getlastmod</span>

getopt
======

Gets options from the command line argument list

### Description

<span class="type">array</span> <span class="methodname">getopt</span> (
<span class="methodparam"><span class="type">string</span>
`$options`</span> \[, <span class="methodparam"><span
class="type">array</span> `$longopts`</span> \[, <span
class="methodparam"><span class="type">int</span> `&$optind`</span> \]\]
)

Parses options passed to the script.

### Parameters

`options`  
<span class="simpara"> Each character in this string will be used as
option characters and matched against options passed to the script
starting with a single hyphen (*-*). </span> <span class="simpara"> For
example, an option string *"x"* recognizes an option *-x*. </span> <span
class="simpara"> Only a-z, A-Z and 0-9 are allowed. </span>

`longopts`  
<span class="simpara"> An array of options. Each element in this array
will be used as option strings and matched against options passed to the
script starting with two hyphens (*--*). </span> <span class="simpara">
For example, an longopts element *"opt"* recognizes an option *--opt*.
</span>

`optind`  
<span class="simpara"> If the `optind` parameter is present, then the
index where argument parsing stopped will be written to this variable.
</span>

The `options` parameter may contain the following elements:

-   Individual characters (do not accept values)
-   Characters followed by a colon (parameter requires value)
-   Characters followed by two colons (optional value)

Option values are the first argument after the string. If a value is
required, it does not matter whether the value has leading white space
or not. See note.

> **Note**: <span class="simpara"> Optional values do not accept *" "*
> (space) as a separator. </span>

> **Note**:
>
> The format for the `options` and `longopts` is almost the same, the
> only difference is that `longopts` takes an array of options (where
> each element is the option) whereas `options` takes a string (where
> each character is the option).

### Return Values

This function will return an array of option / argument pairs, or
**`FALSE`** on failure.

> **Note**:
>
> The parsing of options will end at the first non-option found,
> anything that follows is discarded.

### Changelog

| Version | Description                   |
|---------|-------------------------------|
| 7.1.0   | Added the `optind` parameter. |

### Examples

**Example \#1 <span class="function">getopt</span> example: The basics**

``` php
<?php
// Script example.php
$options = getopt("f:hp:");
var_dump($options);
?>
```

``` shell
shell> php example.php -fvalue -h
```

The above example will output:

    array(2) {
      ["f"]=>
      string(5) "value"
      ["h"]=>
      bool(false)
    }

**Example \#2 <span class="function">getopt</span> example: Introducing
long options**

``` php
<?php
// Script example.php
$shortopts  = "";
$shortopts .= "f:";  // Required value
$shortopts .= "v::"; // Optional value
$shortopts .= "abc"; // These options do not accept values

$longopts  = array(
    "required:",     // Required value
    "optional::",    // Optional value
    "option",        // No value
    "opt",           // No value
);
$options = getopt($shortopts, $longopts);
var_dump($options);
?>
```

``` shell
shell> php example.php -f "value for f" -v -a --required value --optional="optional value" --option
```

The above example will output:

    array(6) {
      ["f"]=>
      string(11) "value for f"
      ["v"]=>
      bool(false)
      ["a"]=>
      bool(false)
      ["required"]=>
      string(5) "value"
      ["optional"]=>
      string(14) "optional value"
      ["option"]=>
      bool(false)
    }

**Example \#3 <span class="function">getopt</span> example: Passing
multiple options as one**

``` php
<?php
// Script example.php
$options = getopt("abc");
var_dump($options);
?>
```

``` shell
shell> php example.php -aaac
```

The above example will output:

    array(2) {
      ["a"]=>
      array(3) {
        [0]=>
        bool(false)
        [1]=>
        bool(false)
        [2]=>
        bool(false)
      }
      ["c"]=>
      bool(false)
    }

**Example \#4 <span class="function">getopt</span> example: Using
`optind`**

``` php
<?php
// Script example.php
$optind = null;
$opts = getopt('a:b:', [], $optind);
$pos_args = array_slice($argv, $optind);
var_dump($pos_args);
```

``` shell
shell> php example.php -a 1 -b 2 -- test
```

The above example will output:

    array(1) {
      [0]=>
      string(4) "test"
    }

### See Also

-   <a href="/reserved/variables/argv.html" class="link"><var class="varname">$argv</var></a>

getrusage
=========

Gets the current resource usages

### Description

<span class="type">array</span> <span
class="methodname">getrusage</span> (\[ <span class="methodparam"><span
class="type">int</span> `$who`<span class="initializer"> =
0</span></span> \] )

This is an interface to **getrusage(2)**. It gets data returned from the
system call.

### Parameters

`who`  
If `who` is 1, getrusage will be called with **`RUSAGE_CHILDREN`**.

### Return Values

Returns an associative array containing the data returned from the
system call. All entries are accessible by using their documented field
names.

### Examples

**Example \#1 <span class="function">getrusage</span> example**

``` php
<?php
$dat = getrusage();
echo $dat["ru_oublock"];       // number of block output operations
echo $dat["ru_inblock"];       // number of block input operations
echo $dat["ru_msgsnd"];        // number of IPC messages sent
echo $dat["ru_msgrcv"];        // number of IPC messages received
echo $dat["ru_maxrss"];        // maximum resident set size
echo $dat["ru_ixrss"];         // integral shared memory size
echo $dat["ru_idrss"];         // integral unshared data size
echo $dat["ru_minflt"];        // number of page reclaims (soft page faults)
echo $dat["ru_majflt"];        // number of page faults (hard page faults)
echo $dat["ru_nsignals"];      // number of signals received
echo $dat["ru_nvcsw"];         // number of voluntary context switches
echo $dat["ru_nivcsw"];        // number of involuntary context switches
echo $dat["ru_nswap"];         // number of swaps
echo $dat["ru_utime.tv_usec"]; // user time used (microseconds)
echo $dat["ru_utime.tv_sec"];  // user time used (seconds)
echo $dat["ru_stime.tv_usec"]; // system time used (microseconds)
?>
```

### Changelog

| Version | Description                                |
|---------|--------------------------------------------|
| 7.0.0   | This function is now supported on Windows. |

### Notes

> **Note**:
>
> On Windows <span class="function">getrusage</span> will only return
> the following members:
>
> -   *"ru\_stime.tv\_sec"*
> -   *"ru\_stime.tv\_usec"*
> -   *"ru\_utime.tv\_sec"*
> -   *"ru\_utime.tv\_usec"*
> -   *"ru\_majflt"* (only if `who` is **`RUSAGE_SELF`**)
> -   *"ru\_maxrss"* (only if `who` is **`RUSAGE_SELF`**)
>
> If <span class="function">getrusage</span> is called with `who` set to
> *1* (**`RUSAGE_CHILDREN`**), then resource usage for threads are
> collected (meaning that internally the function is called with
> **`RUSAGE_THREAD`**).

> **Note**:
>
> on BeOS 2000, only the following members are returned:
>
> -   *"ru\_stime.tv\_sec"*
> -   *"ru\_stime.tv\_usec"*
> -   *"ru\_utime.tv\_sec"*
> -   *"ru\_utime.tv\_usec"*

### See Also

-   Your system's man page on **getrusage(2)**

ini\_alter
==========

Alias of <span class="function">ini\_set</span>

### Description

This function is an alias of: <span class="function">ini\_set</span>.

ini\_get\_all
=============

Gets all configuration options

### Description

<span class="type">array</span> <span
class="methodname">ini\_get\_all</span> (\[ <span
class="methodparam"><span class="type">string</span> `$extension`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$details`<span class="initializer"> = **`TRUE`**</span></span> \]\] )

Returns all the registered configuration options.

### Parameters

`extension`  
An optional extension name. If set, the function return only options
specific for that extension.

`details`  
Retrieve details settings or only the current value for each setting.
Default is **`TRUE`** (retrieve details).

### Return Values

Returns an associative array with directive name as the array key.
Returns **`FALSE`** and raises an **`E_WARNING`** level error if the
`extension` doesn't exist.

When `details` is **`TRUE`** (default) the array will contain
*global\_value* (set in `php.ini`), *local\_value* (perhaps set with
<span class="function">ini\_set</span> or `.htaccess`), and *access*
(the access level).

When `details` is **`FALSE`** the value will be the current value of the
option.

See the
<a href="/configuration/changes/modes.html" class="link">manual section</a>
for information on what access levels mean.

> **Note**:
>
> It's possible for a directive to have multiple access levels, which is
> why *access* shows the appropriate bitmask values.

### Notes

> **Note**:
>
> <span class="function">ini\_get\_all</span> ignores "array" ini
> options such as pdo.dsn.\*.

### Examples

**Example \#1 <span class="function">ini\_get\_all</span> examples**

``` php
<?php
print_r(ini_get_all("pcre"));
print_r(ini_get_all());
?>
```

The above example will output something similar to:

    Array
    (
        [pcre.backtrack_limit] => Array
            (
                [global_value] => 100000
                [local_value] => 100000
                [access] => 7
            )

        [pcre.recursion_limit] => Array
            (
                [global_value] => 100000
                [local_value] => 100000
                [access] => 7
            )

    )
    Array
    (
        [allow_call_time_pass_reference] => Array
            (
                [global_value] => 0
                [local_value] => 0
                [access] => 6
            )

        [allow_url_fopen] => Array
            (
                [global_value] => 1
                [local_value] => 1
                [access] => 4
            )

        ...

    )

**Example \#2 Disabling `details`**

``` php
<?php
print_r(ini_get_all("pcre", false)); // Added in PHP 5.3.0
print_r(ini_get_all(null, false)); // Added in PHP 5.3.0
?>
```

The above example will output something similar to:

    Array
    (
        [pcre.backtrack_limit] => 100000
        [pcre.recursion_limit] => 100000
    )
    Array
    (
        [allow_call_time_pass_reference] => 0
        [allow_url_fopen] => 1
        ...
    )

### See Also

-   <a href="/configuration/changes.html" class="xref">How to change configuration settings</a>
-   <span class="function">ini\_get</span>
-   <span class="function">ini\_restore</span>
-   <span class="function">ini\_set</span>
-   <span class="function">get\_loaded\_extensions</span>
-   <span class="function">phpinfo</span>
-   <span class="methodname">ReflectionExtension::getINIEntries</span>

ini\_get
========

Gets the value of a configuration option

### Description

<span class="type">string</span> <span
class="methodname">ini\_get</span> ( <span class="methodparam"><span
class="type">string</span> `$varname`</span> )

Returns the value of the configuration option on success.

### Parameters

`varname`  
The configuration option name.

### Return Values

Returns the value of the configuration option as a string on success, or
an empty string for *null* values. Returns **`FALSE`** if the
configuration option doesn't exist.

### Examples

**Example \#1 A few <span class="function">ini\_get</span> examples**

``` php
<?php
/*
Our php.ini contains the following settings:

display_errors = On
register_globals = Off
post_max_size = 8M
*/

echo 'display_errors = ' . ini_get('display_errors') . "\n";
echo 'register_globals = ' . ini_get('register_globals') . "\n";
echo 'post_max_size = ' . ini_get('post_max_size') . "\n";
echo 'post_max_size+1 = ' . (ini_get('post_max_size')+1) . "\n";
echo 'post_max_size in bytes = ' . return_bytes(ini_get('post_max_size'));

function return_bytes($val) {
    $val = trim($val);
    $last = strtolower($val[strlen($val)-1]);
    switch($last) {
        // The 'G' modifier is available since PHP 5.1.0
        case 'g':
            $val *= 1024;
        case 'm':
            $val *= 1024;
        case 'k':
            $val *= 1024;
    }

    return $val;
}

?>
```

The above example will output something similar to:


    display_errors = 1
    register_globals = 0
    post_max_size = 8M
    post_max_size+1 = 9
    post_max_size in bytes = 8388608

### Notes

> **Note**: **When querying boolean values**  
>
> A boolean ini value of *off* will be returned as an empty string or
> "0" while a boolean ini value of *on* will be returned as "1". The
> function can also return the literal string of INI value.

> **Note**: **When querying memory size values**  
>
> Many ini memory size values, such as
> <a href="/ini/core.html#ini.upload-max-filesize" class="link">upload_max_filesize</a>,
> are stored in the `php.ini` file in shorthand notation. <span
> class="function">ini\_get</span> will return the exact string stored
> in the `php.ini` file and *NOT* its <span class="type">integer</span>
> equivalent. Attempting normal arithmetic functions on these values
> will not have otherwise expected results. The example above shows one
> way to convert shorthand notation into bytes, much like how the PHP
> source does it.

> **Note**:
>
> <span class="function">ini\_get</span> can't read "array" ini options
> such as pdo.dsn.\*, and returns **`FALSE`** in this case.

### See Also

-   <span class="function">get\_cfg\_var</span>
-   <span class="function">ini\_get\_all</span>
-   <span class="function">ini\_restore</span>
-   <span class="function">ini\_set</span>

ini\_restore
============

Restores the value of a configuration option

### Description

<span class="type">void</span> <span
class="methodname">ini\_restore</span> ( <span class="methodparam"><span
class="type">string</span> `$varname`</span> )

Restores a given configuration option to its original value.

### Parameters

`varname`  
The configuration option name.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ini\_restore</span> example**

``` php
<?php
$setting = 'y2k_compliance';

echo 'Current value for \'' . $setting . '\': ' . ini_get($setting), PHP_EOL;

ini_set($setting, ini_get($setting) ? 0 : 1);
echo 'New value for \'' . $setting . '\': ' . ini_get($setting), PHP_EOL;

ini_restore($setting);
echo 'Original value for \'' . $setting . '\': ' . ini_get($setting), PHP_EOL;
?>
```

The above example will output:

    Current value for 'y2k_compliance': 1
    New value for 'y2k_compliance': 0
    Original value for 'y2k_compliance': 1

### See Also

-   <span class="function">ini\_get</span>
-   <span class="function">ini\_get\_all</span>
-   <span class="function">ini\_set</span>

ini\_set
========

Sets the value of a configuration option

### Description

<span class="type">string</span> <span
class="methodname">ini\_set</span> ( <span class="methodparam"><span
class="type">string</span> `$varname`</span> , <span
class="methodparam"><span class="type">string</span> `$newvalue`</span>
)

Sets the value of the given configuration option. The configuration
option will keep this new value during the script's execution, and will
be restored at the script's ending.

### Parameters

`varname`  
Not all the available options can be changed using <span
class="function">ini\_set</span>. There is a list of all available
options in the <a href="/ini/list.html" class="link">appendix</a>.

`newvalue`  
The new value for the option.

### Return Values

Returns the old value on success, **`FALSE`** on failure.

### Examples

**Example \#1 Setting an ini option**

``` php
<?php
echo ini_get('display_errors');

if (!ini_get('display_errors')) {
    ini_set('display_errors', '1');
}

echo ini_get('display_errors');
?>
```

### See Also

-   <span class="function">get\_cfg\_var</span>
-   <span class="function">ini\_get</span>
-   <span class="function">ini\_get\_all</span>
-   <span class="function">ini\_restore</span>
-   <a href="/configuration/changes.html" class="link">How to change configuration settings</a>

main
====

Dummy for <span class="function">main</span>

### Description

There is no function named <span class="function">main</span> except in
the PHP source. In PHP 4.3.0, a new type of error handling in the PHP
source (php\_error\_docref) was introduced. One feature is to provide
links to a manual page in PHP error messages when the PHP directives
<a href="/errorfunc/setup.html#" class="link">html_errors</a> (on by
default) and
<a href="/errorfunc/setup.html#" class="link">docref_root</a> (on by
default until PHP 4.3.2) are set.

Sometimes error messages refer to a manual page for the function <span
class="function">main</span> which is why this page exists. If you
discover such a reference, please
<a href="https://bugs.php.net/" class="link external">» file a bug report</a>,
indicating the PHP function caused the error that linked to <span
class="function">main</span> and it will be fixed and properly
documented.

| Function name                               | No longer points here as of |
|---------------------------------------------|-----------------------------|
| <span class="function">include</span>       | 5.1.0                       |
| <span class="function">include\_once</span> | 5.1.0                       |
| <span class="function">require</span>       | 5.1.0                       |
| <span class="function">require\_once</span> | 5.1.0                       |

### See Also

-   <a href="/errorfunc/setup.html#" class="link">html_errors</a>
-   <a href="/errorfunc/setup.html#" class="link">display_errors</a>

memory\_get\_peak\_usage
========================

Returns the peak of memory allocated by PHP

### Description

<span class="type">int</span> <span
class="methodname">memory\_get\_peak\_usage</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$real_usage`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Returns the peak of memory, in bytes, that's been allocated to your PHP
script.

### Parameters

`real_usage`  
Set this to **`TRUE`** to get the real size of memory allocated from
system. If not set or **`FALSE`** only the memory used by *emalloc()* is
reported.

### Return Values

Returns the memory peak in bytes.

### See Also

-   <span class="function">memory\_get\_usage</span>
-   <a href="/ini/core.html#ini.memory-limit" class="link">memory_limit</a>

memory\_get\_usage
==================

Returns the amount of memory allocated to PHP

### Description

<span class="type">int</span> <span
class="methodname">memory\_get\_usage</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$real_usage`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Returns the amount of memory, in bytes, that's currently being allocated
to your PHP script.

### Parameters

`real_usage`  
Set this to **`TRUE`** to get total memory allocated from system,
including unused pages. If not set or **`FALSE`** only the used memory
is reported.

> **Note**:
>
> PHP does not track memory that is not allocated by *emalloc()*

### Return Values

Returns the memory amount in bytes.

### Examples

**Example \#1 A <span class="function">memory\_get\_usage</span>
example**

``` php
<?php
// This is only an example, the numbers below will
// differ depending on your system

echo memory_get_usage() . "\n"; // 36640

$a = str_repeat("Hello", 4242);

echo memory_get_usage() . "\n"; // 57960

unset($a);

echo memory_get_usage() . "\n"; // 36744

?>
```

### See Also

-   <span class="function">memory\_get\_peak\_usage</span>
-   <a href="/ini/core.html#ini.memory-limit" class="link">memory_limit</a>

php\_ini\_loaded\_file
======================

Retrieve a path to the loaded php.ini file

### Description

<span class="type">string</span> <span
class="methodname">php\_ini\_loaded\_file</span> ( <span
class="methodparam">void</span> )

Check if a `php.ini` file is loaded, and retrieve its path.

### Parameters

This function has no parameters.

### Return Values

The loaded `php.ini` path, or **`FALSE`** if one is not loaded.

### Examples

**Example \#1 <span class="function">php\_ini\_loaded\_file</span>
example**

``` php
<?php
$inipath = php_ini_loaded_file();

if ($inipath) {
    echo 'Loaded php.ini: ' . $inipath;
} else {
    echo 'A php.ini file is not loaded';
}
?>
```

The above example will output something similar to:

    Loaded php.ini: /usr/local/php/php.ini

### See Also

-   <span class="function">php\_ini\_scanned\_files</span>
-   <span class="function">phpinfo</span>
-   <a href="/configuration/file.html" class="link">The configuration file</a>

php\_ini\_scanned\_files
========================

Return a list of .ini files parsed from the additional ini dir

### Description

<span class="type">string</span> <span
class="methodname">php\_ini\_scanned\_files</span> ( <span
class="methodparam">void</span> )

<span class="function">php\_ini\_scanned\_files</span> returns a
comma-separated list of configuration files parsed after `php.ini`. The
directories searched are set by a compile time option and, optionally,
by an environment variable at run time: more information can be found in
the
<a href="/configuration/file.html#configuration.file.scan" class="link">installation guide</a>.

The returned configuration files include the full path.

### Return Values

Returns a comma-separated string of .ini files on success. Each comma is
followed by a newline. If the configure directive
**--with-config-file-scan-dir** wasn't set and the `PHP_INI_SCAN_DIR`
environment variable isn't set, **`FALSE`** is returned. If it was set
and the directory was empty, an empty string is returned. If a file is
unrecognizable, the file will still make it into the returned string but
a PHP error will also result. This PHP error will be seen both at
compile time and while using <span
class="function">php\_ini\_scanned\_files</span>.

### Examples

**Example \#1 A simple example to list the returned ini files**

``` php
<?php
if ($filelist = php_ini_scanned_files()) {
    if (strlen($filelist) > 0) {
        $files = explode(',', $filelist);

        foreach ($files as $file) {
            echo "<li>" . trim($file) . "</li>\n";
        }
    }
}
?>
```

### See Also

-   <span class="function">ini\_set</span>
-   <span class="function">phpinfo</span>
-   <span class="function">php\_ini\_loaded\_file</span>

php\_sapi\_name
===============

Returns the type of interface between web server and PHP

### Description

<span class="type">string</span> <span
class="methodname">php\_sapi\_name</span> ( <span
class="methodparam">void</span> )

Returns a lowercase string that describes the type of interface (the
Server API, SAPI) that PHP is using. For example, in CLI PHP this string
will be "cli" whereas with Apache it may have several different values
depending on the exact SAPI used. Possible values are listed below.

### Return Values

Returns the interface type, as a lowercase string.

Although not exhaustive, the possible return values include *apache*,
*apache2handler*, *cgi* (until PHP 5.3), *cgi-fcgi*, *cli*,
*cli-server*, *embed*, *fpm-fcgi*, *litespeed*, *nsapi*, *phpdbg*.

### Examples

**Example \#1 <span class="function">php\_sapi\_name</span> example**

This example checks for the substring *cgi* because it may also be
*cgi-fcgi*.

``` php
<?php
$sapi_type = php_sapi_name();
if (substr($sapi_type, 0, 3) == 'cgi') {
    echo "You are using CGI PHP\n";
} else {
    echo "You are not using CGI PHP\n";
}
?>
```

### Notes

> **Note**: **An alternative approach**  
>
> The PHP constant **`PHP_SAPI`** has the same value as <span
> class="function">php\_sapi\_name</span>.

**Tip**

The defined SAPI may not be obvious, because for example instead of
*apache* it may be defined as *apache2handler*.

### See Also

-   <a href="/reserved/constants.html#reserved.constants.core" class="link">PHP_SAPI</a>

php\_uname
==========

Returns information about the operating system PHP is running on

### Description

<span class="type">string</span> <span
class="methodname">php\_uname</span> (\[ <span class="methodparam"><span
class="type">string</span> `$mode`<span class="initializer"> =
"a"</span></span> \] )

<span class="function">php\_uname</span> returns a description of the
operating system PHP is running on. This is the same string you see at
the very top of the <span class="function">phpinfo</span> output. For
the name of just the operating system, consider using the **`PHP_OS`**
constant, but keep in mind this constant will contain the operating
system PHP was *built* on.

On some older UNIX platforms, it may not be able to determine the
current OS information in which case it will revert to displaying the OS
PHP was built on. This will only happen if your uname() library call
either doesn't exist or doesn't work.

### Parameters

`mode`  
`mode` is a single character that defines what information is returned:

-   <span class="simpara"> *'a'*: This is the default. Contains all
    modes in the sequence *"s n r v m"*. </span>
-   <span class="simpara"> *'s'*: Operating system name. eg. *FreeBSD*.
    </span>
-   <span class="simpara"> *'n'*: Host name. eg.
    *localhost.example.com*. </span>
-   <span class="simpara"> *'r'*: Release name. eg. *5.1.2-RELEASE*.
    </span>
-   <span class="simpara"> *'v'*: Version information. Varies a lot
    between operating systems. </span>
-   <span class="simpara"> *'m'*: Machine type. eg. *i386*. </span>

### Return Values

Returns the description, as a string.

### Examples

**Example \#1 Some <span class="function">php\_uname</span> examples**

``` php
<?php
echo php_uname();
echo PHP_OS;

/* Some possible outputs:
Linux localhost 2.4.21-0.13mdk #1 Fri Mar 14 15:08:06 EST 2003 i686
Linux

FreeBSD localhost 3.2-RELEASE #15: Mon Dec 17 08:46:02 GMT 2001
FreeBSD

Windows NT XN1 5.1 build 2600
WINNT
*/

if (strtoupper(substr(PHP_OS, 0, 3)) === 'WIN') {
    echo 'This is a server using Windows!';
} else {
    echo 'This is a server not using Windows!';
}

?>
```

There are also some related
<a href="/language/constants/predefined.html" class="link">Predefined PHP constants</a>
that may come in handy, for example:

**Example \#2 A few OS related constant examples**

``` php
<?php
// *nix
echo DIRECTORY_SEPARATOR; // /
echo PHP_SHLIB_SUFFIX;    // so
echo PATH_SEPARATOR;      // :

// Win*
echo DIRECTORY_SEPARATOR; // \
echo PHP_SHLIB_SUFFIX;    // dll
echo PATH_SEPARATOR;      // ;
?>
```

### See Also

-   <span class="function">phpversion</span>
-   <span class="function">php\_sapi\_name</span>
-   <span class="function">phpinfo</span>

phpcredits
==========

Prints out the credits for PHP

### Description

<span class="type">bool</span> <span
class="methodname">phpcredits</span> (\[ <span class="methodparam"><span
class="type">int</span> `$flag`<span class="initializer"> =
CREDITS\_ALL</span></span> \] )

This function prints out the credits listing the PHP developers,
modules, etc. It generates the appropriate HTML codes to insert the
information in a page.

### Parameters

`flag`  
To generate a custom credits page, you may want to use the `flag`
parameter.

| name              | description                                                                                                                                                                                                                       |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CREDITS\_ALL      | All the credits, equivalent to using: **`CREDITS_DOCS`** + **`CREDITS_GENERAL`** + **`CREDITS_GROUP`** + **`CREDITS_MODULES`** + **`CREDITS_FULLPAGE`**. It generates a complete stand-alone HTML page with the appropriate tags. |
| CREDITS\_DOCS     | The credits for the documentation team                                                                                                                                                                                            |
| CREDITS\_FULLPAGE | Usually used in combination with the other flags. Indicates that a complete stand-alone HTML page needs to be printed including the information indicated by the other flags.                                                     |
| CREDITS\_GENERAL  | General credits: Language design and concept, PHP authors and SAPI module.                                                                                                                                                        |
| CREDITS\_GROUP    | A list of the core developers                                                                                                                                                                                                     |
| CREDITS\_MODULES  | A list of the extension modules for PHP, and their authors                                                                                                                                                                        |
| CREDITS\_SAPI     | A list of the server API modules for PHP, and their authors                                                                                                                                                                       |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Prints the general credits**

``` php
<?php
phpcredits(CREDITS_GENERAL);
?>
```

**Example \#2 Prints the core developers and the documentation group**

``` php
<?php
phpcredits(CREDITS_GROUP | CREDITS_DOCS | CREDITS_FULLPAGE);
?>
```

**Example \#3 Printing all the credits**

``` php
<html>
 <head>
  <title>My credits page</title>
 </head>
 <body>
<?php
// some code of your own
phpcredits(CREDITS_ALL - CREDITS_FULLPAGE);
// some more code
?>
 </body>
</html>
```

### Notes

> **Note**:
>
> <span class="function">phpcredits</span> outputs plain text instead of
> HTML when using the CLI mode.

### See Also

-   <span class="function">phpversion</span>
-   <span class="function">php\_logo\_guid</span>
-   <span class="function">phpinfo</span>

phpinfo
=======

Outputs information about PHP's configuration

### Description

<span class="type">bool</span> <span class="methodname">phpinfo</span>
(\[ <span class="methodparam"><span class="type">int</span> `$what`<span
class="initializer"> = INFO\_ALL</span></span> \] )

Outputs a large amount of information about the current state of PHP.
This includes information about PHP compilation options and extensions,
the PHP version, server information and environment (if compiled as a
module), the PHP environment, OS version information, paths, master and
local values of configuration options, HTTP headers, and the PHP
License.

Because every system is setup differently, <span
class="function">phpinfo</span> is commonly used to check
<a href="/configuration.html" class="link">configuration settings</a>
and for available
<a href="/language/variables/predefined.html" class="link">predefined variables</a>
on a given system.

<span class="function">phpinfo</span> is also a valuable debugging tool
as it contains all EGPCS (Environment, GET, POST, Cookie, Server) data.

### Parameters

`what`  
The output may be customized by passing one or more of the following
*constants* bitwise values summed together in the optional `what`
parameter. One can also combine the respective constants or bitwise
values together with the
<a href="/language/operators/bitwise.html" class="link">bitwise or operator</a>.

| Name (constant)     | Value | Description                                                                                                                                        |
|---------------------|-------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| INFO\_GENERAL       | 1     | The configuration line, `php.ini` location, build date, Web Server, System and more.                                                               |
| INFO\_CREDITS       | 2     | PHP Credits. See also <span class="function">phpcredits</span>.                                                                                    |
| INFO\_CONFIGURATION | 4     | Current Local and Master values for PHP directives. See also <span class="function">ini\_get</span>.                                               |
| INFO\_MODULES       | 8     | Loaded modules and their respective settings. See also <span class="function">get\_loaded\_extensions</span>.                                      |
| INFO\_ENVIRONMENT   | 16    | Environment Variable information that's also available in `$_ENV`.                                                                                 |
| INFO\_VARIABLES     | 32    | Shows all <a href="/language/variables/predefined.html" class="link">predefined variables</a> from EGPCS (Environment, GET, POST, Cookie, Server). |
| INFO\_LICENSE       | 64    | PHP License information. See also the <a href="https://www.php.net/license/" class="link external">» license FAQ</a>.                              |
| INFO\_ALL           | -1    | Shows all of the above.                                                                                                                            |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">phpinfo</span> Example**

``` php
<?php

// Show all information, defaults to INFO_ALL
phpinfo();

// Show just the module information.
// phpinfo(8) yields identical results.
phpinfo(INFO_MODULES);

?>
```

### Notes

> **Note**:
>
> In versions of PHP before 5.5, parts of the information displayed are
> disabled when the
> <a href="/ini/core.html#ini.expose-php" class="link">expose_php</a>
> configuration setting is set to *off*. This includes the PHP and Zend
> logos, and the credits.

> **Note**:
>
> <span class="function">phpinfo</span> outputs plain text instead of
> HTML when using the CLI mode.

### See Also

-   <span class="function">phpversion</span>
-   <span class="function">phpcredits</span>
-   <span class="function">php\_logo\_guid</span>
-   <span class="function">ini\_get</span>
-   <span class="function">ini\_set</span>
-   <span class="function">get\_loaded\_extensions</span>
-   <a href="/language/variables/predefined.html" class="link">Predefined Variables</a>

phpversion
==========

Gets the current PHP version

### Description

<span class="type">string</span> <span
class="methodname">phpversion</span> (\[ <span class="methodparam"><span
class="type">string</span> `$extension`</span> \] )

Returns a string containing the version of the currently running PHP
parser or extension.

### Parameters

`extension`  
An optional extension name.

### Return Values

If the optional `extension` parameter is specified, <span
class="function">phpversion</span> returns the version of that
extension, or **`FALSE`** if there is no version information associated
or the extension isn't enabled.

### Examples

**Example \#1 <span class="function">phpversion</span> example**

``` php
<?php
// prints e.g. 'Current PHP version: 4.1.1'
echo 'Current PHP version: ' . phpversion();

// prints e.g. '2.0' or nothing if the extension isn't enabled
echo phpversion('tidy');
?>
```

**Example \#2 **`PHP_VERSION_ID`** example and usage**

``` php
<?php
// PHP_VERSION_ID is available as of PHP 5.2.7, if our 
// version is lower than that, then emulate it
if (!defined('PHP_VERSION_ID')) {
    $version = explode('.', PHP_VERSION);

    define('PHP_VERSION_ID', ($version[0] * 10000 + $version[1] * 100 + $version[2]));
}

// PHP_VERSION_ID is defined as a number, where the higher the number 
// is, the newer a PHP version is used. It's defined as used in the above 
// expression:
//
// $version_id = $major_version * 10000 + $minor_version * 100 + $release_version;
//
// Now with PHP_VERSION_ID we can check for features this PHP version 
// may have, this doesn't require to use version_compare() everytime 
// you check if the current PHP version may not support a feature.
//
// For example, we may here define the PHP_VERSION_* constants thats 
// not available in versions prior to 5.2.7

if (PHP_VERSION_ID < 50207) {
    define('PHP_MAJOR_VERSION',   $version[0]);
    define('PHP_MINOR_VERSION',   $version[1]);
    define('PHP_RELEASE_VERSION', $version[2]);

    // and so on, ...
}
?>
```

### Notes

> **Note**:
>
> This information is also available in the predefined constant
> **`PHP_VERSION`**. More versioning information is available using the
> **`PHP_VERSION_*`** constants.

### See Also

-   <a href="/reserved/constants.html#reserved.constants.core" class="link">PHP_VERSION constants</a>
-   <span class="function">version\_compare</span>
-   <span class="function">phpinfo</span>
-   <span class="function">phpcredits</span>
-   <span class="function">php\_logo\_guid</span>
-   <span class="function">zend\_version</span>

putenv
======

Sets the value of an environment variable

### Description

<span class="type">bool</span> <span class="methodname">putenv</span> (
<span class="methodparam"><span class="type">string</span>
`$setting`</span> )

Adds `setting` to the server environment. The environment variable will
only exist for the duration of the current request. At the end of the
request the environment is restored to its original state.

Setting certain environment variables may be a potential security
breach. The *safe\_mode\_allowed\_env\_vars* directive contains a
comma-delimited list of prefixes. In Safe Mode, the user may only alter
environment variables whose names begin with the prefixes supplied by
this directive. By default, users will only be able to set environment
variables that begin with *PHP\_* (e.g. *PHP\_FOO=BAR*). Note: if this
directive is empty, PHP will let the user modify ANY environment
variable!

The *safe\_mode\_protected\_env\_vars* directive contains a
comma-delimited list of environment variables, that the end user won't
be able to change using <span class="function">putenv</span>. These
variables will be protected even if *safe\_mode\_allowed\_env\_vars* is
set to allow to change them.

### Parameters

`setting`  
The setting, like *"FOO=BAR"*

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Setting an environment variable**

``` php
<?php
putenv("UNIQID=$uniqid");
?>
```

### Notes

**Warning**

The *safe\_mode\_allowed\_env\_vars* and
*safe\_mode\_protected\_env\_vars* directives only take effect when
<a href="/features/safe-mode.html" class="link">safe_mode</a> is
enabled.

### See Also

-   <span class="function">getenv</span>
-   <span class="function">apache\_setenv</span>

restore\_include\_path
======================

Restores the value of the include\_path configuration option

### Description

<span class="type">void</span> <span
class="methodname">restore\_include\_path</span> ( <span
class="methodparam">void</span> )

Restores the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
configuration option back to its original master value as set in
`php.ini`

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">restore\_include\_path</span>
example**

``` php
<?php

echo get_include_path();  // .:/usr/local/lib/php

set_include_path('/inc');

echo get_include_path();  // /inc

restore_include_path();

// Or using ini_restore()
ini_restore('include_path');

echo get_include_path();  // .:/usr/local/lib/php

?>
```

### See Also

-   <span class="function">ini\_restore</span>
-   <span class="function">get\_include\_path</span>
-   <span class="function">set\_include\_path</span>
-   <span class="function">include</span>

set\_include\_path
==================

Sets the include\_path configuration option

### Description

<span class="type">string</span> <span
class="methodname">set\_include\_path</span> ( <span
class="methodparam"><span class="type">string</span>
`$new_include_path`</span> )

Sets the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
configuration option for the duration of the script.

### Parameters

`new_include_path`  
The new value for the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>

### Return Values

Returns the old
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">set\_include\_path</span> example**

``` php
<?php
set_include_path('/usr/lib/pear');

// Or using ini_set()
ini_set('include_path', '/usr/lib/pear');
?>
```

**Example \#2 Adding to the include path**

Making use of the **`PATH_SEPARATOR`** constant, it is possible to
extend the include path regardless of the operating system.

In this example we add `/usr/lib/pear` to the end of the existing
*include\_path*.

``` php
<?php
$path = '/usr/lib/pear';
set_include_path(get_include_path() . PATH_SEPARATOR . $path);
?>
```

### See Also

-   <span class="function">ini\_set</span>
-   <span class="function">get\_include\_path</span>
-   <span class="function">restore\_include\_path</span>
-   <span class="function">include</span>

set\_time\_limit
================

Limits the maximum execution time

### Description

<span class="type">bool</span> <span
class="methodname">set\_time\_limit</span> ( <span
class="methodparam"><span class="type">int</span> `$seconds`</span> )

Set the number of seconds a script is allowed to run. If this is
reached, the script returns a fatal error. The default limit is 30
seconds or, if it exists, the *max\_execution\_time* value defined in
the `php.ini`.

When called, <span class="function">set\_time\_limit</span> restarts the
timeout counter from zero. In other words, if the timeout is the default
30 seconds, and 25 seconds into script execution a call such as
*set\_time\_limit(20)* is made, the script will run for a total of 45
seconds before timing out.

### Parameters

`seconds`  
The maximum execution time, in seconds. If set to zero, no time limit is
imposed.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** on failure.

### Notes

**Warning**

This function has no effect when PHP is running in
<a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>.
There is no workaround other than turning off safe mode or changing the
time limit in the `php.ini`.

> **Note**:
>
> The <span class="function">set\_time\_limit</span> function and the
> configuration directive
> <a href="/info/setup.html#" class="link">max_execution_time</a> only
> affect the execution time of the script itself. Any time spent on
> activity that happens outside the execution of the script such as
> system calls using <span class="function">system</span>, stream
> operations, database queries, etc. is not included when determining
> the maximum time that the script has been running. This is not true on
> Windows where the measured time is real.

### See Also

-   <a href="/info/setup.html#" class="link">max_execution_time</a>
-   <a href="/info/setup.html#" class="link">max_input_time</a>

sys\_get\_temp\_dir
===================

Returns directory path used for temporary files

### Description

<span class="type">string</span> <span
class="methodname">sys\_get\_temp\_dir</span> ( <span
class="methodparam">void</span> )

Returns the path of the directory PHP stores temporary files in by
default.

### Return Values

Returns the path of the temporary directory.

### Examples

**Example \#1 <span class="function">sys\_get\_temp\_dir</span>
example**

``` php
<?php
// Create a temporary file in the temporary 
// files directory using sys_get_temp_dir()
$temp_file = tempnam(sys_get_temp_dir(), 'Tux');

echo $temp_file;
?>
```

The above example will output something similar to:

    C:\Windows\Temp\TuxA318.tmp

### See Also

-   <span class="function">tmpfile</span>
-   <span class="function">tempnam</span>

version\_compare
================

Compares two "PHP-standardized" version number strings

### Description

<span class="type">int</span> <span
class="methodname">version\_compare</span> ( <span
class="methodparam"><span class="type">string</span> `$version1`</span>
, <span class="methodparam"><span class="type">string</span>
`$version2`</span> )

<span class="type">bool</span> <span
class="methodname">version\_compare</span> ( <span
class="methodparam"><span class="type">string</span> `$version1`</span>
, <span class="methodparam"><span class="type">string</span>
`$version2`</span> , <span class="methodparam"><span
class="type">string</span> `$operator`</span> )

<span class="function">version\_compare</span> compares two
"PHP-standardized" version number strings.

The function first replaces *\_*, *-* and *+* with a dot *.* in the
version strings and also inserts dots *.* before and after any non
number so that for example '4.3.2RC1' becomes '4.3.2.RC.1'. Then it
compares the parts starting from left to right. If a part contains
special version strings these are handled in the following order: *any
string not found in this list* \< *dev* \< *alpha* = *a* \< *beta* = *b*
\< *RC* = *rc* \< *\#* \< *pl* = *p*. This way not only versions with
different levels like '4.1' and '4.1.2' can be compared but also any PHP
specific version containing development state.

### Parameters

`version1`  
First version number.

`version2`  
Second version number.

`operator`  
If the third optional `operator` argument is specified, test for a
particular relationship. The possible operators are: *\<*, *lt*, *\<=*,
*le*, *\>*, *gt*, *\>=*, *ge*, *==*, *=*, *eq*, *!=*, *\<\>*, *ne*
respectively.

This parameter is case-sensitive, values should be lowercase.

### Return Values

By default, <span class="function">version\_compare</span> returns *-1*
if the first version is lower than the second, *0* if they are equal,
and *1* if the second is lower.

When using the optional `operator` argument, the function will return
**`TRUE`** if the relationship is the one specified by the operator,
**`FALSE`** otherwise. If an unsupported `operator` is given, **`NULL`**
is returned.

### Examples

The examples below use the **`PHP_VERSION`** constant, because it
contains the value of the PHP version that is executing the code.

**Example \#1 <span class="function">version\_compare</span> examples**

``` php
<?php
if (version_compare(PHP_VERSION, '7.0.0') >= 0) {
    echo 'I am at least PHP version 7.0.0, my version: ' . PHP_VERSION . "\n";
}

if (version_compare(PHP_VERSION, '5.3.0') >= 0) {
    echo 'I am at least PHP version 5.3.0, my version: ' . PHP_VERSION . "\n";
}

if (version_compare(PHP_VERSION, '5.0.0', '>=')) {
    echo 'I am at least PHP version 5.0.0, my version: ' . PHP_VERSION . "\n";
}

if (version_compare(PHP_VERSION, '5.0.0', '<')) {
    echo 'I am still PHP 4, my version: ' . PHP_VERSION . "\n";
}
?>
```

### Notes

> **Note**:
>
> The **`PHP_VERSION`** constant holds current PHP version.

> **Note**:
>
> Note that pre-release versions, such as 5.3.0-dev, are considered
> lower than their final release counterparts (like 5.3.0).

> **Note**:
>
> Special version strings such as *alpha* and *beta* are case sensitive.
> Version strings from arbitrary sources that do not adhere to the PHP
> standard may need to be lowercased via <span
> class="function">strtolower</span> before calling <span
> class="function">version\_compare</span>.

### See Also

-   <span class="function">phpversion</span>
-   <span class="function">php\_uname</span>
-   <span class="function">function\_exists</span>

zend\_thread\_id
================

Returns a unique identifier for the current thread

### Description

<span class="type">int</span> <span
class="methodname">zend\_thread\_id</span> ( <span
class="methodparam">void</span> )

This function returns a unique identifier for the current thread.

### Return Values

Returns the thread id as an integer.

### Examples

**Example \#1 <span class="function">zend\_thread\_id</span> example**

``` php
<?php
$thread_id = zend_thread_id();

echo 'Current thread id is: ' . $thread_id;
?>
```

The above example will output something similar to:

    Current thread id is: 7864

### Notes

> **Note**:
>
> This function is only available if PHP has been built with ZTS (Zend
> Thread Safety) support and debug mode (*--enable-debug*).

zend\_version
=============

Gets the version of the current Zend engine

### Description

<span class="type">string</span> <span
class="methodname">zend\_version</span> ( <span
class="methodparam">void</span> )

Returns a string containing the version of the currently running Zend
Engine.

### Return Values

Returns the Zend Engine version number, as a string.

### Examples

**Example \#1 <span class="function">zend\_version</span> example**

``` php
<?php
echo "Zend engine version: " . zend_version();
?>
```

The above example will output something similar to:

    Zend engine version: 2.2.0

### See Also

-   <span class="function">phpinfo</span>
-   <span class="function">phpcredits</span>
-   <span class="function">php\_logo\_guid</span>
-   <span class="function">phpversion</span>

**Table of Contents**

-   [assert\_options](/ref/info.html#assert_options) — Set/get the
    various assert flags
-   [assert](/ref/info.html#assert) — Checks if assertion is FALSE
-   [cli\_get\_process\_title](/ref/info.html#cli_get_process_title) —
    Returns the current process title
-   [cli\_set\_process\_title](/ref/info.html#cli_set_process_title) —
    Sets the process title
-   [dl](/ref/info.html#dl) — Loads a PHP extension at runtime
-   [extension\_loaded](/ref/info.html#extension_loaded) — Find out
    whether an extension is loaded
-   [gc\_collect\_cycles](/ref/info.html#gc_collect_cycles) — Forces
    collection of any existing garbage cycles
-   [gc\_disable](/ref/info.html#gc_disable) — Deactivates the circular
    reference collector
-   [gc\_enable](/ref/info.html#gc_enable) — Activates the circular
    reference collector
-   [gc\_enabled](/ref/info.html#gc_enabled) — Returns status of the
    circular reference collector
-   [gc\_mem\_caches](/ref/info.html#gc_mem_caches) — Reclaims memory
    used by the Zend Engine memory manager
-   [gc\_status](/ref/info.html#gc_status) — Gets information about the
    garbage collector
-   [get\_cfg\_var](/ref/info.html#get_cfg_var) — Gets the value of a
    PHP configuration option
-   [get\_current\_user](/ref/info.html#get_current_user) — Gets the
    name of the owner of the current PHP script
-   [get\_defined\_constants](/ref/info.html#get_defined_constants) —
    Returns an associative array with the names of all the constants and
    their values
-   [get\_extension\_funcs](/ref/info.html#get_extension_funcs) —
    Returns an array with the names of the functions of a module
-   [get\_include\_path](/ref/info.html#get_include_path) — Gets the
    current include\_path configuration option
-   [get\_included\_files](/ref/info.html#get_included_files) — Returns
    an array with the names of included or required files
-   [get\_loaded\_extensions](/ref/info.html#get_loaded_extensions) —
    Returns an array with the names of all modules compiled and loaded
-   [get\_magic\_quotes\_gpc](/ref/info.html#get_magic_quotes_gpc) —
    Gets the current configuration setting of magic\_quotes\_gpc
-   [get\_magic\_quotes\_runtime](/ref/info.html#get_magic_quotes_runtime)
    — Gets the current active configuration setting of
    magic\_quotes\_runtime
-   [get\_required\_files](/ref/info.html#get_required_files) — Alias of
    get\_included\_files
-   [get\_resources](/ref/info.html#get_resources) — Returns active
    resources
-   [getenv](/ref/info.html#getenv) — Gets the value of an environment
    variable
-   [getlastmod](/ref/info.html#getlastmod) — Gets time of last page
    modification
-   [getmygid](/ref/info.html#getmygid) — Get PHP script owner's GID
-   [getmyinode](/ref/info.html#getmyinode) — Gets the inode of the
    current script
-   [getmypid](/ref/info.html#getmypid) — Gets PHP's process ID
-   [getmyuid](/ref/info.html#getmyuid) — Gets PHP script owner's UID
-   [getopt](/ref/info.html#getopt) — Gets options from the command line
    argument list
-   [getrusage](/ref/info.html#getrusage) — Gets the current resource
    usages
-   [ini\_alter](/ref/info.html#ini_alter) — Alias of ini\_set
-   [ini\_get\_all](/ref/info.html#ini_get_all) — Gets all configuration
    options
-   [ini\_get](/ref/info.html#ini_get) — Gets the value of a
    configuration option
-   [ini\_restore](/ref/info.html#ini_restore) — Restores the value of a
    configuration option
-   [ini\_set](/ref/info.html#ini_set) — Sets the value of a
    configuration option
-   [main](/ref/info.html#main) — Dummy for main
-   [memory\_get\_peak\_usage](/ref/info.html#memory_get_peak_usage) —
    Returns the peak of memory allocated by PHP
-   [memory\_get\_usage](/ref/info.html#memory_get_usage) — Returns the
    amount of memory allocated to PHP
-   [php\_ini\_loaded\_file](/ref/info.html#php_ini_loaded_file) —
    Retrieve a path to the loaded php.ini file
-   [php\_ini\_scanned\_files](/ref/info.html#php_ini_scanned_files) —
    Return a list of .ini files parsed from the additional ini dir
-   [php\_sapi\_name](/ref/info.html#php_sapi_name) — Returns the type
    of interface between web server and PHP
-   [php\_uname](/ref/info.html#php_uname) — Returns information about
    the operating system PHP is running on
-   [phpcredits](/ref/info.html#phpcredits) — Prints out the credits for
    PHP
-   [phpinfo](/ref/info.html#phpinfo) — Outputs information about PHP's
    configuration
-   [phpversion](/ref/info.html#phpversion) — Gets the current PHP
    version
-   [putenv](/ref/info.html#putenv) — Sets the value of an environment
    variable
-   [restore\_include\_path](/ref/info.html#restore_include_path) —
    Restores the value of the include\_path configuration option
-   [set\_include\_path](/ref/info.html#set_include_path) — Sets the
    include\_path configuration option
-   [set\_time\_limit](/ref/info.html#set_time_limit) — Limits the
    maximum execution time
-   [sys\_get\_temp\_dir](/ref/info.html#sys_get_temp_dir) — Returns
    directory path used for temporary files
-   [version\_compare](/ref/info.html#version_compare) — Compares two
    "PHP-standardized" version number strings
-   [zend\_thread\_id](/ref/info.html#zend_thread_id) — Returns a unique
    identifier for the current thread
-   [zend\_version](/ref/info.html#zend_version) — Gets the version of
    the current Zend engine

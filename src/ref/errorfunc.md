See also <span class="function">syslog</span>.

debug\_backtrace
================

Generates a backtrace

### Description

<span class="type">array</span> <span
class="methodname">debug\_backtrace</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = DEBUG\_BACKTRACE\_PROVIDE\_OBJECT</span></span>
\[, <span class="methodparam"><span class="type">int</span>
`$limit`<span class="initializer"> = 0</span></span> \]\] )

<span class="function">debug\_backtrace</span> generates a PHP
backtrace.

### Parameters

`options`  
As of 5.3.6, this parameter is a bitmask for the following options:

|                                   |                                                                                                      |
|-----------------------------------|------------------------------------------------------------------------------------------------------|
| DEBUG\_BACKTRACE\_PROVIDE\_OBJECT | Whether or not to populate the "object" index.                                                       |
| DEBUG\_BACKTRACE\_IGNORE\_ARGS    | Whether or not to omit the "args" index, and thus all the function/method arguments, to save memory. |

Before 5.3.6, the only values recognized are **`TRUE`** or **`FALSE`**,
which are the same as setting or not setting the
**`DEBUG_BACKTRACE_PROVIDE_OBJECT`** option respectively.

`limit`  
As of 5.4.0, this parameter can be used to limit the number of stack
frames returned. By default (`limit`=*0*) it returns all stack frames.

### Return Values

Returns an array of associative <span class="type">array</span>s. The
possible returned elements are as follows:

| Name     | Type                              | Description                                                                                                                                              |
|----------|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| function | <span class="type">string</span>  | The current function name. See also <a href="/language/constants/predefined.html" class="link">__FUNCTION__</a>.                                         |
| line     | <span class="type">integer</span> | The current line number. See also <a href="/language/constants/predefined.html" class="link">__LINE__</a>.                                               |
| file     | <span class="type">string</span>  | The current file name. See also <a href="/language/constants/predefined.html" class="link">__FILE__</a>.                                                 |
| class    | <span class="type">string</span>  | The current <a href="/language/oop5.html" class="link">class</a> name. See also <a href="/language/constants/predefined.html" class="link">__CLASS__</a> |
| object   | <span class="type">object</span>  | The current <a href="/language/oop5.html" class="link">object</a>.                                                                                       |
| type     | <span class="type">string</span>  | The current call type. If a method call, "-\>" is returned. If a static method call, "::" is returned. If a function call, nothing is returned.          |
| args     | <span class="type">array</span>   | If inside a function, this lists the functions arguments. If inside an included file, this lists the included file name(s).                              |

### Examples

**Example \#1 <span class="function">debug\_backtrace</span> example**

``` php
<?php
// filename: /tmp/a.php

function a_test($str)
{
    echo "\nHi: $str";
    var_dump(debug_backtrace());
}

a_test('friend');
?>

<?php
// filename: /tmp/b.php
include_once '/tmp/a.php';
?>
```

Results similar to the following when executing `/tmp/b.php`:

    Hi: friend
    array(2) {
    [0]=>
    array(4) {
        ["file"] => string(10) "/tmp/a.php"
        ["line"] => int(10)
        ["function"] => string(6) "a_test"
        ["args"]=>
        array(1) {
          [0] => &string(6) "friend"
        }
    }
    [1]=>
    array(4) {
        ["file"] => string(10) "/tmp/b.php"
        ["line"] => int(2)
        ["args"] =>
        array(1) {
          [0] => string(10) "/tmp/a.php"
        }
        ["function"] => string(12) "include_once"
      }
    }

### See Also

-   <span class="function">trigger\_error</span>
-   <span class="function">debug\_print\_backtrace</span>

debug\_print\_backtrace
=======================

Prints a backtrace

### Description

<span class="type">void</span> <span
class="methodname">debug\_print\_backtrace</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = 0</span></span> \]\] )

<span class="function">debug\_print\_backtrace</span> prints a PHP
backtrace. It prints the function calls, included/required files and
<span class="function">eval</span>ed stuff.

### Parameters

`options`  
As of 5.3.6, this parameter is a bitmask for the following options:

|                                |                                                                                                      |
|--------------------------------|------------------------------------------------------------------------------------------------------|
| DEBUG\_BACKTRACE\_IGNORE\_ARGS | Whether or not to omit the "args" index, and thus all the function/method arguments, to save memory. |

`limit`  
As of 5.4.0, this parameter can be used to limit the number of stack
frames printed. By default (`limit`=*0*) it prints all stack frames.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">debug\_print\_backtrace</span>
example**

``` php
<?php
// include.php file

function a() {
    b();
}

function b() {
    c();
}

function c(){
    debug_print_backtrace();
}

a();

?>
```

``` php
<?php
// test.php file
// this is the file you should run

include 'include.php';
?>
```

The above example will output something similar to:

    #0  c() called at [/tmp/include.php:10]
    #1  b() called at [/tmp/include.php:6]
    #2  a() called at [/tmp/include.php:17]
    #3  include(/tmp/include.php) called at [/tmp/test.php:3]

### See Also

-   <span class="function">debug\_backtrace</span>

error\_clear\_last
==================

Clear the most recent error

### Description

<span class="type">void</span> <span
class="methodname">error\_clear\_last</span> ( <span
class="methodparam">void</span> )

### Return Values

Clears the most recent errors, making it unable to be retrieved with
<span class="function">error\_get\_last</span>.

### Examples

**Example \#1 An <span class="function">error\_clear\_last</span>
example**

``` php
<?php
var_dump(error_get_last());
error_clear_last();
var_dump(error_get_last());

@$a = $b;

var_dump(error_get_last());
error_clear_last();
var_dump(error_get_last());
?>
```

The above example will output something similar to:

    NULL
    NULL
    array(4) {
      ["type"]=>
      int(8)
      ["message"]=>
      string(21) "Undefined variable: b"
      ["file"]=>
      string(9) "%s"
      ["line"]=>
      int(6)
    }
    NULL

### See Also

-   <a href="/errorfunc/constants.html" class="link">Error constants</a>

error\_get\_last
================

Get the last occurred error

### Description

<span class="type">array</span> <span
class="methodname">error\_get\_last</span> ( <span
class="methodparam">void</span> )

Gets information about the last error that occurred.

### Return Values

Returns an associative array describing the last error with keys "type",
"message", "file" and "line". If the error has been caused by a PHP
internal function then the "message" begins with its name. Returns
**`NULL`** if there hasn't been an error yet.

### Examples

**Example \#1 An <span class="function">error\_get\_last</span>
example**

``` php
<?php
echo $a;
print_r(error_get_last());
?>
```

The above example will output something similar to:

    Array
    (
        [type] => 8
        [message] => Undefined variable: a
        [file] => C:\WWW\index.php
        [line] => 2
    )

### See Also

-   <a href="/errorfunc/constants.html" class="link">Error constants</a>
-   Variable `$php_errormsg`
-   <span class="function">error\_clear\_last</span>
-   <a href="/errorfunc/setup.html#" class="link">Directive <code class="parameter">display_errors</code></a>
-   <a href="/errorfunc/setup.html#" class="link">Directive <code class="parameter">html_errors</code></a>
-   <a href="/errorfunc/setup.html#" class="link">Directive <code class="parameter">xmlrpc_errors</code></a>

error\_log
==========

Send an error message to the defined error handling routines

### Description

<span class="type">bool</span> <span
class="methodname">error\_log</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">int</span> `$message_type`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">string</span> `$extra_headers`</span> \]\]\] )

Sends an error message to the web server's error log or to a file.

### Parameters

`message`  
The error message that should be logged.

`message_type`  
Says where the error should go. The possible message types are as
follows:

|     |                                                                                                                                                                                                                                                             |
|-----|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 0   | `message` is sent to PHP's system logger, using the Operating System's system logging mechanism or a file, depending on what the <a href="/errorfunc/setup.html#" class="link">error_log</a> configuration directive is set to. This is the default option. |
| 1   | `message` is sent by email to the address in the `destination` parameter. This is the only message type where the fourth parameter, `extra_headers` is used.                                                                                                |
| 2   | No longer an option.                                                                                                                                                                                                                                        |
| 3   | `message` is appended to the file `destination`. A newline is not automatically added to the end of the `message` string.                                                                                                                                   |
| 4   | `message` is sent directly to the SAPI logging handler.                                                                                                                                                                                                     |

`destination`  
The destination. Its meaning depends on the `message_type` parameter as
described above.

`extra_headers`  
The extra headers. It's used when the `message_type` parameter is set to
*1*. This message type uses the same internal function as <span
class="function">mail</span> does.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

**Warning**

<span class="function">error\_log</span> is not binary safe. `message`
will be truncated by null character.

**Tip**

`message` should not contain null character. Note that `message` may be
sent to file, mail, syslog, etc. Use appropriate conversion/escape
function, <span class="function">base64\_encode</span>, <span
class="function">rawurlencode</span> or <span
class="function">addslashes</span> before calling <span
class="function">error\_log</span>.

### Examples

**Example \#1 <span class="function">error\_log</span> examples**

``` php
<?php
// Send notification through the server log if we can not
// connect to the database.
if (!Ora_Logon($username, $password)) {
    error_log("Oracle database not available!", 0);
}

// Notify administrator by email if we run out of FOO
if (!($foo = allocate_new_foo())) {
    error_log("Big trouble, we're all out of FOOs!", 1,
               "operator@example.com");
}

// another way to call error_log():
error_log("You messed up!", 3, "/var/tmp/my-errors.log");
?>
```

error\_reporting
================

Sets which PHP errors are reported

### Description

<span class="type">int</span> <span
class="methodname">error\_reporting</span> (\[ <span
class="methodparam"><span class="type">int</span> `$level`</span> \] )

The <span class="function">error\_reporting</span> function sets the
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
directive at runtime. PHP has many levels of errors, using this function
sets that level for the duration (runtime) of your script. If the
optional `level` is not set, <span
class="function">error\_reporting</span> will just return the current
error reporting level.

### Parameters

`level`  
The new
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
level. It takes on either a bitmask, or named constants. Using named
constants is strongly encouraged to ensure compatibility for future
versions. As error levels are added, the range of integers increases, so
older integer-based error levels will not always behave as expected.

The available error level constants and the actual meanings of these
error levels are described in the
<a href="/errorfunc/constants.html" class="link">predefined constants</a>.

### Return Values

Returns the old
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
level or the current level if no `level` parameter is given.

### Examples

**Example \#1 <span class="function">error\_reporting</span> examples**

``` php
<?php

// Turn off all error reporting
error_reporting(0);

// Report simple running errors
error_reporting(E_ERROR | E_WARNING | E_PARSE);

// Reporting E_NOTICE can be good too (to report uninitialized
// variables or catch variable name misspellings ...)
error_reporting(E_ERROR | E_WARNING | E_PARSE | E_NOTICE);

// Report all errors except E_NOTICE
error_reporting(E_ALL & ~E_NOTICE);

// Report all PHP errors
error_reporting(E_ALL);

// Report all PHP errors
error_reporting(-1);

// Same as error_reporting(E_ALL);
ini_set('error_reporting', E_ALL);

?>
```

### Notes

**Warning**

Most of **`E_STRICT`** errors are evaluated at the compile time thus
such errors are not reported in the file where
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
is enhanced to include **`E_STRICT`** errors (and vice versa).

**Tip**

Passing in the value *-1* will show every possible error, even when new
levels and constants are added in future PHP versions. The **`E_ALL`**
constant also behaves this way as of PHP 5.4.

### See Also

-   The <a href="/errorfunc/setup.html#" class="link">display_errors</a>
    directive
-   The <a href="/errorfunc/setup.html#" class="link">html_errors</a>
    directive
-   The <a href="/errorfunc/setup.html#" class="link">xmlrpc_errors</a>
    directive
-   <span class="function">ini\_set</span>

restore\_error\_handler
=======================

Restores the previous error handler function

### Description

<span class="type">bool</span> <span
class="methodname">restore\_error\_handler</span> ( <span
class="methodparam">void</span> )

Used after changing the error handler function using <span
class="function">set\_error\_handler</span>, to revert to the previous
error handler (which could be the built-in or a user defined function).

### Return Values

This function always returns **`TRUE`**.

### Examples

**Example \#1 <span class="function">restore\_error\_handler</span>
example**

Decide if <span class="function">unserialize</span> caused an error,
then restore the original error handler.

``` php
<?php
function unserialize_handler($errno, $errstr)
{
    echo "Invalid serialized value.\n";
}

$serialized = 'foo';
set_error_handler('unserialize_handler');
$original = unserialize($serialized);
restore_error_handler();
?>
```

The above example will output:

    Invalid serialized value.

### See Also

-   <span class="function">error\_reporting</span>
-   <span class="function">set\_error\_handler</span>
-   <span class="function">restore\_exception\_handler</span>
-   <span class="function">trigger\_error</span>

restore\_exception\_handler
===========================

Restores the previously defined exception handler function

### Description

<span class="type">bool</span> <span
class="methodname">restore\_exception\_handler</span> ( <span
class="methodparam">void</span> )

Used after changing the exception handler function using <span
class="function">set\_exception\_handler</span>, to revert to the
previous exception handler (which could be the built-in or a user
defined function).

### Return Values

This function always returns **`TRUE`**.

### Examples

**Example \#1 <span class="function">restore\_exception\_handler</span>
example**

``` php
<?php
    function exception_handler_1(Exception $e)
    {
        echo '[' . __FUNCTION__ . '] ' . $e->getMessage();
    }

    function exception_handler_2(Exception $e)
    {
        echo '[' . __FUNCTION__ . '] ' . $e->getMessage();
    }

    set_exception_handler('exception_handler_1');
    set_exception_handler('exception_handler_2');

    restore_exception_handler();

    throw new Exception('This triggers the first exception handler...');
?>
```

The above example will output:

    [exception_handler_1] This triggers the first exception handler...

### See Also

-   <span class="function">set\_exception\_handler</span>
-   <span class="function">set\_error\_handler</span>
-   <span class="function">restore\_error\_handler</span>
-   <span class="function">error\_reporting</span>

set\_error\_handler
===================

Sets a user-defined error handler function

### Description

<span class="type">mixed</span> <span
class="methodname">set\_error\_handler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$error_handler`</span> \[, <span class="methodparam"><span
class="type">int</span> `$error_types`<span class="initializer"> =
E\_ALL \| E\_STRICT</span></span> \] )

Sets a user function (`error_handler`) to handle errors in a script.

This function can be used for defining your own way of handling errors
during runtime, for example in applications in which you need to do
cleanup of data/files when a critical error happens, or when you need to
trigger an error under certain conditions (using <span
class="function">trigger\_error</span>).

It is important to remember that the standard PHP error handler is
completely bypassed for the error types specified by `error_types`
unless the callback function returns **`FALSE`**. <span
class="function">error\_reporting</span> settings will have no effect
and your error handler will be called regardless - however you are still
able to read the current value of
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
and act appropriately. Of particular note is that this value will be 0
if the statement that caused the error was prepended by the
<a href="/language/operators/errorcontrol.html" class="link">@ error-control operator</a>.

Also note that it is your responsibility to <span
class="function">die</span> if necessary. If the error-handler function
returns, script execution will continue with the next statement after
the one that caused an error.

The following error types cannot be handled with a user defined
function: **`E_ERROR`**, **`E_PARSE`**, **`E_CORE_ERROR`**,
**`E_CORE_WARNING`**, **`E_COMPILE_ERROR`**, **`E_COMPILE_WARNING`**
independent of where they were raised, and most of **`E_STRICT`** raised
in the file where <span class="function">set\_error\_handler</span> is
called.

If errors occur before the script is executed (e.g. on file uploads) the
custom error handler cannot be called since it is not registered at that
time.

### Parameters

`error_handler`  
A callback with the following signature. **`NULL`** may be passed
instead, to reset this handler to its default state. Instead of a
function name, an array containing an object reference and a method name
can also be supplied.

<span class="type">bool</span> <span class="methodname"><span
class="replaceable">handler</span></span> ( <span
class="methodparam"><span class="type">int</span> `$errno`</span> ,
<span class="methodparam"><span class="type">string</span>
`$errstr`</span> \[, <span class="methodparam"><span
class="type">string</span> `$errfile`</span> \[, <span
class="methodparam"><span class="type">int</span> `$errline`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$errcontext`</span> \]\]\] )

`errno`  
<span class="simpara"> The first parameter, `errno`, contains the level
of the error raised, as an integer. </span>

`errstr`  
<span class="simpara"> The second parameter, `errstr`, contains the
error message, as a string. </span>

`errfile`  
<span class="simpara"> The third parameter is optional, `errfile`, which
contains the filename that the error was raised in, as a string. </span>

`errline`  
<span class="simpara"> The fourth parameter is optional, `errline`,
which contains the line number the error was raised at, as an integer.
</span>

`errcontext`  
<span class="simpara"> The fifth parameter is optional, `errcontext`,
which is an array that points to the active symbol table at the point
the error occurred. In other words, `errcontext` will contain an array
of every variable that existed in the scope the error was triggered in.
User error handler must not modify error context. </span>

**Warning**
This parameter has been *DEPRECATED* as of PHP 7.2.0. Relying on it is
highly discouraged.

If the function returns **`FALSE`** then the normal error handler
continues.

`error_types`  
Can be used to mask the triggering of the `error_handler` function just
like the
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
ini setting controls which errors are shown. Without this mask set the
`error_handler` will be called for every error regardless to the setting
of the
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
setting.

### Return Values

Returns a string containing the previously defined error handler (if
any). If the built-in error handler is used **`NULL`** is returned.
**`NULL`** is also returned in case of an error such as an invalid
callback. If the previous error handler was a class method, this
function will return an indexed array with the class and the method
name.

### Changelog

| Version | Description                                                                                     |
|---------|-------------------------------------------------------------------------------------------------|
| 7.2.0   | `errcontext` became deprecated. Usage of this parameter now emits an **`E_DEPRECATED`** notice. |

### Examples

**Example \#1 Error handling with <span
class="function">set\_error\_handler</span> and <span
class="function">trigger\_error</span>**

The example below shows the handling of internal exceptions by
triggering errors and handling them with a user defined function:

``` php
<?php
// error handler function
function myErrorHandler($errno, $errstr, $errfile, $errline)
{
    if (!(error_reporting() & $errno)) {
        // This error code is not included in error_reporting, so let it fall
        // through to the standard PHP error handler
        return false;
    }

    // $errstr may need to be escaped:
    $errstr = htmlspecialchars($errstr);

    switch ($errno) {
    case E_USER_ERROR:
        echo "<b>My ERROR</b> [$errno] $errstr<br />\n";
        echo "  Fatal error on line $errline in file $errfile";
        echo ", PHP " . PHP_VERSION . " (" . PHP_OS . ")<br />\n";
        echo "Aborting...<br />\n";
        exit(1);

    case E_USER_WARNING:
        echo "<b>My WARNING</b> [$errno] $errstr<br />\n";
        break;

    case E_USER_NOTICE:
        echo "<b>My NOTICE</b> [$errno] $errstr<br />\n";
        break;

    default:
        echo "Unknown error type: [$errno] $errstr<br />\n";
        break;
    }

    /* Don't execute PHP internal error handler */
    return true;
}

// function to test the error handling
function scale_by_log($vect, $scale)
{
    if (!is_numeric($scale) || $scale <= 0) {
        trigger_error("log(x) for x <= 0 is undefined, you used: scale = $scale", E_USER_ERROR);
    }

    if (!is_array($vect)) {
        trigger_error("Incorrect input vector, array of values expected", E_USER_WARNING);
        return null;
    }

    $temp = array();
    foreach($vect as $pos => $value) {
        if (!is_numeric($value)) {
            trigger_error("Value at position $pos is not a number, using 0 (zero)", E_USER_NOTICE);
            $value = 0;
        }
        $temp[$pos] = log($scale) * $value;
    }

    return $temp;
}

// set to the user defined error handler
$old_error_handler = set_error_handler("myErrorHandler");

// trigger some errors, first define a mixed array with a non-numeric item
echo "vector a\n";
$a = array(2, 3, "foo", 5.5, 43.3, 21.11);
print_r($a);

// now generate second array
echo "----\nvector b - a notice (b = log(PI) * a)\n";
/* Value at position $pos is not a number, using 0 (zero) */
$b = scale_by_log($a, M_PI);
print_r($b);

// this is trouble, we pass a string instead of an array
echo "----\nvector c - a warning\n";
/* Incorrect input vector, array of values expected */
$c = scale_by_log("not array", 2.3);
var_dump($c); // NULL

// this is a critical error, log of zero or negative number is undefined
echo "----\nvector d - fatal error\n";
/* log(x) for x <= 0 is undefined, you used: scale = $scale" */
$d = scale_by_log($a, -2.5);
var_dump($d); // Never reached
?>
```

The above example will output something similar to:

    vector a
    Array
    (
        [0] => 2
        [1] => 3
        [2] => foo
        [3] => 5.5
        [4] => 43.3
        [5] => 21.11
    )
    ----
    vector b - a notice (b = log(PI) * a)
    <b>My NOTICE</b> [1024] Value at position 2 is not a number, using 0 (zero)<br />
    Array
    (
        [0] => 2.2894597716988
        [1] => 3.4341896575482
        [2] => 0
        [3] => 6.2960143721717
        [4] => 49.566804057279
        [5] => 24.165247890281
    )
    ----
    vector c - a warning
    <b>My WARNING</b> [512] Incorrect input vector, array of values expected<br />
    NULL
    ----
    vector d - fatal error
    <b>My ERROR</b> [256] log(x) for x <= 0 is undefined, you used: scale = -2.5<br />
      Fatal error on line 35 in file trigger_error.php, PHP 5.2.1 (FreeBSD)<br />
    Aborting...<br />

### See Also

-   <span class="classname">ErrorException</span>
-   <span class="function">error\_reporting</span>
-   <span class="function">restore\_error\_handler</span>
-   <span class="function">trigger\_error</span>
-   <a href="/errorfunc/constants.html" class="link">error level constants</a>
-   information about the
    <a href="/language/pseudo-types.html#language.types.callback" class="link">callback</a>
    type

set\_exception\_handler
=======================

Sets a user-defined exception handler function

### Description

<span class="type">callable</span> <span
class="methodname">set\_exception\_handler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$exception_handler`</span> )

Sets the default exception handler if an exception is not caught within
a try/catch block. Execution will stop after the `exception_handler` is
called.

### Parameters

`exception_handler`  
Name of the function to be called when an uncaught exception occurs.
This handler function needs to accept one parameter, which will be the
exception object that was thrown. This is the handler signature before
PHP 7:

<span class="type">void</span> <span class="methodname"><span
class="replaceable">handler</span></span> ( <span
class="methodparam"><span class="type">Exception</span> `$ex`</span> )

Since PHP 7, most errors are reported by throwing <span
class="classname">Error</span> exceptions, which will be caught by the
handler as well. Both <span class="classname">Error</span> and <span
class="classname">Exception</span> implements the <span
class="classname">Throwable</span> interface. This is the handler
signature since PHP 7:

<span class="type">void</span> <span class="methodname"><span
class="replaceable">handler</span></span> ( <span
class="methodparam"><span class="type">Throwable</span> `$ex`</span> )

**`NULL`** may be passed instead, to reset this handler to its default
state.

**Caution**
Note that providing an explicit <span class="classname">Exception</span>
type hint for the `ex` parameter in your callback will cause issues with
the changed exception hierarchy in PHP 7.

### Return Values

Returns the name of the previously defined exception handler, or
**`NULL`** on error. If no previous handler was defined, **`NULL`** is
also returned.

### Changelog

| Version | Description                                                                                                                                             |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.0.0   | The type of parameter passed into `exception_handler` changed from <span class="classname">Exception</span> to <span class="classname">Throwable</span> |
| 5.5.0   | Previously, if **`NULL`** was passed then this function returned **`TRUE`**. It returns the previous handler since PHP 5.5.0.                           |

### Examples

**Example \#1 <span class="function">set\_exception\_handler</span>
example**

``` php
<?php
function exception_handler($exception) {
  echo "Uncaught exception: " , $exception->getMessage(), "\n";
}

set_exception_handler('exception_handler');

throw new Exception('Uncaught Exception');
echo "Not Executed\n";
?>
```

### See Also

-   <span class="function">restore\_exception\_handler</span>
-   <span class="function">restore\_error\_handler</span>
-   <span class="function">error\_reporting</span>
-   information about the
    <a href="/language/pseudo-types.html#language.types.callback" class="link">callback</a>
    type
-   <a href="/language/exceptions.html" class="link">PHP 5 Exceptions</a>

trigger\_error
==============

Generates a user-level error/warning/notice message

### Description

<span class="type">bool</span> <span
class="methodname">trigger\_error</span> ( <span
class="methodparam"><span class="type">string</span> `$error_msg`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$error_type`<span class="initializer"> = E\_USER\_NOTICE</span></span>
\] )

Used to trigger a user error condition, it can be used in conjunction
with the built-in error handler, or with a user defined function that
has been set as the new error handler (<span
class="function">set\_error\_handler</span>).

This function is useful when you need to generate a particular response
to an exception at runtime.

### Parameters

`error_msg`  
The designated error message for this error. It's limited to 1024 bytes
in length. Any additional characters beyond 1024 bytes will be
truncated.

`error_type`  
The designated error type for this error. It only works with the E\_USER
family of constants, and will default to **`E_USER_NOTICE`**.

### Return Values

This function returns **`FALSE`** if wrong `error_type` is specified,
**`TRUE`** otherwise.

### Examples

**Example \#1 <span class="function">trigger\_error</span> example**

See <span class="function">set\_error\_handler</span> for a more
extensive example.

``` php
<?php
if ($divisor == 0) {
    trigger_error("Cannot divide by zero", E_USER_ERROR);
}
?>
```

### Notes

**Warning**

HTML entities in `error_msg` are not escaped. Use <span
class="function">htmlentities</span> on the message if the error is to
be displayed in a browser.

### See Also

-   <span class="function">error\_reporting</span>
-   <span class="function">set\_error\_handler</span>
-   <span class="function">restore\_error\_handler</span>
-   The
    <a href="/errorfunc/constants.html" class="link">error level constants</a>

user\_error
===========

Alias of <span class="function">trigger\_error</span>

### Description

This function is an alias of: <span
class="function">trigger\_error</span>.

**Table of Contents**

-   [debug\_backtrace](/ref/errorfunc.html#debug_backtrace) — Generates
    a backtrace
-   [debug\_print\_backtrace](/ref/errorfunc.html#debug_print_backtrace)
    — Prints a backtrace
-   [error\_clear\_last](/ref/errorfunc.html#error_clear_last) — Clear
    the most recent error
-   [error\_get\_last](/ref/errorfunc.html#error_get_last) — Get the
    last occurred error
-   [error\_log](/ref/errorfunc.html#error_log) — Send an error message
    to the defined error handling routines
-   [error\_reporting](/ref/errorfunc.html#error_reporting) — Sets which
    PHP errors are reported
-   [restore\_error\_handler](/ref/errorfunc.html#restore_error_handler)
    — Restores the previous error handler function
-   [restore\_exception\_handler](/ref/errorfunc.html#restore_exception_handler)
    — Restores the previously defined exception handler function
-   [set\_error\_handler](/ref/errorfunc.html#set_error_handler) — Sets
    a user-defined error handler function
-   [set\_exception\_handler](/ref/errorfunc.html#set_exception_handler)
    — Sets a user-defined exception handler function
-   [trigger\_error](/ref/errorfunc.html#trigger_error) — Generates a
    user-level error/warning/notice message
-   [user\_error](/ref/errorfunc.html#user_error) — Alias of
    trigger\_error

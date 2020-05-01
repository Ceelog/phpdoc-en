connection\_aborted
===================

Check whether client disconnected

### Description

<span class="type">int</span> <span
class="methodname">connection\_aborted</span> ( <span
class="methodparam">void</span> )

Checks whether the client disconnected.

### Return Values

Returns 1 if client disconnected, 0 otherwise.

### See Also

-   <span class="function">connection\_status</span>
-   <span class="function">ignore\_user\_abort</span>
-   <a href="/features/connection-handling.html" class="link">Connection Handling</a>
    for a complete description of connection handling in PHP.

connection\_status
==================

Returns connection status bitfield

### Description

<span class="type">int</span> <span
class="methodname">connection\_status</span> ( <span
class="methodparam">void</span> )

Gets the connection status bitfield.

### Return Values

Returns the connection status bitfield, which can be used against the
*CONNECTION\_XXX* constants to determine the connection status.

### See Also

-   <span class="function">connection\_aborted</span>
-   <span class="function">ignore\_user\_abort</span>
-   <a href="/features/connection-handling.html" class="link">Connection Handling</a>
    for a complete description of connection handling in PHP.

constant
========

Returns the value of a constant

### Description

<span class="type">mixed</span> <span class="methodname">constant</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> )

Return the value of the constant indicated by `name`.

<span class="function">constant</span> is useful if you need to retrieve
the value of a constant, but do not know its name. I.e. it is stored in
a variable or returned by a function.

This function works also with
<a href="/language/oop5/constants.html" class="link">class constants</a>.

### Parameters

`name`  
The constant name.

### Return Values

Returns the value of the constant, or **`NULL`** if the constant is not
defined.

### Errors/Exceptions

An **`E_WARNING`** level error is generated if the constant is not
defined.

### Examples

**Example \#1 <span class="function">constant</span> example**

``` php
<?php

define("MAXSIZE", 100);

echo MAXSIZE;
echo constant("MAXSIZE"); // same thing as the previous line


interface bar {
    const test = 'foobar!';
}

class foo {
    const test = 'foobar!';
}

$const = 'test';

var_dump(constant('bar::'. $const)); // string(7) "foobar!"
var_dump(constant('foo::'. $const)); // string(7) "foobar!"

?>
```

### See Also

-   <span class="function">define</span>
-   <span class="function">defined</span>
-   The section on
    <a href="/language/constants.html" class="link">Constants</a>

define
======

Defines a named constant

### Description

<span class="type">bool</span> <span class="methodname">define</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> \[, <span
class="methodparam"><span class="type">bool</span>
`$case_insensitive`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Defines a named constant at runtime.

### Parameters

`name`  
The name of the constant.

> **Note**:
>
> It is possible to <span class="function">define</span> constants with
> reserved or even invalid names, whose value can (only) be retrieved
> with <span class="function">constant</span>. However, doing so is not
> recommended.

`value`  
The value of the constant. In PHP 5, `value` must be a <span
class="type">scalar</span> value (<span class="type">integer</span>,
<span class="type">float</span>, <span class="type">string</span>, <span
class="type">boolean</span>, or **`NULL`**). In PHP 7, <span
class="type">array</span> values are also accepted.

**Warning**
While it is possible to define <span class="type">resource</span>
constants, it is not recommended and may cause unpredictable behavior.

`case_insensitive`  
If set to **`TRUE`**, the constant will be defined case-insensitive. The
default behavior is case-sensitive; i.e. *CONSTANT* and *Constant*
represent different values.

**Warning**
Defining case-insensitive constants is deprecated as of PHP 7.3.0.

> **Note**:
>
> Case-insensitive constants are stored as lower-case.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                  |
|---------|------------------------------------------------------------------------------|
| 7.3.0   | `case_insensitive` has been deprecated and will be removed in version 8.0.0. |
| 7.0.0   | <span class="type">array</span> values are allowed.                          |

### Examples

**Example \#1 Defining Constants**

``` php
<?php
define("CONSTANT", "Hello world.");
echo CONSTANT; // outputs "Hello world."
echo Constant; // outputs "Constant" and issues a notice.

define("GREETING", "Hello you.", true);
echo GREETING; // outputs "Hello you."
echo Greeting; // outputs "Hello you."

// Works as of PHP 7
define('ANIMALS', array(
    'dog',
    'cat',
    'bird'
));
echo ANIMALS[1]; // outputs "cat"

?>
```

**Example \#2 Constants with Reserved Names**

This example illustrates the *possibility* to define a constant with the
same name as a
<a href="/language/constants/predefined.html" class="link">magic constant</a>.
Since the resulting behavior is obviously confusing, it is not
recommended to do this in practise, though.

``` php
<?php
var_dump(defined('__LINE__'));
var_dump(define('__LINE__', 'test'));
var_dump(constant('__LINE__'));
var_dump(__LINE__);
?>
```

The above example will output:

    bool(false)
    bool(true)
    string(4) "test"
    int(5)

### See Also

-   <span class="function">defined</span>
-   <span class="function">constant</span>
-   The section on
    <a href="/language/constants.html" class="link">Constants</a>

defined
=======

Checks whether a given named constant exists

### Description

<span class="type">bool</span> <span class="methodname">defined</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

Checks whether the given constant exists and is defined.

> **Note**:
>
> If you want to see if a variable exists, use <span
> class="function">isset</span> as <span class="function">defined</span>
> only applies to
> <a href="/language/constants.html" class="link">constants</a>. If you
> want to see if a function exists, use <span
> class="function">function\_exists</span>.

### Parameters

`name`  
The constant name.

### Return Values

Returns **`TRUE`** if the named constant given by `name` has been
defined, **`FALSE`** otherwise.

### Examples

**Example \#1 Checking Constants**

``` php
<?php
/* Note the use of quotes, this is important.  This example is checking
 * if the string 'TEST' is the name of a constant named TEST */
if (defined('TEST')) {
    echo TEST;
}
?>
```

### See Also

-   <span class="function">define</span>
-   <span class="function">constant</span>
-   <span class="function">get\_defined\_constants</span>
-   <span class="function">function\_exists</span>
-   The section on
    <a href="/language/constants.html" class="link">Constants</a>

die
===

Equivalent to *exit*

### Description

This language construct is equivalent to <span
class="function">exit</span>.

eval
====

Evaluate a string as PHP code

### Description

<span class="type">mixed</span> <span class="methodname">eval</span> (
<span class="methodparam"><span class="type">string</span>
`$code`</span> )

Evaluates the given `code` as PHP.

**Caution**

The <span class="function">eval</span> language construct is *very
dangerous* because it allows execution of arbitrary PHP code. *Its use
thus is discouraged.* If you have carefully verified that there is no
other option than to use this construct, pay special attention *not to
pass any user provided data* into it without properly validating it
beforehand.

### Parameters

`code`  
Valid PHP code to be evaluated.

The code must not be wrapped in opening and closing
<a href="/language/basic-syntax/phpmode.html" class="link">PHP tags</a>,
i.e. *'echo "Hi!";'* must be passed instead of *'\<?php echo "Hi!";
?\>'*. It is still possible to leave and re-enter PHP mode though using
the appropriate PHP tags, e.g. *'echo "In PHP mode!"; ?\>In HTML
mode!\<?php echo "Back in PHP mode!";'*.

Apart from that the passed code must be valid PHP. This includes that
all statements must be properly terminated using a semicolon. *'echo
"Hi!"'* for example will cause a parse error, whereas *'echo "Hi!";'*
will work.

A *return* statement will immediately terminate the evaluation of the
code.

The code will be executed in the scope of the code calling <span
class="function">eval</span>. Thus any variables defined or changed in
the <span class="function">eval</span> call will remain visible after it
terminates.

### Return Values

<span class="function">eval</span> returns **`NULL`** unless *return* is
called in the evaluated code, in which case the value passed to *return*
is returned. As of PHP 7, if there is a parse error in the evaluated
code, <span class="function">eval</span> throws a ParseError exception.
Before PHP 7, in this case <span class="function">eval</span> returned
**`FALSE`** and execution of the following code continued normally. It
is not possible to catch a parse error in <span
class="function">eval</span> using <span
class="function">set\_error\_handler</span>.

### Examples

**Example \#1 <span class="function">eval</span> example - simple text
merge**

``` php
<?php
$string = 'cup';
$name = 'coffee';
$str = 'This is a $string with my $name in it.';
echo $str. "\n";
eval("\$str = \"$str\";");
echo $str. "\n";
?>
```

The above example will output:

    This is a $string with my $name in it.
    This is a cup with my coffee in it.

### Notes

> **Note**: <span class="simpara">Because this is a language construct
> and not a function, it cannot be called using
> <a href="/functions/variable-functions.html" class="link">variable functions</a>.</span>

**Tip**

As with anything that outputs its result directly to the browser, the
<a href="/book/outcontrol.html" class="link">output-control functions</a>
can be used to capture the output of this function, and save it in a
<span class="type">string</span> (for example).

> **Note**:
>
> In case of a fatal error in the evaluated code, the whole script
> exits.

### See Also

-   <span class="function">call\_user\_func</span>

exit
====

Output a message and terminate the current script

### Description

<span class="type">void</span> <span class="methodname">exit</span> (\[
<span class="methodparam"><span class="type">string</span>
`$status`</span> \] )

<span class="type">void</span> <span class="methodname">exit</span> (
<span class="methodparam"><span class="type">int</span> `$status`</span>
)

Terminates execution of the script.
<a href="/ref/funchand.html#register_shutdown_function" class="link">Shutdown functions</a>
and
<a href="/language/oop5/decon.html#language.oop5.decon.destructor" class="link">object destructors</a>
will always be executed even if *exit* is called.

*exit* is a language construct and it can be called without parentheses
if no `status` is passed.

### Parameters

`status`  
If `status` is a string, this function prints the `status` just before
exiting.

If `status` is an <span class="type">integer</span>, that value will be
used as the exit status and not printed. Exit statuses should be in the
range 0 to 254, the exit status 255 is reserved by PHP and shall not be
used. The status 0 is used to terminate the program successfully.

### Return Values

No value is returned.

### Examples

**Example \#1 *exit* example**

``` php
<?php

$filename = '/path/to/data-file';
$file = fopen($filename, 'r')
    or exit("unable to open file ($filename)");

?>
```

**Example \#2 *exit* status example**

``` php
<?php

//exit program normally
exit;
exit();
exit(0);

//exit with an error code
exit(1);
exit(0376); //octal

?>
```

**Example \#3 Shutdown functions and destructors run regardless**

``` php
<?php
class Foo
{
    public function __destruct()
    {
        echo 'Destruct: ' . __METHOD__ . '()' . PHP_EOL;
    }
}

function shutdown()
{
    echo 'Shutdown: ' . __FUNCTION__ . '()' . PHP_EOL;
}

$foo = new Foo();
register_shutdown_function('shutdown');

exit();
echo 'This will not be output.';
?>
```

The above example will output:

     Shutdown: shutdown()
     Destruct: Foo::__destruct()
     

### Notes

> **Note**: <span class="simpara">Because this is a language construct
> and not a function, it cannot be called using
> <a href="/functions/variable-functions.html" class="link">variable functions</a>.</span>

> **Note**:
>
> This language construct is equivalent to <span
> class="function">die</span>.

### See Also

-   <span class="function">register\_shutdown\_function</span>

get\_browser
============

Tells what the user's browser is capable of

### Description

<span class="type">mixed</span> <span
class="methodname">get\_browser</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$user_agent`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$return_array`<span class="initializer"> =
**`FALSE`**</span></span> \]\] )

Attempts to determine the capabilities of the user's browser, by looking
up the browser's information in the `browscap.ini` file.

### Parameters

`user_agent`  
The User Agent to be analyzed. By default, the value of HTTP User-Agent
header is used; however, you can alter this (i.e., look up another
browser's info) by passing this parameter.

You can bypass this parameter with a **`NULL`** value.

`return_array`  
If set to **`TRUE`**, this function will return an <span
class="type">array</span> instead of an <span
class="type">object</span>.

### Return Values

The information is returned in an object or an array which will contain
various data elements representing, for instance, the browser's major
and minor version numbers and ID string; **`TRUE`**/**`FALSE`** values
for features such as frames, JavaScript, and cookies; and so forth.

The *cookies* value simply means that the browser itself is capable of
accepting cookies and does not mean the user has enabled the browser to
accept cookies or not. The only way to test if cookies are accepted is
to set one with <span class="function">setcookie</span>, reload, and
check for the value.

### Examples

**Example \#1 Listing all information about the users browser**

``` php
<?php
echo $_SERVER['HTTP_USER_AGENT'] . "\n\n";

$browser = get_browser(null, true);
print_r($browser);
?>
```

The above example will output something similar to:

    Mozilla/5.0 (Windows; U; Windows NT 5.1; en-US; rv:1.7) Gecko/20040803 Firefox/0.9.3

    Array
    (
        [browser_name_regex] => ^mozilla/5\.0 (windows; .; windows nt 5\.1; .*rv:.*) gecko/.* firefox/0\.9.*$
        [browser_name_pattern] => Mozilla/5.0 (Windows; ?; Windows NT 5.1; *rv:*) Gecko/* Firefox/0.9*
        [parent] => Firefox 0.9
        [platform] => WinXP
        [browser] => Firefox
        [version] => 0.9
        [majorver] => 0
        [minorver] => 9
        [cssversion] => 2
        [frames] => 1
        [iframes] => 1
        [tables] => 1
        [cookies] => 1
        [backgroundsounds] =>
        [vbscript] =>
        [javascript] => 1
        [javaapplets] => 1
        [activexcontrols] =>
        [cdf] =>
        [aol] =>
        [beta] => 1
        [win16] =>
        [crawler] =>
        [stripper] =>
        [wap] =>
        [netclr] =>
    )

### Notes

> **Note**:
>
> In order for this to work, your
> <a href="/misc/setup.html#" class="link">browscap</a> configuration
> setting in `php.ini` must point to the correct location of the
> `browscap.ini` file on your system.
>
> `browscap.ini` is not bundled with PHP, but you may find an up-to-date
> <a href="http://browscap.org/" class="link external">» php_browscap.ini</a>
> file here.
>
> While `browscap.ini` contains information on many browsers, it relies
> on user updates to keep the database current. The format of the file
> is fairly self-explanatory.

\_\_halt\_compiler
==================

Halts the compiler execution

### Description

<span class="type">void</span> <span
class="methodname">\_\_halt\_compiler</span> ( <span
class="methodparam">void</span> )

Halts the execution of the compiler. This can be useful to embed data in
PHP scripts, like the installation files.

Byte position of the data start can be determined by the
**`__COMPILER_HALT_OFFSET__`** constant which is defined only if there
is a <span class="function">\_\_halt\_compiler</span> presented in the
file.

### Return Values

No value is returned.

### Examples

**Example \#1 A <span class="function">\_\_halt\_compiler</span>
example**

``` php
<?php

// open this file
$fp = fopen(__FILE__, 'r');

// seek file pointer to data
fseek($fp, __COMPILER_HALT_OFFSET__);

// and output it
var_dump(stream_get_contents($fp));

// the end of the script execution
__halt_compiler(); the installation data (eg. tar, gz, PHP, etc.)
```

### Notes

> **Note**:
>
> <span class="function">\_\_halt\_compiler</span> can only be used from
> the outermost scope.

highlight\_file
===============

Syntax highlighting of a file

### Description

<span class="type">mixed</span> <span
class="methodname">highlight\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$return`<span class="initializer"> = **`FALSE`**</span></span> \] )

Prints out or returns a syntax highlighted version of the code contained
in `filename` using the colors defined in the built-in syntax
highlighter for PHP.

Many servers are configured to automatically highlight files with a
*phps* extension. For example, `example.phps` when viewed will show the
syntax highlighted source of the file. To enable this, add this line to
the `httpd.conf`:

``` description
AddType application/x-httpd-php-source .phps
```

### Parameters

`filename`  
Path to the PHP file to be highlighted.

`return`  
Set this parameter to **`TRUE`** to make this function return the
highlighted code.

### Return Values

If `return` is set to **`TRUE`**, returns the highlighted code as a
string instead of printing it out. Otherwise, it will return **`TRUE`**
on success, **`FALSE`** on failure.

### Notes

**Caution**

Care should be taken when using the <span
class="function">highlight\_file</span> function to make sure that you
do not inadvertently reveal sensitive information such as passwords or
any other type of information that might create a potential security
risk.

> **Note**:
>
> When the `return` parameter is used, this function uses internal
> output buffering so it cannot be used inside an <span
> class="function">ob\_start</span> callback function.

### See Also

-   <span class="function">highlight\_string</span>
-   <a href="/misc/setup.html#" class="link">Highlighting INI directives</a>

highlight\_string
=================

Syntax highlighting of a string

### Description

<span class="type">mixed</span> <span
class="methodname">highlight\_string</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$return`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Outputs or returns html markup for a syntax highlighted version of the
given PHP code using the colors defined in the built-in syntax
highlighter for PHP.

### Parameters

`str`  
The PHP code to be highlighted. This should include the opening tag.

`return`  
Set this parameter to **`TRUE`** to make this function return the
highlighted code.

### Return Values

If `return` is set to **`TRUE`**, returns the highlighted code as a
string instead of printing it out. Otherwise, it will return **`TRUE`**
on success, **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">highlight\_string</span> example**

``` php
<?php
highlight_string('<?php phpinfo(); ?>');
?>
```

The above example will output:

    <code><span style="color: #000000">
    <span style="color: #0000BB">&lt;?php phpinfo</span><span style="color: #007700">(); </span><span style="color: #0000BB">?&gt;</span>
    </span>
    </code>

### Notes

> **Note**:
>
> When the `return` parameter is used, this function uses internal
> output buffering so it cannot be used inside an <span
> class="function">ob\_start</span> callback function.

The HTML markup generated is subject to change.

### See Also

-   <span class="function">highlight\_file</span>
-   <a href="/misc/setup.html#" class="link">Highlighting INI directives</a>

hrtime
======

Get the system's high resolution time

### Description

<span class="type">mixed</span> <span class="methodname">hrtime</span>
(\[ <span class="methodparam"><span class="type">bool</span>
`$get_as_number`<span class="initializer"> = **`FALSE`**</span></span>
\] )

Returns the system's high resolution time, counted from an arbitrary
point in time. The delivered timestamp is monotonic and can not be
adjusted.

### Parameters

`get_as_number`  
Whether the high resolution time should be returned as <span
class="type">array</span> or number.

### Return Values

Returns an array of integers in the form \[seconds, nanoseconds\], if
the parameter `get_as_number` is false. Otherwise the nanoseconds are
returned as <span class="type">integer</span> (64bit platforms) or <span
class="type">float</span> (32bit platforms).

### Examples

**Example \#1 <span class="function">hrtime</span> usage**

``` php
<?php
echo hrtime(true), PHP_EOL;
print_r(hrtime());
?>
```

The above example will output something similar to:

    10444739687370679
    Array
    (
        [0] => 10444739
        [1] => 687464812
    )

### See Also

-   The
    <a href="/book/hrtime.html" class="link">High resolution timing</a>
    extension
-   <span class="function">microtime</span>

ignore\_user\_abort
===================

Set whether a client disconnect should abort script execution

### Description

<span class="type">int</span> <span
class="methodname">ignore\_user\_abort</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$value`</span> \] )

Sets whether a client disconnect should cause a script to be aborted.

When running PHP as a command line script, and the script's tty goes
away without the script being terminated then the script will die the
next time it tries to write anything, unless `value` is set to
**`TRUE`**

### Parameters

`value`  
If set, this function will set the
<a href="/misc/setup.html#" class="link">ignore_user_abort</a> ini
setting to the given `value`. If not, this function will only return the
previous setting without changing it.

### Return Values

Returns the previous setting, as an integer.

### Examples

**Example \#1 A <span class="function">ignore\_user\_abort</span>
example**

``` php
<?php
// Ignore user aborts and allow the script
// to run forever
ignore_user_abort(true);
set_time_limit(0);

echo 'Testing connection handling in PHP';

// Run a pointless loop that sometime 
// hopefully will make us click away from 
// page or click the "Stop" button.
while(1)
{
    // Did the connection fail?
    if(connection_status() != CONNECTION_NORMAL)
    {
        break;
    }

    // Sleep for 10 seconds
    sleep(10);
}

// If this is reached, then the 'break' 
// was triggered from inside the while loop

// So here we can log, or perform any other tasks
// we need without actually being dependent on the 
// browser.
?>
```

### Notes

PHP will not detect that the user has aborted the connection until an
attempt is made to send information to the client. Simply using an echo
statement does not guarantee that information is sent, see <span
class="function">flush</span>.

### See Also

-   <span class="function">connection\_aborted</span>
-   <span class="function">connection\_status</span>
-   <a href="/features/connection-handling.html" class="link">Connection Handling</a>
    for a complete description of connection handling in PHP.

pack
====

Pack data into binary string

### Description

<span class="type">string</span> <span class="methodname">pack</span> (
<span class="methodparam"><span class="type">string</span>
`$format`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \] )

Pack given arguments into a binary string according to `format`.

The idea for this function was taken from Perl and all formatting codes
work the same as in Perl. However, there are some formatting codes that
are missing such as Perl's "u" format code.

Note that the distinction between signed and unsigned values only
affects the function <span class="function">unpack</span>, where as
function <span class="function">pack</span> gives the same result for
signed and unsigned format codes.

### Parameters

`format`  
The `format` string consists of format codes followed by an optional
repeater argument. The repeater argument can be either an integer value
or *\** for repeating to the end of the input data. For a, A, h, H the
repeat count specifies how many characters of one data argument are
taken, for @ it is the absolute position where to put the next data, for
everything else the repeat count specifies how many data arguments are
consumed and packed into the resulting binary string.

Currently implemented formats are:

| Code | Description                                                  |
|------|--------------------------------------------------------------|
| a    | NUL-padded string                                            |
| A    | SPACE-padded string                                          |
| h    | Hex string, low nibble first                                 |
| H    | Hex string, high nibble first                                |
| c    | signed char                                                  |
| C    | unsigned char                                                |
| s    | signed short (always 16 bit, machine byte order)             |
| S    | unsigned short (always 16 bit, machine byte order)           |
| n    | unsigned short (always 16 bit, big endian byte order)        |
| v    | unsigned short (always 16 bit, little endian byte order)     |
| i    | signed integer (machine dependent size and byte order)       |
| I    | unsigned integer (machine dependent size and byte order)     |
| l    | signed long (always 32 bit, machine byte order)              |
| L    | unsigned long (always 32 bit, machine byte order)            |
| N    | unsigned long (always 32 bit, big endian byte order)         |
| V    | unsigned long (always 32 bit, little endian byte order)      |
| q    | signed long long (always 64 bit, machine byte order)         |
| Q    | unsigned long long (always 64 bit, machine byte order)       |
| J    | unsigned long long (always 64 bit, big endian byte order)    |
| P    | unsigned long long (always 64 bit, little endian byte order) |
| f    | float (machine dependent size and representation)            |
| g    | float (machine dependent size, little endian byte order)     |
| G    | float (machine dependent size, big endian byte order)        |
| d    | double (machine dependent size and representation)           |
| e    | double (machine dependent size, little endian byte order)    |
| E    | double (machine dependent size, big endian byte order)       |
| x    | NUL byte                                                     |
| X    | Back up one byte                                             |
| Z    | NUL-padded string (new in PHP 5.5)                           |
| @    | NUL-fill to absolute position                                |

`...`  

### Return Values

Returns a binary string containing data.

### Changelog

| Version      | Description                                                                                                            |
|--------------|------------------------------------------------------------------------------------------------------------------------|
| 7.2.0        | <span class="type">float</span> and <span class="type">double</span> types supports both Big Endian and Little Endian. |
| 7.0.15,7.1.1 | The "e", "E", "g" and "G" codes were added to enable byte order support for float and double.                          |
| 5.6.3        | The "q", "Q", "J" and "P" codes were added to enable working with 64-bit numbers.                                      |
| 5.5.0        | The "Z" code was added with equivalent functionality to "a" for Perl compatibility.                                    |

### Examples

**Example \#1 <span class="function">pack</span> example**

``` php
<?php
$binarydata = pack("nvc*", 0x1234, 0x5678, 65, 66);
?>
```

The resulting binary string will be 6 bytes long and contain the byte
sequence 0x12, 0x34, 0x78, 0x56, 0x41, 0x42.

### Notes

**Caution**

Note that PHP internally stores <span class="type">integer</span> values
as signed values of a machine-dependent size (C type *long*). Integer
literals and operations that yield numbers outside the bounds of the
<span class="type">integer</span> type will be stored as <span
class="type">float</span>. When packing these floats as integers, they
are first cast into the integer type. This may or may not result in the
desired byte pattern.

The most relevant case is when packing unsigned numbers that would be
representable with the <span class="type">integer</span> type if it were
unsigned. In systems where the <span class="type">integer</span> type
has a 32-bit size, the cast usually results in the same byte pattern as
if the <span class="type">integer</span> were unsigned (although this
relies on implementation-defined unsigned to signed conversions, as per
the C standard). In systems where the <span class="type">integer</span>
type has 64-bit size, the <span class="type">float</span> most likely
does not have a mantissa large enough to hold the value without loss of
precision. If those systems also have a native 64-bit C *int* type (most
UNIX-like systems don't), the only way to use the *I* pack format in the
upper range is to create <span class="type">integer</span> negative
values with the same byte representation as the desired unsigned value.

### See Also

-   <span class="function">unpack</span>

php\_check\_syntax
==================

Check the PHP syntax of (and execute) the specified file

### Description

<span class="type">bool</span> <span
class="methodname">php\_check\_syntax</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">string</span>
`&$error_message`</span> \] )

Performs a syntax (lint) check on the specified `filename` testing for
scripting errors.

This is similar to using **php -l** from the
<a href="/features/commandline.html" class="link">commandline</a> except
that this function will execute (but not output) the checked `filename`.

For example, if a function is defined in `filename`, this defined
function will be available to the file that executed <span
class="function">php\_check\_syntax</span>, but output from `filename`
will be suppressed.

> **Note**:
>
> For technical reasons, this function is deprecated and removed from
> PHP. Instead, use *php -l somefile.php* from the
> <a href="/features/commandline.html" class="link">commandline</a>.

### Parameters

`filename`  
The name of the file being checked.

`error_message`  
If the `error_message` parameter is used, it will contain the error
message generated by the syntax check. `error_message` is passed by
<a href="/language/references.html" class="link">reference</a>.

### Return Values

Returns **`TRUE`** if the lint check passed, and **`FALSE`** if the link
check failed or if `filename` cannot be opened.

### Changelog

| Version | Description                                                                                                               |
|---------|---------------------------------------------------------------------------------------------------------------------------|
| 5.0.5   | This function was removed from PHP.                                                                                       |
| 5.0.3   | Calling <span class="function">exit</span> after <span class="function">php\_check\_syntax</span> resulted in a Segfault. |
| 5.0.1   | `error_message` is passed by reference.                                                                                   |

### Examples

``` examples
php -l somefile.php
```

The above example will output something similar to:

``` examples
PHP Parse error: unexpected T_STRING in /tmp/somefile.php on line 81
```

### See Also

-   <span class="function">include</span>
-   <span class="function">is\_readable</span>

php\_strip\_whitespace
======================

Return source with stripped comments and whitespace

### Description

<span class="type">string</span> <span
class="methodname">php\_strip\_whitespace</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Returns the PHP source code in `filename` with PHP comments and
whitespace removed. This may be useful for determining the amount of
actual code in your scripts compared with the amount of comments. This
is similar to using **php -w** from the
<a href="/features/commandline.html" class="link">commandline</a>.

### Parameters

`filename`  
Path to the PHP file.

### Return Values

The stripped source code will be returned on success, or an empty string
on failure.

> **Note**:
>
> This function respects the value of the
> <a href="/ini/core.html#ini.short-open-tag" class="link">short_open_tag</a>
> ini directive.

> **Note**:
>
> This function works as described as of PHP 5.0.1. Before this it would
> only return an empty string. For more information on this bug and its
> prior behavior, see bug report
> <a href="https://bugs.php.net/29606" class="link external">» #29606</a>.

### Examples

**Example \#1 <span class="function">php\_strip\_whitespace</span>
example**

``` php
<?php
// PHP comment here

/*
 * Another PHP comment
 */

echo        php_strip_whitespace(__FILE__);
// Newlines are considered whitespace, and are removed too:
do_nothing();
?>
```

The above example will output:

    <?php
     echo php_strip_whitespace(__FILE__); do_nothing(); ?>

Notice the PHP comments are gone, as are the whitespace and newline
after the first echo statement.

sapi\_windows\_cp\_conv
=======================

Convert string from one codepage to another

### Description

<span class="type">string</span> <span
class="methodname">sapi\_windows\_cp\_conv</span> ( <span
class="methodparam"><span class="type">int\|string</span>
`$in_codepage`</span> , <span class="methodparam"><span
class="type">int\|string</span> `$out_codepage`</span> , <span
class="methodparam"><span class="type">string</span> `$subject`</span> )

Convert string from one codepage to another.

### Parameters

`in_codepage`  
The codepage of the `subject` string. Either the codepage name or
identifier.

`out_codepage`  
The codepage to convert the `subject` string to. Either the codepage
name or identifier.

`subject`  
The string to convert.

### Return Values

The `subject` string converted to `out_codepage`, or **`NULL`** on
failure.

### Errors/Exceptions

This function issues E\_WARNING level errors, if invalid codepages are
given, or if the subject is not valid for `in_codepage`.

### See Also

-   <span class="function">sapi\_windows\_cp\_get</span>
-   <span class="function">iconv</span>

sapi\_windows\_cp\_get
======================

Get process codepage

### Description

<span class="type">int</span> <span
class="methodname">sapi\_windows\_cp\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$kind`</span> )

Get the identifier of the codepage of the current process.

### Parameters

`kind`  
The kind of codepage: either *'ansi'* or *'oem'*.

### Return Values

Returns the codepage identifier.

### See Also

-   <span class="function">sapi\_windows\_cp\_set</span>

sapi\_windows\_cp\_is\_utf8
===========================

Indicates whether the codepage is UTF-8 compatible

### Description

<span class="type">bool</span> <span
class="methodname">sapi\_windows\_cp\_is\_utf8</span> ( <span
class="methodparam">void</span> )

Indicates whether the codepage of the current process is UTF-8
compatible.

### Parameters

This function has no parameters.

### Return Values

Returns whether the codepage of the current process is UTF-8 compatible.

### See Also

-   <span class="function">sapi\_windows\_cp\_get</span>

sapi\_windows\_cp\_set
======================

Set process codepage

### Description

<span class="type">bool</span> <span
class="methodname">sapi\_windows\_cp\_set</span> ( <span
class="methodparam"><span class="type">int</span> `$cp`</span> )

Set the codepage of the current process.

### Parameters

`cp`  
A codepage identifier.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">sapi\_windows\_cp\_get</span>

sapi\_windows\_generate\_ctrl\_event
====================================

Send a CTRL event to another process

### Description

<span class="type">bool</span> <span
class="methodname">sapi\_windows\_generate\_ctrl\_event</span> ( <span
class="methodparam"><span class="type">int</span> `$event`</span> \[,
<span class="methodparam"><span class="type">int</span> `$pid`<span
class="initializer"> = 0</span></span> \] )

Sends a CTRL event to another process in the same process group.

### Parameters

`event`  
The *CTRL* even to send; either **`PHP_WINDOWS_EVENT_CTRL_C`** or
**`PHP_WINDOWS_EVENT_CTRL_BREAK`**.

`pid`  
The ID of the process to which to send the event to. If *0* is given,
the event is sent to all processes of the process group.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Basic <span
class="function">sapi\_windows\_generate\_ctrl\_event</span> Usage**

This example shows how to pass along *CTRL+BREAK* events to a child
process. In this case the child process echoes *I'm still alive* every
second, until the user presses *CTRL+BREAK*, what causes only the child
process to be terminated.

``` php
<?php
// forward CTRL+BREAK events to the child process
sapi_windows_set_ctrl_handler('sapi_windows_generate_ctrl_event');

// create a child process which echoes every second
$cmd = ['php', '-r', 'while (true) { echo "I\'m still alive\n"; sleep(1); }'];
$descspec = array(['pipe', 'r'], ['pipe', 'w'], ['pipe', 'w']);
$options = ['create_process_group' => true];
$proc = proc_open($cmd, $descspec, $pipes, null, null, $options);
while (true) {
    echo fgets($pipes[1]);
}
?>
```

### See Also

-   <span class="function">proc\_open</span>
-   <span class="function">sapi\_windows\_set\_ctrl\_handler</span>

sapi\_windows\_set\_ctrl\_handler
=================================

Set or remove a CTRL event handler

### Description

<span class="type">bool</span> <span
class="methodname">sapi\_windows\_set\_ctrl\_handler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callable`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$add`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Sets or removes a *CTRL* event handler, which allows Windows CLI
processes to intercept or ignore *CTRL+C* and *CTRL+BREAK* events. Note
that in multithreaded environments, this is only possible when called
from the main thread.

### Parameters

`callable`  
A callback function to set or remove. If set, this function will be
called whenever a *CTRL+C* or *CTRL+BREAK* event occurs. The function is
supposed to have the following signature:

<span class="type">void</span> <span class="methodname">handler</span> (
<span class="methodparam"><span class="type">int</span> `$event`</span>
)

`event`  
<span class="simpara"> The *CTRL* event which has been received; either
**`PHP_WINDOWS_EVENT_CTRL_C`** or **`PHP_WINDOWS_EVENT_CTRL_BREAK`**.
</span>

Setting a **`NULL`** `callable` causes the process to ignore *CTRL+C*
events, but not *CTRL+BREAK* events.

`add`  
If **`TRUE`**, the handler is set. If **`FALSE`**, the handler is
removed.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Basic <span
class="function">sapi\_windows\_set\_ctrl\_handler</span> Usage**

This example shows how to intercept *CTRL* events.

``` php
<?php
function ctrl_handler(int $event)
{
    switch ($event) {
        case PHP_WINDOWS_EVENT_CTRL_C:
            echo "You have pressed CTRL+C\n";
            break;
        case PHP_WINDOWS_EVENT_CTRL_BREAK:
            echo "You have pressed CTRL+BREAK\n";
            break;
    }
}

sapi_windows_set_ctrl_handler('ctrl_handler');
while (true); // infinite loop, so the handler can be triggered
?>
```

### See Also

-   <span class="function">sapi\_windows\_generate\_ctrl\_event</span>

sapi\_windows\_vt100\_support
=============================

Get or set VT100 support for the specified stream associated to an
output buffer of a Windows console.

### Description

<span class="type">bool</span> <span
class="methodname">sapi\_windows\_vt100\_support</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$enable`</span> \] )

If `enable` is omitted, the function returns **`TRUE`** if the stream
`stream` has VT100 control codes enabled, **`FALSE`** otherwise.

If `enable` is specified, the function will try to enable or disable the
VT100 features of the stream `stream`. If the feature has been
successfully enabled (or disabled), the function will return **`TRUE`**,
or **`FALSE`** otherwise.

At startup, PHP tries to enable the VT100 feature of the
**`STDOUT`**/**`STDERR`** streams. By the way, if those streams are
redirected to a file, the VT100 features may not be enabled.

If VT100 support is enabled, it is possible to use control sequences as
they are known from the VT100 terminal. They allow the modification of
the terminal's output. On Windows these sequences are called Console
Virtual Terminal Sequences.

**Warning**

This function uses the **`ENABLE_VIRTUAL_TERMINAL_PROCESSING`** flag
implemented in the Windows 10 API, so the VT100 feature may not be
available on older Windows versions.

### Parameters

`stream`  
The stream on which the function will operate.

`enable`  
If specified, the VT100 feature will be enabled (if **`TRUE`**) or
disabled (if **`FALSE`**).

### Return Values

If `enable` is not specified: returns **`TRUE`** if the VT100 feature is
enabled, **`FALSE`** otherwise.

If `enable` is specified: Returns **`TRUE`** on success or **`FALSE`**
on failure.

### Examples

**Example \#1 <span
class="function">sapi\_windows\_vt100\_support</span> default state**

By default, **`STDOUT`** and **`STDERR`** have the VT100 feature
enabled.

``` sh
php -r "var_export(sapi_windows_vt100_support(STDOUT));echo ' ';var_export(sapi_windows_vt100_support(STDERR));"
```

The above example will output something similar to:

    true true

By the way, if a stream is redirected, the VT100 feature will not be
enabled:

``` sh
php -r "var_export(sapi_windows_vt100_support(STDOUT));echo ' ';var_export(sapi_windows_vt100_support(STDERR));" 2>NUL
```

The above example will output something similar to:

  
true false  

**Example \#2 <span
class="function">sapi\_windows\_vt100\_support</span> changing state**

You won't be able to enable the VT100 feature of **`STDOUT`** or
**`STDERR`** if the stream is redirected.

``` sh
php -r "var_export(sapi_windows_vt100_support(STDOUT, true));echo ' ';var_export(sapi_windows_vt100_support(STDERR, true));" 2>NUL
```

The above example will output something similar to:

    true false

**Example \#3 Example usage of VT100 support enabled**

``` php
<?php
$out = fopen('php://stdout','w');
fwrite($out, 'Just forgot a lettr.');
// Moves the cursor two characters backwards
fwrite($out, "\033[2D");
// Inserts one blank, shifting existing text to the right -> Just forgot a lett r.
fwrite($out, "\033[1@");
fwrite($out, 'e');
?>
```

The above example will output:

    Just forgot a letter.

show\_source
============

Alias of <span class="function">highlight\_file</span>

### Description

This function is an alias of: <span
class="function">highlight\_file</span>.

sleep
=====

Delay execution

### Description

<span class="type">int</span> <span class="methodname">sleep</span> (
<span class="methodparam"><span class="type">int</span>
`$seconds`</span> )

Delays the program execution for the given number of `seconds`.

### Parameters

`seconds`  
Halt time in seconds.

### Return Values

Returns zero on success, or **`FALSE`** on error.

If the call was interrupted by a signal, <span
class="function">sleep</span> returns a non-zero value. On Windows, this
value will always be *192* (the value of the **`WAIT_IO_COMPLETION`**
constant within the Windows API). On other platforms, the return value
will be the number of seconds left to sleep.

### Errors/Exceptions

If the specified number of `seconds` is negative, this function will
generate a **`E_WARNING`**.

### Changelog

| Version | Description                                                                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.3.4   | Before PHP 5.3.4, on Windows, <span class="function">sleep</span> always returns **`NULL`** when sleep has occurred, regardless of whether the sleep was interrupted or not. |

### Examples

**Example \#1 <span class="function">sleep</span> example**

``` php
<?php

// current time
echo date('h:i:s') . "\n";

// sleep for 10 seconds
sleep(10);

// wake up !
echo date('h:i:s') . "\n";

?>
```

This example will output (after 10 seconds)

    05:31:23
    05:31:33

### See Also

-   <span class="function">usleep</span>
-   <span class="function">time\_nanosleep</span>
-   <span class="function">time\_sleep\_until</span>
-   <span class="function">set\_time\_limit</span>

sys\_getloadavg
===============

Gets system load average

### Description

<span class="type">array</span> <span
class="methodname">sys\_getloadavg</span> ( <span
class="methodparam">void</span> )

Returns three samples representing the average system load (the number
of processes in the system run queue) over the last 1, 5 and 15 minutes,
respectively.

### Return Values

Returns an <span class="type">array</span> with three samples (last 1, 5
and 15 minutes).

### Examples

**Example \#1 A <span class="function">sys\_getloadavg</span> example**

``` php
<?php
$load = sys_getloadavg();
if ($load[0] > 0.80) {
    header('HTTP/1.1 503 Too busy, try again later');
    die('Server too busy. Please try again later.');
}
?>
```

### Notes

> **Note**: <span class="simpara">This function is not implemented on
> Windows platforms.</span>

time\_nanosleep
===============

Delay for a number of seconds and nanoseconds

### Description

<span class="type">mixed</span> <span
class="methodname">time\_nanosleep</span> ( <span
class="methodparam"><span class="type">int</span> `$seconds`</span> ,
<span class="methodparam"><span class="type">int</span>
`$nanoseconds`</span> )

Delays program execution for the given number of `seconds` and
`nanoseconds`.

### Parameters

`seconds`  
Must be a non-negative integer.

`nanoseconds`  
Must be a non-negative integer less than 1 billion.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

If the delay was interrupted by a signal, an associative array will be
returned with the components:

-   <span class="simpara"> *seconds* - number of seconds remaining in
    the delay </span>
-   <span class="simpara"> *nanoseconds* - number of nanoseconds
    remaining in the delay </span>

### Changelog

| Version | Description                                          |
|---------|------------------------------------------------------|
| 5.3.0   | This function is now available on Windows platforms. |

### Examples

**Example \#1 <span class="function">time\_nanosleep</span> example**

``` php
<?php
// Careful! This won't work as expected if an array is returned
if (time_nanosleep(0, 500000000)) {
    echo "Slept for half a second.\n";
}

// This is better:
if (time_nanosleep(0, 500000000) === true) {
    echo "Slept for half a second.\n";
}

// And this is the best:
$nano = time_nanosleep(2, 100000);

if ($nano === true) {
    echo "Slept for 2 seconds, 100 microseconds.\n";
} elseif ($nano === false) {
    echo "Sleeping failed.\n";
} elseif (is_array($nano)) {
    $seconds = $nano['seconds'];
    $nanoseconds = $nano['nanoseconds'];
    echo "Interrupted by a signal.\n";
    echo "Time remaining: $seconds seconds, $nanoseconds nanoseconds.";
}
?>
```

### See Also

-   <span class="function">sleep</span>
-   <span class="function">usleep</span>
-   <span class="function">time\_sleep\_until</span>
-   <span class="function">set\_time\_limit</span>

time\_sleep\_until
==================

Make the script sleep until the specified time

### Description

<span class="type">bool</span> <span
class="methodname">time\_sleep\_until</span> ( <span
class="methodparam"><span class="type">float</span> `$timestamp`</span>
)

Makes the script sleep until the specified `timestamp`.

### Parameters

`timestamp`  
The timestamp when the script should wake.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                          |
|---------|------------------------------------------------------|
| 5.3.0   | This function is now available on Windows platforms. |

### Errors/Exceptions

If the specified `timestamp` is in the past, this function will generate
a **`E_WARNING`**.

### Examples

**Example \#1 A <span class="function">time\_sleep\_until</span>
example**

``` php
<?php

//returns false and generates a warning
var_dump(time_sleep_until(time()-1));

// may only work on faster computers, will sleep up to 0.2 seconds
var_dump(time_sleep_until(microtime(true)+0.2));

?>
```

### Notes

> **Note**: <span class="simpara"> All signals will be delivered after
> the script wakes up. </span>

### See Also

-   <span class="function">sleep</span>
-   <span class="function">usleep</span>
-   <span class="function">time\_nanosleep</span>
-   <span class="function">set\_time\_limit</span>

uniqid
======

Generate a unique ID

### Description

<span class="type">string</span> <span class="methodname">uniqid</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$prefix`<span class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$more_entropy`<span
class="initializer"> = **`FALSE`**</span></span> \]\] )

Gets a prefixed unique identifier based on the current time in
microseconds.

**Caution**

This function does not generate cryptographically secure values, and
should not be used for cryptographic purposes. If you need a
cryptographically secure value, consider using <span
class="function">random\_int</span>, <span
class="function">random\_bytes</span>, or <span
class="function">openssl\_random\_pseudo\_bytes</span> instead.

**Warning**

This function does not guarantee uniqueness of return value. Since most
systems adjust system clock by NTP or like, system time is changed
constantly. Therefore, it is possible that this function does not return
unique ID for the process/thread. Use `more_entropy` to increase
likelihood of uniqueness.

### Parameters

`prefix`  
Can be useful, for instance, if you generate identifiers simultaneously
on several hosts that might happen to generate the identifier at the
same microsecond.

With an empty `prefix`, the returned string will be 13 characters long.
If `more_entropy` is **`TRUE`**, it will be 23 characters.

`more_entropy`  
If set to **`TRUE`**, <span class="function">uniqid</span> will add
additional entropy (using the combined linear congruential generator) at
the end of the return value, which increases the likelihood that the
result will be unique.

### Return Values

Returns timestamp based unique identifier as a string.

**Warning**

This function tries to create unique identifier, but it does not
guarantee 100% uniqueness of return value.

### Examples

**Example \#1 <span class="function">uniqid</span> Example**

``` php
<?php
/* A uniqid, like: 4b3403665fea6 */
printf("uniqid(): %s\r\n", uniqid());

/* We can also prefix the uniqid, this the same as 
 * doing:
 *
 * $uniqid = $prefix . uniqid();
 * $uniqid = uniqid($prefix);
 */
printf("uniqid('php_'): %s\r\n", uniqid('php_'));

/* We can also activate the more_entropy parameter, which is 
 * required on some systems, like Cygwin. This makes uniqid()
 * produce a value like: 4b340550242239.64159797
 */
printf("uniqid('', true): %s\r\n", uniqid('', true));
?>
```

### Notes

> **Note**:
>
> Under Cygwin, the `more_entropy` must be set to **`TRUE`** for this
> function to work.

unpack
======

Unpack data from binary string

### Description

<span class="type">array</span> <span class="methodname">unpack</span> (
<span class="methodparam"><span class="type">string</span>
`$format`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 0</span></span> \] )

Unpacks from a binary string into an array according to the given
`format`.

The unpacked data is stored in an associative array. To accomplish this
you have to name the different format codes and separate them by a slash
/. If a repeater argument is present, then each of the array keys will
have a sequence number behind the given name.

### Parameters

`format`  
See <span class="function">pack</span> for an explanation of the format
codes.

`data`  
The packed data.

`offset`  
The offset to begin unpacking from.

### Return Values

Returns an associative array containing unpacked elements of binary
string.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>7.2.0</td>
<td><span class="type">float</span> and <span class="type">double</span> types supports both Big Endian and Little Endian.</td>
</tr>
<tr class="even">
<td>7.1.0</td>
<td>The optional <code class="parameter">offset</code> has been added.</td>
</tr>
<tr class="odd">
<td>5.5.0</td>
<td><p>Changes were made to bring this function into line with Perl:</p>
<p>The "a" code now retains trailing NULL bytes.</p>
<p>The "A" code now strips all trailing ASCII whitespace (spaces, tabs, newlines, carriage returns, and NULL bytes).</p>
<p>The "Z" code was added for NULL-padded strings, and removes trailing NULL bytes.</p></td>
</tr>
</tbody>
</table>

### Examples

**Example \#1 <span class="function">unpack</span> example**

``` php
<?php
$binarydata = "\x04\x00\xa0\x00";
$array = unpack("cchars/nint", $binarydata);
print_r($array);
?>
```

The above example will output:

    Array
    (
        [chars] => 4
        [int] => 160
    )

**Example \#2 <span class="function">unpack</span> example with a
repeater**

``` php
<?php
$binarydata = "\x04\x00\xa0\x00";
$array = unpack("c2chars/nint", $binarydata);
print_r($array);
?>
```

The above example will output:

    Array
    (
        [chars1] => 4
        [chars2] => 0
        [int] => 40960
    )

### Notes

**Caution**

Note that PHP internally stores integral values as signed. If you unpack
a large unsigned long and it is of the same size as PHP internally
stored values the result will be a negative number even though unsigned
unpacking was specified.

**Caution**

If you do not name an element, numeric indices starting from *1* are
used. Be aware that if you have more than one unnamed element, some data
is overwritten because the numbering restarts from *1* for each element.

**Example \#3 <span class="function">unpack</span> example with unnamed
keys**

``` php
<?php
$binarydata = "\x32\x42\x00\xa0";
$array = unpack("c2/n", $binarydata);
var_dump($array);
?>
```

The above example will output:

    array(2) {
      [1]=>
      int(160)
      [2]=>
      int(66)
    }

Note that the first value from the *c* specifier is overwritten by the
first value from the *n* specifier.

### See Also

-   <span class="function">pack</span>

usleep
======

Delay execution in microseconds

### Description

<span class="type">void</span> <span class="methodname">usleep</span> (
<span class="methodparam"><span class="type">int</span>
`$micro_seconds`</span> )

Delays program execution for the given number of microseconds.

### Parameters

`micro_seconds`  
Halt time in microseconds. A microsecond is one millionth of a second.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">usleep</span> example**

``` php
<?php

// Current time
echo date('h:i:s') . "\n";

// wait for 2 seconds
usleep(2000000);

// back!
echo date('h:i:s') . "\n";

?>
```

The above example will output:

    11:13:28
    11:13:30

### See Also

-   <span class="function">sleep</span>
-   <span class="function">time\_nanosleep</span>
-   <span class="function">time\_sleep\_until</span>
-   <span class="function">set\_time\_limit</span>

**Table of Contents**

-   [connection\_aborted](/ref/misc.html#connection_aborted) — Check
    whether client disconnected
-   [connection\_status](/ref/misc.html#connection_status) — Returns
    connection status bitfield
-   [constant](/ref/misc.html#constant) — Returns the value of a
    constant
-   [define](/ref/misc.html#define) — Defines a named constant
-   [defined](/ref/misc.html#defined) — Checks whether a given named
    constant exists
-   [die](/ref/misc.html#die) — Equivalent to exit
-   [eval](/ref/misc.html#eval) — Evaluate a string as PHP code
-   [exit](/ref/misc.html#exit) — Output a message and terminate the
    current script
-   [get\_browser](/ref/misc.html#get_browser) — Tells what the user's
    browser is capable of
-   [\_\_halt\_compiler](/ref/misc.html#__halt_compiler) — Halts the
    compiler execution
-   [highlight\_file](/ref/misc.html#highlight_file) — Syntax
    highlighting of a file
-   [highlight\_string](/ref/misc.html#highlight_string) — Syntax
    highlighting of a string
-   [hrtime](/ref/misc.html#hrtime) — Get the system's high resolution
    time
-   [ignore\_user\_abort](/ref/misc.html#ignore_user_abort) — Set
    whether a client disconnect should abort script execution
-   [pack](/ref/misc.html#pack) — Pack data into binary string
-   [php\_check\_syntax](/ref/misc.html#php_check_syntax) — Check the
    PHP syntax of (and execute) the specified file
-   [php\_strip\_whitespace](/ref/misc.html#php_strip_whitespace) —
    Return source with stripped comments and whitespace
-   [sapi\_windows\_cp\_conv](/ref/misc.html#sapi_windows_cp_conv) —
    Convert string from one codepage to another
-   [sapi\_windows\_cp\_get](/ref/misc.html#sapi_windows_cp_get) — Get
    process codepage
-   [sapi\_windows\_cp\_is\_utf8](/ref/misc.html#sapi_windows_cp_is_utf8)
    — Indicates whether the codepage is UTF-8 compatible
-   [sapi\_windows\_cp\_set](/ref/misc.html#sapi_windows_cp_set) — Set
    process codepage
-   [sapi\_windows\_generate\_ctrl\_event](/ref/misc.html#sapi_windows_generate_ctrl_event)
    — Send a CTRL event to another process
-   [sapi\_windows\_set\_ctrl\_handler](/ref/misc.html#sapi_windows_set_ctrl_handler)
    — Set or remove a CTRL event handler
-   [sapi\_windows\_vt100\_support](/ref/misc.html#sapi_windows_vt100_support)
    — Get or set VT100 support for the specified stream associated to an
    output buffer of a Windows console.
-   [show\_source](/ref/misc.html#show_source) — Alias of
    highlight\_file
-   [sleep](/ref/misc.html#sleep) — Delay execution
-   [sys\_getloadavg](/ref/misc.html#sys_getloadavg) — Gets system load
    average
-   [time\_nanosleep](/ref/misc.html#time_nanosleep) — Delay for a
    number of seconds and nanoseconds
-   [time\_sleep\_until](/ref/misc.html#time_sleep_until) — Make the
    script sleep until the specified time
-   [uniqid](/ref/misc.html#uniqid) — Generate a unique ID
-   [unpack](/ref/misc.html#unpack) — Unpack data from binary string
-   [usleep](/ref/misc.html#usleep) — Delay execution in microseconds

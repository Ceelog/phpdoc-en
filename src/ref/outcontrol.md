See also <span class="function">header</span> and <span
class="function">setcookie</span>.

flush
=====

Flush system output buffer

### Description

<span class="type">void</span> <span class="methodname">flush</span> (
<span class="methodparam">void</span> )

Flushes the system write buffers of PHP and whatever backend PHP is
using (CGI, a web server, etc). This attempts to push current output all
the way to the browser with a few caveats.

<span class="function">flush</span> may not be able to override the
buffering scheme of your web server and it has no effect on any
client-side buffering in the browser. It also doesn't affect PHP's
userspace output buffering mechanism. This means you will have to call
both <span class="function">ob\_flush</span> and <span
class="function">flush</span> to flush the ob output buffers if you are
using those.

Several servers, especially on Win32, will still buffer the output from
your script until it terminates before transmitting the results to the
browser.

Server modules for Apache like mod\_gzip may do buffering of their own
that will cause <span class="function">flush</span> to not result in
data being sent immediately to the client.

Even the browser may buffer its input before displaying it. Netscape,
for example, buffers text until it receives an end-of-line or the
beginning of a tag, and it won't render tables until the \</table\> tag
of the outermost table is seen.

Some versions of Microsoft Internet Explorer will only start to display
the page after they have received 256 bytes of output, so you may need
to send extra whitespace before flushing to get those browsers to
display the page.

### Return Values

No value is returned.

### See Also

-   <span class="function">ob\_flush</span>
-   <span class="function">ob\_clean</span>
-   <span class="function">ob\_end\_flush</span>
-   <span class="function">ob\_end\_clean</span>

ob\_clean
=========

Clean (erase) the output buffer

### Description

<span class="type">void</span> <span class="methodname">ob\_clean</span>
( <span class="methodparam">void</span> )

This function discards the contents of the output buffer.

This function does not destroy the output buffer like <span
class="function">ob\_end\_clean</span> does.

The output buffer must be started by <span
class="function">ob\_start</span> with
<a href="/outcontrol/constants.html#" class="link">PHP_OUTPUT_HANDLER_CLEANABLE</a>
flag. Otherwise <span class="function">ob\_clean</span> will not work.

### Return Values

No value is returned.

### See Also

-   <span class="function">ob\_flush</span>
-   <span class="function">ob\_end\_flush</span>
-   <span class="function">ob\_end\_clean</span>

ob\_end\_clean
==============

Clean (erase) the output buffer and turn off output buffering

### Description

<span class="type">bool</span> <span
class="methodname">ob\_end\_clean</span> ( <span
class="methodparam">void</span> )

This function discards the contents of the topmost output buffer and
turns off this output buffering. If you want to further process the
buffer's contents you have to call <span
class="function">ob\_get\_contents</span> before <span
class="function">ob\_end\_clean</span> as the buffer contents are
discarded when <span class="function">ob\_end\_clean</span> is called.

The output buffer must be started by <span
class="function">ob\_start</span> with
<a href="/outcontrol/constants.html#" class="link">PHP_OUTPUT_HANDLER_CLEANABLE</a>
and
<a href="/outcontrol/constants.html#" class="link">PHP_OUTPUT_HANDLER_REMOVABLE</a>
flags. Otherwise <span class="function">ob\_end\_clean</span> will not
work.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Reasons for
failure are first that you called the function without an active buffer
or that for some reason a buffer could not be deleted (possible for
special buffer).

### Errors/Exceptions

If the function fails it generates an **`E_NOTICE`**.

### Examples

The following example shows an easy way to get rid of all output
buffers:

**Example \#1 <span class="function">ob\_end\_clean</span> example**

``` php
<?php
ob_start();
echo 'Text that won\'t get displayed.';
ob_end_clean();
?>
```

### See Also

-   <span class="function">ob\_start</span>
-   <span class="function">ob\_get\_contents</span>
-   <span class="function">ob\_flush</span>

ob\_end\_flush
==============

Flush (send) the output buffer and turn off output buffering

### Description

<span class="type">bool</span> <span
class="methodname">ob\_end\_flush</span> ( <span
class="methodparam">void</span> )

This function will send the contents of the topmost output buffer (if
any) and turn this output buffer off. If you want to further process the
buffer's contents you have to call <span
class="function">ob\_get\_contents</span> before <span
class="function">ob\_end\_flush</span> as the buffer contents are
discarded after <span class="function">ob\_end\_flush</span> is called.

The output buffer must be started by <span
class="function">ob\_start</span> with
<a href="/outcontrol/constants.html#" class="link">PHP_OUTPUT_HANDLER_FLUSHABLE</a>
and
<a href="/outcontrol/constants.html#" class="link">PHP_OUTPUT_HANDLER_REMOVABLE</a>
flags. Otherwise <span class="function">ob\_end\_flush</span> will not
work.

> **Note**: <span class="simpara"> This function is similar to <span
> class="function">ob\_get\_flush</span>, except that <span
> class="function">ob\_get\_flush</span> returns the buffer as a string.
> </span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Reasons for
failure are first that you called the function without an active buffer
or that for some reason a buffer could not be deleted (possible for
special buffer).

### Errors/Exceptions

If the function fails it generates an **`E_NOTICE`**.

### Examples

**Example \#1 <span class="function">ob\_end\_flush</span> example**

The following example shows an easy way to flush and end all output
buffers:

``` php
<?php
  while (@ob_end_flush());
?>
```

### See Also

-   <span class="function">ob\_start</span>
-   <span class="function">ob\_get\_contents</span>
-   <span class="function">ob\_get\_flush</span>
-   <span class="function">ob\_flush</span>
-   <span class="function">ob\_end\_clean</span>

ob\_flush
=========

Flush (send) the output buffer

### Description

<span class="type">void</span> <span class="methodname">ob\_flush</span>
( <span class="methodparam">void</span> )

This function will send the contents of the output buffer (if any). If
you want to further process the buffer's contents you have to call <span
class="function">ob\_get\_contents</span> before <span
class="function">ob\_flush</span> as the buffer contents are discarded
after <span class="function">ob\_flush</span> is called.

This function does not destroy the output buffer like <span
class="function">ob\_end\_flush</span> does.

### Return Values

No value is returned.

### See Also

-   <span class="function">ob\_get\_contents</span>
-   <span class="function">ob\_clean</span>
-   <span class="function">ob\_end\_flush</span>
-   <span class="function">ob\_end\_clean</span>

ob\_get\_clean
==============

Get current buffer contents and delete current output buffer

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">ob\_get\_clean</span> ( <span
class="methodparam">void</span> )

Gets the current buffer contents and delete current output buffer.

<span class="function">ob\_get\_clean</span> essentially executes both
<span class="function">ob\_get\_contents</span> and <span
class="function">ob\_end\_clean</span>.

The output buffer must be started by <span
class="function">ob\_start</span> with
<a href="/outcontrol/constants.html#" class="link">PHP_OUTPUT_HANDLER_CLEANABLE</a>
and
<a href="/outcontrol/constants.html#" class="link">PHP_OUTPUT_HANDLER_REMOVABLE</a>
flags. Otherwise <span class="function">ob\_get\_clean</span> will not
work.

### Return Values

Returns the contents of the output buffer and end output buffering. If
output buffering isn't active then **`FALSE`** is returned.

### Examples

**Example \#1 A simple <span class="function">ob\_get\_clean</span>
example**

``` php
<?php

ob_start();

echo "Hello World";

$out = ob_get_clean();
$out = strtolower($out);

var_dump($out);
?>
```

The above example will output:


    string(11) "hello world"

### See Also

-   <span class="function">ob\_get\_contents</span>
-   <span class="function">ob\_start</span>

ob\_get\_contents
=================

Return the contents of the output buffer

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">ob\_get\_contents</span> ( <span
class="methodparam">void</span> )

Gets the contents of the output buffer without clearing it.

### Return Values

This will return the contents of the output buffer or **`FALSE`**, if
output buffering isn't active.

### Examples

**Example \#1 A simple <span class="function">ob\_get\_contents</span>
example**

``` php
<?php

ob_start();

echo "Hello ";

$out1 = ob_get_contents();

echo "World";

$out2 = ob_get_contents();

ob_end_clean();

var_dump($out1, $out2);
?>
```

The above example will output:

    string(6) "Hello "
    string(11) "Hello World"

### See Also

-   <span class="function">ob\_start</span>
-   <span class="function">ob\_get\_length</span>

ob\_get\_flush
==============

Flush the output buffer, return it as a string and turn off output
buffering

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">ob\_get\_flush</span> ( <span
class="methodparam">void</span> )

<span class="function">ob\_get\_flush</span> flushes the output buffer,
return it as a string and turns off output buffering.

The output buffer must be started by <span
class="function">ob\_start</span> with
<a href="/outcontrol/constants.html#" class="link">PHP_OUTPUT_HANDLER_FLUSHABLE</a>
flag. Otherwise <span class="function">ob\_get\_flush</span> will not
work.

> **Note**: <span class="simpara"> This function is similar to <span
> class="function">ob\_end\_flush</span>, except that this function also
> returns the buffer as a string. </span>

### Return Values

Returns the output buffer or **`FALSE`** if no buffering is active.

### Examples

**Example \#1 <span class="function">ob\_get\_flush</span> example**

``` php
<?php
//using output_buffering=On
print_r(ob_list_handlers());

//save buffer in a file
$buffer = ob_get_flush();
file_put_contents('buffer.txt', $buffer);

print_r(ob_list_handlers());
?>
```

The above example will output:

    Array
    (
        [0] => default output handler
    )
    Array
    (
    )

### See Also

-   <span class="function">ob\_end\_clean</span>
-   <span class="function">ob\_end\_flush</span>
-   <span class="function">ob\_list\_handlers</span>

ob\_get\_length
===============

Return the length of the output buffer

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">ob\_get\_length</span> ( <span
class="methodparam">void</span> )

This will return the length of the contents in the output buffer, in
bytes.

### Return Values

Returns the length of the output buffer contents, in bytes, or
**`FALSE`** if no buffering is active.

### Examples

**Example \#1 A simple <span class="function">ob\_get\_length</span>
example**

``` php
<?php

ob_start();

echo "Hello ";

$len1 = ob_get_length();

echo "World";

$len2 = ob_get_length();

ob_end_clean();

echo $len1 . ", " . $len2;
?>
```

The above example will output:

    6, 11

### See Also

-   <span class="function">ob\_start</span>
-   <span class="function">ob\_get\_contents</span>

ob\_get\_level
==============

Return the nesting level of the output buffering mechanism

### Description

<span class="type">int</span> <span
class="methodname">ob\_get\_level</span> ( <span
class="methodparam">void</span> )

Returns the nesting level of the output buffering mechanism.

### Return Values

Returns the level of nested output buffering handlers or zero if output
buffering is not active.

### See Also

-   <span class="function">ob\_start</span>
-   <span class="function">ob\_get\_contents</span>

ob\_get\_status
===============

Get status of output buffers

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">ob\_get\_status</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$full_status` <span
class="initializer"> = FALSE</span></span> \] )

<span class="function">ob\_get\_status</span> returns status information
on either the top level output buffer or all active output buffer levels
if `full_status` is set to **`TRUE`**.

### Parameters

`full_status`  
**`TRUE`** to return all active output buffer levels. If **`FALSE`** or
not set, only the top level output buffer is returned.

### Return Values

If called without the `full_status` parameter or with `full_status` =
**`FALSE`** a simple array with the following elements is returned:

``` returnvalues
Array
(
    [level] => 2
    [type] => 0
    [status] => 0
    [name] => URL-Rewriter
    [del] => 1
)
```

| Key    | Value                                                                                                         |
|--------|---------------------------------------------------------------------------------------------------------------|
| level  | Output nesting level                                                                                          |
| type   | *PHP\_OUTPUT\_HANDLER\_INTERNAL (0)* or *PHP\_OUTPUT\_HANDLER\_USER (1)*                                      |
| status | One of *PHP\_OUTPUT\_HANDLER\_START* (0), *PHP\_OUTPUT\_HANDLER\_CONT* (1) or *PHP\_OUTPUT\_HANDLER\_END* (2) |
| name   | Name of active output handler or ' default output handler' if none is set                                     |
| del    | Erase-flag as set by <span class="function">ob\_start</span>                                                  |

If called with `full_status` = **`TRUE`** an array with one element for
each active output buffer level is returned. The output level is used as
key of the top level array and each array element itself is another
array holding status information on one active output level.

    Array
    (
        [0] => Array
            (
                [chunk_size] => 0
                [size] => 40960
                [block_size] => 10240
                [type] => 1
                [status] => 0
                [name] => default output handler
                [del] => 1
            )

        [1] => Array
            (
                [chunk_size] => 0
                [size] => 40960
                [block_size] => 10240
                [type] => 0
                [buffer_size] => 0
                [status] => 0
                [name] => URL-Rewriter
                [del] => 1
            )

    )

The full output contains these additional elements:

| Key         | Value                                                        |
|-------------|--------------------------------------------------------------|
| chunk\_size | Chunk size as set by <span class="function">ob\_start</span> |
| size        | ...                                                          |
| blocksize   | ...                                                          |

### See Also

-   <span class="function">ob\_get\_level</span>
-   <span class="function">ob\_list\_handlers</span>

ob\_gzhandler
=============

ob\_start callback function to gzip output buffer

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">ob\_gzhandler</span> ( <span
class="methodparam"><span class="type">string</span> `$buffer`</span> ,
<span class="methodparam"><span class="type">int</span> `$mode`</span> )

<span class="function">ob\_gzhandler</span> is intended to be used as a
callback function for <span class="function">ob\_start</span> to help
facilitate sending gz-encoded data to web browsers that support
compressed web pages. Before <span class="function">ob\_gzhandler</span>
actually sends compressed data, it determines what type of content
encoding the browser will accept ("gzip", "deflate" or none at all) and
will return its output accordingly. All browsers are supported since
it's up to the browser to send the correct header saying that it accepts
compressed web pages. If a browser doesn't support compressed pages this
function returns **`FALSE`**.

### Parameters

`buffer`  

`mode`  

### Return Values

### Examples

**Example \#1 <span class="function">ob\_gzhandler</span> example**

``` php
<?php

ob_start("ob_gzhandler");

?>
<html>
<body>
<p>This should be a compressed page.</p>
</body>
</html>
```

### Notes

> **Note**:
>
> <span class="function">ob\_gzhandler</span> requires the
> <a href="/ref/zlib.html" class="link">zlib</a> extension.

> **Note**:
>
> You cannot use both <span class="function">ob\_gzhandler</span> and
> <a href="/zlib/setup.html#" class="link">zlib.output_compression</a>.
> Also note that using
> <a href="/zlib/setup.html#" class="link">zlib.output_compression</a>
> is preferred over <span class="function">ob\_gzhandler</span>.

### See Also

-   <span class="function">ob\_start</span>
-   <span class="function">ob\_end\_flush</span>

ob\_implicit\_flush
===================

Turn implicit flush on/off

### Description

<span class="type">void</span> <span
class="methodname">ob\_implicit\_flush</span> (\[ <span
class="methodparam"><span class="type">int</span> `$flag`<span
class="initializer"> = 1</span></span> \] )

<span class="function">ob\_implicit\_flush</span> will turn implicit
flushing on or off. Implicit flushing will result in a flush operation
after every output call, so that explicit calls to <span
class="function">flush</span> will no longer be needed.

### Parameters

`flag`  
*1* to turn implicit flushing on, *0* otherwise.

### Return Values

No value is returned.

### See Also

-   <span class="function">flush</span>
-   <span class="function">ob\_start</span>
-   <span class="function">ob\_end\_flush</span>

ob\_list\_handlers
==================

List all output handlers in use

### Description

<span class="type">array</span> <span
class="methodname">ob\_list\_handlers</span> ( <span
class="methodparam">void</span> )

Lists all output handlers in use.

### Return Values

This will return an array with the output handlers in use (if any). If
<a href="/outcontrol/setup.html#" class="link">output_buffering</a> is
enabled or an anonymous function was used with <span
class="function">ob\_start</span>, <span
class="function">ob\_list\_handlers</span> will return "default output
handler".

### Examples

**Example \#1 <span class="function">ob\_list\_handlers</span> example**

``` php
<?php
//using output_buffering=On
print_r(ob_list_handlers());
ob_end_flush();

ob_start("ob_gzhandler");
print_r(ob_list_handlers());
ob_end_flush();

// anonymous functions
ob_start(function($string) { return $string; });
print_r(ob_list_handlers());
ob_end_flush();
?>
```

The above example will output:

    Array
    (
        [0] => default output handler
    )

    Array
    (
        [0] => ob_gzhandler
    )

    Array
    (
        [0] => Closure::__invoke
    )

### See Also

-   <span class="function">ob\_end\_clean</span>
-   <span class="function">ob\_end\_flush</span>
-   <span class="function">ob\_get\_flush</span>
-   <span class="function">ob\_start</span>

ob\_start
=========

Turn on output buffering

### Description

<span class="type">bool</span> <span class="methodname">ob\_start</span>
(\[ <span class="methodparam"><span class="type">callable</span>
`$output_callback`<span class="initializer"> = **`NULL`**</span></span>
\[, <span class="methodparam"><span class="type">int</span>
`$chunk_size`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = **`PHP_OUTPUT_HANDLER_STDFLAGS`**</span></span>
\]\]\] )

This function will turn output buffering on. While output buffering is
active no output is sent from the script (other than headers), instead
the output is stored in an internal buffer.

The contents of this internal buffer may be copied into a string
variable using <span class="function">ob\_get\_contents</span>. To
output what is stored in the internal buffer, use <span
class="function">ob\_end\_flush</span>. Alternatively, <span
class="function">ob\_end\_clean</span> will silently discard the buffer
contents.

**Warning**

Some web servers (e.g. Apache) change the working directory of a script
when calling the callback function. You can change it back by e.g.
*chdir(dirname($\_SERVER\['SCRIPT\_FILENAME'\]))* in the callback
function.

Output buffers are stackable, that is, you may call <span
class="function">ob\_start</span> while another <span
class="function">ob\_start</span> is active. Just make sure that you
call <span class="function">ob\_end\_flush</span> the appropriate number
of times. If multiple output callback functions are active, output is
being filtered sequentially through each of them in nesting order.

### Parameters

`output_callback`  
An optional `output_callback` function may be specified. This function
takes a string as a parameter and should return a string. The function
will be called when the output buffer is flushed (sent) or cleaned (with
<span class="function">ob\_flush</span>, <span
class="function">ob\_clean</span> or similar function) or when the
output buffer is flushed to the browser at the end of the request. When
`output_callback` is called, it will receive the contents of the output
buffer as its parameter and is expected to return a new output buffer as
a result, which will be sent to the browser. If the `output_callback` is
not a callable function, this function will return **`FALSE`**. This is
the callback signature:

<span class="type">string</span> <span class="methodname"><span
class="replaceable">handler</span></span> ( <span
class="methodparam"><span class="type">string</span> `$buffer`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$phase`</span> \] )

`buffer`  
<span class="simpara"> Contents of the output buffer. </span>

`phase`  
<span class="simpara"> Bitmask of
<a href="/outcontrol/constants.html" class="link"><strong><code>PHP_OUTPUT_HANDLER_*</code></strong> constants</a>.
</span>

If `output_callback` returns **`FALSE`** original input is sent to the
browser.

The `output_callback` parameter may be bypassed by passing a **`NULL`**
value.

<span class="function">ob\_end\_clean</span>, <span
class="function">ob\_end\_flush</span>, <span
class="function">ob\_clean</span>, <span
class="function">ob\_flush</span> and <span
class="function">ob\_start</span> may not be called from a callback
function. If you call them from callback function, the behavior is
undefined. If you would like to delete the contents of a buffer, return
"" (a null string) from callback function. You can't even call functions
using the output buffering functions like *print\_r($expression, true)*
or *highlight\_file($filename, true)* from a callback function.

> **Note**:
>
> <span class="function">ob\_gzhandler</span> function exists to
> facilitate sending gz-encoded data to web browsers that support
> compressed web pages. <span class="function">ob\_gzhandler</span>
> determines what type of content encoding the browser will accept and
> will return its output accordingly.

`chunk_size`  
If the optional parameter `chunk_size` is passed, the buffer will be
flushed after any output call which causes the buffer's length to equal
or exceed `chunk_size`. The default value *0* means that the output
function will only be called when the output buffer is closed.

Prior to PHP 5.4.0, the value *1* was a special case value that set the
chunk size to 4096 bytes.

`flags`  
The `flags` parameter is a bitmask that controls the operations that can
be performed on the output buffer. The default is to allow output
buffers to be cleaned, flushed and removed, which can be set explicitly
via **`PHP_OUTPUT_HANDLER_CLEANABLE`** \|
**`PHP_OUTPUT_HANDLER_FLUSHABLE`** \|
**`PHP_OUTPUT_HANDLER_REMOVABLE`**, or **`PHP_OUTPUT_HANDLER_STDFLAGS`**
as shorthand.

Each flag controls access to a set of functions, as described below:

| Constant                           | Functions                                                                                                                                     |
|------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| **`PHP_OUTPUT_HANDLER_CLEANABLE`** | <span class="function">ob\_clean</span>, <span class="function">ob\_end\_clean</span>, and <span class="function">ob\_get\_clean</span>.      |
| **`PHP_OUTPUT_HANDLER_FLUSHABLE`** | <span class="function">ob\_end\_flush</span>, <span class="function">ob\_flush</span>, and <span class="function">ob\_get\_flush</span>.      |
| **`PHP_OUTPUT_HANDLER_REMOVABLE`** | <span class="function">ob\_end\_clean</span>, <span class="function">ob\_end\_flush</span>, and <span class="function">ob\_get\_flush</span>. |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 User defined callback function example**

``` php
<?php

function callback($buffer)
{
  // replace all the apples with oranges
  return (str_replace("apples", "oranges", $buffer));
}

ob_start("callback");

?>
<html>
<body>
<p>It's like comparing apples to oranges.</p>
</body>
</html>
<?php

ob_end_flush();

?>
```

The above example will output:

    <html>
    <body>
    <p>It's like comparing oranges to oranges.</p>
    </body>
    </html>

**Example \#2 Creating an uneraseable output buffer in a way compatible
with both PHP 5.3 and 5.4**

``` php
<?php

if (version_compare(PHP_VERSION, '5.4.0', '>=')) {
  ob_start(null, 0, PHP_OUTPUT_HANDLER_STDFLAGS ^
    PHP_OUTPUT_HANDLER_REMOVABLE);
} else {
  ob_start(null, 0, false);
}

?>
```

### See Also

-   <span class="function">ob\_get\_contents</span>
-   <span class="function">ob\_end\_clean</span>
-   <span class="function">ob\_end\_flush</span>
-   <span class="function">ob\_implicit\_flush</span>
-   <span class="function">ob\_gzhandler</span>
-   <span class="function">ob\_iconv\_handler</span>
-   <span class="function">mb\_output\_handler</span>
-   <span class="function">ob\_tidyhandler</span>

output\_add\_rewrite\_var
=========================

Add URL rewriter values

### Description

<span class="type">bool</span> <span
class="methodname">output\_add\_rewrite\_var</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

This function adds another name/value pair to the URL rewrite mechanism.
The name and value will be added to URLs (as GET parameter) and forms
(as hidden input fields) the same way as the session ID when transparent
URL rewriting is enabled with
<a href="/session/setup.html#" class="link">session.use_trans_sid</a>.

This function's behaviour is controlled by the
<a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a> and
<a href="/outcontrol/setup.html#" class="link">url_rewriter.hosts</a>
`php.ini` parameters.

Note that this function can be successfully called at most once per
request.

> **Note**: <span class="simpara"> Calling this function will implicitly
> start output buffering if it is not active already. </span>

### Parameters

`name`  
The variable name.

`value`  
The variable value.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                                                                    |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | Before PHP 7.1.0, rewrite vars set by <span class="function">output\_add\_rewrite\_var</span> use the same Session module trans sid output buffer. Since PHP 7.1.0, dedicated output buffer is used, <a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a> is used solely for output functions, <a href="/outcontrol/setup.html#" class="link">url_rewriter.hosts</a> is added. |

### Examples

**Example \#1 <span class="function">output\_add\_rewrite\_var</span>
example**

``` php
<?php
output_add_rewrite_var('var', 'value');

// some links
echo '<a href="file.php">link</a>
<a href="http://example.com">link2</a>';

// a form
echo '<form action="script.php" method="post">
<input type="text" name="var2" />
</form>';

print_r(ob_list_handlers());
?>
```

The above example will output:

    <a href="file.php?var=value">link</a>
    <a href="http://example.com">link2</a>

    <form action="script.php" method="post">
    <input type="hidden" name="var" value="value" />
    <input type="text" name="var2" />
    </form>

    Array
    (
        [0] => URL-Rewriter
    )

### See Also

-   <span class="function">output\_reset\_rewrite\_vars</span>
-   <span class="function">ob\_flush</span>
-   <span class="function">ob\_list\_handlers</span>
-   <a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a>
-   <a href="/outcontrol/setup.html#" class="link">url_rewriter.hosts</a>
-   <a href="/session/setup.html#" class="link">session.trans_sid_tags</a>
-   <a href="/session/setup.html#" class="link">session.trans_sid_hosts</a>

output\_reset\_rewrite\_vars
============================

Reset URL rewriter values

### Description

<span class="type">bool</span> <span
class="methodname">output\_reset\_rewrite\_vars</span> ( <span
class="methodparam">void</span> )

This function resets the URL rewriter and removes all rewrite variables
previously set by the <span
class="function">output\_add\_rewrite\_var</span> function.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                                      |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | Before PHP 7.1.0, rewrite vars set by <span class="function">output\_add\_rewrite\_var</span> use the same Session module trans sid output buffer. Since PHP 7.1.0, dedicated output buffer is used and <span class="function">output\_reset\_rewrite\_vars</span> only removes rewrite vars defined by <span class="function">output\_add\_rewrite\_var</span>. |

### Examples

**Example \#1 <span class="function">output\_reset\_rewrite\_vars</span>
example**

``` php
<?php
session_start();
output_add_rewrite_var('var', 'value');

echo '<a href="file.php">link</a>';
ob_flush();

output_reset_rewrite_vars();
echo '<a href="file.php">link</a>';
?>
```

The above example will output:

    <a href="file.php?PHPSESSID=xxx&var=value">link</a>
    <a href="file.php">link</a>

### See Also

-   <span class="function">output\_add\_rewrite\_var</span>
-   <span class="function">ob\_flush</span>
-   <span class="function">ob\_list\_handlers</span>
-   <a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a>
-   <a href="/outcontrol/setup.html#" class="link">url_rewriter.hosts</a>
-   <a href="/session/setup.html#" class="link">session.trans_sid_tags</a>
-   <a href="/session/setup.html#" class="link">session.trans_sid_hosts</a>

**Table of Contents**

-   [flush](/ref/outcontrol.html#flush) — Flush system output buffer
-   [ob\_clean](/ref/outcontrol.html#ob_clean) — Clean (erase) the
    output buffer
-   [ob\_end\_clean](/ref/outcontrol.html#ob_end_clean) — Clean (erase)
    the output buffer and turn off output buffering
-   [ob\_end\_flush](/ref/outcontrol.html#ob_end_flush) — Flush (send)
    the output buffer and turn off output buffering
-   [ob\_flush](/ref/outcontrol.html#ob_flush) — Flush (send) the output
    buffer
-   [ob\_get\_clean](/ref/outcontrol.html#ob_get_clean) — Get current
    buffer contents and delete current output buffer
-   [ob\_get\_contents](/ref/outcontrol.html#ob_get_contents) — Return
    the contents of the output buffer
-   [ob\_get\_flush](/ref/outcontrol.html#ob_get_flush) — Flush the
    output buffer, return it as a string and turn off output buffering
-   [ob\_get\_length](/ref/outcontrol.html#ob_get_length) — Return the
    length of the output buffer
-   [ob\_get\_level](/ref/outcontrol.html#ob_get_level) — Return the
    nesting level of the output buffering mechanism
-   [ob\_get\_status](/ref/outcontrol.html#ob_get_status) — Get status
    of output buffers
-   [ob\_gzhandler](/ref/outcontrol.html#ob_gzhandler) — ob\_start
    callback function to gzip output buffer
-   [ob\_implicit\_flush](/ref/outcontrol.html#ob_implicit_flush) — Turn
    implicit flush on/off
-   [ob\_list\_handlers](/ref/outcontrol.html#ob_list_handlers) — List
    all output handlers in use
-   [ob\_start](/ref/outcontrol.html#ob_start) — Turn on output
    buffering
-   [output\_add\_rewrite\_var](/ref/outcontrol.html#output_add_rewrite_var)
    — Add URL rewriter values
-   [output\_reset\_rewrite\_vars](/ref/outcontrol.html#output_reset_rewrite_vars)
    — Reset URL rewriter values

Contact Information
-------------------

If you have comments, bugfixes, enhancements or want to help developing
this beast, you can drop me a mail at
<a href="mailto:alan_k@php.net" class="link external">» alan_k@php.net</a>.
Any help is very welcome.

bcompiler\_load\_exe
====================

Reads and creates classes from a bcompiler exe file

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_load\_exe</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Reads data from a bcompiler exe file and creates classes from the
bytecodes.

### Parameters

`filename`  
The exe file path, as a string.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_load\_exe</span>
example**

``` php
<?php

bcompiler_load_exe("/tmp/example.exe");
print_r(get_defined_classes());

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">bcompiler\_load</span>

bcompiler\_load
===============

Reads and creates classes from a bz compressed file

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_load</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Reads data from a bzcompressed file and creates classes from the
bytecodes.

### Parameters

`filename`  
The bzcompressed file path, as a string.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_load</span> example**

``` php
<?php

bcompiler_load("/tmp/example");

print_r(get_defined_classes());

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

> **Note**:
>
> Please use include or require statements to parse bytecodes, it's more
> portable and convenient way than using this function.
>
> Please note that this function won't execute script body code
> contained in the bytecode file.

### See Also

-   <span class="function">bcompiler\_load\_exe</span>

bcompiler\_parse\_class
=======================

Reads the bytecodes of a class and calls back to a user function

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_parse\_class</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$callback`</span> )

Reads the bytecodes of a class and calls back to a user function.

### Parameters

`class`  
The class name, as a string.

`callback`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_parse\_class</span>
example**

``` php
<?php

function readByteCodes($data) {
    print_r($data);
}

bcompiler_parse_class("DB","readByteCodes");

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

> **Note**:
>
> This function has been removed from bcompiler and is no longer
> available as of bcompiler 0.5.

bcompiler\_read
===============

Reads and creates classes from a filehandle

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_read</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> )

Reads data from a open file handle and creates classes from the
bytecodes.

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_read</span> example**

``` php
<?php
$fh = fopen("/tmp/example","r");
bcompiler_read($fh);
fclose($fh);
print_r(get_defined_classes());

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

> **Note**:
>
> Please use include or require statements to parse bytecodes, it's more
> portable and convenient way than using this function.
>
> Please note that this function won't execute script body code
> contained in the bytecode file.

bcompiler\_write\_class
=======================

Writes a defined class as bytecodes

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_class</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> , <span class="methodparam"><span
class="type">string</span> `$className`</span> \[, <span
class="methodparam"><span class="type">string</span> `$extends`</span>
\] )

Reads the bytecodes from PHP for an existing class, and writes them to
the open file handle.

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

`className`  
The class name, as a string.

`extends`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_write\_class</span>
example**

``` php
<?php
$fh = fopen("/tmp/example","w");
bcompiler_write_header($fh);
bcompiler_write_class($fh,"DB");
// you must write DB_common before DB_mysql, as DB_mysql extends DB_common.
bcompiler_write_class($fh,"DB_common");
bcompiler_write_class($fh,"DB_mysql");
bcompiler_write_footer($fh);
fclose($fh);

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

> **Note**:
>
> This function does not perform dependency checking, so make sure you
> write the classes in an order that will not result in an *undefined
> class* error occurring when you load it.

### See Also

-   <span class="function">bcompiler\_write\_header</span>
-   <span class="function">bcompiler\_write\_footer</span>

bcompiler\_write\_constant
==========================

Writes a defined constant as bytecodes

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_constant</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> , <span class="methodparam"><span
class="type">string</span> `$constantName`</span> )

Reads the bytecodes from PHP for an existing constant, and writes them
to the open file handle.

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

`constantName`  
The name of the defined constant, as a string.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_write\_constant</span>
example**

``` php
<?php
define("MODULE_MAX", 30);

$fh = fopen("/tmp/example","w");
bcompiler_write_header($fh);
bcompiler_write_constant($fh,"MODULE_MAX");
bcompiler_write_footer($fh);
fclose($fh);

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">bcompiler\_write\_header</span>
-   <span class="function">bcompiler\_write\_footer</span>

bcompiler\_write\_exe\_footer
=============================

Writes the start pos, and sig to the end of a exe type file

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_exe\_footer</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> , <span class="methodparam"><span
class="type">int</span> `$startpos`</span> )

An EXE (or self executable) file consists of 3 parts:

-   The *stub* (executable code, e.g. a compiled C program) that loads
    PHP interpreter, bcompiler extension, stored Bytecodes and initiates
    a call for the specified function (e.g. main) or class method (e.g.
    *main::main*)
-   The Bytecodes (uncompressed only for the moment)
-   The bcompiler EXE footer

To obtain a suitable stub you can compile php\_embed-based stub `phpe.c`
located in the `examples/embed` directory on bcompiler's CVS.

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

`startpos`  
The file position at which the Bytecodes start, and can be obtained
using <span class="function">ftell</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="function">bcompiler\_write\_exe\_footer</span> example**

``` php
<?php

/* creating the output file (example.exe) */
$fh = fopen("example.exe", "w");

/* 1) writing a stub (phpe.exe) */
$size = filesize("phpe.exe");
$fr = fopen("phpe.exe", "r");
fwrite($fh, fread($fr, $size), $size);
$startpos = ftell($fh);

/* 2) writing bytecodes */
bcompiler_write_header($fh);
bcompiler_write_class($fh, "myclass");
bcompiler_write_function($fh, "main");
bcompiler_write_footer($fh);

/* 3) writing EXE footer */
bcompiler_write_exe_footer($fh, $startpos);

/* closing the output file */
fclose($fh);
?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">bcompiler\_write\_header</span>
-   <span class="function">bcompiler\_write\_class</span>
-   <span class="function">bcompiler\_write\_footer</span>

bcompiler\_write\_file
======================

Writes a php source file as bytecodes

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_file</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> , <span class="methodparam"><span
class="type">string</span> `$filename`</span> )

This function compiles specified source file into bytecodes, and writes
them to the open file handle.

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

`filename`  
The source file path, as a string.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_write\_file</span>
example**

``` php
<?php
$fh = fopen("example.phb", "w");
bcompiler_write_header($fh);
bcompiler_write_file($fh, "example.php");
bcompiler_write_footer($fh);
fclose($fh);
/* the following should be equivalent:
include "example.php";
   and
include "example.phb";
*/
?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">bcompiler\_write\_header</span>
-   <span class="function">bcompiler\_write\_footer</span>

bcompiler\_write\_footer
========================

Writes the single character \\x00 to indicate End of compiled data

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_footer</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> )

Writes the single character *\\x00* to indicate End of compiled data.

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_write\_footer</span>
example**

``` php
<?php
$fh = fopen("/tmp/example","w");
bcompiler_write_header($fh);
bcompiler_write_class($fh,"DB");
bcompiler_write_class($fh,"DB_common");
bcompiler_write_footer($fh);
fclose($fh);

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">bcompiler\_write\_header</span>

bcompiler\_write\_function
==========================

Writes a defined function as bytecodes

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_function</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> , <span class="methodparam"><span
class="type">string</span> `$functionName`</span> )

Reads the bytecodes from PHP for an existing function, and writes them
to the open file handle. Order is not important, (eg. if function b uses
function a, and you compile it like the example below, it will work
perfectly OK).

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

`functionName`  
The function name, as a string.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_write\_function</span>
example**

``` php
<?php
$fh = fopen("/tmp/example","w");
bcompiler_write_header($fh);
bcompiler_write_function($fh,"my_function_a");
bcompiler_write_function($fh,"my_function_b");
bcompiler_write_footer($fh);
fclose($fh);

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">bcompiler\_write\_header</span>
-   <span class="function">bcompiler\_write\_footer</span>

bcompiler\_write\_functions\_from\_file
=======================================

Writes all functions defined in a file as bytecodes

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_functions\_from\_file</span> (
<span class="methodparam"><span class="type">resource</span>
`$filehandle`</span> , <span class="methodparam"><span
class="type">string</span> `$fileName`</span> )

Searches for all functions declared in the given file, and writes their
correspondent bytecodes to the open file handle.

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

`fileName`  
The file to be compiled. You must always include or require the file you
intend to compile.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="function">bcompiler\_write\_functions\_from\_file</span>
example**

``` php
<?php
require('module.php');

$fh = fopen("/tmp/example","w");
bcompiler_write_header($fh);
bcompiler_write_functions_from_file($fh,'module.php');
bcompiler_write_footer($fh);
fclose($fh);

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">bcompiler\_write\_header</span>
-   <span class="function">bcompiler\_write\_footer</span>

bcompiler\_write\_header
========================

Writes the bcompiler header

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_header</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$write_ver`</span> \] )

Writes the header part of a bcompiler file.

### Parameters

`filehandle`  
A file handle as returned by <span class="function">fopen</span>.

`write_ver`  
Can be used to write bytecode in a previously used format, so that you
can use it with older versions of bcompiler.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">bcompiler\_write\_header</span>
example**

``` php
<?php
$fh = fopen("/tmp/example","w");
bcompiler_write_header($fh);
bcompiler_write_class($fh,"DB");
bcompiler_write_footer($fh);
fclose($fh);

?>
```

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">bcompiler\_write\_footer</span>

bcompiler\_write\_included\_filename
====================================

Writes an included file as bytecodes

### Description

<span class="type">bool</span> <span
class="methodname">bcompiler\_write\_included\_filename</span> ( <span
class="methodparam"><span class="type">resource</span>
`$filehandle`</span> , <span class="methodparam"><span
class="type">string</span> `$filename`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Table of Contents**

-   [bcompiler\_load\_exe](/ref/bcompiler.html#bcompiler_load_exe) —
    Reads and creates classes from a bcompiler exe file
-   [bcompiler\_load](/ref/bcompiler.html#bcompiler_load) — Reads and
    creates classes from a bz compressed file
-   [bcompiler\_parse\_class](/ref/bcompiler.html#bcompiler_parse_class)
    — Reads the bytecodes of a class and calls back to a user function
-   [bcompiler\_read](/ref/bcompiler.html#bcompiler_read) — Reads and
    creates classes from a filehandle
-   [bcompiler\_write\_class](/ref/bcompiler.html#bcompiler_write_class)
    — Writes a defined class as bytecodes
-   [bcompiler\_write\_constant](/ref/bcompiler.html#bcompiler_write_constant)
    — Writes a defined constant as bytecodes
-   [bcompiler\_write\_exe\_footer](/ref/bcompiler.html#bcompiler_write_exe_footer)
    — Writes the start pos, and sig to the end of a exe type file
-   [bcompiler\_write\_file](/ref/bcompiler.html#bcompiler_write_file) —
    Writes a php source file as bytecodes
-   [bcompiler\_write\_footer](/ref/bcompiler.html#bcompiler_write_footer)
    — Writes the single character \\x00 to indicate End of compiled data
-   [bcompiler\_write\_function](/ref/bcompiler.html#bcompiler_write_function)
    — Writes a defined function as bytecodes
-   [bcompiler\_write\_functions\_from\_file](/ref/bcompiler.html#bcompiler_write_functions_from_file)
    — Writes all functions defined in a file as bytecodes
-   [bcompiler\_write\_header](/ref/bcompiler.html#bcompiler_write_header)
    — Writes the bcompiler header
-   [bcompiler\_write\_included\_filename](/ref/bcompiler.html#bcompiler_write_included_filename)
    — Writes an included file as bytecodes

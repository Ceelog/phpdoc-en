bzclose
=======

Close a bzip2 file

### Description

<span class="type">bool</span> <span class="methodname">bzclose</span> (
<span class="methodparam"><span class="type">resource</span>
`$bz`</span> )

Closes the given bzip2 file pointer.

### Parameters

`bz`  
The file pointer. It must be valid and must point to a file successfully
opened by <span class="function">bzopen</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">bzopen</span>

bzcompress
==========

Compress a string into bzip2 encoded data

### Description

<span class="type"><span class="type">string</span><span
class="type">int</span></span> <span
class="methodname">bzcompress</span> ( <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type">int</span> `$block_size`<span
class="initializer"> = 4</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$work_factor`<span
class="initializer"> = 0</span></span> \]\] )

<span class="function">bzcompress</span> compresses the given string and
returns it as bzip2 encoded data.

### Parameters

`data`  
The string to compress.

`block_size`  
Specifies the blocksize used during compression and should be a number
from 1 to 9 with 9 giving the best compression, but using more resources
to do so.

`work_factor`  
Controls how the compression phase behaves when presented with worst
case, highly repetitive, input data. The value can be between 0 and 250
with 0 being a special case.

Regardless of the `work_factor`, the generated output is the same.

### Return Values

The compressed string, or an error number if an error occurred.

### Examples

**Example \#1 Compressing data**

``` php
<?php
$str = "sample data";
$bzstr = bzcompress($str, 9);
echo $bzstr;
?>
```

### See Also

-   <span class="function">bzdecompress</span>

bzdecompress
============

Decompresses bzip2 encoded data

### Description

<span class="type"><span class="type">string</span><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">bzdecompress</span> ( <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type">bool</span>
`$use_less_memory`<span class="initializer"> = **`false`**</span></span>
\] )

<span class="function">bzdecompress</span> decompresses the given string
containing bzip2 encoded data.

### Parameters

`data`  
The string to decompress.

`use_less_memory`  
If **`true`**, an alternative decompression algorithm will be used which
uses less memory (the maximum memory requirement drops to around 2300K)
but works at roughly half the speed.

See the
<a href="https://www.sourceware.org/bzip2/" class="link external">» bzip2 documentation</a>
for more information about this feature.

### Return Values

The decompressed string, or **`false`** or an error number if an error
occurred.

### Changelog

| Version | Description                                                                                                                                                 |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | The type of `use_less_memory` has been changed from <span class="type">int</span> to <span class="type">bool</span>. Previously, the default value was *0*. |

### Examples

**Example \#1 Decompressing a String**

``` php
<?php
$start_str = "This is not an honest face?";
$bzstr = bzcompress($start_str);

echo "Compressed String: ";
echo $bzstr;
echo "\n<br />\n";

$str = bzdecompress($bzstr);
echo "Decompressed String: ";
echo $str;
echo "\n<br />\n";
?>
```

### See Also

-   <span class="function">bzcompress</span>

bzerrno
=======

Returns a bzip2 error number

### Description

<span class="type">int</span> <span class="methodname">bzerrno</span> (
<span class="methodparam"><span class="type">resource</span>
`$bz`</span> )

Returns the error number of any bzip2 error returned by the given file
pointer.

### Parameters

`bz`  
The file pointer. It must be valid and must point to a file successfully
opened by <span class="function">bzopen</span>.

### Return Values

Returns the error number as an integer.

### See Also

-   <span class="function">bzerror</span>
-   <span class="function">bzerrstr</span>

bzerror
=======

Returns the bzip2 error number and error string in an array

### Description

<span class="type">array</span> <span class="methodname">bzerror</span>
( <span class="methodparam"><span class="type">resource</span>
`$bz`</span> )

Returns the error number and error string of any bzip2 error returned by
the given file pointer.

### Parameters

`bz`  
The file pointer. It must be valid and must point to a file successfully
opened by <span class="function">bzopen</span>.

### Return Values

Returns an associative array, with the error code in the *errno* entry,
and the error message in the *errstr* entry.

### Examples

**Example \#1 <span class="function">bzerror</span> example**

``` php
<?php
$error = bzerror($bz);

echo $error["errno"];
echo $error["errstr"];
?>
```

### See Also

-   <span class="function">bzerrno</span>
-   <span class="function">bzerrstr</span>

bzerrstr
========

Returns a bzip2 error string

### Description

<span class="type">string</span> <span
class="methodname">bzerrstr</span> ( <span class="methodparam"><span
class="type">resource</span> `$bz`</span> )

Gets the error string of any bzip2 error returned by the given file
pointer.

### Parameters

`bz`  
The file pointer. It must be valid and must point to a file successfully
opened by <span class="function">bzopen</span>.

### Return Values

Returns a string containing the error message.

### See Also

-   <span class="function">bzerrno</span>
-   <span class="function">bzerror</span>

bzflush
=======

Force a write of all buffered data

### Description

<span class="type">bool</span> <span class="methodname">bzflush</span> (
<span class="methodparam"><span class="type">resource</span>
`$bz`</span> )

Forces a write of all buffered bzip2 data for the file pointer `bz`.

### Parameters

`bz`  
The file pointer. It must be valid and must point to a file successfully
opened by <span class="function">bzopen</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">bzread</span>
-   <span class="function">bzwrite</span>

bzopen
======

Opens a bzip2 compressed file

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span class="methodname">bzopen</span>
( <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">resource</span></span>
`$file`</span> , <span class="methodparam"><span
class="type">string</span> `$mode`</span> )

<span class="function">bzopen</span> opens a bzip2 (`.bz2`) file for
reading or writing.

### Parameters

`file`  
The name of the file to open, or an existing stream resource.

`mode`  
The modes *'r'* (read), and *'w'* (write) are supported. Everything else
will cause <span class="function">bzopen</span> to return **`false`**.

### Return Values

If the open fails, <span class="function">bzopen</span> returns
**`false`**, otherwise it returns a pointer to the newly opened file.

### Examples

**Example \#1 <span class="function">bzopen</span> example**

``` php
<?php

$file = "/tmp/foo.bz2";
$bz = bzopen($file, "r") or die("Couldn't open $file for reading");

bzclose($bz);

?>
```

### See Also

-   <span class="function">bzclose</span>

bzread
======

Binary safe bzip2 file read

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span class="methodname">bzread</span>
( <span class="methodparam"><span class="type">resource</span>
`$bz`</span> \[, <span class="methodparam"><span class="type">int</span>
`$length`<span class="initializer"> = 1024</span></span> \] )

<span class="function">bzread</span> reads from the given bzip2 file
pointer.

Reading stops when `length` (uncompressed) bytes have been read or EOF
is reached, whichever comes first.

### Parameters

`bz`  
The file pointer. It must be valid and must point to a file successfully
opened by <span class="function">bzopen</span>.

`length`  
If not specified, <span class="function">bzread</span> will read 1024
(uncompressed) bytes at a time. A maximum of 8192 uncompressed bytes
will be read at a time.

### Return Values

Returns the uncompressed data, or **`false`** on error.

### Examples

**Example \#1 <span class="function">bzread</span> example**

``` php
<?php

$file = "/tmp/foo.bz2";
$bz = bzopen($file, "r") or die("Couldn't open $file");

$decompressed_file = '';
while (!feof($bz)) {
  $decompressed_file .= bzread($bz, 4096);
}
bzclose($bz);

echo "The contents of $file are: <br />\n";
echo $decompressed_file;

?>
```

### See Also

-   <span class="function">bzwrite</span>
-   <span class="function">feof</span>
-   <span class="function">bzopen</span>

bzwrite
=======

Binary safe bzip2 file write

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span class="methodname">bzwrite</span>
( <span class="methodparam"><span class="type">resource</span>
`$bz`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">int</span><span class="type">null</span></span>
`$length`<span class="initializer"> = **`null`**</span></span> \] )

<span class="function">bzwrite</span> writes a string into the given
bzip2 file stream.

### Parameters

`bz`  
The file pointer. It must be valid and must point to a file successfully
opened by <span class="function">bzopen</span>.

`data`  
The written data.

`length`  
If supplied, writing will stop after `length` (uncompressed) bytes have
been written or the end of `data` is reached, whichever comes first.

### Return Values

Returns the number of bytes written, or **`false`** on error.

### Changelog

| Version | Description               |
|---------|---------------------------|
| 8.0.0   | `length` is nullable now. |

### Examples

**Example \#1 <span class="function">bzwrite</span> example**

``` php
<?php
$str = "uncompressed data";
$bz = bzopen("/tmp/foo.bz2", "w");
bzwrite($bz, $str, strlen($str));
bzclose($bz);
?>
```

### See Also

-   <span class="function">bzread</span>
-   <span class="function">bzopen</span>

**Table of Contents**

-   [bzclose](/ref/bzip2.html#bzclose) — Close a bzip2 file
-   [bzcompress](/ref/bzip2.html#bzcompress) — Compress a string into
    bzip2 encoded data
-   [bzdecompress](/ref/bzip2.html#bzdecompress) — Decompresses bzip2
    encoded data
-   [bzerrno](/ref/bzip2.html#bzerrno) — Returns a bzip2 error number
-   [bzerror](/ref/bzip2.html#bzerror) — Returns the bzip2 error number
    and error string in an array
-   [bzerrstr](/ref/bzip2.html#bzerrstr) — Returns a bzip2 error string
-   [bzflush](/ref/bzip2.html#bzflush) — Force a write of all buffered
    data
-   [bzopen](/ref/bzip2.html#bzopen) — Opens a bzip2 compressed file
-   [bzread](/ref/bzip2.html#bzread) — Binary safe bzip2 file read
-   [bzwrite](/ref/bzip2.html#bzwrite) — Binary safe bzip2 file write

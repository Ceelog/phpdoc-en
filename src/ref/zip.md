zip\_close
==========

Close a ZIP file archive

### Description

<span class="type">void</span> <span
class="methodname">zip\_close</span> ( <span class="methodparam"><span
class="type">resource</span> `$zip`</span> )

Closes the given ZIP file archive.

### Parameters

`zip`  
A ZIP file previously opened with <span
class="function">zip\_open</span>.

### Return Values

No value is returned.

### See Also

-   <span class="function">zip\_open</span>
-   <span class="function">zip\_read</span>

### Changelog

| Version | Description                                                                                                    |
|---------|----------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API, see <span class="methodname">ZipArchive::close</span>. |

zip\_entry\_close
=================

Close a directory entry

### Description

<span class="type">bool</span> <span
class="methodname">zip\_entry\_close</span> ( <span
class="methodparam"><span class="type">resource</span>
`$zip_entry`</span> )

Closes the specified directory entry.

### Parameters

`zip_entry`  
A directory entry previously opened <span
class="function">zip\_entry\_open</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">zip\_entry\_open</span>
-   <span class="function">zip\_entry\_read</span>

### Changelog

| Version | Description                                             |
|---------|---------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API. |

zip\_entry\_compressedsize
==========================

Retrieve the compressed size of a directory entry

### Description

<span class="type">int</span> <span
class="methodname">zip\_entry\_compressedsize</span> ( <span
class="methodparam"><span class="type">resource</span>
`$zip_entry`</span> )

Returns the compressed size of the specified directory entry.

### Parameters

`zip_entry`  
A directory entry returned by <span class="function">zip\_read</span>.

### Return Values

The compressed size.

### See Also

-   <span class="function">zip\_open</span>
-   <span class="function">zip\_read</span>

### Changelog

| Version | Description                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API, see <span class="methodname">ZipArchive::statIndex</span>. |

zip\_entry\_compressionmethod
=============================

Retrieve the compression method of a directory entry

### Description

<span class="type">string</span> <span
class="methodname">zip\_entry\_compressionmethod</span> ( <span
class="methodparam"><span class="type">resource</span>
`$zip_entry`</span> )

Returns the compression method of the directory entry specified by
`zip_entry`.

### Parameters

`zip_entry`  
A directory entry returned by <span class="function">zip\_read</span>.

### Return Values

The compression method.

### See Also

-   <span class="function">zip\_open</span>
-   <span class="function">zip\_read</span>

### Changelog

| Version | Description                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API, see <span class="methodname">ZipArchive::statIndex</span>. |

zip\_entry\_filesize
====================

Retrieve the actual file size of a directory entry

### Description

<span class="type">int</span> <span
class="methodname">zip\_entry\_filesize</span> ( <span
class="methodparam"><span class="type">resource</span>
`$zip_entry`</span> )

Returns the actual size of the specified directory entry.

### Parameters

`zip_entry`  
A directory entry returned by <span class="function">zip\_read</span>.

### Return Values

The size of the directory entry.

### See Also

-   <span class="function">zip\_open</span>
-   <span class="function">zip\_read</span>

### Changelog

| Version | Description                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API, see <span class="methodname">ZipArchive::statIndex</span>. |

zip\_entry\_name
================

Retrieve the name of a directory entry

### Description

<span class="type">string</span> <span
class="methodname">zip\_entry\_name</span> ( <span
class="methodparam"><span class="type">resource</span>
`$zip_entry`</span> )

Returns the name of the specified directory entry.

### Parameters

`zip_entry`  
A directory entry returned by <span class="function">zip\_read</span>.

### Return Values

The name of the directory entry.

### See Also

-   <span class="function">zip\_open</span>
-   <span class="function">zip\_read</span>

### Changelog

| Version | Description                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API, see <span class="methodname">ZipArchive::statIndex</span>. |

zip\_entry\_open
================

Open a directory entry for reading

### Description

<span class="type">bool</span> <span
class="methodname">zip\_entry\_open</span> ( <span
class="methodparam"><span class="type">resource</span> `$zip`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$zip_entry`</span> \[, <span class="methodparam"><span
class="type">string</span> `$mode`</span> \] )

Opens a directory entry in a zip file for reading.

### Parameters

`zip`  
A valid resource handle returned by <span
class="function">zip\_open</span>.

`zip_entry`  
A directory entry returned by <span class="function">zip\_read</span>.

`mode`  
Any of the modes specified in the documentation of <span
class="function">fopen</span>.

> **Note**:
>
> Currently, `mode` is ignored and is always *"rb"*. This is due to the
> fact that zip support in PHP is read only access.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

> **Note**:
>
> Unlike <span class="function">fopen</span> and other similar
> functions, the return value of <span
> class="function">zip\_entry\_open</span> only indicates the result of
> the operation and is not needed for reading or closing the directory
> entry.

### See Also

-   <span class="function">zip\_entry\_close</span>
-   <span class="function">zip\_entry\_read</span>

### Changelog

| Version | Description                                             |
|---------|---------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API. |

zip\_entry\_read
================

Read from an open directory entry

### Description

<span class="type">string</span> <span
class="methodname">zip\_entry\_read</span> ( <span
class="methodparam"><span class="type">resource</span>
`$zip_entry`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`<span class="initializer"> =
1024</span></span> \] )

Reads from an open directory entry.

### Parameters

`zip_entry`  
A directory entry returned by <span class="function">zip\_read</span>.

`length`  
The number of bytes to return.

> **Note**:
>
> This should be the uncompressed length you wish to read.

### Return Values

Returns the data read, empty string on end of a file, or **`FALSE`** on
error.

### See Also

-   <span class="function">zip\_entry\_open</span>
-   <span class="function">zip\_entry\_close</span>
-   <span class="function">zip\_entry\_filesize</span>

### Changelog

| Version | Description                                                                                                           |
|---------|-----------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API, see <span class="methodname">ZipArchive::getFromIndex</span>. |

zip\_open
=========

Open a ZIP file archive

### Description

<span class="type">resource</span> <span
class="methodname">zip\_open</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> )

Opens a new zip archive for reading.

### Parameters

`filename`  
The file name of the ZIP archive to open.

### Return Values

Returns a resource handle for later use with <span
class="function">zip\_read</span> and <span
class="function">zip\_close</span> or returns the number of error if
`filename` does not exist or in case of other error.

### See Also

-   <span class="function">zip\_read</span>
-   <span class="function">zip\_close</span>

### Changelog

| Version | Description                                                                                                   |
|---------|---------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API, see <span class="methodname">ZipArchive::open</span>. |

zip\_read
=========

Read next entry in a ZIP file archive

### Description

<span class="type">resource</span> <span
class="methodname">zip\_read</span> ( <span class="methodparam"><span
class="type">resource</span> `$zip`</span> )

Reads the next entry in a zip file archive.

### Parameters

`zip`  
A ZIP file previously opened with <span
class="function">zip\_open</span>.

### Return Values

Returns a directory entry resource for later use with the
*zip\_entry\_...* functions, or **`FALSE`** if there are no more entries
to read, or an error code if an error occurred.

### See Also

-   <span class="function">zip\_open</span>
-   <span class="function">zip\_close</span>
-   <span class="function">zip\_entry\_open</span>
-   <span class="function">zip\_entry\_read</span>

### Changelog

| Version | Description                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function is deprecated in favor of the Object API, see <span class="methodname">ZipArchive::statIndex</span>. |

**Table of Contents**

-   [zip\_close](/ref/zip.html#zip_close) — Close a ZIP file archive
-   [zip\_entry\_close](/ref/zip.html#zip_entry_close) — Close a
    directory entry
-   [zip\_entry\_compressedsize](/ref/zip.html#zip_entry_compressedsize)
    — Retrieve the compressed size of a directory entry
-   [zip\_entry\_compressionmethod](/ref/zip.html#zip_entry_compressionmethod)
    — Retrieve the compression method of a directory entry
-   [zip\_entry\_filesize](/ref/zip.html#zip_entry_filesize) — Retrieve
    the actual file size of a directory entry
-   [zip\_entry\_name](/ref/zip.html#zip_entry_name) — Retrieve the name
    of a directory entry
-   [zip\_entry\_open](/ref/zip.html#zip_entry_open) — Open a directory
    entry for reading
-   [zip\_entry\_read](/ref/zip.html#zip_entry_read) — Read from an open
    directory entry
-   [zip\_open](/ref/zip.html#zip_open) — Open a ZIP file archive
-   [zip\_read](/ref/zip.html#zip_read) — Read next entry in a ZIP file
    archive

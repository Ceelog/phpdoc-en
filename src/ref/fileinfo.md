finfo\_buffer
=============

finfo::buffer
=============

Return information about a string buffer

### Description

Procedural style

<span class="type">string</span> <span
class="methodname">finfo\_buffer</span> ( <span
class="methodparam"><span class="type">resource</span> `$finfo`</span> ,
<span class="methodparam"><span class="type">string</span>
`$string`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`<span class="initializer"> =
FILEINFO\_NONE</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\] )

Object oriented style

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">finfo::buffer</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = FILEINFO\_NONE</span></span> \[,
<span class="methodparam"><span class="type">resource</span>
`$context`</span> \]\] )

This function is used to get information about binary data in a string.

### Parameters

`finfo`  
Fileinfo resource returned by <span class="function">finfo\_open</span>.

`string`  
Content of a file to be checked.

`options`  
One or disjunction of more
<a href="/fileinfo/constants.html" class="link">Fileinfo constants</a>.

`context`  

### Return Values

Returns a textual description of the `string` argument, or **`FALSE`**
if an error occurred.

### Examples

**Example \#1 A <span class="function">finfo\_buffer</span> example**

``` php
<?php
$finfo = new finfo(FILEINFO_MIME);
echo $finfo->buffer($_POST["script"]) . "\n";
?>
```

The above example will output something similar to:

    application/x-sh; charset=us-ascii

### See Also

-   <span class="function">finfo\_file</span>

finfo\_close
============

Close fileinfo resource

### Description

<span class="type">bool</span> <span
class="methodname">finfo\_close</span> ( <span class="methodparam"><span
class="type">resource</span> `$finfo`</span> )

This function closes the resource opened by <span
class="function">finfo\_open</span>.

### Parameters

`finfo`  
Fileinfo resource returned by <span class="function">finfo\_open</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

finfo\_file
===========

finfo::file
===========

Return information about a file

### Description

Procedural style

<span class="type">string</span> <span
class="methodname">finfo\_file</span> ( <span class="methodparam"><span
class="type">resource</span> `$finfo`</span> , <span
class="methodparam"><span class="type">string</span> `$file_name`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = FILEINFO\_NONE</span></span> \[,
<span class="methodparam"><span class="type">resource</span>
`$context`</span> \]\] )

Object oriented style

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">finfo::file</span> ( <span
class="methodparam"><span class="type">string</span> `$file_name`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = FILEINFO\_NONE</span></span> \[,
<span class="methodparam"><span class="type">resource</span>
`$context`</span> \]\] )

This function is used to get information about a file.

### Parameters

`finfo`  
Fileinfo resource returned by <span class="function">finfo\_open</span>.

`file_name`  
Name of a file to be checked.

`options`  
One or disjunction of more
<a href="/fileinfo/constants.html" class="link">Fileinfo constants</a>.

`context`  
For a description of *contexts*, refer to
<a href="/ref/stream.html" class="xref">Stream Functions</a>.

### Return Values

Returns a textual description of the contents of the `file_name`
argument, or **`FALSE`** if an error occurred.

### Examples

**Example \#1 A <span class="function">finfo\_file</span> example**

``` php
<?php
$finfo = finfo_open(FILEINFO_MIME_TYPE); // return mime type ala mimetype extension
foreach (glob("*") as $filename) {
    echo finfo_file($finfo, $filename) . "\n";
}
finfo_close($finfo);
?>
```

The above example will output something similar to:

    text/html
    image/gif
    application/vnd.ms-excel

### See Also

-   <span class="function">finfo\_buffer</span>

finfo\_open
===========

finfo::\_\_construct
====================

Create a new fileinfo resource

### Description

Procedural style

<span class="type">resource</span> <span
class="methodname">finfo\_open</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = FILEINFO\_NONE</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$magic_file`<span
class="initializer"> = ""</span></span> \]\] )

Object oriented style (constructor):

<span class="modifier">public</span> <span
class="methodname">finfo::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = FILEINFO\_NONE</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$magic_file`<span
class="initializer"> = ""</span></span> \]\] )

This function opens a magic database and returns its resource.

### Parameters

`options`  
One or disjunction of more
<a href="/fileinfo/constants.html" class="link">Fileinfo constants</a>.

`magic_file`  
Name of a magic database file, usually something like
`/path/to/magic.mime`. If not specified, the *MAGIC* environment
variable is used. If the environment variable isn't set, then PHP's
bundled magic database will be used.

Passing **`NULL`** or an empty string will be equivalent to the default
value.

### Return Values

(Procedural style only) Returns a magic database resource on success or
**`FALSE`** on failure.

### Notes

**Warning**

The expected magic database format changed in PHP 5.3.11 and 5.4.1. Due
to this, the internal magic database was upgraded. This mostly effects
code where an external magic database is used: reading an older magic
file will now fail. Also, some textual representations of the mime types
has changed, for instance for PHP would be "PHP script, ASCII text"
instead of "PHP script text" returned.

> **Note**:
>
> Generally, using the bundled magic database (by leaving `magic_file`
> and the *MAGIC* environment variables unset) is the best course of
> action unless you specifically need a custom magic database.

### Examples

**Example \#1 Object oriented style**

``` php
<?php
$finfo = new finfo(FILEINFO_MIME, "/usr/share/misc/magic"); // return mime type ala mimetype extension

/* get mime-type for a specific file */
$filename = "/usr/local/something.txt";
echo $finfo->file($filename);

?>
```

**Example \#2 Procedural style**

``` php
<?php
$finfo = finfo_open(FILEINFO_MIME, "/usr/share/misc/magic"); // return mime type ala mimetype extension

if (!$finfo) {
    echo "Opening fileinfo database failed";
    exit();
}

/* get mime-type for a specific file */
$filename = "/usr/local/something.txt";
echo finfo_file($finfo, $filename);

/* close connection */
finfo_close($finfo);
?>
```

The above example will output:

    text/plain; charset=us-ascii

### See Also

-   <span class="function">finfo\_close</span>

finfo\_set\_flags
=================

finfo::set\_flags
=================

Set libmagic configuration options

### Description

Procedural style

<span class="type">bool</span> <span
class="methodname">finfo\_set\_flags</span> ( <span
class="methodparam"><span class="type">resource</span> `$finfo`</span> ,
<span class="methodparam"><span class="type">int</span>
`$options`</span> )

Object oriented style

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">finfo::set\_flags</span> ( <span
class="methodparam"><span class="type">int</span> `$options`</span> )

This function sets various Fileinfo options. Options can be set also
directly in <span class="function">finfo\_open</span> or other Fileinfo
functions.

### Parameters

`finfo`  
Fileinfo resource returned by <span class="function">finfo\_open</span>.

`options`  
One or disjunction of more
<a href="/fileinfo/constants.html" class="link">Fileinfo constants</a>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

mime\_content\_type
===================

Detect MIME Content-type for a file

### Description

<span class="type">string</span> <span
class="methodname">mime\_content\_type</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Returns the MIME content type for a file as determined by using
information from the `magic.mime` file.

### Parameters

`filename`  
Path to the tested file.

### Return Values

Returns the content type in MIME format, like *text/plain* or
*application/octet-stream*, or **`FALSE`** on failure.

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Examples

**Example \#1 <span class="function">mime\_content\_type</span>
Example**

``` php
<?php
echo mime_content_type('php.gif') . "\n";
echo mime_content_type('test.php');
?>
```

The above example will output:

    image/gif
    text/plain

### See Also

-   <span class="function">finfo\_file</span>
-   <span class="function">finfo\_buffer</span>

**Table of Contents**

-   [finfo\_buffer](/ref/fileinfo.html#finfo_buffer) — Return
    information about a string buffer
-   [finfo\_close](/ref/fileinfo.html#finfo_close) — Close fileinfo
    resource
-   [finfo\_file](/ref/fileinfo.html#finfo_file) — Return information
    about a file
-   [finfo\_open](/ref/fileinfo.html#finfo_open) — Create a new fileinfo
    resource
-   [finfo\_set\_flags](/ref/fileinfo.html#finfo_set_flags) — Set
    libmagic configuration options
-   [mime\_content\_type](/ref/fileinfo.html#mime_content_type) — Detect
    MIME Content-type for a file

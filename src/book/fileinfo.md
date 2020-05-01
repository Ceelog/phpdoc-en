File Information
================

**Table of Contents**

-   [Introduction](/intro/fileinfo.html)
-   [Installing/Configuring](/fileinfo/setup.html)
    -   [Requirements](/fileinfo/setup.html#Requirements)
    -   [Installation](/fileinfo/setup.html#Installation)
    -   [Runtime
        Configuration](/fileinfo/setup.html#Runtime%20Configuration)
    -   [Resource Types](/fileinfo/setup.html#Resource%20Types)
-   [Predefined Constants](/fileinfo/constants.html)
-   [Fileinfo Functions](/ref/fileinfo.html)
    -   [finfo\_buffer](/ref/fileinfo.html#finfo_buffer) — Return
        information about a string buffer
    -   [finfo\_close](/ref/fileinfo.html#finfo_close) — Close fileinfo
        resource
    -   [finfo\_file](/ref/fileinfo.html#finfo_file) — Return
        information about a file
    -   [finfo\_open](/ref/fileinfo.html#finfo_open) — Create a new
        fileinfo resource
    -   [finfo\_set\_flags](/ref/fileinfo.html#finfo_set_flags) — Set
        libmagic configuration options
    -   [mime\_content\_type](/ref/fileinfo.html#mime_content_type) —
        Detect MIME Content-type for a file
-   [finfo](/class/finfo.html) — The finfo class
    -   [finfo::buffer](/class/finfo.html#finfo::buffer) — Alias of
        finfo\_buffer()
    -   [finfo::\_\_construct](/class/finfo.html#finfo::__construct) —
        Alias of finfo\_open
    -   [finfo::file](/class/finfo.html#finfo::file) — Alias of
        finfo\_file()
    -   [finfo::set\_flags](/class/finfo.html#finfo::set_flags) — Alias
        of finfo\_set\_flags()

Introduction
------------

This class provides an object oriented interface into the fileinfo
functions.

Class synopsis
--------------

**finfo**

<span class="ooclass"> class **finfo** </span> {

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = FILEINFO\_NONE</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$magic_file`<span
class="initializer"> = ""</span></span> \]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">buffer</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = FILEINFO\_NONE</span></span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`</span>
\]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">file</span> ( <span class="methodparam"><span
class="type">string</span> `$file_name`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = FILEINFO\_NONE</span></span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`</span>
\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">set\_flags</span> ( <span
class="methodparam"><span class="type">int</span> `$options`</span> )

}

finfo::buffer
=============

Alias of
<a href="/ref/fileinfo.html#finfo_buffer" class="link">finfo_buffer()</a>

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">finfo::buffer</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = FILEINFO\_NONE</span></span> \[,
<span class="methodparam"><span class="type">resource</span>
`$context`</span> \]\] )

This function is an alias of:
<a href="/ref/fileinfo.html#finfo_buffer" class="link">finfo_buffer()</a>

finfo::\_\_construct
====================

Alias of <span class="function">finfo\_open</span>

### Description

<span class="modifier">public</span> <span
class="methodname">finfo::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = FILEINFO\_NONE</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$magic_file`<span
class="initializer"> = ""</span></span> \]\] )

This function is an alias of: <span class="function">finfo\_open</span>

finfo::file
===========

Alias of
<a href="/ref/fileinfo.html#finfo_file" class="link">finfo_file()</a>

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">finfo::file</span> ( <span
class="methodparam"><span class="type">string</span> `$file_name`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = FILEINFO\_NONE</span></span> \[,
<span class="methodparam"><span class="type">resource</span>
`$context`</span> \]\] )

This function is an alias of:
<a href="/ref/fileinfo.html#finfo_file" class="link">finfo_file()</a>

finfo::set\_flags
=================

Alias of
<a href="/ref/fileinfo.html#finfo_set_flags" class="link">finfo_set_flags()</a>

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">finfo::set\_flags</span> ( <span
class="methodparam"><span class="type">int</span> `$options`</span> )

This function is an alias of:
<a href="/ref/fileinfo.html#finfo_set_flags" class="link">finfo_set_flags()</a>

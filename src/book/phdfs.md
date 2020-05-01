Phdfs
=====

**Table of Contents**

-   [](/intro/phdfs.html)
-   [Installing/Configuring](/phdfs/setup.html)
    -   [Requirements](/phdfs/setup.html#Requirements)
    -   [Installation](/phdfs/setup.html#Installation)
    -   [](/phdfs/setup.html#)
    -   [Resource Types](/phdfs/setup.html#Resource%20Types)
-   [Predefined Constants](/phdfs/constants.html)
-   [phdfs](/class/phdfs.html) — The phdfs class
    -   [phdfs::connect](/class/phdfs.html#phdfs::connect) — Description
    -   [phdfs::\_\_construct](/class/phdfs.html#phdfs::__construct) —
        Description
    -   [phdfs::copy](/class/phdfs.html#phdfs::copy) — Description
    -   [phdfs::create\_directory](/class/phdfs.html#phdfs::create_directory)
        — Description
    -   [phdfs::delete](/class/phdfs.html#phdfs::delete) — Description
    -   [phdfs::\_\_destruct](/class/phdfs.html#phdfs::__destruct) —
        Description
    -   [phdfs::disconnect](/class/phdfs.html#phdfs::disconnect) —
        Description
    -   [phdfs::exists](/class/phdfs.html#phdfs::exists) — Description
    -   [phdfs::file\_info](/class/phdfs.html#phdfs::file_info) —
        Description
    -   [phdfs::list\_directory](/class/phdfs.html#phdfs::list_directory)
        — Description
    -   [phdfs::read](/class/phdfs.html#phdfs::read) — Description
    -   [phdfs::rename](/class/phdfs.html#phdfs::rename) — Description
    -   [phdfs::tell](/class/phdfs.html#phdfs::tell) — Description
    -   [phdfs::write](/class/phdfs.html#phdfs::write) — Description

Introduction
------------

Class synopsis
--------------

**phdfs**

<span class="ooclass"> class **phdfs** </span> {

/\* Properties \*/

<span class="modifier">static</span> `$host` ;

<span class="modifier">static</span> `$port` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">connect</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$ip`</span> ,
<span class="methodparam"><span class="type">string</span>
`$port`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">copy</span> ( <span class="methodparam"><span
class="type">string</span> `$source_file`</span> , <span
class="methodparam"><span class="type">string</span>
`$destination_file`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">create\_directory</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">delete</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">disconnect</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">exists</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">file\_info</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">list\_directory</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">int</span> `$level`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">read</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">rename</span> ( <span class="methodparam"><span
class="type">string</span> `$old_path`</span> , <span
class="methodparam"><span class="type">string</span> `$new_path`</span>
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">tell</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">int</span> `$read_length`<span
class="initializer"> = 1024</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">write</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> , <span
class="methodparam"><span class="type">string</span> `$buffer`</span>
\[, <span class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = 0</span></span> \] )

}

Properties
----------

`host`  

`port`  

phdfs::connect
==============

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">phdfs::connect</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

phdfs::\_\_construct
====================

Description

### Description

<span class="modifier">public</span> <span
class="methodname">phdfs::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$ip`</span> ,
<span class="methodparam"><span class="type">string</span>
`$port`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`ip`  

`port`  

### Return Values

phdfs::copy
===========

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">phdfs::copy</span> ( <span
class="methodparam"><span class="type">string</span>
`$source_file`</span> , <span class="methodparam"><span
class="type">string</span> `$destination_file`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`source_file`  

`destination_file`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

phdfs::create\_directory
========================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">phdfs::create\_directory</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

phdfs::delete
=============

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">phdfs::delete</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

phdfs::\_\_destruct
===================

Description

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">phdfs::\_\_destruct</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

phdfs::disconnect
=================

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">phdfs::disconnect</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

phdfs::exists
=============

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">phdfs::exists</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

phdfs::file\_info
=================

Description

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">phdfs::file\_info</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  

### Return Values

Returns array on success or **`FALSE`** on failure.

phdfs::list\_directory
======================

Description

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">phdfs::list\_directory</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">int</span> `$level`<span
class="initializer"> = 0</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  

`level`  

### Return Values

Returns array on success or **`FALSE`** on failure.

phdfs::read
===========

Description

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">phdfs::read</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  

`length`  

### Return Values

phdfs::rename
=============

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">phdfs::rename</span> ( <span
class="methodparam"><span class="type">string</span> `$old_path`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_path`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`old_path`  

`new_path`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

phdfs::tell
===========

Description

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">phdfs::tell</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">int</span> `$read_length`<span
class="initializer"> = 1024</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  

`read_length`  

### Return Values

phdfs::write
============

Description

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">phdfs::write</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> ,
<span class="methodparam"><span class="type">string</span>
`$buffer`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
0</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  

`buffer`  

`mode`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

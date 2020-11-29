xdiff\_file\_bdiff\_size
========================

Read a size of file created by applying a binary diff

### Description

<span class="type">int</span> <span
class="methodname">xdiff\_file\_bdiff\_size</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> )

Returns a size of a result file that would be created after applying
binary patch from file `file` to the original file.

### Parameters

`file`  
The path to the binary patch created by <span
class="function">xdiff\_string\_bdiff</span> or <span
class="function">xdiff\_string\_rabdiff</span> function.

### Return Values

Returns the size of file that would be created.

### Examples

**Example \#1 <span class="function">xdiff\_file\_bdiff\_size</span>
example**

The following code applies reads a size of file that would be created
after applying a binary diff.

``` php
<?php
$length = xdiff_string_bdiff_size('file.bdiff');
echo "Resulting file will be $length bytes long";
?>
```

### See Also

-   <span class="function">xdiff\_file\_bdiff</span>
-   <span class="function">xdiff\_file\_rabdiff</span>
-   <span class="function">xdiff\_file\_bpatch</span>

xdiff\_file\_bdiff
==================

Make binary diff of two files

### Description

<span class="type">bool</span> <span
class="methodname">xdiff\_file\_bdiff</span> ( <span
class="methodparam"><span class="type">string</span> `$old_file`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_file`</span> , <span class="methodparam"><span
class="type">string</span> `$dest`</span> )

Makes a binary diff of two files and stores the result in a patch file.
This function works with both text and binary files. Resulting patch
file can be later applied using <span
class="function">xdiff\_file\_bpatch</span>/<span
class="function">xdiff\_string\_bpatch</span>.

### Parameters

`old_file`  
Path to the first file. This file acts as "old" file.

`new_file`  
Path to the second file. This file acts as "new" file.

`dest`  
Path of the resulting patch file. Resulting file contains differences
between "old" and "new" files. It is in binary format and is
human-unreadable.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">xdiff\_file\_bdiff</span> example**

The following code makes binary diff of two archives.

``` php
<?php
$old_version = 'my_script_1.0.tgz';
$new_version = 'my_script_1.1.tgz';

xdiff_file_bdiff($old_version, $new_version, 'my_script.bdiff');
?>
```

### Notes

> **Note**:
>
> Both files will be loaded into memory so ensure that your
> memory\_limit is set high enough.

### See Also

-   <span class="function">xdiff\_file\_bpatch</span>

xdiff\_file\_bpatch
===================

Patch a file with a binary diff

### Description

<span class="type">bool</span> <span
class="methodname">xdiff\_file\_bpatch</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> ,
<span class="methodparam"><span class="type">string</span>
`$patch`</span> , <span class="methodparam"><span
class="type">string</span> `$dest`</span> )

Patches a `file` with a binary `patch` and stores the result in a file
`dest`. This function accepts patches created both via <span
class="function">xdiff\_file\_bdiff</span> and <span
class="function">xdiff\_file\_rabdiff</span> functions or their string
counterparts.

### Parameters

`file`  
The original file.

`patch`  
The binary patch file.

`dest`  
Path of the resulting file.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">xdiff\_file\_bpatch</span>
example**

The following code applies binary diff to a file.

``` php
<?php
$old_version = 'archive-1.0.tgz';
$patch = 'archive.bpatch';

$result = xdiff_file_bpatch($old_version, $patch, 'archive-1.1.tgz');
if ($result) {
   echo "File patched";
} else {
   echo "File couldn't be patched";
}

?>
```

### Notes

> **Note**:
>
> Both files (`file` and `patch`) will be loaded into memory so ensure
> that your memory\_limit is set high enough.

### See Also

-   <span class="function">xdiff\_file\_bdiff</span>
-   <span class="function">xdiff\_file\_rabdiff</span>

xdiff\_file\_diff\_binary
=========================

Alias of xdiff\_file\_bdiff

### Description

<span class="type">bool</span> <span
class="methodname">xdiff\_file\_diff\_binary</span> ( <span
class="methodparam"><span class="type">string</span> `$old_file`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_file`</span> , <span class="methodparam"><span
class="type">string</span> `$dest`</span> )

Makes a binary diff of two files and stores the result in a patch file.
This function works with both text and binary files. Resulting patch
file can be later applied using <span
class="function">xdiff\_file\_bpatch</span>.

Starting with version 1.5.0 this function is an alias of <span
class="function">xdiff\_file\_bdiff</span>.

### Parameters

`old_file`  
Path to the first file. This file acts as "old" file.

`new_file`  
Path to the second file. This file acts as "new" file.

`dest`  
Path of the resulting patch file. Resulting file contains differences
between "old" and "new" files. It is in binary format and is
human-unreadable.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">xdiff\_file\_diff\_binary</span>
example**

The following code makes binary diff of two archives.

``` php
<?php
$old_version = 'my_script_1.0.tgz';
$new_version = 'my_script_1.1.tgz';

xdiff_file_diff_binary($old_version, $new_version, 'my_script.bdiff');
?>
```

### Notes

> **Note**:
>
> Both files will be loaded into memory so ensure that your
> memory\_limit is set high enough.

### See Also

-   <span class="function">xdiff\_file\_bdiff</span>
-   <span class="function">xdiff\_file\_bpatch</span>

xdiff\_file\_diff
=================

Make unified diff of two files

### Description

<span class="type">bool</span> <span
class="methodname">xdiff\_file\_diff</span> ( <span
class="methodparam"><span class="type">string</span> `$old_file`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_file`</span> , <span class="methodparam"><span
class="type">string</span> `$dest`</span> \[, <span
class="methodparam"><span class="type">int</span> `$context`<span
class="initializer"> = 3</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$minimal`<span
class="initializer"> = **`FALSE`**</span></span> \]\] )

Makes an unified diff containing differences between `old_file` and
`new_file` and stores it in `dest` file. The resulting file is
human-readable. An optional `context` parameter specifies how many lines
of context should be added around each change. Setting `minimal`
parameter to true will result in outputting the shortest patch file
possible (can take a long time).

### Parameters

`old_file`  
Path to the first file. This file acts as "old" file.

`new_file`  
Path to the second file. This file acts as "new" file.

`dest`  
Path of the resulting patch file.

`context`  
Indicates how many lines of context you want to include in diff result.

`minimal`  
Set this parameter to **`TRUE`** if you want to minimalize size of the
result (can take a long time).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">xdiff\_file\_diff</span> example**

The following code makes unified diff of two php files with context
length of 2.

``` php
<?php
$old_version = 'my_script.php';
$new_version = 'my_new_script.php';

xdiff_file_diff($old_version, $new_version, 'my_script.diff', 2);
?>
```

### Notes

> **Note**:
>
> This function doesn't work well with binary files. To make diff of
> binary files use <span
> class="function">xdiff\_file\_bdiff</span>/<span
> class="function">xdiff\_file\_rabdiff</span> function.

### See Also

-   <span class="function">xdiff\_file\_patch</span>

xdiff\_file\_merge3
===================

Merge 3 files into one

### Description

<span class="type">mixed</span> <span
class="methodname">xdiff\_file\_merge3</span> ( <span
class="methodparam"><span class="type">string</span> `$old_file`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_file1`</span> , <span class="methodparam"><span
class="type">string</span> `$new_file2`</span> , <span
class="methodparam"><span class="type">string</span> `$dest`</span> )

Merges three files into one and stores the result in a file `dest`. The
`old_file` is an original version while `new_file1` and `new_file2` are
modified versions of an original.

### Parameters

`old_file`  
Path to the first file. It acts as "old" file.

`new_file1`  
Path to the second file. It acts as modified version of `old_file`.

`new_file2`  
Path to the third file. It acts as modified version of `old_file`.

`dest`  
Path of the resulting file, containing merged changed from both
`new_file1` and `new_file2`.

### Return Values

Returns **`TRUE`** if merge was successful, string with rejected chunks
if it was not or **`FALSE`** if an internal error happened.

### Examples

**Example \#1 <span class="function">xdiff\_file\_merge3</span>
example**

The following code merges three files into one.

``` php
<?php
$old_version = 'original_script.php';
$fix1 = 'script_with_fix1.php';
$fix2 = 'script_with_fix2.php';

$errors = xdiff_file_merge3($old_version, $fix1, $fix2, 'fixed_script.php');
if (is_string($errors)) {
    echo "Rejects:\n";
    echo $errors;
}
?>
```

### See Also

-   <span class="function">xdiff\_string\_merge3</span>

xdiff\_file\_patch\_binary
==========================

Alias of xdiff\_file\_bpatch

### Description

<span class="type">bool</span> <span
class="methodname">xdiff\_file\_patch\_binary</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> ,
<span class="methodparam"><span class="type">string</span>
`$patch`</span> , <span class="methodparam"><span
class="type">string</span> `$dest`</span> )

Patches a `file` with a binary `patch` and stores the result in a file
`dest`. This function accepts patches created both via <span
class="function">xdiff\_file\_bdiff</span> or <span
class="function">xdiff\_file\_rabdiff</span> functions or their string
counterparts.

Starting with version 1.5.0 this function is an alias of <span
class="function">xdiff\_file\_bpatch</span>.

### Parameters

`file`  
The original file.

`patch`  
The binary patch file.

`dest`  
Path of the resulting file.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">xdiff\_file\_patch\_binary</span>
example**

The following code applies binary diff to a file.

``` php
<?php
$old_version = 'archive-1.0.tgz';
$patch = 'archive.bpatch';

$result = xdiff_file_patch_binary($old_version, $patch, 'archive-1.1.tgz');
if ($result) {
   echo "File patched";
} else {
   echo "File couldn't be patched";
}

?>
```

### Notes

> **Note**:
>
> Both files (`file` and `patch`) will be loaded into memory so ensure
> that your memory\_limit is set high enough.

### See Also

-   <span class="function">xdiff\_string\_patch\_binary</span>

xdiff\_file\_patch
==================

Patch a file with an unified diff

### Description

<span class="type">mixed</span> <span
class="methodname">xdiff\_file\_patch</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> ,
<span class="methodparam"><span class="type">string</span>
`$patch`</span> , <span class="methodparam"><span
class="type">string</span> `$dest`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = DIFF\_PATCH\_NORMAL</span></span> \] )

Patches a `file` with a `patch` and stores the result in a file. `patch`
has to be an unified diff created by <span
class="function">xdiff\_file\_diff</span>/<span
class="function">xdiff\_string\_diff</span> function. An optional
`flags` parameter specifies mode of operation.

### Parameters

`file`  
The original file.

`patch`  
The unified patch file. It has to be created using <span
class="function">xdiff\_string\_diff</span>, <span
class="function">xdiff\_file\_diff</span> functions or compatible tools.

`dest`  
Path of the resulting file.

`flags`  
Can be either **`XDIFF_PATCH_NORMAL`** (default mode, normal patch) or
**`XDIFF_PATCH_REVERSE`** (reversed patch).

Starting from version 1.5.0, you can also use binary OR to enable
**`XDIFF_PATCH_IGNORESPACE`** flag.

### Return Values

Returns **`FALSE`** if an internal error happened, string with rejected
chunks if patch couldn't be applied or **`TRUE`** if patch has been
successfully applied.

### Examples

**Example \#1 <span class="function">xdiff\_file\_patch</span> example**

The following code applies unified diff to a file.

``` php
<?php
$old_version = 'my_script-1.0.php';
$patch = 'my_script.patch';

$errors = xdiff_file_patch($old_version, $patch, 'my_script-1.1.php');
if (is_string($errors)) {
   echo "Rejects:\n";
   echo $errors;
}

?>
```

**Example \#2 Patch reversing example**

The following code reverses a patch.

``` php
<?php
$new_version = 'my_script-1.1.php';
$patch = 'my_script.patch';

$errors = xdiff_file_patch($new_version, $patch, 'my_script-1.0.php', XDIFF_PATCH_REVERSE);
if (is_string($errors)) {
   echo "Rejects:\n";
   echo $errors;
}

?>
```

### See Also

-   <span class="function">xdiff\_file\_diff</span>

xdiff\_file\_rabdiff
====================

Make binary diff of two files using the Rabin's polynomial
fingerprinting algorithm

### Description

<span class="type">bool</span> <span
class="methodname">xdiff\_file\_rabdiff</span> ( <span
class="methodparam"><span class="type">string</span> `$old_file`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_file`</span> , <span class="methodparam"><span
class="type">string</span> `$dest`</span> )

Makes a binary diff of two files and stores the result in a patch file.
The difference between this function and <span
class="function">xdiff\_file\_bdiff</span> is different algorithm used
which should result in faster execution and smaller diff produced. This
function works with both text and binary files. Resulting patch file can
be later applied using <span
class="function">xdiff\_file\_bpatch</span>/<span
class="function">xdiff\_string\_bpatch</span>.

For more details about differences between algorithm used please check
<a href="http://www.xmailserver.org/xdiff-lib.html" class="link external">» libxdiff</a>
website.

### Parameters

`old_file`  
Path to the first file. This file acts as "old" file.

`new_file`  
Path to the second file. This file acts as "new" file.

`dest`  
Path of the resulting patch file. Resulting file contains differences
between "old" and "new" files. It is in binary format and is
human-unreadable.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">xdiff\_file\_rabdiff</span>
example**

The following code makes binary diff of two archives.

``` php
<?php
$old_version = 'my_script_1.0.tgz';
$new_version = 'my_script_1.1.tgz';

xdiff_file_rabdiff($old_version, $new_version, 'my_script.bdiff');
?>
```

### Notes

> **Note**:
>
> Both files will be loaded into memory so ensure that your
> memory\_limit is set high enough.

### See Also

-   <span class="function">xdiff\_file\_bpatch</span>

xdiff\_string\_bdiff\_size
==========================

Read a size of file created by applying a binary diff

### Description

<span class="type">int</span> <span
class="methodname">xdiff\_string\_bdiff\_size</span> ( <span
class="methodparam"><span class="type">string</span> `$patch`</span> )

Returns a size of a result file that would be created after applying
binary `patch` to the original file.

### Parameters

`patch`  
The binary patch created by <span
class="function">xdiff\_string\_bdiff</span> or <span
class="function">xdiff\_string\_rabdiff</span> function.

### Return Values

Returns the size of file that would be created.

### Examples

**Example \#1 <span class="function">xdiff\_string\_bdiff\_size</span>
example**

The following code applies reads a size of file that would be created
after applying a binary diff.

``` php
<?php
$binary_patch = file_get_contents('file.bdiff');
$length = xdiff_string_bdiff_size($binary_patch);
echo "Resulting file will be $length bytes long";
?>
```

### See Also

-   <span class="function">xdiff\_string\_bdiff</span>
-   <span class="function">xdiff\_string\_rabdiff</span>
-   <span class="function">xdiff\_string\_bpatch</span>

xdiff\_string\_bdiff
====================

Make binary diff of two strings

### Description

<span class="type">string</span> <span
class="methodname">xdiff\_string\_bdiff</span> ( <span
class="methodparam"><span class="type">string</span> `$old_data`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_data`</span> )

Makes a binary diff of two strings and returns the result. This function
works with both text and binary data. Resulting patch can be later
applied using <span class="function">xdiff\_string\_bpatch</span>/<span
class="function">xdiff\_file\_bpatch</span>.

### Parameters

`old_data`  
First string with binary data. It acts as "old" data.

`new_data`  
Second string with binary data. It acts as "new" data.

### Return Values

Returns string with binary diff containing differences between "old" and
"new" data or **`FALSE`** if an internal error occurred.

### See Also

-   <span class="function">xdiff\_string\_bpatch</span>

xdiff\_string\_bpatch
=====================

Patch a string with a binary diff

### Description

<span class="type">string</span> <span
class="methodname">xdiff\_string\_bpatch</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> ,
<span class="methodparam"><span class="type">string</span>
`$patch`</span> )

Patches a string `str` with a binary `patch`. This function accepts
patches created both via <span
class="function">xdiff\_string\_bdiff</span> and <span
class="function">xdiff\_string\_rabdiff</span> functions or their file
counterparts.

### Parameters

`str`  
The original binary string.

`patch`  
The binary patch string.

### Return Values

Returns the patched string, or **`FALSE`** on error.

### See Also

-   <span class="function">xdiff\_string\_bdiff</span>
-   <span class="function">xdiff\_string\_rabdiff</span>

xdiff\_string\_diff\_binary
===========================

Alias of xdiff\_string\_bdiff

### Description

<span class="type">string</span> <span
class="methodname">xdiff\_string\_bdiff</span> ( <span
class="methodparam"><span class="type">string</span> `$old_data`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_data`</span> )

Makes a binary diff of two strings and returns the result. This function
works with both text and binary data. Resulting patch can be later
applied using <span class="function">xdiff\_string\_bpatch</span>/<span
class="function">xdiff\_file\_bpatch</span>.

Starting with version 1.5.0 this function is an alias of <span
class="function">xdiff\_string\_bdiff</span>.

### Parameters

`old_data`  
First string with binary data. It acts as "old" data.

`new_data`  
Second string with binary data. It acts as "new" data.

### Return Values

Returns string with result or **`FALSE`** if an internal error happened.

### See Also

-   <span class="function">xdiff\_string\_bdiff</span>
-   <span class="function">xdiff\_string\_bpatch</span>

xdiff\_string\_diff
===================

Make unified diff of two strings

### Description

<span class="type">string</span> <span
class="methodname">xdiff\_string\_diff</span> ( <span
class="methodparam"><span class="type">string</span> `$old_data`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_data`</span> \[, <span class="methodparam"><span
class="type">int</span> `$context`<span class="initializer"> =
3</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$minimal`<span class="initializer"> =
**`FALSE`**</span></span> \]\] )

Makes an unified diff containing differences between `old_data` string
and `new_data` string and returns it. The resulting diff is
human-readable. An optional `context` parameter specifies how many lines
of context should be added around each change. Setting `minimal`
parameter to true will result in outputting the shortest patch file
possible (can take a long time).

### Parameters

`old_data`  
First string with data. It acts as "old" data.

`new_data`  
Second string with data. It acts as "new" data.

`context`  
Indicates how many lines of context you want to include in the diff
result.

`minimal`  
Set this parameter to **`TRUE`** if you want to minimalize the size of
the result (can take a long time).

### Return Values

Returns string with resulting diff or **`FALSE`** if an internal error
happened.

### Examples

**Example \#1 <span class="function">xdiff\_string\_diff</span>
example**

The following code makes unified diff of two articles.

``` php
<?php
$old_article = file_get_contents('./old_article.txt');
$new_article = $_REQUEST['article']; /* Let's say that someone pasted a new article to html form */

$diff = xdiff_string_diff($old_article, $new_article, 1);
if (is_string($diff)) {
    echo "Differences between two articles:\n";
    echo $diff;
}

?>
```

### Notes

> **Note**:
>
> This function doesn't work well with binary strings. To make diff of
> binary strings use <span
> class="function">xdiff\_string\_bdiff</span>/<span
> class="function">xdiff\_string\_rabdiff</span>.

### See Also

-   <span class="function">xdiff\_string\_patch</span>

xdiff\_string\_merge3
=====================

Merge 3 strings into one

### Description

<span class="type">mixed</span> <span
class="methodname">xdiff\_string\_merge3</span> ( <span
class="methodparam"><span class="type">string</span> `$old_data`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_data1`</span> , <span class="methodparam"><span
class="type">string</span> `$new_data2`</span> \[, <span
class="methodparam"><span class="type">string</span> `&$error`</span> \]
)

Merges three strings into one and returns the result. The `old_data` is
an original version of data while `new_data1` and `new_data2` are
modified versions of an original. An optional `error` is used to pass
any rejected parts during merging process.

### Parameters

`old_data`  
First string with data. It acts as "old" data.

`new_data1`  
Second string with data. It acts as modified version of `old_data`.

`new_data2`  
Third string with data. It acts as modified version of `old_data`.

`error`  
If provided then rejected parts are stored inside this variable.

### Return Values

Returns the merged string, **`FALSE`** if an internal error happened, or
**`TRUE`** if merged string is empty.

### See Also

-   <span class="function">xdiff\_file\_merge3</span>

xdiff\_string\_patch\_binary
============================

Alias of xdiff\_string\_bpatch

### Description

<span class="type">string</span> <span
class="methodname">xdiff\_string\_patch\_binary</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> ,
<span class="methodparam"><span class="type">string</span>
`$patch`</span> )

Patches a string `str` with a binary `patch`. This function accepts
patches created both via <span
class="function">xdiff\_string\_bdiff</span> and <span
class="function">xdiff\_string\_rabdiff</span> functions or their file
counterparts.

Starting with version 1.5.0 this function is an alias of <span
class="function">xdiff\_string\_bpatch</span>.

### Parameters

`str`  
The original binary string.

`patch`  
The binary patch string.

### Return Values

Returns the patched string, or **`FALSE`** on error.

### See Also

-   <span class="function">xdiff\_string\_bpatch</span>
-   <span class="function">xdiff\_string\_bdiff</span>
-   <span class="function">xdiff\_string\_rabdiff</span>

xdiff\_string\_patch
====================

Patch a string with an unified diff

### Description

<span class="type">string</span> <span
class="methodname">xdiff\_string\_patch</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> ,
<span class="methodparam"><span class="type">string</span>
`$patch`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \[, <span
class="methodparam"><span class="type">string</span> `&$error`</span>
\]\] )

Patches a `str` string with an unified patch in `patch` parameter and
returns the result. `patch` has to be an unified diff created by <span
class="function">xdiff\_file\_diff</span>/<span
class="function">xdiff\_string\_diff</span> function. An optional
`flags` parameter specifies mode of operation. Any rejected parts of the
patch will be stored inside `error` variable if it is provided.

### Parameters

`str`  
The original string.

`patch`  
The unified patch string. It has to be created using <span
class="function">xdiff\_string\_diff</span>, <span
class="function">xdiff\_file\_diff</span> functions or compatible tools.

`flags`  
`flags` can be either **`XDIFF_PATCH_NORMAL`** (default mode, normal
patch) or **`XDIFF_PATCH_REVERSE`** (reversed patch).

Starting from version 1.5.0, you can also use binary OR to enable
**`XDIFF_PATCH_IGNORESPACE`** flag.

`error`  
If provided then rejected parts are stored inside this variable.

### Return Values

Returns the patched string, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">xdiff\_string\_patch</span>
example**

The following code applies changes to some article.

``` php
<?php
$old_article = file_get_contents('./old_article.txt');
$diff = $_SERVER['patch']; /* Let's say that someone pasted a patch to html form */

$errors = '';

$new_article = xdiff_string_patch($old_article, $diff, XDIFF_PATCH_NORMAL, $errors);
if (is_string($new_article)) {
    echo "New article:\n";
    echo $new_article;
}

if (strlen($errors)) {
    echo "Rejects: \n";
    echo $errors;
}

?>
```

### See Also

-   <span class="function">xdiff\_string\_diff</span>

xdiff\_string\_rabdiff
======================

Make binary diff of two strings using the Rabin's polynomial
fingerprinting algorithm

### Description

<span class="type">string</span> <span
class="methodname">xdiff\_string\_bdiff</span> ( <span
class="methodparam"><span class="type">string</span> `$old_data`</span>
, <span class="methodparam"><span class="type">string</span>
`$new_data`</span> )

Makes a binary diff of two strings and returns the result. The
difference between this function and <span
class="function">xdiff\_string\_bdiff</span> is different algorithm used
which should result in faster execution and smaller diff produced. This
function works with both text and binary data. Resulting patch can be
later applied using <span
class="function">xdiff\_string\_bpatch</span>/<span
class="function">xdiff\_file\_bpatch</span>.

For more details about differences between algorithm used please check
<a href="http://www.xmailserver.org/xdiff-lib.html" class="link external">» libxdiff</a>
website.

### Parameters

`old_data`  
First string with binary data. It acts as "old" data.

`new_data`  
Second string with binary data. It acts as "new" data.

### Return Values

Returns string with binary diff containing differences between "old" and
"new" data or **`FALSE`** if an internal error occurred.

### See Also

-   <span class="function">xdiff\_string\_bpatch</span>

**Table of Contents**

-   [xdiff\_file\_bdiff\_size](/ref/xdiff.html#xdiff_file_bdiff_size) —
    Read a size of file created by applying a binary diff
-   [xdiff\_file\_bdiff](/ref/xdiff.html#xdiff_file_bdiff) — Make binary
    diff of two files
-   [xdiff\_file\_bpatch](/ref/xdiff.html#xdiff_file_bpatch) — Patch a
    file with a binary diff
-   [xdiff\_file\_diff\_binary](/ref/xdiff.html#xdiff_file_diff_binary)
    — Alias of xdiff\_file\_bdiff
-   [xdiff\_file\_diff](/ref/xdiff.html#xdiff_file_diff) — Make unified
    diff of two files
-   [xdiff\_file\_merge3](/ref/xdiff.html#xdiff_file_merge3) — Merge 3
    files into one
-   [xdiff\_file\_patch\_binary](/ref/xdiff.html#xdiff_file_patch_binary)
    — Alias of xdiff\_file\_bpatch
-   [xdiff\_file\_patch](/ref/xdiff.html#xdiff_file_patch) — Patch a
    file with an unified diff
-   [xdiff\_file\_rabdiff](/ref/xdiff.html#xdiff_file_rabdiff) — Make
    binary diff of two files using the Rabin's polynomial fingerprinting
    algorithm
-   [xdiff\_string\_bdiff\_size](/ref/xdiff.html#xdiff_string_bdiff_size)
    — Read a size of file created by applying a binary diff
-   [xdiff\_string\_bdiff](/ref/xdiff.html#xdiff_string_bdiff) — Make
    binary diff of two strings
-   [xdiff\_string\_bpatch](/ref/xdiff.html#xdiff_string_bpatch) — Patch
    a string with a binary diff
-   [xdiff\_string\_diff\_binary](/ref/xdiff.html#xdiff_string_diff_binary)
    — Alias of xdiff\_string\_bdiff
-   [xdiff\_string\_diff](/ref/xdiff.html#xdiff_string_diff) — Make
    unified diff of two strings
-   [xdiff\_string\_merge3](/ref/xdiff.html#xdiff_string_merge3) — Merge
    3 strings into one
-   [xdiff\_string\_patch\_binary](/ref/xdiff.html#xdiff_string_patch_binary)
    — Alias of xdiff\_string\_bpatch
-   [xdiff\_string\_patch](/ref/xdiff.html#xdiff_string_patch) — Patch a
    string with an unified diff
-   [xdiff\_string\_rabdiff](/ref/xdiff.html#xdiff_string_rabdiff) —
    Make binary diff of two strings using the Rabin's polynomial
    fingerprinting algorithm

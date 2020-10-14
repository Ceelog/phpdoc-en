For related functions such as <span class="function">dirname</span>,
<span class="function">is\_dir</span>, <span
class="function">mkdir</span>, and <span class="function">rmdir</span>,
see the <a href="/ref/filesystem.html" class="link">Filesystem</a>
section.

chdir
=====

Change directory

### Description

<span class="type">bool</span> <span class="methodname">chdir</span> (
<span class="methodparam"><span class="type">string</span>
`$directory`</span> )

Changes PHP's current directory to `directory`.

### Parameters

`directory`  
The new current directory

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

Throws an error of level **`E_WARNING`** on failure.

### Examples

**Example \#1 <span class="function">chdir</span> example**

``` php
<?php

// current directory
echo getcwd() . "\n";

chdir('public_html');

// current directory
echo getcwd() . "\n";

?>
```

The above example will output something similar to:

    /home/vincent
    /home/vincent/public_html

### Notes

**Caution**

If the PHP interpreter has been built with ZTS (Zend Thread Safety)
enabled, any changes to the current directory made through <span
class="function">chdir</span> will be invisible to the operating system.
All built-in PHP functions will still respect the change in current
directory; but external library functions called using
<a href="/book/ffi.html" class="link">FFI</a> will not. You can tell
whether your copy of PHP was built with ZTS enabled using **php -i** or
the built-in constant **`PHP_ZTS`**.

### See Also

-   <span class="function">getcwd</span>

chroot
======

Change the root directory

### Description

<span class="type">bool</span> <span class="methodname">chroot</span> (
<span class="methodparam"><span class="type">string</span>
`$directory`</span> )

Changes the root directory of the current process to `directory`, and
changes the current working directory to "/".

This function is only available to GNU and BSD systems, and only when
using the CLI, CGI or Embed SAPI. Also, this function requires root
privileges.

### Parameters

`directory`  
The path to change the root directory to.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">chroot</span> example**

``` php
<?php
chroot("/path/to/your/chroot/");
echo getcwd();
?>
```

The above example will output:

    /

### Notes

> **Note**: <span class="simpara">This function is not implemented on
> Windows platforms.</span>

> **Note**: <span class="simpara">This function is not available in PHP
> interpreters built with ZTS (Zend Thread Safety) enabled. To check
> whether your copy of PHP was built with ZTS enabled, use **php -i** or
> test the built-in constant **`PHP_ZTS`**.</span>

closedir
========

Close directory handle

### Description

<span class="type">void</span> <span class="methodname">closedir</span>
(\[ <span class="methodparam"><span class="type">resource</span>
`$dir_handle`</span> \] )

Closes the directory stream indicated by `dir_handle`. The stream must
have previously been opened by <span class="function">opendir</span>.

### Parameters

`dir_handle`  
The directory handle <span class="type">resource</span> previously
opened with <span class="function">opendir</span>. If the directory
handle is not specified, the last link opened by <span
class="function">opendir</span> is assumed.

### Examples

**Example \#1 <span class="function">closedir</span> example**

``` php
<?php
$dir = "/etc/php5/";

// Open a known directory, read directory into variable and then close
if (is_dir($dir)) {
    if ($dh = opendir($dir)) {
        $directory = readdir($dh);
        closedir($dh);
    }
}
?>
```

dir
===

Return an instance of the Directory class

### Description

<span class="type">Directory</span> <span class="methodname">dir</span>
( <span class="methodparam"><span class="type">string</span>
`$directory`</span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \] )

A pseudo-object oriented mechanism for reading a directory. The given
`directory` is opened.

### Parameters

`directory`  
Directory to open

`context`  
> **Note**: <span class="simpara">Context support was added with PHP
> 5.0.0. For a description of *contexts*, refer to
> <a href="/book/stream.html" class="xref">Streams</a>.</span>

### Return Values

Returns an instance of <span class="classname">Directory</span>, or
**`NULL`** with wrong parameters, or **`FALSE`** in case of another
error.

### Examples

**Example \#1 <span class="function">dir</span> example**

Please note the fashion in which <span
class="function">Directory::read</span>'s return value is checked in the
example below. We are explicitly testing whether the return value is
identical to (equal to and of the same type as - see
<a href="/language/operators/comparison.html" class="link">Comparison Operators</a>
for more information) **`FALSE`** since otherwise, any directory entry
whose name evaluates to **`FALSE`** will stop the loop.

``` php
<?php
$d = dir("/etc/php5");
echo "Handle: " . $d->handle . "\n";
echo "Path: " . $d->path . "\n";
while (false !== ($entry = $d->read())) {
   echo $entry."\n";
}
$d->close();
?>
```

The above example will output something similar to:

    Handle: Resource id #2
    Path: /etc/php5
    .
    ..
    apache
    cgi
    cli

### Notes

> **Note**:
>
> The order in which directory entries are returned by the read method
> is system-dependent.

getcwd
======

Gets the current working directory

### Description

<span class="type">string</span> <span class="methodname">getcwd</span>
( <span class="methodparam">void</span> )

Gets the current working directory.

### Return Values

Returns the current working directory on success, or **`FALSE`** on
failure.

On some Unix variants, <span class="function">getcwd</span> will return
**`FALSE`** if any one of the parent directories does not have the
readable or search mode set, even if the current directory does. See
<span class="function">chmod</span> for more information on modes and
permissions.

**Caution**

If the PHP interpreter has been built with ZTS (Zend Thread Safety)
enabled, the current working directory returned by <span
class="function">getcwd</span> may be different from that returned by
operating system interfaces. External libraries (invoked through
<a href="/book/ffi.html" class="link">FFI</a>) which depend on the
current working directory will be affected.

### Examples

**Example \#1 <span class="function">getcwd</span> example**

``` php
<?php

// current directory
echo getcwd() . "\n";

chdir('cvs');

// current directory
echo getcwd() . "\n";

?>
```

The above example will output something similar to:

    /home/didou
    /home/didou/cvs

### See Also

-   <span class="function">chdir</span>
-   <span class="function">chmod</span>

opendir
=======

Open directory handle

### Description

<span class="type">resource</span> <span
class="methodname">opendir</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`</span>
\] )

Opens up a directory handle to be used in subsequent <span
class="function">closedir</span>, <span class="function">readdir</span>,
and <span class="function">rewinddir</span> calls.

### Parameters

`path`  
The directory path that is to be opened

`context`  
For a description of the `context` parameter, refer to
<a href="/ref/stream.html" class="link">the streams section</a> of the
manual.

### Return Values

Returns a directory handle <span class="type">resource</span> on
success, or **`FALSE`** on failure

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

This may happen if `path` is not a valid directory, the directory can
not be opened due to permission restrictions, or due to filesystem
errors.

### Examples

**Example \#1 <span class="function">opendir</span> example**

``` php
<?php
$dir = "/etc/php5/";

// Open a known directory, and proceed to read its contents
if (is_dir($dir)) {
    if ($dh = opendir($dir)) {
        while (($file = readdir($dh)) !== false) {
            echo "filename: $file : filetype: " . filetype($dir . $file) . "\n";
        }
        closedir($dh);
    }
}
?>
```

The above example will output something similar to:

    filename: . : filetype: dir
    filename: .. : filetype: dir
    filename: apache : filetype: dir
    filename: cgi : filetype: dir
    filename: cli : filetype: dir

### See Also

-   <span class="function">is\_dir</span>
-   <span class="function">readdir</span>
-   <span class="function">dir</span>

readdir
=======

Read entry from directory handle

### Description

<span class="type">string</span> <span class="methodname">readdir</span>
(\[ <span class="methodparam"><span class="type">resource</span>
`$dir_handle`</span> \] )

Returns the name of the next entry in the directory. The entries are
returned in the order in which they are stored by the filesystem.

### Parameters

`dir_handle`  
The directory handle <span class="type">resource</span> previously
opened with <span class="function">opendir</span>. If the directory
handle is not specified, the last link opened by <span
class="function">opendir</span> is assumed.

### Return Values

Returns the entry name on success or **`FALSE`** on failure.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 List all entries in a directory**

Please note the fashion in which <span class="function">readdir</span>'s
return value is checked in the examples below. We are explicitly testing
whether the return value is identical to (equal to and of the same type
as--see
<a href="/language/operators/comparison.html" class="link">Comparison Operators</a>
for more information) **`FALSE`** since otherwise, any directory entry
whose name evaluates to **`FALSE`** will stop the loop (e.g. a directory
named "0").

``` php
<?php

if ($handle = opendir('/path/to/files')) {
    echo "Directory handle: $handle\n";
    echo "Entries:\n";

    /* This is the correct way to loop over the directory. */
    while (false !== ($entry = readdir($handle))) {
        echo "$entry\n";
    }

    /* This is the WRONG way to loop over the directory. */
    while ($entry = readdir($handle)) {
        echo "$entry\n";
    }

    closedir($handle);
}
?>
```

**Example \#2 List all entries in the current directory and strip out
*.* and *..***

``` php
<?php
if ($handle = opendir('.')) {
    while (false !== ($entry = readdir($handle))) {
        if ($entry != "." && $entry != "..") {
            echo "$entry\n";
        }
    }
    closedir($handle);
}
?>
```

### See Also

-   <span class="function">is\_dir</span>
-   <span class="function">glob</span>
-   <span class="function">opendir</span>
-   <span class="function">scandir</span>

rewinddir
=========

Rewind directory handle

### Description

<span class="type">void</span> <span class="methodname">rewinddir</span>
(\[ <span class="methodparam"><span class="type">resource</span>
`$dir_handle`</span> \] )

Resets the directory stream indicated by `dir_handle` to the beginning
of the directory.

### Parameters

`dir_handle`  
The directory handle <span class="type">resource</span> previously
opened with <span class="function">opendir</span>. If the directory
handle is not specified, the last link opened by <span
class="function">opendir</span> is assumed.

### Return Values

Returns **`NULL`** on success or **`FALSE`** on failure.

scandir
=======

List files and directories inside the specified path

### Description

<span class="type">array</span> <span class="methodname">scandir</span>
( <span class="methodparam"><span class="type">string</span>
`$directory`</span> \[, <span class="methodparam"><span
class="type">int</span> `$sorting_order`<span class="initializer"> =
SCANDIR\_SORT\_ASCENDING</span></span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`</span>
\]\] )

Returns an <span class="type">array</span> of files and directories from
the `directory`.

### Parameters

`directory`  
The directory that will be scanned.

`sorting_order`  
By default, the sorted order is alphabetical in ascending order. If the
optional `sorting_order` is set to **`SCANDIR_SORT_DESCENDING`**, then
the sort order is alphabetical in descending order. If it is set to
**`SCANDIR_SORT_NONE`** then the result is unsorted.

`context`  
For a description of the `context` parameter, refer to
<a href="/ref/stream.html" class="link">the streams section</a> of the
manual.

### Return Values

Returns an <span class="type">array</span> of filenames on success, or
**`FALSE`** on failure. If `directory` is not a directory, then boolean
**`FALSE`** is returned, and an error of level **`E_WARNING`** is
generated.

### Examples

**Example \#1 A simple <span class="function">scandir</span> example**

``` php
<?php
$dir    = '/tmp';
$files1 = scandir($dir);
$files2 = scandir($dir, 1);

print_r($files1);
print_r($files2);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => .
        [1] => ..
        [2] => bar.php
        [3] => foo.txt
        [4] => somedir
    )
    Array
    (
        [0] => somedir
        [1] => foo.txt
        [2] => bar.php
        [3] => ..
        [4] => .
    )

### Notes

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

### See Also

-   <span class="function">opendir</span>
-   <span class="function">readdir</span>
-   <span class="function">glob</span>
-   <span class="function">is\_dir</span>
-   <span class="function">sort</span>

**Table of Contents**

-   [chdir](/ref/dir.html#chdir) — Change directory
-   [chroot](/ref/dir.html#chroot) — Change the root directory
-   [closedir](/ref/dir.html#closedir) — Close directory handle
-   [dir](/ref/dir.html#dir) — Return an instance of the Directory class
-   [getcwd](/ref/dir.html#getcwd) — Gets the current working directory
-   [opendir](/ref/dir.html#opendir) — Open directory handle
-   [readdir](/ref/dir.html#readdir) — Read entry from directory handle
-   [rewinddir](/ref/dir.html#rewinddir) — Rewind directory handle
-   [scandir](/ref/dir.html#scandir) — List files and directories inside
    the specified path

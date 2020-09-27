For related functions, see also the
<a href="/ref/dir.html" class="link">Directory</a> and
<a href="/ref/exec.html" class="link">Program Execution</a> sections.

For a list and explanation of the various URL wrappers that can be used
as remote files, see also
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>.

basename
========

Returns trailing name component of path

### Description

<span class="type">string</span> <span
class="methodname">basename</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">string</span> `$suffix`</span> \]
)

Given a string containing the path to a file or directory, this function
will return the trailing name component.

> **Note**:
>
> <span class="function">basename</span> operates naively on the input
> string, and is not aware of the actual filesystem, or path components
> such as "*..*".

**Caution**

<span class="function">basename</span> is locale aware, so for it to see
the correct basename with multibyte character paths, the matching locale
must be set using the <span class="function">setlocale</span> function.

### Parameters

`path`  
A path.

On Windows, both slash (*/*) and backslash (*\\*) are used as directory
separator character. In other environments, it is the forward slash
(*/*).

`suffix`  
If the name component ends in `suffix` this will also be cut off.

### Return Values

Returns the base name of the given `path`.

### Examples

**Example \#1 <span class="function">basename</span> example**

``` php
<?php
echo "1) ".basename("/etc/sudoers.d", ".d").PHP_EOL;
echo "2) ".basename("/etc/sudoers.d").PHP_EOL;
echo "3) ".basename("/etc/passwd").PHP_EOL;
echo "4) ".basename("/etc/").PHP_EOL;
echo "5) ".basename(".").PHP_EOL;
echo "6) ".basename("/");
?>
```

The above example will output:

    1) sudoers
    2) sudoers.d
    3) passwd
    4) etc
    5) .
    6) 

### See Also

-   <span class="function">dirname</span>
-   <span class="function">pathinfo</span>

chgrp
=====

Changes file group

### Description

<span class="type">bool</span> <span class="methodname">chgrp</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">mixed</span> `$group`</span> )

Attempts to change the group of the file `filename` to `group`.

Only the superuser may change the group of a file arbitrarily; other
users may change the group of a file to any group of which that user is
a member.

### Parameters

`filename`  
Path to the file.

`group`  
A group name or number.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Changing a file's group**

``` php
<?php
$filename = 'shared_file.txt';
$format = "%s's Group ID @ %s: %d\n";
printf($format, $filename, date('r'), filegroup($filename));
chgrp($filename, 8);
clearstatcache(); // do not cache filegroup() results
printf($format, $filename, date('r'), filegroup($filename));
?>
```

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the files or directories being operated
> upon have the same UID (owner) as the script that is being
> executed.</span>

> **Note**: <span class="simpara"> On Windows, this function fails
> silently when applied on a regular file. </span>

### See Also

-   <span class="function">chown</span>
-   <span class="function">chmod</span>

chmod
=====

Changes file mode

### Description

<span class="type">bool</span> <span class="methodname">chmod</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">int</span> `$mode`</span> )

Attempts to change the mode of the specified file to that given in
`mode`.

### Parameters

`filename`  
Path to the file.

`mode`  
Note that `mode` is not automatically assumed to be an octal value, so
to ensure the expected operation, you need to prefix `mode` with a zero
(0). Strings such as "g+w" will not work properly.

``` php
<?php
chmod("/somedir/somefile", 755);   // decimal; probably incorrect
chmod("/somedir/somefile", "u+rwx,go+rx"); // string; incorrect
chmod("/somedir/somefile", 0755);  // octal; correct value of mode
?>
```

The `mode` parameter consists of three octal number components
specifying access restrictions for the owner, the user group in which
the owner is in, and to everybody else in this order. One component can
be computed by adding up the needed permissions for that target user
base. Number 1 means that you grant execute rights, number 2 means that
you make the file writeable, number 4 means that you make the file
readable. Add up these numbers to specify needed rights. You can also
read more about modes on Unix systems with '**man 1 chmod**' and '**man
2 chmod**'.

``` php
<?php
// Read and write for owner, nothing for everybody else
chmod("/somedir/somefile", 0600);

// Read and write for owner, read for everybody else
chmod("/somedir/somefile", 0644);

// Everything for owner, read and execute for others
chmod("/somedir/somefile", 0755);

// Everything for owner, read and execute for owner's group
chmod("/somedir/somefile", 0750);
?>
```

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> The current user is the user under which PHP runs. It is probably not
> the same user you use for normal shell or FTP access. The mode can be
> changed only by user who owns the file on most systems.

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

> **Note**:
>
> When
> <a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>
> is enabled, PHP checks whether the files or directories you are about
> to operate on have the same UID (owner) as the script that is being
> executed. In addition, you cannot set the SUID, SGID and sticky bits.

### See Also

-   <span class="function">chown</span>
-   <span class="function">chgrp</span>
-   <span class="function">fileperms</span>
-   <span class="function">stat</span>

chown
=====

Changes file owner

### Description

<span class="type">bool</span> <span class="methodname">chown</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">mixed</span> `$user`</span> )

Attempts to change the owner of the file `filename` to user `user`. Only
the superuser may change the owner of a file.

### Parameters

`filename`  
Path to the file.

`user`  
A user name or number.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Simple <span class="function">chown</span> usage**

``` php
<?php

// File name and username to use
$file_name= "foo.php";
$path = "/home/sites/php.net/public_html/sandbox/" . $file_name ;
$user_name = "root";

// Set the user
chown($path, $user_name);

// Check the result
$stat = stat($path);
print_r(posix_getpwuid($stat['uid']));

?>
```

The above example will output something similar to:

    Array
    (
        [name] => root
        [passwd] => x
        [uid] => 0
        [gid] => 0
        [gecos] => root
        [dir] => /root
        [shell] => /bin/bash
    )

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the files or directories being operated
> upon have the same UID (owner) as the script that is being
> executed.</span>

> **Note**: <span class="simpara"> On Windows, this function fails
> silently when applied on a regular file. </span>

### See Also

-   <span class="function">chmod</span>
-   <span class="function">chgrp</span>

clearstatcache
==============

Clears file status cache

### Description

<span class="type">void</span> <span
class="methodname">clearstatcache</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$clear_realpath_cache`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$filename`</span> \]\] )

When you use <span class="function">stat</span>, <span
class="function">lstat</span>, or any of the other functions listed in
the affected functions list (below), PHP caches the information those
functions return in order to provide faster performance. However, in
certain cases, you may want to clear the cached information. For
instance, if the same file is being checked multiple times within a
single script, and that file is in danger of being removed or changed
during that script's operation, you may elect to clear the status cache.
In these cases, you can use the <span
class="function">clearstatcache</span> function to clear the information
that PHP caches about a file.

You should also note that PHP doesn't cache information about
non-existent files. So, if you call <span
class="function">file\_exists</span> on a file that doesn't exist, it
will return **`FALSE`** until you create the file. If you create the
file, it will return **`TRUE`** even if you then delete the file.
However <span class="function">unlink</span> clears the cache
automatically.

> **Note**:
>
> This function caches information about specific filenames, so you only
> need to call <span class="function">clearstatcache</span> if you are
> performing multiple operations on the same filename and require the
> information about that particular file to not be cached.

Affected functions include <span class="function">stat</span>, <span
class="function">lstat</span>, <span
class="function">file\_exists</span>, <span
class="function">is\_writable</span>, <span
class="function">is\_readable</span>, <span
class="function">is\_executable</span>, <span
class="function">is\_file</span>, <span class="function">is\_dir</span>,
<span class="function">is\_link</span>, <span
class="function">filectime</span>, <span
class="function">fileatime</span>, <span
class="function">filemtime</span>, <span
class="function">fileinode</span>, <span
class="function">filegroup</span>, <span
class="function">fileowner</span>, <span
class="function">filesize</span>, <span
class="function">filetype</span>, and <span
class="function">fileperms</span>.

### Parameters

`clear_realpath_cache`  
Whether to clear the realpath cache or not.

`filename`  
Clear the realpath and the stat cache for a specific filename only; only
used if `clear_realpath_cache` is **`TRUE`**.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">clearstatcache</span> example**

``` php
<?php
$file = 'output_log.txt';

function get_owner($file)
{
    $stat = stat($file);
    $user = posix_getpwuid($stat['uid']);
    return $user['name'];
}

$format = "UID @ %s: %s\n";

printf($format, date('r'), get_owner($file));

chown($file, 'ross');
printf($format, date('r'), get_owner($file));

clearstatcache();
printf($format, date('r'), get_owner($file));
?>
```

The above example will output something similar to:

    UID @ Sun, 12 Oct 2008 20:48:28 +0100: root
    UID @ Sun, 12 Oct 2008 20:48:28 +0100: root
    UID @ Sun, 12 Oct 2008 20:48:28 +0100: ross

copy
====

Copies file

### Description

<span class="type">bool</span> <span class="methodname">copy</span> (
<span class="methodparam"><span class="type">string</span>
`$source`</span> , <span class="methodparam"><span
class="type">string</span> `$dest`</span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`</span>
\] )

Makes a copy of the file `source` to `dest`.

If you wish to move a file, use the <span class="function">rename</span>
function.

### Parameters

`source`  
Path to the source file.

`dest`  
The destination path. If `dest` is a URL, the copy operation may fail if
the wrapper does not support overwriting of existing files.

**Warning**
If the destination file already exists, it will be overwritten.

`context`  
A valid context resource created with <span
class="function">stream\_context\_create</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">copy</span> example**

``` php
<?php
$file = 'example.txt';
$newfile = 'example.txt.bak';

if (!copy($file, $newfile)) {
    echo "failed to copy $file...\n";
}
?>
```

### See Also

-   <span class="function">move\_uploaded\_file</span>
-   <span class="function">rename</span>
-   The section of the manual about
    <a href="/features/file-upload.html" class="link">handling file uploads</a>

delete
======

See <span class="function">unlink</span> or <span
class="function">unset</span>

### Description

There is no delete keyword or function in the PHP language. If you
arrived at this page seeking to delete a file, try <span
class="function">unlink</span>. To delete a variable from the local
scope, check out <span class="function">unset</span>.

### See Also

-   <span class="function">unlink</span>
-   <span class="function">unset</span>

dirname
=======

Returns a parent directory's path

### Description

<span class="type">string</span> <span class="methodname">dirname</span>
( <span class="methodparam"><span class="type">string</span>
`$path`</span> \[, <span class="methodparam"><span
class="type">int</span> `$levels`<span class="initializer"> =
1</span></span> \] )

Given a string containing the path of a file or directory, this function
will return the parent directory's path that is `levels` up from the
current directory.

> **Note**:
>
> <span class="function">dirname</span> operates naively on the input
> string, and is not aware of the actual filesystem, or path components
> such as "*..*".

**Caution**

<span class="function">dirname</span> is locale aware, so for it to see
the correct directory name with multibyte character paths, the matching
locale must be set using the <span class="function">setlocale</span>
function.

### Parameters

`path`  
A path.

On Windows, both slash (*/*) and backslash (*\\*) are used as directory
separator character. In other environments, it is the forward slash
(*/*).

`levels`  
The number of parent directories to go up.

This must be an integer greater than 0.

### Return Values

Returns the path of a parent directory. If there are no slashes in
`path`, a dot ('*.*') is returned, indicating the current directory.
Otherwise, the returned string is `path` with any trailing */component*
removed.

### Changelog

| Version | Description                            |
|---------|----------------------------------------|
| 7.0.0   | Added the optional `levels` parameter. |

### Examples

**Example \#1 <span class="function">dirname</span> example**

``` php
<?php
echo dirname("/etc/passwd") . PHP_EOL;
echo dirname("/etc/") . PHP_EOL;
echo dirname(".") . PHP_EOL;
echo dirname("C:\\") . PHP_EOL;
echo dirname("/usr/local/lib", 2);
```

The above example will output something similar to:

    /etc
    / (or \ on Windows)
    .
    C:\
    /usr

### See Also

-   <span class="function">basename</span>
-   <span class="function">pathinfo</span>
-   <span class="function">realpath</span>

disk\_free\_space
=================

Returns available space on filesystem or disk partition

### Description

<span class="type">float</span> <span
class="methodname">disk\_free\_space</span> ( <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

Given a string containing a directory, this function will return the
number of bytes available on the corresponding filesystem or disk
partition.

### Parameters

`directory`  
A directory of the filesystem or disk partition.

> **Note**:
>
> Given a file name instead of a directory, the behaviour of the
> function is unspecified and may differ between operating systems and
> PHP versions.

### Return Values

Returns the number of available bytes as a float or **`FALSE`** on
failure.

### Examples

**Example \#1 <span class="function">disk\_free\_space</span> example**

``` php
<?php
// $df contains the number of bytes available on "/"
$df = disk_free_space("/");

// On Windows:
$df_c = disk_free_space("C:");
$df_d = disk_free_space("D:");
?>
```

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

### See Also

-   <span class="function">disk\_total\_space</span>

disk\_total\_space
==================

Returns the total size of a filesystem or disk partition

### Description

<span class="type">float</span> <span
class="methodname">disk\_total\_space</span> ( <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

Given a string containing a directory, this function will return the
total number of bytes on the corresponding filesystem or disk partition.

### Parameters

`directory`  
A directory of the filesystem or disk partition.

### Return Values

Returns the total number of bytes as a float or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">disk\_total\_space</span> example**

``` php
<?php
// $ds contains the total number of bytes available on "/"
$ds = disk_total_space("/");

// On Windows:
$ds = disk_total_space("C:");
$ds = disk_total_space("D:");
?>
```

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

### See Also

-   <span class="function">disk\_free\_space</span>

diskfreespace
=============

Alias of <span class="function">disk\_free\_space</span>

### Description

This function is an alias of: <span
class="function">disk\_free\_space</span>.

fclose
======

Closes an open file pointer

### Description

<span class="type">bool</span> <span class="methodname">fclose</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

The file pointed to by `handle` is closed.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">fsockopen</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 A simple <span class="function">fclose</span> example**

``` php
<?php

$handle = fopen('somefile.txt', 'r');

fclose($handle);

?>
```

### See Also

-   <span class="function">fopen</span>
-   <span class="function">fsockopen</span>

feof
====

Tests for end-of-file on a file pointer

### Description

<span class="type">bool</span> <span class="methodname">feof</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

Tests for end-of-file on a file pointer.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">fsockopen</span> (and not yet closed by <span
class="function">fclose</span>).

### Return Values

Returns **`TRUE`** if the file pointer is at EOF or an error occurs
(including socket timeout); otherwise returns **`FALSE`**.

### Notes

**Warning**

If a connection opened by <span class="function">fsockopen</span> wasn't
closed by the server, <span class="function">feof</span> will hang. To
workaround this, see below example:

**Example \#1 Handling timeouts with <span
class="function">feof</span>**

``` php
<?php
function safe_feof($fp, &$start = NULL) {
 $start = microtime(true);

 return feof($fp);
}

/* Assuming $fp is previously opened by fsockopen() */

$start = NULL;
$timeout = ini_get('default_socket_timeout');

while(!safe_feof($fp, $start) && (microtime(true) - $start) < $timeout)
{
 /* Handle */
}
?>
```

**Warning**

If the passed file pointer is not valid you may get an infinite loop,
because <span class="function">feof</span> fails to return **`TRUE`**.

**Example \#2 <span class="function">feof</span> example with an invalid
file pointer**

``` php
<?php
// if file can not be read or doesn't exist fopen function returns FALSE
$file = @fopen("no_such_file", "r");

// FALSE from fopen will issue warning and result in infinite loop here
while (!feof($file)) {
}

fclose($file);
?>
```

fflush
======

Flushes the output to a file

### Description

<span class="type">bool</span> <span class="methodname">fflush</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

This function forces a write of all buffered output to the resource
pointed to by the file `handle`.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">fsockopen</span> (and not yet closed by <span
class="function">fclose</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 File write example using <span
class="function">fflush</span>**

``` php
<?php
$filename = 'bar.txt';

$file = fopen($filename, 'r+');
rewind($file);
fwrite($file, 'Foo');
fflush($file);
ftruncate($file, ftell($file));
fclose($file);
?>
```

### See Also

-   <span class="function">clearstatcache</span>
-   <span class="function">fwrite</span>

fgetc
=====

Gets character from file pointer

### Description

<span class="type">string</span> <span class="methodname">fgetc</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

Gets a character from the given file pointer.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">fsockopen</span> (and not yet closed by <span
class="function">fclose</span>).

### Return Values

Returns a string containing a single character read from the file
pointed to by `handle`. Returns **`FALSE`** on EOF.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 A <span class="function">fgetc</span> example**

``` php
<?php
$fp = fopen('somefile.txt', 'r');
if (!$fp) {
    echo 'Could not open file somefile.txt';
}
while (false !== ($char = fgetc($fp))) {
    echo "$char\n";
}
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">fread</span>
-   <span class="function">fopen</span>
-   <span class="function">popen</span>
-   <span class="function">fsockopen</span>
-   <span class="function">fgets</span>

fgetcsv
=======

Gets line from file pointer and parse for CSV fields

### Description

<span class="type">array</span> <span class="methodname">fgetcsv</span>
( <span class="methodparam"><span class="type">resource</span>
`$handle`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$delimiter`<span class="initializer"> =
","</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$enclosure`<span class="initializer"> =
'"'</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$escape`<span class="initializer"> =
"\\\\"</span></span> \]\]\]\] )

Similar to <span class="function">fgets</span> except that <span
class="function">fgetcsv</span> parses the line it reads for fields in
CSV format and returns an array containing the fields read.

> **Note**:
>
> The locale settings are taken into account by this function. If
> *LC\_CTYPE* is e.g. *en\_US.UTF-8*, files in one-byte encodings may be
> read wrongly by this function.

### Parameters

`handle`  
A valid file pointer to a file successfully opened by <span
class="function">fopen</span>, <span class="function">popen</span>, or
<span class="function">fsockopen</span>.

`length`  
Must be greater than the longest line (in characters) to be found in the
CSV file (allowing for trailing line-end characters). Otherwise the line
is split in chunks of `length` characters, unless the split would occur
inside an enclosure.

Omitting this parameter (or setting it to 0 in PHP 5.1.0 and later) the
maximum line length is not limited, which is slightly slower.

`delimiter`  
The optional `delimiter` parameter sets the field delimiter (one
character only).

`enclosure`  
The optional `enclosure` parameter sets the field enclosure character
(one character only).

`escape`  
The optional `escape` parameter sets the escape character (at most one
character). An empty string (*""*) disables the proprietary escape
mechanism.

> **Note**: <span class="simpara"> Usually an `enclosure` character is
> escaped inside a field by doubling it; however, the `escape` character
> can be used as an alternative. So for the default parameter values
> *""* and *\\"* have the same meaning. Other than allowing to escape
> the `enclosure` character the `escape` character has no special
> meaning; it isn't even meant to escape itself. </span>

### Return Values

Returns an indexed array containing the fields read.

> **Note**:
>
> A blank line in a CSV file will be returned as an array comprising a
> single <span class="type">null</span> field, and will not be treated
> as an error.

> **Note**: <span class="simpara">If PHP is not properly recognizing the
> line endings when reading files either on or created by a Macintosh
> computer, enabling the
> <a href="/filesystem/setup.html#" class="link">auto_detect_line_endings</a>
> run-time configuration option may help resolve the problem.</span>

<span class="function">fgetcsv</span> returns **`NULL`** if an invalid
`handle` is supplied or **`FALSE`** on other errors, including end of
file.

### Changelog

| Version | Description                                                                                          |
|---------|------------------------------------------------------------------------------------------------------|
| 7.4.0   | The `escape` parameter now also accepts an empty string to disable the proprietary escape mechanism. |

### Examples

**Example \#1 Read and print the entire contents of a CSV file**

``` php
<?php
$row = 1;
if (($handle = fopen("test.csv", "r")) !== FALSE) {
    while (($data = fgetcsv($handle, 1000, ",")) !== FALSE) {
        $num = count($data);
        echo "<p> $num fields in line $row: <br /></p>\n";
        $row++;
        for ($c=0; $c < $num; $c++) {
            echo $data[$c] . "<br />\n";
        }
    }
    fclose($handle);
}
?>
```

### See Also

-   <span class="function">str\_getcsv</span>
-   <span class="function">explode</span>
-   <span class="function">file</span>
-   <span class="function">pack</span>
-   <span class="function">fputcsv</span>

fgets
=====

Gets line from file pointer

### Description

<span class="type">string</span> <span class="methodname">fgets</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \] )

Gets a line from file pointer.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">fsockopen</span> (and not yet closed by <span
class="function">fclose</span>).

`length`  
Reading ends when `length` - 1 bytes have been read, or a newline (which
is included in the return value), or an EOF (whichever comes first). If
no length is specified, it will keep reading from the stream until it
reaches the end of the line.

### Return Values

Returns a string of up to `length` - 1 bytes read from the file pointed
to by `handle`. If there is no more data to read in the file pointer,
then **`FALSE`** is returned.

If an error occurs, **`FALSE`** is returned.

### Examples

**Example \#1 Reading a file line by line**

``` php
<?php
$handle = @fopen("/tmp/inputfile.txt", "r");
if ($handle) {
    while (($buffer = fgets($handle, 4096)) !== false) {
        echo $buffer;
    }
    if (!feof($handle)) {
        echo "Error: unexpected fgets() fail\n";
    }
    fclose($handle);
}
?>
```

### Notes

> **Note**: <span class="simpara">If PHP is not properly recognizing the
> line endings when reading files either on or created by a Macintosh
> computer, enabling the
> <a href="/filesystem/setup.html#" class="link">auto_detect_line_endings</a>
> run-time configuration option may help resolve the problem.</span>

> **Note**:
>
> People used to the 'C' semantics of <span
> class="function">fgets</span> should note the difference in how *EOF*
> is returned.

### See Also

-   <span class="function">fgetss</span>
-   <span class="function">fread</span>
-   <span class="function">fgetc</span>
-   <span class="function">stream\_get\_line</span>
-   <span class="function">fopen</span>
-   <span class="function">popen</span>
-   <span class="function">fsockopen</span>
-   <span class="function">stream\_set\_timeout</span>

fgetss
======

Gets line from file pointer and strip HTML tags

**Warning**

This function has been *DEPRECATED* as of PHP 7.3.0. Relying on this
function is highly discouraged.

### Description

<span class="type">string</span> <span class="methodname">fgetss</span>
( <span class="methodparam"><span class="type">resource</span>
`$handle`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$allowable_tags`</span> \]\] )

Identical to <span class="function">fgets</span>, except that <span
class="function">fgetss</span> attempts to strip any NUL bytes, HTML and
PHP tags from the text it reads. The function retains the parsing state
from call to call, and as such is not equivalent to calling <span
class="function">strip\_tags</span> on the return value of <span
class="function">fgets</span>.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">fsockopen</span> (and not yet closed by <span
class="function">fclose</span>).

`length`  
Length of the data to be retrieved.

`allowable_tags`  
You can use the optional third parameter to specify tags which should
not be stripped. See <span class="function">strip\_tags</span> for
details regarding `allowable_tags`.

### Return Values

Returns a string of up to `length` - 1 bytes read from the file pointed
to by `handle`, with all HTML and PHP code stripped.

If an error occurs, returns **`FALSE`**.

### Examples

**Example \#1 Reading a PHP file line-by-line**

``` php
<?php
$str = <<<EOD
<html><body>
 <p>Welcome! Today is the <?php echo(date('jS')); ?> of <?= date('F'); ?>.</p>
</body></html>
Text outside of the HTML block.
EOD;
file_put_contents('sample.php', $str);

$handle = @fopen("sample.php", "r");
if ($handle) {
    while (!feof($handle)) {
        $buffer = fgetss($handle, 4096);
        echo $buffer;
    }
    fclose($handle);
}
?>
```

The above example will output something similar to:

     Welcome! Today is the  of .

    Text outside of the HTML block.

### Notes

> **Note**: <span class="simpara">If PHP is not properly recognizing the
> line endings when reading files either on or created by a Macintosh
> computer, enabling the
> <a href="/filesystem/setup.html#" class="link">auto_detect_line_endings</a>
> run-time configuration option may help resolve the problem.</span>

### See Also

-   <span class="function">fgets</span>
-   <span class="function">fopen</span>
-   <span class="function">popen</span>
-   <span class="function">fsockopen</span>
-   <span class="function">strip\_tags</span>
-   <span class="methodname">SplFileObject::fgetss</span>
-   The
    <a href="/filters/string.html#filters.string.strip_tags" class="link">string.strip_tags</a>
    filter

file\_exists
============

Checks whether a file or directory exists

### Description

<span class="type">bool</span> <span
class="methodname">file\_exists</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> )

Checks whether a file or directory exists.

### Parameters

`filename`  
Path to the file or directory.

On windows, use `//computername/share/filename` or
`\\computername\share\filename` to check files on network shares.

### Return Values

Returns **`TRUE`** if the file or directory specified by `filename`
exists; **`FALSE`** otherwise.

> **Note**:
>
> This function will return **`FALSE`** for symlinks pointing to
> non-existing files.

**Warning**

This function returns **`FALSE`** for files inaccessible due to
<a href="/features/safe-mode.html" class="link">safe mode</a>
restrictions. However these files still can be
<a href="/function/include.html" class="link">included</a> if they are
located in
<a href="/ini/sect/safe-mode.html#ini.safe-mode-include-dir" class="link">safe_mode_include_dir</a>.

> **Note**:
>
> The check is done using the real UID/GID instead of the effective one.

> **Note**: <span class="simpara"> Because PHP's integer type is signed
> and many platforms use 32bit integers, some filesystem functions may
> return unexpected results for files which are larger than 2GB. </span>

### Examples

**Example \#1 Testing whether a file exists**

``` php
<?php
$filename = '/path/to/foo.txt';

if (file_exists($filename)) {
    echo "The file $filename exists";
} else {
    echo "The file $filename does not exist";
}
?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">is\_readable</span>
-   <span class="function">is\_writable</span>
-   <span class="function">is\_file</span>
-   <span class="function">file</span>

file\_get\_contents
===================

Reads entire file into a string

### Description

<span class="type">string</span> <span
class="methodname">file\_get\_contents</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$maxlen`</span>
\]\]\]\] )

This function is similar to <span class="function">file</span>, except
that <span class="function">file\_get\_contents</span> returns the file
in a <span class="type">string</span>, starting at the specified
`offset` up to `maxlen` bytes. On failure, <span
class="function">file\_get\_contents</span> will return **`FALSE`**.

<span class="function">file\_get\_contents</span> is the preferred way
to read the contents of a file into a string. It will use memory mapping
techniques if supported by your OS to enhance performance.

> **Note**:
>
> If you're opening a URI with special characters, such as spaces, you
> need to encode the URI with <span class="function">urlencode</span>.

### Parameters

`filename`  
Name of the file to read.

`use_include_path`  
> **Note**:
>
> The **`FILE_USE_INCLUDE_PATH`** constant can be used to trigger
> <a href="/ini/core.html#ini.include-path" class="link">include path</a>
> search. This is not possible if
> <a href="/functions/arguments.html#functions.arguments.type-declaration.strict" class="link">strict typing</a>
> is enabled, since **`FILE_USE_INCLUDE_PATH`** is an <span
> class="type">int</span>. Use **`TRUE`** instead.

`context`  
A valid context resource created with <span
class="function">stream\_context\_create</span>. If you don't need to
use a custom context, you can skip this parameter by **`NULL`**.

`offset`  
The offset where the reading starts on the original stream. Negative
offsets count from the end of the stream.

Seeking (`offset`) is not supported with remote files. Attempting to
seek on non-local files may work with small offsets, but this is
unpredictable because it works on the buffered stream.

`maxlen`  
Maximum length of data read. The default is to read until end of file is
reached. Note that this parameter is applied to the stream processed by
the filters.

### Return Values

The function returns the read data or **`FALSE`** on failure.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Errors/Exceptions

An **`E_WARNING`** level error is generated if `filename` cannot be
found, `maxlength` is less than zero, or if seeking to the specified
`offset` in the stream fails.

### Examples

**Example \#1 Get and output the source of the homepage of a website**

``` php
<?php
$homepage = file_get_contents('http://www.example.com/');
echo $homepage;
?>
```

**Example \#2 Searching within the include\_path**

``` php
<?php
// If strict types are enabled i.e. declare(strict_types=1);
$file = file_get_contents('./people.txt', true);
// Otherwise
$file = file_get_contents('./people.txt', FILE_USE_INCLUDE_PATH);
?>
```

**Example \#3 Reading a section of a file**

``` php
<?php
// Read 14 characters starting from the 21st character
$section = file_get_contents('./people.txt', FALSE, NULL, 20, 14);
var_dump($section);
?>
```

The above example will output something similar to:

    string(14) "lle Bjori Ro" 

**Example \#4 Using stream contexts**

``` php
<?php
// Create a stream
$opts = array(
  'http'=>array(
    'method'=>"GET",
    'header'=>"Accept-language: en\r\n" .
              "Cookie: foo=bar\r\n"
  )
);

$context = stream_context_create($opts);

// Open the file using the HTTP headers set above
$file = file_get_contents('http://www.example.com/', false, $context);
?>
```

### Changelog

| Version | Description                                    |
|---------|------------------------------------------------|
| 7.1.0   | Support for negative `offset`s has been added. |

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

**Warning**

When using SSL, Microsoft IIS will violate the protocol by closing the
connection without sending a *close\_notify* indicator. PHP will report
this as "SSL: Fatal Protocol Error" when you reach the end of the data.
To work around this, the value of
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
should be lowered to a level that does not include warnings. PHP can
detect buggy IIS server software when you open the stream using the
*https://* wrapper and will suppress the warning. When using <span
class="function">fsockopen</span> to create an *ssl://* socket, the
developer is responsible for detecting and suppressing this warning.

### See Also

-   <span class="function">file</span>
-   <span class="function">fgets</span>
-   <span class="function">fread</span>
-   <span class="function">readfile</span>
-   <span class="function">file\_put\_contents</span>
-   <span class="function">stream\_get\_contents</span>
-   <span class="function">stream\_context\_create</span>
-   <a href="/reserved/variables/httpresponseheader.html" class="link">$http_response_header</a>

file\_put\_contents
===================

Write data to a file

### Description

<span class="type">int</span> <span
class="methodname">file\_put\_contents</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$data`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\] )

This function is identical to calling <span
class="function">fopen</span>, <span class="function">fwrite</span> and
<span class="function">fclose</span> successively to write data to a
file.

If `filename` does not exist, the file is created. Otherwise, the
existing file is overwritten, unless the **`FILE_APPEND`** flag is set.

### Parameters

`filename`  
Path to the file where to write the data.

`data`  
The data to write. Can be either a <span class="type">string</span>, an
<span class="type">array</span> or a <span class="type">stream</span>
resource.

If `data` is a <span class="type">stream</span> resource, the remaining
buffer of that stream will be copied to the specified file. This is
similar with using <span
class="function">stream\_copy\_to\_stream</span>.

You can also specify the `data` parameter as a single dimension array.
This is equivalent to *file\_put\_contents($filename, implode('',
$array))*.

`flags`  
The value of `flags` can be any combination of the following flags,
joined with the binary OR (*\|*) operator.

| Flag                        | Description                                                                                                                                                                                                                                                                                                                           |
|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`FILE_USE_INCLUDE_PATH`** | Search for `filename` in the include directory. See <a href="/ini/core.html#ini.include-path" class="link">include_path</a> for more information.                                                                                                                                                                                     |
| **`FILE_APPEND`**           | If file `filename` already exists, append the data to the file instead of overwriting it.                                                                                                                                                                                                                                             |
| **`LOCK_EX`**               | Acquire an exclusive lock on the file while proceeding to the writing. In other words, a <span class="function">flock</span> call happens between the <span class="function">fopen</span> call and the <span class="function">fwrite</span> call. This is not identical to an <span class="function">fopen</span> call with mode "x". |

`context`  
A valid context resource created with <span
class="function">stream\_context\_create</span>.

### Return Values

This function returns the number of bytes that were written to the file,
or **`FALSE`** on failure.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 Simple usage example**

``` php
<?php
$file = 'people.txt';
// Open the file to get existing content
$current = file_get_contents($file);
// Append a new person to the file
$current .= "John Smith\n";
// Write the contents back to the file
file_put_contents($file, $current);
?>
```

**Example \#2 Using flags**

``` php
<?php
$file = 'people.txt';
// The new person to add to the file
$person = "John Smith\n";
// Write the contents to the file, 
// using the FILE_APPEND flag to append the content to the end of the file
// and the LOCK_EX flag to prevent anyone else writing to the file at the same time
file_put_contents($file, $person, FILE_APPEND | LOCK_EX);
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

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

-   <span class="function">fopen</span>
-   <span class="function">fwrite</span>
-   <span class="function">file\_get\_contents</span>
-   <span class="function">stream\_context\_create</span>

file
====

Reads entire file into an array

### Description

<span class="type">array</span> <span class="methodname">file</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\] )

Reads an entire file into an array.

> **Note**:
>
> You can use <span class="function">file\_get\_contents</span> to
> return the contents of a file as a string.

### Parameters

`filename`  
Path to the file.

**Tip**
A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

`flags`  
The optional parameter `flags` can be one, or more, of the following
constants:

**`FILE_USE_INCLUDE_PATH`**  
<span class="simpara"> Search for the file in the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>.
</span>

**`FILE_IGNORE_NEW_LINES`**  
<span class="simpara"> Omit newline at the end of each array element
</span>

**`FILE_SKIP_EMPTY_LINES`**  
<span class="simpara"> Skip empty lines </span>

`context`  
A context resource created with the <span
class="function">stream\_context\_create</span> function.

> **Note**: <span class="simpara">Context support was added with PHP
> 5.0.0. For a description of *contexts*, refer to
> <a href="/book/stream.html" class="xref">Streams</a>.</span>

### Return Values

Returns the file in an array. Each element of the array corresponds to a
line in the file, with the newline still attached. Upon failure, <span
class="function">file</span> returns **`FALSE`**.

> **Note**:
>
> Each line in the resulting array will include the line ending, unless
> **`FILE_IGNORE_NEW_LINES`** is used.

> **Note**: <span class="simpara">If PHP is not properly recognizing the
> line endings when reading files either on or created by a Macintosh
> computer, enabling the
> <a href="/filesystem/setup.html#" class="link">auto_detect_line_endings</a>
> run-time configuration option may help resolve the problem.</span>

### Errors/Exceptions

Emits an **`E_WARNING`** level error if the file does not exist.

### Examples

**Example \#1 <span class="function">file</span> example**

``` php
<?php
// Get a file into an array.  In this example we'll go through HTTP to get
// the HTML source of a URL.
$lines = file('http://www.example.com/');

// Loop through our array, show HTML source as HTML source; and line numbers too.
foreach ($lines as $line_num => $line) {
    echo "Line #<b>{$line_num}</b> : " . htmlspecialchars($line) . "<br />\n";
}

// Another example, let's get a web page into a string.  See also file_get_contents().
$html = implode('', file('http://www.example.com/'));

// Using the optional flags parameter since PHP 5
$trimmed = file('somefile.txt', FILE_IGNORE_NEW_LINES | FILE_SKIP_EMPTY_LINES);
?>
```

### Notes

**Warning**

When using SSL, Microsoft IIS will violate the protocol by closing the
connection without sending a *close\_notify* indicator. PHP will report
this as "SSL: Fatal Protocol Error" when you reach the end of the data.
To work around this, the value of
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
should be lowered to a level that does not include warnings. PHP can
detect buggy IIS server software when you open the stream using the
*https://* wrapper and will suppress the warning. When using <span
class="function">fsockopen</span> to create an *ssl://* socket, the
developer is responsible for detecting and suppressing this warning.

### See Also

-   <span class="function">readfile</span>
-   <span class="function">fopen</span>
-   <span class="function">fsockopen</span>
-   <span class="function">popen</span>
-   <span class="function">file\_get\_contents</span>
-   <span class="function">include</span>
-   <span class="function">stream\_context\_create</span>

fileatime
=========

Gets last access time of file

### Description

<span class="type">int</span> <span class="methodname">fileatime</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gets the last access time of the given file.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the time the file was last accessed, or **`FALSE`** on failure.
The time is returned as a Unix timestamp.

### Examples

**Example \#1 <span class="function">fileatime</span> example**

``` php
<?php

// outputs e.g.  somefile.txt was last accessed: December 29 2002 22:16:23.

$filename = 'somefile.txt';
if (file_exists($filename)) {
    echo "$filename was last accessed: " . date("F d Y H:i:s.", fileatime($filename));
}

?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**:
>
> The atime of a file is supposed to change whenever the data blocks of
> a file are being read. This can be costly performance-wise when an
> application regularly accesses a very large number of files or
> directories.
>
> Some Unix filesystems can be mounted with atime updates disabled to
> increase the performance of such applications; USENET news spools are
> a common example. On such filesystems this function will be useless.

> **Note**:
>
> Note that time resolution may differ from one file system to another.

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">filemtime</span>
-   <span class="function">fileinode</span>
-   <span class="function">date</span>

filectime
=========

Gets inode change time of file

### Description

<span class="type">int</span> <span class="methodname">filectime</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gets the inode change time of a file.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the time the file was last changed, or **`FALSE`** on failure.
The time is returned as a Unix timestamp.

### Examples

**Example \#1 A <span class="function">filectime</span> example**

``` php
<?php

// outputs e.g.  somefile.txt was last changed: December 29 2002 22:16:23.

$filename = 'somefile.txt';
if (file_exists($filename)) {
    echo "$filename was last changed: " . date("F d Y H:i:s.", filectime($filename));
}

?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**:
>
> Note: In most Unix filesystems, a file is considered changed when its
> inode data is changed; that is, when the permissions, owner, group, or
> other metadata from the inode is updated. See also <span
> class="function">filemtime</span> (which is what you want to use when
> you want to create "Last Modified" footers on web pages) and <span
> class="function">fileatime</span>.

> **Note**:
>
> Note also that in some Unix texts the ctime of a file is referred to
> as being the creation time of the file. This is wrong. There is no
> creation time for Unix files in most Unix filesystems.

> **Note**:
>
> Note that time resolution may differ from one file system to another.

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">filemtime</span>

filegroup
=========

Gets file group

### Description

<span class="type">int</span> <span class="methodname">filegroup</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gets the file group. The group ID is returned in numerical format, use
<span class="function">posix\_getgrgid</span> to resolve it to a group
name.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the group ID of the file, or **`FALSE`** if an error occurs. The
group ID is returned in numerical format, use <span
class="function">posix\_getgrgid</span> to resolve it to a group name.
Upon failure, **`FALSE`** is returned.

### Examples

**Example \#1 Finding the group of a file**

``` php
<?php
$filename = 'index.php';
print_r(posix_getgrgid(filegroup($filename)));
?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">fileowner</span>
-   <span class="function">posix\_getgrgid</span>
-   <a href="/ini/sect/safe-mode.html#ini.safe-mode-gid" class="link">safe_mode_gid</a>

fileinode
=========

Gets file inode

### Description

<span class="type">int</span> <span class="methodname">fileinode</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gets the file inode.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the inode number of the file, or **`FALSE`** on failure.

### Examples

**Example \#1 Comparing the inode of a file with the current file**

``` php
<?php
$filename = 'index.php';
if (getmyinode() == fileinode($filename)) {
    echo 'You are checking the current file.';
}
?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">getmyinode</span>
-   <span class="function">stat</span>

filemtime
=========

Gets file modification time

### Description

<span class="type">int</span> <span class="methodname">filemtime</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

This function returns the time when the data blocks of a file were being
written to, that is, the time when the content of the file was changed.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the time the file was last modified, or **`FALSE`** on failure.
The time is returned as a Unix timestamp, which is suitable for the
<span class="function">date</span> function.

### Examples

**Example \#1 <span class="function">filemtime</span> example**

``` php
<?php
// outputs e.g.  somefile.txt was last modified: December 29 2002 22:16:23.

$filename = 'somefile.txt';
if (file_exists($filename)) {
    echo "$filename was last modified: " . date ("F d Y H:i:s.", filemtime($filename));
}
?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**:
>
> Note that time resolution may differ from one file system to another.

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">filectime</span>
-   <span class="function">stat</span>
-   <span class="function">touch</span>
-   <span class="function">getlastmod</span>

fileowner
=========

Gets file owner

### Description

<span class="type">int</span> <span class="methodname">fileowner</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gets the file owner.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the user ID of the owner of the file, or **`FALSE`** on failure.
The user ID is returned in numerical format, use <span
class="function">posix\_getpwuid</span> to resolve it to a username.

### Examples

**Example \#1 Finding the owner of a file**

``` php
<?php
$filename = 'index.php';
print_r(posix_getpwuid(fileowner($filename)));
?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">filegroup</span>
-   <span class="function">stat</span>
-   <span class="function">posix\_getpwuid</span>

fileperms
=========

Gets file permissions

### Description

<span class="type">int</span> <span class="methodname">fileperms</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gets permissions for the given file.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the file's permissions as a numeric mode. Lower bits of this
mode are the same as the permissions expected by <span
class="function">chmod</span>, however on most platforms the return
value will also include information on the type of file given as
`filename`. The examples below demonstrate how to test the return value
for specific permissions and file types on POSIX systems, including
Linux and macOS.

For local files, the specific return value is that of the *st\_mode*
member of the structure returned by the C library's <span
class="function">stat</span> function. Exactly which bits are set can
vary from platform to platform, and looking up your specific platform's
documentation is recommended if parsing the non-permission bits of the
return value is required.

### Examples

**Example \#1 Display permissions as an octal value**

``` php
<?php
echo substr(sprintf('%o', fileperms('/tmp')), -4);
echo substr(sprintf('%o', fileperms('/etc/passwd')), -4);
?>
```

The above example will output:

    1777
    0644

**Example \#2 Display full permissions**

``` php
<?php
$perms = fileperms('/etc/passwd');

switch ($perms & 0xF000) {
    case 0xC000: // socket
        $info = 's';
        break;
    case 0xA000: // symbolic link
        $info = 'l';
        break;
    case 0x8000: // regular
        $info = 'r';
        break;
    case 0x6000: // block special
        $info = 'b';
        break;
    case 0x4000: // directory
        $info = 'd';
        break;
    case 0x2000: // character special
        $info = 'c';
        break;
    case 0x1000: // FIFO pipe
        $info = 'p';
        break;
    default: // unknown
        $info = 'u';
}

// Owner
$info .= (($perms & 0x0100) ? 'r' : '-');
$info .= (($perms & 0x0080) ? 'w' : '-');
$info .= (($perms & 0x0040) ?
            (($perms & 0x0800) ? 's' : 'x' ) :
            (($perms & 0x0800) ? 'S' : '-'));

// Group
$info .= (($perms & 0x0020) ? 'r' : '-');
$info .= (($perms & 0x0010) ? 'w' : '-');
$info .= (($perms & 0x0008) ?
            (($perms & 0x0400) ? 's' : 'x' ) :
            (($perms & 0x0400) ? 'S' : '-'));

// World
$info .= (($perms & 0x0004) ? 'r' : '-');
$info .= (($perms & 0x0002) ? 'w' : '-');
$info .= (($perms & 0x0001) ?
            (($perms & 0x0200) ? 't' : 'x' ) :
            (($perms & 0x0200) ? 'T' : '-'));

echo $info;
?>
```

The above example will output:

    -rw-r--r--

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">chmod</span>
-   <span class="function">is\_readable</span>
-   <span class="function">stat</span>

filesize
========

Gets file size

### Description

<span class="type">int</span> <span class="methodname">filesize</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gets the size for the given file.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the size of the file in bytes, or **`FALSE`** (and generates an
error of level **`E_WARNING`**) in case of an error.

> **Note**: <span class="simpara"> Because PHP's integer type is signed
> and many platforms use 32bit integers, some filesystem functions may
> return unexpected results for files which are larger than 2GB. </span>

### Examples

**Example \#1 <span class="function">filesize</span> example**

``` php
<?php

// outputs e.g.  somefile.txt: 1024 bytes

$filename = 'somefile.txt';
echo $filename . ': ' . filesize($filename) . ' bytes';

?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">file\_exists</span>

filetype
========

Gets file type

### Description

<span class="type">string</span> <span
class="methodname">filetype</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> )

Returns the type of the given file.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns the type of the file. Possible values are fifo, char, dir,
block, link, file, socket and unknown.

Returns **`FALSE`** if an error occurs. <span
class="function">filetype</span> will also produce an **`E_NOTICE`**
message if the stat call fails or if the file type is unknown.

### Examples

**Example \#1 <span class="function">filetype</span> example**

``` php
<?php

echo filetype('/etc/passwd');  // file
echo filetype('/etc/');        // dir

?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">is\_dir</span>
-   <span class="function">is\_file</span>
-   <span class="function">is\_link</span>
-   <span class="function">file\_exists</span>
-   <span class="function">mime\_content\_type</span>
-   <span class="function">pathinfo</span>
-   <span class="function">stat</span>

flock
=====

Portable advisory file locking

### Description

<span class="type">bool</span> <span class="methodname">flock</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">int</span> `$operation`</span> \[, <span
class="methodparam"><span class="type">int</span> `&$wouldblock`</span>
\] )

<span class="function">flock</span> allows you to perform a simple
reader/writer model which can be used on virtually every platform
(including most Unix derivatives and even Windows).

On versions of PHP before 5.3.2, the lock is released also by <span
class="function">fclose</span> (which is also called automatically when
script finished).

PHP supports a portable way of locking complete files in an advisory way
(which means all accessing programs have to use the same way of locking
or it will not work). By default, this function will block until the
requested lock is acquired; this may be controlled with the
**`LOCK_NB`** option documented below.

### Parameters

`handle`  
A file system pointer <span class="type">resource</span> that is
typically created using <span class="function">fopen</span>.

`operation`  
`operation` is one of the following:

-   <span class="simpara"> **`LOCK_SH`** to acquire a shared lock
    (reader). </span>
-   <span class="simpara"> **`LOCK_EX`** to acquire an exclusive lock
    (writer). </span>
-   <span class="simpara"> **`LOCK_UN`** to release a lock (shared or
    exclusive). </span>

It is also possible to add **`LOCK_NB`** as a bitmask to one of the
above operations, if <span class="function">flock</span> should not
block during the locking attempt.

`wouldblock`  
The optional third argument is set to 1 if the lock would block
(EWOULDBLOCK errno condition).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">flock</span> example**

``` php
<?php

$fp = fopen("/tmp/lock.txt", "r+");

if (flock($fp, LOCK_EX)) {  // acquire an exclusive lock
    ftruncate($fp, 0);      // truncate file
    fwrite($fp, "Write something here\n");
    fflush($fp);            // flush output before releasing the lock
    flock($fp, LOCK_UN);    // release the lock
} else {
    echo "Couldn't get the lock!";
}

fclose($fp);

?>
```

**Example \#2 <span class="function">flock</span> using the
**`LOCK_NB`** option**

``` php
<?php
$fp = fopen('/tmp/lock.txt', 'r+');

/* Activate the LOCK_NB option on an LOCK_EX operation */
if(!flock($fp, LOCK_EX | LOCK_NB)) {
    echo 'Unable to obtain lock';
    exit(-1);
}

/* ... */

fclose($fp);
?>
```

### Notes

> **Note**:
>
> <span class="function">flock</span> uses mandatory locking instead of
> advisory locking on Windows. Mandatory locking is also supported on
> Linux and System V based operating systems via the usual mechanism
> supported by the fcntl() system call: that is, if the file in question
> has the setgid permission bit set and the group execution bit cleared.
> On Linux, the file system will also need to be mounted with the mand
> option for this to work.

> **Note**:
>
> Because <span class="function">flock</span> requires a file pointer,
> you may have to use a special lock file to protect access to a file
> that you intend to truncate by opening it in write mode (with a "w" or
> "w+" argument to <span class="function">fopen</span>).

> **Note**:
>
> May only be used on file pointers returned by <span
> class="function">fopen</span> for local files, or file pointers
> pointing to userspace streams that implement the <span
> class="function">streamWrapper::stream\_lock</span> method.

**Warning**

Assigning another value to `handle` argument in subsequent code will
release the lock.

**Warning**

On some operating systems <span class="function">flock</span> is
implemented at the process level. When using a multithreaded server API
you may not be able to rely on <span class="function">flock</span> to
protect files against other PHP scripts running in parallel threads of
the same server instance!

<span class="function">flock</span> is not supported on antiquated
filesystems like *FAT* and its derivates and will therefore always
return **`FALSE`** under these environments.

fnmatch
=======

Match filename against a pattern

### Description

<span class="type">bool</span> <span class="methodname">fnmatch</span> (
<span class="methodparam"><span class="type">string</span>
`$pattern`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \] )

<span class="function">fnmatch</span> checks if the passed `string`
would match the given shell wildcard `pattern`.

### Parameters

`pattern`  
The shell wildcard pattern.

`string`  
The tested string. This function is especially useful for filenames, but
may also be used on regular strings.

The average user may be used to shell patterns or at least in their
simplest form to *'?'* and *'\*'* wildcards so using <span
class="function">fnmatch</span> instead of <span
class="function">preg\_match</span> for frontend search expression input
may be way more convenient for non-programming users.

`flags`  
The value of `flags` can be any combination of the following flags,
joined with the
<a href="/language/operators/bitwise.html" class="link">binary OR (|) operator</a>.

| `Flag`             | Description                                                                      |
|--------------------|----------------------------------------------------------------------------------|
| **`FNM_NOESCAPE`** | Disable backslash escaping.                                                      |
| **`FNM_PATHNAME`** | Slash in string only matches slash in the given pattern.                         |
| **`FNM_PERIOD`**   | Leading period in string must be exactly matched by period in the given pattern. |
| **`FNM_CASEFOLD`** | Caseless match. Part of the GNU extension.                                       |

### Return Values

Returns **`TRUE`** if there is a match, **`FALSE`** otherwise.

### Examples

**Example \#1 Checking a color name against a shell wildcard pattern**

``` php
<?php
if (fnmatch("*gr[ae]y", $color)) {
  echo "some form of gray ...";
}
?>
```

### Notes

**Warning**

For now, this function is not available on non-POSIX compliant systems
except Windows.

### See Also

-   <span class="function">glob</span>
-   <span class="function">preg\_match</span>
-   <span class="function">sscanf</span>
-   <span class="function">printf</span>
-   <span class="function">sprintf</span>

fopen
=====

Opens file or URL

### Description

<span class="type">resource</span> <span class="methodname">fopen</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">string</span> `$mode`</span> \[, <span
class="methodparam"><span class="type">bool</span>
`$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\] )

<span class="function">fopen</span> binds a named resource, specified by
`filename`, to a stream.

### Parameters

`filename`  
If `filename` is of the form "scheme://...", it is assumed to be a URL
and PHP will search for a protocol handler (also known as a wrapper) for
that scheme. If no wrappers for that protocol are registered, PHP will
emit a notice to help you track potential problems in your script and
then continue as though `filename` specifies a regular file.

If PHP has decided that `filename` specifies a local file, then it will
try to open a stream on that file. The file must be accessible to PHP,
so you need to ensure that the file access permissions allow this
access. If you have enabled
<a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>
or
<a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
further restrictions may apply.

If PHP has decided that `filename` specifies a registered protocol, and
that protocol is registered as a network URL, PHP will check to make
sure that
<a href="/filesystem/setup.html#" class="link">allow_url_fopen</a> is
enabled. If it is switched off, PHP will emit a warning and the fopen
call will fail.

> **Note**:
>
> The list of supported protocols can be found in
> <a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>.
> Some protocols (also referred to as *wrappers*) support *context*
> and/or `php.ini` options. Refer to the specific page for the protocol
> in use for a list of options which can be set. (e.g. `php.ini` value
> *user\_agent* used by the *http* wrapper).

On the Windows platform, be careful to escape any backslashes used in
the path to the file, or use forward slashes.

``` php
<?php
$handle = fopen("c:\\folder\\resource.txt", "r");
?>
```

`mode`  
The `mode` parameter specifies the type of access you require to the
stream. It may be any of the following:

| `mode` | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *'r'*  | Open for reading only; place the file pointer at the beginning of the file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| *'r+'* | Open for reading and writing; place the file pointer at the beginning of the file.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| *'w'*  | Open for writing only; place the file pointer at the beginning of the file and truncate the file to zero length. If the file does not exist, attempt to create it.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| *'w+'* | Open for reading and writing; place the file pointer at the beginning of the file and truncate the file to zero length. If the file does not exist, attempt to create it.                                                                                                                                                                                                                                                                                                                                                                                                                         |
| *'a'*  | Open for writing only; place the file pointer at the end of the file. If the file does not exist, attempt to create it. In this mode, <span class="function">fseek</span> has no effect, writes are always appended.                                                                                                                                                                                                                                                                                                                                                                              |
| *'a+'* | Open for reading and writing; place the file pointer at the end of the file. If the file does not exist, attempt to create it. In this mode, <span class="function">fseek</span> only affects the reading position, writes are always appended.                                                                                                                                                                                                                                                                                                                                                   |
| *'x'*  | Create and open for writing only; place the file pointer at the beginning of the file. If the file already exists, the <span class="function">fopen</span> call will fail by returning **`FALSE`** and generating an error of level **`E_WARNING`**. If the file does not exist, attempt to create it. This is equivalent to specifying *O\_EXCL\|O\_CREAT* flags for the underlying *open(2)* system call.                                                                                                                                                                                       |
| *'x+'* | Create and open for reading and writing; otherwise it has the same behavior as *'x'*.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| *'c'*  | Open the file for writing only. If the file does not exist, it is created. If it exists, it is neither truncated (as opposed to *'w'*), nor the call to this function fails (as is the case with *'x'*). The file pointer is positioned on the beginning of the file. This may be useful if it's desired to get an advisory lock (see <span class="function">flock</span>) before attempting to modify the file, as using *'w'* could truncate the file before the lock was obtained (if truncation is desired, <span class="function">ftruncate</span> can be used after the lock is requested). |
| *'c+'* | Open the file for reading and writing; otherwise it has the same behavior as *'c'*.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| *'e'*  | Set close-on-exec flag on the opened file descriptor. Only available in PHP compiled on POSIX.1-2008 conform systems.                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |

> **Note**:
>
> Different operating system families have different line-ending
> conventions. When you write a text file and want to insert a line
> break, you need to use the correct line-ending character(s) for your
> operating system. Unix based systems use *\\n* as the line ending
> character, Windows based systems use *\\r\\n* as the line ending
> characters and Macintosh based systems (Mac OS Classic) used *\\r* as
> the line ending character.
>
> If you use the wrong line ending characters when writing your files,
> you might find that other applications that open those files will
> "look funny".
>
> Windows offers a text-mode translation flag (*'t'*) which will
> transparently translate *\\n* to *\\r\\n* when working with the file.
> In contrast, you can also use *'b'* to force binary mode, which will
> not translate your data. To use these flags, specify either *'b'* or
> *'t'* as the last character of the `mode` parameter.
>
> The default translation mode is *'b'*. You can use the *'t'* mode if
> you are working with plain-text files and you use *\\n* to delimit
> your line endings in your script, but expect your files to be readable
> with applications such as old versions of notepad. You should use the
> *'b'* in all other cases.
>
> If you specify the 't' flag when working with binary files, you may
> experience strange problems with your data, including broken image
> files and strange problems with *\\r\\n* characters.

> **Note**:
>
> For portability, it is also strongly recommended that you re-write
> code that uses or relies upon the *'t'* mode so that it uses the
> correct line endings and *'b'* mode instead.

`use_include_path`  
The optional third `use_include_path` parameter can be set to '1' or
**`TRUE`** if you want to search for the file in the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>,
too.

`context`  
> **Note**: <span class="simpara">Context support was added with PHP
> 5.0.0. For a description of *contexts*, refer to
> <a href="/book/stream.html" class="xref">Streams</a>.</span>

### Return Values

Returns a file pointer resource on success, or **`FALSE`** on failure

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Changelog

| Version       | Description                 |
|---------------|-----------------------------|
| 7.0.16, 7.1.2 | The *'e'* option was added. |

### Examples

**Example \#1 <span class="function">fopen</span> examples**

``` php
<?php
$handle = fopen("/home/rasmus/file.txt", "r");
$handle = fopen("/home/rasmus/file.gif", "wb");
$handle = fopen("http://www.example.com/", "r");
$handle = fopen("ftp://user:password@example.com/somefile.txt", "w");
?>
```

### Notes

**Warning**

When using SSL, Microsoft IIS will violate the protocol by closing the
connection without sending a *close\_notify* indicator. PHP will report
this as "SSL: Fatal Protocol Error" when you reach the end of the data.
To work around this, the value of
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
should be lowered to a level that does not include warnings. PHP can
detect buggy IIS server software when you open the stream using the
*https://* wrapper and will suppress the warning. When using <span
class="function">fsockopen</span> to create an *ssl://* socket, the
developer is responsible for detecting and suppressing this warning.

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the directory in which the script is
> operating has the same UID (owner) as the script that is being
> executed.</span>

> **Note**:
>
> If you are experiencing problems with reading and writing to files and
> you're using the server module version of PHP, remember to make sure
> that the files and directories you're using are accessible to the
> server process.

> **Note**:
>
> This function may also succeed when `filename` is a directory. If you
> are unsure whether `filename` is a file or a directory, you may need
> to use the <span class="function">is\_dir</span> function before
> calling <span class="function">fopen</span>.

### See Also

-   <a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
-   <span class="function">fclose</span>
-   <span class="function">fgets</span>
-   <span class="function">fread</span>
-   <span class="function">fwrite</span>
-   <span class="function">fsockopen</span>
-   <span class="function">file</span>
-   <span class="function">file\_exists</span>
-   <span class="function">is\_readable</span>
-   <span class="function">stream\_set\_timeout</span>
-   <span class="function">popen</span>
-   <span class="function">stream\_context\_create</span>
-   <span class="function">umask</span>
-   <span class="classname">SplFileObject</span>

fpassthru
=========

Output all remaining data on a file pointer

### Description

<span class="type">int</span> <span class="methodname">fpassthru</span>
( <span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

Reads to EOF on the given file pointer from the current position and
writes the results to the output buffer.

You may need to call <span class="function">rewind</span> to reset the
file pointer to the beginning of the file if you have already written
data to the file.

If you just want to dump the contents of a file to the output buffer,
without first modifying it or seeking to a particular offset, you may
want to use the <span class="function">readfile</span>, which saves you
the <span class="function">fopen</span> call.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">fsockopen</span> (and not yet closed by <span
class="function">fclose</span>).

### Return Values

If an error occurs, <span class="function">fpassthru</span> returns
**`FALSE`**. Otherwise, <span class="function">fpassthru</span> returns
the number of characters read from `handle` and passed through to the
output.

### Examples

**Example \#1 Using <span class="function">fpassthru</span> with binary
files**

``` php
<?php

// open the file in a binary mode
$name = './img/ok.png';
$fp = fopen($name, 'rb');

// send the right headers
header("Content-Type: image/png");
header("Content-Length: " . filesize($name));

// dump the picture and stop the script
fpassthru($fp);
exit;

?>
```

### Notes

> **Note**:
>
> When using <span class="function">fpassthru</span> on a binary file on
> Windows systems, you should make sure to open the file in binary mode
> by appending a *b* to the mode used in the call to <span
> class="function">fopen</span>.
>
> You are encouraged to use the *b* flag when dealing with binary files,
> even if your system does not require it, so that your scripts will be
> more portable.

### See Also

-   <span class="function">readfile</span>
-   <span class="function">fopen</span>
-   <span class="function">popen</span>
-   <span class="function">fsockopen</span>

fputcsv
=======

Format line as CSV and write to file pointer

### Description

<span class="type">int</span> <span class="methodname">fputcsv</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">array</span> `$fields`</span> \[, <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = '"'</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape_char`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

<span class="function">fputcsv</span> formats a line (passed as a
`fields` array) as CSV and writes it (terminated by a newline) to the
specified file `handle`.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">fsockopen</span> (and not yet closed by <span
class="function">fclose</span>).

`fields`  
An array of <span class="type">string</span>s.

`delimiter`  
The optional `delimiter` parameter sets the field delimiter (one
character only).

`enclosure`  
The optional `enclosure` parameter sets the field enclosure (one
character only).

`escape_char`  
The optional `escape_char` parameter sets the escape character (at most
one character). An empty string (*""*) disables the proprietary escape
mechanism.

> **Note**:
>
> If an `enclosure` character is contained in a field, it will be
> escaped by doubling it, unless it is immediately preceded by an
> `escape_char`.

### Return Values

Returns the length of the written string or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                               |
|---------|-----------------------------------------------------------------------------------------------------------|
| 7.4.0   | The `escape_char` parameter now also accepts an empty string to disable the proprietary escape mechanism. |
| 5.5.4   | The `escape_char` parameter was added                                                                     |

### Examples

**Example \#1 <span class="function">fputcsv</span> example**

``` php
<?php

$list = array (
    array('aaa', 'bbb', 'ccc', 'dddd'),
    array('123', '456', '789'),
    array('"aaa"', '"bbb"')
);

$fp = fopen('file.csv', 'w');

foreach ($list as $fields) {
    fputcsv($fp, $fields);
}

fclose($fp);
?>
```

The above example will write the following to *file.csv*:

    aaa,bbb,ccc,dddd
    123,456,789
    """aaa""","""bbb"""

### Notes

> **Note**: <span class="simpara">If PHP is not properly recognizing the
> line endings when reading files either on or created by a Macintosh
> computer, enabling the
> <a href="/filesystem/setup.html#" class="link">auto_detect_line_endings</a>
> run-time configuration option may help resolve the problem.</span>

### See Also

-   <span class="function">fgetcsv</span>

fputs
=====

Alias of <span class="function">fwrite</span>

### Description

This function is an alias of: <span class="function">fwrite</span>.

fread
=====

Binary-safe file read

### Description

<span class="type">string</span> <span class="methodname">fread</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">int</span> `$length`</span> )

<span class="function">fread</span> reads up to `length` bytes from the
file pointer referenced by `handle`. Reading stops as soon as one of the
following conditions is met:

-   <span class="simpara"> `length` bytes have been read </span>
-   <span class="simpara"> EOF (end of file) is reached </span>
-   <span class="simpara"> a packet becomes available or the
    <a href="/ref/network.html#socket_set_timeout" class="link">socket timeout</a>
    occurs (for network streams) </span>
-   <span class="simpara"> if the stream is read buffered and it does
    not represent a plain file, at most one read of up to a number of
    bytes equal to the chunk size (usually 8192) is made; depending on
    the previously buffered data, the size of the returned data may be
    larger than the chunk size. </span>

### Parameters

`handle`  
A file system pointer <span class="type">resource</span> that is
typically created using <span class="function">fopen</span>.

`length`  
Up to `length` number of bytes read.

### Return Values

Returns the read string or **`FALSE`** on failure.

### Examples

**Example \#1 A simple <span class="function">fread</span> example**

``` php
<?php
// get contents of a file into a string
$filename = "/usr/local/something.txt";
$handle = fopen($filename, "r");
$contents = fread($handle, filesize($filename));
fclose($handle);
?>
```

**Example \#2 Binary <span class="function">fread</span> example**

**Warning**

On systems which differentiate between binary and text files (i.e.
Windows) the file must be opened with 'b' included in <span
class="function">fopen</span> mode parameter.

``` php
<?php
$filename = "c:\\files\\somepic.gif";
$handle = fopen($filename, "rb");
$contents = fread($handle, filesize($filename));
fclose($handle);
?>
```

**Example \#3 Remote <span class="function">fread</span> examples**

**Warning**

When reading from anything that is not a regular local file, such as
streams returned when reading
<a href="/features/remote-files.html" class="link">remote files</a> or
from <span class="function">popen</span> and <span
class="function">fsockopen</span>, reading will stop after a packet is
available. This means that you should collect the data together in
chunks as shown in the examples below.

``` php
<?php
// For PHP 5 and up
$handle = fopen("http://www.example.com/", "rb");
$contents = stream_get_contents($handle);
fclose($handle);
?>
```

``` php
<?php
$handle = fopen("http://www.example.com/", "rb");
if (FALSE === $handle) {
    exit("Failed to open stream to URL");
}

$contents = '';

while (!feof($handle)) {
    $contents .= fread($handle, 8192);
}
fclose($handle);
?>
```

### Notes

> **Note**:
>
> If you just want to get the contents of a file into a string, use
> <span class="function">file\_get\_contents</span> as it has much
> better performance than the code above.

> **Note**:
>
> Note that <span class="function">fread</span> reads from the current
> position of the file pointer. Use <span class="function">ftell</span>
> to find the current position of the pointer and <span
> class="function">rewind</span> to rewind the pointer position.

### See Also

-   <span class="function">fwrite</span>
-   <span class="function">fopen</span>
-   <span class="function">fsockopen</span>
-   <span class="function">popen</span>
-   <span class="function">fgets</span>
-   <span class="function">fgetss</span>
-   <span class="function">fscanf</span>
-   <span class="function">file</span>
-   <span class="function">fpassthru</span>
-   <span class="function">ftell</span>
-   <span class="function">rewind</span>
-   <span class="function">unpack</span>

fscanf
======

Parses input from a file according to a format

### Description

<span class="type">mixed</span> <span class="methodname">fscanf</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">string</span> `$format`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `&$...`</span> \] )

The function <span class="function">fscanf</span> is similar to <span
class="function">sscanf</span>, but it takes its input from a file
associated with `handle` and interprets the input according to the
specified `format`, which is described in the documentation for <span
class="function">sprintf</span>.

Any whitespace in the format string matches any whitespace in the input
stream. This means that even a tab *\\t* in the format string can match
a single space character in the input stream.

Each call to <span class="function">fscanf</span> reads one line from
the file.

### Parameters

`handle`  
A file system pointer <span class="type">resource</span> that is
typically created using <span class="function">fopen</span>.

`format`  
The format string is composed of zero or more directives: ordinary
characters (excluding *%*) that are copied directly to the result and
*conversion specifications*, each of which results in fetching its own
parameter.

A conversion specification follows this prototype:
*%\[argnum$\]\[flags\]\[width\]\[.precision\]specifier*.

##### Argnum

An integer followed by a dollar sign *$*, to specify which number
argument to treat in the conversion.

| Flag      | Description                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------|
| *-*       | Left-justify within the given field width; Right justification is the default                          |
| *+*       | Prefix positive numbers with a plus sign *+*; Default only negative are prefixed with a negative sign. |
|  (space)  | Pads the result with spaces. This is the default.                                                      |
| *0*       | Only left-pads numbers with zeros. With *s* specifiers this can also right-pad with zeros.             |
| *'*(char) | Pads the result with the character (char).                                                             |

##### Width

An integer that says how many characters (minimum) this conversion
should result in.

##### Precision

A period *.* followed by an integer who's meaning depends on the
specifier:

-   <span class="simpara"> For *e*, *E*, *f* and *F* specifiers: this is
    the number of digits to be printed after the decimal point (by
    default, this is 6). </span>
-   <span class="simpara"> For *g* and *G* specifiers: this is the
    maximum number of significant digits to be printed. </span>
-   <span class="simpara"> For *s* specifier: it acts as a cutoff point,
    setting a maximum character limit to the string. </span>

> **Note**: <span class="simpara"> If the period is specified without an
> explicit value for precision, 0 is assumed. </span>

> **Note**: <span class="simpara"> Attempting to use a position
> specifier greater than **`PHP_INT_MAX`** will generate warnings.
> </span>

<table>
<caption><strong>Specifiers</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>%</em></td>
<td>A literal percent character. No argument is required.</td>
</tr>
<tr class="even">
<td><em>b</em></td>
<td>The argument is treated as an integer and presented as a binary number.</td>
</tr>
<tr class="odd">
<td><em>c</em></td>
<td>The argument is treated as an integer and presented as the character with that ASCII.</td>
</tr>
<tr class="even">
<td><em>d</em></td>
<td>The argument is treated as an integer and presented as a (signed) decimal number.</td>
</tr>
<tr class="odd">
<td><em>e</em></td>
<td>The argument is treated as scientific notation (e.g. 1.2e+2). The precision specifier stands for the number of digits after the decimal point since PHP 5.2.1. In earlier versions, it was taken as number of significant digits (one less).</td>
</tr>
<tr class="even">
<td><em>E</em></td>
<td>Like the <em>e</em> specifier but uses uppercase letter (e.g. 1.2E+2).</td>
</tr>
<tr class="odd">
<td><em>f</em></td>
<td>The argument is treated as a float and presented as a floating-point number (locale aware).</td>
</tr>
<tr class="even">
<td><em>F</em></td>
<td>The argument is treated as a float and presented as a floating-point number (non-locale aware). Available as of PHP 5.0.3.</td>
</tr>
<tr class="odd">
<td><em>g</em></td>
<td><p>General format.</p>
<p>Let P equal the precision if nonzero, 6 if the precision is omitted, or 1 if the precision is zero. Then, if a conversion with style E would have an exponent of X:</p>
<p>If P &gt; X ≥ −4, the conversion is with style f and precision P − (X + 1). Otherwise, the conversion is with style e and precision P − 1.</p></td>
</tr>
<tr class="even">
<td><em>G</em></td>
<td>Like the <em>g</em> specifier but uses <em>E</em> and <em>f</em>.</td>
</tr>
<tr class="odd">
<td><em>o</em></td>
<td>The argument is treated as an integer and presented as an octal number.</td>
</tr>
<tr class="even">
<td><em>s</em></td>
<td>The argument is treated and presented as a string.</td>
</tr>
<tr class="odd">
<td><em>u</em></td>
<td>The argument is treated as an integer and presented as an unsigned decimal number.</td>
</tr>
<tr class="even">
<td><em>x</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with lowercase letters).</td>
</tr>
<tr class="odd">
<td><em>X</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with uppercase letters).</td>
</tr>
</tbody>
</table>

**Warning**
The *c* type specifier ignores padding and width

**Warning**
Attempting to use a combination of the string and width specifiers with
character sets that require more than one byte per character may result
in unexpected results

Variables will be co-erced to a suitable type for the specifier:

| Type      | Specifiers                        |
|-----------|-----------------------------------|
| *string*  | *s*                               |
| *integer* | *d*, *u*, *c*, *o*, *x*, *X*, *b* |
| *double*  | *g*, *G*, *e*, *E*, *f*, *F*      |

`...`  
The optional assigned values.

### Return Values

If only two parameters were passed to this function, the values parsed
will be returned as an array. Otherwise, if optional parameters are
passed, the function will return the number of assigned values. The
optional parameters must be passed by reference.

### Examples

**Example \#1 <span class="function">fscanf</span> Example**

``` php
<?php
$handle = fopen("users.txt", "r");
while ($userinfo = fscanf($handle, "%s\t%s\t%s\n")) {
    list ($name, $profession, $countrycode) = $userinfo;
    //... do something with the values
}
fclose($handle);
?>
```

**Example \#2 Contents of users.txt**

``` txt
javier  argonaut        pe
hiroshi sculptor        jp
robert  slacker us
luigi   florist it
```

### See Also

-   <span class="function">fread</span>
-   <span class="function">fgets</span>
-   <span class="function">fgetss</span>
-   <span class="function">sscanf</span>
-   <span class="function">printf</span>
-   <span class="function">sprintf</span>

fseek
=====

Seeks on a file pointer

### Description

<span class="type">int</span> <span class="methodname">fseek</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">int</span> `$offset`</span> \[, <span
class="methodparam"><span class="type">int</span> `$whence`<span
class="initializer"> = SEEK\_SET</span></span> \] )

Sets the file position indicator for the file referenced by `handle`.
The new position, measured in bytes from the beginning of the file, is
obtained by adding `offset` to the position specified by `whence`.

In general, it is allowed to seek past the end-of-file; if data is then
written, reads in any unwritten region between the end-of-file and the
sought position will yield bytes with value 0. However, certain streams
may not support this behavior, especially when they have an underlying
fixed size storage.

### Parameters

`handle`  
A file system pointer <span class="type">resource</span> that is
typically created using <span class="function">fopen</span>.

`offset`  
The offset.

To move to a position before the end-of-file, you need to pass a
negative value in `offset` and set `whence` to **`SEEK_END`**.

`whence`  
`whence` values are:

-   **`SEEK_SET`** - Set position equal to `offset` bytes.
-   **`SEEK_CUR`** - Set position to current location plus `offset`.
-   **`SEEK_END`** - Set position to end-of-file plus `offset`.

### Return Values

Upon success, returns 0; otherwise, returns -1.

### Examples

**Example \#1 <span class="function">fseek</span> example**

``` php
<?php

$fp = fopen('somefile.txt', 'r');

// read some data
$data = fgets($fp, 4096);

// move back to the beginning of the file
// same as rewind($fp);
fseek($fp, 0);

?>
```

### Notes

> **Note**:
>
> If you have opened the file in append (*a* or *a+*) mode, any data you
> write to the file will always be appended, regardless of the file
> position, and the result of calling <span
> class="function">fseek</span> will be undefined.

> **Note**:
>
> Not all streams support seeking. For those that do not support
> seeking, forward seeking from the current position is accomplished by
> reading and discarding data; other forms of seeking will fail.

### See Also

-   <span class="function">ftell</span>
-   <span class="function">rewind</span>

fstat
=====

Gets information about a file using an open file pointer

### Description

<span class="type">array</span> <span class="methodname">fstat</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

Gathers the statistics of the file opened by the file pointer `handle`.
This function is similar to the <span class="function">stat</span>
function except that it operates on an open file pointer instead of a
filename.

### Parameters

`handle`  
A file system pointer <span class="type">resource</span> that is
typically created using <span class="function">fopen</span>.

### Return Values

Returns an array with the statistics of the file; the format of the
array is described in detail on the <span class="function">stat</span>
manual page.

### Examples

**Example \#1 <span class="function">fstat</span> example**

``` php
<?php

// open a file
$fp = fopen("/etc/passwd", "r");

// gather statistics
$fstat = fstat($fp);

// close the file
fclose($fp);

// print only the associative part
print_r(array_slice($fstat, 13));

?>
```

The above example will output something similar to:

    Array
    (
        [dev] => 771
        [ino] => 488704
        [mode] => 33188
        [nlink] => 1
        [uid] => 0
        [gid] => 0
        [rdev] => 0
        [size] => 1114
        [atime] => 1061067181
        [mtime] => 1056136526
        [ctime] => 1056136526
        [blksize] => 4096
        [blocks] => 8
    )

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

ftell
=====

Returns the current position of the file read/write pointer

### Description

<span class="type">int</span> <span class="methodname">ftell</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

Returns the position of the file pointer referenced by `handle`.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span> or <span
class="function">popen</span>. <span class="function">ftell</span> gives
undefined results for append-only streams (opened with "a" flag).

### Return Values

Returns the position of the file pointer referenced by `handle` as an
integer; i.e., its offset into the file stream.

If an error occurs, returns **`FALSE`**.

> **Note**: <span class="simpara"> Because PHP's integer type is signed
> and many platforms use 32bit integers, some filesystem functions may
> return unexpected results for files which are larger than 2GB. </span>

### Examples

**Example \#1 <span class="function">ftell</span> example**

``` php
<?php

// opens a file and read some data
$fp = fopen("/etc/passwd", "r");
$data = fgets($fp, 12);

// where are we ?
echo ftell($fp); // 11

fclose($fp);

?>
```

### See Also

-   <span class="function">fopen</span>
-   <span class="function">popen</span>
-   <span class="function">fseek</span>
-   <span class="function">rewind</span>

ftruncate
=========

Truncates a file to a given length

### Description

<span class="type">bool</span> <span class="methodname">ftruncate</span>
( <span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">int</span> `$size`</span> )

Takes the filepointer, `handle`, and truncates the file to length,
`size`.

### Parameters

`handle`  
The file pointer.

> **Note**:
>
> The `handle` must be open for writing.

`size`  
The size to truncate to.

> **Note**:
>
> If `size` is larger than the file then the file is extended with null
> bytes.
>
> If `size` is smaller than the file then the file is truncated to that
> size.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 File truncation example**

``` php
<?php
$filename = 'lorem_ipsum.txt';

$handle = fopen($filename, 'r+');
ftruncate($handle, rand(1, filesize($filename)));
rewind($handle);
echo fread($handle, filesize($filename));
fclose($handle);
?>
```

### Notes

> **Note**:
>
> The file pointer is *not* changed.

### See Also

-   <span class="function">fopen</span>
-   <span class="function">fseek</span>

fwrite
======

Binary-safe file write

### Description

<span class="type">int</span> <span class="methodname">fwrite</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$length`</span> \] )

<span class="function">fwrite</span> writes the contents of `string` to
the file stream pointed to by `handle`.

### Parameters

`handle`  
A file system pointer <span class="type">resource</span> that is
typically created using <span class="function">fopen</span>.

`string`  
The string that is to be written.

`length`  
If the `length` argument is given, writing will stop after `length`
bytes have been written or the end of `string` is reached, whichever
comes first.

Note that if the `length` argument is given, then the
<a href="/info/setup.html#" class="link">magic_quotes_runtime</a>
configuration option will be ignored and no slashes will be stripped
from `string`.

### Return Values

<span class="function">fwrite</span> returns the number of bytes
written, or **`FALSE`** on error.

### Notes

> **Note**:
>
> Writing to a network stream may end before the whole string is
> written. Return value of <span class="function">fwrite</span> may be
> checked:
>
> ``` php
> <?php
> function fwrite_stream($fp, $string) {
>     for ($written = 0; $written < strlen($string); $written += $fwrite) {
>         $fwrite = fwrite($fp, substr($string, $written));
>         if ($fwrite === false) {
>             return $written;
>         }
>     }
>     return $written;
> }
> ?>
> ```

> **Note**:
>
> On systems which differentiate between binary and text files (i.e.
> Windows) the file must be opened with 'b' included in <span
> class="function">fopen</span> mode parameter.

> **Note**:
>
> If `handle` was <span class="function">fopen</span>ed in append mode,
> <span class="function">fwrite</span>s are atomic (unless the size of
> `string` exceeds the filesystem's block size, on some platforms, and
> as long as the file is on a local filesystem). That is, there is no
> need to <span class="function">flock</span> a resource before calling
> <span class="function">fwrite</span>; all of the data will be written
> without interruption.

> **Note**:
>
> If writing twice to the file pointer, then the data will be appended
> to the end of the file content:
>
> ``` php
> <?php
> $fp = fopen('data.txt', 'w');
> fwrite($fp, '1');
> fwrite($fp, '23');
> fclose($fp);
>
> // the content of 'data.txt' is now 123 and not 23!
> ?>
> ```

### Examples

**Example \#1 A simple <span class="function">fwrite</span> example**

``` php
<?php
$filename = 'test.txt';
$somecontent = "Add this to the file\n";

// Let's make sure the file exists and is writable first.
if (is_writable($filename)) {

    // In our example we're opening $filename in append mode.
    // The file pointer is at the bottom of the file hence
    // that's where $somecontent will go when we fwrite() it.
    if (!$handle = fopen($filename, 'a')) {
         echo "Cannot open file ($filename)";
         exit;
    }

    // Write $somecontent to our opened file.
    if (fwrite($handle, $somecontent) === FALSE) {
        echo "Cannot write to file ($filename)";
        exit;
    }

    echo "Success, wrote ($somecontent) to file ($filename)";

    fclose($handle);

} else {
    echo "The file $filename is not writable";
}
?>
```

### See Also

-   <span class="function">fread</span>
-   <span class="function">fopen</span>
-   <span class="function">fsockopen</span>
-   <span class="function">popen</span>
-   <span class="function">file\_get\_contents</span>
-   <span class="function">pack</span>

glob
====

Find pathnames matching a pattern

### Description

<span class="type">array</span> <span class="methodname">glob</span> (
<span class="methodparam"><span class="type">string</span>
`$pattern`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \] )

The <span class="function">glob</span> function searches for all the
pathnames matching `pattern` according to the rules used by the libc
glob() function, which is similar to the rules used by common shells.

### Parameters

`pattern`  
The pattern. No tilde expansion or parameter substitution is done.

Special characters:

-   <span class="simpara"> *\** - Matches zero or more characters.
    </span>
-   <span class="simpara"> *?* - Matches exactly one character (any
    character). </span>
-   <span class="simpara"> *\[...\]* - Matches one character from a
    group of characters. If the first character is *!*, matches any
    character not in the group. </span>
-   <span class="simpara"> *\\* - Escapes the following character,
    except when the **`GLOB_NOESCAPE`** flag is used. </span>

`flags`  
Valid flags:

-   <span class="simpara"> **`GLOB_MARK`** - Adds a slash (a backslash
    on Windows) to each directory returned </span>
-   <span class="simpara"> **`GLOB_NOSORT`** - Return files as they
    appear in the directory (no sorting). When this flag is not used,
    the pathnames are sorted alphabetically </span>
-   <span class="simpara"> **`GLOB_NOCHECK`** - Return the search
    pattern if no files matching it were found </span>
-   <span class="simpara"> **`GLOB_NOESCAPE`** - Backslashes do not
    quote metacharacters </span>
-   <span class="simpara"> **`GLOB_BRACE`** - Expands {a,b,c} to match
    'a', 'b', or 'c' </span>
-   <span class="simpara"> **`GLOB_ONLYDIR`** - Return only directory
    entries which match the pattern </span>
-   <span class="simpara"> **`GLOB_ERR`** - Stop on read errors (like
    unreadable directories), by default errors are ignored. </span>

### Return Values

Returns an array containing the matched files/directories, an empty
array if no file matched or **`FALSE`** on error.

> **Note**:
>
> On some systems it is impossible to distinguish between empty match
> and an error.

### Examples

**Example \#1 Convenient way how <span class="function">glob</span> can
replace <span class="function">opendir</span> and friends.**

``` php
<?php
foreach (glob("*.txt") as $filename) {
    echo "$filename size " . filesize($filename) . "\n";
}
?>
```

The above example will output something similar to:

    funclist.txt size 44686
    funcsummary.txt size 267625
    quickref.txt size 137820

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

> **Note**: <span class="simpara"> This function isn't available on some
> systems (e.g. old Sun OS). </span>

> **Note**: <span class="simpara"> The **`GLOB_BRACE`** flag is not
> available on some non GNU systems, like Solaris. </span>

### See Also

-   <span class="function">opendir</span>
-   <span class="function">readdir</span>
-   <span class="function">closedir</span>
-   <span class="function">fnmatch</span>

is\_dir
=======

Tells whether the filename is a directory

### Description

<span class="type">bool</span> <span class="methodname">is\_dir</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Tells whether the given filename is a directory.

### Parameters

`filename`  
Path to the file. If `filename` is a relative filename, it will be
checked relative to the current working directory. If `filename` is a
symbolic or hard link then the link will be resolved and checked. If you
have enabled
<a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>,
or
<a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
further restrictions may apply.

### Return Values

Returns **`TRUE`** if the filename exists and is a directory,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_dir</span> example**

``` php
<?php
var_dump(is_dir('a_file.txt'));
var_dump(is_dir('bogus_dir/abc'));

var_dump(is_dir('..')); //one dir up
?>
```

The above example will output:

    bool(false)
    bool(false)
    bool(true)

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">chdir</span>
-   <span class="function">dir</span>
-   <span class="function">opendir</span>
-   <span class="function">is\_file</span>
-   <span class="function">is\_link</span>

is\_executable
==============

Tells whether the filename is executable

### Description

<span class="type">bool</span> <span
class="methodname">is\_executable</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Tells whether the filename is executable.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns **`TRUE`** if the filename exists and is executable, or
**`FALSE`** on error.

### Examples

**Example \#1 <span class="function">is\_executable</span> example**

``` php
<?php

$file = '/home/vincent/somefile.sh';

if (is_executable($file)) {
    echo $file.' is executable';
} else {
    echo $file.' is not executable';
}

?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">is\_file</span>
-   <span class="function">is\_link</span>

is\_file
========

Tells whether the filename is a regular file

### Description

<span class="type">bool</span> <span class="methodname">is\_file</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Tells whether the given file is a regular file.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns **`TRUE`** if the filename exists and is a regular file,
**`FALSE`** otherwise.

> **Note**: <span class="simpara"> Because PHP's integer type is signed
> and many platforms use 32bit integers, some filesystem functions may
> return unexpected results for files which are larger than 2GB. </span>

### Examples

**Example \#1 <span class="function">is\_file</span> example**

``` php
<?php
var_dump(is_file('a_file.txt')) . "\n";
var_dump(is_file('/usr/bin/')) . "\n";
?>
```

The above example will output:

    bool(true)
    bool(false)

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">is\_dir</span>
-   <span class="function">is\_link</span>

is\_link
========

Tells whether the filename is a symbolic link

### Description

<span class="type">bool</span> <span class="methodname">is\_link</span>
( <span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Tells whether the given file is a symbolic link.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns **`TRUE`** if the filename exists and is a symbolic link,
**`FALSE`** otherwise.

### Examples

**Example \#1 Create and confirm if a file is a symbolic link**

``` php
<?php
$link = 'uploads';

if (is_link($link)) {
    echo(readlink($link));
} else {
    symlink('uploads.php', $link);
}
?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">is\_dir</span>
-   <span class="function">is\_file</span>
-   <span class="function">readlink</span>

is\_readable
============

Tells whether a file exists and is readable

### Description

<span class="type">bool</span> <span
class="methodname">is\_readable</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> )

Tells whether a file exists and is readable.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns **`TRUE`** if the file or directory specified by `filename`
exists and is readable, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_readable</span> example**

``` php
<?php
$filename = 'test.txt';
if (is_readable($filename)) {
    echo 'The file is readable';
} else {
    echo 'The file is not readable';
}
?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

Keep in mind that PHP may be accessing the file as the user id that the
web server runs as (often 'nobody'). Safe mode limitations are not taken
into account before PHP 5.1.5.

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

> **Note**:
>
> The check is done using the real UID/GID instead of the effective one.

This function may return **`TRUE`** for directories. Use <span
class="function">is\_dir</span> to distinguish file and directory.

### See Also

-   <span class="function">is\_writable</span>
-   <span class="function">file\_exists</span>
-   <span class="function">fgets</span>

is\_uploaded\_file
==================

Tells whether the file was uploaded via HTTP POST

### Description

<span class="type">bool</span> <span
class="methodname">is\_uploaded\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Returns **`TRUE`** if the file named by `filename` was uploaded via HTTP
POST. This is useful to help ensure that a malicious user hasn't tried
to trick the script into working on files upon which it should not be
working--for instance, `/etc/passwd`.

This sort of check is especially important if there is any chance that
anything done with uploaded files could reveal their contents to the
user, or even to other users on the same system.

For proper working, the function <span
class="function">is\_uploaded\_file</span> needs an argument like
`$_FILES['userfile']['tmp_name']`, - the name of the uploaded file on
the client's machine `$_FILES['userfile']['name']` does not work.

### Parameters

`filename`  
The filename being checked.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">is\_uploaded\_file</span> example**

``` php
<?php

if (is_uploaded_file($_FILES['userfile']['tmp_name'])) {
   echo "File ". $_FILES['userfile']['name'] ." uploaded successfully.\n";
   echo "Displaying contents\n";
   readfile($_FILES['userfile']['tmp_name']);
} else {
   echo "Possible file upload attack: ";
   echo "filename '". $_FILES['userfile']['tmp_name'] . "'.";
}

?>
```

### See Also

-   <span class="function">move\_uploaded\_file</span>
-   `$_FILES`
-   See
    <a href="/features/file-upload.html" class="link">Handling file uploads</a>
    for a simple usage example.

is\_writable
============

Tells whether the filename is writable

### Description

<span class="type">bool</span> <span
class="methodname">is\_writable</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> )

Returns **`TRUE`** if the `filename` exists and is writable. The
filename argument may be a directory name allowing you to check if a
directory is writable.

Keep in mind that PHP may be accessing the file as the user id that the
web server runs as (often 'nobody'). Safe mode limitations are not taken
into account.

### Parameters

`filename`  
The filename being checked.

### Return Values

Returns **`TRUE`** if the `filename` exists and is writable.

### Examples

**Example \#1 <span class="function">is\_writable</span> example**

``` php
<?php
$filename = 'test.txt';
if (is_writable($filename)) {
    echo 'The file is writable';
} else {
    echo 'The file is not writable';
}
?>
```

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">is\_readable</span>
-   <span class="function">file\_exists</span>
-   <span class="function">fwrite</span>

is\_writeable
=============

Alias of <span class="function">is\_writable</span>

### Description

This function is an alias of: <span
class="function">is\_writable</span>.

lchgrp
======

Changes group ownership of symlink

### Description

<span class="type">bool</span> <span class="methodname">lchgrp</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">mixed</span> `$group`</span> )

Attempts to change the group of the symlink `filename` to `group`.

Only the superuser may change the group of a symlink arbitrarily; other
users may change the group of a symlink to any group of which that user
is a member.

### Parameters

`filename`  
Path to the symlink.

`group`  
The group specified by name or number.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Changing the group of a symbolic link**

``` php
<?php
$target = 'output.php';
$link = 'output.html';
symlink($target, $link);

lchgrp($link, 8);
?>
```

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the files or directories being operated
> upon have the same UID (owner) as the script that is being
> executed.</span>

> **Note**: <span class="simpara">This function is not implemented on
> Windows platforms.</span>

### See Also

-   <span class="function">chgrp</span>
-   <span class="function">lchown</span>
-   <span class="function">chown</span>
-   <span class="function">chmod</span>

lchown
======

Changes user ownership of symlink

### Description

<span class="type">bool</span> <span class="methodname">lchown</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">mixed</span> `$user`</span> )

Attempts to change the owner of the symlink `filename` to user `user`.

Only the superuser may change the owner of a symlink.

### Parameters

`filename`  
Path to the file.

`user`  
User name or number.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Changing the owner of a symbolic link**

``` php
<?php
$target = 'output.php';
$link = 'output.html';
symlink($target, $link);

lchown($link, 8);
?>
```

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the files or directories being operated
> upon have the same UID (owner) as the script that is being
> executed.</span>

> **Note**: <span class="simpara">This function is not implemented on
> Windows platforms.</span>

### See Also

-   <span class="function">chown</span>
-   <span class="function">lchgrp</span>
-   <span class="function">chgrp</span>
-   <span class="function">chmod</span>

link
====

Create a hard link

### Description

<span class="type">bool</span> <span class="methodname">link</span> (
<span class="methodparam"><span class="type">string</span>
`$target`</span> , <span class="methodparam"><span
class="type">string</span> `$link`</span> )

<span class="function">link</span> creates a hard link.

### Parameters

`target`  
Target of the link.

`link`  
The link name.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Creating a simple hard link**

``` php
<?php
$target = 'source.ext'; // This is the file that already exists
$link = 'newfile.ext'; // This the filename that you want to link it to

link($target, $link);
?>
```

### Notes

> **Note**: <span class="simpara">This function will not work on
> <a href="/features/remote-files.html" class="link">remote files</a> as
> the file to be examined must be accessible via the server's
> filesystem.</span>

> **Note**: <span class="simpara"> For Windows only: This function
> requires PHP to run in an elevated mode or with the UAC disabled.
> </span>

### See Also

-   <span class="function">symlink</span>
-   <span class="function">readlink</span>
-   <span class="function">linkinfo</span>

linkinfo
========

Gets information about a link

### Description

<span class="type">int</span> <span class="methodname">linkinfo</span> (
<span class="methodparam"><span class="type">string</span>
`$path`</span> )

Gets information about a link.

This function is used to verify if a link (pointed to by `path`) really
exists (using the same method as the S\_ISLNK macro defined in
`stat.h`).

### Parameters

`path`  
Path to the link.

### Return Values

<span class="function">linkinfo</span> returns the *st\_dev* field of
the Unix C stat structure returned by the *lstat* system call. Returns a
non-negative integer on success, -1 in case the link was not found, or
**`FALSE`** if an open.base\_dir violation occurs.

### Examples

**Example \#1 <span class="function">linkinfo</span> example**

``` php
<?php

echo linkinfo('/vmlinuz'); // 835

?>
```

### See Also

-   <span class="function">symlink</span>
-   <span class="function">link</span>
-   <span class="function">readlink</span>

lstat
=====

Gives information about a file or symbolic link

### Description

<span class="type">array</span> <span class="methodname">lstat</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gathers the statistics of the file or symbolic link named by `filename`.

### Parameters

`filename`  
Path to a file or a symbolic link.

### Return Values

See the manual page for <span class="function">stat</span> for
information on the structure of the array that <span
class="function">lstat</span> returns. This function is identical to the
<span class="function">stat</span> function except that if the
`filename` parameter is a symbolic link, the status of the symbolic link
is returned, not the status of the file pointed to by the symbolic link.

### Examples

**Example \#1 Comparison of <span class="function">stat</span> and <span
class="function">lstat</span>**

``` php
<?php
symlink('uploads.php', 'uploads');

// Contrast information for uploads.php and uploads
array_diff(stat('uploads'), lstat('uploads'));
?>
```

The above example will output something similar to:

Information that differs between the two files.

    Array
    (
        [ino] => 97236376
        [mode] => 33188
        [size] => 34
        [atime] => 1223580003
        [mtime] => 1223581848
        [ctime] => 1223581848
        [blocks] => 8
    )

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Notes

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">stat</span>

mkdir
=====

Makes directory

### Description

<span class="type">bool</span> <span class="methodname">mkdir</span> (
<span class="methodparam"><span class="type">string</span>
`$pathname`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
0777</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$recursive`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\]\] )

Attempts to create the directory specified by pathname.

### Parameters

`pathname`  
The directory path.

`mode`  
The mode is 0777 by default, which means the widest possible access. For
more information on modes, read the details on the <span
class="function">chmod</span> page.

> **Note**:
>
> `mode` is ignored on Windows.

Note that you probably want to specify the mode as an octal number,
which means it should have a leading zero. The mode is also modified by
the current umask, which you can change using <span
class="function">umask</span>.

`recursive`  
Allows the creation of nested directories specified in the `pathname`.

`context`  
> **Note**: <span class="simpara">Context support was added with PHP
> 5.0.0. For a description of *contexts*, refer to
> <a href="/book/stream.html" class="xref">Streams</a>.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">mkdir</span> example**

``` php
<?php
mkdir("/path/to/my/dir", 0700);
?>
```

**Example \#2 <span class="function">mkdir</span> using the `recursive`
parameter**

``` php
<?php
// Desired folder structure
$structure = './depth1/depth2/depth3/';

// To create the nested structure, the $recursive parameter 
// to mkdir() must be specified.

if (!mkdir($structure, 0777, true)) {
    die('Failed to create folders...');
}

// ...
?>
```

### Errors/Exceptions

Emits an **`E_WARNING`** level error if the directory already exists.

Emits an **`E_WARNING`** level error if the relevant permissions prevent
creating the directory.

### Notes

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the directory in which the script is
> operating has the same UID (owner) as the script that is being
> executed.</span>

### See Also

-   <span class="function">is\_dir</span>
-   <span class="function">rmdir</span>

move\_uploaded\_file
====================

Moves an uploaded file to a new location

### Description

<span class="type">bool</span> <span
class="methodname">move\_uploaded\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">string</span>
`$destination`</span> )

This function checks to ensure that the file designated by `filename` is
a valid upload file (meaning that it was uploaded via PHP's HTTP POST
upload mechanism). If the file is valid, it will be moved to the
filename given by `destination`.

This sort of check is especially important if there is any chance that
anything done with uploaded files could reveal their contents to the
user, or even to other users on the same system.

### Parameters

`filename`  
The filename of the uploaded file.

`destination`  
The destination of the moved file.

### Return Values

Returns **`TRUE`** on success.

If `filename` is not a valid upload file, then no action will occur, and
<span class="function">move\_uploaded\_file</span> will return
**`FALSE`**.

If `filename` is a valid upload file, but cannot be moved for some
reason, no action will occur, and <span
class="function">move\_uploaded\_file</span> will return **`FALSE`**.
Additionally, a warning will be issued.

### Examples

**Example \#1 Uploading multiple files**

``` php
<?php
$uploads_dir = '/uploads';
foreach ($_FILES["pictures"]["error"] as $key => $error) {
    if ($error == UPLOAD_ERR_OK) {
        $tmp_name = $_FILES["pictures"]["tmp_name"][$key];
        // basename() may prevent filesystem traversal attacks;
        // further validation/sanitation of the filename may be appropriate
        $name = basename($_FILES["pictures"]["name"][$key]);
        move_uploaded_file($tmp_name, "$uploads_dir/$name");
    }
}
?>
```

### Notes

> **Note**:
>
> <span class="function">move\_uploaded\_file</span> is both
> <a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe mode</a>
> and
> <a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
> aware. However, restrictions are placed only on the `destination` path
> as to allow the moving of uploaded files in which `filename` may
> conflict with such restrictions. <span
> class="function">move\_uploaded\_file</span> ensures the safety of
> this operation by allowing only those files uploaded through PHP to be
> moved.

**Warning**

If the destination file already exists, it will be overwritten.

### See Also

-   <span class="function">is\_uploaded\_file</span>
-   <span class="function">rename</span>
-   See
    <a href="/features/file-upload.html" class="link">Handling file uploads</a>
    for a simple usage example

parse\_ini\_file
================

Parse a configuration file

### Description

<span class="type">array</span> <span
class="methodname">parse\_ini\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$process_sections`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$scanner_mode`<span class="initializer"> =
INI\_SCANNER\_NORMAL</span></span> \]\] )

<span class="function">parse\_ini\_file</span> loads in the ini file
specified in `filename`, and returns the settings in it in an
associative array.

The structure of the ini file is the same as the `php.ini`'s.

### Parameters

`filename`  
The filename of the ini file being parsed.

`process_sections`  
By setting the `process_sections` parameter to **`TRUE`**, you get a
multidimensional array, with the section names and settings included.
The default for `process_sections` is **`FALSE`**

`scanner_mode`  
Can either be **`INI_SCANNER_NORMAL`** (default) or
**`INI_SCANNER_RAW`**. If **`INI_SCANNER_RAW`** is supplied, then option
values will not be parsed.

As of PHP 5.6.1 can also be specified as **`INI_SCANNER_TYPED`**. In
this mode boolean, null and integer types are preserved when possible.
String values *"true"*, *"on"* and *"yes"* are converted to **`TRUE`**.
*"false"*, *"off"*, *"no"* and *"none"* are considered **`FALSE`**.
*"null"* is converted to **`NULL`** in typed mode. Also, all numeric
strings are converted to integer type if it is possible.

### Return Values

The settings are returned as an associative <span
class="type">array</span> on success, and **`FALSE`** on failure.

### Examples

**Example \#1 Contents of `sample.ini`**

    ; This is a sample configuration file
    ; Comments start with ';', as in php.ini

    [first_section]
    one = 1
    five = 5
    animal = BIRD

    [second_section]
    path = "/usr/local/bin"
    URL = "http://www.example.com/~username"

    [third_section]
    phpversion[] = "5.0"
    phpversion[] = "5.1"
    phpversion[] = "5.2"
    phpversion[] = "5.3"

    urls[svn] = "http://svn.php.net"
    urls[git] = "http://git.php.net"

**Example \#2 <span class="function">parse\_ini\_file</span> example**

<a href="/language/constants.html" class="link">Constants</a> may also
be parsed in the ini file so if you define a constant as an ini value
before running <span class="function">parse\_ini\_file</span>, it will
be integrated into the results. Only ini values are evaluated. For
example:

``` php
<?php

define('BIRD', 'Dodo bird');

// Parse without sections
$ini_array = parse_ini_file("sample.ini");
print_r($ini_array);

// Parse with sections
$ini_array = parse_ini_file("sample.ini", true);
print_r($ini_array);

?>
```

The above example will output something similar to:

    Array
    (
        [one] => 1
        [five] => 5
        [animal] => Dodo bird
        [path] => /usr/local/bin
        [URL] => http://www.example.com/~username
        [phpversion] => Array
            (
                [0] => 5.0
                [1] => 5.1
                [2] => 5.2
                [3] => 5.3
            )

        [urls] => Array
            (
                [svn] => http://svn.php.net
                [git] => http://git.php.net
            )

    )
    Array
    (
        [first_section] => Array
            (
                [one] => 1
                [five] => 5
                [animal] => Dodo bird
            )

        [second_section] => Array
            (
                [path] => /usr/local/bin
                [URL] => http://www.example.com/~username
            )

        [third_section] => Array
            (
                [phpversion] => Array
                    (
                        [0] => 5.0
                        [1] => 5.1
                        [2] => 5.2
                        [3] => 5.3
                    )

                [urls] => Array
                    (
                        [svn] => http://svn.php.net
                        [git] => http://git.php.net
                    )

            )

    )

**Example \#3 <span class="function">parse\_ini\_file</span> parsing a
php.ini file**

``` php
<?php
// A simple function used for comparing the results below
function yesno($expression)
{
    return($expression ? 'Yes' : 'No');
}

// Get the path to php.ini using the php_ini_loaded_file() 
// function available as of PHP 5.2.4
$ini_path = php_ini_loaded_file();

// Parse php.ini
$ini = parse_ini_file($ini_path);

// Print and compare the values, note that using get_cfg_var()
// will give the same results for parsed and loaded here
echo '(parsed) magic_quotes_gpc = ' . yesno($ini['magic_quotes_gpc']) . PHP_EOL;
echo '(loaded) magic_quotes_gpc = ' . yesno(get_cfg_var('magic_quotes_gpc')) . PHP_EOL;
?>
```

The above example will output something similar to:

    (parsed) magic_quotes_gpc = Yes
    (loaded) magic_quotes_gpc = Yes

### Notes

> **Note**:
>
> This function has nothing to do with the `php.ini` file. It is already
> processed by the time you run your script. This function can be used
> to read in your own application's configuration files.

> **Note**:
>
> If a value in the ini file contains any non-alphanumeric characters it
> needs to be enclosed in double-quotes (").

> **Note**: <span class="simpara"> There are reserved words which must
> not be used as keys for ini files. These include: *null*, *yes*, *no*,
> *true*, *false*, *on*, *off*, *none*. Values *null*, *off*, *no* and
> *false* result in *""*, and values *on*, *yes* and *true* result in
> *"1"*, unless **`INI_SCANNER_TYPED`** mode is used (as of PHP 5.6.1).
> Characters *?{}\|&\~!()^"* must not be used anywhere in the key and
> have a special meaning in the value. </span>

> **Note**:
>
> Entries without an equal sign are ignored. For example, "foo" is
> ignored whereas "bar =" is parsed and added with an empty value. For
> example, MySQL has a "no-auto-rehash" setting in `my.cnf` that does
> not take a value, so it is ignored.

### See Also

-   <span class="function">parse\_ini\_string</span>

parse\_ini\_string
==================

Parse a configuration string

### Description

<span class="type">array</span> <span
class="methodname">parse\_ini\_string</span> ( <span
class="methodparam"><span class="type">string</span> `$ini`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$process_sections`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$scanner_mode`<span class="initializer"> =
INI\_SCANNER\_NORMAL</span></span> \]\] )

<span class="function">parse\_ini\_string</span> returns the settings in
string `ini` in an associative array.

The structure of the ini string is the same as the `php.ini`'s.

### Parameters

`ini`  
The contents of the ini file being parsed.

`process_sections`  
By setting the `process_sections` parameter to **`TRUE`**, you get a
multidimensional array, with the section names and settings included.
The default for `process_sections` is **`FALSE`**

`scanner_mode`  
Can either be **`INI_SCANNER_NORMAL`** (default) or
**`INI_SCANNER_RAW`**. If **`INI_SCANNER_RAW`** is supplied, then option
values will not be parsed.

As of PHP 5.6.1 can also be specified as **`INI_SCANNER_TYPED`**. In
this mode boolean, null and integer types are preserved when possible.
String values *"true"*, *"on"* and *"yes"* are converted to **`TRUE`**.
*"false"*, *"off"*, *"no"* and *"none"* are considered **`FALSE`**.
*"null"* is converted to **`NULL`** in typed mode. Also, all numeric
strings are converted to integer type if it is possible.

### Return Values

The settings are returned as an associative <span
class="type">array</span> on success, and **`FALSE`** on failure.

### Notes

> **Note**: <span class="simpara"> There are reserved words which must
> not be used as keys for ini files. These include: *null*, *yes*, *no*,
> *true*, *false*, *on*, *off*, *none*. Values *null*, *off*, *no* and
> *false* result in *""*, and values *on*, *yes* and *true* result in
> *"1"*, unless **`INI_SCANNER_TYPED`** mode is used. Characters
> *?{}\|&\~!\[()^"* must not be used anywhere in the key and have a
> special meaning in the value. </span>

### See Also

-   <span class="function">parse\_ini\_file</span>

pathinfo
========

Returns information about a file path

### Description

<span class="type">mixed</span> <span class="methodname">pathinfo</span>
( <span class="methodparam"><span class="type">string</span>
`$path`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`<span class="initializer"> =
PATHINFO\_DIRNAME \| PATHINFO\_BASENAME \| PATHINFO\_EXTENSION \|
PATHINFO\_FILENAME</span></span> \] )

<span class="function">pathinfo</span> returns information about `path`:
either an associative array or a string, depending on `options`.

> **Note**:
>
> For information on retrieving the current path info, read the section
> on
> <a href="/language/variables/predefined.html" class="link">predefined reserved variables</a>.

**Caution**

<span class="function">pathinfo</span> is locale aware, so for it to
parse a path containing multibyte characters correctly, the matching
locale must be set using the <span class="function">setlocale</span>
function.

### Parameters

`path`  
The path to be parsed.

`options`  
If present, specifies a specific element to be returned; one of
**`PATHINFO_DIRNAME`**, **`PATHINFO_BASENAME`**,
**`PATHINFO_EXTENSION`** or **`PATHINFO_FILENAME`**.

If `options` is not specified, returns all available elements.

### Return Values

If the `options` parameter is not passed, an associative <span
class="type">array</span> containing the following elements is returned:
*dirname*, *basename*, *extension* (if any), and *filename*.

> **Note**:
>
> If the `path` has more than one extension, **`PATHINFO_EXTENSION`**
> returns only the last one and **`PATHINFO_FILENAME`** only strips the
> last one. (see first example below).

> **Note**:
>
> If the `path` does not have an extension, no *extension* element will
> be returned (see second example below).

> **Note**:
>
> If the *basename* of the `path` starts with a dot, the following
> characters are interpreted as *extension*, and the *filename* is empty
> (see third example below).

If `options` is present, returns a <span class="type">string</span>
containing the requested element.

### Examples

**Example \#1 <span class="function">pathinfo</span> Example**

``` php
<?php
$path_parts = pathinfo('/www/htdocs/inc/lib.inc.php');

echo $path_parts['dirname'], "\n";
echo $path_parts['basename'], "\n";
echo $path_parts['extension'], "\n";
echo $path_parts['filename'], "\n"; // since PHP 5.2.0
?>
```

The above example will output:

    /www/htdocs/inc
    lib.inc.php
    php
    lib.inc

**Example \#2 <span class="function">pathinfo</span> example showing
difference between null and no extension**

``` php
<?php
$path_parts = pathinfo('/path/emptyextension.');
var_dump($path_parts['extension']);

$path_parts = pathinfo('/path/noextension');
var_dump($path_parts['extension']);
?>
```

The above example will output something similar to:

    string(0) ""

    Notice: Undefined index: extension in test.php on line 6
    NULL

**Example \#3 <span class="function">pathinfo</span> example for a
dot-file**

``` php
<?php
print_r(pathinfo('/some/path/.test'));
?>
```

The above example will output something similar to:

    Array
    (
        [dirname] => /some/path
        [basename] => .test
        [extension] => test
        [filename] => 
    )

### See Also

-   <span class="function">dirname</span>
-   <span class="function">basename</span>
-   <span class="function">parse\_url</span>
-   <span class="function">realpath</span>

pclose
======

Closes process file pointer

### Description

<span class="type">int</span> <span class="methodname">pclose</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

Closes a file pointer to a pipe opened by <span
class="function">popen</span>.

### Parameters

`handle`  
The file pointer must be valid, and must have been returned by a
successful call to <span class="function">popen</span>.

### Return Values

Returns the termination status of the process that was run. In case of
an error then *-1* is returned.

> **Note**:
>
> If PHP has been compiled with --enable-sigchild, the return value of
> this function is undefined.

### Examples

**Example \#1 <span class="function">pclose</span> example**

``` php
<?php
$handle = popen('/bin/ls', 'r');
pclose($handle);
?>
```

### Notes

> **Note**: **Unix Only:**  
>
> <span class="function">pclose</span> is internally implemented using
> the *waitpid(3)* system call. To obtain the real exit status code the
> <span class="function">pcntl\_wexitstatus</span> function should be
> used.

### See Also

-   <span class="function">popen</span>

popen
=====

Opens process file pointer

### Description

<span class="type">resource</span> <span class="methodname">popen</span>
( <span class="methodparam"><span class="type">string</span>
`$command`</span> , <span class="methodparam"><span
class="type">string</span> `$mode`</span> )

Opens a pipe to a process executed by forking the command given by
`command`.

### Parameters

`command`  
The command

`mode`  
The mode

### Return Values

Returns a file pointer identical to that returned by <span
class="function">fopen</span>, except that it is unidirectional (may
only be used for reading or writing) and must be closed with <span
class="function">pclose</span>. This pointer may be used with <span
class="function">fgets</span>, <span class="function">fgetss</span>, and
<span class="function">fwrite</span>. When the mode is 'r', the returned
file pointer equals to the STDOUT of the command, when the mode is 'w',
the returned file pointer equals to the STDIN of the command.

If an error occurs, returns **`FALSE`**.

### Examples

**Example \#1 <span class="function">popen</span> example**

``` php
<?php
$handle = popen("/bin/ls", "r");
?>
```

If the command to be executed could not be found, a valid resource is
returned. This may seem odd, but makes sense; it allows you to access
any error message returned by the shell:

**Example \#2 <span class="function">popen</span> example**

``` php
<?php
error_reporting(E_ALL);

/* Add redirection so we can get stderr. */
$handle = popen('/path/to/executable 2>&1', 'r');
echo "'$handle'; " . gettype($handle) . "\n";
$read = fread($handle, 2096);
echo $read;
pclose($handle);
?>
```

### Notes

> **Note**:
>
> If you're looking for bi-directional support (two-way), use <span
> class="function">proc\_open</span>.

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, you can only execute files within the
> <a href="/ini/sect/safe-mode.html#ini.safe-mode-exec-dir" class="link">safe_mode_exec_dir</a>.
> For practical reasons, it is currently not allowed to have *..*
> components in the path to the executable.</span>

**Warning**

With <a href="/features/safe-mode.html" class="link">safe mode</a>
enabled, the command string is escaped with <span
class="function">escapeshellcmd</span>. Thus, *echo y \| echo x* becomes
*echo y \\\| echo x*.

### See Also

-   <span class="function">pclose</span>
-   <span class="function">fopen</span>
-   <span class="function">proc\_open</span>

readfile
========

Outputs a file

### Description

<span class="type">int</span> <span class="methodname">readfile</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\] )

Reads a file and writes it to the output buffer.

### Parameters

`filename`  
The filename being read.

`use_include_path`  
You can use the optional second parameter and set it to **`TRUE`**, if
you want to search for the file in the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>,
too.

`context`  
A context stream <span class="type">resource</span>.

### Return Values

Returns the number of bytes read from the file on success, or
**`FALSE`** on failure

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Examples

**Example \#1 Forcing a download using <span
class="function">readfile</span>**

``` php
<?php
$file = 'monkey.gif';

if (file_exists($file)) {
    header('Content-Description: File Transfer');
    header('Content-Type: application/octet-stream');
    header('Content-Disposition: attachment; filename="'.basename($file).'"');
    header('Expires: 0');
    header('Cache-Control: must-revalidate');
    header('Pragma: public');
    header('Content-Length: ' . filesize($file));
    readfile($file);
    exit;
}
?>
```

The above example will output something similar to:

<img src="images/e88cefb5c3fca5060e2490b9763c4433-readfile.png" width="319" height="245" alt="Open / Save dialogue" />

### Notes

> **Note**:
>
> <span class="function">readfile</span> will not present any memory
> issues, even when sending large files, on its own. If you encounter an
> out of memory error ensure that output buffering is off with <span
> class="function">ob\_get\_level</span>.

**Tip**

A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

> **Note**: <span class="simpara">Context support was added with PHP
> 5.0.0. For a description of *contexts*, refer to
> <a href="/book/stream.html" class="xref">Streams</a>.</span>

### See Also

-   <span class="function">fpassthru</span>
-   <span class="function">file</span>
-   <span class="function">fopen</span>
-   <span class="function">include</span>
-   <span class="function">require</span>
-   <span class="function">virtual</span>
-   <span class="function">file\_get\_contents</span>
-   <a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>

readlink
========

Returns the target of a symbolic link

### Description

<span class="type">string</span> <span
class="methodname">readlink</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> )

<span class="function">readlink</span> does the same as the readlink C
function.

### Parameters

`path`  
The symbolic link path.

### Return Values

Returns the contents of the symbolic link path or **`FALSE`** on error.

> **Note**: <span class="simpara"> The function fails if `path` is not a
> symlink, except on Windows, where the normalized path will be
> returned. </span>

### Examples

**Example \#1 <span class="function">readlink</span> example**

``` php
<?php

// output e.g. /boot/vmlinux-2.4.20-xfs
echo readlink('/vmlinuz');

?>
```

### See Also

-   <span class="function">is\_link</span>
-   <span class="function">symlink</span>
-   <span class="function">linkinfo</span>

realpath\_cache\_get
====================

Get realpath cache entries

### Description

<span class="type">array</span> <span
class="methodname">realpath\_cache\_get</span> ( <span
class="methodparam">void</span> )

Get the contents of the realpath cache.

### Return Values

Returns an array of realpath cache entries. The keys are original path
entries, and the values are arrays of data items, containing the
resolved path, expiration date, and other options kept in the cache.

### Examples

**Example \#1 <span class="function">realpath\_cache\_get</span>
example**

``` php
<?php
var_dump(realpath_cache_get());
?>
```

The above example will output something similar to:

    array(2) {
      ["/test"]=>
      array(4) {
        ["key"]=>
        int(123456789)
        ["is_dir"]=>
        bool(true)
        ["realpath"]=>
        string(5) "/test"
        ["expires"]=>
        int(1260318939)
      }
      ["/test/test.php"]=>
      array(4) {
        ["key"]=>
        int(987654321)
        ["is_dir"]=>
        bool(false)
        ["realpath"]=>
        string(12) "/root/test.php"
        ["expires"]=>
        int(1260318939)
      }
    }

### See Also

-   <span class="function">realpath\_cache\_size</span>

realpath\_cache\_size
=====================

Get realpath cache size

### Description

<span class="type">int</span> <span
class="methodname">realpath\_cache\_size</span> ( <span
class="methodparam">void</span> )

Get the amount of memory used by the realpath cache.

### Return Values

Returns how much memory realpath cache is using.

### Examples

**Example \#1 <span class="function">realpath\_cache\_size</span>
example**

``` php
<?php
var_dump(realpath_cache_size());
?>
```

The above example will output something similar to:

    int(412)

### See Also

-   <span class="function">realpath\_cache\_get</span>
-   The
    <a href="/ini/core.html#ini.realpath-cache-size" class="link">realpath_cache_size</a>
    configuration option

realpath
========

Returns canonicalized absolute pathname

### Description

<span class="type">string</span> <span
class="methodname">realpath</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> )

<span class="function">realpath</span> expands all symbolic links and
resolves references to */./*, */../* and extra */* characters in the
input `path` and returns the canonicalized absolute pathname.

### Parameters

`path`  
The path being checked.

> **Note**:
>
> Whilst a path must be supplied, the value can be an empty string. In
> this case, the value is interpreted as the current directory.

### Return Values

Returns the canonicalized absolute pathname on success. The resulting
path will have no symbolic link, */./* or */../* components. Trailing
delimiters, such as *\\* and */*, are also removed.

<span class="function">realpath</span> returns **`FALSE`** on failure,
e.g. if the file does not exist.

> **Note**:
>
> The running script must have executable permissions on all directories
> in the hierarchy, otherwise <span class="function">realpath</span>
> will return **`FALSE`**.

> **Note**:
>
> For case-insensitive filesystems <span
> class="function">realpath</span> may or may not normalize the
> character case.

> **Note**:
>
> The function <span class="function">realpath</span> will not work for
> a file which is inside a Phar as such path would be a virtual path,
> not a real one.

> **Note**: <span class="simpara"> Because PHP's integer type is signed
> and many platforms use 32bit integers, some filesystem functions may
> return unexpected results for files which are larger than 2GB. </span>

### Examples

**Example \#1 <span class="function">realpath</span> example**

``` php
<?php
chdir('/var/www/');
echo realpath('./../../etc/passwd') . PHP_EOL;

echo realpath('/tmp/') . PHP_EOL;
?>
```

The above example will output:

    /etc/passwd
    /tmp

**Example \#2 <span class="function">realpath</span> on Windows**

On windows <span class="function">realpath</span> will change unix style
paths to windows style.

``` php
<?php
echo realpath('/windows/system32'), PHP_EOL;

echo realpath('C:\Program Files\\'), PHP_EOL;
?>
```

The above example will output:

    C:\WINDOWS\System32
    C:\Program Files

### See Also

-   <span class="function">basename</span>
-   <span class="function">dirname</span>
-   <span class="function">pathinfo</span>

rename
======

Renames a file or directory

### Description

<span class="type">bool</span> <span class="methodname">rename</span> (
<span class="methodparam"><span class="type">string</span>
`$oldname`</span> , <span class="methodparam"><span
class="type">string</span> `$newname`</span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`</span>
\] )

Attempts to rename `oldname` to `newname`, moving it between directories
if necessary. If renaming a file and `newname` exists, it will be
overwritten. If renaming a directory and `newname` exists, this function
will emit a warning.

### Parameters

`oldname`  
The old name.

> **Note**:
>
> The wrapper used in `oldname` *must* match the wrapper used in
> `newname`.

`newname`  
The new name.

`context`  
> **Note**: <span class="simpara">Context support was added with PHP
> 5.0.0. For a description of *contexts*, refer to
> <a href="/book/stream.html" class="xref">Streams</a>.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Example with <span class="function">rename</span>**

``` php
<?php
rename("/tmp/tmp_file.txt", "/home/user/login/docs/my_file.txt");
?>
```

### See Also

-   <span class="function">copy</span>
-   <span class="function">unlink</span>
-   <span class="function">move\_uploaded\_file</span>

rewind
======

Rewind the position of a file pointer

### Description

<span class="type">bool</span> <span class="methodname">rewind</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> )

Sets the file position indicator for `handle` to the beginning of the
file stream.

> **Note**:
>
> If you have opened the file in append ("a" or "a+") mode, any data you
> write to the file will always be appended, regardless of the file
> pointer position.

### Parameters

`handle`  
The file pointer must be valid, and must point to a file successfully
opened by <span class="function">fopen</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">rewind</span> overwriting example**

``` php
<?php
$handle = fopen('output.txt', 'r+');

fwrite($handle, 'Really long sentence.');
rewind($handle);
fwrite($handle, 'Foo');
rewind($handle);

echo fread($handle, filesize('output.txt'));

fclose($handle);
?>
```

The above example will output something similar to:

    Foolly long sentence.

### See Also

-   <span class="function">fread</span>
-   <span class="function">fseek</span>
-   <span class="function">ftell</span>
-   <span class="function">fwrite</span>

rmdir
=====

Removes directory

### Description

<span class="type">bool</span> <span class="methodname">rmdir</span> (
<span class="methodparam"><span class="type">string</span>
`$dirname`</span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \] )

Attempts to remove the directory named by `dirname`. The directory must
be empty, and the relevant permissions must permit this. A
**`E_WARNING`** level error will be generated on failure.

### Parameters

`dirname`  
Path to the directory.

`context`  
> **Note**: <span class="simpara">Context support was added with PHP
> 5.0.0. For a description of *contexts*, refer to
> <a href="/book/stream.html" class="xref">Streams</a>.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">rmdir</span> example**

``` php
<?php
if (!is_dir('examples')) {
    mkdir('examples');
}

rmdir('examples');
?>
```

### Notes

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the directory in which the script is
> operating has the same UID (owner) as the script that is being
> executed.</span>

### See Also

-   <span class="function">is\_dir</span>
-   <span class="function">mkdir</span>
-   <span class="function">unlink</span>

set\_file\_buffer
=================

Alias of <span class="function">stream\_set\_write\_buffer</span>

### Description

This function is an alias of: <span
class="function">stream\_set\_write\_buffer</span>.

stat
====

Gives information about a file

### Description

<span class="type">array</span> <span class="methodname">stat</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Gathers the statistics of the file named by `filename`. If `filename` is
a symbolic link, statistics are from the file itself, not the symlink.
Prior to PHP 7.4.0, on Windows NTS builds the *size*, *atime*, *mtime*
and *ctime* statistics have been from the symlink, in this case.

<span class="function">lstat</span> is identical to <span
class="function">stat</span> except it would instead be based off the
symlinks status.

### Parameters

`filename`  
Path to the file.

### Return Values

| Numeric | Associative | Description                                |
|---------|-------------|--------------------------------------------|
| 0       | dev         | device number \*\*\*                       |
| 1       | ino         | inode number \*\*\*\*                      |
| 2       | mode        | inode protection mode                      |
| 3       | nlink       | number of links                            |
| 4       | uid         | userid of owner \*                         |
| 5       | gid         | groupid of owner \*                        |
| 6       | rdev        | device type, if inode device               |
| 7       | size        | size in bytes                              |
| 8       | atime       | time of last access (Unix timestamp)       |
| 9       | mtime       | time of last modification (Unix timestamp) |
| 10      | ctime       | time of last inode change (Unix timestamp) |
| 11      | blksize     | blocksize of filesystem IO \*\*            |
| 12      | blocks      | number of 512-byte blocks allocated \*\*   |

\* On Windows this will always be *0*.

\*\* Only valid on systems supporting the st\_blksize type - other
systems (e.g. Windows) return *-1*.

\*\*\* On Windows, as of PHP 7.4.0, this is the serial number of the
volume that contains the file, which is a 64-bit *unsigned* integer, so
may overflow. Previously, it was the numeric representation of the drive
letter (e.g. *2* for *C:*) for <span class="function">stat</span>, and
*0* for <span class="function">lstat</span>.

\*\*\*\* On Windows, as of PHP 7.4.0, this is the identifier associated
with the file, which is a 64-bit *unsigned* integer, so may overflow.
Previously, it was always *0*.

The value of *mode* contains information read by several functions. When
written in octal, starting from the right, the first three digits are
returned by <span class="function">chmod</span>. The next digit is
ignored by PHP. The next two digits indicate the file type:

| *mode* in octal | Meaning      |
|-----------------|--------------|
| **`0120000`**   | link         |
| **`0100000`**   | regular file |
| **`0060000`**   | block device |
| **`0040000`**   | directory    |
| **`0010000`**   | fifo         |

So for example a regular file could be **`0100644`** and a directory
could be **`0040755`**.

In case of error, <span class="function">stat</span> returns
**`FALSE`**.

> **Note**: <span class="simpara"> Because PHP's integer type is signed
> and many platforms use 32bit integers, some filesystem functions may
> return unexpected results for files which are larger than 2GB. </span>

### Errors/Exceptions

Upon failure, an **`E_WARNING`** is emitted.

### Changelog

| Version | Description                                                                                                                                                   |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | On Windows, the device number is now the serial number of the volume that contains the file, and the inode number is the identifier associated with the file. |
| 7.4.0   | The *size*, *atime*, *mtime* and *ctime* statistics of symlinks are always those of the target. This was previously not the case for NTS builds on Windows.   |

### Examples

**Example \#1 <span class="function">stat</span> example**

``` php
<?php
/* Get file stat */
$stat = stat('C:\php\php.exe');

/*
 * Print file access time, this is the same 
 * as calling fileatime()
 */
echo 'Access time: ' . $stat['atime'];

/*
 * Print file modification time, this is the 
 * same as calling filemtime()
 */
echo 'Modification time: ' . $stat['mtime'];

/* Print the device number */
echo 'Device number: ' . $stat['dev'];
?>
```

**Example \#2 Using <span class="function">stat</span> information
together with <span class="function">touch</span>**

``` php
<?php
/* Get file stat */
$stat = stat('C:\php\php.exe');

/* Did we failed to get stat information? */
if (!$stat) {
    echo 'stat() call failed...';
} else {
    /*
     * We want the access time to be 1 week 
     * after the current access time.
     */
    $atime = $stat['atime'] + 604800;

    /* Touch the file */
    if (!touch('some_file.txt', time(), $atime)) {
        echo 'Failed to touch file...';
    } else {
        echo 'touch() returned success...';
    }
}
?>
```

### Notes

> **Note**:
>
> Note that time resolution may differ from one file system to another.

> **Note**: <span class="simpara">The results of this function are
> cached. See <span class="function">clearstatcache</span> for more
> details.</span>

**Tip**

As of PHP 5.0.0, this function can also be used with *some* URL
wrappers. Refer to
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
to determine which wrappers support <span class="function">stat</span>
family of functionality.

### See Also

-   <span class="function">lstat</span>
-   <span class="function">fstat</span>
-   <span class="function">filemtime</span>
-   <span class="function">filegroup</span>

symlink
=======

Creates a symbolic link

### Description

<span class="type">bool</span> <span class="methodname">symlink</span> (
<span class="methodparam"><span class="type">string</span>
`$target`</span> , <span class="methodparam"><span
class="type">string</span> `$link`</span> )

<span class="function">symlink</span> creates a symbolic link to the
existing `target` with the specified name `link`.

### Parameters

`target`  
Target of the link.

`link`  
The link name.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Create a symbolic link**

``` php
<?php
$target = 'uploads.php';
$link = 'uploads';
symlink($target, $link);

echo readlink($link);
?>
```

### Notes

> **Note**: <span class="simpara"> Windows users should note that this
> function will only work if the system you run PHP from is Windows
> Vista/Windows Server 2008 or newer. Windows versions prior to that do
> not support symbolic links. </span>

### See Also

-   <span class="function">link</span>
-   <span class="function">readlink</span>
-   <span class="function">linkinfo</span>

tempnam
=======

Create file with unique file name

### Description

<span class="type">string</span> <span class="methodname">tempnam</span>
( <span class="methodparam"><span class="type">string</span>
`$dir`</span> , <span class="methodparam"><span
class="type">string</span> `$prefix`</span> )

Creates a file with a unique filename, with access permission set to
0600, in the specified directory. If the directory does not exist or is
not writable, <span class="function">tempnam</span> may generate a file
in the system's temporary directory, and return the full path to that
file, including its name.

### Parameters

`dir`  
The directory where the temporary filename will be created.

`prefix`  
The prefix of the generated temporary filename.

> **Note**: <span class="simpara"> Only the first 63 characters of the
> prefix are used. Windows even uses only the first three characters of
> the prefix. </span>

### Return Values

Returns the new temporary filename (with path), or **`FALSE`** on
failure.

### Examples

**Example \#1 <span class="function">tempnam</span> example**

``` php
<?php
$tmpfname = tempnam("/tmp", "FOO");

$handle = fopen($tmpfname, "w");
fwrite($handle, "writing to tempfile");
fclose($handle);

// do here something

unlink($tmpfname);
?>
```

### Notes

> **Note**: <span class="simpara"> If PHP cannot create a file in the
> specified `dir` parameter, it falls back on the system default. On
> NTFS this also happens if the specified `dir` contains more than 65534
> files. </span>

### See Also

-   <span class="function">tmpfile</span>
-   <span class="function">sys\_get\_temp\_dir</span>
-   <span class="function">unlink</span>

tmpfile
=======

Creates a temporary file

### Description

<span class="type">resource</span> <span
class="methodname">tmpfile</span> ( <span
class="methodparam">void</span> )

Creates a temporary file with a unique name in read-write (w+) mode and
returns a file handle.

The file is automatically removed when closed (for example, by calling
<span class="function">fclose</span>, or when there are no remaining
references to the file handle returned by <span
class="function">tmpfile</span>), or when the script ends.

**Caution**

If the script terminates unexpectedly, the temporary file may not be
deleted.

### Return Values

Returns a file handle, similar to the one returned by <span
class="function">fopen</span>, for the new file or **`FALSE`** on
failure.

### Examples

**Example \#1 <span class="function">tmpfile</span> example**

``` php
<?php
$temp = tmpfile();
fwrite($temp, "writing to tempfile");
fseek($temp, 0);
echo fread($temp, 1024);
fclose($temp); // this removes the file
?>
```

The above example will output:

    writing to tempfile

### See Also

-   <span class="function">tempnam</span>
-   <span class="function">sys\_get\_temp\_dir</span>

touch
=====

Sets access and modification time of file

### Description

<span class="type">bool</span> <span class="methodname">touch</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> \[, <span class="methodparam"><span
class="type">int</span> `$time`<span class="initializer"> =
time()</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$atime`</span> \]\] )

Attempts to set the access and modification times of the file named in
the `filename` parameter to the value given in `time`. Note that the
access time is always modified, regardless of the number of parameters.

If the file does not exist, it will be created.

### Parameters

`filename`  
The name of the file being touched.

`time`  
The touch time. If `time` is not supplied, the current system time is
used.

`atime`  
If present, the access time of the given filename is set to the value of
`atime`. Otherwise, it is set to the value passed to the `time`
parameter. If neither are present, the current system time is used.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">touch</span> example**

``` php
<?php
if (touch($filename)) {
    echo $filename . ' modification time has been changed to present time';
} else {
    echo 'Sorry, could not change modification time of ' . $filename;
}
?>
```

**Example \#2 <span class="function">touch</span> using the `time`
parameter**

``` php
<?php
// This is the touch time, we'll set it to one hour in the past.
$time = time() - 3600;

// Touch the file
if (!touch('some_file.txt', $time)) {
    echo 'Whoops, something went wrong...';
} else {
    echo 'Touched file with success';
}
?>
```

### Notes

> **Note**:
>
> Note that time resolution may differ from one file system to another.

**Warning**

Prior to PHP 5.3.0 it was not possible to change the modification time
of a directory with this function under Windows.

umask
=====

Changes the current umask

### Description

<span class="type">int</span> <span class="methodname">umask</span> (\[
<span class="methodparam"><span class="type">int</span> `$mask`</span>
\] )

<span class="function">umask</span> sets PHP's umask to `mask` & 0777
and returns the old umask. When PHP is being used as a server module,
the umask is restored when each request is finished.

### Parameters

`mask`  
The new umask.

### Return Values

<span class="function">umask</span> without arguments simply returns the
current umask otherwise the old umask is returned.

### Examples

**Example \#1 <span class="function">umask</span> example**

``` php
<?php
$old = umask(0);
chmod("/path/some_dir/some_file.txt", 0755);
umask($old);

// Checking
if ($old != umask()) {
    die('An error occurred while changing back the umask');
}
?>
```

### Notes

> **Note**:
>
> Avoid using this function in multithreaded webservers. It is better to
> change the file permissions with <span class="function">chmod</span>
> after creating the file. Using <span class="function">umask</span> can
> lead to unexpected behavior of concurrently running scripts and the
> webserver itself because they all use the same umask.

unlink
======

Deletes a file

### Description

<span class="type">bool</span> <span class="methodname">unlink</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \] )

Deletes `filename`. Similar to the Unix C unlink() function. An
**`E_WARNING`** level error will be generated on failure.

### Parameters

`filename`  
Path to the file.

`context`  
> **Note**: <span class="simpara">Context support was added with PHP
> 5.0.0. For a description of *contexts*, refer to
> <a href="/book/stream.html" class="xref">Streams</a>.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                                                                   |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | On Windows, it is now possible to <span class="function">unlink</span> files with handles in use, while formerly that would fail. However, it is still not possible to re-create the unlinked file, until all handles to it have been closed. |

### Examples

**Example \#1 Basic <span class="function">unlink</span> usage**

``` php
<?php
$fh = fopen('test.html', 'a');
fwrite($fh, '<h1>Hello world!</h1>');
fclose($fh);

unlink('test.html');
?>
```

### See Also

-   <span class="function">rmdir</span>

**Table of Contents**

-   [basename](/ref/filesystem.html#basename) — Returns trailing name
    component of path
-   [chgrp](/ref/filesystem.html#chgrp) — Changes file group
-   [chmod](/ref/filesystem.html#chmod) — Changes file mode
-   [chown](/ref/filesystem.html#chown) — Changes file owner
-   [clearstatcache](/ref/filesystem.html#clearstatcache) — Clears file
    status cache
-   [copy](/ref/filesystem.html#copy) — Copies file
-   [delete](/ref/filesystem.html#delete) — See unlink or unset
-   [dirname](/ref/filesystem.html#dirname) — Returns a parent
    directory's path
-   [disk\_free\_space](/ref/filesystem.html#disk_free_space) — Returns
    available space on filesystem or disk partition
-   [disk\_total\_space](/ref/filesystem.html#disk_total_space) —
    Returns the total size of a filesystem or disk partition
-   [diskfreespace](/ref/filesystem.html#diskfreespace) — Alias of
    disk\_free\_space
-   [fclose](/ref/filesystem.html#fclose) — Closes an open file pointer
-   [feof](/ref/filesystem.html#feof) — Tests for end-of-file on a file
    pointer
-   [fflush](/ref/filesystem.html#fflush) — Flushes the output to a file
-   [fgetc](/ref/filesystem.html#fgetc) — Gets character from file
    pointer
-   [fgetcsv](/ref/filesystem.html#fgetcsv) — Gets line from file
    pointer and parse for CSV fields
-   [fgets](/ref/filesystem.html#fgets) — Gets line from file pointer
-   [fgetss](/ref/filesystem.html#fgetss) — Gets line from file pointer
    and strip HTML tags
-   [file\_exists](/ref/filesystem.html#file_exists) — Checks whether a
    file or directory exists
-   [file\_get\_contents](/ref/filesystem.html#file_get_contents) —
    Reads entire file into a string
-   [file\_put\_contents](/ref/filesystem.html#file_put_contents) —
    Write data to a file
-   [file](/ref/filesystem.html#file) — Reads entire file into an array
-   [fileatime](/ref/filesystem.html#fileatime) — Gets last access time
    of file
-   [filectime](/ref/filesystem.html#filectime) — Gets inode change time
    of file
-   [filegroup](/ref/filesystem.html#filegroup) — Gets file group
-   [fileinode](/ref/filesystem.html#fileinode) — Gets file inode
-   [filemtime](/ref/filesystem.html#filemtime) — Gets file modification
    time
-   [fileowner](/ref/filesystem.html#fileowner) — Gets file owner
-   [fileperms](/ref/filesystem.html#fileperms) — Gets file permissions
-   [filesize](/ref/filesystem.html#filesize) — Gets file size
-   [filetype](/ref/filesystem.html#filetype) — Gets file type
-   [flock](/ref/filesystem.html#flock) — Portable advisory file locking
-   [fnmatch](/ref/filesystem.html#fnmatch) — Match filename against a
    pattern
-   [fopen](/ref/filesystem.html#fopen) — Opens file or URL
-   [fpassthru](/ref/filesystem.html#fpassthru) — Output all remaining
    data on a file pointer
-   [fputcsv](/ref/filesystem.html#fputcsv) — Format line as CSV and
    write to file pointer
-   [fputs](/ref/filesystem.html#fputs) — Alias of fwrite
-   [fread](/ref/filesystem.html#fread) — Binary-safe file read
-   [fscanf](/ref/filesystem.html#fscanf) — Parses input from a file
    according to a format
-   [fseek](/ref/filesystem.html#fseek) — Seeks on a file pointer
-   [fstat](/ref/filesystem.html#fstat) — Gets information about a file
    using an open file pointer
-   [ftell](/ref/filesystem.html#ftell) — Returns the current position
    of the file read/write pointer
-   [ftruncate](/ref/filesystem.html#ftruncate) — Truncates a file to a
    given length
-   [fwrite](/ref/filesystem.html#fwrite) — Binary-safe file write
-   [glob](/ref/filesystem.html#glob) — Find pathnames matching a
    pattern
-   [is\_dir](/ref/filesystem.html#is_dir) — Tells whether the filename
    is a directory
-   [is\_executable](/ref/filesystem.html#is_executable) — Tells whether
    the filename is executable
-   [is\_file](/ref/filesystem.html#is_file) — Tells whether the
    filename is a regular file
-   [is\_link](/ref/filesystem.html#is_link) — Tells whether the
    filename is a symbolic link
-   [is\_readable](/ref/filesystem.html#is_readable) — Tells whether a
    file exists and is readable
-   [is\_uploaded\_file](/ref/filesystem.html#is_uploaded_file) — Tells
    whether the file was uploaded via HTTP POST
-   [is\_writable](/ref/filesystem.html#is_writable) — Tells whether the
    filename is writable
-   [is\_writeable](/ref/filesystem.html#is_writeable) — Alias of
    is\_writable
-   [lchgrp](/ref/filesystem.html#lchgrp) — Changes group ownership of
    symlink
-   [lchown](/ref/filesystem.html#lchown) — Changes user ownership of
    symlink
-   [link](/ref/filesystem.html#link) — Create a hard link
-   [linkinfo](/ref/filesystem.html#linkinfo) — Gets information about a
    link
-   [lstat](/ref/filesystem.html#lstat) — Gives information about a file
    or symbolic link
-   [mkdir](/ref/filesystem.html#mkdir) — Makes directory
-   [move\_uploaded\_file](/ref/filesystem.html#move_uploaded_file) —
    Moves an uploaded file to a new location
-   [parse\_ini\_file](/ref/filesystem.html#parse_ini_file) — Parse a
    configuration file
-   [parse\_ini\_string](/ref/filesystem.html#parse_ini_string) — Parse
    a configuration string
-   [pathinfo](/ref/filesystem.html#pathinfo) — Returns information
    about a file path
-   [pclose](/ref/filesystem.html#pclose) — Closes process file pointer
-   [popen](/ref/filesystem.html#popen) — Opens process file pointer
-   [readfile](/ref/filesystem.html#readfile) — Outputs a file
-   [readlink](/ref/filesystem.html#readlink) — Returns the target of a
    symbolic link
-   [realpath\_cache\_get](/ref/filesystem.html#realpath_cache_get) —
    Get realpath cache entries
-   [realpath\_cache\_size](/ref/filesystem.html#realpath_cache_size) —
    Get realpath cache size
-   [realpath](/ref/filesystem.html#realpath) — Returns canonicalized
    absolute pathname
-   [rename](/ref/filesystem.html#rename) — Renames a file or directory
-   [rewind](/ref/filesystem.html#rewind) — Rewind the position of a
    file pointer
-   [rmdir](/ref/filesystem.html#rmdir) — Removes directory
-   [set\_file\_buffer](/ref/filesystem.html#set_file_buffer) — Alias of
    stream\_set\_write\_buffer
-   [stat](/ref/filesystem.html#stat) — Gives information about a file
-   [symlink](/ref/filesystem.html#symlink) — Creates a symbolic link
-   [tempnam](/ref/filesystem.html#tempnam) — Create file with unique
    file name
-   [tmpfile](/ref/filesystem.html#tmpfile) — Creates a temporary file
-   [touch](/ref/filesystem.html#touch) — Sets access and modification
    time of file
-   [umask](/ref/filesystem.html#umask) — Changes the current umask
-   [unlink](/ref/filesystem.html#unlink) — Deletes a file

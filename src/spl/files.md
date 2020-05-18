File Handling
=============

**Table of Contents**

-   [SplFileInfo](/spl/files.html#SplFileInfo) — The SplFileInfo class
    -   [SplFileInfo::\_\_construct](/spl/files.html#SplFileInfo::__construct)
        — Construct a new SplFileInfo object
    -   [SplFileInfo::getATime](/spl/files.html#SplFileInfo::getATime) —
        Gets last access time of the file
    -   [SplFileInfo::getBasename](/spl/files.html#SplFileInfo::getBasename)
        — Gets the base name of the file
    -   [SplFileInfo::getCTime](/spl/files.html#SplFileInfo::getCTime) —
        Gets the inode change time
    -   [SplFileInfo::getExtension](/spl/files.html#SplFileInfo::getExtension)
        — Gets the file extension
    -   [SplFileInfo::getFileInfo](/spl/files.html#SplFileInfo::getFileInfo)
        — Gets an SplFileInfo object for the file
    -   [SplFileInfo::getFilename](/spl/files.html#SplFileInfo::getFilename)
        — Gets the filename
    -   [SplFileInfo::getGroup](/spl/files.html#SplFileInfo::getGroup) —
        Gets the file group
    -   [SplFileInfo::getInode](/spl/files.html#SplFileInfo::getInode) —
        Gets the inode for the file
    -   [SplFileInfo::getLinkTarget](/spl/files.html#SplFileInfo::getLinkTarget)
        — Gets the target of a link
    -   [SplFileInfo::getMTime](/spl/files.html#SplFileInfo::getMTime) —
        Gets the last modified time
    -   [SplFileInfo::getOwner](/spl/files.html#SplFileInfo::getOwner) —
        Gets the owner of the file
    -   [SplFileInfo::getPath](/spl/files.html#SplFileInfo::getPath) —
        Gets the path without filename
    -   [SplFileInfo::getPathInfo](/spl/files.html#SplFileInfo::getPathInfo)
        — Gets an SplFileInfo object for the path
    -   [SplFileInfo::getPathname](/spl/files.html#SplFileInfo::getPathname)
        — Gets the path to the file
    -   [SplFileInfo::getPerms](/spl/files.html#SplFileInfo::getPerms) —
        Gets file permissions
    -   [SplFileInfo::getRealPath](/spl/files.html#SplFileInfo::getRealPath)
        — Gets absolute path to file
    -   [SplFileInfo::getSize](/spl/files.html#SplFileInfo::getSize) —
        Gets file size
    -   [SplFileInfo::getType](/spl/files.html#SplFileInfo::getType) —
        Gets file type
    -   [SplFileInfo::isDir](/spl/files.html#SplFileInfo::isDir) — Tells
        if the file is a directory
    -   [SplFileInfo::isExecutable](/spl/files.html#SplFileInfo::isExecutable)
        — Tells if the file is executable
    -   [SplFileInfo::isFile](/spl/files.html#SplFileInfo::isFile) —
        Tells if the object references a regular file
    -   [SplFileInfo::isLink](/spl/files.html#SplFileInfo::isLink) —
        Tells if the file is a link
    -   [SplFileInfo::isReadable](/spl/files.html#SplFileInfo::isReadable)
        — Tells if file is readable
    -   [SplFileInfo::isWritable](/spl/files.html#SplFileInfo::isWritable)
        — Tells if the entry is writable
    -   [SplFileInfo::openFile](/spl/files.html#SplFileInfo::openFile) —
        Gets an SplFileObject object for the file
    -   [SplFileInfo::setFileClass](/spl/files.html#SplFileInfo::setFileClass)
        — Sets the class used with SplFileInfo::openFile
    -   [SplFileInfo::setInfoClass](/spl/files.html#SplFileInfo::setInfoClass)
        — Sets the class used with SplFileInfo::getFileInfo and
        SplFileInfo::getPathInfo
    -   [SplFileInfo::\_\_toString](/spl/files.html#SplFileInfo::__toString)
        — Returns the path to the file as a string
-   [SplFileObject](/spl/files.html#SplFileObject) — The SplFileObject
    class
    -   [SplFileObject::\_\_construct](/spl/files.html#SplFileObject::__construct)
        — Construct a new file object
    -   [SplFileObject::current](/spl/files.html#SplFileObject::current)
        — Retrieve current line of file
    -   [SplFileObject::eof](/spl/files.html#SplFileObject::eof) —
        Reached end of file
    -   [SplFileObject::fflush](/spl/files.html#SplFileObject::fflush) —
        Flushes the output to the file
    -   [SplFileObject::fgetc](/spl/files.html#SplFileObject::fgetc) —
        Gets character from file
    -   [SplFileObject::fgetcsv](/spl/files.html#SplFileObject::fgetcsv)
        — Gets line from file and parse as CSV fields
    -   [SplFileObject::fgets](/spl/files.html#SplFileObject::fgets) —
        Gets line from file
    -   [SplFileObject::fgetss](/spl/files.html#SplFileObject::fgetss) —
        Gets line from file and strip HTML tags
    -   [SplFileObject::flock](/spl/files.html#SplFileObject::flock) —
        Portable file locking
    -   [SplFileObject::fpassthru](/spl/files.html#SplFileObject::fpassthru)
        — Output all remaining data on a file pointer
    -   [SplFileObject::fputcsv](/spl/files.html#SplFileObject::fputcsv)
        — Write a field array as a CSV line
    -   [SplFileObject::fread](/spl/files.html#SplFileObject::fread) —
        Read from file
    -   [SplFileObject::fscanf](/spl/files.html#SplFileObject::fscanf) —
        Parses input from file according to a format
    -   [SplFileObject::fseek](/spl/files.html#SplFileObject::fseek) —
        Seek to a position
    -   [SplFileObject::fstat](/spl/files.html#SplFileObject::fstat) —
        Gets information about the file
    -   [SplFileObject::ftell](/spl/files.html#SplFileObject::ftell) —
        Return current file position
    -   [SplFileObject::ftruncate](/spl/files.html#SplFileObject::ftruncate)
        — Truncates the file to a given length
    -   [SplFileObject::fwrite](/spl/files.html#SplFileObject::fwrite) —
        Write to file
    -   [SplFileObject::getChildren](/spl/files.html#SplFileObject::getChildren)
        — No purpose
    -   [SplFileObject::getCsvControl](/spl/files.html#SplFileObject::getCsvControl)
        — Get the delimiter, enclosure and escape character for CSV
    -   [SplFileObject::getCurrentLine](/spl/files.html#SplFileObject::getCurrentLine)
        — Alias of SplFileObject::fgets
    -   [SplFileObject::getFlags](/spl/files.html#SplFileObject::getFlags)
        — Gets flags for the SplFileObject
    -   [SplFileObject::getMaxLineLen](/spl/files.html#SplFileObject::getMaxLineLen)
        — Get maximum line length
    -   [SplFileObject::hasChildren](/spl/files.html#SplFileObject::hasChildren)
        — SplFileObject does not have children
    -   [SplFileObject::key](/spl/files.html#SplFileObject::key) — Get
        line number
    -   [SplFileObject::next](/spl/files.html#SplFileObject::next) —
        Read next line
    -   [SplFileObject::rewind](/spl/files.html#SplFileObject::rewind) —
        Rewind the file to the first line
    -   [SplFileObject::seek](/spl/files.html#SplFileObject::seek) —
        Seek to specified line
    -   [SplFileObject::setCsvControl](/spl/files.html#SplFileObject::setCsvControl)
        — Set the delimiter, enclosure and escape character for CSV
    -   [SplFileObject::setFlags](/spl/files.html#SplFileObject::setFlags)
        — Sets flags for the SplFileObject
    -   [SplFileObject::setMaxLineLen](/spl/files.html#SplFileObject::setMaxLineLen)
        — Set maximum line length
    -   [SplFileObject::\_\_toString](/spl/files.html#SplFileObject::__toString)
        — Alias of SplFileObject::fgets
    -   [SplFileObject::valid](/spl/files.html#SplFileObject::valid) —
        Not at EOF
-   [SplTempFileObject](/spl/files.html#SplTempFileObject) — The
    SplTempFileObject class
    -   [SplTempFileObject::\_\_construct](/spl/files.html#SplTempFileObject::__construct)
        — Construct a new temporary file object

SPL provides a number of classes to work with files.

Introduction
------------

The SplFileInfo class offers a high-level object oriented interface to
information for an individual file.

Class synopsis
--------------

**SplFileInfo**

<span class="ooclass"> class **SplFileInfo** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$file_name`</span>
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getATime</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getBasename</span> (\[ <span
class="methodparam"><span class="type">string</span> `$suffix`</span> \]
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getCTime</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getExtension</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SplFileInfo</span> <span
class="methodname">getFileInfo</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFilename</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getGroup</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getInode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getLinkTarget</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMTime</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getOwner</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SplFileInfo</span> <span
class="methodname">getPathInfo</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getPathname</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getPerms</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getRealPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isDir</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isExecutable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isLink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isReadable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isWritable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SplFileObject</span> <span
class="methodname">openFile</span> (\[ <span class="methodparam"><span
class="type">string</span> `$open_mode`<span class="initializer"> =
"r"</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`<span class="initializer"> =
**`NULL`**</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setFileClass</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "SplFileObject"</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setInfoClass</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "SplFileInfo"</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

SplFileInfo::\_\_construct
==========================

Construct a new SplFileInfo object

### Description

<span class="modifier">public</span> <span
class="methodname">SplFileInfo::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$file_name`</span>
)

Creates a new SplFileInfo object for the file\_name specified. The file
does not need to exist, or be readable.

### Parameters

`file_name`  
Path to the file.

### Examples

**Example \#1 <span class="function">SplFileInfo::\_\_construct</span>
example**

``` php
<?php
$info = new SplFileInfo('example.php');
if ($info->isFile()) {
    echo $info->getRealPath();
}
?>
```

SplFileInfo::getATime
=====================

Gets last access time of the file

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getATime</span> ( <span
class="methodparam">void</span> )

Gets the last access time for the file.

### Parameters

This function has no parameters.

### Return Values

Returns the time the file was last accessed.

### Errors/Exceptions

Throws <span class="classname">RunTimeException</span> on error.

### See Also

-   <span class="function">fileatime</span>

SplFileInfo::getBasename
========================

Gets the base name of the file

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getBasename</span> (\[ <span
class="methodparam"><span class="type">string</span> `$suffix`</span> \]
)

This method returns the base name of the file, directory, or link
without path info.

**Caution**

<span class="function">SplFileInfo::getBasename</span> is locale aware,
so for it to see the correct basename with multibyte character paths,
the matching locale must be set using the <span
class="function">setlocale</span> function.

### Parameters

`suffix`  
Optional suffix to omit from the base name returned.

### Return Values

Returns the base name without path information.

### Examples

**Example \#1 <span class="function">SplFileInfo::getBasename</span>
example**

``` php
<?php
$info = new SplFileInfo('file.txt');
var_dump($info->getBasename());

$info = new SplFileInfo('/path/to/file.txt');
var_dump($info->getBasename());

$info = new SplFileInfo('/path/to/file.txt');
var_dump($info->getBasename('.txt'));
?>
```

The above example will output something similar to:

    string(8) "file.txt"
    string(8) "file.txt"
    string(4) "file" 

### See Also

-   <span class="methodname">SplFileInfo::getFilename</span>

SplFileInfo::getCTime
=====================

Gets the inode change time

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getCTime</span> ( <span
class="methodparam">void</span> )

Returns the inode change time for the file. The time returned is a Unix
timestamp.

### Parameters

This function has no parameters.

### Return Values

The last change time, in a Unix timestamp.

### Errors/Exceptions

Throws <span class="classname">RunTimeException</span> on error.

### Examples

**Example \#1 <span class="function">SplFileInfo::getCTime</span>
example**

``` php
<?php
$info = new SplFileInfo(__FILE__);
echo 'Last changed at ' . date('g:i a', $info->getCTime());
?>
```

The above example will output something similar to:

    Last changed at 1:49 pm

### See Also

-   <span class="function">filectime</span>

SplFileInfo::getExtension
=========================

Gets the file extension

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getExtension</span> ( <span
class="methodparam">void</span> )

Retrieves the file extension.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="type">string</span> containing the file
extension, or an empty <span class="type">string</span> if the file has
no extension.

### Examples

**Example \#1 <span class="function">SplFileInfo::getExtension</span>
example**

``` php
<?php

$info = new SplFileInfo('foo.txt');
var_dump($info->getExtension());

$info = new SplFileInfo('photo.jpg');
var_dump($info->getExtension());

$info = new SplFileInfo('something.tar.gz');
var_dump($info->getExtension());

?>
```

The above example will output:

    string(3) "txt"
    string(3) "jpg"
    string(2) "gz"

### Notes

> **Note**:
>
> This method is only available as of PHP 5.3.6. Another way of getting
> the extension is to use the <span class="function">pathinfo</span>
> function.
>
> ``` php
> <?php
> $extension = pathinfo($info->getFilename(), PATHINFO_EXTENSION);
> ?>
> ```

### See Also

-   <span class="methodname">SplFileInfo::getFilename</span>
-   <span class="methodname">SplFileInfo::getBasename</span>
-   <span class="function">pathinfo</span>

SplFileInfo::getFileInfo
========================

Gets an SplFileInfo object for the file

### Description

<span class="modifier">public</span> <span
class="type">SplFileInfo</span> <span
class="methodname">SplFileInfo::getFileInfo</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> \] )

This method gets an <span class="classname">SplFileInfo</span> object
for the referenced file.

### Parameters

`class_name`  
Name of an <span class="classname">SplFileInfo</span> derived class to
use.

### Return Values

An <span class="classname">SplFileInfo</span> object created for the
file.

### See Also

-   <span class="methodname">SplFileInfo::setInfoClass</span>

SplFileInfo::getFilename
========================

Gets the filename

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getFilename</span> ( <span
class="methodparam">void</span> )

Gets the filename without any path information.

### Parameters

This function has no parameters.

### Return Values

The filename.

### Examples

**Example \#1 <span class="function">SplFileInfo::getFilename</span>
example**

``` php
<?php
$info = new SplFileInfo('foo.txt');
var_dump($info->getFilename());

$info = new SplFileInfo('/path/to/foo.txt');
var_dump($info->getFilename());

$info = new SplFileInfo('http://www.php.net/');
var_dump($info->getFilename());

$info = new SplFileInfo('http://www.php.net/svn.php');
var_dump($info->getFilename());
?>
```

The above example will output something similar to:

    string(7) "foo.txt"
    string(7) "foo.txt"
    string(0) ""
    string(7) "svn.php" 

### See Also

-   <span class="methodname">SplFileInfo::getBasename</span>

SplFileInfo::getGroup
=====================

Gets the file group

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getGroup</span> ( <span
class="methodparam">void</span> )

Gets the file group. The group ID is returned in numerical format.

### Parameters

This function has no parameters.

### Return Values

The group id in numerical format.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> on error.

### Examples

**Example \#1 <span class="function">SplFileInfo::getGroup</span>
example**

``` php
<?php
$info = new SplFileInfo(__FILE__);
print_r(posix_getgrgid($info->getGroup()));
?>
```

The above example will output something similar to:

### See Also

-   <span class="function">posix\_getgrgid</span>

SplFileInfo::getInode
=====================

Gets the inode for the file

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getInode</span> ( <span
class="methodparam">void</span> )

Gets the inode number for the filesystem object.

### Parameters

This function has no parameters.

### Return Values

Returns the inode number for the filesystem object.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> on error.

### See Also

-   <span class="function">fileinode</span>

SplFileInfo::getLinkTarget
==========================

Gets the target of a link

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getLinkTarget</span> ( <span
class="methodparam">void</span> )

Gets the target of a filesystem link.

> **Note**:
>
> The target may not be the real path on the filesystem. Use <span
> class="methodname">SplFileInfo::getRealPath</span> to determine the
> true path on the filesystem.

### Parameters

This function has no parameters.

### Return Values

Returns the target of the filesystem link.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> on error.

### Examples

**Example \#1 <span class="function">SplFileInfo::getLinkTarget</span>
example**

``` php
<?php
$info = new SplFileInfo('/Users/bbieber/workspace');
if ($info->isLink()) {
    var_dump($info->getLinkTarget());
    var_dump($info->getRealPath());
}
?>
```

The above example will output something similar to:

    string(19) "Documents/workspace"
    string(34) "/Users/bbieber/Documents/workspace"

### See Also

-   <span class="methodname">SplFileInfo::isLink</span>
-   <span class="methodname">SplFileInfo::getRealPath</span>

SplFileInfo::getMTime
=====================

Gets the last modified time

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getMTime</span> ( <span
class="methodparam">void</span> )

Returns the time when the contents of the file were changed. The time
returned is a Unix timestamp.

### Parameters

This function has no parameters.

### Return Values

Returns the last modified time for the file, in a Unix timestamp.

### See Also

-   <span class="function">filemtime</span>

SplFileInfo::getOwner
=====================

Gets the owner of the file

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getOwner</span> ( <span
class="methodparam">void</span> )

Gets the file owner. The owner ID is returned in numerical format.

### Parameters

This function has no parameters.

### Return Values

The owner id in numerical format.

### Errors/Exceptions

Throws <span class="classname">RuntimeException</span> on error.

### Examples

**Example \#1 <span class="function">SplFileInfo::getOwner</span>
example**

``` php
<?php
$info = new SplFileInfo('file.txt');
print_r(posix_getpwuid($info->getOwner()));
?>
```

### See Also

-   <span class="function">posix\_getpwuid</span>
-   <span class="methodname">SplFileInfo::getGroup</span>

SplFileInfo::getPath
====================

Gets the path without filename

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getPath</span> ( <span
class="methodparam">void</span> )

Returns the path to the file, omitting the filename and any trailing
slash.

### Parameters

This function has no parameters.

### Return Values

Returns the path to the file.

### Examples

**Example \#1 <span class="function">SplFileInfo::getPath</span>
example**

``` php
<?php
$info = new SplFileInfo('/usr/bin/php');
var_dump($info->getPath());


$info = new SplFileInfo('/usr/');
var_dump($info->getPath());?>
```

The above example will output something similar to:

    string(8) "/usr/bin"
    string(4) "/usr"

### See Also

-   <span class="methodname">SplFileInfo::getRealPath</span>
-   <span class="methodname">SplFileInfo::getFilename</span>
-   <span class="methodname">SplFileInfo::getPathInfo</span>

SplFileInfo::getPathInfo
========================

Gets an SplFileInfo object for the path

### Description

<span class="modifier">public</span> <span
class="type">SplFileInfo</span> <span
class="methodname">SplFileInfo::getPathInfo</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> \] )

Gets an <span class="classname">SplFileInfo</span> object for the parent
of the current file.

### Parameters

`class_name`  
Name of an <span class="classname">SplFileInfo</span> derived class to
use.

### Return Values

Returns an <span class="classname">SplFileInfo</span> object for the
parent path of the file.

### Examples

**Example \#1 <span class="function">SplFileInfo::getPathInfo</span>
example**

``` php
<?php
$info = new SplFileInfo('/usr/bin/php');
$parent_info = $info->getPathInfo();
var_dump($parent_info->getRealPath());
?>
```

The above example will output something similar to:

    string(8) "/usr/bin"

### See Also

-   <span class="methodname">SplFileInfo::setInfoClass</span>

SplFileInfo::getPathname
========================

Gets the path to the file

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getPathname</span> ( <span
class="methodparam">void</span> )

Returns the path to the file.

### Parameters

This function has no parameters.

### Return Values

The path to the file.

### Examples

**Example \#1 <span class="function">SplFileInfo::getPathname</span>
example**

``` php
<?php
$info = new SplFileInfo('/usr/bin/php');
var_dump($info->getPathname());
?>
```

The above example will output something similar to:

    string(12) "/usr/bin/php"

### See Also

-   <span class="methodname">SplFileInfo::getRealPath</span>

SplFileInfo::getPerms
=====================

Gets file permissions

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getPerms</span> ( <span
class="methodparam">void</span> )

Gets the file permissions for the file.

### Parameters

This function has no parameters.

### Return Values

Returns the file permissions.

### Examples

**Example \#1 <span class="function">SplFileInfo::getPerms</span>
example**

``` php
<?php
$info = new SplFileInfo('/tmp');
echo substr(sprintf('%o', $info->getPerms()), -4);

$info = new SplFileInfo(__FILE__);
echo substr(sprintf('%o', $info->getPerms()), -4);
?>
```

The above example will output something similar to:

    1777
    0644

SplFileInfo::getRealPath
========================

Gets absolute path to file

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getRealPath</span> ( <span
class="methodparam">void</span> )

This method expands all symbolic links, resolves relative references and
returns the real path to the file.

### Parameters

This function has no parameters.

### Return Values

Returns the path to the file, or **`FALSE`** if the file does not exist.

### Examples

**Example \#1 <span class="function">SplFileInfo::getRealPath</span>
example**

``` php
<?php
$info = new SplFileInfo('/..//./../../'.__FILE__);
var_dump($info->getRealPath());

$info = new SplFileInfo('/tmp');
var_dump($info->getRealPath());

$info = new SplFileInfo('/I/Do/Not/Exist');
var_dump($info->getRealPath());

$info = new SplFileInfo('php://output');
var_dump($info->getRealPath());

$info = new SplFileInfo("");
var_dump($info->getRealPath());
?>
```

The above example will output something similar to:

    string(28) "/private/tmp/phptempfile.php" 
    string(12) "/private/tmp"
    bool(false)
    bool(false)
    string(12) "/private/tmp" 

### See Also

-   <span class="methodname">SplFileInfo::isLink</span>
-   <span class="methodname">realpath</span>

SplFileInfo::getSize
====================

Gets file size

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getSize</span> ( <span
class="methodparam">void</span> )

Returns the filesize in bytes for the file referenced.

### Parameters

This function has no parameters.

### Return Values

The filesize in bytes.

### Errors/Exceptions

A <span class="classname">RuntimeException</span> will be thrown if the
file does not exist or an error occurs.

### See Also

-   <span class="function">filesize</span>

SplFileInfo::getType
====================

Gets file type

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getType</span> ( <span
class="methodparam">void</span> )

Returns the type of the file referenced.

### Parameters

This function has no parameters.

### Return Values

A <span class="type">string</span> representing the type of the entry.
May be one of *file*, *link*, or *dir*

### Errors/Exceptions

Throws a <span class="classname">RuntimeException</span> on error.

### Examples

**Example \#1 <span class="function">SplFileInfo::getType</span>
example**

``` php
<?php

$info = new SplFileInfo(__FILE__);
echo $info->getType().PHP_EOL;

$info = new SplFileInfo(dirname(__FILE__));
echo $info->getType();

?>
```

The above example will output something similar to:

    file
    dir

SplFileInfo::isDir
==================

Tells if the file is a directory

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isDir</span> ( <span
class="methodparam">void</span> )

This method can be used to determine if the file is a directory.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if a directory, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">SplFileInfo::isDir</span> example**

``` php
<?php
$d = new SplFileInfo(dirname(__FILE__));
var_dump($d->isDir());

$d = new SplFileInfo(__FILE__);
var_dump($d->isDir());
?>
```

The above example will output something similar to:

    bool(true)
    bool(false)

SplFileInfo::isExecutable
=========================

Tells if the file is executable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isExecutable</span> ( <span
class="methodparam">void</span> )

Checks if the file is executable.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if executable, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">SplFileInfo::isExecutable</span>
example**

``` php
<?php
$info = new SplFileInfo('/usr/bin/php');
var_dump($info->isExecutable()); 

$info = new SplFileInfo('/usr/bin');
var_dump($info->isExecutable());

$info = new SplFileInfo('foo');
var_dump($info->isExecutable());
?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(false)

SplFileInfo::isFile
===================

Tells if the object references a regular file

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isFile</span> ( <span
class="methodparam">void</span> )

Checks if the file referenced by this SplFileInfo object exists and is a
regular file.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the file exists and is a regular file (not a
link), **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">SplFileInfo::isFile</span>
example**

``` php
<?php
$info = new SplFileInfo(__FILE__);
var_dump($info->isFile());

$info = new SplFileInfo(dirname(__FILE__));
var_dump($info->isFile());
?>
```

The above example will output something similar to:

    bool(true)
    bool(false)

SplFileInfo::isLink
===================

Tells if the file is a link

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isLink</span> ( <span
class="methodparam">void</span> )

Use this method to check if the file referenced by the SplFileInfo
object is a link.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the file is a link, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">SplFileInfo::isLink</span>
example**

``` php
<?php
$info = new SplFileInfo('/path/to/symlink');
if ($info->isLink()) {
    echo 'The real path is '.$info->getRealPath();
}
?>
```

### See Also

-   <span class="methodname">SplFileInfo::getRealPath</span>

SplFileInfo::isReadable
=======================

Tells if file is readable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isReadable</span> ( <span
class="methodparam">void</span> )

Check if the file is readable.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if readable, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">SplFileInfo::isReadable</span>
example**

``` php
<?php
$info = new SplFileInfo(__FILE__);
var_dump($info->isReadable());

$info = new SplFileInfo('foo');
var_dump($info->isReadable());
?>
```

The above example will output something similar to:

    bool(true)
    bool(false)

SplFileInfo::isWritable
=======================

Tells if the entry is writable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isWritable</span> ( <span
class="methodparam">void</span> )

Checks if the current entry is writable.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if writable, **`FALSE`** otherwise;

SplFileInfo::openFile
=====================

Gets an SplFileObject object for the file

### Description

<span class="modifier">public</span> <span
class="type">SplFileObject</span> <span
class="methodname">SplFileInfo::openFile</span> (\[ <span
class="methodparam"><span class="type">string</span> `$open_mode`<span
class="initializer"> = "r"</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`<span class="initializer"> =
**`NULL`**</span></span> \]\]\] )

Creates an <span class="classname">SplFileObject</span> <span
class="type">object</span> of the file. This is useful because <span
class="classname">SplFileObject</span> contains additional methods for
manipulating the file whereas <span class="classname">SplFileInfo</span>
is only useful for gaining information, like whether the file is
writable.

### Parameters

`open_mode`  
The mode for opening the file. See the <span
class="function">fopen</span> documentation for descriptions of possible
modes. The default is read only.

`use_include_path`  
When set to **`TRUE`**, the filename is also searched for within the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>

`context`  
Refer to the <a href="/context.html" class="link">context</a> section of
the manual for a description of *contexts*.

### Return Values

The opened file as an <span class="classname">SplFileObject</span> <span
class="type">object</span>.

### Errors/Exceptions

A <span class="classname">RuntimeException</span> if the file cannot be
opened (e.g. insufficient access rights).

### Examples

**Example \#1 <span class="methodname">SplFileInfo::openFile</span>
example**

``` php
<?php
$fileinfo = new SplFileInfo('/tmp/foo.txt');

if ($fileinfo->isWritable()) {

    $fileobj = $fileinfo->openFile('a');

    $fileobj->fwrite("appended this sample text");
}
?>
```

### See Also

-   <span class="classname">SplFileObject</span>
-   <span class="function">stream\_context\_create</span>
-   <span class="function">fopen</span>

SplFileInfo::setFileClass
=========================

Sets the class used with <span
class="methodname">SplFileInfo::openFile</span>

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileInfo::setFileClass</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "SplFileObject"</span></span> \] )

Use this method to set a custom class which will be used when <span
class="methodname">SplFileInfo::openFile</span> is called. The class
name passed to this method must be <span
class="classname">SplFileObject</span> or a class derived from <span
class="classname">SplFileObject</span>.

### Parameters

`class_name`  
The class name to use when <span
class="methodname">SplFileInfo::openFile</span> is called.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplFileInfo::setFileClass</span>
example**

``` php
<?php
// Create a class extending SplFileObject
class MyFoo extends SplFileObject {}

$info = new SplFileInfo(__FILE__);
// Set the class to use
$info->setFileClass('MyFoo');
var_dump($info->openFile());
?>
```

The above example will output something similar to:

    object(MyFoo)#2 (0) { } 

### See Also

-   <span class="methodname">SplFileInfo::openFile</span>

SplFileInfo::setInfoClass
=========================

Sets the class used with <span
class="methodname">SplFileInfo::getFileInfo</span> and <span
class="methodname">SplFileInfo::getPathInfo</span>

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileInfo::setInfoClass</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "SplFileInfo"</span></span> \] )

Use this method to set a custom class which will be used when <span
class="methodname">SplFileInfo::getFileInfo</span> and <span
class="methodname">SplFileInfo::getPathInfo</span> are called. The class
name passed to this method must be <span
class="classname">SplFileInfo</span> or a class derived from <span
class="classname">SplFileInfo</span>.

### Parameters

`class_name`  
The class name to use when <span
class="methodname">SplFileInfo::getFileInfo</span> and <span
class="methodname">SplFileInfo::getPathInfo</span> are called.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SplFileInfo::setFileClass</span>
example**

``` php
<?php
// Define a class which extends SplFileInfo
class MyFoo extends SplFileInfo {}

$info = new SplFileInfo('foo');
// Set the class name to use
$info->setInfoClass('MyFoo');
var_dump($info->getFileInfo());
?>
```

The above example will output something similar to:

    object(MyFoo)#2 (0) { } 

### See Also

-   <span class="methodname">SplFileInfo::getFileInfo</span>

SplFileInfo::\_\_toString
=========================

Returns the path to the file as a string

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::\_\_toString</span> ( <span
class="methodparam">void</span> )

This method will return the file name of the referenced file.

### Parameters

This function has no parameters.

### Return Values

Returns the path to the file.

### Examples

**Example \#1 <span class="function">SplFileInfo::\_\_toString</span>
example**

``` php
<?php
$info = new SplFileInfo('foo');
var_dump($info->__toString());
echo $info.PHP_EOL;

$info = new SplFileInfo('/usr/bin/php');
var_dump($info->__toString());
echo $info.PHP_EOL;
?>
```

The above example will output something similar to:

    string(3) "foo"
    foo
    string(12) "/usr/bin/php"
    /usr/bin/php 

Introduction
------------

The SplFileObject class offers an object oriented interface for a file.

Class synopsis
--------------

**SplFileObject**

<span class="ooclass"> class **SplFileObject** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SplFileInfo**
</span> <span class="oointerface">implements <span
class="interfacename">RecursiveIterator</span> </span> <span
class="oointerface">, <span
class="interfacename">SeekableIterator</span> </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">integer</span>
`SplFileObject::DROP_NEW_LINE` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplFileObject::READ_AHEAD` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplFileObject::SKIP_EMPTY` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplFileObject::READ_CSV` <span class="initializer"> = 8</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$open_mode`<span class="initializer"> = "r"</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\]\] )

<span class="modifier">public</span> <span
class="type">string\|array</span> <span
class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">eof</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">fflush</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">fgetc</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">fgetcsv</span> (\[ <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = "\\""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">fgets</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">fgetss</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$allowable_tags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">flock</span> ( <span class="methodparam"><span
class="type">int</span> `$operation`</span> \[, <span
class="methodparam"><span class="type">int</span> `&$wouldblock`</span>
\] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">fpassthru</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">fputcsv</span> ( <span class="methodparam"><span
class="type">array</span> `$fields`</span> \[, <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = '"'</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">fread</span> ( <span class="methodparam"><span
class="type">int</span> `$length`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">fscanf</span> ( <span class="methodparam"><span
class="type">string</span> `$format`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `&$...`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">fseek</span> ( <span class="methodparam"><span
class="type">int</span> `$offset`</span> \[, <span
class="methodparam"><span class="type">int</span> `$whence`<span
class="initializer"> = SEEK\_SET</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">fstat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ftell</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ftruncate</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">fwrite</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> \[, <span
class="methodparam"><span class="type">int</span> `$length`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">getChildren</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getCsvControl</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFlags</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getMaxLineLen</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasChildren</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">key</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">seek</span> ( <span class="methodparam"><span
class="type">int</span> `$line_pos`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setCsvControl</span> (\[ <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = "\\""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setFlags</span> ( <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setMaxLineLen</span> ( <span
class="methodparam"><span class="type">int</span> `$max_len`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getATime</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getBasename</span> (\[ <span
class="methodparam"><span class="type">string</span> `$suffix`</span> \]
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getCTime</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getExtension</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SplFileInfo</span> <span
class="methodname">SplFileInfo::getFileInfo</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getFilename</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getGroup</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getInode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getLinkTarget</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getMTime</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getOwner</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SplFileInfo</span> <span
class="methodname">SplFileInfo::getPathInfo</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getPathname</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getPerms</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getRealPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileInfo::getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::getType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isDir</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isExecutable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isLink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isReadable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileInfo::isWritable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SplFileObject</span> <span
class="methodname">SplFileInfo::openFile</span> (\[ <span
class="methodparam"><span class="type">string</span> `$open_mode`<span
class="initializer"> = "r"</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`<span class="initializer"> =
**`NULL`**</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileInfo::setFileClass</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "SplFileObject"</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileInfo::setInfoClass</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "SplFileInfo"</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileInfo::\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`SplFileObject::DROP_NEW_LINE`**  
Drop newlines at the end of a line.

**`SplFileObject::READ_AHEAD`**  
Read on rewind/next.

**`SplFileObject::SKIP_EMPTY`**  
Skips empty lines in the file. This requires the **`READ_AHEAD`** flag
be enabled, to work as expected.

**`SplFileObject::READ_CSV`**  
Read lines as CSV rows.

Changelog
---------

| Version | Description                                                                  |
|---------|------------------------------------------------------------------------------|
| 5.3.9   | **`SplFileObject::SKIP_EMPTY`** value changed to 4. Previously, value was 6. |

SplFileObject::\_\_construct
============================

Construct a new file object

### Description

<span class="modifier">public</span> <span
class="methodname">SplFileObject::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$open_mode`<span class="initializer"> = "r"</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\]\] )

Construct a new file object.

### Parameters

`filename`  
The file to read.

**Tip**
A URL can be used as a filename with this function if the
<a href="/filesystem/setup.html#" class="link">fopen wrappers</a> have
been enabled. See <span class="function">fopen</span> for more details
on how to specify the filename. See the
<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
for links to information about what abilities the various wrappers have,
notes on their usage, and information on any predefined variables they
may provide.

`open_mode`  
The mode in which to open the file. See <span
class="function">fopen</span> for a list of allowed modes.

`use_include_path`  
Whether to search in the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
for `filename`.

`context`  
A valid context resource created with <span
class="function">stream\_context\_create</span>.

### Return Values

No value is returned.

### Errors/Exceptions

Throws a <span class="classname">RuntimeException</span> if the
`filename` cannot be opened.

Throws a <span class="classname">LogicException</span> if the `filename`
is a directory.

### Examples

**Example \#1 <span
class="methodname">SplFileObject::\_\_construct</span> example**

This example opens the current file and iterates over its contents line
by line.

``` php
<?php
$file = new SplFileObject(__FILE__);
foreach ($file as $line_num => $line) {
    echo "Line $line_num is $line";
}
?>
```

The above example will output something similar to:

    Line 0 is <?php
    Line 1 is $file = new SplFileObject(__FILE__);
    Line 2 is foreach ($file as $line_num => $line) {
    Line 3 is     echo "Line $line_num is $line";
    Line 4 is }
    Line 5 is ?>

### See Also

-   <span class="methodname">SplFileInfo::openFile</span>
-   <span class="function">fopen</span>

SplFileObject::current
======================

Retrieve current line of file

### Description

<span class="modifier">public</span> <span
class="type">string\|array</span> <span
class="methodname">SplFileObject::current</span> ( <span
class="methodparam">void</span> )

Retrieves the current line of the file.

### Parameters

This function has no parameters.

### Return Values

Retrieves the current line of the file. If the
**`SplFileObject::READ_CSV`** flag is set, this method returns an array
containing the current line parsed as CSV data.

### Examples

**Example \#1 <span class="methodname">SplFileObject::current</span>
example**

``` php
<?php
$file = new SplFileObject(__FILE__);
foreach ($file as $k => $line) {
   echo ($file->key() + 1) . ': ' . $file->current();
}
?>
```

The above example will output something similar to:

    1: <?php
    2: $file = new SplFileObject(__FILE__);
    3: foreach ($file as $line) {
    4:     echo ($file->key() + 1) . ': ' . $file->current();
    5: }
    6: ?>

### See Also

-   <span class="methodname">SplFileObject::key</span>
-   <span class="methodname">SplFileObject::seek</span>
-   <span class="methodname">SplFileObject::next</span>
-   <span class="methodname">SplFileObject::rewind</span>
-   <span class="methodname">SplFileObject::valid</span>

SplFileObject::eof
==================

Reached end of file

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::eof</span> ( <span
class="methodparam">void</span> )

Determine whether the end of file has been reached

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if file is at EOF, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="methodname">SplFileObject::eof</span>
example**

``` php
<?php
$file = new SplFileObject("fruits.txt");
while ( ! $file->eof()) {
    echo $file->fgets();
}
?>
```

The above example will output something similar to:

    apple
    banana
    cherry
    date
    elderberry

### See Also

-   <span class="methodname">SplFileObject::valid</span>
-   <span class="function">feof</span>

SplFileObject::fflush
=====================

Flushes the output to the file

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::fflush</span> ( <span
class="methodparam">void</span> )

Forces a write of all buffered output to the file.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fflush</span>
example**

``` php
<?php
$file = new SplFileObject('misc.txt', 'r+');
$file->rewind();
$file->fwrite("Foo");
$file->fflush();
$file->ftruncate($file->ftell());
?>
```

### See Also

-   <span class="methodname">SplFileObject::fwrite</span>

SplFileObject::fgetc
====================

Gets character from file

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileObject::fgetc</span> ( <span
class="methodparam">void</span> )

Gets a character from the file.

### Parameters

This function has no parameters.

### Return Values

Returns a string containing a single character read from the file or
**`FALSE`** on EOF.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fgetc</span>
example**

``` php
<?php
$file = new SplFileObject('file.txt');
while (false !== ($char = $file->fgetc())) {
    echo "$char\n";
}
?>
```

### See Also

-   <span class="methodname">SplFileObject::fgets</span>

SplFileObject::fgetcsv
======================

Gets line from file and parse as CSV fields

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplFileObject::fgetcsv</span> (\[ <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = "\\""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

Gets a line from the file which is in CSV format and returns an array
containing the fields read.

> **Note**:
>
> The locale settings are taken into account by this function. If
> *LC\_CTYPE* is e.g. *en\_US.UTF-8*, files in one-byte encodings may be
> read wrongly by this function.

### Parameters

`delimiter`  
The field delimiter (one character only). Defaults as a comma or the
value set using <span
class="methodname">SplFileObject::setCsvControl</span>.

`enclosure`  
The field enclosure character (one character only). Defaults as a double
quotation mark or the value set using <span
class="methodname">SplFileObject::setCsvControl</span>.

`escape`  
The escape character (at most one character). Defaults as a backslash
(*\\*) or the value set using <span
class="methodname">SplFileObject::setCsvControl</span>. An empty string
(*""*) disables the proprietary escape mechanism.

> **Note**: <span class="simpara"> Usually an `enclosure` character is
> escpaped inside a field by doubling it; however, the `escape`
> character can be used as an alternative. So for the default parameter
> values *""* and *\\"* have the same meaning. Other than allowing to
> escape the `enclosure` character the `escape` character has no special
> meaning; it isn't even meant to escape itself. </span>

### Return Values

Returns an indexed array containing the fields read, or **`FALSE`** on
error.

> **Note**:
>
> A blank line in a CSV file will be returned as an array comprising a
> single **`NULL`** field unless using
> **`SplFileObject::SKIP_EMPTY | SplFileObject::DROP_NEW_LINE`**, in
> which case empty lines are skipped.

### Changelog

| Version | Description                                                                                          |
|---------|------------------------------------------------------------------------------------------------------|
| 7.4.0   | The `escape` parameter now also accepts an empty string to disable the proprietary escape mechanism. |

### Examples

**Example \#1 <span class="methodname">SplFileObject::fgetcsv</span>
example**

``` php
<?php
$file = new SplFileObject("data.csv");
while (!$file->eof()) {
    var_dump($file->fgetcsv());
}
?>
```

**Example \#2 **`SplFileObject::READ_CSV`** example**

``` php
<?php
$file = new SplFileObject("animals.csv");
$file->setFlags(SplFileObject::READ_CSV);
foreach ($file as $row) {
    list($animal, $class, $legs) = $row;
    printf("A %s is a %s with %d legs\n", $animal, $class, $legs);
}
?>
```

Contents of animals.csv

``` txt
crocodile,reptile,4
dolphin,mammal,0
duck,bird,2
koala,mammal,4
salmon,fish,0
```

The above example will output something similar to:

    A crocodile is a reptile with 4 legs
    A dolphin is a mammal with 0 legs
    A duck is a bird with 2 legs
    A koala is a mammal with 4 legs
    A salmon is a fish with 0 legs

### See Also

-   <span class="methodname">SplFileObject::setCsvControl</span>
-   <span class="methodname">SplFileObject::setFlags</span>
-   <a href="/spl/files.html#" class="link">SplFileObject::READ_CSV</a>
-   <span class="methodname">SplFileObject::current</span>

SplFileObject::fgets
====================

Gets line from file

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileObject::fgets</span> ( <span
class="methodparam">void</span> )

Gets a line from the file.

### Parameters

This function has no parameters.

### Return Values

Returns a string containing the next line from the file, or **`FALSE`**
on error.

### Errors/Exceptions

Throws a <span class="classname">RuntimeException</span> if the file
cannot be read.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fgets</span>
example**

This example simply outputs the contents of *file.txt* line-by-line.

``` php
<?php
$file = new SplFileObject("file.txt");
while (!$file->eof()) {
    echo $file->fgets();
}
?>
```

### See Also

-   <span class="function">fgets</span>
-   <span class="methodname">SplFileObject::fgetss</span>
-   <span class="methodname">SplFileObject::fgetc</span>
-   <span class="methodname">SplFileObject::current</span>

SplFileObject::fgetss
=====================

Gets line from file and strip HTML tags

**Warning**

This function has been *DEPRECATED* as of PHP 7.3.0. Relying on this
function is highly discouraged.

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileObject::fgetss</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$allowable_tags`</span> \] )

Identical to <span class="methodname">SplFileObject::fgets</span>,
except that <span class="methodname">SplFileObject::fgetss</span>
attempts to strip any HTML and PHP tags from the text it reads. The
function retains the parsing state from call to call, and as such is not
equivalent to calling <span class="function">strip\_tags</span> on the
return value of <span class="methodname">SplFileObject::fgets</span>.

### Parameters

`allowable_tags`  
Optional parameter to specify tags which should not be stripped.

### Return Values

Returns a string containing the next line of the file with HTML and PHP
code stripped, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fgetss</span>
example**

``` php
<?php
$str = <<<EOD
<html><body>
 <p>Welcome! Today is the <?php echo(date('jS')); ?> of <?= date('F'); ?>.</p>
</body></html>
Text outside of the HTML block.
EOD;
file_put_contents("sample.php", $str);

$file = new SplFileObject("sample.php");
while (!$file->eof()) {
    echo $file->fgetss();
}
?>
```

The above example will output something similar to:


     Welcome! Today is the  of .

    Text outside of the HTML block.

### See Also

-   <span class="function">fgetss</span>
-   <span class="methodname">SplFileObject::fgets</span>
-   <span class="methodname">SplFileObject::fgetc</span>
-   <span class="methodname">SplFileObject::current</span>
-   The
    <a href="/filters/string.html#filters.string.strip_tags" class="link">string.strip_tags</a>
    filter

SplFileObject::flock
====================

Portable file locking

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::flock</span> ( <span
class="methodparam"><span class="type">int</span> `$operation`</span>
\[, <span class="methodparam"><span class="type">int</span>
`&$wouldblock`</span> \] )

Locks or unlocks the file in the same portable way as <span
class="function">flock</span>.

### Parameters

`operation`  
`operation` is one of the following:

-   <span class="simpara"> **`LOCK_SH`** to acquire a shared lock
    (reader). </span>
-   <span class="simpara"> **`LOCK_EX`** to acquire an exclusive lock
    (writer). </span>
-   <span class="simpara"> **`LOCK_UN`** to release a lock (shared or
    exclusive). </span>
-   <span class="simpara"> **`LOCK_NB`** to not block while locking.
    </span>

`wouldblock`  
Set to **`TRUE`** if the lock would block (EWOULDBLOCK errno condition).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">SplFileObject::flock</span>
example**

``` php
<?php
$file = new SplFileObject("/tmp/lock.txt", "w");
if ($file->flock(LOCK_EX)) { // do an exclusive lock
    $file->ftruncate(0);     // truncate file
    $file->fwrite("Write something here\n");
    $file->flock(LOCK_UN);   // release the lock    
} else {
    echo "Couldn't get the lock!";
}
?>
```

### Changelog

| Version       | Description                                                                                                                  |
|---------------|------------------------------------------------------------------------------------------------------------------------------|
| 5.5.22, 5.6.6 | Added support for the `wouldblock` parameter on Windows.                                                                     |
| 5.3.2         | The automatic unlocking when the file's resource handle is closed was removed. Unlocking now always has to be done manually. |

### See Also

-   <span class="function">flock</span>

SplFileObject::fpassthru
========================

Output all remaining data on a file pointer

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::fpassthru</span> ( <span
class="methodparam">void</span> )

Reads to EOF on the given file pointer from the current position and
writes the results to the output buffer.

You may need to call <span
class="methodname">SplFileObject::rewind</span> to reset the file
pointer to the beginning of the file if you have already written data to
the file.

### Parameters

This function has no parameters.

### Return Values

Returns the number of characters read from `handle` and passed through
to the output.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fpassthru</span>
example**

``` php
<?php

// Open the file in binary mode
$file = new SplFileObject("./img/ok.png", "rb");

// Send the right headers
header("Content-Type: image/png");
header("Content-Length: " . $file->getSize());

// Dump the picture and end script
$file->fpassthru();
exit;

?>
```

### See Also

-   <span class="function">fpassthru</span>

SplFileObject::fputcsv
======================

Write a field array as a CSV line

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::fputcsv</span> ( <span
class="methodparam"><span class="type">array</span> `$fields`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$delimiter`<span class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = '"'</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

Writes the `fields` array to the file as a CSV line.

### Parameters

`fields`  
An array of values.

`delimiter`  
The optional `delimiter` parameter sets the field delimiter (one
character only).

`enclosure`  
The optional `enclosure` parameter sets the field enclosure (one
character only).

`escape`  
The optional `escape` parameter sets the escape character (at most one
character). An empty string (*""*) disables the proprietary escape
mechanism.

> **Note**:
>
> If an `enclosure` character is contained in a field, it will be
> escaped by doubling it, unless it is immediately preceded by an
> `escape_char`.

### Return Values

Returns the length of the written string or **`FALSE`** on failure.

Returns **`FALSE`**, and does not write the CSV line to the file, if the
`delimiter` or `enclosure` parameter is not a single character.

### Errors/Exceptions

An **`E_WARNING`** level error is issued if the `delimiter` or
`enclosure` parameter is not a single character.

### Changelog

| Version       | Description                                                                                          |
|---------------|------------------------------------------------------------------------------------------------------|
| 7.4.0         | The `escape` parameter now also accepts an empty string to disable the proprietary escape mechanism. |
| 5.5.21, 5.6.5 | Added the `escape` parameter.                                                                        |

### Examples

**Example \#1 <span class="methodname">SplFileObject::fputcsv</span>
example**

``` php
<?php

$list = array (
    array('aaa', 'bbb', 'ccc', 'dddd'),
    array('123', '456', '789'),
    array('"aaa"', '"bbb"')
);

$file = new SplFileObject('file.csv', 'w');

foreach ($list as $fields) {
    $file->fputcsv($fields);
}

?>
```

The above example will write the following to *file.csv*:

    aaa,bbb,ccc,dddd
    123,456,789
    """aaa""","""bbb"""

### See Also

-   <span class="function">fputcsv</span>
-   <span class="methodname">SplFileObject::fgetcsv</span>

SplFileObject::fread
====================

Read from file

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileObject::fread</span> ( <span
class="methodparam"><span class="type">int</span> `$length`</span> )

Reads the given number of bytes from the file.

### Parameters

`length`  
The number of bytes to read.

### Return Values

Returns the string read from the file or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fread</span>
example**

``` php
<?php
// Get contents of a file into a string
$filename = "/usr/local/something.txt";
$file = new SplFileObject($filename, "r");
$contents = $file->fread($file->getSize());
?>
```

### Notes

> **Note**:
>
> Note that <span class="methodname">SplFileObject::fread</span> reads
> from the current position of the file pointer. Use <span
> class="methodname">SplFileObject::ftell</span> to find the current
> position of the pointer and <span
> class="methodname">SplFileObject::rewind</span> (or <span
> class="methodname">SplFileObject::fseek</span>) to rewind the pointer
> position.

### See Also

-   <span class="function">fread</span>

SplFileObject::fscanf
=====================

Parses input from file according to a format

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplFileObject::fscanf</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`&$...`</span> \] )

Reads a line from the file and interprets it according to the specified
`format`, which is described in the documentation for <span
class="function">sprintf</span>.

Any whitespace in the `format` string matches any whitespace in the line
from the file. This means that even a tab *\\t* in the format string can
match a single space character in the input stream.

### Parameters

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

If only one parameter is passed to this method, the values parsed will
be returned as an array. Otherwise, if optional parameters are passed,
the function will return the number of assigned values. The optional
parameters must be passed by reference.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fscanf</span>
example**

``` php
<?php
$file = new SplFileObject("misc.txt");
while ($userinfo = $file->fscanf("%s %s %s")) {
    list ($name, $profession, $countrycode) = $userinfo;
    // Do something with $name $profession $countrycode
}
?>
```

Contents of users.txt

``` txt
javier   argonaut    pe
hiroshi  sculptor    jp
robert   slacker     us
luigi    florist     it
```

### See Also

-   <span class="function">fscanf</span>
-   <span class="function">sscanf</span>
-   <span class="function">printf</span>
-   <span class="function">sprintf</span>

SplFileObject::fseek
====================

Seek to a position

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::fseek</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> \[,
<span class="methodparam"><span class="type">int</span> `$whence`<span
class="initializer"> = SEEK\_SET</span></span> \] )

Seek to a position in the file measured in bytes from the beginning of
the file, obtained by adding `offset` to the position specified by
`whence`.

### Parameters

`offset`  
The offset. A negative value can be used to move backwards through the
file which is useful when SEEK\_END is used as the `whence` value.

`whence`  
`whence` values are:

-   **`SEEK_SET`** - Set position equal to `offset` bytes.
-   **`SEEK_CUR`** - Set position to current location plus `offset`.
-   **`SEEK_END`** - Set position to end-of-file plus `offset`.

If `whence` is not specified, it is assumed to be **`SEEK_SET`**.

### Return Values

Returns 0 if the seek was successful, -1 otherwise. Note that seeking
past EOF is not considered an error.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fseek</span>
example**

``` php
<?php
$file = new SplFileObject("somefile.txt");

// Read first line
$data = $file->fgets();

// Move back to the beginning of the file
// Same as $file->rewind();
$file->fseek(0);
?>
```

### See Also

-   <span class="function">fseek</span>

SplFileObject::fstat
====================

Gets information about the file

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplFileObject::fstat</span> ( <span
class="methodparam">void</span> )

Gathers the statistics of the file. Behaves identically to <span
class="function">fstat</span>.

### Parameters

This function has no parameters.

### Return Values

Returns an array with the statistics of the file; the format of the
array is described in detail on the <span class="function">stat</span>
manual page.

### Examples

**Example \#1 <span class="methodname">SplFileObject::fstat</span>
example**

``` php
<?php
$file = new SplFileObject("/etc/passwd");
$stat = $file->fstat();

// Print only the associative part
print_r(array_slice($stat, 13));

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

### See Also

-   <span class="function">fstat</span>
-   <span class="function">stat</span>

SplFileObject::ftell
====================

Return current file position

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::ftell</span> ( <span
class="methodparam">void</span> )

Returns the position of the file pointer which represents the current
offset in the file stream.

### Parameters

This function has no parameters.

### Return Values

Returns the position of the file pointer as an integer, or **`FALSE`**
on error.

### Examples

**Example \#1 <span class="methodname">SplFileObject::ftell</span>
example**

``` php
<?php
$file = new SplFileObject("/etc/passwd");

// Read first line
$data = $file->fgets();

// Where are we?
echo $file->ftell();
?>
```

### See Also

-   <span class="function">ftell</span>

SplFileObject::ftruncate
========================

Truncates the file to a given length

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::ftruncate</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

Truncates the file to `size` bytes.

### Parameters

`size`  
The size to truncate to.

> **Note**:
>
> If `size` is larger than the file it is extended with null bytes.
>
> If `size` is smaller than the file, the extra data will be lost.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">SplFileObject::ftruncate</span>
example**

``` php
<?php
// Create file containing "Hello World!"
$file = new SplFileObject("/tmp/ftruncate", "w+");
$file->fwrite("Hello World!");

// Truncate to 5 bytes
$file->ftruncate(5);

// Rewind and read data
$file->rewind();
echo $file->fgets();
?>
```

The above example will output something similar to:

    Hello

### See Also

-   <span class="function">ftruncate</span>

SplFileObject::fwrite
=====================

Write to file

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::fwrite</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`</span>
\] )

Writes the contents of `string` to the file

### Parameters

`str`  
The string to be written to the file.

`length`  
If the `length` argument is given, writing will stop after `length`
bytes have been written or the end of `string` is reached, whichever
comes first.

### Return Values

Returns the number of bytes written, or **`FALSE`** on error.

### Changelog

| Version | Description                                                      |
|---------|------------------------------------------------------------------|
| 7.4.0   | The function now returns **`FALSE`** instead of zero on failure. |

### Examples

**Example \#1 <span class="methodname">SplFileObject::fwrite</span>
example**

``` php
<?php
$file = new SplFileObject("fwrite.txt", "w");
$written = $file->fwrite("12345");
echo "Wrote $written bytes to file";
?>
```

The above example will output something similar to:

    Wrote 5 bytes to file

### See Also

-   <span class="function">fwrite</span>

SplFileObject::getChildren
==========================

No purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::getChildren</span> ( <span
class="methodparam">void</span> )

An <span class="classname">SplFileObject</span> does not have children
so this method returns **`NULL`**.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">RecursiveIterator::getChildren</span>

SplFileObject::getCsvControl
============================

Get the delimiter, enclosure and escape character for CSV

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplFileObject::getCsvControl</span> ( <span
class="methodparam">void</span> )

Gets the delimiter, enclosure and escape character used for parsing CSV
fields.

### Parameters

This function has no parameters.

### Return Values

Returns an indexed array containing the delimiter, enclosure and escape
character.

### Changelog

| Version        | Description                                       |
|----------------|---------------------------------------------------|
| 7.4.0          | The escape character can now be an empty string.  |
| 5.6.25, 7.0.10 | Added the escape character to the returned array. |

### Examples

**Example \#1 <span
class="methodname">SplFileObject::getCsvControl</span> example**

``` php
<?php
$file = new SplFileObject("data.txt");
print_r($file->getCsvControl());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => ,
        [1] => "
        [2] => \
    )

### See Also

-   <span class="methodname">SplFileObject::setCsvControl</span>
-   <span class="methodname">SplFileObject::fgetcsv</span>

SplFileObject::getCurrentLine
=============================

Alias of <span class="methodname">SplFileObject::fgets</span>

### Description

This method is an alias of: <span
class="methodname">SplFileObject::fgets</span>.

SplFileObject::getFlags
=======================

Gets flags for the SplFileObject

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::getFlags</span> ( <span
class="methodparam">void</span> )

Gets the flags set for an instance of SplFileObject as an <span
class="type">integer</span>.

### Parameters

This function has no parameters.

### Return Values

Returns an <span class="type">integer</span> representing the flags.

### Examples

**Example \#1 <span class="methodname">SplFileObject::getFlags</span>
example**

``` php
<?php
$file = new SplFileObject(__FILE__, "r");

if ($file->getFlags() & SplFileObject::SKIP_EMPTY) {
    echo "Skipping empty lines\n";
} else {
    echo "Not skipping empty lines\n";
}

$file->setFlags(SplFileObject::SKIP_EMPTY);

if ($file->getFlags() & SplFileObject::SKIP_EMPTY) {
    echo "Skipping empty lines\n";
} else {
    echo "Not skipping empty lines\n";
}
?>
```

The above example will output something similar to:

    Not skipping empty lines
    Skipping empty lines

### See Also

-   <span class="methodname">SplFileObject::setFlags</span>

SplFileObject::getMaxLineLen
============================

Get maximum line length

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::getMaxLineLen</span> ( <span
class="methodparam">void</span> )

Gets the maximum line length as set by <span
class="methodname">SplFileObject::setMaxLineLen</span>.

### Parameters

This function has no parameters.

### Return Values

Returns the maximum line length if one has been set with <span
class="methodname">SplFileObject::setMaxLineLen</span>, default is *0*.

### Examples

**Example \#1 <span
class="methodname">SplFileObject::getMaxLineLen</span> example**

``` php
<?php
$file = new SplFileObject("file.txt");
var_dump($file->getMaxLineLen());

$file->setMaxLineLen(20);
var_dump($file->getMaxLineLen());
?>
```

The above example will output something similar to:

    int(0)
    int(20)

### See Also

-   <span class="methodname">Classname::Method</span>

SplFileObject::hasChildren
==========================

SplFileObject does not have children

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::hasChildren</span> ( <span
class="methodparam">void</span> )

An <span class="classname">SplFileObject</span> does not have children
so this method always return **`FALSE`**.

### Parameters

This function has no parameters.

### Return Values

Returns **`FALSE`**

### See Also

-   <span class="methodname">RecursiveIterator::hasChildren</span>

SplFileObject::key
==================

Get line number

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::key</span> ( <span
class="methodparam">void</span> )

Gets the current line number.

> **Note**:
>
> This number may not reflect the actual line number in the file if
> <span class="methodname">SplFileObject::setMaxLineLen</span> is used
> to read fixed lengths of the file.

### Parameters

This function has no parameters.

### Return Values

Returns the current line number.

### Examples

**Example \#1 <span class="methodname">SplFileObject::key</span>
example**

``` php
<?php
$file = new SplFileObject("lipsum.txt");
foreach ($file as $line) {
    echo $file->key() . ". " . $line;
}
?>
```

The above example will output something similar to:

    0. Lorem ipsum dolor sit amet, consectetur adipiscing elit. 
    1. Duis nec sapien felis, ac sodales nisl. 
    2. Lorem ipsum dolor sit amet, consectetur adipiscing elit.

**Example \#2 <span class="methodname">SplFileObject::key</span> example
with <span class="methodname">SplFileObject::setMaxLineLen</span>**

``` php
<?php
$file = new SplFileObject("lipsum.txt");
$file->setMaxLineLen(20);
foreach ($file as $line) {
    echo $file->key() . ". " . $line . "\n";
}
?>
```

The above example will output something similar to:

    0. Lorem ipsum dolor s
    1. it amet, consectetu
    2. r adipiscing elit. 
    3. 

    4. Duis nec sapien fel
    5. is, ac sodales nisl
    6. . 

    7. Lorem ipsum dolor s
    8. it amet, consectetu
    9. r adipiscing elit.

### See Also

-   <span class="methodname">SplFileObject::current</span>
-   <span class="methodname">SplFileObject::seek</span>
-   <span class="methodname">SplFileObject::next</span>
-   <span class="methodname">SplFileObject::rewind</span>
-   <span class="methodname">SplFileObject::valid</span>

SplFileObject::next
===================

Read next line

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::next</span> ( <span
class="methodparam">void</span> )

Moves ahead to the next line in the file.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="methodname">SplFileObject::next</span>
example**

``` php
<?php
// Read through file line by line
$file = new SplFileObject("misc.txt");
while (!$file->eof()) {
    echo $file->current();
    $file->next();
}
?>
```

### See Also

-   <span class="methodname">SplFileObject::current</span>
-   <span class="methodname">SplFileObject::key</span>
-   <span class="methodname">SplFileObject::seek</span>
-   <span class="methodname">SplFileObject::rewind</span>
-   <span class="methodname">SplFileObject::valid</span>

SplFileObject::rewind
=====================

Rewind the file to the first line

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::rewind</span> ( <span
class="methodparam">void</span> )

Rewinds the file back to the first line.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Errors/Exceptions

Throws a <span class="classname">RuntimeException</span> if cannot be
rewound.

### Examples

**Example \#1 <span class="methodname">SplFileObject::rewind</span>
example**

``` php
<?php
$file = new SplFileObject("misc.txt");

// Loop over whole file
foreach ($file as $line) { }

// Rewind to first line
$file->rewind();

// Output first line
echo $file->current();
?>
```

### See Also

-   <span class="methodname">SplFileObject::current</span>
-   <span class="methodname">SplFileObject::key</span>
-   <span class="methodname">SplFileObject::seek</span>
-   <span class="methodname">SplFileObject::next</span>
-   <span class="methodname">SplFileObject::valid</span>

SplFileObject::seek
===================

Seek to specified line

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::seek</span> ( <span
class="methodparam"><span class="type">int</span> `$line_pos`</span> )

Seek to specified line in the file.

### Parameters

`line_pos`  
The zero-based line number to seek to.

### Return Values

No value is returned.

### Errors/Exceptions

Throws a <span class="classname">LogicException</span> if the `line_pos`
is negative.

### Examples

**Example \#1 <span class="methodname">SplFileObject::seek</span>
example**

This example outputs the third line of the script which is found at
position 2.

``` php
<?php
$file = new SplFileObject(__FILE__);
$file->seek(2);
echo $file->current();
?>
```

The above example will output something similar to:

    $file->seek(2);

### See Also

-   <span class="methodname">SplFileObject::current</span>
-   <span class="methodname">SplFileObject::key</span>
-   <span class="methodname">SplFileObject::next</span>
-   <span class="methodname">SplFileObject::rewind</span>
-   <span class="methodname">SplFileObject::valid</span>

SplFileObject::setCsvControl
============================

Set the delimiter, enclosure and escape character for CSV

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::setCsvControl</span> (\[ <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = "\\""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

Sets the delimiter, enclosure and escape character for parsing CSV
fields.

### Parameters

`delimiter`  
The field delimiter (one character only).

`enclosure`  
The field enclosure character (one character only).

`escape`  
The field escape character (at most one character). An empty string
(*""*) disables the proprietary escape mechanism.

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                          |
|---------|------------------------------------------------------------------------------------------------------|
| 7.4.0   | The `escape` parameter now also accepts an empty string to disable the proprietary escape mechanism. |
| 5.3.0   | Added the `escape` parameter.                                                                        |

### Examples

**Example \#1 <span
class="methodname">SplFileObject::setCsvControl</span> example**

``` php
<?php
$file = new SplFileObject("data.csv");
$file->setFlags(SplFileObject::READ_CSV);
$file->setCsvControl('|');
foreach ($file as $row) {
    list ($fruit, $quantity) = $row;
    // Do something with values
}
?>
```

Contents of data.csv

``` txt
<?php
apples|20
bananas|14
cherries|87
?>
```

### See Also

-   <span class="methodname">SplFileObject::getCsvControl</span>
-   <span class="methodname">SplFileObject::fgetcsv</span>

SplFileObject::setFlags
=======================

Sets flags for the SplFileObject

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::setFlags</span> ( <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

Sets the flags to be used by the <span
class="classname">SplFileObject</span>.

### Parameters

`flags`  
Bit mask of the flags to set. See
<a href="/spl/files.html#Predefined%20Constants" class="link">SplFileObject constants</a>
for the available flags.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="methodname">SplFileObject::setFlags</span>
example**

``` php
<?php
$file = new SplFileObject("data.csv");
$file->setFlags(SplFileObject::READ_CSV);
foreach ($file as $fields) {
    var_dump($fields);
}
?>
```

### See Also

-   <span class="methodname">SplFileObject::getFlags</span>

SplFileObject::setMaxLineLen
============================

Set maximum line length

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::setMaxLineLen</span> ( <span
class="methodparam"><span class="type">int</span> `$max_len`</span> )

Sets the maximum length of a line to be read.

### Parameters

`max_len`  
The maximum length of a line.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">DomainException</span> when `max_len` is
less than zero.

### Examples

**Example \#1 <span
class="methodname">SplFileObject::setMaxLineLen</span> example**

``` php
<?php
$file = new SplFileObject("lipsum.txt");
$file->setMaxLineLen(20);
foreach ($file as $line) {
    echo $line . "\n";
}
?>
```

Contents of lipsum.txt

``` txt
Lorem ipsum dolor sit amet, consectetur adipiscing elit.
Duis nec sapien felis, ac sodales nisl.
Nulla vitae magna vitae purus aliquet consequat.
```

The above example will output something similar to:

    Lorem ipsum dolor s
    it amet, consectetu
    r adipiscing elit.

    Duis nec sapien fel
    is, ac sodales nisl
    .

    Nulla vitae magna v
    itae purus aliquet 
    consequat.

### See Also

-   <span class="methodname">Classname::Method</span>

SplFileObject::\_\_toString
===========================

Alias of <span class="methodname">SplFileObject::fgets</span>

### Description

This method is an alias of: <span
class="methodname">SplFileObject::fgets</span>.

### Changelog

| Version       | Description                                                                                                                                          |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.19, 7.3.6 | Changed from an alias of <span class="methodname">SplFileObject::current</span> to an alias of <span class="methodname">SplFileObject::fgets</span>. |

SplFileObject::valid
====================

Not at EOF

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::valid</span> ( <span
class="methodparam">void</span> )

Check whether EOF has been reached.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if not reached EOF, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="methodname">SplFileObject::valid</span>
example**

``` php
<?php
// Loop over a file, line by line
$file = new SplFileObject("file.txt");
while ($file->valid()) {
    echo $file->fgets();
}
?>
```

### See Also

-   <span class="methodname">SplFileObject::current</span>
-   <span class="methodname">SplFileObject::key</span>
-   <span class="methodname">SplFileObject::seek</span>
-   <span class="methodname">SplFileObject::next</span>
-   <span class="methodname">SplFileObject::rewind</span>

Introduction
------------

The SplTempFileObject class offers an object oriented interface for a
temporary file.

Class synopsis
--------------

**SplTempFileObject**

<span class="ooclass"> class **SplTempFileObject** </span> <span
class="ooclass"> <span class="modifier">extends</span> **SplFileObject**
</span> <span class="oointerface">implements <span
class="interfacename">SeekableIterator</span> </span> <span
class="oointerface">, <span
class="interfacename">RecursiveIterator</span> </span> {

/\* Inherited constants \*/

<span class="modifier">const</span> <span class="type">integer</span>
`SplFileObject::DROP_NEW_LINE` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplFileObject::READ_AHEAD` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplFileObject::SKIP_EMPTY` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`SplFileObject::READ_CSV` <span class="initializer"> = 8</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$max_memory`</span>
\] )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">string\|array</span> <span
class="methodname">SplFileObject::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::eof</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::fflush</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileObject::fgetc</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplFileObject::fgetcsv</span> (\[ <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = "\\""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileObject::fgets</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileObject::fgetss</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$allowable_tags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::flock</span> ( <span
class="methodparam"><span class="type">int</span> `$operation`</span>
\[, <span class="methodparam"><span class="type">int</span>
`&$wouldblock`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::fpassthru</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::fputcsv</span> ( <span
class="methodparam"><span class="type">array</span> `$fields`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$delimiter`<span class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = '"'</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SplFileObject::fread</span> ( <span
class="methodparam"><span class="type">int</span> `$length`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SplFileObject::fscanf</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`&$...`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::fseek</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> \[,
<span class="methodparam"><span class="type">int</span> `$whence`<span
class="initializer"> = SEEK\_SET</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplFileObject::fstat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::ftell</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::ftruncate</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::fwrite</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`</span>
\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::getChildren</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SplFileObject::getCsvControl</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::getFlags</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::getMaxLineLen</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::hasChildren</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SplFileObject::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::seek</span> ( <span
class="methodparam"><span class="type">int</span> `$line_pos`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::setCsvControl</span> (\[ <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = "\\""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::setFlags</span> ( <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SplFileObject::setMaxLineLen</span> ( <span
class="methodparam"><span class="type">int</span> `$max_len`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SplFileObject::valid</span> ( <span
class="methodparam">void</span> )

}

SplTempFileObject::\_\_construct
================================

Construct a new temporary file object

### Description

<span class="modifier">public</span> <span
class="methodname">SplTempFileObject::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$max_memory`</span>
\] )

Construct a new temporary file object.

### Parameters

`max_memory`  
The maximum amount of memory (in bytes, default is 2 MB) for the
temporary file to use. If the temporary file exceeds this size, it will
be moved to a file in the system's temp directory.

If `max_memory` is negative, only memory will be used. If `max_memory`
is zero, no memory will be used.

### Return Values

No value is returned.

### Errors/Exceptions

Throws a <span class="classname">RuntimeException</span> if an error
occurs.

### Examples

**Example \#1 <span class="methodname">SplTempFileObject</span>
example**

This example writes a temporary file in memory which can be written to
and read from.

``` php
<?php
$temp = new SplTempFileObject();
$temp->fwrite("This is the first line\n");
$temp->fwrite("And this is the second.\n");
echo "Written " . $temp->ftell() . " bytes to temporary file.\n\n";

// Rewind and read what was written
$temp->rewind();
foreach ($temp as $line) {
    echo $line;
}
?>
```

The above example will output something similar to:

    Written 47 bytes to temporary file.

    This is the first line
    And this is the second.

### See Also

-   <span class="classname">SplFileObject</span>
-   <a href="/wrappers/php.html" class="link">PHP input/output streams</a>
    (for *php://temp* and *php://memory*)

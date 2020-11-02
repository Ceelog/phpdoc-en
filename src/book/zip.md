Zip
===

**Table of Contents**

-   [Introduction](/intro/zip.html)
-   [Installing/Configuring](/zip/setup.html)
    -   [Requirements](/zip/setup.html#Requirements)
    -   [Installation](/zip/setup.html#Installation)
    -   [Runtime Configuration](/zip/setup.html#Runtime%20Configuration)
    -   [Resource Types](/zip/setup.html#Resource%20Types)
-   [Predefined Constants](/zip/constants.html)
-   [Examples](/zip/examples.html)
-   [ZipArchive](/class/ziparchive.html) — The ZipArchive class
    -   [ZipArchive::addEmptyDir](/class/ziparchive.html#ZipArchive::addEmptyDir)
        — Add a new directory
    -   [ZipArchive::addFile](/class/ziparchive.html#ZipArchive::addFile)
        — Adds a file to a ZIP archive from the given path
    -   [ZipArchive::addFromString](/class/ziparchive.html#ZipArchive::addFromString)
        — Add a file to a ZIP archive using its contents
    -   [ZipArchive::addGlob](/class/ziparchive.html#ZipArchive::addGlob)
        — Add files from a directory by glob pattern
    -   [ZipArchive::addPattern](/class/ziparchive.html#ZipArchive::addPattern)
        — Add files from a directory by PCRE pattern
    -   [ZipArchive::close](/class/ziparchive.html#ZipArchive::close) —
        Close the active archive (opened or newly created)
    -   [ZipArchive::count](/class/ziparchive.html#ZipArchive::count) —
        Counts the number of files in the archive
    -   [ZipArchive::deleteIndex](/class/ziparchive.html#ZipArchive::deleteIndex)
        — Delete an entry in the archive using its index
    -   [ZipArchive::deleteName](/class/ziparchive.html#ZipArchive::deleteName)
        — Delete an entry in the archive using its name
    -   [ZipArchive::extractTo](/class/ziparchive.html#ZipArchive::extractTo)
        — Extract the archive contents
    -   [ZipArchive::getArchiveComment](/class/ziparchive.html#ZipArchive::getArchiveComment)
        — Returns the Zip archive comment
    -   [ZipArchive::getCommentIndex](/class/ziparchive.html#ZipArchive::getCommentIndex)
        — Returns the comment of an entry using the entry index
    -   [ZipArchive::getCommentName](/class/ziparchive.html#ZipArchive::getCommentName)
        — Returns the comment of an entry using the entry name
    -   [ZipArchive::getExternalAttributesIndex](/class/ziparchive.html#ZipArchive::getExternalAttributesIndex)
        — Retrieve the external attributes of an entry defined by its
        index
    -   [ZipArchive::getExternalAttributesName](/class/ziparchive.html#ZipArchive::getExternalAttributesName)
        — Retrieve the external attributes of an entry defined by its
        name
    -   [ZipArchive::getFromIndex](/class/ziparchive.html#ZipArchive::getFromIndex)
        — Returns the entry contents using its index
    -   [ZipArchive::getFromName](/class/ziparchive.html#ZipArchive::getFromName)
        — Returns the entry contents using its name
    -   [ZipArchive::getNameIndex](/class/ziparchive.html#ZipArchive::getNameIndex)
        — Returns the name of an entry using its index
    -   [ZipArchive::getStatusString](/class/ziparchive.html#ZipArchive::getStatusString)
        — Returns the status error message, system and/or zip messages
    -   [ZipArchive::getStream](/class/ziparchive.html#ZipArchive::getStream)
        — Get a file handler to the entry defined by its name (read
        only)
    -   [ZipArchive::isCompressionMethodSupported](/class/ziparchive.html#ZipArchive::isCompressionMethodSupported)
        — Check if a compression method is supported by libzip
    -   [ZipArchive::isEncryptionMethodSupported](/class/ziparchive.html#ZipArchive::isEncryptionMethodSupported)
        — Check if a encryption method is supported by libzip
    -   [ZipArchive::locateName](/class/ziparchive.html#ZipArchive::locateName)
        — Returns the index of the entry in the archive
    -   [ZipArchive::open](/class/ziparchive.html#ZipArchive::open) —
        Open a ZIP file archive
    -   [ZipArchive::registerCancelCallback](/class/ziparchive.html#ZipArchive::registerCancelCallback)
        — Register a callback to allow cancellation during archive
        close.
    -   [ZipArchive::registerProgressCallback](/class/ziparchive.html#ZipArchive::registerProgressCallback)
        — Register a callback to provide updates during archive close.
    -   [ZipArchive::renameIndex](/class/ziparchive.html#ZipArchive::renameIndex)
        — Renames an entry defined by its index
    -   [ZipArchive::renameName](/class/ziparchive.html#ZipArchive::renameName)
        — Renames an entry defined by its name
    -   [ZipArchive::replaceFile](/class/ziparchive.html#ZipArchive::replaceFile)
        — Replace file in ZIP archive with a given path
    -   [ZipArchive::setArchiveComment](/class/ziparchive.html#ZipArchive::setArchiveComment)
        — Set the comment of a ZIP archive
    -   [ZipArchive::setCommentIndex](/class/ziparchive.html#ZipArchive::setCommentIndex)
        — Set the comment of an entry defined by its index
    -   [ZipArchive::setCommentName](/class/ziparchive.html#ZipArchive::setCommentName)
        — Set the comment of an entry defined by its name
    -   [ZipArchive::setCompressionIndex](/class/ziparchive.html#ZipArchive::setCompressionIndex)
        — Set the compression method of an entry defined by its index
    -   [ZipArchive::setCompressionName](/class/ziparchive.html#ZipArchive::setCompressionName)
        — Set the compression method of an entry defined by its name
    -   [ZipArchive::setEncryptionIndex](/class/ziparchive.html#ZipArchive::setEncryptionIndex)
        — Set the encryption method of an entry defined by its index
    -   [ZipArchive::setEncryptionName](/class/ziparchive.html#ZipArchive::setEncryptionName)
        — Set the encryption method of an entry defined by its name
    -   [ZipArchive::setExternalAttributesIndex](/class/ziparchive.html#ZipArchive::setExternalAttributesIndex)
        — Set the external attributes of an entry defined by its index
    -   [ZipArchive::setExternalAttributesName](/class/ziparchive.html#ZipArchive::setExternalAttributesName)
        — Set the external attributes of an entry defined by its name
    -   [ZipArchive::setMtimeIndex](/class/ziparchive.html#ZipArchive::setMtimeIndex)
        — Set the modification time of an entry defined by its index
    -   [ZipArchive::setMtimeName](/class/ziparchive.html#ZipArchive::setMtimeName)
        — Set the modification time of an entry defined by its name
    -   [ZipArchive::setPassword](/class/ziparchive.html#ZipArchive::setPassword)
        — Set the password for the active archive
    -   [ZipArchive::statIndex](/class/ziparchive.html#ZipArchive::statIndex)
        — Get the details of an entry defined by its index
    -   [ZipArchive::statName](/class/ziparchive.html#ZipArchive::statName)
        — Get the details of an entry defined by its name
    -   [ZipArchive::unchangeAll](/class/ziparchive.html#ZipArchive::unchangeAll)
        — Undo all changes done in the archive
    -   [ZipArchive::unchangeArchive](/class/ziparchive.html#ZipArchive::unchangeArchive)
        — Revert all global changes done in the archive
    -   [ZipArchive::unchangeIndex](/class/ziparchive.html#ZipArchive::unchangeIndex)
        — Revert all changes done to an entry at the given index
    -   [ZipArchive::unchangeName](/class/ziparchive.html#ZipArchive::unchangeName)
        — Revert all changes done to an entry with the given name
-   [Zip Functions](/ref/zip.html)
    -   [zip\_close](/ref/zip.html#zip_close) — Close a ZIP file archive
    -   [zip\_entry\_close](/ref/zip.html#zip_entry_close) — Close a
        directory entry
    -   [zip\_entry\_compressedsize](/ref/zip.html#zip_entry_compressedsize)
        — Retrieve the compressed size of a directory entry
    -   [zip\_entry\_compressionmethod](/ref/zip.html#zip_entry_compressionmethod)
        — Retrieve the compression method of a directory entry
    -   [zip\_entry\_filesize](/ref/zip.html#zip_entry_filesize) —
        Retrieve the actual file size of a directory entry
    -   [zip\_entry\_name](/ref/zip.html#zip_entry_name) — Retrieve the
        name of a directory entry
    -   [zip\_entry\_open](/ref/zip.html#zip_entry_open) — Open a
        directory entry for reading
    -   [zip\_entry\_read](/ref/zip.html#zip_entry_read) — Read from an
        open directory entry
    -   [zip\_open](/ref/zip.html#zip_open) — Open a ZIP file archive
    -   [zip\_read](/ref/zip.html#zip_read) — Read next entry in a ZIP
        file archive

Introduction
------------

A file archive, compressed with Zip.

Class synopsis
--------------

**ZipArchive**

<span class="ooclass"> class **ZipArchive** </span> <span
class="oointerface">implements <span
class="interfacename">Countable</span> </span> {

/\* Properties \*/

<span class="type">int</span>`$lastId`;

<span class="type">int</span>`$status`;

<span class="type">int</span>`$statusSys`;

<span class="type">int</span>`$numFiles`;

<span class="type">string</span>`$filename`;

<span class="type">string</span>`$comment`;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addEmptyDir</span> ( <span
class="methodparam"><span class="type">string</span> `$dirname`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addFile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$entryname`<span class="initializer"> = **`NULL`**</span></span> \[,
<span class="methodparam"><span class="type">int</span> `$start`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = ZipArchive::FL\_OVERWRITE</span></span> \]\]\]\]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">addFromString</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$contents`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
ZipArchive::FL\_OVERWRITE</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">addGlob</span> ( <span class="methodparam"><span
class="type">string</span> `$pattern`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">addPattern</span> ( <span class="methodparam"><span
class="type">string</span> `$pattern`</span> \[, <span
class="methodparam"><span class="type">string</span> `$path`<span
class="initializer"> = "."</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">close</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deleteIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">deleteName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">extractTo</span> ( <span
class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$entries`</span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getArchiveComment</span> (\[ <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getCommentIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getCommentName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">GetExternalAttributesIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">int</span> `&$opsys`</span>
, <span class="methodparam"><span class="type">int</span>
`&$attr`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getExternalAttributesName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `&$opsys`</span>
, <span class="methodparam"><span class="type">int</span>
`&$attr`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getFromIndex</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> \[, <span
class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \]\] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getFromName</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \]\] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getNameIndex</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getStatusString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">resource</span><span class="type">false</span></span> <span
class="methodname">getStream</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isCompressionMethodSupported</span> ( <span
class="methodparam"><span class="type">int</span> `$method`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$encode`<span
class="initializer"> = true</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isEncryptionMethodSupported</span> ( <span
class="methodparam"><span class="type">int</span> `$method`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$encode`<span
class="initializer"> = true</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">locateName</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">open</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">registerCancelCallback</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">registerProgressCallback</span> ( <span
class="methodparam"><span class="type">float</span> `$rate`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">renameIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">string</span>
`$newname`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">renameName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$newname`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">replaceFile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">int</span>
`$index`</span> \[, <span class="methodparam"><span
class="type">int</span> `$start`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$length`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setArchiveComment</span> ( <span
class="methodparam"><span class="type">string</span> `$comment`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setCommentIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">string</span>
`$comment`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setCommentName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$comment`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setCompressionIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">int</span>
`$comp_method`</span> \[, <span class="methodparam"><span
class="type">int</span> `$comp_flags`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setCompressionName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span>
`$comp_method`</span> \[, <span class="methodparam"><span
class="type">int</span> `$comp_flags`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setEncryptionIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">string</span>
`$method`</span> \[, <span class="methodparam"><span
class="type">string</span> `$password`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setEncryptionName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$method`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$password`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setExternalAttributesIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">int</span> `$opsys`</span>
, <span class="methodparam"><span class="type">int</span> `$attr`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setExternalAttributesName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$opsys`</span>
, <span class="methodparam"><span class="type">int</span> `$attr`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setMtimeIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setMtimeName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setPassword</span> ( <span
class="methodparam"><span class="type">string</span> `$password`</span>
)

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">statIndex</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">statName</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unchangeAll</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unchangeArchive</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unchangeIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unchangeName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

}

Properties
----------

`lastId`  
Index value of last added entry (file or directory). Available as of PHP
8.0.0 and PECL zip 1.18.0.

`status`  
Status of the Zip Archive. Available for closed archive, as of PHP 8.0.0
and PECL zip 1.18.0.

`statusSys`  
System status of the Zip Archive. Available for closed archive, as of
PHP 8.0.0 and PECL zip 1.18.0.

`numFiles`  
Number of files in archive

`filename`  
File name in the file system

`comment`  
Comment for the archive

ZipArchive::addEmptyDir
=======================

Add a new directory

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::addEmptyDir</span> ( <span
class="methodparam"><span class="type">string</span> `$dirname`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = 0</span></span> \] )

Adds an empty directory in the archive.

### Parameters

`dirname`  
The directory to add.

`flags`  
Bitmask consisting of **`ZipArchive::FL_ENC_GUESS`**,
**`ZipArchive::FL_ENC_UTF_8`**, **`ZipArchive::FL_ENC_CP437`**. The
behaviour of these constants is described on the
<a href="/zip/constants.html" class="link">ZIP constants</a> page.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version        | Description        |
|----------------|--------------------|
| 8.0.0 / 1.18.0 | `flags` was added. |

### Examples

**Example \#1 Create a new directory in an archive**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test.zip') === TRUE) {
    if($zip->addEmptyDir('newDirectory')) {
        echo 'Created a new root directory';
    } else {
        echo 'Could not create the directory';
    }
    $zip->close();
} else {
    echo 'failed';
}
?>
```

ZipArchive::addFile
===================

Adds a file to a ZIP archive from the given path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::addFile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$entryname`<span class="initializer"> = **`NULL`**</span></span> \[,
<span class="methodparam"><span class="type">int</span> `$start`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = ZipArchive::FL\_OVERWRITE</span></span> \]\]\]\]
)

Adds a file to a ZIP archive from a given path.

> **Note**: <span class="simpara">For maximum portability, it is
> recommended to always use forward slashes (*/*) as directory separator
> in ZIP filenames.</span>

### Parameters

`filename`  
The path to the file to add.

`entryname`  
If supplied, this is the local name inside the ZIP archive that will
override the `filename`.

`start`  
For partial copy, start position.

`length`  
For partial copy, length to be copied, if 0 or -1 the whole file
(starting from `start`) is used.

`flags`  
Bitmask consisting of **`ZipArchive::FL_OVERWRITE`**,
**`ZipArchive::FL_ENC_GUESS`**, **`ZipArchive::FL_ENC_UTF_8`**,
**`ZipArchive::FL_ENC_CP437`**. The behaviour of these constants is
described on the
<a href="/zip/constants.html" class="link">ZIP constants</a> page.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version        | Description        |
|----------------|--------------------|
| 8.0.0 / 1.18.0 | `flags` was added. |

### Examples

This example opens a ZIP file archive `test.zip` and add the file
`/path/to/index.txt`. as `newname.txt`.

**Example \#1 Open and add**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test.zip') === TRUE) {
    $zip->addFile('/path/to/index.txt', 'newname.txt');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

### Notes

> **Note**:
>
> When a file is set to be added to the archive, PHP will lock the file.
> The lock is only released once the <span
> class="classname">ZipArchive</span> object has been closed, either via
> <span class="methodname">ZipArchive::close</span> or the <span
> class="classname">ZipArchive</span> object being destroyed. This may
> prevent you from being able to delete the file being added until after
> the lock has been released.

### See Also

-   <span class="methodname">ZipArchive::replaceFile</span>

ZipArchive::addFromString
=========================

Add a file to a ZIP archive using its contents

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::addFromString</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$contents`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
ZipArchive::FL\_OVERWRITE</span></span> \] )

Add a file to a ZIP archive using its contents.

> **Note**: <span class="simpara">For maximum portability, it is
> recommended to always use forward slashes (*/*) as directory separator
> in ZIP filenames.</span>

### Parameters

`name`  
The name of the entry to create.

`contents`  
The contents to use to create the entry. It is used in a binary safe
mode.

`flags`  
Bitmask consisting of **`ZipArchive::FL_OVERWRITE`**,
**`ZipArchive::FL_ENC_GUESS`**, **`ZipArchive::FL_ENC_UTF_8`**,
**`ZipArchive::FL_ENC_CP437`**. The behaviour of these constants is
described on the
<a href="/zip/constants.html" class="link">ZIP constants</a> page.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version        | Description        |
|----------------|--------------------|
| 8.0.0 / 1.18.0 | `flags` was added. |

### Examples

**Example \#1 Add an entry to a new archive**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip', ZipArchive::CREATE);
if ($res === TRUE) {
    $zip->addFromString('test.txt', 'file content goes here');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

**Example \#2 Add file to a directory inside an archive**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test.zip') === TRUE) {
    $zip->addFromString('dir/test.txt', 'file content goes here');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::addGlob
===================

Add files from a directory by glob pattern

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::addGlob</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

Add files from a directory which match the glob `pattern`.

> **Note**: <span class="simpara">For maximum portability, it is
> recommended to always use forward slashes (*/*) as directory separator
> in ZIP filenames.</span>

### Parameters

`pattern`  
A <span class="function">glob</span> pattern against which files will be
matched.

`flags`  
A bit mask of *glob()* flags.

`options`  
An associative array of options. Available options are:

-   *"add\_path"*

    Prefix to prepend when translating to the local path of the file
    within the archive. This is applied after any remove operations
    defined by the *"remove\_path"* or *"remove\_all\_path"* options.

-   *"remove\_path"*

    Prefix to remove from matching file paths before adding to the
    archive.

-   *"remove\_all\_path"*

    **`TRUE`** to use the file name only and add to the root of the
    archive.

-   *"flags"*

    Bitmask consisting of **`ZipArchive::FL_OVERWRITE`**,
    **`ZipArchive::FL_ENC_GUESS`**, **`ZipArchive::FL_ENC_UTF_8`**,
    **`ZipArchive::FL_ENC_CP437`**. The behaviour of these constants is
    described on the
    <a href="/zip/constants.html" class="link">ZIP constants</a> page.

-   *"comp\_method"*

    Compression method, one of the **`ZipArchive::CM_*`** constants, see
    <a href="/zip/constants.html" class="link">ZIP constants</a> page.

-   *"comp\_flags"*

    Compression level.

-   *"enc\_method"*

    Encryption method, one of the **`ZipArchive::EM_*`** constants, see
    <a href="/zip/constants.html" class="link">ZIP constants</a> page.

-   *"enc\_password"*

    Password used for encryption.

### Return Values

An <span class="type">array</span> of added files on success or
**`FALSE`** on failure

### Changelog

| Version        | Description                                                                                       |
|----------------|---------------------------------------------------------------------------------------------------|
| 8.0.0 / 1.18.0 | *"flags"* in `options` was added.                                                                 |
| 8.0.0 / 1.18.1 | *"comp\_method"*, *"comp\_flags"*, *"enc\_method"* and *"enc\_password"* in `options` were added. |

### Examples

**Example \#1 <span class="methodname">ZipArchive::addGlob</span>
example**

Add all php scripts and text files from current working directory

``` php
<?php
$zip = new ZipArchive();
$ret = $zip->open('application.zip', ZipArchive::CREATE | ZipArchive::OVERWRITE);
if ($ret !== TRUE) {
    printf('Failed with code %d', $ret);
} else {
    $options = array('add_path' => 'sources/', 'remove_all_path' => TRUE);
    $zip->addGlob('*.{php,txt}', GLOB_BRACE, $options);
    $zip->close();
}
?>
```

### See Also

-   <span class="methodname">ZipArchive::addFile</span>
-   <span class="methodname">ZipArchive::addPattern</span>

ZipArchive::addPattern
======================

Add files from a directory by PCRE pattern

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::addPattern</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$path`<span class="initializer"> = "."</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

Add files from a directory which match the regular expression `pattern`.
The operation is not recursive. The pattern will be matched against the
file name only.

### Parameters

`pattern`  
A <a href="/book/pcre.html" class="link">PCRE</a> pattern against which
files will be matched.

`path`  
The directory that will be scanned. Defaults to the current working
directory.

`options`  
An associative array of options accepted by <span
class="methodname">ZipArchive::addGlob</span>.

### Return Values

An <span class="type">array</span> of added files on success or
**`FALSE`** on failure

### Examples

**Example \#1 <span class="methodname">ZipArchive::addPattern</span>
example**

Add all php scripts and text files from current directory

``` php
<?php
$zip = new ZipArchive();
$ret = $zip->open('application.zip', ZipArchive::CREATE | ZipArchive::OVERWRITE);
if ($ret !== TRUE) {
    printf('Failed with code %d', $ret);
} else {
    $directory = realpath('.');
    $options = array('add_path' => 'sources/', 'remove_path' => $directory);
    $zip->addPattern('/\.(?:php|txt)$/', $directory, $options);
    $zip->close();
}
?>
```

### See Also

-   <span class="methodname">ZipArchive::addFile</span>
-   <span class="methodname">ZipArchive::addGlob</span>

ZipArchive::close
=================

Close the active archive (opened or newly created)

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::close</span> ( <span
class="methodparam">void</span> )

Close opened or created archive and save changes. This method is
automatically called at the end of the script.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

ZipArchive::count
=================

Counts the number of files in the archive

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ZipArchive::count</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the number of files in the archive.

ZipArchive::deleteIndex
=======================

Delete an entry in the archive using its index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::deleteIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Delete an entry in the archive using its index.

### Parameters

`index`  
Index of the entry to delete.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Delete file from archive using its index**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test.zip') === TRUE) {
    $zip->deleteIndex(2);
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::deleteName
======================

Delete an entry in the archive using its name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::deleteName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Delete an entry in the archive using its name.

### Parameters

`name`  
Name of the entry to delete.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Deleting a file and directory from an archive, using
names**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test1.zip') === TRUE) {
    $zip->deleteName('testfromfile.php');
    $zip->deleteName('testDir/');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::extractTo
=====================

Extract the archive contents

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::extractTo</span> ( <span
class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$entries`</span> \] )

Extract the complete archive or the given files to the specified
destination.

**Warning**

The default permissions for extracted files and directories give the
widest possible access. This can be restricted by setting the current
umask, which can be changed using <span class="function">umask</span>.

### Parameters

`destination`  
Location where to extract the files.

`entries`  
The entries to extract. It accepts either a single entry name or an
array of names.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Extract all entries**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test.zip') === TRUE) {
    $zip->extractTo('/my/destination/dir/');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

**Example \#2 Extract two entries**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test_im.zip');
if ($res === TRUE) {
    $zip->extractTo('/my/destination/dir/', array('pear_item.gif', 'testfromfile.php'));
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::getArchiveComment
=============================

Returns the Zip archive comment

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::getArchiveComment</span> (\[ <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

Returns the Zip archive comment.

### Parameters

`flags`  
If flags is set to **`ZipArchive::FL_UNCHANGED`**, the original
unchanged comment is returned.

### Return Values

Returns the Zip archive comment or **`FALSE`** on failure.

### Examples

**Example \#1 Dump an archive comment**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test_with_comment.zip');
if ($res === TRUE) {
    var_dump($zip->getArchiveComment());
    /* Or using the archive property */
    var_dump($zip->comment);
} else {
    echo 'failed, code:' . $res;
}
?>
```

ZipArchive::getCommentIndex
===========================

Returns the comment of an entry using the entry index

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::getCommentIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

Returns the comment of an entry using the entry index.

### Parameters

`index`  
Index of the entry

`flags`  
If flags is set to **`ZipArchive::FL_UNCHANGED`**, the original
unchanged comment is returned.

### Return Values

Returns the comment on success or **`FALSE`** on failure.

### Examples

**Example \#1 Dump an entry comment**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test1.zip');
if ($res === TRUE) {
    var_dump($zip->getCommentIndex(1));
} else {
    echo 'failed, code:' . $res;
}
?>
```

ZipArchive::getCommentName
==========================

Returns the comment of an entry using the entry name

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::getCommentName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

Returns the comment of an entry using the entry name.

### Parameters

`name`  
Name of the entry

`flags`  
If flags is set to **`ZipArchive::FL_UNCHANGED`**, the original
unchanged comment is returned.

### Return Values

Returns the comment on success or **`FALSE`** on failure.

### Examples

**Example \#1 Dump an entry comment**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test1.zip');
if ($res === TRUE) {
    var_dump($zip->getCommentName('test/entry1.txt'));
} else {
    echo 'failed, code:' . $res;
}
?>
```

ZipArchive::getExternalAttributesIndex
======================================

Retrieve the external attributes of an entry defined by its index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::GetExternalAttributesIndex</span> (
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">int</span>
`&$opsys`</span> , <span class="methodparam"><span
class="type">int</span> `&$attr`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

Retrieve the external attributes of an entry defined by its index.

### Parameters

`index`  
Index of the entry.

`opsys`  
On success, receive the operating system code defined by one of the
ZipArchive::OPSYS\_ constants.

`attr`  
On success, receive the external attributes. Value depends on operating
system.

`flags`  
If flags is set to **`ZipArchive::FL_UNCHANGED`**, the original
unchanged attributes are returned.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

This example extract all the entries of a ZIP archive `test.zip` and set
the Unix rights from external attributes.

**Example \#1 Extract all entries with Unix rights**

``` php
<?php
$zip = new ZipArchive();
if ($zip->open('test.zip') === TRUE) {
    for ($idx=0 ; $s = $zip->statIndex($idx) ; $idx++) {
        if ($zip->extractTo('.', $s['name'])) {
            if ($zip->getExternalAttributesIndex($idx, $opsys, $attr) 
                && $opsys==ZipArchive::OPSYS_UNIX) {
               chmod($s['name'], ($attr >> 16) & 0777);
            }
        }
    }
    $zip->close();
    echo "Ok\n";
} else {
    echo "KO\n";
}
?>
```

ZipArchive::getExternalAttributesName
=====================================

Retrieve the external attributes of an entry defined by its name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::getExternalAttributesName</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span class="type">int</span>
`&$opsys`</span> , <span class="methodparam"><span
class="type">int</span> `&$attr`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

Retrieve the external attributes of an entry defined by its name.

### Parameters

`name`  
Name of the entry.

`opsys`  
On success, receive the operating system code defined by one of the
ZipArchive::OPSYS\_ constants.

`attr`  
On success, receive the external attributes. Value depends on operating
system.

`flags`  
If flags is set to **`ZipArchive::FL_UNCHANGED`**, the original
unchanged attributes are returned.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

ZipArchive::getFromIndex
========================

Returns the entry contents using its index

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::getFromIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \]\] )

Returns the entry contents using its index.

### Parameters

`index`  
Index of the entry

`length`  
The length to be read from the entry. If *0*, then the entire entry is
read.

`flags`  
The flags to use to open the archive. the following values may be ORed
to it.

-   **`ZipArchive::FL_UNCHANGED`**

-   **`ZipArchive::FL_COMPRESSED`**

### Return Values

Returns the contents of the entry on success or **`FALSE`** on failure.

### Examples

**Example \#1 Get the file contents**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test.zip') === TRUE) {
    echo $zip->getFromIndex(2);
    $zip->close();
} else {
    echo 'failed';
}
?>
```

### See Also

-   <span class="methodname">ZipArchive::getFromName</span>

ZipArchive::getFromName
=======================

Returns the entry contents using its name

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::getFromName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \]\] )

Returns the entry contents using its name.

### Parameters

`name`  
Name of the entry

`length`  
The length to be read from the entry. If *0*, then the entire entry is
read.

`flags`  
The flags to use to find the entry. The following values may be ORed.

-   **`ZipArchive::FL_UNCHANGED`**

-   **`ZipArchive::FL_COMPRESSED`**

-   **`ZipArchive::FL_NOCASE`**

### Return Values

Returns the contents of the entry on success or **`FALSE`** on failure.

### Examples

**Example \#1 Get the file contents**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test1.zip') === TRUE) {
    echo $zip->getFromName('testfromfile.php');
    $zip->close();
} else {
    echo 'failed';
}
?>
```

**Example \#2 Convert an image from a zip entry**

``` php
<?php
$z = new ZipArchive();
if ($z->open(dirname(__FILE__) . '/test_im.zip')) {
    $im_string = $z->getFromName("pear_item.gif");
    $im = imagecreatefromstring($im_string);
    imagepng($im, 'b.png');
}
?>
```

### See Also

-   <span class="methodname">ZipArchive::getFromIndex</span>

ZipArchive::getNameIndex
========================

Returns the name of an entry using its index

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::getNameIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

Returns the name of an entry using its index.

### Parameters

`index`  
Index of the entry.

`flags`  
If flags is set to **`ZipArchive::FL_UNCHANGED`**, the original
unchanged name is returned.

### Return Values

Returns the name on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">ZipArchive::getNameIndex</span>
example**

``` php
<?php
if ($zip->open('test.zip') == TRUE) {
 for ($i = 0; $i < $zip->numFiles; $i++) {
     $filename = $zip->getNameIndex($i);
     // ...
 }
}
?>
```

ZipArchive::getStatusString
===========================

Returns the status error message, system and/or zip messages

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::getStatusString</span> ( <span
class="methodparam">void</span> )

Returns the status error message, system and/or zip messages.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="type">string</span> with the status message on
success or **`FALSE`** on failure.

### Changelog

| Version        | Description                                  |
|----------------|----------------------------------------------|
| 8.0.0 / 1.18.0 | This method can be called on closed archive. |

ZipArchive::getStream
=====================

Get a file handler to the entry defined by its name (read only)

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">resource</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::getStream</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Get a file handler to the entry defined by its name. For now it only
supports read operations.

### Parameters

`name`  
The name of the entry to use.

### Return Values

Returns a file pointer (resource) on success or **`FALSE`** on failure.

### Examples

**Example \#1 Get the entry contents with <span
class="function">fread</span> and store it**

``` php
<?php
$contents = '';
$z = new ZipArchive();
if ($z->open('test.zip')) {
    $fp = $z->getStream('test');
    if(!$fp) exit("failed\n");

    while (!feof($fp)) {
        $contents .= fread($fp, 2);
    }

    fclose($fp);
    file_put_contents('t',$contents);
    echo "done.\n";
}
?>
```

**Example \#2 Same as the previous example but with <span
class="function">fopen</span> and the zip stream wrapper**

``` php
<?php
$contents = '';
$fp = fopen('zip://' . dirname(__FILE__) . '/test.zip#test', 'r');
if (!$fp) {
    exit("cannot open\n");
}
while (!feof($fp)) {
    $contents .= fread($fp, 2);
}
echo "$contents\n";
fclose($fp);
echo "done.\n";
?>
```

**Example \#3 Stream wrapper and image, can be used with the xml
function as well**

``` php
<?php
$im = imagecreatefromgif('zip://' . dirname(__FILE__) . '/test_im.zip#pear_item.gif');
imagepng($im, 'a.png');
?>
```

ZipArchive::isCompressionMethodSupported
========================================

Check if a compression method is supported by libzip

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::isCompressionMethodSupported</span>
( <span class="methodparam"><span class="type">int</span>
`$method`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$encode`<span class="initializer"> =
true</span></span> \] )

Check if a compression method is supported by libzip.

### Parameters

`method`  
The compression method, one of the **`ZipArchive::CM_*`** constants.

`encode`  
If **`TRUE`** check for compression, else check for decompression.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> This function is only available if built against libzip ≥ 1.7.0.

### See Also

-   <span class="methodname">ZipArchive::setCompressionIndex</span>
-   <span class="methodname">ZipArchive::setCompressionName</span>

ZipArchive::isEncryptionMethodSupported
=======================================

Check if a encryption method is supported by libzip

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::isEncryptionMethodSupported</span>
( <span class="methodparam"><span class="type">int</span>
`$method`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$encode`<span class="initializer"> =
true</span></span> \] )

Check if a compression method is supported by libzip.

### Parameters

`method`  
The encryption method, one of the **`ZipArchive::EM_*`** constants.

`encode`  
If **`TRUE`** check for encryption, else check for decryption.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> This function is only available if built against libzip ≥ 1.7.0.

### See Also

-   <span class="methodname">ZipArchive::setEncryptionIndex</span>
-   <span class="methodname">ZipArchive::setEncryptionName</span>

ZipArchive::locateName
======================

Returns the index of the entry in the archive

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::locateName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

Locates an entry using its name.

### Parameters

`name`  
The name of the entry to look up

`flags`  
The flags are specified by ORing the following values, or 0 for none of
them.

-   **`ZipArchive::FL_NOCASE`**

-   **`ZipArchive::FL_NODIR`**

### Return Values

Returns the index of the entry on success or **`FALSE`** on failure.

### Examples

**Example \#1 Create an archive and then use it with <span
class="function">ZipArchive::locateName</span>**

``` php
<?php
$file = 'testlocate.zip';

$zip = new ZipArchive;
if ($zip->open($file, ZipArchive::CREATE) !== TRUE) {
    exit('failed');
}

$zip->addFromString('entry1.txt', 'entry #1');
$zip->addFromString('entry2.txt', 'entry #2');
$zip->addFromString('dir/entry2d.txt', 'entry #2');

if ($zip->status !== ZipArchive::ER_OK) {
    echo "failed to write zip\n";
}
$zip->close();

if ($zip->open($file) !== TRUE) {
    exit('failed');
}

echo $zip->locateName('entry1.txt') . "\n";
echo $zip->locateName('eNtry2.txt') . "\n";
echo $zip->locateName('eNtry2.txt', ZipArchive::FL_NOCASE) . "\n";
echo $zip->locateName('enTRy2d.txt', ZipArchive::FL_NOCASE|ZipArchive::FL_NODIR) . "\n";
$zip->close();

?>
```

The above example will output:

    0

    1
    2

ZipArchive::open
================

Open a ZIP file archive

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ZipArchive::open</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`</span> \] )

Opens a new or existing zip archive for reading, writing or modifying.

Since libzip 1.6.0, a empty file is not a valid archive any longer.

### Parameters

`filename`  
The file name of the ZIP archive to open.

`flags`  
The mode to use to open the archive.

-   **`ZipArchive::OVERWRITE`**

-   **`ZipArchive::CREATE`**

-   **`ZipArchive::RDONLY`**

-   **`ZipArchive::EXCL`**

-   **`ZipArchive::CHECKCONS`**

### Return Values

`Error codes`  
Returns **`TRUE`** on success or the error code.

-   **`ZipArchive::ER_EXISTS`**

    File already exists.

-   **`ZipArchive::ER_INCONS`**

    Zip archive inconsistent.

-   **`ZipArchive::ER_INVAL`**

    Invalid argument.

-   **`ZipArchive::ER_MEMORY`**

    Malloc failure.

-   **`ZipArchive::ER_NOENT`**

    No such file.

-   **`ZipArchive::ER_NOZIP`**

    Not a zip archive.

-   **`ZipArchive::ER_OPEN`**

    Can't open file.

-   **`ZipArchive::ER_READ`**

    Read error.

-   **`ZipArchive::ER_SEEK`**

    Seek error.

### Examples

**Example \#1 Open and extract**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip');
if ($res === TRUE) {
    echo 'ok';
    $zip->extractTo('test');
    $zip->close();
} else {
    echo 'failed, code:' . $res;
}
?>
```

**Example \#2 Create an archive**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip', ZipArchive::CREATE);
if ($res === TRUE) {
    $zip->addFromString('test.txt', 'file content goes here');
    $zip->addFile('data.txt', 'entryname.txt');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

**Example \#3 Create an temporary archive**

``` php
<?php
$name = tempnam(sys_get_temp_dir(), "FOO");
$zip = new ZipArchive;
$res = $zip->open($name, ZipArchive::OVERWRITE); /* truncate as empty file is not valid */
if ($res === TRUE) {
    $zip->addFile('data.txt', 'entryname.txt');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::registerCancelCallback
==================================

Register a callback to allow cancellation during archive close.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::registerCancelCallback</span> (
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Register a `callback` function to allow cancellation during archive
close.

### Parameters

`callback`  
If this function return 0 operation will continue, other value it will
be cancelled.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> This function is only available if built against libzip ≥ 1.6.0.

### Examples

This example creates a ZIP file archive `php.zip` and cancel operation
on some run condition.

**Example \#1 Archive a file**

``` php
<?php
$zip = new ZipArchive();
if ($zip->open('php.zip', ZipArchive::CREATE | ZipArchive::OVERWRITE)) {
    $zip->addFile(PHP_BINARY, 'php');
    $zip->registerCancelCallback(function () {
        return ($someruncondition ? -1 : 0);
    });
    $zip->close();
}
```

### See Also

-   <span class="methodname">ZipArchive::registerProgressCallback</span>

ZipArchive::registerProgressCallback
====================================

Register a callback to provide updates during archive close.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::registerProgressCallback</span> (
<span class="methodparam"><span class="type">float</span> `$rate`</span>
, <span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Register a `callback` function to provide updates during archive close.

### Parameters

`rate`  
Change between each call of the callback (from 0.0 to 1.0).

`callback`  
This function will receive the current `state` as a <span
class="type">float</span> (from 0.0 to 1.0).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> This function is only available if built against libzip ≥ 1.3.0.

### Examples

This example creates a ZIP file archive `php.zip` and show progression.

**Example \#1 Archive a file**

``` php
$zip = new ZipArchive();
if ($zip->open('php.zip', ZipArchive::CREATE | ZipArchive::OVERWRITE)) {
    $zip->addFile(PHP_BINARY, 'php');
    $zip->registerProgressCallback(0.05, function ($r) {
        printf("%d%%\n", $r * 100);
    });
    $zip->close();
}
```

### See Also

-   <span class="methodname">ZipArchive::registerCancelCallback</span>

ZipArchive::renameIndex
=======================

Renames an entry defined by its index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::renameIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">string</span>
`$newname`</span> )

Renames an entry defined by its index.

### Parameters

`index`  
Index of the entry to rename.

`newname`  
New name.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Rename one entry**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip');
if ($res === TRUE) {
    $zip->renameIndex(2,'newname.txt');
    $zip->close();
} else {
    echo 'failed, code:' . $res;
}
?>
```

ZipArchive::renameName
======================

Renames an entry defined by its name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::renameName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$newname`</span> )

Renames an entry defined by its name.

### Parameters

`name`  
Name of the entry to rename.

`newname`  
New name.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Rename one entry**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip');
if ($res === TRUE) {
    $zip->renameName('currentname.txt','newname.txt');
    $zip->close();
} else {
    echo 'failed, code:' . $res;
}
?>
```

ZipArchive::replaceFile
=======================

Replace file in ZIP archive with a given path

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::replaceFile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">int</span>
`$index`</span> \[, <span class="methodparam"><span
class="type">int</span> `$start`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$length`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \]\]\] )

Replace file in ZIP archive with a given path.

> **Note**: <span class="simpara">For maximum portability, it is
> recommended to always use forward slashes (*/*) as directory separator
> in ZIP filenames.</span>

### Parameters

`filename`  
The path to the file to add.

`index`  
The index of the file to be replaced, its name is unchanged.

`start`  
For partial copy, start position.

`length`  
For partial copy, length to be copied, if 0 or -1 the whole file
(starting from `start`) is used.

`flags`  
Bitmask consisting of **`ZipArchive::FL_ENC_GUESS`**,
**`ZipArchive::FL_ENC_UTF_8`**, **`ZipArchive::FL_ENC_CP437`**. The
behaviour of these constants is described on the
<a href="/zip/constants.html" class="link">ZIP constants</a> page.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

This example opens a ZIP file archive `test.zip` and replaces index 1
entry with `/path/to/index.txt`.

**Example \#1 Open and replace**

``` php
<?php
$zip = new ZipArchive;
if ($zip->open('test.zip') === TRUE) {
    $zip->replaceFile('/path/to/index.txt', 1);
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

### See Also

-   <span class="methodname">ZipArchive::addFile</span>

ZipArchive::setArchiveComment
=============================

Set the comment of a ZIP archive

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setArchiveComment</span> ( <span
class="methodparam"><span class="type">string</span> `$comment`</span> )

Set the comment of a ZIP archive.

### Parameters

`comment`  
The contents of the comment.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Create an archive and set a comment**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip', ZipArchive::CREATE);
if ($res === TRUE) {
    $zip->addFromString('test.txt', 'file content goes here');
    $zip->setArchiveComment('new archive comment');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::setCommentIndex
===========================

Set the comment of an entry defined by its index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setCommentIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">string</span>
`$comment`</span> )

Set the comment of an entry defined by its index.

### Parameters

`index`  
Index of the entry.

`comment`  
The contents of the comment.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Open an archive and set a comment for an entry**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip');
if ($res === TRUE) {
    $zip->setCommentIndex(2, 'new entry comment');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::setCommentName
==========================

Set the comment of an entry defined by its name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setCommentName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$comment`</span> )

Set the comment of an entry defined by its name.

### Parameters

`name`  
Name of the entry.

`comment`  
The contents of the comment.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Open an archive and set a comment for an entry**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip');
if ($res === TRUE) {
    $zip->setCommentName('entry1.txt', 'new entry comment');
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::setCompressionIndex
===============================

Set the compression method of an entry defined by its index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setCompressionIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">int</span>
`$comp_method`</span> \[, <span class="methodparam"><span
class="type">int</span> `$comp_flags`<span class="initializer"> =
0</span></span> \] )

Set the compression method of an entry defined by its index.

### Parameters

`index`  
Index of the entry.

`comp_method`  
The compression method, one of the **`ZipArchive::CM_*`** constants.

`comp_flags`  
Compression level.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Add files with different compression methods to an
archive**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip', ZipArchive::CREATE);
if ($res === TRUE) {
    $zip->addFromString('foo', 'Some text');
    $zip->addFromString('bar', 'Some other text');
    $zip->setCompressionIndex(0, ZipArchive::CM_STORE);
    $zip->setCompressionIndex(1, ZipArchive::CM_DEFLATE);
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::setCompressionName
==============================

Set the compression method of an entry defined by its name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setCompressionName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span>
`$comp_method`</span> \[, <span class="methodparam"><span
class="type">int</span> `$comp_flags`<span class="initializer"> =
0</span></span> \] )

Set the compression method of an entry defined by its name.

### Parameters

`name`  
Name of the entry.

`comp_method`  
The compression method, one of the **`ZipArchive::CM_*`** constants.

`comp_flags`  
Compression level.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Add files with different compression methods to an
archive**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip', ZipArchive::CREATE);
if ($res === TRUE) {
    $zip->addFromString('foo', 'Some text');
    $zip->addFromString('bar', 'Some other text');
    $zip->setCompressionName('foo', ZipArchive::CM_STORE);
    $zip->setCompressionName('bar', ZipArchive::CM_DEFLATE);
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

**Example \#2 Add file and set compression method**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip', ZipArchive::CREATE);
if ($res === TRUE) {
    $zip->addFile('foo.jpg', 'bar.jpg');
    $zip->setCompressionName('bar.jpg', ZipArchive::CM_XZ);
    $zip->close();
    echo 'ok';
} else {
    echo 'failed';
}
?>
```

ZipArchive::setEncryptionIndex
==============================

Set the encryption method of an entry defined by its index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setEncryptionIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">string</span>
`$method`</span> \[, <span class="methodparam"><span
class="type">string</span> `$password`</span> \] )

Set the encryption method of an entry defined by its index.

### Parameters

`index`  
Index of the entry.

`method`  
The encryption method defined by one of the ZipArchive::EM\_ constants.

`password`  
Optional password, default used when missing.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> This function is only available if built against libzip ≥ 1.2.0.

### See Also

-   <span class="methodname">ZipArchive::setPassword</span>
-   <span class="methodname">ZipArchive::setEncryptionName</span>

ZipArchive::setEncryptionName
=============================

Set the encryption method of an entry defined by its name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setEncryptionName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$method`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$password`</span> \] )

Set the encryption method of an entry defined by its name.

### Parameters

`name`  
Name of the entry.

`method`  
The encryption method defined by one of the ZipArchive::EM\_ constants.

`password`  
Optional password, default used when missing.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

This example creates a ZIP file archive `test.zip` and add the file
`test.txt` encrypted using the AES 256 method.

**Example \#1 Archive and encrypt a file**

``` php
<?php
$zip = new ZipArchive();
if ($zip->open('test.zip', ZipArchive::CREATE) === TRUE) {
    $zip->setPassword('secret');
    $zip->addFile('text.txt');
    $zip->setEncryptionName('text.txt', ZipArchive::EM_AES_256);
    $zip->close();
    echo "Ok\n";
} else {
    echo "KO\n";
}
?>
```

### Notes

> **Note**:
>
> This function is only available if built against libzip ≥ 1.2.0.

### See Also

-   <span class="methodname">ZipArchive::setPassword</span>
-   <span class="methodname">ZipArchive::setEncryptionIndex</span>

ZipArchive::setExternalAttributesIndex
======================================

Set the external attributes of an entry defined by its index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setExternalAttributesIndex</span> (
<span class="methodparam"><span class="type">int</span> `$index`</span>
, <span class="methodparam"><span class="type">int</span>
`$opsys`</span> , <span class="methodparam"><span
class="type">int</span> `$attr`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

Set the external attributes of an entry defined by its index.

### Parameters

`index`  
Index of the entry.

`opsys`  
The operating system code defined by one of the ZipArchive::OPSYS\_
constants.

`attr`  
The external attributes. Value depends on operating system.

`flags`  
Optional flags. Currently unused.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

ZipArchive::setExternalAttributesName
=====================================

Set the external attributes of an entry defined by its name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setExternalAttributesName</span> (
<span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span class="type">int</span>
`$opsys`</span> , <span class="methodparam"><span
class="type">int</span> `$attr`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

Set the external attributes of an entry defined by its name.

### Parameters

`name`  
Name of the entry.

`opsys`  
The operating system code defined by one of the ZipArchive::OPSYS\_
constants.

`attr`  
The external attributes. Value depends on operating system.

`flags`  
Optional flags. Currently unused.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

This example opens a ZIP file archive `test.zip` and add the file
`test.txt` with its Unix rights as external attributes.

**Example \#1 Archive a file, with its Unix rights**

``` php
<?php
$zip = new ZipArchive();
$stat = stat($filename='test.txt');
if (is_array($stat) && $zip->open('test.zip', ZipArchive::CREATE) === TRUE) {
    $zip->addFile($filename);
    $zip->setExternalAttributesName($filename, ZipArchive::OPSYS_UNIX, $stat['mode'] << 16);
    $zip->close();
    echo "Ok\n";
} else {
    echo "KO\n";
}
?>
```

ZipArchive::setMtimeIndex
=========================

Set the modification time of an entry defined by its index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setMtimeIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \] )

Set the modification time of an entry defined by its index.

### Parameters

`index`  
Index of the entry.

`timestamp`  
The modification time (unix timestamp) of the file.

`flags`  
Optional flags, unused for now.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

This example creates a ZIP file archive `test.zip` and add the file
`test.txt` with its modification date.

**Example \#1 Archive a file**

``` php
<?php
$zip = new ZipArchive();
if ($zip->open('test.zip', ZipArchive::CREATE) === TRUE) {
    $zip->addFile('text.txt');
    $zip->setMtimIndex(0, mktime(0,0,0,12,25,2019));
    $zip->close();
    echo "Ok\n";
} else {
    echo "KO\n";
}
?>
```

### Notes

> **Note**:
>
> This function is only available if built against libzip ≥ 1.0.0.

### See Also

-   <span class="methodname">ZipArchive::setMtimeName</span>

ZipArchive::setMtimeName
========================

Set the modification time of an entry defined by its name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setMtimeName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \] )

Set the modification time of an entry defined by its name.

### Parameters

`name`  
Name of the entry.

`timestamp`  
The modification time (unix timestamp) of the file.

`flags`  
Optional flags, unused for now.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

This example creates a ZIP file archive `test.zip` and add the file
`test.txt` with its modification date.

**Example \#1 Archive a file**

``` php
<?php
$zip = new ZipArchive();
if ($zip->open('test.zip', ZipArchive::CREATE) === TRUE) {
    $zip->addFile('text.txt');
    $zip->setMtimeName('text.txt', mktime(0,0,0,12,25,2019));
    $zip->close();
    echo "Ok\n";
} else {
    echo "KO\n";
}
?>
```

### Notes

> **Note**:
>
> This function is only available if built against libzip ≥ 1.0.0.

### See Also

-   <span class="methodname">ZipArchive::setMtimeIndex</span>

ZipArchive::setPassword
=======================

Set the password for the active archive

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::setPassword</span> ( <span
class="methodparam"><span class="type">string</span> `$password`</span>
)

Sets the password for the active archive.

### Parameters

`password`  
The password to be used for the archive.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> As of PHP 7.2.0 and libzip 1.2.0 the password is used to decompress
> the archive, and is also the default password for <span
> class="methodname">ZipArchive::setEncryptionName</span> and <span
> class="methodname">ZipArchive::setEncryptionIndex</span>. Formerly,
> this function only set the password to be used to decompress the
> archive; it did not turn a non-password-protected <span
> class="classname">ZipArchive</span> into a password-protected <span
> class="classname">ZipArchive</span>.

### See Also

-   <span class="methodname">ZipArchive::setEncryptionIndex</span>
-   <span class="methodname">ZipArchive::setEncryptionName</span>

ZipArchive::statIndex
=====================

Get the details of an entry defined by its index

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::statIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

The function obtains information about the entry defined by its index.

### Parameters

`index`  
Index of the entry

`flags`  
**`ZipArchive::FL_UNCHANGED`** may be ORed to it to request information
about the original file in the archive, ignoring any changes made.

### Return Values

Returns an array containing the entry details or **`FALSE`** on failure.

### Examples

**Example \#1 Dump the stat info of an entry**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip');
if ($res === TRUE) {
    print_r($zip->statIndex(3));
    $zip->close();
} else {
    echo 'failed, code:' . $res;
}
?>
```

The above example will output something similar to:

    Array
    (
        [name] => foobar/baz
        [index] => 3
        [crc] => 499465816
        [size] => 27
        [mtime] => 1123164748
        [comp_size] => 24
        [comp_method] => 8
    )

ZipArchive::statName
====================

Get the details of an entry defined by its name

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">ZipArchive::statName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

The function obtains information about the entry defined by its name.

### Parameters

`name`  
Name of the entry

`flags`  
The flags argument specifies how the name lookup should be done. Also,
**`ZipArchive::FL_UNCHANGED`** may be ORed to it to request information
about the original file in the archive, ignoring any changes made.

-   **`ZipArchive::FL_NOCASE`**

-   **`ZipArchive::FL_NODIR`**

-   **`ZipArchive::FL_UNCHANGED`**

### Return Values

Returns an array containing the entry details or **`FALSE`** on failure.

### Examples

**Example \#1 Dump the stat info of an entry**

``` php
<?php
$zip = new ZipArchive;
$res = $zip->open('test.zip');
if ($res === TRUE) {
    print_r($zip->statName('foobar/baz'));
    $zip->close();
} else {
    echo 'failed, code:' . $res;
}
?>
```

The above example will output something similar to:

    Array
    (
        [name] => foobar/baz
        [index] => 3
        [crc] => 499465816
        [size] => 27
        [mtime] => 1123164748
        [comp_size] => 24
        [comp_method] => 8
    )

ZipArchive::unchangeAll
=======================

Undo all changes done in the archive

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::unchangeAll</span> ( <span
class="methodparam">void</span> )

Undo all changes done in the archive.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

ZipArchive::unchangeArchive
===========================

Revert all global changes done in the archive

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::unchangeArchive</span> ( <span
class="methodparam">void</span> )

Revert all global changes to the archive. For now, this only reverts
archive comment changes.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

ZipArchive::unchangeIndex
=========================

Revert all changes done to an entry at the given index

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::unchangeIndex</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Revert all changes done to an entry at the given index.

### Parameters

`index`  
Index of the entry.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

ZipArchive::unchangeName
========================

Revert all changes done to an entry with the given name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ZipArchive::unchangeName</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Revert all changes done to an entry.

### Parameters

`name`  
Name of the entry.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

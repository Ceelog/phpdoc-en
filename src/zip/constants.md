Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

<span class="classname">ZipArchive</span> uses class constants. There
are three types of constants : Flags (prefixed with *FL\_*), errors
(prefixed with *ER\_*) and mode (no prefix).

**`ZipArchive::CREATE`** (<span class="type">int</span>)  
<span class="simpara"> Create the archive if it does not exist. </span>

**`ZipArchive::OVERWRITE`** (<span class="type">int</span>)  
<span class="simpara"> If archive exists, ignore its current contents.
In other words, handle it the same way as an empty archive. </span>

**`ZipArchive::EXCL`** (<span class="type">int</span>)  
<span class="simpara"> Error if archive already exists. </span>

**`ZipArchive::RDONLY`** (<span class="type">int</span>)  
<span class="simpara"> Open archive in read only mode. Available as of
PHP 7.4.3 and PECL zip 1.17.1, respectively, if built against libzip ≥
1.0.0. </span>

**`ZipArchive::CHECKCONS`** (<span class="type">int</span>)  
<span class="simpara"> Perform additional consistency checks on the
archive, and error if they fail. </span>

**`ZipArchive::FL_NOCASE`** (<span class="type">int</span>)  
<span class="simpara"> Ignore case on name lookup </span>

**`ZipArchive::FL_NODIR`** (<span class="type">int</span>)  
<span class="simpara"> Ignore directory component </span>

**`ZipArchive::FL_COMPRESSED`** (<span class="type">int</span>)  
<span class="simpara"> Read compressed data </span>

**`ZipArchive::FL_UNCHANGED`** (<span class="type">int</span>)  
<span class="simpara"> Use original data, ignoring changes. </span>

**`ZipArchive::FL_RECOMPRESS`** (<span class="type">int</span>)  
<span class="simpara"> Force recompression of data. Available as of PHP
8.0.0 and PECL zip 1.18.0. </span>

**`ZipArchive::FL_ENCRYPTED`** (<span class="type">int</span>)  
<span class="simpara"> Read encrypted data (implies FL\_COMPRESSED).
Available as of PHP 8.0.0 and PECL zip 1.18.0. </span>

**`ZipArchive::FL_OVERWRITE`** (<span class="type">int</span>)  
<span class="simpara"> If file with name exists, overwrite (replace) it.
Available as of PHP 8.0.0 and PECL zip 1.18.0. </span>

**`ZipArchive::FL_LOCAL`** (<span class="type">int</span>)  
<span class="simpara"> In local header. Available as of PHP 8.0.0 and
PECL zip 1.18.0. </span>

**`ZipArchive::ZIP_FL_CENTRAL`** (<span class="type">int</span>)  
<span class="simpara"> In central directory. Available as of PHP 8.0.0
and PECL zip 1.18.0. </span>

**`ZipArchive::FL_ENC_GUESS`** (<span class="type">int</span>)  
<span class="simpara"> Guess string encoding (is default). Available as
of PHP 7.0.8. </span>

**`ZipArchive::FL_ENC_RAW`** (<span class="type">int</span>)  
<span class="simpara"> Get unmodified string. Available as of PHP 7.0.8.
</span>

**`ZipArchive::FL_ENC_STRICT`** (<span class="type">int</span>)  
<span class="simpara"> Follow specification strictly. Available as of
PHP 7.0.8. </span>

**`ZipArchive::FL_ENC_UTF_8`** (<span class="type">int</span>)  
<span class="simpara"> String is UTF-8 encoded. Available as of PHP
7.0.8. </span>

**`ZipArchive::FL_ENC_CP437`** (<span class="type">int</span>)  
<span class="simpara"> String is CP437 encoded. Available as of PHP
7.0.8. </span>

**`ZipArchive::CM_DEFAULT`** (<span class="type">int</span>)  
<span class="simpara"> better of deflate or store. </span>

**`ZipArchive::CM_STORE`** (<span class="type">int</span>)  
<span class="simpara"> stored (uncompressed). </span>

**`ZipArchive::CM_SHRINK`** (<span class="type">int</span>)  
<span class="simpara"> shrunk </span>

**`ZipArchive::CM_REDUCE_1`** (<span class="type">int</span>)  
<span class="simpara"> reduced with factor 1 </span>

**`ZipArchive::CM_REDUCE_2`** (<span class="type">int</span>)  
<span class="simpara"> reduced with factor 2 </span>

**`ZipArchive::CM_REDUCE_3`** (<span class="type">int</span>)  
<span class="simpara"> reduced with factor 3 </span>

**`ZipArchive::CM_REDUCE_4`** (<span class="type">int</span>)  
<span class="simpara"> reduced with factor 4 </span>

**`ZipArchive::CM_IMPLODE`** (<span class="type">int</span>)  
<span class="simpara"> imploded </span>

**`ZipArchive::CM_DEFLATE`** (<span class="type">int</span>)  
<span class="simpara"> deflated </span>

**`ZipArchive::CM_DEFLATE64`** (<span class="type">int</span>)  
<span class="simpara"> deflate64 </span>

**`ZipArchive::CM_PKWARE_IMPLODE`** (<span class="type">int</span>)  
<span class="simpara"> PKWARE imploding </span>

**`ZipArchive::CM_BZIP2`** (<span class="type">int</span>)  
<span class="simpara"> BZIP2 algorithm </span>

**`ZipArchive::CM_LZMA`** (<span class="type">int</span>)  
<span class="simpara"> LZMA algorithm </span>

**`ZipArchive::CM_LZMA2`** (<span class="type">int</span>)  
<span class="simpara"> LZMA2 algorithm. Available as of PHP 7.4.3 and
PECL zip 1.16.0, respectively, if built against libzip ≥ 1.6.0. </span>

**`ZipArchive::CM_ZSTD`** (<span class="type">int</span>)  
<span class="simpara"> Zstandard algorithm. Available as of PHP 8.0.0
and PECL zip 1.19.1, respectively, if built against libzip ≥ 1.8.0.
</span>

**`ZipArchive::CM_XZ`** (<span class="type">int</span>)  
<span class="simpara"> XZ algorithm. Available as of PHP 7.4.3 and PECL
zip 1.16.1, respectively, if built against libzip ≥ 1.6.0. </span>

**`ZipArchive::ER_OK`** (<span class="type">int</span>)  
<span class="simpara"> No error. </span>

**`ZipArchive::ER_MULTIDISK`** (<span class="type">int</span>)  
<span class="simpara"> Multi-disk zip archives not supported. </span>

**`ZipArchive::ER_RENAME`** (<span class="type">int</span>)  
<span class="simpara"> Renaming temporary file failed. </span>

**`ZipArchive::ER_CLOSE`** (<span class="type">int</span>)  
<span class="simpara"> Closing zip archive failed </span>

**`ZipArchive::ER_SEEK`** (<span class="type">int</span>)  
<span class="simpara"> Seek error </span>

**`ZipArchive::ER_READ`** (<span class="type">int</span>)  
<span class="simpara"> Read error </span>

**`ZipArchive::ER_WRITE`** (<span class="type">int</span>)  
<span class="simpara"> Write error </span>

**`ZipArchive::ER_CRC`** (<span class="type">int</span>)  
<span class="simpara"> CRC error </span>

**`ZipArchive::ER_ZIPCLOSED`** (<span class="type">int</span>)  
<span class="simpara"> Containing zip archive was closed </span>

**`ZipArchive::ER_NOENT`** (<span class="type">int</span>)  
<span class="simpara"> No such file. </span>

**`ZipArchive::ER_EXISTS`** (<span class="type">int</span>)  
<span class="simpara"> File already exists </span>

**`ZipArchive::ER_OPEN`** (<span class="type">int</span>)  
<span class="simpara"> Can't open file </span>

**`ZipArchive::ER_TMPOPEN`** (<span class="type">int</span>)  
<span class="simpara"> Failure to create temporary file. </span>

**`ZipArchive::ER_ZLIB`** (<span class="type">int</span>)  
<span class="simpara"> Zlib error </span>

**`ZipArchive::ER_MEMORY`** (<span class="type">int</span>)  
<span class="simpara"> Memory allocation failure </span>

**`ZipArchive::ER_CHANGED`** (<span class="type">string</span>)  
<span class="simpara"> Entry has been changed </span>

**`ZipArchive::ER_COMPNOTSUPP`** (<span class="type">int</span>)  
<span class="simpara"> Compression method not supported. </span>

**`ZipArchive::ER_EOF`** (<span class="type">int</span>)  
<span class="simpara"> Premature EOF </span>

**`ZipArchive::ER_INVAL`** (<span class="type">int</span>)  
<span class="simpara"> Invalid argument </span>

**`ZipArchive::ER_NOZIP`** (<span class="type">int</span>)  
<span class="simpara"> Not a zip archive </span>

**`ZipArchive::ER_INTERNAL`** (<span class="type">int</span>)  
<span class="simpara"> Internal error </span>

**`ZipArchive::ER_INCONS`** (<span class="type">int</span>)  
<span class="simpara"> Zip archive inconsistent </span>

**`ZipArchive::ER_REMOVE`** (<span class="type">int</span>)  
<span class="simpara"> Can't remove file </span>

**`ZipArchive::ER_DELETED`** (<span class="type">int</span>)  
<span class="simpara"> Entry has been deleted </span>

**`ZipArchive::ER_ENCRNOTSUPP`** (<span class="type">int</span>)  
<span class="simpara"> Encryption method not supported. Available as of
PHP 7.4.3 and PECL zip 1.16.1, respectively. </span>

**`ZipArchive::ER_RDONLY`** (<span class="type">int</span>)  
<span class="simpara"> Read-only archive. Available as of PHP 7.4.3 and
PECL zip 1.16.1, respectively. </span>

**`ZipArchive::ER_NOPASSWD`** (<span class="type">int</span>)  
<span class="simpara"> No password provided. Available as of PHP 7.4.3
and PECL zip 1.16.1, respectively. </span>

**`ZipArchive::ER_WRONGPASSWD`** (<span class="type">int</span>)  
<span class="simpara"> Wrong password provided. Available as of PHP
7.4.3 and PECL zip 1.16.1, respectively. </span>

**`ZipArchive::ZIP_ER_OPNOTSUPP`** (<span class="type">int</span>)  
<span class="simpara"> Operation not supported. Available as of PHP
7.4.3 and PECL zip 1.16.1, respectively, if built against libzip ≥
1.0.0. </span>

**`ZipArchive::ZIP_ER_INUSE`** (<span class="type">int</span>)  
<span class="simpara"> Resource still in use. Available as of PHP 7.4.3
and PECL zip 1.16.1, respectively, if built against libzip ≥ 1.0.0.
</span>

**`ZipArchive::ZIP_ER_TELL`** (<span class="type">int</span>)  
<span class="simpara"> Tell error. Available as of PHP 7.4.3 and PECL
zip 1.16.1, respectively, if built against libzip ≥ 1.0.0. </span>

**`ZipArchive::ZIP_ER_COMPRESSED_DATA`** (<span class="type">int</span>)  
<span class="simpara"> Compressed data invalid. Available as of PHP
7.4.3 and PECL zip 1.16.1, respectively, if built against libzip ≥
1.6.0. </span>

**`ZipArchive::ER_CANCELLED`** (<span class="type">int</span>)  
<span class="simpara"> Operation cancelled. Available as of PHP 7.4.3
and PECL zip 1.16.1, respectively, if built against libzip ≥ 1.6.0.
</span>

**`ZipArchive::EM_NONE`** (<span class="type">int</span>)  
<span class="simpara"> No encryption. Available as of PHP 7.2.0 and PECL
zip 1.14.0, respectively. </span>

**`ZipArchive::EM_TRAD_PKWARE`** (<span class="type">int</span>)  
<span class="simpara"> Traditional PKWARE encryption. Available as of
PHP 8.0.0 and PECL zip 1.19.0, respectively. </span>

**`ZipArchive::EM_AES_128`** (<span class="type">int</span>)  
<span class="simpara"> AES 128 encryption. Available as of PHP 7.2.0 and
PECL zip 1.14.0, respectively, if built against libzip ≥ 1.2.0. </span>

**`ZipArchive::EM_AES_192`** (<span class="type">int</span>)  
<span class="simpara"> AES 192 encryption. Available as of PHP 7.2.0 and
PECL zip 1.14.0, respectively, if built against libzip ≥ 1.2.0. </span>

**`ZipArchive::EM_AES_256`** (<span class="type">int</span>)  
<span class="simpara"> AES 256 encryption. Available as of PHP 7.2.0 and
PECL zip 1.14.0, respectively, if built against libzip ≥ 1.2.0. </span>

**`ZipArchive::EM_UNKNOWN`** (<span class="type">int</span>)  
<span class="simpara"> Unknown encryption algorithm. Available as of PHP
8.0.0 and PECL zip 1.19.0, respectively. </span>

**`ZipArchive::LIBZIP_VERSION`** (<span class="type">string</span>)  
<span class="simpara"> Zip library version. Available as of PHP 7.4.3
and PECL zip 1.16.0. </span>

<!-- -->

**`ZipArchive::OPSYS_DOS`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_AMIGA`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_OPENVMS`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_UNIX`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_VM_CMS`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_ATARI_ST`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_OS_2`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_MACINTOSH`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_Z_SYSTEM`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_CPM`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_WINDOWS_NTFS`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_MVS`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_VSE`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_ACORN_RISC`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_VFAT`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_ALTERNATE_MVS`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_BEOS`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_TANDEM`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_OS_400`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_OS_X`** (<span class="type">int</span>)  
**`ZipArchive::OPSYS_DEFAULT`** (<span class="type">int</span>)  
<span class="simpara"> Since PHP 5.6.0, PECL zip 1.12.4 </span>

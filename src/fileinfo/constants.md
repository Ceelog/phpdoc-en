Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`FILEINFO_NONE`** (<span class="type">integer</span>)  
<span class="simpara"> No special handling. </span>

**`FILEINFO_SYMLINK`** (<span class="type">integer</span>)  
<span class="simpara"> Follow symlinks. </span>

**`FILEINFO_MIME_TYPE`** (<span class="type">integer</span>)  
<span class="simpara"> Return the mime type. </span> <span
class="simpara"> Available since PHP 5.3.0. </span>

**`FILEINFO_MIME_ENCODING`** (<span class="type">integer</span>)  
<span class="simpara"> Return the mime encoding of the file. </span>
<span class="simpara"> Available since PHP 5.3.0. </span>

**`FILEINFO_MIME`** (<span class="type">integer</span>)  
<span class="simpara"> Return the mime type and mime encoding as defined
by RFC 2045. </span>

**`FILEINFO_COMPRESS`** (<span class="type">integer</span>)  
<span class="simpara"> Decompress compressed files. </span> <span
class="simpara"> Disabled since PHP 5.3.0 due to thread safety issues.
</span>

**`FILEINFO_DEVICES`** (<span class="type">integer</span>)  
<span class="simpara"> Look at the contents of blocks or character
special devices. </span>

**`FILEINFO_CONTINUE`** (<span class="type">integer</span>)  
<span class="simpara"> Return all matches, not just the first. </span>

**`FILEINFO_PRESERVE_ATIME`** (<span class="type">integer</span>)  
<span class="simpara"> If possible preserve the original access time.
</span>

**`FILEINFO_RAW`** (<span class="type">integer</span>)  
<span class="simpara"> Don't translate unprintable characters to a
*\\ooo* octal representation. </span>

**`FILEINFO_EXTENSION`** (<span class="type">integer</span>)  
<span class="simpara"> Returns the file extension appropriate for the
MIME type detected in the file. </span> <span class="simpara"> For types
that commonly have multiple file extensions, such as *JPEG* images, then
the return value is multiple extensions separated by a forward slash
e.g.: *"jpeg/jpg/jpe/jfif"*. For unknown types not available in the
`magic.mime` database, then return value is *"???"*. </span> <span
class="simpara"> Available since PHP 7.2.0. </span>

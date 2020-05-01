Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`FTP_ASCII`** (<span class="type">integer</span>)  

**`FTP_AUTOSEEK`** (<span class="type">integer</span>)  
See <span class="function">ftp\_set\_option</span> for information.

**`FTP_AUTORESUME`** (<span class="type">integer</span>)  
Automatically determine resume position and start position for GET and
PUT requests (only works if FTP\_AUTOSEEK is enabled)

**`FTP_FAILED`** (<span class="type">integer</span>)  
Asynchronous transfer has failed

**`FTP_FINISHED`** (<span class="type">integer</span>)  
Asynchronous transfer has finished

**`FTP_MOREDATA`** (<span class="type">integer</span>)  
Asynchronous transfer is still active

**`FTP_TEXT`** (<span class="type">integer</span>)  
Alias of **`FTP_ASCII`**.

**`FTP_BINARY`** (<span class="type">integer</span>)  

**`FTP_IMAGE`** (<span class="type">integer</span>)  
Alias of **`FTP_BINARY`**.

**`FTP_TIMEOUT_SEC`** (<span class="type">integer</span>)  
See <span class="function">ftp\_set\_option</span> for information.

**`FTP_USEPASVADDRESS`** (<span class="type">bool</span>)  
See <span class="function">ftp\_set\_option</span> for information.
Available as of PHP 5.6.0.

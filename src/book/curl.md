Client URL Library
==================

**Table of Contents**

-   [Introduction](/intro/curl.html)
-   [Installing/Configuring](/curl/setup.html)
    -   [Requirements](/curl/setup.html#Requirements)
    -   [Installation](/curl/setup.html#Installation)
    -   [Runtime
        Configuration](/curl/setup.html#Runtime%20Configuration)
    -   [Resource Types](/curl/setup.html#Resource%20Types)
-   [Predefined Constants](/curl/constants.html)
-   [Examples](/curl/examples.html)
    -   [Basic curl example](/curl/examples.html#Basic%20curl%20example)
-   [cURL Functions](/ref/curl.html)
    -   [curl\_close](/ref/curl.html#curl_close) — Close a cURL session
    -   [curl\_copy\_handle](/ref/curl.html#curl_copy_handle) — Copy a
        cURL handle along with all of its preferences
    -   [curl\_errno](/ref/curl.html#curl_errno) — Return the last error
        number
    -   [curl\_error](/ref/curl.html#curl_error) — Return a string
        containing the last error for the current session
    -   [curl\_escape](/ref/curl.html#curl_escape) — URL encodes the
        given string
    -   [curl\_exec](/ref/curl.html#curl_exec) — Perform a cURL session
    -   [curl\_file\_create](/ref/curl.html#curl_file_create) — Create a
        CURLFile object
    -   [curl\_getinfo](/ref/curl.html#curl_getinfo) — Get information
        regarding a specific transfer
    -   [curl\_init](/ref/curl.html#curl_init) — Initialize a cURL
        session
    -   [curl\_multi\_add\_handle](/ref/curl.html#curl_multi_add_handle)
        — Add a normal cURL handle to a cURL multi handle
    -   [curl\_multi\_close](/ref/curl.html#curl_multi_close) — Close a
        set of cURL handles
    -   [curl\_multi\_errno](/ref/curl.html#curl_multi_errno) — Return
        the last multi curl error number
    -   [curl\_multi\_exec](/ref/curl.html#curl_multi_exec) — Run the
        sub-connections of the current cURL handle
    -   [curl\_multi\_getcontent](/ref/curl.html#curl_multi_getcontent)
        — Return the content of a cURL handle if CURLOPT\_RETURNTRANSFER
        is set
    -   [curl\_multi\_info\_read](/ref/curl.html#curl_multi_info_read) —
        Get information about the current transfers
    -   [curl\_multi\_init](/ref/curl.html#curl_multi_init) — Returns a
        new cURL multi handle
    -   [curl\_multi\_remove\_handle](/ref/curl.html#curl_multi_remove_handle)
        — Remove a multi handle from a set of cURL handles
    -   [curl\_multi\_select](/ref/curl.html#curl_multi_select) — Wait
        for activity on any curl\_multi connection
    -   [curl\_multi\_setopt](/ref/curl.html#curl_multi_setopt) — Set an
        option for the cURL multi handle
    -   [curl\_multi\_strerror](/ref/curl.html#curl_multi_strerror) —
        Return string describing error code
    -   [curl\_pause](/ref/curl.html#curl_pause) — Pause and unpause a
        connection
    -   [curl\_reset](/ref/curl.html#curl_reset) — Reset all options of
        a libcurl session handle
    -   [curl\_setopt\_array](/ref/curl.html#curl_setopt_array) — Set
        multiple options for a cURL transfer
    -   [curl\_setopt](/ref/curl.html#curl_setopt) — Set an option for a
        cURL transfer
    -   [curl\_share\_close](/ref/curl.html#curl_share_close) — Close a
        cURL share handle
    -   [curl\_share\_errno](/ref/curl.html#curl_share_errno) — Return
        the last share curl error number
    -   [curl\_share\_init](/ref/curl.html#curl_share_init) — Initialize
        a cURL share handle
    -   [curl\_share\_setopt](/ref/curl.html#curl_share_setopt) — Set an
        option for a cURL share handle
    -   [curl\_share\_strerror](/ref/curl.html#curl_share_strerror) —
        Return string describing the given error code
    -   [curl\_strerror](/ref/curl.html#curl_strerror) — Return string
        describing the given error code
    -   [curl\_unescape](/ref/curl.html#curl_unescape) — Decodes the
        given URL encoded string
    -   [curl\_version](/ref/curl.html#curl_version) — Gets cURL version
        information
-   [CurlHandle](/class/curlhandle.html) — The CurlHandle class
-   [CurlMultiHandle](/class/curlmultihandle.html) — The CurlMultiHandle
    class
-   [CurlShareHandle](/class/curlsharehandle.html) — The CurlShareHandle
    class
-   [CURLFile](/class/curlfile.html) — The CURLFile class
    -   [CURLFile::\_\_construct](/class/curlfile.html#CURLFile::__construct)
        — Create a CURLFile object
    -   [CURLFile::getFilename](/class/curlfile.html#CURLFile::getFilename)
        — Get file name
    -   [CURLFile::getMimeType](/class/curlfile.html#CURLFile::getMimeType)
        — Get MIME type
    -   [CURLFile::getPostFilename](/class/curlfile.html#CURLFile::getPostFilename)
        — Get file name for POST
    -   [CURLFile::setMimeType](/class/curlfile.html#CURLFile::setMimeType)
        — Set MIME type
    -   [CURLFile::setPostFilename](/class/curlfile.html#CURLFile::setPostFilename)
        — Set file name for POST

Introduction
------------

A fully opaque class which replaces *curl* resources as of PHP 8.0.0.

Class synopsis
--------------

**CurlHandle**

<span class="ooclass"> <span class="modifier">final</span> class
**CurlHandle** </span> {

}

Introduction
------------

A fully opaque class which replaces *curl\_multi* resources as of PHP
8.0.0.

Class synopsis
--------------

**CurlMultiHandle**

<span class="ooclass"> <span class="modifier">final</span> class
**CurlMultiHandle** </span> {

}

Introduction
------------

A fully opaque class which replaces *curl\_share* resources as of PHP
8.0.0.

Class synopsis
--------------

**CurlShareHandle**

<span class="ooclass"> <span class="modifier">final</span> class
**CurlShareHandle** </span> {

}

Introduction
------------

<span class="classname">CURLFile</span> should be used to upload a file
with **`CURLOPT_POSTFIELDS`**.

Unserialization of <span class="classname">CURLFile</span> instances is
not allowed. As of PHP 7.4.0, serialization is forbidden in the first
place.

Class synopsis
--------------

**CURLFile**

<span class="ooclass"> class **CURLFile** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span class="type">mixed</span>
`$name` ;

<span class="modifier">public</span> <span class="type">mixed</span>
`$mime` ;

<span class="modifier">public</span> <span class="type">mixed</span>
`$postname` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$mime_type`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$posted_filename`<span class="initializer"> = **`null`**</span></span>
\]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFilename</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getMimeType</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getPostFilename</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setMimeType</span> ( <span
class="methodparam"><span class="type">string</span> `$mime_type`</span>
)

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setPostFilename</span> ( <span
class="methodparam"><span class="type">string</span>
`$posted_filename`</span> )

}

Properties
----------

`name`  
Name of the file to be uploaded.

`mime`  
MIME type of the file (default is *application/octet-stream*).

`postname`  
The name of the file in the upload data (defaults to the `name`
property).

See Also
--------

-   <span class="function">curl\_setopt</span>

CURLFile::\_\_construct
=======================

curl\_file\_create
==================

Create a CURLFile object

### Description

Object oriented style

<span class="modifier">public</span> <span
class="methodname">CURLFile::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$mime_type`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$posted_filename`<span class="initializer"> = **`null`**</span></span>
\]\] )

Procedural style

<span class="type">CURLFile</span> <span
class="methodname">curl\_file\_create</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$mime_type`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$posted_filename`<span class="initializer"> = **`null`**</span></span>
\]\] )

Creates a <span class="classname">CURLFile</span> object, used to upload
a file with **`CURLOPT_POSTFIELDS`**.

### Parameters

`filename`  
Path to the file which will be uploaded.

`mime_type`  
Mimetype of the file.

`posted_filename`  
Name of the file to be used in the upload data.

### Return Values

Returns a <span class="classname">CURLFile</span> object.

### Changelog

| Version | Description                                                                           |
|---------|---------------------------------------------------------------------------------------|
| 8.0.0   | `mime_type` and `posted_filename` are nullable now; previously their default was *0*. |

### Examples

**Example \#1 <span class="function">CURLFile::\_\_construct</span>
example**

Object oriented style

``` php
<?php
/* http://example.com/upload.php:
<?php var_dump($_FILES); ?>
*/

// Create a cURL handle
$ch = curl_init('http://example.com/upload.php');

// Create a CURLFile object
$cfile = new CURLFile('cats.jpg','image/jpeg','test_name');

// Assign POST data
$data = array('test_file' => $cfile);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);

// Execute the handle
curl_exec($ch);
?>
```

Procedural style

``` php
<?php
/* http://example.com/upload.php:
<?php var_dump($_FILES); ?>
*/

// Create a cURL handle
$ch = curl_init('http://example.com/upload.php');

// Create a CURLFile object
$cfile = curl_file_create('cats.jpg','image/jpeg','test_name');

// Assign POST data
$data = array('test_file' => $cfile);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);

// Execute the handle
curl_exec($ch);
?>
```

The above example will output:

    array(1) {
      ["test_file"]=>
      array(5) {
        ["name"]=>
        string(9) "test_name"
        ["type"]=>
        string(10) "image/jpeg"
        ["tmp_name"]=>
        string(14) "/tmp/phpPC9Kbx"
        ["error"]=>
        int(0)
        ["size"]=>
        int(46334)
      }
    }

**Example \#2 <span class="function">CURLFile::\_\_construct</span>
uploading multiple files example**

Object oriented style

``` php
<?php
$request = curl_init('http://www.example.com/upload.php');
curl_setopt($request, CURLOPT_POST, true);
curl_setopt($request, 
CURLOPT_SAFE_UPLOAD, true); curl_setopt(
    $request,
    CURLOPT_POSTFIELDS,
    [
        'blob[0]' => new CURLFile(realpath('first-file.jpg'), 'image/jpeg'),
        'blob[1]' => new CURLFile(realpath('second-file.txt'), 'text/plain'),
        'blob[2]' => new CURLFile(realpath('third-file.exe'), 'application/octet-stream'),
    ] );
curl_setopt($request, CURLOPT_RETURNTRANSFER, true);

echo curl_exec($request);

var_dump(curl_getinfo($request));

curl_close($request);
```

Procedural style

``` php
<?php
// procedural
$request = curl_init('http://www.example.com/upload.php');
curl_setopt($request, CURLOPT_POST, true); 
curl_setopt($request, CURLOPT_SAFE_UPLOAD, true); curl_setopt(
    $request,
    CURLOPT_POSTFIELDS,
    [
        'blob[0]' => curl_file_create(realpath('first-file.jpg'), 'image/jpeg'),
        'blob[1]' => curl_file_create(realpath('second-file.txt'), 'text/plain'),
        'blob[2]' => curl_file_create(realpath('third-file.exe'), 'application/octet-stream'),
    ] );
curl_setopt($request, CURLOPT_RETURNTRANSFER, true);

echo curl_exec($request);

var_dump(curl_getinfo($request));

curl_close($request);
```

The above example will output:

    array(26) {
      ["url"]=>
      string(31) "http://www.example.com/upload.php"
      ["content_type"]=>
      string(24) "text/html; charset=UTF-8"
      ["http_code"]=>
      int(200)
      ["header_size"]=>
      int(198)
      ["request_size"]=>
      int(196)
      ["filetime"]=>
      int(-1)
      ["ssl_verify_result"]=>
      int(0)
      ["redirect_count"]=>
      int(0)
      ["total_time"]=>
      float(0.060062)
      ["namelookup_time"]=>
      float(0.028575)
      ["connect_time"]=>
      float(0.029011)
      ["pretransfer_time"]=>
      float(0.029121)
      ["size_upload"]=>
      float(3230730)
      ["size_download"]=>
      float(811)
      ["speed_download"]=>
      float(13516)
      ["speed_upload"]=>
      float(53845500)
      ["download_content_length"]=>
      float(811)
      ["upload_content_length"]=>
      float(3230730)
      ["starttransfer_time"]=>
      float(0.030355)
      ["redirect_time"]=>
      float(0)
      ["redirect_url"]=>
      string(0) ""
      ["primary_ip"]=>
      string(13) "0.0.0.0"
      ["certinfo"]=>
      array(0) {
      }
      ["primary_port"]=>
      int(80)
      ["local_ip"]=>
      string(12) "0.0.0.0"
      ["local_port"]=>
      int(34856)
    }

### See Also

-   <span class="function">curl\_setopt</span>

CURLFile::getFilename
=====================

Get file name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">CURLFile::getFilename</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns file name.

CURLFile::getMimeType
=====================

Get MIME type

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">CURLFile::getMimeType</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns MIME type.

CURLFile::getPostFilename
=========================

Get file name for POST

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">CURLFile::getPostFilename</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns file name for POST.

CURLFile::setMimeType
=====================

Set MIME type

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CURLFile::setMimeType</span> ( <span
class="methodparam"><span class="type">string</span> `$mime_type`</span>
)

### Parameters

`mime_type`  
MIME type to be used in POST data.

### Return Values

No value is returned.

CURLFile::setPostFilename
=========================

Set file name for POST

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CURLFile::setPostFilename</span> ( <span
class="methodparam"><span class="type">string</span>
`$posted_filename`</span> )

### Parameters

`posted_filename`  
Filename to be used in POST data.

### Return Values

No value is returned.

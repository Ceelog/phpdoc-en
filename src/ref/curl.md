curl\_close
===========

Close a cURL session

### Description

<span class="type">void</span> <span
class="methodname">curl\_close</span> ( <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> )

Closes a cURL session and frees all resources. The cURL handle,
`handle`, is also deleted.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Initializing a new cURL session and fetching a web page**

``` php
<?php
// create a new cURL resource
$ch = curl_init();

// set URL and other appropriate options
curl_setopt($ch, CURLOPT_URL, "http://www.example.com/");
curl_setopt($ch, CURLOPT_HEADER, 0);

// grab URL and pass it to the browser
curl_exec($ch);

// close cURL resource, and free up system resources
curl_close($ch);
?>
```

### See Also

-   <span class="function">curl\_init</span>
-   <span class="function">curl\_multi\_close</span>

curl\_copy\_handle
==================

Copy a cURL handle along with all of its preferences

### Description

<span class="type"><span class="type">CurlHandle</span><span
class="type">false</span></span> <span
class="methodname">curl\_copy\_handle</span> ( <span
class="methodparam"><span class="type">CurlHandle</span>
`$handle`</span> )

Copies a cURL handle keeping the same preferences.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

Returns a new cURL handle, or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected.                  |
| 8.0.0   | On success, this function returns a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was returned. |

### Examples

**Example \#1 Copying a cURL handle**

``` php
<?php
// create a new cURL resource
$ch = curl_init();

// set URL and other appropriate options
curl_setopt($ch, CURLOPT_URL, 'http://www.example.com/');
curl_setopt($ch, CURLOPT_HEADER, 0);

// copy the handle
$ch2 = curl_copy_handle($ch);

// grab URL (http://www.example.com/) and pass it to the browser
curl_exec($ch2);

// close cURL resources, and free up system resources
curl_close($ch2);
curl_close($ch);
?>
```

curl\_errno
===========

Return the last error number

### Description

<span class="type">int</span> <span
class="methodname">curl\_errno</span> ( <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> )

Returns the error number for the last cURL operation.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

Returns the error number or *0* (zero) if no error occurred.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_errno</span> example**

``` php
<?php
// Create a curl handle to a non-existing location
$ch = curl_init('http://404.php.net/');

// Execute
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_exec($ch);

// Check if any error occurred
if(curl_errno($ch))
{
    echo 'Curl error: ' . curl_error($ch);
}

// Close handle
curl_close($ch);
?>
```

### See Also

-   <span class="function">curl\_error</span>
-   <a href="http://curl.haxx.se/libcurl/c/libcurl-errors.html" class="link external">» Curl error codes</a>

curl\_error
===========

Return a string containing the last error for the current session

### Description

<span class="type">string</span> <span
class="methodname">curl\_error</span> ( <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> )

Returns a clear text error message for the last cURL operation.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

Returns the error message or *''* (the empty string) if no error
occurred.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_error</span> example**

``` php
<?php
// Create a curl handle to a non-existing location
$ch = curl_init('http://404.php.net/');
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

if(curl_exec($ch) === false)
{
    echo 'Curl error: ' . curl_error($ch);
}
else
{
    echo 'Operation completed without any errors';
}

// Close handle
curl_close($ch);
?>
```

### See Also

-   <span class="function">curl\_errno</span>
-   <a href="http://curl.haxx.se/libcurl/c/libcurl-errors.html" class="link external">» Curl error codes</a>

curl\_escape
============

URL encodes the given string

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">curl\_escape</span> ( <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> , <span
class="methodparam"><span class="type">string</span> `$string`</span> )

This function URL encodes the given string according to
<a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

`string`  
The string to be encoded.

### Return Values

Returns escaped string or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_escape</span> example**

``` php
<?php
// Create a curl handle
$ch = curl_init();

// Escape a string used as a GET parameter
$location = curl_escape($ch, 'Hofbräuhaus / München');
// Result: Hofbr%C3%A4uhaus%20%2F%20M%C3%BCnchen

// Compose an URL with the escaped string
$url = "http://example.com/add_location.php?location={$location}";
// Result: http://example.com/add_location.php?location=Hofbr%C3%A4uhaus%20%2F%20M%C3%BCnchen

// Send HTTP request and close the handle
curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_exec($ch);
curl_close($ch);
?>
```

### See Also

-   <span class="function">curl\_unescape</span>
-   <span class="function">urlencode</span>
-   <span class="function">rawurlencode</span>
-   <a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>

curl\_exec
==========

Perform a cURL session

### Description

<span class="type"><span class="type">string</span><span
class="type">bool</span></span> <span
class="methodname">curl\_exec</span> ( <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> )

Execute the given cURL session.

This function should be called after initializing a cURL session and all
the options for the session are set.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. However, if the
**`CURLOPT_RETURNTRANSFER`** option is
<a href="/ref/curl.html#curl_setopt" class="link">set</a>, it will
return the result on success, **`FALSE`** on failure.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

> **Note**:
>
> Note that response status codes which indicate errors (such as *404
> Not found*) are not regarded as failure. <span
> class="function">curl\_getinfo</span> can be used to check for these.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Fetching a web page**

``` php
<?php
// create a new cURL resource
$ch = curl_init();

// set URL and other appropriate options
curl_setopt($ch, CURLOPT_URL, "http://www.example.com/");
curl_setopt($ch, CURLOPT_HEADER, 0);

// grab URL and pass it to the browser
curl_exec($ch);

// close cURL resource, and free up system resources
curl_close($ch);
?>
```

### See Also

-   <span class="function">curl\_multi\_exec</span>

curl\_file\_create
==================

Create a CURLFile object

### Description

This function is an alias of: <span
class="methodname">CURLFile::\_\_construct</span>

curl\_getinfo
=============

Get information regarding a specific transfer

### Description

<span class="type">mixed</span> <span
class="methodname">curl\_getinfo</span> ( <span
class="methodparam"><span class="type">CurlHandle</span>
`$handle`</span> \[, <span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">null</span></span>
`$option`<span class="initializer"> = **`NULL`**</span></span> \] )

Gets information about the last transfer.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

`option`  
This may be one of the following constants:

-   <span class="simpara"> **`CURLINFO_EFFECTIVE_URL`** - Last effective
    URL </span>
-   <span class="simpara"> **`CURLINFO_HTTP_CODE`** - The last response
    code. As of PHP 5.5.0 and cURL 7.10.8, this is a legacy alias of
    **`CURLINFO_RESPONSE_CODE`** </span>
-   <span class="simpara"> **`CURLINFO_FILETIME`** - Remote time of the
    retrieved document, with the **`CURLOPT_FILETIME`** enabled; if -1
    is returned the time of the document is unknown </span>
-   <span class="simpara"> **`CURLINFO_TOTAL_TIME`** - Total transaction
    time in seconds for last transfer </span>
-   <span class="simpara"> **`CURLINFO_NAMELOOKUP_TIME`** - Time in
    seconds until name resolving was complete </span>
-   <span class="simpara"> **`CURLINFO_CONNECT_TIME`** - Time in seconds
    it took to establish the connection </span>
-   <span class="simpara"> **`CURLINFO_PRETRANSFER_TIME`** - Time in
    seconds from start until just before file transfer begins </span>
-   <span class="simpara"> **`CURLINFO_STARTTRANSFER_TIME`** - Time in
    seconds until the first byte is about to be transferred </span>
-   <span class="simpara"> **`CURLINFO_REDIRECT_COUNT`** - Number of
    redirects, with the **`CURLOPT_FOLLOWLOCATION`** option enabled
    </span>
-   <span class="simpara"> **`CURLINFO_REDIRECT_TIME`** - Time in
    seconds of all redirection steps before final transaction was
    started, with the **`CURLOPT_FOLLOWLOCATION`** option enabled
    </span>
-   <span class="simpara"> **`CURLINFO_REDIRECT_URL`** - With the
    **`CURLOPT_FOLLOWLOCATION`** option disabled: redirect URL found in
    the last transaction, that should be requested manually next. With
    the **`CURLOPT_FOLLOWLOCATION`** option enabled: this is empty. The
    redirect URL in this case is available in
    **`CURLINFO_EFFECTIVE_URL`** </span>
-   <span class="simpara"> **`CURLINFO_PRIMARY_IP`** - IP address of the
    most recent connection </span>
-   <span class="simpara"> **`CURLINFO_PRIMARY_PORT`** - Destination
    port of the most recent connection </span>
-   <span class="simpara"> **`CURLINFO_LOCAL_IP`** - Local (source) IP
    address of the most recent connection </span>
-   <span class="simpara"> **`CURLINFO_LOCAL_PORT`** - Local (source)
    port of the most recent connection </span>
-   <span class="simpara"> **`CURLINFO_SIZE_UPLOAD`** - Total number of
    bytes uploaded </span>
-   <span class="simpara"> **`CURLINFO_SIZE_DOWNLOAD`** - Total number
    of bytes downloaded </span>
-   <span class="simpara"> **`CURLINFO_SPEED_DOWNLOAD`** - Average
    download speed </span>
-   <span class="simpara"> **`CURLINFO_SPEED_UPLOAD`** - Average upload
    speed </span>
-   <span class="simpara"> **`CURLINFO_HEADER_SIZE`** - Total size of
    all headers received </span>
-   <span class="simpara"> **`CURLINFO_HEADER_OUT`** - The request
    string sent. For this to work, add the **`CURLINFO_HEADER_OUT`**
    option to the handle by calling <span
    class="function">curl\_setopt</span> </span>
-   <span class="simpara"> **`CURLINFO_REQUEST_SIZE`** - Total size of
    issued requests, currently only for HTTP requests </span>
-   <span class="simpara"> **`CURLINFO_SSL_VERIFYRESULT`** - Result of
    SSL certification verification requested by setting
    **`CURLOPT_SSL_VERIFYPEER`** </span>
-   <span class="simpara"> **`CURLINFO_CONTENT_LENGTH_DOWNLOAD`** -
    Content length of download, read from *Content-Length:* field
    </span>
-   <span class="simpara"> **`CURLINFO_CONTENT_LENGTH_UPLOAD`** -
    Specified size of upload </span>
-   <span class="simpara"> **`CURLINFO_CONTENT_TYPE`** - *Content-Type:*
    of the requested document. NULL indicates server did not send valid
    *Content-Type:* header </span>
-   <span class="simpara"> **`CURLINFO_PRIVATE`** - Private data
    associated with this cURL handle, previously set with the
    **`CURLOPT_PRIVATE`** option of <span
    class="function">curl\_setopt</span> </span>
-   <span class="simpara"> **`CURLINFO_RESPONSE_CODE`** - The last
    response code </span>
-   <span class="simpara"> **`CURLINFO_HTTP_CONNECTCODE`** - The CONNECT
    response code </span>
-   <span class="simpara"> **`CURLINFO_HTTPAUTH_AVAIL`** - Bitmask
    indicating the authentication method(s) available according to the
    previous response </span>
-   <span class="simpara"> **`CURLINFO_PROXYAUTH_AVAIL`** - Bitmask
    indicating the proxy authentication method(s) available according to
    the previous response </span>
-   <span class="simpara"> **`CURLINFO_OS_ERRNO`** - Errno from a
    connect failure. The number is OS and system specific. </span>
-   <span class="simpara"> **`CURLINFO_NUM_CONNECTS`** - Number of
    connections curl had to create to achieve the previous transfer
    </span>
-   <span class="simpara"> **`CURLINFO_SSL_ENGINES`** - OpenSSL
    crypto-engines supported </span>
-   <span class="simpara"> **`CURLINFO_COOKIELIST`** - All known cookies
    </span>
-   <span class="simpara"> **`CURLINFO_FTP_ENTRY_PATH`** - Entry path in
    FTP server </span>
-   <span class="simpara"> **`CURLINFO_APPCONNECT_TIME`** - Time in
    seconds it took from the start until the SSL/SSH connect/handshake
    to the remote host was completed </span>
-   <span class="simpara"> **`CURLINFO_CERTINFO`** - TLS certificate
    chain </span>
-   <span class="simpara"> **`CURLINFO_CONDITION_UNMET`** - Info on
    unmet time conditional </span>
-   <span class="simpara"> **`CURLINFO_RTSP_CLIENT_CSEQ`** - Next RTSP
    client CSeq </span>
-   <span class="simpara"> **`CURLINFO_RTSP_CSEQ_RECV`** - Recently
    received CSeq </span>
-   <span class="simpara"> **`CURLINFO_RTSP_SERVER_CSEQ`** - Next RTSP
    server CSeq </span>
-   <span class="simpara"> **`CURLINFO_RTSP_SESSION_ID`** - RTSP session
    ID </span>
-   <span class="simpara"> **`CURLINFO_CONTENT_LENGTH_DOWNLOAD_T`** -
    The content-length of the download. This is the value read from the
    *Content-Type:* field. -1 if the size isn't known </span>
-   <span class="simpara"> **`CURLINFO_CONTENT_LENGTH_UPLOAD_T`** - The
    specified size of the upload. -1 if the size isn't known </span>
-   <span class="simpara"> **`CURLINFO_HTTP_VERSION`** - The version
    used in the last HTTP connection. The return value will be one of
    the defined **`CURL_HTTP_VERSION_*`** constants or 0 if the version
    can't be determined </span>
-   <span class="simpara"> **`CURLINFO_PROTOCOL`** - The protocol used
    in the last HTTP connection. The returned value will be exactly one
    of the **`CURLPROTO_*`** values </span>
-   <span class="simpara"> **`CURLINFO_PROXY_SSL_VERIFYRESULT`** - The
    result of the certificate verification that was requested (using the
    **`CURLOPT_PROXY_SSL_VERIFYPEER`** option). Only used for HTTPS
    proxies </span>
-   <span class="simpara"> **`CURLINFO_SCHEME`** - The URL scheme used
    for the most recent connection </span>
-   <span class="simpara"> **`CURLINFO_SIZE_DOWNLOAD_T`** - Total number
    of bytes that were downloaded. The number is only for the latest
    transfer and will be reset again for each new transfer </span>
-   <span class="simpara"> **`CURLINFO_SIZE_UPLOAD_T`** - Total number
    of bytes that were uploaded </span>
-   <span class="simpara"> **`CURLINFO_SPEED_DOWNLOAD_T`** - The average
    download speed in bytes/second that curl measured for the complete
    download </span>
-   <span class="simpara"> **`CURLINFO_SPEED_UPLOAD_T`** - The average
    upload speed in bytes/second that curl measured for the complete
    upload </span>
-   <span class="simpara"> **`CURLINFO_APPCONNECT_TIME_T`** - Time, in
    microseconds, it took from the start until the SSL/SSH
    connect/handshake to the remote host was completed </span>
-   <span class="simpara"> **`CURLINFO_CONNECT_TIME_T`** - Total time
    taken, in microseconds, from the start until the connection to the
    remote host (or proxy) was completed </span>
-   <span class="simpara"> **`CURLINFO_FILETIME_T`** - Remote time of
    the retrieved document (as Unix timestamp), an alternative to
    **`CURLINFO_FILETIME`** to allow systems with 32 bit long variables
    to extract dates outside of the 32bit timestamp range </span>
-   <span class="simpara"> **`CURLINFO_NAMELOOKUP_TIME_T`** - Time in
    microseconds from the start until the name resolving was completed
    </span>
-   <span class="simpara"> **`CURLINFO_PRETRANSFER_TIME_T`** - Time
    taken from the start until the file transfer is just about to begin,
    in microseconds </span>
-   <span class="simpara"> **`CURLINFO_REDIRECT_TIME_T`** - Total time,
    in microseconds, it took for all redirection steps include name
    lookup, connect, pretransfer and transfer before final transaction
    was started </span>
-   <span class="simpara"> **`CURLINFO_STARTTRANSFER_TIME_T`** - Time,
    in microseconds, it took from the start until the first byte is
    received </span>
-   <span class="simpara"> **`CURLINFO_TOTAL_TIME_T`** - Total time in
    microseconds for the previous transfer, including name resolving,
    TCP connect etc. </span>

### Return Values

If `option` is given, returns its value. Otherwise, returns an
associative array with the following elements (which correspond to
`option`), or **`FALSE`** on failure:

-   <span class="simpara"> "url" </span>
-   <span class="simpara"> "content\_type" </span>
-   <span class="simpara"> "http\_code" </span>
-   <span class="simpara"> "header\_size" </span>
-   <span class="simpara"> "request\_size" </span>
-   <span class="simpara"> "filetime" </span>
-   <span class="simpara"> "ssl\_verify\_result" </span>
-   <span class="simpara"> "redirect\_count" </span>
-   <span class="simpara"> "total\_time" </span>
-   <span class="simpara"> "namelookup\_time" </span>
-   <span class="simpara"> "connect\_time" </span>
-   <span class="simpara"> "pretransfer\_time" </span>
-   <span class="simpara"> "size\_upload" </span>
-   <span class="simpara"> "size\_download" </span>
-   <span class="simpara"> "speed\_download" </span>
-   <span class="simpara"> "speed\_upload" </span>
-   <span class="simpara"> "download\_content\_length" </span>
-   <span class="simpara"> "upload\_content\_length" </span>
-   <span class="simpara"> "starttransfer\_time" </span>
-   <span class="simpara"> "redirect\_time" </span>
-   <span class="simpara"> "certinfo" </span>
-   <span class="simpara"> "primary\_ip" </span>
-   <span class="simpara"> "primary\_port" </span>
-   <span class="simpara"> "local\_ip" </span>
-   <span class="simpara"> "local\_port" </span>
-   <span class="simpara"> "redirect\_url" </span>
-   <span class="simpara"> "request\_header" (This is only set if the
    **`CURLINFO_HEADER_OUT`** is set by a previous call to <span
    class="function">curl\_setopt</span>) </span>

Note that private data is not included in the associative array and must
be retrieved individually with the **`CURLINFO_PRIVATE`** option.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected.                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| 8.0.0   | `option` is nullable now; previously, the default was *0*.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| 7.3.0   | Introduced **`CURLINFO_CONTENT_LENGTH_DOWNLOAD_T`**, **`CURLINFO_CONTENT_LENGTH_UPLOAD_T`**, **`CURLINFO_HTTP_VERSION`**, **`CURLINFO_PROTOCOL`**, **`CURLINFO_PROXY_SSL_VERIFYRESULT`**, **`CURLINFO_SCHEME`**, **`CURLINFO_SIZE_DOWNLOAD_T`**, **`CURLINFO_SIZE_UPLOAD_T`**, **`CURLINFO_SPEED_DOWNLOAD_T`**, **`CURLINFO_SPEED_UPLOAD_T`**, **`CURLINFO_APPCONNECT_TIME_T`**, **`CURLINFO_CONNECT_TIME_T`**, **`CURLINFO_FILETIME_T`**, **`CURLINFO_NAMELOOKUP_TIME_T`**, **`CURLINFO_PRETRANSFER_TIME_T`**, **`CURLINFO_REDIRECT_TIME_T`**, **`CURLINFO_STARTTRANSFER_TIME_T`**, **`CURLINFO_TOTAL_TIME_T`**. |

### Examples

**Example \#1 <span class="function">curl\_getinfo</span> example**

``` php
<?php
// Create a cURL handle
$ch = curl_init('http://www.example.com/');

// Execute
curl_exec($ch);

// Check if any error occurred
if (!curl_errno($ch)) {
  $info = curl_getinfo($ch);
  echo 'Took ', $info['total_time'], ' seconds to send a request to ', $info['url'], "\n";
}

// Close handle
curl_close($ch);
?>
```

**Example \#2 <span class="function">curl\_getinfo</span> example with
`option` parameter**

``` php
<?php
// Create a cURL handle
$ch = curl_init('http://www.example.com/');

// Execute
curl_exec($ch);

// Check HTTP status code
if (!curl_errno($ch)) {
  switch ($http_code = curl_getinfo($ch, CURLINFO_HTTP_CODE)) {
    case 200:  # OK
      break;
    default:
      echo 'Unexpected HTTP code: ', $http_code, "\n";
  }
}

// Close handle
curl_close($ch);
?>
```

### Notes

> **Note**:
>
> Information gathered by this function is kept if the handle is
> re-used. This means that unless a statistic is overridden internally
> by this function, the previous info is returned.

curl\_init
==========

Initialize a cURL session

### Description

<span class="type"><span class="type">CurlHandle</span><span
class="type">false</span></span> <span
class="methodname">curl\_init</span> (\[ <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$url`<span class="initializer"> =
**`NULL`**</span></span> \] )

Initializes a new session and return a cURL handle for use with the
<span class="function">curl\_setopt</span>, <span
class="function">curl\_exec</span>, and <span
class="function">curl\_close</span> functions.

### Parameters

`url`  
If provided, the **`CURLOPT_URL`** option will be set to its value. You
can manually set this using the <span
class="function">curl\_setopt</span> function.

> **Note**:
>
> The *file* protocol is disabled by cURL if
> <a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
> is set.

### Return Values

Returns a cURL handle on success, **`FALSE`** on errors.

### Changelog

| Version | Description                                                                                                                                                |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | On success, this function returns a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was returned. |
| 8.0.0   | `url` is nullable now.                                                                                                                                     |

### Examples

**Example \#1 Initializing a new cURL session and fetching a web page**

``` php
<?php
// create a new cURL resource
$ch = curl_init();

// set URL and other appropriate options
curl_setopt($ch, CURLOPT_URL, "http://www.example.com/");
curl_setopt($ch, CURLOPT_HEADER, 0);

// grab URL and pass it to the browser
curl_exec($ch);

// close cURL resource, and free up system resources
curl_close($ch);
?>
```

### See Also

-   <span class="function">curl\_close</span>
-   <span class="function">curl\_multi\_init</span>

curl\_multi\_add\_handle
========================

Add a normal cURL handle to a cURL multi handle

### Description

<span class="type">int</span> <span
class="methodname">curl\_multi\_add\_handle</span> ( <span
class="methodparam"><span class="type">CurlMultiHandle</span>
`$multi_handle`</span> , <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> )

Adds the `handle` handle to the multi handle `multi_handle`

### Parameters

`multi_handle`  
A cURL multi handle returned by <span
class="function">curl\_multi\_init</span>.

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

Returns 0 on success, or one of the **`CURLM_XXX`** errors code.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `multi_handle` expects a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected.            |

### Examples

**Example \#1 <span class="function">curl\_multi\_add\_handle</span>
example**

This example will create two cURL handles, add them to a multi handle,
and process them asynchronously.

``` php
<?php
// create both cURL resources
$ch1 = curl_init();
$ch2 = curl_init();

// set URL and other appropriate options
curl_setopt($ch1, CURLOPT_URL, "http://www.example.com/");
curl_setopt($ch1, CURLOPT_HEADER, 0);
curl_setopt($ch2, CURLOPT_URL, "http://www.php.net/");
curl_setopt($ch2, CURLOPT_HEADER, 0);

//create the multiple cURL handle
$mh = curl_multi_init();

//add the two handles
curl_multi_add_handle($mh,$ch1);
curl_multi_add_handle($mh,$ch2);

//execute the multi handle
do {
    $status = curl_multi_exec($mh, $active);
    if ($active) {
        curl_multi_select($mh);
    }
} while ($active && $status == CURLM_OK);

//close all the handles
curl_multi_remove_handle($mh, $ch1);
curl_multi_remove_handle($mh, $ch2);
curl_multi_close($mh);
?>
```

### See Also

-   <span class="function">curl\_multi\_remove\_handle</span>
-   <span class="function">curl\_multi\_init</span>
-   <span class="function">curl\_init</span>

curl\_multi\_close
==================

Close a set of cURL handles

### Description

<span class="type">void</span> <span
class="methodname">curl\_multi\_close</span> ( <span
class="methodparam"><span class="type">CurlMultiHandle</span>
`$multi_handle`</span> )

Closes a set of cURL handles.

### Parameters

`multi_handle`  
A cURL multi handle returned by <span
class="function">curl\_multi\_init</span>.

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `multi_handle` expects a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_multi\_close</span> example**

This example will create two cURL handles, add them to a multi handle,
and process them asynchronously.

``` php
<?php
// create both cURL resources
$ch1 = curl_init();
$ch2 = curl_init();

// set URL and other appropriate options
curl_setopt($ch1, CURLOPT_URL, "http://www.example.com/");
curl_setopt($ch1, CURLOPT_HEADER, 0);
curl_setopt($ch2, CURLOPT_URL, "http://www.php.net/");
curl_setopt($ch2, CURLOPT_HEADER, 0);

//create the multiple cURL handle
$mh = curl_multi_init();

//add the two handles
curl_multi_add_handle($mh,$ch1);
curl_multi_add_handle($mh,$ch2);

//execute the multi handle
do {
    $status = curl_multi_exec($mh, $active);
    if ($active) {
        curl_multi_select($mh);
    }
} while ($active && $status == CURLM_OK);

//close the handles
curl_multi_remove_handle($mh, $ch1);
curl_close($ch1);
curl_multi_remove_handle($mh, $ch2);
curl_close($ch2);
curl_multi_close($mh);

?>
```

### See Also

-   <span class="function">curl\_multi\_init</span>
-   <span class="function">curl\_close</span>

curl\_multi\_errno
==================

Return the last multi curl error number

### Description

<span class="type">int</span> <span
class="methodname">curl\_multi\_errno</span> ( <span
class="methodparam"><span class="type">CurlMultiHandle</span>
`$multi_handle`</span> )

Return an integer containing the last multi curl error number.

### Parameters

`multi_handle`  
A cURL multi handle returned by <span
class="function">curl\_multi\_init</span>.

### Return Values

Return an integer containing the last multi curl error number.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | The function no longer returns **`FALSE`** on failure.                                                                                               |
| 8.0.0   | `multi_handle` expects a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span class="function">curl\_errno</span>

curl\_multi\_exec
=================

Run the sub-connections of the current cURL handle

### Description

<span class="type">int</span> <span
class="methodname">curl\_multi\_exec</span> ( <span
class="methodparam"><span class="type">CurlMultiHandle</span>
`$multi_handle`</span> , <span class="methodparam"><span
class="type">int</span> `&$still_running`</span> )

Processes each of the handles in the stack. This method can be called
whether or not a handle needs to read or write data.

### Parameters

`multi_handle`  
A cURL multi handle returned by <span
class="function">curl\_multi\_init</span>.

`still_running`  
A reference to a flag to tell whether the operations are still running.

### Return Values

A cURL code defined in the cURL
<a href="/curl/constants.html" class="link">Predefined Constants</a>.

> **Note**:
>
> This only returns errors regarding the whole multi stack. There might
> still have occurred problems on individual transfers even when this
> function returns **`CURLM_OK`**.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `multi_handle` expects a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_multi\_exec</span> example**

This example will create two cURL handles, add them to a multi handle,
and process them asynchronously.

``` php
<?php
// create both cURL resources
$ch1 = curl_init();
$ch2 = curl_init();

// set URL and other appropriate options
curl_setopt($ch1, CURLOPT_URL, "http://example.com/");
curl_setopt($ch1, CURLOPT_HEADER, 0);
curl_setopt($ch2, CURLOPT_URL, "http://www.php.net/");
curl_setopt($ch2, CURLOPT_HEADER, 0);

//create the multiple cURL handle
$mh = curl_multi_init();

//add the two handles
curl_multi_add_handle($mh,$ch1);
curl_multi_add_handle($mh,$ch2);

//execute the multi handle
do {
    $status = curl_multi_exec($mh, $active);
    if ($active) {
        // Wait a short time for more activity
        curl_multi_select($mh);
    }
} while ($active && $status == CURLM_OK);

//close the handles
curl_multi_remove_handle($mh, $ch1);
curl_multi_remove_handle($mh, $ch2);
curl_multi_close($mh);

?>
```

### See Also

-   <span class="function">curl\_multi\_init</span>
-   <span class="function">curl\_multi\_select</span>
-   <span class="function">curl\_exec</span>

curl\_multi\_getcontent
=======================

Return the content of a cURL handle if **`CURLOPT_RETURNTRANSFER`** is
set

### Description

<span class="type"><span class="type">string</span><span
class="type">null</span></span> <span
class="methodname">curl\_multi\_getcontent</span> ( <span
class="methodparam"><span class="type">CurlHandle</span>
`$handle`</span> )

If **`CURLOPT_RETURNTRANSFER`** is an option that is set for a specific
handle, then this function will return the content of that cURL handle
in the form of a string.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

Return the content of a cURL handle if **`CURLOPT_RETURNTRANSFER`** is
set.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span class="function">curl\_multi\_init</span>

curl\_multi\_info\_read
=======================

Get information about the current transfers

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">curl\_multi\_info\_read</span> ( <span
class="methodparam"><span class="type">CurlMultiHandle</span>
`$multi_handle`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$queued_messages`<span class="initializer"> =
**`NULL`**</span></span> \] )

Ask the multi handle if there are any messages or information from the
individual transfers. Messages may include information such as an error
code from the transfer or just the fact that a transfer is completed.

Repeated calls to this function will return a new result each time,
until a **`FALSE`** is returned as a signal that there is no more to get
at this point. The integer pointed to with `queued_messages` will
contain the number of remaining messages after this function was called.

**Warning**

The data the returned resource points to will not survive calling <span
class="function">curl\_multi\_remove\_handle</span>.

### Parameters

`multi_handle`  
A cURL multi handle returned by <span
class="function">curl\_multi\_init</span>.

`queued_messages`  
Number of messages that are still in the queue

### Return Values

On success, returns an associative array for the message, **`FALSE`** on
failure.

| Key:     | Value:                                                                                          |
|----------|-------------------------------------------------------------------------------------------------|
| *msg*    | The **`CURLMSG_DONE`** constant. Other return values are currently not available.               |
| *result* | One of the **`CURLE_*`** constants. If everything is OK, the **`CURLE_OK`** will be the result. |
| *handle* | Resource of type curl indicates the handle which it concerns.                                   |

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `multi_handle` expects a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 A <span class="function">curl\_multi\_info\_read</span>
example**

``` php
<?php

$urls = array(
   "http://www.cnn.com/",
   "http://www.bbc.co.uk/",
   "http://www.yahoo.com/"
);

$mh = curl_multi_init();

foreach ($urls as $i => $url) {
    $conn[$i] = curl_init($url);
    curl_setopt($conn[$i], CURLOPT_RETURNTRANSFER, 1);
    curl_multi_add_handle($mh, $conn[$i]);
}

do {
    $status = curl_multi_exec($mh, $active);
    if ($active) {
        curl_multi_select($mh);
    }
    while (false !== ($info = curl_multi_info_read($mh))) {
        var_dump($info);
    }
} while ($active && $status == CURLM_OK);

foreach ($urls as $i => $url) {
    $res[$i] = curl_multi_getcontent($conn[$i]);
    curl_close($conn[$i]);
}

var_dump(curl_multi_info_read($mh));

?>
```

The above example will output something similar to:

    array(3) {
      ["msg"]=>
      int(1)
      ["result"]=>
      int(0)
      ["handle"]=>
      resource(5) of type (curl)
    }
    array(3) {
      ["msg"]=>
      int(1)
      ["result"]=>
      int(0)
      ["handle"]=>
      resource(7) of type (curl)
    }
    array(3) {
      ["msg"]=>
      int(1)
      ["result"]=>
      int(0)
      ["handle"]=>
      resource(6) of type (curl)
    }
    bool(false)

### See Also

-   <span class="function">curl\_multi\_init</span>

curl\_multi\_init
=================

Returns a new cURL multi handle

### Description

<span class="type">CurlMultiHandle</span> <span
class="methodname">curl\_multi\_init</span> ( <span
class="methodparam">void</span> )

Allows the processing of multiple cURL handles asynchronously.

### Parameters

This function has no parameters.

### Return Values

Returns a cURL multi handle on success, **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                     |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | On success, this function returns a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was returned. |

### Examples

**Example \#1 <span class="function">curl\_multi\_init</span> example**

This example will create two cURL handles, add them to a multi handle,
and process them asynchronously.

``` php
<?php
// create both cURL resources
$ch1 = curl_init();
$ch2 = curl_init();

// set URL and other appropriate options
curl_setopt($ch1, CURLOPT_URL, "http://lxr.php.net/");
curl_setopt($ch1, CURLOPT_HEADER, 0);
curl_setopt($ch2, CURLOPT_URL, "http://www.php.net/");
curl_setopt($ch2, CURLOPT_HEADER, 0);

//create the multiple cURL handle
$mh = curl_multi_init();

//add the two handles
curl_multi_add_handle($mh,$ch1);
curl_multi_add_handle($mh,$ch2);

//execute the multi handle
do {
    $status = curl_multi_exec($mh, $active);
    if ($active) {
        curl_multi_select($mh);
    }
} while ($active && $status == CURLM_OK);

//close the handles
curl_multi_remove_handle($mh, $ch1);
curl_multi_remove_handle($mh, $ch2);
curl_multi_close($mh);

?>
```

### See Also

-   <span class="function">curl\_init</span>
-   <span class="function">curl\_multi\_close</span>

curl\_multi\_remove\_handle
===========================

Remove a multi handle from a set of cURL handles

### Description

<span class="type">int</span> <span
class="methodname">curl\_multi\_remove\_handle</span> ( <span
class="methodparam"><span class="type">CurlMultiHandle</span>
`$multi_handle`</span> , <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> )

Removes a given `handle` handle from the given `multi_handle` handle.
When the `handle` handle has been removed, it is again perfectly legal
to run <span class="function">curl\_exec</span> on this handle. Removing
the `handle` handle while being used, will effectively halt the transfer
in progress involving that handle.

### Parameters

`multi_handle`  
A cURL multi handle returned by <span
class="function">curl\_multi\_init</span>.

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

Returns 0 on success, or one of the **`CURLM_XXX`** error codes.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `multi_handle` expects a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected.            |

### See Also

-   <span class="function">curl\_init</span>
-   <span class="function">curl\_multi\_init</span>
-   <span class="function">curl\_multi\_add\_handle</span>

curl\_multi\_select
===================

Wait for activity on any curl\_multi connection

### Description

<span class="type">int</span> <span
class="methodname">curl\_multi\_select</span> ( <span
class="methodparam"><span class="type">CurlMultiHandle</span>
`$multi_handle`</span> \[, <span class="methodparam"><span
class="type">float</span> `$timeout`<span class="initializer"> =
1.0</span></span> \] )

Blocks until there is activity on any of the curl\_multi connections.

### Parameters

`multi_handle`  
A cURL multi handle returned by <span
class="function">curl\_multi\_init</span>.

`timeout`  
Time, in seconds, to wait for a response.

### Return Values

On success, returns the number of descriptors contained in the
descriptor sets. This may be 0 if there was no activity on any of the
descriptors. On failure, this function will return -1 on a select
failure (from the underlying select system call).

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `multi_handle` expects a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span class="function">curl\_multi\_init</span>

curl\_multi\_setopt
===================

Set an option for the cURL multi handle

### Description

<span class="type">bool</span> <span
class="methodname">curl\_multi\_setopt</span> ( <span
class="methodparam"><span class="type">CurlMultiHandle</span>
`$multi_handle`</span> , <span class="methodparam"><span
class="type">int</span> `$option`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`multi_handle`  

`option`  
One of the **`CURLMOPT_*`** constants.

`value`  
The value to be set on `option`.

`value` should be an <span class="type">int</span> for the following
values of the `option` parameter:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Set <code class="parameter">value</code> to</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><code>CURLMOPT_PIPELINING</code></strong></td>
<td>Pass 1 to enable or 0 to disable. Enabling pipelining on a multi handle will make it attempt to perform HTTP Pipelining as far as possible for transfers using this handle. This means that if you add a second request that can use an already existing connection, the second request will be "piped" on the same connection. As of cURL 7.43.0, the value is a bitmask, and you can also pass 2 to try to multiplex the new transfer over an existing HTTP/2 connection if possible. Passing 3 instructs cURL to ask for pipelining and multiplexing independently of each other. As of cURL 7.62.0, setting the pipelining bit has no effect. Instead of integer literals, you can also use the CURLPIPE_* constants if available.</td>
</tr>
<tr class="even">
<td><strong><code>CURLMOPT_MAXCONNECTS</code></strong></td>
<td>Pass a number that will be used as the maximum amount of simultaneously open connections that libcurl may cache. By default the size will be enlarged to fit four times the number of handles added via <span class="function">curl_multi_add_handle</span>. When the cache is full, curl closes the oldest one in the cache to prevent the number of open connections from increasing.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLMOPT_CHUNK_LENGTH_PENALTY_SIZE</code></strong></td>
<td>Pass a number that specifies the chunk length threshold for pipelining in bytes.</td>
</tr>
<tr class="even">
<td><strong><code>CURLMOPT_CONTENT_LENGTH_PENALTY_SIZE</code></strong></td>
<td>Pass a number that specifies the size threshold for pipelining penalty in bytes.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLMOPT_MAX_HOST_CONNECTIONS</code></strong></td>
<td>Pass a number that specifies the maximum number of connections to a single host.</td>
</tr>
<tr class="even">
<td><strong><code>CURLMOPT_MAX_PIPELINE_LENGTH</code></strong></td>
<td>Pass a number that specifies the maximum number of requests in a pipeline.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLMOPT_MAX_TOTAL_CONNECTIONS</code></strong></td>
<td>Pass a number that specifies the maximum number of simultaneously open connections.</td>
</tr>
<tr class="even">
<td><strong><code>CURLMOPT_PUSHFUNCTION</code></strong></td>
<td>Pass a <span class="type">callable</span> that will be registered to handle server pushes and should have the following signature:
<div class="methodsynopsis dc-description">
<span class="type">int</span> <span class="methodname"><span class="replaceable">pushfunction</span></span> ( <span class="methodparam"><span class="type">resource</span> <code class="parameter">$parent_ch</code></span> , <span class="methodparam"><span class="type">resource</span> <code class="parameter">$pushed_ch</code></span> , <span class="methodparam"><span class="type">array</span> <code class="parameter">$headers</code></span> )
</div>
<dl>
<dt><code class="parameter">parent_ch</code></dt>
<dd><p>The parent cURL handle (the request the client made).</p>
</dd>
<dt><code class="parameter">pushed_ch</code></dt>
<dd><p>A new cURL handle for the pushed request.</p>
</dd>
<dt><code class="parameter">headers</code></dt>
<dd><p>The push promise headers.</p>
</dd>
</dl>
The push function is supposed to return either <strong><code>CURL_PUSH_OK</code></strong> if it can handle the push, or <strong><code>CURL_PUSH_DENY</code></strong> to reject it.</td>
</tr>
</tbody>
</table>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `multi_handle` expects a <span class="classname">CurlMultiHandle</span> instance now; previously, a <span class="type">resource</span> was expected.                                                               |
| 7.1.0   | Introduced **`CURLMOPT_PUSHFUNCTION`**.                                                                                                                                                                            |
| 7.0.7   | Introduced **`CURLMOPT_CHUNK_LENGTH_PENALTY_SIZE`**, **`CURLMOPT_CONTENT_LENGTH_PENALTY_SIZE`**, **`CURLMOPT_MAX_HOST_CONNECTIONS`**, **`CURLMOPT_MAX_PIPELINE_LENGTH`** and **`CURLMOPT_MAX_TOTAL_CONNECTIONS`**. |

curl\_multi\_strerror
=====================

Return string describing error code

### Description

<span class="type"><span class="type">string</span><span
class="type">null</span></span> <span
class="methodname">curl\_multi\_strerror</span> ( <span
class="methodparam"><span class="type">int</span> `$error_code`</span> )

Returns a text error message describing the given CURLM error code.

### Parameters

`error_code`  
One of the
<a href="http://curl.haxx.se/libcurl/c/libcurl-errors.html" class="link external">» CURLM error codes</a>
constants.

### Return Values

Returns error string for valid error code, **`NULL`** otherwise.

### Examples

**Example \#1 <span class="function">curl\_multi\_strerror</span>
example**

``` php
<?php
// Create cURL handles
$ch1 = curl_init("http://example.com"/);
$ch2 = curl_init("http://php.net/");

// Create a cURL multi handle
$mh = curl_multi_init();

// Add the handles to the multi handle
curl_multi_add_handle($mh, $ch1);
curl_multi_add_handle($mh, $ch2);

// Execute the multi handle
do {
    $status = curl_multi_exec($mh, $active);
    if ($active) {
        curl_multi_select($mh);
    }
} while ($active && $status === CURLM_OK);

// Check for errors
if ($status != CURLM_OK) {
    // Display error message
    echo "ERROR!\n " . curl_multi_strerror($status);
}

?>
```

### See Also

-   <span class="function">curl\_strerror</span>
-   <a href="http://curl.haxx.se/libcurl/c/libcurl-errors.html" class="link external">» cURL error codes</a>

curl\_pause
===========

Pause and unpause a connection

### Description

<span class="type">int</span> <span
class="methodname">curl\_pause</span> ( <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> , <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

`flags`  
One of **`CURLPAUSE_*`** constants.

### Return Values

Returns an error code (**`CURLE_OK`** for no error).

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

curl\_reset
===========

Reset all options of a libcurl session handle

### Description

<span class="type">void</span> <span
class="methodname">curl\_reset</span> ( <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> )

This function re-initializes all options set on the given cURL handle to
the default values.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_reset</span> example**

``` php
<?php
// Create a curl handle
$ch = curl_init();

// Set CURLOPT_USERAGENT option
curl_setopt($ch, CURLOPT_USERAGENT, "My test user-agent");

// Reset all previously set options
curl_reset($ch);

// Send HTTP request
curl_setopt($ch, CURLOPT_URL, 'http://example.com/');
curl_exec($ch); // the previously set user-agent will be not sent, it has been reset by curl_reset

// Close the handle
curl_close($ch);
?>
```

### Notes

> **Note**:
>
> <span class="function">curl\_reset</span> also resets the URL given as
> the <span class="function">curl\_init</span> parameter.

### See Also

-   <span class="function">curl\_setopt</span>

curl\_setopt\_array
===================

Set multiple options for a cURL transfer

### Description

<span class="type">bool</span> <span
class="methodname">curl\_setopt\_array</span> ( <span
class="methodparam"><span class="type">CurlHandle</span>
`$handle`</span> , <span class="methodparam"><span
class="type">array</span> `$options`</span> )

Sets multiple options for a cURL session. This function is useful for
setting a large number of cURL options without repetitively calling
<span class="function">curl\_setopt</span>.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

`options`  
An <span class="type">array</span> specifying which options to set and
their values. The keys should be valid <span
class="function">curl\_setopt</span> constants or their integer
equivalents.

### Return Values

Returns **`TRUE`** if all options were successfully set. If an option
could not be successfully set, **`FALSE`** is immediately returned,
ignoring any future options in the `options` array.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Initializing a new cURL session and fetching a web page**

``` php
<?php
// create a new cURL resource
$ch = curl_init();

// set URL and other appropriate options
$options = array(CURLOPT_URL => 'http://www.example.com/',
                 CURLOPT_HEADER => false
                );

curl_setopt_array($ch, $options);

// grab URL and pass it to the browser
curl_exec($ch);

// close cURL resource, and free up system resources
curl_close($ch);
?>
```

Prior to PHP 5.1.3 this function can be simulated with:

**Example \#2 Our own implementation of <span
class="function">curl\_setopt\_array</span>**

``` php
<?php
if (!function_exists('curl_setopt_array')) {
   function curl_setopt_array(&$ch, $curl_options)
   {
       foreach ($curl_options as $option => $value) {
           if (!curl_setopt($ch, $option, $value)) {
               return false;
           } 
       }
       return true;
   }
}
?>
```

### Notes

> **Note**:
>
> As with <span class="function">curl\_setopt</span>, passing an array
> to **`CURLOPT_POST`** will encode the data as *multipart/form-data*,
> while passing a URL-encoded string will encode the data as
> *application/x-www-form-urlencoded*.

### See Also

-   <span class="function">curl\_setopt</span>

curl\_setopt
============

Set an option for a cURL transfer

### Description

<span class="type">bool</span> <span
class="methodname">curl\_setopt</span> ( <span class="methodparam"><span
class="type">CurlHandle</span> `$handle`</span> , <span
class="methodparam"><span class="type">int</span> `$option`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

Sets an option on the given cURL session handle.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

`option`  
The *CURLOPT\_XXX* option to set.

`value`  
The value to be set on `option`.

`value` should be a <span class="type">bool</span> for the following
values of the `option` parameter:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Set <code class="parameter">value</code> to</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><code>CURLOPT_AUTOREFERER</code></strong></td>
<td><strong><code>TRUE</code></strong> to automatically set the <em>Referer:</em> field in requests where it follows a <em>Location:</em> redirect.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_BINARYTRANSFER</code></strong></td>
<td><strong><code>TRUE</code></strong> to return the raw output when <strong><code>CURLOPT_RETURNTRANSFER</code></strong> is used.</td>
<td>From PHP 5.1.3, this option has no effect: the raw output will always be returned when <strong><code>CURLOPT_RETURNTRANSFER</code></strong> is used.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_COOKIESESSION</code></strong></td>
<td><strong><code>TRUE</code></strong> to mark this as a new cookie "session". It will force libcurl to ignore all cookies it is about to load that are "session cookies" from the previous session. By default, libcurl always stores and loads all cookies, independent if they are session cookies or not. Session cookies are cookies without expiry date and they are meant to be alive and existing for this "session" only.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_CERTINFO</code></strong></td>
<td><strong><code>TRUE</code></strong> to output SSL certification information to <em>STDERR</em> on secure transfers.</td>
<td>Added in cURL 7.19.1. Available since PHP 5.3.2. Requires <strong><code>CURLOPT_VERBOSE</code></strong> to be on to have an effect.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_CONNECT_ONLY</code></strong></td>
<td><strong><code>TRUE</code></strong> tells the library to perform all the required proxy authentication and connection setup, but no data transfer. This option is implemented for HTTP, SMTP and POP3.</td>
<td>Added in 7.15.2. Available since PHP 5.5.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_CRLF</code></strong></td>
<td><strong><code>TRUE</code></strong> to convert Unix newlines to CRLF newlines on transfers.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_DISALLOW_USERNAME_IN_URL</code></strong></td>
<td><strong><code>TRUE</code></strong> to not allow URLs that include a username. Usernames are allowed by default (0).</td>
<td>Added in cURL 7.61.0. Available since PHP 7.3.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_DNS_SHUFFLE_ADDRESSES</code></strong></td>
<td><strong><code>TRUE</code></strong> to shuffle the order of all returned addresses so that they will be used in a random order, when a name is resolved and more than one IP address is returned. This may cause IPv4 to be used before IPv6 or vice versa.</td>
<td>Added in cURL 7.60.0. Available since PHP 7.3.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_HAPROXYPROTOCOL</code></strong></td>
<td><strong><code>TRUE</code></strong> to send an HAProxy PROXY protocol v1 header at the start of the connection. The default action is not to send this header.</td>
<td>Added in cURL 7.60.0. Available since PHP 7.3.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSH_COMPRESSION</code></strong></td>
<td><strong><code>TRUE</code></strong> to enable built-in SSH compression. This is a request, not an order; the server may or may not do it.</td>
<td>Added in cURL 7.56.0. Available since PHP 7.3.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_DNS_USE_GLOBAL_CACHE</code></strong></td>
<td><strong><code>TRUE</code></strong> to use a global DNS cache. This option is not thread-safe. It is conditionally enabled by default if PHP is built for non-threaded use (CLI, FCGI, Apache2-Prefork, etc.).</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_FAILONERROR</code></strong></td>
<td><strong><code>TRUE</code></strong> to fail verbosely if the HTTP code returned is greater than or equal to 400. The default behavior is to return the page normally, ignoring the code.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSL_FALSESTART</code></strong></td>
<td><strong><code>TRUE</code></strong> to enable TLS false start.</td>
<td>Added in cURL 7.42.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_FILETIME</code></strong></td>
<td><strong><code>TRUE</code></strong> to attempt to retrieve the modification date of the remote document. This value can be retrieved using the <strong><code>CURLINFO_FILETIME</code></strong> option with <span class="function">curl_getinfo</span>.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_FOLLOWLOCATION</code></strong></td>
<td><strong><code>TRUE</code></strong> to follow any <em>"Location: "</em> header that the server sends as part of the HTTP header (note this is recursive, PHP will follow as many <em>"Location: "</em> headers that it is sent, unless <strong><code>CURLOPT_MAXREDIRS</code></strong> is set).</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_FORBID_REUSE</code></strong></td>
<td><strong><code>TRUE</code></strong> to force the connection to explicitly close when it has finished processing, and not be pooled for reuse.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_FRESH_CONNECT</code></strong></td>
<td><strong><code>TRUE</code></strong> to force the use of a new connection instead of a cached one.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_FTP_USE_EPRT</code></strong></td>
<td><strong><code>TRUE</code></strong> to use EPRT (and LPRT) when doing active FTP downloads. Use <strong><code>FALSE</code></strong> to disable EPRT and LPRT and use PORT only.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_FTP_USE_EPSV</code></strong></td>
<td><strong><code>TRUE</code></strong> to first try an EPSV command for FTP transfers before reverting back to PASV. Set to <strong><code>FALSE</code></strong> to disable EPSV.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_FTP_CREATE_MISSING_DIRS</code></strong></td>
<td><strong><code>TRUE</code></strong> to create missing directories when an FTP operation encounters a path that currently doesn't exist.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_FTPAPPEND</code></strong></td>
<td><strong><code>TRUE</code></strong> to append to the remote file instead of overwriting it.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_TCP_NODELAY</code></strong></td>
<td><strong><code>TRUE</code></strong> to disable TCP's Nagle algorithm, which tries to minimize the number of small packets on the network.</td>
<td>Available since PHP 5.2.1 for versions compiled with libcurl 7.11.2 or greater.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_FTPASCII</code></strong></td>
<td>An alias of <strong><code>CURLOPT_TRANSFERTEXT</code></strong>. Use that instead.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_FTPLISTONLY</code></strong></td>
<td><strong><code>TRUE</code></strong> to only list the names of an FTP directory.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_HEADER</code></strong></td>
<td><strong><code>TRUE</code></strong> to include the header in the output.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLINFO_HEADER_OUT</code></strong></td>
<td><strong><code>TRUE</code></strong> to track the handle's request string.</td>
<td>Available since PHP 5.1.3. The <strong><code>CURLINFO_</code></strong> prefix is intentional.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_HTTP09_ALLOWED </code></strong></td>
<td>Whether to allow HTTP/0.9 responses. Defaults to <strong><code>FALSE</code></strong> as of libcurl 7.66.0; formerly it defaulted to <strong><code>TRUE</code></strong>.</td>
<td>Available since PHP 7.3.15 and 7.4.3, respectively, if built against libcurl &gt;= 7.64.0</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_HTTPGET</code></strong></td>
<td><strong><code>TRUE</code></strong> to reset the HTTP request method to GET. Since GET is the default, this is only necessary if the request method has been changed.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_HTTPPROXYTUNNEL</code></strong></td>
<td><strong><code>TRUE</code></strong> to tunnel through a given HTTP proxy.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_HTTP_CONTENT_DECODING</code></strong></td>
<td><strong><code>FALSE</code></strong> to get the raw HTTP response body.</td>
<td>Available as of PHP 5.5.0 if built against libcurl &gt;= 7.16.2.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_KEEP_SENDING_ON_ERROR</code></strong></td>
<td><strong><code>TRUE</code></strong> to keep sending the request body if the HTTP code returned is equal to or larger than 300. The default action would be to stop sending and close the stream or connection. Suitable for manual NTLM authentication. Most applications do not need this option.</td>
<td>Available as of PHP 7.3.0 if built against libcurl &gt;= 7.51.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_MUTE</code></strong></td>
<td><strong><code>TRUE</code></strong> to be completely silent with regards to the cURL functions.</td>
<td>Removed in cURL 7.15.5 (You can use CURLOPT_RETURNTRANSFER instead)</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_NETRC</code></strong></td>
<td><strong><code>TRUE</code></strong> to scan the <var class="filename">~/.netrc</var> file to find a username and password for the remote site that a connection is being established with.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_NOBODY</code></strong></td>
<td><strong><code>TRUE</code></strong> to exclude the body from the output. Request method is then set to HEAD. Changing this to <strong><code>FALSE</code></strong> does not change it to GET.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_NOPROGRESS</code></strong></td>
<td><p><strong><code>TRUE</code></strong> to disable the progress meter for cURL transfers.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>PHP automatically sets this option to <strong><code>TRUE</code></strong>, this should only be changed for debugging purposes.</p>
</blockquote></td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_NOSIGNAL</code></strong></td>
<td><strong><code>TRUE</code></strong> to ignore any cURL function that causes a signal to be sent to the PHP process. This is turned on by default in multi-threaded SAPIs so timeout options can still be used.</td>
<td>Added in cURL 7.10.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PATH_AS_IS</code></strong></td>
<td><strong><code>TRUE</code></strong> to not handle dot dot sequences.</td>
<td>Added in cURL 7.42.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PIPEWAIT</code></strong></td>
<td><strong><code>TRUE</code></strong> to wait for pipelining/multiplexing.</td>
<td>Added in cURL 7.43.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_POST</code></strong></td>
<td><strong><code>TRUE</code></strong> to do a regular HTTP POST. This POST is the normal <em>application/x-www-form-urlencoded</em> kind, most commonly used by HTML forms.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PUT</code></strong></td>
<td><strong><code>TRUE</code></strong> to HTTP PUT a file. The file to PUT must be set with <strong><code>CURLOPT_INFILE</code></strong> and <strong><code>CURLOPT_INFILESIZE</code></strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_RETURNTRANSFER</code></strong></td>
<td><strong><code>TRUE</code></strong> to return the transfer as a string of the return value of <span class="function">curl_exec</span> instead of outputting it directly.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SASL_IR</code></strong></td>
<td><strong><code>TRUE</code></strong> to enable sending the initial response in the first packet.</td>
<td>Added in cURL 7.31.10. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSL_ENABLE_ALPN</code></strong></td>
<td><strong><code>FALSE</code></strong> to disable ALPN in the SSL handshake (if the SSL backend libcurl is built to use supports it), which can be used to negotiate http2.</td>
<td>Added in cURL 7.36.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSL_ENABLE_NPN</code></strong></td>
<td><strong><code>FALSE</code></strong> to disable NPN in the SSL handshake (if the SSL backend libcurl is built to use supports it), which can be used to negotiate http2.</td>
<td>Added in cURL 7.36.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSL_VERIFYPEER</code></strong></td>
<td><strong><code>FALSE</code></strong> to stop cURL from verifying the peer's certificate. Alternate certificates to verify against can be specified with the <strong><code>CURLOPT_CAINFO</code></strong> option or a certificate directory can be specified with the <strong><code>CURLOPT_CAPATH</code></strong> option.</td>
<td><strong><code>TRUE</code></strong> by default as of cURL 7.10. Default bundle installed as of cURL 7.10.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSL_VERIFYSTATUS</code></strong></td>
<td><strong><code>TRUE</code></strong> to verify the certificate's status.</td>
<td>Added in cURL 7.41.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_SSL_VERIFYPEER</code></strong></td>
<td><strong><code>FALSE</code></strong> to stop cURL from verifying the peer's certificate. Alternate certificates to verify against can be specified with the <strong><code>CURLOPT_CAINFO</code></strong> option or a certificate directory can be specified with the <strong><code>CURLOPT_CAPATH</code></strong> option. When set to false, the peer certificate verification succeeds regardless.</td>
<td><strong><code>TRUE</code></strong> by default. Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SUPPRESS_CONNECT_HEADERS</code></strong></td>
<td><strong><code>TRUE</code></strong> to suppress proxy CONNECT response headers from the user callback functions <strong><code>CURLOPT_HEADERFUNCTION</code></strong> and <strong><code>CURLOPT_WRITEFUNCTION</code></strong>, when <strong><code>CURLOPT_HTTPPROXYTUNNEL</code></strong> is used and a CONNECT request is made.</td>
<td>Added in cURL 7.54.0. Available since PHP 7.3.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_TCP_FASTOPEN</code></strong></td>
<td><strong><code>TRUE</code></strong> to enable TCP Fast Open.</td>
<td>Added in cURL 7.49.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_TFTP_NO_OPTIONS</code></strong></td>
<td><strong><code>TRUE</code></strong> to not send TFTP options requests.</td>
<td>Added in cURL 7.48.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_TRANSFERTEXT</code></strong></td>
<td><strong><code>TRUE</code></strong> to use ASCII mode for FTP transfers. For LDAP, it retrieves data in plain text instead of HTML. On Windows systems, it will not set <em>STDOUT</em> to binary mode.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_UNRESTRICTED_AUTH</code></strong></td>
<td><strong><code>TRUE</code></strong> to keep sending the username and password when following locations (using <strong><code>CURLOPT_FOLLOWLOCATION</code></strong>), even when the hostname has changed.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_UPLOAD</code></strong></td>
<td><strong><code>TRUE</code></strong> to prepare for an upload.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_VERBOSE</code></strong></td>
<td><strong><code>TRUE</code></strong> to output verbose information. Writes output to <em>STDERR</em>, or the file specified using <strong><code>CURLOPT_STDERR</code></strong>.</td>
<td></td>
</tr>
</tbody>
</table>

`value` should be an <span class="type">int</span> for the following
values of the `option` parameter:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Set <code class="parameter">value</code> to</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><code>CURLOPT_BUFFERSIZE</code></strong></td>
<td>The size of the buffer to use for each read. There is no guarantee this request will be fulfilled, however.</td>
<td>Added in cURL 7.10.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_CLOSEPOLICY</code></strong></td>
<td>One of the <strong><code>CURLCLOSEPOLICY_*</code></strong> values.
<blockquote>
<p><strong>Note</strong>:</p>
<p>This option is deprecated, as it was never implemented in cURL and never had any effect.</p>
</blockquote></td>
<td>Removed in PHP 5.6.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_CONNECTTIMEOUT</code></strong></td>
<td>The number of seconds to wait while trying to connect. Use 0 to wait indefinitely.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_CONNECTTIMEOUT_MS</code></strong></td>
<td>The number of milliseconds to wait while trying to connect. Use 0 to wait indefinitely. If libcurl is built to use the standard system name resolver, that portion of the connect will still use full-second resolution for timeouts with a minimum timeout allowed of one second.</td>
<td>Added in cURL 7.16.2. Available since PHP 5.2.3.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_DNS_CACHE_TIMEOUT</code></strong></td>
<td>The number of seconds to keep DNS entries in memory. This option is set to 120 (2 minutes) by default.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_EXPECT_100_TIMEOUT_MS</code></strong></td>
<td>The timeout for Expect: 100-continue responses in milliseconds. Defaults to 1000 milliseconds.</td>
<td>Added in cURL 7.36.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_HAPPY_EYEBALLS_TIMEOUT_MS</code></strong></td>
<td>Head start for ipv6 for the happy eyeballs algorithm. Happy eyeballs attempts to connect to both IPv4 and IPv6 addresses for dual-stack hosts, preferring IPv6 first for timeout milliseconds. Defaults to CURL_HET_DEFAULT, which is currently 200 milliseconds.</td>
<td>Added in cURL 7.59.0. Available since PHP 7.3.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_FTPSSLAUTH</code></strong></td>
<td>The FTP authentication method (when is activated): <em>CURLFTPAUTH_SSL</em> (try SSL first), <em>CURLFTPAUTH_TLS</em> (try TLS first), or <em>CURLFTPAUTH_DEFAULT</em> (let cURL decide).</td>
<td>Added in cURL 7.12.2.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_HEADEROPT</code></strong></td>
<td>How to deal with headers. One of the following constants: <span class="simpara"> <strong><code>CURLHEADER_UNIFIED</code></strong>: the headers specified in <strong><code>CURLOPT_HTTPHEADER</code></strong> will be used in requests both to servers and proxies. With this option enabled, <strong><code>CURLOPT_PROXYHEADER</code></strong> will not have any effect. </span> <span class="simpara"> <strong><code>CURLHEADER_SEPARATE</code></strong>: makes <strong><code>CURLOPT_HTTPHEADER</code></strong> headers only get sent to a server and not to a proxy. Proxy headers must be set with <strong><code>CURLOPT_PROXYHEADER</code></strong> to get used. Note that if a non-CONNECT request is sent to a proxy, libcurl will send both server headers and proxy headers. When doing CONNECT, libcurl will send <strong><code>CURLOPT_PROXYHEADER</code></strong> headers only to the proxy and then <strong><code>CURLOPT_HTTPHEADER</code></strong> headers only to the server. </span> <span class="simpara"> Defaults to <strong><code>CURLHEADER_SEPARATE</code></strong> as of cURL 7.42.1, and <strong><code>CURLHEADER_UNIFIED</code></strong> before. </span></td>
<td>Added in cURL 7.37.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_HTTP_VERSION</code></strong></td>
<td><strong><code>CURL_HTTP_VERSION_NONE</code></strong> (default, lets CURL decide which version to use), <strong><code>CURL_HTTP_VERSION_1_0</code></strong> (forces HTTP/1.0), <strong><code>CURL_HTTP_VERSION_1_1</code></strong> (forces HTTP/1.1), <strong><code>CURL_HTTP_VERSION_2_0</code></strong> (attempts HTTP 2), <strong><code>CURL_HTTP_VERSION_2 </code></strong> (alias of <strong><code>CURL_HTTP_VERSION_2_0</code></strong>), <strong><code>CURL_HTTP_VERSION_2TLS</code></strong> (attempts HTTP 2 over TLS (HTTPS) only) or <strong><code>CURL_HTTP_VERSION_2_PRIOR_KNOWLEDGE</code></strong> (issues non-TLS HTTP requests using HTTP/2 without HTTP/1.1 Upgrade).</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_HTTPAUTH</code></strong></td>
<td><p>The HTTP authentication method(s) to use. The options are: <strong><code>CURLAUTH_BASIC</code></strong>, <strong><code>CURLAUTH_DIGEST</code></strong>, <strong><code>CURLAUTH_GSSNEGOTIATE</code></strong>, <strong><code>CURLAUTH_NTLM</code></strong>, <strong><code>CURLAUTH_ANY</code></strong>, and <strong><code>CURLAUTH_ANYSAFE</code></strong>.</p>
<p>The bitwise <em>|</em> (or) operator can be used to combine more than one method. If this is done, cURL will poll the server to see what methods it supports and pick the best one.</p>
<p><strong><code>CURLAUTH_ANY</code></strong> is an alias for <em>CURLAUTH_BASIC | CURLAUTH_DIGEST | CURLAUTH_GSSNEGOTIATE | CURLAUTH_NTLM</em>.</p>
<p><strong><code>CURLAUTH_ANYSAFE</code></strong> is an alias for <em>CURLAUTH_DIGEST | CURLAUTH_GSSNEGOTIATE | CURLAUTH_NTLM</em>.</p></td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_INFILESIZE</code></strong></td>
<td>The expected size, in bytes, of the file when uploading a file to a remote site. Note that using this option will not stop libcurl from sending more data, as exactly what is sent depends on <strong><code>CURLOPT_READFUNCTION</code></strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_LOW_SPEED_LIMIT</code></strong></td>
<td>The transfer speed, in bytes per second, that the transfer should be below during the count of <strong><code>CURLOPT_LOW_SPEED_TIME</code></strong> seconds before PHP considers the transfer too slow and aborts.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_LOW_SPEED_TIME</code></strong></td>
<td>The number of seconds the transfer speed should be below <strong><code>CURLOPT_LOW_SPEED_LIMIT</code></strong> before PHP considers the transfer too slow and aborts.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_MAXCONNECTS</code></strong></td>
<td>The maximum amount of persistent connections that are allowed. When the limit is reached, <strong><code>CURLOPT_CLOSEPOLICY</code></strong> is used to determine which connection to close.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_MAXREDIRS</code></strong></td>
<td>The maximum amount of HTTP redirections to follow. Use this option alongside <strong><code>CURLOPT_FOLLOWLOCATION</code></strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PORT</code></strong></td>
<td>An alternative port number to connect to.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_POSTREDIR</code></strong></td>
<td>A bitmask of 1 (301 Moved Permanently), 2 (302 Found) and 4 (303 See Other) if the HTTP POST method should be maintained when <strong><code>CURLOPT_FOLLOWLOCATION</code></strong> is set and a specific type of redirect occurs.</td>
<td>Added in cURL 7.19.1. Available since PHP 5.3.2.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROTOCOLS</code></strong></td>
<td><p>Bitmask of <strong><code>CURLPROTO_*</code></strong> values. If used, this bitmask limits what protocols libcurl may use in the transfer. This allows you to have a libcurl built to support a wide range of protocols but still limit specific transfers to only be allowed to use a subset of them. By default libcurl will accept all protocols it supports. See also <strong><code>CURLOPT_REDIR_PROTOCOLS</code></strong>.</p>
<p>Valid protocol options are: <strong><code>CURLPROTO_HTTP</code></strong>, <strong><code>CURLPROTO_HTTPS</code></strong>, <strong><code>CURLPROTO_FTP</code></strong>, <strong><code>CURLPROTO_FTPS</code></strong>, <strong><code>CURLPROTO_SCP</code></strong>, <strong><code>CURLPROTO_SFTP</code></strong>, <strong><code>CURLPROTO_TELNET</code></strong>, <strong><code>CURLPROTO_LDAP</code></strong>, <strong><code>CURLPROTO_LDAPS</code></strong>, <strong><code>CURLPROTO_DICT</code></strong>, <strong><code>CURLPROTO_FILE</code></strong>, <strong><code>CURLPROTO_TFTP</code></strong>, <strong><code>CURLPROTO_ALL</code></strong></p></td>
<td>Added in cURL 7.19.4.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXYAUTH</code></strong></td>
<td>The HTTP authentication method(s) to use for the proxy connection. Use the same bitmasks as described in <strong><code>CURLOPT_HTTPAUTH</code></strong>. For proxy authentication, only <strong><code>CURLAUTH_BASIC</code></strong> and <strong><code>CURLAUTH_NTLM</code></strong> are currently supported.</td>
<td>Added in cURL 7.10.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXYPORT</code></strong></td>
<td>The port number of the proxy to connect to. This port number can also be set in <strong><code>CURLOPT_PROXY</code></strong>.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXYTYPE</code></strong></td>
<td>Either <strong><code>CURLPROXY_HTTP</code></strong> (default), <strong><code>CURLPROXY_SOCKS4</code></strong>, <strong><code>CURLPROXY_SOCKS5</code></strong>, <strong><code>CURLPROXY_SOCKS4A</code></strong> or <strong><code>CURLPROXY_SOCKS5_HOSTNAME</code></strong>.</td>
<td>Added in cURL 7.10.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_REDIR_PROTOCOLS</code></strong></td>
<td>Bitmask of <strong><code>CURLPROTO_*</code></strong> values. If used, this bitmask limits what protocols libcurl may use in a transfer that it follows to in a redirect when <strong><code>CURLOPT_FOLLOWLOCATION</code></strong> is enabled. This allows you to limit specific transfers to only be allowed to use a subset of protocols in redirections. By default libcurl will allow all protocols except for FILE and SCP. This is a difference compared to pre-7.19.4 versions which unconditionally would follow to all protocols supported. See also <strong><code>CURLOPT_PROTOCOLS</code></strong> for protocol constant values.</td>
<td>Added in cURL 7.19.4.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_RESUME_FROM</code></strong></td>
<td>The offset, in bytes, to resume a transfer from.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SOCKS5_AUTH</code></strong></td>
<td><p>The SOCKS5 authentication method(s) to use. The options are: <strong><code>CURLAUTH_BASIC</code></strong>, <strong><code>CURLAUTH_GSSAPI</code></strong>, <strong><code>CURLAUTH_NONE</code></strong>.</p>
<p>The bitwise <em>|</em> (or) operator can be used to combine more than one method. If this is done, cURL will poll the server to see what methods it supports and pick the best one.</p>
<p><strong><code>CURLAUTH_BASIC</code></strong> allows username/password authentication.</p>
<p><strong><code>CURLAUTH_GSSAPI</code></strong> allows GSS-API authentication.</p>
<p><strong><code>CURLAUTH_NONE</code></strong> allows no authentication.</p>
<p>Defaults to <em>CURLAUTH_BASIC|CURLAUTH_GSSAPI</em>. Set the actual username and password with the <strong><code>CURLOPT_PROXYUSERPWD</code></strong> option.</p></td>
<td>Available as of 7.3.0 and curl &gt;= 7.55.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSL_OPTIONS</code></strong></td>
<td>Set SSL behavior options, which is a bitmask of any of the following constants: <span class="simpara"> <strong><code>CURLSSLOPT_ALLOW_BEAST</code></strong>: do not attempt to use any workarounds for a security flaw in the SSL3 and TLS1.0 protocols. </span> <span class="simpara"> <strong><code>CURLSSLOPT_NO_REVOKE</code></strong>: disable certificate revocation checks for those SSL backends where such behavior is present. </span></td>
<td>Added in cURL 7.25.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSL_VERIFYHOST</code></strong></td>
<td><em>1</em> to check the existence of a common name in the SSL peer certificate. <em>2</em> to check the existence of a common name and also verify that it matches the hostname provided. <em>0</em> to not check the names. In production environments the value of this option should be kept at <em>2</em> (default value).</td>
<td>Support for value <em>1</em> removed in cURL 7.28.1.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSLVERSION</code></strong></td>
<td>One of <strong><code>CURL_SSLVERSION_DEFAULT</code></strong> (0), <strong><code>CURL_SSLVERSION_TLSv1</code></strong> (1), <strong><code>CURL_SSLVERSION_SSLv2</code></strong> (2), <strong><code>CURL_SSLVERSION_SSLv3</code></strong> (3), <strong><code>CURL_SSLVERSION_TLSv1_0</code></strong> (4), <strong><code>CURL_SSLVERSION_TLSv1_1</code></strong> (5) or <strong><code>CURL_SSLVERSION_TLSv1_2</code></strong> (6). The maximum TLS version can be set by using one of the <strong><code>CURL_SSLVERSION_MAX_*</code></strong> constants. It is also possible to OR one of the <strong><code>CURL_SSLVERSION_*</code></strong> constants with one of the <strong><code>CURL_SSLVERSION_MAX_*</code></strong> constants. <strong><code>CURL_SSLVERSION_MAX_DEFAULT</code></strong> (the maximum version supported by the library), <strong><code>CURL_SSLVERSION_MAX_TLSv1_0</code></strong>, <strong><code>CURL_SSLVERSION_MAX_TLSv1_1</code></strong>, <strong><code>CURL_SSLVERSION_MAX_TLSv1_2</code></strong>, or <strong><code>CURL_SSLVERSION_MAX_TLSv1_3</code></strong>.
<blockquote>
<p><strong>Note</strong>:</p>
<p>Your best bet is to not set this and let it use the default. Setting it to 2 or 3 is very dangerous given the known vulnerabilities in SSLv2 and SSLv3.</p>
</blockquote></td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_SSL_OPTIONS</code></strong></td>
<td>Set proxy SSL behavior options, which is a bitmask of any of the following constants: <span class="simpara"> <strong><code>CURLSSLOPT_ALLOW_BEAST</code></strong>: do not attempt to use any workarounds for a security flaw in the SSL3 and TLS1.0 protocols. </span> <span class="simpara"> <strong><code>CURLSSLOPT_NO_REVOKE</code></strong>: disable certificate revocation checks for those SSL backends where such behavior is present. (curl &gt;= 7.44.0) </span> <span class="simpara"> <strong><code>CURLSSLOPT_NO_PARTIALCHAIN</code></strong>: do not accept "partial" certificate chains, which it otherwise does by default. (curl &gt;= 7.68.0) </span></td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY_SSL_VERIFYHOST</code></strong></td>
<td>Set to <em>2</em> to verify in the HTTPS proxy's certificate name fields against the proxy name. When set to <em>0</em> the connection succeeds regardless of the names used in the certificate. Use that ability with caution! <em>1</em> treated as a debug option in curl 7.28.0 and earlier. From curl 7.28.1 to 7.65.3 <strong><code>CURLE_BAD_FUNCTION_ARGUMENT</code></strong> is returned. From curl 7.66.0 onwards <em>1</em> and <em>2</em> is treated as the same value. In production environments the value of this option should be kept at <em>2</em> (default value).</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_SSLVERSION</code></strong></td>
<td>One of <strong><code>CURL_SSLVERSION_DEFAULT</code></strong>, <strong><code>CURL_SSLVERSION_TLSv1</code></strong>, <strong><code>CURL_SSLVERSION_TLSv1_0</code></strong>, <strong><code>CURL_SSLVERSION_TLSv1_1</code></strong>, <strong><code>CURL_SSLVERSION_TLSv1_2</code></strong>, <strong><code>CURL_SSLVERSION_TLSv1_3</code></strong>, <strong><code>CURL_SSLVERSION_MAX_DEFAULT</code></strong>, <strong><code>CURL_SSLVERSION_MAX_TLSv1_0</code></strong>, <strong><code>CURL_SSLVERSION_MAX_TLSv1_1</code></strong>, <strong><code>CURL_SSLVERSION_MAX_TLSv1_2</code></strong>, <strong><code>CURL_SSLVERSION_MAX_TLSv1_3</code></strong> or <strong><code>CURL_SSLVERSION_SSLv3</code></strong>.
<blockquote>
<p><strong>Note</strong>:</p>
<p>Your best bet is to not set this and let it use the default <strong><code>CURL_SSLVERSION_DEFAULT</code></strong> which will attempt to figure out the remote SSL protocol version.</p>
</blockquote></td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_STREAM_WEIGHT</code></strong></td>
<td>Set the numerical stream weight (a number between 1 and 256).</td>
<td>Added in cURL 7.46.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_TCP_KEEPALIVE</code></strong></td>
<td>If set to <em>1</em>, TCP keepalive probes will be sent. The delay and frequency of these probes can be controlled by the <strong><code>CURLOPT_TCP_KEEPIDLE</code></strong> and <strong><code>CURLOPT_TCP_KEEPINTVL</code></strong> options, provided the operating system supports them. If set to <em>0</em> (default) keepalive probes are disabled.</td>
<td>Added in cURL 7.25.0. Available since PHP 5.5.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_TCP_KEEPIDLE</code></strong></td>
<td>Sets the delay, in seconds, that the operating system will wait while the connection is idle before sending keepalive probes, if <strong><code>CURLOPT_TCP_KEEPALIVE</code></strong> is enabled. Not all operating systems support this option. The default is <em>60</em>.</td>
<td>Added in cURL 7.25.0. Available since PHP 5.5.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_TCP_KEEPINTVL</code></strong></td>
<td>Sets the interval, in seconds, that the operating system will wait between sending keepalive probes, if <strong><code>CURLOPT_TCP_KEEPALIVE</code></strong> is enabled. Not all operating systems support this option. The default is <em>60</em>.</td>
<td>Added in cURL 7.25.0. Available since PHP 5.5.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_TIMECONDITION</code></strong></td>
<td>How <strong><code>CURLOPT_TIMEVALUE</code></strong> is treated. Use <strong><code>CURL_TIMECOND_IFMODSINCE</code></strong> to return the page only if it has been modified since the time specified in <strong><code>CURLOPT_TIMEVALUE</code></strong>. If it hasn't been modified, a <em>"304 Not Modified"</em> header will be returned assuming <strong><code>CURLOPT_HEADER</code></strong> is <strong><code>TRUE</code></strong>. Use <strong><code>CURL_TIMECOND_IFUNMODSINCE</code></strong> for the reverse effect. <strong><code>CURL_TIMECOND_IFMODSINCE</code></strong> is the default.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_TIMEOUT</code></strong></td>
<td>The maximum number of seconds to allow cURL functions to execute.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_TIMEOUT_MS</code></strong></td>
<td>The maximum number of milliseconds to allow cURL functions to execute. If libcurl is built to use the standard system name resolver, that portion of the connect will still use full-second resolution for timeouts with a minimum timeout allowed of one second.</td>
<td>Added in cURL 7.16.2. Available since PHP 5.2.3.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_TIMEVALUE</code></strong></td>
<td>The time in seconds since January 1st, 1970. The time will be used by <strong><code>CURLOPT_TIMECONDITION</code></strong>. By default, <strong><code>CURL_TIMECOND_IFMODSINCE</code></strong> is used.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_TIMEVALUE_LARGE</code></strong></td>
<td>The time in seconds since January 1st, 1970. The time will be used by <strong><code>CURLOPT_TIMECONDITION</code></strong>. Defaults to zero. The difference between this option and <strong><code>CURLOPT_TIMEVALUE</code></strong> is the type of the argument. On systems where 'long' is only 32 bit wide, this option has to be used to set dates beyond the year 2038.</td>
<td>Added in cURL 7.59.0. Available since PHP 7.3.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_MAX_RECV_SPEED_LARGE</code></strong></td>
<td>If a download exceeds this speed (counted in bytes per second) on cumulative average during the transfer, the transfer will pause to keep the average rate less than or equal to the parameter value. Defaults to unlimited speed.</td>
<td>Added in cURL 7.15.5. Available since PHP 5.4.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_MAX_SEND_SPEED_LARGE</code></strong></td>
<td>If an upload exceeds this speed (counted in bytes per second) on cumulative average during the transfer, the transfer will pause to keep the average rate less than or equal to the parameter value. Defaults to unlimited speed.</td>
<td>Added in cURL 7.15.5. Available since PHP 5.4.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSH_AUTH_TYPES</code></strong></td>
<td>A bitmask consisting of one or more of <strong><code>CURLSSH_AUTH_PUBLICKEY</code></strong>, <strong><code>CURLSSH_AUTH_PASSWORD</code></strong>, <strong><code>CURLSSH_AUTH_HOST</code></strong>, <strong><code>CURLSSH_AUTH_KEYBOARD</code></strong>. Set to <strong><code>CURLSSH_AUTH_ANY</code></strong> to let libcurl pick one.</td>
<td>Added in cURL 7.16.1.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_IPRESOLVE</code></strong></td>
<td>Allows an application to select what kind of IP addresses to use when resolving host names. This is only interesting when using host names that resolve addresses using more than one version of IP, possible values are <strong><code>CURL_IPRESOLVE_WHATEVER</code></strong>, <strong><code>CURL_IPRESOLVE_V4</code></strong>, <strong><code>CURL_IPRESOLVE_V6</code></strong>, by default <strong><code>CURL_IPRESOLVE_WHATEVER</code></strong>.</td>
<td>Added in cURL 7.10.8.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_FTP_FILEMETHOD</code></strong></td>
<td>Tell curl which method to use to reach a file on a FTP(S) server. Possible values are <strong><code>CURLFTPMETHOD_MULTICWD</code></strong>, <strong><code>CURLFTPMETHOD_NOCWD</code></strong> and <strong><code>CURLFTPMETHOD_SINGLECWD</code></strong>.</td>
<td>Added in cURL 7.15.1. Available since PHP 5.3.0.</td>
</tr>
</tbody>
</table>

`value` should be a <span class="type">string</span> for the following
values of the `option` parameter:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Set <code class="parameter">value</code> to</th>
<th>Notes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><code>CURLOPT_ABSTRACT_UNIX_SOCKET</code></strong></td>
<td>Enables the use of an abstract Unix domain socket instead of establishing a TCP connection to a host and sets the path to the given <span class="type">string</span>. This option shares the same semantics as <strong><code>CURLOPT_UNIX_SOCKET_PATH</code></strong>. These two options share the same storage and therefore only one of them can be set per handle.</td>
<td>Available since PHP 7.3.0 and cURL 7.53.0</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_CAINFO</code></strong></td>
<td>The name of a file holding one or more certificates to verify the peer with. This only makes sense when used in combination with <strong><code>CURLOPT_SSL_VERIFYPEER</code></strong>.</td>
<td>Might require an absolute path.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_CAPATH</code></strong></td>
<td>A directory that holds multiple CA certificates. Use this option alongside <strong><code>CURLOPT_SSL_VERIFYPEER</code></strong>.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_COOKIE</code></strong></td>
<td>The contents of the <em>"Cookie: "</em> header to be used in the HTTP request. Note that multiple cookies are separated with a semicolon followed by a space (e.g., "<em>fruit=apple; colour=red</em>")</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_COOKIEFILE</code></strong></td>
<td>The name of the file containing the cookie data. The cookie file can be in Netscape format, or just plain HTTP-style headers dumped into a file. If the name is an empty string, no cookies are loaded, but cookie handling is still enabled.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_COOKIEJAR</code></strong></td>
<td>The name of a file to save all internal cookies to when the handle is closed, e.g. after a call to curl_close.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_COOKIELIST</code></strong></td>
<td>A cookie string (i.e. a single line in Netscape/Mozilla format, or a regular HTTP-style Set-Cookie header) adds that single cookie to the internal cookie store. <em>"ALL"</em> erases all cookies held in memory. <em>"SESS"</em> erases all session cookies held in memory. <em>"FLUSH"</em> writes all known cookies to the file specified by <strong><code>CURLOPT_COOKIEJAR</code></strong>. <em>"RELOAD"</em> loads all cookies from the files specified by <strong><code>CURLOPT_COOKIEFILE</code></strong>.</td>
<td>Available since PHP 5.5.0 and cURL 7.14.1.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_CUSTOMREQUEST</code></strong></td>
<td><p>A custom request method to use instead of <em>"GET"</em> or <em>"HEAD"</em> when doing a HTTP request. This is useful for doing <em>"DELETE"</em> or other, more obscure HTTP requests. Valid values are things like <em>"GET"</em>, <em>"POST"</em>, <em>"CONNECT"</em> and so on; i.e. Do not enter a whole HTTP request line here. For instance, entering <em>"GET /index.html HTTP/1.0\r\n\r\n"</em> would be incorrect.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>Don't do this without making sure the server supports the custom request method first.</p>
</blockquote></td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_DEFAULT_PROTOCOL</code></strong></td>
<td><p>The default protocol to use if the URL is missing a scheme name.</p></td>
<td>Added in cURL 7.45.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_DNS_INTERFACE</code></strong></td>
<td><p>Set the name of the network interface that the DNS resolver should bind to. This must be an interface name (not an address).</p></td>
<td>Added in cURL 7.33.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_DNS_LOCAL_IP4</code></strong></td>
<td><p>Set the local IPv4 address that the resolver should bind to. The argument should contain a single numerical IPv4 address as a string.</p></td>
<td>Added in cURL 7.33.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_DNS_LOCAL_IP6</code></strong></td>
<td><p>Set the local IPv6 address that the resolver should bind to. The argument should contain a single numerical IPv6 address as a string.</p></td>
<td>Added in cURL 7.33.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_EGDSOCKET</code></strong></td>
<td>Like <strong><code>CURLOPT_RANDOM_FILE</code></strong>, except a filename to an Entropy Gathering Daemon socket.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_ENCODING</code></strong></td>
<td>The contents of the <em>"Accept-Encoding: "</em> header. This enables decoding of the response. Supported encodings are <em>"identity"</em>, <em>"deflate"</em>, and <em>"gzip"</em>. If an empty string, <em>""</em>, is set, a header containing all supported encoding types is sent.</td>
<td>Added in cURL 7.10.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_FTPPORT</code></strong></td>
<td>The value which will be used to get the IP address to use for the FTP "PORT" instruction. The "PORT" instruction tells the remote server to connect to our specified IP address. The string may be a plain IP address, a hostname, a network interface name (under Unix), or just a plain '-' to use the systems default IP address.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_INTERFACE</code></strong></td>
<td>The name of the outgoing network interface to use. This can be an interface name, an IP address or a host name.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_KEYPASSWD</code></strong></td>
<td>The password required to use the <strong><code>CURLOPT_SSLKEY</code></strong> or <strong><code>CURLOPT_SSH_PRIVATE_KEYFILE</code></strong> private key.</td>
<td>Added in cURL 7.16.1.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_KRB4LEVEL</code></strong></td>
<td>The KRB4 (Kerberos 4) security level. Any of the following values (in order from least to most powerful) are valid: <em>"clear"</em>, <em>"safe"</em>, <em>"confidential"</em>, <em>"private".</em>. If the string does not match one of these, <em>"private"</em> is used. Setting this option to <strong><code>NULL</code></strong> will disable KRB4 security. Currently KRB4 security only works with FTP transactions.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_LOGIN_OPTIONS</code></strong></td>
<td>Can be used to set protocol specific login options, such as the preferred authentication mechanism via "AUTH=NTLM" or "AUTH=*", and should be used in conjunction with the <strong><code>CURLOPT_USERNAME</code></strong> option.</td>
<td>Added in cURL 7.34.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PINNEDPUBLICKEY</code></strong></td>
<td>Set the pinned public key. The string can be the file name of your pinned public key. The file format expected is "PEM" or "DER". The string can also be any number of base64 encoded sha256 hashes preceded by "sha256//" and separated by ";".</td>
<td>Added in cURL 7.39.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_POSTFIELDS</code></strong></td>
<td><span class="simpara"> The full data to post in a HTTP "POST" operation. This parameter can either be passed as a urlencoded string like '<em>para1=val1&amp;para2=val2&amp;...</em>' or as an array with the field name as key and field data as value. If <code class="parameter">value</code> is an array, the <em>Content-Type</em> header will be set to <em>multipart/form-data</em>. </span> <span class="simpara"> Files can be sent using <span class="classname">CURLFile</span>, in which case <code class="parameter">value</code> must be an array. </span></td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PRIVATE</code></strong></td>
<td>Any data that should be associated with this cURL handle. This data can subsequently be retrieved with the <strong><code>CURLINFO_PRIVATE</code></strong> option of <span class="function">curl_getinfo</span>. cURL does nothing with this data. When using a cURL multi handle, this private data is typically a unique key to identify a standard cURL handle.</td>
<td>Added in cURL 7.10.3.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PRE_PROXY</code></strong></td>
<td>Set a <span class="type">string</span> holding the host name or dotted numerical IP address to be used as the preproxy that curl connects to before it connects to the HTTP(S) proxy specified in the <strong><code>CURLOPT_PROXY</code></strong> option for the upcoming request. The preproxy can only be a SOCKS proxy and it should be prefixed with <em>[scheme]://</em> to specify which kind of socks is used. A numerical IPv6 address must be written within [brackets]. Setting the preproxy to an empty string explicitly disables the use of a preproxy. To specify port number in this string, append <em>:[port]</em> to the end of the host name. The proxy's port number may optionally be specified with the separate option <strong><code>CURLOPT_PROXYPORT</code></strong>. Defaults to using port 1080 for proxies if a port is not specified.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY</code></strong></td>
<td>The HTTP proxy to tunnel requests through.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_SERVICE_NAME</code></strong></td>
<td>The proxy authentication service name.</td>
<td>Added in cURL 7.34.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY_CAINFO</code></strong></td>
<td>The path to proxy Certificate Authority (CA) bundle. Set the path as a <span class="type">string</span> naming a file holding one or more certificates to verify the HTTPS proxy with. This option is for connecting to an HTTPS proxy, not an HTTPS server. Defaults set to the system path where libcurl's cacert bundle is assumed to be stored.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_CAPATH</code></strong></td>
<td>The directory holding multiple CA certificates to verify the HTTPS proxy with.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY_CRLFILE</code></strong></td>
<td>Set the file name with the concatenation of CRL (Certificate Revocation List) in PEM format to use in the certificate validation that occurs during the SSL exchange.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_KEYPASSWD</code></strong></td>
<td>Set the string be used as the password required to use the <strong><code>CURLOPT_PROXY_SSLKEY</code></strong> private key. You never needed a passphrase to load a certificate but you need one to load your private key. This option is for connecting to an HTTPS proxy, not an HTTPS server.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY_PINNEDPUBLICKEY</code></strong></td>
<td>Set the pinned public key for HTTPS proxy. The string can be the file name of your pinned public key. The file format expected is "PEM" or "DER". The string can also be any number of base64 encoded sha256 hashes preceded by "sha256//" and separated by ";"</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_SSLCERT</code></strong></td>
<td>The file name of your client certificate used to connect to the HTTPS proxy. The default format is "P12" on Secure Transport and "PEM" on other engines, and can be changed with <strong><code>CURLOPT_PROXY_SSLCERTTYPE</code></strong>. With NSS or Secure Transport, this can also be the nickname of the certificate you wish to authenticate with as it is named in the security database. If you want to use a file from the current directory, please precede it with "./" prefix, in order to avoid confusion with a nickname.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY_SSLCERTTYPE</code></strong></td>
<td>The format of your client certificate used when connecting to an HTTPS proxy. Supported formats are "PEM" and "DER", except with Secure Transport. OpenSSL (versions 0.9.3 and later) and Secure Transport (on iOS 5 or later, or OS X 10.7 or later) also support "P12" for PKCS#12-encoded files. Defaults to "PEM".</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_SSL_CIPHER_LIST</code></strong></td>
<td>The list of ciphers to use for the connection to the HTTPS proxy. The list must be syntactically correct, it consists of one or more cipher strings separated by colons. Commas or spaces are also acceptable separators but colons are normally used, !, - and + can be used as operators.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY_TLS13_CIPHERS</code></strong></td>
<td>The list of cipher suites to use for the TLS 1.3 connection to a proxy. The list must be syntactically correct, it consists of one or more cipher suite strings separated by colons. This option is currently used only when curl is built to use OpenSSL 1.1.1 or later. If you are using a different SSL backend you can try setting TLS 1.3 cipher suites by using the <strong><code>CURLOPT_PROXY_SSL_CIPHER_LIST</code></strong> option.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.61.0. Available when built with OpenSSL &gt;= 1.1.1.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_SSLKEY</code></strong></td>
<td>The file name of your private key used for connecting to the HTTPS proxy. The default format is "PEM" and can be changed with <strong><code>CURLOPT_PROXY_SSLKEYTYPE</code></strong>. (iOS and Mac OS X only) This option is ignored if curl was built against Secure Transport.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0. Available if built TLS enabled.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY_SSLKEYTYPE</code></strong></td>
<td>The format of your private key. Supported formats are "PEM", "DER" and "ENG".</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_TLSAUTH_PASSWORD</code></strong></td>
<td>The password to use for the TLS authentication method specified with the <strong><code>CURLOPT_PROXY_TLSAUTH_TYPE</code></strong> option. Requires that the <strong><code>CURLOPT_PROXY_TLSAUTH_USERNAME</code></strong> option to also be set.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXY_TLSAUTH_TYPE</code></strong></td>
<td>The method of the TLS authentication used for the HTTPS connection. Supported method is "SRP".
<blockquote>
<p><strong>Note</strong>:</p>
<p>Secure Remote Password (SRP) authentication for TLS provides mutual authentication if both sides have a shared secret. To use TLS-SRP, you must also set the <strong><code>CURLOPT_PROXY_TLSAUTH_USERNAME</code></strong> and <strong><code>CURLOPT_PROXY_TLSAUTH_PASSWORD</code></strong> options.</p>
</blockquote></td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROXY_TLSAUTH_USERNAME</code></strong></td>
<td>Tusername to use for the HTTPS proxy TLS authentication method specified with the <strong><code>CURLOPT_PROXY_TLSAUTH_TYPE</code></strong> option. Requires that the <strong><code>CURLOPT_PROXY_TLSAUTH_PASSWORD</code></strong> option to also be set.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.52.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PROXYUSERPWD</code></strong></td>
<td>A username and password formatted as <em>"[username]:[password]"</em> to use for the connection to the proxy.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_RANDOM_FILE</code></strong></td>
<td>A filename to be used to seed the random number generator for SSL.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_RANGE</code></strong></td>
<td>Range(s) of data to retrieve in the format <em>"X-Y"</em> where X or Y are optional. HTTP transfers also support several intervals, separated with commas in the format <em>"X-Y,N-M"</em>.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_REFERER</code></strong></td>
<td>The contents of the <em>"Referer: "</em> header to be used in a HTTP request.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SERVICE_NAME</code></strong></td>
<td>The authentication service name.</td>
<td>Added in cURL 7.43.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSH_HOST_PUBLIC_KEY_MD5</code></strong></td>
<td>A string containing 32 hexadecimal digits. The string should be the MD5 checksum of the remote host's public key, and libcurl will reject the connection to the host unless the md5sums match. This option is only for SCP and SFTP transfers.</td>
<td>Added in cURL 7.17.1.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSH_PUBLIC_KEYFILE</code></strong></td>
<td>The file name for your public key. If not used, libcurl defaults to $HOME/.ssh/id_dsa.pub if the HOME environment variable is set, and just "id_dsa.pub" in the current directory if HOME is not set.</td>
<td>Added in cURL 7.16.1.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSH_PRIVATE_KEYFILE</code></strong></td>
<td>The file name for your private key. If not used, libcurl defaults to $HOME/.ssh/id_dsa if the HOME environment variable is set, and just "id_dsa" in the current directory if HOME is not set. If the file is password-protected, set the password with <strong><code>CURLOPT_KEYPASSWD</code></strong>.</td>
<td>Added in cURL 7.16.1.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSL_CIPHER_LIST</code></strong></td>
<td>A list of ciphers to use for SSL. For example, <em>RC4-SHA</em> and <em>TLSv1</em> are valid cipher lists.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSLCERT</code></strong></td>
<td>The name of a file containing a PEM formatted certificate.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSLCERTPASSWD</code></strong></td>
<td>The password required to use the <strong><code>CURLOPT_SSLCERT</code></strong> certificate.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSLCERTTYPE</code></strong></td>
<td>The format of the certificate. Supported formats are <em>"PEM"</em> (default), <em>"DER"</em>, and <em>"ENG"</em>. As of OpenSSL 0.9.3, <em>"P12"</em> (for PKCS#12-encoded files) is also supported.</td>
<td>Added in cURL 7.9.3.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSLENGINE</code></strong></td>
<td>The identifier for the crypto engine of the private SSL key specified in <strong><code>CURLOPT_SSLKEY</code></strong>.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSLENGINE_DEFAULT</code></strong></td>
<td>The identifier for the crypto engine used for asymmetric crypto operations.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSLKEY</code></strong></td>
<td>The name of a file containing a private SSL key.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_SSLKEYPASSWD</code></strong></td>
<td><p>The secret password needed to use the private SSL key specified in <strong><code>CURLOPT_SSLKEY</code></strong>.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>Since this option contains a sensitive password, remember to keep the PHP script it is contained within safe.</p>
</blockquote></td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_SSLKEYTYPE</code></strong></td>
<td>The key type of the private SSL key specified in <strong><code>CURLOPT_SSLKEY</code></strong>. Supported key types are <em>"PEM"</em> (default), <em>"DER"</em>, and <em>"ENG"</em>.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_TLS13_CIPHERS</code></strong></td>
<td>The list of cipher suites to use for the TLS 1.3 connection. The list must be syntactically correct, it consists of one or more cipher suite strings separated by colons. This option is currently used only when curl is built to use OpenSSL 1.1.1 or later. If you are using a different SSL backend you can try setting TLS 1.3 cipher suites by using the <strong><code>CURLOPT_SSL_CIPHER_LIST</code></strong> option.</td>
<td>Available since PHP 7.3.0 and libcurl &gt;= cURL 7.61.0. Available when built with OpenSSL &gt;= 1.1.1.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_UNIX_SOCKET_PATH</code></strong></td>
<td>Enables the use of Unix domain sockets as connection endpoint and sets the path to the given <span class="type">string</span>.</td>
<td>Added in cURL 7.40.0. Available since PHP 7.0.7.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_URL</code></strong></td>
<td>The URL to fetch. This can also be set when initializing a session with <span class="function">curl_init</span>.</td>
<td></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_USERAGENT</code></strong></td>
<td>The contents of the <em>"User-Agent: "</em> header to be used in a HTTP request.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_USERNAME</code></strong></td>
<td>The user name to use in authentication.</td>
<td>Added in cURL 7.19.1. Available since PHP 5.5.0.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_USERPWD</code></strong></td>
<td>A username and password formatted as <em>"[username]:[password]"</em> to use for the connection.</td>
<td></td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_XOAUTH2_BEARER</code></strong></td>
<td>Specifies the OAuth 2.0 access token.</td>
<td>Added in cURL 7.33.0. Available since PHP 7.0.7.</td>
</tr>
</tbody>
</table>

`value` should be an array for the following values of the `option`
parameter:

| Option                       | Set `value` to                                                                                                                                                                                                                   | Notes                                            |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| **`CURLOPT_CONNECT_TO`**     | Connect to a specific host and port instead of the URL's host and port. Accepts an array of strings with the format *HOST:PORT:CONNECT-TO-HOST:CONNECT-TO-PORT*.                                                                 | Added in cURL 7.49.0. Available since PHP 7.0.7. |
| **`CURLOPT_HTTP200ALIASES`** | An array of HTTP 200 responses that will be treated as valid responses and not as errors.                                                                                                                                        | Added in cURL 7.10.3.                            |
| **`CURLOPT_HTTPHEADER`**     | An array of HTTP header fields to set, in the format `              array('Content-type: text/plain', 'Content-length: 100')             `                                                                                       |                                                  |
| **`CURLOPT_POSTQUOTE`**      | An array of FTP commands to execute on the server after the FTP request has been performed.                                                                                                                                      |                                                  |
| **`CURLOPT_PROXYHEADER`**    | An array of custom HTTP headers to pass to proxies.                                                                                                                                                                              | Added in cURL 7.37.0. Available since PHP 7.0.7. |
| **`CURLOPT_QUOTE`**          | An array of FTP commands to execute on the server prior to the FTP request.                                                                                                                                                      |                                                  |
| **`CURLOPT_RESOLVE`**        | Provide a custom address for a specific host and port pair. An array of hostname, port, and IP address strings, each element separated by a colon. In the format: `              array("example.com:80:127.0.0.1")             ` | Added in cURL 7.21.3. Available since PHP 5.5.0. |

`value` should be a stream resource (using <span
class="function">fopen</span>, for example) for the following values of
the `option` parameter:

| Option                    | Set `value` to                                                                                 |
|---------------------------|------------------------------------------------------------------------------------------------|
| **`CURLOPT_FILE`**        | The file that the transfer should be written to. The default is *STDOUT* (the browser window). |
| **`CURLOPT_INFILE`**      | The file that the transfer should be read from when uploading.                                 |
| **`CURLOPT_STDERR`**      | An alternative location to output errors to instead of *STDERR*.                               |
| **`CURLOPT_WRITEHEADER`** | The file that the header part of the transfer is written to.                                   |

`value` should be the name of a valid function or a Closure for the
following values of the `option` parameter:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Set <code class="parameter">value</code> to</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><code>CURLOPT_HEADERFUNCTION</code></strong></td>
<td>A callback accepting two parameters. The first is the cURL resource, the second is a string with the header data to be written. The header data must be written by this callback. Return the number of bytes written.</td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_PASSWDFUNCTION</code></strong></td>
<td>A callback accepting three parameters. The first is the cURL resource, the second is a string containing a password prompt, and the third is the maximum password length. Return the string containing the password.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_PROGRESSFUNCTION</code></strong></td>
<td><p>A callback accepting five parameters. The first is the cURL resource, the second is the total number of bytes expected to be downloaded in this transfer, the third is the number of bytes downloaded so far, the fourth is the total number of bytes expected to be uploaded in this transfer, and the fifth is the number of bytes uploaded so far.</p>
<blockquote>
<p><strong>Note</strong>:</p>
<p>The callback is only called when the <strong><code>CURLOPT_NOPROGRESS</code></strong> option is set to <strong><code>FALSE</code></strong>.</p>
</blockquote>
<p>Return a non-zero value to abort the transfer. In which case, the transfer will set a <strong><code>CURLE_ABORTED_BY_CALLBACK</code></strong> error.</p></td>
</tr>
<tr class="even">
<td><strong><code>CURLOPT_READFUNCTION</code></strong></td>
<td>A callback accepting three parameters. The first is the cURL resource, the second is a stream resource provided to cURL through the option <strong><code>CURLOPT_INFILE</code></strong>, and the third is the maximum amount of data to be read. The callback must return a string with a length equal or smaller than the amount of data requested, typically by reading it from the passed stream resource. It should return an empty string to signal <em>EOF</em>.</td>
</tr>
<tr class="odd">
<td><strong><code>CURLOPT_WRITEFUNCTION</code></strong></td>
<td>A callback accepting two parameters. The first is the cURL resource, and the second is a string with the data to be written. The data must be saved by this callback. It must return the exact number of bytes written or the transfer will be aborted with an error.</td>
</tr>
</tbody>
</table>

Other values:

| Option              | Set `value` to                                                                                                             |
|---------------------|----------------------------------------------------------------------------------------------------------------------------|
| **`CURLOPT_SHARE`** | A result of <span class="function">curl\_share\_init</span>. Makes the cURL handle to use the data from the shared handle. |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version       | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0         | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 7.3.15, 7.4.3 | Introduced **`CURLOPT_HTTP09_ALLOWED `**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| 7.3.0         | Introduced **`CURLOPT_ABSTRACT_UNIX_SOCKET`**, **`CURLOPT_KEEP_SENDING_ON_ERROR`**, **`CURLOPT_PRE_PROXY`**, **`CURLOPT_PROXY_CAINFO`**, **`CURLOPT_PROXY_CAPATH`**, **`CURLOPT_PROXY_CRLFILE`**, **`CURLOPT_PROXY_KEYPASSWD`**, **`CURLOPT_PROXY_PINNEDPUBLICKEY`**, **`CURLOPT_PROXY_SSLCERT`**, **`CURLOPT_PROXY_SSLCERTTYPE`**, **`CURLOPT_PROXY_SSL_CIPHER_LIST`**, **`CURLOPT_PROXY_SSLKEY`**, **`CURLOPT_PROXY_SSLKEYTYPE`**, **`CURLOPT_PROXY_SSL_OPTIONS`**, **`CURLOPT_PROXY_SSL_VERIFYHOST`**, **`CURLOPT_PROXY_SSL_VERIFYPEER`**, **`CURLOPT_PROXY_SSLVERSION`**, **`CURLOPT_PROXY_TLSAUTH_PASSWORD`**, **`CURLOPT_PROXY_TLSAUTH_TYPE`**, **`CURLOPT_PROXY_TLSAUTH_USERNAME`**, **`CURLOPT_SOCKS5_AUTH`**, **`CURLOPT_SUPPRESS_CONNECT_HEADERS`**, **`CURLOPT_DISALLOW_USERNAME_IN_URL`**, **`CURLOPT_DNS_SHUFFLE_ADDRESSES`**, **`CURLOPT_HAPPY_EYEBALLS_TIMEOUT_MS`**, **`CURLOPT_HAPROXYPROTOCOL`**, **`CURLOPT_PROXY_TLS13_CIPHERS`**, **`CURLOPT_SSH_COMPRESSION`**, **`CURLOPT_TIMEVALUE_LARGE`** and **`CURLOPT_TLS13_CIPHERS`**.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| 7.0.7         | Introduced **`CURL_HTTP_VERSION_2`**, **`CURL_HTTP_VERSION_2_PRIOR_KNOWLEDGE`**, **`CURL_HTTP_VERSION_2TLS`**, **`CURL_REDIR_POST_301`**, **`CURL_REDIR_POST_302`**, **`CURL_REDIR_POST_303`**, **`CURL_REDIR_POST_ALL`**, **`CURL_VERSION_KERBEROS5`**, **`CURL_VERSION_PSL`**, **`CURL_VERSION_UNIX_SOCKETS`**, **`CURLAUTH_NEGOTIATE`**, **`CURLAUTH_NTLM_WB`**, **`CURLFTP_CREATE_DIR`**, **`CURLFTP_CREATE_DIR_NONE`**, **`CURLFTP_CREATE_DIR_RETRY`**, **`CURLHEADER_SEPARATE`**, **`CURLHEADER_UNIFIED`**, **`CURLMOPT_CHUNK_LENGTH_PENALTY_SIZE`**, **`CURLMOPT_CONTENT_LENGTH_PENALTY_SIZE`**, **`CURLMOPT_MAX_HOST_CONNECTIONS`**, **`CURLMOPT_MAX_PIPELINE_LENGTH`**, **`CURLMOPT_MAX_TOTAL_CONNECTIONS`**, **`CURLOPT_CONNECT_TO`**, **`CURLOPT_DEFAULT_PROTOCOL`**, **`CURLOPT_DNS_INTERFACE`**, **`CURLOPT_DNS_LOCAL_IP4`**, **`CURLOPT_DNS_LOCAL_IP6`**, **`CURLOPT_EXPECT_100_TIMEOUT_MS`**, **`CURLOPT_HEADEROPT`**, **`CURLOPT_LOGIN_OPTIONS`**, **`CURLOPT_PATH_AS_IS`**, **`CURLOPT_PINNEDPUBLICKEY`**, **`CURLOPT_PIPEWAIT`**, **`CURLOPT_PROXY_SERVICE_NAME`**, **`CURLOPT_PROXYHEADER`**, **`CURLOPT_SASL_IR`**, **`CURLOPT_SERVICE_NAME`**, **`CURLOPT_SSL_ENABLE_ALPN`**, **`CURLOPT_SSL_ENABLE_NPN`**, **`CURLOPT_SSL_FALSESTART`**, **`CURLOPT_SSL_VERIFYSTATUS`**, **`CURLOPT_STREAM_WEIGHT`**, **`CURLOPT_TCP_FASTOPEN`**, **`CURLOPT_TFTP_NO_OPTIONS`**, **`CURLOPT_UNIX_SOCKET_PATH`**, **`CURLOPT_XOAUTH2_BEARER`**, **`CURLPROTO_SMB`**, **`CURLPROTO_SMBS`**, **`CURLPROXY_HTTP_1_0`**, **`CURLSSH_AUTH_AGENT`** and **`CURLSSLOPT_NO_REVOKE`**. |

### Examples

**Example \#1 Initializing a new cURL session and fetching a web page**

``` php
<?php
// create a new cURL resource
$ch = curl_init();

// set URL and other appropriate options
curl_setopt($ch, CURLOPT_URL, "http://www.example.com/");
curl_setopt($ch, CURLOPT_HEADER, false);

// grab URL and pass it to the browser
curl_exec($ch);

// close cURL resource, and free up system resources
curl_close($ch);
?>
```

### Notes

> **Note**:
>
> Passing an array to **`CURLOPT_POSTFIELDS`** will encode the data as
> *multipart/form-data*, while passing a URL-encoded string will encode
> the data as *application/x-www-form-urlencoded*.

### See Also

-   <span class="function">curl\_setopt\_array</span>

curl\_share\_close
==================

Close a cURL share handle

### Description

<span class="type">void</span> <span
class="methodname">curl\_share\_close</span> ( <span
class="methodparam"><span class="type">CurlShareHandle</span>
`$share_handle`</span> )

Closes a cURL share handle and frees all resources.

### Parameters

`share_handle`  
A cURL share handle returned by <span
class="function">curl\_share\_init</span>.

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `share_handle` expects a <span class="classname">CurlShareHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_share\_setopt</span>
example**

This example will create a cURL share handle, add two cURL handles to
it, and then run them with cookie data sharing.

``` php
<?php
// Create cURL share handle and set it to share cookie data
$sh = curl_share_init();
curl_share_setopt($sh, CURLSHOPT_SHARE, CURL_LOCK_DATA_COOKIE);

// Initialize the first cURL handle and assign the share handle to it
$ch1 = curl_init("http://example.com/");
curl_setopt($ch1, CURLOPT_SHARE, $sh);

// Execute the first cURL handle
curl_exec($ch1);

// Initialize the second cURL handle and assign the share handle to it
$ch2 = curl_init("http://php.net/");
curl_setopt($ch2, CURLOPT_SHARE, $sh);

// Execute the second cURL handle
//  all cookies from $ch1 handle are shared with $ch2 handle
curl_exec($ch2);

// Close the cURL share handle
curl_share_close($sh);

// Close the cURL handles
curl_close($ch1);
curl_close($ch2);
?>
```

### See Also

-   <span class="function">curl\_share\_init</span>

curl\_share\_errno
==================

Return the last share curl error number

### Description

<span class="type">int</span> <span
class="methodname">curl\_share\_errno</span> ( <span
class="methodparam"><span class="type">CurlShareHandle</span>
`$share_handle`</span> )

Return an integer containing the last share curl error number.

### Parameters

`share_handle`  
A cURL share handle returned by <span
class="function">curl\_share\_init</span>.

### Return Values

Returns an integer containing the last share curl error number, or
**`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | The function no longer returns **`FALSE`** on failure.                                                                                               |
| 8.0.0   | `share_handle` expects a <span class="classname">CurlShareHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span class="function">curl\_errno</span>

curl\_share\_init
=================

Initialize a cURL share handle

### Description

<span class="type">CurlShareHandle</span> <span
class="methodname">curl\_share\_init</span> ( <span
class="methodparam">void</span> )

Allows to share data between cURL handles.

### Parameters

This function has no parameters.

### Return Values

Returns a cURL share handle.

### Changelog

| Version | Description                                                                                                                                         |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function returns a <span class="classname">CurlShareHandle</span> instance now; previously, a <span class="type">resource</span> was returned. |

### Examples

**Example \#1 <span class="function">curl\_share\_init</span> example**

This example will create a cURL share handle, add two cURL handles to
it, and then run them with cookie data sharing.

``` php
<?php
// Create cURL share handle and set it to share cookie data
$sh = curl_share_init();
curl_share_setopt($sh, CURLSHOPT_SHARE, CURL_LOCK_DATA_COOKIE);

// Initialize the first cURL handle and assign the share handle to it
$ch1 = curl_init("http://example.com/");
curl_setopt($ch1, CURLOPT_SHARE, $sh);

// Execute the first cURL handle
curl_exec($ch1);

// Initialize the second cURL handle and assign the share handle to it
$ch2 = curl_init("http://php.net/");
curl_setopt($ch2, CURLOPT_SHARE, $sh);

// Execute the second cURL handle
//  all cookies from $ch1 handle are shared with $ch2 handle
curl_exec($ch2);

// Close the cURL share handle
curl_share_close($sh);

// Close the cURL handles
curl_close($ch1);
curl_close($ch2);
?>
```

### See Also

-   <span class="function">curl\_share\_setopt</span>
-   <span class="function">curl\_share\_close</span>

curl\_share\_setopt
===================

Set an option for a cURL share handle

### Description

<span class="type">bool</span> <span
class="methodname">curl\_share\_setopt</span> ( <span
class="methodparam"><span class="type">CurlShareHandle</span>
`$share_handle`</span> , <span class="methodparam"><span
class="type">int</span> `$option`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Sets an option on the given cURL share handle.

### Parameters

`share_handle`  
A cURL share handle returned by <span
class="function">curl\_share\_init</span>.

`option`  
| Option                  | Description                                             |
|-------------------------|---------------------------------------------------------|
| **`CURLSHOPT_SHARE`**   | Specifies a type of data that should be shared.         |
| **`CURLSHOPT_UNSHARE`** | Specifies a type of data that will be no longer shared. |

`value`  
| Value                            | Description                                                                                                                                                                        |
|----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`CURL_LOCK_DATA_COOKIE`**      | Shares cookie data.                                                                                                                                                                |
| **`CURL_LOCK_DATA_DNS`**         | Shares DNS cache. Note that when you use cURL multi handles, all handles added to the same multi handle will share DNS cache by default.                                           |
| **`CURL_LOCK_DATA_SSL_SESSION`** | Shares SSL session IDs, reducing the time spent on the SSL handshake when reconnecting to the same server. Note that SSL session IDs are reused within the same handle by default. |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `share_handle` expects a <span class="classname">CurlShareHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_share\_setopt</span>
example**

This example will create a cURL share handle, add two cURL handles to
it, and then run them with cookie data sharing.

``` php
<?php
// Create cURL share handle and set it to share cookie data
$sh = curl_share_init();
curl_share_setopt($sh, CURLSHOPT_SHARE, CURL_LOCK_DATA_COOKIE);

// Initialize the first cURL handle and assign the share handle to it
$ch1 = curl_init("http://example.com/");
curl_setopt($ch1, CURLOPT_SHARE, $sh);

// Execute the first cURL handle
curl_exec($ch1);

// Initialize the second cURL handle and assign the share handle to it
$ch2 = curl_init("http://php.net/");
curl_setopt($ch2, CURLOPT_SHARE, $sh);

// Execute the second cURL handle
//  all cookies from $ch1 handle are shared with $ch2 handle
curl_exec($ch2);

// Close the cURL share handle
curl_share_close($sh);

// Close the cURL handles
curl_close($ch1);
curl_close($ch2);
?>
```

curl\_share\_strerror
=====================

Return string describing the given error code

### Description

<span class="type"><span class="type">string</span><span
class="type">null</span></span> <span
class="methodname">curl\_share\_strerror</span> ( <span
class="methodparam"><span class="type">int</span> `$error_code`</span> )

Returns a text error message describing the given error code.

### Parameters

`error_code`  
One of the
<a href="http://curl.haxx.se/libcurl/c/libcurl-errors.html" class="link external">» cURL error codes</a>
constants.

### Return Values

Returns error description or **`NULL`** for invalid error code.

### See Also

-   <span class="function">curl\_share\_errno</span>
-   <span class="function">curl\_strerror</span>

curl\_strerror
==============

Return string describing the given error code

### Description

<span class="type"><span class="type">string</span><span
class="type">null</span></span> <span
class="methodname">curl\_strerror</span> ( <span
class="methodparam"><span class="type">int</span> `$error_code`</span> )

Returns a text error message describing the given error code.

### Parameters

`error_code`  
One of the
<a href="http://curl.haxx.se/libcurl/c/libcurl-errors.html" class="link external">» cURL error codes</a>
constants.

### Return Values

Returns error description or **`NULL`** for invalid error code.

### Examples

**Example \#1 <span class="function">curl\_errno</span> example**

``` php
<?php
// Create a curl handle with a misspelled protocol in URL
$ch = curl_init("htp://example.com/");

// Send request
curl_exec($ch);

// Check for errors and display the error message
if($errno = curl_errno($ch)) {
    $error_message = curl_strerror($errno);
    echo "cURL error ({$errno}):\n {$error_message}";
}

// Close the handle
curl_close($ch);
?>
```

The above example will output:

    cURL error (1):
     Unsupported protocol

### See Also

-   <span class="function">curl\_errno</span>
-   <span class="function">curl\_error</span>
-   <a href="http://curl.haxx.se/libcurl/c/libcurl-errors.html" class="link external">» Curl error codes</a>

curl\_unescape
==============

Decodes the given URL encoded string

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">curl\_unescape</span> ( <span
class="methodparam"><span class="type">CurlHandle</span>
`$handle`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> )

This function decodes the given URL encoded string.

### Parameters

`handle`  
A cURL handle returned by <span class="function">curl\_init</span>.

`string`  
The URL encoded string to be decoded.

### Return Values

Returns decoded string or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `handle` expects a <span class="classname">CurlHandle</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">curl\_escape</span> example**

``` php
<?php
// Create a curl handle
$ch = curl_init('http://example.com/redirect.php');

// Send HTTP request and follow redirections
curl_setopt($ch, CURLOPT_FOLLOWLOCATION, 1);
curl_exec($ch);

// Get the last effective URL
$effective_url = curl_getinfo($ch, CURLINFO_EFFECTIVE_URL);
// ie. "http://example.com/show_location.php?loc=M%C3%BCnchen"

// Decode the URL
$effective_url_decoded = curl_unescape($ch, $effective_url);
// "http://example.com/show_location.php?loc=München"

// Close the handle
curl_close($ch);
?>
```

### Notes

> **Note**:
>
> <span class="function">curl\_unescape</span> does not decode plus
> symbols (+) into spaces. <span class="function">urldecode</span> does.

### See Also

-   <span class="function">curl\_escape</span>
-   <span class="function">urlencode</span>
-   <span class="function">urldecode</span>
-   <span class="function">rawurlencode</span>
-   <span class="function">rawurldecode</span>

curl\_version
=============

Gets cURL version information

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">curl\_version</span> ( <span
class="methodparam">void</span> )

Returns information about the cURL version.

### Parameters

`age`  

### Return Values

Returns an associative array with the following elements:

| Key                  | Value description                               |
|----------------------|-------------------------------------------------|
| version\_number      | cURL 24 bit version number                      |
| version              | cURL version number, as a string                |
| ssl\_version\_number | OpenSSL 24 bit version number                   |
| ssl\_version         | OpenSSL version number, as a string             |
| libz\_version        | zlib version number, as a string                |
| host                 | Information about the host where cURL was built |
| age                  |                                                 |
| features             | A bitmask of the *CURL\_VERSION\_XXX* constants |
| protocols            | An array of protocols names supported by cURL   |

### Examples

**Example \#1 <span class="function">curl\_version</span> example**

This example will check which features that's available in cURL build by
using the *'features'* bitmask returned by <span
class="function">curl\_version</span>.

``` php
<?php
// Get curl version array
$version = curl_version();

// These are the bitfields that can be used 
// to check for features in the curl build
$bitfields = Array(
            'CURL_VERSION_IPV6', 
            'CURL_VERSION_KERBEROS4', 
            'CURL_VERSION_SSL', 
            'CURL_VERSION_LIBZ'
            );


foreach($bitfields as $feature)
{
    echo $feature . ($version['features'] & constant($feature) ? ' matches' : ' does not match');
    echo PHP_EOL;
}
?>
```

**Table of Contents**

-   [curl\_close](/ref/curl.html#curl_close) — Close a cURL session
-   [curl\_copy\_handle](/ref/curl.html#curl_copy_handle) — Copy a cURL
    handle along with all of its preferences
-   [curl\_errno](/ref/curl.html#curl_errno) — Return the last error
    number
-   [curl\_error](/ref/curl.html#curl_error) — Return a string
    containing the last error for the current session
-   [curl\_escape](/ref/curl.html#curl_escape) — URL encodes the given
    string
-   [curl\_exec](/ref/curl.html#curl_exec) — Perform a cURL session
-   [curl\_file\_create](/ref/curl.html#curl_file_create) — Create a
    CURLFile object
-   [curl\_getinfo](/ref/curl.html#curl_getinfo) — Get information
    regarding a specific transfer
-   [curl\_init](/ref/curl.html#curl_init) — Initialize a cURL session
-   [curl\_multi\_add\_handle](/ref/curl.html#curl_multi_add_handle) —
    Add a normal cURL handle to a cURL multi handle
-   [curl\_multi\_close](/ref/curl.html#curl_multi_close) — Close a set
    of cURL handles
-   [curl\_multi\_errno](/ref/curl.html#curl_multi_errno) — Return the
    last multi curl error number
-   [curl\_multi\_exec](/ref/curl.html#curl_multi_exec) — Run the
    sub-connections of the current cURL handle
-   [curl\_multi\_getcontent](/ref/curl.html#curl_multi_getcontent) —
    Return the content of a cURL handle if CURLOPT\_RETURNTRANSFER is
    set
-   [curl\_multi\_info\_read](/ref/curl.html#curl_multi_info_read) — Get
    information about the current transfers
-   [curl\_multi\_init](/ref/curl.html#curl_multi_init) — Returns a new
    cURL multi handle
-   [curl\_multi\_remove\_handle](/ref/curl.html#curl_multi_remove_handle)
    — Remove a multi handle from a set of cURL handles
-   [curl\_multi\_select](/ref/curl.html#curl_multi_select) — Wait for
    activity on any curl\_multi connection
-   [curl\_multi\_setopt](/ref/curl.html#curl_multi_setopt) — Set an
    option for the cURL multi handle
-   [curl\_multi\_strerror](/ref/curl.html#curl_multi_strerror) — Return
    string describing error code
-   [curl\_pause](/ref/curl.html#curl_pause) — Pause and unpause a
    connection
-   [curl\_reset](/ref/curl.html#curl_reset) — Reset all options of a
    libcurl session handle
-   [curl\_setopt\_array](/ref/curl.html#curl_setopt_array) — Set
    multiple options for a cURL transfer
-   [curl\_setopt](/ref/curl.html#curl_setopt) — Set an option for a
    cURL transfer
-   [curl\_share\_close](/ref/curl.html#curl_share_close) — Close a cURL
    share handle
-   [curl\_share\_errno](/ref/curl.html#curl_share_errno) — Return the
    last share curl error number
-   [curl\_share\_init](/ref/curl.html#curl_share_init) — Initialize a
    cURL share handle
-   [curl\_share\_setopt](/ref/curl.html#curl_share_setopt) — Set an
    option for a cURL share handle
-   [curl\_share\_strerror](/ref/curl.html#curl_share_strerror) — Return
    string describing the given error code
-   [curl\_strerror](/ref/curl.html#curl_strerror) — Return string
    describing the given error code
-   [curl\_unescape](/ref/curl.html#curl_unescape) — Decodes the given
    URL encoded string
-   [curl\_version](/ref/curl.html#curl_version) — Gets cURL version
    information

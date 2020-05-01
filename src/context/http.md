HTTP context options
====================

HTTP context option listing

### Description

Context options for *http://* and *https://* transports.

### Options

`method` <span class="type">string</span>  
**`GET`**, **`POST`**, or any other HTTP method supported by the remote
server.

Defaults to **`GET`**.

`header` <span class="type">array</span> or <span class="type">string</span>  
Additional headers to be sent during request. Values in this option will
override other values (such as *User-agent:*, *Host:*, and
*Authentication:*).

`user_agent` <span class="type">string</span>  
Value to send with *User-Agent:* header. This value will only be used if
user-agent is *not* specified in the *header* context option above.

By default the
<a href="/filesystem/setup.html#" class="link">user_agent</a> `php.ini`
setting is used.

`content` <span class="type">string</span>  
Additional data to be sent after the headers. Typically used with POST
or PUT requests.

`proxy` <span class="type">string</span>  
URI specifying address of proxy server. (e.g.
*tcp://proxy.example.com:5100*).

`request_fulluri` <span class="type">boolean</span>  
When set to **`TRUE`**, the entire URI will be used when constructing
the request. (i.e. *GET http://www.example.com/path/to/file.html
HTTP/1.0*). While this is a non-standard request format, some proxy
servers require it.

Defaults to **`FALSE`**.

`follow_location` <span class="type">integer</span>  
Follow *Location* header redirects. Set to *0* to disable.

Defaults to *1*.

`max_redirects` <span class="type">integer</span>  
The max number of redirects to follow. Value *1* or less means that no
redirects are followed.

Defaults to *20*.

`protocol_version` <span class="type">float</span>  
HTTP protocol version.

Defaults to *1.0*.

> **Note**:
>
> PHP prior to 5.3.0 does not implement chunked transfer decoding. If
> this value is set to *1.1* it is your responsibility to be *1.1*
> compliant.

`timeout` <span class="type">float</span>  
Read timeout in seconds, specified by a <span class="type">float</span>
(e.g. *10.5*).

By default the
<a href="/filesystem/setup.html#" class="link">default_socket_timeout</a>
`php.ini` setting is used.

`ignore_errors` <span class="type">boolean</span>  
Fetch the content even on failure status codes.

Defaults to **`FALSE`**.

### Changelog

| Version | Description                                                                     |
|---------|---------------------------------------------------------------------------------|
| 5.3.4   | Added `follow_location`.                                                        |
| 5.3.0   | The `protocol_version` supports chunked transfer decoding when set to *1.1*.    |
| 5.2.10  | Added `ignore_errors`.                                                          |
| 5.2.10  | The `header` can now be an numerically indexed <span class="type">array</span>. |
| 5.2.1   | Added `timeout`.                                                                |
| 5.1.0   | Added HTTPS proxying through HTTP proxies.                                      |
| 5.1.0   | Added `max_redirects`.                                                          |
| 5.1.0   | Added `protocol_version`.                                                       |

### Examples

**Example \#1 Fetch a page and send POST data**

``` php
<?php

$postdata = http_build_query(
    array(
        'var1' => 'some content',
        'var2' => 'doh'
    )
);

$opts = array('http' =>
    array(
        'method'  => 'POST',
        'header'  => 'Content-type: application/x-www-form-urlencoded',
        'content' => $postdata
    )
);

$context = stream_context_create($opts);

$result = file_get_contents('http://example.com/submit.php', false, $context);

?>
```

**Example \#2 Ignore redirects but fetch headers and content**

``` php
<?php

$url = "http://www.example.org/header.php";

$opts = array('http' =>
    array(
        'method' => 'GET',
        'max_redirects' => '0',
        'ignore_errors' => '1'
    )
);

$context = stream_context_create($opts);
$stream = fopen($url, 'r', false, $context);

// header information as well as meta data
// about the stream
var_dump(stream_get_meta_data($stream));

// actual data at $url
var_dump(stream_get_contents($stream));
fclose($stream);
?>
```

### Notes

> **Note**: **Underlying socket stream context options**  
> <span class="simpara"> Additional context options may be supported by
> the
> <a href="/transports/inet.html" class="link">underlying transport</a>
> For *http://* streams, refer to context options for the *tcp://*
> transport. For *https://* streams, refer to context options for the
> *ssl://* transport. </span>

> **Note**: **HTTP status line**  
> <span class="simpara"> When this stream wrapper follows a redirect,
> the *wrapper\_data* returned by <span
> class="function">stream\_get\_meta\_data</span> might not necessarily
> contain the HTTP status line that actually applies to the content data
> at index *0*. </span>
>
>     array (
>       'wrapper_data' =>
>       array (
>         0 => 'HTTP/1.0 301 Moved Permantenly',
>         1 => 'Cache-Control: no-cache',
>         2 => 'Connection: close',
>         3 => 'Location: http://example.com/foo.jpg',
>         4 => 'HTTP/1.1 200 OK',
>         ...
>
> <span class="simpara"> The first request returned a *301* (permanent
> redirect), so the stream wrapper automatically followed the redirect
> to get a *200* response (index = *4*). </span>

### See Also

-   <a href="/wrappers/http.html" class="xref">http://</a>
-   <a href="/context/socket.html" class="xref">Socket context options</a>
-   <a href="/context/ssl.html" class="xref">SSL context options</a>

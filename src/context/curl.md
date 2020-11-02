CURL context options
====================

CURL context option listing

### Description

CURL context options are available when the
<a href="/intro/curl.html" class="link">CURL</a> extension was compiled
using the **--with-curlwrappers** configure option.

### Options

`method` <span class="type">string</span>  
**`GET`**, **`POST`**, or any other HTTP method supported by the remote
server.

Defaults to **`GET`**.

`header` <span class="type">string</span>  
Additional headers to be sent during request. Values in this option will
override other values (such as *User-agent:*, *Host:*, and
*Authentication:*).

`user_agent` <span class="type">string</span>  
Value to send with User-Agent: header.

By default the
<a href="/filesystem/setup.html#" class="link">user_agent</a> `php.ini`
setting is used.

`content` <span class="type">string</span>  
Additional data to be sent after the headers. This option is not used
for **`GET`** or **`HEAD`** requests.

`proxy` <span class="type">string</span>  
URI specifying address of proxy server. (e.g.
*tcp://proxy.example.com:5100*).

`max_redirects` <span class="type">int</span>  
The max number of redirects to follow. Value *1* or less means that no
redirects are followed.

Defaults to *20*.

`curl_verify_ssl_host` <span class="type">bool</span>  
Verify the host.

Defaults to **`FALSE`**

> **Note**:
>
> This option is available for both the http and ftp protocol wrappers.

`curl_verify_ssl_peer` <span class="type">bool</span>  
Require verification of SSL certificate used.

Defaults to **`FALSE`**

> **Note**:
>
> This option is available for both the http and ftp protocol wrappers.

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

### See Also

-   <a href="/context/socket.html" class="xref">Socket context options</a>

http://
=======

https://
========

Accessing HTTP(s) URLs

### Description

Allows read-only access to files/resources via HTTP 1.0, using the HTTP
GET method. A *Host:* header is sent with the request to handle
name-based virtual hosts. If you have configured a
<a href="/filesystem/setup.html#" class="link">user_agent</a> string
using your `php.ini` file or the stream context, it will also be
included in the request.

The stream allows access to the *body* of the resource; the headers are
stored in the `$http_response_header` variable.

If it's important to know the URL of the resource where your document
came from (after all redirects have been processed), you'll need to
process the series of response headers returned by the stream.

The <a href="/filesystem/setup.html#" class="link">from</a> directive
will be used for the *From:* header if set and not overwritten by the
<a href="/context.html" class="xref">Context options and parameters</a>.

### Usage

-   <span class="simpara">`http://example.com`</span>
-   <span
    class="simpara">`http://example.com/file.php?var1=val1&var2=val2`</span>
-   <span class="simpara">`http://user:password@example.com`</span>
-   <span class="simpara">`https://example.com`</span>
-   <span
    class="simpara">`https://example.com/file.php?var1=val1&var2=val2`</span>
-   <span class="simpara">`https://user:password@example.com`</span>

### Options

| Attribute                                                                        | Supported |
|----------------------------------------------------------------------------------|-----------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a> | Yes       |
| Allows Reading                                                                   | Yes       |
| Allows Writing                                                                   | No        |
| Allows Appending                                                                 | No        |
| Allows Simultaneous Reading and Writing                                          | N/A       |
| Supports <span class="function">stat</span>                                      | No        |
| Supports <span class="function">unlink</span>                                    | No        |
| Supports <span class="function">rename</span>                                    | No        |
| Supports <span class="function">mkdir</span>                                     | No        |
| Supports <span class="function">rmdir</span>                                     | No        |

### Examples

**Example \#1 Detecting which URL we ended up on after redirects**

``` php
<?php
$url = 'http://www.example.com/redirecting_page.php';

$fp = fopen($url, 'r');

$meta_data = stream_get_meta_data($fp);
foreach ($meta_data['wrapper_data'] as $response) {

    /* Were we redirected? */
    if (strtolower(substr($response, 0, 10)) == 'location: ') {

        /* update $url with where we were redirected to */
        $url = substr($response, 10);
    }

}

?>
```

### Notes

> **Note**: <span class="simpara"> HTTPS is only supported when the
> <a href="/book/openssl.html" class="link">openssl</a> extension is
> enabled. </span>

HTTP connections are read-only; writing data or copying files to an HTTP
resource is not supported.

Sending *POST* and *PUT* requests, for example, can be done with the
help of <a href="/context/http.html" class="link">HTTP Contexts</a>.

### See Also

-   <a href="/context/http.html" class="xref">HTTP context options</a>
-   `$http_response_header`
-   <span class="function">stream\_get\_meta\_data</span>

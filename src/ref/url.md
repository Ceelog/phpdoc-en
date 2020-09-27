base64\_decode
==============

Decodes data encoded with MIME base64

### Description

<span class="type">string</span> <span
class="methodname">base64\_decode</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$strict`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Decodes a base64 encoded `data`.

### Parameters

`data`  
The encoded data.

`strict`  
If the `strict` parameter is set to **`TRUE`** then the <span
class="function">base64\_decode</span> function will return **`FALSE`**
if the input contains character from outside the base64 alphabet.
Otherwise invalid characters will be silently discarded.

### Return Values

Returns the decoded data or **`FALSE`** on failure. The returned data
may be binary.

### Examples

**Example \#1 <span class="function">base64\_decode</span> example**

``` php
<?php
$str = 'VGhpcyBpcyBhbiBlbmNvZGVkIHN0cmluZw==';
echo base64_decode($str);
?>
```

The above example will output:

    This is an encoded string

### See Also

-   <span class="function">base64\_encode</span>
-   <a href="http://www.faqs.org/rfcs/rfc2045" class="link external">» RFC 2045</a>
    section 6.8

base64\_encode
==============

Encodes data with MIME base64

### Description

<span class="type">string</span> <span
class="methodname">base64\_encode</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

Encodes the given `data` with base64.

This encoding is designed to make binary data survive transport through
transport layers that are not 8-bit clean, such as mail bodies.

Base64-encoded data takes about 33% more space than the original data.

### Parameters

`data`  
The data to encode.

### Return Values

The encoded data, as a string.

### Examples

**Example \#1 <span class="function">base64\_encode</span> example**

``` php
<?php
$str = 'This is an encoded string';
echo base64_encode($str);
?>
```

The above example will output:

    VGhpcyBpcyBhbiBlbmNvZGVkIHN0cmluZw==

### See Also

-   <span class="function">base64\_decode</span>
-   <span class="function">chunk\_split</span>
-   <span class="function">convert\_uuencode</span>
-   <a href="http://www.faqs.org/rfcs/rfc2045" class="link external">» RFC 2045</a>
    section 6.8

get\_headers
============

Fetches all the headers sent by the server in response to an HTTP
request

### Description

<span class="type">array</span> <span
class="methodname">get\_headers</span> ( <span class="methodparam"><span
class="type">string</span> `$url`</span> \[, <span
class="methodparam"><span class="type">int</span> `$format`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`</span>
\]\] )

<span class="function">get\_headers</span> returns an array with the
headers sent by the server in response to a HTTP request.

### Parameters

`url`  
The target URL.

`format`  
If the optional `format` parameter is set to non-zero, <span
class="function">get\_headers</span> parses the response and sets the
array's keys.

`context`  
A valid context resource created with <span
class="function">stream\_context\_create</span>.

### Return Values

Returns an indexed or associative array with the headers, or **`FALSE`**
on failure.

### Changelog

| Version | Description                        |
|---------|------------------------------------|
| 7.1.0   | The `context` parameter was added. |

### Examples

**Example \#1 <span class="function">get\_headers</span> example**

``` php
<?php
$url = 'http://www.example.com';

print_r(get_headers($url));

print_r(get_headers($url, 1));
?>
```

The above example will output something similar to:

    Array
    (
        [0] => HTTP/1.1 200 OK
        [1] => Date: Sat, 29 May 2004 12:28:13 GMT
        [2] => Server: Apache/1.3.27 (Unix)  (Red-Hat/Linux)
        [3] => Last-Modified: Wed, 08 Jan 2003 23:11:55 GMT
        [4] => ETag: "3f80f-1b6-3e1cb03b"
        [5] => Accept-Ranges: bytes
        [6] => Content-Length: 438
        [7] => Connection: close
        [8] => Content-Type: text/html
    )

    Array
    (
        [0] => HTTP/1.1 200 OK
        [Date] => Sat, 29 May 2004 12:28:14 GMT
        [Server] => Apache/1.3.27 (Unix)  (Red-Hat/Linux)
        [Last-Modified] => Wed, 08 Jan 2003 23:11:55 GMT
        [ETag] => "3f80f-1b6-3e1cb03b"
        [Accept-Ranges] => bytes
        [Content-Length] => 438
        [Connection] => close
        [Content-Type] => text/html
    )

**Example \#2 <span class="function">get\_headers</span> using HEAD
example**

``` php
<?php
// By default get_headers uses a GET request to fetch the headers. If you
// want to send a HEAD request instead, you can do so using a stream context:
stream_context_set_default(
    array(
        'http' => array(
            'method' => 'HEAD'
        )
    )
);
$headers = get_headers('http://example.com');
?>
```

### See Also

-   <span class="function">apache\_request\_headers</span>

get\_meta\_tags
===============

Extracts all meta tag content attributes from a file and returns an
array

### Description

<span class="type">array</span> <span
class="methodname">get\_meta\_tags</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$use_include_path`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Opens `filename` and parses it line by line for \<meta\> tags in the
file. The parsing stops at *\</head\>*.

### Parameters

`filename`  
The path to the HTML file, as a string. This can be a local file or an
URL.

**Example \#1 What <span class="function">get\_meta\_tags</span>
parses**

``` html
<meta name="author" content="name">
<meta name="keywords" content="php documentation">
<meta name="DESCRIPTION" content="a php manual">
<meta name="geo.position" content="49.33;-86.59">
</head> <!-- parsing stops here -->
```

(pay attention to line endings - PHP uses a native function to parse the
input, so a Mac file won't work on Unix).

`use_include_path`  
Setting `use_include_path` to **`TRUE`** will result in PHP trying to
open the file along the standard include path as per the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
directive. This is used for local files, not URLs.

### Return Values

Returns an array with all the parsed meta tags.

The value of the name property becomes the key, the value of the content
property becomes the value of the returned array, so you can easily use
standard array functions to traverse it or access single values. Special
characters in the value of the name property are substituted with '\_',
the rest is converted to lower case. If two meta tags have the same
name, only the last one is returned.

### Examples

**Example \#2 What <span class="function">get\_meta\_tags</span>
returns**

``` php
<?php
// Assuming the above tags are at www.example.com
$tags = get_meta_tags('http://www.example.com/');

// Notice how the keys are all lowercase now, and
// how . was replaced by _ in the key.
echo $tags['author'];       // name
echo $tags['keywords'];     // php documentation
echo $tags['description'];  // a php manual
echo $tags['geo_position']; // 49.33;-86.59
?>
```

### Notes

> **Note**:
>
> Only meta tags with name attributes will be parsed. Quotes are not
> required.

### See Also

-   <span class="function">htmlentities</span>
-   <span class="function">urlencode</span>

http\_build\_query
==================

Generate URL-encoded query string

### Description

<span class="type">string</span> <span
class="methodname">http\_build\_query</span> ( <span
class="methodparam"><span class="type">mixed</span> `$query_data`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$numeric_prefix`</span> \[, <span class="methodparam"><span
class="type">string</span> `$arg_separator`</span> \[, <span
class="methodparam"><span class="type">int</span> `$enc_type`<span
class="initializer"> = **`PHP_QUERY_RFC1738`**</span></span> \]\]\] )

Generates a URL-encoded query string from the associative (or indexed)
array provided.

### Parameters

`query_data`  
May be an array or object containing properties.

If `query_data` is an array, it may be a simple one-dimensional
structure, or an array of arrays (which in turn may contain other
arrays).

If `query_data` is an object, then only public properties will be
incorporated into the result.

`numeric_prefix`  
If numeric indices are used in the base array and this parameter is
provided, it will be prepended to the numeric index for elements in the
base array only.

This is meant to allow for legal variable names when the data is decoded
by PHP or another CGI application later on.

`arg_separator`  
<a href="/ini/core.html#ini.arg-separator.output" class="link">arg_separator.output</a>
is used to separate arguments but may be overridden by specifying this
parameter.

`enc_type`  
By default, **`PHP_QUERY_RFC1738`**.

If `enc_type` is **`PHP_QUERY_RFC1738`**, then encoding is performed per
<a href="http://www.faqs.org/rfcs/rfc1738" class="link external">» RFC 1738</a>
and the *application/x-www-form-urlencoded* media type, which implies
that spaces are encoded as plus (*+*) signs.

If `enc_type` is **`PHP_QUERY_RFC3986`**, then encoding is performed
according to
<a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>,
and spaces will be percent encoded (*%20*).

### Return Values

Returns a URL-encoded string.

### Examples

**Example \#1 Simple usage of <span
class="function">http\_build\_query</span>**

``` php
<?php
$data = array(
    'foo' => 'bar',
    'baz' => 'boom',
    'cow' => 'milk',
    'php' => 'hypertext processor'
);

echo http_build_query($data) . "\n";
echo http_build_query($data, '', '&amp;');

?>
```

The above example will output:

    foo=bar&baz=boom&cow=milk&php=hypertext+processor
    foo=bar&amp;baz=boom&amp;cow=milk&amp;php=hypertext+processor

**Example \#2 <span class="function">http\_build\_query</span> with
numerically index elements.**

``` php
<?php
$data = array('foo', 'bar', 'baz', 'boom', 'cow' => 'milk', 'php' => 'hypertext processor');

echo http_build_query($data) . "\n";
echo http_build_query($data, 'myvar_');
?>
```

The above example will output:

    0=foo&1=bar&2=baz&3=boom&cow=milk&php=hypertext+processor
    myvar_0=foo&myvar_1=bar&myvar_2=baz&myvar_3=boom&cow=milk&php=hypertext+processor

**Example \#3 <span class="function">http\_build\_query</span> with
complex arrays**

``` php
<?php
$data = array(
    'user' => array(
        'name' => 'Bob Smith',
        'age'  => 47,
        'sex'  => 'M',
        'dob'  => '5/12/1956'
    ),
    'pastimes' => array('golf', 'opera', 'poker', 'rap'),
    'children' => array(
        'bobby' => array('age'=>12, 'sex'=>'M'),
        'sally' => array('age'=>8, 'sex'=>'F')
    ),
    'CEO'
);

echo http_build_query($data, 'flags_');
?>
```

this will output : (word wrapped for readability)

    user%5Bname%5D=Bob+Smith&user%5Bage%5D=47&user%5Bsex%5D=M&
    user%5Bdob%5D=5%2F12%2F1956&pastimes%5B0%5D=golf&pastimes%5B1%5D=opera&
    pastimes%5B2%5D=poker&pastimes%5B3%5D=rap&children%5Bbobby%5D%5Bage%5D=12&
    children%5Bbobby%5D%5Bsex%5D=M&children%5Bsally%5D%5Bage%5D=8&
    children%5Bsally%5D%5Bsex%5D=F&flags_0=CEO

> **Note**:
>
> Only the numerically indexed element in the base array "CEO" received
> a prefix. The other numeric indices, found under pastimes, do not
> require a string prefix to be legal variable names.

**Example \#4 Using <span class="function">http\_build\_query</span>
with an object**

``` php
<?php
class parentClass {
    public    $pub      = 'publicParent';
    protected $prot     = 'protectedParent';
    private   $priv     = 'privateParent';
    public    $pub_bar  = Null;
    protected $prot_bar = Null;
    private   $priv_bar = Null;

    public function __construct(){
        $this->pub_bar  = new childClass();
        $this->prot_bar = new childClass();
        $this->priv_bar = new childClass();
    }
}

class childClass {
    public    $pub  = 'publicChild';
    protected $prot = 'protectedChild';
    private   $priv = 'privateChild';
}

$parent = new parentClass();

echo http_build_query($parent);
?>
```

The above example will output:

    pub=publicParent&pub_bar%5Bpub%5D=publicChild

### See Also

-   <span class="function">parse\_str</span>
-   <span class="function">parse\_url</span>
-   <span class="function">urlencode</span>
-   <span class="function">array\_walk</span>

parse\_url
==========

Parse a URL and return its components

### Description

<span class="type">mixed</span> <span
class="methodname">parse\_url</span> ( <span class="methodparam"><span
class="type">string</span> `$url`</span> \[, <span
class="methodparam"><span class="type">int</span> `$component`<span
class="initializer"> = -1</span></span> \] )

This function parses a URL and returns an associative array containing
any of the various components of the URL that are present. The values of
the array elements are *not* URL decoded.

This function is *not* meant to validate the given URL, it only breaks
it up into the above listed parts. Partial URLs are also accepted, <span
class="function">parse\_url</span> tries its best to parse them
correctly.

### Parameters

`url`  
The URL to parse. Invalid characters are replaced by *\_*.

<!-- -->

`component`  
Specify one of **`PHP_URL_SCHEME`**, **`PHP_URL_HOST`**,
**`PHP_URL_PORT`**, **`PHP_URL_USER`**, **`PHP_URL_PASS`**,
**`PHP_URL_PATH`**, **`PHP_URL_QUERY`** or **`PHP_URL_FRAGMENT`** to
retrieve just a specific URL component as a <span
class="type">string</span> (except when **`PHP_URL_PORT`** is given, in
which case the return value will be an <span
class="type">integer</span>).

### Return Values

On seriously malformed URLs, <span class="function">parse\_url</span>
may return **`FALSE`**.

If the `component` parameter is omitted, an associative <span
class="type">array</span> is returned. At least one element will be
present within the array. Potential keys within this array are:

-   <span class="simpara"> `scheme` - e.g. http </span>
-   <span class="simpara"> `host` </span>
-   <span class="simpara"> `port` </span>
-   <span class="simpara"> `user` </span>
-   <span class="simpara"> `pass` </span>
-   <span class="simpara"> `path` </span>
-   <span class="simpara"> `query` - after the question mark *?* </span>
-   <span class="simpara"> `fragment` - after the hashmark *\#* </span>

If the `component` parameter is specified, <span
class="function">parse\_url</span> returns a <span
class="type">string</span> (or an <span class="type">integer</span>, in
the case of **`PHP_URL_PORT`**) instead of an <span
class="type">array</span>. If the requested component doesn't exist
within the given URL, **`NULL`** will be returned.

### Examples

**Example \#1 A <span class="function">parse\_url</span> example**

``` php
<?php
$url = 'http://username:password@hostname:9090/path?arg=value#anchor';

var_dump(parse_url($url));
var_dump(parse_url($url, PHP_URL_SCHEME));
var_dump(parse_url($url, PHP_URL_USER));
var_dump(parse_url($url, PHP_URL_PASS));
var_dump(parse_url($url, PHP_URL_HOST));
var_dump(parse_url($url, PHP_URL_PORT));
var_dump(parse_url($url, PHP_URL_PATH));
var_dump(parse_url($url, PHP_URL_QUERY));
var_dump(parse_url($url, PHP_URL_FRAGMENT));
?>
```

The above example will output:

    array(8) {
      ["scheme"]=>
      string(4) "http"
      ["host"]=>
      string(8) "hostname"
      ["port"]=>
      int(9090)
      ["user"]=>
      string(8) "username"
      ["pass"]=>
      string(8) "password"
      ["path"]=>
      string(5) "/path"
      ["query"]=>
      string(9) "arg=value"
      ["fragment"]=>
      string(6) "anchor"
    }
    string(4) "http"
    string(8) "username"
    string(8) "password"
    string(8) "hostname"
    int(9090)
    string(5) "/path"
    string(9) "arg=value"
    string(6) "anchor"

**Example \#2 A <span class="function">parse\_url</span> example with
missing scheme**

``` php
<?php
$url = '//www.example.com/path?googleguy=googley';

// Prior to 5.4.7 this would show the path as "//www.example.com/path"
var_dump(parse_url($url));
?>
```

The above example will output:

    array(3) {
      ["host"]=>
      string(15) "www.example.com"
      ["path"]=>
      string(5) "/path"
      ["query"]=>
      string(17) "googleguy=googley"
    }

### Notes

> **Note**:
>
> This function may not give correct results for relative URLs.

> **Note**:
>
> This function is intended specifically for the purpose of parsing URLs
> and not URIs. However, to comply with PHP's backwards compatibility
> requirements it makes an exception for the file:// scheme where triple
> slashes (file:///...) are allowed. For any other scheme this is
> invalid.

### See Also

-   <span class="function">pathinfo</span>
-   <span class="function">parse\_str</span>
-   <span class="function">http\_build\_query</span>
-   <span class="function">dirname</span>
-   <span class="function">basename</span>
-   <a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>

rawurldecode
============

Decode URL-encoded strings

### Description

<span class="type">string</span> <span
class="methodname">rawurldecode</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

Returns a string in which the sequences with percent (*%*) signs
followed by two hex digits have been replaced with literal characters.

### Parameters

`str`  
The URL to be decoded.

### Return Values

Returns the decoded URL, as a string.

### Examples

**Example \#1 <span class="function">rawurldecode</span> example**

``` php
<?php

echo rawurldecode('foo%20bar%40baz'); // foo bar@baz

?>
```

### Notes

> **Note**:
>
> <span class="function">rawurldecode</span> does not decode plus
> symbols ('+') into spaces. <span class="function">urldecode</span>
> does.

### See Also

-   <span class="function">rawurlencode</span>
-   <span class="function">urldecode</span>
-   <span class="function">urlencode</span>
-   <a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>

rawurlencode
============

URL-encode according to RFC 3986

### Description

<span class="type">string</span> <span
class="methodname">rawurlencode</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

Encodes the given string according to
<a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>.

### Parameters

`str`  
The URL to be encoded.

### Return Values

Returns a string in which all non-alphanumeric characters except
*-\_.\~* have been replaced with a percent (*%*) sign followed by two
hex digits. This is the encoding described in
<a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>
for protecting literal characters from being interpreted as special URL
delimiters, and for protecting URLs from being mangled by transmission
media with character conversions (like some email systems).

> **Note**:
>
> Prior to PHP 5.3.0, rawurlencode encoded tildes (*\~*) as per
> <a href="http://www.faqs.org/rfcs/rfc1738" class="link external">» RFC 1738</a>.

### Examples

**Example \#1 including a password in an FTP URL**

``` php
<?php
echo '<a href="ftp://user:', rawurlencode('foo @+%/'),
     '@ftp.example.com/x.txt">';
?>
```

The above example will output:

    <a href="ftp://user:foo%20%40%2B%25%2F@ftp.example.com/x.txt">

Or, if you pass information in a PATH\_INFO component of the URL:

**Example \#2 <span class="function">rawurlencode</span> example 2**

``` php
<?php
echo '<a href="http://example.com/department_list_script/',
    rawurlencode('sales and marketing/Miami'), '">';
?>
```

The above example will output:

    <a href="http://example.com/department_list_script/sales%20and%20marketing%2FMiami">

### See Also

-   <span class="function">rawurldecode</span>
-   <span class="function">urldecode</span>
-   <span class="function">urlencode</span>
-   <a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>

urldecode
=========

Decodes URL-encoded string

### Description

<span class="type">string</span> <span
class="methodname">urldecode</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

Decodes any *%<span class="replaceable">\#\#</span>* encoding in the
given string. Plus symbols ('*+*') are decoded to a space character.

### Parameters

`str`  
The string to be decoded.

### Return Values

Returns the decoded string.

### Examples

**Example \#1 <span class="function">urldecode</span> example**

``` php
<?php
$query = "my=apples&are=green+and+red";

foreach (explode('&', $query) as $chunk) {
    $param = explode("=", $chunk);

    if ($param) {
        printf("Value for parameter \"%s\" is \"%s\"<br/>\n", urldecode($param[0]), urldecode($param[1]));
    }
}
?>
```

### Notes

**Warning**

The superglobals `$_GET` and `$_REQUEST` are already decoded. Using
<span class="function">urldecode</span> on an element in `$_GET` or
`$_REQUEST` could have unexpected and dangerous results.

### See Also

-   <span class="function">urlencode</span>
-   <span class="function">rawurlencode</span>
-   <span class="function">rawurldecode</span>
-   <a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>

urlencode
=========

URL-encodes string

### Description

<span class="type">string</span> <span
class="methodname">urlencode</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

This function is convenient when encoding a string to be used in a query
part of a URL, as a convenient way to pass variables to the next page.

### Parameters

`str`  
The string to be encoded.

### Return Values

Returns a string in which all non-alphanumeric characters except *-\_.*
have been replaced with a percent (*%*) sign followed by two hex digits
and spaces encoded as plus (*+*) signs. It is encoded the same way that
the posted data from a WWW form is encoded, that is the same way as in
*application/x-www-form-urlencoded* media type. This differs from the
<a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>
encoding (see <span class="function">rawurlencode</span>) in that for
historical reasons, spaces are encoded as plus (+) signs.

### Examples

**Example \#1 <span class="function">urlencode</span> example**

``` php
<?php
echo '<a href="mycgi?foo=', urlencode($userinput), '">';
?>
```

**Example \#2 <span class="function">urlencode</span> and <span
class="function">htmlentities</span> example**

``` php
<?php
$query_string = 'foo=' . urlencode($foo) . '&bar=' . urlencode($bar);
echo '<a href="mycgi?' . htmlentities($query_string) . '">';
?>
```

### Notes

> **Note**:
>
> Be careful about variables that may match HTML entities. Things like
> &amp, &copy and &pound are parsed by the browser and the actual entity
> is used instead of the desired variable name. This is an obvious
> hassle that the W3C has been telling people about for years. The
> reference is here:
> <a href="http://www.w3.org/TR/html4/appendix/notes.html#h-B.2.2" class="link external">» http://www.w3.org/TR/html4/appendix/notes.html#h-B.2.2</a>.
>
> PHP supports changing the argument separator to the W3C-suggested
> semi-colon through the arg\_separator .ini directive. Unfortunately
> most user agents do not send form data in this semi-colon separated
> format. A more portable way around this is to use &amp; instead of &
> as the separator. You don't need to change PHP's arg\_separator for
> this. Leave it as &, but simply encode your URLs using <span
> class="function">htmlentities</span> or <span
> class="function">htmlspecialchars</span>.

### See Also

-   <span class="function">urldecode</span>
-   <span class="function">htmlentities</span>
-   <span class="function">rawurlencode</span>
-   <span class="function">rawurldecode</span>
-   <a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>

**Table of Contents**

-   [base64\_decode](/ref/url.html#base64_decode) — Decodes data encoded
    with MIME base64
-   [base64\_encode](/ref/url.html#base64_encode) — Encodes data with
    MIME base64
-   [get\_headers](/ref/url.html#get_headers) — Fetches all the headers
    sent by the server in response to an HTTP request
-   [get\_meta\_tags](/ref/url.html#get_meta_tags) — Extracts all meta
    tag content attributes from a file and returns an array
-   [http\_build\_query](/ref/url.html#http_build_query) — Generate
    URL-encoded query string
-   [parse\_url](/ref/url.html#parse_url) — Parse a URL and return its
    components
-   [rawurldecode](/ref/url.html#rawurldecode) — Decode URL-encoded
    strings
-   [rawurlencode](/ref/url.html#rawurlencode) — URL-encode according to
    RFC 3986
-   [urldecode](/ref/url.html#urldecode) — Decodes URL-encoded string
-   [urlencode](/ref/url.html#urlencode) — URL-encodes string

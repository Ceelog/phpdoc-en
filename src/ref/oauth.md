oauth\_get\_sbs
===============

Generate a Signature Base String

### Description

<span class="type">string</span> <span
class="methodname">oauth\_get\_sbs</span> ( <span
class="methodparam"><span class="type">string</span>
`$http_method`</span> , <span class="methodparam"><span
class="type">string</span> `$uri`</span> \[, <span
class="methodparam"><span class="type">array</span>
`$request_parameters`</span> \] )

Generates a Signature Base String according to pecl/oauth.

### Parameters

`http_method`  
The HTTP method.

`uri`  
URI to encode.

`request_parameters`  
Array of request parameters.

### Return Values

Returns a Signature Base String.

oauth\_urlencode
================

Encode a URI to RFC 3986

### Description

<span class="type">string</span> <span
class="methodname">oauth\_urlencode</span> ( <span
class="methodparam"><span class="type">string</span> `$uri`</span> )

Encodes a URI to
<a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>.

### Parameters

`uri`  
URI to encode.

### Return Values

Returns an
<a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>
encoded string.

**Table of Contents**

-   [oauth\_get\_sbs](/ref/oauth.html#oauth_get_sbs) — Generate a
    Signature Base String
-   [oauth\_urlencode](/ref/oauth.html#oauth_urlencode) — Encode a URI
    to RFC 3986

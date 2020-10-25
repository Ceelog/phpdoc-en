OAuth
=====

**Table of Contents**

-   [Introduction](/intro/oauth.html)
-   [Installing/Configuring](/oauth/setup.html)
    -   [Requirements](/oauth/setup.html#Requirements)
    -   [Installation](/oauth/setup.html#Installation)
    -   [Runtime
        Configuration](/oauth/setup.html#Runtime%20Configuration)
    -   [Resource Types](/oauth/setup.html#Resource%20Types)
-   [Predefined Constants](/oauth/constants.html)
-   [Examples](/oauth/examples.html)
    -   [FireEagle](/oauth/examples.html#FireEagle)
-   [OAuth Functions](/ref/oauth.html)
    -   [oauth\_get\_sbs](/ref/oauth.html#oauth_get_sbs) — Generate a
        Signature Base String
    -   [oauth\_urlencode](/ref/oauth.html#oauth_urlencode) — Encode a
        URI to RFC 3986
-   [OAuth](/class/oauth.html) — The OAuth class
    -   [OAuth::\_\_construct](/class/oauth.html#OAuth::__construct) —
        Create a new OAuth object
    -   [OAuth::\_\_destruct](/class/oauth.html#OAuth::__destruct) — The
        destructor
    -   [OAuth::disableDebug](/class/oauth.html#OAuth::disableDebug) —
        Turn off verbose debugging
    -   [OAuth::disableRedirects](/class/oauth.html#OAuth::disableRedirects)
        — Turn off redirects
    -   [OAuth::disableSSLChecks](/class/oauth.html#OAuth::disableSSLChecks)
        — Turn off SSL checks
    -   [OAuth::enableDebug](/class/oauth.html#OAuth::enableDebug) —
        Turn on verbose debugging
    -   [OAuth::enableRedirects](/class/oauth.html#OAuth::enableRedirects)
        — Turn on redirects
    -   [OAuth::enableSSLChecks](/class/oauth.html#OAuth::enableSSLChecks)
        — Turn on SSL checks
    -   [OAuth::fetch](/class/oauth.html#OAuth::fetch) — Fetch an OAuth
        protected resource
    -   [OAuth::generateSignature](/class/oauth.html#OAuth::generateSignature)
        — Generate a signature
    -   [OAuth::getAccessToken](/class/oauth.html#OAuth::getAccessToken)
        — Fetch an access token
    -   [OAuth::getCAPath](/class/oauth.html#OAuth::getCAPath) — Gets CA
        information
    -   [OAuth::getLastResponse](/class/oauth.html#OAuth::getLastResponse)
        — Get the last response
    -   [OAuth::getLastResponseHeaders](/class/oauth.html#OAuth::getLastResponseHeaders)
        — Get headers for last response
    -   [OAuth::getLastResponseInfo](/class/oauth.html#OAuth::getLastResponseInfo)
        — Get HTTP information about the last response
    -   [OAuth::getRequestHeader](/class/oauth.html#OAuth::getRequestHeader)
        — Generate OAuth header string signature
    -   [OAuth::getRequestToken](/class/oauth.html#OAuth::getRequestToken)
        — Fetch a request token
    -   [OAuth::setAuthType](/class/oauth.html#OAuth::setAuthType) — Set
        authorization type
    -   [OAuth::setCAPath](/class/oauth.html#OAuth::setCAPath) — Set CA
        path and info
    -   [OAuth::setNonce](/class/oauth.html#OAuth::setNonce) — Set the
        nonce for subsequent requests
    -   [OAuth::setRequestEngine](/class/oauth.html#OAuth::setRequestEngine)
        — The setRequestEngine purpose
    -   [OAuth::setRSACertificate](/class/oauth.html#OAuth::setRSACertificate)
        — Set the RSA certificate
    -   [OAuth::setSSLChecks](/class/oauth.html#OAuth::setSSLChecks) —
        Tweak specific SSL checks for requests
    -   [OAuth::setTimestamp](/class/oauth.html#OAuth::setTimestamp) —
        Set the timestamp
    -   [OAuth::setToken](/class/oauth.html#OAuth::setToken) — Sets the
        token and secret
    -   [OAuth::setVersion](/class/oauth.html#OAuth::setVersion) — Set
        the OAuth version
-   [OAuthProvider](/class/oauthprovider.html) — The OAuthProvider class
    -   [OAuthProvider::addRequiredParameter](/class/oauthprovider.html#OAuthProvider::addRequiredParameter)
        — Add required parameters
    -   [OAuthProvider::callconsumerHandler](/class/oauthprovider.html#OAuthProvider::callconsumerHandler)
        — Calls the consumerNonceHandler callback
    -   [OAuthProvider::callTimestampNonceHandler](/class/oauthprovider.html#OAuthProvider::callTimestampNonceHandler)
        — Calls the timestampNonceHandler callback
    -   [OAuthProvider::calltokenHandler](/class/oauthprovider.html#OAuthProvider::calltokenHandler)
        — Calls the tokenNonceHandler callback
    -   [OAuthProvider::checkOAuthRequest](/class/oauthprovider.html#OAuthProvider::checkOAuthRequest)
        — Check an oauth request
    -   [OAuthProvider::\_\_construct](/class/oauthprovider.html#OAuthProvider::__construct)
        — Constructs a new OAuthProvider object
    -   [OAuthProvider::consumerHandler](/class/oauthprovider.html#OAuthProvider::consumerHandler)
        — Set the consumerHandler handler callback
    -   [OAuthProvider::generateToken](/class/oauthprovider.html#OAuthProvider::generateToken)
        — Generate a random token
    -   [OAuthProvider::is2LeggedEndpoint](/class/oauthprovider.html#OAuthProvider::is2LeggedEndpoint)
        — is2LeggedEndpoint
    -   [OAuthProvider::isRequestTokenEndpoint](/class/oauthprovider.html#OAuthProvider::isRequestTokenEndpoint)
        — Sets isRequestTokenEndpoint
    -   [OAuthProvider::removeRequiredParameter](/class/oauthprovider.html#OAuthProvider::removeRequiredParameter)
        — Remove a required parameter
    -   [OAuthProvider::reportProblem](/class/oauthprovider.html#OAuthProvider::reportProblem)
        — Report a problem
    -   [OAuthProvider::setParam](/class/oauthprovider.html#OAuthProvider::setParam)
        — Set a parameter
    -   [OAuthProvider::setRequestTokenPath](/class/oauthprovider.html#OAuthProvider::setRequestTokenPath)
        — Set request token path
    -   [OAuthProvider::timestampNonceHandler](/class/oauthprovider.html#OAuthProvider::timestampNonceHandler)
        — Set the timestampNonceHandler handler callback
    -   [OAuthProvider::tokenHandler](/class/oauthprovider.html#OAuthProvider::tokenHandler)
        — Set the tokenHandler handler callback
-   [OAuthException](/class/oauthexception.html) — OAuthException class

Introduction
------------

The OAuth extension provides a simple interface to interact with data
providers using the OAuth HTTP specification to protect private
resources.

Class synopsis
--------------

**OAuth**

<span class="ooclass"> class **OAuth** </span> {

/\* Properties \*/

<span class="modifier">public</span> `$debug` ;

<span class="modifier">public</span> `$sslChecks` ;

<span class="modifier">public</span> `$debugInfo` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$consumer_key`</span> , <span class="methodparam"><span
class="type">string</span> `$consumer_secret`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$signature_method`<span class="initializer"> =
**`OAUTH_SIG_METHOD_HMACSHA1`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$auth_type`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">disableDebug</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">disableRedirects</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">disableSSLChecks</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">enableDebug</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">enableRedirects</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">enableSSLChecks</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">fetch</span> ( <span class="methodparam"><span
class="type">string</span> `$protected_resource_url`</span> \[, <span
class="methodparam"><span class="type">array</span>
`$extra_parameters`</span> \[, <span class="methodparam"><span
class="type">string</span> `$http_method`</span> \[, <span
class="methodparam"><span class="type">array</span>
`$http_headers`</span> \]\]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">generateSignature</span> ( <span
class="methodparam"><span class="type">string</span>
`$http_method`</span> , <span class="methodparam"><span
class="type">string</span> `$url`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$extra_parameters`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getAccessToken</span> ( <span
class="methodparam"><span class="type">string</span>
`$access_token_url`</span> \[, <span class="methodparam"><span
class="type">string</span> `$auth_session_handle`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$verifier_token`</span> \[, <span class="methodparam"><span
class="type">string</span> `$http_method`</span> \]\]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getCAPath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getLastResponse</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getLastResponseHeaders</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getLastResponseInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getRequestHeader</span> ( <span
class="methodparam"><span class="type">string</span>
`$http_method`</span> , <span class="methodparam"><span
class="type">string</span> `$url`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$extra_parameters`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getRequestToken</span> ( <span
class="methodparam"><span class="type">string</span>
`$request_token_url`</span> \[, <span class="methodparam"><span
class="type">string</span> `$callback_url`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$http_method`</span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setAuthType</span> ( <span
class="methodparam"><span class="type">int</span> `$auth_type`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">setCAPath</span> (\[ <span
class="methodparam"><span class="type">string</span> `$ca_path`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$ca_info`</span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">setNonce</span> ( <span
class="methodparam"><span class="type">string</span> `$nonce`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setRequestEngine</span> ( <span
class="methodparam"><span class="type">int</span> `$reqengine`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">setRSACertificate</span> ( <span
class="methodparam"><span class="type">string</span> `$cert`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSSLChecks</span> ( <span
class="methodparam"><span class="type">int</span> `$sslcheck`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">setTimestamp</span> ( <span
class="methodparam"><span class="type">string</span> `$timestamp`</span>
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setToken</span> ( <span
class="methodparam"><span class="type">string</span> `$token`</span> ,
<span class="methodparam"><span class="type">string</span>
`$token_secret`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setVersion</span> ( <span
class="methodparam"><span class="type">string</span> `$version`</span> )

}

Properties
----------

`debug`  

`sslChecks`  

`debugInfo`  

OAuth::\_\_construct
====================

Create a new OAuth object

### Description

<span class="modifier">public</span> <span
class="methodname">OAuth::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span>
`$consumer_key`</span> , <span class="methodparam"><span
class="type">string</span> `$consumer_secret`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$signature_method`<span class="initializer"> =
**`OAUTH_SIG_METHOD_HMACSHA1`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$auth_type`<span
class="initializer"> = 0</span></span> \]\] )

Creates a new OAuth object

### Parameters

`consumer_key`  
The consumer key provided by the service provider.

`consumer_secret`  
The consumer secret provided by the service provider.

`signature_method`  
This optional parameter defines which signature method to use, by
default it is **`OAUTH_SIG_METHOD_HMACSHA1`** (HMAC-SHA1).

`auth_type`  
This optional parameter defines how to pass the OAuth parameters to a
consumer, by default it is **`OAUTH_AUTH_TYPE_AUTHORIZATION`** (in the
*Authorization* header).

OAuth::\_\_destruct
===================

The destructor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuth::\_\_destruct</span> ( <span
class="methodparam">void</span> )

The destructor.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">OAuth::\_\_construct</span>

OAuth::disableDebug
===================

Turn off verbose debugging

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::disableDebug</span> ( <span
class="methodparam">void</span> )

Turns off verbose request information (off by default). Alternatively,
the <a href="/class/oauth.html#" class="link">debug</a> property can be
set to a **`FALSE`** value to turn debug off.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`**

### Changelog

| Version           | Description                                                                         |
|-------------------|-------------------------------------------------------------------------------------|
| PECL oauth 0.99.8 | The related <a href="/class/oauth.html#" class="link">debug</a> property was added. |

### See Also

-   <span class="methodname">OAuth::enableDebug</span>

OAuth::disableRedirects
=======================

Turn off redirects

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::disableRedirects</span> ( <span
class="methodparam">void</span> )

Disable redirects from being followed automatically, thus allowing the
request to be manually redirected.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`**

### See Also

-   <span class="methodname">OAuth::enableRedirects</span>

OAuth::disableSSLChecks
=======================

Turn off SSL checks

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::disableSSLChecks</span> ( <span
class="methodparam">void</span> )

Turns off the usual SSL peer certificate and host checks, this is not
for production environments. Alternatively, the `sslChecks` member can
be set to **`FALSE`** to turn SSL checks off.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`**

### Changelog

| Version           | Description                      |
|-------------------|----------------------------------|
| PECL oauth 0.99.8 | The `sslChecks` member was added |

### See Also

-   <span class="methodname">OAuth::enableSSLChecks</span>

OAuth::enableDebug
==================

Turn on verbose debugging

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::enableDebug</span> ( <span
class="methodparam">void</span> )

Turns on verbose request information useful for debugging, the debug
information is stored in the `debugInfo` member. Alternatively, the
`debug` member can be set to a non-**`FALSE`** value to turn debug on.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`**

### Changelog

| Version           | Description                                    |
|-------------------|------------------------------------------------|
| PECL oauth 0.99.8 | The `debug` and `debugInfo` members were added |

### See Also

-   <span class="methodname">OAuth::disableDebug</span>

OAuth::enableRedirects
======================

Turn on redirects

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::enableRedirects</span> ( <span
class="methodparam">void</span> )

Follow and sign redirects automatically, which is enabled by default.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`**

### See Also

-   <span class="methodname">OAuth::disableRedirects</span>

OAuth::enableSSLChecks
======================

Turn on SSL checks

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::enableSSLChecks</span> ( <span
class="methodparam">void</span> )

Turns on the usual SSL peer certificate and host checks (enabled by
default). Alternatively, the `sslChecks` member can be set to a
non-**`FALSE`** value to turn SSL checks off.

### Parameters

This function has no parameters.

### Return Values

**`TRUE`**

### Changelog

| Version           | Description                      |
|-------------------|----------------------------------|
| PECL oauth 0.99.8 | The `sslChecks` member was added |

### See Also

-   <span class="methodname">OAuth::disableSSLChecks</span>

OAuth::fetch
============

Fetch an OAuth protected resource

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">OAuth::fetch</span> ( <span
class="methodparam"><span class="type">string</span>
`$protected_resource_url`</span> \[, <span class="methodparam"><span
class="type">array</span> `$extra_parameters`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$http_method`</span> \[, <span class="methodparam"><span
class="type">array</span> `$http_headers`</span> \]\]\] )

Fetch a resource.

### Parameters

`protected_resource_url`  
URL to the OAuth protected resource.

`extra_parameters`  
Extra parameters to send with the request for the resource.

`http_method`  
One of the **`OAUTH_HTTP_METHOD_*`**
<a href="/oauth/constants.html" class="link">OAUTH constants</a>, which
includes GET, POST, PUT, HEAD, or DELETE.

HEAD (**`OAUTH_HTTP_METHOD_HEAD`**) can be useful for discovering
information prior to the request (if OAuth credentials are in the
*Authorization* header).

`http_headers`  
HTTP client headers (such as User-Agent, Accept, etc.)

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version           | Description                                                        |
|-------------------|--------------------------------------------------------------------|
| PECL oauth 1.0.0  | Previously returned **`NULL`** on failure, instead of **`FALSE`**. |
| PECL oauth 0.99.5 | The `http_method` parameter was added                              |
| PECL oauth 0.99.8 | The `http_headers` parameter was added                             |

### Examples

**Example \#1 <span class="function">OAuth::fetch</span> example**

``` php
<?php
try {
    $oauth = new OAuth("consumer_key","consumer_secret",OAUTH_SIG_METHOD_HMACSHA1,OAUTH_AUTH_TYPE_AUTHORIZATION);
    $oauth->setToken("access_token","access_token_secret");

    $oauth->fetch("http://photos.example.net/photo?file=vacation.jpg");

    $response_info = $oauth->getLastResponseInfo();
    header("Content-Type: {$response_info["content_type"]}");
    echo $oauth->getLastResponse();
} catch(OAuthException $E) {
    echo "Exception caught!\n";
    echo "Response: ". $E->lastResponse . "\n";
}
?>
```

### See Also

-   <span class="methodname">OAuth::getLastResponse</span>
-   <span class="methodname">OAuth::getLastResponseInfo</span>
-   <span class="methodname">OAuth::setToken</span>

OAuth::generateSignature
========================

Generate a signature

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">OAuth::generateSignature</span> ( <span
class="methodparam"><span class="type">string</span>
`$http_method`</span> , <span class="methodparam"><span
class="type">string</span> `$url`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$extra_parameters`</span> \] )

Generate a signature based on the final HTTP method, URL and a
string/array of parameters.

### Parameters

`http_method`  
HTTP method for request

`url`  
URL for request

`extra_parameters`  
String or array of additional parameters.

### Return Values

A string containing the generated signature or **`FALSE`** on failure

OAuth::getAccessToken
=====================

Fetch an access token

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">OAuth::getAccessToken</span> ( <span
class="methodparam"><span class="type">string</span>
`$access_token_url`</span> \[, <span class="methodparam"><span
class="type">string</span> `$auth_session_handle`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$verifier_token`</span> \[, <span class="methodparam"><span
class="type">string</span> `$http_method`</span> \]\]\] )

Fetch an access token, secret and any additional response parameters
from the service provider.

### Parameters

`access_token_url`  
URL to the access token API.

`auth_session_handle`  
Authorization session handle, this parameter does not have any citation
in the core OAuth 1.0 specification but may be implemented by large
providers.
<a href="http://oauth.pbwiki.com/ScalableOAuth/" class="link external">» See ScalableOAuth</a>
for more information.

`verifier_token`  
For service providers which support 1.0a, a `verifier_token` must be
passed while exchanging the request token for the access token. If the
`verifier_token` is present in `$_GET` or `$_POST` it is passed
automatically and the caller does not need to specify a `verifier_token`
(usually if the access token is exchanged at the oauth\_callback URL).
<a href="http://oauth.pbwiki.com/ScalableOAuth/" class="link external">» See ScalableOAuth</a>
for more information.

`http_method`  
HTTP method to use, e.g. *GET* or *POST*.

### Return Values

Returns an array containing the parsed OAuth response on success or
**`FALSE`** on failure.

### Changelog

| Version           | Description                                                        |
|-------------------|--------------------------------------------------------------------|
| PECL oauth 1.0.0  | Previously returned **`NULL`** on failure, instead of **`FALSE`**. |
| PECL oauth 0.99.9 | The `verifier_token` parameter was added                           |

### Examples

**Example \#1 <span class="function">OAuth::getAccessToken</span>
example**

``` php
<?php
try {
    $oauth = new OAuth(OAUTH_CONSUMER_KEY,OAUTH_CONSUMER_SECRET);
    $oauth->setToken($request_token,$request_token_secret);
    $access_token_info = $oauth->getAccessToken("https://example.com/oauth/access_token");
    if(!empty($access_token_info)) {
        print_r($access_token_info);
    } else {
        print "Failed fetching access token, response was: " . $oauth->getLastResponse();
    }
} catch(OAuthException $E) {
    echo "Response: ". $E->lastResponse . "\n";
}
?>
```

The above example will output something similar to:

    Array
    (
        [oauth_token] => some_token
        [oauth_token_secret] => some_token_secret
    )

### See Also

-   <span class="methodname">OAuth::getLastResponse</span>
-   <span class="methodname">OAuth::getLastResponseInfo</span>
-   <span class="methodname">OAuth::setToken</span>

OAuth::getCAPath
================

Gets CA information

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">OAuth::getCAPath</span> ( <span
class="methodparam">void</span> )

Gets the Certificate Authority information, which includes the ca\_path
and ca\_info set by <span class="methodname">OAuth::setCaPath</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of Certificate Authority information,
specifically as *ca\_path* and *ca\_info* keys within the returned
associative array.

### See Also

-   <span class="methodname">OAuth::setCAPath</span>
-   <span class="methodname">OAuth::getLastResponseInfo</span>

OAuth::getLastResponse
======================

Get the last response

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">OAuth::getLastResponse</span> ( <span
class="methodparam">void</span> )

Get the raw response of the most recent request.

### Parameters

This function has no parameters.

### Return Values

Returns a string containing the last response.

### See Also

-   <span class="methodname">OAuth::getLastResponseInfo</span>
-   <span class="methodname">OAuth::fetch</span>

OAuth::getLastResponseHeaders
=============================

Get headers for last response

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">OAuth::getLastResponseHeaders</span> ( <span
class="methodparam">void</span> )

Get headers for last response.

### Parameters

This function has no parameters.

### Return Values

A string containing the last response's headers or **`FALSE`** on
failure

OAuth::getLastResponseInfo
==========================

Get HTTP information about the last response

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">OAuth::getLastResponseInfo</span> ( <span
class="methodparam">void</span> )

Get HTTP information about the last response.

### Parameters

This function has no parameters.

### Return Values

Returns an array containing the response information for the last
request. Constants from <span class="function">curl\_getinfo</span> may
be used.

### See Also

-   <span class="methodname">OAuth::fetch</span>
-   <span class="methodname">OAuth::getLastResponse</span>

OAuth::getRequestHeader
=======================

Generate OAuth header string signature

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">OAuth::getRequestHeader</span> ( <span
class="methodparam"><span class="type">string</span>
`$http_method`</span> , <span class="methodparam"><span
class="type">string</span> `$url`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$extra_parameters`</span> \] )

Generate OAuth header string signature based on the final HTTP method,
URL and a string/array of parameters

### Parameters

`http_method`  
HTTP method for request.

`url`  
URL for request.

`extra_parameters`  
String or array of additional parameters.

### Return Values

A string containing the generated request header or **`FALSE`** on
failure

OAuth::getRequestToken
======================

Fetch a request token

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">OAuth::getRequestToken</span> ( <span
class="methodparam"><span class="type">string</span>
`$request_token_url`</span> \[, <span class="methodparam"><span
class="type">string</span> `$callback_url`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$http_method`</span> \]\] )

Fetch a request token, secret and any additional response parameters
from the service provider.

### Parameters

`request_token_url`  
URL to the request token API.

`callback_url`  
OAuth callback URL. If `callback_url` is passed and is an empty value,
it is set to "oob" to address the OAuth 2009.1 advisory.

`http_method`  
HTTP method to use, e.g. *GET* or *POST*.

### Return Values

Returns an array containing the parsed OAuth response on success or
**`FALSE`** on failure.

### Changelog

| Version           | Description                                                        |
|-------------------|--------------------------------------------------------------------|
| PECL oauth 1.0.0  | Previously returned **`NULL`** on failure, instead of **`FALSE`**. |
| PECL oauth 0.99.9 | The `callback_url` parameter was added                             |

### Examples

**Example \#1 <span class="function">OAuth::getRequestToken</span>
example**

``` php
<?php
try {
    $oauth = new OAuth(OAUTH_CONSUMER_KEY,OAUTH_CONSUMER_SECRET);
    $request_token_info = $oauth->getRequestToken("https://example.com/oauth/request_token");
    if(!empty($request_token_info)) {
        print_r($request_token_info);
    } else {
        print "Failed fetching request token, response was: " . $oauth->getLastResponse();
    }
} catch(OAuthException $E) {
    echo "Response: ". $E->lastResponse . "\n";
}
?>
```

The above example will output something similar to:

    Array
    (
        [oauth_token] => some_token
        [oauth_token_secret] => some_token_secret
    )

### See Also

-   <span class="methodname">OAuth::getLastResponse</span>
-   <span class="methodname">OAuth::getLastResponseInfo</span>

OAuth::setAuthType
==================

Set authorization type

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::setAuthType</span> ( <span
class="methodparam"><span class="type">int</span> `$auth_type`</span> )

Set where the OAuth parameters should be passed.

### Parameters

`auth_type`  
`auth_type` can be one of the following flags (in order of decreasing
preference as per OAuth 1.0 section 5.2):

**`OAUTH_AUTH_TYPE_AUTHORIZATION`**  
<span class="simpara"> Pass the OAuth parameters in the HTTP
*Authorization* header. </span>

**`OAUTH_AUTH_TYPE_FORM`**  
<span class="simpara"> Append the OAuth parameters to the HTTP POST
request body. </span>

**`OAUTH_AUTH_TYPE_URI`**  
<span class="simpara"> Append the OAuth parameters to the request URI.
</span>

**`OAUTH_AUTH_TYPE_NONE`**  
<span class="simpara"> None. </span>

### Return Values

Returns **`TRUE`** if a parameter is correctly set, otherwise
**`FALSE`** (e.g., if an invalid `auth_type` is passed in.)

### Changelog

| Version          | Description                                                        |
|------------------|--------------------------------------------------------------------|
| PECL oauth 1.0.0 | Previously returned **`NULL`** on failure, instead of **`FALSE`**. |

OAuth::setCAPath
================

Set CA path and info

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">OAuth::setCAPath</span> (\[ <span
class="methodparam"><span class="type">string</span> `$ca_path`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$ca_info`</span> \]\] )

Sets the Certificate Authority (CA), both for path and info.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`ca_path`  
The CA Path being set.

`ca_info`  
The CA Info being set.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** if either `ca_path` or
`ca_info` are considered invalid.

### Changelog

| Version          | Description                                                        |
|------------------|--------------------------------------------------------------------|
| PECL oauth 1.0.0 | Previously returned **`NULL`** on failure, instead of **`FALSE`**. |

### See Also

-   <span class="methodname">OAuth::getCaPath</span>

OAuth::setNonce
===============

Set the nonce for subsequent requests

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">OAuth::setNonce</span> ( <span
class="methodparam"><span class="type">string</span> `$nonce`</span> )

Sets the nonce for all subsequent requests.

### Parameters

`nonce`  
The value for oauth\_nonce.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** if the `nonce` is
considered invalid.

### Changelog

| Version          | Description                                                        |
|------------------|--------------------------------------------------------------------|
| PECL oauth 1.0.0 | Previously returned **`NULL`** on failure, instead of **`FALSE`**. |

### See Also

-   <span class="methodname">OAuth::setToken</span>
-   <span class="methodname">OAuth::setAuthType</span>
-   <span class="methodname">OAuth::setVersion</span>

OAuth::setRequestEngine
=======================

The setRequestEngine purpose

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuth::setRequestEngine</span> ( <span
class="methodparam"><span class="type">int</span> `$reqengine`</span> )

Sets the Request Engine, that will be sending the HTTP requests.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`reqengine`  
The desired request engine. Set to **`OAUTH_REQENGINE_STREAMS`** to use
PHP Streams, or **`OAUTH_REQENGINE_CURL`** to use
<a href="/book/curl.html" class="link">Curl</a>.

### Return Values

No value is returned.

### Errors/Exceptions

Emits an <span class="classname">OAuthException</span> exception if an
invalid request engine is chosen.

### Examples

**Example \#1 <span class="function">OAuth::setRequestEngine</span>
example**

``` php
<?php
$consumer = new OAuth();

$consumer->setRequestEngine(OAUTH_REQENGINE_STREAMS);
?>
```

### See Also

-   <a href="/book/curl.html" class="link">Curl</a>
-   <a href="/book/stream.html" class="link">PHP streams</a>
-   <span class="classname">OAuthException</span>

OAuth::setRSACertificate
========================

Set the RSA certificate

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">OAuth::setRSACertificate</span> ( <span
class="methodparam"><span class="type">string</span> `$cert`</span> )

Sets the RSA certificate.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`cert`  
The RSA certificate.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** on failure (e.g., the RSA
certificate cannot be parsed.)

### Changelog

| Version          | Description                                                        |
|------------------|--------------------------------------------------------------------|
| PECL oauth 1.0.0 | Previously returned **`NULL`** on failure, instead of **`FALSE`**. |

### Examples

**Example \#1 An <span
class="methodname">OAuth::setRsaCertificate</span> example**

``` php
<?php
$consume = new OAuth('1234', '', OAUTH_SIG_METHOD_RSASHA1);

$consume->setRSACertificate(file_get_contents('test.pem'));
?>
```

### See Also

-   <span class="methodname">OAuth::setCaPath</span>

OAuth::setSSLChecks
===================

Tweak specific SSL checks for requests

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::setSSLChecks</span> ( <span
class="methodparam"><span class="type">int</span> `$sslcheck`</span> )

Tweak specific SSL checks for requests.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`sslcheck`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

OAuth::setTimestamp
===================

Set the timestamp

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">OAuth::setTimestamp</span> ( <span
class="methodparam"><span class="type">string</span> `$timestamp`</span>
)

Sets the OAuth timestamp for subsequent requests.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`timestamp`  
The timestamp.

### Return Values

Returns **`TRUE`**, unless the `timestamp` is invalid, in which case
**`FALSE`** is returned.

### Changelog

| Version          | Description                                                        |
|------------------|--------------------------------------------------------------------|
| PECL oauth 1.0.0 | Previously returned **`NULL`** on failure, instead of **`FALSE`**. |

### See Also

-   <span class="methodname">OAuth::setNonce</span>

OAuth::setToken
===============

Sets the token and secret

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::setToken</span> ( <span
class="methodparam"><span class="type">string</span> `$token`</span> ,
<span class="methodparam"><span class="type">string</span>
`$token_secret`</span> )

Set the token and secret for subsequent requests.

### Parameters

`token`  
The OAuth token.

`token_secret`  
The OAuth token secret.

### Return Values

**`TRUE`**

### Examples

**Example \#1 <span class="function">OAuth::setToken</span> example**

``` php
<?php
$oauth = new OAuth(OAUTH_CONSUMER_KEY,OAUTH_CONSUMER_SECRET);
$oauth->setToken("token","token-secret");
?>
```

OAuth::setVersion
=================

Set the OAuth version

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">OAuth::setVersion</span> ( <span
class="methodparam"><span class="type">string</span> `$version`</span> )

Sets the OAuth version for subsequent requests

### Parameters

`version`  
OAuth version, default value is always "1.0"

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

Introduction
------------

Manages an OAuth provider class.

See also an external in-depth tutorial titled
<a href="http://toys.lerdorf.com/archives/55-Writing-an-OAuth-Provider-Service.html" class="link external">» Writing an OAuth Provider Service</a>,
which takes a hands-on approach to providing this service. There are
also
<a href="https://svn.php.net/viewvc/pecl/oauth/trunk/examples" class="link external">» OAuth provider examples</a>
within the OAuth extensions sources.

Class synopsis
--------------

**OAuthProvider**

<span class="ooclass"> class **OAuthProvider** </span> {

/\* Methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">bool</span> <span
class="methodname">addRequiredParameter</span> ( <span
class="methodparam"><span class="type">string</span>
`$req_params`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">callconsumerHandler</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">callTimestampNonceHandler</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">calltokenHandler</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">checkOAuthRequest</span> (\[ <span
class="methodparam"><span class="type">string</span> `$uri`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$method`</span> \]\] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">array</span>
`$params_array`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">consumerHandler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback_function`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">string</span>
<span class="methodname">generateToken</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$strong`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">is2LeggedEndpoint</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$params_array`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">isRequestTokenEndpoint</span> ( <span
class="methodparam"><span class="type">bool</span>
`$will_issue_request_token`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">bool</span> <span
class="methodname">removeRequiredParameter</span> ( <span
class="methodparam"><span class="type">string</span>
`$req_params`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">string</span>
<span class="methodname">reportProblem</span> ( <span
class="methodparam"><span class="type">string</span>
`$oauthexception`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$send_headers`<span class="initializer"> =
**`TRUE`**</span></span> \] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">bool</span> <span class="methodname">setParam</span>
( <span class="methodparam"><span class="type">string</span>
`$param_key`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$param_val`</span> \] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">bool</span> <span
class="methodname">setRequestTokenPath</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">timestampNonceHandler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback_function`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">tokenHandler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback_function`</span> )

}

OAuthProvider::addRequiredParameter
===================================

Add required parameters

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">bool</span> <span
class="methodname">OAuthProvider::addRequiredParameter</span> ( <span
class="methodparam"><span class="type">string</span>
`$req_params`</span> )

Add required oauth provider parameters.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`req_params`  
The required parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span
    class="methodname">OAuthProvider::removeRequiredParameter</span>

OAuthProvider::callconsumerHandler
==================================

Calls the consumerNonceHandler callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::callconsumerHandler</span> (
<span class="methodparam">void</span> )

Calls the registered consumer handler callback function, which is set
with <span class="methodname">OAuthProvider::consumerHandler</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Errors/Exceptions

Emits an **`E_ERROR`** level error if the callback function cannot be
called, or was not specified.

### See Also

-   <span class="methodname">OAuthProvider::consumerHandler</span>

OAuthProvider::callTimestampNonceHandler
========================================

Calls the timestampNonceHandler callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::callTimestampNonceHandler</span>
( <span class="methodparam">void</span> )

Calls the registered timestamp handler callback function, which is set
with <span
class="methodname">OAuthProvider::timestampNonceHandler</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Errors/Exceptions

Emits an **`E_ERROR`** level error if the callback function cannot be
called, or was not specified.

### See Also

-   <span class="methodname">OAuthProvider::timestampNonceHandler</span>

OAuthProvider::calltokenHandler
===============================

Calls the tokenNonceHandler callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::calltokenHandler</span> ( <span
class="methodparam">void</span> )

Calls the registered token handler callback function, which is set with
<span class="methodname">OAuthProvider::tokenHandler</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Errors/Exceptions

Emits an **`E_ERROR`** level error if the callback function cannot be
called, or was not specified.

### See Also

-   <span class="methodname">OAuthProvider::tokenHandler</span>

OAuthProvider::checkOAuthRequest
================================

Check an oauth request

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::checkOAuthRequest</span> (\[
<span class="methodparam"><span class="type">string</span> `$uri`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$method`</span> \]\] )

Checks an OAuth request.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`uri`  
The optional URI, or endpoint.

`method`  
The HTTP method. Optionally pass in one of the **`OAUTH_HTTP_METHOD_*`**
<a href="/oauth/constants.html" class="link">OAuth constants</a>.

### Return Values

No value is returned.

### Errors/Exceptions

Emits an **`E_ERROR`** level error if the HTTP method cannot be
detected.

### See Also

-   <span class="methodname">OAuthProvider::reportProblem</span>

OAuthProvider::\_\_construct
============================

Constructs a new OAuthProvider object

### Description

<span class="modifier">public</span> <span
class="methodname">OAuthProvider::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">array</span>
`$params_array`</span> \] )

Initiates a new <span class="classname">OAuthProvider</span> <span
class="type">object</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`params_array`  
Setting these optional parameters is limited to the
<a href="/features/commandline.html" class="link">CLI SAPI</a>.

### Return Values

An <span class="classname">OAuthProvider</span> <span
class="type">object</span>.

### Examples

**Example \#1 <span class="function">OAuthProvider::\_\_construct</span>
example**

``` php
<?php
try {

    $op = new OAuthProvider();

    // Uses user-defined callback functions
    $op->consumerHandler(array($this, 'lookupConsumer'));
    $op->timestampNonceHandler(array($this, 'timestampNonceChecker'));
    $op->tokenHandler(array($this, 'myTokenHandler'));

    // Ignore the foo_uri parameter
    $op->setParam('foo_uri', NULL);

    // No token needed for this end point
    $op->setRequestTokenPath('/v1/oauth/request_token');

    $op->checkOAuthRequest();

} catch (OAuthException $e) {

    echo OAuthProvider::reportProblem($e);
}
?>
```

### See Also

-   <span class="methodname">OAuthProvider::setParam</span>

OAuthProvider::consumerHandler
==============================

Set the consumerHandler handler callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::consumerHandler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback_function`</span> )

Sets the consumer handler callback, which will later be called with
<span class="methodname">OAuthProvider::callConsumerHandler</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`callback_function`  
The <span class="type">callable</span> functions name.

### Return Values

No value is returned.

### Examples

**Example \#1 Example <span
class="methodname">OAuthProvider::consumerHandler</span> callback**

``` php
<?php
function lookupConsumer($provider) {

    if ($provider->consumer_key === 'unknown') {
        return OAUTH_CONSUMER_KEY_UNKNOWN;
    } else if($provider->consumer_key == 'blacklisted' || $provider->consumer_key === 'throttled') {
        return OAUTH_CONSUMER_KEY_REFUSED;
    }

    $provider->consumer_secret = "the_consumers_secret";

    return OAUTH_OK;
}
?>
```

### See Also

-   <span class="methodname">OAuthProvider::callConsumerHandler</span>

OAuthProvider::generateToken
============================

Generate a random token

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">string</span>
<span class="methodname">OAuthProvider::generateToken</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$strong`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Generates a <span class="type">string</span> of pseudo-random bytes.

### Parameters

`size`  
The desired token length, in terms of bytes.

`strong`  
Setting to **`TRUE`** means */dev/random* will be used for entropy, as
otherwise the non-blocking */dev/urandom* is used. This parameter is
ignored on Windows.

### Return Values

The generated token, as a <span class="type">string</span> of bytes.

### Errors/Exceptions

If the `strong` parameter is **`TRUE`**, then an **`E_WARNING`** level
error will be emitted when the fallback <span
class="function">rand</span> implementation is used to fill the
remaining random bytes (e.g., when not enough random data was found,
initially).

### Examples

**Example \#1 <span class="function">OAuthProvider::generateToken</span>
example**

``` php
<?php
$p = new OAuthProvider();

$t = $p->generateToken(4);

echo strlen($t),  PHP_EOL;
echo bin2hex($t), PHP_EOL;

?>
```

The above example will output something similar to:

    4
    b6a82c27

### Notes

> **Note**:
>
> When not enough random data is available to the system, this function
> will fill the remaining random bytes using the internal PHP <span
> class="function">rand</span> implementation.

### See Also

-   <span class="function">openssl\_random\_pseudo\_bytes</span>
-   <span class="function">mcrypt\_create\_iv</span>

OAuthProvider::is2LeggedEndpoint
================================

is2LeggedEndpoint

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::is2LeggedEndpoint</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$params_array`</span> )

The 2-legged flow, or request signing. It does not require a token.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`params_array`  

### Return Values

An <span class="classname">OAuthProvider</span> <span
class="type">object</span>.

### Examples

**Example \#1 <span
class="function">OAuthProvider::is2LeggedEndpoint</span> example**

``` php
<?php

$provider = new OAuthProvider();

$provider->is2LeggedEndpoint(true);

?>
```

### See Also

-   <span class="methodname">OAuthProvider::\_\_construct</span>

OAuthProvider::isRequestTokenEndpoint
=====================================

Sets isRequestTokenEndpoint

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::isRequestTokenEndpoint</span> (
<span class="methodparam"><span class="type">bool</span>
`$will_issue_request_token`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`will_issue_request_token`  
Sets whether or not it will issue a request token, thus determining if
<span class="methodname">OAuthProvider::tokenHandler</span> needs to be
called.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">OAuthProvider::setRequestTokenPath</span>
-   <span class="methodname">OAuthProvider::reportProblem</span>

OAuthProvider::removeRequiredParameter
======================================

Remove a required parameter

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">bool</span> <span
class="methodname">OAuthProvider::removeRequiredParameter</span> ( <span
class="methodparam"><span class="type">string</span>
`$req_params`</span> )

Removes a required parameter.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`req_params`  
The required parameter to be removed.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">OAuthProvider::setParam</span>
-   <span class="methodname">OAuthProvider::addRequiredParameter</span>

OAuthProvider::reportProblem
============================

Report a problem

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="modifier">static</span> <span class="type">string</span>
<span class="methodname">OAuthProvider::reportProblem</span> ( <span
class="methodparam"><span class="type">string</span>
`$oauthexception`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$send_headers`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Pass in a problem as an <span class="classname">OAuthException</span>,
with possible problems listed in the
<a href="/oauth/constants.html" class="link">OAuth constants</a>
section.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`oauthexception`  
The <span class="classname">OAuthException</span>.

### Return Values

No value is returned.

### See Also

-   <span class="methodname">OAuthProvider::checkOAuthRequest</span>
-   <span
    class="methodname">OAuthProvider::isRequestTokenEndpoint</span>

OAuthProvider::setParam
=======================

Set a parameter

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">bool</span> <span
class="methodname">OAuthProvider::setParam</span> ( <span
class="methodparam"><span class="type">string</span> `$param_key`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$param_val`</span> \] )

Sets a parameter.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`param_key`  
The parameter key.

`param_val`  
The optional parameter value.

To exclude a parameter from signature verification, set its value to
**`NULL`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="methodname">OAuthProvider::addRequiredParameter</span>

OAuthProvider::setRequestTokenPath
==================================

Set request token path

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">bool</span> <span
class="methodname">OAuthProvider::setRequestTokenPath</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

Sets the request tokens path.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`path`  
The path.

### Return Values

**`TRUE`**

### See Also

-   <span class="methodname">OAuthProvider::tokenHandler</span>

OAuthProvider::timestampNonceHandler
====================================

Set the timestampNonceHandler handler callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::timestampNonceHandler</span> (
<span class="methodparam"><span class="type">callable</span>
`$callback_function`</span> )

Sets the timestamp nonce handler callback, which will later be called
with <span
class="methodname">OAuthProvider::callTimestampNonceHandler</span>.
Errors related to timestamp/nonce are thrown to this callback.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`callback_function`  
The <span class="type">callable</span> functions name.

### Return Values

No value is returned.

### Examples

**Example \#1 Example <span
class="methodname">OAuthProvider::timestampNonceHandler</span>
callback**

``` php
<?php
function timestampNonceChecker($provider) {

    if ($provider->nonce === 'bad') {
        return OAUTH_BAD_NONCE;
    } elseif ($provider->timestamp == '0') {
        return OAUTH_BAD_TIMESTAMP;
    }
    
    return OAUTH_OK;
}
?>
```

### See Also

-   <span
    class="methodname">OAuthProvider::callTimestampNonceHandler</span>

OAuthProvider::tokenHandler
===========================

Set the tokenHandler handler callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">OAuthProvider::tokenHandler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback_function`</span> )

Sets the token handler callback, which will later be called with <span
class="methodname">OAuthProvider::callTokenHandler</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`callback_function`  
The <span class="type">callable</span> functions name.

### Return Values

No value is returned.

### Examples

**Example \#1 Example <span
class="methodname">OAuthProvider::tokenHandler</span> callback**

``` php
<?php
function tokenHandler($provider) {
    
    if ($provider->token === 'rejected') {
        return OAUTH_TOKEN_REJECTED;
    } elseif ($provider->token === 'revoked') {
        return OAUTH_TOKEN_REVOKED;
    }

    $provider->token_secret = "the_tokens_secret";
    return OAUTH_OK;
}
?>
```

### See Also

-   <span class="methodname">OAuthProvider::callTokenHandler</span>

Introduction
------------

This exception is thrown when exceptional errors occur while using the
OAuth extension and contains useful debugging information.

Class synopsis
--------------

**OAuthException**

<span class="ooclass"> class **OAuthException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Properties \*/

<span class="modifier">public</span> `$lastResponse` ;

<span class="modifier">public</span> `$debugInfo` ;

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`lastResponse`  
The response of the exception which occurred, if any

`debugInfo`  

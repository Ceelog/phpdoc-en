Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

Most of these constants involve problems, which are also described
within the official OAuth
<a href="http://wiki.oauth.net/ProblemReporting" class="link external">» Problem Reporting</a>
documentation. Note however, that these constant names are specific to
PHP, although the naming scheme is similar.

**`OAUTH_SIG_METHOD_RSASHA1`** (<span class="type">string</span>)  
<span class="simpara"> OAuth *RSA-SHA1* signature method. </span>

**`OAUTH_SIG_METHOD_HMACSHA1`** (<span class="type">string</span>)  
OAuth *HMAC-SHA1* signature method.

**`OAUTH_SIG_METHOD_HMACSHA256`** (<span class="type">string</span>)  
<span class="simpara"> OAuth *HMAC-SHA256* signature method. </span>

**`OAUTH_AUTH_TYPE_AUTHORIZATION`** (<span class="type">string</span>)  
This constant represents putting OAuth parameters in the *Authorization*
header.

**`OAUTH_AUTH_TYPE_NONE`** (<span class="type">string</span>)  
This constant indicates a NoAuth OAuth request.

**`OAUTH_AUTH_TYPE_URI`** (<span class="type">string</span>)  
This constant represents putting OAuth parameters in the request URI.

**`OAUTH_AUTH_TYPE_FORM`** (<span class="type">string</span>)  
This constant represents putting OAuth parameters as part of the HTTP
POST body.

**`OAUTH_HTTP_METHOD_GET`** (<span class="type">string</span>)  
Use the *GET* method for the OAuth request.

**`OAUTH_HTTP_METHOD_POST`** (<span class="type">string</span>)  
Use the *POST* method for the OAuth request.

**`OAUTH_HTTP_METHOD_PUT`** (<span class="type">string</span>)  
Use the *PUT* method for the OAuth request.

**`OAUTH_HTTP_METHOD_HEAD`** (<span class="type">string</span>)  
Use the *HEAD* method for the OAuth request.

**`OAUTH_HTTP_METHOD_DELETE`** (<span class="type">string</span>)  
<span class="simpara"> Use the *DELETE* method for the OAuth request.
</span>

**`OAUTH_REQENGINE_STREAMS`** (<span class="type">int</span>)  
<span class="simpara"> Used by <span
class="methodname">OAuth::setRequestEngine</span> to set the engine to
<a href="/book/stream.html" class="link">PHP streams</a>, as opposed to
**`OAUTH_REQENGINE_CURL`** for
<a href="/book/curl.html" class="link">Curl</a>. </span>

**`OAUTH_REQENGINE_CURL`** (<span class="type">int</span>)  
<span class="simpara"> Used by <span
class="methodname">OAuth::setRequestEngine</span> to set the engine to
<a href="/book/curl.html" class="link">Curl</a>, as opposed to
**`OAUTH_REQENGINE_STREAMS`** for
<a href="/book/stream.html" class="link">PHP streams</a>. </span>

**`OAUTH_OK`** (<span class="type">int</span>)  
<span class="simpara"> Life is good. </span>

**`OAUTH_BAD_NONCE`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_nonce* value was used in a previous
request, therefore it cannot be used now. </span>

**`OAUTH_BAD_TIMESTAMP`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_timestamp* value was not accepted by
the service provider. In this case, the response should also contain the
*oauth\_acceptable\_timestamps* parameter. </span>

**`OAUTH_CONSUMER_KEY_UNKNOWN`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_consumer\_key* is temporarily
unacceptable to the service provider. For example, the service provider
may be throttling the consumer. </span>

**`OAUTH_CONSUMER_KEY_REFUSED`** (<span class="type">int</span>)  
<span class="simpara"> The consumer key was refused. </span>

**`OAUTH_INVALID_SIGNATURE`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_signature* is invalid, as it does not
match the signature computed by the service provider. </span>

**`OAUTH_TOKEN_USED`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_token* has been consumed. It can no
longer be used because it has already been used in the previous
request(s). </span>

**`OAUTH_TOKEN_EXPIRED`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_token* has expired. </span>

**`OAUTH_TOKEN_REVOKED`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_token* has been revoked, and will
never be accepted. </span>

**`OAUTH_TOKEN_REJECTED`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_token* was not accepted by the
service provider. The reason is not known, but it might be because the
token was never issued, already consumed, expired, and/or forgotten by
the service provider. </span>

**`OAUTH_VERIFIER_INVALID`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_verifier* is incorrect. </span>

**`OAUTH_PARAMETER_ABSENT`** (<span class="type">int</span>)  
<span class="simpara"> A required parameter was not received. In this
case, the response should also contain the *oauth\_parameters\_absent*
parameter. </span>

**`OAUTH_SIGNATURE_METHOD_REJECTED`** (<span class="type">int</span>)  
<span class="simpara"> The *oauth\_signature\_method* was not accepted
by service provider. </span>

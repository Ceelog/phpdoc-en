Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

The following constants are meant to be used with <span
class="function">parse\_url</span> and are available since PHP 5.1.2.

**`PHP_URL_SCHEME`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`PHP_URL_HOST`** (<span class="type">int</span>)  
<span class="simpara"> Outputs the hostname of the URL parsed. </span>

**`PHP_URL_PORT`** (<span class="type">int</span>)  
<span class="simpara"> Outputs the port of the URL parsed. </span>

**`PHP_URL_USER`** (<span class="type">int</span>)  
<span class="simpara"> Outputs the user of the URL parsed. </span>

**`PHP_URL_PASS`** (<span class="type">int</span>)  
<span class="simpara"> Outputs the password of the URL parsed. </span>

**`PHP_URL_PATH`** (<span class="type">int</span>)  
<span class="simpara"> Outputs the path of the URL parsed. </span>

**`PHP_URL_QUERY`** (<span class="type">int</span>)  
<span class="simpara"> Outputs the query string of the URL parsed.
</span>

**`PHP_URL_FRAGMENT`** (<span class="type">int</span>)  
<span class="simpara"> Outputs the fragment (string after the
hashmark \#) of the URL parsed. </span>

The following constants are meant to be used with <span
class="function">http\_build\_query</span>.

**`PHP_QUERY_RFC1738`** (<span class="type">int</span>)  
<span class="simpara"> Encoding is performed per
<a href="http://www.faqs.org/rfcs/rfc1738" class="link external">» RFC 1738</a>
and the *application/x-www-form-urlencoded* media type, which implies
that spaces are encoded as plus (*+*) signs. </span>

**`PHP_QUERY_RFC3986`** (<span class="type">int</span>)  
<span class="simpara"> Encoding is performed according to
<a href="http://www.faqs.org/rfcs/rfc3986" class="link external">» RFC 3986</a>,
and spaces will be percent encoded (*%20*). </span>

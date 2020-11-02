Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`INPUT_POST`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/reserved/variables/post.html" class="link">POST</a> variables.
</span>

**`INPUT_GET`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/reserved/variables/get.html" class="link">GET</a> variables.
</span>

**`INPUT_COOKIE`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/reserved/variables/cookies.html" class="link">COOKIE</a>
variables. </span>

**`INPUT_ENV`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/reserved/variables/environment.html" class="link">ENV</a>
variables. </span>

**`INPUT_SERVER`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/reserved/variables/server.html" class="link">SERVER</a>
variables. </span>

**`INPUT_SESSION`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/reserved/variables/session.html" class="link">SESSION</a>
variables. (not implemented yet) </span>

**`INPUT_REQUEST`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/reserved/variables/request.html" class="link">REQUEST</a>
variables. (not implemented yet) </span>

**`FILTER_FLAG_NONE`** (<span class="type">int</span>)  
<span class="simpara"> No flags. </span>

**`FILTER_REQUIRE_SCALAR`** (<span class="type">int</span>)  
<span class="simpara"> Flag used to require scalar as input </span>

**`FILTER_REQUIRE_ARRAY`** (<span class="type">int</span>)  
<span class="simpara"> Require an array as input. </span>

**`FILTER_FORCE_ARRAY`** (<span class="type">int</span>)  
<span class="simpara"> Always returns an array. </span>

**`FILTER_NULL_ON_FAILURE`** (<span class="type">int</span>)  
<span class="simpara"> Use NULL instead of FALSE on failure. </span>

**`FILTER_VALIDATE_INT`** (<span class="type">int</span>)  
<span class="simpara"> ID of "int" filter. </span>

**`FILTER_VALIDATE_BOOLEAN`** (<span class="type">int</span>)  
<span class="simpara"> ID of "boolean" filter. </span>

**`FILTER_VALIDATE_FLOAT`** (<span class="type">int</span>)  
<span class="simpara"> ID of "float" filter. </span>

**`FILTER_VALIDATE_REGEXP`** (<span class="type">int</span>)  
<span class="simpara"> ID of "validate\_regexp" filter. </span>

**`FILTER_VALIDATE_URL`** (<span class="type">int</span>)  
<span class="simpara"> ID of "validate\_url" filter. </span>

**`FILTER_VALIDATE_DOMAIN`** (<span class="type">int</span>)  
<span class="simpara"> ID of "validate\_domain" filter. (Available as of
PHP 7.0.0) </span>

**`FILTER_VALIDATE_EMAIL`** (<span class="type">int</span>)  
<span class="simpara"> ID of "validate\_email" filter. </span>

**`FILTER_VALIDATE_IP`** (<span class="type">int</span>)  
<span class="simpara"> ID of "validate\_ip" filter. </span>

**`FILTER_VALIDATE_MAC`** (<span class="type">int</span>)  
<span class="simpara"> ID of "validate\_mac\_address" filter. (Available
as of PHP 5.5.0) </span>

**`FILTER_DEFAULT`** (<span class="type">int</span>)  
<span class="simpara"> ID of default ("unsafe\_raw") filter. This is
equivalent to **`FILTER_UNSAFE_RAW`**. </span>

**`FILTER_UNSAFE_RAW`** (<span class="type">int</span>)  
<span class="simpara"> ID of "unsafe\_raw" filter. </span>

**`FILTER_SANITIZE_STRING`** (<span class="type">int</span>)  
<span class="simpara"> ID of "string" filter. </span>

**`FILTER_SANITIZE_STRIPPED`** (<span class="type">int</span>)  
<span class="simpara"> ID of "stripped" filter. </span>

**`FILTER_SANITIZE_ENCODED`** (<span class="type">int</span>)  
<span class="simpara"> ID of "encoded" filter. </span>

**`FILTER_SANITIZE_SPECIAL_CHARS`** (<span class="type">int</span>)  
<span class="simpara"> ID of "special\_chars" filter. </span>

**`FILTER_SANITIZE_EMAIL`** (<span class="type">int</span>)  
<span class="simpara"> ID of "email" filter. </span>

**`FILTER_SANITIZE_URL`** (<span class="type">int</span>)  
<span class="simpara"> ID of "url" filter. </span>

**`FILTER_SANITIZE_NUMBER_INT`** (<span class="type">int</span>)  
<span class="simpara"> ID of "number\_int" filter. </span>

**`FILTER_SANITIZE_NUMBER_FLOAT`** (<span class="type">int</span>)  
<span class="simpara"> ID of "number\_float" filter. </span>

**`FILTER_SANITIZE_MAGIC_QUOTES`** (<span class="type">int</span>)  
<span class="simpara"> ID of "magic\_quotes" filter. (Deprecated per PHP
7.3.0, use FILTER\_SANITIZE\_ADD\_SLASHES instead.) </span>

**`FILTER_SANITIZE_ADD_SLASHES`** (<span class="type">int</span>)  
<span class="simpara"> ID of "add\_slashes" filter. (Available as of PHP
7.3.0) </span>

**`FILTER_CALLBACK`** (<span class="type">int</span>)  
<span class="simpara"> ID of "callback" filter. </span>

**`FILTER_FLAG_ALLOW_OCTAL`** (<span class="type">int</span>)  
<span class="simpara"> Allow octal notation (*0\[0-7\]+*) in "int"
filter. </span>

**`FILTER_FLAG_ALLOW_HEX`** (<span class="type">int</span>)  
<span class="simpara"> Allow hex notation (*0x\[0-9a-fA-F\]+*) in "int"
filter. </span>

**`FILTER_FLAG_STRIP_LOW`** (<span class="type">int</span>)  
<span class="simpara"> Strip characters with ASCII value less than 32.
</span>

**`FILTER_FLAG_STRIP_HIGH`** (<span class="type">int</span>)  
<span class="simpara"> Strip characters with ASCII value greater than
127. </span>

**`FILTER_FLAG_STRIP_BACKTICK`** (<span class="type">int</span>)  
<span class="simpara"> Strips backtick characters. (Available as of PHP
5.3.2) </span>

**`FILTER_FLAG_ENCODE_LOW`** (<span class="type">int</span>)  
<span class="simpara"> Encode characters with ASCII value less than 32.
</span>

**`FILTER_FLAG_ENCODE_HIGH`** (<span class="type">int</span>)  
<span class="simpara"> Encode characters with ASCII value greater than
127. </span>

**`FILTER_FLAG_ENCODE_AMP`** (<span class="type">int</span>)  
<span class="simpara"> Encode *&*. </span>

**`FILTER_FLAG_NO_ENCODE_QUOTES`** (<span class="type">int</span>)  
<span class="simpara"> Don't encode *'* and *"*. </span>

**`FILTER_FLAG_EMPTY_STRING_NULL`** (<span class="type">int</span>)  
<span class="simpara"> (No use for now.) </span>

**`FILTER_FLAG_ALLOW_FRACTION`** (<span class="type">int</span>)  
<span class="simpara"> Allow fractional part in "number\_float" filter.
</span>

**`FILTER_FLAG_ALLOW_THOUSAND`** (<span class="type">int</span>)  
<span class="simpara"> Allow thousand separator (*,*) in "number\_float"
filter. </span>

**`FILTER_FLAG_ALLOW_SCIENTIFIC`** (<span class="type">int</span>)  
<span class="simpara"> Allow scientific notation (*e*, *E*) in
"number\_float" filter. </span>

**`FILTER_FLAG_PATH_REQUIRED`** (<span class="type">int</span>)  
<span class="simpara"> Require path in "validate\_url" filter. </span>

**`FILTER_FLAG_QUERY_REQUIRED`** (<span class="type">int</span>)  
<span class="simpara"> Require query in "validate\_url" filter. </span>

**`FILTER_FLAG_SCHEME_REQUIRED`** (<span class="type">int</span>)  
<span class="simpara"> Require scheme in "validate\_url" filter.
(Deprecated per PHP 7.3 as it is implied in the filter already.) </span>

**`FILTER_FLAG_HOST_REQUIRED`** (<span class="type">int</span>)  
<span class="simpara"> Require host in "validate\_url" filter.
(Deprecated per PHP 7.3 as it is implied in the filter already.) </span>

**`FILTER_FLAG_HOSTNAME`** (<span class="type">int</span>)  
<span class="simpara"> Require hostnames to start with an alphanumeric
character and contain only alphanumerics or hyphens. (Available as of
PHP 7.0.0) </span>

**`FILTER_FLAG_IPV4`** (<span class="type">int</span>)  
<span class="simpara"> Allow only IPv4 address in "validate\_ip" filter.
</span>

**`FILTER_FLAG_IPV6`** (<span class="type">int</span>)  
<span class="simpara"> Allow only IPv6 address in "validate\_ip" filter.
</span>

**`FILTER_FLAG_NO_RES_RANGE`** (<span class="type">int</span>)  
<span class="simpara"> Deny reserved addresses in "validate\_ip" filter.
</span>

**`FILTER_FLAG_NO_PRIV_RANGE`** (<span class="type">int</span>)  
<span class="simpara"> Deny private addresses in "validate\_ip" filter.
</span>

**`FILTER_FLAG_EMAIL_UNICODE`** (<span class="type">int</span>)  
<span class="simpara"> Accepts Unicode characters in the local part in
"validate\_email" filter. (Available as of PHP 7.1.0) </span>

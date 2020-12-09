Backward incompatible changes
-----------------------------

Although most existing PHP 5 code should work without changes, please
take note of some backward incompatible changes:

### Array keys won't be overwritten when defining an array as a property of a class via an array literal

Previously, arrays declared as class properties which mixed explicit and
implicit keys could have array elements silently overwritten if an
explicit key was the same as a sequential implicit key. For example:

``` php
<?php
class C {
    const ONE = 1;
    public $array = [
        self::ONE => 'foo',
        'bar',
        'quux',
    ];
}

var_dump((new C)->array);
?>
```

Output of the above example in PHP 5.5:

    array(2) {
      [0]=>
      string(3) "bar"
      [1]=>
      string(4) "quux"
    }

Output of the above example in PHP 5.6:

    array(3) {
      [1]=>
      string(3) "foo"
      [2]=>
      string(3) "bar"
      [3]=>
      string(4) "quux"
    }

### <span class="function">json\_decode</span> strictness

<span class="function">json\_decode</span> now rejects non-lowercase
variants of the JSON literals *true*, *false* and *null* at all times,
as per the JSON specification, and sets <span
class="function">json\_last\_error</span> accordingly. Previously,
inputs to <span class="function">json\_decode</span> that consisted
solely of one of these values in upper or mixed case were accepted.

This change will only affect cases where invalid JSON was being passed
to <span class="function">json\_decode</span>: valid JSON input is
unaffected and will continue to be parsed normally.

### Stream wrappers now verify peer certificates and host names by default when using SSL/TLS

All encrypted client streams now enable peer verification by default. By
default, this will use OpenSSL's default CA bundle to verify the peer
certificate. In most cases, no changes will need to be made to
communicate with servers with valid SSL certificates, as distributors
generally configure OpenSSL to use known good CA bundles.

The default CA bundle may be overridden on a global basis by setting
either the openssl.cafile or openssl.capath configuration setting, or on
a per request basis by using the
<a href="/context/ssl.html#context.ssl.cafile" class="link"><code class="parameter">cafile</code></a>
or
<a href="/context/ssl.html#context.ssl.capath" class="link"><code class="parameter">capath</code></a>
context options.

While not recommended in general, it is possible to disable peer
certificate verification for a request by setting the
<a href="/context/ssl.html#context.ssl.verify-peer" class="link"><code class="parameter">verify_peer</code></a>
context option to **`false`**, and to disable peer name validation by
setting the
<a href="/context/ssl.html#context.ssl.verify-peer-name" class="link"><code class="parameter">verify_peer_name</code></a>
context option to **`false`**.

### <a href="/book/gmp.html" class="link">GMP</a> resources are now objects

<a href="/book/gmp.html" class="link">GMP</a> resources are now objects.
The functional API implemented in the GMP extension has not changed, and
code should run unmodified unless it checks explicitly for a resource
using <span class="function">is\_resource</span> or similar.

### <a href="/book/mcrypt.html" class="link">Mcrypt</a> functions now require valid keys and IVs

<span class="function">mcrypt\_encrypt</span>, <span
class="function">mcrypt\_decrypt</span>, <span
class="function">mcrypt\_cbc</span>, <span
class="function">mcrypt\_cfb</span>, <span
class="function">mcrypt\_ecb</span>, <span
class="function">mcrypt\_generic</span> and <span
class="function">mcrypt\_ofb</span> will no longer accept keys or IVs
with incorrect sizes, and block cipher modes that require IVs will now
fail if an IV isn't provided.

### <a href="/book/curl.html" class="link">cURL</a> file uploads

Uploads using the @file syntax now require CURLOPT\_SAFE\_UPLOAD to be
set to **`false`**. <span class="classname">CURLFile</span> should be
used instead.

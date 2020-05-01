Changed functions
-----------------

### PHP Core

-   <span class="simpara"> <span class="function">crypt</span> will now
    raise an **`E_NOTICE`** error if the `salt` parameter is omitted.
    </span>
-   <span class="simpara"> <span class="function">substr\_compare</span>
    will now accept *0* for its `length` parameter. </span>
-   <span class="simpara"> <span class="function">unserialize</span>
    will now fail if passed serialised data that has been manipulated to
    attempt to instantiate an object without calling its constructor.
    </span>

### <a href="/book/curl.html" class="link">cURL</a>

-   <span class="simpara"> Uploads using the *@file* syntax are now only
    supported if the **`CURLOPT_SAFE_UPLOAD`** option is set to
    **`FALSE`**. <span class="classname">CURLFile</span> should be used
    instead. </span>

### <a href="/book/mcrypt.html" class="link">Mcrypt</a>

-   <span class="simpara"> The `source` parameter of <span
    class="function">mcrypt\_create\_iv</span> now defaults to
    **`MCRYPT_DEV_URANDOM`** instead of **`MCRYPT_DEV_RANDOM`**. </span>

### <a href="/book/openssl.html" class="link">OpenSSL</a>

-   <span class="simpara"> <span
    class="function">stream\_socket\_enable\_crypto</span> now allows
    the `crypto_type` parameter to be optional if the stream's SSL
    context includes the new `crypto_type` option. </span>

### <a href="/book/pgsql.html" class="link">PostgreSQL</a>

-   <span class="simpara"> <span class="function">pg\_insert</span>,
    <span class="function">pg\_select</span>, <span
    class="function">pg\_update</span> and <span
    class="function">pg\_delete</span> are no longer experimental.
    </span>
-   <span class="simpara"> <span
    class="function">pg\_send\_execute</span>, <span
    class="function">pg\_send\_prepare</span>, <span
    class="function">pg\_send\_query</span> and <span
    class="function">pg\_send\_query\_params</span> will no longer block
    until query write completion if the underlying socket stream for the
    database connection is set to non-blocking mode. </span>

### <a href="/book/reflection.html" class="link">Reflection</a>

-   <span class="simpara"> <span
    class="methodname">ReflectionClass::newInstanceWithoutConstructor</span>
    now allows non-final internal classes to be instantiated. </span>

### <a href="/book/xmlreader.html" class="link">XMLReader</a>

-   <span class="simpara"> <span
    class="methodname">XMLReader::getAttributeNs</span> and <span
    class="methodname">XMLReader::getAttributeNo</span> now return
    **`NULL`** if the attribute could not be found, like <span
    class="methodname">XMLReader::getAttribute</span>. </span>

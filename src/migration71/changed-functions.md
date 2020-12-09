Changed functions
-----------------

### PHP Core

-   <span class="simpara"> <span class="function">getopt</span> has an
    optional third parameter that exposes the index of the next element
    in the argument vector list to be processed. This is done via a
    by-ref parameter. </span>
-   <span class="simpara"> <span class="function">getenv</span> no
    longer requires its parameter. If the parameter is omitted, then the
    current environment variables will be returned as an associative
    array. </span>
-   <span class="simpara"> <span class="function">get\_headers</span>
    now has an additional parameter to enable for the passing of custom
    stream contexts. </span>
-   <span class="simpara"> <span
    class="function">output\_reset\_rewrite\_vars</span> no longer
    resets session URL rewrite variables. </span>
-   <span class="simpara"> <span class="function">parse\_url</span> is
    now more restrictive and supports RFC3986. </span>
-   <span class="simpara"> <span class="function">unpack</span> now
    accepts an optional third parameter to specify the offset to begin
    unpacking from. </span>

### File System

-   <span class="simpara"> <span
    class="function">file\_get\_contents</span> now accepts a negative
    seek offset if the stream is seekable. </span>
-   <span class="simpara"> <span class="function">tempnam</span> now
    emits a notice when falling back to the system's temp directory.
    </span>

### JSON

-   <span class="simpara"> <span class="function">json\_encode</span>
    now accepts a new option, **`JSON_UNESCAPED_LINE_TERMINATORS`**, to
    disable the escaping of U+2028 and U+2029 characters when
    **`JSON_UNESCAPED_UNICODE`** is supplied. </span>

### Multibyte String

-   <span class="simpara"> <span class="function">mb\_ereg</span> now
    rejects illegal byte sequences. </span>
-   <span class="simpara"> <span
    class="function">mb\_ereg\_replace</span> now rejects illegal byte
    sequences. </span>

### PDO

-   <span class="simpara"> <span
    class="methodname">PDO::lastInsertId</span> for PostgreSQL will now
    trigger an error when *nextval* has not been called for the current
    session (the postgres connection). </span>

### PostgreSQL

-   <span class="simpara"> <span
    class="function">pg\_last\_notice</span> now accepts an optional
    parameter to specify an operation. This can be done with one of the
    following new constants: **`PGSQL_NOTICE_LAST`**,
    **`PGSQL_NOTICE_ALL`**, or **`PGSQL_NOTICE_CLEAR`**. </span>
-   <span class="simpara"> <span class="function">pg\_fetch\_all</span>
    now accepts an optional second parameter to specify the result type
    (similar to the third parameter of <span
    class="function">pg\_fetch\_array</span>). </span>
-   <span class="simpara"> <span class="function">pg\_select</span> now
    accepts an optional fourth parameter to specify the result type
    (similar to the third parameter of <span
    class="function">pg\_fetch\_array</span>). </span>

### Session

-   <span class="simpara"> <span class="function">session\_start</span>
    now returns **`false`** and no longer initializes `$_SESSION` when
    it failed to start the session. </span>

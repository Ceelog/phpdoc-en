New Functions
-------------

PHP 5.3 introduced some new functions:

PHP Core:

-   <span class="simpara"> <span
    class="function">array\_replace</span> - Replaces elements from
    passed arrays into one array. </span>
-   <span class="simpara"> <span
    class="function">array\_replace\_recursive</span> - Recursively
    replaces elements from passed arrays into one array. </span>
-   <span class="simpara"> <span class="function">class\_alias</span> -
    Creates an alias for a user defined class. </span>
-   <span class="simpara"> <span
    class="function">forward\_static\_call</span> - Call a user function
    from a method context. </span>
-   <span class="simpara"> <span
    class="function">forward\_static\_call\_array</span> - Call a user
    function from a method context, with the arguments contained in an
    array. </span>
-   <span class="simpara"> <span
    class="function">gc\_collect\_cycles</span> - Forces collection of
    any existing garbage cycles. </span>
-   <span class="simpara"> <span class="function">gc\_disable</span> -
    Deactivates the circular reference collector. </span>
-   <span class="simpara"> <span class="function">gc\_enable</span> -
    Activates the circular reference collector. </span>
-   <span class="simpara"> <span class="function">gc\_enabled</span> -
    Returns the status of the circular reference collector. </span>
-   <span class="simpara"> <span
    class="function">get\_called\_class</span> - Return the name of the
    class a static method is called in. </span>
-   <span class="simpara"> <span class="function">gethostname</span> -
    Return the current host name for the local machine. </span>
-   <span class="simpara"> <span
    class="function">header\_remove</span> - Removes an HTTP header
    previously set using the <span class="function">header</span>
    function. </span>
-   <span class="simpara"> <span class="function">lcfirst</span> - Make
    a string's first character lowercase. </span>
-   <span class="simpara"> <span
    class="function">parse\_ini\_string</span> - Parse a configuration
    string. </span>
-   <span class="simpara"> <span
    class="function">quoted\_printable\_encode</span> - Convert an 8 bit
    string to a quoted-printable string. </span>
-   <span class="simpara"> <span class="function">str\_getcsv</span> -
    Parse a CSV string into an array. </span>
-   <span class="simpara"> <span
    class="function">stream\_context\_set\_default</span> - Set the
    default stream context. </span>
-   <span class="simpara"> <span
    class="function">stream\_supports\_lock</span> - Return **`true`**
    if the stream supports locking. </span>
-   <span class="simpara"> <span
    class="function">stream\_context\_get\_params</span> - Retrieve
    parameters from a stream context. </span>
-   <span class="simpara"> <span
    class="function">streamWrapper::stream\_cast</span> - Retrieve the
    underlying stream resource. </span>
-   <span class="simpara"> <span
    class="function">streamWrapper::stream\_set\_option</span> - Change
    stream options </span>

<a href="/book/datetime.html" class="link">Date/Time</a>:

-   <span class="simpara"> <span class="function">date\_add</span> -
    Adds an amount of days, months, years, hours, minutes and seconds to
    a <span class="classname">DateTime</span> object. </span>
-   <span class="simpara"> <span
    class="function">date\_create\_from\_format</span> - Returns a new
    <span class="classname">DateTime</span> object formatted according
    to the given format. </span>
-   <span class="simpara"> <span class="function">date\_diff</span> -
    Returns the difference between two <span
    class="classname">DateTime</span> objects. </span>
-   <span class="simpara"> <span
    class="function">date\_get\_last\_errors</span> - Returns the
    warnings and errors from the last date/time operation. </span>
-   <span class="simpara"> <span
    class="function">date\_parse\_from\_format</span> - Get information
    about a given date. </span>
-   <span class="simpara"> <span class="function">date\_sub</span> -
    Subtracts an amount of days, months, years, hours, minutes and
    seconds from a <span class="classname">DateTime</span> object.
    </span>
-   <span class="simpara"> <span
    class="function">timezone\_version\_get</span> - Returns the version
    of the timezonedb. </span>

<a href="/book/gmp.html" class="link">GMP</a>:

-   <span class="simpara"> <span class="function">gmp\_testbit</span> -
    Tests whether a bit is set. </span>

<a href="/book/hash.html" class="link">Hash</a>:

-   <span class="simpara"> <span class="function">hash\_copy</span> -
    Copy hashing context. </span>

<a href="/book/imap.html" class="link">IMAP</a>:

-   <span class="simpara"> <span class="function">imap\_gc</span> -
    Clears IMAP cache. </span>
-   <span class="simpara"> <span
    class="function">imap\_utf8\_to\_mutf7</span> - Encode a UTF-8
    string to modified UTF-7. </span>
-   <span class="simpara"> <span
    class="function">imap\_mutf7\_to\_utf8</span> - Decode a modified
    UTF-7 string to UTF-8. </span>

<a href="/book/json.html" class="link">JSON</a>:

-   <span class="simpara"> <span
    class="function">json\_last\_error</span> - Returns the last JSON
    error that occurred. </span>

<a href="/set/mysqlinfo.html#MySQLi" class="link">MySQL Improved</a>:

-   <span class="simpara"> <span
    class="function">mysqli\_fetch\_all</span> - Fetches all result rows
    as an associative array, a numeric array, or both. </span>
-   <span class="simpara"> <span
    class="function">mysqli\_get\_connection\_stats</span> - Returns
    statistics about the client connection. </span>
-   <span class="simpara"> <span class="function">mysqli\_poll</span> -
    Poll connections. </span>
-   <span class="simpara"> <span
    class="function">mysqli\_reap\_async\_query</span> - Get result from
    async query. </span>

<a href="/book/openssl.html" class="link">OpenSSL</a>:

-   <span class="simpara"> <span
    class="function">openssl\_random\_pseudo\_bytes</span> - Returns a
    string of the given length specified, filled with pseudo-random
    bytes. </span>

<a href="/book/pcntl.html" class="link">PCNTL</a>:

-   <span class="simpara"> <span
    class="function">pcntl\_signal\_dispatch</span> - Calls signal
    handlers for pending signals. </span>
-   <span class="simpara"> <span
    class="function">pcntl\_sigprocmask</span> - Sets and retrieves
    blocked signals. </span>
-   <span class="simpara"> <span
    class="function">pcntl\_sigtimedwait</span> - Wait for signals with
    a timeout. </span>
-   <span class="simpara"> <span
    class="function">pcntl\_sigwaitinfo</span> - Wait for signals.
    </span>

<a href="/book/pcre.html" class="link">PCRE</a>:

-   <span class="simpara"> <span class="function">preg\_filter</span> -
    Perform a regular expression search and replace, returning only
    results which matched the pattern. </span>

<a href="/book/sem.html" class="link">Semaphore</a>:

-   <span class="simpara"> <span
    class="function">msg\_queue\_exists</span> - Check whether a message
    queue exists. </span>
-   <span class="simpara"> <span class="function">shm\_has\_var</span> -
    Checks whether a specific key exists inside a shared memory segment.
    </span>

The following functions are now natively implemented, making them
available on all operating systems which can run PHP:

-   <span class="simpara"> <span class="function">acosh</span> </span>
-   <span class="simpara"> <span class="function">asinh</span> </span>
-   <span class="simpara"> <span class="function">atanh</span> </span>
-   <span class="simpara"> <span class="function">expm1</span> </span>
-   <span class="simpara"> <span class="function">log1p</span> </span>

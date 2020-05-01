Other changes to extensions
---------------------------

The following extensions can no longer be disabled during build
configuration:

-   <span class="simpara">
    <a href="/book/pcre.html" class="link">PCRE</a> </span>
-   <span class="simpara">
    <a href="/book/reflection.html" class="link">Reflection</a> </span>
-   <span class="simpara"> <a href="/book/spl.html" class="link">SPL</a>
    </span>

Changes in extension behaviour, and new features:

-   <span class="simpara">
    <a href="/book/datetime.html" class="link">Date and Time</a> - The
    TZ environment variable is no longer used to guess the timezone
    </span>
-   <span class="simpara">
    <a href="/book/curl.html" class="link">cURL</a> - cURL now supports
    SSH </span>
-   <span class="simpara">
    <a href="/book/network.html" class="link">Network</a> - <span
    class="function">dns\_check\_record</span> now returns an extra
    "entries" index, containing the TXT elements. </span>
-   <span class="simpara">
    <a href="/book/hash.html" class="link">Hash</a> - The SHA-224 and
    salsa hash algorithms are now supported. </span>
-   <span class="simpara">
    <a href="/book/mbstring.html" class="link">mbstring</a> - Now
    supports CP850 encoding. </span>
-   <span class="simpara">
    <a href="/book/oci8.html" class="link">OCI8</a> - A call to <span
    class="function">oci\_close</span> on a persistent connection, or a
    variable referencing a persistent connection going out of scope,
    will now roll back any uncommitted transaction. To avoid unexpected
    behavior, explicitly issue a commit or roll back as needed. The old
    behavior can be enabled with the INI directive
    <a href="/book/oci8.html#" class="link">oci8.old_oci_close_semantics</a>.
    </span> <span class="simpara"> Database Resident Connection Pooling
    (DRCP) and Fast Application Notification (FAN) are now supported.
    </span> <span class="simpara"> Oracle External Authentication is now
    supported (except on Windows). </span> <span class="simpara"> The
    <span class="function">oci\_bind\_by\_name</span> function now
    supports SQLT\_AFC (aka the CHAR datatype). </span>
-   <span class="simpara">
    <a href="/book/openssl.html" class="link">OpenSSL</a> - OpenSSL
    digest and cipher functions are now supported. It is also now
    possible to access the internal values of DSA, RSA and DH keys.
    </span>
-   <span class="simpara">
    <a href="/book/session.html" class="link">Session</a> - Sessions
    will no longer store session-files in *"/tmp"* when
    <a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
    restrictions apply, unless *"/tmp"* is explicitly added to the list
    of allowed paths. </span>
-   <span class="simpara">
    <a href="/book/soap.html" class="link">SOAP</a> Now supports sending
    user supplied HTTP headers. </span>
-   <span class="simpara">
    <a href="/set/mysqlinfo.html#MySQLi" class="link">MySQLi</a> Now
    supports persistent connections, by prepending the hostname with
    *"p:"*. </span>
-   <span class="simpara">
    <a href="/book/image.html" class="link">Image Processing and GD</a>
    The "JPG Support" index returned from <span
    class="function">gd\_info</span> has been renamed to "JPEG Support".
    </span>

Other changes
-------------

-   <span class="simpara"> **`E_ALL`** now includes **`E_STRICT`** level
    errors in the
    <a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
    configuration directive. </span>
-   <span class="simpara">
    <a href="/book/snmp.html" class="link">SNMP</a> now has an OOP API.
    </span> <span class="simpara"> Functions now return **`false`** on
    every error condition including SNMP-related (no such instance, end
    of MIB, etc). Thus, in particular, breaks previous behavior of
    get/walk functions returning an empty string on SNMP-related errors.
    </span> <span class="simpara"> Multi OID get/getnext/set queries are
    now supported. </span> <span class="simpara"> Dropped UCD-SNMP
    compatibility code, consider upgrading to net-snmp v5.3+, Net-SNMP
    v5.4+ is required for Windows version. </span> <span
    class="simpara"> In sake of adding support for IPv6 DNS name
    resolution of remote SNMP agent (peer) is done by extension now, not
    by Net-SNMP library anymore. </span>
-   <span class="simpara">
    <a href="/book/openssl.html" class="link">OpenSSL</a> now supports
    AES. </span>
-   <span class="simpara">
    <a href="/features/commandline.html" class="link">CLI SAPI</a>
    doesn't terminate any more on fatal errors when using interactive
    mode with readline support. </span>
-   <span class="simpara">
    <a href="/language/variables/superglobals.html" class="link">$_SERVER['REQUEST_TIME_FLOAT']</a>
    has been added to include microsecond precision. </span>
-   <span class="simpara"> Added new hash algorithms: fnv132, fnv164,
    joaat </span>
-   <span class="simpara"> Chained string offsets - e.g. $a\[0\]\[0\]
    where $a is a string - now work. </span>
-   <span class="simpara"> Arrays cast from <span
    class="type">SimpleXMLElement</span> now *always* contain all nodes
    instead of just the first matching node. All <span
    class="type">SimpleXMLElement</span> children are now *always*
    printed when using <span class="function">var\_dump</span>, <span
    class="function">var\_export</span> and <span
    class="function">print\_r</span>. </span>
-   <span class="simpara"> It's now possible to enforce the class'
    <a href="/language/oop5/decon.html" class="link">__construct</a>
    arguments in an abstract constructor in the base class. </span>

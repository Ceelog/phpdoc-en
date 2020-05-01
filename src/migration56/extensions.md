Other changes to extensions
---------------------------

### <a href="/book/curl.html" class="link">cURL</a>

A number of constants marked obsolete in the cURL library have now been
removed:

-   <span class="simpara"> **`CURLOPT_CLOSEPOLICY`** </span>
-   <span class="simpara"> **`CURLCLOSEPOLICY_CALLBACK`** </span>
-   <span class="simpara"> **`CURLCLOSEPOLICY_LEAST_RECENTLY_USED`**
    </span>
-   <span class="simpara"> **`CURLCLOSEPOLICY_LEAST_TRAFFIC`** </span>
-   <span class="simpara"> **`CURLCLOSEPOLICY_OLDEST`** </span>
-   <span class="simpara"> **`CURLCLOSEPOLICY_SLOWEST`** </span>

### <a href="/book/oci8.html" class="link">OCI8</a>

-   <span class="simpara"> Support for implicit result sets for Oracle
    Database 12c has been added via the new <span
    class="function">oci\_get\_implicit\_resultset</span> function.
    </span>
-   <span class="simpara"> Using *oci\_execute($s,
    OCI\_NO\_AUTO\_COMMIT)* for a SELECT no longer unnecessarily
    initiates an internal ROLLBACK during connection close. </span>
-   <span class="simpara"> Added DTrace probes controlled by the
    *--enable-dtrace* configure option. </span>
-   <span class="simpara"> <span
    class="function">oci\_internal\_debug</span> is now a no-op. </span>
-   <span class="simpara"> The <span class="function">phpinfo</span>
    output format for OCI8 has changed. </span>

### <a href="/book/zip.html" class="link">Zip</a>

A *--with-libzip* configure option has been added to use a system libzip
installation. libzip version 0.11 is required, with 0.11.2 or later
recommended.

### <a href="/set/mysqlinfo.html#MySQLi" class="link">MySQLi</a>

A new
<a href="/set/mysqlinfo.html#" class="link">mysqli.rollback_on_cached_plink</a>
option was added, which controls the rollback behavior of persistent
connections.

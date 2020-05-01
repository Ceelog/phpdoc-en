Changes made to Windows support
-------------------------------

Changes to the Windows releases:

-   <span class="simpara"> The minimum Windows version is now Windows XP
    SP3; Windows 98, ME, 2000 and NT4 are no longer supported. </span>
-   <span class="simpara"> Windows binaries now target i586 and later.
    i386 and i486 are not supported. </span>
-   <span class="simpara"> There is now experimental support for x64
    versions of PHP on Windows. </span>
-   <span class="simpara"> There is now compiler support for Visual C++
    9 (VC9), using Visual Studio 2008. Snapshots and releases will now
    also be available for VC9. Old binaries using VC6 are still
    supported and released in the line with VC9. </span>
-   <span class="simpara"> The
    <a href="/book/pdo.html#Oracle%20(PDO)" class="link">PDO_OCI</a>
    *php\_pdo\_oci8.dll* library (for use with Oracle version 8 client
    libraries) is no longer being built. Instead, use
    *php\_pdo\_oci.dll* (note no '8') with Oracle 10 or 11 client
    libraries. Connection to other database versions is still supported.
    </span>
-   <span class="simpara"> For the
    <a href="/book/oci8.html" class="link">OCI8</a> extension, a new
    library *php\_oci8\_11g.dll* is available in addition to
    *php\_oci8.dll*. Only one can be enabled at any time. Use
    *php\_oci8.dll* with Oracle 10.2 client libraries. Use
    *php\_oci8\_11g.dll* with Oracle 11 or later client libraries.
    Connection to other database versions is still supported. </span>

Windows support has been added for the following functions:

-   <span class="simpara"> <span class="function">checkdnsrr</span>
    </span>
-   <span class="simpara"> <span
    class="function">dns\_get\_record</span> </span>
-   <span class="simpara"> <span class="function">fnmatch</span> </span>
-   <span class="simpara"> <span class="function">getmxrr</span> </span>
-   <span class="simpara"> <span class="function">getopt</span> </span>
-   <span class="simpara"> <span
    class="function">imagecolorclosesthwb</span> </span>
-   <span class="simpara"> <span class="function">inet\_ntop</span>
    </span>
-   <span class="simpara"> <span class="function">inet\_pton</span>
    </span>
-   <span class="simpara"> <span class="function">link</span> </span>
-   <span class="simpara"> <span class="function">linkinfo</span>
    </span>
-   <span class="simpara"> <span
    class="function">mcrypt\_create\_iv</span> </span>
-   <span class="simpara"> <span class="function">readlink</span>
    </span>
-   <span class="simpara"> <span
    class="function">socket\_create\_pair</span> - This function was
    previously available on Windows, but was disabled as of PHP 4.3.0
    due to a bug. </span>
-   <span class="simpara"> <span
    class="function">stream\_socket\_pair</span> </span>
-   <span class="simpara"> <span class="function">symlink</span> </span>
-   <span class="simpara"> <span class="function">time\_nanosleep</span>
    </span>
-   <span class="simpara"> <span
    class="function">time\_sleep\_until</span> </span>

Other changes:

-   <span class="simpara"> Improved portability of the <span
    class="function">stat</span>, <span class="function">touch</span>,
    <span class="function">filemtime</span>, <span
    class="function">filesize</span> functions, and other related
    functions (100% portable for the available data). </span>
-   <span class="simpara"> It is now possible to create hard links on
    Windows using the <span class="function">link</span> function, and
    symbolic links using the <span class="function">symlink</span>
    function. Hard links are available as of Windows 2000, and symbolic
    links as of Windows Vista. </span>
-   <span class="simpara"> The Windows version of PHP now exposes a set
    of constants prefixed *PHP\_WINDOWS\_\**. A list of these constants
    and their usage can be found at
    <a href="/info/constants.html" class="xref">Predefined Constants</a>.
    </span>

**Warning**

Support for the ISAPI module has been dropped. Use the improved FastCGI
SAPI module instead.

> **Note**: <span class="simpara"> A new dedicated site for PHP on
> Windows is now available, including downloads, release candidates, and
> snapshots in various flavors (thread-safe/not-thread-safe, VC6/VC9,
> x86/x64). The URL of this site is
> <a href="https://windows.php.net/" class="link external">» https://windows.php.net/</a>.
> </span>

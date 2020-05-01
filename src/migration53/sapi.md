Changes in SAPI modules
-----------------------

-   <span class="simpara"> A new SAPI module named litespeed is now
    available. </span>
-   <span class="simpara"> FastCGI support in the CGI SAPI is now always
    enabled and can not be disabled. See *sapi/cgi/CHANGES* for more
    details. </span>
-   <span class="simpara"> A new CGI SAPI option, *-T*, can be used to
    measure repeated execution time of a script. </span>
-   <span class="simpara"> CGI/FastCGI now has support for
    .htaccess-style user-defined `php.ini` files. </span>
-   <span class="simpara"> The <span class="function">dl</span> function
    is now disabled by default, and is now available only under the CLI,
    CGI, and embed SAPIs. </span>

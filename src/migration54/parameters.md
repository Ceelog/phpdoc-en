Changed Functions
-----------------

Several functions were given new, optional parameters in PHP 5.4:

PHP Core:

-   <span class="simpara"> Added the optional `limit` parameter to <span
    class="function">debug\_backtrace</span> and <span
    class="function">debug\_print\_backtrace</span>, to limit the amount
    of stack frames returned. </span>
-   <span class="simpara"> <span class="function">is\_link</span> now
    works properly for symbolic links on Windows Vista or later. Earlier
    systems do not support symbolic links. </span>
-   <span class="simpara"> <span class="function">parse\_url</span> now
    recognizes the host when a scheme is omitted, and a leading
    component separator is present. As of PHP 5.4.7. </span>

OpenSSL:

-   <span class="simpara"> Added a no padding option to the <span
    class="function">openssl\_encrypt</span> and <span
    class="function">openssl\_decrypt</span> functions. </span>

Intl:

-   <span class="simpara"> <span class="function">idn\_to\_ascii</span>
    and <span class="function">idn\_to\_utf8</span> now take two extra
    parameters, one indicating the variant (IDNA 2003 or UTS \#46) and
    another, passed by reference, to return details about the operation
    in case UTS \#46 is chosen. </span>

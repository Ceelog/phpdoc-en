Changes in SAPI modules
-----------------------

-   <span class="simpara"> A new SAPI module named *cli-server* is now
    available. </span>
-   <span class="simpara"> Added CLI option *--rz* which shows
    information of the named Zend extension. </span>
-   <span class="simpara"> Added shortcut *\#inisetting=value* to change
    `php.ini` settings at run-time in interactive readline CLI </span>
-   <span class="simpara"> Added apache compatible functions: <span
    class="function">apache\_child\_terminate</span>, <span
    class="function">getallheaders</span>, <span
    class="function">apache\_request\_headers</span> and <span
    class="function">apache\_response\_headers</span> for FastCGI SAPI.
    </span>
-   <span class="simpara"> PHP-FPM: Added the *process.max* setting, to
    control the number of processes that FPM can fork. </span>

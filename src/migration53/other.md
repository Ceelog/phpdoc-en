Other changes
-------------

-   <span class="simpara"> <span
    class="function">SplFileInfo::getpathinfo</span> now returns
    information about the path name. </span>
-   <span class="simpara"> <span
    class="classname">SplObjectStorage</span> now has <span
    class="classname">ArrayAccess</span> support. It is now also
    possible to store associative information with objects in <span
    class="classname">SplObjectStorage</span>. </span>
-   <span class="simpara"> In the GD extension, there is now pixelation
    support available through the <span
    class="function">imagefilter</span> function. </span>
-   <span class="simpara"> <span class="function">var\_dump</span>
    output now includes private object properties. </span>
-   <span class="simpara"> <span class="function">session\_start</span>
    now returns **`false`** when session startup fails. </span>
-   <span class="simpara"> <span
    class="function">property\_exists</span> now checks the existence of
    a property independent of accessibility (like <span
    class="function">method\_exists</span>). </span>
-   <span class="simpara">
    <a href="/wrappers.html" class="link">Stream wrappers</a> can now be
    used by
    <a href="/ini/core.html#ini.include-path" class="link">include_path</a>.
    </span>
-   <span class="simpara"> The `initial` parameter for <span
    class="function">array\_reduce</span> can now be of any type.
    </span>
-   <span class="simpara"> The
    <a href="/ref/dir.html" class="link">directory functions</a> <span
    class="function">opendir</span>, <span
    class="function">scandir</span>, and <span
    class="function">dir</span> now use the default stream context if no
    explicit context is passed. </span>
-   <span class="simpara"> <span class="function">crypt</span> now has
    Blowfish and extended DES support, and <span
    class="function">crypt</span> features are now 100% portable. PHP
    has its own internal crypt implementation which drops into place
    when support for *crypt* or *crypt\_r* is not found. </span>
-   <span class="simpara"> <span class="function">getopt</span> now
    accepts "long options" on all platforms. Optional values and *=* as
    a separator for short options are now supported. </span>
-   <span class="simpara"> <span class="function">fopen</span> has a new
    mode option (*n*), which passes **`O_NONBLOCK`** to the underlying
    *open()* system call. Note that this mode is not currently supported
    on Windows. </span>
-   <span class="simpara"> <span class="function">getimagesize</span>
    now supports icon files (.ico). </span>
-   <span class="simpara"> The mhash extension have moved to PECL, but
    the <a href="/ref/hash.html" class="link">Hash</a> extension have
    been modified to support mhash if PHP is compiled with
    *--with-mhash*. Note that the Hash extension does not require the
    mhash library to be available whether or not the mhash emulation is
    enabled. </span>

Obtaining PHP
=============

This section has details about PHP download locations, and OS issues.

1.  [Where can I obtain PHP?](#faq.obtaining.where)
2.  [Are pre-compiled binary versions
    available?](#faq.obtaining.precompiled)
3.  [Where can I get libraries needed to compile some of the optional
    PHP extensions?](#faq.obtaining.optional)
4.  [How do I get these libraries to work?](#faq.obtaining.how)
5.  [I got the latest version of the PHP source code from the Git
    repository on my Windows machine, what do I need to compile
    it?](#faq.obtaining.compilent)
6.  [Where do I find the Browser Capabilities
    File?](#faq.obtaining.browscap)
7.  [What does thread safety mean when downloading
    PHP?](#faq.obtaining.threadsafety)

**Where can I obtain PHP?**  
You can download PHP from any of the members of the PHP network of
sites. These can be found at
<a href="https://www.php.net/" class="link external">» https://www.php.net/</a>.
You can also use anonymous Git to get the absolute latest version of the
source. For more information, go to
<a href="https://www.php.net/git.php" class="link external">» https://www.php.net/git.php</a>.

<!-- -->

**Are pre-compiled binary versions available?**  
We only distribute precompiled binaries for Windows systems, as we are
not able to compile PHP for every major Linux/Unix platform with every
extension combination. Also note, that many Linux distributions come
with PHP built in these days. Windows binaries can be downloaded from
our
<a href="https://www.php.net/downloads.php" class="link external">» Downloads</a>
page, for Linux binaries, please visit your distribution's website.

<!-- -->

**Where can I get libraries needed to compile some of the optional PHP extensions?**  
> **Note**: <span class="simpara"> Those marked with a \* are to the
> best of our knowledge not thread safe; they are not recommended for
> use in a multi-threaded environment. </span>

-   <span class="simpara">
    <a href="ftp://ftp.openldap.org/pub/OpenLDAP/openldap-stable/" class="link external">» LDAP (Unix)</a>.
    </span>
-   <span class="simpara">
    <a href="https://wiki.mozilla.org/LDAP_C_SDK" class="link external">» LDAP (Unix/Win)</a>
    : Mozilla Directory (LDAP) SDK </span>
-   <span class="simpara">
    <a href="http://www.bind9.net/download-openldap/" class="link external">» free LDAP server</a>.
    </span>
-   <span class="simpara">
    <a href="http://www.sleepycat.com/" class="link external">» Berkeley DB2 (Unix/Win)</a>
    : http://www.sleepycat.com/. </span>
-   <span class="simpara">
    <a href="http://www.net-snmp.org/" class="link external">» SNMP* (Unix):</a>
    . </span>
-   <span class="simpara">
    <a href="http://www.libgd.org/" class="link external">» GD (Unix/Win)</a>.
    </span>
-   <span class="simpara">
    <a href="http://www.hughes.com.au/" class="link external">» mSQL* (Unix)</a>.
    </span>
-   <span class="simpara">
    <a href="http://www.postgresql.org/" class="link external">» PostgreSQL (Unix)</a>.
    </span>
-   <span class="simpara">
    <a href="https://www.washington.edu/imap/" class="link external">» IMAP* (Win/Unix)</a>.
    </span>
-   <span class="simpara">
    <a href="http://www.sybase.com/" class="link external">» Sybase-CT* (Linux, libc5)</a>
    : Available locally. </span>
-   <span class="simpara">
    <a href="http://www.freetype.org/" class="link external">» FreeType (libttf):</a>.
    </span>
-   <span class="simpara">
    <a href="http://www.zlib.net/" class="link external">» ZLib (Unix/Win32)</a>.
    </span>
-   <span class="simpara">
    <a href="http://www.jclark.com/xml/expat.html" class="link external">» expat XML parser (Unix/Win32)</a>.
    </span>
-   <span class="simpara">
    <a href="http://www.pdflib.com/products/pdflib-family/" class="link external">» PDFLib</a>.
    </span>
-   <span class="simpara">
    <a href="http://mcrypt.sourceforge.net/" class="link external">» mcrypt</a>.
    </span>
-   <span class="simpara">
    <a href="http://mhash.sourceforge.net/" class="link external">» mhash</a>.
    </span>
-   <span class="simpara">
    <a href="ftp://sunsite.unc.edu/pub/Linux/libs/graphics/" class="link external">» t1lib</a>.
    </span>
-   <span class="simpara">
    <a href="http://dmalloc.com/" class="link external">» dmalloc</a>.
    </span>
-   <span class="simpara">
    <a href="http://aspell.net/" class="link external">» aspell</a>.
    </span>
-   <span class="simpara">
    <a href="http://cnswww.cns.cwru.edu/~chet/readline/rltop.html" class="link external">» readline</a>.
    </span>

<!-- -->

**How do I get these libraries to work?**  
You will need to follow instructions provided with the library. Some of
these libraries are detected automatically when you run the 'configure'
script of PHP (such as the GD library), and others you will have to
enable using '*--with-EXTENSION*' options to '*configure*'. Run
'*configure --help*' for a listing of these.

<!-- -->

**I got the latest version of the PHP source code from the Git repository on my Windows machine, what do I need to compile it?**  
See the PHP Wiki for the latest instructions:
<a href="https://wiki.php.net/internals/windows/stepbystepbuild" class="link external">» Step by Step Build Instructions</a>

<!-- -->

**Where do I find the Browser Capabilities File?**  
You can find a `browscap.ini` file at
<a href="http://browscap.org/" class="link external">» http://browscap.org/</a>.

<!-- -->

**What does thread safety mean when downloading PHP?**  
Thread Safety means that binary can work in a multithreaded webserver
context, such as Apache 2 on Windows. Thread Safety works by creating a
local storage copy in each thread, so that the data won't collide with
another thread.

So what do I choose? If you choose to run PHP as a CGI binary, then you
won't need thread safety, because the binary is invoked at each request.
For multithreaded webservers, such as IIS5 and IIS6, you should use the
threaded version of PHP.

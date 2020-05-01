Build Problems
==============

This section gathers most common errors that occur at build time.

1.  [I got the latest version of PHP using the anonymous Git service,
    but there's no configure script!](#faq.build.configure)
2.  [I'm having problems configuring PHP to work with Apache. It says it
    can't find httpd.h, but it's right where I said it
    is!](#faq.build.configuring)
3.  [While configuring PHP (./configure), you come across an error
    similar to the following: checking lex output file root...
    ./configure: lex: command not found configure: error: cannot find
    output from lex; giving up](#faq.build.lex)
4.  [When I try to start Apache, I get the following message: fatal:
    relocation error: file /path/to/libphp4.so: symbol
    ap\_block\_alarms: referenced symbol not
    found](#faq.build.apache-sharedcore)
5.  [When I run configure, it says that it can't find the include files
    or library for GD, gdbm, or some other
    package!](#faq.build.not-found)
6.  [When it is compiling the file language-parser.tab.c, it gives me
    errors that say yytname undeclared.](#faq.build.yytname)
7.  [When I run make, it seems to run fine but then fails when it tries
    to link the final application complaining that it can't find some
    files.](#faq.build.link)
8.  [When linking PHP, it complains about a number of undefined
    references.](#faq.build.undefined)
9.  [I can't figure out how to build PHP with Apache
    1.3.](#faq.build.apache)
10. [I have followed all the steps to install the Apache module version
    on Unix, and my PHP scripts show up in my browser or I am being
    asked to save the file.](#faq.build.not-running)
11. [It says to use: --activate-module=src/modules/php4/libphp4.a, but
    that file doesn't exist, so I changed it to
    --activate-module=src/modules/php4/libmodphp4.a and it doesn't
    work!? What's going on?](#faq.build.activate-module)
12. [When I try to build Apache with PHP as a static module using
    --activate-module=src/modules/php4/libphp4.a it tells me that my
    compiler is not ANSI compliant.](#faq.build.ansi)
13. [When I try to build PHP using --with-apxs I get strange error
    messages.](#faq.build.apxs)
14. [During make, I get errors in microtime, and a lot of RUSAGE\_
    stuff.](#faq.build.microtime)
15. [When compiling PHP with MySQL, configure runs fine but during make
    I get an error similar to the following:
    ext/mysql/libmysqlclient/my\_tempnam.o(.text+0x46): In function
    my\_tempnam': /php4/ext/mysql/libmysqlclient/my\_tempnam.c:103: the
    use of tempnam' is dangerous, better use mkstemp', what's
    wrong?](#faq.build.mysql.tempnam)
16. [I want to upgrade my PHP. Where can I find the ./configure line
    that was used to build my current PHP
    installation?](#faq.build.upgrade)
17. [When building PHP with the GD library it either gives strange
    compile errors or segfaults on execution.](#faq.build.gdlibs)
18. [When compiling PHP I seemingly get random errors, like it hangs.
    I'm using Solaris if that matters.](#faq.installation.needgnu)

**I got the latest version of PHP using the anonymous Git service, but there's no configure script!**  
You have to have the GNU autoconf package installed so you can generate
the configure script from `configure.in`. Just run **./buildconf** in
the top-level directory after getting the sources from the Git server.
(Also, unless you run **configure** with the *--enable-maintainer-mode*
option, the configure script will not automatically get rebuilt when the
`configure.in` file is updated, so you should make sure to do that
manually when you notice `configure.in` has changed. One symptom of this
is finding things like @VARIABLE@ in your Makefile after configure or
`config.status` is run.)

<!-- -->

**I'm having problems configuring PHP to work with Apache. It says it can't find `httpd.h`, but it's right where I said it is!**  
You need to tell the configure/setup script the location of the
top-level of your Apache source tree. This means that you want to
specify **--with-apache=/path/to/apache** and *not*
**--with-apache=/path/to/apache/src**.

**While configuring PHP (*./configure*), you come across an error
similar to the following:**

  
checking lex output file root... ./configure: lex: command not found  
configure: error: cannot find output from lex; giving up  

Be sure to read the
<a href="/install/unix.html" class="link">installation</a> instructions
carefully and note that you need both flex and bison installed to
compile PHP. Depending on your setup you will install bison and flex
from either source or a package, such as a RPM.

**When I try to start Apache, I get the following message:**

  
fatal: relocation error: file /path/to/libphp4.so:  
symbol ap\_block\_alarms: referenced symbol not found  

This error usually comes up when one compiles the Apache core program as
a DSO library for shared usage. Try to reconfigure apache, making sure
to use at least the following flags:

  
--enable-shared=max --enable-rule=SHARED\_CORE  

For more information, read the top-level Apache `INSTALL` file or the
Apache
<a href="http://httpd.apache.org/docs/current/dso.html" class="link external">» DSO manual page</a>.

**When I run configure, it says that it can't find the include files or library for GD, gdbm, or some other package!**  
You can make the configure script look for header files and libraries in
non-standard locations by specifying additional flags to pass to the C
preprocessor and linker, such as:

        CPPFLAGS=-I/path/to/include LDFLAGS=-L/path/to/library ./configure

If you're using a csh-variant for your login shell (why?), it would be:

        env CPPFLAGS=-I/path/to/include LDFLAGS=-L/path/to/library ./configure

<!-- -->

**When it is compiling the file `language-parser.tab.c`, it gives me errors that say *yytname undeclared*.**  
You need to update your version of Bison. You can find the latest
version at
<a href="http://www.gnu.org/software/bison/bison.html" class="link external">» http://www.gnu.org/software/bison/bison.html</a>.

<!-- -->

**When I run **make**, it seems to run fine but then fails when it tries to link the final application complaining that it can't find some files.**  
Some old versions of make that don't correctly put the compiled versions
of the files in the functions directory into that same directory. Try
running **cp \*.o functions** and then re-running **make** to see if
that helps. If it does, you should really upgrade to a recent version of
GNU make.

<!-- -->

**When linking PHP, it complains about a number of undefined references.**  
Take a look at the link line and make sure that all of the appropriate
libraries are being included at the end. Common ones that you might have
missed are '-ldl' and any libraries required for any database support
you included.

Some people have also reported that they had to add '-ldl' immediately
following `libphp4.a` when linking with Apache.

<!-- -->

**I can't figure out how to build PHP with Apache 1.3.**  
This is actually quite easy. Follow these steps carefully:

-   <span class="simpara"> Grab the latest Apache 1.3 distribution from
    <a href="http://httpd.apache.org/download.cgi" class="link external">» http://httpd.apache.org/download.cgi</a>.
    </span>
-   <span class="simpara"> Ungzip and untar it somewhere, for example
    `/usr/local/src/apache-1.3`. </span>
-   <span class="simpara"> Compile PHP by first running **./configure
    --with-apache=/\<path\>/apache-1.3** (substitute \<path\> for the
    actual path to your apache-1.3 directory). </span>
-   <span class="simpara"> Type **make** followed by **make install** to
    build PHP and copy the necessary files to the Apache distribution
    tree. </span>
-   <span class="simpara"> Change directories into to your
    `/<path>/apache-1.3/src` directory and edit the `Configuration`
    file. Add to the file: *AddModule modules/php4/libphp4.a*. </span>
-   <span class="simpara"> Type: **./configure** followed by *make*.
    </span>
-   <span class="simpara"> You should now have a PHP-enabled httpd
    binary! </span>

*Note:* You can also use the new Apache *./configure* script. See the
instructions in the *README.configure* file which is part of your Apache
distribution. Also have a look at the `INSTALL` file in the PHP
distribution.

<!-- -->

**I have followed all the steps to install the Apache module version on Unix, and my PHP scripts show up in my browser or I am being asked to save the file.**  
This means that the PHP module is not getting invoked for some reason.
Three things to check before asking for further help:

-   <span class="simpara"> Make sure that the httpd binary you are
    running is the actual new httpd binary you just built. To do this,
    try running: */path/to/binary/httpd -l* </span> <span
    class="simpara"> If you don't see `mod_php4.c` listed then you are
    not running the right binary. Find and install the correct binary.
    </span>
-   <span class="simpara"> Make sure you have added the correct Mime
    Type to one of your *Apache .conf* files. It should be: *AddType
    application/x-httpd-php .php* </span> <span class="simpara"> Also
    make sure that this AddType line is not hidden away inside a
    \<Virtualhost\> or \<Directory\> block which would prevent it from
    applying to the location of your test script. </span>
-   <span class="simpara"> Finally, the default location of the Apache
    configuration files changed between Apache 1.2 and Apache 1.3. You
    should check to make sure that the configuration file you are adding
    the AddType line to is actually being read. You can put an obvious
    syntax error into your `httpd.conf` file or some other obvious
    change that will tell you if the file is being read correctly.
    </span>

<!-- -->

**It says to use: *--activate-module=src/modules/php4/libphp4.a*, but that file doesn't exist, so I changed it to *--activate-module=src/modules/php4/libmodphp4.a* and it doesn't work!? What's going on?**  
Note that the `libphp4.a` file is not supposed to exist. The apache
process will create it!

<!-- -->

**When I try to build Apache with PHP as a static module using *--activate-module=src/modules/php4/libphp4.a* it tells me that my compiler is not ANSI compliant.**  
This is a misleading error message from Apache that has been fixed in
more recent versions.

<!-- -->

**When I try to build PHP using **--with-apxs** I get strange error messages.**  
There are three things to check here. First, for some reason when Apache
builds the apxs Perl script, it sometimes ends up getting built without
the proper compiler and flags variables. Find your apxs script (try the
command **which apxs**), it's sometimes found in
`/usr/local/apache/bin/apxs` or `/usr/sbin/apxs`. Open it and check for
lines similar to these:

    my $CFG_CFLAGS_SHLIB  = ' ';          # substituted via Makefile.tmpl
    my $CFG_LD_SHLIB      = ' ';          # substituted via Makefile.tmpl
    my $CFG_LDFLAGS_SHLIB = ' ';          # substituted via Makefile.tmpl

If this is what you see, you have found your problem. They may contain
just spaces or other incorrect values, such as 'q()'. Change these lines
to say:

    my $CFG_CFLAGS_SHLIB  = '-fpic -DSHARED_MODULE'; # substituted via Makefile.tmpl
    my $CFG_LD_SHLIB      = 'gcc';                   # substituted via Makefile.tmpl
    my $CFG_LDFLAGS_SHLIB = q(-shared);              # substituted via Makefile.tmpl 

The second possible problem should only be an issue on Red Hat 6.1 and
6.2. The apxs script Red Hat ships is broken. Look for this line:

    my $CFG_LIBEXECDIR    = 'modules';         # substituted via APACI install

If you see the above line, change it to this:

    my $CFG_LIBEXECDIR    = '/usr/lib/apache'; # substituted via APACI install

Last, if you reconfigure/reinstall Apache, add a **make clean** to the
process after **./configure** and before **make**.

<!-- -->

**During **make**, I get errors in microtime, and a lot of *RUSAGE\_* stuff.**  
During the **make** portion of installation, if you encounter problems
that look similar to this:

    microtime.c: In function `php_if_getrusage':
    microtime.c:94: storage size of `usg' isn't known
    microtime.c:97: `RUSAGE_SELF' undeclared (first use in this function)
    microtime.c:97: (Each undeclared identifier is reported only once
    microtime.c:97: for each function it appears in.)
    microtime.c:103: `RUSAGE_CHILDREN' undeclared (first use in this function)
    make[3]: *** [microtime.lo] Error 1
    make[3]: Leaving directory `/home/master/php-4.0.1/ext/standard'
    make[2]: *** [all-recursive] Error 1
    make[2]: Leaving directory `/home/master/php-4.0.1/ext/standard'
    make[1]: *** [all-recursive] Error 1
    make[1]: Leaving directory `/home/master/php-4.0.1/ext'
    make: *** [all-recursive] Error 1

Your system is broken. You need to fix your `/usr/include` files by
installing a glibc-devel package that matches your glibc. This has
absolutely nothing to do with PHP. To prove this to yourself, try this
simple test:

    $ cat >test.c <<X
    #include <sys/resource.h>
    X
    $ gcc -E test.c >/dev/null

If that spews out errors, you know your include files are messed up.

<!-- -->

**When compiling PHP with MySQL, configure runs fine but during *make* I get an error similar to the following: *ext/mysql/libmysqlclient/my\_tempnam.o(.text+0x46): In function my\_tempnam': /php4/ext/mysql/libmysqlclient/my\_tempnam.c:103: the use of tempnam' is dangerous, better use mkstemp'*, what's wrong?**  
First, it's important to realize that this is a *Warning* and not a
fatal error. Because this is often the last output seen during *make*,
it may seem like a fatal error but it's not. Of course, if you set your
compiler to die on Warnings, it will. Also keep in mind that MySQL
support is enabled by default.

> **Note**:
>
> As of PHP 4.3.2, you'll also see the following text after the build
> (make) completes:
>
>   
> Build complete.  
> (It is safe to ignore warnings about tempnam and tmpnam).  

<!-- -->

**I want to upgrade my PHP. Where can I find the **./configure** line that was used to build my current PHP installation?**  
Either you look at config.nice file, in the source tree of your current
PHP installation or, if this is not available, you simply run a

``` php
<?php phpinfo(); ?>
```

script. On top of the output the **./configure** line, that was used to
build this PHP installation is shown.

<!-- -->

**When building PHP with the GD library it either gives strange compile errors or segfaults on execution.**  
Make sure your GD library and PHP are linked against the same depending
libraries (e.g. libpng).

<!-- -->

**When compiling PHP I seemingly get random errors, like it hangs. I'm using Solaris if that matters.**  
Using non-GNU utilities while compiling PHP may cause problems. Be sure
to use GNU tools in order to be certain that compiling PHP will work.
For example, on Solaris, using either the SunOS BSD-compatible or
Solaris versions of *sed* will not work, but using the GNU or Sun POSIX
(xpg4) versions of *sed* will work. Links:
<a href="http://www.gnu.org/software/sed/sed.html" class="link external">» GNU sed</a>,
<a href="http://www.gnu.org/software/flex/flex.html" class="link external">» GNU flex</a>,
and
<a href="http://www.gnu.org/software/bison/bison.html" class="link external">» GNU bison</a>.

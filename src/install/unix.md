Installation on Unix systems
============================

**Table of Contents**

-   [Apache 1.3.x on Unix systems](/install/unix/apache.html)
-   [Apache 2.x on Unix systems](/install/unix/apache2.html)
-   [Nginx 1.4.x on Unix systems](/install/unix/nginx.html)
-   [Lighttpd 1.4 on Unix systems](/install/unix/lighttpd-14.html)
-   [Sun, iPlanet and Netscape servers on Sun
    Solaris](/install/unix/sun.html)
-   [LiteSpeed Web Server/OpenLiteSpeed Web Server on Unix
    systems](/install/unix/litespeed.html)
-   [CGI and command line setups](/install/unix/commandline.html)
-   [HP-UX specific installation notes](/install/unix/hpux.html)
-   [OpenBSD installation notes](/install/unix/openbsd.html)
-   [Solaris specific installation tips](/install/unix/solaris.html)
-   [Debian GNU/Linux installation notes](/install/unix/debian.html)

This section will guide you through the general configuration and
installation of PHP on Unix systems. Be sure to investigate any sections
specific to your platform or web server before you begin the process.

As our manual outlines in the
<a href="/install/general.html" class="link">General Installation Considerations</a>
section, we are mainly dealing with web centric setups of PHP in this
section, although we will cover setting up PHP for command line usage as
well.

There are several ways to install PHP for the Unix platform, either with
a compile and configure process, or through various pre-packaged
methods. This documentation is mainly focused around the process of
compiling and configuring PHP. Many Unix like systems have some sort of
package installation system. This can assist in setting up a standard
configuration, but if you need to have a different set of features (such
as a secure server, or a different database driver), you may need to
build PHP and/or your web server. If you are unfamiliar with building
and compiling your own software, it is worth checking to see whether
somebody has already built a packaged version of PHP with the features
you need.

Prerequisite knowledge and software for compiling:

-   <span class="simpara"> Basic Unix skills (being able to operate
    "make" and a C compiler) </span>
-   <span class="simpara"> An ANSI C compiler </span>
-   <span class="simpara"> A web server </span>
-   <span class="simpara"> Any module specific components (such as GD,
    PDF libs, etc.) </span>

When building directly from Git sources or after custom modifications
you might also need:

-   <span class="simpara"> autoconf: 2.59+ (for PHP \>= 7.0.0), 2.64+
    (for PHP \>= 7.2.0) </span>
-   <span class="simpara"> automake: 1.4+ </span>
-   <span class="simpara"> libtool: 1.4.x+ (except 1.4.2) </span>
-   <span class="simpara"> re2c: 0.13.4+ (for PHP \> 7.0.0), 0.13.7+
    (for PHP \> 8.0.0) </span>
-   <span class="simpara"> bison: </span>
    -   <span class="simpara"> PHP 7.0 - 7.3: 2.4 or later (including
        Bison 3.x) </span>
    -   <span class="simpara"> PHP 7.4: \> 3.0 </span>

The initial PHP setup and configuration process is controlled by the use
of the command line options of the **configure** script. You could get a
list of all available options along with short explanations running
**./configure --help**. Our manual documents the different options
separately. You will find the
<a href="/configure/about.html" class="link">core options in the appendix</a>,
while the different extension specific options are described on the
reference pages.

When PHP is configured, you are ready to build the module and/or
executables. The command **make** should take care of this. If it fails
and you can't figure out why, see the
<a href="/install/problems.html" class="link">Problems section</a>.

> **Note**:
>
> Some Unix systems (such as OpenBSD and SELinux) may disallow mapping
> pages both writable and executable for security reasons, what is
> called PaX MPROTECT or W^X violation protection. This kind of memory
> mapping is, however, necessary for PCRE's JIT support, so either PHP
> has to be built
> <a href="/pcre/setup.html#Installation" class="link">without PCRE's JIT support</a>,
> or the binary has to be whitelisted by any means provided by the
> system.

> **Note**: <span class="simpara"> Cross-compiling for ARM with the
> Android toolchain is currently not supported. </span>

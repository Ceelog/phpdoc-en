List of core configure options
------------------------------

Below is a partial list of configure options used by the PHP `configure`
scripts when compiling in Unix-like environments. Most configure options
are listed in their appropriate locations on the extension reference
pages and not here. For a complete up-to-date list of configure options,
run **./configure --help** in your PHP source directory after running
**autoconf** (see also the
<a href="/install.html" class="link">Installation chapter</a>). You may
also be interested in reading the
<a href="http://www.airs.com/ian/configure/" class="link external">» GNU configure</a>
documentation for information on additional **configure** options such
as *--prefix=PREFIX*.

> **Note**:
>
> These are only used at compile time. If you want to alter PHP's
> runtime configuration, please see the chapter on
> <a href="/configuration.html" class="link">Runtime Configuration</a>.

-   <span class="simpara">
    <a href="/configure/about.html#configure.options.misc" class="link">Miscellaneous</a>
    </span>
-   <span class="simpara">
    <a href="/configure/about.html#configure.options.php" class="link">PHP Behaviour</a>
    </span>
-   <span class="simpara">
    <a href="/configure/about.html#configure.options.servers" class="link">Server</a>
    </span>

### Configure Options in PHP

#### Misc options

**--enable-debug**  
Compile with debugging symbols.

**--with-layout=TYPE**  
Sets how installed files will be laid out. Type is one of PHP (default)
or GNU.

**--with-pear=DIR**  
Install PEAR in DIR (default PREFIX/lib/php).

**--without-pear**  
Do not install PEAR.

**--enable-sigchild**  
Enable PHP's own SIGCHLD handler.

**--disable-rpath**  
Disable passing additional runtime library search paths.

**--enable-libgcc**  
Enable explicitly linking against libgcc.

**--enable-php-streams**  
Include experimental PHP streams. Do not use unless you are testing the
code!

**--with-zlib-dir\[=DIR\]**  
Define the location of zlib install directory.

**--with-tsrm-pthreads**  
Use POSIX threads (default).

**--enable-shared\[=PKGS\]**  
Build shared libraries \[default=yes\].

**--enable-static\[=PKGS\]**  
Build static libraries \[default=yes\].

**--enable-fast-install\[=PKGS\]**  
Optimize for fast installation \[default=yes\].

**--with-gnu-ld**  
Assume the C compiler uses GNU ld \[default=no\].

**--disable-libtool-lock**  
Avoid locking (might break parallel builds).

**--with-pic**  
Try to use only PIC/non-PIC objects \[default=use both\].

**--enable-memory-limit**  
Compile with memory limit support. (not available since PHP 5.2.1 -
always enabled)

**--disable-url-fopen-wrapper**  
Disable the URL-aware fopen wrapper that allows accessing files via HTTP
or FTP. (not available since PHP 5.2.5)

**--enable-versioning**  
Export only required symbols. See INSTALL for more information.

#### PHP options

**--enable-maintainer-mode**  
Enable make rules and dependencies not useful (and sometimes confusing)
to the casual installer.

**--with-config-file-path=PATH**  
Sets the path in which to look for `php.ini`, defaults to *PREFIX/lib*.

**--enable-safe-mode**  
Enable safe mode by default.

**Warning**
This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

**--with-exec-dir\[=DIR\]**  
Only allow executables in DIR when in safe mode defaults to
*/usr/local/php/bin*.

**Warning**
This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

**--enable-magic-quotes**  
Enable magic quotes by default.

**Warning**
This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

**--disable-short-tags**  
Disable the short-form \<? start tag by default.

**--enable-zend-multibyte**  
Enables multibyte code in the language parser and scanner to be
executed. When PHP is compiled with this option, it also enables the
<a href="/control-structures/declare.html#control-structures.declare.encoding" class="link">encoding</a>
directive in the
<a href="/control-structures/declare.html" class="link">declare</a>
construct.

**Warning**
This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

**--with-libdir**  
Specifies the directory where the libraries to build PHP exist on a Unix
system. For 64bit systems, its needed to specify this argument to the
*lib64* directory like: *--with-libdir=lib64*.

#### SAPI options

The following list contains the available SAPI&s (*Server Application
Programming Interface*) for PHP.

**--with-aolserver=DIR**  
Specify path to the installed AOLserver.

**--with-apxs\[=FILE\]**  
Build shared Apache module. FILE is the optional pathname to the Apache
apxs tool; defaults to apxs. Make sure you specify the version of apxs
that is actually installed on your system and NOT the one that is in the
apache source tarball.

**--with-apache\[=DIR\]**  
Build a static Apache module. DIR is the top-level Apache build
directory, defaults to `/usr/local/apache`.

**--with-mod\_charset**  
Enable transfer tables for mod\_charset (Russian Apache).

**--with-apxs2\[=FILE\]**  
Build shared Apache 2.0 module. FILE is the optional pathname to the
Apache apxs tool; defaults to apxs.

**--with-caudium=DIR**  
Build PHP as a Pike module for use with Caudium. DIR is the Caudium
server dir, with the default value `/usr/local/caudium/server`.

**--disable-cli**  
Disable building the CLI version of PHP (this forces
<a href="/configure/about.html#configure.without-pear" class="link">--without-pear</a>).
More information is available in the section about
<a href="/features/commandline.html" class="link">Using PHP from the command line</a>.

**--enable-phpdbg**  
Enable phpdbg interactive debugger SAPI module support in PHP 5.6.x or
later.

**--enable-embed\[=TYPE\]**  
Enable building of the embedded SAPI library. TYPE is either *shared* or
*static*, which defaults to *shared*.

**--with-isapi=DIR**  
Build PHP as an ISAPI module for use with Zeus.

**--with-nsapi=DIR**  
Specify path to the installed Netscape/iPlanet/SunONE Webserver.

**--with-phttpd=DIR**  
No information yet.

**--with-pi3web=DIR**  
Build PHP as a module for use with Pi3Web.

**--with-roxen=DIR**  
Build PHP as a Pike module. DIR is the base Roxen directory, normally
`/usr/local/roxen/server`.

**--enable-roxen-zts**  
Build the Roxen module using Zend Thread Safety.

**--with-servlet\[=DIR\]**  
Include servlet support. DIR is the base install directory for the JSDK.
This SAPI requires the java extension must be built as a shared dl.

**--with-thttpd=SRCDIR**  
Build PHP as thttpd module.

**--with-tux=MODULEDIR**  
Build PHP as a TUX module (Linux only).

**--with-webjames=SRCDIR**  
Build PHP as a WebJames module (RISC OS only)

**--disable-cgi**  
Disable building CGI version of PHP.

As of PHP 5.3.0 this argument enables FastCGI which previously had to be
enabled using *--enable-fastcgi*.

**--enable-force-cgi-redirect**  
Enable the security check for internal server redirects. You should use
this if you are running the CGI version with Apache.

As of PHP 5.3.0 this argument is enabled by default and no longer
exists. To disable this, the
<a href="/ini/core.html#ini.cgi.force-redirect" class="link">cgi.force_redirect</a>
ini directive should be set to *0*.

**--enable-discard-path**  
If this is enabled, the PHP CGI binary can safely be placed outside of
the web tree and people will not be able to circumvent `.htaccess`
security.

As of PHP 5.3.0 this argument is disabled by default and no longer
exists. To enable this feature the cgi.discard\_path ini directive must
be set to *1*.

**--enable-fastcgi**  
If this is enabled, the CGI module will be built with support for
FastCGI also.

As of PHP 5.3.0 this argument no longer exists and is enabled by
*--enable-cgi* instead.

**--disable-path-info-check**  
If this is disabled, paths such as `/info.php/test?a=b` will fail to
work. For more information see the
<a href="http://httpd.apache.org/docs/current/mod/core.html#acceptpathinfo" class="link external">» Apache Manual</a>.

As of PHP 5.3.0 this argument is enabled by default and no longer
exists. To disable this feature the
<a href="/ini/core.html#ini.cgi.fix-pathinfo" class="link">cgi.fix_pathinfo</a>
ini directive must be set to *0*.

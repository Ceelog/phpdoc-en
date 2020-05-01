Installation
============

This section holds common questions about the way to install PHP. PHP is
available for almost any OS, and almost any web server.

To install PHP, follow the instructions in
<a href="/install.html" class="xref">Installation and Configuration</a>.

1.  [Why shouldn't I use Apache2 with a threaded MPM in a production
    environment?](#faq.installation.apache2)
2.  [Unix/Windows: Where should my php.ini file be
    located?](#faq.installation.phpini)
3.  [Unix: I installed PHP, but every time I load a document, I get the
    message 'Document Contains No Data'! What's going on
    here?](#faq.installation.nodata)
4.  [Unix: I installed PHP using RPMS, but Apache isn't processing the
    PHP pages! What's going on here?](#faq.installation.processing)
5.  [Unix: I patched Apache with the FrontPage extensions patch, and
    suddenly PHP stopped working. Is PHP incompatible with the Apache
    FrontPage extensions?](#faq.installation.frontpage)
6.  [Unix/Windows: I have installed PHP, but when I try to access a PHP
    script file via my browser, I get a blank
    screen.](#faq.installation.blankscreen)
7.  [Unix/Windows: I have installed PHP, but when try to access a PHP
    script file via my browser, I get a server 500
    error.](#faq.installation.500error)
8.  [Some operating systems: I have installed PHP without errors, but
    when I try to start Apache I get undefined symbol errors:
    \[mybox:user /src/php5\] root\# apachectl configtest apachectl:
    /usr/local/apache/bin/httpd Undefined symbols: \_compress
    \_uncompress](#faq.installation.undefinedsyms)
9.  [Windows: I have installed PHP, but when I try to access a PHP
    script file via my browser, I get the error: cgi error: The
    specified CGI application misbehaved by not returning a complete set
    of HTTP headers. The headers it did return
    are:](#faq.installation.cgierror)
10. [Windows: I've followed all the instructions, but still can't get
    PHP and IIS to work together!](#faq.installation.phpandiis)
11. [When running PHP as CGI with IIS, PWS, OmniHTTPD or Xitami, I get
    the following error: Security Alert! PHP CGI cannot be accessed
    directly..](#faq.installation.forceredirect)
12. [How do I know if my php.ini is being found and read? It seems like
    it isn't as my changes aren't being
    implemented.](#faq.installation.findphpini)
13. [How do I add my PHP directory to the PATH on
    Windows?](#faq.installation.addtopath)
14. [How do I make the php.ini file available to PHP on
    windows?](#faq.installation.phprc)
15. [Is it possible to use Apache content negotiation (MultiViews
    option) with PHP?](#faq.installation.apache.multiviews)
16. [Is PHP limited to process GET and POST request methods
    only?](#faq.installation.requestmethods)

**Why shouldn't I use Apache2 with a threaded MPM in a production environment?**  
PHP is glue. It is the glue used to build cool web applications by
sticking dozens of 3rd-party libraries together and making it all appear
as one coherent entity through an intuitive and easy to learn language
interface. The flexibility and power of PHP relies on the stability and
robustness of the underlying platform. It needs a working OS, a working
web server and working 3rd-party libraries to glue together. When any of
these stop working PHP needs ways to identify the problems and fix them
quickly. When you make the underlying framework more complex by not
having completely separate execution threads, completely separate memory
segments and a strong sandbox for each request to play in, further
weaknesses are introduced into PHP's system.

If you want to use a threaded MPM, look at a FastCGI configuration where
PHP is running in its own memory space.

<!-- -->

**Unix/Windows: Where should my `php.ini` file be located?**  
By default on Unix it should be in `/usr/local/lib` which is
`<install-path>/lib`. Most people will want to change this at
compile-time with the
<a href="/configure/about.html#configure.with-config-file-path" class="link">--with-config-file-path</a>
flag. You would, for example, set it with something like:

``` shell
--with-config-file-path=/etc
```

And then you would copy `php.ini-development` from the distribution to
`/etc/php.ini` and edit it to make any local changes you want.

``` shell
--with-config-file-scan-dir=PATH
```

On Windows the default path for the `php.ini` file is the Windows
directory. If you're using the Apache webserver, `php.ini` is first
searched in the Apaches install directory, e.g.
`c:\program       files\apache group\apache`. This way you can have
different `php.ini` files for different versions of Apache on the same
machine.

See also the chapter about the
<a href="/configuration/file.html" class="link">configuration file</a>.

<!-- -->

**Unix: I installed PHP, but every time I load a document, I get the message 'Document Contains No Data'! What's going on here?**  
This probably means that PHP is having some sort of problem and is
core-dumping. Look in your server error log to see if this is the case,
and then try to reproduce the problem with a small test case. If you
know how to use 'gdb', it is very helpful when you can provide a
backtrace with your bug report to help the developers pinpoint the
problem. If you are using PHP as an Apache module try something like:

-   Stop your httpd processes

-   gdb httpd

-   Stop your httpd processes

-   \> run -X -f /path/to/httpd.conf

-   Then fetch the URL causing the problem with your browser

-   \> run -X -f /path/to/httpd.conf

-   If you are getting a core dump, gdb should inform you of this now

-   type: bt

-   You should include your backtrace in your bug report. This should be
    submitted to
    <a href="https://bugs.php.net/" class="link external">» https://bugs.php.net/</a>

If your script uses the regular expression functions (<span
class="function">preg\_match</span> and friends), you should make sure
that you compiled PHP and Apache with the same regular expression
package. This should happen automatically with PHP and Apache 1.3.x

<!-- -->

**Unix: I installed PHP using RPMS, but Apache isn't processing the PHP pages! What's going on here?**  
Assuming you installed both Apache and PHP from RPM packages, you need
to uncomment or add some or all of the following lines in your
`httpd.conf` file:

``` apache-conf
# Extra Modules
AddModule mod_php.c
AddModule mod_perl.c

# Extra Modules
LoadModule php_module         modules/mod_php.so
LoadModule php5_module        modules/libphp5.so
LoadModule perl_module        modules/libperl.so
```

And add:

``` apache-conf
AddType application/x-httpd-php .php
```

... to the global properties, or to the properties of the VirtualDomain
you want to have PHP support added to.

<!-- -->

**Unix: I patched Apache with the FrontPage extensions patch, and suddenly PHP stopped working. Is PHP incompatible with the Apache FrontPage extensions?**  
No, PHP works fine with the FrontPage extensions. The problem is that
the FrontPage patch modifies several Apache structures, that PHP relies
on. Recompiling PHP (using 'make clean ; make') after the FP patch is
applied would solve the problem.

<!-- -->

**Unix/Windows: I have installed PHP, but when I try to access a PHP script file via my browser, I get a blank screen.**  
Do a 'view source' in the web browser and you will probably find that
you can see the source code of your PHP script. This means that the web
server did not send the script to PHP for interpretation. Something is
wrong with the server configuration - double check the server
configuration against the PHP installation instructions.

<!-- -->

**Unix/Windows: I have installed PHP, but when try to access a PHP script file via my browser, I get a server 500 error.**  
Something went wrong when the server tried to run PHP. To get to see a
sensible error message, from the command line, change to the directory
containing the PHP executable (`php.exe` on Windows) and run **php -i**.
If PHP has any problems running, then a suitable error message will be
displayed which will give you a clue as to what needs to be done next.
If you get a screen full of HTML codes (the output of the <span
class="function">phpinfo</span> function) then PHP is working, and your
problem may be related to your server configuration which you should
double check.

**Some operating systems: I have installed PHP without errors, but when
I try to start Apache I get undefined symbol errors:**

``` shell
[mybox:user /src/php5] root# apachectl configtest
 apachectl: /usr/local/apache/bin/httpd Undefined symbols:
  _compress
  _uncompress
```

This has actually nothing to do with PHP, but with the MySQL client
libraries. Some need **--with-zlib**, others do not. This is also
covered in the MySQL FAQ.

**Windows: I have installed PHP, but when I try to access a PHP script
file via my browser, I get the error:**

    cgi error:
     The specified CGI application misbehaved by not
     returning a complete set of HTTP headers.
     The headers it did return are:

This error message means that PHP failed to output anything at all. To
get to see a sensible error message, from the command line, change to
the directory containing the PHP executable (`php.exe` on Windows) and
run **php -i**. If PHP has any problems running, then a suitable error
message will be displayed which will give you a clue as to what needs to
be done next. If you get a screen full of HTML codes (the output of the
<span class="function">phpinfo</span> function) then PHP is working.

Once PHP is working at the command line, try accessing the script via
the browser again. If it still fails then it could be one of the
following:

-   <span class="simpara"> File permissions on your PHP script,
    `php.exe`, `php5ts.dll`, `php.ini` or any PHP extensions you are
    trying to load are such that the anonymous internet user
    *ISUR\_\<machinename\>* cannot access them. </span>
-   <span class="simpara"> The script file does not exist (or possibly
    isn't where you think it is relative to your web root directory).
    Note that for IIS you can trap this error by ticking the 'check file
    exists' box when setting up the script mappings in the Internet
    Services Manager. If a script file does not exist then the server
    will return a 404 error instead. There is also the additional
    benefit that IIS will do any authentication required for you based
    on the NTLanMan permissions on your script file. </span>

**Windows: I've followed all the instructions, but still can't get PHP and IIS to work together!**  
Make sure any user who needs to run a PHP script has the rights to run
`php.exe`! IIS uses an anonymous user which is added at the time IIS is
installed. This user needs rights to `php.exe`. Also, any authenticated
user will also need rights to execute `php.exe`. And for IIS4 you need
to tell it that PHP is a script engine. Also, you will want to read
<a href="/faq/installation.html#faq.installation.forceredirect" class="link">this faq</a>.

<!-- -->

**When running PHP as CGI with IIS, PWS, OmniHTTPD or Xitami, I get the following error: *Security Alert! PHP CGI cannot be accessed directly.*.**  
You must set the
<a href="/ini/core.html#ini.cgi.force-redirect" class="link">cgi.force_redirect</a>
directive to *0*. It defaults to *1* so be sure the directive isn't
commented out (with a *;*). Like all directives, this is set in
`php.ini`

Because the default is *1*, it's critical that you're 100% sure that the
correct `php.ini` file is being read. Read
<a href="/faq/installation.html#faq.installation.findphpini" class="link">this faq</a>
for details.

<!-- -->

**How do I know if my `php.ini` is being found and read? It seems like it isn't as my changes aren't being implemented.**  
To be sure your `php.ini` is being read by PHP, make a call to <span
class="function">phpinfo</span>. Near the top, there will be a listing
called *Configuration File (php.ini)*. This will tell you where PHP is
looking for `php.ini` and whether or not it's being read. If just a
directory `PATH` exists, then it's not being read, and you should put
your `php.ini` in that directory. If `php.ini` is included within the
`PATH`, it is being read.

If `php.ini` is being read and you're running PHP as a module, then be
sure to restart your web server after making changes to `php.ini`

See also <span class="function">php\_ini\_loaded\_file</span>.

<!-- -->

**How do I add my PHP directory to the `PATH` on Windows?**  
On Windows 7, XP, Vista, 2008, 2012 and up:

-   Go to Control Panel and open the System icon (Start → Control Panel)

-   Go to the Advanced tab

-   Click on the 'Environment Variables' button

-   Look into the 'System Variables' pane

-   Find the Path entry (you may need to scroll to find it)

-   Double click on the Path entry

-   Enter your PHP directory at the end, including ';' before (e.g.
    *;C:\\php*)

-   Press OK

On Windows 98/Me you need to edit the `autoexec.bat` file:

-   Open the Notepad (Start → Run and enter notepad)

-   Open the `C:\autoexec.bat` file

-   Locate the line with PATH=C:\\WINDOWS;C:\\WINDOWS\\COMMAND;..... and
    add: *;C:\\php* to the end of the line

-   Save the file and restart your computer

> **Note**: <span class="simpara"> Be sure to reboot after following the
> steps above to ensure that the `PATH` changes are applied. </span>

The PHP manual used to promote the copying of files into the Windows
system directory, this is because this directory (`C:\Windows`,
`C:\WINNT`, etc.) is by default in the system's `PATH`. Copying files
into the Windows system directory has long since been deprecated and may
cause problems.

<!-- -->

**How do I make the `php.ini` file available to PHP on windows?**  
There are several ways of doing this. If you are using Apache, read
their installation specific instructions
(<a href="/install/windows/legacy/index.html#install.windows.legacy.apache1" class="link">Apache 1</a>,
<a href="/install/windows/legacy/index.html#install.windows.legacy.apache2" class="link">Apache 2</a>),
otherwise you must set the `PHPRC` environment variable:

On Windows:

-   Go to Control Panel and open the System icon (Start → Settings →
    Control Panel → System, or just Start → Control Panel → System)

-   Go to the Advanced tab

-   Click on the 'Environment Variables' button

-   Look into the 'System variables' pane

-   Click on 'New' and enter 'PHPRC' as the variable name and the
    directory where `php.ini` is located as the variable value (e.g.
    *C:\\php*)

-   Press OK and restart your computer

On Windows 98/Me you need to edit the `autoexec.bat` file:

-   Open the Notepad (Start → Run and enter notepad)

-   Open the `C:\autoexec.bat` file

-   Add a new line to the end of the file: *set PHPRC=C:\\php* (replace
    *C:\\php* with the directory where `php.ini` is located). Please
    note that the path cannot contain spaces. For instance, if you have
    installed PHP in `C:\Program Files\PHP`, you would enter
    `C:\PROGRA~1\PHP` instead.

-   Save the file and restart your computer

<!-- -->

**Is it possible to use Apache content negotiation (MultiViews option) with PHP?**  
If links to PHP files include extension, everything works perfect. This
FAQ is only for the case when links to PHP files don't include extension
and you want to use content negotiation to choose PHP files from URL
with no extension. In this case, replace the line *AddType
application/x-httpd-php .php* with:

``` apache-conf
AddHandler php5-script php
AddType text/html php
```

This solution doesn't work for Apache 1 as PHP module doesn't catch
*php-script*.

<!-- -->

**Is PHP limited to process GET and POST request methods only?**  
No, it is possible to handle any request method, e.g. CONNECT. Proper
response status can be sent with <span class="function">header</span>.
If only GET and POST methods should be handled, it can be achieved with
this Apache configuration:

``` apache-conf
<LimitExcept GET POST>
Deny from all
</LimitExcept>
```

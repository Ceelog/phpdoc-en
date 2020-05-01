Sun, iPlanet and Netscape servers on Sun Solaris
------------------------------------------------

This section contains notes and hints specific to Sun Java System Web
Server, Sun ONE Web Server, iPlanet and Netscape server installs of PHP
on Sun Solaris.

From PHP 4.3.3 on you can use PHP scripts with the
<a href="/ref/nsapi.html" class="link">NSAPI module</a> to
<a href="/install/unix/sun.html#install.unix.sun.specialpages" class="link">generate custom directory listings and error pages</a>.
Additional functions for Apache compatibility are also available. For
support in current web servers read the
<a href="/install/unix/sun.html#install.unix.sun.notes" class="link">note about subrequests</a>.

You can find more information about setting up PHP for the Netscape
Enterprise Server (NES) here:
<a href="http://benoit.noss.free.fr/php/install-php4.html" class="link external">» http://benoit.noss.free.fr/php/install-php4.html</a>

To build PHP with Sun JSWS/Sun ONE WS/iPlanet/Netscape web servers,
enter the proper install directory for the
<a href="/configure/about.html#configure.with-nsapi" class="link">--with-nsapi=[DIR]</a>
option. The default directory is usually `/opt/netscape/suitespot/`.
Please also read `/php-xxx-version/sapi/nsapi/nsapi-readme.txt`.

1.  Install the following packages from
    <a href="http://www.sunfreeware.com/" class="link external">»  http://www.sunfreeware.com/</a>
    or another download site:

    -   `autoconf-2.13`
    -   `automake-1.4`
    -   `bison-1_25-sol26-sparc-local`
    -   `flex-2_5_4a-sol26-sparc-local`
    -   `gcc-2_95_2-sol26-sparc-local`
    -   `gzip-1.2.4-sol26-sparc-local`
    -   `m4-1_4-sol26-sparc-local`
    -   `make-3_76_1-sol26-sparc-local`
    -   `mysql-3.23.24-beta` (if you want mysql support)
    -   `perl-5_005_03-sol26-sparc-local`
    -   `tar-1.13` (GNU tar)

2.  <span class="simpara"> Make sure your path includes the proper
    directories *PATH=.:/usr/local/bin:/usr/sbin:/usr/bin:/usr/ccs/bin*
    and make it available to your system **`export PATH`**. </span>

3.  <span class="simpara"> **`gunzip php-x.x.x.tar.gz`** (if you have a
    `.gz` dist, otherwise go to 4). </span>

4.  <span class="simpara"> **`tar xvf php-x.x.x.tar`** </span>

5.  <span class="simpara"> Change to your extracted PHP directory:
    **`cd ../php-x.x.x`** </span>

6.  For the following step, make sure `/opt/netscape/suitespot/` is
    where your netscape server is installed. Otherwise, change to the
    correct path and run:

    ``` shell
    ./configure --with-mysql=/usr/local/mysql \
    --with-nsapi=/opt/netscape/suitespot/ \
    --enable-libgcc
    ```

7.  <span class="simpara"> Run **make** followed by **make install**.
    </span>

After performing the base install and reading the appropriate readme
file, you may need to perform some additional configuration steps.

##### Configuration Instructions for Sun/iPlanet/Netscape

Firstly you may need to add some paths to the `LD_LIBRARY_PATH`
environment for the server to find all the shared libs. This can best
done in the start script for your web server. The start script is often
located in: `/path/to/server/https-servername/start`. You may also need
to edit the configuration files that are located in:
`/path/to/server/https-servername/config/`.

1.  Add the following line to `mime.types` (you can do that by the
    administration server):

        type=magnus-internal/x-httpd-php exts=php

2.  Edit `magnus.conf` (for servers \>= 6) or `obj.conf` (for servers
    \< 6) and add the following, shlib will vary depending on your
    system, it will be something like
    `/opt/netscape/suitespot/bin/libphp4.so`. You should place the
    following lines after *mime types init*.

        Init fn="load-modules" funcs="php4_init,php4_execute,php4_auth_trans" shlib="/opt/netscape/suitespot/bin/libphp4.so"
        Init fn="php4_init" LateInit="yes" errorString="Failed to initialize PHP!" [php_ini="/path/to/php.ini"]

    (PHP \>= 4.3.3) The *php\_ini* parameter is optional but with it you
    can place your `php.ini` in your web server config directory.

3.  Configure the default object in `obj.conf` (for virtual server
    classes \[version 6.0+\] in their `vserver.obj.conf`):

        <Object name="default">
        .
        .
        .
        .#NOTE this next line should happen after all 'ObjectType' and before all 'AddLog' lines
        Service fn="php4_execute" type="magnus-internal/x-httpd-php" [inikey=value inikey=value ...]
        .
        .
        </Object>

    (PHP \>= 4.3.3) As additional parameters you can add some special
    `php.ini`-values, for example you can set a
    *docroot="/path/to/docroot"* specific to the context *php4\_execute*
    is called. For boolean ini-keys please use 0/1 as value, not
    *"On","Off",...* (this will not work correctly), e.g.
    *zlib.output\_compression=1* instead of
    *zlib.output\_compression="On"*

4.  This is only needed if you want to configure a directory that only
    consists of PHP scripts (same like a `cgi-bin` directory):

        <Object name="x-httpd-php">
        ObjectType fn="force-type" type="magnus-internal/x-httpd-php"
        Service fn=php4_execute [inikey=value inikey=value ...]
        </Object>

    After that you can configure a directory in the Administration
    server and assign it the style *x-httpd-php*. All files in it will
    get executed as PHP. This is nice to hide PHP usage by renaming
    files to `.html`.

5.  Setup of authentication: PHP authentication cannot be used with any
    other authentication. ALL AUTHENTICATION IS PASSED TO YOUR PHP
    SCRIPT. To configure PHP Authentication for the entire server, add
    the following line to your default object:

        <Object name="default">
        AuthTrans fn=php4_auth_trans
        .
        .
        .
        </Object>

6.  To use PHP Authentication on a single directory, add the following:

        <Object ppath="d:\path\to\authenticated\dir\*">
        AuthTrans fn=php4_auth_trans
        </Object>

> **Note**:
>
> The stacksize that PHP uses depends on the configuration of the web
> server. If you get crashes with very large PHP scripts, it is
> recommended to raise it with the Admin Server (in the section "MAGNUS
> EDITOR").

### CGI environment and recommended modifications in `php.ini`

Important when writing PHP scripts is the fact that Sun JSWS/Sun ONE
WS/iPlanet/Netscape is a multithreaded web server. Because of that all
requests are running in the same process space (the space of the web
server itself) and this space has only one environment. If you want to
get CGI variables like *PATH\_INFO*, *HTTP\_HOST* etc. it is not the
correct way to try this in the old PHP way with <span
class="function">getenv</span> or a similar way (register globals to
environment, `$_ENV`). You would only get the environment of the running
web server without any valid CGI variables!

> **Note**:
>
> Why are there (invalid) CGI variables in the environment?
>
> Answer: This is because you started the web server process from the
> admin server which runs the startup script of the web server, you
> wanted to start, as a CGI script (a CGI script inside of the admin
> server!). This is why the environment of the started web server has
> some CGI environment variables in it. You can test this by starting
> the web server not from the administration server. Use the command
> line as root user and start it manually - you will see there are no
> CGI-like environment variables.

Simply change your scripts to get CGI variables in the correct way for
PHP 4.x by using the superglobal `$_SERVER`. If you have older scripts
which use `$HTTP_HOST`, etc., you should turn on *register\_globals* in
`php.ini` and change the variable order too (important: remove *"E"*
from it, because you do not need the environment here):

    variables_order = "GPCS"
    register_globals = On

### Special use for error pages or self-made directory listings (PHP \>= 4.3.3)

You can use PHP to generate the error pages for *"404 Not Found"* or
similar. Add the following line to the object in `obj.conf` for every
error page you want to overwrite:

    Error fn="php4_execute" code=XXX script="/path/to/script.php" [inikey=value inikey=value...]

where *XXX* is the HTTP error code. Please delete any other *Error*
directives which could interfere with yours. If you want to place a page
for all errors that could exist, leave the *code* parameter out. Your
script can get the HTTP status code with `$_SERVER['ERROR_TYPE']`.

Another possibility is to generate self-made directory listings. Just
create a PHP script which displays a directory listing and replace the
corresponding default *Service* line for
*type="magnus-internal/directory"* in `obj.conf` with the following:

    Service fn="php4_execute" type="magnus-internal/directory" script="/path/to/script.php" [inikey=value inikey=value...]

For both error and directory listing pages the original URI and
translated URI are in the variables `$_SERVER['PATH_INFO']` and
`$_SERVER['PATH_TRANSLATED']`.

### Note about <span class="function">nsapi\_virtual</span> and subrequests (PHP \>= 4.3.3)

The NSAPI module now supports the <span
class="function">nsapi\_virtual</span> function (alias: <span
class="function">virtual</span>) to make subrequests on the web server
and insert the result in the web page. This function uses some
undocumented features from the NSAPI library. On Unix the module
automatically looks for the needed functions and uses them if available.
If not, <span class="function">nsapi\_virtual</span> is disabled.

> **Note**:
>
> But be warned: Support for <span
> class="function">nsapi\_virtual</span> is EXPERIMENTAL!!!

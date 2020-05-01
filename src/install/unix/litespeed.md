LiteSpeed Web Server/OpenLiteSpeed Web Server on Unix systems
-------------------------------------------------------------

LiteSpeed PHP is an optimized compilation of PHP built to work with
LiteSpeed products through the LiteSpeed SAPI. LSPHP runs as its own
process and has its own standalone binary, which can be used as a simple
command line binary to execute PHP scripts from the command line.

The LSAPI is a highly optimized API that allows communication between
LiteSpeed and third party web engines. Its protocol is similar to FCGI,
but is more efficient.

This documentation will cover installing and configuring PHP with LSAPI
for a LiteSpeed Web Server and OpenLiteSpeed Web Server.

This guide will assume that either LSWS or OLS is installed with their
default paths and flags. The default installation directory for both web
servers is /usr/local/lsws and both can be run from the bin
subdirectory.

Please note that throughout this documentation, version numbers have
been replaced with an *x* to ensure this documentation stays correct in
the future, please replace these, as necessary, with the corresponding
version numbers.

1.  To obtain and install either LiteSpeed Web Server or OpenLiteSpeed
    Web Server, visit the LiteSpeed Web Server wiki
    <a href="https://www.litespeedtech.com/support/wiki/doku.php/litespeed_wiki:installation" class="link external">» install page</a>
    or OpenLiteSpeed wiki
    <a href="http://open.litespeedtech.com/mediawiki/index.php/Help:Install" class="link external">» install page</a>.

2.  Obtain and unpack the php source:

        mkdir /home/php
        cd /home/php
        wget http://us1.php.net/get/php-x.x.x.tar.gz/from/this/mirror
        tar -zxvf php-x.x.x.tar.gz
        cd php-x.x.x

3.  Configure and build PHP. This is where PHP can be customized with
    various options, such as which extensions will be enabled. Run
    ./configure --help for a list of available options. In the example,
    we'll use the default recommended configuration options for
    LiteSpeed Web Server:

        ./configure ... '--with-litespeed'
        make
        sudo make install

4.  Checking The LSPHP Installation

    One of the simplest ways to check whether the installation of PHP
    was successful is to run the following code:

        cd /usr/local/lsws/fcgi-bin/
        ./lsphp5 -v

    This should return information about the new PHP build:

        PHP 5.6.17 (litespeed) (built: Mar 22 2016 11:34:19)
        Copyright (c) 1997-2014 The PHP Group
        Zend Engine v2.6.0, Copyright (c) 1998-2015 Zend Technologies

    Notice the *litespeed* in parenthesis. This means that the PHP
    binary has been built with LSAPI support.

Following the steps above, LiteSpeed / OpenLiteSpeed Web Server should
now be running with support for PHP as an SAPI extension. There are many
more configuration options available for LSWS / OLS and PHP. For more
information, check out the LiteSpeed wiki about
<a href="https://www.litespeedtech.com/support/wiki/doku.php/litespeed_wiki:php" class="link external">» PHP</a>.

Using LSPHP from the command line:

LSPHP(LSAPI + PHP) command line mode is used to process PHP scripts
running on a remote server that does not necessarily have a web server
running. It is used to process PHP scripts residing on a local web
server (separate). This setup is suitable for service scalability as PHP
processing is offloaded to a remote server.

Start lsphp from the command line on a remote server: LSPHP is an
executable and can be started manually and bound to IPv4, IPv6, or Unix
domain socket addresses with the command line option -b socket\_address

Examples:

Have LSPHP bind to port 3000 on all IPv4 and IPv6 addresses:

    /path/to/lsphp -b [::]:3000

Have LSPHP bind to port 3000 on all IPv4 addresses:

    /path/to/lsphp -b *:3000

Have LSPHP bind to address 192.168.0.2:3000:

    /path/to/lsphp -b 192.168.0.2:3000

Have LSPHP accept requests on Unix domain socket
*/tmp/lsphp\_manual.sock*:

    /path/to/lsphp -b /tmp/lsphp_manual.sock

Environment variables can be added before the LSPHP executable:

    PHP_LSAPI_MAX_REQUESTS=500 PHP_LSAPI_CHILDREN=35 /path/to/lsphp -b IP_address:port

Currently LiteSpeed PHP can be used with LiteSpeed Web Server,
OpenLiteSpeed Web Server, and Apache mod\_lsapi. For steps on
server-side configuration, visit the wiki pages for
<a href="https://www.litespeedtech.com/support/wiki/doku.php/litespeed_wiki:php:configuring-lsws-for-php" class="link external">» LiteSpeed Web Server</a>
and
<a href="http://open.litespeedtech.com/mediawiki/index.php/Help:Default_PHP_Settings" class="link external">» OpenLiteSpeed</a>.

LSPHP can be installed in several other ways as well.

CentOS: On CentOS, LSPHP can be installed from the LiteSpeed Repository
or the Remi Repository using
<a href="https://www.litespeedtech.com/support/wiki/doku.php/litespeed_wiki:php:rpm" class="link external">» RPM</a>.

Debian: On Debian, LSPHP can be installed from the LiteSpeed Repository
using
<a href="https://www.litespeedtech.com/support/wiki/doku.php/litespeed_wiki:php:apt" class="link external">» apt</a>.

cPanel: Visit the respective
<a href="https://www.litespeedtech.com/support/wiki/doku.php/litespeed_wiki:cpanel:easyapache4-config" class="link external">» wiki page</a>
about how to install LSPHP with cPanel and LSWS/OLS using EasyApache 4.

Plesk: Plesk can be used with LSPHP on CentOS, CloudLinux, Debian, and
Ubuntu, for more details on this, visit the respective
<a href="https://www.litespeedtech.com/support/wiki/doku.php/litespeed_wiki:plesk:php_guide" class="link external">» wiki page</a>

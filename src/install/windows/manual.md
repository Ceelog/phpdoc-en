Manual PHP Installation on Windows
----------------------------------

### Choose Web Server

#### IIS

IIS is built in to Windows. On Windows Server, the IIS role can be added
via the Server Manager. The CGI Role Feature needs to be included. On
Windows Desktop, IIS has to be added via the Control Panel's Add/Remove
Programs. The Microsoft documentation has
<a href="https://docs.microsoft.com/en-us/previous-versions/ms181052(v=vs.80)" class="link external">» detailed instructions</a>.
For desktop web apps and web-development, IIS/Express or PHP Desktop can
also be used.

**Example \#1 Command line to configure IIS and PHP**


    @echo off

    REM download .ZIP file of PHP build from http://windows.php.net/downloads/

    REM path to directory you decompressed PHP .ZIP file into (no trailing \)
    set phppath=c:\php


    REM Clear current PHP handlers
    %windir%\system32\inetsrv\appcmd clear config /section:system.webServer/fastCGI
    REM The following command will generate an error message if PHP is not installed. This can be ignored.
    %windir%\system32\inetsrv\appcmd set config /section:system.webServer/handlers /-[name='PHP_via_FastCGI']

    REM Set up the PHP handler
    %windir%\system32\inetsrv\appcmd set config /section:system.webServer/fastCGI /+[fullPath='%phppath%\php-cgi.exe']
    %windir%\system32\inetsrv\appcmd set config /section:system.webServer/handlers /+[name='PHP_via_FastCGI',path='*.php',verb='*',modules='FastCgiModule',scriptProcessor='%phppath%\php-cgi.exe',resourceType='Unspecified']
    %windir%\system32\inetsrv\appcmd set config /section:system.webServer/handlers /accessPolicy:Read,Script

    REM Configure FastCGI Variables
    %windir%\system32\inetsrv\appcmd set config -section:system.webServer/fastCgi /[fullPath='%phppath%\php-cgi.exe'].instanceMaxRequests:10000
    %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi /+"[fullPath='%phppath%\php-cgi.exe'].environmentVariables.[name='PHP_FCGI_MAX_REQUESTS',value='10000']"
    %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi /+"[fullPath='%phppath%\php-cgi.exe'].environmentVariables.[name='PHPRC',value='%phppath%\php.ini']"

See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.iis7" class="link">old IIS installation instructions</a>.

#### Apache

There are several builds of Apache2 for Windows. The Apache builds of
ApacheLounge are recommended, but other options include XAMPP,
WampServer and BitNami, which provide automatic installer tools. PHP can
be used on Apache through mod\_php or mod\_fastcgi. mod\_php requires a
TS build of Apache built with same version of Visual C and same CPU (x86
or x64). See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.apache2" class="link">old Apache installation instructions</a>.

### Choose Build

Windows builds can be downloaded from
<a href="http://windows.php.net/download/" class="link external">» http://windows.php.net/download/</a>.
All builds are optimized (PGO), and QA and GA releases are thoroughly
tested.

There are 4 types of PHP builds:

-   Thread-Safe(TS) - for single process web servers, like Apache with
    mod\_php

-   Non-Thread-Safe(NTS) - for IIS and other FastCGI web servers (Apache
    with mod\_fastcgi) and recommended for command-line scripts

-   x86 - production use of PHP 5.5 and up.

-   x64 - production use of PHP 7 (unless its a 32-bit only version of
    Windows). PHP 5.5 and 5.6 x64 builds are experimental.

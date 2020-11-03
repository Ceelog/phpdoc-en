Installation on old Windows systems
-----------------------------------

This section applies to Windows 98/Me and Windows NT/2000/XP/2003. PHP
will not work on 16 bit platforms such as Windows 3.1 and sometimes we
refer to the supported Windows platforms as Win32.

> **Note**:
>
> Windows XP/2003 are no longer supported as of PHP 5.5.0.

> **Note**:
>
> Windows 98/Me/NT4/2000 are no longer supported as of PHP 5.3.0.

> **Note**:
>
> Windows 95 is no longer supported as of PHP 4.3.0.

If you have a development environment such as Microsoft Visual Studio,
you can also build PHP from the original source code.

Once you have PHP installed on your Windows system, you may also want to
<a href="/install/windows/legacy/index.html#install.windows.legacy.extensions" class="link">load various extensions</a>
for added functionality.

### Manual Installation Steps

This section contains instructions for manually installing and
configuring PHP on Microsoft Windows.

#### Selecting and downloading the PHP distribution package

Download the PHP zip binary distribution from
<a href="https://windows.php.net/download/" class="link external">» PHP for Windows: Binaries and Sources</a>.
There are several different versions of the zip package - to choose the
right version for you, follow the detailed guide on the
<a href="https://windows.php.net/download/" class="link external">» download page</a>.

#### The PHP package structure and content

Unpack the content of the zip archive into a directory of your choice,
for example C:\\PHP\\. The directory and file structure extracted from
the zip will look as below:

**Example \#1 PHP 5 package structure**


    c:\php
       |
       +--dev
       |  |
       |  |-php5ts.lib                 -- php5.lib in non thread safe version
       |
       +--ext                          -- extension DLLs for PHP
       |  |
       |  |-php_bz2.dll
       |  |
       |  |-php_cpdf.dll
       |  |
       |  |-...
       |
       +--extras                       -- empty 
       |
       +--pear                         -- initial copy of PEAR
       |
       |
       |-go-pear.bat                   -- PEAR setup script
       |
       |-...
       |
       |-php-cgi.exe                   -- CGI executable
       |
       |-php-win.exe                   -- executes scripts without an opened command prompt
       |
       |-php.exe                       -- Command line PHP executable (CLI)
       |
       |-...
       |
       |-php.ini-development           -- default php.ini settings
       |
       |-php.ini-production            -- recommended php.ini settings
       |
       |-php5apache2_2.dll             -- does not exist in non thread safe version
       |
       |-php5apache2_2_filter.dll      -- does not exist in non thread safe version
       |
       |-...
       |
       |-php5ts.dll                    -- core PHP DLL ( php5.dll in non thread safe version)
       | 
       |-...

Below is the list of the modules and executables included in the PHP zip
distribution:

-   `go-pear.bat` - the PEAR setup script. Refer to
    <a href="https://pear.php.net/manual/en/installation.php" class="link external">» Installation (PEAR)</a>
    for more details.

-   `php-cgi.exe` - CGI executable that can be used when running PHP on
    IIS via CGI or FastCGI.

-   `php-win.exe` - the PHP executable for executing PHP scripts without
    using a command line window (for example PHP applications that use
    Windows GUI).

-   `php.exe` - the PHP executable for executing PHP scripts within a
    command line interface (CLI).

-   `php5apache2_2.dll` - Apache 2.2.X module.

-   `php5apache2_2_filter.dll` - Apache 2.2.X filter.

#### Changing the `php.ini` file

After the php package content has been extracted, copy the
`php.ini-production` into `php.ini` in the same folder. If necessary, it
is also possible to place the `php.ini` into any other location of your
choice but that will require additional configuration steps as described
in
<a href="/configuration/file.html" class="link">PHP Configuration</a>.

The `php.ini` file tells PHP how to configure itself, and how to work
with the environment that it runs in. Here are a number of settings for
the `php.ini` file that help PHP work better with Windows. Some of these
are optional. There are many other directives that may be relevant to
your environment - refer to the
<a href="/ini/list.html" class="link">list of php.ini directives</a> for
more information.

Required directives:

-   `extension_dir` = *\<path to extension directory\>* - The
    `extension_dir` needs to point to the directory where PHP extensions
    files are stored. The path can be absolute (i.e. "C:\\PHP\\ext") or
    relative (i.e. ".\\ext"). Extensions that are listed lower in the
    `php.ini` file need to be located in the `extension_dir`.

-   `extension` = *xxxxx.dll* - For each extension you wish to enable,
    you need a corresponding "extension=" directive that tells PHP which
    extensions in the `extension_dir` to load at startup time.

-   `log_errors` = *On* - PHP has an error logging facility that can be
    used to send errors to a file, or to a service (i.e. syslog) and
    works in conjunction with the `error_log` directive below. When
    running under IIS, the `log_errors` should be enabled, with a valid
    `error_log`.

-   `error_log` = *\<path to the error log file\>* - The error\_log
    needs to specify the absolute, or relative path to the file where
    PHP errors should be logged. This file needs to be writable for the
    web server. The most common places for this file are in various TEMP
    directories, for example "C:\\inetpub\\temp\\php-errors.log".

-   `cgi.force_redirect` = *0* - This directive is required for running
    under IIS. It is a directory security facility required by many
    other web servers. However, enabling it under IIS will cause the PHP
    engine to fail on Windows.

-   `cgi.fix_pathinfo` = *1* - This lets PHP access real path info
    following the CGI Spec. The IIS FastCGI implementation needs this
    set.

-   `fastcgi.impersonate` = *1* - FastCGI under IIS supports the ability
    to impersonate security tokens of the calling client. This allows
    IIS to define the security context that the request runs under.

-   `fastcgi.logging` = *0* - FastCGI logging should be disabled on IIS.
    If it is left enabled, then any messages of any class are treated by
    FastCGI as error conditions which will cause IIS to generate an HTTP
    500 exception.

Optional directives

-   `max_execution_time` = *\#\#* - This directive tells PHP the maximum
    amount of time that it can spend executing any given script. The
    default for this is 30 seconds. Increase the value of this directive
    if PHP application take long time to execute.

-   `memory_limit` = *\#\#\#M* - The amount of memory available for the
    PHP process, in Megabytes. The default is 128, which is fine for
    most PHP applications. Some of the more complex ones might need
    more.

-   `display_errors` = *Off* - This directive tells PHP whether to
    include any error messages in the stream that it returns to the Web
    server. If this is set to "On", then PHP will send whichever classes
    of errors that you define with the `error_reporting` directive back
    to web server as part of the error stream. For security reasons it
    is recommended to set it to "Off" on production servers in order not
    to reveal any security sensitive information that is often included
    in the error messages.

-   `open_basedir` = *\<paths to directories, separated by semicolon\>*,
    e.g. openbasedir="C:\\inetpub\\wwwroot;C:\\inetpub\\temp". This
    directive specified the directory paths where PHP is allowed to
    perform file system operations. Any file operation outside of the
    specified paths will result in an error. This directive is
    especially useful for locking down the PHP installation in shared
    hosting environments to prevent PHP scripts from accessing any files
    outside of the web site's root directory.

-   `upload_max_filesize` = *\#\#\#M* and `post_max_size` = *\#\#\#M* -
    The maximum allowed size of an uploaded file and post data
    respectively. The values of these directives should be increased if
    PHP applications need to perform large uploads, such as for example
    photos or video files.

PHP is now setup on your system. The next step is to choose a web
server, and enable it to run PHP. Choose a web server from the table of
contents.

In addition to running PHP via a web server, PHP can run from the
command line just like a *.BAT* script. See

### Microsoft IIS

This section contains PHP installation instructions specific to
Microsoft Internet Information Services (IIS).

-   <span class="simpara">
    <a href="/install/windows/legacy/index.html#install.windows.legacy.iis6" class="link">Manually installing PHP on Microsoft IIS 5.1 and IIS 6.0</a>
    </span>
-   <span class="simpara">
    <a href="/install/windows/legacy/index.html#install.windows.legacy.iis7" class="link">Manually installing PHP on Microsoft IIS 7.0 and later</a>
    </span>

### Microsoft IIS 5.1 and IIS 6.0

This section contains instructions for manually setting up Internet
Information Services (IIS) 5.1 and IIS 6.0 to work with PHP on Microsoft
Windows XP and Windows Server 2003. For instructions on setting up IIS
7.0 and later versions on Windows Vista, Windows Server 2008, Windows 7
and Windows Server 2008 R2 refer to
<a href="/install/windows/legacy/index.html#install.windows.legacy.iis7" class="link">Microsoft IIS 7.0 and later</a>.

#### Configuring IIS to process PHP requests

Download and install PHP in accordance to the instructions described in
<a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">manual installation steps</a>

> **Note**:
>
> Non-thread-safe build of PHP is recommended when using IIS. The
> non-thread-safe builds are available at
> <a href="https://windows.php.net/download/" class="link external">» PHP for Windows: Binaries and Sources Releases.</a>

Configure the CGI- and FastCGI-specific settings in `php.ini` file as
shown below:

**Example \#2 CGI and FastCGI settings in `php.ini`**

``` ini
fastcgi.impersonate = 1
fastcgi.logging = 0
cgi.fix_pathinfo=1
cgi.force_redirect = 0
```

Download and install the
<a href="http://www.iis.net/extensions/fastcgi" class="link external">» Microsoft FastCGI Extension for IIS 5.1 and 6.0</a>.
The extension is available for 32-bit and 64-bit platforms - select the
right download package for your platform.

Configure the FastCGI extension to handle PHP-specific requests by
running the command shown below. Replace the value of the "-path"
parameter with the absolute file path to the `php-cgi.exe` file.

**Example \#3 Configuring FastCGI extension to handle PHP requests**

    cscript %windir%\system32\inetsrv\fcgiconfig.js -add -section:"PHP" ^
    -extension:php -path:"C:\PHP\php-cgi.exe"

This command will create an IIS script mapping for \*.php file
extension, which will result in all URLs that end with .php being
handled by FastCGI extension. Also, it will configure FastCGI extension
to use the executable `php-cgi.exe` to process the PHP requests.

> **Note**:
>
> At this point the required installation and configuration steps are
> completed. The remaining instructions below are optional but highly
> recommended for achieving optimal functionality and performance of PHP
> on IIS.

#### Impersonation and file system access

It is recommended to enable FastCGI impersonation in PHP when using IIS.
This is controlled by the `fastcgi.impersonate` directive in `php.ini`
file. When impersonation is enabled, PHP will perform all the file
system operations on behalf of the user account that has been determined
by IIS authentication. This ensures that even if the same PHP process is
shared across different IIS web sites, the PHP scripts in those web
sites will not be able to access each others' files as long as different
user accounts are used for IIS authentication on each web site.

For example IIS 5.1 and IIS 6.0, in its default configuration, has
anonymous authentication enabled with built-in user account
IUSR\_\<MACHINE\_NAME\> used as a default identity. This means that in
order for IIS to execute PHP scripts, it is necessary to grant
IUSR\_\<MACHINE\_NAME\> account read permission on those scripts. If PHP
applications need to perform write operations on certain files or write
files into some folders then IUSR\_\<MACHINE\_NAME\> account should have
write permission to those.

To determine which user account is used by IIS anonymous authentication,
follow these steps:

1.  In the Windows Start Menu choose "Run:", type "inetmgr" and click
    "Ok";

2.  Expand the list of web sites under the "Web Sites" node in the tree
    view, right-click on a web site that is being used and select
    "Properties";

3.  Click the "Directory Security" tab;

4.  Take note of a "User name:" field in the "Authentication Methods"
    dialog

<img src="images/b4cf2bb34e3c20eebcf8f9e8e7949efd-iis6anonauth.png" width="654" height="461" alt="Anonymous authenication for IIS 5.1 and IIS 6.0" />

To modify the permissions settings on files and folders, use the Windows
Explorer user interface or `icacls` command.

**Example \#4 Configuring file access permissions**

    icacls C:\inetpub\wwwroot\upload /grant IUSR:(OI)(CI)(M)

#### Set `index.php` as a default document in IIS

The IIS default documents are used for HTTP requests that do not specify
a document name. With PHP applications, `index.php` usually acts as a
default document. To add `index.php` to the list of IIS default
documents, follow these steps:

1.  In the Windows Start Menu choose "Run:", type "inetmgr" and click
    "Ok";

2.  Right-click on the "Web Sites" node in the tree view and select
    "Properties";

3.  Click the "Documents" tab;

4.  Click the "Add..." button and enter "index.php" for the "Default
    content page:".

<img src="images/b4cf2bb34e3c20eebcf8f9e8e7949efd-iis6defaultdoc.png" width="659" height="465" alt="Setting index.php as default document for IIS" />

#### FastCGI and PHP Recycling configuration

Configure IIS FastCGI extension settings for recycling of PHP processes
by using the commands shown below. The FastCGI setting
`instanceMaxRequests` controls how many requests will be processed by a
single `php-cgi.exe` process before FastCGI extension shuts it down. The
PHP environment variable `PHP_FCGI_MAX_REQUESTS` controls how many
requests a single `php-cgi.exe` process will handle before it recycles
itself. Make sure that the value specified for FastCGI
`InstanceMaxRequests` setting is less than or equal to the value
specified for `PHP_FCGI_MAX_REQUESTS`.

**Example \#5 Configuring FastCGI and PHP recycling**

    cscript %windir%\system32\inetsrv\fcgiconfig.js -set -section:"PHP" ^
    -InstanceMaxRequests:10000

    cscript %windir%\system32\inetsrv\fcgiconfig.js -set -section:"PHP" ^
    -EnvironmentVars:PHP_FCGI_MAX_REQUESTS:10000

#### Configuring FastCGI timeout settings

Increase the timeout settings for FastCGI extension if there are
applications that have long running PHP scripts. The two settings that
control timeouts are `ActivityTimeout` and `RequestTimeout`. Refer to
<a href="http://learn.iis.net/page.aspx/248/configuring-fastcgi-extension-for-iis-60/" class="link external">» Configuring FastCGI Extension for IIS 6.0</a>
for more information about those settings.

**Example \#6 Configuring FastCGI timeout settings**

    cscript %windir%\system32\inetsrv\fcgiconfig.js -set -section:"PHP" ^
    -ActivityTimeout:90

    cscript %windir%\system32\inetsrv\fcgiconfig.js -set -section:"PHP" ^
    -RequestTimeout:90

#### Changing the Location of `php.ini` file

PHP searches for `php.ini` file in
<a href="/configuration/file.html" class="link">several locations</a>
and it is possible to change the default locations of `php.ini` file by
using `PHPRC` environment variable. To instruct PHP to load the
configuration file from a custom location run the command shown below.
The absolute path to the directory with `php.ini` file should be
specified as a value of `PHPRC` environment variable.

**Example \#7 Changing the location of `php.ini` file**

    cscript %windir%\system32\inetsrv\fcgiconfig.js -set -section:"PHP" ^
    -EnvironmentVars:PHPRC:"C:\Some\Directory\"

### Microsoft IIS 7.0 and later

This section contains instructions for manually setting up Internet
Information Services (IIS) 7.0 and later to work with PHP on Microsoft
Windows Vista SP1, Windows 7, Windows Server 2008 and Windows Server
2008 R2. For instructions on setting up IIS 5.1 and IIS 6.0 on Windows
XP and Windows Server 2003 refer to
<a href="/install/windows/legacy/index.html#install.windows.legacy.iis6" class="link">Microsoft IIS 5.1 and IIS 6.0</a>.

#### Enabling FastCGI support in IIS

FastCGI module is disabled in default installation of IIS. The steps to
enable it differ based on the version of Windows being used.

To enable FastCGI support on Windows Vista SP1 and Windows 7:

1.  In the Windows Start Menu choose "Run:", type "optionalfeatures.exe"
    and click "Ok";

2.  In the "Windows Features" dialog expand "Internet Information
    Services", "World Wide Web Services", "Application Development
    Features" and then enable the "CGI" checkbox;

3.  Click OK and wait until the installation is complete.

<img src="images/b4cf2bb34e3c20eebcf8f9e8e7949efd-iis7vistacgi.png" width="429" height="375" alt="Enabling FastCGI support for IIS7 on Windows Vista SP1 and Windows 7" />

To enable FastCGI support on Windows Server 2008 and Windows Server 2008
R2:

1.  In the Windows Start Menu choose "Run:", type "CompMgmtLauncher" and
    click "Ok";

2.  If the "Web Server (IIS)" role is not present under the "Roles"
    node, then add it by clicking "Add Roles";

3.  If the "Web Server (IIS)" role is present, then click "Add Role
    Services" and then enable the "CGI" checkbox under "Application
    Development" group;

4.  Click "Next" and then "Install" and wait for the installation to
    complete.

<img src="images/b4cf2bb34e3c20eebcf8f9e8e7949efd-iis7w2k8cgi.png" width="546" height="411" alt="Enabling FastCGI support on Windows Server 2008 and Windows Server 2008 R2" />

#### Configuring IIS to process PHP requests

Download and install PHP in accordance to the instructions described in
<a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">manual installation steps</a>

> **Note**:
>
> Non-thread-safe build of PHP is recommended when using IIS. The
> non-thread-safe builds are available at
> <a href="https://windows.php.net/download/" class="link external">» PHP for Windows: Binaries and Sources Releases.</a>

Configure the CGI- and FastCGI-specific settings in `php.ini` file as
shown below:

**Example \#8 CGI and FastCGI settings in `php.ini`**

``` ini
fastcgi.impersonate = 1
fastcgi.logging = 0
cgi.fix_pathinfo=1
cgi.force_redirect = 0
```

Configure IIS handler mapping for PHP by using either IIS Manager user
interface or a command line tool.

##### Using IIS Manager user interface to create a handler mapping for PHP

Follow these steps to create an IIS handler mapping for PHP in IIS
Manager user interface:

1.  In the Windows Start Menu choose "Run:", type "inetmgr" and click
    "Ok";

2.  In the IIS Manager user interface select the server node in the
    "Connections" tree view;

3.  In the "Features View" page open the "Handler Mappings" feature;

    <img src="images/b4cf2bb34e3c20eebcf8f9e8e7949efd-iis7handlericon.png" width="708" height="515" alt="Create IIS handler mapping for PHP : Locate Handler Mappings" />

4.  In the "Actions" pane click "Add Module Mapping...";

5.  In the "Add Module Mapping" dialog enter the following:

    -   <span class="simpara">Request path: \*.php</span>
    -   <span class="simpara">Module: FastCgiModule</span>
    -   <span class="simpara">Executable: C:\\\[Path to PHP
        installation\]\\php-cgi.exe</span>
    -   <span class="simpara">Name: PHP\_via\_FastCGI</span>

6.  Click "Request Restrictions" button and then configure the mapping
    to invoke handler only if request is mapped to a file or a folder;

7.  Click OK on all the dialogs to save the configuration.

<img src="images/b4cf2bb34e3c20eebcf8f9e8e7949efd-iis7handlermap.png" width="705" height="512" alt="Create IIS handler mapping for PHP : Add Handler Mapping" />

##### Using command line tool to create a handler mapping for PHP

Use the command shown below to create an IIS FastCGI process pool which
will use `php-cgi.exe` executable for processing PHP requests. Replace
the value of the `fullPath` parameter with the absolute file path to the
`php-cgi.exe` file.

**Example \#9 Creating IIS FastCGI process pool**

    %windir%\system32\inetsrv\appcmd set config /section:system.webServer/fastCGI ^
    /+[fullPath='c:\PHP\php-cgi.exe']

Configure IIS to handle PHP specific requests by running the command
shown below. Replace the value of the `scriptProcessor` parameter with
the absolute file path to the `php-cgi.exe` file.

**Example \#10 Creating handler mapping for PHP requests**

    %windir%\system32\inetsrv\appcmd set config /section:system.webServer/handlers ^
    /+[name='PHP_via_FastCGI', path='*.php',verb='*',modules='FastCgiModule',^
    scriptProcessor='c:\PHP\php-cgi.exe',resourceType='Either']

This command creates an IIS handler mapping for \*.php file extension,
which will result in all URLs that end with .php being handled by
FastCGI module.

> **Note**:
>
> At this point the required installation and configuration steps are
> completed. The remaining instructions below are optional but highly
> recommended for achieving optimal functionality and performance of PHP
> on IIS.

#### Impersonation and file system access

It is recommended to enable FastCGI impersonation in PHP when using IIS.
This is controlled by the `fastcgi.impersonate` directive in `php.ini`
file. When impersonation is enabled, PHP will perform all the file
system operations on behalf of the user account that has been determined
by IIS authentication. This ensures that even if the same PHP process is
shared across different IIS web sites, the PHP scripts in those web
sites will not be able to access each other's files as long as different
user accounts are used for IIS authentication on each web site.

For example IIS 7, in its default configuration, has anonymous
authentication enabled with built-in user account IUSR used as a default
identity. This means that in order for IIS to execute PHP scripts, it is
necessary to grant IUSR account read permission on those scripts. If PHP
applications need to perform write operations on certain files or write
files into some folders then IUSR account should have write permission
to those.

To determine what user account is used as an anonymous identity in IIS 7
use the following command. Replace the "Default Web Site" with the name
of IIS web site that you use. In the output XML configuration element
look for the `userName` attribute.

**Example \#11 Determining the account used as IIS anonymous identity**

    %windir%\system32\inetsrv\appcmd.exe list config "Default Web Site" ^
    /section:anonymousAuthentication

    <system.webServer>
      <security>
        <authentication>
          <anonymousAuthentication enabled="true" userName="IUSR" />
        </authentication>
       </security>
    </system.webServer>

> **Note**:
>
> If `userName` attribute is not present in the
> `anonymousAuthentication` element, or is set to an empty string, then
> it means that the application pool identity is used as an anonymous
> identity for that web site.

To modify the permissions settings on files and folders, use the Windows
Explorer user interface or `icacls` command.

**Example \#12 Configuring file access permissions**

    icacls C:\inetpub\wwwroot\upload /grant IUSR:(OI)(CI)(M)

#### Set `index.php` as a default document in IIS

The IIS default documents are used for HTTP requests that do not specify
a document name. With PHP applications, `index.php` usually acts as a
default document. To add `index.php` to the list of IIS default
documents, use this command:

**Example \#13 Set `index.php` as a default document in IIS**

    %windir%\system32\inetsrv\appcmd.exe set config ^
    -section:system.webServer/defaultDocument /+"files.[value='index.php']" ^
    /commit:apphost

#### FastCGI and PHP Recycling configuration

Configure IIS FastCGI settings for recycling of PHP processes by using
the commands shown below. The FastCGI setting `instanceMaxRequests`
controls how many requests will be processed by a single `php-cgi.exe`
process before IIS shuts it down. The PHP environment variable
`PHP_FCGI_MAX_REQUESTS` controls how many requests a single
`php-cgi.exe` process will handle before it recycles itself. Make sure
that the value specified for FastCGI `InstanceMaxRequests` setting is
less than or equal to the value specified for `PHP_FCGI_MAX_REQUESTS`.

**Example \#14 Configuring FastCGI and PHP recycling**

    %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi ^
    /[fullPath='c:\php\php-cgi.exe'].instanceMaxRequests:10000

    %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi ^
    /+"[fullPath='C:\{php_folder}\php-cgi.exe'].environmentVariables.^
    [name='PHP_FCGI_MAX_REQUESTS',value='10000']"

#### FastCGI timeout settings

Increase the timeout settings for FastCGI if it is expected to have long
running PHP scripts. The two settings that control timeouts are
`activityTimeout` and `requestTimeout`. Use the commands below to change
the timeout settings. Make sure to replace the value in the `fullPath`
parameter to contain the absolute path to the `php-cgi.exe` file.

**Example \#15 Configuring FastCGI timeout settings**

    %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi ^
    /[fullPath='C:\php\php-cgi.exe',arguments=''].activityTimeout:"90"  /commit:apphost

    %windir%\system32\inetsrv\appcmd.exe set config -section:system.webServer/fastCgi ^
    /[fullPath='C:\php\php-cgi.exe',arguments=''].requestTimeout:"90"  /commit:apphost

#### Changing the Location of `php.ini` file

PHP searches for `php.ini` file in
<a href="/configuration/file.html" class="link">several locations</a>
and it is possible to change the default locations of `php.ini` file by
using `PHPRC` environment variable. To instruct PHP to load the
configuration file from a custom location run the command shown below.
The absolute path to the directory with `php.ini` file should be
specified as a value of `PHPRC` environment variable.

**Example \#16 Changing the location of `php.ini` file**

    appcmd.exe set config  -section:system.webServer/fastCgi ^
    /+"[fullPath='C:\php\php.exe',arguments=''].environmentVariables.^
    [name='PHPRC',value='C:\Some\Directory\']" /commit:apphost

### Apache 1.3.x on Microsoft Windows

This section contains notes and hints specific to Apache 1.3.x installs
of PHP on Microsoft Windows systems. There are also

> **Note**:
>
> Please read the
> <a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">manual installation steps</a>
> first!

There are two ways to set up PHP to work with Apache 1.3.x on Windows.
One is to use the CGI binary (`php.exe` for PHP 4 and `php-cgi.exe` for
PHP 5), the other is to use the Apache Module DLL. In either case you
need to edit your `httpd.conf` to configure Apache to work with PHP, and
then restart the server.

It is worth noting here that now the SAPI module has been made more
stable under Windows, we recommend it's use above the CGI binary, since
it is more transparent and secure.

Although there can be a few variations of configuring PHP under Apache,
these are simple enough to be used by the newcomer. Please consult the
Apache Documentation for further configuration directives.

After changing the configuration file, remember to restart the server,
for example, **NET STOP APACHE** followed by **NET START APACHE**, if
you run Apache as a Windows Service, or use your regular shortcuts.

> **Note**: <span class="simpara">Remember that when adding path values
> in the Apache configuration files on Windows, all backslashes such as
> `c:\directory\file.ext` should be converted to forward slashes:
> `c:/directory/file.ext`. A trailing slash may also be necessary for
> directories.</span>

#### Installing as an Apache module

You should add the following lines to your Apache `httpd.conf` file:

**Example \#17 PHP as an Apache 1.3.x module**

This assumes PHP is installed to `c:\php`. Adjust the path if this is
not the case.

For PHP 4:

``` apache-conf
# Add to the end of the LoadModule section
# Don't forget to copy this file from the sapi directory!
LoadModule php4_module "C:/php/php4apache.dll"

# Add to the end of the AddModule section
AddModule mod_php4.c
```

For PHP 5:

``` apache-conf
# Add to the end of the LoadModule section
LoadModule php5_module "C:/php/php5apache.dll"

# Add to the end of the AddModule section
AddModule mod_php5.c
```

For both:

``` apache-conf
# Add this line inside the <IfModule mod_mime.c> conditional brace
AddType application/x-httpd-php .php

# For syntax highlighted .phps files, also add
AddType application/x-httpd-php-source .phps
```

#### Installing as a CGI binary

If you unzipped the PHP package to `C:\php\` as described in the
<a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">Manual Installation Steps</a>
section, you need to insert these lines to your Apache configuration
file to set up the CGI binary:

**Example \#18 PHP and Apache 1.3.x as CGI**

``` apache-conf
ScriptAlias /php/ "c:/php/"
AddType application/x-httpd-php .php

# For PHP 4
Action application/x-httpd-php "/php/php.exe"

# For PHP 5
Action application/x-httpd-php "/php/php-cgi.exe"

# specify the directory where php.ini is
SetEnv PHPRC C:/php
```

Note that the second line in the list above can be found in the actual
versions of `httpd.conf`, but it is commented out. Remember also to
substitute the `c:/php/` for your actual path to PHP.

**Warning**

A server deployed in CGI mode is open to several possible
vulnerabilities. Please read our
<a href="/security/cgi-bin.html" class="link">CGI security section</a>
to learn how to defend yourself from such attacks.

If you would like to present PHP source files syntax highlighted, there
is no such convenient option as with the module version of PHP. If you
chose to configure Apache to use PHP as a CGI binary, you will need to
use the <span class="function">highlight\_file</span> function. To do
this simply create a PHP script file and add this code: *\<?php
highlight\_file('some\_php\_script.php'); ?\>*.

### Apache 2.x on Microsoft Windows

This section contains notes and hints specific to Apache 2.x installs of
PHP on Microsoft Windows systems. We also

> **Note**:
>
> You should read the
> <a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">manual installation steps</a>
> first!

> **Note**: **Apache 2.2 Support**  
>
> Users of Apache 2.2 should note that the DLL file for Apache 2.2 is
> named `php5apache2_2.dll` rather than `php5apache2.dll` and is
> available only for PHP 5.2.0 and later.

You are strongly encouraged to consult the
<a href="http://httpd.apache.org/docs/current/" class="link external">» Apache Documentation</a>
to get a basic understanding of the Apache 2.x Server. Also consider
reading the
<a href="http://httpd.apache.org/docs/current/platform/windows.html" class="link external">» Windows specific notes</a>
for Apache 2.x before reading on here.

Apache 2.x is designed to run on the Windows version designated as
server platforms, such as Windows NT 4.0, Windows 2000, Windows XP, or
Windows 7. While Apache 2.x works tolerably well on Windows 9x, support
on these platforms is incomplete, and some things will not work
correctly. There is no plan to remedy this situation.

Download the most recent version of
<a href="http://httpd.apache.org/" class="link external">»  Apache 2.x</a>
and a fitting PHP version. Follow the
<a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">Manual Installation Steps</a>
and come back to go on with the integration of PHP and Apache.

There are three ways to set up PHP to work with Apache 2.x on Windows.
You can run PHP as a handler, as a CGI, or under FastCGI.

> **Note**: <span class="simpara">Remember that when adding path values
> in the Apache configuration files on Windows, all backslashes such as
> `c:\directory\file.ext` should be converted to forward slashes:
> `c:/directory/file.ext`. A trailing slash may also be necessary for
> directories.</span>

#### Installing as an Apache handler

You need to insert the following lines into your Apache `httpd.conf`
configuration file to load the PHP module for Apache 2.x:

**Example \#19 PHP and Apache 2.x as handler**

``` apache-conf
# 
LoadModule php5_module "c:/php/php5apache2.dll"
AddHandler application/x-httpd-php .php

# configure the path to php.ini
PHPIniDir "C:/php"
```

> **Note**: <span class="simpara"> Remember to substitute your actual
> path to PHP for the `C:/php/` in the above examples. Take care to use
> either `php5apache2.dll` or `php5apache2_2.dll` in your LoadModule
> directive and verify that the referenced file is in fact located at
> the file path that you point to in this directive. </span>

The above configuration will enable PHP handling of any file that has a
.php extension, even if there are other file extensions. For example, a
file named `example.php.txt` will be executed by the PHP handler. To
ensure that only files that *end in* `.php` are executed, use the
following configuration instead:

``` apache-conf
<FilesMatch \.php$>
      SetHandler application/x-httpd-php
 </FilesMatch>
```

#### Running PHP as CGI

You should consult the
<a href="http://httpd.apache.org/docs/current/howto/cgi.html" class="link external">» Apache CGI documentation</a>
for a more complete understanding of running CGI on Apache.

To run PHP as CGI, you'll need to place your php-cgi files in a
directory designated as a CGI directory using the ScriptAlias directive.

You will then need to insert a \#! line in the PHP files, pointing to
the location of your PHP binary:

**Example \#20 PHP and Apache 2.x as CGI**

    #!C:/php/php.exe
    <?php
      phpinfo();
    ?>

**Warning**

A server deployed in CGI mode is open to several possible
vulnerabilities. Please read our
<a href="/security/cgi-bin.html" class="link">CGI security section</a>
to learn how to defend yourself from such attacks.

#### Running PHP under FastCGI

Running PHP under FastCGI has a number of advantages over running it as
a CGI. Setting it up this way is fairly straightforward:

Obtain mod\_fcgid from
<a href="http://httpd.apache.org/mod_fcgid/" class="link external">» http://httpd.apache.org/mod_fcgid/</a>.
Win32 binaries are available for download from that site. Install the
module according to the instructions that will come with it.

Configure your web server as shown below, taking care to adjust any
paths to reflect your how you have installed things on your particular
system:

**Example \#21 Configure Apache to run PHP as FastCGI**

    LoadModule fcgid_module modules/mod_fcgid.so  

    # Where is your php.ini file?
    FcgidInitialEnv PHPRC        "c:/php" 

    AddHandler fcgid-script .php  
    FcgidWrapper "c:/php/php-cgi.exe" .php  

Files with a .php extension will now be executed by the PHP FastCGI
wrapper.

### Sun, iPlanet and Netscape servers on Microsoft Windows

This section contains notes and hints specific to Sun Java System Web
Server, Sun ONE Web Server, iPlanet and Netscape server installs of PHP
on Windows.

From PHP 4.3.3 on you can use PHP scripts with the
<a href="/ref/nsapi.html" class="link">NSAPI module</a> to Apache
compatibility are also available. For support in current web servers

#### CGI setup on Sun, iPlanet and Netscape servers

To install PHP as a CGI handler, do the following:

-   <span class="simpara"> Copy `php4ts.dll` to your systemroot (the
    directory where you installed Windows) </span>

-   Make a file association from the command line. Type the following
    two lines:

    ``` shell
    assoc .php=PHPScript
    ftype PHPScript=c:\php\php.exe %1 %*
    ```

-   <span class="simpara"> In the Netscape Enterprise Administration
    Server create a dummy shellcgi directory and remove it just after
    (this step creates 5 important lines in obj.conf and allow the web
    server to handle shellcgi scripts). </span>

-   <span class="simpara"> In the Netscape Enterprise Administration
    Server create a new mime type (Category: type, Content-Type:
    magnus-internal/shellcgi, File Suffix:php). </span>

-   <span class="simpara"> Do it for each web server instance you want
    PHP to run </span>

More details about setting up PHP as a CGI executable can be found here:
<a href="http://benoit.noss.free.fr/php/install-php.html" class="link external">» http://benoit.noss.free.fr/php/install-php.html</a>

#### NSAPI setup on Sun, iPlanet and Netscape servers

To install PHP with NSAPI, do the following:

-   <span class="simpara"> Copy `php4ts.dll` to your systemroot (the
    directory where you installed Windows) </span>

-   Make a file association from the command line. Type the following
    two lines:

    ``` shell
    assoc .php=PHPScript
    ftype PHPScript=c:\php\php.exe %1 %*
    ```

-   <span class="simpara"> In the Netscape Enterprise Administration
    Server create a new mime type (Category: type, Content-Type:
    magnus-internal/x-httpd-php, File Suffix: php). </span>

-   Edit `magnus.conf` (for servers \>= 6) or `obj.conf` (for servers
    \< 6) and add the following: You should place the lines after *mime
    types init*.

        Init fn="load-modules" funcs="php4_init,php4_execute,php4_auth_trans" shlib="c:/php/sapi/php4nsapi.dll"
        Init fn="php4_init" LateInit="yes" errorString="Failed to initialise PHP!" [php_ini="c:/path/to/php.ini"]

    (PHP \>= 4.3.3) The *php\_ini* parameter is optional but with it you
    can place your `php.ini` in your web server configuration directory.

-   Configure the default object in `obj.conf` (for virtual server
    classes \[Sun Web Server 6.0+\] in their `vserver.obj.conf`): In the
    *\<Object name="default"\>* section, place this line necessarily
    after all 'ObjectType' and before all 'AddLog' lines:

        Service fn="php4_execute" type="magnus-internal/x-httpd-php" [inikey=value inikey=value ...]

    (PHP \>= 4.3.3) As additional parameters you can add some special
    `php.ini`-values, for example you can set a
    *docroot="/path/to/docroot"* specific to the context *php4\_execute*
    is called. For boolean ini-keys please use 0/1 as value, not
    *"On","Off",...* (this will not work correctly), e.g.
    *zlib.output\_compression=1* instead of
    *zlib.output\_compression="On"*

-   This is only needed if you want to configure a directory that only
    consists of PHP scripts (same like a cgi-bin directory):

        <Object name="x-httpd-php">
        ObjectType fn="force-type" type="magnus-internal/x-httpd-php"
        Service fn=php4_execute [inikey=value inikey=value ...]
        </Object>

    After that you can configure a directory in the Administration
    server and assign it the style *x-httpd-php*. All files in it will
    get executed as PHP. This is nice to hide PHP usage by renaming
    files to `.html`.

-   <span class="simpara"> Restart your web service and apply changes
    </span>

-   <span class="simpara"> Do it for each web server instance you want
    PHP to run </span>

> **Note**:
>
> More details about setting up PHP as an NSAPI filter can be found
> here:
> <a href="http://benoit.noss.free.fr/php/install-php4.html" class="link external">» http://benoit.noss.free.fr/php/install-php4.html</a>

> **Note**:
>
> The stacksize that PHP uses depends on the configuration of the web
> server. If you get crashes with very large PHP scripts, it is
> recommended to raise it with the Admin Server (in the section "MAGNUS
> EDITOR").

#### CGI environment and recommended modifications in `php.ini`

Important when writing PHP scripts is the fact that Sun JSWS/Sun ONE
WS/iPlanet/Netscape is a multithreaded web server. Because of that all
requests are running in the same process space (the space of the web
server itself) and this space has only one environment. If you want to
get CGI variables like *PATH\_INFO*, *HTTP\_HOST* etc. it is not the
correct way to try this in the old PHP way with <span
class="function">getenv</span> or a similar way (register globals to
environment, *$\_ENV*). You would only get the environment of the
running web server without any valid CGI variables!

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

#### Special use for error pages or self-made directory listings (PHP \>= 4.3.3)

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
corresponding default Service line for
*type="magnus-internal/directory"* in `obj.conf` with the following:

    Service fn="php4_execute" type="magnus-internal/directory" script="/path/to/script.php" [inikey=value inikey=value...]

For both error and directory listing pages the original URI and
translated URI are in the variables `$_SERVER['PATH_INFO']` and
`$_SERVER['PATH_TRANSLATED']`.

#### Note about <span class="function">nsapi\_virtual</span> and subrequests (PHP \>= 4.3.3)

The NSAPI module now supports the <span
class="function">nsapi\_virtual</span> function (alias: <span
class="function">virtual</span>) to make subrequests on the web server
and insert the result in the web page. The problem is, that this
function uses some undocumented features from the NSAPI library.

Under Unix this is not a problem, because the module automatically looks
for the needed functions and uses them if available. If not, <span
class="function">nsapi\_virtual</span> is disabled.

Under Windows limitations in the DLL handling need the use of a
automatic detection of the most recent `ns-httpdXX.dll` file. This is
tested for servers till version 6.1. If a newer version of the Sun
server is used, the detection fails and <span
class="function">nsapi\_virtual</span> is disabled.

If this is the case, try the following: Add the following parameter to
*php4\_init* in `magnus.conf`/`obj.conf`:

    Init fn=php4_init ... server_lib="ns-httpdXX.dll"

where *XX* is the correct DLL version number. To get it, look in the
server-root for the correct DLL name. The DLL with the biggest filesize
is the right one.

You can check the status by using the <span
class="function">phpinfo</span> function.

> **Note**:
>
> But be warned: Support for <span
> class="function">nsapi\_virtual</span> is EXPERIMENTAL!!!

### Sambar Server on Microsoft Windows

This section contains notes and hints specific to the
<a href="http://www.sambar.com/" class="link external">» Sambar Server</a>
for Windows.

> **Note**:
>
> You should read the
> <a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">manual installation steps</a>
> first!

This list describes how to set up the ISAPI module to work with the
Sambar server on Windows.

-   Find the file called `mappings.ini` (in the config directory) in the
    Sambar install directory.

-   Open `mappings.ini` and add the following line under *\[ISAPI\]*:

    **Example \#22 ISAPI configuration of Sambar**

        #for PHP 4
        *.php = c:\php\php4isapi.dll

        #for PHP 5
        *.php = c:\php\php5isapi.dll

    (This line assumes that PHP was installed in `c:\php`.)

-   Now restart the Sambar server for the changes to take effect.

> **Note**:
>
> If you intend to use PHP to communicate with resources which are held
> on a different computer on your network, then you will need to alter
> the account used by the Sambar Server Service. The default account
> used for the Sambar Server Service is LocalSystem which will not have
> access to remote resources. The account can be amended by using the
> Services option from within the Windows Control Panel Administration
> Tools.

### Xitami on Microsoft Windows

This section contains notes and hints specific to
<a href="http://www.xitami.com/" class="link external">» Xitami</a> on
Windows.

> **Note**:
>
> You should read the
> <a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">manual installation steps</a>
> first!

This list describes how to set up the PHP CGI binary to work with Xitami
on Windows.

> **Note**: **Important for CGI users**  
>
> Read the
> <a href="/faq/installation.html#faq.installation.forceredirect" class="link">faq on cgi.force_redirect</a>
> for important details. This directive needs to be set to *0*. If you
> want to use *$\_SERVER\['PHP\_SELF'\]* you have to enable the
> <a href="/ini/core.html#ini.cgi.fix-pathinfo" class="link">cgi.fix_pathinfo</a>
> directive.

**Warning**

A server deployed in CGI mode is open to several possible
vulnerabilities. Please read our
<a href="/security/cgi-bin.html" class="link">CGI security section</a>
to learn how to defend yourself from such attacks.

-   Make sure the web server is running, and point your browser to
    xitamis admin console (usually *http://127.0.0.1/admin*), and click
    on Configuration.

-   Navigate to the Filters, and put the extension which PHP should
    parse (i.e. .php) into the field File extensions (.xxx).

-   In Filter command or script put the path and name of your PHP CGI
    executable i.e. `C:\php\php.exe` for PHP 4, or `C:\php\php-cgi.exe`
    for PHP 5.

-   Press the 'Save' icon.

-   Restart the server to reflect changes.

### Building from source

This chapter teaches how to compile PHP from sources on windows, using
Microsoft's tools. To compile PHP with cygwin, please refer to
<a href="/install/unix.html" class="xref">Installation on Unix systems</a>.

See the Wiki documentation at:
<a href="https://wiki.php.net/internals/windows/stepbystepbuild" class="link external">» https://wiki.php.net/internals/windows/stepbystepbuild</a>

### Installation of extensions on Windows

After installing PHP and a web server on Windows, you will probably want
to install some extensions for added functionality. You can choose which
extensions you would like to load when PHP starts by modifying your
`php.ini`. You can also load a module dynamically in your script using
<span class="function">dl</span>.

The DLLs for PHP extensions are prefixed with *php\_*.

Many extensions are *built into* the Windows version of PHP. This means
additional DLL files, and the
<a href="/ini/core.html#ini.extension" class="link">extension</a>
directive, are *not* used to load these extensions. The Windows
<a href="/install/windows/legacy/index.html#install.windows.legacy.extensions.overview" class="link">PHP Extensions</a>
table lists extensions that require, or used to require, additional PHP
DLL files. Here's a list of built in extensions (updated PHP 5.0.4):
<a href="/book/bc.html" class="link">BCMath</a>,
<a href="/book/calendar.html" class="link">Calendar</a>,
<a href="/book/com.html" class="link">COM</a>,
<a href="/book/ctype.html" class="link">Ctype</a>,
<a href="/book/dom.html" class="link">DOM</a>,
<a href="/book/ftp.html" class="link">FTP</a>,
<a href="/book/libxml.html" class="link">LibXML</a>,
<a href="/book/iconv.html" class="link">Iconv</a>,
<a href="/book/uodbc.html" class="link">ODBC</a>,
<a href="/book/pcre.html" class="link">PCRE</a>,
<a href="/book/session.html" class="link">Session</a>,
<a href="/book/simplexml.html" class="link">SimpleXML</a>,
<a href="/book/spl.html" class="link">SPL</a>,
<a href="/book/wddx.html" class="link">WDDX</a>,
<a href="/book/xml.html" class="link">XML</a> and
<a href="/book/zlib.html" class="link">Zlib</a>.

The default location PHP searches for extensions is `C:\php5`. To change
this setting to reflect your setup of PHP edit your `php.ini` file:

-   You will need to change the
    <a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>
    setting to point to the directory where your extensions lives, or
    where you have placed your `php_*.dll` files. For example:

    ``` ini
    extension_dir = C:\php\extensions
    ```

-   Enable the extension(s) in `php.ini` you want to use by uncommenting
    the *extension=php\_\*.dll* lines in `php.ini`. This is done by
    deleting the leading ; from the extension you want to load.

    **Example \#23 Enable
    <a href="/book/bzip2.html" class="link">Bzip2</a> extension for
    PHP-Windows**

    ``` ini
    // change the following line from ...
    ;extension=php_bz2.dll

    // ... to
    extension=php_bz2.dll
    ```

-   Some of the extensions need extra DLLs to work. Couple of them can
    be found in the distribution package, in the main folder, but some,
    for example Oracle (`php_oci8.dll`) require DLLs which are not
    bundled with the distribution package. Don't forget to include
    `C:\php` in the system `PATH` (this process is explained in a
    separate
    <a href="/faq/installation.html#faq.installation.addtopath" class="link">FAQ entry</a>).

-   Some of these DLLs are not bundled with the PHP distribution. See
    each extensions documentation page for details. Also, read the
    manual section titled
    <a href="/install/pecl.html" class="link">Installation of PECL extensions</a>
    for details on PECL. An increasingly large number of PHP extensions
    are found in PECL, and these extensions require a
    <a href="/install/pecl/downloads.html" class="link">separate download</a>.

> **Note**: <span class="simpara"> If you are running a server module
> version of PHP remember to restart your web server to reflect your
> changes to `php.ini`. </span>

The following table describes some of the extensions available and
required additional dlls.

| Extension            | Description                                                                                     | Notes                                                                                                                                        |
|----------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| php\_bz2.dll         | <a href="/book/bzip2.html" class="link">bzip2</a> compression functions                         | None                                                                                                                                         |
| php\_calendar.dll    | <a href="/book/calendar.html" class="link">Calendar</a> conversion functions                    | None                                                                                                                                         |
| php\_ctype.dll       | <a href="/book/ctype.html" class="link">ctype</a> family functions                              | None                                                                                                                                         |
| php\_curl.dll        | <a href="/book/curl.html" class="link">CURL</a>, Client URL library functions                   | Requires: `libeay32.dll`, `ssleay32.dll` (bundled), or, as of OpenSSL 1.1 `libcrypto-*.dll` and `libssl-*.dll` (bundled)                     |
| php\_dba.dll         | <a href="/book/dba.html" class="link">DBA</a>: DataBase (dbm-style) Abstraction layer functions | None                                                                                                                                         |
| php\_dbase.dll       | <a href="/book/dbase.html" class="link">dBase</a> functions                                     | None                                                                                                                                         |
| php\_dbx.dll         | <a href="/book/dbx.html" class="link">dbx</a> functions                                         |                                                                                                                                              |
| php\_exif.dll        | <a href="/book/exif.html" class="link">EXIF</a> functions                                       | <a href="/book/mbstring.html" class="link">php_mbstring.dll</a>. And, `php_exif.dll` must be loaded *after* `php_mbstring.dll` in `php.ini`. |
| php\_fbsql.dll       | <a href="/book/fbsql.html" class="link">FrontBase</a> functions                                 | None                                                                                                                                         |
| php\_fdf.dll         | <a href="/book/fdf.html" class="link">FDF</a>: Forms Data Format functions.                     | Requires: `fdftk.dll` (bundled)                                                                                                              |
| php\_filepro.dll     | <a href="/book/filepro.html" class="link">filePro</a> functions                                 | Read-only access                                                                                                                             |
| php\_ftp.dll         | <a href="/book/ftp.html" class="link">FTP</a> functions                                         | None                                                                                                                                         |
| php\_gd2.dll         | <a href="/book/image.html" class="link">GD</a> library image functions                          | GD2                                                                                                                                          |
| php\_gettext.dll     | <a href="/book/gettext.html" class="link">Gettext</a> functions                                 | PHP \<= 4.2.0 requires `gnu_gettext.dll` (bundled), PHP \>= 4.2.3 requires `libintl-1.dll`, `iconv.dll` (bundled).                           |
| php\_hyperwave.dll   | HyperWave functions                                                                             | None                                                                                                                                         |
| php\_iconv.dll       | <a href="/book/iconv.html" class="link">ICONV</a> characterset conversion                       | Requires: `iconv-1.3.dll` (bundled), `iconv.dll`                                                                                             |
| php\_ifx.dll         | <a href="/book/ifx.html" class="link">Informix</a> functions                                    | Requires: Informix libraries                                                                                                                 |
| php\_iisfunc.dll     | IIS management functions                                                                        | None                                                                                                                                         |
| php\_imap.dll        | <a href="/book/imap.html" class="link">IMAP</a> POP3 and NNTP functions                         | None                                                                                                                                         |
| php\_ingres.dll      | <a href="/book/ingres.html" class="link">Ingres</a> functions                                   | Requires: Ingres libraries                                                                                                                   |
| php\_interbase.dll   | <a href="/book/ibase.html" class="link">InterBase</a> functions                                 | Requires: `gds32.dll` (bundled)                                                                                                              |
| php\_ldap.dll        | <a href="/book/ldap.html" class="link">LDAP</a> functions                                       | Requires `libeay32.dll`, `ssleay32.dll` (bundled), or, as of OpenSSL 1.1 `libcrypto-*.dll` and `libssl-*.dll` (bundled)                      |
| php\_mbstring.dll    | <a href="/book/mbstring.html" class="link">Multi-Byte String</a> functions                      | None                                                                                                                                         |
| php\_mcrypt.dll      | <a href="/book/mcrypt.html" class="link">Mcrypt Encryption</a> functions                        | Requires: `libmcrypt.dll`                                                                                                                    |
| php\_mhash.dll       | <a href="/book/mhash.html" class="link">Mhash</a> functions                                     | Requires: `libmhash.dll` (bundled)                                                                                                           |
| php\_mime\_magic.dll | <a href="/book/mime-magic.html" class="link">Mimetype</a> functions                             | Requires: `magic.mime` (bundled)                                                                                                             |
| php\_mysql.dll       | <a href="/set/mysqlinfo.html#MySQL%20(Original)" class="link">MySQL</a> functions               | Requires `libmysql.dll` (bundled)                                                                                                            |
| php\_mysqli.dll      | <a href="/set/mysqlinfo.html#MySQLi" class="link">MySQLi</a> functions                          | Requires `libmysql.dll` (`libmysqli.dll` in PHP \<= 5.0.2) (bundled)                                                                         |
| php\_oci8.dll        | <a href="/book/oci8.html" class="link">Oracle 8</a> functions                                   | Requires: Oracle 8.1+ client libraries                                                                                                       |
| php\_openssl.dll     | <a href="/book/openssl.html" class="link">OpenSSL</a> functions                                 | Requires: `libeay32.dll` (bundled), or, as of OpenSSL 1.1, `liblibcrypto-*.dll` (bundled)                                                    |
| php\_pgsql.dll       | <a href="/book/pgsql.html" class="link">PostgreSQL</a> functions                                | None                                                                                                                                         |
| php\_shmop.dll       | <a href="/book/shmop.html" class="link">Shared Memory</a> functions                             | None                                                                                                                                         |
| php\_snmp.dll        | <a href="/book/snmp.html" class="link">SNMP</a> get and walk functions                          | NT only!                                                                                                                                     |
| php\_soap.dll        | <a href="/book/soap.html" class="link">SOAP</a> functions                                       | None                                                                                                                                         |
| php\_sockets.dll     | <a href="/book/sockets.html" class="link">Socket</a> functions                                  | None                                                                                                                                         |
| php\_tidy.dll        | <a href="/book/tidy.html" class="link">Tidy</a> functions                                       | None                                                                                                                                         |
| php\_tokenizer.dll   | <a href="/book/tokenizer.html" class="link">Tokenizer</a> functions                             | None                                                                                                                                         |
| php\_w32api.dll      | W32api functions                                                                                | None                                                                                                                                         |
| php\_xmlrpc.dll      | <a href="/book/xmlrpc.html" class="link">XML-RPC</a> functions                                  | Requires: `iconv.dll` (bundled)                                                                                                              |
| php\_xslt.dll        | XSLT functions                                                                                  | Requires `sablot.dll`, `expat.dll`, `iconv.dll` (bundled).                                                                                   |
| php\_yaz.dll         | <a href="/book/yaz.html" class="link">YAZ</a> functions                                         | Requires: `yaz.dll` (bundled)                                                                                                                |
| php\_zip.dll         | <a href="/book/zip.html" class="link">Zip File</a> functions                                    | Read only access                                                                                                                             |
| php\_zlib.dll        | <a href="/book/zlib.html" class="link">ZLib</a> compression functions                           | None                                                                                                                                         |

### Command Line PHP on Microsoft Windows

This section contains notes and hints specific to getting PHP running
from the command line for Windows.

> **Note**:
>
> You should read the
> <a href="/install/windows/legacy/index.html#install.windows.legacy.manual" class="link">manual installation steps</a>
> first!

Getting PHP to run from the command line can be performed without making
any changes to Windows.

    C:\PHP5\php.exe -f "C:\PHP Scripts\script.php" -- -arg1 -arg2 -arg3

But there are some easy steps that can be followed to make this simpler.
Some of these steps should already have been taken, but are repeated
here to be able to provide a complete step-by-step sequence.

-   Append the location of the PHP executable (`php.exe`, `php-win.exe`
    or `php-cli.exe` depending upon your PHP version and display
    preferences) to the `PATH` environment variable. Read more about how
    to add your PHP directory to `PATH` in the
    <a href="/faq/installation.html#faq.installation.addtopath" class="link">corresponding FAQ entry</a>.

-   Append the *.PHP* extension to the `PATHEXT` environment variable.
    This can be done at the same time as amending the `PATH` environment
    variable. Follow the same steps as described in the
    <a href="/faq/installation.html#faq.installation.addtopath" class="link">FAQ</a>
    but amend the `PATHEXT` environment variable rather than the `PATH`
    environment variable.

    > **Note**:
    >
    > The position in which you place the *.PHP* will determine which
    > script or program is executed when there are matching filenames.
    > For example, placing *.PHP* before *.BAT* will cause your script
    > to run, rather than the batch file, if there is a batch file with
    > the same name.

-   Associate the *.PHP* extension with a file type. This is done by
    running the following command:

        assoc .php=phpfile

-   Associate the *phpfile* file type with the appropriate PHP
    executable. This is done by running the following command:

        ftype phpfile="C:\PHP5\php.exe" -f "%1" -- %~2

Following these steps will allow PHP scripts to be run from any
directory without the need to type the PHP executable or the *.PHP*
extension and all parameters will be supplied to the script for
processing.

The example below details some of the registry changes that can be made
manually.

**Example \#24 Registry changes**

    Windows Registry Editor Version 5.00

    [HKEY_LOCAL_MACHINE\SOFTWARE\Classes\.php]
    @="phpfile"
    "Content Type"="application/php"

    [HKEY_LOCAL_MACHINE\SOFTWARE\Classes\phpfile]
    @="PHP Script"
    "EditFlags"=dword:00000000
    "BrowserFlags"=dword:00000008
    "AlwaysShowExt"=""

    [HKEY_LOCAL_MACHINE\SOFTWARE\Classes\phpfile\DefaultIcon]
    @="C:\\PHP5\\php-win.exe,0"

    [HKEY_LOCAL_MACHINE\SOFTWARE\Classes\phpfile\shell]
    @="Open"

    [HKEY_LOCAL_MACHINE\SOFTWARE\Classes\phpfile\shell\Open]
    @="&Open"

    [HKEY_LOCAL_MACHINE\SOFTWARE\Classes\phpfile\shell\Open\command]
    @="\"C:\\PHP5\\php.exe\" -f \"%1\" -- %~2"

With these changes the same command can be written as:

    "C:\PHP Scripts\script" -arg1 -arg2 -arg3

or, if your *"C:\\PHP Scripts"* path is in the `PATH` environment
variable:

    script -arg1 -arg2 -arg3

> **Note**:
>
> There is a small problem if you intend to use this technique and use
> your PHP scripts as a command line filter, like the example below:
>
>     dir | "C:\PHP Scripts\script" -arg1 -arg2 -arg3
>
> or
>
>     dir | script -arg1 -arg2 -arg3
>
> You may find that the script simply hangs and nothing is output. To
> get this operational, you need to make another registry change.
>
>     Windows Registry Editor Version 5.00
>
>     [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\policies\Explorer]
>     "InheritConsoleHandles"=dword:00000001
>
> Further information regarding this issue can be found in this
> <a href="http://support.microsoft.com/default.aspx?scid=kb;en-us;321788" class="link external">» Microsoft Knowledgebase Article : 321788</a>.
> As of Windows 10, this setting seems to be reversed, making the
> default install of Windows 10 support inherited console handles
> automatically. This
> <a href="https://social.msdn.microsoft.com/Forums/en-US/f19d740d-21c8-4dc2-a9ab-d5c0527e932b/nasty-file-association-regression-bug-in-windows-10-console?forum=windowssdk" class="link external">»  Microsoft forum post</a>
> provides the explanation.

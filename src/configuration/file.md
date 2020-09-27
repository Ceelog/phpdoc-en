The configuration file
----------------------

The configuration file (`php.ini`) is read when PHP starts up. For the
server module versions of PHP, this happens only once when the web
server is started. For the CGI and CLI versions, it happens on every
invocation.

`php.ini` is searched for in these locations (in order):

-   <span class="simpara"> SAPI module specific location (*PHPIniDir*
    directive in Apache 2, *-c* command line option in CGI and CLI,
    *php\_ini* parameter in NSAPI) </span>
-   <span class="simpara"> The `PHPRC` environment variable. Before PHP
    5.2.0, this was checked after the registry key mentioned below.
    </span>
-   <span class="simpara"> As of PHP 5.2.0, the location of the
    *php.ini* file can be set for different versions of PHP. The root of
    the registry keys depends on 32- or 64-bitness of the installed OS
    and PHP. For 32-bit PHP on a 32-bit OS or a 64-bit PHP on a 64-bit
    OS use *\[(HKEY\_LOCAL\_MACHINE\\SOFTWARE\\PHP\]* for 32-bit version
    of PHP on a 64-bit OS use
    *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\WOW6432Node\\PHP\]*\] instead.
    For same bitness installation the following registry keys are
    examined in order: *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\PHP\\x.y.z\]*,
    *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\PHP\\x.y\]* and
    *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\PHP\\x\]*, where x, y and z mean
    the PHP major, minor and release versions. For 32 bit versions of
    PHP on a 64 bit OS the following registry keys are examined in
    order:
    *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\WOW6421Node\\PHP\\x.y.z\]*,
    *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\WOW6421Node\\PHP\\x.y\]* and
    *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\WOW6421Node\\PHP\\x\]*, where x,
    y and z mean the PHP major, minor and release versions. If there is
    a value for *IniFilePath* in any of these keys, the first one found
    will be used as the location of the *php.ini* (Windows only).
    </span>
-   <span class="simpara"> *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\PHP\]* or
    *\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\WOW6432Node\\PHP\]*, value of
    *IniFilePath* (Windows only). </span>
-   <span class="simpara"> Current working directory (except CLI).
    </span>
-   <span class="simpara"> The web server's directory (for SAPI
    modules), or directory of PHP (otherwise in Windows). </span>
-   <span class="simpara"> Windows directory (`C:\windows` or
    `C:\winnt`) (for Windows), or *--with-config-file-path* compile time
    option. </span>

If `php-SAPI.ini` exists (where SAPI is the SAPI in use, so, for
example, `php-cli.ini` or `php-apache.ini`), it is used instead of
`php.ini`. The SAPI name can be determined with <span
class="function">php\_sapi\_name</span>.

> **Note**:
>
> The Apache web server changes the directory to root at startup,
> causing PHP to attempt to read `php.ini` from the root filesystem if
> it exists.

Using environment variables can be used in `php.ini` as shown below.

**Example \#1 `php.ini` Environment Variables**

``` ini
; PHP_MEMORY_LIMIT is taken from environment
memory_limit = ${PHP_MEMORY_LIMIT}
```

The `php.ini` directives handled by extensions are documented on the
respective pages of the extensions themselves. A
<a href="/ini.html" class="link">list of the core directives</a> is
available in the appendix. Not all PHP directives are necessarily
documented in this manual: for a complete list of directives available
in your PHP version, please read your well commented `php.ini` file.
Alternatively, you may find
<a href="https://git.php.net/?p=php-src.git;a=blob;f=php.ini-production;hb=HEAD" class="link external">» the latest <var class="filename">php.ini</var></a>
from Git helpful too.

**Example \#2 `php.ini` example**

``` ini
; any text on a line after an unquoted semicolon (;) is ignored
[php] ; section markers (text within square brackets) are also ignored
; Boolean values can be set to either:
;    true, on, yes
; or false, off, no, none
register_globals = off
track_errors = yes

; you can enclose strings in double-quotes
include_path = ".:/usr/local/lib/php"

; backslashes are treated the same as any other character
include_path = ".;c:\php\lib"
```

Since PHP 5.1.0, it is possible to refer to existing .ini variables from
within .ini files. Example: *open\_basedir = ${open\_basedir}
":/new/dir"*.

### Scan directories

It is possible to configure PHP to scan for .ini files in a directory
after reading `php.ini`. This can be done at compile time by setting the
**--with-config-file-scan-dir** option. In PHP 5.2.0 and later, the scan
directory can then be overridden at run time by setting the
`PHP_INI_SCAN_DIR` environment variable.

It is possible to scan multiple directories by separating them with the
platform-specific path separator (*;* on Windows, NetWare and RISC OS;
*:* on all other platforms; the value PHP is using is available as the
**`PATH_SEPARATOR`** constant). If a blank directory is given in
`PHP_INI_SCAN_DIR`, PHP will also scan the directory given at compile
time via **--with-config-file-scan-dir**.

Within each directory, PHP will scan all files ending in *.ini* in
alphabetical order. A list of the files that were loaded, and in what
order, is available by calling <span
class="function">php\_ini\_scanned\_files</span>, or by running PHP with
the **--ini** option.

    Assuming PHP is configured with --with-config-file-scan-dir=/etc/php.d,
    and that the path separator is :...

    $ php
      PHP will load all files in /etc/php.d/*.ini as configuration files.

    $ PHP_INI_SCAN_DIR=/usr/local/etc/php.d php
      PHP will load all files in /usr/local/etc/php.d/*.ini as
      configuration files.

    $ PHP_INI_SCAN_DIR=:/usr/local/etc/php.d php
      PHP will load all files in /etc/php.d/*.ini, then
      /usr/local/etc/php.d/*.ini as configuration files.

    $ PHP_INI_SCAN_DIR=/usr/local/etc/php.d: php
      PHP will load all files in /usr/local/etc/php.d/*.ini, then
      /etc/php.d/*.ini as configuration files.

### Changelog

| Version | Description                                                                                                         |
|---------|---------------------------------------------------------------------------------------------------------------------|
| 7.0.0   | Hash marks (*\#*) are no longer recognized as comments.                                                             |
| 5.3.0   | Hash marks (*\#*) should no longer be used as comments and will throw a deprecation warning if used.                |
| 5.2.0   | The `PHP_INI_SCAN_DIR` environment variable can be set to override the scan directory set via the configure script. |
| 5.1.0   | It is possible to refer to existing .ini variables from within .ini files.                                          |

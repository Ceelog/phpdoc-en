Installing a PHP extension on Windows
-------------------------------------

On Windows, you have two ways to load a PHP extension: either compile it
into PHP, or load the DLL. Loading a pre-compiled extension is the
easiest and preferred way.

To load an extension, you need to have it available as a ".dll" file on
your system. All the extensions are automatically and periodically
compiled by the PHP Group (see next section for the download).

To compile an extension into PHP, please refer to
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building from source</a>
documentation.

To compile a standalone extension (aka a DLL file), please refer to
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building from source</a>
documentation. If the DLL file is available neither with your PHP
distribution nor in PECL, you may have to compile it before you can
start using the extension.

### Where to find an extension?

PHP extensions are usually called "php\_\*.dll" (where the star
represents the name of the extension) and they are located under the
"PHP\\ext" folder.

PHP ships with the extensions most useful to the majority of developers.
They are called "core" extensions.

However, if you need functionality not provided by any core extension,
you may still be able to find one in
<a href="https://pecl.php.net/" class="link external">» PECL</a>. The
PHP Extension Community Library (PECL) is a repository for PHP
Extensions, providing a directory of all known extensions and hosting
facilities for downloading and development of PHP extensions.

If you have developed an extension for your own uses, you might want to
think about hosting it on PECL so that others with the same needs can
benefit from your time. A nice side effect is that you give them a good
chance to give you feedback, (hopefully) thanks, bug reports and even
fixes/patches. Before you submit your extension for hosting on PECL,
please read
<a href="https://pecl.php.net/package-new.php" class="link external">» PECL submit</a>.

### Which extension to download?

*Many times, you will find several versions of each DLL:*

-   <span class="simpara"> Different version numbers (at least the first
    two numbers should match) </span>
-   <span class="simpara"> Different thread safety settings </span>
-   <span class="simpara"> Different processor architecture (x86, x64,
    ...) </span>
-   <span class="simpara"> Different debugging settings </span>
-   <span class="simpara"> *etc.* </span>

You should keep in mind that your extension settings should match all
the settings of the PHP executable you are using. The following PHP
script will tell you *all* about your PHP settings:

**Example \#1 <span class="function">phpinfo</span> call**

``` php
<?php
phpinfo();
?>
```

Or from the command line, run:

    drive:\\path\to\php\executable\php.exe -i

### Loading an extension

The most common way to load a PHP extension is to include it in your
`php.ini` configuration file. Please note that many extensions are
already present in your `php.ini` and that you only need to remove the
semicolon to activate them.

Note that, on PHP version 7.2.0 and up, the extension name may be used
instead of the extension's file name. As this is OS-independent and
easier, especially for newcomers, it becomes the recommended way of
specifying extensions to load. File names remain supported for
compatibility with prior versions.

    ;extension=php_extname.dll

    extension=php_extname.dll

    ; On PHP version 7.2 and up, prefer :
    extension=extname
    zend_extension=another_extension

However, some web servers are confusing because they do not use the
`php.ini` located alongside your PHP executable. To find out where your
actual `php.ini` resides, look for its path in <span
class="function">phpinfo</span>:

    Configuration File (php.ini) Path  C:\WINDOWS

    Loaded Configuration File   C:\Program Files\PHP\5.2\php.ini

After activating an extension, save `php.ini`, restart the web server
and check <span class="function">phpinfo</span> again. The new extension
should now have its own section.

### Resolving problems

If the extension does not appear in <span
class="function">phpinfo</span>, you should check your logs to learn
where the problem comes from.

If you are using PHP from the command line (CLI), the extension loading
error can be read directly on screen.

If you are using PHP with a web server, the location and format of the
logs vary depending on your software. Please read your web server
documentation to locate the logs, as it does not have anything to do
with PHP itself.

Common problems are the location of the DLL, the value of the "
<a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>"
setting inside `php.ini` and compile-time setting mismatches.

If the problem lies in a compile-time setting mismatch, you probably
didn't download the right DLL. Try downloading again the extension with
the right settings. Again, <span class="function">phpinfo</span> can be
of great help.

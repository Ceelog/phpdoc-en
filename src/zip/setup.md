Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/zip/setup.html#Requirements)
-   [Installation](/zip/setup.html#Installation)
-   [Runtime Configuration](/zip/setup.html#Runtime%20Configuration)
-   [Resource Types](/zip/setup.html#Resource%20Types)

Requirements
------------

This extension requires
<a href="https://libzip.org/" class="link external">» libzip</a>.
Version 1.1.2 was bundled in PHP until version 7.3.

Minimal supported version is 0.11, but higher is highly recommended.

-   Version 1.2 required for encryption support, see <span
    class="methodname">ZipArchive::setEncryptionIndex</span>
-   Version 1.3 required for progress support, see <span
    class="methodname">ZipArchive::registerProgressCallback</span>
-   Version 1.6 required for cancel support, see <span
    class="methodname">ZipArchive::registerCancelCallback</span>

Installation
------------

Linux systems
-------------

As of PHP 7.4.0, in order to use these functions you must compile PHP
with zip support by using the **--with-zip** configure option.
Previously, zip support had to be enabled by using the **--enable-zip**
configure option.

As of PHP 5.6.0 a **--with-libzip=DIR** configure option has been added
to use a system libzip installation. libzip version 0.11 is required,
with 0.11.2 or later recommended.

As of PHP 7.3.0, building against the bundled libzip is discouraged, but
still possible by adding **--without-libzip** to the configuration. As
of PHP 7.4.0, the bundled libzip is removed.

Windows
-------

As of PHP 5.3 this extension is built-in. Before, Windows users need to
enable `php_zip.dll` inside of `php.ini` in order to use these
functions.

Installation via PECL
---------------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/zip" class="link external">» https://pecl.php.net/package/zip</a>.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

There are two resource types used in the Zip module. The first one is
the Zip directory for the Zip archive, the second Zip Entry for the
archive entries.

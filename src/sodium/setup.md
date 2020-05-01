Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/sodium/setup.html#Requirements)
-   [Installation](/sodium/setup.html#Installation)
-   [Runtime Configuration](/sodium/setup.html#Runtime%20Configuration)
-   [Resource Types](/sodium/setup.html#Resource%20Types)

Requirements
------------

This extension requires
<a href="https://libsodium.org/" class="link external">» libsodium</a> ≥
1.0.8.

Installation
------------

As of PHP 7.2.0 this extension is bundled with PHP. For older PHP
versions this extension is available via PECL.

Linux Systems
-------------

In order to use this extension you must compile PHP with sodium support
by using the **--with-sodium\[=DIR\]** configure option.

Windows
-------

In order to use this extension you have to add
*extension=php\_sodium.dll* to `php.ini`.

Installation via PECL
---------------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/libsodium" class="link external">» https://pecl.php.net/package/libsodium</a>

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

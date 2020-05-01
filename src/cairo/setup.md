Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/cairo/setup.html#Requirements)
-   [Installation](/cairo/setup.html#Installation)
-   [Runtime Configuration](/cairo/setup.html#Runtime%20Configuration)
-   [Resource Types](/cairo/setup.html#Resource%20Types)

Requirements
------------

Cairo is only available for PHP 5.2+ and PHP 5.3+ The extension also
requires the cairo graphics library version 1.4 or higher. The cairo
graphics library uses an even and odd numbering scheme to denote stable
and unstable library versions. Both unstable and stable versions can be
used with the extension, but conditional support for new features is
determined by the stable version below the unstable version in use. The
latest cairo release can be found at
<a href="http://cairographics.org/" class="link external">» http://cairographics.org/</a>.

The binary files used for the windows compiles can be found at
<a href="http://cairographics.org/download/" class="link external">» http://cairographics.org/download/</a>
along with the project files used to create them.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/cairo" class="link external">» https://pecl.php.net/package/cairo</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Notes specific to installation on Windows

Binary builds of the extension can be found at
<a href="http://cairographics.org/download/" class="link external">» http://cairographics.org/download/</a>.
Download the correct zip file, place php\_cairo.dll in the extensions
directory, and enable it via the php.ini file in use. Please be sure the
PHP minor version (5.2, 5.3) match, the thread safety (Thread Safe TS or
Non-Thread Safe NTS), the architecture (x86 or x64), and the compiler
version (VC6 or VC9) match or the extension will not load.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

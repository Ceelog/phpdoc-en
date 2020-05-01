Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/ming/setup.html#Requirements)
-   [Installation](/ming/setup.html#Installation)
-   [Runtime Configuration](/ming/setup.html#Runtime%20Configuration)
-   [Resource Types](/ming/setup.html#Resource%20Types)

Requirements
------------

To use Ming with PHP, you first need to build and install the Ming
library. Source code and installation instructions are available at the
Ming home page:
<a href="http://www.libming.org/" class="link external">» http://www.libming.org/</a>
along with examples, a small tutorial, and the latest news.

Download the ming archive. Unpack the archive. Go in the Ming directory.
make. make install.

This will build `libming.so` and install it into `/usr/lib/`, and copy
`ming.h` into `/usr/include/`. Edit the *PREFIX=* line in the `Makefile`
to change the installation directory.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/ming" class="link external">» https://pecl.php.net/package/ming</a>.

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 5.3.0

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

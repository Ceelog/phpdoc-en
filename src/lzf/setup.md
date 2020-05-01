Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/lzf/setup.html#Requirements)
-   [Installation](/lzf/setup.html#Installation)
-   [Runtime Configuration](/lzf/setup.html#Runtime%20Configuration)
-   [Resource Types](/lzf/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP. Information for installing this PECL
extension may be found in the manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/lzf" class="link external">» https://pecl.php.net/package/lzf</a>.

In order to use these functions you must compile PHP with lzf support by
using the **--with-lzf\[=DIR\]** configure option. You may also pass
**--enable-lzf-better-compression** to optimize LZF for space rather
than speed.

Windows users will enable `php_lzf.dll` inside of `php.ini` in order to
use these functions. A DLL for this PECL extension is currently
unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/crack/setup.html#Requirements)
-   [Installation](/crack/setup.html#Installation)
-   [Runtime Configuration](/crack/setup.html#Runtime%20Configuration)
-   [Resource Types](/crack/setup.html#Resource%20Types)

Requirements
------------

More information regarding CrackLib along with the library can be found
at
<a href="http://sourceforge.net/projects/cracklib" class="link external">» http://sourceforge.net/projects/cracklib</a>.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP. Information for installing this PECL
extension may be found in the manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/crack" class="link external">» https://pecl.php.net/package/crack</a>.

In order to use these functions you must compile PHP with Crack support
by using the **--with-crack\[=DIR\]** configuration option.

Windows users will enable `php_crack.dll` inside of `php.ini` in order
to use these functions. A DLL for this PECL extension is currently
unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

The CrackLib extension defines a dictionary resource identifier returned
by <span class="function">crack\_opendict</span>.

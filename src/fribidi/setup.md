Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/fribidi/setup.html#Requirements)
-   [Installation](/fribidi/setup.html#Installation)
-   [Runtime Configuration](/fribidi/setup.html#Runtime%20Configuration)
-   [Resource Types](/fribidi/setup.html#Resource%20Types)

Requirements
------------

You must download and install the
<a href="http://fribidi.org/" class="link external">» FriBiDi package</a>.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP. Information for installing this PECL
extension may be found in the manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/fribidi" class="link external">» https://pecl.php.net/package/fribidi</a>.

In order to use these functions you must compile PHP with Fribidi
support by using the **--with-fribidi\[=DIR\]** configure option.

Windows users will enable `php_fribidi.dll` inside of `php.ini` in order
to use these functions. A DLL for this PECL extension is currently
unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

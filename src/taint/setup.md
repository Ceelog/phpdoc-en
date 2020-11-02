Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/taint/setup.html#Requirements)
-   [Installation](/taint/setup.html#Installation)
-   [Runtime Configuration](/taint/setup.html#Runtime%20Configuration)
-   [Resource Types](/taint/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/taint" class="link external">» https://pecl.php.net/package/taint</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                            | Default    | Changeable       | Changelog |
|-----------------------------------------------------------------|------------|------------------|-----------|
| <a href="/taint/setup.html#" class="link">taint.enable</a>      | 0          | PHP\_INI\_SYSTEM |           |
| <a href="/taint/setup.html#" class="link">taint.error_level</a> | E\_WARNING | PHP\_INI\_ALL    |           |

Here's a short explanation of the configuration directives.

`taint.enable` <span class="type">int</span>  
Whether enable the taint.

`taint.error_level` <span class="type">int</span>  
the error type which taint will report as when taint find a tainted
string.

Resource Types
--------------

This extension has no resource types defined.

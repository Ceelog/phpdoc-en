Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/openal/setup.html#Requirements)
-   [Installation](/openal/setup.html#Installation)
-   [Runtime Configuration](/openal/setup.html#Runtime%20Configuration)
-   [Resource Types](/openal/setup.html#Resource%20Types)

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
<a href="https://pecl.php.net/package/openal" class="link external">» https://pecl.php.net/package/openal</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension defines four resource types: *Open AL(Device)* - Returned
by <span class="function">openal\_device\_open</span>, *Open
AL(Context)* - Returned by <span
class="function">openal\_context\_create</span>, *Open AL(Buffer)* -
Returned by <span class="function">openal\_buffer\_create</span>, and
*Open AL(Source)* - Returned by <span
class="function">openal\_source\_create</span>.

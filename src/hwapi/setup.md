Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/hwapi/setup.html#Requirements)
-   [Installation](/hwapi/setup.html#Installation)
-   [Runtime Configuration](/hwapi/setup.html#Runtime%20Configuration)
-   [Resource Types](/hwapi/setup.html#Resource%20Types)

Requirements
------------

Since 2001 there is a Hyperwave SDK available. It supports Java,
JavaScript and C++. This PHP Extension is based on the C++ interface. In
order to activate the hwapi support in PHP you will have to install the
Hyperwave SDK first.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/hwapi" class="link external">» https://pecl.php.net/package/hwapi</a>.

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 5.2.0

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                    | Default | Changeable       | Changelog |
|-------------------------|---------|------------------|-----------|
| hwapi.allow\_persistent | "0"     | PHP\_INI\_SYSTEM |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Resource Types
--------------

This extension has no resource types defined.

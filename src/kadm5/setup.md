Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/kadm5/setup.html#Requirements)
-   [Installation](/kadm5/setup.html#Installation)
-   [Runtime Configuration](/kadm5/setup.html#Runtime%20Configuration)
-   [Resource Types](/kadm5/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/kadm5" class="link external">» https://pecl.php.net/package/kadm5</a>.

> **Note**:
>
> If this option is used without specifying the path to KADM5, PHP will
> use the built-in KADM5 client libraries. Users who run other
> applications that use KADM5 (for example, running PHP 4 and PHP 5 as
> concurrent apache modules, or auth-kadm5) should always specify the
> path to KADM5: *--with-kadm5=/path/to/kadm5*. This will force PHP to
> use the client libraries installed by KADM5, avoiding any conflicts.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension defines a KADM5 handle returned by <span
class="function">kadm5\_init\_with\_password</span>.

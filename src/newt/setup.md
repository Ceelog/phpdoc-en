Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/newt/setup.html#Requirements)
-   [Installation](/newt/setup.html#Installation)
-   [Runtime Configuration](/newt/setup.html#Runtime%20Configuration)
-   [Resource Types](/newt/setup.html#Resource%20Types)

Requirements
------------

This module uses the functions of the RedHat Newt library. You need
libnewt version \>= 0.51.0.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP. Information for installing this PECL
extension may be found in the manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/newt" class="link external">» https://pecl.php.net/package/newt</a>.

In order to use these functions you must compile CGI or CLI PHP with
newt support by using the **--with-newt\[=DIR\]** configure option.

> **Note**:
>
> This extension is not available for Windows platform.
>
> You may need also *curses* and *slang* libraries, in order to compile
> this extension. To specify locations of these libraries, use the
> following configuration options:
> *--with-curses-dir=/path/to/libcurses*
> *--with-slang-dir=/path/to/libslang*

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension uses two resource types: "newt component" and "newt
grid".

Resource type "newt component" is returned by functions, which create
common newt widgets (for example: <span
class="function">newt\_button</span>)

Resource type "newt grid" is a special link identifier for components,
returned by newt grid factory functions (for example: <span
class="function">newt\_create\_grid</span>)

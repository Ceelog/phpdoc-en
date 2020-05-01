Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mnogosearch/setup.html#Requirements)
-   [Installation](/mnogosearch/setup.html#Installation)
-   [Runtime
    Configuration](/mnogosearch/setup.html#Runtime%20Configuration)
-   [Resource Types](/mnogosearch/setup.html#Resource%20Types)

Requirements
------------

Download mnoGosearch from
<a href="http://www.mnogosearch.org/" class="link external">» http://www.mnogosearch.org/</a>
and install it on your system. You need at least version 3.1.10 of
mnoGoSearch installed to use these functions.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/mnogosearch" class="link external">» https://pecl.php.net/package/mnogosearch</a>.

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 5.1.0

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

> **Note**:
>
> PHP contains built-in MySQL access library, which can be used to
> access MySQL. It is known that mnoGoSearch is not compatible with this
> built-in library and can work only with generic MySQL libraries. Thus,
> if you use mnoGoSearch with MySQL, during PHP configuration you have
> to indicate the directory of your MySQL installation, that was used
> during mnoGoSearch configuration, i.e. for example:
> **--with-mnogosearch --with-mysql=/usr**.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

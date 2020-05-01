Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/regex/setup.html#Requirements)
-   [Installation](/regex/setup.html#Installation)
-   [Runtime Configuration](/regex/setup.html#Runtime%20Configuration)
-   [Resource Types](/regex/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

PHP 7
-----

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/regex" class="link external">» https://pecl.php.net/package/regex</a>.

PHP 5
-----

**Warning**

Do not change the TYPE unless you know what you are doing.

To enable regexp support configure PHP **--with-regex\[=TYPE\]**. TYPE
can be one of *system*, *apache*, *php*. The default value is *php*.

The Windows version of PHP has built-in support for this extension. You
do not need to load any additional extensions in order to use these
functions.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

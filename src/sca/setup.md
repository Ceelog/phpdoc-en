Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/sca/setup.html#Requirements)
-   [Installation](/sca/setup.html#Installation)
-   [Runtime Configuration](/sca/setup.html#Runtime%20Configuration)
-   [Resource Types](/sca/setup.html#Resource%20Types)

Requirements
------------

If you want to use SCA to consume or produce Web services then you need
PHP 5.2.0 or later, built with the soap extension enabled. If you just
want to use local components, and do not wish to use the Web service
bindings, then this version of SCA for PHP will also run with PHP 5.1.6.

SCA is packaged along with SDO in one combined package on PECL. See
http://www.php.net/sdo\#sdo.installation for installing the SCA\_SDO
package from PECL. The SCA code must be on the include path of your PHP
installation, for example if it is installed as /usr/local/lib/php/SCA,
the include\_path directive must include /usr/local/lib/php

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/sca" class="link external">» https://pecl.php.net/package/sca</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

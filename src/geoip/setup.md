Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/geoip/setup.html#Requirements)
-   [Installation](/geoip/setup.html#Installation)
-   [Runtime Configuration](/geoip/setup.html#Runtime%20Configuration)
-   [Resource Types](/geoip/setup.html#Resource%20Types)

Requirements
------------

This extension requires the GeoIP C library version 1.4.0 or higher to
be installed. You can grab the latest version from
<a href="http://www.maxmind.com/app/c" class="link external">» http://www.maxmind.com/app/c</a>
and compile it yourself.

By default, you will only have access to the Free GeoIP Country or
GeoLite City databases. While this module can work with other types of
database, you must buy a commercial license from
<a href="http://www.maxmind.com/" class="link external">» Maxmind</a>.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/geoip" class="link external">» https://pecl.php.net/package/geoip</a>.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                 | Default | Changeable    | Changelog |
|----------------------------------------------------------------------|---------|---------------|-----------|
| <a href="/geoip/setup.html#" class="link">geoip.custom_directory</a> | ""      | PHP\_INI\_ALL |           |

Here's a short explanation of the configuration directives.

`geoip.custom_directory` <span class="type">string</span>  
Empty by default, but can be set to force a different database path than
the one compiled in the library.

Resource Types
--------------

This extension has no resource types defined.

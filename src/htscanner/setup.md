Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/htscanner/setup.html#Requirements)
-   [Installation](/htscanner/setup.html#Installation)
-   [Runtime
    Configuration](/htscanner/setup.html#Runtime%20Configuration)
-   [Resource Types](/htscanner/setup.html#Resource%20Types)

Requirements
------------

PHP version 5.2.0 or greater.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/htscanner" class="link external">» https://pecl.php.net/package/htscanner</a>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                        | Default      | Changeable       | Changelog |
|-----------------------------------------------------------------------------|--------------|------------------|-----------|
| <a href="/htscanner/setup.html#" class="link">htscanner.config_file</a>     | ".htscanner" | PHP\_INI\_SYSTEM |           |
| <a href="/htscanner/setup.html#" class="link">htscanner.default_docroot</a> | "/"          | PHP\_INI\_SYSTEM |           |
| <a href="/htscanner/setup.html#" class="link">htscanner.default_ttl</a>     | "300"        | PHP\_INI\_SYSTEM |           |
| <a href="/htscanner/setup.html#" class="link">htscanner.stop_on_error</a>   | "Off"        | PHP\_INI\_SYSTEM |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`htscanner.config_file` <span class="type">string</span>  
Filename to use as configuration file.

`htscanner.default_docroot` <span class="type">string</span>  
Default document root.

`htscanner.default_ttl` <span class="type">int</span>  
Cache time out for the configuration data, in seconds.

`htscanner.stop_on_error` <span class="type">int</span>  
Stop on error (parse error, cannot set an ini setting).

Resource Types
--------------

This extension has no resource types defined.

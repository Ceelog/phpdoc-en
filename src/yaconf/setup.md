Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/yaconf/setup.html#Requirements)
-   [Installation](/yaconf/setup.html#Installation)
-   [Runtime Configuration](/yaconf/setup.html#Runtime%20Configuration)
-   [Resource Types](/yaconf/setup.html#Resource%20Types)

Requirements
------------

Yaconf requires PHP 7.0 and above.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/yaconf" class="link external">» https://pecl.php.net/package/yaconf</a>.

Windows binaries (DLL files) for this PECL extension are available from
the PECL website.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                              | Default    | Changeable       | Changelog |
|-------------------------------------------------------------------|------------|------------------|-----------|
| <a href="/yaconf/setup.html#" class="link">yaconf.check_delay</a> | 300        | PHP\_INI\_SYSTEM |           |
| <a href="/yaconf/setup.html#" class="link">yaconf.directory</a>   | /tmp/conf/ | PHP\_INI\_SYSTEM |           |

Here's a short explanation of the configuration directives.

`yaconf.check_delay` <span class="type">integer</span>  
In which interval Yaconf will detect ini file's change(by directory's
mtime), if it is set to zero, you have to restart php to reloading
configurations.

`yaconf.directory` <span class="type">string</span>  
Path to directory which all INI configuration files are placed in.

Resource Types
--------------

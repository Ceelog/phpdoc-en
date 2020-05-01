Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/imagick/setup.html#Requirements)
-   [Installation](/imagick/setup.html#Installation)
-   [Runtime Configuration](/imagick/setup.html#Runtime%20Configuration)
-   [Resource Types](/imagick/setup.html#Resource%20Types)

Requirements
------------

Installation requirements on Windows
------------------------------------

Version information does not differ from that above. There are binaries
available from http://www.imagemagick.org/ so that you can load this
extension on *Windows* without need for a compiler.

Installation requirements on other platforms
--------------------------------------------

PHP \>= 5.1.3 and ImageMagick \>= 6.2.4 is required. The amount of file
formats supported by Imagick depends entirely upon the amount of formats
supported by your ImageMagick installation. For example, Imagemagick
requires ghostscript to conduct PDF operations.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/imagick" class="link external">» https://pecl.php.net/package/imagick</a>.

> **Note**: <span class="simpara">The official name of this extension is
> *imagick*.</span>

Windows users can download prebuilt DLL from the
<a href="https://windows.php.net/downloads/pecl/releases/imagick" class="link external">» PECL</a>
website.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                       | Default     | Changeable       | Changelog                     |
|----------------------------------------------------------------------------|-------------|------------------|-------------------------------|
| <a href="/imagick/setup.html#" class="link">imagick.locale_fix</a>         | **`FALSE`** | PHP\_INI\_ALL    | Available since Imagick 2.1.0 |
| <a href="/imagick/setup.html#" class="link">imagick.progress_monitor</a>   | **`FALSE`** | PHP\_INI\_SYSTEM | Available since Imagick 2.2.2 |
| <a href="/imagick/setup.html#" class="link">imagick.skip_version_check</a> | **`FALSE`** | PHP\_INI\_SYSTEM | Available since Imagick 3.3.0 |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`imagick.locale_fix` <span class="type">boolean</span>  
Fixes a drawing bug with locales that use '*,*' as float separators.

`imagick.progress_monitor` <span class="type">boolean</span>  
Used to enable the image progress monitor.

`imagick.skip_version_check` <span class="type">boolean</span>  
When Imagick is loaded, it checks the version number of ImageMagick that
it was compiled against, with the version number that is currently being
used and will give a warning if they don't match. This warning can be
suppressed by enabling this ini setting.

Using a version of Imagick that was compiled against a different version
of ImageMagick than the one being used is not recommended. Although it
may appear to work, it can lead to random crashes or other undefined
behaviour.

Resource Types
--------------

This extension has no resource types defined.

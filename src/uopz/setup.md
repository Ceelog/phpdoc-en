Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/uopz/setup.html#Requirements)
-   [Installation](/uopz/setup.html#Installation)
-   [Runtime Configuration](/uopz/setup.html#Runtime%20Configuration)
-   [Resource Types](/uopz/setup.html#Resource%20Types)

Requirements
------------

uopz 2 requires PHP 5.4+. uopz 5.0 requires PHP 7. As of uopz 5.1, PHP
7.1+ is required.

Installation
------------

uopz releases are hosted by PECL and the source code by
<a href="https://github.com/krakjoe/uopz" class="link external">» github</a>,
the easiest route to installation is the normal PECL route:
<a href="https://pecl.php.net/package/uopz" class="link external">» https://pecl.php.net/package/uopz</a>.

Windows users can download prebuilt release binaries from the
<a href="https://windows.php.net/downloads/pecl/releases/uopz" class="link external">» PECL</a>
website.

As of uopz 5.0.0 the extension must be loaded as
<a href="/ini/core.html#ini.extension" class="link">extension</a>.
Before this version it must be loaded as
<a href="/ini/core.html#ini.zend-extension" class="link">zend_extension</a>.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                      | Default | Changeable       | Changelog                  |
|-----------------------------------------------------------|---------|------------------|----------------------------|
| <a href="/uopz/setup.html#" class="link">uopz.disable</a> | "0"     | PHP\_INI\_SYSTEM | Available as of uopz 5.0.2 |
| <a href="/uopz/setup.html#" class="link">uopz.exit</a>    | "0"     | PHP\_INI\_SYSTEM | Available as of uopz 6.0.1 |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`uopz.disable` <span class="type">bool</span>  
If enabled, uopz should stop having any effect on the engine.

`uopz.exit` <span class="type">bool</span>  
Whether to allow the execution of exit opcodes or not. This setting can
be overridden during runtime by calling <span
class="function">uopz\_allow\_exit</span>.

Resource Types
--------------

This extension has no resource types defined.

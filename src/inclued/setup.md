Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/inclued/setup.html#Requirements)
-   [Installation](/inclued/setup.html#Installation)
-   [Runtime Configuration](/inclued/setup.html#Runtime%20Configuration)
-   [Resource Types](/inclued/setup.html#Resource%20Types)

Requirements
------------

PHP version 5.1.0 or greater.

The included `gengraph.php` file utilizes the
<a href="http://www.graphviz.org/" class="link external">» graphviz</a>
library, however, this is not required.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/inclued" class="link external">» https://pecl.php.net/package/inclued</a>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                            | Default    | Changeable       | Changelog |
|-----------------------------------------------------------------|------------|------------------|-----------|
| <a href="/inclued/setup.html#" class="link">inclued.enabled</a> | Off        | PHP\_INI\_SYSTEM |           |
| <a href="/inclued/setup.html#" class="link">inclued.dumpdir</a> | **`NULL`** | PHP\_INI\_SYSTEM |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`inclued.enabled` <span class="type">bool</span>  
Whether or not to enable inclued.

`inclued.dumpdir` <span class="type">string</span>  
Location (path) to the directory that stores inclued files. If set, each
PHP request will create a file. These files are serialized versions of
what <span class="function">inclued\_get\_data</span> would produce, so
may be unserialized with <span class="function">unserialize</span>.

**Caution**
Because every request creates a file, this directory may fill up fast!

Resource Types
--------------

This extension has no resource types defined.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/yac/setup.html#Requirements)
-   [Installation](/yac/setup.html#Installation)
-   [Runtime Configuration](/yac/setup.html#Runtime%20Configuration)
-   [Resource Types](/yac/setup.html#Resource%20Types)

Requirements
------------

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/yac" class="link external">» https://pecl.php.net/package/yac</a>.

Windows binaries (DLL files) for this PECL extension are available from
the PECL website.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                               | Default | Changeable       | Changelog |
|--------------------------------------------------------------------|---------|------------------|-----------|
| <a href="/yac/setup.html#" class="link">yac.compress_threshold</a> | -1      | PHP\_INI\_SYSTEM |           |
| <a href="/yac/setup.html#" class="link">yac.debug</a>              | 0       | PHP\_INI\_ALL    |           |
| <a href="/yac/setup.html#" class="link">yac.enable</a>             | 1       | PHP\_INI\_SYSTEM |           |
| <a href="/yac/setup.html#" class="link">yac.enable_cli</a>         | 0       | PHP\_INI\_SYSTEM |           |
| <a href="/yac/setup.html#" class="link">yac.keys_memory_size</a>   | 4M      | PHP\_INI\_SYSTEM |           |
| <a href="/yac/setup.html#" class="link">yac.serializer</a>         | php     | PHP\_INI\_SYSTEM |           |
| <a href="/yac/setup.html#" class="link">yac.values_memory_size</a> | 64M     | PHP\_INI\_SYSTEM |           |

Here's a short explanation of the configuration directives.

`yac.compress_threshold` <span class="type">int</span>  

`yac.debug` <span class="type">int</span>  

`yac.enable` <span class="type">int</span>  

`yac.enable_cli` <span class="type">int</span>  

`yac.keys_memory_size` <span class="type">string</span>  

`yac.serializer` <span class="type">string</span>  

`yac.values_memory_size` <span class="type">string</span>  

Resource Types
--------------

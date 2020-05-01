Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/yar/setup.html#Requirements)
-   [Installation](/yar/setup.html#Installation)
-   [Runtime Configuration](/yar/setup.html#Runtime%20Configuration)
-   [Resource Types](/yar/setup.html#Resource%20Types)

Requirements
------------

if you want to use msgpack as packager, you need compile Yar by your
self with ./configure --enable-msgpack

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/yar" class="link external">» https://pecl.php.net/package/yar</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                            | Default | Changeable       | Changelog |
|-----------------------------------------------------------------|---------|------------------|-----------|
| <a href="/yar/setup.html#" class="link">yar.packager</a>        | php     | PHP\_INI\_SYSTEM |           |
| <a href="/yar/setup.html#" class="link">yar.debug</a>           | Off     | PHP\_INI\_ALL    |           |
| <a href="/yar/setup.html#" class="link">yar.connect_timeout</a> | 1000    | PHP\_INI\_ALL    |           |
| <a href="/yar/setup.html#" class="link">yar.timeout</a>         | 5000    | PHP\_INI\_ALL    |           |
| <a href="/yar/setup.html#" class="link">yar.expose_info</a>     | On      | PHP\_INI\_SYSTEM |           |

Here's a short explanation of the configuration directives.

`yar.packager` <span class="type">string</span>  
it could be php, json, and msgpack(require built with msgpack support)

`yar.debug` <span class="type">string</span>  

`yar.connect_timeout` <span class="type">integer</span>  
timeout in ms

`yar.timeout` <span class="type">integer</span>  
timeout in ms

`yar.expose_info` <span class="type">bool</span>  
whether expose the service info(when access the server via GET)

Resource Types
--------------

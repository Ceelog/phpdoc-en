Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/v8js/setup.html#Requirements)
-   [Installation](/v8js/setup.html#Installation)
-   [Runtime Configuration](/v8js/setup.html#Runtime%20Configuration)
-   [Resource Types](/v8js/setup.html#Resource%20Types)

Requirements
------------

PHP 5.3.3+ and V8 library and headers installed in proper paths.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/v8js" class="link external">» https://pecl.php.net/package/v8js</a>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                    | Default | Changeable    | Changelog |
|-------------------------------------------------------------------------|---------|---------------|-----------|
| <a href="/v8js/setup.html#" class="link">v8js.max_disposed_contexts</a> | 25      | PHP\_INI\_ALL |           |
| <a href="/v8js/setup.html#" class="link">v8js.flags</a>                 |         | PHP\_INI\_ALL |           |

Here's a short explanation of the configuration directives.

`v8js.max_disposed_contexts` <span class="type">integer</span>  
Sets limit for disposed contexts before forcing V8 to do garbage
collection.

`v8js.flags` <span class="type">string</span>  
Sets V8 command line flags. The list of available flags can be obtained
in CLI mode by setting this parameter to *--help*. Example:

    $ php -r 'ini_set("v8js.flags", "--help"); new V8Js;' | less

> **Note**:
>
> For these flags to be effective in runtime the ini\_set() call has to
> be done before any V8Js objects are instantiated!

Resource Types
--------------

This extension has no resource types defined.

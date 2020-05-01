Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/apd/setup.html#Requirements)
-   [Installation](/apd/setup.html#Installation)
-   [Building on Win32](/apd/setup.html#Building%20on%20Win32)
-   [Runtime Configuration](/apd/setup.html#Runtime%20Configuration)
-   [Resource Types](/apd/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/apd" class="link external">» https://pecl.php.net/package/apd</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

In your INI file, add the following lines:

``` php.ini
zend_extension = /absolute/path/to/apd.so
apd.dumpdir = /absolute/path/to/trace/directory
apd.statement_tracing = 0
```

Depending on your PHP build, the zend\_extension directive can be one of
the following:

``` script
zend_extension              (non ZTS, non debug build)
zend_extension_ts           (    ZTS, non debug build)
zend_extension_debug        (non ZTS,     debug build)
zend_extension_debug_ts     (    ZTS,     debug build)
```

Building on Win32
-----------------

To build APD under Windows you need a working PHP compilation
environment as described on http://php.net/ -- basically, it requires
you to have Microsoft Visual C++, win32build.zip, bison/flex, and some
know how to get it to work. Also ensure that adp.dsp has DOS line
endings; if it has unix line endings, Microsoft Visual C++ will complain
about it.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                              | Default | Changeable    | Changelog                |
|-------------------------------------------------------------------|---------|---------------|--------------------------|
| <a href="/apd/setup.html#" class="link">apd.dumpdir</a>           | NULL    | PHP\_INI\_ALL |                          |
| <a href="/apd/setup.html#" class="link">apd.statement_tracing</a> | "0"     | PHP\_INI\_ALL | Available since apd 0.9. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`apd.dumpdir` <span class="type">string</span>  
Sets the directory in which APD writes profile dump files. You can
specify an absolute path or a relative path.

You can specify a different directory as an argument to <span
class="function">apd\_set\_pprof\_trace</span>.

`apd.statement_tracing` <span class="type">boolean</span>  
Specfies whether or not to do per-line tracings. Turning this on (1)
will impact the performance of your application.

Resource Types
--------------

This extension has no resource types defined.

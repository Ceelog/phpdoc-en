Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/xhprof/setup.html#Requirements)
-   [Installation](/xhprof/setup.html#Installation)
-   [Runtime Configuration](/xhprof/setup.html#Runtime%20Configuration)
-   [Resource Types](/xhprof/setup.html#Resource%20Types)

Requirements
------------

Although not required, xhprof includes an interface that's written in
PHP. It's used to save and display the profiled data in a usable way,
where viewing is done via a web browser. So, a PHP enabled web server
will likely make the xhprof experience more useful.

There's also a fork of the GUI interface at
<a href="http://github.com/preinheimer/xhprof" class="link external">» http://github.com/preinheimer/xhprof</a>

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/xhprof" class="link external">» https://pecl.php.net/package/xhprof</a>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                             | Default | Changeable        | Changelog |
|------------------------------------------------------------------|---------|-------------------|-----------|
| <a href="/xhprof/setup.html#" class="link">xhprof.output_dir</a> | ""      | **`PHP_INI_ALL`** |           |

Here's a short explanation of the configuration directives.

`xhprof.output_dir` <span class="type">string</span>  
Directory used by the default implementation of the iXHProfRuns
interface (namely, the XHProfRuns\_Default class) for storing XHProf
runs.

Resource Types
--------------

This extension has no resource types defined.

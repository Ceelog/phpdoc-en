Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/solr/setup.html#Requirements)
-   [Installation](/solr/setup.html#Installation)
-   [Runtime Configuration](/solr/setup.html#Runtime%20Configuration)
-   [Resource Types](/solr/setup.html#Resource%20Types)

Requirements
------------

PHP version 5.2.11 or later is required.

The libxml and curl extensions must also be enabled for the Apache Solr
extension to be available.

libxml2 2.6.31 or later is required.

libcurl 7.18.0 or later is also required.

The above library versions are required and attempting to hack the code
to make it compile is strongly discouraged. It will fail, possibly with
errors that could be hard to debug

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/solr" class="link external">» https://pecl.php.net/package/solr</a>.

For help and support, please visit the extension google group.
<a href="https://groups.google.com/forum/#!forum/php-solr" class="link external">» Apache Solr PHP Extension</a>

Windows binaries (DLL files) for this PECL extension are available from
the PECL website.

> **Note**:
>
> The solr module can be compiled in debug mode by passing the
> --enable-solr-debug flag to configure
>
> When building manually, be sure to include curl and libxml support
> within the build.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/xmlwriter/setup.html#Requirements)
-   [Installation](/xmlwriter/setup.html#Installation)
-   [Runtime
    Configuration](/xmlwriter/setup.html#Runtime%20Configuration)
-   [Resource Types](/xmlwriter/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

Installation
------------

The XMLWriter extension was initially a PECL extension for PHP 5. It was
later added to the PHP source (bundled) as of PHP 5.1.2. This extension
is enabled by default.

This extension is enabled by default. It may be disabled by using the
following option at compile time: **--disable-xmlwriter**

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

Prior to PHP 8.0.0, there was one resource type used by the procedural
version of the XMLWriter extension: returned by <span
class="function">xmlwriter\_open\_memory</span> or <span
class="function">xmlwriter\_open\_uri</span>.

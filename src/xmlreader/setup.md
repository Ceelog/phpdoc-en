Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/xmlreader/setup.html#Requirements)
-   [Installation](/xmlreader/setup.html#Installation)
-   [Runtime
    Configuration](/xmlreader/setup.html#Runtime%20Configuration)
-   [Resource Types](/xmlreader/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

Installation
------------

The XMLReader extension was initially a PECL extension for PHP 5. It was
later moved to the PHP source (bundled) as of PHP 5.1.0, and later
enabled by default as of PHP 5.1.2.

This extension is enabled by default. It may be disabled by using the
following option at compile time: **--disable-xmlreader**

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

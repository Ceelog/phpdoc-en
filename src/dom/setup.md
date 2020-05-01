Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/dom/setup.html#Requirements)
-   [Installation](/dom/setup.html#Installation)
-   [Runtime Configuration](/dom/setup.html#Runtime%20Configuration)
-   [Resource Types](/dom/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

Installation
------------

This extension is enabled by default. It may be disabled by using the
following option at compile time: **--disable-dom**

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

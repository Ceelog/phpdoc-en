Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/simplexml/setup.html#Requirements)
-   [Installation](/simplexml/setup.html#Installation)
-   [Runtime
    Configuration](/simplexml/setup.html#Runtime%20Configuration)
-   [Resource Types](/simplexml/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

The SimpleXML extension requires PHP 5.

Installation
------------

This extension is enabled by default. It may be disabled by using the
following option at compile time: **--disable-simplexml**

Note: Before PHP 5.1.2, **--enable-simplexml** is required to enable
this extension.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

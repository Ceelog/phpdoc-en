Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/wddx/setup.html#Requirements)
-   [Installation](/wddx/setup.html#Installation)
-   [Runtime Configuration](/wddx/setup.html#Runtime%20Configuration)
-   [Resource Types](/wddx/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

In order to use WDDX, you will need to install the expat library (which
comes with Apache 1.3.7 or higher).

Installation
------------

After installing the required expat library, compile PHP with
**--enable-wddx**, and use **--with-libexpat-dir** for expat.

The Windows version of PHP has built-in support for this extension. You
do not need to load any additional extensions in order to use these
functions.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension defines a WDDX packet identifier returned by <span
class="function">wddx\_packet\_start</span>.

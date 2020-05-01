Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/xsl/setup.html#Requirements)
-   [Installation](/xsl/setup.html#Installation)
-   [Runtime Configuration](/xsl/setup.html#Runtime%20Configuration)
-   [Resource Types](/xsl/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

This extension uses <span class="productname">libxslt</span> which can
be found at
<a href="http://xmlsoft.org/XSLT/" class="link external">» http://xmlsoft.org/XSLT/</a>.
libxslt version 1.1.0 or greater is required.

Installation
------------

PHP 5 includes the XSL extension by default and can be enabled by adding
the argument **--with-xsl\[=DIR\]** to your configure line (*DIR* being
the libxslt installation directory).

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

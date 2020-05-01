Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mhash/setup.html#Requirements)
-   [Installation](/mhash/setup.html#Installation)
-   [Runtime Configuration](/mhash/setup.html#Runtime%20Configuration)
-   [Resource Types](/mhash/setup.html#Resource%20Types)

Requirements
------------

To use it, download the mhash distribution from
<a href="http://mhash.sourceforge.net/" class="link external">» its web site</a>
and follow the included installation instructions.

Installation
------------

You need to compile PHP with the **--with-mhash\[=DIR\]** parameter to
enable this extension. DIR is the mhash installation directory.

As of PHP 5.3.0, the mhash extension is emulated thru the
<a href="/ref/hash.html" class="link">Hash</a> extension. This makes the
mhash installation directory have no effect, and requires the hash
extension enabled to make the mhash support available.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

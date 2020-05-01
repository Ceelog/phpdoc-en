Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/libxml/setup.html#Requirements)
-   [Installation](/libxml/setup.html#Installation)
-   [Runtime Configuration](/libxml/setup.html#Runtime%20Configuration)
-   [Resource Types](/libxml/setup.html#Resource%20Types)

Requirements
------------

This extension requires
<a href="http://www.xmlsoft.org/" class="link external">» libxml</a> \>=
2.6.0.

Installation
------------

The libxml extension is enabled by default, although it may be disabled
with **--disable-libxml**.

The optional **--with-libxml-dir** directive is used to specify the
location of *libxml* on the system that PHP is being compiled on,
otherwise only the default locations are scanned. The *configure*
process checks for libxml (specifically, *xml2-config*) in the following
order:

1.  The location (\[DIR\]) specified with **--with-libxml-dir**
    (\[DIR\]=`/bin/xml2-config`)

2.  `/usr/local/bin/xml2-config`

3.  `/usr/bin/xml2-config`

If *configure* cannot find `xml2-config` in the directory specified by
**--with-libxml-dir**, then it'll continue on and check the default
locations.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

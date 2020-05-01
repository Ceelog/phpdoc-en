Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/gupnp/setup.html#Requirements)
-   [Installation](/gupnp/setup.html#Installation)
-   [Runtime Configuration](/gupnp/setup.html#Runtime%20Configuration)
-   [Resource Types](/gupnp/setup.html#Resource%20Types)

Requirements
------------

In order to use PECL/Gupnp functions you need to install the
<a href="http://www.gupnp.org/" class="link external">» gUPnP library</a>
version 0.12.7 or greater. It also requires glib-2.0, gssdp-1.0,
libsoup-2.4 or greater for all of them.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/gupnp" class="link external">» https://pecl.php.net/package/gupnp</a>

> **Note**: <span class="simpara"> If `./configure` is having trouble
> finding the libgupnp files (for example, it was installed into a
> custom prefix directory), use
> **`./configure      --with-gupnp=$PREFIX`**, where $PREFIX is
> installation prefix of libgupnp. </span>

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

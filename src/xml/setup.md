Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/xml/setup.html#Requirements)
-   [Installation](/xml/setup.html#Installation)
-   [Runtime Configuration](/xml/setup.html#Runtime%20Configuration)
-   [Resource Types](/xml/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

This extension uses an <span class="productname">expat compat
layer</span> by default. It can use also <span
class="productname">expat</span>, which can be found at
<a href="http://www.jclark.com/xml/expat.html" class="link external">» http://www.jclark.com/xml/expat.html</a>.
The Makefile that comes with <span class="productname">expat</span> does
not build a library by default, you can use this make rule for that:

``` makefile
libexpat.a: $(OBJS)
    ar -rc $@ $(OBJS)
    ranlib $@
```

A source RPM package of expat can be found at
<a href="http://sourceforge.net/projects/expat/" class="link external">» http://sourceforge.net/projects/expat/</a>.

Installation
------------

This extension is enabled by default. It may be disabled by using the
following option at compile time: **--disable-xml**

These functions are enabled by default, using the bundled expat library.
You can disable XML support with **--disable-xml**. If you compile PHP
as a module for Apache 1.3.9 or later, PHP will automatically use the
bundled <span class="productname">expat</span> library from Apache. If
you don't want to use the bundled expat library, configure PHP with
**--with-expat-dir=DIR**, where DIR should point to the base
installation directory of expat.

The Windows version of PHP has built-in support for this extension. You
do not need to load any additional extensions in order to use these
functions.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

The *xml* resource as returned by <span
class="function">xml\_parser\_create</span> and <span
class="function">xml\_parser\_create\_ns</span> references an xml parser
instance to be used with the functions provided by this extension.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/xmlrpc/setup.html#Requirements)
-   [Installation](/xmlrpc/setup.html#Installation)
-   [Runtime Configuration](/xmlrpc/setup.html#Runtime%20Configuration)
-   [Resource Types](/xmlrpc/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="/book/libxml.html" class="link">libxml</a> PHP extension. This
means passing the **--with-libxml**, or prior to PHP 7.4 the
**--enable-libxml**, configuration flag, although this is implicitly
accomplished because libxml is enabled by default.

Installation
------------

XML-RPC support in PHP is not enabled by default. You will need to use
the **--with-xmlrpc\[=DIR\]** configuration option when compiling PHP to
enable XML-RPC support.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension defines a XML-RPC server resource returned by <span
class="function">xmlrpc\_server\_create</span>.

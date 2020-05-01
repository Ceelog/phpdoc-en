Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/hash/setup.html#Requirements)
-   [Installation](/hash/setup.html#Installation)
-   [Runtime Configuration](/hash/setup.html#Runtime%20Configuration)
-   [Resource Types](/hash/setup.html#Resource%20Types)

Requirements
------------

There is no installation needed to use these functions; they are part of
the PHP core.

Installation
------------

As of PHP 5.1.2, the Hash extension is bundled and compiled into PHP by
default.

It may be explicitly disabled by using the --disable-hash switch to
configure. Earlier versions of PHP may incorporate the Hash extension by
installing the
<a href="https://pecl.php.net/package/hash" class="link external">» PECL module</a>.

As of PHP 7.4.0, the Hash extension is a core PHP extension, so it is
always enabled.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension defines a Hashing Context resource returned by <span
class="function">hash\_init</span>.

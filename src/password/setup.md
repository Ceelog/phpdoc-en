Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/password/setup.html#Requirements)
-   [Installation](/password/setup.html#Installation)
-   [Runtime
    Configuration](/password/setup.html#Runtime%20Configuration)
-   [Resource Types](/password/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

For Argon2 password hashing,
<a href="https://github.com/P-H-C/phc-winner-argon2" class="link external">» libargon2</a>
is required, though. As of PHP 7.3.0, libargon2 version 20161029 or
later is required.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

To enable Argon2 password hashing, however, PHP must be build with
libargon2 support using the **--with-password-argon2\[=DIR\]** configure
option.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/bzip2/setup.html#Requirements)
-   [Installation](/bzip2/setup.html#Installation)
-   [Runtime Configuration](/bzip2/setup.html#Runtime%20Configuration)
-   [Resource Types](/bzip2/setup.html#Resource%20Types)

Requirements
------------

This module uses the functions of the
<a href="https://www.sourceware.org/bzip2/" class="link external">» bzip2</a>
library by Julian Seward. This module requires bzip2/libbzip2 version
\>= 1.0.x.

Installation
------------

Bzip2 support in PHP is not enabled by default. You will need to use the
**--with-bz2\[=DIR\]** configuration option when compiling PHP to enable
bzip2 support.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension defines one resource type: a file pointer identifying the
bz2-file to work on.

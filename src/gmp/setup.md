Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/gmp/setup.html#Requirements)
-   [Installation](/gmp/setup.html#Installation)
-   [Runtime Configuration](/gmp/setup.html#Runtime%20Configuration)
-   [Resource Types](/gmp/setup.html#Resource%20Types)

Requirements
------------

The GMP library can be downloaded from
<a href="http://gmplib.org/#DOWNLOAD" class="link external">» http://gmplib.org/#DOWNLOAD</a>.
This site also has the GMP manual available.

At least GMP version 2 is required, with some functions requiring a more
recent version of the GMP library.

Installation
------------

In order to have these functions available, PHP must be compiled with
GMP support by using the **--with-gmp** option.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

Prior to PHP 5.6, most GMP functions operate on or return GMP number
resources. PHP 5.6 onwards uses <span class="classname">GMP</span>
objects in place of GMP number resources.

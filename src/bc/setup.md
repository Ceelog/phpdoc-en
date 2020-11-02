Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/bc/setup.html#Requirements)
-   [Installation](/bc/setup.html#Installation)
-   [Runtime Configuration](/bc/setup.html#Runtime%20Configuration)
-   [Resource Types](/bc/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

These functions are only available if PHP was configured with
**--enable-bcmath**.

The Windows version of PHP has built-in support for this extension. You
do not need to load any additional extensions in order to use these
functions.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                    | Default | Changeable    | Changelog |
|---------------------------------------------------------|---------|---------------|-----------|
| <a href="/bc/setup.html#" class="link">bcmath.scale</a> | "0"     | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`bcmath.scale` <span class="type">int</span>  
Number of decimal digits for all bcmath functions. See also <span
class="function">bcscale</span>.

Resource Types
--------------

This extension has no resource types defined.

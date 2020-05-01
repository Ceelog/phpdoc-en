Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/sem/setup.html#Requirements)
-   [Installation](/sem/setup.html#Installation)
-   [Runtime Configuration](/sem/setup.html#Runtime%20Configuration)
-   [Resource Types](/sem/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

Support for this functions are not enabled by default. To enable System
V semaphore support compile PHP with the option **--enable-sysvsem**. To
enable the System V shared memory support compile PHP with the option
**--enable-sysvshm**. To enable the System V messages support compile
PHP with the option **--enable-sysvmsg**.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                         | Default | Changeable       | Changelog |
|--------------------------------------------------------------|---------|------------------|-----------|
| <a href="/sem/setup.html#" class="link">sysvshm.init_mem</a> | 10000   | PHP\_INI\_SYSTEM |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`sysvshm.init_mem` <span class="type">int</span>  
A default size of the shared memory segment.

Resource Types
--------------

This extension has no resource types defined.

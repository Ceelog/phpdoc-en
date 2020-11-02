Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/memtrack/setup.html#Requirements)
-   [Installation](/memtrack/setup.html#Installation)
-   [Runtime
    Configuration](/memtrack/setup.html#Runtime%20Configuration)
-   [Resource Types](/memtrack/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/memtrack" class="link external">» https://pecl.php.net/package/memtrack</a>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                              | Default | Changeable       |
|-------------------------------------------------------------------|---------|------------------|
| <a href="/memtrack/setup.html#" class="link">memtrack.enabled</a> | "0"     | PHP\_INI\_SYSTEM |
| memtrack.soft\_limit                                              | "0"     | PHP\_INI\_ALL    |
| memtrack.hard\_limit                                              | "0"     | PHP\_INI\_ALL    |
| memtrack.vm\_limit                                                | "0"     | PHP\_INI\_ALL    |
| memtrack.ignore\_functions                                        | ""      | PHP\_INI\_SYSTEM |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`memtrack.enabled` <span class="type">bool</span>  
Disables or enables the extension. Default value is 0, i.e. disabled.

`memtrack.soft_limit` <span class="type">int</span>  
Soft memory limit.

The extension checks memory consumption before and after executing an
op\_array and produces a warning is the difference between the two
values is equal to or greater than the soft limit, but only if the
function is not ignored.

Setting this option to 0 also disables both soft and hard limit
warnings. Default value is 0, i.e. no warnings is produced.

`memtrack.hard_limit` <span class="type">int</span>  
Hard memory limit.

The extension checks memory consumption before and after executing an
op\_array and produces a warning is the difference between the two
values is equal to or greater than the hard limit, *even if the function
is ignored*. Setting this option to 0 disables hard limit warnings
completely. Default value is 0, i.e. no hard limit warnings is produced.

`memtrack.vm_limit` <span class="type">int</span>  
Virtual memory limit (set on a process).

This limit is checked only on shutdown and a warning is produced if the
value is greater than or equal to the limit.

This option is currently supported only on OSes where mallinfo()
function is available (i.e. Linux).

`memtrack.ignore_functions` <span class="type">string</span>  
A comma or whitespace-separated list of functions which are to be
ignored by soft\_limit. The values are case-insensitive, for class
methods use class::method syntax.

Resource Types
--------------

This extension has no resource types defined.

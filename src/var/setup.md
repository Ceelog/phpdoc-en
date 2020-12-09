Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/var/setup.html#Requirements)
-   [Installation](/var/setup.html#Installation)
-   [Runtime Configuration](/var/setup.html#Runtime%20Configuration)
-   [Resource Types](/var/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                  | Default    | Changeable    | Changelog |
|-----------------------------------------------------------------------|------------|---------------|-----------|
| <a href="/var/setup.html#" class="link">unserialize_callback_func</a> | **`null`** | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`unserialize_callback_func` <span class="type">string</span>  
The callback specified is called when <span
class="function">unserialize</span> attempts to use an undefined class.
A warning appears if the specified callback function is not defined, or
if the callback function fails to define the missing class.

See also <span class="function">unserialize</span> and
<a href="/language/oop5/autoload.html" class="link">Autoloading Objects</a>.

Resource Types
--------------

This extension has no resource types defined.

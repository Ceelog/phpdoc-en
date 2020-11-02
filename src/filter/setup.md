Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/filter/setup.html#Requirements)
-   [Installation](/filter/setup.html#Installation)
-   [Runtime Configuration](/filter/setup.html#Runtime%20Configuration)
-   [Resource Types](/filter/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

The filter extension is enabled by default as of PHP 5.2.0. To disable
the filter extension, use **--disable-filter**.

Before PHP 5.2 an experimental PECL extension was used, however, the
PECL version is no longer recommended or updated.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                | Default       | Changeable       | Changelog                                                     |
|---------------------------------------------------------------------|---------------|------------------|---------------------------------------------------------------|
| <a href="/filter/setup.html#" class="link">filter.default</a>       | "unsafe\_raw" | PHP\_INI\_PERDIR | PHP\_INI\_ALL in filter \<= 0.9.4. Available since PHP 5.2.0. |
| <a href="/filter/setup.html#" class="link">filter.default_flags</a> | NULL          | PHP\_INI\_PERDIR | PHP\_INI\_ALL in filter \<= 0.9.4. Available since PHP 5.2.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`filter.default` <span class="type">string</span>  
Filter all `$_GET`, `$_POST`, `$_COOKIE`, `$_REQUEST` and `$_SERVER`
data by this filter. Original data can be accessed through <span
class="function">filter\_input</span>.

Accepts the name of the filter you like to use by default. See the
existing <a href="/filter/filters.html" class="link">filter list</a> for
the list of the filter names.

> **Note**:
>
> Be careful about the default flags for the default filters. You should
> explicitly set them to the value you want. For example, to configure
> the default filter to behave exactly like <span
> class="function">htmlspecialchars</span> you need to set them default
> flags to 0 as shown below.
>
> **Example \#1 Configuring the default filter to act like
> htmlspecialchars**
>
> ``` php
> filter.default = full_special_chars
> filter.default_flags = 0
> ```

`filter.default_flags` <span class="type">int</span>  
Default flags to apply when the default filter is set. This is set to
**`FILTER_FLAG_NO_ENCODE_QUOTES`** by default for backwards
compatibility reasons. See the
<a href="/filter/filters.html#Filter%20flags" class="link">flag list</a>
for the list of all the flag names.

Resource Types
--------------

This extension has no resource types defined.

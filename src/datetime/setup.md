Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/datetime/setup.html#Requirements)
-   [Installation](/datetime/setup.html#Installation)
-   [Runtime
    Configuration](/datetime/setup.html#Runtime%20Configuration)
-   [Resource Types](/datetime/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

> **Note**: **Getting the latest timezone database**  
>
> The latest version of the timezone database can be installed via
> PECL's
> <a href="https://pecl.php.net/get/timezonedb" class="link external">» timezonedb</a>.

> **Note**: **Experimental DateTime support in PHP 5.1.x**  
>
> Although the <span class="classname">DateTime</span> class (and
> related functions) are enabled by default since PHP 5.2.0, it is
> possible to add experimental support into PHP 5.1.x by using the
> following flag before configure/compile:
> *CFLAGS=-DEXPERIMENTAL\_DATE\_SUPPORT=1*

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                    | Default     | Changeable    | Changelog                  |
|-------------------------------------------------------------------------|-------------|---------------|----------------------------|
| <a href="/datetime/setup.html#" class="link">date.default_latitude</a>  | "31.7667"   | PHP\_INI\_ALL |                            |
| <a href="/datetime/setup.html#" class="link">date.default_longitude</a> | "35.2333"   | PHP\_INI\_ALL |                            |
| <a href="/datetime/setup.html#" class="link">date.sunrise_zenith</a>    | "90.583333" | PHP\_INI\_ALL |                            |
| <a href="/datetime/setup.html#" class="link">date.sunset_zenith</a>     | "90.583333" | PHP\_INI\_ALL |                            |
| <a href="/datetime/setup.html#" class="link">date.timezone</a>          | ""          | PHP\_INI\_ALL | Available as of PHP 5.1.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`date.default_latitude` <span class="type">float</span>  
The default latitude.

`date.default_longitude` <span class="type">float</span>  
The default longitude.

`date.sunrise_zenith` <span class="type">float</span>  
The default sunrise zenith.

`date.sunset_zenith` <span class="type">float</span>  
The default sunset zenith.

`date.timezone` <span class="type">string</span>  
The default timezone used by all date/time functions. Prior to PHP
5.4.0, this would only work if the `TZ` environment variable was not
set. The precedence order for which timezone is used if none is
explicitly mentioned is described in the <span
class="function">date\_default\_timezone\_get</span> page. See
<a href="/timezones.html" class="xref">List of Supported Timezones</a>
for a list of supported timezones.

> **Note**: <span class="simpara"> The first four configuration options
> are currently only used by <span class="function">date\_sunrise</span>
> and <span class="function">date\_sunset</span>. </span>

Resource Types
--------------

This extension has no resource types defined.

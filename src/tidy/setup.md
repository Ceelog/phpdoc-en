Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/tidy/setup.html#Requirements)
-   [Installation](/tidy/setup.html#Installation)
-   [Runtime Configuration](/tidy/setup.html#Runtime%20Configuration)
-   [Resource Types](/tidy/setup.html#Resource%20Types)

Requirements
------------

To use Tidy, you will need libtidy installed, available on the
<a href="http://tidy.sourceforge.net/" class="link external">» tidy homepage</a>.
As of PHP 7.1.0, the HTML5 aware successor
<a href="http://www.html-tidy.org/" class="link external">» libtidy5</a>
can be used alternatively. As of PHP 7.3.0, another option is to use
<a href="https://github.com/petdance/tidyp" class="link external">» libtidyp</a>.

Installation
------------

This extension is bundled with PHP 5 and greater, and is installed using
the **--with-tidy** configure option.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                             | Default | Changeable       | Changelog                           |
|------------------------------------------------------------------|---------|------------------|-------------------------------------|
| <a href="/tidy/setup.html#" class="link">tidy.default_config</a> | ""      | PHP\_INI\_SYSTEM |                                     |
| <a href="/tidy/setup.html#" class="link">tidy.clean_output</a>   | "0"     | PHP\_INI\_USER   | PHP\_INI\_PERDIR prior to PHP 5.4.0 |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`tidy.default_config` <span class="type">string</span>  
Default path for tidy config file.

`tidy.clean_output` <span class="type">bool</span>  
Turns on/off the output repairing by Tidy.

**Warning**
Do not turn on *tidy.clean\_output* if you are generating non-html
content such as dynamic images.

Resource Types
--------------

This extension has no resource types defined.

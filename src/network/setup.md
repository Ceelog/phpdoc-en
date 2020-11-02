Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/network/setup.html#Requirements)
-   [Installation](/network/setup.html#Installation)
-   [Runtime Configuration](/network/setup.html#Runtime%20Configuration)
-   [Resource Types](/network/setup.html#Resource%20Types)

Requirements
------------

Functions <span class="function">checkdnsrr</span>, <span
class="function">getmxrr</span> and <span
class="function">dns\_get\_record</span> requires Bind on Linux.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                    | Default | Changeable    | Changelog                                      |
|-------------------------------------------------------------------------|---------|---------------|------------------------------------------------|
| <a href="/network/setup.html#" class="link">define_syslog_variables</a> | "0"     | PHP\_INI\_ALL | Deprecated in PHP 5.3.0. Removed in PHP 5.4.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`define_syslog_variables` <span class="type">bool</span>  
Whether or not to define the various syslog variables (e.g. $LOG\_PID,
$LOG\_CRON, etc.). Turning it off is a good idea performance-wise. At
runtime, you can define these variables by calling <span
class="function">define\_syslog\_variables</span>.

Resource Types
--------------

This extension defines a file pointer resource returned by <span
class="function">fsockopen</span> and <span
class="function">pfsockopen</span>.

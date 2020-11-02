Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/nsapi/setup.html#Requirements)
-   [Installation](/nsapi/setup.html#Installation)
-   [Runtime Configuration](/nsapi/setup.html#Runtime%20Configuration)
-   [Resource Types](/nsapi/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

For PHP installation on Netscape/iPlanet/Sun webservers see the NSAPI
section (<a href="/install/unix/sun.html" class="link">UNIX</a>,
<a href="/install/windows/legacy/index.html#install.windows.legacy.sun" class="link">Windows</a>)
in the installation chapter.

Runtime Configuration
---------------------

The behaviour of the NSAPI PHP module is affected by settings in
`php.ini`. Configuration settings from `php.ini` may be overridden by
additional parameters to the *php4\_execute* call in `obj.conf`

| Name                                                             | Default | Changeable    | Changelog |
|------------------------------------------------------------------|---------|---------------|-----------|
| <a href="/nsapi/setup.html#" class="link">nsapi.read_timeout</a> | "60"    | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`nsapi.read_timeout` <span class="type">int</span>  
Sets the time in seconds the plugin is waiting for POST data from the
client.

Resource Types
--------------

This extension has no resource types defined.

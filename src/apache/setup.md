Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/apache/setup.html#Requirements)
-   [Installation](/apache/setup.html#Installation)
-   [Runtime Configuration](/apache/setup.html#Runtime%20Configuration)
-   [Resource Types](/apache/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

For PHP installation on Apache see the
<a href="/install.html" class="link">installation chapter</a>.

Runtime Configuration
---------------------

The behaviour of the Apache PHP module is affected by settings in
`php.ini`. Configuration settings from `php.ini` may be overridden by
<a href="/configuration/changes.html#configuration.changes.apache" class="link">php_flag</a>
settings in the server configuration file or local `.htaccess` files.

**Example \#1 Turning off PHP parsing for a directory using
`.htaccess`**

    php_flag engine off

| Name                                                           | Default | Changeable    | Changelog |
|----------------------------------------------------------------|---------|---------------|-----------|
| <a href="/apache/setup.html#" class="link">engine</a>          | "1"     | PHP\_INI\_ALL |           |
| <a href="/apache/setup.html#" class="link">child_terminate</a> | "0"     | PHP\_INI\_ALL |           |
| <a href="/apache/setup.html#" class="link">last_modified</a>   | "0"     | PHP\_INI\_ALL |           |
| <a href="/apache/setup.html#" class="link">xbithack</a>        | "0"     | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`engine` <span class="type">bool</span>  
Turns PHP parsing on or off. This directive is really only useful in the
Apache module version of PHP. It is used by sites that would like to
turn PHP parsing on and off on a per-directory or per-virtual server
basis. By putting **`engine off`** in the appropriate places in the
`httpd.conf` file, PHP can be enabled or disabled.

`child_terminate` <span class="type">bool</span>  
Specify whether PHP scripts may request child process termination on end
of request, see also <span
class="function">apache\_child\_terminate</span>.

`last_modified` <span class="type">bool</span>  
Send PHP scripts modification date as Last-Modified: header for this
request.

`xbithack` <span class="type">bool</span>  
Parse files with executable bit set as PHP regardless of their file
ending.

Resource Types
--------------

This extension has no resource types defined.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mime-magic/setup.html#Requirements)
-   [Installation](/mime-magic/setup.html#Installation)
-   [Runtime
    Configuration](/mime-magic/setup.html#Runtime%20Configuration)
-   [Resource Types](/mime-magic/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

**Warning**

Mimetype extensions has been removed from PHP 5.3.0 in favor of
<a href="/book/fileinfo.html" class="link">Fileinfo</a>.

You must compile PHP with the configure switch **--with-mime-magic** to
get support for mime-type functions. The extension needs a copy of the
simplified `magic` file that is distributed with the Apache httpd.

> **Note**:
>
> This extension is not capable of handling the fully decorated `magic`
> file that generally comes with standard Linux distro's and is supposed
> to be used with recent versions of `file` command.

> **Note**: **Note to Win32 Users**  
>
> In order to use this module on a Windows environment, you must set the
> path to the bundled `magic.mime` file in your `php.ini`.
>
> **Example \#1 Setting the path to `magic.mime`**
>
>     mime_magic.magicfile = "$PHP_INSTALL_DIR\magic.mime"
>
> Remember to substitute the `$PHP_INSTALL_DIR` for your actual path to
> PHP in the above example. e.g. `c:\php`

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                    | Default                   | Changeable       | Changelog                  |
|-------------------------------------------------------------------------|---------------------------|------------------|----------------------------|
| <a href="/mime-magic/setup.html#" class="link">mime_magic.debug</a>     | "0"                       | PHP\_INI\_SYSTEM | Available since PHP 5.0.0. |
| <a href="/mime-magic/setup.html#" class="link">mime_magic.magicfile</a> | "/path/to/php/magic.mime" | PHP\_INI\_SYSTEM | Available since PHP 4.3.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`mime_magic.debug` <span class="type">bool</span>  
Enable/disable debugging.

`mime_magic.magicfile` <span class="type">string</span>  
The path to the magic.mime file.

Resource Types
--------------

This extension has no resource types defined.

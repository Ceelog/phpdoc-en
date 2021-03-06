Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/com/setup.html#Requirements)
-   [Installation](/com/setup.html#Installation)
-   [Runtime Configuration](/com/setup.html#Runtime%20Configuration)
-   [Resource Types](/com/setup.html#Resource%20Types)

Requirements
------------

COM functions are only available for the Windows version of PHP.

.Net support requires the .Net runtime.

Installation
------------

As of PHP 5.3.15 / 5.4.5, this extension requires `php_com_dotnet.dll`
to be enabled inside of `php.ini` in order to use these functions.
Previous versions of PHP enabled these extensions by default.

You are responsible for installing support for the various COM objects
that you intend to use (such as MS Word); we don't and can't bundle all
of those with PHP.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                       | Default | Changeable       | Changelog       |
|----------------------------------------------------------------------------|---------|------------------|-----------------|
| <a href="/com/setup.html#" class="link">com.allow_dcom</a>                 | "0"     | PHP\_INI\_SYSTEM |                 |
| <a href="/com/setup.html#" class="link">com.autoregister_typelib</a>       | "0"     | PHP\_INI\_ALL    |                 |
| <a href="/com/setup.html#" class="link">com.autoregister_verbose</a>       | "0"     | PHP\_INI\_ALL    |                 |
| <a href="/com/setup.html#" class="link">com.autoregister_casesensitive</a> | "1"     | PHP\_INI\_ALL    |                 |
| <a href="/com/setup.html#" class="link">com.code_page</a>                  | ""      | PHP\_INI\_ALL    |                 |
| <a href="/com/setup.html#" class="link">com.dotnet_version</a>             | ""      | PHP\_INI\_SYSTEM | As of PHP 8.0.0 |
| <a href="/com/setup.html#" class="link">com.typelib_file</a>               | ""      | PHP\_INI\_SYSTEM |                 |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`com.allow_dcom`  
When this is turned on, PHP will be allowed to operate as a D-COM
(Distributed COM) client and will allow the PHP script to instantiate
COM objects on a remote server.

`com.autoregister_typelib`  
When this is turned on, PHP will attempt to register constants from the
typelibrary of <span class="classname">COM</span> objects that it
instantiates, if those objects implement the interfaces required to
obtain that information. The case sensitivity of the constants it
registers is controlled by the
<a href="/com/setup.html#" class="xref"></a> configuration directive.

`com.autoregister_verbose`  
When this is turned on, any problems with loading a typelibrary during
object instantiation will be reported using the PHP error mechanism. The
default is off, which does not emit any indication if there was an error
finding or loading the type library.

`com.autoregister_casesensitive`  
When this is turned on (the default), constants found in auto-loaded
type libraries when instatiating <span class="classname">COM</span>
objects will be registered case sensitively. See <span
class="function">com\_load\_typelib</span> for more details.

`com.code_page`  
It controls the default character set code-page to use when passing
strings to and from COM objects. If set to an empty string, PHP will
assume that you want **`CP_ACP`**, which is the default system ANSI code
page.

If the text in your scripts is encoded using a different
encoding/character set by default, setting this directive will save you
from having to pass the code page as a parameter to the
<a href="/class/com.html" class="xref">com</a> class constructor. Please
note that by using this directive (as with any PHP configuration
directive), your PHP script becomes less portable; you should use the
COM constructor parameter whenever possible.

`com.dotnet_version`  
The version of the .NET framework to use for <span
class="classname">dotnet</span> objects. The value of the setting is the
first three parts of the framework's version number, separated by dots,
and prefixed with *v*, e.g. *v4.0.30319*.

`com.typelib_file`  
When set, this should hold the path to a file that contains a list of
typelibraries that should be loaded on startup. Each line of the file
will be treated as the type library name and loaded as though you had
called <span class="function">com\_load\_typelib</span>. The constants
will be registered persistently, so that the library only needs to be
loaded once. If a type library name ends with the string *\#cis* or
*\#case\_insensitive*, then the constants from that library will be
registered case insensitively.

Resource Types
--------------

This extension has no resource types defined.

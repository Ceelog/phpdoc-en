Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/ffi/setup.html#Requirements)
-   [Installation](/ffi/setup.html#Installation)
-   [Runtime Configuration](/ffi/setup.html#Runtime%20Configuration)
-   [Resource Types](/ffi/setup.html#Resource%20Types)

Requirements
------------

This extension requires the
<a href="https://sourceware.org/libffi/" class="link external">» libffi library</a>
to be installed.

Installation
------------

To enable the FFI extension, PHP has to be configured with
**--with-ffi**.

Windows users have to include `php_ffi.dll` into `php.ini` to enable the
FFI extension.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                    | Default   | Changeable       | Changelog |
|---------------------------------------------------------|-----------|------------------|-----------|
| <a href="/ffi/setup.html#" class="link">ffi.enable</a>  | "preload" | PHP\_INI\_SYSTEM |           |
| <a href="/ffi/setup.html#" class="link">ffi.preload</a> | ""        | PHP\_INI\_SYSTEM |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`ffi.enable` <span class="type">string</span>  
Allows enabling (*"true"*) or disabling (*"false"*) FFI API usage, or
restricting it only to the CLI SAPI and preloaded files (*"preload"*).

The FFI API restrictions only affect the <span
class="classname">FFI</span> class, but not overloaded functions of
<span class="classname">FFI\\CData</span> objects. This means that it is
possible to create some <span class="classname">FFI\\CData</span>
objects in preloaded files, and then to use these directly in PHP
scripts.

`ffi.preload` <span class="type">string</span>  
Allows preloading of FFI bindings during startup, which is not possible
with <span class="methodname">FFI::load</span> if
<a href="/opcache/setup.html#" class="link">opcache.preload_user</a> is
set. This directive accepts a **`DIRECTORY_SEPARATOR`** delimited list
of filenames. The preloaded bindings can be accessed by calling <span
class="methodname">FFI::scope</span>.

Resource Types
--------------

This extension has no resource types defined.

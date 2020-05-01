Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/fileinfo/setup.html#Requirements)
-   [Installation](/fileinfo/setup.html#Installation)
-   [Runtime
    Configuration](/fileinfo/setup.html#Runtime%20Configuration)
-   [Resource Types](/fileinfo/setup.html#Resource%20Types)

Requirements
------------

Before PHP 5.3.0, the *magic\_open* library is needed to build this
extension.

Installation
------------

This extension is enabled by default as of PHP 5.3.0. Before this time,
fileinfo was a PECL extension but is no longer maintained there.
However, versions prior to 5.3+ may use the
<a href="https://pecl.php.net/package/fileinfo" class="link external">» discontinued PECL extension</a>.

Windows users must include the bundled `php_fileinfo.dll` DLL file in
`php.ini` to enable this extension.

The libmagic library is bundled with PHP, but includes PHP specific
changes. A patch against libmagic named `libmagic.patch` is maintained
and may be found within the PHP fileinfo extensions source.

| PHP Version | Updated libmagic Version | Notes |
|-------------|--------------------------|-------|
| 5.3.2       | 5.03                     |       |
| 5.3.0       | 5.02                     |       |

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

There is one resource used in Fileinfo extension: a magic database
descriptor returned by <span class="function">finfo\_open</span>.

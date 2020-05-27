Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mailparse/setup.html#Requirements)
-   [Installation](/mailparse/setup.html#Installation)
-   [Runtime
    Configuration](/mailparse/setup.html#Runtime%20Configuration)
-   [Resource Types](/mailparse/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP. Information for installing this PECL
extension may be found in the manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/mailparse" class="link external">» https://pecl.php.net/package/mailparse</a>.

In order to use these functions you must compile PHP with mailparse
support by using the **--enable-mailparse** configure option.

Windows users will enable `php_mailparse.dll` inside of `php.ini` in
order to use these functions. Windows binaries (DLL files) for this PECL
extension are available from the PECL website.

It is necessary that the
<a href="/ref/mbstring.html" class="link">mbstring</a> extension is
loaded before mailparse.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

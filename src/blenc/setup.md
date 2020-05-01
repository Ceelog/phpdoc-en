Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/blenc/setup.html#Requirements)
-   [Installation](/blenc/setup.html#Installation)
-   [Runtime Configuration](/blenc/setup.html#Runtime%20Configuration)
-   [Resource Types](/blenc/setup.html#Resource%20Types)

Requirements
------------

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/blenc" class="link external">» https://pecl.php.net/package/blenc</a>

It's strongly recommended to install BLENC from sources without 'pecl'
command. In this way you can:

-   Specify your personal encryption key used to create redistributable
    keys. Your sourcecode will be more difficult to decrypt also for
    users that can read your key\_file on webserver.
-   Specify a expiration date for the BLENC module. With expiration date
    you can decide that BLENC module on target system will work until a
    date. After that BLENC will not decrypt any files.

All these configuration options are stored into header file:
blenc\_protect.h

Please read the content of blenc\_protect.h in sources of BLENC to know
how set these hardcoded options.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                         | Default                  | Changeable    | Changelog |
|--------------------------------------------------------------|--------------------------|---------------|-----------|
| <a href="/blenc/setup.html#" class="link">blenc.key_file</a> | /usr/local/etc/blenckeys | PHP\_INI\_ALL |           |

Here's a short explanation of the configuration directives.

`blenc.key_file` <span class="type">string</span>  
It's the location where BLENC can find the file containing a list of
available decryption keys. This file must be readable by webserver.

Resource Types
--------------

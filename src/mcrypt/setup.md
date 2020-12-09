Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mcrypt/setup.html#Requirements)
-   [Installation](/mcrypt/setup.html#Installation)
-   [Runtime Configuration](/mcrypt/setup.html#Runtime%20Configuration)
-   [Resource Types](/mcrypt/setup.html#Resource%20Types)

Requirements
------------

These functions work using
<a href="http://mcrypt.sourceforge.net/" class="link external">» mcrypt</a>.
To use it, download `libmcrypt-x.x.tar.gz` from
<a href="http://mcrypt.sourceforge.net/" class="link external">» http://mcrypt.sourceforge.net/</a>
and follow the included installation instructions.

libmcrypt Version 2.5.6 or greater is required.

Windows users will find the library is the PHP 5.2 Windows binaries
release. PHP 5.3 Windows binaries uses the static version of the MCrypt
library, no DLL are needed.

If you linked against libmcrypt 2.4.x or higher, the following
additional block algorithms are supported: CAST, LOKI97, RIJNDAEL,
SAFERPLUS, SERPENT and the following stream ciphers: ENIGMA (crypt),
PANAMA, RC4 and WAKE. With libmcrypt 2.4.x or higher another cipher mode
is also available; nOFB.

Installation
------------

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 7.2.0

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/mcrypt" class="link external">» https://pecl.php.net/package/mcrypt</a>.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                 | Default    | Changeable    | Changelog |
|----------------------------------------------------------------------|------------|---------------|-----------|
| <a href="/mcrypt/setup.html#" class="link">mcrypt.algorithms_dir</a> | **`null`** | PHP\_INI\_ALL |           |
| <a href="/mcrypt/setup.html#" class="link">mcrypt.modes_dir</a>      | **`null`** | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`mcrypt.algorithms_dir` <span class="type">string</span>  
The directory that contains the algorithms. Defaults to the directories
compiled within libmcrypt, which is typically
*/usr/local/lib/libmcrypt*. See <span
class="function">mcrypt\_list\_algorithms</span> for additional details.

`mcrypt.modes_dir` <span class="type">string</span>  
The directory that contains the modes. Defaults to the directories
compiled within libmcrypt, which is typically
*/usr/local/lib/libmcrypt*. See <span
class="function">mcrypt\_list\_modes</span> for additional details.

Resource Types
--------------

<span class="function">mcrypt\_module\_open</span> returns an encryption
descriptor.

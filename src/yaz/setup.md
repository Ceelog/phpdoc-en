Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/yaz/setup.html#Requirements)
-   [Installation](/yaz/setup.html#Installation)
-   [Runtime Configuration](/yaz/setup.html#Runtime%20Configuration)
-   [Resource Types](/yaz/setup.html#Resource%20Types)

Requirements
------------

Obtain YAZ (ANSI/NISO Z39.50 support) and install it. YAZ can be fetched
in source or in various prebuilt packages from the
<a href="http://ftp.indexdata.dk/pub/yaz/" class="link external">» YAZ archive</a>.
Systems such as Debian GNU/Linux, Suse Linux, FreeBSD also has YAZ as
part of their distribution.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/yaz" class="link external">» https://pecl.php.net/package/yaz</a>

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

> **Note**: **Information specific to Windows users**  
>
> `php_yaz.dll` depends on `yaz.dll`. The `yaz.dll` is part of the Win32
> ZIP from the PHP site. It is also part of the Windows YAZ install
> available from the
> <a href="http://ftp.indexdata.dk/pub/yaz/win32/" class="link external">» YAZ WIN32 area</a>.
>
> On windows, don't forget to add the PHP directory to the `PATH`, so
> that the `yaz.dll` file can be found by the system.

**Warning**

The <a href="/book/imap.html" class="link">IMAP</a>,
<a href="/book/recode.html" class="link">recode</a> and
<a href="/book/yaz.html" class="link">YAZ</a> extensions cannot be used
in conjunction, because they share the same internal symbols. Note: Yaz
2.0 and above does not suffer from this problem.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

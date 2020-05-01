Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mcve/setup.html#Requirements)
-   [Installation](/mcve/setup.html#Installation)
-   [Runtime Configuration](/mcve/setup.html#Runtime%20Configuration)
-   [Resource Types](/mcve/setup.html#Resource%20Types)

Requirements
------------

The LibMonetra (formerly libmcve) library.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/mcve" class="link external">» https://pecl.php.net/package/mcve</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

If installing without specifying the libmonetra path, PHP will attempt
to look in the default LibMonetra Install location (`/usr/local`). If
Monetra (MCVE) is in a non-standard location, run configure with:
**--with-mcve=$mcve\_path**, where $mcve\_path is the path to your
MCVE/Monetra installation. Please note that MCVE/Monetra support
requires that $mcve\_path/lib and $mcve\_path/include exist, and include
`mcve.h` or `monetra.h` under the include directory and `libmcve.so`
and/or `libmcve.a` and/or `libmonetra.so` and/or `libmonetra.a` under
the lib directory.

Since MCVE/Monetra has true server/client separation, there are no
additional requirements for running PHP with MCVE support. To test your
MCVE/Monetra extension in PHP, you may connect to testbox.monetra.com on
port 8333 for IP, or port 8444 for SSL using the MCVE/Monetra PHP API.
Use 'vitale' for your username, and 'test' for your password. Additional
information about test facilities are available at
<a href="http://www.mainstreetsoftworks.com/" class="link external">» http://www.mainstreetsoftworks.com/</a>.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension defines a MCVE\_CONN resource returned by <span
class="function">m\_initconn</span>.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/ssh2/setup.html#Requirements)
-   [Installation](/ssh2/setup.html#Installation)
-   [Runtime Configuration](/ssh2/setup.html#Runtime%20Configuration)
-   [Resource Types](/ssh2/setup.html#Resource%20Types)

Requirements
------------

The
<a href="http://www.openssl.org/" class="link external">» OpenSSL</a>
and <a href="http://libssh2.org/" class="link external">» libssh2</a>
libraries are required. Ensure that the development libraries are
installed, where a typical package name might be *openssl-dev*.

Version 1.2 or newer of the libssh2 library is required, although it's
possible newer releases of pecl/ssh2 may require newer versions (see the
release notes).

The <span class="function">ssh2\_auth\_agent</span> function will only
be available with libssh \>= 1.2.3.

support for <span class="function">stream\_set\_timeout</span> to
channel streams will only be available with libssh \>= 1.2.9.

Libssh2 comes in two flavours: gcrypt or openssl. Some linux
distributions build libssh2 with the gcrypt library, some use openssl.
Libssh2 has some issues when compiled with gcrypt, please use openssl.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/ssh2" class="link external">» https://pecl.php.net/package/ssh2</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

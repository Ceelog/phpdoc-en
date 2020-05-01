Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/openssl/setup.html#Requirements)
-   [Installation](/openssl/setup.html#Installation)
-   [Runtime Configuration](/openssl/setup.html#Runtime%20Configuration)
-   [Resource Types](/openssl/setup.html#Resource%20Types)

Requirements
------------

In order to use the OpenSSL functions you need to install the
<a href="http://www.openssl.org/" class="link external">» OpenSSL</a>
library. PHP 5 requires at least OpenSSL \>= 0.9.6. However later PHP 5
versions have some compilation issues and should be used at least with
OpenSSL \>= 0.9.8 which is also a minimal version for PHP 7.0. Other
versions (PHP \>= 7.1.0) require OpenSSL \>= 1.0.1.

**Warning**

You are strongly encouraged to use the most recent OpenSSL version,
otherwise your web server could be vulnerable to attack.

Installation
------------

To use PHP's OpenSSL support you must also compile PHP
**--with-openssl\[=DIR\]**.

The OpenSSL library also has additional requirements for normal
operation at run-time. Most notably, OpenSSL requires access to a random
or pseudo-random number generator; on most Unix and Unix-like platforms
(including Linux), this means that it must have access to a
*/dev/urandom* or */dev/random* device.

As of PHP 5.6.3, the configure option **--with-system-ciphers** is
available which causes PHP to use the system cipher list instead of a
hard-coded default.

> **Note**: **Note to Win32 Users**  
>
> In order for this extension to work, there are DLL files that must be
> available to the Windows system `PATH`. For information on how to do
> this, see the FAQ entitled
> "<a href="/faq/installation.html#faq.installation.addtopath" class="link">How do I add my PHP directory to the PATH on Windows</a>".
> Although copying DLL files from the PHP folder into the Windows system
> directory also works (because the system directory is by default in
> the system's `PATH`), this is not recommended. *This extension
> requires the following files to be in the `PATH`:* `libeay32.dll`, or,
> as of OpenSSL 1.1, `libcrypto-*.dll`
>
> Additionally, if you are planning to use the key generation and
> certificate signing functions, you will need to install a valid
> `openssl.cnf` file on your system. We include a sample configuration
> file in our win32 binary distributions, in the `extras/openssl`
> directory.
>
> PHP will search for the `openssl.cnf` using the following logic:
>
> -   <span class="simpara">the *OPENSSL\_CONF* environmental variable,
>     if set, will be used as the path (including filename) of the
>     configuration file. </span>
> -   <span class="simpara">the *SSLEAY\_CONF* environmental variable,
>     if set, will be used as the path (including filename) of the
>     configuration file. </span>
> -   <span class="simpara">The file `openssl.cnf` will be assumed to be
>     found in the default certificate area, as configured at the time
>     that the openssl DLL was compiled. This is usually means that the
>     default filename is
>     `C:\Program Files\Common Files\SSL\openssl.cnf` (x64) or
>     `C:\Program Files (x86)\Common Files\SSL\openssl.cnf` (x86), or,
>     prior to PHP 7.4.0, `C:\usr\local\ssl\openssl.cnf`. </span>
>
> <span class="simpara"> In your installation, you need to decide
> whether to install the configuration file in the default path or
> whether to install it someplace else and use environmental variables
> (possibly on a per-virtual-host basis) to locate the configuration
> file. Note that it is possible to override the default path from the
> script using the `configargs` of the functions that require a
> configuration file. </span>
>
> **Caution**
>
> Ensure that non-privileged users are not allowed to modify
> `openssl.cnf`.

| Version | Description                                                                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | The OpenSSL default config path has been changed from `C:\usr\local\ssl` to `C:\Program Files\Common Files\SSL` and `C:\Program Files (x86)\Common Files\SSL`, respectively. |

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name           | Default | Changeable       | Changelog                  |
|----------------|---------|------------------|----------------------------|
| openssl.cafile | ""      | PHP\_INI\_PERDIR | Available as of PHP 5.6.0. |
| openssl.capath | ""      | PHP\_INI\_PERDIR | Available as of PHP 5.6.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`openssl.cafile` <span class="type">string</span>  
Location of Certificate Authority file on local filesystem which should
be used with the verify\_peer context option to authenticate the
identity of the remote peer.

`openssl.capath` <span class="type">string</span>  
If cafile is not specified or if the certificate is not found there, the
directory pointed to by capath is searched for a suitable certificate.
capath must be a correctly hashed certificate directory.

See also the
<a href="/context/ssl.html" class="link">SSL stream context</a> options.

Resource Types
--------------

There are 3 resource types defined in the OpenSSL module. The first one
is a pkey (public or private key) identifier, the second one is a X509
certificate identifier and the third one is a CSR (certificate signing
request) identifier.

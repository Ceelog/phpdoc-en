Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/curl/setup.html#Requirements)
-   [Installation](/curl/setup.html#Installation)
-   [Runtime Configuration](/curl/setup.html#Runtime%20Configuration)
-   [Resource Types](/curl/setup.html#Resource%20Types)

Requirements
------------

In order to use PHP's cURL functions you need to install the
<a href="http://curl.haxx.se/" class="link external">» libcurl</a>
package. PHP requires libcurl version 7.10.5 or later.

Installation
------------

To use PHP's cURL support you must also compile PHP
**--with-curl\[=DIR\]** where DIR is the location of the directory
containing the `lib` and `include` directories. In the `include`
directory there should be a folder named `curl` which should contain the
`easy.h` and `curl.h` files. There should be a file named `libcurl.a`
located in the `lib` directory. Before PHP 5.5.0 it was possible to
configure PHP to use cURL for URL streams **--with-curlwrappers**.

> **Note**: **Note to Win32 Users**  
> <span class="simpara"> In order to enable this module on a Windows
> environment, `libeay32.dll` and `ssleay32.dll`, or, as of OpenSSL 1.1
> `libcrypto-*.dll` and `libssl-*.dll`, must be present in your `PATH`.
> Also `libssh2.dll` must be present in your `PATH`. </span> <span
> class="simpara"> You don't need `libcurl.dll` from the cURL site.
> </span>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                     | Default | Changeable       | Changelog                  |
|----------------------------------------------------------|---------|------------------|----------------------------|
| <a href="/curl/setup.html#" class="link">curl.cainfo</a> | NULL    | PHP\_INI\_SYSTEM | Available since PHP 5.3.7. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`curl.cainfo` <span class="type">string</span>  
A default value for the **`CURLOPT_CAINFO`** option. This is required to
be an absolute path.

Resource Types
--------------

This extension defines two resource types: a cURL handle and a cURL
multi handle.

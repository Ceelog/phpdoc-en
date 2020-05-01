Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/ldap/setup.html#Requirements)
-   [Installation](/ldap/setup.html#Installation)
-   [Runtime Configuration](/ldap/setup.html#Runtime%20Configuration)
-   [Resource Types](/ldap/setup.html#Resource%20Types)

Requirements
------------

You will need to get and compile LDAP client libraries from either
<a href="ftp://ftp.openldap.org/pub/OpenLDAP/openldap-stable/" class="link external">» OpenLDAP</a>
or
<a href="http://www.bind9.net/download-openldap/" class="link external">» Bind9.net</a>
in order to compile PHP with LDAP support. For PHP 5.6 or newer you will
need OpenLDAP 2.4 or newer.

Installation
------------

LDAP support in PHP is not enabled by default. You will need to use the
**--with-ldap\[=DIR\]** configuration option when compiling PHP to
enable LDAP support. DIR is the LDAP base install directory. To enable
SASL support, be sure **--with-ldap-sasl\[=DIR\]** is used, and that
`sasl.h` exists on the system.

> **Note**: **Note to Win32 Users**  
>
> In order for this extension to work, there are DLL files that must be
> available to the Windows system `PATH`. For information on how to do
> this, see the FAQ entitled
> "<a href="/faq/installation.html#faq.installation.addtopath" class="link">How do I add my PHP directory to the PATH on Windows</a>".
> Although copying DLL files from the PHP folder into the Windows system
> directory also works (because the system directory is by default in
> the system's `PATH`), this is not recommended. *This extension
> requires the following files to be in the `PATH`:* `libeay32.dll` and
> `ssleay32.dll`, or, as of OpenSSL 1.1 `libcrypto-*.dll` and
> `libssl-*.dll`

In order to use Oracle LDAP libraries, proper
<a href="/book/oci8.html#Requirements" class="link">Oracle environment</a>
has to be set.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                        | Default | Changeable       | Changelog |
|-------------------------------------------------------------|---------|------------------|-----------|
| <a href="/ldap/setup.html#" class="link">ldap.max_links</a> | "-1"    | PHP\_INI\_SYSTEM |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`ldap.max_links` <span class="type">integer</span>  
The maximum number of LDAP connections per process.

Resource Types
--------------

Most LDAP functions operate on or return resources (e.g. <span
class="function">ldap\_connect</span> returns a positive LDAP link
identifier required by most LDAP functions).

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/imap/setup.html#Requirements)
-   [Installation](/imap/setup.html#Installation)
-   [Runtime Configuration](/imap/setup.html#Runtime%20Configuration)
-   [Resource Types](/imap/setup.html#Resource%20Types)

Requirements
------------

This extension requires the c-client library to be installed. Grab the
latest version from
<a href="https://www.washington.edu/imap/" class="link external">» https://www.washington.edu/imap/</a>
and compile it.

It's important that you do not copy the IMAP source files directly into
the system include directory as there may be conflicts. Instead, create
a new directory inside the system include directory, such as
`/usr/local/imap-2000b/` (location and name depend on your setup and
IMAP version), and inside this new directory create additional
directories named `lib/` and `include/`. From the `c-client` directory
from your IMAP source tree, copy all the `*.h` files into `include/` and
all the `*.c` files into `lib/`. Additionally when you compiled IMAP, a
file named `c-client.a` was created. Also put this in the `lib/`
directory but rename it as `libc-client.a`.

> **Note**:
>
> To build the c-client library with SSL or/and Kerberos support read
> the docs supplied with the package.

> **Note**: <span class="simpara"> In Mandrake Linux, the IMAP library
> (`libc-client.a`) is compiled without Kerberos support. A separate
> version with SSL (`client-PHP4.a`) is installed. The library must be
> recompiled in order to add Kerberos support. </span>

Installation
------------

To get these functions to work, you have to compile PHP with
**--with-imap\[=DIR\]**, where DIR is the c-client install prefix. From
our example above, you would use **--with-imap=/usr/local/imap-2000b**.
This location depends on where you created this directory according to
the description above. <span class="productname">Windows</span> users
may include the `php_imap.dll` DLL in `php.ini`.

> **Note**: <span class="simpara"> Depending on how the c-client was
> configured, you might also need to add
> **--with-imap-ssl=/path/to/openssl/** and/or
> **--with-kerberos=/path/to/kerberos** to the PHP configure line.
> </span>

**Warning**

The IMAP extension is not thread-safe; it should not be used with ZTS
builds.

**Warning**

The <a href="/book/imap.html" class="link">IMAP</a>,
<a href="/book/recode.html" class="link">recode</a> and
<a href="/book/yaz.html" class="link">YAZ</a> extensions cannot be used
in conjunction, because they share the same internal symbols. Note: Yaz
2.0 and above does not suffer from this problem.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                  | Default | Changeable       | Changelog                                                                          |
|-----------------------------------------------------------------------|---------|------------------|------------------------------------------------------------------------------------|
| <a href="/imap/setup.html#" class="link">imap.enable_insecure_rsh</a> | "0"     | PHP\_INI\_SYSTEM | Available as of PHP 7.1.25, 7.2.13 and 7.3.0. Formerly, it was implicitly enabled. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`imap.enable_insecure_rsh` <span class="type">bool</span>  
Establishing a connection to a server may invoke **rsh** or **ssh**
commands, unless this `php.ini` option is disabled.

**Warning**
Neither PHP nor the IMAP library filter mailbox names before passing
them to **rsh** or **ssh** commands, thus passing untrusted data to this
function without disabling this `php.ini` option is *insecure*.

Resource Types
--------------

The *imap* resource as returned by <span
class="function">imap\_open</span> references an opened IMAP stream.

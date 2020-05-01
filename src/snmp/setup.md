Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/snmp/setup.html#Requirements)
-   [Installation](/snmp/setup.html#Installation)
-   [Runtime Configuration](/snmp/setup.html#Runtime%20Configuration)
-   [Resource Types](/snmp/setup.html#Resource%20Types)

Requirements
------------

In order to use the SNMP functions requires installation of the
<a href="http://www.net-snmp.org/" class="link external">» Net-SNMP</a>
package. SNMPv3 functions available only when
<a href="http://www.openssl.org/" class="link external">» OpenSSL</a>
package is installed too.

Beginning with PHP 5.4.0 Net-SNMP version 5.3+ is required for Unix
installations and Net-SNMP version 5.4+ for Windows.

Installation
------------

PHP 5.3.0, 5.3.1 and 5.3.2 do not have SNMP support. SNMP support has
been restored in PHP 5.3.3.

The Windows distribution of Net-SNMP contains support files for SNMP in
the `mibs` directory. This directory should added to Windows'
environment variables, as MIBDIRS, with the value being the full path to
the `mibs` directory: e.g. `c:\usr\mibs`.

Important notes for PHP prior to 5.4.0: In order to use the UCD SNMP
package, you need to define *NO\_ZEROLENGTH\_COMMUNITY* to *1* before
compiling it. After configuring UCD SNMP, edit `config.h` or
`acconfig.h` and search for *NO\_ZEROLENGTH\_COMMUNITY*. Uncomment the
*\#define* line. It should look like this afterwards:

``` c
#define NO_ZEROLENGTH_COMMUNITY 1
```

Now compile PHP **--with-snmp\[=DIR\]**.

If you see strange segmentation faults in combination with SNMP
commands, you did not follow the above instructions. If you do not want
to recompile UCD SNMP, you can compile PHP with the
**--enable-ucd-snmp-hack** switch which will work around the misfeature.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

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

Net-SNMP version 5.3+ is required for Unix installations and Net-SNMP
version 5.4+ for Windows.

Installation
------------

The Windows distribution of Net-SNMP contains support files for SNMP in
the `mibs` directory. This directory should added to Windows'
environment variables, as MIBDIRS, with the value being the full path to
the `mibs` directory: e.g. `c:\usr\mibs`.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

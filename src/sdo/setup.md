Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/sdo/setup.html#Requirements)
-   [Installation](/sdo/setup.html#Installation)
-   [Runtime Configuration](/sdo/setup.html#Runtime%20Configuration)
-   [Resource Types](/sdo/setup.html#Resource%20Types)

Requirements
------------

The SDO extension requires PHP 5.1.0 or higher. It also requires the
libxml2 library. Normally libxml2 will already be installed, but if not,
it can be downloaded from
<a href="http://www.xmlsoft.org/" class="link external">» http://www.xmlsoft.org/</a>.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/sca_sdo" class="link external">» https://pecl.php.net/package/sca_sdo</a>.

> **Note**:
>
> Earlier versions of the SDO extension required a separate shared
> library for the XML DAS. This is now obsolete and any references to
> `php_sdo_das_xml.dll` or `sdo_das_xml.so` should be removed from your
> `php.ini`.

**Unix systems**

1.  The three SDO components - the SDO core, the XML DAS and the
    Relational DAS - are packaged together with *Service Component
    Architecture (SCA)* into one PECL project, SCA\_SDO, so you can
    download SCA and all three parts of SDO with the command:

        pecl install SCA_SDO

    This command will build the SDO shared library as well as installing
    the PHP files that make up SCA and the SDO Relational DAS.

    If you want to use the latest beta version, then instead run:

        pecl install SCA_SDO-beta

2.  The **pecl** command automatically installs the SDO module into your
    PHP extensions directory. To enable the SDO extension you must add
    the following line to `php.ini`:

        extension=sdo.so

    For more information about building PECL packages, consult the
    <a href="/install/pecl.html" class="link">PECL installation</a>
    section of the manual.

**Building SDO on Linux**

This section describes how to build the SDO core and XML DAS on Linux.
You would only need to know how to do this if you wish to build a recent
version that you have checked out of SVN.

1.  Change to the main extension directory: **cd \< wherever your sdo
    code is \>**

2.  Run **phpize**, which will set up the environment to compile SDO.

3.  Next, run **./configure; make; make install**. Please note, you may
    need to login as root to install the extension.

4.  Make sure that the module is loaded by PHP, by adding
    `extension=sdo.so` to your `php.ini` file.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

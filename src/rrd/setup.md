Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/rrd/setup.html#Requirements)
-   [Installation](/rrd/setup.html#Installation)
-   [Runtime Configuration](/rrd/setup.html#Runtime%20Configuration)
-   [Resource Types](/rrd/setup.html#Resource%20Types)

Requirements
------------

You need to install librrd first to be able to use PECL/rrd. Most common
option is using of librrd-dev package from your favourite linux distro.
PECL/rrd is tested with librrd 1.4.3, older or newer versions might or
might not work for you. PECL/rrd installation is tested with PHP 5.3.2
or newer.

**Warning**

Librrd and hence extension itself aren't mostly thread safe. There are
many global and shared states in librrd. It can be dangerous use this
extension in multi threaded environments like Apache2 mpm worker. If
there are many parallel requests, one request can change some global
librrd state of other runnig requests.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/rrd" class="link external">» https://pecl.php.net/package/rrd</a>.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/luasandbox/setup.html#Requirements)
-   [Installation](/luasandbox/setup.html#Installation)
-   [Runtime
    Configuration](/luasandbox/setup.html#Runtime%20Configuration)
-   [Resource Types](/luasandbox/setup.html#Resource%20Types)

Requirements
------------

To use this extension, Lua 5.1 will need to be installed, available on
the
<a href="http://www.lua.org/" class="link external">» Lua homepage</a>.

To make full use of the timer features, LuaSandbox should be installed
on Linux.

If FreeBSD or Mac OS X is used, only real (wall-clock) time is
supported, the functions purporting to return CPU time will actually
return wall clock time.

If Windows is used, no timer functions will be supported. The time
limits will be inoperable.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/luasandbox" class="link external">» https://pecl.php.net/package/luasandbox</a>.

If the operating system is Debian 9 or later, or Ubuntu 18.04 or later,
then LuaSandbox should typically be installed from the package
*php-luasandbox*:

    sudo apt-get install php-luasandbox

Debian 9 users may need to add

    deb http://ftp.debian.org/debian stretch-backports main

to their
<a href="https://manpages.debian.org/stretch/apt/sources.list.5.en.html" class="link external">» sources.list</a>.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

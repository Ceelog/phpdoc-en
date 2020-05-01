Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/judy/setup.html#Requirements)
-   [Installation](/judy/setup.html#Installation)
-   [Runtime Configuration](/judy/setup.html#Runtime%20Configuration)
-   [Resource Types](/judy/setup.html#Resource%20Types)

Requirements
------------

This extension require the
<a href="http://judy.sourceforge.net" class="link external">» Judy C library</a>.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/judy" class="link external">» https://pecl.php.net/package/judy</a>

Installation on Linux Systems
-----------------------------

From sources
------------

Download and install
<a href="http://judy.sourceforge.net" class="link external">» libJudy</a>,
then :

         phpize
         ./configure --with-judy[=DIR]
         make
         make test
         make install
        

Ubuntu/Debian
-------------

libJudy can be installed with apt-get :

        apt-get install libjudydebian1 libjudy-dev
        

Then by installing the Judy extension from PECL or from the sources.

Installation on Windows Systems
-------------------------------

Download
<a href="http://judy.sourceforge.net" class="link external">» libJudy</a>,
then extract the sources and open the Visual Studio command prompt and
navigate to the source directory. Then execute :

    build

This creates "Judy.lib", copy this into the php-sdk library folder and
name it "libJudy.lib" Then copy the include file "judy.h" into the
php-sdk includes folder.

Next, the PHP Judy extension can be installed from PECL or from the
sources by extracting the pecl/judy into your build folder where the
build scripts will be able to pick it up, e.g.:

        C:\php\pecl\judy\
       

If your source of PHP is located in:

        C:\php\src\
       

The rest of the steps is pretty straight forward, like any other
external extension:

        buildconf
        configure --with-judy=shared
        nmake
       

Installation on macOS
---------------------

Download and install
<a href="http://judy.sourceforge.net" class="link external">» libJudy</a>.
Then install the Judy extension from PECL or from the sources.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

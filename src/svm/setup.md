Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/svm/setup.html#Requirements)
-   [Installation](/svm/setup.html#Installation)
-   [Runtime Configuration](/svm/setup.html#Runtime%20Configuration)
-   [Resource Types](/svm/setup.html#Resource%20Types)

Requirements
------------

Libsvm itself is required, and is available through some package
management - libsvm-devel for RPM based system or libsvm-dev for Debian
based ones. Alternatively it is available direct from the website. If
installing from the
<a href="http://www.csie.ntu.edu.tw/~cjlin/libsvm" class="link external">» official website</a>
then some steps will need to be taken as the package does not install
automatically. For example, assuming the latest version is 3.1:

    wget http://www.csie.ntu.edu.tw/~cjlin/cgi-bin/libsvm.cgi?+http://www.csie.ntu.edu.tw/~cjlin/libsvm+tar.gz 
    tar xvzf libsvm-3.1.tar.gz 
    cd libsvm-3.1
    make lib 
    cp libsvm.so.1 /usr/lib 
    ln -s libsvm.so.1 libsvm.so 
    ldconfig 
    ldconfig --print | grep libsvm

This last step should show libsvm is installed.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/svm" class="link external">» https://pecl.php.net/package/svm</a>

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

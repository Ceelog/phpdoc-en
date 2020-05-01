Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/svn/setup.html#Requirements)
-   [Installation](/svn/setup.html#Installation)
-   [Runtime Configuration](/svn/setup.html#Runtime%20Configuration)
-   [Resource Types](/svn/setup.html#Resource%20Types)

Requirements
------------

The Subversion binaries are not necessary to use this extension.
However, when compiling the extension, libsvn (the Subversion headers)
must be available.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/svn" class="link external">» https://pecl.php.net/package/svn</a>

If `./configure` is having trouble finding the SVN files (for example,
Subversion was installed with a different prefix directory), use
**`./configure --with-svn=$USR_PATH`** to specify the directory where
the `include/subversion-1/` folder is located.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

**Warning**

If the extension is compiled against libsvn 1.3, functions that work
with working copies will fail when used on working copies created by
Subversion 1.4.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

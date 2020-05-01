Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/pdf/setup.html#Requirements)
-   [Installation](/pdf/setup.html#Installation)
-   [Runtime Configuration](/pdf/setup.html#Runtime%20Configuration)
-   [Resource Types](/pdf/setup.html#Resource%20Types)

Requirements
------------

PDFlib Lite is available as open source. However, the PDFlib Lite
license allows free use only under certain conditions. PDFlib Lite
supports a subset of PDFlib's functionality; please see the PDFlib web
site for details. The full version of PDFlib is available for download
at
<a href="http://www.pdflib.com/products/pdflib-family/" class="link external">» http://www.pdflib.com/products/pdflib-family/</a>,
but requires that you purchase a license for commercial use.

Issues with older versions of PDFlib
------------------------------------

Any version of PHP 4 after March 9, 2000 does not support versions of
PDFlib older than 3.0.

PDFlib 4.0 or greater is supported by PHP 4.3.0 and later.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP. Information for installing this PECL
extension may be found in the manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/pdflib" class="link external">» https://pecl.php.net/package/pdflib</a>.

To get these functions to work in PHP \< 4.3.9, you have to compile PHP
with **--with-pdflib\[=DIR\]**. DIR is the PDFlib base install
directory, defaults to `/usr/local`.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

<span class="function">PDF\_new</span> creates a new PDFlib object
required by most PDF functions.

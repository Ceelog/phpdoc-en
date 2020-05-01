Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/fam/setup.html#Requirements)
-   [Installation](/fam/setup.html#Installation)
-   [Runtime Configuration](/fam/setup.html#Runtime%20Configuration)
-   [Resource Types](/fam/setup.html#Resource%20Types)

Requirements
------------

This extension uses the functions of the
<a href="https://web.archive.org/web/20050806075734/http://oss.sgi.com:80/projects/fam/download.html" class="link external">»  FAM</a>
library, developed by SGI. Therefore you have to download and install
the FAM library.

Installation
------------

This extension is considered unmaintained and dead. However, the source
code for this extension is still available within PECL SVN here:
<a href="https://svn.php.net/viewvc/pecl/fam" class="link external">» https://svn.php.net/viewvc/pecl/fam</a>.

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 5.1.0

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

There are two resource types used in the FAM module. The first one is
the connection to the FAM service returned by <span
class="function">fam\_open</span>, the second a monitoring resource
returned by the *fam\_monitor\_XXX* functions.

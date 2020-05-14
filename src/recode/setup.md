Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/recode/setup.html#Requirements)
-   [Installation](/recode/setup.html#Installation)
-   [Runtime Configuration](/recode/setup.html#Runtime%20Configuration)
-   [Resource Types](/recode/setup.html#Resource%20Types)

Requirements
------------

You must have GNU Recode 3.5 or higher installed on your system. You can
download the package from
<a href="http://directory.fsf.org/All_GNU_Packages/recode.html" class="link external">» http://directory.fsf.org/All_GNU_Packages/recode.html</a>.

**Warning**

The Recode library version 3.6 adds weird characters behind converted
strings under certain circumstances. Thus it's safer to use Recode v3.5
or one of the available alternatives like the
<a href="/ref/iconv.html" class="link">iconv</a> or
<a href="/ref/mbstring.html" class="link">mbstring</a> extension.

Installation
------------

PHP 7.4
-------

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 7.4.0

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/recode" class="link external">» https://pecl.php.net/package/recode</a>.

PHP \< 7.4
----------

To be able to use the functions defined in this module you must compile
your PHP interpreter using the **--with-recode\[=DIR\]** option.

**Warning**

Crashes and startup problems of PHP may be encountered when loading the
recode as extension *after* loading any extension of
<a href="/set/mysqlinfo.html#MySQL%20Functions" class="link">mysql</a>
or <a href="/ref/imap.html" class="link">imap</a>. Loading the recode
before those extension has proved to fix the problem. This is due a
technical problem that both the c-client library used by imap and recode
have their own *hash\_lookup()* function and both mysql and recode have
their own *hash\_insert* function.

**Warning**

The <a href="/book/imap.html" class="link">IMAP</a>,
<a href="/book/recode.html" class="link">recode</a>,
<a href="/book/yaz.html" class="link">YAZ</a> and
<a href="/book/cyrus.html" class="link">Cyrus</a> extensions cannot be
used in conjunction, because they share the same internal symbols. Note:
Yaz 2.0 and above does not suffer from this problem.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

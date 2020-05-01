Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/cyrus/setup.html#Requirements)
-   [Installation](/cyrus/setup.html#Installation)
-   [Runtime Configuration](/cyrus/setup.html#Runtime%20Configuration)
-   [Resource Types](/cyrus/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

To enable Cyrus IMAP support and to use these functions you have to
compile PHP with the **--with-cyrus** option.

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

This extension defines a Cyrus IMAP connection identifier returned by
<span class="function">cyrus\_connect</span>.

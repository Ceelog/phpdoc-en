Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/enchant/setup.html#Requirements)
-   [Installation](/enchant/setup.html#Installation)
-   [Runtime Configuration](/enchant/setup.html#Runtime%20Configuration)
-   [Resource Types](/enchant/setup.html#Resource%20Types)

Requirements
------------

This version uses the functions of the
<a href="http://www.abisource.com/projects/enchant/" class="link external">» Enchant library</a>
by Dom Lachowicz. You need Enchant 1.2.4 or later. Enchant 2.0.0 or
later is not yet supported.

Enchant also requires
<a href="http://ftp.gnome.org/pub/gnome/sources/glib/" class="link external">» Glib 2.6</a>
or greater. Pre-compiled Windows libraries are available from
<a href="http://ftp.gnome.org/pub/gnome/binaries/win32/glib/" class="link external">» http://ftp.gnome.org/pub/gnome/binaries/win32/glib/</a>.

Installation
------------

This extension is bundled with PHP as of PHP 5.3.0. Before this time,
enchant was a PECL extension. Users of versions prior to 5.3.0 may use
the
<a href="https://pecl.php.net/package/enchant" class="link external">» PECL extension</a>.

Provided the
<a href="/enchant/setup.html#Requirements" class="link">required libraries</a>
are installed, users of PHP 5.3.0 or later may enable enchant by adding
the **--with-enchant\[=dir\]** option when compiling PHP.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

There are two types of resources in this extension. The first one is the
broker (backends manager) and the second is for the dictionary.

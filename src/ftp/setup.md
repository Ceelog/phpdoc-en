Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/ftp/setup.html#Requirements)
-   [Installation](/ftp/setup.html#Installation)
-   [Runtime Configuration](/ftp/setup.html#Runtime%20Configuration)
-   [Resource Types](/ftp/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

In order to use FTP functions with your PHP configuration, you should
add the **--enable-ftp** option when installing PHP.

The Windows version of PHP 5 has built-in support for this extension.
You do not need to load any additional extensions in order to use these
functions.

As of PHP 7.0.0 on Windows this extension is always built as shared
extension and as such has to be enabled in `php.ini`.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension uses one resource type, which is the link identifier of
the FTP connection, returned by <span
class="function">ftp\_connect</span> or <span
class="function">ftp\_ssl\_connect</span>.

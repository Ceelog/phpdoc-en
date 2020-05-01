Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/pcntl/setup.html#Requirements)
-   [Installation](/pcntl/setup.html#Installation)
-   [Runtime Configuration](/pcntl/setup.html#Runtime%20Configuration)
-   [Resource Types](/pcntl/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

Process Control support in PHP is not enabled by default. You have to
compile the CGI or CLI version of PHP with **--enable-pcntl**
configuration option when compiling PHP to enable Process Control
support.

> **Note**:
>
> Currently, this module will not function on non-Unix platforms
> (Windows).

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/shmop/setup.html#Requirements)
-   [Installation](/shmop/setup.html#Installation)
-   [Runtime Configuration](/shmop/setup.html#Runtime%20Configuration)
-   [Resource Types](/shmop/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

To use shmop you will need to compile PHP with the **--enable-shmop**
parameter in your configure line.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

As of PHP 7.0.0 this extension defines the resource type *shmop* which
is a handle to a shared memory block.

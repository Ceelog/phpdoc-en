Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/stream/setup.html#Requirements)
-   [Installation](/stream/setup.html#Installation)
-   [Runtime Configuration](/stream/setup.html#Runtime%20Configuration)
-   [Stream Classes](/stream/setup.html#Stream%20Classes)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Stream Classes
--------------

User designed wrappers can be registered via <span
class="function">stream\_wrapper\_register</span>, using the class
definition shown on that manual page.

Class <span class="classname">php\_user\_filter</span> is predefined and
is an abstract baseclass for use with user defined filters. See the
manual page for <span class="function">stream\_filter\_register</span>
for details on implementing user defined filters.

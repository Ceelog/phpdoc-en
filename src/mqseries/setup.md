Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mqseries/setup.html#Requirements)
-   [Installation](/mqseries/setup.html#Installation)
-   [Runtime
    Configuration](/mqseries/setup.html#Runtime%20Configuration)
-   [Resource Types](/mqseries/setup.html#Resource%20Types)

Requirements
------------

A working IBM WebSphere MQ installation. If building the extension the
SDK for IBM WebSphere MQ is also required.

> **Note**: <span class="simpara"> Be aware that when running against a
> IBM WebSphere MQ Client installation some methods are not available.
> This is not a problem of the extension but just the way the WebSphere
> MQ Client Interface works. </span>

Installation requirements on non windows platforms
--------------------------------------------------

Build the extension and put it in the PHP extension directory.

Installation requirements on Windows
------------------------------------

No additional requirements.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/mqseries" class="link external">» https://pecl.php.net/package/mqseries</a>.

> **Note**: <span class="simpara"> The official name of this extension
> is *mqseries*. </span>

There are two ways to connect to a queue manager. These depend on the
way the extension is compiled and linked.

-   First one and also the default one is using the mqic libraries.
    Compiling and linking the extension against these IBM WebSphere
    MQSeries libraries allows the extension to connect to the Queue
    manager using the client interface. Remote connections are possible
    this way.

-   The other way is to compile and link against the mqm libraries.
    Using these libraries it is possible to make use of the transaction
    management of a queue manager.

Currently selecting the libraries to use is done by changing the
`config.m4` file.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

There are no extra configuration parameters.

Resource Types
--------------

This extension defines a connection and object\_handle resources.

The <span class="function">mqseries\_conn</span> and <span
class="function">mqseries\_connx</span> define the connectionn handles.

The <span class="function">mqseries\_open</span> defines the object
handle.

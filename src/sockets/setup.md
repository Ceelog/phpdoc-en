Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/sockets/setup.html#Requirements)
-   [Installation](/sockets/setup.html#Installation)
-   [Runtime Configuration](/sockets/setup.html#Runtime%20Configuration)
-   [Resource Types](/sockets/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

The socket functions described here are part of an extension to PHP
which must be enabled at compile time by giving the **--enable-sockets**
option to **configure**.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

<span class="function">socket\_accept</span>, <span
class="function">socket\_import\_stream</span>, <span
class="function">socket\_addrinfo\_connect</span>, <span
class="function">socket\_addrinfo\_bind</span>, <span
class="function">socket\_create\_listen</span>, <span
class="function">socket\_wsaprotocol\_info\_import</span> and <span
class="function">socket\_create</span> return Socket resources.

<span class="function">socket\_addrinfo\_lookup</span> returns an array
of AddressInfo resources.

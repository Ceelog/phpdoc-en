Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/rar/setup.html#Requirements)
-   [Installation](/rar/setup.html#Installation)
-   [Runtime Configuration](/rar/setup.html#Runtime%20Configuration)
-   [Resource Types](/rar/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

Rar is currently available through PECL
<a href="https://pecl.php.net/package/rar" class="link external">» https://pecl.php.net/package/rar</a>.

Also you can use the PECL installer to install the Rar extension, using
the following command: **pecl -v install rar**.

You can always download the `tar.gz` package and install Rar by hand:

**Example \#1 Rar installation**

``` shell
gunzip rar-xxx.tgz
tar -xvf rar-xxx.tar
cd rar-xxx
phpize
./configure && make && make install
```

Windows users will enable `php_rar.dll` inside of `php.ini` in order to
use these functions. A DLL for this PECL extension is currently
unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension registers three internal classes: The archive
representations returned by <span class="function">rar\_open</span> –
<span class="type">RarArchive</span> –, the entry representations
returned by <span class="function">rar\_list</span> and <span
class="function">rar\_entry\_get</span> – <span
class="type">RarEntry</span> and the exception type <span
class="type">RarException</span>.

This extension also register a stream resource, called "rar" and a URL
wrapper called "rar wrapper" and registered under the prefix "rar".

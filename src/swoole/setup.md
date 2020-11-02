Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/swoole/setup.html#Requirements)
-   [Installation](/swoole/setup.html#Installation)
-   [Runtime Configuration](/swoole/setup.html#Runtime%20Configuration)
-   [Resource Types](/swoole/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

Use **--with-swoole\[=DIR\]** when compiling PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/swoole" class="link external">» https://pecl.php.net/package/swoole</a>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                       | Default | Changeable       | Changelog |
|----------------------------------------------------------------------------|---------|------------------|-----------|
| <a href="/swoole/setup.html#" class="link">swoole.aio_thread_num</a>       | 2       | PHP\_INI\_ALL    |           |
| <a href="/swoole/setup.html#" class="link">swoole.display_errors</a>       | On      | PHP\_INI\_ALL    |           |
| <a href="/swoole/setup.html#" class="link">swoole.fast_serialize</a>       | Off     | PHP\_INI\_ALL    |           |
| <a href="/swoole/setup.html#" class="link">swoole.unixsock_buffer_size</a> | 8388608 | PHP\_INI\_ALL    |           |
| <a href="/swoole/setup.html#" class="link">swoole.use_namespace</a>        | On      | PHP\_INI\_SYSTEM |           |

Here's a short explanation of the configuration directives.

`swoole.aio_thread_num` <span class="type">int</span>  
POSIX asynchronous I/O thread number

`swoole.display_errors` <span class="type">string</span>  
This determines whether Swoole errors should be printed to the screen.

`swoole.fast_serialize` <span class="type">string</span>  
Whether to enable Swoole fast\_serialize.

`swoole.unixsock_buffer_size` <span class="type">int</span>  
Buffer size of Unix socket.

`swoole.use_namespace` <span class="type">string</span>  
Whether to use PHP namespaces

Resource Types
--------------

This extension has no resource types defined.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/memcache/setup.html#Requirements)
-   [Installation](/memcache/setup.html#Installation)
-   [Runtime
    Configuration](/memcache/setup.html#Runtime%20Configuration)
-   [Resource Types](/memcache/setup.html#Resource%20Types)

Requirements
------------

This module uses functions of
<a href="http://www.zlib.net/" class="link external">» zlib</a> to
support on-the-fly data compression. Zlib is required to install this
module.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP. Information for installing this PECL
extension may be found in the manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/memcache" class="link external">» https://pecl.php.net/package/memcache</a>.

> **Note**:
>
> It's possible to disable memcache session handler support. The 'pecl
> install' option prompts for this (default is enabled) however when
> compiling statically into PHP the **--disable-memcache-session**
> configure option may be used.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                            | Default    | Changeable      | Changelog                       |
|---------------------------------------------------------------------------------|------------|-----------------|---------------------------------|
| <a href="/memcache/setup.html#" class="link">memcache.allow_failover</a>        | "1"        | PHP\_INI\_ALL   | Available since memcache 2.0.2. |
| <a href="/memcache/setup.html#" class="link">memcache.max_failover_attempts</a> | "20"       | PHP\_INI\_ALL   | Available since memcache 2.1.0. |
| <a href="/memcache/setup.html#" class="link">memcache.chunk_size</a>            | "8192"     | PHP\_INI\_ALL   | Available since memcache 2.0.2. |
| <a href="/memcache/setup.html#" class="link">memcache.default_port</a>          | "11211"    | PHP\_INI\_ALL   | Available since memcache 2.0.2. |
| <a href="/memcache/setup.html#" class="link">memcache.hash_strategy</a>         | "standard" | PHP\_INI\_ALL   | Available since memcache 2.2.0. |
| <a href="/memcache/setup.html#" class="link">memcache.hash_function</a>         | "crc32"    | PHP\_INI\_ALL   | Available since memcache 2.2.0. |
| <a href="/session/setup.html#" class="link">session.save_handler</a>            | "files"    | PHP\_INI\_ALL   | Supported since memcache 2.1.2  |
| <a href="/session/setup.html#" class="link">session.save_path</a>               | ""         | PHP\_INI\_ALL   | Supported since memcache 2.1.2  |
| <a href="/memcache/setup.html#" class="link">memcache.protocol</a>              | ascii      | \>PHP\_INI\_ALL | Supported since memcache 3.0.0  |
| <a href="/memcache/setup.html#" class="link">memcache.redundancy</a>            | 1          | \>PHP\_INI\_ALL | Supported since memcache 3.0.0  |
| <a href="/memcache/setup.html#" class="link">memcache.session_redundancy</a>    | 2          | \>PHP\_INI\_ALL | Supported since memcache 3.0.0  |
| <a href="/memcache/setup.html#" class="link">memcache.compress_threshold</a>    | 20000      | \>PHP\_INI\_ALL | Supported since memcache 3.0.3  |
| <a href="/memcache/setup.html#" class="link">memcache.lock_timeout</a>          | 15         | \>PHP\_INI\_ALL | Supported since memcache 3.0.4  |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`memcache.allow_failover` <span class="type">boolean</span>  
Whether to transparently failover to other servers on errors.

`memcache.max_failover_attempts` <span class="type">integer</span>  
Defines how many servers to try when setting and getting data. Used only
in conjunction with memcache.allow\_failover.

`memcache.chunk_size` <span class="type">integer</span>  
Data will be transferred in chunks of this size, setting the value lower
requires more network writes. Try increasing this value to 32768 if
noticing otherwise inexplicable slowdowns.

`memcache.default_port` <span class="type">string</span>  
The default TCP port number to use when connecting to the memcached
server if no other port is specified.

`memcache.hash_strategy` <span class="type">string</span>  
Controls which strategy to use when mapping keys to servers. Set this
value to *consistent* to enable consistent hashing which allows servers
to be added or removed from the pool without causing keys to be
remapped. Setting this value to *standard* results in the old strategy
being used.

`memcache.hash_function` <span class="type">string</span>  
Controls which hash function to apply when mapping keys to servers,
*crc32* uses the standard CRC32 hash while *fnv* uses FNV-1a.

`session.save_handler` <span class="type">string</span>  
Use memcache as a session handler by setting this value to *memcache*.

`session.save_path` <span class="type">string</span>  
Defines a comma separated of server urls to use for session storage, for
example *"tcp://host1:11211, tcp://host2:11211"*.

Each url may contain parameters which are applied to that server, they
are the same as for the <span
class="function">Memcache::addServer</span> method. For example
*"tcp://host1:11211?persistent=1&weight=1&timeout=1&retry\_interval=15"*

`memcache.protocol` <span class="type">string</span>  

`memcache.redundancy` <span class="type">integer</span>  

`memcache.session_redundancy` <span class="type">integer</span>  

`memcache.compress_threshold` <span class="type">integer</span>  

`memcache.lock_timeout` <span class="type">integer</span>  

Resource Types
--------------

There is only one resource type used in memcache module - it's the link
identifier for a cache server connection.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/memcached/setup.html#Requirements)
-   [Installation](/memcached/setup.html#Installation)
-   [Runtime
    Configuration](/memcached/setup.html#Runtime%20Configuration)
-   [Resource Types](/memcached/setup.html#Resource%20Types)

Requirements
------------

This extension requires
<a href="http://libmemcached.org/libMemcached.html" class="link external">» libmemcached</a>
client library (version 1.0.0 or greater). For SASL authentication
support, libmemcached must be built with SASL enabled.

Since version 0.2.0, this extension requires PHP version 5.2.0 or
higher.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/memcached" class="link external">» https://pecl.php.net/package/memcached</a>.

If libmemcached is installed in a non-standard location, use
**--with-libmemcached-dir=DIR** switch, where DIR is the libmemcached
install prefix. This directory has to contain the
`include/libmemcached/memcached.h` file.

Zlib is required for compression support. To specify non-standard
installation of Zlib, use **--with-zlib-dir=DIR** switch, where DIR is
the Zlib install prefix.

Session handler support is enabled by default. To disable it, use
**--disable-memcached-session** switch.

SASL authentication support is disabled by default. To enable it, use
**--enable-memcached-sasl** switch. This requires that libsasl2 has been
installed and that libmemcached has been built with SASL support
enabled.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                                    | Default        | Changeable       | Changelog |
|-----------------------------------------------------------------------------------------|----------------|------------------|-----------|
| <a href="/memcached/setup.html#" class="link">memcached.sess_locking</a>                | 1              | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.sess_consistent_hash</a>        | 0              | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.sess_binary</a>                 | 0              | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.sess_lock_wait</a>              | 150000         | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.sess_prefix</a>                 | memc.sess.key. | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.sess_number_of_replicas</a>     | 0              | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.sess_randomize_replica_read</a> | 0              | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.sess_remove_failed</a>          | 0              | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.compression_type</a>            | fastlz         | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.compression_factor</a>          | 1.3            | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.compression_threshold</a>       | 2000           | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.serializer</a>                  | php            | PHP\_INI\_ALL    |           |
| <a href="/memcached/setup.html#" class="link">memcached.use_sasl</a>                    | 0              | PHP\_INI\_SYSTEM |           |

Here's a short explanation of the configuration directives.

`memcached.sess_locking` <span class="type">int</span>  
Use session locking. Valid values: On, Off, the default is On.

`memcached.sess_consistent_hash` <span class="type">int</span>  
Memcached session consistent hash mode. If set to On, consistent hashing
is used for session handling. When consistent hashing is used, one can
add or remove cache node(s) without messing up too much with existing
keys. The default is Off.

`memcached.sess_binary` <span class="type">int</span>  
Use memcached session binary mode. Libmemcached replicas only work if
binary mode is enabled. The default is Off.

`memcached.sess_lock_wait` <span class="type">int</span>  
Session spin lock retry wait time in microseconds. Be careful when
setting this value. Valid values are integers, where 0 is interpreted as
the default value. Negative values result in a reduces locking to a try
lock. The default is 150000.

`memcached.sess_prefix` <span class="type">string</span>  
Memcached session key prefix. Valid values are strings less than 219
bytes long. The default value is "memc.sess.key."

`memcached.sess_number_of_replicas` <span class="type">int</span>  
The memcached session number of replicas.

`memcached.sess_randomize_replica_read` <span class="type">int</span>  
Memcached session replica read randomize.

`memcached.sess_remove_failed` <span class="type">int</span>  
Allow failed memcached server to automatically be removed.

`memcached.compression_type` <span class="type">string</span>  
Set the compression type, valid values are: fastlz, zlib. The default is
fastlz.

`memcached.compression_factor` <span class="type">float</span>  
Compression factor. Store compressed value only if the compression
factor (saving) exceeds the set limit. Store compressed if:
*plain\_len \> comp\_len \* factor*. The default value is 1.3 (23% space
saving).

`memcached.compression_threshold` <span class="type">int</span>  
The compression threshold. Do not compress serialized values below this
threshold. The default is 2000 bytes.

`memcached.serializer` <span class="type">string</span>  
Set the default serializer for new memcached objects. Valid values are:
php, igbinary, json, json\_array.

json  
Standard php JSON encoding. This serializer is fast and compact but only
works on UTF-8 encoded data and does not fully implement serializing.
See the JSON extension.

json\_array  
As json, but decodes into arrays.

php  
The standard PHP serializer.

igbinary  
A binary serializer

The default is igbinary if available and php otherwise.

`memcached.use_sasl` <span class="type">int</span>  
Use SASL authentication for connections. Valid values: On, Off. The
default is Off.

Resource Types
--------------

This extension has no resource types defined.

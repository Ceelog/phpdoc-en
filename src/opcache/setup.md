Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/opcache/setup.html#Requirements)
-   [Installation](/opcache/setup.html#Installation)
-   [Runtime Configuration](/opcache/setup.html#Runtime%20Configuration)
-   [Resource Types](/opcache/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

The process of installing OPcache varies depending on which version of
PHP you're running. Please refer to the appropriate section below.

> **Note**:
>
> If you want to use OPcache with
> <a href="http://xdebug.org/" class="link external">» Xdebug</a>, you
> must load OPcache before Xdebug.

### PHP 5.5.0 and later

OPcache can only be compiled as a shared extension. If you have disabled
the building of default extensions with **--disable-all**, you must
compile PHP with the **--enable-opcache** option for OPcache to be
available.

Once compiled, you can use the
<a href="/ini/core.html#ini.zend-extension" class="link">zend_extension</a>
configuration directive to load the OPcache extension into PHP. This can
be done with *zend\_extension=/full/path/to/opcache.so* on non-Windows
platforms, and *zend\_extension=C:\\path\\to\\php\_opcache.dll* on
Windows.

### PHP 5.2, 5.3 and 5.4

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/ZendOpcache" class="link external">» https://pecl.php.net/package/ZendOpcache</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

### Recommended php.ini settings

The following settings are generally recommended as providing good
performance:

    opcache.memory_consumption=128
    opcache.interned_strings_buffer=8
    opcache.max_accelerated_files=4000
    opcache.revalidate_freq=60
    opcache.fast_shutdown=1
    opcache.enable_cli=1

You may also want to consider disabling
<a href="/opcache/setup.html#" class="link">opcache.save_comments</a>
and enabling
<a href="/opcache/setup.html#" class="link">opcache.enable_file_override</a>,
however note that you will have to test your code before using these in
production as they are known to break some frameworks and applications,
particularly in cases where documentation comment annotations are used.

A full list of configuration directives supported by OPcache
<a href="/opcache/setup.html#Runtime%20Configuration" class="link">is also available</a>.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                                  | Default      | Changeable       | Changelog                                                               |
|---------------------------------------------------------------------------------------|--------------|------------------|-------------------------------------------------------------------------|
| <a href="/opcache/setup.html#" class="link">opcache.enable</a>                        | "1"          | PHP\_INI\_ALL    |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.enable_cli</a>                    | "0"          | PHP\_INI\_SYSTEM | Between PHP 7.1.2 and 7.1.6 inclusive, the default was "1"              |
| <a href="/opcache/setup.html#" class="link">opcache.memory_consumption</a>            | "128"        | PHP\_INI\_SYSTEM | Before PHP 7.0.0 the default was "64"                                   |
| <a href="/opcache/setup.html#" class="link">opcache.interned_strings_buffer</a>       | "8"          | PHP\_INI\_SYSTEM | Before PHP 7.0.0 the default was "4"                                    |
| <a href="/opcache/setup.html#" class="link">opcache.max_accelerated_files</a>         | "10000"      | PHP\_INI\_SYSTEM | Before PHP 7.0.0 the default was "2000"                                 |
| <a href="/opcache/setup.html#" class="link">opcache.max_wasted_percentage</a>         | "5"          | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.use_cwd</a>                       | "1"          | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.validate_timestamps</a>           | "1"          | PHP\_INI\_ALL    |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.revalidate_freq</a>               | "2"          | PHP\_INI\_ALL    |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.revalidate_path</a>               | "0"          | PHP\_INI\_ALL    |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.save_comments</a>                 | "1"          | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.load_comments</a>                 | "1"          | PHP\_INI\_ALL    | Removed in PHP 7.0.0.                                                   |
| <a href="/opcache/setup.html#" class="link">opcache.fast_shutdown</a>                 | "0"          | PHP\_INI\_SYSTEM | Removed in PHP 7.2.0                                                    |
| <a href="/opcache/setup.html#" class="link">opcache.enable_file_override</a>          | "0"          | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.optimization_level</a>            | "0x7FFEBFFF" | PHP\_INI\_SYSTEM | Changed from 0x7FFFBFFF in PHP 7.3.0, and from 0xFFFFFFFF in PHP 5.6.18 |
| <a href="/opcache/setup.html#" class="link">opcache.inherited_hack</a>                | "1"          | PHP\_INI\_SYSTEM | Removed in PHP 7.3.0                                                    |
| <a href="/opcache/setup.html#" class="link">opcache.dups_fix</a>                      | "0"          | PHP\_INI\_ALL    |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.blacklist_filename</a>            | ""           | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.max_file_size</a>                 | "0"          | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.consistency_checks</a>            | "0"          | PHP\_INI\_ALL    |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.force_restart_timeout</a>         | "180"        | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.error_log</a>                     | ""           | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.log_verbosity_level</a>           | "1"          | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.preferred_memory_model</a>        | ""           | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.protect_memory</a>                | "0"          | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.mmap_base</a>                     | **`NULL`**   | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.restrict_api</a>                  | ""           | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.file_update_protection</a>        | "2"          | PHP\_INI\_ALL    |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.huge_code_pages</a>               | "0"          | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.lockfile_path</a>                 | "/tmp"       | PHP\_INI\_SYSTEM |                                                                         |
| <a href="/opcache/setup.html#" class="link">opcache.opt_debug_level</a>               | "0"          | PHP\_INI\_SYSTEM | Available as of PHP 7.1.0                                               |
| <a href="/opcache/setup.html#" class="link">opcache.file_cache</a>                    | NULL         | PHP\_INI\_SYSTEM | Available as of PHP 7.0.0                                               |
| <a href="/opcache/setup.html#" class="link">opcache.file_cache_only</a>               | "0"          | PHP\_INI\_SYSTEM | Available as of PHP 7.0.0                                               |
| <a href="/opcache/setup.html#" class="link">opcache.file_cache_consistency_checks</a> | "1"          | PHP\_INI\_SYSTEM | Available as of PHP 7.0.0                                               |
| <a href="/opcache/setup.html#" class="link">opcache.file_cache_fallback</a>           | "1"          | PHP\_INI\_SYSTEM | Windows only. Available as of PHP 7.0.0                                 |
| <a href="/opcache/setup.html#" class="link">opcache.validate_permission</a>           | "0"          | PHP\_INI\_SYSTEM | Available as of PHP 7.0.14                                              |
| <a href="/opcache/setup.html#" class="link">opcache.validate_root</a>                 | "0"          | PHP\_INI\_SYSTEM | Available as of PHP 7.0.14                                              |
| <a href="/opcache/setup.html#" class="link">opcache.preload</a>                       | ""           | PHP\_INI\_SYSTEM | Available as of PHP 7.4.0                                               |
| <a href="/opcache/setup.html#" class="link">opcache.preload_user</a>                  | ""           | PHP\_INI\_SYSTEM | Available as of PHP 7.4.0                                               |
| <a href="/opcache/setup.html#" class="link">opcache.cache_id</a>                      | "1"          | PHP\_INI\_SYSTEM | Windows only. Available as of PHP 7.4.0                                 |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`opcache.enable` <span class="type">boolean</span>  
Enables the opcode cache. When disabled, code is not optimised or
cached. The setting *opcache.enable* can not be enabled at runtime
through <span class="function">ini\_set</span>, it can only be disabled.
Trying to enable it at in a script will generate a warning.

`opcache.enable_cli` <span class="type">boolean</span>  
Enables the opcode cache for the CLI version of PHP.

`opcache.memory_consumption` <span class="type">integer</span>  
The size of the shared memory storage used by OPcache, in megabytes.

`opcache.interned_strings_buffer` <span class="type">integer</span>  
The amount of memory used to store interned strings, in megabytes. This
configuration directive is ignored in PHP \< 5.3.0.

`opcache.max_accelerated_files` <span class="type">integer</span>  
The maximum number of keys (and therefore scripts) in the OPcache hash
table. The actual value used will be the first number in the set of
prime numbers *{ 223, 463, 983, 1979, 3907, 7963, 16229, 32531, 65407,
130987, 262237, 524521, 1048793 }* that is greater than or equal to the
configured value. The minimum value is 200. The maximum value is 100000
in PHP \< 5.5.6, and 1000000 in later versions.

`opcache.max_wasted_percentage` <span class="type">integer</span>  
The maximum percentage of wasted memory that is allowed before a restart
is scheduled.

`opcache.use_cwd` <span class="type">boolean</span>  
If enabled, OPcache appends the current working directory to the script
key, thereby eliminating possible collisions between files with the same
base name. Disabling this directive improves performance, but may break
existing applications.

`opcache.validate_timestamps` <span class="type">boolean</span>  
If enabled, OPcache will check for updated scripts every
<a href="/opcache/setup.html#" class="link">opcache.revalidate_freq</a>
seconds. When this directive is disabled, you must reset OPcache
manually via <span class="function">opcache\_reset</span>, <span
class="function">opcache\_invalidate</span> or by restarting the Web
server for changes to the filesystem to take effect.

`opcache.revalidate_freq` <span class="type">integer</span>  
How often to check script timestamps for updates, in seconds. *0* will
result in OPcache checking for updates on every request.

This configuration directive is ignored if
<a href="/opcache/setup.html#" class="link">opcache.validate_timestamps</a>
is disabled.

`opcache.revalidate_path` <span class="type">boolean</span>  
If disabled, existing cached files using the same
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
will be reused. Thus, if a file with the same name is elsewhere in the
include\_path, it won't be found.

`opcache.save_comments` <span class="type">boolean</span>  
If disabled, all documentation comments will be discarded from the
opcode cache to reduce the size of the optimised code. Disabling this
configuration directive may break applications and frameworks that rely
on comment parsing for annotations, including Doctrine, Zend Framework 2
and PHPUnit.

`opcache.load_comments` <span class="type">boolean</span>  
If disabled, documentation comments won't be loaded from the opcode
cache even if they exist. This can be used with
<a href="/opcache/setup.html#" class="link">opcache.save_comments</a> to
only load comments for applications that require them.

`opcache.fast_shutdown` <span class="type">boolean</span>  
If enabled, a fast shutdown sequence is used that doesn't free each
allocated block, but relies on the Zend Engine memory manager to
deallocate the entire set of request variables en masse.

This directive has been removed in PHP 7.2.0. A variant of the fast
shutdown sequence has been integrated into PHP and will be automatically
used if possible.

`opcache.enable_file_override` <span class="type">boolean</span>  
When enabled, the opcode cache will be checked for whether a file has
already been cached when <span class="function">file\_exists</span>,
<span class="function">is\_file</span> and <span
class="function">is\_readable</span> are called. This may increase
performance in applications that check the existence and readability of
PHP scripts, but risks returning stale data if
<a href="/opcache/setup.html#" class="link">opcache.validate_timestamps</a>
is disabled.

`opcache.optimization_level` <span class="type">integer</span>  
A bitmask that controls which optimisation passes are executed.

`opcache.inherited_hack` <span class="type">boolean</span>  
In PHP \< 5.3, OPcache stores the places where
<a href="/internals2/opcodes/declare-class.html" class="link">DECLARE_CLASS</a>
opcodes used inheritance; when the file is loaded, OPcache then tries to
bind the inherited classes using the current environment. The problem is
that while the DECLARE\_CLASS opcode may not be needed for the current
script, if the script requires that the opcode be defined, it may not
run.

This configuration directive is ignored in PHP 5.3 and later.

`opcache.dups_fix` <span class="type">boolean</span>  
This hack should only be enabled to work around "Cannot redeclare class"
errors.

`opcache.blacklist_filename` <span class="type">string</span>  
The location of the OPcache blacklist file. A blacklist file is a text
file containing the names of files that should not be accelerated, one
per line. Wildcards are allowed, and prefixes can also be provided.
Lines starting with a semi-colon are ignored as comments.

A simple blacklist file might look as follows:

    ; Matches a specific file.
    /var/www/broken.php
    ; A prefix that matches all files starting with x.
    /var/www/x
    ; A wildcard match.
    /var/www/*-broken.php

`opcache.max_file_size` <span class="type">integer</span>  
The maximum file size that will be cached, in bytes. If this is *0*, all
files will be cached.

`opcache.consistency_checks` <span class="type">integer</span>  
If non-zero, OPcache will verify the cache checksum every N requests,
where N is the value of this configuration directive. This should only
be enabled when debugging, as it will impair performance.

`opcache.force_restart_timeout` <span class="type">integer</span>  
The length of time to wait for a scheduled restart to begin if the cache
isn't active, in seconds. If the timeout is hit, then OPcache assumes
that something is wrong and will kill the processes holding locks on the
cache to permit a restart.

If
<a href="/opcache/setup.html#" class="link">opcache.log_verbosity_level</a>
is set to 2 or above, a warning will be recorded in the error log when
this occurs.

`opcache.error_log` <span class="type">string</span>  
The error log for OPcache errors. An empty string is treated the same as
*stderr*, and will result in logs being sent to standard error (which
will be the Web server error log in most cases).

`opcache.log_verbosity_level` <span class="type">integer</span>  
The log verbosity level. By default, only fatal errors (level 0) and
errors (level 1) are logged. Other levels available are warnings (level
2), information messages (level 3) and debug messages (level 4).

`opcache.preferred_memory_model` <span class="type">string</span>  
The preferred memory model for OPcache to use. If left empty, OPcache
will choose the most appropriate model, which is the correct behaviour
in virtually all cases.

Possible values include *mmap*, *shm*, *posix* and *win32*.

`opcache.protect_memory` <span class="type">boolean</span>  
Protects shared memory from unexpected writes while executing scripts.
This is useful for internal debugging only.

`opcache.mmap_base` <span class="type">string</span>  
The base used for shared memory segments on Windows. All PHP processes
have to map shared memory into the same address space. Using this
directive allows "Unable to reattach to base address" errors to be
fixed.

`opcache.restrict_api` <span class="type">string</span>  
Allows calling OPcache API functions only from PHP scripts which path is
started from specified string. The default "" means no restriction.

`opcache.file_update_protection` <span class="type">string</span>  
Prevents caching files that are less than this number of seconds old. It
protects from caching of incompletely updated files. In case all file
updates on your site are atomic, you may increase performance by setting
it to "0".

`opcache.huge_code_pages` <span class="type">string</span>  
Enables or disables copying of PHP code (text segment) into HUGE PAGES.
This should improve performance, but requires appropriate OS
configuration.

`opcache.lockfile_path` <span class="type">string</span>  
Absolute path used to store shared lockfiles (for \*nix only)

`opcache.opt_debug_level` <span class="type">string</span>  
Produces opcode dumps for debugging different stages of optimizations.
0x10000 will output opcodes as the compiler produced them before any
optimization occurs while 0x20000 will output optimized codes.

`opcache.file_cache` <span class="type">string</span>  
Enables and sets the second level cache directory. It should improve
performance when SHM memory is full, at server restart or SHM reset. The
default "" disables file based caching.

`opcache.file_cache_only` <span class="type">boolean</span>  
Enables or disables opcode caching in shared memory.

`opcache.file_cache_consistency_checks` <span class="type">boolean</span>  
Enables or disables checksum validation when script loaded from file
cache.

`opcache.file_cache_fallback` <span class="type">boolean</span>  
Implies opcache.file\_cache\_only=1 for a certain process that failed to
reattach to the shared memory (for Windows only). Explicitly enabled
file cache is required.

**Caution**
Disabling this configuration option may prevent processes to start, and
is therefore discouraged.

`opcache.validate_permission` <span class="type">boolean</span>  
Validates the cached file permissions against the current user.

`opcache.validate_root` <span class="type">boolean</span>  
Prevents name collisions in chroot'ed environments. This should be
enabled in all chroot'ed environments to prevent access to files outside
the chroot.

`opcache.preload` <span class="type">string</span>  
Specifies a PHP script that is going to be compiled and executed at
server start-up, and which may preload other files, either by <span
class="function">include</span>ing them or by using the <span
class="function">opcache\_compile\_file</span> function. All the
entities (e.g. functions and classes) defined in these files will be
available to requests out of the box, until the server is shut down.

`opcache.preload_user` <span class="type">string</span>  
Preloading code as root is not allowed for security reasons. This
directive facilitates to let the preloading to be run as another user.

`opcache.cache_id` <span class="type">string</span>  
On Windows, all processes running the same PHP SAPI under the same user
account having the same cache ID share a single OPcache instance. The
value of the cache ID can be freely chosen.

Resource Types
--------------

This extension has no resource types defined.

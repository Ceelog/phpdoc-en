Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/apc/setup.html#Requirements)
-   [Installation](/apc/setup.html#Installation)
-   [Runtime Configuration](/apc/setup.html#Runtime%20Configuration)
-   [Resource Types](/apc/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/apc" class="link external">» https://pecl.php.net/package/apc</a>.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section.

> **Note**: <span class="simpara"> On Windows, APC needs a temp path to
> exist, and be writable by the web server. It checks the TMP, TEMP and
> USERPROFILE environment variables in that order and finally tries the
> WINDOWS directory if none of those are set. </span>

> **Note**: <span class="simpara"> For more in-depth, highly technical
> implementation details, see the
> <a href="https://git.php.net/?p=pecl/caching/apc.git;a=blob;f=TECHNOTES.txt" class="link external">»  developer-supplied TECHNOTES file</a>
> . </span>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

Although the default APC settings are fine for many installations,
serious users should consider tuning the following parameters.

There are two primary decisions to be made configuring APC. First, how
much memory is going to be allocated to APC; and second, whether APC
will check if a file has been modified on every request. The two ini
directives that control these settings are *apc.shm\_size* and
*apc.stat*, respectively. Read the sections on these two directive
carefully below.

Once the server is running, the *apc.php* script that is bundled with
the extension should be copied somewhere into the docroot and viewed
with a browser as it provides a detailed analysis of the internal
workings of APC. If GD is enabled in PHP, it will even display some
interesting graphs. The first thing to ensure, of course, is that it is
actually caching files. If APC is working, the *Cache full count* number
(on the left) will display the number of times the cache has reached
maximum capacity and has had to forcefully clean any entries that
haven't been accessed in the last *apc.ttl* seconds. This number is
minimized in a well-configured cache. If the cache is constantly being
filled, and thusly forcefully freed, the resulting churning will have
disparaging effects on script performance. The easiest way to minimize
this number is to allocate more memory for APC. Barring that, the
*apc.filters* ought to be used to cache fewer scripts.

When APC is compiled with mmap support (Memory Mapping), it will use
only one memory segment, unlike when APC is built with SHM (SysV Shared
Memory) support that uses multiple memory segments. MMAP does not have a
maximum limit like SHM does in */proc/sys/kernel/shmmax*. In general
MMAP support is recommended because it will reclaim the memory faster
when the webserver is restarted and all in all reduces memory allocation
impact at startup.

| Name                                                                   | Default                 | Changeable       | Changelog                                                                              |
|------------------------------------------------------------------------|-------------------------|------------------|----------------------------------------------------------------------------------------|
| <a href="/apc/setup.html#" class="link">apc.enabled</a>                | "1"                     | PHP\_INI\_SYSTEM | PHP\_INI\_SYSTEM in APC 2. PHP\_INI\_ALL in APC \<= 3.0.12.                            |
| <a href="/apc/setup.html#" class="link">apc.shm_segments</a>           | "1"                     | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.shm_size</a>               | "32M"                   | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.shm_strings_buffer</a>     | "4M"                    | PHP\_INI\_SYSTEM | Available since APC 3.1.4.                                                             |
| <a href="/apc/setup.html#" class="link">apc.optimization</a>           | "0"                     | PHP\_INI\_ALL    | PHP\_INI\_SYSTEM in APC 2. Removed in APC 3.0.13.                                      |
| <a href="/apc/setup.html#" class="link">apc.num_files_hint</a>         | "1000"                  | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.user_entries_hint</a>      | "4096"                  | PHP\_INI\_SYSTEM | Available since APC 3.0.0.                                                             |
| <a href="/apc/setup.html#" class="link">apc.ttl</a>                    | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.0.                                                             |
| <a href="/apc/setup.html#" class="link">apc.user_ttl</a>               | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.0.                                                             |
| <a href="/apc/setup.html#" class="link">apc.gc_ttl</a>                 | "3600"                  | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.cache_by_default</a>       | "1"                     | PHP\_INI\_ALL    | PHP\_INI\_SYSTEM in APC \<= 3.0.12. Available since APC 3.0.0.                         |
| <a href="/apc/setup.html#" class="link">apc.filters</a>                | NULL                    | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.mmap_file_mask</a>         | NULL                    | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.slam_defense</a>           | "1"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.0. Prior to APC 3.1.4, the default value was *"0"* (disabled). |
| <a href="/apc/setup.html#" class="link">apc.file_update_protection</a> | "2"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.6.                                                             |
| <a href="/apc/setup.html#" class="link">apc.enable_cli</a>             | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.7.                                                             |
| <a href="/apc/setup.html#" class="link">apc.max_file_size</a>          | "1M"                    | PHP\_INI\_SYSTEM | Available since APC 3.0.7.                                                             |
| <a href="/apc/setup.html#" class="link">apc.use_request_time</a>       | "1"                     | PHP\_INI\_ALL    | Available since APC 3.1.3.                                                             |
| <a href="/apc/setup.html#" class="link">apc.stat</a>                   | "1"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.10.                                                            |
| <a href="/apc/setup.html#" class="link">apc.write_lock</a>             | "1"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.11.                                                            |
| <a href="/apc/setup.html#" class="link">apc.report_autofilter</a>      | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.11.                                                            |
| <a href="/apc/setup.html#" class="link">apc.serializer</a>             | "default"               | PHP\_INI\_SYSTEM | Available since APC 3.1.0.                                                             |
| <a href="/apc/setup.html#" class="link">apc.include_once_override</a>  | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.12.                                                            |
| <a href="/apc/setup.html#" class="link">apc.rfc1867</a>                | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.13.                                                            |
| <a href="/apc/setup.html#" class="link">apc.rfc1867_prefix</a>         | "upload\_"              | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.rfc1867_name</a>           | "APC\_UPLOAD\_PROGRESS" | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.rfc1867_freq</a>           | "0"                     | PHP\_INI\_SYSTEM |                                                                                        |
| <a href="/apc/setup.html#" class="link">apc.rfc1867_ttl</a>            | "3600"                  | PHP\_INI\_SYSTEM | Available since APC 3.1.1.                                                             |
| <a href="/apc/setup.html#" class="link">apc.localcache</a>             | "0"                     | PHP\_INI\_SYSTEM | Available in APC 3.0.14 - 3.1.11.                                                      |
| <a href="/apc/setup.html#" class="link">apc.localcache.size</a>        | "512"                   | PHP\_INI\_SYSTEM | vailable in APC 3.0.14 - 3.1.11.                                                       |
| <a href="/apc/setup.html#" class="link">apc.coredump_unmap</a>         | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.16.                                                            |
| <a href="/apc/setup.html#" class="link">apc.stat_ctime</a>             | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.0.13.                                                            |
| <a href="/apc/setup.html#" class="link">apc.preload_path</a>           | NULL                    | PHP\_INI\_SYSTEM | Available since APC 3.1.1.                                                             |
| <a href="/apc/setup.html#" class="link">apc.file_md5</a>               | "0"                     | PHP\_INI\_SYSTEM | Available since APC 3.1.1.                                                             |
| <a href="/apc/setup.html#" class="link">apc.canonicalize</a>           | "1"                     | PHP\_INI\_SYSTEM | Available since APC 3.1.1.                                                             |
| <a href="/apc/setup.html#" class="link">apc.lazy_functions</a>         | 0                       | PHP\_INI\_SYSTEM | Available since APC 3.1.3.                                                             |
| <a href="/apc/setup.html#" class="link">apc.lazy_classes</a>           | 0                       | PHP\_INI\_SYSTEM | Available since APC 3.1.3.                                                             |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`apc.enabled` <span class="type">boolean</span>  
*apc.enabled* can be set to 0 to disable APC. This is primarily useful
when APC is statically compiled into PHP, since there is no other way to
disable it (when compiled as a DSO, the *extension* line in *php.ini*
can just be commented-out).

`apc.shm_segments` <span class="type">integer</span>  
The number of shared memory segments to allocate for the compiler cache.
If APC is running out of shared memory but *apc.shm\_size* is set as
high as the system allows, raising this value might prevent APC from
exhausting its memory.

`apc.shm_size` <span class="type">string</span>  
The size of each shared memory segment given by a shorthand notation as
described in
<a href="/faq/using.html#faq.using.shorthandbytes" class="link">this FAQ</a>.
By default, some systems (including most BSD variants) have very low
limits on the size of a shared memory segment.

`apc.shm_strings_buffer` <span class="type">string</span>  
The size of memory to use as a shared buffer for strings used internally
by APC. Size Should be suffixed by M for megabytes, G for gigabytes.
Enabling this option will reduce the amount of memory used per PHP-FPM
worker as strings will be stored once rather than for each worker.

`apc.optimization` <span class="type">integer</span>  
The optimization level. Zero disables the optimizer, and higher values
use more aggressive optimizations. Expect very modest speed
improvements. This is experimental.

`apc.num_files_hint` <span class="type">integer</span>  
A "hint" about the number of distinct source files that will be included
or requested on your web server. Set to zero or omit if unsure; this
setting is mainly useful for sites that have many thousands of source
files.

`apc.user_entries_hint` <span class="type">integer</span>  
Just like
<a href="/apc/setup.html#" class="link">apc.num_files_hint</a>, a "hint"
about the number of distinct user cache variables to store. Set to zero
or omit if not sure.

`apc.ttl` <span class="type">integer</span>  
The number of seconds a cache entry is allowed to idle in a slot in case
this cache entry slot is needed by another entry. Leaving this at zero
means that APC's cache could potentially fill up with stale entries
while newer entries won't be cached. In the event of a cache running out
of available memory, the cache will be completely expunged if ttl is
equal to 0. Otherwise, if the ttl is greater than 0, APC will attempt to
remove expired entries.

`apc.user_ttl` <span class="type">integer</span>  
The number of seconds a cache entry is allowed to idle in a slot in case
this cache entry slot is needed by another entry. Leaving this at zero
means that APC's cache could potentially fill up with stale entries
while newer entries won't be cached. In the event of a cache running out
of available memory, the cache will be completely expunged if ttl is
equal to 0. Otherwise, if the ttl is greater than 0, APC will attempt to
remove expired entries.

`apc.gc_ttl` <span class="type">integer</span>  
The number of seconds that a cache entry may remain on the
garbage-collection list. This value provides a fail-safe in the event
that a server process dies while executing a cached source file; if that
source file is modified, the memory allocated for the old version will
not be reclaimed until this TTL reached. Set to zero to disable this
feature.

`apc.cache_by_default` <span class="type">boolean</span>  
On by default, but can be set to off and used in conjunction with
positive *apc.filters* so that files are only cached if matched by a
positive filter.

`apc.filters` <span class="type">string</span>  
A comma-separated list of POSIX extended regular expressions. If any
pattern matches the source filename, the file will not be cached. Note
that the filename used for matching is the one passed to
include/require, not the absolute path. If the first character of the
expression is a *+* then the expression will be additive in the sense
that any files matched by the expression will be cached, and if the
first character is a *-* then anything matched will not be cached. The
*-* case is the default, so it can be left off.

`apc.mmap_file_mask` <span class="type">string</span>  
If compiled with MMAP support by using *--enable-mmap* this is the
mktemp-style file\_mask to pass to the mmap module for determining
whether your mmap'ed memory region is going to be file-backed or shared
memory backed. For straight file-backed mmap, set it to something like
*/tmp/apc.XXXXXX* (exactly 6 *X*s). To use POSIX-style shm\_open/mmap
put a *.shm* somewhere in your mask. e.g. */apc.shm.XXXXXX* You can also
set it to */dev/zero* to use your kernel's */dev/zero* interface to
anonymous mmap'ed memory. Leaving it undefined will force an anonymous
mmap.

`apc.slam_defense` <span class="type">integer</span>  
On very busy servers whenever you start the server or modify files you
can create a race of many processes all trying to cache the same file at
the same time. This option sets the percentage of processes that will
skip trying to cache an uncached file. Or think of it as the probability
of a single process to skip caching. For example, setting
*apc.slam\_defense* to *75* would mean that there is a 75% chance that
the process will not cache an uncached file. So, the higher the setting
the greater the defense against cache slams. Setting this to *0*
disables this feature.

Deprecated by
<a href="/apc/setup.html#" class="link">apc.write_lock</a>.

`apc.file_update_protection` <span class="type">integer</span>  
When a file is modified on a live web server it really ought to be done
in an atomic manner. That is, written to a temporary file and renamed
(*mv*) the file into its permanent position when it is ready. Many text
editors, **cp**, **tar** and other such programs don't do this. This
means that there is a chance that a file is accessed (and cached) while
it is still being written to. This *apc.file\_update\_protection*
setting puts a delay on caching brand new files. The default is 2
seconds, which means that if the modification timestamp (*mtime*) on a
file shows that it is less than 2 seconds old when it is accessed, it
will not be cached. The unfortunate person who accessed this
half-written file will still see weirdness, but at least it won't
persist. If all of the webserver's files are atomically updated, via
some method like **rsync** (which updates correctly), this protection
can be disabled by setting this directive to 0. If the system is flooded
with i/o and some update procedures are taking longer than 2 seconds,
this setting should be increased to enable the protection on those
slower update operations.

`apc.enable_cli` <span class="type">integer</span>  
Mostly for testing and debugging. Setting this enables APC for the CLI
version of PHP. Under normal circumstances, it is not ideal to create,
populate and destroy the APC cache on every CLI request, but for various
test scenarios it is useful to be able to enable APC for the CLI version
of PHP easily.

`apc.max_file_size` <span class="type">integer</span>  
Prevent files larger than this value from getting cached. Defaults to
1M.

`apc.stat` <span class="type">integer</span>  
Be careful changing this setting. This defaults to on, forcing APC to
stat (check) the script on each request to determine if it has been
modified. If it has been modified it will recompile and cache the new
version. If this setting is off, APC will not check, which usually means
that to force APC to recheck files, the web server will have to be
restarted or the cache will have to be manually cleared. Note that
FastCGI web server configurations may not clear the cache on restart. On
a production server where the script files rarely change, a significant
performance boost can be achieved by disabled stats.

For included/required files this option applies as well, but note that
for relative path includes (any path that doesn't start with / on Unix)
APC has to check in order to uniquely identify the file. If you use
absolute path includes APC can skip the stat and use that absolute path
as the unique identifier for the file.

`apc.write_lock` <span class="type">boolean</span>  
On busy servers, when the web server is first started, or when many
files have been modified at the same time, APC may try to compile and
cache the same file multiple times. Write\_lock guarantees that only one
process will attempt to compile and cache an uncached script. The other
processes attempting to use the script will run without using the opcode
cache, rather than locking and waiting for the cache to prime.

`apc.report_autofilter` <span class="type">boolean</span>  
Logs any scripts that were automatically excluded from being cached due
to early/late binding issues.

`apc.serializer` <span class="type">string</span>  
Used to configure APC to use a third party serializer.

`apc.include_once_override` <span class="type">boolean</span>  
Optimize <span class="function">include\_once</span> and <span
class="function">require\_once</span> calls and avoid the expensive
system calls used.

**Warning**
This feature is *EXPERIMENTAL*. The behaviour of this directive, its
name, and surrounding documentation may change without notice in a
future release of APC. This feature should be used at your own risk.

`apc.rfc1867` <span class="type">boolean</span>  
RFC1867 File Upload Progress hook handler is only available if APC was
compiled against PHP 5.2.0 or later. When enabled, any file uploads
which includes a field called *APC\_UPLOAD\_PROGRESS* before the file
field in an upload form will cause APC to automatically create an
upload\_*key* user cache entry where *key* is the value of the
*APC\_UPLOAD\_PROGRESS* form entry.

Note that the hidden field specified by *APC\_UPLOAD\_PROGRESS* must
come before the file field, otherwise the upload progress will not work
correctly.

Note that the file upload tracking is not threadsafe at this point, so
new uploads that happen while a previous one is still going will disable
the tracking for the previous.

Note that the *rate* is only available once all file transfers are
completed.

**Example \#1 An apc.rfc1867 example**

``` php
<?php
print_r(apc_fetch("upload_$_POST[APC_UPLOAD_PROGRESS]"));
?>
```

The above example will output something similar to:

    Array
    (
        [total] => 1142543
        [current] => 1142543
        [rate] => 1828068.8
        [filename] => test
        [name] => file
        [temp_filename] => /tmp/php8F
        [cancel_upload] => 0
        [done] => 1
    )

`apc.rfc1867_prefix` <span class="type">string</span>  
Key prefix to use for the user cache entry generated by rfc1867 upload
progress functionality.

`apc.rfc1867_name` <span class="type">string</span>  
Specify the hidden form entry name that activates APC upload progress
and specifies the user cache key suffix.

`apc.rfc1867_freq` <span class="type">string</span>  
The frequency that updates should be made to the user cache entry for
upload progress. This can take the form of a percentage of the total
file size or a size in bytes optionally suffixed with *"k"*, *"m"*, or
*"g"* for kilobytes, megabytes, or gigabytes respectively (case
insensitive). A setting of 0 updates as often as possible, which may
cause slower uploads.

`apc.rfc1867_ttl` <span class="type">integer</span>  
TTL for rfc1867 entries.

`apc.localcache` <span class="type">boolean</span>  
This enables a lock-free local process shadow-cache which reduces lock
contention when the cache is being written to.

`apc.localcache.size` <span class="type">integer</span>  
The size of the local process shadow-cache, should be set to a
sufficiently large value, approximately half of
<a href="/apc/setup.html#" class="link">apc.num_files_hint</a>.

`apc.coredump_unmap` <span class="type">boolean</span>  
Enables APC handling of signals, such as SIGSEGV, that write core files
when signaled. When these signals are received, APC will attempt to
unmap the shared memory segment in order to exclude it from the core
file. This setting may improve system stability when fatal signals are
received and a large APC shared memory segment is configured.

**Warning**
This feature is potentially dangerous. Unmapping the shared memory
segment in a fatal signal handler may cause undefined behaviour if a
fatal error occurs.

> **Note**:
>
> Although some kernels may provide a facility to ignore various types
> of shared memory when generating a core dump file, these
> implementations may also ignore important shared memory segments such
> as the Apache scoreboard.

`apc.stat_ctime` <span class="type">integer</span>  
Verification with ctime will avoid problems caused by programs such as
svn or rsync by making sure inodes haven't changed since the last stat.
APC will normally only check mtime.

`apc.canonicalize` <span class="type">bool</span>  
If on, then relative paths are canonicalized in no-stat mode. If set,
then files included via stream wrappers can not be cached as <span
class="function">realpath</span> does not support stream wrappers.

`apc.preload_path` <span class="type">string</span>  
Optionally, set a path to the directory that APC will load cache data at
startup.

`apc.use_request_time` <span class="type">bool</span>  
Use the SAPI request start time for TTL.

`apc.file_md5` <span class="type">bool</span>  
Records a md5 hash of files.

`apc.lazy_functions` <span class="type">integer</span>  
Enables lazy loading for functions.

`apc.lazy_classes` <span class="type">integer</span>  
Enables lazy loading for classes.

Resource Types
--------------

This extension has no resource types defined.

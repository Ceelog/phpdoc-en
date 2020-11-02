opcache\_compile\_file
======================

Compiles and caches a PHP script without executing it

### Description

<span class="type">bool</span> <span
class="methodname">opcache\_compile\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> )

This function compiles a PHP script and adds it to the opcode cache
without executing it. This can be used to prime the cache after a Web
server restart by pre-caching files that will be included in later
requests.

### Parameters

`file`  
The path to the PHP script to be compiled.

### Return Values

Returns **`TRUE`** if `file` was compiled successfully or **`FALSE`** on
failure.

### Errors/Exceptions

If `file` cannot be loaded or compiled, an error of level
**`E_WARNING`** is generated. You may use
<a href="/language/operators/errorcontrol.html" class="link">@</a> to
suppress this warning.

### See Also

-   <span class="function">opcache\_invalidate</span>

opcache\_get\_configuration
===========================

Get configuration information about the cache

### Description

<span class="type">array</span> <span
class="methodname">opcache\_get\_configuration</span> ( <span
class="methodparam">void</span> )

This function returns configuration information about the cache instance

### Return Values

Returns an array of information, including ini, blacklist and version

### Errors/Exceptions

If *opcache.restrict\_api* is in use and the current path is in
violation of the rule, an E\_WARNING will be raised; no status
information will be returned.

### See Also

-   <span class="function">opcache\_get\_status</span>

opcache\_get\_status
====================

Get status information about the cache

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">opcache\_get\_status</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$get_scripts`<span
class="initializer"> = **`TRUE`**</span></span> \] )

This function returns state information about the cache instance

### Parameters

`get_scripts`  
Include script specific state information

### Return Values

Returns an array of information, optionally containing script specific
state information, or **`FALSE`** on failure.

### Errors/Exceptions

If *opcache.restrict\_api* is in use and the current path is in
violation of the rule, an E\_WARNING will be raised; no status
information will be returned.

### See Also

-   <span class="function">opcache\_get\_configuration</span>

opcache\_invalidate
===================

Invalidates a cached script

### Description

<span class="type">bool</span> <span
class="methodname">opcache\_invalidate</span> ( <span
class="methodparam"><span class="type">string</span> `$script`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$force`<span class="initializer"> = **`FALSE`**</span></span> \] )

This function invalidates a particular script from the opcode cache. If
`force` is unset or **`FALSE`**, the script will only be invalidated if
the modification time of the script is newer than the cached opcodes.

### Parameters

`script`  
The path to the script being invalidated.

`force`  
If set to **`TRUE`**, the script will be invalidated regardless of
whether invalidation is necessary.

### Return Values

Returns **`TRUE`** if the opcode cache for `script` was invalidated or
if there was nothing to invalidate, or **`FALSE`** if the opcode cache
is disabled.

### See Also

-   <span class="function">opcache\_compile\_file</span>
-   <span class="function">opcache\_reset</span>

opcache\_is\_script\_cached
===========================

Tells whether a script is cached in OPCache

### Description

<span class="type">bool</span> <span
class="methodname">opcache\_is\_script\_cached</span> ( <span
class="methodparam"><span class="type">string</span> `$file`</span> )

This function checks if a PHP script has been cached in OPCache. This
can be used to more easily detect the "warming" of the cache for a
particular script.

### Parameters

`file`  
The path to the PHP script to be checked.

### Return Values

Returns **`TRUE`** if `file` is cached in OPCache, **`FALSE`**
otherwise.

### See Also

-   <span class="function">opcache\_compile\_file</span>

opcache\_reset
==============

Resets the contents of the opcode cache

### Description

<span class="type">bool</span> <span
class="methodname">opcache\_reset</span> ( <span
class="methodparam">void</span> )

This function resets the entire opcode cache. After calling <span
class="function">opcache\_reset</span>, all scripts will be reloaded and
reparsed the next time they are hit.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the opcode cache was reset, or **`FALSE`** if the
opcode cache is disabled.

### See Also

-   <span class="function">opcache\_invalidate</span>

**Table of Contents**

-   [opcache\_compile\_file](/ref/opcache.html#opcache_compile_file) —
    Compiles and caches a PHP script without executing it
-   [opcache\_get\_configuration](/ref/opcache.html#opcache_get_configuration)
    — Get configuration information about the cache
-   [opcache\_get\_status](/ref/opcache.html#opcache_get_status) — Get
    status information about the cache
-   [opcache\_invalidate](/ref/opcache.html#opcache_invalidate) —
    Invalidates a cached script
-   [opcache\_is\_script\_cached](/ref/opcache.html#opcache_is_script_cached)
    — Tells whether a script is cached in OPCache
-   [opcache\_reset](/ref/opcache.html#opcache_reset) — Resets the
    contents of the opcode cache

memcache\_debug
===============

Turn debug output on/off

### Description

<span class="type">bool</span> <span
class="methodname">memcache\_debug</span> ( <span
class="methodparam"><span class="type">bool</span> `$on_off`</span> )

<span class="function">memcache\_debug</span> turns on debug output if
parameter `on_off` is equal to **`true`** and turns off if it's
**`false`**.

> **Note**:
>
> <span class="function">memcache\_debug</span> is accessible only if
> PHP was built with --enable-debug option and always returns **`true`**
> in this case. Otherwise, this function has no effect and always
> returns **`false`**.

### Parameters

`on_off`  
Turns debug output on if equals to **`true`**. Turns debug output off if
equals to **`false`**.

### Return Values

Returns **`true`** if PHP was built with --enable-debug option,
otherwise returns **`false`**.

**Table of Contents**

-   [memcache\_debug](/ref/memcache.html#memcache_debug) — Turn debug
    output on/off

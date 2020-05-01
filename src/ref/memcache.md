memcache\_debug
===============

Turn debug output on/off

### Description

<span class="type">bool</span> <span
class="methodname">memcache\_debug</span> ( <span
class="methodparam"><span class="type">bool</span> `$on_off`</span> )

<span class="function">memcache\_debug</span> turns on debug output if
parameter `on_off` is equal to **`TRUE`** and turns off if it's
**`FALSE`**.

> **Note**:
>
> <span class="function">memcache\_debug</span> is accessible only if
> PHP was built with --enable-debug option and always returns **`TRUE`**
> in this case. Otherwise, this function has no effect and always
> returns **`FALSE`**.

### Parameters

`on_off`  
Turns debug output on if equals to **`TRUE`**. Turns debug output off if
equals to **`FALSE`**.

### Return Values

Returns **`TRUE`** if PHP was built with --enable-debug option,
otherwise returns **`FALSE`**.

**Table of Contents**

-   [memcache\_debug](/ref/memcache.html#memcache_debug) — Turn debug
    output on/off

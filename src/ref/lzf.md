lzf\_compress
=============

LZF compression

### Description

<span class="type">string</span> <span
class="methodname">lzf\_compress</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

<span class="function">lzf\_compress</span> compresses the given `data`
string using LZF encoding.

### Parameters

`data`  
The string to compress.

### Return Values

Returns the compressed data or **`FALSE`** if an error occurred.

### See Also

-   <span class="function">lzf\_decompress</span>

lzf\_decompress
===============

LZF decompression

### Description

<span class="type">string</span> <span
class="methodname">lzf\_decompress</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

<span class="function">lzf\_compress</span> decompresses the given
`data` string containing lzf encoded data.

### Parameters

`data`  
The compressed string.

### Return Values

Returns the decompressed data or **`FALSE`** if an error occurred.

### See Also

-   <span class="function">lzf\_compress</span>

lzf\_optimized\_for
===================

Determines what LZF extension was optimized for

### Description

<span class="type">int</span> <span
class="methodname">lzf\_optimized\_for</span> ( <span
class="methodparam">void</span> )

Determines what was LZF extension optimized for during compilation.

### Return Values

Returns 1 if LZF was optimized for speed, 0 for compression.

**Table of Contents**

-   [lzf\_compress](/ref/lzf.html#lzf_compress) — LZF compression
-   [lzf\_decompress](/ref/lzf.html#lzf_decompress) — LZF decompression
-   [lzf\_optimized\_for](/ref/lzf.html#lzf_optimized_for) — Determines
    what LZF extension was optimized for

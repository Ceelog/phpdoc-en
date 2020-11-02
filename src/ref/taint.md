is\_tainted
===========

Checks whether a string is tainted

### Description

<span class="type">bool</span> <span
class="methodname">is\_tainted</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> )

Checks whether a string is tainted

### Parameters

`string`  

### Return Values

Return TRUE if the string is tainted, FALSE otherwise.

taint
=====

Taint a string

### Description

<span class="type">bool</span> <span class="methodname">taint</span> (
<span class="methodparam"><span class="type">string</span>
`&$string`</span> , <span class="methodparam"><span
class="type">string</span> `$strings`</span> )

Make a string tainted. This is used for testing purpose only.

### Parameters

`string`  

`strings`  

### Return Values

Return TRUE if the transformation is done. Always return TRUE if the
taint extension is not enabled.

untaint
=======

Untaint strings

### Description

<span class="type">bool</span> <span class="methodname">untaint</span> (
<span class="methodparam"><span class="type">string</span>
`&$string`</span> , <span class="methodparam"><span
class="type">string</span> `$strings`</span> )

Untaint strings

### Parameters

`string`  

`strings`  

### Return Values

**Table of Contents**

-   [is\_tainted](/ref/taint.html#is_tainted) — Checks whether a string
    is tainted
-   [taint](/ref/taint.html#taint) — Taint a string
-   [untaint](/ref/taint.html#untaint) — Untaint strings

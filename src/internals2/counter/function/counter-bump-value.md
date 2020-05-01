counter\_bump\_value
====================

Change the current value of a counter resource

### Description

<span class="type">void</span> <span
class="methodname">counter\_bump\_value</span> ( <span
class="methodparam"><span class="type">resource</span> `$counter`</span>
, <span class="methodparam"><span class="type">int</span>
`$offset`</span> )

<span class="function">counter\_bump\_value</span> updates the current
value of a counter resource.

### Parameters

`counter`  
<span class="simpara"> The counter resource to operate on. </span>

`offset`  
<span class="simpara"> The amount by which to change the counter's
value. Can be negative. </span>

### See Also

-   <span class="function">counter\_get\_value</span>
-   <span class="function">counter\_reset\_value</span>

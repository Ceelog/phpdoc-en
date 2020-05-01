Throwable::getPrevious
======================

Returns the previous Throwable

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">Throwable</span> <span
class="methodname">Throwable::getPrevious</span> ( <span
class="methodparam">void</span> )

Returns any previous Throwable (for example, one provided as the third
parameter to <span class="methodname">Exception::\_\_construct</span>).

### Parameters

This function has no parameters.

### Return Values

Returns the previous <span class="classname">Throwable</span> if
available, or **`NULL`** otherwise.

### See Also

-   <span class="methodname">Exception::getPrevious</span>

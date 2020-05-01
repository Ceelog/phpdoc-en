Throwable::getCode
==================

Gets the exception code

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Throwable::getCode</span> ( <span
class="methodparam">void</span> )

Returns the error code associated with the thrown object.

### Parameters

This function has no parameters.

### Return Values

Returns the exception code as <span class="type">integer</span> in <span
class="classname">Exception</span> but possibly as other type in <span
class="classname">Exception</span> descendants (for example as <span
class="type">string</span> in <span
class="classname">PDOException</span>).

### See Also

-   <span class="methodname">Exception::getCode</span>

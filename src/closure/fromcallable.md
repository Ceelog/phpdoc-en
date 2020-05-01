Closure::fromCallable
=====================

Converts a callable into a closure

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">Closure</span> <span
class="methodname">Closure::fromCallable</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callable`</span> )

Create and return a new
<a href="/functions/anonymous.html" class="link">anonymous function</a>
from given `callable` using the current scope. This method checks if the
`callable` is callable in the current scope and throws a <span
class="classname">TypeError</span> if it is not.

### Parameters

`callable`  
The callable to convert.

### Return Values

Returns the newly created <span class="classname">Closure</span> or
throws a <span class="classname">TypeError</span> if the `callable` is
not callable in the current scope.

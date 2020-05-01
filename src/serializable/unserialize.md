Serializable::unserialize
=========================

Constructs the object

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Serializable::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

Called during unserialization of the object.

> **Note**:
>
> This method acts as the
> <a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">constructor</a>
> of the object. The
> <a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
> method will *not* be called after this method.

### Parameters

`serialized`  
The string representation of the object.

### Return Values

The return value from this method is ignored.

### See Also

-   <a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>

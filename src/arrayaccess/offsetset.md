ArrayAccess::offsetSet
======================

Assign a value to the specified offset

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">ArrayAccess::offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$offset`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

Assigns a value to the specified offset.

### Parameters

`offset`  
The offset to assign the value to.

`value`  
The value to set.

### Return Values

No value is returned.

### Notes

> **Note**:
>
> The `offset` parameter will be set to **`NULL`** if another value is
> not available, like in the following example.
>
> ``` php
> <?php
> $arrayaccess[] = "first value";
> $arrayaccess[] = "second value";
> print_r($arrayaccess);
> ?>
> ```
>
> The above example will output:
>
>     Array
>     (
>         [0] => first value
>         [1] => second value
>     )

> **Note**:
>
> This function is not called in assignments by reference and otherwise
> indirect changes to array dimensions overloaded with <span
> class="classname">ArrayAccess</span> (indirect in the sense they are
> made not by changing the dimension directly, but by changing a
> sub-dimension or sub-property or assigning the array dimension by
> reference to another variable). Instead, <span
> class="function">ArrayAccess::offsetGet</span> is called. The
> operation will only be successful if that method returns by reference.

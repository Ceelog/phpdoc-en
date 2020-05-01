Exception::getCode
==================

Gets the Exception code

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

Returns the Exception code.

### Parameters

This function has no parameters.

### Return Values

Returns the exception code as <span class="type">integer</span> in <span
class="classname">Exception</span> but possibly as other type in <span
class="classname">Exception</span> descendants (for example as <span
class="type">string</span> in <span
class="classname">PDOException</span>).

### Examples

**Example \#1 <span class="function">Exception::getCode</span> example**

``` php
<?php
try {
    throw new Exception("Some error message", 30);
} catch(Exception $e) {
    echo "The exception code is: " . $e->getCode();
}
?>
```

The above example will output something similar to:

    The exception code is: 30

### See Also

-   <span class="methodname">Throwable::getCode</span>

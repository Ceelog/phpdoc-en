Error::getCode
==============

Gets the error code

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

Returns the error code.

### Parameters

This function has no parameters.

### Return Values

Returns the error code as <span class="type">integer</span>

### Examples

**Example \#1 <span class="function">Error::getCode</span> example**

``` php
<?php
try {
    throw new Error("Some error message", 30);
} catch(Error $e) {
    echo "The Error code is: " . $e->getCode();
}
?>
```

The above example will output something similar to:

    The Error code is: 30

### See Also

-   <span class="methodname">Throwable::getCode</span>

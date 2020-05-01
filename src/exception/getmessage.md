Exception::getMessage
=====================

Gets the Exception message

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

Returns the Exception message.

### Parameters

This function has no parameters.

### Return Values

Returns the Exception message as a string.

### Examples

**Example \#1 <span class="function">Exception::getMessage</span>
example**

``` php
<?php
try {
    throw new Exception("Some error message");
} catch(Exception $e) {
    echo $e->getMessage();
}
?>
```

The above example will output something similar to:

    Some error message

### See Also

-   <span class="methodname">Throwable::getMessage</span>

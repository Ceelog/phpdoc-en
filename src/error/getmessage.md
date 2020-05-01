Error::getMessage
=================

Gets the error message

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

Returns the error message.

### Parameters

This function has no parameters.

### Return Values

Returns the error message as a string.

### Examples

**Example \#1 <span class="function">Error::getMessage</span> example**

``` php
<?php
try {
    throw new Error("Some error message");
} catch(Error $e) {
    echo $e->getMessage();
}
?>
```

The above example will output something similar to:

    Some error message

### See Also

-   <span class="methodname">Throwable::getMessage</span>

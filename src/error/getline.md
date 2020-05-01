Error::getLine
==============

Gets the line in which the error occurred

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

Get line number where the error occurred.

### Parameters

This function has no parameters.

### Return Values

Returns the line number where the error occurred.

### Examples

**Example \#1 <span class="function">Error::getLine</span> example**

``` php
<?php
try {
    throw new Error("Some error message");
} catch(Error $e) {
    echo "The error was created on line: " . $e->getLine();
}
?>
```

The above example will output something similar to:

    The error was created on line: 3

### See Also

-   <span class="methodname">Throwable::getLine</span>

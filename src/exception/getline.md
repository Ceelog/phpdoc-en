Exception::getLine
==================

Gets the line in which the exception was created

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

Get line number where the exception was created.

### Parameters

This function has no parameters.

### Return Values

Returns the line number where the exception was created.

### Examples

**Example \#1 <span class="function">Exception::getLine</span> example**

``` php
<?php
try {
    throw new Exception("Some error message");
} catch(Exception $e) {
    echo "The exception was created on line: " . $e->getLine();
}
?>
```

The above example will output something similar to:

    The exception was created on line: 3

### See Also

-   <span class="methodname">Throwable::getLine</span>

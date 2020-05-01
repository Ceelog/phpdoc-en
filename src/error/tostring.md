Error::\_\_toString
===================

String representation of the error

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns the <span class="type">string</span> representation of the
error.

### Parameters

This function has no parameters.

### Return Values

Returns the <span class="type">string</span> representation of the
error.

### Examples

**Example \#1 <span class="function">Error::\_\_toString</span>
example**

``` php
<?php
try {
    throw new Error("Some error message");
} catch(Error $e) {
    echo $e;
}
?>
```

The above example will output something similar to:

    Error: Some error message in /home/bjori/tmp/ex.php:3
    Stack trace:
    #0 {main}

### See Also

-   <span class="methodname">Throwable::\_\_toString</span>

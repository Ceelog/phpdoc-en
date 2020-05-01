Error::getTraceAsString
=======================

Gets the stack trace as a string

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

Returns the stack trace as a string.

### Parameters

This function has no parameters.

### Return Values

Returns the stack trace as a string.

### Examples

**Example \#1 <span class="function">Error::getTraceAsString</span>
example**

``` php
<?php
function test() {
    throw new Error;
}

try {
    test();
} catch(Error $e) {
    echo $e->getTraceAsString();
}
?>
```

The above example will output something similar to:

    #0 /home/bjori/tmp/ex.php(7): test()
    #1 {main}

### See Also

-   <span class="methodname">Throwable::getTraceAsString</span>

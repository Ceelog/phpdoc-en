Exception::getTraceAsString
===========================

Gets the stack trace as a string

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

Returns the Exception stack trace as a string.

### Parameters

This function has no parameters.

### Return Values

Returns the Exception stack trace as a string.

### Examples

**Example \#1 <span class="function">Exception::getTraceAsString</span>
example**

``` php
<?php
function test() {
    throw new Exception;
}

try {
    test();
} catch(Exception $e) {
    echo $e->getTraceAsString();
}
?>
```

The above example will output something similar to:

    #0 /home/bjori/tmp/ex.php(7): test()
    #1 {main}

### See Also

-   <span class="methodname">Throwable::getTraceAsString</span>

Exception::\_\_toString
=======================

String representation of the exception

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns the <span class="type">string</span> representation of the
exception.

### Parameters

This function has no parameters.

### Return Values

Returns the <span class="type">string</span> representation of the
exception.

### Examples

**Example \#1 <span class="function">Exception::\_\_toString</span>
example**

``` php
<?php
try {
    throw new Exception("Some error message");
} catch(Exception $e) {
    echo $e;
}
?>
```

The above example will output something similar to:

    exception 'Exception' with message 'Some error message' in /home/bjori/tmp/ex.php:3
    Stack trace:
    #0 {main}

### See Also

-   <span class="methodname">Throwable::\_\_toString</span>

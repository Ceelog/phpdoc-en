ErrorException::getSeverity
===========================

Gets the exception severity

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">ErrorException::getSeverity</span> ( <span
class="methodparam">void</span> )

Returns the severity of the exception.

### Parameters

This function has no parameters.

### Return Values

Returns the severity level of the exception.

### Examples

**Example \#1 <span class="function">ErrorException::getSeverity</span>
example**

``` php
<?php
try {
    throw new ErrorException("Exception message", 0, E_USER_ERROR);
} catch(ErrorException $e) {
    echo "This exception severity is: " . $e->getSeverity();
    var_dump($e->getSeverity() === E_USER_ERROR);
}
?>
```

The above example will output something similar to:

    This exception severity is: 256
    bool(true)

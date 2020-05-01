Exception::getFile
==================

Gets the file in which the exception was created

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

Get the name of the file in which the exception was created.

### Parameters

This function has no parameters.

### Return Values

Returns the filename in which the exception was created.

### Examples

**Example \#1 <span class="function">Exception::getFile</span> example**

``` php
<?php
try {
    throw new Exception;
} catch(Exception $e) {
    echo $e->getFile();
}
?>
```

The above example will output something similar to:

    /home/bjori/tmp/ex.php

### See Also

-   <span class="methodname">Throwable::getFile</span>

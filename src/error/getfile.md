Error::getFile
==============

Gets the file in which the error occurred

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

Get the name of the file the error occurred.

### Parameters

This function has no parameters.

### Return Values

Returns the filename in which the error occurred.

### Examples

**Example \#1 <span class="function">Error::getFile</span> example**

``` php
<?php
try {
    throw new Error;
} catch(Error $e) {
    echo $e->getFile();
}
?>
```

The above example will output something similar to:

    /home/bjori/tmp/ex.php

### See Also

-   <span class="methodname">Throwable::getFile</span>

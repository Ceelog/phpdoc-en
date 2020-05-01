Error::getPrevious
==================

Returns previous Throwable

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

Returns previous Throwable (the third parameter of <span
class="methodname">Error::\_\_construct</span>).

### Parameters

This function has no parameters.

### Return Values

Returns the previous <span class="classname">Throwable</span> if
available or **`NULL`** otherwise.

### Examples

**Example \#1 <span class="methodname">Error::getPrevious</span>
example**

Looping over, and printing out, error trace.

``` php
<?php
class MyCustomError extends Error {}

function doStuff() {
    try {
        throw new InvalidArgumentError("You are doing it wrong!", 112);
    } catch(Error $e) {
        throw new MyCustomError("Something happened", 911, $e);
    }
}


try {
    doStuff();
} catch(Error $e) {
    do {
        printf("%s:%d %s (%d) [%s]\n", $e->getFile(), $e->getLine(), $e->getMessage(), $e->getCode(), get_class($e));
    } while($e = $e->getPrevious());
}
?>
```

The above example will output something similar to:

    /home/bjori/ex.php:8 Something happened (911) [MyCustomError]
    /home/bjori/ex.php:6 You are doing it wrong! (112) [InvalidArgumentError]

### See Also

-   <span class="methodname">Throwable::getPrevious</span>

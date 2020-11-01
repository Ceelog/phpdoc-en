Exception::getPrevious
======================

Returns previous Exception

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

Returns previous exception (the third parameter of <span
class="methodname">Exception::\_\_construct</span>).

### Parameters

This function has no parameters.

### Return Values

Returns the previous <span class="classname">Throwable</span> if
available or **`NULL`** otherwise.

### Examples

**Example \#1 <span class="methodname">Exception::getPrevious</span>
example**

Looping over, and printing out, exception trace.

``` php
<?php
class MyCustomException extends Exception {}

function doStuff() {
    try {
        throw new InvalidArgumentException("You are doing it wrong!", 112);
    } catch(Exception $e) {
        throw new MyCustomException("Something happened", 911, $e);
    }
}


try {
    doStuff();
} catch(Exception $e) {
    do {
        printf("%s:%d %s (%d) [%s]\n", $e->getFile(), $e->getLine(), $e->getMessage(), $e->getCode(), get_class($e));
    } while($e = $e->getPrevious());
}
?>
```

The above example will output something similar to:

    /home/bjori/ex.php:8 Something happened (911) [MyCustomException]
    /home/bjori/ex.php:6 You are doing it wrong! (112) [InvalidArgumentException]

### See Also

-   <span class="methodname">Throwable::getPrevious</span>

Error::getTrace
===============

Gets the stack trace

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

Returns the stack trace.

### Parameters

This function has no parameters.

### Return Values

Returns the stack trace as an <span class="type">array</span>.

### Examples

**Example \#1 <span class="function">Error::getTrace</span> example**

``` php
<?php
function test() {
 throw new Error;
}

try {
 test();
} catch(Error $e) {
 var_dump($e->getTrace());
}
?>
```

The above example will output something similar to:

    array(1) {
      [0]=>
      array(4) {
        ["file"]=>
        string(22) "/home/bjori/tmp/ex.php"
        ["line"]=>
        int(7)
        ["function"]=>
        string(4) "test"
        ["args"]=>
        array(0) {
        }
      }
    }

### See Also

-   <span class="methodname">Throwable::getTrace</span>

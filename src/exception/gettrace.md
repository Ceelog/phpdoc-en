Exception::getTrace
===================

Gets the stack trace

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

Returns the Exception stack trace.

### Parameters

This function has no parameters.

### Return Values

Returns the Exception stack trace as an <span class="type">array</span>.

### Examples

**Example \#1 <span class="function">Exception::getTrace</span>
example**

``` php
<?php
function test() {
 throw new Exception;
}

try {
 test();
} catch(Exception $e) {
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

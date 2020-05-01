Generator::getReturn
====================

Get the return value of a generator

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Generator::getReturn</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the generator's return value once it has finished executing.

### Examples

**Example \#1 <span class="methodname">Generator::getReturn</span>
example**

``` php
<?php

$gen = (function() {
    yield 1;
    yield 2;

    return 3;
})();

foreach ($gen as $val) {
    echo $val, PHP_EOL;
}

echo $gen->getReturn(), PHP_EOL;
```

The above example will output:

    1
    2
    3

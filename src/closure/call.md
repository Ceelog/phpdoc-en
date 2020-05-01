Closure::call
=============

Binds and calls the closure

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Closure::call</span> ( <span
class="methodparam"><span class="type">object</span> `$newthis`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$...`</span> \] )

Temporarily binds the closure to `newthis`, and calls it with any given
parameters.

### Parameters

`newthis`  
The <span class="type">object</span> to bind the closure to for the
duration of the call.

`...`  
Zero or more parameters, which will be given as parameters to the
closure.

### Return Values

Returns the return value of the closure.

### Examples

**Example \#1 <span class="function">Closure::call</span> example**

``` php
<?php
class Value {
    protected $value;

    public function __construct($value) {
        $this->value = $value;
    }

    public function getValue() {
        return $this->value;
    }
}

$three = new Value(3);
$four = new Value(4);

$closure = function ($delta) { var_dump($this->getValue() + $delta); };
$closure->call($three, 4);
$closure->call($four, 4);
?>
```

The above example will output:

    int(7)
    int(8)

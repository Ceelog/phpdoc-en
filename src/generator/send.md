Generator::send
===============

Send a value to the generator

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Generator::send</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Sends the given value to the generator as the result of the current
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>
expression and resumes execution of the generator.

If the generator is not at a
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>
expression when this method is called, it will first be let to advance
to the first
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>
expression before sending the value. As such it is not necessary to
"prime" PHP generators with a <span
class="methodname">Generator::next</span> call (like it is done in
Python).

### Parameters

`value`  
Value to send into the generator. This value will be the return value of
the
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>
expression the generator is currently at.

### Return Values

Returns the yielded value.

### Examples

**Example \#1 Using <span class="methodname">Generator::send</span> to
inject values**

``` php
<?php
function printer() {
    echo "I'm printer!".PHP_EOL;
    while (true) {
        $string = yield;
        echo $string.PHP_EOL;
    }
}

$printer = printer();
$printer->send('Hello world!');
$printer->send('Bye world!');
?>
```

The above example will output:

    I'm printer!
    Hello world!
    Bye world!

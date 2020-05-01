Generator::throw
================

Throw an exception into the generator

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">Generator::throw</span> ( <span
class="methodparam"><span class="type">Throwable</span>
`$exception`</span> )

Throws an exception into the generator and resumes execution of the
generator. The behavior will be the same as if the current
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>
expression was replaced with a *throw $exception* statement.

If the generator is already closed when this method is invoked, the
exception will be thrown in the caller's context instead.

### Parameters

`exception`  
Exception to throw into the generator.

### Return Values

Returns the yielded value.

### Changelog

| Version | Description                                                                          |
|---------|--------------------------------------------------------------------------------------|
| 7.0.0   | The `exception` parameter also accepts <span class="classname">Throwable</span> now. |

### Examples

**Example \#1 Throwing an exception into a generator**

``` php
<?php
function gen() {
    echo "Foo\n";
    try {
        yield;
    } catch (Exception $e) {
        echo "Exception: {$e->getMessage()}\n";
    }
    echo "Bar\n";
}
 
$gen = gen();
$gen->rewind();
$gen->throw(new Exception('Test'));
?>
```

The above example will output:

    Foo
    Exception: Test
    Bar

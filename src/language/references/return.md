Returning References
--------------------

Returning by reference is useful when you want to use a function to find
to which variable a reference should be bound. Do *not* use
return-by-reference to increase performance. The engine will
automatically optimize this on its own. Only return references when you
have a valid technical reason to do so. To return references, use this
syntax:

``` php
<?php
class foo {
    public $value = 42;

    public function &getValue() {
        return $this->value;
    }
}

$obj = new foo;
$myValue = &$obj->getValue(); // $myValue is a reference to $obj->value, which is 42.
$obj->value = 2;
echo $myValue;                // prints the new value of $obj->value, i.e. 2.
?>
```

In this example, the property of the object returned by the `getValue`
function would be set, not the copy, as it would be without using
reference syntax.

> **Note**: <span class="simpara"> Unlike parameter passing, here you
> have to use *&* in both places - to indicate that you want to return
> by reference, not a copy, and to indicate that reference binding,
> rather than usual assignment, should be done for `$myValue`. </span>

> **Note**: <span class="simpara"> If you try to return a reference from
> a function with the syntax: *return ($this-\>value);* this will *not*
> work as you are attempting to return the result of an *expression*,
> and not a variable, by reference. You can only return variables by
> reference from a function - nothing else. </span>

To use the returned reference, you must use reference assignment:

``` php
<?php
function &collector() {
  static $collection = array();
  return $collection;
}
$collection = &collector();
$collection[] = 'foo';
?>
```

To pass the returned reference to another function expecting a reference
you can use this syntax:

``` php
<?php
function &collector() {
  static $collection = array();
  return $collection;
}
array_push(collector(), 'foo');
?>
```

> **Note**: <span class="simpara"> Note that *array\_push(&collector(),
> 'foo');* will *not* work, it results in a fatal error. </span>

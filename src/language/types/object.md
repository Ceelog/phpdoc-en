Objects
-------

### Object Initialization

To create a new <span class="type">object</span>, use the *new*
statement to instantiate a class:

``` php
<?php
class foo
{
    function do_foo()
    {
        echo "Doing foo."; 
    }
}

$bar = new foo;
$bar->do_foo();
?>
```

For a full discussion, see the
<a href="/language/oop5.html" class="link">Classes and Objects</a>
chapter.

### Converting to object

If an <span class="type">object</span> is converted to an <span
class="type">object</span>, it is not modified. If a value of any other
type is converted to an <span class="type">object</span>, a new instance
of the *stdClass* built-in class is created. If the value was
**`null`**, the new instance will be empty. An <span
class="type">array</span> converts to an <span
class="type">object</span> with properties named by keys and
corresponding values. Note that in this case before PHP 7.2.0 numeric
keys have been inaccessible unless iterated.

``` php
<?php
$obj = (object) array('1' => 'foo');
var_dump(isset($obj->{'1'})); // outputs 'bool(true)' as of PHP 7.2.0; 'bool(false)' previously
var_dump(key($obj)); // outputs 'string(1) "1"' as of PHP 7.2.0; 'int(1)' previously
?>
```

For any other value, a member variable named *scalar* will contain the
value.

``` php
<?php
$obj = (object) 'ciao';
echo $obj->scalar;  // outputs 'ciao'
?>
```

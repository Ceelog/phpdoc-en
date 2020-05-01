Object Inheritance
------------------

Inheritance is a well-established programming principle, and PHP makes
use of this principle in its object model. This principle will affect
the way many classes and objects relate to one another.

For example, when you extend a class, the subclass inherits all of the
public and protected methods from the parent class. Unless a class
overrides those methods, they will retain their original functionality.

This is useful for defining and abstracting functionality, and permits
the implementation of additional functionality in similar objects
without the need to reimplement all of the shared functionality.

> **Note**:
>
> Unless autoloading is used, then classes must be defined before they
> are used. If a class extends another, then the parent class must be
> declared before the child class structure. This rule applies to
> classes that inherit other classes and interfaces.

**Example \#1 Inheritance Example**

``` php
<?php

class Foo
{
    public function printItem($string)
    {
        echo 'Foo: ' . $string . PHP_EOL;
    }
    
    public function printPHP()
    {
        echo 'PHP is great.' . PHP_EOL;
    }
}

class Bar extends Foo
{
    public function printItem($string)
    {
        echo 'Bar: ' . $string . PHP_EOL;
    }
}

$foo = new Foo();
$bar = new Bar();
$foo->printItem('baz'); // Output: 'Foo: baz'
$foo->printPHP();       // Output: 'PHP is great' 
$bar->printItem('baz'); // Output: 'Bar: baz'
$bar->printPHP();       // Output: 'PHP is great'

?>
```

The Basics
----------

### class

Basic class definitions begin with the keyword *class*, followed by a
class name, followed by a pair of curly braces which enclose the
definitions of the properties and methods belonging to the class.

The class name can be any valid label, provided it is not a PHP
<a href="/reserved.html" class="link">reserved word</a>. A valid class
name starts with a letter or underscore, followed by any number of
letters, numbers, or underscores. As a regular expression, it would be
expressed thus: `^[a-zA-Z_\x80-\xff][a-zA-Z0-9_\x80-\xff]*$`.

A class may contain its own
<a href="/language/oop5/constants.html" class="link">constants</a>,
<a href="/language/oop5/properties.html" class="link">variables</a>
(called "properties"), and functions (called "methods").

**Example \#1 Simple Class definition**

``` php
<?php
class SimpleClass
{
    // property declaration
    public $var = 'a default value';

    // method declaration
    public function displayVar() {
        echo $this->var;
    }
}
?>
```

The pseudo-variable `$this` is available when a method is called from
within an object context. `$this` is a reference to the calling object
(usually the object to which the method belongs, but possibly another
object, if the method is called
<a href="/language/oop5/static.html" class="link">statically</a> from
the context of a secondary object). As of PHP 7.0.0 calling a non-static
method statically from an incompatible context results in $this being
undefined inside the method. Calling a non-static method statically from
an incompatible context has been deprecated as of PHP 5.6.0. As of PHP
7.0.0 calling a non-static method statically has been generally
deprecated (even if called from a compatible context). Before PHP 5.6.0
such calls already triggered a strict notice.

**Example \#2 Some examples of the `$this` pseudo-variable**

We're assuming that error\_reporting is disabled for this example;
otherwise the following code would trigger deprecated and strict
notices, respectively, depending on the PHP version.

``` php
<?php
class A
{
    function foo()
    {
        if (isset($this)) {
            echo '$this is defined (';
            echo get_class($this);
            echo ")\n";
        } else {
            echo "\$this is not defined.\n";
        }
    }
}

class B
{
    function bar()
    {
        A::foo();
    }
}

$a = new A();
$a->foo();

A::foo();

$b = new B();
$b->bar();

B::bar();
?>
```

Output of the above example in PHP 5:

    $this is defined (A)
    $this is not defined.
    $this is defined (B)
    $this is not defined.

Output of the above example in PHP 7:

    $this is defined (A)
    $this is not defined.
    $this is not defined.
    $this is not defined.

### new

To create an instance of a class, the *new* keyword must be used. An
object will always be created unless the object has a
<a href="/language/oop5/decon.html" class="link">constructor</a> defined
that throws an
<a href="/language/exceptions.html" class="link">exception</a> on error.
Classes should be defined before instantiation (and in some cases this
is a requirement).

If a <span class="type">string</span> containing the name of a class is
used with *new*, a new instance of that class will be created. If the
class is in a namespace, its fully qualified name must be used when
doing this.

> **Note**:
>
> If there are no arguments to be passed to the class's constructor,
> parentheses after the class name may be omitted.

**Example \#3 Creating an instance**

``` php
<?php
$instance = new SimpleClass();

// This can also be done with a variable:
$className = 'SimpleClass';
$instance = new $className(); // new SimpleClass()
?>
```

In the class context, it is possible to create a new object by *new
self* and *new parent*.

When assigning an already created instance of a class to a new variable,
the new variable will access the same instance as the object that was
assigned. This behaviour is the same when passing instances to a
function. A copy of an already created object can be made by
<a href="/language/oop5/cloning.html" class="link">cloning</a> it.

**Example \#4 Object Assignment**

``` php
<?php

$instance = new SimpleClass();

$assigned   =  $instance;
$reference  =& $instance;

$instance->var = '$assigned will have this value';

$instance = null; // $instance and $reference become null

var_dump($instance);
var_dump($reference);
var_dump($assigned);
?>
```

The above example will output:

    NULL
    NULL
    object(SimpleClass)#1 (1) {
       ["var"]=>
         string(30) "$assigned will have this value"
    }

PHP 5.3.0 introduced a couple of new ways to create instances of an
object:

**Example \#5 Creating new objects**

``` php
<?php
class Test
{
    static public function getNew()
    {
        return new static;
    }
}

class Child extends Test
{}

$obj1 = new Test();
$obj2 = new $obj1;
var_dump($obj1 !== $obj2);

$obj3 = Test::getNew();
var_dump($obj3 instanceof Test);

$obj4 = Child::getNew();
var_dump($obj4 instanceof Child);
?>
```

The above example will output:

    bool(true)
    bool(true)
    bool(true)

PHP 5.4.0 introduced the possibility to access a member of a newly
created object in a single expression:

**Example \#6 Access member of newly created object**

``` php
<?php
echo (new DateTime())->format('Y');
?>
```

The above example will output something similar to:

    2016

> **Note**: <span class="simpara"> Prior to PHP 7.1, the arguments are
> not evaluated if there is no constructor function defined. </span>

### Properties and methods

Class properties and methods live in separate "namespaces", so it is
possible to have a property and a method with the same name. Referring
to both a property and a method has the same notation, and whether a
property will be accessed or a method will be called, solely depends on
the context, i.e. whether the usage is a variable access or a function
call.

**Example \#7 Property access vs. method call**

``` php
<?php
class Foo
{
    public $bar = 'property';
    
    public function bar() {
        return 'method';
    }
}

$obj = new Foo();
echo $obj->bar, PHP_EOL, $obj->bar(), PHP_EOL;
```

The above example will output:

    property
    method

That means that calling an
<a href="/functions/anonymous.html" class="link">anonymous function</a>
which has been assigned to a property is not directly possible. Instead
the property has to be assigned to a variable first, for instance. As of
PHP 7.0.0 it is possible to call such a property directly by enclosing
it in parentheses.

**Example \#8 Calling an anonymous function stored in a property**

``` php
<?php
class Foo
{
    public $bar;
    
    public function __construct() {
        $this->bar = function() {
            return 42;
        };
    }
}

$obj = new Foo();

// as of PHP 5.3.0:
$func = $obj->bar;
echo $func(), PHP_EOL;

// alternatively, as of PHP 7.0.0:
echo ($obj->bar)(), PHP_EOL;
```

The above example will output:

    42

### extends

A class can inherit the methods and properties of another class by using
the keyword *extends* in the class declaration. It is not possible to
extend multiple classes; a class can only inherit from one base class.

The inherited methods and properties can be overridden by redeclaring
them with the same name defined in the parent class. However, if the
parent class has defined a method as
<a href="/language/oop5/final.html" class="link">final</a>, that method
may not be overridden. It is possible to access the overridden methods
or static properties by referencing them with
<a href="/language/oop5/paamayim-nekudotayim.html" class="link">parent::</a>.

When overriding methods, the parameter signature should remain the same
or PHP will generate an **`E_STRICT`** level error. This does not apply
to the constructor, which allows overriding with different parameters.

**Example \#9 Simple Class Inheritance**

``` php
<?php
class ExtendClass extends SimpleClass
{
    // Redefine the parent method
    function displayVar()
    {
        echo "Extending class\n";
        parent::displayVar();
    }
}

$extended = new ExtendClass();
$extended->displayVar();
?>
```

The above example will output:

    Extending class
    a default value

### ::class

Since PHP 5.5, the *class* keyword is also used for class name
resolution. You can get a string containing the fully qualified name of
the *ClassName* class by using *ClassName::class*. This is particularly
useful with
<a href="/language/namespaces.html" class="link">namespaced</a> classes.

**Example \#10 Class name resolution**

``` php
<?php
namespace NS {
    class ClassName {
    }
    
    echo ClassName::class;
}
?>
```

The above example will output:

    NS\ClassName

> **Note**:
>
> The class name resolution using *::class* is a compile time
> transformation. That means at the time the class name string is
> created no autoloading has happened yet. As a consequence, class names
> are expanded even if the class does not exist. No error is issued in
> that case.

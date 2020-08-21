Type Operators
--------------

*instanceof* is used to determine whether a PHP variable is an
instantiated object of a certain
<a href="/language/oop5/basic.html#language.oop5.basic.class" class="link">class</a>:

**Example \#1 Using *instanceof* with classes**

``` php
<?php
class MyClass
{
}

class NotMyClass
{
}
$a = new MyClass;

var_dump($a instanceof MyClass);
var_dump($a instanceof NotMyClass);
?>
```

The above example will output:

    bool(true)
    bool(false)

*instanceof* can also be used to determine whether a variable is an
instantiated object of a class that inherits from a parent class:

**Example \#2 Using *instanceof* with inherited classes**

``` php
<?php
class ParentClass
{
}

class MyClass extends ParentClass
{
}

$a = new MyClass;

var_dump($a instanceof MyClass);
var_dump($a instanceof ParentClass);
?>
```

The above example will output:

    bool(true)
    bool(true)

To check if an object is *not* an instanceof a class, the
<a href="/language/operators/logical.html" class="link">logical <em>not</em> operator</a>
can be used.

**Example \#3 Using *instanceof* to check if object is *not* an
instanceof a class**

``` php
<?php
class MyClass
{
}

$a = new MyClass;
var_dump(!($a instanceof stdClass));
?>
```

The above example will output:

    bool(true)

Lastly, *instanceof* can also be used to determine whether a variable is
an instantiated object of a class that implements an
<a href="/language/oop5/interfaces.html" class="link">interface</a>:

**Example \#4 Using *instanceof* with interfaces**

``` php
<?php
interface MyInterface
{
}

class MyClass implements MyInterface
{
}

$a = new MyClass;

var_dump($a instanceof MyClass);
var_dump($a instanceof MyInterface);
?>
```

The above example will output:

    bool(true)
    bool(true)

Although *instanceof* is usually used with a literal classname, it can
also be used with another object or a string variable:

**Example \#5 Using *instanceof* with other variables**

``` php
<?php
interface MyInterface
{
}

class MyClass implements MyInterface
{
}

$a = new MyClass;
$b = new MyClass;
$c = 'MyClass';
$d = 'NotMyClass';

var_dump($a instanceof $b); // $b is an object of class MyClass
var_dump($a instanceof $c); // $c is a string 'MyClass'
var_dump($a instanceof $d); // $d is a string 'NotMyClass'
?>
```

The above example will output:

    bool(true)
    bool(true)
    bool(false)

instanceof does not throw any error if the variable being tested is not
an object, it simply returns **`FALSE`**. Constants, however, were not
allowed prior to PHP 7.3.0.

**Example \#6 Using *instanceof* to test other variables**

``` php
<?php
$a = 1;
$b = NULL;
$c = imagecreate(5, 5);
var_dump($a instanceof stdClass); // $a is an integer
var_dump($b instanceof stdClass); // $b is NULL
var_dump($c instanceof stdClass); // $c is a resource
var_dump(FALSE instanceof stdClass);
?>
```

The above example will output:

    bool(false)
    bool(false)
    bool(false)
    PHP Fatal error:  instanceof expects an object instance, constant given

As of PHP 7.3.0, constants are allowed on the left-hand-side of the
*instanceof* operator.

**Example \#7 Using *instanceof* to test constants**

``` php
<?php
var_dump(FALSE instanceof stdClass);
?>
```

Output of the above example in PHP 7.3:

    bool(false)

There are a few pitfalls to be aware of. Before PHP version 5.1.0,
*instanceof* would call <span class="function">\_\_autoload</span> if
the class name did not exist. In addition, if the class was not loaded,
a fatal error would occur. This can be worked around by using a dynamic
class reference, or a string variable containing the class name:

**Example \#8 Avoiding classname lookups and fatal errors with
*instanceof* in PHP 5.0**

``` php
<?php
$d = 'NotMyClass';
var_dump($a instanceof $d); // no fatal error here
?>
```

The above example will output:

    bool(false)

The *instanceof* operator was introduced in PHP 5. Before this time
<span class="function">is\_a</span> was used but <span
class="function">is\_a</span> has since been deprecated in favor of
*instanceof*. Note that as of PHP 5.3.0, <span
class="function">is\_a</span> is no longer deprecated.

See also <span class="function">get\_class</span> and <span
class="function">is\_a</span>.

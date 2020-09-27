\_\_autoload
============

Attempt to load undefined class

**Warning**

This feature has been *DEPRECATED* as of PHP 7.2.0. Relying on this
feature is highly discouraged.

### Description

<span class="type">void</span> <span
class="methodname">\_\_autoload</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> )

You can define this function to enable
<a href="/language/oop5/autoload.html" class="link">classes autoloading</a>.

### Parameters

`class`  
Name of the class to load

### Return Values

No value is returned.

### See Also

-   <span class="function">spl\_autoload\_register</span>

call\_user\_method\_array
=========================

Call a user method given with an array of parameters

**Warning**

This function was *DEPRECATED* in PHP 4.1.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">call\_user\_func\_array</span>

### Description

<span class="type">mixed</span> <span
class="methodname">call\_user\_method\_array</span> ( <span
class="methodparam"><span class="type">string</span>
`$method_name`</span> , <span class="methodparam"><span
class="type">object</span> `&$obj`</span> , <span
class="methodparam"><span class="type">array</span> `$params`</span> )

### Parameters

`method_name`  
The method name being called.

`obj`  
The <span class="type">object</span> that `method_name` is being called
on.

`params`  
An array of parameters.

### Examples

**Example \#1 <span class="function">call\_user\_method\_array</span>
alternative**

``` php
<?php
call_user_func_array(array($obj, $method_name), $params);
?>
```

### See Also

-   <span class="function">call\_user\_func\_array</span>
-   <span class="function">call\_user\_func</span>

call\_user\_method
==================

Call a user method on an specific object

**Warning**

This function was *DEPRECATED* in PHP 4.1.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">call\_user\_func</span>

### Description

<span class="type">mixed</span> <span
class="methodname">call\_user\_method</span> ( <span
class="methodparam"><span class="type">string</span>
`$method_name`</span> , <span class="methodparam"><span
class="type">object</span> `&$obj`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$...`</span> \] )

### Parameters

`method_name`  
The method name being called.

`obj`  
The <span class="type">object</span> that `method_name` is being called
on.

`...`  
The optional parameters.

### Examples

**Example \#1 <span class="function">call\_user\_method</span>
alternative**

``` php
<?php
call_user_func(array($obj, $method_name), $parameter /* , ... */);
?>
```

### See Also

-   <span class="function">call\_user\_func\_array</span>
-   <span class="function">call\_user\_func</span>

class\_alias
============

Creates an alias for a class

### Description

<span class="type">bool</span> <span
class="methodname">class\_alias</span> ( <span class="methodparam"><span
class="type">string</span> `$original`</span> , <span
class="methodparam"><span class="type">string</span> `$alias`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$autoload`<span class="initializer"> = **`TRUE`**</span></span> \] )

Creates an alias named `alias` based on the user defined class
`original`. The aliased class is exactly the same as the original class.

### Parameters

`original`  
The original class.

`alias`  
The alias name for the class.

`autoload`  
Whether to autoload if the original class is not found.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">class\_alias</span> example**

``` php
<?php

class foo { }

class_alias('foo', 'bar');

$a = new foo;
$b = new bar;

// the objects are the same
var_dump($a == $b, $a === $b);
var_dump($a instanceof $b);

// the classes are the same
var_dump($a instanceof foo);
var_dump($a instanceof bar);

var_dump($b instanceof foo);
var_dump($b instanceof bar);

?>
```

The above example will output:

    bool(true)
    bool(false)
    bool(true)
    bool(true)
    bool(true)
    bool(true)
    bool(true)

### See Also

-   <span class="function">get\_parent\_class</span>
-   <span class="function">is\_subclass\_of</span>

class\_exists
=============

Checks if the class has been defined

### Description

<span class="type">bool</span> <span
class="methodname">class\_exists</span> ( <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$autoload`<span class="initializer"> =
**`TRUE`**</span></span> \] )

This function checks whether or not the given class has been defined.

### Parameters

`class_name`  
The class name. The name is matched in a case-insensitive manner.

`autoload`  
Whether or not to call
<a href="/language/oop5/autoload.html" class="link">__autoload</a> by
default.

### Return Values

Returns **`TRUE`** if `class_name` is a defined class, **`FALSE`**
otherwise.

### Examples

**Example \#1 <span class="function">class\_exists</span> example**

``` php
<?php
// Check that the class exists before trying to use it
if (class_exists('MyClass')) {
    $myclass = new MyClass();
}

?>
```

**Example \#2 `autoload` parameter example**

``` php
<?php
function __autoload($class)
{
    include($class . '.php');

    // Check to see whether the include declared the class
    if (!class_exists($class, false)) {
        trigger_error("Unable to load class: $class", E_USER_WARNING);
    }
}

if (class_exists('MyClass')) {
    $myclass = new MyClass();
}

?>
```

### See Also

-   <span class="function">function\_exists</span>
-   <span class="function">interface\_exists</span>
-   <span class="function">get\_declared\_classes</span>

get\_called\_class
==================

The "Late Static Binding" class name

### Description

<span class="type">string</span> <span
class="methodname">get\_called\_class</span> ( <span
class="methodparam">void</span> )

Gets the name of the class the static method is called in.

### Return Values

Returns the class name. Returns **`FALSE`** if called from outside a
class.

### Examples

**Example \#1 Using <span class="function">get\_called\_class</span>**

``` php
<?php

class foo {
    static public function test() {
        var_dump(get_called_class());
    }
}

class bar extends foo {
}

foo::test();
bar::test();

?>
```

The above example will output:

    string(3) "foo"
    string(3) "bar"

### See Also

-   <span class="function">get\_parent\_class</span>
-   <span class="function">get\_class</span>
-   <span class="function">is\_subclass\_of</span>

get\_class\_methods
===================

Gets the class methods' names

### Description

<span class="type">array</span> <span
class="methodname">get\_class\_methods</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class_name`</span>
)

Gets the class methods names.

### Parameters

`class_name`  
The class name or an object instance

### Return Values

Returns an array of method names defined for the class specified by
`class_name`. In case of an error, it returns **`NULL`**.

### Examples

**Example \#1 <span class="function">get\_class\_methods</span>
example**

``` php
<?php

class myclass {
    // constructor
    function __construct()
    {
        return(true);
    }

    // method 1
    function myfunc1()
    {
        return(true);
    }

    // method 2
    function myfunc2()
    {
        return(true);
    }
}

$class_methods = get_class_methods('myclass');
// or
$class_methods = get_class_methods(new myclass());

foreach ($class_methods as $method_name) {
    echo "$method_name\n";
}

?>
```

The above example will output:

    myclass
    myfunc1
    myfunc2

### See Also

-   <span class="function">get\_class</span>
-   <span class="function">get\_class\_vars</span>
-   <span class="function">get\_object\_vars</span>

get\_class\_vars
================

Get the default properties of the class

### Description

<span class="type">array</span> <span
class="methodname">get\_class\_vars</span> ( <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> )

Get the default properties of the given class.

### Parameters

`class_name`  
The class name

### Return Values

Returns an associative array of declared properties visible from the
current scope, with their default value. The resulting array elements
are in the form of *varname =\> value*. In case of an error, it returns
**`FALSE`**.

### Examples

**Example \#1 <span class="function">get\_class\_vars</span> example**

``` php
<?php

class myclass {

    var $var1; // this has no default value...
    var $var2 = "xyz";
    var $var3 = 100;
    private $var4;

    // constructor
    function __construct() {
        // change some properties
        $this->var1 = "foo";
        $this->var2 = "bar";
        return true;
    }

}

$my_class = new myclass();

$class_vars = get_class_vars(get_class($my_class));

foreach ($class_vars as $name => $value) {
    echo "$name : $value\n";
}

?>
```

The above example will output:

    var1 :
    var2 : xyz
    var3 : 100

**Example \#2 <span class="function">get\_class\_vars</span> and scoping
behaviour**

``` php
<?php
function format($array)
{
    return implode('|', array_keys($array)) . "\r\n";
}

class TestCase
{
    public $a    = 1;
    protected $b = 2;
    private $c   = 3;

    public static function expose()
    {
        echo format(get_class_vars(__CLASS__));
    }
}

TestCase::expose();
echo format(get_class_vars('TestCase'));
?>
```

The above example will output:

    // 5.0.0
    a| * b| TestCase c
    a| * b| TestCase c

    // 5.0.1 - 5.0.2
    a|b|c
    a|b|c

    // 5.0.3 +
    a|b|c
    a

### See Also

-   <span class="function">get\_class\_methods</span>
-   <span class="function">get\_object\_vars</span>

get\_class
==========

Returns the name of the class of an object

### Description

<span class="type">string</span> <span
class="methodname">get\_class</span> (\[ <span class="methodparam"><span
class="type">object</span> `$object`</span> \] )

Gets the name of the class of the given `object`.

### Parameters

`object`  
The tested object. This parameter may be omitted when inside a class.

> **Note**: <span class="simpara"> Explicitly passing **`NULL`** as the
> `object` is no longer allowed as of PHP 7.2.0. </span> <span
> class="simpara"> The parameter is still optional and calling <span
> class="function">get\_class</span> without a parameter from inside a
> class will work, but passing **`NULL`** now emits an **`E_WARNING`**
> notice. </span>

### Return Values

Returns the name of the class of which `object` is an instance. Returns
**`FALSE`** if `object` is not an object.

If `object` is omitted when inside a class, the name of that class is
returned.

If the `object` is an instance of a class which exists in a namespace,
the qualified namespaced name of that class is returned.

### Errors/Exceptions

If <span class="function">get\_class</span> is called with anything
other than an object, an **`E_WARNING`** level error is raised.

### Changelog

| Version | Description                                                                                                                                                                                                                 |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | Prior to this version the default value for `object` was **`NULL`** and it had the same effect as not passing any value. Now **`NULL`** has been removed as the default value for `object`, and is no longer a valid input. |

### Examples

**Example \#1 Using <span class="function">get\_class</span>**

``` php
<?php

class foo {
    function name()
    {
        echo "My name is " , get_class($this) , "\n";
    }
}

// create an object
$bar = new foo();

// external call
echo "Its name is " , get_class($bar) , "\n";

// internal call
$bar->name();

?>
```

The above example will output:

    Its name is foo
    My name is foo

**Example \#2 Using <span class="function">get\_class</span> in
superclass**

``` php
<?php

abstract class bar {
    public function __construct()
    {
        var_dump(get_class($this));
        var_dump(get_class());
    }
}

class foo extends bar {
}

new foo;

?>
```

The above example will output:

    string(3) "foo"
    string(3) "bar"

**Example \#3 Using <span class="function">get\_class</span> with
namespaced classes**

``` php
<?php

namespace Foo\Bar;

class Baz {
    public function __construct()
    {

    }
}

$baz = new \Foo\Bar\Baz;

var_dump(get_class($baz));
?>
```

The above example will output:

    string(11) "Foo\Bar\Baz"

### See Also

-   <span class="function">get\_called\_class</span>
-   <span class="function">get\_parent\_class</span>
-   <span class="function">gettype</span>
-   <span class="function">is\_subclass\_of</span>

get\_declared\_classes
======================

Returns an array with the name of the defined classes

### Description

<span class="type">array</span> <span
class="methodname">get\_declared\_classes</span> ( <span
class="methodparam">void</span> )

Gets the declared classes.

### Return Values

Returns an array of the names of the declared classes in the current
script.

> **Note**:
>
> Note that depending on what extensions you have compiled or loaded
> into PHP, additional classes could be present. This means that you
> will not be able to define your own classes using these names. There
> is a list of predefined classes in the
> <a href="/reserved/classes.html" class="link">Predefined Classes</a>
> section of the appendices.

### Changelog

| Version | Description                                                                                                                                                                                                                                                   |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | Previously <span class="function">get\_declared\_classes</span> always returned parent classes before child classes. This is no longer the case. No particular order is guaranteed for the <span class="function">get\_declared\_classes</span> return value. |

### Examples

**Example \#1 <span class="function">get\_declared\_classes</span>
example**

``` php
<?php
print_r(get_declared_classes());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => stdClass
        [1] => __PHP_Incomplete_Class
        [2] => Directory
    )

### See Also

-   <span class="function">class\_exists</span>
-   <span class="function">get\_declared\_interfaces</span>
-   <span class="function">get\_defined\_functions</span>

get\_declared\_interfaces
=========================

Returns an array of all declared interfaces

### Description

<span class="type">array</span> <span
class="methodname">get\_declared\_interfaces</span> ( <span
class="methodparam">void</span> )

Gets the declared interfaces.

### Return Values

Returns an array of the names of the declared interfaces in the current
script.

### Examples

**Example \#1 <span class="function">get\_declared\_interfaces</span>
example**

``` php
<?php
print_r(get_declared_interfaces());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => Traversable
        [1] => IteratorAggregate
        [2] => Iterator
        [3] => ArrayAccess
        [4] => reflector
        [5] => RecursiveIterator
        [6] => SeekableIterator
    )

### See Also

-   <span class="function">interface\_exists</span>
-   <span class="function">get\_declared\_classes</span>
-   <span class="function">class\_implements</span>

get\_declared\_traits
=====================

Returns an array of all declared traits

### Description

<span class="type">array</span> <span
class="methodname">get\_declared\_traits</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns an array with names of all declared traits in values. Returns
**`NULL`** in case of a failure.

### See Also

-   <span class="function">class\_uses</span>
-   <span class="function">trait\_exists</span>

get\_object\_vars
=================

Gets the properties of the given object

### Description

<span class="type">array</span> <span
class="methodname">get\_object\_vars</span> ( <span
class="methodparam"><span class="type">object</span> `$object`</span> )

Gets the accessible non-static properties of the given `object`
according to scope.

### Parameters

`object`  
An object instance.

### Return Values

Returns an associative array of defined object accessible non-static
properties for the specified `object` in scope.

### Examples

**Example \#1 Use of <span class="function">get\_object\_vars</span>**

``` php
<?php

class foo {
    private $a;
    public $b = 1;
    public $c;
    private $d;
    static $e;
   
    public function test() {
        var_dump(get_object_vars($this));
    }
}

$test = new foo;
var_dump(get_object_vars($test));

$test->test();

?>
```

The above example will output:

    array(2) {
      ["b"]=>
      int(1)
      ["c"]=>
      NULL
    }
    array(4) {
      ["a"]=>
      NULL
      ["b"]=>
      int(1)
      ["c"]=>
      NULL
      ["d"]=>
      NULL
    }

### See Also

-   <span class="function">get\_class\_methods</span>
-   <span class="function">get\_class\_vars</span>

get\_parent\_class
==================

Retrieves the parent class name for object or class

### Description

<span class="type">string</span> <span
class="methodname">get\_parent\_class</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$object`</span> \]
)

Retrieves the parent class name for object or class.

### Parameters

`object`  
The tested object or class name. This parameter is optional if called
from the object's method.

### Return Values

Returns the name of the parent class of the class of which `object` is
an instance or the name.

> **Note**:
>
> If the object does not have a parent or the class given does not exist
> **`FALSE`** will be returned.

If called without parameter outside object, this function returns
**`FALSE`**.

### Examples

**Example \#1 Using <span class="function">get\_parent\_class</span>**

``` php
<?php

class dad {
    function dad()
    {
    // implements some logic
    }
}

class child extends dad {
    function child()
    {
        echo "I'm " , get_parent_class($this) , "'s son\n";
    }
}

class child2 extends dad {
    function child2()
    {
        echo "I'm " , get_parent_class('child2') , "'s son too\n";
    }
}

$foo = new child();
$bar = new child2();

?>
```

The above example will output:

    I'm dad's son
    I'm dad's son too

### See Also

-   <span class="function">get\_class</span>
-   <span class="function">is\_subclass\_of</span>
-   <span class="function">class\_parents</span>

interface\_exists
=================

Checks if the interface has been defined

### Description

<span class="type">bool</span> <span
class="methodname">interface\_exists</span> ( <span
class="methodparam"><span class="type">string</span>
`$interface_name`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$autoload`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Checks if the given interface has been defined.

### Parameters

`interface_name`  
The interface name

`autoload`  
Whether to call
<a href="/language/oop5/autoload.html" class="link">__autoload</a> or
not by default.

### Return Values

Returns **`TRUE`** if the interface given by `interface_name` has been
defined, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">interface\_exists</span> example**

``` php
<?php
// Check the interface exists before trying to use it
if (interface_exists('MyInterface')) {
    class MyClass implements MyInterface
    {
        // Methods
    }
}

?>
```

### See Also

-   <span class="function">get\_declared\_interfaces</span>
-   <span class="function">class\_implements</span>
-   <span class="function">class\_exists</span>

is\_a
=====

Checks if the object is of this class or has this class as one of its
parents

### Description

<span class="type">bool</span> <span class="methodname">is\_a</span> (
<span class="methodparam"><span class="type">mixed</span>
`$object`</span> , <span class="methodparam"><span
class="type">string</span> `$class_name`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$allow_string`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Checks if the given `object` is of this class or has this class as one
of its parents.

### Parameters

`object`  
A class name or an object instance.

`class_name`  
The class name

`allow_string`  
If this parameter set to **`FALSE`**, string class name as `object` is
not allowed. This also prevents from calling autoloader if the class
doesn't exist.

### Return Values

Returns **`TRUE`** if the object is of this class or has this class as
one of its parents, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_a</span> example**

``` php
<?php
// define a class
class WidgetFactory
{
  var $oink = 'moo';
}

// create a new object
$WF = new WidgetFactory();

if (is_a($WF, 'WidgetFactory')) {
  echo "yes, \$WF is still a WidgetFactory\n";
}
?>
```

**Example \#2 Using the *instanceof* operator in PHP 5**

``` php
<?php
if ($WF instanceof WidgetFactory) {
    echo 'Yes, $WF is a WidgetFactory';
}
?>
```

### See Also

-   <span class="function">get\_class</span>
-   <span class="function">get\_parent\_class</span>
-   <span class="function">is\_subclass\_of</span>

is\_subclass\_of
================

Checks if the object has this class as one of its parents or implements
it

### Description

<span class="type">bool</span> <span
class="methodname">is\_subclass\_of</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object`</span> ,
<span class="methodparam"><span class="type">string</span>
`$class_name`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$allow_string`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Checks if the given `object` has the class `class_name` as one of its
parents or implements it.

### Parameters

`object`  
A class name or an object instance. No error is generated if the class
does not exist.

`class_name`  
The class name

`allow_string`  
If this parameter set to false, string class name as `object` is not
allowed. This also prevents from calling autoloader if the class doesn't
exist.

### Return Values

This function returns **`TRUE`** if the object `object`, belongs to a
class which is a subclass of `class_name`, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_subclass\_of</span> example**

``` php
<?php
// define a class
class WidgetFactory
{
  var $oink = 'moo';
}

// define a child class
class WidgetFactory_Child extends WidgetFactory
{
  var $oink = 'oink';
}

// create a new object
$WF = new WidgetFactory();
$WFC = new WidgetFactory_Child();

if (is_subclass_of($WFC, 'WidgetFactory')) {
  echo "yes, \$WFC is a subclass of WidgetFactory\n";
} else {
  echo "no, \$WFC is not a subclass of WidgetFactory\n";
}


if (is_subclass_of($WF, 'WidgetFactory')) {
  echo "yes, \$WF is a subclass of WidgetFactory\n";
} else {
  echo "no, \$WF is not a subclass of WidgetFactory\n";
}


// usable only since PHP 5.0.3
if (is_subclass_of('WidgetFactory_Child', 'WidgetFactory')) {
  echo "yes, WidgetFactory_Child is a subclass of WidgetFactory\n";
} else {
  echo "no, WidgetFactory_Child is not a subclass of WidgetFactory\n";
}
?>
```

The above example will output:

    yes, $WFC is a subclass of WidgetFactory
    no, $WF is not a subclass of WidgetFactory
    yes, WidgetFactory_Child is a subclass of WidgetFactory

**Example \#2 <span class="function">is\_subclass\_of</span> using
interface example**

``` php
<?php
// Define the Interface
interface MyInterface
{
  public function MyFunction();
}

// Define the class implementation of the interface
class MyClass implements MyInterface
{
  public function MyFunction()
  {
    return "MyClass Implements MyInterface!";
  }
}

// Instantiate the object
$my_object = new MyClass;

// Works since 5.3.7

// Test using the object instance of the class
if (is_subclass_of($my_object, 'MyInterface')) {
  echo "Yes, \$my_object is a subclass of MyInterface\n";
} else {
  echo "No, \$my_object is not a subclass of MyInterface\n";
}

// Test using a string of the class name
if (is_subclass_of('MyClass', 'MyInterface')) {
  echo "Yes, MyClass is a subclass of MyInterface\n";
} else {
  echo "No, MyClass is not a subclass of MyInterface\n";
}
?>
```

The above example will output:

    Yes, $my_object is a subclass of MyInterface
    Yes, MyClass is a subclass of MyInterface

### Notes

> **Note**:
>
> Using this function will use any registered
> <a href="/language/oop5/autoload.html" class="link">autoloaders</a> if
> the class is not already known.

### See Also

-   <span class="function">get\_class</span>
-   <span class="function">get\_parent\_class</span>
-   <span class="function">is\_a</span>
-   <span class="function">class\_parents</span>

method\_exists
==============

Checks if the class method exists

### Description

<span class="type">bool</span> <span
class="methodname">method\_exists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object`</span> ,
<span class="methodparam"><span class="type">string</span>
`$method_name`</span> )

Checks if the class method exists in the given `object`.

### Parameters

`object`  
An object instance or a class name

`method_name`  
The method name

### Return Values

Returns **`TRUE`** if the method given by `method_name` has been defined
for the given `object`, **`FALSE`** otherwise.

### Notes

> **Note**:
>
> Using this function will use any registered
> <a href="/language/oop5/autoload.html" class="link">autoloaders</a> if
> the class is not already known.

### Examples

**Example \#1 <span class="function">method\_exists</span> example**

``` php
<?php
$directory = new Directory('.');
var_dump(method_exists($directory,'read'));
?>
```

The above example will output:

    bool(true)

**Example \#2 Static <span class="function">method\_exists</span>
example**

``` php
<?php
var_dump(method_exists('Directory','read'));
?>
```

The above example will output:

    bool(true)

### See Also

-   <span class="function">function\_exists</span>
-   <span class="function">is\_callable</span>
-   <span class="function">class\_exists</span>

property\_exists
================

Checks if the object or class has a property

### Description

<span class="type">bool</span> <span
class="methodname">property\_exists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$property`</span> )

This function checks if the given `property` exists in the specified
class.

> **Note**:
>
> As opposed with <span class="function">isset</span>, <span
> class="function">property\_exists</span> returns **`TRUE`** even if
> the property has the value **`NULL`**.

### Parameters

`class`  
The class name or an object of the class to test for

`property`  
The name of the property

### Return Values

Returns **`TRUE`** if the property exists, **`FALSE`** if it doesn't
exist or **`NULL`** in case of an error.

### Notes

> **Note**:
>
> Using this function will use any registered
> <a href="/language/oop5/autoload.html" class="link">autoloaders</a> if
> the class is not already known.

> **Note**:
>
> The <span class="function">property\_exists</span> function cannot
> detect properties that are magically accessible using the
> <a href="/language/oop5/overloading.html#language.oop5.overloading.members" class="link"><em>__get</em></a>
> magic method.

### Examples

**Example \#1 A <span class="function">property\_exists</span> example**

``` php
<?php

class myClass {
    public $mine;
    private $xpto;
    static protected $test;

    static function test() {
        var_dump(property_exists('myClass', 'xpto')); //true
    }
}

var_dump(property_exists('myClass', 'mine'));   //true
var_dump(property_exists(new myClass, 'mine')); //true
var_dump(property_exists('myClass', 'xpto'));   //true, as of PHP 5.3.0
var_dump(property_exists('myClass', 'bar'));    //false
var_dump(property_exists('myClass', 'test'));   //true, as of PHP 5.3.0
myClass::test();

?>
```

### See Also

-   <span class="function">method\_exists</span>

trait\_exists
=============

Checks if the trait exists

### Description

<span class="type">bool</span> <span
class="methodname">trait\_exists</span> ( <span
class="methodparam"><span class="type">string</span> `$traitname`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$autoload`</span> \] )

### Parameters

`traitname`  
Name of the trait to check

`autoload`  
Whether to autoload if not already loaded.

### Return Values

Returns **`TRUE`** if trait exists, **`FALSE`** if not, **`NULL`** in
case of an error.

**Table of Contents**

-   [\_\_autoload](/ref/classobj.html#__autoload) — Attempt to load
    undefined class
-   [call\_user\_method\_array](/ref/classobj.html#call_user_method_array)
    — Call a user method given with an array of parameters
-   [call\_user\_method](/ref/classobj.html#call_user_method) — Call a
    user method on an specific object
-   [class\_alias](/ref/classobj.html#class_alias) — Creates an alias
    for a class
-   [class\_exists](/ref/classobj.html#class_exists) — Checks if the
    class has been defined
-   [get\_called\_class](/ref/classobj.html#get_called_class) — The
    "Late Static Binding" class name
-   [get\_class\_methods](/ref/classobj.html#get_class_methods) — Gets
    the class methods' names
-   [get\_class\_vars](/ref/classobj.html#get_class_vars) — Get the
    default properties of the class
-   [get\_class](/ref/classobj.html#get_class) — Returns the name of the
    class of an object
-   [get\_declared\_classes](/ref/classobj.html#get_declared_classes) —
    Returns an array with the name of the defined classes
-   [get\_declared\_interfaces](/ref/classobj.html#get_declared_interfaces)
    — Returns an array of all declared interfaces
-   [get\_declared\_traits](/ref/classobj.html#get_declared_traits) —
    Returns an array of all declared traits
-   [get\_object\_vars](/ref/classobj.html#get_object_vars) — Gets the
    properties of the given object
-   [get\_parent\_class](/ref/classobj.html#get_parent_class) —
    Retrieves the parent class name for object or class
-   [interface\_exists](/ref/classobj.html#interface_exists) — Checks if
    the interface has been defined
-   [is\_a](/ref/classobj.html#is_a) — Checks if the object is of this
    class or has this class as one of its parents
-   [is\_subclass\_of](/ref/classobj.html#is_subclass_of) — Checks if
    the object has this class as one of its parents or implements it
-   [method\_exists](/ref/classobj.html#method_exists) — Checks if the
    class method exists
-   [property\_exists](/ref/classobj.html#property_exists) — Checks if
    the object or class has a property
-   [trait\_exists](/ref/classobj.html#trait_exists) — Checks if the
    trait exists

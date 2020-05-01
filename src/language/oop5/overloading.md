Overloading
-----------

Overloading in PHP provides means to dynamically “create” properties and
methods. These dynamic entities are processed via magic methods one can
establish in a class for various action types.

The overloading methods are invoked when interacting with properties or
methods that have not been declared or are not
<a href="/language/oop5/visibility.html" class="link">visible</a> in the
current scope. The rest of this section will use the terms “inaccessible
properties” and “inaccessible methods” to refer to this combination of
declaration and visibility.

All overloading methods must be defined as *public*.

> **Note**:
>
> None of the arguments of these magic methods can be
> <a href="/functions/arguments.html#functions.arguments.by-reference" class="link">passed by reference</a>.

> **Note**:
>
> PHP's interpretation of “overloading” is different than most object
> oriented languages. Overloading traditionally provides the ability to
> have multiple methods with the same name but different quantities and
> types of arguments.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                           |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.3.0   | Added <a href="/language/oop5/overloading.html#object.callstatic" class="link">__callStatic()</a>. Added warning to enforce public visibility and non-static declaration.                                                                                                                                             |
| 5.1.0   | Added <a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a> and <a href="/language/oop5/overloading.html#object.unset" class="link">__unset()</a>. Added support for <a href="/language/oop5/overloading.html#object.get" class="link">__get()</a> for overloading of private properties. |
| 5.0.0   | Added <a href="/language/oop5/overloading.html#object.get" class="link">__get()</a>.                                                                                                                                                                                                                                  |

### Property overloading

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">\_\_isset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_unset</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<a href="/language/oop5/overloading.html#object.set" class="link">__set()</a>
is run when writing data to inaccessible (protected or private) or
non-existing properties.

<a href="/language/oop5/overloading.html#object.get" class="link">__get()</a>
is utilized for reading data from inaccessible (protected or private) or
non-existing properties.

<a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a>
is triggered by calling <span class="function">isset</span> or <span
class="function">empty</span> on inaccessible (protected or private) or
non-existing properties.

<a href="/language/oop5/overloading.html#object.unset" class="link">__unset()</a>
is invoked when <span class="function">unset</span> is used on
inaccessible (protected or private) or non-existing properties.

The `$name` argument is the name of the property being interacted with.
The
<a href="/language/oop5/overloading.html#object.set" class="link">__set()</a>
method's `$value` argument specifies the value the `$name`'ed property
should be set to.

Property overloading only works in object context. These magic methods
will not be triggered in static context. Therefore these methods should
not be declared
<a href="/language/oop5/static.html" class="link">static</a>. As of PHP
5.3.0, a warning is issued if one of the magic overloading methods is
declared *static*.

> **Note**:
>
> The return value of
> <a href="/language/oop5/overloading.html#object.set" class="link">__set()</a>
> is ignored because of the way PHP processes the assignment operator.
> Similarly,
> <a href="/language/oop5/overloading.html#object.get" class="link">__get()</a>
> is never called when chaining assignments together like this:
>
>      $a = $obj->b = 8; 

**Example \#1 Overloading properties via the
<a href="/language/oop5/overloading.html#object.get" class="link">__get()</a>,
<a href="/language/oop5/overloading.html#object.set" class="link">__set()</a>,
<a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a>
and
<a href="/language/oop5/overloading.html#object.unset" class="link">__unset()</a>
methods**

``` php
<?php
class PropertyTest
{
    /**  Location for overloaded data.  */
    private $data = array();

    /**  Overloading not used on declared properties.  */
    public $declared = 1;

    /**  Overloading only used on this when accessed outside the class.  */
    private $hidden = 2;

    public function __set($name, $value)
    {
        echo "Setting '$name' to '$value'\n";
        $this->data[$name] = $value;
    }

    public function __get($name)
    {
        echo "Getting '$name'\n";
        if (array_key_exists($name, $this->data)) {
            return $this->data[$name];
        }

        $trace = debug_backtrace();
        trigger_error(
            'Undefined property via __get(): ' . $name .
            ' in ' . $trace[0]['file'] .
            ' on line ' . $trace[0]['line'],
            E_USER_NOTICE);
        return null;
    }

    /**  As of PHP 5.1.0  */
    public function __isset($name)
    {
        echo "Is '$name' set?\n";
        return isset($this->data[$name]);
    }

    /**  As of PHP 5.1.0  */
    public function __unset($name)
    {
        echo "Unsetting '$name'\n";
        unset($this->data[$name]);
    }

    /**  Not a magic method, just here for example.  */
    public function getHidden()
    {
        return $this->hidden;
    }
}


echo "<pre>\n";

$obj = new PropertyTest;

$obj->a = 1;
echo $obj->a . "\n\n";

var_dump(isset($obj->a));
unset($obj->a);
var_dump(isset($obj->a));
echo "\n";

echo $obj->declared . "\n\n";

echo "Let's experiment with the private property named 'hidden':\n";
echo "Privates are visible inside the class, so __get() not used...\n";
echo $obj->getHidden() . "\n";
echo "Privates not visible outside of class, so __get() is used...\n";
echo $obj->hidden . "\n";
?>
```

The above example will output:

    Setting 'a' to '1'
    Getting 'a'
    1

    Is 'a' set?
    bool(true)
    Unsetting 'a'
    Is 'a' set?
    bool(false)

    1

    Let's experiment with the private property named 'hidden':
    Privates are visible inside the class, so __get() not used...
    2
    Privates not visible outside of class, so __get() is used...
    Getting 'hidden'


    Notice:  Undefined property via __get(): hidden in <file> on line 70 in <file> on line 29

### Method overloading

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">\_\_call</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">array</span>
`$arguments`</span> )

<span class="modifier">public static</span> <span
class="type">mixed</span> <span class="methodname">\_\_callStatic</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">array</span> `$arguments`</span> )

<a href="/language/oop5/overloading.html#object.call" class="link">__call()</a>
is triggered when invoking inaccessible methods in an object context.

<a href="/language/oop5/overloading.html#object.callstatic" class="link">__callStatic()</a>
is triggered when invoking inaccessible methods in a static context.

The `$name` argument is the name of the method being called. The
`$arguments` argument is an enumerated array containing the parameters
passed to the `$name`'ed method.

**Example \#2 Overloading methods via the
<a href="/language/oop5/overloading.html#object.call" class="link">__call()</a>
and
<a href="/language/oop5/overloading.html#object.callstatic" class="link">__callStatic()</a>
methods**

``` php
<?php
class MethodTest
{
    public function __call($name, $arguments)
    {
        // Note: value of $name is case sensitive.
        echo "Calling object method '$name' "
             . implode(', ', $arguments). "\n";
    }

    /**  As of PHP 5.3.0  */
    public static function __callStatic($name, $arguments)
    {
        // Note: value of $name is case sensitive.
        echo "Calling static method '$name' "
             . implode(', ', $arguments). "\n";
    }
}

$obj = new MethodTest;
$obj->runTest('in object context');

MethodTest::runTest('in static context');  // As of PHP 5.3.0
?>
```

The above example will output:

    Calling object method 'runTest' in object context
    Calling static method 'runTest' in static context

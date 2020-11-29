uopz\_add\_function
===================

Adds non-existent function or method

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_add\_function</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
, <span class="methodparam"><span class="type">Closure</span>
`$handler`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$flags`<span class="initializer"> =
ZEND\_ACC\_PUBLIC</span></span> \] )

<span class="type">bool</span> <span
class="methodname">uopz\_add\_function</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> , <span class="methodparam"><span
class="type">Closure</span> `$handler`</span> \[, <span
class="methodparam"><span class="type">int</span> `&$flags`<span
class="initializer"> = ZEND\_ACC\_PUBLIC</span></span> \[, <span
class="methodparam"><span class="type">int</span> `&$all`<span
class="initializer"> = **`TRUE`**</span></span> \]\] )

Adds a non-existent function or method.

### Parameters

`class`  
The name of the class.

`function`  
The name of the function or method.

`handler`  
The <span class="classname">Closure</span> that defines the new function
or method.

`flags`  
Flags to set for the new function or method.

`all`  
Whether all classes that descend from `class` will also be affected.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

<span class="function">uopz\_add\_function</span> throws a <span
class="classname">RuntimeException</span> if the function or method to
add already exists.

### Examples

**Example \#1 Basic <span class="function">uopz\_add\_function</span>
Usage**

``` php
<?php
uopz_add_function('foo', function () {echo 'bar';});
foo();
?>
```

The above example will output:

    bar

### See Also

-   <span class="function">uopz\_del\_function</span>
-   <span class="function">uopz\_set\_return</span>

uopz\_allow\_exit
=================

Allows control over disabled exit opcode

### Description

<span class="type">void</span> <span
class="methodname">uopz\_allow\_exit</span> ( <span
class="methodparam"><span class="type">bool</span> `$allow`</span> )

By default uopz disables the exit opcode, so <span
class="function">exit</span> calls are practically ignored. <span
class="function">uopz\_allow\_exit</span> allows to control this
behavior.

### Parameters

`allow`  
Whether to allow the execution of exit opcodes or not.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">uopz\_allow\_exit</span> example**

``` php
<?php
exit(1);
echo 1;
uopz_allow_exit(true);
exit(2);
echo 2;
?>
```

The above example will output:

    1

### Notes

**Caution**

<a href="/book/opcache.html" class="link">OPcache</a> optimizes away
dead code after unconditional exit.

### See Also

-   <span class="function">uopz\_get\_exit\_status</span>

uopz\_backup
============

Backup a function

**Warning**

This function has been *REMOVED* in PECL uopz 5.0.0.

### Description

<span class="type">void</span> <span
class="methodname">uopz\_backup</span> ( <span class="methodparam"><span
class="type">string</span> `$function`</span> )

<span class="type">void</span> <span
class="methodname">uopz\_backup</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

Backup a function at runtime, to be restored on shutdown

### Parameters

`class`  
The name of the class containing the function to backup

`function`  
The name of the function

### Return Values

### Examples

**Example \#1 <span class="function">uopz\_backup</span> example**

``` php
<?php
uopz_backup("fgets");
uopz_function("fgets", function(){
    return true;
});
var_dump(fgets());
?>
```

The above example will output:

    bool(true)

uopz\_compose
=============

Compose a class

**Warning**

This function has been *REMOVED* in PECL uopz 5.0.0.

### Description

<span class="type">void</span> <span
class="methodname">uopz\_compose</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">array</span>
`$classes`</span> \[, <span class="methodparam"><span
class="type">array</span> `$methods`</span> \[, <span
class="methodparam"><span class="type">array</span> `$properties`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`</span> \]\]\] )

Creates a new class of the given name that implements, extends, or uses
all of the provided classes

### Parameters

`name`  
A legal class name

`classes`  
An array of class, interface and trait names

`methods`  
An associative array of methods, values are either closures or
\[modifiers =\> closure\]

`properties`  
An associative array of properties, keys are names, values are modifiers

`flags`  
Entry type, by default ZEND\_ACC\_CLASS

### Return Values

### Examples

**Example \#1 <span class="function">uopz\_compose</span> example**

``` php
<?php
class myClass {}
trait myTrait {}
interface myInterface {}

uopz_compose(
    Composed::class, [
        myClass::class, 
        myTrait::class, 
        myInterface::class
    ], [
    "__construct" => function() {
        /* ... */
    }
]);

var_dump(
 class_uses(Composed::class),
 class_parents(Composed::class),
 class_implements(Composed::class));
?>
```

The above example will output:

    array(1) {
      ["myTrait"]=>
      string(7) "myTrait"
    }
    array(1) {
      ["myClass"]=>
      string(7) "myClass"
    }
    array(1) {
      ["myInterface"]=>
      string(11) "myInterface"
    }

uopz\_copy
==========

Copy a function

**Warning**

This function has been *REMOVED* in PECL uopz 5.0.0.

### Description

<span class="type">Closure</span> <span
class="methodname">uopz\_copy</span> ( <span class="methodparam"><span
class="type">string</span> `$function`</span> )

<span class="type">Closure</span> <span
class="methodname">uopz\_copy</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

Copy a function by name

### Parameters

`class`  
The name of the class containing the function to copy

`function`  
The name of the function

### Return Values

A Closure for the specified function

### Examples

**Example \#1 <span class="function">uopz\_copy</span> example**

``` php
<?php
$strtotime = uopz_copy('strtotime');

uopz_function("strtotime", function($arg1, $arg2) use($strtotime) {
    /* can call original strtotime from here */
    var_dump($arg1);
});

var_dump(strtotime('dummy'));
?>
```

The above example will output:

    string(5) "dummy"

uopz\_del\_function
===================

Deletes previously added function or method

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_del\_function</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

<span class="type">bool</span> <span
class="methodname">uopz\_del\_function</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$all`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Deletes a previously added function or method.

### Parameters

`class`  
The name of the class.

`function`  
The name of the function or method.

`all`  
Whether all classes that descend from `class` will also be affected.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

<span class="function">uopz\_del\_function</span> throws a <span
class="classname">RuntimeException</span> if the function or method to
delete has not been added by <span
class="function">uopz\_add\_function</span>.

### Examples

**Example \#1 Basic <span class="function">uopz\_del\_function</span>
Usage**

``` php
<?php
uopz_add_function('foo', function () {echo 'bar';});
var_dump(function_exists('foo'));
uopz_del_function('foo');
var_dump(function_exists('foo'));
?>
```

The above example will output:

    bool(true)
    bool(false)

### See Also

-   <span class="function">uopz\_add\_function</span>
-   <span class="function">uopz\_unset\_return</span>

uopz\_delete
============

Delete a function

**Warning**

This function has been *REMOVED* in PECL uopz 5.0.0.

### Description

<span class="type">void</span> <span
class="methodname">uopz\_delete</span> ( <span class="methodparam"><span
class="type">string</span> `$function`</span> )

<span class="type">void</span> <span
class="methodname">uopz\_delete</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

Deletes a function or method

### Parameters

`class`  

`function`  

### Return Values

### Examples

**Example \#1 <span class="function">uopz\_delete</span> example**

``` php
<?php
uopz_delete("strlen");

echo strlen("Hello World");
?>
```

The above example will output something similar to:

    PHP Fatal error: Call to undefined function strlen() in /path/to/script.php on line 4

**Example \#2 <span class="function">uopz\_delete</span> class example**

``` php
<?php
class My {
    public static function strlen($arg) {
        return strlen($arg);
    }
}

uopz_delete(My::class, "strlen");

echo My::strlen("Hello World");
?>
```

The above example will output something similar to:

    PHP Fatal error: Call to undefined method My::strlen() in /path/to/script.php on line 10

uopz\_extend
============

Extend a class at runtime

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_extend</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$parent`</span> )

Makes `class` extend `parent`

### Parameters

`class`  
The name of the class to extend

`parent`  
The name of the class to inherit

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

As of PHP 7.4.0, <span class="function">uopz\_extends</span> throws a
<span class="classname">RuntimeException</span>, if
<a href="/book/opcache.html" class="link">OPcache</a> is enabled, and
the class entry of either `class` or `parent` (if it is a trait) is
immutable.

### Examples

**Example \#1 <span class="function">uopz\_extend</span> example**

``` php
<?php
class A {}
class B {}

uopz_extend(A::class, B::class);

var_dump(class_parents(A::class));
?>
```

The above example will output:

    array(1) {
      ["B"]=>
      string(1) "B"
    }

uopz\_flags
===========

Get or set flags on function or class

### Description

<span class="type">int</span> <span
class="methodname">uopz\_flags</span> ( <span class="methodparam"><span
class="type">string</span> `$function`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = PHP\_INT\_MAX</span></span> \] )

<span class="type">int</span> <span
class="methodname">uopz\_flags</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$function`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = PHP\_INT\_MAX</span></span> \] )

Get or set the flags on a class or function entry at runtime

### Parameters

`class`  
The name of a class

`function`  
The name of the function. If `class` is given and an empty string is
passed as `function`, <span class="function">uopz\_flags</span> gets or
sets the flags of the class entry.

`flags`  
A valid set of ZEND\_ACC\_ flags. If omitted, <span
class="function">uopz\_flags</span> acts as getter.

### Return Values

If setting, returns old flags, else returns flags

### Errors/Exceptions

As of PHP 7.4.0, if the parameter `flags` is passed, <span
class="function">uopz\_flags</span> throws a <span
class="classname">RuntimeException</span>, if
<a href="/book/opcache.html" class="link">OPcache</a> is enabled, and
the class entry of `class` or the function entry of `function` is
immutable.

### Changelog

| Version         | Description                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL uopz 5.0.0 | The `flags` parameter is now optional. Formerly, **`ZEND_ACC_FETCH`** had to be passed to use <span class="function">uopz\_flags</span> as getter. |

### Examples

**Example \#1 <span class="function">uopz\_flags</span> example**

``` php
<?php
class Test {
    public function method() {
        return __CLASS__;
    }
}

$flags = uopz_flags("Test", "method");

var_dump((bool) (uopz_flags("Test", "method") & ZEND_ACC_PRIVATE));
var_dump((bool) (uopz_flags("Test", "method") & ZEND_ACC_STATIC));

var_dump(uopz_flags("Test", "method", $flags|ZEND_ACC_STATIC|ZEND_ACC_PRIVATE));

var_dump((bool) (uopz_flags("Test", "method") & ZEND_ACC_PRIVATE));
var_dump((bool) (uopz_flags("Test", "method") & ZEND_ACC_STATIC));
?>
```

The above example will output:

    bool(false)
    bool(false)
    int(1234567890)
    bool(true)
    bool(true)

**Example \#2 "Unfinalize" a Class**

``` php
<?php
final class MyClass
{
}

$flags = uopz_flags(MyClass::class, '');
uopz_flags(MyClass::class, '', $flags & ~ZEND_ACC_FINAL);
var_dump((new ReflectionClass(MyClass::class)->isFinal());
?>
```

The above example will output:

    bool(false)

uopz\_function
==============

Creates a function at runtime

**Warning**

This function has been *REMOVED* in PECL uopz 5.0.0.

### Description

<span class="type">void</span> <span
class="methodname">uopz\_function</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
, <span class="methodparam"><span class="type">Closure</span>
`$handler`</span> \[, <span class="methodparam"><span
class="type">int</span> `$modifiers`</span> \] )

<span class="type">void</span> <span
class="methodname">uopz\_function</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> , <span class="methodparam"><span
class="type">Closure</span> `$handler`</span> \[, <span
class="methodparam"><span class="type">int</span> `$modifiers`</span> \]
)

Creates a function at runtime

### Parameters

`class`  
The name of the class to receive the new function

`function`  
The name of the function

`handler`  
The Closure for the function

`modifiers`  
The modifiers for the function, by default copied or ZEND\_ACC\_PUBLIC

### Return Values

### Examples

**Example \#1 <span class="function">uopz\_function</span> example**

``` php
<?php
uopz_function("my_strlen", function($arg) {
    return strlen($arg);
});
echo my_strlen("Hello World");
?>
```

The above example will output:

    11

**Example \#2 <span class="function">uopz\_function</span> class
example**

``` php
<?php
class My {}

uopz_function(My::class, "strlen", function($arg) {
    return strlen($arg);
}, ZEND_ACC_STATIC);

echo My::strlen("Hello World");
?>
```

The above example will output:

    11

uopz\_get\_exit\_status
=======================

Retrieve the last set exit status

### Description

<span class="type">mixed</span> <span
class="methodname">uopz\_get\_exit\_status</span> ( <span
class="methodparam">void</span> )

Retrieves the last set exit status, i.e. the value passed to <span
class="function">exit</span>.

### Parameters

This function has no parameters.

### Return Values

This function returns the last exit status, or **`NULL`** if <span
class="function">exit</span> has not been called.

### Examples

**Example \#1 <span class="function">uopz\_get\_exit\_status</span>
example**

``` php
<?php
exit(123); 
echo uopz_get_exit_status();?>
```

The above example will output:

    123

### Notes

**Caution**

<a href="/book/opcache.html" class="link">OPcache</a> optimizes away
dead code after unconditional exit.

### See Also

-   <span class="function">uopz\_allow\_exit</span>

uopz\_get\_hook
===============

Gets previously set hook on function or method

### Description

<span class="type">Closure</span> <span
class="methodname">uopz\_get\_hook</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

<span class="type">Closure</span> <span
class="methodname">uopz\_get\_hook</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> )

Gets the previously set hook on a function or method.

### Parameters

`class`  
The name of the class.

`function`  
The name of the function or method.

### Return Values

Returns the previously set hook on a function or method, or **`NULL`**
if no hook has been set.

### Examples

**Example \#1 Basic <span class="function">uopz\_get\_hook</span>
Usage**

``` php
<?php
function foo() {
    echo 'foo';
}
uopz_set_hook('foo', function () {echo 'bar';});
var_dump(uopz_get_hook('foo'));
?>
```

The above example will output something similar to:

    object(Closure)#2 (0) {
    }

### See Also

-   <span class="function">uopz\_set\_hook</span>
-   <span class="function">uopz\_unset\_hook</span>

uopz\_get\_mock
===============

Get the current mock for a class

### Description

<span class="type">mixed</span> <span
class="methodname">uopz\_get\_mock</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> )

Returns the current mock for `class`.

### Parameters

`class`  
The name of the mocked class.

### Return Values

Either a string containing the name of the mock, or an object, or
**`NULL`** if no mock has been set.

### Examples

**Example \#1 <span class="function">uopz\_get\_mock</span> example**

``` php
<?php
class A {
    public static function who() {
        echo "A";
    }
}

class mockA {
    public static function who() {
        echo "mockA";
    }
}

uopz_set_mock(A::class, mockA::class);
echo uopz_get_mock(A::class);
?>
```

The above example will output:

    mockA

### See Also

-   <span class="function">uopz\_set\_mock</span>
-   <span class="function">uopz\_unset\_mock</span>

uopz\_get\_property
===================

Gets value of class or instance property

### Description

<span class="type">mixed</span> <span
class="methodname">uopz\_get\_property</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$property`</span> )

<span class="type">mixed</span> <span
class="methodname">uopz\_get\_property</span> ( <span
class="methodparam"><span class="type">object</span> `$instance`</span>
, <span class="methodparam"><span class="type">string</span>
`$property`</span> )

Gets the value of a static class property, if `class` is given, or the
value of an instance property, if `instance` is given.

### Parameters

`class`  
The name of the class.

`instance`  
The object instance.

`property`  
The name of the property.

### Return Values

Returns the value of the class or instance property, or **`NULL`** if
the property is not defined.

### Examples

**Example \#1 Basic <span class="function">uopz\_get\_property</span>
Usage**

``` php
<?php
class Foo {
    private static $staticBar = 10;
    private $bar = 100;
}
$foo = new Foo;
var_dump(uopz_get_property('Foo', 'staticBar'));
var_dump(uopz_get_property($foo, 'bar'));
?>
```

The above example will output something similar to:

    int(10)
    int(100)

### See Also

-   <span class="function">uopz\_set\_property</span>

uopz\_get\_return
=================

Gets a previous set return value for a function

### Description

<span class="type">mixed</span> <span
class="methodname">uopz\_get\_return</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

<span class="type">mixed</span> <span
class="methodname">uopz\_get\_return</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> )

Gets the return value of the `function` previously set by <span
class="methodname">uopz\_set\_return</span>.

### Parameters

`class`  
The name of the class containing the function

`function`  
The name of the function

### Return Values

The return value or Closure previously set.

### Examples

**Example \#1 <span class="function">uopz\_get\_return</span> example**

``` php
<?php
uopz_set_return("strlen", 42);
echo uopz_get_return("strlen");
?>
```

The above example will output:

    42

uopz\_get\_static
=================

Gets the static variables from function or method scope

### Description

<span class="type">array</span> <span
class="methodname">uopz\_get\_static</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> )

<span class="type">array</span> <span
class="methodname">uopz\_get\_static</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

Gets the static variables from function or method scope.

### Parameters

`class`  
The name of the class.

`function`  
The name of the function or method.

### Return Values

Returns an associative <span class="type">array</span> of variable names
mapped to their current values on success, or **`NULL`** if the function
or method does not exist.

### Examples

**Example \#1 Basic <span class="function">uopz\_get\_static</span>
Usage**

``` php
<?php
function foo() {
    static $bar = 'baz';
}
var_dump(uopz_get_static('foo'));
?>
```

The above example will output:

    array(1) {
      ["bar"]=>
      string(3) "baz"
    }

### See Also

-   <span class="function">uopz\_set\_static</span>

uopz\_implement
===============

Implements an interface at runtime

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_implement</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$interface`</span> )

Makes `class` implement `interface`

### Parameters

`class`  

`interface`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

As of PHP 7.4.0, <span class="function">uopz\_implements</span> throws a
<span class="classname">RuntimeException</span>, if
<a href="/book/opcache.html" class="link">OPcache</a> is enabled, and
the class entry of `class` is immutable.

### Examples

**Example \#1 <span class="function">uopz\_implement</span> example**

``` php
<?php
interface myInterface {}

class myClass {}

uopz_implement(myClass::class, myInterface::class);

var_dump(class_implements(myClass::class));
?>
```

The above example will output:

    array(1) {
      ["myInterface"]=>
      string(11) "myInterface"
    }

uopz\_overload
==============

Overload a VM opcode

**Warning**

This function has been *REMOVED* in PECL uopz 5.0.0.

### Description

<span class="type">void</span> <span
class="methodname">uopz\_overload</span> ( <span
class="methodparam"><span class="type">int</span> `$opcode`</span> ,
<span class="methodparam"><span class="type">Callable</span>
`$callable`</span> )

Overloads the specified `opcode` with the user defined function

### Parameters

`opcode`  
A valid opcode, see constants for details of supported codes

`callable`  

### Return Values

### Examples

**Example \#1 <span class="function">uopz\_overload</span> example**

``` php
<?php
uopz_overload(ZEND_EXIT, function(){});

exit();
echo "Hello World";
?>
```

The above example will output:

    Hello World

uopz\_redefine
==============

Redefine a constant

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_redefine</span> ( <span
class="methodparam"><span class="type">string</span> `$constant`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="type">bool</span> <span
class="methodname">uopz\_redefine</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$constant`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

Redefines the given `constant` as `value`

### Parameters

`class`  
The name of the class containing the constant

`constant`  
The name of the constant

`value`  
The new value for the constant, must be a valid type for a constant
variable

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">uopz\_redefine</span> example**

``` php
<?php
define("MY", 100);

uopz_redefine("MY", 1000);

echo MY;
?>
```

The above example will output:

    1000

uopz\_rename
============

Rename a function at runtime

**Warning**

This function has been *REMOVED* in PECL uopz 5.0.0.

### Description

<span class="type">void</span> <span
class="methodname">uopz\_rename</span> ( <span class="methodparam"><span
class="type">string</span> `$function`</span> , <span
class="methodparam"><span class="type">string</span> `$rename`</span> )

<span class="type">void</span> <span
class="methodname">uopz\_rename</span> ( <span class="methodparam"><span
class="type">string</span> `$class`</span> , <span
class="methodparam"><span class="type">string</span> `$function`</span>
, <span class="methodparam"><span class="type">string</span>
`$rename`</span> )

Renames `function` to `rename`

> **Note**:
>
> If both functions exist, this effectively swaps their names

### Parameters

`class`  
The name of the class containing the function

`function`  
The name of an existing function

`rename`  
The new name for the function

### Return Values

### Examples

**Example \#1 <span class="function">uopz\_rename</span> example**

``` php
<?php
uopz_rename("strlen", "original_strlen");

echo original_strlen("Hello World");
?>
```

The above example will output:

    11

**Example \#2 <span class="function">uopz\_rename</span> class example**

``` php
<?php
class My {
    public function strlen($arg) {
        return strlen($arg);
    }
}

uopz_rename(My::class, "strlen", "original_strlen");

echo My::original_strlen("Hello World");
?>
```

The above example will output:

    11

uopz\_restore
=============

Restore a previously backed up function

**Warning**

This function has been *REMOVED* in PECL uopz 5.0.0.

### Description

<span class="type">void</span> <span
class="methodname">uopz\_restore</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

<span class="type">void</span> <span
class="methodname">uopz\_restore</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> )

Restore a previously backed up function

### Parameters

`class`  
The name of the class containing the function to restore

`function`  
The name of the function

### Return Values

### Examples

**Example \#1 <span class="function">uopz\_restore</span> example**

``` php
<?php
uopz_backup("fgets");
uopz_function("fgets", function(){
    return true;
});
var_dump(fgets());
uopz_restore('fgets');
fgets();
?>
```

The above example will output something similar to:

    Warning: fgets() expects at least 1 parameter, 0 given in /path/to/script.php on line 8

uopz\_set\_hook
===============

Sets hook to execute when entering a function or method

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_set\_hook</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
, <span class="methodparam"><span class="type">Closure</span>
`$hook`</span> )

<span class="type">bool</span> <span
class="methodname">uopz\_set\_hook</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> , <span class="methodparam"><span
class="type">Closure</span> `$hook`</span> )

Sets a hook to execute when entering a function or method.

### Parameters

`class`  
The name of the class.

`function`  
The name of the function or method.

`hook`  
A closure to execute when entering the function or method.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Basic <span class="function">uopz\_set\_hook</span>
Usage**

``` php
<?php
function foo() {
    echo 'foo';
}
uopz_set_hook('foo', function () {echo 'bar';});
foo();
?>
```

The above example will output:

    barfoo

### See Also

-   <span class="function">uopz\_get\_hook</span>
-   <span class="function">uopz\_unset\_hook</span>

uopz\_set\_mock
===============

Use mock instead of class for new objects

### Description

<span class="type">void</span> <span
class="methodname">uopz\_set\_mock</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$mock`</span>
)

If `mock` is a string containing the name of a class then it will be
instantiated instead of `class`. `mock` can also be an object.

> **Note**:
>
> Only dynamic access to properties and methods will use the `mock`
> object. Static access still uses the original `class`. See
> <a href="/ref/uopz.html#uopz_set_mock%20and%20static%20members" class="link">example</a>
> below.

### Parameters

`class`  
The name of the class to be mocked.

`mock`  
The mock to use in the form of a string containing the name of the class
to use or an object. If a string is passed, it has to be the fully
qualified class name. It is recommended to use the `::class` magic
constant in this case.

### Changelog

| Version    | Description                                                                                                                                                                                                                                         |
|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| uopz 6.0.0 | Mocking static members is no longer supported by this function. <span class="function">uopz\_redefine</span> and <span class="function">uopz\_set\_return</span>, or <a href="/book/componere.html" class="link">Componere</a> can be used instead. |

### Examples

**Example \#1 <span class="function">uopz\_set\_mock</span> example**

``` php
<?php
class A {
    public function who() {
        echo "A";
    }
}

class mockA {
    public function who() {
        echo "mockA";
    }
}

uopz_set_mock(A::class, mockA::class);
(new A)->who();
?>
```

The above example will output:

    mockA

**Example \#2 <span class="function">uopz\_set\_mock</span> example**

``` php
<?php
class A {
    public function who() {
        echo "A";
    }
}

uopz_set_mock(A::class, new class {
                            public function who() {
                                echo "mockA";
                            }
                        });
(new A)->who();
?>
```

The above example will output:

    mockA

**Example \#3 <span class="function">uopz\_set\_mock</span> and static
members**

As of uopz 6.0.0 mocking static members is no longer supported.

``` php
<?php
class A {
    const CON = 'A';
    public static function who() {
        echo "A";
    }
}

uopz_set_mock(A::class, new class {
                            const CON = 'mockA';
                            public static function who() {
                                echo "mockA";
                            }
                        });
echo A::CON, PHP_EOL;
A::who();
?>
```

The above example will output:

    A
    A

Output of the above example in uopz 5:

    mockA
    mockA

### See Also

-   <span class="function">uopz\_get\_mock</span>
-   <span class="function">uopz\_unset\_mock</span>

uopz\_set\_property
===================

Sets value of existing class or instance property

### Description

<span class="type">void</span> <span
class="methodname">uopz\_set\_property</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$property`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

<span class="type">void</span> <span
class="methodname">uopz\_set\_property</span> ( <span
class="methodparam"><span class="type">object</span> `$instance`</span>
, <span class="methodparam"><span class="type">string</span>
`$property`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

Sets the value of an existing static class property, if `class` is
given, or the value of an instance property (regardless whether the
instance property already exists), if `instance` is given.

### Parameters

`class`  
The name of the class.

`instance`  
The object instance.

`property`  
The name of the property.

`value`  
The value to assign to the property.

### Return Values

No value is returned.

### Examples

**Example \#1 Basic <span class="function">uopz\_set\_property</span>
Usage**

``` php
<?php
class Foo {
   private static $staticBar;
   private $bar;
   public static function testStaticBar() {
      return self::$staticBar;
   }
   public function testBar() {
      return $this->bar;
   }
}
$foo = new Foo;
uopz_set_property('Foo', 'staticBar', 10);
uopz_set_property($foo, 'bar', 100);
var_dump(Foo::testStaticBar());
var_dump($foo->testBar());
?>
```

The above example will output:

    int(10)

### See Also

-   <span class="function">uopz\_get\_property</span>

uopz\_set\_return
=================

Provide a return value for an existing function

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_set\_return</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$execute`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="type">bool</span> <span
class="methodname">uopz\_set\_return</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> , <span class="methodparam"><span
class="type">mixed</span> `$value`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$execute`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Sets the return value of the `function` to `value`. If `value` is a
Closure and `execute` is set, the Closure will be executed in place of
the original function. It is possible to call the original function from
the Closure.

> **Note**:
>
> This function replaces <span class="methodname">uopz\_rename</span>.

### Parameters

`class`  
The name of the class containing the function

`function`  
The name of an existing function

`value`  
The value the function should return. If a Closure is provided and the
execute flag is set, the Closure will be executed in place of the
original function.

`execute`  
If true, and a Closure was provided as the value, the Closure will be
executed in place of the original function.

### Return Values

True if succeeded, false otherwise.

### Examples

**Example \#1 <span class="function">uopz\_set\_return</span> example**

``` php
<?php
uopz_set_return("strlen", 42);
echo strlen("Banana");
?>
```

The above example will output:

    42

**Example \#2 <span class="function">uopz\_set\_return</span> example**

``` php
<?php
uopz_set_return("strlen", function($str) { return strlen($str) * 2; }, true );
echo strlen("Banana");
?>
```

The above example will output:

    12

**Example \#3 <span class="function">uopz\_set\_return</span> class
example**

``` php
<?php
class My {
    public static function strlen($arg) {
        return strlen($arg);
    }
}
uopz_set_return(My::class, "strlen", function($str) { return strlen($str) * 2; }, true );
echo My::strlen("Banana");
?>
```

The above example will output:

    12

uopz\_set\_static
=================

Sets the static variables in function or method scope

### Description

<span class="type">void</span> <span
class="methodname">uopz\_set\_static</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
, <span class="methodparam"><span class="type">array</span>
`$static`</span> )

<span class="type">void</span> <span
class="methodname">uopz\_set\_static</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> , <span class="methodparam"><span
class="type">array</span> `$static`</span> )

Sets the static variables in function or method scope.

### Parameters

`class`  
The name of the class.

`function`  
The name of the function or method.

`static`  
The associative <span class="type">array</span> of variable names mapped
to their values.

### Return Values

No value is returned.

### Examples

**Example \#1 Basic <span class="function">uopz\_set\_static</span>
Usage**

``` php
<?php
function foo() {
    static $bar = 'baz';
    var_dump($bar);
}
uopz_set_static('foo', ['bar' => 'qux']);
foo();
?>
```

The above example will output:

    string(3) "qux"

### See Also

-   <span class="function">uopz\_get\_static</span>

uopz\_undefine
==============

Undefine a constant

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_undefine</span> ( <span
class="methodparam"><span class="type">string</span> `$constant`</span>
)

<span class="type">bool</span> <span
class="methodname">uopz\_undefine</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$constant`</span> )

Removes the constant at runtime

### Parameters

`class`  
The name of the class containing `constant`

`constant`  
The name of an existing constant

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">uopz\_undefine</span> example**

``` php
<?php
define("MY", true);

uopz_undefine("MY");

var_dump(defined("MY"));
?>
```

The above example will output:

    bool(false)

uopz\_unset\_hook
=================

Removes previously set hook on function or method

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_unset\_hook</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

<span class="type">bool</span> <span
class="methodname">uopz\_unset\_hook</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> )

Removes the previously set hook on a function or method.

### Parameters

`class`  
The name of the class.

`function`  
The name of the function or method.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Basic <span class="function">uopz\_unset\_hook</span>
Usage**

``` php
<?php
function foo() {
    echo 'foo';
}
uopz_set_hook('foo', function () {echo 'bar';});
foo();
echo PHP_EOL;
uopz_unset_hook('foo');
foo();
?>
```

The above example will output:

    barfoo
    foo

### See Also

-   <span class="function">uopz\_set\_hook</span>
-   <span class="function">uopz\_get\_hook</span>

uopz\_unset\_mock
=================

Unset previously set mock

### Description

<span class="type">void</span> <span
class="methodname">uopz\_unset\_mock</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> )

Unsets the previously set mock for `class`.

### Parameters

`class`  
The name of the mocked class.

### Errors/Exceptions

A <span class="classname">RuntimeException</span> is thrown, if no mock
was previously set for `class`.

### Examples

**Example \#1 <span class="function">uopz\_unset\_mock</span> example**

``` php
<?php
class A {
    public static function who() {
        echo "A";
    }
}

class mockA {
    public static function who() {
        echo "mockA";
    }
}

uopz_set_mock(A::class, mockA::class);
uopz_unset_mock(A::class);
A::who();
?>
```

The above example will output:

    A

### See Also

-   <span class="function">uopz\_set\_mock</span>
-   <span class="function">uopz\_get\_mock</span>

uopz\_unset\_return
===================

Unsets a previously set return value for a function

### Description

<span class="type">bool</span> <span
class="methodname">uopz\_unset\_return</span> ( <span
class="methodparam"><span class="type">string</span> `$function`</span>
)

<span class="type">bool</span> <span
class="methodname">uopz\_unset\_return</span> ( <span
class="methodparam"><span class="type">string</span> `$class`</span> ,
<span class="methodparam"><span class="type">string</span>
`$function`</span> )

Unsets the return value of the `function` previously set by <span
class="methodname">uopz\_set\_return</span>.

### Parameters

`class`  
The name of the class containing the function

`function`  
The name of the function

### Return Values

True on success

### Examples

**Example \#1 <span class="function">uopz\_unset\_return</span>
example**

``` php
<?php
uopz_set_return("strlen", 42);
$len = strlen("Banana");
uopz_unset_return("strlen");
echo $len + strlen("Banana");
?>
```

The above example will output:

    48

**Table of Contents**

-   [uopz\_add\_function](/ref/uopz.html#uopz_add_function) — Adds
    non-existent function or method
-   [uopz\_allow\_exit](/ref/uopz.html#uopz_allow_exit) — Allows control
    over disabled exit opcode
-   [uopz\_backup](/ref/uopz.html#uopz_backup) — Backup a function
-   [uopz\_compose](/ref/uopz.html#uopz_compose) — Compose a class
-   [uopz\_copy](/ref/uopz.html#uopz_copy) — Copy a function
-   [uopz\_del\_function](/ref/uopz.html#uopz_del_function) — Deletes
    previously added function or method
-   [uopz\_delete](/ref/uopz.html#uopz_delete) — Delete a function
-   [uopz\_extend](/ref/uopz.html#uopz_extend) — Extend a class at
    runtime
-   [uopz\_flags](/ref/uopz.html#uopz_flags) — Get or set flags on
    function or class
-   [uopz\_function](/ref/uopz.html#uopz_function) — Creates a function
    at runtime
-   [uopz\_get\_exit\_status](/ref/uopz.html#uopz_get_exit_status) —
    Retrieve the last set exit status
-   [uopz\_get\_hook](/ref/uopz.html#uopz_get_hook) — Gets previously
    set hook on function or method
-   [uopz\_get\_mock](/ref/uopz.html#uopz_get_mock) — Get the current
    mock for a class
-   [uopz\_get\_property](/ref/uopz.html#uopz_get_property) — Gets value
    of class or instance property
-   [uopz\_get\_return](/ref/uopz.html#uopz_get_return) — Gets a
    previous set return value for a function
-   [uopz\_get\_static](/ref/uopz.html#uopz_get_static) — Gets the
    static variables from function or method scope
-   [uopz\_implement](/ref/uopz.html#uopz_implement) — Implements an
    interface at runtime
-   [uopz\_overload](/ref/uopz.html#uopz_overload) — Overload a VM
    opcode
-   [uopz\_redefine](/ref/uopz.html#uopz_redefine) — Redefine a constant
-   [uopz\_rename](/ref/uopz.html#uopz_rename) — Rename a function at
    runtime
-   [uopz\_restore](/ref/uopz.html#uopz_restore) — Restore a previously
    backed up function
-   [uopz\_set\_hook](/ref/uopz.html#uopz_set_hook) — Sets hook to
    execute when entering a function or method
-   [uopz\_set\_mock](/ref/uopz.html#uopz_set_mock) — Use mock instead
    of class for new objects
-   [uopz\_set\_property](/ref/uopz.html#uopz_set_property) — Sets value
    of existing class or instance property
-   [uopz\_set\_return](/ref/uopz.html#uopz_set_return) — Provide a
    return value for an existing function
-   [uopz\_set\_static](/ref/uopz.html#uopz_set_static) — Sets the
    static variables in function or method scope
-   [uopz\_undefine](/ref/uopz.html#uopz_undefine) — Undefine a constant
-   [uopz\_unset\_hook](/ref/uopz.html#uopz_unset_hook) — Removes
    previously set hook on function or method
-   [uopz\_unset\_mock](/ref/uopz.html#uopz_unset_mock) — Unset
    previously set mock
-   [uopz\_unset\_return](/ref/uopz.html#uopz_unset_return) — Unsets a
    previously set return value for a function

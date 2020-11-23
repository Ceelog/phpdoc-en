boolval
=======

Get the boolean value of a variable

### Description

<span class="type">bool</span> <span class="methodname">boolval</span> (
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
)

Returns the <span class="type">bool</span> value of `var`.

### Parameters

`var`  
The scalar value being converted to a <span class="type">bool</span>.

### Return Values

The <span class="type">bool</span> value of `var`.

### Examples

**Example \#1 <span class="function">boolval</span> examples**

``` php
<?php
echo '0:        '.(boolval(0) ? 'true' : 'false')."\n";
echo '42:       '.(boolval(42) ? 'true' : 'false')."\n";
echo '0.0:      '.(boolval(0.0) ? 'true' : 'false')."\n";
echo '4.2:      '.(boolval(4.2) ? 'true' : 'false')."\n";
echo '"":       '.(boolval("") ? 'true' : 'false')."\n";
echo '"string": '.(boolval("string") ? 'true' : 'false')."\n";
echo '"0":      '.(boolval("0") ? 'true' : 'false')."\n";
echo '"1":      '.(boolval("1") ? 'true' : 'false')."\n";
echo '[1, 2]:   '.(boolval([1, 2]) ? 'true' : 'false')."\n";
echo '[]:       '.(boolval([]) ? 'true' : 'false')."\n";
echo 'stdClass: '.(boolval(new stdClass) ? 'true' : 'false')."\n";
?>
```

The above example will output:

    0:        false
    42:       true
    0.0:      false
    4.2:      true
    "":       false
    "string": true
    "0":      false
    "1":      true
    [1, 2]:   true
    []:       false
    stdClass: true

### See Also

-   <span class="function">floatval</span>
-   <span class="function">intval</span>
-   <span class="function">strval</span>
-   <span class="function">settype</span>
-   <span class="function">is\_bool</span>
-   <a href="/language/types/type-juggling.html" class="link">Type juggling</a>

debug\_zval\_dump
=================

Dumps a string representation of an internal zend value to output

### Description

<span class="type">void</span> <span
class="methodname">debug\_zval\_dump</span> ( <span
class="methodparam"><span class="type">mixed</span> `$variable`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$variables`</span> )

Dumps a string representation of an internal zend value to output.

### Parameters

`variable`  
The variable to dump.

`variables`  
Further variables to dump.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">debug\_zval\_dump</span> example**

``` php
<?php
$var1 = 'Hello World';
$var2 = '';

$var2 =& $var1;

debug_zval_dump(&$var1);
?>
```

The above example will output:

    &string(11) "Hello World" refcount(3)

> **Note**: **Beware the *refcount***  
>
> The *refcount* value returned by this function is non-obvious in
> certain circumstances. For example, a developer might expect the above
> example to indicate a *refcount* of *2*. The third reference is
> created when actually calling <span
> class="function">debug\_zval\_dump</span>.
>
> This behavior is further compounded when a variable is not passed to
> <span class="function">debug\_zval\_dump</span> by reference. To
> illustrate, consider a slightly modified version of the above example:
>
> ``` php
> <?php
> $var1 = 'Hello World';
> $var2 = '';
>
> $var2 =& $var1;
>
> debug_zval_dump($var1); // not passed by reference, this time
> ?>
> ```
>
> The above example will output:
>
>     string(11) "Hello World" refcount(1)
>
> Why *refcount(1)*? Because a copy of *$var1* is being made, when the
> function is called.
>
> This function becomes even *more* confusing when a variable with a
> *refcount* of *1* is passed (by copy/value):
>
> ``` php
> <?php
> $var1 = 'Hello World';
>
> debug_zval_dump($var1);
> ?>
> ```
>
> The above example will output:
>
>     string(11) "Hello World" refcount(2)
>
> A *refcount* of *2*, here, is extremely non-obvious. Especially
> considering the above examples. So what's happening?
>
> When a variable has a single reference (as did *$var1* before it was
> used as an argument to <span
> class="function">debug\_zval\_dump</span>), PHP's engine optimizes the
> manner in which it is passed to a function. Internally, PHP treats
> *$var1* like a reference (in that the *refcount* is increased for the
> scope of this function), with the caveat that *if* the passed
> reference happens to be written to, a copy is made, but only at the
> moment of writing. This is known as "copy on write."
>
> So, if <span class="function">debug\_zval\_dump</span> happened to
> write to its sole parameter (and it doesn't), then a copy would be
> made. Until then, the parameter remains a reference, causing the
> *refcount* to be incremented to *2* for the scope of the function
> call.

### See Also

-   <span class="function">var\_dump</span>
-   <span class="function">debug\_backtrace</span>
-   <a href="/language/references.html" class="link">References Explained</a>
-   <a href="http://derickrethans.nl/php_references_article.php" class="link external">» References Explained (by Derick Rethans)</a>

doubleval
=========

Alias of <span class="function">floatval</span>

### Description

This function is an alias of: <span class="function">floatval</span>.

empty
=====

Determine whether a variable is empty

### Description

<span class="type">bool</span> <span class="methodname">empty</span> (
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
)

Determine whether a variable is considered to be empty. A variable is
considered empty if it does not exist or if its value equals
**`FALSE`**. <span class="function">empty</span> does not generate a
warning if the variable does not exist.

### Parameters

`var`  
Variable to be checked

> **Note**:
>
> Prior to PHP 5.5, <span class="function">empty</span> only supports
> variables; anything else will result in a parse error. In other words,
> the following will not work: **empty(trim($name))**. Instead, use
> **trim($name) == false**.

No warning is generated if the variable does not exist. That means <span
class="function">empty</span> is essentially the concise equivalent to
**!isset($var) \|\| $var == false**.

### Return Values

Returns **`FALSE`** if `var` exists and has a non-empty, non-zero value.
Otherwise returns **`TRUE`**.

The following values are considered to be empty:

-   *""* (an empty string)
-   *0* (0 as an integer)
-   *0.0* (0 as a float)
-   *"0"* (0 as a string)
-   **`NULL`**
-   **`FALSE`**
-   *array()* (an empty array)

### Examples

**Example \#1 A simple <span class="function">empty</span> / <span
class="function">isset</span> comparison.**

``` php
<?php
$var = 0;

// Evaluates to true because $var is empty
if (empty($var)) {
    echo '$var is either 0, empty, or not set at all';
}

// Evaluates as true because $var is set
if (isset($var)) {
    echo '$var is set even though it is empty';
}
?>
```

**Example \#2 <span class="function">empty</span> on String Offsets**

PHP 5.4 changes how <span class="function">empty</span> behaves when
passed string offsets.

``` php
<?php
$expected_array_got_string = 'somestring';
var_dump(empty($expected_array_got_string['some_key']));
var_dump(empty($expected_array_got_string[0]));
var_dump(empty($expected_array_got_string['0']));
var_dump(empty($expected_array_got_string[0.5]));
var_dump(empty($expected_array_got_string['0.5']));
var_dump(empty($expected_array_got_string['0 Mostel']));
?>
```

Output of the above example in PHP 5.3:

    bool(false)
    bool(false)
    bool(false)
    bool(false)
    bool(false)
    bool(false)

Output of the above example in PHP 5.4:

    bool(true)
    bool(false)
    bool(false)
    bool(false)
    bool(true)
    bool(true)

### Notes

> **Note**: <span class="simpara">Because this is a language construct
> and not a function, it cannot be called using
> <a href="/functions/variable-functions.html" class="link">variable functions</a>.</span>

> **Note**:
>
> When using <span class="function">empty</span> on inaccessible object
> properties, the
> <a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a>
> overloading method will be called, if declared.

### See Also

-   <span class="function">isset</span>
-   <a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a>
-   <span class="function">unset</span>
-   <span class="function">array\_key\_exists</span>
-   <span class="function">count</span>
-   <span class="function">strlen</span>
-   <a href="/types/comparisons.html" class="link">The type comparison tables</a>

floatval
========

Get float value of a variable

### Description

<span class="type">float</span> <span class="methodname">floatval</span>
( <span class="methodparam"><span class="type">mixed</span>
`$var`</span> )

Gets the <span class="type">float</span> value of `var`.

### Parameters

`var`  
May be any scalar type. <span class="function">floatval</span> should
not be used on objects, as doing so will emit an **`E_NOTICE`** level
error and return 1.

### Return Values

The float value of the given variable. Empty arrays return 0, non-empty
arrays return 1.

Strings will most likely return 0 although this depends on the leftmost
characters of the string. The common rules of
<a href="/language/types/float.html#language.types.float.casting" class="link">float casting</a>
apply.

### Examples

**Example \#1 <span class="function">floatval</span> Example**

``` php
<?php
$var = '122.34343The';
$float_value_of_var = floatval($var);
echo $float_value_of_var; // 122.34343
?>
```

**Example \#2 <span class="function">floatval</span> non-numeric
leftmost characters Example**

``` php
<?php
$var = 'The122.34343';
$float_value_of_var = floatval($var);
echo $float_value_of_var; // 0
?>
```

### See Also

-   <span class="function">boolval</span>
-   <span class="function">intval</span>
-   <span class="function">strval</span>
-   <span class="function">settype</span>
-   <a href="/language/types/type-juggling.html" class="link">Type juggling</a>

get\_defined\_vars
==================

Returns an array of all defined variables

### Description

<span class="type">array</span> <span
class="methodname">get\_defined\_vars</span> ( <span
class="methodparam">void</span> )

This function returns a multidimensional array containing a list of all
defined variables, be them environment, server or user-defined
variables, within the scope that <span
class="function">get\_defined\_vars</span> is called.

### Return Values

A multidimensional array with all the variables.

### Examples

**Example \#1 <span class="function">get\_defined\_vars</span> Example**

``` php
<?php
$b = array(1, 1, 2, 3, 5, 8);

$arr = get_defined_vars();

// print $b
print_r($arr["b"]);

/* print path to the PHP interpreter (if used as a CGI)
 * e.g. /usr/local/bin/php */
echo $arr["_"];

// print the command-line parameters if any
print_r($arr["argv"]);

// print all the server vars
print_r($arr["_SERVER"]);

// print all the available keys for the arrays of variables
print_r(array_keys(get_defined_vars()));
?>
```

### See Also

-   <span class="function">isset</span>
-   <span class="function">get\_defined\_functions</span>
-   <span class="function">get\_defined\_constants</span>

get\_resource\_type
===================

Returns the resource type

### Description

<span class="type">string</span> <span
class="methodname">get\_resource\_type</span> ( <span
class="methodparam"><span class="type">resource</span> `$handle`</span>
)

This function gets the type of the given resource.

### Parameters

`handle`  
The evaluated resource handle.

### Return Values

If the given `handle` is a resource, this function will return a string
representing its type. If the type is not identified by this function,
the return value will be the string *Unknown*.

This function will return **`NULL`** and generate an error if `handle`
is not a <span class="type">resource</span>.

### Examples

**Example \#1 <span class="function">get\_resource\_type</span>
example**

``` php
<?php
// prints: mysql link
$c = mysql_connect();
echo get_resource_type($c) . "\n";

// prints: stream
$fp = fopen("foo", "w");
echo get_resource_type($fp) . "\n";

// prints: domxml document
$doc = new_xmldoc("1.0");
echo get_resource_type($doc->doc) . "\n";
?>
```

gettype
=======

Get the type of a variable

### Description

<span class="type">string</span> <span class="methodname">gettype</span>
( <span class="methodparam"><span class="type">mixed</span>
`$var`</span> )

Returns the type of the PHP variable `var`. For type checking, use
*is\_\** functions.

### Parameters

`var`  
The variable being type checked.

### Return Values

Possible values for the returned string are:

-   *"boolean"*
-   *"integer"*
-   *"double"* (for historical reasons *"double"* is returned in case of
    a <span class="type">float</span>, and not simply *"float"*)
-   *"string"*
-   *"array"*
-   *"object"*
-   *"resource"*
-   *"resource (closed)"* as of PHP 7.2.0
-   *"NULL"*
-   *"unknown type"*

### Examples

**Example \#1 <span class="function">gettype</span> example**

``` php
<?php

$data = array(1, 1., NULL, new stdClass, 'foo');

foreach ($data as $value) {
    echo gettype($value), "\n";
}

?>
```

The above example will output something similar to:

    integer
    double
    NULL
    object
    string

### Changelog

| Version | Description                                                                                                                           |
|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | Closed resources are now reported as *'resource (closed)'*. Previously the returned value for closed resources were *'unknown type'*. |

### See Also

-   <span class="function">settype</span>
-   <span class="function">get\_class</span>
-   <span class="function">is\_array</span>
-   <span class="function">is\_bool</span>
-   <span class="function">is\_callable</span>
-   <span class="function">is\_float</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_null</span>
-   <span class="function">is\_numeric</span>
-   <span class="function">is\_object</span>
-   <span class="function">is\_resource</span>
-   <span class="function">is\_scalar</span>
-   <span class="function">is\_string</span>
-   <span class="function">function\_exists</span>
-   <span class="function">method\_exists</span>

intval
======

Get the integer value of a variable

### Description

<span class="type">int</span> <span class="methodname">intval</span> (
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
\[, <span class="methodparam"><span class="type">int</span> `$base`<span
class="initializer"> = 10</span></span> \] )

Returns the <span class="type">int</span> value of `var`, using the
specified `base` for the conversion (the default is base 10). <span
class="function">intval</span> should not be used on objects, as doing
so will emit an **`E_NOTICE`** level error and return 1.

### Parameters

`var`  
The scalar value being converted to an integer

`base`  
The base for the conversion

> **Note**:
>
> If `base` is 0, the base used is determined by the format of `var`:
>
> -   <span class="simpara"> if string includes a "0x" (or "0X") prefix,
>     the base is taken as 16 (hex); otherwise, </span>
> -   <span class="simpara"> if string starts with "0", the base is
>     taken as 8 (octal); otherwise, </span>
> -   <span class="simpara"> the base is taken as 10 (decimal). </span>

### Return Values

The integer value of `var` on success, or 0 on failure. Empty arrays
return 0, non-empty arrays return 1.

The maximum value depends on the system. 32 bit systems have a maximum
signed integer range of -2147483648 to 2147483647. So for example on
such a system, *intval('1000000000000')* will return 2147483647. The
maximum signed integer value for 64 bit systems is 9223372036854775807.

Strings will most likely return 0 although this depends on the leftmost
characters of the string. The common rules of
<a href="/language/types/integer.html#language.types.integer.casting" class="link">integer casting</a>
apply.

### Examples

**Example \#1 <span class="function">intval</span> examples**

The following examples are based on a 32 bit system.

``` php
<?php
echo intval(42);                      // 42
echo intval(4.2);                     // 4
echo intval('42');                    // 42
echo intval('+42');                   // 42
echo intval('-42');                   // -42
echo intval(042);                     // 34
echo intval('042');                   // 42
echo intval(1e10);                    // 1410065408
echo intval('1e10');                  // 1
echo intval(0x1A);                    // 26
echo intval(42000000);                // 42000000
echo intval(420000000000000000000);   // 0
echo intval('420000000000000000000'); // 2147483647
echo intval(42, 8);                   // 42
echo intval('42', 8);                 // 34
echo intval(array());                 // 0
echo intval(array('foo', 'bar'));     // 1
echo intval(false);                   // 0
echo intval(true);                    // 1
?>
```

### Notes

> **Note**:
>
> The `base` parameter has no effect unless the `var` parameter is a
> string.

### See Also

-   <span class="function">boolval</span>
-   <span class="function">floatval</span>
-   <span class="function">strval</span>
-   <span class="function">settype</span>
-   <span class="function">is\_numeric</span>
-   <a href="/language/types/type-juggling.html" class="link">Type juggling</a>
-   <a href="/ref/bc.html" class="link">BCMath Arbitrary Precision Mathematics Functions</a>

is\_array
=========

Finds whether a variable is an array

### Description

<span class="type">bool</span> <span class="methodname">is\_array</span>
( <span class="methodparam"><span class="type">mixed</span>
`$var`</span> )

Finds whether the given variable is an array.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is an <span class="type">array</span>,
**`FALSE`** otherwise.

### Examples

**Example \#1 Check that variable is an array**

``` php
<?php
$yes = array('this', 'is', 'an array');

echo is_array($yes) ? 'Array' : 'not an Array';
echo "\n";

$no = 'this is a string';

echo is_array($no) ? 'Array' : 'not an Array';
?>
```

The above example will output:

    Array
    not an Array

### See Also

-   <span class="function">is\_float</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_string</span>
-   <span class="function">is\_object</span>

is\_bool
========

Finds out whether a variable is a boolean

### Description

<span class="type">bool</span> <span class="methodname">is\_bool</span>
( <span class="methodparam"><span class="type">mixed</span>
`$var`</span> )

Finds whether the given variable is a boolean.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is a <span class="type">bool</span>,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_bool</span> examples**

``` php
<?php
$a = false;
$b = 0;

// Since $a is a boolean, it will return true
if (is_bool($a) === true) {
    echo "Yes, this is a boolean";
}

// Since $b is not a boolean, it will return false
if (is_bool($b) === false) {
    echo "No, this is not a boolean";
}
?>
```

### See Also

-   <span class="function">is\_float</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_string</span>
-   <span class="function">is\_object</span>
-   <span class="function">is\_array</span>

is\_callable
============

Verify that the contents of a variable can be called as a function

### Description

<span class="type">bool</span> <span
class="methodname">is\_callable</span> ( <span class="methodparam"><span
class="type">mixed</span> `$var`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$syntax_only`<span
class="initializer"> = **`FALSE`**</span></span> \[, <span
class="methodparam"><span class="type">string</span>
`&$callable_name`</span> \]\] )

Verify that a value is a <span class="type">callable</span>.

### Parameters

`var`  
The value to check

`syntax_only`  
If set to **`TRUE`** the function only verifies that `var` might be a
function or method. It will only reject simple variables that are not
strings, or an array that does not have a valid structure to be used as
a callback. The valid ones are supposed to have only 2 entries, the
first of which is an object or a string, and the second a string.

`callable_name`  
Receives the "callable name". In the example below it is
"someClass::someMethod". Note, however, that despite the implication
that someClass::SomeMethod() is a callable static method, this is not
the case.

### Return Values

Returns **`TRUE`** if `var` is callable, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_callable</span> example**

``` php
<?php
//  How to check a variable to see if it can be called
//  as a function.

//
//  Simple variable containing a function
//

function someFunction() 
{
}

$functionVariable = 'someFunction';

var_dump(is_callable($functionVariable, false, $callable_name));  // bool(true)

echo $callable_name, "\n";  // someFunction

//
//  Array containing a method
//

class someClass {

  function someMethod() 
  {
  }

}

$anObject = new someClass();

$methodVariable = array($anObject, 'someMethod');

var_dump(is_callable($methodVariable, true, $callable_name));  //  bool(true)

echo $callable_name, "\n";  //  someClass::someMethod

?>
```

**Example \#2 <span class="function">is\_callable</span> and
constructors**

As of PHP 5.3.0 <span class="function">is\_callable</span> reports
constructors as not being callable. This affects PHP 5 style
constructors (*\_\_construct*) as well as PHP 4 style constructors (i.e.
methods with the same name as the class). Formerly, both cases have been
considered callable.

``` php
<?php

class Foo
{
    public function __construct() {}
    public function foo() {}
}

var_dump(
    is_callable(array('Foo', '__construct')),
    is_callable(array('Foo', 'foo'))
);
```

The above example will output:

    bool(false)
    bool(false)

### See Also

-   <span class="function">function\_exists</span>
-   <span class="function">method\_exists</span>

is\_countable
=============

Verify that the contents of a variable is a countable value

### Description

<span class="type">bool</span> <span
class="methodname">is\_countable</span> ( <span
class="methodparam"><span class="type">mixed</span> `$var`</span> )

Verify that the contents of a variable is an <span
class="type">array</span> or an object implementing <span
class="classname">Countable</span>

### Parameters

`var`  
The value to check

### Return Values

Returns **`TRUE`** if `var` is countable, **`FALSE`** otherwise.

### Changelog

| Version | Description                                                 |
|---------|-------------------------------------------------------------|
| 7.3.0   | <span class="function">is\_countable</span> has been added. |

### Examples

**Example \#1 <span class="function">is\_countable</span> examples**

``` php
<?php
var_dump(is_countable([1, 2, 3])); // bool(true)
var_dump(is_countable(new ArrayIterator(['foo', 'bar', 'baz']))); // bool(true)
var_dump(is_countable(new ArrayIterator())); // bool(true)
var_dump(is_countable(new stdClass())); // bool(false)
```

### See Also

-   <span class="function">is\_array</span>
-   <span class="function">is\_object</span>
-   <span class="function">is\_iterable</span>
-   <span class="function">is\_bool</span>

is\_double
==========

Alias of <span class="function">is\_float</span>

### Description

This function is an alias of: <span class="function">is\_float</span>.

is\_float
=========

Finds whether the type of a variable is float

### Description

<span class="type">bool</span> <span class="methodname">is\_float</span>
( <span class="methodparam"><span class="type">mixed</span>
`$var`</span> )

Finds whether the type of the given variable is float.

> **Note**:
>
> To test if a variable is a number or a numeric string (such as form
> input, which is always a string), you must use <span
> class="function">is\_numeric</span>.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is a <span class="type">float</span>,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_float</span> example**

``` php
var_dump(is_float(27.25));
var_dump(is_float('abc'));
var_dump(is_float(23));
var_dump(is_float(23.5));
var_dump(is_float(1e7));  //Scientific Notation
var_dump(is_float(true));
?>
```

The above example will output:

    bool(true)
    bool(false)
    bool(false)
    bool(true)
    bool(true)
    bool(false)

### See Also

-   <span class="function">is\_bool</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_numeric</span>
-   <span class="function">is\_string</span>
-   <span class="function">is\_array</span>
-   <span class="function">is\_object</span>

is\_int
=======

Find whether the type of a variable is integer

### Description

<span class="type">bool</span> <span class="methodname">is\_int</span> (
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
)

Finds whether the type of the given variable is integer.

> **Note**:
>
> To test if a variable is a number or a numeric string (such as form
> input, which is always a string), you must use <span
> class="function">is\_numeric</span>.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is an <span class="type">int</span>,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_int</span> example**

``` php
<?php
$values = array(23, "23", 23.5, "23.5", null, true, false);
foreach ($values as $value) {
    echo "is_int(";
    var_export($value);
    echo ") = ";
    var_dump(is_int($value));
}
?>
```

The above example will output:

    is_int(23) = bool(true)
    is_int('23') = bool(false)
    is_int(23.5) = bool(false)
    is_int('23.5') = bool(false)
    is_int(NULL) = bool(false)
    is_int(true) = bool(false)
    is_int(false) = bool(false)

### See Also

-   <span class="function">is\_bool</span>
-   <span class="function">is\_float</span>
-   <span class="function">is\_numeric</span>
-   <span class="function">is\_string</span>
-   <span class="function">is\_array</span>
-   <span class="function">is\_object</span>

is\_integer
===========

Alias of <span class="function">is\_int</span>

### Description

This function is an alias of: <span class="function">is\_int</span>.

is\_iterable
============

Verify that the contents of a variable is an iterable value

### Description

<span class="type">bool</span> <span
class="methodname">is\_iterable</span> ( <span class="methodparam"><span
class="type">mixed</span> `$var`</span> )

Verify that the contents of a variable is accepted by the <span
class="type">iterable</span> pseudo-type, i.e. that it is either an
<span class="type">array</span> or an object implementing <span
class="classname">Traversable</span>

### Parameters

`var`  
The value to check

### Return Values

Returns **`TRUE`** if `var` is iterable, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_iterable</span> examples**

``` php
<?php

var_dump(is_iterable([1, 2, 3]));  // bool(true)
var_dump(is_iterable(new ArrayIterator([1, 2, 3])));  // bool(true)
var_dump(is_iterable((function () { yield 1; })()));  // bool(true)
var_dump(is_iterable(1));  // bool(false)
var_dump(is_iterable(new stdClass()));  // bool(false)

?>
```

### See Also

-   <span class="function">is\_array</span>

is\_long
========

Alias of <span class="function">is\_int</span>

### Description

This function is an alias of: <span class="function">is\_int</span>.

is\_null
========

Finds whether a variable is **`NULL`**

### Description

<span class="type">bool</span> <span class="methodname">is\_null</span>
( <span class="methodparam"><span class="type">mixed</span>
`$var`</span> )

Finds whether the given variable is **`NULL`**.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is <span class="type">null</span>,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_null</span> example**

``` php
<?php

error_reporting(E_ALL);

$foo = NULL;
var_dump(is_null($inexistent), is_null($foo));

?>
```

    Notice: Undefined variable: inexistent in ...
    bool(true)
    bool(true)

### See Also

-   The
    <a href="/language/types/null.html#language.types.null.syntax" class="link"><strong><code>NULL</code></strong></a>
    type
-   <span class="function">isset</span>
-   <span class="function">is\_bool</span>
-   <span class="function">is\_numeric</span>
-   <span class="function">is\_float</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_string</span>
-   <span class="function">is\_object</span>
-   <span class="function">is\_array</span>

is\_numeric
===========

Finds whether a variable is a number or a numeric string

### Description

<span class="type">bool</span> <span
class="methodname">is\_numeric</span> ( <span class="methodparam"><span
class="type">mixed</span> `$var`</span> )

Finds whether the given variable is numeric. Numeric strings consist of
optional whitespace, optional sign, any number of digits, optional
decimal part and optional exponential part. Thus *+0123.45e6* is a valid
numeric value. Hexadecimal (e.g. *0xf4c3b00c*) and binary (e.g.
*0b10100111001*) notation is not allowed.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is a number or a numeric string, **`FALSE`**
otherwise.

### Examples

**Example \#1 <span class="function">is\_numeric</span> examples**

``` php
<?php
$tests = array(
    "42",
    1337,
    0x539,
    02471,
    0b10100111001,
    1337e0,
    "0x539",
    "02471",
    "0b10100111001",
    "1337e0",
    "not numeric",
    array(),
    9.1,
    null
);

foreach ($tests as $element) {
    if (is_numeric($element)) {
        echo var_export($element, true) . " is numeric", PHP_EOL;
    } else {
        echo var_export($element, true) . " is NOT numeric", PHP_EOL;
    }
}
?>
```

The above example will output:

    '42' is numeric
    1337 is numeric
    1337 is numeric
    1337 is numeric
    1337 is numeric
    1337.0 is numeric
    '0x539' is NOT numeric
    '02471' is numeric
    '0b10100111001' is NOT numeric
    '1337e0' is numeric
    'not numeric' is NOT numeric
    array (
    ) is NOT numeric
    9.1 is numeric
    NULL is NOT numeric

### Changelog

| Version | Description                                                                                                                                                            |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.0.0   | Strings in hexadecimal (e.g. *0xf4c3b00c*) notation are no longer regarded as numeric strings, i.e. <span class="function">is\_numeric</span> returns **`FALSE`** now. |

### See Also

-   <span class="function">ctype\_digit</span>
-   <span class="function">is\_bool</span>
-   <span class="function">is\_null</span>
-   <span class="function">is\_float</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_string</span>
-   <span class="function">is\_object</span>
-   <span class="function">is\_array</span>

is\_object
==========

Finds whether a variable is an object

### Description

<span class="type">bool</span> <span
class="methodname">is\_object</span> ( <span class="methodparam"><span
class="type">mixed</span> `$var`</span> )

Finds whether the given variable is an object.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is an <span class="type">object</span>,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_object</span> example**

``` php
<?php
// Declare a simple function to return an 
// array from our object
function get_students($obj)
{
    if (!is_object($obj)) {
        return false;
    }

    return $obj->students;
}

// Declare a new class instance and fill up 
// some values
$obj = new stdClass();
$obj->students = array('Kalle', 'Ross', 'Felipe');

var_dump(get_students(null));
var_dump(get_students($obj));
?>
```

### Changelog

| Version | Description                                                                                                                                                                                                                    |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="function">is\_object</span> now returns **`TRUE`** for unserialized objects without a class definition (class of <span class="classname">\_\_PHP\_Incomplete\_Class</span>). Previously **`FALSE`** was returned. |

### See Also

-   <span class="function">is\_bool</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_float</span>
-   <span class="function">is\_string</span>
-   <span class="function">is\_array</span>

is\_real
========

Alias of <span class="function">is\_float</span>

### Description

This function is an alias of: <span class="function">is\_float</span>.

**Warning**

This alias was *DEPRECATED* in PHP 7.4.0, and *REMOVED* as of PHP 8.0.0.

is\_resource
============

Finds whether a variable is a resource

### Description

<span class="type">bool</span> <span
class="methodname">is\_resource</span> ( <span class="methodparam"><span
class="type">mixed</span> `$var`</span> )

Finds whether the given variable is a <span
class="type">resource</span>.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is a <span class="type">resource</span>,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_resource</span> example**

``` php
<?php

$db_link = @mysql_connect('localhost', 'mysql_user', 'mysql_pass');
if (!is_resource($db_link)) {
    die('Can\'t connect : ' . mysql_error());
}

?>
```

### Notes

> **Note**:
>
> <span class="function">is\_resource</span> is not a strict
> type-checking method: it will return **`FALSE`** if `var` is a
> resource variable that has been closed.

### See Also

-   <a href="/language/types/resource.html" class="link">The resource-type documentation</a>
-   <span class="function">get\_resource\_type</span>

is\_scalar
==========

Finds whether a variable is a scalar

### Description

<span class="type">bool</span> <span
class="methodname">is\_scalar</span> ( <span class="methodparam"><span
class="type">mixed</span> `$var`</span> )

Finds whether the given variable is a scalar.

Scalar variables are those containing an <span class="type">int</span>,
<span class="type">float</span>, <span class="type">string</span> or
<span class="type">bool</span>. Types <span class="type">array</span>,
<span class="type">object</span> and <span class="type">resource</span>
are not scalar.

> **Note**:
>
> <span class="function">is\_scalar</span> does not consider <span
> class="type">resource</span> type values to be scalar as resources are
> abstract datatypes which are currently based on integers. This
> implementation detail should not be relied upon, as it may change.

> **Note**:
>
> <span class="function">is\_scalar</span> does not consider NULL to be
> scalar.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is a scalar, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_scalar</span> example**

``` php
<?php
function show_var($var) 
{
    if (is_scalar($var)) {
        echo $var;
    } else {
        var_dump($var);
    }
}
$pi = 3.1416;
$proteins = array("hemoglobin", "cytochrome c oxidase", "ferredoxin");

show_var($pi);
show_var($proteins)

?>
```

The above example will output:

    3.1416
    array(3) {
      [0]=>
      string(10) "hemoglobin"
      [1]=>
      string(20) "cytochrome c oxidase"
      [2]=>
      string(10) "ferredoxin"
    }

### See Also

-   <span class="function">is\_float</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_numeric</span>
-   <span class="function">is\_real</span>
-   <span class="function">is\_string</span>
-   <span class="function">is\_bool</span>
-   <span class="function">is\_object</span>
-   <span class="function">is\_array</span>

is\_string
==========

Find whether the type of a variable is string

### Description

<span class="type">bool</span> <span
class="methodname">is\_string</span> ( <span class="methodparam"><span
class="type">mixed</span> `$var`</span> )

Finds whether the type of the given variable is string.

### Parameters

`var`  
The variable being evaluated.

### Return Values

Returns **`TRUE`** if `var` is of type <span class="type">string</span>,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">is\_string</span> example**

``` php
<?php
$values = array(false, true, null, 'abc', '23', 23, '23.5', 23.5, '', ' ', '0', 0);
foreach ($values as $value) {
    echo "is_string(";
    var_export($value);
    echo ") = ";
    echo var_dump(is_string($value));
}
?>
```

The above example will output:

    is_string(false) = bool(false)
    is_string(true) = bool(false)
    is_string(NULL) = bool(false)
    is_string('abc') = bool(true)
    is_string('23') = bool(true)
    is_string(23) = bool(false)
    is_string('23.5') = bool(true)
    is_string(23.5) = bool(false)
    is_string('') = bool(true)
    is_string(' ') = bool(true)
    is_string('0') = bool(true)
    is_string(0) = bool(false)

### See Also

-   <span class="function">is\_float</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_bool</span>
-   <span class="function">is\_object</span>
-   <span class="function">is\_array</span>

isset
=====

Determine if a variable is declared and is different than **`NULL`**

### Description

<span class="type">bool</span> <span class="methodname">isset</span> (
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$vars`</span> )

Determine if a variable is considered set, this means if a variable is
declared and is different than **`NULL`**.

If a variable has been unset with the <span
class="function">unset</span> function, it is no longer considered to be
set.

<span class="function">isset</span> will return **`FALSE`** when
checking a variable that has been assigned to **`NULL`**. Also note that
a null character (*"\\0"*) is not equivalent to the PHP **`NULL`**
constant.

If multiple parameters are supplied then <span
class="function">isset</span> will return **`TRUE`** only if all of the
parameters are considered set. Evaluation goes from left to right and
stops as soon as an unset variable is encountered.

### Parameters

`var`  
The variable to be checked.

`vars`  
Further variables.

### Return Values

Returns **`TRUE`** if `var` exists and has any value other than
**`NULL`**. **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">isset</span> Examples**

``` php
<?php

$var = '';

// This will evaluate to TRUE so the text will be printed.
if (isset($var)) {
    echo "This var is set so I will print.";
}

// In the next examples we'll use var_dump to output
// the return value of isset().

$a = "test";
$b = "anothertest";

var_dump(isset($a));      // TRUE
var_dump(isset($a, $b)); // TRUE

unset ($a);

var_dump(isset($a));     // FALSE
var_dump(isset($a, $b)); // FALSE

$foo = NULL;
var_dump(isset($foo));   // FALSE

?>
```

This also work for elements in arrays:

``` php
<?php

$a = array ('test' => 1, 'hello' => NULL, 'pie' => array('a' => 'apple'));

var_dump(isset($a['test']));            // TRUE
var_dump(isset($a['foo']));             // FALSE
var_dump(isset($a['hello']));           // FALSE

// The key 'hello' equals NULL so is considered unset
// If you want to check for NULL key values then try: 
var_dump(array_key_exists('hello', $a)); // TRUE

// Checking deeper array values
var_dump(isset($a['pie']['a']));        // TRUE
var_dump(isset($a['pie']['b']));        // FALSE
var_dump(isset($a['cake']['a']['b']));  // FALSE

?>
```

**Example \#2 <span class="function">isset</span> on String Offsets**

PHP 5.4 changes how <span class="function">isset</span> behaves when
passed string offsets.

``` php
<?php
$expected_array_got_string = 'somestring';
var_dump(isset($expected_array_got_string['some_key']));
var_dump(isset($expected_array_got_string[0]));
var_dump(isset($expected_array_got_string['0']));
var_dump(isset($expected_array_got_string[0.5]));
var_dump(isset($expected_array_got_string['0.5']));
var_dump(isset($expected_array_got_string['0 Mostel']));
?>
```

Output of the above example in PHP 5.3:

    bool(true)
    bool(true)
    bool(true)
    bool(true)
    bool(true)
    bool(true)

Output of the above example in PHP 5.4:

    bool(false)
    bool(true)
    bool(true)
    bool(true)
    bool(false)
    bool(false)

### Notes

**Warning**

<span class="function">isset</span> only works with variables as passing
anything else will result in a parse error. For checking if
<a href="/language/constants.html" class="link">constants</a> are set
use the <span class="function">defined</span> function.

> **Note**: <span class="simpara">Because this is a language construct
> and not a function, it cannot be called using
> <a href="/functions/variable-functions.html" class="link">variable functions</a>.</span>

> **Note**:
>
> When using <span class="function">isset</span> on inaccessible object
> properties, the
> <a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a>
> overloading method will be called, if declared.

### See Also

-   <span class="function">empty</span>
-   <a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a>
-   <span class="function">unset</span>
-   <span class="function">defined</span>
-   <a href="/types/comparisons.html" class="link">the type comparison tables</a>
-   <span class="function">array\_key\_exists</span>
-   <span class="function">is\_null</span>
-   the error control
    <a href="/language/operators/errorcontrol.html" class="link">@</a>
    operator

print\_r
========

Prints human-readable information about a variable

### Description

<span class="type">mixed</span> <span class="methodname">print\_r</span>
( <span class="methodparam"><span class="type">mixed</span>
`$expression`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$return`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="function">print\_r</span> displays information about a
variable in a way that's readable by humans.

<span class="function">print\_r</span>, <span
class="function">var\_dump</span> and <span
class="function">var\_export</span> will also show protected and private
properties of objects. Static class members will not be shown.

### Parameters

`expression`  
The expression to be printed.

`return`  
If you would like to capture the output of <span
class="function">print\_r</span>, use the `return` parameter. When this
parameter is set to **`TRUE`**, <span class="function">print\_r</span>
will return the information rather than print it.

### Return Values

If given a <span class="type">string</span>, <span
class="type">int</span> or <span class="type">float</span>, the value
itself will be printed. If given an <span class="type">array</span>,
values will be presented in a format that shows keys and elements.
Similar notation is used for <span class="type">object</span>s.

When the `return` parameter is **`TRUE`**, this function will return a
<span class="type">string</span>. Otherwise, the return value is
**`TRUE`**.

### Notes

> **Note**:
>
> When the `return` parameter is used, this function uses internal
> output buffering so it cannot be used inside an <span
> class="function">ob\_start</span> callback function.

### Examples

**Example \#1 <span class="function">print\_r</span> example**

``` php
<pre>
<?php
$a = array ('a' => 'apple', 'b' => 'banana', 'c' => array ('x', 'y', 'z'));
print_r ($a);
?>
</pre>
```

The above example will output:

    <pre>
    Array
    (
        [a] => apple
        [b] => banana
        [c] => Array
            (
                [0] => x
                [1] => y
                [2] => z
            )
    )
    </pre>

**Example \#2 `return` parameter example**

``` php
<?php
$b = array ('m' => 'monkey', 'foo' => 'bar', 'x' => array ('x', 'y', 'z'));
$results = print_r($b, true); // $results now contains output from print_r
?>
```

### See Also

-   <span class="function">ob\_start</span>
-   <span class="function">var\_dump</span>
-   <span class="function">var\_export</span>

serialize
=========

Generates a storable representation of a value

### Description

<span class="type">string</span> <span
class="methodname">serialize</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

Generates a storable representation of a value.

This is useful for storing or passing PHP values around without losing
their type and structure.

To make the serialized string into a PHP value again, use <span
class="function">unserialize</span>.

### Parameters

`value`  
The value to be serialized. <span class="function">serialize</span>
handles all types, except the <span class="type">resource</span>-type
and some <span class="type">object</span>s (see note below). You can
even <span class="function">serialize</span> arrays that contain
references to itself. Circular references inside the array/object you
are serializing will also be stored. Any other reference will be lost.

When serializing objects, PHP will attempt to call the member functions
<a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>
or
<a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
prior to serialization. This is to allow the object to do any last
minute clean-up, etc. prior to being serialized. Likewise, when the
object is restored using <span class="function">unserialize</span> the
<a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>
or
<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
member function is called.

> **Note**:
>
> Object's private members have the class name prepended to the member
> name; protected members have a '\*' prepended to the member name.
> These prepended values have null bytes on either side.

### Return Values

Returns a string containing a byte-stream representation of `value` that
can be stored anywhere.

Note that this is a binary string which may include null bytes, and
needs to be stored and handled as such. For example, <span
class="function">serialize</span> output should generally be stored in a
BLOB field in a database, rather than a CHAR or TEXT field.

### Examples

**Example \#1 <span class="function">serialize</span> example**

``` php
<?php
// $session_data contains a multi-dimensional array with session
// information for the current user.  We use serialize() to store
// it in a database at the end of the request.

$conn = odbc_connect("webdb", "php", "chicken");
$stmt = odbc_prepare($conn,
      "UPDATE sessions SET data = ? WHERE id = ?");
$sqldata = array (serialize($session_data), $_SERVER['PHP_AUTH_USER']);
if (!odbc_execute($stmt, $sqldata)) {
    $stmt = odbc_prepare($conn,
     "INSERT INTO sessions (id, data) VALUES(?, ?)");
    if (!odbc_execute($stmt, $sqldata)) {
        /* Something went wrong.. */
    }
}
?>
```

### Notes

> **Note**:
>
> Note that many built-in PHP objects cannot be serialized. However,
> those with this ability either implement the <span
> class="interfacename">Serializable</span> interface or the magic
> <a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>/<a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>
> or
> <a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>/<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
> methods. If an internal class does not fulfill any of those
> requirements, it cannot reliably be serialized.
>
> There are some historical exceptions to the above rule, where some
> internal objects could be serialized without implementing the
> interface or exposing the methods. Notably, the <span
> class="classname">ArrayObject</span> prior to PHP 5.2.0.

**Warning**

When <span class="function">serialize</span> serializes objects, the
leading backslash is not included in the class name of namespaced
classes for maximum compatibility.

### See Also

-   <span class="function">unserialize</span>
-   <span class="function">var\_export</span>
-   <span class="function">json\_encode</span>
-   <a href="/language/oop5/serialization.html" class="link">Serializing Objects</a>
-   <a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
-   <a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
-   <a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>
-   <a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>

settype
=======

Set the type of a variable

### Description

<span class="type">bool</span> <span class="methodname">settype</span> (
<span class="methodparam"><span class="type">mixed</span> `&$var`</span>
, <span class="methodparam"><span class="type">string</span>
`$type`</span> )

Set the type of variable `var` to `type`.

### Parameters

`var`  
The variable being converted.

`type`  
Possibles values of `type` are:

-   <span class="simpara"> "boolean" or "bool" </span>
-   <span class="simpara"> "integer" or "int" </span>
-   <span class="simpara"> "float" or "double" </span>
-   <span class="simpara"> "string" </span>
-   <span class="simpara"> "array" </span>
-   <span class="simpara"> "object" </span>
-   <span class="simpara"> "null" </span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">settype</span> example**

``` php
<?php
$foo = "5bar"; // string
$bar = true;   // boolean

settype($foo, "integer"); // $foo is now 5   (integer)
settype($bar, "string");  // $bar is now "1" (string)
?>
```

### Notes

> **Note**:
>
> Maximum value for "int" is **`PHP_INT_MAX`**.

### See Also

-   <span class="function">gettype</span>
-   <a href="/language/types/type-juggling.html#language.types.typecasting" class="link">type-casting</a>
-   <a href="/language/types/type-juggling.html" class="link">type-juggling</a>

strval
======

Get string value of a variable

### Description

<span class="type">string</span> <span class="methodname">strval</span>
( <span class="methodparam"><span class="type">mixed</span>
`$var`</span> )

Get the string value of a variable. See the documentation on <span
class="type">string</span> for more information on converting to string.

This function performs no formatting on the returned value. If you are
looking for a way to format a numeric value as a string, please see
<span class="function">sprintf</span> or <span
class="function">number\_format</span>.

### Parameters

`var`  
The variable that is being converted to a <span
class="type">string</span>.

`var` may be any scalar type or an object that implements the
<a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>
method. You cannot use <span class="function">strval</span> on arrays or
on objects that do not implement the
<a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>
method.

### Return Values

The <span class="type">string</span> value of `var`.

### Examples

**Example \#1 <span class="function">strval</span> example using PHP 5's
magic
<a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>
method.**

``` php
<?php
class StrValTest
{
    public function __toString()
    {
        return __CLASS__;
    }
}

// Prints 'StrValTest'
echo strval(new StrValTest);
?>
```

### See Also

-   <span class="function">boolval</span>
-   <span class="function">floatval</span>
-   <span class="function">intval</span>
-   <span class="function">settype</span>
-   <span class="function">sprintf</span>
-   <span class="function">number\_format</span>
-   <a href="/language/types/type-juggling.html" class="link">Type juggling</a>
-   <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

unserialize
===========

Creates a PHP value from a stored representation

### Description

<span class="type">mixed</span> <span
class="methodname">unserialize</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span> \]
)

<span class="function">unserialize</span> takes a single serialized
variable and converts it back into a PHP value.

**Warning**

Do not pass untrusted user input to <span
class="function">unserialize</span> regardless of the `options` value of
*allowed\_classes*. Unserialization can result in code being loaded and
executed due to object instantiation and autoloading, and a malicious
user may be able to exploit this. Use a safe, standard data interchange
format such as JSON (via <span class="function">json\_decode</span> and
<span class="function">json\_encode</span>) if you need to pass
serialized data to the user.

If you need to unserialize externally-stored serialized data, consider
using <span class="function">hash\_hmac</span> for data validation. Make
sure data is not modified by anyone but you.

### Parameters

`str`  
The serialized string.

If the variable being unserialized is an object, after successfully
reconstructing the object PHP will automatically attempt to call the
<a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>
or
<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
methods (if one exists).

> **Note**: **unserialize\_callback\_func directive**  
>
> It's possible to set a callback-function which will be called, if an
> undefined class should be instantiated during unserializing. (to
> prevent getting an incomplete <span class="type">object</span>
> "\_\_PHP\_Incomplete\_Class".) Use your `php.ini`, <span
> class="function">ini\_set</span> or `.htaccess` to define
> <a href="/var/setup.html#" class="link">unserialize_callback_func</a>.
> Everytime an undefined class should be instantiated, it'll be called.
> To disable this feature just empty this setting.

`options`  
Any options to be provided to <span class="function">unserialize</span>,
as an associative array.

| Name               | Type                            | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|--------------------|---------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *allowed\_classes* | <span class="type">mixed</span> | <span class="simpara"> Either an <span class="type">array</span> of class names which should be accepted, **`FALSE`** to accept no classes, or **`TRUE`** to accept all classes. If this option is defined and <span class="function">unserialize</span> encounters an object of a class that isn't to be accepted, then the object will be instantiated as <span class="classname">\_\_PHP\_Incomplete\_Class</span> instead. </span> <span class="simpara"> Omitting this option is the same as defining it as **`TRUE`**: PHP will attempt to instantiate objects of any class. </span> |

### Return Values

The converted value is returned, and can be a <span
class="type">bool</span>, <span class="type">int</span>, <span
class="type">float</span>, <span class="type">string</span>, <span
class="type">array</span> or <span class="type">object</span>.

In case the passed string is not unserializeable, **`FALSE`** is
returned and **`E_NOTICE`** is issued.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                   |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | The *allowed\_classes* element of `options`) is now strictly typed, i.e. if anything other than an <span class="type">array</span> or a <span class="type">bool</span> is given, <span class="function">unserialize</span> returns **`FALSE`** and issues an **`E_WARNING`**. |
| 7.0.0   | The `options` parameter has been added.                                                                                                                                                                                                                                       |
| 5.6.0   | Manipulating the serialised data by replacing *C:* with *O:* to force object instantiation without calling the constructor will now fail.                                                                                                                                     |

### Examples

**Example \#1 <span class="function">unserialize</span> example**

``` php
<?php
// Here, we use unserialize() to load session data to the
// $session_data array from the string selected from a database.
// This example complements the one described with serialize().

$conn = odbc_connect("webdb", "php", "chicken");
$stmt = odbc_prepare($conn, "SELECT data FROM sessions WHERE id = ?");
$sqldata = array($_SERVER['PHP_AUTH_USER']);
if (!odbc_execute($stmt, $sqldata) || !odbc_fetch_into($stmt, $tmp)) {
    // if the execute or fetch fails, initialize to empty array
    $session_data = array();
} else {
    // we should now have the serialized data in $tmp[0].
    $session_data = unserialize($tmp[0]);
    if (!is_array($session_data)) {
        // something went wrong, initialize to empty array
        $session_data = array();
    }
}
?>
```

**Example \#2 unserialize\_callback\_func example**

``` php
<?php
$serialized_object='O:1:"a":1:{s:5:"value";s:3:"100";}';

ini_set('unserialize_callback_func', 'mycallback'); // set your callback_function

function mycallback($classname) 
{
    // just include a file containing your class definition
    // you get $classname to figure out which class definition is required
}
?>
```

### Notes

**Warning**

**`FALSE`** is returned both in the case of an error and if
unserializing the serialized **`FALSE`** value. It is possible to catch
this special case by comparing `str` with *serialize(false)* or by
catching the issued **`E_NOTICE`**.

### See Also

-   <span class="function">json\_encode</span>
-   <span class="function">json\_decode</span>
-   <span class="function">hash\_hmac</span>
-   <span class="function">serialize</span>
-   <a href="/language/oop5/autoload.html" class="link">Autoloading Classes</a>
-   <a href="/var/setup.html#" class="link">unserialize_callback_func</a>
-   <a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
-   <a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>
-   <a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>

unset
=====

Unset a given variable

### Description

<span class="type">void</span> <span class="methodname">unset</span> (
<span class="methodparam"><span class="type">mixed</span> `$var`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$vars`</span> )

<span class="function">unset</span> destroys the specified variables.

The behavior of <span class="function">unset</span> inside of a function
can vary depending on what type of variable you are attempting to
destroy.

If a globalized variable is <span class="function">unset</span> inside
of a function, only the local variable is destroyed. The variable in the
calling environment will retain the same value as before <span
class="function">unset</span> was called.

``` php
<?php
function destroy_foo() 
{
    global $foo;
    unset($foo);
}

$foo = 'bar';
destroy_foo();
echo $foo;
?>
```

The above example will output:

    bar

To <span class="function">unset</span> a global variable inside of a
function, then use the `$GLOBALS` array to do so:

``` php
<?php
function foo() 
{
    unset($GLOBALS['bar']);
}

$bar = "something";
foo();
?>
```

If a variable that is PASSED BY REFERENCE is <span
class="function">unset</span> inside of a function, only the local
variable is destroyed. The variable in the calling environment will
retain the same value as before <span class="function">unset</span> was
called.

``` php
<?php
function foo(&$bar) 
{
    unset($bar);
    $bar = "blah";
}

$bar = 'something';
echo "$bar\n";

foo($bar);
echo "$bar\n";
?>
```

The above example will output:

    something
    something

If a static variable is <span class="function">unset</span> inside of a
function, <span class="function">unset</span> destroys the variable only
in the context of the rest of a function. Following calls will restore
the previous value of a variable.

``` php
<?php
function foo()
{
    static $bar;
    $bar++;
    echo "Before unset: $bar, ";
    unset($bar);
    $bar = 23;
    echo "after unset: $bar\n";
}

foo();
foo();
foo();
?>
```

The above example will output:

    Before unset: 1, after unset: 23
    Before unset: 2, after unset: 23
    Before unset: 3, after unset: 23

### Parameters

`var`  
The variable to be unset.

`vars`  
Further variables.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">unset</span> example**

``` php
<?php
// destroy a single variable
unset($foo);

// destroy a single element of an array
unset($bar['quux']);

// destroy more than one variable
unset($foo1, $foo2, $foo3);
?>
```

**Example \#2 Using *(unset)* casting**

<a href="/language/types/null.html#language.types.null.casting" class="link"><em>(unset)</em></a>
casting is often confused with the <span class="function">unset</span>
function. *(unset)* casting serves only as a *NULL*-type cast, for
completeness. It does not alter the variable it's casting. The (unset)
cast is deprecated as of PHP 7.2.0.

``` php
<?php
$name = 'Felipe';

var_dump((unset) $name);
var_dump($name);
?>
```

The above example will output:

    NULL
    string(6) "Felipe"

### Notes

> **Note**: <span class="simpara">Because this is a language construct
> and not a function, it cannot be called using
> <a href="/functions/variable-functions.html" class="link">variable functions</a>.</span>

> **Note**:
>
> It is possible to unset even object properties visible in current
> context.

> **Note**:
>
> It is not possible to unset *$this* inside an object method.

> **Note**:
>
> When using <span class="function">unset</span> on inaccessible object
> properties, the
> <a href="/language/oop5/overloading.html#object.unset" class="link">__unset()</a>
> overloading method will be called, if declared.

### See Also

-   <span class="function">isset</span>
-   <span class="function">empty</span>
-   <a href="/language/oop5/overloading.html#object.unset" class="link">__unset()</a>
-   <span class="function">array\_splice</span>
-   <a href="/language/types/null.html#language.types.null.casting" class="link">(unset) casting</a>

var\_dump
=========

Dumps information about a variable

### Description

<span class="type">void</span> <span class="methodname">var\_dump</span>
( <span class="methodparam"><span class="type">mixed</span>
`$expression`</span> , <span class="methodparam"><span
class="type">mixed</span> `$expressions`</span> )

This function displays structured information about one or more
expressions that includes its type and value. Arrays and objects are
explored recursively with values indented to show structure.

All public, private and protected properties of objects will be returned
in the output unless the object implements a
<a href="/language/oop5/magic.html#language.oop5.magic.debuginfo" class="link">__debugInfo()</a>
method (implemented in PHP 5.6.0).

**Tip**

As with anything that outputs its result directly to the browser, the
<a href="/book/outcontrol.html" class="link">output-control functions</a>
can be used to capture the output of this function, and save it in a
<span class="type">string</span> (for example).

### Parameters

`expression`  
The expression to dump.

`expressions`  
Further expressions to dump.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">var\_dump</span> example**

``` php
<?php
$a = array(1, 2, array("a", "b", "c"));
var_dump($a);
?>
```

The above example will output:

    array(3) {
      [0]=>
      int(1)
      [1]=>
      int(2)
      [2]=>
      array(3) {
        [0]=>
        string(1) "a"
        [1]=>
        string(1) "b"
        [2]=>
        string(1) "c"
      }
    }

``` php
<?php

$b = 3.1;
$c = true;
var_dump($b, $c);

?>
```

The above example will output:

    float(3.1)
    bool(true)

### See Also

-   <span class="function">print\_r</span>
-   <span class="function">debug\_zval\_dump</span>
-   <span class="function">var\_export</span>
-   <a href="/language/oop5/magic.html#language.oop5.magic.debuginfo" class="link">__debugInfo()</a>

var\_export
===========

Outputs or returns a parsable string representation of a variable

### Description

<span class="type">mixed</span> <span
class="methodname">var\_export</span> ( <span class="methodparam"><span
class="type">mixed</span> `$expression`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$return`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="function">var\_export</span> gets structured information
about the given variable. It is similar to <span
class="function">var\_dump</span> with one exception: the returned
representation is valid PHP code.

### Parameters

`expression`  
The variable you want to export.

`return`  
If used and set to **`TRUE`**, <span class="function">var\_export</span>
will return the variable representation instead of outputting it.

### Return Values

Returns the variable representation when the `return` parameter is used
and evaluates to **`TRUE`**. Otherwise, this function will return
**`NULL`**.

### Notes

> **Note**:
>
> When the `return` parameter is used, this function uses internal
> output buffering so it cannot be used inside an <span
> class="function">ob\_start</span> callback function.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                                                     |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | Now exports <span class="classname">stdClass</span> objects as an array cast to an object (`(object) array( ... )`), rather than using the nonexistent method <span class="methodname">stdClass::\_\_setState</span>. The practical effect is that now <span class="classname">stdClass</span> is exportable, and the resulting code will even work on earlier versions of PHP. |

### Examples

**Example \#1 <span class="function">var\_export</span> Examples**

``` php
<?php
$a = array (1, 2, array ("a", "b", "c"));
var_export($a);
?>
```

The above example will output:

    array (
      0 => 1,
      1 => 2,
      2 => 
      array (
        0 => 'a',
        1 => 'b',
        2 => 'c',
      ),
    )

``` php
<?php

$b = 3.1;
$v = var_export($b, true);
echo $v;

?>
```

The above example will output:

    3.1

**Example \#2 Exporting stdClass (since PHP 7.3.0)**

``` php
<?php
$person = new stdClass;
$person->name = 'ElePHPant ElePHPantsdotter';
$person->website = 'https://php.net/elephpant.php';

var_export($person);
```

The above example will output:

    (object) array(
       'name' => 'ElePHPant ElePHPantsdotter',
       'website' => 'https://php.net/elephpant.php',
    )

**Example \#3 Exporting classes (since PHP 5.1.0)**

``` php
<?php
class A { public $var; }
$a = new A;
$a->var = 5;
var_export($a);
?>
```

The above example will output:

    A::__set_state(array(
       'var' => 5,
    ))

**Example \#4 Using
<a href="/language/oop5/magic.html#object.set-state" class="link">__set_state()</a>
(since PHP 5.1.0)**

``` php
<?php
class A
{
    public $var1;
    public $var2;

    public static function __set_state($an_array)
    {
        $obj = new A;
        $obj->var1 = $an_array['var1'];
        $obj->var2 = $an_array['var2'];
        return $obj;
    }
}

$a = new A;
$a->var1 = 5;
$a->var2 = 'foo';

eval('$b = ' . var_export($a, true) . ';'); // $b = A::__set_state(array(
                                            //    'var1' => 5,
                                            //    'var2' => 'foo',
                                            // ));
var_dump($b);
?>
```

The above example will output:

    object(A)#2 (2) {
      ["var1"]=>
      int(5)
      ["var2"]=>
      string(3) "foo"
    }

### Notes

> **Note**:
>
> Variables of type <span class="type">resource</span> couldn't be
> exported by this function.

> **Note**:
>
> <span class="function">var\_export</span> does not handle circular
> references as it would be close to impossible to generate parsable PHP
> code for that. If you want to do something with the full
> representation of an array or object, use <span
> class="function">serialize</span>.

**Warning**

When <span class="function">var\_export</span> exports objects, the
leading backslash is not included in the class name of namespaced
classes for maximum compatibility.

> **Note**:
>
> To be able to evaluate the PHP generated by <span
> class="function">var\_export</span>, all processed objects must
> implement the magic
> <a href="/language/oop5/magic.html#object.set-state" class="link">__set_state</a>
> method. The only exception is <span class="classname">stdClass</span>,
> which is exported using an array cast to an object.

### See Also

-   <span class="function">print\_r</span>
-   <span class="function">serialize</span>
-   <span class="function">var\_dump</span>

**Table of Contents**

-   [boolval](/ref/var.html#boolval) — Get the boolean value of a
    variable
-   [debug\_zval\_dump](/ref/var.html#debug_zval_dump) — Dumps a string
    representation of an internal zend value to output
-   [doubleval](/ref/var.html#doubleval) — Alias of floatval
-   [empty](/ref/var.html#empty) — Determine whether a variable is empty
-   [floatval](/ref/var.html#floatval) — Get float value of a variable
-   [get\_defined\_vars](/ref/var.html#get_defined_vars) — Returns an
    array of all defined variables
-   [get\_resource\_type](/ref/var.html#get_resource_type) — Returns the
    resource type
-   [gettype](/ref/var.html#gettype) — Get the type of a variable
-   [intval](/ref/var.html#intval) — Get the integer value of a variable
-   [is\_array](/ref/var.html#is_array) — Finds whether a variable is an
    array
-   [is\_bool](/ref/var.html#is_bool) — Finds out whether a variable is
    a boolean
-   [is\_callable](/ref/var.html#is_callable) — Verify that the contents
    of a variable can be called as a function
-   [is\_countable](/ref/var.html#is_countable) — Verify that the
    contents of a variable is a countable value
-   [is\_double](/ref/var.html#is_double) — Alias of is\_float
-   [is\_float](/ref/var.html#is_float) — Finds whether the type of a
    variable is float
-   [is\_int](/ref/var.html#is_int) — Find whether the type of a
    variable is integer
-   [is\_integer](/ref/var.html#is_integer) — Alias of is\_int
-   [is\_iterable](/ref/var.html#is_iterable) — Verify that the contents
    of a variable is an iterable value
-   [is\_long](/ref/var.html#is_long) — Alias of is\_int
-   [is\_null](/ref/var.html#is_null) — Finds whether a variable is NULL
-   [is\_numeric](/ref/var.html#is_numeric) — Finds whether a variable
    is a number or a numeric string
-   [is\_object](/ref/var.html#is_object) — Finds whether a variable is
    an object
-   [is\_real](/ref/var.html#is_real) — Alias of is\_float
-   [is\_resource](/ref/var.html#is_resource) — Finds whether a variable
    is a resource
-   [is\_scalar](/ref/var.html#is_scalar) — Finds whether a variable is
    a scalar
-   [is\_string](/ref/var.html#is_string) — Find whether the type of a
    variable is string
-   [isset](/ref/var.html#isset) — Determine if a variable is declared
    and is different than NULL
-   [print\_r](/ref/var.html#print_r) — Prints human-readable
    information about a variable
-   [serialize](/ref/var.html#serialize) — Generates a storable
    representation of a value
-   [settype](/ref/var.html#settype) — Set the type of a variable
-   [strval](/ref/var.html#strval) — Get string value of a variable
-   [unserialize](/ref/var.html#unserialize) — Creates a PHP value from
    a stored representation
-   [unset](/ref/var.html#unset) — Unset a given variable
-   [var\_dump](/ref/var.html#var_dump) — Dumps information about a
    variable
-   [var\_export](/ref/var.html#var_export) — Outputs or returns a
    parsable string representation of a variable

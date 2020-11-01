Function arguments
------------------

Information may be passed to functions via the argument list, which is a
comma-delimited list of expressions. The arguments are evaluated from
left to right.

PHP supports passing arguments by value (the default),
<a href="/functions/arguments.html#functions.arguments.by-reference" class="link">passing by reference</a>,
and
<a href="/functions/arguments.html#functions.arguments.default" class="link">default argument values</a>.
<a href="/functions/arguments.html#functions.variable-arg-list" class="link">Variable-length argument lists</a>
are also supported.

**Example \#1 Passing arrays to functions**

``` php
<?php
function takes_array($input)
{
    echo "$input[0] + $input[1] = ", $input[0]+$input[1];
}
?>
```

### Passing arguments by reference

By default, function arguments are passed by value (so that if the value
of the argument within the function is changed, it does not get changed
outside of the function). To allow a function to modify its arguments,
they must be passed by reference.

To have an argument to a function always passed by reference, prepend an
ampersand (&) to the argument name in the function definition:

**Example \#2 Passing function parameters by reference**

``` php
<?php
function add_some_extra(&$string)
{
    $string .= 'and something extra.';
}
$str = 'This is a string, ';
add_some_extra($str);
echo $str;    // outputs 'This is a string, and something extra.'
?>
```

### Default argument values

A function may define C++-style default values for scalar arguments as
follows:

**Example \#3 Use of default parameters in functions**

``` php
<?php
function makecoffee($type = "cappuccino")
{
    return "Making a cup of $type.\n";
}
echo makecoffee();
echo makecoffee(null);
echo makecoffee("espresso");
?>
```

The above example will output:

    Making a cup of cappuccino.
    Making a cup of .
    Making a cup of espresso.

PHP also allows the use of <span class="type">array</span>s and the
special type **`NULL`** as default values, for example:

**Example \#4 Using non-scalar types as default values**

``` php
<?php
function makecoffee($types = array("cappuccino"), $coffeeMaker = NULL)
{
    $device = is_null($coffeeMaker) ? "hands" : $coffeeMaker;
    return "Making a cup of ".join(", ", $types)." with $device.\n";
}
echo makecoffee();
echo makecoffee(array("cappuccino", "lavazza"), "teapot");
?>
```

The default value must be a constant expression, not (for example) a
variable, a class member or a function call.

Note that when using default arguments, any defaults should be on the
right side of any non-default arguments; otherwise, things will not work
as expected. Consider the following code snippet:

**Example \#5 Incorrect usage of default function arguments**

``` php
<?php
function makeyogurt($type = "acidophilus", $flavour)
{
    return "Making a bowl of $type $flavour.\n";
}
 
echo makeyogurt("raspberry");   // won't work as expected
?>
```

The above example will output:

    Warning: Missing argument 2 in call to makeyogurt() in 
    /usr/local/etc/httpd/htdocs/phptest/functest.html on line 41
    Making a bowl of raspberry .

Now, compare the above with this:

**Example \#6 Correct usage of default function arguments**

``` php
<?php
function makeyogurt($flavour, $type = "acidophilus")
{
    return "Making a bowl of $type $flavour.\n";
}
 
echo makeyogurt("raspberry");   // works as expected
?>
```

The above example will output:

    Making a bowl of acidophilus raspberry.

> **Note**: <span class="simpara"> Arguments that are passed by
> reference may have a default value. </span>

### Type declarations

> **Note**:
>
> Type declarations were also known as type hints in previous versions
> of PHP.

Type declarations allow functions to require that parameters are of a
certain type at call time. If the given value is of the incorrect type,
then a <span class="classname">TypeError</span> will be thrown.

To specify a type declaration, the type name should be added before the
parameter name. The declaration can be made to accept **`NULL`** values
if the default value of the parameter is set to **`NULL`**.

#### Valid types

| Type                               | Description                                                                                                                                                                                                    | Minimum PHP version |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Class/interface name               | The parameter must be an <a href="/language/operators/type.html" class="link"><em>instanceof</em></a> the given class or interface name.                                                                       |                     |
| *self*                             | The parameter must be an <a href="/language/operators/type.html" class="link"><em>instanceof</em></a> the same class as the one the method is defined on. This can only be used on class and instance methods. |                     |
| <span class="type">array</span>    | The parameter must be an <span class="type">array</span>.                                                                                                                                                      |                     |
| <span class="type">callable</span> | The parameter must be a valid <span class="type">callable</span>.                                                                                                                                              |                     |
| <span class="type">bool</span>     | The parameter must be a <span class="type">boolean</span> value.                                                                                                                                               |                     |
| <span class="type">float</span>    | The parameter must be a <span class="type">float</span>ing point number.                                                                                                                                       |                     |
| <span class="type">int</span>      | The parameter must be an <span class="type">integer</span>.                                                                                                                                                    |                     |
| <span class="type">string</span>   | The parameter must be a <span class="type">string</span>.                                                                                                                                                      |                     |
| *iterable*                         | The parameter must be either an <span class="type">array</span> or an <a href="/language/operators/type.html" class="link"><em>instanceof</em></a> <span class="classname">Traversable</span>.                 | PHP 7.1.0           |
| *object*                           | The parameter must be an <span class="type">object</span>.                                                                                                                                                     | PHP 7.2.0           |

**Warning**

Aliases for the above scalar types are not supported. Instead, they are
treated as class or interface names. For example, using *boolean* as a
parameter or return type will require an argument or return value that
is an
<a href="/language/operators/type.html" class="link"><em>instanceof</em></a>
the class or interface *boolean*, rather than of type <span
class="type">bool</span>:

``` php
<?php
 function test(boolean $param) {}
 test(true);
 ?>
```

The above example will output:

     Fatal error: Uncaught TypeError: Argument 1 passed to test() must be an instance of boolean, boolean given, called in - on line 1 and defined in -:1
     

#### Examples

**Example \#7 Basic class type declaration**

``` php
<?php
class C {}
class D extends C {}

// This doesn't extend C.
class E {}

function f(C $c) {
    echo get_class($c)."\n";
}

f(new C);
f(new D);
f(new E);
?>
```

The above example will output:

    C
    D

    Fatal error: Uncaught TypeError: Argument 1 passed to f() must be an instance of C, instance of E given, called in - on line 14 and defined in -:8
    Stack trace:
    #0 -(14): f(Object(E))
    #1 {main}
      thrown in - on line 8

**Example \#8 Basic interface type declaration**

``` php
<?php
interface I { public function f(); }
class C implements I { public function f() {} }

// This doesn't implement I.
class E {}

function f(I $i) {
    echo get_class($i)."\n";
}

f(new C);
f(new E);
?>
```

The above example will output:

    C

    Fatal error: Uncaught TypeError: Argument 1 passed to f() must implement interface I, instance of E given, called in - on line 13 and defined in -:8
    Stack trace:
    #0 -(13): f(Object(E))
    #1 {main}
      thrown in - on line 8

**Example \#9 Typed pass-by-reference Parameters**

Declared types of reference parameters are checked on function entry,
but not when the function returns, so after the function had returned,
the argument's type may have changed.

``` php
<?php
function array_baz(array &$param)
{
    $param = 1;
}
$var = [];
array_baz($var);
var_dump($var);
array_baz($var);
?>
```

The above example will output something similar to:

    int(1)

    Fatal error: Uncaught TypeError: Argument 1 passed to array_baz() must be of the type array, int given, called in %s on line %d

**Example \#10 Nullable type declaration**

``` php
<?php
class C {}

function f(C $c = null) {
    var_dump($c);
}

f(new C);
f(null);
?>
```

The above example will output:

    object(C)#1 (0) {
    }
    NULL

#### Strict typing

By default, PHP will coerce values of the wrong type into the expected
scalar type if possible. For example, a function that is given an <span
class="type">integer</span> for a parameter that expects a <span
class="type">string</span> will get a variable of type <span
class="type">string</span>.

It is possible to enable strict mode on a per-file basis. In strict
mode, only a variable of exact type of the type declaration will be
accepted, or a <span class="classname">TypeError</span> will be thrown.
The only exception to this rule is that an <span
class="type">integer</span> may be given to a function expecting a <span
class="type">float</span>. Function calls from within internal functions
will not be affected by the *strict\_types* declaration.

To enable strict mode, the
<a href="/control-structures/declare.html" class="link"><em>declare</em></a>
statement is used with the *strict\_types* declaration:

**Caution**

Enabling strict mode will also affect
<a href="/functions/returning-values.html#functions.returning-values.type-declaration" class="link">return type declarations</a>.

> **Note**:
>
> Strict typing applies to function calls made from *within* the file
> with strict typing enabled, not to the functions declared within that
> file. If a file without strict typing enabled makes a call to a
> function that was defined in a file with strict typing, the caller's
> preference (weak typing) will be respected, and the value will be
> coerced.

> **Note**:
>
> Strict typing is only defined for scalar type declarations.

**Example \#11 Strict typing**

``` php
<?php
declare(strict_types=1);

function sum(int $a, int $b) {
    return $a + $b;
}

var_dump(sum(1, 2));
var_dump(sum(1.5, 2.5));
?>
```

The above example will output:

    int(3)

    Fatal error: Uncaught TypeError: Argument 1 passed to sum() must be of the type integer, float given, called in - on line 9 and defined in -:4
    Stack trace:
    #0 -(9): sum(1.5, 2.5)
    #1 {main}
      thrown in - on line 4

**Example \#12 Weak typing**

``` php
<?php
function sum(int $a, int $b) {
    return $a + $b;
}

var_dump(sum(1, 2));

// These will be coerced to integers: note the output below!
var_dump(sum(1.5, 2.5));
?>
```

The above example will output:

    int(3)
    int(3)

**Example \#13 Catching <span class="classname">TypeError</span>**

``` php
<?php
declare(strict_types=1);

function sum(int $a, int $b) {
    return $a + $b;
}

try {
    var_dump(sum(1, 2));
    var_dump(sum(1.5, 2.5));
} catch (TypeError $e) {
    echo 'Error: '.$e->getMessage();
}
?>
```

The above example will output:

    int(3)
    Error: Argument 1 passed to sum() must be of the type integer, float given, called in - on line 10

### Variable-length argument lists

PHP has support for variable-length argument lists in user-defined
functions by using the *...* token.

> **Note**: <span class="simpara"> It is also possible to achieve
> variable-length arguments by using <span
> class="function">func\_num\_args</span>, <span
> class="function">func\_get\_arg</span>, and <span
> class="function">func\_get\_args</span> functions. This technique is
> not recommended as it was used prior to the introduction of the *...*
> token. </span>

Argument lists may include the *...* token to denote that the function
accepts a variable number of arguments. The arguments will be passed
into the given variable as an array; for example:

**Example \#14 Using *...* to access variable arguments**

``` php
<?php
function sum(...$numbers) {
    $acc = 0;
    foreach ($numbers as $n) {
        $acc += $n;
    }
    return $acc;
}

echo sum(1, 2, 3, 4);
?>
```

The above example will output:

    10

*...* can also be used when calling functions to unpack an <span
class="type">array</span> or <span class="classname">Traversable</span>
variable or literal into the argument list:

**Example \#15 Using *...* to provide arguments**

``` php
<?php
function add($a, $b) {
    return $a + $b;
}

echo add(...[1, 2])."\n";

$a = [1, 2];
echo add(...$a);
?>
```

The above example will output:

    3
    3

You may specify normal positional arguments before the *...* token. In
this case, only the trailing arguments that don't match a positional
argument will be added to the array generated by *...*.

It is also possible to add a
<a href="/language/oop5/typehinting.html" class="link">type declaration</a>
before the *...* token. If this is present, then all arguments captured
by *...* must be objects of the hinted class.

**Example \#16 Type declared variable arguments**

``` php
<?php
function total_intervals($unit, DateInterval ...$intervals) {
    $time = 0;
    foreach ($intervals as $interval) {
        $time += $interval->$unit;
    }
    return $time;
}

$a = new DateInterval('P1D');
$b = new DateInterval('P2D');
echo total_intervals('d', $a, $b).' days';

// This will fail, since null isn't a DateInterval object.
echo total_intervals('d', null);
?>
```

The above example will output:

    3 days
    Catchable fatal error: Argument 2 passed to total_intervals() must be an instance of DateInterval, null given, called in - on line 14 and defined in - on line 2

Finally, variable arguments can also be passed
<a href="/functions/arguments.html#functions.arguments.by-reference" class="link">by reference</a>
by prefixing the *...* with an ampersand (*&*).

#### Older versions of PHP

No special syntax is required to note that a function is variadic;
however access to the function's arguments must use <span
class="function">func\_num\_args</span>, <span
class="function">func\_get\_arg</span> and <span
class="function">func\_get\_args</span>.

The first example above would be implemented as follows in old versions
of PHP:

**Example \#17 Accessing variable arguments in old PHP versions**

``` php
<?php
function sum() {
    $acc = 0;
    foreach (func_get_args() as $n) {
        $acc += $n;
    }
    return $acc;
}

echo sum(1, 2, 3, 4);
?>
```

The above example will output:

    10

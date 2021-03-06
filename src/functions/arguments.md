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

As of PHP 8.0.0, the list of function arguments may include a trailing
comma, which will be ignored. That is particularly useful in cases where
the list of arguments is long or contains long variable names, making it
convenient to list arguments vertically.

**Example \#2 Function Argument List with trailing Comma**

``` php
<?php
function takes_many_args(
    $first_arg,
    $second_arg,
    $a_very_long_argument_name,
    $arg_with_default = 5,
    $again = 'a default string', // This trailing comma was not permitted before 8.0.0.
)
{
    // ...
}
?>
```

As of PHP 8.0.0, passing mandatory arguments after optional arguments is
deprecated. This can generally be resolved by dropping the default
value. One exception to this rule are arguments of the form
`Type $param = null`, where the **`null`** default makes the type
implicitly nullable. This usage remains allowed, though it is
recommended to use an explicit nullable type instead.

**Example \#3 Passing optional arguments after mandatory arguments**

``` php
<?php
function foo($a = [], $b) {} // Before
function foo($a, $b) {}      // After

function bar(A $a = null, $b) {} // Still allowed
function bar(?A $a, $b) {}       // Recommended
?>
```

### Passing arguments by reference

By default, function arguments are passed by value (so that if the value
of the argument within the function is changed, it does not get changed
outside of the function). To allow a function to modify its arguments,
they must be passed by reference.

To have an argument to a function always passed by reference, prepend an
ampersand (&) to the argument name in the function definition:

**Example \#4 Passing function parameters by reference**

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

It is an error to pass a value as argument which is supposed to be
passed by reference.

### Default argument values

A function may define C++-style default values for scalar arguments as
follows:

**Example \#5 Use of default parameters in functions**

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
special type **`null`** as default values, for example:

**Example \#6 Using non-scalar types as default values**

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

**Example \#7 Incorrect usage of default function arguments**

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

**Example \#8 Correct usage of default function arguments**

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

**Example \#9 Using *...* to access variable arguments**

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

**Example \#10 Using *...* to provide arguments**

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
<a href="/language/types/declarations.html" class="link">type declaration</a>
before the *...* token. If this is present, then all arguments captured
by *...* must be objects of the hinted class.

**Example \#11 Type declared variable arguments**

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

**Example \#12 Accessing variable arguments in old PHP versions**

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

### Named Arguments

PHP 8.0.0 introduced named arguments as an extension of the existing
positional parameters. Named arguments allow passing arguments to a
function based on the parameter name, rather than the parameter
position. This makes the meaning of the argument self-documenting, makes
the arguments order-independent and allows skipping default values
arbitrarily.

Named arguments are passed by prefixing the value with the parameter
name followed by a colon. Using reserved keywords as parameter names is
allowed. The parameter name must be an identifier, specifying
dynamically is not allowed.

**Example \#13 Named argument syntax**

``` php
<?php
myFunction(paramName: $value);
array_foobar(array: $value);

// NOT supported.
function_name($variableStoringParamName: $value);
?>
```

**Example \#14 Positional arguments versus named arguments**

``` php
<?php
// Using positional arguments:
array_fill(0, 100, 50);

// Using named arguments:
array_fill(start_index: 0, num: 100, value: 50);
?>
```

The order in which the named arguments are passed does not matter.

**Example \#15 Same example as above with a different order of
parameters**

``` php
<?php
array_fill(value: 50, num: 100, start_index: 0);
?>
```

Named arguments can be combined with positional arguments. In this case,
the named arguments must come after the positional arguments. It is also
possible to specify only some of the optional arguments of a function,
regardless of their order.

**Example \#16 Combining named arguments with positional arguments**

``` php
<?php
htmlspecialchars($string, double_encode: false);
// Same as
htmlspecialchars($string, ENT_COMPAT | ENT_HTML401, 'UTF-8', false);
?>
```

Passing the same parameter multiple times results in an Error exception.

**Example \#17 Error exception when passing the same parameter multiple
times**

``` php
<?php
function foo($param) { ... }

foo(param: 1, param: 2);
// Error: Named parameter $param overwrites previous argument
foo(1, param: 2);
// Error: Named parameter $param overwrites previous argument
?>
```

call\_user\_func\_array
=======================

Call a callback with an array of parameters

### Description

<span class="type">mixed</span> <span
class="methodname">call\_user\_func\_array</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> , <span class="methodparam"><span
class="type">array</span> `$param_arr`</span> )

Calls the `callback` given by the first parameter with the parameters in
`param_arr`.

### Parameters

`callback`  
The <span class="type">callable</span> to be called.

`param_arr`  
The parameters to be passed to the callback, as an indexed array.

### Return Values

Returns the return value of the callback, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">call\_user\_func\_array</span>
example**

``` php
<?php
function foobar($arg, $arg2) {
    echo __FUNCTION__, " got $arg and $arg2\n";
}
class foo {
    function bar($arg, $arg2) {
        echo __METHOD__, " got $arg and $arg2\n";
    }
}


// Call the foobar() function with 2 arguments
call_user_func_array("foobar", array("one", "two"));

// Call the $foo->bar() method with 2 arguments
$foo = new foo;
call_user_func_array(array($foo, "bar"), array("three", "four"));
?>
```

The above example will output something similar to:

    foobar got one and two
    foo::bar got three and four

**Example \#2 <span class="function">call\_user\_func\_array</span>
using namespace name**

``` php
<?php

namespace Foobar;

class Foo {
    static public function test($name) {
        print "Hello {$name}!\n";
    }
}

// As of PHP 5.3.0
call_user_func_array(__NAMESPACE__ .'\Foo::test', array('Hannes'));

// As of PHP 5.3.0
call_user_func_array(array(__NAMESPACE__ .'\Foo', 'test'), array('Philip'));

?>
```

The above example will output something similar to:

    Hello Hannes!
    Hello Philip!

**Example \#3 Using lambda function**

``` php
<?php

$func = function($arg1, $arg2) {
    return $arg1 * $arg2;
};

var_dump(call_user_func_array($func, array(2, 4))); /* As of PHP 5.3.0 */

?>
```

The above example will output:

    int(8)

**Example \#4 Passing values by reference**

``` php
<?php

function mega(&$a){
    $a = 55;
    echo "function mega \$a=$a\n";
}
$bar = 77;
call_user_func_array('mega',array(&$bar));
echo "global \$bar=$bar\n";

?>
```

The above example will output:

    function mega $a=55
    global $bar=55

### Notes

> **Note**:
>
> Before PHP 5.4, referenced variables in `param_arr` are passed to the
> function by reference, regardless of whether the function expects the
> respective parameter to be passed by reference. This form of call-time
> pass by reference does not emit a deprecation notice, but it is
> nonetheless deprecated, and has been removed in PHP 5.4. Furthermore,
> this does not apply to internal functions, for which the function
> signature is honored. Passing by value when the function expects a
> parameter by reference results in a warning and having <span
> class="function">call\_user\_func</span> return **`FALSE`** (there is,
> however, an exception for passed values with reference count = 1, such
> as in literals, as these can be turned into references without ill
> effects — but also without writes to that value having any effect —;
> do not rely in this behavior, though, as the reference count is an
> implementation detail and the soundness of this behavior is
> questionable).

> **Note**:
>
> Callbacks registered with functions such as <span
> class="function">call\_user\_func</span> and <span
> class="function">call\_user\_func\_array</span> will not be called if
> there is an uncaught exception thrown in a previous callback.

### See Also

-   <span class="function">call\_user\_func</span>
-   <span class="methodname">ReflectionFunction::invokeArgs</span>
-   <span class="methodname">ReflectionMethod::invokeArgs</span>

call\_user\_func
================

Call the callback given by the first parameter

### Description

<span class="type">mixed</span> <span
class="methodname">call\_user\_func</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> , <span class="methodparam"><span
class="type">mixed</span> `$args`</span> )

Calls the `callback` given by the first parameter and passes the
remaining parameters as arguments.

### Parameters

`callback`  
The <span class="type">callable</span> to be called.

`args`  
Zero or more parameters to be passed to the callback.

> **Note**:
>
> Note that the parameters for <span
> class="function">call\_user\_func</span> are not passed by reference.
>
> **Example \#1 <span class="function">call\_user\_func</span> example
> and references**
>
> ``` php
> <?php
> error_reporting(E_ALL);
> function increment(&$var)
> {
>     $var++;
> }
>
> $a = 0;
> call_user_func('increment', $a);
> echo $a."\n";
>
> // You can use this instead
> call_user_func_array('increment', array(&$a));
> echo $a."\n";
> ?>
> ```
>
> The above example will output:
>
>     Warning: Parameter 1 to increment() expected to be a reference, value given in …
>     0
>     1

### Return Values

Returns the return value of the callback.

### Examples

**Example \#2 <span class="function">call\_user\_func</span> example**

``` php
<?php
function barber($type)
{
    echo "You wanted a $type haircut, no problem\n";
}
call_user_func('barber', "mushroom");
call_user_func('barber', "shave");
?>
```

The above example will output:

    You wanted a mushroom haircut, no problem
    You wanted a shave haircut, no problem

**Example \#3 <span class="function">call\_user\_func</span> using
namespace name**

``` php
<?php

namespace Foobar;

class Foo {
    static public function test() {
        print "Hello world!\n";
    }
}

call_user_func(__NAMESPACE__ .'\Foo::test'); // As of PHP 5.3.0
call_user_func(array(__NAMESPACE__ .'\Foo', 'test')); // As of PHP 5.3.0

?>
```

The above example will output:

    Hello world!
    Hello world!

**Example \#4 Using a class method with <span
class="function">call\_user\_func</span>**

``` php
<?php

class myclass {
    static function say_hello()
    {
        echo "Hello!\n";
    }
}

$classname = "myclass";

call_user_func(array($classname, 'say_hello'));
call_user_func($classname .'::say_hello'); // As of 5.2.3

$myobject = new myclass();

call_user_func(array($myobject, 'say_hello'));

?>
```

The above example will output:

    Hello!
    Hello!
    Hello!

**Example \#5 Using lambda function with <span
class="function">call\_user\_func</span>**

``` php
<?php
call_user_func(function($arg) { print "[$arg]\n"; }, 'test'); /* As of PHP 5.3.0 */
?>
```

The above example will output:

    [test]

### Notes

> **Note**:
>
> Callbacks registered with functions such as <span
> class="function">call\_user\_func</span> and <span
> class="function">call\_user\_func\_array</span> will not be called if
> there is an uncaught exception thrown in a previous callback.

### See Also

-   <span class="function">call\_user\_func\_array</span>
-   <span class="function">is\_callable</span>
-   <span class="methodname">ReflectionFunction::invoke</span>
-   <span class="methodname">ReflectionMethod::invoke</span>

create\_function
================

Create an anonymous (lambda-style) function

**Warning**

This function has been *DEPRECATED* as of PHP 7.2.0. Relying on this
function is highly discouraged.

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">create\_function</span> ( <span
class="methodparam"><span class="type">string</span> `$args`</span> ,
<span class="methodparam"><span class="type">string</span>
`$code`</span> )

Creates an anonymous function from the parameters passed, and returns a
unique name for it.

**Caution**

This function internally performs an <span class="function">eval</span>
and as such has the same security issues as <span
class="function">eval</span>. Additionally it has bad performance and
memory usage characteristics.

If you are using PHP 5.3.0 or newer a native
<a href="/functions/anonymous.html" class="link">anonymous function</a>
should be used instead.

### Parameters

Usually these parameters will be passed as single quote delimited
strings. The reason for using single quoted strings, is to protect the
variable names from parsing, otherwise, if you use double quotes there
will be a need to escape the variable names, e.g. *\\$avar*.

`args`  
The function arguments.

`code`  
The function code.

### Return Values

Returns a unique function name as a string, or **`FALSE`** on error.

### Examples

**Example \#1 Creating an anonymous function with <span
class="function">create\_function</span>**

You can use this function, to (for example) create a function from
information gathered at run time:

``` php
<?php
$newfunc = create_function('$a,$b', 'return "ln($a) + ln($b) = " . log($a * $b);');
echo "New anonymous function: $newfunc\n";
echo $newfunc(2, M_E) . "\n";
// outputs
// New anonymous function: lambda_1
// ln(2) + ln(2.718281828459) = 1.6931471805599
?>
```

Or, perhaps to have general handler function that can apply a set of
operations to a list of parameters:

**Example \#2 Making a general processing function with <span
class="function">create\_function</span>**

``` php
<?php
function process($var1, $var2, $farr)
{
    foreach ($farr as $f) {
        echo $f($var1, $var2) . "\n";
    }
}

// create a bunch of math functions
$f1 = 'if ($a >=0) {return "b*a^2 = ".$b*sqrt($a);} else {return false;}';
$f2 = "return \"min(b^2+a, a^2,b) = \".min(\$a*\$a+\$b,\$b*\$b+\$a);";
$f3 = 'if ($a > 0 && $b != 0) {return "ln(a)/b = ".log($a)/$b; } else { return false; }';
$farr = array(
    create_function('$x,$y', 'return "some trig: ".(sin($x) + $x*cos($y));'),
    create_function('$x,$y', 'return "a hypotenuse: ".sqrt($x*$x + $y*$y);'),
    create_function('$a,$b', $f1),
    create_function('$a,$b', $f2),
    create_function('$a,$b', $f3)
    );

echo "\nUsing the first array of anonymous functions\n";
echo "parameters: 2.3445, M_PI\n";
process(2.3445, M_PI, $farr);

// now make a bunch of string processing functions
$garr = array(
    create_function('$b,$a', 'if (strncmp($a, $b, 3) == 0) return "** \"$a\" '.
    'and \"$b\"\n** Look the same to me! (looking at the first 3 chars)";'),
    create_function('$a,$b', '; return "CRCs: " . crc32($a) . ", ".crc32($b);'),
    create_function('$a,$b', '; return "similar(a,b) = " . similar_text($a, $b, &$p) . "($p%)";')
    );
echo "\nUsing the second array of anonymous functions\n";
process("Twas brilling and the slithy toves", "Twas the night", $garr);
?>
```

The above example will output:

    Using the first array of anonymous functions
    parameters: 2.3445, M_PI
    some trig: -1.6291725057799
    a hypotenuse: 3.9199852871011
    b*a^2 = 4.8103313314525
    min(b^2+a, a^2,b) = 8.6382729035898
    ln(a)/b = 0.27122299212594

    Using the second array of anonymous functions
    ** "Twas the night" and "Twas brilling and the slithy toves"
    ** Look the same to me! (looking at the first 3 chars)
    CRCs: -725381282, 342550513
    similar(a,b) = 11(45.833333333333%)

But perhaps the most common use for of lambda-style (anonymous)
functions is to create callback functions, for example when using <span
class="function">array\_walk</span> or <span
class="function">usort</span>

**Example \#3 Using anonymous functions as callback functions**

``` php
<?php
$av = array("the ", "a ", "that ", "this ");
array_walk($av, create_function('&$v,$k', '$v = $v . "mango";'));
print_r($av);
?>
```

The above example will output:

    Array
    (
      [0] => the mango
      [1] => a mango
      [2] => that mango
      [3] => this mango
    )

an array of strings ordered from shorter to longer

``` php
<?php

$sv = array("small", "larger", "a big string", "it is a string thing");
print_r($sv);

?>
```

The above example will output:

    Array
    (
      [0] => small
      [1] => larger
      [2] => a big string
      [3] => it is a string thing
    )

sort it from longer to shorter

``` php
<?php

usort($sv, create_function('$a,$b','return strlen($b) - strlen($a);'));
print_r($sv);

?>
```

The above example will output:

    Array
    (
      [0] => it is a string thing
      [1] => a big string
      [2] => larger
      [3] => small
    )

### See Also

-   <a href="/functions/anonymous.html" class="link">Anonymous functions</a>

forward\_static\_call\_array
============================

Call a static method and pass the arguments as array

### Description

<span class="type">mixed</span> <span
class="methodname">forward\_static\_call\_array</span> ( <span
class="methodparam"><span class="type">callable</span>
`$function`</span> , <span class="methodparam"><span
class="type">array</span> `$parameters`</span> )

Calls a user defined function or method given by the `function`
parameter. This function must be called within a method context, it
can't be used outside a class. It uses the
<a href="/language/oop5/late-static-bindings.html" class="link">late static binding</a>.
All arguments of the forwarded method are passed as values, and as an
array, similarly to <span
class="function">call\_user\_func\_array</span>.

### Parameters

`function`  
The function or method to be called. This parameter may be an <span
class="type">array</span>, with the name of the class, and the method,
or a <span class="type">string</span>, with a function name.

`parameter`  
One parameter, gathering all the method parameter in one array.

> **Note**:
>
> Note that the parameters for <span
> class="function">forward\_static\_call\_array</span> are not passed by
> reference.

### Return Values

Returns the function result, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">forward\_static\_call\_array</span>
example**

``` php
<?php

class A
{
    const NAME = 'A';
    public static function test() {
        $args = func_get_args();
        echo static::NAME, " ".join(',', $args)." \n";
    }
}

class B extends A
{
    const NAME = 'B';

    public static function test() {
        echo self::NAME, "\n";
        forward_static_call_array(array('A', 'test'), array('more', 'args'));
        forward_static_call_array( 'test', array('other', 'args'));
    }
}

B::test('foo');

function test() {
        $args = func_get_args();
        echo "C ".join(',', $args)." \n";
    }

?>
```

The above example will output:

    B
    B more,args 
    C other,args

### See Also

-   <span class="function">forward\_static\_call</span>
-   <span class="function">call\_user\_func</span>
-   <span class="function">call\_user\_func\_array</span>
-   <span class="function">is\_callable</span>

forward\_static\_call
=====================

Call a static method

### Description

<span class="type">mixed</span> <span
class="methodname">forward\_static\_call</span> ( <span
class="methodparam"><span class="type">callable</span>
`$function`</span> , <span class="methodparam"><span
class="type">mixed</span> `$args`</span> )

Calls a user defined function or method given by the `function`
parameter, with the following arguments. This function must be called
within a method context, it can't be used outside a class. It uses the
<a href="/language/oop5/late-static-bindings.html" class="link">late static binding</a>.

### Parameters

`function`  
The function or method to be called. This parameter may be an array,
with the name of the class, and the method, or a string, with a function
name.

`args`  
Zero or more parameters to be passed to the function.

### Return Values

Returns the function result, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">forward\_static\_call</span>
example**

``` php
<?php

class A
{
    const NAME = 'A';
    public static function test() {
        $args = func_get_args();
        echo static::NAME, " ".join(',', $args)." \n";
    }
}

class B extends A
{
    const NAME = 'B';

    public static function test() {
        echo self::NAME, "\n";
        forward_static_call(array('A', 'test'), 'more', 'args');
        forward_static_call( 'test', 'other', 'args');
    }
}

B::test('foo');

function test() {
        $args = func_get_args();
        echo "C ".join(',', $args)." \n";
    }

?>
```

The above example will output:

    B
    B more,args 
    C other,args

### See Also

-   <span class="function">forward\_static\_call\_array</span>
-   <span class="function">call\_user\_func\_array</span>
-   <span class="function">call\_user\_func</span>
-   <span class="function">is\_callable</span>

func\_get\_arg
==============

Return an item from the argument list

### Description

<span class="type">mixed</span> <span
class="methodname">func\_get\_arg</span> ( <span
class="methodparam"><span class="type">int</span> `$arg_num`</span> )

Gets the specified argument from a user-defined function's argument
list.

This function may be used in conjunction with <span
class="function">func\_get\_args</span> and <span
class="function">func\_num\_args</span> to allow user-defined functions
to accept variable-length argument lists.

### Parameters

`arg_num`  
The argument offset. Function arguments are counted starting from zero.

### Return Values

Returns the specified argument, or **`FALSE`** on error.

### Errors/Exceptions

Generates a warning if called from outside of a user-defined function,
or if `arg_num` is greater than the number of arguments actually passed.

### Examples

**Example \#1 <span class="function">func\_get\_arg</span> example**

``` php
<?php
function foo()
{
     $numargs = func_num_args();
     echo "Number of arguments: $numargs\n";
     if ($numargs >= 2) {
         echo "Second argument is: " . func_get_arg(1) . "\n";
     }
}

foo(1, 2, 3);
?>
```

The above example will output:

    Number of arguments: 3
    Second argument is: 2

**Example \#2 <span class="function">func\_get\_arg</span> example
before and after PHP 5.3**

``` php
test.php
<?php
function foo() {
    include './fga.inc';
}

foo('First arg', 'Second arg');
?>

fga.inc
<?php

$arg = func_get_arg(1);
var_export($arg);

?>
```

Output previous to PHP 5.3:

    'Second arg'

Output in PHP 5.3 and later:

    Warning: func_get_arg():  Called from the global scope - no function
    context in /home/torben/Desktop/code/ml/fga.inc on line 3
    false

**Example \#3 <span class="function">func\_get\_arg</span> example of
byref and byval arguments**

``` php
<?php
function byVal($arg) {
    echo 'As passed     : ', var_export(func_get_arg(0)), PHP_EOL;
    $arg = 'baz';
    echo 'After change  : ', var_export(func_get_arg(0)), PHP_EOL;
}

function byRef(&$arg) {
    echo 'As passed     : ', var_export(func_get_arg(0)), PHP_EOL;
    $arg = 'baz';
    echo 'After change  : ', var_export(func_get_arg(0)), PHP_EOL;
}

$arg = 'bar';
byVal($arg);
byRef($arg);
?>
```

Output of the above example in PHP 7:

  
As passed : 'bar'  
After change : 'baz'  
As passed : 'bar'  
After change : 'baz'  

Output of the above example in PHP 5:

  
As passed : 'bar'  
After change : 'bar'  
As passed : 'bar'  
After change : 'baz'  

### Notes

> **Note**:
>
> Because this function depends on the current scope to determine
> parameter details, it cannot be used as a function parameter in
> versions prior to 5.3.0. If this value must be passed, the results
> should be assigned to a variable, and that variable should be passed.

> **Note**:
>
> If the arguments are passed by reference, any changes to the arguments
> will be reflected in the values returned by this function. As of PHP 7
> the current values will also be returned if the arguments are passed
> by value.

> **Note**: <span class="simpara"> This function returns a copy of the
> passed arguments only, and does not account for default (non-passed)
> arguments. </span>

### See Also

-   <a href="/functions/arguments.html#functions.variable-arg-list" class="link"><em>...</em> syntax in PHP 5.6+</a>
-   <span class="function">func\_get\_args</span>
-   <span class="function">func\_num\_args</span>

func\_get\_args
===============

Returns an array comprising a function's argument list

### Description

<span class="type">array</span> <span
class="methodname">func\_get\_args</span> ( <span
class="methodparam">void</span> )

Gets an array of the function's argument list.

This function may be used in conjunction with <span
class="function">func\_get\_arg</span> and <span
class="function">func\_num\_args</span> to allow user-defined functions
to accept variable-length argument lists.

### Return Values

Returns an array in which each element is a copy of the corresponding
member of the current user-defined function's argument list.

### Errors/Exceptions

Generates a warning if called from outside of a user-defined function.

### Examples

**Example \#1 <span class="function">func\_get\_args</span> example**

``` php
<?php
function foo()
{
    $numargs = func_num_args();
    echo "Number of arguments: $numargs \n";
    if ($numargs >= 2) {
        echo "Second argument is: " . func_get_arg(1) . "\n";
    }
    $arg_list = func_get_args();
    for ($i = 0; $i < $numargs; $i++) {
        echo "Argument $i is: " . $arg_list[$i] . "\n";
    }
}

foo(1, 2, 3);
?>
```

The above example will output:

    Number of arguments: 3 
    Second argument is: 2
    Argument 0 is: 1
    Argument 1 is: 2
    Argument 2 is: 3

**Example \#2 <span class="function">func\_get\_args</span> example
before and after PHP 5.3**

``` php
test.php
<?php
function foo() {
    include './fga.inc';
}

foo('First arg', 'Second arg');
?>

fga.inc
<?php

$args = func_get_args();
var_export($args);

?>
```

Output previous to PHP 5.3:

    array (
      0 => 'First arg',
      1 => 'Second arg',
    )

Output in PHP 5.3 and later:

    Warning: func_get_args():  Called from the global scope - no function
    context in /home/torben/Desktop/code/ml/fga.inc on line 3
    false

**Example \#3 <span class="function">func\_get\_args</span> example of
byref and byval arguments**

``` php
<?php
function byVal($arg) {
    echo 'As passed     : ', var_export(func_get_args()), PHP_EOL;
    $arg = 'baz';
    echo 'After change  : ', var_export(func_get_args()), PHP_EOL;
}

function byRef(&$arg) {
    echo 'As passed     : ', var_export(func_get_args()), PHP_EOL;
    $arg = 'baz';
    echo 'After change  : ', var_export(func_get_args()), PHP_EOL;
}

$arg = 'bar';
byVal($arg);
byRef($arg);
?>
```

Output of the above example in PHP 7:

  
As passed : array (  
0 =\> 'bar',  
)  
After change : array (  
0 =\> 'baz',  
)  
As passed : array (  
0 =\> 'bar',  
)  
After change : array (  
0 =\> 'baz',  
)  

Output of the above example in PHP 5:

  
As passed : array (  
0 =\> 'bar',  
)  
After change : array (  
0 =\> 'bar',  
)  
As passed : array (  
0 =\> 'bar',  
)  
After change : array (  
0 =\> 'baz',  
)  

### Notes

> **Note**:
>
> Because this function depends on the current scope to determine
> parameter details, it cannot be used as a function parameter in
> versions prior to 5.3.0. If this value must be passed, the results
> should be assigned to a variable, and that variable should be passed.

> **Note**:
>
> If the arguments are passed by reference, any changes to the arguments
> will be reflected in the values returned by this function. As of PHP 7
> the current values will also be returned if the arguments are passed
> by value.

> **Note**: <span class="simpara"> This function returns a copy of the
> passed arguments only, and does not account for default (non-passed)
> arguments. </span>

### See Also

-   <a href="/functions/arguments.html#functions.variable-arg-list" class="link"><em>...</em> syntax in PHP 5.6+</a>
-   <span class="function">func\_get\_arg</span>
-   <span class="function">func\_num\_args</span>
-   <span
    class="methodname">ReflectionFunctionAbstract::getParameters</span>

func\_num\_args
===============

Returns the number of arguments passed to the function

### Description

<span class="type">int</span> <span
class="methodname">func\_num\_args</span> ( <span
class="methodparam">void</span> )

Gets the number of arguments passed to the function.

This function may be used in conjunction with <span
class="function">func\_get\_arg</span> and <span
class="function">func\_get\_args</span> to allow user-defined functions
to accept variable-length argument lists.

### Return Values

Returns the number of arguments passed into the current user-defined
function.

### Errors/Exceptions

Generates a warning if called from outside of a user-defined function.

### Examples

**Example \#1 <span class="function">func\_num\_args</span> example**

``` php
<?php
function foo()
{
    $numargs = func_num_args();
    echo "Number of arguments: $numargs\n";
}

foo(1, 2, 3);   
?>
```

The above example will output:

    Number of arguments: 3

**Example \#2 <span class="function">func\_num\_args</span> example
before and after PHP 5.3**

``` php
test.php
<?php
function foo() {
    include './fna.php';
}

foo('First arg', 'Second arg');
?>

fna.php
<?php

$num_args = func_num_args();
var_export($num_args);

?>
```

Output previous to PHP 5.3:

    2

Output in PHP 5.3 and later will be something similar to:

    Warning: func_num_args():  Called from the global scope - no function
    context in /home/torben/Desktop/code/ml/fna.php on line 3
    -1

### Notes

> **Note**:
>
> Because this function depends on the current scope to determine
> parameter details, it cannot be used as a function parameter in
> versions prior to 5.3.0. If this value must be passed, the results
> should be assigned to a variable, and that variable should be passed.

### See Also

-   <a href="/functions/arguments.html#functions.variable-arg-list" class="link"><em>...</em> syntax in PHP 5.6+</a>
-   <span class="function">func\_get\_arg</span>
-   <span class="function">func\_get\_args</span>
-   <span
    class="methodname">ReflectionFunctionAbstract::getNumberOfParameters</span>

function\_exists
================

Return **`TRUE`** if the given function has been defined

### Description

<span class="type">bool</span> <span
class="methodname">function\_exists</span> ( <span
class="methodparam"><span class="type">string</span>
`$function_name`</span> )

Checks the list of defined functions, both built-in (internal) and
user-defined, for `function_name`.

### Parameters

`function_name`  
The function name, as a string.

### Return Values

Returns **`TRUE`** if `function_name` exists and is a function,
**`FALSE`** otherwise.

> **Note**:
>
> This function will return **`FALSE`** for constructs, such as <span
> class="function">include\_once</span> and <span
> class="function">echo</span>.

### Examples

**Example \#1 <span class="function">function\_exists</span> example**

``` php
<?php
if (function_exists('imap_open')) {
    echo "IMAP functions are available.<br />\n";
} else {
    echo "IMAP functions are not available.<br />\n";
}
?>
```

### Notes

> **Note**:
>
> A function name may exist even if the function itself is unusable due
> to configuration or compiling options (with the
> <a href="/ref/image.html" class="link">image</a> functions being an
> example).

### See Also

-   <span class="function">method\_exists</span>
-   <span class="function">is\_callable</span>
-   <span class="function">get\_defined\_functions</span>
-   <span class="function">class\_exists</span>
-   <span class="function">extension\_loaded</span>

get\_defined\_functions
=======================

Returns an array of all defined functions

### Description

<span class="type">array</span> <span
class="methodname">get\_defined\_functions</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$exclude_disabled`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Gets an array of all defined functions.

### Parameters

`exclude_disabled`  
Whether disabled functions should be excluded from the return value.

### Return Values

Returns a multidimensional array containing a list of all defined
functions, both built-in (internal) and user-defined. The internal
functions will be accessible via `$arr["internal"]`, and the user
defined ones using `$arr["user"]` (see example below).

### Changelog

| Version       | Description                                      |
|---------------|--------------------------------------------------|
| 7.0.15, 7.1.1 | The `exclude_disabled` parameter has been added. |

### Examples

**Example \#1 <span class="function">get\_defined\_functions</span>
example**

``` php
<?php
function myrow($id, $data)
{
    return "<tr><th>$id</th><td>$data</td></tr>\n";
}

$arr = get_defined_functions();

print_r($arr);
?>
```

The above example will output something similar to:

    Array
    (
        [internal] => Array
            (
                [0] => zend_version
                [1] => func_num_args
                [2] => func_get_arg
                [3] => func_get_args
                [4] => strlen
                [5] => strcmp
                [6] => strncmp
                ...
                [750] => bcscale
                [751] => bccomp
            )

        [user] => Array
            (
                [0] => myrow
            )

    )

### See Also

-   <span class="function">function\_exists</span>
-   <span class="function">get\_defined\_vars</span>
-   <span class="function">get\_defined\_constants</span>
-   <span class="function">get\_declared\_classes</span>

register\_shutdown\_function
============================

Register a function for execution on shutdown

### Description

<span class="type">void</span> <span
class="methodname">register\_shutdown\_function</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> , <span class="methodparam"><span
class="type">mixed</span> `$args`</span> )

Registers a `callback` to be executed after script execution finishes or
<span class="function">exit</span> is called.

Multiple calls to <span
class="function">register\_shutdown\_function</span> can be made, and
each will be called in the same order as they were registered. If you
call <span class="function">exit</span> within one registered shutdown
function, processing will stop completely and no other registered
shutdown functions will be called.

### Parameters

`callback`  
The shutdown callback to register.

The shutdown callbacks are executed as the part of the request, so it's
possible to send output from them and access output buffers.

`args`  
It is possible to pass parameters to the shutdown function by passing
additional parameters.

### Return Values

No value is returned.

### Errors/Exceptions

If the passed callback is not callable a **`E_WARNING`** level error
will be generated.

### Examples

**Example \#1 <span class="function">register\_shutdown\_function</span>
example**

``` php
<?php
function shutdown()
{
    // This is our shutdown function, in 
    // here we can do any last operations
    // before the script is complete.

    echo 'Script executed with success', PHP_EOL;
}

register_shutdown_function('shutdown');
?>
```

### Notes

> **Note**:
>
> Working directory of the script can change inside the shutdown
> function under some web servers, e.g. Apache.

> **Note**:
>
> Shutdown functions will not be executed if the process is killed with
> a SIGTERM or SIGKILL signal. While you cannot intercept a SIGKILL, you
> can use <span class="function">pcntl\_signal</span> to install a
> handler for a SIGTERM which uses <span class="function">exit</span> to
> end cleanly.

### See Also

-   <a href="/ini/core.html#ini.auto-append-file" class="link">auto_append_file</a>
-   <span class="function">exit</span>
-   The section on
    <a href="/features/connection-handling.html" class="link">connection handling</a>

register\_tick\_function
========================

Register a function for execution on each tick

### Description

<span class="type">bool</span> <span
class="methodname">register\_tick\_function</span> ( <span
class="methodparam"><span class="type">callable</span>
`$function`</span> , <span class="methodparam"><span
class="type">mixed</span> `$args`</span> )

Registers the given `function` to be executed when a
<a href="/control-structures/declare.html#control-structures.declare.ticks" class="link">tick</a>
is called.

### Parameters

`function`  
The function to register.

`args`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">register\_tick\_function</span>
example**

``` php
<?php
declare(ticks=1);

// using a function as the callback
register_tick_function('my_function', true);

// using an object->method
$object = new my_class();
register_tick_function(array(&$object, 'my_method'), true);
?>
```

### Notes

**Warning**

<span class="function">register\_tick\_function</span> should not be
used with threaded web server modules with PHP 5.2 or lower.

### See Also

-   <a href="/control-structures/declare.html" class="link">declare</a>
-   <span class="function">unregister\_tick\_function</span>

unregister\_tick\_function
==========================

De-register a function for execution on each tick

### Description

<span class="type">void</span> <span
class="methodname">unregister\_tick\_function</span> ( <span
class="methodparam"><span class="type">callable</span>
`$function`</span> )

De-registers the function `function` so it is no longer executed when a
<a href="/control-structures/declare.html" class="link">tick</a> is
called.

### Parameters

`function`  
The function to de-register.

### Return Values

No value is returned.

### See Also

-   <span class="function">register\_tick\_function</span>

**Table of Contents**

-   [call\_user\_func\_array](/ref/funchand.html#call_user_func_array) —
    Call a callback with an array of parameters
-   [call\_user\_func](/ref/funchand.html#call_user_func) — Call the
    callback given by the first parameter
-   [create\_function](/ref/funchand.html#create_function) — Create an
    anonymous (lambda-style) function
-   [forward\_static\_call\_array](/ref/funchand.html#forward_static_call_array)
    — Call a static method and pass the arguments as array
-   [forward\_static\_call](/ref/funchand.html#forward_static_call) —
    Call a static method
-   [func\_get\_arg](/ref/funchand.html#func_get_arg) — Return an item
    from the argument list
-   [func\_get\_args](/ref/funchand.html#func_get_args) — Returns an
    array comprising a function's argument list
-   [func\_num\_args](/ref/funchand.html#func_num_args) — Returns the
    number of arguments passed to the function
-   [function\_exists](/ref/funchand.html#function_exists) — Return TRUE
    if the given function has been defined
-   [get\_defined\_functions](/ref/funchand.html#get_defined_functions)
    — Returns an array of all defined functions
-   [register\_shutdown\_function](/ref/funchand.html#register_shutdown_function)
    — Register a function for execution on shutdown
-   [register\_tick\_function](/ref/funchand.html#register_tick_function)
    — Register a function for execution on each tick
-   [unregister\_tick\_function](/ref/funchand.html#unregister_tick_function)
    — De-register a function for execution on each tick

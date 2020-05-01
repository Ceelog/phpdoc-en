Anonymous functions
-------------------

Anonymous functions, also known as *closures*, allow the creation of
functions which have no specified name. They are most useful as the
value of
<a href="/language/pseudo-types.html#language.types.callback" class="link">callback</a>
parameters, but they have many other uses.

Anonymous functions are implemented using the
<a href="/class/closure.html" class="link"><span class="classname">Closure</span></a>
class.

**Example \#1 Anonymous function example**

``` php
<?php
echo preg_replace_callback('~-([a-z])~', function ($match) {
    return strtoupper($match[1]);
}, 'hello-world');
// outputs helloWorld
?>
```

Closures can also be used as the values of variables; PHP automatically
converts such expressions into instances of the <span
class="classname">Closure</span> internal class. Assigning a closure to
a variable uses the same syntax as any other assignment, including the
trailing semicolon:

**Example \#2 Anonymous function variable assignment example**

``` php
<?php
$greet = function($name)
{
    printf("Hello %s\r\n", $name);
};

$greet('World');
$greet('PHP');
?>
```

Closures may also inherit variables from the parent scope. Any such
variables must be passed to the *use* language construct. From PHP 7.1,
these variables must not include
<a href="/language/variables/predefined.html" class="link">superglobals</a>,
`$this`, or variables with the same name as a parameter.

**Example \#3 Inheriting variables from the parent scope**

``` php
<?php
$message = 'hello';

// No "use"
$example = function () {
    var_dump($message);
};
$example();

// Inherit $message
$example = function () use ($message) {
    var_dump($message);
};
$example();

// Inherited variable's value is from when the function
// is defined, not when called
$message = 'world';
$example();

// Reset message
$message = 'hello';

// Inherit by-reference
$example = function () use (&$message) {
    var_dump($message);
};
$example();

// The changed value in the parent scope
// is reflected inside the function call
$message = 'world';
$example();

// Closures can also accept regular arguments
$example = function ($arg) use ($message) {
    var_dump($arg . ' ' . $message);
};
$example("hello");
?>
```

The above example will output something similar to:

    Notice: Undefined variable: message in /example.php on line 6
    NULL
    string(5) "hello"
    string(5) "hello"
    string(5) "hello"
    string(5) "world"
    string(11) "hello world"

Inheriting variables from the parent scope is *not* the same as using
global variables. Global variables exist in the global scope, which is
the same no matter what function is executing. The parent scope of a
closure is the function in which the closure was declared (not
necessarily the function it was called from). See the following example:

**Example \#4 Closures and scoping**

``` php
<?php
// A basic shopping cart which contains a list of added products
// and the quantity of each product. Includes a method which
// calculates the total price of the items in the cart using a
// closure as a callback.
class Cart
{
    const PRICE_BUTTER  = 1.00;
    const PRICE_MILK    = 3.00;
    const PRICE_EGGS    = 6.95;

    protected $products = array();
    
    public function add($product, $quantity)
    {
        $this->products[$product] = $quantity;
    }
    
    public function getQuantity($product)
    {
        return isset($this->products[$product]) ? $this->products[$product] :
               FALSE;
    }
    
    public function getTotal($tax)
    {
        $total = 0.00;
        
        $callback =
            function ($quantity, $product) use ($tax, &$total)
            {
                $pricePerItem = constant(__CLASS__ . "::PRICE_" .
                    strtoupper($product));
                $total += ($pricePerItem * $quantity) * ($tax + 1.0);
            };
        
        array_walk($this->products, $callback);
        return round($total, 2);
    }
}

$my_cart = new Cart;

// Add some items to the cart
$my_cart->add('butter', 1);
$my_cart->add('milk', 3);
$my_cart->add('eggs', 6);

// Print the total with a 5% sales tax.
print $my_cart->getTotal(0.05) . "\n";
// The result is 54.29
?>
```

**Example \#5 Automatic binding of *$this***

``` php
<?php

class Test
{
    public function testing()
    {
        return function() {
            var_dump($this);
        };
    }
}

$object = new Test;
$function = $object->testing();
$function();
    
?>
```

The above example will output:

    object(Test)#1 (0) {
    }

Output of the above example in PHP 5.3:

    Notice: Undefined variable: this in script.php on line 8
    NULL

As of PHP 5.4.0, when declared in the context of a class, the current
class is automatically bound to it, making *$this* available inside of
the function's scope. If this automatic binding of the current class is
not wanted, then
<a href="/functions/anonymous.html#functions.anonymous-functions.static" class="link">static anonymous functions</a>
may be used instead.

### Static anonymous functions

As of PHP 5.4, anonymous functions may be declared statically. This
prevents them from having the current class automatically bound to them.
Objects may also not be bound to them at runtime.

**Example \#6 Attempting to use *$this* inside a static anonymous
function**

``` php
<?php

class Foo
{
    function __construct()
    {
        $func = static function() {
            var_dump($this);
        };
        $func();
    }
};
new Foo();

?>
```

The above example will output:

    Notice: Undefined variable: this in %s on line %d
    NULL

**Example \#7 Attempting to bind an object to a static anonymous
function**

``` php
<?php

$func = static function() {
    // function body
};
$func = $func->bindTo(new StdClass);
$func();

?>
```

The above example will output:

    Warning: Cannot bind an instance to a static closure in %s on line %d

### Changelog

| Version | Description                                                                                                                                                                     |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | Anonymous functions may not close over <a href="/language/variables/predefined.html" class="link">superglobals</a>, `$this`, or any variable with the same name as a parameter. |
| 5.4.0   | Anonymous functions may use `$this`, as well as be declared statically.                                                                                                         |
| 5.3.0   | Anonymous functions become available.                                                                                                                                           |

### Notes

> **Note**: <span class="simpara"> It is possible to use <span
> class="function">func\_num\_args</span>, <span
> class="function">func\_get\_arg</span>, and <span
> class="function">func\_get\_args</span> from within a closure. </span>

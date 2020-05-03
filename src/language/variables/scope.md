Variable scope
--------------

The scope of a variable is the context within which it is defined. For
the most part all PHP variables only have a single scope. This single
scope spans included and required files as well. For example:

``` php
<?php
$a = 1;
include 'b.inc';
?>
```

Here the `$a` variable will be available within the included `b.inc`
script. However, within user-defined functions a local function scope is
introduced. Any variable used inside a function is by default limited to
the local function scope. For example:

``` php
<?php
$a = 1; /* global scope */ 

function test()
{ 
    echo $a; /* reference to local scope variable */ 
} 

test();
?>
```

This script will not produce any output because the echo statement
refers to a local version of the `$a` variable, and it has not been
assigned a value within this scope. You may notice that this is a little
bit different from the C language in that global variables in C are
automatically available to functions unless specifically overridden by a
local definition. This can cause some problems in that people may
inadvertently change a global variable. In PHP global variables must be
declared global inside a function if they are going to be used in that
function.

### The *global* keyword

First, an example use of *global*:

**Example \#1 Using *global***

``` php
<?php
$a = 1;
$b = 2;

function Sum()
{
    global $a, $b;

    $b = $a + $b;
} 

Sum();
echo $b;
?>
```

The above script will output *3*. By declaring `$a` and `$b` global
within the function, all references to either variable will refer to the
global version. There is no limit to the number of global variables that
can be manipulated by a function.

A second way to access variables from the global scope is to use the
special PHP-defined `$GLOBALS` array. The previous example can be
rewritten as:

**Example \#2 Using `$GLOBALS` instead of global**

``` php
<?php
$a = 1;
$b = 2;

function Sum()
{
    $GLOBALS['b'] = $GLOBALS['a'] + $GLOBALS['b'];
} 

Sum();
echo $b;
?>
```

The `$GLOBALS` array is an associative array with the name of the global
variable being the key and the contents of that variable being the value
of the array element. Notice how `$GLOBALS` exists in any scope, this is
because `$GLOBALS` is a
<a href="/language/variables/superglobals.html" class="link">superglobal</a>.
Here's an example demonstrating the power of superglobals:

**Example \#3 Example demonstrating superglobals and scope**

``` php
<?php
function test_superglobal()
{
    echo $_POST['name'];
}
?>
```

> **Note**:
>
> Using *global* keyword outside a function is not an error. It can be
> used if the file is included from inside a function.

### Using *static* variables

Another important feature of variable scoping is the *static* variable.
A static variable exists only in a local function scope, but it does not
lose its value when program execution leaves this scope. Consider the
following example:

**Example \#4 Example demonstrating need for static variables**

``` php
<?php
function test()
{
    $a = 0;
    echo $a;
    $a++;
}
?>
```

This function is quite useless since every time it is called it sets
`$a` to *0* and prints *0*. The `$a`++ which increments the variable
serves no purpose since as soon as the function exits the `$a` variable
disappears. To make a useful counting function which will not lose track
of the current count, the `$a` variable is declared static:

**Example \#5 Example use of static variables**

``` php
<?php
function test()
{
    static $a = 0;
    echo $a;
    $a++;
}
?>
```

Now, `$a` is initialized only in first call of function and every time
the *test()* function is called it will print the value of `$a` and
increment it.

Static variables also provide one way to deal with recursive functions.
A recursive function is one which calls itself. Care must be taken when
writing a recursive function because it is possible to make it recurse
indefinitely. You must make sure you have an adequate way of terminating
the recursion. The following simple function recursively counts to 10,
using the static variable `$count` to know when to stop:

**Example \#6 Static variables with recursive functions**

``` php
<?php
function test()
{
    static $count = 0;

    $count++;
    echo $count;
    if ($count < 10) {
        test();
    }
    $count--;
}
?>
```

> **Note**:
>
> Static variables may be declared as seen in the examples above. From
> PHP 5.6 you can assign values to these variables which are the result
> of expressions, but you can't use any function here, what will cause a
> parse error.
>
> **Example \#7 Declaring static variables**
>
> ``` php
> <?php
> function foo(){
>     static $int = 0;          // correct 
>     static $int = 1+2;        // correct (as of PHP 5.6)
>     static $int = sqrt(121);  // wrong  (as it is a function)
>
>     $int++;
>     echo $int;
> }
> ?>
> ```

> **Note**:
>
> Static declarations are resolved in compile-time.

### References with *global* and *static* variables

PHP implements the
<a href="/language/variables/scope.html#language.variables.scope.static" class="link">static</a>
and
<a href="/language/variables/scope.html#language.variables.scope.global" class="link">global</a>
modifier for variables in terms of
<a href="/language/references.html" class="link">references</a>. For
example, a true global variable imported inside a function scope with
the *global* statement actually creates a reference to the global
variable. This can lead to unexpected behaviour which the following
example addresses:

``` php
<?php
function test_global_ref() {
    global $obj;
    $new = new stdclass;
    $obj = &$new;
}

function test_global_noref() {
    global $obj;
    $new = new stdclass;
    $obj = $new;
}

test_global_ref();
var_dump($obj);
test_global_noref();
var_dump($obj);
?>
```

The above example will output:

    NULL
    object(stdClass)#1 (0) {
    }

A similar behaviour applies to the *static* statement. References are
not stored statically:

``` php
<?php
function &get_instance_ref() {
    static $obj;

    echo 'Static object: ';
    var_dump($obj);
    if (!isset($obj)) {
        $new = new stdclass;
        // Assign a reference to the static variable
        $obj = &$new;
    }
    if (!isset($obj->property)) {
        $obj->property = 1;
    } else {
        $obj->property++;
    }
    return $obj;
}

function &get_instance_noref() {
    static $obj;

    echo 'Static object: ';
    var_dump($obj);
    if (!isset($obj)) {
        $new = new stdclass;
        // Assign the object to the static variable
        $obj = $new;
    }
    if (!isset($obj->property)) {
        $obj->property = 1;
    } else {
        $obj->property++;
    }
    return $obj;
}

$obj1 = get_instance_ref();
$still_obj1 = get_instance_ref();
echo "\n";
$obj2 = get_instance_noref();
$still_obj2 = get_instance_noref();
?>
```

The above example will output:

    Static object: NULL
    Static object: NULL

    Static object: NULL
    Static object: object(stdClass)#3 (1) {
      ["property"]=>
      int(1)
    }

This example demonstrates that when assigning a reference to a static
variable, it's not *remembered* when you call the
*&get\_instance\_ref()* function a second time.

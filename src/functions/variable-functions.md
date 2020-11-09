Variable functions
------------------

PHP supports the concept of variable functions. This means that if a
variable name has parentheses appended to it, PHP will look for a
function with the same name as whatever the variable evaluates to, and
will attempt to execute it. Among other things, this can be used to
implement callbacks, function tables, and so forth.

Variable functions won't work with language constructs such as <span
class="function">echo</span>, <span class="function">print</span>, <span
class="function">unset</span>, <span class="function">isset</span>,
<span class="function">empty</span>, <span
class="function">include</span>, <span class="function">require</span>
and the like. Utilize wrapper functions to make use of any of these
constructs as variable functions.

**Example \#1 Variable function example**

``` php
<?php
function foo() {
    echo "In foo()<br />\n";
}

function bar($arg = '')
{
    echo "In bar(); argument was '$arg'.<br />\n";
}

// This is a wrapper function around echo
function echoit($string)
{
    echo $string;
}

$func = 'foo';
$func();        // This calls foo()

$func = 'bar';
$func('test');  // This calls bar()

$func = 'echoit';
$func('test');  // This calls echoit()
?>
```

Object methods can also be called with the variable functions syntax.

**Example \#2 Variable method example**

``` php
<?php
class Foo
{
    function Variable()
    {
        $name = 'Bar';
        $this->$name(); // This calls the Bar() method
    }
    
    function Bar()
    {
        echo "This is Bar";
    }
}

$foo = new Foo();
$funcname = "Variable";
$foo->$funcname();  // This calls $foo->Variable()

?>
```

When calling static methods, the function call is stronger than the
static property operator:

**Example \#3 Variable method example with static properties**

``` php
<?php
class Foo
{
    static $variable = 'static property';
    static function Variable()
    {
        echo 'Method Variable called';
    }
}

echo Foo::$variable; // This prints 'static property'. It does need a $variable in this scope.
$variable = "Variable";
Foo::$variable();  // This calls $foo->Variable() reading $variable in this scope.

?>
```

**Example \#4 Complex callables**

``` php
<?php
class Foo
{
    static function bar()
    {
        echo "bar\n";
    }
    function baz()
    {
        echo "baz\n";
    }
}

$func = array("Foo", "bar");
$func(); // prints "bar"
$func = array(new Foo, "baz");
$func(); // prints "baz"
$func = "Foo::bar";
$func(); // prints "bar"
?>
```

### See Also

-   <span class="function">is\_callable</span>
-   <span class="function">call\_user\_func</span>
-   <span class="function">function\_exists</span>
-   <a href="/language/variables/variable.html" class="link">variable variables</a>

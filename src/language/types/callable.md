Callbacks / Callables
---------------------

Callbacks can be denoted by <span class="type">callable</span> type
hint.

Some functions like <span class="function">call\_user\_func</span> or
<span class="function">usort</span> accept user-defined callback
functions as a parameter. Callback functions can not only be simple
functions, but also <span class="type">object</span> methods, including
static class methods.

### Passing

A PHP function is passed by its name as a <span
class="type">string</span>. Any built-in or user-defined function can be
used, except language constructs such as: <span
class="function">array</span>, <span class="function">echo</span>, <span
class="function">empty</span>, <span class="function">eval</span>, <span
class="function">exit</span>, <span class="function">isset</span>, <span
class="function">list</span>, <span class="function">print</span> or
<span class="function">unset</span>.

A method of an instantiated <span class="type">object</span> is passed
as an <span class="type">array</span> containing an <span
class="type">object</span> at index 0 and the method name at index 1.
Accessing protected and private methods from within a class is allowed.

Static class methods can also be passed without instantiating an <span
class="type">object</span> of that class by either, passing the class
name instead of an <span class="type">object</span> at index 0, or
passing *'ClassName::methodName'*.

Apart from common user-defined function,
<a href="/functions/anonymous.html" class="link">anonymous functions</a>
and <a href="/functions/arrow.html" class="link">arrow functions</a> can
also be passed to a callback parameter.

Generally, any object implementing
<a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>
can also be passed to a callback parameter.

**Example \#1 Callback function examples**

``` php
<?php

// An example callback function
function my_callback_function() {
    echo 'hello world!';
}

// An example callback method
class MyClass {
    static function myCallbackMethod() {
        echo 'Hello World!';
    }
}

// Type 1: Simple callback
call_user_func('my_callback_function');

// Type 2: Static class method call
call_user_func(array('MyClass', 'myCallbackMethod'));

// Type 3: Object method call
$obj = new MyClass();
call_user_func(array($obj, 'myCallbackMethod'));

// Type 4: Static class method call
call_user_func('MyClass::myCallbackMethod');

// Type 5: Relative static class method call
class A {
    public static function who() {
        echo "A\n";
    }
}

class B extends A {
    public static function who() {
        echo "B\n";
    }
}

call_user_func(array('B', 'parent::who')); // A

// Type 6: Objects implementing __invoke can be used as callables
class C {
    public function __invoke($name) {
        echo 'Hello ', $name, "\n";
    }
}

$c = new C();
call_user_func($c, 'PHP!');
?>
```

**Example \#2 Callback example using a Closure**

``` php
<?php
// Our closure
$double = function($a) {
    return $a * 2;
};

// This is our range of numbers
$numbers = range(1, 5);

// Use the closure as a callback here to
// double the size of each element in our
// range
$new_numbers = array_map($double, $numbers);

print implode(' ', $new_numbers);
?>
```

The above example will output:

    2 4 6 8 10

> **Note**:
>
> Callbacks registered with functions such as <span
> class="function">call\_user\_func</span> and <span
> class="function">call\_user\_func\_array</span> will not be called if
> there is an uncaught exception thrown in a previous callback.

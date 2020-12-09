Closure::bind
=============

Duplicates a closure with a specific bound object and class scope

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">Closure</span><span class="type">false</span></span> <span
class="methodname">Closure::bind</span> ( <span
class="methodparam"><span class="type">Closure</span> `$closure`</span>
, <span class="methodparam"><span class="type">object</span>
`$newthis`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$newscope` <span class="initializer"> =
"static"</span></span> \] )

This method is a static version of <span
class="methodname">Closure::bindTo</span>. See the documentation of that
method for more information.

### Parameters

`closure`  
The anonymous functions to bind.

`newthis`  
The object to which the given anonymous function should be bound, or
**`null`** for the closure to be unbound.

`newscope`  
The class scope to which the closure is to be associated, or 'static' to
keep the current one. If an object is given, the type of the object will
be used instead. This determines the visibility of protected and private
methods of the bound object. It is not allowed to pass (an object of) an
internal class as this parameter.

### Return Values

Returns a new <span class="classname">Closure</span> object or
**`false`** on failure

### Examples

**Example \#1 <span class="function">Closure::bind</span> example**

``` php
<?php
class A {
    private static $sfoo = 1;
    private $ifoo = 2;
}
$cl1 = static function() {
    return A::$sfoo;
};
$cl2 = function() {
    return $this->ifoo;
};

$bcl1 = Closure::bind($cl1, null, 'A');
$bcl2 = Closure::bind($cl2, new A(), 'A');
echo $bcl1(), "\n";
echo $bcl2(), "\n";
?>
```

The above example will output something similar to:

    1
    2

### See Also

-   <a href="/functions/anonymous.html" class="link">Anonymous functions</a>
-   <span class="methodname">Closure::bindTo</span>

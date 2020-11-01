Closure::bindTo
===============

Duplicates the closure with a new bound object and class scope

### Description

<span class="modifier">public</span> <span class="type">Closure</span>
<span class="methodname">Closure::bindTo</span> ( <span
class="methodparam"><span class="type">object</span> `$newthis`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$newscope` <span class="initializer"> = "static"</span></span> \] )

Create and return a new
<a href="/functions/anonymous.html" class="link">anonymous function</a>
with the same body and bound variables as this one, but possibly with a
different bound object and a new class scope.

The “bound object” determines the value *$this* will have in the
function body and the “class scope” represents a class which determines
which private and protected members the anonymous function will be able
to access. Namely, the members that will be visible are the same as if
the anonymous function were a method of the class given as value of the
`newscope` parameter.

Static closures cannot have any bound object (the value of the parameter
`newthis` should be **`NULL`**), but this function can nevertheless be
used to change their class scope.

This function will ensure that for a non-static closure, having a bound
instance will imply being scoped and vice-versa. To this end, non-static
closures that are given a scope but a **`NULL`** instance are made
static and non-static non-scoped closures that are given a non-null
instance are scoped to an unspecified class.

> **Note**:
>
> If you only want to duplicate the anonymous functions, you can use
> <a href="/language/oop5/cloning.html" class="link">cloning</a>
> instead.

### Parameters

`newthis`  
The object to which the given anonymous function should be bound, or
**`NULL`** for the closure to be unbound.

`newscope`  
The class scope to which the closure is to be associated, or 'static' to
keep the current one. If an object is given, the type of the object will
be used instead. This determines the visibility of protected and private
methods of the bound object. It is not allowed to pass (an object of) an
internal class as this parameter.

### Return Values

Returns the newly created <span class="classname">Closure</span> object
or **`FALSE`** on failure

### Examples

**Example \#1 <span class="function">Closure::bindTo</span> example**

``` php
<?php

class A {
    function __construct($val) {
        $this->val = $val;
    }
    function getClosure() {
        //returns closure bound to this object and scope
        return function() { return $this->val; };
    }
}

$ob1 = new A(1);
$ob2 = new A(2);

$cl = $ob1->getClosure();
echo $cl(), "\n";
$cl = $cl->bindTo($ob2);
echo $cl(), "\n";
?>
```

The above example will output something similar to:

    1
    2

### See Also

-   <a href="/functions/anonymous.html" class="link">Anonymous functions</a>
-   <span class="methodname">Closure::bind</span>

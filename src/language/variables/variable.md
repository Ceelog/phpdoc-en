Variable variables
------------------

Sometimes it is convenient to be able to have variable variable names.
That is, a variable name which can be set and used dynamically. A normal
variable is set with a statement such as:

``` php
<?php
$a = 'hello';
?>
```

A variable variable takes the value of a variable and treats that as the
name of a variable. In the above example, *hello*, can be used as the
name of a variable by using two dollar signs. i.e.

``` php
<?php
$$a = 'world';
?>
```

At this point two variables have been defined and stored in the PHP
symbol tree: `$a` with contents "hello" and `$hello` with contents
"world". Therefore, this statement:

``` php
<?php
echo "$a ${$a}";
?>
```

produces the exact same output as:

``` php
<?php
echo "$a $hello";
?>
```

i.e. they both produce: <span class="computeroutput">hello world</span>.

In order to use variable variables with arrays, you have to resolve an
ambiguity problem. That is, if you write `$$a[1]` then the parser needs
to know if you meant to use `$a[1]` as a variable, or if you wanted
`$$a` as the variable and then the \[1\] index from that variable. The
syntax for resolving this ambiguity is: `${$a[1]}` for the first case
and `${$a}[1]` for the second.

Class properties may also be accessed using variable property names. The
variable property name will be resolved within the scope from which the
call is made. For instance, if you have an expression such as
`$foo->$bar`, then the local scope will be examined for `$bar` and its
value will be used as the name of the property of `$foo`. This is also
true if `$bar` is an array access.

Curly braces may also be used, to clearly delimit the property name.
They are most useful when accessing values within a property that
contains an array, when the property name is made of multiple parts, or
when the property name contains characters that are not otherwise valid
(e.g. from <span class="function">json\_decode</span> or
<a href="/book/simplexml.html" class="link">SimpleXML</a>).

**Example \#1 Variable property example**

``` php
<?php
class foo {
    var $bar = 'I am bar.';
    var $arr = array('I am A.', 'I am B.', 'I am C.');
    var $r   = 'I am r.';
}

$foo = new foo();
$bar = 'bar';
$baz = array('foo', 'bar', 'baz', 'quux');
echo $foo->$bar . "\n";
echo $foo->{$baz[1]} . "\n";

$start = 'b';
$end   = 'ar';
echo $foo->{$start . $end} . "\n";

$arr = 'arr';
echo $foo->{$arr[1]} . "\n";

?>
```

The above example will output:

  
I am bar.  
I am bar.  
I am bar.  
I am r.  

**Warning**

Please note that variable variables cannot be used with PHP's
<a href="/language/variables/superglobals.html" class="link">Superglobal arrays</a>
within functions or class methods. The variable *$this* is also a
special variable that cannot be referenced dynamically.

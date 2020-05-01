Class Constants
---------------

It is possible to define constant values on a per-class basis remaining
the same and unchangeable. Constants differ from normal variables in
that you don't use the `$` symbol to declare or use them. The default
visibility of class constants is *public*.

The value must be a constant expression, not (for example) a variable, a
property, or a function call.

It's also possible for interfaces to have *constants*. Look at the
<a href="/language/oop5/interfaces.html" class="link">interface documentation</a>
for examples.

As of PHP 5.3.0, it's possible to reference the class using a variable.
The variable's value can not be a keyword (e.g. *self*, *parent* and
*static*).

Note that class constants are allocated once per class, and not for each
class instance.

**Example \#1 Defining and using a constant**

``` php
<?php
class MyClass
{
    const CONSTANT = 'constant value';

    function showConstant() {
        echo  self::CONSTANT . "\n";
    }
}

echo MyClass::CONSTANT . "\n";

$classname = "MyClass";
echo $classname::CONSTANT . "\n"; // As of PHP 5.3.0

$class = new MyClass();
$class->showConstant();

echo $class::CONSTANT."\n"; // As of PHP 5.3.0
?>
```

**Example \#2 Static data example**

``` php
<?php
class foo {
    // As of PHP 5.3.0
    const BAR = <<<'EOT'
bar
EOT;
    // As of PHP 5.3.0
    const BAZ = <<<EOT
baz
EOT;
}
?>
```

> **Note**:
>
> Support for initializing constants with Heredoc and Nowdoc syntax was
> added in PHP 5.3.0.

The special **`::class`** constant is available as of PHP 5.5.0, and
allows for fully qualified class name resolution at compile time, this
is useful for namespaced classes:

**Example \#3 Namespaced ::class example**

``` php
<?php
namespace foo {
    class bar {
    }

    echo bar::class; // foo\bar
}
?>
```

**Example \#4 Constant expression example**

``` php
<?php
const ONE = 1;

class foo {
    // As of PHP 5.6.0
    const TWO = ONE * 2;
    const THREE = ONE + self::TWO;
    const SENTENCE = 'The value of THREE is '.self::THREE;
}
?>
```

It is possible to provide a scalar expression involving numeric and
string literals and/or constants in context of a class constant.

> **Note**:
>
> Constant expression support was added in PHP 5.6.0.

**Example \#5 Class constant visibility modifiers**

``` php
<?php
class Foo {
    // As of PHP 7.1.0
    public const BAR = 'bar';
    private const BAZ = 'baz';
}
echo Foo::BAR, PHP_EOL;
echo Foo::BAZ, PHP_EOL;
?>
```

Output of the above example in PHP 7.1:

    bar

    Fatal error: Uncaught Error: Cannot access private const Foo::BAZ in …

> **Note**:
>
> As of PHP 7.1.0 visibility modifiers are allowed for class constants.

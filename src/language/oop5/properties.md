Properties
----------

Class member variables are called *properties*. You may also see them
referred to using other terms such as *attributes* or *fields*, but for
the purposes of this reference we will use *properties*. They are
defined by using one of the keywords *public*, *protected*, or
*private*, optionally followed by a type declaration, followed by a
normal variable declaration. This declaration may include an
initialization, but this initialization must be a constant value--that
is, it must be able to be evaluated at compile time and must not depend
on run-time information in order to be evaluated.

See <a href="/language/oop5/visibility.html" class="xref">Visibility</a>
for more information on the meanings of *public*, *protected*, and
*private*.

> **Note**:
>
> In order to maintain backward compatibility with PHP 4, PHP 5 will
> still accept the use of the keyword *var* in property declarations
> instead of (or in addition to) *public*, *protected*, or *private*.
> However, *var* is no longer required. In versions of PHP from 5.0 to
> 5.1.3, the use of *var* was considered deprecated and would issue an
> **`E_STRICT`** warning, but since PHP 5.1.3 it is no longer deprecated
> and does not issue the warning.
>
> If you declare a property using *var* instead of one of *public*,
> *protected*, or *private*, then PHP 5 will treat the property as if it
> had been declared as *public*.

Within class methods non-static properties may be accessed by using
*-\>* (Object Operator): `$this->property` (where *property* is the name
of the property). Static properties are accessed by using the *::*
(Double Colon): `self::$property`. See
<a href="/language/oop5/static.html" class="link">Static Keyword</a> for
more information on the difference between static and non-static
properties.

The pseudo-variable `$this` is available inside any class method when
that method is called from within an object context. `$this` is a
reference to the calling object (usually the object to which the method
belongs, but possibly another object, if the method is called
<a href="/language/oop5/static.html" class="link">statically</a> from
the context of a secondary object).

**Example \#1 property declarations**

``` php
<?php
class SimpleClass
{
   // valid as of PHP 5.6.0:
   public $var1 = 'hello ' . 'world';
   // valid as of PHP 5.3.0:
   public $var2 = <<<EOD
hello world
EOD;
   // valid as of PHP 5.6.0:
   public $var3 = 1+2;
   // invalid property declarations:
   public $var4 = self::myStaticMethod();
   public $var5 = $myVar;

   // valid property declarations:
   public $var6 = myConstant;
   public $var7 = array(true, false);

   // valid as of PHP 5.3.0:
   public $var8 = <<<'EOD'
hello world
EOD;
}
?>
```

> **Note**:
>
> There are some nice functions to handle classes and objects. You might
> want to take a look at the
> <a href="/ref/classobj.html" class="link">Class/Object Functions</a>.

### Heredoc and Nowdoc

As of PHP 5.3.0
<a href="/language/types/string.html#language.types.string.syntax.heredoc" class="link">heredocs</a>
and
<a href="/language/types/string.html#language.types.string.syntax.nowdoc" class="link">nowdocs</a>
can be used in any static data context, including property declarations.

**Example \#2 Example of using a nowdoc to initialize a property**

``` php
<?php
class foo {
   // As of PHP 5.3.0
   public $bar = <<<'EOT'
bar
EOT;
   public $baz = <<<EOT
baz
EOT;
}
?>
```

> **Note**:
>
> Nowdoc and Heredoc support was added in PHP 5.3.0.

### Type declarations

As of PHP 7.4.0, property definitions can include a type declaration.

**Example \#3 Example of typed properties**

``` php
<?php

class User
{
    public int $id;
    public ?string $name;

    public function __construct(int $id, ?string $name)
    {
        $this->id = $id;
        $this->name = $name;
    }
}

$user = new User(1234, null);

var_dump($user->id);
var_dump($user->name);

?>
```

The above example will output:

    int(1234)
    NULL

Typed properties must be initialized before accessing, otherwise an
<span class="classname">Error</span> is thrown.

**Example \#4 Accessing properties**

``` php
<?php

class Shape
{
    public int $numberOfSides;
    public string $name;

    public function setNumberOfSides(int $numberOfSides): void
    {
        $this->numberOfSides = $numberOfSides;
    }

    public function setName(string $name): void
    {
        $this->name = $name;
    }

    public function getNumberOfSides(): int
    {
        return $this->numberOfSides;
    }

    public function getName(): string
    {
        return $this->name;
    }
}

$triangle = new Shape();
$triangle->setName("triangle");
$triangle->setNumberofSides(3);
var_dump($triangle->getName());
var_dump($triangle->getNumberOfSides());

$circle = new Shape();
$circle->setName("circle");
var_dump($circle->getName());
var_dump($circle->getNumberOfSides());
?>
```

The above example will output:

    string(8) "triangle"
    int(3)
    string(6) "circle"

    Fatal error: Uncaught Error: Typed property Shape::$numberOfSides must not be accessed before initialization

#### Valid property types

| Type                             | Description                                                                                                                                                                                       | Minimum PHP version |
|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| <span class="type">bool</span>   | The property must be <span class="type">boolean</span> value.                                                                                                                                     | PHP 7.4.0           |
| <span class="type">int</span>    | The property must be an <span class="type">integer</span>.                                                                                                                                        | PHP 7.4.0           |
| <span class="type">float</span>  | The property must be a <span class="type">float</span>ing point number.                                                                                                                           | PHP 7.4.0           |
| <span class="type">string</span> | The property must be a <span class="type">string</span>.                                                                                                                                          | PHP 7.4.0           |
| <span class="type">array</span>  | The property must be an <span class="type">array</span>.                                                                                                                                          | PHP 7.4.0           |
| *object*                         | The property must be an <span class="type">object</span>.                                                                                                                                         | PHP 7.4.0           |
| *iterable*                       | The property must be either an <span class="type">array</span> or an <a href="/language/operators/type.html" class="link"><em>instanceof</em></a> <span class="interfacename">Traversable</span>. | PHP 7.4.0           |
| *self*                           | The property must be an <a href="/language/operators/type.html" class="link"><em>instanceof</em></a> the same class in which the property is defined.                                             | PHP 7.4.0           |
| *parent*                         | The property must be an <a href="/language/operators/type.html" class="link"><em>instanceof</em></a> the parent class of the class in which the property is defined.                              | PHP 7.4.0           |
| Class/interface name             | The property must be an <a href="/language/operators/type.html" class="link"><em>instanceof</em></a> the given class or interface name.                                                           | PHP 7.4.0           |
| ?type                            | The property must be the specified type, or **`NULL`**.                                                                                                                                           | PHP 7.4.0           |

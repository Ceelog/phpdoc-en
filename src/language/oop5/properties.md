Properties
----------

Class member variables are called "properties". You may also see them
referred to using other terms such as "attributes" or "fields", but for
the purposes of this reference we will use "properties". They are
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

As of PHP 7.4.0, property definitions can include a type declaration,
with the exception of the *callable* type.

**Example \#3 Example of typed properties**

``` php
<?php

class User
{
    public int $id;
    public string $name;

    public function __construct(int $id, string $name)
    {
        $this->id = $id;
        $this->name = $name;
    }
}

$user = new User(1234, "php");
echo "ID: " . $user->id;
echo "\n";
echo "Name: " . $user->name;

?>
```

The above example will output:

    ID: 1234
    Name: php

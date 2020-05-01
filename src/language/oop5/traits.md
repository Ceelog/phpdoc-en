Traits
------

As of PHP 5.4.0, PHP implements a method of code reuse called Traits.

Traits are a mechanism for code reuse in single inheritance languages
such as PHP. A Trait is intended to reduce some limitations of single
inheritance by enabling a developer to reuse sets of methods freely in
several independent classes living in different class hierarchies. The
semantics of the combination of Traits and classes is defined in a way
which reduces complexity, and avoids the typical problems associated
with multiple inheritance and Mixins.

A Trait is similar to a class, but only intended to group functionality
in a fine-grained and consistent way. It is not possible to instantiate
a Trait on its own. It is an addition to traditional inheritance and
enables horizontal composition of behavior; that is, the application of
class members without requiring inheritance.

**Example \#1 Trait example**

``` php
<?php
trait ezcReflectionReturnInfo {
    function getReturnType() { /*1*/ }
    function getReturnDescription() { /*2*/ }
}

class ezcReflectionMethod extends ReflectionMethod {
    use ezcReflectionReturnInfo;
    /* ... */
}

class ezcReflectionFunction extends ReflectionFunction {
    use ezcReflectionReturnInfo;
    /* ... */
}
?>
```

### Precedence

An inherited member from a base class is overridden by a member inserted
by a Trait. The precedence order is that members from the current class
override Trait methods, which in turn override inherited methods.

**Example \#2 Precedence Order Example**

An inherited method from a base class is overridden by the method
inserted into MyHelloWorld from the SayWorld Trait. The behavior is the
same for methods defined in the MyHelloWorld class. The precedence order
is that methods from the current class override Trait methods, which in
turn override methods from the base class.

``` php
<?php
class Base {
    public function sayHello() {
        echo 'Hello ';
    }
}

trait SayWorld {
    public function sayHello() {
        parent::sayHello();
        echo 'World!';
    }
}

class MyHelloWorld extends Base {
    use SayWorld;
}

$o = new MyHelloWorld();
$o->sayHello();
?>
```

The above example will output:

    Hello World!

**Example \#3 Alternate Precedence Order Example**

``` php
<?php
trait HelloWorld {
    public function sayHello() {
        echo 'Hello World!';
    }
}

class TheWorldIsNotEnough {
    use HelloWorld;
    public function sayHello() {
        echo 'Hello Universe!';
    }
}

$o = new TheWorldIsNotEnough();
$o->sayHello();
?>
```

The above example will output:

    Hello Universe!

### Multiple Traits

Multiple Traits can be inserted into a class by listing them in the use
statement, separated by commas.

**Example \#4 Multiple Traits Usage**

``` php
<?php
trait Hello {
    public function sayHello() {
        echo 'Hello ';
    }
}

trait World {
    public function sayWorld() {
        echo 'World';
    }
}

class MyHelloWorld {
    use Hello, World;
    public function sayExclamationMark() {
        echo '!';
    }
}

$o = new MyHelloWorld();
$o->sayHello();
$o->sayWorld();
$o->sayExclamationMark();
?>
```

The above example will output:

    Hello World!

### Conflict Resolution

If two Traits insert a method with the same name, a fatal error is
produced, if the conflict is not explicitly resolved.

To resolve naming conflicts between Traits used in the same class, the
*insteadof* operator needs to be used to choose exactly one of the
conflicting methods.

Since this only allows one to exclude methods, the *as* operator can be
used to add an alias to one of the methods. Note the *as* operator does
not rename the method and it does not affect any other method either.

**Example \#5 Conflict Resolution**

In this example, Talker uses the traits A and B. Since A and B have
conflicting methods, it defines to use the variant of smallTalk from
trait B, and the variant of bigTalk from trait A.

The Aliased\_Talker makes use of the *as* operator to be able to use B's
bigTalk implementation under an additional alias *talk*.

``` php
<?php
trait A {
    public function smallTalk() {
        echo 'a';
    }
    public function bigTalk() {
        echo 'A';
    }
}

trait B {
    public function smallTalk() {
        echo 'b';
    }
    public function bigTalk() {
        echo 'B';
    }
}

class Talker {
    use A, B {
        B::smallTalk insteadof A;
        A::bigTalk insteadof B;
    }
}

class Aliased_Talker {
    use A, B {
        B::smallTalk insteadof A;
        A::bigTalk insteadof B;
        B::bigTalk as talk;
    }
}
?>
```

> **Note**:
>
> Prior to PHP 7.0, defining a property in a class with the same name as
> in a trait would throw an **`E_STRICT`** if the class definition was
> compatible (same visibility and initial value).

### Changing Method Visibility

Using the *as* syntax, one can also adjust the visibility of the method
in the exhibiting class.

**Example \#6 Changing Method Visibility**

``` php
<?php
trait HelloWorld {
    public function sayHello() {
        echo 'Hello World!';
    }
}

// Change visibility of sayHello
class MyClass1 {
    use HelloWorld { sayHello as protected; }
}

// Alias method with changed visibility
// sayHello visibility not changed
class MyClass2 {
    use HelloWorld { sayHello as private myPrivateHello; }
}
?>
```

### Traits Composed from Traits

Just as classes can make use of traits, so can other traits. By using
one or more traits in a trait definition, it can be composed partially
or entirely of the members defined in those other traits.

**Example \#7 Traits Composed from Traits**

``` php
<?php
trait Hello {
    public function sayHello() {
        echo 'Hello ';
    }
}

trait World {
    public function sayWorld() {
        echo 'World!';
    }
}

trait HelloWorld {
    use Hello, World;
}

class MyHelloWorld {
    use HelloWorld;
}

$o = new MyHelloWorld();
$o->sayHello();
$o->sayWorld();
?>
```

The above example will output:

    Hello World!

### Abstract Trait Members

Traits support the use of abstract methods in order to impose
requirements upon the exhibiting class.

**Caution**

A concrete class fulfills this requirement by defining a concrete method
with the same name; its signature may be different.

**Example \#8 Express Requirements by Abstract Methods**

``` php
<?php
trait Hello {
    public function sayHelloWorld() {
        echo 'Hello'.$this->getWorld();
    }
    abstract public function getWorld();
}

class MyHelloWorld {
    private $world;
    use Hello;
    public function getWorld() {
        return $this->world;
    }
    public function setWorld($val) {
        $this->world = $val;
    }
}
?>
```

### Static Trait Members

Traits can define both static members and static methods.

**Example \#9 Static Variables**

``` php
<?php
trait Counter {
    public function inc() {
        static $c = 0;
        $c = $c + 1;
        echo "$c\n";
    }
}

class C1 {
    use Counter;
}

class C2 {
    use Counter;
}

$o = new C1(); $o->inc(); // echo 1
$p = new C2(); $p->inc(); // echo 1
?>
```

**Example \#10 Static Methods**

``` php
<?php
trait StaticExample {
    public static function doSomething() {
        return 'Doing something';
    }
}

class Example {
    use StaticExample;
}

Example::doSomething();
?>
```

### Properties

Traits can also define properties.

**Example \#11 Defining Properties**

``` php
<?php
trait PropertiesTrait {
    public $x = 1;
}

class PropertiesExample {
    use PropertiesTrait;
}

$example = new PropertiesExample;
$example->x;
?>
```

If a trait defines a property then a class can not define a property
with the same name unless it is compatible (same visibility and initial
value), otherwise a fatal error is issued. Before PHP 7.0.0, defining a
property in the class with the same visibility and initial value as in
the trait, raised an E\_STRICT notice.

**Example \#12 Conflict Resolution**

``` php
<?php
trait PropertiesTrait {
    public $same = true;
    public $different = false;
}

class PropertiesExample {
    use PropertiesTrait;
    public $same = true; // Allowed as of PHP 7.0.0; E_STRICT notice formerly
    public $different = true; // Fatal error
}
?>
```

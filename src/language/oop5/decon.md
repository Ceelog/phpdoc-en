Constructors and Destructors
----------------------------

### Constructor

<span class="type">void</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$values`<span
class="initializer"> = ""</span></span> )

PHP allows developers to declare constructor methods for classes.
Classes which have a constructor method call this method on each
newly-created object, so it is suitable for any initialization that the
object may need before it is used.

> **Note**: <span class="simpara"> Parent constructors are not called
> implicitly if the child class defines a constructor. In order to run a
> parent constructor, a call to <span
> class="function">parent::\_\_construct</span> within the child
> constructor is required. If the child does not define a constructor
> then it may be inherited from the parent class just like a normal
> class method (if it was not declared as private). </span>

**Example \#1 Constructors in inheritance**

``` php
<?php
class BaseClass {
    function __construct() {
        print "In BaseClass constructor\n";
    }
}

class SubClass extends BaseClass {
    function __construct() {
        parent::__construct();
        print "In SubClass constructor\n";
    }
}

class OtherSubClass extends BaseClass {
    // inherits BaseClass's constructor
}

// In BaseClass constructor
$obj = new BaseClass();

// In BaseClass constructor
// In SubClass constructor
$obj = new SubClass();

// In BaseClass constructor
$obj = new OtherSubClass();
?>
```

Unlike with other methods, PHP will not generate an **`E_STRICT`** level
error message when
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
is overridden with different parameters than the parent
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
method has.

Constructors are ordinary methods which are called during the
instantiation of their corresponding object. As such, they may define an
arbitrary number of arguments, which may be required, may have a type,
and may have a default value. Constructor arguments are called by
placing the arguments in parentheses after the class name.

**Example \#2 Using constructor arguments**

``` php
<?php
class Point {
    protected int $x;
    protected int $y;

    public function __construct(int $x, int $y = 0) {
        $this->x = $x;
        $this->y = $y;
    }
}

// Pass both parameters.
$p1 = new Point(4, 5);
// Pass only the required parameter. $y will take its default value of 0.
$p2 = new Point(4);
// With named parameters (as of PHP 8.0):
$p3 = new Point(y: 5, x: 4);
?>
```

If a class has no constructor, or the constructor has no required
arguments, the parentheses may be omitted.

#### Old-style constructors

Prior to PHP 8.0.0, classes in the global namespace will interpret a
method named the same as the class as an old-style constructor. That
syntax is deprecated, and will result in an **`E_DEPRECATED`** error but
still call that function as a constructor. If both
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
and a same-name method are defined,
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
will be called.

In namespaced classes, or any class as of PHP 8.0.0, a method named the
same as the class never has any special meaning.

Always use
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
in new code.

#### Constructor Promotion

As of PHP 8.0.0, constructor parameters may also be promoted to
correspond to an object property. It is very common for constructor
parameters to be assigned to a property in the constructor but otherwise
not operated upon. Constructor promotion provides a short-hand for that
use case. The example above could be rewritten as the following.

**Example \#3 Using constructor property promotion**

``` php
<?php
class Point {
    public function __construct(protected int $x, protected int $y = 0) {
    }
}
```

When a constructor argument includes a visibility modifier, PHP will
interpret it as both an object property and a constructor argument, and
assign the argument value to the property. The constructor body may then
be empty or may contain other statements. Any additional statements will
be executed after the argument values have been assigned to the
corresponding properties.

Not all arguments need to be promoted. It is possible to mix and match
promoted and not-promoted arguments, in any order. Promoted arguments
have no impact on code calling the constructor.

> **Note**:
>
> Object properties may not be typed <span class="type">callable</span>
> due to engine ambiguity that would introduce. Promoted arguments,
> therefore, may not be typed <span class="type">callable</span> either.
> Any other
> <a href="/language/types/declarations.html" class="link">type declaration</a>
> is permitted, however.

> **Note**:
>
> Attributes placed on a promoted constructor argument will be
> replicated to both the property and argument.

#### Static creation methods

PHP only supports a single constructor per class. In some cases,
however, it may be desirable to allow an object to be constructed in
different ways with different inputs. The recommended way to do so is by
using static methods as constructor wrappers.

**Example \#4 Using static creation methods**

``` php
<?php
class Product {

    private ?int $id;
    private ?string $name;

    private function __construct(?int $id = null, ?string $name = null) {
        $this->id = $id;
        $this->name = $name;
    }

    public static function fromBasicData(int $id, string $name): static {
        $new = new static($id, $name);
        return $new;
    }

    public static function fromJson(string $json): static {
        $data = json_decode($json);
        return new static($data['id'], $data['name']);
    }

    public static function fromXml(string $xml): static {
        // Put your own logic here.
        $data = convert_xml_to_array($xml);
        $new = new static();
        $new->id = $data['id'];
        $new->name = $data['name'];
        return $new;
    }
}

$p1 = Product::fromBasicData(5, 'Widget');
$p2 = Product::fromJson($some_json_string);
$p3 = Product::fromXml($some_xml_string);
```

The constructor may be made private or protected to prevent it from
being called externally. If so, only a static method will be able to
instantiate the class. Because they are in the same class definition
they have access to private methods, even if not of the same object
instance. The private constructor is optional and may or may not make
sense depending on the use case.

The three public static methods then demonstrate different ways of
instantiating the object.

-   `fromBasicData()` takes the exact parameters that are needed, then
    creates the object by calling the constructor and returning the
    result.
-   `fromJson()` accepts a JSON string and does some pre-processing on
    it itself to convert it into the format desired by the constructor.
    It then returns the new object.
-   `fromXml()` accepts an XML string, preprocesses it, and then creates
    a bare object. The constructor is still called, but as all of the
    parameters are optional the method skips them. It then assigns
    values to the object properties directly before returning the
    result.

In all three cases, the `static` keyword is translated into the name of
the class the code is in. In this case, `Product`.

### Destructor

<span class="type">void</span> <span
class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

PHP 5 introduces a destructor concept similar to that of other
object-oriented languages, such as C++. The destructor method will be
called as soon as there are no other references to a particular object,
or in any order during the shutdown sequence.

**Example \#5 Destructor Example**

``` php
<?php

class MyDestructableClass 
{
    function __construct() {
        print "In constructor\n";
    }

    function __destruct() {
        print "Destroying " . __CLASS__ . "\n";
    }
}

$obj = new MyDestructableClass();
```

Like constructors, parent destructors will not be called implicitly by
the engine. In order to run a parent destructor, one would have to
explicitly call <span class="function">parent::\_\_destruct</span> in
the destructor body. Also like constructors, a child class may inherit
the parent's destructor if it does not implement one itself.

The destructor will be called even if script execution is stopped using
<span class="function">exit</span>. Calling <span
class="function">exit</span> in a destructor will prevent the remaining
shutdown routines from executing.

> **Note**:
>
> Destructors called during the script shutdown have HTTP headers
> already sent. The working directory in the script shutdown phase can
> be different with some SAPIs (e.g. Apache).

> **Note**:
>
> Attempting to throw an exception from a destructor (called in the time
> of script termination) causes a fatal error.

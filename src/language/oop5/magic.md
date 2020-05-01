Magic Methods
-------------

The function names
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>,
<a href="/language/oop5/decon.html#object.destruct" class="link">__destruct()</a>,
<a href="/language/oop5/overloading.html#object.call" class="link">__call()</a>,
<a href="/language/oop5/overloading.html#object.callstatic" class="link">__callStatic()</a>,
<a href="/language/oop5/overloading.html#object.get" class="link">__get()</a>,
<a href="/language/oop5/overloading.html#object.set" class="link">__set()</a>,
<a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a>,
<a href="/language/oop5/overloading.html#object.unset" class="link">__unset()</a>,
<a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>,
<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>,
<a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>,
<a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>,
<a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>,
<a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>,
<a href="/language/oop5/magic.html#object.set-state" class="link">__set_state()</a>,
<a href="/language/oop5/cloning.html#object.clone" class="link">__clone()</a>
and
<a href="/language/oop5/magic.html#object.debuginfo" class="link">__debugInfo()</a>
are magical in PHP classes. You cannot have functions with these names
in any of your classes unless you want the magic functionality
associated with them.

> **Note**: <span class="simpara"> All magic methods *MUST* be declared
> as *public* </span>

**Caution**

PHP reserves all function names starting with \_\_ as magical. It is
recommended that you do not use function names with \_\_ in PHP unless
you want some documented magic functionality.

### <a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a> and <a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">\_\_sleep</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_wakeup</span> ( <span
class="methodparam">void</span> )

<span class="function">serialize</span> checks if the class has a
function with the magic name
<a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>.
If so, that function is executed prior to any serialization. It can
clean up the object and is supposed to return an array with the names of
all variables of that object that should be serialized. If the method
doesn't return anything then **`NULL`** is serialized and **`E_NOTICE`**
is issued.

> **Note**:
>
> It is not possible for
> <a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
> to return names of private properties in parent classes. Doing this
> will result in an **`E_NOTICE`** level error. Instead you may use the
> <span class="classname">Serializable</span> interface.

The intended use of
<a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
is to commit pending data or perform similar cleanup tasks. Also, the
function is useful if you have very large objects which do not need to
be saved completely.

Conversely, <span class="function">unserialize</span> checks for the
presence of a function with the magic name
<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>.
If present, this function can reconstruct any resources that the object
may have.

The intended use of
<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
is to reestablish any database connections that may have been lost
during serialization and perform other reinitialization tasks.

**Example \#1 Sleep and wakeup**

``` php
<?php
class Connection
{
    protected $link;
    private $dsn, $username, $password;
    
    public function __construct($dsn, $username, $password)
    {
        $this->dsn = $dsn;
        $this->username = $username;
        $this->password = $password;
        $this->connect();
    }
    
    private function connect()
    {
        $this->link = new PDO($this->dsn, $this->username, $this->password);
    }
    
    public function __sleep()
    {
        return array('dsn', 'username', 'password');
    }
    
    public function __wakeup()
    {
        $this->connect();
    }
}?>
```

### <a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a> and <a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">\_\_serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">\_\_unserialize</span> ( <span
class="methodparam"><span class="type">array</span> `$data`</span> )

<span class="function">serialize</span> checks if the class has a
function with the magic name
<a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>.
If so, that function is executed prior to any serialization. It must
construct and return an associative array of key/value pairs that
represent the serialized form of the object. If no array is returned a
<span class="classname">TypeError</span> will be thrown.

> **Note**:
>
> If both
> <a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>
> and
> <a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
> are defined in the same object, only
> <a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>
> will be called.
> <a href="/language/oop5/magic.html#object.sleep" class="link">__sleep()</a>
> will be ignored. If the object implements the
> <a href="/class/serializable.html" class="link">Serializable</a>
> interface, the interface's *serialize()* method will be ignored and
> <a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>
> used instead.

The intended use of
<a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>
is to define a serialization-friendly arbitrary representation of the
object. Elements of the array may correspond to properties of the object
but that is not required.

Conversely, <span class="function">unserialize</span> checks for the
presence of a function with the magic name
<a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>.
If present, this function will be passed the restored array that was
returned from
<a href="/language/oop5/magic.html#object.serialize" class="link">__serialize()</a>.
It may then restore the properties of the object from that array as
appropriate.

> **Note**:
>
> If both
> <a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>
> and
> <a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
> are defined in the same object, only
> <a href="/language/oop5/magic.html#object.unserialize" class="link">__unserialize()</a>
> will be called.
> <a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
> will be ignored.

> **Note**:
>
> This feature is available since PHP 7.4.0.

**Example \#2 Serialize and unserialize**

``` php
<?php
class Connection
{
    protected $link;
    private $dsn, $username, $password;

    public function __construct($dsn, $username, $password)
    {
        $this->dsn = $dsn;
        $this->username = $username;
        $this->password = $password;
        $this->connect();
    }

    private function connect()
    {
        $this->link = new PDO($this->dsn, $this->username, $this->password);
    }

    public function __serialize(): array
    {
        return [
          'dsn' => $this->dsn,
          'user' => $this->username,
          'pass' => $this->password,
        ];
    }

    public function __unserialize(array $data): void
    {
        $this->dsn = $data['dsn'];
        $this->username = $data['user'];
        $this->password = $data['pass'];

        $this->connect();
    }
}?>
```

### <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

The
<a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>
method allows a class to decide how it will react when it is treated
like a string. For example, what *echo $obj;* will print. This method
must return a string, as otherwise a fatal **`E_RECOVERABLE_ERROR`**
level error is emitted.

**Warning**

It was not possible to throw an exception from within a
<a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>
method before PHP 7.4.0. Doing so will result in a fatal error.

**Example \#3 Simple example**

``` php
<?php
// Declare a simple class
class TestClass
{
    public $foo;

    public function __construct($foo)
    {
        $this->foo = $foo;
    }

    public function __toString()
    {
        return $this->foo;
    }
}

$class = new TestClass('Hello');
echo $class;
?>
```

The above example will output:

    Hello

It is worth noting that before PHP 5.2.0 the
<a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>
method was only called when it was directly combined with <span
class="function">echo</span> or <span class="function">print</span>.
Since PHP 5.2.0, it is called in any string context (e.g. in <span
class="function">printf</span> with *%s* modifier) but not in other
types contexts (e.g. with *%d* modifier). Since PHP 5.2.0, converting
objects without
<a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>
method to string would cause **`E_RECOVERABLE_ERROR`**.

### <a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>

<span class="type">mixed</span> <span
class="methodname">\_\_invoke</span> (\[ <span class="methodparam">
`$...`</span> \] )

The
<a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>
method is called when a script tries to call an object as a function.

> **Note**:
>
> This feature is available since PHP 5.3.0.

**Example \#4 Using
<a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>**

``` php
<?php
class CallableClass
{
    public function __invoke($x)
    {
        var_dump($x);
    }
}
$obj = new CallableClass;
$obj(5);
var_dump(is_callable($obj));
?>
```

The above example will output:

    int(5)
    bool(true)

### <a href="/language/oop5/magic.html#object.set-state" class="link">__set_state()</a>

<span class="modifier">static</span> <span class="type">object</span>
<span class="methodname">\_\_set\_state</span> ( <span
class="methodparam"><span class="type">array</span> `$properties`</span>
)

This <a href="/language/oop5/static.html" class="link">static</a> method
is called for classes exported by <span
class="function">var\_export</span> since PHP 5.1.0.

The only parameter of this method is an array containing exported
properties in the form *array('property' =\> value, ...)*.

**Example \#5 Using
<a href="/language/oop5/magic.html#object.set-state" class="link">__set_state()</a>
(since PHP 5.1.0)**

``` php
<?php

class A
{
    public $var1;
    public $var2;

    public static function __set_state($an_array) // As of PHP 5.1.0
    {
        $obj = new A;
        $obj->var1 = $an_array['var1'];
        $obj->var2 = $an_array['var2'];
        return $obj;
    }
}

$a = new A;
$a->var1 = 5;
$a->var2 = 'foo';

eval('$b = ' . var_export($a, true) . ';'); // $b = A::__set_state(array(
                                            //    'var1' => 5,
                                            //    'var2' => 'foo',
                                            // ));
var_dump($b);

?>
```

The above example will output:

    object(A)#2 (2) {
      ["var1"]=>
      int(5)
      ["var2"]=>
      string(3) "foo"
    }

> **Note**: <span class="simpara"> When exporting an object, <span
> class="function">var\_export</span> does not check whether
> <a href="/language/oop5/magic.html#object.set-state" class="link">__set_state()</a>
> is implemented by the object's class, so re-importing such objects
> will fail, if \_\_set\_state() is not implemented. Particularly, this
> affects some internal classes. </span> <span class="simpara"> It is
> the responsibility of the programmer to verify that only objects will
> be re-imported, whose class implements \_\_set\_state(). </span>

### <a href="/language/oop5/magic.html#object.debuginfo" class="link">__debugInfo()</a>

<span class="type">array</span> <span
class="methodname">\_\_debugInfo</span> ( <span
class="methodparam">void</span> )

This method is called by <span class="function">var\_dump</span> when
dumping an object to get the properties that should be shown. If the
method isn't defined on an object, then all public, protected and
private properties will be shown.

This feature was added in PHP 5.6.0.

**Example \#6 Using
<a href="/language/oop5/magic.html#object.debuginfo" class="link">__debugInfo()</a>**

``` php
<?php
class C {
    private $prop;

    public function __construct($val) {
        $this->prop = $val;
    }

    public function __debugInfo() {
        return [
            'propSquared' => $this->prop ** 2,
        ];
    }
}

var_dump(new C(42));
?>
```

The above example will output:

    object(C)#1 (1) {
      ["propSquared"]=>
      int(1764)
    }

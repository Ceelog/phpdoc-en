Constructors and Destructors
----------------------------

### Constructor

<span class="type">void</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$args`<span
class="initializer"> = ""</span></span> \[, <span class="methodparam">
`$...`</span> \]\] )

PHP 5 allows developers to declare constructor methods for classes.
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

**Example \#1 using new unified constructors**

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

For backwards compatibility with PHP 3 and 4, if PHP cannot find a
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
function for a given class, it will search for the old-style constructor
function, by the name of the class. Effectively, it means that the only
case that would have compatibility issues is if the class had a method
named
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
which was used for different semantics.

**Warning**

Old style constructors are *DEPRECATED* in PHP 7.0, and will be removed
in a future version. You should always use
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
in new code.

Unlike with other methods, PHP will not generate an **`E_STRICT`** level
error message when
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
is overridden with different parameters than the parent
<a href="/language/oop5/decon.html#object.construct" class="link">__construct()</a>
method has.

As of PHP 5.3.3, methods with the same name as the last element of a
namespaced class name will no longer be treated as constructor. This
change doesn't affect non-namespaced classes.

**Example \#2 Constructors in namespaced classes**

``` php
<?php
namespace Foo;
class Bar {
    public function Bar() {
        // treated as constructor in PHP 5.3.0-5.3.2
        // treated as regular method as of PHP 5.3.3
    }
}
?>
```

### Destructor

<span class="type">void</span> <span
class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

PHP 5 introduces a destructor concept similar to that of other
object-oriented languages, such as C++. The destructor method will be
called as soon as there are no other references to a particular object,
or in any order during the shutdown sequence.

**Example \#3 Destructor Example**

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

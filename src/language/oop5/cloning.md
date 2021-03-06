Object Cloning
--------------

Creating a copy of an object with fully replicated properties is not
always the wanted behavior. A good example of the need for copy
constructors, is if you have an object which represents a GTK window and
the object holds the resource of this GTK window, when you create a
duplicate you might want to create a new window with the same properties
and have the new object hold the resource of the new window. Another
example is if your object holds a reference to another object which it
uses and when you replicate the parent object you want to create a new
instance of this other object so that the replica has its own separate
copy.

An object copy is created by using the *clone* keyword (which calls the
object's
<a href="/language/oop5/cloning.html#object.clone" class="link">__clone()</a>
method if possible). An object's
<a href="/language/oop5/cloning.html#object.clone" class="link">__clone()</a>
method cannot be called directly.

    $copy_of_object = clone $object;

When an object is cloned, PHP will perform a shallow copy of all of the
object's properties. Any properties that are references to other
variables will remain references.

<span class="type">void</span> <span class="methodname">\_\_clone</span>
( <span class="methodparam">void</span> )

Once the cloning is complete, if a
<a href="/language/oop5/cloning.html#object.clone" class="link">__clone()</a>
method is defined, then the newly created object's
<a href="/language/oop5/cloning.html#object.clone" class="link">__clone()</a>
method will be called, to allow any necessary properties that need to be
changed.

**Example \#1 Cloning an object**

``` php
<?php
class SubObject
{
    static $instances = 0;
    public $instance;

    public function __construct() {
        $this->instance = ++self::$instances;
    }

    public function __clone() {
        $this->instance = ++self::$instances;
    }
}

class MyCloneable
{
    public $object1;
    public $object2;

    function __clone()
    {
        // Force a copy of this->object, otherwise
        // it will point to same object.
        $this->object1 = clone $this->object1;
    }
}

$obj = new MyCloneable();

$obj->object1 = new SubObject();
$obj->object2 = new SubObject();

$obj2 = clone $obj;


print("Original Object:\n");
print_r($obj);

print("Cloned Object:\n");
print_r($obj2);

?>
```

The above example will output:

    Original Object:
    MyCloneable Object
    (
        [object1] => SubObject Object
            (
                [instance] => 1
            )

        [object2] => SubObject Object
            (
                [instance] => 2
            )

    )
    Cloned Object:
    MyCloneable Object
    (
        [object1] => SubObject Object
            (
                [instance] => 3
            )

        [object2] => SubObject Object
            (
                [instance] => 2
            )

    )

PHP 7.0.0 introduced the possibility to access a member of a freshly
cloned object in a single expression:

**Example \#2 Access member of freshly cloned object**

``` php
<?php
$dateTime = new DateTime();
echo (clone $dateTime)->format('Y');
?>
```

The above example will output something similar to:

    2016

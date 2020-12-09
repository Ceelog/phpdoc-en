Miscellaneous Classes and Interfaces
====================================

**Table of Contents**

-   [ArrayObject](/spl/misc.html#ArrayObject) — The ArrayObject class
    -   [ArrayObject::append](/spl/misc.html#ArrayObject::append) —
        Appends the value
    -   [ArrayObject::asort](/spl/misc.html#ArrayObject::asort) — Sort
        the entries by value
    -   [ArrayObject::\_\_construct](/spl/misc.html#ArrayObject::__construct)
        — Construct a new array object
    -   [ArrayObject::count](/spl/misc.html#ArrayObject::count) — Get
        the number of public properties in the ArrayObject
    -   [ArrayObject::exchangeArray](/spl/misc.html#ArrayObject::exchangeArray)
        — Exchange the array for another one
    -   [ArrayObject::getArrayCopy](/spl/misc.html#ArrayObject::getArrayCopy)
        — Creates a copy of the ArrayObject
    -   [ArrayObject::getFlags](/spl/misc.html#ArrayObject::getFlags) —
        Gets the behavior flags
    -   [ArrayObject::getIterator](/spl/misc.html#ArrayObject::getIterator)
        — Create a new iterator from an ArrayObject instance
    -   [ArrayObject::getIteratorClass](/spl/misc.html#ArrayObject::getIteratorClass)
        — Gets the iterator classname for the ArrayObject
    -   [ArrayObject::ksort](/spl/misc.html#ArrayObject::ksort) — Sort
        the entries by key
    -   [ArrayObject::natcasesort](/spl/misc.html#ArrayObject::natcasesort)
        — Sort an array using a case insensitive "natural order"
        algorithm
    -   [ArrayObject::natsort](/spl/misc.html#ArrayObject::natsort) —
        Sort entries using a "natural order" algorithm
    -   [ArrayObject::offsetExists](/spl/misc.html#ArrayObject::offsetExists)
        — Returns whether the requested index exists
    -   [ArrayObject::offsetGet](/spl/misc.html#ArrayObject::offsetGet)
        — Returns the value at the specified index
    -   [ArrayObject::offsetSet](/spl/misc.html#ArrayObject::offsetSet)
        — Sets the value at the specified index to newval
    -   [ArrayObject::offsetUnset](/spl/misc.html#ArrayObject::offsetUnset)
        — Unsets the value at the specified index
    -   [ArrayObject::serialize](/spl/misc.html#ArrayObject::serialize)
        — Serialize an ArrayObject
    -   [ArrayObject::setFlags](/spl/misc.html#ArrayObject::setFlags) —
        Sets the behavior flags
    -   [ArrayObject::setIteratorClass](/spl/misc.html#ArrayObject::setIteratorClass)
        — Sets the iterator classname for the ArrayObject
    -   [ArrayObject::uasort](/spl/misc.html#ArrayObject::uasort) — Sort
        the entries with a user-defined comparison function and maintain
        key association
    -   [ArrayObject::uksort](/spl/misc.html#ArrayObject::uksort) — Sort
        the entries by keys using a user-defined comparison function
    -   [ArrayObject::unserialize](/spl/misc.html#ArrayObject::unserialize)
        — Unserialize an ArrayObject
-   [SplObserver](/spl/misc.html#SplObserver) — The SplObserver
    interface
    -   [SplObserver::update](/spl/misc.html#SplObserver::update) —
        Receive update from subject
-   [SplSubject](/spl/misc.html#SplSubject) — The SplSubject interface
    -   [SplSubject::attach](/spl/misc.html#SplSubject::attach) — Attach
        an SplObserver
    -   [SplSubject::detach](/spl/misc.html#SplSubject::detach) — Detach
        an observer
    -   [SplSubject::notify](/spl/misc.html#SplSubject::notify) — Notify
        an observer

Classes and interfaces which do not fit into the other SPL categories.

Introduction
------------

This class allows objects to work as arrays.

Class synopsis
--------------

**ArrayObject**

<span class="ooclass"> class **ArrayObject** </span> <span
class="oointerface">implements <span
class="interfacename">IteratorAggregate</span> </span> <span
class="oointerface">, <span class="interfacename">ArrayAccess</span>
</span> <span class="oointerface">, <span
class="interfacename">Serializable</span> </span> <span
class="oointerface">, <span class="interfacename">Countable</span>
</span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`STD_PROP_LIST` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`ARRAY_AS_PROPS` <span class="initializer"> = 2</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$input`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span>
`$iterator_class`<span class="initializer"> =
"ArrayIterator"</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">append</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">asort</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">exchangeArray</span> ( <span
class="methodparam"><span class="type">mixed</span> `$input`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getArrayCopy</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getFlags</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">ArrayIterator</span> <span
class="methodname">getIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getIteratorClass</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ksort</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">natcasesort</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">natsort</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">offsetExists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">offsetGet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">offsetUnset</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">serialize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setFlags</span> ( <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setIteratorClass</span> ( <span
class="methodparam"><span class="type">string</span>
`$iterator_class`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">uasort</span> ( <span class="methodparam"><span
class="type">callable</span> `$cmp_function`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">uksort</span> ( <span class="methodparam"><span
class="type">callable</span> `$cmp_function`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

}

Predefined Constants
--------------------

ArrayObject Flags
-----------------

**`ArrayObject::STD_PROP_LIST`**  
Properties of the object have their normal functionality when accessed
as list (var\_dump, foreach, etc.).

**`ArrayObject::ARRAY_AS_PROPS`**  
Entries can be accessed as properties (read and write).

Changelog
---------

| Version | Description                                                 |
|---------|-------------------------------------------------------------|
| 5.3.0   | Implements <span class="interfacename">Serializable</span>. |

ArrayObject::append
===================

Appends the value

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::append</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Appends a new value as the last element.

> **Note**:
>
> This method cannot be called when the <span
> class="classname">ArrayObject</span> was constructed from an object.
> Use <span class="methodname">ArrayObject::offsetSet</span> instead.

### Parameters

`value`  
The value being appended.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="methodname">ArrayObject::append</span>
example**

``` php
<?php
$arrayobj = new ArrayObject(array('first','second','third'));
$arrayobj->append('fourth');
$arrayobj->append(array('five', 'six'));
var_dump($arrayobj);
?>
```

The above example will output:

    object(ArrayObject)#1 (5) {
      [0]=>
      string(5) "first"
      [1]=>
      string(6) "second"
      [2]=>
      string(5) "third"
      [3]=>
      string(6) "fourth"
      [4]=>
      array(2) {
        [0]=>
        string(4) "five"
        [1]=>
        string(3) "six"
      }
    }

### See Also

-   <span class="methodname">ArrayObject::offsetSet</span>

ArrayObject::asort
==================

Sort the entries by value

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::asort</span> ( <span
class="methodparam">void</span> )

Sorts the entries such that the keys maintain their correlation with the
entries they are associated with. This is used mainly when sorting
associative arrays where the actual element order is significant.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ArrayObject::asort</span> example**

``` php
<?php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");
$fruitArrayObject = new ArrayObject($fruits);
$fruitArrayObject->asort();

foreach ($fruitArrayObject as $key => $val) {
    echo "$key = $val\n";
}
?>
```

The above example will output:

    c = apple
    b = banana
    d = lemon
    a = orange

The fruits have been sorted in alphabetical order, and the key
associated with each entry has been maintained.

### See Also

-   <span class="methodname">ArrayObject::ksort</span>
-   <span class="methodname">ArrayObject::natsort</span>
-   <span class="methodname">ArrayObject::natcasesort</span>
-   <span class="methodname">ArrayObject::uasort</span>
-   <span class="methodname">ArrayObject::uksort</span>

ArrayObject::\_\_construct
==========================

Construct a new array object

### Description

<span class="modifier">public</span> <span
class="methodname">ArrayObject::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$input`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span>
`$iterator_class`<span class="initializer"> =
"ArrayIterator"</span></span> \]\]\] )

This constructs a new array <span class="type">object</span>.

### Parameters

`input`  
The `input` parameter accepts an <span class="type">array</span> or an
<span class="type">Object</span>.

`flags`  
Flags to control the behaviour of the <span
class="classname">ArrayObject</span> object. See <span
class="methodname">ArrayObject::setFlags</span>.

`iterator_class`  
Specify the class that will be used for iteration of the <span
class="classname">ArrayObject</span> object.

### Return Values

Returns an ArrayObject object on success.

### Errors/Exceptions

Throws <span class="classname">InvalidArgumentException</span> when:

-   <span class="simpara"> `input` is not an array or object </span>
-   <span class="simpara"> `flags` is not an integer </span>
-   <span class="simpara"> `iterator_class` is not an object that
    implements <span class="classname">Iterator</span> </span>

### Examples

**Example \#1 <span class="function">ArrayObject::\_\_construct</span>
example**

``` php
<?php
$array = array('1' => 'one',
               '2' => 'two',
               '3' => 'three');

$arrayobject = new ArrayObject($array);

var_dump($arrayobject);
?>
```

The above example will output:

    object(ArrayObject)#1 (3) {
      [1]=>
      string(3) "one"
      [2]=>
      string(3) "two"
      [3]=>
      string(5) "three"
    }

### See Also

-   <span class="methodname">ArrayObject::setflags</span>

ArrayObject::count
==================

Get the number of public properties in the ArrayObject

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ArrayObject::count</span> ( <span
class="methodparam">void</span> )

Get the number of public properties in the <span
class="classname">ArrayObject</span>.

### Parameters

This function has no parameters.

### Return Values

The number of public properties in the <span
class="classname">ArrayObject</span>.

> **Note**:
>
> When the <span class="classname">ArrayObject</span> is constructed
> from an array all properties are public.

### Examples

**Example \#1 <span class="methodname">ArrayObject::count</span>
example**

``` php
<?php
class Example {
    public $public = 'prop:public';
    private $prv   = 'prop:private';
    protected $prt = 'prop:protected';
}

$arrayobj = new ArrayObject(new Example());
var_dump($arrayobj->count());

$arrayobj = new ArrayObject(array('first','second','third'));
var_dump($arrayobj->count());
?>
```

The above example will output:

    int(1)
    int(3)

ArrayObject::exchangeArray
==========================

Exchange the array for another one

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ArrayObject::exchangeArray</span> ( <span
class="methodparam"><span class="type">mixed</span> `$input`</span> )

Exchange the current <span class="type">array</span> with another <span
class="type">array</span> or <span class="type">object</span>.

### Parameters

`input`  
The new <span class="type">array</span> or <span
class="type">object</span> to exchange with the current array.

### Return Values

Returns the old <span class="type">array</span>.

### Examples

**Example \#1 <span class="function">ArrayObject::exchangeArray</span>
example**

``` php
<?php
// Array of available fruits
$fruits = array("lemons" => 1, "oranges" => 4, "bananas" => 5, "apples" => 10);
// Array of locations in Europe
$locations = array('Amsterdam', 'Paris', 'London');

$fruitsArrayObject = new ArrayObject($fruits);

// Now exchange fruits for locations
$old = $fruitsArrayObject->exchangeArray($locations);
print_r($old);
print_r($fruitsArrayObject);

?>
```

The above example will output:

    Array
    (
        [lemons] => 1
        [oranges] => 4
        [bananas] => 5
        [apples] => 10
    )
    ArrayObject Object
    (
        [0] => Amsterdam
        [1] => Paris
        [2] => London
    )

ArrayObject::getArrayCopy
=========================

Creates a copy of the ArrayObject

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">ArrayObject::getArrayCopy</span> ( <span
class="methodparam">void</span> )

Exports the <span class="classname">ArrayObject</span> to an array.

### Parameters

This function has no parameters.

### Return Values

Returns a copy of the array. When the <span
class="classname">ArrayObject</span> refers to an object, an array of
the properties of that object will be returned.

### Examples

**Example \#1 <span class="function">ArrayObject::getArrayCopy</span>
example**

``` php
<?php
// Array of available fruits
$fruits = array("lemons" => 1, "oranges" => 4, "bananas" => 5, "apples" => 10);

$fruitsArrayObject = new ArrayObject($fruits);
$fruitsArrayObject['pears'] = 4;

// create a copy of the array
$copy = $fruitsArrayObject->getArrayCopy();
print_r($copy);

?>
```

The above example will output:

    Array
    (
        [lemons] => 1
        [oranges] => 4
        [bananas] => 5
        [apples] => 10
        [pears] => 4
    )

ArrayObject::getFlags
=====================

Gets the behavior flags

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">ArrayObject::getFlags</span> ( <span
class="methodparam">void</span> )

Gets the behavior flags of the <span
class="classname">ArrayObject</span>. See the
<a href="/spl/misc.html#ArrayObject::setFlags" class="link">ArrayObject::setFlags</a>
method for a list of the available flags.

### Parameters

This function has no parameters.

### Return Values

Returns the behavior flags of the ArrayObject.

### Examples

**Example \#1 <span class="function">ArrayObject::getFlags</span>
example**

``` php
<?php
// Array of available fruits
$fruits = array("lemons" => 1, "oranges" => 4, "bananas" => 5, "apples" => 10);

$fruitsArrayObject = new ArrayObject($fruits);

// Get the current flags
$flags = $fruitsArrayObject->getFlags();
var_dump($flags);

// Set new flags
$fruitsArrayObject->setFlags(ArrayObject::ARRAY_AS_PROPS);

// Get the new flags
$flags = $fruitsArrayObject->getFlags();
var_dump($flags);
?>
```

The above example will output:

    int(0)
    int(2)

### See Also

-   <span class="methodname">ArrayObject::setFlags</span>

ArrayObject::getIterator
========================

Create a new iterator from an ArrayObject instance

### Description

<span class="modifier">public</span> <span
class="type">ArrayIterator</span> <span
class="methodname">ArrayObject::getIterator</span> ( <span
class="methodparam">void</span> )

Create a new iterator from an <span class="classname">ArrayObject</span>
instance.

### Parameters

This function has no parameters.

### Return Values

An iterator from an <span class="classname">ArrayObject</span>.

### Examples

**Example \#1 <span class="function">ArrayObject::getIterator</span>
example**

``` php
<?php
$array = array('1' => 'one',
               '2' => 'two',
               '3' => 'three');

$arrayobject = new ArrayObject($array);

$iterator = $arrayobject->getIterator();

while($iterator->valid()) {
    echo $iterator->key() . ' => ' . $iterator->current() . "\n";

    $iterator->next();
}
?>
```

The above example will output:

    1 => one
    2 => two
    3 => three

ArrayObject::getIteratorClass
=============================

Gets the iterator classname for the ArrayObject

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ArrayObject::getIteratorClass</span> ( <span
class="methodparam">void</span> )

Gets the class name of the array iterator that is used by
<a href="/spl/misc.html#ArrayObject::getIterator" class="link">ArrayObject::getIterator()</a>.

### Parameters

This function has no parameters.

### Return Values

Returns the iterator class name that is used to iterate over this
object.

### Examples

**Example \#1 <span
class="function">ArrayObject::getIteratorClass</span> example**

``` php
<?php
// Custom ArrayIterator (inherits from ArrayIterator)
class MyArrayIterator extends ArrayIterator {
    // custom implementation
}

// Array of available fruits
$fruits = array("lemons" => 1, "oranges" => 4, "bananas" => 5, "apples" => 10);

$fruitsArrayObject = new ArrayObject($fruits);

// Get the current class name
$className = $fruitsArrayObject->getIteratorClass();
var_dump($className);

// Set new classname
$fruitsArrayObject->setIteratorClass('MyArrayIterator');

// Get the new iterator classname
$className = $fruitsArrayObject->getIteratorClass();
var_dump($className);
?>
```

The above example will output:

    string(13) "ArrayIterator"
    string(15) "MyArrayIterator"

### See Also

-   The
    <a href="/spl/misc.html#ArrayObject::setIteratorClass" class="link">ArrayObject::setIteratorClass</a>
    method

ArrayObject::ksort
==================

Sort the entries by key

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::ksort</span> ( <span
class="methodparam">void</span> )

Sorts the entries by key, maintaining key to entry correlations. This is
useful mainly for associative arrays.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ArrayObject::ksort</span> example**

``` php
<?php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");
$fruitArrayObject = new ArrayObject($fruits);
$fruitArrayObject->ksort();

foreach ($fruitArrayObject as $key => $val) {
    echo "$key = $val\n";
}
 ?>
```

The above example will output:

    a = orange
    b = banana
    c = apple
    d = lemon

### See Also

-   <span class="methodname">ArrayObject::asort</span>
-   <span class="methodname">ArrayObject::natsort</span>
-   <span class="methodname">ArrayObject::natcasesort</span>
-   <span class="methodname">ArrayObject::uasort</span>
-   <span class="methodname">ArrayObject::uksort</span>

ArrayObject::natcasesort
========================

Sort an array using a case insensitive "natural order" algorithm

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::natcasesort</span> ( <span
class="methodparam">void</span> )

This method is a case insensitive version of
<a href="/spl/misc.html#ArrayObject::natsort" class="link">ArrayObject::natsort</a>.

This method implements a sort algorithm that orders alphanumeric strings
in the way a human being would while maintaining key/value associations.
This is described as a "natural ordering".

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ArrayObject::natcasesort</span>
example**

``` php
<?php
$array = array('IMG0.png', 'img12.png', 'img10.png', 'img2.png', 'img1.png', 'IMG3.png');

$arr1 = new ArrayObject($array);
$arr2 = clone $arr1;

$arr1->asort();
echo "Standard sorting\n";
print_r($arr1);

$arr2->natcasesort();
echo "\nNatural order sorting (case-insensitive)\n";
print_r($arr2);
?>
```

The above example will output:

    Standard sorting
    ArrayObject Object
    (
        [0] => IMG0.png
        [5] => IMG3.png
        [4] => img1.png
        [2] => img10.png
        [1] => img12.png
        [3] => img2.png
    )

    Natural order sorting (case-insensitive)
    ArrayObject Object
    (
        [0] => IMG0.png
        [4] => img1.png
        [3] => img2.png
        [5] => IMG3.png
        [2] => img10.png
        [1] => img12.png
    )

For more information see: Martin Pool's
<a href="http://sourcefrog.net/projects/natsort/" class="link external">» Natural Order String Comparison</a>
page.

### See Also

-   <span class="methodname">ArrayObject::asort</span>
-   <span class="methodname">ArrayObject::ksort</span>
-   <span class="methodname">ArrayObject::natsort</span>
-   <span class="methodname">ArrayObject::uasort</span>
-   <span class="methodname">ArrayObject::uksort</span>

ArrayObject::natsort
====================

Sort entries using a "natural order" algorithm

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::natsort</span> ( <span
class="methodparam">void</span> )

This method implements a sort algorithm that orders alphanumeric strings
in the way a human being would while maintaining key/value associations.
This is described as a "natural ordering". An example of the difference
between this algorithm and the regular computer string sorting
algorithms (used in
<a href="/spl/misc.html#ArrayObject::asort" class="link">ArrayObject::asort</a>)
method can be seen in the example below.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ArrayObject::natsort</span>
example**

``` php
<?php
$array = array("img12.png", "img10.png", "img2.png", "img1.png");

$arr1 = new ArrayObject($array);
$arr2 = clone $arr1;

$arr1->asort();
echo "Standard sorting\n";
print_r($arr1);

$arr2->natsort();
echo "\nNatural order sorting\n";
print_r($arr2);
?>
```

The above example will output:

    Standard sorting
    ArrayObject Object
    (
        [3] => img1.png
        [1] => img10.png
        [0] => img12.png
        [2] => img2.png
    )

    Natural order sorting
    ArrayObject Object
    (
        [3] => img1.png
        [2] => img2.png
        [1] => img10.png
        [0] => img12.png
    )

For more information see: Martin Pool's
<a href="http://sourcefrog.net/projects/natsort/" class="link external">» Natural Order String Comparison</a>
page.

### See Also

-   <span class="methodname">ArrayObject::asort</span>
-   <span class="methodname">ArrayObject::ksort</span>
-   <span class="methodname">ArrayObject::natcasesort</span>
-   <span class="methodname">ArrayObject::uasort</span>
-   <span class="methodname">ArrayObject::uksort</span>

ArrayObject::offsetExists
=========================

Returns whether the requested index exists

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ArrayObject::offsetExists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

### Parameters

`index`  
The index being checked.

### Return Values

**`true`** if the requested index exists, otherwise **`false`**

### Examples

**Example \#1 <span class="methodname">ArrayObject::offsetExists</span>
example**

``` php
<?php
$arrayobj = new ArrayObject(array('zero', 'one', 'example'=>'e.g.'));
var_dump($arrayobj->offsetExists(1));
var_dump($arrayobj->offsetExists('example'));
var_dump($arrayobj->offsetExists('notfound'));
?>
```

The above example will output:

    bool(true)
    bool(true)
    bool(false)

ArrayObject::offsetGet
======================

Returns the value at the specified index

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">ArrayObject::offsetGet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

### Parameters

`index`  
The index with the value.

### Return Values

The value at the specified index or **`null`**.

### Errors/Exceptions

Produces an **`E_NOTICE`** error message when the specified index does
not exist.

### Examples

**Example \#1 <span class="methodname">ArrayObject::offsetGet</span>
example**

``` php
<?php
$arrayobj = new ArrayObject(array('zero', 7, 'example'=>'e.g.'));
var_dump($arrayobj->offsetGet(1));
var_dump($arrayobj->offsetGet('example'));
var_dump($arrayobj->offsetExists('notfound'));
?>
```

The above example will output:

    int(7)
    string(4) "e.g."
    bool(false)

ArrayObject::offsetSet
======================

Sets the value at the specified index to newval

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::offsetSet</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$newval`</span> )

Sets the value at the specified index to newval.

### Parameters

`index`  
The index being set.

`newval`  
The new value for the `index`.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="methodname">ArrayObject::offsetSet</span>
example**

``` php
<?php
class Example {
    public $property = 'prop:public';
}
$arrayobj = new ArrayObject(new Example());
$arrayobj->offsetSet(4, 'four');
$arrayobj->offsetSet('group', array('g1', 'g2'));
var_dump($arrayobj);

$arrayobj = new ArrayObject(array('zero','one'));
$arrayobj->offsetSet(null, 'last');
var_dump($arrayobj);
?>
```

The above example will output:

    object(ArrayObject)#1 (3) {
      ["property"]=>
      string(11) "prop:public"
      [4]=>
      string(4) "four"
      ["group"]=>
      array(2) {
        [0]=>
        string(2) "g1"
        [1]=>
        string(2) "g2"
      }
    }
    object(ArrayObject)#3 (3) {
      [0]=>
      string(4) "zero"
      [1]=>
      string(3) "one"
      [2]=>
      string(4) "last"
    }

### See Also

-   <span class="methodname">ArrayObject::append</span>

ArrayObject::offsetUnset
========================

Unsets the value at the specified index

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::offsetUnset</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

Unsets the value at the specified index.

### Parameters

`index`  
The index being unset.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="methodname">ArrayObject::offsetUnset</span>
example**

``` php
<?php
$arrayobj = new ArrayObject(array(0=>'zero',2=>'two'));
$arrayobj->offsetUnset(2);
var_dump($arrayobj);
?>
```

The above example will output:

    object(ArrayObject)#1 (1) {
      [0]=>
      string(4) "zero"
    }

ArrayObject::serialize
======================

Serialize an ArrayObject

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ArrayObject::serialize</span> ( <span
class="methodparam">void</span> )

Serializes an <span class="classname">ArrayObject</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

The serialized representation of the <span
class="classname">ArrayObject</span>.

### Examples

**Example \#1 <span class="methodname">ArrayObject::serialize</span>
example**

``` php
<?php
$o = new ArrayObject();

$s1 = serialize($o);
$s2 = $o->serialize();

var_dump($s1);
var_dump($s2);
?>
```

The above example will output:

    string(45) "C:11:"ArrayObject":21:{x:i:0;a:0:{};m:a:0:{}}"
    string(21) "x:i:0;a:0:{};m:a:0:{}"

### See Also

-   <span class="methodname">ArrayObject::unserialize</span>
-   <span class="function">serialize</span>
-   <a href="/language/oop5/serialization.html" class="link">Serializing Objects</a>

ArrayObject::setFlags
=====================

Sets the behavior flags

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::setFlags</span> ( <span
class="methodparam"><span class="type">int</span> `$flags`</span> )

Set the flags that change the behavior of the ArrayObject.

### Parameters

`flags`  
The new ArrayObject behavior. It takes on either a bitmask, or named
constants. Using named constants is strongly encouraged to ensure
compatibility for future versions.

The available behavior flags are listed below. The actual meanings of
these flags are described in the
<a href="/spl/misc.html#Predefined%20Constants" class="link">predefined constants</a>.

| value | constant                                                               |
|-------|------------------------------------------------------------------------|
| 1     | <a href="/spl/misc.html#" class="link">ArrayObject::STD_PROP_LIST</a>  |
| 2     | <a href="/spl/misc.html#" class="link">ArrayObject::ARRAY_AS_PROPS</a> |

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ArrayObject::setFlags</span>
example**

``` php
<?php
// Array of available fruits
$fruits = array("lemons" => 1, "oranges" => 4, "bananas" => 5, "apples" => 10);

$fruitsArrayObject = new ArrayObject($fruits);

// Try to use array key as property
var_dump($fruitsArrayObject->lemons);
// Set the flag so that the array keys can be used as properties of the ArrayObject
$fruitsArrayObject->setFlags(ArrayObject::ARRAY_AS_PROPS);
// Try it again
var_dump($fruitsArrayObject->lemons);
?>
```

The above example will output:

    NULL
    int(1)

ArrayObject::setIteratorClass
=============================

Sets the iterator classname for the ArrayObject

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::setIteratorClass</span> ( <span
class="methodparam"><span class="type">string</span>
`$iterator_class`</span> )

Sets the classname of the array iterator that is used by
<a href="/spl/misc.html#ArrayObject::getIterator" class="link">ArrayObject::getIterator()</a>.

### Parameters

`iterator_class`  
The classname of the array iterator to use when iterating over this
object.

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">ArrayObject::setIteratorClass</span> example**

``` php
<?php
// Custom ArrayIterator (inherits from ArrayIterator)
class MyArrayIterator extends ArrayIterator {
    // custom implementation
}

// Array of available fruits
$fruits = array("lemons" => 1, "oranges" => 4, "bananas" => 5, "apples" => 10);

$fruitsArrayObject = new ArrayObject($fruits);

// Set the iterator classname to the newly
$fruitsArrayObject->setIteratorClass('MyArrayIterator');
print_r($fruitsArrayObject->getIterator());

?>
```

The above example will output:

    MyArrayIterator Object
    (
        [lemons] => 1
        [oranges] => 4
        [bananas] => 5
        [apples] => 10
    )

ArrayObject::uasort
===================

Sort the entries with a user-defined comparison function and maintain
key association

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::uasort</span> ( <span
class="methodparam"><span class="type">callable</span>
`$cmp_function`</span> )

This function sorts the entries such that keys maintain their
correlation with the entry that they are associated with, using a
user-defined comparison function.

This is used mainly when sorting associative arrays where the actual
element order is significant.

### Parameters

`cmp_function`  
Function `cmp_function` should accept two parameters which will be
filled by pairs of entries. The comparison function must return an
integer less than, equal to, or greater than zero if the first argument
is considered to be respectively less than, equal to, or greater than
the second.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ArrayObject::uasort</span>
example**

``` php
<?php
// Comparison function
function cmp($a, $b) {
    if ($a == $b) {
        return 0;
    }
    return ($a < $b) ? -1 : 1;
}

// Array to be sorted
$array = array('a' => 4, 'b' => 8, 'c' => -1, 'd' => -9, 'e' => 2, 'f' => 5, 'g' => 3, 'h' => -4);
$arrayObject = new ArrayObject($array);
print_r($arrayObject);

// Sort and print the resulting array
$arrayObject->uasort('cmp');
print_r($arrayObject);
?>
```

The above example will output:

    Array
    (
        [a] => 4
        [b] => 8
        [c] => -1
        [d] => -9
        [e] => 2
        [f] => 5
        [g] => 3
        [h] => -4
    )
    Array
    (
        [d] => -9
        [h] => -4
        [c] => -1
        [e] => 2
        [g] => 3
        [a] => 4
        [f] => 5
        [b] => 8
    )

### See Also

-   <span class="methodname">ArrayObject::asort</span>
-   <span class="methodname">ArrayObject::ksort</span>
-   <span class="methodname">ArrayObject::natsort</span>
-   <span class="methodname">ArrayObject::natcasesort</span>
-   <span class="methodname">ArrayObject::uksort</span>

ArrayObject::uksort
===================

Sort the entries by keys using a user-defined comparison function

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::uksort</span> ( <span
class="methodparam"><span class="type">callable</span>
`$cmp_function`</span> )

This function sorts the keys of the entries using a user-supplied
comparison function. The key to entry correlations will be maintained.

### Parameters

`cmp_function`  
The callback comparison function.

Function `cmp_function` should accept two parameters which will be
filled by pairs of entry keys. The comparison function must return an
integer less than, equal to, or greater than zero if the first argument
is considered to be respectively less than, equal to, or greater than
the second.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">ArrayObject::uksort</span>
example**

``` php
<?php
function cmp($a, $b) {
    $a = preg_replace('@^(a|an|the) @', '', $a);
    $b = preg_replace('@^(a|an|the) @', '', $b);
    return strcasecmp($a, $b);
}

$array = array("John" => 1, "the Earth" => 2, "an apple" => 3, "a banana" => 4);
$arrayObject = new ArrayObject($array);
$arrayObject->uksort('cmp');

foreach ($arrayObject as $key => $value) {
    echo "$key: $value\n";
}
?>
```

The above example will output:

    an apple: 3
    a banana: 4
    the Earth: 2
    John: 1

### See Also

-   <span class="methodname">ArrayObject::asort</span>
-   <span class="methodname">ArrayObject::ksort</span>
-   <span class="methodname">ArrayObject::natsort</span>
-   <span class="methodname">ArrayObject::natcasesort</span>
-   <span class="methodname">ArrayObject::uasort</span>

ArrayObject::unserialize
========================

Unserialize an ArrayObject

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">ArrayObject::unserialize</span> ( <span
class="methodparam"><span class="type">string</span>
`$serialized`</span> )

Unserializes a serialized <span class="classname">ArrayObject</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`serialized`  
The serialized <span class="classname">ArrayObject</span>.

### Return Values

The unserialized <span class="classname">ArrayObject</span>.

### See Also

-   <span class="methodname">ArrayIterator::serialize</span>
-   <span class="function">unserialize</span>
-   <a href="/language/oop5/serialization.html" class="link">Serializing Objects</a>

Introduction
------------

The <span class="classname">SplObserver</span> interface is used
alongside <span class="classname">SplSubject</span> to implement the
Observer Design Pattern.

Interface synopsis
------------------

**SplObserver**

<span class="ooclass"> class **SplObserver** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">update</span> ( <span class="methodparam"><span
class="type">SplSubject</span> `$subject`</span> )

}

SplObserver::update
===================

Receive update from subject

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">SplObserver::update</span> ( <span
class="methodparam"><span class="type">SplSubject</span>
`$subject`</span> )

This method is called when any <span class="classname">SplSubject</span>
to which the observer is attached calls <span
class="methodname">SplSubject::notify</span>.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`subject`  
The <span class="classname">SplSubject</span> notifying the observer of
an update.

### Return Values

No value is returned.

Introduction
------------

The <span class="classname">SplSubject</span> interface is used
alongside <span class="classname">SplObserver</span> to implement the
Observer Design Pattern.

Interface synopsis
------------------

**SplSubject**

<span class="ooclass"> class **SplSubject** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">attach</span> ( <span class="methodparam"><span
class="type">SplObserver</span> `$observer`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">detach</span> ( <span class="methodparam"><span
class="type">SplObserver</span> `$observer`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">notify</span> ( <span class="methodparam">void</span>
)

}

SplSubject::attach
==================

Attach an SplObserver

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">SplSubject::attach</span> ( <span
class="methodparam"><span class="type">SplObserver</span>
`$observer`</span> )

Attaches an <span class="classname">SplObserver</span> so that it can be
notified of updates.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`observer`  
The <span class="classname">SplObserver</span> to attach.

### Return Values

No value is returned.

SplSubject::detach
==================

Detach an observer

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">SplSubject::detach</span> ( <span
class="methodparam"><span class="type">SplObserver</span>
`$observer`</span> )

Detaches an observer from the subject to no longer notify it of updates.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`observer`  
The <span class="classname">SplObserver</span> to detach.

### Return Values

No value is returned.

SplSubject::notify
==================

Notify an observer

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">SplSubject::notify</span> ( <span
class="methodparam">void</span> )

Notifies all attached observers.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

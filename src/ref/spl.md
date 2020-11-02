class\_implements
=================

Return the interfaces which are implemented by the given class or
interface

### Description

<span class="type">array</span> <span
class="methodname">class\_implements</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$autoload`<span class="initializer"> = **`TRUE`**</span></span> \] )

This function returns an array with the names of the interfaces that the
given `class` and its parents implement.

### Parameters

`class`  
An object (class instance) or a string (class or interface name).

`autoload`  
Whether to allow this function to load the class automatically through
the <span class="function">\_\_autoload</span> magic method.

### Return Values

An array on success, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">class\_implements</span> example**

``` php
<?php

interface foo { }
class bar implements foo {}

print_r(class_implements(new bar));

// since PHP 5.1.0 you may also specify the parameter as a string
print_r(class_implements('bar'));


function __autoload($class_name) {
   require_once $class_name . '.php';
}

// use __autoload to load the 'not_loaded' class
print_r(class_implements('not_loaded', true));

?>
```

The above example will output something similar to:

    Array
    (
        [foo] => foo
    )

    Array
    (
        [interface_of_not_loaded] => interface_of_not_loaded
    )

### See Also

-   <span class="function">class\_parents</span>
-   <span class="function">get\_declared\_interfaces</span>

class\_parents
==============

Return the parent classes of the given class

### Description

<span class="type">array</span> <span
class="methodname">class\_parents</span> ( <span
class="methodparam"><span class="type">mixed</span> `$class`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$autoload`<span class="initializer"> = **`TRUE`**</span></span> \] )

This function returns an array with the name of the parent classes of
the given `class`.

### Parameters

`class`  
An object (class instance) or a string (class name).

`autoload`  
Whether to allow this function to load the class automatically through
the <span class="function">\_\_autoload</span> magic method.

### Return Values

An array on success, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">class\_parents</span> example**

``` php
<?php

class foo { }
class bar extends foo {}

print_r(class_parents(new bar));

// since PHP 5.1.0 you may also specify the parameter as a string
print_r(class_parents('bar'));


function __autoload($class_name) {
   require_once $class_name . '.php';
}

// use __autoload to load the 'not_loaded' class
print_r(class_parents('not_loaded', true));
?>
```

The above example will output something similar to:

    Array
    (
        [foo] => foo
    )

    Array
    (
        [parent_of_not_loaded] => parent_of_not_loaded
    )

### See Also

-   <span class="function">class\_implements</span>

class\_uses
===========

Return the traits used by the given class

### Description

<span class="type">array</span> <span
class="methodname">class\_uses</span> ( <span class="methodparam"><span
class="type">mixed</span> `$class`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$autoload`<span
class="initializer"> = **`TRUE`**</span></span> \] )

This function returns an array with the names of the traits that the
given `class` uses. This does however not include any traits used by a
parent class.

### Parameters

`class`  
An object (class instance) or a string (class name).

`autoload`  
Whether to allow this function to load the class automatically through
the <span class="function">\_\_autoload</span> magic method.

### Return Values

An array on success, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">class\_uses</span> example**

``` php
<?php

trait foo { }
class bar {
  use foo;
}

print_r(class_uses(new bar));

print_r(class_uses('bar'));

function __autoload($class_name) {
   require_once $class_name . '.php';
}

// use __autoload to load the 'not_loaded' class
print_r(class_uses('not_loaded', true));

?>
```

The above example will output something similar to:

    Array
    (
        [foo] => foo
    )

    Array
    (
        [foo] => foo
    )

    Array
    (
        [trait_of_not_loaded] => trait_of_not_loaded
    )

### See Also

-   <span class="function">class\_parents</span>
-   <span class="function">get\_declared\_traits</span>

iterator\_apply
===============

Call a function for every element in an iterator

### Description

<span class="type">int</span> <span
class="methodname">iterator\_apply</span> ( <span
class="methodparam"><span class="type">Traversable</span>
`$iterator`</span> , <span class="methodparam"><span
class="type">callable</span> `$function`</span> \[, <span
class="methodparam"><span class="type">array</span> `$args`<span
class="initializer"> = **`NULL`**</span></span> \] )

Calls a function for every element in an iterator.

### Parameters

`iterator`  
The iterator object to iterate over.

`function`  
The callback function to call on every element. This function only
receives the given `args`, so it is nullary by default. If *count($args)
=== 3*, for instance, the callback function is ternary.

> **Note**: <span class="simpara"> The function must return **`TRUE`**
> in order to continue iterating over the `iterator`. </span>

`args`  
An <span class="type">array</span> of arguments; each element of `args`
is passed to the callback `function` as separate argument.

### Return Values

Returns the iteration count.

### Examples

**Example \#1 <span class="function">iterator\_apply</span> example**

``` php
<?php
function print_caps(Iterator $iterator) {
    echo strtoupper($iterator->current()) . "\n";
    return TRUE;
}

$it = new ArrayIterator(array("Apples", "Bananas", "Cherries"));
iterator_apply($it, "print_caps", array($it));
?>
```

The above example will output:

    APPLES
    BANANAS
    CHERRIES

### See Also

-   <span class="function">array\_walk</span>

iterator\_count
===============

Count the elements in an iterator

### Description

<span class="type">int</span> <span
class="methodname">iterator\_count</span> ( <span
class="methodparam"><span class="type">Traversable</span>
`$iterator`</span> )

Count the elements in an iterator. <span
class="function">iterator\_count</span> is not guaranteed to retain the
current position of the `iterator`.

### Parameters

`iterator`  
The iterator being counted.

### Return Values

The number of elements in `iterator`.

### Examples

**Example \#1 <span class="function">iterator\_count</span> example**

``` php
<?php
$iterator = new ArrayIterator(array('recipe'=>'pancakes', 'egg', 'milk', 'flour'));
var_dump(iterator_count($iterator));
?>
```

The above example will output:

    int(4)

**Example \#2 <span class="function">iterator\_count</span> modifies
position**

``` php
<?php
$iterator = new ArrayIterator(['one', 'two', 'three']);
var_dump($iterator->current());
var_dump(iterator_count($iterator));
var_dump($iterator->current());
?>
```

The above example will output:

    string(3) "one"
    int(3)
    NULL

**Example \#3 <span class="function">iterator\_count</span> in
<a href="/control-structures/foreach.html" class="link">foreach</a>
loops**

``` php
<?php
$iterator = new ArrayIterator(['one', 'two', 'three']);
foreach ($iterator as $key => $value) {
    echo "$key: $value (", iterator_count($iterator), ")\n";
}?>
```

The above example will output:

    0: one (3)

iterator\_to\_array
===================

Copy the iterator into an array

### Description

<span class="type">array</span> <span
class="methodname">iterator\_to\_array</span> ( <span
class="methodparam"><span class="type">Traversable</span>
`$iterator`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$use_keys`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Copy the elements of an iterator into an array.

### Parameters

`iterator`  
The iterator being copied.

`use_keys`  
Whether to use the iterator element keys as index.

In PHP 5.5 and later, if a key is an <span class="type">array</span> or
<span class="type">object</span>, a warning will be generated.
**`NULL`** keys will be converted to an empty string, <span
class="type">float</span> keys will be truncated to their <span
class="type">int</span> counterpart, <span class="type">resource</span>
keys will generate a warning and be converted to their resource ID, and
<span class="type">bool</span> keys will be converted to integers.

> **Note**:
>
> If this parameter is not set or set to **`TRUE`**, duplicate keys will
> be overwritten. The last value with a given key will be in the
> returned <span class="type">array</span>. Set this parameter to
> **`FALSE`** to get all the values in any case.

### Return Values

An <span class="type">array</span> containing the elements of the
`iterator`.

### Examples

**Example \#1 <span class="function">iterator\_to\_array</span>
example**

``` php
<?php
$iterator = new ArrayIterator(array('recipe'=>'pancakes', 'egg', 'milk', 'flour'));
var_dump(iterator_to_array($iterator, true));
var_dump(iterator_to_array($iterator, false));
?>
```

The above example will output:

    array(4) {
      ["recipe"]=>
      string(8) "pancakes"
      [0]=>
      string(3) "egg"
      [1]=>
      string(4) "milk"
      [2]=>
      string(5) "flour"
    }
    array(4) {
      [0]=>
      string(8) "pancakes"
      [1]=>
      string(3) "egg"
      [2]=>
      string(4) "milk"
      [3]=>
      string(5) "flour"
    }

spl\_autoload\_call
===================

Try all registered \_\_autoload() functions to load the requested class

### Description

<span class="type">void</span> <span
class="methodname">spl\_autoload\_call</span> ( <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> )

This function can be used to manually search for a class or interface
using the registered \_\_autoload functions.

### Parameters

`class_name`  
The class name being searched.

### Return Values

No value is returned.

spl\_autoload\_extensions
=========================

Register and return default file extensions for spl\_autoload

### Description

<span class="type">string</span> <span
class="methodname">spl\_autoload\_extensions</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$file_extensions`</span> \] )

This function can modify and check the file extensions that the built in
<span class="function">\_\_autoload</span> fallback function <span
class="function">spl\_autoload</span> will be using.

> **Note**: <span class="simpara"> There should not be a space between
> the defined file extensions. </span>

### Parameters

`file_extensions`  
When calling without an argument, it simply returns the current list of
extensions each separated by comma. To modify the list of file
extensions, simply invoke the functions with the new list of file
extensions to use in a single string with each extensions separated by
comma.

### Return Values

A comma delimited list of default file extensions for <span
class="function">spl\_autoload</span>.

### Examples

**Example \#1 <span class="function">spl\_autoload\_extensions</span>
example**

``` php
<?php
spl_autoload_extensions(".php,.inc");
?>
```

spl\_autoload\_functions
========================

Return all registered \_\_autoload() functions

### Description

<span class="type">array</span> <span
class="methodname">spl\_autoload\_functions</span> ( <span
class="methodparam">void</span> )

Get all registered \_\_autoload() functions.

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of all registered \_\_autoload
functions. If the autoload queue is not activated then the return value
is **`FALSE`**. If no function is registered the return value will be an
empty array.

spl\_autoload\_register
=======================

Register given function as \_\_autoload() implementation

### Description

<span class="type">bool</span> <span
class="methodname">spl\_autoload\_register</span> (\[ <span
class="methodparam"><span class="type">callable</span>
`$autoload_function`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$throw`<span class="initializer"> =
**`TRUE`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$prepend`<span class="initializer"> =
**`FALSE`**</span></span> \]\]\] )

Register a function with the spl provided \_\_autoload queue. If the
queue is not yet activated it will be activated.

If your code has an existing <span class="function">\_\_autoload</span>
function then this function must be explicitly registered on the
\_\_autoload queue. This is because <span
class="function">spl\_autoload\_register</span> will effectively replace
the engine cache for the <span class="function">\_\_autoload</span>
function by either <span class="function">spl\_autoload</span> or <span
class="function">spl\_autoload\_call</span>.

If there must be multiple autoload functions, <span
class="function">spl\_autoload\_register</span> allows for this. It
effectively creates a queue of autoload functions, and runs through each
of them in the order they are defined. By contrast, <span
class="function">\_\_autoload</span> may only be defined once.

### Parameters

`autoload_function`  
The autoload function being registered. If no parameter is provided,
then the default implementation of <span
class="function">spl\_autoload</span> will be registered.

`throw`  
This parameter specifies whether <span
class="function">spl\_autoload\_register</span> should throw exceptions
when the `autoload_function` cannot be registered.

`prepend`  
If true, <span class="function">spl\_autoload\_register</span> will
prepend the autoloader on the autoload queue instead of appending it.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">spl\_autoload\_register</span> as a
replacement for an <span class="function">\_\_autoload</span> function**

``` php
<?php

// function __autoload($class) {
//     include 'classes/' . $class . '.class.php';
// }

function my_autoloader($class) {
    include 'classes/' . $class . '.class.php';
}

spl_autoload_register('my_autoloader');

// Or, using an anonymous function as of PHP 5.3.0
spl_autoload_register(function ($class) {
    include 'classes/' . $class . '.class.php';
});

?>
```

**Example \#2 <span class="function">spl\_autoload\_register</span>
example where the class is not loaded**

``` php
<?php

namespace Foobar;

class Foo {
    static public function test($name) {
        print '[['. $name .']]';
    }
}

spl_autoload_register(__NAMESPACE__ .'\Foo::test'); // As of PHP 5.3.0

new InexistentClass;

?>
```

The above example will output something similar to:

    [[Foobar\InexistentClass]]
    Fatal error: Class 'Foobar\InexistentClass' not found in ...

### See Also

-   <span class="function">\_\_autoload</span>

spl\_autoload\_unregister
=========================

Unregister given function as \_\_autoload() implementation

### Description

<span class="type">bool</span> <span
class="methodname">spl\_autoload\_unregister</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$autoload_function`</span> )

Removes a function from the autoload queue. If the queue is activated
and empty after removing the given function then it will be deactivated.

When this function results in the queue being deactivated, any
\_\_autoload function that previously existed will not be reactivated.

### Parameters

`autoload_function`  
The autoload function being unregistered.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

spl\_autoload
=============

Default implementation for \_\_autoload()

### Description

<span class="type">void</span> <span
class="methodname">spl\_autoload</span> ( <span
class="methodparam"><span class="type">string</span>
`$class_name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$file_extensions`<span class="initializer">
= spl\_autoload\_extensions()</span></span> \] )

This function is intended to be used as a default implementation for
<span class="function">\_\_autoload</span>. If nothing else is specified
and <span class="function">spl\_autoload\_register</span> is called
without any parameters then this function will be used for any later
call to <span class="function">\_\_autoload</span>.

### Parameters

`class_name`  
The lowercased name of the class (and namespace) being instantiated.

`file_extensions`  
By default it checks all include paths to contain filenames built up by
the lowercase class name appended by the filename extensions .inc and
.php.

### Return Values

No value is returned.

### Errors/Exceptions

Throws <span class="classname">LogicException</span> when the class is
not found and there are no other autoloaders registered.

spl\_classes
============

Return available SPL classes

### Description

<span class="type">array</span> <span
class="methodname">spl\_classes</span> ( <span
class="methodparam">void</span> )

This function returns an array with the current available SPL classes.

### Parameters

This function has no parameters.

### Return Values

Returns an <span class="type">array</span> containing the currently
available SPL classes.

### Examples

**Example \#1 <span class="function">spl\_classes</span> example**

``` php
<?php

print_r(spl_classes());

?>
```

The above example will output something similar to:

    Array
    (
        [ArrayObject] => ArrayObject
        [ArrayIterator] => ArrayIterator
        [CachingIterator] => CachingIterator
        [RecursiveCachingIterator] => RecursiveCachingIterator
        [DirectoryIterator] => DirectoryIterator
        [FilterIterator] => FilterIterator
        [LimitIterator] => LimitIterator
        [ParentIterator] => ParentIterator
        [RecursiveDirectoryIterator] => RecursiveDirectoryIterator
        [RecursiveIterator] => RecursiveIterator
        [RecursiveIteratorIterator] => RecursiveIteratorIterator
        [SeekableIterator] => SeekableIterator
        [SimpleXMLIterator] => SimpleXMLIterator
    )

spl\_object\_hash
=================

Return hash id for given object

### Description

<span class="type">string</span> <span
class="methodname">spl\_object\_hash</span> ( <span
class="methodparam"><span class="type">object</span> `$obj`</span> )

This function returns a unique identifier for the object. This id can be
used as a hash key for storing objects, or for identifying an object, as
long as the object is not destroyed. Once the object is destroyed, its
hash may be reused for other objects.

### Parameters

`object`  
Any object.

### Return Values

A string that is unique for each currently existing object and is always
the same for each object.

### Examples

**Example \#1 A <span class="function">spl\_object\_hash</span>
example**

``` php
<?php
$id = spl_object_hash($object);
$storage[$id] = $object;
?>
```

### Notes

> **Note**:
>
> When an object is destroyed, its hash may be reused for other objects.

spl\_object\_id
===============

Return the integer object handle for given object

### Description

<span class="type">int</span> <span
class="methodname">spl\_object\_id</span> ( <span
class="methodparam"><span class="type">object</span> `$obj`</span> )

This function returns a unique identifier for the object. The object id
is unique for the lifetime of the object. Once the object is destroyed,
its id may be reused for other objects. This behavior is similar to
<span class="function">spl\_object\_hash</span>.

### Parameters

`object`  
Any object.

### Return Values

An integer identifier that is unique for each currently existing object
and is always the same for each object.

### Examples

**Example \#1 A <span class="function">spl\_object\_id</span> example**

``` php
<?php
$id = spl_object_id($object);
$storage[$id] = $object;
?>
```

### Notes

> **Note**:
>
> When an object is destroyed, its id may be reused for other objects.

**Table of Contents**

-   [class\_implements](/ref/spl.html#class_implements) — Return the
    interfaces which are implemented by the given class or interface
-   [class\_parents](/ref/spl.html#class_parents) — Return the parent
    classes of the given class
-   [class\_uses](/ref/spl.html#class_uses) — Return the traits used by
    the given class
-   [iterator\_apply](/ref/spl.html#iterator_apply) — Call a function
    for every element in an iterator
-   [iterator\_count](/ref/spl.html#iterator_count) — Count the elements
    in an iterator
-   [iterator\_to\_array](/ref/spl.html#iterator_to_array) — Copy the
    iterator into an array
-   [spl\_autoload\_call](/ref/spl.html#spl_autoload_call) — Try all
    registered \_\_autoload() functions to load the requested class
-   [spl\_autoload\_extensions](/ref/spl.html#spl_autoload_extensions) —
    Register and return default file extensions for spl\_autoload
-   [spl\_autoload\_functions](/ref/spl.html#spl_autoload_functions) —
    Return all registered \_\_autoload() functions
-   [spl\_autoload\_register](/ref/spl.html#spl_autoload_register) —
    Register given function as \_\_autoload() implementation
-   [spl\_autoload\_unregister](/ref/spl.html#spl_autoload_unregister) —
    Unregister given function as \_\_autoload() implementation
-   [spl\_autoload](/ref/spl.html#spl_autoload) — Default implementation
    for \_\_autoload()
-   [spl\_classes](/ref/spl.html#spl_classes) — Return available SPL
    classes
-   [spl\_object\_hash](/ref/spl.html#spl_object_hash) — Return hash id
    for given object
-   [spl\_object\_id](/ref/spl.html#spl_object_id) — Return the integer
    object handle for given object

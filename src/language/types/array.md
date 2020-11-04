Arrays
------

An <span class="type">array</span> in PHP is actually an ordered map. A
map is a type that associates *values* to *keys*. This type is optimized
for several different uses; it can be treated as an array, list
(vector), hash table (an implementation of a map), dictionary,
collection, stack, queue, and probably more. As <span
class="type">array</span> values can be other <span
class="type">array</span>s, trees and multidimensional <span
class="type">array</span>s are also possible.

Explanation of those data structures is beyond the scope of this manual,
but at least one example is provided for each of them. For more
information, look towards the considerable literature that exists about
this broad topic.

### Syntax

#### Specifying with <span class="function">array</span>

An <span class="type">array</span> can be created using the <span
class="function">array</span> language construct. It takes any number of
comma-separated *<span class="replaceable">key</span> =\> <span
class="replaceable">value</span>* pairs as arguments.

``` synopsis
array(
    key  => value,
    key2 => value2,
    key3 => value3,
    ...
)
```

The comma after the last array element is optional and can be omitted.
This is usually done for single-line arrays, i.e. *array(1, 2)* is
preferred over *array(1, 2, )*. For multi-line arrays on the other hand
the trailing comma is commonly used, as it allows easier addition of new
elements at the end.

> **Note**:
>
> A short array syntax exists which replaces *array()* with *\[\]*.

**Example \#1 A simple array**

``` php
<?php
$array = array(
    "foo" => "bar",
    "bar" => "foo",
);

// Using the short array syntax
$array = [
    "foo" => "bar",
    "bar" => "foo",
];
?>
```

The <span class="replaceable">key</span> can either be an <span
class="type">int</span> or a <span class="type">string</span>. The <span
class="replaceable">value</span> can be of any type.

Additionally the following <span class="replaceable">key</span> casts
will occur:

-   <span class="simpara"> <span class="type">String</span>s containing
    valid decimal <span class="type">int</span>s, unless the number is
    preceded by a *+* sign, will be cast to the <span
    class="type">int</span> type. E.g. the key *"8"* will actually be
    stored under *8*. On the other hand *"08"* will not be cast, as it
    isn't a valid decimal integer. </span>
-   <span class="simpara"> <span class="type">Float</span>s are also
    cast to <span class="type">int</span>s, which means that the
    fractional part will be truncated. E.g. the key *8.7* will actually
    be stored under *8*. </span>
-   <span class="simpara"> <span class="type">Bool</span>s are cast to
    <span class="type">int</span>s, too, i.e. the key *true* will
    actually be stored under *1* and the key *false* under *0*. </span>
-   <span class="simpara"> <span class="type">Null</span> will be cast
    to the empty string, i.e. the key *null* will actually be stored
    under *""*. </span>
-   <span class="simpara"> <span class="type">Array</span>s and <span
    class="type">object</span>s *can not* be used as keys. Doing so will
    result in a warning: *Illegal offset type*. </span>

If multiple elements in the array declaration use the same key, only the
last one will be used as all others are overwritten.

**Example \#2 Type Casting and Overwriting example**

``` php
<?php
$array = array(
    1    => "a",
    "1"  => "b",
    1.5  => "c",
    true => "d",
);
var_dump($array);
?>
```

The above example will output:

    array(1) {
      [1]=>
      string(1) "d"
    }

As all the keys in the above example are cast to *1*, the value will be
overwritten on every new element and the last assigned value *"d"* is
the only one left over.

PHP arrays can contain <span class="type">int</span> and <span
class="type">string</span> keys at the same time as PHP does not
distinguish between indexed and associative arrays.

**Example \#3 Mixed <span class="type">int</span> and <span
class="type">string</span> keys**

``` php
<?php
$array = array(
    "foo" => "bar",
    "bar" => "foo",
    100   => -100,
    -100  => 100,
);
var_dump($array);
?>
```

The above example will output:

    array(4) {
      ["foo"]=>
      string(3) "bar"
      ["bar"]=>
      string(3) "foo"
      [100]=>
      int(-100)
      [-100]=>
      int(100)
    }

The <span class="replaceable">key</span> is optional. If it is not
specified, PHP will use the increment of the largest previously used
<span class="type">int</span> key.

**Example \#4 Indexed arrays without key**

``` php
<?php
$array = array("foo", "bar", "hello", "world");
var_dump($array);
?>
```

The above example will output:

    array(4) {
      [0]=>
      string(3) "foo"
      [1]=>
      string(3) "bar"
      [2]=>
      string(5) "hello"
      [3]=>
      string(5) "world"
    }

It is possible to specify the key only for some elements and leave it
out for others:

**Example \#5 Keys not on all elements**

``` php
<?php
$array = array(
         "a",
         "b",
    6 => "c",
         "d",
);
var_dump($array);
?>
```

The above example will output:

    array(4) {
      [0]=>
      string(1) "a"
      [1]=>
      string(1) "b"
      [6]=>
      string(1) "c"
      [7]=>
      string(1) "d"
    }

As you can see the last value *"d"* was assigned the key *7*. This is
because the largest integer key before that was *6*.

#### Accessing array elements with square bracket syntax

Array elements can be accessed using the *array\[key\]* syntax.

**Example \#6 Accessing array elements**

``` php
<?php
$array = array(
    "foo" => "bar",
    42    => 24,
    "multi" => array(
         "dimensional" => array(
             "array" => "foo"
         )
    )
);

var_dump($array["foo"]);
var_dump($array[42]);
var_dump($array["multi"]["dimensional"]["array"]);
?>
```

The above example will output:

    string(3) "bar"
    int(24)
    string(3) "foo"

> **Note**:
>
> Both square brackets and curly braces can be used interchangeably for
> accessing array elements (e.g. *$array\[42\]* and *$array{42}* will
> both do the same thing in the example above).

**Example \#7 Array dereferencing**

``` php
<?php
function getArray() {
    return array(1, 2, 3);
}

$secondElement = getArray()[1];

// or
list(, $secondElement) = getArray();
?>
```

> **Note**:
>
> Attempting to access an array key which has not been defined is the
> same as accessing any other undefined variable: an
> **`E_NOTICE`**-level error message will be issued, and the result will
> be **`NULL`**.

> **Note**:
>
> Array dereferencing a scalar value which is not a <span
> class="type">string</span> yields **`NULL`**. Prior to PHP 7.4.0, that
> did not issue an error message. As of PHP 7.4.0, this issues
> **`E_NOTICE`**; as of PHP 8.0.0, this issues **`E_WARNING`**.

#### Creating/modifying with square bracket syntax

An existing <span class="type">array</span> can be modified by
explicitly setting values in it.

This is done by assigning values to the <span class="type">array</span>,
specifying the key in brackets. The key can also be omitted, resulting
in an empty pair of brackets (*\[\]*).

``` synopsis
$arr[key] = value;
$arr[] = value;
// key may be an int or string
// value may be any value of any type
```

If `$arr` doesn't exist yet, it will be created, so this is also an
alternative way to create an <span class="type">array</span>. This
practice is however discouraged because if `$arr` already contains some
value (e.g. <span class="type">string</span> from request variable) then
this value will stay in the place and *\[\]* may actually stand for
<a href="/language/types/string.html#language.types.string.substr" class="link">string access operator</a>.
It is always better to initialize a variable by a direct assignment.

> **Note**: <span class="simpara"> As of PHP 7.1.0, applying the empty
> index operator on a string throws a fatal error. Formerly, the string
> was silently converted to an array. </span>

To change a certain value, assign a new value to that element using its
key. To remove a key/value pair, call the <span
class="function">unset</span> function on it.

``` php
<?php
$arr = array(5 => 1, 12 => 2);

$arr[] = 56;    // This is the same as $arr[13] = 56;
                // at this point of the script

$arr["x"] = 42; // This adds a new element to
                // the array with key "x"
                
unset($arr[5]); // This removes the element from the array

unset($arr);    // This deletes the whole array
?>
```

> **Note**:
>
> As mentioned above, if no key is specified, the maximum of the
> existing <span class="type">int</span> indices is taken, and the new
> key will be that maximum value plus 1 (but at least 0). If no <span
> class="type">int</span> indices exist yet, the key will be *0* (zero).
>
> Note that the maximum integer key used for this *need not currently
> exist in the <span class="type">array</span>*. It need only have
> existed in the <span class="type">array</span> at some time since the
> last time the <span class="type">array</span> was re-indexed. The
> following example illustrates:
>
> ``` php
> <?php
> // Create a simple array.
> $array = array(1, 2, 3, 4, 5);
> print_r($array);
>
> // Now delete every item, but leave the array itself intact:
> foreach ($array as $i => $value) {
>     unset($array[$i]);
> }
> print_r($array);
>
> // Append an item (note that the new key is 5, instead of 0).
> $array[] = 6;
> print_r($array);
>
> // Re-index:
> $array = array_values($array);
> $array[] = 7;
> print_r($array);
> ?>
> ```
>
> The above example will output:
>
>     Array
>     (
>         [0] => 1
>         [1] => 2
>         [2] => 3
>         [3] => 4
>         [4] => 5
>     )
>     Array
>     (
>     )
>     Array
>     (
>         [5] => 6
>     )
>     Array
>     (
>         [0] => 6
>         [1] => 7
>     )

### Useful functions

There are quite a few useful functions for working with arrays. See the
<a href="/ref/array.html" class="link">array functions</a> section.

> **Note**:
>
> The <span class="function">unset</span> function allows removing keys
> from an <span class="type">array</span>. Be aware that the array will
> *not* be reindexed. If a true "remove and shift" behavior is desired,
> the <span class="type">array</span> can be reindexed using the <span
> class="function">array\_values</span> function.
>
> ``` php
> <?php
> $a = array(1 => 'one', 2 => 'two', 3 => 'three');
> unset($a[2]);
> /* will produce an array that would have been defined as
>    $a = array(1 => 'one', 3 => 'three');
>    and NOT
>    $a = array(1 => 'one', 2 =>'three');
> */
>
> $b = array_values($a);
> // Now $b is array(0 => 'one', 1 =>'three')
> ?>
> ```

The <a href="/control-structures/foreach.html" class="link">foreach</a>
control structure exists specifically for <span
class="type">array</span>s. It provides an easy way to traverse an <span
class="type">array</span>.

### Array do's and don'ts

#### Why is *$foo\[bar\]* wrong?

Always use quotes around a string literal array index. For example,
*$foo\['bar'\]* is correct, while *$foo\[bar\]* is not. But why? It is
common to encounter this kind of syntax in old scripts:

``` php
<?php
$foo[bar] = 'enemy';
echo $foo[bar];
// etc
?>
```

This is wrong, but it works. The reason is that this code has an
undefined constant (*bar*) rather than a <span
class="type">string</span> (*'bar'* - notice the quotes). It works
because PHP automatically converts a *bare string* (an unquoted <span
class="type">string</span> which does not correspond to any known
symbol) into a <span class="type">string</span> which contains the bare
<span class="type">string</span>. For instance, if there is no defined
constant named **`bar`**, then PHP will substitute in the <span
class="type">string</span> *'bar'* and use that.

**Warning**

The fallback to treat an undefined constant as bare string is deprecated
as of PHP 7.2.0, and issues an error of level **`E_WARNING`**. Formerly,
an error of level **`E_NOTICE`** has been issued.

> **Note**: <span class="simpara"> This does not mean to *always* quote
> the key. Do not quote keys which are
> <a href="/language/constants.html" class="link">constants</a> or
> <a href="/language/variables.html" class="link">variables</a>, as this
> will prevent PHP from interpreting them. </span>
>
> ``` php
> <?php
> error_reporting(E_ALL);
> ini_set('display_errors', true);
> ini_set('html_errors', false);
> // Simple array:
> $array = array(1, 2);
> $count = count($array);
> for ($i = 0; $i < $count; $i++) {
>     echo "\nChecking $i: \n";
>     echo "Bad: " . $array['$i'] . "\n";
>     echo "Good: " . $array[$i] . "\n";
>     echo "Bad: {$array['$i']}\n";
>     echo "Good: {$array[$i]}\n";
> }
> ?>
> ```
>
> The above example will output:
>
>     Checking 0: 
>     Notice: Undefined index:  $i in /path/to/script.html on line 9
>     Bad: 
>     Good: 1
>     Notice: Undefined index:  $i in /path/to/script.html on line 11
>     Bad: 
>     Good: 1
>
>     Checking 1: 
>     Notice: Undefined index:  $i in /path/to/script.html on line 9
>     Bad: 
>     Good: 2
>     Notice: Undefined index:  $i in /path/to/script.html on line 11
>     Bad: 
>     Good: 2

More examples to demonstrate this behaviour:

``` php
<?php
// Show all errors
error_reporting(E_ALL);

$arr = array('fruit' => 'apple', 'veggie' => 'carrot');

// Correct
print $arr['fruit'];  // apple
print $arr['veggie']; // carrot

// Incorrect.  This works but also throws a PHP error of level E_NOTICE because
// of an undefined constant named fruit
// 
// Notice: Use of undefined constant fruit - assumed 'fruit' in...
print $arr[fruit];    // apple

// This defines a constant to demonstrate what's going on.  The value 'veggie'
// is assigned to a constant named fruit.
define('fruit', 'veggie');

// Notice the difference now
print $arr['fruit'];  // apple
print $arr[fruit];    // carrot

// The following is okay, as it's inside a string. Constants are not looked for
// within strings, so no E_NOTICE occurs here
print "Hello $arr[fruit]";      // Hello apple

// With one exception: braces surrounding arrays within strings allows constants
// to be interpreted
print "Hello {$arr[fruit]}";    // Hello carrot
print "Hello {$arr['fruit']}";  // Hello apple

// This will not work, and will result in a parse error, such as:
// Parse error: parse error, expecting T_STRING' or T_VARIABLE' or T_NUM_STRING'
// This of course applies to using superglobals in strings as well
print "Hello $arr['fruit']";
print "Hello $_GET['foo']";

// Concatenation is another option
print "Hello " . $arr['fruit']; // Hello apple
?>
```

When
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
is set to show **`E_NOTICE`** level errors (by setting it to
**`E_ALL`**, for example), such uses will become immediately visible. By
default,
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
is set not to show notices.

As stated in the
<a href="/language/types/array.html#language.types.array.syntax" class="link">syntax</a>
section, what's inside the square brackets ('*\[*' and '*\]*') must be
an expression. This means that code like this works:

``` php
<?php
echo $arr[somefunc($bar)];
?>
```

This is an example of using a function return value as the array index.
PHP also knows about constants:

``` php
<?php
$error_descriptions[E_ERROR]   = "A fatal error has occurred";
$error_descriptions[E_WARNING] = "PHP issued a warning";
$error_descriptions[E_NOTICE]  = "This is just an informal notice";
?>
```

Note that **`E_ERROR`** is also a valid identifier, just like *bar* in
the first example. But the last example is in fact the same as writing:

``` php
<?php
$error_descriptions[1] = "A fatal error has occurred";
$error_descriptions[2] = "PHP issued a warning";
$error_descriptions[8] = "This is just an informal notice";
?>
```

because **`E_ERROR`** equals *1*, etc.

##### So why is it bad then?

At some point in the future, the PHP team might want to add another
constant or keyword, or a constant in other code may interfere. For
example, it is already wrong to use the words *empty* and *default* this
way, since they are
<a href="/reserved.html" class="link">reserved keywords</a>.

> **Note**: <span class="simpara"> To reiterate, inside a double-quoted
> <span class="type">string</span>, it's valid to not surround array
> indexes with quotes so *"$foo\[bar\]"* is valid. See the above
> examples for details on why as well as the section on
> <a href="/language/types/string.html#language.types.string.parsing" class="link">variable parsing in strings</a>.
> </span>

### Converting to array

For any of the types <span class="type">int</span>, <span
class="type">float</span>, <span class="type">string</span>, <span
class="type">bool</span> and <span class="type">resource</span>,
converting a value to an <span class="type">array</span> results in an
array with a single element with index zero and the value of the scalar
which was converted. In other words, *(array)$scalarValue* is exactly
the same as *array($scalarValue)*.

If an <span class="type">object</span> is converted to an <span
class="type">array</span>, the result is an <span
class="type">array</span> whose elements are the <span
class="type">object</span>'s properties. The keys are the member
variable names, with a few notable exceptions: integer properties are
unaccessible; private variables have the class name prepended to the
variable name; protected variables have a '\*' prepended to the variable
name. These prepended values have null bytes on either side. This can
result in some unexpected behaviour:

``` php
<?php

class A {
    private $A; // This will become '\0A\0A'
}

class B extends A {
    private $A; // This will become '\0B\0A'
    public $AA; // This will become 'AA'
}

var_dump((array) new B());
?>
```

The above will appear to have two keys named 'AA', although one of them
is actually named '\\0A\\0A'.

Converting **`NULL`** to an <span class="type">array</span> results in
an empty <span class="type">array</span>.

### Comparing

It is possible to compare arrays with the <span
class="function">array\_diff</span> function and with
<a href="/language/operators/array.html" class="link">array operators</a>.

### Examples

The array type in PHP is very versatile. Here are some examples:

``` php
<?php
// This:
$a = array( 'color' => 'red',
            'taste' => 'sweet',
            'shape' => 'round',
            'name'  => 'apple',
            4        // key will be 0
          );

$b = array('a', 'b', 'c');

// . . .is completely equivalent with this:
$a = array();
$a['color'] = 'red';
$a['taste'] = 'sweet';
$a['shape'] = 'round';
$a['name']  = 'apple';
$a[]        = 4;        // key will be 0

$b = array();
$b[] = 'a';
$b[] = 'b';
$b[] = 'c';

// After the above code is executed, $a will be the array
// array('color' => 'red', 'taste' => 'sweet', 'shape' => 'round', 
// 'name' => 'apple', 0 => 4), and $b will be the array 
// array(0 => 'a', 1 => 'b', 2 => 'c'), or simply array('a', 'b', 'c').
?>
```

**Example \#8 Using array()**

``` php
<?php
// Array as (property-)map
$map = array( 'version'    => 4,
              'OS'         => 'Linux',
              'lang'       => 'english',
              'short_tags' => true
            );
            
// strictly numerical keys
$array = array( 7,
                8,
                0,
                156,
                -10
              );
// this is the same as array(0 => 7, 1 => 8, ...)

$switching = array(         10, // key = 0
                    5    =>  6,
                    3    =>  7, 
                    'a'  =>  4,
                            11, // key = 6 (maximum of integer-indices was 5)
                    '8'  =>  2, // key = 8 (integer!)
                    '02' => 77, // key = '02'
                    0    => 12  // the value 10 will be overwritten by 12
                  );
                  
// empty array
$empty = array();         
?>
```

**Example \#9 Collection**

``` php
<?php
$colors = array('red', 'blue', 'green', 'yellow');

foreach ($colors as $color) {
    echo "Do you like $color?\n";
}

?>
```

The above example will output:

    Do you like red?
    Do you like blue?
    Do you like green?
    Do you like yellow?

Changing the values of the <span class="type">array</span> directly is
possible by passing them by reference.

**Example \#10 Changing element in the loop**

``` php
<?php
foreach ($colors as &$color) {
    $color = strtoupper($color);
}
unset($color); /* ensure that following writes to
$color will not modify the last array element */

print_r($colors);
?>
```

The above example will output:

    Array
    (
        [0] => RED
        [1] => BLUE
        [2] => GREEN
        [3] => YELLOW
    )

This example creates a one-based array.

**Example \#11 One-based index**

``` php
<?php
$firstquarter  = array(1 => 'January', 'February', 'March');
print_r($firstquarter);
?>
```

The above example will output:

    Array 
    (
        [1] => 'January'
        [2] => 'February'
        [3] => 'March'
    )

**Example \#12 Filling an array**

``` php
<?php
// fill an array with all items from a directory
$handle = opendir('.');
while (false !== ($file = readdir($handle))) {
    $files[] = $file;
}
closedir($handle); 
?>
```

<span class="type">Array</span>s are ordered. The order can be changed
using various sorting functions. See the
<a href="/ref/array.html" class="link">array functions</a> section for
more information. The <span class="function">count</span> function can
be used to count the number of items in an <span
class="type">array</span>.

**Example \#13 Sorting an array**

``` php
<?php
sort($files);
print_r($files);
?>
```

Because the value of an <span class="type">array</span> can be anything,
it can also be another <span class="type">array</span>. This enables the
creation of recursive and multi-dimensional <span
class="type">array</span>s.

**Example \#14 Recursive and multi-dimensional arrays**

``` php
<?php
$fruits = array ( "fruits"  => array ( "a" => "orange",
                                       "b" => "banana",
                                       "c" => "apple"
                                     ),
                  "numbers" => array ( 1,
                                       2,
                                       3,
                                       4,
                                       5,
                                       6
                                     ),
                  "holes"   => array (      "first",
                                       5 => "second",
                                            "third"
                                     )
                );

// Some examples to address values in the array above 
echo $fruits["holes"][5];    // prints "second"
echo $fruits["fruits"]["a"]; // prints "orange"
unset($fruits["holes"][0]);  // remove "first"

// Create a new multi-dimensional array
$juices["apple"]["green"] = "good"; 
?>
```

<span class="type">Array</span> assignment always involves value
copying. Use the
<a href="/language/operators.html" class="link">reference operator</a>
to copy an <span class="type">array</span> by reference.

``` php
<?php
$arr1 = array(2, 3);
$arr2 = $arr1;
$arr2[] = 4; // $arr2 is changed,
             // $arr1 is still array(2, 3)
             
$arr3 = &$arr1;
$arr3[] = 4; // now $arr1 and $arr3 are the same
?>
```

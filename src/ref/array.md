See also <span class="function">is\_array</span>, <span
class="function">explode</span>, <span class="function">implode</span>,
<span class="function">split</span>, <span
class="function">preg\_split</span>, and <span
class="function">unset</span>.

array\_change\_key\_case
========================

Changes the case of all keys in an array

### Description

<span class="type">array</span> <span
class="methodname">array\_change\_key\_case</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> \[,
<span class="methodparam"><span class="type">int</span> `$case`<span
class="initializer"> = CASE\_LOWER</span></span> \] )

Returns an array with all keys from `array` lowercased or uppercased.
Numbered indices are left as is.

### Parameters

`array`  
The array to work on

`case`  
Either **`CASE_UPPER`** or **`CASE_LOWER`** (default)

### Return Values

Returns an array with its keys lower or uppercased, or **`FALSE`** if
`array` is not an array.

### Errors/Exceptions

Throws **`E_WARNING`** if `array` is not an array.

### Examples

**Example \#1 <span class="function">array\_change\_key\_case</span>
example**

``` php
<?php
$input_array = array("FirSt" => 1, "SecOnd" => 4);
print_r(array_change_key_case($input_array, CASE_UPPER));
?>
```

The above example will output:

    Array
    (
        [FIRST] => 1
        [SECOND] => 4
    )

### Notes

> **Note**:
>
> If an array has indices that will be the same once run through this
> function (e.g. "*keY*" and "*kEY*"), the value that is later in the
> array will override other indices.

array\_chunk
============

Split an array into chunks

### Description

<span class="type">array</span> <span
class="methodname">array\_chunk</span> ( <span class="methodparam"><span
class="type">array</span> `$array`</span> , <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$preserve_keys`<span class="initializer"> = **`FALSE`**</span></span>
\] )

Chunks an array into arrays with `size` elements. The last chunk may
contain less than `size` elements.

### Parameters

`array`  
The array to work on

`size`  
The size of each chunk

`preserve_keys`  
When set to **`TRUE`** keys will be preserved. Default is **`FALSE`**
which will reindex the chunk numerically

### Return Values

Returns a multidimensional numerically indexed array, starting with
zero, with each dimension containing `size` elements.

### Errors/Exceptions

If `size` is less than 1 **`E_WARNING`** will be thrown and **`NULL`**
returned.

### Examples

**Example \#1 <span class="function">array\_chunk</span> example**

``` php
<?php
$input_array = array('a', 'b', 'c', 'd', 'e');
print_r(array_chunk($input_array, 2));
print_r(array_chunk($input_array, 2, true));
?>
```

The above example will output:

    Array
    (
        [0] => Array
            (
                [0] => a
                [1] => b
            )

        [1] => Array
            (
                [0] => c
                [1] => d
            )

        [2] => Array
            (
                [0] => e
            )

    )
    Array
    (
        [0] => Array
            (
                [0] => a
                [1] => b
            )

        [1] => Array
            (
                [2] => c
                [3] => d
            )

        [2] => Array
            (
                [4] => e
            )

    )

### See Also

-   <span class="function">array\_slice</span>

array\_column
=============

Return the values from a single column in the input array

### Description

<span class="type">array</span> <span
class="methodname">array\_column</span> ( <span
class="methodparam"><span class="type">array</span> `$input`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$column_key`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$index_key`<span class="initializer"> =
**`NULL`**</span></span> \] )

<span class="function">array\_column</span> returns the values from a
single column of the `input`, identified by the `column_key`.
Optionally, an `index_key` may be provided to index the values in the
returned array by the values from the `index_key` column of the input
array.

### Parameters

`input`  
A multi-dimensional array or an array of objects from which to pull a
column of values from. If an array of objects is provided, then public
properties can be directly pulled. In order for protected or private
properties to be pulled, the class must implement both the <span
class="function">\_\_get</span> and <span
class="function">\_\_isset</span> magic methods.

`column_key`  
The column of values to return. This value may be an integer key of the
column you wish to retrieve, or it may be a string key name for an
associative array or property name. It may also be **`NULL`** to return
complete arrays or objects (this is useful together with `index_key` to
reindex the array).

`index_key`  
The column to use as the index/keys for the returned array. This value
may be the integer key of the column, or it may be the string key name.
The value is
<a href="/language/types/array.html#language.types.array.key-casts" class="link">cast</a>
as usual for array keys (however, objects supporting conversion to
string are also allowed).

### Return Values

Returns an array of values representing a single column from the input
array.

### Changelog

| Version | Description                                                            |
|---------|------------------------------------------------------------------------|
| 7.0.0   | Added the ability for the `input` parameter to be an array of objects. |

### Examples

**Example \#1 Get the column of first names from a recordset**

``` php
<?php
// Array representing a possible record set returned from a database
$records = array(
    array(
        'id' => 2135,
        'first_name' => 'John',
        'last_name' => 'Doe',
    ),
    array(
        'id' => 3245,
        'first_name' => 'Sally',
        'last_name' => 'Smith',
    ),
    array(
        'id' => 5342,
        'first_name' => 'Jane',
        'last_name' => 'Jones',
    ),
    array(
        'id' => 5623,
        'first_name' => 'Peter',
        'last_name' => 'Doe',
    )
);
 
$first_names = array_column($records, 'first_name');
print_r($first_names);
?>
```

The above example will output:

    Array
    (
        [0] => John
        [1] => Sally
        [2] => Jane
        [3] => Peter
    )

**Example \#2 Get the column of last names from a recordset, indexed by
the "id" column**

``` php
<?php
// Using the $records array from Example #1
$last_names = array_column($records, 'last_name', 'id');
print_r($last_names);
?>
```

The above example will output:

    Array
    (
        [2135] => Doe
        [3245] => Smith
        [5342] => Jones
        [5623] => Doe
    )

**Example \#3 Get the column of usernames from the public "username"
property of an object**

``` php
<?php

class User
{
    public $username;

    public function __construct(string $username)
    {
        $this->username = $username;
    }
}

$users = [
    new User('user 1'),
    new User('user 2'),
    new User('user 3'),
];

print_r(array_column($users, 'username'));
?>
```

The above example will output:

    Array
    (
        [0] => user 1
        [1] => user 2
        [2] => user 3
    )

**Example \#4 Get the column of names from the private "name" property
of an object using the magic <span class="function">\_\_get</span>
method.**

``` php
<?php

class Person
{
    private $name;

    public function __construct(string $name)
    {
        $this->name = $name;
    }

    public function __get($prop)
    {
        return $this->$prop;
    }

    public function __isset($prop) : bool
    {
        return isset($this->$prop);
    }
}

$people = [
    new Person('Fred'),
    new Person('Jane'),
    new Person('John'),
];

print_r(array_column($people, 'name'));
?>
```

The above example will output:

    Array
    (
        [0] => Fred
        [1] => Jane
        [2] => John
    )

If <span class="function">\_\_isset</span> is not provided, then an
empty array will be returned.

### See Also

-   <a href="https://github.com/ramsey/array_column/blob/master/src/array_column.php" class="link external">» Recommended userland implementation for PHP lower than 5.5</a>

array\_combine
==============

Creates an array by using one array for keys and another for its values

### Description

<span class="type">array</span> <span
class="methodname">array\_combine</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> ,
<span class="methodparam"><span class="type">array</span>
`$values`</span> )

Creates an <span class="type">array</span> by using the values from the
`keys` array as keys and the values from the `values` array as the
corresponding values.

### Parameters

`keys`  
Array of keys to be used. Illegal values for key will be converted to
<span class="type">string</span>.

`values`  
<span class="type">Array</span> of values to be used

### Return Values

Returns the combined <span class="type">array</span>, **`FALSE`** if the
number of elements for each array isn't equal.

### Errors/Exceptions

Throws **`E_WARNING`** if the number of elements in `keys` and `values`
does not match.

### Changelog

| Version | Description                                                                         |
|---------|-------------------------------------------------------------------------------------|
| 5.4.0   | Previous versions issued **`E_WARNING`** and returned **`FALSE`** for empty arrays. |

### Examples

**Example \#1 A simple <span class="function">array\_combine</span>
example**

``` php
<?php
$a = array('green', 'red', 'yellow');
$b = array('avocado', 'apple', 'banana');
$c = array_combine($a, $b);

print_r($c);
?>
```

The above example will output:

    Array
    (
        [green]  => avocado
        [red]    => apple
        [yellow] => banana
    )

### See Also

-   <span class="function">array\_merge</span>
-   <span class="function">array\_walk</span>
-   <span class="function">array\_values</span>

array\_count\_values
====================

Counts all the values of an array

### Description

<span class="type">array</span> <span
class="methodname">array\_count\_values</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

<span class="function">array\_count\_values</span> returns an array
using the values of `array` as keys and their frequency in `array` as
values.

### Parameters

`array`  
The array of values to count

### Return Values

Returns an associative array of values from `array` as keys and their
count as value.

### Errors/Exceptions

Throws **`E_WARNING`** for every element which is not <span
class="type">string</span> or <span class="type">integer</span>.

### Examples

**Example \#1 <span class="function">array\_count\_values</span>
example**

``` php
<?php
$array = array(1, "hello", 1, "world", "hello");
print_r(array_count_values($array));
?>
```

The above example will output:

    Array
    (
        [1] => 2
        [hello] => 2
        [world] => 1
    )

### See Also

-   <span class="function">count</span>
-   <span class="function">array\_unique</span>
-   <span class="function">array\_values</span>
-   <span class="function">count\_chars</span>

array\_diff\_assoc
==================

Computes the difference of arrays with additional index check

### Description

<span class="type">array</span> <span
class="methodname">array\_diff\_assoc</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \] )

Compares `array1` against `array2` and returns the difference. Unlike
<span class="function">array\_diff</span> the array keys are also used
in the comparison.

### Parameters

`array1`  
The array to compare from

`array2`  
An array to compare against

`...`  
More arrays to compare against

### Return Values

Returns an <span class="type">array</span> containing all the values
from `array1` that are not present in any of the other arrays.

### Examples

**Example \#1 <span class="function">array\_diff\_assoc</span> example**

In this example you see the *"a" =\> "green"* pair is present in both
arrays and thus it is not in the output from the function. Unlike this,
the pair *0 =\> "red"* is in the output because in the second argument
*"red"* has key which is *1*.

``` php
<?php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "yellow", "red");
$result = array_diff_assoc($array1, $array2);
print_r($result);
?>
```

The above example will output:

    Array
    (
        [b] => brown
        [c] => blue
        [0] => red
    )

**Example \#2 <span class="function">array\_diff\_assoc</span> example**

Two values from *key =\> value* pairs are considered equal only if
*(string) $elem1 === (string) $elem2* . In other words a strict check
takes place so the string representations must be the same.

``` php
<?php
$array1 = array(0, 1, 2);
$array2 = array("00", "01", "2");
$result = array_diff_assoc($array1, $array2);
print_r($result);
?>
```

The above example will output:

    Array
    (
        [0] => 0
        [1] => 1
        )

### Notes

> **Note**: <span class="simpara"> This function only checks one
> dimension of a n-dimensional array. Of course you can check deeper
> dimensions by using, for example, *array\_diff\_assoc($array1\[0\],
> $array2\[0\]);*. </span>

> **Note**: <span class="simpara"> Ensure you pass arguments in the
> correct order when comparing similar arrays with more keys. The new
> array should be the first in the list. </span>

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_diff\_uassoc</span>
-   <span class="function">array\_udiff\_assoc</span>
-   <span class="function">array\_udiff\_uassoc</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>

array\_diff\_key
================

Computes the difference of arrays using keys for comparison

### Description

<span class="type">array</span> <span
class="methodname">array\_diff\_key</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \] )

Compares the keys from `array1` against the keys from `array2` and
returns the difference. This function is like <span
class="function">array\_diff</span> except the comparison is done on the
keys instead of the values.

### Parameters

`array1`  
The array to compare from

`array2`  
An array to compare against

`...`  
More arrays to compare against

### Return Values

Returns an <span class="type">array</span> containing all the entries
from `array1` whose keys are absent from all of the other arrays.

### Examples

**Example \#1 <span class="function">array\_diff\_key</span> example**

The two keys from the *key =\> value* pairs are considered equal only if
*(string) $key1 === (string) $key2* . In other words a strict type check
is executed so the string representation must be the same.

``` php
<?php
$array1 = array('blue' => 1, 'red' => 2, 'green' => 3, 'purple' => 4);
$array2 = array('green' => 5, 'yellow' => 7, 'cyan' => 8);

var_dump(array_diff_key($array1, $array2));
?>
```

The above example will output:

    array(3) {
      ["blue"]=>
      int(1)
      ["red"]=>
      int(2)
      ["purple"]=>
      int(4)
    }

``` php
<?php
$array1 = array('blue' => 1, 'red'  => 2, 'green' => 3, 'purple' => 4);
$array2 = array('green' => 5, 'yellow' => 7, 'cyan' => 8);
$array3 = array('blue' => 6, 'yellow' => 7, 'mauve' => 8);

var_dump(array_diff_key($array1, $array2, $array3));
?>
```

The above example will output:

    array(2) {
      ["red"]=>
      int(2)
      ["purple"]=>
      int(4)
    }

### Notes

> **Note**:
>
> This function only checks one dimension of a n-dimensional array. Of
> course you can check deeper dimensions by using
> *array\_diff\_key($array1\[0\], $array2\[0\]);*.

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_udiff</span>
-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_diff\_uassoc</span>
-   <span class="function">array\_udiff\_assoc</span>
-   <span class="function">array\_udiff\_uassoc</span>
-   <span class="function">array\_diff\_ukey</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_intersect\_uassoc</span>
-   <span class="function">array\_intersect\_key</span>
-   <span class="function">array\_intersect\_ukey</span>

array\_diff\_uassoc
===================

Computes the difference of arrays with additional index check which is
performed by a user supplied callback function

### Description

<span class="type">array</span> <span
class="methodname">array\_diff\_uassoc</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$key_compare_func`</span> )

Compares `array1` against `array2` and returns the difference. Unlike
<span class="function">array\_diff</span> the array keys are used in the
comparison.

Unlike <span class="function">array\_diff\_assoc</span> a user supplied
callback function is used for the indices comparison, not internal
function.

### Parameters

`array1`  
The array to compare from

`array2`  
An array to compare against

`...`  
More arrays to compare against

`key_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

Returns an <span class="type">array</span> containing all the entries
from `array1` that are not present in any of the other arrays.

### Examples

**Example \#1 <span class="function">array\_diff\_uassoc</span>
example**

The *"a" =\> "green"* pair is present in both arrays and thus it is not
in the output from the function. Unlike this, the pair *0 =\> "red"* is
in the output because in the second argument *"red"* has key which is
*1*.

``` php
<?php
function key_compare_func($a, $b)
{
    if ($a === $b) {
        return 0;
    }
    return ($a > $b)? 1:-1;
}

$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "yellow", "red");
$result = array_diff_uassoc($array1, $array2, "key_compare_func");
print_r($result);
?>
```

The above example will output:

    Array
    (
        [b] => brown
        [c] => blue
        [0] => red
    )

The equality of 2 indices is checked by the user supplied callback
function.

### Notes

> **Note**:
>
> This function only checks one dimension of a n-dimensional array. Of
> course you can check deeper dimensions by using, for example,
> *array\_diff\_uassoc($array1\[0\], $array2\[0\],
> "key\_compare\_func");*.

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_udiff</span>
-   <span class="function">array\_udiff\_assoc</span>
-   <span class="function">array\_udiff\_uassoc</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_uintersect</span>
-   <span class="function">array\_uintersect\_assoc</span>
-   <span class="function">array\_uintersect\_uassoc</span>

array\_diff\_ukey
=================

Computes the difference of arrays using a callback function on the keys
for comparison

### Description

<span class="type">array</span> <span
class="methodname">array\_diff\_ukey</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$key_compare_func`</span> )

Compares the keys from `array1` against the keys from `array2` and
returns the difference. This function is like <span
class="function">array\_diff</span> except the comparison is done on the
keys instead of the values.

Unlike <span class="function">array\_diff\_key</span> a user supplied
callback function is used for the indices comparison, not internal
function.

### Parameters

`array1`  
The array to compare from

`array2`  
An array to compare against

`...`  
More arrays to compare against

`key_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

Returns an <span class="type">array</span> containing all the entries
from `array1` that are not present in any of the other arrays.

### Examples

**Example \#1 <span class="function">array\_diff\_ukey</span> example**

``` php
<?php
function key_compare_func($key1, $key2)
{
    if ($key1 == $key2)
        return 0;
    else if ($key1 > $key2)
        return 1;
    else
        return -1;
}

$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);

var_dump(array_diff_ukey($array1, $array2, 'key_compare_func'));
?>
```

The above example will output:

    array(2) {
      ["red"]=>
      int(2)
      ["purple"]=>
      int(4)
    }

### Notes

> **Note**:
>
> This function only checks one dimension of a n-dimensional array. Of
> course you can check deeper dimensions by using
> *array\_diff\_ukey($array1\[0\], $array2\[0\], 'callback\_func');*.

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_udiff</span>
-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_diff\_uassoc</span>
-   <span class="function">array\_udiff\_assoc</span>
-   <span class="function">array\_udiff\_uassoc</span>
-   <span class="function">array\_diff\_key</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_intersect\_uassoc</span>
-   <span class="function">array\_intersect\_key</span>
-   <span class="function">array\_intersect\_ukey</span>

array\_diff
===========

Computes the difference of arrays

### Description

<span class="type">array</span> <span
class="methodname">array\_diff</span> ( <span class="methodparam"><span
class="type">array</span> `$array1`</span> , <span
class="methodparam"><span class="type">array</span> `$array2`</span> \[,
<span class="methodparam"><span class="type">array</span> `$...`</span>
\] )

Compares `array1` against one or more other arrays and returns the
values in `array1` that are not present in any of the other arrays.

### Parameters

`array1`  
The array to compare from

`array2`  
An array to compare against

`...`  
More arrays to compare against

### Return Values

Returns an <span class="type">array</span> containing all the entries
from `array1` that are not present in any of the other arrays.

### Examples

**Example \#1 <span class="function">array\_diff</span> example**

``` php
<?php
$array1 = array("a" => "green", "red", "blue", "red");
$array2 = array("b" => "green", "yellow", "red");
$result = array_diff($array1, $array2);

print_r($result);
?>
```

Multiple occurrences in `$array1` are all treated the same way. This
will output :

    Array
    (
        [1] => blue
    )

### Notes

> **Note**:
>
> Two elements are considered equal if and only if *(string) $elem1 ===
> (string) $elem2*. In other words: when the string representation is
> the same.

> **Note**:
>
> This function only checks one dimension of a n-dimensional array. Of
> course you can check deeper dimensions by using
> *array\_diff($array1\[0\], $array2\[0\]);*.

### See Also

-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>

array\_fill\_keys
=================

Fill an array with values, specifying keys

### Description

<span class="type">array</span> <span
class="methodname">array\_fill\_keys</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

Fills an array with the value of the `value` parameter, using the values
of the `keys` array as keys.

### Parameters

`keys`  
Array of values that will be used as keys. Illegal values for key will
be converted to <span class="type">string</span>.

`value`  
Value to use for filling

### Return Values

Returns the filled array

### Examples

**Example \#1 <span class="function">array\_fill\_keys</span> example**

``` php
<?php
$keys = array('foo', 5, 10, 'bar');
$a = array_fill_keys($keys, 'banana');
print_r($a);
?>
```

The above example will output:

    Array
    (
        [foo] => banana
        [5] => banana
        [10] => banana
        [bar] => banana
    )

### See Also

-   <span class="function">array\_fill</span>
-   <span class="function">array\_combine</span>

array\_fill
===========

Fill an array with values

### Description

<span class="type">array</span> <span
class="methodname">array\_fill</span> ( <span class="methodparam"><span
class="type">int</span> `$start_index`</span> , <span
class="methodparam"><span class="type">int</span> `$num`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Fills an array with `num` entries of the value of the `value` parameter,
keys starting at the `start_index` parameter.

### Parameters

`start_index`  
The first index of the returned array.

If `start_index` is negative, the first index of the returned array will
be `start_index` and the following indices will start from zero (see
<a href="/ref/array.html#array_fill%20example" class="link">example</a>).

`num`  
Number of elements to insert. Must be greater than or equal to zero.

`value`  
Value to use for filling

### Return Values

Returns the filled array

### Errors/Exceptions

Throws a **`E_WARNING`** if `num` is less than zero.

### Changelog

| Version | Description                                                                    |
|---------|--------------------------------------------------------------------------------|
| 5.6.0   | `num` may now be zero. Previously, `num` was required to be greater than zero. |

### Examples

**Example \#1 <span class="function">array\_fill</span> example**

``` php
<?php
$a = array_fill(5, 6, 'banana');
$b = array_fill(-2, 4, 'pear');
print_r($a);
print_r($b);
?>
```

The above example will output:

    Array
    (
        [5]  => banana
        [6]  => banana
        [7]  => banana
        [8]  => banana
        [9]  => banana
        [10] => banana
    )
    Array
    (
        [-2] => pear
        [0] => pear
        [1] => pear
        [2] => pear
    )

### Notes

See also the
<a href="/language/types/array.html" class="link">Arrays</a> section of
manual for a detailed explanation of negative keys.

### See Also

-   <span class="function">array\_fill\_keys</span>
-   <span class="function">str\_repeat</span>
-   <span class="function">range</span>

array\_filter
=============

Filters elements of an array using a callback function

### Description

<span class="type">array</span> <span
class="methodname">array\_filter</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> \[,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flag`<span class="initializer"> =
0</span></span> \]\] )

Iterates over each value in the `array` passing them to the `callback`
function. If the `callback` function returns **`TRUE`**, the current
value from `array` is returned into the result <span
class="type">array</span>. Array keys are preserved.

### Parameters

`array`  
The array to iterate over

`callback`  
The callback function to use

If no `callback` is supplied, all entries of `array` equal to
**`FALSE`** (see
<a href="/language/types/boolean.html#language.types.boolean.casting" class="link">converting to boolean</a>)
will be removed.

`flag`  
Flag determining what arguments are sent to `callback`:

-   <span class="simpara">**`ARRAY_FILTER_USE_KEY`** - pass key as the
    only argument to `callback` instead of the value</span>
-   <span class="simpara">**`ARRAY_FILTER_USE_BOTH`** - pass both value
    and key as arguments to `callback` instead of the value</span>

Default is *0* which will pass value as the only argument to `callback`
instead.

### Return Values

Returns the filtered array.

### Changelog

| Version | Description                                                                                              |
|---------|----------------------------------------------------------------------------------------------------------|
| 5.6.0   | Added optional `flag` parameter and constants **`ARRAY_FILTER_USE_KEY`** and **`ARRAY_FILTER_USE_BOTH`** |

### Examples

**Example \#1 <span class="function">array\_filter</span> example**

``` php
<?php
function odd($var)
{
    // returns whether the input integer is odd
    return $var & 1;
}

function even($var)
{
    // returns whether the input integer is even
    return !($var & 1);
}

$array1 = ['a' => 1, 'b' => 2, 'c' => 3, 'd' => 4, 'e' => 5];
$array2 = [6, 7, 8, 9, 10, 11, 12];

echo "Odd :\n";
print_r(array_filter($array1, "odd"));
echo "Even:\n";
print_r(array_filter($array2, "even"));
?>
```

The above example will output:

    Odd :
    Array
    (
        [a] => 1
        [c] => 3
        [e] => 5
    )
    Even:
    Array
    (
        [0] => 6
        [2] => 8
        [4] => 10
        [6] => 12
    )

**Example \#2 <span class="function">array\_filter</span> without
`callback`**

``` php
<?php

$entry = [
    0 => 'foo',
    1 => false,
    2 => -1,
    3 => null,
    4 => '',
    5 => '0',
    6 => 0,
];

print_r(array_filter($entry));
?>
```

The above example will output:

    Array
    (
        [0] => foo
        [2] => -1
    )

**Example \#3 <span class="function">array\_filter</span> with `flag`**

``` php
<?php

$arr = ['a' => 1, 'b' => 2, 'c' => 3, 'd' => 4];

var_dump(array_filter($arr, function($k) {
    return $k == 'b';
}, ARRAY_FILTER_USE_KEY));

var_dump(array_filter($arr, function($v, $k) {
    return $k == 'b' || $v == 4;
}, ARRAY_FILTER_USE_BOTH));
?>
```

The above example will output:

    array(1) {
      ["b"]=>
      int(2)
    }
    array(2) {
      ["b"]=>
      int(2)
      ["d"]=>
      int(4)
    }

### Notes

**Caution**

If the array is changed from the callback function (e.g. element added,
deleted or unset) the behavior of this function is undefined.

### See Also

-   <span class="function">array\_map</span>
-   <span class="function">array\_reduce</span>
-   <span class="function">array\_walk</span>

array\_flip
===========

Exchanges all keys with their associated values in an array

### Description

<span class="type">array</span> <span
class="methodname">array\_flip</span> ( <span class="methodparam"><span
class="type">array</span> `$array`</span> )

<span class="function">array\_flip</span> returns an <span
class="type">array</span> in flip order, i.e. keys from `array` become
values and values from `array` become keys.

Note that the values of `array` need to be valid keys, i.e. they need to
be either <span class="type">integer</span> or <span
class="type">string</span>. A warning will be emitted if a value has the
wrong type, and the key/value pair in question *will not be included in
the result*.

If a value has several occurrences, the latest key will be used as its
value, and all others will be lost.

### Parameters

`array`  
An array of key/value pairs to be flipped.

### Return Values

Returns the flipped array on success and **`NULL`** on failure.

### Examples

**Example \#1 <span class="function">array\_flip</span> example**

``` php
<?php
$input = array("oranges", "apples", "pears");
$flipped = array_flip($input);

print_r($flipped);
?>
```

The above example will output:

    Array
    (
        [oranges] => 0
        [apples] => 1
        [pears] => 2
    )

**Example \#2 <span class="function">array\_flip</span> example :
collision**

``` php
<?php
$input = array("a" => 1, "b" => 1, "c" => 2);
$flipped = array_flip($input);

print_r($flipped);
?>
```

The above example will output:

    Array
    (
        [1] => b
        [2] => c
    )

### See Also

-   <span class="function">array\_values</span>
-   <span class="function">array\_keys</span>
-   <span class="function">array\_reverse</span>

array\_intersect\_assoc
=======================

Computes the intersection of arrays with additional index check

### Description

<span class="type">array</span> <span
class="methodname">array\_intersect\_assoc</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \] )

<span class="function">array\_intersect\_assoc</span> returns an array
containing all the values of `array1` that are present in all the
arguments. Note that the keys are also used in the comparison unlike in
<span class="function">array\_intersect</span>.

### Parameters

`array1`  
The array with master values to check.

`array2`  
An array to compare values against.

`...`  
A variable list of arrays to compare.

### Return Values

Returns an associative array containing all the values in `array1` that
are present in all of the arguments.

### Examples

**Example \#1 <span class="function">array\_intersect\_assoc</span>
example**

``` php
<?php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "green", "b" => "yellow", "blue", "red");
$result_array = array_intersect_assoc($array1, $array2);
print_r($result_array);
?>
```

The above example will output:

    Array
    (
        [a] => green
    )

In our example you see that only the pair *"a" =\> "green"* is present
in both arrays and thus is returned. The value *"red"* is not returned
because in `$array1` its key is *0* while the key of "red" in `$array2`
is *1*, and the key *"b"* is not returned because its values are
different in each array.

The two values from the *key =\> value* pairs are considered equal only
if *(string) $elem1 === (string) $elem2* . In other words a strict type
check is executed so the string representation must be the same.

### See Also

-   <span class="function">array\_intersect</span>
-   <span class="function">array\_uintersect\_assoc</span>
-   <span class="function">array\_intersect\_uassoc</span>
-   <span class="function">array\_uintersect\_uassoc</span>
-   <span class="function">array\_diff</span>
-   <span class="function">array\_diff\_assoc</span>

array\_intersect\_key
=====================

Computes the intersection of arrays using keys for comparison

### Description

<span class="type">array</span> <span
class="methodname">array\_intersect\_key</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \] )

<span class="function">array\_intersect\_key</span> returns an array
containing all the entries of `array1` which have keys that are present
in all the arguments.

### Parameters

`array1`  
The array with master keys to check.

`array2`  
An array to compare keys against.

`...`  
A variable list of arrays to compare.

### Return Values

Returns an associative array containing all the entries of `array1`
which have keys that are present in all arguments.

### Examples

**Example \#1 <span class="function">array\_intersect\_key</span>
example**

``` php
<?php
$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);

var_dump(array_intersect_key($array1, $array2));
?>
```

The above example will output:

    array(2) {
      ["blue"]=>
      int(1)
      ["green"]=>
      int(3)
    }

In our example you see that only the keys *'blue'* and *'green'* are
present in both arrays and thus returned. Also notice that the values
for the keys *'blue'* and *'green'* differ between the two arrays. A
match still occurs because only the keys are checked. The values
returned are those of `array1`.

The two keys from the *key =\> value* pairs are considered equal only if
*(string) $key1 === (string) $key2* . In other words a strict type check
is executed so the string representation must be the same.

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_udiff</span>
-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_diff\_uassoc</span>
-   <span class="function">array\_udiff\_assoc</span>
-   <span class="function">array\_udiff\_uassoc</span>
-   <span class="function">array\_diff\_key</span>
-   <span class="function">array\_diff\_ukey</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_intersect\_uassoc</span>
-   <span class="function">array\_intersect\_ukey</span>

array\_intersect\_uassoc
========================

Computes the intersection of arrays with additional index check,
compares indexes by a callback function

### Description

<span class="type">array</span> <span
class="methodname">array\_intersect\_uassoc</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$key_compare_func`</span> )

<span class="function">array\_intersect\_uassoc</span> returns an array
containing all the values of `array1` that are present in all the
arguments. Note that the keys are used in the comparison unlike in <span
class="function">array\_intersect</span>.

### Parameters

`array1`  
Initial array for comparison of the arrays.

`array2`  
First array to compare keys against.

`...`  
Variable list of array arguments to compare values against.

`key_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

Returns the values of `array1` whose values exist in all of the
arguments.

### Examples

**Example \#1 <span class="function">array\_intersect\_uassoc</span>
example**

``` php
<?php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");

print_r(array_intersect_uassoc($array1, $array2, "strcasecmp"));
?>
```

The above example will output:

    Array
    (
        [b] => brown
    )

### See Also

-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_uintersect\_assoc</span>
-   <span class="function">array\_uintersect\_uassoc</span>
-   <span class="function">array\_intersect\_key</span>
-   <span class="function">array\_intersect\_ukey</span>

array\_intersect\_ukey
======================

Computes the intersection of arrays using a callback function on the
keys for comparison

### Description

<span class="type">array</span> <span
class="methodname">array\_intersect\_ukey</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$key_compare_func`</span> )

<span class="function">array\_intersect\_ukey</span> returns an array
containing all the values of `array1` which have matching keys that are
present in all the arguments.

### Parameters

`array1`  
Initial array for comparison of the arrays.

`array2`  
First array to compare keys against.

`...`  
Variable list of array arguments to compare keys against.

`key_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

Returns the values of `array1` whose keys exist in all the arguments.

### Examples

**Example \#1 <span class="function">array\_intersect\_ukey</span>
example**

``` php
<?php
function key_compare_func($key1, $key2)
{
    if ($key1 == $key2)
        return 0;
    else if ($key1 > $key2)
        return 1;
    else
        return -1;
}

$array1 = array('blue'  => 1, 'red'  => 2, 'green'  => 3, 'purple' => 4);
$array2 = array('green' => 5, 'blue' => 6, 'yellow' => 7, 'cyan'   => 8);

var_dump(array_intersect_ukey($array1, $array2, 'key_compare_func'));
?>
```

The above example will output:

    array(2) {
      ["blue"]=>
      int(1)
      ["green"]=>
      int(3)
    }

In our example you see that only the keys *'blue'* and *'green'* are
present in both arrays and thus returned. Also notice that the values
for the keys *'blue'* and *'green'* differ between the two arrays. A
match still occurs because only the keys are checked. The values
returned are those of `array1`.

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_udiff</span>
-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_diff\_uassoc</span>
-   <span class="function">array\_udiff\_assoc</span>
-   <span class="function">array\_udiff\_uassoc</span>
-   <span class="function">array\_diff\_key</span>
-   <span class="function">array\_diff\_ukey</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_intersect\_uassoc</span>
-   <span class="function">array\_intersect\_key</span>

array\_intersect
================

Computes the intersection of arrays

### Description

<span class="type">array</span> <span
class="methodname">array\_intersect</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \] )

<span class="function">array\_intersect</span> returns an array
containing all the values of `array1` that are present in all the
arguments. Note that keys are preserved.

### Parameters

`array1`  
The array with master values to check.

`array2`  
An array to compare values against.

`...`  
A variable list of arrays to compare.

### Return Values

Returns an array containing all of the values in `array1` whose values
exist in all of the parameters.

### Examples

**Example \#1 <span class="function">array\_intersect</span> example**

``` php
<?php
$array1 = array("a" => "green", "red", "blue");
$array2 = array("b" => "green", "yellow", "red");
$result = array_intersect($array1, $array2);
print_r($result);
?>
```

The above example will output:

    Array
    (
        [a] => green
        [0] => red
    )

### Notes

> **Note**: <span class="simpara"> Two elements are considered equal if
> and only if *(string) $elem1 === (string) $elem2*. In words: when the
> string representation is the same. </span>

### See Also

-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_diff</span>
-   <span class="function">array\_diff\_assoc</span>

array\_key\_exists
==================

Checks if the given key or index exists in the array

### Description

<span class="type">bool</span> <span
class="methodname">array\_key\_exists</span> ( <span
class="methodparam"><span class="type">mixed</span> `$key`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array`</span> )

<span class="function">array\_key\_exists</span> returns **`TRUE`** if
the given `key` is set in the array. `key` can be any value possible for
an array index.

### Parameters

`key`  
Value to check.

`array`  
An array with keys to check.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

> **Note**:
>
> <span class="function">array\_key\_exists</span> will search for the
> keys in the first dimension only. Nested keys in multidimensional
> arrays will not be found.

### Examples

**Example \#1 <span class="function">array\_key\_exists</span> example**

``` php
<?php
$search_array = array('first' => 1, 'second' => 4);
if (array_key_exists('first', $search_array)) {
    echo "The 'first' element is in the array";
}
?>
```

**Example \#2 <span class="function">array\_key\_exists</span> vs <span
class="function">isset</span>**

<span class="function">isset</span> does not return **`TRUE`** for array
keys that correspond to a **`NULL`** value, while <span
class="function">array\_key\_exists</span> does.

``` php
<?php
$search_array = array('first' => null, 'second' => 4);

// returns false
isset($search_array['first']);

// returns true
array_key_exists('first', $search_array);
?>
```

### Notes

> **Note**:
>
> For backward compatibility reasons, <span
> class="function">array\_key\_exists</span> will also return **`TRUE`**
> if `key` is a property defined within an <span
> class="type">object</span> given as `array`. This behaviour should not
> be relied upon, and care should be taken to ensure that `array` is an
> <span class="type">array</span>.
>
> To check whether a property exists in an object, use <span
> class="function">property\_exists</span>.

### See Also

-   <span class="function">isset</span>
-   <span class="function">array\_keys</span>
-   <span class="function">in\_array</span>
-   <span class="function">property\_exists</span>

array\_key\_first
=================

Gets the first key of an array

### Description

<span class="type">mixed</span> <span
class="methodname">array\_key\_first</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

Get the first key of the given `array` without affecting the internal
array pointer.

### Parameters

`array`  
An array.

### Return Values

Returns the first key of `array` if the array is not empty; **`NULL`**
otherwise.

### Examples

**Example \#1 Basic <span class="function">array\_key\_first</span>
Usage**

``` php
<?php
$array = ['a' => 1, 'b' => 2, 'c' => 3];

$firstKey = array_key_first($array);

var_dump($firstKey);
?>
```

The above example will output:

    string(1) "a"

### Notes

**Tip**

There are several ways to provide this functionality for versions prior
to PHP 7.3.0. It is possible to use <span
class="function">array\_keys</span>, but that may be rather inefficient.
It is also possible to use <span class="function">reset</span> and <span
class="function">key</span>, but that may change the internal array
pointer. An efficient solution, which does not change the internal array
pointer, written as polyfill:

``` php
<?php
if (!function_exists('array_key_first')) {
    function array_key_first(array $arr) {
        foreach($arr as $key => $unused) {
            return $key;
        }
        return NULL;
    }
}
?>
```

### See Also

-   <span class="function">array\_key\_last</span>
-   <span class="function">reset</span>

array\_key\_last
================

Gets the last key of an array

### Description

<span class="type">mixed</span> <span
class="methodname">array\_key\_last</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

Get the last key of the given `array` without affecting the internal
array pointer.

### Parameters

`array`  
An array.

### Return Values

Returns the last key of `array` if the array is not empty; **`NULL`**
otherwise.

### See Also

-   <span class="function">array\_key\_first</span>
-   <span class="function">end</span>

array\_keys
===========

Return all the keys or a subset of the keys of an array

### Description

<span class="type">array</span> <span
class="methodname">array\_keys</span> ( <span class="methodparam"><span
class="type">array</span> `$array`</span> )

<span class="type">array</span> <span
class="methodname">array\_keys</span> ( <span class="methodparam"><span
class="type">array</span> `$array`</span> , <span
class="methodparam"><span class="type">mixed</span>
`$search_value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="function">array\_keys</span> returns the keys, numeric and
string, from the `array`.

If a `search_value` is specified, then only the keys for that value are
returned. Otherwise, all the keys from the `array` are returned.

### Parameters

`array`  
An array containing keys to return.

`search_value`  
If specified, then only keys containing these values are returned.

`strict`  
Determines if strict comparison (===) should be used during the search.

### Return Values

Returns an array of all the keys in `array`.

### Examples

**Example \#1 <span class="function">array\_keys</span> example**

``` php
<?php
$array = array(0 => 100, "color" => "red");
print_r(array_keys($array));

$array = array("blue", "red", "green", "blue", "blue");
print_r(array_keys($array, "blue"));

$array = array("color" => array("blue", "red", "green"),
               "size"  => array("small", "medium", "large"));
print_r(array_keys($array));
?>
```

The above example will output:

    Array
    (
        [0] => 0
        [1] => color
    )
    Array
    (
        [0] => 0
        [1] => 3
        [2] => 4
    )
    Array
    (
        [0] => color
        [1] => size
    )

### See Also

-   <span class="function">array\_values</span>
-   <span class="function">array\_combine</span>
-   <span class="function">array\_key\_exists</span>
-   <span class="function">array\_search</span>

array\_map
==========

Applies the callback to the elements of the given arrays

### Description

<span class="type">array</span> <span
class="methodname">array\_map</span> ( <span class="methodparam"><span
class="type">callable</span> `$callback`</span> , <span
class="methodparam"><span class="type">array</span> `$array1`</span> \[,
<span class="methodparam"><span class="type">array</span> `$...`</span>
\] )

<span class="function">array\_map</span> returns an <span
class="type">array</span> containing the results of applying the
`callback` function to the corresponding index of `array1` (and `...` if
more arrays are provided) used as arguments for the callback. The number
of parameters that the `callback` function accepts should match the
number of arrays passed to <span class="function">array\_map</span>.

### Parameters

`callback`  
Callback function to run for each element in each array.

**`NULL`** can be passed as a value to `callback` to perform a zip
operation on multiple arrays. If only `array1` is provided, <span
class="methodname">array\_map</span> will return the input array.

`array1`  
An array to run through the `callback` function.

`...`  
Supplementary variable list of array arguments to run through the
`callback` function.

### Return Values

Returns an array containing the results of applying the `callback`
function to the corresponding index of `array1` (and `...` if more
arrays are provided) used as arguments for the callback.

The returned array will preserve the keys of the array argument if and
only if exactly one array is passed. If more than one array is passed,
the returned array will have sequential integer keys.

### Examples

**Example \#1 <span class="function">array\_map</span> example**

``` php
<?php
function cube($n)
{
    return ($n * $n * $n);
}

$a = [1, 2, 3, 4, 5];
$b = array_map('cube', $a);
print_r($b);
?>
```

This makes `$b` have:

    Array
    (
        [0] => 1
        [1] => 8
        [2] => 27
        [3] => 64
        [4] => 125
    )

**Example \#2 <span class="function">array\_map</span> using a lambda
function (as of PHP 5.3.0)**

``` php
<?php
$func = function($value) {
    return $value * 2;
};

print_r(array_map($func, range(1, 5)));
?>
```

    Array
    (
        [0] => 2
        [1] => 4
        [2] => 6
        [3] => 8
        [4] => 10
    )

**Example \#3 <span class="function">array\_map</span> - using more
arrays**

``` php
<?php
function show_Spanish($n, $m)
{
    return "The number {$n} is called {$m} in Spanish";
}

function map_Spanish($n, $m)
{
    return [$n => $m];
}

$a = [1, 2, 3, 4, 5];
$b = ['uno', 'dos', 'tres', 'cuatro', 'cinco'];

$c = array_map('show_Spanish', $a, $b);
print_r($c);

$d = array_map('map_Spanish', $a , $b);
print_r($d);
?>
```

The above example will output:

    // printout of $c
    Array
    (
        [0] => The number 1 is called uno in Spanish
        [1] => The number 2 is called dos in Spanish
        [2] => The number 3 is called tres in Spanish
        [3] => The number 4 is called cuatro in Spanish
        [4] => The number 5 is called cinco in Spanish
    )

    // printout of $d
    Array
    (
        [0] => Array
            (
                [1] => uno
            )

        [1] => Array
            (
                [2] => dos
            )

        [2] => Array
            (
                [3] => tres
            )

        [3] => Array
            (
                [4] => cuatro
            )

        [4] => Array
            (
                [5] => cinco
            )

    )

Usually when using two or more arrays, they should be of equal length
because the callback function is applied in parallel to the
corresponding elements. If the arrays are of unequal length, shorter
ones will be extended with empty elements to match the length of the
longest.

An interesting use of this function is to construct an array of arrays,
which can be easily performed by using **`NULL`** as the name of the
callback function

**Example \#4 Performing a zip operation of arrays**

``` php
<?php
$a = [1, 2, 3, 4, 5];
$b = ['one', 'two', 'three', 'four', 'five'];
$c = ['uno', 'dos', 'tres', 'cuatro', 'cinco'];

$d = array_map(null, $a, $b, $c);
print_r($d);
?>
```

The above example will output:

    Array
    (
        [0] => Array
            (
                [0] => 1
                [1] => one
                [2] => uno
            )

        [1] => Array
            (
                [0] => 2
                [1] => two
                [2] => dos
            )

        [2] => Array
            (
                [0] => 3
                [1] => three
                [2] => tres
            )

        [3] => Array
            (
                [0] => 4
                [1] => four
                [2] => cuatro
            )

        [4] => Array
            (
                [0] => 5
                [1] => five
                [2] => cinco
            )

    )

**Example \#5 **`NULL`** `callback` with only `array1`**

``` php
<?php
$array = [1, 2, 3];
var_dump(array_map(null, $array));
?>
```

The above example will output:

    array(3) {
      [0]=>
      int(1)
      [1]=>
      int(2)
      [2]=>
      int(3)
    }

**Example \#6 <span class="function">array\_map</span> - with string
keys**

``` php
<?php
$arr = ['stringkey' => 'value'];
function cb1($a) {
    return [$a];
}
function cb2($a, $b) {
    return [$a, $b];
}
var_dump(array_map('cb1', $arr));
var_dump(array_map('cb2', $arr, $arr));
var_dump(array_map(null,  $arr));
var_dump(array_map(null, $arr, $arr));
?>
```

The above example will output:

    array(1) {
      ["stringkey"]=>
      array(1) {
        [0]=>
        string(5) "value"
      }
    }
    array(1) {
      [0]=>
      array(2) {
        [0]=>
        string(5) "value"
        [1]=>
        string(5) "value"
      }
    }
    array(1) {
      ["stringkey"]=>
      string(5) "value"
    }
    array(1) {
      [0]=>
      array(2) {
        [0]=>
        string(5) "value"
        [1]=>
        string(5) "value"
      }
    }

### See Also

-   <span class="function">array\_filter</span>
-   <span class="function">array\_reduce</span>
-   <span class="function">array\_walk</span>
-   information about the
    <a href="/language/pseudo-types.html#language.types.callback" class="link">callback</a>
    type

array\_merge\_recursive
=======================

Merge one or more arrays recursively

### Description

<span class="type">array</span> <span
class="methodname">array\_merge\_recursive</span> (\[ <span
class="methodparam"><span class="type">array</span> `$...`</span> \] )

<span class="function">array\_merge\_recursive</span> merges the
elements of one or more arrays together so that the values of one are
appended to the end of the previous one. It returns the resulting array.

If the input arrays have the same string keys, then the values for these
keys are merged together into an array, and this is done recursively, so
that if one of the values is an array itself, the function will merge it
with a corresponding entry in another array too. If, however, the arrays
have the same numeric key, the later value will not overwrite the
original value, but will be appended.

### Parameters

`...`  
Variable list of arrays to recursively merge.

### Return Values

An array of values resulted from merging the arguments together. If
called without any arguments, returns an empty <span
class="type">array</span>.

### Changelog

| Version | Description                                                                                                |
|---------|------------------------------------------------------------------------------------------------------------|
| 7.4.0   | This function can now be called without any parameter. Formerly, at least one parameter has been required. |

### Examples

**Example \#1 <span class="function">array\_merge\_recursive</span>
example**

``` php
<?php
$ar1 = array("color" => array("favorite" => "red"), 5);
$ar2 = array(10, "color" => array("favorite" => "green", "blue"));
$result = array_merge_recursive($ar1, $ar2);
print_r($result);
?>
```

The above example will output:

    Array
    (
        [color] => Array
            (
                [favorite] => Array
                    (
                        [0] => red
                        [1] => green
                    )

                [0] => blue
            )

        [0] => 5
        [1] => 10
    )

### See Also

-   <span class="function">array\_merge</span>
-   <span class="function">array\_replace\_recursive</span>

array\_merge
============

Merge one or more arrays

### Description

<span class="type">array</span> <span
class="methodname">array\_merge</span> (\[ <span
class="methodparam"><span class="type">array</span> `$...`</span> \] )

Merges the elements of one or more arrays together so that the values of
one are appended to the end of the previous one. It returns the
resulting array.

If the input arrays have the same string keys, then the later value for
that key will overwrite the previous one. If, however, the arrays
contain numeric keys, the later value will *not* overwrite the original
value, but will be appended.

Values in the input arrays with numeric keys will be renumbered with
incrementing keys starting from zero in the result array.

### Parameters

`...`  
Variable list of arrays to merge.

### Return Values

Returns the resulting array. If called without any arguments, returns an
empty <span class="type">array</span>.

### Changelog

| Version | Description                                                                                                |
|---------|------------------------------------------------------------------------------------------------------------|
| 7.4.0   | This function can now be called without any parameter. Formerly, at least one parameter has been required. |

### Examples

**Example \#1 <span class="function">array\_merge</span> example**

``` php
<?php
$array1 = array("color" => "red", 2, 4);
$array2 = array("a", "b", "color" => "green", "shape" => "trapezoid", 4);
$result = array_merge($array1, $array2);
print_r($result);
?>
```

The above example will output:

    Array
    (
        [color] => green
        [0] => 2
        [1] => 4
        [2] => a
        [3] => b
        [shape] => trapezoid
        [4] => 4
    )

**Example \#2 Simple <span class="function">array\_merge</span>
example**

``` php
<?php
$array1 = array();
$array2 = array(1 => "data");
$result = array_merge($array1, $array2);
?>
```

Don't forget that numeric keys will be renumbered!

    Array
    (
        [0] => data
    )

If you want to append array elements from the second array to the first
array while not overwriting the elements from the first array and not
re-indexing, use the *+* array union operator:

``` php
<?php
$array1 = array(0 => 'zero_a', 2 => 'two_a', 3 => 'three_a');
$array2 = array(1 => 'one_b', 3 => 'three_b', 4 => 'four_b');
$result = $array1 + $array2;
var_dump($result);
?>
```

The keys from the first array will be preserved. If an array key exists
in both arrays, then the element from the first array will be used and
the matching key's element from the second array will be ignored.

    array(5) {
      [0]=>
      string(6) "zero_a"
      [2]=>
      string(5) "two_a"
      [3]=>
      string(7) "three_a"
      [1]=>
      string(5) "one_b"
      [4]=>
      string(6) "four_b"
    }

**Example \#3 <span class="function">array\_merge</span> with non-array
types**

``` php
<?php
$beginning = 'foo';
$end = array(1 => 'bar');
$result = array_merge((array)$beginning, (array)$end);
print_r($result);
?>
```

The above example will output:

        Array
        (
            [0] => foo
            [1] => bar
        )

### See Also

-   <span class="function">array\_merge\_recursive</span>
-   <span class="function">array\_replace</span>
-   <span class="function">array\_combine</span>
-   <a href="/language/operators/array.html" class="link">array operators</a>

array\_multisort
================

Sort multiple or multi-dimensional arrays

### Description

<span class="type">bool</span> <span
class="methodname">array\_multisort</span> ( <span
class="methodparam"><span class="type">array</span> `&$array1`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$array1_sort_order`<span class="initializer"> = SORT\_ASC</span></span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$array1_sort_flags`<span class="initializer"> =
SORT\_REGULAR</span></span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \]\]\] )

<span class="function">array\_multisort</span> can be used to sort
several arrays at once, or a multi-dimensional array by one or more
dimensions.

Associative (<span class="type">string</span>) keys will be maintained,
but numeric keys will be re-indexed.

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array1`  
An <span class="type">array</span> being sorted.

`array1_sort_order`  
The order used to sort the previous <span class="type">array</span>
argument. Either **`SORT_ASC`** to sort ascendingly or **`SORT_DESC`**
to sort descendingly.

This argument can be swapped with `array1_sort_flags` or omitted
entirely, in which case **`SORT_ASC`** is assumed.

`array1_sort_flags`  
Sort options for the previous <span class="type">array</span> argument:

Sorting type flags:

-   <span class="simpara">**`SORT_REGULAR`** - compare items normally
    (don't change types)</span>
-   <span class="simpara">**`SORT_NUMERIC`** - compare items
    numerically</span>
-   <span class="simpara">**`SORT_STRING`** - compare items as
    strings</span>
-   <span class="simpara"> **`SORT_LOCALE_STRING`** - compare items as
    strings, based on the current locale. It uses the locale, which can
    be changed using <span class="function">setlocale</span> </span>
-   <span class="simpara"> **`SORT_NATURAL`** - compare items as strings
    using "natural ordering" like <span class="function">natsort</span>
    </span>
-   <span class="simpara"> **`SORT_FLAG_CASE`** - can be combined
    (bitwise OR) with **`SORT_STRING`** or **`SORT_NATURAL`** to sort
    strings case-insensitively </span>

This argument can be swapped with `array1_sort_order` or omitted
entirely, in which case **`SORT_REGULAR`** is assumed.

`...`  
More arrays, optionally followed by sort order and flags. Only elements
corresponding to equivalent elements in previous arrays are compared. In
other words, the sort is lexicographical.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                               |
|---------|-----------------------------------------------------------------------------------------------------------|
| 5.4.0   | The **`SORT_NATURAL`** and **`SORT_FLAG_CASE`** were added to `array1_sort_flags` as possible sort flags. |
| 5.3.0   | The **`SORT_LOCALE_STRING`** was added to `array1_sort_flags` as possible sort flags.                     |

### Examples

**Example \#1 Sorting multiple arrays**

``` php
<?php
$ar1 = array(10, 100, 100, 0);
$ar2 = array(1, 3, 2, 4);
array_multisort($ar1, $ar2);

var_dump($ar1);
var_dump($ar2);
?>
```

In this example, after sorting, the first array will contain 0, 10, 100,
100. The second array will contain 4, 1, 2, 3. The entries in the second
array corresponding to the identical entries in the first array (100 and
100) were sorted as well.

    array(4) {
      [0]=> int(0)
      [1]=> int(10)
      [2]=> int(100)
      [3]=> int(100)
    }
    array(4) {
      [0]=> int(4)
      [1]=> int(1)
      [2]=> int(2)
      [3]=> int(3)
    }

**Example \#2 Sorting multi-dimensional array**

``` php
<?php
$ar = array(
       array("10", 11, 100, 100, "a"),
       array(   1,  2, "2",   3,   1)
      );
array_multisort($ar[0], SORT_ASC, SORT_STRING,
                $ar[1], SORT_NUMERIC, SORT_DESC);
var_dump($ar);
?>
```

In this example, after sorting, the first array will transform to "10",
100, 100, 11, "a" (it was sorted as strings in ascending order). The
second will contain 1, 3, "2", 2, 1 (sorted as numbers, in descending
order).

    array(2) {
      [0]=> array(5) {
        [0]=> string(2) "10"
        [1]=> int(100)
        [2]=> int(100)
        [3]=> int(11)
        [4]=> string(1) "a"
      }
      [1]=> array(5) {
        [0]=> int(1)
        [1]=> int(3)
        [2]=> string(1) "2"
        [3]=> int(2)
        [4]=> int(1)
      }
    }

**Example \#3 Sorting database results**

For this example, each element in the `data` array represents one row in
a table. This type of dataset is typical of database records.

Example data:

    volume | edition
    -------+--------
        67 |       2
        86 |       1
        85 |       6
        98 |       2
        86 |       6
        67 |       7

The data as an array, called `data`. This would usually, for example, be
obtained by looping with <span
class="function">mysqli\_fetch\_assoc</span>.

``` php
<?php
$data[] = array('volume' => 67, 'edition' => 2);
$data[] = array('volume' => 86, 'edition' => 1);
$data[] = array('volume' => 85, 'edition' => 6);
$data[] = array('volume' => 98, 'edition' => 2);
$data[] = array('volume' => 86, 'edition' => 6);
$data[] = array('volume' => 67, 'edition' => 7);
?>
```

In this example, we will order by `volume` descending, `edition`
ascending.

We have an array of rows, but <span
class="function">array\_multisort</span> requires an array of columns,
so we use the below code to obtain the columns, then perform the
sorting.

``` php
<?php
// Obtain a list of columns
foreach ($data as $key => $row) {
    $volume[$key]  = $row['volume'];
    $edition[$key] = $row['edition'];
}

// as of PHP 5.5.0 you can use array_column() instead of the above code
$volume  = array_column($data, 'volume');
$edition = array_column($data, 'edition');

// Sort the data with volume descending, edition ascending
// Add $data as the last parameter, to sort by the common key
array_multisort($volume, SORT_DESC, $edition, SORT_ASC, $data);
?>
```

The dataset is now sorted, and will look like this:

    volume | edition
    -------+--------
        98 |       2
        86 |       1
        86 |       6
        85 |       6
        67 |       2
        67 |       7

**Example \#4 Case insensitive sorting**

Both **`SORT_STRING`** and **`SORT_REGULAR`** are case sensitive,
strings starting with a capital letter will come before strings starting
with a lowercase letter.

To perform a case insensitive sort, force the sorting order to be
determined by a lowercase copy of the original array.

``` php
<?php
$array = array('Alpha', 'atomic', 'Beta', 'bank');
$array_lowercase = array_map('strtolower', $array);

array_multisort($array_lowercase, SORT_ASC, SORT_STRING, $array);

print_r($array);
?>
```

The above example will output:

    Array
    (
        [0] => Alpha
        [1] => atomic
        [2] => bank
        [3] => Beta
    )

### See Also

-   <span class="function">usort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

array\_pad
==========

Pad array to the specified length with a value

### Description

<span class="type">array</span> <span
class="methodname">array\_pad</span> ( <span class="methodparam"><span
class="type">array</span> `$array`</span> , <span
class="methodparam"><span class="type">int</span> `$size`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="function">array\_pad</span> returns a copy of the `array`
padded to size specified by `size` with value `value`. If `size` is
positive then the array is padded on the right, if it's negative then on
the left. If the absolute value of `size` is less than or equal to the
length of the `array` then no padding takes place. It is possible to add
at most 1048576 elements at a time.

### Parameters

`array`  
Initial array of values to pad.

`size`  
New size of the array.

`value`  
Value to pad if `array` is less than `size`.

### Return Values

Returns a copy of the `array` padded to size specified by `size` with
value `value`. If `size` is positive then the array is padded on the
right, if it's negative then on the left. If the absolute value of
`size` is less than or equal to the length of the `array` then no
padding takes place.

### Examples

**Example \#1 <span class="function">array\_pad</span> example**

``` php
<?php
$input = array(12, 10, 9);

$result = array_pad($input, 5, 0);
// result is array(12, 10, 9, 0, 0)

$result = array_pad($input, -7, -1);
// result is array(-1, -1, -1, -1, 12, 10, 9)

$result = array_pad($input, 2, "noop");
// not padded
?>
```

### See Also

-   <span class="function">array\_fill</span>
-   <span class="function">range</span>

array\_pop
==========

Pop the element off the end of array

### Description

<span class="type">mixed</span> <span
class="methodname">array\_pop</span> ( <span class="methodparam"><span
class="type">array</span> `&$array`</span> )

<span class="function">array\_pop</span> pops and returns the value of
the last element of `array`, shortening the `array` by one element.

> **Note**: <span class="simpara">This function will <span
> class="function">reset</span> the <span class="type">array</span>
> pointer of the input array after use.</span>

### Parameters

`array`  
The array to get the value from.

### Return Values

Returns the value of the last element of `array`. If `array` is empty
(or is not an array), **`NULL`** will be returned.

### Errors/Exceptions

This function will produce an error of level
<a href="/errorfunc/constants.html" class="link">E_WARNING</a> when
called on a non-array.

### Examples

**Example \#1 <span class="function">array\_pop</span> example**

``` php
<?php
$stack = array("orange", "banana", "apple", "raspberry");
$fruit = array_pop($stack);
print_r($stack);
?>
```

After this, `$stack` will have only 3 elements:

    Array
    (
        [0] => orange
        [1] => banana
        [2] => apple
    )

and *raspberry* will be assigned to `$fruit`.

### See Also

-   <span class="function">array\_push</span>
-   <span class="function">array\_shift</span>
-   <span class="function">array\_unshift</span>

array\_product
==============

Calculate the product of values in an array

### Description

<span class="type">number</span> <span
class="methodname">array\_product</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

<span class="function">array\_product</span> returns the product of
values in an array.

### Parameters

`array`  
The array.

### Return Values

Returns the product as an integer or float.

### Changelog

| Version | Description                                                                                          |
|---------|------------------------------------------------------------------------------------------------------|
| 5.3.6   | The product of an empty array is now 1, when before this function would return 0 for an empty array. |

### Examples

**Example \#1 <span class="function">array\_product</span> examples**

``` php
<?php

$a = array(2, 4, 6, 8);
echo "product(a) = " . array_product($a) . "\n";
echo "product(array()) = " . array_product(array()) . "\n";

?>
```

The above example will output:

    product(a) = 384
    product(array()) = 1

array\_push
===========

Push one or more elements onto the end of array

### Description

<span class="type">int</span> <span
class="methodname">array\_push</span> ( <span class="methodparam"><span
class="type">array</span> `&$array`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$...`</span> \] )

<span class="function">array\_push</span> treats `array` as a stack, and
pushes the passed variables onto the end of `array`. The length of
`array` increases by the number of variables pushed. Has the same effect
as:

``` php
<?php
$array[] = $var;
?>
```

repeated for each passed value.

> **Note**: <span class="simpara"> If you use <span
> class="function">array\_push</span> to add one element to the array,
> it's better to use *$array\[\] =* because in that way there is no
> overhead of calling a function. </span>

> **Note**: <span class="simpara"> <span
> class="function">array\_push</span> will raise a warning if the first
> argument is not an array. This differs from the *$var\[\]* behaviour
> where a new array is created. </span>

### Parameters

`array`  
The input array.

`...`  
The values to push onto the end of the `array`.

### Return Values

Returns the new number of elements in the array.

### Changelog

| Version | Description                                                                                                    |
|---------|----------------------------------------------------------------------------------------------------------------|
| 7.3.0   | This function can now be called with only one parameter. Formerly, at least two parameters have been required. |

### Examples

**Example \#1 <span class="function">array\_push</span> example**

``` php
<?php
$stack = array("orange", "banana");
array_push($stack, "apple", "raspberry");
print_r($stack);
?>
```

The above example will output:

    Array
    (
        [0] => orange
        [1] => banana
        [2] => apple
        [3] => raspberry
    )

### See Also

-   <span class="function">array\_pop</span>
-   <span class="function">array\_shift</span>
-   <span class="function">array\_unshift</span>

array\_rand
===========

Pick one or more random keys out of an array

### Description

<span class="type">mixed</span> <span
class="methodname">array\_rand</span> ( <span class="methodparam"><span
class="type">array</span> `$array`</span> \[, <span
class="methodparam"><span class="type">int</span> `$num`<span
class="initializer"> = 1</span></span> \] )

Picks one or more random entries out of an array, and returns the key
(or keys) of the random entries. It uses a pseudo random number
generator that is not suitable for cryptographic purposes.

### Parameters

`array`  
The input array.

`num`  
Specifies how many entries should be picked.

### Return Values

When picking only one entry, <span class="function">array\_rand</span>
returns the key for a random entry. Otherwise, an array of keys for the
random entries is returned. This is done so that random keys can be
picked from the array as well as random values. Trying to pick more
elements than there are in the array will result in an **`E_WARNING`**
level error, and NULL will be returned.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                       |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | The internal randomization algorithm <a href="/migration71/incompatible.html#migration71.incompatible.rand-srand-aliases" class="link">has been changed</a> to use the <a href="http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/emt.html" class="link external">» Mersenne Twister</a> Random Number Generator instead of the libc rand function. |
| 5.2.10  | The resulting array of keys is no longer shuffled.                                                                                                                                                                                                                                                                                                |

### Examples

**Example \#1 <span class="function">array\_rand</span> example**

``` php
<?php
$input = array("Neo", "Morpheus", "Trinity", "Cypher", "Tank");
$rand_keys = array_rand($input, 2);
echo $input[$rand_keys[0]] . "\n";
echo $input[$rand_keys[1]] . "\n";
?>
```

### See Also

-   <span class="function">shuffle</span>

array\_reduce
=============

Iteratively reduce the array to a single value using a callback function

### Description

<span class="type">mixed</span> <span
class="methodname">array\_reduce</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$initial`<span class="initializer"> =
**`NULL`**</span></span> \] )

<span class="function">array\_reduce</span> applies iteratively the
`callback` function to the elements of the `array`, so as to reduce the
array to a single value.

### Parameters

`array`  
The input array.

`callback`  
<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$carry`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$item`</span>
)

`carry`  
Holds the return value of the previous iteration; in the case of the
first iteration it instead holds the value of `initial`.

`item`  
Holds the value of the current iteration.

`initial`  
If the optional `initial` is available, it will be used at the beginning
of the process, or as a final result in case the array is empty.

### Return Values

Returns the resulting value.

If the array is empty and `initial` is not passed, <span
class="function">array\_reduce</span> returns **`NULL`**.

### Changelog

| Version | Description                                                                                               |
|---------|-----------------------------------------------------------------------------------------------------------|
| 5.3.0   | Changed `initial` to allow <span class="type">mixed</span>, previously <span class="type">integer</span>. |

### Examples

**Example \#1 <span class="function">array\_reduce</span> example**

``` php
<?php
function sum($carry, $item)
{
    $carry += $item;
    return $carry;
}

function product($carry, $item)
{
    $carry *= $item;
    return $carry;
}

$a = array(1, 2, 3, 4, 5);
$x = array();

var_dump(array_reduce($a, "sum")); // int(15)
var_dump(array_reduce($a, "product", 10)); // int(1200), because: 10*1*2*3*4*5
var_dump(array_reduce($x, "sum", "No data to reduce")); // string(17) "No data to reduce"
?>
```

### See Also

-   <span class="function">array\_filter</span>
-   <span class="function">array\_map</span>
-   <span class="function">array\_unique</span>
-   <span class="function">array\_count\_values</span>

array\_replace\_recursive
=========================

Replaces elements from passed arrays into the first array recursively

### Description

<span class="type">array</span> <span
class="methodname">array\_replace\_recursive</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> \[,
<span class="methodparam"><span class="type">array</span> `$...`</span>
\] )

<span class="function">array\_replace\_recursive</span> replaces the
values of `array1` with the same values from all the following arrays.
If a key from the first array exists in the second array, its value will
be replaced by the value from the second array. If the key exists in the
second array, and not the first, it will be created in the first array.
If a key only exists in the first array, it will be left as is. If
several arrays are passed for replacement, they will be processed in
order, the later array overwriting the previous values.

<span class="function">array\_replace\_recursive</span> is recursive :
it will recurse into arrays and apply the same process to the inner
value.

When the value in the first array is scalar, it will be replaced by the
value in the second array, may it be scalar or array. When the value in
the first array and the second array are both arrays, <span
class="function">array\_replace\_recursive</span> will replace their
respective value recursively.

### Parameters

`array1`  
The array in which elements are replaced.

`...`  
Optional. Arrays from which elements will be extracted.

### Return Values

Returns an <span class="type">array</span>, or **`NULL`** if an error
occurs.

### Examples

**Example \#1 <span class="function">array\_replace\_recursive</span>
example**

``` php
<?php
$base = array('citrus' => array( "orange") , 'berries' => array("blackberry", "raspberry"), );
$replacements = array('citrus' => array('pineapple'), 'berries' => array('blueberry'));

$basket = array_replace_recursive($base, $replacements);
print_r($basket);

$basket = array_replace($base, $replacements);
print_r($basket);
?>
```

The above example will output:

    Array
    (
        [citrus] => Array
            (
                [0] => pineapple
            )

        [berries] => Array
            (
                [0] => blueberry
                [1] => raspberry
            )

    )
    Array
    (
        [citrus] => Array
            (
                [0] => pineapple
            )

        [berries] => Array
            (
                [0] => blueberry
            )

    )

**Example \#2 <span class="function">array\_replace\_recursive</span>
and recursive behavior**

``` php
<?php
$base = array('citrus' => array("orange") , 'berries' => array("blackberry", "raspberry"), 'others' => 'banana' );
$replacements = array('citrus' => 'pineapple', 'berries' => array('blueberry'), 'others' => array('litchis'));
$replacements2 = array('citrus' => array('pineapple'), 'berries' => array('blueberry'), 'others' => 'litchis');

$basket = array_replace_recursive($base, $replacements, $replacements2);
print_r($basket);

?>
```

The above example will output:

    Array
    (
        [citrus] => Array
            (
                [0] => pineapple
            )

        [berries] => Array
            (
                [0] => blueberry
                [1] => raspberry
            )

        [others] => litchis
    )

### See Also

-   <span class="function">array\_replace</span>
-   <span class="function">array\_merge\_recursive</span>

array\_replace
==============

Replaces elements from passed arrays into the first array

### Description

<span class="type">array</span> <span
class="methodname">array\_replace</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> \[,
<span class="methodparam"><span class="type">array</span> `$...`</span>
\] )

<span class="function">array\_replace</span> replaces the values of
`array1` with values having the same keys in each of the following
arrays. If a key from the first array exists in the second array, its
value will be replaced by the value from the second array. If the key
exists in the second array, and not the first, it will be created in the
first array. If a key only exists in the first array, it will be left as
is. If several arrays are passed for replacement, they will be processed
in order, the later arrays overwriting the previous values.

<span class="function">array\_replace</span> is not recursive : it will
replace values in the first array by whatever type is in the second
array.

### Parameters

`array1`  
The array in which elements are replaced.

`...`  
Arrays from which elements will be extracted. Values from later arrays
overwrite the previous values.

### Return Values

Returns an <span class="type">array</span>, or **`NULL`** if an error
occurs.

### Examples

**Example \#1 <span class="function">array\_replace</span> example**

``` php
<?php
$base = array("orange", "banana", "apple", "raspberry");
$replacements = array(0 => "pineapple", 4 => "cherry");
$replacements2 = array(0 => "grape");

$basket = array_replace($base, $replacements, $replacements2);
print_r($basket);
?>
```

The above example will output:

    Array
    (
        [0] => grape
        [1] => banana
        [2] => apple
        [3] => raspberry
        [4] => cherry
    )

### See Also

-   <span class="function">array\_replace\_recursive</span>
-   <span class="function">array\_merge</span>

array\_reverse
==============

Return an array with elements in reverse order

### Description

<span class="type">array</span> <span
class="methodname">array\_reverse</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$preserve_keys`<span class="initializer"> = **`FALSE`**</span></span>
\] )

Takes an input `array` and returns a new array with the order of the
elements reversed.

### Parameters

`array`  
The input array.

`preserve_keys`  
If set to **`TRUE`** numeric keys are preserved. Non-numeric keys are
not affected by this setting and will always be preserved.

### Return Values

Returns the reversed array.

### Examples

**Example \#1 <span class="function">array\_reverse</span> example**

``` php
<?php
$input  = array("php", 4.0, array("green", "red"));
$reversed = array_reverse($input);
$preserved = array_reverse($input, true);

print_r($input);
print_r($reversed);
print_r($preserved);
?>
```

The above example will output:

    Array
    (
        [0] => php
        [1] => 4
        [2] => Array
            (
                [0] => green
                [1] => red
            )

    )
    Array
    (
        [0] => Array
            (
                [0] => green
                [1] => red
            )

        [1] => 4
        [2] => php
    )
    Array
    (
        [2] => Array
            (
                [0] => green
                [1] => red
            )

        [1] => 4
        [0] => php
    )

### See Also

-   <span class="function">array\_flip</span>

array\_search
=============

Searches the array for a given value and returns the first corresponding
key if successful

### Description

<span class="type">mixed</span> <span
class="methodname">array\_search</span> ( <span
class="methodparam"><span class="type">mixed</span> `$needle`</span> ,
<span class="methodparam"><span class="type">array</span>
`$haystack`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Searches for `needle` in `haystack`.

### Parameters

`needle`  
The searched value.

> **Note**:
>
> If `needle` is a string, the comparison is done in a case-sensitive
> manner.

`haystack`  
The array.

`strict`  
If the third parameter `strict` is set to **`TRUE`** then the <span
class="function">array\_search</span> function will search for
*identical* elements in the `haystack`. This means it will also perform
a <a href="/language/types.html" class="link">strict type comparison</a>
of the `needle` in the `haystack`, and objects must be the same
instance.

### Return Values

Returns the key for `needle` if it is found in the array, **`FALSE`**
otherwise.

If `needle` is found in `haystack` more than once, the first matching
key is returned. To return the keys for all matching values, use <span
class="function">array\_keys</span> with the optional `search_value`
parameter instead.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Changelog

| Version | Description                                                                                                                                            |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.3.0   | As with all internal PHP functions as of 5.3.0, <span class="function">array\_search</span> returns **`NULL`** if invalid parameters are passed to it. |

### Examples

**Example \#1 <span class="function">array\_search</span> example**

``` php
<?php
$array = array(0 => 'blue', 1 => 'red', 2 => 'green', 3 => 'red');

$key = array_search('green', $array); // $key = 2;
$key = array_search('red', $array);   // $key = 1;
?>
```

### See Also

-   <span class="function">array\_keys</span>
-   <span class="function">array\_values</span>
-   <span class="function">array\_key\_exists</span>
-   <span class="function">in\_array</span>

array\_shift
============

Shift an element off the beginning of array

### Description

<span class="type">mixed</span> <span
class="methodname">array\_shift</span> ( <span class="methodparam"><span
class="type">array</span> `&$array`</span> )

<span class="function">array\_shift</span> shifts the first value of the
`array` off and returns it, shortening the `array` by one element and
moving everything down. All numerical array keys will be modified to
start counting from zero while literal keys won't be affected.

> **Note**: <span class="simpara">This function will <span
> class="function">reset</span> the <span class="type">array</span>
> pointer of the input array after use.</span>

### Parameters

`array`  
The input array.

### Return Values

Returns the shifted value, or **`NULL`** if `array` is empty or is not
an array.

### Examples

**Example \#1 <span class="function">array\_shift</span> example**

``` php
<?php
$stack = array("orange", "banana", "apple", "raspberry");
$fruit = array_shift($stack);
print_r($stack);
?>
```

The above example will output:

    Array
    (
        [0] => banana
        [1] => apple
        [2] => raspberry
    )

and *orange* will be assigned to `$fruit`.

### See Also

-   <span class="function">array\_unshift</span>
-   <span class="function">array\_push</span>
-   <span class="function">array\_pop</span>

array\_slice
============

Extract a slice of the array

### Description

<span class="type">array</span> <span
class="methodname">array\_slice</span> ( <span class="methodparam"><span
class="type">array</span> `$array`</span> , <span
class="methodparam"><span class="type">int</span> `$offset`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = **`NULL`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$preserve_keys`<span
class="initializer"> = **`FALSE`**</span></span> \]\] )

<span class="function">array\_slice</span> returns the sequence of
elements from the array `array` as specified by the `offset` and
`length` parameters.

### Parameters

`array`  
The input array.

`offset`  
If `offset` is non-negative, the sequence will start at that offset in
the `array`.

If `offset` is negative, the sequence will start that far from the end
of the `array`.

> **Note**:
>
> The `offset` parameter denotes the position in the array, not the key.

`length`  
If `length` is given and is positive, then the sequence will have up to
that many elements in it.

If the array is shorter than the `length`, then only the available array
elements will be present.

If `length` is given and is negative then the sequence will stop that
many elements from the end of the array.

If it is omitted, then the sequence will have everything from `offset`
up until the end of the `array`.

`preserve_keys`  
> **Note**:
>
> <span class="function">array\_slice</span> will reorder and reset the
> integer array indices by default. This behaviour can be changed by
> setting `preserve_keys` to **`TRUE`**. String keys are always
> preserved, regardless of this parameter.

### Return Values

Returns the slice. If the offset is larger than the size of the array,
an empty array is returned.

### Changelog

| Version | Description                                                                                                                                                                                                                                                |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.2.4   | The default value of the `length` parameter was changed to **`NULL`**. A **`NULL`** `length` now tells the function to use the length of `array`. Prior to this version, a **`NULL`** `length` was taken to mean a zero length (nothing will be returned). |
| 5.0.2   | The optional `preserve_keys` parameter was added.                                                                                                                                                                                                          |

### Examples

**Example \#1 <span class="function">array\_slice</span> examples**

``` php
<?php
$input = array("a", "b", "c", "d", "e");

$output = array_slice($input, 2);      // returns "c", "d", and "e"
$output = array_slice($input, -2, 1);  // returns "d"
$output = array_slice($input, 0, 3);   // returns "a", "b", and "c"

// note the differences in the array keys
print_r(array_slice($input, 2, -1));
print_r(array_slice($input, 2, -1, true));
?>
```

The above example will output:

    Array
    (
        [0] => c
        [1] => d
    )
    Array
    (
        [2] => c
        [3] => d
    )

**Example \#2 <span class="function">array\_slice</span> and one-based
array**

``` php
<?php
$input = array(1 => "a", "b", "c", "d", "e");
print_r(array_slice($input, 1, 2));
?>
```

The above example will output:

    Array
    (
        [0] => b
        [1] => c
    )

**Example \#3 <span class="function">array\_slice</span> and array with
mixed keys**

``` php
<?php
$ar = array('a'=>'apple', 'b'=>'banana', '42'=>'pear', 'd'=>'orange');
print_r(array_slice($ar, 0, 3));
print_r(array_slice($ar, 0, 3, true));
?>
```

The above example will output:

    Array
    (
        [a] => apple
        [b] => banana
        [0] => pear
    )
    Array
    (
        [a] => apple
        [b] => banana
        [42] => pear
    )

### See Also

-   <span class="function">array\_chunk</span>
-   <span class="function">array\_splice</span>
-   <span class="function">unset</span>

array\_splice
=============

Remove a portion of the array and replace it with something else

### Description

<span class="type">array</span> <span
class="methodname">array\_splice</span> ( <span
class="methodparam"><span class="type">array</span> `&$input`</span> ,
<span class="methodparam"><span class="type">int</span> `$offset`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$length`<span class="initializer"> = count($input)</span></span> \[,
<span class="methodparam"><span class="type">mixed</span>
`$replacement`<span class="initializer"> = array()</span></span> \]\] )

Removes the elements designated by `offset` and `length` from the
`input` array, and replaces them with the elements of the `replacement`
array, if supplied.

> **Note**:
>
> Numerical keys in `input` are not preserved.

> **Note**: <span class="simpara"> If `replacement` is not an array, it
> will be
> <a href="/language/types/array.html#language.types.array.casting" class="link">typecast</a>
> to one (i.e. `(array) $replacement`). This may result in unexpected
> behavior when using an object or **`NULL`** `replacement`. </span>

### Parameters

`input`  
The input array.

`offset`  
If `offset` is positive then the start of the removed portion is at that
offset from the beginning of the `input` array.

If `offset` is negative then the start of the removed portion is at that
offset from the end of the `input` array.

`length`  
If `length` is omitted, removes everything from `offset` to the end of
the array.

If `length` is specified and is positive, then that many elements will
be removed.

If `length` is specified and is negative, then the end of the removed
portion will be that many elements from the end of the array.

If `length` is specified and is zero, no elements will be removed.

**Tip**
To remove everything from `offset` to the end of the array when
`replacement` is also specified, use `count($input)` for `length`.

`replacement`  
If `replacement` array is specified, then the removed elements are
replaced with elements from this array.

If `offset` and `length` are such that nothing is removed, then the
elements from the `replacement` array are inserted in the place
specified by the `offset`.

> **Note**:
>
> Keys in the `replacement` array are not preserved.

If `replacement` is just one element it is not necessary to put
*array()* or square brackets around it, unless the element is an array
itself, an object or **`NULL`**.

### Return Values

Returns an array consisting of the extracted elements.

### Examples

**Example \#1 <span class="function">array\_splice</span> examples**

``` php
<?php
$input = array("red", "green", "blue", "yellow");
array_splice($input, 2);
var_dump($input);

$input = array("red", "green", "blue", "yellow");
array_splice($input, 1, -1);
var_dump($input);

$input = array("red", "green", "blue", "yellow");
array_splice($input, 1, count($input), "orange");
var_dump($input);

$input = array("red", "green", "blue", "yellow");
array_splice($input, -1, 1, array("black", "maroon"));
var_dump($input);
?>
```

The above example will output:

    array(2) {
      [0]=>
      string(3) "red"
      [1]=>
      string(5) "green"
    }
    array(2) {
      [0]=>
      string(3) "red"
      [1]=>
      string(6) "yellow"
    }
    array(2) {
      [0]=>
      string(3) "red"
      [1]=>
      string(6) "orange"
    }
    array(5) {
      [0]=>
      string(3) "red"
      [1]=>
      string(5) "green"
      [2]=>
      string(4) "blue"
      [3]=>
      string(5) "black"
      [4]=>
      string(6) "maroon"
    }

**Example \#2 Equivalent statements to various <span
class="function">array\_splice</span> examples**

The following statements are equivalent:

``` php
<?php

// append two elements to $input
array_push($input, $x, $y);
array_splice($input, count($input), 0, array($x, $y));

// remove the last element of $input
array_pop($input);
array_splice($input, -1);

// remove the first element of $input
array_shift($input);
array_splice($input, 0, 1);

// insert an element at the start of $input
array_unshift($input, $x, $y);
array_splice($input, 0, 0, array($x, $y));

// replace the value in $input at index $x
$input[$x] = $y; // for arrays where key equals offset
array_splice($input, $x, 1, $y);

?>
```

### See Also

-   <span class="function">array\_merge</span>
-   <span class="function">array\_slice</span>
-   <span class="function">unset</span>

array\_sum
==========

Calculate the sum of values in an array

### Description

<span class="type">number</span> <span
class="methodname">array\_sum</span> ( <span class="methodparam"><span
class="type">array</span> `$array`</span> )

<span class="function">array\_sum</span> returns the sum of values in an
array.

### Parameters

`array`  
The input array.

### Return Values

Returns the sum of values as an integer or float; *0* if the `array` is
empty.

### Examples

**Example \#1 <span class="function">array\_sum</span> examples**

``` php
<?php
$a = array(2, 4, 6, 8);
echo "sum(a) = " . array_sum($a) . "\n";

$b = array("a" => 1.2, "b" => 2.3, "c" => 3.4);
echo "sum(b) = " . array_sum($b) . "\n";
?>
```

The above example will output:

    sum(a) = 20
    sum(b) = 6.9

array\_udiff\_assoc
===================

Computes the difference of arrays with additional index check, compares
data by a callback function

### Description

<span class="type">array</span> <span
class="methodname">array\_udiff\_assoc</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$value_compare_func`</span> )

Computes the difference of arrays with additional index check, compares
data by a callback function.

> **Note**: <span class="simpara"> Please note that this function only
> checks one dimension of a n-dimensional array. Of course you can check
> deeper dimensions by using, for example,
> *array\_udiff\_assoc($array1\[0\], $array2\[0\],
> "some\_comparison\_func");*. </span>

### Parameters

`array1`  
The first array.

`array2`  
The second array.

`value_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

<span class="function">array\_udiff\_assoc</span> returns an <span
class="type">array</span> containing all the values from `array1` that
are not present in any of the other arguments. Note that the keys are
used in the comparison unlike <span class="function">array\_diff</span>
and <span class="function">array\_udiff</span>. The comparison of
arrays' data is performed by using an user-supplied callback. In this
aspect the behaviour is opposite to the behaviour of <span
class="function">array\_diff\_assoc</span> which uses internal function
for comparison.

### Examples

**Example \#1 <span class="function">array\_udiff\_assoc</span>
example**

``` php
<?php
class cr {
    private $priv_member;
    function cr($val)
    {
        $this->priv_member = $val;
    }

    static function comp_func_cr($a, $b)
    {
        if ($a->priv_member === $b->priv_member) return 0;
        return ($a->priv_member > $b->priv_member)? 1:-1;
    }
}

$a = array("0.1" => new cr(9), "0.5" => new cr(12), 0 => new cr(23), 1=> new cr(4), 2 => new cr(-15),);
$b = array("0.2" => new cr(9), "0.5" => new cr(22), 0 => new cr(3), 1=> new cr(4), 2 => new cr(-15),);

$result = array_udiff_assoc($a, $b, array("cr", "comp_func_cr"));
print_r($result);
?>
```

The above example will output:

    Array
    (
        [0.1] => cr Object
            (
                [priv_member:private] => 9
            )

        [0.5] => cr Object
            (
                [priv_member:private] => 12
            )

        [0] => cr Object
            (
                [priv_member:private] => 23
            )
    )

In our example above you see the *"1" =\> new cr(4)* pair is present in
both arrays and thus it is not in the output from the function.

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_diff\_uassoc</span>
-   <span class="function">array\_udiff</span>
-   <span class="function">array\_udiff\_uassoc</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_uintersect</span>
-   <span class="function">array\_uintersect\_assoc</span>
-   <span class="function">array\_uintersect\_uassoc</span>

array\_udiff\_uassoc
====================

Computes the difference of arrays with additional index check, compares
data and indexes by a callback function

### Description

<span class="type">array</span> <span
class="methodname">array\_udiff\_uassoc</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$value_compare_func`</span> , <span class="methodparam"><span
class="type">callable</span> `$key_compare_func`</span> )

Computes the difference of arrays with additional index check, compares
data and indexes by a callback function.

Note that the keys are used in the comparison unlike <span
class="function">array\_diff</span> and <span
class="function">array\_udiff</span>.

### Parameters

`array1`  
The first array.

`array2`  
The second array.

`value_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

`key_compare_func`  
The comparison of keys (indices) is done also by the callback function
`key_compare_func`. This behaviour is unlike what <span
class="function">array\_udiff\_assoc</span> does, since the latter
compares the indices by using an internal function.

### Return Values

Returns an <span class="type">array</span> containing all the values
from `array1` that are not present in any of the other arguments.

### Examples

**Example \#1 <span class="function">array\_udiff\_uassoc</span>
example**

``` php
<?php
class cr {
    private $priv_member;
    function cr($val)
    {
        $this->priv_member = $val;
    }

    static function comp_func_cr($a, $b)
    {
        if ($a->priv_member === $b->priv_member) return 0;
        return ($a->priv_member > $b->priv_member)? 1:-1;
    }

    static function comp_func_key($a, $b)
    {
        if ($a === $b) return 0;
        return ($a > $b)? 1:-1;
    }
}
$a = array("0.1" => new cr(9), "0.5" => new cr(12), 0 => new cr(23), 1=> new cr(4), 2 => new cr(-15),);
$b = array("0.2" => new cr(9), "0.5" => new cr(22), 0 => new cr(3), 1=> new cr(4), 2 => new cr(-15),);

$result = array_udiff_uassoc($a, $b, array("cr", "comp_func_cr"), array("cr", "comp_func_key"));
print_r($result);
?>
```

The above example will output:

    Array
    (
        [0.1] => cr Object
            (
                [priv_member:private] => 9
            )

        [0.5] => cr Object
            (
                [priv_member:private] => 12
            )

        [0] => cr Object
            (
                [priv_member:private] => 23
            )
    )

In our example above you see the *"1" =\> new cr(4)* pair is present in
both arrays and thus it is not in the output from the function. Keep in
mind that you have to supply 2 callback functions.

### Notes

> **Note**: <span class="simpara"> Please note that this function only
> checks one dimension of a n-dimensional array. Of course you can check
> deeper dimensions by using, for example,
> *array\_udiff\_uassoc($array1\[0\], $array2\[0\],
> "data\_compare\_func", "key\_compare\_func");*. </span>

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_udiff</span>
-   <span class="function">array\_udiff\_assoc</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_uintersect</span>
-   <span class="function">array\_uintersect\_assoc</span>
-   <span class="function">array\_uintersect\_uassoc</span>

array\_udiff
============

Computes the difference of arrays by using a callback function for data
comparison

### Description

<span class="type">array</span> <span
class="methodname">array\_udiff</span> ( <span class="methodparam"><span
class="type">array</span> `$array1`</span> , <span
class="methodparam"><span class="type">array</span> `$array2`</span> \[,
<span class="methodparam"><span class="type">array</span> `$...`</span>
\], <span class="methodparam"><span class="type">callable</span>
`$value_compare_func`</span> )

Computes the difference of arrays by using a callback function for data
comparison. This is unlike <span class="function">array\_diff</span>
which uses an internal function for comparing the data.

### Parameters

`array1`  
The first array.

`array2`  
The second array.

`value_compare_func`  
The callback comparison function.

The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

Returns an array containing all the values of `array1` that are not
present in any of the other arguments.

### Examples

**Example \#1 <span class="function">array\_udiff</span> example using
stdClass Objects**

``` php
<?php
// Arrays to compare
$array1 = array(new stdclass, new stdclass,
                new stdclass, new stdclass,
               );

$array2 = array(
                new stdclass, new stdclass,
               );

// Set some properties for each object
$array1[0]->width = 11; $array1[0]->height = 3;
$array1[1]->width = 7;  $array1[1]->height = 1;
$array1[2]->width = 2;  $array1[2]->height = 9;
$array1[3]->width = 5;  $array1[3]->height = 7;

$array2[0]->width = 7;  $array2[0]->height = 5;
$array2[1]->width = 9;  $array2[1]->height = 2;

function compare_by_area($a, $b) {
    $areaA = $a->width * $a->height;
    $areaB = $b->width * $b->height;
    
    if ($areaA < $areaB) {
        return -1;
    } elseif ($areaA > $areaB) {
        return 1;
    } else {
        return 0;
    }
}

print_r(array_udiff($array1, $array2, 'compare_by_area'));
?>
```

The above example will output:

    Array
    (
        [0] => stdClass Object
            (
                [width] => 11
                [height] => 3
            )

        [1] => stdClass Object
            (
                [width] => 7
                [height] => 1
            )

    )

**Example \#2 <span class="function">array\_udiff</span> example using
DateTime Objects**

``` php
<?php
class MyCalendar {
    public $free = array();
    public $booked = array();

    public function __construct($week = 'now') {
        $start = new DateTime($week);
        $start->modify('Monday this week midnight');
        $end = clone $start;
        $end->modify('Friday this week midnight');
        $interval = new DateInterval('P1D');
        foreach (new DatePeriod($start, $interval, $end) as $freeTime) {
            $this->free[] = $freeTime;
        }
    }

    public function bookAppointment(DateTime $date, $note) {
        $this->booked[] = array('date' => $date->modify('midnight'), 'note' => $note);
    }

    public function checkAvailability() {
        return array_udiff($this->free, $this->booked, array($this, 'customCompare'));
    }
    
    public function customCompare($free, $booked) {
        if (is_array($free)) $a = $free['date'];
        else $a = $free;
        if (is_array($booked)) $b = $booked['date'];
        else $b = $booked;
        if ($a == $b) {
            return 0;
        } elseif ($a > $b) {
            return 1;
        } else {
            return -1;
        }
    }
}

// Create a calendar for weekly appointments
$myCalendar = new MyCalendar;

// Book some appointments for this week
$myCalendar->bookAppointment(new DateTime('Monday this week'), "Cleaning GoogleGuy's apartment.");
$myCalendar->bookAppointment(new DateTime('Wednesday this week'), "Going on a snowboarding trip.");
$myCalendar->bookAppointment(new DateTime('Friday this week'), "Fixing buggy code.");

// Check availability of days by comparing $booked dates against $free dates
echo "I'm available on the following days this week...\n\n";
foreach ($myCalendar->checkAvailability() as $free) {
    echo $free->format('l'), "\n"; 
}
echo "\n\n";
echo "I'm busy on the following days this week...\n\n";
foreach ($myCalendar->booked as $booked) {
    echo $booked['date']->format('l'), ": ", $booked['note'], "\n"; 
}
?>
```

The above example will output:

    I'm available on the following days this week...

    Tuesday
    Thursday


    I'm busy on the following days this week...

    Monday: Cleaning GoogleGuy's apartment.
    Wednesday: Going on a snowboarding trip.
    Friday: Fixing buggy code.

### Notes

> **Note**: <span class="simpara"> Please note that this function only
> checks one dimension of a n-dimensional array. Of course you can check
> deeper dimensions by using *array\_udiff($array1\[0\], $array2\[0\],
> "data\_compare\_func");*. </span>

### See Also

-   <span class="function">array\_diff</span>
-   <span class="function">array\_diff\_assoc</span>
-   <span class="function">array\_diff\_uassoc</span>
-   <span class="function">array\_udiff\_assoc</span>
-   <span class="function">array\_udiff\_uassoc</span>
-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_uintersect</span>
-   <span class="function">array\_uintersect\_assoc</span>
-   <span class="function">array\_uintersect\_uassoc</span>

array\_uintersect\_assoc
========================

Computes the intersection of arrays with additional index check,
compares data by a callback function

### Description

<span class="type">array</span> <span
class="methodname">array\_uintersect\_assoc</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$value_compare_func`</span> )

Computes the intersection of arrays with additional index check,
compares data by a callback function.

Note that the keys are used in the comparison unlike in <span
class="function">array\_uintersect</span>. The data is compared by using
a callback function.

### Parameters

`array1`  
The first array.

`array2`  
The second array.

`value_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

Returns an array containing all the values of `array1` that are present
in all the arguments.

### Examples

**Example \#1 <span class="function">array\_uintersect\_assoc</span>
example**

``` php
<?php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");

print_r(array_uintersect_assoc($array1, $array2, "strcasecmp"));
?>
```

The above example will output:

    Array
    (
        [a] => green
    )

### See Also

-   <span class="function">array\_uintersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_intersect\_uassoc</span>
-   <span class="function">array\_uintersect\_uassoc</span>

array\_uintersect\_uassoc
=========================

Computes the intersection of arrays with additional index check,
compares data and indexes by separate callback functions

### Description

<span class="type">array</span> <span
class="methodname">array\_uintersect\_uassoc</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$value_compare_func`</span> , <span class="methodparam"><span
class="type">callable</span> `$key_compare_func`</span> )

Computes the intersection of arrays with additional index check,
compares data and indexes by separate callback functions.

### Parameters

`array1`  
The first array.

`array2`  
The second array.

`value_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

`key_compare_func`  
Key comparison callback function.

### Return Values

Returns an array containing all the values of `array1` that are present
in all the arguments.

### Examples

**Example \#1 <span class="function">array\_uintersect\_uassoc</span>
example**

``` php
<?php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");

print_r(array_uintersect_uassoc($array1, $array2, "strcasecmp", "strcasecmp"));
?>
```

The above example will output:

    Array
    (
        [a] => green
        [b] => brown
    )

### See Also

-   <span class="function">array\_uintersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_intersect\_uassoc</span>
-   <span class="function">array\_uintersect\_assoc</span>

array\_uintersect
=================

Computes the intersection of arrays, compares data by a callback
function

### Description

<span class="type">array</span> <span
class="methodname">array\_uintersect</span> ( <span
class="methodparam"><span class="type">array</span> `$array1`</span> ,
<span class="methodparam"><span class="type">array</span>
`$array2`</span> \[, <span class="methodparam"><span
class="type">array</span> `$...`</span> \], <span
class="methodparam"><span class="type">callable</span>
`$value_compare_func`</span> )

Computes the intersection of arrays, compares data by a callback
function.

### Parameters

`array1`  
The first array.

`array2`  
The second array.

`value_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

Returns an array containing all the values of `array1` that are present
in all the arguments.

### Examples

**Example \#1 <span class="function">array\_uintersect</span> example**

``` php
<?php
$array1 = array("a" => "green", "b" => "brown", "c" => "blue", "red");
$array2 = array("a" => "GREEN", "B" => "brown", "yellow", "red");

print_r(array_uintersect($array1, $array2, "strcasecmp"));
?>
```

The above example will output:

    Array
    (
        [a] => green
        [b] => brown
        [0] => red
    )

### See Also

-   <span class="function">array\_intersect</span>
-   <span class="function">array\_intersect\_assoc</span>
-   <span class="function">array\_uintersect\_assoc</span>
-   <span class="function">array\_uintersect\_uassoc</span>

array\_unique
=============

Removes duplicate values from an array

### Description

<span class="type">array</span> <span
class="methodname">array\_unique</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$sort_flags`<span class="initializer"> = SORT\_STRING</span></span> \]
)

Takes an input `array` and returns a new array without duplicate values.

Note that keys are preserved. If multiple elements compare equal under
the given `sort_flags`, then the key and value of the first equal
element will be retained.

> **Note**: <span class="simpara"> Two elements are considered equal if
> and only if *(string) $elem1 === (string) $elem2* i.e. when the string
> representation is the same, the first element will be used. </span>

### Parameters

`array`  
The input array.

`sort_flags`  
The optional second parameter `sort_flags` may be used to modify the
sorting behavior using these values:

Sorting type flags:

-   <span class="simpara">**`SORT_REGULAR`** - compare items normally
    (don't change types)</span>
-   <span class="simpara">**`SORT_NUMERIC`** - compare items
    numerically</span>
-   <span class="simpara">**`SORT_STRING`** - compare items as
    strings</span>
-   <span class="simpara">**`SORT_LOCALE_STRING`** - compare items as
    strings, based on the current locale. </span>

### Return Values

Returns the filtered array.

### Changelog

| Version | Description                                                                                                                                                                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | If `sort_flags` is **`SORT_STRING`**, formerly `array` has been copied and non-unique elements have been removed (without packing the array afterwards), but now a new array is built by adding the unique elements. This can result in different numeric indexes. |
| 5.2.10  | Changed the default value of `sort_flags` back to **`SORT_STRING`**.                                                                                                                                                                                               |
| 5.2.9   | Added the optional `sort_flags` defaulting to **`SORT_REGULAR`**. Prior to 5.2.9, this function used to sort the array with **`SORT_STRING`** internally.                                                                                                          |

### Examples

**Example \#1 <span class="function">array\_unique</span> example**

``` php
<?php
$input = array("a" => "green", "red", "b" => "green", "blue", "red");
$result = array_unique($input);
print_r($result);
?>
```

The above example will output:

    Array
    (
        [a] => green
        [0] => red
        [1] => blue
    )

**Example \#2 <span class="function">array\_unique</span> and types**

``` php
<?php
$input = array(4, "4", "3", 4, 3, "3");
$result = array_unique($input);
var_dump($result);
?>
```

The above example will output:

    array(2) {
      [0] => int(4)
      [2] => string(1) "3"
    }

### See Also

-   <span class="function">array\_count\_values</span>

### Notes

> **Note**: <span class="simpara"> Note that <span
> class="function">array\_unique</span> is not intended to work on multi
> dimensional arrays. </span>

array\_unshift
==============

Prepend one or more elements to the beginning of an array

### Description

<span class="type">int</span> <span
class="methodname">array\_unshift</span> ( <span
class="methodparam"><span class="type">array</span> `&$array`</span> \[,
<span class="methodparam"><span class="type">mixed</span> `$...`</span>
\] )

<span class="function">array\_unshift</span> prepends passed elements to
the front of the `array`. Note that the list of elements is prepended as
a whole, so that the prepended elements stay in the same order. All
numerical array keys will be modified to start counting from zero while
literal keys won't be changed.

### Parameters

`array`  
The input array.

`...`  
The values to prepend.

### Return Values

Returns the new number of elements in the `array`.

### Changelog

| Version | Description                                                                                                    |
|---------|----------------------------------------------------------------------------------------------------------------|
| 7.3.0   | This function can now be called with only one parameter. Formerly, at least two parameters have been required. |

### Examples

**Example \#1 <span class="function">array\_unshift</span> example**

``` php
<?php
$queue = array("orange", "banana");
array_unshift($queue, "apple", "raspberry");
print_r($queue);
?>
```

The above example will output:

    Array
    (
        [0] => apple
        [1] => raspberry
        [2] => orange
        [3] => banana
    )

### See Also

-   <span class="function">array\_shift</span>
-   <span class="function">array\_push</span>
-   <span class="function">array\_pop</span>

array\_values
=============

Return all the values of an array

### Description

<span class="type">array</span> <span
class="methodname">array\_values</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

<span class="function">array\_values</span> returns all the values from
the `array` and indexes the array numerically.

### Parameters

`array`  
The array.

### Return Values

Returns an indexed array of values.

### Examples

**Example \#1 <span class="function">array\_values</span> example**

``` php
<?php
$array = array("size" => "XL", "color" => "gold");
print_r(array_values($array));
?>
```

The above example will output:

    Array
    (
        [0] => XL
        [1] => gold
    )

### See Also

-   <span class="function">array\_keys</span>
-   <span class="function">array\_combine</span>

array\_walk\_recursive
======================

Apply a user function recursively to every member of an array

### Description

<span class="type">bool</span> <span
class="methodname">array\_walk\_recursive</span> ( <span
class="methodparam"><span class="type">array</span> `&$array`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$userdata`<span class="initializer"> =
**`NULL`**</span></span> \] )

Applies the user-defined `callback` function to each element of the
`array`. This function will recurse into deeper arrays.

### Parameters

`array`  
The input array.

`callback`  
Typically, `callback` takes on two parameters. The `array` parameter's
value being the first, and the key/index second.

> **Note**:
>
> If `callback` needs to be working with the actual values of the array,
> specify the first parameter of `callback` as a
> <a href="/language/references.html" class="link">reference</a>. Then,
> any changes made to those elements will be made in the original array
> itself.

`userdata`  
If the optional `userdata` parameter is supplied, it will be passed as
the third parameter to the `callback`.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">array\_walk\_recursive</span>
example**

``` php
<?php
$sweet = array('a' => 'apple', 'b' => 'banana');
$fruits = array('sweet' => $sweet, 'sour' => 'lemon');

function test_print($item, $key)
{
    echo "$key holds $item\n";
}

array_walk_recursive($fruits, 'test_print');
?>
```

The above example will output:

    a holds apple
    b holds banana
    sour holds lemon

You may notice that the key '*sweet*' is never displayed. Any key that
holds an <span class="type">array</span> will not be passed to the
function.

### See Also

-   <span class="function">array\_walk</span>
-   information about the
    <a href="/language/pseudo-types.html#language.types.callback" class="link">callback</a>
    type

array\_walk
===========

Apply a user supplied function to every member of an array

### Description

<span class="type">bool</span> <span
class="methodname">array\_walk</span> ( <span class="methodparam"><span
class="type">array</span> `&$array`</span> , <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$userdata`<span class="initializer"> =
**`NULL`**</span></span> \] )

Applies the user-defined `callback` function to each element of the
`array` array.

<span class="function">array\_walk</span> is not affected by the
internal array pointer of `array`. <span
class="function">array\_walk</span> will walk through the entire array
regardless of pointer position.

### Parameters

`array`  
The input array.

`callback`  
Typically, `callback` takes on two parameters. The `array` parameter's
value being the first, and the key/index second.

> **Note**:
>
> If `callback` needs to be working with the actual values of the array,
> specify the first parameter of `callback` as a
> <a href="/language/references.html" class="link">reference</a>. Then,
> any changes made to those elements will be made in the original array
> itself.

> **Note**:
>
> Many internal functions (for example <span
> class="function">strtolower</span>) will throw a warning if more than
> the expected number of argument are passed in and are not usable
> directly as a `callback`.

Only the values of the `array` may potentially be changed; its structure
cannot be altered, i.e., the programmer cannot add, unset or reorder
elements. If the callback does not respect this requirement, the
behavior of this function is undefined, and unpredictable.

`userdata`  
If the optional `userdata` parameter is supplied, it will be passed as
the third parameter to the `callback`.

### Return Values

Returns **`TRUE`**.

### Errors/Exceptions

As of PHP 7.1.0, an <span class="classname">ArgumentCountError</span>
will be thrown if the `callback` function requires more than 2
parameters (the value and key of the array member). Previously, if the
`callback` function required more than 2 parameters, an error of level
<a href="/errorfunc/constants.html" class="link">E_WARNING</a> would be
generated each time <span class="function">array\_walk</span> calls
`callback`.

### Examples

**Example \#1 <span class="function">array\_walk</span> example**

``` php
<?php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");

function test_alter(&$item1, $key, $prefix)
{
    $item1 = "$prefix: $item1";
}

function test_print($item2, $key)
{
    echo "$key. $item2<br />\n";
}

echo "Before ...:\n";
array_walk($fruits, 'test_print');

array_walk($fruits, 'test_alter', 'fruit');
echo "... and after:\n";

array_walk($fruits, 'test_print');
?>
```

The above example will output:

    Before ...:
    d. lemon
    a. orange
    b. banana
    c. apple
    ... and after:
    d. fruit: lemon
    a. fruit: orange
    b. fruit: banana
    c. fruit: apple

### See Also

-   <span class="function">array\_walk\_recursive</span>
-   <span class="function">iterator\_apply</span>
-   <span class="function">list</span>
-   <span class="function">each</span>
-   <span class="function">call\_user\_func\_array</span>
-   <span class="function">array\_map</span>
-   information about the
    <a href="/language/pseudo-types.html#language.types.callback" class="link">callback</a>
    type
-   <a href="/control-structures/foreach.html" class="link">foreach</a>

array
=====

Create an array

### Description

<span class="type">array</span> <span class="methodname">array</span>
(\[ <span class="methodparam"><span class="type">mixed</span>
`$...`</span> \] )

Creates an array. Read the section on the
<a href="/language/types/array.html" class="link">array type</a> for
more information on what an array is.

### Parameters

`...`  
Syntax "index =\> values", separated by commas, define index and values.
index may be of type string or integer. When index is omitted, an
integer index is automatically generated, starting at 0. If index is an
integer, next generated index will be the biggest integer index + 1.
Note that when two identical index are defined, the last overwrite the
first.

Having a trailing comma after the last defined array entry, while
unusual, is a valid syntax.

### Return Values

Returns an array of the parameters. The parameters can be given an index
with the *=\>* operator. Read the section on the
<a href="/language/types/array.html" class="link">array type</a> for
more information on what an array is.

### Examples

The following example demonstrates how to create a two-dimensional
array, how to specify keys for associative arrays, and how to
skip-and-continue numeric indices in normal arrays.

**Example \#1 <span class="function">array</span> example**

``` php
<?php
$fruits = array (
    "fruits"  => array("a" => "orange", "b" => "banana", "c" => "apple"),
    "numbers" => array(1, 2, 3, 4, 5, 6),
    "holes"   => array("first", 5 => "second", "third")
);
?>
```

**Example \#2 Automatic index with <span class="function">array</span>**

``` php
<?php
$array = array(1, 1, 1, 1,  1, 8 => 1,  4 => 1, 19, 3 => 13);
print_r($array);
?>
```

The above example will output:

    Array
    (
        [0] => 1
        [1] => 1
        [2] => 1
        [3] => 13
        [4] => 1
        [8] => 1
        [9] => 19
    )

Note that index '3' is defined twice, and keep its final value of 13.
Index 4 is defined after index 8, and next generated index (value 19) is
9, since biggest index was 8.

This example creates a 1-based array.

**Example \#3 1-based index with <span class="function">array</span>**

``` php
<?php
$firstquarter = array(1 => 'January', 'February', 'March');
print_r($firstquarter);
?>
```

The above example will output:

    Array
    (
        [1] => January
        [2] => February
        [3] => March
    )

As in Perl, you can access a value from the array inside double quotes.
However, with PHP you'll need to enclose your array between curly
braces.

**Example \#4 Accessing an array inside double quotes**

``` php
<?php

$foo = array('bar' => 'baz');
echo "Hello {$foo['bar']}!"; // Hello baz!

?>
```

### Notes

> **Note**:
>
> <span class="function">array</span> is a language construct used to
> represent literal arrays, and not a regular function.

### See Also

-   <span class="function">array\_pad</span>
-   <span class="function">list</span>
-   <span class="function">count</span>
-   <span class="function">range</span>
-   <a href="/control-structures/foreach.html" class="link">foreach</a>
-   The <a href="/language/types/array.html" class="link">array</a> type

arsort
======

Sort an array in reverse order and maintain index association

### Description

<span class="type">bool</span> <span class="methodname">arsort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> \[, <span class="methodparam"><span
class="type">int</span> `$sort_flags`<span class="initializer"> =
SORT\_REGULAR</span></span> \] )

This function sorts an array such that array indices maintain their
correlation with the array elements they are associated with.

This is used mainly when sorting associative arrays where the actual
element order is significant.

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array`  
The input array.

`sort_flags`  
You may modify the behavior of the sort using the optional parameter
`sort_flags`, for details see <span class="function">sort</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">arsort</span> example**

``` php
<?php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");
arsort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
?>
```

The above example will output:

    a = orange
    d = lemon
    b = banana
    c = apple

The fruits have been sorted in reverse alphabetical order, and the index
associated with each element has been maintained.

### See Also

-   <span class="function">asort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

asort
=====

Sort an array and maintain index association

### Description

<span class="type">bool</span> <span class="methodname">asort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> \[, <span class="methodparam"><span
class="type">int</span> `$sort_flags`<span class="initializer"> =
SORT\_REGULAR</span></span> \] )

This function sorts an array such that array indices maintain their
correlation with the array elements they are associated with. This is
used mainly when sorting associative arrays where the actual element
order is significant.

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array`  
The input array.

`sort_flags`  
You may modify the behavior of the sort using the optional parameter
`sort_flags`, for details see <span class="function">sort</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">asort</span> example**

``` php
<?php
$fruits = array("d" => "lemon", "a" => "orange", "b" => "banana", "c" => "apple");
asort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
?>
```

The above example will output:

    c = apple
    b = banana
    d = lemon
    a = orange

The fruits have been sorted in alphabetical order, and the index
associated with each element has been maintained.

### See Also

-   <span class="function">arsort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

compact
=======

Create array containing variables and their values

### Description

<span class="type">array</span> <span class="methodname">compact</span>
( <span class="methodparam"><span class="type">mixed</span>
`$varname1`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \] )

Creates an array containing variables and their values.

For each of these, <span class="function">compact</span> looks for a
variable with that name in the current symbol table and adds it to the
output array such that the variable name becomes the key and the
contents of the variable become the value for that key. In short, it
does the opposite of <span class="function">extract</span>.

> **Note**:
>
> Before PHP 7.3, any strings that are not set will silently be skipped.

### Parameters

`varname1`  
<span class="function">compact</span> takes a variable number of
parameters. Each parameter can be either a string containing the name of
the variable, or an array of variable names. The array can contain other
arrays of variable names inside it; <span
class="function">compact</span> handles it recursively.

### Return Values

Returns the output array with all the variables added to it.

### Errors/Exceptions

<span class="function">compact</span> issues an E\_NOTICE level error if
a given string refers to an unset variable.

### Changelog

| Version | Description                                                                                                                                                                 |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | <span class="function">compact</span> now issues an E\_NOTICE level error if a given string refers to an unset variable. Formerly, such strings have been silently skipped. |

### Examples

**Example \#1 <span class="function">compact</span> example**

``` php
<?php
$city  = "San Francisco";
$state = "CA";
$event = "SIGGRAPH";

$location_vars = array("city", "state");

$result = compact("event", $location_vars);
print_r($result);
?>
```

The above example will output:

    Array
    (
        [event] => SIGGRAPH
        [city] => San Francisco
        [state] => CA
    )

### Notes

> **Note**: **Gotcha**  
>
> Because
> <a href="/language/variables/variable.html" class="link">variable variables</a>
> may not be used with PHP's
> <a href="/language/variables/superglobals.html" class="link">Superglobal arrays</a>
> within functions, the Superglobal arrays may not be passed into <span
> class="function">compact</span>.

### See Also

-   <span class="function">extract</span>

count
=====

Count all elements in an array, or something in an object

### Description

<span class="type">int</span> <span class="methodname">count</span> (
<span class="methodparam"><span class="type">mixed</span>
`$array_or_countable`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
COUNT\_NORMAL</span></span> \] )

Counts all elements in an array, or something in an object.

For objects, if you have <a href="/ref/spl.html" class="link">SPL</a>
installed, you can hook into <span class="function">count</span> by
implementing interface <span class="classname">Countable</span>. The
interface has exactly one method, <span
class="methodname">Countable::count</span>, which returns the return
value for the <span class="function">count</span> function.

Please see the
<a href="/language/types/array.html" class="link">Array</a> section of
the manual for a detailed explanation of how arrays are implemented and
used in PHP.

### Parameters

`array_or_countable`  
An array or <span class="classname">Countable</span> object.

`mode`  
If the optional `mode` parameter is set to **`COUNT_RECURSIVE`** (or 1),
<span class="function">count</span> will recursively count the array.
This is particularly useful for counting all the elements of a
multidimensional array.

**Caution**
<span class="function">count</span> can detect recursion to avoid an
infinite loop, but will emit an **`E_WARNING`** every time it does (in
case the array contains itself more than once) and return a count higher
than may be expected.

### Return Values

Returns the number of elements in `array_or_countable`. When the
parameter is neither an array nor an object with implemented <span
class="classname">Countable</span> interface, *1* will be returned.
There is one exception, if `array_or_countable` is **`NULL`**, *0* will
be returned.

### Examples

**Example \#1 <span class="function">count</span> example**

``` php
<?php
$a[0] = 1;
$a[1] = 3;
$a[2] = 5;
var_dump(count($a));

$b[0]  = 7;
$b[5]  = 9;
$b[10] = 11;
var_dump(count($b));

var_dump(count(null));

var_dump(count(false));
?>
```

The above example will output:

    int(3)
    int(3)

    Warning: count(): Parameter must be an array or an object that implements Countable in … on line 12 // as of PHP 7.2
    int(0)

    Warning: count(): Parameter must be an array or an object that implements Countable in … on line 14 // as of PHP 7.2
    int(1)

**Example \#2 Recursive <span class="function">count</span> example**

``` php
<?php
$food = array('fruits' => array('orange', 'banana', 'apple'),
              'veggie' => array('carrot', 'collard', 'pea'));

// recursive count
echo count($food, COUNT_RECURSIVE); // output 8

// normal count
echo count($food); // output 2

?>
```

### Changelog

| Version | Description                                                                                                                           |
|---------|---------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="function">count</span> will now yield a warning on invalid countable types passed to the `array_or_countable` parameter. |

### See Also

-   <span class="function">is\_array</span>
-   <span class="function">isset</span>
-   <span class="function">empty</span>
-   <span class="function">strlen</span>
-   <span class="function">is\_countable</span>

current
=======

Return the current element in an array

### Description

<span class="type">mixed</span> <span class="methodname">current</span>
( <span class="methodparam"><span class="type">array</span>
`$array`</span> )

Every array has an internal pointer to its "current" element, which is
initialized to the first element inserted into the array.

### Parameters

`array`  
The array.

### Return Values

The <span class="function">current</span> function simply returns the
value of the array element that's currently being pointed to by the
internal pointer. It does not move the pointer in any way. If the
internal pointer points beyond the end of the elements list or the array
is empty, <span class="function">current</span> returns **`FALSE`**.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Changelog

| Version | Description                                                                                                                   |
|---------|-------------------------------------------------------------------------------------------------------------------------------|
| 7.0.0   | `array` is now always passed by value. Prior to this version, it was passed by reference if possible, and by value otherwise. |

### Examples

**Example \#1 Example use of <span class="function">current</span> and
friends**

``` php
<?php
$transport = array('foot', 'bike', 'car', 'plane');
$mode = current($transport); // $mode = 'foot';
$mode = next($transport);    // $mode = 'bike';
$mode = current($transport); // $mode = 'bike';
$mode = prev($transport);    // $mode = 'foot';
$mode = end($transport);     // $mode = 'plane';
$mode = current($transport); // $mode = 'plane';

$arr = array();
var_dump(current($arr)); // bool(false)

$arr = array(array());
var_dump(current($arr)); // array(0) { }
?>
```

### Notes

> **Note**: <span class="simpara"> The end of an array and the result of
> calling <span class="function">current</span> on an empty array are
> indistinguishable from a <span class="type">boolean</span> **`FALSE`**
> element. To properly traverse an array which may contain **`FALSE`**
> elements, see the <span class="function">foreach</span> function.
> </span> <span class="simpara"> To still use <span
> class="function">current</span> and properly check if the value is
> really an element of the array, the <span class="function">key</span>
> of the <span class="function">current</span> element should be checked
> to be strictly different from **`NULL`**. </span>

### See Also

-   <span class="function">end</span>
-   <span class="function">key</span>
-   <span class="function">each</span>
-   <span class="function">prev</span>
-   <span class="function">reset</span>
-   <span class="function">next</span>

each
====

Return the current key and value pair from an array and advance the
array cursor

**Warning**

This function has been *DEPRECATED* as of PHP 7.2.0. Relying on this
function is highly discouraged.

### Description

<span class="type">array</span> <span class="methodname">each</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> )

Return the current key and value pair from an array and advance the
array cursor.

After <span class="function">each</span> has executed, the array cursor
will be left on the next element of the array, or past the last element
if it hits the end of the array. You have to use <span
class="function">reset</span> if you want to traverse the array again
using each.

### Parameters

`array`  
The input array.

### Return Values

Returns the current key and value pair from the array `array`. This pair
is returned in a four-element array, with the keys *0*, *1*, *key*, and
*value*. Elements *0* and *key* contain the key name of the array
element, and *1* and *value* contain the data.

If the internal pointer for the array points past the end of the array
contents, <span class="function">each</span> returns **`FALSE`**.

### Examples

**Example \#1 <span class="function">each</span> examples**

``` php
<?php
$foo = array("bob", "fred", "jussi", "jouni", "egon", "marliese");
$bar = each($foo);
print_r($bar);
?>
```

`$bar` now contains the following key/value pairs:

    Array
    (
        [1] => bob
        [value] => bob
        [0] => 0
        [key] => 0
    )

``` php
<?php
$foo = array("Robert" => "Bob", "Seppo" => "Sepi");
$bar = each($foo);
print_r($bar);
?>
```

`$bar` now contains the following key/value pairs:

    Array
    (
        [1] => Bob
        [value] => Bob
        [0] => Robert
        [key] => Robert
    )

<span class="function">each</span> is typically used in conjunction with
<span class="function">list</span> to traverse an array, here's an
example:

**Example \#2 Traversing an array with <span
class="function">each</span>**

``` php
<?php
$fruit = array('a' => 'apple', 'b' => 'banana', 'c' => 'cranberry');

reset($fruit);
while (list($key, $val) = each($fruit)) {
    echo "$key => $val\n";
}
?>
```

The above example will output:

    a => apple
    b => banana
    c => cranberry

**Caution**

Because assigning an array to another variable resets the original
array's pointer, our example above would cause an endless loop had we
assigned `$fruit` to another variable inside the loop.

**Warning**

<span class="function">each</span> will also accept objects, but may
return unexpected results. It's therefore not recommended to iterate
though object properties with <span class="function">each</span>.

### See Also

-   <span class="function">key</span>
-   <span class="function">list</span>
-   <span class="function">current</span>
-   <span class="function">reset</span>
-   <span class="function">next</span>
-   <span class="function">prev</span>
-   <a href="/control-structures/foreach.html" class="link">foreach</a>
-   <a href="/language/oop5/iterations.html" class="link">Object Iteration</a>

end
===

Set the internal pointer of an array to its last element

### Description

<span class="type">mixed</span> <span class="methodname">end</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> )

<span class="function">end</span> advances `array`'s internal pointer to
the last element, and returns its value.

### Parameters

`array`  
The array. This array is passed by reference because it is modified by
the function. This means you must pass it a real variable and not a
function returning an array because only actual variables may be passed
by reference.

### Return Values

Returns the value of the last element or **`FALSE`** for empty array.

### Examples

**Example \#1 <span class="function">end</span> example**

``` php
<?php

$fruits = array('apple', 'banana', 'cranberry');
echo end($fruits); // cranberry

?>
```

### See Also

-   <span class="function">current</span>
-   <span class="function">each</span>
-   <span class="function">prev</span>
-   <span class="function">reset</span>
-   <span class="function">next</span>
-   <span class="function">array\_key\_last</span>

extract
=======

Import variables into the current symbol table from an array

### Description

<span class="type">int</span> <span class="methodname">extract</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
EXTR\_OVERWRITE</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$prefix`<span class="initializer"> =
**`NULL`**</span></span> \]\] )

Import variables from an array into the current symbol table.

Checks each key to see whether it has a valid variable name. It also
checks for collisions with existing variables in the symbol table.

**Warning**

Do not use <span class="function">extract</span> on untrusted data, like
user input (e.g. `$_GET`, `$_FILES`).

### Parameters

`array`  
An associative array. This function treats keys as variable names and
values as variable values. For each key/value pair it will create a
variable in the current symbol table, subject to `flags` and `prefix`
parameters.

You must use an associative array; a numerically indexed array will not
produce results unless you use **`EXTR_PREFIX_ALL`** or
**`EXTR_PREFIX_INVALID`**.

`flags`  
The way invalid/numeric keys and collisions are treated is determined by
the extraction `flags`. It can be one of the following values:

**`EXTR_OVERWRITE`**  
<span class="simpara"> If there is a collision, overwrite the existing
variable. </span>

**`EXTR_SKIP`**  
<span class="simpara"> If there is a collision, don't overwrite the
existing variable. </span>

**`EXTR_PREFIX_SAME`**  
<span class="simpara">If there is a collision, prefix the variable name
with `prefix`. </span>

**`EXTR_PREFIX_ALL`**  
<span class="simpara"> Prefix all variable names with `prefix`. </span>

**`EXTR_PREFIX_INVALID`**  
<span class="simpara"> Only prefix invalid/numeric variable names with
`prefix`. </span>

**`EXTR_IF_EXISTS`**  
<span class="simpara"> Only overwrite the variable if it already exists
in the current symbol table, otherwise do nothing. This is useful for
defining a list of valid variables and then extracting only those
variables you have defined out of `$_REQUEST`, for example. </span>

**`EXTR_PREFIX_IF_EXISTS`**  
<span class="simpara"> Only create prefixed variable names if the
non-prefixed version of the same variable exists in the current symbol
table. </span>

**`EXTR_REFS`**  
<span class="simpara"> Extracts variables as references. This
effectively means that the values of the imported variables are still
referencing the values of the `array` parameter. You can use this flag
on its own or combine it with any other flag by OR'ing the `flags`.
</span>

If `flags` is not specified, it is assumed to be **`EXTR_OVERWRITE`**.

`prefix`  
Note that `prefix` is only required if `flags` is
**`EXTR_PREFIX_SAME`**, **`EXTR_PREFIX_ALL`**, **`EXTR_PREFIX_INVALID`**
or **`EXTR_PREFIX_IF_EXISTS`**. If the prefixed result is not a valid
variable name, it is not imported into the symbol table. Prefixes are
automatically separated from the array key by an underscore character.

### Return Values

Returns the number of variables successfully imported into the symbol
table.

### Examples

**Example \#1 <span class="function">extract</span> example**

A possible use for <span class="function">extract</span> is to import
into the symbol table variables contained in an associative array
returned by <span class="function">wddx\_deserialize</span>.

``` php
<?php

/* Suppose that $var_array is an array returned from
   wddx_deserialize */

$size = "large";
$var_array = array("color" => "blue",
                   "size"  => "medium",
                   "shape" => "sphere");
extract($var_array, EXTR_PREFIX_SAME, "wddx");

echo "$color, $size, $shape, $wddx_size\n";

?>
```

The above example will output:

    blue, large, sphere, medium

The `$size` wasn't overwritten because we specified
**`EXTR_PREFIX_SAME`**, which resulted in `$wddx_size` being created. If
**`EXTR_SKIP`** was specified, then `$wddx_size` wouldn't even have been
created. **`EXTR_OVERWRITE`** would have caused `$size` to have value
"medium", and **`EXTR_PREFIX_ALL`** would result in new variables being
named `$wddx_color`, `$wddx_size`, and `$wddx_shape`.

### Notes

**Warning**

Do not use <span class="function">extract</span> on untrusted data, like
user input (i.e. `$_GET`, `$_FILES`, etc.). If you do, for example if
you want to temporarily run old code that relied on
<a href="/security/globals.html" class="link">register_globals</a>, make
sure you use one of the non-overwriting `flags` values such as
**`EXTR_SKIP`** and be aware that you should extract in the same order
that's defined in
<a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
within the
<a href="/ini.html" class="link"><var class="filename">php.ini</var></a>.

> **Note**:
>
> If you still have
> <a href="/security/globals.html" class="link">register_globals</a> and
> it is turned on, if you use <span class="function">extract</span> on
> `$_FILES` and specify **`EXTR_SKIP`**, you may be surprised at the
> results.
>
> **Warning**
>
> This is not recommended practice and is only documented here for
> completeness. The use of
> <a href="/security/globals.html" class="link">register_globals</a> is
> deprecated and calling <span class="function">extract</span> on
> untrusted data such as `$_FILES` is, as noted above, a potential
> security risk. If you encounter this issue, it means that you are
> using at least two poor coding practices.
>
> ``` php
> <?php
>
> /* Suppose that $testfile is the name of a file upload input
>    and that register_globals is turned on. */
>
> var_dump($testfile);
> extract($_FILES, EXTR_SKIP);
> var_dump($testfile);
> var_dump($testfile['tmp_name']);
>
> ?>
> ```
>
> <span class="simpara"> You might expect to see something like the
> following: </span>
>
>     string(14) "/tmp/phpgCCPX8"
>     array(5) {
>       ["name"]=>
>       string(10) "somefile.txt"
>       ["type"]=>
>       string(24) "application/octet-stream"
>       ["tmp_name"]=>
>       string(14) "/tmp/phpgCCPX8"
>       ["error"]=>
>       int(0)
>       ["size"]=>
>       int(4208)
>     }
>     string(14) "/tmp/phpgCCPX8"
>
> <span class="simpara"> However, you would instead see something like
> this: </span>
>
>     string(14) "/tmp/phpgCCPX8"
>     string(14) "/tmp/phpgCCPX8"
>     string(1) "/"
>
> This is due to the fact that since
> <a href="/security/globals.html" class="link">register_globals</a> is
> turned on, `$testfile` already exists in the global scope when <span
> class="function">extract</span> is called. And since **`EXTR_SKIP`**
> is specified, `$testfile` is not overwritten with the contents of the
> **`$_FILES`** array so `$testfile` remains a string. Because
> <a href="/language/types/string.html#language.types.string.substr" class="link">strings may be accessed using array syntax</a>
> and the non-numeric string *tmp\_name* is interpreted as *0*, PHP sees
> `$testfile['tmp_name']` as `$testfile[0]`.

### See Also

-   <span class="function">compact</span>
-   <span class="function">list</span>

in\_array
=========

Checks if a value exists in an array

### Description

<span class="type">bool</span> <span class="methodname">in\_array</span>
( <span class="methodparam"><span class="type">mixed</span>
`$needle`</span> , <span class="methodparam"><span
class="type">array</span> `$haystack`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$strict`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Searches for `needle` in `haystack` using loose comparison unless
`strict` is set.

### Parameters

`needle`  
The searched value.

> **Note**:
>
> If `needle` is a string, the comparison is done in a case-sensitive
> manner.

`haystack`  
The array.

`strict`  
If the third parameter `strict` is set to **`TRUE`** then the <span
class="function">in\_array</span> function will also check the
<a href="/language/types.html" class="link">types</a> of the `needle` in
the `haystack`.

### Return Values

Returns **`TRUE`** if `needle` is found in the array, **`FALSE`**
otherwise.

### Examples

**Example \#1 <span class="function">in\_array</span> example**

``` php
<?php
$os = array("Mac", "NT", "Irix", "Linux");
if (in_array("Irix", $os)) {
    echo "Got Irix";
}
if (in_array("mac", $os)) {
    echo "Got mac";
}
?>
```

The second condition fails because <span
class="function">in\_array</span> is case-sensitive, so the program
above will display:

    Got Irix

**Example \#2 <span class="function">in\_array</span> with strict
example**

``` php
<?php
$a = array('1.10', 12.4, 1.13);

if (in_array('12.4', $a, true)) {
    echo "'12.4' found with strict check\n";
}

if (in_array(1.13, $a, true)) {
    echo "1.13 found with strict check\n";
}
?>
```

The above example will output:

    1.13 found with strict check

**Example \#3 <span class="function">in\_array</span> with an array as
needle**

``` php
<?php
$a = array(array('p', 'h'), array('p', 'r'), 'o');

if (in_array(array('p', 'h'), $a)) {
    echo "'ph' was found\n";
}

if (in_array(array('f', 'i'), $a)) {
    echo "'fi' was found\n";
}

if (in_array('o', $a)) {
    echo "'o' was found\n";
}
?>
```

The above example will output:

      'ph' was found
      'o' was found

### See Also

-   <span class="function">array\_search</span>
-   <span class="function">isset</span>
-   <span class="function">array\_key\_exists</span>

key\_exists
===========

Alias of <span class="function">array\_key\_exists</span>

### Description

This function is an alias of: <span
class="function">array\_key\_exists</span>.

key
===

Fetch a key from an array

### Description

<span class="type">mixed</span> <span class="methodname">key</span> (
<span class="methodparam"><span class="type">array</span>
`$array`</span> )

<span class="function">key</span> returns the index element of the
current array position.

### Parameters

`array`  
The array.

### Return Values

The <span class="function">key</span> function simply returns the key of
the array element that's currently being pointed to by the internal
pointer. It does not move the pointer in any way. If the internal
pointer points beyond the end of the elements list or the array is
empty, <span class="function">key</span> returns **`NULL`**.

### Changelog

| Version | Description                                                                                                                   |
|---------|-------------------------------------------------------------------------------------------------------------------------------|
| 7.0.0   | `array` is now always passed by value. Prior to this version, it was passed by reference if possible, and by value otherwise. |

### Examples

**Example \#1 <span class="function">key</span> example**

``` php
<?php
$array = array(
    'fruit1' => 'apple',
    'fruit2' => 'orange',
    'fruit3' => 'grape',
    'fruit4' => 'apple',
    'fruit5' => 'apple');

// this cycle echoes all associative array
// key where value equals "apple"
while ($fruit_name = current($array)) {
    if ($fruit_name == 'apple') {
        echo key($array).'<br />';
    }
    next($array);
}
?>
```

The above example will output:

    fruit1<br />
    fruit4<br />
    fruit5<br />

### See Also

-   <span class="function">current</span>
-   <span class="function">next</span>
-   <a href="/control-structures/foreach.html" class="link">foreach</a>

krsort
======

Sort an array by key in reverse order

### Description

<span class="type">bool</span> <span class="methodname">krsort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> \[, <span class="methodparam"><span
class="type">int</span> `$sort_flags`<span class="initializer"> =
SORT\_REGULAR</span></span> \] )

Sorts an array by key in reverse order, maintaining key to data
correlations. This is useful mainly for associative arrays.

### Parameters

`array`  
The input array.

`sort_flags`  
You may modify the behavior of the sort using the optional parameter
`sort_flags`, for details see <span class="function">sort</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">krsort</span> example**

``` php
<?php
$fruits = array("d"=>"lemon", "a"=>"orange", "b"=>"banana", "c"=>"apple");
krsort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
?>
```

The above example will output:

    d = lemon
    c = apple
    b = banana
    a = orange

### See Also

-   <span class="function">arsort</span>
-   <span class="function">ksort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

ksort
=====

Sort an array by key

### Description

<span class="type">bool</span> <span class="methodname">ksort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> \[, <span class="methodparam"><span
class="type">int</span> `$sort_flags`<span class="initializer"> =
SORT\_REGULAR</span></span> \] )

Sorts an array by key, maintaining key to data correlations. This is
useful mainly for associative arrays.

### Parameters

`array`  
The input array.

`sort_flags`  
You may modify the behavior of the sort using the optional parameter
`sort_flags`, for details see <span class="function">sort</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">ksort</span> example**

``` php
<?php
$fruits = array("d"=>"lemon", "a"=>"orange", "b"=>"banana", "c"=>"apple");
ksort($fruits);
foreach ($fruits as $key => $val) {
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

-   <span class="function">asort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

list
====

Assign variables as if they were an array

### Description

<span class="type">array</span> <span class="methodname">list</span> (
<span class="methodparam"><span class="type">mixed</span> `$var1`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$...`</span> \] )

Like <span class="function">array</span>, this is not really a function,
but a language construct. <span class="function">list</span> is used to
assign a list of variables in one operation.

> **Note**:
>
> Before PHP 7.1.0, <span class="function">list</span> only worked on
> numerical arrays and assumes the numerical indices start at 0.

**Warning**

In PHP 5, <span class="function">list</span> assigns the values starting
with the right-most parameter. In PHP 7, <span
class="function">list</span> starts with the left-most parameter.

If you are using plain variables, you don't have to worry about this.
But if you are using arrays with indices you usually expect the order of
the indices in the array the same you wrote in the <span
class="function">list</span> from left to right, which is not the case
in PHP 5, as it's assigned in the reverse order.

Generally speaking, it is advisable to avoid relying on a specific order
of operation, as this may change again in the future.

### Parameters

`var1`  
A variable.

### Return Values

Returns the assigned array.

### Changelog

| Version | Description                                                                                                                                                                                       |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | It is now possible to specify keys in <span class="function">list</span>. This enables destructuring of arrays with non-integer or non-sequential keys.                                           |
| 7.0.0   | <a href="/migration70/incompatible.html#migration70.incompatible.variable-handling.list.order" class="link">The order that the assignment operations are performed in has changed.</a>            |
| 7.0.0   | <a href="/migration70/incompatible.html#migration70.incompatible.variable-handling.list.empty" class="link"><span class="function">list</span> expressions can no longer be completely empty.</a> |
| 7.0.0   | <a href="/migration70/incompatible.html#migration70.incompatible.variable-handling.list.string" class="link">Strings can no longer be unpacked.</a>                                               |

### Examples

**Example \#1 <span class="function">list</span> examples**

``` php
<?php

$info = array('coffee', 'brown', 'caffeine');

// Listing all the variables
list($drink, $color, $power) = $info;
echo "$drink is $color and $power makes it special.\n";

// Listing some of them
list($drink, , $power) = $info;
echo "$drink has $power.\n";

// Or let's skip to only the third one
list( , , $power) = $info;
echo "I need $power!\n";

// list() doesn't work with strings
list($bar) = "abcde";
var_dump($bar); // NULL
?>
```

**Example \#2 An example use of <span class="function">list</span>**

``` php
<table>
 <tr>
  <th>Employee name</th>
  <th>Salary</th>
 </tr>

<?php
$result = $pdo->query("SELECT id, name, salary FROM employees");
while (list($id, $name, $salary) = $result->fetch(PDO::FETCH_NUM)) {
    echo " <tr>\n" .
          "  <td><a href=\"info.php?id=$id\">$name</a></td>\n" .
          "  <td>$salary</td>\n" .
          " </tr>\n";
}

?>

</table>
```

**Example \#3 Using nested <span class="function">list</span>**

``` php
<?php

list($a, list($b, $c)) = array(1, array(2, 3));

var_dump($a, $b, $c);

?>
```

    int(1)
    int(2)
    int(3)

**Example \#4 Using <span class="function">list</span> with array
indices**

``` php
<?php

$info = array('coffee', 'brown', 'caffeine');

list($a[0], $a[1], $a[2]) = $info;

var_dump($a);

?>
```

Gives the following output (note the order of the elements compared in
which order they were written in the <span class="function">list</span>
syntax):

Output of the above example in PHP 7:

    array(3) {
      [0]=>
      string(6) "coffee"
      [1]=>
      string(5) "brown"
      [2]=>
      string(8) "caffeine"
    }

Output of the above example in PHP 5:

    array(3) {
      [2]=>
      string(8) "caffeine"
      [1]=>
      string(5) "brown"
      [0]=>
      string(6) "coffee"
    }

**Example \#5 <span class="function">list</span> and order of index
definitions**

The order in which the indices of the array to be consumed by <span
class="function">list</span> are defined is irrelevant.

``` php
<?php
$foo = array(2 => 'a', 'foo' => 'b', 0 => 'c');
$foo[1] = 'd';
list($x, $y, $z) = $foo;
var_dump($foo, $x, $y, $z);
```

Gives the following output (note the order of the elements compared in
which order they were written in the <span class="function">list</span>
syntax):

    array(4) {
      [2]=>
      string(1) "a"
      ["foo"]=>
      string(1) "b"
      [0]=>
      string(1) "c"
      [1]=>
      string(1) "d"
    }
    string(1) "c"
    string(1) "d"
    string(1) "a"

**Example \#6 <span class="function">list</span> with keys**

As of PHP 7.1.0 <span class="function">list</span> can now also contain
explicit keys, which can be given as arbitrary expressions. Mixing of
integer and string keys is allowed; however, elements with and without
keys cannot be mixed.

``` php
<?php
$data = [
    ["id" => 1, "name" => 'Tom'],
    ["id" => 2, "name" => 'Fred'],
];
foreach ($data as ["id" => $id, "name" => $name]) {
    echo "id: $id, name: $name\n";
}
echo PHP_EOL;
list(1 => $second, 3 => $fourth) = [1, 2, 3, 4];
echo "$second, $fourth\n";
```

The above example will output:

    id: 1, name: Tom
    id: 2, name: Fred

    2, 4

### See Also

-   <span class="function">each</span>
-   <span class="function">array</span>
-   <span class="function">extract</span>

natcasesort
===========

Sort an array using a case insensitive "natural order" algorithm

### Description

<span class="type">bool</span> <span
class="methodname">natcasesort</span> ( <span class="methodparam"><span
class="type">array</span> `&$array`</span> )

<span class="function">natcasesort</span> is a case insensitive version
of <span class="function">natsort</span>.

This function implements a sort algorithm that orders alphanumeric
strings in the way a human being would while maintaining key/value
associations. This is described as a "natural ordering".

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array`  
The input array.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">natcasesort</span> example**

``` php
<?php
$array1 = $array2 = array('IMG0.png', 'img12.png', 'img10.png', 'img2.png', 'img1.png', 'IMG3.png');

sort($array1);
echo "Standard sorting\n";
print_r($array1);

natcasesort($array2);
echo "\nNatural order sorting (case-insensitive)\n";
print_r($array2);
?>
```

The above example will output:

    Standard sorting
    Array
    (
        [0] => IMG0.png
        [1] => IMG3.png
        [2] => img1.png
        [3] => img10.png
        [4] => img12.png
        [5] => img2.png
    )

    Natural order sorting (case-insensitive)
    Array
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

-   <span class="function">natsort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>
-   <span class="function">strnatcmp</span>
-   <span class="function">strnatcasecmp</span>

natsort
=======

Sort an array using a "natural order" algorithm

### Description

<span class="type">bool</span> <span class="methodname">natsort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> )

This function implements a sort algorithm that orders alphanumeric
strings in the way a human being would while maintaining key/value
associations. This is described as a "natural ordering". An example of
the difference between this algorithm and the regular computer string
sorting algorithms (used in <span class="function">sort</span>) can be
seen in the example below.

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array`  
The input array.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                       |
|---------|-----------------------------------------------------------------------------------|
| 5.2.10  | Zero padded numeric strings (e.g., '00005') now essentially ignore the 0 padding. |

### Examples

**Example \#1 <span class="function">natsort</span> examples
demonstrating basic usage**

``` php
<?php
$array1 = $array2 = array("img12.png", "img10.png", "img2.png", "img1.png");

asort($array1);
echo "Standard sorting\n";
print_r($array1);

natsort($array2);
echo "\nNatural order sorting\n";
print_r($array2);
?>
```

The above example will output:

    Standard sorting
    Array
    (
        [3] => img1.png
        [1] => img10.png
        [0] => img12.png
        [2] => img2.png
    )

    Natural order sorting
    Array
    (
        [3] => img1.png
        [2] => img2.png
        [1] => img10.png
        [0] => img12.png
    )

For more information see: Martin Pool's
<a href="http://sourcefrog.net/projects/natsort/" class="link external">» Natural Order String Comparison</a>
page.

**Example \#2 <span class="function">natsort</span> examples
demonstrating potential gotchas**

``` php
<?php
echo "Negative numbers\n";
$negative = array('-5','3','-2','0','-1000','9','1');
print_r($negative);
natsort($negative);
print_r($negative);

echo "Zero padding\n";
$zeros = array('09', '8', '10', '009', '011', '0'); 
print_r($zeros);
natsort($zeros);
print_r($zeros);
?>
```

The above example will output:

    Negative numbers
    Array
    (
        [0] => -5
        [1] => 3
        [2] => -2
        [3] => 0
        [4] => -1000
        [5] => 9
        [6] => 1
    )
    Array
    (
        [2] => -2
        [0] => -5
        [4] => -1000
        [3] => 0
        [6] => 1
        [1] => 3
        [5] => 9
    )

    Zero padding
    Array
    (
        [0] => 09
        [1] => 8
        [2] => 10
        [3] => 009
        [4] => 011
        [5] => 0
    )
    Array
    (
        [5] => 0
        [1] => 8
        [3] => 009
        [0] => 09
        [2] => 10
        [4] => 011
    )

### See Also

-   <span class="function">natcasesort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>
-   <span class="function">strnatcmp</span>
-   <span class="function">strnatcasecmp</span>

next
====

Advance the internal pointer of an array

### Description

<span class="type">mixed</span> <span class="methodname">next</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> )

<span class="function">next</span> behaves like <span
class="function">current</span>, with one difference. It advances the
internal array pointer one place forward before returning the element
value. That means it returns the next array value and advances the
internal array pointer by one.

### Parameters

`array`  
The <span class="type">array</span> being affected.

### Return Values

Returns the array value in the next place that's pointed to by the
internal array pointer, or **`FALSE`** if there are no more elements.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 Example use of <span class="function">next</span> and
friends**

``` php
<?php
$transport = array('foot', 'bike', 'car', 'plane');
$mode = current($transport); // $mode = 'foot';
$mode = next($transport);    // $mode = 'bike';
$mode = next($transport);    // $mode = 'car';
$mode = prev($transport);    // $mode = 'bike';
$mode = end($transport);     // $mode = 'plane';
?>
```

### Notes

> **Note**: <span class="simpara"> The end of an array is
> indistinguishable from a <span class="type">boolean</span> **`FALSE`**
> element. To properly traverse an array which may contain **`FALSE`**
> elements, see the <span class="function">foreach</span> function.
> </span> <span class="simpara"> To still use <span
> class="function">next</span> and properly check if the end of the
> array has been reached, verify that the <span
> class="function">key</span> is **`NULL`**. </span>

### See Also

-   <span class="function">current</span>
-   <span class="function">end</span>
-   <span class="function">prev</span>
-   <span class="function">reset</span>
-   <span class="function">each</span>

pos
===

Alias of <span class="function">current</span>

### Description

This function is an alias of: <span class="function">current</span>

prev
====

Rewind the internal array pointer

### Description

<span class="type">mixed</span> <span class="methodname">prev</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> )

Rewind the internal array pointer.

<span class="function">prev</span> behaves just like <span
class="function">next</span>, except it rewinds the internal array
pointer one place instead of advancing it.

### Parameters

`array`  
The input array.

### Return Values

Returns the array value in the previous place that's pointed to by the
internal array pointer, or **`FALSE`** if there are no more elements.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 Example use of <span class="function">prev</span> and
friends**

``` php
<?php
$transport = array('foot', 'bike', 'car', 'plane');
$mode = current($transport); // $mode = 'foot';
$mode = next($transport);    // $mode = 'bike';
$mode = next($transport);    // $mode = 'car';
$mode = prev($transport);    // $mode = 'bike';
$mode = end($transport);     // $mode = 'plane';
?>
```

### Notes

> **Note**: <span class="simpara"> The beginning of an array is
> indistinguishable from a <span class="type">boolean</span> **`FALSE`**
> element. To make the distinction, check that the <span
> class="function">key</span> of the <span class="function">prev</span>
> element is not **`NULL`**. </span>

### See Also

-   <span class="function">current</span>
-   <span class="function">end</span>
-   <span class="function">next</span>
-   <span class="function">reset</span>
-   <span class="function">each</span>

range
=====

Create an array containing a range of elements

### Description

<span class="type">array</span> <span class="methodname">range</span> (
<span class="methodparam"><span class="type">mixed</span>
`$start`</span> , <span class="methodparam"><span
class="type">mixed</span> `$end`</span> \[, <span
class="methodparam"><span class="type">number</span> `$step`<span
class="initializer"> = 1</span></span> \] )

Create an array containing a range of elements.

### Parameters

`start`  
First value of the sequence.

`end`  
The sequence is ended upon reaching the `end` value.

`step`  
If a `step` value is given, it will be used as the increment between
elements in the sequence. `step` should be given as a positive number.
If not specified, `step` will default to 1.

### Return Values

Returns an array of elements from `start` to `end`, inclusive.

### Examples

**Example \#1 <span class="function">range</span> examples**

``` php
<?php
// array(0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12)
foreach (range(0, 12) as $number) {
    echo $number;
}

// The step parameter
// array(0, 10, 20, 30, 40, 50, 60, 70, 80, 90, 100)
foreach (range(0, 100, 10) as $number) {
    echo $number;
}

// Usage of character sequences
// array('a', 'b', 'c', 'd', 'e', 'f', 'g', 'h', 'i');
foreach (range('a', 'i') as $letter) {
    echo $letter;
}
// array('c', 'b', 'a');
foreach (range('c', 'a') as $letter) {
    echo $letter;
}
?>
```

### Notes

> **Note**:
>
> Character sequence values are limited to a length of one. If a length
> greater than one is entered, only the first character is used.

### See Also

-   <span class="function">shuffle</span>
-   <span class="function">array\_fill</span>
-   <a href="/control-structures/foreach.html" class="link">foreach</a>

reset
=====

Set the internal pointer of an array to its first element

### Description

<span class="type">mixed</span> <span class="methodname">reset</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> )

<span class="function">reset</span> rewinds `array`'s internal pointer
to the first element and returns the value of the first array element.

### Parameters

`array`  
The input array.

### Return Values

Returns the value of the first array element, or **`FALSE`** if the
array is empty.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Examples

**Example \#1 <span class="function">reset</span> example**

``` php
<?php

$array = array('step one', 'step two', 'step three', 'step four');

// by default, the pointer is on the first element
echo current($array) . "<br />\n"; // "step one"

// skip two steps
next($array);
next($array);
echo current($array) . "<br />\n"; // "step three"

// reset pointer, start again on step one
reset($array);
echo current($array) . "<br />\n"; // "step one"

?>
```

### Notes

> **Note**: <span class="simpara"> The return value for an empty array
> is indistinguishable from the return value in case of an array which
> has a <span class="type">boolean</span> **`FALSE`** first element. To
> properly check the value of the first element of an array which may
> contain **`FALSE`** elements, first check the <span
> class="function">count</span> of the array, or check that <span
> class="function">key</span> is not **`NULL`**, after calling <span
> class="function">reset</span>. </span>

### See Also

-   <span class="function">current</span>
-   <span class="function">each</span>
-   <span class="function">end</span>
-   <span class="function">next</span>
-   <span class="function">prev</span>
-   <span class="function">array\_key\_first</span>

rsort
=====

Sort an array in reverse order

### Description

<span class="type">bool</span> <span class="methodname">rsort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> \[, <span class="methodparam"><span
class="type">int</span> `$sort_flags`<span class="initializer"> =
SORT\_REGULAR</span></span> \] )

This function sorts an array in reverse order (highest to lowest).

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array`  
The input array.

`sort_flags`  
You may modify the behavior of the sort using the optional parameter
`sort_flags`, for details see <span class="function">sort</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">rsort</span> example**

``` php
<?php
$fruits = array("lemon", "orange", "banana", "apple");
rsort($fruits);
foreach ($fruits as $key => $val) {
    echo "$key = $val\n";
}
?>
```

The above example will output:

    0 = orange
    1 = lemon
    2 = banana
    3 = apple

The fruits have been sorted in reverse alphabetical order.

### Notes

> **Note**: <span class="simpara">This function assigns new keys to the
> elements in `array`. It will remove any existing keys that may have
> been assigned, rather than just reordering the keys.</span>

### See Also

-   <span class="function">arsort</span>
-   <span class="function">krsort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

shuffle
=======

Shuffle an array

### Description

<span class="type">bool</span> <span class="methodname">shuffle</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> )

This function shuffles (randomizes the order of the elements in) an
array. It uses a pseudo random number generator that is not suitable for
cryptographic purposes.

### Parameters

`array`  
The array.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                       |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | The internal randomization algorithm <a href="/migration71/incompatible.html#migration71.incompatible.rand-srand-aliases" class="link">has been changed</a> to use the <a href="http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/emt.html" class="link external">» Mersenne Twister</a> Random Number Generator instead of the libc rand function. |

### Examples

**Example \#1 <span class="function">shuffle</span> example**

``` php
<?php
$numbers = range(1, 20);
shuffle($numbers);
foreach ($numbers as $number) {
    echo "$number ";
}
?>
```

### Notes

> **Note**: <span class="simpara">This function assigns new keys to the
> elements in `array`. It will remove any existing keys that may have
> been assigned, rather than just reordering the keys.</span>

### See Also

-   <span class="function">array\_rand</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

sizeof
======

Alias of <span class="function">count</span>

### Description

This function is an alias of: <span class="function">count</span>.

sort
====

Sort an array

### Description

<span class="type">bool</span> <span class="methodname">sort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> \[, <span class="methodparam"><span
class="type">int</span> `$sort_flags`<span class="initializer"> =
SORT\_REGULAR</span></span> \] )

This function sorts an array. Elements will be arranged from lowest to
highest when this function has completed.

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array`  
The input array.

`sort_flags`  
The optional second parameter `sort_flags` may be used to modify the
sorting behavior using these values:

Sorting type flags:

-   <span class="simpara">**`SORT_REGULAR`** - compare items normally;
    the details are described in the
    <a href="/language/operators/comparison.html" class="link">comparison operators</a>
    section</span>
-   <span class="simpara">**`SORT_NUMERIC`** - compare items
    numerically</span>
-   <span class="simpara">**`SORT_STRING`** - compare items as
    strings</span>
-   <span class="simpara"> **`SORT_LOCALE_STRING`** - compare items as
    strings, based on the current locale. It uses the locale, which can
    be changed using <span class="function">setlocale</span> </span>
-   <span class="simpara"> **`SORT_NATURAL`** - compare items as strings
    using "natural ordering" like <span class="function">natsort</span>
    </span>
-   <span class="simpara"> **`SORT_FLAG_CASE`** - can be combined
    (bitwise OR) with **`SORT_STRING`** or **`SORT_NATURAL`** to sort
    strings case-insensitively </span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 5.4.0   | Added support for **`SORT_NATURAL`** and **`SORT_FLAG_CASE`** as `sort_flags` |
| 5.0.2   | Added **`SORT_LOCALE_STRING`**                                                |

### Examples

**Example \#1 <span class="function">sort</span> example**

``` php
<?php

$fruits = array("lemon", "orange", "banana", "apple");
sort($fruits);
foreach ($fruits as $key => $val) {
    echo "fruits[" . $key . "] = " . $val . "\n";
}

?>
```

The above example will output:

    fruits[0] = apple
    fruits[1] = banana
    fruits[2] = lemon
    fruits[3] = orange

The fruits have been sorted in alphabetical order.

**Example \#2 <span class="function">sort</span> example using
case-insensitive natural ordering**

``` php
<?php

$fruits = array(
    "Orange1", "orange2", "Orange3", "orange20"
);
sort($fruits, SORT_NATURAL | SORT_FLAG_CASE);
foreach ($fruits as $key => $val) {
    echo "fruits[" . $key . "] = " . $val . "\n";
}

?>
```

The above example will output:

    fruits[0] = Orange1
    fruits[1] = orange2
    fruits[2] = Orange3
    fruits[3] = orange20

The fruits have been sorted like <span
class="function">natcasesort</span>.

### Notes

> **Note**: <span class="simpara">This function assigns new keys to the
> elements in `array`. It will remove any existing keys that may have
> been assigned, rather than just reordering the keys.</span>

> **Note**: <span class="simpara"> Like most PHP sorting functions,
> <span class="function">sort</span> uses an implementation of
> <a href="http://en.wikipedia.org/wiki/Quicksort" class="link external">» Quicksort</a>.
> The pivot is chosen in the middle of the partition resulting in an
> optimal time for already sorted arrays. This is however an
> implementation detail you shouldn't rely on. </span>

**Warning**

Be careful when sorting arrays with mixed types values because <span
class="function">sort</span> can produce unexpected results, if
`sort_flags` is **`SORT_REGULAR`**,

### See Also

-   <span class="function">asort</span>
-   <span class="function">rsort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

uasort
======

Sort an array with a user-defined comparison function and maintain index
association

### Description

<span class="type">bool</span> <span class="methodname">uasort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> , <span class="methodparam"><span
class="type">callable</span> `$value_compare_func`</span> )

This function sorts an array such that array indices maintain their
correlation with the array elements they are associated with, using a
user-defined comparison function.

This is used mainly when sorting associative arrays where the actual
element order is significant.

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array`  
The input array.

`value_compare_func`  
See <span class="function">usort</span> and <span
class="function">uksort</span> for examples of user-defined comparison
functions.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Basic <span class="function">uasort</span> example**

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
print_r($array);

// Sort and print the resulting array
uasort($array, 'cmp');
print_r($array);
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

-   <span class="function">usort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

uksort
======

Sort an array by keys using a user-defined comparison function

### Description

<span class="type">bool</span> <span class="methodname">uksort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> , <span class="methodparam"><span
class="type">callable</span> `$key_compare_func`</span> )

<span class="function">uksort</span> will sort the keys of an array
using a user-supplied comparison function. If the array you wish to sort
needs to be sorted by some non-trivial criteria, you should use this
function.

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

### Parameters

`array`  
The input array.

`key_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">uksort</span> example**

``` php
<?php
function cmp($a, $b)
{
    $a = preg_replace('@^(a|an|the) @', '', $a);
    $b = preg_replace('@^(a|an|the) @', '', $b);
    return strcasecmp($a, $b);
}

$a = array("John" => 1, "the Earth" => 2, "an apple" => 3, "a banana" => 4);

uksort($a, "cmp");

foreach ($a as $key => $value) {
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

-   <span class="function">usort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

usort
=====

Sort an array by values using a user-defined comparison function

### Description

<span class="type">bool</span> <span class="methodname">usort</span> (
<span class="methodparam"><span class="type">array</span>
`&$array`</span> , <span class="methodparam"><span
class="type">callable</span> `$value_compare_func`</span> )

This function will sort an array by its values using a user-supplied
comparison function. If the array you wish to sort needs to be sorted by
some non-trivial criteria, you should use this function.

> **Note**:
>
> If two members compare as equal, their relative order in the sorted
> array is undefined.

> **Note**: <span class="simpara">This function assigns new keys to the
> elements in `array`. It will remove any existing keys that may have
> been assigned, rather than just reordering the keys.</span>

### Parameters

`array`  
The input array.

`value_compare_func`  
The comparison function must return an integer less than, equal to, or
greater than zero if the first argument is considered to be respectively
less than, equal to, or greater than the second. Note that before PHP
7.0.0 this integer had to be in the range from -2147483648
to 2147483647.

<span class="type">int</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$a`</span>, <span
class="methodparam"><span class="type">mixed</span> `$b`</span> )

**Caution**
Returning *non-integer* values from the comparison function, such as
<span class="type">float</span>, will result in an internal cast to
<span class="type">integer</span> of the callback's return value. So
values such as 0.99 and 0.1 will both be cast to an integer value of 0,
which will compare such values as equal.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">usort</span> example**

``` php
<?php
function cmp($a, $b)
{
    if ($a == $b) {
        return 0;
    }
    return ($a < $b) ? -1 : 1;
}

$a = array(3, 2, 5, 6, 1);

usort($a, "cmp");

foreach ($a as $key => $value) {
    echo "$key: $value\n";
}
?>
```

The above example will output:

    0: 1
    1: 2
    2: 3
    3: 5
    4: 6

> **Note**:
>
> Obviously in this trivial case the <span class="function">sort</span>
> function would be more appropriate.

**Example \#2 <span class="function">usort</span> example using
multi-dimensional array**

``` php
<?php
function cmp($a, $b)
{
    return strcmp($a["fruit"], $b["fruit"]);
}

$fruits[0]["fruit"] = "lemons";
$fruits[1]["fruit"] = "apples";
$fruits[2]["fruit"] = "grapes";

usort($fruits, "cmp");

while (list($key, $value) = each($fruits)) {
    echo "\$fruits[$key]: " . $value["fruit"] . "\n";
}
?>
```

When sorting a multi-dimensional array, `$a` and `$b` contain references
to the first index of the array.

The above example will output:

    $fruits[0]: apples
    $fruits[1]: grapes
    $fruits[2]: lemons

**Example \#3 <span class="function">usort</span> example using a member
function of an object**

``` php
<?php
class TestObj {
    var $name;

    function TestObj($name)
    {
        $this->name = $name;
    }

    /* This is the static comparing function: */
    static function cmp_obj($a, $b)
    {
        $al = strtolower($a->name);
        $bl = strtolower($b->name);
        if ($al == $bl) {
            return 0;
        }
        return ($al > $bl) ? +1 : -1;
    }
}

$a[] = new TestObj("c");
$a[] = new TestObj("b");
$a[] = new TestObj("d");

usort($a, array("TestObj", "cmp_obj"));

foreach ($a as $item) {
    echo $item->name . "\n";
}
?>
```

The above example will output:

    b
    c
    d

**Example \#4 <span class="function">usort</span> example using a
<a href="/functions/anonymous.html" class="link">closure</a> to sort a
multi-dimensional array**

``` php
<?php
$array[0] = array('key_a' => 'z', 'key_b' => 'c');
$array[1] = array('key_a' => 'x', 'key_b' => 'b');
$array[2] = array('key_a' => 'y', 'key_b' => 'a');

function build_sorter($key) {
    return function ($a, $b) use ($key) {
        return strnatcmp($a[$key], $b[$key]);
    };
}

usort($array, build_sorter('key_b'));

foreach ($array as $item) {
    echo $item['key_a'] . ', ' . $item['key_b'] . "\n";
}
?>
```

The above example will output:

    y, a
    x, b
    z, c

### See Also

-   <span class="function">uasort</span>
-   The
    <a href="/array/sorting.html" class="link">comparison of array sorting functions</a>

**Table of Contents**

-   [array\_change\_key\_case](/ref/array.html#array_change_key_case) —
    Changes the case of all keys in an array
-   [array\_chunk](/ref/array.html#array_chunk) — Split an array into
    chunks
-   [array\_column](/ref/array.html#array_column) — Return the values
    from a single column in the input array
-   [array\_combine](/ref/array.html#array_combine) — Creates an array
    by using one array for keys and another for its values
-   [array\_count\_values](/ref/array.html#array_count_values) — Counts
    all the values of an array
-   [array\_diff\_assoc](/ref/array.html#array_diff_assoc) — Computes
    the difference of arrays with additional index check
-   [array\_diff\_key](/ref/array.html#array_diff_key) — Computes the
    difference of arrays using keys for comparison
-   [array\_diff\_uassoc](/ref/array.html#array_diff_uassoc) — Computes
    the difference of arrays with additional index check which is
    performed by a user supplied callback function
-   [array\_diff\_ukey](/ref/array.html#array_diff_ukey) — Computes the
    difference of arrays using a callback function on the keys for
    comparison
-   [array\_diff](/ref/array.html#array_diff) — Computes the difference
    of arrays
-   [array\_fill\_keys](/ref/array.html#array_fill_keys) — Fill an array
    with values, specifying keys
-   [array\_fill](/ref/array.html#array_fill) — Fill an array with
    values
-   [array\_filter](/ref/array.html#array_filter) — Filters elements of
    an array using a callback function
-   [array\_flip](/ref/array.html#array_flip) — Exchanges all keys with
    their associated values in an array
-   [array\_intersect\_assoc](/ref/array.html#array_intersect_assoc) —
    Computes the intersection of arrays with additional index check
-   [array\_intersect\_key](/ref/array.html#array_intersect_key) —
    Computes the intersection of arrays using keys for comparison
-   [array\_intersect\_uassoc](/ref/array.html#array_intersect_uassoc) —
    Computes the intersection of arrays with additional index check,
    compares indexes by a callback function
-   [array\_intersect\_ukey](/ref/array.html#array_intersect_ukey) —
    Computes the intersection of arrays using a callback function on the
    keys for comparison
-   [array\_intersect](/ref/array.html#array_intersect) — Computes the
    intersection of arrays
-   [array\_key\_exists](/ref/array.html#array_key_exists) — Checks if
    the given key or index exists in the array
-   [array\_key\_first](/ref/array.html#array_key_first) — Gets the
    first key of an array
-   [array\_key\_last](/ref/array.html#array_key_last) — Gets the last
    key of an array
-   [array\_keys](/ref/array.html#array_keys) — Return all the keys or a
    subset of the keys of an array
-   [array\_map](/ref/array.html#array_map) — Applies the callback to
    the elements of the given arrays
-   [array\_merge\_recursive](/ref/array.html#array_merge_recursive) —
    Merge one or more arrays recursively
-   [array\_merge](/ref/array.html#array_merge) — Merge one or more
    arrays
-   [array\_multisort](/ref/array.html#array_multisort) — Sort multiple
    or multi-dimensional arrays
-   [array\_pad](/ref/array.html#array_pad) — Pad array to the specified
    length with a value
-   [array\_pop](/ref/array.html#array_pop) — Pop the element off the
    end of array
-   [array\_product](/ref/array.html#array_product) — Calculate the
    product of values in an array
-   [array\_push](/ref/array.html#array_push) — Push one or more
    elements onto the end of array
-   [array\_rand](/ref/array.html#array_rand) — Pick one or more random
    keys out of an array
-   [array\_reduce](/ref/array.html#array_reduce) — Iteratively reduce
    the array to a single value using a callback function
-   [array\_replace\_recursive](/ref/array.html#array_replace_recursive)
    — Replaces elements from passed arrays into the first array
    recursively
-   [array\_replace](/ref/array.html#array_replace) — Replaces elements
    from passed arrays into the first array
-   [array\_reverse](/ref/array.html#array_reverse) — Return an array
    with elements in reverse order
-   [array\_search](/ref/array.html#array_search) — Searches the array
    for a given value and returns the first corresponding key if
    successful
-   [array\_shift](/ref/array.html#array_shift) — Shift an element off
    the beginning of array
-   [array\_slice](/ref/array.html#array_slice) — Extract a slice of the
    array
-   [array\_splice](/ref/array.html#array_splice) — Remove a portion of
    the array and replace it with something else
-   [array\_sum](/ref/array.html#array_sum) — Calculate the sum of
    values in an array
-   [array\_udiff\_assoc](/ref/array.html#array_udiff_assoc) — Computes
    the difference of arrays with additional index check, compares data
    by a callback function
-   [array\_udiff\_uassoc](/ref/array.html#array_udiff_uassoc) —
    Computes the difference of arrays with additional index check,
    compares data and indexes by a callback function
-   [array\_udiff](/ref/array.html#array_udiff) — Computes the
    difference of arrays by using a callback function for data
    comparison
-   [array\_uintersect\_assoc](/ref/array.html#array_uintersect_assoc) —
    Computes the intersection of arrays with additional index check,
    compares data by a callback function
-   [array\_uintersect\_uassoc](/ref/array.html#array_uintersect_uassoc)
    — Computes the intersection of arrays with additional index check,
    compares data and indexes by separate callback functions
-   [array\_uintersect](/ref/array.html#array_uintersect) — Computes the
    intersection of arrays, compares data by a callback function
-   [array\_unique](/ref/array.html#array_unique) — Removes duplicate
    values from an array
-   [array\_unshift](/ref/array.html#array_unshift) — Prepend one or
    more elements to the beginning of an array
-   [array\_values](/ref/array.html#array_values) — Return all the
    values of an array
-   [array\_walk\_recursive](/ref/array.html#array_walk_recursive) —
    Apply a user function recursively to every member of an array
-   [array\_walk](/ref/array.html#array_walk) — Apply a user supplied
    function to every member of an array
-   [array](/ref/array.html#array) — Create an array
-   [arsort](/ref/array.html#arsort) — Sort an array in reverse order
    and maintain index association
-   [asort](/ref/array.html#asort) — Sort an array and maintain index
    association
-   [compact](/ref/array.html#compact) — Create array containing
    variables and their values
-   [count](/ref/array.html#count) — Count all elements in an array, or
    something in an object
-   [current](/ref/array.html#current) — Return the current element in
    an array
-   [each](/ref/array.html#each) — Return the current key and value pair
    from an array and advance the array cursor
-   [end](/ref/array.html#end) — Set the internal pointer of an array to
    its last element
-   [extract](/ref/array.html#extract) — Import variables into the
    current symbol table from an array
-   [in\_array](/ref/array.html#in_array) — Checks if a value exists in
    an array
-   [key\_exists](/ref/array.html#key_exists) — Alias of
    array\_key\_exists
-   [key](/ref/array.html#key) — Fetch a key from an array
-   [krsort](/ref/array.html#krsort) — Sort an array by key in reverse
    order
-   [ksort](/ref/array.html#ksort) — Sort an array by key
-   [list](/ref/array.html#list) — Assign variables as if they were an
    array
-   [natcasesort](/ref/array.html#natcasesort) — Sort an array using a
    case insensitive "natural order" algorithm
-   [natsort](/ref/array.html#natsort) — Sort an array using a "natural
    order" algorithm
-   [next](/ref/array.html#next) — Advance the internal pointer of an
    array
-   [pos](/ref/array.html#pos) — Alias of current
-   [prev](/ref/array.html#prev) — Rewind the internal array pointer
-   [range](/ref/array.html#range) — Create an array containing a range
    of elements
-   [reset](/ref/array.html#reset) — Set the internal pointer of an
    array to its first element
-   [rsort](/ref/array.html#rsort) — Sort an array in reverse order
-   [shuffle](/ref/array.html#shuffle) — Shuffle an array
-   [sizeof](/ref/array.html#sizeof) — Alias of count
-   [sort](/ref/array.html#sort) — Sort an array
-   [uasort](/ref/array.html#uasort) — Sort an array with a user-defined
    comparison function and maintain index association
-   [uksort](/ref/array.html#uksort) — Sort an array by keys using a
    user-defined comparison function
-   [usort](/ref/array.html#usort) — Sort an array by values using a
    user-defined comparison function

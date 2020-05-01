Array Operators
---------------

| Example    | Name         | Result                                                                                             |
|------------|--------------|----------------------------------------------------------------------------------------------------|
| $a + $b    | Union        | Union of `$a` and `$b`.                                                                            |
| $a == $b   | Equality     | **`TRUE`** if `$a` and `$b` have the same key/value pairs.                                         |
| $a === $b  | Identity     | **`TRUE`** if `$a` and `$b` have the same key/value pairs in the same order and of the same types. |
| $a != $b   | Inequality   | **`TRUE`** if `$a` is not equal to `$b`.                                                           |
| $a \<\> $b | Inequality   | **`TRUE`** if `$a` is not equal to `$b`.                                                           |
| $a !== $b  | Non-identity | **`TRUE`** if `$a` is not identical to `$b`.                                                       |

The *+* operator returns the right-hand array appended to the left-hand
array; for keys that exist in both arrays, the elements from the
left-hand array will be used, and the matching elements from the
right-hand array will be ignored.

``` php
<?php
$a = array("a" => "apple", "b" => "banana");
$b = array("a" => "pear", "b" => "strawberry", "c" => "cherry");

$c = $a + $b; // Union of $a and $b
echo "Union of \$a and \$b: \n";
var_dump($c);

$c = $b + $a; // Union of $b and $a
echo "Union of \$b and \$a: \n";
var_dump($c);

$a += $b; // Union of $a += $b is $a and $b
echo "Union of \$a += \$b: \n";
var_dump($a);
?>
```

When executed, this script will print the following:

    Union of $a and $b:
    array(3) {
      ["a"]=>
      string(5) "apple"
      ["b"]=>
      string(6) "banana"
      ["c"]=>
      string(6) "cherry"
    }
    Union of $b and $a:
    array(3) {
      ["a"]=>
      string(4) "pear"
      ["b"]=>
      string(10) "strawberry"
      ["c"]=>
      string(6) "cherry"
    }
    Union of $a += $b:
    array(3) {
      ["a"]=>
      string(5) "apple"
      ["b"]=>
      string(6) "banana"
      ["c"]=>
      string(6) "cherry"
    }

Elements of arrays are equal for the comparison if they have the same
key and value.

**Example \#1 Comparing arrays**

``` php
<?php
$a = array("apple", "banana");
$b = array(1 => "banana", "0" => "apple");

var_dump($a == $b); // bool(true)
var_dump($a === $b); // bool(false)
?>
```

See also the manual sections on the
<a href="/language/types/array.html" class="link">Array type</a> and
<a href="/ref/array.html" class="link">Array functions</a>.

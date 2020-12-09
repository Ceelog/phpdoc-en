foreach
-------

The *foreach* construct provides an easy way to iterate over arrays.
*foreach* works only on arrays and objects, and will issue an error when
you try to use it on a variable with a different data type or an
uninitialized variable. There are two syntaxes:

    foreach (iterable_expression as $value)
        statement
    foreach (iterable_expression as $key => $value)
        statement

The first form traverses the iterable given by *iterable\_expression*.
On each iteration, the value of the current element is assigned to
*$value*.

The second form will additionally assign the current element's key to
the *$key* variable on each iteration.

It is possible to
<a href="/language/oop5/iterations.html" class="link">customize object iteration</a>.

In order to be able to directly modify array elements within the loop
precede *$value* with &. In that case the value will be assigned by
<a href="/language/references.html" class="link">reference</a>.

``` php
<?php
$arr = array(1, 2, 3, 4);
foreach ($arr as &$value) {
    $value = $value * 2;
}
// $arr is now array(2, 4, 6, 8)
unset($value); // break the reference with the last element
?>
```

**Warning**

Reference of a *$value* and the last array element remain even after the
*foreach* loop. It is recommended to destroy it by <span
class="function">unset</span>. Otherwise you will experience the
following behavior:

``` php
<?php
$arr = array(1, 2, 3, 4);
foreach ($arr as &$value) {
    $value = $value * 2;
}
// $arr is now array(2, 4, 6, 8)

// without an unset($value), $value is still a reference to the last item: $arr[3]

foreach ($arr as $key => $value) {
    // $arr[3] will be updated with each value from $arr...
    echo "{$key} => {$value} ";
    print_r($arr);
}
// ...until ultimately the second-to-last value is copied onto the last value

// output:
// 0 => 2 Array ( [0] => 2, [1] => 4, [2] => 6, [3] => 2 )
// 1 => 4 Array ( [0] => 2, [1] => 4, [2] => 6, [3] => 4 )
// 2 => 6 Array ( [0] => 2, [1] => 4, [2] => 6, [3] => 6 )
// 3 => 6 Array ( [0] => 2, [1] => 4, [2] => 6, [3] => 6 )
?>
```

It is possible to iterate a constant array's value by reference:

``` php
<?php
foreach (array(1, 2, 3, 4) as &$value) {
    $value = $value * 2;
}
?>
```

> **Note**:
>
> *foreach* does not support the ability to suppress error messages
> using *@*.

Some more examples to demonstrate usage:

``` php
<?php
/* foreach example 1: value only */

$a = array(1, 2, 3, 17);

foreach ($a as $v) {
    echo "Current value of \$a: $v.\n";
}

/* foreach example 2: value (with its manual access notation printed for illustration) */

$a = array(1, 2, 3, 17);

$i = 0; /* for illustrative purposes only */

foreach ($a as $v) {
    echo "\$a[$i] => $v.\n";
    $i++;
}

/* foreach example 3: key and value */

$a = array(
    "one" => 1,
    "two" => 2,
    "three" => 3,
    "seventeen" => 17
);

foreach ($a as $k => $v) {
    echo "\$a[$k] => $v.\n";
}

/* foreach example 4: multi-dimensional arrays */
$a = array();
$a[0][0] = "a";
$a[0][1] = "b";
$a[1][0] = "y";
$a[1][1] = "z";

foreach ($a as $v1) {
    foreach ($v1 as $v2) {
        echo "$v2\n";
    }
}

/* foreach example 5: dynamic arrays */

foreach (array(1, 2, 3, 4, 5) as $v) {
    echo "$v\n";
}
?>
```

### Unpacking nested arrays with list()

It is possible to iterate over an array of arrays and unpack the nested
array into loop variables by providing a <span
class="function">list</span> as the value.

For example:

``` php
<?php
$array = [
    [1, 2],
    [3, 4],
];

foreach ($array as list($a, $b)) {
    // $a contains the first element of the nested array,
    // and $b contains the second element.
    echo "A: $a; B: $b\n";
}
?>
```

The above example will output:

    A: 1; B: 2
    A: 3; B: 4

You can provide fewer elements in the <span class="function">list</span>
than there are in the nested array, in which case the leftover array
values will be ignored:

``` php
<?php
$array = [
    [1, 2],
    [3, 4],
];

foreach ($array as list($a)) {
    // Note that there is no $b here.
    echo "$a\n";
}
?>
```

The above example will output:

    1
    3

A notice will be generated if there aren't enough array elements to fill
the <span class="function">list</span>:

``` php
<?php
$array = [
    [1, 2],
    [3, 4],
];

foreach ($array as list($a, $b, $c)) {
    echo "A: $a; B: $b; C: $c\n";
}
?>
```

The above example will output:


    Notice: Undefined offset: 2 in example.php on line 7
    A: 1; B: 2; C: 

    Notice: Undefined offset: 2 in example.php on line 7
    A: 3; B: 4; C: 

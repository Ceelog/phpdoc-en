Incrementing/Decrementing Operators
-----------------------------------

PHP supports C-style pre- and post-increment and decrement operators.

> **Note**: <span class="simpara"> The increment/decrement operators
> only affect numbers and strings. Arrays, objects, booleans and
> resources are not affected. Decrementing **`null`** values has no
> effect too, but incrementing them results in *1*. </span>

| Example | Name           | Effect                                     |
|---------|----------------|--------------------------------------------|
| ++$a    | Pre-increment  | Increments `$a` by one, then returns `$a`. |
| $a++    | Post-increment | Returns `$a`, then increments `$a` by one. |
| --$a    | Pre-decrement  | Decrements `$a` by one, then returns `$a`. |
| $a--    | Post-decrement | Returns `$a`, then decrements `$a` by one. |

Here's a simple example script:

``` php
<?php
echo "<h3>Postincrement</h3>";
$a = 5;
echo "Should be 5: " . $a++ . "<br />\n";
echo "Should be 6: " . $a . "<br />\n";

echo "<h3>Preincrement</h3>";
$a = 5;
echo "Should be 6: " . ++$a . "<br />\n";
echo "Should be 6: " . $a . "<br />\n";

echo "<h3>Postdecrement</h3>";
$a = 5;
echo "Should be 5: " . $a-- . "<br />\n";
echo "Should be 4: " . $a . "<br />\n";

echo "<h3>Predecrement</h3>";
$a = 5;
echo "Should be 4: " . --$a . "<br />\n";
echo "Should be 4: " . $a . "<br />\n";
?>
```

PHP follows Perl's convention when dealing with arithmetic operations on
character variables and not C's. For example, in PHP and Perl *$a = 'Z';
$a++;* turns *$a* into *'AA'*, while in C *a = 'Z'; a++;* turns *a* into
*'\['* (ASCII value of *'Z'* is 90, ASCII value of *'\['* is 91). Note
that character variables can be incremented but not decremented and even
so only plain ASCII alphabets and digits (a-z, A-Z and 0-9) are
supported. Incrementing/decrementing other character variables has no
effect, the original string is unchanged.

**Example \#1 Arithmetic Operations on Character Variables**

``` php
<?php
echo '== Alphabets ==' . PHP_EOL;
$s = 'W';
for ($n=0; $n<6; $n++) {
    echo ++$s . PHP_EOL;
}
// Digit characters behave differently
echo '== Digits ==' . PHP_EOL;
$d = 'A8';
for ($n=0; $n<6; $n++) {
    echo ++$d . PHP_EOL;
}
$d = 'A08';
for ($n=0; $n<6; $n++) {
    echo ++$d . PHP_EOL;
}
?>
```

The above example will output:

    == Characters ==
    X
    Y
    Z
    AA
    AB
    AC
    == Digits ==
    A9
    B0
    B1
    B2
    B3
    B4
    A09
    A10
    A11
    A12
    A13
    A14

Incrementing or decrementing booleans has no effect.

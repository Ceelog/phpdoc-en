Arithmetic Operators
--------------------

Remember basic arithmetic from school? These work just like those.

| Example    | Name           | Result                                                                                                 |
|------------|----------------|--------------------------------------------------------------------------------------------------------|
| +$a        | Identity       | Conversion of `$a` to <span class="type">int</span> or <span class="type">float</span> as appropriate. |
| -$a        | Negation       | Opposite of `$a`.                                                                                      |
| $a + $b    | Addition       | Sum of `$a` and `$b`.                                                                                  |
| $a - $b    | Subtraction    | Difference of `$a` and `$b`.                                                                           |
| $a \* $b   | Multiplication | Product of `$a` and `$b`.                                                                              |
| $a / $b    | Division       | Quotient of `$a` and `$b`.                                                                             |
| $a % $b    | Modulo         | Remainder of `$a` divided by `$b`.                                                                     |
| $a \*\* $b | Exponentiation | Result of raising `$a` to the `$b`'th power. Introduced in PHP 5.6.                                    |

The division operator ("/") returns a float value unless the two
operands are integers (or strings that get converted to integers) and
the numbers are evenly divisible, in which case an integer value will be
returned. For integer division, see <span
class="function">intdiv</span>.

Operands of modulo are converted to integers (by stripping the decimal
part) before processing. For floating-point modulo, see <span
class="function">fmod</span>.

The result of the modulo operator *%* has the same sign as the dividend
— that is, the result of *$a % $b* will have the same sign as `$a`. For
example:

``` php
<?php

echo (5 % 3)."\n";           // prints 2
echo (5 % -3)."\n";          // prints 2
echo (-5 % 3)."\n";          // prints -2
echo (-5 % -3)."\n";         // prints -2

?>
```

See also the manual page on
<a href="/ref/math.html" class="link">Math functions</a>.

Assignment Operators
--------------------

The basic assignment operator is "=". Your first inclination might be to
think of this as "equal to". Don't. It really means that the left
operand gets set to the value of the expression on the right (that is,
"gets set to").

The value of an assignment expression is the value assigned. That is,
the value of "*$a = 3*" is 3. This allows you to do some tricky things:

``` php
<?php

$a = ($b = 4) + 5; // $a is equal to 9 now, and $b has been set to 4.

?>
```

In addition to the basic assignment operator, there are "combined
operators" for all of the
<a href="/language/operators.html" class="link">binary arithmetic</a>,
array union and string operators that allow you to use a value in an
expression and then set its value to the result of that expression. For
example:

``` php
<?php

$a = 3;
$a += 5; // sets $a to 8, as if we had said: $a = $a + 5;
$b = "Hello ";
$b .= "There!"; // sets $b to "Hello There!", just like $b = $b . "There!";

?>
```

Note that the assignment copies the original variable to the new one
(assignment by value), so changes to one will not affect the other. This
may also have relevance if you need to copy something like a large array
inside a tight loop.

An exception to the usual assignment by value behaviour within PHP
occurs with <span class="type">object</span>s, which are assigned by
reference. Objects may be explicitly copied via the
<a href="/language/oop5/cloning.html" class="link">clone</a> keyword.

### Assignment by Reference

Assignment by reference is also supported, using the "<span
class="computeroutput">$var = &$othervar;</span>" syntax. Assignment by
reference means that both variables end up pointing at the same data,
and nothing is copied anywhere.

**Example \#1 Assigning by reference**

``` php
<?php
$a = 3;
$b = &$a; // $b is a reference to $a

print "$a\n"; // prints 3
print "$b\n"; // prints 3

$a = 4; // change $a

print "$a\n"; // prints 4
print "$b\n"; // prints 4 as well, since $b is a reference to $a, which has
              // been changed
?>
```

The
<a href="/language/oop5/basic.html#language.oop5.basic.new" class="link">new</a>
operator returns a reference automatically, so assigning the result of
<a href="/language/oop5/basic.html#language.oop5.basic.new" class="link">new</a>
by reference is not allowed as of PHP 7.0.0, results in an
**`E_DEPRECATED`** message as of PHP 5.3.0, and an **`E_STRICT`**
message in earlier versions.

For example, this code will result in an error or warning:

``` php
<?php
class C {}

$o = &new C;
?>
```

Output of the above example in PHP 7:

    Parse error: syntax error, unexpected 'new' (T_NEW) in …

Output of the above example in PHP 5.3:

    Deprecated: Assigning the return value of new by reference is deprecated in …

Output of the above example in PHP 5:

    Strict Standards: Assigning the return value of new by reference is deprecated in …

More information on references and their potential uses can be found in
the
<a href="/language/references.html" class="link">References Explained</a>
section of the manual.

### Arithmetic Assignment Operators

| Example   | Equivalent    | Operation      |
|-----------|---------------|----------------|
| $a += $b  | $a = $a + b   | Addition       |
| $a -= $b  | $a = $a - $b  | Subtraction    |
| $a \*= $b | $a = $a \* $b | Multiplication |
| $a /= $b  | $a = $a / $b  | Division       |
| $a %= $b  | $a = $a % $b  | Modulus        |

### Bitwise Assignment Operators

| Example     | Equivalent      | Operation   |
|-------------|-----------------|-------------|
| $a &= $b    | $a = $a & $b    | Bitwise And |
| $a \|= $b   | $a = $a \| $b   | Bitwise Or  |
| $a ^= $b    | $a = $a ^ $b    | Bitwise Xor |
| $a \<\<= $b | $a = $a \<\< $b | Left Shift  |
| $a \>\>= $b | $a = $a \>\> $b | Right Shift |

### Other Assignment Operators

| Example   | Equivalent    | Operation            |
|-----------|---------------|----------------------|
| $a .= $b  | $a = $a . $b  | String Concatenation |
| $a ??= $b | $a = $a ?? $b | Null Coalesce        |

See also the manual sections on
<a href="/language/operators/arithmetic.html" class="link">arithmetic operators</a>,
<a href="/language/operators/bitwise.html" class="link">bitwise operators</a>,
<a href="/language/operators/string.html" class="link">string operators</a>,
and
<a href="/language/operators/comparison.html#language.operators.comparison.coalesce" class="link">null coalescing operator</a>.

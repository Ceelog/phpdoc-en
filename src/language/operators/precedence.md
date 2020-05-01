Operator Precedence
-------------------

The precedence of an operator specifies how "tightly" it binds two
expressions together. For example, in the expression *1 + 5 \* 3*, the
answer is *16* and not *18* because the multiplication ("\*") operator
has a higher precedence than the addition ("+") operator. Parentheses
may be used to force precedence, if necessary. For instance: *(1 + 5) \*
3* evaluates to *18*.

When operators have equal precedence their associativity decides how the
operators are grouped. For example "-" is left-associative, so *1 - 2 -
3* is grouped as *(1 - 2) - 3* and evaluates to *-4*. "=" on the other
hand is right-associative, so *$a = $b = $c* is grouped as *$a = ($b =
$c)*.

Operators of equal precedence that are non-associative cannot be used
next to each other, for example *1 \< 2 \> 1* is illegal in PHP. The
expression *1 \<= 1 == 1* on the other hand is legal, because the *==*
operator has lesser precedence than the *\<=* operator.

Use of parentheses, even when not strictly necessary, can often increase
readability of the code by making grouping explicit rather than relying
on the implicit operator precedence and associativity.

The following table lists the operators in order of precedence, with the
highest-precedence ones at the top. Operators on the same line have
equal precedence, in which case associativity decides grouping.

| Associativity   | Operators                                                                        | Additional Information                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| (n/a)           | *clone* *new*                                                                    | <a href="/language/oop5/cloning.html" class="link">clone</a> and <a href="/language/oop5/basic.html#language.oop5.basic.new" class="link">new</a> |
| right           | *\*\**                                                                           | <a href="/language/operators/arithmetic.html" class="link">arithmetic</a>                                                                         |
| (n/a)           | *++* *--* *\~* *(int)* *(float)* *(string)* *(array)* *(object)* *(bool)* *@*    | <a href="/language/types.html" class="link">types</a> and <a href="/language/operators/increment.html" class="link">increment/decrement</a>       |
| left            | *instanceof*                                                                     | <a href="/language/types.html" class="link">types</a>                                                                                             |
| (n/a)           | *!*                                                                              | <a href="/language/operators/logical.html" class="link">logical</a>                                                                               |
| left            | *\** */* *%*                                                                     | <a href="/language/operators/arithmetic.html" class="link">arithmetic</a>                                                                         |
| left            | *+* *-* *.*                                                                      | <a href="/language/operators/arithmetic.html" class="link">arithmetic</a> and <a href="/language/operators/string.html" class="link">string</a>   |
| left            | *\<\<* *\>\>*                                                                    | <a href="/language/operators/bitwise.html" class="link">bitwise</a>                                                                               |
| non-associative | *\<* *\<=* *\>* *\>=*                                                            | <a href="/language/operators/comparison.html" class="link">comparison</a>                                                                         |
| non-associative | *==* *!=* *===* *!==* *\<\>* *\<=\>*                                             | <a href="/language/operators/comparison.html" class="link">comparison</a>                                                                         |
| left            | *&*                                                                              | <a href="/language/operators/bitwise.html" class="link">bitwise</a> and <a href="/language/references.html" class="link">references</a>           |
| left            | *^*                                                                              | <a href="/language/operators/bitwise.html" class="link">bitwise</a>                                                                               |
| left            | *\|*                                                                             | <a href="/language/operators/bitwise.html" class="link">bitwise</a>                                                                               |
| left            | *&&*                                                                             | <a href="/language/operators/logical.html" class="link">logical</a>                                                                               |
| left            | *\|\|*                                                                           | <a href="/language/operators/logical.html" class="link">logical</a>                                                                               |
| right           | *??*                                                                             | <a href="/language/operators/comparison.html#language.operators.comparison.coalesce" class="link">null coalescing</a>                             |
| left            | *? :*                                                                            | <a href="/language/operators/comparison.html#language.operators.comparison.ternary" class="link">ternary</a>                                      |
| right           | *=* *+=* *-=* *\*=* *\*\*=* */=* *.=* *%=* *&=* *\|=* *^=* *\<\<=* *\>\>=* *??=* | <a href="/language/operators/assignment.html" class="link">assignment</a>                                                                         |
| (n/a)           | *yield from*                                                                     | <a href="/language/generators/syntax.html#control-structures.yield.from" class="link">yield from</a>                                              |
| (n/a)           | *yield*                                                                          | <a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>                                                        |
| (n/a)           | *print*                                                                          | <span class="function">print</span>                                                                                                               |
| left            | *and*                                                                            | <a href="/language/operators/logical.html" class="link">logical</a>                                                                               |
| left            | *xor*                                                                            | <a href="/language/operators/logical.html" class="link">logical</a>                                                                               |
| left            | *or*                                                                             | <a href="/language/operators/logical.html" class="link">logical</a>                                                                               |

**Example \#1 Associativity**

``` php
<?php
$a = 3 * 3 % 5; // (3 * 3) % 5 = 4
// ternary operator associativity differs from C/C++
$a = true ? 0 : true ? 1 : 2; // (true ? 0 : true) ? 1 : 2 = 2

$a = 1;
$b = 2;
$a = $b += 3; // $a = ($b += 3) -> $a = 5, $b = 5
?>
```

Operator precedence and associativity only determine how expressions are
grouped, they do not specify an order of evaluation. PHP does not (in
the general case) specify in which order an expression is evaluated and
code that assumes a specific order of evaluation should be avoided,
because the behavior can change between versions of PHP or depending on
the surrounding code.

**Example \#2 Undefined order of evaluation**

``` php
<?php
$a = 1;
echo $a + $a++; // may print either 2 or 3

$i = 1;
$array[$i] = $i++; // may set either index 1 or 2
?>
```

**Example \#3 *+*, *-* and *.* have the same precedence**

``` php
<?php
$x = 4;
// this line might result in unexpected output:
echo "x minus one equals " . $x-1 . ", or so I hope\n";
// because it is evaluated like this line:
echo (("x minus one equals " . $x) - 1) . ", or so I hope\n";
// the desired precedence can be enforced by using parentheses:
echo "x minus one equals " . ($x-1) . ", or so I hope\n";
?>
```

The above example will output:

    -1, or so I hope
    -1, or so I hope
    x minus one equals 3, or so I hope

> **Note**:
>
> Although *=* has a lower precedence than most other operators, PHP
> will still allow expressions similar to the following: *if (!$a =
> foo())*, in which case the return value of *foo()* is put into `$a`.

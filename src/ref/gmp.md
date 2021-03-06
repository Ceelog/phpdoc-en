See Also
--------

More mathematical functions can be found in the
<a href="/refs/math.html" class="xref">Mathematical Extensions</a>
section

gmp\_abs
========

Absolute value

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_abs</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Get the absolute value of a number.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns the absolute value of `num`, as a GMP number.

### Examples

**Example \#1 <span class="function">gmp\_abs</span> example**

``` php
<?php
$abs1 = gmp_abs("274982683358");
$abs2 = gmp_abs("-274982683358");

echo gmp_strval($abs1) . "\n";
echo gmp_strval($abs2) . "\n";
?>
```

The above example will output:

    274982683358
    274982683358

gmp\_add
========

Add numbers

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_add</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Add two numbers.

### Parameters

`num1`  
The first summand (augent).

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
The second summand (addend).

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A GMP number representing the sum of the arguments.

### Examples

**Example \#1 <span class="function">gmp\_add</span> example**

``` php
<?php
$sum = gmp_add("123456789012345", "76543210987655");
echo gmp_strval($sum) . "\n";
?>
```

The above example will output:

    200000000000000

gmp\_and
========

Bitwise AND

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_and</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Calculates bitwise AND of two GMP numbers.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A GMP number representing the bitwise *AND* comparison.

### Examples

**Example \#1 <span class="function">gmp\_and</span> example**

``` php
<?php
$and1 = gmp_and("0xfffffffff4", "0x4");
$and2 = gmp_and("0xfffffffff4", "0x8");
echo gmp_strval($and1) . "\n";
echo gmp_strval($and2) . "\n";
?>
```

The above example will output:

    4
    0

gmp\_binomial
=============

Calculates binomial coefficient

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_binomial</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$n`</span> , <span
class="methodparam"><span class="type">int</span> `$k`</span> )

Calculates the binomial coefficient C(n, k).

### Parameters

`n`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`k`  

### Return Values

Returns the binomial coefficient C(n, k).

### Errors/Exceptions

Throws <span class="classname">ValueError</span> if `k` is negative.
Prior to PHP 8.0.0, **`E_WARNING`** was issued instead.

### Changelog

| Version | Description                                             |
|---------|---------------------------------------------------------|
| 8.0.0   | This function no longer returns **`false`** on failure. |

gmp\_clrbit
===========

Clear bit

### Description

<span class="type">void</span> <span
class="methodname">gmp\_clrbit</span> ( <span class="methodparam"><span
class="type">GMP</span> `$num`</span> , <span class="methodparam"><span
class="type">int</span> `$index`</span> )

Clears (sets to 0) bit `index` in `num`. The index starts at 0.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`index`  
The index of the bit to clear. Index 0 represents the least significant
bit.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_clrbit</span> example**

``` php
<?php
$a = gmp_init("0xff");
gmp_clrbit($a, 0); // index starts at 0, least significant bit
echo gmp_strval($a) . "\n";
?>
```

The above example will output:

    254

### Notes

> **Note**:
>
> Unlike most of the other GMP functions, <span
> class="function">gmp\_clrbit</span> must be called with a GMP object
> that already exists (using <span class="function">gmp\_init</span> for
> example). One will not be automatically created.

### See Also

-   <span class="function">gmp\_setbit</span>
-   <span class="function">gmp\_testbit</span>

gmp\_cmp
========

Compare numbers

### Description

<span class="type">int</span> <span class="methodname">gmp\_cmp</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Compares two numbers.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns a positive value if *a \> b*, zero if *a = b* and a negative
value if *a \< b*.

### Examples

**Example \#1 <span class="function">gmp\_cmp</span> example**

``` php
<?php
$cmp1 = gmp_cmp("1234", "1000"); // greater than
$cmp2 = gmp_cmp("1000", "1234"); // less than
$cmp3 = gmp_cmp("1234", "1234"); // equal to

echo "$cmp1 $cmp2 $cmp3\n";
?>
```

The above example will output:

    1 -1 0

gmp\_com
========

Calculates one's complement

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_com</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Returns the one's complement of `num`.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns the one's complement of `num`, as a GMP number.

### Examples

**Example \#1 <span class="function">gmp\_com</span> example**

``` php
<?php
$com = gmp_com("1234");
echo gmp_strval($com) . "\n";
?>
```

The above example will output:

    -1235

gmp\_div\_q
===========

Divide numbers

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_div\_q</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num1`</span> , <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> \[, <span
class="methodparam"><span class="type">int</span> `$rounding_mode`<span
class="initializer"> = **`GMP_ROUND_ZERO`**</span></span> \] )

Divides `num1` by `num2` and returns the integer result.

### Parameters

`num1`  
The number being divided.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
The number that `num1` is being divided by.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`rounding_mode`  
The result rounding is defined by the `rounding_mode`, which can have
the following values:

-   <span class="simpara"> **`GMP_ROUND_ZERO`**: The result is truncated
    towards 0. </span>
-   <span class="simpara"> **`GMP_ROUND_PLUSINF`**: The result is
    rounded towards *+infinity*. </span>
-   <span class="simpara"> **`GMP_ROUND_MINUSINF`**: The result is
    rounded towards *-infinity*. </span>

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_div\_q</span> example**

``` php
<?php
$div1 = gmp_div_q("100", "5");
echo gmp_strval($div1) . "\n";

$div2 = gmp_div_q("1", "3");
echo gmp_strval($div2) . "\n";

$div3 = gmp_div_q("1", "3", GMP_ROUND_PLUSINF);
echo gmp_strval($div3) . "\n";

$div4 = gmp_div_q("-1", "4", GMP_ROUND_PLUSINF);
echo gmp_strval($div4) . "\n";

$div5 = gmp_div_q("-1", "4", GMP_ROUND_MINUSINF);
echo gmp_strval($div5) . "\n";
?>
```

The above example will output:

    20
    0
    1
    0
    -1

### Notes

> **Note**:
>
> This function can also be called as <span
> class="function">gmp\_div</span>.

### See Also

-   <span class="function">gmp\_div\_r</span>
-   <span class="function">gmp\_div\_qr</span>

gmp\_div\_qr
============

Divide numbers and get quotient and remainder

### Description

<span class="type">array</span> <span
class="methodname">gmp\_div\_qr</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num1`</span> , <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> \[, <span
class="methodparam"><span class="type">int</span> `$rounding_mode`<span
class="initializer"> = **`GMP_ROUND_ZERO`**</span></span> \] )

The function divides `num1` by `num2`.

### Parameters

`num1`  
The number being divided.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
The number that `num1` is being divided by.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`rounding_mode`  
See the <span class="function">gmp\_div\_q</span> function for
description of the `rounding_mode` argument.

### Return Values

Returns an <span class="type">array</span>, with the first element being
*\[n/d\]* (the integer result of the division) and the second being *(n
- \[n/d\] \* d)* (the remainder of the division).

### Examples

**Example \#1 Division of GMP numbers**

``` php
<?php
$a = gmp_init("0x41682179fbf5");
$res = gmp_div_qr($a, "0xDEFE75");
printf("Result is: q - %s, r - %s",
       gmp_strval($res[0]), gmp_strval($res[1]));
?>
```

### See Also

-   <span class="function">gmp\_div\_q</span>
-   <span class="function">gmp\_div\_r</span>

gmp\_div\_r
===========

Remainder of the division of numbers

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_div\_r</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num1`</span> , <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> \[, <span
class="methodparam"><span class="type">int</span> `$rounding_mode`<span
class="initializer"> = **`GMP_ROUND_ZERO`**</span></span> \] )

Calculates remainder of the integer division of `num1` by `num2`. The
remainder has the sign of the `num1` argument, if not zero.

### Parameters

`num1`  
The number being divided.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
The number that `num1` is being divided by.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`rounding_mode`  
See the <span class="function">gmp\_div\_q</span> function for
description of the `rounding_mode` argument.

### Return Values

The remainder, as a GMP number.

### Examples

**Example \#1 <span class="function">gmp\_div\_r</span> example**

``` php
<?php
$div = gmp_div_r("105", "20");
echo gmp_strval($div) . "\n";
?>
```

The above example will output:

    5

### See Also

-   <span class="function">gmp\_div\_q</span>
-   <span class="function">gmp\_div\_qr</span>

gmp\_div
========

Alias of <span class="function">gmp\_div\_q</span>

### Description

This function is an alias of: <span class="function">gmp\_div\_q</span>.

gmp\_divexact
=============

Exact division of numbers

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_divexact</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Divides `num1` by `num2`, using fast "exact division" algorithm. This
function produces correct results only when it is known in advance that
`num2` divides `num1`.

### Parameters

`num1`  
The number being divided.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
The number that `a` is being divided by.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_divexact</span> example**

``` php
<?php
$div1 = gmp_divexact("10", "2");
echo gmp_strval($div1) . "\n";

$div2 = gmp_divexact("10", "3"); // bogus result
echo gmp_strval($div2) . "\n";
?>
```

The above example will output:

    5
    2863311534

gmp\_export
===========

Export to a binary string

### Description

<span class="type">string</span> <span
class="methodname">gmp\_export</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num`</span> \[, <span class="methodparam"><span
class="type">int</span> `$word_size`<span class="initializer"> =
1</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
**`GMP_MSW_FIRST`** \| **`GMP_NATIVE_ENDIAN`**</span></span> \]\] )

Export a GMP number to a binary string

### Parameters

`num`  
The GMP number being exported

`word_size`  
Default value is 1. The number of bytes in each chunk of binary data.
This is mainly used in conjunction with the options parameter.

`flags`  
Default value is GMP\_MSW\_FIRST \| GMP\_NATIVE\_ENDIAN.

### Return Values

Returns a string.

### Changelog

| Version | Description                                             |
|---------|---------------------------------------------------------|
| 8.0.0   | This function no longer returns **`false`** on failure. |

### Examples

**Example \#1 <span class="function">gmp\_export</span> example**

``` php
<?php
$number = gmp_init(16705);
echo gmp_export($number) . "\n";
?>
```

The above example will output:

    AA

### See Also

-   <span class="function">gmp\_import</span>

gmp\_fact
=========

Factorial

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_fact</span>
( <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Calculates factorial (*num!*) of `num`.

### Parameters

`num`  
The factorial number.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_fact</span> example**

``` php
<?php
$fact1 = gmp_fact(5); // 5 * 4 * 3 * 2 * 1
echo gmp_strval($fact1) . "\n";

$fact2 = gmp_fact(50); // 50 * 49 * 48, ... etc
echo gmp_strval($fact2) . "\n";
?>
```

The above example will output:

    120
    30414093201713378043612608166064768844377641568960512000000000000

gmp\_gcd
========

Calculate GCD

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_gcd</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Calculate greatest common divisor of `num1` and `num2`. The result is
always positive even if either of, or both, input operands are negative.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A positive GMP number that divides into both `num1` and `num2`.

### Examples

**Example \#1 <span class="function">gmp\_gcd</span> example**

``` php
<?php
$gcd = gmp_gcd("12", "21");
echo gmp_strval($gcd) . "\n";
?>
```

The above example will output:

    3

### See Also

-   <span class="function">gmp\_lcm</span>

gmp\_gcdext
===========

Calculate GCD and multipliers

### Description

<span class="type">array</span> <span
class="methodname">gmp\_gcdext</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num1`</span> , <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Calculates g, s, and t, such that *a\*s + b\*t = g = gcd(a,b)*, where
gcd is the greatest common divisor. Returns an array with respective
elements g, s and t.

This function can be used to solve linear Diophantine equations in two
variables. These are equations that allow only integer solutions and
have the form: *a\*x + b\*y = c*. For more information, go to the
<a href="http://mathworld.wolfram.com/DiophantineEquation.html" class="link external">» "Diophantine Equation" page at MathWorld</a>

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

An <span class="type">array</span> of GMP numbers.

### Examples

**Example \#1 Solving a linear Diophantine equation**

``` php
<?php
// Solve the equation a*s + b*t = g
// where a = 12, b = 21, g = gcd(12, 21) = 3
$a = gmp_init(12);
$b = gmp_init(21);
$g = gmp_gcd($a, $b);
$r = gmp_gcdext($a, $b);

$check_gcd = (gmp_strval($g) == gmp_strval($r['g']));
$eq_res = gmp_add(gmp_mul($a, $r['s']), gmp_mul($b, $r['t']));
$check_res = (gmp_strval($g) == gmp_strval($eq_res));

if ($check_gcd && $check_res) {
    $fmt = "Solution: %d*%d + %d*%d = %d\n";
    printf($fmt, gmp_strval($a), gmp_strval($r['s']), gmp_strval($b),
    gmp_strval($r['t']), gmp_strval($r['g']));
} else {
    echo "Error while solving the equation\n";
}

// output: Solution: 12*2 + 21*-1 = 3
?>
```

gmp\_hamdist
============

Hamming distance

### Description

<span class="type">int</span> <span
class="methodname">gmp\_hamdist</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num1`</span> , <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Returns the hamming distance between `num1` and `num2`. Both operands
should be non-negative.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

It should be positive.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

It should be positive.

### Return Values

The hamming distance between `num1` and `num2`, as an <span
class="type">int</span>.

### Examples

**Example \#1 <span class="function">gmp\_hamdist</span> example**

``` php
<?php
$ham1 = gmp_init("1001010011", 2);
$ham2 = gmp_init("1011111100", 2);
echo gmp_hamdist($ham1, $ham2) . "\n";

/* hamdist is equivalent to: */
echo gmp_popcount(gmp_xor($ham1, $ham2)) . "\n";
?>
```

The above example will output:

    6
    6

### See Also

-   <span class="function">gmp\_popcount</span>
-   <span class="function">gmp\_xor</span>

gmp\_import
===========

Import from a binary string

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_import</span> ( <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type">int</span> `$word_size`<span
class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = **`GMP_MSW_FIRST`** \|
**`GMP_NATIVE_ENDIAN`**</span></span> \]\] )

Import a GMP number from a binary string

### Parameters

`data`  
The binary string being imported

`word_size`  
Default value is 1. The number of bytes in each chunk of binary data.
This is mainly used in conjunction with the options parameter.

`flags`  
Default value is GMP\_MSW\_FIRST \| GMP\_NATIVE\_ENDIAN.

### Return Values

Returns a GMP number.

### Changelog

| Version | Description                                             |
|---------|---------------------------------------------------------|
| 8.0.0   | This function no longer returns **`false`** on failure. |

### Examples

**Example \#1 <span class="function">gmp\_import</span> example**

``` php
<?php
$number = gmp_import("\0");
echo gmp_strval($number) . "\n";

$number = gmp_import("\0\1\2");
echo gmp_strval($number) . "\n";
?>
```

The above example will output:

    0
    258

### See Also

-   <span class="function">gmp\_export</span>

gmp\_init
=========

Create GMP number

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_init</span>
( <span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">string</span></span>
`$num`</span> \[, <span class="methodparam"><span
class="type">int</span> `$base`<span class="initializer"> =
0</span></span> \] )

Creates a GMP number from an integer or string.

### Parameters

`num`  
An integer or a string. The string representation can be decimal,
hexadecimal or octal.

`base`  
The base.

The base may vary from 2 to 62. If base is 0 (default value), the actual
base is determined from the leading characters: if the first two
characters are *0x* or *0X*, hexadecimal is assumed, if the first two
characters are *0b* or *0B*, binary is assumed, otherwise if the first
character is *0*, octal is assumed, otherwise decimal is assumed. For
bases up to 36, case is ignored; upper-case and lower-case letters have
the same value. For bases 37 to 62, upper-case letter represent the
usual 10 to 35 while lower-case letter represent 36 to 61.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 Creating GMP number**

``` php
<?php
$a = gmp_init(123456);
$b = gmp_init("0xFFFFDEBACDFEDF7200");
?>
```

### Notes

> **Note**:
>
> It is not necessary to call this function in order to use integers or
> strings in place of GMP numbers in GMP functions (such as with <span
> class="function">gmp\_add</span>). Function arguments are
> automatically converted to GMP numbers, if such conversion is possible
> and needed, using the same rules as <span
> class="function">gmp\_init</span>.

gmp\_intval
===========

Convert GMP number to integer

### Description

<span class="type">int</span> <span
class="methodname">gmp\_intval</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num`</span> )

This function converts GMP number into native PHP <span
class="type">int</span>s.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

The <span class="type">int</span> value of `num`.

### Examples

**Example \#1 <span class="function">gmp\_intval</span> example**

``` php
<?php
// displays correct result
echo gmp_intval("2147483647") . "\n";

// displays wrong result, above PHP integer limit
echo gmp_intval("2147483648") . "\n";

// displays correct result
echo gmp_strval("2147483648") . "\n";
?>
```

The above example will output:

    2147483647
    2147483647
    2147483648

### Notes

**Warning**

This function returns a useful result only if the number actually fits
the PHP integer (i.e., signed long type). To simply print the GMP
number, use <span class="function">gmp\_strval</span>.

gmp\_invert
===========

Inverse by modulo

### Description

<span class="type"><span class="type">GMP</span><span
class="type">false</span></span> <span
class="methodname">gmp\_invert</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num1`</span> , <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Computes the inverse of `num1` modulo `num2`.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A GMP number on success or **`false`** if an inverse does not exist.

### Examples

**Example \#1 <span class="function">gmp\_invert</span> example**

``` php
<?php
echo gmp_invert("5", "10"); // no inverse, outputs nothing, result is FALSE
$invert = gmp_invert("5", "11");
echo gmp_strval($invert) . "\n";
?>
```

The above example will output:

    9

gmp\_jacobi
===========

Jacobi symbol

### Description

<span class="type">int</span> <span
class="methodname">gmp\_jacobi</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num1`</span> , <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Computes
<a href="http://primes.utm.edu/glossary/page.php?sort=JacobiSymbol" class="link external">» Jacobi symbol</a>
of `num1` and `num2`. `num2` should be odd and must be positive.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

Should be odd and must be positive.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_jacobi</span> example**

``` php
<?php
echo gmp_jacobi("1", "3") . "\n";
echo gmp_jacobi("2", "3") . "\n";
?>
```

The above example will output:

    1
    0

### See Also

-   <span class="function">gmp\_kronecker</span>
-   <span class="function">gmp\_legendre</span>

gmp\_kronecker
==============

Kronecker symbol

### Description

<span class="type">int</span> <span
class="methodname">gmp\_kronecker</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

This function computes the Kronecker symbol of `num1` and `num2`.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns the Kronecker symbol of `num1` and `num2`

### See Also

-   <span class="function">gmp\_jacobi</span>
-   <span class="function">gmp\_legendre</span>

gmp\_lcm
========

Calculate LCM

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_lcm</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

This function computes the least common multiple (lcm) of `num1` and
`num2`.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### See Also

-   <span class="function">gmp\_gcd</span>

gmp\_legendre
=============

Legendre symbol

### Description

<span class="type">int</span> <span
class="methodname">gmp\_legendre</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Compute the
<a href="http://primes.utm.edu/glossary/page.php?sort=LegendreSymbol" class="link external">»  Legendre symbol</a>
of `num1` and `num2`. `num2` should be odd and must be positive.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

Should be odd and must be positive.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_legendre</span> example**

``` php
<?php
echo gmp_legendre("1", "3") . "\n";
echo gmp_legendre("2", "3") . "\n";
?>
```

The above example will output:

    1
    0

### See Also

-   <span class="function">gmp\_jacobi</span>
-   <span class="function">gmp\_kronecker</span>

gmp\_mod
========

Modulo operation

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_mod</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Calculates `num1` modulo `num2`. The result is always non-negative, the
sign of `num2` is ignored.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
The modulo that is being evaluated.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_mod</span> example**

``` php
<?php
$mod = gmp_mod("8", "3");
echo gmp_strval($mod) . "\n";
?>
```

The above example will output:

    2

gmp\_mul
========

Multiply numbers

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_mul</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Multiplies `num1` by `num2` and returns the result.

### Parameters

`num1`  
A number that will be multiplied by `num2`.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A number that will be multiplied by `num1`.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_mul</span> example**

``` php
<?php
$mul = gmp_mul("12345678", "2000");
echo gmp_strval($mul) . "\n";
?>
```

The above example will output:

    24691356000

gmp\_neg
========

Negate number

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_neg</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Returns the negative value of a number.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns -`num`, as a GMP number.

### Examples

**Example \#1 <span class="function">gmp\_neg</span> example**

``` php
<?php
$neg1 = gmp_neg("1");
echo gmp_strval($neg1) . "\n";
$neg2 = gmp_neg("-1");
echo gmp_strval($neg2) . "\n";
?>
```

The above example will output:

    -1
    1

gmp\_nextprime
==============

Find next prime number

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_nextprime</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Find next prime number

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Return the next prime number greater than `num`, as a GMP number.

### Examples

**Example \#1 <span class="function">gmp\_nextprime</span> example**

``` php
<?php
$prime1 = gmp_nextprime(10); // next prime number greater than 10
$prime2 = gmp_nextprime(-1000); // next prime number greater than -1000

echo gmp_strval($prime1) . "\n";
echo gmp_strval($prime2) . "\n";
?>
```

The above example will output:

    11
    2

### Notes

> **Note**:
>
> This function uses a probabilistic algorithm to identify primes and
> chances to get a composite number are extremely small.

gmp\_or
=======

Bitwise OR

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_or</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Calculates bitwise inclusive OR of two GMP numbers.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_or</span> example**

``` php
<?php
$or1 = gmp_or("0xfffffff2", "4");
echo gmp_strval($or1, 16) . "\n";
$or2 = gmp_or("0xfffffff2", "2");
echo gmp_strval($or2, 16) . "\n";
?>
```

The above example will output:

    fffffff6
    fffffff2

gmp\_perfect\_power
===================

Perfect power check

### Description

<span class="type">bool</span> <span
class="methodname">gmp\_perfect\_power</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Checks whether `num` is a perfect power.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns **`true`** if `num` is a perfect power, **`false`** otherwise.

### See Also

-   <span class="function">gmp\_perfect\_square</span>

gmp\_perfect\_square
====================

Perfect square check

### Description

<span class="type">bool</span> <span
class="methodname">gmp\_perfect\_square</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Check if a number is a perfect square.

### Parameters

`num`  
The number being checked as a perfect square.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns **`true`** if `num` is a perfect square, **`false`** otherwise.

### Examples

**Example \#1 <span class="function">gmp\_perfect\_square</span>
example**

``` php
<?php
// 3 * 3, perfect square
var_dump(gmp_perfect_square("9"));

// not a perfect square
var_dump(gmp_perfect_square("7"));

// 1234567890 * 1234567890, perfect square
var_dump(gmp_perfect_square("1524157875019052100"));
?>
```

The above example will output:

    bool(true)
    bool(false)
    bool(true)

### See Also

-   <span class="function">gmp\_perfect\_power</span>
-   <span class="function">gmp\_sqrt</span>
-   <span class="function">gmp\_sqrtrem</span>

gmp\_popcount
=============

Population count

### Description

<span class="type">int</span> <span
class="methodname">gmp\_popcount</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Get the population count.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

The population count of `num`, as an <span class="type">int</span>.

### Examples

**Example \#1 <span class="function">gmp\_popcount</span> example**

``` php
<?php
$pop1 = gmp_init("10000101", 2); // 3 1's
echo gmp_popcount($pop1) . "\n";
$pop2 = gmp_init("11111110", 2); // 7 1's
echo gmp_popcount($pop2) . "\n";
?>
```

The above example will output:

    3
    7

gmp\_pow
========

Raise number into power

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_pow</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> , <span
class="methodparam"><span class="type">int</span> `$exponent`</span> )

Raise `num` into power `exponent`.

### Parameters

`num`  
The base number.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`exponent`  
The positive power to raise the `num`.

### Return Values

The new (raised) number, as a GMP number. The case of *0^0* yields 1.

### Examples

**Example \#1 <span class="function">gmp\_pow</span> example**

``` php
<?php
$pow1 = gmp_pow("2", 31);
echo gmp_strval($pow1) . "\n";
$pow2 = gmp_pow("0", 0);
echo gmp_strval($pow2) . "\n";
$pow3 = gmp_pow("2", -1); // Negative exp, generates warning
echo gmp_strval($pow3) . "\n";
?>
```

The above example will output:

    2147483648
    1

gmp\_powm
=========

Raise number into power with modulo

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_powm</span>
( <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$exponent`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$modulus`</span> )

Calculate (`num` raised into power `exponent`) modulo `modulus`. If
`exponent` is negative, result is undefined.

### Parameters

`num`  
The base number.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`exponent`  
The positive power to raise the `num`.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`modulus`  
The modulo.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

The new (raised) number, as a GMP number.

### Examples

**Example \#1 <span class="function">gmp\_powm</span> example**

``` php
<?php
$pow1 = gmp_powm("2", "31", "2147483649");
echo gmp_strval($pow1) . "\n";
?>
```

The above example will output:

    2147483648

gmp\_prob\_prime
================

Check if number is "probably prime"

### Description

<span class="type">int</span> <span
class="methodname">gmp\_prob\_prime</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> \[, <span
class="methodparam"><span class="type">int</span> `$repetitions`<span
class="initializer"> = 10</span></span> \] )

The function uses Miller-Rabin's probabilistic test to check if a number
is a prime.

### Parameters

`num`  
The number being checked as a prime.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`repetitions`  
Reasonable values of `repetitions` vary from 5 to 10 (default being 10);
a higher value lowers the probability for a non-prime to pass as a
"probable" prime.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

If this function returns 0, `num` is definitely not prime. If it returns
1, then `num` is "probably" prime. If it returns 2, then `num` is surely
prime.

### Examples

**Example \#1 <span class="function">gmp\_prob\_prime</span> example**

``` php
<?php
// definitely not a prime
echo gmp_prob_prime("6") . "\n";

// probably a prime
echo gmp_prob_prime("1111111111111111111") . "\n";

// definitely a prime
echo gmp_prob_prime("11") . "\n";
?>
```

The above example will output:

    0
    1
    2

gmp\_random\_bits
=================

Random number

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_random\_bits</span> ( <span
class="methodparam"><span class="type">int</span> `$bits`</span> )

Generate a random number. The number will be between 0 and (2 \*\*
`bits`) - 1.

`bits` must greater than 0, and the maximum value is restricted by
available memory.

### Parameters

`bits`  
The number of bits.

### Return Values

A random GMP number.

### Examples

**Example \#1 <span class="function">gmp\_random\_bits</span> example**

``` php
<?php
$rand1 = gmp_random_bits(3); // random number from 0 to 7
$rand2 = gmp_random_bits(5); // random number from 0 to 31

echo gmp_strval($rand1) . "\n";
echo gmp_strval($rand2) . "\n";
?>
```

The above example will output:

    3
    15

gmp\_random\_range
==================

Random number

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_random\_range</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$min`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$max`</span> )

Generate a random number. The number will be between `min` and `max`.

`min` and `max` can both be negative but `min` must always be less than
`max`.

### Parameters

`min`  
A GMP number representing the lower bound for the random number

`max`  
A GMP number representing the upper bound for the random number

### Return Values

A random GMP number.

### Examples

**Example \#1 <span class="function">gmp\_random\_range</span> example**

``` php
<?php
$rand1 = gmp_random_range(0, 100);    // random number between 0 and 100
$rand2 = gmp_random_range(-100, -10); // random number between -100 and -10

echo gmp_strval($rand1) . "\n";
echo gmp_strval($rand2) . "\n";
?>
```

The above example will output:

    42
    -67

gmp\_random\_seed
=================

Sets the RNG seed

### Description

<span class="type">void</span> <span
class="methodname">gmp\_random\_seed</span> ( <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$seed`</span> )

### Parameters

`seed`  
The seed to be set for the <span class="function">gmp\_random</span>,
<span class="function">gmp\_random\_bits</span>, and <span
class="function">gmp\_random\_range</span> functions.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns **`null`** on success or **`false`** on failure.

### Errors/Exceptions

Issues an **`E_WARNING`** and returns **`false`** if `seed` is not
valid.

### Examples

**Example \#1 <span class="function">gmp\_random\_seed</span> example**

``` php
<?php
// set the seed
gmp_random_seed(100);

var_dump(gmp_strval(gmp_random(1)));

// set the seed to something else
gmp_random_seed(gmp_init(-100));

var_dump(gmp_strval(gmp_random_bits(10)));

// set the seed to something invalid
var_dump(gmp_random_seed('not a number'));
```

The above example will output:

    string(20) "15370156633245019617"
    string(3) "683"

    Warning: gmp_random_seed(): Unable to convert variable to GMP - string is not an integer in %s on line %d
    bool(false)

### See Also

-   <span class="function">gmp\_init</span>
-   <span class="function">gmp\_random</span>
-   <span class="function">gmp\_random\_bits</span>
-   <span class="function">gmp\_random\_range</span>

gmp\_random
===========

Random number

**Warning**

This function has been *DEPRECATED* as of PHP 7.2.0. Relying on this
function is highly discouraged.

### Description

<span class="type">GMP</span> <span
class="methodname">gmp\_random</span> (\[ <span
class="methodparam"><span class="type">int</span> `$limiter`<span
class="initializer"> = 20</span></span> \] )

Generate a random number. The number will be between 0 and (2 \*\* n) -
1, where n is the number of bits per limb multiplied by `limiter`. If
`limiter` is negative, negative numbers are generated.

A limb is an internal GMP mechanism. The number of bits in a limb is not
static, and can vary from system to system. Generally, the number of
bits in a limb is either 32 or 64, but this is not guaranteed.

### Parameters

`limiter`  
The limiter.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A random GMP number.

### Examples

**Example \#1 <span class="function">gmp\_random</span> example**

``` php
<?php
$rand1 = gmp_random(1); // random number from 0 to 1 * bits per limb
$rand2 = gmp_random(2); // random number from 0 to 2 * bits per limb

echo gmp_strval($rand1) . "\n";
echo gmp_strval($rand2) . "\n";
?>
```

The above example will output:

    1915834968
    8642564075890328087

gmp\_root
=========

Take the integer part of nth root

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_root</span>
( <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> , <span
class="methodparam"><span class="type">int</span> `$nth`</span> )

Takes the `nth` root of `num` and returns the integer component of the
result.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`nth`  
The positive root to take of `num`.

### Return Values

The integer component of the resultant root, as a GMP number.

gmp\_rootrem
============

Take the integer part and remainder of nth root

### Description

<span class="type">array</span> <span
class="methodname">gmp\_rootrem</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num`</span> , <span class="methodparam"><span class="type">int</span>
`$nth`</span> )

Takes the `nth` root of `num` and returns the integer component and
remainder of the result.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`nth`  
The positive root to take of `num`.

### Return Values

A two element array, where the first element is the integer component of
the root, and the second element is the remainder, both represented as
GMP numbers.

gmp\_scan0
==========

Scan for 0

### Description

<span class="type">int</span> <span class="methodname">gmp\_scan0</span>
( <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type">int</span> `$start`</span> )

Scans `num1`, starting with bit `start`, towards more significant bits,
until the first clear bit is found.

### Parameters

`num1`  
The number to scan.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`start`  
The starting bit.

### Return Values

Returns the index of the found bit, as an <span class="type">int</span>.
The index starts from 0.

### Examples

**Example \#1 <span class="function">gmp\_scan0</span> example**

``` php
<?php
// "0" bit is found at position 3. index starts at 0
$s1 = gmp_init("10111", 2);
echo gmp_scan0($s1, 0) . "\n";

// "0" bit is found at position 7. index starts at 5
$s2 = gmp_init("101110000", 2);
echo gmp_scan0($s2, 5) . "\n";
?>
```

The above example will output:

    3
    7

gmp\_scan1
==========

Scan for 1

### Description

<span class="type">int</span> <span class="methodname">gmp\_scan1</span>
( <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type">int</span> `$start`</span> )

Scans `num1`, starting with bit `start`, towards more significant bits,
until the first set bit is found.

### Parameters

`num1`  
The number to scan.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`start`  
The starting bit.

### Return Values

Returns the index of the found bit, as an <span class="type">int</span>.
If no set bit is found, -1 is returned.

### Examples

**Example \#1 <span class="function">gmp\_scan1</span> example**

``` php
<?php
// "1" bit is found at position 3. index starts at 0
$s1 = gmp_init("01000", 2);
echo gmp_scan1($s1, 0) . "\n";

// "1" bit is found at position 9. index starts at 5
$s2 = gmp_init("01000001111", 2);
echo gmp_scan1($s2, 5) . "\n";
?>
```

The above example will output:

    3
    9

gmp\_setbit
===========

Set bit

### Description

<span class="type">void</span> <span
class="methodname">gmp\_setbit</span> ( <span class="methodparam"><span
class="type">GMP</span> `$num`</span> , <span class="methodparam"><span
class="type">int</span> `$index`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$value`<span
class="initializer"> = **`true`**</span></span> \] )

Sets bit `index` in `num`.

### Parameters

`num`  
The value to modify.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`index`  
The index of the bit to set. Index 0 represents the least significant
bit.

`value`  
True to set the bit (set it to 1/on); false to clear the bit (set it to
0/off).

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_setbit</span> example - 0
index**

``` php
<?php
$a = gmp_init("2"); //
echo gmp_strval($a), ' -> 0b', gmp_strval($a, 2), "\n";
gmp_setbit($a, 0); // 0b10 now becomes 0b11
echo gmp_strval($a), ' -> 0b', gmp_strval($a, 2), "\n";
?>
```

The above example will output:

    2 -> 0b10
    3 -> 0b11

**Example \#2 <span class="function">gmp\_setbit</span> example - 1
index**

``` php
<?php
$a = gmp_init("0xfd");
echo gmp_strval($a), ' -> 0b', gmp_strval($a, 2), "\n";
gmp_setbit($a, 1); // index starts at 0
echo gmp_strval($a), ' -> 0b', gmp_strval($a, 2), "\n";
?>
```

The above example will output:

    253 -> 0b11111101
    255 -> 0b11111111

**Example \#3 <span class="function">gmp\_setbit</span> example -
clearing a bit**

``` php
<?php
$a = gmp_init("0xff");
echo gmp_strval($a), ' -> 0b', gmp_strval($a, 2), "\n";
gmp_setbit($a, 0, false); // clear bit at index 0
echo gmp_strval($a), ' -> 0b', gmp_strval($a, 2), "\n";
?>
```

The above example will output:

    255 -> 0b11111111
    254 -> 0b11111110

### Notes

> **Note**:
>
> Unlike most of the other GMP functions, <span
> class="function">gmp\_setbit</span> must be called with a GMP object
> that already exists (using <span class="function">gmp\_init</span> for
> example). One will not be automatically created.

### See Also

-   <span class="function">gmp\_clrbit</span>
-   <span class="function">gmp\_testbit</span>

gmp\_sign
=========

Sign of number

### Description

<span class="type">int</span> <span class="methodname">gmp\_sign</span>
( <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Checks the sign of a number.

### Parameters

`num`  
Either a GMP number <span class="type">resource</span> in PHP 5.5 and
earlier, a <span class="classname">GMP</span> object in PHP 5.6 and
later, or a numeric string provided that it is possible to convert the
latter to an <span class="type">int</span>.

### Return Values

Returns 1 if `num` is positive, -1 if `num` is negative, and 0 if `num`
is zero.

### Examples

**Example \#1 <span class="function">gmp\_sign</span> example**

``` php
<?php
// positive
echo gmp_sign("500") . "\n";

// negative
echo gmp_sign("-500") . "\n";

// zero
echo gmp_sign("0") . "\n";
?>
```

The above example will output:

    1
    -1
    0

### See Also

-   <span class="function">gmp\_abs</span>
-   <span class="function">abs</span>

gmp\_sqrt
=========

Calculate square root

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_sqrt</span>
( <span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num`</span> )

Calculates square root of `num`.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

The integer portion of the square root, as a GMP number.

### Examples

**Example \#1 <span class="function">gmp\_sqrt</span> example**

``` php
<?php
$sqrt1 = gmp_sqrt("9");
$sqrt2 = gmp_sqrt("7");
$sqrt3 = gmp_sqrt("1524157875019052100");

echo gmp_strval($sqrt1) . "\n";
echo gmp_strval($sqrt2) . "\n";
echo gmp_strval($sqrt3) . "\n";
?>
```

The above example will output:

    3
    2
    1234567890

gmp\_sqrtrem
============

Square root with remainder

### Description

<span class="type">array</span> <span
class="methodname">gmp\_sqrtrem</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num`</span> )

Calculate the square root of a number, with remainder.

### Parameters

`num`  
The number being square rooted.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

Returns array where first element is the integer square root of `num`
and the second is the remainder (i.e., the difference between `num` and
the first element squared).

### Examples

**Example \#1 <span class="function">gmp\_sqrtrem</span> example**

``` php
<?php
list($sqrt1, $sqrt1rem) = gmp_sqrtrem("9");
list($sqrt2, $sqrt2rem) = gmp_sqrtrem("7");
list($sqrt3, $sqrt3rem) = gmp_sqrtrem("1048576");

echo gmp_strval($sqrt1) . ", " . gmp_strval($sqrt1rem) . "\n";
echo gmp_strval($sqrt2) . ", " . gmp_strval($sqrt2rem) . "\n";
echo gmp_strval($sqrt3) . ", " . gmp_strval($sqrt3rem) . "\n";
?>
```

The above example will output:

    3, 0
    2, 3
    1024, 0

gmp\_strval
===========

Convert GMP number to string

### Description

<span class="type">string</span> <span
class="methodname">gmp\_strval</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num`</span> \[, <span class="methodparam"><span
class="type">int</span> `$base`<span class="initializer"> =
10</span></span> \] )

Convert GMP number to string representation in base `base`. The default
base is 10.

### Parameters

`num`  
The GMP number that will be converted to a string.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`base`  
The base of the returned number. The default base is 10. Allowed values
for the base are from 2 to 62 and -2 to -36.

### Return Values

The number, as a <span class="type">string</span>.

### Examples

**Example \#1 Converting a GMP number to a string**

``` php
<?php
$a = gmp_init("0x41682179fbf5");
printf("Decimal: %s, 36-based: %s", gmp_strval($a), gmp_strval($a,36));
?>
```

gmp\_sub
========

Subtract numbers

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_sub</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Subtracts `num2` from `num1` and returns the result.

### Parameters

`num1`  
The number being subtracted from.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
The number subtracted from `num1`.

A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_sub</span> example**

``` php
<?php
$sub = gmp_sub("281474976710656", "4294967296"); // 2^48 - 2^32
echo gmp_strval($sub) . "\n";
?>
```

The above example will output:

    281470681743360

gmp\_testbit
============

Tests if a bit is set

### Description

<span class="type">bool</span> <span
class="methodname">gmp\_testbit</span> ( <span class="methodparam"><span
class="type"><span class="type">GMP</span><span
class="type">int</span><span class="type">string</span></span>
`$num`</span> , <span class="methodparam"><span class="type">int</span>
`$index`</span> )

Tests if the specified bit is set.

### Parameters

`num`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`index`  
The bit to test

### Return Values

Returns **`true`** if the bit is set in resource `$a`, otherwise
**`false`**.

### Errors/Exceptions

An **`E_WARNING`** level error is issued when `index` is less than zero,
and **`false`** is returned.

### Examples

**Example \#1 <span class="function">gmp\_testbit</span> example**

``` php
<?php
$n = gmp_init("1000000");
var_dump(gmp_testbit($n, 1));
gmp_setbit($n, 1);
var_dump(gmp_testbit($n, 1));
?>
```

The above example will output:

    bool(false)
    bool(true)

### See Also

-   <span class="function">gmp\_setbit</span>
-   <span class="function">gmp\_clrbit</span>

gmp\_xor
========

Bitwise XOR

### Description

<span class="type">GMP</span> <span class="methodname">gmp\_xor</span> (
<span class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num1`</span> , <span
class="methodparam"><span class="type"><span
class="type">GMP</span><span class="type">int</span><span
class="type">string</span></span> `$num2`</span> )

Calculates bitwise exclusive OR (XOR) of two GMP numbers.

### Parameters

`num1`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

`num2`  
A <span class="classname">GMP</span> object, an <span
class="type">int</span> or a numeric <span class="type">string</span>.

### Return Values

A <span class="classname">GMP</span> object.

### Examples

**Example \#1 <span class="function">gmp\_xor</span> example**

``` php
<?php
$xor1 = gmp_init("1101101110011101", 2);
$xor2 = gmp_init("0110011001011001", 2);

$xor3 = gmp_xor($xor1, $xor2);

echo gmp_strval($xor3, 2) . "\n";
?>
```

The above example will output:

    1011110111000100

**Table of Contents**

-   [gmp\_abs](/ref/gmp.html#gmp_abs) — Absolute value
-   [gmp\_add](/ref/gmp.html#gmp_add) — Add numbers
-   [gmp\_and](/ref/gmp.html#gmp_and) — Bitwise AND
-   [gmp\_binomial](/ref/gmp.html#gmp_binomial) — Calculates binomial
    coefficient
-   [gmp\_clrbit](/ref/gmp.html#gmp_clrbit) — Clear bit
-   [gmp\_cmp](/ref/gmp.html#gmp_cmp) — Compare numbers
-   [gmp\_com](/ref/gmp.html#gmp_com) — Calculates one's complement
-   [gmp\_div\_q](/ref/gmp.html#gmp_div_q) — Divide numbers
-   [gmp\_div\_qr](/ref/gmp.html#gmp_div_qr) — Divide numbers and get
    quotient and remainder
-   [gmp\_div\_r](/ref/gmp.html#gmp_div_r) — Remainder of the division
    of numbers
-   [gmp\_div](/ref/gmp.html#gmp_div) — Alias of gmp\_div\_q
-   [gmp\_divexact](/ref/gmp.html#gmp_divexact) — Exact division of
    numbers
-   [gmp\_export](/ref/gmp.html#gmp_export) — Export to a binary string
-   [gmp\_fact](/ref/gmp.html#gmp_fact) — Factorial
-   [gmp\_gcd](/ref/gmp.html#gmp_gcd) — Calculate GCD
-   [gmp\_gcdext](/ref/gmp.html#gmp_gcdext) — Calculate GCD and
    multipliers
-   [gmp\_hamdist](/ref/gmp.html#gmp_hamdist) — Hamming distance
-   [gmp\_import](/ref/gmp.html#gmp_import) — Import from a binary
    string
-   [gmp\_init](/ref/gmp.html#gmp_init) — Create GMP number
-   [gmp\_intval](/ref/gmp.html#gmp_intval) — Convert GMP number to
    integer
-   [gmp\_invert](/ref/gmp.html#gmp_invert) — Inverse by modulo
-   [gmp\_jacobi](/ref/gmp.html#gmp_jacobi) — Jacobi symbol
-   [gmp\_kronecker](/ref/gmp.html#gmp_kronecker) — Kronecker symbol
-   [gmp\_lcm](/ref/gmp.html#gmp_lcm) — Calculate LCM
-   [gmp\_legendre](/ref/gmp.html#gmp_legendre) — Legendre symbol
-   [gmp\_mod](/ref/gmp.html#gmp_mod) — Modulo operation
-   [gmp\_mul](/ref/gmp.html#gmp_mul) — Multiply numbers
-   [gmp\_neg](/ref/gmp.html#gmp_neg) — Negate number
-   [gmp\_nextprime](/ref/gmp.html#gmp_nextprime) — Find next prime
    number
-   [gmp\_or](/ref/gmp.html#gmp_or) — Bitwise OR
-   [gmp\_perfect\_power](/ref/gmp.html#gmp_perfect_power) — Perfect
    power check
-   [gmp\_perfect\_square](/ref/gmp.html#gmp_perfect_square) — Perfect
    square check
-   [gmp\_popcount](/ref/gmp.html#gmp_popcount) — Population count
-   [gmp\_pow](/ref/gmp.html#gmp_pow) — Raise number into power
-   [gmp\_powm](/ref/gmp.html#gmp_powm) — Raise number into power with
    modulo
-   [gmp\_prob\_prime](/ref/gmp.html#gmp_prob_prime) — Check if number
    is "probably prime"
-   [gmp\_random\_bits](/ref/gmp.html#gmp_random_bits) — Random number
-   [gmp\_random\_range](/ref/gmp.html#gmp_random_range) — Random number
-   [gmp\_random\_seed](/ref/gmp.html#gmp_random_seed) — Sets the RNG
    seed
-   [gmp\_random](/ref/gmp.html#gmp_random) — Random number
-   [gmp\_root](/ref/gmp.html#gmp_root) — Take the integer part of nth
    root
-   [gmp\_rootrem](/ref/gmp.html#gmp_rootrem) — Take the integer part
    and remainder of nth root
-   [gmp\_scan0](/ref/gmp.html#gmp_scan0) — Scan for 0
-   [gmp\_scan1](/ref/gmp.html#gmp_scan1) — Scan for 1
-   [gmp\_setbit](/ref/gmp.html#gmp_setbit) — Set bit
-   [gmp\_sign](/ref/gmp.html#gmp_sign) — Sign of number
-   [gmp\_sqrt](/ref/gmp.html#gmp_sqrt) — Calculate square root
-   [gmp\_sqrtrem](/ref/gmp.html#gmp_sqrtrem) — Square root with
    remainder
-   [gmp\_strval](/ref/gmp.html#gmp_strval) — Convert GMP number to
    string
-   [gmp\_sub](/ref/gmp.html#gmp_sub) — Subtract numbers
-   [gmp\_testbit](/ref/gmp.html#gmp_testbit) — Tests if a bit is set
-   [gmp\_xor](/ref/gmp.html#gmp_xor) — Bitwise XOR

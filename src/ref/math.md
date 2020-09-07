abs
===

Absolute value

### Description

<span class="type">number</span> <span class="methodname">abs</span> (
<span class="methodparam"><span class="type">mixed</span>
`$number`</span> )

Returns the absolute value of `number`.

### Parameters

`number`  
The numeric value to process

### Return Values

The absolute value of `number`. If the argument `number` is of type
<span class="type">float</span>, the return type is also <span
class="type">float</span>, otherwise it is <span
class="type">integer</span> (as <span class="type">float</span> usually
has a bigger value range than <span class="type">integer</span>).

### Examples

**Example \#1 <span class="function">abs</span> example**

``` php
<?php
echo abs(-4.2); // 4.2 (double/float)
echo abs(5);    // 5 (integer)
echo abs(-5);   // 5 (integer)
?>
```

### See Also

-   <span class="function">gmp\_abs</span>
-   <span class="function">gmp\_sign</span>

acos
====

Arc cosine

### Description

<span class="type">float</span> <span class="methodname">acos</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the arc cosine of `arg` in radians. <span
class="function">acos</span> is the inverse function of <span
class="function">cos</span>, which means that *a==cos(acos(a))* for
every value of a that is within <span class="function">acos</span>'
range.

### Parameters

`arg`  
The argument to process

### Return Values

The arc cosine of `arg` in radians.

### See Also

-   <span class="function">cos</span>
-   <span class="function">acosh</span>
-   <span class="function">asin</span>
-   <span class="function">atan</span>

acosh
=====

Inverse hyperbolic cosine

### Description

<span class="type">float</span> <span class="methodname">acosh</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the inverse hyperbolic cosine of `arg`, i.e. the value whose
hyperbolic cosine is `arg`.

### Parameters

`arg`  
The value to process

### Return Values

The inverse hyperbolic cosine of `arg`

### Changelog

| Version | Description                                     |
|---------|-------------------------------------------------|
| 5.3.0   | This function is now available on all platforms |

### See Also

-   <span class="function">cosh</span>
-   <span class="function">acos</span>
-   <span class="function">asinh</span>
-   <span class="function">atanh</span>

asin
====

Arc sine

### Description

<span class="type">float</span> <span class="methodname">asin</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the arc sine of `arg` in radians. <span
class="function">asin</span> is the inverse function of <span
class="function">sin</span>, which means that *a==sin(asin(a))* for
every value of a that is within <span class="function">asin</span>'s
range.

### Parameters

`arg`  
The argument to process

### Return Values

The arc sine of `arg` in radians

### See Also

-   <span class="function">sin</span>
-   <span class="function">asinh</span>
-   <span class="function">acos</span>
-   <span class="function">atan</span>

asinh
=====

Inverse hyperbolic sine

### Description

<span class="type">float</span> <span class="methodname">asinh</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the inverse hyperbolic sine of `arg`, i.e. the value whose
hyperbolic sine is `arg`.

### Parameters

`arg`  
The argument to process

### Return Values

The inverse hyperbolic sine of `arg`

### Changelog

| Version | Description                                     |
|---------|-------------------------------------------------|
| 5.3.0   | This function is now available on all platforms |

### See Also

-   <span class="function">sinh</span>
-   <span class="function">asin</span>
-   <span class="function">acosh</span>
-   <span class="function">atanh</span>

atan2
=====

Arc tangent of two variables

### Description

<span class="type">float</span> <span class="methodname">atan2</span> (
<span class="methodparam"><span class="type">float</span> `$y`</span> ,
<span class="methodparam"><span class="type">float</span> `$x`</span> )

This function calculates the arc tangent of the two variables `x` and
`y`. It is similar to calculating the arc tangent of `y` / `x`, except
that the signs of both arguments are used to determine the quadrant of
the result.

The function returns the result in radians, which is between -PI and PI
(inclusive).

### Parameters

`y`  
Dividend parameter

`x`  
Divisor parameter

### Return Values

The arc tangent of `y`/`x` in radians.

### See Also

-   <span class="function">atan</span>

atan
====

Arc tangent

### Description

<span class="type">float</span> <span class="methodname">atan</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the arc tangent of `arg` in radians. <span
class="function">atan</span> is the inverse function of <span
class="function">tan</span>, which means that *a==tan(atan(a))* for
every value of a that is within <span class="function">atan</span>'s
range.

### Parameters

`arg`  
The argument to process

### Return Values

The arc tangent of `arg` in radians.

### See Also

-   <span class="function">tan</span>
-   <span class="function">atanh</span>
-   <span class="function">asin</span>
-   <span class="function">acos</span>

atanh
=====

Inverse hyperbolic tangent

### Description

<span class="type">float</span> <span class="methodname">atanh</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the inverse hyperbolic tangent of `arg`, i.e. the value whose
hyperbolic tangent is `arg`.

### Parameters

`arg`  
The argument to process

### Return Values

Inverse hyperbolic tangent of `arg`

### Changelog

| Version | Description                                     |
|---------|-------------------------------------------------|
| 5.3.0   | This function is now available on all platforms |

### See Also

-   <span class="function">tanh</span>
-   <span class="function">atan</span>
-   <span class="function">asinh</span>
-   <span class="function">acosh</span>

base\_convert
=============

Convert a number between arbitrary bases

### Description

<span class="type">string</span> <span
class="methodname">base\_convert</span> ( <span
class="methodparam"><span class="type">string</span> `$number`</span> ,
<span class="methodparam"><span class="type">int</span>
`$frombase`</span> , <span class="methodparam"><span
class="type">int</span> `$tobase`</span> )

Returns a string containing `number` represented in base `tobase`. The
base in which `number` is given is specified in `frombase`. Both
`frombase` and `tobase` have to be between 2 and 36, inclusive. Digits
in numbers with a base higher than 10 will be represented with the
letters a-z, with a meaning 10, b meaning 11 and z meaning 35. The case
of the letters doesn't matter, i.e. `number` is interpreted
case-insensitively.

**Warning**

<span class="function">base\_convert</span> may lose precision on large
numbers due to properties related to the internal "double" or "float"
type used. Please see the
<a href="/language/types/float.html" class="link">Floating point numbers</a>
section in the manual for more specific information and limitations.

### Parameters

`number`  
The number to convert. Any invalid characters in `number` are silently
ignored. As of PHP 7.4.0 supplying any invalid characters is deprecated.

`frombase`  
The base `number` is in

`tobase`  
The base to convert `number` to

### Return Values

`number` converted to base `tobase`

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | Passing invalid characters will now generate a deprecation notice. The result will still be computed as if the invalid characters did not exist. |

### Examples

**Example \#1 <span class="function">base\_convert</span> example**

``` php
<?php
$hexadecimal = 'a37334';
echo base_convert($hexadecimal, 16, 2);
?>
```

The above example will output:

    101000110111001100110100

### See Also

-   <span class="function">intval</span>

bindec
======

Binary to decimal

### Description

<span class="type">number</span> <span class="methodname">bindec</span>
( <span class="methodparam"><span class="type">string</span>
`$binary_string`</span> )

Returns the decimal equivalent of the binary number represented by the
`binary_string` argument.

<span class="function">bindec</span> converts a binary number to an
<span class="type">integer</span> or, if needed for size reasons, <span
class="type">float</span>.

<span class="function">bindec</span> interprets all `binary_string`
values as unsigned integers. This is because <span
class="function">bindec</span> sees the most significant bit as another
order of magnitude rather than as the sign bit.

### Parameters

`binary_string`  
The binary string to convert. Any invalid characters in `binary_string`
are silently ignored. As of PHP 7.4.0 supplying any invalid characters
is deprecated.

**Warning**

The parameter must be a string. Using other data types will produce
unexpected results.

### Return Values

The decimal value of `binary_string`

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | Passing invalid characters will now generate a deprecation notice. The result will still be computed as if the invalid characters did not exist. |

### Examples

**Example \#1 <span class="function">bindec</span> example**

``` php
<?php
echo bindec('110011') . "\n";
echo bindec('000110011') . "\n";

echo bindec('111');
?>
```

The above example will output:

    51
    51
    7

**Example \#2 <span class="function">bindec</span> interprets input as
unsigned integers**

``` php
<?php
/*
 * The lesson from this example is in the output
 * rather than the PHP code itself.
 */

$magnitude_lower = pow(2, (PHP_INT_SIZE * 8) - 2);
p($magnitude_lower - 1);
p($magnitude_lower, 'See the rollover?  Watch it next time around...');

p(PHP_INT_MAX, 'PHP_INT_MAX');
p(~PHP_INT_MAX, 'interpreted to be one more than PHP_INT_MAX');

if (PHP_INT_SIZE == 4) {
    $note = 'interpreted to be the largest unsigned integer';
} else {
    $note = 'interpreted to be the largest unsigned integer
              (18446744073709551615) but skewed by float precision';
}
p(-1, $note);


function p($input, $note = '') {
    echo "input:        $input\n";

    $format = '%0' . (PHP_INT_SIZE * 8) . 'b';
    $bin = sprintf($format, $input);
    echo "binary:       $bin\n";

    ini_set('precision', 20);  // For readability on 64 bit boxes.
    $dec = bindec($bin);
    echo 'bindec():     ' . $dec . "\n";

    if ($note) {
        echo "NOTE:         $note\n";
    }

    echo "\n";
}
?>
```

Output of the above example on 32 bit machines:

    input:        1073741823
    binary:       00111111111111111111111111111111
    bindec():     1073741823

    input:        1073741824
    binary:       01000000000000000000000000000000
    bindec():     1073741824
    NOTE:         See the rollover?  Watch it next time around...

    input:        2147483647
    binary:       01111111111111111111111111111111
    bindec():     2147483647
    NOTE:         PHP_INT_MAX

    input:        -2147483648
    binary:       10000000000000000000000000000000
    bindec():     2147483648
    NOTE:         interpreted to be one more than PHP_INT_MAX

    input:        -1
    binary:       11111111111111111111111111111111
    bindec():     4294967295
    NOTE:         interpreted to be the largest unsigned integer

Output of the above example on 64 bit machines:

    input:        4611686018427387903
    binary:       0011111111111111111111111111111111111111111111111111111111111111
    bindec():     4611686018427387903

    input:        4611686018427387904
    binary:       0100000000000000000000000000000000000000000000000000000000000000
    bindec():     4611686018427387904
    NOTE:         See the rollover?  Watch it next time around...

    input:        9223372036854775807
    binary:       0111111111111111111111111111111111111111111111111111111111111111
    bindec():     9223372036854775807
    NOTE:         PHP_INT_MAX

    input:        -9223372036854775808
    binary:       1000000000000000000000000000000000000000000000000000000000000000
    bindec():     9223372036854775808
    NOTE:         interpreted to be one more than PHP_INT_MAX

    input:        -1
    binary:       1111111111111111111111111111111111111111111111111111111111111111
    bindec():     18446744073709551616
    NOTE:         interpreted to be the largest unsigned integer
                  (18446744073709551615) but skewed by float precision

### Notes

> **Note**:
>
> The function can convert numbers that are too large to fit into the
> platforms <span class="type">integer</span> type, larger values are
> returned as <span class="type">float</span> in that case.

### See Also

-   <span class="function">decbin</span>
-   <span class="function">octdec</span>
-   <span class="function">hexdec</span>
-   <span class="function">base\_convert</span>

ceil
====

Round fractions up

### Description

<span class="type">float</span> <span class="methodname">ceil</span> (
<span class="methodparam"><span class="type">float</span>
`$value`</span> )

Returns the next highest integer value by rounding up `value` if
necessary.

### Parameters

`value`  
The value to round

### Return Values

`value` rounded up to the next highest integer. The return value of
<span class="function">ceil</span> is still of type <span
class="type">float</span> as the value range of <span
class="type">float</span> is usually bigger than that of <span
class="type">integer</span>.

### Examples

**Example \#1 <span class="function">ceil</span> example**

``` php
<?php
echo ceil(4.3);    // 5
echo ceil(9.999);  // 10
echo ceil(-3.14);  // -3
?>
```

### See Also

-   <span class="function">floor</span>
-   <span class="function">round</span>

cos
===

Cosine

### Description

<span class="type">float</span> <span class="methodname">cos</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

<span class="function">cos</span> returns the cosine of the `arg`
parameter. The `arg` parameter is in radians.

### Parameters

`arg`  
An angle in radians

### Return Values

The cosine of `arg`

### Examples

**Example \#1 <span class="function">cos</span> example**

``` php
<?php

echo cos(M_PI); // -1

?>
```

### See Also

-   <span class="function">acos</span>
-   <span class="function">sin</span>
-   <span class="function">tan</span>
-   <span class="function">deg2rad</span>

cosh
====

Hyperbolic cosine

### Description

<span class="type">float</span> <span class="methodname">cosh</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the hyperbolic cosine of `arg`, defined as *(exp(arg) +
exp(-arg))/2*.

### Parameters

`arg`  
The argument to process

### Return Values

The hyperbolic cosine of `arg`

### See Also

-   <span class="function">cos</span>
-   <span class="function">acosh</span>
-   <span class="function">sinh</span>
-   <span class="function">tanh</span>

decbin
======

Decimal to binary

### Description

<span class="type">string</span> <span class="methodname">decbin</span>
( <span class="methodparam"><span class="type">int</span>
`$number`</span> )

Returns a string containing a binary representation of the given
`number` argument.

### Parameters

`number`  
Decimal value to convert

**Range of inputs on 32-bit machines**

positive `number`

### Return Values

Binary string representation of `number`

### Examples

**Example \#1 <span class="function">decbin</span> example**

``` php
<?php
echo decbin(12) . "\n";
echo decbin(26);
?>
```

The above example will output:

    1100
    11010

### See Also

-   <span class="function">bindec</span>
-   <span class="function">decoct</span>
-   <span class="function">dechex</span>
-   <span class="function">base\_convert</span>
-   <span class="function">printf</span>, using *%b*, *%032b* or *%064b*
    as the format
-   <span class="function">sprintf</span>, using *%b*, *%032b* or
    *%064b* as the format

dechex
======

Decimal to hexadecimal

### Description

<span class="type">string</span> <span class="methodname">dechex</span>
( <span class="methodparam"><span class="type">int</span>
`$number`</span> )

Returns a string containing a hexadecimal representation of the given
unsigned `number` argument.

The largest number that can be converted is **`PHP_INT_MAX`** *\* 2 + 1*
(or *-1*): on 32-bit platforms, this will be *4294967295* in decimal,
which results in <span class="function">dechex</span> returning
*ffffffff*.

### Parameters

`number`  
The decimal value to convert.

As PHP's <span class="type">integer</span> type is signed, but <span
class="function">dechex</span> deals with unsigned integers, negative
integers will be treated as though they were unsigned.

### Return Values

Hexadecimal string representation of `number`.

### Examples

**Example \#1 <span class="function">dechex</span> example**

``` php
<?php
echo dechex(10) . "\n";
echo dechex(47);
?>
```

The above example will output:

    a
    2f

**Example \#2 <span class="function">dechex</span> example with large
integers**

``` php
<?php
// The output below assumes a 32-bit platform.
// Note that the output is the same for all values.
echo dechex(-1)."\n";
echo dechex(PHP_INT_MAX * 2 + 1)."\n";
echo dechex(pow(2, 32) - 1)."\n";
?>
```

The above example will output:

    ffffffff
    ffffffff
    ffffffff

### See Also

-   <span class="function">hexdec</span>
-   <span class="function">decbin</span>
-   <span class="function">decoct</span>
-   <span class="function">base\_convert</span>

decoct
======

Decimal to octal

### Description

<span class="type">string</span> <span class="methodname">decoct</span>
( <span class="methodparam"><span class="type">int</span>
`$number`</span> )

Returns a string containing an octal representation of the given
`number` argument. The largest number that can be converted depends on
the platform in use. For 32-bit platforms this is usually *4294967295*
in decimal resulting in *37777777777*. For 64-bit platforms this is
usually *9223372036854775807* in decimal resulting in
*777777777777777777777*.

### Parameters

`number`  
Decimal value to convert

### Return Values

Octal string representation of `number`

### Examples

**Example \#1 <span class="function">decoct</span> example**

``` php
<?php
echo decoct(15) . "\n";
echo decoct(264);
?>
```

The above example will output:

    17
    410

### See Also

-   <span class="function">octdec</span>
-   <span class="function">decbin</span>
-   <span class="function">dechex</span>
-   <span class="function">base\_convert</span>

deg2rad
=======

Converts the number in degrees to the radian equivalent

### Description

<span class="type">float</span> <span class="methodname">deg2rad</span>
( <span class="methodparam"><span class="type">float</span>
`$number`</span> )

This function converts `number` from degrees to the radian equivalent.

### Parameters

`number`  
Angular value in degrees

### Return Values

The radian equivalent of `number`

### Examples

**Example \#1 <span class="function">deg2rad</span> example**

``` php
<?php

echo deg2rad(45); // 0.785398163397
var_dump(deg2rad(45) === M_PI_4); // bool(true)

?>
```

### See Also

-   <span class="function">rad2deg</span>

exp
===

Calculates the exponent of **`e`**

### Description

<span class="type">float</span> <span class="methodname">exp</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns **`e`** raised to the power of `arg`.

> **Note**:
>
> '**`e`**' is the base of the natural system of logarithms, or
> approximately 2.718282.

### Parameters

`arg`  
The argument to process

### Return Values

'e' raised to the power of `arg`

### Examples

**Example \#1 <span class="function">exp</span> example**

``` php
<?php
echo exp(12) . "\n";
echo exp(5.7);
?>
```

The above example will output:

    1.6275E+005
    298.87

### See Also

-   <span class="function">log</span>
-   <span class="function">pow</span>

expm1
=====

Returns exp(number) - 1, computed in a way that is accurate even when
the value of number is close to zero

### Description

<span class="type">float</span> <span class="methodname">expm1</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

<span class="function">expm1</span> returns the equivalent to
'exp(`arg`) - 1' computed in a way that is accurate even if the value of
`arg` is near zero, a case where 'exp (`arg`) - 1' would be inaccurate
due to subtraction of two numbers that are nearly equal.

### Parameters

`arg`  
The argument to process

### Return Values

'e' to the power of `arg` minus one

### Changelog

| Version | Description                                     |
|---------|-------------------------------------------------|
| 5.3.0   | This function is now available on all platforms |

### See Also

-   <span class="function">log1p</span>
-   <span class="function">exp</span>

floor
=====

Round fractions down

### Description

<span class="type">float</span> <span class="methodname">floor</span> (
<span class="methodparam"><span class="type">float</span>
`$value`</span> )

Returns the next lowest integer value (as float) by rounding down
`value` if necessary.

### Parameters

`value`  
The numeric value to round

### Return Values

`value` rounded to the next lowest integer. The return value of <span
class="function">floor</span> is still of type <span
class="type">float</span> because the value range of <span
class="type">float</span> is usually bigger than that of <span
class="type">integer</span>. This function returns **`FALSE`** in case
of an error (e.g. passing an array).

### Examples

**Example \#1 <span class="function">floor</span> example**

``` php
<?php
echo floor(4.3);   // 4
echo floor(9.999); // 9
echo floor(-3.14); // -4
?>
```

### See Also

-   <span class="function">ceil</span>
-   <span class="function">round</span>

fmod
====

Returns the floating point remainder (modulo) of the division of the
arguments

### Description

<span class="type">float</span> <span class="methodname">fmod</span> (
<span class="methodparam"><span class="type">float</span> `$x`</span> ,
<span class="methodparam"><span class="type">float</span> `$y`</span> )

Returns the floating point remainder of dividing the dividend (`x`) by
the divisor (`y`). The remainder (`r`) is defined as: x = i \* y + r,
for some integer `i`. If `y` is non-zero, `r` has the same sign as `x`
and a magnitude less than the magnitude of `y`.

### Parameters

`x`  
The dividend

`y`  
The divisor

### Return Values

The floating point remainder of `x`/`y`

### Examples

**Example \#1 Using <span class="function">fmod</span>**

``` php
<?php
$x = 5.7;
$y = 1.3;
$r = fmod($x, $y);
// $r equals 0.5, because 4 * 1.3 + 0.5 = 5.7
?>
```

### See Also

-   <a href="/language/operators/arithmetic.html" class="link"><em>/</em></a> -
    Floating-point division
-   <a href="/language/operators/arithmetic.html" class="link"><em>%</em></a> -
    Integer modulus
-   <span class="function">intdiv</span> - Integer division

getrandmax
==========

Show largest possible random value

### Description

<span class="type">int</span> <span class="methodname">getrandmax</span>
( <span class="methodparam">void</span> )

Returns the maximum value that can be returned by a call to <span
class="function">rand</span>.

### Return Values

The largest possible random value returned by <span
class="function">rand</span>

### See Also

-   <span class="function">rand</span>
-   <span class="function">srand</span>
-   <span class="function">mt\_getrandmax</span>

hexdec
======

Hexadecimal to decimal

### Description

<span class="type">number</span> <span class="methodname">hexdec</span>
( <span class="methodparam"><span class="type">string</span>
`$hex_string`</span> )

Returns the decimal equivalent of the hexadecimal number represented by
the `hex_string` argument. <span class="function">hexdec</span> converts
a hexadecimal string to a decimal number.

<span class="function">hexdec</span> will ignore any non-hexadecimal
characters it encounters. As of PHP 7.4.0 supplying any invalid
characters is deprecated.

### Parameters

`hex_string`  
The hexadecimal string to convert

### Return Values

The decimal representation of `hex_string`

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | Passing invalid characters will now generate a deprecation notice. The result will still be computed as if the invalid characters did not exist. |

### Examples

**Example \#1 <span class="function">hexdec</span> example**

``` php
<?php
var_dump(hexdec("See"));
var_dump(hexdec("ee"));
// both print "int(238)"

var_dump(hexdec("that")); // print "int(10)"
var_dump(hexdec("a0")); // print "int(160)"
?>
```

### Notes

> **Note**:
>
> The function can convert numbers that are too large to fit into the
> platforms <span class="type">integer</span> type, larger values are
> returned as <span class="type">float</span> in that case.

### See Also

-   <span class="function">dechex</span>
-   <span class="function">bindec</span>
-   <span class="function">octdec</span>
-   <span class="function">base\_convert</span>

hypot
=====

Calculate the length of the hypotenuse of a right-angle triangle

### Description

<span class="type">float</span> <span class="methodname">hypot</span> (
<span class="methodparam"><span class="type">float</span> `$x`</span> ,
<span class="methodparam"><span class="type">float</span> `$y`</span> )

<span class="function">hypot</span> returns the length of the hypotenuse
of a right-angle triangle with sides of length `x` and `y`, or the
distance of the point (`x`, `y`) from the origin. This is equivalent to
*sqrt(x\*x + y\*y)*.

### Parameters

`x`  
Length of first side

`y`  
Length of second side

### Return Values

Calculated length of the hypotenuse

intdiv
======

Integer division

### Description

<span class="type">int</span> <span class="methodname">intdiv</span> (
<span class="methodparam"><span class="type">int</span>
`$dividend`</span> , <span class="methodparam"><span
class="type">int</span> `$divisor`</span> )

Returns the integer quotient of the division of `dividend` by `divisor`.

### Parameters

`dividend`  
Number to be divided.

`divisor`  
Number which divides the `dividend`.

### Return Values

The integer quotient of the division of `dividend` by `divisor`.

### Errors/Exceptions

If `divisor` is *0*, a <span
class="classname">DivisionByZeroError</span> exception is thrown. If the
`dividend` is **`PHP_INT_MIN`** and the `divisor` is *-1*, then an <span
class="classname">ArithmeticError</span> exception is thrown.

### Examples

**Example \#1 <span class="function">intdiv</span> example**

``` php
<?php
var_dump(intdiv(3, 2));
var_dump(intdiv(-3, 2));
var_dump(intdiv(3, -2));
var_dump(intdiv(-3, -2));
var_dump(intdiv(PHP_INT_MAX, PHP_INT_MAX));
var_dump(intdiv(PHP_INT_MIN, PHP_INT_MIN));
var_dump(intdiv(PHP_INT_MIN, -1));
var_dump(intdiv(1, 0));
?>
```

    int(1)
    int(-1)
    int(-1)
    int(1)
    int(1)
    int(1)

    Fatal error: Uncaught ArithmeticError: Division of PHP_INT_MIN by -1 is not an integer in %s on line 8
    Fatal error: Uncaught DivisionByZeroError: Division by zero in %s on line 9

### See Also

-   <a href="/language/operators/arithmetic.html" class="link"><em>/</em></a> -
    Floating-point division
-   <a href="/language/operators/arithmetic.html" class="link"><em>%</em></a> -
    Integer modulus
-   <span class="function">fmod</span> - Floating-point modulo

is\_finite
==========

Finds whether a value is a legal finite number

### Description

<span class="type">bool</span> <span
class="methodname">is\_finite</span> ( <span class="methodparam"><span
class="type">float</span> `$val`</span> )

Checks whether `val` is a legal finite on this platform.

### Parameters

`val`  
The value to check

### Return Values

**`TRUE`** if `val` is a legal finite number within the allowed range
for a PHP float on this platform, else **`FALSE`**.

### See Also

-   <span class="function">is\_infinite</span>
-   <span class="function">is\_nan</span>

is\_infinite
============

Finds whether a value is infinite

### Description

<span class="type">bool</span> <span
class="methodname">is\_infinite</span> ( <span class="methodparam"><span
class="type">float</span> `$val`</span> )

Returns **`TRUE`** if `val` is infinite (positive or negative), like the
result of *log(0)* or any value too big to fit into a float on this
platform.

### Parameters

`val`  
The value to check

### Return Values

**`TRUE`** if `val` is infinite, else **`FALSE`**.

### See Also

-   <span class="function">is\_finite</span>
-   <span class="function">is\_nan</span>

is\_nan
=======

Finds whether a value is not a number

### Description

<span class="type">bool</span> <span class="methodname">is\_nan</span> (
<span class="methodparam"><span class="type">float</span> `$val`</span>
)

Checks whether `val` is 'not a number', like the result of *acos(1.01)*.

### Parameters

`val`  
The value to check

### Return Values

Returns **`TRUE`** if `val` is 'not a number', else **`FALSE`**.

### Examples

**Example \#1 <span class="function">is\_nan</span> example**

``` php
<?php
// Invalid calculation, will return a 
// NaN value
$nan = acos(8);

var_dump($nan, is_nan($nan));
?>
```

The above example will output:

    float(NAN)
    bool(true)

### See Also

-   <span class="function">is\_finite</span>
-   <span class="function">is\_infinite</span>

lcg\_value
==========

Combined linear congruential generator

### Description

<span class="type">float</span> <span
class="methodname">lcg\_value</span> ( <span
class="methodparam">void</span> )

<span class="function">lcg\_value</span> returns a pseudo random number
in the range of (0, 1). The function combines two CGs with periods of
2^31 - 85 and 2^31 - 249. The period of this function is equal to the
product of both primes.

**Caution**

This function does not generate cryptographically secure values, and
should not be used for cryptographic purposes. If you need a
cryptographically secure value, consider using <span
class="function">random\_int</span>, <span
class="function">random\_bytes</span>, or <span
class="function">openssl\_random\_pseudo\_bytes</span> instead.

### Return Values

A pseudo random float value between 0.0 and 1.0, inclusive.

### See Also

-   <span class="function">rand</span>
-   <span class="function">mt\_rand</span>

log10
=====

Base-10 logarithm

### Description

<span class="type">float</span> <span class="methodname">log10</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the base-10 logarithm of `arg`.

### Parameters

`arg`  
The argument to process

### Return Values

The base-10 logarithm of `arg`

### See Also

-   <span class="function">log</span>

log1p
=====

Returns log(1 + number), computed in a way that is accurate even when
the value of number is close to zero

### Description

<span class="type">float</span> <span class="methodname">log1p</span> (
<span class="methodparam"><span class="type">float</span>
`$number`</span> )

<span class="function">log1p</span> returns log(1 + `number`) computed
in a way that is accurate even when the value of `number` is close to
zero. <span class="function">log</span> might only return log(1) in this
case due to lack of precision.

### Parameters

`number`  
The argument to process

### Return Values

log(1 + `number`)

### Changelog

| Version | Description                                     |
|---------|-------------------------------------------------|
| 5.3.0   | This function is now available on all platforms |

### See Also

-   <span class="function">expm1</span>
-   <span class="function">log</span>
-   <span class="function">log10</span>

log
===

Natural logarithm

### Description

<span class="type">float</span> <span class="methodname">log</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
\[, <span class="methodparam"><span class="type">float</span>
`$base`<span class="initializer"> = M\_E</span></span> \] )

If the optional `base` parameter is specified, <span
class="function">log</span> returns log<sub>base</sub> `arg`, otherwise
<span class="function">log</span> returns the natural logarithm of
`arg`.

### Parameters

`arg`  
The value to calculate the logarithm for

`base`  
The optional logarithmic base to use (defaults to 'e' and so to the
natural logarithm).

### Return Values

The logarithm of `arg` to `base`, if given, or the natural logarithm.

### See Also

-   <span class="function">log10</span>
-   <span class="function">exp</span>
-   <span class="function">pow</span>

max
===

Find highest value

### Description

<span class="type">mixed</span> <span class="methodname">max</span> (
<span class="methodparam"><span class="type">array</span>
`$values`</span> )

<span class="type">mixed</span> <span class="methodname">max</span> (
<span class="methodparam"><span class="type">mixed</span>
`$value1`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \] )

If the first and only parameter is an array, <span
class="function">max</span> returns the highest value in that array. If
at least two parameters are provided, <span class="function">max</span>
returns the biggest of these values.

> **Note**:
>
> Values of different types will be compared using the
> <a href="/language/operators/comparison.html" class="link">standard comparison rules</a>.
> For instance, a non-numeric <span class="type">string</span> will be
> compared to an <span class="type">integer</span> as though it were
> *0*, but multiple non-numeric <span class="type">string</span> values
> will be compared alphanumerically. The actual value returned will be
> of the original type with no conversion applied.

**Caution**

Be careful when passing arguments with mixed types values because <span
class="function">max</span> can produce unpredictable results.

### Parameters

`values`  
An array containing the values.

`value1`  
Any
<a href="/language/operators/comparison.html" class="link">comparable</a>
value.

`...`  
Any
<a href="/language/operators/comparison.html" class="link">comparable</a>
value.

### Return Values

<span class="function">max</span> returns the parameter value considered
"highest" according to standard comparisons. If multiple values of
different types evaluate as equal (e.g. *0* and *'abc'*) the first
provided to the function will be returned.

If an empty array is passed, then **`FALSE`** will be returned and an
**`E_WARNING`** error will be emitted.

### Examples

**Example \#1 Example uses of <span class="function">max</span>**

``` php
<?php
echo max(2, 3, 1, 6, 7);  // 7
echo max(array(2, 4, 5)); // 5

// The string 'hello' when compared to an int is treated as 0
// Since the two values are equal, the order they are provided determines the result
echo max(0, 'hello');     // 0
echo max('hello', 0);     // hello

// Here we are comparing -1 < 0, so 'hello' is the highest value
echo max('hello', -1);    // hello

// With multiple arrays of different lengths, max returns the longest
$val = max(array(2, 2, 2), array(1, 1, 1, 1)); // array(1, 1, 1, 1)

// Multiple arrays of the same length are compared from left to right
// so in our example: 2 == 2, but 5 > 4
$val = max(array(2, 4, 8), array(2, 5, 1)); // array(2, 5, 1)

// If both an array and non-array are given, the array will be returned
// as comparisons treat arrays as greater than any other value
$val = max('string', array(2, 5, 7), 42);   // array(2, 5, 7)

// If one argument is NULL or a boolean, it will be compared against
// other values using the rule FALSE < TRUE regardless of the other types involved
// In the below example, -10 is treated as TRUE in the comparison
$val = max(-10, FALSE); // -10

// 0, on the other hand, is treated as FALSE, so is "lower than" TRUE
$val = max(0, TRUE); // TRUE
?>
```

### See Also

-   <span class="function">min</span>
-   <span class="function">count</span>

min
===

Find lowest value

### Description

<span class="type">mixed</span> <span class="methodname">min</span> (
<span class="methodparam"><span class="type">array</span>
`$values`</span> )

<span class="type">mixed</span> <span class="methodname">min</span> (
<span class="methodparam"><span class="type">mixed</span>
`$value1`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \] )

If the first and only parameter is an array, <span
class="function">min</span> returns the lowest value in that array. If
at least two parameters are provided, <span class="function">min</span>
returns the smallest of these values.

> **Note**:
>
> Values of different types will be compared using the
> <a href="/language/operators/comparison.html" class="link">standard comparison rules</a>.
> For instance, a non-numeric <span class="type">string</span> will be
> compared to an <span class="type">integer</span> as though it were
> *0*, but multiple non-numeric <span class="type">string</span> values
> will be compared alphanumerically. The actual value returned will be
> of the original type with no conversion applied.

**Caution**

Be careful when passing arguments with mixed types values because <span
class="function">min</span> can produce unpredictable results.

### Parameters

`values`  
An array containing the values.

`value1`  
Any
<a href="/language/operators/comparison.html" class="link">comparable</a>
value.

`...`  
Any
<a href="/language/operators/comparison.html" class="link">comparable</a>
value.

### Return Values

<span class="function">min</span> returns the parameter value considered
"lowest" according to standard comparisons. If multiple values of
different types evaluate as equal (e.g. *0* and *'abc'*) the first
provided to the function will be returned.

If an empty array is passed, then **`FALSE`** will be returned and an
**`E_WARNING`** error will be emitted.

### Examples

**Example \#1 Example uses of <span class="function">min</span>**

``` php
<?php
echo min(2, 3, 1, 6, 7);  // 1
echo min(array(2, 4, 5)); // 2

// The string 'hello' when compared to an int is treated as 0
// Since the two values are equal, the order they are provided determines the result
echo min(0, 'hello');     // 0
echo min('hello', 0);     // hello

// Here we are comparing -1 < 0, so -1 is the lowest value
echo min('hello', -1);    // -1

// With multiple arrays of different lengths, min returns the shortest
$val = min(array(2, 2, 2), array(1, 1, 1, 1)); // array(2, 2, 2)

// Multiple arrays of the same length are compared from left to right
// so in our example: 2 == 2, but 4 < 5
$val = min(array(2, 4, 8), array(2, 5, 1)); // array(2, 4, 8)

// If both an array and non-array are given, the array is never returned
// as comparisons treat arrays as greater than any other value
$val = min('string', array(2, 5, 7), 42);   // string

// If one argument is NULL or a boolean, it will be compared against
// other values using the rules FALSE < TRUE and NULL == FALSE regardless of the 
// other types involved
// In the below examples, both -10 and 10 are treated as TRUE in the comparison
$val = min(-10, FALSE, 10); // FALSE
$val = min(-10, NULL, 10);  // NULL

// 0, on the other hand, is treated as FALSE, so is "lower than" TRUE
$val = min(0, TRUE); // 0
?>
```

### See Also

-   <span class="function">max</span>
-   <span class="function">count</span>

mt\_getrandmax
==============

Show largest possible random value

### Description

<span class="type">int</span> <span
class="methodname">mt\_getrandmax</span> ( <span
class="methodparam">void</span> )

Returns the maximum value that can be returned by a call to <span
class="function">mt\_rand</span>.

### Return Values

Returns the maximum random value returned by a call to <span
class="function">mt\_rand</span> without arguments, which is the maximum
value that can be used for its `max` parameter without the result being
scaled up (and therefore less random).

### Examples

**Example \#1 Calculate a random floating-point number**

``` php
<?php
function randomFloat($min = 0, $max = 1) {
    return $min + mt_rand() / mt_getrandmax() * ($max - $min);
}

var_dump(randomFloat());
var_dump(randomFloat(2, 20));
?>
```

The above example will output something similar to:

    float(0.91601131712832)
    float(16.511210331931)

### See Also

-   <span class="function">mt\_rand</span>
-   <span class="function">mt\_srand</span>
-   <span class="function">getrandmax</span>

mt\_rand
========

Generate a random value via the Mersenne Twister Random Number Generator

### Description

<span class="type">int</span> <span class="methodname">mt\_rand</span> (
<span class="methodparam">void</span> )

<span class="type">int</span> <span class="methodname">mt\_rand</span> (
<span class="methodparam"><span class="type">int</span> `$min`</span> ,
<span class="methodparam"><span class="type">int</span> `$max`</span> )

**Caution**

This function does not generate cryptographically secure values, and
should not be used for cryptographic purposes. If you need a
cryptographically secure value, consider using <span
class="function">random\_int</span>, <span
class="function">random\_bytes</span>, or <span
class="function">openssl\_random\_pseudo\_bytes</span> instead.

Many random number generators of older libcs have dubious or unknown
characteristics and are slow. The <span class="function">mt\_rand</span>
function is a drop-in replacement for the older <span
class="function">rand</span>. It uses a random number generator with
known characteristics using the
<a href="http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/emt.html" class="link external">» Mersenne Twister</a>,
which will produce random numbers four times faster than what the
average libc rand() provides.

If called without the optional `min`, `max` arguments <span
class="function">mt\_rand</span> returns a pseudo-random value between 0
and <span class="function">mt\_getrandmax</span>. If you want a random
number between 5 and 15 (inclusive), for example, use *mt\_rand(5, 15)*.

### Parameters

`min`  
Optional lowest value to be returned (default: 0)

`max`  
Optional highest value to be returned (default: <span
class="function">mt\_getrandmax</span>)

### Return Values

A random integer value between `min` (or 0) and `max` (or <span
class="function">mt\_getrandmax</span>, inclusive), or **`FALSE`** if
`max` is less than `min`.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                                                |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="function">mt\_rand</span> <a href="/migration72/incompatible.html#migration72.incompatible.rand-mt_rand-output" class="link">has received a bug fix</a> for a modulo bias bug. This means that sequences generated with a specific seed may differ from PHP 7.1 on 64-bit machines.                                                                           |
| 7.1.0   | <span class="function">rand</span> <a href="/migration71/incompatible.html#migration71.incompatible.rand-srand-aliases" class="link">has been made</a> an alias of <span class="function">mt\_rand</span>.                                                                                                                                                                 |
| 7.1.0   | <span class="function">mt\_rand</span> <a href="/migration71/incompatible.html#migration71.incompatible.fixes-to-mt_rand-algorithm" class="link">has been updated</a> to use the fixed, correct, version of the Mersenne Twister algorithm. To fall back to the old behaviour, use <span class="function">mt\_srand</span> with **`MT_RAND_PHP`** as the second parameter. |
| 5.3.4   | Issues an **`E_WARNING`** and returns **`FALSE`** if `max` \< `min`.                                                                                                                                                                                                                                                                                                       |

### Examples

**Example \#1 <span class="function">mt\_rand</span> example**

``` php
<?php
echo mt_rand() . "\n";
echo mt_rand() . "\n";

echo mt_rand(5, 15);
?>
```

The above example will output something similar to:

    1604716014
    1478613278
    6

### Notes

**Warning**

`min` `max` range must be within the range <span
class="function">mt\_getrandmax</span>. i.e. (`max` - `min`) \<= <span
class="function">mt\_getrandmax</span> Otherwise, <span
class="function">mt\_rand</span> may return poorer random numbers than
it should.

### See Also

-   <span class="function">mt\_srand</span>
-   <span class="function">mt\_getrandmax</span>
-   <span class="function">random\_int</span>
-   <span class="function">random\_bytes</span>
-   <span class="function">openssl\_random\_pseudo\_bytes</span>
-   <span class="function">rand</span>

mt\_srand
=========

Seeds the Mersenne Twister Random Number Generator

### Description

<span class="type">void</span> <span class="methodname">mt\_srand</span>
(\[ <span class="methodparam"><span class="type">int</span>
`$seed`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
MT\_RAND\_MT19937</span></span> \]\] )

Seeds the random number generator with `seed` or with a random value if
no `seed` is given.

> **Note**: <span class="simpara">There is no need to seed the random
> number generator with <span class="function">srand</span> or <span
> class="function">mt\_srand</span> as this is done automatically.
> </span>

### Parameters

`seed`  
An arbitrary <span class="type">integer</span> seed value.

`mode`  
Use one of the following constants to specify the implementation of the
algorithm to use.

| Constant              | Description                                                                                                                                           |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`MT_RAND_MT19937`** | Uses the fixed, correct, Mersenne Twister implementation, available as of PHP 7.1.0.                                                                  |
| **`MT_RAND_PHP`**     | Uses an incorrect Mersenne Twister implementation which was used as the default up till PHP 7.1.0. This mode is available for backward compatibility. |

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                                                |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | <span class="function">srand</span> <a href="/migration71/incompatible.html#migration71.incompatible.rand-srand-aliases" class="link">has been made</a> an alias of <span class="function">mt\_srand</span>.                                                                                                                                                               |
| 7.1.0   | <span class="function">mt\_rand</span> <a href="/migration71/incompatible.html#migration71.incompatible.fixes-to-mt_rand-algorithm" class="link">has been updated</a> to use the fixed, correct, version of the Mersenne Twister algorithm. To fall back to the old behaviour, use <span class="function">mt\_srand</span> with **`MT_RAND_PHP`** as the second parameter. |
| 5.2.1   | The Mersenne Twister implementation in PHP now uses a new seeding algorithm by Richard Wagner. Identical seeds no longer produce the same sequence of values they did in previous versions. This behavior is not expected to change again, but it is considered unsafe to rely upon it nonetheless.                                                                        |

### Examples

**Example \#1 <span class="function">mt\_srand</span> example**

``` php
<?php
// seed with microseconds
function make_seed()
{
  list($usec, $sec) = explode(' ', microtime());
  return $sec + $usec * 1000000;
}
mt_srand(make_seed());
$randval = mt_rand();
?>
```

### See Also

-   <span class="function">mt\_rand</span>
-   <span class="function">mt\_getrandmax</span>
-   <span class="function">srand</span>

octdec
======

Octal to decimal

### Description

<span class="type">number</span> <span class="methodname">octdec</span>
( <span class="methodparam"><span class="type">string</span>
`$octal_string`</span> )

Returns the decimal equivalent of the octal number represented by the
`octal_string` argument.

### Parameters

`octal_string`  
The octal string to convert. Any invalid characters in `octal_string`
are silently ignored. As of PHP 7.4.0 supplying any invalid characters
is deprecated.

### Return Values

The decimal representation of `octal_string`

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | Passing invalid characters will now generate a deprecation notice. The result will still be computed as if the invalid characters did not exist. |

### Examples

**Example \#1 <span class="function">octdec</span> example**

``` php
<?php
echo octdec('77') . "\n";
echo octdec(decoct(45));
?>
```

The above example will output:

    63
    45

### Notes

> **Note**:
>
> The function can convert numbers that are too large to fit into the
> platforms <span class="type">integer</span> type, larger values are
> returned as <span class="type">float</span> in that case.

### See Also

-   <span class="function">decoct</span>
-   <span class="function">bindec</span>
-   <span class="function">hexdec</span>
-   <span class="function">base\_convert</span>

pi
==

Get value of pi

### Description

<span class="type">float</span> <span class="methodname">pi</span> (
<span class="methodparam">void</span> )

Returns an approximation of pi. Also, you can use the **`M_PI`**
constant which yields identical results to <span
class="function">pi</span>.

### Return Values

The value of pi as float.

### Examples

**Example \#1 <span class="function">pi</span> example**

``` php
<?php
echo pi(); // 3.1415926535898
echo M_PI; // 3.1415926535898
?>
```

pow
===

Exponential expression

### Description

<span class="type">number</span> <span class="methodname">pow</span> (
<span class="methodparam"><span class="type">number</span>
`$base`</span> , <span class="methodparam"><span
class="type">number</span> `$exp`</span> )

Returns `base` raised to the power of `exp`.

> **Note**:
>
> In PHP 5.6 onwards, you may prefer to use the
> <a href="/language/operators/arithmetic.html" class="link">**</a>
> operator.

### Parameters

`base`  
The base to use

`exp`  
The exponent

### Return Values

`base` raised to the power of `exp`. If both arguments are non-negative
integers and the result can be represented as an integer, the result
will be returned with <span class="type">integer</span> type, otherwise
it will be returned as a <span class="type">float</span>.

### Examples

**Example \#1 Some examples of <span class="function">pow</span>**

``` php
<?php

var_dump(pow(2, 8)); // int(256)
echo pow(-1, 20); // 1
echo pow(0, 0); // 1
echo pow(10, -1); // 0.1

echo pow(-1, 5.5); // PHP >=5.2.2: NAN
echo pow(-1, 5.5); // PHP <5.2.2: -NAN
?>
```

### Notes

> **Note**:
>
> This function will convert all input to a number, even non-scalar
> values, which could lead to *weird* results.

### See Also

-   <span class="function">exp</span>
-   <span class="function">sqrt</span>
-   <span class="function">bcpow</span>
-   <span class="function">gmp\_pow</span>

rad2deg
=======

Converts the radian number to the equivalent number in degrees

### Description

<span class="type">float</span> <span class="methodname">rad2deg</span>
( <span class="methodparam"><span class="type">float</span>
`$number`</span> )

This function converts `number` from radian to degrees.

### Parameters

`number`  
A radian value

### Return Values

The equivalent of `number` in degrees

### Examples

**Example \#1 <span class="function">rad2deg</span> example**

``` php
<?php

echo rad2deg(M_PI_4); // 45

?>
```

### See Also

-   <span class="function">deg2rad</span>

rand
====

Generate a random integer

### Description

<span class="type">int</span> <span class="methodname">rand</span> (
<span class="methodparam">void</span> )

<span class="type">int</span> <span class="methodname">rand</span> (
<span class="methodparam"><span class="type">int</span> `$min`</span> ,
<span class="methodparam"><span class="type">int</span> `$max`</span> )

If called without the optional `min`, `max` arguments <span
class="function">rand</span> returns a pseudo-random integer between 0
and <span class="function">getrandmax</span>. If you want a random
number between 5 and 15 (inclusive), for example, use *rand(5, 15)*.

**Caution**

This function does not generate cryptographically secure values, and
should not be used for cryptographic purposes. If you need a
cryptographically secure value, consider using <span
class="function">random\_int</span>, <span
class="function">random\_bytes</span>, or <span
class="function">openssl\_random\_pseudo\_bytes</span> instead.

> **Note**: <span class="simpara"> On some platforms (such as Windows),
> <span class="function">getrandmax</span> is only 32767. If you require
> a range larger than 32767, specifying `min` and `max` will allow you
> to create a range larger than this, or consider using <span
> class="function">mt\_rand</span> instead. </span>

> **Note**: <span class="simpara">As of PHP 7.1.0, <span
> class="function">rand</span> uses the same random number generator as
> <span class="function">mt\_rand</span>. To preserve backwards
> compatibility <span class="function">rand</span> allows `max` to be
> smaller than `min` as opposed to returning **`FALSE`** as <span
> class="function">mt\_rand</span>.</span>

### Parameters

`min`  
The lowest value to return (default: 0)

`max`  
The highest value to return (default: <span
class="function">getrandmax</span>)

### Return Values

A pseudo random value between `min` (or 0) and `max` (or <span
class="function">getrandmax</span>, inclusive).

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                  |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="function">rand</span> <a href="/migration72/incompatible.html#migration72.incompatible.rand-mt_rand-output" class="link">has received a bug fix</a> for a modulo bias bug. This means that sequences generated with a specific seed may differ from PHP 7.1 on 64-bit machines. |
| 7.1.0   | <span class="function">rand</span> <a href="/migration71/incompatible.html#migration71.incompatible.rand-srand-aliases" class="link">has been made</a> an alias of <span class="function">mt\_rand</span>.                                                                                   |

### Examples

**Example \#1 <span class="function">rand</span> example**

``` php
<?php
echo rand() . "\n";
echo rand() . "\n";

echo rand(5, 15);
?>
```

The above example will output something similar to:

    7771
    22264
    11

### Notes

**Warning**

`min` `max` range must be within the range <span
class="function">getrandmax</span>. i.e. (`max` - `min`) \<= <span
class="function">getrandmax</span> Otherwise, <span
class="function">rand</span> may return poor-quality random numbers.

### See Also

-   <span class="function">srand</span>
-   <span class="function">getrandmax</span>
-   <span class="function">mt\_rand</span>
-   <span class="function">random\_int</span>
-   <span class="function">random\_bytes</span>
-   <span class="function">openssl\_random\_pseudo\_bytes</span>

round
=====

Rounds a float

### Description

<span class="type">float</span> <span class="methodname">round</span> (
<span class="methodparam"><span class="type">float</span> `$val`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$precision`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = PHP\_ROUND\_HALF\_UP</span></span> \]\] )

Returns the rounded value of `val` to specified `precision` (number of
digits after the decimal point). `precision` can also be negative or
zero (default).

> **Note**: <span class="simpara"> PHP doesn't handle strings like
> *"12,300.2"* correctly by default. See
> <a href="/language/types/string.html#language.types.string.conversion" class="link">converting from strings</a>.
> </span>

### Parameters

`val`  
The value to round.

`precision`  
The optional number of decimal digits to round to.

If the `precision` is positive, `val` is rounded to `precision`
significant digits after the decimal point.

If the `precision` is negative, `val` is rounded to `precision`
significant digits before the decimal point, i.e. to the nearest
multiple of *pow(10, -precision)*, e.g. for a `precision` of -1 `val` is
rounded to tens, for a `precision` of -2 to hundreds, etc.

`mode`  
Use one of the following constants to specify the mode in which rounding
occurs.

| Constants                 | Description                                                                                                 |
|---------------------------|-------------------------------------------------------------------------------------------------------------|
| **`PHP_ROUND_HALF_UP`**   | Rounds `val` away from zero when it is half way there, making 1.5 into 2 and -1.5 into -2.                  |
| **`PHP_ROUND_HALF_DOWN`** | Rounds `val` towards zero when it is half way there, making 1.5 into 1 and -1.5 into -1.                    |
| **`PHP_ROUND_HALF_EVEN`** | Rounds `val` towards the nearest even value when it is half way there, making both 1.5 and 2.5 into 2.      |
| **`PHP_ROUND_HALF_ODD`**  | Rounds `val` towards the nearest odd value when it is half way there, making 1.5 into 1 and and 2.5 into 3. |

### Return Values

The value rounded to the given `precision` as a <span
class="type">float</span>.

### Examples

**Example \#1 <span class="function">round</span> examples**

``` php
<?php
var_dump(round(3.4));
var_dump(round(3.5));
var_dump(round(3.6));
var_dump(round(3.6, 0));
var_dump(round(5.045, 2));
var_dump(round(5.055, 2));
var_dump(round(345, -2));
var_dump(round(345, -3));
var_dump(round(678, -2));
var_dump(round(678, -3));
?>
```

The above example will output:

    float(3)
    float(4)
    float(4)
    float(4)
    float(5.05)
    float(5.06)
    float(300)
    float(0)
    float(700)
    float(1000)

**Example \#2 How `precision` affects a float**

``` php
<?php
$number = 135.79;

var_dump(round($number, 3));
var_dump(round($number, 2));
var_dump(round($number, 1));
var_dump(round($number, 0));
var_dump(round($number, -1));
var_dump(round($number, -2));
var_dump(round($number, -3));
?>
```

The above example will output:

    float(135.79)
    float(135.79)
    float(135.8)
    float(136)
    float(140)
    float(100)
    float(0)

**Example \#3 `mode` examples**

``` php
<?php
echo 'Rounding modes with 9.5' . PHP_EOL;
var_dump(round(9.5, 0, PHP_ROUND_HALF_UP));
var_dump(round(9.5, 0, PHP_ROUND_HALF_DOWN));
var_dump(round(9.5, 0, PHP_ROUND_HALF_EVEN));
var_dump(round(9.5, 0, PHP_ROUND_HALF_ODD));

echo PHP_EOL;
echo 'Rounding modes with 8.5' . PHP_EOL;
var_dump(round(8.5, 0, PHP_ROUND_HALF_UP));
var_dump(round(8.5, 0, PHP_ROUND_HALF_DOWN));
var_dump(round(8.5, 0, PHP_ROUND_HALF_EVEN));
var_dump(round(8.5, 0, PHP_ROUND_HALF_ODD));
?>
```

The above example will output:

    Rounding modes with 9.5
    float(10)
    float(9)
    float(10)
    float(9)

    Rounding modes with 8.5
    float(9)
    float(8)
    float(8)
    float(9)

**Example \#4 `mode` with `precision` examples**

``` php
<?php
echo 'Using PHP_ROUND_HALF_UP with 1 decimal digit precision' . PHP_EOL;
var_dump(round( 1.55, 1, PHP_ROUND_HALF_UP));
var_dump(round(-1.55, 1, PHP_ROUND_HALF_UP));

echo PHP_EOL;
echo 'Using PHP_ROUND_HALF_DOWN with 1 decimal digit precision' . PHP_EOL;
var_dump(round( 1.55, 1, PHP_ROUND_HALF_DOWN));
var_dump(round(-1.55, 1, PHP_ROUND_HALF_DOWN));

echo PHP_EOL;
echo 'Using PHP_ROUND_HALF_EVEN with 1 decimal digit precision' . PHP_EOL;
var_dump(round( 1.55, 1, PHP_ROUND_HALF_EVEN));
var_dump(round(-1.55, 1, PHP_ROUND_HALF_EVEN));

echo PHP_EOL;
echo 'Using PHP_ROUND_HALF_ODD with 1 decimal digit precision' . PHP_EOL;
var_dump(round( 1.55, 1, PHP_ROUND_HALF_ODD));
var_dump(round(-1.55, 1, PHP_ROUND_HALF_ODD));
?>
```

The above example will output:

    Using PHP_ROUND_HALF_UP with 1 decimal digit precision
    float(1.6)
    float(-1.6)

    Using PHP_ROUND_HALF_DOWN with 1 decimal digit precision
    float(1.5)
    float(-1.5)

    Using PHP_ROUND_HALF_EVEN with 1 decimal digit precision
    float(1.6)
    float(-1.6)

    Using PHP_ROUND_HALF_ODD with 1 decimal digit precision
    float(1.5)
    float(-1.5)

### Changelog

| Version | Description                                                                                           |
|---------|-------------------------------------------------------------------------------------------------------|
| 5.3.0   | The `mode` parameter was introduced.                                                                  |
| 5.2.7   | The inner workings of <span class="function">round</span> was changed to conform to the C99 standard. |

### See Also

-   <span class="function">ceil</span>
-   <span class="function">floor</span>
-   <span class="function">number\_format</span>

sin
===

Sine

### Description

<span class="type">float</span> <span class="methodname">sin</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

<span class="function">sin</span> returns the sine of the `arg`
parameter. The `arg` parameter is in radians.

### Parameters

`arg`  
A value in radians

### Return Values

The sine of `arg`

### Examples

**Example \#1 <span class="function">sin</span> example**

``` php
<?php

// Precision depends on your precision directive
echo sin(deg2rad(60));  //  0.866025403 ...
echo sin(60);           // -0.304810621 ...

?>
```

### See Also

-   <span class="function">asin</span>
-   <span class="function">sinh</span>
-   <span class="function">cos</span>
-   <span class="function">tan</span>
-   <span class="function">deg2rad</span>

sinh
====

Hyperbolic sine

### Description

<span class="type">float</span> <span class="methodname">sinh</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the hyperbolic sine of `arg`, defined as *(exp(arg) -
exp(-arg))/2*.

### Parameters

`arg`  
The argument to process

### Return Values

The hyperbolic sine of `arg`

### See Also

-   <span class="function">sin</span>
-   <span class="function">asinh</span>
-   <span class="function">cosh</span>
-   <span class="function">tanh</span>

sqrt
====

Square root

### Description

<span class="type">float</span> <span class="methodname">sqrt</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the square root of `arg`.

### Parameters

`arg`  
The argument to process

### Return Values

The square root of `arg` or the special value *NAN* for negative
numbers.

### Examples

**Example \#1 <span class="function">sqrt</span> example**

``` php
<?php
// Precision depends on your precision directive
echo sqrt(9); // 3
echo sqrt(10); // 3.16227766 ...
?>
```

### See Also

-   <span class="function">pow</span>

srand
=====

Seed the random number generator

### Description

<span class="type">void</span> <span class="methodname">srand</span> (\[
<span class="methodparam"><span class="type">int</span> `$seed`</span>
\] )

Seeds the random number generator with `seed` or with a random value if
no `seed` is given.

> **Note**: <span class="simpara">There is no need to seed the random
> number generator with <span class="function">srand</span> or <span
> class="function">mt\_srand</span> as this is done automatically.
> </span>

> **Note**: <span class="simpara">As of PHP 7.1.0, <span
> class="function">srand</span> has been made an alias of <span
> class="function">mt\_srand</span>.</span>

### Parameters

`seed`  
An arbitrary <span class="type">integer</span> seed value.

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                                                                                                                                  |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | <span class="function">srand</span> <a href="/migration71/incompatible.html#migration71.incompatible.rand-srand-aliases" class="link">has been made</a> an alias of <span class="function">mt\_srand</span>. |

### Examples

**Example \#1 <span class="function">srand</span> example**

``` php
<?php
// seed with microseconds
function make_seed()
{
  list($usec, $sec) = explode(' ', microtime());
  return $sec + $usec * 1000000;
}
srand(make_seed());
$randval = rand();
?>
```

### See Also

-   <span class="function">rand</span>
-   <span class="function">getrandmax</span>
-   <span class="function">mt\_srand</span>

tan
===

Tangent

### Description

<span class="type">float</span> <span class="methodname">tan</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

<span class="function">tan</span> returns the tangent of the `arg`
parameter. The `arg` parameter is in radians.

### Parameters

`arg`  
The argument to process in radians

### Return Values

The tangent of `arg`

### Examples

**Example \#1 <span class="function">tan</span> example**

``` php
<?php

echo tan(M_PI_4); // 1

?>
```

### See Also

-   <span class="function">atan</span>
-   <span class="function">atan2</span>
-   <span class="function">sin</span>
-   <span class="function">cos</span>
-   <span class="function">tanh</span>
-   <span class="function">deg2rad</span>

tanh
====

Hyperbolic tangent

### Description

<span class="type">float</span> <span class="methodname">tanh</span> (
<span class="methodparam"><span class="type">float</span> `$arg`</span>
)

Returns the hyperbolic tangent of `arg`, defined as
*sinh(arg)/cosh(arg)*.

### Parameters

`arg`  
The argument to process

### Return Values

The hyperbolic tangent of `arg`

### See Also

-   <span class="function">tan</span>
-   <span class="function">atanh</span>
-   <span class="function">sinh</span>
-   <span class="function">cosh</span>

**Table of Contents**

-   [abs](/ref/math.html#abs) — Absolute value
-   [acos](/ref/math.html#acos) — Arc cosine
-   [acosh](/ref/math.html#acosh) — Inverse hyperbolic cosine
-   [asin](/ref/math.html#asin) — Arc sine
-   [asinh](/ref/math.html#asinh) — Inverse hyperbolic sine
-   [atan2](/ref/math.html#atan2) — Arc tangent of two variables
-   [atan](/ref/math.html#atan) — Arc tangent
-   [atanh](/ref/math.html#atanh) — Inverse hyperbolic tangent
-   [base\_convert](/ref/math.html#base_convert) — Convert a number
    between arbitrary bases
-   [bindec](/ref/math.html#bindec) — Binary to decimal
-   [ceil](/ref/math.html#ceil) — Round fractions up
-   [cos](/ref/math.html#cos) — Cosine
-   [cosh](/ref/math.html#cosh) — Hyperbolic cosine
-   [decbin](/ref/math.html#decbin) — Decimal to binary
-   [dechex](/ref/math.html#dechex) — Decimal to hexadecimal
-   [decoct](/ref/math.html#decoct) — Decimal to octal
-   [deg2rad](/ref/math.html#deg2rad) — Converts the number in degrees
    to the radian equivalent
-   [exp](/ref/math.html#exp) — Calculates the exponent of e
-   [expm1](/ref/math.html#expm1) — Returns exp(number) - 1, computed in
    a way that is accurate even when the value of number is close to
    zero
-   [floor](/ref/math.html#floor) — Round fractions down
-   [fmod](/ref/math.html#fmod) — Returns the floating point remainder
    (modulo) of the division of the arguments
-   [getrandmax](/ref/math.html#getrandmax) — Show largest possible
    random value
-   [hexdec](/ref/math.html#hexdec) — Hexadecimal to decimal
-   [hypot](/ref/math.html#hypot) — Calculate the length of the
    hypotenuse of a right-angle triangle
-   [intdiv](/ref/math.html#intdiv) — Integer division
-   [is\_finite](/ref/math.html#is_finite) — Finds whether a value is a
    legal finite number
-   [is\_infinite](/ref/math.html#is_infinite) — Finds whether a value
    is infinite
-   [is\_nan](/ref/math.html#is_nan) — Finds whether a value is not a
    number
-   [lcg\_value](/ref/math.html#lcg_value) — Combined linear
    congruential generator
-   [log10](/ref/math.html#log10) — Base-10 logarithm
-   [log1p](/ref/math.html#log1p) — Returns log(1 + number), computed in
    a way that is accurate even when the value of number is close to
    zero
-   [log](/ref/math.html#log) — Natural logarithm
-   [max](/ref/math.html#max) — Find highest value
-   [min](/ref/math.html#min) — Find lowest value
-   [mt\_getrandmax](/ref/math.html#mt_getrandmax) — Show largest
    possible random value
-   [mt\_rand](/ref/math.html#mt_rand) — Generate a random value via the
    Mersenne Twister Random Number Generator
-   [mt\_srand](/ref/math.html#mt_srand) — Seeds the Mersenne Twister
    Random Number Generator
-   [octdec](/ref/math.html#octdec) — Octal to decimal
-   [pi](/ref/math.html#pi) — Get value of pi
-   [pow](/ref/math.html#pow) — Exponential expression
-   [rad2deg](/ref/math.html#rad2deg) — Converts the radian number to
    the equivalent number in degrees
-   [rand](/ref/math.html#rand) — Generate a random integer
-   [round](/ref/math.html#round) — Rounds a float
-   [sin](/ref/math.html#sin) — Sine
-   [sinh](/ref/math.html#sinh) — Hyperbolic sine
-   [sqrt](/ref/math.html#sqrt) — Square root
-   [srand](/ref/math.html#srand) — Seed the random number generator
-   [tan](/ref/math.html#tan) — Tangent
-   [tanh](/ref/math.html#tanh) — Hyperbolic tangent

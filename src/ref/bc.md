bcadd
=====

Add two arbitrary precision numbers

### Description

<span class="type">string</span> <span class="methodname">bcadd</span> (
<span class="methodparam"><span class="type">string</span>
`$left_operand`</span> , <span class="methodparam"><span
class="type">string</span> `$right_operand`</span> \[, <span
class="methodparam"><span class="type">int</span> `$scale`<span
class="initializer"> = 0</span></span> \] )

Sums `left_operand` and `right_operand`.

### Parameters

`left_operand`  
The left operand, as a string.

`right_operand`  
The right operand, as a string.

` scale`  
This optional parameter is used to set the number of digits after the
decimal place in the result. If omitted, it will default to the scale
set globally with the <span class="function">bcscale</span> function, or
fallback to *0* if this has not been set.

### Return Values

The sum of the two operands, as a string.

### Examples

**Example \#1 <span class="function">bcadd</span> example**

``` php
<?php

$a = '1.234';
$b = '5';

echo bcadd($a, $b);     // 6
echo bcadd($a, $b, 4);  // 6.2340

?>
```

### See Also

-   <span class="function">bcsub</span>

bccomp
======

Compare two arbitrary precision numbers

### Description

<span class="type">int</span> <span class="methodname">bccomp</span> (
<span class="methodparam"><span class="type">string</span>
`$left_operand`</span> , <span class="methodparam"><span
class="type">string</span> `$right_operand`</span> \[, <span
class="methodparam"><span class="type">int</span> `$scale`<span
class="initializer"> = 0</span></span> \] )

Compares the `left_operand` to the `right_operand` and returns the
result as an integer.

### Parameters

`left_operand`  
The left operand, as a string.

`right_operand`  
The right operand, as a string.

`scale`  
The optional `scale` parameter is used to set the number of digits after
the decimal place which will be used in the comparison.

### Return Values

Returns 0 if the two operands are equal, 1 if the `left_operand` is
larger than the `right_operand`, -1 otherwise.

### Examples

**Example \#1 <span class="function">bccomp</span> example**

``` php
<?php

echo bccomp('1', '2') . "\n";   // -1
echo bccomp('1.00001', '1', 3); // 0
echo bccomp('1.00001', '1', 5); // 1

?>
```

bcdiv
=====

Divide two arbitrary precision numbers

### Description

<span class="type">string</span> <span class="methodname">bcdiv</span> (
<span class="methodparam"><span class="type">string</span>
`$dividend`</span> , <span class="methodparam"><span
class="type">string</span> `$divisor`</span> \[, <span
class="methodparam"><span class="type">int</span> `$scale`<span
class="initializer"> = 0</span></span> \] )

Divides the `dividend` by the `divisor`.

### Parameters

`dividend`  
The dividend, as a string.

`divisor`  
The divisor, as a string.

` scale`  
This optional parameter is used to set the number of digits after the
decimal place in the result. If omitted, it will default to the scale
set globally with the <span class="function">bcscale</span> function, or
fallback to *0* if this has not been set.

### Return Values

Returns the result of the division as a string, or **`NULL`** if
`divisor` is *0*.

### Examples

**Example \#1 <span class="function">bcdiv</span> example**

``` php
<?php

echo bcdiv('105', '6.55957', 3);  // 16.007

?>
```

### See Also

-   <span class="function">bcmul</span>

bcmod
=====

Get modulus of an arbitrary precision number

### Description

<span class="type">string</span> <span class="methodname">bcmod</span> (
<span class="methodparam"><span class="type">string</span>
`$dividend`</span> , <span class="methodparam"><span
class="type">string</span> `$divisor`</span> \[, <span
class="methodparam"><span class="type">int</span> `$scale`<span
class="initializer"> = 0</span></span> \] )

Get the remainder of dividing `dividend` by `divisor`. Unless `divisor`
is zero, the result has the same sign as `dividend`.

### Parameters

`dividend`  
The dividend, as a string.

`divisor`  
The divisor, as a string.

### Return Values

Returns the modulus as a string, or **`NULL`** if `divisor` is *0*.

### Changelog

| Version | Description                                                                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | `dividend` and `divisor` are no longer truncated to integer, so now the behavior of <span class="function">bcmod</span> follows <span class="function">fmod</span> rather than the *%* operator. |
| 7.2.0   | The `scale` parameter was added.                                                                                                                                                                 |

### Examples

**Example \#1 <span class="function">bcmod</span> example**

``` php
<?php
bcscale(0);
echo bcmod( '5',  '3'); //  2
echo bcmod( '5', '-3'); //  2
echo bcmod('-5',  '3'); // -2
echo bcmod('-5', '-3'); // -2
?>
```

**Example \#2 <span class="function">bcmod</span> with decimals**

``` php
<?php
bcscale(1);
echo bcmod('5.7', '1.3'); // 0.5 as of PHP 7.2.0; 0 previously
?>
```

### See Also

-   <span class="function">bcdiv</span>

bcmul
=====

Multiply two arbitrary precision numbers

### Description

<span class="type">string</span> <span class="methodname">bcmul</span> (
<span class="methodparam"><span class="type">string</span>
`$left_operand`</span> , <span class="methodparam"><span
class="type">string</span> `$right_operand`</span> \[, <span
class="methodparam"><span class="type">int</span> `$scale`<span
class="initializer"> = 0</span></span> \] )

Multiply the `left_operand` by the `right_operand`.

### Parameters

`left_operand`  
The left operand, as a string.

`right_operand`  
The right operand, as a string.

` scale`  
This optional parameter is used to set the number of digits after the
decimal place in the result. If omitted, it will default to the scale
set globally with the <span class="function">bcscale</span> function, or
fallback to *0* if this has not been set.

### Return Values

Returns the result as a string.

### Changelog

| Version | Description                                                                                                                                                |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | <span class="function">bcmul</span> now returns numbers with the requested scale. Formerly, the returned numbers may have omitted trailing decimal zeroes. |

### Examples

**Example \#1 <span class="function">bcmul</span> example**

``` php
<?php
echo bcmul('1.34747474747', '35', 3); // 47.161
echo bcmul('2', '4'); // 8
?>
```

### Notes

> **Note**:
>
> Before PHP 7.3.0 <span class="function">bcmul</span> may return a
> result with fewer digits after the decimal point than the `scale`
> parameter would indicate. This only occurs when the result doesn't
> require all of the precision allowed by the `scale`. For example:
>
> **Example \#2 <span class="function">bcmul</span> scale example**
>
> ``` php
> <?php
> echo bcmul('5', '2', 2);     // prints "10", not "10.00"
> ?>
> ```

### See Also

-   <span class="function">bcdiv</span>

bcpow
=====

Raise an arbitrary precision number to another

### Description

<span class="type">string</span> <span class="methodname">bcpow</span> (
<span class="methodparam"><span class="type">string</span>
`$base`</span> , <span class="methodparam"><span
class="type">string</span> `$exponent`</span> \[, <span
class="methodparam"><span class="type">int</span> `$scale`<span
class="initializer"> = 0</span></span> \] )

Raise `base` to the power `exponent`.

### Parameters

`base`  
The base, as a string.

`exponent`  
The exponent, as a string. If the exponent is non-integral, it is
truncated. The valid range of the exponent is platform specific, but is
at least *-2147483648* to *2147483647*.

` scale`  
This optional parameter is used to set the number of digits after the
decimal place in the result. If omitted, it will default to the scale
set globally with the <span class="function">bcscale</span> function, or
fallback to *0* if this has not been set.

### Return Values

Returns the result as a string.

### Changelog

| Version | Description                                                                                                                                                |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | <span class="function">bcpow</span> now returns numbers with the requested scale. Formerly, the returned numbers may have omitted trailing decimal zeroes. |

### Examples

**Example \#1 <span class="function">bcpow</span> example**

``` php
<?php

echo bcpow('4.2', '3', 2); // 74.08

?>
```

### Notes

> **Note**:
>
> Before PHP 7.3.0 <span class="function">bcpow</span> may return a
> result with fewer digits after the decimal point than the `scale`
> parameter would indicate. This only occurs when the result doesn't
> require all of the precision allowed by the `scale`. For example:
>
> **Example \#2 <span class="function">bcpow</span> scale example**
>
> ``` php
> <?php
> echo bcpow('5', '2', 2);     // prints "25", not "25.00"
> ?>
> ```

### See Also

-   <span class="function">bcpowmod</span>
-   <span class="function">bcsqrt</span>

bcpowmod
========

Raise an arbitrary precision number to another, reduced by a specified
modulus

### Description

<span class="type">string</span> <span
class="methodname">bcpowmod</span> ( <span class="methodparam"><span
class="type">string</span> `$base`</span> , <span
class="methodparam"><span class="type">string</span> `$exponent`</span>
, <span class="methodparam"><span class="type">string</span>
`$modulus`</span> \[, <span class="methodparam"><span
class="type">int</span> `$scale`<span class="initializer"> =
0</span></span> \] )

Use the fast-exponentiation method to raise `base` to the power
`exponent` with respect to the modulus `modulus`.

### Parameters

`base`  
The base, as an integral string (i.e. the scale has to be zero).

`exponent`  
The exponent, as an non-negative, integral string (i.e. the scale has to
be zero).

`modulus`  
The modulus, as an integral string (i.e. the scale has to be zero).

` scale`  
This optional parameter is used to set the number of digits after the
decimal place in the result. If omitted, it will default to the scale
set globally with the <span class="function">bcscale</span> function, or
fallback to *0* if this has not been set.

### Return Values

Returns the result as a string, or **`FALSE`** if `modulus` is *0* or
`exponent` is negative.

### Notes

> **Note**:
>
> Because this method uses the modulus operation, numbers which are not
> positive integers may give unexpected results.

### Examples

The following two statements are functionally identical. The <span
class="function">bcpowmod</span> version however, executes in less time
and can accept larger parameters.

``` php
<?php
$a = bcpowmod($x, $y, $mod);

$b = bcmod(bcpow($x, $y), $mod);

// $a and $b are equal to each other.

?>
```

### See Also

-   <span class="function">bcpow</span>
-   <span class="function">bcmod</span>

bcscale
=======

Set or get default scale parameter for all bc math functions

### Description

<span class="type">int</span> <span class="methodname">bcscale</span> (
<span class="methodparam"><span class="type">int</span> `$scale`</span>
)

Sets the default scale parameter for all subsequent calls to bc math
functions that do not explicitly specify a scale parameter.

<span class="type">int</span> <span class="methodname">bcscale</span> (
<span class="methodparam">void</span> )

Gets the current scale factor.

### Parameters

`scale`  
The scale factor.

### Return Values

Returns the old scale when used as setter. Otherwise the current scale
is returned.

### Changelog

| Version | Description                                                                                                                                                                                                                                            |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | <span class="function">bcscale</span> can now be used to get the current scale factor; when used as setter, it now returns the old scale value. Formerly, `scale` was mandatory, and <span class="function">bcscale</span> always returned **`TRUE`**. |

### Examples

**Example \#1 <span class="function">bcscale</span> example**

``` php
<?php

// default scale : 3
bcscale(3);
echo bcdiv('105', '6.55957'); // 16.007

// this is the same without bcscale()
echo bcdiv('105', '6.55957', 3); // 16.007

?>
```

bcsqrt
======

Get the square root of an arbitrary precision number

### Description

<span class="type">string</span> <span class="methodname">bcsqrt</span>
( <span class="methodparam"><span class="type">string</span>
`$operand`</span> \[, <span class="methodparam"><span
class="type">int</span> `$scale`<span class="initializer"> =
0</span></span> \] )

Return the square root of the `operand`.

### Parameters

`operand`  
The operand, as a string.

` scale`  
This optional parameter is used to set the number of digits after the
decimal place in the result. If omitted, it will default to the scale
set globally with the <span class="function">bcscale</span> function, or
fallback to *0* if this has not been set.

### Return Values

Returns the square root as a string, or **`NULL`** if `operand` is
negative.

### Examples

**Example \#1 <span class="function">bcsqrt</span> example**

``` php
<?php

echo bcsqrt('2', 3); // 1.414

?>
```

### See Also

-   <span class="function">bcpow</span>

bcsub
=====

Subtract one arbitrary precision number from another

### Description

<span class="type">string</span> <span class="methodname">bcsub</span> (
<span class="methodparam"><span class="type">string</span>
`$left_operand`</span> , <span class="methodparam"><span
class="type">string</span> `$right_operand`</span> \[, <span
class="methodparam"><span class="type">int</span> `$scale`<span
class="initializer"> = 0</span></span> \] )

Subtracts the `right_operand` from the `left_operand`.

### Parameters

`left_operand`  
The left operand, as a string.

`right_operand`  
The right operand, as a string.

` scale`  
This optional parameter is used to set the number of digits after the
decimal place in the result. If omitted, it will default to the scale
set globally with the <span class="function">bcscale</span> function, or
fallback to *0* if this has not been set.

### Return Values

The result of the subtraction, as a string.

### Examples

**Example \#1 <span class="function">bcsub</span> example**

``` php
<?php

$a = '1.234';
$b = '5';

echo bcsub($a, $b);     // -3
echo bcsub($a, $b, 4);  // -3.7660

?>
```

### See Also

-   <span class="function">bcadd</span>

**Table of Contents**

-   [bcadd](/ref/bc.html#bcadd) — Add two arbitrary precision numbers
-   [bccomp](/ref/bc.html#bccomp) — Compare two arbitrary precision
    numbers
-   [bcdiv](/ref/bc.html#bcdiv) — Divide two arbitrary precision numbers
-   [bcmod](/ref/bc.html#bcmod) — Get modulus of an arbitrary precision
    number
-   [bcmul](/ref/bc.html#bcmul) — Multiply two arbitrary precision
    numbers
-   [bcpow](/ref/bc.html#bcpow) — Raise an arbitrary precision number to
    another
-   [bcpowmod](/ref/bc.html#bcpowmod) — Raise an arbitrary precision
    number to another, reduced by a specified modulus
-   [bcscale](/ref/bc.html#bcscale) — Set or get default scale parameter
    for all bc math functions
-   [bcsqrt](/ref/bc.html#bcsqrt) — Get the square root of an arbitrary
    precision number
-   [bcsub](/ref/bc.html#bcsub) — Subtract one arbitrary precision
    number from another

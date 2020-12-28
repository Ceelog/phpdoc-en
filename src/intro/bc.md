For arbitrary precision mathematics PHP offers BCMath which supports
numbers of any size and precision up to *2147483647* (or *0x7FFFFFFF*)
decimal digits, if there is sufficient memory, represented as strings.

Valid (aka. well-formed) BCMath numbers are strings which match the
regular expression */^\[+-\]?\[0\]\*\[1-9\]\*\[.\]?\[0-9\]\*$/*.

**Caution**

Passing values of type <span class="type">float</span> to a BCMath
function which expects a <span class="type">string</span> as operand may
not have the desired effect due to the way PHP converts <span
class="type">float</span> values to <span class="type">string</span>,
namely that the <span class="type">string</span> may be in exponential
notation (which is not supported by BCMath), and that the decimal
separator is locale dependent (while BCMath always expects a decimal
point).

``` php
<?php
$num1 = 0; // (string) 0 => '0'
$num2 = -0.000005; // (string) -0.000005 => '-5.05E-6'
echo bcadd($num1, $num2, 6); // => '0.000000'

setlocale(LC_NUMERIC, 'de_DE'); // uses a decimal comma
$num2 = 1.2; // (string) 1.2 => '1,2'
echo bcsub($num1, $num2, 1); // => '0.0'
?>
```

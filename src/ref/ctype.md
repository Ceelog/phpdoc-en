ctype\_alnum
============

Check for alphanumeric character(s)

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_alnum</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are alphanumeric.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` is either a letter or a
digit, **`FALSE`** otherwise.

### Examples

**Example \#1 A <span class="function">ctype\_alnum</span> example
(using the default locale)**

``` php
<?php
$strings = array('AbCd1zyZ9', 'foo!#$bar');
foreach ($strings as $testcase) {
    if (ctype_alnum($testcase)) {
        echo "The string $testcase consists of all letters or digits.\n";
    } else {
        echo "The string $testcase does not consist of all letters or digits.\n";
    }
}
?>
```

The above example will output:

    The string AbCd1zyZ9 consists of all letters or digits.
    The string foo!#$bar does not consist of all letters or digits.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_alpha</span>
-   <span class="function">ctype\_digit</span>
-   <span class="function">setlocale</span>

ctype\_alpha
============

Check for alphabetic character(s)

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_alpha</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are alphabetic. In the standard *C*
locale letters are just *\[A-Za-z\]* and <span
class="function">ctype\_alpha</span> is equivalent to
*(ctype\_upper($text) \|\| ctype\_lower($text))* if $text is just a
single character, but other languages have letters that are considered
neither upper nor lower case.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` is a letter from the
current locale, **`FALSE`** otherwise.

### Examples

**Example \#1 A <span class="function">ctype\_alpha</span> example
(using the default locale)**

``` php
<?php
$strings = array('KjgWZC', 'arf12');
foreach ($strings as $testcase) {
    if (ctype_alpha($testcase)) {
        echo "The string $testcase consists of all letters.\n";
    } else {
        echo "The string $testcase does not consist of all letters.\n";
    }
}
?>
```

The above example will output:

    The string KjgWZC consists of all letters.
    The string arf12 does not consist of all letters.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_upper</span>
-   <span class="function">ctype\_lower</span>
-   <span class="function">setlocale</span>

ctype\_cntrl
============

Check for control character(s)

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_cntrl</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are control characters. Control
characters are e.g. line feed, tab, escape.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` is a control character
from the current locale, **`FALSE`** otherwise.

### Examples

**Example \#1 A <span class="function">ctype\_cntrl</span> example**

``` php
<?php
$strings = array('string1' => "\n\r\t", 'string2' => 'arf12');
foreach ($strings as $name => $testcase) {
    if (ctype_cntrl($testcase)) {
        echo "The string '$name' consists of all control characters.\n";
    } else {
        echo "The string '$name' does not consist of all control characters.\n";
    }
}
?>
```

The above example will output:

    The string 'string1' consists of all control characters.
    The string 'string2' does not consist of all control characters.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_print</span>

ctype\_digit
============

Check for numeric character(s)

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_digit</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are numerical.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in the string `text` is a decimal
digit, **`FALSE`** otherwise.

### Examples

**Example \#1 A <span class="function">ctype\_digit</span> example**

``` php
<?php
$strings = array('1820.20', '10002', 'wsl!12');
foreach ($strings as $testcase) {
    if (ctype_digit($testcase)) {
        echo "The string $testcase consists of all digits.\n";
    } else {
        echo "The string $testcase does not consist of all digits.\n";
    }
}
?>
```

The above example will output:

    The string 1820.20 does not consist of all digits.
    The string 10002 consists of all digits.
    The string wsl!12 does not consist of all digits.

**Example \#2 A <span class="function">ctype\_digit</span> example
comparing strings with integers**

``` php
<?php

$numeric_string = '42';
$integer        = 42;

ctype_digit($numeric_string);  // true
ctype_digit($integer);         // false (ASCII 42 is the * character)

is_numeric($numeric_string);   // true
is_numeric($integer);          // true
?>
```

### Notes

> **Note**:
>
> This function expects a <span class="type">string</span> to be useful,
> so for example passing in an <span class="type">integer</span> may not
> return the expected result. However, also note that HTML forms will
> result in numeric strings and not integers. See also the
> <a href="/language/types.html" class="link">types</a> section of the
> manual.

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_alnum</span>
-   <span class="function">ctype\_xdigit</span>
-   <span class="function">is\_numeric</span>
-   <span class="function">is\_int</span>
-   <span class="function">is\_string</span>

ctype\_graph
============

Check for any printable character(s) except space

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_graph</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, creates visible output.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` is printable and
actually creates visible output (no white space), **`FALSE`** otherwise.

### Examples

**Example \#1 A <span class="function">ctype\_graph</span> example**

``` php
<?php
$strings = array('string1' => "asdf\n\r\t", 'string2' => 'arf12', 'string3' => 'LKA#@%.54');
foreach ($strings as $name => $testcase) {
    if (ctype_graph($testcase)) {
        echo "The string '$name' consists of all (visibly) printable characters.\n";
    } else {
        echo "The string '$name' does not consist of all (visibly) printable characters.\n";
    }
}
?>
```

The above example will output:

    The string 'string1' does not consist of all (visibly) printable characters.
    The string 'string2' consists of all (visibly) printable characters.
    The string 'string3' consists of all (visibly) printable characters.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_alnum</span>
-   <span class="function">ctype\_print</span>
-   <span class="function">ctype\_punct</span>

ctype\_lower
============

Check for lowercase character(s)

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_lower</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are lowercase letters.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` is a lowercase letter in
the current locale.

### Examples

**Example \#1 A <span class="function">ctype\_lower</span> example
(using the default locale)**

``` php
<?php
$strings = array('aac123', 'qiutoas', 'QASsdks');
foreach ($strings as $testcase) {
    if (ctype_lower($testcase)) {
        echo "The string $testcase consists of all lowercase letters.\n";
    } else {
        echo "The string $testcase does not consist of all lowercase letters.\n";
    }
}
?>
```

The above example will output:

    The string aac123 does not consist of all lowercase letters.
    The string qiutoas consists of all lowercase letters.
    The string QASsdks does not consist of all lowercase letters.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_alpha</span>
-   <span class="function">ctype\_upper</span>
-   <span class="function">setlocale</span>

ctype\_print
============

Check for printable character(s)

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_print</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are printable.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` will actually create
output (including blanks). Returns **`FALSE`** if `text` contains
control characters or characters that do not have any output or control
function at all.

### Examples

**Example \#1 A <span class="function">ctype\_print</span> example**

``` php
<?php
$strings = array('string1' => "asdf\n\r\t", 'string2' => 'arf12', 'string3' => 'LKA#@%.54');
foreach ($strings as $name => $testcase) {
    if (ctype_print($testcase)) {
        echo "The string '$name' consists of all printable characters.\n";
    } else {
        echo "The string '$name' does not consist of all printable characters.\n";
    }
}
?>
```

The above example will output:

    The string 'string1' does not consist of all printable characters.
    The string 'string2' consists of all printable characters.
    The string 'string3' consists of all printable characters.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_cntrl</span>
-   <span class="function">ctype\_graph</span>
-   <span class="function">ctype\_punct</span>

ctype\_punct
============

Check for any printable character which is not whitespace or an
alphanumeric character

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_punct</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are punctuation character.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` is printable, but
neither letter, digit or blank, **`FALSE`** otherwise.

### Examples

**Example \#1 A <span class="function">ctype\_punct</span> example**

``` php
<?php
$strings = array('ABasdk!@!$#', '!@ # $', '*&$()');
foreach ($strings as $testcase) {
    if (ctype_punct($testcase)) {
        echo "The string $testcase consists of all punctuation.\n";
    } else {
        echo "The string $testcase does not consist of all punctuation.\n";
    }
}
?>
```

The above example will output:

    The string ABasdk!@!$# does not consist of all punctuation.
    The string !@ # $ does not consist of all punctuation.
    The string *&$() consists of all punctuation.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_cntrl</span>
-   <span class="function">ctype\_graph</span>

ctype\_space
============

Check for whitespace character(s)

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_space</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, creates whitespace.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` creates some sort of
white space, **`FALSE`** otherwise. Besides the blank character this
also includes tab, vertical tab, line feed, carriage return and form
feed characters.

### Examples

**Example \#1 A <span class="function">ctype\_space</span> example**

``` php
<?php
$strings = array(
    'string1' => "\n\r\t",
    'string2' => "\narf12",
    'string3' => '\n\r\t' // note the single quotes
);
foreach ($strings as $name => $testcase) {
    if (ctype_space($testcase)) {
        echo "The string '$name' consists of whitespace characters only.\n";
    } else {
        echo "The string '$name' contains non-whitespace characters.\n";
    }
}
?>
```

The above example will output:

    The string 'string1' consists of whitespace characters only.
    The string 'string2' contains non-whitespace characters.
    The string 'string3' contains non-whitespace characters.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_cntrl</span>
-   <span class="function">ctype\_graph</span>
-   <span class="function">ctype\_punct</span>

ctype\_upper
============

Check for uppercase character(s)

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_upper</span> ( <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are uppercase characters.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` is an uppercase letter
in the current locale.

### Examples

**Example \#1 A <span class="function">ctype\_upper</span> example
(using the default locale)**

``` php
<?php
$strings = array('AKLWC139', 'LMNSDO', 'akwSKWsm');
foreach ($strings as $testcase) {
    if (ctype_upper($testcase)) {
        echo "The string $testcase consists of all uppercase letters.\n";
    } else {
        echo "The string $testcase does not consist of all uppercase letters.\n";
    }
}
?>
```

The above example will output:

    The string AKLWC139 does not consist of all uppercase letters.
    The string LMNSDO consists of all uppercase letters.
    The string akwSKWsm does not consist of all uppercase letters.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_alpha</span>
-   <span class="function">ctype\_lower</span>
-   <span class="function">setlocale</span>

ctype\_xdigit
=============

Check for character(s) representing a hexadecimal digit

### Description

<span class="type">bool</span> <span
class="methodname">ctype\_xdigit</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Checks if all of the characters in the provided <span
class="type">string</span>, `text`, are hexadecimal 'digits'.

### Parameters

`text`  
The tested string.

### Return Values

Returns **`TRUE`** if every character in `text` is a hexadecimal
'digit', that is a decimal digit or a character from *\[A-Fa-f\]* ,
**`FALSE`** otherwise.

### Examples

**Example \#1 A <span class="function">ctype\_xdigit</span> example**

``` php
<?php
$strings = array('AB10BC99', 'AR1012', 'ab12bc99');
foreach ($strings as $testcase) {
    if (ctype_xdigit($testcase)) {
        echo "The string $testcase consists of all hexadecimal digits.\n";
    } else {
        echo "The string $testcase does not consist of all hexadecimal digits.\n";
    }
}
?>
```

The above example will output:

    The string AB10BC99 consists of all hexadecimal digits.
    The string AR1012 does not consist of all hexadecimal digits.
    The string ab12bc99 consists of all hexadecimal digits.

### Notes

> **Note**:
>
> If an <span class="type">integer</span> between -128 and 255 inclusive
> is provided, it is interpreted as the ASCII value of a single
> character (negative values have 256 added in order to allow characters
> in the Extended ASCII range). Any other integer is interpreted as a
> string containing the decimal digits of the integer.

### See Also

-   <span class="function">ctype\_digit</span>

**Table of Contents**

-   [ctype\_alnum](/ref/ctype.html#ctype_alnum) — Check for alphanumeric
    character(s)
-   [ctype\_alpha](/ref/ctype.html#ctype_alpha) — Check for alphabetic
    character(s)
-   [ctype\_cntrl](/ref/ctype.html#ctype_cntrl) — Check for control
    character(s)
-   [ctype\_digit](/ref/ctype.html#ctype_digit) — Check for numeric
    character(s)
-   [ctype\_graph](/ref/ctype.html#ctype_graph) — Check for any
    printable character(s) except space
-   [ctype\_lower](/ref/ctype.html#ctype_lower) — Check for lowercase
    character(s)
-   [ctype\_print](/ref/ctype.html#ctype_print) — Check for printable
    character(s)
-   [ctype\_punct](/ref/ctype.html#ctype_punct) — Check for any
    printable character which is not whitespace or an alphanumeric
    character
-   [ctype\_space](/ref/ctype.html#ctype_space) — Check for whitespace
    character(s)
-   [ctype\_upper](/ref/ctype.html#ctype_upper) — Check for uppercase
    character(s)
-   [ctype\_xdigit](/ref/ctype.html#ctype_xdigit) — Check for
    character(s) representing a hexadecimal digit

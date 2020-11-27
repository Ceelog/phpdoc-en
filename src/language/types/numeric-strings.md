Numeric strings
---------------

A PHP <span class="type">string</span> is considered numeric if it can
be interpreted as an <span class="type">int</span> or a <span
class="type">float</span>.

Formally as of PHP 8.0.0:

    WHITESPACES      \s*
    LNUM             [0-9]+
    DNUM             ([0-9]*)[\.]{LNUM}) | ({LNUM}[\.][0-9]*)
    EXPONENT_DNUM    (({LNUM} | {DNUM}) [eE][+-]? {LNUM})
    INT_NUM_STRING   {WHITESPACES} [+-]? {LNUM} {WHITESPACES}
    FLOAT_NUM_STRING {WHITESPACES} [+-]? {EXPONENT_DNUM} {WHITESPACES}
    NUM_STRING       ({INT_NUM_STRING} | {FLOAT_NUM_STRING})

PHP also has a concept of *leading* numeric strings. This is simply a
string which starts like a numeric string followed by any characters.

### Strings used in numeric contexts

When a <span class="type">string</span> needs to be evaluated as number
(e.g. arithmetic operations, <span class="type">int</span> type
declaration, etc.) the following steps are taken to determine the
outcome:

1.  <span class="simpara"> If the <span class="type">string</span> is
    numeric, resolve to an <span class="type">int</span> if the <span
    class="type">string</span> is an integer numeric string and fits
    into the limits of the <span class="type">int</span> type limits (as
    defined by **`PHP_INT_MAX`**), otherwise resolve to a <span
    class="type">float</span>. </span>
2.  <span class="simpara"> If the context allows leading numeric strings
    and the <span class="type">string</span> is one, resolve to an <span
    class="type">int</span> if the leading part of the <span
    class="type">string</span> is an integer numeric string and fits
    into the limits of the <span class="type">int</span> type limits (as
    defined by **`PHP_INT_MAX`**), otherwise resolve to a <span
    class="type">float</span>. Additionally an error of level
    **`E_WARNING`** is raised. </span>
3.  <span class="simpara"> The <span class="type">string</span> is not
    numeric, throw a <span class="classname">TypeError</span>. </span>

### Behavior prior to PHP 8.0.0

Prior to PHP 8.0.0, a <span class="type">string</span> was considered
numeric only if it had *leading* whitespaces, if it had *trailing*
whitespaces then the string was considered to be leading numeric.

Prior to PHP 8.0.0, when a string was used in a numeric context it would
perform the same steps as above with the following differences:

-   <span class="simpara"> The usage of a leading numeric string would
    raise an **`E_NOTICE`** instead of an **`E_WARNING`**. </span>
-   <span class="simpara"> If the string is not numeric, an
    **`E_WARNING`** was raised and the value *0* would be returned.
    </span>

``` php
<?php
$foo = 1 + "10.5";                // $foo is float (11.5)
$foo = 1 + "-1.3e3";              // $foo is float (-1299)
$foo = 1 + "bob-1.3e3";           // TypeError as of PHP 8.0.0, $foo is integer (1) previously
$foo = 1 + "bob3";                // TypeError as of PHP 8.0.0, $foo is integer (1) previously
$foo = 1 + "10 Small Pigs";       // $foo is integer (11) and an E_WARNING is raised in PHP 8.0.0, E_NOTICE previously
$foo = 4 + "10.2 Little Piggies"; // $foo is float (14.2) and an E_WARNING is raised in PHP 8.0.0, E_NOTICE previously
$foo = "10.0 pigs " + 1;          // $foo is float (11) and an E_WARNING is raised in PHP 8.0.0, E_NOTICE previously
$foo = "10.0 pigs " + 1.0;        // $foo is float (11) and an E_WARNING is raised in PHP 8.0.0, E_NOTICE previously
?>
```

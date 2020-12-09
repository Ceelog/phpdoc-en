**Warning**

This feature was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this feature include:

-   <a href="/book/pcre.html" class="link">PCRE</a> (for full regular
    expression support)
-   <span class="function">fnmatch</span> (for simpler shell style
    wildcard pattern matching)

ereg\_replace
=============

Replace regular expression

**Warning**

This function was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">preg\_replace</span>

### Description

<span class="type">string</span> <span
class="methodname">ereg\_replace</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">string</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> )

This function scans `string` for matches to `pattern`, then replaces the
matched text with `replacement`.

### Parameters

`pattern`  
A POSIX extended regular expression.

`replacement`  
If `pattern` contains parenthesized substrings, `replacement` may
contain substrings of the form *\\<span
class="replaceable">digit</span>*, which will be replaced by the text
matching the digit'th parenthesized substring; *\\0* will produce the
entire contents of string. Up to nine substrings may be used.
Parentheses may be nested, in which case they are counted by the opening
parenthesis.

`string`  
The input string.

### Return Values

The modified string is returned. If no matches are found in `string`,
then it will be returned unchanged.

### Examples

For example, the following code snippet prints "This was a test" three
times:

**Example \#1 <span class="function">ereg\_replace</span> example**

``` php
<?php

$string = "This is a test";
echo str_replace(" is", " was", $string);
echo ereg_replace("( )is", "\\1was", $string);
echo ereg_replace("(( )is)", "\\2was", $string);

?>
```

One thing to take note of is that if you use an integer value as the
`replacement` parameter, you may not get the results you expect. This is
because <span class="function">ereg\_replace</span> will interpret the
number as the ordinal value of a character, and apply that. For
instance:

**Example \#2 <span class="function">ereg\_replace</span> example**

``` php
<?php
/* This will not work as expected. */
$num = 4;
$string = "This string has four words.";
$string = ereg_replace('four', $num, $string);
echo $string;   /* Output: 'This string has   words.' */

/* This will work. */
$num = '4';
$string = "This string has four words.";
$string = ereg_replace('four', $num, $string);
echo $string;   /* Output: 'This string has 4 words.' */
?>
```

**Example \#3 Replace URLs with links**

``` php
<?php
$text = ereg_replace("[[:alpha:]]+://[^<>[:space:]]+[[:alnum:]/]",
                     '<a href="\\0">\\0</a>', $text);
?>
```

### See Also

-   <span class="function">ereg</span>
-   <span class="function">eregi</span>
-   <span class="function">eregi\_replace</span>
-   <span class="function">str\_replace</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">quotemeta</span>

ereg
====

Regular expression match

**Warning**

This function was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">preg\_match</span>

### Description

<span class="type">int</span> <span class="methodname">ereg</span> (
<span class="methodparam"><span class="type">string</span>
`$pattern`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$regs`</span> \] )

Searches a `string` for matches to the regular expression given in
`pattern` in a case-sensitive way.

### Parameters

`pattern`  
Case sensitive regular expression.

`string`  
The input string.

`regs`  
If matches are found for parenthesized substrings of `pattern` and the
function is called with the third argument `regs`, the matches will be
stored in the elements of the array `regs`.

`$regs[1]` will contain the substring which starts at the first left
parenthesis; `$regs[2]` will contain the substring starting at the
second, and so on. `$regs[0]` will contain a copy of the complete string
matched.

### Return Values

Returns the length of the matched string if a match for `pattern` was
found in `string`, or **`false`** if no matches were found or an error
occurred.

If the optional parameter `regs` was not passed or the length of the
matched string is *0*, this function returns *1*.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                                       |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 4.1.0   | Up to (and including) PHP 4.1.0 `$regs` will be filled with exactly ten elements, even though more or fewer than ten parenthesized substrings may actually have matched. This has no effect on <span class="function">ereg</span>'s ability to match more substrings. If no matches are found, *$regs* will not be altered by <span class="function">ereg</span>. |

### Examples

**Example \#1 <span class="function">ereg</span> example**

The following code snippet takes a date in ISO format (YYYY-MM-DD) and
prints it in DD.MM.YYYY format:

``` php
<?php
if (ereg ("([0-9]{4})-([0-9]{1,2})-([0-9]{1,2})", $date, $regs)) {
    echo "$regs[3].$regs[2].$regs[1]";
} else {
    echo "Invalid date format: $date";
}
?>
```

### See Also

-   <span class="function">eregi</span>
-   <span class="function">ereg\_replace</span>
-   <span class="function">eregi\_replace</span>
-   <span class="function">preg\_match</span>
-   <span class="function">strpos</span>
-   <span class="function">strstr</span>
-   <span class="function">quotemeta</span>

eregi\_replace
==============

Replace regular expression case insensitive

**Warning**

This function was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">preg\_replace</span> (with the *i*
    (**`PCRE_CASELESS`**) modifier)

### Description

<span class="type">string</span> <span
class="methodname">eregi\_replace</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">string</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> )

This function is identical to <span
class="function">ereg\_replace</span> except that this ignores case
distinction when matching alphabetic characters.

### Parameters

`pattern`  
A POSIX extended regular expression.

`replacement`  
If `pattern` contains parenthesized substrings, `replacement` may
contain substrings of the form *\\<span
class="replaceable">digit</span>*, which will be replaced by the text
matching the digit'th parenthesized substring; *\\0* will produce the
entire contents of string. Up to nine substrings may be used.
Parentheses may be nested, in which case they are counted by the opening
parenthesis.

`string`  
The input string.

### Return Values

The modified string is returned. If no matches are found in `string`,
then it will be returned unchanged.

### Examples

**Example \#1 Highlight search results**

``` php
<?php
$pattern = '(>[^<]*)('. quotemeta($_GET['search']) .')';
$replacement = '\\1<span class="search">\\2</span>';
$body = eregi_replace($pattern, $replacement, $body);
?>
```

### See Also

-   <span class="function">ereg</span>
-   <span class="function">eregi</span>
-   <span class="function">ereg\_replace</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">quotemeta</span>

eregi
=====

Case insensitive regular expression match

**Warning**

This function was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">preg\_match</span> (with the *i*
    (**`PCRE_CASELESS`**) modifier)

### Description

<span class="type">int</span> <span class="methodname">eregi</span> (
<span class="methodparam"><span class="type">string</span>
`$pattern`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$regs`</span> \] )

This function is identical to <span class="function">ereg</span> except
that it ignores case distinction when matching alphabetic characters.

### Parameters

`pattern`  
Case insensitive regular expression.

`string`  
The input string.

`regs`  
If matches are found for parenthesized substrings of `pattern` and the
function is called with the third argument `regs`, the matches will be
stored in the elements of the array `regs`.

`$regs[1]` will contain the substring which starts at the first left
parenthesis; `$regs[2]` will contain the substring starting at the
second, and so on. `$regs[0]` will contain a copy of the complete string
matched.

### Return Values

Returns the length of the matched string if a match for `pattern` was
found in `string`, or **`false`** if no matches were found or an error
occurred.

If the optional parameter `regs` was not passed or the length of the
matched string is *0*, this function returns *1*.

### Examples

**Example \#1 <span class="function">eregi</span> example**

``` php
<?php
$string = 'XYZ';
if (eregi('z', $string)) {
    echo "'$string' contains a 'z' or 'Z'!";
}
?>
```

### See Also

-   <span class="function">ereg</span>
-   <span class="function">ereg\_replace</span>
-   <span class="function">eregi\_replace</span>
-   <span class="function">preg\_match</span>
-   <span class="function">stripos</span>
-   <span class="function">stristr</span>
-   <span class="function">quotemeta</span>

split
=====

Split string into array by regular expression

**Warning**

This function was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">preg\_split</span>
-   <span class="function">explode</span>
-   <span class="function">str\_split</span>

### Description

<span class="type">array</span> <span class="methodname">split</span> (
<span class="methodparam"><span class="type">string</span>
`$pattern`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = -1</span></span> \] )

Splits a `string` into array by regular expression.

### Parameters

`pattern`  
Case sensitive regular expression.

If you want to split on any of the characters which are considered
special by regular expressions, you'll need to escape them first. If you
think <span class="function">split</span> (or any other regex function,
for that matter) is doing something weird, please read the file
`regex.7`, included in the `regex/` subdirectory of the PHP
distribution. It's in manpage format, so you'll want to do something
along the lines of **man /usr/local/src/regex/regex.7** in order to read
it.

`string`  
The input string.

`limit`  
If `limit` is set, the returned array will contain a maximum of `limit`
elements with the last element containing the whole rest of `string`.

### Return Values

Returns an array of strings, each of which is a substring of `string`
formed by splitting it on boundaries formed by the case-sensitive
regular expression `pattern`.

If there are <span class="replaceable">n</span> occurrences of
`pattern`, the returned array will contain *<span
class="replaceable">n</span>+1* items. For example, if there is no
occurrence of `pattern`, an array with only one element will be
returned. Of course, this is also true if `string` is empty. If an error
occurs, <span class="function">split</span> returns **`false`**.

### Examples

**Example \#1 <span class="function">split</span> example**

To split off the first four fields from a line from `/etc/passwd`:

``` php
<?php
list($user, $pass, $uid, $gid, $extra) =
    split(":", $passwd_line, 5);
?>
```

**Example \#2 <span class="function">split</span> example**

To parse a date which may be delimited with slashes, dots, or hyphens:

``` php
<?php
// Delimiters may be slash, dot, or hyphen
$date = "04/30/1973";
list($month, $day, $year) = split('[/.-]', $date);
echo "Month: $month; Day: $day; Year: $year<br />\n";
?>
```

### Notes

**Tip**

<span class="function">split</span> is deprecated as of PHP 5.3.0. <span
class="function">preg\_split</span> is the suggested alternative to this
function. If you don't require the power of regular expressions, it is
faster to use <span class="function">explode</span>, which doesn't incur
the overhead of the regular expression engine.

**Tip**

For users looking for a way to emulate Perl's **@chars = split('',
$str)** behaviour, please see the examples for <span
class="function">preg\_split</span> or <span
class="function">str\_split</span>.

### See Also

-   <span class="function">preg\_split</span>
-   <span class="function">spliti</span>
-   <span class="function">str\_split</span>
-   <span class="function">explode</span>
-   <span class="function">implode</span>
-   <span class="function">chunk\_split</span>
-   <span class="function">wordwrap</span>

spliti
======

Split string into array by regular expression case insensitive

**Warning**

This function was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">preg\_split</span> (with the *i*
    (**`PCRE_CASELESS`**) modifier)

### Description

<span class="type">array</span> <span class="methodname">spliti</span> (
<span class="methodparam"><span class="type">string</span>
`$pattern`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = -1</span></span> \] )

Splits a `string` into array by regular expression.

This function is identical to <span class="function">split</span> except
that this ignores case distinction when matching alphabetic characters.

### Parameters

`pattern`  
Case insensitive regular expression.

If you want to split on any of the characters which are considered
special by regular expressions, you'll need to escape them first. If you
think <span class="function">spliti</span> (or any other regex function,
for that matter) is doing something weird, please read the file
`regex.7`, included in the `regex/` subdirectory of the PHP
distribution. It's in manpage format, so you'll want to do something
along the lines of **man /usr/local/src/regex/regex.7** in order to read
it.

`string`  
The input string.

`limit`  
If `limit` is set, the returned array will contain a maximum of `limit`
elements with the last element containing the whole rest of `string`.

### Return Values

Returns an array of strings, each of which is a substring of `string`
formed by splitting it on boundaries formed by the case insensitive
regular expression `pattern`.

If there are <span class="replaceable">n</span> occurrences of
`pattern`, the returned array will contain *<span
class="replaceable">n</span>+1* items. For example, if there is no
occurrence of `pattern`, an array with only one element will be
returned. Of course, this is also true if `string` is empty. If an error
occurs, <span class="function">spliti</span> returns **`false`**.

### Examples

This example splits a string using 'a' as the separator :

**Example \#1 <span class="function">spliti</span> example**

``` php
<?php
$string = "aBBBaCCCADDDaEEEaGGGA";
$chunks = spliti ("a", $string, 5);
print_r($chunks);
?>
```

The above example will output:

    Array
    (
      [0] =>
      [1] => BBB
      [2] => CCC
      [3] => DDD
      [4] => EEEaGGGA
    )

### See Also

-   <span class="function">preg\_split</span>
-   <span class="function">split</span>
-   <span class="function">explode</span>
-   <span class="function">implode</span>

sql\_regcase
============

Make regular expression for case insensitive match

**Warning**

This function was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">preg\_match</span>
-   <span class="function">preg\_quote</span>

### Description

<span class="type">string</span> <span
class="methodname">sql\_regcase</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> )

Creates a regular expression for a case insensitive match.

### Parameters

`string`  
The input string.

### Return Values

Returns a valid regular expression which will match `string`, ignoring
case. This expression is `string` with each alphabetic character
converted to a bracket expression; this bracket expression contains that
character's uppercase and lowercase form. Other characters remain
unchanged.

### Examples

**Example \#1 <span class="function">sql\_regcase</span> example**

``` php
<?php
echo sql_regcase("Foo - bar.");
?>
```

The above example will output:

    [Ff][Oo][Oo] - [Bb][Aa][Rr].

This can be used to achieve case insensitive pattern matching in
products which support only case sensitive regular expressions.

**Table of Contents**

-   [ereg\_replace](/ref/regex.html#ereg_replace) — Replace regular
    expression
-   [ereg](/ref/regex.html#ereg) — Regular expression match
-   [eregi\_replace](/ref/regex.html#eregi_replace) — Replace regular
    expression case insensitive
-   [eregi](/ref/regex.html#eregi) — Case insensitive regular expression
    match
-   [split](/ref/regex.html#split) — Split string into array by regular
    expression
-   [spliti](/ref/regex.html#spliti) — Split string into array by
    regular expression case insensitive
-   [sql\_regcase](/ref/regex.html#sql_regcase) — Make regular
    expression for case insensitive match

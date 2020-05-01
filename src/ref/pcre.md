preg\_filter
============

Perform a regular expression search and replace

### Description

<span class="type">mixed</span> <span
class="methodname">preg\_filter</span> ( <span class="methodparam"><span
class="type">mixed</span> `$pattern`</span> , <span
class="methodparam"><span class="type">mixed</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$subject`</span> \[, <span
class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `&$count`</span> \]\]
)

<span class="function">preg\_filter</span> is identical to <span
class="function">preg\_replace</span> except it only returns the
(possibly transformed) subjects where there was a match. For details
about how this function works, read the <span
class="function">preg\_replace</span> documentation.

### Return Values

Returns an <span class="type">array</span> if the `subject` parameter is
an <span class="type">array</span>, or a <span
class="type">string</span> otherwise.

If no matches are found or an error occurred, an empty <span
class="type">array</span> is returned when `subject` is an <span
class="type">array</span> or **`NULL`** otherwise.

### Examples

**Example \#1 Example comparing <span
class="function">preg\_filter</span> with <span
class="function">preg\_replace</span>**

``` php
<?php
$subject = array('1', 'a', '2', 'b', '3', 'A', 'B', '4'); 
$pattern = array('/\d/', '/[a-z]/', '/[1a]/'); 
$replace = array('A:$0', 'B:$0', 'C:$0'); 

echo "preg_filter returns\n";
print_r(preg_filter($pattern, $replace, $subject)); 

echo "preg_replace returns\n";
print_r(preg_replace($pattern, $replace, $subject)); 
?>
```

The above example will output:

    preg_filter returns
    Array
    (
        [0] => A:C:1
        [1] => B:C:a
        [2] => A:2
        [3] => B:b
        [4] => A:3
        [7] => A:4
    )
    preg_replace returns
    Array
    (
        [0] => A:C:1
        [1] => B:C:a
        [2] => A:2
        [3] => B:b
        [4] => A:3
        [5] => A
        [6] => B
        [7] => A:4
    )

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">preg\_quote</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">preg\_replace\_callback</span>
-   <span class="function">preg\_grep</span>
-   <span class="function">preg\_last\_error</span>

preg\_grep
==========

Return array entries that match the pattern

### Description

<span class="type">array</span> <span
class="methodname">preg\_grep</span> ( <span class="methodparam"><span
class="type">string</span> `$pattern`</span> , <span
class="methodparam"><span class="type">array</span> `$input`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \] )

Returns the array consisting of the elements of the `input` array that
match the given `pattern`.

### Parameters

`pattern`  
The pattern to search for, as a string.

`input`  
The input array.

`flags`  
If set to **`PREG_GREP_INVERT`**, this function returns the elements of
the input array that do *not* match the given `pattern`.

### Return Values

Returns an array indexed using the keys from the `input` array.

### Examples

**Example \#1 <span class="function">preg\_grep</span> example**

``` php
<?php
// return all array elements
// containing floating point numbers
$fl_array = preg_grep("/^(\d+)?\.\d+$/", $array);
?>
```

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">preg\_quote</span>
-   <span class="function">preg\_match\_all</span>
-   <span class="function">preg\_filter</span>
-   <span class="function">preg\_last\_error</span>

preg\_last\_error
=================

Returns the error code of the last PCRE regex execution

### Description

<span class="type">int</span> <span
class="methodname">preg\_last\_error</span> ( <span
class="methodparam">void</span> )

Returns the error code of the last PCRE regex execution.

**Example \#1 <span class="function">preg\_last\_error</span> example**

``` php
<?php

preg_match('/(?:\D+|<\d+>)*[!?]/', 'foobar foobar foobar');

if (preg_last_error() == PREG_BACKTRACK_LIMIT_ERROR) {
    print 'Backtrack limit was exhausted!';
}

?>
```

The above example will output:

    Backtrack limit was exhausted!

### Return Values

Returns one of the following constants
(<a href="/pcre/constants.html" class="link">explained on their own page</a>):

-   **`PREG_NO_ERROR`**
-   **`PREG_INTERNAL_ERROR`**
-   **`PREG_BACKTRACK_LIMIT_ERROR`** (see also
    <a href="/pcre/setup.html#" class="link">pcre.backtrack_limit</a>)
-   **`PREG_RECURSION_LIMIT_ERROR`** (see also
    <a href="/pcre/setup.html#" class="link">pcre.recursion_limit</a>)
-   **`PREG_BAD_UTF8_ERROR`**
-   **`PREG_BAD_UTF8_OFFSET_ERROR`** (since PHP 5.3.0)
-   **`PREG_JIT_STACKLIMIT_ERROR`** (since PHP 7.0.0)

preg\_match\_all
================

Perform a global regular expression match

### Description

<span class="type">int</span> <span
class="methodname">preg\_match\_all</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">string</span>
`$subject`</span> \[, <span class="methodparam"><span
class="type">array</span> `&$matches`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = **`PREG_PATTERN_ORDER`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 0</span></span> \]\]\] )

Searches `subject` for all matches to the regular expression given in
`pattern` and puts them in `matches` in the order specified by `flags`.

After the first match is found, the subsequent searches are continued on
from end of the last match.

### Parameters

`pattern`  
The pattern to search for, as a string.

`subject`  
The input string.

`matches`  
Array of all matches in multi-dimensional array ordered according to
`flags`.

`flags`  
Can be a combination of the following flags (note that it doesn't make
sense to use **`PREG_PATTERN_ORDER`** together with
**`PREG_SET_ORDER`**):

**`PREG_PATTERN_ORDER`**  
Orders results so that `$matches[0]` is an array of full pattern
matches, `$matches[1]` is an array of strings matched by the first
parenthesized subpattern, and so on.

``` php
<?php
preg_match_all("|<[^>]+>(.*)</[^>]+>|U",
    "<b>example: </b><div align=left>this is a test</div>",
    $out, PREG_PATTERN_ORDER);
echo $out[0][0] . ", " . $out[0][1] . "\n";
echo $out[1][0] . ", " . $out[1][1] . "\n";
?>
```

The above example will output:

    <b>example: </b>, <div align=left>this is a test</div>
    example: , this is a test

So, `$out[0]` contains array of strings that matched full pattern, and
`$out[1]` contains array of strings enclosed by tags.

If the pattern contains named subpatterns, `$matches` additionally
contains entries for keys with the subpattern name.

If the pattern contains duplicate named subpatterns, only the rightmost
subpattern is stored in `$matches[NAME]`.

``` php
<?php
preg_match_all(
    '/(?J)(?<match>foo)|(?<match>bar)/',
    'foo bar',
    $matches,
    PREG_PATTERN_ORDER
);
print_r($matches['match']);
?>
```

The above example will output:

    Array
    (
        [0] => 
        [1] => bar
    )

**`PREG_SET_ORDER`**  
Orders results so that `$matches[0]` is an array of first set of
matches, `$matches[1]` is an array of second set of matches, and so on.

``` php
<?php
preg_match_all("|<[^>]+>(.*)</[^>]+>|U",
    "<b>example: </b><div align=\"left\">this is a test</div>",
    $out, PREG_SET_ORDER);
echo $out[0][0] . ", " . $out[0][1] . "\n";
echo $out[1][0] . ", " . $out[1][1] . "\n";
?>
```

The above example will output:

    <b>example: </b>, example:
    <div align="left">this is a test</div>, this is a test

**`PREG_OFFSET_CAPTURE`**  
If this flag is passed, for every occurring match the appendant string
offset will also be returned. Note that this changes the value of
`matches` into an array of arrays where every element is an array
consisting of the matched string at offset *0* and its string offset
into `subject` at offset *1*.

``` php
<?php
preg_match_all('/(foo)(bar)(baz)/', 'foobarbaz', $matches, PREG_OFFSET_CAPTURE);
print_r($matches);
?>
```

The above example will output:

    Array
    (
        [0] => Array
            (
                [0] => Array
                    (
                        [0] => foobarbaz
                        [1] => 0
                    )

            )

        [1] => Array
            (
                [0] => Array
                    (
                        [0] => foo
                        [1] => 0
                    )

            )

        [2] => Array
            (
                [0] => Array
                    (
                        [0] => bar
                        [1] => 3
                    )

            )

        [3] => Array
            (
                [0] => Array
                    (
                        [0] => baz
                        [1] => 6
                    )

            )

    )

**`PREG_UNMATCHED_AS_NULL`**  
If this flag is passed, unmatched subpatterns are reported as
**`NULL`**; otherwise they are reported as an empty <span
class="type">string</span>.

If no order flag is given, **`PREG_PATTERN_ORDER`** is assumed.

`offset`  
Normally, the search starts from the beginning of the subject string.
The optional parameter `offset` can be used to specify the alternate
place from which to start the search (in bytes).

> **Note**:
>
> Using `offset` is not equivalent to passing
> `substr($subject, $offset)` to <span
> class="function">preg\_match\_all</span> in place of the subject
> string, because `pattern` can contain assertions such as *^*, *$* or
> *(?\<=x)*. See <span class="function">preg\_match</span> for examples.

### Return Values

Returns the number of full pattern matches (which might be zero), or
**`FALSE`** if an error occurred.

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The **`PREG_UNMATCHED_AS_NULL`** is now supported for the `$flags` parameter.                                                                    |
| 5.4.0   | The `matches` parameter became optional.                                                                                                         |
| 5.3.6   | Returns **`FALSE`** if `offset` is higher than `subject` length.                                                                                 |
| 5.2.2   | Named subpatterns now accept the syntax *(?\<name\>)* and *(?'name')* as well as *(?P\<name\>)*. Previous versions accepted only *(?P\<name\>)*. |

### Examples

**Example \#1 Getting all phone numbers out of some text.**

``` php
<?php
preg_match_all("/\(?  (\d{3})?  \)?  (?(1)  [\-\s] ) \d{3}-\d{4}/x",
                "Call 555-1212 or 1-800-555-1212", $phones);
?>
```

**Example \#2 Find matching HTML tags (greedy)**

``` php
<?php
// The \\2 is an example of backreferencing. This tells pcre that
// it must match the second set of parentheses in the regular expression
// itself, which would be the ([\w]+) in this case. The extra backslash is
// required because the string is in double quotes.
$html = "<b>bold text</b><a href=howdy.html>click me</a>";

preg_match_all("/(<([\w]+)[^>]*>)(.*?)(<\/\\2>)/", $html, $matches, PREG_SET_ORDER);

foreach ($matches as $val) {
    echo "matched: " . $val[0] . "\n";
    echo "part 1: " . $val[1] . "\n";
    echo "part 2: " . $val[2] . "\n";
    echo "part 3: " . $val[3] . "\n";
    echo "part 4: " . $val[4] . "\n\n";
}
?>
```

The above example will output:

    matched: <b>bold text</b>
    part 1: <b>
    part 2: b
    part 3: bold text
    part 4: </b>

    matched: <a href=howdy.html>click me</a>
    part 1: <a href=howdy.html>
    part 2: a
    part 3: click me
    part 4: </a>

**Example \#3 Using named subpattern**

``` php
<?php

$str = <<<FOO
a: 1
b: 2
c: 3
FOO;

preg_match_all('/(?P<name>\w+): (?P<digit>\d+)/', $str, $matches);

/* This also works in PHP 5.2.2 (PCRE 7.0) and later, however 
 * the above form is recommended for backwards compatibility */
// preg_match_all('/(?<name>\w+): (?<digit>\d+)/', $str, $matches);

print_r($matches);

?>
```

The above example will output:

    Array
    (
        [0] => Array
            (
                [0] => a: 1
                [1] => b: 2
                [2] => c: 3
            )

        [name] => Array
            (
                [0] => a
                [1] => b
                [2] => c
            )

        [1] => Array
            (
                [0] => a
                [1] => b
                [2] => c
            )

        [digit] => Array
            (
                [0] => 1
                [1] => 2
                [2] => 3
            )

        [2] => Array
            (
                [0] => 1
                [1] => 2
                [2] => 3
            )

    )

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">preg\_quote</span>
-   <span class="function">preg\_match</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">preg\_split</span>
-   <span class="function">preg\_last\_error</span>

preg\_match
===========

Perform a regular expression match

### Description

<span class="type">int</span> <span
class="methodname">preg\_match</span> ( <span class="methodparam"><span
class="type">string</span> `$pattern`</span> , <span
class="methodparam"><span class="type">string</span> `$subject`</span>
\[, <span class="methodparam"><span class="type">array</span>
`&$matches`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$offset`<span class="initializer"> =
0</span></span> \]\]\] )

Searches `subject` for a match to the regular expression given in
`pattern`.

### Parameters

`pattern`  
The pattern to search for, as a string.

`subject`  
The input string.

`matches`  
If `matches` is provided, then it is filled with the results of search.
`$matches[0]` will contain the text that matched the full pattern,
`$matches[1]` will have the text that matched the first captured
parenthesized subpattern, and so on.

`flags`  
`flags` can be a combination of the following flags:

**`PREG_OFFSET_CAPTURE`**  
If this flag is passed, for every occurring match the appendant string
offset (in bytes) will also be returned. Note that this changes the
value of `matches` into an array where every element is an array
consisting of the matched string at offset *0* and its string offset
into `subject` at offset *1*.

``` php
<?php
preg_match('/(foo)(bar)(baz)/', 'foobarbaz', $matches, PREG_OFFSET_CAPTURE);
print_r($matches);
?>
```

The above example will output:

    Array
    (
        [0] => Array
            (
                [0] => foobarbaz
                [1] => 0
            )

        [1] => Array
            (
                [0] => foo
                [1] => 0
            )

        [2] => Array
            (
                [0] => bar
                [1] => 3
            )

        [3] => Array
            (
                [0] => baz
                [1] => 6
            )

    )

**`PREG_UNMATCHED_AS_NULL`**  
If this flag is passed, unmatched subpatterns are reported as
**`NULL`**; otherwise they are reported as an empty <span
class="type">string</span>.

``` php
<?php
preg_match('/(a)(b)*(c)/', 'ac', $matches);
var_dump($matches);
preg_match('/(a)(b)*(c)/', 'ac', $matches, PREG_UNMATCHED_AS_NULL);
var_dump($matches);
?>
```

The above example will output:

    array(4) {
      [0]=>
      string(2) "ac"
      [1]=>
      string(1) "a"
      [2]=>
      string(0) ""
      [3]=>
      string(1) "c"
    }
    array(4) {
      [0]=>
      string(2) "ac"
      [1]=>
      string(1) "a"
      [2]=>
      NULL
      [3]=>
      string(1) "c"
    }

`offset`  
Normally, the search starts from the beginning of the subject string.
The optional parameter `offset` can be used to specify the alternate
place from which to start the search (in bytes).

> **Note**:
>
> Using `offset` is not equivalent to passing
> `substr($subject, $offset)` to <span
> class="function">preg\_match</span> in place of the subject string,
> because `pattern` can contain assertions such as *^*, *$* or
> *(?\<=x)*. Compare:
>
> ``` php
> <?php
> $subject = "abcdef";
> $pattern = '/^def/';
> preg_match($pattern, $subject, $matches, PREG_OFFSET_CAPTURE, 3);
> print_r($matches);
> ?>
> ```
>
> The above example will output:
>
>     Array
>     (
>     )
>
> while this example
>
> ``` php
> <?php
> $subject = "abcdef";
> $pattern = '/^def/';
> preg_match($pattern, substr($subject,3), $matches, PREG_OFFSET_CAPTURE);
> print_r($matches);
> ?>
> ```
>
> will produce
>
>     Array
>     (
>         [0] => Array
>             (
>                 [0] => def
>                 [1] => 0
>             )
>
>     )
>
> Alternatively, to avoid using <span class="function">substr</span>,
> use the *\\G* assertion rather than the *^* anchor, or the *A*
> modifier instead, both of which work with the `offset` parameter.

### Return Values

<span class="function">preg\_match</span> returns 1 if the `pattern`
matches given `subject`, 0 if it does not, or **`FALSE`** if an error
occurred.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The **`PREG_UNMATCHED_AS_NULL`** is now supported for the `$flags` parameter.                                                                    |
| 5.3.6   | Returns **`FALSE`** if `offset` is higher than `subject` length.                                                                                 |
| 5.2.2   | Named subpatterns now accept the syntax *(?\<name\>)* and *(?'name')* as well as *(?P\<name\>)*. Previous versions accepted only *(?P\<name\>)*. |

### Examples

**Example \#1 Find the string of text "php"**

``` php
<?php
// The "i" after the pattern delimiter indicates a case-insensitive search
if (preg_match("/php/i", "PHP is the web scripting language of choice.")) {
    echo "A match was found.";
} else {
    echo "A match was not found.";
}
?>
```

**Example \#2 Find the word "web"**

``` php
<?php
/* The \b in the pattern indicates a word boundary, so only the distinct
 * word "web" is matched, and not a word partial like "webbing" or "cobweb" */
if (preg_match("/\bweb\b/i", "PHP is the web scripting language of choice.")) {
    echo "A match was found.";
} else {
    echo "A match was not found.";
}

if (preg_match("/\bweb\b/i", "PHP is the website scripting language of choice.")) {
    echo "A match was found.";
} else {
    echo "A match was not found.";
}
?>
```

**Example \#3 Getting the domain name out of a URL**

``` php
<?php
// get host name from URL
preg_match('@^(?:http://)?([^/]+)@i',
    "http://www.php.net/index.html", $matches);
$host = $matches[1];

// get last two segments of host name
preg_match('/[^.]+\.[^.]+$/', $host, $matches);
echo "domain name is: {$matches[0]}\n";
?>
```

The above example will output:

    domain name is: php.net

**Example \#4 Using named subpattern**

``` php
<?php

$str = 'foobar: 2008';

preg_match('/(?P<name>\w+): (?P<digit>\d+)/', $str, $matches);

/* This also works in PHP 5.2.2 (PCRE 7.0) and later, however 
 * the above form is recommended for backwards compatibility */
// preg_match('/(?<name>\w+): (?<digit>\d+)/', $str, $matches);

print_r($matches);

?>
```

The above example will output:

    Array
    (
        [0] => foobar: 2008
        [name] => foobar
        [1] => foobar
        [digit] => 2008
        [2] => 2008
    )

### Notes

**Tip**

Do not use <span class="function">preg\_match</span> if you only want to
check if one string is contained in another string. Use <span
class="function">strpos</span> instead as it will be faster.

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">preg\_quote</span>
-   <span class="function">preg\_match\_all</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">preg\_split</span>
-   <span class="function">preg\_last\_error</span>

preg\_quote
===========

Quote regular expression characters

### Description

<span class="type">string</span> <span
class="methodname">preg\_quote</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> \[, <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = **`NULL`**</span></span> \] )

<span class="function">preg\_quote</span> takes `str` and puts a
backslash in front of every character that is part of the regular
expression syntax. This is useful if you have a run-time string that you
need to match in some text and the string may contain special regex
characters.

The special regular expression characters are: *. \\ + \* ? \[ ^ \] $ (
) { } = ! \< \> \| : - \#*

Note that */* is not a special regular expression character.

> **Note**:
>
> Note that <span class="function">preg\_quote</span> is not meant to be
> applied to the $replacement string(s) of <span
> class="function">preg\_replace</span> etc.

### Parameters

`str`  
The input string.

`delimiter`  
If the optional `delimiter` is specified, it will also be escaped. This
is useful for escaping the delimiter that is required by the PCRE
functions. The */* is the most commonly used delimiter.

### Return Values

Returns the quoted (escaped) string.

### Changelog

| Version | Description                      |
|---------|----------------------------------|
| 7.3.0   | The *\#* character is now quoted |
| 5.3.0   | The *-* character is now quoted  |

### Examples

**Example \#1 <span class="function">preg\_quote</span> example**

``` php
<?php
$keywords = '$40 for a g3/400';
$keywords = preg_quote($keywords, '/');
echo $keywords; // returns \$40 for a g3\/400
?>
```

**Example \#2 Italicizing a word within some text**

``` php
<?php
// In this example, preg_quote($word) is used to keep the
// asterisks from having special meaning to the regular
// expression.

$textbody = "This book is *very* difficult to find.";
$word = "*very*";
$textbody = preg_replace ("/" . preg_quote($word, '/') . "/",
                          "<i>" . $word . "</i>",
                          $textbody);
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">escapeshellcmd</span>

preg\_replace\_callback\_array
==============================

Perform a regular expression search and replace using callbacks

### Description

<span class="type">mixed</span> <span
class="methodname">preg\_replace\_callback\_array</span> ( <span
class="methodparam"><span class="type">array</span>
`$patterns_and_callbacks`</span> , <span class="methodparam"><span
class="type">mixed</span> `$subject`</span> \[, <span
class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `&$count`</span> \]\]
)

The behavior of this function is similar to <span
class="function">preg\_replace\_callback</span>, except that callbacks
are executed on a per-pattern basis.

### Parameters

`patterns_and_callbacks`  
An associative array mapping patterns (keys) to callbacks (values).

`subject`  
The string or an array with strings to search and replace.

`limit`  
The maximum possible replacements for each pattern in each `subject`
string. Defaults to *-1* (no limit).

`count`  
If specified, this variable will be filled with the number of
replacements done.

### Return Values

<span class="function">preg\_replace\_callback\_array</span> returns an
array if the `subject` parameter is an array, or a string otherwise. On
errors the return value is **`NULL`**

If matches are found, the new subject will be returned, otherwise
`subject` will be returned unchanged.

### Examples

**Example \#1 <span
class="function">preg\_replace\_callback\_array</span> example**

``` php
<?php
$subject = 'Aaaaaa Bbb';

preg_replace_callback_array(
    [
        '~[a]+~i' => function ($match) {
            echo strlen($match[0]), ' matches for "a" found', PHP_EOL;
        },
        '~[b]+~i' => function ($match) {
            echo strlen($match[0]), ' matches for "b" found', PHP_EOL;
        }
    ],
    $subject
);
?>
```

The above example will output:

    6 matches for "a" found
    3 matches for "b" found

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">preg\_replace\_callback</span>
-   <span class="function">preg\_quote</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">preg\_last\_error</span>
-   <a href="/functions/anonymous.html" class="link">Anonymous functions</a>
-   information about the
    <a href="/language/pseudo-types.html#language.types.callback" class="link">callback</a>
    type

preg\_replace\_callback
=======================

Perform a regular expression search and replace using a callback

### Description

<span class="type">mixed</span> <span
class="methodname">preg\_replace\_callback</span> ( <span
class="methodparam"><span class="type">mixed</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> , <span class="methodparam"><span
class="type">mixed</span> `$subject`</span> \[, <span
class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `&$count`</span> \]\]
)

The behavior of this function is almost identical to <span
class="function">preg\_replace</span>, except for the fact that instead
of `replacement` parameter, one should specify a `callback`.

### Parameters

`pattern`  
The pattern to search for. It can be either a string or an array with
strings.

`callback`  
A callback that will be called and passed an array of matched elements
in the `subject` string. The callback should return the replacement
string. This is the callback signature:

<span class="type">string</span> <span class="methodname"><span
class="replaceable">handler</span></span> ( <span
class="methodparam"><span class="type">array</span> `$matches`</span> )

You'll often need the `callback` function for a <span
class="function">preg\_replace\_callback</span> in just one place. In
this case you can use an
<a href="/functions/anonymous.html" class="link">anonymous function</a>
to declare the callback within the call to <span
class="function">preg\_replace\_callback</span>. By doing it this way
you have all information for the call in one place and do not clutter
the function namespace with a callback function's name not used anywhere
else.

**Example \#1 <span class="function">preg\_replace\_callback</span> and
anonymous function**

``` php
<?php
/* a unix-style command line filter to convert uppercase
 * letters at the beginning of paragraphs to lowercase */
$fp = fopen("php://stdin", "r") or die("can't read stdin");
while (!feof($fp)) {
    $line = fgets($fp);
    $line = preg_replace_callback(
        '|<p>\s*\w|',
        function ($matches) {
            return strtolower($matches[0]);
        },
        $line
    );
    echo $line;
}
fclose($fp);
?>
```

`subject`  
The string or an array with strings to search and replace.

`limit`  
The maximum possible replacements for each pattern in each `subject`
string. Defaults to *-1* (no limit).

`count`  
If specified, this variable will be filled with the number of
replacements done.

### Return Values

<span class="function">preg\_replace\_callback</span> returns an array
if the `subject` parameter is an array, or a string otherwise. On errors
the return value is **`NULL`**

If matches are found, the new subject will be returned, otherwise
`subject` will be returned unchanged.

### Changelog

| Version | Description                     |
|---------|---------------------------------|
| 5.1.0   | The `count` parameter was added |

### Examples

**Example \#2 <span class="function">preg\_replace\_callback</span>
example**

``` php
<?php
// this text was used in 2002
// we want to get this up to date for 2003
$text = "April fools day is 04/01/2002\n";
$text.= "Last christmas was 12/24/2001\n";
// the callback function
function next_year($matches)
{
  // as usual: $matches[0] is the complete match
  // $matches[1] the match for the first subpattern
  // enclosed in '(...)' and so on
  return $matches[1].($matches[2]+1);
}
echo preg_replace_callback(
            "|(\d{2}/\d{2}/)(\d{4})|",
            "next_year",
            $text);

?>
```

The above example will output:

    April fools day is 04/01/2003
    Last christmas was 12/24/2002

**Example \#3 <span class="function">preg\_replace\_callback</span>
using recursive structure to handle encapsulated BB code**

``` php
<?php
$input = "plain [indent] deep [indent] deeper [/indent] deep [/indent] plain";

function parseTagsRecursive($input)
{

    $regex = '#\[indent]((?:[^[]|\[(?!/?indent])|(?R))+)\[/indent]#';

    if (is_array($input)) {
        $input = '<div style="margin-left: 10px">'.$input[1].'</div>';
    }

    return preg_replace_callback($regex, 'parseTagsRecursive', $input);
}

$output = parseTagsRecursive($input);

echo $output;
?>
```

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">preg\_replace\_callback\_array</span>
-   <span class="function">preg\_quote</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">preg\_last\_error</span>
-   <a href="/functions/anonymous.html" class="link">Anonymous functions</a>
-   information about the
    <a href="/language/pseudo-types.html#language.types.callback" class="link">callback</a>
    type

preg\_replace
=============

Perform a regular expression search and replace

### Description

<span class="type">mixed</span> <span
class="methodname">preg\_replace</span> ( <span
class="methodparam"><span class="type">mixed</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$subject`</span> \[, <span
class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `&$count`</span> \]\]
)

Searches `subject` for matches to `pattern` and replaces them with
`replacement`.

### Parameters

`pattern`  
The pattern to search for. It can be either a string or an array with
strings.

Several
<a href="/pcre/pattern.html#Possible%20modifiers%20in%20regex%20patterns" class="link">PCRE modifiers</a>
are also available.

`replacement`  
The string or an array with strings to replace. If this parameter is a
string and the `pattern` parameter is an array, all patterns will be
replaced by that string. If both `pattern` and `replacement` parameters
are arrays, each `pattern` will be replaced by the `replacement`
counterpart. If there are fewer elements in the `replacement` array than
in the `pattern` array, any extra `pattern`s will be replaced by an
empty string.

`replacement` may contain references of the form *\\<span
class="replaceable">n</span>* or *$<span class="replaceable">n</span>*,
with the latter form being the preferred one. Every such reference will
be replaced by the text captured by the <span
class="replaceable">n</span>'th parenthesized pattern. <span
class="replaceable">n</span> can be from 0 to 99, and *\\0* or *$0*
refers to the text matched by the whole pattern. Opening parentheses are
counted from left to right (starting from 1) to obtain the number of the
capturing subpattern. Note that backslashes in <span
class="type">string</span> literals may require to be escaped.

When working with a replacement pattern where a backreference is
immediately followed by another number (i.e.: placing a literal number
immediately after a matched pattern), you cannot use the familiar *\\1*
notation for your backreference. *\\11*, for example, would confuse
<span class="function">preg\_replace</span> since it does not know
whether you want the *\\1* backreference followed by a literal *1*, or
the *\\11* backreference followed by nothing. In this case the solution
is to use *${1}1*. This creates an isolated *$1* backreference, leaving
the *1* as a literal.

When using the deprecated *e* modifier, this function escapes some
characters (namely *'*, *"*, *\\* and NULL) in the strings that replace
the backreferences. This is done to ensure that no syntax errors arise
from backreference usage with either single or double quotes (e.g.
*'strlen(\\'$1\\')+strlen("$2")'*). Make sure you are aware of PHP's
<a href="/language/types/string.html" class="link">string syntax</a> to
know exactly how the interpreted string will look.

`subject`  
The string or an array with strings to search and replace.

If `subject` is an array, then the search and replace is performed on
every entry of `subject`, and the return value is an array as well.

`limit`  
The maximum possible replacements for each pattern in each `subject`
string. Defaults to *-1* (no limit).

`count`  
If specified, this variable will be filled with the number of
replacements done.

### Return Values

<span class="function">preg\_replace</span> returns an array if the
`subject` parameter is an array, or a string otherwise.

If matches are found, the new `subject` will be returned, otherwise
`subject` will be returned unchanged or **`NULL`** if an error occurred.

### Errors/Exceptions

As of PHP 5.5.0 **`E_DEPRECATED`** level error is emitted when passing
in the "\\e" modifier. As of PHP 7.0.0 using the "\\e" modifier is an
error; an **`E_WARNING`** is emitted in this case.

### Changelog

| Version | Description                                                                                                                                                                                                                                 |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.0.0   | Support for the */e* modifier has been removed. Use <span class="function">preg\_replace\_callback</span> instead.                                                                                                                          |
| 5.5.0   | The */e* modifier is deprecated. Use <span class="function">preg\_replace\_callback</span> instead. See the <a href="/pcre/pattern.html#" class="link">PREG_REPLACE_EVAL</a> documentation for additional information about security risks. |
| 5.1.0   | Added the `count` parameter                                                                                                                                                                                                                 |

### Examples

**Example \#1 Using backreferences followed by numeric literals**

``` php
<?php
$string = 'April 15, 2003';
$pattern = '/(\w+) (\d+), (\d+)/i';
$replacement = '${1}1,$3';
echo preg_replace($pattern, $replacement, $string);
?>
```

The above example will output:

    April1,2003

**Example \#2 Using indexed arrays with <span
class="function">preg\_replace</span>**

``` php
<?php
$string = 'The quick brown fox jumps over the lazy dog.';
$patterns = array();
$patterns[0] = '/quick/';
$patterns[1] = '/brown/';
$patterns[2] = '/fox/';
$replacements = array();
$replacements[2] = 'bear';
$replacements[1] = 'black';
$replacements[0] = 'slow';
echo preg_replace($patterns, $replacements, $string);
?>
```

The above example will output:

    The bear black slow jumps over the lazy dog.

By ksorting patterns and replacements, we should get what we wanted.

``` php
<?php
ksort($patterns);
ksort($replacements);
echo preg_replace($patterns, $replacements, $string);
?>
```

The above example will output:

    The slow black bear jumps over the lazy dog.

**Example \#3 Replacing several values**

``` php
<?php
$patterns = array ('/(19|20)(\d{2})-(\d{1,2})-(\d{1,2})/',
                   '/^\s*{(\w+)}\s*=/');
$replace = array ('\3/\4/\1\2', '$\1 =');
echo preg_replace($patterns, $replace, '{startDate} = 1999-5-27');
?>
```

The above example will output:

    $startDate = 5/27/1999

**Example \#4 Strip whitespace**

This example strips excess whitespace from a string.

``` php
<?php
$str = 'foo   o';
$str = preg_replace('/\s\s+/', ' ', $str);
// This will be 'foo o' now
echo $str;
?>
```

**Example \#5 Using the `count` parameter**

``` php
<?php
$count = 0;

echo preg_replace(array('/\d/', '/\s/'), '*', 'xp 4 to', -1 , $count);
echo $count; //3
?>
```

The above example will output:

    xp***to
    3

### Notes

> **Note**:
>
> When using arrays with `pattern` and `replacement`, the keys are
> processed in the order they appear in the array. This is *not
> necessarily* the same as the numerical index order. If you use indexes
> to identify which `pattern` should be replaced by which `replacement`,
> you should perform a <span class="function">ksort</span> on each array
> prior to calling <span class="function">preg\_replace</span>.

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">preg\_quote</span>
-   <span class="function">preg\_filter</span>
-   <span class="function">preg\_match</span>
-   <span class="function">preg\_replace\_callback</span>
-   <span class="function">preg\_split</span>
-   <span class="function">preg\_last\_error</span>

preg\_split
===========

Split string by a regular expression

### Description

<span class="type">array</span> <span
class="methodname">preg\_split</span> ( <span class="methodparam"><span
class="type">string</span> `$pattern`</span> , <span
class="methodparam"><span class="type">string</span> `$subject`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$limit`<span class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \]\] )

Split the given string by a regular expression.

### Parameters

`pattern`  
The pattern to search for, as a string.

`subject`  
The input string.

`limit`  
If specified, then only substrings up to `limit` are returned with the
rest of the string being placed in the last substring. A `limit` of -1
or 0 means "no limit" and, as is standard across PHP, you can use
**`NULL`** to skip to the `flags` parameter.

`flags`  
`flags` can be any combination of the following flags (combined with the
*\|* bitwise operator):

**`PREG_SPLIT_NO_EMPTY`**  
<span class="simpara"> If this flag is set, only non-empty pieces will
be returned by <span class="function">preg\_split</span>. </span>

**`PREG_SPLIT_DELIM_CAPTURE`**  
<span class="simpara"> If this flag is set, parenthesized expression in
the delimiter pattern will be captured and returned as well. </span>

**`PREG_SPLIT_OFFSET_CAPTURE`**  
If this flag is set, for every occurring match the appendant string
offset will also be returned. Note that this changes the return value in
an array where every element is an array consisting of the matched
string at offset *0* and its string offset into `subject` at offset *1*.

### Return Values

Returns an array containing substrings of `subject` split along
boundaries matched by `pattern`, or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">preg\_split</span> example : Get
the parts of a search string**

``` php
<?php
// split the phrase by any number of commas or space characters,
// which include " ", \r, \t, \n and \f
$keywords = preg_split("/[\s,]+/", "hypertext language, programming");
print_r($keywords);
?>
```

The above example will output:

    Array
    (
        [0] => hypertext
        [1] => language
        [2] => programming
    )

**Example \#2 Splitting a string into component characters**

``` php
<?php
$str = 'string';
$chars = preg_split('//', $str, -1, PREG_SPLIT_NO_EMPTY);
print_r($chars);
?>
```

The above example will output:

    Array
    (
        [0] => s
        [1] => t
        [2] => r
        [3] => i
        [4] => n
        [5] => g
    )

**Example \#3 Splitting a string into matches and their offsets**

``` php
<?php
$str = 'hypertext language programming';
$chars = preg_split('/ /', $str, -1, PREG_SPLIT_OFFSET_CAPTURE);
print_r($chars);
?>
```

The above example will output:

    Array
    (
        [0] => Array
            (
                [0] => hypertext
                [1] => 0
            )

        [1] => Array
            (
                [0] => language
                [1] => 10
            )

        [2] => Array
            (
                [0] => programming
                [1] => 19
            )

    )

### Notes

**Tip**

If you don't need the power of regular expressions, you can choose
faster (albeit simpler) alternatives like <span
class="function">explode</span> or <span
class="function">str\_split</span>.

**Tip**

If matching fails, an array with a single element containing the input
string will be returned.

### See Also

-   <a href="/pcre/pattern.html" class="link">PCRE Patterns</a>
-   <span class="function">preg\_quote</span>
-   <span class="function">implode</span>
-   <span class="function">preg\_match</span>
-   <span class="function">preg\_match\_all</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">preg\_last\_error</span>

**Table of Contents**

-   [preg\_filter](/ref/pcre.html#preg_filter) — Perform a regular
    expression search and replace
-   [preg\_grep](/ref/pcre.html#preg_grep) — Return array entries that
    match the pattern
-   [preg\_last\_error](/ref/pcre.html#preg_last_error) — Returns the
    error code of the last PCRE regex execution
-   [preg\_match\_all](/ref/pcre.html#preg_match_all) — Perform a global
    regular expression match
-   [preg\_match](/ref/pcre.html#preg_match) — Perform a regular
    expression match
-   [preg\_quote](/ref/pcre.html#preg_quote) — Quote regular expression
    characters
-   [preg\_replace\_callback\_array](/ref/pcre.html#preg_replace_callback_array)
    — Perform a regular expression search and replace using callbacks
-   [preg\_replace\_callback](/ref/pcre.html#preg_replace_callback) —
    Perform a regular expression search and replace using a callback
-   [preg\_replace](/ref/pcre.html#preg_replace) — Perform a regular
    expression search and replace
-   [preg\_split](/ref/pcre.html#preg_split) — Split string by a regular
    expression

token\_get\_all
===============

Split given source into PHP tokens

### Description

<span class="type">array</span> <span
class="methodname">token\_get\_all</span> ( <span
class="methodparam"><span class="type">string</span> `$source`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = 0</span></span> \] )

<span class="function">token\_get\_all</span> parses the given `source`
string into PHP language tokens using the Zend engine's lexical scanner.

For a list of parser tokens, see
<a href="/tokens.html" class="xref">List of Parser Tokens</a>, or use
<span class="function">token\_name</span> to translate a token value
into its string representation.

### Parameters

`source`  
The PHP source to parse.

`flags`  
Valid flags:

-   <span class="simpara"> **`TOKEN_PARSE`** - Recognises the ability to
    use reserved words in specific contexts. </span>

### Return Values

An array of token identifiers. Each individual token identifier is
either a single character (i.e.: *;*, *.*, *\>*, *!*, etc...), or a
three element array containing the token index in element 0, the string
content of the original token in element 1 and the line number in
element 2.

### Changelog

| Version | Description                                                                 |
|---------|-----------------------------------------------------------------------------|
| 7.0.0   | Added the optional `flags` parameter along with the **`TOKEN_PARSE`** flag. |
| 5.2.2   | Line numbers are returned in element 2                                      |

### Examples

**Example \#1 <span class="function">token\_get\_all</span> example**

``` php
<?php
$tokens = token_get_all('<?php echo; ?>');

foreach ($tokens as $token) {
    if (is_array($token)) {
        echo "Line {$token[2]}: ", token_name($token[0]), " ('{$token[1]}')", PHP_EOL;
    }
}
?>
```

The above example will output something similar to:

    Line 1: T_OPEN_TAG ('<?php ')
    Line 1: T_ECHO ('echo')
    Line 1: T_WHITESPACE (' ')
    Line 1: T_CLOSE_TAG ('?>')

**Example \#2 <span class="function">token\_get\_all</span> incorrect
usage example**

``` php
<?php
$tokens = token_get_all('/* comment */');

foreach ($tokens as $token) {
    if (is_array($token)) {
        echo "Line {$token[2]}: ", token_name($token[0]), " ('{$token[1]}')", PHP_EOL;
    }
}
?>
```

The above example will output something similar to:

    Line 1: T_INLINE_HTML ('/* comment */')

Note in the previous example that the string is parsed as
**`T_INLINE_HTML`** rather than the expected **`T_COMMENT`**. This is
because no open tag was used in the code provided. This would be
equivalent to putting a comment outside of the PHP tags in a normal
file.

**Example \#3 <span class="function">token\_get\_all</span> on a class
using a reserved word example**

``` php
<?php

$source = <<<'code'
<?php

class A
{
    const PUBLIC = 1;
}
code;

$tokens = token_get_all($source, TOKEN_PARSE);

foreach ($tokens as $token) {
    if (is_array($token)) {
        echo token_name($token[0]) , PHP_EOL;
    }
}
?>
```

The above example will output something similar to:

    T_OPEN_TAG
    T_WHITESPACE
    T_CLASS
    T_WHITESPACE
    T_STRING
    T_CONST
    T_WHITESPACE
    T_STRING
    T_LNUMBER

Without the **`TOKEN_PARSE`** flag, the penultimate token
(**`T_STRING`**) would have been **`T_PUBLIC`**.

### See Also

-   <span class="function">token\_name</span>

token\_name
===========

Get the symbolic name of a given PHP token

### Description

<span class="type">string</span> <span
class="methodname">token\_name</span> ( <span class="methodparam"><span
class="type">int</span> `$token`</span> )

<span class="function">token\_name</span> gets the symbolic name for a
PHP `token` value.

### Parameters

`token`  
The token value.

### Return Values

The symbolic name of the given `token`.

### Examples

**Example \#1 <span class="function">token\_name</span> example**

``` php
<?php
// 260 is the token value for the T_EVAL token
echo token_name(260);        // -> "T_EVAL"

// a token constant maps to its own name
echo token_name(T_FUNCTION); // -> "T_FUNCTION"
?>
```

### See Also

-   <a href="/tokens.html" class="link">List of Parser Tokens</a>

**Table of Contents**

-   [token\_get\_all](/ref/tokenizer.html#token_get_all) — Split given
    source into PHP tokens
-   [token\_name](/ref/tokenizer.html#token_name) — Get the symbolic
    name of a given PHP token

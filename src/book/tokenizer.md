Tokenizer
=========

**Table of Contents**

-   [Introduction](/intro/tokenizer.html)
-   [Installing/Configuring](/tokenizer/setup.html)
    -   [Requirements](/tokenizer/setup.html#Requirements)
    -   [Installation](/tokenizer/setup.html#Installation)
    -   [Runtime
        Configuration](/tokenizer/setup.html#Runtime%20Configuration)
    -   [Resource Types](/tokenizer/setup.html#Resource%20Types)
-   [Predefined Constants](/tokenizer/constants.html)
-   [Examples](/tokenizer/examples.html)
-   [PhpToken](/class/phptoken.html) — The PhpToken class
    -   [PhpToken::\_\_construct](/class/phptoken.html#PhpToken::__construct)
        — Returns a new PhpToken object
    -   [PhpToken::getTokenName](/class/phptoken.html#PhpToken::getTokenName)
        — Returns the name of the token.
    -   [PhpToken::is](/class/phptoken.html#PhpToken::is) — Tells
        whether the token is of given kind.
    -   [PhpToken::isIgnorable](/class/phptoken.html#PhpToken::isIgnorable)
        — Tells whether the token would be ignored by the PHP parser.
    -   [PhpToken::\_\_toString](/class/phptoken.html#PhpToken::__toString)
        — Returns the textual content of the token.
    -   [PhpToken::tokenize](/class/phptoken.html#PhpToken::tokenize) —
        Splits given source into PHP tokens, represented by PhpToken
        objects.
-   [Tokenizer Functions](/ref/tokenizer.html)
    -   [token\_get\_all](/ref/tokenizer.html#token_get_all) — Split
        given source into PHP tokens
    -   [token\_name](/ref/tokenizer.html#token_name) — Get the symbolic
        name of a given PHP token

Introduction
------------

This class provides an alternative to <span
class="function">token\_get\_all</span>. While the function returns
tokens either as a single-character string, or an array with a token ID,
token text and line number, <span
class="function">PhpToken::tokenize</span> normalizes all tokens into
PhpToken objects, which makes code operating on tokens more memory
efficient and readable.

Class synopsis
--------------

**PhpToken**

<span class="ooclass"> class **PhpToken** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span class="type">int</span> `$id`
;

<span class="modifier">public</span> <span class="type">string</span>
`$text` ;

<span class="modifier">public</span> <span class="type">int</span>
`$line` ;

<span class="modifier">public</span> <span class="type">int</span>
`$pos` ;

/\* Methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$id`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> \[,
<span class="methodparam"><span class="type">int</span> `$line`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$pos`<span
class="initializer"> = -1</span></span> \]\] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span> <span
class="methodname">getTokenName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">is</span> ( <span class="methodparam"><span
class="type"><span class="type">int</span><span
class="type">string</span><span class="type">array</span></span>
`$kind`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isIgnorable</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">tokenize</span> ( <span class="methodparam"><span
class="type">string</span> `$code`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \] )

}

Properties
----------

`id`  
One of the T\_\* constants, or an ASCII codepoint representing a
single-char token.

`text`  
The textual content of the token.

`line`  
The starting line number (1-based) of the token.

`pos`  
The starting position (0-based) in the tokenized string.

PhpToken::\_\_construct
=======================

Returns a new PhpToken object

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="methodname">PhpToken::\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$id`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> \[,
<span class="methodparam"><span class="type">int</span> `$line`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$pos`<span
class="initializer"> = -1</span></span> \]\] )

Returns a new PhpToken object

### Parameters

`id`  
One of the T\_\* constants (see
<a href="/tokens.html" class="xref">List of Parser Tokens</a>), or an
ASCII codepoint representing a single-char token.

`text`  
The textual content of the token.

`line`  
The starting line number (1-based) of the token.

`pos`  
The starting position (0-based) in the tokenized string.

### Return Values

Returns a new PhpToken instance.

### See Also

-   <span class="function">PhpToken::tokenize</span>

PhpToken::getTokenName
======================

Returns the name of the token.

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span> <span
class="methodname">PhpToken::getTokenName</span> ( <span
class="methodparam">void</span> )

Returns the name of the token.

### Parameters

This function has no parameters.

### Return Values

An ASCII character for single-char tokens, or one of T\_\* constant
names for known tokens (see
<a href="/tokens.html" class="xref">List of Parser Tokens</a>), or
**`null`** for unknown tokens.

### Examples

**Example \#1 <span class="function">PhpToken::getTokenName</span>
example**

``` php
<?php
// known token
$token = new PhpToken(T_ECHO, 'echo');
var_dump($token->getTokenName());   // -> string(6) "T_ECHO"

// single-char token
$token = new PhpToken(ord(';'), ';');
var_dump($token->getTokenName());   // -> string(1) ";"

// unknown token
$token = new PhpToken(10000 , "\0");
var_dump($token->getTokenName());   // -> NULL
```

### See Also

-   <span class="function">PhpToken::tokenize</span>
-   <span class="function">token\_name</span>

PhpToken::is
============

Tells whether the token is of given kind.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PhpToken::is</span> ( <span
class="methodparam"><span class="type"><span
class="type">int</span><span class="type">string</span><span
class="type">array</span></span> `$kind`</span> )

Tells whether the token is of given `kind`.

### Parameters

`kind`  
Either a single value to match the token's id or textual content, or an
array thereof.

### Return Values

A boolean value whether the token is of given kind.

### Examples

**Example \#1 <span class="function">PhpToken::is</span> example**

``` php
<?php
$token = new PhpToken(T_ECHO, 'echo');
var_dump($token->is(T_ECHO));        // -> bool(true)
var_dump($token->is('echo'));        // -> bool(true)
var_dump($token->is(T_FOREACH));     // -> bool(false)
var_dump($token->is('foreach'));     // -> bool(false)
```

**Example \#2 Usage with array**

``` php
<?php
function isClassType(PhpToken $token): bool {
    return $token->is([T_CLASS, T_INTERFACE, T_TRAIT]);
}

$interface = new PhpToken(T_INTERFACE, 'interface');
var_dump(isClassType($interface));   // -> bool(true)

$function = new PhpToken(T_FUNCTION, 'function');
var_dump(isClassType($function));    // -> bool(false)
```

### See Also

-   <span class="function">token\_name</span>

PhpToken::isIgnorable
=====================

Tells whether the token would be ignored by the PHP parser.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PhpToken::isIgnorable</span> ( <span
class="methodparam">void</span> )

Tells whether the token would be ignored by the PHP parser.

### Parameters

This function has no parameters.

### Return Values

A boolean value whether the token would be ignored by the PHP parser
(such as whitespace or comments).

### Examples

**Example \#1 <span class="function">PhpToken::isIgnorable</span>
example**

``` php
<?php
$echo = new PhpToken(T_ECHO, 'echo');
var_dump($echo->isIgnorable());   // -> bool(false)

$space = new PhpToken(T_WHITESPACE, ' ');
var_dump($space->isIgnorable());  // -> bool(true)
```

### See Also

-   <span class="function">PhpToken::tokenize</span>

PhpToken::\_\_toString
======================

Returns the textual content of the token.

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">PhpToken::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns the textual content of the token.

### Parameters

This function has no parameters.

### Return Values

A textual content of the token.

### Examples

**Example \#1 <span class="function">PhpToken::\_\_toString</span>
example**

``` php
<?php
$token = new PhpToken(T_ECHO, 'echo');
echo $token;
```

The above examples will output:

    echo

### See Also

-   <span class="function">token\_name</span>

PhpToken::tokenize
==================

Splits given source into PHP tokens, represented by PhpToken objects.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">PhpToken::tokenize</span> ( <span
class="methodparam"><span class="type">string</span> `$code`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \] )

Returns an array of PhpToken objects representing given `code`.

### Parameters

`code`  
The PHP source to parse.

`flags`  
Valid flags:

-   <span class="simpara"> **`TOKEN_PARSE`** - Recognises the ability to
    use reserved words in specific contexts. </span>

### Return Values

An array of PHP tokens represented by instances of PhpToken or its
descendants. This method returns <span class="type">static\[\]</span> so
that PhpToken can be seamlessly extended.

### Examples

**Example \#1 <span class="function">PhpToken::tokenize</span> example**

``` php
<?php
$tokens = PhpToken::tokenize('<?php echo; ?>');

foreach ($tokens as $token) {
    echo "Line {$token->line}: {$token->getTokenName()} ('{$token->text}')", PHP_EOL;
}
```

The above examples will output:

    Line 1: T_OPEN_TAG ('<?php ')
    Line 1: T_ECHO ('echo')
    Line 1: ; (';')
    Line 1: T_WHITESPACE (' ')
    Line 1: T_CLOSE_TAG ('?>')

**Example \#2 Extending PhpToken**

``` php
<?php

class MyPhpToken extends PhpToken {
    public function getUpperText() {
        return strtoupper($this->text);
    }
}

$tokens = MyPhpToken::tokenize('<?php echo; ?>');
echo "'{$tokens[0]->getUpperText()}'";
```

The above examples will output:

    '<?PHP '

### See Also

-   <span class="function">token\_get\_all</span>

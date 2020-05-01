Parsing and lexing
==================

**Table of Contents**

-   [Introduction](/intro/parle.html)
-   [Installing/Configuring](/parle/setup.html)
    -   [Requirements](/parle/setup.html#Requirements)
    -   [Installation](/parle/setup.html#Installation)
-   [Predefined Constants](/parle/constants.html)
-   [Pattern matching](/parle/pattern/matching.html) — Parle pattern
    matching
    -   [Character
        representations](/parle/pattern/matching.html#Character%20representations)
    -   [Character
        classes](/parle/pattern/matching.html#Character%20classes)
    -   [Unicode character
        classes](/parle/pattern/matching.html#Unicode%20character%20classes)
    -   [Alternation and
        repetition](/parle/pattern/matching.html#Alternation%20and%20repetition)
    -   [Anchors](/parle/pattern/matching.html#Anchors)
    -   [Grouping](/parle/pattern/matching.html#Grouping)
-   [Examples](/parle/examples.html)
    -   [Lexer examples](/parle/examples.html#Lexer%20examples)
    -   [Parser examples](/parle/examples.html#Parser%20examples)
-   [Parle\\Lexer](/class/parle-lexer.html) — The Parle\\Lexer class
    -   [Parle\\Lexer::advance](/class/parle-lexer.html#Parle\Lexer::advance)
        — Process next lexer rule
    -   [Parle\\Lexer::build](/class/parle-lexer.html#Parle\Lexer::build)
        — Finalize the lexer rule set
    -   [Parle\\Lexer::callout](/class/parle-lexer.html#Parle\Lexer::callout)
        — Define token callback
    -   [Parle\\Lexer::consume](/class/parle-lexer.html#Parle\Lexer::consume)
        — Pass the data for processing
    -   [Parle\\Lexer::dump](/class/parle-lexer.html#Parle\Lexer::dump)
        — Dump the state machine
    -   [Parle\\Lexer::getToken](/class/parle-lexer.html#Parle\Lexer::getToken)
        — Retrieve the current token
    -   [Parle\\Lexer::insertMacro](/class/parle-lexer.html#Parle\Lexer::insertMacro)
        — Insert regex macro
    -   [Parle\\Lexer::push](/class/parle-lexer.html#Parle\Lexer::push)
        — Add a lexer rule
    -   [Parle\\Lexer::reset](/class/parle-lexer.html#Parle\Lexer::reset)
        — Reset lexer
-   [Parle\\RLexer](/class/parle-rlexer.html) — The Parle\\RLexer class
    -   [Parle\\RLexer::advance](/class/parle-rlexer.html#Parle\RLexer::advance)
        — Process next lexer rule
    -   [Parle\\RLexer::build](/class/parle-rlexer.html#Parle\RLexer::build)
        — Finalize the lexer rule set
    -   [Parle\\RLexer::callout](/class/parle-rlexer.html#Parle\RLexer::callout)
        — Define token callback
    -   [Parle\\RLexer::consume](/class/parle-rlexer.html#Parle\RLexer::consume)
        — Pass the data for processing
    -   [Parle\\RLexer::dump](/class/parle-rlexer.html#Parle\RLexer::dump)
        — Dump the state machine
    -   [Parle\\RLexer::getToken](/class/parle-rlexer.html#Parle\RLexer::getToken)
        — Retrieve the current token
    -   [Parle\\RLexer::insertMacro](/class/parle-rlexer.html#Parle\RLexer::insertMacro)
        — Insert regex macro
    -   [Parle\\RLexer::push](/class/parle-rlexer.html#Parle\RLexer::push)
        — Add a lexer rule
    -   [Parle\\RLexer::pushState](/class/parle-rlexer.html#Parle\RLexer::pushState)
        — Push a new start state
    -   [Parle\\RLexer::reset](/class/parle-rlexer.html#Parle\RLexer::reset)
        — Reset lexer
-   [Parle\\Parser](/class/parle-parser.html) — The Parle\\Parser class
    -   [Parle\\Parser::advance](/class/parle-parser.html#Parle\Parser::advance)
        — Process next parser rule
    -   [Parle\\Parser::build](/class/parle-parser.html#Parle\Parser::build)
        — Finalize the grammar rules
    -   [Parle\\Parser::consume](/class/parle-parser.html#Parle\Parser::consume)
        — Consume the data for processing
    -   [Parle\\Parser::dump](/class/parle-parser.html#Parle\Parser::dump)
        — Dump the grammar
    -   [Parle\\Parser::errorInfo](/class/parle-parser.html#Parle\Parser::errorInfo)
        — Retrieve the error information
    -   [Parle\\Parser::left](/class/parle-parser.html#Parle\Parser::left)
        — Declare a token with left-associativity
    -   [Parle\\Parser::nonassoc](/class/parle-parser.html#Parle\Parser::nonassoc)
        — Declare a token with no associativity
    -   [Parle\\Parser::precedence](/class/parle-parser.html#Parle\Parser::precedence)
        — Declare a precedence rule
    -   [Parle\\Parser::push](/class/parle-parser.html#Parle\Parser::push)
        — Add a grammar rule
    -   [Parle\\Parser::reset](/class/parle-parser.html#Parle\Parser::reset)
        — Reset parser state
    -   [Parle\\Parser::right](/class/parle-parser.html#Parle\Parser::right)
        — Declare a token with right-associativity
    -   [Parle\\Parser::sigil](/class/parle-parser.html#Parle\Parser::sigil)
        — Retrieve a matching part of a rule
    -   [Parle\\Parser::token](/class/parle-parser.html#Parle\Parser::token)
        — Declare a token
    -   [Parle\\Parser::tokenId](/class/parle-parser.html#Parle\Parser::tokenId)
        — Get token id
    -   [Parle\\Parser::trace](/class/parle-parser.html#Parle\Parser::trace)
        — Trace the parser operation
    -   [Parle\\Parser::validate](/class/parle-parser.html#Parle\Parser::validate)
        — Validate input
-   [Parle\\RParser](/class/parle-rparser.html) — The Parle\\RParser
    class
    -   [Parle\\RParser::advance](/class/parle-rparser.html#Parle\RParser::advance)
        — Process next parser rule
    -   [Parle\\RParser::build](/class/parle-rparser.html#Parle\RParser::build)
        — Finalize the grammar rules
    -   [Parle\\RParser::consume](/class/parle-rparser.html#Parle\RParser::consume)
        — Consume the data for processing
    -   [Parle\\RParser::dump](/class/parle-rparser.html#Parle\RParser::dump)
        — Dump the grammar
    -   [Parle\\RParser::errorInfo](/class/parle-rparser.html#Parle\RParser::errorInfo)
        — Retrieve the error information
    -   [Parle\\RParser::left](/class/parle-rparser.html#Parle\RParser::left)
        — Declare a token with left-associativity
    -   [Parle\\RParser::nonassoc](/class/parle-rparser.html#Parle\RParser::nonassoc)
        — Declare a token with no associativity
    -   [Parle\\RParser::precedence](/class/parle-rparser.html#Parle\RParser::precedence)
        — Declare a precedence rule
    -   [Parle\\RParser::push](/class/parle-rparser.html#Parle\RParser::push)
        — Add a grammar rule
    -   [Parle\\RParser::reset](/class/parle-rparser.html#Parle\RParser::reset)
        — Reset parser state
    -   [Parle\\RParser::right](/class/parle-rparser.html#Parle\RParser::right)
        — Declare a token with right-associativity
    -   [Parle\\RParser::sigil](/class/parle-rparser.html#Parle\RParser::sigil)
        — Retrieve a matching part of a rule
    -   [Parle\\RParser::token](/class/parle-rparser.html#Parle\RParser::token)
        — Declare a token
    -   [Parle\\RParser::tokenId](/class/parle-rparser.html#Parle\RParser::tokenId)
        — Get token id
    -   [Parle\\RParser::trace](/class/parle-rparser.html#Parle\RParser::trace)
        — Trace the parser operation
    -   [Parle\\RParser::validate](/class/parle-rparser.html#Parle\RParser::validate)
        — Validate input
-   [Parle\\Stack](/class/parle-stack.html) — The Parle\\Stack class
    -   [Parle\\Stack::pop](/class/parle-stack.html#Parle\Stack::pop) —
        Pop an item from the stack
    -   [Parle\\Stack::push](/class/parle-stack.html#Parle\Stack::push)
        — Push an item into the stack
-   [Parle\\Token](/class/parle-token.html) — The Parle\\Token class
-   [Parle\\ErrorInfo](/class/parle-errorinfo.html) — The
    Parle\\ErrorInfo class
-   [Parle\\LexerException](/class/parle-lexerexception.html) — The
    Parle\\LexerException class
-   [Parle\\ParserException](/class/parle-parserexception.html) — The
    Parle\\ParserException class

Introduction
------------

Single state lexer class. Lexemes can be defined on the fly. If the
particular lexer instance is meant to be used with <span
class="classname">Parle\\Parser</span>, the token IDs need to be taken
from there. Otherwise, arbitrary token IDs can be supplied. This lexer
can give a certain performance advantage over <span
class="classname">Parle\\RLexer</span>, if no multiple states are
required. Note, that <span class="classname">Parle\\RParser</span> is
not compatible with this lexer.

Class synopsis
--------------

**Parle\\Lexer**

<span class="ooclass"> class **Parle\\Lexer** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Lexer::ICASE` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Lexer::DOT_NOT_LF` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Lexer::DOT_NOT_CRLF` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Lexer::SKIP_WS` <span class="initializer"> = 8</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Lexer::MATCH_ZERO_LEN` <span class="initializer"> = 16</span> ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">boolean</span>
`$bol` <span class="initializer"> = **`FALSE`**</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$flags` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$state` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$marker` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$cursor` <span class="initializer"> = 0</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">advance</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">build</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">callout</span> ( <span
class="methodparam"><span class="type">int</span> `$id`</span> , <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">consume</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">dump</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Parle\\Token</span> <span
class="methodname">getToken</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">insertMacro</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$regex`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">push</span> ( <span class="methodparam"><span
class="type">string</span> `$regex`</span> , <span
class="methodparam"><span class="type">int</span> `$id`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">reset</span> ( <span class="methodparam"><span
class="type">int</span> `$pos`</span> )

}

Predefined Constants
--------------------

**`Parle\Lexer::ICASE`**  

**`Parle\Lexer::DOT_NOT_LF`**  

**`Parle\Lexer::DOT_NOT_CRLF`**  

**`Parle\Lexer::SKIP_WS`**  

**`Parle\Lexer::MATCH_ZERO_LEN`**  

Properties
----------

`bol`  
Start of input flag.

`flags`  
Lexer flags.

`state`  
Current lexer state, readonly.

`marker`  
Position of the latest token match, readonly.

`cursor`  
Current input offset, readonly.

Parle\\Lexer::advance
=====================

Process next lexer rule

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Lexer::advance</span> ( <span
class="methodparam">void</span> )

Processes the next rule and prepares the resulting token data.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\Lexer::build
===================

Finalize the lexer rule set

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Lexer::build</span> ( <span
class="methodparam">void</span> )

Rules, previously added with <span
class="methodname">Parle\\Lexer::push</span> are finalized. This method
call has to be done after all the necessary rules was pushed. The rule
set becomes read only. The lexing can begin.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\Lexer::callout
=====================

Define token callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Lexer::callout</span> ( <span
class="methodparam"><span class="type">int</span> `$id`</span> , <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Define a callback to be invoked once lexer encounters a particular
token.

### Parameters

`id`  
Token id.

`callback`  
Callable to be invoked. The callable doesn't receive any arguments and
its return value is ignored.

### Return Values

No value is returned.

Parle\\Lexer::consume
=====================

Pass the data for processing

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Lexer::consume</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

Consume the data for lexing.

### Parameters

`data`  
Data to be lexed.

### Return Values

No value is returned.

Parle\\Lexer::dump
==================

Dump the state machine

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Lexer::dump</span> ( <span
class="methodparam">void</span> )

Dump the current state machine to stdout.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\Lexer::getToken
======================

Retrieve the current token

### Description

<span class="modifier">public</span> <span
class="type">Parle\\Token</span> <span
class="methodname">Parle\\Lexer::getToken</span> ( <span
class="methodparam">void</span> )

Retrieve the current token.

### Parameters

This function has no parameters.

### Return Values

Returns an instance of <span class="classname">Parle\\Token</span>.

Parle\\Lexer::insertMacro
=========================

Insert regex macro

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Lexer::insertMacro</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$regex`</span> )

Insert a regex macro, that can be later used as a shortcut and included
in other regular expressions.

### Parameters

`name`  
Name of the macros.

`regex`  
Regular expression.

### Return Values

No value is returned.

Parle\\Lexer::push
==================

Add a lexer rule

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Lexer::push</span> ( <span
class="methodparam"><span class="type">string</span> `$regex`</span> ,
<span class="methodparam"><span class="type">int</span> `$id`</span> )

Push a pattern for lexeme recognition.

### Parameters

`regex`  
Regular expression used for token matching.

`id`  
Token id. If the lexer instance is meant to be used standalone, this can
be an arbitrary number. If the lexer instance is going to be passed to
the parser, it has to be an id returned by <span
class="methodname">Parle\\Parser::tokenid</span>.

### Return Values

No value is returned.

Parle\\Lexer::reset
===================

Reset lexer

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Lexer::reset</span> ( <span
class="methodparam"><span class="type">int</span> `$pos`</span> )

Reset lexing optionally supplying the desired offset.

### Parameters

`pos`  
Reset position.

### Return Values

No value is returned.

Introduction
------------

Multistate lexer class. Lexemes can be defined on the fly. If the
particular lexer instance is meant to be used with <span
class="classname">Parle\\RParser</span>, the token IDs need to be taken
from there. Otherwise, arbitrary token IDs can be supplied. Note, that
<span class="classname">Parle\\Parser</span> is not compatible with this
lexer.

Class synopsis
--------------

**Parle\\RLexer**

<span class="ooclass"> class **Parle\\RLexer** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RLexer::ICASE` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RLexer::DOT_NOT_LF` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RLexer::DOT_NOT_CRLF` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RLexer::SKIP_WS` <span class="initializer"> = 8</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RLexer::MATCH_ZERO_LEN` <span class="initializer"> = 16</span> ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">boolean</span>
`$bol` <span class="initializer"> = **`FALSE`**</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$flags` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$state` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$marker` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$cursor` <span class="initializer"> = 0</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">advance</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">build</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">callout</span> ( <span
class="methodparam"><span class="type">int</span> `$id`</span> , <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">consume</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">dump</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Parle\\Token</span> <span
class="methodname">getToken</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">insertMacro</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$regex`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">push</span> ( <span class="methodparam"><span
class="type">string</span> `$regex`</span> , <span
class="methodparam"><span class="type">int</span> `$id`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">push</span> ( <span class="methodparam"><span
class="type">string</span> `$state`</span> , <span
class="methodparam"><span class="type">string</span> `$regex`</span> ,
<span class="methodparam"><span class="type">int</span> `$id`</span> ,
<span class="methodparam"><span class="type">string</span>
`$newState`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">push</span> ( <span class="methodparam"><span
class="type">string</span> `$state`</span> , <span
class="methodparam"><span class="type">string</span> `$regex`</span> ,
<span class="methodparam"><span class="type">string</span>
`$newState`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">pushState</span> ( <span class="methodparam"><span
class="type">string</span> `$state`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">reset</span> ( <span class="methodparam"><span
class="type">int</span> `$pos`</span> )

}

Predefined Constants
--------------------

**`Parle\RLexer::ICASE`**  

**`Parle\RLexer::DOT_NOT_LF`**  

**`Parle\RLexer::DOT_NOT_CRLF`**  

**`Parle\RLexer::SKIP_WS`**  

**`Parle\RLexer::MATCH_ZERO_LEN`**  

Properties
----------

`bol`  
Start of input flag.

`flags`  
Lexer flags.

`state`  
Current lexer state, readonly.

`marker`  
Position of the latest token match, readonly.

`cursor`  
Current input offset, readonly.

Parle\\RLexer::advance
======================

Process next lexer rule

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::advance</span> ( <span
class="methodparam">void</span> )

Processes the next rule and prepares the resulting token data.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\RLexer::build
====================

Finalize the lexer rule set

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::build</span> ( <span
class="methodparam">void</span> )

Rules, previously added with <span
class="methodname">Parle\\RLexer::push</span> are finalized. This method
call has to be done after all the necessary rules was pushed. The rule
set becomes read only. The lexing can begin.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\RLexer::callout
======================

Define token callback

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::callout</span> ( <span
class="methodparam"><span class="type">int</span> `$id`</span> , <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Define a callback to be invoked once lexer encounters a particular
token.

### Parameters

`id`  
Token id.

`callback`  
Callable to be invoked. The callable doesn't receive any arguments and
its return value is ignored.

### Return Values

No value is returned.

Parle\\RLexer::consume
======================

Pass the data for processing

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::consume</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

Consume the data for lexing.

### Parameters

`data`  
Data to be lexed.

### Return Values

No value is returned.

Parle\\RLexer::dump
===================

Dump the state machine

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::dump</span> ( <span
class="methodparam">void</span> )

Dump the current state machine to stdout.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\RLexer::getToken
=======================

Retrieve the current token

### Description

<span class="modifier">public</span> <span
class="type">Parle\\Token</span> <span
class="methodname">Parle\\RLexer::getToken</span> ( <span
class="methodparam">void</span> )

Retrive the current token.

### Parameters

This function has no parameters.

### Return Values

Returns an instance of <span class="classname">Parle\\Token</span>.

Parle\\RLexer::insertMacro
==========================

Insert regex macro

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::insertMacro</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$regex`</span> )

Insert a regex macro, that can be later used as a shortcut and included
in other regular expressions.

### Parameters

`name`  
Name of the macros.

`regex`  
Regular expression.

### Return Values

No value is returned.

Parle\\RLexer::push
===================

Add a lexer rule

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::push</span> ( <span
class="methodparam"><span class="type">string</span> `$regex`</span> ,
<span class="methodparam"><span class="type">int</span> `$id`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::push</span> ( <span
class="methodparam"><span class="type">string</span> `$state`</span> ,
<span class="methodparam"><span class="type">string</span>
`$regex`</span> , <span class="methodparam"><span
class="type">int</span> `$id`</span> , <span class="methodparam"><span
class="type">string</span> `$newState`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::push</span> ( <span
class="methodparam"><span class="type">string</span> `$state`</span> ,
<span class="methodparam"><span class="type">string</span>
`$regex`</span> , <span class="methodparam"><span
class="type">string</span> `$newState`</span> )

Push a pattern for lexeme recognition.

A 'start state' and 'exit state' can be specified by using a suitable
signature.

### Parameters

`regex`  
Regular expression used for token matching.

`id`  
Token id. If the lexer instance is meant to be used standalone, this can
be an arbitrary number. If the lexer instance is going to be passed to
the parser, it has to be an id returned by <span
class="methodname">Parle\\RParser::tokenid</span>.

`state`  
State name. If '\*' is used as start state, then the rule is applied to
all lexer states.

`newState`  
New state name, after the rule was applied.

If '.' is specified as the exit state, then the lexer state is unchanged
when that rule matches. An exit state with '\>' before the name means
push. Use the signature without id for either continuation or to start
matching, when a continuation or recursion is required.

If '\<' is specified as exit state, it means pop. In that case, the
signature containing the id can be used to identify the match. Note that
even in the case an id is specified, the rule will finish first when all
the previous pushes popped.

### Return Values

No value is returned.

Parle\\RLexer::pushState
========================

Push a new start state

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Parle\\RLexer::pushState</span> ( <span
class="methodparam"><span class="type">string</span> `$state`</span> )

This lexer type can have more than one state machine. This allows you to
lex different tokens depending on context, thus allowing simple parsing
to take place. Once a state pushed, it can be used with a suitable <span
class="methodname">Parle\\RLexer::push</span> signature variant.

### Parameters

`state`  
Name of the state.

### Return Values

Parle\\RLexer::reset
====================

Reset lexer

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RLexer::reset</span> ( <span
class="methodparam"><span class="type">int</span> `$pos`</span> )

Reset lexing optionally supplying the desired offset.

### Parameters

`pos`  
Reset position.

### Return Values

No value is returned.

Introduction
------------

Parser class. Rules can be defined on the fly. Once finalized, a <span
class="classname">Parle\\Lexer</span> instance is required to deliver
the token stream.

Class synopsis
--------------

**Parle\\Parser**

<span class="ooclass"> class **Parle\\Parser** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Parser::ACTION_ERROR` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Parser::ACTION_SHIFT` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Parser::ACTION_REDUCE` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Parser::ACTION_GOTO` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Parser::ACTION_ACCEPT` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Parser::ERROR_SYNTAX` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Parser::ERROR_NON_ASSOCIATIVE` <span class="initializer"> =
1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Parser::ERROR_UNKNOWN_TOKEN` <span class="initializer"> =
2</span> ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">integer</span>
`$action` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$reduceId` <span class="initializer"> = 0</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">advance</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">build</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">consume</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">Parle\\Lexer</span>
`$lexer`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">dump</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Parle\\ErrorInfo</span> <span
class="methodname">errorInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">left</span> ( <span class="methodparam"><span
class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">nonassoc</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">precedence</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">push</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">string</span> `$rule`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">reset</span> (\[ <span
class="methodparam"><span class="type">int</span> `$tokenId`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">right</span> ( <span class="methodparam"><span
class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">sigil</span> ( <span class="methodparam"><span
class="type">int</span> `$idx`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">token</span> ( <span class="methodparam"><span
class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">tokenId</span> ( <span class="methodparam"><span
class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">trace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">validate</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">Parle\\Lexer</span>
`$lexer`</span> )

}

Predefined Constants
--------------------

**`Parle\Parser::ACTION_ERROR`**  

**`Parle\Parser::ACTION_SHIFT`**  

**`Parle\Parser::ACTION_REDUCE`**  

**`Parle\Parser::ACTION_GOTO`**  

**`Parle\Parser::ACTION_ACCEPT`**  

**`Parle\Parser::ERROR_SYNTAX`**  

**`Parle\Parser::ERROR_NON_ASSOCIATIVE`**  

**`Parle\Parser::ERROR_UNKNOWN_TOKEN`**  

Properties
----------

`action`  
Current parser action that matches one of the action class constants,
readonly.

`reduceId`  
Grammar rule id just processed in the reduce action. The value
corresponds either to a token or to a production id. Readonly.

Parle\\Parser::advance
======================

Process next parser rule

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::advance</span> ( <span
class="methodparam">void</span> )

Process next parser rule.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\Parser::build
====================

Finalize the grammar rules

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::build</span> ( <span
class="methodparam">void</span> )

Any tokens and grammar rules previously added are finalized. The rule
set becomes readonly and the parser is ready to start.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\Parser::consume
======================

Consume the data for processing

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::consume</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">Parle\\Lexer</span>
`$lexer`</span> )

Consume the data for parsing.

### Parameters

`data`  
Data to be parsed.

`lexer`  
A lexer object containing the lexing rules prepared for the particular
grammar.

### Return Values

No value is returned.

Parle\\Parser::dump
===================

Dump the grammar

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::dump</span> ( <span
class="methodparam">void</span> )

Dump the current grammar to stdout.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\Parser::errorInfo
========================

Retrieve the error information

### Description

<span class="modifier">public</span> <span
class="type">Parle\\ErrorInfo</span> <span
class="methodname">Parle\\Parser::errorInfo</span> ( <span
class="methodparam">void</span> )

Retrieve the error information in case <span
class="methodname">Parle\\Parser::action</span> returned the error
action.

### Parameters

This function has no parameters.

### Return Values

Returns an instance of <span class="classname">Parle\\ErrorInfo</span>.

Parle\\Parser::left
===================

Declare a token with left-associativity

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::left</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declare a terminal with left associativity.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\Parser::nonassoc
=======================

Declare a token with no associativity

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::nonassoc</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declare a terminal, that cannot appear more than once in the row.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\Parser::precedence
=========================

Declare a precedence rule

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::precedence</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declares a precedence rule for a fictitious terminal symbol. This rule
can be later used in the specific grammar rules.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\Parser::push
===================

Add a grammar rule

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Parle\\Parser::push</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$rule`</span> )

Push a grammar rule. The production id returned can be used later in the
parsing process to identify the rule matched.

### Parameters

`name`  
Rule name.

`rule`  
The rule to be added. The syntax is Bison compatible.

### Return Values

Returns <span class="type">integer</span> representing the rule index.

Parle\\Parser::reset
====================

Reset parser state

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::reset</span> (\[ <span
class="methodparam"><span class="type">int</span> `$tokenId`</span> \] )

Reset parser state using the given token id.

### Parameters

`tokenId`  
Token id.

### Return Values

No value is returned.

Parle\\Parser::right
====================

Declare a token with right-associativity

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::right</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declare a terminal with right associativity.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\Parser::sigil
====================

Retrieve a matching part of a rule

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Parle\\Parser::sigil</span> ( <span
class="methodparam"><span class="type">int</span> `$idx`</span> )

Retrieve a part of the match by a rule. This method is equivalent to the
pseudo variable functionality in Bison.

### Parameters

`idx`  
Match index, zero based.

### Return Values

Returns a <span class="type">string</span> with the matched part.

Parle\\Parser::token
====================

Declare a token

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Parser::token</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declare a terminal to be used in the grammar.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\Parser::tokenId
======================

Get token id

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Parle\\Parser::tokenId</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Retrieve the id of the named token.

### Parameters

`tok`  
Name of the token as used in <span
class="methodname">Parle\\Parser::token</span>.

### Return Values

Returns <span class="type">integer</span> representing the token id.

Parle\\Parser::trace
====================

Trace the parser operation

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Parle\\Parser::trace</span> ( <span
class="methodparam">void</span> )

Retrieve the current parser operation description. This can be
especially useful for studying the parser and to optimize the grammar.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="type">string</span> with the trace information.

Parle\\Parser::validate
=======================

Validate input

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Parle\\Parser::validate</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">Parle\\Lexer</span>
`$lexer`</span> )

Validate an input string. The string is parsed internally, thus this
method is useful for the quick input validation.

### Parameters

`data`  
String to be validated.

`lexer`  
A lexer object containing the lexing rules prepared for the particular
grammar.

### Return Values

Returns <span class="type">boolean</span> witnessing whether the input
chimes or not with the defined rules.

Introduction
------------

Parser class. Rules can be defined on the fly. Once finalized, a <span
class="classname">Parle\\RLexer</span> instance is required to deliver
the token stream.

Class synopsis
--------------

**Parle\\RParser**

<span class="ooclass"> class **Parle\\RParser** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RParser::ACTION_ERROR` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RParser::ACTION_SHIFT` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RParser::ACTION_REDUCE` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RParser::ACTION_GOTO` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RParser::ACTION_ACCEPT` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RParser::ERROR_SYNTAX` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RParser::ERROR_NON_ASSOCIATIVE` <span class="initializer"> =
1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\RParser::ERROR_UNKNOWN_TOKEN` <span class="initializer"> =
2</span> ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">integer</span>
`$action` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$reduceId` <span class="initializer"> = 0</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">advance</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">build</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">consume</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">Parle\\RLexer</span>
`$rlexer`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">dump</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">Parle\\ErrorInfo</span> <span
class="methodname">errorInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">left</span> ( <span class="methodparam"><span
class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">nonassoc</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">precedence</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">push</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">string</span> `$rule`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">reset</span> (\[ <span
class="methodparam"><span class="type">int</span> `$tokenId`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">right</span> ( <span class="methodparam"><span
class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">sigil</span> (\[ <span
class="methodparam"><span class="type">int</span> `$idx`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">token</span> ( <span class="methodparam"><span
class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">tokenId</span> ( <span class="methodparam"><span
class="type">string</span> `$tok`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">trace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">validate</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">Parle\\RLexer</span>
`$lexer`</span> )

}

Predefined Constants
--------------------

**`Parle\RParser::ACTION_ERROR`**  

**`Parle\RParser::ACTION_SHIFT`**  

**`Parle\RParser::ACTION_REDUCE`**  

**`Parle\RParser::ACTION_GOTO`**  

**`Parle\RParser::ACTION_ACCEPT`**  

**`Parle\RParser::ERROR_SYNTAX`**  

**`Parle\RParser::ERROR_NON_ASSOCIATIVE`**  

**`Parle\RParser::ERROR_UNKNOWN_TOKEN`**  

Properties
----------

`action`  
Current parser action that matches one of the action class constants,
readonly.

`reduceId`  
Grammar rule id just processed in the reduce action. The value
corresponds either to a token or to a production id. Readonly.

Parle\\RParser::advance
=======================

Process next parser rule

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::advance</span> ( <span
class="methodparam">void</span> )

Prosess next parser rule.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\RParser::build
=====================

Finalize the grammar rules

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::build</span> ( <span
class="methodparam">void</span> )

Any tokens and grammar rules previously added are finalized. The rule
set becomes readonly and the parser is ready to start.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\RParser::consume
=======================

Consume the data for processing

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::consume</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">Parle\\RLexer</span>
`$rlexer`</span> )

Consume the data for parsing.

### Parameters

`data`  
Data to be parsed.

`lexer`  
A lexer object containing the lexing rules prepared for the particular
grammar.

### Return Values

No value is returned.

Parle\\RParser::dump
====================

Dump the grammar

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::dump</span> ( <span
class="methodparam">void</span> )

Dump the current grammar to stdout.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\RParser::errorInfo
=========================

Retrieve the error information

### Description

<span class="modifier">public</span> <span
class="type">Parle\\ErrorInfo</span> <span
class="methodname">Parle\\RParser::errorInfo</span> ( <span
class="methodparam">void</span> )

Retrieve the error information in case <span
class="methodname">Parle\\RParser::action</span> returned the error
action.

### Parameters

This function has no parameters.

### Return Values

Returns an instance of <span class="classname">Parle\\ErrorInfo</span>.

Parle\\RParser::left
====================

Declare a token with left-associativity

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::left</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declare a terminal with left associativity.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\RParser::nonassoc
========================

Declare a token with no associativity

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::nonassoc</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declare a terminal, that cannot appear more than once in the row.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\RParser::precedence
==========================

Declare a precedence rule

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::precedence</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declares a precedence rule for a fictious terminal symbol. This rule can
be later used in the specific grammar rules.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\RParser::push
====================

Add a grammar rule

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Parle\\RParser::push</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$rule`</span> )

Push a grammar rule. The production id returned can be used later in the
parsing process to identify the rule matched.

### Parameters

`name`  
Rule name.

`rule`  
The rule to be added. The syntax is Bison compatible.

### Return Values

Returns <span class="type">integer</span> representing the rule index.

Parle\\RParser::reset
=====================

Reset parser state

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::reset</span> (\[ <span
class="methodparam"><span class="type">int</span> `$tokenId`</span> \] )

Reset parser state using the given token id.

### Parameters

`tokenId`  
Token id.

### Return Values

No value is returned.

Parle\\RParser::right
=====================

Declare a token with right-associativity

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::right</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declare a terminal with right associativity.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\RParser::sigil
=====================

Retrieve a matching part of a rule

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Parle\\RParser::sigil</span> (\[ <span
class="methodparam"><span class="type">int</span> `$idx`</span> \] )

Retrieve a part of the match by a rule. This method is equivalent to the
pseudo variable functionality in Bison.

### Parameters

`idx`  
Match index, zero based.

### Return Values

Returns a <span class="type">string</span> with the matched part.

Parle\\RParser::token
=====================

Declare a token

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\RParser::token</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Declare a terminal to be used in the grammar.

### Parameters

`tok`  
Token name.

### Return Values

No value is returned.

Parle\\RParser::tokenId
=======================

Get token id

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">Parle\\RParser::tokenId</span> ( <span
class="methodparam"><span class="type">string</span> `$tok`</span> )

Retrieve the id of the named token.

### Parameters

`tok`  
Name of the token as used in <span
class="methodname">Parle\\RParser::token</span>.

### Return Values

Returns <span class="type">integer</span> representing the token id.

Parle\\RParser::trace
=====================

Trace the parser operation

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Parle\\RParser::trace</span> ( <span
class="methodparam">void</span> )

Retrieve the current parser operation description. This can be
especially useful to study the parser and to optimize the grammar.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="type">string</span> with the trace information.

Parle\\RParser::validate
========================

Validate input

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Parle\\RParser::validate</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">Parle\\RLexer</span>
`$lexer`</span> )

Validate an input string. The string is parsed internally, thus this
method is useful for the quick input validation.

### Parameters

`data`  
String to be validated.

`lexer`  
A lexer object containing the lexing rules prepared for the particular
grammar.

### Return Values

Returns <span class="type">boolean</span> whitnessing whether the input
chimes or not with the defined rules.

Introduction
------------

<span class="classname">Parle\\Stack</span> is a LIFO stack. The
elements are inserted and removed only from one end.

Class synopsis
--------------

**Parle\\Stack**

<span class="ooclass"> class **Parle\\Stack** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span class="type">boolean</span>
`$empty` <span class="initializer"> = **`TRUE`**</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$size` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">mixed</span>
`$top` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">pop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">push</span> ( <span class="methodparam"><span
class="type">mixed</span> `$item`</span> )

}

Properties
----------

`empty`  
Whether the stack is empty, readonly.

`size`  
Stack size, readonly.

`top`  
Element on the top of the stack.

Parle\\Stack::pop
=================

Pop an item from the stack

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Stack::pop</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

No value is returned.

Parle\\Stack::push
==================

Push an item into the stack

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Parle\\Stack::push</span> ( <span
class="methodparam"><span class="type">mixed</span> `$item`</span> )

### Parameters

`item`  
Variable to be pushed.

### Return Values

No value is returned.

Introduction
------------

This class represents a token. Lexer returns instances of this class.

Class synopsis
--------------

**Parle\\Token**

<span class="ooclass"> class **Parle\\Token** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Token::EOI` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Token::UNKNOWN` <span class="initializer"> = -1</span> ;

<span class="modifier">const</span> <span class="type">integer</span>
`Parle\Token::SKIP` <span class="initializer"> = -2</span> ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">integer</span>
`$id` ;

<span class="modifier">public</span> <span class="type">string</span>
`$value` ;

/\* Methods \*/

}

Properties
----------

`id`  
Token id.

`value`  
Token value.

Predefined Constants
--------------------

**`Parle\Token::EOI`**  
End of input token id.

**`Parle\Token::UNKNOWN`**  
Unknown token id.

**`Parle\Token::SKIP`**  
Skip token id.

Introduction
------------

The class represents detailed error information as supplied by <span
class="methodname">Parle\\Parser::errorInfo</span>

Class synopsis
--------------

**Parle\\ErrorInfo**

<span class="ooclass"> class **Parle\\ErrorInfo** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span class="type">integer</span>
`$id` ;

<span class="modifier">public</span> <span class="type">integer</span>
`$position` ;

<span class="modifier">public</span> <span class="type">mixed</span>
`$token` ;

/\* Methods \*/

}

Properties
----------

`id`  
Error id.

`position`  
Position in the input, where the error occurred.

`token`  
If applicable - the <span class="classname">Parle\\Token</span> related
to the error, otherwise **`NULL`**.

Introduction
------------

Class synopsis
--------------

**Parle\\LexerException**

<span class="ooclass"> class **Parle\\LexerException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> <span class="oointerface">implements <span
class="interfacename">Throwable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

Class synopsis
--------------

**Parle\\ParserException**

<span class="ooclass"> class **Parle\\ParserException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> <span class="oointerface">implements <span
class="interfacename">Throwable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Backward incompatible changes
-----------------------------

### Changes to error and exception handling

Many fatal and recoverable fatal errors have been converted to
exceptions in PHP 7. These error exceptions inherit from the <span
class="classname">Error</span> class, which itself implements the <span
class="classname">Throwable</span> interface (the new base interface all
exceptions inherit).

This means that custom error handlers may no longer be triggered because
exceptions may be thrown instead (causing new fatal errors for uncaught
<span class="classname">Error</span> exceptions).

A fuller description of how errors operate in PHP 7 can be found
<a href="/language/errors/php7.html" class="link">on the PHP 7 errors page</a>.
This migration guide will merely enumerate the changes that affect
backward compatibility.

#### <span class="function">set\_exception\_handler</span> is no longer guaranteed to receive <span class="classname">Exception</span> objects

Code that implements an exception handler registered with <span
class="function">set\_exception\_handler</span> using a type declaration
of <span class="classname">Exception</span> will cause a fatal error
when an <span class="classname">Error</span> object is thrown.

If the handler needs to work on both PHP 5 and 7, you should remove the
type declaration from the handler, while code that is being migrated to
work on PHP 7 exclusively can simply replace the <span
class="classname">Exception</span> type declaration with <span
class="classname">Throwable</span> instead.

``` php
<?php
// PHP 5 era code that will break.
function handler(Exception $e) { ... }
set_exception_handler('handler');

// PHP 5 and 7 compatible.
function handler($e) { ... }

// PHP 7 only.
function handler(Throwable $e) { ... }
?>
```

#### Internal constructors always throw exceptions on failure

Previously, some internal classes would return **`NULL`** or an unusable
object when the constructor failed. All internal classes will now throw
an <span class="classname">Exception</span> in this case in the same way
that user classes already had to.

#### Parse errors throw <span class="classname">ParseError</span>

Parser errors now throw a <span class="classname">ParseError</span>
object. Error handling for <span class="function">eval</span> should now
include a
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block that can handle this error.

#### E\_STRICT notices severity changes

All of the **`E_STRICT`** notices have been reclassified to other
levels. **`E_STRICT`** constant is retained, so calls like
*error\_reporting(E\_ALL\|E\_STRICT)* will not cause an error.

| Situation                                      | New level/behaviour               |
|------------------------------------------------|-----------------------------------|
| Indexing by a resource                         | **`E_NOTICE`**                    |
| Abstract static methods                        | Notice removed, triggers no error |
| "Redefining" a constructor                     | Notice removed, triggers no error |
| Signature mismatch during inheritance          | **`E_WARNING`**                   |
| Same (compatible) property in two used traits  | Notice removed, triggers no error |
| Accessing static property non-statically       | **`E_NOTICE`**                    |
| Only variables should be assigned by reference | **`E_NOTICE`**                    |
| Only variables should be passed by reference   | **`E_NOTICE`**                    |
| Calling non-static methods statically          | **`E_DEPRECATED`**                |

### Changes to variable handling

PHP 7 now uses an abstract syntax tree when parsing source files. This
has permitted many improvements to the language which were previously
impossible due to limitations in the parser used in earlier versions of
PHP, but has resulted in the removal of a few special cases for
consistency reasons, which has resulted in backward compatibility
breaks. These cases are detailed in this section.

#### Changes to the handling of indirect variables, properties, and methods

Indirect access to variables, properties, and methods will now be
evaluated strictly in left-to-right order, as opposed to the previous
mix of special cases. The table below shows how the order of evaluation
has changed.

| Expression            | PHP 5 interpretation    | PHP 7 interpretation    |
|-----------------------|-------------------------|-------------------------|
| `$$foo['bar']['baz']` | `${$foo['bar']['baz']}` | `($$foo)['bar']['baz']` |
| `$foo->$bar['baz']`   | `$foo->{$bar['baz']}`   | `($foo->$bar)['baz']`   |
| `$foo->$bar['baz']()` | `$foo->{$bar['baz']}()` | `($foo->$bar)['baz']()` |
| `Foo::$bar['baz']()`  | `Foo::{$bar['baz']}()`  | `(Foo::$bar)['baz']()`  |

Code that used the old right-to-left evaluation order must be rewritten
to explicitly use that evaluation order with curly braces (see the above
middle column). This will make the code both forwards compatible with
PHP 7.x and backwards compatible with PHP 5.x.

This also affects the
<a href="/language/variables/scope.html#language.variables.scope.global" class="link"><em>global</em></a>
keyword. The curly brace syntax can be used to emulate the previous
behaviour if required:

``` php
<?php
function f() {
    // Valid in PHP 5 only.
    global $$foo->bar;

    // Valid in PHP 5 and 7.
    global ${$foo->bar};
}
?>
```

#### Changes to <span class="function">list</span> handling

##### <span class="function">list</span> no longer assigns variables in reverse order

<span class="function">list</span> will now assign values to variables
in the order they are defined, rather than reverse order. In general,
this only affects the case where <span class="function">list</span> is
being used in conjunction with the array `[]` operator, as shown below:

``` php
<?php
list($a[], $a[], $a[]) = [1, 2, 3];
var_dump($a);
?>
```

Output of the above example in PHP 5:

    array(3) {
      [0]=>
      int(3)
      [1]=>
      int(2)
      [2]=>
      int(1)
    }

Output of the above example in PHP 7:

    array(3) {
      [0]=>
      int(1)
      [1]=>
      int(2)
      [2]=>
      int(3)
    }

In general, it is recommended not to rely on the order in which <span
class="function">list</span> assignments occur, as this is an
implementation detail that may change again in the future.

##### Empty <span class="function">list</span> assignments have been removed

<span class="function">list</span> constructs can no longer be empty.
The following are no longer allowed:

``` php
<?php
list() = $a;
list(,,) = $a;
list($x, list(), $y) = $a;
?>
```

##### <span class="function">list</span> cannot unpack <span class="type">string</span>s

<span class="function">list</span> can no longer unpack <span
class="type">string</span> variables. <span
class="function">str\_split</span> should be used instead.

#### Array ordering when elements are automatically created during by reference assignments has changed

The order of the elements in an array has changed when those elements
have been automatically created by referencing them in a by reference
assignment. For example:

``` php
<?php
$array = [];
$array["a"] =& $array["b"];
$array["b"] = 1;
var_dump($array);
?>
```

Output of the above example in PHP 5:

    array(2) {
      ["b"]=>
      &int(1)
      ["a"]=>
      &int(1)
    }

Output of the above example in PHP 7:

    array(2) {
      ["a"]=>
      &int(1)
      ["b"]=>
      &int(1)
    }

#### Parentheses around function arguments no longer affect behaviour

In PHP 5, using redundant parentheses around a function argument could
quiet strict standards warnings when the function argument was passed by
reference. The warning will now always be issued.

``` php
<?php
function getArray() {
    return [1, 2, 3];
}

function squareArray(array &$a) {
    foreach ($a as &$v) {
        $v **= 2;
    }
}

// Generates a warning in PHP 7.
squareArray((getArray()));
?>
```

The above example will output:

    Notice: Only variables should be passed by reference in /tmp/test.php on line 13

### Changes to <a href="/control-structures/foreach.html" class="link">foreach</a>

Minor changes have been made to the behaviour of the
<a href="/control-structures/foreach.html" class="link">foreach</a>
control structure, primarily around the handling of the internal array
pointer and modification of the array being iterated over.

#### <a href="/control-structures/foreach.html" class="link">foreach</a> no longer changes the internal array pointer

Prior to PHP 7, the internal array pointer was modified while an array
was being iterated over with
<a href="/control-structures/foreach.html" class="link">foreach</a>.
This is no longer the case, as shown in the following example:

``` php
<?php
$array = [0, 1, 2];
foreach ($array as &$val) {
    var_dump(current($array));
}
?>
```

Output of the above example in PHP 5:

    int(1)
    int(2)
    bool(false)

Output of the above example in PHP 7:

    int(0)
    int(0)
    int(0)

#### <a href="/control-structures/foreach.html" class="link">foreach</a> by-value operates on a copy of the array

When used in the default by-value mode,
<a href="/control-structures/foreach.html" class="link">foreach</a> will
now operate on a copy of the array being iterated rather than the array
itself. This means that changes to the array made during iteration will
not affect the values that are iterated.

#### <a href="/control-structures/foreach.html" class="link">foreach</a> by-reference has improved iteration behaviour

When iterating by-reference,
<a href="/control-structures/foreach.html" class="link">foreach</a> will
now do a better job of tracking changes to the array made during
iteration. For example, appending to an array while iterating will now
result in the appended values being iterated over as well:

``` php
<?php
$array = [0];
foreach ($array as &$val) {
    var_dump($val);
    $array[1] = 1;
}
?>
```

Output of the above example in PHP 5:

    int(0)

Output of the above example in PHP 7:

    int(0)
    int(1)

#### Iteration of non-<span class="classname">Traversable</span> objects

Iterating over a non-<span class="classname">Traversable</span> object
will now have the same behaviour as iterating over by-reference arrays.
This results in the
<a href="/migration70/incompatible.html#migration70.incompatible.foreach.by-ref" class="link">improved behaviour when modifying an array during iteration</a>
also being applied when properties are added to or removed from the
object.

### Changes to <span class="type">integer</span> handling

#### Invalid octal literals

Previously, octal literals that contained invalid numbers were silently
truncated (*0128* was taken as *012*). Now, an invalid octal literal
will cause a parse error.

#### Negative bitshifts

Bitwise shifts by negative numbers will now throw an <span
class="classname">ArithmeticError</span>:

``` php
<?php
var_dump(1 >> -1);
?>
```

Output of the above example in PHP 5:

    int(0)

Output of the above example in PHP 7:

    Fatal error: Uncaught ArithmeticError: Bit shift by negative number in /tmp/test.php:2
    Stack trace:
    #0 {main}
      thrown in /tmp/test.php on line 2

#### Out of range bitshifts

Bitwise shifts (in either direction) beyond the bit width of an <span
class="type">integer</span> will always result in 0. Previously, the
behaviour of such shifts was architecture dependent.

#### Changes to Division By Zero

Previously, when 0 was used as the divisor for either the divide (/) or
modulus (%) operators, an E\_WARNING would be emitted and **`false`**
would be returned. Now, the divide operator returns a float as either
+INF, -INF, or NAN, as specified by IEEE 754. The modulus operator
E\_WARNING has been removed and will throw a <span
class="classname">DivisionByZeroError</span> exception.

``` php
<?php
var_dump(3/0);
var_dump(0/0);
var_dump(0%0);
?>
```

Output of the above example in PHP 5:

    Warning: Division by zero in %s on line %d
    bool(false)

    Warning: Division by zero in %s on line %d
    bool(false)

    Warning: Division by zero in %s on line %d
    bool(false)

Output of the above example in PHP 7:

    Warning: Division by zero in %s on line %d
    float(INF)

    Warning: Division by zero in %s on line %d
    float(NAN)

    PHP Fatal error:  Uncaught DivisionByZeroError: Modulo by zero in %s line %d

### Changes to <span class="type">string</span> handling

#### Hexadecimal strings are no longer considered numeric

Strings containing hexadecimal numbers are no longer considered to be
numeric. For example:

``` php
<?php
var_dump("0x123" == "291");
var_dump(is_numeric("0x123"));
var_dump("0xe" + "0x1");
var_dump(substr("foo", "0x1"));
?>
```

Output of the above example in PHP 5:

    bool(true)
    bool(true)
    int(15)
    string(2) "oo"

Output of the above example in PHP 7:

    bool(false)
    bool(false)
    int(0)

    Notice: A non well formed numeric value encountered in /tmp/test.php on line 5
    string(3) "foo"

<span class="function">filter\_var</span> can be used to check if a
<span class="type">string</span> contains a hexadecimal number, and also
to convert a string of that type to an <span
class="type">integer</span>:

``` php
<?php
$str = "0xffff";
$int = filter_var($str, FILTER_VALIDATE_INT, FILTER_FLAG_ALLOW_HEX);
if (false === $int) {
    throw new Exception("Invalid integer!");
}
var_dump($int); // int(65535)
?>
```

#### *\\u{* may cause errors

Due to the addition of the new
<a href="/migration70/new-features.html#migration70.new-features.unicode-codepoint-escape-syntax" class="link">Unicode codepoint escape syntax</a>,
strings containing a literal *\\u{* followed by an invalid sequence will
cause a fatal error. To avoid this, the leading backslash should be
escaped.

### Removed functions

#### <span class="function">call\_user\_method</span> and <span class="function">call\_user\_method\_array</span>

These functions were deprecated in PHP 4.1.0 in favour of <span
class="function">call\_user\_func</span> and <span
class="function">call\_user\_func\_array</span>. You may also want to
consider using
<a href="/functions/variable-functions.html" class="link">variable functions</a>
and/or the
<a href="/functions/arguments.html#functions.variable-arg-list.new" class="link"><em>...</em></a>
operator.

#### All ereg\* functions

All <a href="/book/regex.html" class="link">ereg</a> functions were
removed. <a href="/book/pcre.html" class="link">PCRE</a> is a
recommended alternative.

#### <a href="/book/mcrypt.html" class="link">mcrypt</a> aliases

The deprecated <span class="function">mcrypt\_generic\_end</span>
function has been removed in favour of <span
class="function">mcrypt\_generic\_deinit</span>.

Additionally, the deprecated <span class="function">mcrypt\_ecb</span>,
<span class="function">mcrypt\_cbc</span>, <span
class="function">mcrypt\_cfb</span> and <span
class="function">mcrypt\_ofb</span> functions have been removed in
favour of using <span class="function">mcrypt\_decrypt</span> with the
appropriate **`MCRYPT_MODE_*`** constant.

#### All ext/mysql functions

All
<a href="/set/mysqlinfo.html#MySQL%20(Original)" class="link">ext/mysql</a>
functions were removed. For details about choosing a different MySQL
API, see
<a href="/set/mysqlinfo.html#Choosing%20an%20API" class="link">Choosing a MySQL API</a>.

#### All ext/mssql functions

All <a href="/book/mssql.html" class="link">ext/mssql</a> functions were
removed. For a list of alternatives, see the
<a href="/book/mssql.html#Introduction" class="link">MSSQL Introduction</a>.

#### <a href="/book/intl.html" class="link">intl</a> aliases

The deprecated <span class="function">datefmt\_set\_timezone\_id</span>
and <span class="methodname">IntlDateFormatter::setTimeZoneID</span>
aliases have been removed in favour of <span
class="function">datefmt\_set\_timezone</span> and <span
class="methodname">IntlDateFormatter::setTimeZone</span>, respectively.

#### <span class="function">set\_magic\_quotes\_runtime</span>

<span class="function">set\_magic\_quotes\_runtime</span>, along with
its alias <span class="function">magic\_quotes\_runtime</span>, have
been removed. They were deprecated in PHP 5.3.0, and became effectively
non-functional with the removal of magic quotes
<a href="/migration54/incompatible.html" class="link">in PHP 5.4.0</a>.

#### <span class="function">set\_socket\_blocking</span>

The deprecated <span class="function">set\_socket\_blocking</span> alias
has been removed in favour of <span
class="function">stream\_set\_blocking</span>.

#### <span class="function">dl</span> in PHP-FPM

<span class="function">dl</span> can no longer be used in PHP-FPM. It
remains functional in the CLI and embed SAPIs.

#### <a href="/book/image.html" class="link">GD</a> Type1 functions

Support for PostScript Type1 fonts has been removed from the GD
extension, resulting in the removal of the following functions:

-   <span class="simpara"> <span class="function">imagepsbbox</span>
    </span>
-   <span class="simpara"> <span
    class="function">imagepsencodefont</span> </span>
-   <span class="simpara"> <span
    class="function">imagepsextendfont</span> </span>
-   <span class="simpara"> <span class="function">imagepsfreefont</span>
    </span>
-   <span class="simpara"> <span class="function">imagepsloadfont</span>
    </span>
-   <span class="simpara"> <span
    class="function">imagepsslantfont</span> </span>
-   <span class="simpara"> <span class="function">imagepstext</span>
    </span>

Using TrueType fonts and their associated functions is recommended
instead.

### Removed INI directives

#### Removed features

The following INI directives have been removed as their associated
features have also been removed:

-   <span class="simpara">
    <a href="/ini/core.html#ini.always-populate-raw-post-data" class="link"><code class="parameter">always_populate_raw_post_data</code></a>
    </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.asp-tags" class="link"><code class="parameter">asp_tags</code></a>
    </span>

#### `xsl.security_prefs`

The `xsl.security_prefs` directive has been removed. Instead, the <span
class="methodname">XsltProcessor::setSecurityPrefs</span> method should
be called to control the security preferences on a per-processor basis.

### Other backward incompatible changes

#### New objects cannot be assigned by reference

The result of the
<a href="/language/oop5/basic.html#language.oop5.basic.new" class="link"><em>new</em></a>
statement can no longer be assigned to a variable by reference:

``` php
<?php
class C {}
$c =& new C;
?>
```

Output of the above example in PHP 5:

    Deprecated: Assigning the return value of new by reference is deprecated in /tmp/test.php on line 3

Output of the above example in PHP 7:

    Parse error: syntax error, unexpected 'new' (T_NEW) in /tmp/test.php on line 3

#### Invalid class, interface and trait names

The following names cannot be used to name classes, interfaces or
traits:

-   <span class="simpara"><span class="type">bool</span></span>
-   <span class="simpara"><span class="type">int</span></span>
-   <span class="simpara"><span class="type">float</span></span>
-   <span class="simpara"><span class="type">string</span></span>
-   <span class="simpara">**`NULL`**</span>
-   <span class="simpara">**`TRUE`**</span>
-   <span class="simpara">**`FALSE`**</span>

Furthermore, the following names should not be used. Although they will
not generate an error in PHP 7.0, they are reserved for future use and
should be considered deprecated.

-   <span class="simpara"><span class="type">resource</span></span>
-   <span class="simpara"><span class="type">object</span></span>
-   <span class="simpara"><span class="type">mixed</span></span>
-   <span class="simpara"><span class="type">numeric</span></span>

#### ASP and script PHP tags removed

Support for using ASP and script tags to delimit PHP code has been
removed. The affected tags are:

| Opening tag               | Closing tag |
|---------------------------|-------------|
| `<%`                      | `%>`        |
| `<%=`                     | `%>`        |
| `<script language="php">` | `</script>` |

#### Calls from incompatible context removed

<a href="/migration56/deprecated.html#migration56.deprecated.incompatible-context" class="link">Previously deprecated in PHP 5.6</a>,
static calls made to a non-static method with an incompatible context
will now result in the called method having an undefined *$this*
variable and a deprecation warning being issued.

``` php
<?php
class A {
    public function test() { var_dump($this); }
}

// Note: Does NOT extend A
class B {
    public function callNonStaticMethodOfA() { A::test(); }
}

(new B)->callNonStaticMethodOfA();
?>
```

Output of the above example in PHP 5.6:

    Deprecated: Non-static method A::test() should not be called statically, assuming $this from incompatible context in /tmp/test.php on line 8
    object(B)#1 (0) {
    }

Output of the above example in PHP 7:

    Deprecated: Non-static method A::test() should not be called statically in /tmp/test.php on line 8

    Notice: Undefined variable: this in /tmp/test.php on line 3
    NULL

#### <a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a> is now a right associative operator

The
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>
construct no longer requires parentheses, and has been changed to a
right associative operator with precedence between *print* and *=\>*.
This can result in changed behaviour:

``` php
<?php
echo yield -1;
// Was previously interpreted as
echo (yield) - 1;
// And is now interpreted as
echo yield (-1);

yield $foo or die;
// Was previously interpreted as
yield ($foo or die);
// And is now interpreted as
(yield $foo) or die;
?>
```

Parentheses can be used to disambiguate those cases.

#### Functions cannot have multiple parameters with the same name

It is no longer possible to define two or more function parameters with
the same name. For example, the following function will trigger an
**`E_COMPILE_ERROR`**:

``` php
<?php
function foo($a, $b, $unused, $unused) {
    //
}
?>
```

#### Functions inspecting arguments report the *current* parameter value

<span class="function">func\_get\_arg</span>, <span
class="function">func\_get\_args</span>, <span
class="function">debug\_backtrace</span> and exception backtraces will
no longer report the original value that was passed to a parameter, but
will instead provide the current value (which might have been modified).

``` php
<?php
function foo($x) {
    $x++;
    var_dump(func_get_arg(0));
}
foo(1);?>
```

Output of the above example in PHP 5:

    1

Output of the above example in PHP 7:

    2

#### Switch statements cannot have multiple default blocks

It is no longer possible to define two or more default blocks in a
switch statement. For example, the following switch statement will
trigger an **`E_COMPILE_ERROR`**:

``` php
<?php
switch (1) {
    default:
    break;
    default:
    break;
}
?>
```

#### `$HTTP_RAW_POST_DATA` removed

`$HTTP_RAW_POST_DATA` is no longer available. The
<a href="/wrappers/php.html#wrappers.php.input" class="link"><em>php://input</em></a>
stream should be used instead.

#### *\#* comments in INI files removed

Support for prefixing comments with *\#* in INI files has been removed.
*;* (semi-colon) should be used instead. This change applies to
`php.ini`, as well as files handled by <span
class="function">parse\_ini\_file</span> and <span
class="function">parse\_ini\_string</span>.

#### JSON extension replaced with JSOND

The JSON extension has been replaced with JSOND, causing three minor BC
breaks. Firstly, a number must not end in a decimal point (i.e. *34.*
must be changed to either *34.0* or *34*). Secondly, when using
scientific notation, the *e* exponent must not immediately follow a
decimal point (i.e. *3.e3* must be changed to either *3.0e3* or *3e3*).
Finally, an empty string is no longer considered valid JSON.

#### Internal function failure on overflow

Previously, internal functions would silently truncate numbers produced
from float-to-integer coercions when the float was too large to
represent as an integer. Now, an E\_WARNING will be emitted and
**`NULL`** will be returned.

#### Fixes to custom session handler return values

Any predicate functions implemented by custom session handlers that
return either **`FALSE`** or *-1* will be fatal errors. If any value
from these functions other than a boolean, *-1*, or *0* is returned,
then it will fail and an E\_WARNING will be emitted.

#### Sort order of equal elements

The internal sorting algorithm has been improved, what may result in
different sort order of elements, which compare as equal, than before.

> **Note**:
>
> Don't rely on the order of elements which compare as equal; it might
> change anytime.

#### Misplaced break and switch statements

*break* and *continue* statements outside of a loop or *switch* control
structure are now detected at compile-time instead of run-time as
before, and trigger an **`E_COMPILE_ERROR`**.

#### Mhash is not an extension anymore

The Mhash extension has been fully integrated into the
<a href="/book/hash.html" class="link">Hash</a> extension. Therefore, it
is no longer possible to detect Mhash support with <span
class="function">extension\_loaded</span>; use <span
class="function">function\_exists</span> instead. Furthermore, Mhash is
no longer reported by <span
class="function">get\_loaded\_extensions</span> and related features.

#### declare(ticks)

The
<a href="/control-structures/declare.html#control-structures.declare.ticks" class="link">declare(ticks)</a>
directive does no longer leak into different compilation units.

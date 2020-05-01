*declare*
---------

The *declare* construct is used to set execution directives for a block
of code. The syntax of *declare* is similar to the syntax of other flow
control constructs:

    declare (directive)
        statement

The *directive* section allows the behavior of the *declare* block to be
set. Currently only three directives are recognized: the *ticks*
directive (See below for more information on the
<a href="/control-structures/declare.html#control-structures.declare.ticks" class="link">ticks</a>
directive), the *encoding* directive (See below for more information on
the
<a href="/control-structures/declare.html#control-structures.declare.encoding" class="link">encoding</a>
directive) and the *strict\_types* directive (See for more information
the
<a href="/functions/arguments.html#functions.arguments.type-declaration.strict" class="link">strict</a>
section on the Function arguments page)

| Version | Description                                                                 |
|---------|-----------------------------------------------------------------------------|
| 7.0.0   | Added *strict\_types* directive                                             |
| 7.0.0   | The *ticks* directive does no longer leak into different compilation units. |
| 5.3.0   | Added *encoding* directive                                                  |

As directives are handled as the file is being compiled, only literals
may be given as directive values. Variables and constants cannot be
used. To illustrate:

``` php
<?php
// This is valid:
declare(ticks=1);

// This is invalid:
const TICK_VALUE = 1;
declare(ticks=TICK_VALUE);
?>
```

The *statement* part of the *declare* block will be executed - how it is
executed and what side effects occur during execution may depend on the
directive set in the *directive* block.

The *declare* construct can also be used in the global scope, affecting
all code following it (however if the file with *declare* was included
then it does not affect the parent file).

``` php
<?php
// these are the same:

// you can use this:
declare(ticks=1) {
    // entire script here
}

// or you can use this:
declare(ticks=1);
// entire script here
?>
```

### Ticks

A tick is an event that occurs for every `N` low-level tickable
statements executed by the parser within the *declare* block. The value
for `N` is specified using `ticks=N` within the *declare* block's
*directive* section.

Not all statements are tickable. Typically, condition expressions and
argument expressions are not tickable.

The event(s) that occur on each tick are specified using the <span
class="function">register\_tick\_function</span>. See the example below
for more details. Note that more than one event can occur for each tick.

**Example \#1 Tick usage example**

``` php
<?php

declare(ticks=1);

// A function called on each tick event
function tick_handler()
{
    echo "tick_handler() called\n";
}

register_tick_function('tick_handler');

$a = 1;

if ($a > 0) {
    $a += 2;
    print($a);
}

?>
```

**Example \#2 Ticks usage example**

``` php
<?php

function tick_handler()
{
  echo "tick_handler() called\n";
}

$a = 1;
tick_handler();

if ($a > 0) {
    $a += 2;
    tick_handler();
    print($a);
    tick_handler();
}
tick_handler();

?>
```

See also <span class="function">register\_tick\_function</span> and
<span class="function">unregister\_tick\_function</span>.

### Encoding

A script's encoding can be specified per-script using the *encoding*
directive.

**Example \#3 Declaring an encoding for the script.**

``` php
<?php
declare(encoding='ISO-8859-1');
// code here
?>
```

**Caution**

When combined with namespaces, the only legal syntax for declare is
*declare(encoding='...');* where *...* is the encoding value.
*declare(encoding='...') {}* will result in a parse error when combined
with namespaces.

The encoding declare value is ignored in PHP 5.3 unless php is compiled
with *--enable-zend-multibyte*.

Note that PHP does not expose whether *--enable-zend-multibyte* was used
to compile PHP other than by <span class="function">phpinfo</span>.

See also
<a href="/ini/core.html#ini.zend.script-encoding" class="link">zend.script_encoding</a>.

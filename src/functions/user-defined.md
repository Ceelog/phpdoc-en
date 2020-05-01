User-defined functions
----------------------

A function may be defined using syntax such as the following:

**Example \#1 Pseudo code to demonstrate function uses**

``` php
<?php
function foo($arg_1, $arg_2, /* ..., */ $arg_n)
{
    echo "Example function.\n";
    return $retval;
}
?>
```

Any valid PHP code may appear inside a function, even other functions
and
<a href="/language/oop5/basic.html#language.oop5.basic.class" class="link">class</a>
definitions.

Function names follow the same rules as other labels in PHP. A valid
function name starts with a letter or underscore, followed by any number
of letters, numbers, or underscores. As a regular expression, it would
be expressed thus: `^[a-zA-Z_\x80-\xff][a-zA-Z0-9_\x80-\xff]*$`.

**Tip**

See also the
<a href="/userlandnaming.html" class="xref">Userland Naming Guide</a>.

Functions need not be defined before they are referenced, *except* when
a function is conditionally defined as shown in the two examples below.

When a function is defined in a conditional manner such as the two
examples shown. Its definition must be processed *prior* to being
called.

**Example \#2 Conditional functions**

``` php
<?php

$makefoo = true;

/* We can't call foo() from here 
   since it doesn't exist yet,
   but we can call bar() */

bar();

if ($makefoo) {
  function foo()
  {
    echo "I don't exist until program execution reaches me.\n";
  }
}

/* Now we can safely call foo()
   since $makefoo evaluated to true */

if ($makefoo) foo();

function bar() 
{
  echo "I exist immediately upon program start.\n";
}

?>
```

**Example \#3 Functions within functions**

``` php
<?php
function foo() 
{
  function bar() 
  {
    echo "I don't exist until foo() is called.\n";
  }
}

/* We can't call bar() yet
   since it doesn't exist. */

foo();

/* Now we can call bar(),
   foo()'s processing has
   made it accessible. */

bar();

?>
```

All functions and classes in PHP have the global scope - they can be
called outside a function even if they were defined inside and vice
versa.

PHP does not support function overloading, nor is it possible to
undefine or redefine previously-declared functions.

> **Note**: <span class="simpara"> Function names are case-insensitive
> for the ASCII characters *A* to *Z*, though it is usually good form to
> call functions as they appear in their declaration. </span>

Both
<a href="/functions/arguments.html#functions.variable-arg-list" class="link">variable number of arguments</a>
and
<a href="/functions/arguments.html#functions.arguments.default" class="link">default arguments</a>
are supported in functions. See also the function references for <span
class="function">func\_num\_args</span>, <span
class="function">func\_get\_arg</span>, and <span
class="function">func\_get\_args</span> for more information.

It is possible to call recursive functions in PHP.

**Example \#4 Recursive functions**

``` php
<?php
function recursion($a)
{
    if ($a < 20) {
        echo "$a\n";
        recursion($a + 1);
    }
}
?>
```

> **Note**: <span class="simpara"> Recursive function/method calls with
> over 100-200 recursion levels can smash the stack and cause a
> termination of the current script. Especially, infinite recursion is
> considered a programming error. </span>

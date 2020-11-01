Syntax
------

Constants can be defined using the *const* keyword, or by using the
<span class="function">define</span>-function. While <span
class="function">define</span> allows a constant to be defined to an
arbitrary expression, the *const* keyword has restrictions as outlined
in the next paragraph. Once a constant is defined, it can never be
changed or undefined.

When using the *const* keyword, only scalar (<span
class="type">boolean</span>, <span class="type">integer</span>, <span
class="type">float</span> and <span class="type">string</span>)
expressions and constant <span class="type">array</span>s containing
only scalar expressions are accepted. It is possible to define constants
as a <span class="type">resource</span>, but it should be avoided, as it
can cause unexpected results.

The value of a constant is accessed simply by specifying its name.
Unlike variables, a constant is *not* prepended with a *$*. It is also
possible to use the <span class="function">constant</span> function to
read a constant's value if the constant's name is obtainned dynamically.
Use <span class="function">get\_defined\_constants</span> to get a list
of all defined constants.

> **Note**: <span class="simpara"> Constants and (global) variables are
> in a different namespace. This implies that for example **`TRUE`** and
> `$TRUE` are generally different. </span>

If you use an undefined constant, PHP assumes that you mean the name of
the constant itself, just as if you called it as a <span
class="type">string</span> (CONSTANT vs "CONSTANT"). This fallback is
deprecated as of PHP 7.2.0, and an error of level **`E_WARNING`** is
issued when it happens (previously, an error of level
<a href="/ref/errorfunc.html" class="link">E_NOTICE</a> has been issued
instead.) See also the manual entry on why
<a href="/language/types/array.html#language.types.array.foo-bar" class="link">$foo[bar]</a>
is wrong (unless you first <span class="function">define</span> *bar* as
a constant). This does not apply to
<a href="/language/namespaces/rules.html" class="link">(fully) qualified constants</a>,
which will raise a fatal error if undefined. If you simply want to check
if a constant is set, use the <span class="function">defined</span>
function.

These are the differences between constants and variables:

-   <span class="simpara"> Constants do not have a dollar sign (*$*)
    before them; </span>
-   <span class="simpara"> Constants may be defined and accessed
    anywhere without regard to variable scoping rules; </span>
-   <span class="simpara"> Constants may not be redefined or undefined
    once they have been set; and </span>
-   <span class="simpara"> Constants may only evaluate to scalar values
    or arrays. </span>

**Example \#1 Defining Constants**

``` php
<?php
define("CONSTANT", "Hello world.");
echo CONSTANT; // outputs "Hello world."
echo Constant; // outputs "Constant" and issues a notice.
?>
```

**Example \#2 Defining Constants using the *const* keyword**

``` php
<?php
// Simple scalar value
const CONSTANT = 'Hello World';

echo CONSTANT;

// Scalar expression
const ANOTHER_CONST = CONSTANT.'; Goodbye World';
echo ANOTHER_CONST;

const ANIMALS = array('dog', 'cat', 'bird');
echo ANIMALS[1]; // outputs "cat"

// Constant arrays
define('ANIMALS', array(
    'dog',
    'cat',
    'bird'
));
echo ANIMALS[1]; // outputs "cat"
?>
```

> **Note**:
>
> As opposed to defining constants using <span
> class="function">define</span>, constants defined using the *const*
> keyword must be declared at the top-level scope because they are
> defined at compile-time. This means that they cannot be declared
> inside functions, loops, *if* statements or *try*/ *catch* blocks.

> **Note**:
>
> Prior to PHP 8.0.0, constants defined using <span
> class="function">define</span> may be case-insensitive.

See also
<a href="/language/oop5/constants.html" class="link">Class Constants</a>.

Syntax
------

You can define a constant by using the <span
class="function">define</span>-function or by using the *const* keyword
outside a class definition as of PHP 5.3.0. While <span
class="function">define</span> allows a constant to be defined to an
arbitrary expression, the *const* keyword has restrictions as outlined
in the next paragraph. Once a constant is defined, it can never be
changed or undefined.

When using the *const* keyword, only scalar data (<span
class="type">boolean</span>, <span class="type">integer</span>, <span
class="type">float</span> and <span class="type">string</span>) can be
contained in constants prior to PHP 5.6. From PHP 5.6 onwards, it is
possible to define a constant as a scalar expression, and it is also
possible to define an <span class="type">array</span> constant. It is
possible to define constants as a <span class="type">resource</span>,
but it should be avoided, as it can cause unexpected results.

You can get the value of a constant by simply specifying its name.
Unlike with variables, you should *not* prepend a constant with a *$*.
You can also use the function <span class="function">constant</span> to
read a constant's value if you wish to obtain the constant's name
dynamically. Use <span class="function">get\_defined\_constants</span>
to get a list of all defined constants.

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
-   <span class="simpara"> Prior to PHP 5.3, Constants may only be
    defined using the <span class="function">define</span> function, not
    by simple assignment; </span>
-   <span class="simpara"> Constants may be defined and accessed
    anywhere without regard to variable scoping rules; </span>
-   <span class="simpara"> Constants may not be redefined or undefined
    once they have been set; and </span>
-   <span class="simpara"> Constants may only evaluate to scalar values.
    As of PHP 5.6 it is possible to define array constant using *const*
    keywords and as of PHP 7 array constants can also be defined using
    <span class="function">define</span> You may use arrays in constant
    scalar expressions (for example, *const FOO = array(1,2,3)\[0\];*),
    but the end result must be a value of allowed type. </span>

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
// Works as of PHP 5.3.0
const CONSTANT = 'Hello World';

echo CONSTANT;

// Works as of PHP 5.6.0
const ANOTHER_CONST = CONSTANT.'; Goodbye World';
echo ANOTHER_CONST;

const ANIMALS = array('dog', 'cat', 'bird');
echo ANIMALS[1]; // outputs "cat"

// Works as of PHP 7
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
> Constants defined using the *const* keyword are always case-sensitive,
> while constants defined using <span class="function">define</span> may
> be case-insensitive.

See also
<a href="/language/oop5/constants.html" class="link">Class Constants</a>.

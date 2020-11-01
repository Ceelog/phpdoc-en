Type Juggling
-------------

PHP does not require (or support) explicit type definition in variable
declaration; a variable's type is determined by the context in which the
variable is used. That is to say, if a <span class="type">string</span>
value is assigned to variable `$var`, `$var` becomes a <span
class="type">string</span>. If an <span class="type">integer</span>
value is then assigned to `$var`, it becomes an <span
class="type">integer</span>.

An example of PHP's automatic type conversion is the multiplication
operator '\*'. If either operand is a <span class="type">float</span>,
then both operands are evaluated as <span class="type">float</span>s,
and the result will be a <span class="type">float</span>. Otherwise, the
operands will be interpreted as <span class="type">integer</span>s, and
the result will also be an <span class="type">integer</span>. Note that
this does *not* change the types of the operands themselves; the only
change is in how the operands are evaluated and what the type of the
expression itself is.

``` php
<?php
$foo = "1";  // $foo is string (ASCII 49)
$foo *= 2;   // $foo is now an integer (2)
$foo = $foo * 1.3;  // $foo is now a float (2.6)
$foo = 5 * "10 Little Piggies"; // $foo is integer (50)
$foo = 5 * "10 Small Pigs";     // $foo is integer (50)
?>
```

If the last two examples above seem odd, see
<a href="/language/types/string.html#language.types.string.conversion" class="link">String conversion to numbers</a>.

To force a variable to be evaluated as a certain type, see the section
on
<a href="/language/types/type-juggling.html#language.types.typecasting" class="link">Type casting</a>.
To change the type of a variable, see the <span
class="function">settype</span> function.

To test any of the examples in this section, use the <span
class="function">var\_dump</span> function.

> **Note**:
>
> The behaviour of an automatic conversion to <span
> class="type">array</span> is currently undefined.
>
> Also, because PHP supports indexing into <span
> class="type">string</span>s via offsets using the same syntax as <span
> class="type">array</span> indexing, the following example holds true
> for all PHP versions:
>
> ``` php
> <?php
> $a    = 'car'; // $a is a string
> $a[0] = 'b';   // $a is still a string
> echo $a;       // bar
> ?>
> ```
>
> See the section titled
> <a href="/language/types/string.html#language.types.string.substr" class="link">String access by character</a>
> for more information.

### Type Casting

Type casting in PHP works much as it does in C: the name of the desired
type is written in parentheses before the variable which is to be cast.

``` php
<?php
$foo = 10;   // $foo is an integer
$bar = (boolean) $foo;   // $bar is a boolean
?>
```

The casts allowed are:

-   <span class="simpara">(int), (integer) - cast to <span
    class="type">integer</span></span>
-   <span class="simpara">(bool), (boolean) - cast to <span
    class="type">boolean</span></span>
-   <span class="simpara">(float), (double), (real) - cast to <span
    class="type">float</span></span>
-   <span class="simpara">(string) - cast to <span
    class="type">string</span></span>
-   <span class="simpara">(array) - cast to <span
    class="type">array</span></span>
-   <span class="simpara">(object) - cast to <span
    class="type">object</span></span>
-   <span class="simpara">(unset) - cast to <span
    class="type">NULL</span></span>

(binary) casting and b prefix exists for forward support. Note that the
(binary) cast is essential the same as (string), but it should not be
relied upon.

The (unset) cast has been deprecated as of PHP 7.2.0. Note that the
(unset) cast is the same as assigning the value <span
class="type">NULL</span> to the variable or call. The (unset) cast is
removed as of PHP 8.0.0.

Note that tabs and spaces are allowed inside the parentheses, so the
following are functionally equivalent:

``` php
<?php
$foo = (int) $bar;
$foo = ( int ) $bar;
?>
```

Casting literal <span class="type">string</span>s and variables to
binary <span class="type">string</span>s:

``` php
<?php
$binary = (binary) $string;
$binary = b"binary string";
?>
```

> **Note**:
>
> Instead of casting a variable to a <span class="type">string</span>,
> it is also possible to enclose the variable in double quotes.
>
> ``` php
> <?php
> $foo = 10;            // $foo is an integer
> $str = "$foo";        // $str is a string
> $fst = (string) $foo; // $fst is also a string
>
> // This prints out that "they are the same"
> if ($fst === $str) {
>     echo "they are the same";
> }
> ?>
> ```

It may not be obvious exactly what will happen when casting between
certain types. For more information, see these sections:

-   <span class="simpara">
    <a href="/language/types/boolean.html#language.types.boolean.casting" class="link">Converting to boolean</a>
    </span>
-   <span class="simpara">
    <a href="/language/types/integer.html#language.types.integer.casting" class="link">Converting to integer</a>
    </span>
-   <span class="simpara">
    <a href="/language/types/float.html#language.types.float.casting" class="link">Converting to float</a>
    </span>
-   <span class="simpara">
    <a href="/language/types/string.html#language.types.string.casting" class="link">Converting to string</a>
    </span>
-   <span class="simpara">
    <a href="/language/types/array.html#language.types.array.casting" class="link">Converting to array</a>
    </span>
-   <span class="simpara">
    <a href="/language/types/object.html#language.types.object.casting" class="link">Converting to object</a>
    </span>
-   <span class="simpara">
    <a href="/language/types/resource.html#language.types.resource.casting" class="link">Converting to resource</a>
    </span>
-   <span class="simpara">
    <a href="/language/types/null.html#language.types.null.casting" class="link">Converting to NULL</a>
    </span>
-   <span class="simpara">
    <a href="/types/comparisons.html" class="link">The type comparison tables</a>
    </span>

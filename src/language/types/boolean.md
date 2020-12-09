Booleans
--------

This is the simplest type. A <span class="type">bool</span> expresses a
truth value. It can be either **`true`** or **`false`**.

### Syntax

To specify a <span class="type">bool</span> literal, use the constants
**`true`** or **`false`**. Both are case-insensitive.

``` php
<?php
$foo = True; // assign the value TRUE to $foo
?>
```

Typically, the result of an
<a href="/language/operators.html" class="link">operator</a> which
returns a <span class="type">bool</span> value is passed on to a
<a href="/language/control-structures.html" class="link">control structure</a>.

``` php
<?php
// == is an operator which tests
// equality and returns a boolean
if ($action == "show_version") {
    echo "The version is 1.23";
}

// this is not necessary...
if ($show_separators == TRUE) {
    echo "<hr>\n";
}

// ...because this can be used with exactly the same meaning:
if ($show_separators) {
    echo "<hr>\n";
}
?>
```

### Converting to boolean

To explicitly convert a value to <span class="type">bool</span>, use the
*(bool)* or *(boolean)* casts. However, in most cases the cast is
unnecessary, since a value will be automatically converted if an
operator, function or control structure requires a <span
class="type">bool</span> argument.

See also
<a href="/language/types/type-juggling.html" class="link">Type Juggling</a>.

When converting to <span class="type">bool</span>, the following values
are considered **`false`**:

-   <span class="simpara"> the
    <a href="/language/types/boolean.html" class="link">boolean</a>
    **`false`** itself </span>
-   <span class="simpara"> the
    <a href="/language/types/integer.html" class="link">integer</a>s 0
    and -0 (zero) </span>
-   <span class="simpara"> the
    <a href="/language/types/float.html" class="link">float</a>s 0.0 and
    -0.0 (zero) </span>
-   <span class="simpara"> the empty
    <a href="/language/types/string.html" class="link">string</a>, and
    the <a href="/language/types/string.html" class="link">string</a>
    "0" </span>
-   <span class="simpara"> an
    <a href="/language/types/array.html" class="link">array</a> with
    zero elements </span>
-   <span class="simpara"> the special type
    <a href="/language/types/null.html" class="link">NULL</a> (including
    unset variables) </span>
-   <span class="simpara">
    <a href="/ref/simplexml.html" class="link">SimpleXML</a> objects
    created from empty tags </span>

Every other value is considered **`true`** (including any
<a href="/language/types/resource.html" class="link">resource</a> and
**`NAN`**).

**Warning**

*-1* is considered **`true`**, like any other non-zero (whether negative
or positive) number!

``` php
<?php
var_dump((bool) "");        // bool(false)
var_dump((bool) 1);         // bool(true)
var_dump((bool) -2);        // bool(true)
var_dump((bool) "foo");     // bool(true)
var_dump((bool) 2.3e5);     // bool(true)
var_dump((bool) array(12)); // bool(true)
var_dump((bool) array());   // bool(false)
var_dump((bool) "false");   // bool(true)
?>
```

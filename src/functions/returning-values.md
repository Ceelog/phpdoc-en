Returning values
----------------

Values are returned by using the optional return statement. Any type may
be returned, including arrays and objects. This causes the function to
end its execution immediately and pass control back to the line from
which it was called. See <span class="function">return</span> for more
information.

> **Note**:
>
> If the <span class="function">return</span> is omitted the value
> **`NULL`** will be returned.

### Use of return

**Example \#1 Use of <span class="function">return</span>**

``` php
<?php
function square($num)
{
    return $num * $num;
}
echo square(4);   // outputs '16'.
?>
```

A function can not return multiple values, but similar results can be
obtained by returning an array.

**Example \#2 Returning an array to get multiple values**

``` php
<?php
function small_numbers()
{
    return array (0, 1, 2);
}
list ($zero, $one, $two) = small_numbers();
?>
```

To return a reference from a function, use the reference operator & in
both the function declaration and when assigning the returned value to a
variable:

**Example \#3 Returning a reference from a function**

``` php
<?php
function &returns_reference()
{
    return $someref;
}

$newref =& returns_reference();
?>
```

For more information on references, please check out
<a href="/language/references.html" class="link">References Explained</a>.

### Return type declarations

Similarly to
<a href="/functions/arguments.html#functions.arguments.type-declaration" class="link">argument type declarations</a>,
return type declarations specify the type of the value that will be
returned from a function. The same
<a href="/functions/arguments.html#functions.arguments.type-declaration.types" class="link">types</a>
are available for return type declarations as are available for argument
type declarations.

<a href="/functions/arguments.html#functions.arguments.type-declaration.strict" class="link">Strict typing</a>
also has an effect on return type declarations. In the default weak
mode, returned values will be coerced to the correct type if they are
not already of that type. If this type conversion is not allowed (e.g.
when returning an <span class="type">array</span> from a function with
return type <span class="type">int</span>), a <span
class="classname">TypeError</span> will be thrown. In strict mode, the
returned value must be of the correct type, otherwise a <span
class="classname">TypeError</span> will be thrown.

As of PHP 7.1.0, return statements without an argument trigger
**`E_COMPILE_ERROR`**, unless the return type is <span
class="type">void</span>, in which case return statements with an
argument trigger that error.

As of PHP 7.1.0, return values can be marked as nullable by prefixing
the type name with a question mark (*?*). This signifies that the
function returns either the specified type or **`NULL`**.

> **Note**:
>
> When overriding a parent method, the child's method must match any
> return type declaration on the parent. If the parent doesn't define a
> return type, then the child method may do so.

#### Examples

**Example \#4 Basic return type declaration**

``` php
<?php
function sum($a, $b): float {
    return $a + $b;
}

// Note that a float will be returned.
var_dump(sum(1, 2));
?>
```

The above example will output:

    float(3)

**Example \#5 Strict mode in action**

``` php
<?php
declare(strict_types=1);

function sum($a, $b): int {
    return $a + $b;
}

var_dump(sum(1, 2));
var_dump(sum(1, 2.5));
?>
```

The above example will output:

    int(3)

    Fatal error: Uncaught TypeError: Return value of sum() must be of the type integer, float returned in - on line 5 in -:5
    Stack trace:
    #0 -(9): sum(1, 2.5)
    #1 {main}
      thrown in - on line 5

**Example \#6 Returning an object**

``` php
<?php
class C {}

function getC(): C {
    return new C;
}

var_dump(getC());
?>
```

The above example will output:

    object(C)#1 (0) {
    }

**Example \#7 Nullable return type declaration (as of PHP 7.1.0)**

``` php
<?php
function get_item(): ?string {
    if (isset($_GET['item'])) {
        return $_GET['item'];
    } else {
        return null;
    }
}
?>
```

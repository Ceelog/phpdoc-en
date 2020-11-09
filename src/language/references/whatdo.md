What References Do
------------------

There are three basic operations performed using references:
<a href="/language/references/whatdo.html#language.references.whatdo.assign" class="link">assigning by reference</a>,
<a href="/language/references/whatdo.html#language.references.whatdo.pass" class="link">passing by reference</a>,
and
<a href="/language/references/whatdo.html#language.references.whatdo.return" class="link">returning by reference</a>.
This section will give an introduction to these operations, with links
for further reading.

### Assign By Reference

In the first of these, PHP references allow you to make two variables
refer to the same content. Meaning, when you do:

``` php
<?php
$a =& $b;
?>
```

it means that `$a` and `$b` point to the same content.

> **Note**:
>
> `$a` and `$b` are completely equal here. `$a` is not pointing to `$b`
> or vice versa. `$a` and `$b` are pointing to the same place.

> **Note**:
>
> If you assign, pass, or return an undefined variable by reference, it
> will get created.
>
> **Example \#1 Using references with undefined variables**
>
> ``` php
> <?php
> function foo(&$var) { }
>
> foo($a); // $a is "created" and assigned to null
>
> $b = array();
> foo($b['b']);
> var_dump(array_key_exists('b', $b)); // bool(true)
>
> $c = new StdClass;
> foo($c->d);
> var_dump(property_exists($c, 'd')); // bool(true)
> ?>
> ```

The same syntax can be used with functions that return references:

``` php
<?php
$foo =& find_var($bar);
?>
```

<a href="/language/oop5/basic.html#language.oop5.basic.new" class="link">new</a>
returns a reference automatically, thus it is syntactically invalid. For
more information, see
<a href="/language/oop5/references.html" class="link">Objects and references</a>.)

**Warning**

If you assign a reference to a variable declared *global* inside a
function, the reference will be visible only inside the function. You
can avoid this by using the `$GLOBALS` array.

**Example \#2 Referencing global variables inside functions**

``` php
<?php
$var1 = "Example variable";
$var2 = "";

function global_references($use_globals)
{
    global $var1, $var2;
    if (!$use_globals) {
        $var2 =& $var1; // visible only inside the function
    } else {
        $GLOBALS["var2"] =& $var1; // visible also in global context
    }
}

global_references(false);
echo "var2 is set to '$var2'\n"; // var2 is set to ''
global_references(true);
echo "var2 is set to '$var2'\n"; // var2 is set to 'Example variable'
?>
```

Think about *global $var;* as a shortcut to *$var =&
$GLOBALS\['var'\];*. Thus assigning another reference to *$var* only
changes the local variable's reference.

> **Note**:
>
> If you assign a value to a variable with references in a
> <a href="/control-structures/foreach.html" class="link">foreach</a>
> statement, the references are modified too.
>
> **Example \#3 References and foreach statement**
>
> ``` php
> <?php
> $ref = 0;
> $row =& $ref;
> foreach (array(1, 2, 3) as $row) {
>     // do something
> }
> echo $ref; // 3 - last element of the iterated array
> ?>
> ```

While not being strictly an assignment by reference, expressions created
with the language construct
<a href="/ref/array.html#array" class="link"><em>array()</em></a> can
also behave as such by prefixing *&* to the array element to add.
Example:

``` php
<?php
$a = 1;
$b = array(2, 3);
$arr = array(&$a, &$b[0], &$b[1]);
$arr[0]++; $arr[1]++; $arr[2]++;
/* $a == 2, $b == array(3, 4); */
?>
```

Note, however, that references inside arrays are potentially dangerous.
Doing a normal (not by reference) assignment with a reference on the
right side does not turn the left side into a reference, but references
inside arrays are preserved in these normal assignments. This also
applies to function calls where the array is passed by value. Example:

``` php
<?php
/* Assignment of scalar variables */
$a = 1;
$b =& $a;
$c = $b;
$c = 7; //$c is not a reference; no change to $a or $b

/* Assignment of array variables */
$arr = array(1);
$a =& $arr[0]; //$a and $arr[0] are in the same reference set
$arr2 = $arr; //not an assignment-by-reference!
$arr2[0]++;
/* $a == 2, $arr == array(2) */
/* The contents of $arr are changed even though it's not a reference! */
?>
```

In other words, the reference behavior of arrays is defined in an
element-by-element basis; the reference behavior of individual elements
is dissociated from the reference status of the array container.

### Pass By Reference

The second thing references do is to pass variables by reference. This
is done by making a local variable in a function and a variable in the
calling scope referencing the same content. Example:

``` php
<?php
function foo(&$var)
{
    $var++;
}

$a=5;
foo($a);
?>
```

will make `$a` to be 6. This happens because in the function `foo` the
variable `$var` refers to the same content as `$a`. For more information
on this, read the
<a href="/language/references/pass.html" class="link">passing by reference</a>
section.

### Return By Reference

The third thing references can do is
<a href="/language/references/return.html" class="link">return by reference</a>.

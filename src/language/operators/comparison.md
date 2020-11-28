Comparison Operators
--------------------

Comparison operators, as their name implies, allow you to compare two
values. You may also be interested in viewing
<a href="/types/comparisons.html" class="link">the type comparison tables</a>,
as they show examples of various type related comparisons.

| Example     | Name                     | Result                                                                                                                                           |
|-------------|--------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| $a == $b    | Equal                    | **`TRUE`** if `$a` is equal to `$b` after type juggling.                                                                                         |
| $a === $b   | Identical                | **`TRUE`** if `$a` is equal to `$b`, and they are of the same type.                                                                              |
| $a != $b    | Not equal                | **`TRUE`** if `$a` is not equal to `$b` after type juggling.                                                                                     |
| $a \<\> $b  | Not equal                | **`TRUE`** if `$a` is not equal to `$b` after type juggling.                                                                                     |
| $a !== $b   | Not identical            | **`TRUE`** if `$a` is not equal to `$b`, or they are not of the same type.                                                                       |
| $a \< $b    | Less than                | **`TRUE`** if `$a` is strictly less than `$b`.                                                                                                   |
| $a \> $b    | Greater than             | **`TRUE`** if `$a` is strictly greater than `$b`.                                                                                                |
| $a \<= $b   | Less than or equal to    | **`TRUE`** if `$a` is less than or equal to `$b`.                                                                                                |
| $a \>= $b   | Greater than or equal to | **`TRUE`** if `$a` is greater than or equal to `$b`.                                                                                             |
| $a \<=\> $b | Spaceship                | An <span class="type">int</span> less than, equal to, or greater than zero when `$a` is less than, equal to, or greater than `$b`, respectively. |

If both operands are
<a href="/language/types/numeric-strings.html" class="link">numeric strings</a>,
or one operand is a number and the other one is a
<a href="/language/types/numeric-strings.html" class="link">numeric string</a>,
then the comparison is done numerically. These rules also apply to the
<a href="/control-structures/switch.html" class="link">switch</a>
statement. The type conversion does not take place when the comparison
is *===* or *!==* as this involves comparing the type as well as the
value.

**Warning**

Prior to PHP 8.0.0, if a <span class="type">string</span> is compared to
a number or a numeric string then the <span class="type">string</span>
was converted to a number before performing the comparison. This can
lead to surprising results as can be seen with the following example:

``` php
<?php
var_dump(0 == "a"); // 0 == 0 -> true
var_dump("1" == "01"); // 1 == 1 -> true
var_dump("10" == "1e1"); // 10 == 10 -> true
var_dump(100 == "1e2"); // 100 == 100 -> true

switch ("a") {
case 0:
    echo "0";
    break;
case "a": // never reached because "a" is already matched with 0
    echo "a";
    break;
}
?>
```

``` php
<?php  
// Integers
echo 1 <=> 1; // 0
echo 1 <=> 2; // -1
echo 2 <=> 1; // 1
 
// Floats
echo 1.5 <=> 1.5; // 0
echo 1.5 <=> 2.5; // -1
echo 2.5 <=> 1.5; // 1
 
// Strings
echo "a" <=> "a"; // 0
echo "a" <=> "b"; // -1
echo "b" <=> "a"; // 1
 
echo "a" <=> "aa"; // -1
echo "zz" <=> "aa"; // 1
 
// Arrays
echo [] <=> []; // 0
echo [1, 2, 3] <=> [1, 2, 3]; // 0
echo [1, 2, 3] <=> []; // 1
echo [1, 2, 3] <=> [1, 2, 1]; // 1
echo [1, 2, 3] <=> [1, 2, 4]; // -1
 
// Objects
$a = (object) ["a" => "b"]; 
$b = (object) ["a" => "b"]; 
echo $a <=> $b; // 0
 
$a = (object) ["a" => "b"]; 
$b = (object) ["a" => "c"]; 
echo $a <=> $b; // -1
 
$a = (object) ["a" => "c"]; 
$b = (object) ["a" => "b"]; 
echo $a <=> $b; // 1
 
// not only values are compared; keys must match
$a = (object) ["a" => "b"]; 
$b = (object) ["b" => "b"]; 
echo $a <=> $b; // 1

?>
```

For various types, comparison is done according to the following table
(in order).

| Type of Operand 1                                                                                                                      | Type of Operand 2                                                                                                                      | Result                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span class="type">null</span> or <span class="type">string</span>                                                                     | <span class="type">string</span>                                                                                                       | Convert **`NULL`** to "", numerical or lexical comparison                                                                                                                             |
| <span class="type">bool</span> or <span class="type">null</span>                                                                       | anything                                                                                                                               | Convert both sides to <span class="type">bool</span>, **`FALSE`** \< **`TRUE`**                                                                                                       |
| <span class="type">object</span>                                                                                                       | <span class="type">object</span>                                                                                                       | Built-in classes can define its own comparison, different classes are uncomparable, same class see <a href="/language/oop5/object-comparison.html" class="link">Object Comparison</a> |
| <span class="type">string</span>, <span class="type">resource</span>, <span class="type">int</span> or <span class="type">float</span> | <span class="type">string</span>, <span class="type">resource</span>, <span class="type">int</span> or <span class="type">float</span> | Translate strings and resources to numbers, usual math                                                                                                                                |
| <span class="type">array</span>                                                                                                        | <span class="type">array</span>                                                                                                        | Array with fewer members is smaller, if key from operand 1 is not found in operand 2 then arrays are uncomparable, otherwise - compare value by value (see following example)         |
| <span class="type">object</span>                                                                                                       | anything                                                                                                                               | <span class="type">object</span> is always greater                                                                                                                                    |
| <span class="type">array</span>                                                                                                        | anything                                                                                                                               | <span class="type">array</span> is always greater                                                                                                                                     |

**Example \#1 Boolean/null comparison**

``` php
<?php
// Bool and null are compared as bool always
var_dump(1 == TRUE);  // TRUE - same as (bool)1 == TRUE
var_dump(0 == FALSE); // TRUE - same as (bool)0 == FALSE
var_dump(100 < TRUE); // FALSE - same as (bool)100 < TRUE
var_dump(-10 < FALSE);// FALSE - same as (bool)-10 < FALSE
var_dump(min(-100, -10, NULL, 10, 100)); // NULL - (bool)NULL < (bool)-100 is FALSE < TRUE
?>
```

**Example \#2 Transcription of standard array comparison**

``` php
<?php
// Arrays are compared like this with standard comparison operators
function standard_array_compare($op1, $op2)
{
    if (count($op1) < count($op2)) {
        return -1; // $op1 < $op2
    } elseif (count($op1) > count($op2)) {
        return 1; // $op1 > $op2
    }
    foreach ($op1 as $key => $val) {
        if (!array_key_exists($key, $op2)) {
            return null; // uncomparable
        } elseif ($val < $op2[$key]) {
            return -1;
        } elseif ($val > $op2[$key]) {
            return 1;
        }
    }
    return 0; // $op1 == $op2
}
?>
```

**Warning**

Because of the way <span class="type">float</span>s are represented
internally, you should not test two <span class="type">float</span>s for
equality.

See the documentation for <span class="type">float</span> for more
information.

### See Also

-   <span class="function">strcasecmp</span>
-   <span class="function">strcmp</span>
-   <a href="/language/operators/array.html" class="link">Array operators</a>
-   <a href="/language/types.html" class="link">Types</a>

### Ternary Operator

Another conditional operator is the "?:" (or ternary) operator.

**Example \#3 Assigning a default value**

``` php
<?php
// Example usage for: Ternary Operator
$action = (empty($_POST['action'])) ? 'default' : $_POST['action'];

// The above is identical to this if/else statement
if (empty($_POST['action'])) {
    $action = 'default';
} else {
    $action = $_POST['action'];
}

?>
```

The expression *(expr1) ? (expr2) : (expr3)* evaluates to <span
class="replaceable">expr2</span> if <span
class="replaceable">expr1</span> evaluates to **`TRUE`**, and <span
class="replaceable">expr3</span> if <span
class="replaceable">expr1</span> evaluates to **`FALSE`**.

It is possible to leave out the middle part of the ternary operator.
Expression *expr1 ?: expr3* returns <span
class="replaceable">expr1</span> if <span
class="replaceable">expr1</span> evaluates to **`TRUE`**, and <span
class="replaceable">expr3</span> otherwise.

> **Note**: <span class="simpara"> Please note that the ternary operator
> is an expression, and that it doesn't evaluate to a variable, but to
> the result of an expression. This is important to know if you want to
> return a variable by reference. The statement *return $var == 42 ? $a
> : $b;* in a return-by-reference function will therefore not work and a
> warning is issued. </span>

> **Note**:
>
> It is recommended to avoid "stacking" ternary expressions. PHP's
> behaviour when using more than one ternary operator within a single
> statement is non-obvious compared to other languages. Indeed prior to
> PHP 8.0.0, ternary expressions were evaluated from left to right,
> instead of right to left like most other programming languages.
>
> **Example \#4 Non-obvious Ternary Behaviour**
>
> ``` php
> <?php
> // on first glance, the following appears to output 'true'
> echo (true?'true':false?'t':'f');
>
> // however, the actual output of the above is 't' prior to PHP 8.0.0
> // this is because ternary expressions are evaluated from left to right
>
> // the following is a more obvious version of the same code as above
> echo ((true ? 'true' : false) ? 't' : 'f');
>
> // here, one can see that the first expression is evaluated to 'true', which
> // in turn evaluates to (bool)true, thus returning the true branch of the
> // second ternary expression.
> ?>
> ```

### Null Coalescing Operator

Further exists the "??" (or null coalescing) operator.

**Example \#5 Assigning a default value**

``` php
<?php
// Example usage for: Null Coalesce Operator
$action = $_POST['action'] ?? 'default';

// The above is identical to this if/else statement
if (isset($_POST['action'])) {
    $action = $_POST['action'];
} else {
    $action = 'default';
}

?>
```

The expression *(expr1) ?? (expr2)* evaluates to <span
class="replaceable">expr2</span> if <span
class="replaceable">expr1</span> is **`NULL`**, and <span
class="replaceable">expr1</span> otherwise.

In particular, this operator does not emit a notice if the left-hand
side value does not exist, just like <span
class="function">isset</span>. This is especially useful on array keys.

> **Note**: <span class="simpara"> Please note that the null coalescing
> operator is an expression, and that it doesn't evaluate to a variable,
> but to the result of an expression. This is important to know if you
> want to return a variable by reference. The statement *return $foo ??
> $bar;* in a return-by-reference function will therefore not work and a
> warning is issued. </span>

> **Note**:
>
> Please note that the null coalescing operator allows for simple
> nesting:
>
> **Example \#6 Nesting null coalescing operator**
>
> ``` php
> <?php
>
> $foo = null;
> $bar = null;
> $baz = 1;
> $qux = 2;
>
> echo $foo ?? $bar ?? $baz ?? $qux; // outputs 1
>
> ?>
> ```

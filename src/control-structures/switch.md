*switch*
--------

The *switch* statement is similar to a series of IF statements on the
same expression. In many occasions, you may want to compare the same
variable (or expression) with many different values, and execute a
different piece of code depending on which value it equals to. This is
exactly what the *switch* statement is for.

> **Note**: <span class="simpara"> Note that unlike some other
> languages, the
> <a href="/control-structures/continue.html" class="link">continue</a>
> statement applies to *switch* and acts similar to *break*. If you have
> a *switch* inside a loop and wish to continue to the next iteration of
> the outer loop, use *continue 2*. </span>

> **Note**:
>
> Note that switch/case does
> <a href="/types/comparisons.html#types.comparisions-loose" class="link">loose comparison</a>.

The following two examples are two different ways to write the same
thing, one using a series of *if* and *elseif* statements, and the other
using the *switch* statement:

**Example \#1 *switch* structure**

``` php
<?php
if ($i == 0) {
    echo "i equals 0";
} elseif ($i == 1) {
    echo "i equals 1";
} elseif ($i == 2) {
    echo "i equals 2";
}

switch ($i) {
    case 0:
        echo "i equals 0";
        break;
    case 1:
        echo "i equals 1";
        break;
    case 2:
        echo "i equals 2";
        break;
}
?>
```

**Example \#2 *switch* structure allows usage of <span
class="type">string</span>s**

``` php
<?php
switch ($i) {
    case "apple":
        echo "i is apple";
        break;
    case "bar":
        echo "i is bar";
        break;
    case "cake":
        echo "i is cake";
        break;
}
?>
```

It is important to understand how the *switch* statement is executed in
order to avoid mistakes. The *switch* statement executes line by line
(actually, statement by statement). In the beginning, no code is
executed. Only when a *case* statement is found whose expression
evaluates to a value that matches the value of the *switch* expression
does PHP begin to execute the statements. PHP continues to execute the
statements until the end of the *switch* block, or the first time it
sees a *break* statement. If you don't write a *break* statement at the
end of a case's statement list, PHP will go on executing the statements
of the following case. For example:

``` php
<?php
switch ($i) {
    case 0:
        echo "i equals 0";
    case 1:
        echo "i equals 1";
    case 2:
        echo "i equals 2";
}
?>
```

Here, if `$i` is equal to 0, PHP would execute all of the echo
statements! If `$i` is equal to 1, PHP would execute the last two echo
statements. You would get the expected behavior ('i equals 2' would be
displayed) only if `$i` is equal to 2. Thus, it is important not to
forget *break* statements (even though you may want to avoid supplying
them on purpose under certain circumstances).

In a *switch* statement, the condition is evaluated only once and the
result is compared to each *case* statement. In an *elseif* statement,
the condition is evaluated again. If your condition is more complicated
than a simple compare and/or is in a tight loop, a *switch* may be
faster.

The statement list for a case can also be empty, which simply passes
control into the statement list for the next case.

``` php
<?php
switch ($i) {
    case 0:
    case 1:
    case 2:
        echo "i is less than 3 but not negative";
        break;
    case 3:
        echo "i is 3";
}
?>
```

A special case is the *default* case. This case matches anything that
wasn't matched by the other cases. For example:

``` php
<?php
switch ($i) {
    case 0:
        echo "i equals 0";
        break;
    case 1:
        echo "i equals 1";
        break;
    case 2:
        echo "i equals 2";
        break;
    default:
       echo "i is not equal to 0, 1 or 2";
}
?>
```

> **Note**: <span class="simpara"> Multiple default cases will raise a
> **`E_COMPILE_ERROR`** error. </span>

The alternative syntax for control structures is supported with
switches. For more information, see
<a href="/control-structures/alternative-syntax.html" class="link">Alternative syntax for control structures</a>.

``` php
<?php
switch ($i):
    case 0:
        echo "i equals 0";
        break;
    case 1:
        echo "i equals 1";
        break;
    case 2:
        echo "i equals 2";
        break;
    default:
        echo "i is not equal to 0, 1 or 2";
endswitch;
?>
```

It's possible to use a semicolon instead of a colon after a case like:

``` php
<?php
switch($beer)
{
    case 'tuborg';
    case 'carlsberg';
    case 'heineken';
        echo 'Good choice';
    break;
    default;
        echo 'Please make a new selection...';
    break;
}
?>
```

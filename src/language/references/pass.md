Passing by Reference
--------------------

You can pass a variable by reference to a function so the function can
modify the variable. The syntax is as follows:

``` php
<?php
function foo(&$var)
{
    $var++;
}

$a=5;
foo($a);
// $a is 6 here
?>
```

> **Note**: <span class="simpara"> There is no reference sign on a
> function call - only on function definitions. Function definitions
> alone are enough to correctly pass the argument by reference. As of
> PHP 5.3.0, you will get a warning saying that "call-time
> pass-by-reference" is deprecated when you use & in *foo(&$a);*. And as
> of PHP 5.4.0, call-time pass-by-reference was removed, so using it
> will raise a fatal error. </span>

The following things can be passed by reference:

-   <span class="simpara"> Variables, i.e. *foo($a)* </span>

-   References returned from functions, i.e.:

    ``` php
    <?php
    function foo(&$var)
    {
        $var++;
    }
    function &bar()
    {
        $a = 5;
        return $a;
    }
    foo(bar());
    ?>
    ```

    See more about
    <a href="/language/references/return.html" class="link">returning by reference</a>.

No other expressions should be passed by reference, as the result is
undefined. For example, the following examples of passing by reference
are invalid:

``` php
<?php
function foo(&$var)
{
    $var++;
}
function bar() // Note the missing &
{
    $a = 5;
    return $a;
}
foo(bar()); // Produces fatal error as of PHP 5.0.5, strict standards notice
            // as of PHP 5.1.1, and notice as of PHP 7.0.0

foo($a = 5); // Expression, not variable
foo(5); // Produces fatal error

class Foobar
{
}

foo(new Foobar()) // Produces a notice as of PHP 7.0.7
                  // Notice: Only variables should be passed by reference
?>
```

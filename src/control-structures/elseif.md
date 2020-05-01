*elseif*/*else if*
------------------

*elseif*, as its name suggests, is a combination of *if* and *else*.
Like *else*, it extends an *if* statement to execute a different
statement in case the original *if* expression evaluates to **`FALSE`**.
However, unlike *else*, it will execute that alternative expression only
if the *elseif* conditional expression evaluates to **`TRUE`**. For
example, the following code would display <span class="computeroutput">a
is bigger than b</span>, <span class="computeroutput">a equal to
b</span> or <span class="computeroutput">a is smaller than b</span>:

``` php
<?php
if ($a > $b) {
    echo "a is bigger than b";
} elseif ($a == $b) {
    echo "a is equal to b";
} else {
    echo "a is smaller than b";
}
?>
```

There may be several *elseif*s within the same *if* statement. The first
*elseif* expression (if any) that evaluates to **`TRUE`** would be
executed. In PHP, you can also write 'else if' (in two words) and the
behavior would be identical to the one of 'elseif' (in a single word).
The syntactic meaning is slightly different (if you're familiar with C,
this is the same behavior) but the bottom line is that both would result
in exactly the same behavior.

The *elseif* statement is only executed if the preceding *if* expression
and any preceding *elseif* expressions evaluated to **`FALSE`**, and the
current *elseif* expression evaluated to **`TRUE`**.

> **Note**: <span class="simpara"> Note that *elseif* and *else if* will
> only be considered exactly the same when using curly brackets as in
> the above example. When using a colon to define your *if*/*elseif*
> conditions, you must not separate *else if* into two words, or PHP
> will fail with a parse error. </span>

``` php
<?php

/* Incorrect Method: */
if ($a > $b):
    echo $a." is greater than ".$b;
else if ($a == $b): // Will not compile.
    echo "The above line causes a parse error.";
endif;


/* Correct Method: */
if ($a > $b):
    echo $a." is greater than ".$b;
elseif ($a == $b): // Note the combination of the words.
    echo $a." equals ".$b;
else:
    echo $a." is neither greater than or equal to ".$b;
endif;

?>
```

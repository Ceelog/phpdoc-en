*else*
------

Often you'd want to execute a statement if a certain condition is met,
and a different statement if the condition is not met. This is what
*else* is for. *else* extends an *if* statement to execute a statement
in case the expression in the *if* statement evaluates to **`FALSE`**.
For example, the following code would display <span
class="computeroutput">a is greater than b</span> if `$a` is greater
than `$b`, and <span class="computeroutput">a is NOT greater than
b</span> otherwise:

``` php
<?php
if ($a > $b) {
  echo "a is greater than b";
} else {
  echo "a is NOT greater than b";
}
?>
```

The *else* statement is only executed if the *if* expression evaluated
to **`FALSE`**, and if there were any *elseif* expressions - only if
they evaluated to **`FALSE`** as well (see
<a href="/control-structures/elseif.html" class="link">elseif</a>).

*if*
----

The *if* construct is one of the most important features of many
languages, PHP included. It allows for conditional execution of code
fragments. PHP features an *if* structure that is similar to that of C:

    if (expr)
      statement

As described in
<a href="/language/expressions.html" class="link">the section about expressions</a>,
<span class="replaceable">expression</span> is evaluated to its Boolean
value. If <span class="replaceable">expression</span> evaluates to
**`TRUE`**, PHP will execute <span class="replaceable">statement</span>,
and if it evaluates to **`FALSE`** - it'll ignore it. More information
about what values evaluate to **`FALSE`** can be found in the
<a href="/language/types/boolean.html#language.types.boolean.casting" class="link">'Converting to boolean'</a>
section.

The following example would display <span class="computeroutput">a is
bigger than b</span> if `$a` is bigger than `$b`:

``` php
<?php
if ($a > $b)
  echo "a is bigger than b";
?>
```

Often you'd want to have more than one statement to be executed
conditionally. Of course, there's no need to wrap each statement with an
*if* clause. Instead, you can group several statements into a statement
group. For example, this code would display <span
class="computeroutput">a is bigger than b</span> if `$a` is bigger than
`$b`, and would then assign the value of `$a` into `$b`:

``` php
<?php
if ($a > $b) {
  echo "a is bigger than b";
  $b = $a;
}
?>
```

*If* statements can be nested infinitely within other *if* statements,
which provides you with complete flexibility for conditional execution
of the various parts of your program.

Alternative syntax for control structures
-----------------------------------------

PHP offers an alternative syntax for some of its control structures;
namely, *if*, *while*, *for*, *foreach*, and *switch*. In each case, the
basic form of the alternate syntax is to change the opening brace to a
colon (:) and the closing brace to *endif;*, *endwhile;*, *endfor;*,
*endforeach;*, or *endswitch;*, respectively.

``` php
<?php if ($a == 5): ?>
A is equal to 5
<?php endif; ?>
```

In the above example, the HTML block "A is equal to 5" is nested within
an *if* statement written in the alternative syntax. The HTML block
would be displayed only if `$a` is equal to 5.

The alternative syntax applies to *else* and *elseif* as well. The
following is an *if* structure with *elseif* and *else* in the
alternative format:

``` php
<?php
if ($a == 5):
    echo "a equals 5";
    echo "...";
elseif ($a == 6):
    echo "a equals 6";
    echo "!!!";
else:
    echo "a is neither 5 nor 6";
endif;
?>
```

> **Note**:
>
> Mixing syntaxes in the same control block is not supported.

**Warning**

Any output (including whitespace) between a *switch* statement and the
first *case* will result in a syntax error. For example, this is
invalid:

``` php
<?php switch ($foo): ?>
    <?php case 1: ?>
    ...
<?php endswitch ?>
```

Whereas this is valid, as the trailing newline after the *switch*
statement is considered part of the closing *?\>* and hence nothing is
output between the *switch* and *case*:

``` php
<?php switch ($foo): ?>
<?php case 1: ?>
    ...
<?php endswitch ?>
```

See also
<a href="/control-structures/while.html" class="link">while</a>,
<a href="/control-structures/for.html" class="link">for</a>, and
<a href="/control-structures/if.html" class="link">if</a> for further
examples.

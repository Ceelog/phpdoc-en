What References Are Not
-----------------------

As said before, references are not pointers. That means, the following
construct won't do what you expect:

``` php
<?php
function foo(&$var)
{
    $var =& $GLOBALS["baz"];
}
foo($bar); 
?>
```

What happens is that `$var` in `foo` will be bound with `$bar` in the
caller, but then re-bound with `$GLOBALS["baz"]`. There's no way to bind
`$bar` in the calling scope to something else using the reference
mechanism, since `$bar` is not available in the function `foo` (it is
represented by `$var`, but `$var` has only variable contents and not
name-to-value binding in the calling symbol table). You can use
<a href="/language/references/return.html" class="link">returning references</a>
to reference variables selected by the function.

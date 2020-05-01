Unsetting References
--------------------

When you unset the reference, you just break the binding between
variable name and variable content. This does not mean that variable
content will be destroyed. For example:

``` php
<?php
$a = 1;
$b =& $a;
unset($a); 
?>
```

won't unset `$b`, just `$a`.

Again, it might be useful to think about this as analogous to the Unix
**unlink** call.

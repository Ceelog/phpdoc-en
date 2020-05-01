Spotting References
-------------------

Many syntax constructs in PHP are implemented via referencing
mechanisms, so everything mentioned herein about reference binding also
applies to these constructs. Some constructs, like passing and returning
by reference, are mentioned above. Other constructs that use references
are:

### global References

When you declare a variable as **global $var** you are in fact creating
reference to a global variable. That means, this is the same as:

``` php
<?php
$var =& $GLOBALS["var"];
?>
```

This also means that unsetting `$var` won't unset the global variable.

### *$this*

In an object method, `$this` is always a reference to the called object.

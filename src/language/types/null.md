NULL
----

The special **`NULL`** value represents a variable with no value.
**`NULL`** is the only possible value of type <span
class="type">null</span>.

A variable is considered to be <span class="type">null</span> if:

-   it has been assigned the constant **`NULL`**.

-   it has not been set to any value yet.

-   it has been <span class="function">unset</span>.

### Syntax

There is only one value of type <span class="type">null</span>, and that
is the case-insensitive constant **`NULL`**.

``` php
<?php
$var = NULL;       
?>
```

See also the functions <span class="function">is\_null</span> and <span
class="function">unset</span>.

### Casting to **`NULL`**

**Warning**

This feature has been *DEPRECATED* as of PHP 7.2.0. Relying on this
feature is highly discouraged.

Casting a variable to <span class="type">null</span> using *(unset)
$var* will *not* remove the variable or unset its value. It will only
return a **`NULL`** value.

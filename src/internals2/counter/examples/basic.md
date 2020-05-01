Basic interface
---------------

The basic interface provides three simple functions, illustrated here:

**Example \#1 "counter"'s basic interface**

``` php
<?php
$starting_counter_value = counter_get();
counter_bump(1);
$second_counter_value = counter_get();
counter_reset();
$final_counter_value = counter_get();
printf("%3d %3d %3d", $starting_counter_value, $second_counter_value, $final_counter_value);
?>
```

The above example will output:

      0   1   0

The basic interface also provides a number of
<a href="/internals2/counter/constants.html" class="link">INI settings</a>.

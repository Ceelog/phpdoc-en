Extended interface
------------------

The extended interface provides a small suite of functions that allow
the user to define an arbitrary number of named counters with unique
settings. The basic interface can be used in parallel with the extended
interface.

**Example \#1 "counter"'s extended interface**

``` php
<?php
function print_counter_info($counter)
{
    if (is_resource($counter)) {
        printf("Counter's name is '%s' and is%s persistent. Its current value is %d.\n",
            counter_get_meta($counter, COUNTER_META_NAME),
            counter_get_meta($counter, COUNTER_META_IS_PERSISTENT) ? '' : ' not',
            counter_get_value($counter));
    } else {
      print "Not a valid counter!\n";
    }
}

if (($counter_one = counter_get_named("one")) === NULL) {
    $counter_one = counter_create("one", 0, COUNTER_FLAG_PERSIST);
}
counter_bump_value($counter_one, 2);
$counter_two = counter_create("two", 5);
$counter_three = counter_get_named("three");
$counter_four = counter_create("four", 2, COUNTER_FLAG_PERSIST | COUNTER_FLAG_SAVE | COUNTER_FLAG_NO_OVERWRITE);
counter_bump_value($counter_four, 1);

print_counter_info($counter_one);
print_counter_info($counter_two);
print_counter_info($counter_three);
print_counter_info($counter_four);
?>
```

When run once, the above example outputs:

    Counter's name is 'one' and is persistent. Its current value is 2.
    Counter's name is 'two' and is not persistent. Its current value is 5.
    Not a valid counter!
    Counter's name is 'four' and is persistent. Its current value is 3.

If run a second time within the same instance of PHP, it outputs:

    Counter's name is 'one' and is persistent. Its current value is 4.
    Counter's name is 'two' and is not persistent. Its current value is 5.
    Not a valid counter!
    Counter's name is 'four' and is persistent. Its current value is 4.

If then run a third time *in a different instance of PHP*, it outputs:

    Counter's name is 'one' and is persistent. Its current value is 2.
    Counter's name is 'two' and is not persistent. Its current value is 5.
    Not a valid counter!
    Counter's name is 'four' and is persistent. Its current value is 5.

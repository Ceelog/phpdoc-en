Objective interface
-------------------

The objective interface provides an object-oriented way to access the
extended interfaces. The following example shows how the above one would
be implemented using the objective interface. The output of this example
is exactly the same, except that instead of printing "Not a valid
counter!", this will instead issue a PHP warning that the variable
*$counter\_three* is not an object. This example shows that it is
possible to subclass the <span class="classname">Counter</span> class
defined by the extension, as well as that the counter's value is
maintained using an instance variable rather than method access.

**Example \#1 "counter"'s objective interface**

``` php
<?php
class MyCounter extends Counter
{
    public function printCounterInfo() {
        printf("Counter's name is '%s' and is%s persistent. Its current value is %d.\n",
            $this->getMeta(COUNTER_META_NAME),
            $this->getMeta(COUNTER_META_IS_PERSISTENT) ? '' : ' not',
            $this->value);
    }
}

Counter::setCounterClass("MyCounter");
if (($counter_one = Counter::getNamed("one")) === NULL) {
    $counter_one = new Counter("one", 0, COUNTER_FLAG_PERSIST);
}
$counter_one->bumpValue(2); // we aren't allowed to "set" the value directly
$counter_two = new Counter("two", 5);
$counter_three = Counter::getNamed("three");
$counter_four = new Counter("four", 2, COUNTER_FLAG_PERSIST | COUNTER_FLAG_SAVE | COUNTER_FLAG_NO_OVERWRITE);
$counter_four->bumpValue(1);

$counter_one->printCounterInfo();
$counter_two->printCounterInfo();
$counter_three->printCounterInfo();
$counter_four->printCounterInfo();
?>
```

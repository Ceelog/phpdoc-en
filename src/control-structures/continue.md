*continue*
----------

*continue* is used within looping structures to skip the rest of the
current loop iteration and continue execution at the condition
evaluation and then the beginning of the next iteration.

> **Note**: <span class="simpara"> In PHP the
> <a href="/control-structures/switch.html" class="link">switch</a>
> statement is considered a looping structure for the purposes of
> *continue*. *continue* behaves like *break* (when no arguments are
> passed) but will raise a warning as this is likely to be a mistake. If
> a *switch* is inside a loop, *continue 2* will continue with the next
> iteration of the outer loop. </span>

*continue* accepts an optional numeric argument which tells it how many
levels of enclosing loops it should skip to the end of. The default
value is *1*, thus skipping to the end of the current loop.

``` php
<?php
foreach ($arr as $key => $value) {
    if (!($key % 2)) { // skip even members
        continue;
    }
    do_something_odd($value);
}

$i = 0;
while ($i++ < 5) {
    echo "Outer<br />\n";
    while (1) {
        echo "Middle<br />\n";
        while (1) {
            echo "Inner<br />\n";
            continue 3;
        }
        echo "This never gets output.<br />\n";
    }
    echo "Neither does this.<br />\n";
}
?>
```

Omitting the semicolon after *continue* can lead to confusion. Here's an
example of what you shouldn't do.

``` php
<?php
for ($i = 0; $i < 5; ++$i) {
    if ($i == 2)
        continue
    print "$i\n";
}
?>
```

One can expect the result to be:

    0
    1
    3
    4

| Version | Description                                                                                                                       |
|---------|-----------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | *continue* within a *switch* that is attempting to act like a *break* statement for the *switch* will trigger an **`E_WARNING`**. |

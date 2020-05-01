String Operators
----------------

There are two <span class="type">string</span> operators. The first is
the concatenation operator ('.'), which returns the concatenation of its
right and left arguments. The second is the concatenating assignment
operator ('*.=*'), which appends the argument on the right side to the
argument on the left side. Please read
<a href="/language/operators/assignment.html" class="link">Assignment Operators</a>
for more information.

``` php
<?php
$a = "Hello ";
$b = $a . "World!"; // now $b contains "Hello World!"

$a = "Hello ";
$a .= "World!";     // now $a contains "Hello World!"
?>
```

See also the manual sections on the
<a href="/language/types/string.html" class="link">String type</a> and
<a href="/ref/strings.html" class="link">String functions</a>.

*do-while*
----------

*do-while* loops are very similar to *while* loops, except the truth
expression is checked at the end of each iteration instead of in the
beginning. The main difference from regular *while* loops is that the
first iteration of a *do-while* loop is guaranteed to run (the truth
expression is only checked at the end of the iteration), whereas it may
not necessarily run with a regular *while* loop (the truth expression is
checked at the beginning of each iteration, if it evaluates to
**`FALSE`** right from the beginning, the loop execution would end
immediately).

There is just one syntax for *do-while* loops:

``` php
<?php
$i = 0;
do {
    echo $i;
} while ($i > 0);
?>
```

The above loop would run one time exactly, since after the first
iteration, when truth expression is checked, it evaluates to **`FALSE`**
(`$i` is not bigger than 0) and the loop execution ends.

Advanced C users may be familiar with a different usage of the
*do-while* loop, to allow stopping execution in the middle of code
blocks, by encapsulating them with *do-while* (0), and using the
<a href="/control-structures/break.html" class="link"><em>break</em></a>
statement. The following code fragment demonstrates this:

``` php
<?php
do {
    if ($i < 5) {
        echo "i is not big enough";
        break;
    }
    $i *= $factor;
    if ($i < $minimum_limit) {
        break;
    }
   echo "i is ok";

    /* process i */

} while (0);
?>
```

Don't worry if you don't understand this right away or at all. You can
code scripts and even powerful scripts without using this 'feature'.
Since PHP 5.3.0, it is possible to use
<a href="/control-structures/goto.html" class="link"><em>goto</em></a>
operator instead of this hack.

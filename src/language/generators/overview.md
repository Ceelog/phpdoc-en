Generators overview
-------------------

Generators provide an easy way to implement simple
<a href="/language/oop5/iterations.html" class="link">iterators</a>
without the overhead or complexity of implementing a class that
implements the <span class="classname">Iterator</span> interface.

A generator allows you to write code that uses
<a href="/control-structures/foreach.html" class="link">foreach</a> to
iterate over a set of data without needing to build an array in memory,
which may cause you to exceed a memory limit, or require a considerable
amount of processing time to generate. Instead, you can write a
generator function, which is the same as a normal
<a href="/functions/user-defined.html" class="link">function</a>, except
that instead of
<a href="/functions/returning-values.html" class="link">return</a>ing
once, a generator can
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>
as many times as it needs to in order to provide the values to be
iterated over.

A simple example of this is to reimplement the <span
class="function">range</span> function as a generator. The standard
<span class="function">range</span> function has to generate an array
with every value in it and return it, which can result in large arrays:
for example, calling **range(0, 1000000)** will result in well over 100
MB of memory being used.

As an alternative, we can implement an *xrange()* generator, which will
only ever need enough memory to create an <span
class="classname">Iterator</span> object and track the current state of
the generator internally, which turns out to be less than 1 kilobyte.

**Example \#1 Implementing <span class="function">range</span> as a
generator**

``` php
<?php
function xrange($start, $limit, $step = 1) {
    if ($start <= $limit) {
        if ($step <= 0) {
            throw new LogicException('Step must be positive');
        }

        for ($i = $start; $i <= $limit; $i += $step) {
            yield $i;
        }
    } else {
        if ($step >= 0) {
            throw new LogicException('Step must be negative');
        }

        for ($i = $start; $i >= $limit; $i += $step) {
            yield $i;
        }
    }
}

/*
 * Note that both range() and xrange() result in the same
 * output below.
 */

echo 'Single digit odd numbers from range():  ';
foreach (range(1, 9, 2) as $number) {
    echo "$number ";
}
echo "\n";

echo 'Single digit odd numbers from xrange(): ';
foreach (xrange(1, 9, 2) as $number) {
    echo "$number ";
}
?>
```

The above example will output:

    Single digit odd numbers from range():  1 3 5 7 9 
    Single digit odd numbers from xrange(): 1 3 5 7 9 

### <span class="classname">Generator</span> objects

When a generator function is called, a new object of the internal <span
class="classname">Generator</span> class is returned. This object
implements the <span class="classname">Iterator</span> interface in much
the same way as a forward-only iterator object would, and provides
methods that can be called to manipulate the state of the generator,
including sending values to and returning values from it.

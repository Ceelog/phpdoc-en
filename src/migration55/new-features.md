New features
------------

### <a href="/language/generators.html" class="link">Generators</a> added

Support for
<a href="/language/generators.html" class="link">generators</a> has been
added via the **yield** keyword. Generators provide an easy way to
implement simple iterators without the overhead or complexity of
implementing a class that implements the <span
class="classname">Iterator</span> interface.

A simple example that reimplements the <span
class="function">range</span> function as a generator (at least for
positive *step* values):

``` php
<?php
function xrange($start, $limit, $step = 1) {
    for ($i = $start; $i <= $limit; $i += $step) {
        yield $i;
    }
}

echo 'Single digit odd numbers: ';

/*
 * Note that an array is never created or returned,
 * which saves memory.
 */
foreach (xrange(1, 9, 2) as $number) {
    echo "$number ";
}

echo "\n";
?>
```

The above example will output:

    Single digit odd numbers: 1 3 5 7 9 

### <a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a> keyword added

<a href="/language/exceptions.html" class="link"><em>try</em></a>-<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
blocks now support a
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block for code that should be run regardless of whether an exception has
been thrown or not.

### New password hashing API

A
<a href="/book/password.html" class="link">new password hashing API</a>
that makes it easier to securely hash and manage passwords using the
same underlying library as <span class="function">crypt</span> in PHP
has been added. See the documentation for <span
class="function">password\_hash</span> for more detail.

### <a href="/control-structures/foreach.html" class="link"><em>foreach</em></a> now supports <span class="function">list</span>

The <a href="/control-structures/foreach.html" class="link">foreach</a>
control structure now supports unpacking nested arrays into separate
variables via the <span class="function">list</span> construct. For
example:

``` php
<?php
$array = [
    [1, 2],
    [3, 4],
];

foreach ($array as list($a, $b)) {
    echo "A: $a; B: $b\n";
}
?>
```

The above example will output:

    A: 1; B: 2
    A: 3; B: 4

Further documentation is available on the
<a href="/control-structures/foreach.html#control-structures.foreach.list" class="link">foreach</a>
manual page.

### <span class="function">empty</span> supports arbitrary expressions

Passing an arbitrary expression instead of a variable to <span
class="function">empty</span> is now supported. For example:

``` php
<?php
function always_false() {
    return false;
}

if (empty(always_false())) {
    echo "This will be printed.\n";
}

if (empty(true)) {
    echo "This will not be printed.\n";
}
?>
```

The above example will output:

    This will be printed.

### <span class="type">array</span> and <span class="type">string</span> literal dereferencing

<span class="type">Array</span> and <span class="type">string</span>
literals can now be dereferenced directly to access individual elements
and characters:

``` php
<?php
echo 'Array dereferencing: ';
echo [1, 2, 3][0];
echo "\n";

echo 'String dereferencing: ';
echo 'PHP'[0];
echo "\n";
?>
```

The above example will output:

    Array dereferencing: 1
    String dereferencing: P

### Class name resolution via <a href="/language/oop5/basic.html#language.oop5.basic.class.class" class="link">::class</a>

It is possible to use *ClassName::class* to get a fully qualified name
of class *ClassName*. For example:

``` php
<?php
namespace Name\Space;
class ClassName {}

echo ClassName::class;

echo "\n";
?>
```

The above example will output:

    Name\Space\ClassName

### <a href="/book/opcache.html" class="link">OPcache</a> extension added

The Zend Optimiser+ opcode cache has been added to PHP as the new
<a href="/book/opcache.html" class="link">OPcache extension</a>. OPcache
improves PHP performance by storing precompiled script bytecode in
shared memory, thereby removing the need for PHP to load and parse
scripts on each request. See
<a href="/opcache/setup.html#Installation" class="link">the installation instructions</a>
for more detail on enabling and using OPcache.

### <a href="/control-structures/foreach.html" class="link"><em>foreach</em></a> now supports non-scalar keys

<a href="/control-structures/foreach.html" class="link">foreach</a> now
supports keys of any type. While non-scalar keys cannot occur in native
PHP arrays, it is possible for <span
class="methodname">Iterator::key</span> to return a value of any type,
and this will now be handled correctly.

### Apache 2.4 handler supported on Windows

The Apache 2.4 handler SAPI is now supported on Windows.

### Improvements to GD

Various improvements have been made to the GD extension, these include:

-   <span class="simpara"> Flipping support using the new <span
    class="function">imageflip</span> function. </span>
-   <span class="simpara"> Advanced cropping support using the <span
    class="function">imagecrop</span> & <span
    class="function">imagecropauto</span> functions. </span>

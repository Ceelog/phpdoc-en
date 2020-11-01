Generator syntax
----------------

A generator function looks just like a normal function, except that
instead of returning a value, a generator
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>s
as many values as it needs to. Any function containing
<a href="/language/generators/syntax.html#control-structures.yield" class="link">yield</a>
is a generator function.

When a generator function is called, it returns an object that can be
iterated over. When you iterate over that object (for instance, via a
<a href="/control-structures/foreach.html" class="link">foreach</a>
loop), PHP will call the object's iteration methods each time it needs a
value, then saves the state of the generator when the generator yields a
value so that it can be resumed when the next value is required.

Once there are no more values to be yielded, then the generator can
simply exit, and the calling code continues just as if an array has run
out of values.

> **Note**:
>
> A generator can return values, which can be retrieved using <span
> class="methodname">Generator::getReturn</span>.

### **yield** keyword

The heart of a generator function is the **yield** keyword. In its
simplest form, a yield statement looks much like a return statement,
except that instead of stopping execution of the function and returning,
yield instead provides a value to the code looping over the generator
and pauses execution of the generator function.

**Example \#1 A simple example of yielding values**

``` php
<?php
function gen_one_to_three() {
    for ($i = 1; $i <= 3; $i++) {
        // Note that $i is preserved between yields.
        yield $i;
    }
}

$generator = gen_one_to_three();
foreach ($generator as $value) {
    echo "$value\n";
}
?>
```

The above example will output:

    1
    2
    3

> **Note**:
>
> Internally, sequential integer keys will be paired with the yielded
> values, just as with a non-associative array.

**Caution**

The value that will be assigned to `$data` is the value passed to <span
class="methodname">Generator::send</span>, or **`NULL`** if <span
class="methodname">Generator::next</span> is called instead.

#### Yielding values with keys

PHP also supports associative arrays, and generators are no different.
In addition to yielding simple values, as shown above, you can also
yield a key at the same time.

The syntax for yielding a key/value pair is very similar to that used to
define an associative array, as shown below.

**Example \#2 Yielding a key/value pair**

``` php
<?php
/*
 * The input is semi-colon separated fields, with the first
 * field being an ID to use as a key.
 */

$input = <<<'EOF'
1;PHP;Likes dollar signs
2;Python;Likes whitespace
3;Ruby;Likes blocks
EOF;

function input_parser($input) {
    foreach (explode("\n", $input) as $line) {
        $fields = explode(';', $line);
        $id = array_shift($fields);

        yield $id => $fields;
    }
}

foreach (input_parser($input) as $id => $fields) {
    echo "$id:\n";
    echo "    $fields[0]\n";
    echo "    $fields[1]\n";
}
?>
```

The above example will output:

    1:
        PHP
        Likes dollar signs
    2:
        Python
        Likes whitespace
    3:
        Ruby
        Likes blocks

**Caution**

As with the simple value yields shown earlier, yielding a key/value pair
in an expression context requires the yield statement to be
parenthesised:

``` php
$data = (yield $key => $value);
```

#### Yielding null values

Yield can be called without an argument to yield a **`NULL`** value with
an automatic key.

**Example \#3 Yielding **`NULL`**s**

``` php
<?php
function gen_three_nulls() {
    foreach (range(1, 3) as $i) {
        yield;
    }
}

var_dump(iterator_to_array(gen_three_nulls()));
?>
```

The above example will output:

    array(3) {
      [0]=>
      NULL
      [1]=>
      NULL
      [2]=>
      NULL
    }

#### Yielding by reference

Generator functions are able to yield values by reference as well as by
value. This is done in the same way as
<a href="/functions/returning-values.html" class="link">returning references from functions</a>:
by prepending an ampersand to the function name.

**Example \#4 Yielding values by reference**

``` php
<?php
function &gen_reference() {
    $value = 3;

    while ($value > 0) {
        yield $value;
    }
}

/*
 * Note that we can change $number within the loop, and
 * because the generator is yielding references, $value
 * within gen_reference() changes.
 */
foreach (gen_reference() as &$number) {
    echo (--$number).'... ';
}
?>
```

The above example will output:

    2... 1... 0... 

#### Generator delegation via **yield from**

Generator delegation allows you to yield values from another generator,
<span class="classname">Traversable</span> object, or <span
class="type">array</span> by using the **yield from** keyword. The outer
generator will then yield all values from the inner generator, object,
or array until that is no longer valid, after which execution will
continue in the outer generator.

If a generator is used with **yield from**, the **yield from**
expression will also return any value returned by the inner generator.

**Caution**

**yield from** does not reset the keys. It preserves the keys returned
by the <span class="classname">Traversable</span> object, or <span
class="type">array</span>. Thus some values may share a common key with
another **yield** or **yield from**, which, upon insertion into an
array, will overwrite former values with that key.

A common case where this matters is <span
class="function">iterator\_to\_array</span> returning a keyed array by
default, leading to possibly unexpected results. <span
class="function">iterator\_to\_array</span> has a second parameter
`use_keys` which can be set to **`FALSE`** to collect all the values
while ignoring the keys returned by the <span
class="classname">Generator</span>.

**Example \#5 **yield from** with <span
class="function">iterator\_to\_array</span>**

``` php
<?php
function inner() {
    yield 1; // key 0
    yield 2; // key 1
    yield 3; // key 2
}
function gen() {
    yield 0; // key 0
    yield from inner(); // keys 0-2
    yield 4; // key 1
}
// pass false as second parameter to get an array [0, 1, 2, 3, 4]
var_dump(iterator_to_array(gen()));
?>
```

The above example will output:

    array(3) {
      [0]=>
      int(1)
      [1]=>
      int(4)
      [2]=>
      int(3)
    }

**Example \#6 Basic use of **yield from****

``` php
<?php
function count_to_ten() {
    yield 1;
    yield 2;
    yield from [3, 4];
    yield from new ArrayIterator([5, 6]);
    yield from seven_eight();
    yield 9;
    yield 10;
}

function seven_eight() {
    yield 7;
    yield from eight();
}

function eight() {
    yield 8;
}

foreach (count_to_ten() as $num) {
    echo "$num ";
}
?>
```

The above example will output:

    1 2 3 4 5 6 7 8 9 10 

**Example \#7 **yield from** and return values**

``` php
<?php
function count_to_ten() {
    yield 1;
    yield 2;
    yield from [3, 4];
    yield from new ArrayIterator([5, 6]);
    yield from seven_eight();
    return yield from nine_ten();
}

function seven_eight() {
    yield 7;
    yield from eight();
}

function eight() {
    yield 8;
}

function nine_ten() {
    yield 9;
    return 10;
}

$gen = count_to_ten();
foreach ($gen as $num) {
    echo "$num ";
}
echo $gen->getReturn();
?>
```

The above example will output:

    1 2 3 4 5 6 7 8 9 10

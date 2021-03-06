New features
------------

### Nullable types

Type declarations for parameters and return values can now be marked as
nullable by prefixing the type name with a question mark. This signifies
that as well as the specified type, **`null`** can be passed as an
argument, or returned as a value, respectively.

``` php
<?php

function testReturn(): ?string
{
    return 'elePHPant';
}

var_dump(testReturn());

function testReturn(): ?string
{
    return null;
}

var_dump(testReturn());

function test(?string $name)
{
    var_dump($name);
}

test('elePHPant');
test(null);
test();
```

The above example will output:

    string(10) "elePHPant"
    NULL
    string(10) "elePHPant"
    NULL
    Uncaught Error: Too few arguments to function test(), 0 passed in...

### Void functions

A <span class="type">void</span> return type has been introduced.
Functions declared with void as their return type must either omit their
return statement altogether, or use an empty return statement.
**`null`** is not a valid return value for a void function.

``` php
<?php
function swap(&$left, &$right): void
{
    if ($left === $right) {
        return;
    }

    $tmp = $left;
    $left = $right;
    $right = $tmp;
}

$a = 1;
$b = 2;
var_dump(swap($a, $b), $a, $b);
```

The above example will output:

    null
    int(2)
    int(1)

Attempting to use a void function's return value simply evaluates to
**`null`**, with no warnings emitted. The reason for this is because
warnings would implicate the use of generic higher order functions.

### Symmetric array destructuring

The shorthand array syntax (*\[\]*) may now be used to destructure
arrays for assignments (including within *foreach*), as an alternative
to the existing <span class="function">list</span> syntax, which is
still supported.

``` php
<?php
$data = [
    [1, 'Tom'],
    [2, 'Fred'],
];

// list() style
list($id1, $name1) = $data[0];

// [] style
[$id1, $name1] = $data[0];

// list() style
foreach ($data as list($id, $name)) {
    // logic here with $id and $name
}

// [] style
foreach ($data as [$id, $name]) {
    // logic here with $id and $name
}
```

### Class constant visibility

Support for specifying the visibility of class constants has been added.

``` php
<?php
class ConstDemo
{
    const PUBLIC_CONST_A = 1;
    public const PUBLIC_CONST_B = 2;
    protected const PROTECTED_CONST = 3;
    private const PRIVATE_CONST = 4;
}
```

### <span class="type">iterable</span> pseudo-type

A new pseudo-type (similar to <span class="type">callable</span>) called
<span class="type">iterable</span> has been introduced. It may be used
in parameter and return types, where it accepts either arrays or objects
that implement the <span class="classname">Traversable</span> interface.
With respect to subtyping, parameter types of child classes may broaden
a parent's declaration of <span class="type">array</span> or <span
class="classname">Traversable</span> to <span
class="type">iterable</span>. With return types, child classes may
narrow a parent's return type of <span class="type">iterable</span> to
<span class="type">array</span> or an object that implements <span
class="classname">Traversable</span>.

``` php
<?php
function iterator(iterable $iter)
{
    foreach ($iter as $val) {
        //
    }
}
```

### Multi catch exception handling

Multiple exceptions per catch block may now be specified using the pipe
character (*\|*). This is useful for when different exceptions from
different class hierarchies are handled the same.

``` php
<?php
try {
    // some code
} catch (FirstException | SecondException $e) {
    // handle first and second exceptions
}
```

### Support for keys in <span class="function">list</span>

You can now specify keys in <span class="function">list</span>, or its
new shorthand *\[\]* syntax. This enables destructuring of arrays with
non-integer or non-sequential keys.

``` php
<?php
$data = [
    ["id" => 1, "name" => 'Tom'],
    ["id" => 2, "name" => 'Fred'],
];

// list() style
list("id" => $id1, "name" => $name1) = $data[0];

// [] style
["id" => $id1, "name" => $name1] = $data[0];

// list() style
foreach ($data as list("id" => $id, "name" => $name)) {
    // logic here with $id and $name
}

// [] style
foreach ($data as ["id" => $id, "name" => $name]) {
    // logic here with $id and $name
}
```

### Support for negative string offsets

Support for negative string offsets has been added to the
<a href="/book/strings.html" class="link">string manipulation functions</a>
accepting offsets, as well as to
<a href="/language/types/string.html#language.types.string.substr" class="link">string indexing</a>
with *\[\]* or *{}*. In such cases, a negative offset is interpreted as
being an offset from the end of the string.

``` php
<?php
var_dump("abcdef"[-2]);
var_dump(strpos("aabbcc", "b", -3));
```

The above example will output:

    string (1) "e"
    int(3)

Negative string and array offsets are now also supported in the simple
variable parsing syntax inside of strings.

``` php
<?php
$string = 'bar';
echo "The last character of '$string' is '$string[-1]'.\n";
?>
```

The above example will output:

    The last character of 'bar' is 'r'.

### Support for AEAD in ext/openssl

Support for AEAD (modes GCM and CCM) have been added by extending the
<span class="function">openssl\_encrypt</span> and <span
class="function">openssl\_decrypt</span> functions with additional
parameters.

### Convert callables to <span class="classname">Closure</span>s with <span class="methodname">Closure::fromCallable</span>

A new static method has been introduced to the <span
class="classname">Closure</span> class to allow for <span
class="type">callable</span>s to be easily converted into <span
class="classname">Closure</span> objects.

``` php
<?php
class Test
{
    public function exposeFunction()
    {
        return Closure::fromCallable([$this, 'privateFunction']);
    }

    private function privateFunction($param)
    {
        var_dump($param);
    }
}

$privFunc = (new Test)->exposeFunction();
$privFunc('some value');
```

The above example will output:

    string(10) "some value"

### Asynchronous signal handling

A new function called <span
class="function">pcntl\_async\_signals</span> has been introduced to
enable asynchronous signal handling without using ticks (which introduce
a lot of overhead).

``` php
<?php
pcntl_async_signals(true); // turn on async signals

pcntl_signal(SIGHUP,  function($sig) {
    echo "SIGHUP\n";
});

posix_kill(posix_getpid(), SIGHUP);
```

The above example will output:

    SIGHUP

### HTTP/2 server push support in ext/curl

Support for server push has been added to the CURL extension (requires
version 7.46 and above). This can be leveraged through the <span
class="function">curl\_multi\_setopt</span> function with the new
**`CURLMOPT_PUSHFUNCTION`** constant. The constants **`CURL_PUSH_OK`**
and **`CURL_PUSH_DENY`** have also been added so that the execution of
the server push callback can either be approved or denied.

### Stream Context Options

The
<a href="/context/socket.html#context.socket.tcp_nodelay" class="link">tcp_nodelay</a>
stream context option has been added.

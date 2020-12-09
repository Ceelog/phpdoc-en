New features
------------

### Scalar type declarations

Scalar
<a href="/language/types/declarations.html" class="link">type declarations</a>
come in two flavours: coercive (default) and strict. The following types
for parameters can now be enforced (either coercively or strictly):
strings (<span class="type">string</span>), integers (*int*),
floating-point numbers (<span class="type">float</span>), and booleans
(*bool*). They augment the other types introduced in PHP 5: class names,
interfaces, <span class="type">array</span> and <span
class="type">callable</span>.

``` php
<?php
// Coercive mode
function sumOfInts(int ...$ints)
{
    return array_sum($ints);
}

var_dump(sumOfInts(2, '3', 4.1));
```

The above example will output:

    int(9)

To enable strict mode, a single
<a href="/control-structures/declare.html" class="link"><em>declare</em></a>
directive must be placed at the top of the file. This means that the
strictness of typing for scalars is configured on a per-file basis. This
directive not only affects the type declarations of parameters, but also
a function's return type (see
<a href="/language/types/declarations.html" class="link">return type declarations</a>,
built-in PHP functions, and functions from loaded extensions.

Full documentation and examples of scalar type declarations can be found
in the
<a href="/language/types/declarations.html" class="link">type declaration</a>
reference.

### Return type declarations

PHP 7 adds support for
<a href="/language/types/declarations.html" class="link">return type declarations</a>.
Similarly to
<a href="/language/types/declarations.html" class="link">argument type declarations</a>,
return type declarations specify the type of the value that will be
returned from a function. The same
<a href="/language/types/declarations.html" class="link">types</a> are
available for return type declarations as are available for argument
type declarations.

``` php
<?php

function arraysSum(array ...$arrays): array
{
    return array_map(function(array $array): int {
        return array_sum($array);
    }, $arrays);
}

print_r(arraysSum([1,2,3], [4,5,6], [7,8,9]));
```

The above example will output:

    Array
    (
        [0] => 6
        [1] => 15
        [2] => 24
    )

Full documentation and examples of return type declarations can be found
in the
<a href="/language/types/declarations.html" class="link">return type declarations</a>.
reference.

### Null coalescing operator

The null coalescing operator (*??*) has been added as syntactic sugar
for the common case of needing to use a ternary in conjunction with
<span class="function">isset</span>. It returns its first operand if it
exists and is not **`null`**; otherwise it returns its second operand.

``` php
<?php
// Fetches the value of $_GET['user'] and returns 'nobody'
// if it does not exist.
$username = $_GET['user'] ?? 'nobody';
// This is equivalent to:
$username = isset($_GET['user']) ? $_GET['user'] : 'nobody';

// Coalescing can be chained: this will return the first
// defined value out of $_GET['user'], $_POST['user'], and
// 'nobody'.
$username = $_GET['user'] ?? $_POST['user'] ?? 'nobody';
?>
```

### Spaceship operator

The spaceship operator is used for comparing two expressions. It returns
-1, 0 or 1 when `$a` is respectively less than, equal to, or greater
than `$b`. Comparisons are performed according to PHP's usual
<a href="/types/comparisons.html" class="link">type comparison rules</a>.

``` php
<?php
// Integers
echo 1 <=> 1; // 0
echo 1 <=> 2; // -1
echo 2 <=> 1; // 1

// Floats
echo 1.5 <=> 1.5; // 0
echo 1.5 <=> 2.5; // -1
echo 2.5 <=> 1.5; // 1
 
// Strings
echo "a" <=> "a"; // 0
echo "a" <=> "b"; // -1
echo "b" <=> "a"; // 1
?>
```

### Constant arrays using <span class="function">define</span>

<span class="type">Array</span> constants can now be defined with <span
class="function">define</span>. In PHP 5.6, they could only be defined
with
<a href="/language/constants/syntax.html" class="link"><em>const</em></a>.

``` php
<?php
define('ANIMALS', [
    'dog',
    'cat',
    'bird'
]);

echo ANIMALS[1]; // outputs "cat"
?>
```

### Anonymous classes

Support for anonymous classes has been added via *new class*. These can
be used in place of full class definitions for throwaway objects:

``` php
<?php
interface Logger {
    public function log(string $msg);
}

class Application {
    private $logger;

    public function getLogger(): Logger {
         return $this->logger;
    }

    public function setLogger(Logger $logger) {
         $this->logger = $logger;
    }
}

$app = new Application;
$app->setLogger(new class implements Logger {
    public function log(string $msg) {
        echo $msg;
    }
});

var_dump($app->getLogger());
?>
```

The above example will output:

    object(class@anonymous)#2 (0) {
    }

Full documentation can be found in the
<a href="/language/oop5/anonymous.html" class="link">anonymous class reference</a>.

### Unicode codepoint escape syntax

This takes a Unicode codepoint in hexadecimal form, and outputs that
codepoint in UTF-8 to a double-quoted string or a heredoc. Any valid
codepoint is accepted, with leading 0's being optional.

``` php
echo "\u{aa}";
echo "\u{0000aa}";
echo "\u{9999}";
```

The above example will output:

    ª
    ª (same as before but with optional leading 0's)
    香

### <span class="methodname">Closure::call</span>

<span class="methodname">Closure::call</span> is a more performant,
shorthand way of temporarily binding an object scope to a closure and
invoking it.

``` php
<?php
class A {private $x = 1;}

// Pre PHP 7 code
$getX = function() {return $this->x;};
$getXCB = $getX->bindTo(new A, 'A'); // intermediate closure
echo $getXCB();

// PHP 7+ code
$getX = function() {return $this->x;};
echo $getX->call(new A);
```

The above example will output:

    1
    1

### Filtered <span class="function">unserialize</span>

This feature seeks to provide better security when unserializing objects
on untrusted data. It prevents possible code injections by enabling the
developer to whitelist classes that can be unserialized.

``` php
<?php

// converts all objects into __PHP_Incomplete_Class object
$data = unserialize($foo, ["allowed_classes" => false]);

// converts all objects into __PHP_Incomplete_Class object except those of MyClass and MyClass2
$data = unserialize($foo, ["allowed_classes" => ["MyClass", "MyClass2"]]);

// default behaviour (same as omitting the second argument) that accepts all classes
$data = unserialize($foo, ["allowed_classes" => true]);
```

### <span class="classname">IntlChar</span>

The new <span class="classname">IntlChar</span> class seeks to expose
additional ICU functionality. The class itself defines a number of
static methods and constants that can be used to manipulate unicode
characters.

``` php
<?php

printf('%x', IntlChar::CODEPOINT_MAX);
echo IntlChar::charName('@');
var_dump(IntlChar::ispunct('!'));
```

The above example will output:

    10ffff
    COMMERCIAL AT
    bool(true)

In order to use this class, the
<a href="/book/intl.html" class="link">Intl</a> extension must be
installed.

### Expectations

<a href="/ref/info.html#Expectations%20(PHP%207%20only)" class="link">Expectations</a>
are a backwards compatible enhancement to the older <span
class="function">assert</span> function. They allow for zero-cost
assertions in production code, and provide the ability to throw custom
exceptions when the assertion fails.

While the old API continues to be maintained for compatibility, <span
class="function">assert</span> is now a language construct, allowing the
first parameter to be an expression rather than just a <span
class="type">string</span> to be evaluated or a <span
class="type">bool</span> value to be tested.

``` php
<?php
ini_set('assert.exception', 1);

class CustomError extends AssertionError {}

assert(false, new CustomError('Some error message'));
?>
```

The above example will output:

    Fatal error: Uncaught CustomError: Some error message

Full details on this feature, including how to configure it in both
development and production environments, can be found in the
<a href="/ref/info.html#Expectations%20(PHP%207%20only)" class="link">expectations section</a>
of the <span class="function">assert</span> reference.

### Group *use* declarations

Classes, functions and constants being imported from the same
<a href="/language/namespaces/definition.html" class="link"><em>namespace</em></a>
can now be grouped together in a single
<a href="/language/namespaces/importing.html" class="link"><em>use</em></a>
statement.

``` php
<?php
// Pre PHP 7 code
use some\namespace\ClassA;
use some\namespace\ClassB;
use some\namespace\ClassC as C;

use function some\namespace\fn_a;
use function some\namespace\fn_b;
use function some\namespace\fn_c;

use const some\namespace\ConstA;
use const some\namespace\ConstB;
use const some\namespace\ConstC;

// PHP 7+ code
use some\namespace\{ClassA, ClassB, ClassC as C};
use function some\namespace\{fn_a, fn_b, fn_c};
use const some\namespace\{ConstA, ConstB, ConstC};
?>
```

### Generator Return Expressions

This feature builds upon the generator functionality introduced into PHP
5.5. It enables for a *return* statement to be used within a generator
to enable for a final expression to be returned (return by reference is
not allowed). This value can be fetched using the new
*Generator::getReturn()* method, which may only be used once the
generator has finished yielding values.

``` php
<?php

$gen = (function() {
    yield 1;
    yield 2;

    return 3;
})();

foreach ($gen as $val) {
    echo $val, PHP_EOL;
}

echo $gen->getReturn(), PHP_EOL;
```

The above example will output:

    1
    2
    3

Being able to explicitly return a final value from a generator is a
handy ability to have. This is because it enables for a final value to
be returned by a generator (from perhaps some form of coroutine
computation) that can be specifically handled by the client code
executing the generator. This is far simpler than forcing the client
code to firstly check whether the final value has been yielded, and then
if so, to handle that value specifically.

### Generator delegation

Generators can now delegate to another generator, <span
class="classname">Traversable</span> object or <span
class="type">array</span> automatically, without needing to write
boilerplate in the outermost generator by using the
<a href="/language/generators/syntax.html#control-structures.yield.from" class="link"><em>yield from</em></a>
construct.

``` php
<?php
function gen()
{
    yield 1;
    yield 2;
    yield from gen2();
}

function gen2()
{
    yield 3;
    yield 4;
}

foreach (gen() as $val)
{
    echo $val, PHP_EOL;
}
?>
```

The above example will output:

    1
    2
    3
    4

### Integer division with <span class="function">intdiv</span>

The new <span class="function">intdiv</span> function performs an
integer division of its operands and returns it.

``` php
<?php
var_dump(intdiv(10, 3));
?>
```

The above example will output:

    int(3)

### Session options

<span class="function">session\_start</span> now accepts an <span
class="type">array</span> of options that override the
<a href="/session/setup.html#Runtime%20Configuration" class="link">session configuration directives</a>
normally set in php.ini.

These options have also been expanded to support
<a href="/session/setup.html#" class="link">session.lazy_write</a>,
which is on by default and causes PHP to only overwrite any session file
if the session data has changed, and *read\_and\_close*, which is an
option that can only be passed to <span
class="function">session\_start</span> to indicate that the session data
should be read and then the session should immediately be closed
unchanged.

For example, to set
<a href="/session/setup.html#" class="link">session.cache_limiter</a> to
*private* and immediately close the session after reading it:

``` php
<?php
session_start([
    'cache_limiter' => 'private',
    'read_and_close' => true,
]);
?>
```

### <span class="function">preg\_replace\_callback\_array</span>

The new <span class="function">preg\_replace\_callback\_array</span>
function enables code to be written more cleanly when using the <span
class="function">preg\_replace\_callback</span> function. Prior to PHP
7, callbacks that needed to be executed per regular expression required
the callback function to be polluted with lots of branching.

Now, callbacks can be registered to each regular expression using an
associative array, where the key is a regular expression and the value
is a callback.

### <a href="/book/csprng.html" class="link">CSPRNG</a> Functions

Two new functions have been added to generate cryptographically secure
integers and strings in a cross platform way: <span
class="function">random\_bytes</span> and <span
class="function">random\_int</span>.

### <span class="function">list</span> can always unpack objects implementing <span class="classname">ArrayAccess</span>

Previously, <span class="function">list</span> was not guaranteed to
operate correctly with objects implementing <span
class="classname">ArrayAccess</span>. This has been fixed.

### Other Features

-   <span class="simpara"> Class member access on cloning has been
    added, e.g. *(clone $foo)-\>bar()*. </span>

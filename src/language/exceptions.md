Exceptions
==========

**Table of Contents**

-   [Extending Exceptions](/language/exceptions/extending.html)

PHP has an exception model similar to that of other programming
languages. An exception can be
<a href="/language/exceptions.html" class="link"><em>throw</em></a>n,
and caught
("<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>ed")
within PHP. Code may be surrounded in a
<a href="/language/exceptions.html" class="link"><em>try</em></a> block,
to facilitate the catching of potential exceptions. Each
<a href="/language/exceptions.html" class="link"><em>try</em></a> must
have at least one corresponding
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
or
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block.

The thrown object must be an instance of the <span
class="classname">Exception</span> class or a subclass of <span
class="classname">Exception</span>. Trying to throw an object that is
not will result in a PHP Fatal Error.

Multiple
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
blocks can be used to catch different classes of exceptions. Normal
execution (when no exception is thrown within the
<a href="/language/exceptions.html" class="link"><em>try</em></a> block)
will continue after that last
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block defined in sequence. Exceptions can be
<a href="/language/exceptions.html" class="link"><em>throw</em></a>n (or
re-thrown) within a
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block.

When an exception is thrown, code following the statement will not be
executed, and PHP will attempt to find the first matching
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block. If an exception is not caught, a PHP Fatal Error will be issued
with an "*Uncaught Exception ...*" message, unless a handler has been
defined with <span class="function">set\_exception\_handler</span>.

In PHP 7.1 and later, a
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block may specify multiple exceptions using the pipe (*\|*) character.
This is useful for when different exceptions from different class
hierarchies are handled the same.

In PHP 5.5 and later, a
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block may also be specified after or instead of
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
blocks. Code within the
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block will always be executed after the
<a href="/language/exceptions.html" class="link"><em>try</em></a> and
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
blocks, regardless of whether an exception has been thrown, and before
normal execution resumes.

One notable interaction is between the
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block and a
<a href="/function/return.html" class="link"><em>return</em></a>
statement. If a
<a href="/function/return.html" class="link"><em>return</em></a>
statement is encountered inside either the
<a href="/language/exceptions.html" class="link"><em>try</em></a> or the
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
blocks, the
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block will still be executed. Moreover, the
<a href="/function/return.html" class="link"><em>return</em></a>
statement is evaluated when encountered, but the result will be returned
after the
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block is executed. Additionally, if the
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block also contains a
<a href="/function/return.html" class="link"><em>return</em></a>
statement, the value from the
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block is returned.

> **Note**:
>
> Internal PHP functions mainly use
> <a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">Error reporting</a>,
> only modern
> <a href="/language/oop5.html" class="link">Object oriented</a>
> extensions use exceptions. However, errors can be simply translated to
> exceptions with
> <a href="/class/errorexception.html" class="link">ErrorException</a>.

**Tip**

The
<a href="/intro/spl.html" class="link">Standard PHP Library (SPL)</a>
provides a good number of
<a href="/spl/exceptions.html" class="link">built-in exceptions</a>.

**Example \#1 Throwing an Exception**

``` php
<?php
function inverse($x) {
    if (!$x) {
        throw new Exception('Division by zero.');
    }
    return 1/$x;
}

try {
    echo inverse(5) . "\n";
    echo inverse(0) . "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
}

// Continue execution
echo "Hello World\n";
?>
```

The above example will output:

    0.2
    Caught exception: Division by zero.
    Hello World

**Example \#2 Exception handling with a
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block**

``` php
<?php
function inverse($x) {
    if (!$x) {
        throw new Exception('Division by zero.');
    }
    return 1/$x;
}

try {
    echo inverse(5) . "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
} finally {
    echo "First finally.\n";
}

try {
    echo inverse(0) . "\n";
} catch (Exception $e) {
    echo 'Caught exception: ',  $e->getMessage(), "\n";
} finally {
    echo "Second finally.\n";
}

// Continue execution
echo "Hello World\n";
?>
```

The above example will output:

    0.2
    First finally.
    Caught exception: Division by zero.
    Second finally.
    Hello World

**Example \#3 Interaction between the
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
block and
<a href="/function/return.html" class="link"><em>return</em></a>**

``` php
<?php

function test() {
    try {
        throw new Exception('foo');
    } catch (Exception $e) {
        return 'catch';
    } finally {
        return 'finally';
    }
}

echo test();
?>
```

The above example will output:

    finally

**Example \#4 Nested Exception**

``` php
<?php

class MyException extends Exception { }

class Test {
    public function testing() {
        try {
            try {
                throw new MyException('foo!');
            } catch (MyException $e) {
                // rethrow it
                throw $e;
            }
        } catch (Exception $e) {
            var_dump($e->getMessage());
        }
    }
}

$foo = new Test;
$foo->testing();

?>
```

The above example will output:

    string(4) "foo!"

**Example \#5 Multi catch exception handling**

``` php
<?php

class MyException extends Exception { }

class MyOtherException extends Exception { }

class Test {
    public function testing() {
        try {
            throw new MyException();
        } catch (MyException | MyOtherException $e) {
            var_dump(get_class($e));
        }
    }
}

$foo = new Test;
$foo->testing();

?>
```

The above example will output:

    string(11) "MyException"

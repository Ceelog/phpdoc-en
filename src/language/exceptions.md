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

If an exception is thrown and its current function scope has no
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block, the exception will "bubble up" the call stack to the calling
function until it finds a matching
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block. All
<a href="/language/exceptions.html#language.exceptions.finally" class="link"><em>finally</em></a>
blocks it encounters along the way will be executed. If the call stack
is unwound all the way to the global scope without encountering a
matching
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block, the program will terminate with a fatal error unless a global
exception handler has been set.

The thrown object must be an instance of the <span
class="classname">Exception</span> class or a subclass of <span
class="classname">Exception</span>. Trying to throw an object that is
not will result in a PHP Fatal Error.

As of PHP 8.0.0, the
<a href="/language/exceptions.html" class="link"><em>throw</em></a>
keyword is an expression and may be used in any expression context. In
prior versions it was a statement and was required to be on its own
line.

A
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block defines how to respond to a thrown exception. A
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block defines one or more types of exception or error it can handle, and
optionally a variable to which to assign the exception. (The variable
was required prior to PHP 8.0.0.) The first
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block a thrown exception or error encounters that matches the type of
the thrown object will handle the object.

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
block. If not, execution will continue after the
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block that was triggered.

When an exception is thrown, code following the statement will not be
executed, and PHP will attempt to find the first matching
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block. If an exception is not caught, a PHP Fatal Error will be issued
with an "*Uncaught Exception ...*" message, unless a handler has been
defined with <span class="function">set\_exception\_handler</span>.

As of PHP 7.1.0, a
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block may specify multiple exceptions using the pipe (*\|*) character.
This is useful for when different exceptions from different class
hierarchies are handled the same.

As of PHP 8.0.0, the variable name for a caught exception is optional.
If not specified, the
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block will still execute but will not have access to the thrown object.

A
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

If an exception is allowed to bubble up to the global scope, it may be
caught by a global exception handler if set. The <span
class="function">set\_exception\_handler</span> function can set a
function that will be called in place of a
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block if no other block is invoked. The effect is essentially the same
as if the entire program were wrapped in a
<a href="/language/exceptions.html" class="link"><em>try</em></a>-<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block with that function as the
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>.

> **Note**:
>
> Internal PHP functions mainly use
> <a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">Error reporting</a>,
> only modern
> <a href="/language/oop5.html" class="link">Object oriented</a>
> extensions use exceptions. However, errors can be easily translated to
> exceptions with
> <a href="/class/errorexception.html" class="link">ErrorException</a>.
> This technique only works with non-fatal errors, however.
>
> **Example \#1 Converting error reporting to exceptions**
>
> ``` php
> <?php
> function exceptions_error_handler($severity, $message, $filename, $lineno) {
>     throw new ErrorException($message, 0, $severity, $filename, $lineno);
> }
>
> set_error_handler('exceptions_error_handler');
> ?>
> ```

**Tip**

The
<a href="/intro/spl.html" class="link">Standard PHP Library (SPL)</a>
provides a good number of
<a href="/spl/exceptions.html" class="link">built-in exceptions</a>.

**Example \#2 Throwing an Exception**

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

**Example \#3 Exception handling with a
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

**Example \#4 Interaction between the
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

**Example \#5 Nested Exception**

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

**Example \#6 Multi catch exception handling**

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

**Example \#7 Omitting the caught variable**

Only permitted in PHP 8.0.0 and later.

``` php
<?php

class SpecificException extends Exception {}

function test() {
    throw new SpecificException('Oopsie');
}

try {
    test();
} catch (SpecificException) {
    print "A SpecificException was thrown, but we don't care about the details.";
}
?>
```

**Example \#8 Throw as an expression**

Only permitted in PHP 8.0.0 and later.

``` php
<?php

class SpecificException extends Exception {}

function test() {
    do_something_risky() or throw new Exception('It did not work');
}

try {
    test();
} catch (Exception $e) {
    print $e->getMessage();
}
?>
```

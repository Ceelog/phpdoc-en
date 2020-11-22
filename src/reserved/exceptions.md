Predefined Exceptions
=====================

**Table of Contents**

-   [Exception](/class/exception.html) — Exception
    -   [Exception::\_\_construct](/exception/construct.html) —
        Construct the exception
    -   [Exception::getMessage](/exception/getmessage.html) — Gets the
        Exception message
    -   [Exception::getPrevious](/exception/getprevious.html) — Returns
        previous Exception
    -   [Exception::getCode](/exception/getcode.html) — Gets the
        Exception code
    -   [Exception::getFile](/exception/getfile.html) — Gets the file in
        which the exception was created
    -   [Exception::getLine](/exception/getline.html) — Gets the line in
        which the exception was created
    -   [Exception::getTrace](/exception/gettrace.html) — Gets the stack
        trace
    -   [Exception::getTraceAsString](/exception/gettraceasstring.html)
        — Gets the stack trace as a string
    -   [Exception::\_\_toString](/exception/tostring.html) — String
        representation of the exception
    -   [Exception::\_\_clone](/exception/clone.html) — Clone the
        exception
-   [ErrorException](/class/errorexception.html) — ErrorException
    -   [ErrorException::\_\_construct](/errorexception/construct.html)
        — Constructs the exception
    -   [ErrorException::getSeverity](/errorexception/getseverity.html)
        — Gets the exception severity
-   [Error](/class/error.html) — Error
    -   [Error::\_\_construct](/error/construct.html) — Construct the
        error object
    -   [Error::getMessage](/error/getmessage.html) — Gets the error
        message
    -   [Error::getPrevious](/error/getprevious.html) — Returns previous
        Throwable
    -   [Error::getCode](/error/getcode.html) — Gets the error code
    -   [Error::getFile](/error/getfile.html) — Gets the file in which
        the error occurred
    -   [Error::getLine](/error/getline.html) — Gets the line in which
        the error occurred
    -   [Error::getTrace](/error/gettrace.html) — Gets the stack trace
    -   [Error::getTraceAsString](/error/gettraceasstring.html) — Gets
        the stack trace as a string
    -   [Error::\_\_toString](/error/tostring.html) — String
        representation of the error
    -   [Error::\_\_clone](/error/clone.html) — Clone the error
-   [ArgumentCountError](/class/argumentcounterror.html) —
    ArgumentCountError
-   [ArithmeticError](/class/arithmeticerror.html) — ArithmeticError
-   [AssertionError](/class/assertionerror.html) — AssertionError
-   [DivisionByZeroError](/class/divisionbyzeroerror.html) —
    DivisionByZeroError
-   [CompileError](/class/compileerror.html) — CompileError
-   [ParseError](/class/parseerror.html) — ParseError
-   [TypeError](/class/typeerror.html) — TypeError
-   [ValueError](/class/valueerror.html) — ValueError

See also the
<a href="/spl/exceptions.html" class="link">SPL Exceptions</a>

Introduction
------------

<span class="ooclass">**Exception**</span> is the base class for all
user exceptions.

Class synopsis
--------------

**Exception**

<span class="ooclass"> class **Exception** </span> <span
class="ooclass"> <span class="modifier">implements</span> **Throwable**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$message`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$code`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">Throwable</span> `$previous`<span
class="initializer"> = **`NULL`**</span></span> \]\]\] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span class="methodname">getCode</span>
( <span class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span class="methodname">getFile</span>
( <span class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span class="methodname">getLine</span> (
<span class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span class="methodname">getTrace</span>
( <span class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`message`  
The exception message

`code`  
The exception code

`file`  
The filename where the exception was created

`line`  
The line where the exception was created

Introduction
------------

An Error Exception.

Class synopsis
--------------

**ErrorException**

<span class="ooclass"> class **ErrorException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> <span class="type">int</span>
`$severity` ;

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$message`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$code`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$severity`<span
class="initializer"> = E\_ERROR</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$filename`<span
class="initializer"> = \_\_FILE\_\_</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$lineno`<span
class="initializer"> = \_\_LINE\_\_</span></span> \[, <span
class="methodparam"><span class="type">Exception</span> `$previous`<span
class="initializer"> = **`NULL`**</span></span> \]\]\]\]\]\] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">getSeverity</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`severity`  
The severity of the exception

Examples
--------

**Example \#1 Use <span class="function">set\_error\_handler</span> to
change error messages into ErrorException.**

``` php
<?php
function exception_error_handler($severity, $message, $file, $line) {
    if (!(error_reporting() & $severity)) {
        // This error code is not included in error_reporting
        return;
    }
    throw new ErrorException($message, 0, $severity, $file, $line);
}
set_error_handler("exception_error_handler");

/* Trigger exception */
strpos();
?>
```

The above example will output something similar to:

    Fatal error: Uncaught exception 'ErrorException' with message 'strpos() expects at least 2 parameters, 0 given' in /home/bjori/tmp/ex.php:12
    Stack trace:
    #0 [internal function]: exception_error_handler(2, 'strpos() expect...', '/home/bjori/php...', 12, Array)
    #1 /home/bjori/php/cleandocs/test.php(12): strpos()
    #2 {main}
      thrown in /home/bjori/tmp/ex.php on line 12

Introduction
------------

<span class="ooclass">**Error**</span> is the base class for all
internal PHP errors.

Class synopsis
--------------

**Error**

<span class="ooclass"> class **Error** </span> <span class="ooclass">
<span class="modifier">implements</span> **Throwable** </span> {

/\* Properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$message`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$code`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">Throwable</span> `$previous`<span
class="initializer"> = **`NULL`**</span></span> \]\]\] )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span class="methodname">getCode</span>
( <span class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span class="methodname">getFile</span>
( <span class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span class="methodname">getLine</span> (
<span class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span class="methodname">getTrace</span>
( <span class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`message`  
The error message

`code`  
The error code

`file`  
The filename where the error happened

`line`  
The line where the error happened

Introduction
------------

<span class="ooclass">**ArgumentCountError**</span> is thrown when too
few arguments are passed to a user-defined function or method.

Class synopsis
--------------

**ArgumentCountError**

<span class="ooclass"> class **ArgumentCountError** </span> <span
class="ooclass"> <span class="modifier">extends</span> **TypeError**
</span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Error::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

<span class="ooclass">**ArithmeticError**</span> is thrown when an error
occurs while performing mathematical operations. These errors include
attempting to perform a bitshift by a negative amount, and any call to
<span class="function">intdiv</span> that would result in a value
outside the possible bounds of an <span class="type">int</span>.

Class synopsis
--------------

**ArithmeticError**

<span class="ooclass"> class **ArithmeticError** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Error** </span>
{

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Error::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

<span class="ooclass">**AssertionError**</span> is thrown when an
assertion made via <span class="function">assert</span> fails.

Class synopsis
--------------

**AssertionError**

<span class="ooclass"> class **AssertionError** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Error** </span>
{

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Error::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

<span class="ooclass">**DivisionByZeroError**</span> is thrown when an
attempt is made to divide a number by zero.

Class synopsis
--------------

**DivisionByZeroError**

<span class="ooclass"> class **DivisionByZeroError** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**ArithmeticError** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Error::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

<span class="ooclass">**CompileError**</span> is thrown for some
compilation errors, which formerly issued a fatal error.

Class synopsis
--------------

**CompileError**

<span class="ooclass"> class **CompileError** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Error** </span>
{

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Error::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

<span class="ooclass">**ParseError**</span> is thrown when an error
occurs while parsing PHP code, such as when <span
class="function">eval</span> is called.

> **Note**: <span class="simpara"> <span
> class="classname">ParseError</span> extends <span
> class="classname">CompileError</span> as of PHP 7.3.0. Formerly, it
> extended <span class="classname">Error</span>. </span>

Class synopsis
--------------

**ParseError**

<span class="ooclass"> class **ParseError** </span> <span
class="ooclass"> <span class="modifier">extends</span> **CompileError**
</span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Error::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

There are three scenarios where a <span
class="ooclass">**TypeError**</span> may be thrown. The first is where
the argument type being passed to a function does not match its
corresponding declared parameter type. The second is where a value being
returned from a function does not match the declared function return
type. The third is where an invalid number of arguments are passed to a
built-in PHP function (strict mode only).

Class synopsis
--------------

**TypeError**

<span class="ooclass"> class **TypeError** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Error** </span>
{

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Error::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Introduction
------------

A <span class="classname">ValueError</span> is thrown when the type of
an argument is correct but the value of it is incorrect. For example,
passing a negative integer when the function expects a positive one, or
passing an empty string/array when the function expects it to not be
empty.

Class synopsis
--------------

**ValueError**

<span class="ooclass"> class **ValueError** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Error** </span>
{

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Error::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Error::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Error::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Error::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Error::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Error::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Error::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

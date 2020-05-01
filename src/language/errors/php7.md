Errors in PHP 7
---------------

PHP 7 changes how most errors are reported by PHP. Instead of reporting
errors through the traditional error reporting mechanism used by PHP 5,
most errors are now reported by throwing <span
class="classname">Error</span> exceptions.

As with normal exceptions, these <span class="classname">Error</span>
exceptions will bubble up until they reach the first matching
<a href="/language/exceptions.html#language.exceptions.catch" class="link"><em>catch</em></a>
block. If there are no matching blocks, then any default exception
handler installed with <span
class="function">set\_exception\_handler</span> will be called, and if
there is no default exception handler, then the exception will be
converted to a fatal error and will be handled like a traditional error.

As the <span class="classname">Error</span> hierarchy does not inherit
from <span class="classname">Exception</span>, code that uses
`catch (Exception $e) { ... }` blocks to handle uncaught exceptions in
PHP 5 will find that these <span class="classname">Error</span>s are not
caught by these blocks. Either a `catch (Error $e) { ... }` block or a
<span class="function">set\_exception\_handler</span> handler is
required.

### <span class="classname">Error</span> hierarchy

-   <span class="simpara"><span
    class="classname">Throwable</span></span>
    -   <span class="simpara"><span
        class="classname">Error</span></span>
        -   <span class="simpara"><span
            class="classname">ArithmeticError</span></span>
            -   <span class="simpara"><span
                class="classname">DivisionByZeroError</span></span>
        -   <span class="simpara"><span
            class="classname">AssertionError</span></span>
        -   <span class="simpara"><span
            class="classname">CompileError</span></span>
            -   <span class="simpara"><span
                class="classname">ParseError</span></span>
        -   <span class="simpara"><span
            class="classname">TypeError</span></span>
            -   <span class="simpara"><span
                class="classname">ArgumentCountError</span></span>
    -   <span class="simpara"><span
        class="classname">Exception</span></span>
        -   <span class="simpara">...</span>

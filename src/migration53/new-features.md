New features
------------

PHP 5.3.0 offers a wide range of new features:

-   <span class="simpara"> Support for
    <a href="/language/namespaces.html" class="link">namespaces</a> has
    been added. </span>
-   <span class="simpara"> Support for
    <a href="/language/oop5/late-static-bindings.html" class="link">Late Static Bindings</a>
    has been added. </span>
-   <span class="simpara"> Support for
    <a href="/control-structures/goto.html" class="link">jump labels</a>
    (limited goto) has been added. </span>
-   <span class="simpara"> Support for native
    <a href="/functions/anonymous.html" class="link">Closures</a>
    (Lambda/Anonymous functions) has been added. </span>
-   <span class="simpara"> There are two new magic methods,
    <a href="/language/oop5/overloading.html#object.callstatic" class="link">__callStatic()</a>
    and
    <a href="/language/oop5/magic.html#object.invoke" class="link">__invoke()</a>.
    </span>
-   <span class="simpara">
    <a href="/language/types/string.html#language.types.string.syntax.nowdoc" class="link">Nowdoc</a>
    syntax is now supported, similar to
    <a href="/language/types/string.html#language.types.string.syntax.heredoc" class="link">Heredoc</a>
    syntax, but with single quotes. </span>
-   <span class="simpara"> It is now possible to use
    <a href="/language/types/string.html#language.types.string.syntax.heredoc" class="link">Heredoc</a>s
    to initialize static variables and class properties/constants.
    </span>
-   <span class="simpara">
    <a href="/language/types/string.html#language.types.string.syntax.heredoc" class="link">Heredoc</a>s
    may now be declared using double quotes, complementing the
    <a href="/language/types/string.html#language.types.string.syntax.nowdoc" class="link">Nowdoc</a>
    syntax. </span>
-   <span class="simpara">
    <a href="/language/constants/syntax.html" class="link">Constants</a>
    can now be declared outside a class using the *const* keyword.
    </span>
-   <span class="simpara"> The
    <a href="/language/operators/comparison.html#language.operators.comparison.ternary" class="link">ternary</a>
    operator now has a shorthand form: *?:*. </span>
-   <span class="simpara"> The HTTP stream wrapper now considers all
    status codes from 200 to 399 to be successful. </span>
-   <span class="simpara"> Dynamic access to static methods is now
    possible: </span>
    ``` php
    <?php
    class C {
       public static $foo = 123;
    }

    $a = "C";
    echo $a::$foo;
    ?>
    ```

    The above example will output:

        123
-   <span class="simpara">
    <a href="/language/exceptions.html" class="link">Exceptions</a> can
    now be nested: </span>
    ``` php
    <?php
    class MyCustomException extends Exception {}

    try {
        throw new MyCustomException("Exceptional", 112);
    } catch (Exception $e) {
        /* Note the use of the third parameter to pass $e
         * into the RuntimeException. */
        throw new RuntimeException("Rethrowing", 911, $e);
    }
    ?>
    ```
-   <span class="simpara"> A
    <a href="/features/gc.html" class="link">garbage collector</a> for
    circular references has been added, and is enabled by default.
    </span>
-   <span class="simpara"> The <span class="function">mail</span>
    function now supports logging of sent email via the
    <a href="/mail/setup.html#" class="link">mail.log</a> configuration
    directive. (Note: This only applies to email sent through this
    function.) </span>

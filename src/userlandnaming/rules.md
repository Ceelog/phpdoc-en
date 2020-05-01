Rules
-----

The following list gives an overview of which rights the PHP project
reserves for itself, when choosing names for new internal identifiers.
The definitive guide is the official
<a href="https://git.php.net/?p=php-src.git;a=blob_plain;f=CODING_STANDARDS.md;hb=HEAD" class="link external">» CODING STANDARDS</a>:

-   PHP owns the top-level namespace but tries to find decent
    descriptive names and avoid any obvious clashes.

-   Function names use underscores between words, while class names use
    both the *camelCase* and *PascalCase* rules.

-   PHP will prefix any global symbols of an extension with the name of
    the extension. (In the past, there have been numerous exceptions to
    this rule.) Examples:

    -   <span class="function">curl\_close</span>

    -   <span class="function">mysql\_query</span>

    -   PREG\_SPLIT\_DELIM\_CAPTURE

    -   new DOMDocument()

    -   <span class="function">strpos</span> (example of a past mistake)

    -   new SplFileObject()

-   Iterators and Exceptions are however simply postfixed with
    "*Iterator*" and "*Exception*." Examples:

    -   <span class="classname">ArrayIterator</span>

    -   <span class="classname">LogicException</span>

-   PHP reserves all symbols starting with *\_\_* as magical. It is
    recommended that you do not create symbols starting with *\_\_* in
    PHP unless you want to use documented magical functionality.
    Examples:

    -   <a href="/language/oop5/overloading.html#object.get" class="link">__get()</a>

    -   <span class="function">\_\_autoload</span>

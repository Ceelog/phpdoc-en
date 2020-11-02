Introduction
------------

PHP supports ten primitive types.

Four scalar types:

-   <span class="simpara"> <span class="type">bool</span> </span>
-   <span class="simpara"> <span class="type">int</span> </span>
-   <span class="simpara"> <span class="type">float</span>
    (floating-point number, aka <span class="type">double</span>)
    </span>
-   <span class="simpara"> <span class="type">string</span> </span>

Four compound types:

-   <span class="simpara"> <span class="type">array</span> </span>
-   <span class="simpara"> <span class="type">object</span> </span>
-   <span class="simpara"> <span class="type">callable</span> </span>
-   <span class="simpara"> <span class="type">iterable</span> </span>

And finally two special types:

-   <span class="simpara"> <span class="type">resource</span> </span>
-   <span class="simpara"> <span class="type">NULL</span> </span>

This manual also introduces some
<a href="/language/pseudo-types.html" class="link">pseudo-types</a> for
readability reasons:

-   <span class="simpara"> <span class="type">mixed</span> </span>
-   <span class="simpara"> <span class="type">void</span> </span>

Some references to the type "double" may remain in the manual. Consider
double the same as float; the two names exist only for historic reasons.

The type of a variable is not usually set by the programmer; rather, it
is decided at runtime by PHP depending on the context in which that
variable is used.

> **Note**: <span class="simpara"> To check the type and value of an
> <a href="/language/expressions.html" class="link">expression</a>, use
> the <span class="function">var\_dump</span> function. </span>
>
> To get a human-readable representation of a type for debugging, use
> the <span class="function">gettype</span> function. To check for a
> certain type, do *not* use <span class="function">gettype</span>, but
> rather the *is\_<span class="replaceable">type</span>* functions. Some
> examples:
>
> ``` php
> <?php
> $a_bool = TRUE;   // a boolean
> $a_str  = "foo";  // a string
> $a_str2 = 'foo';  // a string
> $an_int = 12;     // an integer
>
> echo gettype($a_bool); // prints out:  boolean
> echo gettype($a_str);  // prints out:  string
>
> // If this is an integer, increment it by four
> if (is_int($an_int)) {
>     $an_int += 4;
> }
>
> // If $a_bool is a string, print it out
> // (does not print out anything)
> if (is_string($a_bool)) {
>     echo "String: $a_bool";
> }
> ?>
> ```

To forcibly convert a variable to a certain type, either
<a href="/language/types/type-juggling.html#language.types.typecasting" class="link">cast</a>
the variable or use the <span class="function">settype</span> function
on it.

Note that a variable may be evaluated with different values in certain
situations, depending on what type it is at the time. For more
information, see the section on
<a href="/language/types/type-juggling.html" class="link">Type Juggling</a>.
<a href="/types/comparisons.html" class="link">The type comparison tables</a>
may also be useful, as they show examples of various type-related
comparisons.

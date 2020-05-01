Function Overloading Feature
============================

**Warning**

This feature has been *DEPRECATED* as of PHP 7.2.0. Relying on this
feature is highly discouraged.

You might often find it difficult to get an existing PHP application to
work in a given multibyte environment. This happens because most PHP
applications out there are written with the standard string functions
such as <span class="function">substr</span>, which are known to not
properly handle multibyte-encoded strings.

mbstring supports a 'function overloading' feature which enables you to
add multibyte awareness to such an application without code modification
by overloading multibyte counterparts on the standard string functions.
For example, <span class="function">mb\_substr</span> is called instead
of <span class="function">substr</span> if function overloading is
enabled. This feature makes it easy to port applications that only
support single-byte encodings to a multibyte environment in many cases.

To use function overloading, set *mbstring.func\_overload* in `php.ini`
to a positive value that represents a combination of bitmasks specifying
the categories of functions to be overloaded. It should be set to 1 to
overload the <span class="function">mail</span> function. 2 for string
functions, 4 for regular expression functions. For example, if it is set
to 7, mail, strings and regular expression functions will be overloaded.
The list of overloaded functions are shown below.

| value of mbstring.func\_overload | original function                            | overloaded function                              |
|----------------------------------|----------------------------------------------|--------------------------------------------------|
| 1                                | <span class="function">mail</span>           | <span class="function">mb\_send\_mail</span>     |
| 2                                | <span class="function">strlen</span>         | <span class="function">mb\_strlen</span>         |
| 2                                | <span class="function">strpos</span>         | <span class="function">mb\_strpos</span>         |
| 2                                | <span class="function">strrpos</span>        | <span class="function">mb\_strrpos</span>        |
| 2                                | <span class="function">substr</span>         | <span class="function">mb\_substr</span>         |
| 2                                | <span class="function">strtolower</span>     | <span class="function">mb\_strtolower</span>     |
| 2                                | <span class="function">strtoupper</span>     | <span class="function">mb\_strtoupper</span>     |
| 2                                | <span class="function">stripos</span>        | <span class="function">mb\_stripos</span>        |
| 2                                | <span class="function">strripos</span>       | <span class="function">mb\_strripos</span>       |
| 2                                | <span class="function">strstr</span>         | <span class="function">mb\_strstr</span>         |
| 2                                | <span class="function">stristr</span>        | <span class="function">mb\_stristr</span>        |
| 2                                | <span class="function">strrchr</span>        | <span class="function">mb\_strrchr</span>        |
| 2                                | <span class="function">substr\_count</span>  | <span class="function">mb\_substr\_count</span>  |
| 4                                | <span class="function">ereg</span>           | <span class="function">mb\_ereg</span>           |
| 4                                | <span class="function">eregi</span>          | <span class="function">mb\_eregi</span>          |
| 4                                | <span class="function">ereg\_replace</span>  | <span class="function">mb\_ereg\_replace</span>  |
| 4                                | <span class="function">eregi\_replace</span> | <span class="function">mb\_eregi\_replace</span> |
| 4                                | <span class="function">split</span>          | <span class="function">mb\_split</span>          |

> **Note**:
>
> It is not recommended to use the function overloading option in the
> per-directory context, because it's not confirmed yet to be stable
> enough in a production environment and may lead to undefined
> behaviour.

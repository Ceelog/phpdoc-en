How to read a function definition (prototype)
---------------------------------------------

Each function in the manual is documented for quick reference. Knowing
how to read and understand the text will make learning PHP much easier.
Rather than relying on examples or cut/paste, everyone should know how
to read function definitions (prototypes). Let's begin:

> **Note**: **Prerequisite: Basic understanding of
> <a href="/language/types.html" class="link">types</a>**  
>
> Although PHP is a loosely typed language, it's important to have a
> basic understanding of
> <a href="/language/types.html" class="link">types</a> as they have
> important meaning.

Function definitions tell us what type of value is
<a href="/functions/returning-values.html" class="link">returned</a>.
Let's use the definition for <span class="function">strlen</span> as our
first example:

    strlen

    (PHP 4, PHP 5)
    strlen -- Get string length

    Description
    strlen ( string $string ) : int

    Returns the length of given string.

| Part               | Description                                                                                                                                |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| strlen             | The function name.                                                                                                                         |
| (PHP 4, PHP 5)     | strlen() has been around in all versions of PHP 4 and PHP 5                                                                                |
| ( string $string ) | The first (and in this case the only) parameter/argument for this function is named `string`, and it's a <span class="type">string</span>. |
| int                | Type of value this function returns, which is an <span class="type">int</span> (i.e. the length of a string is measured in numbers).       |

We could rewrite the above function definition in a generic way:

          function name    ( parameter type   parameter name ) : returned type

Many functions take on multiple parameters, such as <span
class="function">in\_array</span>. Its prototype is as follows:

          in_array ( mixed $needle, array $haystack [, bool $strict = FALSE ] ) : bool

What does this mean? in\_array() returns a
<a href="/language/types/boolean.html" class="link">boolean</a> value,
**`true`** on success (if the `needle` was found in the `haystack`) or
**`false`** on failure (if the `needle` was not found in the
`haystack`). The first parameter is named `needle` and it can be of many
different <a href="/language/types.html" class="link">types</a>, so we
call it "*mixed*". This mixed `needle` (what we're looking for) can be
either a scalar value (string, integer, or
<a href="/language/types/float.html" class="link">float</a>), or an
<a href="/language/types/array.html" class="link">array</a>. `haystack`
(the array we're searching in) is the second parameter. The third
*optional* parameter is named `strict`. All optional parameters are seen
in *\[* brackets *\]*. The manual states that the `strict` parameter
defaults to boolean **`false`**. See the manual page on each function
for details on how they work.

In addition the & (ampersand) symbol prepended to a function parameter
allows the parameter to be passed by
<a href="/language/references/pass.html" class="link">reference</a>, as
seen below:

           preg_match ( string $pattern , string $subject [, array &$matches
          [, int $flags = 0 [, int $offset = 0 ]]] ) : int

In this example, we can see the third optional parameter `&$matches`
will be passed as reference.

There are also functions with more complex PHP version information. Take
<span class="function">html\_entity\_decode</span> as an example:

    (PHP 4 >= 4.3.0, PHP 5)

This means that this function has only been available in a released
version since PHP 4.3.0.

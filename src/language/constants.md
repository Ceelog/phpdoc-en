Constants
=========

**Table of Contents**

-   [Syntax](/language/constants/syntax.html)
-   [Magic constants](/language/constants/predefined.html)

A constant is an identifier (name) for a simple value. As the name
suggests, that value cannot change during the execution of the script
(except for
<a href="/language/constants/predefined.html" class="link">magic constants</a>,
which aren't actually constants). Constants are case-sensitive. By
convention, constant identifiers are always uppercase.

> **Note**:
>
> Prior to PHP 8.0.0, constants defined using the <span
> class="function">define</span> function may be case-insensitive.

The name of a constant follows the same rules as any label in PHP. A
valid constant name starts with a letter or underscore, followed by any
number of letters, numbers, or underscores. As a regular expression, it
would be expressed thusly: `^[a-zA-Z_\x80-\xff][a-zA-Z0-9_\x80-\xff]*$`

It is possible to <span class="function">define</span> constants with
reserved or even invalid names, whose value can only be retrieved with
the <span class="function">constant</span> function. However, doing so
is not recommended.

**Tip**

See also the
<a href="/userlandnaming.html" class="xref">Userland Naming Guide</a>.

**Example \#1 Valid and invalid constant names**

``` php
<?php

// Valid constant names
define("FOO",     "something");
define("FOO2",    "something else");
define("FOO_BAR", "something more");

// Invalid constant names
define("2FOO",    "something");

// This is valid, but should be avoided:
// PHP may one day provide a magical constant
// that will break your script
define("__FOO__", "something"); 

?>
```

> **Note**: <span class="simpara"> For our purposes here, a letter is
> a-z, A-Z, and the ASCII characters from 128 through 255 (0x80-0xff).
> </span>

Like
<a href="/language/variables/predefined.html" class="link">superglobals</a>,
the scope of a constant is global. Constants can be accessed from
anywhere in a script without regard to scope. For more information on
scope, read the manual section on
<a href="/language/variables/scope.html" class="link">variable scope</a>.

> **Note**: <span class="simpara"> As of PHP 7.4.0, class constant may
> declare a visibility of protected or private, making them only
> available in the hierarchical scope of the class in which it is is
> defined. </span>

Deprecated features in PHP 7.2.x
--------------------------------

### Unquoted strings

Unquoted strings that are non-existent global constants are taken to be
strings of themselves. This behaviour used to emit an **`E_NOTICE`**,
but will now emit an **`E_WARNING`**. In the next major version of PHP,
an <span class="classname">Error</span> exception will be thrown
instead.

``` php
<?php

var_dump(NONEXISTENT);

/* Output:
Warning: Use of undefined constant NONEXISTENT - assumed 'NONEXISTENT' (this will throw an Error in a future version of PHP) in %s on line %d
string(11) "NONEXISTENT"
*/
```

### <span class="function">png2wbmp</span> and <span class="function">jpeg2wbmp</span>

The <span class="function">png2wbmp</span> and <span
class="function">jpeg2wbmp</span> functions from the GD extension have
now been deprecated and will be removed in the next major version of
PHP.

### **`INTL_IDNA_VARIANT_2003`** variant

The Intl extension has deprecated the **`INTL_IDNA_VARIANT_2003`**
variant, which is currently being used as the default for <span
class="function">idn\_to\_ascii</span> and <span
class="function">idn\_to\_utf8</span>. PHP 7.4 will see these defaults
changed to **`INTL_IDNA_VARIANT_UTS46`**, and the next major version of
PHP will remove **`INTL_IDNA_VARIANT_2003`** altogether.

### <span class="function">\_\_autoload</span> method

The <span class="function">\_\_autoload</span> method has been
deprecated because it is inferior to <span
class="function">spl\_autoload\_register</span> (due to it not being
able to chain autoloaders), and there is no interoperability between the
two autoloading styles.

### `track_errors` ini setting and *$php\_errormsg* variable

When the `track_errors` ini setting is enabled, a *$php\_errormsg*
variable is created in the local scope when a non-fatal error occurs.
Given that the preferred way of retrieving such error information is by
using <span class="function">error\_get\_last</span>, this feature has
been deprecated.

### <span class="function">create\_function</span> function

Given the security issues of this function (being a thin wrapper around
<span class="function">eval</span>), this dated function has now been
deprecated. The preferred alternative is to use
<a href="/functions/anonymous.html" class="link">anonymous functions</a>.

### `mbstring.func_overload` ini setting

Given the interoperability problems of string-based functions being used
in environments with this setting enabled, it has now been deprecated.

### *(unset)* cast

Casting any expression to this type will always result in **`null`**,
and so this superfluous casting type has now been deprecated.

### <span class="function">parse\_str</span> without a second argument

Without the second argument to <span class="function">parse\_str</span>,
the query string parameters would populate the local symbol table. Given
the security implications of this, using <span
class="function">parse\_str</span> without a second argument has now
been deprecated. The function should always be used with two arguments,
as the second argument causes the query string to be parsed into an
array.

### <span class="function">gmp\_random</span> function

This function generates a random number based upon a range that is
calculated by an unexposed, platform-specific limb size. Because of
this, the function has now been deprecated. The preferred way of
generating a random number using the GMP extension is by <span
class="function">gmp\_random\_bits</span> and <span
class="function">gmp\_random\_range</span>.

### <span class="function">each</span> function

This function is far slower at iteration than a normal *foreach*, and
causes implementation issues for some language changes. It has therefore
been deprecated.

### <span class="function">assert</span> with a string argument

Using <span class="function">assert</span> with a string argument
required the string to be <span class="function">eval</span>'ed. Given
the potential for remote code execution, using <span
class="function">assert</span> with a string argument has now been
deprecated in favour of using boolean expressions.

### *$errcontext* argument of error handlers

The *$errcontext* argument contains all local variables of the error
site. Given its rare usage, and the problems it causes with internal
optimisations, it has now been deprecated. Instead, a debugger should be
used to retrieve information on local variables at the error site.

### <span class="function">read\_exif\_data</span> function

The <span class="function">read\_exif\_data</span> alias has been
deprecated. The <span class="function">exif\_read\_data</span> function
should be used instead.

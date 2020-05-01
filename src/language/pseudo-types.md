Pseudo-types and variables used in this documentation
-----------------------------------------------------

Pseudo-types are keywords used in the PHP documentation to specify the
types or values an argument can have. Please note that they are not
primitives of the PHP language. So you cannot use pseudo-types as
typehints in your own custom functions.

### mixed

*mixed* indicates that a parameter may accept multiple (but not
necessarily all) types.

<span class="function">gettype</span> for example will accept all PHP
types, while <span class="function">str\_replace</span> will accept
<span class="type">string</span>s and <span class="type">array</span>s.

### number

*number* indicates that a parameter can be either <span
class="type">integer</span> or <span class="type">float</span>.

### callback

<span class="type">callback</span> pseudo-types was used in this
documentation before <span class="type">callable</span> type hint was
introduced by PHP 5.4. It means exactly the same.

### array\|object

*array\|object* indicates that a parameter can be either <span
class="type">array</span> or <span class="type">object</span>.

### void

*void* as a return type means that the return value is useless. *void*
in a parameter list means that the function doesn't accept any
parameters. As of PHP 7.1 *void* is accepted as a function return type
hint.

### ...

`$...` in function prototypes means *and so on*. This variable name is
used when a function can take an endless number of arguments.

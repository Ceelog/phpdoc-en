Basics
------

Variables in PHP are represented by a dollar sign followed by the name
of the variable. The variable name is case-sensitive.

Variable names follow the same rules as other labels in PHP. A valid
variable name starts with a letter or underscore, followed by any number
of letters, numbers, or underscores. As a regular expression, it would
be expressed thus: `^[a-zA-Z_\x80-\xff][a-zA-Z0-9_\x80-\xff]*$`

> **Note**: <span class="simpara"> For our purposes here, a letter is
> a-z, A-Z, and the bytes from 128 through 255 (*0x80-0xff*). </span>

> **Note**: <span class="simpara"> *$this* is a special variable that
> can't be assigned. Prior to PHP 7.1.0, indirect assignment (e.g. by
> using
> <a href="/language/variables/variable.html" class="link">variable variables</a>)
> was possible. </span>

**Tip**

See also the
<a href="/userlandnaming.html" class="xref">Userland Naming Guide</a>.

For information on variable related functions, see the
<a href="/ref/var.html" class="link">Variable Functions Reference</a>.

``` php
<?php
$var = 'Bob';
$Var = 'Joe';
echo "$var, $Var";      // outputs "Bob, Joe"

$4site = 'not yet';     // invalid; starts with a number
$_4site = 'not yet';    // valid; starts with an underscore
$täyte = 'mansikka';    // valid; 'ä' is (Extended) ASCII 228.
?>
```

By default, variables are always assigned by value. That is to say, when
you assign an expression to a variable, the entire value of the original
expression is copied into the destination variable. This means, for
instance, that after assigning one variable's value to another, changing
one of those variables will have no effect on the other. For more
information on this kind of assignment, see the chapter on
<a href="/language/expressions.html" class="link">Expressions</a>.

PHP also offers another way to assign values to variables:
<a href="/language/references.html" class="link">assign by reference</a>.
This means that the new variable simply references (in other words,
"becomes an alias for" or "points to") the original variable. Changes to
the new variable affect the original, and vice versa.

To assign by reference, simply prepend an ampersand (&) to the beginning
of the variable which is being assigned (the source variable). For
instance, the following code snippet outputs '*My name is Bob*' twice:

``` php
<?php
$foo = 'Bob';              // Assign the value 'Bob' to $foo
$bar = &$foo;              // Reference $foo via $bar.
$bar = "My name is $bar";  // Alter $bar...
echo $bar;
echo $foo;                 // $foo is altered too.
?>
```

One important thing to note is that only named variables may be assigned
by reference.

``` php
<?php
$foo = 25;
$bar = &$foo;      // This is a valid assignment.
$bar = &(24 * 7);  // Invalid; references an unnamed expression.

function test()
{
   return 25;
}

$bar = &test();    // Invalid.
?>
```

It is not necessary to initialize variables in PHP however it is a very
good practice. Uninitialized variables have a default value of their
type depending on the context in which they are used - booleans default
to **`FALSE`**, integers and floats default to zero, strings (e.g. used
in <span class="function">echo</span>) are set as an empty string and
arrays become to an empty array.

**Example \#1 Default values of uninitialized variables**

``` php
<?php
// Unset AND unreferenced (no use context) variable; outputs NULL
var_dump($unset_var);

// Boolean usage; outputs 'false' (See ternary operators for more on this syntax)
echo($unset_bool ? "true\n" : "false\n");

// String usage; outputs 'string(3) "abc"'
$unset_str .= 'abc';
var_dump($unset_str);

// Integer usage; outputs 'int(25)'
$unset_int += 25; // 0 + 25 => 25
var_dump($unset_int);

// Float/double usage; outputs 'float(1.25)'
$unset_float += 1.25;
var_dump($unset_float);

// Array usage; outputs array(1) {  [3]=>  string(3) "def" }
$unset_arr[3] = "def"; // array() + array(3 => "def") => array(3 => "def")
var_dump($unset_arr);

// Object usage; creates new stdClass object (see http://www.php.net/manual/en/reserved.classes.php)
// Outputs: object(stdClass)#1 (1) {  ["foo"]=>  string(3) "bar" }
$unset_obj->foo = 'bar';
var_dump($unset_obj);
?>
```

Relying on the default value of an uninitialized variable is problematic
in the case of including one file into another which uses the same
variable name. It is also a major
<a href="/security/globals.html" class="link">security risk</a> with
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
turned on. <a href="" class="link">E_NOTICE</a> level error is issued in
case of working with uninitialized variables, however not in the case of
appending elements to the uninitialized array. <span
class="function">isset</span> language construct can be used to detect
if a variable has been already initialized.

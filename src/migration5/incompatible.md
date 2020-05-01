Backward Incompatible Changes
-----------------------------

Although most existing PHP 4 code should work without changes, you
should pay attention to the following backward incompatible changes:

-   <span class="simpara"> There are some
    <a href="/reserved/keywords.html" class="link">new reserved keywords</a>.
    </span>
-   <span class="simpara"> <span class="function">strrpos</span> and
    <span class="function">strripos</span> now use the entire string as
    a needle. </span>
-   <span class="simpara"> Illegal use of string offsets causes
    **`E_ERROR`** instead of **`E_WARNING`**. An example illegal use is:
    *$str = 'abc'; unset($str\[0\]);*. </span>
-   <span class="simpara"> <span class="function">array\_merge</span>
    was changed to accept only arrays. If a non-array variable is
    passed, a **`E_WARNING`** will be thrown for every such parameter.
    Be careful because your code may start emitting **`E_WARNING`** out
    of the blue. </span>
-   <span class="simpara"> **`PATH_TRANSLATED`** server variable is no
    longer set implicitly under Apache2 SAPI in contrast to the
    situation in PHP 4, where it is set to the same value as the
    **`SCRIPT_FILENAME`** server variable when it is not populated by
    Apache. This change was made to comply with the
    <a href="http://www.faqs.org/rfcs/rfc3875" class="link external">» CGI/1.1 specification</a>.
    Please refer to
    <a href="https://bugs.php.net/23610" class="link external">» bug #23610</a>
    for further information, and see also the
    `$_SERVER['PATH_TRANSLATED']` description in the manual. This issue
    also affects PHP versions \>= 4.3.2. </span>
-   <span class="simpara"> The **`T_ML_COMMENT`** constant is no longer
    defined by the
    <a href="/ref/tokenizer.html" class="link">Tokenizer</a> extension.
    If error\_reporting is set to **`E_ALL`**, PHP will generate a
    notice. Although the **`T_ML_COMMENT`** was never used at all, it
    was defined in PHP 4. In both PHP 4 and PHP 5 // and /\* \*/ are
    resolved as the **`T_COMMENT`** constant. However the PHPDoc style
    comments */\*\* \*/*, which starting PHP 5 are parsed by PHP, are
    recognized as **`T_DOC_COMMENT`**. </span>
-   <span class="simpara"> `$_SERVER` should be populated with `argc`
    and `argv` if
    <a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
    includes "S". If you have specifically configured your system to not
    create `$_SERVER`, then of course it shouldn't be there. The change
    was to always make `argc` and `argv` available in the CLI version
    regardless of the
    <a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
    setting. As in, the CLI version will now always populate the global
    `$argc` and `$argv` variables. </span>
-   <span class="simpara"> An object with no properties is no longer
    considered "empty". </span>
-   <span class="simpara"> In some cases classes must be declared before
    use. It only happens if some of the new features of PHP 5 (such as
    <a href="/language/oop5/interfaces.html" class="link">interfaces</a>)
    are used. Otherwise the behaviour is the old. </span>
-   <span class="simpara"> <span class="function">get\_class</span>,
    <span class="function">get\_parent\_class</span> and <span
    class="function">get\_class\_methods</span> now return the name of
    the classes/methods as they were declared (case-sensitive) which may
    lead to problems in older scripts that rely on the previous
    behaviour (the class/method name was always returned lowercased). A
    possible solution is to search for those functions in all your
    scripts and use <span class="function">strtolower</span>. </span>
    <span class="simpara"> This case sensitivity change also applies to
    the
    <a href="/language/constants/predefined.html" class="link">magical predefined constants</a>
    **`__CLASS__`**, **`__METHOD__`**, and **`__FUNCTION__`**. The
    values are returned exactly as they're declared (case-sensitive).
    </span>
-   <span class="simpara"> <span class="function">ip2long</span> now
    returns **`FALSE`** when an invalid IP address is passed as argument
    to the function, and no longer *-1*. </span>
-   <span class="simpara"> If there are functions defined in the
    included file, they can be used in the main file independent if they
    are before <span class="function">return</span> or after. If the
    file is included twice, PHP 5 issues fatal error because functions
    were already declared, while PHP 4 doesn't complain about it. It is
    recommended to use <span class="function">include\_once</span>
    instead of checking if the file was already included and
    conditionally return inside the included file. </span>
-   <span class="simpara"> <span class="function">include\_once</span>
    and <span class="function">require\_once</span> first normalize the
    path of included file on Windows so that including A.php and a.php
    include the file just once. </span>
-   <span class="simpara"> Passing an array to a function by value no
    longer resets the array's internal pointer for array accesses made
    within the function. In other words, in PHP 4 when you passed an
    array to a function, its internal pointer inside the function would
    be reset, while in PHP 5, when you pass an array to a function, its
    array pointer within the function will be wherever it was when the
    array was passed to the function. </span>

**Example \#1 <span class="function">strrpos</span> and <span
class="function">strripos</span> now use the entire string as a needle**

``` php
<?php
var_dump(strrpos('ABCDEF','DEF')); //int(3)

var_dump(strrpos('ABCDEF','DAF')); //bool(false)
?>
```

**Example \#2 An object with no properties is no longer considered
"empty"**

``` php
<?php
class test { }
$t = new test();

var_dump(empty($t)); // echo bool(false)

if ($t) {
    // Will be executed
}
?>
```

**Example \#3 In some cases classes must be declared before used**

``` php
<?php

//works with no errors:
$a = new a();
class a {
}


//throws an error:
$a = new b();

interface c{
}
class b implements c {
} 

?>
```

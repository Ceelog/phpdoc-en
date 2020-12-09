PHP type comparison tables
==========================

The following tables demonstrate behaviors of PHP
<a href="/language/types.html" class="link">types</a> and
<a href="/language/operators/comparison.html" class="link">comparison operators</a>,
for both loose and strict comparisons. This supplemental is also related
to the manual section on
<a href="/language/types/type-juggling.html" class="link">type juggling</a>.
Inspiration was provided by various user comments and by the work over
at
<a href="http://www.blueshoes.org/en/developer/php_cheat_sheet/" class="link external">» BlueShoes</a>.

Before utilizing these tables, it's important to understand types and
their meanings. For example, *"42"* is a <span
class="type">string</span> while *42* is an <span
class="type">int</span>. **`false`** is a <span class="type">bool</span>
while *"false"* is a <span class="type">string</span>.

> **Note**:
>
> HTML Forms do not pass integers, floats, or booleans; they pass
> strings. To find out if a string is numeric, you may use <span
> class="function">is\_numeric</span>.

> **Note**:
>
> Simply doing *if ($x)* while `$x` is undefined will generate an error
> of level **`E_NOTICE`**. Instead, consider using <span
> class="function">empty</span> or <span class="function">isset</span>
> and/or initialize your variables.

> **Note**:
>
> Some numeric operations can result in a value represented by the
> constant **`NAN`**. Any loose or strict comparisons of this value
> against any other value, including itself, but except **`true`**, will
> have a result of **`false`**. (i.e. *NAN != NAN* and *NAN !== NAN*)
> Examples of operations that produce **`NAN`** include *sqrt(-1)*,
> *asin(2)*, and *acosh(0)*.

| Expression              | <span class="function">gettype</span> | <span class="function">empty</span> | <span class="function">is\_null</span> | <span class="function">isset</span> | <span class="type">bool</span> : *if($x)* |
|-------------------------|---------------------------------------|-------------------------------------|----------------------------------------|-------------------------------------|-------------------------------------------|
| *$x = "";*              | <span class="type">string</span>      | **`true`**                          | **`false`**                            | **`true`**                          | **`false`**                               |
| *$x = null;*            | <span class="type">NULL</span>        | **`true`**                          | **`true`**                             | **`false`**                         | **`false`**                               |
| *var $x;*               | <span class="type">NULL</span>        | **`true`**                          | **`true`**                             | **`false`**                         | **`false`**                               |
| `$x` is undefined       | <span class="type">NULL</span>        | **`true`**                          | **`true`**                             | **`false`**                         | **`false`**                               |
| *$x = array();*         | <span class="type">array</span>       | **`true`**                          | **`false`**                            | **`true`**                          | **`false`**                               |
| *$x = array('a', 'b');* | <span class="type">array</span>       | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = false;*           | <span class="type">bool</span>        | **`true`**                          | **`false`**                            | **`true`**                          | **`false`**                               |
| *$x = true;*            | <span class="type">bool</span>        | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = 1;*               | <span class="type">int</span>         | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = 42;*              | <span class="type">int</span>         | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = 0;*               | <span class="type">int</span>         | **`true`**                          | **`false`**                            | **`true`**                          | **`false`**                               |
| *$x = -1;*              | <span class="type">int</span>         | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = "1";*             | <span class="type">string</span>      | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = "0";*             | <span class="type">string</span>      | **`true`**                          | **`false`**                            | **`true`**                          | **`false`**                               |
| *$x = "-1";*            | <span class="type">string</span>      | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = "php";*           | <span class="type">string</span>      | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = "true";*          | <span class="type">string</span>      | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |
| *$x = "false";*         | <span class="type">string</span>      | **`false`**                         | **`false`**                            | **`true`**                          | **`true`**                                |

|             | **`true`**  | **`false`** | *1*         | *0*         | *-1*        | *"1"*       | *"0"*       | *"-1"*      | **`null`**  | *array()*   | *"php"*     | *""*        |
|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|
| **`true`**  | **`true`**  | **`false`** | **`true`**  | **`false`** | **`true`**  | **`true`**  | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** |
| **`false`** | **`false`** | **`true`**  | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** | **`true`**  | **`true`**  | **`false`** | **`true`**  |
| *1*         | **`true`**  | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *0*         | **`false`** | **`true`**  | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** | **`true`**  | **`false`** | **`true`**  | **`true`**  |
| *-1*        | **`true`**  | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** |
| *"1"*       | **`true`**  | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *"0"*       | **`false`** | **`true`**  | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *"-1"*      | **`true`**  | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** |
| **`null`**  | **`false`** | **`true`**  | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`true`**  | **`false`** | **`true`**  |
| *array()*   | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`true`**  | **`false`** | **`false`** |
| *"php"*     | **`true`**  | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** |
| *""*        | **`false`** | **`true`**  | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`true`**  |

|             | **`true`**  | **`false`** | *1*         | *0*         | *-1*        | *"1"*       | *"0"*       | *"-1"*      | **`null`**  | *array()*   | *"php"*     | *""*        |
|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|
| **`true`**  | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *1*         | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *0*         | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *-1*        | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *"1"*       | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *"0"*       | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** |
| *"-1"*      | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** | **`false`** |
| **`null`**  | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** | **`false`** |
| *array()*   | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** | **`false`** |
| *"php"*     | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  | **`false`** |
| *""*        | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`false`** | **`true`**  |

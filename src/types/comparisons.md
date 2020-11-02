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
class="type">int</span>. **`FALSE`** is a <span class="type">bool</span>
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
> against any other value, including itself, but except **`TRUE`**, will
> have a result of **`FALSE`**. (i.e. *NAN != NAN* and *NAN !== NAN*)
> Examples of operations that produce **`NAN`** include *sqrt(-1)*,
> *asin(2)*, and *acosh(0)*.

| Expression              | <span class="function">gettype</span> | <span class="function">empty</span> | <span class="function">is\_null</span> | <span class="function">isset</span> | <span class="type">bool</span> : *if($x)* |
|-------------------------|---------------------------------------|-------------------------------------|----------------------------------------|-------------------------------------|-------------------------------------------|
| *$x = "";*              | <span class="type">string</span>      | **`TRUE`**                          | **`FALSE`**                            | **`TRUE`**                          | **`FALSE`**                               |
| *$x = null;*            | <span class="type">NULL</span>        | **`TRUE`**                          | **`TRUE`**                             | **`FALSE`**                         | **`FALSE`**                               |
| *var $x;*               | <span class="type">NULL</span>        | **`TRUE`**                          | **`TRUE`**                             | **`FALSE`**                         | **`FALSE`**                               |
| `$x` is undefined       | <span class="type">NULL</span>        | **`TRUE`**                          | **`TRUE`**                             | **`FALSE`**                         | **`FALSE`**                               |
| *$x = array();*         | <span class="type">array</span>       | **`TRUE`**                          | **`FALSE`**                            | **`TRUE`**                          | **`FALSE`**                               |
| *$x = array('a', 'b');* | <span class="type">array</span>       | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = false;*           | <span class="type">bool</span>        | **`TRUE`**                          | **`FALSE`**                            | **`TRUE`**                          | **`FALSE`**                               |
| *$x = true;*            | <span class="type">bool</span>        | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = 1;*               | <span class="type">int</span>         | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = 42;*              | <span class="type">int</span>         | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = 0;*               | <span class="type">int</span>         | **`TRUE`**                          | **`FALSE`**                            | **`TRUE`**                          | **`FALSE`**                               |
| *$x = -1;*              | <span class="type">int</span>         | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = "1";*             | <span class="type">string</span>      | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = "0";*             | <span class="type">string</span>      | **`TRUE`**                          | **`FALSE`**                            | **`TRUE`**                          | **`FALSE`**                               |
| *$x = "-1";*            | <span class="type">string</span>      | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = "php";*           | <span class="type">string</span>      | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = "true";*          | <span class="type">string</span>      | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |
| *$x = "false";*         | <span class="type">string</span>      | **`FALSE`**                         | **`FALSE`**                            | **`TRUE`**                          | **`TRUE`**                                |

|             | **`TRUE`**  | **`FALSE`** | *1*         | *0*         | *-1*        | *"1"*       | *"0"*       | *"-1"*      | **`NULL`**  | *array()*   | *"php"*     | *""*        |
|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|
| **`TRUE`**  | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** |
| **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`TRUE`**  | **`FALSE`** | **`TRUE`**  |
| *1*         | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *0*         | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`TRUE`**  |
| *-1*        | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *"1"*       | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *"0"*       | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *"-1"*      | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| **`NULL`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`TRUE`**  | **`FALSE`** | **`TRUE`**  |
| *array()*   | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`TRUE`**  | **`FALSE`** | **`FALSE`** |
| *"php"*     | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** |
| *""*        | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`TRUE`**  |

|             | **`TRUE`**  | **`FALSE`** | *1*         | *0*         | *-1*        | *"1"*       | *"0"*       | *"-1"*      | **`NULL`**  | *array()*   | *"php"*     | *""*        |
|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|-------------|
| **`TRUE`**  | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *1*         | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *0*         | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *-1*        | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *"1"*       | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *"0"*       | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *"-1"*      | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| **`NULL`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** | **`FALSE`** |
| *array()*   | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** | **`FALSE`** |
| *"php"*     | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  | **`FALSE`** |
| *""*        | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`FALSE`** | **`TRUE`**  |

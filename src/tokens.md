List of Parser Tokens
=====================

Various parts of the PHP language are represented internally by types
like T\_SR. PHP outputs identifiers like this one in parse errors, like
*"Parse error: unexpected T\_SR, expecting ',' or ';' in script.php on
line 10."*

You're supposed to know what T\_SR means. For everybody who doesn't know
that, here is a table with those identifiers, PHP-syntax and references
to the appropriate places in the manual.

> **Note**: **Usage of T\_\* constants**  
>
> All tokens listed below are also defined as PHP constants. Their value
> is automatically generated based on PHP's underlying parser
> infrastructure. This means that the concrete value of a token may
> change between two PHP versions. For example the **`T_FILE`** constant
> is *365* in PHP 5.3, while the same value refers now to **`T_TRAIT`**
> in PHP 5.4 and the value of **`T_FILE`** is *369*. This means that
> your code should never rely directly on the original T\_\* values
> taken from PHP version X.Y.Z, to provide some compatibility across
> multiple PHP versions. Instead your code should utilize custom values
> (using big numbers like *10000*) and an appropriate strategy that will
> work with both PHP versions and T\_\* values.

| Token                            | Syntax                      | Reference                                                                                                                                                      |
|----------------------------------|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`T_ABSTRACT`**                 | abstract                    | <a href="/language/oop5/abstract.html" class="xref">Class Abstraction</a>                                                                                      |
| **`T_AND_EQUAL`**                | &=                          | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_ARRAY`**                    | array()                     | <span class="function">array</span>, <a href="/language/types/array.html#language.types.array.syntax" class="link">array syntax</a>                            |
| **`T_ARRAY_CAST`**               | (array)                     | <a href="/language/types/type-juggling.html#language.types.typecasting" class="link">type-casting</a>                                                          |
| **`T_AS`**                       | as                          | <a href="/control-structures/foreach.html" class="link">foreach</a>                                                                                            |
| **`T_BAD_CHARACTER`**            |                             | anything below ASCII 32 except \\t (0x09), \\n (0x0a) and \\r (0x0d) (available since PHP 7.4.0, and also before PHP 7.0.0 but not used)                       |
| **`T_BOOLEAN_AND`**              | &&                          | <a href="/language/operators/logical.html" class="link">logical operators</a>                                                                                  |
| **`T_BOOLEAN_OR`**               | \|\|                        | <a href="/language/operators/logical.html" class="link">logical operators</a>                                                                                  |
| **`T_BOOL_CAST`**                | (bool) or (boolean)         | <a href="/language/types/type-juggling.html#language.types.typecasting" class="link">type-casting</a>                                                          |
| **`T_BREAK`**                    | break                       | <a href="/control-structures/break.html" class="link">break</a>                                                                                                |
| **`T_CALLABLE`**                 | callable                    | <a href="/language/types/callable.html" class="link">callable</a> (available since PHP 5.4.0)                                                                  |
| **`T_CASE`**                     | case                        | <a href="/control-structures/switch.html" class="link">switch</a>                                                                                              |
| **`T_CATCH`**                    | catch                       | <a href="/language/exceptions.html" class="xref">Exceptions</a>                                                                                                |
| **`T_CHARACTER`**                |                             | not used anymore (removed in PHP 7.0.0)                                                                                                                        |
| **`T_CLASS`**                    | class                       | <a href="/language/oop5.html" class="link">classes and objects</a>                                                                                             |
| **`T_CLASS_C`**                  | \_\_CLASS\_\_               | <a href="/language/constants/predefined.html" class="link">magic constants</a>                                                                                 |
| **`T_CLONE`**                    | clone                       | <a href="/language/oop5.html" class="link">classes and objects</a>                                                                                             |
| **`T_CLOSE_TAG`**                | ?\> or %\>                  | <a href="/language/basic-syntax/phpmode.html" class="link">escaping from HTML</a>                                                                              |
| **`T_COALESCE`**                 | ??                          | <a href="/language/operators/comparison.html#language.operators.comparison.coalesce" class="link">comparison operators</a> (available since PHP 7.0.0)         |
| **`T_COALESCE_EQUAL`**           | ??=                         | <a href="/language/operators/assignment.html" class="link">assignment operators</a> (available since PHP 7.4.0)                                                |
| **`T_COMMENT`**                  | // or \#, and /\* \*/       | <a href="/language/basic-syntax/comments.html" class="link">comments</a>                                                                                       |
| **`T_CONCAT_EQUAL`**             | .=                          | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_CONST`**                    | const                       | <a href="/language/constants.html" class="link">class constants</a>                                                                                            |
| **`T_CONSTANT_ENCAPSED_STRING`** | "foo" or 'bar'              | <a href="/language/types/string.html#language.types.string.syntax" class="link">string syntax</a>                                                              |
| **`T_CONTINUE`**                 | continue                    | <a href="/control-structures/continue.html" class="link">continue</a>                                                                                          |
| **`T_CURLY_OPEN`**               | {$                          | <a href="/language/types/string.html#language.types.string.parsing.complex" class="link">complex variable parsed syntax</a>                                    |
| **`T_DEC`**                      | --                          | <a href="/language/operators/increment.html" class="link">incrementing/decrementing operators</a>                                                              |
| **`T_DECLARE`**                  | declare                     | <a href="/control-structures/declare.html" class="link">declare</a>                                                                                            |
| **`T_DEFAULT`**                  | default                     | <a href="/control-structures/switch.html" class="link">switch</a>                                                                                              |
| **`T_DIR`**                      | \_\_DIR\_\_                 | <a href="/language/constants/predefined.html" class="link">magic constants</a> (available since PHP 5.3.0)                                                     |
| **`T_DIV_EQUAL`**                | /=                          | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_DNUMBER`**                  | 0.12, etc.                  | <a href="/language/types/float.html" class="link">floating point numbers</a>                                                                                   |
| **`T_DO`**                       | do                          | <a href="/control-structures/do/while.html" class="link">do..while</a>                                                                                         |
| **`T_DOC_COMMENT`**              | /\*\* \*/                   | <a href="/language/basic-syntax/comments.html" class="link">PHPDoc style comments</a>                                                                          |
| **`T_DOLLAR_OPEN_CURLY_BRACES`** | ${                          | <a href="/language/types/string.html#language.types.string.parsing.complex" class="link">complex variable parsed syntax</a>                                    |
| **`T_DOUBLE_ARROW`**             | =\>                         | <a href="/language/types/array.html#language.types.array.syntax" class="link">array syntax</a>                                                                 |
| **`T_DOUBLE_CAST`**              | (real), (double) or (float) | <a href="/language/types/type-juggling.html#language.types.typecasting" class="link">type-casting</a>                                                          |
| **`T_DOUBLE_COLON`**             | ::                          | see **`T_PAAMAYIM_NEKUDOTAYIM`** below                                                                                                                         |
| **`T_ECHO`**                     | echo                        | <span class="function">echo</span>                                                                                                                             |
| **`T_ELLIPSIS`**                 | ...                         | <a href="/functions/arguments.html#functions.variable-arg-list.new" class="link">function arguments</a> (available since PHP 5.6.0)                            |
| **`T_ELSE`**                     | else                        | <a href="/control-structures/else.html" class="link">else</a>                                                                                                  |
| **`T_ELSEIF`**                   | elseif                      | <a href="/control-structures/elseif.html" class="link">elseif</a>                                                                                              |
| **`T_EMPTY`**                    | empty                       | <span class="function">empty</span>                                                                                                                            |
| **`T_ENCAPSED_AND_WHITESPACE`**  | " $a"                       | <a href="/language/types/string.html#language.types.string.parsing" class="link">constant part of string with variables</a>                                    |
| **`T_ENDDECLARE`**               | enddeclare                  | <a href="/control-structures/declare.html" class="link">declare</a>, <a href="/control-structures/alternative-syntax.html" class="link">alternative syntax</a> |
| **`T_ENDFOR`**                   | endfor                      | <a href="/control-structures/for.html" class="link">for</a>, <a href="/control-structures/alternative-syntax.html" class="link">alternative syntax</a>         |
| **`T_ENDFOREACH`**               | endforeach                  | <a href="/control-structures/foreach.html" class="link">foreach</a>, <a href="/control-structures/alternative-syntax.html" class="link">alternative syntax</a> |
| **`T_ENDIF`**                    | endif                       | <a href="/control-structures/if.html" class="link">if</a>, <a href="/control-structures/alternative-syntax.html" class="link">alternative syntax</a>           |
| **`T_ENDSWITCH`**                | endswitch                   | <a href="/control-structures/switch.html" class="link">switch</a>, <a href="/control-structures/alternative-syntax.html" class="link">alternative syntax</a>   |
| **`T_ENDWHILE`**                 | endwhile                    | <a href="/control-structures/while.html" class="link">while</a>, <a href="/control-structures/alternative-syntax.html" class="link">alternative syntax</a>     |
| **`T_END_HEREDOC`**              |                             | <a href="/language/types/string.html#language.types.string.syntax.heredoc" class="link">heredoc syntax</a>                                                     |
| **`T_EVAL`**                     | eval()                      | <span class="function">eval</span>                                                                                                                             |
| **`T_EXIT`**                     | exit or die                 | <span class="function">exit</span>, <span class="function">die</span>                                                                                          |
| **`T_EXTENDS`**                  | extends                     | <a href="/language/oop5/basic.html#language.oop5.basic.extends" class="link">extends</a>, <a href="/language/oop5.html" class="link">classes and objects</a>   |
| **`T_FILE`**                     | \_\_FILE\_\_                | <a href="/language/constants/predefined.html" class="link">magic constants</a>                                                                                 |
| **`T_FINAL`**                    | final                       | <a href="/language/oop5/final.html" class="xref">Final Keyword</a>                                                                                             |
| **`T_FINALLY`**                  | finally                     | <a href="/language/exceptions.html" class="xref">Exceptions</a> (available since PHP 5.5.0)                                                                    |
| **`T_FN`**                       | fn                          | <a href="/functions/arrow.html" class="link">arrow functions</a> (available since PHP 7.4.0)                                                                   |
| **`T_FOR`**                      | for                         | <a href="/control-structures/for.html" class="link">for</a>                                                                                                    |
| **`T_FOREACH`**                  | foreach                     | <a href="/control-structures/foreach.html" class="link">foreach</a>                                                                                            |
| **`T_FUNCTION`**                 | function                    | <a href="/language/functions.html" class="link">functions</a>                                                                                                  |
| **`T_FUNC_C`**                   | \_\_FUNCTION\_\_            | <a href="/language/constants/predefined.html" class="link">magic constants</a>                                                                                 |
| **`T_GLOBAL`**                   | global                      | <a href="/language/variables/scope.html" class="link">variable scope</a>                                                                                       |
| **`T_GOTO`**                     | goto                        | <a href="/control-structures/goto.html" class="link">goto</a> (available since PHP 5.3.0)                                                                      |
| **`T_HALT_COMPILER`**            | \_\_halt\_compiler()        | <a href="/ref/misc.html#__halt_compiler" class="xref"></a> (available since PHP 5.1.0)                                                                         |
| **`T_IF`**                       | if                          | <a href="/control-structures/if.html" class="link">if</a>                                                                                                      |
| **`T_IMPLEMENTS`**               | implements                  | <a href="/language/oop5/interfaces.html" class="xref">Object Interfaces</a>                                                                                    |
| **`T_INC`**                      | ++                          | <a href="/language/operators/increment.html" class="link">incrementing/decrementing operators</a>                                                              |
| **`T_INCLUDE`**                  | include()                   | <span class="function">include</span>                                                                                                                          |
| **`T_INCLUDE_ONCE`**             | include\_once()             | <span class="function">include\_once</span>                                                                                                                    |
| **`T_INLINE_HTML`**              |                             | <a href="/language/basic-syntax/phpmode.html" class="link">text outside PHP</a>                                                                                |
| **`T_INSTANCEOF`**               | instanceof                  | <a href="/language/operators/type.html" class="link">type operators</a>                                                                                        |
| **`T_INSTEADOF`**                | insteadof                   | <a href="/language/oop5/traits.html" class="xref">Traits</a> (available since PHP 5.4.0)                                                                       |
| **`T_INTERFACE`**                | interface                   | <a href="/language/oop5/interfaces.html" class="xref">Object Interfaces</a>                                                                                    |
| **`T_INT_CAST`**                 | (int) or (integer)          | <a href="/language/types/type-juggling.html#language.types.typecasting" class="link">type-casting</a>                                                          |
| **`T_ISSET`**                    | isset()                     | <span class="function">isset</span>                                                                                                                            |
| **`T_IS_EQUAL`**                 | ==                          | <a href="/language/operators/comparison.html" class="link">comparison operators</a>                                                                            |
| **`T_IS_GREATER_OR_EQUAL`**      | \>=                         | <a href="/language/operators/comparison.html" class="link">comparison operators</a>                                                                            |
| **`T_IS_IDENTICAL`**             | ===                         | <a href="/language/operators/comparison.html" class="link">comparison operators</a>                                                                            |
| **`T_IS_NOT_EQUAL`**             | != or \<\>                  | <a href="/language/operators/comparison.html" class="link">comparison operators</a>                                                                            |
| **`T_IS_NOT_IDENTICAL`**         | !==                         | <a href="/language/operators/comparison.html" class="link">comparison operators</a>                                                                            |
| **`T_IS_SMALLER_OR_EQUAL`**      | \<=                         | <a href="/language/operators/comparison.html" class="link">comparison operators</a>                                                                            |
| **`T_LINE`**                     | \_\_LINE\_\_                | <a href="/language/constants/predefined.html" class="link">magic constants</a>                                                                                 |
| **`T_LIST`**                     | list()                      | <span class="function">list</span>                                                                                                                             |
| **`T_LNUMBER`**                  | 123, 012, 0x1ac, etc.       | <a href="/language/types/integer.html" class="link">integers</a>                                                                                               |
| **`T_LOGICAL_AND`**              | and                         | <a href="/language/operators/logical.html" class="link">logical operators</a>                                                                                  |
| **`T_LOGICAL_OR`**               | or                          | <a href="/language/operators/logical.html" class="link">logical operators</a>                                                                                  |
| **`T_LOGICAL_XOR`**              | xor                         | <a href="/language/operators/logical.html" class="link">logical operators</a>                                                                                  |
| **`T_METHOD_C`**                 | \_\_METHOD\_\_              | <a href="/language/constants/predefined.html" class="link">magic constants</a>                                                                                 |
| **`T_MINUS_EQUAL`**              | -=                          | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_MOD_EQUAL`**                | %=                          | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_MUL_EQUAL`**                | \*=                         | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_NAMESPACE`**                | namespace                   | <a href="/language/namespaces.html" class="link">namespaces</a> (available since PHP 5.3.0)                                                                    |
| **`T_NEW`**                      | new                         | <a href="/language/oop5.html" class="link">classes and objects</a>                                                                                             |
| **`T_NS_C`**                     | \_\_NAMESPACE\_\_           | <a href="/language/namespaces.html" class="link">namespaces</a> (available since PHP 5.3.0)                                                                    |
| **`T_NS_SEPARATOR`**             | \\                          | <a href="/language/namespaces.html" class="link">namespaces</a> (available since PHP 5.3.0)                                                                    |
| **`T_NUM_STRING`**               | "$a\[0\]"                   | <a href="/language/types/string.html#language.types.string.parsing" class="link">numeric array index inside string</a>                                         |
| **`T_OBJECT_CAST`**              | (object)                    | <a href="/language/types/type-juggling.html#language.types.typecasting" class="link">type-casting</a>                                                          |
| **`T_OBJECT_OPERATOR`**          | -\>                         | <a href="/language/oop5.html" class="link">classes and objects</a>                                                                                             |
| **`T_OPEN_TAG`**                 | \<?php, \<? or \<%          | <a href="/language/basic-syntax/phpmode.html" class="link">escaping from HTML</a>                                                                              |
| **`T_OPEN_TAG_WITH_ECHO`**       | \<?= or \<%=                | <a href="/language/basic-syntax/phpmode.html" class="link">escaping from HTML</a>                                                                              |
| **`T_OR_EQUAL`**                 | \|=                         | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_PAAMAYIM_NEKUDOTAYIM`**     | ::                          | <a href="/language/oop5/paamayim-nekudotayim.html" class="link">::</a>. Also defined as **`T_DOUBLE_COLON`**.                                                  |
| **`T_PLUS_EQUAL`**               | +=                          | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_POW`**                      | \*\*                        | <a href="/language/operators/arithmetic.html" class="link">arithmetic operators</a> (available since PHP 5.6.0)                                                |
| **`T_POW_EQUAL`**                | \*\*=                       | <a href="/language/operators/assignment.html" class="link">assignment operators</a> (available since PHP 5.6.0)                                                |
| **`T_PRINT`**                    | print()                     | <span class="function">print</span>                                                                                                                            |
| **`T_PRIVATE`**                  | private                     | <a href="/language/oop5.html" class="link">classes and objects</a>                                                                                             |
| **`T_PROTECTED`**                | protected                   | <a href="/language/oop5.html" class="link">classes and objects</a>                                                                                             |
| **`T_PUBLIC`**                   | public                      | <a href="/language/oop5.html" class="link">classes and objects</a>                                                                                             |
| **`T_REQUIRE`**                  | require()                   | <span class="function">require</span>                                                                                                                          |
| **`T_REQUIRE_ONCE`**             | require\_once()             | <span class="function">require\_once</span>                                                                                                                    |
| **`T_RETURN`**                   | return                      | <a href="/functions/returning-values.html" class="link">returning values</a>                                                                                   |
| **`T_SL`**                       | \<\<                        | <a href="/language/operators/bitwise.html" class="link">bitwise operators</a>                                                                                  |
| **`T_SL_EQUAL`**                 | \<\<=                       | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_SPACESHIP`**                | \<=\>                       | <a href="/language/operators/comparison.html" class="link">comparison operators</a> (available since PHP 7.0.0)                                                |
| **`T_SR`**                       | \>\>                        | <a href="/language/operators/bitwise.html" class="link">bitwise operators</a>                                                                                  |
| **`T_SR_EQUAL`**                 | \>\>=                       | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_START_HEREDOC`**            | \<\<\<                      | <a href="/language/types/string.html#language.types.string.syntax.heredoc" class="link">heredoc syntax</a>                                                     |
| **`T_STATIC`**                   | static                      | <a href="/language/variables/scope.html" class="link">variable scope</a>                                                                                       |
| **`T_STRING`**                   | parent, self, etc.          | identifiers, e.g. keywords like *parent* and *self*, function names, class names and more are matched. See also **`T_CONSTANT_ENCAPSED_STRING`**.              |
| **`T_STRING_CAST`**              | (string)                    | <a href="/language/types/type-juggling.html#language.types.typecasting" class="link">type-casting</a>                                                          |
| **`T_STRING_VARNAME`**           | "${a                        | <a href="/language/types/string.html#language.types.string.parsing.complex" class="link">complex variable parsed syntax</a>                                    |
| **`T_SWITCH`**                   | switch                      | <a href="/control-structures/switch.html" class="link">switch</a>                                                                                              |
| **`T_THROW`**                    | throw                       | <a href="/language/exceptions.html" class="xref">Exceptions</a>                                                                                                |
| **`T_TRAIT`**                    | trait                       | <a href="/language/oop5/traits.html" class="xref">Traits</a> (available since PHP 5.4.0)                                                                       |
| **`T_TRAIT_C`**                  | \_\_TRAIT\_\_               | <a href="" class="link">__TRAIT__</a> (available since PHP 5.4.0)                                                                                              |
| **`T_TRY`**                      | try                         | <a href="/language/exceptions.html" class="xref">Exceptions</a>                                                                                                |
| **`T_UNSET`**                    | unset()                     | <span class="function">unset</span>                                                                                                                            |
| **`T_UNSET_CAST`**               | (unset)                     | <a href="/language/types/type-juggling.html#language.types.typecasting" class="link">type-casting</a>                                                          |
| **`T_USE`**                      | use                         | <a href="/language/namespaces.html" class="link">namespaces</a> (available since PHP 5.3.0)                                                                    |
| **`T_VAR`**                      | var                         | <a href="/language/oop5.html" class="link">classes and objects</a>                                                                                             |
| **`T_VARIABLE`**                 | $foo                        | <a href="/language/variables.html" class="link">variables</a>                                                                                                  |
| **`T_WHILE`**                    | while                       | <a href="/control-structures/while.html" class="link">while</a>, <a href="/control-structures/do/while.html" class="link">do..while</a>                        |
| **`T_WHITESPACE`**               | \\t \\r\\n                  |                                                                                                                                                                |
| **`T_XOR_EQUAL`**                | ^=                          | <a href="/language/operators/assignment.html" class="link">assignment operators</a>                                                                            |
| **`T_YIELD`**                    | yield                       | <a href="/language/generators/syntax.html#control-structures.yield" class="link">generators</a> (available since PHP 5.5.0)                                    |
| **`T_YIELD_FROM`**               | yield from                  | <a href="/language/generators/syntax.html#control-structures.yield.from" class="link">generators</a> (available since PHP 7.0.0)                               |

See also <span class="function">token\_name</span>.

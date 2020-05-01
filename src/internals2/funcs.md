Writing Functions
=================

Functions and Methods in PHP take much the same form, a method is simply
a function with a specific scope; the scope of their class entry. The
`Hacker` will read about class entries in other sections of the
`Hacker's` guide. The purpose of this section is to introduce the
`Hacker` to the anatomy of a function or method; the `Hacker` will learn
how to define functions, how to accept variables and how to return
variables to the programmer of PHP.

The anatomy of a function could not be simpler:

    PHP_FUNCTION(hackers_function) {
      /* your accepted arguments here */
      long number;
      
      /* accepting arguments */
      if (zend_parse_parameters(ZEND_NUM_ARGS() TSRMLS_CC, "l", &number) != SUCCESS) {
          return;
      }
      
      /* do some work on the input */
      number *= 2;
      
      /* set return value */
      RETURN_LONG(number);
    }

The `PHP_FUNCTION(hackers_function)` preprocessor instruction will
result in the following declaration:

    void zif_hackers_function(INTERNAL_FUNCTION_PARAMETERS)

`INTERNAL_FUNCTION_PARAMETERS` is defined as a macro and explained in
the following table:

| Name and type             | Description                                                                                                           | Access macros          |
|---------------------------|-----------------------------------------------------------------------------------------------------------------------|------------------------|
| `int ht`                  | Number of actual parameters passed by user                                                                            | `ZEND_NUM_ARGS()`      |
| `zval *return_value`      | Pointer to a PHP variable that can be filled with the return value passed to the user. The default type is `IS_NULL`. | `RETVAL_*`, `RETURN_*` |
| `zval **return_value_ptr` | When returning references to PHP set this to a pointer to your variable. It is not suggested to return references.    |                        |
| `zval *this_ptr`          | If this is a method call, points to the PHP variable holding the `$this` object.                                      | `getThis()`            |
| `int return_value_used`   | Flag indicating whether the returned value will be used by the caller.                                                |                        |

For clarity, the fully expanded declaration for
`PHP_FUNCTION(hackers_function)` looks like:

    void zif_hackers_function(int ht, zval* return_value, zval** return_value_ptr, zval* this_ptr, int return_value_used)

The presence of `this_ptr` may be confusing, classes are covered in
detail in later sections, suffice to say that
`PHP_METHOD(MyClass, hackersFunction)` would result in the following
declaration:

    void zim_MyClass_hackersFunction(INTERNAL_FUNCTION_PARAMETERS)

`hackers_function` doesn't do anything useful, it accepts a number using
the `zend_parse_parameters` API, doubles it, and returns it to the
engine. It is obvious that a normal function would have to do something
more complex than double the input, for the purposes of education we are
keeping it simple. On entry to the function `return_value` is allocated
and initialized to `null`, making `null` the default return value of any
function in PHP.

If `zend_parse_parameters` does not recieve what is specified by the
`Hacker` as the correct arguments, and the arguments recieved cannot be
converted to conform with `type_spec` an error will be raised, and by
convention, the `Hacker` should `return` immediately.

> **Note**:
>
> `Arrays`, `Objects`, and `Resources` cannot be converted.

|                                                                                                 |
|-------------------------------------------------------------------------------------------------|
| `int zend_parse_parameters(int num_args TSRMLS_DC, char *type_spec, ...)`                       |
| `int zend_parse_parameters_ex(int flags, int num_args TSRMLS_DC, char *type_spec, ...)`         |
| `int zend_parse_parameter(int flags, int arg_num TSRMLS_DC, zval **arg, const char *spec, ...)` |

> **Note**:
>
> `zend_parse_parameter` is available from version 5.5, it behaves like
> `zend_parse_parameters_ex` except that instead of reading the
> arguments from the stack, it receives a single zval to convert, which
> may be changed in place.

> **Note**:
>
> `flags` is intended to be a mask, currently only
> `ZEND_PARSE_PARAMS_QUIET` will have any impact (supress warnings)

The variable arguments recieved by these API functions are expected to
be the address of C variables, and should be considered the output of
the `zend_parse_parameters` API functions.

| Spec | Type                                             | Locals                                       |
|------|--------------------------------------------------|----------------------------------------------|
| a    | `array`                                          | `zval*`                                      |
| A    | `array` or `object`                              | `zval*`                                      |
| b    | `boolean`                                        | `zend_bool`                                  |
| C    | `class`                                          | `zend_class_entry*`                          |
| d    | `double`                                         | `double`                                     |
| f    | `function`                                       | `zend_fcall_info*`, `zend_fcall_info_cache*` |
| h    | `array`                                          | `HashTable*`                                 |
| H    | `array` or `object`                              | `HashTable*`                                 |
| l    | `long`                                           | `long`                                       |
| L    | `long` (limits out-of-range LONG\_MAX/LONG\_MIN) | `long`                                       |
| o    | `object`                                         | `zval*`                                      |
| O    | `object` (of specified `zend_class_entry`)       | `zval*`, `zend_class_entry*`                 |
| p    | `string` (a valid path)                          | `char*`, `int`                               |
| r    | `resource`                                       | `zval*`                                      |
| s    | `string`                                         | `char*`, `int`                               |
| z    | `mixed`                                          | `zval*`                                      |
| Z    | `mixed`                                          | `zval**`                                     |

> **Note**:
>
> Where the type specifier is `O`, the local `zend_class_entry*` is to
> be considered input (part of the type spec) to `zend_parse_parameter`

| Spec | Description                                                                                                                                                                                                                                                 |
|------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| \*   | a variable number of argument of the preceeding type, 0 or more                                                                                                                                                                                             |
| \+   | a variable number of argument of the preceeding type, 1 or more                                                                                                                                                                                             |
| \|   | indicates that the remaining parameters are optional                                                                                                                                                                                                        |
| /    | `SEPARATE_ZVAL_IF_NOT_REF` on the parameter it follows                                                                                                                                                                                                      |
| !    | the preceeding parameter can be of the specified type or `null` For 'b', 'l' and 'd', an extra argument of type zend\_bool\* must be passed after the corresponding `bool*`, `long*` or `double*` addresses which will be set `true` if `null` is recieved. |

> **Note**:
>
> Consult `README.PARAMETER_PARSING_API` included in source
> distributions for more information on parsing parameters

Once the `Hacker's` function has executed whatever it was implemented to
execute, it is time to set the `return_value` for the engine. The
`RETURN_` and `RETVAL_` macros are just wrappers around `Z_*_P` macros
that work with `return_value`.

> **Note**:
>
> `RETURN_` macros cause execution to leave the function immediately
> (ie: `return;`), while `RETVAL_` macros allow execution to continue
> after `return_value` has been set.

The `Hacker` should now have a reasonable understanding of the anatomy
of a function, and to some degree, the anatomy of a method.

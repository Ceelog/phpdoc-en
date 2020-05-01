Introduction to Variables
-------------------------

A good understanding of how variables are stored and manipulated is
essential to becoming a `Hacker`. The engine attempts to cover up the
complexity of the concept of a variable that can be any type by
providing a uniform and intuitive set of macros for accessing the
structures various fields. As the `Hacker` works through this chapter,
they should become comfortable with the terminology and concepts
involved with Variables in PHP.

> **Note**:
>
> PHP is a dynamic, loosely typed language, that uses copy-on-write and
> reference counting.

To clarify what exactly is meant by the statement above: PHP is a high
level language, weak typing is implicit of the engines preference to
convert, or coerce variables into the required type at execution time.
Reference counting is the means by which the engine can deduce when a
variable no longer has any references in the users code, and so is able
to free the structures associated with the variable.

All variables in PHP are represented by one structure, the `zval`:

    typedef struct _zval_struct {
        zvalue_value value;        /* variable value */
        zend_uint refcount__gc;    /* reference counter */
        zend_uchar type;           /* value type */
        zend_uchar is_ref__gc;     /* reference flag */
    } zval;

The `zval_value` is a union which can represent all types a variable may
hold:

    typedef union _zvalue_value {
        long lval;                 /* long value */
        double dval;               /* double value */
        struct {                   
            char *val;
            int len;               /* this will always be set for strings */
        } str;                     /* string (always has length) */
        HashTable *ht;             /* an array */
        zend_object_value obj;     /* stores an object store handle, and handlers */
    } zvalue_value;

It should be clear from the structures above that a variable can be of
one type, the variable data is represented by the appropriate field in
the `zval_value` union. The `zval` itself holds the type, reference
count and a flag to indicate if a variable is a reference.

| Constant     | Mapping                      |
|--------------|------------------------------|
| `IS_NULL`    | no value is set in this case |
| `IS_LONG`    | lval                         |
| `IS_DOUBLE`  | dval                         |
| `IS_BOOL`    | lval                         |
| IS\_RESOURCE | lval                         |
| IS\_STRING   | str                          |
| `IS_ARRAY`   | ht                           |
| `IS_OBJECT`  | obj                          |

> **Note**:
>
> There are additional constants that help to identify internal types
> such as constant arrays and callable objects, their usage is outside
> the scope of this part of the documentation.

The following table defines the macros exposed by the engine for working
with `zval` values:

| Prototype                                   | Accesses           | Description                                                                                |
|---------------------------------------------|--------------------|--------------------------------------------------------------------------------------------|
| `zend_uchar Z_TYPE(zval zv)`                | type               | returns the type of the `value`                                                            |
| `long Z_LVAL(zval zv)`                      | value.lval         |                                                                                            |
| `zend_bool Z_BVAL(zval zv)`                 | value.lval         | cast long `value` to zend\_bool                                                            |
| `double Z_DVAL(zval zv)`                    | value.dval         |                                                                                            |
| `long Z_RESVAL(zval zv)`                    | value.lval         | returns the resource list identifier for `value`                                           |
| `char* Z_STRVAL(zval zv)`                   | value.str.val      | return the string `value`                                                                  |
| `int Z_STRLEN(zval zv)`                     | value.str.len      | return the length of the string `value`                                                    |
| `HashTable* Z_ARRVAL(zval zv)`              | value.ht           | return the HashTable (array) `value`                                                       |
| `zend_object_value Z_OBJVAL(zval zv)`       | value.obj          | returns object `value`                                                                     |
| `uint Z_OBJ_HANDLE(zval zv)`                | value.obj.handle   | returns the object handle for object `value`                                               |
| `zend_object_handlers* Z_OBJ_HT_P(zval zv)` | value.obj.handlers | returns the handler table for object `value`                                               |
| `zend_class_entry* Z_OBJCE(zval zv)`        | value.obj          | returns the class entry for object `value`                                                 |
| `HashTable* Z_OBJPROP(zval zv)`             | value.obj          | returns the properties of object `value`                                                   |
| `HashTable* Z_OBJPROP(zval zv)`             | value.obj          | returns the properties of object `value`                                                   |
| `HashTable* Z_OBJDEBUG(zval zv)`            | value.obj          | if an object has the get\_debug\_info handler set, it is called, else Z\_OBJPROP is called |

Please check the
<a href="/features/gc/refcounting-basics.html" class="xref">Reference Counting Basics</a>
chapter for details how reference counting and references work in
detail.

| Prototype                                     | Description                                                 |
|-----------------------------------------------|-------------------------------------------------------------|
| `zend_uint Z_REFCOUNT(zval zv)`               | returns the reference count of the `value`                  |
| `zend_uint Z_SET_REFCOUNT(zval zv)`           | sets the reference count of the `value`, returning it       |
| `zend_uint Z_ADDREF(zval zv)`                 | pre-increments the reference count of `value`, returning it |
| `zend_uint Z_DELREF(zval zv)`                 | pre-decrements the reference count of `value`, returning it |
| `zend_bool Z_ISREF(zval zv)`                  | tells if the zval is a reference                            |
| `void Z_UNSET_ISREF(zval zv)`                 | set is\_ref\_\_gc to 0                                      |
| `void Z_SET_ISREF(zval zv)`                   | set is\_ref\_\_gc to 1                                      |
| `void Z_SET_ISREF_TO(zval zv, zend_uchar to)` | set is\_ref\_\_gc to `to`                                   |

> **Note**:
>
> The Z\_\* macros above all take a zval, they are all defined again
> suffixed with \_P to take a pointer to a zval, for example
> `zend_uchar Z_TYPE_P(zval* pzv)`, and again suffixed with \_PP to take
> a pointer to a pointer to a zval, for example
> `zend_uchar Z_TYPE_PP(zval** ppzv)`

| Prototype                                     | Description                                                                                                                           |
|-----------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|
| `ALLOC_ZVAL(zval* pzval)`                     | emallocs `pzval`                                                                                                                      |
| `ALLOC_INIT_ZVAL(zval* pzval)`                | emallocs `pzval`, and points `pzval` at a null typed zval for sanity                                                                  |
| `MAKE_STD_ZVAL(zval* pzval)`                  | emallocs `pzval`, setting the refcount to `1`                                                                                         |
| `ZVAL_COPY_VALUE(zval* dst, zval* src)`       | sets the value and type of `dst` from the value and type of `src`                                                                     |
| `INIT_PZVAL_COPY(zval* dst, zval*dst) `       | performs ZVAL\_COPY\_VALUE, setting refcount of `dst` to 1, and setting is\_ref\_\_gc to `0`                                          |
| `SEPARATE_ZVAL(zval** ppzval)`                | if the refcount of `ppzval` is \>1, redirects `*ppzval` to a newly emalloc'd, copied, and constructed zval of the same type and value |
| `SEPARATE_ZVAL_IF_NOT_REF(zval** ppzval)`     | if `*ppzval` is not a reference, will perform SEPARATE\_ZVAL on `ppzval`                                                              |
| `SEPARATE_ZVAL_TO_MAKE_IS_REF(zval** ppzval)` | if `*ppzval` is not a reference, performs SEPARATE\_ZVAL then Z\_SET\_ISREF\_PP on `ppzval`                                           |
| `COPY_PZVAL_TO_ZVAL(zval dst, zval** src)`    | results in `dst` being a copy of `src` without affecting the refcount of `src`                                                        |
| `MAKE_COPY_ZVAL(zval** src, zval* dst)`       | performs INIT\_PZVAL\_COPY, then zval\_copy\_ctor on the new zval                                                                     |
| `void zval_copy_ctor(zval** pzval)`           | performs maintenance of reference counts, used widely throughout the engine                                                           |
| `void zval_ptr_dtor(zval* pzval)`             | decrements the refcount for the variable, if no refcounts remain the variable is destroyed                                            |
| `FREE_ZVAL(zval* pzval)`                      | efrees `pzval`                                                                                                                        |

> **Note**:
>
> Objects and Resources have a reference count as part of their
> respective structures, when zval\_ptr\_dtor is called on either, their
> appropriate del\_ref method is executed. See Working with Objects and
> Working with Resources for more information.

If the `Hacker` only has room to remember two more functions, they
should be `zval_copy_ctor` and `zval_ptr_dtor`, these are at the basis
of the engines reference counting mechanisms and it is important to note
that `zval_copy_ctor` does not actually result in any copying occuring
under normal circumstances, it simply increases the reference count. By
the same token, `zval_ptr_dtor` only really destroys a variable when
there are no references remaining to it and the refcount is at 0.

PHP is weakly typed, as such the engine provides API functions for
converting variables from one type to another.

| Prototype                                                            |
|----------------------------------------------------------------------|
| `void convert_to_long(zval* pzval)`                                  |
| `void convert_to_double(zval* pzval)`                                |
| `void convert_to_long_base(zval* pzval, int base)`                   |
| `void convert_to_null(zval* pzval)`                                  |
| `void convert_to_boolean(zval* pzval)`                               |
| `void convert_to_array(zval* pzval)`                                 |
| `void convert_to_object(zval* pzval)`                                |
| `void convert_object_to_type(zval* pzval, convert_func_t converter)` |

> **Note**:
>
> `convert_func_t` functions should have the prototype
> `(void) (zval* pzval)`

By now you should have a good understanding of: the types that are
native to the engine, how to detect types and read zval values, how to
manipulate refcounts, and other zval flags

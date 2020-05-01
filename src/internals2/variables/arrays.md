Working with Arrays
-------------------

Arrays are stored in HashTable strucures, and have the zval type
IS\_ARRAY. The API functions for creating, destroying and manipulating
these structures as variables are documented here and can be found in
`Zend/zend_API.h`

| Prototype                           | Description                                                                                                     |
|-------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `void array_init(zval* pzval)`      | initializes the variable as a `HashTable`, setting type and appropriate destructor function for the `HashTable` |
| `void array_init_size(zval* pzval)` | initializes the variable as array\_init with a minimum of `size` buckets                                        |

> **Note**:
>
> Do not squint too hard looking for array\_destroy: to destroy a
> variable array you should call `zval_ptr_dtor` on the variable, if
> there are no other references to the variable it will result in the
> array being destroyed.

| Prototype                                                                                         |
|---------------------------------------------------------------------------------------------------|
| `int add_index_long(zval* pzval, ulong index, long value)`                                        |
| `int add_index_null(zval* pzval, ulong index)`                                                    |
| `int add_index_bool(zval* pzval, ulong index, zend_bool value)`                                   |
| `int add_index_bool(zval* pzval, ulong index, zend_bool value)`                                   |
| `int add_index_resource(zval* pzval, ulong index, uint value)`                                    |
| `int add_index_double(zval* pzval, ulong index, double value)`                                    |
| `int add_index_string(zval* pzval, ulong index, char* string, zend_bool duplicate)`               |
| `int add_index_stringl(zval* pzval, ulong index, char* string, uint length, zend_bool duplicate)` |
| `int add_index_zval(zval* pzval, ulong index, zval* value)`                                       |
| `int add_next_index_long(zval* pzval, long value)`                                                |
| `int add_next_index_null(zval* pzval)`                                                            |
| `int add_next_index_bool(zval* pzval, zend_bool value)`                                           |
| `int add_next_index_resource(zval* pzval, uint value)`                                            |
| `int add_next_index_double(zval* pzval, double value)`                                            |
| `int add_next_index_string(zval* pzval, const char* string, zend_bool dulpicate)`                 |
| `int add_next_index_stringl(zval* pzval, const char* string, uint length, zend_bool duplicate)`   |
| `int add_next_index_zval(zval* pzval, zval* value)`                                               |

| Prototype                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------|
| `int add_assoc_long(zval* pzval, const char* key, long value)`                                                         |
| `int add_assoc_long_ex(zval* pzval, const char* key, uint klen, long value)`                                           |
| `int add_assoc_null(zval* pzval, const char* key)`                                                                     |
| `int add_assoc_null_ex(zval* pzval, const char* key, uint klen)`                                                       |
| `int add_assoc_bool(zval* pzval, const char* key, zend_bool value)`                                                    |
| `int add_assoc_bool(zval* pzval, const char* key, zend_bool value)`                                                    |
| `int add_assoc_bool_ex(zval* pzval, const char* key, uint klen, zend_bool value)`                                      |
| `int add_assoc_resource(zval* pzval, const char* key, uint value)`                                                     |
| `int add_assoc_resource_ex(zval* pzval, const char* key, uint klen, uint value)`                                       |
| `int add_assoc_double(zval* pzval, const char* key, double value)`                                                     |
| `int add_assoc_double_ex(zval* pzval, const char* key, uint klen, double value)`                                       |
| `int add_assoc_string(zval* pzval, const char* key, const char* value)`                                                |
| `int add_assoc_string_ex(zval* pzval, const char* key, uint klen, const char* value)`                                  |
| `int add_assoc_stringl(zval* pzval, const char* key, const char* value, uint vlen, zend_bool duplicate)`               |
| `int add_assoc_stringl_ex(zval* pzval, const char* key, uint klen, const char* value, uint vlen, zend_bool duplicate)` |
| `int add_assoc_zval(zval* pzval, const char* key, zval* value)`                                                        |
| `int add_assoc_zval_ex(zval* pzval, const char* key, uint klen, zval* value)`                                          |

> **Note**:
>
> add\_\*\_string functions that accept a parameter named duplicate,
> will duplicate the string with `estrndup` when `duplicate` is true

> **Note**:
>
> add\_\*\_zval functions do not adjust the refcount of the `value`
> parameter

To perform more advanced operations on array variables we must use the
HashTable API directly.

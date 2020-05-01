Working with HashTable
----------------------

The `HashTable` structure serves many purposes in PHP and can be found
everywhere, a good understanding of it's functionality is a prerequisite
of being a good `Hacker`.

The `HashTable` implemented by the engine is a standard `HashTable`,
that is to say, a key =\> value based store, where the keys are always
strings, whose hashes are calculated with a built in hashing algorithm
`zend_inline_hash_func(const char* key, uint length)`, which results in
good distribution, and reasonable usage.

The internal structure and exact operation of `HashTable` is out of the
scope of this document, this document serves to inform you of the API's
available and how best to use them. For a more detailed picture of the
HashTable see `Zend/zend_hash.h`.

Unless otherwise stated, these functions all return `FAILURE` if the
requested operation fails for any reason, otherwise `SUCCESS` is
returned.

> **Note**:
>
> It is important to remember that ordinarily `HashTable` API functions
> expect key lengths to be the length of the null terminated string,
> including the null termination, in other words they expect
> `strlen(key) + 1`

Below are some typedefs you should know when interacting with
`HashTable`. They are mostly self explanitory and will allow the
`Hacker` to fully understand the prototypes below properly.

    typedef ulong (*hash_func_t)(const char *arKey, uint nKeyLength); /* mostly redundant */
    typedef int  (*compare_func_t)(const void *, const void * TSRMLS_DC); /* comparison function */
    typedef void (*sort_func_t)(void *, size_t, register size_t, compare_func_t TSRMLS_DC); /* sorting function */
    typedef void (*dtor_func_t)(void *pDest); /* destructor function */
    typedef void (*copy_ctor_func_t)(void *pElement); /* copy constructor */
    typedef void (*copy_ctor_param_func_t)(void *pElement, void *pParam); /* copy with argument constructor */
    typedef int (*apply_func_t)(void *pDest TSRMLS_DC); /* apply function */
    typedef int (*apply_func_arg_t)(void *pDest, void *argument TSRMLS_DC); /* apply with argument function */
    typedef int (*apply_func_args_t)(void *pDest TSRMLS_DC, int num_args, va_list args, zend_hash_key *hash_key); /* apply with multiple arguments function */

|                                                                                                                                                                                                                                                                     |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `int zend_hash_init(HashTable* ht, uint size, hash_func_t hash, dtor_func_t destructor, zend_bool persistent)`                                                                                                                                                      |
| Initializes the hash table to hold at least `size` elements, `hash` exists for historical reasons and is always ignored, `zend_inline_hash_func` is always used as the hashing function. `destructor` may be `NULL`.                                                |
| `int zend_hash_add(HashTable* ht, const char* key, uint klen, void* data, uint dlen, void** dest)`                                                                                                                                                                  |
| adds `data` to the table using the specified `key`, where the key is `length` bytes long (and will be copied from `key` to the table). If the key is set FAILURE will be returned.                                                                                  |
| `int zend_hash_update(HashTable* ht, const char* key, uint klen, void* data, uint dlen, void** dest)`                                                                                                                                                               |
| adds `data` to the table using the specified `key`, where the key is `length` bytes long (and will be copied from `key` to the table). If the key has been set previously the old data has `dtor_func_t` called on it and the existing data is replaced with `data` |
| `int zend_hash_find(HashTable* ht, const char* key, uint klen, void** data)`                                                                                                                                                                                        |
| searches the table for `key`, setting `*data` and returning SUCCESS if it is found.                                                                                                                                                                                 |
| `zend_bool zend_hash_exists(HashTable* ht, const char* key, uint klen)`                                                                                                                                                                                             |
| returns positively if `key` is found in `ht`                                                                                                                                                                                                                        |
| `int zend_hash_del(HashTable* ht, const char* key, uint klen)`                                                                                                                                                                                                      |
| removes the entry identified by `key` from the table if found                                                                                                                                                                                                       |
| `int zend_hash_index_update(HashTable* ht, ulong index, void* data, uint dsize, void** dest)`                                                                                                                                                                       |
| updates the entry at `index` in `ht`, with the data at `data`                                                                                                                                                                                                       |
| `int zend_hash_index_del(HashTable* ht, ulong index)`                                                                                                                                                                                                               |
| deletes the entry at `index` from `ht`                                                                                                                                                                                                                              |
| `int zend_hash_index_find(HashTable* ht, ulong index, void** data)`                                                                                                                                                                                                 |
| redirects `*data` to the data identified by `index` in `ht`                                                                                                                                                                                                         |
| `int zend_hash_index_exists(HashTable* ht, ulong index)`                                                                                                                                                                                                            |
| returns positively if `index` is found in `ht`                                                                                                                                                                                                                      |
| `ulong zend_hash_next_free_element(HashTable* ht)`                                                                                                                                                                                                                  |
| returns the index of the next free element in `ht`                                                                                                                                                                                                                  |

**Caution**

zend\_hash\_\* functions that accept `void* data` should normally cast
it to `(void**)` (ie, `(void**) &data`)

Traversing the HashTable is often necessary, to do this you provide a
pointer to a `HashTable`, with an optional `HashPosition` - a structure
internal to the HashTable API that allows traversal not to affect the
internal position of HashTable. The following traversal functions are
provided, and an example usage found below.

|                                                                                                                                                                                                                             |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `int zend_hash_internal_pointer_reset(HashTable* ht)`                                                                                                                                                                       |
| resets the internal pointer of `ht` to the start                                                                                                                                                                            |
| `int zend_hash_internal_pointer_reset_ex(HashTable* ht, HashPosition position)`                                                                                                                                             |
| sets `position` to the start of `ht`                                                                                                                                                                                        |
| `int zend_hash_get_current_data(HashTable* ht, void* data)`                                                                                                                                                                 |
| gets the data at the current position in `ht`, `data` should be cast to `void**`, ie: `(void**) &data`                                                                                                                      |
| `int zend_hash_get_current_data_ex(HashTable* ht, void* data, HashPosition position)`                                                                                                                                       |
| sets `data` to the data at `position` in `ht`                                                                                                                                                                               |
| `int zend_hash_get_current_key(HashTable* ht, void* data, char**key, uint klen, ulong index, zend_bool duplicate)`                                                                                                          |
| sets `key`, `klen`, and `index` from the key information at the current position. The possible return values HASH\_KEY\_IS\_STRING and HASH\_KEY\_IS\_LONG are indicative of the kind of key found at the current posision. |
| `int zend_hash_get_current_key_ex(HashTable* ht, void* data, char**key, uint klen, ulong index, zend_bool duplicate, HashPosition position)`                                                                                |
| sets `key`, `klen`, and `index` from the key information at `position`. The possible return values `HASH_KEY_IS_STRING` and `HASH_KEY_IS_LONG` are indicative of the kind of key found at `position`.                       |
| `int zend_hash_move_forward(HashTable* ht)`                                                                                                                                                                                 |
| moves the internal pointer of `ht` to the next entry in `ht`                                                                                                                                                                |
| `int zend_hash_move_forward_ex(HashTable* ht, HashPosition position)`                                                                                                                                                       |
| moves `position` to the next entry in `ht`                                                                                                                                                                                  |

The functions above allow traversal over a `HashTable` to be much like a
normal loop, which will look something like:

    HashPosition position;
    zval **data = NULL;

    for (zend_hash_internal_pointer_reset_ex(ht, &position);
         zend_hash_get_current_data_ex(ht, (void**) &data, &position) == SUCCESS;
         zend_hash_move_forward_ex(ht, &position)) {
         
         /* by now we have data set and can use Z_ macros for accessing type and variable data */

         char *key = NULL;
         uint  klen;
         ulong index;

         if (zend_hash_get_current_key_ex(ht, &key, &klen, &index, 0, &position) == HASH_KEY_IS_STRING) {
             /* the key is a string, key and klen will be set */
         } else {
             /* we assume the key to be long, index will be set */
         }
    }

> **Note**:
>
> If a `HashTable` has been passed into the engine, it is a good idea to
> use the zend\_hash\_\*\_ex API to avoid unexpected behaviour in
> userland.

> **Note**:
>
> If a `duplicate` of the key is requested and `HAS_KEY_IS_STRING` is
> returned the caller must `efree` the duplicated key

In addition to traversal, the engine provides API functions for merging,
copying, and comparing HashTables. These are all concepts that the
`Hacker` should be familiar with. A concept possibly not in the
repertoire of the `Hacker` is `applying`, which is lamens terms is
functionality of the `HashTable` API allowing the `Hacker` to pass a
callback function to be executed on every entry in a `HashTable`.

|                                                                                                                                                                                 |
|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `void zend_hash_copy(HashTable *target, HashTable *source, copy_ctor_func_t pCopyConstructor, void *tmp, uint size)`                                                            |
| Copies the contents of `source` to `target`. `tmp` should be an unallocated temporary pointer of the appropriate type, used during copying. `size` is the size of each element. |
| `void zend_hash_merge(HashTable *target, HashTable *source, copy_ctor_func_t pCopyConstructor, void *tmp, uint size, zend_bool overwrite)`                                      |
| Merges the contents of `source` into `destination`, replacing existing entries only where `overwrite` is true.                                                                  |
| `void int zend_hash_sort(HashTable *ht, sort_func_t sort_func, compare_func_t compare_func, int renumber TSRMLS_DC)`                                                            |
| `renumber` controls if indexes should be preserved, see the typedefs at the start of this section for more information                                                          |

> **Note**:
>
> When a function accepts a `copy_ctor_func_t pCopyConstructor`, the
> function passed with be executed upon creation of every new entry in
> the `HashTable`. The most common copy constructor used within the
> engine is a wrapper around `zval_copy_ctor`, the macro
> `ZVAL_COPY_CTOR`.

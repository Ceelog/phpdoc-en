Data persistence
----------------

In this context, data persistence is taken to mean any data that is
intended to survive the current request. The memory management within
the engine is very focused on request bound allocations, but this is not
always practical or appropriate. Persistent memory is sometimes required
in order to satisfy requirements of external libraries, it can also be
useful while `Hacking`.

A common use of persistent memory is to enable persistent SQL server
connections, though this practice is frowned upon, it is none the less
the most common use of this feature.

> **Note**: <span class="simpara"> All of the following functions take
> the additional persistent parameter, should this be false, the engine
> will use its regular allocators (emalloc) and the memory should not be
> considered persistent. Where memory is allocated as persistent, system
> allocators are invoked, under most circumstances they are still not
> able to return NULL pointers just as the Main memory APIs. </span>

| Prototype                                                                             | Description                                                                                                                                                                                               |
|---------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `void *pemalloc(size_t size, zend_bool persistent)`                                   | Allocate `size` bytes of memory.                                                                                                                                                                          |
| `void *pecalloc(size_t nmemb, size_t size, zend_bool persistent)`                     | Allocate a buffer for `nmemb` elements of `size` bytes and makes sure it is initialized with zeros.                                                                                                       |
| `void *perealloc(void *ptr, size_t size, zend_bool persistent)`                       | Resize the buffer `ptr`, which was allocated using `emalloc` to hold `size` bytes of memory.                                                                                                              |
| `void pefree(void *ptr, zend_bool persistent)`                                        | Free the buffer pointed by `ptr`. The buffer had to be allocated by `pemalloc`.                                                                                                                           |
| `void *safe_pemalloc(size_t nmemb, size_t size, size_t offset, zend_bool persistent)` | Allocate a buffer for holding `nmemb` blocks of each `size` bytes and an additional `offset` bytes. This is similar to `pemalloc(nmemb * size + offset)` but adds a special protection against overflows. |
| `char *pestrdup(const char *s, zend_bool persistent)`                                 | Allocate a buffer that can hold the NULL-terminated string `s` and copy the `s` into that buffer.                                                                                                         |
| `char *pestrndup(const char *s, unsigned int length, zend_bool persistent)`           | Similar to `pestrdup` while the length of the NULL-terminated string is already known.                                                                                                                    |

**Caution**

It is important to remember that memory allocated to be persistent is
not optimized or tracked by the engine; it is not subject to
memory\_limit, additionally, all variables that are created by the
`Hacker` for the engine must not use persistent memory.

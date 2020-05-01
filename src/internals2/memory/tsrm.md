Thread-Safe Resource Manager
----------------------------

When PHP is built with Thread Safety enabled, the engine requires a way
to isolate contexts from one another, such that the threads of a process
may service individual requests without interference. TSRM is omnipotent
within PHP, extension authors have to do very little in order to make
sure their extensions can function in both a Thread Safe and Non Thread
Safe architecture.

**Example \#1 Accessor macros for per-module globals**

``` c
#ifdef ZTS
#define COUNTER_G(v) TSRMG(counter_globals_id, zend_counter_globals *, v)
#else
#define COUNTER_G(v) (counter_globals.v)
#endif
```

The snippet above shows how an extension author is expected to define
their global accessors. The TSRMG macro takes an identifier, type cast
and element name. The identifier is assigned by TSRM during
initialization of the module. Declaring global accessors in this way
ensures that an extension can operate safely in a Thread Safe and Non
Thread Safe architecture using the same logic.

TSRM manages the isolation and safety of all global structures within
PHP, from executor globals to extension globals, a pointer to the
isolated storage is also passed around with most, or many of the API
functions. The macros TSRMLS\_C and TSRMLS\_CC translate to "thread safe
local storage" and "thread safe local storage prefixed with a comma"
respectively.

If a function requires a pointer to TSRM, it is declared with the macro
TSRMLS\_D or TSRMLS\_DC in it's prototype, which translates to "thread
safe local storage only" and "thread safe local storage prefixed with a
comma" respectively. Many macros within the engine reference TSRM, so it
is a good idea to declare most things to accept TSRM, such that if they
need to call upon TSRM they do not have to fetch a pointer during
execution.

Because TSRM is thread local, and some functions (for compatibility
reasons) are not able to accept TSRM directly, the macro TSRMLS\_FETCH
exists, which requests that TSRM fetches the pointer to the thread local
storage. This should be avoided wherever it can be, as it is not without
cost in a Thread Safe setup.

> **Note**: <span class="simpara"> While developing extensions, build
> errors that contain "tsrm\_ls is undefined" or errors to that effect
> stem from the fact that TSRMLS is undefined in the current scope, to
> fix this, declare the function to accept TSRMLS with the appropriate
> macro, if the prototype of the function in question cannot be changed,
> you must call TSRMLS\_FETCH within the function body. </span>

The functionality documented hereafter is aimed at advanced use of TSRM.
It is not ordinary for extensions to have to interact with TSRM
directly, the pecl programmer should use API's above TSRM such as the
Module Globals API.

| Prototype                                                                                                   | Description                                                                                                                                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `typedef int ts_rsrc_id`                                                                                    | The type definition to represent a resource by numeric identifiers                                                                                                                                                                          |
| `int tsrm_startup(int expected_threads, int expected_resources, int debug_level, char *debug_filename)`     | `expected_threads` and `expected_resources` are not hard limits. `debug_level` and `debug_filename` only have an effect on windows in Debug mode or when TSRM\_DEBUG is defined. Called once per process in ZTS mode during server startup. |
| `void tsrm_shutdown(void)`                                                                                  | Should be the last thing called in the process to destroy and free all storage TSRM storage in ZTS mode.                                                                                                                                    |
| `ts_rsrc_id ts_allocate_id(ts_rsrc_id *rsrc_id, size_t size, ts_allocate_ctor ctor, ts_allocate_dtor dtor)` | Allocates and thread safe pointer of `size` bytes, calling `ctor` on the pointer, assigning (and returning) the id to `rsrc_id`, the `dtor` is called when the resource is free'd. Module globals are isolated in ZTS mode using this API.  |
| `void *ts_resource_ex(ts_rsrc_id id, THREAD_T *th_id)`                                                      | Fetches a resource by previously allocated `id` from the entries created by the specified thread identifed by `th_id`.                                                                                                                      |
| `void *ts_resource(ts_rsrc_id id)`                                                                          | Fetches a resource by previously allocated `id` from the entries created by the calling thread.                                                                                                                                             |
| `void ts_free_thread(void)`                                                                                 | Destroys and frees the entries for the calling thread, currently this API is only used by ISAPI module.                                                                                                                                     |
| `void ts_free_id(ts_rsrc_id id)`                                                                            | Destroys the resource identified by previously allocated `id`. Module globals are cleaned up in ZTS mode using this API.                                                                                                                    |

> **Note**: <span class="simpara">There are more TSRM API functions to
> enable the creation and destruction of interpreter contexts, the usage
> of such functionality is out of the scope of this documentation,
> please see TSRM/TSRM.h for more information.</span>

| Prototype                               | Description                                                          |
|-----------------------------------------|----------------------------------------------------------------------|
| `MUTEX_T tsrm_mutex_alloc(void)`        | Allocates and returns a suitable MUTEX\_T for the environment.       |
| `int tsrm_mutex_lock(MUTEX_T mutexp)`   | Locks `mutexp` for the calling thread.                               |
| `int tsrm_mutex_unlock(MUTEX_T mutexp)` | Unlocks `mutexp` for the calling thread.                             |
| `void tsrm_mutex_free(MUTEX_T mutexp);` | Destroys and frees the (unlocked) and previously allocated `mutexp`. |

> **Note**: <span class="simpara">The mutex API is exposed by TSRM.
> However, its internal usage is far too wide to document usefully here,
> none the less, basic functionality and prototypes are documented
> here.</span>

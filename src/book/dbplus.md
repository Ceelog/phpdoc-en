DB++
====

**Table of Contents**

-   [Introduction](/book/dbplus.html#Introduction)
-   [Installing/Configuring](/book/dbplus.html#Installing/Configuring)
    -   [Requirements](/book/dbplus.html#Requirements)
    -   [Installation](/book/dbplus.html#Installation)
    -   [Runtime
        Configuration](/book/dbplus.html#Runtime%20Configuration)
    -   [Resource Types](/book/dbplus.html#Resource%20Types)
-   [Predefined Constants](/book/dbplus.html#Predefined%20Constants)
    -   [db++ error codes](/book/dbplus.html#db++%20error%20codes)
-   [DB++ Functions](/book/dbplus.html#DB++%20Functions)
    -   [dbplus\_add](/book/dbplus.html#dbplus_add) — Add a tuple to a
        relation
    -   [dbplus\_aql](/book/dbplus.html#dbplus_aql) — Perform AQL query
    -   [dbplus\_chdir](/book/dbplus.html#dbplus_chdir) — Get/Set
        database virtual current directory
    -   [dbplus\_close](/book/dbplus.html#dbplus_close) — Close a
        relation
    -   [dbplus\_curr](/book/dbplus.html#dbplus_curr) — Get current
        tuple from relation
    -   [dbplus\_errcode](/book/dbplus.html#dbplus_errcode) — Get error
        string for given errorcode or last error
    -   [dbplus\_errno](/book/dbplus.html#dbplus_errno) — Get error code
        for last operation
    -   [dbplus\_find](/book/dbplus.html#dbplus_find) — Set a constraint
        on a relation
    -   [dbplus\_first](/book/dbplus.html#dbplus_first) — Get first
        tuple from relation
    -   [dbplus\_flush](/book/dbplus.html#dbplus_flush) — Flush all
        changes made on a relation
    -   [dbplus\_freealllocks](/book/dbplus.html#dbplus_freealllocks) —
        Free all locks held by this client
    -   [dbplus\_freelock](/book/dbplus.html#dbplus_freelock) — Release
        write lock on tuple
    -   [dbplus\_freerlocks](/book/dbplus.html#dbplus_freerlocks) — Free
        all tuple locks on given relation
    -   [dbplus\_getlock](/book/dbplus.html#dbplus_getlock) — Get a
        write lock on a tuple
    -   [dbplus\_getunique](/book/dbplus.html#dbplus_getunique) — Get an
        id number unique to a relation
    -   [dbplus\_info](/book/dbplus.html#dbplus_info) — Get information
        about a relation
    -   [dbplus\_last](/book/dbplus.html#dbplus_last) — Get last tuple
        from relation
    -   [dbplus\_lockrel](/book/dbplus.html#dbplus_lockrel) — Request
        write lock on relation
    -   [dbplus\_next](/book/dbplus.html#dbplus_next) — Get next tuple
        from relation
    -   [dbplus\_open](/book/dbplus.html#dbplus_open) — Open relation
        file
    -   [dbplus\_prev](/book/dbplus.html#dbplus_prev) — Get previous
        tuple from relation
    -   [dbplus\_rchperm](/book/dbplus.html#dbplus_rchperm) — Change
        relation permissions
    -   [dbplus\_rcreate](/book/dbplus.html#dbplus_rcreate) — Creates a
        new DB++ relation
    -   [dbplus\_rcrtexact](/book/dbplus.html#dbplus_rcrtexact) —
        Creates an exact but empty copy of a relation including indices
    -   [dbplus\_rcrtlike](/book/dbplus.html#dbplus_rcrtlike) — Creates
        an empty copy of a relation with default indices
    -   [dbplus\_resolve](/book/dbplus.html#dbplus_resolve) — Resolve
        host information for relation
    -   [dbplus\_restorepos](/book/dbplus.html#dbplus_restorepos) —
        Restore position
    -   [dbplus\_rkeys](/book/dbplus.html#dbplus_rkeys) — Specify new
        primary key for a relation
    -   [dbplus\_ropen](/book/dbplus.html#dbplus_ropen) — Open relation
        file local
    -   [dbplus\_rquery](/book/dbplus.html#dbplus_rquery) — Perform
        local (raw) AQL query
    -   [dbplus\_rrename](/book/dbplus.html#dbplus_rrename) — Rename a
        relation
    -   [dbplus\_rsecindex](/book/dbplus.html#dbplus_rsecindex) — Create
        a new secondary index for a relation
    -   [dbplus\_runlink](/book/dbplus.html#dbplus_runlink) — Remove
        relation from filesystem
    -   [dbplus\_rzap](/book/dbplus.html#dbplus_rzap) — Remove all
        tuples from relation
    -   [dbplus\_savepos](/book/dbplus.html#dbplus_savepos) — Save
        position
    -   [dbplus\_setindex](/book/dbplus.html#dbplus_setindex) — Set
        index
    -   [dbplus\_setindexbynumber](/book/dbplus.html#dbplus_setindexbynumber)
        — Set index by number
    -   [dbplus\_sql](/book/dbplus.html#dbplus_sql) — Perform SQL query
    -   [dbplus\_tcl](/book/dbplus.html#dbplus_tcl) — Execute TCL code
        on server side
    -   [dbplus\_tremove](/book/dbplus.html#dbplus_tremove) — Remove
        tuple and return new current tuple
    -   [dbplus\_undo](/book/dbplus.html#dbplus_undo) — Undo
    -   [dbplus\_undoprepare](/book/dbplus.html#dbplus_undoprepare) —
        Prepare undo
    -   [dbplus\_unlockrel](/book/dbplus.html#dbplus_unlockrel) — Give
        up write lock on relation
    -   [dbplus\_unselect](/book/dbplus.html#dbplus_unselect) — Remove a
        constraint from relation
    -   [dbplus\_update](/book/dbplus.html#dbplus_update) — Update
        specified tuple in relation
    -   [dbplus\_xlockrel](/book/dbplus.html#dbplus_xlockrel) — Request
        exclusive lock on relation
    -   [dbplus\_xunlockrel](/book/dbplus.html#dbplus_xunlockrel) — Free
        exclusive lock on relation

db++, made by the German company
<a href="http://www.concept-asa.de/index_gb.html" class="link external">» Concept asa</a>,
is a relational database system with high performance and low memory and
disk usage in mind. While providing SQL as an additional language
interface, it is not really an SQL database in the first place but
provides its own AQL query language which is much more influenced by the
relational algebra than SQL is.

Concept asa always had an interest in supporting open source languages,
db++ has had Perl and Tcl call interfaces for years now and uses Tcl as
its internal stored procedure language.

> **Note**:
>
> This extension has been moved to the
> <a href="https://pecl.php.net/" class="link external">» PECL</a>
> repository and is no longer bundled with PHP as of PHP 4.3.0

**Warning**

This extension is *EXPERIMENTAL*. The behaviour of this extension
including the names of its functions and any other documentation
surrounding this extension may change without notice in a future release
of PHP. This extension should be used at your own risk.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/dbplus.html#Requirements)
-   [Installation](/book/dbplus.html#Installation)
-   [Runtime Configuration](/book/dbplus.html#Runtime%20Configuration)
-   [Resource Types](/book/dbplus.html#Resource%20Types)

Requirements
------------

This extension relies on external client libraries so you have to have a
db++ client installed on the system you want to use this extension on.

<a href="http://www.concept-asa.de/index_gb.html" class="link external">» Concept asa</a>
provides
<a href="http://www.concept-asa.de/down-eng.html" class="link external">» db++ Demo versions</a>
and
<a href="http://www.concept-asa.de/downloads/doc-eng.tar.gz" class="link external">» documentation</a>
for Linux, some other Unix versions. There is also a Windows version of
db++, but this extension doesn't support it (yet).

Installation
------------

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 4.3.0

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/dbplus" class="link external">» https://pecl.php.net/package/dbplus</a>.

In order to build this extension yourself you need the db++ client
libraries and header files to be installed on your system (these are
included in the db++ installation archives by default). You have to run
**configure** with option **--with-dbplus** to build this extension.

**configure** looks for the client libraries and header files under the
default paths `/usr/dbplus`, `/usr/local/dbplus` and `/opt/dblus`. If
you have installed db++ in a different place you have add the
installation path to the **configure** option like this:
**--with-dbplus=/your/installation/path**.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

dbplus\_relation
----------------

Most db++ functions operate on or return `dbplus_relation` resources. A
`dbplus_relation` is a handle to a stored relation or a relation
generated as the result of a query.

Predefined Constants
====================

**Table of Contents**

-   [db++ error codes](/book/dbplus.html#db++%20error%20codes)

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

db++ error codes
----------------

| PHP Constant                                                       | db++ constant       | meaning                                                                                  |
|--------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------|
| **`DBPLUS_ERR_NOERR`** (<span class="type">integer</span>)         | ERR\_NOERR          | Null error condition                                                                     |
| **`DBPLUS_ERR_DUPLICATE`** (<span class="type">integer</span>)     | ERR\_DUPLICATE      | Tried to insert a duplicate tuple                                                        |
| **`DBPLUS_ERR_EOSCAN`** (<span class="type">integer</span>)        | ERR\_EOSCAN         | End of scan from *rget()*                                                                |
| **`DBPLUS_ERR_EMPTY`** (<span class="type">integer</span>)         | ERR\_EMPTY          | Relation is empty (server)                                                               |
| **`DBPLUS_ERR_CLOSE`** (<span class="type">integer</span>)         | ERR\_CLOSE          | The server can't close                                                                   |
| **`DBPLUS_ERR_WLOCKED`** (<span class="type">integer</span>)       | ERR\_WLOCKED        | The record is write locked                                                               |
| **`DBPLUS_ERR_LOCKED`** (<span class="type">integer</span>)        | ERR\_LOCKED         | Relation was already locked                                                              |
| **`DBPLUS_ERR_NOLOCK`** (<span class="type">integer</span>)        | ERR\_NOLOCK         | Relation cannot be locked                                                                |
| **`DBPLUS_ERR_READ`** (<span class="type">integer</span>)          | ERR\_READ           | Read error on relation                                                                   |
| **`DBPLUS_ERR_WRITE`** (<span class="type">integer</span>)         | ERR\_WRITE          | Write error on relation                                                                  |
| **`DBPLUS_ERR_CREATE`** (<span class="type">integer</span>)        | ERR\_CREATE         | *Create()* system call failed                                                            |
| **`DBPLUS_ERR_LSEEK`** (<span class="type">integer</span>)         | ERR\_LSEEK          | *Lseek()* system call failed                                                             |
| **`DBPLUS_ERR_LENGTH`** (<span class="type">integer</span>)        | ERR\_LENGTH         | Tuple exceeds maximum length                                                             |
| **`DBPLUS_ERR_OPEN`** (<span class="type">integer</span>)          | ERR\_OPEN           | *Open()* system call failed                                                              |
| **`DBPLUS_ERR_WOPEN`** (<span class="type">integer</span>)         | ERR\_WOPEN          | Relation already opened for writing                                                      |
| **`DBPLUS_ERR_MAGIC`** (<span class="type">integer</span>)         | ERR\_MAGIC          | File is not a relation                                                                   |
| **`DBPLUS_ERR_VERSION`** (<span class="type">integer</span>)       | ERR\_VERSION        | File is a very old relation                                                              |
| **`DBPLUS_ERR_PGSIZE`** (<span class="type">integer</span>)        | ERR\_PGSIZE         | Relation uses a different page size                                                      |
| **`DBPLUS_ERR_CRC`** (<span class="type">integer</span>)           | ERR\_CRC            | Invalid crc in the superpage                                                             |
| **`DBPLUS_ERR_PIPE`** (<span class="type">integer</span>)          | ERR\_PIPE           | Piped relation requires *lseek()*                                                        |
| **`DBPLUS_ERR_NIDX`** (<span class="type">integer</span>)          | ERR\_NIDX           | Too many secondary indices                                                               |
| **`DBPLUS_ERR_MALLOC`** (<span class="type">integer</span>)        | ERR\_MALLOC         | *Malloc()* call failed                                                                   |
| **`DBPLUS_ERR_NUSERS`** (<span class="type">integer</span>)        | ERR\_NUSERS         | Error use of max users                                                                   |
| **`DBPLUS_ERR_PREEXIT`** (<span class="type">integer</span>)       | ERR\_PREEXIT        | Caused by invalid usage                                                                  |
| **`DBPLUS_ERR_ONTRAP`** (<span class="type">integer</span>)        | ERR\_ONTRAP         | Caused by a signal                                                                       |
| **`DBPLUS_ERR_PREPROC`** (<span class="type">integer</span>)       | ERR\_PREPROC        | Error in the preprocessor                                                                |
| **`DBPLUS_ERR_DBPARSE`** (<span class="type">integer</span>)       | ERR\_DBPARSE        | Error in the parser                                                                      |
| **`DBPLUS_ERR_DBRUNERR`** (<span class="type">integer</span>)      | ERR\_DBRUNERR       | Run error in db                                                                          |
| **`DBPLUS_ERR_DBPREEXIT`** (<span class="type">integer</span>)     | ERR\_DBPREEXIT      | Exit condition caused by *prexit()* \* procedure                                         |
| **`DBPLUS_ERR_WAIT`** (<span class="type">integer</span>)          | ERR\_WAIT           | Wait a little (Simple only)                                                              |
| **`DBPLUS_ERR_CORRUPT_TUPLE`** (<span class="type">integer</span>) | ERR\_CORRUPT\_TUPLE | A client sent a corrupt tuple                                                            |
| **`DBPLUS_ERR_WARNING0`** (<span class="type">integer</span>)      | ERR\_WARNING0       | The Simple routines encountered a non fatal error which was corrected                    |
| **`DBPLUS_ERR_PANIC`** (<span class="type">integer</span>)         | ERR\_PANIC          | The server should not really die but after a disaster send ERR\_PANIC to all its clients |
| **`DBPLUS_ERR_FIFO`** (<span class="type">integer</span>)          | ERR\_FIFO           | Can't create a fifo                                                                      |
| **`DBPLUS_ERR_PERM`** (<span class="type">integer</span>)          | ERR\_PERM           | Permission denied                                                                        |
| **`DBPLUS_ERR_TCL`** (<span class="type">integer</span>)           | ERR\_TCL            | TCL\_error                                                                               |
| **`DBPLUS_ERR_RESTRICTED`** (<span class="type">integer</span>)    | ERR\_RESTRICTED     | Only two users                                                                           |
| **`DBPLUS_ERR_USER`** (<span class="type">integer</span>)          | ERR\_USER           | An error in the use of the library by an application programmer                          |
| **`DBPLUS_ERR_UNKNOWN`** (<span class="type">integer</span>)       | ERR\_UNKNOWN        |                                                                                          |

dbplus\_add
===========

Add a tuple to a relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_add</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> , <span
class="methodparam"><span class="type">array</span> `$tuple`</span> )

Adds a tuple to a `relation`.

### Parameters

`relation`  

`tuple`  
An array of attribute/value pairs to be inserted into the given
`relation`.

After successful execution this array will contain the complete data of
the newly created tuple, including all implicitly set domain fields like
sequences.

### Return Values

The function will return **`DBPLUS_ERR_NOERR`** on success or a db++
error code on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_errcode</span>

dbplus\_aql
===========

Perform AQL query

### Description

<span class="type">resource</span> <span
class="methodname">dbplus\_aql</span> ( <span class="methodparam"><span
class="type">string</span> `$query`</span> \[, <span
class="methodparam"><span class="type">string</span> `$server`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$dbpath`</span> \]\] )

Executes an AQL `query` on the given `server` and `dbpath`.

### Parameters

`query`  
The AQL query to be executed. Further information on the AQL (Algebraic
Query Language) is provided in the original db++ manual.

`server`  

`dbpath`  

### Return Values

Returns a relation handle on success. The result data may be fetched
from this relation by calling <span class="function">dbplus\_next</span>
and <span class="function">dbplus\_curr</span>. Other relation access
functions will not work on a result relation.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_chdir
=============

Get/Set database virtual current directory

### Description

<span class="type">string</span> <span
class="methodname">dbplus\_chdir</span> (\[ <span
class="methodparam"><span class="type">string</span> `$newdir`</span> \]
)

Changes the virtual current directory where relation files will be
looked for by <span class="function">dbplus\_open</span>.

### Parameters

`newdir`  
The new directory for relation files. You can omit this parameter to
query the current working directory.

### Return Values

Returns the absolute path of the current directory.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_close
=============

Close a relation

### Description

<span class="type">mixed</span> <span
class="methodname">dbplus\_close</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

Closes a relation previously opened by <span
class="function">dbplus\_open</span>.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

Returns **`TRUE`** on success or **`DBPLUS_ERR_UNKNOWN`** on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_curr
============

Get current tuple from relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_curr</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> , <span
class="methodparam"><span class="type">array</span> `&$tuple`</span> )

Reads the data for the current tuple for the given `relation`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  
The data will be passed back in this parameter, as an associative array.

### Return Values

The function will return zero (aka. **`DBPLUS_ERR_NOERR`**) on success
or a db++ error code on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_first</span>
-   <span class="function">dbplus\_prev</span>
-   <span class="function">dbplus\_next</span>
-   <span class="function">dbplus\_last</span>
-   <span class="function">dbplus\_errcode</span>

dbplus\_errcode
===============

Get error string for given errorcode or last error

### Description

<span class="type">string</span> <span
class="methodname">dbplus\_errcode</span> (\[ <span
class="methodparam"><span class="type">int</span> `$errno`</span> \] )

Returns a clear error string for the given error code.

### Parameters

`errno`  
The error code. If not provided, the result code of the last db++
operation is assumed.

### Return Values

Returns the error message.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_errno
=============

Get error code for last operation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_errno</span> ( <span
class="methodparam">void</span> )

Returns the error code returned by the last db++ operation.

### Return Values

Returns the error code, as an integer.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_errcode</span>

dbplus\_find
============

Set a constraint on a relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_find</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> , <span
class="methodparam"><span class="type">array</span>
`$constraints`</span> , <span class="methodparam"><span
class="type">mixed</span> `$tuple`</span> )

Places a constraint on the given `relation`.

Further calls to functions like <span
class="function">dbplus\_curr</span> or <span
class="function">dbplus\_next</span> will only return tuples matching
the given constraints.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`constraints`  
Constraints are triplets of strings containing of a domain name, a
comparison operator and a comparison value. The `constraints` parameter
array may consist of a collection of string arrays, each of which
contains a domain, an operator and a value, or of a single string array
containing a multiple of three elements.

The comparison operator may be one of the following strings: '==', '\>',
'\>=', '\<', '\<=', '!=', '\~' for a regular expression match and 'BAND'
or 'BOR' for bitwise operations.

`tuple`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_unselect</span>

dbplus\_first
=============

Get first tuple from relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_first</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">array</span> `&$tuple`</span> )

Reads the data for the first tuple for the given `relation`, makes it
the current tuple and pass it back as an associative array in `tuple`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  

### Return Values

Returns **`DBPLUS_ERR_NOERR`** on success or a db++ error code on
failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_curr</span>
-   <span class="function">dbplus\_prev</span>
-   <span class="function">dbplus\_next</span>
-   <span class="function">dbplus\_last</span>
-   <span class="function">dbplus\_errcode</span>

dbplus\_flush
=============

Flush all changes made on a relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_flush</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

Writes all changes applied to `relation` since the last flush to disk.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

Returns **`DBPLUS_ERR_NOERR`** on success or a db++ error code on
failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_errcode</span>

dbplus\_freealllocks
====================

Free all locks held by this client

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_freealllocks</span> ( <span
class="methodparam">void</span> )

Frees all tuple locks held by this client.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_getlock</span>
-   <span class="function">dbplus\_freelock</span>
-   <span class="function">dbplus\_freerlocks</span>

dbplus\_freelock
================

Release write lock on tuple

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_freelock</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">string</span> `$tuple`</span> )

Releases a write lock on the given `tuple` previously obtained by <span
class="function">dbplus\_getlock</span>.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_getlock</span>
-   <span class="function">dbplus\_freerlocks</span>
-   <span class="function">dbplus\_freealllocks</span>

dbplus\_freerlocks
==================

Free all tuple locks on given relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_freerlocks</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

Frees all tuple locks held on the given `relation`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_getlock</span>
-   <span class="function">dbplus\_freelock</span>
-   <span class="function">dbplus\_freealllocks</span>

dbplus\_getlock
===============

Get a write lock on a tuple

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_getlock</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">string</span> `$tuple`</span> )

Requests a write lock on the specified `tuple`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  

### Return Values

Returns zero on success or a non-zero error code, especially
**`DBPLUS_ERR_WLOCKED`** on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_freelock</span>
-   <span class="function">dbplus\_freerlocks</span>
-   <span class="function">dbplus\_freealllocks</span>

dbplus\_getunique
=================

Get an id number unique to a relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_getunique</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">int</span> `$uniqueid`</span> )

Obtains a number guaranteed to be unique for the given `relation` and
will pass it back in the variable given as `uniqueid`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`uniqueid`  

### Return Values

Returns **`DBPLUS_ERR_NOERR`** on success or a db++ error code on
failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_info
============

Get information about a relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_info</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">array</span>
`&$result`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`key`  

`result`  

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_last
============

Get last tuple from relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_last</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> , <span
class="methodparam"><span class="type">array</span> `&$tuple`</span> )

Reads the data for the last tuple for the given `relation`, makes it the
current tuple and pass it back as an associative array in `tuple`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  

### Return Values

Returns **`DBPLUS_ERR_NOERR`** on success or a db++ error code on
failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_first</span>
-   <span class="function">dbplus\_curr</span>
-   <span class="function">dbplus\_prev</span>
-   <span class="function">dbplus\_next</span>

dbplus\_lockrel
===============

Request write lock on relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_lockrel</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

Requests a write lock on the given `relation`.

Other clients may still query the relation, but can't alter it while it
is locked.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_next
============

Get next tuple from relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_next</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> , <span
class="methodparam"><span class="type">array</span> `&$tuple`</span> )

Reads the data for the next tuple for the given `relation`, makes it the
current tuple and will pass it back as an associative array in `tuple`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  

### Return Values

Returns **`DBPLUS_ERR_NOERR`** on success or a db++ error code on
failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_first</span>
-   <span class="function">dbplus\_curr</span>
-   <span class="function">dbplus\_prev</span>
-   <span class="function">dbplus\_last</span>

dbplus\_open
============

Open relation file

### Description

<span class="type">resource</span> <span
class="methodname">dbplus\_open</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

Opens the given relation file.

### Parameters

`name`  
Can be either a file name or a relative or absolute path name. This will
be mapped in any case to an absolute relation file path on a specific
host machine and server.

### Return Values

On success a relation file resource (cursor) is returned which must be
used in any subsequent commands referencing the relation. Failure leads
to a zero return value, the actual error code may be asked for by
calling <span class="function">dbplus\_errno</span>.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_prev
============

Get previous tuple from relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_prev</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> , <span
class="methodparam"><span class="type">array</span> `&$tuple`</span> )

Reads the data for the previous tuple for the given `relation`, makes it
the current tuple and will pass it back as an associative array in
`tuple`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  

### Return Values

Returns **`DBPLUS_ERR_NOERR`** on success or a db++ error code on
failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_first</span>
-   <span class="function">dbplus\_curr</span>
-   <span class="function">dbplus\_next</span>
-   <span class="function">dbplus\_last</span>

dbplus\_rchperm
===============

Change relation permissions

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_rchperm</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">int</span> `$mask`</span> , <span class="methodparam"><span
class="type">string</span> `$user`</span> , <span
class="methodparam"><span class="type">string</span> `$group`</span> )

Changes access permissions as specified by `mask`, `user` and `group`.
The values for these are operating system specific.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`mask`  

`user`  

`group`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_rcreate
===============

Creates a new DB++ relation

### Description

<span class="type">resource</span> <span
class="methodname">dbplus\_rcreate</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$domlist`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$overwrite`</span> \] )

Creates a new relation. Any existing relation sharing the same `name`
will be overwritten if the relation is currently not in use and
`overwrite` is set to TRUE.

### Parameters

`name`  

`domlist`  
A combination of domains. May be passed as a single domain name string
or as an array of domain names.

This parameter should contain the domain specification for the new
relation within an array of domain description strings. A domain
description string consists of a domain name unique to this relation, a
slash and a type specification character. See the db++ documentation,
especially the dbcreate(1) manpage, for a description of available type
specifiers and their meanings.

> **Note**:
>
> This function will also accept a string with space delimited domain
> description strings, but it is recommended to use an array

`overwrite`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_rcrtexact
=================

Creates an exact but empty copy of a relation including indices

### Description

<span class="type">mixed</span> <span
class="methodname">dbplus\_rcrtexact</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$relation`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$overwrite`</span> \] )

<span class="function">dbplus\_rcrtexact</span> will create an exact but
empty copy of the given `relation` under a new `name`.

### Parameters

`name`  

`relation`  
The copied relation, opened by <span
class="function">dbplus\_open</span>.

`overwrite`  
An existing relation by the same `name` will only be overwritten if this
parameter is set to **`TRUE`** and no other process is currently using
the relation.

### Return Values

Returns resource on success or **`DBPLUS_ERR_UNKNOWN`** on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_rcrtlike
================

Creates an empty copy of a relation with default indices

### Description

<span class="type">mixed</span> <span
class="methodname">dbplus\_rcrtlike</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$relation`</span> \[, <span class="methodparam"><span
class="type">int</span> `$overwrite`</span> \] )

<span class="function">dbplus\_rcrtexact</span> will create an empty
copy of the given `relation` under a new `name`, but with default
indices.

### Parameters

`name`  

`relation`  
The copied relation, opened by <span
class="function">dbplus\_open</span>.

`overwrite`  
An existing relation by the same `name` will only be overwritten if this
parameter is set to **`TRUE`** and no other process is currently using
the relation.

### Return Values

Returns resource on success or **`DBPLUS_ERR_UNKNOWN`** on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_resolve
===============

Resolve host information for relation

### Description

<span class="type">array</span> <span
class="methodname">dbplus\_resolve</span> ( <span
class="methodparam"><span class="type">string</span>
`$relation_name`</span> )

<span class="function">dbplus\_resolve</span> will try to resolve the
given `relation_name` and find out internal server id, real hostname and
the database path on this host.

### Parameters

`relation_name`  
The relation name.

### Return Values

Returns an array containing these values under the keys *sid*, *host*
and *host\_path* or **`FALSE`** on error.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_tcl</span>

dbplus\_restorepos
==================

Restore position

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_restorepos</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">array</span> `$tuple`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_rkeys
=============

Specify new primary key for a relation

### Description

<span class="type">mixed</span> <span
class="methodname">dbplus\_rkeys</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">mixed</span> `$domlist`</span> )

<span class="function">dbplus\_rkeys</span> will replace the current
primary key for `relation` with the combination of domains specified by
`domlist`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`domlist`  
A combination of domains. May be passed as a single domain name string
or as an array of domain names.

### Return Values

Returns resource on success or **`DBPLUS_ERR_UNKNOWN`** on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_ropen
=============

Open relation file local

### Description

<span class="type">resource</span> <span
class="methodname">dbplus\_ropen</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="function">dbplus\_ropen</span> will open the relation
`file` locally for quick access without any client/server overhead.
Access is read only and only <span class="function">dbplus\_curr</span>
and <span class="function">dbplus\_next</span> may be applied to the
returned relation.

### Parameters

`name`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_rquery
==============

Perform local (raw) AQL query

### Description

<span class="type">resource</span> <span
class="methodname">dbplus\_rquery</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$dbpath`</span> \] )

<span class="function">dbplus\_rquery</span> performs a local (raw) AQL
query using an AQL interpreter embedded into the db++ client library.
<span class="function">dbplus\_rquery</span> is faster than <span
class="function">dbplus\_aql</span> but will work on local data only.

### Parameters

`query`  

`dbpath`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_rrename
===============

Rename a relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_rrename</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="function">dbplus\_rrename</span> will change the name of
`relation` to `name`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`name`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_rsecindex
=================

Create a new secondary index for a relation

### Description

<span class="type">mixed</span> <span
class="methodname">dbplus\_rsecindex</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">mixed</span> `$domlist`</span> , <span
class="methodparam"><span class="type">int</span> `$type`</span> )

<span class="function">dbplus\_rsecindex</span> will create a new
secondary index for `relation` with consists of the domains specified by
`domlist` and is of type `type`

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`domlist`  
A combination of domains. May be passed as a single domain name string
or as an array of domain names.

`type`  

### Return Values

Returns resource on success or **`DBPLUS_ERR_UNKNOWN`** on failure.

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_runlink
===============

Remove relation from filesystem

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_runlink</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

<span class="function">dbplus\_runlink</span> will close and remove the
`relation`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_rzap
============

Remove all tuples from relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_rzap</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> )

<span class="function">dbplus\_rzap</span> will remove all tuples from
`relation`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_savepos
===============

Save position

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_savepos</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_setindex
================

Set index

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_setindex</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">string</span> `$idx_name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`idx_name`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_setindexbynumber
========================

Set index by number

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_setindexbynumber</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">int</span> `$idx_number`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`idx_number`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_sql
===========

Perform SQL query

### Description

<span class="type">resource</span> <span
class="methodname">dbplus\_sql</span> ( <span class="methodparam"><span
class="type">string</span> `$query`</span> \[, <span
class="methodparam"><span class="type">string</span> `$server`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$dbpath`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`query`  

`server`  

`dbpath`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_tcl
===========

Execute TCL code on server side

### Description

<span class="type">string</span> <span
class="methodname">dbplus\_tcl</span> ( <span class="methodparam"><span
class="type">int</span> `$sid`</span> , <span class="methodparam"><span
class="type">string</span> `$script`</span> )

A db++ server will prepare a TCL interpreter for each client connection.
This interpreter will enable the server to execute TCL code provided by
the client as a sort of stored procedures to improve the performance of
database operations by avoiding client/server data transfers and context
switches.

<span class="function">dbplus\_tcl</span> needs to pass the client
connection id the TCL `script` code should be executed by. <span
class="function">dbplus\_resolve</span> will provide this connection id.
The function will return whatever the TCL code returns or a TCL error
message if the TCL code fails.

### Parameters

`sid`  

`script`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_resolve</span>

dbplus\_tremove
===============

Remove tuple and return new current tuple

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_tremove</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">array</span> `$tuple`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$current`</span>
\] )

<span class="function">dbplus\_tremove</span> removes `tuple` from
`relation` if it perfectly matches a tuple within the relation.
`current`, if given, will contain the data of the new current tuple
after calling <span class="function">dbplus\_tremove</span>.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`tuple`  

`current`  

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_undo
============

Undo

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_undo</span> ( <span class="methodparam"><span
class="type">resource</span> `$relation`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_undoprepare
===================

Prepare undo

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_undoprepare</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_unlockrel
=================

Give up write lock on relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_unlockrel</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

Release a write lock previously obtained by <span
class="function">dbplus\_lockrel</span>.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_unselect
================

Remove a constraint from relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_unselect</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

Calling <span class="function">dbplus\_unselect</span> will remove a
constraint previously set by <span class="function">dbplus\_find</span>
on `relation`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_update
==============

Update specified tuple in relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_update</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> , <span class="methodparam"><span
class="type">array</span> `$old`</span> , <span
class="methodparam"><span class="type">array</span> `$new`</span> )

<span class="function">dbplus\_update</span> replaces the `old` tuple
with the data from the `new` one, only if the `old` completely matches a
tuple within `relation`.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

`old`  
The old tuple.

`new`  
The new tuple.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

dbplus\_xlockrel
================

Request exclusive lock on relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_xlockrel</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

Request an exclusive lock on `relation` preventing even read access from
other clients.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### See Also

-   <span class="function">dbplus\_xunlockrel</span>

dbplus\_xunlockrel
==================

Free exclusive lock on relation

### Description

<span class="type">int</span> <span
class="methodname">dbplus\_xunlockrel</span> ( <span
class="methodparam"><span class="type">resource</span>
`$relation`</span> )

Releases an exclusive lock previously obtained by <span
class="function">dbplus\_xlockrel</span>.

### Parameters

`relation`  
A relation opened by <span class="function">dbplus\_open</span>.

### Return Values

### Notes

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Table of Contents**

-   [dbplus\_add](/book/dbplus.html#dbplus_add) — Add a tuple to a
    relation
-   [dbplus\_aql](/book/dbplus.html#dbplus_aql) — Perform AQL query
-   [dbplus\_chdir](/book/dbplus.html#dbplus_chdir) — Get/Set database
    virtual current directory
-   [dbplus\_close](/book/dbplus.html#dbplus_close) — Close a relation
-   [dbplus\_curr](/book/dbplus.html#dbplus_curr) — Get current tuple
    from relation
-   [dbplus\_errcode](/book/dbplus.html#dbplus_errcode) — Get error
    string for given errorcode or last error
-   [dbplus\_errno](/book/dbplus.html#dbplus_errno) — Get error code for
    last operation
-   [dbplus\_find](/book/dbplus.html#dbplus_find) — Set a constraint on
    a relation
-   [dbplus\_first](/book/dbplus.html#dbplus_first) — Get first tuple
    from relation
-   [dbplus\_flush](/book/dbplus.html#dbplus_flush) — Flush all changes
    made on a relation
-   [dbplus\_freealllocks](/book/dbplus.html#dbplus_freealllocks) — Free
    all locks held by this client
-   [dbplus\_freelock](/book/dbplus.html#dbplus_freelock) — Release
    write lock on tuple
-   [dbplus\_freerlocks](/book/dbplus.html#dbplus_freerlocks) — Free all
    tuple locks on given relation
-   [dbplus\_getlock](/book/dbplus.html#dbplus_getlock) — Get a write
    lock on a tuple
-   [dbplus\_getunique](/book/dbplus.html#dbplus_getunique) — Get an id
    number unique to a relation
-   [dbplus\_info](/book/dbplus.html#dbplus_info) — Get information
    about a relation
-   [dbplus\_last](/book/dbplus.html#dbplus_last) — Get last tuple from
    relation
-   [dbplus\_lockrel](/book/dbplus.html#dbplus_lockrel) — Request write
    lock on relation
-   [dbplus\_next](/book/dbplus.html#dbplus_next) — Get next tuple from
    relation
-   [dbplus\_open](/book/dbplus.html#dbplus_open) — Open relation file
-   [dbplus\_prev](/book/dbplus.html#dbplus_prev) — Get previous tuple
    from relation
-   [dbplus\_rchperm](/book/dbplus.html#dbplus_rchperm) — Change
    relation permissions
-   [dbplus\_rcreate](/book/dbplus.html#dbplus_rcreate) — Creates a new
    DB++ relation
-   [dbplus\_rcrtexact](/book/dbplus.html#dbplus_rcrtexact) — Creates an
    exact but empty copy of a relation including indices
-   [dbplus\_rcrtlike](/book/dbplus.html#dbplus_rcrtlike) — Creates an
    empty copy of a relation with default indices
-   [dbplus\_resolve](/book/dbplus.html#dbplus_resolve) — Resolve host
    information for relation
-   [dbplus\_restorepos](/book/dbplus.html#dbplus_restorepos) — Restore
    position
-   [dbplus\_rkeys](/book/dbplus.html#dbplus_rkeys) — Specify new
    primary key for a relation
-   [dbplus\_ropen](/book/dbplus.html#dbplus_ropen) — Open relation file
    local
-   [dbplus\_rquery](/book/dbplus.html#dbplus_rquery) — Perform local
    (raw) AQL query
-   [dbplus\_rrename](/book/dbplus.html#dbplus_rrename) — Rename a
    relation
-   [dbplus\_rsecindex](/book/dbplus.html#dbplus_rsecindex) — Create a
    new secondary index for a relation
-   [dbplus\_runlink](/book/dbplus.html#dbplus_runlink) — Remove
    relation from filesystem
-   [dbplus\_rzap](/book/dbplus.html#dbplus_rzap) — Remove all tuples
    from relation
-   [dbplus\_savepos](/book/dbplus.html#dbplus_savepos) — Save position
-   [dbplus\_setindex](/book/dbplus.html#dbplus_setindex) — Set index
-   [dbplus\_setindexbynumber](/book/dbplus.html#dbplus_setindexbynumber)
    — Set index by number
-   [dbplus\_sql](/book/dbplus.html#dbplus_sql) — Perform SQL query
-   [dbplus\_tcl](/book/dbplus.html#dbplus_tcl) — Execute TCL code on
    server side
-   [dbplus\_tremove](/book/dbplus.html#dbplus_tremove) — Remove tuple
    and return new current tuple
-   [dbplus\_undo](/book/dbplus.html#dbplus_undo) — Undo
-   [dbplus\_undoprepare](/book/dbplus.html#dbplus_undoprepare) —
    Prepare undo
-   [dbplus\_unlockrel](/book/dbplus.html#dbplus_unlockrel) — Give up
    write lock on relation
-   [dbplus\_unselect](/book/dbplus.html#dbplus_unselect) — Remove a
    constraint from relation
-   [dbplus\_update](/book/dbplus.html#dbplus_update) — Update specified
    tuple in relation
-   [dbplus\_xlockrel](/book/dbplus.html#dbplus_xlockrel) — Request
    exclusive lock on relation
-   [dbplus\_xunlockrel](/book/dbplus.html#dbplus_xunlockrel) — Free
    exclusive lock on relation

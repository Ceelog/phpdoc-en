Informix
========

**Table of Contents**

-   [Introduction](/book/ifx.html#Introduction)
-   [Installing/Configuring](/book/ifx.html#Installing/Configuring)
    -   [Requirements](/book/ifx.html#Requirements)
    -   [Installation](/book/ifx.html#Installation)
    -   [Runtime Configuration](/book/ifx.html#Runtime%20Configuration)
    -   [Resource Types](/book/ifx.html#Resource%20Types)
-   [Predefined Constants](/book/ifx.html#Predefined%20Constants)
-   [Informix Functions](/book/ifx.html#Informix%20Functions)
    -   [ifx\_affected\_rows](/book/ifx.html#ifx_affected_rows) — Get
        number of rows affected by a query
    -   [ifx\_blobinfile\_mode](/book/ifx.html#ifx_blobinfile_mode) —
        Set the default blob mode for all select queries
    -   [ifx\_byteasvarchar](/book/ifx.html#ifx_byteasvarchar) — Set the
        default byte mode
    -   [ifx\_close](/book/ifx.html#ifx_close) — Close Informix
        connection
    -   [ifx\_connect](/book/ifx.html#ifx_connect) — Open Informix
        server connection
    -   [ifx\_copy\_blob](/book/ifx.html#ifx_copy_blob) — Duplicates the
        given blob object
    -   [ifx\_create\_blob](/book/ifx.html#ifx_create_blob) — Creates an
        blob object
    -   [ifx\_create\_char](/book/ifx.html#ifx_create_char) — Creates an
        char object
    -   [ifx\_do](/book/ifx.html#ifx_do) — Execute a previously prepared
        SQL-statement
    -   [ifx\_error](/book/ifx.html#ifx_error) — Returns error code of
        last Informix call
    -   [ifx\_errormsg](/book/ifx.html#ifx_errormsg) — Returns error
        message of last Informix call
    -   [ifx\_fetch\_row](/book/ifx.html#ifx_fetch_row) — Get row as an
        associative array
    -   [ifx\_fieldproperties](/book/ifx.html#ifx_fieldproperties) —
        List of SQL fieldproperties
    -   [ifx\_fieldtypes](/book/ifx.html#ifx_fieldtypes) — List of
        Informix SQL fields
    -   [ifx\_free\_blob](/book/ifx.html#ifx_free_blob) — Deletes the
        blob object
    -   [ifx\_free\_char](/book/ifx.html#ifx_free_char) — Deletes the
        char object
    -   [ifx\_free\_result](/book/ifx.html#ifx_free_result) — Releases
        resources for the query
    -   [ifx\_get\_blob](/book/ifx.html#ifx_get_blob) — Return the
        content of a blob object
    -   [ifx\_get\_char](/book/ifx.html#ifx_get_char) — Return the
        content of the char object
    -   [ifx\_getsqlca](/book/ifx.html#ifx_getsqlca) — Get the contents
        of sqlca.sqlerrd\[0..5\] after a query
    -   [ifx\_htmltbl\_result](/book/ifx.html#ifx_htmltbl_result) —
        Formats all rows of a query into a HTML table
    -   [ifx\_nullformat](/book/ifx.html#ifx_nullformat) — Sets the
        default return value on a fetch row
    -   [ifx\_num\_fields](/book/ifx.html#ifx_num_fields) — Returns the
        number of columns in the query
    -   [ifx\_num\_rows](/book/ifx.html#ifx_num_rows) — Count the rows
        already fetched from a query
    -   [ifx\_pconnect](/book/ifx.html#ifx_pconnect) — Open persistent
        Informix connection
    -   [ifx\_prepare](/book/ifx.html#ifx_prepare) — Prepare an
        SQL-statement for execution
    -   [ifx\_query](/book/ifx.html#ifx_query) — Send Informix query
    -   [ifx\_textasvarchar](/book/ifx.html#ifx_textasvarchar) — Set the
        default text mode
    -   [ifx\_update\_blob](/book/ifx.html#ifx_update_blob) — Updates
        the content of the blob object
    -   [ifx\_update\_char](/book/ifx.html#ifx_update_char) — Updates
        the content of the char object
    -   [ifxus\_close\_slob](/book/ifx.html#ifxus_close_slob) — Deletes
        the slob object
    -   [ifxus\_create\_slob](/book/ifx.html#ifxus_create_slob) —
        Creates an slob object and opens it
    -   [ifxus\_free\_slob](/book/ifx.html#ifxus_free_slob) — Deletes
        the slob object
    -   [ifxus\_open\_slob](/book/ifx.html#ifxus_open_slob) — Opens an
        slob object
    -   [ifxus\_read\_slob](/book/ifx.html#ifxus_read_slob) — Reads
        nbytes of the slob object
    -   [ifxus\_seek\_slob](/book/ifx.html#ifxus_seek_slob) — Sets the
        current file or seek position
    -   [ifxus\_tell\_slob](/book/ifx.html#ifxus_tell_slob) — Returns
        the current file or seek position
    -   [ifxus\_write\_slob](/book/ifx.html#ifxus_write_slob) — Writes a
        string into the slob object

The Informix driver for Informix (IDS) 7.x, SE 7.x, Universal Server
(IUS) 9.x and IDS 2000 is implemented in "ifx.ec" and "php\_informix.h"
in the informix extension directory. IDS 7.x support is fairly complete,
with full support for BYTE and TEXT columns. IUS 9.x support is partly
finished: the new data types are there, but SLOB and CLOB support is
still under construction.

> **Note**:
>
> This extension has been moved to the
> <a href="https://pecl.php.net/" class="link external">» PECL</a>
> repository and is no longer bundled with PHP as of PHP 5.2.1.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/ifx.html#Requirements)
-   [Installation](/book/ifx.html#Installation)
-   [Runtime Configuration](/book/ifx.html#Runtime%20Configuration)
-   [Resource Types](/book/ifx.html#Resource%20Types)

Requirements
------------

> **Note**: **Configuration notes**  
>
> You need a version of ESQL/C to compile the PHP Informix driver.
> ESQL/C versions from 7.2x on should be OK. ESQL/C is now part of the
> Informix Client SDK.
>
> Make sure that the "INFORMIXDIR" variable has been set, and that
> $INFORMIXDIR/bin is in your `PATH` before you run the "configure"
> script.

Installation
------------

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 5.2.1

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/informix" class="link external">» https://pecl.php.net/package/informix</a>.

To be able to use the functions defined in this module you must compile
your PHP interpreter using the configure line
**--with-informix\[=DIR\]**, where DIR is the Informix base install
directory, defaults to nothing.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

> **Note**:
>
> Make sure that the Informix environment variables INFORMIXDIR and
> INFORMIXSERVER are available to the PHP ifx driver, and that the
> INFORMIX bin directory is in the `PATH`. Check this by running a
> script that contains a call to <span class="function">phpinfo</span>
> before you start testing. The <span class="function">phpinfo</span>
> output should list these environment variables. This is true for both
> CGI php and Apache mod\_php. You may have to set these environment
> variables in your Apache startup script.
>
> The Informix shared libraries should also be available to the loader
> (check LD\_LIBRARY\_PATH or ld.so.conf/ldconfig).

> **Note**: **Some notes on the use of BLOBs (TEXT and BYTE columns)**  
>
> BLOBs are normally addressed by BLOB identifiers. Select queries
> return a "blob id" for every BYTE and TEXT column. You can get at the
> contents with "string\_var = ifx\_get\_blob($blob\_id);" if you choose
> to get the BLOBs in memory (with: "ifx\_blobinfile(0);"). If you
> prefer to receive the content of BLOB columns in a file, use
> "ifx\_blobinfile(1);", and "ifx\_get\_blob($blob\_id);" will get you
> the filename. Use normal file I/O to get at the blob contents.
>
> For insert/update queries you must create these "blob id's" yourself
> with "<span class="function">ifx\_create\_blob</span>;". You then plug
> the blob id's into an array, and replace the blob columns with a
> question mark (?) in the query string. For updates/inserts, you are
> responsible for setting the blob contents with <span
> class="function">ifx\_update\_blob</span>.
>
> The behaviour of BLOB columns can be altered by configuration
> variables that also can be set at runtime:
>
> configuration variable: ifx.textasvarchar
>
> configuration variable: ifx.byteasvarchar
>
> runtime functions:
>
> ifx\_textasvarchar(0): use blob id's for select queries with TEXT
> columns
>
> ifx\_byteasvarchar(0): use blob id's for select queries with BYTE
> columns
>
> ifx\_textasvarchar(1): return TEXT columns as if they were VARCHAR
> columns, so that you don't need to use blob id's for select queries.
>
> ifx\_byteasvarchar(1): return BYTE columns as if they were VARCHAR
> columns, so that you don't need to use blob id's for select queries.
>
> configuration variable: ifx.blobinfile
>
> runtime function:
>
> ifx\_blobinfile\_mode(0): return BYTE columns in memory, the blob id
> lets you get at the contents.
>
> ifx\_blobinfile\_mode(1): return BYTE columns in a file, the blob id
> lets you get at the file name.
>
> If you set ifx\_text/byteasvarchar to 1, you can use TEXT and BYTE
> columns in select queries just like normal (but rather long) VARCHAR
> fields. Since all strings are "counted" in PHP, this remains "binary
> safe". It is up to you to handle this correctly. The returned data can
> contain anything, you are responsible for the contents.
>
> If you set ifx\_blobinfile to 1, use the file name returned by
> ifx\_get\_blob(..) to get at the blob contents. Note that in this case
> YOU ARE RESPONSIBLE FOR DELETING THE TEMPORARY FILES CREATED BY
> INFORMIX when fetching the row. Every new row fetched will create new
> temporary files for every BYTE column.
>
> The location of the temporary files can be influenced by the
> environment variable "blobdir", default is "." (the current
> directory). Something like: putenv(blobdir=tmpblob"); will ease the
> cleaning up of temp files accidentally left behind (their names all
> start with "blb").

> **Note**: **Automatically trimming "char" (SQLCHAR and SQLNCHAR)
> data**  
>
> This can be set with the configuration variable
>
> ifx.charasvarchar: if set to 1 trailing spaces will be automatically
> trimmed, to save you some "chopping".

> **Note**: ****`NULL`** values**  
>
> The configuration variable ifx.nullformat (and the runtime function
> <span class="function">ifx\_nullformat</span>) when set to **`TRUE`**
> will return **`NULL`** columns as the string "**`NULL`**", when set to
> **`FALSE`** they return the empty string. This allows you to
> discriminate between **`NULL`** columns and empty columns.

| Name                                                            | Default | Changeable       | Changelog             |
|-----------------------------------------------------------------|---------|------------------|-----------------------|
| <a href="/book/ifx.html#" class="link">ifx.allow_persistent</a> | "1"     | PHP\_INI\_SYSTEM | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.max_persistent</a>   | "-1"    | PHP\_INI\_SYSTEM | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.max_links</a>        | "-1"    | PHP\_INI\_SYSTEM | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.default_host</a>     | NULL    | PHP\_INI\_SYSTEM | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.default_user</a>     | NULL    | PHP\_INI\_SYSTEM | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.default_password</a> | NULL    | PHP\_INI\_SYSTEM | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.blobinfile</a>       | "1"     | PHP\_INI\_ALL    | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.textasvarchar</a>    | "0"     | PHP\_INI\_ALL    | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.byteasvarchar</a>    | "0"     | PHP\_INI\_ALL    | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.charasvarchar</a>    | "0"     | PHP\_INI\_ALL    | Removed in PHP 5.2.1. |
| <a href="/book/ifx.html#" class="link">ifx.nullformat</a>       | "0"     | PHP\_INI\_ALL    | Removed in PHP 5.2.1. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`ifx.allow_persistent` <span class="type">bool</span>  
Whether to allow persistent Informix connections.

`ifx.max_persistent` <span class="type">int</span>  
The maximum number of persistent Informix connections per process.

`ifx.max_links` <span class="type">int</span>  
The maximum number of Informix connections per process, including
persistent connections.

`ifx.default_host` <span class="type">string</span>  
The default host to connect to when no host is specified in <span
class="function">ifx\_connect</span> or <span
class="function">ifx\_pconnect</span>.

`ifx.default_user` <span class="type">string</span>  
The default user id to use when none is specified in <span
class="function">ifx\_connect</span> or <span
class="function">ifx\_pconnect</span>.

`ifx.default_password` <span class="type">string</span>  
The default password to use when none is specified in <span
class="function">ifx\_connect</span> or <span
class="function">ifx\_pconnect</span>.

`ifx.blobinfile` <span class="type">bool</span>  
Set to **`TRUE`** if you want to return blob columns in a file,
**`FALSE`** if you want them in memory. You can override the setting at
runtime with <span class="function">ifx\_blobinfile\_mode</span>.

`ifx.textasvarchar` <span class="type">bool</span>  
Set to **`TRUE`** if you want to return TEXT columns as normal strings
in select statements, **`FALSE`** if you want to use blob id parameters.
You can override the setting at runtime with <span
class="function">ifx\_textasvarchar</span>.

`ifx.byteasvarchar` <span class="type">bool</span>  
Set to **`TRUE`** if you want to return BYTE columns as normal strings
in select queries, **`FALSE`** if you want to use blob id parameters.
You can override the setting at runtime with <span
class="function">ifx\_textasvarchar</span>.

`ifx.charasvarchar` <span class="type">bool</span>  
Set to **`TRUE`** if you want to trim trailing spaces from CHAR columns
when fetching them.

`ifx.nullformat` <span class="type">bool</span>  
Set to **`TRUE`** if you want to return **`NULL`** columns as the
literal string "**`NULL`**", **`FALSE`** if you want them returned as
the empty string "". You can override this setting at runtime with <span
class="function">ifx\_nullformat</span>.

Resource Types
--------------

This extension has no resource types defined.

Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`IFX_SCROLL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`IFX_HOLD`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`IFX_LO_RDONLY`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`IFX_LO_WRONLY`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`IFX_LO_APPEND`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`IFX_LO_RDWR`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`IFX_LO_BUFFER`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`IFX_LO_NOBUFFER`** (<span class="type">int</span>)  
<span class="simpara"> </span>

ifx\_affected\_rows
===================

Get number of rows affected by a query

### Description

<span class="type">int</span> <span
class="methodname">ifx\_affected\_rows</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

Returns the number of rows affected by a query associated with
`result_id`.

For inserts, updates and deletes the number is the real number
(sqlerrd\[2\]) of affected rows. For selects it is an estimate
(sqlerrd\[0\]). Don't rely on it. The database server can never return
the actual number of rows that will be returned by a SELECT because it
has not even begun fetching them at this stage (just after the "PREPARE"
when the optimizer has determined the query plan).

Useful after <span class="function">ifx\_prepare</span> to limit queries
to reasonable result sets.

### Parameters

`result_id`  
A valid result id returned by <span class="function">ifx\_query</span>
or <span class="function">ifx\_prepare</span>.

### Return Values

Returns the number of rows as an integer.

### Examples

**Example \#1 Informix affected rows**

``` php
<?php
$rid = ifx_prepare("select * from emp
                     where name like " . $name, $connid);
if (! $rid) {
    /* ... error ... */
}
$rowcount = ifx_affected_rows($rid);
if ($rowcount > 1000) {
    printf ("Too many rows in result set (%d)\n<br />", $rowcount);
    die ("Please restrict your query<br />\n");
}
?>
```

### See Also

-   <span class="function">ifx\_num\_rows</span>

ifx\_blobinfile\_mode
=====================

Set the default blob mode for all select queries

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_blobinfile\_mode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Set the default blob mode for all select queries.

### Parameters

`mode`  
Mode "0" means save Byte-Blobs in memory, and mode "1" means save
Byte-Blobs in a file.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

ifx\_byteasvarchar
==================

Set the default byte mode

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_byteasvarchar</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Sets the default byte mode for all select-queries.

### Parameters

`mode`  
Mode "0" will return a blob id, and mode "1" will return a varchar with
text content.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifx\_textasvarchar</span>

ifx\_close
==========

Close Informix connection

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_close</span> (\[ <span class="methodparam"><span
class="type">resource</span> `$link_identifier`</span> \] )

<span class="function">ifx\_close</span> closes the link to an Informix
database that's associated with the specified link identifier.

Note that this isn't usually necessary, as non-persistent open links are
automatically closed at the end of the script's execution.

<span class="function">ifx\_close</span> will not close persistent links
generated by <span class="function">ifx\_pconnect</span>.

### Parameters

`link_identifier`  
The link identifier. If not specified, the last opened link is assumed.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Closing a Informix connection**

``` php
<?php
$conn_id = ifx_connect ("mydb@ol_srv", "itsme", "mypassword");
/* ... some queries and stuff ... */
ifx_close($conn_id);
?>
```

### See Also

-   <span class="function">ifx\_connect</span>
-   <span class="function">ifx\_pconnect</span>

ifx\_connect
============

Open Informix server connection

### Description

<span class="type">resource</span> <span
class="methodname">ifx\_connect</span> (\[ <span
class="methodparam"><span class="type">string</span> `$database`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$userid`</span> \[, <span class="methodparam"><span
class="type">string</span> `$password`</span> \]\]\] )

<span class="function">ifx\_connect</span> establishes a connection to
an Informix server.

In case a second call is made to <span
class="function">ifx\_connect</span> with the same arguments, no new
link will be established, but instead, the link identifier of the
already opened link will be returned.

The link to the server will be closed as soon as the execution of the
script ends, unless it's closed earlier by explicitly calling <span
class="function">ifx\_close</span>.

### Parameters

All of the arguments are optional, and if they're missing, defaults are
taken from values supplied in `php.ini` (ifx.default\_host for the host
(Informix libraries will use `INFORMIXSERVER` environment value if not
defined), ifx.default\_user for user, ifx.default\_password for the
password (none if not defined).

`database`  
The database name, as a string.

`userid`  
The username, as a string.

`password`  
The password, as a string.

### Return Values

Returns a connection identifier on success, or **`FALSE`** on error.

### Examples

**Example \#1 Connect to a Informix database**

``` php
<?php
$conn_id = ifx_connect ("mydb@ol_srv1", "imyself", "mypassword");
?>
```

### See Also

-   <span class="function">ifx\_pconnect</span>
-   <span class="function">ifx\_close</span>

ifx\_copy\_blob
===============

Duplicates the given blob object

### Description

<span class="type">int</span> <span
class="methodname">ifx\_copy\_blob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> )

Duplicates the given blob object.

### Parameters

`bid`  
A BLOB identifier.

### Return Values

Returns the new blob object-id, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifx\_create\_blob</span>
-   <span class="function">ifx\_free\_blob</span>

ifx\_create\_blob
=================

Creates an blob object

### Description

<span class="type">int</span> <span
class="methodname">ifx\_create\_blob</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">int</span> `$mode`</span> , <span
class="methodparam"><span class="type">string</span> `$param`</span> )

Creates a blob object.

### Parameters

`type`  
1 = TEXT, 0 = BYTE

`mode`  
0 = blob-object holds the content in memory, 1 = blob-object holds the
content in file.

`param`  
if mode = 0: pointer to the content, if mode = 1: pointer to the
filestring.

### Return Values

Returns the new BLOB object-id, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifx\_copy\_blob</span>
-   <span class="function">ifx\_free\_blob</span>

ifx\_create\_char
=================

Creates an char object

### Description

<span class="type">int</span> <span
class="methodname">ifx\_create\_char</span> ( <span
class="methodparam"><span class="type">string</span> `$param`</span> )

Creates an char object.

### Parameters

`param`  
The char content.

### Return Values

Returns the new char object id, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifx\_free\_char</span>

ifx\_do
=======

Execute a previously prepared SQL-statement

### Description

<span class="type">bool</span> <span class="methodname">ifx\_do</span> (
<span class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

Executes a previously prepared query or opens a cursor for it.

Does NOT free `result_id` on error.

Also sets the real number of <span
class="function">ifx\_affected\_rows</span> for non-select statements
for retrieval by <span class="function">ifx\_affected\_rows</span>.

### Parameters

`result_id`  
`result_id` is a valid resultid returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

**Example \#1 <span class="function">ifx\_do</span> Example**

``` php
<?php
$conn = fx_connect( "db", "user", "password" );
$result = ifx_prepare("SELECT customer_num, company FROM customer", $conn);
ifx_do($result);
?>
```

### See Also

-   <span class="function">ifx\_prepare</span>

ifx\_error
==========

Returns error code of last Informix call

### Description

<span class="type">string</span> <span
class="methodname">ifx\_error</span> (\[ <span class="methodparam"><span
class="type">resource</span> `$link_identifier`</span> \] )

Returns in a string one character describing the general results of a
statement and both SQLSTATE and SQLCODE associated with the most recent
SQL statement executed.

### Parameters

`link_identifier`  
The link identifier.

### Return Values

The Informix error codes (SQLSTATE & SQLCODE) formatted as *x \[SQLSTATE
= aa bbb SQLCODE=cccc\]*.

where x = space : no error

E : error

N : no more data

W : warning

? : undefined

If the "x" character is anything other than space, SQLSTATE and SQLCODE
describe the error in more detail.

See the Informix manual for the description of SQLSTATE and SQLCODE

### See Also

-   <span class="function">ifx\_errormsg</span>

ifx\_errormsg
=============

Returns error message of last Informix call

### Description

<span class="type">string</span> <span
class="methodname">ifx\_errormsg</span> (\[ <span
class="methodparam"><span class="type">int</span> `$errorcode`</span> \]
)

Returns the Informix error message associated with the most recent
Informix error.

### Parameters

`errorcode`  
If specified, the function will return the message corresponding to the
specified code.

### Return Values

Return the error message, as a string.

### Examples

**Example \#1 <span class="function">ifx\_errormsg</span> example**

``` php
<?php
printf("%s\n<br>", ifx_errormsg(-201));
?>
```

### See Also

-   <span class="function">ifx\_error</span>

ifx\_fetch\_row
===============

Get row as an associative array

### Description

<span class="type">array</span> <span
class="methodname">ifx\_fetch\_row</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$position`</span> \] )

Fetches one row of data from the result associated with the specified
result identifier.

Subsequent calls to <span class="function">ifx\_fetch\_row</span> would
return the next row in the result set, or **`FALSE`** if there are no
more rows.

### Parameters

`result_id`  
`result_id` is a valid resultid returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

`position`  
An optional parameter for a "fetch" operation on "scroll" cursors:
*NEXT*, *PREVIOUS*, *CURRENT*, *FIRST*, *LAST* or a number. If you
specify a number, an "absolute" row fetch is executed. This parameter is
optional, and only valid for SCROLL cursors.

### Return Values

Returns an associative array that corresponds to the fetched row, or
**`FALSE`** if there are no more rows.

Blob columns are returned as integer blob id values for use in <span
class="function">ifx\_get\_blob</span> unless you have used
ifx\_textasvarchar(1) or ifx\_byteasvarchar(1), in which case blobs are
returned as string values.

### Examples

**Example \#1 Informix fetch rows**

``` php
<?php
$rid = ifx_prepare ("select * from emp where name like " . $name,
                     $connid, IFX_SCROLL);
if (! $rid) {
    /* ... error ... */
}
$rowcount = ifx_affected_rows($rid);
if ($rowcount > 1000) {
    printf ("Too many rows in result set (%d)\n<br />", $rowcount);
    die ("Please restrict your query<br />\n");
}
if (! ifx_do ($rid)) {
   /* ... error ... */
}
$row = ifx_fetch_row ($rid, "NEXT");
while (is_array($row)) {
    for (reset($row); $fieldname=key($row); next($row)) {
        $fieldvalue = $row[$fieldname];
        printf ("%s = %s,", $fieldname, $fieldvalue);
    }
    printf("\n<br />");
    $row = ifx_fetch_row($rid, "NEXT");
}
ifx_free_result ($rid);
?>
```

ifx\_fieldproperties
====================

List of SQL fieldproperties

### Description

<span class="type">array</span> <span
class="methodname">ifx\_fieldproperties</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

Returns the Informix SQL fieldproperties of every field in the query as
an associative array. Properties are encoded as:
"SQLTYPE;length;precision;scale;ISNULLABLE" where SQLTYPE = the Informix
type like "SQLVCHAR" etc. and ISNULLABLE = "Y" or "N".

### Parameters

`result_id`  
`result_id` is a valid resultid returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

### Return Values

Returns an associative array with fieldnames as key and the SQL
fieldproperties as data for a query with `result_id`. Returns
**`FALSE`** on errors.

### Examples

**Example \#1 Informix SQL fieldproperties**

``` php
<?php
$properties = ifx_fieldproperties($resultid);
if (!isset($properties)) {
    /* ... error ... */
}
foreach ($properties as $fname => $val) {
    echo "$fname:\t property = $val\n";
}
?>
```

### See Also

-   <span class="function">ifx\_fieldtypes</span>

ifx\_fieldtypes
===============

List of Informix SQL fields

### Description

<span class="type">array</span> <span
class="methodname">ifx\_fieldtypes</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

Returns an associative array with fieldnames as key and the SQL
fieldtypes as data for the query associated with `result_id`.

### Parameters

`result_id`  
`result_id` is a valid resultid returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

### Return Values

Returns an associative array with fieldnames as key and the SQL
fieldtypes as data for query with `result_id`. Returns **`FALSE`** on
error.

### Examples

**Example \#1 Fieldnames and SQL fieldtypes**

``` php
<?php
$types = ifx_fieldtypes($resultid);
if (is_array($types)) {
    foreach ($types as $fname => $val) {
        echo "$fname:\t type = $val\n";
    }
}
?>
```

### See Also

-   <span class="function">ifx\_fieldproperties</span>

ifx\_free\_blob
===============

Deletes the blob object

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_free\_blob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> )

Deletes the blobobject for the given blob object-id.

### Parameters

`bid`  
The BLOB object id.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifx\_create\_blob</span>

ifx\_free\_char
===============

Deletes the char object

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_free\_char</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> )

Deletes the charobject for the given char object-id.

### Parameters

`bid`  
The char object id.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifx\_create\_char</span>

ifx\_free\_result
=================

Releases resources for the query

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_free\_result</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

Releases resources for the query associated with `result_id`.

### Parameters

`result_id`  
`result_id` is a valid resultid returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifx\_do</span>

ifx\_get\_blob
==============

Return the content of a blob object

### Description

<span class="type">string</span> <span
class="methodname">ifx\_get\_blob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> )

Returns the content of the blob object.

### Parameters

`bid`  
The BLOB object id.

### Return Values

The contents of the BLOB as a string, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifx\_get\_char</span>

ifx\_get\_char
==============

Return the content of the char object

### Description

<span class="type">string</span> <span
class="methodname">ifx\_get\_char</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> )

Returns the content of the char object.

### Parameters

`bid`  
The char object-id.

### Return Values

Returns the contents as a string, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifx\_get\_blob</span>

ifx\_getsqlca
=============

Get the contents of sqlca.sqlerrd\[0..5\] after a query

### Description

<span class="type">array</span> <span
class="methodname">ifx\_getsqlca</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

Returns a pseudo-row with sqlca.sqlerrd\[0\] ... sqlca.sqlerrd\[5\]
after the query associated with `result_id`.

For inserts, updates and deletes the values returned are those as set by
the server after executing the query. This gives access to the number of
affected rows and the serial insert value. For *SELECT*s the values are
those saved after the *PREPARE* statement. This gives access to the
\*estimated\* number of affected rows. The use of this function saves
the overhead of executing a *SELECT dbinfo('sqlca.sqlerrdx')* query, as
it retrieves the values that were saved by the ifx driver at the
appropriate moment.

### Parameters

`result_id`  
`result_id` is a valid result id returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

### Return Values

Returns an associative array with the following entries: *sqlerrd0*,
*sqlerrd1*, *sqlerrd2*, *sqlerrd3*, *sqlerrd4* and *sqlerrd5*.

### Examples

**Example \#1 Retrieve Informix sqlca.sqlerrd\[x\] values**

``` php
<?php
/* assume the first column of 'sometable' is a serial */
$qid = ifx_query("insert into sometable
                  values (0, '2nd column', 'another column') ", $connid);
if (!$qid) {
    /* ... error ... */
}
$sqlca = ifx_getsqlca($qid);
$serial_value = $sqlca["sqlerrd1"];
echo "The serial value of the inserted row is : $serial_value<br />\n";
?>
```

ifx\_htmltbl\_result
====================

Formats all rows of a query into a HTML table

### Description

<span class="type">int</span> <span
class="methodname">ifx\_htmltbl\_result</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> \[, <span class="methodparam"><span
class="type">string</span> `$html_table_options`</span> \] )

Formats and prints all rows of the `result_id` query into a HTML table.

### Parameters

`result_id`  
`result_id` is a valid resultid returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

`html_table_options`  
This optional argument is a string of \<table\> tag options.

### Return Values

Returns the number of fetched rows, or **`FALSE`** on errors.

### Examples

**Example \#1 Informix results as HTML table**

``` php
<?php
$rid = ifx_prepare ("select * from emp where name like " . $name,
                     $connid, IFX_SCROLL);
if (! $rid) {
    /* ... error ... */
}
$rowcount = ifx_affected_rows ($rid);
if ($rowcount > 1000) {
    printf ("Too many rows in result set (%d)\n<br />", $rowcount);
    die ("Please restrict your query<br />\n");
}
if (! ifx_do($rid)) {
    /* ... error ... */
}

ifx_htmltbl_result ($rid, "border=\"2\"");

ifx_free_result($rid);
?>
```

ifx\_nullformat
===============

Sets the default return value on a fetch row

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_nullformat</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Sets the default return value of a NULL-value on a fetch row.

### Parameters

`mode`  
Mode "0" returns "", and mode "1" returns "**`NULL`**".

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

ifx\_num\_fields
================

Returns the number of columns in the query

### Description

<span class="type">int</span> <span
class="methodname">ifx\_num\_fields</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

After preparing or executing a query, this call gives you the number of
columns in the query.

### Parameters

`result_id`  
`result_id` is a valid resultid returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

### Return Values

Returns the number of columns in query for `result_id`, or **`FALSE`**
on errors.

### Examples

**Example \#1 <span class="function">ifx\_num\_fields</span> Example**

``` php
<?php
$conn_id = ifx_connect("db", "user", "password");
$res_id = ifx_query("select * from systables", $conn_id);
echo ifx_num_fields($res_id);
?>
```

### See Also

-   <span class="function">ifx\_num\_rows</span>

ifx\_num\_rows
==============

Count the rows already fetched from a query

### Description

<span class="type">int</span> <span
class="methodname">ifx\_num\_rows</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

Gives the number of rows fetched so far for a query with `result_id`
after a <span class="function">ifx\_query</span> or <span
class="function">ifx\_do</span> query.

### Parameters

`result_id`  
`result_id` is a valid resultid returned by <span
class="function">ifx\_query</span> or <span
class="function">ifx\_prepare</span> (select type queries only!).

### Return Values

Returns the number of fetched rows or **`FALSE`** on errors.

### See Also

-   <span class="function">ifx\_num\_fields</span>

ifx\_pconnect
=============

Open persistent Informix connection

### Description

<span class="type">resource</span> <span
class="methodname">ifx\_pconnect</span> (\[ <span
class="methodparam"><span class="type">string</span> `$database`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$userid`</span> \[, <span class="methodparam"><span
class="type">string</span> `$password`</span> \]\]\] )

<span class="function">ifx\_pconnect</span> acts very much like <span
class="function">ifx\_connect</span> with two major differences.

First, when connecting, the function would first try to find a
(persistent) link that's already open with the same host, username and
password. If one is found, an identifier for it will be returned instead
of opening a new connection.

Second, the connection to the SQL server will not be closed when the
execution of the script ends. Instead, the link will remain open for
future use (<span class="function">ifx\_close</span> will not close
links established by <span class="function">ifx\_pconnect</span>).

This type of links is therefore called 'persistent'.

### Parameters

All of the arguments are optional, and if they're missing, defaults are
taken from values supplied in `php.ini` (ifx.default\_host for the host
(Informix libraries will use `INFORMIXSERVER` environment value if not
defined), ifx.default\_user for user, ifx.default\_password for the
password (none if not defined).

`database`  
The database name, as a string.

`userid`  
The username, as a string.

`password`  
The password, as a string.

### Return Values

Returns: valid Informix persistent link identifier on success, or
**`FALSE`** on errors.

### See Also

-   <span class="function">ifx\_connect</span>

ifx\_prepare
============

Prepare an SQL-statement for execution

### Description

<span class="type">resource</span> <span
class="methodname">ifx\_prepare</span> ( <span class="methodparam"><span
class="type">string</span> `$query`</span> , <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> \[, <span class="methodparam"><span
class="type">int</span> `$cursor_def`</span> \], <span
class="methodparam"><span class="type">mixed</span>
`$blobidarray`</span> )

Prepares a `query` for later use with <span
class="function">ifx\_do</span>.

For "select-type" queries a cursor is declared and opened. Non-select
queries are "execute immediate".

For either query type the number of (estimated or real) affected rows is
saved for retrieval by <span
class="function">ifx\_affected\_rows</span>.

If the contents of the TEXT (or BYTE) column allow it, you can also use
*ifx\_textasvarchar(1)* and *ifx\_byteasvarchar(1)*. This allows you to
treat TEXT (or BYTE) columns just as if they were ordinary (but long)
VARCHAR columns for select queries, and you don't need to bother with
blob id's.

With *ifx\_textasvarchar(0)* or *ifx\_byteasvarchar(0)* (the default
situation), select queries will return BLOB columns as blob id's
(integer value). You can get the value of the blob as a string or file
with the blob functions (see below).

### Parameters

`query`  
The query string.

`link_identifier`  
The link identifier.

`cursor_def`  
This optional parameter allows you to make this a *scroll* and/or *hold*
cursor. It's a bitmask and can be either **`IFX_SCROLL`**,
**`IFX_HOLD`**, or both or'ed together.

`blobidarray`  
If you have BLOB (BYTE or TEXT) columns in the query, you can add a
`blobidarray` parameter containing the corresponding "blob ids", and you
should replace those columns with a "?" in the query text.

### Return Values

Returns a valid result identifier for use by <span
class="function">ifx\_do</span>, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifx\_do</span>

ifx\_query
==========

Send Informix query

### Description

<span class="type">resource</span> <span
class="methodname">ifx\_query</span> ( <span class="methodparam"><span
class="type">string</span> `$query`</span> , <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> \[, <span class="methodparam"><span
class="type">int</span> `$cursor_type`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$blobidarray`</span> \]\] )

Sends a `query` to the currently active database on the server that's
associated with the specified link identifier.

For "select-type" queries a cursor is declared and opened. Non-select
queries are "execute immediate".

For either query type the number of (estimated or real) affected rows is
saved for retrieval by <span
class="function">ifx\_affected\_rows</span>.

If the contents of the TEXT (or BYTE) column allow it, you can also use
*ifx\_textasvarchar(1)* and *ifx\_byteasvarchar(1)*. This allows you to
treat TEXT (or BYTE) columns just as if they were ordinary (but long)
VARCHAR columns for select queries, and you don't need to bother with
blob id's.

With *ifx\_textasvarchar(0)* or *ifx\_byteasvarchar(0)* (the default
situation), select queries will return BLOB columns as blob id's
(integer value). You can get the value of the blob as a string or file
with the blob functions (see below).

### Parameters

`query`  
The query string.

`link_identifier`  
The link identifier.

`cursor_def`  
This optional parameter allows you to make this a *scroll* and/or *hold*
cursor. It's a bitmask and can be either **`IFX_SCROLL`**,
**`IFX_HOLD`**, or both or'ed together. I you omit this parameter the
cursor is a normal sequential cursor.

`blobidarray`  
If you have BLOB (BYTE or TEXT) columns in the query, you can add a
`blobidarray` parameter containing the corresponding "blob ids", and you
should replace those columns with a "?" in the query text.

### Return Values

Returns valid Informix result identifier on success, or **`FALSE`** on
errors.

### Examples

**Example \#1 Show all rows of the "orders" table as a HTML table**

``` php
<?php
ifx_textasvarchar(1);      // use "text mode" for blobs
$res_id = ifx_query("select * from orders", $conn_id);
if (! $res_id) {
    printf("Can't select orders : %s\n<br />%s<br />\n", ifx_error(), ifx_errormsg());
    die;
}
ifx_htmltbl_result($res_id, "border=\"1\"");
ifx_free_result($res_id);
?>
```

**Example \#2 Insert some values into the "catalog" table**

``` php
<?php

// create blob id's for a byte and text column
$textid = ifx_create_blob(0, 0, "Text column in memory");
$byteid = ifx_create_blob(1, 0, "Byte column in memory");

// store blob id's in a blobid array
$blobidarray[] = $textid;
$blobidarray[] = $byteid;

// launch query
$query = "insert into catalog (stock_num, manu_code, " .
         "cat_descr,cat_picture) values(1,'HRO',?,?)";
$res_id = ifx_query($query, $conn_id, $blobidarray);
if (! $res_id) {
    /* ... error ... */
}

// free result id
ifx_free_result($res_id);
?>
```

### See Also

-   <span class="function">ifx\_connect</span>

ifx\_textasvarchar
==================

Set the default text mode

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_textasvarchar</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Sets the default text mode for all select-queries.

### Parameters

`mode`  
Mode "0" will return a blob id, and mode "1" will return a varchar with
text content.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifx\_byteasvarchar</span>

ifx\_update\_blob
=================

Updates the content of the blob object

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_update\_blob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> , <span
class="methodparam"><span class="type">string</span> `$content`</span> )

Updates the content of the blob object for the given blob object `bid`.

### Parameters

`bid`  
A BLOB object identifier.

`content`  
The new data, as a string.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifx\_update\_char</span>

ifx\_update\_char
=================

Updates the content of the char object

### Description

<span class="type">bool</span> <span
class="methodname">ifx\_update\_char</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> , <span
class="methodparam"><span class="type">string</span> `$content`</span> )

Updates the content of the char object for the given char object `bid`.

### Parameters

`bid`  
A char object identifier.

`content`  
The new data, as a string.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifx\_update\_blob</span>

ifxus\_close\_slob
==================

Deletes the slob object

### Description

<span class="type">bool</span> <span
class="methodname">ifxus\_close\_slob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> )

Deletes the slob object on the given slob object-id `bid`.

### Parameters

`bid`  
An existing slob id.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifxus\_open\_slob</span>

ifxus\_create\_slob
===================

Creates an slob object and opens it

### Description

<span class="type">int</span> <span
class="methodname">ifxus\_create\_slob</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Creates an slob object and opens it.

### Parameters

`mode`  
A combination of **`IFX_LO_RDONLY`**, **`IFX_LO_WRONLY`**,
**`IFX_LO_APPEND`** **`IFX_LO_RDWR`**, **`IFX_LO_BUFFER`**,
**`IFX_LO_NOBUFFER`**.

### Return Values

Return the new slob object-id, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifxus\_close\_slob</span>
-   <span class="function">ifxus\_free\_slob</span>

ifxus\_free\_slob
=================

Deletes the slob object

### Description

<span class="type">bool</span> <span
class="methodname">ifxus\_free\_slob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> )

Deletes the slob object.

### Parameters

`bid`  
An existing slob id.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">ifxus\_close\_slob</span>

ifxus\_open\_slob
=================

Opens an slob object

### Description

<span class="type">int</span> <span
class="methodname">ifxus\_open\_slob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> , <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Opens an slob object. `bid` should be an existing slob id.

### Parameters

`bid`  
An existing slob id.

`mode`  
A combination of **`IFX_LO_RDONLY`**, **`IFX_LO_WRONLY`**,
**`IFX_LO_APPEND`** **`IFX_LO_RDWR`**, **`IFX_LO_BUFFER`**,
**`IFX_LO_NOBUFFER`**.

### Return Values

Returns the new slob object-id, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifxus\_close\_slob</span>
-   <span class="function">ifxus\_free\_slob</span>

ifxus\_read\_slob
=================

Reads nbytes of the slob object

### Description

<span class="type">string</span> <span
class="methodname">ifxus\_read\_slob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> , <span
class="methodparam"><span class="type">int</span> `$nbytes`</span> )

Reads `nbytes` of the slob object.

### Parameters

`bid`  
An existing slob id.

`nbytes`  
The number of bytes to read.

### Return Values

Returns the slob contents as a string, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifxus\_write\_slob</span>

ifxus\_seek\_slob
=================

Sets the current file or seek position

### Description

<span class="type">int</span> <span
class="methodname">ifxus\_seek\_slob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> , <span
class="methodparam"><span class="type">int</span> `$mode`</span> , <span
class="methodparam"><span class="type">int</span> `$offset`</span> )

Sets the current file or seek position of an open slob object.

### Parameters

`bid`  
An existing slob id.

`mode`  
0 = LO\_SEEK\_SET, 1 = LO\_SEEK\_CUR, 2 = LO\_SEEK\_END.

`offset`  
A byte offset.

### Return Values

Returns the seek position as an integer, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifxus\_tell\_slob</span>

ifxus\_tell\_slob
=================

Returns the current file or seek position

### Description

<span class="type">int</span> <span
class="methodname">ifxus\_tell\_slob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> )

Returns the current file or seek position of an open slob object

### Parameters

`bid`  
An existing slob id.

### Return Values

Returns the seek position as an integer, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifxus\_seek\_slob</span>

ifxus\_write\_slob
==================

Writes a string into the slob object

### Description

<span class="type">int</span> <span
class="methodname">ifxus\_write\_slob</span> ( <span
class="methodparam"><span class="type">int</span> `$bid`</span> , <span
class="methodparam"><span class="type">string</span> `$content`</span> )

Writes a string into the slob object.

### Parameters

`bid`  
An existing slob id.

`content`  
The content to write, as a string.

### Return Values

Returns the bytes written as an integer, or **`FALSE`** on errors.

### See Also

-   <span class="function">ifxus\_read\_slob</span>

**Table of Contents**

-   [ifx\_affected\_rows](/book/ifx.html#ifx_affected_rows) — Get number
    of rows affected by a query
-   [ifx\_blobinfile\_mode](/book/ifx.html#ifx_blobinfile_mode) — Set
    the default blob mode for all select queries
-   [ifx\_byteasvarchar](/book/ifx.html#ifx_byteasvarchar) — Set the
    default byte mode
-   [ifx\_close](/book/ifx.html#ifx_close) — Close Informix connection
-   [ifx\_connect](/book/ifx.html#ifx_connect) — Open Informix server
    connection
-   [ifx\_copy\_blob](/book/ifx.html#ifx_copy_blob) — Duplicates the
    given blob object
-   [ifx\_create\_blob](/book/ifx.html#ifx_create_blob) — Creates an
    blob object
-   [ifx\_create\_char](/book/ifx.html#ifx_create_char) — Creates an
    char object
-   [ifx\_do](/book/ifx.html#ifx_do) — Execute a previously prepared
    SQL-statement
-   [ifx\_error](/book/ifx.html#ifx_error) — Returns error code of last
    Informix call
-   [ifx\_errormsg](/book/ifx.html#ifx_errormsg) — Returns error message
    of last Informix call
-   [ifx\_fetch\_row](/book/ifx.html#ifx_fetch_row) — Get row as an
    associative array
-   [ifx\_fieldproperties](/book/ifx.html#ifx_fieldproperties) — List of
    SQL fieldproperties
-   [ifx\_fieldtypes](/book/ifx.html#ifx_fieldtypes) — List of Informix
    SQL fields
-   [ifx\_free\_blob](/book/ifx.html#ifx_free_blob) — Deletes the blob
    object
-   [ifx\_free\_char](/book/ifx.html#ifx_free_char) — Deletes the char
    object
-   [ifx\_free\_result](/book/ifx.html#ifx_free_result) — Releases
    resources for the query
-   [ifx\_get\_blob](/book/ifx.html#ifx_get_blob) — Return the content
    of a blob object
-   [ifx\_get\_char](/book/ifx.html#ifx_get_char) — Return the content
    of the char object
-   [ifx\_getsqlca](/book/ifx.html#ifx_getsqlca) — Get the contents of
    sqlca.sqlerrd\[0..5\] after a query
-   [ifx\_htmltbl\_result](/book/ifx.html#ifx_htmltbl_result) — Formats
    all rows of a query into a HTML table
-   [ifx\_nullformat](/book/ifx.html#ifx_nullformat) — Sets the default
    return value on a fetch row
-   [ifx\_num\_fields](/book/ifx.html#ifx_num_fields) — Returns the
    number of columns in the query
-   [ifx\_num\_rows](/book/ifx.html#ifx_num_rows) — Count the rows
    already fetched from a query
-   [ifx\_pconnect](/book/ifx.html#ifx_pconnect) — Open persistent
    Informix connection
-   [ifx\_prepare](/book/ifx.html#ifx_prepare) — Prepare an
    SQL-statement for execution
-   [ifx\_query](/book/ifx.html#ifx_query) — Send Informix query
-   [ifx\_textasvarchar](/book/ifx.html#ifx_textasvarchar) — Set the
    default text mode
-   [ifx\_update\_blob](/book/ifx.html#ifx_update_blob) — Updates the
    content of the blob object
-   [ifx\_update\_char](/book/ifx.html#ifx_update_char) — Updates the
    content of the char object
-   [ifxus\_close\_slob](/book/ifx.html#ifxus_close_slob) — Deletes the
    slob object
-   [ifxus\_create\_slob](/book/ifx.html#ifxus_create_slob) — Creates an
    slob object and opens it
-   [ifxus\_free\_slob](/book/ifx.html#ifxus_free_slob) — Deletes the
    slob object
-   [ifxus\_open\_slob](/book/ifx.html#ifxus_open_slob) — Opens an slob
    object
-   [ifxus\_read\_slob](/book/ifx.html#ifxus_read_slob) — Reads nbytes
    of the slob object
-   [ifxus\_seek\_slob](/book/ifx.html#ifxus_seek_slob) — Sets the
    current file or seek position
-   [ifxus\_tell\_slob](/book/ifx.html#ifxus_tell_slob) — Returns the
    current file or seek position
-   [ifxus\_write\_slob](/book/ifx.html#ifxus_write_slob) — Writes a
    string into the slob object

Firebird/InterBase
==================

**Table of Contents**

-   [Introduction](/book/ibase.html#Introduction)
-   [Installing/Configuring](/book/ibase.html#Installing/Configuring)
    -   [Requirements](/book/ibase.html#Requirements)
    -   [Installation](/book/ibase.html#Installation)
    -   [Runtime
        Configuration](/book/ibase.html#Runtime%20Configuration)
    -   [Resource Types](/book/ibase.html#Resource%20Types)
-   [Predefined Constants](/book/ibase.html#Predefined%20Constants)
-   [Firebird/InterBase
    Functions](/book/ibase.html#Firebird/InterBase%20Functions)
    -   [fbird\_add\_user](/book/ibase.html#fbird_add_user) — Alias of
        ibase\_add\_user
    -   [fbird\_affected\_rows](/book/ibase.html#fbird_affected_rows) —
        Alias of ibase\_affected\_rows
    -   [fbird\_backup](/book/ibase.html#fbird_backup) — Alias of
        ibase\_backup
    -   [fbird\_blob\_add](/book/ibase.html#fbird_blob_add) — Alias of
        ibase\_blob\_add
    -   [fbird\_blob\_cancel](/book/ibase.html#fbird_blob_cancel) —
        Cancel creating blob
    -   [fbird\_blob\_close](/book/ibase.html#fbird_blob_close) — Alias
        of ibase\_blob\_close
    -   [fbird\_blob\_create](/book/ibase.html#fbird_blob_create) —
        Alias of ibase\_blob\_create
    -   [fbird\_blob\_echo](/book/ibase.html#fbird_blob_echo) — Alias of
        ibase\_blob\_echo
    -   [fbird\_blob\_get](/book/ibase.html#fbird_blob_get) — Alias of
        ibase\_blob\_get
    -   [fbird\_blob\_import](/book/ibase.html#fbird_blob_import) —
        Alias of ibase\_blob\_import
    -   [fbird\_blob\_info](/book/ibase.html#fbird_blob_info) — Alias of
        ibase\_blob\_info
    -   [fbird\_blob\_open](/book/ibase.html#fbird_blob_open) — Alias of
        ibase\_blob\_open
    -   [fbird\_close](/book/ibase.html#fbird_close) — Alias of
        ibase\_close
    -   [fbird\_commit\_ret](/book/ibase.html#fbird_commit_ret) — Alias
        of ibase\_commit\_ret
    -   [fbird\_commit](/book/ibase.html#fbird_commit) — Alias of
        ibase\_commit
    -   [fbird\_connect](/book/ibase.html#fbird_connect) — Alias of
        ibase\_connect
    -   [fbird\_db\_info](/book/ibase.html#fbird_db_info) — Alias of
        ibase\_db\_info
    -   [fbird\_delete\_user](/book/ibase.html#fbird_delete_user) —
        Alias of ibase\_delete\_user
    -   [fbird\_drop\_db](/book/ibase.html#fbird_drop_db) — Alias of
        ibase\_drop\_db
    -   [fbird\_errcode](/book/ibase.html#fbird_errcode) — Alias of
        ibase\_errcode
    -   [fbird\_errmsg](/book/ibase.html#fbird_errmsg) — Alias of
        ibase\_errmsg
    -   [fbird\_execute](/book/ibase.html#fbird_execute) — Alias of
        ibase\_execute
    -   [fbird\_fetch\_assoc](/book/ibase.html#fbird_fetch_assoc) —
        Alias of ibase\_fetch\_assoc
    -   [fbird\_fetch\_object](/book/ibase.html#fbird_fetch_object) —
        Alias of ibase\_fetch\_object
    -   [fbird\_fetch\_row](/book/ibase.html#fbird_fetch_row) — Alias of
        ibase\_fetch\_row
    -   [fbird\_field\_info](/book/ibase.html#fbird_field_info) — Alias
        of ibase\_field\_info
    -   [fbird\_free\_event\_handler](/book/ibase.html#fbird_free_event_handler)
        — Alias of ibase\_free\_event\_handler
    -   [fbird\_free\_query](/book/ibase.html#fbird_free_query) — Alias
        of ibase\_free\_query
    -   [fbird\_free\_result](/book/ibase.html#fbird_free_result) —
        Alias of ibase\_free\_result
    -   [fbird\_gen\_id](/book/ibase.html#fbird_gen_id) — Alias of
        ibase\_gen\_id
    -   [fbird\_maintain\_db](/book/ibase.html#fbird_maintain_db) —
        Alias of ibase\_maintain\_db
    -   [fbird\_modify\_user](/book/ibase.html#fbird_modify_user) —
        Alias of ibase\_modify\_user
    -   [fbird\_name\_result](/book/ibase.html#fbird_name_result) —
        Alias of ibase\_name\_result
    -   [fbird\_num\_fields](/book/ibase.html#fbird_num_fields) — Alias
        of ibase\_num\_fields
    -   [fbird\_num\_params](/book/ibase.html#fbird_num_params) — Alias
        of ibase\_num\_params
    -   [fbird\_param\_info](/book/ibase.html#fbird_param_info) — Alias
        of ibase\_param\_info
    -   [fbird\_pconnect](/book/ibase.html#fbird_pconnect) — Alias of
        ibase\_pconnect
    -   [fbird\_prepare](/book/ibase.html#fbird_prepare) — Alias of
        ibase\_prepare
    -   [fbird\_query](/book/ibase.html#fbird_query) — Alias of
        ibase\_query
    -   [fbird\_restore](/book/ibase.html#fbird_restore) — Alias of
        ibase\_restore
    -   [fbird\_rollback\_ret](/book/ibase.html#fbird_rollback_ret) —
        Alias of ibase\_rollback\_ret
    -   [fbird\_rollback](/book/ibase.html#fbird_rollback) — Alias of
        ibase\_rollback
    -   [fbird\_server\_info](/book/ibase.html#fbird_server_info) —
        Alias of ibase\_server\_info
    -   [fbird\_service\_attach](/book/ibase.html#fbird_service_attach)
        — Alias of ibase\_service\_attach
    -   [fbird\_service\_detach](/book/ibase.html#fbird_service_detach)
        — Alias of ibase\_service\_detach
    -   [fbird\_set\_event\_handler](/book/ibase.html#fbird_set_event_handler)
        — Alias of ibase\_set\_event\_handler
    -   [fbird\_trans](/book/ibase.html#fbird_trans) — Alias of
        ibase\_trans
    -   [fbird\_wait\_event](/book/ibase.html#fbird_wait_event) — Alias
        of ibase\_wait\_event
    -   [ibase\_add\_user](/book/ibase.html#ibase_add_user) — Add a user
        to a security database
    -   [ibase\_affected\_rows](/book/ibase.html#ibase_affected_rows) —
        Return the number of rows that were affected by the previous
        query
    -   [ibase\_backup](/book/ibase.html#ibase_backup) — Initiates a
        backup task in the service manager and returns immediately
    -   [ibase\_blob\_add](/book/ibase.html#ibase_blob_add) — Add data
        into a newly created blob
    -   [ibase\_blob\_cancel](/book/ibase.html#ibase_blob_cancel) —
        Cancel creating blob
    -   [ibase\_blob\_close](/book/ibase.html#ibase_blob_close) — Close
        blob
    -   [ibase\_blob\_create](/book/ibase.html#ibase_blob_create) —
        Create a new blob for adding data
    -   [ibase\_blob\_echo](/book/ibase.html#ibase_blob_echo) — Output
        blob contents to browser
    -   [ibase\_blob\_get](/book/ibase.html#ibase_blob_get) — Get len
        bytes data from open blob
    -   [ibase\_blob\_import](/book/ibase.html#ibase_blob_import) —
        Create blob, copy file in it, and close it
    -   [ibase\_blob\_info](/book/ibase.html#ibase_blob_info) — Return
        blob length and other useful info
    -   [ibase\_blob\_open](/book/ibase.html#ibase_blob_open) — Open
        blob for retrieving data parts
    -   [ibase\_close](/book/ibase.html#ibase_close) — Close a
        connection to an InterBase database
    -   [ibase\_commit\_ret](/book/ibase.html#ibase_commit_ret) — Commit
        a transaction without closing it
    -   [ibase\_commit](/book/ibase.html#ibase_commit) — Commit a
        transaction
    -   [ibase\_connect](/book/ibase.html#ibase_connect) — Open a
        connection to a database
    -   [ibase\_db\_info](/book/ibase.html#ibase_db_info) — Request
        statistics about a database
    -   [ibase\_delete\_user](/book/ibase.html#ibase_delete_user) —
        Delete a user from a security database
    -   [ibase\_drop\_db](/book/ibase.html#ibase_drop_db) — Drops a
        database
    -   [ibase\_errcode](/book/ibase.html#ibase_errcode) — Return an
        error code
    -   [ibase\_errmsg](/book/ibase.html#ibase_errmsg) — Return error
        messages
    -   [ibase\_execute](/book/ibase.html#ibase_execute) — Execute a
        previously prepared query
    -   [ibase\_fetch\_assoc](/book/ibase.html#ibase_fetch_assoc) —
        Fetch a result row from a query as an associative array
    -   [ibase\_fetch\_object](/book/ibase.html#ibase_fetch_object) —
        Get an object from a InterBase database
    -   [ibase\_fetch\_row](/book/ibase.html#ibase_fetch_row) — Fetch a
        row from an InterBase database
    -   [ibase\_field\_info](/book/ibase.html#ibase_field_info) — Get
        information about a field
    -   [ibase\_free\_event\_handler](/book/ibase.html#ibase_free_event_handler)
        — Cancels a registered event handler
    -   [ibase\_free\_query](/book/ibase.html#ibase_free_query) — Free
        memory allocated by a prepared query
    -   [ibase\_free\_result](/book/ibase.html#ibase_free_result) — Free
        a result set
    -   [ibase\_gen\_id](/book/ibase.html#ibase_gen_id) — Increments the
        named generator and returns its new value
    -   [ibase\_maintain\_db](/book/ibase.html#ibase_maintain_db) —
        Execute a maintenance command on the database server
    -   [ibase\_modify\_user](/book/ibase.html#ibase_modify_user) —
        Modify a user to a security database
    -   [ibase\_name\_result](/book/ibase.html#ibase_name_result) —
        Assigns a name to a result set
    -   [ibase\_num\_fields](/book/ibase.html#ibase_num_fields) — Get
        the number of fields in a result set
    -   [ibase\_num\_params](/book/ibase.html#ibase_num_params) — Return
        the number of parameters in a prepared query
    -   [ibase\_param\_info](/book/ibase.html#ibase_param_info) — Return
        information about a parameter in a prepared query
    -   [ibase\_pconnect](/book/ibase.html#ibase_pconnect) — Open a
        persistent connection to an InterBase database
    -   [ibase\_prepare](/book/ibase.html#ibase_prepare) — Prepare a
        query for later binding of parameter placeholders and execution
    -   [ibase\_query](/book/ibase.html#ibase_query) — Execute a query
        on an InterBase database
    -   [ibase\_restore](/book/ibase.html#ibase_restore) — Initiates a
        restore task in the service manager and returns immediately
    -   [ibase\_rollback\_ret](/book/ibase.html#ibase_rollback_ret) —
        Roll back a transaction without closing it
    -   [ibase\_rollback](/book/ibase.html#ibase_rollback) — Roll back a
        transaction
    -   [ibase\_server\_info](/book/ibase.html#ibase_server_info) —
        Request information about a database server
    -   [ibase\_service\_attach](/book/ibase.html#ibase_service_attach)
        — Connect to the service manager
    -   [ibase\_service\_detach](/book/ibase.html#ibase_service_detach)
        — Disconnect from the service manager
    -   [ibase\_set\_event\_handler](/book/ibase.html#ibase_set_event_handler)
        — Register a callback function to be called when events are
        posted
    -   [ibase\_trans](/book/ibase.html#ibase_trans) — Begin a
        transaction
    -   [ibase\_wait\_event](/book/ibase.html#ibase_wait_event) — Wait
        for an event to be posted by the database

Firebird is a relational database offering many ISO SQL-2003 features
that runs on Linux, Windows, and a variety of Unix platforms. Firebird
offers excellent concurrency, high performance, and powerful language
support for stored procedures and triggers. It has been used in
production systems, under a variety of names since 1981.

InterBase is the name of the closed-source variant of this RDBMS that
was developed by Embarcadero/Inprise. More information about InterBase
is available at
<a href="http://www.embarcadero.com/products/interbase" class="link external">» http://www.embarcadero.com/products/interbase</a>.

Firebird is a commercially independent project (fundation) of C++
programmers, technical advisors and supporters developing and enhancing
a multi-platform relational database management system based on the
source code released by Inprise Corp (now known as Embarcadero) under
the InterBase Public License v.1.0 on 25 July, 2000. More information
about Firebird is available at
<a href="http://www.firebirdsql.org/" class="link external">» http://www.firebirdsql.org/</a>.

> **Note**:
>
> This extension has been moved to the
> <a href="https://pecl.php.net/" class="link external">» PECL</a>
> repository and is no longer bundled with PHP as of PHP 7.4.0
>
> This extension supports InterBase versions 6 and up and Firebird
> version 2.0 and up.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/ibase.html#Requirements)
-   [Installation](/book/ibase.html#Installation)
-   [Runtime Configuration](/book/ibase.html#Runtime%20Configuration)
-   [Resource Types](/book/ibase.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 7.4.0

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/ibase" class="link external">» https://pecl.php.net/package/ibase</a>.

To enable Firebird/InterBase support configure PHP
**--with-interbase\[=DIR\]**, where DIR is the Firebird/InterBase base
install directory, which defaults to `/usr`.

> **Note**: **Note to Win32/Win64 Users**  
>
> In order for this extension to work, there are DLL files that must be
> available to the Windows system `PATH`. For information on how to do
> this, see the FAQ entitled
> "<a href="/faq/installation.html#faq.installation.addtopath" class="link">How do I add my PHP directory to the PATH on Windows</a>".
> Although copying DLL files from the PHP folder into the Windows system
> directory also works (because the system directory is by default in
> the system's `PATH`), this is not recommended. *This extension
> requires the following files to be in the `PATH`:*
> `fbclient.dll,gds32.dll`
>
> If you installed the Firebird/InterBase database server on the same
> machine PHP is running on, you will have this DLL already and
> `fbclient.dll,gds32.dll` (gds32.dll is generated from the installer
> for legacy applications) will already be in the `PATH`.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                | Default             | Changeable       | Changelog |
|---------------------------------------------------------------------|---------------------|------------------|-----------|
| <a href="/book/ibase.html#" class="link">ibase.allow_persistent</a> | "1"                 | PHP\_INI\_SYSTEM |           |
| <a href="/book/ibase.html#" class="link">ibase.max_persistent</a>   | "-1"                | PHP\_INI\_SYSTEM |           |
| <a href="/book/ibase.html#" class="link">ibase.max_links</a>        | "-1"                | PHP\_INI\_SYSTEM |           |
| <a href="/book/ibase.html#" class="link">ibase.default_db</a>       | NULL                | PHP\_INI\_SYSTEM |           |
| <a href="/book/ibase.html#" class="link">ibase.default_user</a>     | NULL                | PHP\_INI\_ALL    |           |
| <a href="/book/ibase.html#" class="link">ibase.default_password</a> | NULL                | PHP\_INI\_ALL    |           |
| <a href="/book/ibase.html#" class="link">ibase.default_charset</a>  | NULL                | PHP\_INI\_ALL    |           |
| <a href="/book/ibase.html#" class="link">ibase.timestampformat</a>  | "%Y-%m-%d %H:%M:%S" | PHP\_INI\_ALL    |           |
| <a href="/book/ibase.html#" class="link">ibase.dateformat</a>       | "%Y-%m-%d"          | PHP\_INI\_ALL    |           |
| <a href="/book/ibase.html#" class="link">ibase.timeformat</a>       | "%H:%M:%S"          | PHP\_INI\_ALL    |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`ibase.allow_persistent` <span class="type">bool</span>  
Whether to allow
<a href="/features/persistent-connections.html" class="link">persistent connections</a>
to Firebird/InterBase.

`ibase.max_persistent` <span class="type">int</span>  
The maximum number of persistent Firebird/InterBase connections per
process. New connections created with ibase\_pconnect() will be
non-persistent if this number would be exceeded.

`ibase.max_links` <span class="type">int</span>  
The maximum number of Firebird/InterBase connections per process,
including persistent connections.

`ibase.default_db` <span class="type">string</span>  
The default database to connect to when ibase\_\[p\]connect() is called
without specifying a database name. If this value is set and SQL safe
mode is enabled, no other connections than to this database will be
allowed.

`ibase.default_user` <span class="type">string</span>  
The user name to use when connecting to a database if no user name is
specified.

`ibase.default_password` <span class="type">string</span>  
The password to use when connecting to a database if no password is
specified.

`ibase.default_charset` <span class="type">string</span>  
The character set to use when connecting to a database if no character
set is specified.

`ibase.timestampformat` <span class="type">string</span>  

`ibase.dateformat` <span class="type">string</span>  

`ibase.timeformat` <span class="type">string</span>  
These directives are used to set the date and time formats that are used
when returning dates and times from a result set, or when binding
arguments to date and time parameters.

Resource Types
--------------

This extension has no resource types defined.

Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

The following constants can be passed to <span
class="function">ibase\_trans</span> to specify transaction behaviour.

| Constant           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IBASE\_DEFAULT     | The default transaction settings are to be used. This default is determined by the client library, which defines it as IBASE\_WRITE\|IBASE\_CONCURRENCY\|IBASE\_WAIT in most cases.                                                                                                                                                                                                                                                                                                                       |
| IBASE\_READ        | Starts a read-only transaction.                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| IBASE\_WRITE       | Starts a read-write transaction.                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| IBASE\_CONSISTENCY | Starts a transaction with the isolation level set to 'consistency', which means the transaction cannot read from tables that are being modified by other concurrent transactions.                                                                                                                                                                                                                                                                                                                         |
| IBASE\_CONCURRENCY | Starts a transaction with the isolation level set to 'concurrency' (or 'snapshot'), which means the transaction has access to all tables, but cannot see changes that were committed by other transactions after the transaction was started.                                                                                                                                                                                                                                                             |
| IBASE\_COMMITTED   | Starts a transaction with the isolation level set to 'read committed'. This flag should be combined with either **`IBASE_REC_VERSION`** or **`IBASE_REC_NO_VERSION`**. This isolation level allows access to changes that were committed after the transaction was started. If **`IBASE_REC_NO_VERSION`** was specified, only the latest version of a row can be read. If **`IBASE_REC_VERSION`** was specified, a row can even be read when a modification to it is pending in a concurrent transaction. |
| IBASE\_WAIT        | Indicated that a transaction should wait and retry when a conflict occurs.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| IBASE\_NOWAIT      | Indicated that a transaction should fail immediately when a conflict occurs.                                                                                                                                                                                                                                                                                                                                                                                                                              |

The following constants can be passed to <span
class="function">ibase\_fetch\_row</span>, <span
class="function">ibase\_fetch\_assoc</span> or <span
class="function">ibase\_fetch\_object</span> to specify fetch behaviour.

| Constant             | Description                                                                                                                                                                                                                   |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| IBASE\_FETCH\_BLOBS  | Also available as **`IBASE_TEXT`**for backward compatibility. Causes BLOB contents to be fetched inline, instead of being fetched as BLOB identifiers.                                                                        |
| IBASE\_FETCH\_ARRAYS | Causes arrays to be fetched inline. Otherwise, array identifiers are returned. Array identifiers can only be used as arguments to INSERT operations, as no functions to handle array identifiers are currently available.     |
| IBASE\_UNIXTIME      | Causes date and time fields not to be returned as strings, but as UNIX timestamps (the number of seconds since the epoch, which is 1-Jan-1970 0:00 UTC). Might be problematic if used with dates before 1970 on some systems. |

The following constants are used to pass requests and options to the
service API functions (<span
class="function">ibase\_server\_info</span>, <span
class="function">ibase\_db\_info</span>, <span
class="function">ibase\_backup</span>, <span
class="function">ibase\_restore</span> and <span
class="function">ibase\_maintain\_db</span>). Please refer to the
Firebird/InterBase manuals for the meaning of these options.

**`IBASE_BKP_IGNORE_CHECKSUMS`**  
<span class="simpara"> Options to <span
class="function">ibase\_backup</span> </span>

**`IBASE_BKP_IGNORE_LIMBO`**  
<span class="simpara"> Options to <span
class="function">ibase\_backup</span> </span>

**`IBASE_BKP_METADATA_ONLY`**  
<span class="simpara"> Options to <span
class="function">ibase\_backup</span> </span>

**`IBASE_BKP_NO_GARBAGE_COLLECT`**  
<span class="simpara"> Options to <span
class="function">ibase\_backup</span> </span>

**`IBASE_BKP_OLD_DESCRIPTIONS`**  
<span class="simpara"> Options to <span
class="function">ibase\_backup</span> </span>

**`IBASE_BKP_NON_TRANSPORTABLE`**  
<span class="simpara"> Options to <span
class="function">ibase\_backup</span> </span>

**`IBASE_BKP_CONVERT`**  
<span class="simpara"> Options to <span
class="function">ibase\_backup</span> </span>

**`IBASE_RES_DEACTIVATE_IDX`**  
<span class="simpara"> Options to <span
class="function">ibase\_restore</span> </span>

**`IBASE_RES_NO_SHADOW`**  
<span class="simpara"> Options to <span
class="function">ibase\_restore</span> </span>

**`IBASE_RES_NO_VALIDITY`**  
<span class="simpara"> Options to <span
class="function">ibase\_restore</span> </span>

**`IBASE_RES_ONE_AT_A_TIME`**  
<span class="simpara"> Options to <span
class="function">ibase\_restore</span> </span>

**`IBASE_RES_REPLACE`**  
<span class="simpara"> </span>

**`IBASE_RES_CREATE`**  
<span class="simpara"> Options to <span
class="function">ibase\_restore</span> </span>

**`IBASE_RES_USE_ALL_SPACE`**  
<span class="simpara"> Options to <span
class="function">ibase\_restore</span> </span>

**`IBASE_PRP_PAGE_BUFFERS`**  
<span class="simpara"> </span>

**`IBASE_PRP_SWEEP_INTERVAL`**  
<span class="simpara"> </span>

**`IBASE_PRP_SHUTDOWN_DB`**  
<span class="simpara"> </span>

**`IBASE_PRP_DENY_NEW_TRANSACTIONS`**  
<span class="simpara"> </span>

**`IBASE_PRP_DENY_NEW_ATTACHMENTS`**  
<span class="simpara"> </span>

**`IBASE_PRP_RESERVE_SPACE`**  
<span class="simpara"> </span>

**`IBASE_PRP_RES_USE_FULL`**  
<span class="simpara"> </span>

**`IBASE_PRP_RES`**  
<span class="simpara"> </span>

**`IBASE_PRP_WRITE_MODE`**  
<span class="simpara"> </span>

**`IBASE_PRP_WM_ASYNC`**  
<span class="simpara"> </span>

**`IBASE_PRP_WM_SYNC`**  
<span class="simpara"> </span>

**`IBASE_PRP_ACCESS_MODE`**  
<span class="simpara"> </span>

**`IBASE_PRP_AM_READONLY`**  
<span class="simpara"> </span>

**`IBASE_PRP_AM_READWRITE`**  
<span class="simpara"> </span>

**`IBASE_PRP_SET_SQL_DIALECT`**  
<span class="simpara"> </span>

**`IBASE_PRP_ACTIVATE`**  
<span class="simpara"> </span>

**`IBASE_PRP_DB_ONLINE`**  
<span class="simpara"> </span>

**`IBASE_RPR_CHECK_DB`**  
<span class="simpara"> </span>

**`IBASE_RPR_IGNORE_CHECKSUM`**  
<span class="simpara"> </span>

**`IBASE_RPR_KILL_SHADOWS`**  
<span class="simpara"> </span>

**`IBASE_RPR_MEND_DB`**  
<span class="simpara"> </span>

**`IBASE_RPR_VALIDATE_DB`**  
<span class="simpara"> </span>

**`IBASE_RPR_FULL`**  
<span class="simpara"> </span>

**`IBASE_RPR_SWEEP_DB`**  
<span class="simpara"> Options to <span
class="function">ibase\_maintain\_db</span> </span>

**`IBASE_STS_DATA_PAGES`**  
<span class="simpara"> </span>

**`IBASE_STS_DB_LOG`**  
<span class="simpara"> </span>

**`IBASE_STS_HDR_PAGES`**  
<span class="simpara"> </span>

**`IBASE_STS_IDX_PAGES`**  
<span class="simpara"> </span>

**`IBASE_STS_SYS_RELATIONS`**  
<span class="simpara"> Options to <span
class="function">ibase\_db\_info</span> </span>

**`IBASE_SVC_SERVER_VERSION`**  
<span class="simpara"> Options to <span
class="function">ibase\_server\_info</span> </span>

**`IBASE_SVC_IMPLEMENTATION`**  
<span class="simpara"> Options to <span
class="function">ibase\_server\_info</span> </span>

**`IBASE_SVC_GET_ENV`**  
<span class="simpara"> Options to <span
class="function">ibase\_server\_info</span> </span>

**`IBASE_SVC_GET_ENV_LOCK`**  
<span class="simpara"> </span>

**`IBASE_SVC_GET_ENV_MSG`**  
<span class="simpara"> </span>

**`IBASE_SVC_USER_DBPATH`**  
<span class="simpara"> </span>

**`IBASE_SVC_SVR_DB_INFO`**  
<span class="simpara"> </span>

**`IBASE_SVC_GET_USERS`**  
<span class="simpara"> Options to <span
class="function">ibase\_server\_info</span> </span>

fbird\_add\_user
================

Alias of <span class="function">ibase\_add\_user</span>

### Description

This function is an alias of: <span
class="function">ibase\_add\_user</span>.

### See Also

-   <span class="function">fbird\_modify\_user</span>
-   <span class="function">fbird\_delete\_user</span>

fbird\_affected\_rows
=====================

Alias of <span class="function">ibase\_affected\_rows</span>

### Description

This function is an alias of: <span
class="function">ibase\_affected\_rows</span>.

### See Also

-   <span class="function">fbird\_query</span>
-   <span class="function">fbird\_execute</span>

fbird\_backup
=============

Alias of <span class="function">ibase\_backup</span>

### Description

This function is an alias of: <span
class="function">ibase\_backup</span>.

fbird\_blob\_add
================

Alias of <span class="function">ibase\_blob\_add</span>

### Description

This function is an alias of: <span
class="function">ibase\_blob\_add</span>.

### See Also

-   <span class="function">fbird\_blob\_cancel</span>
-   <span class="function">fbird\_blob\_close</span>
-   <span class="function">fbird\_blob\_create</span>
-   <span class="function">fbird\_blob\_import</span>

fbird\_blob\_cancel
===================

Cancel creating blob

### Description

<span class="type">bool</span> <span
class="methodname">fbird\_blob\_cancel</span> ( <span
class="methodparam"><span class="type">resource</span>
`$blob_handle`</span> )

This function will discard a BLOB if it has not yet been closed by <span
class="function">fbird\_blob\_close</span>.

### Parameters

`blob_handle`  
A BLOB handle opened with <span
class="function">fbird\_blob\_create</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">fbird\_blob\_close</span>
-   <span class="function">fbird\_blob\_create</span>
-   <span class="function">fbird\_blob\_import</span>

fbird\_blob\_close
==================

Alias of <span class="function">ibase\_blob\_close</span>

### Description

This function is an alias of: <span
class="function">ibase\_blob\_close</span>.

### See Also

-   <span class="function">fbird\_blob\_create</span>
-   <span class="function">fbird\_blob\_cancel</span>
-   <span class="function">fbird\_blob\_open</span>
-   <span class="function">fbird\_blob\_import</span>

fbird\_blob\_create
===================

Alias of <span class="function">ibase\_blob\_create</span>

### Description

This function is an alias of: <span
class="function">ibase\_blob\_create</span>.

### See Also

-   <span class="function">fbird\_blob\_add</span>
-   <span class="function">fbird\_blob\_cancel</span>
-   <span class="function">fbird\_blob\_close</span>
-   <span class="function">fbird\_blob\_import</span>

fbird\_blob\_echo
=================

Alias of <span class="function">ibase\_blob\_echo</span>

### Description

This function is an alias of: <span
class="function">ibase\_blob\_echo</span>.

### See Also

-   <span class="function">fbird\_blob\_open</span>
-   <span class="function">fbird\_blob\_close</span>
-   <span class="function">fbird\_blob\_get</span>

fbird\_blob\_get
================

Alias of <span class="function">ibase\_blob\_get</span>

### Description

This function is an alias of: <span
class="function">ibase\_blob\_get</span>.

### See Also

-   <span class="function">fbird\_blob\_open</span>
-   <span class="function">fbird\_blob\_close</span>
-   <span class="function">fbird\_blob\_echo</span>

fbird\_blob\_import
===================

Alias of <span class="function">ibase\_blob\_import</span>

### Description

This function is an alias of: <span
class="function">ibase\_blob\_import</span>.

### See Also

-   <span class="function">fbird\_blob\_add</span>
-   <span class="function">fbird\_blob\_cancel</span>
-   <span class="function">fbird\_blob\_close</span>
-   <span class="function">fbird\_blob\_create</span>

fbird\_blob\_info
=================

Alias of <span class="function">ibase\_blob\_info</span>

### Description

This function is an alias of: <span
class="function">ibase\_blob\_info</span>.

fbird\_blob\_open
=================

Alias of <span class="function">ibase\_blob\_open</span>

### Description

This function is an alias of: <span
class="function">ibase\_blob\_open</span>.

### See Also

-   <span class="function">fbird\_blob\_close</span>
-   <span class="function">fbird\_blob\_echo</span>
-   <span class="function">fbird\_blob\_get</span>

fbird\_close
============

Alias of <span class="function">ibase\_close</span>

### Description

This function is an alias of: <span
class="function">ibase\_close</span>.

### See Also

-   <span class="function">fbird\_connect</span>
-   <span class="function">fbird\_pconnect</span>

fbird\_commit\_ret
==================

Alias of <span class="function">ibase\_commit\_ret</span>

### Description

This function is an alias of: <span
class="function">ibase\_commit\_ret</span>.

fbird\_commit
=============

Alias of <span class="function">ibase\_commit</span>

### Description

This function is an alias of: <span
class="function">ibase\_commit</span>.

fbird\_connect
==============

Alias of <span class="function">ibase\_connect</span>

### Description

This function is an alias of: <span
class="function">ibase\_connect</span>.

### See Also

-   <span class="function">fbird\_pconnect</span>
-   <span class="function">fbird\_close</span>

fbird\_db\_info
===============

Alias of <span class="function">ibase\_db\_info</span>

### Description

This function is an alias of: <span
class="function">ibase\_db\_info</span>.

fbird\_delete\_user
===================

Alias of <span class="function">ibase\_delete\_user</span>

### Description

This function is an alias of: <span
class="function">ibase\_delete\_user</span>.

### See Also

-   <span class="function">fbird\_add\_user</span>
-   <span class="function">fbird\_modify\_user</span>

fbird\_drop\_db
===============

Alias of <span class="function">ibase\_drop\_db</span>

### Description

This function is an alias of: <span
class="function">ibase\_drop\_db</span>.

### See Also

-   <span class="function">fbird\_connect</span>
-   <span class="function">fbird\_pconnect</span>

fbird\_errcode
==============

Alias of <span class="function">ibase\_errcode</span>

### Description

This function is an alias of: <span
class="function">ibase\_errcode</span>.

### See Also

-   <span class="function">fbird\_errmsg</span>

fbird\_errmsg
=============

Alias of <span class="function">ibase\_errmsg</span>

### Description

This function is an alias of: <span
class="function">ibase\_errmsg</span>.

### See Also

-   <span class="function">fbird\_errcode</span>

fbird\_execute
==============

Alias of <span class="function">ibase\_execute</span>

### Description

This function is an alias of: <span
class="function">ibase\_execute</span>.

### See Also

-   <span class="function">fbird\_query</span>

fbird\_fetch\_assoc
===================

Alias of <span class="function">ibase\_fetch\_assoc</span>

### Description

This function is an alias of: <span
class="function">ibase\_fetch\_assoc</span>.

### See Also

-   <span class="function">fbird\_fetch\_row</span>
-   <span class="function">fbird\_fetch\_object</span>

fbird\_fetch\_object
====================

Alias of <span class="function">ibase\_fetch\_object</span>

### Description

This function is an alias of: <span
class="function">ibase\_fetch\_object</span>.

### See Also

-   <span class="function">fbird\_fetch\_row</span>
-   <span class="function">fbird\_fetch\_assoc</span>

fbird\_fetch\_row
=================

Alias of <span class="function">ibase\_fetch\_row</span>

### Description

This function is an alias of: <span
class="function">ibase\_fetch\_row</span>.

### See Also

-   <span class="function">fbird\_fetch\_assoc</span>
-   <span class="function">fbird\_fetch\_object</span>

fbird\_field\_info
==================

Alias of <span class="function">ibase\_field\_info</span>

### Description

This function is an alias of: <span
class="function">ibase\_field\_info</span>.

### See Also

-   <span class="function">fbird\_num\_fields</span>

fbird\_free\_event\_handler
===========================

Alias of <span class="function">ibase\_free\_event\_handler</span>

### Description

This function is an alias of: <span
class="function">ibase\_free\_event\_handler</span>.

### See Also

-   <span class="function">fbird\_set\_event\_handler</span>

fbird\_free\_query
==================

Alias of <span class="function">ibase\_free\_query</span>

### Description

This function is an alias of: <span
class="function">ibase\_free\_query</span>.

fbird\_free\_result
===================

Alias of <span class="function">ibase\_free\_result</span>

### Description

This function is an alias of: <span
class="function">ibase\_free\_result</span>.

fbird\_gen\_id
==============

Alias of <span class="function">ibase\_gen\_id</span>

### Description

This function is an alias of: <span
class="function">ibase\_gen\_id</span>.

fbird\_maintain\_db
===================

Alias of <span class="function">ibase\_maintain\_db</span>

### Description

This function is an alias of: <span
class="function">ibase\_maintain\_db</span>.

fbird\_modify\_user
===================

Alias of <span class="function">ibase\_modify\_user</span>

### Description

This function is an alias of: <span
class="function">ibase\_modify\_user</span>.

### See Also

-   <span class="function">fbird\_add\_user</span>
-   <span class="function">fbird\_delete\_user</span>

fbird\_name\_result
===================

Alias of <span class="function">ibase\_name\_result</span>

### Description

This function is an alias of: <span
class="function">ibase\_name\_result</span>.

### See Also

-   <span class="function">fbird\_prepare</span>
-   <span class="function">fbird\_execute</span>

fbird\_num\_fields
==================

Alias of <span class="function">ibase\_num\_fields</span>

### Description

This function is an alias of: <span
class="function">ibase\_num\_fields</span>.

### See Also

-   <span class="function">fbird\_field\_info</span>

fbird\_num\_params
==================

Alias of <span class="function">ibase\_num\_params</span>

### Description

This function is an alias of: <span
class="function">ibase\_num\_params</span>.

### See Also

-   <span class="function">fbird\_prepare</span>
-   <span class="function">fbird\_param\_info</span>

fbird\_param\_info
==================

Alias of <span class="function">ibase\_param\_info</span>

### Description

This function is an alias of: <span
class="function">ibase\_param\_info</span>.

### See Also

-   <span class="function">fbird\_field\_info</span>
-   <span class="function">fbird\_num\_params</span>

fbird\_pconnect
===============

Alias of <span class="function">ibase\_pconnect</span>

### Description

This function is an alias of: <span
class="function">ibase\_pconnect</span>.

### See Also

-   <span class="function">fbird\_close</span>
-   <span class="function">fbird\_connect</span>

fbird\_prepare
==============

Alias of <span class="function">ibase\_prepare</span>

### Description

This function is an alias of: <span
class="function">ibase\_prepare</span>.

fbird\_query
============

Alias of <span class="function">ibase\_query</span>

### Description

This function is an alias of: <span
class="function">ibase\_query</span>.

### See Also

-   <span class="function">fbird\_errmsg</span>
-   <span class="function">fbird\_fetch\_row</span>
-   <span class="function">fbird\_fetch\_object</span>
-   <span class="function">fbird\_free\_result</span>

fbird\_restore
==============

Alias of <span class="function">ibase\_restore</span>

### Description

This function is an alias of: <span
class="function">ibase\_restore</span>.

fbird\_rollback\_ret
====================

Alias of <span class="function">ibase\_rollback\_ret</span>

### Description

This function is an alias of: <span
class="function">ibase\_rollback\_ret</span>.

fbird\_rollback
===============

Alias of <span class="function">ibase\_rollback</span>

### Description

This function is an alias of: <span
class="function">ibase\_rollback</span>.

fbird\_server\_info
===================

Alias of <span class="function">ibase\_server\_info</span>

### Description

This function is an alias of: <span
class="function">ibase\_server\_info</span>.

fbird\_service\_attach
======================

Alias of <span class="function">ibase\_service\_attach</span>

### Description

This function is an alias of: <span
class="function">ibase\_service\_attach</span>.

fbird\_service\_detach
======================

Alias of <span class="function">ibase\_service\_detach</span>

### Description

This function is an alias of: <span
class="function">ibase\_service\_detach</span>.

fbird\_set\_event\_handler
==========================

Alias of <span class="function">ibase\_set\_event\_handler</span>

### Description

This function is an alias of: <span
class="function">ibase\_set\_event\_handler</span>.

### See Also

-   <span class="function">fbird\_free\_event\_handler</span>
-   <span class="function">fbird\_wait\_event</span>

fbird\_trans
============

Alias of <span class="function">ibase\_trans</span>

### Description

This function is an alias of: <span
class="function">ibase\_trans</span>.

fbird\_wait\_event
==================

Alias of <span class="function">ibase\_wait\_event</span>

### Description

This function is an alias of: <span
class="function">ibase\_wait\_event</span>.

### See Also

-   <span class="function">fbird\_set\_event\_handler</span>
-   <span class="function">fbird\_free\_event\_handler</span>

ibase\_add\_user
================

Add a user to a security database

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_add\_user</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> , <span class="methodparam"><span
class="type">string</span> `$user_name`</span> , <span
class="methodparam"><span class="type">string</span> `$password`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$first_name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$middle_name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$last_name`</span>
\]\]\] )

### Parameters

`service_handle`  
The handle on the database server service.

`user_name`  
The login name of the new database user.

`password`  
The password of the new user.

`first_name`  
The first name of the new database user.

`middle_name`  
The middle name of the new database user.

`last_name`  
The last name of the new database user.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ibase\_modify\_user</span>
-   <span class="function">ibase\_delete\_user</span>

ibase\_affected\_rows
=====================

Return the number of rows that were affected by the previous query

### Description

<span class="type">int</span> <span
class="methodname">ibase\_affected\_rows</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> \] )

This function returns the number of rows that were affected by the
previous query (INSERT, UPDATE or DELETE) that was executed from within
the specified transaction context.

### Parameters

`link_identifier`  
A transaction context. If `link_identifier` is a connection resource,
its default transaction is used.

### Return Values

Returns the number of rows as an integer.

### See Also

-   <span class="function">ibase\_query</span>
-   <span class="function">ibase\_execute</span>

ibase\_backup
=============

Initiates a backup task in the service manager and returns immediately

### Description

<span class="type">mixed</span> <span
class="methodname">ibase\_backup</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> , <span class="methodparam"><span
class="type">string</span> `$source_db`</span> , <span
class="methodparam"><span class="type">string</span> `$dest_file`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$verbose`<span
class="initializer"> = **`false`**</span></span> \]\] )

This function passes the arguments to the (remote) database server.
There it starts a new backup process. Therefore you won't get any
responses.

### Parameters

`service_handle`  
A previously opened connection to the database server.

`source_db`  
The absolute file path to the database on the database server. You can
also use a database alias.

`dest_file`  
The path to the backup file on the database server.

`options`  
Additional options to pass to the database server for backup. The
`options` parameter can be a combination of the following constants:
**`IBASE_BKP_IGNORE_CHECKSUMS`**, **`IBASE_BKP_IGNORE_LIMBO`**,
**`IBASE_BKP_METADATA_ONLY`**, **`IBASE_BKP_NO_GARBAGE_COLLECT`**,
**`IBASE_BKP_OLD_DESCRIPTIONS`**, **`IBASE_BKP_NON_TRANSPORTABLE`** or
**`IBASE_BKP_CONVERT`**. Read the section about
<a href="/book/ibase.html#Predefined%20Constants" class="xref"></a> for
further information.

`verbose`  
Since the backup process is done on the database server, you don't have
any chance to get its output. This argument is useless.

### Return Values

Returns **`true`** on success or **`false`** on failure.

Since the backup process is done on the (remote) server, this function
just passes the arguments to it. While the arguments are legal, you
won't get **`false`**.

### Examples

**Example \#1 <span class="function">ibase\_backup</span> example**

``` php
<?php

// Attach to database server by ip address and port
$service = ibase_service_attach ('10.1.11.200/3050', 'sysdba', 'masterkey');

// Start the backup process on database server
// Backup employee database using full path to /srv/backup/employees.fbk
// Don't use any special arguments
ibase_backup($service, '/srv/firebird/employees.fdb', '/srv/backup/employees.fbk');

// Free the attached connection
ibase_service_detach ($service);
?>
```

**Example \#2 <span class="function">ibase\_backup</span> example with
arguments**

``` php
<?php

// Attach to database server by name and default port
$service = ibase_service_attach ('fb-server.contoso.local', 'sysdba', 'masterkey');

// Start the backup process on database server
// Backup employee database using alias to /srv/backup/employees.fbk.
// Backup only the metadata. Don't create a transportable backup.
ibase_backup($service, 'employees.fdb', '/srv/backup/employees.fbk', IBASE_BKP_METADATA_ONLY | IBASE_BKP_NON_TRANSPORTABLE);

// Free the attached connection
ibase_service_detach ($service);
?>
```

### See Also

-   <span class="function">ibase\_restore</span>

ibase\_blob\_add
================

Add data into a newly created blob

### Description

<span class="type">void</span> <span
class="methodname">ibase\_blob\_add</span> ( <span
class="methodparam"><span class="type">resource</span>
`$blob_handle`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> )

<span class="function">ibase\_blob\_add</span> adds data into a blob
created with <span class="function">ibase\_blob\_create</span>.

### Parameters

`blob_handle`  
A blob handle opened with <span
class="function">ibase\_blob\_create</span>.

`data`  
The data to be added.

### Return Values

No value is returned.

### See Also

-   <span class="function">ibase\_blob\_cancel</span>
-   <span class="function">ibase\_blob\_close</span>
-   <span class="function">ibase\_blob\_create</span>
-   <span class="function">ibase\_blob\_import</span>

ibase\_blob\_cancel
===================

Cancel creating blob

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_blob\_cancel</span> ( <span
class="methodparam"><span class="type">resource</span>
`$blob_handle`</span> )

This function will discard a BLOB if it has not yet been closed by <span
class="function">ibase\_blob\_close</span>.

### Parameters

`blob_handle`  
A BLOB handle opened with <span
class="function">ibase\_blob\_create</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ibase\_blob\_close</span>
-   <span class="function">ibase\_blob\_create</span>
-   <span class="function">ibase\_blob\_import</span>

ibase\_blob\_close
==================

Close blob

### Description

<span class="type">mixed</span> <span
class="methodname">ibase\_blob\_close</span> ( <span
class="methodparam"><span class="type">resource</span>
`$blob_handle`</span> )

This function closes a BLOB that has either been opened for reading by
<span class="function">ibase\_blob\_open</span> or has been opened for
writing by <span class="function">ibase\_blob\_create</span>.

### Parameters

`blob_handle`  
A BLOB handle opened with <span
class="function">ibase\_blob\_create</span> or <span
class="function">ibase\_blob\_open</span>.

### Return Values

If the BLOB was being read, this function returns **`true`** on success,
if the BLOB was being written to, this function returns a string
containing the BLOB id that has been assigned to it by the database. On
failure, this function returns **`false`**.

### See Also

-   <span class="function">ibase\_blob\_cancel</span>
-   <span class="function">ibase\_blob\_open</span>

ibase\_blob\_create
===================

Create a new blob for adding data

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">ibase\_blob\_create</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`<span class="initializer"> = **`null`**</span></span>
\] )

<span class="function">ibase\_blob\_create</span> creates a new BLOB for
filling with data.

### Parameters

`link_identifier`  
An InterBase link identifier. If omitted, the last opened link is
assumed.

### Return Values

Returns a BLOB handle for later use with <span
class="function">ibase\_blob\_add</span> or **`false`** on failure.

### See Also

-   <span class="function">ibase\_blob\_add</span>
-   <span class="function">ibase\_blob\_cancel</span>
-   <span class="function">ibase\_blob\_close</span>
-   <span class="function">ibase\_blob\_import</span>

ibase\_blob\_echo
=================

Output blob contents to browser

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_blob\_echo</span> ( <span
class="methodparam"><span class="type">string</span> `$blob_id`</span> )

<span class="type">bool</span> <span
class="methodname">ibase\_blob\_echo</span> ( <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$blob_id`</span> )

This function opens a BLOB for reading and sends its contents directly
to standard output (the browser, in most cases).

### Parameters

`link_identifier`  
An InterBase link identifier. If omitted, the last opened link is
assumed.

`blob_id`  

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ibase\_blob\_open</span>
-   <span class="function">ibase\_blob\_close</span>
-   <span class="function">ibase\_blob\_get</span>

ibase\_blob\_get
================

Get len bytes data from open blob

### Description

<span class="type">string</span> <span
class="methodname">ibase\_blob\_get</span> ( <span
class="methodparam"><span class="type">resource</span>
`$blob_handle`</span> , <span class="methodparam"><span
class="type">int</span> `$len`</span> )

This function returns at most `len` bytes from a BLOB that has been
opened for reading by <span class="function">ibase\_blob\_open</span>.

> **Note**:
>
> It is not possible to read from a BLOB that has been opened for
> writing by <span class="function">ibase\_blob\_create</span>.

### Parameters

`blob_handle`  
A BLOB handle opened with <span
class="function">ibase\_blob\_open</span>.

`len`  
Size of returned data.

### Return Values

Returns at most `len` bytes from the BLOB, or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ibase\_blob\_get</span> example**

``` php
<?php
$result    = ibase_query("SELECT blob_value FROM table");
$data      = ibase_fetch_object($result);
$blob_data = ibase_blob_info($data->BLOB_VALUE);
$blob_hndl = ibase_blob_open($data->BLOB_VALUE);
echo         ibase_blob_get($blob_hndl, $blob_data[0]);
?>
```

Whilst this example doesn't do much more than a
'ibase\_blob\_echo($data-\>BLOB\_VALUE)' would do, it does show you how
to get information into a $variable to manipulate as you please.

### See Also

-   <span class="function">ibase\_blob\_open</span>
-   <span class="function">ibase\_blob\_close</span>
-   <span class="function">ibase\_blob\_echo</span>

ibase\_blob\_import
===================

Create blob, copy file in it, and close it

### Description

<span class="type">string</span> <span
class="methodname">ibase\_blob\_import</span> ( <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> , <span class="methodparam"><span
class="type">resource</span> `$file_handle`</span> )

<span class="type">string</span> <span
class="methodname">ibase\_blob\_import</span> ( <span
class="methodparam"><span class="type">resource</span>
`$file_handle`</span> )

This function creates a BLOB, reads an entire file into it, closes it
and returns the assigned BLOB id.

### Parameters

`link_identifier`  
An InterBase link identifier. If omitted, the last opened link is
assumed.

`file_handle`  
The file handle is a handle returned by <span
class="function">fopen</span>.

### Return Values

Returns the BLOB id on success, or **`false`** on error.

### Examples

**Example \#1 <span class="function">ibase\_blob\_import</span>
example**

``` php
<?php
$dbh = ibase_connect($host, $username, $password);
$filename = '/tmp/bar';

$fd = fopen($filename, 'r');
if ($fd) {

    $blob = ibase_blob_import($dbh, $fd);
    fclose($fd);

    if (!is_string($blob)) {
        // import failed
    } else {
        $query = "INSERT INTO foo (name, data) VALUES ('$filename', ?)";
        $prepared = ibase_prepare($dbh, $query);
        if (!ibase_execute($prepared, $blob)) {
            // record insertion failed
        }
    }
} else {
    // unable to open the data file
}
?>
```

### See Also

-   <span class="function">ibase\_blob\_add</span>
-   <span class="function">ibase\_blob\_cancel</span>
-   <span class="function">ibase\_blob\_close</span>
-   <span class="function">ibase\_blob\_create</span>

ibase\_blob\_info
=================

Return blob length and other useful info

### Description

<span class="type">array</span> <span
class="methodname">ibase\_blob\_info</span> ( <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$blob_id`</span> )

<span class="type">array</span> <span
class="methodname">ibase\_blob\_info</span> ( <span
class="methodparam"><span class="type">string</span> `$blob_id`</span> )

Returns the BLOB length and other useful information.

### Parameters

`link_identifier`  
An InterBase link identifier. If omitted, the last opened link is
assumed.

`blob_id`  
A BLOB id.

### Return Values

Returns an array containing information about a BLOB. The information
returned consists of the length of the BLOB, the number of segments it
contains, the size of the largest segment, and whether it is a stream
BLOB or a segmented BLOB.

ibase\_blob\_open
=================

Open blob for retrieving data parts

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">ibase\_blob\_open</span> ( <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$blob_id`</span> )

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">ibase\_blob\_open</span> ( <span
class="methodparam"><span class="type">string</span> `$blob_id`</span> )

Opens an existing BLOB for reading.

### Parameters

`link_identifier`  
An InterBase link identifier. If omitted, the last opened link is
assumed.

`blob_id`  
A BLOB id.

### Return Values

Returns a BLOB handle for later use with <span
class="function">ibase\_blob\_get</span> or **`false`** on failure.

### See Also

-   <span class="function">ibase\_blob\_close</span>
-   <span class="function">ibase\_blob\_echo</span>
-   <span class="function">ibase\_blob\_get</span>

ibase\_close
============

Close a connection to an InterBase database

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_close</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection_id`<span class="initializer"> = **`null`**</span></span> \]
)

Closes the link to an InterBase database that's associated with a
connection id returned from <span
class="function">ibase\_connect</span>. Default transaction on link is
committed, other transactions are rolled back.

### Parameters

`connection_id`  
An InterBase link identifier returned from <span
class="function">ibase\_connect</span>. If omitted, the last opened link
is assumed.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ibase\_connect</span>
-   <span class="function">ibase\_pconnect</span>

ibase\_commit\_ret
==================

Commit a transaction without closing it

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_commit\_ret</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$link_or_trans_identifier`<span class="initializer"> =
**`null`**</span></span> \] )

Commits a transaction without closing it.

### Parameters

`link_or_trans_identifier`  
If called without an argument, this function commits the default
transaction of the default link. If the argument is a connection
identifier, the default transaction of the corresponding connection will
be committed. If the argument is a transaction identifier, the
corresponding transaction will be committed. The transaction context
will be retained, so statements executed from within this transaction
will not be invalidated.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ibase\_commit
=============

Commit a transaction

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_commit</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$link_or_trans_identifier`<span class="initializer"> =
**`null`**</span></span> \] )

Commits a transaction.

### Parameters

`link_or_trans_identifier`  
If called without an argument, this function commits the default
transaction of the default link. If the argument is a connection
identifier, the default transaction of the corresponding connection will
be committed. If the argument is a transaction identifier, the
corresponding transaction will be committed.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ibase\_connect
==============

Open a connection to a database

### Description

<span class="type">resource</span> <span
class="methodname">ibase\_connect</span> (\[ <span
class="methodparam"><span class="type">string</span> `$database`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$username`</span> \[, <span class="methodparam"><span
class="type">string</span> `$password`</span> \[, <span
class="methodparam"><span class="type">string</span> `$charset`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$buffers`</span> \[, <span class="methodparam"><span
class="type">int</span> `$dialect`</span> \[, <span
class="methodparam"><span class="type">string</span> `$role`</span> \[,
<span class="methodparam"><span class="type">int</span> `$sync`</span>
\]\]\]\]\]\]\]\] )

Establishes a connection to an Firebird/InterBase server.

In case a second call is made to <span
class="function">ibase\_connect</span> with the same arguments, no new
link will be established, but instead, the link identifier of the
already opened link will be returned. The link to the server will be
closed as soon as the execution of the script ends, unless it's closed
earlier by explicitly calling <span
class="function">ibase\_close</span>.

### Parameters

`database`  
The `database` argument has to be a valid path to database file on the
server it resides on. If the server is not local, it must be prefixed
with either 'hostname:' (TCP/IP), 'hostname/port:' (TCP/IP with
interbase server on custom TCP port), '//hostname/' (NetBEUI), depending
on the connection protocol used.

`username`  
The user name. Can be set with the *ibase.default\_user* `php.ini`
directive.

`password`  
The password for `username`. Can be set with the
*ibase.default\_password* `php.ini` directive.

`charset`  
`charset` is the default character set for a database.

`buffers`  
`buffers` is the number of database buffers to allocate for the
server-side cache. If 0 or omitted, server chooses its own default.

`dialect`  
`dialect` selects the default SQL dialect for any statement executed
within a connection, and it defaults to the highest one supported by
client libraries.

`role`  
Functional only with InterBase 5 and up.

`sync`  

### Return Values

Returns an Firebird/InterBase link identifier on success, or **`false`**
on error.

### Errors/Exceptions

If you get some error like "arithmetic exception, numeric overflow, or
string truncation. Cannot transliterate character between character
sets" (this occurs when you try use some character with accents) when
using this and after <span class="function">ibase\_query</span> you must
set the character set (i.e. ISO8859\_1 or your current character set).

### Examples

**Example \#1 <span class="function">ibase\_connect</span> example**

``` php
<?php
$host = 'localhost:/path/to/your.gdb';

$dbh = ibase_connect($host, $username, $password);
$stmt = 'SELECT * FROM tblname';
$sth = ibase_query($dbh, $stmt);
while ($row = ibase_fetch_object($sth)) {
    echo $row->email, "\n";
}
ibase_free_result($sth);
ibase_close($dbh);
?>
```

### See Also

-   <span class="function">ibase\_pconnect</span>
-   <span class="function">ibase\_close</span>

ibase\_db\_info
===============

Request statistics about a database

### Description

<span class="type">string</span> <span
class="methodname">ibase\_db\_info</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> , <span class="methodparam"><span
class="type">string</span> `$db`</span> , <span
class="methodparam"><span class="type">int</span> `$action`</span> \[,
<span class="methodparam"><span class="type">int</span> `$argument`<span
class="initializer"> = 0</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

ibase\_delete\_user
===================

Delete a user from a security database

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_delete\_user</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> , <span class="methodparam"><span
class="type">string</span> `$user_name`</span> )

### Parameters

`service_handle`  
The handle on the database server service.

`user_name`  
The login name of the user you want to delete from the database.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ibase\_add\_user</span>
-   <span class="function">ibase\_modify\_user</span>

ibase\_drop\_db
===============

Drops a database

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_drop\_db</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`<span class="initializer"> = **`null`**</span></span> \] )

This functions drops a database that was opened by either <span
class="function">ibase\_connect</span> or <span
class="function">ibase\_pconnect</span>. The database is closed and
deleted from the server.

### Parameters

`connection`  
An InterBase link identifier. If omitted, the last opened link is
assumed.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ibase\_connect</span>
-   <span class="function">ibase\_pconnect</span>

ibase\_errcode
==============

Return an error code

### Description

<span class="type">int</span> <span
class="methodname">ibase\_errcode</span> ( <span
class="methodparam">void</span> )

Returns the error code that resulted from the most recent InterBase
function call.

### Return Values

Returns the error code as an integer, or **`false`** if no error
occurred.

### See Also

-   <span class="function">ibase\_errmsg</span>

ibase\_errmsg
=============

Return error messages

### Description

<span class="type">string</span> <span
class="methodname">ibase\_errmsg</span> ( <span
class="methodparam">void</span> )

Returns the error message that resulted from the most recent InterBase
function call.

### Return Values

Returns the error message as a string, or **`false`** if no error
occurred.

### See Also

-   <span class="function">ibase\_errcode</span>

ibase\_execute
==============

Execute a previously prepared query

### Description

<span class="type">resource</span> <span
class="methodname">ibase\_execute</span> ( <span
class="methodparam"><span class="type">resource</span> `$query`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$values`</span> )

Execute a query prepared by <span
class="function">ibase\_prepare</span>.

This is a lot more effective than using <span
class="function">ibase\_query</span> if you are repeating a same kind of
query several times with only some parameters changing.

### Parameters

`query`  
An InterBase query prepared by <span
class="function">ibase\_prepare</span>.

`values`  

### Return Values

If the query raises an error, returns **`false`**. If it is successful
and there is a (possibly empty) result set (such as with a SELECT
query), returns a result identifier. If the query was successful and
there were no results, returns **`true`**.

> **Note**:
>
> This function returns the number of rows affected by the query (if \>
> 0 and applicable to the statement type). A query that succeeded, but
> did not affect any rows (e.g. an UPDATE of a non-existent record) will
> return **`true`**.

### Examples

**Example \#1 <span class="function">ibase\_execute</span> example**

``` php
<?php

$dbh = ibase_connect($host, $username, $password);

$updates = array(
    1 => 'Eric',
    5 => 'Filip',
    7 => 'Larry'
);

$query = ibase_prepare($dbh, "UPDATE FOO SET BAR = ? WHERE BAZ = ?");

foreach ($updates as $baz => $bar) {
    ibase_execute($query, $bar, $baz);
}

?>
```

### See Also

-   <span class="function">ibase\_query</span>

ibase\_fetch\_assoc
===================

Fetch a result row from a query as an associative array

### Description

<span class="type">array</span> <span
class="methodname">ibase\_fetch\_assoc</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$fetch_flag`<span class="initializer"> = 0</span></span> \] )

Fetch a result row from a query as an associative array.

<span class="function">ibase\_fetch\_assoc</span> fetches one row of
data from the `result`. If two or more columns of the result have the
same field names, the last column will take precedence. To access the
other column(s) of the same name, you either need to access the result
with numeric indices by using <span
class="function">ibase\_fetch\_row</span> or use alias names in your
query.

### Parameters

`result`  
The result handle.

`fetch_flag`  
`fetch_flag` is a combination of the constants **`IBASE_TEXT`** and
**`IBASE_UNIXTIME`** ORed together. Passing **`IBASE_TEXT`** will cause
this function to return BLOB contents instead of BLOB ids. Passing
**`IBASE_UNIXTIME`** will cause this function to return date/time values
as Unix timestamps instead of as formatted strings.

### Return Values

Returns an associative array that corresponds to the fetched row.
Subsequent calls will return the next row in the result set, or
**`false`** if there are no more rows.

### See Also

-   <span class="function">ibase\_fetch\_row</span>
-   <span class="function">ibase\_fetch\_object</span>

ibase\_fetch\_object
====================

Get an object from a InterBase database

### Description

<span class="type">object</span> <span
class="methodname">ibase\_fetch\_object</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> \[, <span class="methodparam"><span
class="type">int</span> `$fetch_flag`<span class="initializer"> =
0</span></span> \] )

Fetches a row as a pseudo-object from a given result identifier.

Subsequent calls to <span class="function">ibase\_fetch\_object</span>
return the next row in the result set.

### Parameters

`result_id`  
An InterBase result identifier obtained either by <span
class="function">ibase\_query</span> or <span
class="function">ibase\_execute</span>.

`fetch_flag`  
`fetch_flag` is a combination of the constants **`IBASE_TEXT`** and
**`IBASE_UNIXTIME`** ORed together. Passing **`IBASE_TEXT`** will cause
this function to return BLOB contents instead of BLOB ids. Passing
**`IBASE_UNIXTIME`** will cause this function to return date/time values
as Unix timestamps instead of as formatted strings.

### Return Values

Returns an object with the next row information, or **`false`** if there
are no more rows.

### Examples

**Example \#1 <span class="function">ibase\_fetch\_object</span>
example**

``` php
<?php
$dbh = ibase_connect($host, $username, $password);
$stmt = 'SELECT * FROM tblname';
$sth = ibase_query($dbh, $stmt);
while ($row = ibase_fetch_object($sth)) {
    echo $row->email . "\n";
}
ibase_close($dbh);
?>
```

### See Also

-   <span class="function">ibase\_fetch\_row</span>
-   <span class="function">ibase\_fetch\_assoc</span>

ibase\_fetch\_row
=================

Fetch a row from an InterBase database

### Description

<span class="type">array</span> <span
class="methodname">ibase\_fetch\_row</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_identifier`</span> \[, <span class="methodparam"><span
class="type">int</span> `$fetch_flag`<span class="initializer"> =
0</span></span> \] )

<span class="function">ibase\_fetch\_row</span> fetches one row of data
from the given result set.

Subsequent calls to <span class="function">ibase\_fetch\_row</span>
return the next row in the result set, or **`false`** if there are no
more rows.

### Parameters

`result_identifier`  
An InterBase result identifier.

`fetch_flag`  
`fetch_flag` is a combination of the constants **`IBASE_TEXT`** and
**`IBASE_UNIXTIME`** ORed together. Passing **`IBASE_TEXT`** will cause
this function to return BLOB contents instead of BLOB ids. Passing
**`IBASE_UNIXTIME`** will cause this function to return date/time values
as Unix timestamps instead of as formatted strings.

### Return Values

Returns an array that corresponds to the fetched row, or **`false`** if
there are no more rows. Each result column is stored in an array offset,
starting at offset 0.

### See Also

-   <span class="function">ibase\_fetch\_assoc</span>
-   <span class="function">ibase\_fetch\_object</span>

ibase\_field\_info
==================

Get information about a field

### Description

<span class="type">array</span> <span
class="methodname">ibase\_field\_info</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$field_number`</span> )

Returns an array with information about a field after a select query has
been run.

### Parameters

`result`  
An InterBase result identifier.

`field_number`  
Field offset.

### Return Values

Returns an array with the following keys: *name*, *alias*, *relation*,
*length* and *type*.

### Examples

**Example \#1 <span class="function">ibase\_field\_info</span> example**

``` php
<?php
$rs = ibase_query("SELECT * FROM tablename");
$coln = ibase_num_fields($rs);
for ($i = 0; $i < $coln; $i++) {
    $col_info = ibase_field_info($rs, $i);
    echo "name: ". $col_info['name']. "\n";
    echo "alias: ". $col_info['alias']. "\n";
    echo "relation: ". $col_info['relation']. "\n";
    echo "length: ". $col_info['length']. "\n";
    echo "type: ". $col_info['type']. "\n";
}
?>
```

### See Also

-   <span class="function">ibase\_num\_fields</span>

ibase\_free\_event\_handler
===========================

Cancels a registered event handler

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_free\_event\_handler</span> ( <span
class="methodparam"><span class="type">resource</span> `$event`</span> )

This function causes the registered event handler specified by `event`
to be cancelled. The callback function will no longer be called for the
events it was registered to handle.

### Parameters

`event`  
An event resource, created by <span
class="function">ibase\_set\_event\_handler</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ibase\_set\_event\_handler</span>

ibase\_free\_query
==================

Free memory allocated by a prepared query

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_free\_query</span> ( <span
class="methodparam"><span class="type">resource</span> `$query`</span> )

Frees a prepared query.

### Parameters

`query`  
A query prepared with <span class="function">ibase\_prepare</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ibase\_free\_result
===================

Free a result set

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_free\_result</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_identifier`</span> )

Frees a result set.

### Parameters

`result_identifier`  
A result set created by <span class="function">ibase\_query</span> or
<span class="function">ibase\_execute</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ibase\_gen\_id
==============

Increments the named generator and returns its new value

### Description

<span class="type">mixed</span> <span
class="methodname">ibase\_gen\_id</span> ( <span
class="methodparam"><span class="type">string</span> `$generator`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$increment`<span class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`<span class="initializer"> = **`null`**</span></span>
\]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Return Values

Returns new generator value as integer, or as string if the value is too
big.

ibase\_maintain\_db
===================

Execute a maintenance command on the database server

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_maintain\_db</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> , <span class="methodparam"><span
class="type">string</span> `$db`</span> , <span
class="methodparam"><span class="type">int</span> `$action`</span> \[,
<span class="methodparam"><span class="type">int</span> `$argument`<span
class="initializer"> = 0</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ibase\_modify\_user
===================

Modify a user to a security database

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_modify\_user</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> , <span class="methodparam"><span
class="type">string</span> `$user_name`</span> , <span
class="methodparam"><span class="type">string</span> `$password`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$first_name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$middle_name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$last_name`</span>
\]\]\] )

### Parameters

`service_handle`  
The handle on the database server service.

`user_name`  
The login name of the database user to modify.

`password`  
The user's new password.

`first_name`  
The user's new first name.

`middle_name`  
The user's new middle name.

`last_name`  
The user's new last name.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ibase\_add\_user</span>
-   <span class="function">ibase\_delete\_user</span>

ibase\_name\_result
===================

Assigns a name to a result set

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_name\_result</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> )

This function assigns a name to a result set. This name can be used
later in UPDATE\|DELETE ... WHERE CURRENT OF `name` statements.

### Parameters

`result`  
An InterBase result set.

`name`  
The name to be assigned.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ibase\_name\_result</span>
example**

``` php
<?php
$result = ibase_query("SELECT field1,field2 FROM table FOR UPDATE");
ibase_name_result($result, "my_cursor");

$updateqry = ibase_prepare("UPDATE table SET field2 = ? WHERE CURRENT OF my_cursor");

for ($i = 0; ibase_fetch_row($result); ++$i) {
    ibase_execute($updateqry, $i);
}
?>
```

### See Also

-   <span class="function">ibase\_prepare</span>
-   <span class="function">ibase\_execute</span>

ibase\_num\_fields
==================

Get the number of fields in a result set

### Description

<span class="type">int</span> <span
class="methodname">ibase\_num\_fields</span> ( <span
class="methodparam"><span class="type">resource</span>
`$result_id`</span> )

Get the number of fields in a result set.

### Parameters

`result_id`  
An InterBase result identifier.

### Return Values

Returns the number of fields as an integer.

### Examples

**Example \#1 <span class="function">ibase\_num\_fields</span> example**

``` php
<?php
$rs = ibase_query("SELECT * FROM tablename");
$coln = ibase_num_fields($rs);
for ($i = 0; $i < $coln; $i++) {
    $col_info = ibase_field_info($rs, $i);
    echo "name: " . $col_info['name'] . "\n";
    echo "alias: " . $col_info['alias'] . "\n";
    echo "relation: " . $col_info['relation'] . "\n";
    echo "length: " . $col_info['length'] . "\n";
    echo "type: " . $col_info['type'] . "\n";
}
?>
```

### See Also

-   <span class="function">ibase\_field\_info</span>

ibase\_num\_params
==================

Return the number of parameters in a prepared query

### Description

<span class="type">int</span> <span
class="methodname">ibase\_num\_params</span> ( <span
class="methodparam"><span class="type">resource</span> `$query`</span> )

This function returns the number of parameters in the prepared query
specified by `query`. This is the number of binding arguments that must
be present when calling <span class="function">ibase\_execute</span>.

### Parameters

`query`  
The prepared query handle.

### Return Values

Returns the number of parameters as an integer.

### See Also

-   <span class="function">ibase\_prepare</span>
-   <span class="function">ibase\_param\_info</span>

ibase\_param\_info
==================

Return information about a parameter in a prepared query

### Description

<span class="type">array</span> <span
class="methodname">ibase\_param\_info</span> ( <span
class="methodparam"><span class="type">resource</span> `$query`</span> ,
<span class="methodparam"><span class="type">int</span>
`$param_number`</span> )

Returns an array with information about a parameter after a query has
been prepared.

### Parameters

`query`  
An InterBase prepared query handle.

`param_number`  
Parameter offset.

### Return Values

Returns an array with the following keys: *name*, *alias*, *relation*,
*length* and *type*.

### See Also

-   <span class="function">ibase\_field\_info</span>
-   <span class="function">ibase\_num\_params</span>

ibase\_pconnect
===============

Open a persistent connection to an InterBase database

### Description

<span class="type">resource</span> <span
class="methodname">ibase\_pconnect</span> (\[ <span
class="methodparam"><span class="type">string</span> `$database`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$username`</span> \[, <span class="methodparam"><span
class="type">string</span> `$password`</span> \[, <span
class="methodparam"><span class="type">string</span> `$charset`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$buffers`</span> \[, <span class="methodparam"><span
class="type">int</span> `$dialect`</span> \[, <span
class="methodparam"><span class="type">string</span> `$role`</span> \[,
<span class="methodparam"><span class="type">int</span> `$sync`</span>
\]\]\]\]\]\]\]\] )

Opens a persistent connection to an InterBase database.

<span class="function">ibase\_pconnect</span> acts very much like <span
class="function">ibase\_connect</span> with two major differences.

First, when connecting, the function will first try to find a
(persistent) link that's already opened with the same parameters. If one
is found, an identifier for it will be returned instead of opening a new
connection.

Second, the connection to the InterBase server will not be closed when
the execution of the script ends. Instead, the link will remain open for
future use (<span class="function">ibase\_close</span> will not close
links established by <span class="function">ibase\_pconnect</span>).
This type of link is therefore called 'persistent'.

### Parameters

`database`  
The `database` argument has to be a valid path to database file on the
server it resides on. If the server is not local, it must be prefixed
with either 'hostname:' (TCP/IP), '//hostname/' (NetBEUI) or 'hostname@'
(IPX/SPX), depending on the connection protocol used.

`username`  
The user name. Can be set with the *ibase.default\_user* `php.ini`
directive.

`password`  
The password for `username`. Can be set with the
*ibase.default\_password* `php.ini` directive.

`charset`  
`charset` is the default character set for a database.

`buffers`  
`buffers` is the number of database buffers to allocate for the
server-side cache. If 0 or omitted, server chooses its own default.

`dialect`  
`dialect` selects the default SQL dialect for any statement executed
within a connection, and it defaults to the highest one supported by
client libraries. Functional only with InterBase 6 and up.

`role`  
Functional only with InterBase 5 and up.

`sync`  

### Return Values

Returns an InterBase link identifier on success, or **`false`** on
error.

### See Also

-   <span class="function">ibase\_close</span>
-   <span class="function">ibase\_connect</span>

ibase\_prepare
==============

Prepare a query for later binding of parameter placeholders and
execution

### Description

<span class="type">resource</span> <span
class="methodname">ibase\_prepare</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

<span class="type">resource</span> <span
class="methodname">ibase\_prepare</span> ( <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$query`</span> )

<span class="type">resource</span> <span
class="methodname">ibase\_prepare</span> ( <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$trans`</span> , <span
class="methodparam"><span class="type">string</span> `$query`</span> )

Prepare a query for later binding of parameter placeholders and
execution (via <span class="function">ibase\_execute</span>).

### Parameters

`query`  
An InterBase query.

`link_identifier`  
An InterBase link identifier returned from <span
class="function">ibase\_connect</span>. If omitted, the last opened link
is assumed.

`trans`  
An InterBase transaction handle the query should be associated with. If
omitted, the default transaction of the connection is assumed.

### Return Values

Returns a prepared query handle, or **`false`** on error.

ibase\_query
============

Execute a query on an InterBase database

### Description

<span class="type">resource</span> <span
class="methodname">ibase\_query</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> \], <span class="methodparam"><span
class="type">string</span> `$query`</span> \[, <span
class="methodparam"><span class="type">int</span> `$bind_args`</span> \]
)

Performs a query on an InterBase database.

### Parameters

`link_identifier`  
An InterBase link identifier. If omitted, the last opened link is
assumed.

`query`  
An InterBase query.

`bind_args`  

### Return Values

If the query raises an error, returns **`false`**. If it is successful
and there is a (possibly empty) result set (such as with a SELECT
query), returns a result identifier. If the query was successful and
there were no results, returns **`true`**.

> **Note**:
>
> In PHP 5.0.0 and up, this function will return the number of rows
> affected by the query for INSERT, UPDATE and DELETE statements. In
> order to retain backward compatibility, it will return **`true`** for
> these statements if the query succeeded without affecting any rows.

### Errors/Exceptions

If you get some error like "arithmetic exception, numeric overflow, or
string truncation. Cannot transliterate character between character
sets" (this occurs when you try use some character with accents) when
using this and after <span class="function">ibase\_query</span> you must
set the character set (i.e. ISO8859\_1 or your current character set).

### Examples

**Example \#1 <span class="function">ibase\_query</span> example**

``` php
<?php

$host = 'localhost:/path/to/your.gdb';

$dbh = ibase_connect($host, $username, $password);
$stmt = 'SELECT * FROM tblname';

$sth = ibase_query($dbh, $stmt) or die(ibase_errmsg());

?>
```

### See Also

-   <span class="function">ibase\_errmsg</span>
-   <span class="function">ibase\_fetch\_row</span>
-   <span class="function">ibase\_fetch\_object</span>
-   <span class="function">ibase\_free\_result</span>

ibase\_restore
==============

Initiates a restore task in the service manager and returns immediately

### Description

<span class="type">mixed</span> <span
class="methodname">ibase\_restore</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> , <span class="methodparam"><span
class="type">string</span> `$source_file`</span> , <span
class="methodparam"><span class="type">string</span> `$dest_db`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$verbose`<span
class="initializer"> = **`false`**</span></span> \]\] )

This function passes the arguments to the (remote) database server.
There it starts a new restore process. Therefore you won't get any
responses.

### Parameters

`service_handle`  
A previously opened connection to the database server.

`source_file`  
The absolute path on the server where the backup file is located.

`dest_db`  
The path to create the new database on the server. You can also use
database alias.

`options`  
Additional options to pass to the database server for restore. The
`options` parameter can be a combination of the following constants:
**`IBASE_RES_DEACTIVATE_IDX`**, **`IBASE_RES_NO_SHADOW`**,
**`IBASE_RES_NO_VALIDITY`**, **`IBASE_RES_ONE_AT_A_TIME`**,
**`IBASE_RES_REPLACE`**, **`IBASE_RES_CREATE`**,
**`IBASE_RES_USE_ALL_SPACE`**, **`IBASE_PRP_PAGE_BUFFERS`**,
**`IBASE_PRP_SWEEP_INTERVAL`**, **`IBASE_RES_CREATE`**. Read the section
about
<a href="/book/ibase.html#Predefined%20Constants" class="xref"></a> for
further information.

`verbose`  
Since the restore process is done on the database server, you don't have
any chance to get its output. This argument is useless.

### Return Values

Returns **`true`** on success or **`false`** on failure.

Since the restore process is done on the (remote) server, this function
just passes the arguments to it. While the arguments are legal, you
won't get **`false`**.

### Examples

**Example \#1 <span class="function">ibase\_restore</span> example**

``` php
<?php

// Attach to database server by ip address and port
$service = ibase_service_attach ('10.1.11.200/3050', 'sysdba', 'masterkey');

// Start the restore process on database server
// Restore employee backup to the new emps.fdb database
// Don't use any special arguments
ibase_restore($service, '/srv/backup/employees.fbk', '/srv/firebird/emps.fdb');

// Free the attached connection
ibase_service_detach ($service);
?>
```

**Example \#2 <span class="function">ibase\_restore</span> example with
arguments**

``` php
<?php

// Attach to database server by name and default port
$service = ibase_service_attach ('fb-server.contoso.local', 'sysdba', 'masterkey');

// Start the restore process on database server
// Restore to employee database using alias.
// Restore without indixes. Replace existing database.
ibase_restore($service, '/srv/backup/employees.fbk', 'employees.fdb', IBASE_RES_DEACTIVATE_IDX | IBASE_RES_REPLACE);

// Free the attached connection
ibase_service_detach ($service);
?>
```

### See Also

-   <span class="function">ibase\_backup</span>

ibase\_rollback\_ret
====================

Roll back a transaction without closing it

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_rollback\_ret</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$link_or_trans_identifier`<span class="initializer"> =
**`null`**</span></span> \] )

Rolls back a transaction without closing it.

### Parameters

`link_or_trans_identifier`  
If called without an argument, this function rolls back the default
transaction of the default link. If the argument is a connection
identifier, the default transaction of the corresponding connection will
be rolled back. If the argument is a transaction identifier, the
corresponding transaction will be rolled back. The transaction context
will be retained, so statements executed from within this transaction
will not be invalidated.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ibase\_rollback
===============

Roll back a transaction

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_rollback</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$link_or_trans_identifier`<span class="initializer"> =
**`null`**</span></span> \] )

Rolls back a transaction.

### Parameters

`link_or_trans_identifier`  
If called without an argument, this function rolls back the default
transaction of the default link. If the argument is a connection
identifier, the default transaction of the corresponding connection will
be rolled back. If the argument is a transaction identifier, the
corresponding transaction will be rolled back.

### Return Values

Returns **`true`** on success or **`false`** on failure.

ibase\_server\_info
===================

Request information about a database server

### Description

<span class="type">string</span> <span
class="methodname">ibase\_server\_info</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> , <span class="methodparam"><span
class="type">int</span> `$action`</span> )

### Parameters

`service_handle`  
A previously created connection to the database server.

`action`  
A valid constant.

### Return Values

Returns mixed types depending on context.

### Examples

**Example \#1 <span class="function">ibase\_service\_attach</span>
example**

``` php
<?php
    // Attach to the remote Firebird server
    if (($service = ibase_service_attach('10.1.1.254/3050', 'sysdba', 'masterkey')) != FALSE) {

        // Successfully attached.

        // Output the info
        echo "Server version: " . ibase_server_info($service, IBASE_SVC_SERVER_VERSION) . "\n";
        echo "Server implementation: " . ibase_server_info($service, IBASE_SVC_IMPLEMENTATION) . "\n";
        echo "Server users: " . print_r(ibase_server_info($service, IBASE_SVC_GET_USERS), true) . "\n";
        echo "Server directory: " . ibase_server_info($service, IBASE_SVC_GET_ENV) . "\n";
        echo "Server lock path: " . ibase_server_info($service, IBASE_SVC_GET_ENV_LOCK) . "\n";
        echo "Server lib path: " . ibase_server_info($service, IBASE_SVC_GET_ENV_MSG) . "\n";
        echo "Path of user db: " . ibase_server_info($service, IBASE_SVC_USER_DBPATH) . "\n";
        echo "Established connections: " . print_r(ibase_server_info($service, IBASE_SVC_SVR_DB_INFO),true) . "\n";

        // Detach from server (disconnect)
        ibase_service_detach($service);

    }
    else {
        // Output message on error
        $conn_error = ibase_errmsg();
        die($conn_error);
    }
?>
```

The above example will output:

    Server version: LI-V3.0.4.33054 Firebird 3.0
    Server implementation: Firebird/Linux/AMD/Intel/x64
    Server users: Array
    (
        [0] => Array
            (
                [user_name] => SYSDBA
                [first_name] => Sql
                [middle_name] => Server
                [last_name] => Administrator
                [user_id] => 0
                [group_id] => 0
            )

    )

    Server directory: /etc/firebird/
    Server lock path: /tmp/firebird/
    Server lib path: /usr/lib64/firebird/lib/
    Path of user db: /var/lib/firebird/secdb/security3.fdb
    Established connections: Array
    (
        [attachments] => 3
        [databases] => 2
        [0] => /srv/firebird/poss.fdb
        [1] => /srv/firebird/employees.fdb
    )

ibase\_service\_attach
======================

Connect to the service manager

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">ibase\_service\_attach</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">string</span>
`$dba_username`</span> , <span class="methodparam"><span
class="type">string</span> `$dba_password`</span> )

### Parameters

`host`  
The name or ip address of the database host. You can define the port by
adding '/' and port number. If no port is specified, port 3050 will be
used.

`dba_username`  
The name of any valid user.

`dba_password`  
The user's password.

### Return Values

Returns a Interbase / Firebird link identifier on success or **`false`**
on failure.

### Examples

**Example \#1 <span class="function">ibase\_service\_attach</span>
example**

``` php
<?php
    // Attach to the remote Firebird server by ip address
    if (($service = ibase_service_attach('10.1.1.199', 'sysdba', 'masterkey')) != FALSE) {
        
        // Successfully attached. 
        // Fetch server version (something like 'LI-V3.0.4.33054 Firebird 3.0')
        $server_version  = ibase_server_info($service, IBASE_SVC_SERVER_VERSION);

        // Fetch server implementation (something like 'Firebird/Linux/AMD/Intel/x64')
        $server_implementation = ibase_server_info($service, IBASE_SVC_IMPLEMENTATION);

        // Detach from server (disconnect)
        ibase_service_detach($service);

        // Output the info
        echo "Server version: " . $server_version . "<br/>";
        echo "Server implementation: " . $server_implementation;
    }
    else {
        // Output message on error
        $conn_error = ibase_errmsg();
        die($conn_error);
    }

?>
```

**Example \#2 <span class="function">ibase\_service\_attach</span>
example using *hostname/port* syntax**

``` php
<?php
    // Attach to the remote Firebird server by name. Use Port 3050.
    if (($service = ibase_service_attach('FB-SRV-01.contoso.local/3050', 'sysdba', 'masterkey')) != FALSE) {
        
        // Successfully attached. 
        // Fetch server version (something like 'LI-V3.0.4.33054 Firebird 3.0')
        $server_version  = ibase_server_info($service, IBASE_SVC_SERVER_VERSION);

        // Fetch server implementation (something like 'Firebird/Linux/AMD/Intel/x64')
        $server_implementation = ibase_server_info($service, IBASE_SVC_IMPLEMENTATION);

        // Detach from server (disconnect)
        ibase_service_detach($service);

        // Output the info
        echo "Server version: " . $server_version . "<br/>";
        echo "Server implementation: " . $server_implementation;
    }
    else {
        // Output message on error
        $conn_error = ibase_errmsg();
        die($conn_error);
    }

?>
```

### See Also

-   <span class="function">ibase\_service\_detach</span>

ibase\_service\_detach
======================

Disconnect from the service manager

### Description

<span class="type">bool</span> <span
class="methodname">ibase\_service\_detach</span> ( <span
class="methodparam"><span class="type">resource</span>
`$service_handle`</span> )

### Parameters

`service_handle`  
A previously created connection to the database server.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ibase\_service\_detach</span>
example**

``` php
<?php
    // Attach to the remote Firebird server by ip address
    if (($service = ibase_service_attach('10.1.1.199', 'sysdba', 'masterkey')) != FALSE) {
        
        // Successfully attached. 
        // Fetch server version (something like 'LI-V3.0.4.33054 Firebird 3.0')
        $server_version  = ibase_server_info($service, IBASE_SVC_SERVER_VERSION);

        // Fetch server implementation (something like 'Firebird/Linux/AMD/Intel/x64')
        $server_implementation = ibase_server_info($service, IBASE_SVC_IMPLEMENTATION);

        // Detach from server (disconnect)
        if(ibase_service_detach($service) == FALSE) {
            echo "Error on service detach.";
        }
        else {
            echo "Successfully detached from service.";
        }

    }
    else {
        // Output message on error
        $conn_error = ibase_errmsg();
        die($conn_error);
    }

?>
```

ibase\_set\_event\_handler
==========================

Register a callback function to be called when events are posted

### Description

<span class="type">resource</span> <span
class="methodname">ibase\_set\_event\_handler</span> ( <span
class="methodparam"><span class="type">callable</span>
`$event_handler`</span> , <span class="methodparam"><span
class="type">string</span> `$event_name`</span> , <span
class="methodparam"><span class="type">string</span>
`$even_names`</span> )

<span class="type">resource</span> <span
class="methodname">ibase\_set\_event\_handler</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">callable</span> `$event_handler`</span> , <span
class="methodparam"><span class="type">string</span>
`$event_name`</span> , <span class="methodparam"><span
class="type">string</span> `$event_names`</span> )

This function registers a PHP user function as event handler for the
specified events.

### Parameters

`event_handler`  
The callback is called with the event name and the link resource as
arguments whenever one of the specified events is posted by the
database.

The callback must return **`false`** if the event handler should be
canceled. Any other return value is ignored. This function accepts up to
15 event arguments.

`event_name`  
An event name.

`event_names`  
At most 15 events allowed.

### Return Values

The return value is an event resource. This resource can be used to free
the event handler using <span
class="function">ibase\_free\_event\_handler</span>.

### Examples

**Example \#1 <span class="function">ibase\_set\_event\_handler</span>
example**

``` php
<?php

function event_handler($event_name, $link)
{
    if ($event_name == "NEW ORDER") {
        // process new order
        ibase_query($link, "UPDATE orders SET status='handled'");
    } else if ($event_name == "DB_SHUTDOWN") {
        // free event handler
        return false;
    }
}

ibase_set_event_handler($link, "event_handler", "NEW_ORDER", "DB_SHUTDOWN");
?>
```

### See Also

-   <span class="function">ibase\_free\_event\_handler</span>
-   <span class="function">ibase\_wait\_event</span>

ibase\_trans
============

Begin a transaction

### Description

<span class="type">resource</span> <span
class="methodname">ibase\_trans</span> (\[ <span
class="methodparam"><span class="type">int</span> `$trans_args`</span>
\[, <span class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> \]\] )

<span class="type">resource</span> <span
class="methodname">ibase\_trans</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$link_identifier`</span> \[, <span class="methodparam"><span
class="type">int</span> `$trans_args`</span> \]\] )

Begins a transaction.

> **Note**:
>
> The first call to <span class="function">ibase\_trans</span> will not
> return the default transaction of a connection. All transactions
> started by <span class="function">ibase\_trans</span> will be rolled
> back at the end of the script if they were not committed or rolled
> back by either <span class="function">ibase\_commit</span> or <span
> class="function">ibase\_rollback</span>.

> **Note**:
>
> This function will accept multiple `trans_args` and `link_identifier`
> arguments. This allows transactions over multiple database
> connections, which are committed using a 2-phase commit algorithm.
> This means you can rely on the updates to either succeed in every
> database, or fail in every database. It does NOT mean you can use
> tables from different databases in the same query!
>
> If you use transactions over multiple databases, you will have to
> specify both the `link_id` and `transaction_id` in calls to <span
> class="function">ibase\_query</span> and <span
> class="function">ibase\_prepare</span>.

### Parameters

`trans_args`  
`trans_args` can be a combination of **`IBASE_READ`**,
**`IBASE_WRITE`**, **`IBASE_COMMITTED`**, **`IBASE_CONSISTENCY`**,
**`IBASE_CONCURRENCY`**, **`IBASE_REC_VERSION`**,
**`IBASE_REC_NO_VERSION`**, **`IBASE_WAIT`** and **`IBASE_NOWAIT`**.

`link_identifier`  
An InterBase link identifier. If omitted, the last opened link is
assumed.

### Return Values

Returns a transaction handle, or **`false`** on error.

ibase\_wait\_event
==================

Wait for an event to be posted by the database

### Description

<span class="type">string</span> <span
class="methodname">ibase\_wait\_event</span> ( <span
class="methodparam"><span class="type">string</span>
`$event_name`</span> , <span class="methodparam"><span
class="type">string</span> `$event_names`</span> )

<span class="type">string</span> <span
class="methodname">ibase\_wait\_event</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$event_name`</span> , <span
class="methodparam"><span class="type">string</span>
`$event_names`</span> )

This function suspends execution of the script until one of the
specified events is posted by the database. The name of the event that
was posted is returned. This function accepts up to 15 event arguments.

### Parameters

`event_name`  
The event name.

`event_names`  

### Return Values

Returns the name of the event that was posted.

### See Also

-   <span class="function">ibase\_set\_event\_handler</span>
-   <span class="function">ibase\_free\_event\_handler</span>

**Table of Contents**

-   [fbird\_add\_user](/book/ibase.html#fbird_add_user) — Alias of
    ibase\_add\_user
-   [fbird\_affected\_rows](/book/ibase.html#fbird_affected_rows) —
    Alias of ibase\_affected\_rows
-   [fbird\_backup](/book/ibase.html#fbird_backup) — Alias of
    ibase\_backup
-   [fbird\_blob\_add](/book/ibase.html#fbird_blob_add) — Alias of
    ibase\_blob\_add
-   [fbird\_blob\_cancel](/book/ibase.html#fbird_blob_cancel) — Cancel
    creating blob
-   [fbird\_blob\_close](/book/ibase.html#fbird_blob_close) — Alias of
    ibase\_blob\_close
-   [fbird\_blob\_create](/book/ibase.html#fbird_blob_create) — Alias of
    ibase\_blob\_create
-   [fbird\_blob\_echo](/book/ibase.html#fbird_blob_echo) — Alias of
    ibase\_blob\_echo
-   [fbird\_blob\_get](/book/ibase.html#fbird_blob_get) — Alias of
    ibase\_blob\_get
-   [fbird\_blob\_import](/book/ibase.html#fbird_blob_import) — Alias of
    ibase\_blob\_import
-   [fbird\_blob\_info](/book/ibase.html#fbird_blob_info) — Alias of
    ibase\_blob\_info
-   [fbird\_blob\_open](/book/ibase.html#fbird_blob_open) — Alias of
    ibase\_blob\_open
-   [fbird\_close](/book/ibase.html#fbird_close) — Alias of ibase\_close
-   [fbird\_commit\_ret](/book/ibase.html#fbird_commit_ret) — Alias of
    ibase\_commit\_ret
-   [fbird\_commit](/book/ibase.html#fbird_commit) — Alias of
    ibase\_commit
-   [fbird\_connect](/book/ibase.html#fbird_connect) — Alias of
    ibase\_connect
-   [fbird\_db\_info](/book/ibase.html#fbird_db_info) — Alias of
    ibase\_db\_info
-   [fbird\_delete\_user](/book/ibase.html#fbird_delete_user) — Alias of
    ibase\_delete\_user
-   [fbird\_drop\_db](/book/ibase.html#fbird_drop_db) — Alias of
    ibase\_drop\_db
-   [fbird\_errcode](/book/ibase.html#fbird_errcode) — Alias of
    ibase\_errcode
-   [fbird\_errmsg](/book/ibase.html#fbird_errmsg) — Alias of
    ibase\_errmsg
-   [fbird\_execute](/book/ibase.html#fbird_execute) — Alias of
    ibase\_execute
-   [fbird\_fetch\_assoc](/book/ibase.html#fbird_fetch_assoc) — Alias of
    ibase\_fetch\_assoc
-   [fbird\_fetch\_object](/book/ibase.html#fbird_fetch_object) — Alias
    of ibase\_fetch\_object
-   [fbird\_fetch\_row](/book/ibase.html#fbird_fetch_row) — Alias of
    ibase\_fetch\_row
-   [fbird\_field\_info](/book/ibase.html#fbird_field_info) — Alias of
    ibase\_field\_info
-   [fbird\_free\_event\_handler](/book/ibase.html#fbird_free_event_handler)
    — Alias of ibase\_free\_event\_handler
-   [fbird\_free\_query](/book/ibase.html#fbird_free_query) — Alias of
    ibase\_free\_query
-   [fbird\_free\_result](/book/ibase.html#fbird_free_result) — Alias of
    ibase\_free\_result
-   [fbird\_gen\_id](/book/ibase.html#fbird_gen_id) — Alias of
    ibase\_gen\_id
-   [fbird\_maintain\_db](/book/ibase.html#fbird_maintain_db) — Alias of
    ibase\_maintain\_db
-   [fbird\_modify\_user](/book/ibase.html#fbird_modify_user) — Alias of
    ibase\_modify\_user
-   [fbird\_name\_result](/book/ibase.html#fbird_name_result) — Alias of
    ibase\_name\_result
-   [fbird\_num\_fields](/book/ibase.html#fbird_num_fields) — Alias of
    ibase\_num\_fields
-   [fbird\_num\_params](/book/ibase.html#fbird_num_params) — Alias of
    ibase\_num\_params
-   [fbird\_param\_info](/book/ibase.html#fbird_param_info) — Alias of
    ibase\_param\_info
-   [fbird\_pconnect](/book/ibase.html#fbird_pconnect) — Alias of
    ibase\_pconnect
-   [fbird\_prepare](/book/ibase.html#fbird_prepare) — Alias of
    ibase\_prepare
-   [fbird\_query](/book/ibase.html#fbird_query) — Alias of ibase\_query
-   [fbird\_restore](/book/ibase.html#fbird_restore) — Alias of
    ibase\_restore
-   [fbird\_rollback\_ret](/book/ibase.html#fbird_rollback_ret) — Alias
    of ibase\_rollback\_ret
-   [fbird\_rollback](/book/ibase.html#fbird_rollback) — Alias of
    ibase\_rollback
-   [fbird\_server\_info](/book/ibase.html#fbird_server_info) — Alias of
    ibase\_server\_info
-   [fbird\_service\_attach](/book/ibase.html#fbird_service_attach) —
    Alias of ibase\_service\_attach
-   [fbird\_service\_detach](/book/ibase.html#fbird_service_detach) —
    Alias of ibase\_service\_detach
-   [fbird\_set\_event\_handler](/book/ibase.html#fbird_set_event_handler)
    — Alias of ibase\_set\_event\_handler
-   [fbird\_trans](/book/ibase.html#fbird_trans) — Alias of ibase\_trans
-   [fbird\_wait\_event](/book/ibase.html#fbird_wait_event) — Alias of
    ibase\_wait\_event
-   [ibase\_add\_user](/book/ibase.html#ibase_add_user) — Add a user to
    a security database
-   [ibase\_affected\_rows](/book/ibase.html#ibase_affected_rows) —
    Return the number of rows that were affected by the previous query
-   [ibase\_backup](/book/ibase.html#ibase_backup) — Initiates a backup
    task in the service manager and returns immediately
-   [ibase\_blob\_add](/book/ibase.html#ibase_blob_add) — Add data into
    a newly created blob
-   [ibase\_blob\_cancel](/book/ibase.html#ibase_blob_cancel) — Cancel
    creating blob
-   [ibase\_blob\_close](/book/ibase.html#ibase_blob_close) — Close blob
-   [ibase\_blob\_create](/book/ibase.html#ibase_blob_create) — Create a
    new blob for adding data
-   [ibase\_blob\_echo](/book/ibase.html#ibase_blob_echo) — Output blob
    contents to browser
-   [ibase\_blob\_get](/book/ibase.html#ibase_blob_get) — Get len bytes
    data from open blob
-   [ibase\_blob\_import](/book/ibase.html#ibase_blob_import) — Create
    blob, copy file in it, and close it
-   [ibase\_blob\_info](/book/ibase.html#ibase_blob_info) — Return blob
    length and other useful info
-   [ibase\_blob\_open](/book/ibase.html#ibase_blob_open) — Open blob
    for retrieving data parts
-   [ibase\_close](/book/ibase.html#ibase_close) — Close a connection to
    an InterBase database
-   [ibase\_commit\_ret](/book/ibase.html#ibase_commit_ret) — Commit a
    transaction without closing it
-   [ibase\_commit](/book/ibase.html#ibase_commit) — Commit a
    transaction
-   [ibase\_connect](/book/ibase.html#ibase_connect) — Open a connection
    to a database
-   [ibase\_db\_info](/book/ibase.html#ibase_db_info) — Request
    statistics about a database
-   [ibase\_delete\_user](/book/ibase.html#ibase_delete_user) — Delete a
    user from a security database
-   [ibase\_drop\_db](/book/ibase.html#ibase_drop_db) — Drops a database
-   [ibase\_errcode](/book/ibase.html#ibase_errcode) — Return an error
    code
-   [ibase\_errmsg](/book/ibase.html#ibase_errmsg) — Return error
    messages
-   [ibase\_execute](/book/ibase.html#ibase_execute) — Execute a
    previously prepared query
-   [ibase\_fetch\_assoc](/book/ibase.html#ibase_fetch_assoc) — Fetch a
    result row from a query as an associative array
-   [ibase\_fetch\_object](/book/ibase.html#ibase_fetch_object) — Get an
    object from a InterBase database
-   [ibase\_fetch\_row](/book/ibase.html#ibase_fetch_row) — Fetch a row
    from an InterBase database
-   [ibase\_field\_info](/book/ibase.html#ibase_field_info) — Get
    information about a field
-   [ibase\_free\_event\_handler](/book/ibase.html#ibase_free_event_handler)
    — Cancels a registered event handler
-   [ibase\_free\_query](/book/ibase.html#ibase_free_query) — Free
    memory allocated by a prepared query
-   [ibase\_free\_result](/book/ibase.html#ibase_free_result) — Free a
    result set
-   [ibase\_gen\_id](/book/ibase.html#ibase_gen_id) — Increments the
    named generator and returns its new value
-   [ibase\_maintain\_db](/book/ibase.html#ibase_maintain_db) — Execute
    a maintenance command on the database server
-   [ibase\_modify\_user](/book/ibase.html#ibase_modify_user) — Modify a
    user to a security database
-   [ibase\_name\_result](/book/ibase.html#ibase_name_result) — Assigns
    a name to a result set
-   [ibase\_num\_fields](/book/ibase.html#ibase_num_fields) — Get the
    number of fields in a result set
-   [ibase\_num\_params](/book/ibase.html#ibase_num_params) — Return the
    number of parameters in a prepared query
-   [ibase\_param\_info](/book/ibase.html#ibase_param_info) — Return
    information about a parameter in a prepared query
-   [ibase\_pconnect](/book/ibase.html#ibase_pconnect) — Open a
    persistent connection to an InterBase database
-   [ibase\_prepare](/book/ibase.html#ibase_prepare) — Prepare a query
    for later binding of parameter placeholders and execution
-   [ibase\_query](/book/ibase.html#ibase_query) — Execute a query on an
    InterBase database
-   [ibase\_restore](/book/ibase.html#ibase_restore) — Initiates a
    restore task in the service manager and returns immediately
-   [ibase\_rollback\_ret](/book/ibase.html#ibase_rollback_ret) — Roll
    back a transaction without closing it
-   [ibase\_rollback](/book/ibase.html#ibase_rollback) — Roll back a
    transaction
-   [ibase\_server\_info](/book/ibase.html#ibase_server_info) — Request
    information about a database server
-   [ibase\_service\_attach](/book/ibase.html#ibase_service_attach) —
    Connect to the service manager
-   [ibase\_service\_detach](/book/ibase.html#ibase_service_detach) —
    Disconnect from the service manager
-   [ibase\_set\_event\_handler](/book/ibase.html#ibase_set_event_handler)
    — Register a callback function to be called when events are posted
-   [ibase\_trans](/book/ibase.html#ibase_trans) — Begin a transaction
-   [ibase\_wait\_event](/book/ibase.html#ibase_wait_event) — Wait for
    an event to be posted by the database

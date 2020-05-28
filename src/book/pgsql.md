PostgreSQL
==========

**Table of Contents**

-   [Introduction](/book/pgsql.html#Introduction)
-   [Installing/Configuring](/book/pgsql.html#Installing/Configuring)
    -   [Requirements](/book/pgsql.html#Requirements)
    -   [Installation](/book/pgsql.html#Installation)
    -   [Runtime
        Configuration](/book/pgsql.html#Runtime%20Configuration)
    -   [Resource Types](/book/pgsql.html#Resource%20Types)
-   [Predefined Constants](/book/pgsql.html#Predefined%20Constants)
-   [Examples](/book/pgsql.html#Examples)
    -   [Basic usage](/book/pgsql.html#Basic%20usage)
    -   [Basic usage](/book/pgsql.html#Basic%20usage)
-   [PostgreSQL Functions](/book/pgsql.html#PostgreSQL%20Functions)
    -   [pg\_affected\_rows](/book/pgsql.html#pg_affected_rows) —
        Returns number of affected records (tuples)
    -   [pg\_cancel\_query](/book/pgsql.html#pg_cancel_query) — Cancel
        an asynchronous query
    -   [pg\_client\_encoding](/book/pgsql.html#pg_client_encoding) —
        Gets the client encoding
    -   [pg\_close](/book/pgsql.html#pg_close) — Closes a PostgreSQL
        connection
    -   [pg\_connect\_poll](/book/pgsql.html#pg_connect_poll) — Poll the
        status of an in-progress asynchronous PostgreSQL connection
        attempt
    -   [pg\_connect](/book/pgsql.html#pg_connect) — Open a PostgreSQL
        connection
    -   [pg\_connection\_busy](/book/pgsql.html#pg_connection_busy) —
        Get connection is busy or not
    -   [pg\_connection\_reset](/book/pgsql.html#pg_connection_reset) —
        Reset connection (reconnect)
    -   [pg\_connection\_status](/book/pgsql.html#pg_connection_status)
        — Get connection status
    -   [pg\_consume\_input](/book/pgsql.html#pg_consume_input) — Reads
        input on the connection
    -   [pg\_convert](/book/pgsql.html#pg_convert) — Convert associative
        array values into forms suitable for SQL statements
    -   [pg\_copy\_from](/book/pgsql.html#pg_copy_from) — Insert records
        into a table from an array
    -   [pg\_copy\_to](/book/pgsql.html#pg_copy_to) — Copy a table to an
        array
    -   [pg\_dbname](/book/pgsql.html#pg_dbname) — Get the database name
    -   [pg\_delete](/book/pgsql.html#pg_delete) — Deletes records
    -   [pg\_end\_copy](/book/pgsql.html#pg_end_copy) — Sync with
        PostgreSQL backend
    -   [pg\_escape\_bytea](/book/pgsql.html#pg_escape_bytea) — Escape a
        string for insertion into a bytea field
    -   [pg\_escape\_identifier](/book/pgsql.html#pg_escape_identifier)
        — Escape a identifier for insertion into a text field
    -   [pg\_escape\_literal](/book/pgsql.html#pg_escape_literal) —
        Escape a literal for insertion into a text field
    -   [pg\_escape\_string](/book/pgsql.html#pg_escape_string) — Escape
        a string for query
    -   [pg\_execute](/book/pgsql.html#pg_execute) — Sends a request to
        execute a prepared statement with given parameters, and waits
        for the result
    -   [pg\_fetch\_all\_columns](/book/pgsql.html#pg_fetch_all_columns)
        — Fetches all rows in a particular result column as an array
    -   [pg\_fetch\_all](/book/pgsql.html#pg_fetch_all) — Fetches all
        rows from a result as an array
    -   [pg\_fetch\_array](/book/pgsql.html#pg_fetch_array) — Fetch a
        row as an array
    -   [pg\_fetch\_assoc](/book/pgsql.html#pg_fetch_assoc) — Fetch a
        row as an associative array
    -   [pg\_fetch\_object](/book/pgsql.html#pg_fetch_object) — Fetch a
        row as an object
    -   [pg\_fetch\_result](/book/pgsql.html#pg_fetch_result) — Returns
        values from a result resource
    -   [pg\_fetch\_row](/book/pgsql.html#pg_fetch_row) — Get a row as
        an enumerated array
    -   [pg\_field\_is\_null](/book/pgsql.html#pg_field_is_null) — Test
        if a field is SQL NULL
    -   [pg\_field\_name](/book/pgsql.html#pg_field_name) — Returns the
        name of a field
    -   [pg\_field\_num](/book/pgsql.html#pg_field_num) — Returns the
        field number of the named field
    -   [pg\_field\_prtlen](/book/pgsql.html#pg_field_prtlen) — Returns
        the printed length
    -   [pg\_field\_size](/book/pgsql.html#pg_field_size) — Returns the
        internal storage size of the named field
    -   [pg\_field\_table](/book/pgsql.html#pg_field_table) — Returns
        the name or oid of the tables field
    -   [pg\_field\_type\_oid](/book/pgsql.html#pg_field_type_oid) —
        Returns the type ID (OID) for the corresponding field number
    -   [pg\_field\_type](/book/pgsql.html#pg_field_type) — Returns the
        type name for the corresponding field number
    -   [pg\_flush](/book/pgsql.html#pg_flush) — Flush outbound query
        data on the connection
    -   [pg\_free\_result](/book/pgsql.html#pg_free_result) — Free
        result memory
    -   [pg\_get\_notify](/book/pgsql.html#pg_get_notify) — Gets SQL
        NOTIFY message
    -   [pg\_get\_pid](/book/pgsql.html#pg_get_pid) — Gets the backend's
        process ID
    -   [pg\_get\_result](/book/pgsql.html#pg_get_result) — Get
        asynchronous query result
    -   [pg\_host](/book/pgsql.html#pg_host) — Returns the host name
        associated with the connection
    -   [pg\_insert](/book/pgsql.html#pg_insert) — Insert array into
        table
    -   [pg\_last\_error](/book/pgsql.html#pg_last_error) — Get the last
        error message string of a connection
    -   [pg\_last\_notice](/book/pgsql.html#pg_last_notice) — Returns
        the last notice message from PostgreSQL server
    -   [pg\_last\_oid](/book/pgsql.html#pg_last_oid) — Returns the last
        row's OID
    -   [pg\_lo\_close](/book/pgsql.html#pg_lo_close) — Close a large
        object
    -   [pg\_lo\_create](/book/pgsql.html#pg_lo_create) — Create a large
        object
    -   [pg\_lo\_export](/book/pgsql.html#pg_lo_export) — Export a large
        object to file
    -   [pg\_lo\_import](/book/pgsql.html#pg_lo_import) — Import a large
        object from file
    -   [pg\_lo\_open](/book/pgsql.html#pg_lo_open) — Open a large
        object
    -   [pg\_lo\_read\_all](/book/pgsql.html#pg_lo_read_all) — Reads an
        entire large object and send straight to browser
    -   [pg\_lo\_read](/book/pgsql.html#pg_lo_read) — Read a large
        object
    -   [pg\_lo\_seek](/book/pgsql.html#pg_lo_seek) — Seeks position
        within a large object
    -   [pg\_lo\_tell](/book/pgsql.html#pg_lo_tell) — Returns current
        seek position a of large object
    -   [pg\_lo\_truncate](/book/pgsql.html#pg_lo_truncate) — Truncates
        a large object
    -   [pg\_lo\_unlink](/book/pgsql.html#pg_lo_unlink) — Delete a large
        object
    -   [pg\_lo\_write](/book/pgsql.html#pg_lo_write) — Write to a large
        object
    -   [pg\_meta\_data](/book/pgsql.html#pg_meta_data) — Get meta data
        for table
    -   [pg\_num\_fields](/book/pgsql.html#pg_num_fields) — Returns the
        number of fields in a result
    -   [pg\_num\_rows](/book/pgsql.html#pg_num_rows) — Returns the
        number of rows in a result
    -   [pg\_options](/book/pgsql.html#pg_options) — Get the options
        associated with the connection
    -   [pg\_parameter\_status](/book/pgsql.html#pg_parameter_status) —
        Looks up a current parameter setting of the server
    -   [pg\_pconnect](/book/pgsql.html#pg_pconnect) — Open a persistent
        PostgreSQL connection
    -   [pg\_ping](/book/pgsql.html#pg_ping) — Ping database connection
    -   [pg\_port](/book/pgsql.html#pg_port) — Return the port number
        associated with the connection
    -   [pg\_prepare](/book/pgsql.html#pg_prepare) — Submits a request
        to create a prepared statement with the given parameters, and
        waits for completion
    -   [pg\_put\_line](/book/pgsql.html#pg_put_line) — Send a
        NULL-terminated string to PostgreSQL backend
    -   [pg\_query\_params](/book/pgsql.html#pg_query_params) — Submits
        a command to the server and waits for the result, with the
        ability to pass parameters separately from the SQL command text
    -   [pg\_query](/book/pgsql.html#pg_query) — Execute a query
    -   [pg\_result\_error\_field](/book/pgsql.html#pg_result_error_field)
        — Returns an individual field of an error report
    -   [pg\_result\_error](/book/pgsql.html#pg_result_error) — Get
        error message associated with result
    -   [pg\_result\_seek](/book/pgsql.html#pg_result_seek) — Set
        internal row offset in result resource
    -   [pg\_result\_status](/book/pgsql.html#pg_result_status) — Get
        status of query result
    -   [pg\_select](/book/pgsql.html#pg_select) — Select records
    -   [pg\_send\_execute](/book/pgsql.html#pg_send_execute) — Sends a
        request to execute a prepared statement with given parameters,
        without waiting for the result(s)
    -   [pg\_send\_prepare](/book/pgsql.html#pg_send_prepare) — Sends a
        request to create a prepared statement with the given
        parameters, without waiting for completion
    -   [pg\_send\_query\_params](/book/pgsql.html#pg_send_query_params)
        — Submits a command and separate parameters to the server
        without waiting for the result(s)
    -   [pg\_send\_query](/book/pgsql.html#pg_send_query) — Sends
        asynchronous query
    -   [pg\_set\_client\_encoding](/book/pgsql.html#pg_set_client_encoding)
        — Set the client encoding
    -   [pg\_set\_error\_verbosity](/book/pgsql.html#pg_set_error_verbosity)
        — Determines the verbosity of messages returned by
        pg\_last\_error and pg\_result\_error
    -   [pg\_socket](/book/pgsql.html#pg_socket) — Get a read only
        handle to the socket underlying a PostgreSQL connection
    -   [pg\_trace](/book/pgsql.html#pg_trace) — Enable tracing a
        PostgreSQL connection
    -   [pg\_transaction\_status](/book/pgsql.html#pg_transaction_status)
        — Returns the current in-transaction status of the server
    -   [pg\_tty](/book/pgsql.html#pg_tty) — Return the TTY name
        associated with the connection
    -   [pg\_unescape\_bytea](/book/pgsql.html#pg_unescape_bytea) —
        Unescape binary for bytea type
    -   [pg\_untrace](/book/pgsql.html#pg_untrace) — Disable tracing of
        a PostgreSQL connection
    -   [pg\_update](/book/pgsql.html#pg_update) — Update table
    -   [pg\_version](/book/pgsql.html#pg_version) — Returns an array
        with client, protocol and server version (when available)

PostgreSQL database is an Open Source product and available without
cost. Postgres, developed originally in the UC Berkeley Computer Science
Department, pioneered many of the object-relational concepts now
becoming available in some commercial databases. It provides SQL92/SQL99
language support, transactions, referential integrity, stored procedures
and type extensibility. PostgreSQL is an open source descendant of this
original Berkeley code.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/pgsql.html#Requirements)
-   [Installation](/book/pgsql.html#Installation)
-   [Runtime Configuration](/book/pgsql.html#Runtime%20Configuration)
-   [Resource Types](/book/pgsql.html#Resource%20Types)

Requirements
------------

To use PostgreSQL support, you need PostgreSQL 6.5 or later, PostgreSQL
8.0 or later to enable all PostgreSQL module features. PostgreSQL
supports many character encodings including multibyte character
encoding. The current version and more information about PostgreSQL is
available at
<a href="http://www.postgresql.org/" class="link external">» http://www.postgresql.org/</a>
and the
<a href="http://www.postgresql.org/docs/current/interactive/" class="link external">» PostgreSQL Documentation</a>.

Installation
------------

In order to enable PostgreSQL support, **--with-pgsql\[=DIR\]** is
required when you compile PHP. *DIR* is the PostgreSQL base install
directory, defaults to `/usr/local/pgsql`. If shared object module is
available, PostgreSQL module may be loaded using
<a href="/ini/core.html#ini.extension" class="link">extension</a>
directive in `php.ini` or <span class="function">dl</span> function.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                     | Default | Changeable       | Changelog                  |
|--------------------------------------------------------------------------|---------|------------------|----------------------------|
| <a href="/book/pgsql.html#" class="link">pgsql.allow_persistent</a>      | "1"     | PHP\_INI\_SYSTEM |                            |
| <a href="/book/pgsql.html#" class="link">pgsql.max_persistent</a>        | "-1"    | PHP\_INI\_SYSTEM |                            |
| <a href="/book/pgsql.html#" class="link">pgsql.max_links</a>             | "-1"    | PHP\_INI\_SYSTEM |                            |
| <a href="/book/pgsql.html#" class="link">pgsql.auto_reset_persistent</a> | "0"     | PHP\_INI\_SYSTEM | Available since PHP 4.2.0. |
| <a href="/book/pgsql.html#" class="link">pgsql.ignore_notice</a>         | "0"     | PHP\_INI\_ALL    | Available since PHP 4.3.0. |
| <a href="/book/pgsql.html#" class="link">pgsql.log_notice</a>            | "0"     | PHP\_INI\_ALL    | Available since PHP 4.3.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`pgsql.allow_persistent` <span class="type">boolean</span>  
Whether to allow persistent Postgres connections.

`pgsql.max_persistent` <span class="type">integer</span>  
The maximum number of persistent Postgres connections per process.

`pgsql.max_links` <span class="type">integer</span>  
The maximum number of Postgres connections per process, including
persistent connections.

`pgsql.auto_reset_persistent` <span class="type">integer</span>  
Detect broken persistent links with <span
class="function">pg\_pconnect</span>. Needs a little overhead.

`pgsql.ignore_notice` <span class="type">integer</span>  
Whether or not to ignore PostgreSQL backend notices.

`pgsql.log_notice` <span class="type">integer</span>  
Whether or not to log PostgreSQL backends notice messages. The PHP
directive
<a href="/book/pgsql.html#" class="link">pgsql.ignore_notice</a> must be
off in order to log notice messages.

Resource Types
--------------

There are two resource types used in the PostgreSQL module. The first
one is the link identifier for a database connection, the second a
resource which holds the result of a query.

Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`PGSQL_LIBPQ_VERSION`** (<span class="type">string</span>)  
<span class="simpara"> Short libpq version that contains only numbers
and dots. </span>

**`PGSQL_LIBPQ_VERSION_STR`** (<span class="type">string</span>)  
<span class="simpara"> Long libpq version that includes compiler
information. </span>

**`PGSQL_ASSOC`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_fetch\_array</span>. Return an associative array of
field names and values. </span>

**`PGSQL_NUM`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_fetch\_array</span>. Return a numerically indexed
array of field numbers and values. </span>

**`PGSQL_BOTH`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_fetch\_array</span>. Return an array of field
values that is both numerically indexed (by field number) and associated
(by field name). </span>

**`PGSQL_CONNECT_FORCE_NEW`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_connect</span> to force the creation of a new
connection, rather than re-using an existing identical connection.
</span>

**`PGSQL_CONNECT_ASYNC`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_connect</span> to create an asynchronous
connection. Added in PHP 5.6.0. </span>

**`PGSQL_CONNECTION_AUTH_OK`** (<span class="type">integer</span>)  
<span class="simpara"> Available since PHP 5.6.0. </span>

**`PGSQL_CONNECTION_AWAITING_RESPONSE`** (<span class="type">integer</span>)  
<span class="simpara"> Available since PHP 5.6.0. </span>

**`PGSQL_CONNECTION_BAD`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_connection\_status</span> indicating that the
database connection is in an invalid state. </span>

**`PGSQL_CONNECTION_MADE`** (<span class="type">integer</span>)  
<span class="simpara"> Available since PHP 5.6.0. </span>

**`PGSQL_CONNECTION_OK`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_connection\_status</span> indicating that the
database connection is in a valid state. </span>

**`PGSQL_CONNECTION_SETENV`** (<span class="type">integer</span>)  
<span class="simpara"> Available since PHP 5.6.0. </span>

**`PGSQL_CONNECTION_SSL_STARTUP`** (<span class="type">integer</span>)  
<span class="simpara"> Available since PHP 5.6.0. </span>

**`PGSQL_CONNECTION_STARTED`** (<span class="type">integer</span>)  
<span class="simpara"> Available since PHP 5.6.0. </span>

**`PGSQL_SEEK_SET`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_lo\_seek</span>. Seek operation is to begin from
the start of the object. </span>

**`PGSQL_SEEK_CUR`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_lo\_seek</span>. Seek operation is to begin from
the current position. </span>

**`PGSQL_SEEK_END`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_lo\_seek</span>. Seek operation is to begin from
the end of the object. </span>

**`PGSQL_EMPTY_QUERY`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_result\_status</span>. The string sent to the
server was empty. </span>

**`PGSQL_COMMAND_OK`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_result\_status</span>. Successful completion of a
command returning no data. </span>

**`PGSQL_TUPLES_OK`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_result\_status</span>. Successful completion of a
command returning data (such as a *SELECT* or *SHOW*). </span>

**`PGSQL_COPY_OUT`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_result\_status</span>. Copy Out (from server) data
transfer started. </span>

**`PGSQL_COPY_IN`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_result\_status</span>. Copy In (to server) data
transfer started. </span>

**`PGSQL_BAD_RESPONSE`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_result\_status</span>. The server's response was
not understood. </span>

**`PGSQL_NONFATAL_ERROR`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_result\_status</span>. A nonfatal error (a notice
or warning) occurred. </span>

**`PGSQL_FATAL_ERROR`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_result\_status</span>. A fatal error occurred.
</span>

**`PGSQL_TRANSACTION_IDLE`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_transaction\_status</span>. Connection is currently
idle, not in a transaction. </span>

**`PGSQL_TRANSACTION_ACTIVE`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_transaction\_status</span>. A command is in
progress on the connection. A query has been sent via the connection and
not yet completed. </span>

**`PGSQL_TRANSACTION_INTRANS`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_transaction\_status</span>. The connection is idle,
in a transaction block. </span>

**`PGSQL_TRANSACTION_INERROR`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_transaction\_status</span>. The connection is idle,
in a failed transaction block. </span>

**`PGSQL_TRANSACTION_UNKNOWN`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_transaction\_status</span>. The connection is bad.
</span>

**`PGSQL_DIAG_SEVERITY`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. The severity; the
field contents are *ERROR*, *FATAL*, or *PANIC* (in an error message),
or *WARNING*, *NOTICE*, *DEBUG*, *INFO*, or *LOG* (in a notice message),
or a localized translation of one of these. Always present. </span>

**`PGSQL_DIAG_SQLSTATE`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. The SQLSTATE code for
the error. The SQLSTATE code identifies the type of error that has
occurred; it can be used by front-end applications to perform specific
operations (such as error handling) in response to a particular database
error. This field is not localizable, and is always present. </span>

**`PGSQL_DIAG_MESSAGE_PRIMARY`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. The primary
human-readable error message (typically one line). Always present.
</span>

**`PGSQL_DIAG_MESSAGE_DETAIL`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. Detail: an optional
secondary error message carrying more detail about the problem. May run
to multiple lines. </span>

**`PGSQL_DIAG_MESSAGE_HINT`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. Hint: an optional
suggestion what to do about the problem. This is intended to differ from
detail in that it offers advice (potentially inappropriate) rather than
hard facts. May run to multiple lines. </span>

**`PGSQL_DIAG_STATEMENT_POSITION`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. A string containing a
decimal integer indicating an error cursor position as an index into the
original statement string. The first character has index 1, and
positions are measured in characters not bytes. </span>

**`PGSQL_DIAG_INTERNAL_POSITION`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. This is defined the
same as the **`PG_DIAG_STATEMENT_POSITION`** field, but it is used when
the cursor position refers to an internally generated command rather
than the one submitted by the client. The **`PG_DIAG_INTERNAL_QUERY`**
field will always appear when this field appears. </span>

**`PGSQL_DIAG_INTERNAL_QUERY`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. The text of a failed
internally-generated command. This could be, for example, a SQL query
issued by a PL/pgSQL function. </span>

**`PGSQL_DIAG_CONTEXT`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. An indication of the
context in which the error occurred. Presently this includes a call
stack traceback of active procedural language functions and
internally-generated queries. The trace is one entry per line, most
recent first. </span>

**`PGSQL_DIAG_SOURCE_FILE`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. The file name of the
PostgreSQL source-code location where the error was reported. </span>

**`PGSQL_DIAG_SOURCE_LINE`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. The line number of the
PostgreSQL source-code location where the error was reported. </span>

**`PGSQL_DIAG_SOURCE_FUNCTION`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_error\_field</span>. The name of the
PostgreSQL source-code function reporting the error. </span>

**`PGSQL_DIAG_SCHEMA_NAME`** (<span class="type">string</span>)  
<span class="simpara"> Available since PHP 7.3.0. </span>

**`PGSQL_DIAG_TABLE_NAME`** (<span class="type">string</span>)  
<span class="simpara"> Available since PHP 7.3.0. </span>

**`PGSQL_DIAG_COLUMN_NAME`** (<span class="type">string</span>)  
<span class="simpara"> Available since PHP 7.3.0. </span>

**`PGSQL_DIAG_DATATYPE_NAME`** (<span class="type">string</span>)  
<span class="simpara"> Available since PHP 7.3.0. </span>

**`PGSQL_DIAG_CONSTRAINT_NAME`** (<span class="type">string</span>)  
<span class="simpara"> Available since PHP 7.3.0. </span>

**`PGSQL_ERRORS_TERSE`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_set\_error\_verbosity</span>. Specified that
returned messages include severity, primary text, and position only;
this will normally fit on a single line. </span>

**`PGSQL_ERRORS_DEFAULT`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_set\_error\_verbosity</span>. The default mode
produces messages that include the above plus any detail, hint, or
context fields (these may span multiple lines). </span>

**`PGSQL_ERRORS_VERBOSE`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_set\_error\_verbosity</span>. The verbose mode
includes all available fields. </span>

**`PGSQL_NOTICE_LAST`** (<span class="type">integer</span>)  
<span class="simpara"> Used by <span
class="function">pg\_last\_notice</span>. Available since PHP 7.1.0.
</span>

**`PGSQL_NOTICE_ALL`** (<span class="type">integer</span>)  
<span class="simpara"> Used by <span
class="function">pg\_last\_notice</span>. Available since PHP 7.1.0.
</span>

**`PGSQL_NOTICE_CLEAR`** (<span class="type">integer</span>)  
<span class="simpara"> Used by <span
class="function">pg\_last\_notice</span>. Available since PHP 7.1.0.
</span>

**`PGSQL_STATUS_LONG`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_status</span>. Indicates that numerical
result code is desired. </span>

**`PGSQL_STATUS_STRING`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_result\_status</span>. Indicates that textual
result command tag is desired. </span>

**`PGSQL_CONV_IGNORE_DEFAULT`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_convert</span>. Ignore default values in the table
during conversion. </span>

**`PGSQL_CONV_FORCE_NULL`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_convert</span>. Use SQL *NULL* in place of an empty
<span class="type">string</span>. </span>

**`PGSQL_CONV_IGNORE_NOT_NULL`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_convert</span>. Ignore conversion of **`NULL`**
into SQL *NOT NULL* columns. </span>

**`PGSQL_DML_NO_CONV`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_insert</span>, <span
class="function">pg\_select</span>, <span
class="function">pg\_update</span> and <span
class="function">pg\_delete</span>. All parameters passed as is. Manual
escape is required if parameters contain user supplied data. Use <span
class="function">pg\_escape\_string</span> for it. </span>

**`PGSQL_DML_EXEC`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_insert</span>, <span
class="function">pg\_select</span>, <span
class="function">pg\_update</span> and <span
class="function">pg\_delete</span>. Execute query by these functions.
</span>

**`PGSQL_DML_ASYNC`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_insert</span>, <span
class="function">pg\_select</span>, <span
class="function">pg\_update</span> and <span
class="function">pg\_delete</span>. Execute asynchronous query by these
functions. </span>

**`PGSQL_DML_STRING`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_insert</span>, <span
class="function">pg\_select</span>, <span
class="function">pg\_update</span> and <span
class="function">pg\_delete</span>. Return executed query string.
</span>

**`PGSQL_DML_ESCAPE`** (<span class="type">integer</span>)  
<span class="simpara"> Passed to <span
class="function">pg\_insert</span>, <span
class="function">pg\_select</span>, <span
class="function">pg\_update</span> and <span
class="function">pg\_delete</span>. Apply escape to all parameters
instead of calling <span class="function">pg\_convert</span> internally.
This option omits meta data look up. Query could be as fast as <span
class="function">pg\_query</span> and <span
class="function">pg\_send\_query</span>. Available since PHP 5.6.0.
</span>

**`PGSQL_POLLING_FAILED`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_connect\_poll</span> to indicate that the
connection attempt failed. Available since PHP 5.6.0. </span>

**`PGSQL_POLLING_READING`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_connect\_poll</span> to indicate that the
connection is waiting for the PostgreSQL socket to be readable.
Available since PHP 5.6.0. </span>

**`PGSQL_POLLING_WRITING`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_connect\_poll</span> to indicate that the
connection is waiting for the PostgreSQL socket to be writable.
Available since PHP 5.6.0. </span>

**`PGSQL_POLLING_OK`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_connect\_poll</span> to indicate that the
connection is ready to be used. Available since PHP 5.6.0. </span>

**`PGSQL_POLLING_ACTIVE`** (<span class="type">integer</span>)  
<span class="simpara"> Returned by <span
class="function">pg\_connect\_poll</span> to indicate that the
connection is currently active. Available since PHP 5.6.0. </span>

**`PGSQL_DIAG_SEVERITY_NONLOCALIZED`** (<span class="type">integer</span>)  
<span class="simpara"> The severity; the field contents are ERROR,
FATAL, or PANIC (in an error message), or WARNING, NOTICE, DEBUG, INFO,
or LOG (in a notice message). This is identical to the
PG\_DIAG\_SEVERITY field except that the contents are never localized.
This is present only in versions 9.6 and later / PHP 7.3.0 and later.
</span>

Examples
========

**Table of Contents**

-   [Basic usage](/book/pgsql.html#Basic%20usage)
-   [Basic usage](/book/pgsql.html#Basic%20usage)

Basic usage
-----------

This simple example shows how to connect, execute a query, print
resulting rows and disconnect from a PostgreSQL database.

**Example \#1 PostgreSQL extension overview example**

``` php
<?php
// Connecting, selecting database
$dbconn = pg_connect("host=localhost dbname=publishing user=www password=foo")
    or die('Could not connect: ' . pg_last_error());

// Performing SQL query
$query = 'SELECT * FROM authors';
$result = pg_query($query) or die('Query failed: ' . pg_last_error());

// Printing results in HTML
echo "<table>\n";
while ($line = pg_fetch_array($result, null, PGSQL_ASSOC)) {
    echo "\t<tr>\n";
    foreach ($line as $col_value) {
        echo "\t\t<td>$col_value</td>\n";
    }
    echo "\t</tr>\n";
}
echo "</table>\n";

// Free resultset
pg_free_result($result);

// Closing connection
pg_close($dbconn);
?>
```

Basic usage
-----------

These examples contain user defined functions similar to legacy MySQL
functions.

**Example \#1 PostgreSQL user defined functions example**

``` php
<?php
// This function should be needed, since PostgreSQL connection binds database.
function pg_list_dbs($db)
{
    assert(is_resource($db));
    $query = '
SELECT
 d.datname as "Name",
 u.usename as "Owner",
 pg_encoding_to_char(d.encoding) as "Encoding"
FROM
 pg_database d LEFT JOIN pg_user u ON d.datdba = u.usesysid
ORDER BY 1;
';
    return pg_query($db, $query);
}

// List tables.
function pg_list_tables($db)
{
    assert(is_resource($db));
    $query = "
SELECT
 c.relname as \"Name\",
 CASE c.relkind WHEN 'r' THEN 'table' WHEN 'v' THEN 'view' WHEN 'i' THEN 'index' WHEN 'S' THEN 'sequence' WHEN 's' THEN 'special' END as \"Type\",
  u.usename as \"Owner\"
FROM
 pg_class c LEFT JOIN pg_user u ON c.relowner = u.usesysid
WHERE
 c.relkind IN ('r','v','S','')
 AND c.relname !~ '^pg_'
ORDER BY 1;
";
    return pg_query($db, $query);
}

// See also pg_meta_data(). It returns field definition as array.
function pg_list_fields($db, $table)
{
    assert(is_resource($db));
    $query = "
SELECT
 a.attname,
 format_type(a.atttypid, a.atttypmod),
 a.attnotnull,
 a.atthasdef,
 a.attnum
FROM
 pg_class c,
 pg_attribute a
WHERE
 c.relname = '".$table."'
 AND a.attnum > 0 AND a.attrelid = c.oid
ORDER BY a.attnum;
";
    return pg_query($db, $query);
}
?>
```

Notes
-----

> **Note**:
>
> Not all functions are supported by all builds. It depends on your
> libpq (The PostgreSQL C client library) version and how libpq is
> compiled. If PHP PostgreSQL extensions are missing, then it is because
> your libpq version does not support them.

> **Note**:
>
> Most PostgreSQL functions accept `connection` as the optional first
> parameter. If it is not provided, the last opened connection is used.
> If it doesn't exist, functions return **`FALSE`**.

> **Note**:
>
> PostgreSQL automatically folds all identifiers (e.g. table/column
> names) to lower-case values at object creation time and at query time.
> To force the use of mixed or upper case identifiers, you must escape
> the identifier using double quotes ("").

> **Note**:
>
> PostgreSQL does not have special commands for fetching database schema
> information (eg. all the tables in the current database). Instead,
> there is a standard schema named *information\_schema* in PostgreSQL
> 7.4 and above containing system views with all the necessary
> information, in an easily queryable form. See the
> <a href="http://www.postgresql.org/docs/current/interactive/" class="link external">» PostgreSQL Documentation</a>
> for full details.

pg\_affected\_rows
==================

Returns number of affected records (tuples)

### Description

<span class="type">int</span> <span
class="methodname">pg\_affected\_rows</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
)

<span class="function">pg\_affected\_rows</span> returns the number of
tuples (instances/records/rows) affected by *INSERT*, *UPDATE*, and
*DELETE* queries.

Since PostgreSQL 9.0 and above, the server returns the number of
SELECTed rows. Older PostgreSQL return 0 for SELECT.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_cmdtuples</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

### Return Values

The number of rows affected by the query. If no tuple is affected, it
will return 0.

### Examples

**Example \#1 <span class="function">pg\_affected\_rows</span> example**

``` php
<?php
$result = pg_query($conn, "INSERT INTO authors VALUES ('Orwell', 2002, 'Animal Farm')");

$cmdtuples = pg_affected_rows($result);

echo $cmdtuples . " tuples are affected.\n";
?>
```

The above example will output:

    1 tuples are affected.

### See Also

-   <span class="function">pg\_query</span>
-   <span class="function">pg\_query\_params</span>
-   <span class="function">pg\_execute</span>
-   <span class="function">pg\_num\_rows</span>

pg\_cancel\_query
=================

Cancel an asynchronous query

### Description

<span class="type">bool</span> <span
class="methodname">pg\_cancel\_query</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

<span class="function">pg\_cancel\_query</span> cancels an asynchronous
query sent with <span class="function">pg\_send\_query</span>, <span
class="function">pg\_send\_query\_params</span> or <span
class="function">pg\_send\_execute</span>. You cannot cancel a query
executed using <span class="function">pg\_query</span>.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_cancel\_query</span> example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  if (!pg_connection_busy($dbconn)) {
      pg_send_query($dbconn, "select * from authors; select count(*) from authors;");
  }
  
  $res1 = pg_get_result($dbconn);
  echo "First call to pg_get_result(): $res1\n";
  $rows1 = pg_num_rows($res1);
  echo "$res1 has $rows1 records\n\n";
  
  // Cancel the currently running query.  Will be the second query if it is
  // still running.
  pg_cancel_query($dbconn);
?>
```

The above example will output:

    First call to pg_get_result(): Resource id #3
    Resource id #3 has 3 records

### See Also

-   <span class="function">pg\_send\_query</span>
-   <span class="function">pg\_connection\_busy</span>

pg\_client\_encoding
====================

Gets the client encoding

### Description

<span class="type">string</span> <span
class="methodname">pg\_client\_encoding</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

PostgreSQL supports automatic character set conversion between server
and client for certain character sets. <span
class="function">pg\_client\_encoding</span> returns the client encoding
as a string. The returned string will be one of the standard PostgreSQL
encoding identifiers.

> **Note**:
>
> This function requires PHP 4.0.3 or higher and PostgreSQL 7.0 or
> higher. If libpq is compiled without multibyte encoding support, <span
> class="function">pg\_client\_encoding</span> always returns
> *SQL\_ASCII*. Supported encoding depends on PostgreSQL version. Refer
> to the PostgreSQL Documentation supported encodings.
>
> The function used to be called <span
> class="function">pg\_clientencoding</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

The client encoding, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_client\_encoding</span>
example**

``` php
<?php
// Assume $conn is a connection to a ISO-8859-1 database
$encoding = pg_client_encoding($conn);

echo "Client encoding is: ", $encoding, "\n";
?>
```

The above example will output:

    Client encoding is: ISO-8859-1

### See Also

-   <span class="function">pg\_set\_client\_encoding</span>

pg\_close
=========

Closes a PostgreSQL connection

### Description

<span class="type">bool</span> <span class="methodname">pg\_close</span>
(\[ <span class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_close</span> closes the non-persistent
connection to a PostgreSQL database associated with the given
`connection` resource.

> **Note**:
>
> Using <span class="function">pg\_close</span> is not usually
> necessary, as non-persistent open connections are automatically closed
> at the end of the script.

If there is open large object resource on the connection, do not close
the connection before closing all large object resources.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_close</span> example**

``` php
<?php
$dbconn = pg_connect("host=localhost port=5432 dbname=mary")
   or die("Could not connect");
echo "Connected successfully";
pg_close($dbconn);
?>
```

The above example will output:

    Connected successfully

### See Also

-   <span class="function">pg\_connect</span>

pg\_connect\_poll
=================

Poll the status of an in-progress asynchronous PostgreSQL connection
attempt

### Description

<span class="type">int</span> <span
class="methodname">pg\_connect\_poll</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

<span class="function">pg\_connect\_poll</span> polls the status of a
PostgreSQL connection created by calling <span
class="function">pg\_connect</span> with the **`PGSQL_CONNECT_ASYNC`**
option.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

Returns **`PGSQL_POLLING_FAILED`**, **`PGSQL_POLLING_READING`**,
**`PGSQL_POLLING_WRITING`**, **`PGSQL_POLLING_OK`**, or
**`PGSQL_POLLING_ACTIVE`**.

pg\_connect
===========

Open a PostgreSQL connection

### Description

<span class="type">resource</span> <span
class="methodname">pg\_connect</span> ( <span class="methodparam"><span
class="type">string</span> `$connection_string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$connect_type`</span>
\] )

<span class="function">pg\_connect</span> opens a connection to a
PostgreSQL database specified by the `connection_string`.

If a second call is made to <span class="function">pg\_connect</span>
with the same `connection_string` as an existing connection, the
existing connection will be returned unless you pass
**`PGSQL_CONNECT_FORCE_NEW`** as `connect_type`.

The old syntax with multiple parameters **$conn = pg\_connect("host",
"port", "options", "tty", "dbname")** has been deprecated.

### Parameters

`connection_string`  
The `connection_string` can be empty to use all default parameters, or
it can contain one or more parameter settings separated by whitespace.
Each parameter setting is in the form *keyword = value*. Spaces around
the equal sign are optional. To write an empty value or a value
containing spaces, surround it with single quotes, e.g., *keyword = 'a
value'*. Single quotes and backslashes within the value must be escaped
with a backslash, i.e., \\' and \\\\.

The currently recognized parameter keywords are: `host`, `hostaddr`,
`port`, `dbname` (defaults to value of `user`), `user`, `password`,
`connect_timeout`, `options`, `tty` (ignored), `sslmode`, `requiressl`
(deprecated in favor of `sslmode`), and `service`. Which of these
arguments exist depends on your PostgreSQL version.

The `options` parameter can be used to set command line parameters to be
invoked by the server.

`connect_type`  
If **`PGSQL_CONNECT_FORCE_NEW`** is passed, then a new connection is
created, even if the `connection_string` is identical to an existing
connection.

If **`PGSQL_CONNECT_ASYNC`** is given, then the connection is
established asynchronously. The state of the connection can then be
checked via <span class="function">pg\_connect\_poll</span> or <span
class="function">pg\_connection\_status</span>.

### Return Values

PostgreSQL connection resource on success, **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                |
|---------|--------------------------------------------------------------------------------------------|
| 5.6.0   | Support for giving the **`PGSQL_CONNECT_ASYNC`** constant as the `connect_type` was added. |

### Examples

**Example \#1 Using <span class="function">pg\_connect</span>**

``` php
<?php
$dbconn = pg_connect("dbname=mary");
//connect to a database named "mary"

$dbconn2 = pg_connect("host=localhost port=5432 dbname=mary");
// connect to a database named "mary" on "localhost" at port "5432"

$dbconn3 = pg_connect("host=sheep port=5432 dbname=mary user=lamb password=foo");
//connect to a database named "mary" on the host "sheep" with a username and password

$conn_string = "host=sheep port=5432 dbname=test user=lamb password=bar";
$dbconn4 = pg_connect($conn_string);
//connect to a database named "test" on the host "sheep" with a username and password

$dbconn5 = pg_connect("host=localhost options='--client_encoding=UTF8'");
//connect to a database on "localhost" and set the command line parameter which tells the encoding is in UTF-8
?>
```

### See Also

-   <span class="function">pg\_pconnect</span>
-   <span class="function">pg\_close</span>
-   <span class="function">pg\_host</span>
-   <span class="function">pg\_port</span>
-   <span class="function">pg\_tty</span>
-   <span class="function">pg\_options</span>
-   <span class="function">pg\_dbname</span>

pg\_connection\_busy
====================

Get connection is busy or not

### Description

<span class="type">bool</span> <span
class="methodname">pg\_connection\_busy</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

<span class="function">pg\_connection\_busy</span> determines whether or
not a connection is busy. If it is busy, a previous query is still
executing. If <span class="function">pg\_get\_result</span> is used on
the connection, it will be blocked.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

Returns **`TRUE`** if the connection is busy, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">pg\_connection\_busy</span>
example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");
  $bs = pg_connection_busy($dbconn);
  if ($bs) {
      echo 'connection is busy';
  } else {
     echo 'connection is not busy';
  }
?>
```

### See Also

-   <span class="function">pg\_connection\_status</span>
-   <span class="function">pg\_get\_result</span>

pg\_connection\_reset
=====================

Reset connection (reconnect)

### Description

<span class="type">bool</span> <span
class="methodname">pg\_connection\_reset</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

<span class="function">pg\_connection\_reset</span> resets the
connection. It is useful for error recovery.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_connection\_reset</span>
example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");
  $dbconn2 = pg_connection_reset($dbconn);
  if ($dbconn2) {
      echo "reset successful\n";
  } else {
      echo "reset failed\n";
  }
?>
```

### See Also

-   <span class="function">pg\_connect</span>
-   <span class="function">pg\_pconnect</span>
-   <span class="function">pg\_connection\_status</span>

pg\_connection\_status
======================

Get connection status

### Description

<span class="type">int</span> <span
class="methodname">pg\_connection\_status</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

<span class="function">pg\_connection\_status</span> returns the status
of the specified `connection`.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

**`PGSQL_CONNECTION_OK`** or **`PGSQL_CONNECTION_BAD`**.

### Examples

**Example \#1 <span class="function">pg\_connection\_status</span>
example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");
  $stat = pg_connection_status($dbconn);
  if ($stat === PGSQL_CONNECTION_OK) {
      echo 'Connection status ok';
  } else {
      echo 'Connection status bad';
  }    
?>
```

### See Also

-   <span class="function">pg\_connection\_busy</span>

pg\_consume\_input
==================

Reads input on the connection

### Description

<span class="type">bool</span> <span
class="methodname">pg\_consume\_input</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

<span class="function">pg\_consume\_input</span> consumes any input
waiting to be read from the database server.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

**`TRUE`** if no error occurred, or **`FALSE`** if there was an error.
Note that **`TRUE`** does not necessarily indicate that input was
waiting to be read.

pg\_convert
===========

Convert associative array values into forms suitable for SQL statements

### Description

<span class="type">array</span> <span
class="methodname">pg\_convert</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> , <span class="methodparam"><span
class="type">array</span> `$assoc_array`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = 0</span></span> \] )

<span class="function">pg\_convert</span> checks and converts the values
in `assoc_array` into suitable values for use in an SQL statement.
Precondition for <span class="function">pg\_convert</span> is the
existence of a table `table_name` which has at least as many columns as
`assoc_array` has elements. The fieldnames in `table_name` must match
the indices in `assoc_array` and the corresponding datatypes must be
compatible. Returns an array with the converted values on success,
**`FALSE`** otherwise.

> **Note**:
>
> Since PHP 5.6.0, it accepts boolean values, converting them to
> PostgreSQL booleans. String representations of boolean values are also
> supported. **`NULL`** is converted to PostgreSQL NULL.
>
> Prior to PHP 5.6.0, if there are boolean fields in `table_name` don't
> use the constant **`TRUE`** in `assoc_array`. It will be converted to
> the string 'TRUE' which is not a valid entry for boolean fields in
> PostgreSQL. Use one of "t", "true", 1, "y", "yes" instead.

### Parameters

`connection`  
PostgreSQL database connection resource.

`table_name`  
Name of the table against which to convert types.

`assoc_array`  
Data to be converted.

`options`  
Any number of **`PGSQL_CONV_IGNORE_DEFAULT`**,
**`PGSQL_CONV_FORCE_NULL`** or **`PGSQL_CONV_IGNORE_NOT_NULL`**,
combined.

### Return Values

An <span class="type">array</span> of converted values, or **`FALSE`**
on error.

### Examples

**Example \#1 <span class="function">pg\_convert</span> example**

``` php
<?php 
  $dbconn = pg_connect('dbname=foo');
  
  $tmp = array(
      'author' => 'Joe Thackery',
      'year' => 2005,
      'title' => 'My Life, by Joe Thackery'
  );
  
  $vals = pg_convert($dbconn, 'authors', $tmp);
?>
```

### Changelog

| Version | Description                                                                                                                                                                                              |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.6.0   | No longer experimental. Boolean/NULL data types are supported. Unknown/unsupported data types are escaped without validation. <span class="function">pg\_convert</span> can be used with any data types. |

### See Also

-   <span class="function">pg\_meta\_data</span>
-   <span class="function">pg\_insert</span>
-   <span class="function">pg\_select</span>
-   <span class="function">pg\_update</span>
-   <span class="function">pg\_delete</span>

pg\_copy\_from
==============

Insert records into a table from an array

### Description

<span class="type">bool</span> <span
class="methodname">pg\_copy\_from</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$table_name`</span> , <span
class="methodparam"><span class="type">array</span> `$rows`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$delimiter`</span> \[, <span class="methodparam"><span
class="type">string</span> `$null_as`</span> \]\] )

<span class="function">pg\_copy\_from</span> inserts records into a
table from `rows`. It issues a *COPY FROM* SQL command internally to
insert records.

### Parameters

`connection`  
PostgreSQL database connection resource.

`table_name`  
Name of the table into which to copy the `rows`.

`rows`  
An <span class="type">array</span> of data to be copied into
`table_name`. Each value in `rows` becomes a row in `table_name`. Each
value in `rows` should be a delimited string of the values to insert
into each field. Values should be linefeed terminated.

`delimiter`  
The token that separates values for each field in each element of
`rows`. Default is *TAB*.

`null_as`  
How SQL *NULL* values are represented in the `rows`. Default is \\N
("\\\\N").

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_copy\_from</span> example**

``` php
<?php
   $db = pg_connect("dbname=publisher") or die("Could not connect");
   
   $rows = pg_copy_to($db, $table_name);
   
   pg_query($db, "DELETE FROM $table_name");
   
   pg_copy_from($db, $table_name, $rows);
?>
```

### See Also

-   <span class="function">pg\_copy\_to</span>

pg\_copy\_to
============

Copy a table to an array

### Description

<span class="type">array</span> <span
class="methodname">pg\_copy\_to</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$delimiter`</span> \[, <span
class="methodparam"><span class="type">string</span> `$null_as`</span>
\]\] )

<span class="function">pg\_copy\_to</span> copies a table to an array.
It issues *COPY TO* SQL command internally to retrieve records.

### Parameters

`connection`  
PostgreSQL database connection resource.

`table_name`  
Name of the table from which to copy the data into `rows`.

`delimiter`  
The token that separates values for each field in each element of
`rows`. Default is *TAB*.

`null_as`  
How SQL *NULL* values are represented in the `rows`. Default is \\N
("\\\\N").

### Return Values

An <span class="type">array</span> with one element for each line of
*COPY* data. It returns **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_copy\_to</span> example**

``` php
<?php
   $db = pg_connect("dbname=publisher") or die("Could not connect");
   
   $rows = pg_copy_to($db, $table_name);
   
   pg_query($db, "DELETE FROM $table_name");
   
   pg_copy_from($db, $table_name, $rows);
?>
```

### See Also

-   <span class="function">pg\_copy\_from</span>

pg\_dbname
==========

Get the database name

### Description

<span class="type">string</span> <span
class="methodname">pg\_dbname</span> (\[ <span class="methodparam"><span
class="type">resource</span> `$connection`</span> \] )

<span class="function">pg\_dbname</span> returns the name of the
database that the given PostgreSQL `connection` resource.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

A <span class="type">string</span> containing the name of the database
the `connection` is to, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_dbname</span> example**

``` php
<?php
  error_reporting(E_ALL);

  pg_connect("host=localhost port=5432 dbname=mary");
  echo pg_dbname(); // mary
?>
```

pg\_delete
==========

Deletes records

### Description

<span class="type">mixed</span> <span
class="methodname">pg\_delete</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> , <span class="methodparam"><span
class="type">array</span> `$assoc_array`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = PGSQL\_DML\_EXEC</span></span> \] )

<span class="function">pg\_delete</span> deletes records from a table
specified by the keys and values in `assoc_array`. If `options` is
specified, <span class="function">pg\_convert</span> is applied to
`assoc_array` with the specified options.

If *options* is specified, <span class="function">pg\_convert</span> is
applied to *assoc\_array* with the specified flags.

By default <span class="function">pg\_delete</span> passes raw values.
Values must be escaped or PGSQL\_DML\_ESCAPE option must be specified.
PGSQL\_DML\_ESCAPE quotes and escapes parameters/identifiers. Therefore,
table/column names became case sensitive.

Note that neither escape nor prepared query can protect LIKE query,
JSON, Array, Regex, etc. These parameters should be handled according to
their contexts. i.e. Escape/validate values.

### Parameters

`connection`  
PostgreSQL database connection resource.

`table_name`  
Name of the table from which to delete rows.

`assoc_array`  
An <span class="type">array</span> whose keys are field names in the
table `table_name`, and whose values are the values of those fields that
are to be deleted.

`options`  
Any number of **`PGSQL_CONV_FORCE_NULL`**, **`PGSQL_DML_NO_CONV`**,
**`PGSQL_DML_ESCAPE`**, **`PGSQL_DML_EXEC`**, **`PGSQL_DML_ASYNC`** or
**`PGSQL_DML_STRING`** combined. If **`PGSQL_DML_STRING`** is part of
the `options` then query string is returned. When
**`PGSQL_DML_NO_CONV`** or **`PGSQL_DML_ESCAPE`** is set, it does not
call <span class="function">pg\_convert</span> internally.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Returns <span
class="type">string</span> if **`PGSQL_DML_STRING`** is passed via
`options`.

### Examples

**Example \#1 <span class="function">pg\_delete</span> example**

``` php
<?php 
  $db = pg_connect('dbname=foo');
  // This is safe somewhat, since all values are escaped.
  // However PostgreSQL supports JSON/Array. These are not
  // safe by neither escape nor prepared query.
  $res = pg_delete($db, 'post_log', $_POST);
  if ($res) {
      echo "POST data is deleted: $res\n";
  } else {
      echo "User must have sent wrong inputs\n";
  }
?>
```

### Changelog

| Version      | Description                                                                                                             |
|--------------|-------------------------------------------------------------------------------------------------------------------------|
| 5.6.0        | No longer experimental. Added **`PGSQL_DML_ESCAPE`** constant, **`TRUE`**/**`FALSE`** and **`NULL`** data type support. |
| 5.5.3/5.4.19 | Direct SQL injection to `table_name` and Indirect SQL injection to identifiers are fixed.                               |

### See Also

-   <span class="function">pg\_convert</span>

pg\_end\_copy
=============

Sync with PostgreSQL backend

### Description

<span class="type">bool</span> <span
class="methodname">pg\_end\_copy</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_end\_copy</span> syncs the PostgreSQL
frontend (usually a web server process) with the PostgreSQL server after
doing a copy operation performed by <span
class="function">pg\_put\_line</span>. <span
class="function">pg\_end\_copy</span> must be issued, otherwise the
PostgreSQL server may get out of sync with the frontend and will report
an error.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_end\_copy</span> example**

``` php
<?php 
  $conn = pg_pconnect("dbname=foo");
  pg_query($conn, "create table bar (a int4, b char(16), d float8)");
  pg_query($conn, "copy bar from stdin");
  pg_put_line($conn, "3\thello world\t4.5\n");
  pg_put_line($conn, "4\tgoodbye world\t7.11\n");
  pg_put_line($conn, "\\.\n");
  pg_end_copy($conn);
?>
```

### See Also

-   <span class="function">pg\_put\_line</span>

pg\_escape\_bytea
=================

Escape a string for insertion into a bytea field

### Description

<span class="type">string</span> <span
class="methodname">pg\_escape\_bytea</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$data`</span> )

<span class="function">pg\_escape\_bytea</span> escapes string for bytea
datatype. It returns escaped string.

> **Note**:
>
> When you *SELECT* a bytea type, PostgreSQL returns octal byte values
> prefixed with '\\' (e.g. \\032). Users are supposed to convert back to
> binary format manually.
>
> This function requires PostgreSQL 7.2 or later. With PostgreSQL 7.2.0
> and 7.2.1, bytea values must be cast when you enable multi-byte
> support. i.e. *INSERT INTO test\_table (image) VALUES
> ('$image\_escaped'::bytea);* PostgreSQL 7.2.2 or later does not need a
> cast. The exception is when the client and backend character encoding
> does not match, and there may be multi-byte stream error. User must
> then cast to bytea to avoid this error.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`data`  
A <span class="type">string</span> containing text or binary data to be
inserted into a bytea column.

### Return Values

A <span class="type">string</span> containing the escaped data.

### Changelog

| Version | Description        |
|---------|--------------------|
| 5.2.0   | `connection` added |

### Examples

**Example \#1 <span class="function">pg\_escape\_bytea</span> example**

``` php
<?php 
  // Connect to the database
  $dbconn = pg_connect('dbname=foo');
  
  // Read in a binary file
  $data = file_get_contents('image1.jpg');
  
  // Escape the binary data
  $escaped = pg_escape_bytea($data);
  
  // Insert it into the database
  pg_query("INSERT INTO gallery (name, data) VALUES ('Pine trees', '{$escaped}')");
?>
```

### See Also

-   <span class="function">pg\_unescape\_bytea</span>
-   <span class="function">pg\_escape\_string</span>

pg\_escape\_identifier
======================

Escape a identifier for insertion into a text field

### Description

<span class="type">string</span> <span
class="methodname">pg\_escape\_identifier</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$data`</span> )

<span class="function">pg\_escape\_identifier</span> escapes a
identifier (e.g. table, field names) for querying the database. It
returns an escaped identifier string for PostgreSQL server. <span
class="function">pg\_escape\_identifier</span> adds double quotes before
and after data. Users should not add double quotes. Use of this function
is recommended for identifier parameters in query. For SQL literals
(i.e. parameters except bytea), <span
class="function">pg\_escape\_literal</span> or <span
class="function">pg\_escape\_string</span> must be used. For bytea type
fields, <span class="function">pg\_escape\_bytea</span> must be used
instead.

> **Note**:
>
> This function has internal escape code and can also be used with
> PostgreSQL 8.4 or less.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`data`  
A <span class="type">string</span> containing text to be escaped.

### Return Values

A <span class="type">string</span> containing the escaped data.

### Examples

**Example \#1 <span class="function">pg\_escape\_identifier</span>
example**

``` php
<?php 
  // Connect to the database
  $dbconn = pg_connect('dbname=foo');
  
  // Escape the table name data
  $escaped = pg_escape_identifier($table_name);
  
  // Select rows from $table_name
  pg_query("SELECT * FROM {$escaped};");
?>
```

### See Also

-   <span class="function">pg\_escape\_literal</span>
-   <span class="function">pg\_escape\_bytea</span>
-   <span class="function">pg\_escape\_string</span>

pg\_escape\_literal
===================

Escape a literal for insertion into a text field

### Description

<span class="type">string</span> <span
class="methodname">pg\_escape\_literal</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$data`</span> )

<span class="function">pg\_escape\_literal</span> escapes a literal for
querying the PostgreSQL database. It returns an escaped literal in the
PostgreSQL format. <span class="function">pg\_escape\_literal</span>
adds quotes before and after data. Users should not add quotes. Use of
this function is recommended instead of <span
class="function">pg\_escape\_string</span>. If the type of the column is
bytea, <span class="function">pg\_escape\_bytea</span> must be used
instead. For escaping identifiers (e.g. table, field names), <span
class="function">pg\_escape\_identifier</span> must be used.

> **Note**:
>
> This function has internal escape code and can also be used with
> PostgreSQL 8.4 or less.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>. When there is no default
connection, it raises *E\_WARNING* and returns **`FALSE`**.

`data`  
A <span class="type">string</span> containing text to be escaped.

### Return Values

A <span class="type">string</span> containing the escaped data.

### Examples

**Example \#1 <span class="function">pg\_escape\_literal</span>
example**

``` php
<?php 
  // Connect to the database
  $dbconn = pg_connect('dbname=foo');
  
  // Read in a text file (containing apostrophes and backslashes)
  $data = file_get_contents('letter.txt');
  
  // Escape the text data
  $escaped = pg_escape_literal($data);
  
  // Insert it into the database. Note that no quotes around {$escaped}
  pg_query("INSERT INTO correspondence (name, data) VALUES ('My letter', {$escaped})");
?>
```

### See Also

-   <span class="function">pg\_escape\_identifier</span>
-   <span class="function">pg\_escape\_bytea</span>
-   <span class="function">pg\_escape\_string</span>

pg\_escape\_string
==================

Escape a string for query

### Description

<span class="type">string</span> <span
class="methodname">pg\_escape\_string</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$data`</span> )

<span class="function">pg\_escape\_string</span> escapes a string for
querying the database. It returns an escaped string in the PostgreSQL
format without quotes. <span class="function">pg\_escape\_literal</span>
is more preferred way to escape SQL parameters for PostgreSQL. <span
class="function">addslashes</span> must not be used with PostgreSQL. If
the type of the column is bytea, <span
class="function">pg\_escape\_bytea</span> must be used instead. <span
class="function">pg\_escape\_identifier</span> must be used to escape
identifiers (e.g. table names, field names)

> **Note**:
>
> This function requires PostgreSQL 7.2 or later.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`data`  
A <span class="type">string</span> containing text to be escaped.

### Return Values

A <span class="type">string</span> containing the escaped data.

### Changelog

| Version | Description        |
|---------|--------------------|
| 5.2.0   | `connection` added |

### Examples

**Example \#1 <span class="function">pg\_escape\_string</span> example**

``` php
<?php 
  // Connect to the database
  $dbconn = pg_connect('dbname=foo');
  
  // Read in a text file (containing apostrophes and backslashes)
  $data = file_get_contents('letter.txt');
  
  // Escape the text data
  $escaped = pg_escape_string($data);
  
  // Insert it into the database
  pg_query("INSERT INTO correspondence (name, data) VALUES ('My letter', '{$escaped}')");
?>
```

### See Also

-   <span class="function">pg\_escape\_bytea</span>

pg\_execute
===========

Sends a request to execute a prepared statement with given parameters,
and waits for the result

### Description

<span class="type">resource</span> <span
class="methodname">pg\_execute</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$stmtname`</span> , <span
class="methodparam"><span class="type">array</span> `$params`</span> )

Sends a request to execute a prepared statement with given parameters,
and waits for the result.

<span class="function">pg\_execute</span> is like <span
class="function">pg\_query\_params</span>, but the command to be
executed is specified by naming a previously-prepared statement, instead
of giving a query string. This feature allows commands that will be used
repeatedly to be parsed and planned just once, rather than each time
they are executed. The statement must have been prepared previously in
the current session. <span class="function">pg\_execute</span> is
supported only against PostgreSQL 7.4 or higher connections; it will
fail when using earlier versions.

The parameters are identical to <span
class="function">pg\_query\_params</span>, except that the name of a
prepared statement is given instead of a query string.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`stmtname`  
The name of the prepared statement to execute. if "" is specified, then
the unnamed statement is executed. The name must have been previously
prepared using <span class="function">pg\_prepare</span>, <span
class="function">pg\_send\_prepare</span> or a *PREPARE* SQL command.

`params`  
An array of parameter values to substitute for the $1, $2, etc.
placeholders in the original prepared query string. The number of
elements in the array must match the number of placeholders.

**Warning**
Elements are converted to strings by calling this function.

### Return Values

A query result resource on success or **`FALSE`** on failure.

### Examples

**Example \#1 Using <span class="function">pg\_execute</span>**

``` php
<?php
// Connect to a database named "mary"
$dbconn = pg_connect("dbname=mary");

// Prepare a query for execution
$result = pg_prepare($dbconn, "my_query", 'SELECT * FROM shops WHERE name = $1');

// Execute the prepared query.  Note that it is not necessary to escape
// the string "Joe's Widgets" in any way
$result = pg_execute($dbconn, "my_query", array("Joe's Widgets"));

// Execute the same prepared query, this time with a different parameter
$result = pg_execute($dbconn, "my_query", array("Clothes Clothes Clothes"));

?>
```

### See Also

-   <span class="function">pg\_prepare</span>
-   <span class="function">pg\_send\_prepare</span>
-   <span class="function">pg\_query\_params</span>

pg\_fetch\_all\_columns
=======================

Fetches all rows in a particular result column as an array

### Description

<span class="type">array</span> <span
class="methodname">pg\_fetch\_all\_columns</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$column`<span class="initializer"> = 0</span></span> \] )

<span class="function">pg\_fetch\_all\_columns</span> returns an array
that contains all rows (records) in a particular column of the result
resource.

> **Note**: <span class="simpara">This function sets NULL fields to the
> PHP **`NULL`** value.</span>

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`column`  
Column number, zero-based, to be retrieved from the result resource.
Defaults to the first column if not specified.

### Return Values

An <span class="type">array</span> with all values in the result column.

**`FALSE`** is returned if `column` is larger than the number of columns
in the result, or on any other error.

### Examples

**Example \#1 <span class="function">pg\_fetch\_all\_columns</span>
example**

``` php
<?php 
$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

$result = pg_query($conn, "SELECT title, name, address FROM authors");
if (!$result) {
  echo "An error occurred.\n";
  exit;
}

// Get an array of all author names
$arr = pg_fetch_all_columns($result, 1);

var_dump($arr);

?>
```

### See Also

-   <span class="function">pg\_fetch\_all</span>

pg\_fetch\_all
==============

Fetches all rows from a result as an array

### Description

<span class="type">array</span> <span
class="methodname">pg\_fetch\_all</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$result_type`<span class="initializer"> = PGSQL\_ASSOC</span></span> \]
)

<span class="function">pg\_fetch\_all</span> returns an array that
contains all rows (records) in the result resource.

> **Note**: <span class="simpara">This function sets NULL fields to the
> PHP **`NULL`** value.</span>

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

### Return Values

An <span class="type">array</span> with all rows in the result. Each row
is an array of field values indexed by field name.

**`FALSE`** is returned if there are no rows in the result, or on any
other error.

### Examples

**Example \#1 PostgreSQL fetch all**

``` php
<?php 
$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
    echo "An error occurred.\n";
    exit;
}

$result = pg_query($conn, "SELECT * FROM authors");
if (!$result) {
    echo "An error occurred.\n";
    exit;
}

$arr = pg_fetch_all($result);

print_r($arr);

?>
```

The above example will output something similar to:

    Array
    (
        [0] => Array
            (
                [id] => 1
                [name] => Fred
            )

        [1] => Array
            (
                [id] => 2
                [name] => Bob
            )

    )

### Changelog

| Version | Description                            |
|---------|----------------------------------------|
| 7.1.0   | The `result_type` parameter was added. |

### See Also

-   <span class="function">pg\_fetch\_row</span>
-   <span class="function">pg\_fetch\_array</span>
-   <span class="function">pg\_fetch\_object</span>
-   <span class="function">pg\_fetch\_result</span>

pg\_fetch\_array
================

Fetch a row as an array

### Description

<span class="type">array</span> <span
class="methodname">pg\_fetch\_array</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$row`</span> \[, <span class="methodparam"><span
class="type">int</span> `$result_type`<span class="initializer"> =
PGSQL\_BOTH</span></span> \]\] )

<span class="function">pg\_fetch\_array</span> returns an array that
corresponds to the fetched row (record).

<span class="function">pg\_fetch\_array</span> is an extended version of
<span class="function">pg\_fetch\_row</span>. In addition to storing the
data in the numeric indices (field number) to the result array, it can
also store the data using associative indices (field name). It stores
both indices by default.

> **Note**: <span class="simpara">This function sets NULL fields to the
> PHP **`NULL`** value.</span>

<span class="function">pg\_fetch\_array</span> is NOT significantly
slower than using <span class="function">pg\_fetch\_row</span>, and is
significantly easier to use.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`row`  
Row number in result to fetch. Rows are numbered from 0 upwards. If
omitted or **`NULL`**, the next row is fetched.

`result_type`  
An optional parameter that controls how the returned <span
class="type">array</span> is indexed. `result_type` is a constant and
can take the following values: **`PGSQL_ASSOC`**, **`PGSQL_NUM`** and
**`PGSQL_BOTH`**. Using **`PGSQL_NUM`**, <span
class="function">pg\_fetch\_array</span> will return an array with
numerical indices, using **`PGSQL_ASSOC`** it will return only
associative indices while **`PGSQL_BOTH`**, the default, will return
both numerical and associative indices.

### Return Values

An <span class="type">array</span> indexed numerically (beginning with
0) or associatively (indexed by field name), or both. Each value in the
<span class="type">array</span> is represented as a <span
class="type">string</span>. Database *NULL* values are returned as
**`NULL`**.

**`FALSE`** is returned if `row` exceeds the number of rows in the set,
there are no more rows, or on any other error.

### Examples

**Example \#1 <span class="function">pg\_fetch\_array</span> example**

``` php
<?php 

$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

$result = pg_query($conn, "SELECT author, email FROM authors");
if (!$result) {
  echo "An error occurred.\n";
  exit;
}

$arr = pg_fetch_array($result, 0, PGSQL_NUM);
echo $arr[0] . " <- Row 1 Author\n";
echo $arr[1] . " <- Row 1 E-mail\n";

// The row parameter is optional; NULL can be passed instead,
// to pass a result_type.  Successive calls to pg_fetch_array
// will return the next row.
$arr = pg_fetch_array($result, NULL, PGSQL_ASSOC);
echo $arr["author"] . " <- Row 2 Author\n";
echo $arr["email"] . " <- Row 2 E-mail\n";

$arr = pg_fetch_array($result);
echo $arr["author"] . " <- Row 3 Author\n";
echo $arr[1] . " <- Row 3 E-mail\n";

?>
```

### See Also

-   <span class="function">pg\_fetch\_row</span>
-   <span class="function">pg\_fetch\_object</span>
-   <span class="function">pg\_fetch\_result</span>

pg\_fetch\_assoc
================

Fetch a row as an associative array

### Description

<span class="type">array</span> <span
class="methodname">pg\_fetch\_assoc</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$row`</span> \] )

<span class="function">pg\_fetch\_assoc</span> returns an associative
array that corresponds to the fetched row (records).

<span class="function">pg\_fetch\_assoc</span> is equivalent to calling
<span class="function">pg\_fetch\_array</span> with **`PGSQL_ASSOC`** as
the optional third parameter. It only returns an associative array. If
you need the numeric indices, use <span
class="function">pg\_fetch\_row</span>.

> **Note**: <span class="simpara">This function sets NULL fields to the
> PHP **`NULL`** value.</span>

<span class="function">pg\_fetch\_assoc</span> is NOT significantly
slower than using <span class="function">pg\_fetch\_row</span>, and is
significantly easier to use.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`row`  
Row number in result to fetch. Rows are numbered from 0 upwards. If
omitted or **`NULL`**, the next row is fetched.

### Return Values

An <span class="type">array</span> indexed associatively (by field
name). Each value in the <span class="type">array</span> is represented
as a <span class="type">string</span>. Database *NULL* values are
returned as **`NULL`**.

**`FALSE`** is returned if `row` exceeds the number of rows in the set,
there are no more rows, or on any other error.

### Examples

**Example \#1 <span class="function">pg\_fetch\_assoc</span> example**

``` php
<?php 
$conn = pg_connect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

$result = pg_query($conn, "SELECT id, author, email FROM authors");
if (!$result) {
  echo "An error occurred.\n";
  exit;
}

while ($row = pg_fetch_assoc($result)) {
  echo $row['id'];
  echo $row['author'];
  echo $row['email'];
}
?>
```

### See Also

-   <span class="function">pg\_fetch\_row</span>
-   <span class="function">pg\_fetch\_array</span>
-   <span class="function">pg\_fetch\_object</span>
-   <span class="function">pg\_fetch\_result</span>

pg\_fetch\_object
=================

Fetch a row as an object

### Description

<span class="type">object</span> <span
class="methodname">pg\_fetch\_object</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$row`</span> \[, <span class="methodparam"><span
class="type">int</span> `$result_type`<span class="initializer"> =
PGSQL\_ASSOC</span></span> \]\] )

<span class="type">object</span> <span
class="methodname">pg\_fetch\_object</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$row`</span> \[, <span class="methodparam"><span
class="type">string</span> `$class_name`</span> \[, <span
class="methodparam"><span class="type">array</span> `$params`</span>
\]\]\] )

<span class="function">pg\_fetch\_object</span> returns an object with
properties that correspond to the fetched row's field names. It can
optionally instantiate an object of a specific class, and pass
parameters to that class's constructor.

> **Note**: <span class="simpara">This function sets NULL fields to the
> PHP **`NULL`** value.</span>

Speed-wise, the function is identical to <span
class="function">pg\_fetch\_array</span>, and almost as fast as <span
class="function">pg\_fetch\_row</span> (the difference is
insignificant).

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`row`  
Row number in result to fetch. Rows are numbered from 0 upwards. If
omitted or **`NULL`**, the next row is fetched.

`result_type`  
Ignored and deprecated.

`class_name`  
The name of the class to instantiate, set the properties of and return.
If not specified, a <span class="classname">stdClass</span> object is
returned.

`params`  
An optional <span class="type">array</span> of parameters to pass to the
constructor for `class_name` objects.

### Return Values

An <span class="type">object</span> with one attribute for each field
name in the result. Database *NULL* values are returned as **`NULL`**.

**`FALSE`** is returned if `row` exceeds the number of rows in the set,
there are no more rows, or on any other error.

### Examples

**Example \#1 <span class="function">pg\_fetch\_object</span> example**

``` php
<?php 

$database = "store";

$db_conn = pg_connect("host=localhost port=5432 dbname=$database");
if (!$db_conn) {
  echo "Failed connecting to postgres database $database\n";
  exit;
}

$qu = pg_query($db_conn, "SELECT * FROM books ORDER BY author");


while ($data = pg_fetch_object($qu)) {
  echo $data->author . " (";
  echo $data->year . "): ";
  echo $data->title . "<br />";
}

pg_free_result($qu);
pg_close($db_conn);

?>
```

### See Also

-   <span class="function">pg\_query</span>
-   <span class="function">pg\_fetch\_array</span>
-   <span class="function">pg\_fetch\_assoc</span>
-   <span class="function">pg\_fetch\_row</span>
-   <span class="function">pg\_fetch\_result</span>

pg\_fetch\_result
=================

Returns values from a result resource

### Description

<span class="type">string</span> <span
class="methodname">pg\_fetch\_result</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span> `$row`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$field`</span> )

<span class="type">string</span> <span
class="methodname">pg\_fetch\_result</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$field`</span> )

<span class="function">pg\_fetch\_result</span> returns the value of a
particular row and field (column) in a PostgreSQL result resource.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_result</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`row`  
Row number in result to fetch. Rows are numbered from 0 upwards. If
omitted, next row is fetched.

`field`  
A <span class="type">string</span> representing the name of the field
(column) to fetch, otherwise an <span class="type">int</span>
representing the field number to fetch. Fields are numbered from 0
upwards.

### Return Values

Boolean is returned as "t" or "f". All other types, including arrays are
returned as strings formatted in the same default PostgreSQL manner that
you would see in the **psql** program. Database *NULL* values are
returned as **`NULL`**.

**`FALSE`** is returned if `row` exceeds the number of rows in the set,
or on any other error.

### Examples

**Example \#1 <span class="function">pg\_fetch\_result</span> example**

``` php
<?php
$db = pg_connect("dbname=users user=me") || die();

$res = pg_query($db, "SELECT 1 UNION ALL SELECT 2");

$val = pg_fetch_result($res, 1, 0);

echo "First field in the second row is: ", $val, "\n";
?>
```

The above example will output:

    First field in the second row is: 2

### See Also

-   <span class="function">pg\_query</span>
-   <span class="function">pg\_fetch\_array</span>

pg\_fetch\_row
==============

Get a row as an enumerated array

### Description

<span class="type">array</span> <span
class="methodname">pg\_fetch\_row</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$row`</span> \] )

<span class="function">pg\_fetch\_row</span> fetches one row of data
from the result associated with the specified `result` resource.

> **Note**: <span class="simpara">This function sets NULL fields to the
> PHP **`NULL`** value.</span>

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`row`  
Row number in result to fetch. Rows are numbered from 0 upwards. If
omitted or **`NULL`**, the next row is fetched.

### Return Values

An <span class="type">array</span>, indexed from 0 upwards, with each
value represented as a <span class="type">string</span>. Database *NULL*
values are returned as **`NULL`**.

**`FALSE`** is returned if `row` exceeds the number of rows in the set,
there are no more rows, or on any other error.

### Examples

**Example \#1 <span class="function">pg\_fetch\_row</span> example**

``` php
<?php

$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

$result = pg_query($conn, "SELECT author, email FROM authors");
if (!$result) {
  echo "An error occurred.\n";
  exit;
}

while ($row = pg_fetch_row($result)) {
  echo "Author: $row[0]  E-mail: $row[1]";
  echo "<br />\n";
}
 
?>
```

### See Also

-   <span class="function">pg\_query</span>
-   <span class="function">pg\_fetch\_array</span>
-   <span class="function">pg\_fetch\_object</span>
-   <span class="function">pg\_fetch\_result</span>

pg\_field\_is\_null
===================

Test if a field is SQL *NULL*

### Description

<span class="type">int</span> <span
class="methodname">pg\_field\_is\_null</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span> `$row`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$field`</span> )

<span class="type">int</span> <span
class="methodname">pg\_field\_is\_null</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$field`</span> )

<span class="function">pg\_field\_is\_null</span> tests if a field in a
PostgreSQL result resource is SQL *NULL* or not.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_fieldisnull</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`row`  
Row number in result to fetch. Rows are numbered from 0 upwards. If
omitted, current row is fetched.

`field`  
Field number (starting from 0) as an <span class="type">integer</span>
or the field name as a <span class="type">string</span>.

### Return Values

Returns *1* if the field in the given row is SQL *NULL*, *0* if not.
**`FALSE`** is returned if the row is out of range, or upon any other
error.

### Examples

**Example \#1 <span class="function">pg\_field\_is\_null</span>
example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die ("Could not connect");
  $res = pg_query($dbconn, "select * from authors where author = 'Orwell'");
  if ($res) {
      if (pg_field_is_null($res, 0, "year") == 1) {
          echo "The value of the field year is null.\n";
      }
      if (pg_field_is_null($res, 0, "year") == 0) {
          echo "The value of the field year is not null.\n";
    }
 }
?>
```

pg\_field\_name
===============

Returns the name of a field

### Description

<span class="type">string</span> <span
class="methodname">pg\_field\_name</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$field_number`</span> )

<span class="function">pg\_field\_name</span> returns the name of the
field occupying the given `field_number` in the given PostgreSQL
`result` resource. Field numbering starts from 0.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_fieldname</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`field_number`  
Field number, starting from 0.

### Return Values

The field name, or **`FALSE`** on error.

### Examples

**Example \#1 Getting information about fields**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  $res = pg_query($dbconn, "select * from authors where author = 'Orwell'");
  $i = pg_num_fields($res);
  for ($j = 0; $j < $i; $j++) {
      echo "column $j\n";
      $fieldname = pg_field_name($res, $j);
      echo "fieldname: $fieldname\n";
      echo "printed length: " . pg_field_prtlen($res, $fieldname) . " characters\n";
      echo "storage length: " . pg_field_size($res, $j) . " bytes\n";
      echo "field type: " . pg_field_type($res, $j) . " \n\n";
  }
?>
```

The above example will output:

    column 0
    fieldname: author
    printed length: 6 characters
    storage length: -1 bytes
    field type: varchar 

    column 1
    fieldname: year
    printed length: 4 characters
    storage length: 2 bytes
    field type: int2 

    column 2
    fieldname: title
    printed length: 24 characters
    storage length: -1 bytes
    field type: varchar 

### See Also

-   <span class="function">pg\_field\_num</span>

pg\_field\_num
==============

Returns the field number of the named field

### Description

<span class="type">int</span> <span
class="methodname">pg\_field\_num</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">string</span>
`$field_name`</span> )

<span class="function">pg\_field\_num</span> will return the number of
the field number that corresponds to the `field_name` in the given
PostgreSQL `result` resource.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_fieldnum</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`field_name`  
The name of the field.

### Return Values

The field number (numbered from 0), or -1 on error.

### Examples

**Example \#1 Getting information about fields**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  $res = pg_query($dbconn, "select author, year, title from authors where author = 'Orwell'");
  
  echo "Column 'title' is field number: ", pg_field_num($res, 'title');
?>
```

The above example will output:

    Column 'title' is field number: 2

### See Also

-   <span class="function">pg\_field\_name</span>

pg\_field\_prtlen
=================

Returns the printed length

### Description

<span class="type">int</span> <span
class="methodname">pg\_field\_prtlen</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$row_number`</span> , <span class="methodparam"><span
class="type">mixed</span> `$field_name_or_number`</span> )

<span class="type">int</span> <span
class="methodname">pg\_field\_prtlen</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$field_name_or_number`</span> )

<span class="function">pg\_field\_prtlen</span> returns the actual
printed length (number of characters) of a specific value in a
PostgreSQL `result`. Row numbering starts at 0. This function will
return **`FALSE`** on an error.

`field_name_or_number` can be passed either as an <span
class="type">integer</span> or as a <span class="type">string</span>. If
it is passed as an <span class="type">integer</span>, PHP recognises it
as the field number, otherwise as field name.

See the example given at the <span
class="function">pg\_field\_name</span> page.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_fieldprtlen</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`row`  
Row number in result. Rows are numbered from 0 upwards. If omitted,
current row is fetched.

### Return Values

The field printed length, or **`FALSE`** on error.

### Examples

**Example \#1 Getting information about fields**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  $res = pg_query($dbconn, "select * from authors where author = 'Orwell'");
  $i = pg_num_fields($res);
  for ($j = 0; $j < $i; $j++) {
      echo "column $j\n";
      $fieldname = pg_field_name($res, $j);
      echo "fieldname: $fieldname\n";
      echo "printed length: " . pg_field_prtlen($res, $fieldname) . " characters\n";
      echo "storage length: " . pg_field_size($res, $j) . " bytes\n";
      echo "field type: " . pg_field_type($res, $j) . " \n\n";
  }
?>
```

The above example will output:

    column 0
    fieldname: author
    printed length: 6 characters
    storage length: -1 bytes
    field type: varchar 

    column 1
    fieldname: year
    printed length: 4 characters
    storage length: 2 bytes
    field type: int2 

    column 2
    fieldname: title
    printed length: 24 characters
    storage length: -1 bytes
    field type: varchar 

### See Also

-   <span class="function">pg\_field\_size</span>

pg\_field\_size
===============

Returns the internal storage size of the named field

### Description

<span class="type">int</span> <span
class="methodname">pg\_field\_size</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$field_number`</span> )

<span class="function">pg\_field\_size</span> returns the internal
storage size (in bytes) of the field number in the given PostgreSQL
`result`.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_fieldsize</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`field_number`  
Field number, starting from 0.

### Return Values

The internal field storage size (in bytes). -1 indicates a variable
length field. **`FALSE`** is returned on error.

### Examples

**Example \#1 Getting information about fields**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  $res = pg_query($dbconn, "select * from authors where author = 'Orwell'");
  $i = pg_num_fields($res);
  for ($j = 0; $j < $i; $j++) {
      echo "column $j\n";
      $fieldname = pg_field_name($res, $j);
      echo "fieldname: $fieldname\n";
      echo "printed length: " . pg_field_prtlen($res, $fieldname) . " characters\n";
      echo "storage length: " . pg_field_size($res, $j) . " bytes\n";
      echo "field type: " . pg_field_type($res, $j) . " \n\n";
  }
?>
```

The above example will output:

    column 0
    fieldname: author
    printed length: 6 characters
    storage length: -1 bytes
    field type: varchar 

    column 1
    fieldname: year
    printed length: 4 characters
    storage length: 2 bytes
    field type: int2 

    column 2
    fieldname: title
    printed length: 24 characters
    storage length: -1 bytes
    field type: varchar 

### See Also

-   <span class="function">pg\_field\_prtlen</span>
-   <span class="function">pg\_field\_type</span>

pg\_field\_table
================

Returns the name or oid of the tables field

### Description

<span class="type">mixed</span> <span
class="methodname">pg\_field\_table</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$field_number`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$oid_only`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="function">pg\_field\_table</span> returns the name of the
table that field belongs to, or the table's oid if `oid_only` is
**`TRUE`**.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`field_number`  
Field number, starting from 0.

`oid_only`  
By default the tables name that field belongs to is returned but if
`oid_only` is set to **`TRUE`**, then the oid will instead be returned.

### Return Values

On success either the fields table name or oid. Or, **`FALSE`** on
failure.

### Examples

**Example \#1 Getting table information about a field**

``` php
<?php
$dbconn = pg_connect("dbname=publisher") or die("Could not connect");

$res = pg_query($dbconn, "SELECT bar FROM foo");

echo pg_field_table($res, 0);
echo pg_field_table($res, 0, true);

$res = pg_query($dbconn, "SELECT version()");
var_dump(pg_field_table($res, 0));
?>
```

The above example will output something similar to:

    foo
    14379580

    bool(false)

### Notes

> **Note**:
>
> Returning the oid is much faster than returning the table name because
> fetching the table name requires a query to the database system table.

### See Also

-   <span class="function">pg\_field\_name</span>
-   <span class="function">pg\_field\_type</span>

pg\_field\_type\_oid
====================

Returns the type ID (OID) for the corresponding field number

### Description

<span class="type">int</span> <span
class="methodname">pg\_field\_type\_oid</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$field_number`</span> )

<span class="function">pg\_field\_type\_oid</span> returns an integer
containing the OID of the base type of the given `field_number` in the
given PostgreSQL `result` resource.

You can get more information about the field type by querying
PostgreSQL's *pg\_type* system table using the OID obtained with this
function. The PostgreSQL <span class="function">format\_type</span>
function will convert a type OID into an SQL standard type name.

> **Note**:
>
> If the field uses a PostgreSQL domain (rather than a basic type), it
> is the OID of the domain's underlying type that is returned, rather
> than the OID of the domain itself.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`field_number`  
Field number, starting from 0.

### Return Values

The OID of the field's base type. **`FALSE`** is returned on error.

### Examples

**Example \#1 Getting information about fields**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  // Assume 'title' is a varchar type
  $res = pg_query($dbconn, "select title from authors where author = 'Orwell'");

  echo "Title field type OID: ", pg_field_type_oid($res, 0);
?>
```

The above example will output:

    Title field type OID: 1043

### See Also

-   <span class="function">pg\_field\_type</span>
-   <span class="function">pg\_field\_prtlen</span>
-   <span class="function">pg\_field\_name</span>

pg\_field\_type
===============

Returns the type name for the corresponding field number

### Description

<span class="type">string</span> <span
class="methodname">pg\_field\_type</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$field_number`</span> )

<span class="function">pg\_field\_type</span> returns a string
containing the base type name of the given `field_number` in the given
PostgreSQL `result` resource.

> **Note**:
>
> If the field uses a PostgreSQL domain (rather than a basic type), it
> is the name of the domain's underlying type that is returned, rather
> than the name of the domain itself.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_fieldtype</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`field_number`  
Field number, starting from 0.

### Return Values

A <span class="type">string</span> containing the base name of the
field's type, or **`FALSE`** on error.

### Examples

**Example \#1 Getting information about fields**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  // Assume 'title' is a varchar type
  $res = pg_query($dbconn, "select title from authors where author = 'Orwell'");

  echo "Title field type: ", pg_field_type($res, 0);
?>
```

The above example will output:

    Title field type: varchar

### See Also

-   <span class="function">pg\_field\_prtlen</span>
-   <span class="function">pg\_field\_name</span>
-   <span class="function">pg\_field\_type\_oid</span>

pg\_flush
=========

Flush outbound query data on the connection

### Description

<span class="type">mixed</span> <span
class="methodname">pg\_flush</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> )

<span class="function">pg\_flush</span> flushes any outbound query data
waiting to be sent on the connection.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

Returns **`TRUE`** if the flush was successful or no data was waiting to
be flushed, *0* if part of the pending data was flushed but more remains
or **`FALSE`** on failure.

pg\_free\_result
================

Free result memory

### Description

<span class="type">bool</span> <span
class="methodname">pg\_free\_result</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
)

<span class="function">pg\_free\_result</span> frees the memory and data
associated with the specified PostgreSQL query result <span
class="type">resource</span>.

This function need only be called if memory consumption during script
execution is a problem. Otherwise, all result memory will be
automatically freed when the script ends.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_freeresult</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_free\_result</span> example**

``` php
<?php
$db = pg_connect("dbname=users user=me") || die();

$res = pg_query($db, "SELECT 1 UNION ALL SELECT 2");

$val = pg_fetch_result($res, 1, 0);

echo "First field in the second row is: ", $val, "\n";

pg_free_result($res);
?>
```

The above example will output:

    First field in the second row is: 2

### See Also

-   <span class="function">pg\_query</span>
-   <span class="function">pg\_query\_params</span>
-   <span class="function">pg\_execute</span>

pg\_get\_notify
===============

Gets SQL NOTIFY message

### Description

<span class="type">array</span> <span
class="methodname">pg\_get\_notify</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \[, <span class="methodparam"><span
class="type">int</span> `$result_type`</span> \] )

<span class="function">pg\_get\_notify</span> gets notifications
generated by a *NOTIFY* SQL command. To receive notifications, the
*LISTEN* SQL command must be issued.

### Parameters

`connection`  
PostgreSQL database connection resource.

`result_type`  
An optional parameter that controls how the returned <span
class="type">array</span> is indexed. `result_type` is a constant and
can take the following values: **`PGSQL_ASSOC`**, **`PGSQL_NUM`** and
**`PGSQL_BOTH`**. Using **`PGSQL_NUM`**, <span
class="function">pg\_get\_notify</span> will return an array with
numerical indices, using **`PGSQL_ASSOC`** it will return only
associative indices while **`PGSQL_BOTH`**, the default, will return
both numerical and associative indices.

### Return Values

An <span class="type">array</span> containing the *NOTIFY* message name
and backend PID. As of PHP 5.4.0 and if supported by the server, the
array also contains the server version and the payload. Otherwise if no
*NOTIFY* is waiting, then **`FALSE`** is returned.

### Examples

**Example \#1 PostgreSQL NOTIFY message**

``` php
<?php 
$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

// Listen 'author_updated' message from other processes
pg_query($conn, 'LISTEN author_updated;');
$notify = pg_get_notify($conn);
if (!$notify) {
  echo "No messages\n";
} else {
  print_r($notify);
}
?>
```

### See Also

-   <span class="function">pg\_get\_pid</span>

pg\_get\_pid
============

Gets the backend's process ID

### Description

<span class="type">int</span> <span
class="methodname">pg\_get\_pid</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> )

<span class="function">pg\_get\_pid</span> gets the backend's (database
server process) PID. The PID is useful to determine whether or not a
*NOTIFY* message received via <span
class="function">pg\_get\_notify</span> is sent from another process or
not.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

The backend database process ID.

### Examples

**Example \#1 PostgreSQL backend PID**

``` php
<?php 
$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

// Backend process PID. Use PID with pg_get_notify()
$pid = pg_get_pid($conn);
?>
```

### See Also

-   <span class="function">pg\_get\_notify</span>

pg\_get\_result
===============

Get asynchronous query result

### Description

<span class="type">resource</span> <span
class="methodname">pg\_get\_result</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_get\_result</span> gets the result resource
from an asynchronous query executed by <span
class="function">pg\_send\_query</span>, <span
class="function">pg\_send\_query\_params</span> or <span
class="function">pg\_send\_execute</span>.

<span class="function">pg\_send\_query</span> and the other asynchronous
query functions can send multiple queries to a PostgreSQL server and
<span class="function">pg\_get\_result</span> is used to get each
query's results, one by one.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

The result <span class="type">resource</span>, or **`FALSE`** if no more
results are available.

### Examples

**Example \#1 <span class="function">pg\_get\_result</span> example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  if (!pg_connection_busy($dbconn)) {
      pg_send_query($dbconn, "select * from authors; select count(*) from authors;");
  }
  
  $res1 = pg_get_result($dbconn);
  echo "First call to pg_get_result(): $res1\n";
  $rows1 = pg_num_rows($res1);
  echo "$res1 has $rows1 records\n\n";
  
  $res2 = pg_get_result($dbconn);
  echo "Second call to pg_get_result(): $res2\n";
  $rows2 = pg_num_rows($res2);
  echo "$res2 has $rows2 records\n";
?>
```

The above example will output:

    First call to pg_get_result(): Resource id #3
    Resource id #3 has 3 records

    Second call to pg_get_result(): Resource id #4
    Resource id #4 has 1 records

### See Also

-   <span class="function">pg\_send\_query</span>

pg\_host
========

Returns the host name associated with the connection

### Description

<span class="type">string</span> <span
class="methodname">pg\_host</span> (\[ <span class="methodparam"><span
class="type">resource</span> `$connection`</span> \] )

<span class="function">pg\_host</span> returns the host name of the
given PostgreSQL `connection` resource is connected to.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

A <span class="type">string</span> containing the name of the host the
`connection` is to, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_host</span> example**

``` php
<?php
$pgsql_conn = pg_connect("dbname=mark host=localhost");

if ($pgsql_conn) {
   print "Successfully connected to: " . pg_host($pgsql_conn) . "<br/>\n";
} else {
   print pg_last_error($pgsql_conn);
   exit;
}
?>
```

### See Also

-   <span class="function">pg\_connect</span>
-   <span class="function">pg\_pconnect</span>

pg\_insert
==========

Insert array into table

### Description

<span class="type">mixed</span> <span
class="methodname">pg\_insert</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> , <span class="methodparam"><span
class="type">array</span> `$assoc_array`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = PGSQL\_DML\_EXEC</span></span> \] )

<span class="function">pg\_insert</span> inserts the values of
`assoc_array` into the table specified by `table_name`. If `options` is
specified, <span class="function">pg\_convert</span> is applied to
`assoc_array` with the specified options.

If *options* is specified, <span class="function">pg\_convert</span> is
applied to *assoc\_array* with the specified flags.

By default <span class="function">pg\_insert</span> passes raw values.
Values must be escaped or PGSQL\_DML\_ESCAPE option must be specified.
PGSQL\_DML\_ESCAPE quotes and escapes parameters/identifiers. Therefore,
table/column names became case sensitive.

Note that neither escape nor prepared query can protect LIKE query,
JSON, Array, Regex, etc. These parameters should be handled according to
their contexts. i.e. Escape/validate values.

### Parameters

`connection`  
PostgreSQL database connection resource.

`table_name`  
Name of the table into which to insert rows. The table `table_name` must
at least have as many columns as `assoc_array` has elements.

`assoc_array`  
An <span class="type">array</span> whose keys are field names in the
table `table_name`, and whose values are the values of those fields that
are to be inserted.

`options`  
Any number of **`PGSQL_CONV_OPTS`**, **`PGSQL_DML_NO_CONV`**,
**`PGSQL_DML_ESCAPE`**, **`PGSQL_DML_EXEC`**, **`PGSQL_DML_ASYNC`** or
**`PGSQL_DML_STRING`** combined. If **`PGSQL_DML_STRING`** is part of
the `options` then query string is returned. When
**`PGSQL_DML_NO_CONV`** or **`PGSQL_DML_ESCAPE`** is set, it does not
call <span class="function">pg\_convert</span> internally.

### Return Values

Returns the connection resource on success, or **`FALSE`** on failure.
Returns <span class="type">string</span> if **`PGSQL_DML_STRING`** is
passed via `options`.

### Examples

**Example \#1 <span class="function">pg\_insert</span> example**

``` php
<?php 
  $dbconn = pg_connect('dbname=foo');
  // This is safe somewhat, since all values are escaped.
  // However PostgreSQL supports JSON/Array. These are not
  // safe by neither escape nor prepared query.
  $res = pg_insert($dbconn, 'post_log', $_POST, PG_DML_ESCAPE);
  if ($res) {
      echo "POST data is successfully logged\n";
  } else {
      echo "User must have sent wrong inputs\n";
  }
?>
```

### Changelog

| Version      | Description                                                                                                                 |
|--------------|-----------------------------------------------------------------------------------------------------------------------------|
| 5.6.0        | Unless **`PGSQL_DML_STRING`** is passed, the function now returns the connection resource instead of **`TRUE`** on success. |
| 5.6.0        | No longer experimental. Added **`PGSQL_DML_ESCAPE`** constant, **`TRUE`**/**`FALSE`** and **`NULL`** data type support.     |
| 5.5.3/5.4.19 | Direct SQL injection to `table_name` and Indirect SQL injection to identifiers are fixed.                                   |

### See Also

-   <span class="function">pg\_convert</span>

pg\_last\_error
===============

Get the last error message string of a connection

### Description

<span class="type">string</span> <span
class="methodname">pg\_last\_error</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_last\_error</span> returns the last error
message for a given `connection`.

Error messages may be overwritten by internal PostgreSQL (libpq)
function calls. It may not return an appropriate error message if
multiple errors occur inside a PostgreSQL module function.

Use <span class="function">pg\_result\_error</span>, <span
class="function">pg\_result\_error\_field</span>, <span
class="function">pg\_result\_status</span> and <span
class="function">pg\_connection\_status</span> for better error
handling.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_errormessage</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

A <span class="type">string</span> containing the last error message on
the given `connection`, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_last\_error</span> example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  // Query that fails
  $res = pg_query($dbconn, "select * from doesnotexist");
  
  echo pg_last_error($dbconn);
?>
```

### See Also

-   <span class="function">pg\_result\_error</span>
-   <span class="function">pg\_result\_error\_field</span>

pg\_last\_notice
================

Returns the last notice message from PostgreSQL server

### Description

<span class="type">mixed</span> <span
class="methodname">pg\_last\_notice</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \[, <span class="methodparam"><span
class="type">int</span> `$option`<span class="initializer"> =
PGSQL\_NOTICE\_LAST</span></span> \] )

<span class="function">pg\_last\_notice</span> returns the last notice
message from the PostgreSQL server on the specified `connection`. The
PostgreSQL server sends notice messages in several cases, for instance
when creating a *SERIAL* column in a table.

With <span class="function">pg\_last\_notice</span>, you can avoid
issuing useless queries by checking whether or not the notice is related
to your transaction.

Notice message tracking can be set to optional by setting 1 for
*pgsql.ignore\_notice* in `php.ini`.

Notice message logging can be set to optional by setting 0 for
*pgsql.log\_notice* in `php.ini`. Unless *pgsql.ignore\_notice* is set
to 0, notice message cannot be logged.

### Parameters

`connection`  
PostgreSQL database connection resource.

`option`  
One of **`PGSQL_NOTICE_LAST`** (to return last notice),
**`PGSQL_NOTICE_ALL`** (to return all notices), or
**`PGSQL_NOTICE_CLEAR`** (to clear notices).

### Return Values

A <span class="type">string</span> containing the last notice on the
given `connection` with **`PGSQL_NOTICE_LAST`**, an <span
class="type">array</span> with **`PGSQL_NOTICE_ALL`**, a <span
class="type">boolean</span> with **`PGSQL_NOTICE_CLEAR`**, or
**`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_last\_notice</span> example**

``` php
<?php
  $pgsql_conn = pg_connect("dbname=mark host=localhost");
  
  $res = pg_query("CREATE TABLE test (id SERIAL)");
  
  $notice = pg_last_notice($pgsql_conn);
  
  echo $notice;
?>
```

The above example will output:

    CREATE TABLE will create implicit sequence "test_id_seq" for "serial" column "test.id"

### Changelog

| Version | Description                       |
|---------|-----------------------------------|
| 7.1.0   | The `option` parameter was added. |

### See Also

-   <span class="function">pg\_query</span>
-   <span class="function">pg\_last\_error</span>

pg\_last\_oid
=============

Returns the last row's OID

### Description

<span class="type">string</span> <span
class="methodname">pg\_last\_oid</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
)

<span class="function">pg\_last\_oid</span> is used to retrieve the
`OID` assigned to an inserted row.

OID field became an optional field from PostgreSQL 7.2 and will not be
present by default in PostgreSQL 8.1. When the OID field is not present
in a table, the programmer must use <span
class="function">pg\_result\_status</span> to check for successful
insertion.

To get the value of a *SERIAL* field in an inserted row, it is necessary
to use the PostgreSQL *CURRVAL* function, naming the sequence whose last
value is required. If the name of the sequence is unknown, the
*pg\_get\_serial\_sequence* PostgreSQL 8.0 function is necessary.

PostgreSQL 8.1 has a function *LASTVAL* that returns the value of the
most recently used sequence in the session. This avoids the need for
naming the sequence, table or column altogether.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_getlastoid</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

### Return Values

A <span class="type">string</span> containing the OID assigned to the
most recently inserted row in the specified `connection`, or **`FALSE`**
on error or no available OID.

### Examples

**Example \#1 <span class="function">pg\_last\_oid</span> example**

``` php
<?php
  // Connect to the database
  pg_connect("dbname=mark host=localhost");

  // Create a sample table
  pg_query("CREATE TABLE test (a INTEGER) WITH OIDS");

  // Insert some data into it
  $res = pg_query("INSERT INTO test VALUES (1)");

  $oid = pg_last_oid($res);
?>
```

### See Also

-   <span class="function">pg\_query</span>
-   <span class="function">pg\_result\_status</span>

pg\_lo\_close
=============

Close a large object

### Description

<span class="type">bool</span> <span
class="methodname">pg\_lo\_close</span> ( <span
class="methodparam"><span class="type">resource</span>
`$large_object`</span> )

<span class="function">pg\_lo\_close</span> closes a large object.
`large_object` is a resource for the large object from <span
class="function">pg\_lo\_open</span>.

To use the large object interface, it is necessary to enclose it within
a transaction block.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_loclose</span>.

### Parameters

`result`  
PostgreSQL large object (LOB) resource, returned by <span
class="function">pg\_lo\_open</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_lo\_close</span> example**

``` php
<?php
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $oid = pg_lo_create($database);
   echo "$oid\n";
   $handle = pg_lo_open($database, $oid, "w");
   echo "$handle\n";
   pg_lo_write($handle, "large object data");
   pg_lo_close($handle);
   pg_query($database, "commit");
?>
```

### See Also

-   <span class="function">pg\_lo\_open</span>
-   <span class="function">pg\_lo\_create</span>
-   <span class="function">pg\_lo\_import</span>

pg\_lo\_create
==============

Create a large object

### Description

<span class="type">int</span> <span
class="methodname">pg\_lo\_create</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$object_id`</span> \]\] )

<span class="type">int</span> <span
class="methodname">pg\_lo\_create</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object_id`</span>
)

<span class="function">pg\_lo\_create</span> creates a large object and
returns the `OID` of the large object. PostgreSQL access modes
**`INV_READ`**, **`INV_WRITE`**, and **`INV_ARCHIVE`** are not
supported, the object is created always with both read and write access.
**`INV_ARCHIVE`** has been removed from PostgreSQL itself (version 6.3
and above).

To use the large object interface, it is necessary to enclose it within
a transaction block.

Instead of using the large object interface (which has no access
controls and is cumbersome to use), try PostgreSQL's `bytea` column type
and <span class="function">pg\_escape\_bytea</span>.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_locreate</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`object_id`  
If an `object_id` is given the function will try to create a large
object with this id, else a free object id is assigned by the server.
The parameter was added in PHP 5.3 and relies on functionality that
first appeared in PostgreSQL 8.1.

### Return Values

A large object `OID` or **`FALSE`** on error.

### Changelog

| Version | Description                         |
|---------|-------------------------------------|
| 5.3.0   | The optional `object_id` was added. |

### Examples

**Example \#1 <span class="function">pg\_lo\_create</span> example**

``` php
<?php
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $oid = pg_lo_create($database);
   echo "$oid\n";
   $handle = pg_lo_open($database, $oid, "w");
   echo "$handle\n";
   pg_lo_write($handle, "large object data");
   pg_lo_close($handle);
   pg_query($database, "commit");
?>
```

pg\_lo\_export
==============

Export a large object to file

### Description

<span class="type">bool</span> <span
class="methodname">pg\_lo\_export</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">int</span> `$oid`</span> , <span class="methodparam"><span
class="type">string</span> `$pathname`</span> )

<span class="function">pg\_lo\_export</span> takes a large object in a
PostgreSQL database and saves its contents to a file on the local
filesystem.

To use the large object interface, it is necessary to enclose it within
a transaction block.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_loexport</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`oid`  
The `OID` of the large object in the database.

`pathname`  
The full path and file name of the file in which to write the large
object on the client filesystem.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_lo\_export</span> example**

``` php
<?php
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $oid = pg_lo_create($database);
   $handle = pg_lo_open($database, $oid, "w");
   pg_lo_write($handle, "large object data");
   pg_lo_close($handle);
   pg_lo_export($database, $oid, '/tmp/lob.dat');
   pg_query($database, "commit");
?>
```

### See Also

-   <span class="function">pg\_lo\_import</span>

pg\_lo\_import
==============

Import a large object from file

### Description

<span class="type">int</span> <span
class="methodname">pg\_lo\_import</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$pathname`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$object_id`</span>
\] )

<span class="function">pg\_lo\_import</span> creates a new large object
in the database using a file on the filesystem as its data source.

To use the large object interface, it is necessary to enclose it within
a transaction block.

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the files or directories being operated
> upon have the same UID (owner) as the script that is being
> executed.</span>

> **Note**:
>
> This function used to be called <span
> class="function">pg\_loimport</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`pathname`  
The full path and file name of the file on the client filesystem from
which to read the large object data.

`object_id`  
If an `object_id` is given the function will try to create a large
object with this id, else a free object id is assigned by the server.
The parameter was added in PHP 5.3 and relies on functionality that
first appeared in PostgreSQL 8.1.

### Return Values

The `OID` of the newly created large object, or **`FALSE`** on failure.

### Changelog

| Version | Description                         |
|---------|-------------------------------------|
| 5.3.0   | The optional `object_id` was added. |

### Examples

**Example \#1 <span class="function">pg\_lo\_import</span> example**

``` php
<?php
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $oid = pg_lo_import($database, '/tmp/lob.dat');
   pg_query($database, "commit");
?>
```

### See Also

-   <span class="function">pg\_lo\_export</span>
-   <span class="function">pg\_lo\_open</span>

pg\_lo\_open
============

Open a large object

### Description

<span class="type">resource</span> <span
class="methodname">pg\_lo\_open</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">int</span> `$oid`</span> , <span
class="methodparam"><span class="type">string</span> `$mode`</span> )

<span class="function">pg\_lo\_open</span> opens a large object in the
database and returns large object resource so that it can be
manipulated.

**Warning**

Do not close the database connection before closing the large object
resource.

To use the large object interface, it is necessary to enclose it within
a transaction block.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_loopen</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`oid`  
The `OID` of the large object in the database.

`mode`  
Can be either "r" for read-only, "w" for write only or "rw" for read and
write.

### Return Values

A large object resource or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_lo\_open</span> example**

``` php
<?php
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $oid = pg_lo_create($database);
   echo "$oid\n";
   $handle = pg_lo_open($database, $oid, "w");
   echo "$handle\n";
   pg_lo_write($handle, "large object data");
   pg_lo_close($handle);
   pg_query($database, "commit");
?>
```

### See Also

-   <span class="function">pg\_lo\_close</span>
-   <span class="function">pg\_lo\_create</span>

pg\_lo\_read\_all
=================

Reads an entire large object and send straight to browser

### Description

<span class="type">int</span> <span
class="methodname">pg\_lo\_read\_all</span> ( <span
class="methodparam"><span class="type">resource</span>
`$large_object`</span> )

<span class="function">pg\_lo\_read\_all</span> reads a large object and
passes it straight through to the browser after sending all pending
headers. Mainly intended for sending binary data like images or sound.

To use the large object interface, it is necessary to enclose it within
a transaction block.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_loreadall</span>.

### Parameters

`large_object`  
PostgreSQL large object (LOB) resource, returned by <span
class="function">pg\_lo\_open</span>.

### Return Values

Number of bytes read or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_lo\_read\_all</span> example**

``` php
<?php
   header('Content-type: image/jpeg');
   $image_oid = 189762345;
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $handle = pg_lo_open($database, $image_oid, "r");
   pg_lo_read_all($handle);
   pg_query($database, "commit");
?>
```

### See Also

-   <span class="function">pg\_lo\_read</span>

pg\_lo\_read
============

Read a large object

### Description

<span class="type">string</span> <span
class="methodname">pg\_lo\_read</span> ( <span class="methodparam"><span
class="type">resource</span> `$large_object`</span> \[, <span
class="methodparam"><span class="type">int</span> `$len`<span
class="initializer"> = 8192</span></span> \] )

<span class="function">pg\_lo\_read</span> reads at most `len` bytes
from a large object and returns it as a <span
class="type">string</span>.

To use the large object interface, it is necessary to enclose it within
a transaction block.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_loread</span>.

### Parameters

`large_object`  
PostgreSQL large object (LOB) resource, returned by <span
class="function">pg\_lo\_open</span>.

`len`  
An optional maximum number of bytes to return.

### Return Values

A <span class="type">string</span> containing `len` bytes from the large
object, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_lo\_read</span> example**

``` php
<?php
   $doc_oid = 189762345;
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $handle = pg_lo_open($database, $doc_oid, "r");
   $data = pg_lo_read($handle, 50000);
   pg_query($database, "commit");
   echo $data;
?>
```

### See Also

-   <span class="function">pg\_lo\_read\_all</span>

pg\_lo\_seek
============

Seeks position within a large object

### Description

<span class="type">bool</span> <span
class="methodname">pg\_lo\_seek</span> ( <span class="methodparam"><span
class="type">resource</span> `$large_object`</span> , <span
class="methodparam"><span class="type">int</span> `$offset`</span> \[,
<span class="methodparam"><span class="type">int</span> `$whence`<span
class="initializer"> = PGSQL\_SEEK\_CUR</span></span> \] )

<span class="function">pg\_lo\_seek</span> seeks a position within a
large object resource.

To use the large object interface, it is necessary to enclose it within
a transaction block.

### Parameters

`large_object`  
PostgreSQL large object (LOB) resource, returned by <span
class="function">pg\_lo\_open</span>.

`offset`  
The number of bytes to seek.

`whence`  
One of the constants **`PGSQL_SEEK_SET`** (seek from object start),
**`PGSQL_SEEK_CUR`** (seek from current position) or
**`PGSQL_SEEK_END`** (seek from object end) .

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_lo\_seek</span> example**

``` php
<?php
   $doc_oid = 189762345;
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $handle = pg_lo_open($database, $doc_oid, "r");
   // Skip first 50000 bytes
   pg_lo_seek($handle, 50000, PGSQL_SEEK_SET);
   // Read the next 10000 bytes
   $data = pg_lo_read($handle, 10000);
   pg_query($database, "commit");
   echo $data;
?>
```

### Changelog

| Version | Description                                                                                                                                                  |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.6.0   | Added PostgreSQL 9.3's 64bit large object support. Both client and server must support PostgreSQL 9.3 and PHP must be 64bit build to use 64bit large object. |

### See Also

-   <span class="function">pg\_lo\_tell</span>

pg\_lo\_tell
============

Returns current seek position a of large object

### Description

<span class="type">int</span> <span
class="methodname">pg\_lo\_tell</span> ( <span class="methodparam"><span
class="type">resource</span> `$large_object`</span> )

<span class="function">pg\_lo\_tell</span> returns the current position
(offset from the beginning) of a large object.

To use the large object interface, it is necessary to enclose it within
a transaction block.

### Parameters

`large_object`  
PostgreSQL large object (LOB) resource, returned by <span
class="function">pg\_lo\_open</span>.

### Return Values

The current seek offset (in number of bytes) from the beginning of the
large object. If there is an error, the return value is negative.

### Examples

**Example \#1 <span class="function">pg\_lo\_tell</span> example**

``` php
<?php
   $doc_oid = 189762345;
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $handle = pg_lo_open($database, $doc_oid, "r");
   // Skip first 50000 bytes
   pg_lo_seek($handle, 50000, PGSQL_SEEK_SET);
   // See how far we've skipped
   $offset = pg_lo_tell($handle);
   echo "Seek position is: $offset";
   pg_query($database, "commit");
?>
```

The above example will output:

    Seek position is: 50000

### Changelog

| Version | Description                                                                                                                                                  |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.6.0   | Added PostgreSQL 9.3's 64bit large object support. Both client and server must support PostgreSQL 9.3 and PHP must be 64bit build to use 64bit large object. |

### See Also

-   <span class="function">pg\_lo\_seek</span>

pg\_lo\_truncate
================

Truncates a large object

### Description

<span class="type">bool</span> <span
class="methodname">pg\_lo\_truncate</span> ( <span
class="methodparam"><span class="type">resource</span>
`$large_object`</span> , <span class="methodparam"><span
class="type">int</span> `$size`</span> )

<span class="function">pg\_lo\_truncate</span> truncates a large object
resource.

To use the large object interface, it is necessary to enclose it within
a transaction block.

### Parameters

`large_object`  
PostgreSQL large object (LOB) resource, returned by <span
class="function">pg\_lo\_open</span>.

`size`  
The number of bytes to truncate.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_lo\_truncate</span> example**

``` php
<?php
   $doc_oid = 189762345;
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $handle = pg_lo_open($database, $doc_oid, "r");
   // Truncate to 0
   pg_lo_truncate($handle, 0);
   pg_query($database, "commit");
   echo $data;
?>
```

### Changelog

| Version | Description                                                                                                                                                                         |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.6.0   | Added truncate function. It supports PostgreSQL 9.3's 64bit large object. Both client and server must support PostgreSQL 9.3 and PHP must be 64bit build to use 64bit large object. |

### See Also

-   <span class="function">pg\_lo\_tell</span>

pg\_lo\_unlink
==============

Delete a large object

### Description

<span class="type">bool</span> <span
class="methodname">pg\_lo\_unlink</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">int</span> `$oid`</span> )

<span class="function">pg\_lo\_unlink</span> deletes a large object with
the `oid`. Returns **`TRUE`** on success or **`FALSE`** on failure.

To use the large object interface, it is necessary to enclose it within
a transaction block.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_lounlink</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`oid`  
The `OID` of the large object in the database.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_lo\_unlink</span> example**

``` php
<?php
   // OID of the large object to delete
   $doc_oid = 189762345;
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   pg_lo_unlink($database, $doc_oid);
   pg_query($database, "commit");
?>
```

### See Also

-   <span class="function">pg\_lo\_create</span>
-   <span class="function">pg\_lo\_import</span>

pg\_lo\_write
=============

Write to a large object

### Description

<span class="type">int</span> <span
class="methodname">pg\_lo\_write</span> ( <span
class="methodparam"><span class="type">resource</span>
`$large_object`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type">int</span> `$len`</span> \] )

<span class="function">pg\_lo\_write</span> writes data into a large
object at the current seek position.

To use the large object interface, it is necessary to enclose it within
a transaction block.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_lowrite</span>.

### Parameters

`large_object`  
PostgreSQL large object (LOB) resource, returned by <span
class="function">pg\_lo\_open</span>.

`data`  
The data to be written to the large object. If `len` is specified and is
less than the length of `data`, only `len` bytes will be written.

`len`  
An optional maximum number of bytes to write. Must be greater than zero
and no greater than the length of `data`. Defaults to the length of
`data`.

### Return Values

The number of bytes written to the large object, or **`FALSE`** on
error.

### Examples

**Example \#1 <span class="function">pg\_lo\_write</span> example**

``` php
<?php
   $doc_oid = 189762345;
   $data = "This will overwrite the start of the large object.";
   $database = pg_connect("dbname=jacarta");
   pg_query($database, "begin");
   $handle = pg_lo_open($database, $doc_oid, "w");
   $data = pg_lo_write($handle, $data);
   pg_query($database, "commit");
?>
```

### See Also

-   <span class="function">pg\_lo\_create</span>
-   <span class="function">pg\_lo\_open</span>

pg\_meta\_data
==============

Get meta data for table

### Description

<span class="type">array</span> <span
class="methodname">pg\_meta\_data</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$table_name`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$extended`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="function">pg\_meta\_data</span> returns table definition
for *table\_name* as an array.

### Parameters

`connection`  
PostgreSQL database connection resource.

`table_name`  
The name of the table.

`extended`  
Flag for returning extended meta data. Default to **`FALSE`**.

### Return Values

An <span class="type">array</span> of the table definition, or
**`FALSE`** on error.

### Examples

**Example \#1 Getting table metadata**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  $meta = pg_meta_data($dbconn, 'authors');
  if (is_array($meta)) {
      echo '<pre>';
      var_dump($meta);
      echo '</pre>';
  }
?>
```

The above example will output:

    array(3) {
    ["author"]=>
    array(5) {
      ["num"]=>
      int(1)
      ["type"]=>
      string(7) "varchar"
      ["len"]=>
      int(-1)
      ["not null"]=>
      bool(false)
      ["has default"]=>
      bool(false)
    }
    ["year"]=>
    array(5) {
      ["num"]=>
      int(2)
      ["type"]=>
      string(4) "int2"
      ["len"]=>
      int(2)
      ["not null"]=>
      bool(false)
      ["has default"]=>
      bool(false)
    }
    ["title"]=>
    array(5) {
      ["num"]=>
      int(3)
      ["type"]=>
      string(7) "varchar"
      ["len"]=>
      int(-1)
      ["not null"]=>
      bool(false)
      ["has default"]=>
      bool(false)
    }
    }

### Changelog

| Version | Description                                                                             |
|---------|-----------------------------------------------------------------------------------------|
| 5.6.0   | No longer experimental. Added "is enum" as default attribute. `extended` flag is added. |

### See Also

-   <span class="function">pg\_convert</span>

pg\_num\_fields
===============

Returns the number of fields in a result

### Description

<span class="type">int</span> <span
class="methodname">pg\_num\_fields</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
)

<span class="function">pg\_num\_fields</span> returns the number of
fields (columns) in a PostgreSQL result resource.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_numfields</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

### Return Values

The number of fields (columns) in the result. On error, -1 is returned.

### Examples

**Example \#1 <span class="function">pg\_num\_fields</span> example**

``` php
<?php
$result = pg_query($conn, "SELECT 1, 2");

$num = pg_num_fields($result);

echo $num . " field(s) returned.\n";
?>
```

The above example will output:

    2 field(s) returned.

### See Also

-   <span class="function">pg\_num\_rows</span>
-   <span class="function">pg\_affected\_rows</span>

pg\_num\_rows
=============

Returns the number of rows in a result

### Description

<span class="type">int</span> <span
class="methodname">pg\_num\_rows</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
)

<span class="function">pg\_num\_rows</span> will return the number of
rows in a PostgreSQL result resource.

> **Note**:
>
> This function used to be called <span
> class="function">pg\_numrows</span>.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

### Return Values

The number of rows in the result. On error, -1 is returned.

### Examples

**Example \#1 <span class="function">pg\_num\_rows</span> example**

``` php
<?php
$result = pg_query($conn, "SELECT 1");

$rows = pg_num_rows($result);

echo $rows . " row(s) returned.\n";
?>
```

The above example will output:

    1 row(s) returned.

### See Also

-   <span class="function">pg\_num\_fields</span>
-   <span class="function">pg\_affected\_rows</span>

pg\_options
===========

Get the options associated with the connection

### Description

<span class="type">string</span> <span
class="methodname">pg\_options</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_options</span> will return a string
containing the options specified on the given PostgreSQL `connection`
resource.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

A <span class="type">string</span> containing the `connection` options,
or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_options</span> example**

``` php
<?php
   $pgsql_conn = pg_connect("dbname=mark host=localhost");
   echo pg_options($pgsql_conn);
?>
```

### See Also

-   <span class="function">pg\_connect</span>

pg\_parameter\_status
=====================

Looks up a current parameter setting of the server

### Description

<span class="type">string</span> <span
class="methodname">pg\_parameter\_status</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$param_name`</span> )

Looks up a current parameter setting of the server.

Certain parameter values are reported by the server automatically at
connection startup or whenever their values change. <span
class="function">pg\_parameter\_status</span> can be used to interrogate
these settings. It returns the current value of a parameter if known, or
**`FALSE`** if the parameter is not known.

Parameters reported as of PostgreSQL 8.0 include *server\_version*,
*server\_encoding*, *client\_encoding*, *is\_superuser*,
*session\_authorization*, *DateStyle*, *TimeZone*, and
*integer\_datetimes*. (*server\_encoding*, *TimeZone*, and
*integer\_datetimes* were not reported by releases before 8.0.) Note
that *server\_version*, *server\_encoding* and *integer\_datetimes*
cannot change after PostgreSQL startup.

PostgreSQL 7.3 or lower servers do not report parameter settings, <span
class="function">pg\_parameter\_status</span> includes logic to obtain
values for *server\_version* and *client\_encoding* anyway. Applications
are encouraged to use <span
class="function">pg\_parameter\_status</span> rather than ad hoc code to
determine these values.

**Caution**

On a pre-7.4 PostgreSQL server, changing *client\_encoding* via *SET*
after connection startup will not be reflected by <span
class="function">pg\_parameter\_status</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`param_name`  
Possible `param_name` values include *server\_version*,
*server\_encoding*, *client\_encoding*, *is\_superuser*,
*session\_authorization*, *DateStyle*, *TimeZone*, and
*integer\_datetimes*.

### Return Values

A <span class="type">string</span> containing the value of the
parameter, **`FALSE`** on failure or invalid `param_name`.

### Examples

**Example \#1 <span class="function">pg\_parameter\_status</span>
example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  echo "Server encoding: ", pg_parameter_status($dbconn, "server_encoding");
?>
```

The above example will output:

    Server encoding: SQL_ASCII

pg\_pconnect
============

Open a persistent PostgreSQL connection

### Description

<span class="type">resource</span> <span
class="methodname">pg\_pconnect</span> ( <span class="methodparam"><span
class="type">string</span> `$connection_string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$connect_type`</span>
\] )

<span class="function">pg\_pconnect</span> opens a connection to a
PostgreSQL database. It returns a connection resource that is needed by
other PostgreSQL functions.

If a second call is made to <span class="function">pg\_pconnect</span>
with the same `connection_string` as an existing connection, the
existing connection will be returned unless you pass
**`PGSQL_CONNECT_FORCE_NEW`** as `connect_type`.

To enable persistent connection, the
<a href="/book/pgsql.html#" class="link">pgsql.allow_persistent</a>
`php.ini` directive must be set to "On" (which is the default). The
maximum number of persistent connection can be defined with the
<a href="/book/pgsql.html#" class="link">pgsql.max_persistent</a>
`php.ini` directive (defaults to -1 for no limit). The total number of
connections can be set with the
<a href="/book/pgsql.html#" class="link">pgsql.max_links</a> `php.ini`
directive.

<span class="function">pg\_close</span> will not close persistent links
generated by <span class="function">pg\_pconnect</span>.

### Parameters

`connection_string`  
The `connection_string` can be empty to use all default parameters, or
it can contain one or more parameter settings separated by whitespace.
Each parameter setting is in the form *keyword = value*. Spaces around
the equal sign are optional. To write an empty value or a value
containing spaces, surround it with single quotes, e.g., *keyword = 'a
value'*. Single quotes and backslashes within the value must be escaped
with a backslash, i.e., \\' and \\\\.

The currently recognized parameter keywords are: `host`, `hostaddr`,
`port`, `dbname`, `user`, `password`, `connect_timeout`, `options`,
`tty` (ignored), `sslmode`, `requiressl` (deprecated in favor of
`sslmode`), and `service`. Which of these arguments exist depends on
your PostgreSQL version.

`connect_type`  
If **`PGSQL_CONNECT_FORCE_NEW`** is passed, then a new connection is
created, even if the `connection_string` is identical to an existing
connection.

### Return Values

PostgreSQL connection resource on success, **`FALSE`** on failure.

### Examples

**Example \#1 Using <span class="function">pg\_pconnect</span>**

``` php
<?php
$dbconn = pg_pconnect("dbname=mary");
//connect to a database named "mary"

$dbconn2 = pg_pconnect("host=localhost port=5432 dbname=mary");
// connect to a database named "mary" on "localhost" at port "5432"

$dbconn3 = pg_pconnect("host=sheep port=5432 dbname=mary user=lamb password=foo");
//connect to a database named "mary" on the host "sheep" with a username and password

$conn_string = "host=sheep port=5432 dbname=test user=lamb password=bar";
$dbconn4 = pg_pconnect($conn_string);
//connect to a database named "test" on the host "sheep" with a username and password
?>
```

### See Also

-   <span class="function">pg\_connect</span>
-   <a href="/features/persistent-connections.html" class="link">Persistent Database Connections</a>

pg\_ping
========

Ping database connection

### Description

<span class="type">bool</span> <span class="methodname">pg\_ping</span>
(\[ <span class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_ping</span> pings a database connection and
tries to reconnect it if it is broken.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_ping</span> example**

``` php
<?php 
$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

if (!pg_ping($conn))
  die("Connection is broken\n");
?>
```

### See Also

-   <span class="function">pg\_connection\_status</span>
-   <span class="function">pg\_connection\_reset</span>

pg\_port
========

Return the port number associated with the connection

### Description

<span class="type">int</span> <span class="methodname">pg\_port</span>
(\[ <span class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_port</span> returns the port number that the
given PostgreSQL `connection` resource is connected to.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

An <span class="type">int</span> containing the port number of the
database server the `connection` is to, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_port</span> example**

``` php
<?php
$pgsql_conn = pg_connect("dbname=mark host=localhost");

if ($pgsql_conn) {
   print "Successfully connected to port: " . pg_port($pgsql_conn) . "<br/>\n";
} else {
   print pg_last_error($pgsql_conn);
   exit;
}
?>
```

pg\_prepare
===========

Submits a request to create a prepared statement with the given
parameters, and waits for completion

### Description

<span class="type">resource</span> <span
class="methodname">pg\_prepare</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$stmtname`</span> , <span
class="methodparam"><span class="type">string</span> `$query`</span> )

<span class="function">pg\_prepare</span> creates a prepared statement
for later execution with <span class="function">pg\_execute</span> or
<span class="function">pg\_send\_execute</span>. This feature allows
commands that will be used repeatedly to be parsed and planned just
once, rather than each time they are executed. <span
class="function">pg\_prepare</span> is supported only against PostgreSQL
7.4 or higher connections; it will fail when using earlier versions.

The function creates a prepared statement named `stmtname` from the
`query` string, which must contain a single SQL command. `stmtname` may
be "" to create an unnamed statement, in which case any pre-existing
unnamed statement is automatically replaced; otherwise it is an error if
the statement name is already defined in the current session. If any
parameters are used, they are referred to in the `query` as $1, $2, etc.

Prepared statements for use with <span
class="function">pg\_prepare</span> can also be created by executing SQL
*PREPARE* statements. (But <span class="function">pg\_prepare</span> is
more flexible since it does not require parameter types to be
pre-specified.) Also, although there is no PHP function for deleting a
prepared statement, the SQL *DEALLOCATE* statement can be used for that
purpose.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`stmtname`  
The name to give the prepared statement. Must be unique per-connection.
If "" is specified, then an unnamed statement is created, overwriting
any previously defined unnamed statement.

`query`  
The parameterized SQL statement. Must contain only a single statement.
(multiple statements separated by semi-colons are not allowed.) If any
parameters are used, they are referred to as $1, $2, etc.

### Return Values

A query result resource on success or **`FALSE`** on failure.

### Examples

**Example \#1 Using <span class="function">pg\_prepare</span>**

``` php
<?php
// Connect to a database named "mary"
$dbconn = pg_connect("dbname=mary");

// Prepare a query for execution
$result = pg_prepare($dbconn, "my_query", 'SELECT * FROM shops WHERE name = $1');

// Execute the prepared query.  Note that it is not necessary to escape
// the string "Joe's Widgets" in any way
$result = pg_execute($dbconn, "my_query", array("Joe's Widgets"));

// Execute the same prepared query, this time with a different parameter
$result = pg_execute($dbconn, "my_query", array("Clothes Clothes Clothes"));

?>
```

### See Also

-   <span class="function">pg\_execute</span>
-   <span class="function">pg\_send\_execute</span>

pg\_put\_line
=============

Send a NULL-terminated string to PostgreSQL backend

### Description

<span class="type">bool</span> <span
class="methodname">pg\_put\_line</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$data`</span> )

<span class="function">pg\_put\_line</span> sends a NULL-terminated
string to the PostgreSQL backend server. This is needed in conjunction
with PostgreSQL's *COPY FROM* command.

*COPY* is a high-speed data loading interface supported by PostgreSQL.
Data is passed in without being parsed, and in a single transaction.

An alternative to using raw <span class="function">pg\_put\_line</span>
commands is to use <span class="function">pg\_copy\_from</span>. This is
a far simpler interface.

> **Note**:
>
> The application must explicitly send the two characters "\\." on the
> last line to indicate to the backend that it has finished sending its
> data, before issuing <span class="function">pg\_end\_copy</span>.

**Warning**

Use of the <span class="function">pg\_put\_line</span> causes most large
object operations, including <span class="function">pg\_lo\_read</span>
and <span class="function">pg\_lo\_tell</span>, to subsequently fail.
You can use <span class="function">pg\_copy\_from</span> and <span
class="function">pg\_copy\_to</span> instead.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`data`  
A line of text to be sent directly to the PostgreSQL backend. A *NULL*
terminator is added automatically.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_put\_line</span> example**

``` php
<?php 
  $conn = pg_pconnect("dbname=foo");
  pg_query($conn, "create table bar (a int4, b char(16), d float8)");
  pg_query($conn, "copy bar from stdin");
  pg_put_line($conn, "3\thello world\t4.5\n");
  pg_put_line($conn, "4\tgoodbye world\t7.11\n");
  pg_put_line($conn, "\\.\n");
  pg_end_copy($conn);
?>
```

### See Also

-   <span class="function">pg\_end\_copy</span>

pg\_query\_params
=================

Submits a command to the server and waits for the result, with the
ability to pass parameters separately from the SQL command text

### Description

<span class="type">resource</span> <span
class="methodname">pg\_query\_params</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$query`</span> , <span
class="methodparam"><span class="type">array</span> `$params`</span> )

Submits a command to the server and waits for the result, with the
ability to pass parameters separately from the SQL command text.

<span class="function">pg\_query\_params</span> is like <span
class="function">pg\_query</span>, but offers additional functionality:
parameter values can be specified separately from the command string
proper. <span class="function">pg\_query\_params</span> is supported
only against PostgreSQL 7.4 or higher connections; it will fail when
using earlier versions.

If parameters are used, they are referred to in the `query` string as
$1, $2, etc. The same parameter may appear more than once in the
`query`; the same value will be used in that case. `params` specifies
the actual values of the parameters. A **`NULL`** value in this array
means the corresponding parameter is SQL *NULL*.

The primary advantage of <span class="function">pg\_query\_params</span>
over <span class="function">pg\_query</span> is that parameter values
may be separated from the `query` string, thus avoiding the need for
tedious and error-prone quoting and escaping. Unlike <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> allows at most one SQL command
in the given string. (There can be semicolons in it, but not more than
one nonempty command.)

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`query`  
The parameterized SQL statement. Must contain only a single statement.
(multiple statements separated by semi-colons are not allowed.) If any
parameters are used, they are referred to as $1, $2, etc.

User-supplied values should always be passed as parameters, not
interpolated into the query string, where they form possible
<a href="/security/database/sql-injection.html" class="link">SQL injection</a>
attack vectors and introduce bugs when handling data containing quotes.
If for some reason you cannot use a parameter, ensure that interpolated
values are
<a href="/book/pgsql.html#pg_escape_string" class="link">properly escaped</a>.

`params`  
An array of parameter values to substitute for the $1, $2, etc.
placeholders in the original prepared query string. The number of
elements in the array must match the number of placeholders.

Values intended for *bytea* fields are not supported as parameters. Use
<span class="function">pg\_escape\_bytea</span> instead, or use the
large object functions.

### Return Values

A query result resource on success or **`FALSE`** on failure.

### Examples

**Example \#1 Using <span class="function">pg\_query\_params</span>**

``` php
<?php
// Connect to a database named "mary"
$dbconn = pg_connect("dbname=mary");

// Find all shops named Joe's Widgets.  Note that it is not necessary to
// escape "Joe's Widgets"
$result = pg_query_params($dbconn, 'SELECT * FROM shops WHERE name = $1', array("Joe's Widgets"));

// Compare against just using pg_query
$str = pg_escape_string("Joe's Widgets");
$result = pg_query($dbconn, "SELECT * FROM shops WHERE name = '{$str}'");

?>
```

### See Also

-   <span class="function">pg\_query</span>

pg\_query
=========

Execute a query

### Description

<span class="type">resource</span> <span
class="methodname">pg\_query</span> (\[ <span class="methodparam"><span
class="type">resource</span> `$connection`</span> \], <span
class="methodparam"><span class="type">string</span> `$query`</span> )

<span class="function">pg\_query</span> executes the `query` on the
specified database `connection`. <span
class="function">pg\_query\_params</span> should be preferred in most
cases.

If an error occurs, and **`FALSE`** is returned, details of the error
can be retrieved using the <span class="function">pg\_last\_error</span>
function if the connection is valid.

> **Note**: <span class="simpara"> Although `connection` can be omitted,
> it is not recommended, since it can be the cause of hard to find bugs
> in scripts. </span>

> **Note**:
>
> This function used to be called <span
> class="function">pg\_exec</span>. <span
> class="function">pg\_exec</span> is still available for compatibility
> reasons, but users are encouraged to use the newer name.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`query`  
The SQL statement or statements to be executed. When multiple statements
are passed to the function, they are automatically executed as one
transaction, unless there are explicit BEGIN/COMMIT commands included in
the query string. However, using multiple transactions in one function
call is not recommended.

**Warning**
String interpolation of user-supplied data is extremely dangerous and is
likely to lead to
<a href="/security/database/sql-injection.html" class="link">SQL injection</a>
vulnerabilities. In most cases <span
class="function">pg\_query\_params</span> should be preferred, passing
user-supplied values as parameters rather than substituting them into
the query string.

Any user-supplied data substituted directly into a query string should
be
<a href="/book/pgsql.html#pg_escape_string" class="link">properly escaped</a>.

### Return Values

A query result resource on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_query</span> example**

``` php
<?php

$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

$result = pg_query($conn, "SELECT author, email FROM authors");
if (!$result) {
  echo "An error occurred.\n";
  exit;
}

while ($row = pg_fetch_row($result)) {
  echo "Author: $row[0]  E-mail: $row[1]";
  echo "<br />\n";
}
 
?>
```

**Example \#2 Using <span class="function">pg\_query</span> with
multiple statements**

``` php
<?php

$conn = pg_pconnect("dbname=publisher");

// these statements will be executed as one transaction

$query = "UPDATE authors SET author=UPPER(author) WHERE id=1;";
$query .= "UPDATE authors SET author=LOWER(author) WHERE id=2;";
$query .= "UPDATE authors SET author=NULL WHERE id=3;";

pg_query($conn, $query);

?>
```

### See Also

-   <span class="function">pg\_connect</span>
-   <span class="function">pg\_pconnect</span>
-   <span class="function">pg\_fetch\_array</span>
-   <span class="function">pg\_fetch\_object</span>
-   <span class="function">pg\_num\_rows</span>
-   <span class="function">pg\_affected\_rows</span>

pg\_result\_error\_field
========================

Returns an individual field of an error report

### Description

<span class="type">string</span> <span
class="methodname">pg\_result\_error\_field</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$fieldcode`</span> )

<span class="function">pg\_result\_error\_field</span> returns one of
the detailed error message fields associated with `result` resource. It
is only available against a PostgreSQL 7.4 or above server. The error
field is specified by the `fieldcode`.

Because <span class="function">pg\_query</span> and <span
class="function">pg\_query\_params</span> return **`FALSE`** if the
query fails, you must use <span class="function">pg\_send\_query</span>
and <span class="function">pg\_get\_result</span> to get the result
handle.

If you need to get additional error information from failed <span
class="function">pg\_query</span> queries, use <span
class="function">pg\_set\_error\_verbosity</span> and <span
class="function">pg\_last\_error</span> and then parse the result.

### Parameters

`result`  
A PostgreSQL query result resource from a previously executed statement.

`fieldcode`  
Possible `fieldcode` values are: **`PGSQL_DIAG_SEVERITY`**,
**`PGSQL_DIAG_SQLSTATE`**, **`PGSQL_DIAG_MESSAGE_PRIMARY`**,
**`PGSQL_DIAG_MESSAGE_DETAIL`**, **`PGSQL_DIAG_MESSAGE_HINT`**,
**`PGSQL_DIAG_STATEMENT_POSITION`**, **`PGSQL_DIAG_INTERNAL_POSITION`**
(PostgreSQL 8.0+ only), **`PGSQL_DIAG_INTERNAL_QUERY`** (PostgreSQL 8.0+
only), **`PGSQL_DIAG_CONTEXT`**, **`PGSQL_DIAG_SOURCE_FILE`**,
**`PGSQL_DIAG_SOURCE_LINE`** or **`PGSQL_DIAG_SOURCE_FUNCTION`**.

### Return Values

A <span class="type">string</span> containing the contents of the error
field, **`NULL`** if the field does not exist or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_result\_error\_field</span>
example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  if (!pg_connection_busy($dbconn)) {
      pg_send_query($dbconn, "select * from doesnotexist;");
  }
  
  $res1 = pg_get_result($dbconn);
  echo pg_result_error_field($res1, PGSQL_DIAG_SQLSTATE);
?>
```

### See Also

-   <span class="function">pg\_result\_error</span>

pg\_result\_error
=================

Get error message associated with result

### Description

<span class="type">string</span> <span
class="methodname">pg\_result\_error</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
)

<span class="function">pg\_result\_error</span> returns any error
message associated with the `result` resource. Therefore, the user has a
better chance of getting the correct error message than with <span
class="function">pg\_last\_error</span>.

The function <span class="function">pg\_result\_error\_field</span> can
give much greater detail on result errors than <span
class="function">pg\_result\_error</span>.

Because <span class="function">pg\_query</span> returns **`FALSE`** if
the query fails, you must use <span
class="function">pg\_send\_query</span> and <span
class="function">pg\_get\_result</span> to get the result handle.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

### Return Values

Returns a <span class="type">string</span>. Returns empty string if
there is no error. If there is an error associated with the `result`
parameter, returns **`FALSE`**.

### Examples

**Example \#1 <span class="function">pg\_result\_error</span> example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  if (!pg_connection_busy($dbconn)) {
      pg_send_query($dbconn, "select * from doesnotexist;");
  }
  
  $res1 = pg_get_result($dbconn);
  echo pg_result_error($res1);
?>
```

### See Also

-   <span class="function">pg\_result\_error\_field</span>
-   <span class="function">pg\_query</span>
-   <span class="function">pg\_send\_query</span>
-   <span class="function">pg\_get\_result</span>
-   <span class="function">pg\_last\_error</span>
-   <span class="function">pg\_last\_notice</span>

pg\_result\_seek
================

Set internal row offset in result resource

### Description

<span class="type">bool</span> <span
class="methodname">pg\_result\_seek</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
, <span class="methodparam"><span class="type">int</span>
`$offset`</span> )

<span class="function">pg\_result\_seek</span> sets the internal row
offset in a result resource.

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`offset`  
Row to move the internal offset to in the `result` resource. Rows are
numbered starting from zero.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_result\_seek</span> example**

``` php
<?php

// Connect to the database
$conn = pg_pconnect("dbname=publisher");

// Execute a query
$result = pg_query($conn, "SELECT author, email FROM authors");

// Seek to the 3rd row (assuming there are 3 rows)
pg_result_seek($result, 2);

// Fetch the 3rd row
$row = pg_fetch_row($result);
 
?>
```

### See Also

-   <span class="function">pg\_fetch\_row</span>
-   <span class="function">pg\_fetch\_assoc</span>
-   <span class="function">pg\_fetch\_array</span>
-   <span class="function">pg\_fetch\_object</span>
-   <span class="function">pg\_fetch\_result</span>

pg\_result\_status
==================

Get status of query result

### Description

<span class="type">mixed</span> <span
class="methodname">pg\_result\_status</span> ( <span
class="methodparam"><span class="type">resource</span> `$result`</span>
\[, <span class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = PGSQL\_STATUS\_LONG</span></span> \] )

<span class="function">pg\_result\_status</span> returns the status of a
result resource, or the PostgreSQL command completion tag associated
with the result

### Parameters

`result`  
PostgreSQL query result resource, returned by <span
class="function">pg\_query</span>, <span
class="function">pg\_query\_params</span> or <span
class="function">pg\_execute</span> (among others).

`type`  
Either **`PGSQL_STATUS_LONG`** to return the numeric status of the
`result`, or **`PGSQL_STATUS_STRING`** to return the command tag of the
`result`. If not specified, **`PGSQL_STATUS_LONG`** is the default.

### Return Values

Possible return values are **`PGSQL_EMPTY_QUERY`**,
**`PGSQL_COMMAND_OK`**, **`PGSQL_TUPLES_OK`**, **`PGSQL_COPY_OUT`**,
**`PGSQL_COPY_IN`**, **`PGSQL_BAD_RESPONSE`**,
**`PGSQL_NONFATAL_ERROR`** and **`PGSQL_FATAL_ERROR`** if
**`PGSQL_STATUS_LONG`** is specified. Otherwise, a <span
class="type">string</span> containing the PostgreSQL command tag is
returned.

### Examples

**Example \#1 <span class="function">pg\_result\_status</span> example**

``` php
<?php

// Connect to the database
$conn = pg_pconnect("dbname=publisher");

// Execute a COPY
$result = pg_query($conn, "COPY authors FROM STDIN;");

// Get the result status
$status = pg_result_status($result);

// Determine status
if ($status == PGSQL_COPY_IN)
   echo "Copy began.";
else
   echo "Copy failed.";
 
?>
```

The above example will output:

    Copy began.

### See Also

-   <span class="function">pg\_connection\_status</span>

pg\_select
==========

Select records

### Description

<span class="type">mixed</span> <span
class="methodname">pg\_select</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> , <span class="methodparam"><span
class="type">array</span> `$assoc_array`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = PGSQL\_DML\_EXEC</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$result_type`<span
class="initializer"> = PGSQL\_ASSOC</span></span> \]\] )

<span class="function">pg\_select</span> selects records specified by
*assoc\_array* which has *field=\>value*. For a successful query, it
returns an array containing all records and fields that match the
condition specified by *assoc\_array*.

If *options* is specified, <span class="function">pg\_convert</span> is
applied to *assoc\_array* with the specified flags.

By default <span class="function">pg\_select</span> passes raw values.
Values must be escaped or PGSQL\_DML\_ESCAPE option must be specified.
PGSQL\_DML\_ESCAPE quotes and escapes parameters/identifiers. Therefore,
table/column names became case sensitive.

Note that neither escape nor prepared query can protect LIKE query,
JSON, Array, Regex, etc. These parameters should be handled according to
their contexts. i.e. Escape/validate values.

### Parameters

`connection`  
PostgreSQL database connection resource.

`table_name`  
Name of the table from which to select rows.

`assoc_array`  
An <span class="type">array</span> whose keys are field names in the
table `table_name`, and whose values are the conditions that a row must
meet to be retrieved.

`options`  
Any number of **`PGSQL_CONV_FORCE_NULL`**, **`PGSQL_DML_NO_CONV`**,
**`PGSQL_DML_ESCAPE`**, **`PGSQL_DML_EXEC`**, **`PGSQL_DML_ASYNC`** or
**`PGSQL_DML_STRING`** combined. If **`PGSQL_DML_STRING`** is part of
the `options` then query string is returned. When
**`PGSQL_DML_NO_CONV`** or **`PGSQL_DML_ESCAPE`** is set, it does not
call <span class="function">pg\_convert</span> internally.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Returns <span
class="type">string</span> if **`PGSQL_DML_STRING`** is passed via
`options`.

### Examples

**Example \#1 <span class="function">pg\_select</span> example**

``` php
<?php 
  $db = pg_connect('dbname=foo');
  // This is safe somewhat, since all values are escaped.
  // However PostgreSQL supports JSON/Array. These are not
  // safe by neither escape nor prepared query.
  $rec = pg_select($db, 'post_log', $_POST, PG_DML_ESCAPE);
  if ($rec) {
      echo "Records selected\n";
      var_dump($rec);
  } else {
      echo "User must have sent wrong inputs\n";
  }
?>
```

### Changelog

| Version      | Description                                                                                                             |
|--------------|-------------------------------------------------------------------------------------------------------------------------|
| 7.1.0        | The `result_type` parameter was added.                                                                                  |
| 5.6.0        | No longer experimental. Added **`PGSQL_DML_ESCAPE`** constant, **`TRUE`**/**`FALSE`** and **`NULL`** data type support. |
| 5.5.3/5.4.19 | Direct SQL injection to `table_name` and Indirect SQL injection to identifiers are fixed.                               |

### See Also

-   <span class="function">pg\_convert</span>

pg\_send\_execute
=================

Sends a request to execute a prepared statement with given parameters,
without waiting for the result(s)

### Description

<span class="type">bool</span> <span
class="methodname">pg\_send\_execute</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$stmtname`</span> , <span
class="methodparam"><span class="type">array</span> `$params`</span> )

Sends a request to execute a prepared statement with given parameters,
without waiting for the result(s).

This is similar to <span
class="function">pg\_send\_query\_params</span>, but the command to be
executed is specified by naming a previously-prepared statement, instead
of giving a query string. The function's parameters are handled
identically to <span class="function">pg\_execute</span>. Like <span
class="function">pg\_execute</span>, it will not work on pre-7.4
versions of PostgreSQL.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`stmtname`  
The name of the prepared statement to execute. if "" is specified, then
the unnamed statement is executed. The name must have been previously
prepared using <span class="function">pg\_prepare</span>, <span
class="function">pg\_send\_prepare</span> or a *PREPARE* SQL command.

`params`  
An array of parameter values to substitute for the $1, $2, etc.
placeholders in the original prepared query string. The number of
elements in the array must match the number of placeholders.

### Return Values

Returns **`TRUE`** on success, **`FALSE`** on failure. Use <span
class="function">pg\_get\_result</span> to determine the query result.

### Examples

**Example \#1 Using <span class="function">pg\_send\_execute</span>**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  // Prepare a query for execution
  if (!pg_connection_busy($dbconn)) {
    pg_send_prepare($dbconn, "my_query", 'SELECT * FROM shops WHERE name = $1');
    $res1 = pg_get_result($dbconn);
  }

  // Execute the prepared query.  Note that it is not necessary to escape
  // the string "Joe's Widgets" in any way
  if (!pg_connection_busy($dbconn)) {
    pg_send_execute($dbconn, "my_query", array("Joe's Widgets"));
    $res2 = pg_get_result($dbconn);
  }
  
  // Execute the same prepared query, this time with a different parameter
  if (!pg_connection_busy($dbconn)) {
    pg_send_execute($dbconn, "my_query", array("Clothes Clothes Clothes"));
    $res3 = pg_get_result($dbconn);
  }
  
?>
```

### See Also

-   <span class="function">pg\_prepare</span>
-   <span class="function">pg\_send\_prepare</span>
-   <span class="function">pg\_execute</span>

pg\_send\_prepare
=================

Sends a request to create a prepared statement with the given
parameters, without waiting for completion

### Description

<span class="type">bool</span> <span
class="methodname">pg\_send\_prepare</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$stmtname`</span> , <span
class="methodparam"><span class="type">string</span> `$query`</span> )

Sends a request to create a prepared statement with the given
parameters, without waiting for completion.

This is an asynchronous version of <span
class="function">pg\_prepare</span>: it returns **`TRUE`** if it was
able to dispatch the request, and **`FALSE`** if not. After a successful
call, call <span class="function">pg\_get\_result</span> to determine
whether the server successfully created the prepared statement. The
function's parameters are handled identically to <span
class="function">pg\_prepare</span>. Like <span
class="function">pg\_prepare</span>, it will not work on pre-7.4
versions of PostgreSQL.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`stmtname`  
The name to give the prepared statement. Must be unique per-connection.
If "" is specified, then an unnamed statement is created, overwriting
any previously defined unnamed statement.

`query`  
The parameterized SQL statement. Must contain only a single statement.
(multiple statements separated by semi-colons are not allowed.) If any
parameters are used, they are referred to as $1, $2, etc.

### Return Values

Returns **`TRUE`** on success, **`FALSE`** on failure. Use <span
class="function">pg\_get\_result</span> to determine the query result.

### Examples

**Example \#1 Using <span class="function">pg\_send\_prepare</span>**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  // Prepare a query for execution
  if (!pg_connection_busy($dbconn)) {
    pg_send_prepare($dbconn, "my_query", 'SELECT * FROM shops WHERE name = $1');
    $res1 = pg_get_result($dbconn);
  }

  // Execute the prepared query.  Note that it is not necessary to escape
  // the string "Joe's Widgets" in any way
  if (!pg_connection_busy($dbconn)) {
    pg_send_execute($dbconn, "my_query", array("Joe's Widgets"));
    $res2 = pg_get_result($dbconn);
  }
  
  // Execute the same prepared query, this time with a different parameter
  if (!pg_connection_busy($dbconn)) {
    pg_send_execute($dbconn, "my_query", array("Clothes Clothes Clothes"));
    $res3 = pg_get_result($dbconn);
  }
  
?>
```

### See Also

-   <span class="function">pg\_connect</span>
-   <span class="function">pg\_pconnect</span>
-   <span class="function">pg\_execute</span>
-   <span class="function">pg\_send\_execute</span>
-   <span class="function">pg\_send\_query\_params</span>

pg\_send\_query\_params
=======================

Submits a command and separate parameters to the server without waiting
for the result(s)

### Description

<span class="type">bool</span> <span
class="methodname">pg\_send\_query\_params</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$query`</span> , <span
class="methodparam"><span class="type">array</span> `$params`</span> )

Submits a command and separate parameters to the server without waiting
for the result(s).

This is equivalent to <span class="function">pg\_send\_query</span>
except that query parameters can be specified separately from the
`query` string. The function's parameters are handled identically to
<span class="function">pg\_query\_params</span>. Like <span
class="function">pg\_query\_params</span>, it will not work on pre-7.4
PostgreSQL connections, and it allows only one command in the query
string.

### Parameters

`connection`  
PostgreSQL database connection resource.

`query`  
The parameterized SQL statement. Must contain only a single statement.
(multiple statements separated by semi-colons are not allowed.) If any
parameters are used, they are referred to as $1, $2, etc.

`params`  
An array of parameter values to substitute for the $1, $2, etc.
placeholders in the original prepared query string. The number of
elements in the array must match the number of placeholders.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

Use <span class="function">pg\_get\_result</span> to determine the query
result.

### Examples

**Example \#1 Using <span
class="function">pg\_send\_query\_params</span>**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  // Using parameters.  Note that it is not necessary to quote or escape
  // the parameter.
  pg_send_query_params($dbconn, 'select count(*) from authors where city = $1', array('Perth'));
  
  // Compare against basic pg_send_query usage
  $str = pg_escape_string('Perth');
  pg_send_query($dbconn, "select count(*) from authors where city = '${str}'");
?>
```

### See Also

-   <span class="function">pg\_send\_query</span>

pg\_send\_query
===============

Sends asynchronous query

### Description

<span class="type">bool</span> <span
class="methodname">pg\_send\_query</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$query`</span> )

<span class="function">pg\_send\_query</span> sends a query or queries
asynchronously to the `connection`. Unlike <span
class="function">pg\_query</span>, it can send multiple queries at once
to PostgreSQL and get the results one by one using <span
class="function">pg\_get\_result</span>.

Script execution is not blocked while the queries are executing. Use
<span class="function">pg\_connection\_busy</span> to check if the
connection is busy (i.e. the query is executing). Queries may be
cancelled using <span class="function">pg\_cancel\_query</span>.

Although the user can send multiple queries at once, multiple queries
cannot be sent over a busy connection. If a query is sent while the
connection is busy, it waits until the last query is finished and
discards all its results.

### Parameters

`connection`  
PostgreSQL database connection resource.

`query`  
The SQL statement or statements to be executed.

Data inside the query should be
<a href="/book/pgsql.html#pg_escape_string" class="link">properly escaped</a>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

Use <span class="function">pg\_get\_result</span> to determine the query
result.

### Examples

**Example \#1 <span class="function">pg\_send\_query</span> example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  if (!pg_connection_busy($dbconn)) {
      pg_send_query($dbconn, "select * from authors; select count(*) from authors;");
  }
  
  $res1 = pg_get_result($dbconn);
  echo "First call to pg_get_result(): $res1\n";
  $rows1 = pg_num_rows($res1);
  echo "$res1 has $rows1 records\n\n";
  
  $res2 = pg_get_result($dbconn);
  echo "Second call to pg_get_result(): $res2\n";
  $rows2 = pg_num_rows($res2);
  echo "$res2 has $rows2 records\n";
?>
```

The above example will output:

    First call to pg_get_result(): Resource id #3
    Resource id #3 has 3 records

    Second call to pg_get_result(): Resource id #4
    Resource id #4 has 1 records

### See Also

-   <span class="function">pg\_query</span>
-   <span class="function">pg\_cancel\_query</span>
-   <span class="function">pg\_get\_result</span>
-   <span class="function">pg\_connection\_busy</span>

pg\_set\_client\_encoding
=========================

Set the client encoding

### Description

<span class="type">int</span> <span
class="methodname">pg\_set\_client\_encoding</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">string</span> `$encoding`</span> )

<span class="function">pg\_set\_client\_encoding</span> sets the client
encoding and returns 0 if success or -1 if error.

PostgreSQL will automatically convert data in the backend database
encoding into the frontend encoding.

> **Note**:
>
> The function used to be called <span
> class="function">pg\_setclientencoding</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`encoding`  
The required client encoding. One of *SQL\_ASCII*, *EUC\_JP*, *EUC\_CN*,
*EUC\_KR*, *EUC\_TW*, *UNICODE*, *MULE\_INTERNAL*, *LATINX* (X=1...9),
*KOI8*, *WIN*, *ALT*, *SJIS*, *BIG5* or *WIN1250*.

The exact list of available encodings depends on your PostgreSQL
version, so check your PostgreSQL manual for a more specific list.

### Return Values

Returns 0 on success or -1 on error.

### Examples

**Example \#1 <span class="function">pg\_set\_client\_encoding</span>
example**

``` php
<?php

$conn = pg_pconnect("dbname=publisher");
if (!$conn) {
  echo "An error occurred.\n";
  exit;
}

// Set the client encoding to UNICODE.  Data will be automatically
// converted from the backend encoding to the frontend.
pg_set_client_encoding($conn, "UNICODE");

$result = pg_query($conn, "SELECT author, email FROM authors");
if (!$result) {
  echo "An error occurred.\n";
  exit;
}

// Write out UTF-8 data
while ($row = pg_fetch_row($result)) {
  echo "Author: $row[0]  E-mail: $row[1]";
  echo "<br />\n";
}
 
?>
```

### See Also

-   <span class="function">pg\_client\_encoding</span>

pg\_set\_error\_verbosity
=========================

Determines the verbosity of messages returned by <span
class="function">pg\_last\_error</span> and <span
class="function">pg\_result\_error</span>

### Description

<span class="type">int</span> <span
class="methodname">pg\_set\_error\_verbosity</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \], <span class="methodparam"><span
class="type">int</span> `$verbosity`</span> )

Determines the verbosity of messages returned by <span
class="function">pg\_last\_error</span> and <span
class="function">pg\_result\_error</span>.

<span class="function">pg\_set\_error\_verbosity</span> sets the
verbosity mode, returning the connection's previous setting. In
**`PGSQL_ERRORS_TERSE`** mode, returned messages include severity,
primary text, and position only; this will normally fit on a single
line. The default mode (**`PGSQL_ERRORS_DEFAULT`**) produces messages
that include the above plus any detail, hint, or context fields (these
may span multiple lines). The **`PGSQL_ERRORS_VERBOSE`** mode includes
all available fields. Changing the verbosity does not affect the
messages available from already-existing result objects, only
subsequently-created ones.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

`verbosity`  
The required verbosity: **`PGSQL_ERRORS_TERSE`**,
**`PGSQL_ERRORS_DEFAULT`** or **`PGSQL_ERRORS_VERBOSE`**.

### Return Values

The previous verbosity level: **`PGSQL_ERRORS_TERSE`**,
**`PGSQL_ERRORS_DEFAULT`** or **`PGSQL_ERRORS_VERBOSE`**.

### Examples

**Example \#1 <span class="function">pg\_set\_error\_verbosity</span>
example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");

  if (!pg_connection_busy($dbconn)) {
      pg_send_query($dbconn, "select * from doesnotexist;");
  }
  
  pg_set_error_verbosity($dbconn, PGSQL_ERRORS_VERBOSE);
  $res1 = pg_get_result($dbconn);
  echo pg_result_error($res1);
?>
```

### See Also

-   <span class="function">pg\_last\_error</span>
-   <span class="function">pg\_result\_error</span>

pg\_socket
==========

Get a read only handle to the socket underlying a PostgreSQL connection

### Description

<span class="type">resource</span> <span
class="methodname">pg\_socket</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> )

<span class="function">pg\_socket</span> returns a read only <span
class="type">resource</span> corresponding to the socket underlying the
given PostgreSQL connection.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

A socket resource on success or **`FALSE`** on failure.

pg\_trace
=========

Enable tracing a PostgreSQL connection

### Description

<span class="type">bool</span> <span class="methodname">pg\_trace</span>
( <span class="methodparam"><span class="type">string</span>
`$pathname`</span> \[, <span class="methodparam"><span
class="type">string</span> `$mode`<span class="initializer"> =
"w"</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$connection`</span> \]\] )

<span class="function">pg\_trace</span> enables tracing of the
PostgreSQL frontend/backend communication to a file. To fully understand
the results, one needs to be familiar with the internals of PostgreSQL
communication protocol.

For those who are not, it can still be useful for tracing errors in
queries sent to the server, you could do for example **grep '^To
backend' trace.log** and see what queries actually were sent to the
PostgreSQL server. For more information, refer to the
<a href="http://www.postgresql.org/docs/current/interactive/" class="link external">» PostgreSQL Documentation</a>.

### Parameters

`pathname`  
The full path and file name of the file in which to write the trace log.
Same as in <span class="function">fopen</span>.

`mode`  
An optional file access mode, same as for <span
class="function">fopen</span>.

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pg\_trace</span> example**

``` php
<?php
$pgsql_conn = pg_connect("dbname=mark host=localhost");

if ($pgsql_conn) {
   pg_trace('/tmp/trace.log', 'w', $pgsql_conn);
   pg_query("SELECT 1");
   pg_untrace($pgsql_conn);
   // Now /tmp/trace.log will contain backend communication
} else {
   print pg_last_error($pgsql_conn);
   exit;
}
?>
```

### See Also

-   <span class="function">fopen</span>
-   <span class="function">pg\_untrace</span>

pg\_transaction\_status
=======================

Returns the current in-transaction status of the server

### Description

<span class="type">int</span> <span
class="methodname">pg\_transaction\_status</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

Returns the current in-transaction status of the server.

**Caution**

<span class="function">pg\_transaction\_status</span> will give
incorrect results when using a PostgreSQL 7.3 server that has the
parameter *autocommit* set to off. The server-side autocommit feature
has been deprecated and does not exist in later server versions.

### Parameters

`connection`  
PostgreSQL database connection resource.

### Return Values

The status can be **`PGSQL_TRANSACTION_IDLE`** (currently idle),
**`PGSQL_TRANSACTION_ACTIVE`** (a command is in progress),
**`PGSQL_TRANSACTION_INTRANS`** (idle, in a valid transaction block), or
**`PGSQL_TRANSACTION_INERROR`** (idle, in a failed transaction block).
**`PGSQL_TRANSACTION_UNKNOWN`** is reported if the connection is bad.
**`PGSQL_TRANSACTION_ACTIVE`** is reported only when a query has been
sent to the server and not yet completed.

### Examples

**Example \#1 <span class="function">pg\_transaction\_status</span>
example**

``` php
<?php
  $dbconn = pg_connect("dbname=publisher") or die("Could not connect");
  $stat = pg_transaction_status($dbconn);
  if ($stat === PGSQL_TRANSACTION_UNKNOWN) {
      echo 'Connection is bad';
  } else if ($stat === PGSQL_TRANSACTION_IDLE) {
      echo 'Connection is currently idle';
  } else {
      echo 'Connection is in a transaction state';
  }    
?>
```

pg\_tty
=======

Return the TTY name associated with the connection

### Description

<span class="type">string</span> <span class="methodname">pg\_tty</span>
(\[ <span class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_tty</span> returns the TTY name that server
side debugging output is sent to on the given PostgreSQL `connection`
resource.

> **Note**:
>
> <span class="function">pg\_tty</span> is obsolete, since the server no
> longer pays attention to the TTY setting, but the function remains for
> backwards compatibility.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

A <span class="type">string</span> containing the debug TTY of the
`connection`, or **`FALSE`** on error.

### Examples

**Example \#1 <span class="function">pg\_tty</span> example**

``` php
<?php
$pgsql_conn = pg_connect("dbname=mark host=localhost");

if ($pgsql_conn) {
   print "Server debug TTY is: " . pg_tty($pgsql_conn) . "<br/>\n";
} else {
   print pg_last_error($pgsql_conn);
   exit;
}
?>
```

pg\_unescape\_bytea
===================

Unescape binary for bytea type

### Description

<span class="type">string</span> <span
class="methodname">pg\_unescape\_bytea</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

<span class="function">pg\_unescape\_bytea</span> unescapes PostgreSQL
bytea data values. It returns the unescaped string, possibly containing
binary data.

> **Note**:
>
> When you *SELECT* a bytea type, PostgreSQL returns octal byte values
> prefixed with '\\' (e.g. \\032). Users are supposed to convert back to
> binary format manually.
>
> This function requires PostgreSQL 7.2 or later. With PostgreSQL 7.2.0
> and 7.2.1, bytea values must be cast when you enable multi-byte
> support. i.e. *INSERT INTO test\_table (image) VALUES
> ('$image\_escaped'::bytea);* PostgreSQL 7.2.2 or later does not need a
> cast. The exception is when the client and backend character encoding
> does not match, and there may be multi-byte stream error. User must
> then cast to bytea to avoid this error.

### Parameters

`data`  
A <span class="type">string</span> containing PostgreSQL bytea data to
be converted into a PHP binary string.

### Return Values

A <span class="type">string</span> containing the unescaped data.

### Examples

**Example \#1 <span class="function">pg\_unescape\_bytea</span>
example**

``` php
<?php 
  // Connect to the database
  $dbconn = pg_connect('dbname=foo');
  
  // Get the bytea data
  $res = pg_query("SELECT data FROM gallery WHERE name='Pine trees'");  
  $raw = pg_fetch_result($res, 'data');
  
  // Convert to binary and send to the browser
  header('Content-type: image/jpeg');
  echo pg_unescape_bytea($raw);
?>
```

### Changelog

| Version | Description                                         |
|---------|-----------------------------------------------------|
| 5.5.1   | A warning is thrown if the input string is invalid. |

### See Also

-   <span class="function">pg\_escape\_bytea</span>
-   <span class="function">pg\_escape\_string</span>

pg\_untrace
===========

Disable tracing of a PostgreSQL connection

### Description

<span class="type">bool</span> <span
class="methodname">pg\_untrace</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

Stop tracing started by <span class="function">pg\_trace</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

Always returns **`TRUE`**.

### Examples

**Example \#1 <span class="function">pg\_untrace</span> example**

``` php
<?php
$pgsql_conn = pg_connect("dbname=mark host=localhost");

if ($pgsql_conn) {
   pg_trace('/tmp/trace.log', 'w', $pgsql_conn);
   pg_query("SELECT 1");
   pg_untrace($pgsql_conn);
   // Now tracing of backend communication is disabled
} else {
   print pg_last_error($pgsql_conn);
   exit;
}
?>
```

### See Also

-   <span class="function">pg\_trace</span>

pg\_update
==========

Update table

### Description

<span class="type">mixed</span> <span
class="methodname">pg\_update</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> , <span class="methodparam"><span
class="type">array</span> `$data`</span> , <span
class="methodparam"><span class="type">array</span> `$condition`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = PGSQL\_DML\_EXEC</span></span> \]
)

<span class="function">pg\_update</span> updates records that matches
*condition* with *data*. If *options* is specified, <span
class="function">pg\_convert</span> is applied to *data* with specified
options.

<span class="function">pg\_update</span> updates records specified by
*assoc\_array* which has *field=\>value*.

If *options* is specified, <span class="function">pg\_convert</span> is
applied to *assoc\_array* with the specified flags.

By default <span class="function">pg\_update</span> passes raw values.
Values must be escaped or PGSQL\_DML\_ESCAPE option must be specified.
PGSQL\_DML\_ESCAPE quotes and escapes parameters/identifiers. Therefore,
table/column names became case sensitive.

Note that neither escape nor prepared query can protect LIKE query,
JSON, Array, Regex, etc. These parameters should be handled according to
their contexts. i.e. Escape/validate values.

### Parameters

`connection`  
PostgreSQL database connection resource.

`table_name`  
Name of the table into which to update rows.

`data`  
An <span class="type">array</span> whose keys are field names in the
table `table_name`, and whose values are what matched rows are to be
updated to.

`condition`  
An <span class="type">array</span> whose keys are field names in the
table `table_name`, and whose values are the conditions that a row must
meet to be updated.

`options`  
Any number of **`PGSQL_CONV_FORCE_NULL`**, **`PGSQL_DML_NO_CONV`**,
**`PGSQL_DML_ESCAPE`**, **`PGSQL_DML_EXEC`**, **`PGSQL_DML_ASYNC`** or
**`PGSQL_DML_STRING`** combined. If **`PGSQL_DML_STRING`** is part of
the `options` then query string is returned. When
**`PGSQL_DML_NO_CONV`** or **`PGSQL_DML_ESCAPE`** is set, it does not
call <span class="function">pg\_convert</span> internally.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. Returns <span
class="type">string</span> if **`PGSQL_DML_STRING`** is passed via
`options`.

### Examples

**Example \#1 <span class="function">pg\_update</span> example**

``` php
<?php 
  $db = pg_connect('dbname=foo');
  $data = array('field1'=>'AA', 'field2'=>'BB');
  // This is safe somewhat, since all values are escaped.
  // However PostgreSQL supports JSON/Array. These are not
  // safe by neither escape nor prepared query.
  $res = pg_update($db, 'post_log', $_POST, $data);
  if ($res) {
      echo "Data is updated: $res\n";
  } else {
      echo "User must have sent wrong inputs\n";
  }
?>
```

### Changelog

| Version      | Description                                                                                                             |
|--------------|-------------------------------------------------------------------------------------------------------------------------|
| 5.6.0        | No longer experimental. Added **`PGSQL_DML_ESCAPE`** constant, **`TRUE`**/**`FALSE`** and **`NULL`** data type support. |
| 5.5.3/5.4.19 | Direct SQL injection to `table_name` and Indirect SQL injection to identifiers are fixed.                               |

### See Also

-   <span class="function">pg\_convert</span>

pg\_version
===========

Returns an array with client, protocol and server version (when
available)

### Description

<span class="type">array</span> <span
class="methodname">pg\_version</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \] )

<span class="function">pg\_version</span> returns an array with the
client, protocol and server version. Protocol and server versions are
only available if PHP was compiled with PostgreSQL 7.4 or later.

For more detailed server information, use <span
class="function">pg\_parameter\_status</span>.

### Parameters

`connection`  
PostgreSQL database connection resource. When `connection` is not
present, the default connection is used. The default connection is the
last connection made by <span class="function">pg\_connect</span> or
<span class="function">pg\_pconnect</span>.

### Return Values

Returns an array with *client*, *protocol* and *server* keys and values
(if available). Returns **`FALSE`** on error or invalid connection.

### Examples

**Example \#1 <span class="function">pg\_version</span> example**

``` php
<?php
  $dbconn = pg_connect("host=localhost port=5432 dbname=mary")
     or die("Could not connect");
     
  $v = pg_version($dbconn);
  
  echo $v['client'];
?>
```

The above example will output:

    7.4

### See Also

-   <span class="function">pg\_parameter\_status</span>

**Table of Contents**

-   [pg\_affected\_rows](/book/pgsql.html#pg_affected_rows) — Returns
    number of affected records (tuples)
-   [pg\_cancel\_query](/book/pgsql.html#pg_cancel_query) — Cancel an
    asynchronous query
-   [pg\_client\_encoding](/book/pgsql.html#pg_client_encoding) — Gets
    the client encoding
-   [pg\_close](/book/pgsql.html#pg_close) — Closes a PostgreSQL
    connection
-   [pg\_connect\_poll](/book/pgsql.html#pg_connect_poll) — Poll the
    status of an in-progress asynchronous PostgreSQL connection attempt
-   [pg\_connect](/book/pgsql.html#pg_connect) — Open a PostgreSQL
    connection
-   [pg\_connection\_busy](/book/pgsql.html#pg_connection_busy) — Get
    connection is busy or not
-   [pg\_connection\_reset](/book/pgsql.html#pg_connection_reset) —
    Reset connection (reconnect)
-   [pg\_connection\_status](/book/pgsql.html#pg_connection_status) —
    Get connection status
-   [pg\_consume\_input](/book/pgsql.html#pg_consume_input) — Reads
    input on the connection
-   [pg\_convert](/book/pgsql.html#pg_convert) — Convert associative
    array values into forms suitable for SQL statements
-   [pg\_copy\_from](/book/pgsql.html#pg_copy_from) — Insert records
    into a table from an array
-   [pg\_copy\_to](/book/pgsql.html#pg_copy_to) — Copy a table to an
    array
-   [pg\_dbname](/book/pgsql.html#pg_dbname) — Get the database name
-   [pg\_delete](/book/pgsql.html#pg_delete) — Deletes records
-   [pg\_end\_copy](/book/pgsql.html#pg_end_copy) — Sync with PostgreSQL
    backend
-   [pg\_escape\_bytea](/book/pgsql.html#pg_escape_bytea) — Escape a
    string for insertion into a bytea field
-   [pg\_escape\_identifier](/book/pgsql.html#pg_escape_identifier) —
    Escape a identifier for insertion into a text field
-   [pg\_escape\_literal](/book/pgsql.html#pg_escape_literal) — Escape a
    literal for insertion into a text field
-   [pg\_escape\_string](/book/pgsql.html#pg_escape_string) — Escape a
    string for query
-   [pg\_execute](/book/pgsql.html#pg_execute) — Sends a request to
    execute a prepared statement with given parameters, and waits for
    the result
-   [pg\_fetch\_all\_columns](/book/pgsql.html#pg_fetch_all_columns) —
    Fetches all rows in a particular result column as an array
-   [pg\_fetch\_all](/book/pgsql.html#pg_fetch_all) — Fetches all rows
    from a result as an array
-   [pg\_fetch\_array](/book/pgsql.html#pg_fetch_array) — Fetch a row as
    an array
-   [pg\_fetch\_assoc](/book/pgsql.html#pg_fetch_assoc) — Fetch a row as
    an associative array
-   [pg\_fetch\_object](/book/pgsql.html#pg_fetch_object) — Fetch a row
    as an object
-   [pg\_fetch\_result](/book/pgsql.html#pg_fetch_result) — Returns
    values from a result resource
-   [pg\_fetch\_row](/book/pgsql.html#pg_fetch_row) — Get a row as an
    enumerated array
-   [pg\_field\_is\_null](/book/pgsql.html#pg_field_is_null) — Test if a
    field is SQL NULL
-   [pg\_field\_name](/book/pgsql.html#pg_field_name) — Returns the name
    of a field
-   [pg\_field\_num](/book/pgsql.html#pg_field_num) — Returns the field
    number of the named field
-   [pg\_field\_prtlen](/book/pgsql.html#pg_field_prtlen) — Returns the
    printed length
-   [pg\_field\_size](/book/pgsql.html#pg_field_size) — Returns the
    internal storage size of the named field
-   [pg\_field\_table](/book/pgsql.html#pg_field_table) — Returns the
    name or oid of the tables field
-   [pg\_field\_type\_oid](/book/pgsql.html#pg_field_type_oid) — Returns
    the type ID (OID) for the corresponding field number
-   [pg\_field\_type](/book/pgsql.html#pg_field_type) — Returns the type
    name for the corresponding field number
-   [pg\_flush](/book/pgsql.html#pg_flush) — Flush outbound query data
    on the connection
-   [pg\_free\_result](/book/pgsql.html#pg_free_result) — Free result
    memory
-   [pg\_get\_notify](/book/pgsql.html#pg_get_notify) — Gets SQL NOTIFY
    message
-   [pg\_get\_pid](/book/pgsql.html#pg_get_pid) — Gets the backend's
    process ID
-   [pg\_get\_result](/book/pgsql.html#pg_get_result) — Get asynchronous
    query result
-   [pg\_host](/book/pgsql.html#pg_host) — Returns the host name
    associated with the connection
-   [pg\_insert](/book/pgsql.html#pg_insert) — Insert array into table
-   [pg\_last\_error](/book/pgsql.html#pg_last_error) — Get the last
    error message string of a connection
-   [pg\_last\_notice](/book/pgsql.html#pg_last_notice) — Returns the
    last notice message from PostgreSQL server
-   [pg\_last\_oid](/book/pgsql.html#pg_last_oid) — Returns the last
    row's OID
-   [pg\_lo\_close](/book/pgsql.html#pg_lo_close) — Close a large object
-   [pg\_lo\_create](/book/pgsql.html#pg_lo_create) — Create a large
    object
-   [pg\_lo\_export](/book/pgsql.html#pg_lo_export) — Export a large
    object to file
-   [pg\_lo\_import](/book/pgsql.html#pg_lo_import) — Import a large
    object from file
-   [pg\_lo\_open](/book/pgsql.html#pg_lo_open) — Open a large object
-   [pg\_lo\_read\_all](/book/pgsql.html#pg_lo_read_all) — Reads an
    entire large object and send straight to browser
-   [pg\_lo\_read](/book/pgsql.html#pg_lo_read) — Read a large object
-   [pg\_lo\_seek](/book/pgsql.html#pg_lo_seek) — Seeks position within
    a large object
-   [pg\_lo\_tell](/book/pgsql.html#pg_lo_tell) — Returns current seek
    position a of large object
-   [pg\_lo\_truncate](/book/pgsql.html#pg_lo_truncate) — Truncates a
    large object
-   [pg\_lo\_unlink](/book/pgsql.html#pg_lo_unlink) — Delete a large
    object
-   [pg\_lo\_write](/book/pgsql.html#pg_lo_write) — Write to a large
    object
-   [pg\_meta\_data](/book/pgsql.html#pg_meta_data) — Get meta data for
    table
-   [pg\_num\_fields](/book/pgsql.html#pg_num_fields) — Returns the
    number of fields in a result
-   [pg\_num\_rows](/book/pgsql.html#pg_num_rows) — Returns the number
    of rows in a result
-   [pg\_options](/book/pgsql.html#pg_options) — Get the options
    associated with the connection
-   [pg\_parameter\_status](/book/pgsql.html#pg_parameter_status) —
    Looks up a current parameter setting of the server
-   [pg\_pconnect](/book/pgsql.html#pg_pconnect) — Open a persistent
    PostgreSQL connection
-   [pg\_ping](/book/pgsql.html#pg_ping) — Ping database connection
-   [pg\_port](/book/pgsql.html#pg_port) — Return the port number
    associated with the connection
-   [pg\_prepare](/book/pgsql.html#pg_prepare) — Submits a request to
    create a prepared statement with the given parameters, and waits for
    completion
-   [pg\_put\_line](/book/pgsql.html#pg_put_line) — Send a
    NULL-terminated string to PostgreSQL backend
-   [pg\_query\_params](/book/pgsql.html#pg_query_params) — Submits a
    command to the server and waits for the result, with the ability to
    pass parameters separately from the SQL command text
-   [pg\_query](/book/pgsql.html#pg_query) — Execute a query
-   [pg\_result\_error\_field](/book/pgsql.html#pg_result_error_field) —
    Returns an individual field of an error report
-   [pg\_result\_error](/book/pgsql.html#pg_result_error) — Get error
    message associated with result
-   [pg\_result\_seek](/book/pgsql.html#pg_result_seek) — Set internal
    row offset in result resource
-   [pg\_result\_status](/book/pgsql.html#pg_result_status) — Get status
    of query result
-   [pg\_select](/book/pgsql.html#pg_select) — Select records
-   [pg\_send\_execute](/book/pgsql.html#pg_send_execute) — Sends a
    request to execute a prepared statement with given parameters,
    without waiting for the result(s)
-   [pg\_send\_prepare](/book/pgsql.html#pg_send_prepare) — Sends a
    request to create a prepared statement with the given parameters,
    without waiting for completion
-   [pg\_send\_query\_params](/book/pgsql.html#pg_send_query_params) —
    Submits a command and separate parameters to the server without
    waiting for the result(s)
-   [pg\_send\_query](/book/pgsql.html#pg_send_query) — Sends
    asynchronous query
-   [pg\_set\_client\_encoding](/book/pgsql.html#pg_set_client_encoding)
    — Set the client encoding
-   [pg\_set\_error\_verbosity](/book/pgsql.html#pg_set_error_verbosity)
    — Determines the verbosity of messages returned by pg\_last\_error
    and pg\_result\_error
-   [pg\_socket](/book/pgsql.html#pg_socket) — Get a read only handle to
    the socket underlying a PostgreSQL connection
-   [pg\_trace](/book/pgsql.html#pg_trace) — Enable tracing a PostgreSQL
    connection
-   [pg\_transaction\_status](/book/pgsql.html#pg_transaction_status) —
    Returns the current in-transaction status of the server
-   [pg\_tty](/book/pgsql.html#pg_tty) — Return the TTY name associated
    with the connection
-   [pg\_unescape\_bytea](/book/pgsql.html#pg_unescape_bytea) — Unescape
    binary for bytea type
-   [pg\_untrace](/book/pgsql.html#pg_untrace) — Disable tracing of a
    PostgreSQL connection
-   [pg\_update](/book/pgsql.html#pg_update) — Update table
-   [pg\_version](/book/pgsql.html#pg_version) — Returns an array with
    client, protocol and server version (when available)

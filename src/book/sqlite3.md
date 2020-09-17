SQLite3
=======

**Table of Contents**

-   [Introduction](/book/sqlite3.html#Introduction)
-   [Installing/Configuring](/book/sqlite3.html#Installing/Configuring)
    -   [Requirements](/book/sqlite3.html#Requirements)
    -   [Installation](/book/sqlite3.html#Installation)
    -   [Runtime
        Configuration](/book/sqlite3.html#Runtime%20Configuration)
    -   [Resource Types](/book/sqlite3.html#Resource%20Types)
-   [Predefined Constants](/book/sqlite3.html#Predefined%20Constants)
-   [SQLite3](/book/sqlite3.html#SQLite3) — The SQLite3 class
    -   [SQLite3::backup](/book/sqlite3.html#SQLite3::backup) — Backup
        one database to another database
    -   [SQLite3::busyTimeout](/book/sqlite3.html#SQLite3::busyTimeout)
        — Sets the busy connection handler
    -   [SQLite3::changes](/book/sqlite3.html#SQLite3::changes) —
        Returns the number of database rows that were changed (or
        inserted or deleted) by the most recent SQL statement
    -   [SQLite3::close](/book/sqlite3.html#SQLite3::close) — Closes the
        database connection
    -   [SQLite3::\_\_construct](/book/sqlite3.html#SQLite3::__construct)
        — Instantiates an SQLite3 object and opens an SQLite 3 database
    -   [SQLite3::createAggregate](/book/sqlite3.html#SQLite3::createAggregate)
        — Registers a PHP function for use as an SQL aggregate function
    -   [SQLite3::createCollation](/book/sqlite3.html#SQLite3::createCollation)
        — Registers a PHP function for use as an SQL collating function
    -   [SQLite3::createFunction](/book/sqlite3.html#SQLite3::createFunction)
        — Registers a PHP function for use as an SQL scalar function
    -   [SQLite3::enableExceptions](/book/sqlite3.html#SQLite3::enableExceptions)
        — Enable throwing exceptions
    -   [SQLite3::escapeString](/book/sqlite3.html#SQLite3::escapeString)
        — Returns a string that has been properly escaped
    -   [SQLite3::exec](/book/sqlite3.html#SQLite3::exec) — Executes a
        result-less query against a given database
    -   [SQLite3::lastErrorCode](/book/sqlite3.html#SQLite3::lastErrorCode)
        — Returns the numeric result code of the most recent failed
        SQLite request
    -   [SQLite3::lastErrorMsg](/book/sqlite3.html#SQLite3::lastErrorMsg)
        — Returns English text describing the most recent failed SQLite
        request
    -   [SQLite3::lastInsertRowID](/book/sqlite3.html#SQLite3::lastInsertRowID)
        — Returns the row ID of the most recent INSERT into the database
    -   [SQLite3::loadExtension](/book/sqlite3.html#SQLite3::loadExtension)
        — Attempts to load an SQLite extension library
    -   [SQLite3::open](/book/sqlite3.html#SQLite3::open) — Opens an
        SQLite database
    -   [SQLite3::openBlob](/book/sqlite3.html#SQLite3::openBlob) —
        Opens a stream resource to read a BLOB
    -   [SQLite3::prepare](/book/sqlite3.html#SQLite3::prepare) —
        Prepares an SQL statement for execution
    -   [SQLite3::query](/book/sqlite3.html#SQLite3::query) — Executes
        an SQL query
    -   [SQLite3::querySingle](/book/sqlite3.html#SQLite3::querySingle)
        — Executes a query and returns a single result
    -   [SQLite3::version](/book/sqlite3.html#SQLite3::version) —
        Returns the SQLite3 library version as a string constant and as
        a number
-   [SQLite3Stmt](/book/sqlite3.html#SQLite3Stmt) — The SQLite3Stmt
    class
    -   [SQLite3Stmt::bindParam](/book/sqlite3.html#SQLite3Stmt::bindParam)
        — Binds a parameter to a statement variable
    -   [SQLite3Stmt::bindValue](/book/sqlite3.html#SQLite3Stmt::bindValue)
        — Binds the value of a parameter to a statement variable
    -   [SQLite3Stmt::clear](/book/sqlite3.html#SQLite3Stmt::clear) —
        Clears all current bound parameters
    -   [SQLite3Stmt::close](/book/sqlite3.html#SQLite3Stmt::close) —
        Closes the prepared statement
    -   [SQLite3Stmt::execute](/book/sqlite3.html#SQLite3Stmt::execute)
        — Executes a prepared statement and returns a result set object
    -   [SQLite3Stmt::getSQL](/book/sqlite3.html#SQLite3Stmt::getSQL) —
        Get the SQL of the statement
    -   [SQLite3Stmt::paramCount](/book/sqlite3.html#SQLite3Stmt::paramCount)
        — Returns the number of parameters within the prepared statement
    -   [SQLite3Stmt::readOnly](/book/sqlite3.html#SQLite3Stmt::readOnly)
        — Returns whether a statement is definitely read only
    -   [SQLite3Stmt::reset](/book/sqlite3.html#SQLite3Stmt::reset) —
        Resets the prepared statement
-   [SQLite3Result](/book/sqlite3.html#SQLite3Result) — The
    SQLite3Result class
    -   [SQLite3Result::columnName](/book/sqlite3.html#SQLite3Result::columnName)
        — Returns the name of the nth column
    -   [SQLite3Result::columnType](/book/sqlite3.html#SQLite3Result::columnType)
        — Returns the type of the nth column
    -   [SQLite3Result::fetchArray](/book/sqlite3.html#SQLite3Result::fetchArray)
        — Fetches a result row as an associative or numerically indexed
        array or both
    -   [SQLite3Result::finalize](/book/sqlite3.html#SQLite3Result::finalize)
        — Closes the result set
    -   [SQLite3Result::numColumns](/book/sqlite3.html#SQLite3Result::numColumns)
        — Returns the number of columns in the result set
    -   [SQLite3Result::reset](/book/sqlite3.html#SQLite3Result::reset)
        — Resets the result set back to the first row

Support for SQLite version 3 databases.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/sqlite3.html#Requirements)
-   [Installation](/book/sqlite3.html#Installation)
-   [Runtime Configuration](/book/sqlite3.html#Runtime%20Configuration)
-   [Resource Types](/book/sqlite3.html#Resource%20Types)

Requirements
------------

As of PHP 7.4.0
<a href="http://sqlite.org/" class="link external">» libsqlite</a> ≥
3.7.4 is required. Formerly, the bundled libsqlite could have been used
instead.

Installation
------------

The SQLite3 extension is enabled by default as of PHP 5.3.0. It's
possible to disable it by using *--without-sqlite3* at compile time.

Windows users must enable `php_sqlite3.dll` in order to use this
extension. This DLL is included with Windows distributions of PHP as of
PHP 5.3.0.

> **Note**: **Additional setup on Windows as of PHP 7.4.0**  
>
> In order for this extension to work, there are DLL files that must be
> available to the Windows system `PATH`. For information on how to do
> this, see the FAQ entitled
> "<a href="/faq/installation.html#faq.installation.addtopath" class="link">How do I add my PHP directory to the PATH on Windows</a>".
> Although copying DLL files from the PHP folder into the Windows system
> directory also works (because the system directory is by default in
> the system's `PATH`), this is not recommended. *This extension
> requires the following files to be in the `PATH`:* `libsqlite3.dll`.

> **Note**:
>
> This extension was briefly a PECL extension but that version is only
> recommended for experimental use.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                 | Default | Changeable       | Changelog                                                    |
|----------------------------------------------------------------------|---------|------------------|--------------------------------------------------------------|
| <a href="/book/sqlite3.html#" class="link">sqlite3.extension_dir</a> | ""      | PHP\_INI\_SYSTEM | Available as of PHP 5.3.11.                                  |
| <a href="/book/sqlite3.html#" class="link">sqlite3.defensive</a>     | 1       | PHP\_INI\_SYSTEM | Available as of PHP 7.2.17 and 7.3.4 for libsqlite ≥ 3.26.0. |

Here's a short explanation of the configuration directives.

`sqlite3.extension_dir` <span class="type">string</span>  
Path to the directory where the loadable extensions for SQLite reside.

`sqlite3.defensive` <span class="type">bool</span>  
When the defensive flag is enabled, language features that allow
ordinary SQL to deliberately corrupt the database file are disabled.
This forbids writing directly to the schema, shadow tables (eg. FTS data
tables), or the sqlite\_dbpage virtual table. This `php.ini` setting is
only effective for libsqlite ≥ 3.26.0.

Resource Types
--------------

This extension has no resource types defined.

Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`SQLITE3_ASSOC`** (<span class="type">integer</span>)  
<span class="simpara"> Specifies that the <span
class="methodname">Sqlite3Result::fetchArray</span> method shall return
an array indexed by column name as returned in the corresponding result
set. </span>

**`SQLITE3_NUM`** (<span class="type">integer</span>)  
<span class="simpara"> Specifies that the <span
class="methodname">Sqlite3Result::fetchArray</span> method shall return
an array indexed by column number as returned in the corresponding
result set, starting at column 0. </span>

**`SQLITE3_BOTH`** (<span class="type">integer</span>)  
<span class="simpara"> Specifies that the <span
class="methodname">Sqlite3Result::fetchArray</span> method shall return
an array indexed by both column name and number as returned in the
corresponding result set, starting at column 0. </span>

**`SQLITE3_INTEGER`** (<span class="type">integer</span>)  
<span class="simpara"> Represents the SQLite3 INTEGER storage class.
</span>

**`SQLITE3_FLOAT`** (<span class="type">integer</span>)  
<span class="simpara"> Represents the SQLite3 REAL (FLOAT) storage
class. </span>

**`SQLITE3_TEXT`** (<span class="type">integer</span>)  
<span class="simpara"> Represents the SQLite3 TEXT storage class.
</span>

**`SQLITE3_BLOB`** (<span class="type">integer</span>)  
<span class="simpara"> Represents the SQLite3 BLOB storage class.
</span>

**`SQLITE3_NULL`** (<span class="type">integer</span>)  
<span class="simpara"> Represents the SQLite3 NULL storage class.
</span>

**`SQLITE3_OPEN_READONLY`** (<span class="type">integer</span>)  
<span class="simpara"> Specifies that the SQLite3 database be opened for
reading only. </span>

**`SQLITE3_OPEN_READWRITE`** (<span class="type">integer</span>)  
<span class="simpara"> Specifies that the SQLite3 database be opened for
reading and writing. </span>

**`SQLITE3_OPEN_CREATE`** (<span class="type">integer</span>)  
<span class="simpara"> Specifies that the SQLite3 database be created if
it does not already exist. </span>

**`SQLITE3_DETERMINISTIC`** (<span class="type">integer</span>)  
<span class="simpara"> Specifies that a function created with <span
class="function">SQLite3::createFunction</span> is deterministic, i.e.
it always returns the same result given the same inputs within a single
SQL statement. (Available as of PHP 7.1.4.) </span>

Introduction
------------

A class that interfaces SQLite 3 databases.

Class synopsis
--------------

**SQLite3**

<span class="ooclass"> class **SQLite3** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">backup</span> ( <span class="methodparam"><span
class="type">SQLite3</span> `$destination_db`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$source_dbname`<span class="initializer"> = "main"</span></span> \[,
<span class="methodparam"><span class="type">string</span>
`$destination_dbname`<span class="initializer"> = "main"</span></span>
\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">busyTimeout</span> ( <span
class="methodparam"><span class="type">int</span> `$msecs`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">changes</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">close</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = SQLITE3\_OPEN\_READWRITE \|
SQLITE3\_OPEN\_CREATE</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$encryption_key`<span class="initializer"> =
""</span></span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">createAggregate</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$step_callback`</span> , <span class="methodparam"><span
class="type">mixed</span> `$final_callback`</span> \[, <span
class="methodparam"><span class="type">int</span> `$argument_count`<span
class="initializer"> = -1</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">createCollation</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">createFunction</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">int</span> `$argument_count`<span class="initializer"> =
-1</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \]\] )

<span class="type">bool</span> <span
class="methodname">enableExceptions</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$enableExceptions`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">escapeString</span> ( <span class="methodparam"><span
class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">exec</span> ( <span class="methodparam"><span
class="type">string</span> `$query`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">lastErrorCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">lastErrorMsg</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">lastInsertRowID</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">loadExtension</span> ( <span
class="methodparam"><span class="type">string</span>
`$shared_library`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">open</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = SQLITE3\_OPEN\_READWRITE \|
SQLITE3\_OPEN\_CREATE</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$encryption_key`<span class="initializer"> =
""</span></span> \]\] )

<span class="modifier">public</span> <span class="type">resource</span>
<span class="methodname">openBlob</span> ( <span
class="methodparam"><span class="type">string</span> `$table`</span> ,
<span class="methodparam"><span class="type">string</span>
`$column`</span> , <span class="methodparam"><span
class="type">int</span> `$rowid`</span> \[, <span
class="methodparam"><span class="type">string</span> `$dbname`<span
class="initializer"> = "main"</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = SQLITE3\_OPEN\_READONLY</span></span> \]\] )

<span class="modifier">public</span> <span
class="type">SQLite3Stmt</span> <span class="methodname">prepare</span>
( <span class="methodparam"><span class="type">string</span>
`$query`</span> )

<span class="modifier">public</span> <span
class="type">SQLite3Result</span> <span class="methodname">query</span>
( <span class="methodparam"><span class="type">string</span>
`$query`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">querySingle</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$entire_row`<span class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">version</span> ( <span
class="methodparam">void</span> )

}

SQLite3::backup
===============

Backup one database to another database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3::backup</span> ( <span
class="methodparam"><span class="type">SQLite3</span>
`$destination_db`</span> \[, <span class="methodparam"><span
class="type">string</span> `$source_dbname`<span class="initializer"> =
"main"</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$destination_dbname`<span
class="initializer"> = "main"</span></span> \]\] )

<span class="methodname">SQLite3::backup</span> copies the contents of
one database into another, overwriting the contents of the destination
database. It is useful either for creating backups of databases or for
copying in-memory databases to or from persistent files.

### Parameters

`destination_db`  
A database connection opened with <span
class="methodname">SQLite3::open</span>.

`source_dbname`  
The database name is *"main"* for the main database, *"temp"* for the
temporary database, or the name specified after the *AS* keyword in an
*ATTACH* statement for an attached database.

`destination_dbname`  
Analogous to `source_dbname` but for the `destination_db`.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Backup an existing database**

``` php
<?php
// $conn is a connection to an already opened sqlite3 database

$backup = new SQLite3('backup.sqlite');
$conn->backup($backup);
?>
```

SQLite3::busyTimeout
====================

Sets the busy connection handler

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3::busyTimeout</span> ( <span
class="methodparam"><span class="type">int</span> `$msecs`</span> )

Sets a busy handler that will sleep until the database is not locked or
the timeout is reached.

### Parameters

`msecs`  
The milliseconds to sleep. Setting this value to a value less than or
equal to zero, will turn off an already set timeout handler.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** on failure.

SQLite3::changes
================

Returns the number of database rows that were changed (or inserted or
deleted) by the most recent SQL statement

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SQLite3::changes</span> ( <span
class="methodparam">void</span> )

Returns the number of database rows that were changed (or inserted or
deleted) by the most recent SQL statement.

### Parameters

This function has no parameters.

### Return Values

Returns an <span class="type">integer</span> value corresponding to the
number of database rows changed (or inserted or deleted) by the most
recent SQL statement.

### Examples

**Example \#1 <span class="function">SQLite3::changes</span> example**

``` php
<?php
$db = new SQLite3('mysqlitedb.db');

$query = $db->exec('UPDATE counter SET views=0 WHERE page="test"');
if ($query) {
    echo 'Number of rows modified: ', $db->changes();
}
?>
```

SQLite3::close
==============

Closes the database connection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3::close</span> ( <span
class="methodparam">void</span> )

Closes the database connection.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">SQLite3::close</span> example**

``` php
<?php
$db = new SQLite3('mysqlitedb.db');
$db->close();
?>
```

SQLite3::\_\_construct
======================

Instantiates an SQLite3 object and opens an SQLite 3 database

### Description

<span class="modifier">public</span> <span
class="methodname">SQLite3::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = SQLITE3\_OPEN\_READWRITE \|
SQLITE3\_OPEN\_CREATE</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$encryption_key`<span class="initializer"> =
""</span></span> \]\] )

Instantiates an SQLite3 object and opens a connection to an SQLite 3
database. If the build includes encryption, then it will attempt to use
the key.

### Parameters

`filename`  
Path to the SQLite database, or *:memory:* to use in-memory database. If
`filename` is an empty string, then a private, temporary on-disk
database will be created. This private database will be automatically
deleted as soon as the database connection is closed.

`flags`  
Optional flags used to determine how to open the SQLite database. By
default, open uses *SQLITE3\_OPEN\_READWRITE \| SQLITE3\_OPEN\_CREATE*.

-   *SQLITE3\_OPEN\_READONLY*: Open the database for reading only.

-   *SQLITE3\_OPEN\_READWRITE*: Open the database for reading and
    writing.

-   *SQLITE3\_OPEN\_CREATE*: Create the database if it does not exist.

`encryption_key`  
An optional encryption key used when encrypting and decrypting an SQLite
database. If the SQLite encryption module is not installed, this
parameter will have no effect.

### Return Values

Returns an SQLite3 object on success.

### Errors/Exceptions

Throws an <span class="classname">Exception</span> on failure.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 7.0.10  | The `filename` can now be empty to use a private, temporary on-disk database. |

### Examples

**Example \#1 <span class="function">SQLite3::\_\_construct</span>
example**

``` php
<?php
$db = new SQLite3('mysqlitedb.db');

$db->exec('CREATE TABLE foo (bar TEXT)');
$db->exec("INSERT INTO foo (bar) VALUES ('This is a test')");

$result = $db->query('SELECT bar FROM foo');
var_dump($result->fetchArray());
?>
```

SQLite3::createAggregate
========================

Registers a PHP function for use as an SQL aggregate function

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3::createAggregate</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$step_callback`</span> , <span class="methodparam"><span
class="type">mixed</span> `$final_callback`</span> \[, <span
class="methodparam"><span class="type">int</span> `$argument_count`<span
class="initializer"> = -1</span></span> \] )

Registers a PHP function or user-defined function for use as an SQL
aggregate function for use within SQL statements.

### Parameters

`name`  
Name of the SQL aggregate to be created or redefined.

`step_callback`  
Callback function called for each row of the result set. Your PHP
function should accumulate the result and store it in the aggregation
context.

This function need to be defined as:

<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">step</span></span> ( <span class="methodparam"><span
class="type">mixed</span> `$context`</span> , <span
class="methodparam"><span class="type">int</span> `$rownumber`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value1`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \] )

`context`  
**`NULL`** for the first row; on subsequent rows it will have the value
that was previously returned from the step function; you should use this
to maintain the aggregate state.

`rownumber`  
The current row number.

`value1`  
The first argument passed to the aggregate.

`...`  
Further arguments passed to the aggregate.

The return value of this function will be used as the `context` argument
in the next call of the step or finalize functions.

`final_callback`  
Callback function to aggregate the "stepped" data from each row. Once
all the rows have been processed, this function will be called and it
should then take the data from the aggregation context and return the
result. This callback function should return a type understood by SQLite
(i.e.
<a href="/language/types/intro.html" class="link">scalar type</a>).

This function need to be defined as:

<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">fini</span></span> ( <span class="methodparam"><span
class="type">mixed</span> `$context`</span> , <span
class="methodparam"><span class="type">int</span> `$rownumber`</span> )

`context`  
Holds the return value from the very last call to the step function.

`rownumber`  
Always *0*.

The return value of this function will be used as the return value for
the aggregate.

`argument_count`  
The number of arguments that the SQL aggregate takes. If this parameter
is negative, then the SQL aggregate may take any number of arguments.

### Return Values

Returns **`TRUE`** upon successful creation of the aggregate, or
**`FALSE`** on failure.

### Examples

**Example \#1 max\_length aggregation function example**

``` php
<?php
$data = array(
   'one',
   'two',
   'three',
   'four',
   'five',
   'six',
   'seven',
   'eight',
   'nine',
   'ten',
   );
$db = new SQLite3(':memory:');
$db->exec("CREATE TABLE strings(a)");
$insert = $db->prepare('INSERT INTO strings VALUES (?)');
foreach ($data as $str) {
    $insert->bindValue(1, $str);
    $insert->execute();
}
$insert = null;

function max_len_step($context, $rownumber, $string)
{
    if (strlen($string) > $context) {
        $context = strlen($string);
    }
    return $context;
}

function max_len_finalize($context, $rownumber)
{
    return $context === null ? 0 : $context;
}

$db->createAggregate('max_len', 'max_len_step', 'max_len_finalize');

var_dump($db->querySingle('SELECT max_len(a) from strings'));
?>
```

The above example will output:

    int(5)

In this example, we are creating an aggregating function that will
calculate the length of the longest string in one of the columns of the
table. For each row, the *max\_len\_step* function is called and passed
a *$context* parameter. The context parameter is just like any other PHP
variable and be set to hold an array or even an object value. In this
example, we are simply using it to hold the maximum length we have seen
so far; if the *$string* has a length longer than the current maximum,
we update the context to hold this new maximum length.

After all of the rows have been processed, SQLite calls the
*max\_len\_finalize* function to determine the aggregate result. Here,
we could perform some kind of calculation based on the data found in the
*$context*. In our simple example though, we have been calculating the
result as the query progressed, so we simply need to return the context
value.

**Tip**

It is NOT recommended for you to store a copy of the values in the
context and then process them at the end, as you would cause SQLite to
use a lot of memory to process the query - just think of how much memory
you would need if a million rows were stored in memory, each containing
a string 32 bytes in length.

**Tip**

You can use <span class="methodname">SQLite3::createAggregate</span> to
override SQLite native SQL functions.

SQLite3::createCollation
========================

Registers a PHP function for use as an SQL collating function

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3::createCollation</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Registers a PHP function or user-defined function for use as a collating
function within SQL statements.

### Parameters

`name`  
Name of the SQL collating function to be created or redefined

`callback`  
The name of a PHP function or user-defined function to apply as a
callback, defining the behavior of the collation. It should accept two
values and return as <span class="function">strcmp</span> does, i.e. it
should return -1, 1, or 0 if the first string sorts before, sorts after,
or is equal to the second.

This function need to be defined as:

<span class="type">int</span> <span class="methodname"><span
class="replaceable">collation</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value2`</span> )

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">SQLite3::createCollation</span>
example**

Register the PHP function <span class="function">strnatcmp</span> as a
collating sequence in the SQLite3 database.

``` php
<?php

$db = new SQLite3(":memory:");
$db->exec("CREATE TABLE test (col1 string)");
$db->exec("INSERT INTO test VALUES ('a1')");
$db->exec("INSERT INTO test VALUES ('a10')");
$db->exec("INSERT INTO test VALUES ('a2')");

$db->createCollation('NATURAL_CMP', 'strnatcmp');

$defaultSort = $db->query("SELECT col1 FROM test ORDER BY col1");
$naturalSort = $db->query("SELECT col1 FROM test ORDER BY col1 COLLATE NATURAL_CMP");

echo "default:\n";
while ($row = $defaultSort->fetchArray()){
    echo $row['col1'], "\n";
}

echo "\nnatural:\n";
while ($row = $naturalSort->fetchArray()){
    echo $row['col1'], "\n";
}

$db->close();

?>
```

The above example will output:


    default:
    a1
    a10
    a2

    natural:
    a1
    a2
    a10

### See Also

-   The SQLite collation documentation:
    <a href="http://sqlite.org/datatype3.html#collation" class="link external">» http://sqlite.org/datatype3.html#collation</a>

SQLite3::createFunction
=======================

Registers a PHP function for use as an SQL scalar function

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3::createFunction</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">int</span> `$argument_count`<span class="initializer"> =
-1</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \]\] )

Registers a PHP function or user-defined function for use as an SQL
scalar function for use within SQL statements.

### Parameters

`name`  
Name of the SQL function to be created or redefined.

`callback`  
The name of a PHP function or user-defined function to apply as a
callback, defining the behavior of the SQL function.

This function need to be defined as:

<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$value1`</span> \[,
<span class="methodparam"><span class="type">mixed</span> `$...`</span>
\] )

`value1`  
The first argument passed to the SQL function.

`...`  
Further arguments passed to the SQL function.

`argument_count`  
The number of arguments that the SQL function takes. If this parameter
is *-1*, then the SQL function may take any number of arguments.

`flags`  
A bitwise conjunction of flags. Currently, only
**`SQLITE3_DETERMINISTIC`** is supported, which specifies that the
function always returns the same result given the same inputs within a
single SQL statement.

### Return Values

Returns **`TRUE`** upon successful creation of the function, **`FALSE`**
on failure.

### Changelog

| Version | Description                           |
|---------|---------------------------------------|
| 7.1.4   | The `flags` parameter has been added. |

### Examples

**Example \#1 <span class="function">SQLite3::createFunction</span>
example**

``` php
<?php
function my_udf_md5($string) {
    return md5($string);
}

$db = new SQLite3('mysqlitedb.db');
$db->createFunction('my_udf_md5', 'my_udf_md5');

var_dump($db->querySingle('SELECT my_udf_md5("test")'));
?>
```

The above example will output something similar to:

    string(32) "098f6bcd4621d373cade4e832627b4f6"

SQLite3::enableExceptions
=========================

Enable throwing exceptions

### Description

<span class="type">bool</span> <span
class="methodname">SQLite3::enableExceptions</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$enableExceptions`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Controls whether the <span class="classname">SQLite3</span> instance
will throw exceptions or warnings on error.

### Parameters

`enable`  
When **`TRUE`**, the <span class="classname">SQLite3</span> instance,
and <span class="classname">SQLite3Stmt</span> and <span
class="classname">SQLite3Result</span> instances derived from it, will
throw exceptions on error.

When **`FALSE`**, the <span class="classname">SQLite3</span> instance,
and <span class="classname">SQLite3Stmt</span> and <span
class="classname">SQLite3Result</span> instances derived from it, will
raise warnings on error.

For either mode, the error code and message, if any, will be available
via <span class="methodname">SQLite3::lastErrorCode</span> and <span
class="methodname">SQLite3::lastErrorMsg</span> respectively.

### Return Values

Returns the old value; **`TRUE`** if exceptions were enabled,
**`FALSE`** otherwise.

### Examples

**Example \#1 <span class="methodname">SQLite3::enableExceptions</span>
example**

``` php
<?php
$sqlite = new SQLite3(':memory:');
try {
    $sqlite->exec('create table foo');
    $sqlite->enableExceptions(true);
    $sqlite->exec('create table bar');
} catch (Exception $e) {
    echo 'Caught exception: ' . $e->getMessage();
}
?>
```

The above example will output something similar to:

    Warning: SQLite3::exec(): near "foo": syntax error in example.php on line 4
    Caught exception: near "bar": syntax error

SQLite3::escapeString
=====================

Returns a string that has been properly escaped

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">SQLite3::escapeString</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Returns a string that has been properly escaped for safe inclusion in an
SQL statement.

**Warning**

This function is not (yet) binary safe!

To properly handle BLOB fields which may contain NUL characters, use
<span class="function">SQLite3Stmt::bindParam</span> instead.

### Parameters

`value`  
The string to be escaped.

### Return Values

Returns a properly escaped string that may be used safely in an SQL
statement.

### Notes

**Warning**

<span class="function">addslashes</span> should *NOT* be used to quote
your strings for SQLite queries; it will lead to strange results when
retrieving your data.

SQLite3::exec
=============

Executes a result-less query against a given database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3::exec</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

Executes a result-less query against a given database.

> **Note**: <span class="simpara"> SQLite3 may need to create
> <a href="https://sqlite.org/tempfiles.html" class="link external">» temporary files</a>
> during the execution of queries, so the respective directories may
> have to be writable. </span>

### Parameters

`query`  
The SQL query to execute (typically an INSERT, UPDATE, or DELETE query).

### Return Values

Returns **`TRUE`** if the query succeeded, **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">SQLite3::exec</span> example**

``` php
<?php
$db = new SQLite3('mysqlitedb.db');

$db->exec('CREATE TABLE bar (bar STRING)');
?>
```

SQLite3::lastErrorCode
======================

Returns the numeric result code of the most recent failed SQLite request

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SQLite3::lastErrorCode</span> ( <span
class="methodparam">void</span> )

Returns the numeric result code of the most recent failed SQLite
request.

### Parameters

This function has no parameters.

### Return Values

Returns an integer value representing the numeric result code of the
most recent failed SQLite request.

SQLite3::lastErrorMsg
=====================

Returns English text describing the most recent failed SQLite request

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SQLite3::lastErrorMsg</span> ( <span
class="methodparam">void</span> )

Returns English text describing the most recent failed SQLite request.

### Parameters

This function has no parameters.

### Return Values

Returns an English string describing the most recent failed SQLite
request.

SQLite3::lastInsertRowID
========================

Returns the row ID of the most recent INSERT into the database

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SQLite3::lastInsertRowID</span> ( <span
class="methodparam">void</span> )

Returns the row ID of the most recent INSERT into the database.

### Parameters

This function has no parameters.

### Return Values

Returns the row ID of the most recent INSERT into the database

SQLite3::loadExtension
======================

Attempts to load an SQLite extension library

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3::loadExtension</span> ( <span
class="methodparam"><span class="type">string</span>
`$shared_library`</span> )

Attempts to load an SQLite extension library.

### Parameters

`shared_library`  
The name of the library to load. The library must be located in the
directory specified in the configure option sqlite3.extension\_dir.

### Return Values

Returns **`TRUE`** if the extension is successfully loaded, **`FALSE`**
on failure.

### Examples

**Example \#1 <span class="function">SQLite3::loadExtension</span>
example**

``` php
<?php
$db = new SQLite3('mysqlitedb.db');
$db->loadExtension('libagg.so');
?>
```

SQLite3::open
=============

Opens an SQLite database

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">SQLite3::open</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = SQLITE3\_OPEN\_READWRITE \|
SQLITE3\_OPEN\_CREATE</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$encryption_key`<span class="initializer"> =
""</span></span> \]\] )

Opens an SQLite 3 Database. If the build includes encryption, then it
will attempt to use the key.

### Parameters

`filename`  
Path to the SQLite database, or *:memory:* to use in-memory database.

`flags`  
Optional flags used to determine how to open the SQLite database. By
default, open uses *SQLITE3\_OPEN\_READWRITE \| SQLITE3\_OPEN\_CREATE*.

-   *SQLITE3\_OPEN\_READONLY*: Open the database for reading only.

-   *SQLITE3\_OPEN\_READWRITE*: Open the database for reading and
    writing.

-   *SQLITE3\_OPEN\_CREATE*: Create the database if it does not exist.

`encryption_key`  
An optional encryption key used when encrypting and decrypting an SQLite
database. If the SQLite encryption module is not installed, this
parameter will have no effect.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">SQLite3::open</span> example**

``` php
<?php
/**
 * Simple example of extending the SQLite3 class and changing the __construct
 * parameters, then using the open method to initialize the DB.
 */
class MyDB extends SQLite3
{
    function __construct()
    {
        $this->open('mysqlitedb.db');
    }
}

$db = new MyDB();

$db->exec('CREATE TABLE foo (bar STRING)');
$db->exec("INSERT INTO foo (bar) VALUES ('This is a test')");

$result = $db->query('SELECT bar FROM foo');
var_dump($result->fetchArray());
?>
```

SQLite3::openBlob
=================

Opens a stream resource to read a BLOB

### Description

<span class="modifier">public</span> <span class="type">resource</span>
<span class="methodname">SQLite3::openBlob</span> ( <span
class="methodparam"><span class="type">string</span> `$table`</span> ,
<span class="methodparam"><span class="type">string</span>
`$column`</span> , <span class="methodparam"><span
class="type">int</span> `$rowid`</span> \[, <span
class="methodparam"><span class="type">string</span> `$dbname`<span
class="initializer"> = "main"</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = SQLITE3\_OPEN\_READONLY</span></span> \]\] )

Opens a stream resource to read or write a BLOB, which would be selected
by:

SELECT `column` FROM `dbname`.`table` WHERE rowid = `rowid`

> **Note**: <span class="simpara"> It is not possible to change the size
> of a BLOB by writing to the stream. Instead, an UPDATE statement has
> to be executed, possibly using SQLite's zeroblob() function to set the
> desired BLOB size. </span>

### Parameters

`table`  
The table name.

`column`  
The column name.

`rowid`  
The row ID.

`dbname`  
The symbolic name of the DB

`flags`  
Either **`SQLITE3_OPEN_READONLY`** or **`SQLITE3_OPEN_READWRITE`** to
open the stream for reading only, or for reading and writing,
respectively.

### Return Values

Returns a stream resource, or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                         |
|---------|-----------------------------------------------------------------------------------------------------|
| 7.2.0   | The `flags` parameter has been added, allowing to write BLOBs; formerly only reading was supported. |

### Examples

**Example \#1 <span class="function">SQLite3::openBlob</span> example**

``` php
<?php
$conn = new SQLite3(':memory:');
$conn->exec('CREATE TABLE test (text text)');
$conn->exec("INSERT INTO test VALUES ('Lorem ipsum')");
$stream = $conn->openBlob('test', 'text', 1);
echo stream_get_contents($stream);
fclose($stream); // mandatory, otherwise the next line would fail
$conn->close();
?>
```

The above example will output:

    Lorem ipsum

**Example \#2 Incrementally writing a BLOB**

``` php
<?php
$conn = new SQLite3(':memory:');
$conn->exec('CREATE TABLE test (text text)');
$conn->exec("INSERT INTO test VALUES (zeroblob(36))");
$stream = $conn->openBlob('test', 'text', 1, 'main', SQLITE3_OPEN_READWRITE);
for ($i = 0; $i < 3; $i++) {
    fwrite($stream,  "Lorem ipsum\n");
}
fclose($stream);
echo $conn->querySingle("SELECT text FROM test");
$conn->close();
?>
```

The above example will output:

    Lorem ipsum
    Lorem ipsum
    Lorem ipsum

SQLite3::prepare
================

Prepares an SQL statement for execution

### Description

<span class="modifier">public</span> <span
class="type">SQLite3Stmt</span> <span
class="methodname">SQLite3::prepare</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

Prepares an SQL statement for execution and returns an <span
class="classname">SQLite3Stmt</span> object.

### Parameters

`query`  
The SQL query to prepare.

### Return Values

Returns an <span class="classname">SQLite3Stmt</span> object on success
or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">SQLite3::prepare</span> example**

``` php
<?php
unlink('mysqlitedb.db');
$db = new SQLite3('mysqlitedb.db');

$db->exec('CREATE TABLE foo (id INTEGER, bar STRING)');
$db->exec("INSERT INTO foo (id, bar) VALUES (1, 'This is a test')");

$stmt = $db->prepare('SELECT bar FROM foo WHERE id=:id');
$stmt->bindValue(':id', 1, SQLITE3_INTEGER);

$result = $stmt->execute();
var_dump($result->fetchArray());
?>
```

### See Also

-   <span class="methodname">SQLite3Stmt::paramCount</span>
-   <span class="methodname">SQLite3Stmt::bindValue</span>
-   <span class="methodname">SQLite3Stmt::bindParam</span>

SQLite3::query
==============

Executes an SQL query

### Description

<span class="modifier">public</span> <span
class="type">SQLite3Result</span> <span
class="methodname">SQLite3::query</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

Executes an SQL query, returning an <span
class="classname">SQLite3Result</span> object. If the query does not
yield a result (such as DML statements) the returned <span
class="classname">SQLite3Result</span> object is not really usable. Use
<span class="methodname">SQLite3::exec</span> for such queries instead.

### Parameters

`query`  
The SQL query to execute.

### Return Values

Returns an <span class="classname">SQLite3Result</span> object, or
**`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">SQLite3::query</span> example**

``` php
<?php
$db = new SQLite3('mysqlitedb.db');

$results = $db->query('SELECT bar FROM foo');
while ($row = $results->fetchArray()) {
    var_dump($row);
}
?>
```

SQLite3::querySingle
====================

Executes a query and returns a single result

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">SQLite3::querySingle</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$entire_row`<span class="initializer"> = **`FALSE`**</span></span> \] )

Executes a query and returns a single result.

### Parameters

`query`  
The SQL query to execute.

`entire_row`  
By default, <span class="function">querySingle</span> returns the value
of the first column returned by the query. If `entire_row` is
**`TRUE`**, then it returns an array of the entire first row.

### Return Values

Returns the value of the first column of results or an array of the
entire first row (if `entire_row` is **`TRUE`**).

If the query is valid but no results are returned, then **`NULL`** will
be returned if `entire_row` is **`FALSE`**, otherwise an empty array is
returned.

Invalid or failing queries will return **`FALSE`**.

### Examples

**Example \#1 <span class="function">SQLite3::querySingle</span>
example**

``` php
<?php
$db = new SQLite3('mysqlitedb.db');

var_dump($db->querySingle('SELECT username FROM user WHERE userid=1'));
print_r($db->querySingle('SELECT username, email FROM user WHERE userid=1', true));
?>
```

The above example will output something similar to:

    string(5) "Scott"
    Array
    (
        [username] => Scott
        [email] => scott@example.com
    )

SQLite3::version
================

Returns the SQLite3 library version as a string constant and as a number

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">SQLite3::version</span> ( <span
class="methodparam">void</span> )

Returns the SQLite3 library version as a string constant and as a
number.

### Parameters

This function has no parameters.

### Return Values

Returns an associative array with the keys "versionString" and
"versionNumber".

### Examples

**Example \#1 <span class="function">SQLite3::version</span> example**

``` php
<?php
print_r(SQLite3::version());
?>
```

The above example will output something similar to:

    Array
    (
        [versionString] => 3.5.9
        [versionNumber] => 3005009
    )

Introduction
------------

A class that handles prepared statements for the SQLite 3 extension.

Class synopsis
--------------

**SQLite3Stmt**

<span class="ooclass"> class **SQLite3Stmt** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">bindParam</span> ( <span
class="methodparam"><span class="type">mixed</span> `$sql_param`</span>
, <span class="methodparam"><span class="type">mixed</span>
`&$param`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">bindValue</span> ( <span
class="methodparam"><span class="type">mixed</span> `$sql_param`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">clear</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">close</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">SQLite3Result</span> <span
class="methodname">execute</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getSQL</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$expanded`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">paramCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">readOnly</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">reset</span> ( <span
class="methodparam">void</span> )

}

SQLite3Stmt::bindParam
======================

Binds a parameter to a statement variable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3Stmt::bindParam</span> ( <span
class="methodparam"><span class="type">mixed</span> `$sql_param`</span>
, <span class="methodparam"><span class="type">mixed</span>
`&$param`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`</span> \] )

Binds a parameter to a statement variable.

**Caution**

Before PHP 7.2.14 and 7.3.0, respectively, <span
class="methodname">SQLite3Stmt::reset</span> must be called after the
first call to <span class="methodname">SQLite3Stmt::execute</span> if
the bound value should be properly updated on following calls to <span
class="methodname">SQLite3Stmt::execute</span>. If <span
class="methodname">SQLite3Stmt::reset</span> is not called, the bound
value will not change, even if the value assigned to the variable passed
to <span class="methodname">SQLite3Stmt::bindParam</span> has changed,
or <span class="methodname">SQLite3Stmt::bindParam</span> has been
called again.

### Parameters

`sql_param`  
Either a <span class="type">string</span> (for named parameters) or an
<span class="type">int</span> (for positional parameters) identifying
the statement variable to which the value should be bound. If a named
parameter does not start with a colon (*:*) or an at sign (*@*), a colon
(*:*) is automatically preprended. Positional parameters start with *1*.

`param`  
The parameter to bind to a statement variable.

`type`  
The data type of the parameter to bind.

-   **`SQLITE3_INTEGER`**: The value is a signed integer, stored in 1,
    2, 3, 4, 6, or 8 bytes depending on the magnitude of the value.

-   **`SQLITE3_FLOAT`**: The value is a floating point value, stored as
    an 8-byte IEEE floating point number.

-   **`SQLITE3_TEXT`**: The value is a text string, stored using the
    database encoding (UTF-8, UTF-16BE or UTF-16-LE).

-   **`SQLITE3_BLOB`**: The value is a blob of data, stored exactly as
    it was input.

-   **`SQLITE3_NULL`**: The value is a NULL value.

As of PHP 7.0.7, if `type` is omitted, it is automatically detected from
the type of the `param`: <span class="type">boolean</span> and <span
class="type">integer</span> are treated as **`SQLITE3_INTEGER`**, <span
class="type">float</span> as **`SQLITE3_FLOAT`**, <span
class="type">null</span> as **`SQLITE3_NULL`** and all others as
**`SQLITE3_TEXT`**. Formerly, if `type` has been omitted, it has
defaulted to **`SQLITE3_TEXT`**.

> **Note**:
>
> If `param` is **`NULL`**, it is always treated as **`SQLITE3_NULL`**,
> regardless of the given `type`.

### Return Values

Returns **`TRUE`** if the parameter is bound to the statement variable,
**`FALSE`** on failure.

### Changelog

| Version | Description                                          |
|---------|------------------------------------------------------|
| 7.4.0   | `sql_param` now also supports the *@param* notation. |

### Examples

**Example \#1 <span class="function">SQLite3Stmt::bindParam</span>
Usage**

This example shows how a single prepared statement with a single
parameter binding can be used to insert multiple rows with different
values.

``` php
<?php
$db = new SQLite3(':memory:');
$db->exec("CREATE TABLE foo (bar TEXT)");

$stmt = $db->prepare("INSERT INTO foo VALUES (:bar)");
$stmt->bindParam(':bar', $bar, SQLITE3_TEXT);

$bar = 'baz';
$stmt->execute();

$bar = 42;
$stmt->execute();

$res = $db->query("SELECT * FROM foo");
while (($row = $res->fetchArray(SQLITE3_ASSOC))) {
    var_dump($row);
}
?>
```

The above example will output:

    array(1) {
      ["bar"]=>
      string(3) "baz"
    }
    array(1) {
      ["bar"]=>
      string(2) "42"
    }

### See Also

-   <span class="methodname">SQLite3Stmt::bindValue</span>
-   <span class="methodname">SQLite3::prepare</span>

SQLite3Stmt::bindValue
======================

Binds the value of a parameter to a statement variable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3Stmt::bindValue</span> ( <span
class="methodparam"><span class="type">mixed</span> `$sql_param`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`</span> \] )

Binds the value of a parameter to a statement variable.

**Caution**

Before PHP 7.2.14 and 7.3.0, respectively, once the statement has been
executed, <span class="methodname">SQLite3Stmt::reset</span> needs to be
called to be able to change the value of bound parameters.

### Parameters

`sql_param`  
Either a <span class="type">string</span> (for named parameters) or an
<span class="type">int</span> (for positional parameters) identifying
the statement variable to which the value should be bound. If a named
parameter does not start with a colon (*:*) or an at sign (*@*), a colon
(*:*) is automatically preprended. Positional parameters start with *1*.

`value`  
The value to bind to a statement variable.

`type`  
The data type of the value to bind.

-   **`SQLITE3_INTEGER`**: The value is a signed integer, stored in 1,
    2, 3, 4, 6, or 8 bytes depending on the magnitude of the value.

-   **`SQLITE3_FLOAT`**: The value is a floating point value, stored as
    an 8-byte IEEE floating point number.

-   **`SQLITE3_TEXT`**: The value is a text string, stored using the
    database encoding (UTF-8, UTF-16BE or UTF-16-LE).

-   **`SQLITE3_BLOB`**: The value is a blob of data, stored exactly as
    it was input.

-   **`SQLITE3_NULL`**: The value is a NULL value.

As of PHP 7.0.7, if `type` is omitted, it is automatically detected from
the type of the `value`: <span class="type">boolean</span> and <span
class="type">integer</span> are treated as **`SQLITE3_INTEGER`**, <span
class="type">float</span> as **`SQLITE3_FLOAT`**, <span
class="type">null</span> as **`SQLITE3_NULL`** and all others as
**`SQLITE3_TEXT`**. Formerly, if `type` has been omitted, it has
defaulted to **`SQLITE3_TEXT`**.

> **Note**:
>
> If `value` is **`NULL`**, it is always treated as **`SQLITE3_NULL`**,
> regardless of the given `type`.

### Return Values

Returns **`TRUE`** if the value is bound to the statement variable, or
**`FALSE`** on failure.

### Changelog

| Version | Description                                          |
|---------|------------------------------------------------------|
| 7.4.0   | `sql_param` now also supports the *@param* notation. |

### Examples

**Example \#1 <span class="function">SQLite3Stmt::bindValue</span>
example**

``` php
<?php
$db = new SQLite3(':memory:');

$db->exec('CREATE TABLE foo (id INTEGER, bar STRING)');
$db->exec("INSERT INTO foo (id, bar) VALUES (1, 'This is a test')");

$stmt = $db->prepare('SELECT bar FROM foo WHERE id=:id');
$stmt->bindValue(':id', 1, SQLITE3_INTEGER);

$result = $stmt->execute();
var_dump($result->fetchArray(SQLITE3_ASSOC));
?>
```

The above example will output:

    array(1) {
      ["bar"]=>
      string(14) "This is a test"
    }

### See Also

-   <span class="methodname">SQLite3Stmt::bindParam</span>
-   <span class="methodname">SQLite3::prepare</span>

SQLite3Stmt::clear
==================

Clears all current bound parameters

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3Stmt::clear</span> ( <span
class="methodparam">void</span> )

Clears all current bound parameters (sets them to **`NULL`**).

**Caution**

This method needs to be used with <span
class="methodname">SQLite3Stmt::reset</span>. If used alone, any call to
<span class="methodname">SQLite3Stmt::bindValue</span> or <span
class="methodname">SQLite3Stmt::bindParam</span> will be of no effect
and all bound parameters will have the **`NULL`** value.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** on successful clearing of bound parameters,
**`FALSE`** on failure.

SQLite3Stmt::close
==================

Closes the prepared statement

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3Stmt::close</span> ( <span
class="methodparam">void</span> )

Closes the prepared statement.

> **Note**: <span class="simpara"> Note that all <span
> class="classname">SQLite3Result</span>s that have been retrieved by
> executing this statement will be invalidated when the statement is
> closed. </span>

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`**

SQLite3Stmt::execute
====================

Executes a prepared statement and returns a result set object

### Description

<span class="modifier">public</span> <span
class="type">SQLite3Result</span> <span
class="methodname">SQLite3Stmt::execute</span> ( <span
class="methodparam">void</span> )

Executes a prepared statement and returns a result set object.

**Caution**

Result set objects retrieved by calling this method on the same
statement object are not independent, but rather share the same
underlying structure. Therefore it is recommended to call <span
class="methodname">SQLite3Result::finalize</span>, before calling <span
class="methodname">SQLite3Stmt::execute</span> on the same statement
object again.

### Parameters

This function has no parameters.

### Return Values

Returns an <span class="classname">SQLite3Result</span> object on
successful execution of the prepared statement, **`FALSE`** on failure.

### See Also

-   <span class="methodname">SQLite3::prepare</span>
-   <span class="methodname">SQLite3Stmt::bindValue</span>
-   <span class="methodname">SQLite3Stmt::bindParam</span>

SQLite3Stmt::getSQL
===================

Get the SQL of the statement

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SQLite3Stmt::getSQL</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$expanded`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Retrieves the SQL of the prepared statement. If `expanded` is
**`FALSE`**, the unmodified SQL is retrieved. If `expanded` is
**`TRUE`**, all query parameters are replaced with their bound values,
or with an SQL *NULL*, if not already bound.

### Parameters

`expanded`  
Whether to retrieve the expanded SQL. Passing **`TRUE`** is only
supported as of libsqlite 3.14.

### Return Values

Returns the SQL of the prepared statement, or **`FALSE`** on failure.

### Errors/Exceptions

If `expanded` is **`TRUE`**, but the libsqlite version is less than
3.14, an error of level **`E_WARNING`** or an <span
class="classname">Exception</span> is issued, according to <span
class="methodname">SQLite3::enableExceptions</span>.

### Examples

**Example \#1 Inspecting the expanded SQL**

``` php
<?php
$db = new SQLite3(':memory:');
$stmt = $db->prepare("SELECT :a, ?, :c");
$stmt->bindValue(':a', 'foo');
$answer = 42;
$stmt->bindParam(2, $answer);
var_dump($stmt->getSQL(true));
?>
```

The above example will output something similar to:

    string(24) "SELECT 'foo', '42', NULL"

SQLite3Stmt::paramCount
=======================

Returns the number of parameters within the prepared statement

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SQLite3Stmt::paramCount</span> ( <span
class="methodparam">void</span> )

Returns the number of parameters within the prepared statement.

### Parameters

This function has no parameters.

### Return Values

Returns the number of parameters within the prepared statement.

### See Also

-   <span class="methodname">SQLite3::prepare</span>

SQLite3Stmt::readOnly
=====================

Returns whether a statement is definitely read only

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3Stmt::readOnly</span> ( <span
class="methodparam">void</span> )

Returns whether a statement is definitely read only. A statement is
considered read only, if it makes no *direct* changes to the content of
the database file. Note that user defined SQL functions might change the
database *indirectly* as a side effect.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if a statement is definitely read only, **`FALSE`**
otherwise.

SQLite3Stmt::reset
==================

Resets the prepared statement

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3Stmt::reset</span> ( <span
class="methodparam">void</span> )

Resets the prepared statement to its state prior to execution. All
bindings remain intact after reset.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the statement is successfully reset, or
**`FALSE`** on failure.

Introduction
------------

A class that handles result sets for the SQLite 3 extension.

Class synopsis
--------------

**SQLite3Result**

<span class="ooclass"> class **SQLite3Result** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">columnName</span> ( <span
class="methodparam"><span class="type">int</span>
`$column_number`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">columnType</span> ( <span class="methodparam"><span
class="type">int</span> `$column_number`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">fetchArray</span> (\[ <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = SQLITE3\_BOTH</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">finalize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">numColumns</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">reset</span> ( <span
class="methodparam">void</span> )

}

SQLite3Result::columnName
=========================

Returns the name of the nth column

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SQLite3Result::columnName</span> ( <span
class="methodparam"><span class="type">int</span>
`$column_number`</span> )

Returns the name of the column specified by the `column_number`. Note
that the name of a result column is the value of the *AS* clause for
that column, if there is an *AS* clause. If there is no *AS* clause then
the name of the column is unspecified and may change from one release of
libsqlite3 to the next.

### Parameters

`column_number`  
The numeric zero-based index of the column.

### Return Values

Returns the <span class="type">string</span> name of the column
identified by `column_number`.

SQLite3Result::columnType
=========================

Returns the type of the nth column

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SQLite3Result::columnType</span> ( <span
class="methodparam"><span class="type">int</span>
`$column_number`</span> )

Returns the type of the column identified by `column_number`.

### Parameters

`column_number`  
The numeric zero-based index of the column.

### Return Values

Returns the data type index of the column identified by `column_number`
(one of **`SQLITE3_INTEGER`**, **`SQLITE3_FLOAT`**, **`SQLITE3_TEXT`**,
**`SQLITE3_BLOB`**, or **`SQLITE3_NULL`**).

SQLite3Result::fetchArray
=========================

Fetches a result row as an associative or numerically indexed array or
both

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">SQLite3Result::fetchArray</span> (\[ <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = SQLITE3\_BOTH</span></span> \] )

Fetches a result row as an associative or numerically indexed array or
both. By default, fetches as both.

### Parameters

`mode`  
Controls how the next row will be returned to the caller. This value
must be one of either *SQLITE3\_ASSOC*, *SQLITE3\_NUM*, or
*SQLITE3\_BOTH*.

-   *SQLITE3\_ASSOC*: returns an array indexed by column name as
    returned in the corresponding result set

-   *SQLITE3\_NUM*: returns an array indexed by column number as
    returned in the corresponding result set, starting at column 0

-   *SQLITE3\_BOTH*: returns an array indexed by both column name and
    number as returned in the corresponding result set, starting at
    column 0

### Return Values

Returns a result row as an associatively or numerically indexed array or
both. Alternately will return **`FALSE`** if there are no more rows.

The types of the values of the returned array are mapped from SQLite3
types as follows: integers are mapped to <span
class="type">integer</span> if they fit into the range
**`PHP_INT_MIN`**..**`PHP_INT_MAX`**, and to <span
class="type">string</span> otherwise. Floats are mapped to <span
class="type">float</span>, *NULL* values are mapped to <span
class="type">null</span>, and strings and blobs are mapped to <span
class="type">string</span>.

SQLite3Result::finalize
=======================

Closes the result set

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3Result::finalize</span> ( <span
class="methodparam">void</span> )

Closes the result set.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`**.

SQLite3Result::numColumns
=========================

Returns the number of columns in the result set

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">SQLite3Result::numColumns</span> ( <span
class="methodparam">void</span> )

Returns the number of columns in the result set.

### Parameters

This function has no parameters.

### Return Values

Returns the number of columns in the result set.

SQLite3Result::reset
====================

Resets the result set back to the first row

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SQLite3Result::reset</span> ( <span
class="methodparam">void</span> )

Resets the result set back to the first row.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the result set is successfully reset back to the
first row, **`FALSE`** on failure.

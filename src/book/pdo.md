PHP Data Objects
================

**Table of Contents**

-   [Introduction](/book/pdo.html#Introduction)
-   [Installing/Configuring](/book/pdo.html#Installing/Configuring)
    -   [Requirements](/book/pdo.html#Requirements)
    -   [Installation](/book/pdo.html#Installation)
    -   [Runtime Configuration](/book/pdo.html#Runtime%20Configuration)
    -   [Resource Types](/book/pdo.html#Resource%20Types)
-   [Predefined Constants](/book/pdo.html#Predefined%20Constants)
-   [Connections and Connection
    management](/book/pdo.html#Connections%20and%20Connection%20management)
-   [Transactions and
    auto-commit](/book/pdo.html#Transactions%20and%20auto-commit)
-   [Prepared statements and stored
    procedures](/book/pdo.html#Prepared%20statements%20and%20stored%20procedures)
-   [Errors and error
    handling](/book/pdo.html#Errors%20and%20error%20handling)
-   [Large Objects (LOBs)](/book/pdo.html#Large%20Objects%20(LOBs))
-   [PDO](/book/pdo.html#PDO) — The PDO class
    -   [PDO::beginTransaction](/book/pdo.html#PDO::beginTransaction) —
        Initiates a transaction
    -   [PDO::commit](/book/pdo.html#PDO::commit) — Commits a
        transaction
    -   [PDO::\_\_construct](/book/pdo.html#PDO::__construct) — Creates
        a PDO instance representing a connection to a database
    -   [PDO::errorCode](/book/pdo.html#PDO::errorCode) — Fetch the
        SQLSTATE associated with the last operation on the database
        handle
    -   [PDO::errorInfo](/book/pdo.html#PDO::errorInfo) — Fetch extended
        error information associated with the last operation on the
        database handle
    -   [PDO::exec](/book/pdo.html#PDO::exec) — Execute an SQL statement
        and return the number of affected rows
    -   [PDO::getAttribute](/book/pdo.html#PDO::getAttribute) — Retrieve
        a database connection attribute
    -   [PDO::getAvailableDrivers](/book/pdo.html#PDO::getAvailableDrivers)
        — Return an array of available PDO drivers
    -   [PDO::inTransaction](/book/pdo.html#PDO::inTransaction) — Checks
        if inside a transaction
    -   [PDO::lastInsertId](/book/pdo.html#PDO::lastInsertId) — Returns
        the ID of the last inserted row or sequence value
    -   [PDO::prepare](/book/pdo.html#PDO::prepare) — Prepares a
        statement for execution and returns a statement object
    -   [PDO::query](/book/pdo.html#PDO::query) — Executes an SQL
        statement, returning a result set as a PDOStatement object
    -   [PDO::quote](/book/pdo.html#PDO::quote) — Quotes a string for
        use in a query
    -   [PDO::rollBack](/book/pdo.html#PDO::rollBack) — Rolls back a
        transaction
    -   [PDO::setAttribute](/book/pdo.html#PDO::setAttribute) — Set an
        attribute
-   [PDOStatement](/book/pdo.html#PDOStatement) — The PDOStatement class
    -   [PDOStatement::bindColumn](/book/pdo.html#PDOStatement::bindColumn)
        — Bind a column to a PHP variable
    -   [PDOStatement::bindParam](/book/pdo.html#PDOStatement::bindParam)
        — Binds a parameter to the specified variable name
    -   [PDOStatement::bindValue](/book/pdo.html#PDOStatement::bindValue)
        — Binds a value to a parameter
    -   [PDOStatement::closeCursor](/book/pdo.html#PDOStatement::closeCursor)
        — Closes the cursor, enabling the statement to be executed again
    -   [PDOStatement::columnCount](/book/pdo.html#PDOStatement::columnCount)
        — Returns the number of columns in the result set
    -   [PDOStatement::debugDumpParams](/book/pdo.html#PDOStatement::debugDumpParams)
        — Dump an SQL prepared command
    -   [PDOStatement::errorCode](/book/pdo.html#PDOStatement::errorCode)
        — Fetch the SQLSTATE associated with the last operation on the
        statement handle
    -   [PDOStatement::errorInfo](/book/pdo.html#PDOStatement::errorInfo)
        — Fetch extended error information associated with the last
        operation on the statement handle
    -   [PDOStatement::execute](/book/pdo.html#PDOStatement::execute) —
        Executes a prepared statement
    -   [PDOStatement::fetch](/book/pdo.html#PDOStatement::fetch) —
        Fetches the next row from a result set
    -   [PDOStatement::fetchAll](/book/pdo.html#PDOStatement::fetchAll)
        — Returns an array containing all of the result set rows
    -   [PDOStatement::fetchColumn](/book/pdo.html#PDOStatement::fetchColumn)
        — Returns a single column from the next row of a result set
    -   [PDOStatement::fetchObject](/book/pdo.html#PDOStatement::fetchObject)
        — Fetches the next row and returns it as an object
    -   [PDOStatement::getAttribute](/book/pdo.html#PDOStatement::getAttribute)
        — Retrieve a statement attribute
    -   [PDOStatement::getColumnMeta](/book/pdo.html#PDOStatement::getColumnMeta)
        — Returns metadata for a column in a result set
    -   [PDOStatement::nextRowset](/book/pdo.html#PDOStatement::nextRowset)
        — Advances to the next rowset in a multi-rowset statement handle
    -   [PDOStatement::rowCount](/book/pdo.html#PDOStatement::rowCount)
        — Returns the number of rows affected by the last SQL statement
    -   [PDOStatement::setAttribute](/book/pdo.html#PDOStatement::setAttribute)
        — Set a statement attribute
    -   [PDOStatement::setFetchMode](/book/pdo.html#PDOStatement::setFetchMode)
        — Set the default fetch mode for this statement
-   [PDOException](/book/pdo.html#PDOException) — The PDOException class
-   [PDO Drivers](/book/pdo.html#PDO%20Drivers)
    -   [CUBRID (PDO)](/book/pdo.html#CUBRID%20(PDO)) — CUBRID Functions
        (PDO\_CUBRID)
    -   [MS SQL Server (PDO)](/book/pdo.html#MS%20SQL%20Server%20(PDO))
        — Microsoft SQL Server and Sybase Functions (PDO\_DBLIB)
    -   [Firebird (PDO)](/book/pdo.html#Firebird%20(PDO)) — Firebird
        Functions (PDO\_FIREBIRD)
    -   [IBM (PDO)](/book/pdo.html#IBM%20(PDO)) — IBM Functions
        (PDO\_IBM)
    -   [Informix (PDO)](/book/pdo.html#Informix%20(PDO)) — Informix
        Functions (PDO\_INFORMIX)
    -   [MySQL (PDO)](/book/pdo.html#MySQL%20(PDO)) — MySQL Functions
        (PDO\_MYSQL)
    -   [MS SQL Server (PDO)](/book/pdo.html#MS%20SQL%20Server%20(PDO))
        — Microsoft SQL Server Functions (PDO\_SQLSRV)
    -   [Oracle (PDO)](/book/pdo.html#Oracle%20(PDO)) — Oracle Functions
        (PDO\_OCI)
    -   [ODBC and DB2 (PDO)](/book/pdo.html#ODBC%20and%20DB2%20(PDO)) —
        ODBC and DB2 Functions (PDO\_ODBC)
    -   [PostgreSQL (PDO)](/book/pdo.html#PostgreSQL%20(PDO)) —
        PostgreSQL Functions (PDO\_PGSQL)
    -   [SQLite (PDO)](/book/pdo.html#SQLite%20(PDO)) — SQLite Functions
        (PDO\_SQLITE)

The *PHP Data Objects* (PDO) extension defines a lightweight, consistent
interface for accessing databases in PHP. Each database driver that
implements the PDO interface can expose database-specific features as
regular extension functions. Note that you cannot perform any database
functions using the PDO extension by itself; you must use a
<a href="/book/pdo.html#PDO%20Drivers" class="link">database-specific PDO driver</a>
to access a database server.

PDO provides a *data-access* abstraction layer, which means that,
regardless of which database you're using, you use the same functions to
issue queries and fetch data. PDO does *not* provide a *database*
abstraction; it doesn't rewrite SQL or emulate missing features. You
should use a full-blown abstraction layer if you need that facility.

PDO ships with PHP 5.1, and is available as a PECL extension for PHP
5.0; PDO requires the new OO features in the core of PHP 5, and so will
not run with earlier versions of PHP.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/pdo.html#Requirements)
-   [Installation](/book/pdo.html#Installation)
-   [Runtime Configuration](/book/pdo.html#Runtime%20Configuration)
-   [Resource Types](/book/pdo.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

**Installing PDO on Unix systems**

1.  PDO and the
    <a href="/book/pdo.html#SQLite%20(PDO)" class="link">PDO_SQLITE</a>
    driver is enabled by default as of PHP 5.1.0. You may need to enable
    the PDO driver for your database of choice; consult the
    documentation for
    <a href="/book/pdo.html#PDO%20Drivers" class="link">database-specific PDO drivers</a>
    to find out more about that.

    > **Note**:
    >
    > When building PDO as a shared extension (*not recommended*) then
    > all PDO drivers *must* be loaded *after* PDO itself.

2.  When installing PDO as a shared module, the php.ini file needs to be
    updated so that the PDO extension will be loaded automatically when
    PHP runs. You will also need to enable any database specific drivers
    there too; make sure that they are listed after the pdo.so line, as
    PDO must be initialized before the database-specific extensions can
    be loaded. If you built PDO and the database-specific extensions
    statically, you can skip this step.

        extension=pdo.so

**Windows users**

1.  PDO and all the major drivers ship with PHP as shared extensions,
    and simply need to be activated by editing the `php.ini` file:

        extension=php_pdo.dll

    > **Note**:
    >
    > This step is not necessary for PHP 5.3 and above, as a DLL is no
    > longer required for PDO.

2.  Next, choose the other database-specific DLL files and either use
    <span class="function">dl</span> to load them at runtime, or enable
    them in `php.ini` below `php_pdo.dll`. For example:

        extension=php_pdo.dll
        extension=php_pdo_firebird.dll
        extension=php_pdo_informix.dll
        extension=php_pdo_mssql.dll
        extension=php_pdo_mysql.dll
        extension=php_pdo_oci.dll
        extension=php_pdo_oci8.dll
        extension=php_pdo_odbc.dll
        extension=php_pdo_pgsql.dll
        extension=php_pdo_sqlite.dll  

    These DLLs should exist in the system's
    <a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>.

> **Note**:
>
> Remember that after making changes to your `php.ini` file you will
> need to restart PHP for your new configuration directives to take
> effect.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                 | Default | Changeable     | Changelog |
|------------------------------------------------------|---------|----------------|-----------|
| <a href="/book/pdo.html#" class="link">pdo.dsn.*</a> |         | `php.ini` only |           |

Here's a short explanation of the configuration directives.

`pdo.dsn.*` <span class="type">string</span>  
Defines DSN alias. See <span class="function">PDO::\_\_construct</span>
for thorough explanation.

Resource Types
--------------

This extension has no resource types defined.

Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**Warning**

PDO uses class constants since PHP 5.1. Prior releases use global
constants in the form **`PDO_PARAM_BOOL`**.

**`PDO::PARAM_BOOL`** (<span class="type">int</span>)  
<span class="simpara"> Represents a boolean data type. </span>

**`PDO::PARAM_NULL`** (<span class="type">int</span>)  
<span class="simpara"> Represents the SQL NULL data type. </span>

**`PDO::PARAM_INT`** (<span class="type">int</span>)  
<span class="simpara"> Represents the SQL INTEGER data type. </span>

**`PDO::PARAM_STR`** (<span class="type">int</span>)  
<span class="simpara"> Represents the SQL CHAR, VARCHAR, or other string
data type. </span>

**`PDO::PARAM_STR_NATL`** (<span class="type">int</span>)  
<span class="simpara"> Flag to denote a string uses the national
character set. </span> <span class="simpara"> Available since PHP 7.2.0
</span>

**`PDO::PARAM_STR_CHAR`** (<span class="type">int</span>)  
<span class="simpara"> Flag to denote a string uses the regular
character set. </span> <span class="simpara"> Available since PHP 7.2.0
</span>

**`PDO::PARAM_LOB`** (<span class="type">int</span>)  
<span class="simpara"> Represents the SQL large object data type.
</span>

**`PDO::PARAM_STMT`** (<span class="type">int</span>)  
<span class="simpara"> Represents a recordset type. Not currently
supported by any drivers. </span>

**`PDO::PARAM_INPUT_OUTPUT`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the parameter is an INOUT
parameter for a stored procedure. You must bitwise-OR this value with an
explicit PDO::PARAM\_\* data type. </span>

**`PDO::FETCH_LAZY`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return each
row as an object with variable names that correspond to the column names
returned in the result set. **`PDO::FETCH_LAZY`** creates the object
variable names as they are accessed. Not valid inside <span
class="function">PDOStatement::fetchAll</span>. </span>

**`PDO::FETCH_ASSOC`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return each
row as an array indexed by column name as returned in the corresponding
result set. If the result set contains multiple columns with the same
name, **`PDO::FETCH_ASSOC`** returns only a single value per column
name. </span>

**`PDO::FETCH_NAMED`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return each
row as an array indexed by column name as returned in the corresponding
result set. If the result set contains multiple columns with the same
name, **`PDO::FETCH_NAMED`** returns an array of values per column name.
</span>

**`PDO::FETCH_NUM`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return each
row as an array indexed by column number as returned in the
corresponding result set, starting at column 0. </span>

**`PDO::FETCH_BOTH`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return each
row as an array indexed by both column name and number as returned in
the corresponding result set, starting at column 0. </span>

**`PDO::FETCH_OBJ`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return each
row as an object with property names that correspond to the column names
returned in the result set. </span>

**`PDO::FETCH_BOUND`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return TRUE
and assign the values of the columns in the result set to the PHP
variables to which they were bound with the <span
class="function">PDOStatement::bindParam</span> or <span
class="function">PDOStatement::bindColumn</span> methods. </span>

**`PDO::FETCH_COLUMN`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return only
a single requested column from the next row in the result set. </span>

**`PDO::FETCH_CLASS`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall return a
new instance of the requested class, mapping the columns to named
properties in the class. </span>

> **Note**: <span class="simpara"> The magic
> <a href="/language/oop5/overloading.html#language.oop5.overloading.members" class="link"><span class="methodname">__set</span></a>
> method is called if the property doesn't exist in the requested class
> </span>

**`PDO::FETCH_INTO`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that the fetch method shall update an
existing instance of the requested class, mapping the columns to named
properties in the class. </span>

**`PDO::FETCH_FUNC`** (<span class="type">int</span>)  
<span class="simpara"> Allows completely customize the way data is
treated on the fly (only valid inside <span
class="function">PDOStatement::fetchAll</span>). </span>

**`PDO::FETCH_GROUP`** (<span class="type">int</span>)  
<span class="simpara"> Group return by values. Usually combined with
**`PDO::FETCH_COLUMN`** or **`PDO::FETCH_KEY_PAIR`**. </span>

**`PDO::FETCH_UNIQUE`** (<span class="type">int</span>)  
<span class="simpara"> Fetch only the unique values. </span>

**`PDO::FETCH_KEY_PAIR`** (<span class="type">int</span>)  
<span class="simpara"> Fetch a two-column result into an array where the
first column is a key and the second column is the value. Available
since PHP 5.2.3. </span>

**`PDO::FETCH_CLASSTYPE`** (<span class="type">int</span>)  
<span class="simpara"> Determine the class name from the value of first
column. </span>

**`PDO::FETCH_SERIALIZE`** (<span class="type">int</span>)  
<span class="simpara"> As **`PDO::FETCH_INTO`** but object is provided
as a serialized string. Available since PHP 5.1.0. Since PHP 5.3.0 the
class constructor is never called if this flag is set. </span>

**`PDO::FETCH_PROPS_LATE`** (<span class="type">int</span>)  
<span class="simpara"> Call the constructor before setting properties.
Available since PHP 5.2.0. </span>

**`PDO::ATTR_AUTOCOMMIT`** (<span class="type">int</span>)  
<span class="simpara"> If this value is **`FALSE`**, PDO attempts to
disable autocommit so that the connection begins a transaction. </span>

**`PDO::ATTR_PREFETCH`** (<span class="type">int</span>)  
<span class="simpara"> Setting the prefetch size allows you to balance
speed against memory usage for your application. Not all database/driver
combinations support setting of the prefetch size. A larger prefetch
size results in increased performance at the cost of higher memory
usage. </span>

**`PDO::ATTR_TIMEOUT`** (<span class="type">int</span>)  
<span class="simpara"> Sets the timeout value in seconds for
communications with the database. </span>

**`PDO::ATTR_ERRMODE`** (<span class="type">int</span>)  
<span class="simpara"> See the
<a href="/book/pdo.html#Errors%20and%20error%20handling" class="link">Errors and error handling</a>
section for more information about this attribute. </span>

**`PDO::ATTR_SERVER_VERSION`** (<span class="type">int</span>)  
<span class="simpara"> This is a read only attribute; it will return
information about the version of the database server to which PDO is
connected. </span>

**`PDO::ATTR_CLIENT_VERSION`** (<span class="type">int</span>)  
<span class="simpara"> This is a read only attribute; it will return
information about the version of the client libraries that the PDO
driver is using. </span>

**`PDO::ATTR_SERVER_INFO`** (<span class="type">int</span>)  
<span class="simpara"> This is a read only attribute; it will return
some meta information about the database server to which PDO is
connected. </span>

**`PDO::ATTR_CONNECTION_STATUS`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`PDO::ATTR_CASE`** (<span class="type">int</span>)  
<span class="simpara"> Force column names to a specific case specified
by the *PDO::CASE\_\** constants. </span>

**`PDO::ATTR_CURSOR_NAME`** (<span class="type">int</span>)  
<span class="simpara"> Get or set the name to use for a cursor. Most
useful when using scrollable cursors and positioned updates. </span>

**`PDO::ATTR_CURSOR`** (<span class="type">int</span>)  
<span class="simpara"> Selects the cursor type. PDO currently supports
either **`PDO::CURSOR_FWDONLY`** and **`PDO::CURSOR_SCROLL`**. Stick
with **`PDO::CURSOR_FWDONLY`** unless you know that you need a
scrollable cursor. </span>

**`PDO::ATTR_DRIVER_NAME`** (<span class="type">string</span>)  
<span class="simpara"> Returns the name of the driver. </span>

**Example \#1 using **`PDO::ATTR_DRIVER_NAME`****

``` php
<?php
if ($db->getAttribute(PDO::ATTR_DRIVER_NAME) == 'mysql') {
  echo "Running on mysql; doing something mysql specific here\n";
}
?>
```

**`PDO::ATTR_ORACLE_NULLS`** (<span class="type">int</span>)  
<span class="simpara"> Convert empty strings to SQL NULL values on data
fetches. </span>

**`PDO::ATTR_PERSISTENT`** (<span class="type">mixed</span>)  
<span class="simpara"> Request a persistent connection, rather than
creating a new connection. See
<a href="/book/pdo.html#Connections%20and%20Connection%20management" class="link">Connections and Connection management</a>
for more information on this attribute. </span>

**`PDO::ATTR_STATEMENT_CLASS`** (<span class="type">int</span>)  
<span class="simpara"> Sets the class name of which statements are
returned as. </span>

**`PDO::ATTR_FETCH_CATALOG_NAMES`** (<span class="type">int</span>)  
<span class="simpara"> Prepend the containing catalog name to each
column name returned in the result set. The catalog name and column name
are separated by a decimal (.) character. Support of this attribute is
at the driver level; it may not be supported by your driver. </span>

**`PDO::ATTR_FETCH_TABLE_NAMES`** (<span class="type">int</span>)  
<span class="simpara"> Prepend the containing table name to each column
name returned in the result set. The table name and column name are
separated by a decimal (.) character. Support of this attribute is at
the driver level; it may not be supported by your driver. </span>

**`PDO::ATTR_STRINGIFY_FETCHES`** (<span class="type">int</span>)  
<span class="simpara"> Forces all values fetched to be treated as
strings. </span>

**`PDO::ATTR_MAX_COLUMN_LEN`** (<span class="type">int</span>)  
<span class="simpara"> Sets the maximum column name length. </span>

**`PDO::ATTR_DEFAULT_FETCH_MODE`** (<span class="type">int</span>)  
<span class="simpara"> Available since PHP 5.2.0 </span>

**`PDO::ATTR_EMULATE_PREPARES`** (<span class="type">int</span>)  
<span class="simpara"> Available since PHP 5.1.3. </span>

**`PDO::ATTR_DEFAULT_STR_PARAM`** (<span class="type">int</span>)  
<span class="simpara"> Sets the default string parameter type, this can
be one of **`PDO::PARAM_STR_NATL`** and **`PDO::PARAM_STR_CHAR`**.
</span> <span class="simpara"> Available since PHP 7.2.0. </span>

**`PDO::ERRMODE_SILENT`** (<span class="type">int</span>)  
<span class="simpara"> Do not raise an error or exception if an error
occurs. The developer is expected to explicitly check for errors. This
is the default mode. See
<a href="/book/pdo.html#Errors%20and%20error%20handling" class="link">Errors and error handling</a>
for more information about this attribute. </span>

**`PDO::ERRMODE_WARNING`** (<span class="type">int</span>)  
<span class="simpara"> Issue a PHP **`E_WARNING`** message if an error
occurs. See
<a href="/book/pdo.html#Errors%20and%20error%20handling" class="link">Errors and error handling</a>
for more information about this attribute. </span>

**`PDO::ERRMODE_EXCEPTION`** (<span class="type">int</span>)  
<span class="simpara"> Throw a <span
class="classname">PDOException</span> if an error occurs. See
<a href="/book/pdo.html#Errors%20and%20error%20handling" class="link">Errors and error handling</a>
for more information about this attribute. </span>

**`PDO::CASE_NATURAL`** (<span class="type">int</span>)  
<span class="simpara"> Leave column names as returned by the database
driver. </span>

**`PDO::CASE_LOWER`** (<span class="type">int</span>)  
<span class="simpara"> Force column names to lower case. </span>

**`PDO::CASE_UPPER`** (<span class="type">int</span>)  
<span class="simpara"> Force column names to upper case. </span>

**`PDO::NULL_NATURAL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`PDO::NULL_EMPTY_STRING`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`PDO::NULL_TO_STRING`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`PDO::FETCH_ORI_NEXT`** (<span class="type">int</span>)  
<span class="simpara"> Fetch the next row in the result set. Valid only
for scrollable cursors. </span>

**`PDO::FETCH_ORI_PRIOR`** (<span class="type">int</span>)  
<span class="simpara"> Fetch the previous row in the result set. Valid
only for scrollable cursors. </span>

**`PDO::FETCH_ORI_FIRST`** (<span class="type">int</span>)  
<span class="simpara"> Fetch the first row in the result set. Valid only
for scrollable cursors. </span>

**`PDO::FETCH_ORI_LAST`** (<span class="type">int</span>)  
<span class="simpara"> Fetch the last row in the result set. Valid only
for scrollable cursors. </span>

**`PDO::FETCH_ORI_ABS`** (<span class="type">int</span>)  
<span class="simpara"> Fetch the requested row by row number from the
result set. Valid only for scrollable cursors. </span>

**`PDO::FETCH_ORI_REL`** (<span class="type">int</span>)  
<span class="simpara"> Fetch the requested row by relative position from
the current position of the cursor in the result set. Valid only for
scrollable cursors. </span>

**`PDO::CURSOR_FWDONLY`** (<span class="type">int</span>)  
<span class="simpara"> Create a <span
class="classname">PDOStatement</span> object with a forward-only cursor.
This is the default cursor choice, as it is the fastest and most common
data access pattern in PHP. </span>

**`PDO::CURSOR_SCROLL`** (<span class="type">int</span>)  
<span class="simpara"> Create a <span
class="classname">PDOStatement</span> object with a scrollable cursor.
Pass the *PDO::FETCH\_ORI\_\** constants to control the rows fetched
from the result set. </span>

**`PDO::ERR_NONE`** (<span class="type">string</span>)  
<span class="simpara"> Corresponds to SQLSTATE '00000', meaning that the
SQL statement was successfully issued with no errors or warnings. This
constant is for your convenience when checking <span
class="function">PDO::errorCode</span> or <span
class="function">PDOStatement::errorCode</span> to determine if an error
occurred. You will usually know if this is the case by examining the
return code from the method that raised the error condition anyway.
</span>

**`PDO::PARAM_EVT_ALLOC`** (<span class="type">int</span>)  
<span class="simpara"> Allocation event </span>

**`PDO::PARAM_EVT_FREE`** (<span class="type">int</span>)  
<span class="simpara"> Deallocation event </span>

**`PDO::PARAM_EVT_EXEC_PRE`** (<span class="type">int</span>)  
<span class="simpara"> Event triggered prior to execution of a prepared
statement. </span>

**`PDO::PARAM_EVT_EXEC_POST`** (<span class="type">int</span>)  
<span class="simpara"> Event triggered subsequent to execution of a
prepared statement. </span>

**`PDO::PARAM_EVT_FETCH_PRE`** (<span class="type">int</span>)  
<span class="simpara"> Event triggered prior to fetching a result from a
resultset. </span>

**`PDO::PARAM_EVT_FETCH_POST`** (<span class="type">int</span>)  
<span class="simpara"> Event triggered subsequent to fetching a result
from a resultset. </span>

**`PDO::PARAM_EVT_NORMALIZE`** (<span class="type">int</span>)  
<span class="simpara"> Event triggered during bound parameter
registration allowing the driver to normalize the parameter name.
</span>

**`PDO::SQLITE_DETERMINISTIC`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that a function created with <span
class="function">PDO::sqliteCreateFunction</span> is deterministic, i.e.
it always returns the same result given the same inputs within a single
SQL statement. (Available as of PHP 7.1.4.) </span>

Connections and Connection management
=====================================

Connections are established by creating instances of the PDO base class.
It doesn't matter which driver you want to use; you always use the PDO
class name. The constructor accepts parameters for specifying the
database source (known as the DSN) and optionally for the username and
password (if any).

**Example \#1 Connecting to MySQL**

``` php
<?php
$dbh = new PDO('mysql:host=localhost;dbname=test', $user, $pass);
?>
```

If there are any connection errors, a *PDOException* object will be
thrown. You may catch the exception if you want to handle the error
condition, or you may opt to leave it for an application global
exception handler that you set up via <span
class="function">set\_exception\_handler</span>.

**Example \#2 Handling connection errors**

``` php
<?php
try {
    $dbh = new PDO('mysql:host=localhost;dbname=test', $user, $pass);
    foreach($dbh->query('SELECT * from FOO') as $row) {
        print_r($row);
    }
    $dbh = null;
} catch (PDOException $e) {
    print "Error!: " . $e->getMessage() . "<br/>";
    die();
}
?>
```

**Warning**

If your application does not catch the exception thrown from the PDO
constructor, the default action taken by the zend engine is to terminate
the script and display a back trace. This back trace will likely reveal
the full database connection details, including the username and
password. It is your responsibility to catch this exception, either
explicitly (via a *catch* statement) or implicitly via <span
class="function">set\_exception\_handler</span>.

Upon successful connection to the database, an instance of the PDO class
is returned to your script. The connection remains active for the
lifetime of that PDO object. To close the connection, you need to
destroy the object by ensuring that all remaining references to it are
deleted—you do this by assigning **`NULL`** to the variable that holds
the object. If you don't do this explicitly, PHP will automatically
close the connection when your script ends.

> **Note**: <span class="simpara"> If there are still other references
> to this PDO instance (such as from a PDOStatement instance, or from
> other variables referencing the same PDO instance), these have to be
> removed also (for instance, by assigning **`NULL`** to the variable
> that references the PDOStatement). </span>

**Example \#3 Closing a connection**

``` php
<?php
$dbh = new PDO('mysql:host=localhost;dbname=test', $user, $pass);
// use the connection here
$sth = $dbh->query('SELECT * FROM foo');

// and now we're done; close it
$sth = null;
$dbh = null;
?>
```

Many web applications will benefit from making persistent connections to
database servers. Persistent connections are not closed at the end of
the script, but are cached and re-used when another script requests a
connection using the same credentials. The persistent connection cache
allows you to avoid the overhead of establishing a new connection every
time a script needs to talk to a database, resulting in a faster web
application.

**Example \#4 Persistent connections**

``` php
<?php
$dbh = new PDO('mysql:host=localhost;dbname=test', $user, $pass, array(
    PDO::ATTR_PERSISTENT => true
));
?>
```

The value of the **`PDO::ATTR_PERSISTENT`** option is converted to <span
class="type">bool</span> (enable/disable persistent connections), unless
it is a non-numeric <span class="type">string</span>, in which case it
allows to use multiple persistent connection pools. This is useful if
different connections use incompatible settings, for instance, different
values of **`PDO::MYSQL_ATTR_USE_BUFFERED_QUERY`**.

> **Note**:
>
> If you wish to use persistent connections, you must set
> **`PDO::ATTR_PERSISTENT`** in the array of driver options passed to
> the PDO constructor. If setting this attribute with <span
> class="function">PDO::setAttribute</span> after instantiation of the
> object, the driver will not use persistent connections.

> **Note**:
>
> If you're using the PDO ODBC driver and your ODBC libraries support
> ODBC Connection Pooling (unixODBC and Windows are two that do; there
> may be more), then it's recommended that you don't use persistent PDO
> connections, and instead leave the connection caching to the ODBC
> Connection Pooling layer. The ODBC Connection Pool is shared with
> other modules in the process; if PDO is told to cache the connection,
> then that connection would never be returned to the ODBC connection
> pool, resulting in additional connections being created to service
> those other modules.

Transactions and auto-commit
============================

Now that you're connected via PDO, you must understand how PDO manages
transactions before you start issuing queries. If you've never
encountered transactions before, they offer 4 major features: Atomicity,
Consistency, Isolation and Durability (ACID). In layman's terms, any
work carried out in a transaction, even if it is carried out in stages,
is guaranteed to be applied to the database safely, and without
interference from other connections, when it is committed. Transactional
work can also be automatically undone at your request (provided you
haven't already committed it), which makes error handling in your
scripts easier.

Transactions are typically implemented by "saving-up" your batch of
changes to be applied all at once; this has the nice side effect of
drastically improving the efficiency of those updates. In other words,
transactions can make your scripts faster and potentially more robust
(you still need to use them correctly to reap that benefit).

Unfortunately, not every database supports transactions, so PDO needs to
run in what is known as "auto-commit" mode when you first open the
connection. Auto-commit mode means that every query that you run has its
own implicit transaction, if the database supports it, or no transaction
if the database doesn't support transactions. If you need a transaction,
you must use the <span class="function">PDO::beginTransaction</span>
method to initiate one. If the underlying driver does not support
transactions, a PDOException will be thrown (regardless of your error
handling settings: this is always a serious error condition). Once you
are in a transaction, you may use <span
class="function">PDO::commit</span> or <span
class="function">PDO::rollBack</span> to finish it, depending on the
success of the code you run during the transaction.

**Warning**

PDO only checks for transaction capabilities on driver level. If certain
runtime conditions mean that transactions are unavailable, <span
class="methodname">PDO::beginTransaction</span> will still return
**`TRUE`** without error if the database server accepts the request to
start a transaction.

An example of this would be trying to use transactions on MyISAM tables
on a MySQL database.

When the script ends or when a connection is about to be closed, if you
have an outstanding transaction, PDO will automatically roll it back.
This is a safety measure to help avoid inconsistency in the cases where
the script terminates unexpectedly--if you didn't explicitly commit the
transaction, then it is assumed that something went awry, so the
rollback is performed for the safety of your data.

**Warning**

The automatic rollback only happens if you initiate the transaction via
<span class="function">PDO::beginTransaction</span>. If you manually
issue a query that begins a transaction PDO has no way of knowing about
it and thus cannot roll it back if something bad happens.

**Example \#1 Executing a batch in a transaction**

In the following sample, let's assume that we are creating a set of
entries for a new employee, who has been assigned an ID number of 23. In
addition to entering the basic data for that person, we also need to
record their salary. It's pretty simple to make two separate updates,
but by enclosing them within the <span
class="function">PDO::beginTransaction</span> and <span
class="function">PDO::commit</span> calls, we are guaranteeing that no
one else will be able to see those changes until they are complete. If
something goes wrong, the catch block rolls back all changes made since
the transaction was started, and then prints out an error message.

``` php
<?php
try {
  $dbh = new PDO('odbc:SAMPLE', 'db2inst1', 'ibmdb2', 
      array(PDO::ATTR_PERSISTENT => true));
  echo "Connected\n";
} catch (Exception $e) {
  die("Unable to connect: " . $e->getMessage());
}

try {  
  $dbh->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);

  $dbh->beginTransaction();
  $dbh->exec("insert into staff (id, first, last) values (23, 'Joe', 'Bloggs')");
  $dbh->exec("insert into salarychange (id, amount, changedate) 
      values (23, 50000, NOW())");
  $dbh->commit();
  
} catch (Exception $e) {
  $dbh->rollBack();
  echo "Failed: " . $e->getMessage();
}
?>
```

You're not limited to making updates in a transaction; you can also
issue complex queries to extract data, and possibly use that information
to build up more updates and queries; while the transaction is active,
you are guaranteed that no one else can make changes while you are in
the middle of your work. For further reading on transactions, refer to
the documentation provided by your database server.

Prepared statements and stored procedures
=========================================

Many of the more mature databases support the concept of prepared
statements. What are they? They can be thought of as a kind of compiled
template for the SQL that an application wants to run, that can be
customized using variable parameters. Prepared statements offer two
major benefits:

-   <span class="simpara"> The query only needs to be parsed (or
    prepared) once, but can be executed multiple times with the same or
    different parameters. When the query is prepared, the database will
    analyze, compile and optimize its plan for executing the query. For
    complex queries this process can take up enough time that it will
    noticeably slow down an application if there is a need to repeat the
    same query many times with different parameters. By using a prepared
    statement the application avoids repeating the
    analyze/compile/optimize cycle. This means that prepared statements
    use fewer resources and thus run faster. </span>
-   <span class="simpara"> The parameters to prepared statements don't
    need to be quoted; the driver automatically handles this. If an
    application exclusively uses prepared statements, the developer can
    be sure that no SQL injection will occur (however, if other portions
    of the query are being built up with unescaped input, SQL injection
    is still possible). </span>

Prepared statements are so useful that they are the only feature that
PDO will emulate for drivers that don't support them. This ensures that
an application will be able to use the same data access paradigm
regardless of the capabilities of the database.

**Example \#1 Repeated inserts using prepared statements**

This example performs an INSERT query by substituting a *name* and a
*value* for the named placeholders.

``` php
<?php
$stmt = $dbh->prepare("INSERT INTO REGISTRY (name, value) VALUES (:name, :value)");
$stmt->bindParam(':name', $name);
$stmt->bindParam(':value', $value);

// insert one row
$name = 'one';
$value = 1;
$stmt->execute();

// insert another row with different values
$name = 'two';
$value = 2;
$stmt->execute();
?>
```

**Example \#2 Repeated inserts using prepared statements**

This example performs an INSERT query by substituting a *name* and a
*value* for the positional *?* placeholders.

``` php
<?php
$stmt = $dbh->prepare("INSERT INTO REGISTRY (name, value) VALUES (?, ?)");
$stmt->bindParam(1, $name);
$stmt->bindParam(2, $value);

// insert one row
$name = 'one';
$value = 1;
$stmt->execute();

// insert another row with different values
$name = 'two';
$value = 2;
$stmt->execute();
?>
```

**Example \#3 Fetching data using prepared statements**

This example fetches data based on a key value supplied by a form. The
user input is automatically quoted, so there is no risk of a SQL
injection attack.

``` php
<?php
$stmt = $dbh->prepare("SELECT * FROM REGISTRY where name = ?");
if ($stmt->execute(array($_GET['name']))) {
  while ($row = $stmt->fetch()) {
    print_r($row);
  }
}
?>
```

**Example \#4 Calling a stored procedure with an output parameter**

If the database driver supports it, an application may also bind
parameters for output as well as input. Output parameters are typically
used to retrieve values from stored procedures. Output parameters are
slightly more complex to use than input parameters, in that a developer
must know how large a given parameter might be when they bind it. If the
value turns out to be larger than the size they suggested, an error is
raised.

``` php
<?php
$stmt = $dbh->prepare("CALL sp_returns_string(?)");
$stmt->bindParam(1, $return_value, PDO::PARAM_STR, 4000); 

// call the stored procedure
$stmt->execute();

print "procedure returned $return_value\n";
?>
```

**Example \#5 Calling a stored procedure with an input/output
parameter**

Developers may also specify parameters that hold values both input and
output; the syntax is similar to output parameters. In this next
example, the string 'hello' is passed into the stored procedure, and
when it returns, hello is replaced with the return value of the
procedure.

``` php
<?php
$stmt = $dbh->prepare("CALL sp_takes_string_returns_string(?)");
$value = 'hello';
$stmt->bindParam(1, $value, PDO::PARAM_STR|PDO::PARAM_INPUT_OUTPUT, 4000); 

// call the stored procedure
$stmt->execute();

print "procedure returned $value\n";
?>
```

**Example \#6 Invalid use of placeholder**

``` php
<?php
$stmt = $dbh->prepare("SELECT * FROM REGISTRY where name LIKE '%?%'");
$stmt->execute(array($_GET['name']));

// placeholder must be used in the place of the whole value
$stmt = $dbh->prepare("SELECT * FROM REGISTRY where name LIKE ?");
$stmt->execute(array("%$_GET[name]%"));
?>
```

Errors and error handling
=========================

PDO offers you a choice of 3 different error handling strategies, to fit
your style of application development.

-   **`PDO::ERRMODE_SILENT`**

    This is the default mode. PDO will simply set the error code for you
    to inspect using the <span class="function">PDO::errorCode</span>
    and <span class="function">PDO::errorInfo</span> methods on both the
    statement and database objects; if the error resulted from a call on
    a statement object, you would invoke the <span
    class="function">PDOStatement::errorCode</span> or <span
    class="function">PDOStatement::errorInfo</span> method on that
    object. If the error resulted from a call on the database object,
    you would invoke those methods on the database object instead.

-   **`PDO::ERRMODE_WARNING`**

    In addition to setting the error code, PDO will emit a traditional
    E\_WARNING message. This setting is useful during debugging/testing,
    if you just want to see what problems occurred without interrupting
    the flow of the application.

-   **`PDO::ERRMODE_EXCEPTION`**

    In addition to setting the error code, PDO will throw a <span
    class="classname">PDOException</span> and set its properties to
    reflect the error code and error information. This setting is also
    useful during debugging, as it will effectively "blow up" the script
    at the point of the error, very quickly pointing a finger at
    potential problem areas in your code (remember: transactions are
    automatically rolled back if the exception causes the script to
    terminate).

    Exception mode is also useful because you can structure your error
    handling more clearly than with traditional PHP-style warnings, and
    with less code/nesting than by running in silent mode and explicitly
    checking the return value of each database call.

    See <a href="/language/exceptions.html" class="link">Exceptions</a>
    for more information about Exceptions in PHP.

PDO standardizes on using SQL-92 SQLSTATE error code strings; individual
PDO drivers are responsible for mapping their native codes to the
appropriate SQLSTATE codes. The <span
class="function">PDO::errorCode</span> method returns a single SQLSTATE
code. If you need more specific information about an error, PDO also
offers an <span class="function">PDO::errorInfo</span> method which
returns an array containing the SQLSTATE code, the driver specific error
code and driver specific error string.

**Example \#1 Create a PDO instance and set the error mode**

``` php
<?php
$dsn = 'mysql:dbname=testdb;host=127.0.0.1';
$user = 'dbuser';
$password = 'dbpass';

try {
    $dbh = new PDO($dsn, $user, $password);
    $dbh->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
} catch (PDOException $e) {
    echo 'Connection failed: ' . $e->getMessage();
}

?>
```

> **Note**:
>
> <span class="function">PDO::\_\_construct</span> will always throw a
> <span class="classname">PDOException</span> if the connection fails
> regardless of which **`PDO::ATTR_ERRMODE`** is currently set. Uncaught
> Exceptions are fatal.

**Example \#2 Create a PDO instance and set the error mode from the
constructor**

``` php
<?php
$dsn = 'mysql:dbname=test;host=127.0.0.1';
$user = 'googleguy';
$password = 'googleguy';

/*
    Using try/catch around the constructor is still valid even though we set the ERRMODE to WARNING since
    PDO::__construct will always throw a PDOException if the connection fails.
*/
try {
    $dbh = new PDO($dsn, $user, $password, array(PDO::ATTR_ERRMODE => PDO::ERRMODE_WARNING));
} catch (PDOException $e) {
    echo 'Connection failed: ' . $e->getMessage();
    exit;
}

// This will cause PDO to throw an error of level E_WARNING instead of an exception (when the table doesn't exist)
$dbh->query("SELECT wrongcolumn FROM wrongtable");
?>
```

The above example will output:

    Warning: PDO::query(): SQLSTATE[42S02]: Base table or view not found: 1146 Table 'test.wrongtable' doesn't exist in
    /tmp/pdo_test.php on line 18

Large Objects (LOBs)
====================

At some point in your application, you might find that you need to store
"large" data in your database. Large typically means "around 4kb or
more", although some databases can happily handle up to 32kb before data
becomes "large". Large objects can be either textual or binary in
nature. PDO allows you to work with this large data type by using the
**`PDO::PARAM_LOB`** type code in your <span
class="function">PDOStatement::bindParam</span> or <span
class="function">PDOStatement::bindColumn</span> calls.
**`PDO::PARAM_LOB`** tells PDO to map the data as a stream, so that you
can manipulate it using the
<a href="/ref/stream.html" class="link">PHP Streams API</a>.

**Example \#1 Displaying an image from a database**

This example binds the LOB into the variable named $lob and then sends
it to the browser using <span class="function">fpassthru</span>. Since
the LOB is represented as a stream, functions such as <span
class="function">fgets</span>, <span class="function">fread</span> and
<span class="function">stream\_get\_contents</span> can be used on it.

``` php
<?php
$db = new PDO('odbc:SAMPLE', 'db2inst1', 'ibmdb2');
$stmt = $db->prepare("select contenttype, imagedata from images where id=?");
$stmt->execute(array($_GET['id']));
$stmt->bindColumn(1, $type, PDO::PARAM_STR, 256);
$stmt->bindColumn(2, $lob, PDO::PARAM_LOB);
$stmt->fetch(PDO::FETCH_BOUND);

header("Content-Type: $type");
fpassthru($lob);
?>
```

**Example \#2 Inserting an image into a database**

This example opens up a file and passes the file handle to PDO to insert
it as a LOB. PDO will do its best to get the contents of the file up to
the database in the most efficient manner possible.

``` php
<?php
$db = new PDO('odbc:SAMPLE', 'db2inst1', 'ibmdb2');
$stmt = $db->prepare("insert into images (id, contenttype, imagedata) values (?, ?, ?)");
$id = get_new_id(); // some function to allocate a new ID

// assume that we are running as part of a file upload form
// You can find more information in the PHP documentation

$fp = fopen($_FILES['file']['tmp_name'], 'rb');

$stmt->bindParam(1, $id);
$stmt->bindParam(2, $_FILES['file']['type']);
$stmt->bindParam(3, $fp, PDO::PARAM_LOB);

$db->beginTransaction();
$stmt->execute();
$db->commit();
?>
```

**Example \#3 Inserting an image into a database: Oracle**

Oracle requires a slightly different syntax for inserting a lob from a
file. It's also essential that you perform the insert under a
transaction, otherwise your newly inserted LOB will be committed with a
zero-length as part of the implicit commit that happens when the query
is executed:

``` php
<?php
$db = new PDO('oci:', 'scott', 'tiger');
$stmt = $db->prepare("insert into images (id, contenttype, imagedata) " .
"VALUES (?, ?, EMPTY_BLOB()) RETURNING imagedata INTO ?");
$id = get_new_id(); // some function to allocate a new ID

// assume that we are running as part of a file upload form
// You can find more information in the PHP documentation

$fp = fopen($_FILES['file']['tmp_name'], 'rb');

$stmt->bindParam(1, $id);
$stmt->bindParam(2, $_FILES['file']['type']);
$stmt->bindParam(3, $fp, PDO::PARAM_LOB);

$db->beginTransaction();
$stmt->execute();
$db->commit();
?>
```

Introduction
------------

Represents a connection between PHP and a database server.

Class synopsis
--------------

**PDO**

<span class="ooclass"> class **PDO** </span> {

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$dsn`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$username`</span> \[, <span class="methodparam"><span
class="type">string</span> `$passwd`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">beginTransaction</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">commit</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">errorCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">errorInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">exec</span> ( <span class="methodparam"><span
class="type">string</span> `$statement`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getAttribute</span> ( <span
class="methodparam"><span class="type">int</span> `$attribute`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getAvailableDrivers</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">inTransaction</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">lastInsertId</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`<span
class="initializer"> = **`NULL`**</span></span> \] )

<span class="modifier">public</span> <span
class="type">PDOStatement</span> <span class="methodname">prepare</span>
( <span class="methodparam"><span class="type">string</span>
`$statement`</span> \[, <span class="methodparam"><span
class="type">array</span> `$driver_options`<span class="initializer"> =
array()</span></span> \] )

<span class="modifier">public</span> <span
class="type">PDOStatement</span> <span class="methodname">query</span> (
<span class="methodparam"><span class="type">string</span>
`$statement`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">quote</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$parameter_type`<span
class="initializer"> = PDO::PARAM\_STR</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">rollBack</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setAttribute</span> ( <span
class="methodparam"><span class="type">int</span> `$attribute`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

}

PDO::beginTransaction
=====================

Initiates a transaction

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::beginTransaction</span> ( <span
class="methodparam">void</span> )

Turns off autocommit mode. While autocommit mode is turned off, changes
made to the database via the PDO object instance are not committed until
you end the transaction by calling <span
class="function">PDO::commit</span>. Calling <span
class="function">PDO::rollBack</span> will roll back all changes to the
database and return the connection to autocommit mode.

Some databases, including MySQL, automatically issue an implicit COMMIT
when a database definition language (DDL) statement such as DROP TABLE
or CREATE TABLE is issued within a transaction. The implicit COMMIT will
prevent you from rolling back any other changes within the transaction
boundary.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

Throws a <span class="classname">PDOException</span> if there is already
a transaction started or the driver does not support transactions.

> **Note**: <span class="simpara">An exception is raised even when the
> **`PDO::ATTR_ERRMODE`** attribute is not
> **`PDO::ERRMODE_EXCEPTION`**.</span>

### Examples

**Example \#1 Roll back a transaction**

The following example begins a transaction and issues two statements
that modify the database before rolling back the changes. On MySQL,
however, the DROP TABLE statement automatically commits the transaction
so that none of the changes in the transaction are rolled back.

``` php
<?php
/* Begin a transaction, turning off autocommit */
$dbh->beginTransaction();

/* Change the database schema and data */
$sth = $dbh->exec("DROP TABLE fruit");
$sth = $dbh->exec("UPDATE dessert
    SET name = 'hamburger'");

/* Recognize mistake and roll back changes */
$dbh->rollBack();

/* Database connection is now back in autocommit mode */
?>
```

### See Also

-   <span class="function">PDO::commit</span>
-   <span class="function">PDO::rollBack</span>
-   <a href="/book/pdo.html#Transactions%20and%20auto-commit" class="link">Transactions and auto-commit</a>

PDO::commit
===========

Commits a transaction

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::commit</span> ( <span
class="methodparam">void</span> )

Commits a transaction, returning the database connection to autocommit
mode until the next call to <span
class="function">PDO::beginTransaction</span> starts a new transaction.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

Throws a <span class="classname">PDOException</span> if there is no
active transaction.

> **Note**: <span class="simpara">An exception is raised even when the
> **`PDO::ATTR_ERRMODE`** attribute is not
> **`PDO::ERRMODE_EXCEPTION`**.</span>

### Examples

**Example \#1 Committing a basic transaction**

``` php
<?php
/* Begin a transaction, turning off autocommit */
$dbh->beginTransaction();

/* Insert multiple records on an all-or-nothing basis */
$sql = 'INSERT INTO fruit
    (name, colour, calories)
    VALUES (?, ?, ?)';

$sth = $dbh->prepare($sql);

foreach ($fruits as $fruit) {
    $sth->execute(array(
        $fruit->name,
        $fruit->colour,
        $fruit->calories,
    ));
}

/* Commit the changes */
$dbh->commit();

/* Database connection is now back in autocommit mode */
?>
```

**Example \#2 Committing a DDL transaction**

``` php
<?php
/* Begin a transaction, turning off autocommit */
$dbh->beginTransaction();

/* Change the database schema */
$sth = $dbh->exec("DROP TABLE fruit");

/* Commit the changes */
$dbh->commit();

/* Database connection is now back in autocommit mode */
?>
```

> **Note**: <span class="simpara"> Not all databases will allow
> transactions to operate on DDL statements: some will generate errors,
> whereas others (including MySQL) will automatically commit the
> transaction after the first DDL statement has been encountered.
> </span>

### See Also

-   <span class="function">PDO::beginTransaction</span>
-   <span class="function">PDO::rollBack</span>
-   <a href="/book/pdo.html#Transactions%20and%20auto-commit" class="link">Transactions and auto-commit</a>

PDO::\_\_construct
==================

Creates a PDO instance representing a connection to a database

### Description

<span class="modifier">public</span> <span
class="methodname">PDO::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$dsn`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$username`</span> \[, <span class="methodparam"><span
class="type">string</span> `$passwd`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\] )

Creates a PDO instance to represent a connection to the requested
database.

### Parameters

dsn  
The Data Source Name, or DSN, contains the information required to
connect to the database.

In general, a DSN consists of the PDO driver name, followed by a colon,
followed by the PDO driver-specific connection syntax. Further
information is available from the
<a href="/book/pdo.html#PDO%20Drivers" class="link">PDO driver-specific documentation</a>.

The `dsn` parameter supports three different methods of specifying the
arguments required to create a database connection:

Driver invocation  
`dsn` contains the full DSN.

URI invocation  
`dsn` consists of **`uri:`** followed by a URI that defines the location
of a file containing the DSN string. The URI can specify a local file or
a remote URL.

**`uri:file:///path/to/dsnfile`**

Aliasing  
`dsn` consists of a name `name` that maps to `pdo.dsn.name` in `php.ini`
defining the DSN string.

> **Note**:
>
> The alias must be defined in `php.ini`, and not `.htaccess` or
> `httpd.conf`

username  
The user name for the DSN string. This parameter is optional for some
PDO drivers.

passwd  
The password for the DSN string. This parameter is optional for some PDO
drivers.

options  
A key=\>value array of driver-specific connection options.

### Return Values

Returns a PDO object on success.

### Errors/Exceptions

<span class="function">PDO::\_\_construct</span> throws a <span
class="classname">PDOException</span> if the attempt to connect to the
requested database fails.

### Examples

**Example \#1 Create a PDO instance via driver invocation**

``` php
<?php
/* Connect to a MySQL database using driver invocation */
$dsn = 'mysql:dbname=testdb;host=127.0.0.1';
$user = 'dbuser';
$password = 'dbpass';

try {
    $dbh = new PDO($dsn, $user, $password);
} catch (PDOException $e) {
    echo 'Connection failed: ' . $e->getMessage();
}

?>
```

**Example \#2 Create a PDO instance via URI invocation**

The following example assumes that the file `/usr/local/dbconnect`
exists with file permissions that enable PHP to read the file. The file
contains the PDO DSN to connect to a DB2 database through the PDO\_ODBC
driver:

    odbc:DSN=SAMPLE;UID=john;PWD=mypass

The PHP script can then create a database connection by simply passing
the *uri:* parameter and pointing to the file URI:

``` php
<?php
/* Connect to an ODBC database using driver invocation */
$dsn = 'uri:file:///usr/local/dbconnect';
$user = '';
$password = '';

try {
    $dbh = new PDO($dsn, $user, $password);
} catch (PDOException $e) {
    echo 'Connection failed: ' . $e->getMessage();
}

?>
```

**Example \#3 Create a PDO instance using an alias**

The following example assumes that `php.ini` contains the following
entry to enable a connection to a MySQL database using only the alias
*mydb*:

``` ini
[PDO]
pdo.dsn.mydb="mysql:dbname=testdb;host=localhost"
```

``` php
<?php
/* Connect to an ODBC database using an alias */
$dsn = 'mydb';
$user = '';
$password = '';

try {
    $dbh = new PDO($dsn, $user, $password);
} catch (PDOException $e) {
    echo 'Connection failed: ' . $e->getMessage();
}

?>
```

PDO::errorCode
==============

Fetch the SQLSTATE associated with the last operation on the database
handle

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">PDO::errorCode</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns an SQLSTATE, a five characters alphanumeric identifier defined
in the ANSI SQL-92 standard. Briefly, an SQLSTATE consists of a two
characters class value followed by a three characters subclass value. A
class value of 01 indicates a warning and is accompanied by a return
code of SQL\_SUCCESS\_WITH\_INFO. Class values other than '01', except
for the class 'IM', indicate an error. The class 'IM' is specific to
warnings and errors that derive from the implementation of PDO (or
perhaps ODBC, if you're using the ODBC driver) itself. The subclass
value '000' in any class indicates that there is no subclass for that
SQLSTATE.

<span class="function">PDO::errorCode</span> only retrieves error codes
for operations performed directly on the database handle. If you create
a PDOStatement object through <span class="function">PDO::prepare</span>
or <span class="function">PDO::query</span> and invoke an error on the
statement handle, <span class="function">PDO::errorCode</span> will not
reflect that error. You must call <span
class="function">PDOStatement::errorCode</span> to return the error code
for an operation performed on a particular statement handle.

Returns **`NULL`** if no operation has been run on the database handle.

### Examples

**Example \#1 Retrieving an SQLSTATE code**

``` php
<?php
/* Provoke an error -- the BONES table does not exist */
$dbh->exec("INSERT INTO bones(skull) VALUES ('lucy')");

echo "\nPDO::errorCode(): ", $dbh->errorCode();
?>
```

The above example will output:

    PDO::errorCode(): 42S02

### See Also

-   <span class="function">PDO::errorInfo</span>
-   <span class="function">PDOStatement::errorCode</span>
-   <span class="function">PDOStatement::errorInfo</span>

PDO::errorInfo
==============

Fetch extended error information associated with the last operation on
the database handle

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">PDO::errorInfo</span> ( <span
class="methodparam">void</span> )

### Return Values

<span class="function">PDO::errorInfo</span> returns an array of error
information about the last operation performed by this database handle.
The array consists of at least the following fields:

| Element | Information                                                                                       |
|---------|---------------------------------------------------------------------------------------------------|
| 0       | SQLSTATE error code (a five characters alphanumeric identifier defined in the ANSI SQL standard). |
| 1       | Driver-specific error code.                                                                       |
| 2       | Driver-specific error message.                                                                    |

> **Note**:
>
> If the SQLSTATE error code is not set or there is no driver-specific
> error, the elements following element 0 will be set to **`NULL`**.

<span class="function">PDO::errorInfo</span> only retrieves error
information for operations performed directly on the database handle. If
you create a PDOStatement object through <span
class="function">PDO::prepare</span> or <span
class="function">PDO::query</span> and invoke an error on the statement
handle, <span class="function">PDO::errorInfo</span> will not reflect
the error from the statement handle. You must call <span
class="function">PDOStatement::errorInfo</span> to return the error
information for an operation performed on a particular statement handle.

### Examples

**Example \#1 Displaying errorInfo() fields for a PDO\_ODBC connection
to a DB2 database**

``` php
<?php
/* Provoke an error -- bogus SQL syntax */
$stmt = $dbh->prepare('bogus sql');
if (!$stmt) {
    echo "\nPDO::errorInfo():\n";
    print_r($dbh->errorInfo());
}
?>
```

The above example will output:

    PDO::errorInfo():
    Array
    (
        [0] => HY000
        [1] => 1
        [2] => near "bogus": syntax error
    )

### See Also

-   <span class="function">PDO::errorCode</span>
-   <span class="function">PDOStatement::errorCode</span>
-   <span class="function">PDOStatement::errorInfo</span>

PDO::exec
=========

Execute an SQL statement and return the number of affected rows

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">PDO::exec</span> ( <span class="methodparam"><span
class="type">string</span> `$statement`</span> )

<span class="function">PDO::exec</span> executes an SQL statement in a
single function call, returning the number of rows affected by the
statement.

<span class="function">PDO::exec</span> does not return results from a
SELECT statement. For a SELECT statement that you only need to issue
once during your program, consider issuing <span
class="function">PDO::query</span>. For a statement that you need to
issue multiple times, prepare a PDOStatement object with <span
class="function">PDO::prepare</span> and issue the statement with <span
class="function">PDOStatement::execute</span>.

### Parameters

`statement`  
The SQL statement to prepare and execute.

Data inside the query should be
<a href="/book/pdo.html#PDO::quote" class="link">properly escaped</a>.

### Return Values

<span class="function">PDO::exec</span> returns the number of rows that
were modified or deleted by the SQL statement you issued. If no rows
were affected, <span class="function">PDO::exec</span> returns *0*.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

The following example incorrectly relies on the return value of <span
class="function">PDO::exec</span>, wherein a statement that affected 0
rows results in a call to <span class="function">die</span>:

``` php
<?php
$db->exec() or die(print_r($db->errorInfo(), true)); // incorrect
?>
```

### Examples

**Example \#1 Issuing a DELETE statement**

Count the number of rows deleted by a DELETE statement with no WHERE
clause.

``` php
<?php
$dbh = new PDO('odbc:sample', 'db2inst1', 'ibmdb2');

/* Delete all rows from the FRUIT table */
$count = $dbh->exec("DELETE FROM fruit");

/* Return number of rows that were deleted */
print("Deleted $count rows.\n");
?>
```

The above example will output:

    Deleted 1 rows.

### See Also

-   <span class="function">PDO::prepare</span>
-   <span class="function">PDO::query</span>
-   <span class="function">PDOStatement::execute</span>

PDO::getAttribute
=================

Retrieve a database connection attribute

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">PDO::getAttribute</span> ( <span
class="methodparam"><span class="type">int</span> `$attribute`</span> )

This function returns the value of a database connection attribute. To
retrieve PDOStatement attributes, refer to <span
class="function">PDOStatement::getAttribute</span>.

Note that some database/driver combinations may not support all of the
database connection attributes.

### Parameters

`attribute`  
One of the *PDO::ATTR\_\** constants. The constants that apply to
database connections are as follows:

-   *PDO::ATTR\_AUTOCOMMIT*
-   *PDO::ATTR\_CASE*
-   *PDO::ATTR\_CLIENT\_VERSION*
-   *PDO::ATTR\_CONNECTION\_STATUS*
-   *PDO::ATTR\_DRIVER\_NAME*
-   *PDO::ATTR\_ERRMODE*
-   *PDO::ATTR\_ORACLE\_NULLS*
-   *PDO::ATTR\_PERSISTENT*
-   *PDO::ATTR\_PREFETCH*
-   *PDO::ATTR\_SERVER\_INFO*
-   *PDO::ATTR\_SERVER\_VERSION*
-   *PDO::ATTR\_TIMEOUT*

### Return Values

A successful call returns the value of the requested PDO attribute. An
unsuccessful call returns *null*.

### Examples

**Example \#1 Retrieving database connection attributes**

``` php
<?php
$conn = new PDO('odbc:sample', 'db2inst1', 'ibmdb2');
$attributes = array(
    "AUTOCOMMIT", "ERRMODE", "CASE", "CLIENT_VERSION", "CONNECTION_STATUS",
    "ORACLE_NULLS", "PERSISTENT", "PREFETCH", "SERVER_INFO", "SERVER_VERSION",
    "TIMEOUT"
);

foreach ($attributes as $val) {
    echo "PDO::ATTR_$val: ";
    echo $conn->getAttribute(constant("PDO::ATTR_$val")) . "\n";
}
?>
```

### See Also

-   <span class="function">PDO::setAttribute</span>
-   <span class="function">PDOStatement::getAttribute</span>
-   <span class="function">PDOStatement::setAttribute</span>

PDO::getAvailableDrivers
========================

pdo\_drivers
============

Return an array of available PDO drivers

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">PDO::getAvailableDrivers</span> ( <span
class="methodparam">void</span> )

<span class="type">array</span> <span
class="methodname">pdo\_drivers</span> ( <span
class="methodparam">void</span> )

This function returns all currently available PDO drivers which can be
used in `DSN` parameter of <span
class="function">PDO::\_\_construct</span>.

### Return Values

<span class="function">PDO::getAvailableDrivers</span> returns an array
of PDO driver names. If no drivers are available, it returns an empty
array.

### Examples

**Example \#1 A <span class="function">PDO::getAvailableDrivers</span>
example**

``` php
<?php
print_r(PDO::getAvailableDrivers());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => mysql
        [1] => sqlite
    )

PDO::inTransaction
==================

Checks if inside a transaction

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::inTransaction</span> ( <span
class="methodparam">void</span> )

Checks if a transaction is currently active within the driver. This
method only works for database drivers that support transactions.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if a transaction is currently active, and **`FALSE`**
if not.

PDO::lastInsertId
=================

Returns the ID of the last inserted row or sequence value

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">PDO::lastInsertId</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`<span
class="initializer"> = **`NULL`**</span></span> \] )

Returns the ID of the last inserted row, or the last value from a
sequence object, depending on the underlying driver. For example,
<a href="/book/pdo.html#PostgreSQL%20(PDO)" class="link">PDO_PGSQL</a>
requires you to specify the name of a sequence object for the `name`
parameter.

> **Note**:
>
> This method may not return a meaningful or consistent result across
> different PDO drivers, because the underlying database may not even
> support the notion of auto-increment fields or sequences.

### Parameters

`name`  
Name of the sequence object from which the ID should be returned.

### Return Values

If a sequence name was not specified for the `name` parameter, <span
class="function">PDO::lastInsertId</span> returns a string representing
the row ID of the last row that was inserted into the database.

If a sequence name was specified for the `name` parameter, <span
class="function">PDO::lastInsertId</span> returns a string representing
the last value retrieved from the specified sequence object.

If the PDO driver does not support this capability, <span
class="function">PDO::lastInsertId</span> triggers an *IM001* SQLSTATE.

PDO::prepare
============

Prepares a statement for execution and returns a statement object

### Description

<span class="modifier">public</span> <span
class="type">PDOStatement</span> <span
class="methodname">PDO::prepare</span> ( <span class="methodparam"><span
class="type">string</span> `$statement`</span> \[, <span
class="methodparam"><span class="type">array</span>
`$driver_options`<span class="initializer"> = array()</span></span> \] )

Prepares an SQL statement to be executed by the <span
class="function">PDOStatement::execute</span> method. The statement
template can contain zero or more named (:name) or question mark (?)
parameter markers for which real values will be substituted when the
statement is executed. Both named and question mark parameter markers
cannot be used within the same statement template; only one or the other
parameter style. Use these parameters to bind any user-input, do not
include the user-input directly in the query.

You must include a unique parameter marker for each value you wish to
pass in to the statement when you call <span
class="function">PDOStatement::execute</span>. You cannot use a named
parameter marker of the same name more than once in a prepared
statement, unless emulation mode is on.

> **Note**:
>
> Parameter markers can represent a complete data literal only. Neither
> part of literal, nor keyword, nor identifier, nor whatever arbitrary
> query part can be bound using parameters. For example, you cannot bind
> multiple values to a single parameter in the IN() clause of an SQL
> statement.

Calling <span class="function">PDO::prepare</span> and <span
class="function">PDOStatement::execute</span> for statements that will
be issued multiple times with different parameter values optimizes the
performance of your application by allowing the driver to negotiate
client and/or server side caching of the query plan and meta
information. Also, calling <span class="function">PDO::prepare</span>
and <span class="function">PDOStatement::execute</span> helps to prevent
SQL injection attacks by eliminating the need to manually quote and
escape the parameters.

PDO will emulate prepared statements/bound parameters for drivers that
do not natively support them, and can also rewrite named or question
mark style parameter markers to something more appropriate, if the
driver supports one style but not the other.

> **Note**: <span class="simpara"> As of PHP 5.3.0, the parser used for
> emulated prepared statements and for rewriting named or question mark
> style parameters supports the non standard backslash escapes for
> single- and double quotes. That means that terminating quotes
> immediately preceeded by a backslash are not recognized as such, which
> may result in wrong detection of parameters causing the prepared
> statement to fail when it is executed. A work-around is to not use
> emulated prepares for such SQL queries, and to avoid rewriting of
> parameters by using a parameter style which is natively supported by
> the driver. </span>

### Parameters

`statement`  
This must be a valid SQL statement template for the target database
server.

`driver_options`  
This array holds one or more key=\>value pairs to set attribute values
for the PDOStatement object that this method returns. You would most
commonly use this to set the *PDO::ATTR\_CURSOR* value to
*PDO::CURSOR\_SCROLL* to request a scrollable cursor. Some drivers have
driver-specific options that may be set at prepare-time.

### Return Values

If the database server successfully prepares the statement, <span
class="function">PDO::prepare</span> returns a <span
class="classname">PDOStatement</span> object. If the database server
cannot successfully prepare the statement, <span
class="function">PDO::prepare</span> returns **`FALSE`** or emits <span
class="classname">PDOException</span> (depending on
<a href="/book/pdo.html#Errors%20and%20error%20handling" class="link">error handling</a>).

> **Note**:
>
> Emulated prepared statements does not communicate with the database
> server so <span class="function">PDO::prepare</span> does not check
> the statement.

### Examples

**Example \#1 SQL statement template with named parameters**

``` php
<?php
/* Execute a prepared statement by passing an array of values */
$sql = 'SELECT name, colour, calories
    FROM fruit
    WHERE calories < :calories AND colour = :colour';
$sth = $dbh->prepare($sql, array(PDO::ATTR_CURSOR => PDO::CURSOR_FWDONLY));
$sth->execute(array(':calories' => 150, ':colour' => 'red'));
$red = $sth->fetchAll();
$sth->execute(array(':calories' => 175, ':colour' => 'yellow'));
$yellow = $sth->fetchAll();
?>
```

**Example \#2 SQL statement template with question mark parameters**

``` php
<?php
/* Execute a prepared statement by passing an array of values */
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < ? AND colour = ?');
$sth->execute(array(150, 'red'));
$red = $sth->fetchAll();
$sth->execute(array(175, 'yellow'));
$yellow = $sth->fetchAll();
?>
```

### See Also

-   <span class="function">PDO::exec</span>
-   <span class="function">PDO::query</span>
-   <span class="function">PDOStatement::execute</span>

PDO::query
==========

Executes an SQL statement, returning a result set as a PDOStatement
object

### Description

<span class="modifier">public</span> <span
class="type">PDOStatement</span> <span
class="methodname">PDO::query</span> ( <span class="methodparam"><span
class="type">string</span> `$statement`</span> )

<span class="modifier">public</span> <span
class="type">PDOStatement</span> <span
class="methodname">PDO::query</span> ( <span class="methodparam"><span
class="type">string</span> `$statement`</span> , <span
class="methodparam"><span class="type">int</span> `$fetch_style`<span
class="initializer"> = PDO::FETCH\_COLUMN</span></span> , <span
class="methodparam"><span class="type">int</span> `$colno`</span> )

<span class="modifier">public</span> <span
class="type">PDOStatement</span> <span
class="methodname">PDO::query</span> ( <span class="methodparam"><span
class="type">string</span> `$statement`</span> , <span
class="methodparam"><span class="type">int</span> `$fetch_style`<span
class="initializer"> = PDO::FETCH\_CLASS</span></span> , <span
class="methodparam"><span class="type">string</span> `$classname`</span>
, <span class="methodparam"><span class="type">array</span>
`$ctorargs`</span> )

<span class="modifier">public</span> <span
class="type">PDOStatement</span> <span
class="methodname">PDO::query</span> ( <span class="methodparam"><span
class="type">string</span> `$statement`</span> , <span
class="methodparam"><span class="type">int</span> `$fetch_style`<span
class="initializer"> = PDO::FETCH\_INTO</span></span> , <span
class="methodparam"><span class="type">object</span> `$object`</span> )

<span class="function">PDO::query</span> executes an SQL statement in a
single function call, returning the result set (if any) returned by the
statement as a PDOStatement object.

For a query that you need to issue multiple times, you will realize
better performance if you prepare a PDOStatement object using <span
class="function">PDO::prepare</span> and issue the statement with
multiple calls to <span class="function">PDOStatement::execute</span>.

If you do not fetch all of the data in a result set before issuing your
next call to <span class="function">PDO::query</span>, your call may
fail. Call <span class="function">PDOStatement::closeCursor</span> to
release the database resources associated with the PDOStatement object
before issuing your next call to <span
class="function">PDO::query</span>.

> **Note**:
>
> If more than one argument is passed to this function, the remaining
> arguments will be treated as though you called <span
> class="function">PDOStatement::setFetchMode</span> on the resultant
> statement object.

### Parameters

`statement`  
The SQL statement to prepare and execute.

Data inside the query should be
<a href="/book/pdo.html#PDO::quote" class="link">properly escaped</a>.

### Return Values

<span class="function">PDO::query</span> returns a PDOStatement object,
or **`FALSE`** on failure.

### Examples

**Example \#1 Demonstrate PDO::query**

A nice feature of <span class="function">PDO::query</span> is that it
enables you to iterate over the rowset returned by a successfully
executed SELECT statement.

``` php
<?php
$sql = 'SELECT name, color, calories FROM fruit ORDER BY name';
foreach ($conn->query($sql) as $row) {
    print $row['name'] . "\t";
    print $row['color'] . "\t";
    print $row['calories'] . "\n";
}
?>
```

The above example will output:

    apple   red     150
    banana  yellow  250
    kiwi    brown   75
    lemon   yellow  25
    orange  orange  300
    pear    green   150
    watermelon      pink    90

### See Also

-   <span class="function">PDO::exec</span>
-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::execute</span>

PDO::quote
==========

Quotes a string for use in a query

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">PDO::quote</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$parameter_type`<span class="initializer"> =
PDO::PARAM\_STR</span></span> \] )

<span class="function">PDO::quote</span> places quotes around the input
string (if required) and escapes special characters within the input
string, using a quoting style appropriate to the underlying driver.

If you are using this function to build SQL statements, you are
*strongly* recommended to use <span class="function">PDO::prepare</span>
to prepare SQL statements with bound parameters instead of using <span
class="function">PDO::quote</span> to interpolate user input into an SQL
statement. Prepared statements with bound parameters are not only more
portable, more convenient, immune to SQL injection, but are often much
faster to execute than interpolated queries, as both the server and
client side can cache a compiled form of the query.

Not all PDO drivers implement this method (notably PDO\_ODBC). Consider
using prepared statements instead.

**Caution**

The character set must be set either on the server level, or within the
database connection itself (depending on the driver) for it to affect
<span class="methodname">PDO::quote</span>. See the
<a href="/book/pdo.html#PDO%20Drivers" class="link">driver-specific documentation</a>
for more information.

### Parameters

`string`  
The string to be quoted.

`parameter_type`  
Provides a data type hint for drivers that have alternate quoting
styles.

### Return Values

Returns a quoted string that is theoretically safe to pass into an SQL
statement. Returns **`FALSE`** if the driver does not support quoting in
this way.

### Examples

**Example \#1 Quoting a normal string**

``` php
<?php
$conn = new PDO('sqlite:/home/lynn/music.sql3');

/* Simple string */
$string = 'Nice';
print "Unquoted string: $string\n";
print "Quoted string: " . $conn->quote($string) . "\n";
?>
```

The above example will output:

    Unquoted string: Nice
    Quoted string: 'Nice'

**Example \#2 Quoting a dangerous string**

``` php
<?php
$conn = new PDO('sqlite:/home/lynn/music.sql3');

/* Dangerous string */
$string = 'Naughty \' string';
print "Unquoted string: $string\n";
print "Quoted string:" . $conn->quote($string) . "\n";
?>
```

The above example will output:

    Unquoted string: Naughty ' string
    Quoted string: 'Naughty '' string'

**Example \#3 Quoting a complex string**

``` php
<?php
$conn = new PDO('sqlite:/home/lynn/music.sql3');

/* Complex string */
$string = "Co'mpl''ex \"st'\"ring";
print "Unquoted string: $string\n";
print "Quoted string: " . $conn->quote($string) . "\n";
?>
```

The above example will output:

    Unquoted string: Co'mpl''ex "st'"ring
    Quoted string: 'Co''mpl''''ex "st''"ring'

### See Also

-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::execute</span>

PDO::rollBack
=============

Rolls back a transaction

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::rollBack</span> ( <span
class="methodparam">void</span> )

Rolls back the current transaction, as initiated by <span
class="function">PDO::beginTransaction</span>.

If the database was set to autocommit mode, this function will restore
autocommit mode after it has rolled back the transaction.

Some databases, including MySQL, automatically issue an implicit COMMIT
when a database definition language (DDL) statement such as DROP TABLE
or CREATE TABLE is issued within a transaction. The implicit COMMIT will
prevent you from rolling back any other changes within the transaction
boundary.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

Throws a <span class="classname">PDOException</span> if there is no
active transaction.

> **Note**: <span class="simpara">An exception is raised even when the
> **`PDO::ATTR_ERRMODE`** attribute is not
> **`PDO::ERRMODE_EXCEPTION`**.</span>

### Examples

**Example \#1 Roll back a transaction**

The following example begins a transaction and issues two statements
that modify the database before rolling back the changes. On MySQL,
however, the DROP TABLE statement automatically commits the transaction
so that none of the changes in the transaction are rolled back.

``` php
<?php
/* Begin a transaction, turning off autocommit */
$dbh->beginTransaction();

/* Change the database schema and data */
$sth = $dbh->exec("DROP TABLE fruit");
$sth = $dbh->exec("UPDATE dessert
    SET name = 'hamburger'");

/* Recognize mistake and roll back changes */
$dbh->rollBack();

/* Database connection is now back in autocommit mode */
?>
```

### See Also

-   <span class="function">PDO::beginTransaction</span>
-   <span class="function">PDO::commit</span>
-   <a href="/book/pdo.html#Transactions%20and%20auto-commit" class="link">Transactions and auto-commit</a>

PDO::setAttribute
=================

Set an attribute

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::setAttribute</span> ( <span
class="methodparam"><span class="type">int</span> `$attribute`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

Sets an attribute on the database handle. Some of the available generic
attributes are listed below; some drivers may make use of additional
driver specific attributes.

-   *PDO::ATTR\_CASE*: Force column names to a specific case.

    -   *PDO::CASE\_LOWER*: Force column names to lower case.

    -   *PDO::CASE\_NATURAL*: Leave column names as returned by the
        database driver.

    -   *PDO::CASE\_UPPER*: Force column names to upper case.

-   *PDO::ATTR\_ERRMODE*: Error reporting.

    -   *PDO::ERRMODE\_SILENT*: Just set error codes.

    -   *PDO::ERRMODE\_WARNING*: Raise **`E_WARNING`**.

    -   *PDO::ERRMODE\_EXCEPTION*: Throw
        <a href="/book/pdo.html#PDOException" class="link">exceptions</a>.

-   *PDO::ATTR\_ORACLE\_NULLS* (available with all drivers, not just
    Oracle): Conversion of NULL and empty strings.

    -   *PDO::NULL\_NATURAL*: No conversion.

    -   *PDO::NULL\_EMPTY\_STRING*: Empty string is converted to
        **`NULL`**.

    -   *PDO::NULL\_TO\_STRING*: NULL is converted to an empty string.

-   *PDO::ATTR\_STRINGIFY\_FETCHES*: Convert numeric values to strings
    when fetching. Requires <span class="type">bool</span>.

-   *PDO::ATTR\_STATEMENT\_CLASS*: Set user-supplied statement class
    derived from PDOStatement. Cannot be used with persistent PDO
    instances. Requires *array(string classname, array(mixed
    constructor\_args))*.

-   *PDO::ATTR\_TIMEOUT*: Specifies the timeout duration in seconds. Not
    all drivers support this option, and its meaning may differ from
    driver to driver. For example, sqlite will wait for up to this time
    value before giving up on obtaining an writable lock, but other
    drivers may interpret this as a connect or a read timeout interval.
    Requires <span class="type">int</span>.

-   *PDO::ATTR\_AUTOCOMMIT* (available in OCI, Firebird and MySQL):
    Whether to autocommit every single statement.

-   *PDO::ATTR\_EMULATE\_PREPARES* Enables or disables emulation of
    prepared statements. Some drivers do not support native prepared
    statements or have limited support for them. Use this setting to
    force PDO to either always emulate prepared statements (if
    **`TRUE`** and emulated prepares are supported by the driver), or to
    try to use native prepared statements (if **`FALSE`**). It will
    always fall back to emulating the prepared statement if the driver
    cannot successfully prepare the current query. Requires <span
    class="type">bool</span>.

-   *PDO::MYSQL\_ATTR\_USE\_BUFFERED\_QUERY* (available in MySQL): Use
    buffered queries.

-   *PDO::ATTR\_DEFAULT\_FETCH\_MODE*: Set default fetch mode.
    Description of modes is available in <span
    class="function">PDOStatement::fetch</span> documentation.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

Introduction
------------

Represents a prepared statement and, after the statement is executed, an
associated result set.

Class synopsis
--------------

**PDOStatement**

<span class="ooclass"> class **PDOStatement** </span> <span
class="oointerface">implements <span
class="interfacename">Traversable</span> </span> {

/\* Properties \*/

<span class="modifier">readonly</span> <span
class="type">string</span>`$queryString`;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">bindColumn</span> ( <span
class="methodparam"><span class="type">mixed</span> `$column`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`&$param`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`</span> \[, <span
class="methodparam"><span class="type">int</span> `$maxlen`</span> \[,
<span class="methodparam"><span class="type">mixed</span>
`$driverdata`</span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">bindParam</span> ( <span
class="methodparam"><span class="type">mixed</span> `$parameter`</span>
, <span class="methodparam"><span class="type">mixed</span>
`&$variable`</span> \[, <span class="methodparam"><span
class="type">int</span> `$data_type`<span class="initializer"> =
PDO::PARAM\_STR</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$driver_options`</span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">bindValue</span> ( <span
class="methodparam"><span class="type">mixed</span> `$parameter`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$data_type`<span class="initializer"> =
PDO::PARAM\_STR</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">closeCursor</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">columnCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">debugDumpParams</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">errorCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">errorInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">execute</span> (\[ <span
class="methodparam"><span class="type">array</span>
`$input_parameters`<span class="initializer"> = **`NULL`**</span></span>
\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">fetch</span> (\[ <span
class="methodparam"><span class="type">int</span> `$fetch_style`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$cursor_orientation`<span class="initializer"> =
PDO::FETCH\_ORI\_NEXT</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$cursor_offset`<span class="initializer"> =
0</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">fetchAll</span> (\[ <span
class="methodparam"><span class="type">int</span> `$fetch_style`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$fetch_argument`</span> \[, <span class="methodparam"><span
class="type">array</span> `$ctor_args`<span class="initializer"> =
array()</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">fetchColumn</span> (\[ <span
class="methodparam"><span class="type">int</span> `$column_number`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">object</span><span class="type">false</span></span> <span
class="methodname">fetchObject</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "stdClass"</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$ctor_args`</span>
\]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">getAttribute</span> ( <span
class="methodparam"><span class="type">int</span> `$attribute`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getColumnMeta</span> ( <span
class="methodparam"><span class="type">int</span> `$column`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">nextRowset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">rowCount</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setAttribute</span> ( <span
class="methodparam"><span class="type">int</span> `$attribute`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setFetchMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

}

Properties
----------

`queryString`  
Used query string.

PDOStatement::bindColumn
========================

Bind a column to a PHP variable

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::bindColumn</span> ( <span
class="methodparam"><span class="type">mixed</span> `$column`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`&$param`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`</span> \[, <span
class="methodparam"><span class="type">int</span> `$maxlen`</span> \[,
<span class="methodparam"><span class="type">mixed</span>
`$driverdata`</span> \]\]\] )

<span class="function">PDOStatement::bindColumn</span> arranges to have
a particular variable bound to a given column in the result-set from a
query. Each call to <span class="function">PDOStatement::fetch</span> or
<span class="function">PDOStatement::fetchAll</span> will update all the
variables that are bound to columns.

> **Note**:
>
> Since information about the columns is not always available to PDO
> until the statement is executed, portable applications should call
> this function *after* <span
> class="function">PDOStatement::execute</span>.
>
> However, to be able to bind a LOB column as a stream when using the
> *PgSQL driver*, applications should call this method *before* calling
> <span class="function">PDOStatement::execute</span>, otherwise the
> large object OID will be returned as an integer.

### Parameters

`column`  
Number of the column (1-indexed) or name of the column in the result
set. If using the column name, be aware that the name should match the
case of the column, as returned by the driver.

`param`  
Name of the PHP variable to which the column will be bound.

`type`  
Data type of the parameter, specified by the
<a href="/book/pdo.html#Predefined%20Constants" class="link"><em>PDO::PARAM_*</em> constants</a>.

`maxlen`  
A hint for pre-allocation.

`driverdata`  
Optional parameter(s) for the driver.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Binding result set output to PHP variables**

Binding columns in the result set to PHP variables is an effective way
to make the data contained in each row immediately available to your
application. The following example demonstrates how PDO allows you to
bind and retrieve columns with a variety of options and with intelligent
defaults.

``` php
<?php
function readData($dbh) {
  $sql = 'SELECT name, colour, calories FROM fruit';
  try {
    $stmt = $dbh->prepare($sql);
    $stmt->execute();

    /* Bind by column number */
    $stmt->bindColumn(1, $name);
    $stmt->bindColumn(2, $colour);
    
    /* Bind by column name */
    $stmt->bindColumn('calories', $cals);

    while ($row = $stmt->fetch(PDO::FETCH_BOUND)) {
      $data = $name . "\t" . $colour . "\t" . $cals . "\n";
      print $data;
    }
  }
  catch (PDOException $e) {
    print $e->getMessage();
  }
}
readData($dbh);
?>
```

The above example will output:

    apple   red     150
    banana  yellow  175
    kiwi    green   75
    orange  orange  150
    mango   red     200
    strawberry      red     25

### See Also

-   <span class="function">PDOStatement::execute</span>
-   <span class="function">PDOStatement::fetch</span>
-   <span class="function">PDOStatement::fetchAll</span>
-   <span class="function">PDOStatement::fetchColumn</span>

PDOStatement::bindParam
=======================

Binds a parameter to the specified variable name

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::bindParam</span> ( <span
class="methodparam"><span class="type">mixed</span> `$parameter`</span>
, <span class="methodparam"><span class="type">mixed</span>
`&$variable`</span> \[, <span class="methodparam"><span
class="type">int</span> `$data_type`<span class="initializer"> =
PDO::PARAM\_STR</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$driver_options`</span> \]\]\] )

Binds a PHP variable to a corresponding named or question mark
placeholder in the SQL statement that was used to prepare the statement.
Unlike <span class="function">PDOStatement::bindValue</span>, the
variable is bound as a reference and will only be evaluated at the time
that <span class="function">PDOStatement::execute</span> is called.

Most parameters are input parameters, that is, parameters that are used
in a read-only fashion to build up the query (but may nonetheless be
cast according to `data_type`). Some drivers support the invocation of
stored procedures that return data as output parameters, and some also
as input/output parameters that both send in data and are updated to
receive it.

### Parameters

`parameter`  
Parameter identifier. For a prepared statement using named placeholders,
this will be a parameter name of the form `:name`. For a prepared
statement using question mark placeholders, this will be the 1-indexed
position of the parameter.

`variable`  
Name of the PHP variable to bind to the SQL statement parameter.

`data_type`  
Explicit data type for the parameter using the
<a href="/book/pdo.html#Predefined%20Constants" class="link"><em>PDO::PARAM_*</em> constants</a>.
To return an INOUT parameter from a stored procedure, use the bitwise OR
operator to set the PDO::PARAM\_INPUT\_OUTPUT bits for the `data_type`
parameter.

`length`  
Length of the data type. To indicate that a parameter is an OUT
parameter from a stored procedure, you must explicitly set the length.

`driver_options`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Execute a prepared statement with named placeholders**

``` php
<?php
/* Execute a prepared statement by binding PHP variables */
$calories = 150;
$colour = 'red';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < :calories AND colour = :colour');
$sth->bindParam(':calories', $calories, PDO::PARAM_INT);
$sth->bindParam(':colour', $colour, PDO::PARAM_STR, 12);
$sth->execute();
?>
```

**Example \#2 Execute a prepared statement with question mark
placeholders**

``` php
<?php
/* Execute a prepared statement by binding PHP variables */
$calories = 150;
$colour = 'red';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < ? AND colour = ?');
$sth->bindParam(1, $calories, PDO::PARAM_INT);
$sth->bindParam(2, $colour, PDO::PARAM_STR, 12);
$sth->execute();
?>
```

**Example \#3 Call a stored procedure with an INOUT parameter**

``` php
<?php
/* Call a stored procedure with an INOUT parameter */
$colour = 'red';
$sth = $dbh->prepare('CALL puree_fruit(?)');
$sth->bindParam(1, $colour, PDO::PARAM_STR|PDO::PARAM_INPUT_OUTPUT, 12);
$sth->execute();
print("After pureeing fruit, the colour is: $colour");
?>
```

### See Also

-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::execute</span>
-   <span class="function">PDOStatement::bindValue</span>

PDOStatement::bindValue
=======================

Binds a value to a parameter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::bindValue</span> ( <span
class="methodparam"><span class="type">mixed</span> `$parameter`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$data_type`<span class="initializer"> =
PDO::PARAM\_STR</span></span> \] )

Binds a value to a corresponding named or question mark placeholder in
the SQL statement that was used to prepare the statement.

### Parameters

`parameter`  
Parameter identifier. For a prepared statement using named placeholders,
this will be a parameter name of the form `:name`. For a prepared
statement using question mark placeholders, this will be the 1-indexed
position of the parameter.

`value`  
The value to bind to the parameter.

`data_type`  
Explicit data type for the parameter using the
<a href="/book/pdo.html#Predefined%20Constants" class="link"><em>PDO::PARAM_*</em> constants</a>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Execute a prepared statement with named placeholders**

``` php
<?php
/* Execute a prepared statement by binding PHP variables */
$calories = 150;
$colour = 'red';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < :calories AND colour = :colour');
$sth->bindValue(':calories', $calories, PDO::PARAM_INT);
$sth->bindValue(':colour', $colour, PDO::PARAM_STR);
$sth->execute();
?>
```

**Example \#2 Execute a prepared statement with question mark
placeholders**

``` php
<?php
/* Execute a prepared statement by binding PHP variables */
$calories = 150;
$colour = 'red';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < ? AND colour = ?');
$sth->bindValue(1, $calories, PDO::PARAM_INT);
$sth->bindValue(2, $colour, PDO::PARAM_STR);
$sth->execute();
?>
```

### See Also

-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::execute</span>
-   <span class="function">PDOStatement::bindParam</span>

PDOStatement::closeCursor
=========================

Closes the cursor, enabling the statement to be executed again

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::closeCursor</span> ( <span
class="methodparam">void</span> )

<span class="function">PDOStatement::closeCursor</span> frees up the
connection to the server so that other SQL statements may be issued, but
leaves the statement in a state that enables it to be executed again.

This method is useful for database drivers that do not support executing
a PDOStatement object when a previously executed PDOStatement object
still has unfetched rows. If your database driver suffers from this
limitation, the problem may manifest itself in an out-of-sequence error.

<span class="function">PDOStatement::closeCursor</span> is implemented
either as an optional driver specific method (allowing for maximum
efficiency), or as the generic PDO fallback if no driver specific
function is installed. The PDO generic fallback is semantically the same
as writing the following code in your PHP script:

``` php
<?php
do {
    while ($stmt->fetch())
        ;
    if (!$stmt->nextRowset())
        break;
} while (true);
?>
```

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">PDOStatement::closeCursor</span>
example**

In the following example, the `$stmt` PDOStatement object returns
multiple rows but the application fetches only the first row, leaving
the PDOStatement object in a state of having unfetched rows. To ensure
that the application will work with all database drivers, the author
inserts a call to <span
class="function">PDOStatement::closeCursor</span> on `$stmt` before
executing the `$otherStmt` PDOStatement object.

``` php
<?php
/* Create a PDOStatement object */
$stmt = $dbh->prepare('SELECT foo FROM bar');

/* Create a second PDOStatement object */
$otherStmt = $dbh->prepare('SELECT foobaz FROM foobar');

/* Execute the first statement */
$stmt->execute();

/* Fetch only the first row from the results */
$stmt->fetch();

/* The following call to closeCursor() may be required by some drivers */
$stmt->closeCursor();

/* Now we can execute the second statement */
$otherStmt->execute();
?>
```

### See Also

-   <span class="function">PDOStatement::execute</span>

PDOStatement::columnCount
=========================

Returns the number of columns in the result set

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">PDOStatement::columnCount</span> ( <span
class="methodparam">void</span> )

Use <span class="function">PDOStatement::columnCount</span> to return
the number of columns in the result set represented by the PDOStatement
object.

If the PDOStatement object was returned from <span
class="function">PDO::query</span>, the column count is immediately
available.

If the PDOStatement object was returned from <span
class="function">PDO::prepare</span>, an accurate column count will not
be available until you invoke <span
class="function">PDOStatement::execute</span>.

### Return Values

Returns the number of columns in the result set represented by the
PDOStatement object, even if the result set is empty. If there is no
result set, <span class="function">PDOStatement::columnCount</span>
returns *0*.

### Examples

**Example \#1 Counting columns**

This example demonstrates how <span
class="function">PDOStatement::columnCount</span> operates with and
without a result set.

``` php
<?php
$dbh = new PDO('odbc:sample', 'db2inst1', 'ibmdb2');

$sth = $dbh->prepare("SELECT name, colour FROM fruit");

/* Count the number of columns in the (non-existent) result set */
$colcount = $sth->columnCount();
print("Before execute(), result set has $colcount columns (should be 0)\n");

$sth->execute();

/* Count the number of columns in the result set */
$colcount = $sth->columnCount();
print("After execute(), result set has $colcount columns (should be 2)\n");

?>
```

The above example will output:

    Before execute(), result set has 0 columns (should be 0)
    After execute(), result set has 2 columns (should be 2)

### See Also

-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::execute</span>
-   <span class="function">PDOStatement::rowCount</span>

PDOStatement::debugDumpParams
=============================

Dump an SQL prepared command

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">PDOStatement::debugDumpParams</span> ( <span
class="methodparam">void</span> )

Dumps the information contained by a prepared statement directly on the
output. It will provide the *SQL* query in use, the number of parameters
used (*Params*), the list of parameters with their key name or position,
their name, their position in the query (if this is supported by the PDO
driver, otherwise, it will be -1), type (*param\_type*) as an integer,
and a boolean value *is\_param*.

This is a debug function, which dumps the data directly to the normal
output.

**Tip**

As with anything that outputs its result directly to the browser, the
<a href="/book/outcontrol.html" class="link">output-control functions</a>
can be used to capture the output of this function, and save it in a
<span class="type">string</span> (for example).

This will only dump the parameters in the statement at the moment of the
dump. Extra parameters are not stored in the statement, and not
displayed.

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">PDOStatement::debugDumpParams</span> example with named
parameters**

``` php
<?php
/* Execute a prepared statement by binding PHP variables */
$calories = 150;
$colour = 'red';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < :calories AND colour = :colour');
$sth->bindParam(':calories', $calories, PDO::PARAM_INT);
$sth->bindValue(':colour', $colour, PDO::PARAM_STR, 12);
$sth->execute();

$sth->debugDumpParams();

?>
```

The above example will output:

    SQL: [96] SELECT name, colour, calories
        FROM fruit
        WHERE calories < :calories AND colour = :colour
    Params:  2
    Key: Name: [9] :calories
    paramno=-1
    name=[9] ":calories"
    is_param=1
    param_type=1
    Key: Name: [7] :colour
    paramno=-1
    name=[7] ":colour"
    is_param=1
    param_type=2

**Example \#2 <span
class="function">PDOStatement::debugDumpParams</span> example with
unnamed parameters**

``` php
<?php

/* Execute a prepared statement by binding PHP variables */
$calories = 150;
$colour = 'red';
$name = 'apple';

$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < ? AND colour = ?');
$sth->bindParam(1, $calories, PDO::PARAM_INT);
$sth->bindValue(2, $colour, PDO::PARAM_STR);
$sth->execute();

$sth->debugDumpParams();

?>
```

The above example will output:

    SQL: [82] SELECT name, colour, calories
        FROM fruit
        WHERE calories < ? AND colour = ?
    Params:  2
    Key: Position #0:
    paramno=0
    name=[0] ""
    is_param=1
    param_type=1
    Key: Position #1:
    paramno=1
    name=[0] ""
    is_param=1
    param_type=2

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                  |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="methodname">PDOStatement::debugDumpParams</span> now returns the SQL sent to the database, including the full, raw query (including the replaced placeholders with their bounded values). Note, that this will only be available if emulated prepared statements are turned on. |

### See Also

-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::bindParam</span>
-   <span class="function">PDOStatement::bindValue</span>

PDOStatement::errorCode
=======================

Fetch the SQLSTATE associated with the last operation on the statement
handle

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">PDOStatement::errorCode</span> ( <span
class="methodparam">void</span> )

### Return Values

Identical to <span class="function">PDO::errorCode</span>, except that
<span class="function">PDOStatement::errorCode</span> only retrieves
error codes for operations performed with PDOStatement objects.

### Examples

**Example \#1 Retrieving an SQLSTATE code**

``` php
<?php
/* Provoke an error -- the BONES table does not exist */
$err = $dbh->prepare('SELECT skull FROM bones');
$err->execute();

echo "\nPDOStatement::errorCode(): ";
print $err->errorCode();
?>
```

The above example will output:

    PDOStatement::errorCode(): 42S02

### See Also

-   <span class="function">PDO::errorCode</span>
-   <span class="function">PDO::errorInfo</span>
-   <span class="function">PDOStatement::errorInfo</span>

PDOStatement::errorInfo
=======================

Fetch extended error information associated with the last operation on
the statement handle

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">PDOStatement::errorInfo</span> ( <span
class="methodparam">void</span> )

### Return Values

<span class="function">PDOStatement::errorInfo</span> returns an array
of error information about the last operation performed by this
statement handle. The array consists of at least the following fields:

| Element | Information                                                                                       |
|---------|---------------------------------------------------------------------------------------------------|
| 0       | SQLSTATE error code (a five characters alphanumeric identifier defined in the ANSI SQL standard). |
| 1       | Driver specific error code.                                                                       |
| 2       | Driver specific error message.                                                                    |

### Examples

**Example \#1 Displaying errorInfo() fields for a PDO\_ODBC connection
to a DB2 database**

``` php
<?php
/* Provoke an error -- the BONES table does not exist */
$sth = $dbh->prepare('SELECT skull FROM bones');
$sth->execute();

echo "\nPDOStatement::errorInfo():\n";
$arr = $sth->errorInfo();
print_r($arr);
?>
```

The above example will output:

    PDOStatement::errorInfo():
    Array
    (
        [0] => 42S02
        [1] => -204
        [2] => [IBM][CLI Driver][DB2/LINUX] SQL0204N  "DANIELS.BONES" is an undefined name.  SQLSTATE=42704
    )

### See Also

-   <span class="function">PDO::errorCode</span>
-   <span class="function">PDO::errorInfo</span>
-   <span class="function">PDOStatement::errorCode</span>

PDOStatement::execute
=====================

Executes a prepared statement

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::execute</span> (\[ <span
class="methodparam"><span class="type">array</span>
`$input_parameters`<span class="initializer"> = **`NULL`**</span></span>
\] )

Execute the
<a href="/book/pdo.html#Prepared%20statements%20and%20stored%20procedures" class="link">prepared statement</a>.
If the prepared statement included parameter markers, either:

-   <span class="function">PDOStatement::bindParam</span> and/or <span
    class="function">PDOStatement::bindValue</span> has to be called to
    bind either variables or values (respectively) to the parameter
    markers. Bound variables pass their value as input and receive the
    output value, if any, of their associated parameter markers

-   or an array of input-only parameter values has to be passed

### Parameters

`input_parameters`  
An array of values with as many elements as there are bound parameters
in the SQL statement being executed. All values are treated as
**`PDO::PARAM_STR`**.

Multiple values cannot be bound to a single parameter; for example, it
is not allowed to bind two values to a single named parameter in an IN()
clause.

Binding more values than specified is not possible; if more keys exist
in `input_parameters` than in the SQL specified in the <span
class="methodname">PDO::prepare</span>, then the statement will fail and
an error is emitted.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Execute a prepared statement with a bound variable and
value**

``` php
<?php
/* Execute a prepared statement by binding a variable and value */
$calories = 150;
$colour = 'gre';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < :calories AND colour LIKE :colour');
$sth->bindParam(':calories', $calories, PDO::PARAM_INT);
$sth->bindValue(':colour', "%{$colour}%");
$sth->execute();
?>
```

**Example \#2 Execute a prepared statement with an array of insert
values (named parameters)**

``` php
<?php
/* Execute a prepared statement by passing an array of insert values */
$calories = 150;
$colour = 'red';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < :calories AND colour = :colour');
$sth->execute(array(':calories' => $calories, ':colour' => $colour));
?>
```

**Example \#3 Execute a prepared statement with an array of insert
values (placeholders)**

``` php
<?php
/* Execute a prepared statement by passing an array of insert values */
$calories = 150;
$colour = 'red';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < ? AND colour = ?');
$sth->execute(array($calories, $colour));
?>
```

**Example \#4 Execute a prepared statement with question mark
placeholders**

``` php
<?php
/* Execute a prepared statement by binding PHP variables */
$calories = 150;
$colour = 'red';
$sth = $dbh->prepare('SELECT name, colour, calories
    FROM fruit
    WHERE calories < ? AND colour = ?');
$sth->bindParam(1, $calories, PDO::PARAM_INT);
$sth->bindParam(2, $colour, PDO::PARAM_STR, 12);
$sth->execute();
?>
```

**Example \#5 Execute a prepared statement using array for IN clause**

``` php
<?php
/* Execute a prepared statement using an array of values for an IN clause */
$params = array(1, 21, 63, 171);
/* Create a string for the parameter placeholders filled to the number of params */
$place_holders = implode(',', array_fill(0, count($params), '?'));

/*
    This prepares the statement with enough unnamed placeholders for every value
    in our $params array. The values of the $params array are then bound to the
    placeholders in the prepared statement when the statement is executed.
    This is not the same thing as using PDOStatement::bindParam() since this
    requires a reference to the variable. PDOStatement::execute() only binds
    by value instead.
*/
$sth = $dbh->prepare("SELECT id, name FROM contacts WHERE id IN ($place_holders)");
$sth->execute($params);
?>
```

### Notes

> **Note**:
>
> Some drivers require to
> <a href="/book/pdo.html#PDOStatement::closeCursor" class="link">close cursor</a>
> before executing next statement.

### See Also

-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::bindParam</span>
-   <span class="function">PDOStatement::fetch</span>
-   <span class="function">PDOStatement::fetchAll</span>
-   <span class="function">PDOStatement::fetchColumn</span>

PDOStatement::fetch
===================

Fetches the next row from a result set

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">PDOStatement::fetch</span> (\[ <span
class="methodparam"><span class="type">int</span> `$fetch_style`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$cursor_orientation`<span class="initializer"> =
PDO::FETCH\_ORI\_NEXT</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$cursor_offset`<span class="initializer"> =
0</span></span> \]\]\] )

Fetches a row from a result set associated with a PDOStatement object.
The `fetch_style` parameter determines how PDO returns the row.

### Parameters

`fetch_style`  
Controls how the next row will be returned to the caller. This value
must be one of the *PDO::FETCH\_\** constants, defaulting to value of
*PDO::ATTR\_DEFAULT\_FETCH\_MODE* (which defaults to
*PDO::FETCH\_BOTH*).

-   *PDO::FETCH\_ASSOC*: returns an array indexed by column name as
    returned in your result set

-   *PDO::FETCH\_BOTH* (default): returns an array indexed by both
    column name and 0-indexed column number as returned in your result
    set

-   *PDO::FETCH\_BOUND*: returns **`TRUE`** and assigns the values of
    the columns in your result set to the PHP variables to which they
    were bound with the <span
    class="function">PDOStatement::bindColumn</span> method

-   *PDO::FETCH\_CLASS*: returns a new instance of the requested class,
    mapping the columns of the result set to named properties in the
    class, and calling the constructor afterwards, unless
    *PDO::FETCH\_PROPS\_LATE* is also given. If `fetch_style` includes
    PDO::FETCH\_CLASSTYPE (e.g. *PDO::FETCH\_CLASS \|
    PDO::FETCH\_CLASSTYPE*) then the name of the class is determined
    from a value of the first column.

-   *PDO::FETCH\_INTO*: updates an existing instance of the requested
    class, mapping the columns of the result set to named properties in
    the class

-   *PDO::FETCH\_LAZY*: combines *PDO::FETCH\_BOTH* and
    *PDO::FETCH\_OBJ*, creating the object variable names as they are
    accessed

-   *PDO::FETCH\_NAMED*: returns an array with the same form as
    *PDO::FETCH\_ASSOC*, except that if there are multiple columns with
    the same name, the value referred to by that key will be an array of
    all the values in the row that had that column name

-   *PDO::FETCH\_NUM*: returns an array indexed by column number as
    returned in your result set, starting at column 0

-   *PDO::FETCH\_OBJ*: returns an anonymous object with property names
    that correspond to the column names returned in your result set

-   *PDO::FETCH\_PROPS\_LATE*: when used with *PDO::FETCH\_CLASS*, the
    constructor of the class is called before the properties are
    assigned from the respective column values.

`cursor_orientation`  
For a PDOStatement object representing a scrollable cursor, this value
determines which row will be returned to the caller. This value must be
one of the *PDO::FETCH\_ORI\_\** constants, defaulting to
*PDO::FETCH\_ORI\_NEXT*. To request a scrollable cursor for your
PDOStatement object, you must set the *PDO::ATTR\_CURSOR* attribute to
*PDO::CURSOR\_SCROLL* when you prepare the SQL statement with <span
class="function">PDO::prepare</span>.

`offset`  
For a PDOStatement object representing a scrollable cursor for which the
*cursor\_orientation* parameter is set to *PDO::FETCH\_ORI\_ABS*, this
value specifies the absolute number of the row in the result set that
shall be fetched.

For a PDOStatement object representing a scrollable cursor for which the
*cursor\_orientation* parameter is set to *PDO::FETCH\_ORI\_REL*, this
value specifies the row to fetch relative to the cursor position before
<span class="function">PDOStatement::fetch</span> was called.

### Return Values

The return value of this function on success depends on the fetch type.
In all cases, **`FALSE`** is returned on failure.

### Examples

**Example \#1 Fetching rows using different fetch styles**

``` php
<?php
$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();

/* Exercise PDOStatement::fetch styles */
print("PDO::FETCH_ASSOC: ");
print("Return next row as an array indexed by column name\n");
$result = $sth->fetch(PDO::FETCH_ASSOC);
print_r($result);
print("\n");

print("PDO::FETCH_BOTH: ");
print("Return next row as an array indexed by both column name and number\n");
$result = $sth->fetch(PDO::FETCH_BOTH);
print_r($result);
print("\n");

print("PDO::FETCH_LAZY: ");
print("Return next row as an anonymous object with column names as properties\n");
$result = $sth->fetch(PDO::FETCH_LAZY);
print_r($result);
print("\n");

print("PDO::FETCH_OBJ: ");
print("Return next row as an anonymous object with column names as properties\n");
$result = $sth->fetch(PDO::FETCH_OBJ);
print $result->name;
print("\n");
?>
```

The above example will output:

    PDO::FETCH_ASSOC: Return next row as an array indexed by column name
    Array
    (
        [name] => apple
        [colour] => red
    )

    PDO::FETCH_BOTH: Return next row as an array indexed by both column name and number
    Array
    (
        [name] => banana
        [0] => banana
        [colour] => yellow
        [1] => yellow
    )

    PDO::FETCH_LAZY: Return next row as an anonymous object with column names as properties
    PDORow Object
    (
        [name] => orange
        [colour] => orange
    )

    PDO::FETCH_OBJ: Return next row as an anonymous object with column names as properties
    kiwi

**Example \#2 Fetching rows with a scrollable cursor**

``` php
<?php
function readDataForwards($dbh) {
  $sql = 'SELECT hand, won, bet FROM mynumbers ORDER BY BET';
  try {
    $stmt = $dbh->prepare($sql, array(PDO::ATTR_CURSOR => PDO::CURSOR_SCROLL));
    $stmt->execute();
    while ($row = $stmt->fetch(PDO::FETCH_NUM, PDO::FETCH_ORI_NEXT)) {
      $data = $row[0] . "\t" . $row[1] . "\t" . $row[2] . "\n";
      print $data;
    }
    $stmt = null;
  }
  catch (PDOException $e) {
    print $e->getMessage();
  }
}
function readDataBackwards($dbh) {
  $sql = 'SELECT hand, won, bet FROM mynumbers ORDER BY bet';
  try {
    $stmt = $dbh->prepare($sql, array(PDO::ATTR_CURSOR => PDO::CURSOR_SCROLL));
    $stmt->execute();
    $row = $stmt->fetch(PDO::FETCH_NUM, PDO::FETCH_ORI_LAST);
    do {
      $data = $row[0] . "\t" . $row[1] . "\t" . $row[2] . "\n";
      print $data;
    } while ($row = $stmt->fetch(PDO::FETCH_NUM, PDO::FETCH_ORI_PRIOR));
    $stmt = null;
  }
  catch (PDOException $e) {
    print $e->getMessage();
  }
}

print "Reading forwards:\n";
readDataForwards($conn);

print "Reading backwards:\n";
readDataBackwards($conn);
?>
```

The above example will output:

    Reading forwards:
    21    10    5
    16    0     5
    19    20    10

    Reading backwards:
    19    20    10
    16    0     5
    21    10    5

**Example \#3 Construction order**

When objects are fetched via *PDO::FETCH\_CLASS* the object properties
are assigned first, and then the constructor of the class is invoked. If
*PDO::FETCH\_PROPS\_LATE* is also given, this order is reversed, i.e.
first the constructor is called, and afterwards the properties are
assigned.

``` php
<?php
class Person
{
    private $name;

    public function __construct()
    {
        $this->tell();
    }

    public function tell()
    {
        if (isset($this->name)) {
            echo "I am {$this->name}.\n";
        } else {
            echo "I don't have a name yet.\n";
        }
    }
}

$sth = $dbh->query("SELECT * FROM people");
$sth->setFetchMode(PDO::FETCH_CLASS, 'Person');
$person = $sth->fetch();
$person->tell();
$sth->setFetchMode(PDO::FETCH_CLASS|PDO::FETCH_PROPS_LATE, 'Person');
$person = $sth->fetch();
$person->tell();
?>
```

The above example will output something similar to:

    I am Alice.
    I am Alice.
    I don't have a name yet.
    I am Bob.

### See Also

-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::execute</span>
-   <span class="function">PDOStatement::fetchAll</span>
-   <span class="function">PDOStatement::fetchColumn</span>
-   <span class="function">PDOStatement::fetchObject</span>
-   <span class="function">PDOStatement::setFetchMode</span>

PDOStatement::fetchAll
======================

Returns an array containing all of the result set rows

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">PDOStatement::fetchAll</span> (\[ <span
class="methodparam"><span class="type">int</span> `$fetch_style`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$fetch_argument`</span> \[, <span class="methodparam"><span
class="type">array</span> `$ctor_args`<span class="initializer"> =
array()</span></span> \]\]\] )

### Parameters

`fetch_style`  
Controls the contents of the returned array as documented in <span
class="function">PDOStatement::fetch</span>. Defaults to value of
**`PDO::ATTR_DEFAULT_FETCH_MODE`** (which defaults to
**`PDO::FETCH_BOTH`**)

To return an array consisting of all values of a single column from the
result set, specify **`PDO::FETCH_COLUMN`**. You can specify which
column you want with the `fetch_argument` parameter.

To fetch only the unique values of a single column from the result set,
bitwise-OR **`PDO::FETCH_COLUMN`** with **`PDO::FETCH_UNIQUE`**.

To return an associative array grouped by the values of a specified
column, bitwise-OR **`PDO::FETCH_COLUMN`** with **`PDO::FETCH_GROUP`**.

`fetch_argument`  
This argument has a different meaning depending on the value of the
`fetch_style` parameter:

-   **`PDO::FETCH_COLUMN`**: Returns the indicated 0-indexed column.

-   **`PDO::FETCH_CLASS`**: Returns instances of the specified class,
    mapping the columns of each row to named properties in the class.

-   **`PDO::FETCH_FUNC`**: Returns the results of calling the specified
    function, using each row's columns as parameters in the call.

`ctor_args`  
Arguments of custom class constructor when the `fetch_style` parameter
is **`PDO::FETCH_CLASS`**.

### Return Values

<span class="function">PDOStatement::fetchAll</span> returns an array
containing all of the remaining rows in the result set. The array
represents each row as either an array of column values or an object
with properties corresponding to each column name. An empty array is
returned if there are zero results to fetch, or **`FALSE`** on failure.

Using this method to fetch large result sets will result in a heavy
demand on system and possibly network resources. Rather than retrieving
all of the data and manipulating it in PHP, consider using the database
server to manipulate the result sets. For example, use the WHERE and
ORDER BY clauses in SQL to restrict results before retrieving and
processing them with PHP.

### Examples

**Example \#1 Fetch all remaining rows in a result set**

``` php
<?php
$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();

/* Fetch all of the remaining rows in the result set */
print("Fetch all of the remaining rows in the result set:\n");
$result = $sth->fetchAll();
print_r($result);
?>
```

The above example will output something similar to:

    Fetch all of the remaining rows in the result set:
    Array
    (
        [0] => Array
            (
                [name] => apple
                [0] => apple
                [colour] => red
                [1] => red
            )

        [1] => Array
            (
                [name] => pear
                [0] => pear
                [colour] => green
                [1] => green
            )

        [2] => Array
            (
                [name] => watermelon
                [0] => watermelon
                [colour] => pink
                [1] => pink
            )

    )

**Example \#2 Fetching all values of a single column from a result set**

The following example demonstrates how to return all of the values of a
single column from a result set, even though the SQL statement itself
may return multiple columns per row.

``` php
<?php
$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();

/* Fetch all of the values of the first column */
$result = $sth->fetchAll(PDO::FETCH_COLUMN, 0);
var_dump($result);
?>
```

The above example will output something similar to:

    Array(3)
    (
        [0] =>
        string(5) => apple
        [1] =>
        string(4) => pear
        [2] =>
        string(10) => watermelon
    )

**Example \#3 Grouping all values by a single column**

The following example demonstrates how to return an associative array
grouped by the values of the specified column in the result set. The
array contains three keys: values *apple* and *pear* are returned as
arrays that contain two different colours, while *watermelon* is
returned as an array that contains only one colour.

``` php
<?php
$insert = $dbh->prepare("INSERT INTO fruit(name, colour) VALUES (?, ?)");
$insert->execute(array('apple', 'green'));
$insert->execute(array('pear', 'yellow'));

$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();

/* Group values by the first column */
var_dump($sth->fetchAll(PDO::FETCH_COLUMN|PDO::FETCH_GROUP));
?>
```

The above example will output something similar to:

    array(3) {
      ["apple"]=>
      array(2) {
        [0]=>
        string(5) "green"
        [1]=>
        string(3) "red"
      }
      ["pear"]=>
      array(2) {
        [0]=>
        string(5) "green"
        [1]=>
        string(6) "yellow"
      }
      ["watermelon"]=>
      array(1) {
        [0]=>
        string(5) "pink"
      }
    }

**Example \#4 Instantiating a class for each result**

The following example demonstrates the behaviour of the
**`PDO::FETCH_CLASS`** fetch style.

``` php
<?php
class fruit {
    public $name;
    public $colour;
}

$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();

$result = $sth->fetchAll(PDO::FETCH_CLASS, "fruit");
var_dump($result);
?>
```

The above example will output something similar to:

    array(3) {
      [0]=>
      object(fruit)#1 (2) {
        ["name"]=>
        string(5) "apple"
        ["colour"]=>
        string(5) "green"
      }
      [1]=>
      object(fruit)#2 (2) {
        ["name"]=>
        string(4) "pear"
        ["colour"]=>
        string(6) "yellow"
      }
      [2]=>
      object(fruit)#3 (2) {
        ["name"]=>
        string(10) "watermelon"
        ["colour"]=>
        string(4) "pink"
      }
      [3]=>
      object(fruit)#4 (2) {
        ["name"]=>
        string(5) "apple"
        ["colour"]=>
        string(3) "red"
      }
      [4]=>
      object(fruit)#5 (2) {
        ["name"]=>
        string(4) "pear"
        ["colour"]=>
        string(5) "green"
      }
    }

**Example \#5 Calling a function for each result**

The following example demonstrates the behaviour of the
**`PDO::FETCH_FUNC`** fetch style.

``` php
<?php
function fruit($name, $colour) {
    return "{$name}: {$colour}";
}

$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();

$result = $sth->fetchAll(PDO::FETCH_FUNC, "fruit");
var_dump($result);
?>
```

The above example will output something similar to:

    array(3) {
      [0]=>
      string(12) "apple: green"
      [1]=>
      string(12) "pear: yellow"
      [2]=>
      string(16) "watermelon: pink"
      [3]=>
      string(10) "apple: red"
      [4]=>
      string(11) "pear: green"
    }

### See Also

-   <span class="function">PDO::query</span>
-   <span class="function">PDOStatement::fetch</span>
-   <span class="function">PDOStatement::fetchColumn</span>
-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::setFetchMode</span>

PDOStatement::fetchColumn
=========================

Returns a single column from the next row of a result set

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">PDOStatement::fetchColumn</span> (\[ <span
class="methodparam"><span class="type">int</span> `$column_number`<span
class="initializer"> = 0</span></span> \] )

Returns a single column from the next row of a result set or **`FALSE`**
if there are no more rows.

> **Note**:
>
> <span class="function">PDOStatement::fetchColumn</span> should not be
> used to retrieve boolean columns, as it is impossible to distinguish a
> value of **`FALSE`** from there being no more rows to retrieve. Use
> <span class="function">PDOStatement::fetch</span> instead.

### Parameters

`column_number`  
0-indexed number of the column you wish to retrieve from the row. If no
value is supplied, <span
class="function">PDOStatement::fetchColumn</span> fetches the first
column.

### Return Values

<span class="function">PDOStatement::fetchColumn</span> returns a single
column from the next row of a result set or **`FALSE`** if there are no
more rows.

**Warning**

There is no way to return another column from the same row if you use
<span class="function">PDOStatement::fetchColumn</span> to retrieve
data.

### Examples

**Example \#1 Return first column of the next row**

``` php
<?php
$sth = $dbh->prepare("SELECT name, colour FROM fruit");
$sth->execute();

print("Fetch the first column from the first row in the result set:\n");
$result = $sth->fetchColumn();
print("name = $result\n");

print("Fetch the second column from the second row in the result set:\n");
$result = $sth->fetchColumn(1);
print("colour = $result\n");
?>
```

The above example will output:

    Fetch the first column from the first row in the result set:
    name = lemon
    Fetch the second column from the second row in the result set:
    colour = red

### See Also

-   <span class="function">PDO::query</span>
-   <span class="function">PDOStatement::fetch</span>
-   <span class="function">PDOStatement::fetchAll</span>
-   <span class="function">PDO::prepare</span>
-   <span class="function">PDOStatement::setFetchMode</span>

PDOStatement::fetchObject
=========================

Fetches the next row and returns it as an object

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">object</span><span class="type">false</span></span> <span
class="methodname">PDOStatement::fetchObject</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "stdClass"</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$ctor_args`</span>
\]\] )

Fetches the next row and returns it as an object. This function is an
alternative to <span class="function">PDOStatement::fetch</span> with
**`PDO::FETCH_CLASS`** or **`PDO::FETCH_OBJ`** style.

When an object is fetched, its properties are assigned from respective
column values, and afterwards its constructor is invoked.

### Parameters

`class_name`  
Name of the created class.

`ctor_args`  
Elements of this array are passed to the constructor.

### Return Values

Returns an instance of the required class with property names that
correspond to the column names or **`FALSE`** on failure.

### See Also

-   <span class="function">PDOStatement::fetch</span>

PDOStatement::getAttribute
==========================

Retrieve a statement attribute

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">PDOStatement::getAttribute</span> ( <span
class="methodparam"><span class="type">int</span> `$attribute`</span> )

Gets an attribute of the statement. Currently, no generic attributes
exist but only driver specific:

-   *PDO::ATTR\_CURSOR\_NAME* (Firebird and ODBC specific): Get the name
    of cursor for *UPDATE ... WHERE CURRENT OF*.

### Return Values

Returns the attribute value.

### See Also

-   <span class="function">PDO::getAttribute</span>
-   <span class="function">PDO::setAttribute</span>
-   <span class="function">PDOStatement::setAttribute</span>

PDOStatement::getColumnMeta
===========================

Returns metadata for a column in a result set

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">PDOStatement::getColumnMeta</span> ( <span
class="methodparam"><span class="type">int</span> `$column`</span> )

Retrieves the metadata for a 0-indexed column in a result set as an
associative array.

**Warning**

Not all PDO drivers support <span
class="function">PDOStatement::getColumnMeta</span>.

The following drivers support this method:

-   <span
    class="simpara"><a href="/book/pdo.html#MS%20SQL%20Server%20(PDO)" class="link">PDO_DBLIB</a></span>
-   <span
    class="simpara"><a href="/book/pdo.html#MySQL%20(PDO)" class="link">PDO_MYSQL</a></span>
-   <span
    class="simpara"><a href="/book/pdo.html#PostgreSQL%20(PDO)" class="link">PDO_PGSQL</a></span>
-   <span
    class="simpara"><a href="/book/pdo.html#SQLite%20(PDO)" class="link">PDO_SQLITE</a></span>

### Parameters

`column`  
The 0-indexed column in the result set.

### Return Values

Returns an associative array containing the following values
representing the metadata for a single column:

| Name                | Value                                                                                                                                                                                                                  |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *native\_type*      | The PHP native type used to represent the column value.                                                                                                                                                                |
| *driver:decl\_type* | The SQL type used to represent the column value in the database. If the column in the result set is the result of a function, this value is not returned by <span class="function">PDOStatement::getColumnMeta</span>. |
| *flags*             | Any flags set for this column.                                                                                                                                                                                         |
| *name*              | The name of this column as returned by the database.                                                                                                                                                                   |
| *table*             | The name of this column's table as returned by the database.                                                                                                                                                           |
| *len*               | The length of this column. Normally *-1* for types other than floating point decimals.                                                                                                                                 |
| *precision*         | The numeric precision of this column. Normally *0* for types other than floating point decimals.                                                                                                                       |
| *pdo\_type*         | The type of this column as represented by the <a href="/book/pdo.html#Predefined%20Constants" class="link"><em>PDO::PARAM_*</em> constants</a>.                                                                        |

Returns **`FALSE`** if the requested column does not exist in the result
set, or if no result set exists.

### Examples

**Example \#1 Retrieving column metadata**

The following example shows the results of retrieving the metadata for a
single column generated by a function (COUNT) in a PDO\_SQLITE driver.

``` php
<?php
$select = $DB->query('SELECT COUNT(*) FROM fruit');
$meta = $select->getColumnMeta(0);
var_dump($meta);
?>
```

The above example will output:

    array(6) {
      ["native_type"]=>
      string(7) "integer"
      ["flags"]=>
      array(0) {
      }
      ["name"]=>
      string(8) "COUNT(*)"
      ["len"]=>
      int(-1)
      ["precision"]=>
      int(0)
      ["pdo_type"]=>
      int(2)
    }

### See Also

-   <span class="function">PDOStatement::columnCount</span>
-   <span class="function">PDOStatement::rowCount</span>

PDOStatement::nextRowset
========================

Advances to the next rowset in a multi-rowset statement handle

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::nextRowset</span> ( <span
class="methodparam">void</span> )

Some database servers support stored procedures that return more than
one rowset (also known as a result set). <span
class="function">PDOStatement::nextRowset</span> enables you to access
the second and subsequent rowsets associated with a PDOStatement object.
Each rowset can have a different set of columns from the preceding
rowset.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Fetching multiple rowsets returned from a stored
procedure**

The following example shows how to call a stored procedure,
MULTIPLE\_ROWSETS, that returns three rowsets. We use a do / while loop
to loop over the <span class="function">PDOStatement::nextRowset</span>
method, which returns false and terminates the loop when no more rowsets
can be returned.

``` php
<?php
$sql = 'CALL multiple_rowsets()';
$stmt = $conn->query($sql);
$i = 1;
do {
    $rowset = $stmt->fetchAll(PDO::FETCH_NUM);
    if ($rowset) {
        printResultSet($rowset, $i);
    }
    $i++;
} while ($stmt->nextRowset());

function printResultSet(&$rowset, $i) {
    print "Result set $i:\n";
    foreach ($rowset as $row) {
        foreach ($row as $col) {
            print $col . "\t";
        }
        print "\n";
    }
    print "\n";
}
?>
```

The above example will output:

    Result set 1:
    apple    red
    banana   yellow

    Result set 2:
    orange   orange    150
    banana   yellow    175

    Result set 3:
    lime     green
    apple    red
    banana   yellow

### See Also

-   <span class="function">PDOStatement::columnCount</span>
-   <span class="function">PDOStatement::execute</span>
-   <span class="function">PDOStatement::getColumnMeta</span>
-   <span class="function">PDO::query</span>

PDOStatement::rowCount
======================

Returns the number of rows affected by the last SQL statement

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">PDOStatement::rowCount</span> ( <span
class="methodparam">void</span> )

<span class="function">PDOStatement::rowCount</span> returns the number
of rows affected by the last DELETE, INSERT, or UPDATE statement
executed by the corresponding *PDOStatement* object.

If the last SQL statement executed by the associated *PDOStatement* was
a SELECT statement, some databases may return the number of rows
returned by that statement. However, this behaviour is not guaranteed
for all databases and should not be relied on for portable applications.

> **Note**:
>
> This method returns "0" (zero) with the SQLite driver at all times,
> and with the PostgreSQL driver only when setting the
> **`PDO::ATTR_CURSOR`** statement attribute to
> **`PDO::CURSOR_SCROLL`**.

### Return Values

Returns the number of rows.

### Examples

**Example \#1 Return the number of deleted rows**

<span class="function">PDOStatement::rowCount</span> returns the number
of rows affected by a DELETE, INSERT, or UPDATE statement.

``` php
<?php
/* Delete all rows from the FRUIT table */
$del = $dbh->prepare('DELETE FROM fruit');
$del->execute();

/* Return number of rows that were deleted */
print("Return number of rows that were deleted:\n");
$count = $del->rowCount();
print("Deleted $count rows.\n");
?>
```

The above example will output something similar to:

    Return number of rows that were deleted:
    Deleted 9 rows.

**Example \#2 Counting rows returned by a SELECT statement**

For most databases, <span class="function">PDOStatement::rowCount</span>
does not return the number of rows affected by a SELECT statement.
Instead, use <span class="function">PDO::query</span> to issue a SELECT
COUNT(\*) statement with the same predicates as your intended SELECT
statement, then use <span
class="function">PDOStatement::fetchColumn</span> to retrieve the number
of matching rows.

``` php
<?php
$sql = "SELECT COUNT(*) FROM fruit WHERE calories > 100";
$res = $conn->query($sql);
$count = $res->fetchColumn();

print "There are " .  $count . " matching records.";
```

The above example will output something similar to:

    There are 2 matching records.

### See Also

-   <span class="function">PDOStatement::columnCount</span>
-   <span class="function">PDOStatement::fetchColumn</span>
-   <span class="function">PDO::query</span>

PDOStatement::setAttribute
==========================

Set a statement attribute

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::setAttribute</span> ( <span
class="methodparam"><span class="type">int</span> `$attribute`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

Sets an attribute on the statement. Currently, no generic attributes are
set but only driver specific:

-   *PDO::ATTR\_CURSOR\_NAME* (Firebird and ODBC specific): Set the name
    of cursor for *UPDATE ... WHERE CURRENT OF*.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">PDO::getAttribute</span>
-   <span class="function">PDO::setAttribute</span>
-   <span class="function">PDOStatement::getAttribute</span>

PDOStatement::setFetchMode
==========================

Set the default fetch mode for this statement

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::setFetchMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::setFetchMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = PDO::FETCH\_COLUMN</span></span> , <span
class="methodparam"><span class="type">int</span> `$colno`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::setFetchMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = PDO::FETCH\_CLASS</span></span> , <span
class="methodparam"><span class="type">string</span> `$classname`</span>
, <span class="methodparam"><span class="type">array</span>
`$ctorargs`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDOStatement::setFetchMode</span> ( <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = PDO::FETCH\_INTO</span></span> , <span
class="methodparam"><span class="type">object</span> `$object`</span> )

### Parameters

`mode`  
The fetch mode must be one of the *PDO::FETCH\_\** constants.

`colno`  
Column number.

`classname`  
Class name.

`ctorargs`  
Constructor arguments.

`object`  
Object.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Setting the fetch mode**

The following example demonstrates how <span
class="function">PDOStatement::setFetchMode</span> changes the default
fetch mode for a PDOStatement object.

``` php
<?php
$sql = 'SELECT name, colour, calories FROM fruit';
try {
  $stmt = $dbh->query($sql);
  $result = $stmt->setFetchMode(PDO::FETCH_NUM);
  while ($row = $stmt->fetch()) {
    print $row[0] . "\t" . $row[1] . "\t" . $row[2] . "\n";
  }
}
catch (PDOException $e) {
  print $e->getMessage();
}
?>
```

The above example will output:

    apple   red     150
    banana  yellow  250
    orange  orange  300
    kiwi    brown   75
    lemon   yellow  25
    pear    green   150
    watermelon      pink    90

Introduction
------------

Represents an error raised by PDO. You should not throw a <span
class="classname">PDOException</span> from your own code. See
<a href="/language/exceptions.html" class="link">Exceptions</a> for more
information about Exceptions in PHP.

Class synopsis
--------------

**PDOException**

<span class="ooclass"> class **PDOException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**RuntimeException** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span class="type">array</span>
`$errorInfo` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$code` ;

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`errorInfo`  
Corresponds to <span class="function">PDO::errorInfo</span> or <span
class="function">PDOStatement::errorInfo</span>

`code`  
*SQLSTATE* error code. Use <span
class="function">Exception::getCode</span> to access it.

PDO Drivers
===========

**Table of Contents**

-   [CUBRID (PDO)](/book/pdo.html#CUBRID%20(PDO)) — CUBRID Functions
    (PDO\_CUBRID)
    -   [PDO\_CUBRID DSN](/book/pdo.html#PDO_CUBRID%20DSN) — Connecting
        to CUBRID databases
    -   [PDO::cubrid\_schema](/book/pdo.html#PDO::cubrid_schema) — Get
        the requested schema information
-   [MS SQL Server (PDO)](/book/pdo.html#MS%20SQL%20Server%20(PDO)) —
    Microsoft SQL Server and Sybase Functions (PDO\_DBLIB)
    -   [PDO\_DBLIB DSN](/book/pdo.html#PDO_DBLIB%20DSN) — Connecting to
        Microsoft SQL Server and Sybase databases
-   [Firebird (PDO)](/book/pdo.html#Firebird%20(PDO)) — Firebird
    Functions (PDO\_FIREBIRD)
    -   [PDO\_FIREBIRD DSN](/book/pdo.html#PDO_FIREBIRD%20DSN) —
        Connecting to Firebird databases
-   [IBM (PDO)](/book/pdo.html#IBM%20(PDO)) — IBM Functions (PDO\_IBM)
    -   [PDO\_IBM DSN](/book/pdo.html#PDO_IBM%20DSN) — Connecting to IBM
        databases
-   [Informix (PDO)](/book/pdo.html#Informix%20(PDO)) — Informix
    Functions (PDO\_INFORMIX)
    -   [PDO\_INFORMIX DSN](/book/pdo.html#PDO_INFORMIX%20DSN) —
        Connecting to Informix databases
-   [MySQL (PDO)](/book/pdo.html#MySQL%20(PDO)) — MySQL Functions
    (PDO\_MYSQL)
    -   [PDO\_MYSQL DSN](/book/pdo.html#PDO_MYSQL%20DSN) — Connecting to
        MySQL databases
-   [MS SQL Server (PDO)](/book/pdo.html#MS%20SQL%20Server%20(PDO)) —
    Microsoft SQL Server Functions (PDO\_SQLSRV)
    -   [PDO\_SQLSRV DSN](/book/pdo.html#PDO_SQLSRV%20DSN) — Connecting
        to MS SQL Server and SQL Azure databases
-   [Oracle (PDO)](/book/pdo.html#Oracle%20(PDO)) — Oracle Functions
    (PDO\_OCI)
    -   [PDO\_OCI DSN](/book/pdo.html#PDO_OCI%20DSN) — Connecting to
        Oracle databases
-   [ODBC and DB2 (PDO)](/book/pdo.html#ODBC%20and%20DB2%20(PDO)) — ODBC
    and DB2 Functions (PDO\_ODBC)
    -   [PDO\_ODBC DSN](/book/pdo.html#PDO_ODBC%20DSN) — Connecting to
        ODBC or DB2 databases
-   [PostgreSQL (PDO)](/book/pdo.html#PostgreSQL%20(PDO)) — PostgreSQL
    Functions (PDO\_PGSQL)
    -   [PDO\_PGSQL DSN](/book/pdo.html#PDO_PGSQL%20DSN) — Connecting to
        PostgreSQL databases
    -   [PDO::pgsqlCopyFromArray](/book/pdo.html#PDO::pgsqlCopyFromArray)
        — Copy data from PHP array into table
    -   [PDO::pgsqlCopyFromFile](/book/pdo.html#PDO::pgsqlCopyFromFile)
        — Copy data from file into table
    -   [PDO::pgsqlCopyToArray](/book/pdo.html#PDO::pgsqlCopyToArray) —
        Copy data from database table into PHP array
    -   [PDO::pgsqlCopyToFile](/book/pdo.html#PDO::pgsqlCopyToFile) —
        Copy data from table into file
    -   [PDO::pgsqlGetNotify](/book/pdo.html#PDO::pgsqlGetNotify) — Get
        asynchronous notification
    -   [PDO::pgsqlGetPid](/book/pdo.html#PDO::pgsqlGetPid) — Get the
        server PID
    -   [PDO::pgsqlLOBCreate](/book/pdo.html#PDO::pgsqlLOBCreate) —
        Creates a new large object
    -   [PDO::pgsqlLOBOpen](/book/pdo.html#PDO::pgsqlLOBOpen) — Opens an
        existing large object stream
    -   [PDO::pgsqlLOBUnlink](/book/pdo.html#PDO::pgsqlLOBUnlink) —
        Deletes the large object
-   [SQLite (PDO)](/book/pdo.html#SQLite%20(PDO)) — SQLite Functions
    (PDO\_SQLITE)
    -   [PDO\_SQLITE DSN](/book/pdo.html#PDO_SQLITE%20DSN) — Connecting
        to SQLite databases
    -   [PDO::sqliteCreateAggregate](/book/pdo.html#PDO::sqliteCreateAggregate)
        — Registers an aggregating User Defined Function for use in SQL
        statements
    -   [PDO::sqliteCreateCollation](/book/pdo.html#PDO::sqliteCreateCollation)
        — Registers a User Defined Function for use as a collating
        function in SQL statements
    -   [PDO::sqliteCreateFunction](/book/pdo.html#PDO::sqliteCreateFunction)
        — Registers a User Defined Function for use in SQL statements

The following drivers currently implement the PDO interface:

| Driver name                                                                    | Supported databases                        |
|--------------------------------------------------------------------------------|--------------------------------------------|
| <a href="/book/pdo.html#CUBRID%20(PDO)" class="link">PDO_CUBRID</a>            | Cubrid                                     |
| <a href="/book/pdo.html#MS%20SQL%20Server%20(PDO)" class="link">PDO_DBLIB</a>  | FreeTDS / Microsoft SQL Server / Sybase    |
| <a href="/book/pdo.html#Firebird%20(PDO)" class="link">PDO_FIREBIRD</a>        | Firebird                                   |
| <a href="/book/pdo.html#IBM%20(PDO)" class="link">PDO_IBM</a>                  | IBM DB2                                    |
| <a href="/book/pdo.html#Informix%20(PDO)" class="link">PDO_INFORMIX</a>        | IBM Informix Dynamic Server                |
| <a href="/book/pdo.html#MySQL%20(PDO)" class="link">PDO_MYSQL</a>              | MySQL 3.x/4.x/5.x                          |
| <a href="/book/pdo.html#Oracle%20(PDO)" class="link">PDO_OCI</a>               | Oracle Call Interface                      |
| <a href="/book/pdo.html#ODBC%20and%20DB2%20(PDO)" class="link">PDO_ODBC</a>    | ODBC v3 (IBM DB2, unixODBC and win32 ODBC) |
| <a href="/book/pdo.html#PostgreSQL%20(PDO)" class="link">PDO_PGSQL</a>         | PostgreSQL                                 |
| <a href="/book/pdo.html#SQLite%20(PDO)" class="link">PDO_SQLITE</a>            | SQLite 3 and SQLite 2                      |
| <a href="/book/pdo.html#MS%20SQL%20Server%20(PDO)" class="link">PDO_SQLSRV</a> | Microsoft SQL Server / SQL Azure           |

Introduction
------------

PDO\_CUBRID is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO) interface</a>
to enable access from PHP to CUBRID databases.

> **Note**:
>
> Current version of PDO\_CUBRID doesn't support persistent connection
> now.

Installation
------------

To build the PDO\_CUBRID extension, the CUBRID DBMS must be installed on
the same system as PHP. PDO\_CUBRID is a
<a href="https://pecl.php.net/" class="link external">» PECL</a>
extension, so follow the instructions in
<a href="/install/pecl.html" class="xref">Installation of PECL extensions</a>
to install the PDO\_CUBRID extension. Issue the **configure** command to
point to the location of your CUBRID base dir as follows:

       $ ./configure --with-pdo-cubrid=/path/to/CUBRID[,shared]

The **configure** command defaults to the value of the *CUBRID*
environment variable.

A DLL for this PECL extension is currently unavailable. See also the
<a href="/install/windows/legacy/index.html#install.windows.legacy.building" class="link">building on Windows</a>
section. Detailed information about installation on Linux and Windows
manually, please read build-guide.html in PECL package CUBRID for
reference.

Features
--------

<table>
<caption><strong>PDO_CUBRID Features</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Feature</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Scrollable cursors</td>
<td>PDO_CUBRID supports scrollable cursors. The default cursor type is forward only, and you can use parameter driver_options in <span class="function">PDO::prepare</span> to change cursor type.</td>
</tr>
<tr class="even">
<td>Timeout</td>
<td>PDO_CUBRID supports sql statement execution timeout setting; You can use <span class="function">PDO::setAttribute</span> to set timeout value.</td>
</tr>
<tr class="odd">
<td>Autocommit_mode and Transaction</td>
<td>PDO_CUBRID supports both autocommit_mode and transaction, and autocommit_mode is enabled by default. You can use <span class="function">PDO::setAttribute</span> to change its state.
<p>If you use <span class="function">PDO::beginTransaction</span> to begin a transaction, it will disable autocommit_mode automatically and restore it after <span class="function">PDO::commit</span> or <span class="function">PDO::rollBack</span>. Note that before disabling the autocommit_mode, any pending work is automatically committed.</p></td>
</tr>
<tr class="even">
<td>Multiple SQL Statements</td>
<td>PDO_CUBRID supports Multiple SQL statements. Multiple SQL statements are separated by semicolons (;)</td>
</tr>
<tr class="odd">
<td>Schema Information</td>
<td>PDO_CUBRID implements a function <span class="function">PDO::cubrid_schema</span> to get schema information.</td>
</tr>
<tr class="even">
<td>LOBs</td>
<td>PDO_CUBRID supports BLOB/CLOB data type. The LOB in PDO is represented as a stream, so you can insert LOBs by binding a stream, and get LOBs by reading a stream returned by CUBRID PDO. For example:
<div id="example-1041" class="example">
<p><strong>Example #1 Insert LOBs in CUBRID PDO</strong></p>
<div class="example-contents">
<div class="phpcode">
<div class="sourceCode" id="cb1"><pre class="sourceCode php"><code class="sourceCode php"><span id="cb1-1"><a href="#cb1-1"></a><span class="kw">&lt;?php</span></span>
<span id="cb1-2"><a href="#cb1-2"></a><span class="kw">$fp</span> = <span class="fu">fopen</span><span class="ot">(</span><span class="st">&#39;lob_test.png&#39;</span><span class="ot">,</span> <span class="st">&#39;rb&#39;</span><span class="ot">);</span></span>
<span id="cb1-3"><a href="#cb1-3"></a></span>
<span id="cb1-4"><a href="#cb1-4"></a><span class="kw">$sql_stmt</span> = <span class="st">&quot;INSERT INTO lob_test(name, content) VALUES(&#39;lob_test.png&#39;, ?)&quot;</span><span class="ot">;</span></span>
<span id="cb1-5"><a href="#cb1-5"></a></span>
<span id="cb1-6"><a href="#cb1-6"></a><span class="kw">$stmt</span> = <span class="kw">$dbh</span>-&gt;prepare<span class="ot">(</span><span class="kw">$sql_stmt</span><span class="ot">);</span></span>
<span id="cb1-7"><a href="#cb1-7"></a><span class="kw">$ret</span> = <span class="kw">$stmt</span>-&gt;bindParam<span class="ot">(</span><span class="dv">1</span><span class="ot">,</span> <span class="kw">$fp</span><span class="ot">,</span> <span class="kw">PDO</span>::<span class="kw">PARAM_LOB</span><span class="ot">);</span></span>
<span id="cb1-8"><a href="#cb1-8"></a><span class="kw">$ret</span> = <span class="kw">$stmt</span>-&gt;execute<span class="ot">();</span></span>
<span id="cb1-9"><a href="#cb1-9"></a><span class="kw">?&gt;</span></span></code></pre></div>
</div>
</div>
</div>
<div id="example-1042" class="example">
<p><strong>Example #2 Fetch LOBs in CUBRID PDO</strong></p>
<div class="example-contents">
<div class="phpcode">
<div class="sourceCode" id="cb2"><pre class="sourceCode php"><code class="sourceCode php"><span id="cb2-1"><a href="#cb2-1"></a><span class="kw">&lt;?php</span></span>
<span id="cb2-2"><a href="#cb2-2"></a><span class="kw">$sql_stmt</span> = <span class="st">&quot;SELECT content FROM lob_test WHERE name=&#39;lob_test.png&#39;&quot;</span><span class="ot">;</span></span>
<span id="cb2-3"><a href="#cb2-3"></a></span>
<span id="cb2-4"><a href="#cb2-4"></a><span class="kw">$stmt</span> = <span class="kw">$dbh</span>-&gt;prepare<span class="ot">(</span><span class="kw">$sql_stmt</span><span class="ot">);</span></span>
<span id="cb2-5"><a href="#cb2-5"></a><span class="kw">$stmt</span>-&gt;execute<span class="ot">();</span></span>
<span id="cb2-6"><a href="#cb2-6"></a><span class="kw">$result</span> = <span class="kw">$stmt</span>-&gt;fetch<span class="ot">(</span><span class="kw">PDO</span>::<span class="kw">FETCH_NUM</span><span class="ot">);</span></span>
<span id="cb2-7"><a href="#cb2-7"></a></span>
<span id="cb2-8"><a href="#cb2-8"></a><span class="fu">header</span><span class="ot">(</span><span class="st">&quot;Content-Type: image/png&quot;</span><span class="ot">);</span></span>
<span id="cb2-9"><a href="#cb2-9"></a><span class="fu">fpassthru</span><span class="ot">(</span><span class="kw">$result</span><span class="ot">[</span><span class="dv">0</span><span class="ot">]);</span></span>
<span id="cb2-10"><a href="#cb2-10"></a><span class="kw">?&gt;</span></span></code></pre></div>
</div>
</div>
</div></td>
</tr>
<tr class="odd">
<td>Column meta</td>
<td>The <span class="function">PDOStatement::getColumnMeta</span> in CUBRID PDO will return an associative array containing the following values:
<ul>
<li>type</li>
<li>name</li>
<li>table</li>
<li>def</li>
<li>precision</li>
<li>scale</li>
<li>not_null</li>
<li>auto_increment</li>
<li>unique_key</li>
<li>multiple_key</li>
<li>primary_key</li>
<li>foreign_key</li>
<li>reverse_index</li>
<li>reverse_unique</li>
</ul></td>
</tr>
<tr class="even">
<td>Collection Data Type</td>
<td>PDO_CUBRID supports SET/MULTISET/SEQUENCE data type. If you don't specify data type, the default data type is char,for example:
<div id="example-1043" class="example">
<p><strong>Example #3 Insert set in CUBRID PDO with default data type.</strong></p>
<div class="example-contents">
<div class="phpcode">
<div class="sourceCode" id="cb3"><pre class="sourceCode php"><code class="sourceCode php"><span id="cb3-1"><a href="#cb3-1"></a><span class="kw">&lt;?php</span></span>
<span id="cb3-2"><a href="#cb3-2"></a><span class="kw">$conn_str</span> =<span class="st">&quot;cubrid:dbname=demodb;host=localhost;port=33000&quot;</span><span class="ot">;</span></span>
<span id="cb3-3"><a href="#cb3-3"></a><span class="kw">$cubrid_pdo</span> = <span class="kw">new</span> <span class="kw">PDO</span><span class="ot">(</span><span class="kw">$conn_str</span><span class="ot">,</span> <span class="st">&#39;dba&#39;</span><span class="ot">,</span> <span class="st">&#39;&#39;</span><span class="ot">);</span></span>
<span id="cb3-4"><a href="#cb3-4"></a></span>
<span id="cb3-5"><a href="#cb3-5"></a><span class="kw">$cubrid_pdo</span>-&gt;<span class="fu">exec</span><span class="ot">(</span><span class="st">&quot;DROP TABLE if exists test_tbl&quot;</span><span class="ot">);</span> </span>
<span id="cb3-6"><a href="#cb3-6"></a><span class="kw">$cubrid_pdo</span>-&gt;<span class="fu">exec</span><span class="ot">(</span><span class="st">&quot;CREATE TABLE test_tbl (col_1 SET(VARCHAR))&quot;</span><span class="ot">);</span></span>
<span id="cb3-7"><a href="#cb3-7"></a> </span>
<span id="cb3-8"><a href="#cb3-8"></a><span class="kw">$sql_stmt_insert</span> = <span class="st">&quot;INSERT INTO test_tbl VALUES (?);&quot;</span><span class="ot">;</span></span>
<span id="cb3-9"><a href="#cb3-9"></a><span class="kw">$stmt</span> = <span class="kw">$cubrid_pdo</span>-&gt;prepare<span class="ot">(</span><span class="kw">$sql_stmt_insert</span><span class="ot">);</span></span>
<span id="cb3-10"><a href="#cb3-10"></a><span class="kw">$data</span> = <span class="kw">array</span><span class="ot">(</span><span class="st">&quot;abc&quot;</span><span class="ot">,</span><span class="st">&quot;def&quot;</span><span class="ot">,</span><span class="st">&quot;ghi&quot;</span><span class="ot">);</span></span>
<span id="cb3-11"><a href="#cb3-11"></a><span class="kw">$ret</span> = <span class="kw">$stmt</span>-&gt;bindParam<span class="ot">(</span><span class="dv">1</span><span class="ot">,</span> <span class="kw">$data</span><span class="ot">,</span> <span class="kw">PDO</span>::<span class="kw">PARAM_NULL</span><span class="ot">);</span></span>
<span id="cb3-12"><a href="#cb3-12"></a><span class="kw">$ret</span> = <span class="kw">$stmt</span>-&gt;execute<span class="ot">();</span></span>
<span id="cb3-13"><a href="#cb3-13"></a><span class="fu">var_Dump</span><span class="ot">(</span><span class="kw">$ret</span><span class="ot">);</span></span>
<span id="cb3-14"><a href="#cb3-14"></a><span class="kw">?&gt;</span></span></code></pre></div>
</div>
</div>
</div>
<div id="example-1044" class="example">
<p><strong>Example #4 Specify data type when insert set in CUBRID PDO</strong></p>
<div class="example-contents">
<div class="phpcode">
<div class="sourceCode" id="cb4"><pre class="sourceCode php"><code class="sourceCode php"><span id="cb4-1"><a href="#cb4-1"></a><span class="kw">&lt;?php</span></span>
<span id="cb4-2"><a href="#cb4-2"></a><span class="kw">$conn_str</span> =<span class="st">&quot;cubrid:dbname=demodb;host=localhost;port=33000&quot;</span><span class="ot">;</span></span>
<span id="cb4-3"><a href="#cb4-3"></a><span class="kw">$cubrid_pdo</span> = <span class="kw">new</span> <span class="kw">PDO</span><span class="ot">(</span><span class="kw">$conn_str</span><span class="ot">,</span> <span class="st">&#39;dba&#39;</span><span class="ot">,</span> <span class="st">&#39;&#39;</span><span class="ot">);</span></span>
<span id="cb4-4"><a href="#cb4-4"></a></span>
<span id="cb4-5"><a href="#cb4-5"></a><span class="kw">$cubrid_pdo</span>-&gt;<span class="fu">exec</span><span class="ot">(</span><span class="st">&quot;DROP TABLE if exists test_tbl&quot;</span><span class="ot">);</span> </span>
<span id="cb4-6"><a href="#cb4-6"></a><span class="kw">$cubrid_pdo</span>-&gt;<span class="fu">exec</span><span class="ot">(</span><span class="st">&quot;CREATE TABLE test_tbl (col_1 SET(int))&quot;</span><span class="ot">);</span></span>
<span id="cb4-7"><a href="#cb4-7"></a> </span>
<span id="cb4-8"><a href="#cb4-8"></a><span class="kw">$sql_stmt_insert</span> = <span class="st">&quot;INSERT INTO test_tbl VALUES (?);&quot;</span><span class="ot">;</span></span>
<span id="cb4-9"><a href="#cb4-9"></a><span class="kw">$stmt</span> = <span class="kw">$cubrid_pdo</span>-&gt;prepare<span class="ot">(</span><span class="kw">$sql_stmt_insert</span><span class="ot">);</span></span>
<span id="cb4-10"><a href="#cb4-10"></a><span class="kw">$data</span> = <span class="kw">array</span><span class="ot">(</span><span class="dv">1</span><span class="ot">,</span><span class="dv">2</span><span class="ot">,</span><span class="dv">3</span><span class="ot">,</span><span class="dv">4</span><span class="ot">);</span></span>
<span id="cb4-11"><a href="#cb4-11"></a><span class="kw">$ret</span> = <span class="kw">$stmt</span>-&gt;bindParam<span class="ot">(</span><span class="dv">1</span><span class="ot">,</span> <span class="kw">$data</span><span class="ot">,</span> <span class="dv">0</span><span class="ot">,</span><span class="dv">0</span><span class="ot">,</span><span class="st">&quot;int&quot;</span><span class="ot">);</span></span>
<span id="cb4-12"><a href="#cb4-12"></a><span class="kw">$ret</span> = <span class="kw">$stmt</span>-&gt;execute<span class="ot">();</span></span>
<span id="cb4-13"><a href="#cb4-13"></a><span class="fu">var_Dump</span><span class="ot">(</span><span class="kw">$ret</span><span class="ot">);</span></span>
<span id="cb4-14"><a href="#cb4-14"></a><span class="kw">?&gt;</span></span></code></pre></div>
</div>
</div>
</div>
CUBRID Bind Data Types:(The fifth parameter of PDOStatement::bindParam):
<ul>
<li>CHAR</li>
<li>STRING</li>
<li>NCHAR</li>
<li>VARNCHAR</li>
<li>BIT</li>
<li>VARBIT</li>
<li>NUMERIC</li>
<li>NUMBER</li>
<li>INT</li>
<li>SHORT</li>
<li>BIGINT</li>
<li>MONETARY</li>
<li>FLOAT</li>
<li>DOUBLE</li>
<li>DATE</li>
<li>TIME</li>
<li>DATETIME</li>
<li>TIMESTAMP</li>
</ul></td>
</tr>
</tbody>
</table>

Predefined Constants
--------------------

The constants below are defined by this driver, and will only be
available when the extension has been either compiled into PHP or
dynamically loaded at runtime. In addition, these driver-specific
constants should only be used if you are using this driver. Using
driver-specific attributes with another driver may result in unexpected
behaviour. <span class="function">PDO::getAttribute</span> may be used
to obtain the **`PDO::ATTR_DRIVER_NAME`** attribute to check the driver,
if your code can run against multiple drivers.

The following constants can be used when setting the database attribute.
They can be passed to <span class="function">PDO::getAttribute</span> or
<span class="function">PDO::setAttribute</span>.

| Constant                               | Description                                                                                                                     |
|----------------------------------------|---------------------------------------------------------------------------------------------------------------------------------|
| PDO::CUBRID\_ATTR\_ISOLATION\_LEVEL    | Transaction isolation level for the database connection.                                                                        |
| PDO::CUBRID\_ATTR\_LOCK\_TIMEOUT       | Transaction timeout in seconds.                                                                                                 |
| PDO::CUBRID\_ATTR\_MAX\_STRING\_LENGTH | Read only. The maximum string length for bit, varbit, char, varchar, nchar, nchar varying data types when using CUBRID PDO API. |

The following constants can be used when setting the transaction
isolation level. They can be passed to <span
class="function">PDO::getAttribute</span> or returned by <span
class="function">PDO::setAttribute</span>.

| Constant                                     | Description                                                                                                                                                |
|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PDO::TRAN\_COMMIT\_CLASS\_UNCOMMIT\_INSTANCE | The lowest isolation level (1). A dirty, non-repeatable or phantom read may occur for the tuple and a non-repeatable read may occur for the table as well. |
| PDO::TRAN\_COMMIT\_CLASS\_COMMIT\_INSTANCE   | A relatively low isolation level (2). A dirty read does not occur, but non-repeatable or phantom read may occur.                                           |
| PDO::TRAN\_REP\_CLASS\_UNCOMMIT\_INSTANCE    | The default isolation of CUBRID (3). A dirty, non-repeatable or phantom read may occur for the tuple, but repeatable read is ensured for the table.        |
| PDO::TRAN\_REP\_CLASS\_COMMIT\_INSTANCE      | A relatively low isolation level (4). A dirty read does not occur, but non-repeatable or phantom read may.                                                 |
| PDO::TRAN\_REP\_CLASS\_REP\_INSTANCE         | A relatively high isolation level (5). A dirty or non-repeatable read does not occur, but a phantom read may.                                              |
| PDO::TRAN\_SERIALIZABLE                      | The highest isolation level (6). Problems concerning concurrency (e.g. dirty read, non-repeatable read, phantom read, etc.) do not occur.                  |

The following constants can be used when getting schema information.
They can be passed to <span class="function">PDO::cubrid\_schema</span>.

| Constant                               | Description                                                                                                                                                                                               |
|----------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PDO::CUBRID\_SCH\_TABLE                | Get name and type of table in CUBRID.                                                                                                                                                                     |
| PDO::CUBRID\_SCH\_VIEW                 | Get name and type of view in CUBRID.                                                                                                                                                                      |
| PDO::CUBRID\_SCH\_QUERY\_SPEC          | Get the query definition of view.                                                                                                                                                                         |
| PDO::CUBRID\_SCH\_ATTRIBUTE            | Get the attributes of table column.                                                                                                                                                                       |
| PDO::CUBRID\_SCH\_TABLE\_ATTRIBUTE     | Get the attributes of table.                                                                                                                                                                              |
| PDO::CUBRID\_SCH\_METHOD               | Get the instance method. The instance method is a method called by a class instance. It is used more often than the class method because most operations are executed in the instance.                    |
| PDO::CUBRID\_SCH\_TABLE\_METHOD        | Get the class method. The class method is a method called by a class object. It is usually used to create a new class instance or to initialize it. It is also used to access or update class attributes. |
| PDO::CUBRID\_SCH\_METHOD\_FILE         | Get the information of the file where the method of the table is defined.                                                                                                                                 |
| PDO::CUBRID\_SCH\_SUPER\_TABLE         | Get the name and type of table which table inherites attributes from.                                                                                                                                     |
| PDO::CUBRID\_SCH\_SUB\_TABLE           | Get the name and type of table which inherites attributes from this table.                                                                                                                                |
| PDO::CUBRID\_SCH\_CONSTRAINT           | Get the table constraints.                                                                                                                                                                                |
| PDO::CUBRID\_SCH\_TRIGGER              | Get the table triggers.                                                                                                                                                                                   |
| PDO::CUBRID\_SCH\_TABLE\_PRIVILEGE     | Get the privilege information of table.                                                                                                                                                                   |
| PDO::CUBRID\_SCH\_COL\_PRIVILEGE       | Get the privilege information of column.                                                                                                                                                                  |
| PDO::CUBRID\_SCH\_DIRECT\_SUPER\_TABLE | Get the direct super table of table.                                                                                                                                                                      |
| PDO::CUBRID\_SCH\_PRIMARY\_KEY         | Get the table primary key.                                                                                                                                                                                |
| PDO::CUBRID\_SCH\_IMPORTED\_KEYS       | Get imported keys of table.                                                                                                                                                                               |
| PDO::CUBRID\_SCH\_EXPORTED\_KEYS       | Get exported keys of table.                                                                                                                                                                               |
| PDO::CUBRID\_SCH\_CROSS\_REFERENCE     | Get reference relationship of tow tables.                                                                                                                                                                 |

PDO\_CUBRID DSN
===============

Connecting to CUBRID databases

### Description

The PDO\_CUBRID Data Source Name (DSN) is composed of the following
elements, delimited by semicolons:

DSN prefix  
The DSN prefix is **`cubrid:`**.

*host*  
The hostname on which the database server resides.

*port*  
The port on which the database server is running.

*dbname*  
The name of the database.

### Notes

> **Note**:
>
> When you estalish the connection to CUBRID, you should give username
> and password except DSN.

### Examples

**Example \#1 PDO\_CUBRID DSN examples**

The following example shows a PDO\_CUBRID DSN for connecting to a CUBRID
database:

    cubrid:host=localhost;port=33000;dbname=demodb

PDO::cubrid\_schema
===================

Get the requested schema information

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">PDO::cubrid\_schema</span> ( <span
class="methodparam"><span class="type">int</span> `$schema_type`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$table_name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$col_name`</span> \]\] )

This function is used to get the requested schema information from
database. You have to designate `table_name`, if you want to get
information on certain table, `col_name`, if you want to get information
on certain column (can be used only with
PDO::CUBRID\_SCH\_COL\_PRIVILEGE).

The result of this function is returned as a two-dimensional array
(column (associative array) \* row (numeric array)). The following
tables shows types of schema and the column structure of the result
array to be returned based on the schema type.

| Schema                                                                                                   | Column Number | Column Name              | Value                                             |
|----------------------------------------------------------------------------------------------------------|---------------|--------------------------|---------------------------------------------------|
| PDO::CUBRID\_SCH\_TABLE                                                                                  | 1             | NAME                     |                                                   |
|                                                                                                          | 2             | TYPE                     | 0:system table 1:view 2:table                     |
| PDO::CUBRID\_SCH\_VIEW                                                                                   | 1             | NAME                     |                                                   |
|                                                                                                          | 2             | TYPE                     | 1:view                                            |
| PDO::CUBRID\_SCH\_QUERY\_SPEC                                                                            | 1             | QUERY\_SPEC              |                                                   |
| PDO::CUBRID\_SCH\_ATTRIBUTE / PDO::CUBRID\_SCH\_TABLE\_ATTRIBUTE                                         | 1             | ATTR\_NAME               |                                                   |
|                                                                                                          | 2             | DOMAIN                   |                                                   |
|                                                                                                          | 3             | SCALE                    |                                                   |
|                                                                                                          | 4             | PRECISION                |                                                   |
|                                                                                                          | 5             | INDEXED                  | 1:indexed                                         |
|                                                                                                          | 6             | NOT NULL                 | 1:not null                                        |
|                                                                                                          | 7             | SHARED                   | 1:shared                                          |
|                                                                                                          | 8             | UNIQUE                   | 1:unique                                          |
|                                                                                                          | 9             | DEFAULT                  |                                                   |
|                                                                                                          | 10            | ATTR\_ORDER              | base:1                                            |
|                                                                                                          | 11            | CLASS\_NAME              |                                                   |
|                                                                                                          | 12            | SOURCE\_CLASS            |                                                   |
|                                                                                                          | 13            | IS\_KEY                  | 1:key                                             |
| PDO::CUBRID\_SCH\_METHOD / PDO::CUBRID\_SCH\_TABLE\_METHOD                                               | 1             | NAME                     |                                                   |
|                                                                                                          | 2             | RET\_DOMAIN              |                                                   |
|                                                                                                          | 3             | ARG\_DOMAIN              |                                                   |
| PDO::CUBRID\_SCH\_METHOD\_FILE                                                                           | 1             | METHOD\_FILE             |                                                   |
| PDO::CUBRID\_SCH\_SUPER\_TABLE / PDO::CUBRID\_SCH\_DIRECT\_SUPER\_TABLE / PDO::CUBRID\_SCH\_SUB\_TABLE   | 1             | CLASS\_NAME              |                                                   |
|                                                                                                          | 2             | TYPE                     | 0:system table 1:view 2:table                     |
| PDO::CUBRID\_SCH\_CONSTRAINT                                                                             | 1             | TYPE                     | 0:unique 1:index 2:reverse unique 3:reverse index |
|                                                                                                          | 2             | NAME                     |                                                   |
|                                                                                                          | 3             | ATTR\_NAME               |                                                   |
|                                                                                                          | 4             | NUM\_PAGES               |                                                   |
|                                                                                                          | 5             | NUM\_KEYS                |                                                   |
|                                                                                                          | 6             | PRIMARY\_KEY             | 1:primary key                                     |
|                                                                                                          | 7             | KEY\_ORDER               | base:1                                            |
| PDO::CUBRID\_SCH\_TRIGGER                                                                                | 1             | NAME                     |                                                   |
|                                                                                                          | 2             | STATUS                   |                                                   |
|                                                                                                          | 3             | EVENT                    |                                                   |
|                                                                                                          | 4             | TARGET\_CLASS            |                                                   |
|                                                                                                          | 5             | TARGET\_ATTR             |                                                   |
|                                                                                                          | 6             | ACTION\_TIME             |                                                   |
|                                                                                                          | 7             | ACTION                   |                                                   |
|                                                                                                          | 8             | PRIORITY                 |                                                   |
|                                                                                                          | 9             | CONDITION\_TIME          |                                                   |
|                                                                                                          | 10            | CONDITION                |                                                   |
| PDO::CUBRID\_SCH\_TABLE\_PRIVILEGE / PDO::CUBRID\_SCH\_COL\_PRIVILEGE                                    | 1             | CLASS\_NAME / ATTR\_NAME |                                                   |
|                                                                                                          | 2             | PRIVILEGE                |                                                   |
|                                                                                                          | 3             | GRANTABLE                |                                                   |
| PDO::CUBRID\_SCH\_PRIMARY\_KEY                                                                           | 1             | CLASS\_NAME              |                                                   |
|                                                                                                          | 2             | ATTR\_NAME               |                                                   |
|                                                                                                          | 3             | KEY\_SEQ                 | base:1                                            |
|                                                                                                          | 4             | KEY\_NAME                |                                                   |
| PDO::CUBRID\_SCH\_IMPORTED\_KEYS / PDO::CUBRID\_SCH\_EXPORTED\_KEYS / PDO::CUBRID\_SCH\_CROSS\_REFERENCE | 1             | PKTABLE\_NAME            |                                                   |
|                                                                                                          | 2             | PKCOLUMN\_NAME           |                                                   |
|                                                                                                          | 3             | FKTABLE\_NAME            | base:1                                            |
|                                                                                                          | 4             | FKCOLUMN\_NAME           |                                                   |
|                                                                                                          | 5             | KEY\_SEQ                 | base:1                                            |
|                                                                                                          | 6             | UPDATE\_ACTION           | 0:cascade 1:restrict 2:no action 3:set null       |
|                                                                                                          | 7             | DELETE\_ACTION           | 0:cascade 1:restrict 2:no action 3:set null       |
|                                                                                                          | 8             | FK\_NAME                 |                                                   |
|                                                                                                          | 9             | PK\_NAME                 |                                                   |

### Parameters

`schema_type`  
Schema type that you want to know.

`table_name`  
Table you want to know the schema of.

`col_name`  
Column you want to know the schema of.

### Return Values

Array containing the schema information, when process is successful;

FALSE, when process is unsuccessful

### Examples

**Example \#1 A <span class="function">PDO::cubrid\_schema</span>
example**

This example shows how to get primary key and foreign keys of table
game.

``` php
<?php
$pk_list = $dbh->cubrid_schema(PDO::CUBRID_SCH_PRIMARY_KEY, "game");
print_r($pk_list);

$fk_list = $dbh->cubrid_schema(PDO::CUBRID_SCH_IMPORTED_KEYS, "game");
print_r($fk_list);
?>
```

The above example will output:

    Result:
    Array
    (
        [0] => Array
            (
                [CLASS_NAME] => game
                [ATTR_NAME] => athlete_code
                [KEY_SEQ] => 3
                [KEY_NAME] => pk_game_host_year_event_code_athlete_code
            )

        [1] => Array
            (
                [CLASS_NAME] => game
                [ATTR_NAME] => event_code
                [KEY_SEQ] => 2
                [KEY_NAME] => pk_game_host_year_event_code_athlete_code
            )

        [2] => Array
            (
                [CLASS_NAME] => game
                [ATTR_NAME] => host_year
                [KEY_SEQ] => 1
                [KEY_NAME] => pk_game_host_year_event_code_athlete_code
            )

    )
    Array
    (
        [0] => Array
            (
                [PKTABLE_NAME] => athlete
                [PKCOLUMN_NAME] => code
                [FKTABLE_NAME] => game
                [FKCOLUMN_NAME] => athlete_code
                [KEY_SEQ] => 1
                [UPDATE_RULE] => 1
                [DELETE_RULE] => 1
                [FK_NAME] => fk_game_athlete_code
                [PK_NAME] => pk_athlete_code
            )

        [1] => Array
            (
                [PKTABLE_NAME] => event
                [PKCOLUMN_NAME] => code
                [FKTABLE_NAME] => game
                [FKCOLUMN_NAME] => event_code
                [KEY_SEQ] => 1
                [UPDATE_RULE] => 1
                [DELETE_RULE] => 1
                [FK_NAME] => fk_game_event_code
                [PK_NAME] => pk_event_code
            )

    )

**Table of Contents**

-   [PDO\_CUBRID DSN](/book/pdo.html#PDO_CUBRID%20DSN) — Connecting to
    CUBRID databases
-   [PDO::cubrid\_schema](/book/pdo.html#PDO::cubrid_schema) — Get the
    requested schema information

Introduction
------------

PDO\_DBLIB is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO) interface</a>
to enable access from PHP to Microsoft SQL Server and Sybase databases
through the FreeTDS library.

This extension is not available anymore on Windows with PHP 5.3 or
later.

On Windows, you should use SqlSrv, an alternative driver for MS SQL is
available from Microsoft:
<a href="http://msdn.microsoft.com/en-us/sqlserver/ff657782.aspx" class="link external">» http://msdn.microsoft.com/en-us/sqlserver/ff657782.aspx</a>
.

If it is not possible to use SqlSrv, you can use the
<a href="/book/pdo.html#ODBC%20and%20DB2%20(PDO)" class="link">PDO_ODBC</a>
driver to connect to Microsoft SQL Server and Sybase databases, as the
native Windows DB-LIB is ancient, thread un-safe and no longer supported
by Microsoft.

PDO\_DBLIB DSN
==============

Connecting to Microsoft SQL Server and Sybase databases

### Description

The PDO\_DBLIB Data Source Name (DSN) is composed of the following
elements:

DSN prefix  
The DSN prefix is **`sybase:`** if PDO\_DBLIB was linked against the
Sybase ct-lib libraries, **`mssql:`** if PDO\_DBLIB was linked against
the Microsoft SQL Server libraries, or **`dblib:`** if PDO\_DBLIB was
linked against the FreeTDS libraries.

*host*  
The hostname on which the database server resides. Defaults to
127.0.0.1.

*dbname*  
The name of the database.

*charset*  
The client character set.

*appname*  
The application name (used in sysprocesses). Defaults to "PHP Generic
DB-lib" or "PHP freetds".

*secure*  
Currently unused.

### Examples

**Example \#1 PDO\_DBLIB DSN examples**

The following examples show a PDO\_DBLIB DSN for connecting to Microsoft
SQL Server and Sybase databases:

    mssql:host=localhost;dbname=testdb
    sybase:host=localhost;dbname=testdb
    dblib:host=localhost;dbname=testdb

**Table of Contents**

-   [PDO\_DBLIB DSN](/book/pdo.html#PDO_DBLIB%20DSN) — Connecting to
    Microsoft SQL Server and Sybase databases

Introduction
------------

PDO\_FIREBIRD is a driver that implements the PHP Data Objects (PDO)
interface to enable access from PHP to Firebird database.

Installation
------------

Use **--with-pdo-firebird\[=DIR\]** to install the PDO Firebird
extension, where the optional *\[=DIR\]* is the Firebird base install
directory.

    $ ./configure --with-pdo-firebird

Predefined Constants
--------------------

The constants below are defined by this driver, and will only be
available when the extension has been either compiled into PHP or
dynamically loaded at runtime. In addition, these driver-specific
constants should only be used if you are using this driver. Using
driver-specific attributes with another driver may result in unexpected
behaviour. <span class="function">PDO::getAttribute</span> may be used
to obtain the **`PDO::ATTR_DRIVER_NAME`** attribute to check the driver,
if your code can run against multiple drivers.

**`PDO::FB_ATTR_DATE_FORMAT`** (<span class="type">int</span>)  
Available since PHP 5.3.0.

Sets the date format.

**`PDO::FB_ATTR_TIME_FORMAT`** (<span class="type">int</span>)  
Sets the time format.

Available since PHP 5.3.0.

**`PDO::FB_ATTR_TIMESTAMP_FORMAT`** (<span class="type">int</span>)  
Sets the timestamp format.

Available since PHP 5.3.0.

PDO\_FIREBIRD DSN
=================

Connecting to Firebird databases

### Description

The PDO\_FIREBIRD Data Source Name (DSN) is composed of the following
elements:

DSN prefix  
The DSN prefix is **`firebird:`**.

*dbname*  
The name of the database.

*charset*  
The character set.

*role*  
The SQL role name.

*dialect*  
The dialect of the database; either *1* or *3*. If not specified, the
dialect defaults to *3*. Available as of PHP 7.4.0.

### Examples

**Example \#1 PDO\_FIREBIRD DSN example with path**

The following example shows a PDO\_FIREBIRD DSN for connecting to
Firebird databases:

    firebird:dbname=/path/to/DATABASE.FDB

**Example \#2 PDO\_FIREBIRD DSN example with port and path**

The following example shows a PDO\_FIREBIRD DSN for connecting to a
Firebird database using hostname port and path:

    firebird:dbname=hostname/port:/path/to/DATABASE.FDB

**Example \#3 PDO\_FIREBIRD DSN example with localhost and path to
employee.fdb on Debian system**

The following example shows a PDO\_FIREBIRD DSN for connecting to a
Firebird database employee.fdb using localhost:

    firebird:dbname=localhost:/var/lib/firebird/2.5/data/employee.fdb

**Example \#4 PDO\_FIREBIRD DSN to connect to a dialect 1 database**

The following example shows a PDO\_FIREBIRD DSN for connecting to a
Firebird database test.fdb which has been created using dialect 1. This
is only supported as of PHP 7.4.0.

    firebird:dbname=localhost:/var/lib/firebird/2.5/data/test.fdb;charset=utf-8;dialect=1

**Table of Contents**

-   [PDO\_FIREBIRD DSN](/book/pdo.html#PDO_FIREBIRD%20DSN) — Connecting
    to Firebird databases

Introduction
------------

PDO\_IBM is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO)</a>
interface to enable access from PHP to IBM databases.

Installation
------------

To build the PDO\_IBM extension, the DB2 Client v9.1 or later must be
installed on the same system as PHP. The DB2 Client can be downloaded
from the IBM
<a href="http://www.ibm.com/software/data/db2/ad" class="link external">» Application Development Site</a>.

> **Note**: **Note**  
>
> The DB2 Client v9.1 or later supports direct access to DB2 for Linux,
> UNIX, and Windows v8 and v9.1 servers.
>
> The DB2 Client v9.1 also supports access to DB2 UDB for i5 and DB2 UDB
> for z/OS servers using the separately purchased
> <a href="http://www.ibm.com/software/data/db2/db2connect" class="link external">» DB2 Connect product</a>.

PDO\_IBM is a
<a href="https://pecl.php.net/" class="link external">» PECL</a>
extension, so follow the instructions in
<a href="/install/pecl.html" class="xref">Installation of PECL extensions</a>
to install the PDO\_IBM extension. Issue the **configure** command to
point to the location of your DB2 Client header files and libraries as
follows:

    bash$ ./configure --with-pdo-ibm=/path/to/sqllib[,shared]

The **configure** command defaults to the value of the *DB2DIR*
environment variable.

PDO\_IBM DSN
============

Connecting to IBM databases

### Description

The PDO\_IBM Data Source Name (DSN) is based on the IBM CLI DSN. The
major components of the PDO\_IBM DSN are:

DSN prefix  
The DSN prefix is **`ibm:`**.

DSN  
The DSN can be any of the following:

-   a\) Data source setup using `db2cli.ini` or `odbc.ini`

-   b\) Catalogued database name i.e. database alias in the DB2 client
    catalog

-   c\) Complete connection string in the following format:
    `DRIVER={IBM DB2 ODBC DRIVER};DATABASE=database`;HOSTNAME=`hostname`;PORT=`port`;PROTOCOL=TCPIP;UID=`username`;PWD=`password`;
    where the parameters represent the following values:

    `database`  
    The name of the database.

    `hostname`  
    The hostname or IP address of the database server.

    `port`  
    The TCP/IP port on which the database is listening for requests.

    `username`  
    The username with which you are connecting to the database.

    `password`  
    The password with which you are connecting to the database.

### Examples

**Example \#1 PDO\_IBM DSN example using `db2cli.ini`**

The following example shows a PDO\_IBM DSN for connecting to an DB2
database cataloged as DB2\_9 in `db2cli.ini`:

    $db = new PDO("ibm:DSN=DB2_9", "", "");

    [DB2_9]
    Database=testdb
    Protocol=tcpip
    Hostname=11.22.33.444
    Servicename=56789

**Example \#2 PDO\_IBM DSN example using a connection string**

The following example shows a PDO\_IBM DSN for connecting to an DB2
database named **`testdb`** using the DB2 CLI connection string syntax.

    $db = new PDO("ibm:DRIVER={IBM DB2 ODBC DRIVER};DATABASE=testdb;" .
      "HOSTNAME=11.22.33.444;PORT=56789;PROTOCOL=TCPIP;", "testuser", "tespass");

**Table of Contents**

-   [PDO\_IBM DSN](/book/pdo.html#PDO_IBM%20DSN) — Connecting to IBM
    databases

Introduction
------------

PDO\_INFORMIX is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO)</a>
interface to enable access from PHP to Informix databases.

Installation
------------

To build the PDO\_INFORMIX extension, the Informix Client SDK 2.81 UC1
or higher must be installed on the same system as PHP. The Informix
Client SDK is available from the
<a href="http://www-306.ibm.com/software/data/informix/tools/csdk/" class="link external">» IBM Informix Support Site</a>.

PDO\_INFORMIX is a
<a href="https://pecl.php.net/" class="link external">» PECL</a>
extension, so follow the instructions in
<a href="/install/pecl.html" class="xref">Installation of PECL extensions</a>
to install the PDO\_INFORMIX extension. Issue the **configure** command
to point to the location of your Informix Client SDK header files and
libraries as follows:

       bash$ ./configure --with-pdo-informix=/path/to/SDK[,shared]

The **configure** command defaults to the value of the *INFORMIXDIR*
environment variable.

Scrollable cursors
------------------

PDO\_INFORMIX supports scrollable cursors; however, they are not enabled
by default. To enable scrollable cursor support, you must either set
**`ENABLESCROLLABLECURSORS=1`** in the corresponding ODBC connection
settings in `odbc.ini` or pass the **`EnableScrollableCursors=1`**
clause in the DSN connection string.

PDO\_INFORMIX DSN
=================

Connecting to Informix databases

### Description

The PDO\_INFORMIX Data Source Name (DSN) is based on the Informix ODBC
DSN string. Details on configuring an Informix ODBC DSN are available
from the
<a href="http://publib.boulder.ibm.com/infocenter/idshelp/v10/index.jsp" class="link external">» Informix Dynamic Server Information Center</a>.
The major components of the PDO\_INFORMIX DSN are:

DSN prefix  
The DSN prefix is **`informix:`**.

DSN  
The DSN can be either a data source setup using `odbc.ini` or a complete
<a href="http://publib.boulder.ibm.com/infocenter/idshelp/v10/topic/com.ibm.odbc.doc/odbc66.htm#sii02998361" class="link external">» connection string</a>.

### Examples

**Example \#1 PDO\_INFORMIX DSN example using `odbc.ini`**

The following example shows a PDO\_INFORMIX DSN for connecting to an
Informix database cataloged as Infdrv33 in `odbc.ini`:

    $db = new PDO("informix:DSN=Infdrv33", "", "");

    [ODBC Data Sources]
    Infdrv33=INFORMIX 3.3 32-BIT

    [Infdrv33]
    Driver=/opt/informix/csdk_2.81.UC1G2/lib/cli/iclis09b.so
    Description=INFORMIX 3.3 32-BIT
    Database=common_db
    LogonID=testuser
    pwd=testpass
    Servername=ids_server
    DB_LOCALE=en_US.819
    OPTIMIZEAUTOCOMMIT=1
    ENABLESCROLLABLECURSORS=1

**Example \#2 PDO\_INFORMIX DSN example using a connection string**

The following example shows a PDO\_INFORMIX DSN for connecting to an
Informix database named **`common_db`** using the Informix connection
string syntax.

    $db = new PDO("informix:host=host.domain.com; service=9800;
        database=common_db; server=ids_server; protocol=onsoctcp;
        EnableScrollableCursors=1", "testuser", "tespass");

**Table of Contents**

-   [PDO\_INFORMIX DSN](/book/pdo.html#PDO_INFORMIX%20DSN) — Connecting
    to Informix databases

Introduction
------------

PDO\_MYSQL is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO) interface</a>
to enable access from PHP to MySQL databases.

As of PHP 5.2.1, PDO\_MYSQL uses emulated prepares by default. Formerly,
PDO\_MYSQL defaulted to native prepared statement support present in
MySQL 4.1 and higher, and emulated them for older versions of the mysql
client libraries.

*MySQL 8*

When running a PHP version before 7.1.16, or PHP 7.2 before 7.2.4, set
MySQL 8 Server's default password plugin to *mysql\_native\_password* or
else you will see errors similar to *The server requested authentication
method unknown to the client \[caching\_sha2\_password\]* even when
*caching\_sha2\_password* is not used.

This is because MySQL 8 defaults to caching\_sha2\_password, a plugin
that is not recognized by the older PHP (mysqlnd) releases. Instead,
change it by setting
*default\_authentication\_plugin=mysql\_native\_password* in `my.cnf`.
The *caching\_sha2\_password* plugin will be supported in a future PHP
release. In the meantime, the
<a href="/set/mysqlinfo.html#Mysql_xdevapi" class="link">mysql_xdevapi</a>
extension does support it.

**Warning**

Beware: Some MySQL table types (storage engines) do not support
transactions. When writing transactional database code using a table
type that does not support transactions, MySQL will pretend that a
transaction was initiated successfully. In addition, any DDL queries
issued will implicitly commit any pending transactions.

Installation
------------

The common Unix distributions include binary versions of PHP that can be
installed. Although these binary versions are typically built with
support for the MySQL extensions, the extension libraries themselves may
need to be installed using an additional package. Check the package
manager than comes with your chosen distribution for availability.

For example, on Ubuntu the *php5-mysql* package installs the ext/mysql,
ext/mysqli, and PDO\_MYSQL PHP extensions. On CentOS, the *php-mysql*
package also installs these three PHP extensions.

Alternatively, you can compile this extension yourself. Building PHP
from source allows you to specify the MySQL extensions you want to use,
as well as your choice of client library for each extension.

When compiling, use **--with-pdo-mysql\[=DIR\]** to install the PDO
MySQL extension, where the optional *\[=DIR\]* is the MySQL base
library. As of PHP 5.4,
<a href="/set/mysqlinfo.html#Mysqlnd" class="link">mysqlnd</a> is the
default library. For details about choosing a library, see
<a href="/set/mysqlinfo.html#Choosing%20a%20library" class="link">Choosing a MySQL library</a>.

Optionally, the **--with-mysql-sock\[=DIR\]** sets to location to the
MySQL unix socket pointer for all MySQL extensions, including
PDO\_MYSQL. If unspecified, the default locations are searched.

Optionally, the **--with-zlib-dir\[=DIR\]** is used to set the path to
the libz install prefix.

    $ ./configure --with-pdo-mysql --with-mysql-sock=/var/mysql/mysql.sock

SSL support is enabled using the appropriate
<a href="/book/pdo.html#Predefined%20Constants" class="link">PDO_MySQL constants</a>,
which is equivalent to calling the
<a href="http://dev.mysql.com/doc/mysql/en/mysql-ssl-set.html" class="link external">» MySQL C API function mysql_ssl_set()</a>.
Also, SSL cannot be enabled with <span
class="classname">PDO::setAttribute</span> because the connection
already exists. See also the MySQL documentation about
<a href="http://dev.mysql.com/doc/mysql/en/configuring-for-ssl.html" class="link external">» connecting to MySQL with SSL</a>.

| Version | Description                                                                                                                                                                          |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.4.0   | <a href="/set/mysqlinfo.html#Mysqlnd" class="link">mysqlnd</a> became the default MySQL library when compiling PDO\_MYSQL. Previously, libmysqlclient was the default MySQL library. |
| 5.4.0   | MySQL client libraries 4.1 and below are no longer supported.                                                                                                                        |
| 5.3.9   | Added SSL support with mysqlnd and OpenSSL.                                                                                                                                          |
| 5.3.7   | Added SSL support with libmysqlclient and OpenSSL.                                                                                                                                   |

Predefined Constants
--------------------

The constants below are defined by this driver, and will only be
available when the extension has been either compiled into PHP or
dynamically loaded at runtime. In addition, these driver-specific
constants should only be used if you are using this driver. Using
driver-specific attributes with another driver may result in unexpected
behaviour. <span class="function">PDO::getAttribute</span> may be used
to obtain the **`PDO::ATTR_DRIVER_NAME`** attribute to check the driver,
if your code can run against multiple drivers.

**`PDO::MYSQL_ATTR_USE_BUFFERED_QUERY`** (<span class="type">int</span>)  
<span class="simpara"> If this attribute is set to **`TRUE`** on a <span
class="classname">PDOStatement</span>, the MySQL driver will use the
buffered versions of the MySQL API. If you're writing portable code, you
should use <span class="function">PDOStatement::fetchAll</span> instead.
</span>

**Example \#1 Forcing queries to be buffered in mysql**

``` php
<?php
if ($db->getAttribute(PDO::ATTR_DRIVER_NAME) == 'mysql') {
    $stmt = $db->prepare('select * from foo',
        array(PDO::MYSQL_ATTR_USE_BUFFERED_QUERY => true));
} else {
    die("my application only works with mysql; I should use \$stmt->fetchAll() instead");
}
?>
```

**`PDO::MYSQL_ATTR_LOCAL_INFILE`** (<span class="type">int</span>)  
Enable *LOAD LOCAL INFILE*.

Note, this constant can only be used in the `driver_options` array when
constructing a new database handle.

**`PDO::MYSQL_ATTR_LOCAL_INFILE_DIRECTORY`** (<span class="type">string</span>)  
Allows restricting LOCAL DATA loading to files located in this
designated directory.

Note, this constant can only be used in the `driver_options` array when
constructing a new database handle.

**`PDO::MYSQL_ATTR_INIT_COMMAND`** (<span class="type">int</span>)  
Command to execute when connecting to the MySQL server. Will
automatically be re-executed when reconnecting.

Note, this constant can only be used in the `driver_options` array when
constructing a new database handle.

**`PDO::MYSQL_ATTR_READ_DEFAULT_FILE`** (<span class="type">int</span>)  
Read options from the named option file instead of from `my.cnf`. This
option is not available if mysqlnd is used, because mysqlnd does not
read the mysql configuration files.

**`PDO::MYSQL_ATTR_READ_DEFAULT_GROUP`** (<span class="type">int</span>)  
Read options from the named group from `my.cnf` or the file specified
with **`MYSQL_READ_DEFAULT_FILE`**. This option is not available if
mysqlnd is used, because mysqlnd does not read the mysql configuration
files.

**`PDO::MYSQL_ATTR_MAX_BUFFER_SIZE`** (<span class="type">int</span>)  
Maximum buffer size. Defaults to 1 MiB. This constant is not supported
when compiled against mysqlnd.

**`PDO::MYSQL_ATTR_DIRECT_QUERY`** (<span class="type">int</span>)  
Perform direct queries, don't use prepared statements.

**`PDO::MYSQL_ATTR_FOUND_ROWS`** (<span class="type">int</span>)  
Return the number of found (matched) rows, not the number of changed
rows.

**`PDO::MYSQL_ATTR_IGNORE_SPACE`** (<span class="type">int</span>)  
Permit spaces after function names. Makes all functions names reserved
words.

**`PDO::MYSQL_ATTR_COMPRESS`** (<span class="type">int</span>)  
Enable network communication compression. This is also supported when
compiled against mysqlnd as of PHP 5.3.11.

**`PDO::MYSQL_ATTR_SSL_CA`** (<span class="type">int</span>)  
The file path to the SSL certificate authority.

This exists as of PHP 5.3.7.

**`PDO::MYSQL_ATTR_SSL_CAPATH`** (<span class="type">int</span>)  
The file path to the directory that contains the trusted SSL CA
certificates, which are stored in PEM format.

This exists as of PHP 5.3.7.

**`PDO::MYSQL_ATTR_SSL_CERT`** (<span class="type">int</span>)  
The file path to the SSL certificate.

This exists as of PHP 5.3.7.

**`PDO::MYSQL_ATTR_SSL_CIPHER`** (<span class="type">int</span>)  
A list of one or more permissible ciphers to use for SSL encryption, in
a format understood by OpenSSL. For example:
*DHE-RSA-AES256-SHA:AES128-SHA*

This exists as of PHP 5.3.7.

**`PDO::MYSQL_ATTR_SSL_KEY`** (<span class="type">int</span>)  
The file path to the SSL key.

This exists as of PHP 5.3.7.

**`PDO::MYSQL_ATTR_SSL_VERIFY_SERVER_CERT`** (<span class="type">int</span>)  
Provides a way to disable verification of the server SSL certificate.

This exists as of PHP 7.0.18 and PHP 7.1.4.

**`PDO::MYSQL_ATTR_MULTI_STATEMENTS`** (<span class="type">int</span>)  
Disables multi query execution in both <span
class="function">PDO::prepare</span> and <span
class="function">PDO::query</span> when set to **`FALSE`**.

Note, this constant can only be used in the `driver_options` array when
constructing a new database handle.

This exists as of PHP 5.5.21 and PHP 5.6.5.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                | Default           | Changeable       |
|---------------------------------------------------------------------|-------------------|------------------|
| <a href="/book/pdo.html#" class="link">pdo_mysql.default_socket</a> | "/tmp/mysql.sock" | PHP\_INI\_SYSTEM |
| <a href="/book/pdo.html#" class="link">pdo_mysql.debug</a>          | NULL              | PHP\_INI\_SYSTEM |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`pdo_mysql.default_socket` <span class="type">string</span>  
Sets a Unix domain socket. This value can either be set at compile time
if a domain socket is found at configure. This ini setting is Unix only.

`pdo_mysql.debug` <span class="type">bool</span>  
Enables debugging for PDO\_MYSQL. This setting is only available when
PDO\_MYSQL is compiled against mysqlnd and in PDO debug mode.

PDO\_MYSQL DSN
==============

Connecting to MySQL databases

### Description

The PDO\_MYSQL Data Source Name (DSN) is composed of the following
elements:

DSN prefix  
The DSN prefix is **`mysql:`**.

*host*  
The hostname on which the database server resides.

*port*  
The port number where the database server is listening.

*dbname*  
The name of the database.

*unix\_socket*  
The MySQL Unix socket (shouldn't be used with *host* or *port*).

*charset*  
The character set. See the
<a href="/set/mysqlinfo.html#Character%20sets" class="link">character set</a>
concepts documentation for more information.

Prior to PHP 5.3.6, this element was silently ignored. The same
behaviour can be partly replicated with the
**`PDO::MYSQL_ATTR_INIT_COMMAND`** driver option, as the following
example shows.

**Warning**
The method in the below example can only be used with character sets
that share the same lower 7 bit representation as ASCII, such as
ISO-8859-1 and UTF-8. Users using character sets that have different
representations (such as UTF-16 or Big5) *must* use the *charset* option
provided in PHP 5.3.6 and later versions.

**Example \#1 Setting the connection character set to UTF-8 prior to PHP
5.3.6**

``` php
<?php
$dsn = 'mysql:host=localhost;dbname=testdb';
$username = 'username';
$password = 'password';
$options = array(
    PDO::MYSQL_ATTR_INIT_COMMAND => 'SET NAMES utf8',
); 

$dbh = new PDO($dsn, $username, $password, $options);
?>
```

### Examples

**Example \#2 PDO\_MYSQL DSN examples**

The following example shows a PDO\_MYSQL DSN for connecting to MySQL
databases:

    mysql:host=localhost;dbname=testdb

More complete examples:

    mysql:host=localhost;port=3307;dbname=testdb
    mysql:unix_socket=/tmp/mysql.sock;dbname=testdb

### Notes

> **Note**: **Unix only:**  
>
> When the host name is set to *"localhost"*, then the connection to the
> server is made thru a domain socket. If PDO\_MYSQL is compiled against
> libmysqlclient then the location of the socket file is at
> libmysqlclient's compiled in location. If PDO\_MYSQL is compiled
> against mysqlnd a default socket can be set thru the
> <a href="/book/pdo.html#" class="link">pdo_mysql.default_socket</a>
> setting.

**Table of Contents**

-   [PDO\_MYSQL DSN](/book/pdo.html#PDO_MYSQL%20DSN) — Connecting to
    MySQL databases

Introduction
------------

PDO\_SQLSRV is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO) interface</a>
to enable access from PHP to MS SQL Server (starting with SQL Server
2005) and SQL Azure databases.

Installation
------------

The PDO\_SQLSRV extension is enabled by adding appropriate DLL file to
your PHP extension directory and the corresponding entry to the
`php.ini` file. The PDO\_SQLSRV download comes 8 driver files, four of
which are for PDO support. If you are running non-thread-safe PHP (PHP
5.3), use the php\_pdo\_sqlsrv\_53\_nts.dll file. (You should use a
non-thread-safe version if you are using IIS as your web server). If you
are running thread-safe PHP, use the php\_pdo\_sqlsrv\_53\_ts.dll file.
Similarly for PHP 5.4, use the php\_pdo\_sqlsrv\_54\_nts.dll or
php\_pdo\_sqlsrv\_54\_ts.dll depending on whether your PHP installation
is non-thread-safe or thread-safe.

The most recent version of the driver is available for download here:
<a href="http://msdn.microsoft.com/en-us/sqlserver/ff657782.aspx" class="link external">» SQLSRV download</a>.
If you need support for PHP 5.2 and/or PHP compiled with VC6, use the
2.0 release of the driver:
<a href="http://download.microsoft.com/download/C/D/B/CDB0A3BB-600E-42ED-8D5E-E4630C905371/SQLSRV20.EXE" class="link external">» SQLSRV 2.0 download</a>.
The driver sources are hosted in a
<a href="https://github.com/microsoft/msphpsql" class="link external">» public repository</a>.

For more information about system requirements, see
<a href="http://msdn.microsoft.com/en-us/library/cc296170.aspx" class="link external">» SQLSRV System Requirements</a>.

The PDO\_SQLSRV extension is only compatible with PHP running on
Windows. For Linux, see
<a href="/book/pdo.html#ODBC%20and%20DB2%20(PDO)" class="link">ODBC</a>
and
<a href="http://www.microsoft.com/download/en/details.aspx?id=28160" class="link external">» Microsoft's SQL Server ODBC Driver for Linux</a>.

Predefined Constants
--------------------

The constants below are defined by this driver, and will only be
available when the extension has been either compiled into PHP or
dynamically loaded at runtime. In addition, these driver-specific
constants should only be used if you are using this driver. Using
driver-specific attributes with another driver may result in unexpected
behaviour. <span class="function">PDO::getAttribute</span> may be used
to obtain the **`PDO::ATTR_DRIVER_NAME`** attribute to check the driver,
if your code can run against multiple drivers.

**`PDO::SQLSRV_TXN_READ_UNCOMMITTED`** (<span class="type">int</span>)  
<span class="simpara"> This constant is an acceptable value for the
SQLSRV DSN key TransactionIsolation. This constant sets the transaction
isolation level for the connection to Read Uncommitted. </span>

**`PDO::SQLSRV_TXN_READ_COMMITTED`** (<span class="type">int</span>)  
<span class="simpara"> This constant is an acceptable value for the
SQLSRV DSN key TransactionIsolation. This constant sets the transaction
isolation level for the connection to Read Committed. </span>

**`PDO::SQLSRV_TXN_REPEATABLE_READ`** (<span class="type">int</span>)  
<span class="simpara"> This constant is an acceptable value for the
SQLSRV DSN key TransactionIsolation. This constant sets the transaction
isolation level for the connection to Repeateable Read. </span>

**`PDO::SQLSRV_TXN_SNAPSHOT`** (<span class="type">int</span>)  
<span class="simpara"> This constant is an acceptable value for the
SQLSRV DSN key TransactionIsolation. This constant sets the transaction
isolation level for the connection to Snapshot. </span>

**`PDO::SQLSRV_TXN_SERIALIZABLE`** (<span class="type">int</span>)  
<span class="simpara"> This constant is an acceptable value for the
SQLSRV DSN key TransactionIsolation. This constant sets the transaction
isolation level for the connection to Serializable. </span>

**`PDO::SQLSRV_ENCODING_BINARY`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that data is sent/retrieved as a raw
byte stream to/from the server without performing encoding or
translation. This constant can be passed to PDOStatement::setAttribute,
PDO::prepare, PDOStatement::bindColumn, and PDOStatement::bindParam.
</span>

**`PDO::SQLSRV_ENCODING_SYSTEM`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that data is sent/retrieved to/from the
server as 8-bit characters as specified in the code page of the Windows
locale that is set on the system. Any multi-byte characters or
characters that do not map into this code page are substituted with a
single byte question mark (?) character. This constant can be passed to
PDOStatement::setAttribute, PDO::setAttribute, PDO::prepare,
PDOStatement::bindColumn, and PDOStatement::bindParam. </span>

**`PDO::SQLSRV_ENCODING_UTF8`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that data is sent/retrieved to/from the
server in UTF-8 encoding. This is the default encoding. This constant
can be passed to PDOStatement::setAttribute, PDO::setAttribute,
PDO::prepare, PDOStatement::bindColumn, and PDOStatement::bindParam.
</span>

**`PDO::SQLSRV_ENCODING_DEFAULT`** (<span class="type">int</span>)  
<span class="simpara"> Specifies that data is sent/retrieved to/from the
server according to PDO::SQLSRV\_ENCODING\_SYSTEM if specified during
connection. The connection's encoding is used if specified in a prepare
statement. This constant can be passed to PDOStatement::setAttribute,
PDO::setAttribute, PDO::prepare, PDOStatement::bindColumn, and
PDOStatement::bindParam. </span>

**`PDO::SQLSRV_ATTR_QUERY_TIMEOUT`** (<span class="type">int</span>)  
<span class="simpara"> A non-negative integer representing the timeout
period, in seconds. Zero (0) is the default and means no timeout. This
constant can be passed to PDOStatement::setAttribute, PDO::setAttribute,
and PDO::prepare. </span>

**`PDO::SQLSRV_ATTR_DIRECT_QUERY`** (<span class="type">int</span>)  
<span class="simpara"> Indicates that a query should be executed
directly, without being prepared. This constant can be passed to
PDO::setAttribute, and PDO::prepare. For more information, see
<a href="http://msdn.microsoft.com/en-us/library/ff754356.aspx" class="link external">» Direct and Prepared Statement Execution</a>.
</span>

PDO\_SQLSRV DSN
===============

Connecting to MS SQL Server and SQL Azure databases

### Description

The PDO\_SQLSRV Data Source Name (DSN) is composed of the following
elements:

DSN prefix  
The DSN prefix is **`sqlsrv:`**.

*APP*  
The application name used in tracing.

*ConnectionPooling*  
Specifies whether the connection is assigned from a connection pool (1
or **`TRUE`**) or not (0 or **`FALSE`**).

*Database*  
The name of the database.

*Encrypt*  
Specifies whether the communication with SQL Server is encrypted (1 or
**`TRUE`**) or unencrypted (0 or **`FALSE`**).

*Failover\_Partner*  
Specifies the server and instance of the database's mirror (if enabled
and configured) to use when the primary server is unavailable.

*LoginTimeout*  
Specifies the number of seconds to wait before failing the connection
attempt.

*MultipleActiveResultSets*  
Disables or explicitly enables support for multiple active Result sets
(MARS).

*QuotedId*  
Specifies whether to use SQL-92 rules for quoted identifiers (1 or
**`TRUE`**) or to use legacy Transact-SQL rules (0 or **`FALSE`**).

*Server*  
The name of the database server.

*TraceFile*  
Specifies the path for the file used for trace data.

*TraceOn*  
Specifies whether ODBC tracing is enabled (1 or **`TRUE`**) or disabled
(0 or **`FALSE`**) for the connection being established.

*TransactionIsolation*  
Specifies the transaction isolation level. The accepted values for this
option are PDO::SQLSRV\_TXN\_READ\_UNCOMMITTED,
PDO::SQLSRV\_TXN\_READ\_COMMITTED, PDO::SQLSRV\_TXN\_REPEATABLE\_READ,
PDO::SQLSRV\_TXN\_SNAPSHOT, and PDO::SQLSRV\_TXN\_SERIALIZABLE.

*TrustServerCertificate*  
Specifies whether the client should trust (1 or **`TRUE`**) or reject (0
or **`FALSE`**) a self-signed server certificate.

*WSID*  
Specifies the name of the computer for tracing.

### Examples

**Example \#1 PDO\_SQLSRV DSN examples**

The following example shows how to connecto to a specified MS SQL Server
database:

    $c = new PDO("sqlsrv:Server=localhost;Database=testdb", "UserName", "Password");

The following example shows how to connect to a MS SQL Server database
on a specified port:

    $c = new PDO("sqlsrv:Server=localhost,1521;Database=testdb", "UserName", "Password");

The following example shows how to connecto to a SQL Azure database with
server ID 12345abcde. Note that when you connect to SQL Azure with PDO,
your username will be UserName@12345abcde (UserName@ServerId).

    $c = new PDO("sqlsrv:Server=12345abcde.database.windows.net;Database=testdb", "UserName@12345abcde", "Password");

**Table of Contents**

-   [PDO\_SQLSRV DSN](/book/pdo.html#PDO_SQLSRV%20DSN) — Connecting to
    MS SQL Server and SQL Azure databases

Installation
------------

If the Oracle Database is on the same machine as PHP, the database
software already contains the necessary libraries. When PHP is on a
different machine, use the free
<a href="https://www.oracle.com/database/technologies/instant-client.html" class="link external">» Oracle Instant Client</a>
libraries. For details refer to the
<a href="/book/oci8.html#Requirements" class="link">OCI8 Requirements</a>
section.

Use **--with-pdo-oci\[=DIR\]** to install the PDO Oracle OCI extension,
where the optional *\[=DIR\]* is the Oracle Home directory. *\[=DIR\]*
defaults to the `$ORACLE_HOME` environment variable.

Use **--with-pdo-oci=instantclient,prefix,version** for an Oracle
Instant Client SDK, where prefix and version are configured.

    // Using $ORACLE_HOME
    $ ./configure --with-pdo-oci

    // Using OIC for Linux with 10.2.0.3 RPMs with a /usr prefix
    $ ./configure --with-pdo-oci=instantclient,/usr,10.2.0.3

Predefined Constants
--------------------

The constants below are defined by this driver, and will only be
available when the extension has been either compiled into PHP or
dynamically loaded at runtime. In addition, these driver-specific
constants should only be used if you are using this driver. Using
driver-specific attributes with another driver may result in unexpected
behaviour. <span class="function">PDO::getAttribute</span> may be used
to obtain the **`PDO::ATTR_DRIVER_NAME`** attribute to check the driver,
if your code can run against multiple drivers.

**`PDO::OCI_ATTR_ACTION`** (<span class="type">int</span>)  
Provides a way to specify the action on the database session.

This exists as of PHP 7.2.16 and 7.3.3

**`PDO::OCI_ATTR_CLIENT_INFO`** (<span class="type">int</span>)  
Provides a way to specify the client info on the database session.

This exists as of PHP 7.2.16 and 7.3.3

**`PDO::OCI_ATTR_CLIENT_IDENTIFIER`** (<span class="type">int</span>)  
Provides a way to specify the client identifier on the database session.

This exists as of PHP 7.2.16 and 7.3.3

**`PDO::OCI_ATTR_MODULE`** (<span class="type">int</span>)  
Provides a way to specify the module on the database session.

This exists as of PHP 7.2.16 and 7.3.3

PDO\_OCI DSN
============

Connecting to Oracle databases

### Description

The PDO\_OCI Data Source Name (DSN) is composed of the following
elements:

DSN prefix  
The DSN prefix is **`oci:`**.

*dbname* (Oracle Instant Client)  
The URI for the Oracle Instant Client connection takes the form of
`dbname=//hostname:port-number/database`. If you are connecting to a
database defined in `tnsnames.ora`, use only the name of the database:
`dbname=database`.

*charset*  
The client-side character set for the current environment handle.

### Examples

**Example \#1 PDO\_OCI DSN examples**

The following examples show a PDO\_OCI DSN for connecting to Oracle
databases:

    // Connect to a database defined in tnsnames.ora
    oci:dbname=mydb

    // Connect using the Oracle Instant Client
    oci:dbname=//localhost:1521/mydb

**Table of Contents**

-   [PDO\_OCI DSN](/book/pdo.html#PDO_OCI%20DSN) — Connecting to Oracle
    databases

Introduction
------------

PDO\_ODBC is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO) interface</a>
to enable access from PHP to databases through ODBC drivers or through
the IBM DB2 Call Level Interface (DB2 CLI) library. PDO\_ODBC currently
supports three different "flavours" of database drivers:

ibm-db2  
Supports access to IBM DB2 Universal Database, Cloudscape, and Apache
Derby servers through the free DB2 express-C client.

unixODBC  
Supports access to database servers through the unixODBC driver manager
and the database's own ODBC drivers.

generic  
Offers a compile option for ODBC driver managers that are not explicitly
supported by PDO\_ODBC.

On Windows, `php_pdo_odbc.dll` has to be enabled as extension in
`php.ini`. It is linked against the Windows ODBC Driver Manager so that
PHP can connect to any database cataloged as a System DSN, and is the
recommended driver for connecting to Microsoft SQL Server databases.

Installation
------------

**PDO\_ODBC on UNIX systems**

1.  As of PHP 5.1, PDO\_ODBC is included in the PHP source. You can
    compile the PDO\_ODBC extension as either a static or shared module
    using the following **configure** commands.

    ibm\_db2  
        ./configure --with-pdo-odbc=ibm-db2,/opt/IBM/db2/V8.1/

    To build PDO\_ODBC with the ibm-db2 flavour, you have to have
    previously installed the DB2 application development headers on the
    same machine on which you are compiling PDO\_ODBC. The DB2
    application development headers are an installable option in the DB2
    servers, and are also available as part of the DB2 Application
    Development Client freely available for download from the IBM
    developerWorks
    <a href="https://www.ibm.com/developerworks/downloads/im/db2express/index.html" class="link external">» website</a>.

    If you do not supply a location for the DB2 libraries and headers to
    the **configure** command, PDO\_ODBC defaults to
    `/home/db2inst1/sqllib`.

    unixODBC  
        ./configure --with-pdo-odbc=unixODBC,/usr/local

    If you do not supply a location for the unixODBC libraries and
    headers to the **configure** command, PDO\_ODBC defaults to
    `/usr/local`.

    generic  
        ./configure --with-pdo-odbc=generic,/usr/local,libname,ldflags,cflags

Predefined Constants
--------------------

The constants below are defined by this driver, and will only be
available when the extension has been either compiled into PHP or
dynamically loaded at runtime. In addition, these driver-specific
constants should only be used if you are using this driver. Using
driver-specific attributes with another driver may result in unexpected
behaviour. <span class="function">PDO::getAttribute</span> may be used
to obtain the **`PDO::ATTR_DRIVER_NAME`** attribute to check the driver,
if your code can run against multiple drivers.

**`PDO::ODBC_ATTR_USE_CURSOR_LIBRARY`** (<span class="type">int</span>)  
This option controls whether the ODBC cursor library is used. The ODBC
cursor library supports some advanced ODBC features (e.g. block
scrollable cursors), which may not be implemented by the driver. The
following values are supported:

-   **`PDO::ODBC_SQL_USE_IF_NEEDED`** (the default): use the ODBC cursor
    library when needed.

-   **`PDO::ODBC_SQL_USE_DRIVER`**: never use the ODBC cursor library.

-   **`PDO::ODBC_SQL_USE_ODBC`**: always use the ODBC cursor library.

**`PDO::ODBC_ATTR_ASSUME_UTF8`** (<span class="type">bool</span>)  
Windows only. If **`TRUE`**, UTF-16 encoded character data (*CHAR*,
*VARCHAR* and *LONGVARCHAR*) is converted to UTF-8 when reading from or
writing data to the database. If **`FALSE`** (the default), no character
encoding conversion is done.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                   | Default  | Changeable       | Changelog                                                                                       |
|------------------------------------------------------------------------|----------|------------------|-------------------------------------------------------------------------------------------------|
| <a href="/book/pdo.html#" class="link">pdo_odbc.connection_pooling</a> | "strict" | PHP\_INI\_ALL    | Available since PHP 5.1.0.                                                                      |
| <a href="/book/pdo.html#" class="link">pdo_odbc.db2_instance_name</a>  | NULL     | PHP\_INI\_SYSTEM | Available since PHP 5.1.1. This deprecated feature *will* certainly be *removed* in the future. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`pdo_odbc.connection_pooling` <span class="type">string</span>  
Whether to pool ODBC connections. Can be one of *"strict"*, *"relaxed"*
or *"off"* (equals to *""*). The parameter describes how strict the
connection manager should be when matching connection parameters to
existing pooled connections. **`strict`** is the recommend default, and
will result in the use of cached connections only when all the
connection parameters match exactly. **`relaxed`** will result in the
use of cached connections when similar connection parameters are used.
This can result in increased use of the cache, at the risk of bleeding
connection information between (for example) virtual hosts.

This setting can only be changed from the `php.ini` file, and affects
the entire process; any other modules loaded into the process that use
the same ODBC libraries will be affected too, including the
<a href="/book/uodbc.html#ODBC%20Functions" class="link">Unified ODBC extension</a>.

**Warning**
**`relaxed`** matching should not be used on a shared server, for
security reasons.

**Tip**
Leave this setting at the default **`strict`** setting unless you have
good reason to change it.

`pdo_odbc.db2_instance_name` <span class="type">string</span>  
If you compile PDO\_ODBC using the *db2* flavour, this setting sets the
value of the DB2INSTANCE environment variable on Linux and UNIX
operating systems to the specified name of the DB2 instance. This
enables PDO\_ODBC to resolve the location of the DB2 libraries and make
cataloged connections to DB2 databases.

This setting can only be changed from the `php.ini` file, and affects
the entire process; any other modules loaded into the process that use
the same ODBC libraries will be affected too, including the
<a href="/book/uodbc.html#ODBC%20Functions" class="link">Unified ODBC extension</a>.

This setting has no effect on Windows.

PDO\_ODBC DSN
=============

Connecting to ODBC or DB2 databases

### Description

The PDO\_ODBC Data Source Name (DSN) is composed of the following
elements:

DSN prefix  
The DSN prefix is **`odbc:`**. If you are connecting to a database
cataloged in the ODBC driver manager or the DB2 catalog, you can append
the cataloged name of the database to the DSN.

DSN  
The name of the database as cataloged in the ODBC driver manager or the
DB2 catalog. Alternately, you can provide a complete ODBC connection
string to connect to a database as described at
<a href="http://www.connectionstrings.com/" class="link external">» http://www.connectionstrings.com/</a>.

*UID*  
The name of the user for the connection. If you specify the user name in
the DSN, PDO ignores the value of the user name argument in the PDO
constructor.

*PWD*  
The password of the user for the connection. If you specify the password
in the DSN, PDO ignores the value of the password argument in the PDO
constructor.

### Examples

**Example \#1 PDO\_ODBC DSN example (ODBC driver manager)**

The following example shows a PDO\_ODBC DSN for connecting to an ODBC
database cataloged as testdb in the ODBC driver manager:

    odbc:testdb

**Example \#2 PDO\_ODBC DSN example (IBM DB2 uncataloged connection)**

The following example shows a PDO\_ODBC DSN for connecting to an IBM DB2
database named **`SAMPLE`** using the full ODBC DSN syntax:

    odbc:DRIVER={IBM DB2 ODBC DRIVER};HOSTNAME=localhost;PORT=50000;DATABASE=SAMPLE;PROTOCOL=TCPIP;UID=db2inst1;PWD=ibmdb2;

**Example \#3 PDO\_ODBC DSN example (Microsoft Access uncataloged
connection)**

The following example shows a PDO\_ODBC DSN for connecting to a
Microsoft Access database stored at **`C:\db.mdb`** using the full ODBC
DSN syntax:

    odbc:Driver={Microsoft Access Driver (*.mdb)};Dbq=C:\\db.mdb;Uid=Admin

**Table of Contents**

-   [PDO\_ODBC DSN](/book/pdo.html#PDO_ODBC%20DSN) — Connecting to ODBC
    or DB2 databases

Introduction
------------

PDO\_PGSQL is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO) interface</a>
to enable access from PHP to PostgreSQL databases.

Resource Types
--------------

This extension defines a stream resource returned by <span
class="function">PDO::pgsqlLOBOpen</span>.

Installation
------------

Use **--with-pdo-pgsql\[=DIR\]** to install the PDO PostgreSQL
extension, where the optional *\[=DIR\]* is the PostgreSQL base install
directory, or the path to *pg\_config*.

    $ ./configure --with-pdo-pgsql

PDO\_PGSQL DSN
==============

Connecting to PostgreSQL databases

### Description

The PDO\_PGSQL Data Source Name (DSN) is composed of the following
elements, delimited by spaces or semicolons:

DSN prefix  
The DSN prefix is **`pgsql:`**.

*host*  
The hostname on which the database server resides.

*port*  
The port on which the database server is running.

*dbname*  
The name of the database.

*user*  
The name of the user for the connection. If you specify the user name in
the DSN, PDO ignores the value of the user name argument in the PDO
constructor.

*password*  
The password of the user for the connection. If you specify the password
in the DSN, PDO ignores the value of the password argument in the PDO
constructor.

> **Note**:
>
> The *bytea* fields are returned as streams.

### Examples

**Example \#1 PDO\_PGSQL DSN examples**

The following example shows a PDO\_PGSQL DSN for connecting to a
PostgreSQL database:

    pgsql:host=localhost;port=5432;dbname=testdb;user=bruce;password=mypass

PDO::pgsqlCopyFromArray
=======================

Copy data from PHP array into table

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::pgsqlCopyFromArray</span> ( <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> , <span class="methodparam"><span
class="type">array</span> `$rows`</span> \[, <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = '\\t'</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$null_as`<span
class="initializer"> = "\\\\\\\\N"</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$fields`</span>
\]\]\] )

Copies data from `rows` array to table `table_name` using `delimiter` as
fields delimiter and `fields` list

### Parameters

`table_name`  
String containing table name

`rows`  
Array of strings with fields separated by `delimiter`

`delimiter`  
Delimiter used in `rows` array

`null_as`  
How to interpret null values

`fields`  
List of fields to insert

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** on failure.

PDO::pgsqlCopyFromFile
======================

Copy data from file into table

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::pgsqlCopyFromFile</span> ( <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> , <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = '\\t'</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$null_as`<span
class="initializer"> = "\\\\\\\\N"</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$fields`</span>
\]\]\] )

Copies data from file specified by `filename` into table `table_name`
using `delimiter` as fields delimiter and `fields` list

### Parameters

`table_name`  
String containing table name

`filename`  
Filename containing data to import

`delimiter`  
Delimiter used in file specified by `filename`

`null_as`  
How to interpret null values

`fields`  
List of fields to insert

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** on failure.

PDO::pgsqlCopyToArray
=====================

Copy data from database table into PHP array

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">PDO::pgsqlCopyToArray</span> ( <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$delimiter`<span class="initializer"> =
'\\t'</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$null_as`<span class="initializer"> =
"\\\\\\\\N"</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$fields`</span> \]\]\] )

Copies data from `table` into array using `delimiter` as fields
delimiter and `fields` list

### Parameters

`table_name`  
String containing table name

`delimiter`  
Delimiter used in rows

`null_as`  
How to interpret null values

`fields`  
List of fields to export

### Return Values

Returns an array of rows, or **`FALSE`** on failure.

PDO::pgsqlCopyToFile
====================

Copy data from table into file

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::pgsqlCopyToFile</span> ( <span
class="methodparam"><span class="type">string</span>
`$table_name`</span> , <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = '\\t'</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$null_as`<span
class="initializer"> = "\\\\\\\\N"</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$fields`</span>
\]\]\] )

Copies data from table into file specified by `filename` using
`delimiter` as fields delimiter and `fields` list

### Parameters

`table_name`  
String containing table name

`filename`  
Filename to export data

`delimiter`  
Delimiter used in file specified by `filename`

`null_as`  
How to interpret null values

`fields`  
List of fields to insert

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** on failure.

PDO::pgsqlGetNotify
===================

Get asynchronous notification

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">PDO::pgsqlGetNotify</span> (\[ <span
class="methodparam"><span class="type">int</span> `$result_type`<span
class="initializer"> = **`PDO::FETCH_USE_DEFAULT`**</span></span> \[,
<span class="methodparam"><span class="type">int</span>
`$ms_timeout`<span class="initializer"> = 0</span></span> \]\] )

Returns a result set representing a pending asynchronous notification.

### Parameters

`result_type`  
The format the result set should be returned as, represented as a
<a href="/book/pdo.html#PDOStatement::fetch" class="link"><strong><code>PDO::FETCH_*</code></strong></a>
constant.

`ms_timeout`  
The length of time to wait for a response, in milliseconds.

### Return Values

If one or more notifications is pending, returns a single row, with
fields *message* and *pid*, otherwise returns **`FALSE`**.

PDO::pgsqlGetPid
================

Get the server PID

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">PDO::pgsqlGetPid</span> ( <span
class="methodparam">void</span> )

Returns the server's PID.

### Return Values

The server's PID.

PDO::pgsqlLOBCreate
===================

Creates a new large object

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">PDO::pgsqlLOBCreate</span> ( <span
class="methodparam">void</span> )

<span class="function">PDO::pgsqlLOBCreate</span> creates a large object
and returns the OID of that object. You may then open a stream on the
object using <span class="function">PDO::pgsqlLOBOpen</span> to read or
write data to it. The OID can be stored in columns of type OID and be
used to reference the large object, without causing the row to grow
arbitrarily large. The large object will continue to live in the
database until it is removed by calling <span
class="function">PDO::pgsqlLOBUnlink</span>.

Large objects can be up to 2GB in size, but are cumbersome to use; you
need to ensure that <span class="function">PDO::pgsqlLOBUnlink</span> is
called prior to deleting the last row that references its OID from your
database. In addition, large objects have no access controls. As an
alternative, try the bytea column type; recent versions of PostgreSQL
allow bytea columns of up to 1GB in size and transparently manage the
storage for optimal row size.

> **Note**: <span class="simpara"> This function must be called within a
> transaction. </span>

### Parameters

<span class="function">PDO::pgsqlLOBCreate</span> takes no parameters.

### Return Values

Returns the OID of the newly created large object on success, or
**`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">PDO::pgsqlLOBCreate</span>
example**

This example creates a new large object and copies the contents of a
file into it. The OID is then stored into a table.

``` php
<?php
$db = new PDO('pgsql:dbname=test host=localhost', $user, $pass);
$db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
$db->beginTransaction();
$oid = $db->pgsqlLOBCreate();
$stream = $db->pgsqlLOBOpen($oid, 'w');
$local = fopen($filename, 'rb');
stream_copy_to_stream($local, $stream);
$local = null;
$stream = null;
$stmt = $db->prepare("INSERT INTO BLOBS (ident, oid) VALUES (?, ?)");
$stmt->execute(array($some_id, $oid));
$db->commit();
?>
```

### See Also

-   <span class="function">PDO::pgsqlLOBOpen</span>
-   <span class="function">PDO::pgsqlLOBUnlink</span>
-   <span class="function">pg\_lo\_create</span>

PDO::pgsqlLOBOpen
=================

Opens an existing large object stream

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">resource</span><span class="type">false</span></span> <span
class="methodname">PDO::pgsqlLOBOpen</span> ( <span
class="methodparam"><span class="type">string</span> `$oid`</span> \[,
<span class="methodparam"><span class="type">string</span> `$mode`<span
class="initializer"> = "rb"</span></span> \] )

<span class="function">PDO::pgsqlLOBOpen</span> opens a stream to access
the data referenced by `oid`. If `mode` is *r*, the stream is opened for
reading, if `mode` is *w*, then the stream will be opened for writing.
You can use all the usual filesystem functions, such as <span
class="function">fread</span>, <span class="function">fwrite</span> and
<span class="function">fgets</span> to manipulate the contents of the
stream.

> **Note**: <span class="simpara"> This function, and all manipulations
> of the large object, must be called and carried out within a
> transaction. </span>

### Parameters

`oid`  
A large object identifier.

`mode`  
If mode is *r*, open the stream for reading. If mode is *w*, open the
stream for writing.

### Return Values

Returns a stream resource on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">PDO::pgsqlLOBOpen</span>
example**

Following on from the <span class="function">PDO::pgsqlLOBCreate</span>
example, this code snippet retrieves the large object from the database
and outputs it to the browser.

``` php
<?php
$db = new PDO('pgsql:dbname=test host=localhost', $user, $pass);
$db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
$db->beginTransaction();
$stmt = $db->prepare("select oid from BLOBS where ident = ?");
$stmt->execute(array($some_id));
$stmt->bindColumn('oid', $oid, PDO::PARAM_STR);
$stmt->fetch(PDO::FETCH_BOUND);
$stream = $db->pgsqlLOBOpen($oid, 'r');
header("Content-type: application/octet-stream");
fpassthru($stream);
?>
```

### See Also

-   <span class="function">PDO::pgsqlLOBCreate</span>
-   <span class="function">PDO::pgsqlLOBUnlink</span>
-   <span class="function">pg\_lo\_open</span>

PDO::pgsqlLOBUnlink
===================

Deletes the large object

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::pgsqlLOBUnlink</span> ( <span
class="methodparam"><span class="type">string</span> `$oid`</span> )

Deletes a large object from the database identified by OID.

> **Note**: <span class="simpara"> This function must be called within a
> transaction. </span>

### Parameters

`oid`  
A large object identifier

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">PDO::pgsqlLOBUnlink</span>
example**

This example unlinks a large object from the database prior to deleting
the row that references it from the blobs table we've been using in our
<span class="function">PDO::pgsqlLOBCreate</span> and <span
class="function">PDO::pgsqlLOBOpen</span> examples.

``` php
<?php
$db = new PDO('pgsql:dbname=test host=localhost', $user, $pass);
$db->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
$db->beginTransaction();
$db->pgsqlLOBUnlink($oid);
$stmt = $db->prepare("DELETE FROM BLOBS where ident = ?");
$stmt->execute(array($some_id));
$db->commit();
?>
```

### See Also

-   <span class="function">PDO::pgsqlLOBOpen</span>
-   <span class="function">PDO::pgsqlLOBCreate</span>

**Table of Contents**

-   [PDO\_PGSQL DSN](/book/pdo.html#PDO_PGSQL%20DSN) — Connecting to
    PostgreSQL databases
-   [PDO::pgsqlCopyFromArray](/book/pdo.html#PDO::pgsqlCopyFromArray) —
    Copy data from PHP array into table
-   [PDO::pgsqlCopyFromFile](/book/pdo.html#PDO::pgsqlCopyFromFile) —
    Copy data from file into table
-   [PDO::pgsqlCopyToArray](/book/pdo.html#PDO::pgsqlCopyToArray) — Copy
    data from database table into PHP array
-   [PDO::pgsqlCopyToFile](/book/pdo.html#PDO::pgsqlCopyToFile) — Copy
    data from table into file
-   [PDO::pgsqlGetNotify](/book/pdo.html#PDO::pgsqlGetNotify) — Get
    asynchronous notification
-   [PDO::pgsqlGetPid](/book/pdo.html#PDO::pgsqlGetPid) — Get the server
    PID
-   [PDO::pgsqlLOBCreate](/book/pdo.html#PDO::pgsqlLOBCreate) — Creates
    a new large object
-   [PDO::pgsqlLOBOpen](/book/pdo.html#PDO::pgsqlLOBOpen) — Opens an
    existing large object stream
-   [PDO::pgsqlLOBUnlink](/book/pdo.html#PDO::pgsqlLOBUnlink) — Deletes
    the large object

Introduction
------------

PDO\_SQLITE is a driver that implements the
<a href="/book/pdo.html#Introduction" class="link">PHP Data Objects (PDO) interface</a>
to enable access to SQLite 3 databases.

> **Note**:
>
> PDO\_SQLITE allows using strings apart from streams together with
> **`PDO::PARAM_LOB`**.

Installation
------------

The PDO\_SQLITE PDO driver is enabled by default. To disable,
**--without-pdo-sqlite\[=DIR\]** may be used, where the optional
*\[=DIR\]* is the sqlite base install directory. As of PHP 7.4.0
<a href="http://sqlite.org/" class="link external">» libsqlite</a> ≥
3.5.0 is required. Formerly, the bundled libsqlite could have been used
instead, and was the default, if *\[=DIR\]* has been omitted.

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

PDO\_SQLITE DSN
===============

Connecting to SQLite databases

### Description

The PDO\_SQLITE Data Source Name (DSN) is composed of the following
elements:

DSN prefix (SQLite 3)  
The DSN prefix is **`sqlite:`**.

-   To access a database on disk, the absolute path has to be appended
    to the DSN prefix.

-   To create a database in memory, *:memory:* has to be appended to the
    DSN prefix.

-   If the DSN consists of the DSN prefix only, a temporary database is
    used, which is deleted when the connection is closed.

### Examples

**Example \#1 PDO\_SQLITE DSN examples**

The following examples show PDO\_SQLITE DSN for connecting to SQLite
databases:

    sqlite:/opt/databases/mydb.sq3
    sqlite::memory:
    sqlite:

PDO::sqliteCreateAggregate
==========================

Registers an aggregating User Defined Function for use in SQL statements

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::sqliteCreateAggregate</span> ( <span
class="methodparam"><span class="type">string</span>
`$function_name`</span> , <span class="methodparam"><span
class="type">callable</span> `$step_func`</span> , <span
class="methodparam"><span class="type">callable</span>
`$finalize_func`</span> \[, <span class="methodparam"><span
class="type">int</span> `$num_args`</span> \] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

This method is similar to
<a href="/book/pdo.html#PDO::sqliteCreateFunction" class="xref"></a>
except that it registers functions that can be used to calculate a
result aggregated across all the rows of a query.

The key difference between this method and
<a href="/book/pdo.html#PDO::sqliteCreateFunction" class="xref"></a> is
that two functions are required to manage the aggregate.

### Parameters

`function_name`  
The name of the function used in SQL statements.

`step_func`  
Callback function called for each row of the result set. Your PHP
function should accumulate the result and store it in the aggregation
context.

This function need to be defined as:

<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">step</span></span> ( <span class="methodparam"><span
class="type">mixed</span> `$context`</span> , <span
class="methodparam"><span class="type">int</span> `$rownumber`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> , <span class="methodparam"><span
class="type">mixed</span> `$values`</span> )

`context`  
**`NULL`** for the first row; on subsequent rows it will have the value
that was previously returned from the step function; you should use this
to maintain the aggregate state.

`rownumber`  
The current row number.

`value`  
The first argument passed to the aggregate.

`values`  
Further arguments passed to the aggregate.

The return value of this function will be used as the `context` argument
in the next call of the step or finalize functions.

`finalize_func`  
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
class="methodparam"><span class="type">int</span> `$rowcount`</span> )

`context`  
Holds the return value from the very last call to the step function.

`rowcount`  
Holds the number of rows over which the aggregate was performed.

The return value of this function will be used as the return value for
the aggregate.

`num_args`  
Hint to the SQLite parser if the callback function accepts a
predetermined number of arguments.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

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
$db = new PDO('sqlite::memory:');
$db->exec("CREATE TABLE strings(a)");
$insert = $db->prepare('INSERT INTO strings VALUES (?)');
foreach ($data as $str) {
    $insert->execute(array($str));
}
$insert = null;

function max_len_step($context, $rownumber, $string) 
{
    if (strlen($string) > $context) {
        $context = strlen($string);
    }
    return $context;
}

function max_len_finalize($context, $rowcount) 
{
    return $context === null ? 0 : $context;
}

$db->sqliteCreateAggregate('max_len', 'max_len_step', 'max_len_finalize');

var_dump($db->query('SELECT max_len(a) from strings')->fetchAll());

?>
```

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

You can use
<a href="/book/pdo.html#PDO::sqliteCreateFunction" class="xref"></a> and
<a href="/book/pdo.html#PDO::sqliteCreateAggregate" class="xref"></a> to
override SQLite native SQL functions.

### See Also

-   <a href="/book/pdo.html#PDO::sqliteCreateFunction" class="xref"></a>
-   <span class="function">sqlite\_create\_function</span>
-   <span class="function">sqlite\_create\_aggregate</span>

PDO::sqliteCreateCollation
==========================

Registers a User Defined Function for use as a collating function in SQL
statements

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::sqliteCreateCollation</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`name`  
Name of the SQL collating function to be created or redefined.

`callback`  
The name of a PHP function or user-defined function to apply as a
callback, defining the behavior of the collation. It should accept two
strings and return as strcmp() does, i.e. it should return -1, 1, or 0
if the first string sorts before, sorts after, or is equal to the
second.

This function need to be defined as:

<span class="type">int</span> <span class="methodname"><span
class="replaceable">collation</span></span> ( <span
class="methodparam"><span class="type">string</span> `$string1`</span> ,
<span class="methodparam"><span class="type">string</span>
`$string2`</span> )

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">PDO::sqliteCreateCollation</span>
example**

``` php
<?php
$db = new PDO('sqlite::memory:');
$db->exec("CREATE TABLE test (col1 string)");
$db->exec("INSERT INTO test VALUES ('a1')");
$db->exec("INSERT INTO test VALUES ('a10')");
$db->exec("INSERT INTO test VALUES ('a2')");

$db->sqliteCreateCollation('NATURAL_CMP', 'strnatcmp');
foreach ($db->query("SELECT col1 FROM test ORDER BY col1") as $row) {
  echo $row['col1'] . "\n";
}
echo "\n";
foreach ($db->query("SELECT col1 FROM test ORDER BY col1 COLLATE NATURAL_CMP") as $row) {
  echo $row['col1'] . "\n";
}
?>
```

The above example will output:

    a1
    a10
    a2

    a1
    a2
    a10

PDO::sqliteCreateFunction
=========================

Registers a User Defined Function for use in SQL statements

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">PDO::sqliteCreateFunction</span> ( <span
class="methodparam"><span class="type">string</span>
`$function_name`</span> , <span class="methodparam"><span
class="type">callable</span> `$callback`</span> \[, <span
class="methodparam"><span class="type">int</span> `$num_args`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \]\] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

This method allows you to register a PHP function with SQLite as an UDF
(User Defined Function), so that it can be called from within your SQL
statements.

The UDF can be used in any SQL statement that can call functions, such
as SELECT and UPDATE statements and also in triggers.

### Parameters

`function_name`  
The name of the function used in SQL statements.

`callback`  
Callback function to handle the defined SQL function.

> **Note**: <span class="simpara"> Callback functions should return a
> type understood by SQLite (i.e.
> <a href="/language/types/intro.html" class="link">scalar type</a>).
> </span>

This function need to be defined as:

<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$values`</span> )

`value`  
The first argument passed to the SQL function.

`values`  
Further arguments passed to the SQL function.

`num_args`  
The number of arguments that the SQL function takes. If this parameter
is *-1*, then the SQL function may take any number of arguments.

`flags`  
A bitwise conjunction of flags. Currently, only
**`PDO::SQLITE_DETERMINISTIC`** is supported, which specifies that the
function always returns the same result given the same inputs within a
single SQL statement.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                           |
|---------|---------------------------------------|
| 7.1.4   | The `flags` parameter has been added. |

### Examples

**Example \#1 <span class="function">PDO::sqliteCreateFunction</span>
example**

``` php
<?php
function md5_and_reverse($string) 
{
    return strrev(md5($string));
}

$db = new PDO('sqlite:sqlitedb');
$db->sqliteCreateFunction('md5rev', 'md5_and_reverse', 1);
$rows = $db->query('SELECT md5rev(filename) FROM files')->fetchAll();
?>
```

In this example, we have a function that calculates the md5 sum of a
string, and then reverses it. When the SQL statement executes, it
returns the value of the filename transformed by our function. The data
returned in *$rows* contains the processed result.

The beauty of this technique is that you do not need to process the
result using a
<a href="/control-structures/foreach.html" class="link">foreach</a> loop
after you have queried for the data.

**Tip**

You can use
<a href="/book/pdo.html#PDO::sqliteCreateFunction" class="xref"></a> and
<a href="/book/pdo.html#PDO::sqliteCreateAggregate" class="xref"></a> to
override SQLite native SQL functions.

### See Also

-   <a href="/book/pdo.html#PDO::sqliteCreateAggregate" class="xref"></a>
-   <span class="function">sqlite\_create\_function</span>
-   <span class="function">sqlite\_create\_aggregate</span>

**Table of Contents**

-   [PDO\_SQLITE DSN](/book/pdo.html#PDO_SQLITE%20DSN) — Connecting to
    SQLite databases
-   [PDO::sqliteCreateAggregate](/book/pdo.html#PDO::sqliteCreateAggregate)
    — Registers an aggregating User Defined Function for use in SQL
    statements
-   [PDO::sqliteCreateCollation](/book/pdo.html#PDO::sqliteCreateCollation)
    — Registers a User Defined Function for use as a collating function
    in SQL statements
-   [PDO::sqliteCreateFunction](/book/pdo.html#PDO::sqliteCreateFunction)
    — Registers a User Defined Function for use in SQL statements

dbx
===

**Table of Contents**

-   [Introduction](/book/dbx.html#Introduction)
-   [Installing/Configuring](/book/dbx.html#Installing/Configuring)
    -   [Requirements](/book/dbx.html#Requirements)
    -   [Installation](/book/dbx.html#Installation)
    -   [Runtime Configuration](/book/dbx.html#Runtime%20Configuration)
    -   [Resource Types](/book/dbx.html#Resource%20Types)
-   [Predefined Constants](/book/dbx.html#Predefined%20Constants)
-   [dbx Functions](/book/dbx.html#dbx%20Functions)
    -   [dbx\_close](/book/dbx.html#dbx_close) — Close an open
        connection/database
    -   [dbx\_compare](/book/dbx.html#dbx_compare) — Compare two rows
        for sorting purposes
    -   [dbx\_connect](/book/dbx.html#dbx_connect) — Open a
        connection/database
    -   [dbx\_error](/book/dbx.html#dbx_error) — Report the error
        message of the latest function call in the module
    -   [dbx\_escape\_string](/book/dbx.html#dbx_escape_string) — Escape
        a string so it can safely be used in an sql-statement
    -   [dbx\_fetch\_row](/book/dbx.html#dbx_fetch_row) — Fetches rows
        from a query-result that had the DBX\_RESULT\_UNBUFFERED flag
        set
    -   [dbx\_query](/book/dbx.html#dbx_query) — Send a query and fetch
        all results (if any)
    -   [dbx\_sort](/book/dbx.html#dbx_sort) — Sort a result from a
        dbx\_query by a custom sort function

The dbx module is a database abstraction layer (db 'X', where 'X' is a
supported database). The dbx functions allow you to access all supported
databases using a single calling convention. The dbx-functions
themselves do not interface directly to the databases, but interface to
the modules that are used to support these databases.

> **Note**:
>
> This extension has been moved to the
> <a href="https://pecl.php.net/" class="link external">» PECL</a>
> repository and is no longer bundled with PHP as of PHP 5.1.0.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/dbx.html#Requirements)
-   [Installation](/book/dbx.html#Installation)
-   [Runtime Configuration](/book/dbx.html#Runtime%20Configuration)
-   [Resource Types](/book/dbx.html#Resource%20Types)

Requirements
------------

To be able to use a database with the dbx-module, the module must be
either linked or loaded into PHP, and the database module must be
supported by the dbx-module. Currently, the following databases are
supported, but others will follow:

-   <span class="simpara">
    <a href="/book/fbsql.html#FrontBase%20Functions" class="link">FrontBase</a>
    </span>
-   <span class="simpara">
    <a href="/set/mysqlinfo.html#MySQL%20Functions" class="link">MySQL</a>
    </span>
-   <span class="simpara">
    <a href="/book/uodbc.html#ODBC%20Functions" class="link">ODBC</a>
    </span>
-   <span class="simpara">
    <a href="/book/pgsql.html#PostgreSQL%20Functions" class="link">PostgreSQL</a>
    </span>
-   <span class="simpara">
    <a href="/book/oci8.html#OCI8%20Functions" class="link">Oracle (oci8)</a>
    </span>
-   <span class="simpara"> SQLite </span>

Documentation for adding additional database support to dbx can be found
at
<a href="http://www.guidance.nl/php/dbx/doc/" class="link external">» http://www.guidance.nl/php/dbx/doc/</a>.

Installation
------------

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 5.1.0

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/dbx" class="link external">» https://pecl.php.net/package/dbx</a>.

In order to have these functions available, you must compile PHP with
dbx support by using the **--enable-dbx** option and all options for the
databases that will be used, e.g. for MySQL you must also specify
**--with-mysql=\[DIR\]**. To get other supported databases to work with
the dbx-module refer to their specific documentation.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                         | Default     | Changeable       | Changelog             |
|--------------------------------------------------------------|-------------|------------------|-----------------------|
| <a href="/book/dbx.html#" class="link">dbx.colnames_case</a> | "unchanged" | PHP\_INI\_SYSTEM | Removed in PHP 5.1.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`dbx.colnames_case` <span class="type">string</span>  
Columns names can be returned "unchanged" or converted to "uppercase" or
"lowercase". This directive can be overridden with a flag to <span
class="function">dbx\_query</span>.

Resource Types
--------------

There are two resource types used in the dbx module. The first one is
the link-<span class="type">object</span> for a database connection, the
second a result-<span class="type">object</span> which holds the result
of a query.

Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`DBX_MYSQL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_ODBC`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_PGSQL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_MSSQL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_FBSQL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_OCI8`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_SYBASECT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_SQLITE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_PERSISTENT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_RESULT_INFO`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_RESULT_INDEX`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_RESULT_ASSOC`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_RESULT_UNBUFFERED`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_COLNAMES_UNCHANGED`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_COLNAMES_UPPERCASE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_COLNAMES_LOWERCASE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_CMP_NATIVE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_CMP_TEXT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_CMP_NUMBER`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_CMP_ASC`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`DBX_CMP_DESC`** (<span class="type">int</span>)  
<span class="simpara"> </span>

dbx\_close
==========

Close an open connection/database

### Description

<span class="type">int</span> <span class="methodname">dbx\_close</span>
( <span class="methodparam"><span class="type">object</span>
`$link_identifier`</span> )

### Parameters

`link_identifier`  
The DBX link object to close.

### Return Values

Returns 1 on success and 0 on errors.

### Examples

**Example \#1 <span class="function">dbx\_close</span> example**

``` php
<?php
$link = dbx_connect(DBX_MYSQL, "localhost", "db", "username", "password")
    or die("Could not connect");

echo "Connected successfully";
dbx_close($link);
?>
```

### Notes

> **Note**:
>
> Always refer to the module-specific documentation as well.

### See Also

-   <span class="function">dbx\_connect</span>

dbx\_compare
============

Compare two rows for sorting purposes

### Description

<span class="type">int</span> <span
class="methodname">dbx\_compare</span> ( <span class="methodparam"><span
class="type">array</span> `$row_a`</span> , <span
class="methodparam"><span class="type">array</span> `$row_b`</span> ,
<span class="methodparam"><span class="type">string</span>
`$column_key`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
DBX\_CMP\_ASC \| DBX\_CMP\_NATIVE</span></span> \] )

<span class="function">dbx\_compare</span> is a helper function for
<span class="function">dbx\_sort</span> to ease the make and use of the
custom sorting function.

### Parameters

`row_a`  
First row

`row_b`  
Second row

`column_key`  
The compared column

`flags`  
The `flags` can be set to specify comparison direction:

-   <span class="simpara"> **`DBX_CMP_ASC`** - ascending order </span>
-   <span class="simpara"> **`DBX_CMP_DESC`** - descending order </span>

and the preferred comparison type:

-   <span class="simpara"> **`DBX_CMP_NATIVE`** - no type conversion
    </span>
-   <span class="simpara"> **`DBX_CMP_TEXT`** - compare items as strings
    </span>
-   <span class="simpara"> **`DBX_CMP_NUMBER`** - compare items
    numerically </span>

One of the direction and one of the type constant can be combined with
bitwise OR operator (\|).

### Return Values

Returns *0* if the *row\_a\[$column\_key\]* is equal to
*row\_b\[$column\_key\]*, and *1* or *-1* if the former is greater or is
smaller than the latter one, respectively, or vice versa if the `flag`
is set to **`DBX_CMP_DESC`**.

### Examples

**Example \#1 <span class="function">dbx\_compare</span> example**

``` php
<?php
function user_re_order($a, $b) 
{
    $rv = dbx_compare($a, $b, "parentid", DBX_CMP_DESC);
    if (!$rv) {
        $rv = dbx_compare($a, $b, "id", DBX_CMP_NUMBER);
    }
    return $rv;
}

$link   = dbx_connect(DBX_ODBC, "", "db", "username", "password")
    or die("Could not connect");

$result = dbx_query($link, "SELECT id, parentid, description FROM table ORDER BY id");
    // data in $result is now ordered by id

dbx_sort($result, "user_re_order");
    // date in $result is now ordered by parentid (descending), then by id

dbx_close($link);
?>
```

### See Also

-   <span class="function">dbx\_sort</span>

dbx\_connect
============

Open a connection/database

### Description

<span class="type"><span class="type">object</span><span
class="type">false</span></span> <span
class="methodname">dbx\_connect</span> ( <span class="methodparam"><span
class="type">mixed</span> `$module`</span> , <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">string</span>
`$database`</span> , <span class="methodparam"><span
class="type">string</span> `$username`</span> , <span
class="methodparam"><span class="type">string</span> `$password`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$persistent`</span> \] )

Opens a connection to a database.

### Parameters

`module`  
The `module` parameter can be either a string or a constant, though the
latter form is preferred. The possible values are given below, but keep
in mind that they only work if the module is actually loaded.

-   <span class="simpara"> **`DBX_MYSQL`** or *"mysql"* </span>
-   <span class="simpara"> **`DBX_ODBC`** or *"odbc"* </span>
-   <span class="simpara"> **`DBX_PGSQL`** or *"pgsql"* </span>
-   <span class="simpara"> **`DBX_MSSQL`** or *"mssql"* </span>
-   <span class="simpara"> **`DBX_FBSQL`** or *"fbsql"* </span>
-   <span class="simpara"> **`DBX_SYBASECT`** or *"sybase\_ct"* </span>
-   <span class="simpara"> **`DBX_OCI8`** or *"oci8"* </span>
-   <span class="simpara"> **`DBX_SQLITE`** or *"sqlite"* </span>

`host`  
The SQL server host

`database`  
The database name

`username`  
The username

`password`  
The password

`persistent`  
The `persistent` parameter can be set to **`DBX_PERSISTENT`**, if so, a
persistent connection will be created.

The `host`, `database`, `username` and `password` parameters are
expected, but not always used depending on the connect functions for the
abstracted module.

### Return Values

Returns an object on success, **`FALSE`** on error. If a connection has
been made but the database could not be selected, the connection is
closed and **`FALSE`** is returned.

The returned `object` has three properties:

<span class="property">database</span>  
<span class="simpara"> It is the name of the currently selected
database. </span>

<span class="property">handle</span>  
It is a valid handle for the connected database, and as such it can be
used in module-specific functions (if required).

``` php
<?php
$link = dbx_connect(DBX_MYSQL, "localhost", "db", "username", "password");
mysql_close($link->handle); // dbx_close($link) would be better here
?>
```

<span class="property">module</span>  
<span class="simpara"> It is used internally by dbx only, and is
actually the module number mentioned above. </span>

### Examples

**Example \#1 <span class="function">dbx\_connect</span> example**

``` php
<?php
$link = dbx_connect(DBX_ODBC, "", "db", "username", "password", DBX_PERSISTENT)
    or die("Could not connect");

echo "Connected successfully";
dbx_close($link);
?>
```

### Notes

> **Note**:
>
> Always refer to the module-specific documentation as well.

### See Also

-   <span class="function">dbx\_close</span>

dbx\_error
==========

Report the error message of the latest function call in the module

### Description

<span class="type">string</span> <span
class="methodname">dbx\_error</span> ( <span class="methodparam"><span
class="type">object</span> `$link_identifier`</span> )

<span class="function">dbx\_error</span> returns the last error message.

### Parameters

`link_identifier`  
The DBX link object returned by <span
class="function">dbx\_connect</span>

### Return Values

Returns a string containing the error message from the last function
call of the abstracted module (e.g. mysql module). If there are multiple
connections in the same module, just the last error is given. If there
are connections on different modules, the latest error is returned for
the module specified by the `link_identifier` parameter.

### Examples

**Example \#1 <span class="function">dbx\_error</span> example**

``` php
<?php
$link   = dbx_connect(DBX_MYSQL, "localhost", "db", "username", "password")
    or die("Could not connect");

$result = dbx_query($link, "select id from non_existing_table");
if ($result == 0) {
    echo dbx_error($link);
}
dbx_close($link);
?>
```

### Notes

> **Note**:
>
> Always refer to the module-specific documentation as well.
>
> The error message for <span class="productname">Microsoft SQL
> Server</span> is actually the result of the <span
> class="function">mssql\_get\_last\_message</span> function.
>
> The error message for Oracle (oci8) is not implemented yet.

dbx\_escape\_string
===================

Escape a string so it can safely be used in an sql-statement

### Description

<span class="type"><span class="type">string</span><span
class="type">null</span></span> <span
class="methodname">dbx\_escape\_string</span> ( <span
class="methodparam"><span class="type">object</span>
`$link_identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Escape the given string so that it can safely be used in an
sql-statement.

### Parameters

`link_identifier`  
The DBX link object returned by <span
class="function">dbx\_connect</span>

`text`  
The string to escape.

### Return Values

Returns the text, escaped where necessary (such as quotes, backslashes
etc). On error, **`NULL`** is returned.

### Examples

**Example \#1 <span class="function">dbx\_escape\_string</span>
example**

``` php
<?php
$link   = dbx_connect(DBX_MYSQL, "localhost", "db", "username", "password")
    or die("Could not connect");

$text = dbx_escape_string($link, "It\'s quoted and backslashed (\\).");
$result = dbx_query($link, "insert into tbl (txt) values ('" . $text . "')");
if ($result == 0) {
    echo dbx_error($link);
}
dbx_close($link);
?>
```

### See Also

-   <span class="function">dbx\_query</span>

dbx\_fetch\_row
===============

Fetches rows from a query-result that had the
**`DBX_RESULT_UNBUFFERED`** flag set

### Description

<span class="type">mixed</span> <span
class="methodname">dbx\_fetch\_row</span> ( <span
class="methodparam"><span class="type">object</span>
`$result_identifier`</span> )

<span class="function">dbx\_fetch\_row</span> fetches rows from a result
identifier that had the **`DBX_RESULT_UNBUFFERED`** flag set.

When the **`DBX_RESULT_UNBUFFERED`** is not set in the query, <span
class="function">dbx\_fetch\_row</span> will fail as all rows have
already been fetched into the results <span class="property">data</span>
property.

As a side effect, the <span class="property">rows</span> property of the
query-result object is incremented for each successful call to <span
class="function">dbx\_fetch\_row</span>.

### Parameters

`result_identifier`  
A result set returned by <span class="function">dbx\_query</span>.

### Return Values

Returns an object on success that contains the same information as any
row would have in the <span class="function">dbx\_query</span> result
<span class="property">data</span> property, including columns
accessible by index or fieldname when the flags for <span
class="function">dbx\_query</span> were set that way.

Upon failure, returns *0* (e.g. when no more rows are available).

### Examples

**Example \#1 How to handle the returned value**

``` php
<?php
$result = dbx_query($link, 'SELECT id, parentid, description FROM table', DBX_RESULT_UNBUFFERED);

echo "<table>\n";
while ($row = dbx_fetch_row($result)) {
    echo "<tr>\n";
    foreach ($row as $field) {
        echo "<td>$field</td>";
    }
    echo "</tr>\n";
}
echo "</table>\n";
?>
```

### See Also

-   <span class="function">dbx\_query</span>

dbx\_query
==========

Send a query and fetch all results (if any)

### Description

<span class="type">mixed</span> <span
class="methodname">dbx\_query</span> ( <span class="methodparam"><span
class="type">object</span> `$link_identifier`</span> , <span
class="methodparam"><span class="type">string</span>
`$sql_statement`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \] )

Sends a query and fetch all results.

### Parameters

`link_identifier`  
The DBX link object returned by <span
class="function">dbx\_connect</span>

`sql_statement`  
SQL statement.

Data inside the query should be
<a href="/book/dbx.html#dbx_escape_string" class="link">properly escaped</a>.

`flags`  
The `flags` parameter is used to control the amount of information that
is returned. It may be any combination of the following constants with
the bitwise OR operator (\|). The DBX\_COLNAMES\_\* flags override the
dbx.colnames\_case setting from `php.ini`.

**`DBX_RESULT_INDEX`**  
<span class="simpara"> It is *always* set, that is, the returned object
has a <span class="property">data</span> property which is a 2
dimensional array indexed numerically. For example, in the expression
*data\[2\]\[3\]* *2* stands for the row (or record) number and *3*
stands for the column (or field) number. The first row and column are
indexed at 0. </span> <span class="simpara"> If **`DBX_RESULT_ASSOC`**
is also specified, the returning object contains the information related
to **`DBX_RESULT_INFO`** too, even if it was not specified. </span>

**`DBX_RESULT_INFO`**  
<span class="simpara"> It provides info about columns, such as field
names and field types. </span>

**`DBX_RESULT_ASSOC`**  
<span class="simpara"> It effects that the field values can be accessed
with the respective column names used as keys to the returned object's
<span class="property">data</span> property. </span> <span
class="simpara"> Associated results are actually references to the
numerically indexed data, so modifying *data\[0\]\[0\]* causes that
*data\[0\]\['field\_name\_for\_first\_column'\]* is modified as well.
</span>

**`DBX_RESULT_UNBUFFERED`**  
<span class="simpara"> This flag will not create the <span
class="property">data</span> property, and the <span
class="property">rows</span> property will initially be 0. Use this flag
for large datasets, and use <span
class="function">dbx\_fetch\_row</span> to retrieve the results row by
row. </span> <span class="simpara"> The <span
class="function">dbx\_fetch\_row</span> function will return rows that
are conformant to the flags set with this query. Incidentally, it will
also update the <span class="property">rows</span> each time it is
called. </span>

**`DBX_COLNAMES_UNCHANGED`**  
<span class="simpara"> The case of the returned column names will not be
changed. </span>

**`DBX_COLNAMES_UPPERCASE`**  
<span class="simpara"> The case of the returned column names will be
changed to uppercase. </span>

**`DBX_COLNAMES_LOWERCASE`**  
<span class="simpara"> The case of the returned column names will be
changed to lowercase. </span>

Note that **`DBX_RESULT_INDEX`** is always used, regardless of the
actual value of `flags` parameter. This means that only the following
combinations are effective:

-   <span class="simpara"> **`DBX_RESULT_INDEX`** </span>
-   <span class="simpara"> **`DBX_RESULT_INDEX`** \|
    **`DBX_RESULT_INFO`** </span>
-   <span class="simpara"> **`DBX_RESULT_INDEX`** \|
    **`DBX_RESULT_INFO`** \| **`DBX_RESULT_ASSOC`** - this is the
    default, if `flags` is not specified. </span>

### Return Values

<span class="function">dbx\_query</span> returns an object or *1* on
success, and *0* on failure. The result object is returned only if the
query given in `sql_statement` produces a result set (i.e. a SELECT
query, even if the result set is empty).

The returned object has four or five properties depending on `flags`:

<span class="property">handle</span>  
It is a valid handle for the connected database, and as such it can be
used in module specific functions (if required).

``` php
<?php
$result = dbx_query($link, "SELECT id FROM table");
mysql_field_len($result->handle, 0);
?>
```

<span class="property">cols</span> and <span class="property">rows</span>  
These contain the number of columns (or fields) and rows (or records)
respectively.

``` php
<?php
$result = dbx_query($link, 'SELECT id FROM table');
echo $result->rows; // number of records
echo $result->cols; // number of fields 
?>
```

<span class="property">info</span> (optional)  
<span class="simpara"> It is returned only if either
**`DBX_RESULT_INFO`** or **`DBX_RESULT_ASSOC`** is specified in the
`flags` parameter. It is a 2 dimensional array, that has two named rows
(*name* and *type*) to retrieve column information. </span>

**Example \#1 lists each field's name and type**

``` php
<?php
$result = dbx_query($link, 'SELECT id FROM table',
                     DBX_RESULT_INDEX | DBX_RESULT_INFO);

for ($i = 0; $i < $result->cols; $i++ ) {
    echo $result->info['name'][$i] . "\n";
    echo $result->info['type'][$i] . "\n";  
}
?>
```

<span class="property">data</span>  
<span class="simpara"> This property contains the actual resulting data,
possibly associated with column names as well depending on `flags`. If
**`DBX_RESULT_ASSOC`** is set, it is possible to use
*$result-\>data\[2\]\["field\_name"\]*. </span>

**Example \#2 outputs the content of data property into HTML table**

``` php
<?php
$result = dbx_query($link, 'SELECT id, parentid, description FROM table');

echo "<table>\n";
foreach ($result->data as $row) {
    echo "<tr>\n";
    foreach ($row as $field) {
        echo "<td>$field</td>";
    }
    echo "</tr>\n";
}
echo "</table>\n";
?>
```

**Example \#3 How to handle UNBUFFERED queries**

``` php
<?php

$result = dbx_query ($link, 'SELECT id, parentid, description FROM table', DBX_RESULT_UNBUFFERED);

echo "<table>\n";
while ($row = dbx_fetch_row($result)) {
    echo "<tr>\n";
    foreach ($row as $field) {
        echo "<td>$field</td>";
    }
    echo "</tr>\n";
}
echo "</table>\n";

?>
```

### Examples

**Example \#4 How to handle the returned value**

``` php
<?php
$link   = dbx_connect(DBX_ODBC, "", "db", "username", "password")
    or die("Could not connect");

$result = dbx_query($link, 'SELECT id, parentid, description FROM table');

if (is_object($result) ) {
    // ... do some stuff here, see detailed examples below ...
    // first, print out field names and types 
    // then, draw a table filled with the returned field values
} else {
    exit("Query failed");
}

dbx_close($link);
?>
```

### Notes

> **Note**:
>
> Always refer to the module-specific documentation as well.
>
> Column names for queries on an Oracle database are returned in
> lowercase.

### See Also

-   <span class="function">dbx\_escape\_string</span>
-   <span class="function">dbx\_fetch\_row</span>
-   <span class="function">dbx\_connect</span>

dbx\_sort
=========

Sort a result from a dbx\_query by a custom sort function

### Description

<span class="type">bool</span> <span class="methodname">dbx\_sort</span>
( <span class="methodparam"><span class="type">object</span>
`$result`</span> , <span class="methodparam"><span
class="type">string</span> `$user_compare_function`</span> )

Sort a result from a <span class="function">dbx\_query</span> call with
a custom sort function.

### Parameters

`result`  
A result set returned by <span class="function">dbx\_query</span>.

`user_compare_function`  
The user-defined comparison function. It must accept two arguments and
return an integer less than, equal to, or greater than zero if the first
argument is considered to be respectively less than, equal to, or
greater than the second.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">dbx\_sort</span> example**

``` php
<?php
function user_re_order($a, $b) 
{
    $rv = dbx_compare($a, $b, "parentid", DBX_CMP_DESC);
    if (!$rv) {
        $rv = dbx_compare($a, $b, "id", DBX_CMP_NUMBER);
    }
    return $rv;
}

$link   = dbx_connect(DBX_ODBC, "", "db", "username", "password")
    or die("Could not connect");

$result = dbx_query($link, "SELECT id, parentid, description FROM tbl ORDER BY id");
    // data in $result is now ordered by id

dbx_sort($result, "user_re_order");
    // data in $result is now ordered by parentid (descending), then by id

dbx_close($link);
?>
```

### Notes

> **Note**:
>
> It is always better to use *ORDER BY* *SQL* clause instead of <span
> class="function">dbx\_sort</span> if possible.

### See Also

-   <span class="function">dbx\_compare</span>

**Table of Contents**

-   [dbx\_close](/book/dbx.html#dbx_close) — Close an open
    connection/database
-   [dbx\_compare](/book/dbx.html#dbx_compare) — Compare two rows for
    sorting purposes
-   [dbx\_connect](/book/dbx.html#dbx_connect) — Open a
    connection/database
-   [dbx\_error](/book/dbx.html#dbx_error) — Report the error message of
    the latest function call in the module
-   [dbx\_escape\_string](/book/dbx.html#dbx_escape_string) — Escape a
    string so it can safely be used in an sql-statement
-   [dbx\_fetch\_row](/book/dbx.html#dbx_fetch_row) — Fetches rows from
    a query-result that had the DBX\_RESULT\_UNBUFFERED flag set
-   [dbx\_query](/book/dbx.html#dbx_query) — Send a query and fetch all
    results (if any)
-   [dbx\_sort](/book/dbx.html#dbx_sort) — Sort a result from a
    dbx\_query by a custom sort function

Database issues
===============

This section holds common questions about relation between PHP and
databases. Yes, PHP can access virtually any database available today.

1.  [I heard it's possible to access Microsoft SQL Server from PHP.
    How?](#faq.databases.mssql)
2.  [Can I access Microsoft Access databases?](#faq.databases.access)
3.  [Why is the MySQL extension (ext/mysql) that I've been using for
    over 10 years discouraged from use? Is it deprecated? What do I use
    instead? How can I migrate?](#faq.databases.mysql.deprecated)
4.  [Why do I get an error that looks something like this: "Warning: 0
    is not a MySQL result index in \<file\> on line \<x\>" or "Warning:
    Supplied argument is not a valid MySQL result resource in \<file\>
    on line \<x\>"?](#faq.databases.mysqlresource)

**I heard it's possible to access Microsoft SQL Server from PHP. How?**  
On Unix machines you can use
<a href="/book/pdo.html#ODBC%20and%20DB2%20(PDO)" class="link">PDO_ODBC</a>
or the <a href="/book/uodbc.html" class="link">Unified ODBC API</a>.

On Windows machines you can also use
<a href="/book/pdo.html#MS%20SQL%20Server%20(PDO)" class="link">PDO_SQLSRV</a>
or <a href="/book/sqlsrv.html" class="link">SQLSRV</a>.

Also see the answer to the next question.

<!-- -->

**Can I access Microsoft Access databases?**  
Yes. You already have all the tools you need if you are running entirely
under Windows 9x/Me, or NT/2000, where you can use ODBC and Microsoft's
ODBC drivers for Microsoft Access databases.

If you are running PHP on a Unix box and want to talk to MS Access on a
Windows box you will need Unix ODBC drivers.
<a href="http://www.openlinksw.com/" class="link external">» OpenLink Software</a>
has Unix-based ODBC drivers that can do this.

Another alternative is to use an SQL server that has Windows ODBC
drivers and use that to store the data, which you can then access from
Microsoft Access (using ODBC) and PHP (using the built in drivers), or
to use an intermediary file format that Access and PHP both understand,
such as flat files or dBase databases. On this point Tim Hayes from
OpenLink software writes:

> Using another database as an intermediary is not a good idea, when you
> can use ODBC from PHP straight to your database - i.e. with OpenLink's
> drivers. If you do need to use an intermediary file format, OpenLink
> have now released Virtuoso (a virtual database engine) for NT, Linux
> and other Unix platforms. Please visit our
> <a href="http://www.openlinksw.com/" class="link external">» website</a>
> for a free download.

One option that has proved successful is to use MySQL and its MyODBC
drivers on Windows and synchronizing the databases. Steve Lawrence
writes:

-   <span class="simpara"> Install MySQL on your platform according to
    instructions with MySQL. Latest available from
    <a href="http://www.mysql.com/" class="link external">» http://www.mysql.com/</a>
    No special configuration required except when you set up a database,
    and configure the user account, you should put % in the host field,
    or the host name of the Windows computer you wish to access MySQL
    with. Make a note of your server name, username, and password.
    </span>
-   <span class="simpara"> Download the MyODBC for Windows driver from
    the MySQL site. Install it on your Windows machine. You can test the
    operation with the utilities included with this program. </span>
-   <span class="simpara"> Create a user or system dsn in your ODBC
    administrator, located in the control panel. Make up a dsn name,
    enter your hostname, user name, password, port, etc for you MySQL
    database configured in step 1. </span>
-   <span class="simpara"> Install Access with a full install, this
    makes sure you get the proper add-ins... at the least you will need
    ODBC support and the linked table manager. </span>
-   <span class="simpara"> Now the fun part! Create a new access
    database. In the table window right click and select Link Tables, or
    under the file menu option, select Get External Data and then Link
    Tables. When the file browser box comes up, select files of type:
    ODBC. Select System dsn and the name of your dsn created in step 3.
    Select the table to link, press OK, and presto! You can now open the
    table and add/delete/edit data on your MySQL server! You can also
    build queries, import/export tables to MySQL, build forms and
    reports, etc. </span>

Tips and Tricks:

-   <span class="simpara"> You can construct your tables in Access and
    export them to MySQL, then link them back in. That makes table
    creation quick. </span>
-   <span class="simpara"> When creating tables in Access, you must have
    a primary key defined in order to have write access to the table in
    access. Make sure you create a primary key in MySQL before linking
    in access </span>
-   <span class="simpara"> If you change a table in MySQL, you have to
    re-link it in Access. Go to tools\>add-ins\>linked table manager,
    cruise to your ODBC DSN, and select the table to re-link from there.
    you can also move your dsn source around there, just hit the always
    prompt for new location checkbox before pressing OK. </span>

<!-- -->

**Why is the MySQL extension (ext/mysql) that I've been using for over 10 years discouraged from use? Is it deprecated? What do I use instead? How can I migrate?**  
There are three MySQL extensions, as described under the
<a href="/set/mysqlinfo.html#Choosing%20an%20API" class="link">Choosing a MySQL API</a>
section. The old API should not be used, it is deprecated as of PHP
5.5.0 and has been moved to PECL as of PHP 7.0.0. You are strongly
encouraged to write all new code with either
<a href="/set/mysqlinfo.html#MySQLi" class="link">mysqli</a> or
<a href="/book/pdo.html#MySQL%20(PDO)" class="link">PDO_MySQL</a>.

Migration scripts are not available at this time, although the mysqli
API contains both a procedural and OOP API, with the procedural version
being similar to ext/mysql.

It is not possible to mix the extensions. So, for example, passing a
mysqli connection to PDO\_MySQL or ext/mysql will not work.

<!-- -->

**Why do I get an error that looks something like this: "Warning: 0 is not a MySQL result index in \<file\> on line \<x\>" or "Warning: Supplied argument is not a valid MySQL result resource in \<file\> on line \<x\>"?**  
You are trying to use a result identifier that is 0. The 0 indicates
that your query failed for some reason. You need to check for errors
after submitting a query and before you attempt to use the returned
result identifier. The proper way to do this is with code similar to the
following:

``` php
<?php

$result = mysql_query("SELECT * FROM tables_priv");
if (!$result) {
    echo mysql_error();
    exit;
}
?>
```

or

``` php
<?php

$result = mysql_query("SELECT * FROM tables_priv")
    or die("Bad query: " . mysql_error());
?>
```

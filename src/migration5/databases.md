Databases
---------

There were some changes in PHP 5 regarding databases (MySQL and SQLite).

In PHP 5 the MySQL client libraries are not bundled, because of license
and maintenance problems. MySQL is supported with the only change being
that MySQL support is no longer enabled by *default* in PHP 5. This
essentially means that PHP doesn't include the **--with-mysql** option
in the <a href="/configuration.html" class="link">configure</a> line so
that you must now manually do this when compiling PHP. Windows users
will need to edit `php.ini` and enable the `php_mysql.dll` DLL as in PHP
4 no such DLL existed, it was simply built into your Windows PHP
binaries.

There is also a new extension,
<a href="/set/mysqlinfo.html#Aliases%20and%20deprecated%20Mysqli%20Functions" class="link">MySQLi (Improved MySQL)</a>,
which is designed to work with MySQL 4.1 and above.

Since PHP 5, the
<a href="/book/sqlite.html#SQLite%20Functions" class="link">SQLite</a>
extension is built-in PHP. SQLite is an embeddable SQL database engine
and is not a client library used to connect to a big database server
(like MySQL or PostgreSQL). The SQLite library reads and writes directly
to and from the database files on disk.

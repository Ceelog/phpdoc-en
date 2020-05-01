New Extensions
--------------

The following new extensions are added (by default) as of PHP 5.3.0:

-   <span class="simpara">
    <a href="/book/enchant.html" class="link">Enchant</a> - An
    abstraction layer above various spelling libraries </span>
-   <span class="simpara">
    <a href="/book/fileinfo.html" class="link">Fileinfo</a> - An
    improved and more solid replacement, featuring full BC, for the
    <a href="/book/mime-magic.html" class="link">Mimetype</a> extension,
    which has been removed. </span>
-   <span class="simpara">
    <a href="/book/intl.html" class="link">INTL</a> -
    Internationalization extension. INTL is a wrapper around the
    <a href="http://www.icu-project.org/" class="link external">» ICU</a>
    library. </span>
-   <span class="simpara">
    <a href="/book/phar.html" class="link">Phar</a> - Implementation of
    PHP-Archive files. </span>
-   <span class="simpara">
    <a href="/book/sqlite3.html" class="link">SQLite3</a> - Support for
    SQLite version 3 databases. </span>

mysqlnd is a new core library shipped with PHP. It is a PHP-specific
replacement for libmysqlclient. mysqlnd will be used to build the
<a href="/set/mysqlinfo.html#MySQL%20(Original)" class="link">mysql</a>,
<a href="/set/mysqlinfo.html#MySQLi" class="link">mysqli</a> and
<a href="/book/pdo.html#MySQL%20(PDO)" class="link">PDO_MySQL</a>
extensions if libmysqlclient isn't found on the system. It may also be
used instead of libmysqlclient even when libmysqlclient is present.
mysqlnd is recommended for all PHP installations for performance
reasons.

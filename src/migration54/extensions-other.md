Other changes to extensions
---------------------------

Changes in extension behavior, and new features:

-   <span class="simpara">
    <a href="/set/mysqlinfo.html#MySQLi" class="link">mysqli</a> - <span
    class="classname">mysqli\_result</span> now implements
    <a href="/class/traversable.html" class="link">Traversable</a>
    </span>

<!-- -->

-   <span class="simpara">
    <a href="/book/pdo.html#MySQL%20(PDO)" class="link">pdo_mysql</a> -
    Removed support for linking with MySQL client libraries older than
    4.1 </span>

<!-- -->

-   <span class="simpara"> The MySQL extensions
    <a href="/set/mysqlinfo.html#MySQL%20(Original)" class="link">mysql</a>,
    <a href="/set/mysqlinfo.html#MySQLi" class="link">mysqli</a> and
    <a href="/book/pdo.html#MySQL%20(PDO)" class="link">PDO_mysql</a>
    use <a href="/set/mysqlinfo.html#Mysqlnd" class="link">mysqlnd</a>
    as the default library now. It is still possible to use
    libmysqlclient by specifying a path to the configure options.
    </span>

<!-- -->

-   <span class="simpara">
    <a href="/set/mysqlinfo.html#Mysqlnd" class="link">mysqlnd</a> -
    Added named pipes support </span>

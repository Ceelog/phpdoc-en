Backward Incompatible Changes
-----------------------------

Although most existing PHP 5 code should work without changes, please
take note of some backward incompatible changes:

-   <span class="simpara"> The newer internal parameter parsing API has
    been applied across all the extensions bundled with PHP 5.3.x. This
    parameter parsing API causes functions to return **`NULL`** when
    passed incompatible parameters. There are some exceptions to this
    rule, such as the <span class="function">get\_class</span> function,
    which will continue to return **`FALSE`** on error. </span>
-   <span class="simpara"> <span class="function">clearstatcache</span>
    no longer clears the realpath cache by default. </span>
-   <span class="simpara"> <span class="function">realpath</span> is now
    fully platform-independent. Consequence of this is that invalid
    relative paths such as *\_\_FILE\_\_ . "/../x"* do not work anymore.
    </span>
-   <span class="simpara"> The <span
    class="function">call\_user\_func</span> family of functions now
    propagate *$this* even if the callee is a parent class. </span>
-   <span class="simpara"> The array functions <span
    class="function">natsort</span>, <span
    class="function">natcasesort</span>, <span
    class="function">usort</span>, <span class="function">uasort</span>,
    <span class="function">uksort</span>, <span
    class="function">array\_flip</span>, and <span
    class="function">array\_unique</span> no longer accept objects
    passed as arguments. To apply these functions to an object, cast the
    object to an array first. </span>
-   <span class="simpara"> The behaviour of functions with by-reference
    parameters called by value has changed. Where previously the
    function would accept the by-value argument, a fatal error is now
    emitted. Any previous code passing constants or literals to
    functions expecting references, will need altering to assign the
    value to a variable before calling the function. </span>
-   <span class="simpara"> The new mysqlnd library necessitates the use
    of MySQL 4.1's newer 41-byte password format. Continued use of the
    old 16-byte passwords will cause <span
    class="function">mysql\_connect</span> and similar functions to emit
    the error, *"mysqlnd cannot connect to MySQL 4.1+ using old
    authentication."* </span>
-   <span class="simpara"> The new mysqlnd library does not read mysql
    configuration files (my.cnf/my.ini), as the older libmysqlclient
    library does. If your code relies on settings in the configuration
    file, you can load it explicitly with the <span
    class="function">mysqli\_options</span> function. Note that this
    means the PDO specific constants
    **`PDO::MYSQL_ATTR_READ_DEFAULT_FILE`** and
    **`PDO::MYSQL_ATTR_READ_DEFAULT_GROUP`** are not defined if MySQL
    support in PDO is compiled with mysqlnd. </span>
-   <span class="simpara"> The trailing / has been removed from the
    <span class="classname">SplFileInfo</span> class and other related
    directory classes. </span>
-   <span class="simpara"> The
    <a href="/language/oop5/magic.html#object.tostring" class="link">__toString()</a>
    magic method can no longer accept arguments. </span>
-   <span class="simpara"> The magic methods
    <a href="/language/oop5/overloading.html#object.get" class="link">__get()</a>,
    <a href="/language/oop5/overloading.html#object.set" class="link">__set()</a>,
    <a href="/language/oop5/overloading.html#object.isset" class="link">__isset()</a>,
    <a href="/language/oop5/overloading.html#object.unset" class="link">__unset()</a>,
    and
    <a href="/language/oop5/overloading.html#object.call" class="link">__call()</a>
    must always be public and can no longer be static. Method signatures
    are now enforced. </span>
-   <span class="simpara"> The
    <a href="/language/oop5/overloading.html#object.call" class="link">__call()</a>
    magic method is now invoked on access to private and protected
    methods. </span>
-   <span class="simpara"> <span class="function">func\_get\_arg</span>,
    <span class="function">func\_get\_args</span> and <span
    class="function">func\_num\_args</span> can no longer be called from
    the outermost scope of a file that has been included by calling
    <span class="function">include</span> or <span
    class="function">require</span> from within a function in the
    calling file. </span>
-   <span class="simpara"> An emulation layer for the MHASH extension to
    wrap around the Hash extension have been added. However not all the
    algorithms are covered, notable the s2k hashing algorithm. This
    means that s2k hashing is no longer available as of PHP 5.3.0.
    </span>

The following keywords are now reserved and may not be used in function,
class, etc. names.

-   <span class="simpara">
    <a href="/control-structures/goto.html" class="link">goto</a>
    </span>
-   <span class="simpara">
    <a href="/language/namespaces.html" class="link">namespace</a>
    </span>

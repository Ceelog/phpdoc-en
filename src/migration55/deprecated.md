Deprecated features in PHP 5.5.x
--------------------------------

### <a href="/set/mysqlinfo.html#MySQL%20(Original)" class="link">ext/mysql</a> deprecation

The
<a href="/set/mysqlinfo.html#MySQL%20(Original)" class="link">original MySQL extension</a>
is now deprecated, and will generate **`E_DEPRECATED`** errors when
connecting to a database. Instead, use the
<a href="/set/mysqlinfo.html#MySQLi" class="link">MySQLi</a> or
<a href="/book/pdo.html#MySQL%20(PDO)" class="link">PDO_MySQL</a>
extensions.

### <span class="function">preg\_replace</span> */e* modifier

The <span class="function">preg\_replace</span> */e* modifier is now
deprecated. Instead, use the <span
class="function">preg\_replace\_callback</span> function.

### <a href="/book/intl.html" class="link">intl</a> deprecations

<span class="methodname">IntlDateFormatter::setTimeZoneID</span> and
<span class="function">datefmt\_set\_timezone\_id</span> are now
deprecated. Instead, use the <span
class="methodname">IntlDateFormatter::setTimeZone</span> method and
<span class="function">datefmt\_set\_timezone</span> function,
respectively.

### <a href="/book/mcrypt.html" class="link">mcrypt</a> deprecations

The following functions have been deprecated:

-   <span class="simpara"> <span class="function">mcrypt\_cbc</span>
    </span>
-   <span class="simpara"> <span class="function">mcrypt\_cfb</span>
    </span>
-   <span class="simpara"> <span class="function">mcrypt\_ecb</span>
    </span>
-   <span class="simpara"> <span class="function">mcrypt\_ofb</span>
    </span>

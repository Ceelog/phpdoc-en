New features
------------

### New object type

A new type, <span class="type">object</span>, has been introduced that
can be used for (contravariant) parameter typing and (covariant) return
typing of any objects.

``` php
<?php

function test(object $obj) : object
{
    return new SplQueue();
}

test(new StdClass());
```

### Extension loading by name

Shared extensions no longer require their file extension (*.so* for Unix
or *.dll* for Windows) to be specified. This is enabled in the php.ini
file, as well as in the <span class="function">dl</span> function.

### Abstract method overriding

Abstract methods can now be overridden when an abstract class extends
another abstract class.

``` php
<?php

abstract class A
{
    abstract function test(string $s);
}
abstract class B extends A
{
    // overridden - still maintaining contravariance for parameters and covariance for return
    abstract function test($s) : int;
}
```

### <a href="/book/sodium.html" class="link">Sodium</a> is now a core extension

The modern Sodium cryptography library has now become a core extension
in PHP.

For a complete function reference, see the
<a href="/book/sodium.html" class="link">Sodium</a> chapter.

### Password hashing with Argon2

Argon2 has been added to the
<a href="/book/password.html" class="link">password hashing API</a>,
where the following constants have been exposed:

-   <span class="simpara"> **`PASSWORD_ARGON2I`** </span>
-   <span class="simpara"> **`PASSWORD_ARGON2_DEFAULT_MEMORY_COST`**
    </span>
-   <span class="simpara"> **`PASSWORD_ARGON2_DEFAULT_TIME_COST`**
    </span>
-   <span class="simpara"> **`PASSWORD_ARGON2_DEFAULT_THREADS`** </span>

### Extended string types for <a href="/book/pdo.html" class="link">PDO</a>

PDO's string type has been extended to support the national character
type when emulating prepares. This has been done with the following
constants:

-   <span class="simpara"> **`PDO::PARAM_STR_NATL`** </span>
-   <span class="simpara"> **`PDO::PARAM_STR_CHAR`** </span>
-   <span class="simpara"> **`PDO::ATTR_DEFAULT_STR_PARAM`** </span>

These constants are utilised by bitwise *OR*'ing them with
**`PDO::PARAM_STR`**:

``` php
<?php

$db->quote('über', PDO::PARAM_STR | PDO::PARAM_STR_NATL);
```

### Additional emulated prepares debugging information for <a href="/book/pdo.html" class="link">PDO</a>

The <span class="function">PDOStatement::debugDumpParams</span> method
has been updated to include the SQL being sent to the DB, where the
full, raw query (including the replaced placeholders with their bounded
values) will be shown. This has been added to aid with debugging
emulated prepares (and so it will only be available when emulated
prepares are turned on).

### Support for extended operations in <a href="/book/ldap.html" class="link">LDAP</a>

Support for EXOP has been added to the LDAP extension. This has been
done by exposing the following functions and constants:

-   <span class="simpara"> <span
    class="function">ldap\_parse\_exop</span> </span>
-   <span class="simpara"> <span class="function">ldap\_exop</span>
    </span>
-   <span class="simpara"> <span
    class="function">ldap\_exop\_passwd</span> </span>
-   <span class="simpara"> <span
    class="function">ldap\_exop\_whoami</span> </span>
-   <span class="simpara"> **`LDAP_EXOP_START_TLS`** </span>
-   <span class="simpara"> **`LDAP_EXOP_MODIFY_PASSWD`** </span>
-   <span class="simpara"> **`LDAP_EXOP_REFRESH`** </span>
-   <span class="simpara"> **`LDAP_EXOP_WHO_AM_I`** </span>
-   <span class="simpara"> **`LDAP_EXOP_TURN`** </span>

### Address Information additions to the <a href="/book/sockets.html" class="link">Sockets</a> extension

The sockets extension now has the ability to lookup address information,
as well as connect to it, bind to it, and explain it. The following four
functions have been added for this:

-   <span class="simpara"> <span
    class="function">socket\_addrinfo\_lookup</span> </span>
-   <span class="simpara"> <span
    class="function">socket\_addrinfo\_connect</span> </span>
-   <span class="simpara"> <span
    class="function">socket\_addrinfo\_bind</span> </span>
-   <span class="simpara"> <span
    class="function">socket\_addrinfo\_explain</span> </span>

### Parameter type widening

Parameter types from overridden methods and from interface
implementations may now be omitted. This is still in compliance with
LSP, since parameters types are contravariant.

``` php
<?php

interface A
{
    public function Test(array $input);
}

class B implements A
{
    public function Test($input){} // type omitted for $input
}
```

### Allow a trailing comma for grouped namespaces

A trailing comma can now be added to the group-use syntax introduced in
PHP 7.0.

``` php
<?php

use Foo\Bar\{
    Foo,
    Bar,
    Baz,
};
```

### <span class="function">proc\_nice</span> support on Windows

The <span class="function">proc\_nice</span> function is now supported
on Windows.

### <span class="function">pack</span> and <span class="function">unpack</span> endian support

The <span class="function">pack</span> and <span
class="function">unpack</span> functions now support float and double in
both little and big endian.

### Enhancements to the <a href="/book/exif.html" class="link">EXIF</a> extension

The EXIF extension has been updated to support a much larger range of
formats. This means that their format specific tags are now properly
translated when parsing images with the <span
class="function">exif\_read\_data</span> function. The following new
formats are now supported:

-   <span class="simpara"> Samsung </span>
-   <span class="simpara"> DJI </span>
-   <span class="simpara"> Panasonic </span>
-   <span class="simpara"> Sony </span>
-   <span class="simpara"> Pentax </span>
-   <span class="simpara"> Minolta </span>
-   <span class="simpara"> Sigma/Foveon </span>
-   <span class="simpara"> AGFA </span>
-   <span class="simpara"> Kyocera </span>
-   <span class="simpara"> Ricoh </span>
-   <span class="simpara"> Epson </span>

The EXIF functions <span class="function">exif\_read\_data</span> and
<span class="function">exif\_thumbnail</span> now support passing
streams as their first argument.

### New features in <a href="/book/pcre.html" class="link">PCRE</a>

-   <span class="simpara"> The *J* modifier for setting PCRE\_DUPNAMES
    has been added. </span>

### <a href="/book/sqlite3.html" class="link">SQLite3</a> allows writing BLOBs

<span class="methodname">SQLite3::openBlob</span> now allows to open
BLOB fields in write mode; formerly only read mode was supported.

### <a href="/book/oci8.html" class="link">Oracle OCI8</a> Transparent Application Failover Callbacks

Support for
<a href="/book/oci8.html#OCI8%20Transparent%20Application%20Failover%20(TAF)%20Support" class="link">Oracle Database Transparent Application Failover (TAF) callbacks</a>
has been added. TAF allows PHP OCI8 applications to automatically
reconnect to a preconfigured database when a connection is broken. The
new TAF callback support allows PHP applications to monitor and control
reconnection during failover.

### Enhancements to the <a href="/book/zip.html" class="link">ZIP</a> extension

Read and write support for encrypted archives has been added (requires
libzip 1.2.0).

The <span class="classname">ZipArchive</span> class now implements the
<span class="interfacename">Countable</span> interface.

The *zip://* stream now accepts a *'password'* context option.

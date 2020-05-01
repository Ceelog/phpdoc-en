Other changes
-------------

### Moving of <span class="function">utf8\_encode</span> and <span class="function">utf8\_decode</span>

The <span class="function">utf8\_encode</span> and <span
class="function">utf8\_decode</span> functions have now been moved to
the standard extension as string functions, whereas before the
<a href="/book/xml.html" class="link">XML</a> extension was required for
them to be available.

### Changes to <span class="function">mail</span> and <span class="function">mb\_sendmail</span>

The $additional\_headers parameter of <span class="function">mail</span>
and <span class="function">mb\_sendmail</span> now also accepts an <span
class="type">array</span> instead of a <span class="type">string</span>.

### LMDB support

The <a href="/book/dba.html" class="link">DBA</a> extension now has
support for LMDB.

### Changes to the PHP build system

-   <span class="simpara"> Unix: Autoconf 2.64 or greater is now
    required to build PHP. </span>
-   <span class="simpara"> Unix: *--with-pdo-oci* configure argument no
    longer needs the version number of the Oracle Instant Client.
    </span>
-   <span class="simpara"> Unix: *--enable-gd-native-ttf* configure
    argument has been removed. This was not used since PHP 5.5.0.
    </span>
-   <span class="simpara"> Windows: *--with-config-profile* configure
    argument has been added. This can be used to save specific
    configures, much like the magical `config.nice.bat` file. </span>

### Changes to <a href="/book/image.html" class="link">GD</a>

-   <span class="simpara"> <span class="function">imageantialias</span>
    is now also available if compiled with a system libgd. </span>
-   <span class="simpara"> <span class="function">imagegd</span> stores
    truecolor images as real truecolor images. Formerly, they have been
    converted to palette. </span>

### Moving <a href="/book/mcrypt.html" class="link">MCrypt</a> to PECL

The <a href="/book/mcrypt.html" class="link">MCrypt</a> extension has
now been moved out of the core to PECL. Given the mcrypt library has not
seen any updates since 2007, its usage is highly discouraged. Instead,
either the <a href="/book/openssl.html" class="link">OpenSSL</a> or
<a href="/book/sodium.html" class="link">Sodium</a> extension should be
used.

### <span class="function">session\_module\_name</span>

Passing *"user"* to <span class="function">session\_module\_name</span>
now raises an error of level **`E_RECOVERABLE_ERROR`**. Formerly, this
has been silently ignored.

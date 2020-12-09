Oracle OCI8
===========

**Table of Contents**

-   [Introduction](/book/oci8.html#Introduction)
-   [Installing/Configuring](/book/oci8.html#Installing/Configuring)
    -   [Requirements](/book/oci8.html#Requirements)
    -   [Installation](/book/oci8.html#Installation)
    -   [Testing](/book/oci8.html#Testing)
    -   [Runtime Configuration](/book/oci8.html#Runtime%20Configuration)
-   [Predefined Constants](/book/oci8.html#Predefined%20Constants)
-   [Examples](/book/oci8.html#Examples)
-   [OCI8 Connection Handling and Connection
    Pooling](/book/oci8.html#OCI8%20Connection%20Handling%20and%20Connection%20Pooling)
-   [OCI8 Fast Application Notification (FAN)
    Support](/book/oci8.html#OCI8%20Fast%20Application%20Notification%20(FAN)%20Support)
-   [OCI8 Transparent Application Failover (TAF)
    Support](/book/oci8.html#OCI8%20Transparent%20Application%20Failover%20(TAF)%20Support)
-   [OCI8 and DTrace Dynamic
    Tracing](/book/oci8.html#OCI8%20and%20DTrace%20Dynamic%20Tracing)
-   [Supported Datatypes](/book/oci8.html#Supported%20Datatypes)
-   [OCI8 Functions](/book/oci8.html#OCI8%20Functions)
    -   [oci\_bind\_array\_by\_name](/book/oci8.html#oci_bind_array_by_name)
        — Binds a PHP array to an Oracle PL/SQL array parameter
    -   [oci\_bind\_by\_name](/book/oci8.html#oci_bind_by_name) — Binds
        a PHP variable to an Oracle placeholder
    -   [oci\_cancel](/book/oci8.html#oci_cancel) — Cancels reading from
        cursor
    -   [oci\_client\_version](/book/oci8.html#oci_client_version) —
        Returns the Oracle client library version
    -   [oci\_close](/book/oci8.html#oci_close) — Closes an Oracle
        connection
    -   [oci\_commit](/book/oci8.html#oci_commit) — Commits the
        outstanding database transaction
    -   [oci\_connect](/book/oci8.html#oci_connect) — Connect to an
        Oracle database
    -   [oci\_define\_by\_name](/book/oci8.html#oci_define_by_name) —
        Associates a PHP variable with a column for query fetches
    -   [oci\_error](/book/oci8.html#oci_error) — Returns the last error
        found
    -   [oci\_execute](/book/oci8.html#oci_execute) — Executes a
        statement
    -   [oci\_fetch\_all](/book/oci8.html#oci_fetch_all) — Fetches
        multiple rows from a query into a two-dimensional array
    -   [oci\_fetch\_array](/book/oci8.html#oci_fetch_array) — Returns
        the next row from a query as an associative or numeric array
    -   [oci\_fetch\_assoc](/book/oci8.html#oci_fetch_assoc) — Returns
        the next row from a query as an associative array
    -   [oci\_fetch\_object](/book/oci8.html#oci_fetch_object) — Returns
        the next row from a query as an object
    -   [oci\_fetch\_row](/book/oci8.html#oci_fetch_row) — Returns the
        next row from a query as a numeric array
    -   [oci\_fetch](/book/oci8.html#oci_fetch) — Fetches the next row
        from a query into internal buffers
    -   [oci\_field\_is\_null](/book/oci8.html#oci_field_is_null) —
        Checks if a field in the currently fetched row is null
    -   [oci\_field\_name](/book/oci8.html#oci_field_name) — Returns the
        name of a field from the statement
    -   [oci\_field\_precision](/book/oci8.html#oci_field_precision) —
        Tell the precision of a field
    -   [oci\_field\_scale](/book/oci8.html#oci_field_scale) — Tell the
        scale of the field
    -   [oci\_field\_size](/book/oci8.html#oci_field_size) — Returns
        field's size
    -   [oci\_field\_type\_raw](/book/oci8.html#oci_field_type_raw) —
        Tell the raw Oracle data type of the field
    -   [oci\_field\_type](/book/oci8.html#oci_field_type) — Returns a
        field's data type name
    -   [oci\_free\_descriptor](/book/oci8.html#oci_free_descriptor) —
        Frees a descriptor
    -   [oci\_free\_statement](/book/oci8.html#oci_free_statement) —
        Frees all resources associated with statement or cursor
    -   [oci\_get\_implicit\_resultset](/book/oci8.html#oci_get_implicit_resultset)
        — Returns the next child statement resource from a parent
        statement resource that has Oracle Database Implicit Result Sets
    -   [oci\_lob\_copy](/book/oci8.html#oci_lob_copy) — Copies large
        object
    -   [oci\_lob\_is\_equal](/book/oci8.html#oci_lob_is_equal) —
        Compares two LOB/FILE locators for equality
    -   [oci\_new\_collection](/book/oci8.html#oci_new_collection) —
        Allocates new collection object
    -   [oci\_new\_connect](/book/oci8.html#oci_new_connect) — Connect
        to the Oracle server using a unique connection
    -   [oci\_new\_cursor](/book/oci8.html#oci_new_cursor) — Allocates
        and returns a new cursor (statement handle)
    -   [oci\_new\_descriptor](/book/oci8.html#oci_new_descriptor) —
        Initializes a new empty LOB or FILE descriptor
    -   [oci\_num\_fields](/book/oci8.html#oci_num_fields) — Returns the
        number of result columns in a statement
    -   [oci\_num\_rows](/book/oci8.html#oci_num_rows) — Returns number
        of rows affected during statement execution
    -   [oci\_parse](/book/oci8.html#oci_parse) — Prepares an Oracle
        statement for execution
    -   [oci\_password\_change](/book/oci8.html#oci_password_change) —
        Changes password of Oracle's user
    -   [oci\_pconnect](/book/oci8.html#oci_pconnect) — Connect to an
        Oracle database using a persistent connection
    -   [oci\_register\_taf\_callback](/book/oci8.html#oci_register_taf_callback)
        — Register a user-defined callback function for Oracle Database
        TAF
    -   [oci\_result](/book/oci8.html#oci_result) — Returns field's
        value from the fetched row
    -   [oci\_rollback](/book/oci8.html#oci_rollback) — Rolls back the
        outstanding database transaction
    -   [oci\_server\_version](/book/oci8.html#oci_server_version) —
        Returns the Oracle Database version
    -   [oci\_set\_action](/book/oci8.html#oci_set_action) — Sets the
        action name
    -   [oci\_set\_call\_timeout](/book/oci8.html#oci_set_call_timeout)
        — Sets a millisecond timeout for database calls
    -   [oci\_set\_client\_identifier](/book/oci8.html#oci_set_client_identifier)
        — Sets the client identifier
    -   [oci\_set\_client\_info](/book/oci8.html#oci_set_client_info) —
        Sets the client information
    -   [oci\_set\_db\_operation](/book/oci8.html#oci_set_db_operation)
        — Sets the database operation
    -   [oci\_set\_edition](/book/oci8.html#oci_set_edition) — Sets the
        database edition
    -   [oci\_set\_module\_name](/book/oci8.html#oci_set_module_name) —
        Sets the module name
    -   [oci\_set\_prefetch](/book/oci8.html#oci_set_prefetch) — Sets
        number of rows to be prefetched by queries
    -   [oci\_statement\_type](/book/oci8.html#oci_statement_type) —
        Returns the type of a statement
    -   [oci\_unregister\_taf\_callback](/book/oci8.html#oci_unregister_taf_callback)
        — Unregister a user-defined callback function for Oracle
        Database TAF
-   [OCICollection](/book/oci8.html#OCICollection) — The OCICollection
    class
    -   [OCICollection::append](/book/oci8.html#OCICollection::append) —
        Appends element to the collection
    -   [OCICollection::assign](/book/oci8.html#OCICollection::assign) —
        Assigns a value to the collection from another existing
        collection
    -   [OCICollection::assignElem](/book/oci8.html#OCICollection::assignElem)
        — Assigns a value to the element of the collection
    -   [OCICollection::free](/book/oci8.html#OCICollection::free) —
        Frees the resources associated with the collection object
    -   [OCICollection::getElem](/book/oci8.html#OCICollection::getElem)
        — Returns value of the element
    -   [OCICollection::max](/book/oci8.html#OCICollection::max) —
        Returns the maximum number of elements in the collection
    -   [OCICollection::size](/book/oci8.html#OCICollection::size) —
        Returns size of the collection
    -   [OCICollection::trim](/book/oci8.html#OCICollection::trim) —
        Trims elements from the end of the collection
-   [OCILob](/book/oci8.html#OCILob) — The OCILob class
    -   [OCILob::append](/book/oci8.html#OCILob::append) — Appends data
        from the large object to another large object
    -   [OCILob::close](/book/oci8.html#OCILob::close) — Closes LOB
        descriptor
    -   [OCILob::eof](/book/oci8.html#OCILob::eof) — Tests for
        end-of-file on a large object's descriptor
    -   [OCILob::erase](/book/oci8.html#OCILob::erase) — Erases a
        specified portion of the internal LOB data
    -   [OCILob::export](/book/oci8.html#OCILob::export) — Exports LOB's
        contents to a file
    -   [OCILob::flush](/book/oci8.html#OCILob::flush) — Flushes/writes
        buffer of the LOB to the server
    -   [OCILob::free](/book/oci8.html#OCILob::free) — Frees resources
        associated with the LOB descriptor
    -   [OCILob::getBuffering](/book/oci8.html#OCILob::getBuffering) —
        Returns current state of buffering for the large object
    -   [OCILob::import](/book/oci8.html#OCILob::import) — Imports file
        data to the LOB
    -   [OCILob::load](/book/oci8.html#OCILob::load) — Returns large
        object's contents
    -   [OCILob::read](/book/oci8.html#OCILob::read) — Reads part of the
        large object
    -   [OCILob::rewind](/book/oci8.html#OCILob::rewind) — Moves the
        internal pointer to the beginning of the large object
    -   [OCILob::save](/book/oci8.html#OCILob::save) — Saves data to the
        large object
    -   [OCILob::saveFile](/book/oci8.html#OCILob::saveFile) — Alias of
        OCILob::import
    -   [OCILob::seek](/book/oci8.html#OCILob::seek) — Sets the internal
        pointer of the large object
    -   [OCILob::setBuffering](/book/oci8.html#OCILob::setBuffering) —
        Changes current state of buffering for the large object
    -   [OCILob::size](/book/oci8.html#OCILob::size) — Returns size of
        large object
    -   [OCILob::tell](/book/oci8.html#OCILob::tell) — Returns the
        current position of internal pointer of large object
    -   [OCILob::truncate](/book/oci8.html#OCILob::truncate) — Truncates
        large object
    -   [OCILob::write](/book/oci8.html#OCILob::write) — Writes data to
        the large object
    -   [OCILob::writeTemporary](/book/oci8.html#OCILob::writeTemporary)
        — Writes a temporary large object
    -   [OCILob::writeToFile](/book/oci8.html#OCILob::writeToFile) —
        Alias of OCILob::export
-   [OCI8 Obsolete Aliases and
    Functions](/book/oci8.html#OCI8%20Obsolete%20Aliases%20and%20Functions)
    -   [oci\_internal\_debug](/book/oci8.html#oci_internal_debug) —
        Enables or disables internal debug output
    -   [ocibindbyname](/book/oci8.html#ocibindbyname) — Alias of
        oci\_bind\_by\_name
    -   [ocicancel](/book/oci8.html#ocicancel) — Alias of oci\_cancel
    -   [ocicloselob](/book/oci8.html#ocicloselob) — Alias of
        OCI-Lob::close
    -   [ocicollappend](/book/oci8.html#ocicollappend) — Alias of
        OCICollection::append
    -   [ocicollassign](/book/oci8.html#ocicollassign) — Alias of
        OCICollection::assign
    -   [ocicollassignelem](/book/oci8.html#ocicollassignelem) — Alias
        of OCICollection::assignElem
    -   [ocicollgetelem](/book/oci8.html#ocicollgetelem) — Alias of
        OCICollection::getElem
    -   [ocicollmax](/book/oci8.html#ocicollmax) — Alias of
        OCICollection::max
    -   [ocicollsize](/book/oci8.html#ocicollsize) — Alias of
        OCICollection::size
    -   [ocicolltrim](/book/oci8.html#ocicolltrim) — Alias of
        OCICollection::trim
    -   [ocicolumnisnull](/book/oci8.html#ocicolumnisnull) — Alias of
        oci\_field\_is\_null
    -   [ocicolumnname](/book/oci8.html#ocicolumnname) — Alias of
        oci\_field\_name
    -   [ocicolumnprecision](/book/oci8.html#ocicolumnprecision) — Alias
        of oci\_field\_precision
    -   [ocicolumnscale](/book/oci8.html#ocicolumnscale) — Alias of
        oci\_field\_scale
    -   [ocicolumnsize](/book/oci8.html#ocicolumnsize) — Alias of
        oci\_field\_size
    -   [ocicolumntype](/book/oci8.html#ocicolumntype) — Alias of
        oci\_field\_type
    -   [ocicolumntyperaw](/book/oci8.html#ocicolumntyperaw) — Alias of
        oci\_field\_type\_raw
    -   [ocicommit](/book/oci8.html#ocicommit) — Alias of oci\_commit
    -   [ocidefinebyname](/book/oci8.html#ocidefinebyname) — Alias of
        oci\_define\_by\_name
    -   [ocierror](/book/oci8.html#ocierror) — Alias of oci\_error
    -   [ociexecute](/book/oci8.html#ociexecute) — Alias of oci\_execute
    -   [ocifetch](/book/oci8.html#ocifetch) — Alias of oci\_fetch
    -   [ocifetchinto](/book/oci8.html#ocifetchinto) — Obsolete variant
        of oci\_fetch\_array, oci\_fetch\_object, oci\_fetch\_assoc and
        oci\_fetch\_row
    -   [ocifetchstatement](/book/oci8.html#ocifetchstatement) — Alias
        of oci\_fetch\_all
    -   [ocifreecollection](/book/oci8.html#ocifreecollection) — Alias
        of OCICollection::free
    -   [ocifreecursor](/book/oci8.html#ocifreecursor) — Alias of
        oci\_free\_statement
    -   [ocifreedesc](/book/oci8.html#ocifreedesc) — Alias of
        OCI-Lob::free
    -   [ocifreestatement](/book/oci8.html#ocifreestatement) — Alias of
        oci\_free\_statement
    -   [ociinternaldebug](/book/oci8.html#ociinternaldebug) — Alias of
        oci\_internal\_debug
    -   [ociloadlob](/book/oci8.html#ociloadlob) — Alias of
        OCI-Lob::load
    -   [ocilogoff](/book/oci8.html#ocilogoff) — Alias of oci\_close
    -   [ocilogon](/book/oci8.html#ocilogon) — Alias of oci\_connect
    -   [ocinewcollection](/book/oci8.html#ocinewcollection) — Alias of
        oci\_new\_collection
    -   [ocinewcursor](/book/oci8.html#ocinewcursor) — Alias of
        oci\_new\_cursor
    -   [ocinewdescriptor](/book/oci8.html#ocinewdescriptor) — Alias of
        oci\_new\_descriptor
    -   [ocinlogon](/book/oci8.html#ocinlogon) — Alias of
        oci\_new\_connect
    -   [ocinumcols](/book/oci8.html#ocinumcols) — Alias of
        oci\_num\_fields
    -   [ociparse](/book/oci8.html#ociparse) — Alias of oci\_parse
    -   [ociplogon](/book/oci8.html#ociplogon) — Alias of oci\_pconnect
    -   [ociresult](/book/oci8.html#ociresult) — Alias of oci\_result
    -   [ocirollback](/book/oci8.html#ocirollback) — Alias of
        oci\_rollback
    -   [ocirowcount](/book/oci8.html#ocirowcount) — Alias of
        oci\_num\_rows
    -   [ocisavelob](/book/oci8.html#ocisavelob) — Alias of
        OCI-Lob::save
    -   [ocisavelobfile](/book/oci8.html#ocisavelobfile) — Alias of
        OCI-Lob::import
    -   [ociserverversion](/book/oci8.html#ociserverversion) — Alias of
        oci\_server\_version
    -   [ocisetprefetch](/book/oci8.html#ocisetprefetch) — Alias of
        oci\_set\_prefetch
    -   [ocistatementtype](/book/oci8.html#ocistatementtype) — Alias of
        oci\_statement\_type
    -   [ociwritelobtofile](/book/oci8.html#ociwritelobtofile) — Alias
        of OCI-Lob::export
    -   [ociwritetemporarylob](/book/oci8.html#ociwritetemporarylob) —
        Alias of OCI-Lob::writeTemporary

These functions allow you to access Oracle Database. They support SQL
and PL/SQL statements. Basic features include transaction control,
binding of PHP variables to Oracle placeholders, and support for large
object (LOB) types and collections. Oracle's scalability features such
as Database Resident Connection Pooling (DRCP) and result caching are
also supported.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/oci8.html#Requirements)
-   [Installation](/book/oci8.html#Installation)
-   [Testing](/book/oci8.html#Testing)
-   [Runtime Configuration](/book/oci8.html#Runtime%20Configuration)

Requirements
------------

OCI8 3.0 is included with PHP 8. It is also available from
<a href="https://pecl.php.net/" class="link external">» PECL</a>. For
PHP 7, use OCI8 2.2 from
<a href="https://pecl.php.net/" class="link external">» PECL</a>. OCI8
requires Oracle 10*g* or later Oracle client libraries.

If the Oracle Database is on the same machine as PHP, the database
software already contains the necessary libraries and header files. When
PHP is on a different machine, use the free
<a href="https://www.oracle.com/database/technologies/instant-client.html" class="link external">» Oracle Instant Client</a>
libraries.

To use Oracle Instant Client, install the *Basic* or *Basic Light*
Oracle Instant Client ZIP file, RPM package, or DMG package. When
building OCI8 from source code, also install the Instant Client *SDK*.

You must run PHP with the same, or a more recent, version of the Oracle
libraries that OCI8 was built with.

> **Note**:
>
> Oracle's standard client-server network interoperability allows
> connections between different versions of Oracle Client and Oracle
> Database. For certified configurations see Oracle Support's Doc ID
> 207303.1. In summary, Oracle Client 19, 18 and 12.2 can connect to
> Oracle Database 11.2 or greater. Oracle Client 12.1 can connect to
> Oracle Database 10.2 or greater. Oracle Client 11.2 can connect to
> Oracle Database 9.2 or greater.

> **Note**:
>
> Full OCI8 feature support is only available when using the most recent
> versions of the Oracle client libraries and database.

Installation
------------

Configuring PHP with OCI8
-------------------------

Review the previous
<a href="/book/oci8.html#Requirements" class="link">Requirements</a>
section before configuring OCI8.

Before starting the web server, OCI8 typically requires several Oracle
environment variables (see below) to locate libraries, point to
configuration files, and set some basic properties such as the character
set used by Oracle libraries. The variables must be set *before* any PHP
process starts.

The PHP binary must link with the same, or more recent, major version of
Oracle libraries as it was configured with. For example, if you build
OCI8 with Oracle 19 libraries, then PHP should also be deployed and run
with Oracle 19 libraries. PHP applications can connect to other versions
of Oracle Database, since Oracle has client-server cross-version
compatibility.

Installing OCI8 from PECL Using the pecl Command
------------------------------------------------

The OCI8 extension can be added to an existing PHP installation by using
the
<a href="https://pecl.php.net/package/oci8" class="link external">» PECL</a>
repository.

-   If you are behind a firewall, set PEAR's proxy, for example:

        pear config-set http_proxy http://my-proxy.example.com:80/

-   Run

        pecl install oci8

    For PHP 7, use *pecl install oci8-2.2.0*

-   When prompted, enter either the value of *$ORACLE\_HOME*, or
    *instantclient,/path/to/instant/client/lib*.

    Note: Do not enter variable names like *$ORACLE\_HOME* or *$HOME*
    because *pecl* will not expand them. Instead, enter an expanded
    path, for example */opt/oracle/product/19c/dbhome\_1* or
    *instantclient,/Users/myname/Downloads/instantclient\_19\_8*

-   If you get an error *oci8\_dtrace\_gen.h: No such file or
    directory*, it means PHP was built with
    <a href="/features/dtrace.html" class="link">DTrace Dynamic Tracing</a>
    enabled. Install using:

        $ export PHP_DTRACE=yes
        $ pecl install oci8

-   Edit your `php.ini` file and add the line:

        extension=oci8.so

    Make sure the `php.ini` directive
    <a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>
    is set to the directory that `oci8.so` was installed in.

Installing OCI8 from PECL Using phpize
--------------------------------------

To install OCI8 on an existing PHP installation when the *pecl* command
is not available, manually download the
<a href="https://pecl.php.net/package/oci8" class="link external">» PECL</a>
OCI8 package, e.g. `oci8-3.0.0.tgz`.

-   Extract the package:

        tar -zxf oci8-3.0.0.tgz
        cd oci8-3.0.0

-   Prepare the package:

        phpize

-   Configure the package, either using *$ORACLE\_HOME* or Instant
    Client

        ./configure -with-oci8=shared,$ORACLE_HOME

    or

        ./configure -with-oci8=shared,instantclient,/path/to/instant/client/lib

-   Install the package:

        make install

-   If you get an error *oci8\_dtrace\_gen.h: No such file or
    directory*, it means PHP was built with
    <a href="/features/dtrace.html" class="link">DTrace Dynamic Tracing</a>
    enabled. Re-run the *configure* and *make* commands after setting
    this environment variable:

        $ export PHP_DTRACE=yes

-   Edit your `php.ini` file and add the line:

        extension=oci8.so

    Make sure the `php.ini` directive
    <a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>
    is set to the directory that `oci8.so` was installed in.

Installing OCI8 as a Shared Extension when Building PHP
-------------------------------------------------------

If you are building PHP from source code, the configuration *shared*
option can be used to build OCI8 as a shared library that can be
dynamically loaded into PHP. Building a shared extension allows OCI8 to
be upgraded easily without impacting the rest of PHP.

Configure OCI8 using one of the following configure options.

-   If using the free
    <a href="https://www.oracle.com/database/technologies/instant-client.html" class="link external">» Oracle Instant Client</a>
    libraries, then do:

        ./configure --with-oci8=shared,instantclient,/path/to/instant/client/lib

    If Instant Client 12.2 (or earlier) is installed from ZIP files,
    make sure to create the library symbolic link first, for example *ln
    -s libclntsh.so.12.1 libclntsh.so*.

    If using an RPM-based installation of Oracle Instant Client, the
    configure line will look like this:

        ./configure --with-oci8=shared,instantclient,/usr/lib/oracle/<version>/client/lib

    For example,
    **--with-oci8=shared,instantclient,/usr/lib/oracle/19.9/client/lib**

    Note that Oracle Instant Client support first appeared in PHP 4.3.11
    and 5.0.4 and originally used the option
    **--with-oci8-instant-client** to configure PHP.

-   If using an Oracle database or full Oracle Client installation then
    do:

        ./configure --with-oci8=shared,$ORACLE_HOME

    Make sure the web server user (*nobody*, *www*) has access to the
    libraries, initialization files and `tnsnames.ora` (if used) under
    the *$ORACLE\_HOME* directory. With Oracle 10*g*R2, you may need to
    run the `$ORACLE_HOME/install/changePerm.sh` utility to give
    directory access.

After configuration, follow the usual PHP building procedure, e.g. *make
install*. The OCI8 shared extension `oci8.so` library will be created.
It may need to be manually moved to the PHP extension directory,
specified by the
<a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>
option in your `php.ini` file.

To complete installation of OCI8, edit `php.ini` and add the line:

    extension=oci8.so

Installing OCI8 as a Statically Compiled Extension when Building PHP
--------------------------------------------------------------------

If you are building PHP from source code, you can configure PHP to
include OCI8 as a static extension using one of the following configure
options.

-   If using Oracle Instant Client, then do:

        ./configure --with-oci8=instantclient,/path/to/instant/client/lib

-   If using an Oracle database or full Oracle Client installation then
    do:

        ./configure --with-oci8=$ORACLE_HOME

After configuration, follow the usual PHP building procedure, e.g. *make
install*. After successful compilation, you do not need to add `oci8.so`
to `php.ini`. No additional build steps are required.

Installing OCI8 on Windows
--------------------------

The OCI8 extension can be added to an existing PHP installation by using
the DLLs from
<a href="https://pecl.php.net/package/oci8" class="link external">» PECL</a>
repository or the libraries in your PHP installation's *ext* directory.

With Oracle 12*c* (or later) libraries, uncomment one of the `php.ini`
lines *extension=php\_oci8\_12c.dll* or *extension=php\_oci8\_11g.dll*
or *extension=php\_oci8.dll*. Only one of these DLLs may be enabled at a
time. DLLs with higher versions may contain more functionality. Not all
DLLs may be available for all versions of PHP. Make sure
<a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>
is set to the directory containing the PHP extension DLLs.

If using Instant Client, set the system `PATH` environment variable to
the Oracle library directory.

Setting the Oracle Environment
------------------------------

Before using this extension, make sure that the Oracle environment
variables are properly set for the web daemon user. If your web server
is automatically started at boot time then make sure that the boot-time
environment is also configured correctly.

> **Note**:
>
> Do not set Oracle environment variables using <span
> class="function">putenv</span> in a PHP script because Oracle
> libraries may be loaded and initialized before your script runs.
> Variables set with <span class="function">putenv</span> may then cause
> conflicts, crashes, or unpredictable behavior. Some functions may work
> but others might give subtle errors. The variables should be set up
> *before* the web server is started.

On Red Hat Linux and variants, export variables at the end of
`/etc/sysconfig/httpd`. Other systems with Apache 2 may use an `envvars`
script in the Apache `bin` directory. A third option, the Apache
*SetEnv* directive in `httpd.conf`, may work in some systems but is
known to be insufficient in others.

To check that environment variables are set correctly, use <span
class="function">phpinfo</span> and check the *Environment* (not the
*Apache Environment*) section contains the expected variables.

The variables that might be needed are included in the following table.
Refer to the Oracle documentation for more information on all the
available variables.

| Name              | Purpose                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ORACLE\_HOME      | Contains the directory of the full Oracle Database software. Do not set this when using Oracle Instant Client as it is unnecessary and may cause installation problems.                                                                                                                                                                                                                                                                                                                  |
| ORACLE\_SID       | Contains the name of the database on the local machine to be connected to. There is no need to set this if you using Oracle Instant Client, or always pass the connection parameter to <span class="function">oci\_connect</span>.                                                                                                                                                                                                                                                       |
| LD\_LIBRARY\_PATH | Set this (or its platform equivalent, such as *LIBPATH*, or *SHLIB\_PATH*) to the location of the Oracle libraries, for example `$ORACLE_HOME/lib` or `/usr/lib/oracle/18.5/client/lib`. Note with Instant Client ZIP files on Linux it is more reliable to use `ldconfig` instead, see the Instant Client installation instructions. With Instant Client 19 (or later) RPM files, *ldconfig* is automatically run for you. Some users use *LD\_PRELOAD* instead of *LD\_LIBRARY\_PATH*. |
| NLS\_LANG         | This is the primary variable for setting the character set and globalization information used by the Oracle libraries.                                                                                                                                                                                                                                                                                                                                                                   |
| ORA\_SDTZ         | Sets the Oracle session timezone.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| TNS\_ADMIN        | Contains the directory where the Oracle Net Services configuration files such as `tnsnames.ora` and `sqlnet.ora` are kept. Not needed if the <span class="function">oci\_connect</span> connection string uses the Easy Connect naming syntax such as *localhost/XE*. Not needed if the network configuration files are in one of the default locations such as `/usr/lib/oracle/VERSION/client/lib/network/admin`, `$ORACLE_HOME/network/admin` or `/etc`.                              |

Less frequently used Oracle environment variables include *TWO\_TASK*,
*ORA\_TZFILE*, and the various Oracle globalization settings like
*NLS\** and the *ORA\_NLS\_\** variables.

Troubleshooting
---------------

The most common problem with installing OCI8 is not having the Oracle
environment correctly set. This typically appears as a problem using
<span class="function">oci\_connect</span> or <span
class="function">oci\_pconnect</span>. The error may be a PHP error such
as *Call to undefined function oci\_connect()*, an Oracle error such as
ORA-12705, or even an Apache crash. Check the Apache log files for
startup errors and see the sections above to resolve this problem.

While network errors like ORA-12154 or ORA-12514 indicate an Oracle
network naming or configuration issue, the root cause may be because the
PHP environment is incorrectly set up and Oracle libraries are unable to
locate the `tnsnames.ora` configuration file.

On Windows, having multiple versions of Oracle on the one machine can
easily cause library clashes unless care is taken to make sure PHP only
uses the correct version of Oracle.

A utility to examine what libraries are being looked for and loaded can
help resolve missing or clashing library issues, particularly on
Windows.

> **Note**: **If the web server doesn't start or crashes at startup**  
>
> Check that Apache is linked with the pthread library:
>
>     # ldd /www/apache/bin/httpd
>       libpthread.so.0 => /lib/libpthread.so.0 (0x4001c000)
>       libm.so.6 => /lib/libm.so.6 (0x4002f000)
>       libcrypt.so.1 => /lib/libcrypt.so.1 (0x4004c000)
>       libdl.so.2 => /lib/libdl.so.2 (0x4007a000)
>       libc.so.6 => /lib/libc.so.6 (0x4007e000)
>       /lib/ld-linux.so.2 => /lib/ld-linux.so.2 (0x40000000)
>
> If the libpthread is not listed, then reinstall Apache:
>
>     # cd /usr/src/apache_1.3.xx
>     # make clean
>     # LIBS=-lpthread ./config.status
>     # make
>     # make install
>
> Please note that on some systems like UnixWare, it is libthread
> instead of libpthread. PHP and Apache have to be configured with
> EXTRA\_LIBS=-lthread.

Testing
-------

The OCI8 test suite is in `ext/oci8/tests`. After OCI8 tests are run
this directory will also contain logs of any failures.

Before running PHP's tests, edit `details.inc` and set $user, $password
and the $dbase connection string. The OCI8 test suite has been developed
using the *SYSTEM* account. Some tests will fail if the test user does
not have equivalent permissions.

If Oracle Database Resident Connection Pooling is being tested, set
$test\_drcp to **`true`** and ensure the connection string uses an
appropriate DRCP pooled server.

An alternative to editing `details.inc` is the set environment
variables, for example:

        $ export PHP_OCI8_TEST_USER=system
        $ export PHP_OCI8_TEST_PASS=oracle
        $ export PHP_OCI8_TEST_DB=localhost/XE
        $ export PHP_OCI8_TEST_DRCP=FALSE

Note in some shells these variables are not propagated correctly to the
PHP process and tests will fail to connect if this method is used.

Next, set any necessary environment for the Oracle database. If you are
running PHP on the same machines as Oracle Database, you can run:

        $ . /usr/local/bin/oraenv

With Oracle 11*g*R2 XE do:

        $ . /u01/app/oracle/product/11.2.0/xe/bin/oracle_env.sh

Some shells require that `php.ini` has *E* in the variables\_order
parameter, for example:

        variables_order = "EGPCS"

Run all the PHP tests with:

        $ cd your_php_src_directory
        $ make test

or run only the OCI8 tests with

        $ cd your_php_src_directory
        $ make test TESTS=ext/oci8

When the tests have completed, review any test failures. On slow
systems, some tests may take longer than the default test timeout in
`run-tests.php`. To correct this, set the environment variable
*TEST\_TIMEOUT* to a larger number of seconds.

On fast machines with a local database configured for light load (e.g.
Oracle 11*g*R2 XE) some tests might fail with ORA-12516 or ORA-12520
errors. To prevent this, increase the database *PROCESSES* parameter
using the following steps:

Connect as the oracle software owner:

        $ su - oracle

Set the necessary Oracle environment with `oracle_env.sh` or `oraenv`,
as described above.

Start the SQL\*Plus command line tool and increase *PROCESSES*

        $ sqlplus / as sysdba
        SQL> alter system set processes=100 scope=spfile

Restart the database:

        SQL> startup force

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                     | Default | Changeable       | Changelog                                  |
|--------------------------------------------------------------------------|---------|------------------|--------------------------------------------|
| <a href="/book/oci8.html#" class="link">oci8.connection_class</a>        | ""      | PHP\_INI\_ALL    | Available since PHP 5.3 (PECL OCI8 1.3).   |
| <a href="/book/oci8.html#" class="link">oci8.default_prefetch</a>        | "100"   | PHP\_INI\_SYSTEM | Available since PHP 5.1.2 (PECL OCI8 1.1). |
| <a href="/book/oci8.html#" class="link">oci8.events</a>                  | Off     | PHP\_INI\_SYSTEM | Available since PHP 5.3 (PECL OCI8 1.3).   |
| <a href="/book/oci8.html#" class="link">oci8.max_persistent</a>          | "-1"    | PHP\_INI\_SYSTEM | Available since PHP 5.1.2 (PECL OCI8 1.1). |
| <a href="/book/oci8.html#" class="link">oci8.old_oci_close_semantics</a> | Off     | PHP\_INI\_SYSTEM | Available since PHP 5.1.2 (PECL OCI8 1.1). |
| <a href="/book/oci8.html#" class="link">oci8.persistent_timeout</a>      | "-1"    | PHP\_INI\_SYSTEM | Available since PHP 5.1.2 (PECL OCI8 1.1). |
| <a href="/book/oci8.html#" class="link">oci8.ping_interval</a>           | "60"    | PHP\_INI\_SYSTEM | Available since PHP 5.1.2 (PECL OCI8 1.1). |
| <a href="/book/oci8.html#" class="link">oci8.privileged_connect</a>      | Off     | PHP\_INI\_SYSTEM | Available since PHP 5.1.2 (PECL OCI8 1.1). |
| <a href="/book/oci8.html#" class="link">oci8.statement_cache_size</a>    | "20"    | PHP\_INI\_SYSTEM | Available since PHP 5.1.2 (PECL OCI8 1.1). |

Here's a short explanation of the configuration directives.

`oci8.connection_class` <span class="type">string</span>  
This user defined text should always be set when using Oracle Database
Resident Connection Pooling (DRCP). It allows sub-partitioning of the
DRCP connection pool, allowing OCI8 persistent connections from an
application to reuse database sessions from a previous PHP script,
giving better scalability. When an application uses a database pooled
process previously used with a different connection class, the session
settings such as the default Oracle date format are reset. This prevents
accidental sharing of information between different applications.

The value can be set at runtime with <span
class="function">ini\_set</span> prior to connecting.

To use DRCP, OCI8 must be linked with Oracle 11*g* (or later) libraries
and the database must be Oracle 11*g* (or later). The DRCP connection
pool must be enabled in the database, the *oci8.connection\_class*
should be set to the same string for all web servers running the same
application, and the OCI8 connection string must specify to use a pooled
server. The application should use persistent connections.

`oci8.default_prefetch` <span class="type">int</span>  
This option sets the default number of extra rows that will be fetched
and cached automatically whenever a low-level request for data from the
database is made. Setting a value of *0* turns off prefetching.

The prefetch value does not alter the number of rows that functions like
<span class="function">oci\_fetch\_array</span> return to the user; the
prefetching and caching of rows is handled internally in OCI8.

The value can be set per-statement with <span
class="function">oci\_set\_prefetch</span> prior to statement execution.

In PHP 5.3 (PECL OCI8 1.3.4) the default value was increased from *10*
to *100*.

In PHP 5.3.2 (PECL OCI8 1.4) the minimum value settable was reduced from
*1* to *0*, allowing prefetching to be turned off.

When using Oracle Database 12*c* (or later), the prefetch value set by
PHP can be overridden by Oracle's client *oraaccess.xml* configuration
file. Refer to Oracle documentation for more detail.

> **Note**: <span class="simpara"> A larger prefetch can result in
> improved performance, at the cost of some increased memory usage. For
> queries that return large amounts of data, the performance benefit can
> be significant. </span>

`oci8.events` <span class="type">bool</span>  
Using *On* allows PHP to be notified of database Fast Application
Notification (FAN) events.

Without FAN, when a database instance or machine node fails
unexpectedly, PHP applications may be blocked waiting for a database
response until a TCP timeout expires. With FAN events, PHP applications
are quickly notified of failures that affect their established database
connections. The OCI8 extension will clean up unusable connections in
the persistent connection cache.

When using *On*, the database must also be configured to post FAN
events.

FAN support is available when OCI8 is linked with Oracle 10*g*R2 (or
later) libraries and connected to Oracle Database 10*g*R2 (or later).

`oci8.max_persistent` <span class="type">int</span>  
The maximum number of persistent OCI8 connections per PHP process.
Setting this option to -1 means that there is no limit.

`oci8.old_oci_close_semantics` <span class="type">bool</span>  
This option controls <span class="function">oci\_close</span> behaviour.
Enabling it means that <span class="function">oci\_close</span> will do
nothing; the connection will not be closed until the end of the script.
This is for backward compatibility only. If you find that you need to
enable this setting, you are *strongly encouraged* to adjust the <span
class="function">oci\_close</span> calls in your application instead of
enabling this option.

`oci8.persistent_timeout` <span class="type">int</span>  
The maximum number of seconds that a PHP process is allowed to keep an
idle persistent connection open. Setting this option to -1 means that
idle persistent connections will be retained until the PHP process
terminates or the connection is explicitly closed with <span
class="function">oci\_close</span>.

> **Note**: <span class="simpara"> In PHP, the expiry of idle resources
> is not alarm-based. It occurs when PHP finishes processing a script
> and checks the last-used timestamp of resources. Hence there is a
> paradox that idle connections can only be closed when there is some
> activity (though not necessarily OCI8 related) in the PHP process. If
> there is more than one PHP process then each must individually be
> activated in order to trigger expiry of its idle resources. The
> introduction of Database Resident Connection Pooling (DRCP) in Oracle
> 11*g* resolves the memory and resource issues that
> *oci8.max\_persistent* and *oci8.persistent\_timeout* previously
> attempted to overcome. </span>

> **Note**: <span class="simpara"> In PHP 5.3 (PECL OCI8 1.3),
> persistent connections can be closed with <span
> class="function">oci\_close</span>. </span>

`oci8.ping_interval` <span class="type">int</span>  
The number of seconds that must pass before issuing a ping during <span
class="function">oci\_pconnect</span>. A ping ensures that the database
connection is valid. When set to 0, persistent connections will be
pinged every time <span class="function">oci\_pconnect</span> is called.
To disable pings completely, set this option to -1.

> **Note**: <span class="simpara"> Disabling pings allows <span
> class="function">oci\_pconnect</span> to operate at the highest
> efficiency, but PHP may not be able to detect unusable connections,
> such as caused by network dropout, or if the Oracle database has gone
> down since PHP connected, until the connection is used later in the
> script. Consult the <span class="function">oci\_pconnect</span>
> documentation for more information. </span>

`oci8.privileged_connect` <span class="type">bool</span>  
This option allows connections to use the privileged external
credentials **`OCI_SYSOPER`** or **`OCI_SYSDBA`**.

> **Note**: <span class="simpara"> Seting this *On* can allow scripts on
> web servers running with the appropriate OS user privileges to connect
> as privileged database users without requiring a database password.
> This can be a security risk. </span>

`oci8.statement_cache_size` <span class="type">int</span>  
This option enables statement caching, and specifies how many statements
to cache. To disable statement caching just set this option to 0.

Statement caching removes the need to transmit the statement text to the
database and removes the need to transmit any meta data about the
statement back to PHP. This can significantly improve overall system
performance in applications which reuse statements during the lifetime
of a connection. Some extra database "cursors" may be held open under
the assumption that statements will be reused.

Set this value to the size of the working set of statements used by your
application. Setting too small a value can cause statements to be
flushed from the cache before they are reused.

This option is of most use with persistent connections.

When using Oracle Database 12*c* (or later), this value can be
overridden and automatically tuned by Oracle's client *oraaccess.xml*
file. Refer to Oracle documentation for more detail.

Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

| Constant                           | Description                                                                                                                                                                                                                                                                                                 |
|------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`OCI_ASSOC`**                    | Used with <span class="function">oci\_fetch\_all</span> and <span class="function">oci\_fetch\_array</span> to get results as an associative array.                                                                                                                                                         |
| **`OCI_BOTH`**                     | Used with <span class="function">oci\_fetch\_all</span> and <span class="function">oci\_fetch\_array</span> to get results as an array with both associative and number indices.                                                                                                                            |
| **`OCI_COMMIT_ON_SUCCESS`**        | Statement execution mode for <span class="function">oci\_execute</span> call. Automatically commit changes when the statement has succeeded.                                                                                                                                                                |
| **`OCI_CRED_EXT`**                 | Used with <span class="function">oci\_connect</span> for using Oracles' External or OS authentication. Introduced in PHP 5.3 and PECL OCI8 1.3.4.                                                                                                                                                           |
| **`OCI_DEFAULT`**                  | See **`OCI_NO_AUTO_COMMIT`**.                                                                                                                                                                                                                                                                               |
| **`OCI_DESCRIBE_ONLY`**            | Statement execution mode for <span class="function">oci\_execute</span>. Use this mode if you want meta data such as the column names but don't want to fetch rows from the query.                                                                                                                          |
| **`OCI_EXACT_FETCH`**              | Obsolete. Statement fetch mode. Used when the application knows in advance exactly how many rows it will be fetching. This mode turns prefetching off for Oracle release 8 or later mode. The cursor is canceled after the desired rows are fetched which may result in reduced server-side resource usage. |
| **`OCI_FETCHSTATEMENT_BY_COLUMN`** | Default mode of <span class="function">oci\_fetch\_all</span>.                                                                                                                                                                                                                                              |
| **`OCI_FETCHSTATEMENT_BY_ROW`**    | Alternative mode of <span class="function">oci\_fetch\_all</span>.                                                                                                                                                                                                                                          |
| **`OCI_LOB_BUFFER_FREE`**          | Used with <a href="/book/oci8.html#OCILob::flush" class="xref"></a> to free buffers used.                                                                                                                                                                                                                   |
| **`OCI_NO_AUTO_COMMIT`**           | Statement execution mode for <span class="function">oci\_execute</span>. The transaction is not automatically committed when using this mode. For readability in new code, use this value instead of the older, equivalent **`OCI_DEFAULT`** constant. Introduced in PHP 5.3.2 (PECL OCI8 1.4).             |
| **`OCI_NUM`**                      | Used with <span class="function">oci\_fetch\_all</span> and <span class="function">oci\_fetch\_array</span> to get results as an enumerated array.                                                                                                                                                          |
| **`OCI_RETURN_LOBS`**              | Used with <span class="function">oci\_fetch\_array</span> to get the data value of the LOB instead of the descriptor.                                                                                                                                                                                       |
| **`OCI_RETURN_NULLS`**             | Used with <span class="function">oci\_fetch\_array</span> to get empty array elements if the row items value is **`null`**.                                                                                                                                                                                 |
| **`OCI_SEEK_CUR`**                 | Used with <a href="/book/oci8.html#OCILob::seek" class="xref"></a> to set the seek position.                                                                                                                                                                                                                |
| **`OCI_SEEK_END`**                 | Used with <a href="/book/oci8.html#OCILob::seek" class="xref"></a> to set the seek position.                                                                                                                                                                                                                |
| **`OCI_SEEK_SET`**                 | Used with <a href="/book/oci8.html#OCILob::seek" class="xref"></a> to set the seek position.                                                                                                                                                                                                                |
| **`OCI_SYSDATE`**                  | Obsolete.                                                                                                                                                                                                                                                                                                   |
| **`OCI_SYSDBA`**                   | Used with <span class="function">oci\_connect</span> to connect with the SYSDBA privilege. The `php.ini` setting <a href="/book/oci8.html#" class="link">oci8.privileged_connect</a> should be enabled to use this.                                                                                         |
| **`OCI_SYSOPER`**                  | Used with <span class="function">oci\_connect</span> to connect with the SYSOPER privilege. The `php.ini` setting <a href="/book/oci8.html#" class="link">oci8.privileged_connect</a> should be enabled to use this.                                                                                        |
| **`OCI_TEMP_BLOB`**                | Used with <a href="/book/oci8.html#OCILob::writeTemporary" class="xref"></a> to indicate that a temporary BLOB should be created.                                                                                                                                                                           |
| **`OCI_TEMP_CLOB`**                | Used with <a href="/book/oci8.html#OCILob::writeTemporary" class="xref"></a> to indicate that a temporary CLOB should be created.                                                                                                                                                                           |

| Constant           | Description                                                                                                                                                      |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`OCI_B_BFILE`**  | Used with <span class="function">oci\_bind\_by\_name</span> when binding BFILEs.                                                                                 |
| **`OCI_B_BIN`**    | Used with <span class="function">oci\_bind\_by\_name</span> to bind RAW values.                                                                                  |
| **`OCI_B_BLOB`**   | Used with <span class="function">oci\_bind\_by\_name</span> when binding BLOBs.                                                                                  |
| **`OCI_B_BOL`**    | Used with <span class="function">oci\_bind\_by\_name</span> to bind a PL/SQL BOOLEAN variable.                                                                   |
| **`OCI_B_CFILEE`** | Used with <span class="function">oci\_bind\_by\_name</span> when binding CFILEs.                                                                                 |
| **`OCI_B_CLOB`**   | Used with <span class="function">oci\_bind\_by\_name</span> when binding CLOBs.                                                                                  |
| **`OCI_B_CURSOR`** | Used with <span class="function">oci\_bind\_by\_name</span> when binding cursors, previously allocated with <span class="function">oci\_new\_descriptor</span>.  |
| **`OCI_B_INT`**    | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of INTEGER.                                                                    |
| **`OCI_B_NTY`**    | Used with <span class="function">oci\_bind\_by\_name</span> when binding named data types. Note: in PHP \< 5.0 it was called **`OCI_B_SQLT_NTY`**.               |
| **`OCI_B_NUM`**    | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of NUMBER.                                                                     |
| **`OCI_B_ROWID`**  | Used with <span class="function">oci\_bind\_by\_name</span> when binding ROWIDs.                                                                                 |
| **`SQLT_AFC`**     | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of CHAR.                                                                       |
| **`SQLT_AVC`**     | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of VARCHAR2.                                                                   |
| **`SQLT_BDOUBLE`** | Not supported.                                                                                                                                                   |
| **`SQLT_BFILEE`**  | The same as **`OCI_B_BFILE`**.                                                                                                                                   |
| **`SQLT_BFLOAT`**  | Not supported.                                                                                                                                                   |
| **`SQLT_BIN`**     | The same as **`OCI_B_BIN`**.                                                                                                                                     |
| **`SQLT_BLOB`**    | The same as **`OCI_B_BLOB`**.                                                                                                                                    |
| **`SQLT_BOL`**     | The same as **`OCI_B_BOL`**.                                                                                                                                     |
| **`SQLT_CFILEE`**  | The same as **`OCI_B_CFILEE`**.                                                                                                                                  |
| **`SQLT_CHR`**     | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of VARCHAR2. Also used with <span class="function">oci\_bind\_by\_name</span>. |
| **`SQLT_CLOB`**    | The same as **`OCI_B_CLOB`**.                                                                                                                                    |
| **`SQLT_FLT`**     | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of FLOAT.                                                                      |
| **`SQLT_INT`**     | The same as **`OCI_B_INT`**.                                                                                                                                     |
| **`SQLT_LBI`**     | Used with <span class="function">oci\_bind\_by\_name</span> to bind LONG RAW values.                                                                             |
| **`SQLT_LNG`**     | Used with <span class="function">oci\_bind\_by\_name</span> to bind LONG values.                                                                                 |
| **`SQLT_LVC`**     | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of LONG VARCHAR.                                                               |
| **`SQLT_NTY`**     | The same as **`OCI_B_NTY`**.                                                                                                                                     |
| **`SQLT_NUM`**     | The same as **`OCI_B_NUM`**.                                                                                                                                     |
| **`SQLT_ODT`**     | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of LONG.                                                                       |
| **`SQLT_RDD`**     | The same as **`OCI_B_ROWID`**.                                                                                                                                   |
| **`SQLT_RSET`**    | The same as **`OCI_B_CURSOR`**.                                                                                                                                  |
| **`SQLT_STR`**     | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of STRING.                                                                     |
| **`SQLT_UIN`**     | Not supported.                                                                                                                                                   |
| **`SQLT_VCS`**     | Used with <span class="function">oci\_bind\_array\_by\_name</span> to bind arrays of VARCHAR.                                                                    |

| Constant              | Description                                                                                              |
|-----------------------|----------------------------------------------------------------------------------------------------------|
| **`OCI_DTYPE_FILE`**  | This flag tells <span class="function">oci\_new\_descriptor</span> to initialize a new FILE descriptor.  |
| **`OCI_DTYPE_LOB`**   | This flag tells <span class="function">oci\_new\_descriptor</span> to initialize a new LOB descriptor.   |
| **`OCI_DTYPE_ROWID`** | This flag tells <span class="function">oci\_new\_descriptor</span> to initialize a new ROWID descriptor. |
| **`OCI_D_FILE`**      | The same as **`OCI_DTYPE_FILE`**.                                                                        |
| **`OCI_D_LOB`**       | The same as **`OCI_DTYPE_LOB`**.                                                                         |
| **`OCI_D_ROWID`**     | The same as **`OCI_DTYPE_ROWID`**.                                                                       |

Examples
========

These examples connect as the *HR* user, which is the sample "Human
Resources" schema supplied with the Oracle database. The account may
need to be unlocked and the password reset before you can use it.

The examples connect to the *XE* database on your machine. Change the
connect string to your database before running the examples.

**Example \#1 Basic query**

This shows querying and displaying results. Statements in OCI8 use a
prepare-execute-fetch sequence of steps.

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

// Prepare the statement
$stid = oci_parse($conn, 'SELECT * FROM departments');
if (!$stid) {
    $e = oci_error($conn);
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

// Perform the logic of the query
$r = oci_execute($stid);
if (!$r) {
    $e = oci_error($stid);
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

// Fetch the results of the query
print "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    print "<tr>\n";
    foreach ($row as $item) {
        print "    <td>" . ($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;") . "</td>\n";
    }
    print "</tr>\n";
}
print "</table>\n";

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 Inserting with bind variables**

Bind variables improve performance by allowing reuse of execution
contexts and caches. Bind variables improve security by preventing some
kinds of SQL Injection problems.

``` php
<?php

// Before running, create the table:
//   CREATE TABLE MYTABLE (mid NUMBER, myd VARCHAR2(20));

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'INSERT INTO MYTABLE (mid, myd) VALUES(:myid, :mydata)');

$id = 60;
$data = 'Some data';

oci_bind_by_name($stid, ':myid', $id);
oci_bind_by_name($stid, ':mydata', $data);

$r = oci_execute($stid);  // executes and commits

if ($r) {
    print "One row inserted";
}

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#3 Binding in the WHERE clause of a query**

This shows a single scalar bind.

``` php
<?php

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$sql = 'SELECT last_name FROM employees WHERE department_id = :didbv ORDER BY last_name';
$stid = oci_parse($conn, $sql);
$didbv = 60;
oci_bind_by_name($stid, ':didbv', $didbv);
oci_execute($stid);
while (($row = oci_fetch_array($stid, OCI_ASSOC)) != false) {
    echo $row['LAST_NAME'] ."<br>\n";
}

// Output is
//    Austin
//    Ernst
//    Hunold
//    Lorentz
//    Pataballa

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#4 Inserting and fetching a CLOB**

For large data use binary long object (BLOB) or character long object
(CLOB) types. This example uses CLOB.

``` php
<?php

// Before running, create the table:
//     CREATE TABLE MYTABLE (mykey NUMBER, myclob CLOB);

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$mykey = 12343;  // arbitrary key for this example;

$sql = "INSERT INTO mytable (mykey, myclob)
        VALUES (:mykey, EMPTY_CLOB())
        RETURNING myclob INTO :myclob";

$stid = oci_parse($conn, $sql);
$clob = oci_new_descriptor($conn, OCI_D_LOB);
oci_bind_by_name($stid, ":mykey", $mykey, 5);
oci_bind_by_name($stid, ":myclob", $clob, -1, OCI_B_CLOB);
oci_execute($stid, OCI_NO_AUTO_COMMIT); // use OCI_DEFAULT for PHP <= 5.3.1
$clob->save("A very long string");

oci_commit($conn);

// Fetching CLOB data

$query = 'SELECT myclob FROM mytable WHERE mykey = :mykey';

$stid = oci_parse ($conn, $query);
oci_bind_by_name($stid, ":mykey", $mykey, 5);
oci_execute($stid);

print '<table border="1">';
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_LOBS)) {
    print '<tr><td>'.$row['MYCLOB'].'</td></tr>';
    // In a loop, freeing the large variable before the 2nd fetch reduces PHP's peak memory usage
    unset($row);  
}
print '</table>';

?>
```

**Example \#5 Using a PL/SQL stored function**

You must bind a variable for the return value and optionally for any
PL/SQL function arguments.

``` php
<?php

/*
  Before running the PHP program, create a stored function in
  SQL*Plus or SQL Developer:

  CREATE OR REPLACE FUNCTION myfunc(p IN NUMBER) RETURN NUMBER AS
  BEGIN
      RETURN p * 3;
  END;

*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$p = 8;

$stid = oci_parse($conn, 'begin :r := myfunc(:p); end;');
oci_bind_by_name($stid, ':p', $p);
oci_bind_by_name($stid, ':r', $r, 40);

oci_execute($stid);

print "$r\n";   // prints 24

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#6 Using a PL/SQL stored procedure**

With stored procedures, you should bind variables for any arguments.

``` php
<?php

/*
  Before running the PHP program, create a stored procedure in
  SQL*Plus or SQL Developer:

  CREATE OR REPLACE PROCEDURE myproc(p1 IN NUMBER, p2 OUT NUMBER) AS
  BEGIN
      p2 := p1 * 2;
  END;

*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$p1 = 8;

$stid = oci_parse($conn, 'begin myproc(:p1, :p2); end;');
oci_bind_by_name($stid, ':p1', $p1);
oci_bind_by_name($stid, ':p2', $p2, 40);

oci_execute($stid);

print "$p2\n";   // prints 16

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#7 Calling a PL/SQL function that returns a *REF CURSOR***

Each returned value from the query is a *REF CURSOR* that can be fetched
from.

``` php
<?php
/*
  Create the PL/SQL stored function as:

  CREATE OR REPLACE FUNCTION myfunc(p1 IN NUMBER) RETURN SYS_REFCURSOR AS
      rc SYS_REFCURSOR;
  BEGIN
      OPEN rc FOR SELECT city FROM locations WHERE ROWNUM < p1;
      RETURN rc;
  END;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'SELECT myfunc(5) AS mfrc FROM dual');
oci_execute($stid);

echo "<table border='1'>\n";
while (($row = oci_fetch_array($stid, OCI_ASSOC))) {
    echo "<tr>\n";
    $rc = $row['MFRC'];
    oci_execute($rc);  // returned column value from the query is a ref cursor
    while (($rc_row = oci_fetch_array($rc, OCI_ASSOC))) {   
        echo "    <td>" . $rc_row['CITY'] . "</td>\n";
    }
    oci_free_statement($rc);
    echo "</tr>\n";
}
echo "</table>\n";

// Output is:
//   Beijing
//   Bern
//   Bombay
//   Geneva

oci_free_statement($stid);
oci_close($conn);

?>
```

OCI8 Connection Handling and Connection Pooling
===============================================

Connection Functions
--------------------

The OCI8 extension provides three different functions for connecting to
Oracle. The standard connection function is <span
class="function">oci\_connect</span>. This creates a connection to an
Oracle database and returns a resource used by subsequent database
calls.

Connecting to an Oracle server is a reasonably expensive operation in
terms of the time that it takes to complete. The <span
class="function">oci\_pconnect</span> function uses a persistent cache
of connections that can be re-used across different script requests.
This means that the connection overhead will typically only occur once
per PHP process (or Apache child).

If the application connects to Oracle using a different set of database
credentials for each web user, the persistent cache employed by <span
class="function">oci\_pconnect</span> will become less useful as the
number of concurrent users increases, to the point where it may start to
adversely affect the overall performance of the Oracle server due to
maintaining too many idle connections. If the application is structured
in this way, it is recommended to either tune the application using the
<a href="/book/oci8.html#" class="link">oci8.max_persistent</a> and
<a href="/book/oci8.html#" class="link">oci8.persistent_timeout</a>
configuration settings (these will give control over the persistent
connection cache size and lifetime), use Oracle Database Resident
Connection Pooling (in Oracle Database 11g or later), or use <span
class="function">oci\_connect</span> instead.

Both <span class="function">oci\_connect</span> and <span
class="function">oci\_pconnect</span> employ a connection cache; if
multiple calls to <span class="function">oci\_connect</span> use the
same parameters in a given script, the second and subsequent calls
return the existing connection handle. The cache used by <span
class="function">oci\_connect</span> is cleaned up at the end of the
script run, or when the connection handle is explicitly closed. The
function <span class="function">oci\_pconnect</span> has similar
behavior, although its cache is maintained separately and survives
between HTTP requests.

This caching feature means the two handles are not transactionally
isolated (they are in fact the same connection handle, so there is no
isolation of any kind). If the application needs two separate,
transactionally isolated connections, then use <span
class="function">oci\_new\_connect</span>.

The <span class="function">oci\_pconnect</span> cache is cleared and any
database connections closed when the PHP process terminates, so
effective use of persistent connections requires that PHP be an Apache
module or used with FPM, or similar. Persistent connections will not
have any benefits over <span class="function">oci\_connect</span> when
PHP is used with CGI or via the command-line.

The function <span class="function">oci\_new\_connect</span> always
creates a new connection to the Oracle server, regardless of what other
connections might already exist. High traffic web applications should
avoid using <span class="function">oci\_new\_connect</span>, especially
in the busiest sections of the application.

From OCI8 1.3, persistent connections can be closed by the user,
allowing greater control over connection resource usage. Persistent
connections will now also be closed automatically when there is no PHP
variable referencing them, such as at the end of scope of a PHP user
function. This will rollback any uncommitted transaction. These changes
to persistent connections make them behave similarly to non-persistent
connections, simplifying the interface, allowing for greater application
consistency and predictability. Use
<a href="/book/oci8.html#" class="link">oci8.old_oci_close_semantics</a>
set to *On* to retain the historical behavior.

The automatic re-establishment of PHP persistent connections after an
Apache or FPM process respawns means Oracle Database *LOGON* triggers
are only recommended for setting session attributes and not for
per-application user connection requests.

DRCP Connection Pooling
-----------------------

PHP from 5.3 (PECL OCI8 1.3) supports Oracle Database Resident
Connection Pooling (DRCP). DRCP allows more efficient use of database
machine memory and provides high scalability. No, or minimal,
application changes are needed to use DRCP.

DRCP is suited for applications that connect using few database schemas
and hold database connections open for a short period of time. Other
applications should use Oracle's default *Dedicated* database server
processes, or use *Shared* servers.

DRCP benefits all three connection functions, but gives the highest
scalability when connections are created with <span
class="function">oci\_pconnect</span>.

For DRCP to be available in OCI8, Oracle client libraries used by PHP
and the version of the Oracle Database must both be 11g or greater.

Documentation on DRCP is found in several Oracle manuals. For example,
see
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-82FF6896-F57E-41CF-89F7-755F3BC9C924" class="link external">» Configuring Database Resident Connection Pooling</a>
in the Oracle documentation for usage information. A
<a href="https://www.oracle.com/technetwork/topics/php/whatsnew/php-scalability-ha-twp-128842.pdf" class="link external">» DRCP white paper</a>
contains background information on DRCP.

To use DRCP, install the OCI8 1.3 (or later) extension and Oracle 11g
(or later) libraries and then follow these steps:

-   As a privileged database administrator, use a program like SQL\*Plus
    to start the connection pool in the database:

            SQL> execute dbms_connection_pool.start_pool;

-   Optionally use *dbms\_connection\_pool.alter\_param()* to configure
    DRCP settings. The current pool settings can be queried from the
    *DBA\_CPOOL\_INFO* view.

-   Update the connection strings used. For PHP applications that
    currently connect using a Network Connect Name like *MYDB*:

            $c = oci_pconnect("myuser", "mypassword", "MYDB");

    modify the tnsnames.ora file and add a *(SERVER=POOLED)* clause, for
    example:

            MYDB = (DESCRIPTION=(ADDRESS=(PROTOCOL=tcp) (HOST=myhost.dom.com)
                   (PORT=1521))(CONNECT_DATA=(SERVICE_NAME=sales)
                   (SERVER=POOLED)))

    Alternatively, modify the Easy Connect syntax in PHP and add
    *:POOLED* after the service name:

            $c = oci_pconnect("myuser", "mypassword", "myhost.dom.com:1521/sales:POOLED");

-   Edit `php.ini` and choose a connection class name. This name
    indicates a logical division of the connection pool and can be used
    to isolate pooling for separate applications. Any PHP applications
    with the same user name and connection class value will be able to
    share connections in the pool, giving greater scalability.

            oci8.connection_class = "MY_APPLICATION_NAME"

-   Run the application, connecting to the 11g (or later) database.

> **Note**:
>
> Applications using Oracle Client libraries 10g that require the
> performance of persistent connections can reduce the amount of
> database server memory needed by using Oracle *Shared* servers
> (previously known as Multi Threaded Servers). Refer to Oracle
> documentation for information.

> **Note**:
>
> Changing a password over DRCP connections will fail with the error
> *ORA-56609: Usage not supported with DRCP*. This is a documented
> restriction of Oracle Database 11g.

OCI8 Fast Application Notification (FAN) Support
================================================

FAN support gives fast connection failover, an Oracle Database high
availability feature. This allows PHP OCI8 scripts to be notified when a
database machine or database instance becomes unavailable. Without FAN,
OCI8 can hang until a TCP timeout occurs and an error is returned, which
might be several minutes. Enabling FAN in OCI8 can allow applications to
detect errors and re-connect to an available database instance without
the web user being aware of an outage.

FAN support is available when the Oracle client libraries that PHP links
with and the Oracle Database are either version 10gR2 or later.

FAN benefits users of Oracle's clustering technology (RAC) because
connections to surviving database instances can be immediately made.
Users of Oracle's Data Guard with a broker will see the FAN events
generated when the standby database goes online. Standalone databases
will send FAN events when the database restarts.

For active connections, when a machine or database instance becomes
unavailable, a connection failure error will be returned by the OCI8
extension function currently being called. On a subsequent PHP script
re-connect, a connection to a surviving database instance will be
established. The OCI8 extension also transparently cleans up any idle
connections affected by a database machine or instance failure so PHP
connect calls will establish a fresh connection without the script being
aware of any service disruption.

When <a href="/book/oci8.html#" class="link">oci8.events</a> is *On*, it
is suggested to set
<a href="/book/oci8.html#" class="link">oci8.ping_interval</a> to -1 to
disable pinging, since enabling FAN events provide pro-active connection
management of idle connections made invalid by a service disruption.

To enable FAN support in PHP OCI8, build PHP OCI8 with Oracle 10gR2 or
later libraries and then follow these steps:

-   <span class="simpara"> As a privileged database administrator, use a
    program like SQL\*Plus to enable the database service to post FAN
    events, for example: </span>
            SQL> execute dbms_service.modify_service(
                           SERVICE_NAME        => 'sales',
                           AQ_HA_NOTIFICATIONS => TRUE);
-   <span class="simpara"> Edit php.ini and add </span>
            oci8.events = On
-   <span class="simpara"> If the application does not already handle
    OCI8 error conditions, modify it to detect failures and take
    appropriate action. This may include re-connecting and re-executing
    statements. </span>
-   <span class="simpara"> Run the application, connecting to Oracle
    Database 10gR2 or later. </span>

OCI8 Transparent Application Failover (TAF) Support
===================================================

TAF is an Oracle Database feature that provides high availability. It
enables PHP OCI8 applications to automatically reconnect to a
preconfigured database when database connectivity fails due to instance
or network failure.

In a configured Oracle Database system, TAF occurs when the PHP
application detects that the database instance is down or unreachable.
It establishes a connection to another node in an Oracle
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-DEF850F6-27E9-428E-B8FC-530230D78AD2" class="link external">» RAC</a>
configuration, a hot standby database, or the same database instance
itself. See
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-F7817CD2-4A2C-4D37-BD36-56DBABD4725F" class="link external">» Oracle Call Interface Programmer's Guide</a>
for more information about OCI TAF.

An application callback can be registered with <span
class="function">oci\_register\_taf\_callback</span>. During failover,
normal application processing stops and the registered callback is
invoked. The callback notifies the application of the failover events.
If the failover succeeds, normal processing will be resumed. If the
failover aborts, any following database operations in the application
will fail due to no connection being available.

When a connection fails over to another database, the callback can reset
any necessary connection state, for example replaying any necessary
ALTER SESSION commands if the database service did not have
-failover\_restore enabled.

An application callback can be removed by calling <span
class="function">oci\_unregister\_taf\_callback</span>.

Configuring Transparent Application Failover
--------------------------------------------

TAF can be configured on the PHP OCI8 side or in the database
configuration. If both are configured, database-side settings take
precedence.

Configure TAF in PHP OCI8 (the client side) by including the
FAILOVER\_MODE parameter in the CONNECT\_DATA portion of a connect
descriptor. See Configuring Transparent Application Failover in
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-8F532535-C401-4B51-BE0B-04FD74BB0621" class="link external">»  Oracle Database Net Services Administrator's Guide</a>
for more information about client side configuration of TAF.

An example tnsnames.ora to configure TAF reconnecting to the same
database instance:

        ORCL =
          (DESCRIPTION =
            (ADDRESS = (PROTOCOL = TCP)(HOST = 127.0.0.1)(PORT = 1521))
            (CONNECT_DATA =
              (SERVICE_NAME = orclpdb1)
              (FAILOVER_MODE =
                (TYPE = SELECT)
                (METHOD = BASIC)
                (RETRIES = 20)
                (DELAY = 15))))
     

Alternatively configure TAF on the database side by modifying the target
service with
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-8DC4D5E0-CA9D-47BC-BAD0-8769405AFEC5" class="link external">» srvctl</a>
(for RAC) or the
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-C11449DC-EEDE-4BB8-9D2C-0A45198C1928" class="link external">»  DBMS_SERVICE.MODIFY_SERVICE</a>
packaged procedure (for single instance databases).

Using TAF Callbacks in OCI8
---------------------------

A TAF callback is an application function that can be registered to be
called during failover. It is called several times while re-establishing
the application's connection.

Callback first occurs when a loss of connection is detected. This allows
the application to act accordingly for the upcoming delay of the
failover. If the failover is successful, the callback is invoked after
connection is re-established and usable. At this time, the application
can resynchronize session settings and take actions such as informing
the user that failover occurred. If failover is unsuccessful, a callback
occurs to inform the application that a failover did not take place and
the connection is unusable.

The interface of a TAF user-defined callback function is as follows:

<span class="type">int</span> <span
class="methodname">userCallbackFn</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">int</span> `$event`</span> , <span
class="methodparam"><span class="type">int</span> `$type`</span> )

`connection`  
The Oracle connection on which the TAF callback was registered via <span
class="function">oci\_register\_taf\_callback</span>. The connection is
not valid until the failover completes successfully.

`event`  
The failover event indicates the current status of the failover.

-   **`OCI_FO_BEGIN`** indicates that failover has detected a lost
    connection and failover is starting.

-   **`OCI_FO_END`** indicates successful completion of failover.

-   **`OCI_FO_ABORT`** indicates that failover was unsuccessful, and
    there is no option of retrying.

-   **`OCI_FO_ERROR`** also indicates that failover was unsuccessful,
    but it gives the application the opportunity to handle the error and
    return OCI\_FO\_RETRY to retry failover.

-   **`OCI_FO_REAUTH`** indicates that an Oracle user has been
    re-authenticated.

`type`  
The failover type. This lets the callback know what type of failover the
application has requested. The usual values are as follows:

-   **`OCI_FO_SESSION`** indicates that the user has requested only
    session failover. For example, if a user's connection is lost, then
    a new session is automatically created for the user on the backup.
    This type of failover does not attempt to recover SELECTs.

-   **`OCI_FO_SELECT`** indicates that the user has requested SELECT
    failover as well. It allows users with open cursors to continue
    fetching from them after failure.

`return value`  
-   **`0`** indicates the failover steps should continue normally.

-   **`OCI_FO_RETRY`** indicates that the failover should be attempted
    again by Oracle. In case of an error while failing over to a new
    connection, TAF is able to retry the failover. Typically, the
    application code should sleep for a while before returning
    OCI\_FO\_RETRY.

The following example registers a TAF callback

``` php
<?php

// Define userspace callback
class MyClass {
    public static $retry_count;
    public static function TAFCallback($conn, $event, $type)
    {
        switch ($event) {
            case OCI_FO_BEGIN:
                printf(" Failing Over ... Please stand by\n");
                printf(" Failover type was found to be %s \n",
                       (($type==OCI_FO_SESSION) ? "SESSION"
                        :(($type==OCI_FO_SELECT) ? "SELECT" : "UNKNOWN!")));
                self::$retry_count = 0;
                break;
            case OCI_FO_ABORT:
                // The application cannot continue using the database
                printf(" Failover aborted. Failover will not take place.\n");
                break;
            case OCI_FO_END:
                // Failover completes successfully. Inform users a failover occurs.
                printf(" Failover ended ... resuming services\n");
                break;
            case OCI_FO_REAUTH:
                printf(" Failed over user ... resuming services\n");
                // Replay any ALTER SESSION commands associated with this connection
                // eg. oci_parse($conn, ‘ALTER SESSION …’) ;
                break;
            case OCI_FO_ERROR:
                // Stop retrying if we have already attempted for 20 times.
                if (self::$retry_count >= 20)
                    return 0;
                printf(" Failover error received. Sleeping...\n");
                sleep(10);
                self::$retry_count++;
                return OCI_FO_RETRY; // retry failover
                break;
            default:
                printf("Bad Failover Event: %d.\n", $event);
                break;
        }
        return 0;
    }
}

$fn_name = 'MyClass::TAFCallback';

$conn = oci_connect('hr', 'welcome', 'orcl');
$sysconn = oci_connect('system', 'oracle', 'orcl');

// Use a privileged connection to construct a SQL statement that will initiate failover
$sql = <<< 'END'
select unique 'alter system disconnect session '''||sid||','||serial#||''''
from v$session_connect_info
where sid = sys_context('USERENV', 'SID')
END;

$s = oci_parse($conn, $sql);
oci_execute($s);
$r = oci_fetch_array($s);
$disconnectssql = $r[0];

oci_register_taf_callback($conn, $fn_name); // Register TAFCallback to Oracle TAF

print("Parsing user query\n");
$sql = "select systimestamp from dual";
$stmt = oci_parse($conn, $sql);

// For example, if a connection loss occurs at this point, oci_execute() will
// detect the loss and failover begins. During failover, oci_execute() will
// invoke the TAF callback function several times. If the failover is successful,
// a new connection is transparently created and oci_execute() will continue as
// usual. The connection session settings can be reset in the TAF callback
// function. If the failover is aborted, oci_execute() will return an error
// because a valid connection is not available.

// Disconnect the user, which initiates failover
print("Disconnecting the user\n");
$discsql = oci_parse($sysconn, $disconnectssql);
oci_execute($discsql);

print("Executing user query\n");
$e = oci_execute($stmt);
if (!$e) {
    $m = oci_error($stmt);
    trigger_error("Could not execute statement: ". $m['message'], E_USER_ERROR);
}
$row = oci_fetch_array($stmt);
print($row[0] . "\n");

// do other SQL statements with the new connection, if it is valid
// $stmt = oci_parse($conn,  . . .);

?>
```

See Also
--------

-   <span class="function">oci\_register\_taf\_callback</span>
-   <span class="function">oci\_unregister\_taf\_callback</span>

OCI8 and DTrace Dynamic Tracing
===============================

OCI8 2.0 introduced static DTrace probes that can be used on operating
systems that support DTrace. See
<a href="/features/dtrace.html" class="link">DTrace Dynamic Tracing</a>
for an overview of PHP and DTrace.

Installing OCI8 with DTrace Support
-----------------------------------

To enable DTrace support in PHP OCI8, build OCI8 as a shared extension
after setting *PHP\_DTRACE*.

    $ export PHP_DTRACE=yes
    $ pecl install oci8

Edit php.ini, set
<a href="/ini/core.html#ini.extension-dir" class="link">extension_dir</a>
to the directory with the created `oci8.so` and also enable the
extension by adding:

    extension=oci8.so

If you install PHP OCI8 from PECL using `phpize` and `configure`
(instead of `pecl`), you will still need to set *PHP\_DTRACE=yes*. This
is because the *--enable-dtrace* option will be ignored by the limited
`configure` script of a PECL bundle.

See
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>
for general PECL installation instructions.

DTrace Static Probes in PHP OCI8
--------------------------------

| Probe Name              | Probe Description                                                                                                      | Probe Arguments                                                                                              |
|-------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| *oci8-connect-entry*    | Initiated by oci\_connect(), oci\_pconnect() and oci\_new\_connect(). Fires before database connection is established. | char \*`username`, char \*`dbname`, char \*`charset`, long `session_mode`, int `persistent`, int `exclusive` |
| *oci8-connect-return*   | Fires at the end of connection.                                                                                        | void \*`connection`                                                                                          |
| *oci8-check-connection* | Fires if an Oracle error might have caused the connection to become invalid.                                           | void \*`connection`, char \*`client_id`, int `is_open`, long `errcode`, unsigned long `server_status`        |
| *oci8-sqltext*          | Fires when oci\_parse() is executed.                                                                                   | void \*`connection`, char \*`client_id`, void \*`statement`, char \*`sql`                                    |
| *oci8-connection-close* | Fires when the connection to the database is completely destroyed.                                                     | void \*`connection`                                                                                          |
| *oci8-error*            | Fires if an Oracle error occurs.                                                                                       | int `status`, long `errcode`                                                                                 |
| *oci8-execute-mode*     | Fires at <span class="function">oci\_execute</span> to show the execution mode.                                        | void \*`connection`, char \*`client_id`, void \*`statement`, unsigned int `mode`                             |

These probes are useful for tracing OCI8 scripts.

The `connection` and `statement` are the pointers to internal structures
used for tracking PHP connections and executed statements.

The `client_id` is the value set by <span
class="function">oci\_set\_client\_identifier</span>.

Core PHP also has static probes. See
<a href="/features/dtrace/dtrace.html#features.dtrace.static-probes" class="link">DTrace Static Probes in Core PHP</a>.

| Probe Name                    |
|-------------------------------|
| *oci8-connect-expiry*         |
| *oci8-connect-lookup*         |
| *oci8-connect-p-dtor-close*   |
| *oci8-connect-p-dtor-release* |
| *oci8-connect-type*           |
| *oci8-sesspool-create*        |
| *oci8-sesspool-stats*         |
| *oci8-sesspool-type*          |

These probes are useful for OCI8 maintainers. Refer to the OCI8 source
code for arguments and to see when the will fire.

Listing DTrace Static Probes in PHP OCI8
----------------------------------------

To list available probes, start a PHP process and then run:

    # dtrace -l

The output will be similar to:

       ID   PROVIDER            MODULE                          FUNCTION NAME
       [ . . . ]
       17 phpoci22116           oci8.so   php_oci_dtrace_check_connection oci8-check-connection
       18 phpoci22116           oci8.so                php_oci_do_connect oci8-connect-entry
       19 phpoci22116           oci8.so         php_oci_persistent_helper oci8-connect-expiry
       20 phpoci22116           oci8.so             php_oci_do_connect_ex oci8-connect-lookup
       21 phpoci22116           oci8.so  php_oci_pconnection_list_np_dtor oci8-connect-p-dtor-close
       22 phpoci22116           oci8.so  php_oci_pconnection_list_np_dtor oci8-connect-p-dtor-release
       23 phpoci22116           oci8.so                php_oci_do_connect oci8-connect-return
       24 phpoci22116           oci8.so             php_oci_do_connect_ex oci8-connect-type
       25 phpoci22116           oci8.so          php_oci_connection_close oci8-connection-close
       26 phpoci22116           oci8.so                     php_oci_error oci8-error
       27 phpoci22116           oci8.so         php_oci_statement_execute oci8-execute-mode
       28 phpoci22116           oci8.so              php_oci_create_spool oci8-sesspool-create
       29 phpoci22116           oci8.so            php_oci_create_session oci8-sesspool-stats
       30 phpoci22116           oci8.so            php_oci_create_session oci8-sesspool-type
       31 phpoci22116           oci8.so          php_oci_statement_create oci8-sqltext

The Provider column values consist of *phpoci* and the process id of the
currently running PHP process.

The Function column refers to PHP's internal C implementation function
names where each provider is located.

If a PHP process is not running, then no PHP probes will be shown.

DTrace with PHP OCI8 Example
----------------------------

This example shows the basics of the DTrace D scripting language.

**Example \#1 `user_oci8_probes.d` for tracing all user-level PHP OCI8
Static Probes with DTrace**

    #!/usr/sbin/dtrace -Zs

    #pragma D option quiet

    php*:::oci8-connect-entry
    {
        printf("%lld: PHP connect-entry\n", walltimestamp);
        printf("  credentials=\"%s@%s\"\n", arg0 ? copyinstr(arg0) : "", arg1 ? copyinstr(arg1) : "");
        printf("  charset=\"%s\"\n", arg2 ? copyinstr(arg2) : "");
        printf("  session_mode=%ld\n", (long)arg3);
        printf("  persistent=%d\n", (int)arg4);
        printf("  exclusive=%d\n", (int)arg5);
    }

    php*:::oci8-connect-return
    {
        printf("%lld: PHP oci8-connect-return\n", walltimestamp);
        printf("  connection=0x%p\n", (void *)arg0);
    }

    php*:::oci8-connection-close
    {
        printf("%lld: PHP oci8-connect-close\n", walltimestamp);
        printf("  connection=0x%p\n", (void *)arg0);
    }

    php*:::oci8-error
    {
        printf("%lld: PHP oci8-error\n", walltimestamp);
        printf("  status=%d\n", (int)arg0);
        printf("  errcode=%ld\n", (long)arg1);
    }

    php*:::oci8-check-connection
    {
        printf("%lld: PHP oci8-check-connection\n", walltimestamp);
        printf("  connection=0x%p\n", (void *)arg0);
        printf("  client_id=\"%s\"\n", arg1 ? copyinstr(arg1) : "");
        printf("  is_open=%d\n", arg2);
        printf("  errcode=%ld\n", (long)arg3);
        printf("  server_status=%lu\n", (unsigned long)arg4);
    }

    php*:::oci8-sqltext
    {
        printf("%lld: PHP oci8-sqltext\n", walltimestamp);
        printf("  connection=0x%p\n", (void *)arg0);
        printf("  client_id=\"%s\"\n", arg1 ? copyinstr(arg1) : "");
        printf("  statement=0x%p\n", (void *)arg2);
        printf("  sql=\"%s\"\n", arg3 ? copyinstr(arg3) : "");
    }

    php*:::oci8-execute-mode
    {
        printf("%lld: PHP oci8-execute-mode\n", walltimestamp);
        printf("  connection=0x%p\n", (void *)arg0);
        printf("  client_id=\"%s\"\n", arg1 ? copyinstr(arg1) : "");
        printf("  statement=0x%p\n", (void *)arg2);
        printf("  mode=0x%x\n", arg3);
    }

This script uses the *-Z* option to `dtrace`, allowing it to be run when
there is no PHP process executing. If this option were omitted the
script would immediately terminate when no PHP executable was running
because it knows none of the probes to be monitored are in existence.

On multi-CPU machines the probe ordering might not appear to be
sequential. This depends on which CPU was processing the probes, and how
threads migrate across CPUs. Displaying probe time stamps helps reduce
confusion.

The script traces all user-level PHP OCI8 static probe points throughout
the duration of a running PHP script. Run the D script:

    # ./user_oci8_probes.d

Run a PHP script or application. The monitoring D script will output
each probe's arguments as it fires. For example, a simple PHP script
that queries a table might produce the following trace output:

    1381794982092854582: PHP connect-entry
      credentials="hr@localhost/pdborcl"
      charset=""
      session_mode=0
      persistent=0
      exclusive=0
    1381794982183158766: PHP oci8-connect-return
      connection=0x7f4a7907bfb8
    1381794982183594576: PHP oci8-sqltext
      connection=0x7f4a7907bfb8
      client_id="Chris"
      statement=0x7f4a7907c2a0
      sql="select * from employees"
    1381794982183783706: PHP oci8-execute-mode
      connection=0x7f4a7907bfb8
      client_id="Chris"
      statement=0x7f4a7907c2a0
      mode=0x20
    1381794982444344390: PHP oci8-connect-close
      connection=0x7f4a7907bfb8

When monitoring is complete, the D script can be terminated with a *^C*.

See Also
--------

-   <a href="/features/dtrace.html" class="link">DTrace Dynamic Tracing</a>

Supported Datatypes
===================

| Type                              | Mapping                                                                                                                                      |
|-----------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **`SQLT_NTY`**                    | Maps a native collection type from a PHP collection object, such as those created by <span class="function">oci\_new\_collection</span>.     |
| **`SQLT_BFILEE`**                 | Maps a native descriptor, such as those created by <span class="function">oci\_new\_descriptor</span>.                                       |
| **`SQLT_CFILEE`**                 | Maps a native descriptor, such as those created by <span class="function">oci\_new\_descriptor</span>.                                       |
| **`SQLT_CLOB`**                   | Maps a native descriptor, such as those created by <span class="function">oci\_new\_descriptor</span>.                                       |
| **`SQLT_BLOB`**                   | Maps a native descriptor, such as those created by <span class="function">oci\_new\_descriptor</span>.                                       |
| **`SQLT_RDD`**                    | Maps a native descriptor, such as those created by <span class="function">oci\_new\_descriptor</span>.                                       |
| **`SQLT_NUM`**                    | Converts the PHP parameter to a 'C' long type, and binds to that value.                                                                      |
| **`SQLT_RSET`**                   | Maps a native statement handle, such as those created by <span class="function">oci\_parse</span> or those retrieved from other OCI queries. |
| **`SQLT_BOL`**                    | Bind the PHP parameter to a PL/SQL BOOLEAN                                                                                                   |
| **`SQLT_CHR`** and any other type | Converts the PHP parameter to a string type and binds as a string.                                                                           |

| Type             | Mapping                                                    |
|------------------|------------------------------------------------------------|
| **`SQLT_RSET`**  | Creates an oci statement resource to represent the cursor. |
| **`SQLT_RDD`**   | Creates a ROWID object.                                    |
| **`SQLT_BLOB`**  | Creates a LOB object.                                      |
| **`SQLT_CLOB`**  | Creates a LOB object.                                      |
| **`SQLT_BFILE`** | Creates a LOB object.                                      |
| **`SQLT_LNG`**   | Bound as SQLT\_CHR, returned as a string                   |
| **`SQLT_LBI`**   | Bound as **`SQLT_BIN`**, returned as a string              |
| Any other type   | Bound as **`SQLT_CHR`**, returned as a string              |

oci\_bind\_array\_by\_name
==========================

Binds a PHP array to an Oracle PL/SQL array parameter

### Description

<span class="type">bool</span> <span
class="methodname">oci\_bind\_array\_by\_name</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">array</span> `&$var_array`</span>
, <span class="methodparam"><span class="type">int</span>
`$max_table_length`</span> \[, <span class="methodparam"><span
class="type">int</span> `$max_item_length`<span class="initializer"> =
-1</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$type`<span class="initializer"> =
SQLT\_AFC</span></span> \]\] )

Binds the PHP array `var_array` to the Oracle placeholder `name`, which
points to an Oracle PL/SQL array. Whether it will be used for input or
output will be determined at run-time.

### Parameters

`statement`  
A valid OCI statement identifier.

`name`  
The Oracle placeholder.

`var_array`  
An array.

`max_table_length`  
Sets the maximum length both for incoming and result arrays.

`max_item_length`  
Sets maximum length for array items. If not specified or equals to -1,
<span class="function">oci\_bind\_array\_by\_name</span> will find the
longest element in the incoming array and will use it as the maximum
length.

`type`  
Should be used to set the type of PL/SQL array items. See list of
available types below:

-   **`SQLT_NUM`** - for arrays of NUMBER.

-   **`SQLT_INT`** - for arrays of INTEGER (Note: INTEGER it is actually
    a synonym for NUMBER(38), but **`SQLT_NUM`** type won't work in this
    case even though they are synonyms).

-   **`SQLT_FLT`** - for arrays of FLOAT.

-   **`SQLT_AFC`** - for arrays of CHAR.

-   **`SQLT_CHR`** - for arrays of VARCHAR2.

-   **`SQLT_VCS`** - for arrays of VARCHAR.

-   **`SQLT_AVC`** - for arrays of CHARZ.

-   **`SQLT_STR`** - for arrays of STRING.

-   **`SQLT_LVC`** - for arrays of LONG VARCHAR.

-   **`SQLT_ODT`** - for arrays of DATE.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">oci\_bind\_array\_by\_name</span>
example**

``` php
<?php

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$create = "CREATE TABLE bind_example(name VARCHAR(20))";
$stid = oci_parse($conn, $create);
oci_execute($stid);

$create_pkg = "
CREATE OR REPLACE PACKAGE ARRAYBINDPKG1 AS
  TYPE ARRTYPE IS TABLE OF VARCHAR(20) INDEX BY BINARY_INTEGER;
  PROCEDURE iobind(c1 IN OUT ARRTYPE);
END ARRAYBINDPKG1;";
$stid = oci_parse($conn, $create_pkg);
oci_execute($stid);

$create_pkg_body = "
CREATE OR REPLACE PACKAGE BODY ARRAYBINDPKG1 AS
  CURSOR CUR IS SELECT name FROM bind_example;
  PROCEDURE iobind(c1 IN OUT ARRTYPE) IS
    BEGIN
    -- Bulk Insert
    FORALL i IN INDICES OF c1
      INSERT INTO bind_example VALUES (c1(i));

    -- Fetch and reverse
    IF NOT CUR%ISOPEN THEN
      OPEN CUR;
    END IF;
    FOR i IN REVERSE 1..5 LOOP
      FETCH CUR INTO c1(i);
      IF CUR%NOTFOUND THEN
        CLOSE CUR;
        EXIT;
      END IF;
    END LOOP;
  END iobind;
END ARRAYBINDPKG1;";
$stid = oci_parse($conn, $create_pkg_body);
oci_execute($stid);

$stid = oci_parse($conn, "BEGIN arraybindpkg1.iobind(:c1); END;");
$array = array("one", "two", "three", "four", "five");
oci_bind_array_by_name($stid, ":c1", $array, 5, -1, SQLT_CHR);
oci_execute($stid);

var_dump($array);

?>
```

oci\_bind\_by\_name
===================

Binds a PHP variable to an Oracle placeholder

### Description

<span class="type">bool</span> <span
class="methodname">oci\_bind\_by\_name</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">string</span> `$bv_name`</span> , <span
class="methodparam"><span class="type">mixed</span> `&$variable`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$maxlength`<span class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = SQLT\_CHR</span></span> \]\] )

Binds a PHP variable `variable` to the Oracle bind variable placeholder
`bv_name`. Binding is important for Oracle database performance and also
as a way to avoid SQL Injection security issues.

Binding allows the database to reuse the statement context and caches
from previous executions of the statement, even if another user or
process originally executed it. Binding reduces SQL Injection concerns
because the data associated with a bind variable is never treated as
part of the SQL statement. It does not need quoting or escaping.

PHP variables that have been bound can be changed and the statement
re-executed without needing to re-parse the statement or re-bind.

In Oracle, bind variables are commonly divided into *IN* binds for
values that are passed into the database, and *OUT* binds for values
that are returned to PHP. A bind variable may be both *IN* and *OUT*.
Whether a bind variable will be used for input or output is determined
at run-time.

You must specify `maxlength` when using an *OUT* bind so that PHP
allocates enough memory to hold the returned value.

For *IN* binds it is recommended to set the `maxlength` length if the
statement is re-executed multiple times with different values for the
PHP variable. Otherwise Oracle may truncate data to the length of the
initial PHP variable value. If you don't know what the maximum length
will be, then re-call <span class="function">oci\_bind\_by\_name</span>
with the current data size prior to each <span
class="function">oci\_execute</span> call. Binding an unnecessarily
large length will have an impact on process memory in the database.

A bind call tells Oracle which memory address to read data from. For
*IN* binds that address needs to contain valid data when <span
class="function">oci\_execute</span> is called. This means that the
variable bound must remain in scope until execution. If it doesn't,
unexpected results or errors such as "ORA-01460: unimplemented or
unreasonable conversion requested" may occur. For *OUT* binds one
symptom is no value being set in the PHP variable.

For a statement that is repeatedly executed, binding values that never
change may reduce the ability of the Oracle optimizer to choose the best
statement execution plan. Long running statements that are rarely
re-executed may not benefit from binding. However in both cases, binding
might be safer than joining strings into a SQL statement, as this can be
a security risk if unfiltered user text is concatenated.

### Parameters

`statement`  
A valid OCI8 statement identifer.

`bv_name`  
The colon-prefixed bind variable placeholder used in the statement. The
colon is optional in `bv_name`. Oracle does not use question marks for
placeholders.

`variable`  
The PHP variable to be associated with `bv_name`

`maxlength`  
Sets the maximum length for the data. If you set it to -1, this function
will use the current length of `variable` to set the maximum length. In
this case the `variable` must exist and contain data when <span
class="function">oci\_bind\_by\_name</span> is called.

`type`  
The datatype that Oracle will treat the data as. The default `type` used
is **`SQLT_CHR`**. Oracle will convert the data between this type and
the database column (or PL/SQL variable type), when possible.

If you need to bind an abstract datatype (LOB/ROWID/BFILE) you need to
allocate it first using the <span
class="function">oci\_new\_descriptor</span> function. The `length` is
not used for abstract datatypes and should be set to -1.

Possible values for `type` are:

-   **`SQLT_BFILEE`** or **`OCI_B_BFILE`** - for BFILEs;

-   **`SQLT_CFILEE`** or **`OCI_B_CFILEE`** - for CFILEs;

-   **`SQLT_CLOB`** or **`OCI_B_CLOB`** - for CLOBs;

-   **`SQLT_BLOB`** or **`OCI_B_BLOB`** - for BLOBs;

-   **`SQLT_RDD`** or **`OCI_B_ROWID`** - for ROWIDs;

-   **`SQLT_NTY`** or **`OCI_B_NTY`** - for named datatypes;

-   **`SQLT_INT`** or **`OCI_B_INT`** - for integers;

-   **`SQLT_CHR`** - for VARCHARs;

-   **`SQLT_BIN`** or **`OCI_B_BIN`** - for RAW columns;

-   **`SQLT_LNG`** - for LONG columns;

-   **`SQLT_LBI`** - for LONG RAW columns;

-   **`SQLT_RSET`** - for cursors created with <span
    class="function">oci\_new\_cursor</span>;

-   **`SQLT_BOL`** or **`OCI_B_BOL`** - for PL/SQL BOOLEANs (Requires
    OCI8 2.0.7 and Oracle Database 12c)

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Inserting data with <span
class="function">oci\_bind\_by\_name</span>**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (id NUMBER, text VARCHAR2(40));

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn,"INSERT INTO mytab (id, text) VALUES(:id_bv, :text_bv)");

$id = 1;
$text = "Data to insert     ";
oci_bind_by_name($stid, ":id_bv", $id);
oci_bind_by_name($stid, ":text_bv", $text);
oci_execute($stid);

// Table now contains: 1, 'Data to insert     '

?>
```

**Example \#2 Binding once for multiple executions**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (id NUMBER);

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$a = array(1,3,5,7,11);  // data to insert

$stid = oci_parse($conn, 'INSERT INTO mytab (id) VALUES (:bv)');
oci_bind_by_name($stid, ':bv', $v, 20);
foreach ($a as $v) {
    $r = oci_execute($stid, OCI_DEFAULT);  // don't auto commit
}
oci_commit($conn); // commit everything at once

// Table contains five rows: 1, 3, 5, 7, 11

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#3 Binding with a <span class="function">foreach</span>
loop**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$sql = 'SELECT * FROM departments WHERE department_name = :dname AND location_id = :loc';
$stid = oci_parse($conn, $sql);

$ba = array(':dname' => 'IT Support', ':loc' => 1700);

foreach ($ba as $key => $val) {

    // oci_bind_by_name($stid, $key, $val) does not work
    // because it binds each placeholder to the same location: $val
    // instead use the actual location of the data: $ba[$key]
    oci_bind_by_name($stid, $key, $ba[$key]);
}

oci_execute($stid);
$row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS);
foreach ($row as $item) {
    print $item."<br>\n";
}

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#4 Binding in a WHERE clause**

``` php
<?php

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$sql = 'SELECT last_name FROM employees WHERE department_id = :didbv ORDER BY last_name';
$stid = oci_parse($conn, $sql);
$didbv = 60;
oci_bind_by_name($stid, ':didbv', $didbv);
oci_execute($stid);
while (($row = oci_fetch_array($stid, OCI_ASSOC)) != false) {
    echo $row['LAST_NAME'] ."<br>\n";
}

// Output is
//    Austin
//    Ernst
//    Hunold
//    Lorentz
//    Pataballa

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#5 Binding with a LIKE clause**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

// Find all cities that begin with 'South'
$stid = oci_parse($conn, "SELECT city FROM locations WHERE city LIKE :bv");
$city = 'South%';  // '%' is a wildcard in SQL
oci_bind_by_name($stid, ":bv", $city);
oci_execute($stid);
oci_fetch_all($stid, $res);

foreach ($res['CITY'] as $c) {
    print $c . "<br>\n";
}
// Output is
//   South Brunswick
//   South San Francisco
//   Southlake

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#6 Binding with REGEXP\_LIKE**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

// Find all cities that contain 'ing'
$stid = oci_parse($conn, "SELECT city FROM locations WHERE REGEXP_LIKE(city, :bv)");
$city = '.*ing.*';
oci_bind_by_name($stid, ":bv", $city);
oci_execute($stid);
oci_fetch_all($stid, $res);

foreach ($res['CITY'] as $c) {
    print $c . "<br>\n";
}
// Output is
//   Beijing
//   Singapore

oci_free_statement($stid);
oci_close($conn);

?>
```

For a small, fixed number of IN clause conditions, use individual bind
variables. Values unknown at run time can be set to NULL. This allows a
single statement to be used by all application users, maximizing Oracle
DB cache efficiency.

**Example \#7 Binding Multiple Values in an IN Clause**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$sql = 'SELECT last_name FROM employees WHERE employee_id in (:e1, :e2, :e3)';
$stid = oci_parse($conn, $sql);
$mye1 = 103;
$mye2 = 104;
$mye3 = NULL; // pretend we were not given this value
oci_bind_by_name($stid, ':e1', $mye1);
oci_bind_by_name($stid, ':e2', $mye2);
oci_bind_by_name($stid, ':e3', $mye3);
oci_execute($stid);
oci_fetch_all($stid, $res);
foreach ($res['LAST_NAME'] as $name) {
    print $name ."<br>\n";
}

// Output is
//   Ernst
//   Hunold

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#8 Binding a ROWID returned by a query**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (id NUMBER, salary NUMBER, name VARCHAR2(40));
//   INSERT INTO mytab (id, salary, name) VALUES (1, 100, 'Chris');
//   COMMIT;

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT ROWID, name FROM mytab WHERE id = :id_bv FOR UPDATE');
$id = 1;
oci_bind_by_name($stid, ':id_bv', $id);
oci_execute($stid);
$row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS);
$rid = $row['ROWID'];
$name = $row['NAME'];

// Change name to upper case & save the changes
$name = strtoupper($name);
$stid = oci_parse($conn, 'UPDATE mytab SET name = :n_bv WHERE ROWID = :r_bv');
oci_bind_by_name($stid, ':n_bv', $name);
oci_bind_by_name($stid, ':r_bv', $rid, -1, OCI_B_ROWID);
oci_execute($stid);

// The table now contains 1, 100, CHRIS

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#9 Binding a ROWID on INSERT**

``` php
<?php

// This example inserts an id & name, and then updates the salary
// Create the table with:
//   CREATE TABLE mytab (id NUMBER, salary NUMBER, name VARCHAR2(40));
//
// Based on original ROWID example by thies at thieso dot net (980221)

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$sql = "INSERT INTO mytab (id, name) VALUES(:id_bv, :name_bv)
        RETURNING ROWID INTO :rid";

$ins_stid = oci_parse($conn, $sql);

$rowid = oci_new_descriptor($conn, OCI_D_ROWID);
oci_bind_by_name($ins_stid, ":id_bv",   $id,    10);
oci_bind_by_name($ins_stid, ":name_bv", $name,  32);
oci_bind_by_name($ins_stid, ":rid",     $rowid, -1, OCI_B_ROWID);

$sql = "UPDATE mytab SET salary = :salary WHERE ROWID = :rid";
$upd_stid = oci_parse($conn, $sql);
oci_bind_by_name($upd_stid, ":rid", $rowid, -1, OCI_B_ROWID);
oci_bind_by_name($upd_stid, ":salary", $salary,   32);

// ids and names to insert
$data = array(1111 => "Larry",
              2222 => "Bill",
              3333 => "Jim");

// Salary of each person
$salary = 10000;

// Insert and immediately update each row
foreach ($data as $id => $name) {
    oci_execute($ins_stid);
    oci_execute($upd_stid);
}

$rowid->free();
oci_free_statement($upd_stid);
oci_free_statement($ins_stid);

// Show the new rows
$stid = oci_parse($conn, "SELECT * FROM mytab");
oci_execute($stid);
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    var_dump($row);
}

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#10 Binding for a PL/SQL stored function**

``` php
<?php

//  Before running the PHP program, create a stored function in
//  SQL*Plus or SQL Developer:
//
//  CREATE OR REPLACE FUNCTION myfunc(p IN NUMBER) RETURN NUMBER AS
//  BEGIN
//      RETURN p * 3;
//  END;

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

$p = 8;

$stid = oci_parse($conn, 'begin :r := myfunc(:p); end;');
oci_bind_by_name($stid, ':p', $p);

// The return value is an OUT bind. The default type will be a string
// type so binding a length 40 means that at most 40 digits will be
// returned.
oci_bind_by_name($stid, ':r', $r, 40);

oci_execute($stid);

print "$r\n";   // prints 24

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#11 Binding parameters for a PL/SQL stored procedure**

``` php
<?php

//  Before running the PHP program, create a stored procedure in
//  SQL*Plus or SQL Developer:
//
//  CREATE OR REPLACE PROCEDURE myproc(p1 IN NUMBER, p2 OUT NUMBER) AS
//  BEGIN
//      p2 := p1 * 2;
//  END;

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

$p1 = 8;

$stid = oci_parse($conn, 'begin myproc(:p1, :p2); end;');
oci_bind_by_name($stid, ':p1', $p1);

// The second procedure parameter is an OUT bind. The default type
// will be a string type so binding a length 40 means that at most 40
// digits will be returned.
oci_bind_by_name($stid, ':p2', $p2, 40);

oci_execute($stid);

print "$p2\n";   // prints 16

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#12 Binding a CLOB column**

``` php
<?php

// Before running, create the table:
//     CREATE TABLE mytab (mykey NUMBER, myclob CLOB);

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

$mykey = 12343;  // arbitrary key for this example;

$sql = "INSERT INTO mytab (mykey, myclob)
        VALUES (:mykey, EMPTY_CLOB())
        RETURNING myclob INTO :myclob";

$stid = oci_parse($conn, $sql);
$clob = oci_new_descriptor($conn, OCI_D_LOB);
oci_bind_by_name($stid, ":mykey", $mykey, 5);
oci_bind_by_name($stid, ":myclob", $clob, -1, OCI_B_CLOB);
oci_execute($stid, OCI_DEFAULT);
$clob->save("A very long string");

oci_commit($conn);

// Fetching CLOB data

$query = 'SELECT myclob FROM mytab WHERE mykey = :mykey';

$stid = oci_parse ($conn, $query);
oci_bind_by_name($stid, ":mykey", $mykey, 5);
oci_execute($stid);

print '<table border="1">';
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_LOBS)) {
    print '<tr><td>'.$row['MYCLOB'].'</td></tr>';
    // In a loop, freeing the large variable before the 2nd fetch reduces PHP's peak memory usage
    unset($row);  
}
print '</table>';

?>
```

**Example \#13 Binding a PL/SQL BOOLEAN**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

$plsql = 
  "begin
    :output1 := true;
    :output2 := false;
   end;";

$s = oci_parse($c, $plsql);
oci_bind_by_name($s, ':output1', $output1, -1, OCI_B_BOL);
oci_bind_by_name($s, ':output2', $output2, -1, OCI_B_BOL);
oci_execute($s);
var_dump($output1);  // true
var_dump($output2);  // false

?>
```

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Notes

**Warning**

Do not use <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>
or <span class="function">addslashes</span> and <span
class="function">oci\_bind\_by\_name</span> simultaneously as no quoting
is needed. Any magically applied quotes will be written into your
database because <span class="function">oci\_bind\_by\_name</span>
inserts data verbatim and does not remove quotes or escape characters.

> **Note**:
>
> If you bind a string to a *CHAR* column in a *WHERE* clause, remember
> that Oracle uses blank-padded comparison semantics for *CHAR* columns.
> Your PHP variable should be blank padded to the same width as the
> column for the *WHERE* clause to succeed.

> **Note**:
>
> The PHP `variable` argument is a reference. Some forms of loops do not
> work as expected:
>
> ``` php
> <?php
> foreach ($myarray as $key => $value)  {
>     oci_bind_by_name($stid, $key, $value);
> }
> ?>
> ```
>
> This binds each key to the location of $value, so all bound variables
> end up pointing to the last loop iteration's value. Instead use the
> following:
>
> ``` php
> <?php
> foreach ($myarray as $key => $value) {
>     oci_bind_by_name($stid, $key, $myarray[$key]);
> }
> ?>
> ```

### See Also

-   <span class="function">oci\_bind\_array\_by\_name</span>
-   <span class="function">oci\_parse</span>

oci\_cancel
===========

Cancels reading from cursor

### Description

<span class="type">bool</span> <span
class="methodname">oci\_cancel</span> ( <span class="methodparam"><span
class="type">resource</span> `$statement`</span> )

Invalidates a cursor, freeing all associated resources and cancels the
ability to read from it.

### Parameters

`statement`  
An OCI statement.

### Return Values

Returns **`true`** on success or **`false`** on failure.

oci\_client\_version
====================

Returns the Oracle client library version

### Description

<span class="type">string</span> <span
class="methodname">oci\_client\_version</span> ( <span
class="methodparam">void</span> )

Returns a string containing the version number of the Oracle C client
library that PHP is linked with.

### Parameters

None

### Return Values

Returns the version number as a string.

### Examples

**Example \#1 <span class="function">oci\_client\_version</span>
example**

``` php
<?php
    echo "Client Version: " . oci_client_version(); // Client version: 19.9.0.0.0
?>
```

### Notes

> **Note**:
>
> Oracle libraries before 10*g*R2 do not have the underlying
> functionality to get the client library version number. The string
> "Unknown" will be returned in this case.

### See Also

-   <span class="function">oci\_server\_version</span>

oci\_close
==========

Closes an Oracle connection

### Description

<span class="type">bool</span> <span
class="methodname">oci\_close</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> )

Unsets `connection`. The underlying database connection is closed if no
other resources are using it and if it was created with <span
class="function">oci\_connect</span> or <span
class="function">oci\_new\_connect</span>.

It is recommended to close connections that are no longer needed because
this makes database resources available for other users.

### Parameters

`connection`  
An Oracle connection identifier returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Closing a connection**

Resources associated with a connection should be closed to ensure the
underlying database connection is properly terminated and the database
resources are released.

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM departments');
$r = oci_execute($stid);
oci_fetch_all($stid, $res);
var_dump($res);

// Free the statement identifier when closing the connection
oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 Database connections are not closed until all references
are closed**

The internal refcount of a connection identifier must be zero before the
underlying connection to the database is closed.

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM departments');  // this increases the refcount on $conn
oci_execute($stid);
oci_fetch_all($stid, $res);
var_dump($res);

oci_close($conn);

// $conn is no longer usable in the script but the underlying database
// connection is still held open until $stid is freed.
var_dump($conn);  // prints NULL  

// While PHP sleeps, querying the Oracle V$SESSION view in a
// terminal window will show that the database user is still connected.
sleep(10);

// When $stid is freed, the database connection is physically closed
oci_free_statement($stid);  

// While PHP sleeps, querying the Oracle V$SESSION view in a
// terminal window will show that the database user has disconnected.
sleep(10);

?>
```

**Example \#3 Closing a connection opened more than once**

When database credentials are reused, both connections must be closed
before the underlying database connection is closed.

``` php
<?php

$conn1 = oci_connect('hr', 'welcome', 'localhost/XE');

// Using the same credentials reuses the same underlying database connection
// Any uncommitted changes done on $conn1 will be visible in $conn2
$conn2 = oci_connect('hr', 'welcome', 'localhost/XE');

// While PHP sleeps, querying the Oracle V$SESSION view in a
// terminal window will show that only one database user is connected.
sleep(10);

oci_close($conn1); // doesn't close the underlying database connection
var_dump($conn1);  // prints NULL because the variable $conn1 is no longer usable
var_dump($conn2);  // displays that $conn2 is still a valid connection resource

?>
```

**Example \#4 Connections are closed when variables go out of scope**

When all variables referencing a connection go out of scope and are
freed by PHP, a rollback occurs (if necessary) and the underlying
connection to the database is closed.

``` php
<?php

function myfunc() {
    $conn = oci_connect('hr', 'hrpwd', 'localhost/XE');
    if (!$conn) {
        $e = oci_error();
        trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
    }

    $stid = oci_parse($conn, 'UPDATE mytab SET id = 100');
    oci_execute($stid, OCI_NO_AUTO_COMMIT);
    return "Finished";
}

$r = myfunc();
// At this point a rollback occurred and the underlying database connection was released.

print $r;  // displays the function return value "Finished"

?>
```

### Notes

> **Note**:
>
> Variables that have a dependency on the connection identifier, such as
> statement identifiers returned by <span
> class="function">oci\_parse</span>, must also be freed before the
> underlying database connection is closed.

> **Note**:
>
> Prior to version PHP 5.1.2 (PECL OCI8 1.1) <span
> class="function">oci\_close</span> was a no-op. In more recent
> versions it correctly closes the Oracle connection. Use
> <a href="/book/oci8.html#" class="link">oci8.old_oci_close_semantics</a>
> option to restore old behavior of this function.

> **Note**:
>
> The <span class="function">oci\_close</span> function does not close
> the underlying database connections created with <span
> class="function">oci\_pconnect</span>.

### See Also

-   <span class="function">oci\_connect</span>
-   <span class="function">oci\_free\_statement</span>

oci\_commit
===========

Commits the outstanding database transaction

### Description

<span class="type">bool</span> <span
class="methodname">oci\_commit</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> )

Commits the outstanding transaction for the Oracle `connection`. A
commit ends the current transaction and makes permanent all changes. It
releases all locks held.

A transaction begins when the first SQL statement that changes data is
executed with <span class="function">oci\_execute</span> using the
**`OCI_NO_AUTO_COMMIT`** flag. Further data changes made by other
statements become part of the same transaction. Data changes made in a
transaction are temporary until the transaction is committed or rolled
back. Other users of the database will not see the changes until they
are committed.

When inserting or updating data, using transactions is recommended for
relational data consistency and for performance reasons.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">oci\_commit</span> example**

``` php
<?php

// Insert into several tables, rolling back the changes if an error occurs

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, "INSERT INTO mysalary (id, name) VALUES (1, 'Chris')");

// The OCI_NO_AUTO_COMMIT flag tells Oracle not to commit the INSERT immediately
// Use OCI_DEFAULT as the flag for PHP <= 5.3.1.  The two flags are equivalent
$r = oci_execute($stid, OCI_NO_AUTO_COMMIT);
if (!$r) {    
    $e = oci_error($stid);
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, 'INSERT INTO myschedule (startday) VALUES (12)');
$r = oci_execute($stid, OCI_NO_AUTO_COMMIT);
if (!$r) {    
    $e = oci_error($stid);
    oci_rollback($conn);  // rollback changes to both tables
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

// Commit the changes to both tables
$r = oci_commit($conn);
if (!$r) {
    $e = oci_error($conn);
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

?>
```

### Notes

> **Note**:
>
> Transactions are automatically rolled back when you close the
> connection, or when the script ends, whichever is soonest. You need to
> explicitly call <span class="function">oci\_commit</span> to commit
> the transaction.
>
> Any call to <span class="function">oci\_execute</span> that uses
> **`OCI_COMMIT_ON_SUCCESS`** mode explicitly or by default will commit
> any previous uncommitted transaction.
>
> Any Oracle DDL statement such as *CREATE* or *DROP* will automatically
> commit any uncommitted transaction.

### See Also

-   <span class="function">oci\_execute</span>
-   <span class="function">oci\_rollback</span>

oci\_connect
============

Connect to an Oracle database

### Description

<span class="type">resource</span> <span
class="methodname">oci\_connect</span> ( <span class="methodparam"><span
class="type">string</span> `$username`</span> , <span
class="methodparam"><span class="type">string</span> `$password`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$connection_string`</span> \[, <span class="methodparam"><span
class="type">string</span> `$character_set`</span> \[, <span
class="methodparam"><span class="type">int</span> `$session_mode`</span>
\]\]\] )

Returns a connection identifier needed for most other OCI8 operations.

For performance, most applications should use persistent connections
with <span class="function">oci\_pconnect</span> instead of <span
class="function">oci\_connect</span>. See
<a href="/book/oci8.html#OCI8%20Connection%20Handling%20and%20Connection%20Pooling" class="link">Connection Handling</a>
for general information on connection management and connection pooling.

From PHP 5.1.2 (PECL OCI8 1.1) <span class="function">oci\_close</span>
can be used to close the connection.

The second and subsequent calls to <span
class="function">oci\_connect</span> with the same parameters will
return the connection handle returned from the first call. This means
that transactions in one handle are also in the other handles, because
they use the *same* underlying database connection. If two handles need
to be transactionally isolated from each other, use <span
class="function">oci\_new\_connect</span> instead.

### Parameters

`username`  
The Oracle user name.

`password`  
The password for `username`.

`connection_string`  
Contains the *Oracle instance* to connect to. It can be an
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-E5358DEA-D619-4B7B-A799-3D2F802500F1" class="link external">» Easy Connect string</a>,
or a Connect Name from the `tnsnames.ora` file, or the name of a local
Oracle instance.

If not specified, PHP uses environment variables such as **`TWO_TASK`**
(on Linux) or **`LOCAL`** (on Windows) and **`ORACLE_SID`** to determine
the *Oracle instance* to connect to.

To use the Easy Connect naming method, PHP must be linked with Oracle
10*g* or greater Client libraries. The Easy Connect string for Oracle
10*g* is of the form: *\[//\]host\_name\[:port\]\[/service\_name\]*.
From Oracle 11*g*, the syntax is:
*\[//\]host\_name\[:port\]\[/service\_name\]\[:server\_type\]\[/instance\_name\]*.
Futher options were introduced with Oracle 19c, including timeout and
keep-alive settings. Refer to Oracle documentation. Service names can be
found by running the Oracle utility *lsnrctl status* on the database
server machine.

The `tnsnames.ora` file can be in the Oracle Net search path, which
includes `/your/path/to/instantclient/network/admin`,
`$ORACLE_HOME/network/admin` and `/etc`. Alternatively set *TNS\_ADMIN*
so that `$TNS_ADMIN/tnsnames.ora` is read. Make sure the web daemon has
read access to the file.

`character_set`  
Determines the character set used by the Oracle Client libraries. The
character set does not need to match the character set used by the
database. If it doesn't match, Oracle will do its best to convert data
to and from the database character set. Depending on the character sets
this may not give usable results. Conversion also adds some time
overhead.

If not specified, the Oracle Client libraries determine a character set
from the **`NLS_LANG`** environment variable.

Passing this parameter can reduce the time taken to connect.

`session_mode`  
This parameter is available since version PHP 5 (PECL OCI8 1.1) and
accepts the following values: **`OCI_DEFAULT`**, **`OCI_SYSOPER`** and
**`OCI_SYSDBA`**. If either **`OCI_SYSOPER`** or **`OCI_SYSDBA`** were
specified, this function will try to establish privileged connection
using external credentials. Privileged connections are disabled by
default. To enable them you need to set
<a href="/book/oci8.html#" class="link">oci8.privileged_connect</a> to
*On*.

PHP 5.3 (PECL OCI8 1.3.4) introduced the **`OCI_CRED_EXT`** mode value.
This tells Oracle to use External or OS authentication, which must be
configured in the database. The **`OCI_CRED_EXT`** flag can only be used
with username of "/" and a empty password.
<a href="/book/oci8.html#" class="link">oci8.privileged_connect</a> may
be *On* or *Off*.

**`OCI_CRED_EXT`** may be combined with the **`OCI_SYSOPER`** or
**`OCI_SYSDBA`** modes.

**`OCI_CRED_EXT`** is not supported on Windows for security reasons.

### Return Values

Returns a connection identifier or **`false`** on error.

### Examples

**Example \#1 Basic <span class="function">oci\_connect</span> using
Easy Connect syntax**

``` php
<?php

// Connects to the XE service (i.e. database) on the "localhost" machine
$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM employees');
oci_execute($stid);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>" . ($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;") . "</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

?>
```

**Example \#2 Basic <span class="function">oci\_connect</span> using a
Network Connect name**

``` php
<?php

// Connects to the MYDB database described in tnsnames.ora file,
// One example tnsnames.ora entry for MYDB could be:
//   MYDB =
//     (DESCRIPTION =
//       (ADDRESS = (PROTOCOL = TCP)(HOST = mymachine.oracle.com)(PORT = 1521))
//       (CONNECT_DATA =
//         (SERVER = DEDICATED)
//         (SERVICE_NAME = XE)
//       )
//     )

$conn = oci_connect('hr', 'welcome', 'MYDB');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM employees');
oci_execute($stid);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>" . ($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;") . "</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

?>
```

**Example \#3 <span class="function">oci\_connect</span> with an
explicit character set**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE', 'AL32UTF8');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM employees');
oci_execute($stid);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>" . ($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;") . "</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

?>
```

**Example \#4 Using multiple calls to <span
class="function">oci\_connect</span>**

``` php
<?php

$c1 = oci_connect("hr", "welcome", 'localhost/XE');
$c2 = oci_connect("hr", "welcome", 'localhost/XE');

// Both $c1 and $c2 show the same PHP resource id meaning they use the
// same underlying database connection
echo "c1 is $c1<br>\n";
echo "c2 is $c2<br>\n";

function create_table($conn)
{
    $stmt = oci_parse($conn, "create table hallo (test varchar2(64))");
    oci_execute($stmt);
    echo "Created table<br>\n";
}

function drop_table($conn)
{
    $stmt = oci_parse($conn, "drop table hallo");
    oci_execute($stmt);
    echo "Dropped table<br>\n";
}

function insert_data($connname, $conn)
{
    $stmt = oci_parse($conn, "insert into hallo
              values(to_char(sysdate,'DD-MON-YY HH24:MI:SS'))");
    oci_execute($stmt, OCI_DEFAULT);
    echo "$connname inserted row without committing<br>\n";
}

function rollback($connname, $conn)
{
    oci_rollback($conn);
    echo "$connname rollback<br>\n";
}

function select_data($connname, $conn)
{
    $stmt = oci_parse($conn, "select * from hallo");
    oci_execute($stmt, OCI_DEFAULT);
    echo "$connname ----selecting<br>\n";
    while (oci_fetch($stmt)) {
        echo "    " . oci_result($stmt, "TEST") . "<br>\n";
    }
    echo "$connname ----done<br>\n";
}

create_table($c1);

insert_data('c1', $c1);   // Insert a row using c1
sleep(2);                 // sleep to show a different timestamp for the 2nd row
insert_data('c2', $c2);   // Insert a row using c2

select_data('c1', $c1);   // Results of both inserts are returned
select_data('c2', $c2);   // Results of both inserts are returned

rollback('c1', $c1);      // Rollback using c1

select_data('c1', $c1);   // Both inserts have been rolled back
select_data('c2', $c2);

drop_table($c1);

// Closing one of the connections makes the PHP variable unusable, but
// the other could be used
oci_close($c1);
echo "c1 is $c1<br>\n";
echo "c2 is $c2<br>\n";


// Output is:
//    c1 is Resource id #5
//    c2 is Resource id #5
//    Created table
//    c1 inserted row without committing
//    c2 inserted row without committing
//    c1 ----selecting
//        09-DEC-09 12:14:43
//        09-DEC-09 12:14:45
//    c1 ----done
//    c2 ----selecting
//        09-DEC-09 12:14:43
//        09-DEC-09 12:14:45
//    c2 ----done
//    c1 rollback
//    c1 ----selecting
//    c1 ----done
//    c2 ----selecting
//    c2 ----done
//    Dropped table
//    c1 is
//    c2 is Resource id #5

?>
```

### Notes

> **Note**:
>
> An incorrectly installed or configured OCI8 extension will often
> manifest itself as a connection problem or error. See
> <a href="/book/oci8.html#Installing/Configuring" class="link">Installing/Configuring</a>
> for troubleshooting information.

### See Also

-   <span class="function">oci\_pconnect</span>
-   <span class="function">oci\_new\_connect</span>
-   <span class="function">oci\_close</span>

oci\_define\_by\_name
=====================

Associates a PHP variable with a column for query fetches

### Description

<span class="type">bool</span> <span
class="methodname">oci\_define\_by\_name</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">string</span> `$column_name`</span> , <span
class="methodparam"><span class="type">mixed</span> `&$variable`</span>
\[, <span class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = SQLT\_CHR</span></span> \] )

Associates a PHP variable with a column for query fetches using <span
class="function">oci\_fetch</span>.

The <span class="function">oci\_define\_by\_name</span> call must occur
before executing <span class="function">oci\_execute</span>.

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>, or a *REF CURSOR* statement
identifier.

`column_name`  
The column name used in the query.

Use uppercase for Oracle's default, non-case sensitive column names. Use
the exact column name case for case-sensitive column names.

`variable`  
The PHP variable that will contain the returned column value.

`type`  
The data type to be returned. Generally not needed. Note that
Oracle-style data conversions are not performed. For example,
*SQLT\_INT* will be ignored and the returned data type will still be
*SQLT\_CHR*.

You can optionally use <span
class="function">oci\_new\_descriptor</span> to allocate LOB/ROWID/BFILE
descriptors.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">oci\_define\_by\_name</span>
example**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'SELECT location_id, city FROM locations WHERE location_id < 1200';
$stid = oci_parse($conn, $sql);

// The defines MUST be done before executing
oci_define_by_name($stid, 'LOCATION_ID', $locid);
oci_define_by_name($stid, 'CITY', $city);

oci_execute($stid);

// Each fetch populates the previously defined variables with the next row's data
while (oci_fetch($stid)) {
    echo "Location id $locid is $city<br>\n";
}

// Displays:
//   Location id 1000 is Roma
//   Location id 1100 is Venice

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 <span class="function">oci\_define\_by\_name</span> with
case sensitive column names**

``` php
<?php

/*
  Before running, create the table with a case sensitive column name:
    CREATE TABLE mytab (id NUMBER, "MyDescription" VARCHAR2(30));
    INSERT INTO mytab (id, "MyDescription") values (1, 'Iced Coffee');
    COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM mytab');

// Use uppercase for non case-sensitive column names
oci_define_by_name($stid, 'ID', $id);

// Use the exact case for case-sensitive column names
oci_define_by_name($stid, 'MyDescription', $mydesc);

oci_execute($stid);

while (oci_fetch($stid)) {
    echo "id $id is $mydesc<br>\n";
}

// Displays:
//   id 1 is Iced Coffee

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#3 <span class="function">oci\_define\_by\_name</span> with
LOB columns**

``` php
<?php

/*
  Before running, create the table:
    CREATE TABLE mytab (id NUMBER, fruit CLOB);
    INSERT INTO mytab (id, fruit) values (1, 'apple');
    INSERT INTO mytab (id, fruit) values (2, 'orange');
    COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM mytab');

// The defines MUST be done before executing
oci_define_by_name($stid, 'ID', $id);
oci_define_by_name($stid, 'FRUIT', $fruit);  // $fruit will become a LOB descriptor

oci_execute($stid);

while (oci_fetch($stid)) {
    echo $id . " is " . $fruit->load(100) . "<br>\n";
}

// Displays:
//   1 is apple
//   2 is orange

$fruit->free();
oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#4 <span class="function">oci\_define\_by\_name</span> with
an explicit type**

``` php
<?php

/*
  Before running, create the table:
    CREATE TABLE mytab (id NUMBER, fruit CLOB);
    INSERT INTO mytab (id, fruit) values (1, 'apple');
    INSERT INTO mytab (id, fruit) values (2, 'orange');
    COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM mytab');

// The defines MUST be done before executing
oci_define_by_name($stid, 'ID', $id);

$fruit = oci_new_descriptor($conn, OCI_D_LOB);
oci_define_by_name($stid, 'FRUIT', $fruit, OCI_D_CLOB);

oci_execute($stid);

while (oci_fetch($stid)) {
    echo $id . " is " . $fruit->load(100) . "<br>\n";
}

// Displays:
//   1 is apple
//   2 is orange

$fruit->free();
oci_free_statement($stid);
oci_close($conn);

?>
```

### See Also

-   <span class="function">oci\_fetch</span>
-   <span class="function">oci\_new\_descriptor</span>

oci\_error
==========

Returns the last error found

### Description

<span class="type">array</span> <span
class="methodname">oci\_error</span> (\[ <span class="methodparam"><span
class="type">resource</span> `$resource`</span> \] )

Returns the last error found.

The function should be called immediately after an error occurs. Errors
are cleared by a successful statement.

### Parameters

`resource`  
For most errors, `resource` is the resource handle that was passed to
the failing function call. For connection errors with <span
class="function">oci\_connect</span>, <span
class="function">oci\_new\_connect</span> or <span
class="function">oci\_pconnect</span> do not pass `resource`.

### Return Values

If no error is found, <span class="function">oci\_error</span> returns
**`false`**. Otherwise, <span class="function">oci\_error</span> returns
the error information as an associative array.

| Array key | Type                             | Description                                                                                |
|-----------|----------------------------------|--------------------------------------------------------------------------------------------|
| *code*    | <span class="type">int</span>    | The Oracle error number.                                                                   |
| *message* | <span class="type">string</span> | The Oracle error text.                                                                     |
| *offset*  | <span class="type">int</span>    | The byte position of an error in the SQL statement. If there was no statement, this is *0* |
| *sqltext* | <span class="type">string</span> | The SQL statement text. If there was no statement, this is an empty string.                |

### Examples

**Example \#1 Displaying the Oracle error message after a connection
error**

``` php
<?php
$conn = oci_connect("hr", "welcome", "localhost/XE");
if (!$conn) {
    $e = oci_error();   // For oci_connect errors do not pass a handle
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}
?>
```

**Example \#2 Displaying the Oracle error message after a parsing
error**

``` php
<?php
$stid = oci_parse($conn, "select ' from dual");  // note mismatched quote
if (!$stid) {
    $e = oci_error($conn);  // For oci_parse errors pass the connection handle
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}
?>
```

**Example \#3 Displaying the Oracle error message, the problematic
statement, and the position of the problem of an execution error**

``` php
<?php
$stid = oci_parse($conn, "select does_not_exist from dual");
$r = oci_execute($stid);
if (!$r) {
    $e = oci_error($stid);  // For oci_execute errors pass the statement handle
    print htmlentities($e['message']);
    print "\n<pre>\n";
    print htmlentities($e['sqltext']);
    printf("\n%".($e['offset']+1)."s", "^");
    print  "\n</pre>\n";
}
?>
```

oci\_execute
============

Executes a statement

### Description

<span class="type">bool</span> <span
class="methodname">oci\_execute</span> ( <span class="methodparam"><span
class="type">resource</span> `$statement`</span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = OCI\_COMMIT\_ON\_SUCCESS</span></span> \] )

Executes a `statement` previously returned from <span
class="function">oci\_parse</span>.

After execution, statements like *INSERT* will have data committed to
the database by default. For statements like *SELECT*, execution
performs the logic of the query. Query results can subsequently be
fetched in PHP with functions like <span
class="function">oci\_fetch\_array</span>.

Each parsed statement may be executed multiple times, saving the cost of
re-parsing. This is commonly used for *INSERT* statements when data is
bound with <span class="function">oci\_bind\_by\_name</span>.

### Parameters

`statement`  
A valid OCI statement identifier.

`mode`  
An optional second parameter can be one of the following constants:

| Constant                    | Description                                                                                                                                                                                                                  |
|-----------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`OCI_COMMIT_ON_SUCCESS`** | Automatically commit all outstanding changes for this connection when the statement has succeeded. This is the default.                                                                                                      |
| **`OCI_DESCRIBE_ONLY`**     | Make query meta data available to functions like <span class="function">oci\_field\_name</span> but do not create a result set. Any subsequent fetch call such as <span class="function">oci\_fetch\_array</span> will fail. |
| **`OCI_NO_AUTO_COMMIT`**    | Do not automatically commit changes. Prior to PHP 5.3.2 (PECL OCI8 1.4) use **`OCI_DEFAULT`** which is equivalent to **`OCI_NO_AUTO_COMMIT`**.                                                                               |

Using **`OCI_NO_AUTO_COMMIT`** mode starts or continues a transaction.
Transactions are automatically rolled back when the connection is
closed, or when the script ends. Explicitly call <span
class="function">oci\_commit</span> to commit a transaction, or <span
class="function">oci\_rollback</span> to abort it.

When inserting or updating data, using transactions is recommended for
relational data consistency and for performance reasons.

If **`OCI_NO_AUTO_COMMIT`** mode is used for any statement including
queries, and <span class="function">oci\_commit</span> or <span
class="function">oci\_rollback</span> is not subsequently called, then
OCI8 will perform a rollback at the end of the script even if no data
was changed. To avoid an unnecessary rollback, many scripts do not use
**`OCI_NO_AUTO_COMMIT`** mode for queries or PL/SQL. Be careful to
ensure the appropriate transactional consistency for the application
when using <span class="function">oci\_execute</span> with different
modes in the same script.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">oci\_execute</span> for queries**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'SELECT * FROM employees');
oci_execute($stid);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>" . ($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;") . "</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

?>
```

**Example \#2 <span class="function">oci\_execute</span> without
specifying a mode example**

``` php
<?php

// Before running, create the table:
//   CREATE TABLE MYTABLE (col1 NUMBER);

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'INSERT INTO mytab (col1) VALUES (123)');

oci_execute($stid); // The row is committed and immediately visible to other users

?>
```

**Example \#3 <span class="function">oci\_execute</span> with
**`OCI_NO_AUTO_COMMIT`** example**

``` php
<?php

// Before running, create the table:
//   CREATE TABLE MYTABLE (col1 NUMBER);

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'INSERT INTO mytab (col1) VALUES (:bv)');
oci_bind_by_name($stid, ':bv', $i, 10);
for ($i = 1; $i <= 5; ++$i) {
    oci_execute($stid, OCI_NO_AUTO_COMMIT);  // use OCI_DEFAULT for PHP <= 5.3.1
}
oci_commit($conn);  // commits all new values: 1, 2, 3, 4, 5

?>
```

**Example \#4 <span class="function">oci\_execute</span> with different
commit modes example**

``` php
<?php

// Before running, create the table:
//   CREATE TABLE MYTABLE (col1 NUMBER);

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'INSERT INTO mytab (col1) VALUES (123)');
oci_execute($stid, OCI_NO_AUTO_COMMIT);  // data not committed

$stid = oci_parse($conn, 'INSERT INTO mytab (col1) VALUES (456)');
oci_execute($stid);  // commits both 123 and 456 values

?>
```

**Example \#5 <span class="function">oci\_execute</span> with
**`OCI_DESCRIBE_ONLY`** example**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'SELECT * FROM locations');
oci_execute($s, OCI_DESCRIBE_ONLY);
for ($i = 1; $i <= oci_num_fields($stid); ++$i) {
    echo oci_field_name($stid, $i) . "<br>\n";
}

?>
```

### Notes

> **Note**:
>
> Transactions are automatically rolled back when connections are
> closed, or when the script ends, whichever is soonest. Explicitly call
> <span class="function">oci\_commit</span> to commit a transaction.
>
> Any call to <span class="function">oci\_execute</span> that uses
> **`OCI_COMMIT_ON_SUCCESS`** mode explicitly or by default will commit
> any previous uncommitted transaction.
>
> Any Oracle DDL statement such as *CREATE* or *DROP* will automatically
> commit any uncommitted transaction.

> **Note**:
>
> Because the <span class="function">oci\_execute</span> function
> generally sends the statement to the database, <span
> class="function">oci\_execute</span> can identify some statement
> syntax errors that the lightweight, local <span
> class="function">oci\_parse</span> function does not.

### See Also

-   <span class="function">oci\_parse</span>

oci\_fetch\_all
===============

Fetches multiple rows from a query into a two-dimensional array

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">oci\_fetch\_all</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">array</span> `&$output`</span> \[, <span
class="methodparam"><span class="type">int</span> `$skip`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$maxrows`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = **`OCI_FETCHSTATEMENT_BY_COLUMN`** +
**`OCI_ASSOC`**</span></span> \]\]\] )

Fetches multiple rows from a query into a two-dimensional array. By
default, all rows are returned.

This function can be called only once for each query executed with <span
class="function">oci\_execute</span>.

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>, or a *REF CURSOR* statement
identifier.

`output`  
The variable to contain the returned rows.

LOB columns are returned as strings, where Oracle supports conversion.

See <span class="function">oci\_fetch\_array</span> for more information
on how data and types are fetched.

`skip`  
The number of initial rows to discard when fetching the result. The
default value is 0, so the first row onwards is returned.

`maxrows`  
The number of rows to return. The default is -1 meaning return all the
rows from `skip` + 1 onwards.

`flags`  
Parameter `flags` indicates the array structure and whether associative
arrays should be used.

| Constant                           | Description                                                                       |
|------------------------------------|-----------------------------------------------------------------------------------|
| **`OCI_FETCHSTATEMENT_BY_ROW`**    | The outer array will contain one sub-array per query row.                         |
| **`OCI_FETCHSTATEMENT_BY_COLUMN`** | The outer array will contain one sub-array per query column. This is the default. |

Arrays can be indexed either by column heading or numerically. Only one
index mode will be returned.

| Constant        | Description                                                                |
|-----------------|----------------------------------------------------------------------------|
| **`OCI_NUM`**   | Numeric indexes are used for each column's array.                          |
| **`OCI_ASSOC`** | Associative indexes are used for each column's array. This is the default. |

Use the addition operator "+" to choose a combination of array structure
and index modes.

Oracle's default, non-case sensitive column names will have uppercase
array keys. Case-sensitive column names will have array keys using the
exact column case. Use <span class="function">var\_dump</span> on
`output` to verify the appropriate case to use for each query.

Queries that have more than one column with the same name should use
column aliases. Otherwise only one of the columns will appear in an
associative array.

### Return Values

Returns the number of rows in `output`, which may be 0 or more, or
**`false`** on failure.

### Examples

**Example \#1 <span class="function">oci\_fetch\_all</span> example**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT POSTAL_CODE, CITY FROM locations WHERE ROWNUM < 3');
oci_execute($stid);

$nrows = oci_fetch_all($stid, $res);

echo "$nrows rows fetched<br>\n";
var_dump($res);

// var_dump output is:
//    2 rows fetched
//    array(2) {
//      ["POSTAL_CODE"]=>
//      array(2) {
//        [0]=>
//        string(6) "00989x"
//        [1]=>
//        string(6) "10934x"
//      }
//      ["CITY"]=>
//      array(2) {
//        [0]=>
//        string(4) "Roma"
//        [1]=>
//        string(6) "Venice"
//      }
//    }

// Pretty-print the results
echo "<table border='1'>\n";
foreach ($res as $col) {
    echo "<tr>\n";
    foreach ($col as $item) {
        echo "    <td>".($item !== null ? htmlentities($item, ENT_QUOTES) : "")."</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 <span class="function">oci\_fetch\_all</span> example with
**`OCI_FETCHSTATEMENT_BY_ROW`****

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT POSTAL_CODE, CITY FROM locations WHERE ROWNUM < 3');
oci_execute($stid);

$nrows = oci_fetch_all($stid, $res, null, null, OCI_FETCHSTATEMENT_BY_ROW);

echo "$nrows rows fetched<br>\n";
var_dump($res);

// Output is:
//    2 rows fetched
//    array(2) {
//      [0]=>
//      array(2) {
//        ["POSTAL_CODE"]=>
//        string(6) "00989x"
//        ["CITY"]=>
//        string(4) "Roma"
//      }
//      [1]=>
//      array(2) {
//        ["POSTAL_CODE"]=>
//        string(6) "10934x"
//        ["CITY"]=>
//        string(6) "Venice"
//      }
//    }

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#3 <span class="function">oci\_fetch\_all</span> with
**`OCI_NUM`****

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT POSTAL_CODE, CITY FROM locations WHERE ROWNUM < 3');
oci_execute($stid);

$nrows = oci_fetch_all($stid, $res, null, null, OCI_FETCHSTATEMENT_BY_ROW + OCI_NUM);

echo "$nrows rows fetched<br>\n";
var_dump($res);

// Output is:
//    2 rows fetched
//    array(2) {
//      [0]=>
//      array(2) {
//        [0]=>
//        string(6) "00989x"
//        [1]=>
//        string(4) "Roma"
//      }
//      [1]=>
//      array(2) {
//        [0]=>
//        string(6) "10934x"
//        [1]=>
//        string(6) "Venice"
//      }
//    }

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> Using `skip` is very inefficient. All the rows to be skipped are
> included in the result set that is returned from the database to PHP.
> They are then discarded. It is more efficient to use SQL to restrict
> the offset and range of rows in the query. See <span
> class="function">oci\_fetch\_array</span> for an example.

> **Note**:
>
> Queries that return a large number of rows can be more memory
> efficient if a single-row fetching function like <span
> class="function">oci\_fetch\_array</span> is used.

> **Note**:
>
> For queries returning a large number of rows, performance can be
> significantly improved by increasing
> <a href="/book/oci8.html#" class="link">oci8.default_prefetch</a> or
> using <span class="function">oci\_set\_prefetch</span>.

> **Note**:
>
> Will not return rows from Oracle Database 12*c* Implicit Result Sets.
> Use <span class="function">oci\_fetch\_array</span> instead.

### See Also

-   <span class="function">oci\_fetch</span>
-   <span class="function">oci\_fetch\_array</span>
-   <span class="function">oci\_fetch\_assoc</span>
-   <span class="function">oci\_fetch\_object</span>
-   <span class="function">oci\_fetch\_row</span>
-   <span class="function">oci\_set\_prefetch</span>

oci\_fetch\_array
=================

Returns the next row from a query as an associative or numeric array

### Description

<span class="type">array</span> <span
class="methodname">oci\_fetch\_array</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`</span> \] )

Returns an array containing the next result-set row of a query. Each
array entry corresponds to a column of the row. This function is
typically called in a loop until it returns **`false`**, indicating no
more rows exist.

If `statement` corresponds to a PL/SQL block returning Oracle Database
Implicit Result Sets, then rows from all sets are consecutively fetched.
If `statement` is returned by <span
class="function">oci\_get\_implicit\_resultset</span>, then only the
subset of rows for one child query are returned.

For details on the data type mapping performed by the OCI8 extension,
see the
<a href="/book/oci8.html#Supported%20Datatypes" class="link">datatypes supported by the driver</a>

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>, or a *REF CURSOR* statement
identifier.

Can also be a statement identifier returned by <span
class="function">oci\_get\_implicit\_resultset</span>.

`mode`  
An optional second parameter can be any combination of the following
constants:

| Constant               | Description                                                                                                                                  |
|------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| **`OCI_BOTH`**         | Returns an array with both associative and numeric indices. This is the same as **`OCI_ASSOC`** + **`OCI_NUM`** and is the default behavior. |
| **`OCI_ASSOC`**        | Returns an associative array.                                                                                                                |
| **`OCI_NUM`**          | Returns a numeric array.                                                                                                                     |
| **`OCI_RETURN_NULLS`** | Creates elements for **`null`** fields. The element values will be a PHP **`null`**.                                                         |
| **`OCI_RETURN_LOBS`**  | Returns the contents of LOBs instead of the LOB descriptors.                                                                                 |

The default `mode` is **`OCI_BOTH`**.

Use the addition operator "+" to specify more than one mode at a time.

### Return Values

Returns an array with associative and/or numeric indices. If there are
no more rows in the `statement` then **`false`** is returned.

By default, *LOB* columns are returned as LOB descriptors.

*DATE* columns are returned as strings formatted to the current date
format. The default format can be changed with Oracle environment
variables such as *NLS\_LANG* or by a previously executed *ALTER SESSION
SET NLS\_DATE\_FORMAT* command.

Oracle's default, non-case sensitive column names will have uppercase
associative indices in the result array. Case-sensitive column names
will have array indices using the exact column case. Use <span
class="function">var\_dump</span> on the result array to verify the
appropriate case to use for each query.

The table name is not included in the array index. If your query
contains two different columns with the same name, use **`OCI_NUM`** or
add a column alias to the query to ensure name uniqueness, see example
\#7. Otherwise only one column will be returned via PHP.

### Examples

**Example \#1 <span class="function">oci\_fetch\_array</span> with
**`OCI_BOTH`****

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT department_id, department_name FROM departments');
oci_execute($stid);

while (($row = oci_fetch_array($stid, OCI_BOTH)) != false) {
    // Use the uppercase column names for the associative array indices
    echo $row[0] . " and " . $row['DEPARTMENT_ID']   . " are the same<br>\n";
    echo $row[1] . " and " . $row['DEPARTMENT_NAME'] . " are the same<br>\n";
}

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 <span class="function">oci\_fetch\_array</span> with
**`OCI_NUM`****

``` php
<?php

/*
  Before running, create the table:
      CREATE TABLE mytab (id NUMBER, description CLOB);
      INSERT INTO mytab (id, description) values (1, 'A very long string');
      COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT id, description FROM mytab');
oci_execute($stid);

while (($row = oci_fetch_array($stid, OCI_NUM)) != false) {
    echo $row[0] . "<br>\n";
    echo $row[1]->read(11) . "<br>\n"; // this will output first 11 bytes from DESCRIPTION
}

// Output is:
//    1
//    A very long

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#3 <span class="function">oci\_fetch\_array</span> with
**`OCI_ASSOC`****

``` php
<?php

/*
  Before running, create the table:
      CREATE TABLE mytab (id NUMBER, description CLOB);
      INSERT INTO mytab (id, description) values (1, 'A very long string');
      COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT id, description FROM mytab');
oci_execute($stid);

while (($row = oci_fetch_array($stid, OCI_ASSOC)) != false) {
    echo $row['ID'] . "<br>\n";
    echo $row['DESCRIPTION']->read(11) . "<br>\n"; // this will output first 11 bytes from DESCRIPTION
}

// Output is:
//    1
//    A very long

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#4 <span class="function">oci\_fetch\_array</span> with
**`OCI_RETURN_NULLS`****

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT 1, null FROM dual');
oci_execute($stid);
while (($row = oci_fetch_array ($stid, OCI_ASSOC)) != false) { // Ignore NULLs
    var_dump($row);
}

/*
The above code prints:
  array(1) {
    [1]=>
    string(1) "1"
  }
*/

$stid = oci_parse($conn, 'SELECT 1, null FROM dual');
oci_execute($stid);
while (($row = oci_fetch_array ($stid, OCI_ASSOC+OCI_RETURN_NULLS)) != false) { // Fetch NULLs
    var_dump($row);
}

/*
The above code prints:
  array(2) {
    [1]=>
    string(1) "1"
    ["NULL"]=>
    NULL
  }
*/

?>
```

**Example \#5 <span class="function">oci\_fetch\_array</span> with
**`OCI_RETURN_LOBS`****

``` php
<?php

/*
  Before running, create the table:
      CREATE TABLE mytab (id NUMBER, description CLOB);
      INSERT INTO mytab (id, description) values (1, 'A very long string');
      COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT id, description FROM mytab');
oci_execute($stid);

while (($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_LOBS)) != false) {
    echo $row['ID'] . "<br>\n";
    echo $row['DESCRIPTION'] . "<br>\n"; // this contains all of DESCRIPTION
    // In a loop, freeing the large variable before the 2nd fetch reduces PHP's peak memory usage
    unset($row); 
}

// Output is:
//    1
//    A very long string

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#6 <span class="function">oci\_fetch\_array</span> with case
sensitive column names**

``` php
<?php

/*
   Before running, create the table:
      CREATE TABLE mytab ("Name" VARCHAR2(20), city VARCHAR2(20));
      INSERT INTO mytab ("Name", city) values ('Chris', 'Melbourne');
      COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'select * from mytab');
oci_execute($stid);
$row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS);

// Because 'Name' was created as a case-sensitive column, that same
// case is used for the array index.  However uppercase 'CITY' must
// be used for the case-insensitive column index
print $row['Name'] . "<br>\n";   //  prints Chris
print $row['CITY'] . "<br>\n";   //  prints Melbourne

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#7 <span class="function">oci\_fetch\_array</span> with
columns having duplicate names**

``` php
<?php

/*
  Before running, create the tables:
      CREATE TABLE mycity (id NUMBER, name VARCHAR2(20));
      INSERT INTO mycity (id, name) values (1, 'Melbourne');
      CREATE TABLE mycountry (id NUMBER, name VARCHAR2(20));
      INSERT INTO mycountry (id, name) values (1, 'Australia');
      COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'SELECT mycity.name, mycountry.name
        FROM mycity, mycountry
        WHERE mycity.id = mycountry.id';
$stid = oci_parse($conn, $sql);
oci_execute($stid);
$row = oci_fetch_array($stid, OCI_ASSOC);
var_dump($row);

// Output only contains one "NAME" entry:
//    array(1) {
//      ["NAME"]=>
//      string(9) "Australia"
//    }

// To query a repeated column name, use an SQL column alias like "AS ctnm":
$sql = 'SELECT mycity.name AS ctnm, mycountry.name 
        FROM mycity, mycountry 
        WHERE mycity.id = mycountry.id';
$stid = oci_parse($conn, $sql);
oci_execute($stid);
$row = oci_fetch_array($stid, OCI_ASSOC);
var_dump($row);

// Output now contains both columns selected:
//    array(2) {
//      ["CTNM"]=>
//      string(9) "Melbourne"
//      ["NAME"]=>
//      string(9) "Australia"
//    }


oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#8 <span class="function">oci\_fetch\_array</span> with
*DATE* columns**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

// Set the date format for this connection.
// For performance reasons, consider changing the format
// in a trigger or with environment variables instead
$stid = oci_parse($conn, "ALTER SESSION SET NLS_DATE_FORMAT = 'YYYY-MM-DD'");
oci_execute($stid);

$stid = oci_parse($conn, 'SELECT hire_date FROM employees WHERE employee_id = 188');
oci_execute($stid);
$row = oci_fetch_array($stid, OCI_ASSOC);
echo $row['HIRE_DATE'] . "<br>\n";  // prints 1997-06-14

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#9 <span class="function">oci\_fetch\_array</span> with *REF
CURSOR***

``` php
<?php
/*
  Create the PL/SQL stored procedure as:

  CREATE OR REPLACE PROCEDURE myproc(p1 OUT SYS_REFCURSOR) AS
  BEGIN
    OPEN p1 FOR SELECT * FROM all_objects WHERE ROWNUM < 5000;
  END;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'BEGIN myproc(:rc); END;');
$refcur = oci_new_cursor($conn);
oci_bind_by_name($stid, ':rc', $refcur, -1, OCI_B_CURSOR);
oci_execute($stid);

// Execute the returned REF CURSOR and fetch from it like a statement identifier
oci_execute($refcur);  
echo "<table border='1'>\n";
while (($row = oci_fetch_array($refcur, OCI_ASSOC+OCI_RETURN_NULLS)) != false) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>".($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;")."</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

oci_free_statement($refcur);
oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#10 Pagination with <span
class="function">oci\_fetch\_array</span> using a *LIMIT*-like query**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

// Find the version of the database
preg_match('/Release ([0-9]+)\./', oci_server_version($conn), $matches);
$oracleversion = $matches[1];

// This is the query you want to "page" through
$sql = 'SELECT city, postal_code FROM locations ORDER BY city';

if ($oracleversion >= 12) {
    // Make use of Oracle 12c OFFSET / FETCH NEXT syntax
    $sql = $sql . ' OFFSET :offset ROWS FETCH NEXT :numrows ROWS ONLY';
} else {
    // Older Oracle versions need a nested query selecting a subset
    // from $sql.  Or, if the SQL statement is known at development
    // time, consider using a row_number() function instead of this
    // nested solution.  In production environments, be careful to
    // avoid SQL Injection issues with concatenation.
    $sql = "SELECT * FROM (SELECT a.*, ROWNUM AS my_rnum
                           FROM ($sql) a
                           WHERE ROWNUM <= :offset + :numrows)
            WHERE my_rnum > :offset";
}

$offset  = 0;  // skip this many rows
$numrows = 5;  // return 5 rows
$stid = oci_parse($conn, $sql);
oci_bind_by_name($stid, ':numrows', $numrows);
oci_bind_by_name($stid, ':offset', $offset);
oci_execute($stid);

while (($row = oci_fetch_array($stid, OCI_ASSOC + OCI_RETURN_NULLS)) != false) {
    echo $row['CITY'] . " " . $row['POSTAL_CODE'] . "<br>\n";
}

// Output is:
//    Beijing 190518
//    Bern 3095
//    Bombay 490231
//    Geneva 1730
//    Hiroshima 6823

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#11 <span class="function">oci\_fetch\_array</span> with
Oracle Database Implicit Result Sets**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/pdborcl');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

// Requires OCI8 2.0 (or later) and Oracle Database 12c (or later)
// Also see oci_get_implicit_resultset()
$sql = 'DECLARE
           c1 SYS_REFCURSOR;
        BEGIN
           OPEN c1 FOR SELECT city, postal_code FROM locations WHERE ROWNUM < 4 ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
           OPEN c1 FOR SELECT country_id FROM locations WHERE ROWNUM < 4 ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
        END;';

$stid = oci_parse($conn, $sql);
oci_execute($stid);

// Note: oci_fetch_all and oci_fetch() cannot be used in this manner
echo "<table>\n";
while (($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) != false) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "  <td>".($item!==null?htmlentities($item, ENT_QUOTES|ENT_SUBSTITUTE):"&nbsp;")."</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

// Output is:
//    Beijing 190518
//    Bern    3095
//    Bombay  490231
//    CN
//    CH
//    IN

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> Associative array indices need to be in uppercase for standard Oracle
> columns that were created with case insensitive names.

> **Note**:
>
> For queries returning a large number of rows, performance can be
> significantly improved by increasing
> <a href="/book/oci8.html#" class="link">oci8.default_prefetch</a> or
> using <span class="function">oci\_set\_prefetch</span>.

> **Note**:
>
> The function <span class="function">oci\_fetch\_array</span> is
> *insignificantly* slower than <span
> class="function">oci\_fetch\_assoc</span> or <span
> class="function">oci\_fetch\_row</span>, but is more flexible.

### See Also

-   <span class="function">oci\_fetch</span>
-   <span class="function">oci\_fetch\_all</span>
-   <span class="function">oci\_fetch\_assoc</span>
-   <span class="function">oci\_fetch\_object</span>
-   <span class="function">oci\_fetch\_row</span>
-   <span class="function">oci\_set\_prefetch</span>

oci\_fetch\_assoc
=================

Returns the next row from a query as an associative array

### Description

<span class="type">array</span> <span
class="methodname">oci\_fetch\_assoc</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> )

Returns an associative array containing the next result-set row of a
query. Each array entry corresponds to a column of the row. This
function is typically called in a loop until it returns **`false`**,
indicating no more rows exist.

Calling <span class="function">oci\_fetch\_assoc</span> is identical to
calling <span class="function">oci\_fetch\_array</span> with
**`OCI_ASSOC`** + **`OCI_RETURN_NULLS`**.

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>, or a *REF CURSOR* statement
identifier.

### Return Values

Returns an associative array. If there are no more rows in the
`statement` then **`false`** is returned.

### Examples

**Example \#1 <span class="function">oci\_fetch\_assoc</span> Example**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT department_id, department_name FROM departments');
oci_execute($stid);

while (($row = oci_fetch_assoc($stid)) != false) {
    echo $row['DEPARTMENT_ID'] . " " . $row['DEPARTMENT_NAME'] . "<br>\n";
}

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> See <span class="function">oci\_fetch\_array</span> for more examples
> of fetching rows.

### See Also

-   <span class="function">oci\_fetch</span>
-   <span class="function">oci\_fetch\_all</span>
-   <span class="function">oci\_fetch\_array</span>
-   <span class="function">oci\_fetch\_object</span>
-   <span class="function">oci\_fetch\_row</span>

oci\_fetch\_object
==================

Returns the next row from a query as an object

### Description

<span class="type">object</span> <span
class="methodname">oci\_fetch\_object</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> )

Returns an object containing the next result-set row of a query. Each
attribute of the object corresponds to a column of the row. This
function is typically called in a loop until it returns **`false`**,
indicating no more rows exist.

For details on the data type mapping performed by the OCI8 extension,
see the
<a href="/book/oci8.html#Supported%20Datatypes" class="link">datatypes supported by the driver</a>

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>, or a *REF CURSOR* statement
identifier.

### Return Values

Returns an object. Each attribute of the object corresponds to a column
of the row. If there are no more rows in the `statement` then
**`false`** is returned.

Any *LOB* columns are returned as LOB descriptors.

*DATE* columns are returned as strings formatted to the current date
format. The default format can be changed with Oracle environment
variables such as *NLS\_LANG* or by a previously executed *ALTER SESSION
SET NLS\_DATE\_FORMAT* command.

Oracle's default, non-case sensitive column names will have uppercase
attribute names. Case-sensitive column names will have attribute names
using the exact column case. Use <span class="function">var\_dump</span>
on the result object to verify the appropriate case for attribute
access.

Attribute values will be **`null`** for any *NULL* data fields.

### Examples

**Example \#1 <span class="function">oci\_fetch\_object</span> example**

``` php
<?php

/*
  Before running, create the table:
    CREATE TABLE mytab (id NUMBER, description VARCHAR2(30));
    INSERT INTO mytab (id, description) values (1, 'Fish and Chips');
    COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT id, description FROM mytab');
oci_execute($stid);

while (($row = oci_fetch_object($stid)) != false) {
    // Use upper case attribute names for each standard Oracle column
    echo $row->ID . "<br>\n";
    echo $row->DESCRIPTION . "<br>\n"; 
}

// Output is:
//    1
//    Fish and Chips

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 <span class="function">oci\_fetch\_object</span> with case
sensitive column names**

``` php
<?php

/*
  Before running, create the table with a case sensitive column name:
    CREATE TABLE mytab (id NUMBER, "MyDescription" VARCHAR2(30));
    INSERT INTO mytab (id, "MyDescription") values (1, 'Iced Coffee');
    COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT id, "MyDescription" FROM mytab');
oci_execute($stid);

while (($row = oci_fetch_object($stid)) != false) {
    // Use upper case attribute names for each standard Oracle column
    echo $row->ID . "<br>\n";
    // Use the exact case for the case sensitive column name
    echo $row->MyDescription . "<br>\n";   
}

// Output is:
//    1
//    Iced Coffee

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#3 <span class="function">oci\_fetch\_object</span> with
LOBs**

``` php
<?php

/*
  Before running, create the table:
    CREATE TABLE mytab (id NUMBER, description CLOB);
    INSERT INTO mytab (id, description) values (1, 'A very long string');
    COMMIT;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT id, description FROM mytab');
oci_execute($stid);

while (($row = oci_fetch_object($stid)) != false) {
    echo $row->ID . "<br>\n";
    // The following will output the first 11 bytes from DESCRIPTION
    echo $row->DESCRIPTION->read(11) . "<br>\n"; 
}

// Output is:
//    1
//    A very long

oci_free_statement($stid);
oci_close($conn);

?>
```

### See Also

-   <span class="function">oci\_fetch</span>
-   <span class="function">oci\_fetch\_all</span>
-   <span class="function">oci\_fetch\_assoc</span>
-   <span class="function">oci\_fetch\_array</span>
-   <span class="function">oci\_fetch\_row</span>

oci\_fetch\_row
===============

Returns the next row from a query as a numeric array

### Description

<span class="type">array</span> <span
class="methodname">oci\_fetch\_row</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> )

Returns a numerically indexed array containing the next result-set row
of a query. Each array entry corresponds to a column of the row. This
function is typically called in a loop until it returns **`false`**,
indicating no more rows exist.

Calling <span class="function">oci\_fetch\_row</span> is identical to
calling <span class="function">oci\_fetch\_array</span> with
**`OCI_NUM`** + **`OCI_RETURN_NULLS`**.

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>, or a *REF CURSOR* statement
identifier.

### Return Values

Returns a numerically indexed array. If there are no more rows in the
`statement` then **`false`** is returned.

### Examples

**Example \#1 <span class="function">oci\_fetch\_row</span> Example**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT department_id, department_name FROM departments');
oci_execute($stid);

while (($row = oci_fetch_row($stid)) != false) {
    echo $row[0] . " " . $row[1] . "<br>\n";
}

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> See <span class="function">oci\_fetch\_array</span> for more examples
> of fetching rows.

### See Also

-   <span class="function">oci\_fetch</span>
-   <span class="function">oci\_fetch\_all</span>
-   <span class="function">oci\_fetch\_array</span>
-   <span class="function">oci\_fetch\_assoc</span>
-   <span class="function">oci\_fetch\_object</span>

oci\_fetch
==========

Fetches the next row from a query into internal buffers

### Description

<span class="type">bool</span> <span
class="methodname">oci\_fetch</span> ( <span class="methodparam"><span
class="type">resource</span> `$statement`</span> )

Fetches the next row from a query into internal buffers accessible
either with <span class="function">oci\_result</span>, or by using
variables previously defined with <span
class="function">oci\_define\_by\_name</span>.

See <span class="function">oci\_fetch\_array</span> for general
information about fetching data.

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>, or a *REF CURSOR* statement
identifier.

### Return Values

Returns **`true`** on success or **`false`** if there are no more rows
in the `statement`.

### Examples

**Example \#1 <span class="function">oci\_fetch</span> with defined
variables**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'SELECT location_id, city FROM locations WHERE location_id < 1200';
$stid = oci_parse($conn, $sql);

// The defines MUST be done before executing
oci_define_by_name($stid, 'LOCATION_ID', $locid);
oci_define_by_name($stid, 'CITY', $city);

oci_execute($stid);

// Each fetch populates the previously defined variables with the next row's data
while (oci_fetch($stid)) {
    echo "Location id $locid is $city<br>\n";
}

// Displays:
//   Location id 1000 is Roma
//   Location id 1100 is Venice

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 <span class="function">oci\_fetch</span> with <span
class="function">oci\_result</span>**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'SELECT location_id, city FROM locations WHERE location_id < 1200';
$stid = oci_parse($conn, $sql);
oci_execute($stid);

while (oci_fetch($stid)) {
    echo oci_result($stid, 'LOCATION_ID') . " is ";
    echo oci_result($stid, 'CITY') . "<br>\n";
}

// Displays:
//   1000 is Roma
//   1100 is Venice

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> Will not return rows from Oracle Database Implicit Result Sets. Use
> <span class="function">oci\_fetch\_array</span> instead.

### See Also

-   <span class="function">oci\_define\_by\_name</span>
-   <span class="function">oci\_fetch\_all</span>
-   <span class="function">oci\_fetch\_array</span>
-   <span class="function">oci\_fetch\_assoc</span>
-   <span class="function">oci\_fetch\_object</span>
-   <span class="function">oci\_fetch\_row</span>
-   <span class="function">oci\_result</span>

oci\_field\_is\_null
====================

Checks if a field in the currently fetched row is **`null`**

### Description

<span class="type">bool</span> <span
class="methodname">oci\_field\_is\_null</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$field`</span> )

Checks if the given `field` from the current row of `statement` is
**`null`**.

### Parameters

`statement`  
A valid OCI statement identifier.

`field`  
Can be the field's index (1-based) or name.

### Return Values

Returns **`true`** if `field` is **`null`**, **`false`** otherwise.

### Examples

**Example \#1 <span class="function">oci\_field\_name</span> example**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (c1 NUMBER);
//   INSERT INTO mytab VALUES (1);
//   INSERT INTO mytab VALUES (NULL);

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, "SELECT * FROM mytab");
oci_execute($stid);

while (($row = oci_fetch_array($stid, OCI_RETURN_NULLS)) != false) {
    $ncols = oci_num_fields($stid);
    for ($col = 1; $col <= $ncols; $col++) {
        var_dump(oci_field_is_null($stid, $col));
    }    
}

// Outputs:
//    bool(false)
//    bool(true)

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocicolumnisnull</span> instead. This name still can
> be used, it was left as alias of <span
> class="function">oci\_field\_is\_null</span> for downwards
> compatability. This, however, is deprecated and not recommended.

oci\_field\_name
================

Returns the name of a field from the statement

### Description

<span class="type">string</span> <span
class="methodname">oci\_field\_name</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$field`</span> )

Returns the name of the `field`.

### Parameters

`statement`  
A valid OCI statement identifier.

`field`  
Can be the field's index (1-based) or name.

### Return Values

Returns the name as a string, or **`false`** on errors.

### Examples

**Example \#1 <span class="function">oci\_field\_name</span> example**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (number_col NUMBER, varchar2_col varchar2(1),
//                       clob_col CLOB, date_col DATE);

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, "SELECT * FROM mytab");
oci_execute($stid, OCI_DESCRIBE_ONLY); // Use OCI_DESCRIBE_ONLY if not fetching rows

echo "<table border=\"1\">\n";
echo "<tr>";
echo "<th>Name</th>";
echo "<th>Type</th>";
echo "<th>Length</th>";
echo "</tr>\n";

$ncols = oci_num_fields($stid);

for ($i = 1; $i <= $ncols; $i++) {
    $column_name  = oci_field_name($stid, $i);
    $column_type  = oci_field_type($stid, $i);

    echo "<tr>";
    echo "<td>$column_name</td>";
    echo "<td>$column_type</td>";
    echo "</tr>\n";
}

echo "</table>\n";

// Outputs:
//    Name           Type
//    NUMBER_COL    NUMBER
//    VARCHAR2_COL  VARCHAR2
//    CLOB_COL      CLOB
//    DATE_COL      DATE

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocicolumnname</span> instead. This name still can be
> used, it was left as alias of <span
> class="function">oci\_field\_name</span> for downwards compatability.
> This, however, is deprecated and not recommended.

### See Also

-   <span class="function">oci\_num\_fields</span>
-   <span class="function">oci\_field\_type</span>
-   <span class="function">oci\_field\_size</span>

oci\_field\_precision
=====================

Tell the precision of a field

### Description

<span class="type">int</span> <span
class="methodname">oci\_field\_precision</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$field`</span> )

Returns precision of the `field`.

For FLOAT columns, precision is nonzero and scale is -127. If precision
is 0, then column is NUMBER. Else it's NUMBER(precision, scale).

### Parameters

`statement`  
A valid OCI statement identifier.

`field`  
Can be the field's index (1-based) or name.

### Return Values

Returns the precision as an integer, or **`false`** on errors.

### Examples

**Example \#1 <span class="function">oci\_field\_precision</span>
Example**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (c1 NUMBER, c2 FLOAT, c3 NUMBER(4), c4 NUMBER(5,3));

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, "SELECT * FROM mytab");
oci_execute($stid, OCI_DESCRIBE_ONLY); // Use OCI_DESCRIBE_ONLY if not fetching rows

$ncols = oci_num_fields($stid);
for ($i = 1; $i <= $ncols; $i++) {
    echo oci_field_name($stid, $i) . " " 
        . oci_field_precision($stid, $i) . " " 
        . oci_field_scale($stid, $i) . "<br>\n";
}

// Outputs:
//   C1    0 -127
//   C2  126 -127
//   C3    4    0
//   C4    5    3

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocicolumnprecision</span> instead. This name still
> can be used, it was left as alias of <span
> class="function">oci\_field\_precision</span> for downwards
> compatability. This, however, is deprecated and not recommended.

### See Also

-   <span class="function">oci\_field\_scale</span>
-   <span class="function">oci\_field\_type</span>

oci\_field\_scale
=================

Tell the scale of the field

### Description

<span class="type">int</span> <span
class="methodname">oci\_field\_scale</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$field`</span> )

Returns the scale of the column with `field` index.

For FLOAT columns, precision is nonzero and scale is -127. If precision
is 0, then column is NUMBER. Else it's NUMBER(precision, scale).

### Parameters

`statement`  
A valid OCI statement identifier.

`field`  
Can be the field's index (1-based) or name.

### Return Values

Returns the scale as an integer, or **`false`** on errors.

### Examples

**Example \#1 <span class="function">oci\_field\_scale</span> Example**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (c1 NUMBER, c2 FLOAT, c3 NUMBER(4), c4 NUMBER(5,3));

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, "SELECT * FROM mytab");
oci_execute($stid, OCI_DESCRIBE_ONLY); // Use OCI_DESCRIBE_ONLY if not fetching rows

$ncols = oci_num_fields($stid);
for ($i = 1; $i <= $ncols; $i++) {
    echo oci_field_name($stid, $i) . " " 
        . oci_field_precision($stid, $i) . " " 
        . oci_field_scale($stid, $i) . "<br>\n";
}

// Outputs:
//   C1    0 -127
//   C2  126 -127
//   C3    4    0
//   C4    5    3

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocicolumnscale</span> instead. This name still can be
> used, it was left as alias of <span
> class="function">oci\_field\_scale</span> for downwards compatability.
> This, however, is deprecated and not recommended.

### See Also

-   <span class="function">oci\_field\_precision</span>
-   <span class="function">oci\_field\_type</span>

oci\_field\_size
================

Returns field's size

### Description

<span class="type">int</span> <span
class="methodname">oci\_field\_size</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$field`</span> )

Returns the size of a `field`.

### Parameters

`statement`  
A valid OCI statement identifier.

`field`  
Can be the field's index (1-based) or name.

### Return Values

Returns the size of a `field` in bytes, or **`false`** on errors.

### Examples

**Example \#1 <span class="function">oci\_field\_size</span> example**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (number_col NUMBER, varchar2_col varchar2(1), 
//                       clob_col CLOB, date_col DATE);

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, "SELECT * FROM mytab");
oci_execute($stid, OCI_DESCRIBE_ONLY); // Use OCI_DESCRIBE_ONLY if not fetching rows

echo "<table border=\"1\">\n";
echo "<tr>";
echo "<th>Name</th>";
echo "<th>Type</th>";
echo "<th>Length</th>";
echo "</tr>\n";

$ncols = oci_num_fields($stid);

for ($i = 1; $i <= $ncols; $i++) {
    $column_name  = oci_field_name($stid, $i);
    $column_type  = oci_field_type($stid, $i);
    $column_size  = oci_field_size($stid, $i);

    echo "<tr>";
    echo "<td>$column_name</td>";
    echo "<td>$column_type</td>";
    echo "<td>$column_size</td>";
    echo "</tr>\n";
}

echo "</table>\n";

// Outputs:
//    Name           Type       Length
//    NUMBER_COL    NUMBER        22
//    VARCHAR2_COL  VARCHAR2       1
//    CLOB_COL      CLOB        4000
//    DATE_COL      DATE           7

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocicolumnsize</span> instead. This name still can be
> used, it was left as alias of <span
> class="function">oci\_field\_size</span> for downwards compatability.
> This, however, is deprecated and not recommended.

### See Also

-   <span class="function">oci\_num\_fields</span>
-   <span class="function">oci\_field\_name</span>

oci\_field\_type\_raw
=====================

Tell the raw Oracle data type of the field

### Description

<span class="type">int</span> <span
class="methodname">oci\_field\_type\_raw</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$field`</span> )

Returns Oracle's raw "SQLT" data type of the `field`.

If you want a field's type name, then use <span
class="function">oci\_field\_type</span> instead.

### Parameters

`statement`  
A valid OCI statement identifier.

`field`  
Can be the field's index (1-based) or name.

### Return Values

Returns Oracle's raw data type as a number, or **`false`** on errors.

### Examples

**Example \#1 <span class="function">oci\_field\_type\_raw</span>
Example**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (number_col NUMBER, varchar2_col varchar2(1), clob_col CLOB, date_col DATE);

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, 'select * from mytab');
oci_execute($stid, OCI_DESCRIBE_ONLY);  // Use OCI_DESCRIBE_ONLY if not fetching rows
$n = oci_num_fields($stid);
for ($i = 1; $i <= $n; ++$i) {
    echo oci_field_name($stid, $i) . " is raw type: " . oci_field_type_raw($stid, $i) . "<br>\n";
}

// Output is:
//    NUMBER_COL is raw type: 2
//    VARCHAR2_COL is raw type: 1
//    CLOB_COL is raw type: 112
//    DATE_COL is raw type: 12

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocicolumntyperaw</span> instead. This name still can
> be used, it was left as alias of <span
> class="function">oci\_field\_type\_raw</span> for downwards
> compatability. This, however, is deprecated and not recommended.

oci\_field\_type
================

Returns a field's data type name

### Description

<span class="type">mixed</span> <span
class="methodname">oci\_field\_type</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$field`</span> )

Returns a field's data type name.

### Parameters

`statement`  
A valid OCI statement identifier.

`field`  
Can be the field's index (1-based) or name.

### Return Values

Returns the field data type as a string, or **`false`** on errors.

### Examples

**Example \#1 <span class="function">oci\_field\_type</span> example**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (number_col NUMBER, varchar2_col varchar2(1), 
//                       clob_col CLOB, date_col DATE);

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, "SELECT * FROM mytab");
oci_execute($stid, OCI_DESCRIBE_ONLY); // Use OCI_DESCRIBE_ONLY if not fetching rows

echo "<table border=\"1\">\n";
echo "<tr>";
echo "<th>Name</th>";
echo "<th>Type</th>";
echo "<th>Length</th>";
echo "</tr>\n";

$ncols = oci_num_fields($stid);

for ($i = 1; $i <= $ncols; $i++) {
    $column_name  = oci_field_name($stid, $i);
    $column_type  = oci_field_type($stid, $i);
    $column_size  = oci_field_size($stid, $i);

    echo "<tr>";
    echo "<td>$column_name</td>";
    echo "<td>$column_type</td>";
    echo "<td>$column_size</td>";
    echo "</tr>\n";
}

echo "</table>\n";

// Outputs:
//    Name           Type       Length
//    NUMBER_COL    NUMBER        22
//    VARCHAR2_COL  VARCHAR2       1
//    CLOB_COL      CLOB        4000
//    DATE_COL      DATE           7

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocicolumntype</span> instead. This name still can be
> used, it was left as alias of <span
> class="function">oci\_field\_type</span> for downwards compatability.
> This, however, is deprecated and not recommended.

### See Also

-   <span class="function">oci\_num\_fields</span>
-   <span class="function">oci\_field\_name</span>
-   <span class="function">oci\_field\_size</span>

oci\_free\_descriptor
=====================

Frees a descriptor

### Description

<span class="type">bool</span> <span
class="methodname">oci\_free\_descriptor</span> ( <span
class="methodparam"><span class="type">resource</span>
`$descriptor`</span> )

Frees a descriptor allocated by <span
class="function">oci\_new\_descriptor</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Notes

> **Note**:
>
> This function is commonly used as a method
> <a href="/book/oci8.html#OCILob::free" class="link">OCILOB::free</a>.

### See Also

-   <a href="/book/oci8.html#OCILob::free" class="link">OCILOB::free</a>

oci\_free\_statement
====================

Frees all resources associated with statement or cursor

### Description

<span class="type">bool</span> <span
class="methodname">oci\_free\_statement</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> )

Frees resources associated with Oracle's cursor or statement, which was
received from as a result of <span class="function">oci\_parse</span> or
obtained from Oracle.

### Parameters

`statement`  
A valid OCI statement identifier.

### Return Values

Returns **`true`** on success or **`false`** on failure.

oci\_get\_implicit\_resultset
=============================

Returns the next child statement resource from a parent statement
resource that has Oracle Database Implicit Result Sets

### Description

<span class="type">resource </span> <span
class="methodname">oci\_get\_implicit\_resultset</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> )

Used to fetch consectutive sets of query results after the execution of
a stored or anonymous Oracle PL/SQL block where that block returns query
results with the Oracle Database 12 (or later)
*DBMS\_SQL.RETURN\_RESULT* PL/SQL function. This allows PL/SQL blocks to
easily return query results.

The child statement can be used with any of the OCI8 fetching functions:
<span class="function">oci\_fetch</span>, <span
class="function">oci\_fetch\_all</span>, <span
class="function">oci\_fetch\_array</span>, <span
class="function">oci\_fetch\_object</span>, <span
class="function">oci\_fetch\_assoc</span> or <span
class="function">oci\_fetch\_row</span>

Child statements inherit their parent statement's prefetch value, or it
can be explicitly set with <span
class="function">oci\_set\_prefetch</span>.

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>. The statement identifier may or
may not be associated with a SQL statement that returns Implicit Result
Sets.

### Return Values

Returns a statement handle for the next child statement available on
`statement`. Returns **`false`** when child statements do not exist, or
all child statements have been returned by previous calls to <span
class="function">oci\_get\_implicit\_resultset</span>.

### Examples

**Example \#1 Fetching Implicit Result Sets in a loop**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/pdborcl');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'DECLARE
            c1 SYS_REFCURSOR;
        BEGIN
           OPEN c1 FOR SELECT city, postal_code FROM locations WHERE ROWNUM < 4 ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
           OPEN c1 FOR SELECT country_id FROM locations WHERE ROWNUM < 4 ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
        END;';

$stid = oci_parse($conn, $sql);
oci_execute($stid);

while (($stid_c = oci_get_implicit_resultset($stid))) {
    echo "<h2>New Implicit Result Set:</h2>\n";
    echo "<table>\n";
    while (($row = oci_fetch_array($stid_c, OCI_ASSOC+OCI_RETURN_NULLS)) != false) {
        echo "<tr>\n";
        foreach ($row as $item) {
            echo "  <td>".($item!==null?htmlentities($item, ENT_QUOTES|ENT_SUBSTITUTE):"&nbsp;")."</td>\n";
        }
        echo "</tr>\n";
    }
    echo "</table>\n";
}

// Output is:
//    New Implicit Result Set:
//     Beijing 190518
//     Bern    3095
//     Bombay  490231
//    New Implicit Result Set:
//     CN
//     CH
//     IN

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 Getting child statement handles individually**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/pdborcl');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'DECLARE
            c1 SYS_REFCURSOR;
        BEGIN
           OPEN c1 FOR SELECT city, postal_code FROM locations WHERE ROWNUM < 4 ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
           OPEN c1 FOR SELECT country_id FROM locations WHERE ROWNUM < 4 ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
        END;';

$stid = oci_parse($conn, $sql);
oci_execute($stid);

$stid_1 = oci_get_implicit_resultset($stid);
$stid_2 = oci_get_implicit_resultset($stid);

$row = oci_fetch_array($stid_1, OCI_ASSOC+OCI_RETURN_NULLS);
var_dump($row);
$row = oci_fetch_array($stid_2, OCI_ASSOC+OCI_RETURN_NULLS);
var_dump($row);
$row = oci_fetch_array($stid_1, OCI_ASSOC+OCI_RETURN_NULLS);
var_dump($row);
$row = oci_fetch_array($stid_2, OCI_ASSOC+OCI_RETURN_NULLS);
var_dump($row);

// Output is:
//    array(2) {
//      ["CITY"]=>
//      string(7) "Beijing"
//      ["POSTAL_CODE"]=>
//      string(6) "190518"
//    }
//    array(1) {
//      ["COUNTRY_ID"]=>
//      string(2) "CN"
//    }
//    array(2) {
//      ["CITY"]=>
//      string(4) "Bern"
//      ["POSTAL_CODE"]=>
//      string(4) "3095"
//    }
//    array(1) {
//      ["COUNTRY_ID"]=>
//      string(2) "CH"
//    }

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#3 Explicitly setting the Prefetch Count**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/pdborcl');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'DECLARE
            c1 SYS_REFCURSOR;
        BEGIN
           OPEN c1 FOR SELECT city, postal_code FROM locations ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
        END;';

$stid = oci_parse($conn, $sql);
oci_execute($stid);

$stid_c = oci_get_implicit_resultset($stid);
oci_set_prefetch($stid_c, 200);   // Set the prefetch before fetching from the child statement
echo "<table>\n";
while (($row = oci_fetch_array($stid_c, OCI_ASSOC+OCI_RETURN_NULLS)) != false) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "  <td>".($item!==null?htmlentities($item, ENT_QUOTES|ENT_SUBSTITUTE):"&nbsp;")."</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#4 Implicit Result Set example without using <span
class="function">oci\_get\_implicit\_resultset</span>**

All results from all queries are returned consecutively.

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/pdborcl');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'DECLARE
            c1 SYS_REFCURSOR;
        BEGIN
           OPEN c1 FOR SELECT city, postal_code FROM locations WHERE ROWNUM < 4 ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
           OPEN c1 FOR SELECT country_id FROM locations WHERE ROWNUM < 4 ORDER BY city;
           DBMS_SQL.RETURN_RESULT(c1);
        END;';

$stid = oci_parse($conn, $sql);
oci_execute($stid);

// Note: oci_fetch_all and oci_fetch() cannot be used in this manner
echo "<table>\n";
while (($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) != false) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "  <td>".($item!==null?htmlentities($item, ENT_QUOTES|ENT_SUBSTITUTE):"&nbsp;")."</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

// Output is:
//    Beijing 190518
//    Bern 3095
//    Bombay 490231
//    CN
//    CH
//    IN

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> For queries returning a large number of rows, performance can be
> significantly improved by increasing
> <a href="/book/oci8.html#" class="link">oci8.default_prefetch</a> or
> using <span class="function">oci\_set\_prefetch</span>.

oci\_lob\_copy
==============

Copies large object

### Description

<span class="type">bool</span> <span
class="methodname">oci\_lob\_copy</span> ( <span
class="methodparam"><span class="type">OCILob</span> `$lob_to`</span> ,
<span class="methodparam"><span class="type">OCILob</span>
`$lob_from`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`<span class="initializer"> =
0</span></span> \] )

Copies a large object or a part of a large object to another large
object. Old LOB-recipient data will be overwritten.

If you need to copy a particular part of a LOB to a particular position
of a LOB, use <span class="function">OCILob::seek</span> to move LOB
internal pointers.

### Parameters

`lob_to`  
The destination LOB.

`lob_from`  
The copied LOB.

`length`  
Indicates the length of data to be copied.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Notes

> **Note**:
>
> The OCILob class was called OCI-Lob prior to PHP 8 and PECL OCI8
> 3.0.0.

oci\_lob\_is\_equal
===================

Compares two LOB/FILE locators for equality

### Description

<span class="type">bool</span> <span
class="methodname">oci\_lob\_is\_equal</span> ( <span
class="methodparam"><span class="type">OCI-Lob</span> `$lob1`</span> ,
<span class="methodparam"><span class="type">OCI-Lob</span>
`$lob2`</span> )

Compares two LOB/FILE locators.

### Parameters

`lob1`  
A LOB identifier.

`lob2`  
A LOB identifier.

### Return Values

Returns **`true`** if these objects are equal, **`false`** otherwise.

### Notes

> **Note**:
>
> The OCILob class was called OCI-Lob prior to PHP 8 and PECL OCI8
> 3.0.0.

oci\_new\_collection
====================

Allocates new collection object

### Description

<span class="type">OCICollection</span> <span
class="methodname">oci\_new\_collection</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$tdo`</span> \[, <span
class="methodparam"><span class="type">string</span> `$schema`<span
class="initializer"> = **`null`**</span></span> \] )

Allocates a new collection object.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span> or <span
class="function">oci\_pconnect</span>.

`tdo`  
Should be a valid named type (uppercase).

`schema`  
Should point to the scheme, where the named type was created. The name
of the current user is the default value.

### Return Values

Returns a new <span class="classname">OCICollection</span> object or
**`false`** on error.

### Notes

> **Note**:
>
> The OCICollection class was called OCI-Collection prior to PHP 8 and
> OCI8 3.0.0.

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocinewcollection</span> instead. This name still can
> be used, it was left as alias of <span
> class="function">oci\_new\_collection</span> for downwards
> compatability. This, however, is deprecated and not recommended.

oci\_new\_connect
=================

Connect to the Oracle server using a unique connection

### Description

<span class="type">resource</span> <span
class="methodname">oci\_new\_connect</span> ( <span
class="methodparam"><span class="type">string</span> `$username`</span>
, <span class="methodparam"><span class="type">string</span>
`$password`</span> \[, <span class="methodparam"><span
class="type">string</span> `$connection_string`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$character_set`</span> \[, <span class="methodparam"><span
class="type">int</span> `$session_mode`</span> \]\]\] )

Establishes a new connection to an Oracle server and logs on.

Unlike <span class="function">oci\_connect</span> and <span
class="function">oci\_pconnect</span>, <span
class="function">oci\_new\_connect</span> does not cache connections and
will always return a brand-new freshly opened connection handle. This is
useful if your application needs transactional isolation between two
sets of queries.

### Parameters

`username`  
The Oracle user name.

`password`  
The password for `username`.

`connection_string`  
Contains the *Oracle instance* to connect to. It can be an
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-E5358DEA-D619-4B7B-A799-3D2F802500F1" class="link external">» Easy Connect string</a>,
or a Connect Name from the `tnsnames.ora` file, or the name of a local
Oracle instance.

If not specified, PHP uses environment variables such as **`TWO_TASK`**
(on Linux) or **`LOCAL`** (on Windows) and **`ORACLE_SID`** to determine
the *Oracle instance* to connect to.

To use the Easy Connect naming method, PHP must be linked with Oracle
10*g* or greater Client libraries. The Easy Connect string for Oracle
10*g* is of the form: *\[//\]host\_name\[:port\]\[/service\_name\]*.
From Oracle 11*g*, the syntax is:
*\[//\]host\_name\[:port\]\[/service\_name\]\[:server\_type\]\[/instance\_name\]*.
Futher options were introduced with Oracle 19c, including timeout and
keep-alive settings. Refer to Oracle documentation. Service names can be
found by running the Oracle utility *lsnrctl status* on the database
server machine.

The `tnsnames.ora` file can be in the Oracle Net search path, which
includes `/your/path/to/instantclient/network/admin`,
`$ORACLE_HOME/network/admin` and `/etc`. Alternatively set *TNS\_ADMIN*
so that `$TNS_ADMIN/tnsnames.ora` is read. Make sure the web daemon has
read access to the file.

`character_set`  
Determines the character set used by the Oracle Client libraries. The
character set does not need to match the character set used by the
database. If it doesn't match, Oracle will do its best to convert data
to and from the database character set. Depending on the character sets
this may not give usable results. Conversion also adds some time
overhead.

If not specified, the Oracle Client libraries determine a character set
from the **`NLS_LANG`** environment variable.

Passing this parameter can reduce the time taken to connect.

`session_mode`  
This parameter is available since version PHP 5 (PECL OCI8 1.1) and
accepts the following values: **`OCI_DEFAULT`**, **`OCI_SYSOPER`** and
**`OCI_SYSDBA`**. If either **`OCI_SYSOPER`** or **`OCI_SYSDBA`** were
specified, this function will try to establish privileged connection
using external credentials. Privileged connections are disabled by
default. To enable them you need to set
<a href="/book/oci8.html#" class="link">oci8.privileged_connect</a> to
*On*.

PHP 5.3 (PECL OCI8 1.3.4) introduced the **`OCI_CRED_EXT`** mode value.
This tells Oracle to use External or OS authentication, which must be
configured in the database. The **`OCI_CRED_EXT`** flag can only be used
with username of "/" and a empty password.
<a href="/book/oci8.html#" class="link">oci8.privileged_connect</a> may
be *On* or *Off*.

**`OCI_CRED_EXT`** may be combined with the **`OCI_SYSOPER`** or
**`OCI_SYSDBA`** modes.

**`OCI_CRED_EXT`** is not supported on Windows for security reasons.

### Return Values

Returns a connection identifier or **`false`** on error.

### Examples

The following demonstrates how you can separate connections.

**Example \#1 <span class="function">oci\_new\_connect</span> example**

``` php
<?php

// create table mytab (mycol number);

function query($name, $c)
{
    echo "Querying $name\n";
    $s = oci_parse($c, "select * from mytab");
    oci_execute($s, OCI_NO_AUTO_COMMIT);
    $row = oci_fetch_array($s, OCI_ASSOC);
    if (!$row) {
        echo "No rows\n";
    } else {
        do {
            foreach ($row as $item)
                echo $item . " ";
            echo "\n";
        } while (($row = oci_fetch_array($s, OCI_ASSOC)) != false);
    }
}

$c1 = oci_connect("hr", "welcome", "localhost/orcl");
$c2 = oci_new_connect("hr", "welcome", "localhost/orcl");

$s = oci_parse($c1, "insert into mytab values(1234)");
oci_execute($s, OCI_NO_AUTO_COMMIT);

query("basic connection", $c1);
query("new connection", $c2);
oci_commit($c1);
query("new connection after commit", $c2);

// Output is:
//   Querying basic connection
//   1234 
//   Querying new connection
//   No rows
//   Querying new connection after commit
//   1234 

?>
```

See <span class="function">oci\_connect</span> for further examples of
parameter usage.

### See Also

-   <span class="function">oci\_connect</span>
-   <span class="function">oci\_pconnect</span>

oci\_new\_cursor
================

Allocates and returns a new cursor (statement handle)

### Description

<span class="type">resource</span> <span
class="methodname">oci\_new\_cursor</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

Allocates a new statement handle on the specified connection.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span> or <span
class="function">oci\_pconnect</span>.

### Return Values

Returns a new statement handle, or **`false`** on error.

### Examples

**Example \#1 Binding a REF CURSOR in an Oracle stored procedure call**

``` php
<?php

// Precreate:
//   create or replace procedure myproc(myrc out sys_refcursor) as
//   begin
//     open myrc for select first_name from employees;
//   end;

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$curs = oci_new_cursor($conn);
$stid = oci_parse($conn, "begin myproc(:cursbv); end;");
oci_bind_by_name($stid, ":cursbv", $curs, -1, OCI_B_CURSOR);
oci_execute($stid);

oci_execute($curs);  // Execute the REF CURSOR like a normal statement id
while (($row = oci_fetch_array($curs, OCI_ASSOC+OCI_RETURN_NULLS)) != false) {
    echo $row['FIRST_NAME'] . "<br />\n";
}

oci_free_statement($stid);
oci_free_statement($curs);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocinewcursor</span> instead. This name still can be
> used, it was left as alias of <span
> class="function">oci\_new\_cursor</span> for downwards compatability.
> This, however, is deprecated and not recommended.

oci\_new\_descriptor
====================

Initializes a new empty LOB or FILE descriptor

### Description

<span class="type">OCI-Lob</span> <span
class="methodname">oci\_new\_descriptor</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`<span class="initializer"> =
OCI\_DTYPE\_LOB</span></span> \] )

Allocates resources to hold descriptor or LOB locator.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span> or <span
class="function">oci\_pconnect</span>.

`type`  
Valid values for `type` are: **`OCI_DTYPE_FILE`**, **`OCI_DTYPE_LOB`**
and **`OCI_DTYPE_ROWID`**.

### Return Values

Returns a new LOB or FILE descriptor on success, **`false`** on error.

### Examples

**Example \#1 <span class="function">oci\_new\_descriptor</span>
example**

``` php
<?php
/* This script is designed to be called from a HTML form.
 * It expects $user, $password, $table, $where, and $commitsize
 * to be passed in from the form.  The script then deletes
 * the selected rows using the ROWID and commits after each
 * set of $commitsize rows. (Use with care, there is no rollback)
 */
$conn = oci_connect($user, $password);
$stmt = oci_parse($conn, "select rowid from $table $where");
$rowid = oci_new_descriptor($conn, OCI_D_ROWID);
oci_define_by_name($stmt, "ROWID", $rowid);
oci_execute($stmt);
while (oci_fetch($stmt)) {
    $nrows = oci_num_rows($stmt);
    $delete = oci_parse($conn, "delete from $table where ROWID = :rid");
    oci_bind_by_name($delete, ":rid", $rowid, -1, OCI_B_ROWID);
    oci_execute($delete);
    echo "$nrows\n";
    if (($nrows % $commitsize) == 0) {
        oci_commit($conn);
    }
}
$nrows = oci_num_rows($stmt);
echo "$nrows deleted...\n";
oci_free_statement($stmt);
oci_close($conn);
?>
```

``` php
<?php
    /* This script demonstrates file upload to LOB columns
     * The formfield used for this example looks like this
     * <form action="upload.php" method="post" enctype="multipart/form-data">
     * <input type="file" name="lob_upload" />
     * ...
     */
  if (!isset($lob_upload) || $lob_upload == 'none'){
?>
<form action="upload.php" method="post" enctype="multipart/form-data">
Upload file: <input type="file" name="lob_upload" /><br />
<input type="submit" value="Upload" /> - <input type="reset" value="Reset" />
</form>
<?php
  } else {

     // $lob_upload contains the temporary filename of the uploaded file

     // see also the features section on file upload,
     // if you would like to use secure uploads

     $conn = oci_connect($user, $password);
     $lob = oci_new_descriptor($conn, OCI_D_LOB);
     $stmt = oci_parse($conn, "insert into $table (id, the_blob)
               values(my_seq.NEXTVAL, EMPTY_BLOB()) returning the_blob into :the_blob");
     oci_bind_by_name($stmt, ':the_blob', $lob, -1, OCI_B_BLOB);
     oci_execute($stmt, OCI_DEFAULT);
     if ($lob->savefile($lob_upload)){
        oci_commit($conn);
        echo "Blob successfully uploaded\n";
     }else{
        echo "Couldn't upload Blob\n";
     }
     $lob->free();
     oci_free_statement($stmt);
     oci_close($conn);
  }
?>
```

**Example \#2 <span class="function">oci\_new\_descriptor</span>
example**

``` php
<?php
/* Calling PL/SQL stored procedures which contain clobs as input
 * parameters.
 * Example PL/SQL stored procedure signature is:
 *
 * PROCEDURE save_data
 *   Argument Name                  Type                    In/Out Default?
 *   ------------------------------ ----------------------- ------ --------
 *   KEY                            NUMBER(38)              IN
 *   DATA                           CLOB                    IN
 *
 */

$conn = oci_connect($user, $password);
$stmt = oci_parse($conn, "begin save_data(:key, :data); end;");
$clob = oci_new_descriptor($conn, OCI_D_LOB);
oci_bind_by_name($stmt, ':key', $key);
oci_bind_by_name($stmt, ':data', $clob, -1, OCI_B_CLOB);
$clob->write($data);
oci_execute($stmt, OCI_DEFAULT);
oci_commit($conn);
$clob->free();
oci_free_statement($stmt);
?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocinewdescriptor</span> instead. This name still can
> be used, it was left as alias of <span
> class="function">oci\_new\_descriptor</span> for downwards
> compatability. This, however, is deprecated and not recommended.

### See Also

-   <span class="function">oci\_bind\_by\_name</span>

oci\_num\_fields
================

Returns the number of result columns in a statement

### Description

<span class="type">int</span> <span
class="methodname">oci\_num\_fields</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> )

Gets the number of columns in the given `statement`.

### Parameters

`statement`  
A valid OCI statement identifier.

### Return Values

Returns the number of columns as an integer, or **`false`** on errors.

### Examples

**Example \#1 <span class="function">oci\_num\_fields</span> example**

``` php
<?php

// Create the table with:
//   CREATE TABLE mytab (id NUMBER, quantity NUMBER);

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, "SELECT * FROM mytab");
oci_execute($stid, OCI_DESCRIBE_ONLY); // Use OCI_DESCRIBE_ONLY if not fetching rows

$ncols = oci_num_fields($stid);
for ($i = 1; $i <= $ncols; $i++) {
    echo oci_field_name($stid, $i) . " " . oci_field_type($stid, $i) . "<br>\n";
}

// Outputs:
//    ID NUMBER
//    QUANTITY NUMBER

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocinumcols</span> instead. This name still can be
> used, it was left as alias of <span
> class="function">oci\_num\_fields</span> for downwards compatability.
> This, however, is deprecated and not recommended.

oci\_num\_rows
==============

Returns number of rows affected during statement execution

### Description

<span class="type">int</span> <span
class="methodname">oci\_num\_rows</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> )

Gets the number of rows affected during statement execution.

### Parameters

`statement`  
A valid OCI statement identifier.

### Return Values

Returns the number of rows affected as an integer, or **`false`** on
errors.

### Examples

**Example \#1 <span class="function">oci\_num\_rows</span> example**

``` php
<?php

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
if (!$conn) {
    $m = oci_error();
    trigger_error(htmlentities($m['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, "create table emp2 as select * from employees");
oci_execute($stid);
echo oci_num_rows($stid) . " rows inserted.<br />\n";
oci_free_statement($stid);

$stid = oci_parse($conn, "delete from emp2");
oci_execute($stid, OCI_DEFAULT);
echo oci_num_rows($stid) . " rows deleted.<br />\n";
oci_commit($conn);
oci_free_statement($stid);

$stid = oci_parse($conn, "drop table emp2");
oci_execute($stid);
oci_free_statement($stid);

oci_close($conn);

?>
```

### Notes

> **Note**:
>
> This function *does not* return number of rows selected! For SELECT
> statements this function will return the number of rows, that were
> fetched to the buffer with <span class="function">oci\_fetch\*</span>
> functions.

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocirowcount</span> instead. This name still can be
> used, it was left as alias of <span
> class="function">oci\_num\_rows</span> for downwards compatability.
> This, however, is deprecated and not recommended.

oci\_parse
==========

Prepares an Oracle statement for execution

### Description

<span class="type">resource</span> <span
class="methodname">oci\_parse</span> ( <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span> `$sql_text`</span>
)

Prepares `sql_text` using `connection` and returns the statement
identifier, which can be used with <span
class="function">oci\_bind\_by\_name</span>, <span
class="function">oci\_execute</span> and other functions.

Statement identifiers can be freed with <span
class="function">oci\_free\_statement</span> or by setting the variable
to **`null`**.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

`sql_text`  
The SQL or PL/SQL statement.

SQL statements *should not* end with a semi-colon (";"). PL/SQL
statements *should* end with a semi-colon (";").

### Return Values

Returns a statement handle on success, or **`false`** on error.

### Examples

**Example \#1 <span class="function">oci\_parse</span> example for SQL
statements**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

// Parse the statement. Note there is no final semi-colon in the SQL statement
$stid = oci_parse($conn, 'SELECT * FROM employees');
oci_execute($stid);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>" . ($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;") . "</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

?>
```

**Example \#2 <span class="function">oci\_parse</span> example for
PL/SQL statements**

``` php
<?php

/*
  Before running the PHP program, create a stored procedure in
  SQL*Plus or SQL Developer:

  CREATE OR REPLACE PROCEDURE myproc(p1 IN NUMBER, p2 OUT NUMBER) AS
  BEGIN
      p2 := p1 * 2;
  END;

*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$p1 = 8;

// When parsing PL/SQL programs, there should be a final semi-colon in the string
$stid = oci_parse($conn, 'begin myproc(:p1, :p2); end;');
oci_bind_by_name($stid, ':p1', $p1);
oci_bind_by_name($stid, ':p2', $p2, 40);

oci_execute($stid);

print "$p2\n";   // prints 16

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> This function *does not* validate `sql_text`. The only way to find out
> if `sql_text` is a valid SQL or PL/SQL statement is to execute it.

### See Also

-   <span class="function">oci\_execute</span>
-   <span class="function">oci\_free\_statement</span>

oci\_password\_change
=====================

Changes password of Oracle's user

### Description

<span class="type">bool</span> <span
class="methodname">oci\_password\_change</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$username`</span> , <span
class="methodparam"><span class="type">string</span>
`$old_password`</span> , <span class="methodparam"><span
class="type">string</span> `$new_password`</span> )

<span class="type">resource</span> <span
class="methodname">oci\_password\_change</span> ( <span
class="methodparam"><span class="type">string</span> `$dbname`</span> ,
<span class="methodparam"><span class="type">string</span>
`$username`</span> , <span class="methodparam"><span
class="type">string</span> `$old_password`</span> , <span
class="methodparam"><span class="type">string</span>
`$new_password`</span> )

Changes password for user with `username`.

The <span class="function">oci\_password\_change</span> function is most
useful for PHP command-line scripts, or when non-persistent connections
are used throughout the PHP application.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span> or <span
class="function">oci\_pconnect</span>.

`username`  
The Oracle user name.

`old_password`  
The old password.

`new_password`  
The new password to be set.

`dbname`  
The database name.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">oci\_password\_change</span>
example changing the password of an already connected user**

``` php
<?php

$dbase      = 'localhost/orcl';
$user       = 'cj';
$current_pw = 'welcome';
$new_pw     = 'geelong';

$c = oci_pconnect($user, $current_pw, $dbase);
oci_password_change($c, $user, $current_pw, $new_pw);
echo "New password is : " . $new_pw . "\n";

?>
```

**Example \#2 <span class="function">oci\_password\_change</span>
example of connecting and changing the password in one step**

``` php
<?php

$dbase      = 'localhost/orcl';
$user       = 'cj';
$current_pw = 'welcome';
$new_pw     = 'geelong';

$c = oci_pconnect($user, $current_pw, $dbase);
if (!$c) {
    $m = oci_error();
    if ($m['code'] == 28001) { // "ORA-28001: the password has expired"
        // Login and reset password at the same time
        $c = oci_password_change($dbase, $user, $current_pw, $new_pw);
        if ($c) {
            echo "New password is : " . $new_pw . "\n";
        }
    }
}

if (!$c) {  // The original error wasn't 28001, or the password change failed
    $m = oci_error();
    trigger_error('Could not connect to database: '. $m['message'], E_USER_ERROR);
}

// Use the connection $c
...

?>
```

### Notes

> **Note**:
>
> Changing the password either with this function or directly in Oracle
> should be done carefully. This is because PHP applications may
> continue to successfully reuse persistent connections by
> authenticating with the old password. The best practice is to restart
> all web servers whenever the user password is changed.

> **Note**:
>
> If upgrading the Oracle client libraries or the database from a
> release prior to 11.2.0.3 to version 11.2.0.3 or higher, <span
> class="function">oci\_password\_change</span> may give the error
> "ORA-1017: invalid username/password" unless both client and server
> versions are upgraded at the same time.

> **Note**:
>
> The second <span class="function">oci\_password\_change</span> syntax
> is available since OCI8 version 1.1.

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ocipasswordchange</span> instead. This name still can
> be used, it was left as alias of <span
> class="function">oci\_password\_change</span> for downwards
> compatability. This, however, is deprecated and not recommended.

oci\_pconnect
=============

Connect to an Oracle database using a persistent connection

### Description

<span class="type">resource</span> <span
class="methodname">oci\_pconnect</span> ( <span
class="methodparam"><span class="type">string</span> `$username`</span>
, <span class="methodparam"><span class="type">string</span>
`$password`</span> \[, <span class="methodparam"><span
class="type">string</span> `$connection_string`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$character_set`</span> \[, <span class="methodparam"><span
class="type">int</span> `$session_mode`</span> \]\]\] )

Creates a persistent connection to an Oracle server and logs on.

Persistent connections are cached and re-used between requests,
resulting in reduced overhead on each page load; a typical PHP
application will have a single persistent connection open against an
Oracle server per Apache child process (or PHP FPM process). See the
<a href="/book/oci8.html#OCI8%20Connection%20Handling%20and%20Connection%20Pooling" class="link">OCI8 Connection Handling and Connection Pooling</a>
section for more information.

### Parameters

`username`  
The Oracle user name.

`password`  
The password for `username`.

`connection_string`  
Contains the *Oracle instance* to connect to. It can be an
<a href="https://www.oracle.com/pls/topic/lookup?ctx=dblatest&amp;id=GUID-E5358DEA-D619-4B7B-A799-3D2F802500F1" class="link external">» Easy Connect string</a>,
or a Connect Name from the `tnsnames.ora` file, or the name of a local
Oracle instance.

If not specified, PHP uses environment variables such as **`TWO_TASK`**
(on Linux) or **`LOCAL`** (on Windows) and **`ORACLE_SID`** to determine
the *Oracle instance* to connect to.

To use the Easy Connect naming method, PHP must be linked with Oracle
10*g* or greater Client libraries. The Easy Connect string for Oracle
10*g* is of the form: *\[//\]host\_name\[:port\]\[/service\_name\]*.
From Oracle 11*g*, the syntax is:
*\[//\]host\_name\[:port\]\[/service\_name\]\[:server\_type\]\[/instance\_name\]*.
Futher options were introduced with Oracle 19c, including timeout and
keep-alive settings. Refer to Oracle documentation. Service names can be
found by running the Oracle utility *lsnrctl status* on the database
server machine.

The `tnsnames.ora` file can be in the Oracle Net search path, which
includes `/your/path/to/instantclient/network/admin`,
`$ORACLE_HOME/network/admin` and `/etc`. Alternatively set *TNS\_ADMIN*
so that `$TNS_ADMIN/tnsnames.ora` is read. Make sure the web daemon has
read access to the file.

`character_set`  
Determines the character set used by the Oracle Client libraries. The
character set does not need to match the character set used by the
database. If it doesn't match, Oracle will do its best to convert data
to and from the database character set. Depending on the character sets
this may not give usable results. Conversion also adds some time
overhead.

If not specified, the Oracle Client libraries determine a character set
from the **`NLS_LANG`** environment variable.

Passing this parameter can reduce the time taken to connect.

`session_mode`  
This parameter is available since version PHP 5 (PECL OCI8 1.1) and
accepts the following values: **`OCI_DEFAULT`**, **`OCI_SYSOPER`** and
**`OCI_SYSDBA`**. If either **`OCI_SYSOPER`** or **`OCI_SYSDBA`** were
specified, this function will try to establish privileged connection
using external credentials. Privileged connections are disabled by
default. To enable them you need to set
<a href="/book/oci8.html#" class="link">oci8.privileged_connect</a> to
*On*.

PHP 5.3 (PECL OCI8 1.3.4) introduced the **`OCI_CRED_EXT`** mode value.
This tells Oracle to use External or OS authentication, which must be
configured in the database. The **`OCI_CRED_EXT`** flag can only be used
with username of "/" and a empty password.
<a href="/book/oci8.html#" class="link">oci8.privileged_connect</a> may
be *On* or *Off*.

**`OCI_CRED_EXT`** may be combined with the **`OCI_SYSOPER`** or
**`OCI_SYSDBA`** modes.

**`OCI_CRED_EXT`** is not supported on Windows for security reasons.

### Return Values

Returns a connection identifier or **`false`** on error.

### Examples

**Example \#1 Basic <span class="function">oci\_pconnect</span> Example
using Easy Connect syntax**

``` php
<?php

// Connects to the XE service (i.e. database) on the "localhost" machine
$conn = oci_pconnect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$stid = oci_parse($conn, 'SELECT * FROM employees');
oci_execute($stid);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>" . ($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;") . "</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

?>
```

See <span class="function">oci\_connect</span> for further examples of
parameter usage.

### Notes

> **Note**: <span class="simpara"> Starting with PHP 5.1.2 and PECL OCI8
> 1.1, the lifetime and maximum number of persistent Oracle connections
> per PHP process can be tuned by setting the following configuration
> values:
> <a href="/book/oci8.html#" class="link">oci8.persistent_timeout</a>,
> <a href="/book/oci8.html#" class="link">oci8.ping_interval</a> and
> <a href="/book/oci8.html#" class="link">oci8.max_persistent</a>.
> </span>

### See Also

-   <span class="function">oci\_connect</span>
-   <span class="function">oci\_new\_connect</span>

oci\_register\_taf\_callback
============================

Register a user-defined callback function for Oracle Database TAF

### Description

<span class="type">bool</span> <span
class="methodname">oci\_register\_taf\_callback</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$callbackFn`</span> \] )

Registers a user-defined callback function to `connection`. If
`connection` fails due to instance or network failure, the registered
callback function will be invoked for several times during failover. See
<a href="/book/oci8.html#OCI8%20Transparent%20Application%20Failover%20(TAF)%20Support" class="link">OCI8 Transparent Application Failover (TAF) Support</a>
for information.

When <span class="function">oci\_register\_taf\_callback</span> is
called multiple times, each registration overwrites the previous one.

Use <span class="function">oci\_unregister\_taf\_callback</span> to
explicitly unregister a user-defined callback.

TAF callback registration will NOT be saved across persistent
connections, therefore the callback needs to be re-registered for a new
persistent connection.

### Parameters

`connection`  
An Oracle connection identifier.

`callbackFn`  
A user-defined callback to register for Oracle TAF. It can be a string
of the function name or a Closure (anonymous function).

The interface of a TAF user-defined callback function is as follows:

<span class="type">int</span> <span
class="methodname">userCallbackFn</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">int</span> `$event`</span> , <span
class="methodparam"><span class="type">int</span> `$type`</span> )

See the parameter description and an example on
<a href="/book/oci8.html#OCI8%20Transparent%20Application%20Failover%20(TAF)%20Support" class="link">OCI8 Transparent Application Failover (TAF) Support</a>
page.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">oci\_unregister\_taf\_callback</span>

oci\_result
===========

Returns field's value from the fetched row

### Description

<span class="type">mixed</span> <span
class="methodname">oci\_result</span> ( <span class="methodparam"><span
class="type">resource</span> `$statement`</span> , <span
class="methodparam"><span class="type">mixed</span> `$field`</span> )

Returns the data from `field` in the current row, fetched by <span
class="function">oci\_fetch</span>.

For details on the data type mapping performed by the OCI8 extension,
see the
<a href="/book/oci8.html#Supported%20Datatypes" class="link">datatypes supported by the driver</a>

### Parameters

`statement`  

`field`  
Can be either use the column number (1-based) or the column name. The
case of the column name must be the case that Oracle meta data describes
the column as, which is uppercase for columns created case
insensitively.

### Return Values

Returns everything as strings except for abstract types (ROWIDs, LOBs
and FILEs). Returns **`false`** on error.

### Examples

**Example \#1 <span class="function">oci\_fetch</span> with <span
class="function">oci\_result</span>**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
if (!$conn) {
    $e = oci_error();
    trigger_error(htmlentities($e['message'], ENT_QUOTES), E_USER_ERROR);
}

$sql = 'SELECT location_id, city FROM locations WHERE location_id < 1200';
$stid = oci_parse($conn, $sql);
oci_execute($stid);

while (oci_fetch($stid)) {
    echo oci_result($stid, 'LOCATION_ID') . " is ";
    echo oci_result($stid, 'CITY') . "<br>\n";
}

// Displays:
//   1000 is Roma
//   1100 is Venice

oci_free_statement($stid);
oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ociresult</span> instead. This name still can be
> used, it was left as alias of <span
> class="function">oci\_result</span> for downwards compatability. This,
> however, is deprecated and not recommended.

### See Also

-   <span class="function">oci\_fetch\_array</span>
-   <span class="function">oci\_fetch\_assoc</span>
-   <span class="function">oci\_fetch\_object</span>
-   <span class="function">oci\_fetch\_row</span>
-   <span class="function">oci\_fetch\_all</span>

oci\_rollback
=============

Rolls back the outstanding database transaction

### Description

<span class="type">bool</span> <span
class="methodname">oci\_rollback</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

Reverts all uncommitted changes for the Oracle `connection` and ends the
transaction. It releases all locks held. All Oracle *SAVEPOINTS* are
erased.

A transaction begins when the first SQL statement that changes data is
executed with <span class="function">oci\_execute</span> using the
**`OCI_NO_AUTO_COMMIT`** flag. Further data changes made by other
statements become part of the same transaction. Data changes made in a
transaction are temporary until the transaction is committed or rolled
back. Other users of the database will not see the changes until they
are committed.

When inserting or updating data, using transactions is recommended for
relational data consistency and for performance reasons.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span> or <span
class="function">oci\_new\_connect</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">oci\_rollback</span> example**

``` php
<?php

// Insert into several tables, rolling back the changes if an error occurs

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, "INSERT INTO mysalary (id, name) VALUES (1, 'Chris')");

// The OCI_NO_AUTO_COMMIT flag tells Oracle not to commit the INSERT immediately
// Use OCI_DEFAULT as the flag for PHP <= 5.3.1.  The two flags are equivalent
$r = oci_execute($stid, OCI_NO_AUTO_COMMIT);
if (!$r) {    
    $e = oci_error($stid);
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

$stid = oci_parse($conn, 'INSERT INTO myschedule (startday) VALUES (12)');
$r = oci_execute($stid, OCI_NO_AUTO_COMMIT);
if (!$r) {    
    $e = oci_error($stid);
    oci_rollback($conn);  // rollback changes to both tables
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

// Commit the changes to both tables
$r = oci_commit($conn);
if (!r) {
    $e = oci_error($conn);
    trigger_error(htmlentities($e['message']), E_USER_ERROR);
}

?>
```

**Example \#2 Rolling back to a *SAVEPOINT* example**

``` php
<?php
$stid = oci_parse($conn, 'UPDATE mytab SET id = 1111');
oci_execute($stid, OCI_NO_AUTO_COMMIT);

// Create the savepoint
$stid = oci_parse($conn, 'SAVEPOINT mysavepoint');
oci_execute($stid, OCI_NO_AUTO_COMMIT);

$stid = oci_parse($conn, 'UPDATE mytab SET id = 2222');
oci_execute($stid, OCI_NO_AUTO_COMMIT);

// Use an explicit SQL statement to rollback to the savepoint
$stid = oci_parse($conn, 'ROLLBACK TO SAVEPOINT mysavepoint');
oci_execute($stid, OCI_NO_AUTO_COMMIT);

oci_commit($conn);  // mytab now has id of 1111
?>
```

### Notes

> **Note**:
>
> Transactions are automatically rolled back when you close the
> connection, or when the script ends, whichever is soonest. You need to
> explicitly call <span class="function">oci\_commit</span> to commit
> the transaction.
>
> Any call to <span class="function">oci\_execute</span> that uses
> **`OCI_COMMIT_ON_SUCCESS`** mode explicitly or by default will commit
> any previous uncommitted transaction.
>
> Any Oracle DDL statement such as *CREATE* or *DROP* will automatically
> commit any uncommitted transaction.

### See Also

-   <span class="function">oci\_commit</span>
-   <span class="function">oci\_execute</span>

oci\_server\_version
====================

Returns the Oracle Database version

### Description

<span class="type">string</span> <span
class="methodname">oci\_server\_version</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

Returns a string with the Oracle Database version and available options

### Parameters

`connection`  

### Return Values

Returns the version information as a string or **`false`** on error.

### Examples

**Example \#1 <span class="function">oci\_server\_version</span>
example**

``` php
<?php

$conn = oci_connect("hr", "hrpwd", "localhost/XE");
echo "Server Version: " . oci_server_version($conn);

// Displays:
// Server Version: Oracle Database 11g Enterprise Edition Release 11.2.0.1.0 - 64bit Production
// With the Partitioning, OLAP, Data Mining and Real Application Testing option

oci_close($conn);

?>
```

### Notes

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ociserverversion</span> instead. This old name still
> can be used. However it is deprecated and not recommended.

### See Also

-   <span class="function">oci\_client\_version</span>

oci\_set\_action
================

Sets the action name

### Description

<span class="type">bool</span> <span
class="methodname">oci\_set\_action</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$action_name`</span> )

Sets the action name for Oracle tracing.

The action name is registered with the database when the next
'round-trip' from PHP to the database occurs, typically when an SQL
statement is executed.

The action name can subsequently be queried from database administration
views such as *V$SESSION*. It can be used for tracing and monitoring
such as with *V$SQLAREA* and
*DBMS\_MONITOR.SERV\_MOD\_ACT\_STAT\_ENABLE*.

The value may be retained across persistent connections.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

`action_name`  
User chosen string up to 32 bytes long.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Setting the action**

``` php
<?php

$c = oci_connect('hr', 'welcome', 'localhost/XE');

// Record the action
oci_set_action($c, 'Friend Lookup');

// Code that causes a round-trip, for example a query:
$s = oci_parse($c, 'select * from dual');
oci_execute($s);
oci_fetch_all($s, $res);

sleep(30);

?>
```

    // While the script is running, the administrator can see the actions
    // being performed:

    sqlplus system/welcome
    SQL> select action from v$session;

### Notes

> **Note**: **Oracle version requirement**  
>
> This function is available when PHP is linked with Oracle Database
> libraries from version 10*g* onwards.

**Tip**

With older versions of OCI8 or the Oracle Database, the client
information can be set using the Oracle *DBMS\_APPLICATION\_INFO*
package. This is less efficient than using <span
class="function">oci\_set\_client\_info</span>.

**Caution**

Some but not all OCI8 functions cause round-trips. Round-trips to the
database may not occur with queries when result caching is enabled.

### See Also

-   <span class="function">oci\_set\_module\_name</span>
-   <span class="function">oci\_set\_client\_info</span>
-   <span class="function">oci\_set\_client\_identifier</span>
-   <span class="function">oci\_set\_db\_operation</span>

oci\_set\_call\_timeout
=======================

Sets a millisecond timeout for database calls

### Description

<span class="type">bool</span> <span
class="methodname">oci\_set\_call\_timeout</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">int</span> `$time_out`</span> )

Sets a timeout limiting the maxium time a database round-trip using this
connection may take.

Each OCI8 operation may make zero or more calls to Oracle's client
library. These internal calls may then may make zero or more round-trips
to Oracle Database. If any one of those round-trips takes more than
*time\_out* milliseconds, then the operation is cancelled and an error
is returned to the application.

The *time\_out* value applies to each round-trip individually, not to
the sum of all round-trips. Time spent processing in PHP OCI8 before or
after the completion of each round-trip is not counted.

When a call is interrupted, Oracle will attempt to clean up the
connection for reuse. This operation is allowed to run for another
*time\_out* period. Depending on the outcome of the cleanup, the
connection may or may not be reusable.

When persistent connections are used, the timeout value will be retained
across PHP requests.

The <span class="function">oci\_set\_call\_timeout</span> function is
available when OCI8 uses Oracle 18 (or later) Client libraries.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

`time_out`  
The maximum time in milliseconds that any single round-trip between PHP
and Oracle Database may take.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Setting the timeout**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');
oci_set_call_timeout($conn, 5000);

?>
```

oci\_set\_client\_identifier
============================

Sets the client identifier

### Description

<span class="type">bool</span> <span
class="methodname">oci\_set\_client\_identifier</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$client_identifier`</span> )

Sets the client identifier used by various database components to
identify lightweight application users who authenticate as the same
database user.

The client identifier is registered with the database when the next
'round-trip' from PHP to the database occurs, typically when an SQL
statement is executed.

The identifier can subsequently be queried, for example with *SELECT
SYS\_CONTEXT('USERENV','CLIENT\_IDENTIFIER') FROM DUAL*. Database
administration views such as *V$SESSION* will also contain the value. It
can be used with *DBMS\_MONITOR.CLIENT\_ID\_TRACE\_ENABLE* for tracing
and can also be used for auditing.

The value may be retained across page requests that use the same
persistent connection.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

`client_identifier`  
User chosen string up to 64 bytes long.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Setting the client identifier to the application user**

``` php
<?php

// Find the application user's login name
session_start();
$un = my_validate_session($_SESSION['username']);
$c = oci_connect('myschema', 'welcome', 'localhost/XE');

// Tell Oracle who that user is
oci_set_client_identifier($c, $un);

// The next round-trip to the database will piggyback the identifier
$s = oci_parse($c, 'select mydata from mytable');
oci_execute($s);

// ...

?>
```

### Notes

**Caution**

Some but not all OCI8 functions cause round-trips. Round-trips to the
database may not occur with queries when result caching is enabled.

### See Also

-   <span class="function">oci\_set\_module\_name</span>
-   <span class="function">oci\_set\_action</span>
-   <span class="function">oci\_set\_client\_info</span>
-   <span class="function">oci\_set\_db\_operation</span>

oci\_set\_client\_info
======================

Sets the client information

### Description

<span class="type">bool</span> <span
class="methodname">oci\_set\_client\_info</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$client_info`</span> )

Sets the client information for Oracle tracing.

The client information is registered with the database when the next
'round-trip' from PHP to the database occurs, typically when an SQL
statement is executed.

The client information can subsequently be queried from database
administration views such as *V$SESSION*.

The value may be retained across persistent connections.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

`client_info`  
User chosen string up to 64 bytes long.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Setting the client information**

``` php
<?php

$c = oci_connect('hr', 'welcome', 'localhost/XE');

// Record the client information
oci_set_client_info($c, 'My Application Version 2');

// Code that causes a round-trip, for example a query:
$s = oci_parse($c, 'select * from dual');
oci_execute($s);
oci_fetch_all($s, $res);

sleep(30);

?>
```

    // While the script is running, the administrator can see the client
    // information:

    sqlplus system/welcome
    SQL> select client_info from v$session;

### Notes

> **Note**: **Oracle version requirement**  
>
> This function is available when PHP is linked with Oracle Database
> libraries from version 10*g* onwards.

**Tip**

With older versions of OCI8 or the Oracle Database, the client
information can be set using the Oracle *DBMS\_APPLICATION\_INFO*
package. This is less efficient than using <span
class="function">oci\_set\_client\_info</span>.

**Caution**

Some but not all OCI8 functions cause round-trips. Round-trips to the
database may not occur with queries when result caching is enabled.

### See Also

-   <span class="function">oci\_set\_module\_name</span>
-   <span class="function">oci\_set\_action</span>
-   <span class="function">oci\_set\_client\_identifier</span>
-   <span class="function">oci\_set\_db\_operation</span>

oci\_set\_db\_operation
=======================

Sets the database operation

### Description

<span class="type">bool</span> <span
class="methodname">oci\_set\_db\_operation</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$dbop`</span> )

Sets the DBOP for Oracle tracing.

The database operation name is registered with the database when the
next 'round-trip' from PHP to the database occurs, typically when a SQL
statement is executed.

The database operation can subsequently be queried from database
administration views such as *V$SQL\_MONITOR*.

The <span class="function">oci\_set\_db\_operation</span> function is
available when OCI8 uses Oracle 12 (or later) Client libraries and
Oracle Database 12 (or later).

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

`dbop`  
User chosen string.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Setting the DBOP**

``` php
<?php

$c = oci_connect('hr', 'welcome', 'localhost/XE');

// Record the operation
oci_set_db_operation($c, 'main query');

// Code that causes a round-trip, for example a query:
$s = oci_parse($c, 'select * from dual');
oci_execute($s);
oci_fetch_all($s, $res);

sleep(30);

?>
```

    // While the script is running, the administrator can see the database operations
    // being performed:

    sqlplus system/welcome
    SQL> select dbop_name from v$sql_monitor;

### Notes

**Caution**

Some but not all OCI8 functions cause round-trips. Round-trips to the
database may not occur with queries when result caching is enabled.

### See Also

-   <span class="function">oci\_set\_action</span>
-   <span class="function">oci\_set\_module\_name</span>
-   <span class="function">oci\_set\_client\_info</span>
-   <span class="function">oci\_set\_client\_identifier</span>

oci\_set\_edition
=================

Sets the database edition

### Description

<span class="type">bool</span> <span
class="methodname">oci\_set\_edition</span> ( <span
class="methodparam"><span class="type">string</span> `$edition`</span> )

Sets the database "edition" of objects to be used by a subsequent
connections.

Oracle Editions allow concurrent versions of applications to run using
the same schema and object names. This is useful for upgrading live
systems.

Call <span class="function">oci\_set\_edition</span> before calling
<span class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span> or <span
class="function">oci\_new\_connect</span>.

If an edition is set that is not valid in the database, connection will
fail even if <span class="function">oci\_set\_edition</span> returns
success.

When using persistent connections, if a connection with the requested
edition setting already exists, it is reused. Otherwise, a different
persistent connection is created

### Parameters

`edition`  
Oracle Database edition name previously created with the SQL "*CREATE
EDITION*" command.

### Notes

> **Note**: **Oracle version requirement**  
>
> This function is available from Oracle 11*g*R2 onwards.

**Caution**

To avoid inconsistencies and unexpected errors, do not use ALTER SESSION
SET EDITION to change the edition on persistent connections.

**Caution**

To avoid inconsistencies and unexpected errors when using editions and
<a href="/book/oci8.html#OCI8%20Connection%20Handling%20and%20Connection%20Pooling" class="link">DRCP</a>
with Oracle 11.2.0.1, keep a one-to-one correspondence between the
<a href="/book/oci8.html#" class="link">oci8.connection_class</a> and
the edition name used by applications. Each pooled server of a given
connection class should only be used with one edition. This restriction
has been removed with Oracle 11.2.0.2.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Two scripts can use different versions of myfunc() at the
same time**

``` php
<?php

// File 1

echo "Version 1 of application\n";

oci_set_edition('ORA$BASE');
$c = oci_connect('hr', 'welcome', 'localhost/XE');

$s = oci_parse($c, "begin :r := myfunc(); end;");
oci_bind_by_name($s, ":r", $r, 20);
oci_execute($s);
echo "The result is $r\n";

?>
```

``` php
<?php

// File 2

echo "Version 2 of application\n";

oci_set_edition('E1');
$c = oci_connect('hr', 'welcome', 'localhost/XE');

$s = oci_parse($c, "begin :r := myfunc(); end;");
oci_bind_by_name($s, ":r", $r, 20);
oci_execute($s);
echo "The result is $r\n";

?>
```

oci\_set\_module\_name
======================

Sets the module name

### Description

<span class="type">bool</span> <span
class="methodname">oci\_set\_module\_name</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$module_name`</span> )

Sets the module name for Oracle tracing.

The module name is registered with the database when the next
'round-trip' from PHP to the database occurs, typically when an SQL
statement is executed.

The name can subsequently be queried from database administration views
such as *V$SESSION*. It can be used for tracing and monitoring such as
with *V$SQLAREA* and *DBMS\_MONITOR.SERV\_MOD\_ACT\_STAT\_ENABLE*.

The value may be retained across persistent connections.

### Parameters

`connection`  
An Oracle connection identifier, returned by <span
class="function">oci\_connect</span>, <span
class="function">oci\_pconnect</span>, or <span
class="function">oci\_new\_connect</span>.

`module_name`  
User chosen <span class="type">string</span> up to 48 bytes long.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Notes

> **Note**: **Oracle version requirement**  
>
> This function is available when PHP is linked with Oracle Database
> libraries from version 10*g* onwards.

**Tip**

With older versions of OCI8 or the Oracle Database, the client
information can be set using the Oracle *DBMS\_APPLICATION\_INFO*
package. This is less efficient than using <span
class="function">oci\_set\_client\_info</span>.

**Caution**

Some but not all OCI8 functions cause round-trips. Round-trips to the
database may not occur with queries when result caching is enabled.

### Examples

**Example \#1 Setting the module name**

``` php
<?php

$c = oci_connect('hr', 'welcome', 'localhost/XE');

// Record the module
oci_set_module_name($c, 'Home Page');

// Code that causes a round-trip, for example a query:
$s = oci_parse($c, 'select * from dual');
oci_execute($s);
oci_fetch_all($s, $res);

sleep(30);
?>
```

    // While the script is running, the administrator can see the
    // modules in use:

    sqlplus system/welcome
    SQL> select module from v$session;

### See Also

-   <span class="function">oci\_set\_action</span>
-   <span class="function">oci\_set\_client\_info</span>
-   <span class="function">oci\_set\_client\_identifier</span>
-   <span class="function">oci\_set\_db\_operation</span>

oci\_set\_prefetch
==================

Sets number of rows to be prefetched by queries

### Description

<span class="type">bool</span> <span
class="methodname">oci\_set\_prefetch</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> , <span class="methodparam"><span
class="type">int</span> `$rows`</span> )

Sets the number of rows to be buffered by the Oracle Client libraries
after a successful query call to <span
class="function">oci\_execute</span> and for each subsequent internal
fetch request to the database. For queries returning a large number of
rows, performance can be significantly improved by increasing the
prefetch count above the default
<a href="/book/oci8.html#" class="link">oci8.default_prefetch</a> value.

Prefetching is Oracle's efficient way of returning more than one data
row from the database in each network request. This can result in better
network and CPU utilization. The buffering of rows is internal to OCI8
and the behavior of OCI8 fetching functions is unchanged regardless of
the prefetch count. For example, <span
class="function">oci\_fetch\_row</span> will always return one row. The
prefetch buffer is per-statement and is not used by re-executed
statements or by other connections.

Call <span class="function">oci\_set\_prefetch</span> before calling
<span class="function">oci\_execute</span>.

A tuning goal is to set the prefetch value to a reasonable size for the
network and database to handle. For queries returning a very large
number of rows, overall system efficiency might be better if rows are
retrieved from the database in several chunks (i.e set the prefetch
value smaller than the number of rows). This allows the database to
handle other users' statements while the PHP script is processing the
current set of rows.

Query prefetching was introduced in Oracle 8*i*. REF CURSOR prefetching
was introduced in Oracle 11*g*R2 and occurs when PHP is linked with
Oracle 11*g*R2 (or later) Client libraries. Nested cursor prefetching
was introduced in Oracle 11*g*R2 and requires both the Oracle Client
libraries and the database to be version 11*g*R2 or greater.

Prefetching is not supported when queries contain LONG or LOB columns.
The prefetch value is ignored and single-row fetches will be used in all
the situations when prefetching is not supported.

When using Oracle Database 12*c*, the prefetch value set by PHP can be
overridden by Oracle's client *oraaccess.xml* configuration file. Refer
to Oracle documentation for more detail.

### Parameters

`statement`  
A valid OCI8 statement identifier created by <span
class="function">oci\_parse</span> and executed by <span
class="function">oci\_execute</span>, or a *REF CURSOR* statement
identifier.

`rows`  
The number of rows to be prefetched, \>= 0

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version         | Description                                                                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL OCI8 1.4   | Before this release, `rows` must be \>= 1.                                                                                                          |
| PECL OCI8 1.3.4 | Before this release, prefetching was limited to the lesser of `rows` rows and 1024 \* `rows` bytes. The byte size restriction has now been removed. |

### Examples

**Example \#1 Changing the default prefetch value for a query**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'SELECT * FROM myverybigtable');
oci_set_prefetch($stid, 300);  // Set before calling oci_execute()
oci_execute($stid);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($stid, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>".($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;")."</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

oci_free_statement($stid);
oci_close($conn);

?>
```

**Example \#2 Changing the default prefetch for a REF CURSOR fetch**

``` php
<?php
/*
  Create the PL/SQL stored procedure as:

  CREATE OR REPLACE PROCEDURE myproc(p1 OUT SYS_REFCURSOR) AS
  BEGIN
    OPEN p1 FOR SELECT * FROM all_objects WHERE ROWNUM < 5000;
  END;
*/

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'BEGIN myproc(:rc); END;');
$refcur = oci_new_cursor($conn);
oci_bind_by_name($stid, ':rc', $refcur, -1, OCI_B_CURSOR);
oci_execute($stid);

// Change the prefetch before executing the cursor.
// REF CURSOR prefetching works when PHP is linked with Oracle 11gR2 or later Client libraries
oci_set_prefetch($refcur, 200);
oci_execute($refcur);

echo "<table border='1'>\n";
while ($row = oci_fetch_array($refcur, OCI_ASSOC+OCI_RETURN_NULLS)) {
    echo "<tr>\n";
    foreach ($row as $item) {
        echo "    <td>".($item !== null ? htmlentities($item, ENT_QUOTES) : "&nbsp;")."</td>\n";
    }
    echo "</tr>\n";
}
echo "</table>\n";

oci_free_statement($refcur);
oci_free_statement($stid);
oci_close($conn);

?>
```

If PHP OCI8 fetches from a REF CURSOR and then passes the REF CURSOR
back to a second PL/SQL procedure for further processing, then set the
REF CURSOR prefetch count to **`0`** to avoid rows being "lost" from the
result set. The prefetch value is the number of extra rows fetched in
each OCI8 internal request to the database, so setting it to **`0`**
means only fetch one row at a time.

**Example \#3 Setting the prefetch value when passing a REF CURSOR back
to Oracle**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/orcl');

// get the REF CURSOR
$stid = oci_parse($conn, 'BEGIN myproc(:rc_out); END;');
$refcur = oci_new_cursor($conn);
oci_bind_by_name($stid, ':rc_out', $refcur, -1, OCI_B_CURSOR);
oci_execute($stid);

// Display two rows, but don't prefetch any extra rows otherwise
// those extra rows would not be passed back to myproc_use_rc().
// A prefetch value of 0 is allowed in PHP 5.3.2 and PECL OCI8 1.4
oci_set_prefetch($refcur, 0);
oci_execute($refcur);
$row = oci_fetch_array($refcur);
var_dump($row);
$row = oci_fetch_array($refcur);
var_dump($row);

// pass the REF CURSOR to myproc_use_rc() to do more data processing
// with the result set
$stid = oci_parse($conn, 'begin myproc_use_rc(:rc_in); end;'); 
oci_bind_by_name($stid, ':rc_in', $refcur, -1, OCI_B_CURSOR);
oci_execute($stid);

?>
```

### See Also

-   <a href="/book/oci8.html#" class="link">oci8.default_prefetch</a>
    ini option

oci\_statement\_type
====================

Returns the type of a statement

### Description

<span class="type">string</span> <span
class="methodname">oci\_statement\_type</span> ( <span
class="methodparam"><span class="type">resource</span>
`$statement`</span> )

Returns a keyword identifying the type of the OCI8 `statement`.

### Parameters

`statement`  
A valid OCI8 statement identifier from <span
class="function">oci\_parse</span>.

### Return Values

Returns the type of `statement` as one of the following strings.

| Return String | Notes                                     |
|---------------|-------------------------------------------|
| *ALTER*       |                                           |
| *BEGIN*       |                                           |
| *CALL*        | Introduced in PHP 5.2.1 (PECL OCI8 1.2.3) |
| *CREATE*      |                                           |
| *DECLARE*     |                                           |
| *DELETE*      |                                           |
| *DROP*        |                                           |
| *INSERT*      |                                           |
| *SELECT*      |                                           |
| *UPDATE*      |                                           |
| *UNKNOWN*     |                                           |

Returns **`false`** on error.

### Examples

**Example \#1 <span class="function">oci\_statement\_type</span>
example**

``` php
<?php

$conn = oci_connect('hr', 'welcome', 'localhost/XE');

$stid = oci_parse($conn, 'DELETE FROM departments WHERE department_id = 130;');
if (oci_statement_type($stid) == "DELETE") {
    trigger_error('You are not allowed to delete from this table', E_USER_ERROR);
}
else {
    oci_execute($stid);  // delete the row
}

oci_free_statement($stid);
oci_close($conn);

?>
```

oci\_unregister\_taf\_callback
==============================

Unregister a user-defined callback function for Oracle Database TAF

### Description

<span class="type">bool</span> <span
class="methodname">oci\_unregister\_taf\_callback</span> ( <span
class="methodparam"><span class="type">resource</span>
`$connection`</span> )

Unregister the user-defined callback function registered to
`connection    ` by <span
class="function">oci\_register\_taf\_callback</span>. See
<a href="/book/oci8.html#OCI8%20Transparent%20Application%20Failover%20(TAF)%20Support" class="link">OCI8 Transparent Application Failover (TAF) Support</a>
for information.

### Parameters

`connection`  
An Oracle connection identifier.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">oci\_register\_taf\_callback</span>

**Table of Contents**

-   [oci\_bind\_array\_by\_name](/book/oci8.html#oci_bind_array_by_name)
    — Binds a PHP array to an Oracle PL/SQL array parameter
-   [oci\_bind\_by\_name](/book/oci8.html#oci_bind_by_name) — Binds a
    PHP variable to an Oracle placeholder
-   [oci\_cancel](/book/oci8.html#oci_cancel) — Cancels reading from
    cursor
-   [oci\_client\_version](/book/oci8.html#oci_client_version) — Returns
    the Oracle client library version
-   [oci\_close](/book/oci8.html#oci_close) — Closes an Oracle
    connection
-   [oci\_commit](/book/oci8.html#oci_commit) — Commits the outstanding
    database transaction
-   [oci\_connect](/book/oci8.html#oci_connect) — Connect to an Oracle
    database
-   [oci\_define\_by\_name](/book/oci8.html#oci_define_by_name) —
    Associates a PHP variable with a column for query fetches
-   [oci\_error](/book/oci8.html#oci_error) — Returns the last error
    found
-   [oci\_execute](/book/oci8.html#oci_execute) — Executes a statement
-   [oci\_fetch\_all](/book/oci8.html#oci_fetch_all) — Fetches multiple
    rows from a query into a two-dimensional array
-   [oci\_fetch\_array](/book/oci8.html#oci_fetch_array) — Returns the
    next row from a query as an associative or numeric array
-   [oci\_fetch\_assoc](/book/oci8.html#oci_fetch_assoc) — Returns the
    next row from a query as an associative array
-   [oci\_fetch\_object](/book/oci8.html#oci_fetch_object) — Returns the
    next row from a query as an object
-   [oci\_fetch\_row](/book/oci8.html#oci_fetch_row) — Returns the next
    row from a query as a numeric array
-   [oci\_fetch](/book/oci8.html#oci_fetch) — Fetches the next row from
    a query into internal buffers
-   [oci\_field\_is\_null](/book/oci8.html#oci_field_is_null) — Checks
    if a field in the currently fetched row is null
-   [oci\_field\_name](/book/oci8.html#oci_field_name) — Returns the
    name of a field from the statement
-   [oci\_field\_precision](/book/oci8.html#oci_field_precision) — Tell
    the precision of a field
-   [oci\_field\_scale](/book/oci8.html#oci_field_scale) — Tell the
    scale of the field
-   [oci\_field\_size](/book/oci8.html#oci_field_size) — Returns field's
    size
-   [oci\_field\_type\_raw](/book/oci8.html#oci_field_type_raw) — Tell
    the raw Oracle data type of the field
-   [oci\_field\_type](/book/oci8.html#oci_field_type) — Returns a
    field's data type name
-   [oci\_free\_descriptor](/book/oci8.html#oci_free_descriptor) — Frees
    a descriptor
-   [oci\_free\_statement](/book/oci8.html#oci_free_statement) — Frees
    all resources associated with statement or cursor
-   [oci\_get\_implicit\_resultset](/book/oci8.html#oci_get_implicit_resultset)
    — Returns the next child statement resource from a parent statement
    resource that has Oracle Database Implicit Result Sets
-   [oci\_lob\_copy](/book/oci8.html#oci_lob_copy) — Copies large object
-   [oci\_lob\_is\_equal](/book/oci8.html#oci_lob_is_equal) — Compares
    two LOB/FILE locators for equality
-   [oci\_new\_collection](/book/oci8.html#oci_new_collection) —
    Allocates new collection object
-   [oci\_new\_connect](/book/oci8.html#oci_new_connect) — Connect to
    the Oracle server using a unique connection
-   [oci\_new\_cursor](/book/oci8.html#oci_new_cursor) — Allocates and
    returns a new cursor (statement handle)
-   [oci\_new\_descriptor](/book/oci8.html#oci_new_descriptor) —
    Initializes a new empty LOB or FILE descriptor
-   [oci\_num\_fields](/book/oci8.html#oci_num_fields) — Returns the
    number of result columns in a statement
-   [oci\_num\_rows](/book/oci8.html#oci_num_rows) — Returns number of
    rows affected during statement execution
-   [oci\_parse](/book/oci8.html#oci_parse) — Prepares an Oracle
    statement for execution
-   [oci\_password\_change](/book/oci8.html#oci_password_change) —
    Changes password of Oracle's user
-   [oci\_pconnect](/book/oci8.html#oci_pconnect) — Connect to an Oracle
    database using a persistent connection
-   [oci\_register\_taf\_callback](/book/oci8.html#oci_register_taf_callback)
    — Register a user-defined callback function for Oracle Database TAF
-   [oci\_result](/book/oci8.html#oci_result) — Returns field's value
    from the fetched row
-   [oci\_rollback](/book/oci8.html#oci_rollback) — Rolls back the
    outstanding database transaction
-   [oci\_server\_version](/book/oci8.html#oci_server_version) — Returns
    the Oracle Database version
-   [oci\_set\_action](/book/oci8.html#oci_set_action) — Sets the action
    name
-   [oci\_set\_call\_timeout](/book/oci8.html#oci_set_call_timeout) —
    Sets a millisecond timeout for database calls
-   [oci\_set\_client\_identifier](/book/oci8.html#oci_set_client_identifier)
    — Sets the client identifier
-   [oci\_set\_client\_info](/book/oci8.html#oci_set_client_info) — Sets
    the client information
-   [oci\_set\_db\_operation](/book/oci8.html#oci_set_db_operation) —
    Sets the database operation
-   [oci\_set\_edition](/book/oci8.html#oci_set_edition) — Sets the
    database edition
-   [oci\_set\_module\_name](/book/oci8.html#oci_set_module_name) — Sets
    the module name
-   [oci\_set\_prefetch](/book/oci8.html#oci_set_prefetch) — Sets number
    of rows to be prefetched by queries
-   [oci\_statement\_type](/book/oci8.html#oci_statement_type) — Returns
    the type of a statement
-   [oci\_unregister\_taf\_callback](/book/oci8.html#oci_unregister_taf_callback)
    — Unregister a user-defined callback function for Oracle Database
    TAF

Introduction
------------

OCI8 Collection functionality.

> **Note**:
>
> The OCI-Collection class was renamed to OCICollection in PHP 8 OCI8
> 3.0.0 to align with PHP naming standards.

Class synopsis
--------------

**OCICollection**

<span class="ooclass"> class **OCICollection** </span> {

/\* Methods \*/

<span class="type">bool</span> <span class="methodname">append</span> (
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="type">bool</span> <span class="methodname">assign</span> (
<span class="methodparam"><span class="type">OCICollection</span>
`$from`</span> )

<span class="type">bool</span> <span
class="methodname">assignElem</span> ( <span class="methodparam"><span
class="type">int</span> `$index`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="type">bool</span> <span class="methodname">free</span> (
<span class="methodparam">void</span> )

<span class="type">mixed</span> <span class="methodname">getElem</span>
( <span class="methodparam"><span class="type">int</span>
`$index`</span> )

<span class="type">int</span> <span class="methodname">max</span> (
<span class="methodparam">void</span> )

<span class="type">int</span> <span class="methodname">size</span> (
<span class="methodparam">void</span> )

<span class="type">bool</span> <span class="methodname">trim</span> (
<span class="methodparam"><span class="type">int</span> `$num`</span> )

}

OCICollection::append
=====================

Appends element to the collection

### Description

<span class="type">bool</span> <span
class="methodname">OCICollection::append</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

Appends element to the end of the collection.

### Parameters

`value`  
The value to be added to the collection. Can be a string or a number.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Collection</span> class was renamed to <span class="classname">OCICollection</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCICollection::assign" class="xref"></a>

OCICollection::assign
=====================

Assigns a value to the collection from another existing collection

### Description

<span class="type">bool</span> <span
class="methodname">OCICollection::assign</span> ( <span
class="methodparam"><span class="type">OCICollection</span>
`$from`</span> )

Assigns a value to the collection from another, previously created
collection. Both collections must be created with <span
class="function">oci\_new\_collection</span> prior to using them.

### Parameters

`from`  
An instance of OCI-Collection.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Collection</span> class was renamed to <span class="classname">OCICollection</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCICollection::append" class="xref"></a>

OCICollection::assignElem
=========================

Assigns a value to the element of the collection

### Description

<span class="type">bool</span> <span
class="methodname">OCICollection::assignElem</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

Assigns a value to the element with index `index`.

### Parameters

`index`  
The element index. First index is 0.

`value`  
Can be a string or a number.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Collection</span> class was renamed to <span class="classname">OCICollection</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCICollection::getElem" class="xref"></a>

OCICollection::free
===================

Frees the resources associated with the collection object

### Description

<span class="type">bool</span> <span
class="methodname">OCICollection::free</span> ( <span
class="methodparam">void</span> )

Frees the resources associated with the collection object.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Collection</span> class was renamed to <span class="classname">OCICollection</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#oci_new_collection" class="xref"></a>

OCICollection::getElem
======================

Returns value of the element

### Description

<span class="type">mixed</span> <span
class="methodname">OCICollection::getElem</span> ( <span
class="methodparam"><span class="type">int</span> `$index`</span> )

Returns element's value with the index `index` (0-based).

### Parameters

`index`  
The element index. First index is 0.

### Return Values

Returns **`false`** if such element doesn't exist; **`null`** if element
is **`null`**; string if element is column of a string datatype or
number if element is numeric field.

### Changelog

| Version                | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Collection</span> class was renamed to <span class="classname">OCICollection</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCICollection::assignElem" class="xref"></a>

OCICollection::max
==================

Returns the maximum number of elements in the collection

### Description

<span class="type">int</span> <span
class="methodname">OCICollection::max</span> ( <span
class="methodparam">void</span> )

Returns the maximum number of elements in the collection.

### Return Values

Returns the maximum number as an integer, or **`false`** on errors.

If the returned value is 0, then the number of elements is not limited.

### Changelog

| Version                | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Collection</span> class was renamed to <span class="classname">OCICollection</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCICollection::size" class="xref"></a>

OCICollection::size
===================

Returns size of the collection

### Description

<span class="type">int</span> <span
class="methodname">OCICollection::size</span> ( <span
class="methodparam">void</span> )

Returns the size of the collection.

### Return Values

Returns the number of elements in the collection or **`false`** on
error.

### Changelog

| Version                | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Collection</span> class was renamed to <span class="classname">OCICollection</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCICollection::max" class="xref"></a>

OCICollection::trim
===================

Trims elements from the end of the collection

### Description

<span class="type">bool</span> <span
class="methodname">OCICollection::trim</span> ( <span
class="methodparam"><span class="type">int</span> `$num`</span> )

Trims `num` of elements from the end of the collection.

### Parameters

`num`  
The number of elements to be trimmed.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                                             |
|------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Collection</span> class was renamed to <span class="classname">OCICollection</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCICollection::size" class="xref"></a>

Introduction
------------

OCI8 LOB functionality for large binary (BLOB) and character (CLOB)
objects.

> **Note**:
>
> The OCI-Lob class was renamed to OCILob in PHP 8 and PECL OCI8 3.0.0
> to align with PHP naming standards.

Class synopsis
--------------

**OCILob**

<span class="ooclass"> class **OCILob** </span> {

/\* Methods \*/

<span class="type">bool</span> <span class="methodname">append</span> (
<span class="methodparam"><span class="type">OCILob</span>
`$lob_from`</span> )

<span class="type">bool</span> <span class="methodname">close</span> (
<span class="methodparam">void</span> )

<span class="type">bool</span> <span class="methodname">eof</span> (
<span class="methodparam">void</span> )

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span class="methodname">erase</span>
(\[ <span class="methodparam"><span class="type">int</span>
`$offset`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \]\] )

<span class="type">bool</span> <span class="methodname">export</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> \[, <span class="methodparam"><span
class="type">int</span> `$start`</span> \[, <span
class="methodparam"><span class="type">int</span> `$length`</span> \]\]
)

<span class="type">bool</span> <span class="methodname">flush</span> (\[
<span class="methodparam"><span class="type">int</span> `$flag`</span>
\] )

<span class="type">bool</span> <span class="methodname">free</span> (
<span class="methodparam">void</span> )

<span class="type">bool</span> <span
class="methodname">getBuffering</span> ( <span
class="methodparam">void</span> )

<span class="type">bool</span> <span class="methodname">import</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

<span class="type">string</span> <span class="methodname">load</span> (
<span class="methodparam">void</span> )

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span class="methodname">read</span> (
<span class="methodparam"><span class="type">int</span> `$length`</span>
)

<span class="type">bool</span> <span class="methodname">rewind</span> (
<span class="methodparam">void</span> )

<span class="type">bool</span> <span class="methodname">save</span> (
<span class="methodparam"><span class="type">string</span>
`$data`</span> \[, <span class="methodparam"><span
class="type">int</span> `$offset`</span> \] )

<span class="type">bool</span> <span class="methodname">seek</span> (
<span class="methodparam"><span class="type">int</span> `$offset`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$whence`<span class="initializer"> = **`OCI_SEEK_SET`**</span></span>
\] )

<span class="type">bool</span> <span
class="methodname">setBuffering</span> ( <span class="methodparam"><span
class="type">bool</span> `$on_off`</span> )

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span class="methodname">size</span> (
<span class="methodparam">void</span> )

<span class="type">int</span> <span class="methodname">tell</span> (
<span class="methodparam">void</span> )

<span class="type">bool</span> <span
class="methodname">Lob::truncate</span> (\[ <span
class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \] )

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span class="methodname">write</span> (
<span class="methodparam"><span class="type">string</span>
`$data`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \] )

<span class="type">bool</span> <span
class="methodname">writeTemporary</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> \[,
<span class="methodparam"><span class="type">int</span> `$lob_type`<span
class="initializer"> = OCI\_TEMP\_CLOB</span></span> \] )

}

OCILob::append
==============

Appends data from the large object to another large object

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::append</span> ( <span
class="methodparam"><span class="type">OCILob</span> `$lob_from`</span>
)

Appends data from the large object to the end of another large object.

Writing to the large object with this method will fail if buffering was
previously enabled. You must disable buffering before appending. You may
need to flush buffers with
<a href="/book/oci8.html#OCILob::flush" class="xref"></a> before
disabling buffering.

### Parameters

`lob_from`  
The copied LOB.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::flush" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::setBuffering" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::getBuffering" class="xref"></a>

OCILob::close
=============

Closes LOB descriptor

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::close</span> ( <span
class="methodparam">void</span> )

Closes descriptor of LOB or FILE. This function should be used only with
<a href="/book/oci8.html#OCILob::writeTemporary" class="xref"></a>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::writeTemporary" class="xref"></a>

OCILob::eof
===========

Tests for end-of-file on a large object's descriptor

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::eof</span> ( <span
class="methodparam">void</span> )

Tells whether the internal pointer of large object is at the end of LOB.

### Return Values

Returns **`true`** if internal pointer of large object is at the end of
LOB. Otherwise returns **`false`**.

### Notes

> **Note**:
>
> This function will return an Oracle error if
> <a href="/book/oci8.html#OCILob::setBuffering" class="xref"></a> is
> enabled on the LOB.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::size" class="xref"></a>

OCILob::erase
=============

Erases a specified portion of the internal LOB data

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">OCILob::erase</span> (\[ <span
class="methodparam"><span class="type">int</span> `$offset`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`</span>
\]\] )

Erases a specified portion of the internal LOB data starting at a
specified `offset`. If called without parameters, it erases all LOB
data.

For BLOBs, erasing means that the existing LOB value is overwritten with
zero-bytes. For CLOBs, the existing LOB value is overwritten with
spaces.

### Parameters

`offset`  

`length`  

### Return Values

Returns the actual number of characters/bytes erased or **`false`** on
failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::truncate" class="xref"></a>

OCILob::export
==============

Exports LOB's contents to a file

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::export</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$start`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \]\] )

Exports LOB contents to a file.

### Parameters

`filename`  
Path to the file.

`start`  
Indicates from where to start exporting.

`length`  
Indicates the length of data to be exported.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::import" class="xref"></a>

OCILob::flush
=============

Flushes/writes buffer of the LOB to the server

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::flush</span> (\[ <span
class="methodparam"><span class="type">int</span> `$flag`</span> \] )

<span class="function">OCILob::flush</span> actually writes data to the
server.

### Parameters

`flag`  
By default, resources are not freed, but using flag
**`OCI_LOB_BUFFER_FREE`** you can do it explicitly. Be sure you know
what you're doing - next read/write operation to the same part of LOB
will involve a round-trip to the server and initialize new buffer
resources. It is recommended to use **`OCI_LOB_BUFFER_FREE`** flag only
when you are not going to work with the LOB anymore.

### Return Values

Returns **`true`** on success or **`false`** on failure.

Returns **`false`** if buffering was not enabled or an error occurred.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::getBuffering" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::setBuffering" class="xref"></a>

OCILob::free
============

Frees resources associated with the LOB descriptor

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::free</span> ( <span
class="methodparam">void</span> )

Frees resources associated with the descriptor, previously allocated
with <span class="function">oci\_new\_descriptor</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

OCILob::getBuffering
====================

Returns current state of buffering for the large object

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::getBuffering</span> ( <span
class="methodparam">void</span> )

Tells whether the buffering for the large object is on or off.

### Return Values

Returns **`false`** if buffering for the large object is off and
**`true`** if buffering is used.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::setBuffering" class="xref"></a>

OCILob::import
==============

Imports file data to the LOB

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::import</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Writes data from the `filename` in to the current position of large
object.

### Parameters

`filename`  
Path to the file.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::export" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::write" class="xref"></a>

OCILob::load
============

Returns large object's contents

### Description

<span class="type">string</span> <span
class="methodname">OCILob::load</span> ( <span
class="methodparam">void</span> )

Returns large object's contents. As script execution is terminated when
the
<a href="/ini/core.html#ini.memory-limit" class="link">memory_limit</a>
is reached, ensure that the LOB does not exceed this limit. In most
cases it's recommended to use
<a href="/book/oci8.html#OCILob::read" class="xref"></a> instead.

### Return Values

Returns the contents of the object, or **`false`** on errors.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::read" class="xref"></a>

OCILob::read
============

Reads part of the large object

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">OCILob::read</span> ( <span class="methodparam"><span
class="type">int</span> `$length`</span> )

Reads `length` bytes from the current position of LOB's internal
pointer.

Reading stops when `length` bytes have been read or end of the large
object is reached. Internal pointer of the large object will be shifted
on the amount of bytes read.

### Parameters

`length`  
The length of data to read, in bytes. Large values will be rounded down
to 1 MB.

### Return Values

Returns the contents as a string, or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::load" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::write" class="xref"></a>

OCILob::rewind
==============

Moves the internal pointer to the beginning of the large object

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::rewind</span> ( <span
class="methodparam">void</span> )

Sets the internal pointer to the beginning of the large object.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::seek" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::tell" class="xref"></a>

OCILob::save
============

Saves data to the large object

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::save</span> ( <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`</span> \] )

Saves `data` to the large object.

### Parameters

`data`  
The data to be saved.

`offset`  
Can be used to indicate offset from the beginning of the large object.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::write" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::import" class="xref"></a>

OCILob::saveFile
================

Alias of <span class="function">OCILob::import</span>

### Description

This function is an alias of: <span
class="function">OCILob::import</span>.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

OCILob::seek
============

Sets the internal pointer of the large object

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::seek</span> ( <span class="methodparam"><span
class="type">int</span> `$offset`</span> \[, <span
class="methodparam"><span class="type">int</span> `$whence`<span
class="initializer"> = **`OCI_SEEK_SET`**</span></span> \] )

Sets the internal pointer of the large object.

### Parameters

`offset`  
Indicates the amount of bytes, on which internal pointer should be moved
from the position, pointed by `whence`.

`whence`  
May be one of:

-   **`OCI_SEEK_SET`** - sets the position equal to `offset`
-   **`OCI_SEEK_CUR`** - adds `offset` bytes to the current position
-   **`OCI_SEEK_END`** - adds `offset` bytes to the end of large object
    (use negative value to move to a position before the end of large
    object)

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::rewind" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::tell" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::eof" class="xref"></a>

OCILob::setBuffering
====================

Changes current state of buffering for the large object

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::setBuffering</span> ( <span
class="methodparam"><span class="type">bool</span> `$on_off`</span> )

Sets the buffering for the large object, depending on the value of the
`on_off` parameter.

Use of this function may provide performance improvements by buffering
small reads and writes of LOBs by reducing the number of network
round-trips and LOB versions. <span
class="function">OCILob::flush</span> should be used to flush buffers,
when you have finished working with the large object.

### Parameters

`on_off`  
**`true`** for on and **`false`** for off.

### Return Values

Returns **`true`** on success or **`false`** on failure. Repeated calls
to this method with the same flag will return **`true`**.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::getBuffering" class="xref"></a>

OCILob::size
============

Returns size of large object

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">OCILob::size</span> ( <span
class="methodparam">void</span> )

Gets the size of the large object.

### Return Values

Returns length of large object value or **`false`** on failure. Empty
objects have zero length.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

OCILob::tell
============

Returns the current position of internal pointer of large object

### Description

<span class="type">int</span> <span
class="methodname">OCILob::tell</span> ( <span
class="methodparam">void</span> )

Gets the current position of a LOB's internal pointer.

### Return Values

Returns current position of a LOB's internal pointer or **`false`** if
an error occurred.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::rewind" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::size" class="xref"></a>
-   <a href="/book/oci8.html#OCILob::eof" class="xref"></a>

OCILob::truncate
================

Truncates large object

### Description

<span class="type">bool</span> <span
class="methodname">Lob::truncate</span> (\[ <span
class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \] )

Truncates the LOB.

### Parameters

`length`  
If provided, this method will truncate the LOB to `length` bytes.
Otherwise, it will completely purge the LOB.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::erase" class="xref"></a>

OCILob::write
=============

Writes data to the large object

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">OCILob::write</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`</span>
\] )

Writes data from the parameter `data` into the current position of LOB's
internal pointer.

### Parameters

`data`  
The data to write in the LOB.

`length`  
If this parameter is given, writing will stop after `length` bytes have
been written or the end of `data` is reached, whichever comes first.

### Return Values

Returns the number of bytes written or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::read" class="xref"></a>

OCILob::writeTemporary
======================

Writes a temporary large object

### Description

<span class="type">bool</span> <span
class="methodname">OCILob::writeTemporary</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> \[,
<span class="methodparam"><span class="type">int</span> `$lob_type`<span
class="initializer"> = OCI\_TEMP\_CLOB</span></span> \] )

Creates a temporary large object and writes `data` to it.

You should use <a href="/book/oci8.html#OCILob::close" class="xref"></a>
when you are done with this object.

### Parameters

`data`  
The data to write.

`lob_type`  
Can be one of the following:

-   **`OCI_TEMP_BLOB`** is used to create temporary BLOBs
-   **`OCI_TEMP_CLOB`** is used to create temporary CLOBs

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

### See Also

-   <a href="/book/oci8.html#OCILob::close" class="xref"></a>

OCILob::writeToFile
===================

Alias of <span class="function">OCILob::export</span>

### Description

This function is an alias of: <span
class="function">OCILob::export</span>.

### Changelog

| Version                | Description                                                                                                                               |
|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0, PECL OCI8 3.0.0 | The <span class="classname">OCI-Lob</span> class was renamed to <span class="classname">OCILob</span> to align with PHP naming standards. |

oci\_internal\_debug
====================

Enables or disables internal debug output

### Description

<span class="type">void</span> <span
class="methodname">oci\_internal\_debug</span> ( <span
class="methodparam"><span class="type">bool</span> `$onoff`</span> )

Enables or disables internal debug output.

### Parameters

`onoff`  
Set this to **`false`** to turn debug output off or **`true`** to turn
it on.

### Return Values

No value is returned.

### Notes

> **Note**:
>
> This function was removed in PHP 8 and PECL OCI8 3.0.

> **Note**:
>
> This function is a no-op in PHP 5.6 and PECL OCI8 2.0. Use DTrace
> instead.

> **Note**:
>
> In PHP versions before 5.0.0 you must use <span
> class="function">ociinternaldebug</span> instead. This name still can
> be used, it was left as alias of <span
> class="function">oci\_internal\_debug</span> for downwards
> compatability. This, however, is deprecated and not recommended.

ocibindbyname
=============

Alias of <span class="function">oci\_bind\_by\_name</span>

### Description

Alias of <span class="function">oci\_bind\_by\_name</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicancel
=========

Alias of <span class="function">oci\_cancel</span>

### Description

Alias of <span class="function">oci\_cancel</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicloselob
===========

Alias of <span class="function">OCI-Lob::close</span>

### Description

Alias of <span class="function">OCI-Lob::close</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicollappend
=============

Alias of <span class="function">OCICollection::append</span>

### Description

Alias of <span class="function">OCICollection::append</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicollassign
=============

Alias of <span class="function">OCICollection::assign</span>

### Description

Alias of <span class="function">OCICollection::assign</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicollassignelem
=================

Alias of <span class="function">OCICollection::assignElem</span>

### Description

Alias of <span class="function">OCICollection::assignElem</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicollgetelem
==============

Alias of <span class="function">OCICollection::getElem</span>

### Description

Alias of <span class="function">OCICollection::getElem</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicollmax
==========

Alias of <span class="function">OCICollection::max</span>

### Description

Alias of <span class="function">OCICollection::max</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicollsize
===========

Alias of <span class="function">OCICollection::size</span>

### Description

Alias of <span class="function">OCICollection::size</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicolltrim
===========

Alias of <span class="function">OCICollection::trim</span>

### Description

Alias of <span class="function">OCICollection::trim</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicolumnisnull
===============

Alias of <span class="function">oci\_field\_is\_null</span>

### Description

Alias of <span class="function">oci\_field\_is\_null</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicolumnname
=============

Alias of <span class="function">oci\_field\_name</span>

### Description

Alias of <span class="function">oci\_field\_name</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicolumnprecision
==================

Alias of <span class="function">oci\_field\_precision</span>

### Description

Alias of <span class="function">oci\_field\_precision</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicolumnscale
==============

Alias of <span class="function">oci\_field\_scale</span>

### Description

Alias of <span class="function">oci\_field\_scale</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicolumnsize
=============

Alias of <span class="function">oci\_field\_size</span>

### Description

Alias of <span class="function">oci\_field\_size</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicolumntype
=============

Alias of <span class="function">oci\_field\_type</span>

### Description

Alias of <span class="function">oci\_field\_type</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicolumntyperaw
================

Alias of <span class="function">oci\_field\_type\_raw</span>

### Description

Alias of <span class="function">oci\_field\_type\_raw</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocicommit
=========

Alias of <span class="function">oci\_commit</span>

### Description

Alias of <span class="function">oci\_commit</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocidefinebyname
===============

Alias of <span class="function">oci\_define\_by\_name</span>

### Description

Alias of <span class="function">oci\_define\_by\_name</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocierror
========

Alias of <span class="function">oci\_error</span>

### Description

Alias of <span class="function">oci\_error</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociexecute
==========

Alias of <span class="function">oci\_execute</span>

### Description

Alias of <span class="function">oci\_execute</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocifetch
========

Alias of <span class="function">oci\_fetch</span>

### Description

Alias of <span class="function">oci\_fetch</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocifetchinto
============

Obsolete variant of <span class="function">oci\_fetch\_array</span>,
<span class="function">oci\_fetch\_object</span>, <span
class="function">oci\_fetch\_assoc</span> and <span
class="function">oci\_fetch\_row</span>

### Description

Obsolete variant of <span class="function">oci\_fetch\_array</span>,
<span class="function">oci\_fetch\_object</span>, <span
class="function">oci\_fetch\_assoc</span> and <span
class="function">oci\_fetch\_row</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocifetchstatement
=================

Alias of <span class="function">oci\_fetch\_all</span>

### Description

Alias of <span class="function">oci\_fetch\_all</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocifreecollection
=================

Alias of <span class="function">OCICollection::free</span>

### Description

Alias of <span class="function">OCICollection::free</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocifreecursor
=============

Alias of <span class="function">oci\_free\_statement</span>

### Description

Alias of <span class="function">oci\_free\_statement</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocifreedesc
===========

Alias of <span class="function">OCI-Lob::free</span>

### Description

Alias of <span class="function">OCI-Lob::free</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocifreestatement
================

Alias of <span class="function">oci\_free\_statement</span>

### Description

Alias of <span class="function">oci\_free\_statement</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociinternaldebug
================

Alias of <span class="function">oci\_internal\_debug</span>

### Description

Alias of <span class="function">oci\_internal\_debug</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociloadlob
==========

Alias of <span class="function">OCI-Lob::load</span>

### Description

Alias of <span class="function">OCI-Lob::load</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocilogoff
=========

Alias of <span class="function">oci\_close</span>

### Description

Alias of <span class="function">oci\_close</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocilogon
========

Alias of <span class="function">oci\_connect</span>

### Description

Alias of <span class="function">oci\_connect</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocinewcollection
================

Alias of <span class="function">oci\_new\_collection</span>

### Description

Alias of <span class="function">oci\_new\_collection</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocinewcursor
============

Alias of <span class="function">oci\_new\_cursor</span>

### Description

Alias of <span class="function">oci\_new\_cursor</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocinewdescriptor
================

Alias of <span class="function">oci\_new\_descriptor</span>

### Description

Alias of <span class="function">oci\_new\_descriptor</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocinlogon
=========

Alias of <span class="function">oci\_new\_connect</span>

### Description

Alias of <span class="function">oci\_new\_connect</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocinumcols
==========

Alias of <span class="function">oci\_num\_fields</span>

### Description

Alias of <span class="function">oci\_num\_fields</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociparse
========

Alias of <span class="function">oci\_parse</span>

### Description

Alias of <span class="function">oci\_parse</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociplogon
=========

Alias of <span class="function">oci\_pconnect</span>

### Description

Alias of <span class="function">oci\_pconnect</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociresult
=========

Alias of <span class="function">oci\_result</span>

### Description

Alias of <span class="function">oci\_result</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocirollback
===========

Alias of <span class="function">oci\_rollback</span>

### Description

Alias of <span class="function">oci\_rollback</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocirowcount
===========

Alias of <span class="function">oci\_num\_rows</span>

### Description

Alias of <span class="function">oci\_num\_rows</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocisavelob
==========

Alias of <span class="function">OCI-Lob::save</span>

### Description

Alias of <span class="function">OCI-Lob::save</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocisavelobfile
==============

Alias of <span class="function">OCI-Lob::import</span>

### Description

Alias of <span class="function">OCI-Lob::import</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociserverversion
================

Alias of <span class="function">oci\_server\_version</span>

### Description

Alias of <span class="function">oci\_server\_version</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocisetprefetch
==============

Alias of <span class="function">oci\_set\_prefetch</span>

### Description

Alias of <span class="function">oci\_set\_prefetch</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ocistatementtype
================

Alias of <span class="function">oci\_statement\_type</span>

### Description

Alias of <span class="function">oci\_statement\_type</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociwritelobtofile
=================

Alias of <span class="function">OCI-Lob::export</span>

### Description

Alias of <span class="function">OCI-Lob::export</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

ociwritetemporarylob
====================

Alias of <span class="function">OCI-Lob::writeTemporary</span>

### Description

Alias of <span class="function">OCI-Lob::writeTemporary</span>

**Warning**

This alias has been *DEPRECATED* as of PHP 5.4.0. Relying on this alias
is highly discouraged.

**Table of Contents**

-   [oci\_internal\_debug](/book/oci8.html#oci_internal_debug) — Enables
    or disables internal debug output
-   [ocibindbyname](/book/oci8.html#ocibindbyname) — Alias of
    oci\_bind\_by\_name
-   [ocicancel](/book/oci8.html#ocicancel) — Alias of oci\_cancel
-   [ocicloselob](/book/oci8.html#ocicloselob) — Alias of OCI-Lob::close
-   [ocicollappend](/book/oci8.html#ocicollappend) — Alias of
    OCICollection::append
-   [ocicollassign](/book/oci8.html#ocicollassign) — Alias of
    OCICollection::assign
-   [ocicollassignelem](/book/oci8.html#ocicollassignelem) — Alias of
    OCICollection::assignElem
-   [ocicollgetelem](/book/oci8.html#ocicollgetelem) — Alias of
    OCICollection::getElem
-   [ocicollmax](/book/oci8.html#ocicollmax) — Alias of
    OCICollection::max
-   [ocicollsize](/book/oci8.html#ocicollsize) — Alias of
    OCICollection::size
-   [ocicolltrim](/book/oci8.html#ocicolltrim) — Alias of
    OCICollection::trim
-   [ocicolumnisnull](/book/oci8.html#ocicolumnisnull) — Alias of
    oci\_field\_is\_null
-   [ocicolumnname](/book/oci8.html#ocicolumnname) — Alias of
    oci\_field\_name
-   [ocicolumnprecision](/book/oci8.html#ocicolumnprecision) — Alias of
    oci\_field\_precision
-   [ocicolumnscale](/book/oci8.html#ocicolumnscale) — Alias of
    oci\_field\_scale
-   [ocicolumnsize](/book/oci8.html#ocicolumnsize) — Alias of
    oci\_field\_size
-   [ocicolumntype](/book/oci8.html#ocicolumntype) — Alias of
    oci\_field\_type
-   [ocicolumntyperaw](/book/oci8.html#ocicolumntyperaw) — Alias of
    oci\_field\_type\_raw
-   [ocicommit](/book/oci8.html#ocicommit) — Alias of oci\_commit
-   [ocidefinebyname](/book/oci8.html#ocidefinebyname) — Alias of
    oci\_define\_by\_name
-   [ocierror](/book/oci8.html#ocierror) — Alias of oci\_error
-   [ociexecute](/book/oci8.html#ociexecute) — Alias of oci\_execute
-   [ocifetch](/book/oci8.html#ocifetch) — Alias of oci\_fetch
-   [ocifetchinto](/book/oci8.html#ocifetchinto) — Obsolete variant of
    oci\_fetch\_array, oci\_fetch\_object, oci\_fetch\_assoc and
    oci\_fetch\_row
-   [ocifetchstatement](/book/oci8.html#ocifetchstatement) — Alias of
    oci\_fetch\_all
-   [ocifreecollection](/book/oci8.html#ocifreecollection) — Alias of
    OCICollection::free
-   [ocifreecursor](/book/oci8.html#ocifreecursor) — Alias of
    oci\_free\_statement
-   [ocifreedesc](/book/oci8.html#ocifreedesc) — Alias of OCI-Lob::free
-   [ocifreestatement](/book/oci8.html#ocifreestatement) — Alias of
    oci\_free\_statement
-   [ociinternaldebug](/book/oci8.html#ociinternaldebug) — Alias of
    oci\_internal\_debug
-   [ociloadlob](/book/oci8.html#ociloadlob) — Alias of OCI-Lob::load
-   [ocilogoff](/book/oci8.html#ocilogoff) — Alias of oci\_close
-   [ocilogon](/book/oci8.html#ocilogon) — Alias of oci\_connect
-   [ocinewcollection](/book/oci8.html#ocinewcollection) — Alias of
    oci\_new\_collection
-   [ocinewcursor](/book/oci8.html#ocinewcursor) — Alias of
    oci\_new\_cursor
-   [ocinewdescriptor](/book/oci8.html#ocinewdescriptor) — Alias of
    oci\_new\_descriptor
-   [ocinlogon](/book/oci8.html#ocinlogon) — Alias of oci\_new\_connect
-   [ocinumcols](/book/oci8.html#ocinumcols) — Alias of oci\_num\_fields
-   [ociparse](/book/oci8.html#ociparse) — Alias of oci\_parse
-   [ociplogon](/book/oci8.html#ociplogon) — Alias of oci\_pconnect
-   [ociresult](/book/oci8.html#ociresult) — Alias of oci\_result
-   [ocirollback](/book/oci8.html#ocirollback) — Alias of oci\_rollback
-   [ocirowcount](/book/oci8.html#ocirowcount) — Alias of oci\_num\_rows
-   [ocisavelob](/book/oci8.html#ocisavelob) — Alias of OCI-Lob::save
-   [ocisavelobfile](/book/oci8.html#ocisavelobfile) — Alias of
    OCI-Lob::import
-   [ociserverversion](/book/oci8.html#ociserverversion) — Alias of
    oci\_server\_version
-   [ocisetprefetch](/book/oci8.html#ocisetprefetch) — Alias of
    oci\_set\_prefetch
-   [ocistatementtype](/book/oci8.html#ocistatementtype) — Alias of
    oci\_statement\_type
-   [ociwritelobtofile](/book/oci8.html#ociwritelobtofile) — Alias of
    OCI-Lob::export
-   [ociwritetemporarylob](/book/oci8.html#ociwritetemporarylob) — Alias
    of OCI-Lob::writeTemporary

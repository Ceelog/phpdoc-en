tokyo\_tyrant
=============

**Table of Contents**

-   [Introduction](/book/tokyo-tyrant.html#Introduction)
-   [Installing/Configuring](/book/tokyo-tyrant.html#Installing/Configuring)
    -   [Requirements](/book/tokyo-tyrant.html#Requirements)
    -   [Installation](/book/tokyo-tyrant.html#Installation)
    -   [Runtime
        Configuration](/book/tokyo-tyrant.html#Runtime%20Configuration)
    -   [Resource Types](/book/tokyo-tyrant.html#Resource%20Types)
-   [Predefined
    Constants](/book/tokyo-tyrant.html#Predefined%20Constants)
-   [Examples](/book/tokyo-tyrant.html#Examples)
-   [TokyoTyrant](/book/tokyo-tyrant.html#TokyoTyrant) — The TokyoTyrant
    class
    -   [TokyoTyrant::add](/book/tokyo-tyrant.html#TokyoTyrant::add) —
        Adds to a numeric key
    -   [TokyoTyrant::connect](/book/tokyo-tyrant.html#TokyoTyrant::connect)
        — Connect to a database
    -   [TokyoTyrant::connectUri](/book/tokyo-tyrant.html#TokyoTyrant::connectUri)
        — Connects to a database
    -   [TokyoTyrant::\_\_construct](/book/tokyo-tyrant.html#TokyoTyrant::__construct)
        — Construct a new TokyoTyrant object
    -   [TokyoTyrant::copy](/book/tokyo-tyrant.html#TokyoTyrant::copy) —
        Copies the database
    -   [TokyoTyrant::ext](/book/tokyo-tyrant.html#TokyoTyrant::ext) —
        Execute a remote script
    -   [TokyoTyrant::fwmKeys](/book/tokyo-tyrant.html#TokyoTyrant::fwmKeys)
        — Returns the forward matching keys
    -   [TokyoTyrant::get](/book/tokyo-tyrant.html#TokyoTyrant::get) —
        The get purpose
    -   [TokyoTyrant::getIterator](/book/tokyo-tyrant.html#TokyoTyrant::getIterator)
        — Get an iterator
    -   [TokyoTyrant::num](/book/tokyo-tyrant.html#TokyoTyrant::num) —
        Number of records in the database
    -   [TokyoTyrant::out](/book/tokyo-tyrant.html#TokyoTyrant::out) —
        Removes records
    -   [TokyoTyrant::put](/book/tokyo-tyrant.html#TokyoTyrant::put) —
        Puts values
    -   [TokyoTyrant::putCat](/book/tokyo-tyrant.html#TokyoTyrant::putCat)
        — Concatenates to a record
    -   [TokyoTyrant::putKeep](/book/tokyo-tyrant.html#TokyoTyrant::putKeep)
        — Puts a record
    -   [TokyoTyrant::putNr](/book/tokyo-tyrant.html#TokyoTyrant::putNr)
        — Puts value
    -   [TokyoTyrant::putShl](/book/tokyo-tyrant.html#TokyoTyrant::putShl)
        — Concatenates to a record
    -   [TokyoTyrant::restore](/book/tokyo-tyrant.html#TokyoTyrant::restore)
        — Restore the database
    -   [TokyoTyrant::setMaster](/book/tokyo-tyrant.html#TokyoTyrant::setMaster)
        — Set the replication master
    -   [TokyoTyrant::size](/book/tokyo-tyrant.html#TokyoTyrant::size) —
        Returns the size of the value
    -   [TokyoTyrant::stat](/book/tokyo-tyrant.html#TokyoTyrant::stat) —
        Get statistics
    -   [TokyoTyrant::sync](/book/tokyo-tyrant.html#TokyoTyrant::sync) —
        Synchronize the database
    -   [TokyoTyrant::tune](/book/tokyo-tyrant.html#TokyoTyrant::tune) —
        Tunes connection values
    -   [TokyoTyrant::vanish](/book/tokyo-tyrant.html#TokyoTyrant::vanish)
        — Empties the database
-   [TokyoTyrantTable](/book/tokyo-tyrant.html#TokyoTyrantTable) — The
    TokyoTyrantTable class
    -   [TokyoTyrantTable::add](/book/tokyo-tyrant.html#TokyoTyrantTable::add)
        — Adds a record
    -   [TokyoTyrantTable::genUid](/book/tokyo-tyrant.html#TokyoTyrantTable::genUid)
        — Generate unique id
    -   [TokyoTyrantTable::get](/book/tokyo-tyrant.html#TokyoTyrantTable::get)
        — Get a row
    -   [TokyoTyrantTable::getIterator](/book/tokyo-tyrant.html#TokyoTyrantTable::getIterator)
        — Get an iterator
    -   [TokyoTyrantTable::getQuery](/book/tokyo-tyrant.html#TokyoTyrantTable::getQuery)
        — Get a query object
    -   [TokyoTyrantTable::out](/book/tokyo-tyrant.html#TokyoTyrantTable::out)
        — Remove records
    -   [TokyoTyrantTable::put](/book/tokyo-tyrant.html#TokyoTyrantTable::put)
        — Store a row
    -   [TokyoTyrantTable::putCat](/book/tokyo-tyrant.html#TokyoTyrantTable::putCat)
        — Concatenates to a row
    -   [TokyoTyrantTable::putKeep](/book/tokyo-tyrant.html#TokyoTyrantTable::putKeep)
        — Put a new record
    -   [TokyoTyrantTable::putNr](/book/tokyo-tyrant.html#TokyoTyrantTable::putNr)
        — Puts value
    -   [TokyoTyrantTable::putShl](/book/tokyo-tyrant.html#TokyoTyrantTable::putShl)
        — Concatenates to a record
    -   [TokyoTyrantTable::setIndex](/book/tokyo-tyrant.html#TokyoTyrantTable::setIndex)
        — Sets index
-   [TokyoTyrantQuery](/book/tokyo-tyrant.html#TokyoTyrantQuery) — The
    TokyoTyrantQuery class
    -   [TokyoTyrantQuery::addCond](/book/tokyo-tyrant.html#TokyoTyrantQuery::addCond)
        — Adds a condition to the query
    -   [TokyoTyrantQuery::\_\_construct](/book/tokyo-tyrant.html#TokyoTyrantQuery::__construct)
        — Construct a new query
    -   [TokyoTyrantQuery::count](/book/tokyo-tyrant.html#TokyoTyrantQuery::count)
        — Counts records
    -   [TokyoTyrantQuery::current](/book/tokyo-tyrant.html#TokyoTyrantQuery::current)
        — Returns the current element
    -   [TokyoTyrantQuery::hint](/book/tokyo-tyrant.html#TokyoTyrantQuery::hint)
        — Get the hint string of the query
    -   [TokyoTyrantQuery::key](/book/tokyo-tyrant.html#TokyoTyrantQuery::key)
        — Returns the current key
    -   [TokyoTyrantQuery::metaSearch](/book/tokyo-tyrant.html#TokyoTyrantQuery::metaSearch)
        — Retrieve records with multiple queries
    -   [TokyoTyrantQuery::next](/book/tokyo-tyrant.html#TokyoTyrantQuery::next)
        — Moves the iterator to next entry
    -   [TokyoTyrantQuery::out](/book/tokyo-tyrant.html#TokyoTyrantQuery::out)
        — Removes records based on query
    -   [TokyoTyrantQuery::rewind](/book/tokyo-tyrant.html#TokyoTyrantQuery::rewind)
        — Rewinds the iterator
    -   [TokyoTyrantQuery::search](/book/tokyo-tyrant.html#TokyoTyrantQuery::search)
        — Searches records
    -   [TokyoTyrantQuery::setLimit](/book/tokyo-tyrant.html#TokyoTyrantQuery::setLimit)
        — Limit results
    -   [TokyoTyrantQuery::setOrder](/book/tokyo-tyrant.html#TokyoTyrantQuery::setOrder)
        — Orders results
    -   [TokyoTyrantQuery::valid](/book/tokyo-tyrant.html#TokyoTyrantQuery::valid)
        — Checks the validity of current item
-   [TokyoTyrantIterator](/book/tokyo-tyrant.html#TokyoTyrantIterator) —
    The TokyoTyrantIterator class
    -   [TokyoTyrantIterator::\_\_construct](/book/tokyo-tyrant.html#TokyoTyrantIterator::__construct)
        — Construct an iterator
    -   [TokyoTyrantIterator::current](/book/tokyo-tyrant.html#TokyoTyrantIterator::current)
        — Get the current value
    -   [TokyoTyrantIterator::key](/book/tokyo-tyrant.html#TokyoTyrantIterator::key)
        — Returns the current key
    -   [TokyoTyrantIterator::next](/book/tokyo-tyrant.html#TokyoTyrantIterator::next)
        — Move to next key
    -   [TokyoTyrantIterator::rewind](/book/tokyo-tyrant.html#TokyoTyrantIterator::rewind)
        — Rewinds the iterator
    -   [TokyoTyrantIterator::valid](/book/tokyo-tyrant.html#TokyoTyrantIterator::valid)
        — Rewinds the iterator
-   [TokyoTyrantException](/book/tokyo-tyrant.html#TokyoTyrantException)
    — The TokyoTyrantException class

tokyo\_tyrant extension provides a wrapper for Tokyo Tyrant client
libraries. The extension contains the normal key-value API and the table
API.

*"Tokyo Tyrant is a package of network interface to the DBM called Tokyo
Cabinet. Though the DBM has high performance, you might bother in case
that multiple processes share the same database, or remote processes
access the database. Thus, Tokyo Tyrant is provided for concurrent and
remote connections to Tokyo Cabinet. It is composed of the server
process managing a database and its access library for client
applications." --Tokyo Tyrant documentation*

Tokyo Tyrant is written by Mikio Hirabayashi and is licensed under GNU
Lesser General Public License.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/tokyo-tyrant.html#Requirements)
-   [Installation](/book/tokyo-tyrant.html#Installation)
-   [Runtime
    Configuration](/book/tokyo-tyrant.html#Runtime%20Configuration)
-   [Resource Types](/book/tokyo-tyrant.html#Resource%20Types)

Requirements
------------

Before using this extension Tokyo Cabinet and Tokyo Tyrant must be
installed.

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/tokyo_tyrant" class="link external">» https://pecl.php.net/package/tokyo_tyrant</a>

Configure options
-----------------

-   *--with-tokyo-tyrant\[=DIR\]* DIR is the prefix to the Tokyo Tyrant
    installation
-   *--with-tokyo-cabinet-dir\[=DIR\]* DIR is the prefix to the Tokyo
    Cabinet installation
-   *--disable-tokyo-tyrant-session* Disable Tokyo Tyrant session
    handler support

Enabling the extension
----------------------

The extension can be enabled by adding *extension=tokyo\_tyrant.so* to
the INI-configuration

Running Tokyo Tyrant for the session handler
--------------------------------------------

*ttserver -port 2000 -ext /path/to/expire.lua -extpc expire 30.0
'/tmp/sessions.tct\#idx=ts:dec'*

> **Note**: <span class="simpara"> expire.lua is included in the
> tokyo\_tyrant extension source distribution </span>

Configuring session handler
---------------------------

-   tokyo\_tyrant.session\_salt="randomlongstring"
-   session.save\_handler=tokyo\_tyrant
-   session.save\_path="tcp://hostname1:2000,tcp://hostname2:2000"

> **Note**: <span class="simpara"> It is important to make sure that
> <a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.session_salt</a>
> matches on all servers. </span>

How it works?
-------------

The session handler creates a session id like the following:
8b0e27a823fa4a6cf7246945b82c1d51-a5eadbbed1f2075952900628456bfd6830541629-0-5460

The parts from left to right:

-   *Session id* - Generated session id
-   *Checksum* - Checksum of session salt, session id, node id and
    primary key
-   *Node id* - The id of the node where the session maps to
-   *Primary key* - The primary key of the row where the session is
    stored

The checksum contains SHA1 sum of the node id, primary key, session id
and the salt which is known only on the server side. This allows quick
mapping of session id to node and primary key since there is no need to
do an additional search. During session id regeneration only the parts 1
and 2 change but the mapping to the node and primary key stays constant.

In case some of the nodes fail
<a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.allow_failover</a>,
<a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.fail_threshold</a>
and
<a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.health_check_divisor</a>
INI-settings control the behavior during failover. If failover is
allowed the session handler will map the session to a healthy node and
creates a new empty session.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                                  | Default    | Changeable    | Changelog |
|---------------------------------------------------------------------------------------|------------|---------------|-----------|
| <a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.default_timeout</a>      | 2.0        | PHP\_INI\_ALL |           |
| <a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.session_salt</a>         | **`NULL`** | PHP\_INI\_ALL |           |
| <a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.key_prefix</a>           | **`NULL`** | PHP\_INI\_ALL |           |
| <a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.allow_failover</a>       | 1          | PHP\_INI\_ALL |           |
| <a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.fail_threshold</a>       | 5          | PHP\_INI\_ALL |           |
| <a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.health_check_divisor</a> | 1000       | PHP\_INI\_ALL |           |
| <a href="/book/tokyo-tyrant.html#" class="link">tokyo_tyrant.php_expiration</a>       | 0          | PHP\_INI\_ALL |           |

Here's a short explanation of the configuration directives.

`tokyo_tyrant.default_timeout` <span class="type">int</span>  
Default timeout when connecting to databases

`tokyo_tyrant.session_salt` <span class="type">string</span>  
The secret that is used to salt session id

`tokyo_tyrant.key_prefix` <span class="type">string</span>  
Prefix all keys with this string. The prefix is transparent to the
developer but helps making sure that keys won't collide if multiple
applications are using the same database.

`tokyo_tyrant.allow_failover` <span class="type">int</span>  
Whether to allow session failover in case a server dies.

`tokyo_tyrant.fail_threshold` <span class="type">int</span>  
How many read/write or connection failures is allowed before server is
marked as failed.

`tokyo_tyrant.health_check_divisor` <span class="type">int</span>  
Defines the divisor for the health check probability. If there are
failed servers and the probability matches, the servers are health
checked and in case the server seems healthy, it will be added back to
the pool.

`tokyo_tyrant.php_expiration` <span class="type">int</span>  
Whether to use built in session expiration mechanism or delegate the
expiration to a lua-script on the server-side.

Resource Types
--------------

This extension has no resource types defined.

Predefined Constants
====================

<a href="/book/tokyo-tyrant.html#TokyoTyrant%20Constants" class="link">TokyoTyrant constants</a>

Examples
========

Basic usage

**Example \#1 Putting and getting a key-value pair**

``` php
<?php
$tt = new TokyoTyrant("localhost");
$tt->put("key", "value");
echo $tt->get("key");
?>
```

The above example will output:

    value

Introduction
------------

The main Tokyo Tyrant class

Class synopsis
--------------

**TokyoTyrant**

<span class="ooclass"> class **TokyoTyrant** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBDEF_PORT` <span class="initializer"> = 1978</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_STREQ` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_STRINC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_STRBW` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_STREW` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_STRAND` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_STROR` <span class="initializer"> = 5</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_STROREQ` <span class="initializer"> = 6</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_STRRX` <span class="initializer"> = 7</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NUMEQ` <span class="initializer"> = 8</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NUMGT` <span class="initializer"> = 9</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NUMGE` <span class="initializer"> = 10</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NUMLT` <span class="initializer"> = 11</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NUMLE` <span class="initializer"> = 12</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NUMBT` <span class="initializer"> = 13</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NUMOREQ` <span class="initializer"> = 14</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NEGATE` <span class="initializer"> = 16777216</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQC_NOIDX` <span class="initializer"> = 33554432</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQO_STRASC` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQO_STRDESC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQO_NUMASC` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQO_NUMDESC` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBIT_LEXICAL` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBIT_DECIMAL` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBIT_TOKEN` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBIT_QGRAM` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBIT_OPT` <span class="initializer"> = 9998</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBIT_VOID` <span class="initializer"> = 9999</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBIT_KEEP` <span class="initializer"> = 16777216</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQCFTS_PH` <span class="initializer"> = 15</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQCFTS_AND` <span class="initializer"> = 16</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQCFTS_OR` <span class="initializer"> = 17</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBQCFTS_EX` <span class="initializer"> = 18</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBXO_LCKREC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBXOLCK_GLB` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBREC_INT` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBREC_DBL` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBMS_UNION` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBMS_ISECT` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBMS_DIFF` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`TokyoTyrant::RDBT_RECON` <span class="initializer"> = 1</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">float</span></span> <span
class="methodname">add</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type"><span
class="type">int</span><span class="type">float</span></span>
`$increment`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span class="methodname">connect</span>
( <span class="methodparam"><span class="type">string</span>
`$host`</span> \[, <span class="methodparam"><span
class="type">int</span> `$port`<span class="initializer"> =
TokyoTyrant::RDBDEF\_PORT</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">connectUri</span> ( <span class="methodparam"><span
class="type">string</span> `$uri`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = TokyoTyrant::RDBDEF\_PORT</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span class="methodname">copy</span> (
<span class="methodparam"><span class="type">string</span>
`$path`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">ext</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> , <span
class="methodparam"><span class="type">int</span> `$options`</span> ,
<span class="methodparam"><span class="type">string</span> `$key`</span>
, <span class="methodparam"><span class="type">string</span>
`$value`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">fwmKeys</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span> ,
<span class="methodparam"><span class="type">int</span>
`$max_recs`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">get</span> ( <span class="methodparam"><span
class="type">mixed</span> `$keys`</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrantIterator</span> <span
class="methodname">getIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">num</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span class="methodname">out</span> (
<span class="methodparam"><span class="type">mixed</span> `$keys`</span>
)

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span class="methodname">put</span> (
<span class="methodparam"><span class="type">mixed</span> `$keys`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$value`<span class="initializer"> = NULL</span></span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span class="methodname">putCat</span> (
<span class="methodparam"><span class="type">mixed</span> `$keys`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span class="methodname">putKeep</span>
( <span class="methodparam"><span class="type">mixed</span>
`$keys`</span> \[, <span class="methodparam"><span
class="type">string</span> `$value`</span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span class="methodname">putNr</span> (
<span class="methodparam"><span class="type">mixed</span> `$keys`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$value`<span class="initializer"> = NULL</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">putShl</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> ,
<span class="methodparam"><span class="type">int</span> `$width`</span>
)

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">restore</span> ( <span
class="methodparam"><span class="type">string</span> `$log_dir`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$check_consistency`<span class="initializer">
= **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">setMaster</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$check_consistency`<span class="initializer">
= **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">size</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">stat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">sync</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span class="methodname">tune</span> (
<span class="methodparam"><span class="type">float</span>
`$timeout`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`<span class="initializer"> =
TokyoTyrant::RDBT\_RECON</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">vanish</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

TokyoTyrant Constants
---------------------

**`TokyoTyrant::RDBDEF_PORT`**  
The default port of the Tokyo Tyrant database

**`TokyoTyrant::RDBQC_STREQ`**  
string is equal to

**`TokyoTyrant::RDBQC_STRINC`**  
string is included in

**`TokyoTyrant::RDBQC_STRBW`**  
string begins with

**`TokyoTyrant::RDBQC_STREW`**  
string ends with

**`TokyoTyrant::RDBQC_STRAND`**  
string includes all tokens in

**`TokyoTyrant::RDBQC_STROR`**  
string includes at least one token in

**`TokyoTyrant::RDBQC_STROREQ`**  
string is equal to at least one token in

**`TokyoTyrant::RDBQC_STRRX`**  
string matches regular expressions of

**`TokyoTyrant::RDBQC_NUMEQ`**  
number is equal to

**`TokyoTyrant::RDBQC_NUMGT`**  
number is greater than

**`TokyoTyrant::RDBQC_NUMGE`**  
number is greater than or equal to

**`TokyoTyrant::RDBQC_NUMLT`**  
number is less than

**`TokyoTyrant::RDBQC_NUMLE`**  
number is less than or equal to

**`TokyoTyrant::RDBQC_NUMBT`**  
number is between two tokens of

**`TokyoTyrant::RDBQC_NUMOREQ`**  
number is equal to at least one token in

**`TokyoTyrant::RDBQC_NEGATE`**  
negation flag

**`TokyoTyrant::RDBQC_NOIDX`**  
no index flag

**`TokyoTyrant::RDBQO_STRASC`**  
string ascending

**`TokyoTyrant::RDBQO_STRDESC`**  
string descending

**`TokyoTyrant::RDBQO_NUMASC`**  
number ascending

**`TokyoTyrant::RDBQO_NUMDESC`**  
number descending

**`TokyoTyrant::RDBIT_LEXICAL`**  
lexical string

**`TokyoTyrant::RDBIT_DECIMAL`**  
decimal string

**`TokyoTyrant::RDBIT_TOKEN`**  
token inverted index (Tokyo Tyrant \>= 1.1.29)

**`TokyoTyrant::RDBIT_QGRAM`**  
QGRAM inverted index (Tokyo Tyrant \>= 1.1.29)

**`TokyoTyrant::RDBIT_OPT`**  
optimize

**`TokyoTyrant::RDBIT_VOID`**  
void

**`TokyoTyrant::RDBIT_KEEP`**  
keep existing index

**`TokyoTyrant::RDBQCFTS_PH`**  
full-text search with the phrase of (Tokyo Tyrant \>= 1.1.29)

**`TokyoTyrant::RDBQCFTS_AND`**  
full-text search with all tokens in (Tokyo Tyrant \>= 1.1.29)

**`TokyoTyrant::RDBQCFTS_OR`**  
full-text search with at least one token in (Tokyo Tyrant \>= 1.1.29)

**`TokyoTyrant::RDBQCFTS_EX`**  
full-text search with the compound expression of (Tokyo Tyrant \>=
1.1.29)

**`TokyoTyrant::RDBQCFTS_AND`**  
Metasearch union between records (Tokyo Tyrant \>= 1.1.33)

**`TokyoTyrant::RDBQCFTS_OR`**  
Metasearch intersection between records (Tokyo Tyrant \>= 1.1.33)

**`TokyoTyrant::RDBQCFTS_EX`**  
Metasearch difference between records (Tokyo Tyrant \>= 1.1.33)

**`TokyoTyrant::RDBT_RECON`**  
Whether to reconnect on connection failure. It is recommended to have
this parameter on for persistent connections

**`TokyoTyrant::RDBXOLCK_REC`**  
record locking

**`TokyoTyrant::RDBXOLCK_GLB`**  
global locking

**`TokyoTyrant::RDBREC_INT`**  
record type int

**`TokyoTyrant::RDBREC_DBL`**  
record type float (double)

**`TokyoTyrant::TTE_SUCCESS`**  
success

**`TokyoTyrant::TTE_INVALID`**  
invalid operation

**`TokyoTyrant::TTE_NOHOST`**  
host not found

**`TokyoTyrant::TTE_REFUSED`**  
connection refused

**`TokyoTyrant::TTE_SEND`**  
send error

**`TokyoTyrant::TTE_RECV`**  
recv error

**`TokyoTyrant::TTE_KEEP`**  
record exist

**`TokyoTyrant::TTE_NOREC`**  
no record found

**`TokyoTyrant::TTE_MISC`**  
miscellaneous error

TokyoTyrant::add
================

Adds to a numeric key

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">float</span></span> <span
class="methodname">TokyoTyrant::add</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">float</span></span>
`$increment`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`<span class="initializer"> =
0</span></span> \] )

Adds to an int or double value. This increments the value by the given
amount and returns the new value. If the key does not exist a new key is
created with initial value of the increment parameter.

### Parameters

`key`  
The string key

`increment`  
The amount to increment

`type`  
**`TokyoTyrant::RDBREC_INT`** or **`TokyoTyrant::RDBREC_DBL`** constant.
If this parameter is omitted the type is guessed from the `increment`
parameters type.

### Return Values

Returns the new value on success

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::add</span> example**

``` php
<?php
$tt = new TokyoTyrant("localhost", TokyoTyrant::RDBDEF_PORT);
/* Adds integer 3 to key and creates a new key */
$tt->add("test", 3);

/* String value is converted to double */
echo $tt->add("test", "3.5", TokyoTyrant::RDBREC_DBL);
?>
```

The above example will output something similar to:

    6.5

### See Also

-   <span class="methodname">TokyoTyrant::put</span>
-   <span class="methodname">TokyoTyrant::putcat</span>
-   <span class="methodname">TokyoTyrant::putkeep</span>

TokyoTyrant::connect
====================

Connect to a database

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = TokyoTyrant::RDBDEF\_PORT</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\] )

Connects to a remote database

### Parameters

`host`  
The hostname

`port`  
The port. Default: 1978

`options`  
Connection options: timeout (default: 5.0), reconnect (default:
**`TRUE`**) and persistent (default: **`TRUE`**)

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::connect</span>
example**

``` php
<?php
$tt = new TokyoTyrant();
$tt->connect("localhost", TokyoTyrant::RDBDEF_PORT)->put("test", "value");
?>
```

### See Also

-   <span class="methodname">TokyoTyrant::connectUri</span>

TokyoTyrant::connectUri
=======================

Connects to a database

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::connectUri</span> ( <span
class="methodparam"><span class="type">string</span> `$uri`</span> )

Connects to a database using an uri

### Parameters

`uri`  
An URI to the database. For example *tcp://localhost:1979/*

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::connectUri</span>
example**

``` php
<?php
$tt = new TokyoTyrant();
$tt->connectUri("tcp://localhost:1978/")->put("test", "hi");
?>
```

### See Also

-   <span class="methodname">TokyoTyrant::connect</span>

TokyoTyrant::\_\_construct
==========================

Construct a new TokyoTyrant object

### Description

<span class="modifier">public</span> <span
class="methodname">TokyoTyrant::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = TokyoTyrant::RDBDEF\_PORT</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\] )

Constructs a new TokyoTyrant object and optionally connects to the
database

### Parameters

`host`  
The hostname. Default: **`NULL`**

`port`  
port number. Default: 1978

`options`  
Connection options: timeout (default: 5.0), reconnect (default:
**`TRUE`**) and persistent (default: **`TRUE`**)

### Return Values

Throws TokyoTyrantException if connection to database fails

### See Also

-   <span class="methodname">TokyoTyrant::connect</span>
-   <span class="methodname">TokyoTyrant::connectUri</span>

TokyoTyrant::copy
=================

Copies the database

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::copy</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

Makes a copy of the current database

### Parameters

`path`  
Path to where to copy the database. The user running the remote database
must have a write access to the directory.

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::copy</span>
example**

``` php
<?php
$tt = new TokyoTyrant("localhost", 1978);
$tt->copy("/tmp/foobar.tct");
?>
```

### See Also

-   <span class="methodname">TokyoTyrant::restore</span>

TokyoTyrant::ext
================

Execute a remote script

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">TokyoTyrant::ext</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span>
`$options`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Executes a remote script extension.

### Parameters

`name`  
Name of the function to execute

`options`  
Either **`TokyoTyrant::RDBXO_LCKREC`** for record locking and
**`TokyoTyrant::RDBXO_LCKGLB`** for global locking.

`key`  
The key to pass to the function

`value`  
The value to pass to the function

### Return Values

Returns the result of the script function

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::ext</span> example**

``` php
<?php
$tt = new TokyoTyrant("localhost", 1978);
echo $tt->ext("somefunc", TokyoTyrant::RDBXO_LCKREC, "some_key", "some_value");
?>
```

TokyoTyrant::fwmKeys
====================

Returns the forward matching keys

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrant::fwmKeys</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span> ,
<span class="methodparam"><span class="type">int</span>
`$max_recs`</span> )

Returns the forward matching keys from the database

### Parameters

`prefix`  
Prefix of the keys

`max_recs`  
Maximum records to return

### Return Values

Returns an array of matching keys. The values are not returned

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::fwmKeys</span>
example**

``` php
<?php

$tt = new TokyoTyrant("localhost");

/* Create 20 macthing keys */
for ($i = 0; $i < 20; $i++) {
    $tt->put("key_" . $i, "value_" . $i);
}

/* Create 20 non-macthing keys */
for ($i = 0; $i < 20; $i++) {
    $tt->put("something_" . $i, "data_" . $i);
}

/* Get five matching keys */
var_dump($tt->fwmKeys("key_", 5));
?>
```

The above example will output something similar to:

    array(5) {
      [0]=>
      string(5) "key_5"
      [1]=>
      string(6) "key_14"
      [2]=>
      string(5) "key_6"
      [3]=>
      string(6) "key_15"
      [4]=>
      string(5) "key_7"
    }

TokyoTyrant::get
================

The get purpose

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::get</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

This method is used to return a value or multiple values. This method
accepts a <span class="type">string</span> or an <span
class="type">array</span> as a value.

### Parameters

`keys`  
A <span class="type">string</span> key or an <span
class="type">array</span> of <span class="type">string</span> keys

### Return Values

Returns a string or an array based on the given parameters. Throws a
TokyoTyrantException on error. If string is passed null is returned if
the key is not found. In case an array is given as an parameter only
existing keys will be returned. It is not an error to pass a key that
does not exist.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::get</span> example**

``` php
<?php
$tt = new TokyoTyrant("localhost", 1978);
$tt->put("key1", "value1");
$tt->put("key2", "value2");
var_dump($tt->get(array("key1", "key2")));
var_dump($tt->get("key1"));
?>
```

The above example will output:

    array(2) {
      ["key1"]=>
      string(6) "value1"
      ["key2"]=>
      string(6) "value2"
    }
    string(6) "value1"

### See Also

-   <span class="methodname">TokyoTyrant::put</span>

TokyoTyrant::getIterator
========================

Get an iterator

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrantIterator</span> <span
class="methodname">TokyoTyrant::getIterator</span> ( <span
class="methodparam">void</span> )

Gets an iterator for iterating all keys / values in the database.

### Parameters

This function has no parameters.

### Return Values

This method returns TokyoTyrantIterator object and throws
TokyoTyrantException on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::getIterator</span>
example**

``` php
<?php
$tt = new TokyoTyrant("localhost");
$it = $tt->getIterator();

foreach ($it as $k => $v) {

}
?>
```

### See Also

-   <span class="methodname">TokyoTyrantTable::getQuery</span>
-   <span class="methodname">TokyoTyrantTable::getIterator</span>

TokyoTyrant::num
================

Number of records in the database

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrant::num</span> ( <span
class="methodparam">void</span> )

Returns the number of records in the database

### Parameters

This function has no parameters.

### Return Values

Returns number of records in the database

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::num</span> example**

``` php
<?php
/* Connect to a database on default port */
$tt = new TokyoTyrant("localhost");

/* Echo the number of records */
echo $tt->num();
?>
```

The above example will output something similar to:

    1234

### See Also

-   <span class="methodname">TokyoTyrant::stat</span>

TokyoTyrant::out
================

Removes records

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::out</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

Removes a record or multiple records. This method accepts a <span
class="type">string</span> for a single key or an array of keys for
multiple records.

### Parameters

`keys`  
A <span class="type">string</span> key or an <span
class="type">array</span> of <span class="type">string</span> keys

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::out</span> example**

``` php
<?php
/* Connect to a database on default port */
$tt = new TokyoTyrant("localhost");

$tt->put("test1", "value1");
$tt->put("test2", "value2");

$tt->out(array("test1", "test2"));
?>
```

### See Also

-   <span class="methodname">TokyoTyrant::put</span>

TokyoTyrant::put
================

Puts values

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::put</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span> `$value`<span
class="initializer"> = NULL</span></span> \] )

Puts a key-value pair into the database or multiple key-value pairs. If
`keys` is string then the second parameter value defines the value. The
second parameter is mandatory if `keys` is a string. If the key exists
the value will be replaced with new value.

### Parameters

`keys`  
A string key or an array of key-value pairs

`value`  
The value in case a string key is used

### Return Values

This method returns a reference to the current object and throws
TokyoTyrantException on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::put</span> example**

``` php
<?php
/* Connect to a database on default port */
$tt = new TokyoTyrant("localhost");

/* Put single key-value pair */
$tt->put("key", "value");

/* Put key-value pairs, new value overwrites the old */
$tt->put(array("key1" => "value1", "key" => "value2"));

/* Get back one key */
echo $tt->get("key");
?>
```

The above example will output:

    value2

### See Also

-   <span class="methodname">TokyoTyrant::putKeep</span>
-   <span class="methodname">TokyoTyrant::putCat</span>

TokyoTyrant::putCat
===================

Concatenates to a record

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putCat</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

Appends a value into existing key or multiple values if `keys` is an
array. The second parameter is mandatory if `keys` is a string. If the
record does not exist a new record is created.

### Parameters

`keys`  
A <span class="type">string</span> key or an <span
class="type">array</span> of key-value pairs

`value`  
The value in case a string key is used

### Return Values

This method returns a reference to the current object and throws
TokyoTyrantException on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::putCat</span>
example**

``` php
<?php
/* Connect to a database on default port */
$tt = new TokyoTyrant("localhost");

/* Create a new key */
$tt->put("key", "value");

/* Concatenate single key-value pair */
$tt->putCat("key", " has more data");

/* Echo the key */
echo $tt->get("key");
?>
```

The above example will output:

    value has more data

### See Also

-   <span class="methodname">TokyoTyrant::put</span>
-   <span class="methodname">TokyoTyrant::putKeep</span>

TokyoTyrant::putKeep
====================

Puts a record

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putKeep</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

Puts a key-value pair into the database or multiple key-value pairs. If
`keys` is string then the second parameter value defines the value. The
second parameter is mandatory if `keys` is a string. If the key already
exists this method throws an exception indicating that the records
exists.

### Parameters

`keys`  
A <span class="type">string</span> key or an <span
class="type">array</span> of key-value pairs

`value`  
The <span class="type">string</span> value

### Return Values

This method returns a reference to the current object and throws
TokyoTyrantException on failure.

### Examples

**Example \#1 <span class="methodname">tokyotyrant::putKeep</span>
example**

``` php
<?php
/* Connect to a database on default port */
$tt = new TokyoTyrant("localhost");

/* Create a new key */
$tt->put("key", "value");

try {
    $tt->putKeep("key", "new value");
} catch (TokyoTyrantException $e) {
    if ($e->getCode() === TokyoTyrant::TTE_KEEP) {
        echo "Existing record! Not modified\n";
    } else {
        echo "Error: " , $e->getMessage() , "\n"; 
    }
}
echo $tt->get("key");
?>
```

The above example will output:

    Existing record! Not modified
    value

### See Also

-   <span class="methodname">TokyoTyrant::put</span>
-   <span class="methodname">TokyoTyrant::putCat</span>

TokyoTyrant::putNr
==================

Puts value

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putNr</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span> `$value`<span
class="initializer"> = NULL</span></span> \] )

Puts a key-value pair into the database or multiple key-value pairs. If
`keys` is string then the second parameter value defines the value. The
second parameter is mandatory if `keys` is a string. This method does
not wait for the response from the server.

### Parameters

`keys`  
A string key or an array of key-value pairs

`value`  
The value in case a string key is used

### Return Values

This method returns a reference to the current object and throws
TokyoTyrantException on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::putNr</span>
example**

``` php
<?php
/* Connect to a database on default port */
$tt = new TokyoTyrant("localhost");

/* Put single key-value pair */
$tt->putNr("key", "value");

/* Put key-value pairs */
$tt->putNr(array("key1" => "value1", "key2" => "value2"));

/* Get back one key */
echo $tt->get("key1");
?>
```

The above example will output:

    value1

### See Also

-   <span class="methodname">TokyoTyrant::putNr</span>
-   <span class="methodname">TokyoTyrant::putKeep</span>
-   <span class="methodname">TokyoTyrant::putCat</span>

TokyoTyrant::putShl
===================

Concatenates to a record

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::putShl</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> )

Concatenate to a record and shift to left.

### Parameters

`key`  
A string key

`value`  
The value to concatenate

`width`  
The width of the record

### Return Values

This method returns a reference to the current object and throws
TokyoTyrantException on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::putShl</span>
example**

``` php
<?php
/* Connect to a database on default port */
$tt = new TokyoTyrant("localhost");

/* Create a new key */
$tt->put("key", "just a long piece of data");

/* Concatenate and shift to left */
$tt->putShl("key", " and string", 15);

/* Echo the key */
echo $tt->get("key");
?>
```

The above example will output:

    data and string

### See Also

-   <span class="methodname">TokyoTyrant::put</span>
-   <span class="methodname">TokyoTyrant::putKeep</span>
-   <span class="methodname">TokyoTyrant::putCat</span>

TokyoTyrant::restore
====================

Restore the database

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::restore</span> ( <span
class="methodparam"><span class="type">string</span> `$log_dir`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$check_consistency`<span class="initializer">
= **`TRUE`**</span></span> \] )

Restore the database from the update log.

**Warning**

This method is not supported on 32bit platforms.

### Parameters

`log_dir`  
Directory where the log is

`timestamp`  
Beginning timestamp with microseconds

`check_consistency`  
Whether to check consistency: Default: **`TRUE`**

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

TokyoTyrant::setMaster
======================

Set the replication master

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::setMaster</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$check_consistency`<span class="initializer">
= **`TRUE`**</span></span> \] )

Sets the replication master of the database

**Warning**

This method is not supported on 32bit platforms.

### Parameters

`host`  
Hostname of the replication master. If **`NULL`** the replication is
disabled.

`port`  
Port of the replication master

`timestamp`  
Beginning timestamp with microseconds

`check_consistency`  
Whether to check consistency.

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::setMaster</span>
example**

``` php
<?php
/* Connect to a database */
$tt = new TokyoTyrant("tokyotyrant.example.com");

/* Disable the replication */
$tt->setMaster(NULL, 0, 0);
?>
```

### See Also

-   <span class="methodname">Classname::Method</span>

TokyoTyrant::size
=================

Returns the size of the value

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrant::size</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

Returns the size of a value by key

### Parameters

`key`  
The key of which size to fetch

### Return Values

Returns the size of the key or throw TokyoTyrantException on error

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::size</span>
example**

``` php
<?php
$tt = new TokyoTyrant("localhost");

$tt->put("test_key", "12345");

echo $tt->size("test_key");
?>
```

The above example will output:

    5

TokyoTyrant::stat
=================

Get statistics

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrant::stat</span> ( <span
class="methodparam">void</span> )

Returns statistics of the remote database

### Parameters

This function has no parameters.

### Return Values

Returns an array of key value pairs describing the statistics

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::stat</span>
example**

``` php
<?php
$tt = new TokyoTyrant("localhost");

var_dump($tt->stat());
?>
```

The above example will output something similar to:

    array(19) {
      ["version"]=>
      string(6) "1.1.28"
      ["libver"]=>
      string(3) "311"
      ["protver"]=>
      string(4) "0.91"
      ["os"]=>
      string(5) "Linux"
      ["time"]=>
      string(17) "1247358357.665630"
      ["pid"]=>
      string(5) "14348"
      ["sid"]=>
      string(8) "59025947"
      ["type"]=>
      string(9) "on-memory"
      ["path"]=>
      string(1) "*"
      ["rnum"]=>
      string(1) "4"
      ["size"]=>
      string(6) "262856"
      ["bigend"]=>
      string(1) "0"
      ["fd"]=>
      string(1) "5"
      ["loadavg"]=>
      string(8) "0.000000"
      ["memsize"]=>
      string(8) "77328384"
      ["memrss"]=>
      string(7) "1183744"
      ["ru_real"]=>
      string(13) "162776.042152"
      ["ru_user"]=>
      string(8) "0.476029"
      ["ru_sys"]=>
      string(8) "8.652540"
    }

### See Also

-   <span class="methodname">Classname::Method</span>

TokyoTyrant::sync
=================

Synchronize the database

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::sync</span> ( <span
class="methodparam">void</span> )

Synchronizes the database on to the physical device

### Parameters

This function has no parameters.

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

TokyoTyrant::tune
=================

Tunes connection values

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::tune</span> ( <span
class="methodparam"><span class="type">float</span> `$timeout`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> =
TokyoTyrant::RDBT\_RECON</span></span> \] )

Tunes database connection options.

### Parameters

`timeout`  
The objects timeout value (default: 5.0)

`options`  
Bitmask of options to tune. This can be either 0 or
**`TokyoTyrant::RDBT_RECON`**. It is recommended not to change the
second parameter.

### Return Values

This method returns a reference to the current object and throws
TokyoTyrantException on failure.

TokyoTyrant::vanish
===================

Empties the database

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::vanish</span> ( <span
class="methodparam">void</span> )

Empties a remote database

### Parameters

This function has no parameters.

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrant::vanish</span>
example**

``` php
<?php
$tt = new TokyoTyrant("localhost");
$tt->vanish();
?>
```

### See Also

-   <span class="methodname">TokyoTyrant::out</span>

Introduction
------------

Provides an API to the table databases. A table database can be create
using the following command: *ttserver -port 1979 /tmp/tt\_table.tct*.
In Tokyo Tyrant the table API is a schemaless database which can store
arbitrary amount of key-value pairs under a single primary key.

Class synopsis
--------------

**TokyoTyrantTable**

<span class="ooclass"> class **TokyoTyrantTable** </span> <span
class="ooclass"> <span class="modifier">extends</span> **TokyoTyrant**
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$increment`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$type`</span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">genUid</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">get</span> ( <span class="methodparam"><span
class="type">mixed</span> `$keys`</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrantIterator</span> <span
class="methodname">getIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrantQuery</span> <span
class="methodname">getQuery</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">out</span> ( <span class="methodparam"><span
class="type">mixed</span> `$keys`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">put</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">array</span> `$columns`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">putCat</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">array</span> `$columns`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">putKeep</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">array</span>
`$columns`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">putNr</span> ( <span class="methodparam"><span
class="type">mixed</span> `$keys`</span> \[, <span
class="methodparam"><span class="type">string</span> `$value`</span> \]
)

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">putShl</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> ,
<span class="methodparam"><span class="type">int</span> `$width`</span>
)

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">setIndex</span> ( <span
class="methodparam"><span class="type">string</span> `$column`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">float</span></span> <span
class="methodname">TokyoTyrant::add</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">float</span></span>
`$increment`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = TokyoTyrant::RDBDEF\_PORT</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::connectUri</span> ( <span
class="methodparam"><span class="type">string</span> `$uri`</span> )

<span class="modifier">public</span> <span
class="methodname">TokyoTyrant::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = TokyoTyrant::RDBDEF\_PORT</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::copy</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">TokyoTyrant::ext</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span>
`$options`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrant::fwmKeys</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span> ,
<span class="methodparam"><span class="type">int</span>
`$max_recs`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::get</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrantIterator</span> <span
class="methodname">TokyoTyrant::getIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrant::num</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::out</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::put</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span> `$value`<span
class="initializer"> = NULL</span></span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putCat</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putKeep</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putNr</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span> `$value`<span
class="initializer"> = NULL</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::putShl</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::restore</span> ( <span
class="methodparam"><span class="type">string</span> `$log_dir`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$check_consistency`<span class="initializer">
= **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::setMaster</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$check_consistency`<span class="initializer">
= **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrant::size</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrant::stat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::sync</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::tune</span> ( <span
class="methodparam"><span class="type">float</span> `$timeout`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> =
TokyoTyrant::RDBT\_RECON</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::vanish</span> ( <span
class="methodparam">void</span> )

}

TokyoTyrantTable::add
=====================

Adds a record

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">TokyoTyrantTable::add</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$increment`</span> \[, <span class="methodparam"><span
class="type">string</span> `$type`</span> \] )

This method is not supported with table databases.

### Parameters

`key`  
The string key

`increment`  
The amount to increment

`type`  
**`TokyoTyrant::RDB_RECINT`** or **`TokyoTyrant::RDB_RECDBL`** constant.
If this parameter is omitted the type is guessed from the `increment`
parameters type.

### Return Values

This method throws an TokyoTyrantException if used through this class.

### See Also

-   <span class="methodname">TokyoTyrant::add</span>

TokyoTyrantTable::genUid
========================

Generate unique id

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrantTable::genUid</span> ( <span
class="methodparam">void</span> )

Generates an unique id inside the table database. In table databases
rows are referenced using a numeric primary key.

### Parameters

This function has no parameters.

### Return Values

Returns an unique id or throws TokyoTyrantException on error

### Examples

**Example \#1 <span class="methodname">TokyoTyrantTable::genUid</span>
example**

``` php
<?php
$tt = new TokyoTyrantTable("localhost", 1122);

echo $tt->genUid();
?>
```

The above example will output something similar to:

    4

### See Also

-   <span class="methodname">TokyoTyrantTable::put</span>

TokyoTyrantTable::get
=====================

Get a row

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrantTable::get</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

Gets a row from table database. `keys` is a single integer for the
primary key of the row or an array of integers for multiple rows.

### Parameters

`keys`  
The primary key, can be a string or an integer

### Return Values

Returns the row as an array

### Examples

**Example \#1 <span class="methodname">TokyoTyrantTable::get</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Passing null to put generates a new uid */
$index = $tt->put(null, array("column1" => "some data", "column2" => "more data"));

/* Get the row back */
var_dump($tt->get($index));
?>
```

The above example will output:

    array(2) {
      ["column1"]=>
      string(9) "some data"
      ["column2"]=>
      string(9) "more data"
    }

### Notes

> **Note**:
>
> Starting from version 0.3.0 this method accepts array as parameter.
> Please note that multi-get on tables is not binary-safe.

### See Also

-   <span class="methodname">TokyoTyrantTable::put</span>

TokyoTyrantTable::getIterator
=============================

Get an iterator

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrantIterator</span> <span
class="methodname">TokyoTyrantTable::getIterator</span> ( <span
class="methodparam">void</span> )

Gets an iterator for iterating all keys / values in the database.

### Parameters

This function has no parameters.

### Return Values

This method returns TokyoTyrantIterator object and throws
TokyoTyrantException on failure.

### Examples

**Example \#1 <span
class="methodname">TokyoTyrantTable::getIterator</span> example**

``` php
<?php
$tt = new TokyoTyrantTable("localhost");
$it = $tt->getIterator();

foreach ($it as $k => $v) {
  var_dump($k, $v);
}
?>
```

### See Also

-   <span class="methodname">TokyoTyrantTable::getQuery</span>
-   <span class="methodname">TokyoTyrant::getIterator</span>

TokyoTyrantTable::getQuery
==========================

Get a query object

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrantQuery</span> <span
class="methodname">TokyoTyrantTable::getQuery</span> ( <span
class="methodparam">void</span> )

Get a query object to execute searches on the database

### Parameters

This function has no parameters.

### Return Values

Returns TokyoTyrantQuery on success and throws TokyoTyrantException on
error

### Examples

**Example \#1 <span class="methodname">TokyoTyrantTable::getQuery</span>
example**

``` php
<?php
/* Connect to a table database */
$table = new TokyoTyrantTable("localhost", 1979);

/* Put a few rows */
$table->put(null, array("column1" => "some data", "column2" => "more data"));
$table->put(null, array("something" => "value", "data" => "good data"));

/* Get query object */
$query = $table->getQuery();

/* Add condition to query */
$query->addCond('data', TokyoTyrant::RDBQC_STREQ, 'good data');

/* Get matching rows */
var_dump($query->search());
?>
```

The above example will output something similar to:

    array(1) {
      [11]=>
      array(2) {
        ["something"]=>
        string(5) "value"
        ["data"]=>
        string(9) "good data"
      }
    }

### See Also

-   <span class="methodname">TokyoTyrantQuery::search</span>
-   <span class="methodname">TokyoTyrantQuery::out</span>

TokyoTyrantTable::out
=====================

Remove records

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">TokyoTyrantTable::out</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

Removes records from a table database.

### Parameters

`keys`  
A single integer key or an array of integers

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrantTable::out</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Passing null to put generates a new uid */
$index = $tt->put(null, array("column1" => "some data", "column2" => "more data"));

/* Delete the row */
$tt->out($index);
?>
```

### See Also

-   <span class="methodname">TokyoTyrantTable::put</span>

TokyoTyrantTable::put
=====================

Store a row

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrantTable::put</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">array</span>
`$columns`</span> )

Puts a new row into the database. This method parameters are `key` which
is the primary key of the row, passing **`NULL`** will generate a new
unique id. `value` is an array containing the row contents which is
usually key value pairs.

### Parameters

`key`  
The primary key of the row

`columns`  
The row contents

### Return Values

Returns the primary key on success and throws TokyoTyrantException on
error

### Examples

**Example \#1 <span class="methodname">TokyoTyrantTable::put</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Passing null to put generates a new uid */
$index = $tt->put(null, array("column1" => "some data", "column2" => "more data"));

/* Get the row back */
var_dump($tt->get($index));

/* Modify an existing row */
$tt->put($index, array("column1" => "other data", "column2" => "better data"));

/* Get the row back */
var_dump($tt->get($index));
?>
```

The above example will output:

    array(2) {
      ["column1"]=>
      string(9) "some data"
      ["column2"]=>
      string(9) "more data"
    }
    array(2) {
      ["column1"]=>
      string(10) "other data"
      ["column2"]=>
      string(11) "better data"
    }

### See Also

-   <span class="methodname">TokyoTyrantTable::get</span>

TokyoTyrantTable::putCat
========================

Concatenates to a row

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">TokyoTyrantTable::putCat</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">array</span>
`$columns`</span> )

This method can be used to add new columns to existing records. Existing
keys will be left unmodified but any new columns will be appended to the
row. Passing null as key will generate a new row.

### Parameters

`key`  
The primary key of the row or **`NULL`**

`columns`  
Array of row contents

### Return Values

Returns the primary key and throws TokyoTyrantException on error.

### Examples

**Example \#1 <span class="methodname">TokyoTyrantTable::putCat</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Passing null to put generates a new uid */
$index = $tt->put(null, array("column1" => "some data", "column2" => "more data"));

/* Get the row back */
var_dump($tt->get($index));

/* Modify an existing row */
$tt->putcat($index, array("column1" => "something new", "new_column" => "other data"));

/* Get the row back */
var_dump($tt->get($index));
?>
```

The above example will output:

    array(2) {
      ["column1"]=>
      string(9) "some data"
      ["column2"]=>
      string(9) "more data"
    }
    array(3) {
      ["column1"]=>
      string(9) "some data"
      ["column2"]=>
      string(9) "more data"
      ["new_column"]=>
      string(10) "other data"
    }

### See Also

-   <span class="methodname">TokyoTyrantTable::put</span>

TokyoTyrantTable::putKeep
=========================

Put a new record

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">TokyoTyrantTable::putKeep</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">array</span>
`$columns`</span> )

Puts a new record into the database. If the key already exists this
method throws an exception indicating that the records exists.

### Parameters

`key`  
The primary key of the row or **`NULL`**

`columns`  
Array of the row contents

### Return Values

Returns the primary key and throws TokyoTyrantException on error.

### Examples

**Example \#1 <span class="methodname">TokyoTyrantTable::putKeep</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Passing null to put generates a new uid */
$index = $tt->put(null, array("column1" => "some data", "column2" => "more data"));

/* Get the row back */
var_dump($tt->get($index));

try {
    $tt->putKeep($index, array("column1" => "something new", "new_column" => "other data"));
} catch (TokyoTyrantException $e) {
    if ($e->getCode() === TokyoTyrant::TTE_KEEP) {
        echo "Existing record! Not modified\n";
    } else {
        echo "Error: " , $e->getMessage() , "\n"; 
    }
}

/* Get the row back */
var_dump($tt->get($index));
?>
```

The above example will output something similar to:

    array(2) {
      ["column1"]=>
      string(9) "some data"
      ["column2"]=>
      string(9) "more data"
    }
    Existing record! Not modified
    array(2) {
      ["column1"]=>
      string(9) "some data"
      ["column2"]=>
      string(9) "more data"
    }

### See Also

-   <span class="methodname">TokyoTyrantTable::put</span>

TokyoTyrantTable::putNr
=======================

Puts value

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">TokyoTyrantTable::putNr</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

This method is not supported on table databases. Calling this method
through TokyoTyrantTable is considered an error and an
TokyoTyrantException will be thrown.

### Parameters

`keys`  
A string key or an array of key-value pairs

`value`  
The value in case a string key is used

### Return Values

This method is not supported on table databases. Calling this method
through TokyoTyrantTable is considered an error and an
TokyoTyrantException will be thrown.

### See Also

-   <span class="methodname">TokyoTyrant::putNr</span>
-   <span class="methodname">TokyoTyrant::putKeep</span>
-   <span class="methodname">TokyoTyrant::putCat</span>

TokyoTyrantTable::putShl
========================

Concatenates to a record

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">TokyoTyrantTable::putShl</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> )

This method is not supported on table databases. Calling this method
through TokyoTyrantTable is considered an error and an
TokyoTyrantException will be thrown.

### Parameters

`key`  
A string key

`value`  
The value to concatenate

`width`  
The width of the record

### Return Values

This method is not supported on table databases.

### See Also

-   <span class="methodname">TokyoTyrant::put</span>
-   <span class="methodname">TokyoTyrant::putKeep</span>
-   <span class="methodname">TokyoTyrant::putCat</span>
-   <span class="methodname">TokyoTyrantTable::put</span>
-   <span class="methodname">TokyoTyrantTable::putKeep</span>
-   <span class="methodname">TokyoTyrantTable::putCat</span>

TokyoTyrantTable::setIndex
==========================

Sets index

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrantTable::setIndex</span> ( <span
class="methodparam"><span class="type">string</span> `$column`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> )

Sets an index on a specified column. The index type is one of the
**`TokyoTyrant::RDBIT_*`** constants. Passing
**`TokyoTyrant::RDBIT_VOID`** removes the index.

### Parameters

`column`  
The name of the column

`type`  
The index type

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

Introduction
------------

This class is used to query the table databases

Class synopsis
--------------

**TokyoTyrantQuery**

<span class="ooclass"> class **TokyoTyrantQuery** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">addCond</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$op`</span> ,
<span class="methodparam"><span class="type">string</span>
`$expr`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">TokyoTyrantTable</span>
`$table`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">hint</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">metaSearch</span> ( <span
class="methodparam"><span class="type">array</span> `$queries`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrantQuery</span> <span class="methodname">out</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">search</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">setLimit</span> (\[ <span
class="methodparam"><span class="type">int</span> `$max`</span> \[,
<span class="methodparam"><span class="type">int</span> `$skip`</span>
\]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">setOrder</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

TokyoTyrantQuery::addCond
=========================

Adds a condition to the query

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrantQuery::addCond</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$op`</span> ,
<span class="methodparam"><span class="type">string</span>
`$expr`</span> )

Adds a condition to the query. Condition can be something like: get all
keys which value matches expr.

### Parameters

`name`  
Name of the column in the condition

`op`  
The operator. One of the **`TokyoTyrant::RDBQC_*`** constants

`expr`  
The expression

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrantQuery::addCond</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "not here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Dump the search results */
var_dump($query->search());
?>
```

The above example will output:

    array(2) {
      [1]=>
      array(2) {
        ["column1"]=>
        string(9) "some data"
        ["column2"]=>
        string(14) "something here"
      }
      [4]=>
      array(2) {
        ["column45"]=>
        string(11) "random data"
        ["column2"]=>
        string(25) "something along the lines"
      }
    }

### See Also

-   <span class="methodname">Classname::Method</span>

TokyoTyrantQuery::\_\_construct
===============================

Construct a new query

### Description

<span class="modifier">public</span> <span
class="methodname">TokyoTyrantQuery::\_\_construct</span> ( <span
class="methodparam"><span class="type">TokyoTyrantTable</span>
`$table`</span> )

Construct a new query object

### Parameters

`table`  
TokyoTyrantTable object with active database connection

### Return Values

Returns a new TokyoTyrantQuery object and throws TokyoTyrantException on
error

### Examples

**Example \#1 <span
class="methodname">TokyoTyrantQuery::\_\_construct</span> example**

``` php
<?php
$tt = new TokyoTyrantTable("localhost", 1979);

$query = new TokyoTyrantQuery($tt);

/* Work with $query */
?>
```

### See Also

-   <span class="methodname">TokyoTyrantTable::getQuery</span>

TokyoTyrantQuery::count
=======================

Counts records

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrantQuery::count</span> ( <span
class="methodparam">void</span> )

Returns a count of how many records a query returns.

### Parameters

This function has no parameters.

### Return Values

Returns a count of matching rows and throws TokyoTyrantException on
error

### Examples

**Example \#1 <span class="methodname">TokyoTyrantQuery::count</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "not here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Count the results */
var_dump($query->count());
?>
```

The above example will output:

    int(2)

### See Also

-   <span class="methodname">TokyoTyrantQuery::out</span>
-   <span class="methodname">TokyoTyrantQuery::search</span>
-   <span class="methodname">TokyoTyrantQuery::metaSearch</span>

TokyoTyrantQuery::current
=========================

Returns the current element

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrantQuery::current</span> ( <span
class="methodparam">void</span> )

Returns the current element. Part of Iterator interface

### Parameters

This function has no parameters.

### Return Values

Returns the current row

### Examples

**Example \#1 TokyoTyrantQuery iterator example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "foobar here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Iterate the results */
foreach ($query as $key => $value) {
    echo "pk: $key, columns: ", count($value) ,"\n";
}
?>
```

The above example will output something similar to:

    pk: 1, columns: 2
    pk: 4, columns: 2

### See Also

-   <span class="methodname">TokyoTyrantQuery::addCond</span>

TokyoTyrantQuery::hint
======================

Get the hint string of the query

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">TokyoTyrantQuery::hint</span> ( <span
class="methodparam">void</span> )

Get the hint string of the query. The hint string contains information
about an executed query and it could be compared to for example MySQL
EXPLAIN statement.

### Parameters

This function has no parameters.

### Return Values

This method always returns a string

### Examples

**Example \#1 TokyoTyrantQuery::hint example**

``` php
<?php
$tt = new TokyoTyrantTable("localhost", 1979);
$tt->vanish();

for ($i = 0; $i < 11; $i++) {
     $tt->put(null, array('a_col' => 'a' . $i, 'b_col' => 'b' . $i));
}

$query = $tt->getQuery();
$query->addCond('a_col', TokyoTyrant::RDBQC_STRBW, 'a');

$query->search();
var_dump($query->hint());
?>
```

The above example will output something similar to:

    string(72) "
    scanning the whole table
    result set size: 11
    leaving the natural order
    "

### See Also

-   <span class="methodname">TokyoTyrantQuery::addCond</span>

TokyoTyrantQuery::key
=====================

Returns the current key

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">TokyoTyrantQuery::key</span> ( <span
class="methodparam">void</span> )

Returns the current key. Part of the Iterator interface

### Parameters

This function has no parameters.

### Return Values

Returns the current key and throws TokyoTyrantException on error

### Examples

**Example \#1 TokyoTyrantQuery iterator example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "foobar here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Iterate the results */
foreach ($query as $key => $value) {
    echo "pk: $key, columns: ", count($value) ,"\n";
}
?>
```

The above example will output something similar to:

    pk: 1, columns: 2
    pk: 4, columns: 2

### See Also

-   <span class="methodname">TokyoTyrantQuery::addCond</span>

TokyoTyrantQuery::metaSearch
============================

Retrieve records with multiple queries

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrantQuery::metaSearch</span> ( <span
class="methodparam"><span class="type">array</span> `$queries`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> )

Executes multiple queries on a database and returns matching records.
The current object is always the left most object in the search.

### Parameters

`queries`  
Array of TokyoTyrantQuery objects

`type`  
One of the **`TokyoTyrant::RDBMS_*`** constants

### Return Values

Returns the matching rows and throws TokyoTyrantException on error

### Examples

**Example \#1 <span
class="methodname">TokyoTyrantQuery::metaSearch</span> example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add test data */
$tt->put('cherry',     array('color' => 'red'));
$tt->put('strawberry', array('color' => 'red'));
$tt->put('apple',      array('color' => 'green'));
$tt->put('lemon',      array('color' => 'yellow'));

/* First query */
$query = $tt->getQuery();
$query->addCond('color', TokyoTyrant::RDBQC_STREQ, 'red')->setOrder('color', TokyoTyrant::RDBQO_STRASC);

/* Second query */
$query1 = $tt->getQuery();
$query1->addCond('color', TokyoTyrant::RDBQC_STREQ, 'yellow');

/* Get union between the queries */
var_dump($query->metaSearch(array($query1), TokyoTyrant::RDBMS_UNION));
?>
```

The above example will output:

    array(3) {
      ["cherry"]=>
      array(1) {
        ["color"]=>
        string(3) "red"
      }
      ["strawberry"]=>
      array(1) {
        ["color"]=>
        string(3) "red"
      }
      ["lemon"]=>
      array(1) {
        ["color"]=>
        string(6) "yellow"
      }
    }

### See Also

-   <span class="methodname">TokyoTyrantQuery::search</span>

TokyoTyrantQuery::next
======================

Moves the iterator to next entry

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrantQuery::next</span> ( <span
class="methodparam">void</span> )

Returns the next result in the resultset. Part of the Iterator
interface.

### Parameters

This function has no parameters.

### Return Values

Returns the next row and throws TokyoTyrantException on error.

### Examples

**Example \#1 TokyoTyrantQuery iterator example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "foobar here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Iterate the results */
foreach ($query as $key => $value) {
    echo "pk: $key, columns: ", count($value) ,"\n";
}
?>
```

The above example will output something similar to:

    pk: 1, columns: 2
    pk: 4, columns: 2

### See Also

-   <span class="methodname">TokyoTyrantQuery::addCond</span>

TokyoTyrantQuery::out
=====================

Removes records based on query

### Description

<span class="modifier">public</span> <span
class="type">TokyoTyrantQuery</span> <span
class="methodname">TokyoTyrantQuery::out</span> ( <span
class="methodparam">void</span> )

Removes all records that match the query. Works exactly like search but
removes the records instead of returning them.

### Parameters

This function has no parameters.

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

### Examples

**Example \#1 <span class="methodname">TokyoTyrantQuery::out</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "foobar here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Remove matching records */
$query->out();
?>
```

### See Also

-   <span class="methodname">TokyoTyrantQuery::addCond</span>

TokyoTyrantQuery::rewind
========================

Rewinds the iterator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">TokyoTyrantQuery::rewind</span> ( <span
class="methodparam">void</span> )

Rewind the resultset and executes the query if it has not been executed.
Part of the Iterator interface.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`**

### Examples

**Example \#1 TokyoTyrantQuery iterator example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "foobar here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Iterate the results */
foreach ($query as $key => $value) {
    echo "pk: $key, columns: ", count($value) ,"\n";
}
?>
```

The above example will output something similar to:

    pk: 1, columns: 2
    pk: 4, columns: 2

### See Also

-   <span class="methodname">TokyoTyrantQuery::addCond</span>

TokyoTyrantQuery::search
========================

Searches records

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrantQuery::search</span> ( <span
class="methodparam">void</span> )

Executes a search on the table database. Returns an array of arrays
containing the matching records. In the returned array the first level
is the primary key of the data and the second level is the row data.

### Parameters

This function has no parameters.

### Return Values

Returns the matching rows and throws TokyoTyrantException on error

### Examples

**Example \#1 <span class="methodname">TokyoTyrantQuery::search</span>
example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "not here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Dump the search results */
var_dump($query->search());
?>
```

The above example will output:

    array(2) {
      [1]=>
      array(2) {
        ["column1"]=>
        string(9) "some data"
        ["column2"]=>
        string(14) "something here"
      }
      [4]=>
      array(2) {
        ["column45"]=>
        string(11) "random data"
        ["column2"]=>
        string(25) "something along the lines"
      }
    }

### See Also

-   <span class="methodname">TokyoTyrantQuery::out</span>
-   <span class="methodname">TokyoTyrantQuery::metaSearch</span>

TokyoTyrantQuery::setLimit
==========================

Limit results

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrantQuery::setLimit</span> (\[ <span
class="methodparam"><span class="type">int</span> `$max`</span> \[,
<span class="methodparam"><span class="type">int</span> `$skip`</span>
\]\] )

Set the maximum amount of records to return on a query.

### Parameters

`max`  
Maximum amount of records. Default: -1

`skip`  
How many records to skip from the start. Default: -1

### Return Values

This method returns the current object and throws TokyoTyrantException
on failure.

TokyoTyrantQuery::setOrder
==========================

Orders results

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrantQuery::setOrder</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> )

Sets the order of a query

### Parameters

`name`  
The column name to apply the ordering on.

`type`  
The `type` can be one of the following constants:

-   <span class="simpara"> **`TokyoTyrant::RDBQO_STRASC`** - String
    ascending </span>
-   <span class="simpara"> **`TokyoTyrant::RDBQO_STRDESC`** - String
    descending </span>
-   <span class="simpara"> **`TokyoTyrant::RDBQO_NUMASC`** - Numberic
    ascending </span>
-   <span class="simpara"> **`TokyoTyrant::RDBQO_NUMDESC`** - String
    descending </span>

### Return Values

This method returns the current object.

TokyoTyrantQuery::valid
=======================

Checks the validity of current item

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">TokyoTyrantQuery::valid</span> ( <span
class="methodparam">void</span> )

Checks if the current item is valid. Part of the Iterator interface

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the current item is valid and **`FALSE`** if not.

### Examples

**Example \#1 TokyoTyrantQuery iterator example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Add rows */
$tt->put(null, array("column1" => "some data", "column2" => "something here"));
$tt->put(null, array("column1" => "more data", "column2" => "best data this far"));
$tt->put(null, array("column1" => "again data", "column3" => "foobar here"));
$tt->put(null, array("column45" => "random data", "column2" => "something along the lines"));
$tt->put(null, array("column21" => "test data", "column2" => "generating.."));
$tt->put(null, array("column1" => "foobar data", "column2" => "value here"));

/* Get a new query object */
$query = $tt->getQuery();

/* Add a search condition */
$query->addCond("column2", TokyoTyrant::RDBQC_STROR, "something");

/* Iterate the results */
foreach ($query as $key => $value) {
    echo "pk: $key, columns: ", count($value) ,"\n";
}
?>
```

The above example will output something similar to:

    pk: 1, columns: 2
    pk: 4, columns: 2

### See Also

-   <span class="methodname">TokyoTyrantQuery::addCond</span>

Introduction
------------

Provides an iterator for TokyoTyrant and TokyoTyrantTable objects. The
iterator iterates over all keys and values in the database.
TokyoTyrantIterator was added in version 0.2.0.

Class synopsis
--------------

**TokyoTyrantIterator**

<span class="ooclass"> class **TokyoTyrantIterator** </span> <span
class="oointerface">implements <span
class="interfacename">Iterator</span> </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">float</span></span> <span
class="methodname">TokyoTyrant::add</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">float</span></span>
`$increment`</span> \[, <span class="methodparam"><span
class="type">int</span> `$type`<span class="initializer"> =
0</span></span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = TokyoTyrant::RDBDEF\_PORT</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::connectUri</span> ( <span
class="methodparam"><span class="type">string</span> `$uri`</span> )

<span class="modifier">public</span> <span
class="methodname">TokyoTyrant::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = TokyoTyrant::RDBDEF\_PORT</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::copy</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">TokyoTyrant::ext</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">int</span>
`$options`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrant::fwmKeys</span> ( <span
class="methodparam"><span class="type">string</span> `$prefix`</span> ,
<span class="methodparam"><span class="type">int</span>
`$max_recs`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::get</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrantIterator</span> <span
class="methodname">TokyoTyrant::getIterator</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrant::num</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::out</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::put</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span> `$value`<span
class="initializer"> = NULL</span></span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putCat</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putKeep</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \] )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::putNr</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">string</span> `$value`<span
class="initializer"> = NULL</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::putShl</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::restore</span> ( <span
class="methodparam"><span class="type">string</span> `$log_dir`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$check_consistency`<span class="initializer">
= **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::setMaster</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span> ,
<span class="methodparam"><span class="type">int</span>
`$timestamp`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$check_consistency`<span class="initializer">
= **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">TokyoTyrant::size</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">TokyoTyrant::stat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::sync</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">TokyoTyrant</span> <span
class="methodname">TokyoTyrant::tune</span> ( <span
class="methodparam"><span class="type">float</span> `$timeout`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> =
TokyoTyrant::RDBT\_RECON</span></span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrant::vanish</span> ( <span
class="methodparam">void</span> )

}

TokyoTyrantIterator::\_\_construct
==================================

Construct an iterator

### Description

<span class="modifier">public</span> <span
class="methodname">TokyoTyrantIterator::\_\_construct</span> ( <span
class="methodparam"><span class="type">mixed</span> `$object`</span> )

Construct a new TokyoTyrantIterator object. One connection can have
multiple iterators but it is not quaranteed that all items are traversed
in that case. `object` parameter can be either an of instance
TokyoTyrant or TokyoTyrantTable.

### Parameters

This function has no parameters.

### Return Values

Throws an exception if iterator initialization fails.

### Examples

**Example \#1 <span
class="methodname">TokyoTyrantIterator::\_\_construct</span> example**

``` php
<?php
/* Connect to a table database */
$tt = new TokyoTyrantTable("localhost", 1979);

/* Passing null to put generates a new uid */
$index = $tt->put(null, array("column1" => "some data", "column2" => "more data"));

/* Construct an iterator */
$it = new TokyoTyrantIterator($tt);

foreach ($it as $value) {
    var_dump($value);
}
?>
```

The above example will output:

    array(2) {
      ["column1"]=>
      string(9) "some data"
      ["column2"]=>
      string(9) "more data"
    }

### See Also

-   <span class="methodname">TokyoTyrantIterator::key</span>
-   <span class="methodname">TokyoTyrantIterator::current</span>
-   <span class="methodname">TokyoTyrantIterator::next</span>
-   <span class="methodname">TokyoTyrantIterator::rewind</span>
-   <span class="methodname">TokyoTyrantIterator::key</span>

TokyoTyrantIterator::current
============================

Get the current value

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrantIterator::current</span> ( <span
class="methodparam">void</span> )

Returns the current value during iteration.

### Parameters

This function has no parameters.

### Return Values

Returns the current value on success and false on failure.

### See Also

-   <span class="methodname">TokyoTyrantIterator::valid</span>
-   <span class="methodname">TokyoTyrantIterator::key</span>
-   <span class="methodname">TokyoTyrantIterator::next</span>
-   <span class="methodname">TokyoTyrantIterator::rewind</span>

TokyoTyrantIterator::key
========================

Returns the current key

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrantIterator::key</span> ( <span
class="methodparam">void</span> )

Returns the current key.

### Parameters

This function has no parameters.

### Return Values

Returns the current key on success and false on failure.

### See Also

-   <span class="methodname">TokyoTyrantIterator::valid</span>
-   <span class="methodname">TokyoTyrantIterator::current</span>
-   <span class="methodname">TokyoTyrantIterator::next</span>
-   <span class="methodname">TokyoTyrantIterator::rewind</span>

TokyoTyrantIterator::next
=========================

Move to next key

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">TokyoTyrantIterator::next</span> ( <span
class="methodparam">void</span> )

Move to next key during iteration and return it's value.

### Parameters

This function has no parameters.

### Return Values

Returns the next value on success and false on failure.

### See Also

-   <span class="methodname">TokyoTyrantIterator::valid</span>
-   <span class="methodname">TokyoTyrantIterator::key</span>
-   <span class="methodname">TokyoTyrantIterator::current</span>
-   <span class="methodname">TokyoTyrantIterator::rewind</span>

TokyoTyrantIterator::rewind
===========================

Rewinds the iterator

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">TokyoTyrantIterator::rewind</span> ( <span
class="methodparam">void</span> )

Rewinds the iterator for new iteration. Called automatically at the
beginning of foreach.

### Parameters

This function has no parameters.

### Return Values

Throws TokyoTyrantException if iterator initialization fails.

### See Also

-   <span class="methodname">TokyoTyrantIterator::valid</span>
-   <span class="methodname">TokyoTyrantIterator::current</span>
-   <span class="methodname">TokyoTyrantIterator::next</span>
-   <span class="methodname">TokyoTyrantIterator::rewind</span>

TokyoTyrantIterator::valid
==========================

Rewinds the iterator

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">TokyoTyrantIterator::valid</span> ( <span
class="methodparam">void</span> )

Checks whether the internal pointer points to valid element.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if the current item is valid and **`FALSE`** if not.

### See Also

-   <span class="methodname">TokyoTyrantIterator::key</span>
-   <span class="methodname">TokyoTyrantIterator::current</span>
-   <span class="methodname">TokyoTyrantIterator::next</span>
-   <span class="methodname">TokyoTyrantIterator::rewind</span>

Introduction
------------

TokyoTyrantException

Class synopsis
--------------

**tokyotyrantexception**

<span class="ooclass"> class **tokyotyrantexception** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`code`  
The exception code. This can be compared to **`TokyoTyrant::TTE_*`**
constants

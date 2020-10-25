MongoDB driver (legacy)
=======================

**Table of Contents**

-   [Installing/Configuring](/book/mongo.html#Installing/Configuring)
    -   [Requirements](/book/mongo.html#Requirements)
    -   [Installation](/book/mongo.html#Installation)
    -   [Runtime
        Configuration](/book/mongo.html#Runtime%20Configuration)
-   [Predefined Constants](/book/mongo.html#Predefined%20Constants)
-   [Manual](/book/mongo.html#Manual)
    -   [Tutorial](/book/mongo.html#Tutorial)
    -   [Read Preferences](/book/mongo.html#Read%20Preferences)
    -   [Write Concerns](/book/mongo.html#Write%20Concerns)
    -   [SQL to Mongo Mapping
        Chart](/book/mongo.html#SQL%20to%20Mongo%20Mapping%20Chart)
    -   [Connecting](/book/mongo.html#Connecting)
    -   [Stream Context
        Options](/book/mongo.html#Stream%20Context%20Options)
    -   [Writes](/book/mongo.html#Writes)
    -   [Querying](/book/mongo.html#Querying)
    -   [Updates](/book/mongo.html#Updates)
    -   [Security](/book/mongo.html#Security)
    -   [Troubleshooting](/book/mongo.html#Troubleshooting)
    -   [Running the Driver's
        Tests](/book/mongo.html#Running%20the%20Driver's%20Tests)
-   [Core Classes](/book/mongo.html#Core%20Classes)
    -   [MongoClient](/book/mongo.html#MongoClient) — The MongoClient
        class
    -   [MongoDB](/book/mongo.html#MongoDB) — The MongoDB class
    -   [MongoCollection](/book/mongo.html#MongoCollection) — The
        MongoCollection class
    -   [MongoCursor](/book/mongo.html#MongoCursor) — The MongoCursor
        class
    -   [MongoCursorInterface](/book/mongo.html#MongoCursorInterface) —
        The MongoCursorInterface interface
    -   [MongoCommandCursor](/book/mongo.html#MongoCommandCursor) — The
        MongoCommandCursor class
-   [Types](/book/mongo.html#Types)
    -   [MongoId](/book/mongo.html#MongoId) — The MongoId class
    -   [MongoCode](/book/mongo.html#MongoCode) — The MongoCode class
    -   [MongoDate](/book/mongo.html#MongoDate) — The MongoDate class
    -   [MongoRegex](/book/mongo.html#MongoRegex) — The MongoRegex class
    -   [MongoBinData](/book/mongo.html#MongoBinData) — The MongoBinData
        class
    -   [MongoInt32](/book/mongo.html#MongoInt32) — The MongoInt32 class
    -   [MongoInt64](/book/mongo.html#MongoInt64) — The MongoInt64 class
    -   [MongoDBRef](/book/mongo.html#MongoDBRef) — The MongoDBRef class
    -   [MongoMinKey](/book/mongo.html#MongoMinKey) — The MongoMinKey
        class
    -   [MongoMaxKey](/book/mongo.html#MongoMaxKey) — The MongoMaxKey
        class
    -   [MongoTimestamp](/book/mongo.html#MongoTimestamp) — The
        MongoTimestamp class
-   [GridFS Classes](/book/mongo.html#GridFS%20Classes)
    -   [MongoGridFS](/book/mongo.html#MongoGridFS) — The MongoGridFS
        class
    -   [MongoGridFSFile](/book/mongo.html#MongoGridFSFile) — The
        MongoGridFSFile class
    -   [MongoGridFSCursor](/book/mongo.html#MongoGridFSCursor) — The
        MongoGridFSCursor class
-   [Batch Classes](/book/mongo.html#Batch%20Classes)
    -   [MongoWriteBatch](/book/mongo.html#MongoWriteBatch) — The
        MongoWriteBatch class
    -   [MongoInsertBatch](/book/mongo.html#MongoInsertBatch) — The
        MongoInsertBatch class
    -   [MongoUpdateBatch](/book/mongo.html#MongoUpdateBatch) — The
        MongoUpdateBatch class
    -   [MongoDeleteBatch](/book/mongo.html#MongoDeleteBatch) — The
        MongoDeleteBatch class
-   [Miscellaneous](/book/mongo.html#Miscellaneous)
    -   [MongoLog](/book/mongo.html#MongoLog) — The MongoLog class
    -   [MongoPool](/book/mongo.html#MongoPool) — The MongoPool class
    -   [Mongo](/book/mongo.html#Mongo) — The Mongo class \[deprecated\]
-   [Mongo Functions](/book/mongo.html#Mongo%20Functions)
    -   [bson\_decode](/book/mongo.html#bson_decode) — Deserializes a
        BSON object into a PHP array
    -   [bson\_encode](/book/mongo.html#bson_encode) — Serializes a PHP
        variable into a BSON string
-   [Exceptions](/book/mongo.html#Exceptions)
    -   [MongoException](/book/mongo.html#MongoException) — The
        MongoException class
    -   [MongoResultException](/book/mongo.html#MongoResultException) —
        The MongoResultException class
    -   [MongoCursorException](/book/mongo.html#MongoCursorException) —
        The MongoCursorException class
    -   [MongoCursorTimeoutException](/book/mongo.html#MongoCursorTimeoutException)
        — The MongoCursorTimeoutException class
    -   [MongoConnectionException](/book/mongo.html#MongoConnectionException)
        — The MongoConnectionException class
    -   [MongoGridFSException](/book/mongo.html#MongoGridFSException) —
        The MongoGridFSException class
    -   [MongoDuplicateKeyException](/book/mongo.html#MongoDuplicateKeyException)
        — The MongoDuplicateKeyException class
    -   [MongoProtocolException](/book/mongo.html#MongoProtocolException)
        — The MongoProtocolException class
    -   [MongoExecutionTimeoutException](/book/mongo.html#MongoExecutionTimeoutException)
        — The MongoExecutionTimeoutException class
    -   [MongoWriteConcernException](/book/mongo.html#MongoWriteConcernException)
        — The MongoWriteConcernException class
-   [Changelog](/book/mongo.html#Changelog)

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/mongo.html#Requirements)
-   [Installation](/book/mongo.html#Installation)
-   [Runtime Configuration](/book/mongo.html#Runtime%20Configuration)

**Warning**

This extension is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used.

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

**Warning**

This extension is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used.

The MongoDB PHP driver should work on nearly any system: Windows, macOS,
Unix, and Linux; little- and big-endian machines; 32- and 64-bit
machines; PHP 5.3 through 5.6 (versions prior to 1.6 also support PHP
5.2).

This <a href="https://pecl.php.net/" class="link external">» PECL</a>
extension is not bundled with PHP.

-   <a href="/book/mongo.html#Manual%20Installation" class="xref"></a>
-   <a href="/book/mongo.html#Installing%20on%20*NIX" class="xref"></a>
-   <a href="/book/mongo.html#Installing%20on%20Windows" class="xref"></a>
-   <a href="/book/mongo.html#macOS" class="xref"></a>
-   <a href="/book/mongo.html#Gentoo" class="xref"></a>
-   <a href="/book/mongo.html#Red%20Hat" class="xref"></a>
-   <a href="/book/mongo.html#Third-Party%20Installation%20Instructions" class="xref"></a>

Manual Installation
-------------------

For driver developers and people interested in the latest bugfixes, you
can compile the driver from the latest source code on
<a href="https://github.com/mongodb/mongo-php-driver-legacy" class="link external">» Github</a>.
Go to Github and click the "download" button. Then run:

``` shell
$ tar zxvf mongo-php-driver-legacy-<commit_id>.tar.gz
$ cd mongo-php-driver-legacy-<commit_id>
$ phpize
$ ./configure
$ make all
$ sudo make install
```

Make the following changes to `php.ini`:

-   Make sure the *extension\_dir* variable is pointing to the directory
    containing *mongo.so*. The build will display where it is installing
    the PHP driver with output that looks something like:

    ``` txt
    Installing '/usr/lib/php/extensions/no-debug-non-zts-20060613/mongo.so'
    ```

    Make sure that it is the same as the PHP extension directory by
    running:

    ``` shell
    $ php -i | grep extension_dir
      extension_dir => /usr/lib/php/extensions/no-debug-non-zts-20060613 =>
                       /usr/lib/php/extensions/no-debug-non-zts-20060613
    ```

    If it's not, change the *extension\_dir* in `php.ini` or move
    *mongo.so*.

-   To load the extension on PHP startup, add a line:

    ``` ini
    extension=mongo.so
    ```

Installing on \*NIX
-------------------

Run:

``` shell
$ sudo pecl install mongo
```

Add the following line to your `php.ini` file:

``` ini
extension=mongo.so
```

If pecl runs out of memory while installing, make sure memory\_limit in
`php.ini` is set to at least 128MB.

Installing on Windows
---------------------

Precompiled binaries for each release are available from
<a href="https://pecl.php.net/package/mongo" class="link external">» PECL</a>
for a variety of combinations of versions, thread safety, and VC
libraries. Unzip the archive and put php\_mongo.dll in your PHP
extension directory ("ext" by default).

Add the following line to your `php.ini` file:

``` ini
extension=php_mongo.dll
```

> **Note**: **Additional DLL dependencies for Windows Users**  
>
> In order for this extension to work, there are DLL files that must be
> available to the Windows system `PATH`. For information on how to do
> this, see the FAQ entitled
> "<a href="/faq/installation.html#faq.installation.addtopath" class="link">How do I add my PHP directory to the PATH on Windows</a>".
> Although copying DLL files from the PHP folder into the Windows system
> directory also works (because the system directory is by default in
> the system's `PATH`), this is not recommended. *This extension
> requires the following files to be in the `PATH`:* `libsasl.dll`

macOS
-----

In most cases installing from PECL is the easiest way:

``` shell
$ sudo pecl install mongo
```

If your system has multiple version of PHP installed (e.g. macOS
default, Homebrew,
<a href="https://www.apachefriends.org/" class="link external">» XAMPP</a>),
note that that each version of PHP has its own
<a href="/install/pecl.html" class="link">pecl</a> command and `php.ini`
file.

> **Note**: **Xcode dependency for compiling on macOS**  
>
> Compiling the driver on macOS will require Xcode developer tools,
> which may be installed with `xcode-select --install`. If that command
> is not available, you may first need to install the
> <a href="https://developer.apple.com/downloads/index.action?name=Command%20Line%20Tools" class="link external">» Command Line Tools</a>
> package.

Gentoo
------

Gentoo has a package for the PHP PECL driver called dev-php/pecl-mongo,
which can be installed with:

``` shell
$ sudo emerge -va dev-php/pecl-mongo
```

If you use PECL, you may get an error that libtool is the wrong version.
Compiling from source you'll need to run aclocal and autoconf.

``` shell
$ phpize
$ aclocal 
$ autoconf 
$ ./configure
$ make
$ sudo make install
```

Red Hat
-------

This includes Fedora and CentOS.

The default Apache settings on these systems do not let requests make
network connections, meaning that the driver will get "Permission
denied" errors when it tries to connect to the database. If you run into
this, try running:

``` shell
$ /usr/sbin/setsebool -P httpd_can_network_connect 1
```

Then restart Apache. (This issue has also occurred with SELinux.)

Third-Party Installation Instructions
-------------------------------------

A number of people have created excellent tutorials on installing the
PHP driver.

-   <a href="http://justinhileman.info/article/reinstalling-php-on-mac-os-x/" class="link external">»  (Re)installing PHP on macOS</a>

    This article by Justin Hileman details the process of installing PHP
    and additional extensions with Homebrew on macOS. This complements
    the earlier instructions on this page for installing the driver with
    Homebrew.

-   <a href="https://www.vimeo.com/8005503" class="link external">»  PHP 5.3.1 with Xdebug, MongoDB and Lithium on Ubuntu 9.10 / Apache 2.2</a>

    This screencast by Jon Adams demonstrates how to quickly get up and
    running with PHP 5.3.1, Xdebug, and MongoDB on Ubuntu 9.10 with
    Apache.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                  | Default     | Changeable    | Changelog                                               |
|-----------------------------------------------------------------------|-------------|---------------|---------------------------------------------------------|
| <a href="/book/mongo.html#" class="link">mongo.allow_empty_keys</a>   | 0           | PHP\_INI\_ALL |                                                         |
| <a href="/book/mongo.html#" class="link">mongo.allow_persistent</a>   | 1           | PHP\_INI\_ALL | Removed in 1.2.0                                        |
| <a href="/book/mongo.html#" class="link">mongo.chunk_size</a>         | 262144      | PHP\_INI\_ALL |                                                         |
| <a href="/book/mongo.html#" class="link">mongo.cmd</a>                | "$"         | PHP\_INI\_ALL |                                                         |
| <a href="/book/mongo.html#" class="link">mongo.default_host</a>       | "localhost" | PHP\_INI\_ALL |                                                         |
| <a href="/book/mongo.html#" class="link">mongo.default_port</a>       | 27017       | PHP\_INI\_ALL |                                                         |
| <a href="/book/mongo.html#" class="link">mongo.is_master_interval</a> | 15          | PHP\_INI\_ALL | Added in 1.2.10, before 1.3.0 the default value was 60. |
| <a href="/book/mongo.html#" class="link">mongo.long_as_object</a>     | 0           | PHP\_INI\_ALL |                                                         |
| <a href="/book/mongo.html#" class="link">mongo.native_long</a>        | 1           | PHP\_INI\_ALL | Before 1.5.0, the default value was 0.                  |
| <a href="/book/mongo.html#" class="link">mongo.ping_interval</a>      | 5           | PHP\_INI\_ALL | Added in 1.2.10                                         |
| <a href="/book/mongo.html#" class="link">mongo.utf8</a>               | 1           | PHP\_INI\_ALL |                                                         |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`mongo.allow_empty_keys` <span class="type">int</span>  
Added in version 1.0.11.

If empty strings ("") should be allowed as key names. By default, the
driver will throw an exception if you attempt to pass the empty string
as a key to the database. It is extremely easy to do this inavertently
by using double quotes with $-operators, so it is recommended that you
leave this setting as default. However, if you need to save keys that
are empty strings, you can set this option to true and the driver will
allow you to pass empty strings to the database.

`mongo.allow_persistent` <span class="type">int</span>  
If persistent connections are allowed. (Removed in 1.2.0 - all
connections are now persistent).

`mongo.chunk_size` <span class="type">int</span>  
The number of bytes-per-chunk. Used in divvying up GridFS files. This
number must be at least 100 less than 4 megabytes (max: 4194204) and it
is recommended that it be less than that.

`mongo.cmd` <span class="type">string</span>  
A character to be used in place of $ in modifiers and comparisons.

As it is easy to forget to escape the "$", you can also choose your own
special character to use instead of '$'. Choose a character that will
not occur in your key names, e.g. ":":

``` ini
mongo.cmd = ":"
```

Then, to do a comparison, for example:

``` php
<?php

$query = array( "i" => array( ":gt" => 20, ":lte" => 30 ) );

?>
```

You can also change it in your code using *ini\_set("mongo.cmd", ":")*.
Of course, you can also just use single quotes or backslash-escape the
$.

`mongo.default_host` <span class="type">string</span>  
Default hostname when nothing is passed to the constructor.

`mongo.default_port` <span class="type">string</span>  
The default TCP port number to use when connecting to the database
server if no other port is specified. The database's default is *27017*.

`mongo.is_master_interval` <span class="type">int</span>  
Added in version 1.2.10.

For replicaset connections: The minimum interval with which the driver
will send "isMaster" requests to the MongoDB server. If the value is
lower, there will be more requests, but the driver finds faster whether
the topology of the replicaset has been changed.

`mongo.long_as_object` <span class="type">int</span>  
Return a BSON\_LONG as an instance of <span
class="classname">MongoInt64</span> (instead of a primitive type).

`mongo.native_long` <span class="type">int</span>  
*The default behavior for this has been changed to **`TRUE`** in 1.5.0,
so make sure to set this variable to the value you want (probably
**`TRUE`**) so that the driver's behavior doesn't suddenly change when
you upgrade.*

On 64-bit platforms, the *mongo.native\_long* setting allows for 64-bit
integers to be stored in MongoDB. If it is not set, only 32-bits of the
integer will be saved. The MongoDB data type that is used in this case
is the BSON LONG, instead of the BSON INT that is used if this setting
is turned off.

The setting also changes the way how BSON LONGs behave when they are
read back from MongoDB. Without *mongo.native\_long* enabled, the driver
would convert every BSON LONG to a PHP double which can result in a loss
of precision.

On 32-bit platforms, the *mongo.native\_long* setting changes nothing
for storing integers in MongoDB: the integer is stored as a BSON INT as
before. However, when the setting is enabled and a BSON LONG is read
from MongoDB a <span class="classname">MongoCursorException</span> is
thrown alerting you that the data could not be read back without losing
precision.

On 32-bit systems especially, it is recommended that you combine this
with enabling *mongo.long\_as\_object*.

`mongo.ping_interval` <span class="type">int</span>  
Added in version 1.2.10.

For replicaset connections: The minimum interval with which the driver
will send "ping" requests to the MongoDB server. If the value is lower,
there will be more pings, but the driver finds faster whether a node is
no longer reachable from the replicaset.

`mongo.utf8` <span class="type">int</span>  
If an exception should be thrown for non-UTF8 strings. Until version
1.0.4, the PHP driver would ignore non-UTF8 strings, even though you're
not supposed to insert them. As of 1.0.4, the driver throws a <span
class="classname">MongoException</span>. To ease the transition for
applications that insert non-UTF8 strings, you can turn this option off
to emulate the old, non-exception-throwning behavior. This option will
be eliminated and exceptions always thrown for non-UTF8 strings starting
with version 1.1.0.

Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`MONGO_STREAMS`** (<span class="type">integer</span>)  
<span class="simpara"> Alias of **`MONGO_SUPPORTS_STREAMS`** </span>

**`MONGO_SUPPORTS_STREAMS`** (<span class="type">integer</span>)  
<span class="simpara"> 1 when compiled against PHP Streams (default
since 1.4.0). </span>

**`MONGO_SUPPORTS_SSL`** (<span class="type">integer</span>)  
<span class="simpara"> 1 when
<a href="/book/openssl.html" class="xref">OpenSSL</a> is enabled and
available. </span>

**`MONGO_SUPPORTS_AUTH_MECHANISM_MONGODB_CR`** (<span class="type">integer</span>)  
<span class="simpara"> 1 when MongoDB-Challenge/Reponse authentication
is compiled in. </span>

**`MONGO_SUPPORTS_AUTH_MECHANISM_MONGODB_X509`** (<span class="type">integer</span>)  
<span class="simpara"> 1 when x.509 authentication is compiled in.
</span>

**`MONGO_SUPPORTS_AUTH_MECHANISM_GSSAPI`** (<span class="type">integer</span>)  
<span class="simpara"> 1 when GSSAPI authentication is compiled in.
</span>

**`MONGO_SUPPORTS_AUTH_MECHANISM_PLAIN`** (<span class="type">integer</span>)  
<span class="simpara"> 1 when PLAIN authentication is compiled in.
</span>

**`MONGO_STREAM_NOTIFY_TYPE_IO_INIT`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_TYPE_LOG`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_IO_READ`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_IO_WRITE`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_IO_PROGRESS`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_IO_COMPLETED`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_INSERT`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_QUERY`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_UPDATE`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_DELETE`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_GETMORE`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_KILLCURSOR`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_BATCHINSERT`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_RESPONSE_HEADER`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_WRITE_REPLY`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_CMD_INSERT`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_CMD_UPDATE`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_CMD_DELETE`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

**`MONGO_STREAM_NOTIFY_LOG_WRITE_BATCH`** (<span class="type">integer</span>)  
<span class="simpara"> </span>

Manual
======

**Table of Contents**

-   [Tutorial](/book/mongo.html#Tutorial)
    -   [Making a Connection](/book/mongo.html#Making%20a%20Connection)
    -   [Getting a Database](/book/mongo.html#Getting%20a%20Database)
    -   [Getting A
        Collection](/book/mongo.html#Getting%20A%20Collection)
    -   [Inserting a
        Document](/book/mongo.html#Inserting%20a%20Document)
    -   [Finding Documents using
        MongoCollection::findOne](/book/mongo.html#Finding%20Documents%20using%20MongoCollection::findOne)
    -   [Adding Multiple
        Documents](/book/mongo.html#Adding%20Multiple%20Documents)
    -   [Counting Documents in A
        Collection](/book/mongo.html#Counting%20Documents%20in%20A%20Collection)
    -   [Using a Cursor to Get All of the
        Documents](/book/mongo.html#Using%20a%20Cursor%20to%20Get%20All%20of%20the%20Documents)
    -   [Setting Criteria for a
        Query](/book/mongo.html#Setting%20Criteria%20for%20a%20Query)
    -   [Getting A Set of Documents With a
        Query](/book/mongo.html#Getting%20A%20Set%20of%20Documents%20With%20a%20Query)
    -   [Creating An Index](/book/mongo.html#Creating%20An%20Index)
-   [Read Preferences](/book/mongo.html#Read%20Preferences)
-   [Write Concerns](/book/mongo.html#Write%20Concerns)
-   [SQL to Mongo Mapping
    Chart](/book/mongo.html#SQL%20to%20Mongo%20Mapping%20Chart)
-   [Connecting](/book/mongo.html#Connecting)
    -   [Connecting over SSL](/book/mongo.html#Connecting%20over%20SSL)
    -   [Authentication](/book/mongo.html#Authentication)
    -   [Replica Sets](/book/mongo.html#Replica%20Sets)
    -   [Sharding](/book/mongo.html#Sharding)
    -   [Domain Socket
        Support](/book/mongo.html#Domain%20Socket%20Support)
    -   [Persistent Connections (version
        1.3.0+)](/book/mongo.html#Persistent%20Connections%20(version%201.3.0+))
    -   [Connection Pooling (version 1.2.0-1.2.12
        \*only\*)](/book/mongo.html#Connection%20Pooling%20(version%201.2.0-1.2.12%20*only*))
    -   [Manually Persistent Connections (version up to 1.1.4
        \*only\*)](/book/mongo.html#Manually%20Persistent%20Connections%20(version%20up%20to%201.1.4%20*only*))
-   [Stream Context
    Options](/book/mongo.html#Stream%20Context%20Options)
    -   [log\_cmd\_delete](/book/mongo.html#log_cmd_delete) — Callback
        When Deleting Documents
    -   [log\_cmd\_insert](/book/mongo.html#log_cmd_insert) — Callback
        When Inserting Documents
    -   [log\_cmd\_update](/book/mongo.html#log_cmd_update) — Callback
        When Updating Documents
    -   [log\_getmore](/book/mongo.html#log_getmore) — Callback When
        Retrieving Next Cursor Batch
    -   [log\_killcursor](/book/mongo.html#log_killcursor) — Callback
        When Executing KILLCURSOR operations
    -   [log\_reply](/book/mongo.html#log_reply) — Callback When Reading
        the MongoDB reply
    -   [log\_write\_batch](/book/mongo.html#log_write_batch) — Callback
        When Writing Batches
-   [Writes](/book/mongo.html#Writes)
-   [Querying](/book/mongo.html#Querying)
-   [Updates](/book/mongo.html#Updates)
-   [Security](/book/mongo.html#Security)
-   [Troubleshooting](/book/mongo.html#Troubleshooting)
-   [Running the Driver's
    Tests](/book/mongo.html#Running%20the%20Driver's%20Tests)

**Warning**

This extension is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used.

This manual goes into some detail about how to use MongoDB, but it
mostly covers using the PHP driver. For information about how to design
a schema, what terms means, and setting up the database server, check
out the
<a href="https://www.mongodb.com/" class="link external">» MongoDB documentation</a>.

Tutorial
========

**Table of Contents**

-   [Making a Connection](/book/mongo.html#Making%20a%20Connection)
-   [Getting a Database](/book/mongo.html#Getting%20a%20Database)
-   [Getting A Collection](/book/mongo.html#Getting%20A%20Collection)
-   [Inserting a Document](/book/mongo.html#Inserting%20a%20Document)
-   [Finding Documents using
    MongoCollection::findOne](/book/mongo.html#Finding%20Documents%20using%20MongoCollection::findOne)
-   [Adding Multiple
    Documents](/book/mongo.html#Adding%20Multiple%20Documents)
-   [Counting Documents in A
    Collection](/book/mongo.html#Counting%20Documents%20in%20A%20Collection)
-   [Using a Cursor to Get All of the
    Documents](/book/mongo.html#Using%20a%20Cursor%20to%20Get%20All%20of%20the%20Documents)
-   [Setting Criteria for a
    Query](/book/mongo.html#Setting%20Criteria%20for%20a%20Query)
-   [Getting A Set of Documents With a
    Query](/book/mongo.html#Getting%20A%20Set%20of%20Documents%20With%20a%20Query)
-   [Creating An Index](/book/mongo.html#Creating%20An%20Index)

**Warning**

This extension is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used.

This is the official MongoDB driver for PHP.

Here's a quick code sample that connects, inserts documents, queries for
documents, iterates through query results, and disconnects from MongoDB.
There are more details on each step in the tutorial below.

``` php
<?php

// connect
$m = new MongoClient();

// select a database
$db = $m->comedy;

// select a collection (analogous to a relational database's table)
$collection = $db->cartoons;

// add a record
$document = array( "title" => "Calvin and Hobbes", "author" => "Bill Watterson" );
$collection->insert($document);

// add another record, with a different "shape"
$document = array( "title" => "XKCD", "online" => true );
$collection->insert($document);

// find everything in the collection
$cursor = $collection->find();

// iterate through the results
foreach ($cursor as $document) {
    echo $document["title"] . "\n";
}

?>
```

The above example will output:

    Calvin and Hobbes
    XKCD

Making a Connection
-------------------

To connect to the database server, use one of the following:

``` php
<?php
$connection = new MongoClient(); // connects to localhost:27017
$connection = new MongoClient( "mongodb://example.com" ); // connect to a remote host (default port: 27017)
$connection = new MongoClient( "mongodb://example.com:65432" ); // connect to a remote host at a given port
?>
```

You do not have to explicitly disconnect from the database. The driver
uses persistent connections and will re-use already established
connections.

See Also
--------

The chapter on
<a href="/book/mongo.html#Connecting" class="link">connecting</a> covers
different types of connections.

The API documentation on the <span class="classname">MongoClient</span>
class and <span class="function">MongoClient::\_\_construct</span> give
a comprehensive look at all possible options with a number of examples.

Getting a Database
------------------

To select a database, use:

``` php
<?php
$connection = new MongoClient();
$db = $connection->dbname;
?>
```

The database does not need to be created in advance, you can create new
databases by selecting them.

Be careful of typos! You can inadvertently create a new database, which
can cause confusing errors (here *name* is misspelled as *anme* in the
second selection:

``` php
<?php
$connection = new MongoClient();

$db = $connection->mybiglongdbname;
// do some stuff

$db = $connection->mybiglongdbanme;
// now connected to a different database!
?>
```

See Also
--------

The API documentation on the <span class="classname">MongoDB</span>
class contains more information about database objects.

Getting A Collection
--------------------

Getting a collection has the same syntax as getting a database:

``` php
<?php
$connection = new MongoClient();
$db = $connection->baz;

// select a collection:
$collection = $db->foobar;

// or, directly selecting a database and collection:
$collection = $connection->baz->foobar;
?>
```

A collection is analogous to a table (if you are familiar with
relational databases).

See Also
--------

The API documentation on the <span
class="classname">MongoCollection</span> class contains more information
about collection objects.

Inserting a Document
--------------------

Associative arrays are the basic object that can be saved to a
collection in the database. A somewhat random "document" might be:

``` php
<?php
$doc = array(
    "name" => "MongoDB",
    "type" => "database",
    "count" => 1,
    "info" => (object)array( "x" => 203, "y" => 102),
    "versions" => array("0.9.7", "0.9.8", "0.9.9")
);
?>
```

Note that you can have nested arrays and objects. The driver will always
store an associative array as an object in the database. A numerically
indexed array is stored as an array in case the keys start at 0 and are
not interrupted, and as an object if the array keys don't start at 0 or
have gaps (ie: *0, 1, 4, 5*).

To insert this document, use <span
class="function">MongoCollection::insert</span>:

``` php
<?php
$connection = new MongoClient();
$collection = $connection->database->collectionName;

$collection->insert( $doc );
?>
```

See Also
--------

The API documentation on <span
class="function">MongoCollection::insert</span> contains more
information about inserting data.

Finding Documents using <span class="function">MongoCollection::findOne</span>
------------------------------------------------------------------------------

To show that the document we inserted in the previous step is stored in
the database, we can do a simple <span
class="function">MongoCollection::findOne</span> operation to get a
single document from the collection. This method is useful when there is
only one document matching the query or you are only interested in one
result.

``` php
<?php
$connection = new MongoClient();
$collection = $connection->database->collectionName;

$document = $collection->findOne();
var_dump( $document );
?>
```

The above example will output:

    array(6) {
      ["_id"]=>
      object(MongoId)#8 (1) {
        ["$id"]=>
        string(24) "4e2995576803fab768000000"
      }
      ["name"]=>
      string(7) "MongoDB"
      ["type"]=>
      string(8) "database"
      ["count"]=>
      int(1)
      ["info"]=>
      array(2) {
        ["x"]=>
        int(203)
        ["y"]=>
        int(102)
      }
      ["versions"]=>
      array(3) {
        [0]=>
        string(5) "0.9.7"
        [1]=>
        string(5) "0.9.8"
        [2]=>
        string(5) "0.9.9"
      }
    }

Note that there is an *\_id* field that has been added automatically to
your document. *\_id* is the "primary key" field. If your document does
not specify one, the driver will add one automatically.

If you specify your own *\_id* field, it must be unique to the
collection. See the example here:

``` php
<?php
$connection = new MongoClient();
$db = $connection->database;

$db->foo->insert(array("_id" => 1));
// this will throw an exception
$db->foo->insert(array("_id" => 1));

// this is fine, as it is a different collection
$db->bar->insert(array("_id" => 1));
?>
```

By default the driver will ensure the server has acknowledged the write
before returning. You can optionally turn this behaviour off by passing
*array("w" =\> 0)* as the second argument. This means that the driver
should not wait for the database to acknowledge the write and would not
throw the duplicate *\_id* exception.

See Also
--------

<span class="function">MongoCollection::findOne</span> for more
information about finding data.

<span class="classname">MongoId</span> goes into more detail on unique
ids.

The <a href="/book/mongo.html#Writes" class="link">writes</a> section
covers writes in more depth, and the
<a href="/book/mongo.html#Write%20Concerns" class="xref"></a> chapter
goes into details of the various Write Concern options.

Adding Multiple Documents
-------------------------

In order to do more interesting things with queries, let's add multiple
simple documents to the collection. These documents will just be of the
form *array( "i" =\> <span class="replaceable">value</span> );* and we
can do this fairly efficiently in a loop:

``` php
<?php
$connection = new MongoClient();
$collection = $connection->database->collectionName;

for ( $i = 0; $i < 100; $i++ )
{
    $collection->insert( array( 'i' => $i, "field{$i}" => $i * 2 ) );
}
?>
```

Notice that we can insert arrays with different keys into the same
collection. This aspect is what we mean when we say that MongoDB is
"schema-free". In the example above each document has an *i* field, but
also a field name in the form of *field* + *$i*.

Counting Documents in A Collection
----------------------------------

Now that we've inserted 101 documents (the 100 we did in the loop, plus
the first one), we can check to see if we have them all using the <span
class="function">MongoCollection::count</span> method.

``` php
<?php
$connection = new MongoClient();
$collection = $connection->database->collectionName;

echo $collection->count();
?>
```

and it should print 101.

Using a Cursor to Get All of the Documents
------------------------------------------

In order to get all the documents in the collection, we will use <span
class="function">MongoCollection::find</span>. The find() method returns
a <span class="classname">MongoCursor</span> object which allows us to
iterate over the set of documents that matched our query. So to query
all of the documents and print them out:

``` php
<?php
$connection = new MongoClient();
$collection = $connection->database->collectionName;

$cursor = $collection->find();
foreach ( $cursor as $id => $value )
{
    echo "$id: ";
    var_dump( $value );
}
?>
```

and that should print all 101 documents in the collection. *$id* is the
*\_id* field of a document (cast to a string) and *$value* is the
document itself.

See Also
--------

The API documentation on <span
class="function">MongoCollection::find</span> contains more information
about finding data.

Setting Criteria for a Query
----------------------------

We can create a query to pass to the <span
class="function">MongoCollection::find</span> method to get a subset of
the documents in our collection. For example, if we wanted to find the
document for which the value of the *"i"* field is *71*, we would do the
following:

``` php
<?php
$connection = new MongoClient();
$collection = $connection->database->collectionName;

$query = array( 'i' => 71 );
$cursor = $collection->find( $query );

while ( $cursor->hasNext() )
{
    var_dump( $cursor->getNext() );
}
?>
```

The above example will output:

    array(2) {
      ["_id"]=>
      object(MongoId)#6 (0) {
      }
      ["i"]=>
      int(71)
      ["_ns"]=>
      "testCollection"
    }

Getting A Set of Documents With a Query
---------------------------------------

We can use the query to get a set of documents from our collection. For
example, if we wanted to get all documents where *"i"* \> *50*, we could
write:

``` php
<?php
$connection = new MongoClient();
$collection = $connection->database->collectionName;

$query = array( "i" => array( '$gt' => 50 ) ); //note the single quotes around '$gt'
$cursor = $collection->find( $query );

while ( $cursor->hasNext() )
{
    var_dump( $cursor->getNext() );
}
?>
```

which should print the documents where *"i"* \> *50*. We could also get
a range, say *20 \< i \<= 30*:

    <?php
    $connection = new MongoClient();
    $collection = $connection->database->collectionName;

    $query = array( 'i' => array( '$gt' => 20, "\$lte" => 30 ) );
    $cursor = $collection->find( $query );

    while ( $cursor->hasNext() )
    {
        var_dump( $cursor->getNext() );
    }
    ?>

Remember to always escape the $-symbol or use single quotes. Otherwise
PHP will interpret it to be the variable `$gt`.

Creating An Index
-----------------

MongoDB supports indexes, and they are very easy to add on a collection.
To create an index, you specify the field name and direction: ascending
(1) or descending (-1). The following creates an ascending index on the
"i" field:

``` php
<?php
$connection = new MongoClient();
$collection = $connection->database->collectionName;

$collection->ensureIndex( array( "i" => 1 ) );  // create index on "i"
$collection->ensureIndex( array( "i" => -1, "j" => 1 ) );  // index on "i" descending, "j" ascending
?>
```

Indexing is critical for good read performance as your data grows. If
you are not familiar with indexing, check out the <span
class="function">MongoCollection::ensureIndex</span> documentation and
the core
<a href="https://docs.mongodb.com/manual/indexes/" class="link external">» MongoDB indexing documentation</a>.

Read Preferences
================

MongoDB 2.2 and version 1.3.0 of the driver add support for
<a href="https://docs.mongodb.com/manual/core/read-preference/" class="link external">» read preferences</a>,
which allow control over how queries are directed to mongod instances in
a replica set environment. Read preferences may be specified on either a
per-connection, per-database, or per-collection basis. Preferences
defined at a higher level will be inherited by default (e.g. <span
class="classname">MongoCollection</span> will inherit read preferences
defined on the corresponding <span class="classname">MongoDB</span>
instance).

Read preferences are specified with a combination of modes and tag sets.
Modes determine how mongod instances are prioritized, while
<a href="https://docs.mongodb.com/manual/tutorial/configure-replica-set-tag-sets/" class="link external">» tag sets</a>
specify criteria for eligible mongod instances. Mongod instances are
only eligible if they are within a 15ms difference in ping time from the
nearest mongod instance.

**Warning**

All read preference modes except *MongoClient::RP\_PRIMARY* may return
stale data as secondaries replicate operations from the primary with
some delay. Ensure that your application can tolerate stale data if you
choose to use a mode other than *MongoClient::RP\_PRIMARY*.

-   *MongoClient::RP\_PRIMARY*

    All read operations use only the current replica set primary. This
    is the default. If the primary is unavailable, read operations will
    produce an exception.

    This mode is incompatible with use of tag sets. Specifying a tag set
    with *MongoClient::RP\_PRIMARY* will result in an exception.

-   *MongoClient::RP\_PRIMARY\_PREFERRED*

    In most situations, operations read from the primary member of the
    set. However, if the primary is unavailable, as is the case during
    failover situations, operations read from secondary members.

    When the read preference includes a tag set, the client reads first
    from the primary, if available, and then from secondaries that match
    the specified tags. If no secondaries have matching tags, the read
    operation will produce an exception.

    **Warning**
    Version 2.2 of mongos added full support for read preferences. When
    connecting to older mongos instances,
    *MongoClient::RP\_PRIMARY\_PREFERRED* will send queries to
    secondaries.

-   *MongoClient::RP\_SECONDARY*

    Operations read only from the secondary members of the set. If no
    secondaries are available, read operations will produce an
    exception.

    Most sets have at least one secondary, but there are situations
    where there may be no available secondary. For example, a set with a
    primary, a secondary, and an arbiter may not have any secondaries if
    a member is in recovering state or unavailable.

    When the read preference includes a tag set, the client attempts to
    find secondary members that match the specified tag set and directs
    reads to a random secondary from among the nearest group. If no
    secondaries have matching tags, the read operation will produce an
    exception.

-   *MongoClient::RP\_SECONDARY\_PREFERRED*

    In most situations, operations read from secondary members, but in
    situations where the set consists of a single primary with no other
    members, the read operation will use the set's primary.

    When the read preference includes a tag set, the client attempts to
    find a secondary member that matches the specified tag set and
    directs reads to a random secondary from among the nearest group. If
    no secondaries have matching tags, the read operation will produce
    an exception.

-   *MongoClient::RP\_NEAREST*

    The driver reads from a *random* member of the set that has a ping
    time that is less than 15ms slower than the member with the lowest
    ping time. Reads in the *MongoClient::RP\_NEAREST* mode do not
    consider the member's type and may read from both primaries and
    secondaries.

    Set this mode to minimize the effect of network latency on read
    operations without preference for current or stale data.

    If you specify a tag set, the client attempts to find a member that
    matches the specified tag set and directs reads to a random node
    from among the nearest group.

    > **Note**:
    >
    > All operations read from the nearest member of the replica set
    > that matches the specified read preference mode. The
    > *MongoClient::RP\_NEAREST* mode prefers low latency reads over a
    > member's primary or secondary status.

<a href="https://docs.mongodb.com/manual/tutorial/configure-replica-set-tag-sets/" class="link external">» Tag sets</a>
allow you to specify criteria so that your application can target read
operations to specific members, based on custom parameters. Tag sets
make it possible to ensure that read operations target members in a
particular data center or target mongod instances designated for a
particular class of operations, such as reporting or analytics.

You can specify tag sets with the following read preference modes:

-   *MongoClient::RP\_PRIMARY\_PREFERRED*

-   *MongoClient::RP\_SECONDARY*

-   *MongoClient::RP\_SECONDARY\_PREFERRED*

-   *MongoClient::RP\_NEAREST*

You cannot specify tag sets with the *MongoClient::RP\_PRIMARY* read
preference mode. Tags apply only when selecting a secondary member of a
set, except for the when in the nearest mode.

Read preferences may be specified in either the connection URI provided
to <span class="function">MongoClient::\_\_construct</span>, which uses
a query string syntax, or via setter methods on the core classes, which
use an array syntax for tag sets.

When specifying read preference modes in a query string, the tag sets
for the *readPreferenceTags* value should be a comma-delimited sequence
of colon-delimited key/value pairs.

> **Note**:
>
> Each tag set defined in the query string will use the
> *readPreferenceTags* name. Unlike how PHP might handle URL query
> strings, successive values for *readPreferenceTags* will not overwrite
> each other. The driver will collect tag sets in the order they appear
> in the query string.

**Warning**

If the driver cannot find a matching tag set the read will fail! It is
your responsibility of providing suitable fallback, such as an empty
*readPreferenceTags* value to fallback to "no tag set preference".

**Example \#1 Connection URI read preferences with query string syntax**

``` php
<?php
// Prefer the nearest server with no tag preference
$uri  = 'mongodb://rs1.example.com,rs2.example.com/';
$uri .= '?readPreference=nearest';
$m = new MongoClient($uri, array('replicaSet' => 'rs'));

// Pick the nearest server in the "east" data center
$uri  = 'mongodb://rs1.example.com,rs2.example.com/';
$uri .= '?readPreference=nearest';
$uri .= '&readPreferenceTags=dc:east';
$m = new MongoClient($uri, array('replicaSet' => 'rs'));

// Prefer the nearest server in the "east" data center also used for reporting,
// but fall back to a server in the "west" data center
$uri  = 'mongodb://rs1.example.com,rs2.example.com/';
$uri .= '?readPreference=nearest';
$uri .= '&readPreferenceTags=dc:east,use:reporting';
$uri .= '&readPreferenceTags=dc:west';
$m = new MongoClient($uri, array('replicaSet' => 'rs'));

// Prefer the nearest server in the "east" data center, then a server in the
// "west" data center, and finally fall back to no tag set preference
$uri  = 'mongodb://rs1.example.com,rs2.example.com/';
$uri .= '?readPreference=nearest';
$uri .= '&readPreferenceTags=dc:east';
$uri .= '&readPreferenceTags=dc:west';
$uri .= '&readPreferenceTags=';
$m = new MongoClient($uri, array('replicaSet' => 'rs'));
?>
```

**Example \#2 Setting read preferences with array syntax for tag sets**

``` php
<?php

$m = new MongoClient('mongodb://rs1.example.com,rs2.example.com', array(
    'replicaSet' => 'rs',
));

// Prefer the nearest server with no tag preference
$m->setReadPreference(MongoClient::RP_NEAREST, array());

// Pick the nearest server in the "east" data center
$m->setReadPreference(MongoClient::RP_NEAREST, array(
    array('dc' => 'east'),
));

// Prefer the nearest server in the "east" data center also used for reporting,
// but fall back to a server in the "west" data center
$m->setReadPreference(MongoClient::RP_NEAREST, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
));

// Prefer the nearest server in the "east" data center, then a server in the
// "west" data center, and finally fall back to no tag set preference
$m->setReadPreference(MongoClient::RP_NEAREST, array(
    array('dc' => 'east'),
    array('dc' => 'west'),
    array(),
));
?>
```

Write Concerns
==============

MongoDB provides several different ways of selecting how durable a write
to the database should be. These ways are called *Write Concerns* and
span everything from completely ignoring all errors, to specifically
targetting which servers are required to confirm the write before
returning the operation.

When a write (such as with <span
class="methodname">MongoCollection::insert</span>, <span
class="methodname">MongoCollection::update</span>, and <span
class="methodname">MongoCollection::remove</span>) is given a Write
Concern option (*"w"*) the driver will send the query to MongoDB and
piggy back a *getLastError* command (GLE) with the Write Concern option
at the same time. The server only returns when the Write Concern
condition is verified to be fulfilled, or the query times out
(controlled with the *"wtimeout"* option, *10000* milliseconds is the
default).

**Warning**

Even though a *getLastError* command times out the data will most likely
have been written to the primary server and will be replicated to all
the secondaries once they have caught up.

The typical reasons for a timeout to happen is if you specify a Write
Concern which requires confirmation from more servers then you currently
have available.

When using acknowledged writes and the replica set has failed over, the
driver will automatically disconnect from the primary, throw an
exception, and attempt to find a new primary on the next operation (your
application must decide whether or not to retry the operation on the new
primary).

When using unacknowledged writes (w=0) and the replica set has failed
over, there will be no way for the driver to know about the change so it
will continue and silently fail to write.

The default Write Concern for the <span
class="classname">MongoClient</span> is *1*: acknowledge write
operations.

| Write Concern | Meaning                          | Description                                                                                                                   |
|---------------|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|
| w=0           | Unacknowledged                   | A write will not be followed up with a GLE call, and therefore not checked ("fire and forget")                                |
| w=1           | Acknowledged                     | The write will be acknowledged by the server (the primary on replica set configuration)                                       |
| w=N           | Replica Set Acknowledged         | The write will be acknowledged by the primary server, and replicated to *N-1* secondaries.                                    |
| w=majority    | Majority Acknowledged            | The write will be acknowledged by the majority of the replica set (including the primary). This is a special reserved string. |
| w=\<tag set\> | Replica Set Tag Set Acknowledged | The write will be acknowledged by members of the entire tag set                                                               |
| j=true        | Journaled                        | The write will be acknowledged by primary and the journal flushed to disk                                                     |

Each of the methods that causes writes ( <span
class="methodname">MongoCollection::insert</span>, <span
class="methodname">MongoCollection::update</span>, <span
class="methodname">MongoCollection::remove</span>, and <span
class="methodname">MongoCollection::batchInsert</span>) allow an
optional argument to send a set of options to the MongoDB server. With
this option array you can set the WriteConcern as the following example
illustrates:

**Example \#1 Passing a WriteConcern to a write operation**

``` php
<?php
// Setting w=0 for insert:
$collection->insert($someDoc, array("w" => 0));

// Setting w=majority for update:
$collection->update($someDoc, $someUpdates, array("w" => "majority"));

// Setting w=5 and j=true for remove:
$collection->update($someDoc, array("w" => 5, "j" => true));

// Setting w="AllDCs" for batchInsert:
$collection->update(array($someDoc1, $someDoc2), array("w" => "AllDCs"));
?>
```

Besides setting WriteConcerns per operation as an option argument, it is
also possible to set a default WriteConcern in different ways.

The first way is through the
<a href="" class="link">connection string</a>. The connection string
accepts the *journal*, *w*, and *wTimeoutMS* options:

**Example \#2 Connection string WriteConcerns**

``` php
<?php
$m = new MongoClient("mongodb://localhost/?journal=true&w=majority&wTimeoutMS=20000");
?>
```

Since driver version 1.5 it is also possible to call <span
class="methodname">MongoDB::setWriteConcern</span> and <span
class="methodname">MongoCollection::setWriteConcern</span> to set a
default WriteConcern for all operations created from that specific <span
class="classname">MongoDB</span> or <span
class="classname">MongoCollection</span> object:

**Example \#3 MongoDB::setWriteConcern and
MongoCollection::setWriteConcern**

``` php
<?php
$m = new MongoClient("mongodb://localhost/");
$d = $m->demoDb;
$c = $d->demoCollection;

// Set w=3 on the database object with a timeout of 25000ms
$d->setWriteConcern(3, 25000);

// Set w=majority on the collection object without changing the timeout
$c->setWriteConcern("majority");
?>
```

By not requiring the server to acknowledge writes the writes can be
performed extremely quickly, but you don't know whether or not they
actually succeeded. Writes can fail for a number of reasons: if there
are network problems, if a database server goes down, or if the write
was simply invalid (e.g., writing to a system collection; or duplicate
key errors).

While developing, you should always use acknowledged writes (to protect
against inadvertent mistakes, such as syntax errors, invalid operators,
duplicate key errors and so on). In production, unacknowledged writes
can be used for "unimportant" data. Unimportant data varies on
application, but it's generally automatically (instead of user
generated) data, such as click tracking or GPS locations, where you can
get thousands of records per second.

It is strongly recommended that you do an acknowledged write at the end
of series of unacknowledged writes. Doing so will not incur in a too
large performance penalty, but still allow you to catch any errors that
may have occurred.

**Example \#4 Unacknowledged WriteConcern, followed with Acknowledged
Write**

``` php
<?php
$collection->insert($someDoc, array("w" => 0));
$collection->update($criteria, $newObj, array("w" => 0));
$collection->insert($somethingElse, array("w" => 0));
try {
    $collection->remove($something, array("w" => 1));
} catch(MongoCursorException $e) {
    /* Handle the exception.. */
    /* Here we should issue find() queries on the IDs generated for
    $somethingElse and $someDoc to verify they got written to the database and
    attempt to figureout where in the chain something happened. */
}
?>
```

If the last write throws an exception, you know that there's a problem
with your database.

These type of write operations will make sure that the database has
accepted the write operation before returning success. If the write
failed, it will throw a <span
class="classname">MongoCursorException</span> with an explanation of the
failure. The <span class="classname">MongoClient</span> default
behaviour is to acknowledge the write (w=1).

It is possible to specify how many members of an replica set have to
acknowledge the write (i.e. have it replicated) before the write is
deemed acknowledged and the operation returns.

**Example \#5 Acknowledged Writes**

``` php
<?php
// Force acknowledgement from the primary only
$collection->insert($doc, array("w" => 1));

// Force acknowledgement from the primary, and one other member of the
// replica set
$collection->insert($doc, array("w" => 2));

// Force acknowledgement from the primary, and six other members of the
// replica set (you probably never should do this):
$collection->insert($doc, array("w" => 7));
?>
```

Keep in mind to select your Write Concern carefully. If you have a
replica set with 5 members, and you select Write Concern of *4* you will
risk the write blocking forever when one member of the replica set goes
down for maintenance or a temporary network outage happens.

**Warning**

Passing in a string value for Write Concern has a specific meaning
(Replica Set Tag Set Acknowledged). Please be careful of *NOT* using
string values for numbers (i.e. *array("w" =\> "1")*) as it will be
treated as a tag set name.

Using the special *majority* Write Concern option is the recommended way
for writes that are required to survive the apocalypse, as it will
ensure the majority of your replica set will have the write and will
therefore be guaranteed to survive all usual suspect outage scenarios.

**Example \#6 Majority Acknowledged Write**

``` php
<?php
$collection->insert($someDoc, array("w" => "majority"));
?>
```

When connecting to a replica set the default Write Concern is only to
have the primary server acknowledge the write. There is however a 100ms
window until the write gets journaled and flushed to disk. It is
possible to force the write to be journaled before acknowledging the
write by setting the *j* option:

**Example \#7 Acknowledged and Journaled Write**

Forcing journal flush

``` php
<?php
$options = array(
    "w" => 1,
    "j" => true,
);
try {
    $collection->insert($document, $options);
} catch(MongoCursorException $e) {
    /* handle the exception */
}
?>
```

-   <a href="https://docs.mongodb.com/manual/applications/replication/#replica-set-write-concern" class="link external">» MongoDB WriteConcern docs</a>

| Version | Description                                                                                                                                                                                                                                             |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1.3.0   | <span class="classname">MongoClient</span> was introduced and defaults to <a href="/book/mongo.html#Acknowledged%20Writes" class="link">acknowledged</a> writes. The deprecated <span class="classname">Mongo</span> defaults to unacknowledged writes. |
| 1.3.0   | The *"safe"* write option has been deprecated and is not available with the new <span class="classname">MongoClient</span> class. Use the *"w"* option instead.                                                                                         |

SQL to Mongo Mapping Chart
==========================

This is a PHP-specific version of the
<a href="https://docs.mongodb.com/manual/reference/sql-comparison/" class="link external">» SQL to Mongo</a>
mapping chart in the main docs.

| SQL Statement                                      | Mongo Query Language Statement                                                                      |
|----------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| *CREATE TABLE USERS (a Number, b Number)*          | Implicit or use <span class="function">MongoDB::createCollection</span>.                            |
| *INSERT INTO USERS VALUES(1,1)*                    | *$db-\>users-\>insert(array("a" =\> 1, "b" =\> 1));*                                                |
| *SELECT a,b FROM users*                            | *$db-\>users-\>find(array(), array("a" =\> 1, "b" =\> 1));*                                         |
| *SELECT \* FROM users WHERE age=33*                | *$db-\>users-\>find(array("age" =\> 33));*                                                          |
| *SELECT a,b FROM users WHERE age=33*               | *$db-\>users-\>find(array("age" =\> 33), array("a" =\> 1, "b" =\> 1));*                             |
| *SELECT a,b FROM users WHERE age=33 ORDER BY name* | *$db-\>users-\>find(array("age" =\> 33), array("a" =\> 1, "b" =\> 1))-\>sort(array("name" =\> 1));* |
| *SELECT \* FROM users WHERE age\>33*               | *$db-\>users-\>find(array("age" =\> array('$gt' =\> 33)));*                                         |
| *SELECT \* FROM users WHERE age\<33*               | *$db-\>users-\>find(array("age" =\> array('$lt' =\> 33)));*                                         |
| *SELECT \* FROM users WHERE name LIKE "%Joe%"*     | *$db-\>users-\>find(array("name" =\> new MongoRegex("/Joe/")));*                                    |
| *SELECT \* FROM users WHERE name LIKE "Joe%"*      | *$db-\>users-\>find(array("name" =\> new MongoRegex("/^Joe/")));*                                   |
| *SELECT \* FROM users WHERE age\>33 AND age\<=40*  | *$db-\>users-\>find(array("age" =\> array('$gt' =\> 33, '$lte' =\> 40)));*                          |
| *SELECT \* FROM users ORDER BY name DESC*          | *$db-\>users-\>find()-\>sort(array("name" =\> -1));*                                                |
| *CREATE INDEX myindexname ON users(name)*          | *$db-\>users-\>ensureIndex(array("name" =\> 1));*                                                   |
| *CREATE INDEX myindexname ON users(name,ts DESC)*  | *$db-\>users-\>ensureIndex(array("name" =\> 1, "ts" =\> -1));*                                      |
| *SELECT \* FROM users WHERE a=1 and b='q'*         | *$db-\>users-\>find(array("a" =\> 1, "b" =\> "q"));*                                                |
| *SELECT \* FROM users LIMIT 20, 10*                | *$db-\>users-\>find()-\>limit(10)-\>skip(20);*                                                      |
| *SELECT \* FROM users WHERE a=1 or b=2*            | *$db-\>users-\>find(array('$or' =\> array(array("a" =\> 1), array("b" =\> 2))));*                   |
| *SELECT \* FROM users LIMIT 1*                     | *$db-\>users-\>find()-\>limit(1);*                                                                  |
| *EXPLAIN SELECT \* FROM users WHERE z=3*           | *$db-\>users-\>find(array("z" =\> 3))-\>explain()*                                                  |
| *SELECT DISTINCT last\_name FROM users*            | *$db-\>command(array("distinct" =\> "users", "key" =\> "last\_name"));*                             |
| *SELECT COUNT(\*y) FROM users*                     | *$db-\>users-\>count();*                                                                            |
| *SELECT COUNT(\*y) FROM users where AGE \> 30*     | *$db-\>users-\>find(array("age" =\> array('$gt' =\> 30)))-\>count();*                               |
| *SELECT COUNT(AGE) from users*                     | *$db-\>users-\>find(array("age" =\> array('$exists' =\> true)))-\>count();*                         |
| *UPDATE users SET a=1 WHERE b='q'*                 | *$db-\>users-\>update(array("b" =\> "q"), array('$set' =\> array("a" =\> 1)));*                     |
| *UPDATE users SET a=a+2 WHERE b='q'*               | *$db-\>users-\>update(array("b" =\> "q"), array('$inc' =\> array("a" =\> 2)));*                     |
| *DELETE FROM users WHERE z="abc"*                  | *$db-\>users-\>remove(array("z" =\> "abc"));*                                                       |

Connecting
==========

**Table of Contents**

-   [Connecting over SSL](/book/mongo.html#Connecting%20over%20SSL)
-   [Authentication](/book/mongo.html#Authentication)
-   [Replica Sets](/book/mongo.html#Replica%20Sets)
-   [Sharding](/book/mongo.html#Sharding)
-   [Domain Socket Support](/book/mongo.html#Domain%20Socket%20Support)
-   [Persistent Connections (version
    1.3.0+)](/book/mongo.html#Persistent%20Connections%20(version%201.3.0+))
-   [Connection Pooling (version 1.2.0-1.2.12
    \*only\*)](/book/mongo.html#Connection%20Pooling%20(version%201.2.0-1.2.12%20*only*))
-   [Manually Persistent Connections (version up to 1.1.4
    \*only\*)](/book/mongo.html#Manually%20Persistent%20Connections%20(version%20up%20to%201.1.4%20*only*))

Connecting to MongoDB can be as easy as *new MongoClient*, but there are
many additional options and configurations. The documentation for <span
class="function">MongoClient::\_\_construct</span> covers all of the API
options, but this page gives some more details and advice for practical
use cases.

Connecting over SSL
-------------------

The driver supports connecting to
<a href="https://docs.mongodb.com/manual/tutorial/configure-ssl/" class="link external">» MongoDB over SSL</a>
and can optionally use
<a href="/context/ssl.html" class="link">SSL Stream Context</a> options
to provide more details, such as verifying certificates against specific
certificate chain, or authenticate to
<a href="https://docs.mongodb.com/manual/tutorial/configure-x509/" class="link external">» MongoDB using X509 certificates</a>.

**Example \#1 Connect to MongoDB Instance with SSL Encryption**

``` php
<?php
$mc = new MongoClient("mongodb://server1", array("ssl" => true));
?>
```

**Example \#2 Connect to MongoDB Instance with SSL Encryption, verifying
it is who we think it is**

``` php
<?php
$SSL_DIR = "/vagrant/certs";
$SSL_FILE = "CA_Root_Certificate.pem";

$ctx = stream_context_create(array(
    "ssl" => array(
        /* Certificate Authority the remote server certificate must be signed by */
        "cafile"            => $SSL_DIR . "/" . $SSL_FILE,

        /* Disable self signed certificates */
        "allow_self_signed" => false,

        /* Verify the peer certificate against our provided Certificate Authority root certificate */
        "verify_peer"       => true, /* Default to false pre PHP 5.6 */

        /* Verify the peer name (e.g. hostname validation) */
        /* Will use the hostname used to connec to the node */
        "verify_peer_name"  => true,

        /* Verify the server certificate has not expired */
        "verify_expiry"     => true, /* Only available in the MongoDB PHP Driver */
    ),
);

$mc = new MongoClient(
    "mongodb://server1", 
    array("ssl" => true), 
    array("context" => $ctx)
);
?>
```

> **Note**:
>
> The *"verify\_peer\_name"* is new in PHP 5.6.0. The MongoDB driver as
> of 1.6.5 however has backported this feature into the driver itself,
> so it works with PHP 5.3 and 5.4 too

**Example \#3 Connect to MongoDB Instance that Requires Client
Certificates**

``` php
<?php
$SSL_DIR  = "/vagrant/certs";
$SSL_FILE = "CA_Root_Certificate.pem";

$MYCERT   = "/vagrant/certs/ca-signed-client.pem";

$ctx = stream_context_create(array(
    "ssl" => array(
        "local_cert"        => $MYCERT,
        /* If the certificate we are providing was passphrase encoded, we need to set it here */
        "passphrase"        => "My Passphrase for the local_cert",

        /* Optionally verify the server is who he says he is */
        "cafile"            => $SSL_DIR . "/" . $SSL_FILE,
        "allow_self_signed" => false,
        "verify_peer"       => true,
        "verify_peer_name"  => true,
        "verify_expiry"     => true,
    ),
));

$mc = new MongoClient(
    "mongodb://server1/?ssl=true", 
    array(), 
    array("context" => $ctx)
);
?>
```

**Example \#4 Authenticating with X.509 certificates**

The username is the *certificate subject* from the X509, which can be
extracted like this:

``` shell
openssl x509 -in /vagrant/certs/ca-signed-client.pem -inform PEM -subject -nameopt RFC2253
```

``` php
<?php
$ctx = stream_context_create( array(
    "ssl" => array(
        "local_cert" => "/vagrant/certs/ca-signed-client.pem",
    )
) );

$mc = new MongoClient(
    'mongodb://username@server1/?authSource=$external&authMechanism=MONGODB-X509&ssl=true', 
    array(), 
    array("context" => $ctx)
);
?>
```

Where *username* is the certificate subject.

| Version | Description                                          |
|---------|------------------------------------------------------|
| 1.5.0   | Added support for X509 authentication.               |
| 1.4.0   | Added support for connecting to SSL enabled MongoDB. |

Authentication
--------------

If MongoDB is started with the *--auth* or *--keyFile* options, you must
authenticate before you can do any operations with the driver. You may
authenticate a connection by specifying the username and password in
either the connection URI or the *"username"* and *"password"* options
for <span class="function">MongoClient::\_\_construct</span>.

**Example \#1 Authenticating against the "admin" database**

``` php
<?php
// Specifying the username and password in the connection URI (preferred)
$m = new MongoClient("mongodb://${username}:${password}@localhost");

// Specifying the username and password via the options array (alternative)
$m = new MongoClient("mongodb://localhost", array("username" => $username, "password" => $password));
?>
```

By default, the driver will authenticate against the *admin* database.
You may authenticate against a different database by specifying it in
either the connection URI or the *"db"* option for <span
class="function">MongoClient::\_\_construct</span>.

**Example \#2 Authenticating against normal databases**

``` php
<?php
// Specifying the authentication database in the connection URI (preferred)
$m = new MongoClient("mongodb://${username}:${password}@localhost/myDatabase");

// Specifying the authentication database via the options array (alternative)
$m = new MongoClient("mongodb://${username}:${password}@localhost", array("db" => "myDatabase"));
?>
```

If your connection is dropped, the driver will automatically attempt to
reconnect and reauthenticate you.

Replica Sets
------------

To connect to a replica set, specify one or more members of the set and
use the *"replicaSet"* option. Multiple servers may be delimited by a
comma.

**Example \#1 ReplicaSet seed list**

``` php
<?php
// Using multiple servers as the seed list (prefered)
$m = new MongoClient("mongodb://rs1.example.com:27017,rs2.example.com:27017/?replicaSet=myReplSetName");

// Using one server as the seed list
$m = new MongoClient("mongodb://rs1.example.com:27017", array("replicaSet" => "myReplSetName"));

// Using multiple servers as the seed list
$m = new MongoClient("mongodb://rs1.example.com:27017,rs2.example.com:27017", array("replicaSet" => "myReplSetName"));
?>
```

The PHP driver will query the database server(s) listed to determine the
primary. So long as it can connect to at least one host listed and find
a primary, the connection will succeed. If it cannot make a connection
to any servers listed or cannot find a primary, a <span
class="classname">MongoConnectionException</span> will be thrown.

**Tip**

You should always provide a seed list with more than one member of the
ReplicaSet. For highest availability you should seed with at least one
server from each of your datacenters.

**Warning**

The host names that you specify in the seed list *must* match the host
names in the replica set configuration. This is because the driver only
uses the host names in the replica set configuration to create the hash
for its persistent connections.

For example, if an IP address is used in the seed list and the replica
set is configured with host names, the driver will discard any seed list
connection(s) that differ from the canonical host names reported by the
replica set. Effectively, these non-canonical seed list connections will
be recreated on each request, greatly reducing the benefit of using
persistent connections.

**Warning**

The driver does *not* support connecting to different replica sets with
the same name. This extends beyond one script so make sure to have
separate names for each of your replica sets. That also means that you
can *not* do this:

**Example \#2 Wrong replica set name duplication**

``` php
<?php
$m = new MongoClient("mongodb://devserver1,devserver2,devserver3/?replicaSet=repset");
$m = new MongoClient("mongodb://prodserver1,prodserver2,prodserver3/?replicaSet=repset");
?>
```

Instead, you need to have two different names for your replica sets:

**Example \#3 Correct use of two replica set names**

``` php
<?php
$m = new MongoClient("mongodb://devserver1,devserver2,devserver3/?replicaSet=devset");
$m = new MongoClient("mongodb://prodserver1,prodserver2,prodserver3/?replicaSet=prodset");
?>
```

If the primary becomes unavailable, an election will take place and a
secondary will be promoted to the role of primary (unless a majority
vote cannot be established). During this time
(<a href="https://docs.mongodb.com/manual/faq/replica-sets/#how-long-does-replica-set-failover-take" class="link external">» 20-60 seconds</a>),
the connection will not be able to perform any write operations and
attempts to do so will result in an exception. Connections to
secondaries will still be able to perform reads.

> **Note**:
>
> The default
> <a href="/book/mongo.html#Read%20Preferences" class="link">Read Preference</a>
> is to only read from the primary. During the election process there is
> no primary, and all read will therefore fail.
>
> It is recommended to use **`MongoClient::RP_PRIMARY_PREFERRED`** Read
> Preference for applications that require high availability for reads,
> as reads will only be executed on the secondaries when there simply
> isn't a primary available.

Once a primary is elected, attempting to perform a read or write will
allow the driver to detect the new primary. The driver will make this
its primary database connection and continue operating normally.

The health and state of a secondary is checked every 5 seconds
(configurable with
<a href="/book/mongo.html#" class="link">mongo.ping_interval</a>) or
when the next operation occurs after 5 seconds. It will also recheck the
configuration when the driver has a problem reaching a server.

Replica set failovers are checked every 60 seconds (configurable with
<a href="/book/mongo.html#" class="link">mongo.is_master_interval</a>),
and whenever a write operation fails when using acknowledged writes.

**Caution**

Secondaries may be behind the primary in operations, so your application
must be able to handle out-of-date data when using Read Preferences
other then **`MongoClient::RP_PRIMARY`**.

For more information on replica sets, see the
<a href="https://docs.mongodb.com/manual/replication/" class="link external">» core documentation</a>.

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <a href="/book/mongo.html#Write%20Concerns" class="xref"></a>

| Version | Description                                                        |
|---------|--------------------------------------------------------------------|
| 1.0.9   | Added support for connecting to ReplicaSet and automatic failover. |

Sharding
--------

To connect to a shard cluster, specify the address of one or more
*mongos* instances in the connection string. Multiple servers may be
delimited by a comma.

``` php
<?php
// Using one server as the seed list
$m = new MongoClient("mongodb://mongos1.example.com:27017");

// Using multiple servers as the seed list
$m = new MongoClient("mongodb://mongos1.example.com:27017,mongos2.example.com:27017");
?>
```

Regardless of whether each shard is a stand-alone *mongod* server or a
full replica set, the driver's connection process is the same. All
database communication will be routed through *mongos*.

For more information on sharding with MongoDB, see the
<a href="https://docs.mongodb.com/manual/sharding/" class="link external">» sharding documentation</a>.

Domain Socket Support
---------------------

MongoDB has built-in support for connecting via Unix Domain Sockets and
will open the socket on startup. By default, the socket is located in
`/tmp/mongodb-<port>.sock`.

To connect to the socket file, specify the path in your MongoDB
connection string:

``` php
<?php
$m = new MongoClient("mongodb:///tmp/mongo-27017.sock");
?>
```

If you would like to authenticate against a database (as described
above) with a socket file, you must specify a port of *0* so that the
connection string parser can detect the end of the socket path.
Alternatively, you can use the constructor options.

``` php
<?php
$m = new MongoClient("mongodb://username:password@/tmp/mongo-27017.sock:0/foo");
?>
```

| Version | Description                            |
|---------|----------------------------------------|
| 1.0.9   | Added support for Unix Domain Sockets. |

Persistent Connections (version 1.3.0+)
---------------------------------------

All versions of the driver since 1.3.0 utilize persistent connections to
minimize the number of connections made to each database server. These
connections are saved by the PHP worker process and may be reused
between multiple requests.

Before connecting to a database server, the driver will create a hash
for the connection based on its host, port, replica set name (if any),
any authentication credentials (e.g. username, password, database), and
the process ID. If a connection already exists for that hash, it will be
used in lieu of creating a new connection associated with that hash.
<span class="function">MongoClient::getConnections</span> may be used to
retrieve info about each persistent connection. Consider the following
program:

``` php
<?php

$m1 = new MongoClient('mongodb://localhost');
$m2 = new MongoClient('mongodb://localhost');
$m3 = new MongoClient('mongodb://user:pw@localhost');
$m4 = new MongoClient('mongodb://127.0.0.1');
$m5 = new MongoClient('mongodb://rs1.local:30017,rs2.local:30018/?replicaSet=rs');
$m6 = new MongoClient('mongodb://sharding.local:40017');

foreach (MongoClient::getConnections() as $conn) {
    echo $conn['hash'], "\n";
}

?>
```

The above example will output something similar to:

    localhost:27017;-;X;15487
    localhost:27017;-;admin/user/c56c…8bbc;15487
    127.0.0.1:27017;-;X;15487
    rs1.local:30017;rs;X;15487
    rs2.local:30018;rs;X;15487
    sharding.local:40017;-;X;15487

In this example *$m1* and *$m2* have the same hash and share a
persistent connection. Connections for each other MongoClient instance
hash to unique values and use their own sockets. Note that "localhost"
and "127.0.0.1" do not share the same hash; DNS resolution is not taken
into account.

Connection Pooling (version 1.2.0-1.2.12 \*only\*)
--------------------------------------------------

> **Note**:
>
> This section is no longer relevant as of the 1.3.0 release of the
> driver and only serves as a historical information on how the pooling
> used to work.
>
> The latest versions of the driver have no concept of pooling anymore
> and will maintain only one connection per process, for each connection
> type (ReplicaSet/standalone/mongos), for each credentials combination.

Creating connections is one of the most heavyweight things that the
driver does. It can take hundreds of milliseconds to set up a connection
correctly, even on a fast network. Thus, the driver tries to minimize
the number of new connections created by reusing connections from a
pool.

When a user creates a new instance of <span
class="classname">MongoClient</span>, all necessary connections will be
taken from their pools (replica sets may require multiple connections,
one for each member of the set). When the <span
class="classname">MongoClient</span> instance goes out of scope, the
connections will be returned to the pool. When the PHP process exits,
all connections in the pools will be closed.

"Why do I have so many open connections?"
-----------------------------------------

Connection pools can generate a large number of connections. This is
expected and, using a little arithmetic, you can figure out how many
connections will be created. There are three factors in determining the
total number of connections:

-   *connections\_per\_pool*

    Each connection pool will create, by default, an unlimited number of
    connections. One might assume that this is a problem: if it can
    create an unlimited number of connections, couldn't it create
    thousands and the server would run out of file descriptors? In
    practice, this is unlikely, as unused connections are returned to
    the pool to be used later, so future connections will use the same
    connection instead of creating a new one. Unless you create
    thousands of connections at once without letting any go out of
    scope, the number of connections open should stay at a reasonable
    number.

    You can see how many connections you have in a pool using the <span
    class="function">MongoPool::info</span> function. Add up the "in
    use" and "in pool" fields for a given server. That is the total
    number of connections for that pool.

-   *pools\_per\_process*

    Each MongoDB server address you're connecting to gets its own
    connection pool. For example, if your local hostname is
    "example.net", connecting to "example.net:27017", "localhost:27017",
    and "/tmp/mongodb-27017.sock" will create three connection pools.
    You can see how many connection pools you have open using <span
    class="function">MongoPool::info</span>.

-   *processes*

    Each PHP process has a separate set of pools. PHP-FPM and Apache
    generally create between 6 and a couple of dozen PHP worker
    children. Check your settings to see what the max number of PHP
    processes is that can be spawned.

    If you are using PHP-FPM, estimating the number of connections can
    be tricky because it will spawn more PHP-FPM workers under heavy
    load. To be on the safe side, look at the *max\_children* parameter
    or add up *spare\_servers* + *start\_servers* (choose whichever
    number is higher). That will indicate how many PHP processes (i.e.
    sets of pools) you should plan for.

The three variables above can be multiplied together to give the max
number of connections expected: *connections\_per\_pool* \*
*pools\_per\_process* \* *processes*. Note that *connections\_per\_pool*
can be different for different pools, so *connections\_per\_pool* should
be the max.

For example, suppose we're getting 30 connections per pool, 10 pools per
PHP process, and 128 PHP processes. Then we can expect 38400 connections
from this machine. Thus, we should set this machine's file descriptor
limit to be high enough to handle all of these connections or it may run
out of file descriptors.

See <span class="classname">MongoPool</span> for more information on
connection pooling.

Manually Persistent Connections (version up to 1.1.4 \*only\*)
--------------------------------------------------------------

> **Note**:
>
> This section is not relevant for 1.2.0+. In 1.2.0+, connections are
> always persistent and managed automatically by the driver. If you are
> using a 1.2.x release (but not 1.3.x or later), see <span
> class="classname">MongoPool</span> for more information on pooling.

Creating new connection to the database is very slow. To minimize the
number of connections that you need to make, you can use persistent
connections. A persistent connection is saved by PHP, so you can use the
same connection for multiple requests.

For example, this simple program connects to the database 1000 times:

``` php
<?php

for ($i=0; $i<1000; $i++) {
  $m = new MongoClient();
}

?>
```

It takes approximately 18 seconds to execute. If we change it to use a
persistent connection:

``` php
<?php

for ($i=0; $i<1000; $i++) {
  $m = new MongoClient("localhost:27017", array("persist" => "x"));
}

?>
```

...it takes less than .02 seconds to execute, as it only makes one
database connection.

Persistent connections need an identifier string (which is "x" in the
above example) to uniquely identify them. For a persistent connection to
be used, the hostname, port, persist string, and authentication
credentials (username, password and database, if given) must match an
existing persistent connection. Otherwise, a new connection will be
created with this identifying information.

Persistent connections are *highly recommended* and should always be
used in production unless there is a compelling reason not to. Most of
the reasons that they are not recommended for relational databases are
irrelevant to MongoDB.

The PHP MongoDB extension provides
<a href="/context.html" class="link">Stream Context Support</a> using
the <a href="/context/mongodb.html" class="link">mongodb</a> context.

A stream context must be created with <span
class="function">stream\_context\_create</span> and passed to the <span
class="methodname">MongoClient::\_\_construct</span> before the actual
connection to MongoDB is made. It is not possible to apply a stream
context to already created streams.

Additional context options and parameters, such as
<a href="/context/ssl.html" class="link">ssl</a> and
<a href="/context/params.html" class="link">notification parameters</a>,
are also supported.

The MongoDB context options provide a rich interface to log network
traffic between the driver and the MongoDB servers. This interface can
be used to provide query logging, profiler, debuggers, or anything that
would need to inspect the underlaying commands and protocol options.

-   <a href="/context/ssl.html" class="xref">SSL context options</a>
-   <a href="/context/socket.html" class="xref">Socket context options</a>
-   <a href="/context/params.html" class="xref">Context parameters</a>

log\_cmd\_delete
================

Callback When Deleting Documents

### Description

<span class="methodname">log\_cmd\_delete</span> ( <span
class="methodparam"><span class="type">array</span> `$server`</span> ,
<span class="methodparam"><span class="type">array</span>
`$writeOptions`</span> , <span class="methodparam"><span
class="type">array</span> `$deleteOptions`</span> , <span
class="methodparam"><span class="type">array</span>
`$protocolOptions`</span> )

A <span class="type">callable</span> function, used by the
<a href="/context/mongodb.html#context.mongodb.log-cmd-delete" class="link">log_cmd_delete context option</a>,
when deleteing a document

> **Note**:
>
> This is *not* a real function, only a prototype of how the function
> should be.

### Parameters

`server`  
An array containing the basic information about the server that was
picked.

| key                | value                                                                |
|--------------------|----------------------------------------------------------------------|
| hash               | server hash, example: *localhost:27017;-;X;56052*                    |
| type               | Node type (primary/secondary/mongos/arbiter): *2*                    |
| max\_bson\_size    | The maximum BSON Size over the wire this node accepts: *16777216*    |
| max\_message\_size | The maximum Message Size over the wire this node accepts: *48000000* |
| request\_id        | The request identifier for this message: *42*                        |

`writeOptions`  
| key          | value                                                                                               |
|--------------|-----------------------------------------------------------------------------------------------------|
| ordered      | boolean, if the operation (in case of batch operation) must be executed sequentually (ordered=true) |
| writeConcern | An array of writeConcern options (see below)                                                        |

| key      | value                                                                                    |
|----------|------------------------------------------------------------------------------------------|
| fsync    | boolean, force flushing to disk before returning                                         |
| j        | boolean, force journal write before returning                                            |
| wtimeout | integer, milliseconds, maximum time the primary is allowed to wait to verify replication |
| w        | integer=server count, or string=replication-tag                                          |

`deleteOptions`  
| key   | value                                                 |
|-------|-------------------------------------------------------|
| limit | integer, 1 or 0. If 0, delete all matching documents. |
| q     | Array, the search criteria                            |

`protocolOptions`  
| key             | value                                                                       |
|-----------------|-----------------------------------------------------------------------------|
| message\_length | The total size (in bytes) of the encoded message being sent over the wire   |
| request\_id     | The request identifier for this message: *42*                               |
| namespace       | The MongoDB namespace used for the protocol message *dbname.collectionname* |

### Changelog

| Version          | Description                                     |
|------------------|-------------------------------------------------|
| PECL mongo 1.5.0 | Only available when connected to MongoDB 2.6.0+ |

log\_cmd\_insert
================

Callback When Inserting Documents

### Description

<span class="methodname">log\_cmd\_insert</span> ( <span
class="methodparam"><span class="type">array</span> `$server`</span> ,
<span class="methodparam"><span class="type">array</span>
`$document`</span> , <span class="methodparam"><span
class="type">array</span> `$writeOptions`</span> , <span
class="methodparam"><span class="type">array</span>
`$protocolOptions`</span> )

A <span class="type">callable</span> function, used by the
<a href="/context/mongodb.html#context.mongodb.log-cmd-insert" class="link">log_cmd_insert context option</a>,
when inserting a document

> **Note**:
>
> This is *not* a real function, only a prototype of how the function
> should be.

### Parameters

`server`  
An array containing the basic information about the server that was
picked.

| key                | value                                                                |
|--------------------|----------------------------------------------------------------------|
| hash               | server hash, example: *localhost:27017;-;X;56052*                    |
| type               | Node type (primary/secondary/mongos/arbiter): *2*                    |
| max\_bson\_size    | The maximum BSON Size over the wire this node accepts: *16777216*    |
| max\_message\_size | The maximum Message Size over the wire this node accepts: *48000000* |
| request\_id        | The request identifier for this message: *42*                        |

`document`  
The document that has been prepared to be inserted

`writeOptions`  
| key          | value                                                                                               |
|--------------|-----------------------------------------------------------------------------------------------------|
| ordered      | boolean, if the operation (in case of batch operation) must be executed sequentually (ordered=true) |
| writeConcern | An array of writeConcern options (see below)                                                        |

| key      | value                                                                                    |
|----------|------------------------------------------------------------------------------------------|
| fsync    | boolean, force flushing to disk before returning                                         |
| j        | boolean, force journal write before returning                                            |
| wtimeout | integer, milliseconds, maximum time the primary is allowed to wait to verify replication |
| w        | integer=server count, or string=replication-tag                                          |

`protocolOptions`  
| key             | value                                                                       |
|-----------------|-----------------------------------------------------------------------------|
| message\_length | The total size (in bytes) of the encoded message being sent over the wire   |
| request\_id     | The request identifier for this message: *42*                               |
| namespace       | The MongoDB namespace used for the protocol message *dbname.collectionname* |

### Changelog

| Version          | Description                                     |
|------------------|-------------------------------------------------|
| PECL mongo 1.5.0 | Only available when connected to MongoDB 2.6.0+ |

log\_cmd\_update
================

Callback When Updating Documents

### Description

<span class="methodname">log\_cmd\_update</span> ( <span
class="methodparam"><span class="type">array</span> `$server`</span> ,
<span class="methodparam"><span class="type">array</span>
`$writeOptions`</span> , <span class="methodparam"><span
class="type">array</span> `$updateOptions`</span> , <span
class="methodparam"><span class="type">array</span>
`$protocolOptions`</span> )

A <span class="type">callable</span> function, used by the
<a href="/context/mongodb.html#context.mongodb.log-cmd-update" class="link">log_cmd_update context option</a>,
when updateing a document

> **Note**:
>
> This is *not* a real function, only a prototype of how the function
> should be.

### Parameters

`server`  
An array containing the basic information about the server that was
picked.

| key                | value                                                                |
|--------------------|----------------------------------------------------------------------|
| hash               | server hash, example: *localhost:27017;-;X;56052*                    |
| type               | Node type (primary/secondary/mongos/arbiter): *2*                    |
| max\_bson\_size    | The maximum BSON Size over the wire this node accepts: *16777216*    |
| max\_message\_size | The maximum Message Size over the wire this node accepts: *48000000* |
| request\_id        | The request identifier for this message: *42*                        |

`writeOptions`  
| key          | value                                                                                               |
|--------------|-----------------------------------------------------------------------------------------------------|
| ordered      | boolean, if the operation (in case of batch operation) must be executed sequentually (ordered=true) |
| writeConcern | An array of writeConcern options (see below)                                                        |

| key      | value                                                                                    |
|----------|------------------------------------------------------------------------------------------|
| fsync    | boolean, force flushing to disk before returning                                         |
| j        | boolean, force journal write before returning                                            |
| wtimeout | integer, milliseconds, maximum time the primary is allowed to wait to verify replication |
| w        | integer=server count, or string=replication-tag                                          |

`updateOptions`  
| key    | value                                                                      |
|--------|----------------------------------------------------------------------------|
| multi  | Boolean, true if this update is allowed to update all matched criteria     |
| upsert | Boolean, true if the document should be created if criteria does not match |
| q      | Array, the search criteria                                                 |
| u      | Array, the new object/modifications                                        |

`protocolOptions`  
| key             | value                                                                       |
|-----------------|-----------------------------------------------------------------------------|
| message\_length | The total size (in bytes) of the encoded message being sent over the wire   |
| request\_id     | The request identifier for this message: *42*                               |
| namespace       | The MongoDB namespace used for the protocol message *dbname.collectionname* |

### Changelog

| Version          | Description                                     |
|------------------|-------------------------------------------------|
| PECL mongo 1.5.0 | Only available when connected to MongoDB 2.6.0+ |

log\_getmore
============

Callback When Retrieving Next Cursor Batch

### Description

<span class="methodname">log\_getmore</span> ( <span
class="methodparam"><span class="type">array</span> `$server`</span> ,
<span class="methodparam"><span class="type">array</span> `$info`</span>
)

A <span class="type">callable</span> function, used by the
<a href="/context/mongodb.html#context.mongodb.log-getmore" class="link">log_getmore context option</a>,
when executing a GET\_MORE operation.

> **Note**:
>
> This is *not* a real function, only a prototype of how the function
> should be.

### Parameters

`server`  
An array containing the basic information about the server that was
picked.

| key                | value                                                                |
|--------------------|----------------------------------------------------------------------|
| hash               | server hash, example: *localhost:27017;-;X;56052*                    |
| type               | Node type (primary/secondary/mongos/arbiter): *2*                    |
| max\_bson\_size    | The maximum BSON Size over the wire this node accepts: *16777216*    |
| max\_message\_size | The maximum Message Size over the wire this node accepts: *48000000* |
| request\_id        | The request identifier for this message: *42*                        |

`info`  
| key         | value                                                        |
|-------------|--------------------------------------------------------------|
| request\_id | integer, the driver request identifier                       |
| cursor\_id  | integer, the cursor identifier being used to fetch more data |
| batch\_size | integer, maximum number of documents being requested         |

log\_killcursor
===============

Callback When Executing KILLCURSOR operations

### Description

<span class="methodname">log\_killcursor</span> ( <span
class="methodparam"><span class="type">array</span> `$server`</span> ,
<span class="methodparam"><span class="type">array</span> `$info`</span>
)

A <span class="type">callable</span> function, used by the
<a href="/context/mongodb.html#context.mongodb.log-killcursor" class="link">log_killcursor context option</a>,
when reading a killcursor from MongoDB.

> **Note**:
>
> This is *not* a real function, only a prototype of how the function
> should be.

### Parameters

`server`  
An array containing the basic information about the server that was
picked.

| key                | value                                                                |
|--------------------|----------------------------------------------------------------------|
| hash               | server hash, example: *localhost:27017;-;X;56052*                    |
| type               | Node type (primary/secondary/mongos/arbiter): *2*                    |
| max\_bson\_size    | The maximum BSON Size over the wire this node accepts: *16777216*    |
| max\_message\_size | The maximum Message Size over the wire this node accepts: *48000000* |
| request\_id        | The request identifier for this message: *42*                        |

`info`  
| key        | value                                  |
|------------|----------------------------------------|
| cursor\_id | integer, the cursor identifier to kill |

log\_reply
==========

Callback When Reading the MongoDB reply

### Description

<span class="methodname">log\_reply</span> ( <span
class="methodparam"><span class="type">array</span> `$server`</span> ,
<span class="methodparam"><span class="type">array</span>
`$messageHeaders`</span> , <span class="methodparam"><span
class="type">array</span> `$operationHeaders`</span> )

A <span class="type">callable</span> function, used by the
<a href="/context/mongodb.html#context.mongodb.log-reply" class="link">log_reply context option</a>,
when reading a reply from MongoDB.

> **Note**:
>
> This is *not* a real function, only a prototype of how the function
> should be.

### Parameters

`server`  
An array containing the basic information about the server that was
picked.

| key                | value                                                                |
|--------------------|----------------------------------------------------------------------|
| hash               | server hash, example: *localhost:27017;-;X;56052*                    |
| type               | Node type (primary/secondary/mongos/arbiter): *2*                    |
| max\_bson\_size    | The maximum BSON Size over the wire this node accepts: *16777216*    |
| max\_message\_size | The maximum Message Size over the wire this node accepts: *48000000* |
| request\_id        | The request identifier for this message: *42*                        |

`messageHeaders`  
| key          | value                                                                |
|--------------|----------------------------------------------------------------------|
| length       | integer, bytes, message reply length                                 |
| request\_id  | integer, the server request identifier                               |
| response\_id | integer, the driver request identifier this message is a response of |
| opcode       | integer, the opcode id                                               |

`operationHeaders`  
| key        | value                                                                                      |
|------------|--------------------------------------------------------------------------------------------|
| flags      | integer, bitmask of protocol flags                                                         |
| cursor\_id | integer, ID of the cursor created on the server (0 if none created, or its been exhausted) |
| start      | The starting offset of this cursor                                                         |
| returned   | integer, how many documents are returned in this trip                                      |

### See Also

-   The
    <a href="https://docs.mongodb.com/meta-driver/latest/legacy/mongodb-wire-protocol/" class="link external">» OP_REPLY definition in the Wire Protocol</a>

log\_write\_batch
=================

Callback When Writing Batches

### Description

<span class="methodname">log\_write\_batch</span> ( <span
class="methodparam"><span class="type">array</span> `$server`</span> ,
<span class="methodparam"><span class="type">array</span>
`$writeOptions`</span> , <span class="methodparam"><span
class="type">array</span> `$batch`</span> , <span
class="methodparam"><span class="type">array</span>
`$protocolOptions`</span> )

A <span class="type">callable</span> function, used by the
<a href="/context/mongodb.html#context.mongodb.log-write-batch" class="link">log_write_batch context option</a>,
when executing a batch operation.

> **Note**:
>
> This is *not* a real function, only a prototype of how the function
> should be.

### Parameters

`server`  
An array containing the basic information about the server that was
picked.

| key                | value                                                                |
|--------------------|----------------------------------------------------------------------|
| hash               | server hash, example: *localhost:27017;-;X;56052*                    |
| type               | Node type (primary/secondary/mongos/arbiter): *2*                    |
| max\_bson\_size    | The maximum BSON Size over the wire this node accepts: *16777216*    |
| max\_message\_size | The maximum Message Size over the wire this node accepts: *48000000* |
| request\_id        | The request identifier for this message: *42*                        |

`writeOptions`  
| key          | value                                                                                               |
|--------------|-----------------------------------------------------------------------------------------------------|
| ordered      | boolean, if the operation (in case of batch operation) must be executed sequentually (ordered=true) |
| writeConcern | An array of writeConcern options (see below)                                                        |

| key      | value                                                                                    |
|----------|------------------------------------------------------------------------------------------|
| fsync    | boolean, force flushing to disk before returning                                         |
| j        | boolean, force journal write before returning                                            |
| wtimeout | integer, milliseconds, maximum time the primary is allowed to wait to verify replication |
| w        | integer=server count, or string=replication-tag                                          |

`batch`  
Array, the actual batch operation.

`protocolOptions`  
| key             | value                                                                       |
|-----------------|-----------------------------------------------------------------------------|
| message\_length | The total size (in bytes) of the encoded message being sent over the wire   |
| request\_id     | The request identifier for this message: *42*                               |
| namespace       | The MongoDB namespace used for the protocol message *dbname.collectionname* |

### Changelog

| Version          | Description                                     |
|------------------|-------------------------------------------------|
| PECL mongo 1.5.0 | Only available when connected to MongoDB 2.6.0+ |

**Table of Contents**

-   [log\_cmd\_delete](/book/mongo.html#log_cmd_delete) — Callback When
    Deleting Documents
-   [log\_cmd\_insert](/book/mongo.html#log_cmd_insert) — Callback When
    Inserting Documents
-   [log\_cmd\_update](/book/mongo.html#log_cmd_update) — Callback When
    Updating Documents
-   [log\_getmore](/book/mongo.html#log_getmore) — Callback When
    Retrieving Next Cursor Batch
-   [log\_killcursor](/book/mongo.html#log_killcursor) — Callback When
    Executing KILLCURSOR operations
-   [log\_reply](/book/mongo.html#log_reply) — Callback When Reading the
    MongoDB reply
-   [log\_write\_batch](/book/mongo.html#log_write_batch) — Callback
    When Writing Batches

Writes
======

Updating Nested Objects
-----------------------

Suppose we wish to change the name of a comment's author in this
document:

``` javascript
{ 
    "_id" : ObjectId("4b06c282edb87a281e09dad9"), 
    "content" : "this is a blog post.",
    "comments" : 
    [
        {
            "author" : "Mike",
            "comment" : "I think that blah blah blah...",
        },
        {
            "author" : "John",
            "comment" : "I disagree."
        }
    ]
}
```

In order to change an inner field, we use $set (so that all of the other
fields are not removed!) with the index of comment to change:

``` php
<?php

$blog->update($criteria, array('$set' => array("comments.1" => array("author" => "Jim"))));

?>
```

The Positional Operator
-----------------------

The positional operator *$* is useful for updating objects that are in
arrays. In the example above, for instance, suppose that we did not know
the index of the comment that we needed to change, merely that we needed
to change "John" to "Jim". We can use *$* to do so.

``` php
<?php

$blog->update(
    array('comments.author' => 'John'), 
    array('$set' => array('comments.$.author' => 'Jim')));

?>
```

Querying
========

All queries (reads and writes) are only sent to the primary member of a
replica set by default. This is however easily configurable by using the
<a href="/book/mongo.html#Read%20Preferences" class="link">Read Preferences</a>
which allow you to set some generic read preferences (such as allowing
secondary reads of the nearest server), and also provide ways to
specifically target a server in a specific country, datacenter, or even
hardware, by the use of
<a href="/book/mongo.html#Tag%20Sets" class="link">replica set tag sets</a>.

Read preferences can be configured at every level of the driver:

-   As a query parameter or option to <span
    class="methodname">MongoClient::\_\_construct</span>
-   Specifically by calling <span
    class="methodname">MongoClient::setReadPreference</span>
-   At the database level with <span
    class="methodname">MongoDB::setReadPreference</span>
-   At the collection level with <span
    class="methodname">MongoCollection::setReadPreference</span>
-   At the cursor level with <span
    class="methodname">MongoCursor::setReadPreference</span> or <span
    class="methodname">MongoCommandCursor::setReadPreference</span>

Each class inherits its read preference setting from the "parent"
context.

**Example \#1 Inheriting read preferences from the database level down
to the cursor**

``` php
<?php
$db->setReadPreference(MongoClient::RP_SECONDARY_PREFERRED);
$c = $db->myCollection;

$cursor = $c->find();
?>
```

In this example, the query will be executed against a secondary. The
collection inherits **`MongoClient::RP_SECONDARY_PREFERRED`** from the
database and the cursor inherits it from the collection.

Each instance of <span class="classname">MongoClient</span> chooses its
own secondary using the available secondary with the lowest ping time.
So, if we had a PHP client in Europe and one in Australia and we had one
secondary in each of these data centers, we could do:

``` php
<?php
$options = array("replicaSet" => "setName", "readPreference" => MongoClient::RP_SECONDARY_PREFERRED);

// on the Australian client
$m = new MongoClient("mongodb://primary,australianhost.secondary,europeanhost.secondary", $options);
$cursor = $m->foo->bar->find();
$cursor->getNext();
echo "Reading from: ", $cursor->info()["server"], "\n";

// on the European client
$m = new MongoClient("mongodb://primary,australianhost.secondary,europeanhost.secondary", $options);
$cursor = $m->foo->bar->find();
$cursor->getNext();
echo "Reading from: ", $cursor->info()["server"], "\n";
?>
```

The above example will output something similar to:

    Reading from: australianHost
    Reading from: europeanHost

Note that we have to do a query before a secondary is chosen:
secondaries are chosen lazily by the driver, and for each query
separately.

You can see what the driver thinks is the current status of the set
members by running <span class="methodname">MongoClient::getHosts</span>
or <span class="methodname">MongoClient::getConnections</span>.

If no secondary is readable, the driver will send reads to the primary
as we specified **`MongoClient::RP_SECONDARY_PREFERRED`** which will
fallback to execute a query on a primary if no secondaries are
available. A server is considered readable if its state is 2 (SECONDARY)
and its health is 1. You can check this with <span
class="methodname">MongoClient::getHosts</span> and <span
class="methodname">MongoClient::getConnections</span>.

Writes are always sent to the primary—and by default all reads are sent
to the primary too.

Every object inserted is automatically assigned a unique *\_id* field,
which is often a useful field to use in queries. This works similarly to
"get last insert ID" functionality, except that the *\_id* is chosen by
the *client*.

Suppose that we wish to find the document we just inserted. Inserting
adds an *\_id* field to the document, so we can query by that:

``` php
<?php
$person = array("name" => "joe");

$people->insert($person);

// now $joe has an _id field
$joe = $people->findOne(array("_id" => $person['_id']));
?>
```

Unless the user has specified otherwise, the *\_id* field is a <span
class="classname">MongoId</span>. The most common mistake is attempting
to use a string to match a <span class="classname">MongoId</span>. Keep
in mind that these are two different datatypes, and will not match each
other in the same way that the string "array()" is not the same as an
empty array. For example:

``` php
<?php
$person = array("name" => "joe");

$people->insert($person);

// convert the _id to a string
$pid = $person['_id'] . "";

// FAILS - $pid is a string, not a MongoId
$joe = $people->findOne(array("_id" => $pid));
?>
```

Arrays are special in a couple ways. First, there are two types that
MongoDB uses: "normal" arrays and associative arrays. Associative arrays
can have any mix of key types and values. "Normal" arrays are defined as
arrays with ascending numeric indexes starting at 0 and increasing by
one for each element. These are, typically, just your usual PHP array.

For instance, if you want to save a list of awards in a document, you
could say:

``` php
<?php

$collection->save(array("awards" => array("gold", "silver", "bronze")));

?>
```

Queries can reach into arrays to search for elements. Suppose that we
wish to find all documents with an array element of a given value. For
example, documents with a "gold" award, such as:

    { "_id" : ObjectId("4b06c282edb87a281e09dad9"), "awards" : ["gold", "silver", "bronze"]}

This can be done with a simple query, ignoring the fact that "awards" is
an array:

``` php
<?php

  $cursor = $collection->find(array("awards" => "gold"));

?>
```

Suppose we are querying for a more complex object, if each element of
the array were an object itself, such as:

    {
         "_id" : ObjectId("4b06c282edb87a281e09dad9"),
         "awards" :
         [
            {
                "first place" : "gold"
            },
            {
                "second place" : "silver"
            },
            {
                "third place" :  "bronze"
            }
         ]
    }

Still ignoring that this is an array, we can use dot notation to query
the subobject:

``` php
<?php

$cursor = $collection->find(array("awards.first place" => "gold"));

?>
```

Notice that it doesn't matter that there is a space in the field name
(although it may be best not to use spaces, just to make things more
readable).

You can also use an array to query for a number of possible values. For
instance, if we were looking for documents "gold" or "copper", we could
do:

``` php
<?php

$cursor = $collection->find(array("awards" => array('$in' => array("gold", "copper"))));

?>
```

| Version | Description                                                                                                                                                       |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1.3.0   | Introduced the <a href="/book/mongo.html#Read%20Preferences" class="link">Read Preferences</a> framework to allow more fine grained control over secondary reads. |
| 1.3.0   | Deprecated *slaveOkay* usage, the alternative is <a href="/book/mongo.html#Read%20Preferences" class="link">Read Preferences</a>.                                 |
| 1.1.0   | Introduced the possiblity of routing reads to secondaries of replica set members using <span class="methodname">Mongo::setSlaveOkay</span>                        |

Updates
=======

Updates can be one of the most complicated operation available with
MongoDB. They combine a query with an action, modifying documents that
match the criteria. They are also extremely powerful, allowing you to
change documents quickly and replace them altogether. They are done
in-place (when possible) with little overhead.

Modifying vs. replacing documents
---------------------------------

There are two types of updates you can use: modifying updates and
replacing updates. Modifying updates contain $-operators and change
fields in a document: they might increment counters, push new elements
onto an array, or change the type of a field.

For example, a modifying update could add a new field to a document.

``` php
<?php
/** suppose documents look like:
 * {"username" : "...", "password" : "...", "email" : "..."}
 */
$coll->update(array("username" => "joe"), array('$set' => array("twitter" => "@joe4153")));

/** now the document will look like:
 * {"username" : "joe", "password" : "...", "email" : "...", "twitter" : "@joe4153"}
 */
?>
```

Replacing updates replace the entire matching document with a new
document. They are generally not as efficient as using $-modifiers, but
can be very usefully for complex operations or updates that can't be
expressed in terms of $-operators.

For example, a replacing update can completely change the structure of a
document.

``` php
<?php
/** suppose documents look like:
 * {"username" : "...", "password" : "...", "email" : "..."}
 */
$coll->update(array("username" => "joe"), array("userId" => 12345, "info" => array(
    "name" => "joe", "twitter" => "@joe4153", "email" => "..."), "likes" => array()));

/** now the document will look like:
 * {
 *     "userId" : 12345, 
 *     "info" : {
 *         "name" : "joe", 
 *         "twitter" : "@joe4153", 
 *         "email" : "..."
 *     },
 *     "likes" : []
 * }
 */
?>
```

Updating Nested Objects
-----------------------

Suppose we wish to change the name of a comment's author in this
document:

``` javascript
{ 
    "_id" : ObjectId("4b06c282edb87a281e09dad9"), 
    "content" : "this is a blog post.",
    "comments" : 
    [
        {
            "author" : "Mike",
            "comment" : "I think that blah blah blah...",
        },
        {
            "author" : "John",
            "comment" : "I disagree."
        }
    ]
}
```

In order to change an inner field, we use $set (so that all of the other
fields are not removed!) with the index of comment to change:

``` php
<?php

$blog->update($criteria, array('$set' => array("comments.1" => array("author" => "Jim"))));

?>
```

The Positional Operator
-----------------------

The positional operator *$* is useful for updating objects that are in
arrays. In the example above, for instance, suppose that we did not know
the index of the comment that we needed to change, merely that we needed
to change "John" to "Jim". We can use *$* to do so.

``` php
<?php

$blog->update(
    array("comments.author" => "John"), 
    array('$set' => array('comments.$.author' => "Jim")));

?>
```

Security
========

Request Injection Attacks
-------------------------

If you are passing *$\_GET* (or *$\_POST*) parameters to your queries,
make sure that they are cast to strings first. Users can insert
associative arrays in GET and POST requests, which could then become
unwanted $-queries.

A fairly innocuous example: suppose you are looking up a user's
information with the request *http://www.example.com?username=bob*. Your
application does the query *$collection-\>find(array("username" =\>
$\_GET\['username'\]))*.

Someone could subvert this by getting
*http://www.example.com?username\[$ne\]=foo*, which PHP will magically
turn into an associative array, turning your query into
*$collection-\>find(array("username" =\> array('$ne' =\> "foo")))*,
which will return all users not named "foo" (all of your users,
probably).

This is a fairly easy attack to defend against: make sure $\_GET and
$\_POST parameters are the type you expect before you send them to the
database (cast them to strings, in this case).

Note that this type of attack can be used with any databases interation
that locates a document, including updates, upserts, find-and-modifies,
and removes.

Thanks to
<a href="https://www.idontplaydarts.com/2010/07/mongodb-is-vulnerable-to-sql-injection-in-php-at-least/" class="link external">» Phil</a>
for pointing this out.

See
<a href="https://docs.mongodb.com/manual/security/" class="link external">» the main documentation</a>
for more information about SQL-injection-like issues with MongoDB.

Script Injection Attacks
------------------------

If you are using JavaScript, make sure that any variables that cross the
PHP- to-JavaScript boundry are passed in the *scope* field of <span
class="classname">MongoCode</span>, not interpolated into the JavaScript
string. This can come up when using <span
class="function">MongoDB::execute</span>, *$where* clauses, MapReduces,
group-bys, and any other time you may pass JavaScript into the database.

> **Note**:
>
> MapReduce ignore the *scope* field of <span
> class="classname">MongoCode</span>, but there is a *scope* option on
> the command that can be used instead.

For example, suppose we have some JavaScript to greet a user in the
database logs. We could do:

``` php
<?php

// don't do this!

$username = $_POST['username'];
$db->execute("print('Hello, $username!');");

?>
```

However, what if a malicious user passes in some JavaScript?

``` php
<?php

// don't do this!

// $username is set to "'); db.users.drop(); print('"
$db->execute("print('Hello, $username!');");

?>
```

Now MongoDB executes the JavaScript string *"print('Hello, ');
db.users.drop(); print('!');"*. This attack is easy to avoid: use
*scope* to pass variables from PHP to JavaScript:

``` php
<?php

$scope = array("user" => $username);
$db->execute(new MongoCode("print('Hello, '+user+'!');", $scope));

?>
```

This adds a variable *user* to the JavaScript scope. Now if someone
tries to send malicious code, MongoDB will harmlessly print *Hello, ');
db.dropDatabase(); print('!*.

Using *scope* helps prevent malicious input from being executed by the
database. However, you must make sure that your code does not turn
around and execute the input anyway! For example, never use the
JavaScript *eval* function on user input:

``` php
<?php

// don't do this!

// $jsShellInput is "db.users.drop();"
$scope = array("input" => $jsShellInput);
$db->execute(new MongoCode("eval(input);", $scope));

?>
```

Always use *scope* and never allow the database to execute user input as
code.

Troubleshooting
===============

If you're having trouble, there are lots of resources you can turn to.

-   IRC

    The official MongoDB IRC room is irc.freenode.net/\#mongodb. This is
    the fastest way to get help.

-   Mailing List

    <a href="https://groups.google.com/group/mongodb-user/" class="link external">» MongoDB's mailing list</a>
    is a good (and usually very fast) way to get answers to questions.

-   Bug Tracker

    Found a bug? Want a feature? Have a question? File it in the
    <a href="https://jira.mongodb.org/browse/PHP" class="link external">» PHP driver's bug tracker</a>.

You can make the driver log all kinds of error messages as
**`E_NOTICE`** level PHP error messages. Have a look at the <span
class="classname">MongoLog</span> for an example.

Running the Driver's Tests
==========================

The PECL package does not come with the tests, but they are available at
<a href="https://github.com/mongodb/mongo-php-driver-legacy" class="link external">» Github</a>.

.phpt Tests
-----------

.phpt tests are the standard way of testing PHP extensions. After
compiling the MongoDB driver with "make" you can then issue "make test"
to run the tests. These tests require MongoDB to be working, and hence,
you need to configure the test suite itself.

There is more information on running the tests in the contributing
guidelines on
<a href="https://github.com/mongodb/mongo-php-driver/blob/master/CONTRIBUTING.md#running-the-tests" class="link external">» GitHub</a>.

Reporting Errors
----------------

Please report any failures or errors in the
<a href="https://jira.mongodb.org/browse/PHP" class="link external">» bugtracker</a>.
There may be skipped tests, these are normal and can be ignored.

New tests are always welcome! Please feel free to contribute new tests
of any type testing any functionality.

Core Classes
============

**Table of Contents**

-   [MongoClient](/book/mongo.html#MongoClient) — The MongoClient class
    -   [MongoClient::close](/book/mongo.html#MongoClient::close) —
        Closes this connection
    -   [MongoClient::connect](/book/mongo.html#MongoClient::connect) —
        Connects to a database server
    -   [MongoClient::\_\_construct](/book/mongo.html#MongoClient::__construct)
        — Creates a new database connection object
    -   [MongoClient::dropDB](/book/mongo.html#MongoClient::dropDB) —
        Drops a database \[deprecated\]
    -   [MongoClient::\_\_get](/book/mongo.html#MongoClient::__get) —
        Gets a database
    -   [MongoClient::getConnections](/book/mongo.html#MongoClient::getConnections)
        — Return info about all open connections
    -   [MongoClient::getHosts](/book/mongo.html#MongoClient::getHosts)
        — Updates status for all associated hosts
    -   [MongoClient::getReadPreference](/book/mongo.html#MongoClient::getReadPreference)
        — Get the read preference for this connection
    -   [MongoClient::getWriteConcern](/book/mongo.html#MongoClient::getWriteConcern)
        — Get the write concern for this connection
    -   [MongoClient::killCursor](/book/mongo.html#MongoClient::killCursor)
        — Kills a specific cursor on the server
    -   [MongoClient::listDBs](/book/mongo.html#MongoClient::listDBs) —
        Lists all of the databases available
    -   [MongoClient::selectCollection](/book/mongo.html#MongoClient::selectCollection)
        — Gets a database collection
    -   [MongoClient::selectDB](/book/mongo.html#MongoClient::selectDB)
        — Gets a database
    -   [MongoClient::setReadPreference](/book/mongo.html#MongoClient::setReadPreference)
        — Set the read preference for this connection
    -   [MongoClient::setWriteConcern](/book/mongo.html#MongoClient::setWriteConcern)
        — Set the write concern for this connection
    -   [MongoClient::\_\_toString](/book/mongo.html#MongoClient::__toString)
        — String representation of this connection
-   [MongoDB](/book/mongo.html#MongoDB) — The MongoDB class
    -   [MongoDB::authenticate](/book/mongo.html#MongoDB::authenticate)
        — Log in to this database
    -   [MongoDB::command](/book/mongo.html#MongoDB::command) — Execute
        a database command
    -   [MongoDB::\_\_construct](/book/mongo.html#MongoDB::__construct)
        — Creates a new database
    -   [MongoDB::createCollection](/book/mongo.html#MongoDB::createCollection)
        — Creates a collection
    -   [MongoDB::createDBRef](/book/mongo.html#MongoDB::createDBRef) —
        Creates a database reference
    -   [MongoDB::drop](/book/mongo.html#MongoDB::drop) — Drops this
        database
    -   [MongoDB::dropCollection](/book/mongo.html#MongoDB::dropCollection)
        — Drops a collection \[deprecated\]
    -   [MongoDB::execute](/book/mongo.html#MongoDB::execute) — Runs
        JavaScript code on the database server \[deprecated\]
    -   [MongoDB::forceError](/book/mongo.html#MongoDB::forceError) —
        Creates a database error
    -   [MongoDB::\_\_get](/book/mongo.html#MongoDB::__get) — Gets a
        collection
    -   [MongoDB::getCollectionInfo](/book/mongo.html#MongoDB::getCollectionInfo)
        — Returns information about collections in this database
    -   [MongoDB::getCollectionNames](/book/mongo.html#MongoDB::getCollectionNames)
        — Gets an array of names for all collections in this database
    -   [MongoDB::getDBRef](/book/mongo.html#MongoDB::getDBRef) —
        Fetches the document pointed to by a database reference
    -   [MongoDB::getGridFS](/book/mongo.html#MongoDB::getGridFS) —
        Fetches toolkit for dealing with files stored in this database
    -   [MongoDB::getProfilingLevel](/book/mongo.html#MongoDB::getProfilingLevel)
        — Gets this database's profiling level
    -   [MongoDB::getReadPreference](/book/mongo.html#MongoDB::getReadPreference)
        — Get the read preference for this database
    -   [MongoDB::getSlaveOkay](/book/mongo.html#MongoDB::getSlaveOkay)
        — Get slaveOkay setting for this database
    -   [MongoDB::getWriteConcern](/book/mongo.html#MongoDB::getWriteConcern)
        — Get the write concern for this database
    -   [MongoDB::lastError](/book/mongo.html#MongoDB::lastError) —
        Check if there was an error on the most recent db operation
        performed
    -   [MongoDB::listCollections](/book/mongo.html#MongoDB::listCollections)
        — Gets an array of MongoCollection objects for all collections
        in this database
    -   [MongoDB::prevError](/book/mongo.html#MongoDB::prevError) —
        Checks for the last error thrown during a database operation
    -   [MongoDB::repair](/book/mongo.html#MongoDB::repair) — Repairs
        and compacts this database
    -   [MongoDB::resetError](/book/mongo.html#MongoDB::resetError) —
        Clears any flagged errors on the database
    -   [MongoDB::selectCollection](/book/mongo.html#MongoDB::selectCollection)
        — Gets a collection
    -   [MongoDB::setProfilingLevel](/book/mongo.html#MongoDB::setProfilingLevel)
        — Sets this database's profiling level
    -   [MongoDB::setReadPreference](/book/mongo.html#MongoDB::setReadPreference)
        — Set the read preference for this database
    -   [MongoDB::setSlaveOkay](/book/mongo.html#MongoDB::setSlaveOkay)
        — Change slaveOkay setting for this database
    -   [MongoDB::setWriteConcern](/book/mongo.html#MongoDB::setWriteConcern)
        — Set the write concern for this database
    -   [MongoDB::\_\_toString](/book/mongo.html#MongoDB::__toString) —
        The name of this database
-   [MongoCollection](/book/mongo.html#MongoCollection) — The
    MongoCollection class
    -   [MongoCollection::aggregate](/book/mongo.html#MongoCollection::aggregate)
        — Perform an aggregation using the aggregation framework
    -   [MongoCollection::aggregateCursor](/book/mongo.html#MongoCollection::aggregateCursor)
        — Execute an aggregation pipeline command and retrieve results
        through a cursor
    -   [MongoCollection::batchInsert](/book/mongo.html#MongoCollection::batchInsert)
        — Inserts multiple documents into this collection
    -   [MongoCollection::\_\_construct](/book/mongo.html#MongoCollection::__construct)
        — Creates a new collection
    -   [MongoCollection::count](/book/mongo.html#MongoCollection::count)
        — Counts the number of documents in this collection
    -   [MongoCollection::createDBRef](/book/mongo.html#MongoCollection::createDBRef)
        — Creates a database reference
    -   [MongoCollection::createIndex](/book/mongo.html#MongoCollection::createIndex)
        — Creates an index on the specified field(s) if it does not
        already exist
    -   [MongoCollection::deleteIndex](/book/mongo.html#MongoCollection::deleteIndex)
        — Deletes an index from this collection
    -   [MongoCollection::deleteIndexes](/book/mongo.html#MongoCollection::deleteIndexes)
        — Delete all indices for this collection
    -   [MongoCollection::distinct](/book/mongo.html#MongoCollection::distinct)
        — Retrieve a list of distinct values for the given key across a
        collection
    -   [MongoCollection::drop](/book/mongo.html#MongoCollection::drop)
        — Drops this collection
    -   [MongoCollection::ensureIndex](/book/mongo.html#MongoCollection::ensureIndex)
        — Creates an index on the specified field(s) if it does not
        already exist
    -   [MongoCollection::find](/book/mongo.html#MongoCollection::find)
        — Queries this collection, returning a MongoCursor for the
        result set
    -   [MongoCollection::findAndModify](/book/mongo.html#MongoCollection::findAndModify)
        — Update a document and return it
    -   [MongoCollection::findOne](/book/mongo.html#MongoCollection::findOne)
        — Queries this collection, returning a single element
    -   [MongoCollection::\_\_get](/book/mongo.html#MongoCollection::__get)
        — Gets a collection
    -   [MongoCollection::getDBRef](/book/mongo.html#MongoCollection::getDBRef)
        — Fetches the document pointed to by a database reference
    -   [MongoCollection::getIndexInfo](/book/mongo.html#MongoCollection::getIndexInfo)
        — Returns information about indexes on this collection
    -   [MongoCollection::getName](/book/mongo.html#MongoCollection::getName)
        — Returns this collection's name
    -   [MongoCollection::getReadPreference](/book/mongo.html#MongoCollection::getReadPreference)
        — Get the read preference for this collection
    -   [MongoCollection::getSlaveOkay](/book/mongo.html#MongoCollection::getSlaveOkay)
        — Get slaveOkay setting for this collection
    -   [MongoCollection::getWriteConcern](/book/mongo.html#MongoCollection::getWriteConcern)
        — Get the write concern for this collection
    -   [MongoCollection::group](/book/mongo.html#MongoCollection::group)
        — Performs an operation similar to SQL's GROUP BY command
    -   [MongoCollection::insert](/book/mongo.html#MongoCollection::insert)
        — Inserts a document into the collection
    -   [MongoCollection::parallelCollectionScan](/book/mongo.html#MongoCollection::parallelCollectionScan)
        — Returns an array of cursors to iterator over a full collection
        in parallel
    -   [MongoCollection::remove](/book/mongo.html#MongoCollection::remove)
        — Remove records from this collection
    -   [MongoCollection::save](/book/mongo.html#MongoCollection::save)
        — Saves a document to this collection
    -   [MongoCollection::setReadPreference](/book/mongo.html#MongoCollection::setReadPreference)
        — Set the read preference for this collection
    -   [MongoCollection::setSlaveOkay](/book/mongo.html#MongoCollection::setSlaveOkay)
        — Change slaveOkay setting for this collection
    -   [MongoCollection::setWriteConcern](/book/mongo.html#MongoCollection::setWriteConcern)
        — Set the write concern for this database
    -   [MongoCollection::toIndexString](/book/mongo.html#MongoCollection::toIndexString)
        — Converts keys specifying an index to its identifying string
    -   [MongoCollection::\_\_toString](/book/mongo.html#MongoCollection::__toString)
        — String representation of this collection
    -   [MongoCollection::update](/book/mongo.html#MongoCollection::update)
        — Update records based on a given criteria
    -   [MongoCollection::validate](/book/mongo.html#MongoCollection::validate)
        — Validates this collection
-   [MongoCursor](/book/mongo.html#MongoCursor) — The MongoCursor class
    -   [MongoCursor::addOption](/book/mongo.html#MongoCursor::addOption)
        — Adds a top-level key/value pair to a query
    -   [MongoCursor::awaitData](/book/mongo.html#MongoCursor::awaitData)
        — Sets whether this cursor will wait for a while for a tailable
        cursor to return more data
    -   [MongoCursor::batchSize](/book/mongo.html#MongoCursor::batchSize)
        — Limits the number of elements returned in one batch
    -   [MongoCursor::\_\_construct](/book/mongo.html#MongoCursor::__construct)
        — Create a new cursor
    -   [MongoCursor::count](/book/mongo.html#MongoCursor::count) —
        Counts the number of results for this query
    -   [MongoCursor::current](/book/mongo.html#MongoCursor::current) —
        Returns the current element
    -   [MongoCursor::dead](/book/mongo.html#MongoCursor::dead) — Checks
        if there are results that have not yet been sent from the
        database
    -   [MongoCursor::doQuery](/book/mongo.html#MongoCursor::doQuery) —
        Execute the query
    -   [MongoCursor::explain](/book/mongo.html#MongoCursor::explain) —
        Return an explanation of the query, often useful for
        optimization and debugging
    -   [MongoCursor::fields](/book/mongo.html#MongoCursor::fields) —
        Sets the fields for a query
    -   [MongoCursor::getNext](/book/mongo.html#MongoCursor::getNext) —
        Advances the cursor to the next result, and returns that result
    -   [MongoCursor::getReadPreference](/book/mongo.html#MongoCursor::getReadPreference)
        — Get the read preference for this query
    -   [MongoCursor::hasNext](/book/mongo.html#MongoCursor::hasNext) —
        Checks if there are any more elements in this cursor
    -   [MongoCursor::hint](/book/mongo.html#MongoCursor::hint) — Gives
        the database a hint about the query
    -   [MongoCursor::immortal](/book/mongo.html#MongoCursor::immortal)
        — Sets whether this cursor will timeout
    -   [MongoCursor::info](/book/mongo.html#MongoCursor::info) — Gets
        information about the cursor's creation and iteration
    -   [MongoCursor::key](/book/mongo.html#MongoCursor::key) — Returns
        the current result's \_id, or its index within the result set
    -   [MongoCursor::limit](/book/mongo.html#MongoCursor::limit) —
        Limits the number of results returned
    -   [MongoCursor::maxTimeMS](/book/mongo.html#MongoCursor::maxTimeMS)
        — Sets a server-side timeout for this query
    -   [MongoCursor::next](/book/mongo.html#MongoCursor::next) —
        Advances the cursor to the next result, and returns that result
    -   [MongoCursor::partial](/book/mongo.html#MongoCursor::partial) —
        If this query should fetch partial results from mongos if a
        shard is down
    -   [MongoCursor::reset](/book/mongo.html#MongoCursor::reset) —
        Clears the cursor
    -   [MongoCursor::rewind](/book/mongo.html#MongoCursor::rewind) —
        Returns the cursor to the beginning of the result set
    -   [MongoCursor::setFlag](/book/mongo.html#MongoCursor::setFlag) —
        Sets arbitrary flags in case there is no method available the
        specific flag
    -   [MongoCursor::setReadPreference](/book/mongo.html#MongoCursor::setReadPreference)
        — Set the read preference for this query
    -   [MongoCursor::skip](/book/mongo.html#MongoCursor::skip) — Skips
        a number of results
    -   [MongoCursor::slaveOkay](/book/mongo.html#MongoCursor::slaveOkay)
        — Sets whether this query can be done on a secondary
        \[deprecated\]
    -   [MongoCursor::snapshot](/book/mongo.html#MongoCursor::snapshot)
        — Use snapshot mode for the query
    -   [MongoCursor::sort](/book/mongo.html#MongoCursor::sort) — Sorts
        the results by given fields
    -   [MongoCursor::tailable](/book/mongo.html#MongoCursor::tailable)
        — Sets whether this cursor will be left open after fetching the
        last results
    -   [MongoCursor::timeout](/book/mongo.html#MongoCursor::timeout) —
        Sets a client-side timeout for this query
    -   [MongoCursor::valid](/book/mongo.html#MongoCursor::valid) —
        Checks if the cursor is reading a valid result
-   [MongoCursorInterface](/book/mongo.html#MongoCursorInterface) — The
    MongoCursorInterface interface
    -   [MongoCursorInterface::batchSize](/book/mongo.html#MongoCursorInterface::batchSize)
        — Limits the number of elements returned in one batch
    -   [MongoCursorInterface::dead](/book/mongo.html#MongoCursorInterface::dead)
        — Checks if there are results that have not yet been sent from
        the database
    -   [MongoCursorInterface::getReadPreference](/book/mongo.html#MongoCursorInterface::getReadPreference)
        — Get the read preference for this query
    -   [MongoCursorInterface::info](/book/mongo.html#MongoCursorInterface::info)
        — Gets information about the cursor's creation and iteration
    -   [MongoCursorInterface::setReadPreference](/book/mongo.html#MongoCursorInterface::setReadPreference)
        — Set the read preference for this query
    -   [MongoCursorInterface::timeout](/book/mongo.html#MongoCursorInterface::timeout)
        — Sets a client-side timeout for this query
-   [MongoCommandCursor](/book/mongo.html#MongoCommandCursor) — The
    MongoCommandCursor class
    -   [MongoCommandCursor::batchSize](/book/mongo.html#MongoCommandCursor::batchSize)
        — Limits the number of elements returned in one batch
    -   [MongoCommandCursor::\_\_construct](/book/mongo.html#MongoCommandCursor::__construct)
        — Create a new command cursor
    -   [MongoCommandCursor::createFromDocument](/book/mongo.html#MongoCommandCursor::createFromDocument)
        — Create a new command cursor from an existing command response
        document
    -   [MongoCommandCursor::current](/book/mongo.html#MongoCommandCursor::current)
        — Returns the current element
    -   [MongoCommandCursor::dead](/book/mongo.html#MongoCommandCursor::dead)
        — Checks if there are results that have not yet been sent from
        the database
    -   [MongoCommandCursor::getReadPreference](/book/mongo.html#MongoCommandCursor::getReadPreference)
        — Get the read preference for this command
    -   [MongoCommandCursor::info](/book/mongo.html#MongoCommandCursor::info)
        — Gets information about the cursor's creation and iteration
    -   [MongoCommandCursor::key](/book/mongo.html#MongoCommandCursor::key)
        — Returns the current result's index within the result set
    -   [MongoCommandCursor::next](/book/mongo.html#MongoCommandCursor::next)
        — Advances the cursor to the next result
    -   [MongoCommandCursor::rewind](/book/mongo.html#MongoCommandCursor::rewind)
        — Executes the command and resets the cursor to the start of the
        result set
    -   [MongoCommandCursor::setReadPreference](/book/mongo.html#MongoCommandCursor::setReadPreference)
        — Set the read preference for this command
    -   [MongoCommandCursor::timeout](/book/mongo.html#MongoCommandCursor::timeout)
        — Sets a client-side timeout for this command
    -   [MongoCommandCursor::valid](/book/mongo.html#MongoCommandCursor::valid)
        — Checks if the cursor is reading a valid result

**Warning**

This extension is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used.

The core classes are the most important part of the driver.

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\Driver\\Manager</span>

Introduction
------------

A connection manager for PHP and MongoDB.

This class is used to create and manage connections. A typical use is:

**Example \#1 <span class="classname">MongoClient</span> basic usage**

``` php
<?php

$m = new MongoClient(); // connect
$db = $m->foo; // get the database named "foo"

?>
```

See <span class="function">MongoClient::\_\_construct</span> and the
section on
<a href="/book/mongo.html#Connecting" class="link">connecting</a> for
more information about creating connections.

Class synopsis
--------------

**MongoClient**

<span class="ooclass"> class **MongoClient** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`MongoClient::VERSION` ;

<span class="modifier">const</span> <span class="type">string</span>
`MongoClient::DEFAULT_HOST` <span class="initializer"> =
"localhost"</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoClient::DEFAULT_PORT` <span class="initializer"> = 27017</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`MongoClient::RP_PRIMARY` <span class="initializer"> = "primary"</span>
;

<span class="modifier">const</span> <span class="type">string</span>
`MongoClient::RP_PRIMARY_PREFERRED` <span class="initializer"> =
"primaryPreferred"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`MongoClient::RP_SECONDARY` <span class="initializer"> =
"secondary"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`MongoClient::RP_SECONDARY_PREFERRED` <span class="initializer"> =
"secondaryPreferred"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`MongoClient::RP_NEAREST` <span class="initializer"> = "nearest"</span>
;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">boolean</span>
`$connected` <span class="initializer"> = **`FALSE`**</span> ;

<span class="modifier">public</span> <span class="type">string</span>
`$status` <span class="initializer"> = **`NULL`**</span> ;

<span class="modifier">protected</span> <span class="type">string</span>
`$server` <span class="initializer"> = **`NULL`**</span> ;

<span class="modifier">protected</span> <span
class="type">boolean</span> `$persistent` <span class="initializer"> =
**`NULL`**</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$server`<span
class="initializer"> = "mongodb://localhost:27017"</span></span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = array("connect" =\>
**`TRUE`**)</span></span> \[, <span class="methodparam"><span
class="type">array</span> `$driver_options`</span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">close</span> (\[ <span
class="methodparam"><span class="type">boolean\|string</span>
`$connection`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">connect</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">dropDB</span> ( <span class="methodparam"><span
class="type">mixed</span> `$db`</span> )

<span class="modifier">public</span> <span class="type">MongoDB</span>
<span class="methodname">\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$dbname`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getConnections</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getHosts</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getReadPreference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getWriteConcern</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">killCursor</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_hash`</span> , <span class="methodparam"><span
class="type">int\|MongoInt64</span> `$id`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">listDBs</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">selectCollection</span> ( <span
class="methodparam"><span class="type">string</span> `$db`</span> ,
<span class="methodparam"><span class="type">string</span>
`$collection`</span> )

<span class="modifier">public</span> <span class="type">MongoDB</span>
<span class="methodname">selectDB</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setWriteConcern</span> ( <span
class="methodparam"><span class="type">mixed</span> `$w`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$wtimeout`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

MongoClient Constants
---------------------

**`MongoClient::VERSION`**  
<span class="simpara"> PHP driver version. May be suffixed with "dev",
"+" or "-" if it is in-between versions. </span>

**`MongoClient::DEFAULT_HOST`**  
<span class="simpara"> Host to connect to if no host is given. </span>

**`MongoClient::DEFAULT_PORT`**  
<span class="simpara"> Port to connect to if no port is given. </span>

**`MongoClient::RP_PRIMARY`**  
<span class="simpara">
<a href="/book/mongo.html#Read%20Preferences" class="link">Read preference</a>
for the primary replica set member. </span>

**`MongoClient::RP_PRIMARY_PREFERRED`**  
<span class="simpara">
<a href="/book/mongo.html#Read%20Preferences" class="link">Read preference</a>
for preferring the primary replica set member. </span>

**`MongoClient::RP_SECONDARY`**  
<span class="simpara">
<a href="/book/mongo.html#Read%20Preferences" class="link">Read preference</a>
for a secondary replica set member. </span>

**`MongoClient::RP_SECONDARY_PREFERRED`**  
<span class="simpara">
<a href="/book/mongo.html#Read%20Preferences" class="link">Read preference</a>
for preferring a secondary replica set member. </span>

**`MongoClient::RP_NEAREST`**  
<span class="simpara">
<a href="/book/mongo.html#Read%20Preferences" class="link">Read preference</a>
for the nearest replica set member. </span>

Fields
------

`connected`  
This property will be set to **`TRUE`** if we have a open connection to
the database, **`FALSE`** otherwise. If the connection is to a replica
set, this property will only be **`TRUE`** if the driver has a
connection to a node matching the current read preference. This property
does not take authentication into account.

This property is *deprecated* since version 1.5.0.

`status`  
This property is no longer used and will be set to **`NULL`** In driver
versions 1.1.x and earlier, this may be set to a string value (e.g.
*"recycled"*, *"new"*) when persistent connections are used.

This property is *deprecated* since version 1.5.0.

See Also
--------

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <a href="/book/mongo.html#Write%20Concerns" class="xref"></a>
-   <a href="/book/mongo.html#Connecting" class="xref"></a>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/reference/connection-string/" class="link external">» connecting</a>

MongoClient::close
==================

Closes this connection

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::close</span> (\[ <span
class="methodparam"><span class="type">boolean\|string</span>
`$connection`</span> \] )

The <span class="function">MongoClient::close</span> method forcefully
closes a connection to the database, even if persistent connections are
being used. You should *never* have to do this under normal
circumstances.

### Parameters

`connection`  
If connection is not given, or **`FALSE`** then connection that would be
selected for writes would be closed. In a single-node configuration,
that is then the whole connection, but if you are connected to a replica
set, close() will *only* close the connection to the primary server.

If connection is **`TRUE`** then all connections as known by the
connection manager will be closed. This can include connections that are
not referenced in the connection string used to create the object that
you are calling close on.

If connection is a string argument, then it will only close the
connection identified by this hash. Hashes are identifiers for a
connection and can be obtained by calling <span
class="function">MongoClient::getConnections</span>.

### Return Values

Returns if the connection was successfully closed.

### Examples

**Example \#1 <span class="function">MongoClient::close</span> example**

This example demonstrates how to selectively close all connections for
secondaries only.

``` php
<?php
// Connect to a replicaset
$a = new MongoClient("mongodb://whisky:13000/?replicaset=seta");

$connections = $a->getConnections();

foreach ( $connections as $con )
{
    // Loop over all the connections, and when the type is "SECONDARY"
    // we close the connection
    if ( $con['connection']['connection_type_desc'] == "SECONDARY" )
    {
        echo "Closing '{$con['hash']}': ";
        $closed = $a->close( $con['hash'] );
        echo $closed ? "ok" : "failed", "\n";
    }
}
?>
```

The above example will output:

    Closing 'whisky:13001;X;4948': ok

### Changelog

| Version          | Description                                                                                                                                                                                                                                                                                                                            |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.3.0 | The `connection` parameter to this function was added in 1.3.0. Before that, only the write connection would be closed by this method.                                                                                                                                                                                                 |
| PECL mongo 1.2.0 | Before version 1.2.0 the driver would not use persistent connections by default, and all connections would be closed as soon as a MongoDB connection went out if scope. Since version 1.2.0 this is no longer the case and it is a bad idea to call close as you might end up overloading the server with connections under high load. |

### See Also

-   <span class="function">MongoClient::getConnections</span>

MongoClient::connect
====================

Connects to a database server

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::connect</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

If the connection was successful.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
fails to connect to the database.

MongoClient::\_\_construct
==========================

Creates a new database connection object

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\Driver\\Manager::\_\_construct</span>

### Description

<span class="modifier">public</span> <span
class="methodname">MongoClient::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$server`<span
class="initializer"> = "mongodb://localhost:27017"</span></span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = array("connect" =\>
**`TRUE`**)</span></span> \[, <span class="methodparam"><span
class="type">array</span> `$driver_options`</span> \]\]\] )

If no parameters are passed, this connects to "localhost:27017" (or
whatever was specified in php.ini for
<a href="/book/mongo.html#" class="link">mongo.default_host</a> and
<a href="/book/mongo.html#" class="link">mongo.default_port</a>).

`server` should have the form:

``` txt
mongodb://[username:password@]host1[:port1][,host2[:port2:],...]/db
```

The connection string always starts with *mongodb://*, to indicate it is
a connection string in this form.

If *username* and *password* are specified, the constructor will attempt
to authenticate the connection with the database before returning.
Username and password are optional and must be followed by an *@*, if
specified.

At least one host must be given (port optional, always defaulting to
27017) and as many hosts as desired may be connected to. Host names are
comma-separated and the constructor will return successfully if it
connected to at least one host. If it could not connect to any of the
hosts, it will throw a <span
class="classname">MongoConnectionException</span>. Please see the
<a href="/book/mongo.html#Replica%20Sets" class="link">Replica Sets</a>
section for information on how to connect to Replica Sets.

If you specified a username and password, you may specify a database to
authenticate with. If *db* is not specified, "admin" will be used.

An optional query string may be used to specify extra options. The same
options are supported through the `options` array as well, and are
therefore redescribed there. See the
<a href="" class="link">examples below</a> on how to set those options.

One part of the options governs how the driver reads from secondary
nodes in a replica set environment. Extra information on how these read
preferences work is available as well through the
<a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
documentation page.

### Parameters

`server`  
The server name.

`options`  
An array of options for the connection. Currently available options
include:

-   *"authMechanism"*

    Available mechanisms are:

    | authMechanism | Description                                                                                                                                              | Availability                                                                                      |
    |---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
    | MONGODB-CR    | Authenticate using Challenge Response mechanism. This is the default value.                                                                              | All MongoDB versions                                                                              |
    | MONGODB-X509  | Authenticates using X509 certificates                                                                                                                    | MongoDB 2.6. Only available when <a href="/book/openssl.html" class="xref">OpenSSL</a> is enabled |
    | PLAIN         | Authenticates using unencrypted plain username+password. Must be used over SSL connections. Generally used by MongoDB to login via 3rd party LDAP server | MongoDB Enterprise 2.4. The Driver must be compiled against CyrusSASL2                            |
    | GSSAPI        | Authenticates via kerberos systems                                                                                                                       | MongoDB Enterprise 2.4. The Driver must be compiled against CyrusSASL2                            |
    | SCRAM-SHA-1   | Authenticates using SCRAM-SHA-1                                                                                                                          | MongoDB 3.0.                                                                                      |

-   *"authSource"*

    Should be set to the database name where the user is defined it.

-   *"connect"*

    If the constructor should connect before returning. Default is
    **`TRUE`**. When set to **`FALSE`** the driver will *automatically*
    connect to the server whenever it is necessary to do a query.
    Alternatively, you can run <span
    class="function">MongoClient::connect</span> manually.

    **Warning**
    This option is not supported through the connection string.

-   *"connectTimeoutMS"*

    How long a connection can take to be opened before timing out in
    milliseconds. Defaults to *60000* (60 seconds).

    If *-1* is specified, no connection timeout will be applied and PHP
    will use
    <a href="/filesystem/setup.html#" class="link">default_socket_timeout</a>.

-   *"db"*

    The database to authenticate against can be specified here, instead
    of including it in the host list. This overrides a database given in
    the host list.

-   *"fsync"*

    When *"fsync"* is set, all write operations will block until the
    database has flushed the changes to disk. This makes the write
    operations slower, but it guarantees that writes have succeeded and
    that the operations can be recovered in case of total system
    failure.

    If the MongoDB server has journaling enabled, this option is
    identical to *"journal"*. If journaling is not enabled, this option
    ensures that write operations will be synced to database files on
    disk.

    > **Note**: <span class="simpara"> If journaling is enabled, users
    > are strongly encouraged to use the *"journal"* option instead of
    > *"fsync"*. Do not use *"fsync"* and *"journal"* simultaneously, as
    > that will result in an error. </span>

-   *"journal"*

    When *"journal"* is set, all write operations will block until the
    database has flushed the changes to the journal on disk. This makes
    the write operations slower, but it guarantees that writes have
    succeeded and that the operations can be recovered in case of total
    system failure.

    > **Note**: <span class="simpara"> If this option is used and
    > journaling is disabled, MongoDB 2.6+ will raise an error and the
    > write will fail; older server versions will simply ignore the
    > option. </span>

-   *"gssapiServiceName"*

    Sets the
    <a href="https://docs.mongodb.com/manual/core/kerberos/#kerberos-service-principal" class="link external">» Kerberos service principal</a>.
    Only applicable when authMechanism=GSSAPI. Defaults to "mongodb".

-   *"password"*

    The password can be specified here, instead of including it in the
    host list. This is especially useful if a password has a "@" in it.
    This overrides a password set in the host list.

-   *"readPreference"*

    Specifies the read preference type. Read preferences provide you
    with control from which secondaries data can be read from.

    Allowed values are: **`MongoClient::RP_PRIMARY`**,
    **`MongoClient::RP_PRIMARY_PREFERRED`**,
    **`MongoClient::RP_SECONDARY`**,
    **`MongoClient::RP_SECONDARY_PREFERRED`** and
    **`MongoClient::RP_NEAREST`**.

    See the documentation on
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    for more information.

-   *"readPreferenceTags"*

    Specifies the read preference tags as an array of strings. Tags can
    be used in combination with the *readPreference* option to further
    control which secondaries data might be read from.

    See the documentation on
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    for more information.

-   *"replicaSet"*

    The name of the replica set to connect to. If this is given, the
    primary will be automatically be determined. This means that the
    driver may end up connecting to a server that was not even listed.
    See the replica set example below for details.

-   *"secondaryAcceptableLatencyMS"*

    When reading from a secondary (using ReadPreferences), do not read
    from secondaries known to be more then
    *secondaryAcceptableLatencyMS* away from us. Defaults to *15*

-   *"socketTimeoutMS"*

    How long a socket operation (read or write) can take before timing
    out in milliseconds. Defaults to *30000* (30 seconds).

    If *-1* is specified, socket operations may block indefinitely. This
    option may also be set on a per-operation basis using <span
    class="methodname">MongoCursor::timeout</span> for queries or the
    *"socketTimeoutMS"* option for write methods.

    > **Note**: <span class="simpara"> This is a client-side timeout. If
    > a write operation times out, there is no way to know if the server
    > actually handled the write or not, as a <span
    > class="classname">MongoCursorTimeoutException</span> will be
    > thrown in lieu of returning a write result. </span>

-   *"ssl"*

    A boolean to specify whether you want to enable SSL for the
    connections to MongoDB. Extra options such as certificates can be
    set with
    <a href="/context/ssl.html" class="xref">SSL context options</a>.

-   *"username"*

    The username can be specified here, instead of including it in the
    host list. This is especially useful if a username has a ":" in it.
    This overrides a username set in the host list.

-   *"w"*

    The *w* option specifies the
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concern</a>
    for the driver, which determines how long the driver blocks when
    writing. The default value is *1*.

    This option is applicable when connecting to both single servers and
    replica sets. A positive value controls how *many* nodes must
    acknowledge the write instruction before the driver continues. A
    value of *1* would require the single server or primary (in a
    replica set) to acknowledge the write operation. A value of *3*
    would cause the driver to block until the write has been applied to
    the primary as well as two secondary servers (in a replica set).

    A string value is used to control which tag sets are taken into
    account for write concerns. *"majority"* is special and ensures that
    the write operation has been applied to the majority (more than 50%)
    of the participating nodes.

-   *"wTimeoutMS"*

    This option specifies the time limit, in milliseconds, for
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    acknowledgement. It is only applicable for write operations where
    *"w"* is greater than *1*, as the timeout pertains to replication.
    If the write concern is not satisfied within the time limit, a <span
    class="classname">MongoCursorException</span> will be thrown. A
    value of *0* may be specified to block indefinitely. The default
    value is *10000* (ten seconds).

The following options are deprecated and should no longer be used:

-   *"slaveOkay"*

    Deprecated. Please use the
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preference</a>
    options.

-   *"timeout"*

    Deprecated alias for *"connectTimeoutMS"*.

-   *"wTimeout"*

    Deprecated alias for *"wTimeoutMS"*.

`driver_options`  
An array of options for the MongoDB driver. Options include setting
connection
<a href="/book/mongo.html#Connect%20to%20MongoDB%20Instance%20with%20SSL%20Encryption" class="link">context options for SSL</a>
or <a href="/context/mongodb.html" class="link">logging callbacks</a>.

-   *"context"*

    The Stream Context to attach to all new connections. This allows you
    for example to configure SSL certificates and are described at
    <a href="/context/ssl.html" class="link">SSL context options</a>.
    See the
    <a href="/book/mongo.html#Connect%20to%20MongoDB%20Instance%20with%20SSL%20Encryption" class="link">Connecting over SSL</a>
    tutorial.

### Return Values

Returns a new database connection object.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
tries and fails to connect to the database for all hostnames given. It
will also throw a <span
class="classname">MongoConnnectionException</span> if an invalid
username or password is given. See <span
class="classname">MongoConnectionException</span> documentation for
common exceptions and their causes.

### Examples

**Example \#1 <span class="function">MongoClient::\_\_construct</span>
replica set example**

This example shows how to connect the driver to a replica set. It
assumes that there is a set of three servers: sf1.example.com,
sf2.example.com, and ny1.example.com. The primary could be any one of
these servers.

``` php
<?php

// pass a comma-separated list of server names to the constructor
// Note that we don't need to pass in all the members of the replicaset, the driver 
// will derive the full list.
$m1 = new MongoClient("mongodb://sf2.example.com,ny1.example.com", array("replicaSet" => "myReplSet"));

?>
```

If the current primary fails, the driver will figure out which secondary
server became the new primary and automatically start using that
connection. Automatic failover will not work correctly if *replicaSet*
is not specified.

At least one seed in the seed list must be up for the driver to connect
to the replica set.

If you include seeds from two separate replica sets, behavior is
undefined.

See the
<a href="https://docs.mongodb.com/manual/replication/" class="link external">» core documentation</a>
on replica sets for more information.

**Example \#2 Connecting to a domain socket**

In version 1.0.9+, you can use a UNIX domain socket to connect to an
instance of MongoDB running locally. This should be slightly faster than
using a network connection.

In version 1.5.0, the MongoDB server automatically opens a socket at
/tmp/mongodb-\<port\>.sock. You can connect to this by specifying the
path in your connection string:

``` php
<?php

// MongoDB server running locally on port 20000
$m = new MongoClient("mongodb:///tmp/mongodb-20000.sock");

?>
```

You can combine this with any other connections you'd like:

``` php
<?php

// try to connect to the domain socket, fall back to localhost connection
$m = new MongoClient("mongodb:///tmp/mongodb-27017.sock,localhost:27017");

?>
```

**Example \#3 <span class="function">MongoClient::\_\_construct</span>
authentication example**

A user must exist in the admin database before attempting to use
authentication. You can create one with the Mongo shell by running:

``` shell
> use admin
switched to db admin
> db.addUser("testUser", "testPass");
{
        "_id" : ObjectId("4b21272fd9ab21611d19095c"),
        "user" : "testUser",
        "pwd" : "03b9b27e0abf1865e2f6fcbd9845dd59"
}
>
```

After creating a user with, in this case, username "testUser" and
password "testPass", you can create an authenticated connection:

``` php
<?php

$m = new MongoClient("mongodb://testUser:testPass@localhost");

?>
```

**Example \#4 <span class="function">MongoClient::\_\_construct</span>
read preference example**

``` php
<?php

// Prefer the nearest server in the "east" data center
$uri  = 'mongodb://rs1.example.com,rs2.example.com/';
$uri .= '?readPreference=nearest';
$uri .= '&readPreferenceTags=dc:east';
$m = new MongoClient($uri, array('replicaSet' => 'rs'));
?>
```

See the
<a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
section of this manual for further information.

**Example \#5 <span class="function">MongoClient::\_\_construct</span>
options example**

Options can be passed both through the query string in the connection
string, or as an array passed as second argument to the constructor.

Here we set the journal option to true and readPreference to secondary
preferred as default for all write operations:

``` php
<?php
$m = new MongoClient("mongodb://localhost/?journal=true&readPreference=secondary");
?>
```

And now we do the same, but as an options array:

``` php
<?php
$options = array(
    'journal' => true,
    'readPreference' => 'secondary',
);
$m = new MongoClient("mongodb://localhost/", $options);
?>
```

**Example \#6 <span class="function">MongoClient::\_\_construct</span>
read preference example**

``` php
<?php

// Prefer the nearest server in the "east" data center
$uri  = 'mongodb://rs1.example.com,rs2.example.com/';
$uri .= '?readPreference=nearest';
$uri .= '&readPreferenceTags=dc:east';
$m = new MongoClient($uri, array('replicaSet' => 'rs'));
?>
```

See the
<a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
section of this manual for further information.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.6.0</td>
<td><p>Added support for <em>"SCRAM-SHA-1"</em> in <em>"authMechanism"</em> option.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.5.0</td>
<td><p>Added <em>"authMechanism"</em>, <em>"gssapiServiceName"</em>, and <em>"secondaryAcceptableLatencyMS"</em>.</p></td>
</tr>
<tr class="odd">
<td>PECL mongo 1.4.0</td>
<td><p>Added <em>"ssl"</em> option and support for <a href="/book/mongo.html#Connecting%20over%20SSL" class="link">connecting over SSL</a>.</p>
<p>Added <em>"wTimeoutMS"</em> option, which replaces <em>"wTimeout"</em>.</p>
<p>Emits <strong><code>E_DEPRECATED</code></strong> when <em>"slaveOkay"</em> or <em>"timeout"</em> is used.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.5.0</td>
<td><p>Added <em>"authSource"</em>.</p></td>
</tr>
<tr class="odd">
<td>PECL mongo 1.3.4</td>
<td><p>Added <em>"connectTimeoutMS"</em> and <em>"socketTimeoutMS"</em> options.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.3.0</td>
<td><p>Added <em>"readPreference"</em>, <em>"readPreferenceTags"</em>, <em>"w"</em>, and <em>"wTimeout"</em> options.</p></td>
</tr>
<tr class="odd">
<td>PECL mongo 1.2.0</td>
<td><p>Added <em>"username"</em> and <em>"password"</em> options.</p>
<p>Removed <em>"persist"</em> option, as all connections are now persistent. It can still be used, but it doesn't affect anything.</p>
<dl>
<dt><code class="parameter">"persist"</code></dt>
<dd><p>If the connection should be persistent. If set, the connection will be persistent. The string representation of the value is used as an ID for the connection, so two instances of <span class="classname">MongoClient</span> that are initialized with <em>array("persist" =&gt; "foobar")</em> will share the same database connection, whereas an instance initialized with <em>array("persist" =&gt; "barbaz")</em> will use a different database connection.</p>
</dd>
</dl>
<p>The <em>"replicaSet"</em> option now takes a string, not a boolean.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.9</td>
<td>Added <em>"replicaSet"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.2</td>
<td><p>Changed constructor to take an array of options. Pre-1.0.2, the constructor took the following parameters:</p>
<dl>
<dt><code class="parameter">server</code></dt>
<dd><p>The server name.</p>
</dd>
<dt><code class="parameter">connect</code></dt>
<dd><p>Optional boolean parameter specifying if the constructor should connect to the database before returning. Defaults to <strong><code>TRUE</code></strong>.</p>
</dd>
<dt><code class="parameter">persistent</code></dt>
<dd><p>If the connection should be persistent.</p>
</dd>
<dt><code class="parameter">paired</code></dt>
<dd><p>If the connection should be paired.</p>
</dd>
</dl></td>
</tr>
</tbody>
</table>

MongoClient::dropDB
===================

Drops a database \[deprecated\]

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension, but
there is an alternative in the
<a href="/set/mongodb.html#Architecture" class="link">PHP library</a>:

-   <a href="https://docs.mongodb.com/php-library/master/reference/method/MongoDBClient-dropDatabase/" class="link external">» MongoDB\Client::dropDatabase()</a>

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::dropDB</span> ( <span
class="methodparam"><span class="type">mixed</span> `$db`</span> )

**Warning**

Use <span class="function">MongoDB::drop</span> instead.

### Parameters

`db`  
The database to drop. Can be a MongoDB object or the name of the
database.

### Return Values

Returns the database response.

MongoClient::\_\_get
====================

Gets a database

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension, but
there is an alternative in the
<a href="/set/mongodb.html#Architecture" class="link">PHP library</a>:

-   <a href="https://docs.mongodb.com/php-library/master/reference/method/MongoDBClient__get/" class="link external">» MongoDB\Client::__get()</a>

### Description

<span class="modifier">public</span> <span class="type">MongoDB</span>
<span class="methodname">MongoClient::\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$dbname`</span> )

This is the cleanest way of getting a database. If the database name has
any special characters, <span
class="function">MongoClient::selectDB</span> will need to be used;
however, this should be sufficient for most cases.

``` php
<?php

$mongo = new MongoClient();

// the following two lines are equivalent
$db = $mongo->selectDB("foo");
$db = $mongo->foo;

?>
```

### Parameters

`dbname`  
The database name.

### Return Values

Returns a new db object.

### Errors/Exceptions

Throws a generic exception if the database name is invalid.

MongoClient::getConnections
===========================

Return info about all open connections

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">MongoClient::getConnections</span> ( <span
class="methodparam">void</span> )

Returns an array of all open connections, and information about each of
the servers

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of open connections.

### Examples

**Example \#1 <span
class="methodname">MongoClient::getConnections</span> example**

``` php
<?php
$m = new MongoClient;
var_dump($m->getConnections());
?>
```

The above example will output something similar to:

    array(1) {
      [0]=>
      array(3) {
        ["hash"]=>
        string(26) "localhost:27017;-;X;56052"
        ["server"]=>
        array(3) {
          ["host"]=>
          string(10) "localhost"
          ["port"]=>
          int(27017)
          ["pid"]=>
          int(56052)
        }
        ["connection"]=>
        array(8) {
          ["last_ping"]=>
          int(1354076401)
          ["last_ismaster"]=>
          int(0)
          ["ping_ms"]=>
          int(0)
          ["connection_type"]=>
          int(1)
          ["connection_type_desc"]=>
          string(10) "STANDALONE"
          ["max_bson_size"]=>
          int(16777216)
          ["tag_count"]=>
          int(0)
          ["tags"]=>
          array(0) {
          }
        }
      }
    }

MongoClient::getHosts
=====================

Updates status for all associated hosts

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this method include:

-   <span class="methodname">MongoDB\\Driver\\Manager::getServers</span>

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::getHosts</span> ( <span
class="methodparam">void</span> )

This method is only useful with a connection to a replica set. It
returns the status of all of the hosts in the set. Without a replica
set, it will just return an array with one element containing the host
that you are connected to.

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

This function has no parameters.

### Return Values

Returns an array of information about the hosts in the set. Includes
each host's hostname, its health (1 is healthy), its state (1 is
primary, 2 is secondary, 0 is anything else), the amount of time it took
to ping the server, and when the last ping occurred. For example, on a
three-member replica set, it might look something like:

``` returnvalues
array(3) {
  ["A:27017"]=>
  array(4) {
    ["host"]=>
    "A"
    ["port"]=>
    27017
    ["health"]=>
    int(1)
    ["state"]=>
    int(2)
    ["ping"]=>
    int(369)
    ["lastPing"]=>
    int(1309470644)
  }
  ["B:27017"]=>
  array(4) {
    ["host"]=>
    "B"
    ["port"]=>
    27017
    ["health"]=>
    int(1)
    ["state"]=>
    int(1)
    ["ping"]=>
    int(139)
    ["lastPing"]=>
    int(1309470644)
  }
  ["C:27017"]=>
  array(4) {
    ["host"]=>
    "C"
    ["port"]=>
    27017
    ["health"]=>
    int(1)
    ["state"]=>
    int(2)
    ["ping"]=>
    int(1012)
    ["lastPing"]=>
    int(1309470644)
  }
}
```

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.2.10</td>
<td><p>Support for non-replicasets was added.</p>
<p>The returned array elements now also include the <em>hostname</em> and <em>port</em>.</p></td>
</tr>
</tbody>
</table>

### See Also

-   <span class="function">MongoClient::getConnections</span>

MongoClient::getReadPreference
==============================

Get the read preference for this connection

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::getReadPreference</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the read preference. The array
contains the values *type* for the string read preference mode
(corresponding to the <span class="classname">MongoClient</span>
constants), and *tagsets* containing a list of all tag set criteria. If
no tag sets were specified, *tagsets* will not be present in the array.

### Changelog

| Version          | Description                                                                                                                                                                                                                                                                                    |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.3.3 | The return value has changed to be consistent with <span class="methodname">MongoClient::setReadPreference</span>. The *type* value was changed from a number to a string, *type\_string* was removed, and *tagsets* now expresses tags as key/value pairs instead of colon-delimited strings. |

### Examples

**Example \#1 <span
class="methodname">MongoClient::getReadPreference</span> return value
example**

``` php
<?php

$m = new MongoClient();
$m->setReadPreference(MongoClient::RP_SECONDARY, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
    array(),
));
var_dump($m->getReadPreference());
?>
```

The above example will output:

    array(2) {
      ["type"]=>
      string(9) "secondary"
      ["tagsets"]=>
      array(3) {
        [0]=>
        array(2) {
          ["dc"]=>
          string(4) "east"
          ["use"]=>
          string(9) "reporting"
        }
        [1]=>
        array(1) {
          ["dc"]=>
          string(7) "west"
        }
        [2]=>
        array(0) {
        }
      }
    }

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoClient::setReadPreference</span>

MongoClient::getWriteConcern
============================

Get the write concern for this connection

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::getWriteConcern</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the write concern. The array
contains the values *w* for an integer acknowledgement level or string
mode, and *wtimeout* denoting the maximum number of milliseconds to wait
for the server to satisfy the write concern.

### Examples

**Example \#1 <span
class="methodname">MongoClient::getWriteConcern</span> return value
example**

``` php
<?php

$mc = new MongoClient('mongodb://localhost:27017', array('wTimeoutMS' => 500));
var_dump($mc->getWriteConcern());

$mc->setWriteConcern(1, 1000);
var_dump($mc->getWriteConcern());
?>
```

The above example will output:

    array(2) {
      ["w"]=>
      int(1)
      ["wtimeout"]=>
      int(500)
    }
    array(2) {
      ["w"]=>
      int(1)
      ["wtimeout"]=>
      int(1000)
    }

### See Also

-   The
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    documentation.
-   <span class="function">MongoClient::setWriteConcern</span>

MongoClient::killCursor
=======================

Kills a specific cursor on the server

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::killCursor</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_hash`</span> , <span class="methodparam"><span
class="type">int\|MongoInt64</span> `$id`</span> )

In certain situations it might be needed to kill a cursor on the server.
Usually cursors time out after 10 minutes of inactivity, but it is
possible to create an immortal cursor with <span
class="methodname">MongoCursor::immortal</span> that never times out. In
order to be able to kill such an immortal cursor, you can call this
method with the information supplied by <span
class="methodname">MongoCursor::info</span>.

### Parameters

`server_hash`  
The server hash that has the cursor. This can be obtained through <span
class="methodname">MongoCursor::info</span>.

`id`  
The ID of the cursor to kill. You can either supply an <span
class="type">int</span> containing the 64 bit cursor ID, or an object of
the <span class="classname">MongoInt64</span> class. The latter is
necessary on 32 bit platforms (and Windows).

### Return Values

Returns **`TRUE`** if the method attempted to kill a cursor, and
**`FALSE`** if there was something wrong with the arguments (such as a
wrong `server_hash`). The return status does *not reflect* where the
cursor was actually killed as the server does not provide that
information.

### Errors/Exceptions

This method displays a warning if the supplied `server_hash` does not
match up with an existing connection. No attempt to kill a cursor is
attempted in that case either.

### Examples

**Example \#1 <span class="function">MongoClient::killCursor</span>
example**

This example shows how to connect, do a query, obtain the cursor
information and then kill the cursor.

``` php
<?php
$m = new MongoClient();
$c = $m->testdb->collection;
$cursor = $c->find();
$result = $cursor->next();

// Now the cursor is valid, so we can get the hash and ID out:
$info = $cursor->info();

// Kill the cursor
MongoClient::killCursor( $info['server'], $info['id'] );
?>
```

MongoClient::listDBs
====================

Lists all of the databases available

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension, but
there is an alternative in the
<a href="/set/mongodb.html#Architecture" class="link">PHP library</a>:

-   <a href="https://docs.mongodb.com/php-library/master/reference/method/MongoDBClient-listDatabases/" class="link external">» MongoDB\Client::listDatabases()</a>

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::listDBs</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns an associative array containing three fields. The first field is
*databases*, which in turn contains an array. Each element of the array
is an associative array corresponding to a database, giving th
database's name, size, and if it's empty. The other two fields are
*totalSize* (in bytes) and *ok*, which is 1 if this method ran
successfully.

### Examples

**Example \#1 <span class="methodname">MongoClient::listDBs</span>
example**

Example demonstrating how to use listDBs and the returned data
structure.

``` php
<?php

$mongo = new MongoClient();
$dbs = $mongo->listDBs();
print_r($dbs);

?>
```

The above example will output something similar to:

    Array
    (
        [databases] => Array
            (
                [0] => Array
                    (
                        [name] => doctrine
                        [sizeOnDisk] => 218103808
                        [empty] =>
                    )
            )

        [totalSize] => 218103808
        [ok] => 1
    )

MongoClient::selectCollection
=============================

Gets a database collection

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension, but
there is an alternative in the
<a href="/set/mongodb.html#Architecture" class="link">PHP library</a>:

-   <a href="https://docs.mongodb.com/php-library/master/reference/method/MongoDBClient-selectCollection/" class="link external">» MongoDB\Client::selectCollection()</a>

### Description

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">MongoClient::selectCollection</span> ( <span
class="methodparam"><span class="type">string</span> `$db`</span> ,
<span class="methodparam"><span class="type">string</span>
`$collection`</span> )

### Parameters

`db`  
The database name.

`collection`  
The collection name.

### Return Values

Returns a new collection object.

### Errors/Exceptions

Throws <span class="classname">Exception</span> if the database or
collection name is invalid.

### Examples

**Example \#1 <span
class="function">MongoClient::selectCollection</span> example**

``` php
<?php
$m = new MongoClient();

$c1 = $m->selectCollection("foo", "bar.baz");
// which is equivalent to
$c2 = $m->selectDB("foo")->selectCollection("bar.baz");

// $c1 and $c2 now represent the same collection
?>
```

MongoClient::selectDB
=====================

Gets a database

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension, but
there is an alternative in the
<a href="/set/mongodb.html#Architecture" class="link">PHP library</a>:

-   <a href="https://docs.mongodb.com/php-library/master/reference/method/MongoDBClient-selectDatabase/" class="link external">» MongoDB\Client::selectDatabase()</a>

### Description

<span class="modifier">public</span> <span class="type">MongoDB</span>
<span class="methodname">MongoClient::selectDB</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

### Parameters

`name`  
The database name.

### Return Values

Returns a new database object.

### Errors/Exceptions

Throws <span class="classname">Exception</span> if the database name is
invalid.

MongoClient::setReadPreference
==============================

Set the read preference for this connection

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

### Parameters

`read_preference`  
The read preference mode: **`MongoClient::RP_PRIMARY`**,
**`MongoClient::RP_PRIMARY_PREFERRED`**,
**`MongoClient::RP_SECONDARY`**,
**`MongoClient::RP_SECONDARY_PREFERRED`**, or
**`MongoClient::RP_NEAREST`**.

`tags`  
An array of zero or more tag sets, where each tag set is itself an array
of criteria used to match tags on replica set members.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Errors/Exceptions

Emits **`E_WARNING`** if either parameter is invalid, or if one or more
tag sets are provided with the **`MongoClient::RP_PRIMARY`** read
preference mode.

### Examples

**Example \#1 <span
class="methodname">MongoClient::setReadPreference</span> tag set array
syntax example**

``` php
<?php

$m = new MongoClient();

// Prefer the nearest server in the "east" data center also used for reporting,
// but fall back to a server in the "west" data center
$m->setReadPreference(MongoClient::RP_NEAREST, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
));
?>
```

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoClient::getReadPreference</span>

MongoClient::setWriteConcern
============================

Set the write concern for this connection

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::setWriteConcern</span> ( <span
class="methodparam"><span class="type">mixed</span> `$w`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$wtimeout`</span> \] )

### Parameters

`w`  
The write concern. This may be an integer denoting the number of servers
required to acknowledge the write, or a string mode (e.g. "majority").

`wtimeout`  
The maximum number of milliseconds to wait for the server to satisfy the
write concern.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Errors/Exceptions

Emits **`E_WARNING`** if the *w* parameter is not an integer or string
value.

### Examples

**Example \#1 <span
class="methodname">MongoClient::setWriteConcern</span> example**

``` php
<?php

$mc = new MongoClient('mongodb://rs1.example.com,rs2.example.com');

// Require that the majority of servers in the replica set acknowledge writes
// within three seconds.
$mc->setWriteConcern('majority', 3000);
?>
```

### See Also

-   The
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    documentation.
-   <span class="function">MongoClient::getWriteConcern</span>

MongoClient::\_\_toString
=========================

String representation of this connection

This extension that defines this method is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoClient::\_\_toString</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns hostname and port for this connection.

Introduction
------------

Instances of this class are used to interact with a database. To get a
database:

**Example \#1 Selecting a database**

``` php
<?php

$m = new MongoClient(); // connect
$db = $m->selectDB("example");

?>
```

Database names can use almost any character in the ASCII range. However,
they cannot contain " ", "." or be the empty string. The name "system"
is also reserved.

A few unusual, but valid, database names: "null", "\[x,y\]", "3", "\\"",
"/".

Unlike collection names, database names may contain "$".

Class synopsis
--------------

**MongoDB**

<span class="ooclass"> class **MongoDB** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`MongoDB::PROFILING_OFF` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoDB::PROFILING_SLOW` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoDB::PROFILING_ON` <span class="initializer"> = 2</span> ;

/\* Fields \*/

<span class="modifier">public</span> <span class="type">integer</span>
`$w` <span class="initializer"> = 1</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$wtimeout` <span class="initializer"> = 10000</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">authenticate</span> ( <span
class="methodparam"><span class="type">string</span> `$username`</span>
, <span class="methodparam"><span class="type">string</span>
`$password`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">command</span> ( <span
class="methodparam"><span class="type">array</span> `$command`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">string</span> `&$hash`</span>
\]\] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoClient</span> `$conn`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> )

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">createCollection</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">createDBRef</span> ( <span
class="methodparam"><span class="type">string</span>
`$collection`</span> , <span class="methodparam"><span
class="type">mixed</span> `$document_or_id`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">drop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">dropCollection</span> ( <span
class="methodparam"><span class="type">mixed</span> `$coll`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">execute</span> ( <span
class="methodparam"><span class="type">mixed</span> `$code`</span> \[,
<span class="methodparam"><span class="type">array</span> `$args`<span
class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">forceError</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">\_\_get</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getCollectionInfo</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getCollectionNames</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getDBRef</span> ( <span
class="methodparam"><span class="type">array</span> `$ref`</span> )

<span class="modifier">public</span> <span
class="type">MongoGridFS</span> <span
class="methodname">getGridFS</span> (\[ <span class="methodparam"><span
class="type">string</span> `$prefix`<span class="initializer"> =
"fs"</span></span> \] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getProfilingLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getReadPreference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getSlaveOkay</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getWriteConcern</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">lastError</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">listCollections</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">prevError</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">repair</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$preserve_cloned_files`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$backup_original_files`<span
class="initializer"> = **`FALSE`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">resetError</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">selectCollection</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">setProfilingLevel</span> ( <span
class="methodparam"><span class="type">int</span> `$level`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSlaveOkay</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$ok`<span
class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setWriteConcern</span> ( <span
class="methodparam"><span class="type">mixed</span> `$w`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$wtimeout`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

MongoDB Log Levels
------------------

**`MongoDB::PROFILING_OFF`**  
<span class="simpara"> Profiling is off. </span>

**`MongoDB::PROFILING_SLOW`**  
<span class="simpara"> Profiling is on for slow operations (\>100 ms).
</span>

**`MongoDB::PROFILING_ON`**  
<span class="simpara"> Profiling is on for all operations. </span>

Fields
------

`w`  
1  
The number of servers to replicate a change to before returning success.
Inherited by instances of <span class="classname">MongoCollection</span>
derived from this. *w* functionality is only available in version 1.5.1+
of the MongoDB server and 1.0.8+ of the driver.

*w* is used whenever you need to adjust the acknowledgement level (<span
class="function">MongoCollection::insert</span>, <span
class="function">MongoCollection::update</span>, <span
class="function">MongoCollection::remove</span>, <span
class="function">MongoCollection::save</span>, and <span
class="function">MongoCollection::ensureIndex</span> all support this
option). With the default value (1), an acknowledged operation will
return once the database server has the operation. If the server goes
down before the operation has been replicated to a secondary, it is
possible to lose the operation forever. Thus, you can specify *w* to be
higher than one and guarantee that at least one secondary has the
operation before it is considered successful.

For example, if *w* is 2, the primary and one secondary must have a
record of the operation or the driver will throw a <span
class="classname">MongoCursorException</span>. It is tempting to set *w*
to the total number of secondaries + primary, but then if one secondary
is down the operation will fail and an exception will be thrown, so
usually *w=2* is safest (primary and one secondary).

`wtimeout`  
10000  
The number of milliseconds to wait for *MongoDB::$w* replications to
take place. Inherited by instances of <span
class="classname">MongoCollection</span> derived from this. *w*
functionality is only available in version 1.5.1+ of the MongoDB server
and 1.0.8+ of the driver.

Unless *wtimeout* is set, the server waits forever for replicating to
*w* servers to finish. The driver defaults to waiting for 10 seconds,
you can change this value to alter its behavior.

See Also
--------

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/glossary/#term-database" class="link external">» databases</a>.

MongoDB::authenticate
=====================

Log in to this database

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.
>
> Instead, you need to provide credentials through the connection
> string.

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::authenticate</span> ( <span
class="methodparam"><span class="type">string</span> `$username`</span>
, <span class="methodparam"><span class="type">string</span>
`$password`</span> )

This method causes its connection to be authenticated. If authentication
is enabled for the database server (it's not, by default), you need to
log in before the database will allow you to do anything.

In general, you should use the authenticate built into <span
class="function">MongoClient::\_\_construct</span> in preference to this
method. If you authenticate on connection and the connection drops and
reconnects during your session, you'll be reauthenticated. If you
manually authenticated using this method and the connection drops,
you'll have to call this method again once you're reconnected.

This method is identical to running:

``` php
<?php

$salted = "${username}:mongo:${password}";
$hash = md5($salted);

$nonce = $db->command(array("getnonce" => 1));

$saltedHash = md5($nonce["nonce"]."${username}${hash}");

$result = $db->command(array("authenticate" => 1,
    "user" => $username,
    "nonce" => $nonce["nonce"],
    "key" => $saltedHash
));

?>
```

Once a connection has been authenticated, it can only be
un-authenticated by using the "logout" database command:

``` php
<?php

$db->command(array("logout" => 1));

?>
```

### Parameters

`username`  
The username.

`password`  
The password (in plaintext).

### Return Values

Returns database response. If the login was successful, it will return

``` php
<?php
array("ok" => 1);
?>
```

If something went wrong, it will return

``` php
<?php
array("ok" => 0, "errmsg" => "auth fails");
?>
```

("auth fails" could be another message, depending on database version
and what when wrong).

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/command/authenticate" class="link external">» authenticate</a>.

### Changelog

| Version           | Description                                                                                       |
|-------------------|---------------------------------------------------------------------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. Please pass in the authentication details to the constructor. |

MongoDB::command
================

Execute a database command

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::command</span> ( <span
class="methodparam"><span class="type">array</span> `$command`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">string</span> `&$hash`</span>
\]\] )

Almost everything that is not a CRUD operation can be done with a
database command. Need to know the database version? There's a command
for that. Need to do aggregation? There's a command for that. Need to
turn up logging? You get the idea.

This method is identical to:

``` php
<?php

public function command($data) {
    return $this->selectCollection('$cmd')->findOne($data);
}

?>
```

### Parameters

`command`  
The query to send.

`options`  
An array of options for the index creation. Currently available options
include:

-   *"socketTimeoutMS"*

    This option specifies the time limit, in milliseconds, for socket
    communication. If the server does not respond within the timeout
    period, a <span class="classname">MongoCursorTimeoutException</span>
    will be thrown and there will be no way to determine if the server
    actually handled the write or not. A value of *-1* may be specified
    to block indefinitely. The default value for <span
    class="classname">MongoClient</span> is *30000* (30 seconds).

The following options are deprecated and should no longer be used:

-   *"timeout"*

    Deprecated alias for *"socketTimeoutMS"*.

`hash`  
Set to the connection hash of the server that executed the command. When
the command result is suitable for creating a <span
class="classname">MongoCommandCursor</span>, the hash is intended to be
passed to <span
class="function">MongoCommandCursor::createFromDocument</span>.

The hash will also correspond to a connection returned from <span
class="function">MongoClient::getConnections</span>.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.5.0</td>
<td><p>Renamed the <em>"timeout"</em> option to <em>"socketTimeoutMS"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"timeout"</em> is used.</p>
<p>Added <em>hash</em> by-reference parameter.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.2.0</td>
<td>Added <em>options</em> parameter with a single option: <em>"timeout"</em>.</td>
</tr>
</tbody>
</table>

### Return Values

Returns database response. Every database response is always maximum one
document, which means that the result of a database command can never
exceed 16MB. The resulting document's structure depends on the command,
but most results will have the *ok* field to indicate success or failure
and *results* containing an array of each of the resulting documents.

### Examples

**Example \#1 <span class="function">MongoDB::command</span> "distinct"
example**

Finding all of the distinct values for a key.

``` php
<?php

$people = $db->people;

$people->insert(array("name" => "Joe", "age" => 4));
$people->insert(array("name" => "Sally", "age" => 22));
$people->insert(array("name" => "Dave", "age" => 22));
$people->insert(array("name" => "Molly", "age" => 87));

$ages = $db->command(array("distinct" => "people", "key" => "age"));

foreach ($ages['values'] as $age) {
    echo "$age\n";
}

?>
```

The above example will output something similar to:

  
4  
22  
87  

**Example \#2 <span class="function">MongoDB::command</span> "distinct"
example**

Finding all of the distinct values for a key, where the value is larger
than or equal to 18.

``` php
<?php

$people = $db->people;

$people->insert(array("name" => "Joe", "age" => 4));
$people->insert(array("name" => "Sally", "age" => 22));
$people->insert(array("name" => "Dave", "age" => 22));
$people->insert(array("name" => "Molly", "age" => 87));

$ages = $db->command(
    array(
        "distinct" => "people",
        "key" => "age", 
        "query" => array("age" => array('$gte' => 18))
    )
);  

foreach ($ages['values'] as $age) {
    echo "$age\n";
}

?>
```

The above example will output something similar to:

  
22  
87  

**Example \#3 <span class="function">MongoDB::command</span> MapReduce
example**

Get all users with at least on "sale" event, and how many times each of
these users has had a sale.

``` php
<?php

// sample event document
$events->insert(array("user_id" => $id, 
    "type" => $type, 
    "time" => new MongoDate(), 
    "desc" => $description));

// construct map and reduce functions
$map = new MongoCode("function() { emit(this.user_id,1); }");
$reduce = new MongoCode("function(k, vals) { ".
    "var sum = 0;".
    "for (var i in vals) {".
        "sum += vals[i];". 
    "}".
    "return sum; }");

$sales = $db->command(array(
    "mapreduce" => "events", 
    "map" => $map,
    "reduce" => $reduce,
    "query" => array("type" => "sale"),
    "out" => array("merge" => "eventCounts")));

$users = $db->selectCollection($sales['result'])->find();

foreach ($users as $user) {
    echo "{$user['_id']} had {$user['value']} sale(s).\n";
}

?>
```

The above example will output something similar to:

  
User 47cc67093475061e3d9536d2 had 3 sale(s).  
User 49902cde5162504500b45c2c had 14 sale(s).  
User 4af467e4fd543cce7b0ea8e2 had 1 sale(s).  

> **Note**: **Using <span class="classname">MongoCode</span>**  
>
> This example uses <span class="classname">MongoCode</span>, which can
> also take a scope argument. However, at the moment, MongoDB does not
> support using scopes in MapReduce. If you would like to use
> client-side variables in the MapReduce functions, you can add them to
> the global scope by using the optional scope field with the database
> command. See the
> <a href="https://docs.mongodb.com/manual/core/map-reduce/" class="link external">» MapReduce documentation</a>
> for more information.

> **Note**: **The *out* argument**  
>
> Before 1.8.0, the *out* argument was optional. If you did not use it,
> MapReduce results would be written to a temporary collection, which
> would be deleted when your connection was closed. In 1.8.0+, the *out*
> argument is required. See the
> <a href="https://docs.mongodb.com/manual/core/map-reduce/" class="link external">» MapReduce documentation</a>
> for more information.

**Example \#4 <span class="function">MongoDB::command</span> "geoNear"
example**

This example shows how to use the geoNear command.

``` php
<?php
$m = new MongoClient();
$d = $m->demo;
$c = $d->poiConcat;

$r = $d->command(array(
    'geoNear' => "poiConcat",      // Search in the poiConcat collection
    'near' => array(-0.08, 51.48), // Search near 51.48°N, 0.08°E
    'spherical' => true,           // Enable spherical search
    'num' => 5,                    // Maximum 5 returned documents
));
print_r($r);
?>
```

### See Also

-   <span class="methodname">MongoCollection::aggregate</span>
-   <span class="methodname">MongoCollection::findAndModify</span>
-   <span class="methodname">MongoCollection::group</span>

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/command/" class="link external">» database commands</a>.

MongoDB::\_\_construct
======================

Creates a new database

### Description

<span class="modifier">public</span> <span
class="methodname">MongoDB::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoClient</span> `$conn`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> )

This method is not meant to be called directly. The preferred way to
create an instance of MongoDB is through <span
class="function">MongoClient::\_\_get</span> or <span
class="function">MongoClient::selectDB</span>.

If you're ignoring the previous paragraph and want to call it directly
you can do so:

``` php
<?php

$m = new MongoClient();
$db = new MongoDB($m, 'mydbname');

?>
```

But don't. Isn't this much nicer:

``` php
<?php

$m = new MongoClient();
$db = $m->mydbname;

// or, if the name contains weird characters:

$db = $m->selectDB('my,db:name');

?>
```

### Parameters

<span class="type">MongoClient</span> `conn`  
Database connection.

`name`  
Database name.

### Return Values

Returns the database.

### Errors/Exceptions

Throws default exception if the database name is invalid.

MongoDB::createCollection
=========================

Creates a collection

### Description

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">MongoDB::createCollection</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

This method is used to create capped collections and other collections
requiring special options. It is identical to running:

``` php
<?php

$collection = $db->command(array(
    "create" => $name,
    "capped" => $options["capped"],
    "size" => $options["size"],
    "max" => $options["max"],
    "autoIndexId" => $options["autoIndexId"],
));

?>
```

See <span class="function">MongoDB::command</span> for more information
about database commands.

### Parameters

`name`  
The name of the collection.

`options`  
An array containing options for the collections. Each option is its own
element in the options array, with the option name listed below being
the key of the element. The supported options depend on the MongoDB
server version and storage engine, and the driver passes any option that
you give it straight to the server. A few of the supported options are,
but you can find a full list in the MongoDB core docs on
<a href="https://docs.mongodb.com/manual/method/db.createCollection/" class="link external">» createCollection</a>:

`capped`  
If the collection should be a fixed size.

`size`  
If the collection is fixed size, its size in bytes.

`max`  
If the collection is fixed size, the maximum number of elements to store
in the collection.

`autoIndexId`  
If capped is **`TRUE`** you can specify **`FALSE`** to disable the
automatic index created on the *\_id* field. Before MongoDB 2.2, the
default value for *autoIndexId* was **`FALSE`**.

### Return Values

Returns a collection object representing the new collection.

### Examples

**Example \#1 <span class="function">MongoDB::createCollection</span>
capped collection example**

A capped collection is a special type of collection that has either a
fixed or a fixed number of elements. Once the collection is "full," the
oldest elements will be removed when new elements are added. Capped
collections can be very useful for applications like logging, where you
may want to reserve a certain amount of space for logs and not worry
about them getting too big.

This example creates a very tiny log collection that will keep a maximum
of 10 documents.

``` php
<?php

$log = $db->createCollection(
    "logger",
    array(
        'capped' => true,
        'size' => 10*1024,
        'max' => 10
    )
);

for ($i = 0; $i < 100; $i++) {
    $log->insert(array("level" => WARN, "msg" => "sample log message #$i", "ts" => new MongoDate()));
}

$msgs = $log->find();

foreach ($msgs as $msg) {
    echo $msg['msg']."\n";
}

?>
```

The above example will output something similar to:

  
sample log message \#90  
sample log message \#91  
sample log message \#92  
sample log message \#93  
sample log message \#94  
sample log message \#95  
sample log message \#96  
sample log message \#97  
sample log message \#98  
sample log message \#99  

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.4.0</td>
<td><p>In versions before 1.4.0, the options were all arguments to the method. The function synopsis in those older versions is:</p>
<div class="methodsynopsis dc-description">
<span class="modifier">public</span> <span class="type">MongoCollection</span> <span class="methodname">MongoDB::createCollection</span> ( <span class="methodparam"><span class="type">string</span> <code class="parameter">$name</code></span> [, <span class="methodparam"><span class="type">bool</span> <code class="parameter">$capped</code><span class="initializer"> = <strong><code>FALSE</code></strong></span></span> [, <span class="methodparam"><span class="type">int</span> <code class="parameter">$size</code><span class="initializer"> = 0</span></span> [, <span class="methodparam"><span class="type">int</span> <code class="parameter">$max</code><span class="initializer"> = 0</span></span> ]]] )
</div>
<p>The meaning of the options is the same as described under the <code class="parameter">options</code> argument above.</p></td>
</tr>
</tbody>
</table>

MongoDB::createDBRef
====================

Creates a database reference

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::createDBRef</span> ( <span
class="methodparam"><span class="type">string</span>
`$collection`</span> , <span class="methodparam"><span
class="type">mixed</span> `$document_or_id`</span> )

This method is a flexible interface for creating database refrences (see
<span class="classname">MongoDBRef</span>).

### Parameters

`collection`  
The collection to which the database reference will point.

`document_or_id`  
If an array or object is given, its *\_id* field will be used as the
reference ID. If a <span class="classname">MongoId</span> or scalar is
given, it will be used as the reference ID.

### Return Values

Returns a database reference array.

If an array without an *\_id* field was provided as the
*document\_or\_id* parameter, **`NULL`** will be returned.

### Examples

**Example \#1 <span class="function">MongoDB::createDBRef</span>
example**

Example demonstrating how to programatically create a DB reference array
from a document.

``` php
<?php

$articles = $db->articles;

$article = array(
 'title' => 'Test article',
 'description' => 'Test article description'
);

$articles->insert($article);
$ref = $db->createDBRef('articles', $article);

print_r($article);
print_r($ref);
?>
```

The above example will output something similar to:

         Array
         (
             [title] => Test article
             [description] => Test article description
             [_id] => MongoId Object
                 (
                 )

         )
         Array
         (
             [$ref] => articles
             [$id] => MongoId Object
                 (
                 )

         )
         

Now the $ref can be stored on another document and retrieved later with
<span class="methodname">MongoDB::getDBRef</span> or <span
class="methodname">MongoCollection::getDBRef</span>.

**Example \#2 <span class="function">MongoDB::createDBRef</span>
example**

Example demonstrating how to programatically create a DB reference from
just an id.

``` php
<?php

$id = new MongoId('47cc67093475061e3d9536d2');
$ref = $db->createDBRef('articles', $id);
?>
```

MongoDB::drop
=============

Drops this database

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::drop</span> ( <span
class="methodparam">void</span> )

This drops the database currently being used.

This is identical to running:

``` php
<?php

public function drop() {
    $this->command(array("dropDatabase" => 1));
}

?>
```

### Parameters

This function has no parameters.

### Return Values

Returns the database response.

### Examples

**Example \#1 <span class="function">MongoDB::drop</span> example**

This example demonstrates how to drop a mongo database and the response
to expect.

``` php
<?php

$db = $mongo->foo;
$response = $db->drop();
print_r($response);

?>
```

The above example will output something similar to:

    Array
    (
        [dropped] => foo.$cmd
        [ok] => 1
    )

MongoDB::dropCollection
=======================

Drops a collection \[deprecated\]

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::dropCollection</span> ( <span
class="methodparam"><span class="type">mixed</span> `$coll`</span> )

**Warning**

Use <span class="function">MongoCollection::drop</span> instead.

*This function leaks memory in version 1.0.7 and earlier!*

### Parameters

`coll`  
MongoCollection or name of collection to drop.

### Return Values

Returns the database response.

MongoDB::execute
================

Runs JavaScript code on the database server \[deprecated\]

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::execute</span> ( <span
class="methodparam"><span class="type">mixed</span> `$code`</span> \[,
<span class="methodparam"><span class="type">array</span> `$args`<span
class="initializer"> = array()</span></span> \] )

**Warning**

The
<a href="https://docs.mongodb.com/manual/reference/command/eval/" class="link external">» eval</a>
command, which this method invokes, is deprecated in MongoDB 3.0+.

The Mongo database server runs a JavaScript engine. This method allows
you to run arbitary JavaScript on the database. This can be useful if
you want touch a number of collections lightly, or process some results
on the database side to reduce the amount that has to be sent to the
client.

Running JavaScript in the database takes a write lock, meaning it blocks
other operations. Make sure you consider this before running a long
script.

This is a wrapper for the
<a href="https://docs.mongodb.com/manual/reference/command/eval/" class="link external">» eval</a>
database command. This method is basically:

``` php
<?php

public function execute($code, $args) {
    return $this->command(array('eval' => $code, 'args' => $args));
}

?>
```

MongoDB implies a return statement if you have a single statement on a
single line. This can cause some unintuitive behavior. For example, this
returns "foo":

``` php
<?php

$db->execute('"foo";');

?>
```

However, these return **`NULL`**:

``` php
<?php

$db->execute('"bar"; "foo";'); // more than one statement

$db->execute('db.foo.count(
);'); // more than one line

?>
```

To avoid surprising behavior, it is best not to depend on MongoDB to
decide what to return, but to explicitly state a return value. In the
examples above, we can change them to:

``` php
<?php

$db->execute('"bar"; return "foo";');

$db->execute('return db.foo.count(
);');

?>
```

Now the first statement will return "foo" and the second statement will
return a count of the "foo" collection.

### Parameters

`code`  
<span class="classname">MongoCode</span> or string to execute.

`args`  
Arguments to be passed to *code*.

### Return Values

Returns the result of the evaluation.

### Examples

**Example \#1 Simple <span class="function">MongoDB::execute</span>
example**

``` php
<?php

$response = $db->execute("function() { return 'Hello, world!'; }");
echo $response['retval'];

?>
```

The above example will output something similar to:

  
Hello, world!  

**Example \#2 Parameter <span class="function">MongoDB::execute</span>
example**

The optional array of parameters will be passed to the JavaScript
function.

``` php
<?php

$response = $db->execute("function(greeting, name) { return greeting+', '+name+'!'; }", array("Good bye", "Joe"));
echo $response['retval'];

?>
```

The above example will output something similar to:

  
Good bye, Joe!  

**Example \#3 Scope example**

If a <span class="classname">MongoCode</span> object is used instead of
a string for the first parameter, a scope can be passed in which the
JavaScript will be executed.

``` php
<?php

$func = 
    "function(greeting, name) { ".
        "return greeting+', '+name+', says '+greeter;".
    "}";
$scope = array("greeter" => "Fred");

$code = new MongoCode($func, $scope);

$response = $db->execute($code, array("Goodbye", "Joe"));
echo $response['retval'];

?>
```

The above example will output something similar to:

  
Goodbye, Joe, says Fred  

### See Also

-   The MongoDB
    <a href="https://docs.mongodb.com/manual/reference/command/eval/" class="link external">» eval command</a>
    docs

### Changelog

| Version          | Description                                                                                                                                                                                                 |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.7.0 | This method has been deprecated as a result of the underlaying <a href="https://docs.mongodb.com/manual/reference/command/eval/" class="link external">» eval</a> command being deprecated in MongoDB 3.0+. |

MongoDB::forceError
===================

Creates a database error

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoDB::forceError</span> ( <span
class="methodparam">void</span> )

This method is not very useful for normal MongoDB use. It forces a
database error to occur. This means that <span
class="function">MongoDB::lastError</span> will return a generic
database error after running this command.

This command is identical to running:

``` php
<?php

public function forceError() {
    return $this->command(array('forceerror' => 1));
}

?>
```

### Parameters

This function has no parameters.

### Return Values

Returns the database response.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

MongoDB::\_\_get
================

Gets a collection

### Description

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">MongoDB::\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

This is the easiest way of getting a collection from a database object.
If a collection name contains strange characters, you may have to use
<span class="function">MongoDB::selectCollection</span> instead.

``` php
<?php

$mongo = new MongoClient();

// the following two lines are equivalent
$collection = $mongo->selectDB("foo")->selectCollection("bar");
$collection = $mongo->foo->bar;

?>
```

### Parameters

`name`  
The name of the collection.

### Return Values

Returns the collection.

MongoDB::getCollectionInfo
==========================

Returns information about collections in this database

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::getCollectionInfo</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

Gets a list of all collections in the database and returns them as an
array of documents, which contain their names and options.

> **Note**: <span class="simpara">This method will use the
> <a href="https://docs.mongodb.com/manual/reference/command/listCollections" class="link external">» listCollections</a>
> database command when communicating with MongoDB 2.8+. For previous
> database versions, the method will query the special
> *system.namespaces* collection.</span>

### Parameters

`options`  
An array of options for listing the collections. Currently available
options include:

-   *"filter"*

    Optional query criteria. If provided, this criteria will be used to
    filter the collections included in the result.

    Relevant fields that may be queried include *"name"* (collection
    name as a string, without the database name prefix) and *"options"
    (object containing options used to create the collection).*.

    > **Note**: <span class="simpara">MongoDB 2.6 and earlier versions
    > require the *"name"* criteria, if specified, to be a string value
    > (i.e. equality match). This is because the driver must prefix the
    > value with the database name in order to query the
    > *system.namespaces* collection. Later versions of MongoDB do not
    > have this limitation, as the driver will use the listCollections
    > command.</span>

-   *"includeSystemCollections"*

    Boolean, defaults to **`FALSE`**. Determines whether system
    collections should be included in the result.

The following option may be used with MongoDB 2.8+:

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

### Return Values

This function returns an array where each element is an array describing
a collection. Elements will contain a *name* key denoting the name of
the collection, and optionally contain an *options* key denoting an
array of objects used to create the collection. For example, capped
collections will include *capped* and *size* options.

### Errors/Exceptions

For MongoDB 2.6 and earlier, <span
class="classname">MongoException</span> will be thrown if a non-string
value was specified for the *"filter"* option's *"name"* criteria.

### Examples

**Example \#1 <span class="function">MongoDB::getCollectionInfo</span>
example**

``` php
<?php
$m = new MongoClient();
$db = $m->selectDB("demo");
var_dump($db->getCollectionInfo());
?>
```

The above example will output something similar to:

    array(2) {
      [0]=>
      array(2) {
        ["name"]=>
        string(4) "logs"
        ["options"]=>
        array(2) {
          ["capped"]=>
          bool(true)
          ["size"]=>
          int(10240)
        }
      }
      [1]=>
      array(2) {
        ["name"]=>
        string(5) "users"
        ["options"]=>
        array(1) {
          ["flags"]=>
          int(1)
        }
      }
    }

### See Also

-   <span class="function">MongoDB::getCollectionNames</span>
-   <span class="function">MongoDB::listCollections</span>

MongoDB::getCollectionNames
===========================

Gets an array of names for all collections in this database

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::getCollectionNames</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

Gets a list of all collections in the database and returns their names
as an array of strings.

> **Note**: <span class="simpara">This method will use the
> <a href="https://docs.mongodb.com/manual/reference/command/listCollections" class="link external">» listCollections</a>
> database command when communicating with MongoDB 2.8+. For previous
> database versions, the method will query the special
> *system.namespaces* collection.</span>

### Parameters

`options`  
An array of options for listing the collections. Currently available
options include:

-   *"filter"*

    Optional query criteria. If provided, this criteria will be used to
    filter the collections included in the result.

    Relevant fields that may be queried include *"name"* (collection
    name as a string, without the database name prefix) and *"options"
    (object containing options used to create the collection).*.

    > **Note**: <span class="simpara">MongoDB 2.6 and earlier versions
    > require the *"name"* criteria, if specified, to be a string value
    > (i.e. equality match). This is because the driver must prefix the
    > value with the database name in order to query the
    > *system.namespaces* collection. Later versions of MongoDB do not
    > have this limitation, as the driver will use the listCollections
    > command.</span>

-   *"includeSystemCollections"*

    Boolean, defaults to **`FALSE`**. Determines whether system
    collections should be included in the result.

The following option may be used with MongoDB 2.8+:

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

### Return Values

Returns the collection names as an array of strings.

### Errors/Exceptions

For MongoDB 2.6 and earlier, <span
class="classname">MongoException</span> will be thrown if a non-string
value was specified for the *"filter"* option's *"name"* criteria.

### Changelog

| Version          | Description                                                                                                                                         |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.6.0 | Changed first parameter to be an array of options. Pre-1.6.0, the first parameter was a boolean indicating the *"includeSystemCollections"* option. |

### Examples

**Example \#1 <span class="function">MongoDB::getCollectionNames</span>
example**

``` php
<?php
$m = new MongoClient();
$db = $m->selectDB("demo");
$collections = $db->getCollectionNames();

foreach ($collections as $collectionName) {
    echo "Found collection: ", $collectionName, "\n";
}
?>
```

The above example will output something similar to:

    ...
    Found collection: img
    Found collection: beer
    Found collection: collation
    ...

### See Also

-   <span class="function">MongoDB::listCollections</span>
-   <span class="function">MongoDB::getCollectionInfo</span>

MongoDB::getDBRef
=================

Fetches the document pointed to by a database reference

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::getDBRef</span> ( <span
class="methodparam"><span class="type">array</span> `$ref`</span> )

### Parameters

`ref`  
A database reference.

### Return Values

Returns the document pointed to by the reference.

### Examples

**Example \#1 <span class="function">MongoDB::getDBRef</span> example**

Example demonstrating how to get a database reference and what the
expected input is.

``` php
<?php

 $ref = array(
   '$ref' => 'profiles',
   '$id' => new MongoId('47cc67093475061e3d9536d2')
 );
 
 $profile = $db->getDBRef($ref);
 ?>
```

See <span class="function">MongoDB::createDBRef</span> for more
information about how to programatically create DB references.

MongoDB::getGridFS
==================

Fetches toolkit for dealing with files stored in this database

### Description

<span class="modifier">public</span> <span
class="type">MongoGridFS</span> <span
class="methodname">MongoDB::getGridFS</span> (\[ <span
class="methodparam"><span class="type">string</span> `$prefix`<span
class="initializer"> = "fs"</span></span> \] )

### Parameters

`prefix`  
The prefix for the files and chunks collections.

### Return Values

Returns a new gridfs object for this database.

### Examples

**Example \#1 <span class="function">MongoDB::getGridFS</span> example**

This example demonstrates how get a MongoGridFS instance.

``` php
<?php

$db = $mongo->my_db;

$prefix = 'files';
$collection = $db->getGridFS($prefix);

?>
```

Read more about the <span class="classname">MongoGridFS</span> to learn
how to store files with MongoDB.

MongoDB::getProfilingLevel
==========================

Gets this database's profiling level

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoDB::getProfilingLevel</span> ( <span
class="methodparam">void</span> )

This returns the current database profiling level.

The database profiler tracks query execution times. If you turn it on
(say, using <span class="function">MongoDB::setProfilingLevel</span> or
the shell), you can see how many queries took longer than a given number
of milliseconds or the timing for all queries.

Note that profiling slows down queries, so it is better to use in
development or testing than in a time-sensitive application.

This function is equivalent to running:

``` php
<?php

public function getProfilingLevel() {
    return $this->command(array('profile' => -1));
}

?>
```

### Parameters

This function has no parameters.

### Return Values

Returns the profiling level.

### See Also

-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/tutorial/manage-the-database-profiler/" class="link external">» profiling</a>
-   <span class="methodname">MongoDB::setProfilingLevel</span>

MongoDB::getReadPreference
==========================

Get the read preference for this database

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::getReadPreference</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the read preference. The array
contains the values *type* for the string read preference mode
(corresponding to the <span class="classname">MongoClient</span>
constants), and *tagsets* containing a list of all tag set criteria. If
no tag sets were specified, *tagsets* will not be present in the array.

### Changelog

| Version          | Description                                                                                                                                                                                                                                                                                |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.3.3 | The return value has changed to be consistent with <span class="methodname">MongoDB::setReadPreference</span>. The *type* value was changed from a number to a string, *type\_string* was removed, and *tagsets* now expresses tags as key/value pairs instead of colon-delimited strings. |

### Examples

**Example \#1 <span class="methodname">MongoDB::getReadPreference</span>
return value example**

``` php
<?php

$m = new MongoClient();
$db = $m->test;
$db->setReadPreference(MongoClient::RP_SECONDARY, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
    array(),
));
var_dump($db->getReadPreference());
?>
```

The above example will output:

    array(2) {
      ["type"]=>
      string(9) "secondary"
      ["tagsets"]=>
      array(3) {
        [0]=>
        array(2) {
          ["dc"]=>
          string(4) "east"
          ["use"]=>
          string(9) "reporting"
        }
        [1]=>
        array(1) {
          ["dc"]=>
          string(7) "west"
        }
        [2]=>
        array(0) {
        }
      }
    }

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoDB::setReadPreference</span>

MongoDB::getSlaveOkay
=====================

Get slaveOkay setting for this database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoDB::getSlaveOkay</span> ( <span
class="methodparam">void</span> )

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

This function has no parameters.

### Return Values

Returns the value of slaveOkay for this instance.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### See Also

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <span class="methodname">MongoDB::getReadPreference</span>
-   <span class="methodname">MongoDB::setReadPreference</span>

MongoDB::getWriteConcern
========================

Get the write concern for this database

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::getWriteConcern</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the write concern. The array
contains the values *w* for an integer acknowledgement level or string
mode, and *wtimeout* denoting the maximum number of milliseconds to wait
for the server to satisfy the write concern.

### Examples

**Example \#1 <span class="methodname">MongoDB::getWriteConcern</span>
return value example**

``` php
<?php

$mc = new MongoClient('mongodb://localhost:27017', array('wTimeoutMS' => 500));
$db = $mc->selectDB('test');
var_dump($db->getWriteConcern());

$db->setWriteConcern(1, 1000);
var_dump($db->getWriteConcern());
?>
```

The above example will output:

    array(2) {
      ["w"]=>
      int(1)
      ["wtimeout"]=>
      int(500)
    }
    array(2) {
      ["w"]=>
      int(1)
      ["wtimeout"]=>
      int(1000)
    }

### See Also

-   The
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    documentation.
-   <span class="function">MongoDB::setWriteConcern</span>

MongoDB::lastError
==================

Check if there was an error on the most recent db operation performed

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::lastError</span> ( <span
class="methodparam">void</span> )

This method is equivalent to:

``` php
<?php

public function lastError() {
    return $this->command(array('getlasterror' => 1));
}

?>
```

### Parameters

This function has no parameters.

### Return Values

Returns the error, if there was one.

### Examples

**Example \#1 <span class="function">MongoDB::lastError</span>
**`NULL`** error example**

``` php
<?php
$db->resetError();
var_dump($db->lastError());
?>
```

The above example will output something similar to:

    array(3) {
      ["err"]=>
      NULL
      ["n"]=>
      int(0)
      ["ok"]=>
      float(1)
    }

**Example \#2 <span class="function">MongoDB::lastError</span> duplicate
key example**

``` php
<?php
$c = $db->selectCollection("foo");

// insert two documents with the same _id
$c->insert(array("_id" => 1));
$c->insert(array("_id" => 1));

var_dump($db->lastError());
?>
```

The above example will output something similar to:

    array(3) {
      ["err"]=>
      string(64) "E11000 duplicate key errorindex: foo.foo.$_id_  dup key: { : 1 }"
      ["n"]=>
      int(0)
      ["ok"]=>
      float(1)
    }

MongoDB::listCollections
========================

Gets an array of MongoCollection objects for all collections in this
database

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::listCollections</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

Gets a list of all collections in the database and returns them as an
array of <span class="classname">MongoCollection</span> objects.

> **Note**: <span class="simpara">This method will use the
> <a href="https://docs.mongodb.com/manual/reference/command/listCollections" class="link external">» listCollections</a>
> database command when communicating with MongoDB 2.8+. For previous
> database versions, the method will query the special
> *system.namespaces* collection.</span>

### Parameters

`options`  
An array of options for listing the collections. Currently available
options include:

-   *"filter"*

    Optional query criteria. If provided, this criteria will be used to
    filter the collections included in the result.

    Relevant fields that may be queried include *"name"* (collection
    name as a string, without the database name prefix) and *"options"
    (object containing options used to create the collection).*.

    > **Note**: <span class="simpara">MongoDB 2.6 and earlier versions
    > require the *"name"* criteria, if specified, to be a string value
    > (i.e. equality match). This is because the driver must prefix the
    > value with the database name in order to query the
    > *system.namespaces* collection. Later versions of MongoDB do not
    > have this limitation, as the driver will use the listCollections
    > command.</span>

-   *"includeSystemCollections"*

    Boolean, defaults to **`FALSE`**. Determines whether system
    collections should be included in the result.

The following option may be used with MongoDB 2.8+:

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

### Return Values

Returns an array of MongoCollection objects.

### Errors/Exceptions

For MongoDB 2.6 and earlier, <span
class="classname">MongoException</span> will be thrown if a non-string
value was specified for the *"filter"* option's *"name"* criteria.

### Changelog

| Version          | Description                                                                                                                                         |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.6.0 | Changed first parameter to be an array of options. Pre-1.6.0, the first parameter was a boolean indicating the *"includeSystemCollections"* option. |
| PECL mongo 1.3.0 | Added the `includeSystemCollections` parameter.                                                                                                     |

### Examples

**Example \#1 <span class="function">MongoDB::listCollections</span>
example**

The following example demonstrates running count on each collection in a
database.

``` php
<?php

$m = new MongoClient();
$db = $m->selectDB("demo");
$collections = $db->listCollections();

foreach ($collections as $collection) {
    echo "amount of documents in $collection: ";
    echo $collection->count(), "\n";
}

?>
```

The above example will output something similar to:

    ...
    amount of documents in demo.pubs: 4
    amount of documents in demo.elephpants: 3
    amount of documents in demo.cities: 22840
    ...

### See Also

-   <span class="function">MongoDB::getCollectionNames</span>
-   <span class="function">MongoDB::getCollectionInfo</span>

MongoDB::prevError
==================

Checks for the last error thrown during a database operation

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::prevError</span> ( <span
class="methodparam">void</span> )

<span class="function">MongoDB::lastError</span> is usually preferred to
this. This method returns the last database error that occurred and how
many operations ago it occurred. It is mostly deprecated.

### Parameters

This function has no parameters.

### Return Values

Returns the error and the number of operations ago it occurred.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

MongoDB::repair
===============

Repairs and compacts this database

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::repair</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$preserve_cloned_files`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$backup_original_files`<span
class="initializer"> = **`FALSE`**</span></span> \]\] )

This creates a fresh copy of all database data. It will remove any
corrupt data and compact and large stretches of free space it finds.
This is a very slow operation on a large database.

This is usually run from the shell or the command line, not the driver.

It is equivalent to the function:

``` php
<?php

public function repair() {
    return $this->command(array('repairDatabase' => 1));
}

?>
```

### Parameters

`preserve_cloned_files`  
If cloned files should be kept if the repair fails.

`backup_original_files`  
If original files should be backed up.

### Return Values

Returns db response.

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/command/repairDatabase" class="link external">» repairDatabase</a>.

### Examples

**Example \#1 <span class="function">MongoDB::repair</span> example**

This example demonstrates how to repare and compact a database.

``` php
<?php

$db = $mongo->foo;

$response = $db->repair();
print_r($response);

?>
```

The above example will output something similar to:

    Array
    (
        [ok] => 1
    )

MongoDB::resetError
===================

Clears any flagged errors on the database

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoDB::resetError</span> ( <span
class="methodparam">void</span> )

This method is not used in normal operations. It resets the database
error tracker (which can be incremented with <span
class="function">MongoDB::forceError</span>, also not normally used).

It is equivalent to running:

``` php
<?php

public function resetError() {
    return $this->command(array('reseterror' => 1));
}

?>
```

### Parameters

This function has no parameters.

### Return Values

Returns the database response.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

MongoDB::selectCollection
=========================

Gets a collection

### Description

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">MongoDB::selectCollection</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

### Parameters

`name`  
The collection name.

### Return Values

Returns a new collection object.

### Errors/Exceptions

Throws <span class="classname">Exception</span> if the collection name
is invalid.

MongoDB::setProfilingLevel
==========================

Sets this database's profiling level

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoDB::setProfilingLevel</span> ( <span
class="methodparam"><span class="type">int</span> `$level`</span> )

This changes the current database profiling level.

This function is equivalent to running:

``` php
<?php

public function setProfilingLevel($level) {
    return $this->command(array('profile' => $level));
}

?>
```

The options for level are 0 (off), 1 (queries \> 100ms), and 2 (all
queries). If you would like to profile queries that take longer than
another time period, use the database command and pass it a second
option, the number of milliseconds. For example, to profile all queries
that take longer than one second, run:

``` php
<?php

$result = $this->command(array('profile' => 1, 'slowms' => 1000));

?>
```

Profiled queries will appear in the *system.profile* collection of this
database.

### Parameters

`level`  
Profiling level.

### Return Values

Returns the previous profiling level.

### See Also

-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/tutorial/manage-the-database-profiler/" class="link external">» profiling</a>
-   <span class="methodname">MongoDB::getProfilingLevel</span>

MongoDB::setReadPreference
==========================

Set the read preference for this database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoDB::setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

### Parameters

`read_preference`  
The read preference mode: **`MongoClient::RP_PRIMARY`**,
**`MongoClient::RP_PRIMARY_PREFERRED`**,
**`MongoClient::RP_SECONDARY`**,
**`MongoClient::RP_SECONDARY_PREFERRED`**, or
**`MongoClient::RP_NEAREST`**.

`tags`  
An array of zero or more tag sets, where each tag set is itself an array
of criteria used to match tags on replica set members.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Errors/Exceptions

Emits **`E_WARNING`** if either parameter is invalid, or if one or more
tag sets are provided with the **`MongoClient::RP_PRIMARY`** read
preference mode.

### Examples

**Example \#1 <span class="methodname">MongoDB::setReadPreference</span>
tag set array syntax example**

``` php
<?php

$m = new MongoClient();
$db = $m->test;

// Prefer the nearest server in the "east" data center also used for reporting,
// but fall back to a server in the "west" data center
$db->setReadPreference(MongoClient::RP_NEAREST, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
));
?>
```

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoDB::getReadPreference</span>

MongoDB::setSlaveOkay
=====================

Change slaveOkay setting for this database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoDB::setSlaveOkay</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$ok`<span
class="initializer"> = **`TRUE`**</span></span> \] )

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

`ok`  
If reads should be sent to secondary members of a replica set for all
possible queries using this <span class="classname">MongoDB</span>
instance.

### Return Values

Returns the former value of slaveOkay for this instance.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### See Also

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <span class="methodname">MongoDB::setReadPreference</span>
-   <span class="methodname">MongoDB::getReadPreference</span>

MongoDB::setWriteConcern
========================

Set the write concern for this database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoDB::setWriteConcern</span> ( <span
class="methodparam"><span class="type">mixed</span> `$w`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$wtimeout`</span> \] )

### Parameters

`w`  
The write concern. This may be an integer denoting the number of servers
required to acknowledge the write, or a string mode (e.g. "majority").

`wtimeout`  
The maximum number of milliseconds to wait for the server to satisfy the
write concern.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Errors/Exceptions

Emits **`E_WARNING`** if the *w* parameter is not an integer or string
value.

### Examples

**Example \#1 <span class="methodname">MongoDB::setWriteConcern</span>
example**

``` php
<?php

$mc = new MongoClient('mongodb://rs1.example.com,rs2.example.com');
$db = $mc->selectDB('test');

// Require that the majority of servers in the replica set acknowledge writes
// within three seconds.
$db->setWriteConcern('majority', 3000);
?>
```

### See Also

-   The
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    documentation.
-   <span class="function">MongoDB::getWriteConcern</span>

MongoDB::\_\_toString
=====================

The name of this database

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoDB::\_\_toString</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns this database's name.

Introduction
------------

Represents a MongoDB collection.

Collection names can use any character in the ASCII set. Some valid
collection names are "", "...", "my collection", and "\*&\#@".

User-defined collection names cannot contain the $ symbol. There are
certain system collections which use a $ in their names (e.g.,
local.oplog.$main), but it is a reserved character. If you attempt to
create and use a collection with a $ in the name, MongoDB will assert.

Class synopsis
--------------

**MongoCollection**

<span class="ooclass"> class **MongoCollection** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`MongoCollection::ASCENDING` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoCollection::DESCENDING` <span class="initializer"> = -1</span> ;

/\* Fields \*/

<span class="modifier">public</span> <span class="type">MongoDB</span>
`$db` <span class="initializer"> = **`NULL`**</span> ;

<span class="modifier">public</span> <span class="type">integer</span>
`$w` ;

<span class="modifier">public</span> <span class="type">integer</span>
`$wtimeout` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">aggregate</span> ( <span
class="methodparam"><span class="type">array</span> `$pipeline`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

<span class="modifier">public</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">aggregateCursor</span> ( <span
class="methodparam"><span class="type">array</span> `$command`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">batchInsert</span> ( <span
class="methodparam"><span class="type">array</span> `$a`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoDB</span> `$db`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> (\[ <span class="methodparam"><span
class="type">array</span> `$query`<span class="initializer"> =
array()</span></span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">createDBRef</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$document_or_id`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">createIndex</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">deleteIndex</span> ( <span
class="methodparam"><span class="type">string\|array</span>
`$keys`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">deleteIndexes</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">distinct</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">drop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ensureIndex</span> ( <span
class="methodparam"><span class="type">string\|array</span>
`$key|keys`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \] )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">find</span> (\[
<span class="methodparam"><span class="type">array</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$fields`<span
class="initializer"> = array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">findAndModify</span> ( <span
class="methodparam"><span class="type">array</span> `$query`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$update`</span> \[, <span class="methodparam"><span
class="type">array</span> `$fields`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">findOne</span> (\[ <span
class="methodparam"><span class="type">array</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$fields`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\]\] )

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">\_\_get</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getDBRef</span> ( <span
class="methodparam"><span class="type">array</span> `$ref`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getIndexInfo</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getReadPreference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getSlaveOkay</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getWriteConcern</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">group</span> ( <span class="methodparam"><span
class="type">mixed</span> `$keys`</span> , <span
class="methodparam"><span class="type">array</span> `$initial`</span> ,
<span class="methodparam"><span class="type">MongoCode</span>
`$reduce`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \] )

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span class="methodname">insert</span> (
<span class="methodparam"><span class="type">array\|object</span>
`$document`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \] )

<span class="modifier">public</span> <span
class="type">array\[MongoCommandCursor\]</span> <span
class="methodname">parallelCollectionScan</span> ( <span
class="methodparam"><span class="type">int</span> `$num_cursors`</span>
)

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span class="methodname">remove</span>
(\[ <span class="methodparam"><span class="type">array</span>
`$criteria`<span class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">save</span> ( <span class="methodparam"><span
class="type">array\|object</span> `$document`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSlaveOkay</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$ok`<span
class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setWriteConcern</span> ( <span
class="methodparam"><span class="type">mixed</span> `$w`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$wtimeout`</span> \] )

<span class="modifier">static protected</span> <span
class="type">string</span> <span class="methodname">toIndexString</span>
( <span class="methodparam"><span class="type">mixed</span>
`$keys`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span class="methodname">update</span> (
<span class="methodparam"><span class="type">array</span>
`$criteria`</span> , <span class="methodparam"><span
class="type">array</span> `$new_object`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">validate</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$scan_data`<span
class="initializer"> = **`FALSE`**</span></span> \] )

}

Predefined Constants
--------------------

**`MongoCollection::ASCENDING`**  
<span class="simpara"> Ascending direction for sorts and index creation.
</span>

**`MongoCollection::DESCENDING`**  
<span class="simpara"> Descending direction for sorts and index
creation. </span>

Fields
------

`db`  
The "parent" database for this collection.

`w`  
The number of servers to replicate a change to before returning success.
Value is inherited from the parent database. The <span
class="classname">MongoDB</span> class has a more detailed description
of how *w* works.

`wtimeout`  
The number of milliseconds to wait for *$this-\>w* replications to take
place. Value is inherited from the parent database. The <span
class="classname">MongoDB</span> class has a more detailed description
of how *wtimeout* works.

See Also
--------

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/glossary/#term-collection" class="link external">» collections</a>.

MongoCollection::aggregate
==========================

Perform an aggregation using the aggregation framework

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::aggregate</span> ( <span
class="methodparam"><span class="type">array</span> `$pipeline`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::aggregate</span> ( <span
class="methodparam"><span class="type">array</span> `$op`</span> \[,
<span class="methodparam"><span class="type">array</span> `$op`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$...`</span> \]\] )

The MongoDB
<a href="https://docs.mongodb.com/manual/core/aggregation-pipeline/" class="link external">» aggregation framework</a>
provides a means to calculate aggregated values without having to use
MapReduce. While MapReduce is powerful, it is often more difficult than
necessary for many simple aggregation tasks, such as totaling or
averaging field values.

This method accepts either a variable amount of pipeline operators, or a
single array of operators constituting the pipeline.

### Parameters

`pipeline`  
An array of pipeline operators.

`options`  
Options for the aggregation command. Valid options include:

-   *"allowDiskUse"*

    Allow aggregation stages to write to temporary files

-   *"cursor"*

    Options controlling the creation of the cursor object. This option
    causes the command to return a result document suitable for
    constructing a <span class="classname">MongoCommandCursor</span>. If
    you need to use this option, you should consider using <span
    class="methodname">MongoCollection::aggregateCursor</span>.

-   *"explain"*

    Return information on the processing of the pipeline.

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

Or

`op`  
First pipeline operator.

`op`  
The second pipeline operator.

`...`  
Additional pipeline operators.

### Return Values

The result of the aggregation as an array. The `ok` will be set to *1*
on success, *0* on failure.

### Errors/Exceptions

When an error occurs an array with the following keys will be returned:

-   <span class="simpara"> `errmsg` - containing the reason for the
    failure </span>
-   <span class="simpara"> `code` - the errorcode of the failure </span>
-   <span class="simpara"> `ok` - will be set to 0. </span>

### Changelog

| Version          | Description                       |
|------------------|-----------------------------------|
| PECL mongo 1.5.0 | Added optional `options` argument |

### Examples

**Example \#1 <span class="methodname">MongoCollection::aggregate</span>
example**

The following example aggregation operation pivots data to create a set
of author names grouped by tags applied to an article. Call the
aggregation framework by issuing the following command:

``` php
<?php
$m = new MongoClient("localhost");
$c = $m->selectDB("examples")->selectCollection("article");
$data = array (
    'title' => 'this is my title',
    'author' => 'bob',
    'posted' => new MongoDate,
    'pageViews' => 5,
    'tags' => array ( 'fun', 'good', 'fun' ),
    'comments' => array (
      array (
        'author' => 'joe',
        'text' => 'this is cool',
      ),
      array (
        'author' => 'sam',
        'text' => 'this is bad',
      ),
    ),
    'other' =>array (
      'foo' => 5,
    ),
);
$d = $c->insert($data, array("w" => 1));

$ops = array(
    array(
        '$project' => array(
            "author" => 1,
            "tags"   => 1,
        )
    ),
    array('$unwind' => '$tags'),
    array(
        '$group' => array(
            "_id" => array("tags" => '$tags'),
            "authors" => array('$addToSet' => '$author'),
        ),
    ),
);
$results = $c->aggregate($ops);
var_dump($results);
?>
```

The above example will output:

    array(2) {
      ["result"]=>
      array(2) {
        [0]=>
        array(2) {
          ["_id"]=>
          array(1) {
            ["tags"]=>
            string(4) "good"
          }
          ["authors"]=>
          array(1) {
            [0]=>
            string(3) "bob"
          }
        }
        [1]=>
        array(2) {
          ["_id"]=>
          array(1) {
            ["tags"]=>
            string(3) "fun"
          }
          ["authors"]=>
          array(1) {
            [0]=>
            string(3) "bob"
          }
        }
      }
      ["ok"]=>
      float(1)
    }

The following examples use the
<a href="https://media.mongodb.org/zips.json" class="link external">» zipcode data set</a>.
Use mongoimport to load this data set into your mongod instance.

**Example \#2 <span class="methodname">MongoCollection::aggregate</span>
example**

To return all states with a population greater than 10 million, use the
following aggregation operation:

``` php
<?php
$m = new MongoClient("localhost");
$c = $m->selectDB("test")->selectCollection("zips");

$pipeline = array(
    array(
        '$group' => array(
            '_id' => array('state' => '$state'),
            'totalPop' => array('$sum' => '$pop')
        )
    ),
    array(
        '$match' => array(
            'totalPop' => array('$gte' => 10 * 1000 * 1000)
        )
    ),
);
$out = $c->aggregate($pipeline);
var_dump($out);
?>
```

The above example will output something similar to:

    array(2) {
      ["result"]=>
      array(7) {
        [0]=>
        array(2) {
          ["_id"]=>
          string(2) "TX"
          ["totalPop"]=>
          int(16986510)
        }
        [1]=>
        array(2) {
          ["_id"]=>
          string(2) "PA"
          ["totalPop"]=>
          int(11881643)
        }
        [2]=>
        array(2) {
          ["_id"]=>
          string(2) "NY"
          ["totalPop"]=>
          int(17990455)
        }
        [3]=>
        array(2) {
          ["_id"]=>
          string(2) "IL"
          ["totalPop"]=>
          int(11430602)
        }
        [4]=>
        array(2) {
          ["_id"]=>
          string(2) "CA"
          ["totalPop"]=>
          int(29760021)
        }
        [5]=>
        array(2) {
          ["_id"]=>
          string(2) "OH"
          ["totalPop"]=>
          int(10847115)
        }
        [6]=>
        array(2) {
          ["_id"]=>
          string(2) "FL"
          ["totalPop"]=>
          int(12937926)
        }
      }
      ["ok"]=>
      float(1)
    }

**Example \#3 <span class="methodname">MongoCollection::aggregate</span>
example**

To return the average populations for cities in each state, use the
following aggregation operation:

``` php
<?php
$m = new MongoClient;
$c = $m->selectDB("test")->selectCollection("zips");

$out = $c->aggregate(
    array(
        '$group' => array(
            '_id' => array('state' => '$state', 'city' => '$city' ),
            'pop' => array('$sum' => '$pop' )
        )
    ),
    array(
        '$group' => array(
            '_id' => '$_id.state',
            'avgCityPop' => array('$avg' => '$pop')
        )
    )
);

var_dump($out);
?>
```

The above example will output something similar to:

    array(2) {
      ["result"]=>
      array(51) {
        [0]=>
        array(2) {
          ["_id"]=>
          string(2) "DC"
          ["avgCityPop"]=>
          float(303450)
        }
        [1]=>
        array(2) {
          ["_id"]=>
          string(2) "DE"
          ["avgCityPop"]=>
          float(14481.913043478)
        }
    ...
        [49]=>
        array(2) {
          ["_id"]=>
          string(2) "WI"
          ["avgCityPop"]=>
          float(7323.0074850299)
        }
        [50]=>
        array(2) {
          ["_id"]=>
          string(2) "WV"
          ["avgCityPop"]=>
          float(2759.1953846154)
        }
      }
      ["ok"]=>
      float(1)
    }

**Example \#4 <span class="methodname">MongoCollection::aggregate</span>
with command options**

To return information on how the pipeline will be processed we use the
*explain* command option:

``` php
<?php
$m = new MongoClient;
$c = $m->selectDB("test")->selectCollection("zips");

$pipeline = array(
    array(
        '$group' => array(
            '_id' => '$state',
           'totalPop' => array('$sum' => '$pop'),
        ),
    ),
    array(
        '$match' => array(
            'totalPop' => array('$gte' => 10 * 1000 * 1000)
        )
    ),
    array(
        '$sort' => array("totalPop" => -1),
    ),
);

$options = array("explain" => true);
$out = $c->aggregate($pipeline, $options);
var_dump($out);
?>
```

The above example will output something similar to:

    array(2) {
      ["stages"]=>
      array(4) {
        [0]=>
        array(1) {
          ["$cursor"]=>
          array(3) {
            ["query"]=>
            array(0) {
            }
            ["fields"]=>
            array(3) {
              ["pop"]=>
              int(1)
              ["state"]=>
              int(1)
              ["_id"]=>
              int(0)
            }
            ["plan"]=>
            array(4) {
              ["cursor"]=>
              string(11) "BasicCursor"
              ["isMultiKey"]=>
              bool(false)
              ["scanAndOrder"]=>
              bool(false)
              ["allPlans"]=>
              array(1) {
                [0]=>
                array(3) {
                  ["cursor"]=>
                  string(11) "BasicCursor"
                  ["isMultiKey"]=>
                  bool(false)
                  ["scanAndOrder"]=>
                  bool(false)
                }
              }
            }
          }
        }
        [1]=>
        array(1) {
          ["$group"]=>
          array(2) {
            ["_id"]=>
            string(6) "$state"
            ["totalPop"]=>
            array(1) {
              ["$sum"]=>
              string(4) "$pop"
            }
          }
        }
        [2]=>
        array(1) {
          ["$match"]=>
          array(1) {
            ["totalPop"]=>
            array(1) {
              ["$gte"]=>
              int(10000000)
            }
          }
        }
        [3]=>
        array(1) {
          ["$sort"]=>
          array(1) {
            ["sortKey"]=>
            array(1) {
              ["totalPop"]=>
              int(-1)
            }
          }
        }
      }
      ["ok"]=>
      float(1)
    }

### See Also

-   <span class="methodname">MongoCollection::aggregateCursor</span>
-   The MongoDB
    <a href="https://docs.mongodb.com/manual/core/aggregation-pipeline/" class="link external">» aggregation framework</a>

MongoCollection::aggregateCursor
================================

Execute an aggregation pipeline command and retrieve results through a
cursor

### Description

<span class="modifier">public</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">MongoCollection::aggregateCursor</span> ( <span
class="methodparam"><span class="type">array</span> `$command`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

With this method you can execute Aggregation Framework pipelines and
retrieve the results through a cursor, instead of getting just one
document back as you would with <span
class="methodname">MongoCollection::aggregate</span>. This method
returns a <span class="classname">MongoCommandCursor</span> object. This
cursor object implements the <span class="classname">Iterator</span>
interface just like the <span class="classname">MongoCursor</span>
objects that are returned by the <span
class="methodname">MongoCollection::find</span> method.

> **Note**: <span class="simpara"> The resulting <span
> class="classname">MongoCommandCursor</span> will inherit this
> collection's read preference. <span
> class="methodname">MongoCommandCursor::setReadPreference</span> may be
> used to change the read preference before iterating on the cursor.
> </span>

### Parameters

`pipeline`  
The Aggregation Framework pipeline to execute.

`options`  
Options for the aggregation command. Valid options include:

-   *"allowDiskUse"*

    Allow aggregation stages to write to temporary files

-   *"cursor"*

    It is possible to configure how many initial documents the server
    should return with the first result set. The default initial batch
    size is *101*. You can change it by adding the *batchSize* option:

    ``` php
    <?php
    $collection->aggregateCursor( 
        $pipeline,
        [ "cursor" => [ "batchSize" => 4 ] ]
    );
    ```

    This option only configures the size of the first batch. To
    configure the size of future batches, please use the <span
    class="methodname">MongoCommandCursor::batchSize</span> method on
    the returned <span class="classname">MongoCommandCursor</span>
    object.

-   *"explain"*

    Return information on the processing of the pipeline. This option
    may cause the command to return a result document that is unsuitable
    for constructing a <span
    class="classname">MongoCommandCursor</span>. If you need to use this
    option, you should consider using <span
    class="methodname">MongoCollection::aggregate</span>.

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

### Return Values

Returns a <span class="classname">MongoCommandCursor</span> object.
Because this implements the <span class="classname">Iterator</span>
interface you can iterate over each of the results as returned by the
command query. The <span class="classname">MongoCommandCursor</span>
also implements the <span class="classname">MongoCursorInterface</span>
interface which adds the <span
class="methodname">MongoCommandCursor::batchSize</span>, <span
class="methodname">MongoCommandCursor::dead</span>, <span
class="methodname">MongoCommandCursor::info</span> methods.

### Examples

**Example \#1 <span
class="function">MongoCollection::aggregateCursor</span> example**

Finding all of the distinct values for a key.

``` php
<?php
$m = new MongoClient;
$db = $m->test;
$people = $db->people;
$people->drop();

$people->insert(array("name" => "Joe", "points" => 4));
$people->insert(array("name" => "Molly", "points" => 43));
$people->insert(array("name" => "Sally", "points" => 22));
$people->insert(array("name" => "Joe", "points" => 22));
$people->insert(array("name" => "Molly", "points" => 87));

$ages = $people->aggregateCursor( [
        [ '$group' => [ '_id' => '$name', 'points' => [ '$sum' => '$points' ] ] ],
        [ '$sort' => [ 'points' => -1 ] ],
] );

foreach ($ages as $person) {
    echo "{$person['_id']}: {$person['points']}\n";
}

?>
```

The above example will output something similar to:

  
Molly: 130  
Joe: 26  
Sally: 22  

**Example \#2 <span
class="function">MongoCollection::aggregateCursor</span> example with
different initial batch size**

Finding all of the distinct values for a key.

``` php
<?php
$m = new MongoClient;
$db = $m->test;
$people = $db->people;
$people->drop();

/* Insert some sample data */
$people->insert(array("name" => "Joe", "points" => 4));
$people->insert(array("name" => "Molly", "points" => 43));
$people->insert(array("name" => "Sally", "points" => 22));
$people->insert(array("name" => "Joe", "points" => 22));
$people->insert(array("name" => "Molly", "points" => 87));

/* Run the command cursor */
$ages = $people->aggregateCursor(
    [
        [ '$group' => [ '_id' => '$name', 'points' => [ '$sum' => '$points' ] ] ],
        [ '$sort' => [ 'points' => -1 ] ],
    ],
    [ "cursor" => [ "batchSize" => 4 ] ]
);

foreach ($ages as $person) {
    echo "{$person['_id']}: {$person['points']}\n";
}

?>
```

The above example will output something similar to:

  
Molly: 130  
Joe: 26  
Sally: 22  

### See Also

-   <span class="methodname">MongoDB::command</span>
-   <span class="classname">MongoCommandCursor</span>
-   <span class="methodname">MongoCommandCursor::batchSize</span>
-   <span class="methodname">MongoCollection::aggregate</span>
-   The MongoDB
    <a href="https://docs.mongodb.com/manual/core/aggregation-pipeline/" class="link external">» aggregation framework</a>

MongoCollection::batchInsert
============================

Inserts multiple documents into this collection

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">MongoCollection::batchInsert</span> ( <span
class="methodparam"><span class="type">array</span> `$a`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = array()</span></span> \] )

### Parameters

`a`  
An array of arrays or objects. If any objects are used, they may not
have protected or private properties.

> **Note**:
>
> If the documents to insert do not have an *\_id* key or property, a
> new <span class="classname">MongoId</span> instance will be created
> and assigned to it. See <span
> class="function">MongoCollection::insert</span> for additional
> information on this behavior.

`options`  
An array of options for the batch of insert operations. Currently
available options include:

-   *"continueOnError"*

    Boolean, defaults to **`FALSE`**. If set, the database will not stop
    processing a bulk insert if one fails (eg due to duplicate IDs).
    This makes bulk insert behave similarly to a series of single
    inserts, except that calling <span
    class="function">MongoDB::lastError</span> will have an error set if
    any insert fails, not just the last one. If multiple errors occur,
    only the most recent will be reported by <span
    class="function">MongoDB::lastError</span>.

    > **Note**:
    >
    > Please note that *continueOnError* affects errors on the database
    > side only. If you try to insert a document that has errors (for
    > example it contains a key with an empty name), then the document
    > is not even transferred to the database as the driver detects this
    > error and bails out. *continueOnError* has no effect on errors
    > detected in the documents by the driver.

-   *"fsync"*

    Boolean, defaults to **`FALSE`**. If journaling is enabled, it works
    exactly like *"j"*. If journaling is not enabled, the write
    operation blocks until it is synced to database files on disk. If
    **`TRUE`**, an acknowledged insert is implied and this option will
    override setting *"w"* to *0*.

    > **Note**: <span class="simpara">If journaling is enabled, users
    > are strongly encouraged to use the *"j"* option instead of
    > *"fsync"*. Do not use *"fsync"* and *"j"* simultaneously, as that
    > will result in an error.</span>

-   *"j"*

    Boolean, defaults to **`FALSE`**. Forces the write operation to
    block until it is synced to the journal on disk. If **`TRUE`**, an
    acknowledged write is implied and this option will override setting
    *"w"* to *0*.

    > **Note**: <span class="simpara">If this option is used and
    > journaling is disabled, MongoDB 2.6+ will raise an error and the
    > write will fail; older server versions will simply ignore the
    > option.</span>

-   *"socketTimeoutMS"*

    This option specifies the time limit, in milliseconds, for socket
    communication. If the server does not respond within the timeout
    period, a <span class="classname">MongoCursorTimeoutException</span>
    will be thrown and there will be no way to determine if the server
    actually handled the write or not. A value of *-1* may be specified
    to block indefinitely. The default value for <span
    class="classname">MongoClient</span> is *30000* (30 seconds).

-   *"w"*

    See
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concerns</a>.
    The default value for <span class="classname">MongoClient</span> is
    *1*.

-   *"wTimeoutMS"*

    This option specifies the time limit, in milliseconds, for
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    acknowledgement. It is only applicable when *"w"* is greater than
    *1*, as the timeout pertains to replication. If the write concern is
    not satisfied within the time limit, a <span
    class="classname">MongoCursorException</span> will be thrown. A
    value of *0* may be specified to block indefinitely. The default
    value for <span class="classname">MongoClient</span> is *10000* (ten
    seconds).

The following options are deprecated and should no longer be used:

-   *"safe"*

    Deprecated. Please use the
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    *"w"* option.

-   *"timeout"*

    Deprecated alias for *"socketTimeoutMS"*.

-   *"wtimeout"*

    Deprecated alias for *"wTimeoutMS"*.

### Return Values

If the *w* parameter is set to acknowledge the write, returns an
associative array with the status of the inserts ("ok") and any error
that may have occurred ("err"). Otherwise, returns **`TRUE`** if the
batch insert was successfully sent, **`FALSE`** otherwise.

### Errors/Exceptions

Throws <span class="classname">MongoException</span> if any inserted
documents are empty or if they contains zero-length keys. Attempting to
insert an object with protected and private properties will cause a
zero-length key error.

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.5.0</td>
<td><p>Added the <em>"wTimeoutMS"</em> option, which replaces <em>"wtimeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"wtimeout"</em> is used.</p>
<p>Added the <em>"socketTimeoutMS"</em> option, which replaces <em>"timeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"timeout"</em> is used.</p>
<p>Emits <strong><code>E_DEPRECATED</code></strong> when <em>"safe"</em> is used.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.3.4</td>
<td>Added <em>"wtimeout"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.3.0</td>
<td>Added <em>"w"</em> option.</td>
</tr>
<tr class="even">
<td>PECL mongo 1.2.7</td>
<td>Added <em>"continueOnError"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.9</td>
<td><p>Added ability to pass integers to the <em>"safe"</em> option, which previously only accepted booleans.</p>
<p>Added <em>"fsync"</em> option.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.5</td>
<td>Added <code class="parameter">options</code> parameter.</td>
</tr>
</tbody>
</table>

### Examples

**Example \#1 <span class="function">MongoCollection::batchInsert</span>
example**

Batch insertion is a quick way to add many elements to the database at
once

``` php
<?php

$users = array();
for ($i = 0; $i<100; $i++) {
  $users[] = array('username' => 'user'.$i, 'i' => $i);
}

$mongo = new MongoClient();
$collection = $mongo->my_db->users;
$collection->drop();

$collection->batchInsert($users);

foreach ($users as $user) {
  echo $user['_id']."\n"; // populated with instanceof MongoId
}

$users = $collection->find()->sort(array('i' => 1));
foreach ($users as $user) {
    var_dump($user['username']);
}

?>
```

The above example will output something similar to:

    4bf43ac68ead0e1971000000
    4bf43ac68ead0e1971010000
    4bf43ac68ead0e1971020000
    ...
    string(5) "user1"
    string(5) "user2"
    string(5) "user3"
    ...

**Example \#2 <span class="function">MongoCollection::batchInsert</span>
example with ignoring errors**

``` php
<?php

$con = new Mongo;
$db = $con->demo;

$doc1 = array(
        '_id' => new MongoId('4cb4ab6d7addf98506010001'),
        'id' => 1,
        'desc' => "ONE",
);
$doc2 = array(
        '_id' => new MongoId('4cb4ab6d7addf98506010002'),
        'id' => 2,
        'desc' => "TWO",
);
$doc3 = array(
        '_id' => new MongoId('4cb4ab6d7addf98506010002'), // same _id as above
        'id' => 3,
        'desc' => "THREE",
);
$doc4 = array(
        '_id' => new MongoId('4cb4ab6d7addf98506010004'),
        'id' => 4,
        'desc' => "FOUR",
);

$c = $db->selectCollection('c');
$c->batchInsert(
    array($doc1, $doc2, $doc3, $doc4),
    array('continueOnError' => true)
);

$docs = $c->find();
foreach ($docs as $doc) {
    var_dump($doc['desc']);
}
?>
```

The above example will output something similar to:

    string(3) "ONE"
    string(3) "TWO"
    string(4) "FOUR"

### See Also

-   <span class="function">MongoCollection::insert</span>
-   <span class="function">MongoCollection::update</span>
-   <span class="function">MongoCollection::find</span>
-   <span class="function">MongoCollection::remove</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/tutorial/insert-documents/" class="link external">» insert</a>.

MongoCollection::\_\_construct
==============================

Creates a new collection

### Description

<span class="modifier">public</span> <span
class="methodname">MongoCollection::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoDB</span> `$db`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

### Parameters

<span class="type">MongoDB</span> `db`  
Parent database.

<!-- -->

`name`  
Name for this collection.

### Return Values

Returns a new collection object.

### Errors/Exceptions

Throws default exception if the collection name is invalid.

MongoCollection::count
======================

Counts the number of documents in this collection

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoCollection::count</span> (\[ <span
class="methodparam"><span class="type">array</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

### Parameters

`query`  
Associative array or object with fields to match.

`options`  
An array of options for the index creation. Currently available options
include:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Type</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><var class="varname">hint</var></td>
<td><span class="type">mixed</span></td>
<td><p>Index to use for the query. If a string is passed, it should correspond to an index name. If an array or object is passed, it should correspond to the specification used to create the index (i.e. the first argument to <span class="function">MongoCollection::createIndex</span>).</p>
<span class="simpara">This option is only supported in MongoDB 2.6+.</span></td>
</tr>
<tr class="even">
<td><var class="varname">limit</var></td>
<td><span class="type">integer</span></td>
<td>The maximum number of matching documents to return.</td>
</tr>
<tr class="odd">
<td><var class="varname">maxTimeMS</var></td>
<td><span class="type">integer</span></td>
<td><p>Specifies a cumulative time limit in milliseconds for processing the operation (does not include idle time). If the operation is not completed within the timeout period, a <span class="classname">MongoExecutionTimeoutException</span> will be thrown.</p>
<span class="simpara">This option is only supported in MongoDB 2.6+.</span></td>
</tr>
<tr class="even">
<td><var class="varname">skip</var></td>
<td><span class="type">integer</span></td>
<td>The number of matching documents to skip before returning results.</td>
</tr>
</tbody>
</table>

### Return Values

Returns the number of documents matching the query.

### Errors/Exceptions

Throws <span class="classname">MongoResultException</span> if the server
could not execute the command due to an error.

Throws <span class="classname">MongoExecutionTimeoutException</span> if
command execution was terminated due to `maxTimeMS`.

### Changelog

| Version          | Description                                                                                                                                 |
|------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.6.0 | The second parameter is now an `options` array. Passing `limit` and `skip` as the second and third parameters, respectively, is deprecated. |
| PECL mongo 1.0.7 | Added `limit` and `skip` as second and third parameters, respectively.                                                                      |

### Examples

**Example \#1 <span class="function">MongoCollection::count</span>
example**

``` php
<?php

$collection->insert(array('x'=>1));
$collection->insert(array('x'=>2));
$collection->insert(array('x'=>3));

var_dump($collection->count());
var_dump($collection->count(array('x'=>1)));

?>
```

The above example will output something similar to:

    int(3)
    int(1)

MongoCollection::createDBRef
============================

Creates a database reference

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::createDBRef</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$document_or_id`</span> )

### Parameters

`document_or_id`  
If an array or object is given, its *\_id* field will be used as the
reference ID. If a <span class="classname">MongoId</span> or scalar is
given, it will be used as the reference ID.

### Return Values

Returns a database reference array.

If an array without an *\_id* field was provided as the
*document\_or\_id* parameter, **`NULL`** will be returned.

### Examples

**Example \#1 <span
class="methodname">MongoCollection::createDBRef</span> example**

``` php
<?php

$songs = $db->songs;
$playlists = $db->playlists;

// create a reference to a song
$manamana = $songs->findOne(array('title' => 'Ma na ma na'));
$refToSong = $songs->createDBRef($manamana);

// add the reference to my playlist
$playlists->update(array('username' => 'me'), array('$push' => array('songlist' => $refToSong)));

?>
```

### See Also

-   <span class="methodname">MongoCollection::getDBRef</span>

MongoCollection::createIndex
============================

Creates an index on the specified field(s) if it does not already exist

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCollection::createIndex</span> ( <span
class="methodparam"><span class="type">array</span> `$keys`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = array()</span></span> \] )

Creates an index on the specified field(s) if it does not already exist.
Fields may be indexed with a direction (e.g. ascending or descending) or
a special type (e.g. text, geospatial, hashed).

> **Note**:
>
> This method will use the
> <a href="https://docs.mongodb.com/manual/reference/command/createIndexes" class="link external">» createIndexes</a>
> database command when communicating with MongoDB 2.6+. For previous
> database versions, the method will perform an insert operation on the
> special *system.indexes* collection.

### Parameters

`keys`  
An array specifying the index's fields as its keys. For each field, the
value is either the index direction or
<a href="https://docs.mongodb.com/manual/core/index-types/" class="link external">» index type</a>.
If specifying direction, specify *1* for ascending or *-1* for
descending.

`options`  
An array of options for the index creation. We pass all given options
straight to the server, but a non-exhaustive list of currently available
options include:

-   *"unique"*

    Specify **`TRUE`** to create a unique index. The default value is
    **`FALSE`**. This option applies only to ascending/descending
    indexes.

    > **Note**:
    >
    > When MongoDB indexes a field, if a document does not have a value
    > for the field, a **`NULL`** value is indexed. If multiple
    > documents do not contain a field, a unique index will reject all
    > but the first of those documents. The *"sparse"* option may be
    > used to overcome this, since it will prevent documents without the
    > field from being indexed.

-   *"sparse"*

    Specify **`TRUE`** to create a sparse index, which only indexes
    documents containing a specified field. The default value is
    **`FALSE`**.

-   *"expireAfterSeconds"*

    The value of this option should specify the number of seconds after
    which a document should be considered expired and automatically
    removed from the collection. This option is only compatible with
    single-field indexes where the field will contain <span
    class="classname">MongoDate</span> values.

    > **Note**:
    >
    > This feature is available in MongoDB 2.2+. See
    > <a href="https://docs.mongodb.com/manual/tutorial/expire-data/" class="link external">» Expire Data from Collections by Setting TTL</a>
    > for more information.

-   *"name"*

    A optional name that uniquely identifies the index.

    > **Note**:
    >
    > By default, the driver will generate an index name based on the
    > index's field(s) and ordering or type. For example, a compound
    > index *array("x" =\> 1, "y" =\> -1)* would be named
    > *"x\_1\_y\_-1"* and a geospatial index *array("loc" =\>
    > "2dsphere")* would be named *"loc\_2dsphere"*. For indexes with
    > many fields, it is possible that the generated name might exceed
    > MongoDB's
    > <a href="https://docs.mongodb.com/manual/reference/limits/#Index-Name-Length" class="link external">» limit for index names</a>.
    > The *"name"* option may be used in that case to supply a shorter
    > name.

-   *"background"*

    Builds the index in the background so that building an index does
    *not* block other database activities. Specify **`TRUE`** to build
    in the background. The default value is **`FALSE`**.

    **Warning**
    Prior to MongoDB 2.6.0, index builds on secondaries were executed as
    foreground operations, irrespective of this option. See
    <a href="https://docs.mongodb.com/manual/tutorial/build-indexes-on-replica-sets/" class="link external">» Building Indexes with Replica Sets</a>
    for more information.

-   *"socketTimeoutMS"*

    This option specifies the time limit, in milliseconds, for socket
    communication. If the server does not respond within the timeout
    period, a <span class="classname">MongoCursorTimeoutException</span>
    will be thrown and there will be no way to determine if the server
    actually handled the write or not. A value of *-1* may be specified
    to block indefinitely. The default value for <span
    class="classname">MongoClient</span> is *30000* (30 seconds).

The following option may be used with MongoDB 2.6+:

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

The following options may be used with MongoDB versions before 2.8:

-   *"dropDups"*

    Specify **`TRUE`** to force creation of a unique index where the
    collection may contain duplicate values for a key. MongoDB will
    index the first occurrence of a key and delete all subsequent
    documents from the collection that contain a duplicate value for
    that key. The default value is **`FALSE`**.

    **Warning**
    *"dropDups"* may delete data from your database. Use with extreme
    caution.

    > **Note**:
    >
    > This option is not supported on MongoDB 2.8+. Index creation will
    > fail if the collection contains duplicate values.

The following options may be used with MongoDB versions before 2.6:

-   *"w"*

    See
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concerns</a>.
    The default value for <span class="classname">MongoClient</span> is
    *1*.

-   *"wTimeoutMS"*

    This option specifies the time limit, in milliseconds, for
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    acknowledgement. It is only applicable when *"w"* is greater than
    *1*, as the timeout pertains to replication. If the write concern is
    not satisfied within the time limit, a <span
    class="classname">MongoCursorException</span> will be thrown. A
    value of *0* may be specified to block indefinitely. The default
    value for <span class="classname">MongoClient</span> is *10000* (ten
    seconds).

The following options are deprecated and should no longer be used:

-   *"safe"*

    Deprecated. Please use the
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    *"w"* option.

-   *"timeout"*

    Deprecated alias for *"socketTimeoutMS"*.

-   *"wtimeout"*

    Deprecated alias for *"wTimeoutMS"*.

### Return Values

Returns an array containing the status of the index creation. The array
contains whether the operation succeeded (*"ok"*), the number of indexes
before and after the operation (*"numIndexesBefore"* and
*"numIndexesAfter"*), and whether the collection that the index belongs
to has been created (*"createdCollectionAutomatically"*). If the index
already existed and did not need to be created, a *"note"* field may be
present in lieu of *"numIndexesAfter"*.

With MongoDB 2.4 and earlier, a status document is only returned if the
<a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
is at least *1*. Otherwise, **`TRUE`** is returned. The fields in the
status document are different, except for the *"ok"* field, which
signals whether the index creation was successful. Additional fields are
described in the documentation for <span
class="function">MongoCollection::insert</span>.

### Errors/Exceptions

Throws <span class="classname">MongoException</span> if the index name
is longer than 128 bytes, or if the index specification is not an array.

Throws <span class="classname">MongoDuplicateKeyException</span> if the
server could not create the unique index due to conflicting documents.

Throws <span class="classname">MongoResultException</span> if the server
could not create the index due to an error.

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

### Examples

**Example \#1 <span class="function">MongoCollection::createIndex</span>
example**

``` php
<?php

$c = new MongoCollection($db, 'foo');

// create an index on 'x' ascending
$c->createIndex(array('x' => 1));

// create a unique index on 'y'
$c->createIndex(array('y' => 1), array('unique' => true));

// create a compound index on 'za' ascending and 'zb' descending
$c->createIndex(array('za' => 1, 'zb' => -1));

?>
```

**Example \#2 Geospatial Indexing**

Mongo supports geospatial indexes, which allow you to search for
documents near a given location or within a shape. The following example
creates a geospatial index on the *"loc"* field:

``` php
<?php

$collection->createIndex(array('loc' => '2dsphere'));

?>
```

**Example \#3 Drop duplicates example**

``` php
<?php

$collection->insert(array('username' => 'joeschmoe'));
$collection->insert(array('username' => 'joeschmoe'));

/* Index creation fails, since you cannot create a unique index on a field when
 * duplicates exist.
 */
$collection->createIndex(array('username' => 1), array('unique' => 1));

/* MongoDB will one of the conflicting documents and allow the unique index to
 * be created.
 */
$collection->createIndex(array('username' => 1), array('unique' => 1, 'dropDups' => 1));

/* We now have a unique index and subsequent inserts with the same username will
 * fail.
 */
$collection->insert(array('username' => 'joeschmoe'));

?>
```

### See Also

-   <span class="methodname">MongoCollection::deleteIndex</span>
-   <span class="methodname">MongoCollection::deleteIndexes</span>
-   The MongoDB
    <a href="https://docs.mongodb.com/manual/indexes/" class="link external">» index</a>
    and
    <a href="https://docs.mongodb.com/manual/core/index-types/" class="link external">» index type</a>
    documentation.

MongoCollection::deleteIndex
============================

Deletes an index from this collection

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::deleteIndex</span> ( <span
class="methodparam"><span class="type">string\|array</span>
`$keys`</span> )

This method is identical to:

``` php
<?php

public function deleteIndexes($keys) {
  $indexName = $this->toIndexString($keys);

  return $this->db->command(array(
    "deleteIndexes" => $this->getName(),
    "index" => $indexName,
  ));
}

?>
```

Each index is given a unique name when it is created. This is often
generated by the driver based on the index key(s) and order/type, but
custom names may also be specified with <span
class="function">MongoCollection::createIndex</span>'s *"name"* option).

Unfortunately, <span
class="function">MongoCollection::deleteIndex</span> cannot delete
custom-named indexes due to a backwards compatibility issue. When a
string argument is provided, it is assumed to be the single field name
in an ascending index (e.g. the name *"x\_1"* would be used for the
argument *"x"*). If an array or object is provided, an index name is
generated just as if that argument was passed to <span
class="function">MongoCollection::createIndex</span>.

In order to delete a custom-named index with the PHP driver, the
*deleteIndexes* database command must be used. For instance, an index
named "myIndex" could be deleted with the PHP driver by running:

``` php
<?php

$db->command(array(
  "deleteIndexes" => $collection->getName(),
  "index" => "myIndex",
));

?>
```

To determine the name of an index with the PHP driver, you can query the
*system.indexes* collection of a database and look for the *"name"*
field of each result. The *"ns"* field will indicate the collection to
which each index belongs.

### Parameters

`keys`  
An array specifying the index's fields as its keys. For each field, the
value is either the index direction or
<a href="https://docs.mongodb.com/manual/core/index-types/" class="link external">» index type</a>.
If specifying direction, specify *1* for ascending or *-1* for
descending.

If a string is provided, it is assumed to be the single field name in an
ascending index.

### Return Values

Returns the database response.

### Examples

**Example \#1 <span class="function">MongoCollection::deleteIndex</span>
example**

This example passes the function string and array parameters.

``` php
<?php

$m = new MongoClient();
$c = $m->example->indices;

// create and remove a simple index
$c->createIndex(array("i"=>1));
$c->deleteIndex("i");

// create and remove a multi-key index
$c->ensureIndex(array("j" => 1, "k" => 1));
$c->deleteIndex(array("j" => 1, "k" => 1));

?>
```

### See Also

-   <span class="methodname">MongoCollection::createIndex</span>
-   <span class="methodname">MongoCollection::deleteIndexes</span>
-   <span class="methodname">MongoCollection::toIndexString</span>
-   The MongoDB
    <a href="https://docs.mongodb.com/manual/indexes/" class="link external">» index</a>
    and
    <a href="https://docs.mongodb.com/manual/core/index-types/" class="link external">» index type</a>
    documentation.

MongoCollection::deleteIndexes
==============================

Delete all indices for this collection

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::deleteIndexes</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the database response.

### Examples

**Example \#1 <span
class="function">MongoCollection::deleteIndexes</span> example**

This example demonstrates how to delete all indexes from a collection
and the response to expect.

``` php
<?php

$collection = $mongo->my_db->articles;
$response = $collection->deleteIndexes();
print_r($response);

?>
```

The above example will output something similar to:

    Array
    (
        [nIndexesWas] => 1
        [msg] => all indexes deleted for collection
        [ok] => 1
    )

### See Also

-   <span class="methodname">MongoCollection::createIndex</span>
-   <span class="methodname">MongoCollection::deleteIndex</span>

MongoCollection::distinct
=========================

Retrieve a list of distinct values for the given key across a collection

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::distinct</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$query`</span> \] )

The distinct command returns a list of distinct values for the given key
across a collection.

### Parameters

`key`  
The key to use.

`query`  
An optional query parameters

### Return Values

Returns an array of distinct values, or **`FALSE`** on failure

### Examples

**Example \#1 <span class="methodname">MongoCollection::distinct</span>
example**

``` php
<?php
$m = new Mongo;
$db = $m->selectDB("test");
$db->dropCollection("distinct");
$c = $db->distinct;

$c->insert(array("stuff" => "bar", "zip-code" => 10010));
$c->insert(array("stuff" => "foo", "zip-code" => 10010));
$c->insert(array("stuff" => "bar", "zip-code" => 99701), array("w" => 1));

$retval = $c->distinct("zip-code");
var_dump($retval);

$retval = $c->distinct("zip-code", array("stuff" => "foo"));
var_dump($retval);

$retval = $c->distinct("zip-code", array("stuff" => "bar"));
var_dump($retval);

?>
```

The above example will output:

    array(2) {
      [0]=>
      int(10010)
      [1]=>
      int(99701)
    }
    array(1) {
      [0]=>
      int(10010)
    }
    array(2) {
      [0]=>
      int(10010)
      [1]=>
      int(99701)
    }

**Example \#2 <span class="methodname">MongoCollection::distinct</span>
example on a embedded document**

``` php
<?php
$c->insert(array("user" => array("points" => 25)));
$c->insert(array("user" => array("points" => 31)));
$c->insert(array("user" => array("points" => 25)));

$retval = $c->distinct("user.points");
var_dump($retval);

$retval = $c->distinct("user.nonexisting");
var_dump($retval);
?>
```

The above example will output:

    array(2) {
      [0]=>
      int(25)
      [1]=>
      int(31)
    }
    array(0) {
    }

MongoCollection::drop
=====================

Drops this collection

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::drop</span> ( <span
class="methodparam">void</span> )

Drops this collection and deletes its indices.

### Parameters

This function has no parameters.

### Return Values

Returns the database response.

### Examples

**Example \#1 <span class="function">MongoCollection::drop</span>
example**

This example demonstrates how to drop a collection and the response to
expect.

``` php
<?php

$collection = $mongo->my_db->articles;
$response = $collection->drop();
print_r($response);

?>
```

The above example will output something similar to:

    Array
    (
        [nIndexesWas] => 1
        [msg] => all indexes deleted for collection
        [ns] => my_db.articles
        [ok] => 1
    )

MongoCollection::ensureIndex
============================

Creates an index on the specified field(s) if it does not already exist

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCollection::ensureIndex</span> ( <span
class="methodparam"><span class="type">string\|array</span>
`$key|keys`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \] )

**Warning**

This method is deprecated since version 1.5.0. Please use <span
class="methodname">MongoCollection::createIndex</span> instead.

Creates an index on the specified field(s) if it does not already exist.
Fields may be indexed with a direction (e.g. ascending or descending) or
a special type (e.g. text, geospatial, hashed).

> **Note**:
>
> This method will use the
> <a href="https://docs.mongodb.com/manual/reference/command/createIndexes" class="link external">» createIndexes</a>
> database command when communicating with MongoDB 2.6+. For previous
> database versions, the method will perform an insert operation on the
> special *system.indexes* collection.

### Parameters

`keys`  
An array specifying the index's fields as its keys. For each field, the
value is either the index direction or
<a href="https://docs.mongodb.com/manual/core/index-types/" class="link external">» index type</a>.
If specifying direction, specify *1* for ascending or *-1* for
descending.

`options`  
An array of options for the index creation. Currently available options
include:

-   *"unique"*

    Specify **`TRUE`** to create a unique index. The default value is
    **`FALSE`**. This option applies only to ascending/descending
    indexes.

    > **Note**:
    >
    > When MongoDB indexes a field, if a document does not have a value
    > for the field, a **`NULL`** value is indexed. If multiple
    > documents do not contain a field, a unique index will reject all
    > but the first of those documents. The *"sparse"* option may be
    > used to overcome this, since it will prevent documents without the
    > field from being indexed.

-   *"sparse"*

    Specify **`TRUE`** to create a sparse index, which only indexes
    documents containing a specified field. The default value is
    **`FALSE`**.

-   *"expireAfterSeconds"*

    The value of this option should specify the number of seconds after
    which a document should be considered expired and automatically
    removed from the collection. This option is only compatible with
    single-field indexes where the field will contain <span
    class="classname">MongoDate</span> values.

    > **Note**:
    >
    > This feature is available in MongoDB 2.2+. See
    > <a href="https://docs.mongodb.com/manual/tutorial/expire-data/" class="link external">» Expire Data from Collections by Setting TTL</a>
    > for more information.

-   *"name"*

    A optional name that uniquely identifies the index.

    > **Note**:
    >
    > By default, the driver will generate an index name based on the
    > index's field(s) and ordering or type. For example, a compound
    > index *array("x" =\> 1, "y" =\> -1)* would be named
    > *"x\_1\_y\_-1"* and a geospatial index *array("loc" =\>
    > "2dsphere")* would be named *"loc\_2dsphere"*. For indexes with
    > many fields, it is possible that the generated name might exceed
    > MongoDB's
    > <a href="https://docs.mongodb.com/manual/reference/limits/#Index-Name-Length" class="link external">» limit for index names</a>.
    > The *"name"* option may be used in that case to supply a shorter
    > name.

-   *"background"*

    Builds the index in the background so that building an index does
    *not* block other database activities. Specify **`TRUE`** to build
    in the background. The default value is **`FALSE`**.

    **Warning**
    Prior to MongoDB 2.6.0, index builds on secondaries were executed as
    foreground operations, irrespective of this option. See
    <a href="https://docs.mongodb.com/manual/tutorial/build-indexes-on-replica-sets/" class="link external">» Building Indexes with Replica Sets</a>
    for more information.

-   *"socketTimeoutMS"*

    This option specifies the time limit, in milliseconds, for socket
    communication. If the server does not respond within the timeout
    period, a <span class="classname">MongoCursorTimeoutException</span>
    will be thrown and there will be no way to determine if the server
    actually handled the write or not. A value of *-1* may be specified
    to block indefinitely. The default value for <span
    class="classname">MongoClient</span> is *30000* (30 seconds).

The following option may be used with MongoDB 2.6+:

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

The following options may be used with MongoDB versions before 2.8:

-   *"dropDups"*

    Specify **`TRUE`** to force creation of a unique index where the
    collection may contain duplicate values for a key. MongoDB will
    index the first occurrence of a key and delete all subsequent
    documents from the collection that contain a duplicate value for
    that key. The default value is **`FALSE`**.

    **Warning**
    *"dropDups"* may delete data from your database. Use with extreme
    caution.

    > **Note**:
    >
    > This option is not supported on MongoDB 2.8+. Index creation will
    > fail if the collection contains duplicate values.

The following options may be used with MongoDB versions before 2.6:

-   *"w"*

    See
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concerns</a>.
    The default value for <span class="classname">MongoClient</span> is
    *1*.

-   *"wTimeoutMS"*

    This option specifies the time limit, in milliseconds, for
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    acknowledgement. It is only applicable when *"w"* is greater than
    *1*, as the timeout pertains to replication. If the write concern is
    not satisfied within the time limit, a <span
    class="classname">MongoCursorException</span> will be thrown. A
    value of *0* may be specified to block indefinitely. The default
    value for <span class="classname">MongoClient</span> is *10000* (ten
    seconds).

The following options are deprecated and should no longer be used:

-   *"safe"*

    Deprecated. Please use the
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    *"w"* option.

-   *"timeout"*

    Deprecated alias for *"socketTimeoutMS"*.

-   *"wtimeout"*

    Deprecated alias for *"wTimeoutMS"*.

### Return Values

Returns an array containing the status of the index creation. The array
contains whether the operation succeeded (*"ok"*), the number of indexes
before and after the operation (*"numIndexesBefore"* and
*"numIndexesAfter"*), and whether the collection that the index belongs
to has been created (*"createdCollectionAutomatically"*). If the index
already existed and did not need to be created, a *"note"* field may be
present in lieu of *"numIndexesAfter"*.

With MongoDB 2.4 and earlier, a status document is only returned if the
<a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
is at least *1*. Otherwise, **`TRUE`** is returned. The fields in the
status document are different, except for the *"ok"* field, which
signals whether the index creation was successful. Additional fields are
described in the documentation for <span
class="function">MongoCollection::insert</span>.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.5.0</td>
<td><p>Renamed the <em>"wtimeout"</em> option to <em>"wTimeoutMS"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"wtimeout"</em> is used.</p>
<p>Renamed the <em>"timeout"</em> option to <em>"socketTimeoutMS"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"timeout"</em> is used.</p>
<p>Emits <strong><code>E_DEPRECATED</code></strong> when <em>"safe"</em> is used.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.3.4</td>
<td>Added <em>"wtimeout"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.3.0</td>
<td><p>Added <em>"w"</em> option.</p>
<p>The <code class="parameter">options</code> parameter no longer accepts a boolean to signify a unique index. Instead, this now has to be done with <em>array('unique' =&gt; true)</em>.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.2.11</td>
<td>Emits <strong><code>E_DEPRECATED</code></strong> when <code class="parameter">options</code> is <span class="type">scalar</span>.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.2.0</td>
<td>Added <em>"timeout"</em> option.</td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.11</td>
<td><p>The <em>"safe"</em> option will trigger a primary failover, if necessary.</p>
<p><span class="classname">MongoException</span> will be thrown if the index name (either generated or set) is longer than 128 bytes.</p></td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.5</td>
<td>Added the <em>"name"</em> option to override index name creation.</td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.2</td>
<td>Changed <code class="parameter">options</code> parameter from boolean to array. Pre-1.0.2, the second parameter was an optional boolean value specifying a unique index.</td>
</tr>
</tbody>
</table>

### Errors/Exceptions

Throws <span class="classname">MongoException</span> if the index name
is longer than 128 bytes, or if the index specification is not an array.

Throws <span class="classname">MongoDuplicateKeyException</span> if the
server could not create the unique index due to conflicting documents.

Throws <span class="classname">MongoResultException</span> if the server
could not create the index due to an error.

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

### Examples

**Example \#1 <span class="function">MongoCollection::ensureIndex</span>
example**

``` php
<?php

$c = new MongoCollection($db, 'foo');

// create an index on 'x' ascending
$c->ensureIndex(array('x' => 1));

// create a unique index on 'y'
$c->ensureIndex(array('y' => 1), array('unique' => true));

// create a compound index on 'za' ascending and 'zb' descending
$c->ensureIndex(array('za' => 1, 'zb' => -1));

?>
```

**Example \#2 Geospatial Indexing**

Mongo supports geospatial indexes, which allow you to search for
documents near a given location or within a shape. The following example
creates a geospatial index on the *"loc"* field:

``` php
<?php

$collection->ensureIndex(array('loc' => '2dsphere'));

?>
```

**Example \#3 Drop duplicates example**

``` php
<?php

$collection->insert(array('username' => 'joeschmoe'));
$collection->insert(array('username' => 'joeschmoe'));

/* Index creation fails, since you cannot create a unique index on a field when
 * duplicates exist.
 */
$collection->ensureIndex(array('username' => 1), array('unique' => 1));

/* MongoDB will one of the conflicting documents and allow the unique index to
 * be created.
 */
$collection->ensureIndex(array('username' => 1), array('unique' => 1, 'dropDups' => 1));

/* We now have a unique index and subsequent inserts with the same username will
 * fail.
 */
$collection->insert(array('username' => 'joeschmoe'));

?>
```

### See Also

-   <span class="methodname">MongoCollection::createIndex</span>
-   <span class="methodname">MongoCollection::deleteIndex</span>
-   <span class="methodname">MongoCollection::deleteIndexes</span>
-   The MongoDB
    <a href="https://docs.mongodb.com/manual/indexes/" class="link external">» index</a>
    and
    <a href="https://docs.mongodb.com/manual/core/index-types/" class="link external">» index type</a>
    documentation.

MongoCollection::find
=====================

Queries this collection, returning a <span
class="classname">MongoCursor</span> for the result set

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCollection::find</span> (\[ <span
class="methodparam"><span class="type">array</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$fields`<span
class="initializer"> = array()</span></span> \]\] )

### Parameters

`query`  
The fields for which to search. MongoDB's query language is quite
extensive. The PHP driver will in almost all cases pass the query
straight through to the server, so reading the MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/method/db.collection.find/" class="link external">» find</a>
is a good idea.

**Warning**
Please make sure that for all special query operators (starting with
*$*) you use single quotes so that PHP doesn't try to replace
*"$exists"* with the value of the variable *$exists*.

`fields`  
Fields of the results to return. The array is in the format
*array('fieldname' =\> true, 'fieldname2' =\> true)*. The *\_id* field
is always returned.

### Return Values

Returns a cursor for the search results.

### Examples

**Example \#1 <span class="function">MongoCollection::find</span>
example**

This example demonstrates basic search options.

``` php
<?php

$m = new MongoClient();
$db = $m->selectDB('test');
$collection = new MongoCollection($db, 'produce');

// search for fruits
$fruitQuery = array('Type' => 'Fruit');

$cursor = $collection->find($fruitQuery);
foreach ($cursor as $doc) {
    var_dump($doc);
}

// search for produce that is sweet. Taste is a child of Details. 
$sweetQuery = array('Details.Taste' => 'Sweet');
echo "Sweet\n";
$cursor = $collection->find($sweetQuery);
foreach ($cursor as $doc) {
    var_dump($doc);
}

?>
```

The above example will output:

    array(4) {
      ["_id"]=>
      object(MongoId)#7 (1) {
        ["$id"]=>
        string(24) "50a87dd084f045a19b220dd6"
      }
      ["Name"]=>
      string(5) "Apple"
      ["Type"]=>
      string(5) "Fruit"
      ["Details"]=>
      array(2) {
        ["Taste"]=>
        string(5) "Sweet"
        ["Colour"]=>
        string(3) "Red"
      }
    }
    array(4) {
      ["_id"]=>
      object(MongoId)#8 (1) {
        ["$id"]=>
        string(24) "50a87de084f045a19b220dd7"
      }
      ["Name"]=>
      string(5) "Lemon"
      ["Type"]=>
      string(5) "Fruit"
      ["Details"]=>
      array(2) {
        ["Taste"]=>
        string(4) "Sour"
        ["Colour"]=>
        string(5) "Green"
      }
    }

    Sweet:
    array(4) {
      ["_id"]=>
      object(MongoId)#7 (1) {
        ["$id"]=>
        string(24) "50a87dd084f045a19b220dd6"
      }
      ["Name"]=>
      string(5) "Apple"
      ["Type"]=>
      string(5) "Fruit"
      ["Details"]=>
      array(2) {
        ["Taste"]=>
        string(5) "Sweet"
        ["Colour"]=>
        string(3) "Red"
      }
    }

See <span class="classname">MongoCursor</span> for more information how
to work with cursors.

**Example \#2 <span class="function">MongoCollection::find</span>
example**

This example demonstrates how to search for a range.

``` php
<?php

$m = new MongoClient();
$db = $m->selectDB('test');
$collection = new MongoCollection($db, 'phpmanual');

// search for documents where 5 < x < 20
$rangeQuery = array('x' => array( '$gt' => 5, '$lt' => 20 ));

$cursor = $collection->find($rangeQuery);
foreach ($cursor as $doc) {
    var_dump($doc);
}

?>
```

The above example will output:

    array(2) {
      ["_id"]=>
      object(MongoId)#10 (1) {
        ["$id"]=>
        string(24) "4ebc3e3710b89f2349000000"
      }
      ["x"]=>
      int(12)
    }
    array(2) {
      ["_id"]=>
      object(MongoId)#11 (1) {
        ["$id"]=>
        string(24) "4ebc3e3710b89f2349000001"
      }
      ["x"]=>
      int(12)
    }

See <span class="classname">MongoCursor</span> for more information how
to work with cursors.

**Example \#3 <span class="function">MongoCollection::find</span>
example using $where**

This example demonstrates how to search a collection using javascript
code to reduce the resultset.

``` php
<?php

$m = new MongoClient();
$db = $m->selectDB('test');
$collection = new MongoCollection($db, 'phpmanual');

$js = "function() {
    return this.name == 'Joe' || this.age == 50;
}";
$cursor = $collection->find(array('$where' => $js));
foreach ($cursor as $doc) {
    var_dump($doc);
}

?>
```

The above example will output:

    array(3) {
      ["_id"]=>
      object(MongoId)#7 (1) {
        ["$id"]=>
        string(24) "4ebc3e3710b89f2349000002"
      }
      ["name"]=>
      string(3) "Joe"
      ["age"]=>
      int(20)
    }

**Example \#4 <span class="function">MongoCollection::find</span>
example using $in**

This example demonstrates how to search a collection using the $in
operator.

``` php
<?php

$m = new MongoClient();
$db = $m->selectDB('test');
$collection = new MongoCollection($db, 'phpmanual');

$cursor = $collection->find(array(
    'name' => array('$in' => array('Joe', 'Wendy'))
));

?>
```

The above example will output:

    array(3) {
      ["_id"]=>
      object(MongoId)#7 (1) {
        ["$id"]=>
        string(24) "4ebc3e3710b89f2349000002"
      }
      ["name"]=>
      string(3) "Joe"
      ["age"]=>
      int(20)
    }

**Example \#5 Getting results as an array**

This returns a <span class="classname">MongoCursor</span>. Often, when
people are starting out, they are more comfortable using an array. To
turn a cursor into an array, use the <span
class="function">iterator\_to\_array</span> function.

``` php
<?php

$m = new MongoClient();
$db = $m->selectDB('test');
$collection = new MongoCollection($db, 'phpmanual');

$cursor = $collection->find();
$array = iterator_to_array($cursor);

?>
```

The above example will output:

    array(3) {
      ["4ebc40af10b89f5149000000"]=>
      array(2) {
        ["_id"]=>
        object(MongoId)#6 (1) {
          ["$id"]=>
          string(24) "4ebc40af10b89f5149000000"
        }
        ["x"]=>
        int(12)
      }
      ["4ebc40af10b89f5149000001"]=>
      array(2) {
        ["_id"]=>
        object(MongoId)#11 (1) {
          ["$id"]=>
          string(24) "4ebc40af10b89f5149000001"
        }
        ["x"]=>
        int(12)
      }
      ["4ebc40af10b89f5149000002"]=>
      array(3) {
        ["_id"]=>
        object(MongoId)#12 (1) {
          ["$id"]=>
          string(24) "4ebc40af10b89f5149000002"
        }
        ["name"]=>
        string(3) "Joe"
        ["age"]=>
        int(20)
      }
    }

Using <span class="function">iterator\_to\_array</span> forces the
driver to load all of the results into memory, so do not do this for
result sets that are larger than memory!

Also, certain system collections do not have an *\_id* field. If you are
dealing with a collection that might have documents without *\_id*s,
pass **`FALSE`** as the second argument to <span
class="function">iterator\_to\_array</span> (so that it will not try to
use the non-existent *\_id* values as keys).

### See Also

-   <span class="function">MongoCollection::findOne</span>
-   <span class="function">MongoCollection::insert</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/reference/method/db.collection.find/" class="link external">» find</a>.

MongoCollection::findAndModify
==============================

Update a document and return it

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::findAndModify</span> ( <span
class="methodparam"><span class="type">array</span> `$query`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$update`</span> \[, <span class="methodparam"><span
class="type">array</span> `$fields`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\]\] )

The findAndModify command atomically modifies and returns a single
document. By default, the returned document does not include the
modifications made on the update. To return the document with the
modifications made on the update, use the `new` option.

### Parameters

`query`  
The query criteria to search for.

`update`  
The update criteria.

`fields`  
Optionally only return these fields.

`options`  
An array of options to apply, such as remove the match document from the
DB and return it.

| Option                                     | Description                                                                                                                                                                                                                                                               |
|--------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `sort` <span class="type">array</span>     | Determines which document the operation will modify if the query selects multiple documents. findAndModify will modify the first document in the sort order specified by this argument.                                                                                   |
| `remove` <span class="type">boolean</span> | Optional if `update` field exists. When **`TRUE`**, removes the selected document. The default is **`FALSE`**.                                                                                                                                                            |
| `update` <span class="type">array</span>   | Optional if `remove` field exists. Performs an update of the selected document.                                                                                                                                                                                           |
| `new` <span class="type">boolean</span>    | Optional. When **`TRUE`**, returns the modified document rather than the original. The findAndModify method ignores the `new` option for remove operations. The default is **`FALSE`**.                                                                                   |
| `upsert` <span class="type">boolean</span> | Optional. Used in conjunction with the `update` field. When **`TRUE`**, the findAndModify command creates a new document if the query returns no documents. The default is false. In MongoDB 2.2, the findAndModify command returns **`NULL`** when upsert is **`TRUE`**. |
| ``                                         |                                                                                                                                                                                                                                                                           |

### Return Values

Returns the original document, or the modified document when `new` is
set.

### Errors/Exceptions

Throws <span class="classname">MongoResultException</span> on failure.

### Examples

**Example \#1 <span
class="methodname">MongoCollection::findAndModify</span> example**

``` php
<?php
$m = new Mongo;
$col = $m->selectDB("test")->jobs;

$col->insert(array(
     "name" => "Next promo",
     "inprogress" => false,
     "priority" => 0,
     "tasks" => array( "select product", "add inventory", "do placement"),
) );

$col->insert(array(
     "name" => "Biz report",
     "inprogress" => false,
     "priority" => 1,
     "tasks" => array( "run sales report", "email report" )
) );

$col->insert(array(
     "name" => "Biz report",
     "inprogress" => false,
     "priority" => 2,
     "tasks" => array( "run marketing report", "email report" )
    ),
    array("w" => 1)
);



$retval = $col->findAndModify(
     array("inprogress" => false, "name" => "Biz report"),
     array('$set' => array('inprogress' => true, "started" => new MongoDate())),
     null,
     array(
        "sort" => array("priority" => -1),
        "new" => true,
    )
);

var_dump($retval);
?>
```

The above example will output something similar to:

    array(6) {
      ["_id"]=>
      object(MongoId)#7 (1) {
        ["$id"]=>
        string(24) "5091b5b244415e8cc3000002"
      }
      ["inprogress"]=>
      bool(true)
      ["name"]=>
      string(10) "Biz report"
      ["priority"]=>
      int(2)
      ["started"]=>
      object(MongoDate)#8 (2) {
        ["sec"]=>
        int(1351726514)
        ["usec"]=>
        int(925000)
      }
      ["tasks"]=>
      array(2) {
        [0]=>
        string(20) "run marketing report"
        [1]=>
        string(12) "email report"
      }
    }

**Example \#2 <span
class="methodname">MongoCollection::findAndModify</span> error
handling**

``` php
<?php
$m = new Mongo;
$col = $m->selectDB("test")->jobs;
try {
    $retval = $col->findAndModify(
         array("inprogress" => false, "name" => "Next promo"),
         array('$pop' => array("tasks" => -1)),
         array("tasks" => array('$pop' => array("stuff"))),
         array("new" => true)
    );
} catch(MongoResultException $e) {
    echo $e->getCode(), " : ", $e->getMessage(), "\n";
    var_dump($e->getDocument());
}

?>
```

The above example will output something similar to:

    13097 : exception: Unsupported projection option: $pop
    array(3) {
      ["errmsg"]=>
      string(46) "exception: Unsupported projection option: $pop"
      ["code"]=>
      int(13097)
      ["ok"]=>
      float(0)
    }

### See Also

-   The MongoDB
    <a href="https://docs.mongodb.com/manual/reference/command/findAndModify/" class="link external">» findAndModify command</a>
    docs

MongoCollection::findOne
========================

Queries this collection, returning a single element

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::findOne</span> (\[ <span
class="methodparam"><span class="type">array</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$fields`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\]\] )

As opposed to <span class="function">MongoCollection::find</span>, this
method will return only the *first* result from the result set, and not
a <span class="classname">MongoCursor</span> that can be iterated over.

### Parameters

`query`  
The fields for which to search. MongoDB's query language is quite
extensive. The PHP driver will in almost all cases pass the query
straight through to the server, so reading the MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/method/db.collection.find/" class="link external">» find</a>
is a good idea.

**Warning**
Please make sure that for all special query operaters (starting with
*$*) you use single quotes so that PHP doesn't try to replace
*"$exists"* with the value of the variable *$exists*.

`fields`  
Fields of the results to return. The array is in the format
*array('fieldname' =\> true, 'fieldname2' =\> true)*. The *\_id* field
is always returned.

`options`  
This parameter is an associative array of the form *array("name" =\>
\<value\>, ...)*. Currently supported options are:

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

### Return Values

Returns record matching the search or **`NULL`**.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database.

### Changelog

| Version          | Description                        |
|------------------|------------------------------------|
| PECL mongo 1.5.0 | Added optional `options` argument. |

### Examples

**Example \#1 <span class="methodname">MongoCollection::findOne</span>
document by its id.**

This example demonstrates how to find a single document in a collection
by its id.

``` php
<?php

$articles = $mongo->my_db->articles;

$article = $articles->findOne(array('_id' => new MongoId('47cc67093475061e3d9536d2')));

?>
```

**Example \#2 <span class="methodname">MongoCollection::findOne</span>
document by some condition.**

This example demonstrates how to find a single document in a collection
by some condition and limiting the returned fields.

``` php
<?php

$users = $mongo->my_db->users;
$user = $users->findOne(array('username' => 'jwage'), array('password'));
print_r($user);

?>
```

The above example will output something similar to:

    Array
    (
        [_id] => MongoId Object
            (
            )

        [password] => test
    )

Notice how even though the document does have a username field, we
limited the results to only contain the password field.

### See Also

-   <span class="function">MongoCollection::find</span>
-   <span class="function">MongoCollection::insert</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/reference/method/db.collection.find/" class="link external">» find</a>.

MongoCollection::\_\_get
========================

Gets a collection

### Description

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">MongoCollection::\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

A concise syntax for getting a collection with a dot-separated name. If
a collection name contains strange characters, you may have to use <span
class="function">MongoDB::selectCollection</span> instead.

``` php
<?php

$mongo = new MongoClient();

// the following two lines are equivalent
$collection = $mongo->selectDB("foo")->selectCollection("bar.baz");
$collection = $mongo->foo->bar->baz;

?>
```

### Parameters

`name`  
The next string in the collection name.

### Return Values

Returns the collection.

MongoCollection::getDBRef
=========================

Fetches the document pointed to by a database reference

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::getDBRef</span> ( <span
class="methodparam"><span class="type">array</span> `$ref`</span> )

### Parameters

`ref`  
A database reference.

### Return Values

Returns the database document pointed to by the reference.

### Examples

**Example \#1 <span class="methodname">MongoCollection::getDBRef</span>
example**

``` php
<?php

$playlists = $db->playlists;

$myList = $playlists->findOne(array('username' => 'me'));

// fetch each song in the playlist
foreach ($myList['songlist'] as $songRef) {
    $song = $playlists->getDBRef($songRef);
    echo $song['title'] . "\n";
}

?>
```

The above example will output something similar to:

    Dazed and Confused
    Ma na ma na
    Bohemian Rhapsody

  
In the above example each $songRef looks something like the following:  

        Array
        (
            [$ref] => songs
            [$id] => 49902cde5162504500b45c2c
        )
        

### See Also

-   <span class="methodname">MongoCollection::createDBRef</span>

MongoCollection::getIndexInfo
=============================

Returns information about indexes on this collection

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::getIndexInfo</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array in which each element describes an index.
Elements will contain the values *name* for the name of the index, *ns*
for the namespace (a combination of the database and collection name),
and *key* for a list of all fields in the index and their ordering.
Additional values may be present for special indexes, such as *unique*
or *sparse*.

### Examples

**Example \#1 <span
class="function">MongoCollection::getIndexInfo</span> example**

``` php
<?php

$m = new MongoClient();
$c = $m->selectCollection('test', 'venues');
var_dump($c->getIndexInfo());

?>
```

The above example will output something similar to:

    array(4) {
      [0]=>
      array(4) {
        ["v"]=>
        int(1)
        ["key"]=>
        array(1) {
          ["_id"]=>
          int(1)
        }
        ["name"]=>
        string(4) "_id_"
        ["ns"]=>
        string(11) "test.venues"
      }
      [1]=>
      array(4) {
        ["v"]=>
        int(1)
        ["key"]=>
        array(1) {
          ["name"]=>
          float(1)
        }
        ["name"]=>
        string(6) "name_1"
        ["ns"]=>
        string(11) "test.venues"
      }
      [2]=>
      array(4) {
        ["v"]=>
        int(1)
        ["key"]=>
        array(2) {
          ["type"]=>
          float(1)
          ["createdAt"]=>
          float(-1)
        }
        ["name"]=>
        string(19) "type_1_createdAt_-1"
        ["ns"]=>
        string(11) "test.venues"
      }
      [3]=>
      array(5) {
        ["v"]=>
        int(1)
        ["key"]=>
        array(1) {
          ["location"]=>
          string(8) "2dsphere"
        }
        ["name"]=>
        string(17) "location_2dsphere"
        ["ns"]=>
        string(11) "test.venues"
        ["2dsphereIndexVersion"]=>
        int(2)
      }
    }

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/indexes/" class="link external">» vanilla indexes</a>
and
<a href="https://docs.mongodb.com/manual/applications/geospatial-indexes/" class="link external">» geospatial indexes</a>.

MongoCollection::getName
========================

Returns this collection's name

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoCollection::getName</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the name of this collection.

### Examples

**Example \#1 <span class="function">MongoCollection::getName</span>
example**

``` php
<?php

$m = new MongoClient();
$c = $m->foo->bar->baz;

echo "Working with collection " . $c->getName() . ".\n";

// the full namespace is given by the MongoCollection::__toString() method
echo "Working in namespace $c.\n";

?>
```

The above example will output something similar to:

    Working with collection bar.baz.
    Working in namespace foo.bar.baz.

MongoCollection::getReadPreference
==================================

Get the read preference for this collection

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::getReadPreference</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the read preference. The array
contains the values *type* for the string read preference mode
(corresponding to the <span class="classname">MongoClient</span>
constants), and *tagsets* containing a list of all tag set criteria. If
no tag sets were specified, *tagsets* will not be present in the array.

### Changelog

| Version          | Description                                                                                                                                                                                                                                                                                        |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.3.3 | The return value has changed to be consistent with <span class="methodname">MongoCollection::setReadPreference</span>. The *type* value was changed from a number to a string, *type\_string* was removed, and *tagsets* now expresses tags as key/value pairs instead of colon-delimited strings. |

### Examples

**Example \#1 <span
class="methodname">MongoCollection::getReadPreference</span> return
value example**

``` php
<?php

$m = new MongoClient();
$c = $m->test->users;
$c->setReadPreference(MongoClient::RP_SECONDARY, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
    array(),
));
var_dump($c->getReadPreference());
?>
```

The above example will output:

    array(2) {
      ["type"]=>
      string(9) "secondary"
      ["tagsets"]=>
      array(3) {
        [0]=>
        array(2) {
          ["dc"]=>
          string(4) "east"
          ["use"]=>
          string(9) "reporting"
        }
        [1]=>
        array(1) {
          ["dc"]=>
          string(7) "west"
        }
        [2]=>
        array(0) {
        }
      }
    }

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoCollection::setReadPreference</span>

MongoCollection::getSlaveOkay
=============================

Get slaveOkay setting for this collection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCollection::getSlaveOkay</span> ( <span
class="methodparam">void</span> )

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

This function has no parameters.

### Return Values

Returns the value of slaveOkay for this instance.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### See Also

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <span class="methodname">MongoCollection::getReadPreference</span>

MongoCollection::getWriteConcern
================================

Get the write concern for this collection

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::getWriteConcern</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the write concern. The array
contains the values *w* for an integer acknowledgement level or string
mode, and *wtimeout* denoting the maximum number of milliseconds to wait
for the server to satisfy the write concern.

### Examples

**Example \#1 <span
class="methodname">MongoCollection::getWriteConcern</span> return value
example**

``` php
<?php

$mc = new MongoClient('mongodb://localhost:27017', array('wTimeoutMS' => 500));
$coll = $mc->selectCollection('test', 'foo');
var_dump($coll->getWriteConcern());

$coll->setWriteConcern(1, 1000);
var_dump($coll->getWriteConcern());
?>
```

The above example will output:

    array(2) {
      ["w"]=>
      int(1)
      ["wtimeout"]=>
      int(500)
    }
    array(2) {
      ["w"]=>
      int(1)
      ["wtimeout"]=>
      int(1000)
    }

### See Also

-   The
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    documentation.
-   <span class="function">MongoCollection::setWriteConcern</span>

MongoCollection::group
======================

Performs an operation similar to SQL's GROUP BY command

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::group</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> ,
<span class="methodparam"><span class="type">array</span>
`$initial`</span> , <span class="methodparam"><span
class="type">MongoCode</span> `$reduce`</span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

### Parameters

`keys`  
Fields to group by. If an array or non-code object is passed, it will be
the key used to group results.

1.0.4+: If `keys` is an instance of <span
class="classname">MongoCode</span>, `keys` will be treated as a function
that returns the key to group by (see the "Passing a `keys` function"
example below).

`initial`  
Initial value of the aggregation counter object.

`reduce`  
A function that takes two arguments (the current document and the
aggregation to this point) and does the aggregation.

`options`  
Optional parameters to the group command. Valid options include:

-   *"condition"*

    Criteria for including a document in the aggregation.

-   *"finalize"*

    Function called once per unique key that takes the final output of
    the reduce function.

-   *"maxTimeMS"*

    Specifies a cumulative time limit in milliseconds for processing the
    operation on the server (does not include idle time). If the
    operation is not completed by the server within the timeout period,
    a <span class="classname">MongoExecutionTimeoutException</span> will
    be thrown.

### Return Values

Returns an array containing the result.

### Changelog

| Version           | Description                                                                  |
|-------------------|------------------------------------------------------------------------------|
| PECL mongo 1.5.0  | Added *"maxTimeMS"* option.                                                  |
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when `options` is <span class="type">scalar</span>. |

### Examples

**Example \#1 <span class="function">MongoCollection::group</span>
example**

This groups documents by category and creates a list of names within
that category.

``` php
<?php

$collection->insert(array("category" => "fruit", "name" => "apple"));
$collection->insert(array("category" => "fruit", "name" => "peach"));
$collection->insert(array("category" => "fruit", "name" => "banana"));
$collection->insert(array("category" => "veggie", "name" => "corn"));
$collection->insert(array("category" => "veggie", "name" => "broccoli"));

$keys = array("category" => 1);

$initial = array("items" => array());

$reduce = "function (obj, prev) { prev.items.push(obj.name); }";

$g = $collection->group($keys, $initial, $reduce);

echo json_encode($g['retval']);

?>
```

The above example will output something similar to:

    [{"category":"fruit","items":["apple","peach","banana"]},{"category":"veggie","items":["corn","broccoli"]}]

**Example \#2 <span class="function">MongoCollection::group</span>
example**

This example doesn't use any key, so every document will be its own
group. It also uses a condition: only documents that match this
condition will be processed by the grouping function.

``` php
<?php

$collection->save(array("a" => 2));
$collection->save(array("b" => 5));
$collection->save(array("a" => 1));

// use all fields
$keys = array();

// set intial values
$initial = array("count" => 0);

// JavaScript function to perform
$reduce = "function (obj, prev) { prev.count++; }";

// only use documents where the "a" field is greater than 1
$condition = array('condition' => array("a" => array( '$gt' => 1)));

$g = $collection->group($keys, $initial, $reduce, $condition);

var_dump($g);

?>
```

The above example will output something similar to:

    array(4) {
      ["retval"]=>
      array(1) {
        [0]=>
        array(1) {
          ["count"]=>
          float(1)
        }
      }
      ["count"]=>
      float(1)
      ["keys"]=>
      int(1)
      ["ok"]=>
      float(1)
    }

**Example \#3 Passing a `keys` function**

If you want to group by something other than a field name, you can pass
a function as the first parameter of <span
class="function">MongoCollection::group</span> and it will be run
against each document. The return value of the function will be used as
its grouping value.

This example demonstrates grouping by the num field modulo 4.

``` php
<?php

$c->group(new MongoCode('function(doc) { return {mod : doc.num % 4}; }'),
     array("count" => 0),
     new MongoCode('function(current, total) { total.count++; }'));

?>
```

MongoCollection::insert
=======================

Inserts a document into the collection

### Description

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span
class="methodname">MongoCollection::insert</span> ( <span
class="methodparam"><span class="type">array\|object</span>
`$document`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \] )

All strings sent to the database must be UTF-8. If a string is not
UTF-8, a <span class="classname">MongoException</span> will be thrown.
To insert (or query for) a non-UTF-8 string, use <span
class="classname">MongoBinData</span>.

### Parameters

`document`  
An array or object. If an object is used, it may not have protected or
private properties.

> **Note**:
>
> If the parameter does not have an *\_id* key or property, a new <span
> class="classname">MongoId</span> instance will be created and assigned
> to it. This special behavior does not mean that the parameter is
> passed by reference.

`options`  
An array of options for the insert operation. Currently available
options include:

-   *"fsync"*

    Boolean, defaults to **`FALSE`**. If journaling is enabled, it works
    exactly like *"j"*. If journaling is not enabled, the write
    operation blocks until it is synced to database files on disk. If
    **`TRUE`**, an acknowledged insert is implied and this option will
    override setting *"w"* to *0*.

    > **Note**: <span class="simpara">If journaling is enabled, users
    > are strongly encouraged to use the *"j"* option instead of
    > *"fsync"*. Do not use *"fsync"* and *"j"* simultaneously, as that
    > will result in an error.</span>

-   *"j"*

    Boolean, defaults to **`FALSE`**. Forces the write operation to
    block until it is synced to the journal on disk. If **`TRUE`**, an
    acknowledged write is implied and this option will override setting
    *"w"* to *0*.

    > **Note**: <span class="simpara">If this option is used and
    > journaling is disabled, MongoDB 2.6+ will raise an error and the
    > write will fail; older server versions will simply ignore the
    > option.</span>

-   *"socketTimeoutMS"*

    This option specifies the time limit, in milliseconds, for socket
    communication. If the server does not respond within the timeout
    period, a <span class="classname">MongoCursorTimeoutException</span>
    will be thrown and there will be no way to determine if the server
    actually handled the write or not. A value of *-1* may be specified
    to block indefinitely. The default value for <span
    class="classname">MongoClient</span> is *30000* (30 seconds).

-   *"w"*

    See
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concerns</a>.
    The default value for <span class="classname">MongoClient</span> is
    *1*.

-   *"wTimeoutMS"*

    This option specifies the time limit, in milliseconds, for
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    acknowledgement. It is only applicable when *"w"* is greater than
    *1*, as the timeout pertains to replication. If the write concern is
    not satisfied within the time limit, a <span
    class="classname">MongoCursorException</span> will be thrown. A
    value of *0* may be specified to block indefinitely. The default
    value for <span class="classname">MongoClient</span> is *10000* (ten
    seconds).

The following options are deprecated and should no longer be used:

-   *"safe"*

    Deprecated. Please use the
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    *"w"* option.

-   *"timeout"*

    Deprecated alias for *"socketTimeoutMS"*.

-   *"wtimeout"*

    Deprecated alias for *"wTimeoutMS"*.

### Return Values

Returns an array containing the status of the insertion if the *"w"*
option is set. Otherwise, returns **`TRUE`** if the inserted array is
not empty (a <span class="classname">MongoException</span> will be
thrown if the inserted array is empty).

If an array is returned, the following keys may be present:

`ok`  
This should almost always be 1 (unless last\_error itself failed).

`err`  
If this field is non-null, an error occurred on the previous operation.
If this field is set, it will be a string describing the error that
occurred.

`code`  
If a database error occurred, the relevant error code will be passed
back to the client.

`errmsg`  
This field is set if something goes wrong with a database command. It is
coupled with *ok* being 0. For example, if *w* is set and times out,
errmsg will be set to "timed out waiting for slaves" and *ok* will be 0.
If this field is set, it will be a string describing the error that
occurred.

`n`  
If the last operation was an update, upsert, or a remove, the number of
documents affected will be returned. For insert operations, this value
is always *0*.

`wtimeout`  
If the previous option timed out waiting for replication.

`waited`  
How long the operation waited before timing out.

`wtime`  
If *w* was set and the operation succeeded, how long it took to
replicate to *w* servers.

`upserted`  
If an upsert occurred, this field will contain the new record's *\_id*
field. For upserts, either this field or *updatedExisting* will be
present (unless an error occurred).

`updatedExisting`  
If an upsert updated an existing element, this field will be true. For
upserts, either this field or upserted will be present (unless an error
occurred).

### Errors/Exceptions

Throws <span class="classname">MongoException</span> if the inserted
document is empty or if it contains zero-length keys. Attempting to
insert an object with protected and private properties will cause a
zero-length key error.

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.5.0</td>
<td><p>Added the <em>"wTimeoutMS"</em> option, which replaces <em>"wtimeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"wtimeout"</em> is used.</p>
<p>Added the <em>"socketTimeoutMS"</em> option, which replaces <em>"timeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"timeout"</em> is used.</p>
<p>Emits <strong><code>E_DEPRECATED</code></strong> when <em>"safe"</em> is used.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.3.4</td>
<td>Added <em>"wtimeout"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.3.0</td>
<td><p>Added <em>"w"</em> option.</p>
<p>The <code class="parameter">options</code> parameter no longer accepts a boolean to signify an acknowledged write. Instead, this now has to be done with <em>array('w' =&gt; 1)</em> (the default behaviour of <span class="classname">MongoClient</span>).</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.2.0</td>
<td>Added <em>"timeout"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.11</td>
<td>Disconnects on "not master" errors if <em>"safe"</em> is set.</td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.9</td>
<td><p>Added ability to pass integers to the <em>"safe"</em> option, which previously only accepted booleans.</p>
<p>Added <em>"fsync"</em> option.</p>
<p>The return type was changed to be an array containing error information if the <em>"safe"</em> option is used. Otherwise, a boolean is returned as before.</p></td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.2</td>
<td>Changed second parameter to be an array of options. Pre-1.0.2, the second parameter was a boolean indicating the <em>"safe"</em> option.</td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.1</td>
<td>Throw a <span class="classname">MongoCursorException</span> if the <em>"safe"</em> option is set and the insert fails.</td>
</tr>
</tbody>
</table>

### Examples

**Example \#1 <span class="function">MongoCollection::insert</span>
*\_id* example**

An *\_id* field will be added to the inserted document if not already
present. Depending on how the parameter is passed, a generated *\_id*
may or may not be available to calling code.

``` php
<?php

$m = new MongoClient();
$collection = $m->selectCollection('test', 'phpmanual');

// If an array literal is used, there is no way to access the generated _id
$collection->insert(array('x' => 1));

// The _id is available on an array passed by value
$a = array('x' => 2);
$collection->insert($a);
var_dump($a);

// The _id is not available on an array passed by reference
$b = array('x' => 3);
$ref = &$b;
$collection->insert($ref);
var_dump($ref);

// The _id is available if a wrapping function does not trigger copy-on-write
function insert_no_cow($collection, $document)
{
    $collection->insert($document);
}

$c = array('x' => 4);
insert_no_cow($collection, $c);
var_dump($c);

// The _id is not available if a wrapping function triggers copy-on-write
function insert_cow($collection, $document)
{
    $document['y'] = 1;
    $collection->insert($document);
}

$d = array('x' => 5);
insert_cow($collection, $d);
var_dump($d);

?>
```

The above example will output something similar to:

    array(2) {
      ["x"]=>
      int(2)
      ["_id"]=>
      object(MongoId)#4 (0) {
      }
    }
    array(1) {
      ["x"]=>
      int(3)
    }
    array(2) {
      ["x"]=>
      int(4)
      ["_id"]=>
      object(MongoId)#5 (0) {
      }
    }
    array(1) {
      ["x"]=>
      int(5)
    }

**Example \#2 <span class="function">MongoCollection::insert</span>
acknowledged write example**

This example shows inserting two elements with the same \_id, which
causes a <span class="classname">MongoCursorException</span> to be
thrown, as `w` was set.

``` php
<?php

$person = array("name" => "Joe", "age" => 20);
$collection->insert($person);

// now $person has an _id field, so if we save it 
// again, we will get an exception
try {
    $collection->insert($person, array("w" => 1));
} catch(MongoCursorException $e) {
    echo "Can't save the same person twice!\n";
}

?>
```

### See Also

-   <span class="function">MongoCollection::batchInsert</span>
-   <span class="function">MongoCollection::update</span>
-   <span class="function">MongoCollection::find</span>
-   <span class="function">MongoCollection::remove</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/tutorial/insert-documents/" class="link external">» insert</a>.

MongoCollection::parallelCollectionScan
=======================================

Returns an array of cursors to iterator over a full collection in
parallel

### Description

<span class="modifier">public</span> <span
class="type">array\[MongoCommandCursor\]</span> <span
class="methodname">MongoCollection::parallelCollectionScan</span> (
<span class="methodparam"><span class="type">int</span>
`$num_cursors`</span> )

This method returns an array of a maximum of *num\_cursors* cursors. An
iteration over one of the returned cursors results in a partial set of
documents for a collection. Iteration over all the returned cursors
results in getting every document back from the collection.

This method is a wrapper for the *parallelCollectionScan* MongoDB
command.

### Parameters

`num_cursors`  
The number of cursors to request from the server. Please note, that the
server can return less cursors than you requested.

### Return Values

Returns an array of <span class="classname">MongoCommandCursor</span>
objects.

### Examples

**Example \#1 <span
class="function">MongoCollection::parallelCollectionScan</span>
example**

Returning all documents in a collection by using multiple cursors.

``` php
<?php
$m = new MongoClient;
$c = $m->demo->cities;

/* Request three cursors */
$cursors = $c->parallelCollectionScan( 3 );

/* Add all the cursors to the MultipleIterator */
$mi = new MultipleIterator( MultipleIterator::MIT_NEED_ANY );
foreach ( $cursors as $cursor )
{
    $mi->attachIterator( $cursor );
}

/* Iterate over all the associated cursors */
foreach ( $mi as $items )
{
    foreach ( $items as $item )
    {
        if ( $item !== NULL )
        {
            echo $item['name'], "\n";
        }
    }
}
?>
```

### See Also

-   <span class="classname">MultipleIterator</span>
-   <span class="classname">MongoCommandCursor</span>
-   <span class="methodname">MongoDB::command</span>

MongoCollection::remove
=======================

Remove records from this collection

### Description

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span
class="methodname">MongoCollection::remove</span> (\[ <span
class="methodparam"><span class="type">array</span> `$criteria`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

### Parameters

`criteria`  
Query criteria for the documents to delete.

`options`  
An array of options for the remove operation. Currently available
options include:

-   *"w"*

    See
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concerns</a>.
    The default value for <span class="classname">MongoClient</span> is
    *1*.

-   *"justOne"*

    Specify **`TRUE`** to limit deletion to just one document. If
    **`FALSE`** or omitted, all documents matching the criteria will be
    deleted.

-   *"fsync"*

    Boolean, defaults to **`FALSE`**. If journaling is enabled, it works
    exactly like *"j"*. If journaling is not enabled, the write
    operation blocks until it is synced to database files on disk. If
    **`TRUE`**, an acknowledged insert is implied and this option will
    override setting *"w"* to *0*.

    > **Note**: <span class="simpara">If journaling is enabled, users
    > are strongly encouraged to use the *"j"* option instead of
    > *"fsync"*. Do not use *"fsync"* and *"j"* simultaneously, as that
    > will result in an error.</span>

-   *"j"*

    Boolean, defaults to **`FALSE`**. Forces the write operation to
    block until it is synced to the journal on disk. If **`TRUE`**, an
    acknowledged write is implied and this option will override setting
    *"w"* to *0*.

    > **Note**: <span class="simpara">If this option is used and
    > journaling is disabled, MongoDB 2.6+ will raise an error and the
    > write will fail; older server versions will simply ignore the
    > option.</span>

-   *"socketTimeoutMS"*

    This option specifies the time limit, in milliseconds, for socket
    communication. If the server does not respond within the timeout
    period, a <span class="classname">MongoCursorTimeoutException</span>
    will be thrown and there will be no way to determine if the server
    actually handled the write or not. A value of *-1* may be specified
    to block indefinitely. The default value for <span
    class="classname">MongoClient</span> is *30000* (30 seconds).

-   *"w"*

    See
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concerns</a>.
    The default value for <span class="classname">MongoClient</span> is
    *1*.

-   *"wTimeoutMS"*

    This option specifies the time limit, in milliseconds, for
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    acknowledgement. It is only applicable when *"w"* is greater than
    *1*, as the timeout pertains to replication. If the write concern is
    not satisfied within the time limit, a <span
    class="classname">MongoCursorException</span> will be thrown. A
    value of *0* may be specified to block indefinitely. The default
    value for <span class="classname">MongoClient</span> is *10000* (ten
    seconds).

The following options are deprecated and should no longer be used:

-   *"safe"*

    Deprecated. Please use the
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    *"w"* option.

-   *"timeout"*

    Deprecated alias for *"socketTimeoutMS"*.

-   *"wtimeout"*

    Deprecated alias for *"wTimeoutMS"*.

### Return Values

Returns an array containing the status of the removal if the *"w"*
option is set. Otherwise, returns **`TRUE`**.

Fields in the status array are described in the documentation for <span
class="function">MongoCollection::insert</span>.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.5.0</td>
<td><p>Added <em>"wTimeoutMS"</em> option, which replaces <em>"wtimeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"wtimeout"</em> is used.</p>
<p>Added <em>"socketTimeoutMS"</em> option, which replaces <em>"timeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"timeout"</em> is used.</p>
<p>Emits <strong><code>E_DEPRECATED</code></strong> when <em>"safe"</em> is used.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.3.4</td>
<td>Added <em>"wtimeout"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.3.0</td>
<td><p>Added <em>"w"</em> option.</p>
<p>The <code class="parameter">options</code> parameter no longer accepts a boolean to signify <em>"justOne"</em>. Instead, this now has to be done with <em>array('justOne' =&gt; true)</em>.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.2.11</td>
<td>Emits <strong><code>E_DEPRECATED</code></strong> when <code class="parameter">options</code> is <span class="type">scalar</span>.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.2.0</td>
<td>Added <em>"timeout"</em> option.</td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.11</td>
<td>Disconnects on "not master" errors if <em>"safe"</em> is set.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.9</td>
<td><p>Added ability to pass integers to the <em>"safe"</em> option, which previously only accepted booleans.</p>
<p>Added <em>"fsync"</em> option.</p>
<p>The return type was changed to be an array containing error information if the <em>"safe"</em> option is used. Otherwise, a boolean is returned as before.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.5</td>
<td>Changed second parameter to be an array of options. Pre-1.0.5, the second parameter was a boolean indicating the <em>"safe"</em> option.</td>
</tr>
</tbody>
</table>

### Examples

**Example \#1 <span class="function">MongoCollection::remove</span> with
justOne example**

``` php
<?php

$radioactive = $db->radioactive;

// count how much more plutonium there is
$remaining = $radioactive->count(array('type' => 94));

$halflife = $remaining/2;

// remove half of it
while ($halflife > 0) {
    $radioactive->remove(array('type' => 94), array("justOne" => true));
    $halflife--;
}

?>
```

### See Also

-   <span class="function">MongoCollection::insert</span>
-   <span class="function">MongoCollection::update</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/tutorial/remove-documents/" class="link external">» remove</a>.

MongoCollection::save
=====================

Saves a document to this collection

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">MongoCollection::save</span> ( <span
class="methodparam"><span class="type">array\|object</span>
`$document`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \] )

If the object is from the database, update the existing database object,
otherwise insert this object.

### Parameters

`document`  
Array or object to save. If an object is used, it may not have protected
or private properties.

> **Note**:
>
> If the parameter does not have an *\_id* key or property, a new <span
> class="classname">MongoId</span> instance will be created and assigned
> to it. See <span class="function">MongoCollection::insert</span> for
> additional information on this behavior.

`options`  
Options for the save.

-   *"fsync"*

    Boolean, defaults to **`FALSE`**. If journaling is enabled, it works
    exactly like *"j"*. If journaling is not enabled, the write
    operation blocks until it is synced to database files on disk. If
    **`TRUE`**, an acknowledged insert is implied and this option will
    override setting *"w"* to *0*.

    > **Note**: <span class="simpara">If journaling is enabled, users
    > are strongly encouraged to use the *"j"* option instead of
    > *"fsync"*. Do not use *"fsync"* and *"j"* simultaneously, as that
    > will result in an error.</span>

-   *"j"*

    Boolean, defaults to **`FALSE`**. Forces the write operation to
    block until it is synced to the journal on disk. If **`TRUE`**, an
    acknowledged write is implied and this option will override setting
    *"w"* to *0*.

    > **Note**: <span class="simpara">If this option is used and
    > journaling is disabled, MongoDB 2.6+ will raise an error and the
    > write will fail; older server versions will simply ignore the
    > option.</span>

-   *"socketTimeoutMS"*

    This option specifies the time limit, in milliseconds, for socket
    communication. If the server does not respond within the timeout
    period, a <span class="classname">MongoCursorTimeoutException</span>
    will be thrown and there will be no way to determine if the server
    actually handled the write or not. A value of *-1* may be specified
    to block indefinitely. The default value for <span
    class="classname">MongoClient</span> is *30000* (30 seconds).

-   *"w"*

    See
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concerns</a>.
    The default value for <span class="classname">MongoClient</span> is
    *1*.

-   *"wtimeout"*

    Deprecated alias for *"wTimeoutMS"*.

-   *"wTimeoutMS"*

    This option specifies the time limit, in milliseconds, for
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    acknowledgement. It is only applicable when *"w"* is greater than
    *1*, as the timeout pertains to replication. If the write concern is
    not satisfied within the time limit, a <span
    class="classname">MongoCursorException</span> will be thrown. A
    value of *0* may be specified to block indefinitely. The default
    value for <span class="classname">MongoClient</span> is *10000* (ten
    seconds).

-   *"safe"*

    Deprecated. Please use the
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    *"w"* option.

-   *"timeout"*

    Deprecated alias for *"socketTimeoutMS"*.

### Return Values

If `w` was set, returns an array containing the status of the save.
Otherwise, returns a boolean representing if the array was not empty (an
empty array will not be inserted).

### Errors/Exceptions

Throws <span class="classname">MongoException</span> if the inserted
document is empty or if it contains zero-length keys. Attempting to
insert an object with protected and private properties will cause a
zero-length key error.

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.5.0</td>
<td><p>Added <em>"wTimeoutMS"</em> option, which replaces <em>"wtimeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"wtimeout"</em> is used.</p>
<p>Added <em>"socketTimeoutMS"</em> option, which replaces <em>"timeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"timeout"</em> is used.</p>
<p>Emits <strong><code>E_DEPRECATED</code></strong> when <em>"safe"</em> is used.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.2.0</td>
<td>Added <em>"timeout"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.11</td>
<td>Disconnects on "not master" errors if <em>"safe"</em> is set.</td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.9</td>
<td><p>Added <em>"fsync"</em> option.</p></td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.5</td>
<td>Added <code class="parameter">options</code> parameter.</td>
</tr>
</tbody>
</table>

### Examples

**Example \#1 <span class="function">MongoCollection::save</span>
example**

``` php
<?php

$obj = array('x' => 1);

// insert $obj into the db
$collection->save($obj);
var_dump($obj);

// add another field
$obj['foo'] = 'bar';

// $obj cannot be inserted again, causes duplicate _id error
$collection->insert($obj);

// save updates $obj with the new field
$collection->save($obj);

?>
```

The above example will output something similar to:

    array(2) {
      ["x"]=>
      int(1)
      ["_id"]=>
      object(MongoId)#4 (1) {
        ["$id"]=>
        string(24) "50b6afe544415ed606000000"
      }
    }

MongoCollection::setReadPreference
==================================

Set the read preference for this collection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCollection::setReadPreference</span> (
<span class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

### Parameters

`read_preference`  
The read preference mode: **`MongoClient::RP_PRIMARY`**,
**`MongoClient::RP_PRIMARY_PREFERRED`**,
**`MongoClient::RP_SECONDARY`**,
**`MongoClient::RP_SECONDARY_PREFERRED`**, or
**`MongoClient::RP_NEAREST`**.

`tags`  
An array of zero or more tag sets, where each tag set is itself an array
of criteria used to match tags on replica set members.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Errors/Exceptions

Emits **`E_WARNING`** if either parameter is invalid, or if one or more
tag sets are provided with the **`MongoClient::RP_PRIMARY`** read
preference mode.

### Examples

**Example \#1 <span
class="methodname">MongoCollection::setReadPreference</span> tag set
array syntax example**

``` php
<?php

$m = new MongoClient();
$c = $m->test->users;

// Prefer the nearest server in the "east" data center also used for reporting,
// but fall back to a server in the "west" data center
$c->setReadPreference(MongoClient::RP_NEAREST, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
));
?>
```

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoCollection::getReadPreference</span>

MongoCollection::setSlaveOkay
=============================

Change slaveOkay setting for this collection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCollection::setSlaveOkay</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$ok`<span
class="initializer"> = **`TRUE`**</span></span> \] )

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

`ok`  
If reads should be sent to secondary members of a replica set for all
possible queries using this <span
class="classname">MongoCollection</span> instance.

### Return Values

Returns the former value of slaveOkay for this instance.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### See Also

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <span class="methodname">MongoCollection::setReadPreference</span>

MongoCollection::setWriteConcern
================================

Set the write concern for this database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCollection::setWriteConcern</span> ( <span
class="methodparam"><span class="type">mixed</span> `$w`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$wtimeout`</span> \] )

### Parameters

`w`  
The write concern. This may be an integer denoting the number of servers
required to acknowledge the write, or a string mode (e.g. "majority").

`wtimeout`  
The maximum number of milliseconds to wait for the server to satisfy the
write concern.

### Return Values

Returns **`TRUE`** on success, or **`FALSE`** otherwise.

### Errors/Exceptions

Emits **`E_WARNING`** if the *w* parameter is not an integer or string
value.

### Examples

**Example \#1 <span class="methodname">MongoDB::setWriteConcern</span>
example**

``` php
<?php

$mc = new MongoClient('mongodb://rs1.example.com,rs2.example.com');
$coll = $mc->selectCollection('test', 'foo');

// Require that the majority of servers in the replica set acknowledge writes
// within three seconds.
$coll->setWriteConcern('majority', 3000);
?>
```

### See Also

-   The
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    documentation.
-   <span class="function">MongoCollection::getWriteConcern</span>

MongoCollection::toIndexString
==============================

Converts keys specifying an index to its identifying string

### Description

<span class="modifier">static protected</span> <span
class="type">string</span> <span
class="methodname">MongoCollection::toIndexString</span> ( <span
class="methodparam"><span class="type">mixed</span> `$keys`</span> )

**Warning**

This method is deprecated since version 1.5.0.

### Parameters

`keys`  
Field or fields to convert to the identifying string

### Return Values

Returns a string that describes the index.

### Examples

**Example \#1 <span
class="function">MongoCollection::toIndexString</span> example**

This example shows how you can create an index name out of keys. Because
this is a protected (static) method, you need to overload it in a child
class first.

``` php
<?php
// Create inherited class to make the method "public".
class MyCollection extends MongoCollection
{
    static public function toIndexString($a)
    {
        return parent::toIndexString($a);
    }
}

echo MyCollection::toIndexString("foo"), "\n";
// Outputs: foo_1

echo MyCollection::toIndexString(array('name' => 1, 'age' => -1)), "\n";
// Outputs: name_1_age_-1
?>
```

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/indexes/" class="link external">» indexes</a>.

### Changelog

| Version          | Description                      |
|------------------|----------------------------------|
| PECL mongo 1.5.0 | This method has been deprecated. |

MongoCollection::\_\_toString
=============================

String representation of this collection

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoCollection::\_\_toString</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the full name of this collection.

### Examples

**Example \#1 <span
class="function">MongoCollection::\_\_toString</span> example**

``` php
<?php

$m = new MongoClient();

$c1 = $m->foo->bar->baz;
echo "Working with collection $c1.";

$c2 = $m->selectCollection('[]', '&');
echo "Working with collection $c2.";

?>
```

The above example will output something similar to:

    Working with collection foo.bar.baz.
    Working with collection [].&.

MongoCollection::update
=======================

Update records based on a given criteria

### Description

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span
class="methodname">MongoCollection::update</span> ( <span
class="methodparam"><span class="type">array</span> `$criteria`</span> ,
<span class="methodparam"><span class="type">array</span>
`$new_object`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \] )

### Parameters

`criteria`  
Query criteria for the documents to update.

`new_object`  
The object used to update the matched documents. This may either contain
update operators (for modifying specific fields) or be a replacement
document.

`options`  
An array of options for the update operation. Currently available
options include:

-   *"upsert"*

    If no document matches `$criteria`, a new document will be inserted.

    If a new document would be inserted and `$new_object` contains
    atomic modifiers (i.e. *$* operators), those operations will be
    applied to the `$criteria` parameter to create the new document. If
    `$new_object` does not contain atomic modifiers, it will be used
    as-is for the inserted document. See the upsert examples below for
    more information.

-   *"multiple"*

    All documents matching $criteria will be updated. <span
    class="function">MongoCollection::update</span> has exactly the
    opposite behavior of <span
    class="function">MongoCollection::remove</span>: it updates one
    document by default, not all matching documents. *It is recommended
    that you always specify whether you want to update multiple
    documents or a single document*, as the database may change its
    default behavior at some point in the future.

-   *"fsync"*

    Boolean, defaults to **`FALSE`**. If journaling is enabled, it works
    exactly like *"j"*. If journaling is not enabled, the write
    operation blocks until it is synced to database files on disk. If
    **`TRUE`**, an acknowledged insert is implied and this option will
    override setting *"w"* to *0*.

    > **Note**: <span class="simpara">If journaling is enabled, users
    > are strongly encouraged to use the *"j"* option instead of
    > *"fsync"*. Do not use *"fsync"* and *"j"* simultaneously, as that
    > will result in an error.</span>

-   *"j"*

    Boolean, defaults to **`FALSE`**. Forces the write operation to
    block until it is synced to the journal on disk. If **`TRUE`**, an
    acknowledged write is implied and this option will override setting
    *"w"* to *0*.

    > **Note**: <span class="simpara">If this option is used and
    > journaling is disabled, MongoDB 2.6+ will raise an error and the
    > write will fail; older server versions will simply ignore the
    > option.</span>

-   *"socketTimeoutMS"*

    This option specifies the time limit, in milliseconds, for socket
    communication. If the server does not respond within the timeout
    period, a <span class="classname">MongoCursorTimeoutException</span>
    will be thrown and there will be no way to determine if the server
    actually handled the write or not. A value of *-1* may be specified
    to block indefinitely. The default value for <span
    class="classname">MongoClient</span> is *30000* (30 seconds).

-   *"w"*

    See
    <a href="/book/mongo.html#Write%20Concerns" class="link">Write Concerns</a>.
    The default value for <span class="classname">MongoClient</span> is
    *1*.

-   *"wTimeoutMS"*

    This option specifies the time limit, in milliseconds, for
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    acknowledgement. It is only applicable when *"w"* is greater than
    *1*, as the timeout pertains to replication. If the write concern is
    not satisfied within the time limit, a <span
    class="classname">MongoCursorException</span> will be thrown. A
    value of *0* may be specified to block indefinitely. The default
    value for <span class="classname">MongoClient</span> is *10000* (ten
    seconds).

The following options are deprecated and should no longer be used:

-   *"safe"*

    Deprecated. Please use the
    <a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
    *"w"* option.

-   *"timeout"*

    Deprecated alias for *"socketTimeoutMS"*.

-   *"wtimeout"*

    Deprecated alias for *"wTimeoutMS"*.

### Return Values

Returns an array containing the status of the update if the *"w"* option
is set. Otherwise, returns **`TRUE`**.

Fields in the status array are described in the documentation for <span
class="function">MongoCollection::insert</span>.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

### Changelog

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Version</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>PECL mongo 1.5.0</td>
<td><p>Added the <em>"wTimeoutMS"</em> option, which replaces <em>"wtimeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"wtimeout"</em> is used.</p>
<p>Added the <em>"socketTimeoutMS"</em> option, which replaces <em>"timeout"</em>. Emits <strong><code>E_DEPRECATED</code></strong> when <em>"timeout"</em> is used.</p>
<p>Emits <strong><code>E_DEPRECATED</code></strong> when <em>"safe"</em> is used.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.3.4</td>
<td>Added <em>"wtimeout"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.3.0</td>
<td><p>Added <em>"w"</em> option.</p>
<p>The <code class="parameter">options</code> parameter no longer accepts a boolean to signify an upsert. Instead, this now has to be done with <em>array('upsert' =&gt; true)</em>.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.2.11</td>
<td>Emits <strong><code>E_DEPRECATED</code></strong> when <code class="parameter">options</code> is <span class="type">scalar</span>.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.2.0</td>
<td>Added <em>"timeout"</em> option.</td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.11</td>
<td>Disconnects on "not master" errors if <em>"safe"</em> is set.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.9</td>
<td><p>Added ability to pass integers to the <em>"safe"</em> option, which previously only accepted booleans.</p>
<p>Added <em>"fsync"</em> option.</p>
<p>The return type was changed to be an array containing error information if the <em>"safe"</em> option is used. Otherwise, a boolean is returned as before.</p></td>
</tr>
<tr class="even">
<td>PECL mongo 1.0.5</td>
<td>Added <em>"safe"</em> option.</td>
</tr>
<tr class="odd">
<td>PECL mongo 1.0.1</td>
<td>Changed <code class="parameter">options</code> parameter from boolean to array. Pre-1.0.1, the second parameter was an optional boolean value specifying an upsert.</td>
</tr>
</tbody>
</table>

### Examples

**Example \#1 <span class="function">MongoCollection::update</span>**

Adding an address field to a document.

``` php
<?php

$c->insert(array("firstname" => "Bob", "lastname" => "Jones" ));
$newdata = array('$set' => array("address" => "1 Smith Lane"));
$c->update(array("firstname" => "Bob"), $newdata);

var_dump($c->findOne(array("firstname" => "Bob")));

?>
```

The above example will output something similar to:

    array(4) {
      ["_id"]=>
      object(MongoId)#6 (0) {
      }
      ["firstname"]=>
      string(3) "Bob"
      ["lastname"]=>
      string(5) "Jones"
      ["address"]=>
      string(12) "1 Smith Lane"
    }

**Example \#2 <span class="function">MongoCollection::update</span>
upsert examples**

Upserts can simplify code, as a single line can create the document if
it does not exist (based on `$criteria`), or update an existing document
if it matches.

In the following example, `$new_object` contains an atomic modifier.
Since the collection is empty and upsert must insert a new document, it
will apply those operations to the `$criteria` parameter in order to
create the document.

``` php
<?php

$c->drop();
$c->update(
    array("uri" => "/summer_pics"),
    array('$inc' => array("page hits" => 1)),
    array("upsert" => true)
);
var_dump($c->findOne());

?>
```

The above example will output something similar to:

    array(3) {
      ["_id"]=>
      object(MongoId)#9 (0) {
      }
      ["uri"]=>
      string(12) "/summer_pics"
      ["page hits"]=>
      int(1)
    }

If `$new_object` does not contain atomic modifiers (i.e. *$* operators),
upsert will use `$new_object` as-is for the new document. This matches
the behavior of a normal update, where not using atomic modifiers causes
the document to be overwritten.

``` php
<?php

$c->drop();
$c->update(
    array("name" => "joe"),
    array("username" => "joe312", "createdAt" => new MongoDate()), 
    array("upsert" => true)
);
var_dump($c->findOne());

?>
```

The above example will output something similar to:

    array(3) {
      ["_id"]=>
      object(MongoId)#10 (0) {
      }
      ["username"]=>
      string(6) "joe312"
      ["createdAt"]=>
      object(MongoDate)#4 (0) {
      }
    }

**Example \#3 <span class="function">MongoCollection::update</span>
multiple example**

By default, <span class="function">MongoCollection::update</span> will
only update the first document matching `$criteria` that it finds. Using
the "multiple" option can override this behavior, if needed.

This example adds a "gift" field to every person whose birthday is in
the next day.

``` php
<?php

$today = array('$gt' => new MongoDate(), '$lt' => new MongoDate(strtotime("+1 day")));
$people->update(
    array("birthday" => $today),
    array('$set' => array('gift' => $surprise)),
    array("multiple" => true)
);

?>
```

### See Also

The
<a href="/book/mongo.html#Updates" class="link">PHP documentation on updates</a>
and the
<a href="https://docs.mongodb.com/manual/tutorial/modify-documents/" class="link external">» MongoDB core docs</a>.

MongoCollection::validate
=========================

Validates this collection

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCollection::validate</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$scan_data`<span
class="initializer"> = **`FALSE`**</span></span> \] )

### Parameters

`scan_data`  
Only validate indices, not the base collection.

### Return Values

Returns the database's evaluation of this object.

Introduction
------------

A cursor is used to iterate through the results of a database query. For
example, to query the database and see all results, you could do:

**Example \#1 <span class="classname">MongoCursor</span> basic usage**

``` php
<?php

$cursor = $collection->find();
var_dump(iterator_to_array($cursor));

?>
```

You don't generally create cursors using the <span
class="classname">MongoCursor</span> constructor, you get a new cursor
by calling <span class="function">MongoCollection::find</span> (as shown
above).

Suppose that, in the example above, *$collection* was a 50GB collection.
We certainly wouldn't want to load that into memory all at once, which
is what a cursor is for: allowing the client to access the collection in
dribs and drabs.

If we have a large result set, we can iterate through it, loading a few
megabytes of results into memory at a time. For example, we could do:

**Example \#2 Iterating over <span
class="classname">MongoCursor</span>**

``` php
<?php

$cursor = $collection->find();

foreach ($cursor as $doc) {
    // do something to each document
}

?>
```

This will go through each document in the collection, loading and
garbage collecting documents as needed.

Note that this means that a cursor does not "contain" the database
results, it just manages them. Thus, if you print a cursor (with, say,
<span class="function">var\_dump</span> or <span
class="function">print\_r</span>), you'll just get the cursor object,
not your documents. To get the documents themselves, you can use one of
the methods shown above.

Cursor Stages
-------------

A <span class="classname">MongoCursor</span> has two "life stages": pre-
and post- query. When a cursor is created, it has not yet contacted the
database, so it is in its pre-query state. In this state, the client can
further specify what they want the query to do, including adding limits,
skips, sorts, and more advanced options.

When the client attempts to get a result (by calling <span
class="function">MongoCursor::next</span>, directly or indirectly), the
cursor moves into the post-query stage. At this point, the query has
been executed by the database and cannot be modified anymore.

**Example \#3 Adding options to <span
class="classname">MongoCursor</span>**

``` php
<?php

$cursor = $collection->find()->limit(10);

// database has not yet been queried, so more search options can be added
$cursor = $cursor->sort(array("a" => 1));

var_dump($cursor->getNext());
// now database has been queried and more options cannot be added

// so this will throw an exception:
$cursor->skip(4);
?>
```

Class synopsis
--------------

**MongoCursor**

<span class="ooclass"> class **MongoCursor** </span> <span
class="oointerface">implements <span
class="interfacename">MongoCursorInterface</span> </span> <span
class="oointerface">, <span class="interfacename">Iterator</span>
</span> {

/\* Static Fields \*/

<span class="modifier">static</span> <span class="type">boolean</span>
`$slaveOkay` <span class="initializer"> = **`FALSE`**</span> ;

<span class="modifier">static</span> <span class="type">integer</span>
`$timeout` <span class="initializer"> = 30000</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">addOption</span> ( <span class="methodparam"><span
class="type">string</span> `$key`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">awaitData</span> (\[ <span class="methodparam"><span
class="type">bool</span> `$wait`<span class="initializer"> =
**`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">batchSize</span> ( <span class="methodparam"><span
class="type">int</span> `$batchSize`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoClient</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$ns`</span> \[, <span
class="methodparam"><span class="type">array</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$fields`<span
class="initializer"> = array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">count</span> (\[ <span class="methodparam"><span
class="type">bool</span> `$foundOnly`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">dead</span> ( <span
class="methodparam">void</span> )

<span class="modifier">protected</span> <span class="type">void</span>
<span class="methodname">doQuery</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">explain</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">fields</span> (
<span class="methodparam"><span class="type">array</span> `$f`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getNext</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getReadPreference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasNext</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">hint</span> (
<span class="methodparam"><span class="type">mixed</span>
`$index`</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">immortal</span>
(\[ <span class="methodparam"><span class="type">bool</span>
`$liveForever`<span class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">info</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">string\|int</span> <span class="methodname">key</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">limit</span> (
<span class="methodparam"><span class="type">int</span> `$num`</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">maxTimeMS</span> ( <span class="methodparam"><span
class="type">int</span> `$ms`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">partial</span>
(\[ <span class="methodparam"><span class="type">bool</span>
`$okay`<span class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">reset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">setFlag</span>
( <span class="methodparam"><span class="type">int</span> `$flag`</span>
\[, <span class="methodparam"><span class="type">bool</span> `$set`<span
class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">skip</span> (
<span class="methodparam"><span class="type">int</span> `$num`</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">slaveOkay</span> (\[ <span class="methodparam"><span
class="type">bool</span> `$okay`<span class="initializer"> =
**`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">snapshot</span>
( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">sort</span> (
<span class="methodparam"><span class="type">array</span>
`$fields`</span> )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">tailable</span>
(\[ <span class="methodparam"><span class="type">bool</span>
`$tail`<span class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span class="methodname">timeout</span>
( <span class="methodparam"><span class="type">int</span> `$ms`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

Static Variables
----------------

`slaveOkay`  
If the query should have the "slaveOkay" flag set, which allows reads on
the secondary (secondaries are, by default, just for backup and not
queried). Can be overridden with <span
class="function">MongoCursor::slaveOkay</span>.

This functionality is *deprecated*. Please use
<a href="/book/mongo.html#Read%20Preferences" class="xref"></a> instead.

`timeout`  
Set timeout in milliseconds for all database responses. Use *-1* to wait
forever. Can be overridden with <span
class="function">MongoCursor::timeout</span>. This does not cause the
MongoDB server to cancel the operation; it only instructs the driver to
stop waiting for a response and throw a <span
class="classname">MongoCursorTimeoutException</span> after a set time.

See Also
--------

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/core/cursors/" class="link external">» cursors</a>.

MongoCursor::addOption
======================

Adds a top-level key/value pair to a query

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::addOption</span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

This is an advanced function and should not be used unless you know what
you're doing.

A query can optionally be nested in a "query" field if other options,
such as a sort or hint, are given. For instance, adding a sort causes
the query to become a subfield of a bigger query object, like:

``` php
<?php

$query = array("query" => $query, "orderby" => $sort);

?>
```

This method is for adding a top-level field to a query. It makes the
query a subobject (if it isn't already) and adds the key/value pair of
your chosing to the top level.

**Warning**

It cannot be used to add extra criteria to a query on the fly. For
instance, this *will not* work:

``` php
<?php

// NOT CORRECT
$cursor = $users->find()->addOption("name", "joe")->addOption("age", 20);

?>
```

This *does not* query for a user named "joe" with an age of 20.

### Parameters

`key`  
Fieldname to add.

`value`  
Value to add.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### Examples

**Example \#1 Adding a comment with <span
class="function">MongoCursor::addOption</span> example**

MongoDB supports special options to be send to the server. The shell
uses the *\_addSpecial* option to send a *$comment* to the server. This
comment will show up in the profiling log (for slow queries f.e.). In
the PHP driver, you use the <span
class="function">MongoCursor::addOption</span> method.

``` php
<?php
$m = new MongoClient;
$c = $m->demo->demo;
$cursor = $c->find();
$cursor->addOption('$comment', "This comment will show up in the profiling log");

foreach ($cursor as $document) { /* empty */ }
?>
```

The above example will output something similar to:

    {
        "op" : "query",
        "ns" : "demo.demo",
        "query" : {
            "$query" : {
                 
            },
            "$comment" : "This comment will show up in the profiling log"
        },
        "cursorid" : 168463566447,
        "ntoreturn" : 0,
        "ntoskip" : 0,
        "nscanned" : 101,
        "nscannedObjects" : 101,
        "keyUpdates" : 0,
        "numYield" : 0,
    …

**Example \#2 <span class="function">MongoCursor::addOption</span>
example**

Using <span class="function">MongoCursor::skip</span> to skip over
millions of results can become slow. One way around this is to use
*$min* or *$max* options for the query. These can be handy, but they
require an index on exactly the fields being searched for. This is an
example of how to use *$min* as an alternative to <span
class="function">MongoCursor::skip</span>.

``` php
<?php

// make sure we have an index
$c->ensureIndex(array("ts" => 1));

// you may have to modify this to run in a reasonable amount of time on slow 
// machines (should take about 30 seconds on a good machine)
for ($i = 0; $i < 30000000; $i++) {
    $c->insert(array("ts" => new MongoDate(), "i" => $i));
}

$now = strtotime("now");

// find documents inserted in the last 2 seconds
$cursor = $c->find()->addOption('$min', array("ts" => $now-2));

?>
```

MongoCursor::awaitData
======================

Sets whether this cursor will wait for a while for a tailable cursor to
return more data

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::awaitData</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$wait`<span
class="initializer"> = **`TRUE`**</span></span> \] )

This method is to be used with tailable cursors. If we are at the end of
the data, block for a while rather than returning no data. After a
timeout period, we do return as normal.

### Parameters

`wait`  
If the cursor should wait for more data to become available.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### Examples

**Example \#1 <span class="function">MongoCursor::awaitData</span>
example**

In this example we tail the "oplog" and instead of sleeping during every
iteration, we set the <span
class="function">MongoCursor::awaitData</span> option. <span
class="function">MongoCursor::hasNext</span> will now block until there
is more data available.

``` php
<?php
$m = new MongoClient( 'mongodb://localhost:13000', array( 'replSet' => 'seta' ) );
$c = $m->local->selectCollection( 'oplog.rs' );
$cursor = $c->find( array( 'ns' => 'demo.article', 'op' => 'i' ) );
$cursor->tailable( true );
$cursor->awaitData( true );

while (true) {
    if (!$cursor->hasNext()) {
        // we've read all the results, exit
        if ($cursor->dead()) {
            break;
        }
    } else {
        var_dump( $cursor->getNext() );
    }
}
?>
```

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/tutorial/create-tailable-cursor/" class="link external">» tailable cursors</a>.

-   <span class="function">MongoCursor::tailable</span>

MongoCursor::batchSize
======================

Limits the number of elements returned in one batch

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::batchSize</span> ( <span
class="methodparam"><span class="type">int</span> `$batchSize`</span> )

A cursor typically fetches a batch of result objects and store them
locally. This method sets the batchSize value to configure the amount of
documents retrieved from the server in one round trip. However, it will
never return more documents than fit in the max batch size limit
(usually 4MB).

### Parameters

`batchSize`  
The number of results to return per batch. Each batch requires a
round-trip to the server.

If `batchSize` is *2 or more*, it represents the size of each batch of
objects retrieved. It can be adjusted to optimize performance and limit
data transfer.

If `batchSize` is *1* or negative, it will limit of number returned
documents to the absolute value of batchSize, and the cursor will be
closed. For example if batchSize is *-10*, then the server will return a
maximum of 10 documents and as many as can fit in 4MB, then close the
cursor.

**Warning**
A `batchSize` of *1* is special, and means the same as *-1*, i.e. a
value of *1* makes the cursor only capable of returning *one* document.

Note that this feature is different from <span
class="function">MongoCursor::limit</span> in that documents must fit
within a maximum size, and it removes the need to send a request to
close the cursor server-side. The batch size can be changed even after a
cursor is iterated, in which case the setting will apply on the next
batch retrieval.

This cannot override MongoDB's limit on the amount of data it will
return to the client (i.e., if you set batch size to 1,000,000,000,
MongoDB will still only return 4-16MB of results per batch).

To ensure consistent behavior, the rules of <span
class="function">MongoCursor::batchSize</span> and <span
class="function">MongoCursor::limit</span> behave a little complex but
work "as expected". The rules are: hard limits override soft limits with
preference given to <span class="function">MongoCursor::limit</span>
over <span class="function">MongoCursor::batchSize</span>. After that,
whichever is set and lower than the other will take precedence. See
below. section for some examples.

### Return Values

Returns this cursor.

### Examples

**Example \#1 <span class="function">MongoCursor::batchSize</span> and
combinations with <span class="function">MongoCursor::limit</span>**

``` php
<?php

// one batch, at most 10 items. The -10 makes the server to return 10 items,
// and then remove the cursor.
$cursor->limit(20)->batchSize(-10);

// first batch: at most 10 items
$cursor->limit(10);

// first batch: at most 10 items
$cursor->limit(10)->batchSize(20);

// results are fetched in batches of 10 each, with a maximum of 20 items
// returned (that means two batches of 10).
$cursor->limit(20)->batchSize(10);

// results are fetched in batches of 7 each, with a maximum of 30 items
// returned (that means that the driver requests 4 batches of 7, and one batch
// of 2).
$cursor->limit(30)->batchSize(7)
?>
```

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/method/cursor.batchSize/" class="link external">» batchSize</a>.

-   <span class="function">MongoCursor::limit</span>
-   <span class="methodname">MongoCursorInterface::batchSize</span>

### Changelog

| Version          | Description                                                                                                                               |
|------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.4.5 | Before 1.4.5, this method would throw an <span class="classname">MongoCursorException</span> if the cursor had already started iterating. |

MongoCursor::\_\_construct
==========================

Create a new cursor

### Description

<span class="modifier">public</span> <span
class="methodname">MongoCursor::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoClient</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$ns`</span> \[, <span
class="methodparam"><span class="type">array</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$fields`<span
class="initializer"> = array()</span></span> \]\] )

### Parameters

`connection`  
Database connection.

`ns`  
Full name of database and collection.

`query`  
Database query.

`fields`  
Fields to return.

### Return Values

Returns the new cursor.

MongoCursor::count
==================

Counts the number of results for this query

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoCursor::count</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$foundOnly`<span
class="initializer"> = **`FALSE`**</span></span> \] )

This method does not affect the state of the cursor: if you haven't
queried yet, you can still apply limits, skips, etc. If you have started
iterating through results, it will not move the current position of the
cursor. If you have exhausted the cursor, it will not reset it.

### Parameters

`foundOnly`  
Send cursor limit and skip information to the count function, if
applicable.

### Return Values

The number of documents returned by this cursor's query.

### Examples

**Example \#1 <span class="function">MongoCursor::count</span> example**

``` php
<?php

$collection->insert(array('x'=>1));
$collection->insert(array('x'=>2));
$collection->insert(array('x'=>3));

$cursor = $collection->find();

var_dump($cursor->count());
var_dump($cursor->count(true));

$cursor->limit(2);

var_dump($cursor->count());
var_dump($cursor->count(true));

?>
```

The above example will output something similar to:

    int(3)
    int(3)
    int(3)
    int(2)

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database.

MongoCursor::current
====================

Returns the current element

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCursor::current</span> ( <span
class="methodparam">void</span> )

This returns **`NULL`** until <span
class="function">MongoCursor::next</span> is called.

### Parameters

This function has no parameters.

### Return Values

The current result document as an associative array. **`NULL`** will be
returned if there is no result.

### See Also

-   <span class="methodname">Iterator::current</span>

MongoCursor::dead
=================

Checks if there are results that have not yet been sent from the
database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCursor::dead</span> ( <span
class="methodparam">void</span> )

The database sends responses in batches of documents, up to 4MB of
documents per response. This method checks if the database has more
batches or if the result set has been exhausted.

A cursor being "dead" does not mean that <span
class="function">MongoCursor::hasNext</span> will return **`FALSE`**, it
only means that the database is done sending results to the client. The
client should continue iterating through results until <span
class="function">MongoCursor::hasNext</span> is **`FALSE`**.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if there are more results that have not yet been sent
to the client, and **`FALSE`** otherwise.

### See Also

-   <span class="methodname">MongoCursorInterface::dead</span>

MongoCursor::doQuery
====================

Execute the query

### Description

<span class="modifier">protected</span> <span class="type">void</span>
<span class="methodname">MongoCursor::doQuery</span> ( <span
class="methodparam">void</span> )

**Warning**

Please do not use me.

This function actually queries the database. All queries and commands go
through this function. Thus, this function can be overridden to provide
custom query handling.

This handles serializing your query, sending it to the database,
receiving a response, and deserializing it. Thus, if you are planning to
override this, your code should probably call out to the original to use
the existing functionality (see the example below).

### Parameters

This function has no parameters.

### Return Values

**`NULL`**.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### Examples

**Example \#1 <span class="function">MongoCursor::doQuery</span>
example**

You could override this function to attempt a query on a secondary and,
if that fails, try it again on the primary.

``` php
<?php

class MyCursor extends MongoCursor {

    protected function doQuery() {

        $this->slaveOkay();

        try {
            MongoCursor::doQuery();
        }
        catch(MongoCursorException $e) {
            $this->slaveOkay(false);
            MongoCursor::doQuery();
        }
    }
}

?>
```

MongoCursor::explain
====================

Return an explanation of the query, often useful for optimization and
debugging

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCursor::explain</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns an explanation of the query.

### Examples

**Example \#1 <span class="function">MongoCursor::explain</span>
example**

``` php
<?php

$cursor = $collection->find(array("x"=>1), array("y"));
$cursor->sort(array("z" => 1))->limit(4)->skip(5);

var_dump($cursor->explain());

?>
```

The above example will output something similar to:

    array(8) {
      ["cursor"]=>
      string(15) "BtreeCursor x_1"
      ["startKey"]=>
      array(1) {
        ["x"]=>
        int(1)
      }
      ["endKey"]=>
      array(1) {
        ["x"]=>
        int(1)
      }
      ["nscanned"]=>
      float(4)
      ["n"]=>
      int(4)
      ["scanAndOrder"]=>
      int(1)
      ["millis"]=>
      int(3)
      ["allPlans"]=>
      array(2) {
        [0]=>
        array(3) {
          ["cursor"]=>
          string(15) "BtreeCursor x_1"
          ["startKey"]=>
          array(1) {
            ["x"]=>
            int(1)
          }
          ["endKey"]=>
          array(1) {
            ["x"]=>
            int(1)
          }
        }
        [1]=>
        array(3) {
          ["cursor"]=>
          string(11) "BasicCursor"
          ["startKey"]=>
          array(0) {
          }
          ["endKey"]=>
          array(0) {
          }
        }
      }
    }

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database.

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/method/cursor.explain/" class="link external">» explain</a>.

MongoCursor::fields
===================

Sets the fields for a query

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::fields</span> ( <span
class="methodparam"><span class="type">array</span> `$f`</span> )

Fields are specified by *"fieldname" : bool*. **`TRUE`** indicates that
a field should be returned, **`FALSE`** indicates that it should not be
returned. You can also use 1 and 0 instead of **`TRUE`** and
**`FALSE`**.

Thus, to return only the "summary" field, one could say:

``` php
<?php

$cursor->fields(array("summary" => true));

?>
```

To return all fields except the "hidden" field:

``` php
<?php

$cursor->fields(array("hidden" => false));

?>
```

### Parameters

`f`  
Fields to return (or not return).

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating or a scalar argument is given.

MongoCursor::getNext
====================

Advances the cursor to the next result, and returns that result

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCursor::getNext</span> ( <span
class="methodparam">void</span> )

> **Note**:
>
> <span class="methodname">MongoCursor::getNext</span> is an alias of
> <span class="methodname">MongoCursor::next</span>.

MongoCursor::getReadPreference
==============================

Get the read preference for this query

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCursor::getReadPreference</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the read preference. The array
contains the values *type* for the string read preference mode
(corresponding to the <span class="classname">MongoClient</span>
constants), and *tagsets* containing a list of all tag set criteria. If
no tag sets were specified, *tagsets* will not be present in the array.

### Examples

**Example \#1 <span
class="methodname">MongoCursor::getReadPreference</span> return value
example**

``` php
<?php

$m = new MongoClient();
$cursor = $m->test->users->find();
$cursor->setReadPreference(MongoClient::RP_SECONDARY, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
    array(),
));
var_dump($cursor->getReadPreference());
?>
```

The above example will output:

    array(2) {
      ["type"]=>
      string(9) "secondary"
      ["tagsets"]=>
      array(3) {
        [0]=>
        array(2) {
          ["dc"]=>
          string(4) "east"
          ["use"]=>
          string(9) "reporting"
        }
        [1]=>
        array(1) {
          ["dc"]=>
          string(7) "west"
        }
        [2]=>
        array(0) {
        }
      }
    }

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoCursor::setReadPreference</span>
-   <span
    class="function">MongoCursorInterface::getReadPreference</span>

MongoCursor::hasNext
====================

Checks if there are any more elements in this cursor

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCursor::hasNext</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns if there is another element.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database and <span
class="classname">MongoCursorTimeoutException</span> if the timeout is
exceeded.

MongoCursor::hint
=================

Gives the database a hint about the query

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::hint</span> ( <span
class="methodparam"><span class="type">mixed</span> `$index`</span> )

### Parameters

`index`  
Index to use for the query. If a string is passed, it should correspond
to an index name. If an array or object is passed, it should correspond
to the specification used to create the index (i.e. the first argument
to <span class="function">MongoCollection::ensureIndex</span>).

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### Changelog

| Version          | Description                                                                                                                          |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.4.0 | The `index` argument now supports index names as string values. In versions before 1.4.0, only array or object values were accepted. |

MongoCursor::immortal
=====================

Sets whether this cursor will timeout

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::immortal</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$liveForever`<span
class="initializer"> = **`TRUE`**</span></span> \] )

After remaining idle on the server for some amount of time, cursors, by
default, "die." This is generally the behavior one wants. The database
cleans up a cursor once all of its results have been sent to the client,
but if the client doesn't request all of the results, the cursor will
languish there, taking up resources. Thus, after a few minutes, the
cursor "times out" and the database assumes the client has gotten
everything it needs and cleans up its the cursor's resources.

If, for some reason, you need a cursor to hang around for a long time,
you can prevent the database from cleaning it up by using this method.
However, if you make a cursor immortal, you need to iterate through all
of its results (or at least until <span
class="methodname">MongoCursor::dead</span> returns **`TRUE`**) or the
cursor will hang around the database *forever*, taking up resources.

### Parameters

`liveForever`  
If the cursor should be immortal.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

MongoCursor::info
=================

Gets information about the cursor's creation and iteration

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCursor::info</span> ( <span
class="methodparam">void</span> )

This can be called before or after the cursor has started iterating.

### Parameters

This function has no parameters.

### Return Values

Returns the namespace, batch size, limit, skip, flags, query, and
projected fields for this cursor. If the cursor has started iterating,
additional information about iteration and the connection will be
included.

### Changelog

| Version           | Description                                                                                                                                                                                                                                                                                                                                    |
|-------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.1.0  | Added a number of other fields, including *id* (the cursor id), *at* (the driver's counter of which document is current), *numReturned* (the number returned by the server in the current batch), and *server* (which server the query was sent to—useful in conjunction with <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>. |
| PECL mongo 1.0.10 | Added *started\_iterating* field, a boolean indicating if cursor is pre- or post-query.                                                                                                                                                                                                                                                        |

### Examples

**Example \#1 <span class="function">MongoCursor::info</span> example**

``` php
<?php
$m = new MongoClient();

$cursor = $m->test->foo->find(array("x" => 4), array("y" => 0));

echo "Before iteration started:\n";
var_dump($cursor->info());

echo "\nAfter iteration started:\n";
$cursor->rewind();
var_dump($cursor->info());

?>
```

The above example will output something similar to:

    Before iteration started:
    array(8) {
      ["ns"]=>
      string(8) "test.foo"
      ["limit"]=>
      int(0)
      ["batchSize"]=>
      int(0)
      ["skip"]=>
      int(0)
      ["flags"]=>
      int(0)
      ["query"]=>
      array(1) {
        ["x"]=>
        int(4)
      }
      ["fields"]=>
      array(1) {
        ["y"]=>
        int(0)
      }
      ["started_iterating"]=>
      bool(false)
    }

    After iteration started:
    array(15) {
      ["ns"]=>
      string(8) "test.foo"
      ["limit"]=>
      int(0)
      ["batchSize"]=>
      int(0)
      ["skip"]=>
      int(0)
      ["flags"]=>
      int(0)
      ["query"]=>
      array(1) {
        ["x"]=>
        int(4)
      }
      ["fields"]=>
      array(1) {
        ["y"]=>
        int(0)
      }
      ["started_iterating"]=>
      bool(true)
      ["id"]=>
      int(0)
      ["at"]=>
      int(0)
      ["numReturned"]=>
      int(1)
      ["server"]=>
      string(25) "localhost:27017;-;.;26450"
      ["host"]=>
      string(9) "localhost"
      ["port"]=>
      int(27017)
      ["connection_type_desc"]=>
      string(10) "STANDALONE"
    }

### See Also

-   <span class="methodname">MongoCursorInterface::info</span>

MongoCursor::key
================

Returns the current result's \_id, or its index within the result set

### Description

<span class="modifier">public</span> <span
class="type">string\|int</span> <span
class="methodname">MongoCursor::key</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The current result's *\_id* as a string. If the result has no *\_id*,
its numeric index within the result set will be returned as an integer.

### See Also

-   <span class="methodname">Iterator::key</span>

MongoCursor::limit
==================

Limits the number of results returned

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::limit</span> ( <span
class="methodparam"><span class="type">int</span> `$num`</span> )

### Parameters

`num`  
The number of results to return.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### See Also

-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/reference/method/cursor.limit/" class="link external">» limit</a>.
-   <span class="function">MongoCursor::batchSize</span>
-   <span class="methodname">MongoCursor::skip</span>

MongoCursor::maxTimeMS
======================

Sets a server-side timeout for this query

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::maxTimeMS</span> ( <span
class="methodparam"><span class="type">int</span> `$ms`</span> )

Specifies a cumulative time limit in milliseconds to be allowed by the
server for processing operations on the cursor.

### Parameters

`ms`  
Specifies a cumulative time limit in milliseconds to be allowed by the
server for processing operations on the cursor.

### Return Values

This cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

Causes methods that fetch results to throw a <span
class="classname">MongoExecutionTimeoutException</span> if the query
takes longer than the specified number of milliseconds in processing
time.

### Examples

**Example \#1 <span class="methodname">MongoCursor::maxTimeMS</span>
example**

In the following example, the server will abort the query if the cursor
requires more than two seconds in processing time to return its results.

``` php
<?php

$cursor = $collection->find();
$cursor->maxTimeMS(2000);

try {
    $results = iterator_to_array($cursor);
} catch (MongoExecutionTimeoutException $e) {
    echo "query took too long!";
}

?>
```

### Notes

**Warning**

Unlike <span class="methodname">MongoCursor::timeout</span>, which
specifies a client-side timeout, <span
class="methodname">MongoCursor::maxTimeMS</span> can be used to cause
the MongoDB server to abort long-running queries. This timeout is
cumulative for the lifetime of the cursor (i.e. each batch will
contribute to this time limit). The timeout only considers processing
time; idle time is not considered.

MongoCursor::next
=================

Advances the cursor to the next result, and returns that result

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCursor::next</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the next document.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database and <span
class="classname">MongoCursorTimeoutException</span> if the timeout is
exceeded.

### See Also

-   <span class="methodname">Iterator::next</span>

MongoCursor::partial
====================

If this query should fetch partial results from *mongos* if a shard is
down

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::partial</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$okay`<span
class="initializer"> = **`TRUE`**</span></span> \] )

This option allows *mongos* to send partial query results if a shard is
unreachable. This is only applicable when running a sharded MongoDB
cluster and connecting to a *mongos*.

If a shard goes down and a query needs to be sent to that shard,
*mongos* will return the results (if any) from shards it already
contacted, then an error message that it could not reach the shard (a
<span class="classname">MongoCursorException</span> in PHP). If you
would like to get whatever results *mongos* can provide and no
exception, you can use this method. Note that this means that you won't
have an indication that a shard is down in your query response.

This has no effect on the query if all shards are reachable. This flag
was implemented in MongoDB version 1.7.5, so will only work with that
version and higher.

### Parameters

`okay`  
If receiving partial results is okay.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

MongoCursor::reset
==================

Clears the cursor

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">MongoCursor::reset</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

**`NULL`**.

MongoCursor::rewind
===================

Returns the cursor to the beginning of the result set

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">MongoCursor::rewind</span> ( <span
class="methodparam">void</span> )

This is identical to the function:

``` php
<?php

public function rewind() {
    $this->reset();
    $this->next();
}

?>
```

### Parameters

This function has no parameters.

### Return Values

**`NULL`**.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database and <span
class="classname">MongoCursorTimeoutException</span> if the timeout is
exceeded.

### See Also

-   <span class="methodname">Iterator::rewind</span>

MongoCursor::setFlag
====================

Sets arbitrary flags in case there is no method available the specific
flag

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::setFlag</span> ( <span
class="methodparam"><span class="type">int</span> `$flag`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$set`<span
class="initializer"> = **`TRUE`**</span></span> \] )

The <span class="classname">MongoCursor</span> class has several methods
for setting flags on the query object. This method is available in case
the MongoDB wire protocol has acquired a new flag, and the driver has
not been updated with a method for this new flag. In all other cases,
the method should be used. See the "See also" section for available
methods.

### Parameters

`flag`  
Which flag to set. You can not set flag 6 (EXHAUST) as the driver does
not know how to handle them. You will get a warning if you try to use
this flag. For available flags, please refer to the wire protocol
<a href="https://docs.mongodb.com/meta-driver/latest/legacy/mongodb-wire-protocol/#MongoWireProtocol-OPQUERY" class="link external">» documentation</a>.

`set`  
Whether the flag should be set (**`TRUE`**) or unset (**`FALSE`**).

### Return Values

Returns this cursor.

### Errors/Exceptions

Shows a warning when an unsupport flag is attempted to be set.

### Changelog

| Version          | Description                                                                                                                   |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.4.0 | Support for flag 3 (OPLOG\_REPLAY) is added. Versions before 1.4.0 would throw a warning saying that the flag is unsupported. |

### Examples

**Example \#1 <span class="function">MongoCursor::setFlag</span>
example**

``` php
<?php
$m = new MongoClient( 'mongodb://localhost:13000', array( 'replSet' => 'seta' ) );
$c = $m->local->selectCollection( 'oplog.rs' );
$cursor = $c->find( array( 'ns' => 'demo.article', 'op' => 'i' ) );
$cursor->setFlag( 1, true ); // sets the tailable flag
$cursor->setFlag( 5, true ); // sets the await data flag
?>
```

### See Also

-   <span class="function">MongoCursor::tailable</span>
-   <span class="function">MongoCursor::immortal</span>
-   <span class="function">MongoCursor::awaitData</span>
-   <span class="function">MongoCursor::partial</span>
-   MongoDB core docs
    on<a href="https://docs.mongodb.com/meta-driver/latest/legacy/mongodb-wire-protocol/#MongoWireProtocol-OPQUERY" class="link external">» wire protocol query flags</a>

MongoCursor::setReadPreference
==============================

Set the read preference for this query

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

### Parameters

`read_preference`  
The read preference mode: **`MongoClient::RP_PRIMARY`**,
**`MongoClient::RP_PRIMARY_PREFERRED`**,
**`MongoClient::RP_SECONDARY`**,
**`MongoClient::RP_SECONDARY_PREFERRED`**, or
**`MongoClient::RP_NEAREST`**.

`tags`  
An array of zero or more tag sets, where each tag set is itself an array
of criteria used to match tags on replica set members.

### Return Values

Returns this cursor.

### Errors/Exceptions

Emits **`E_WARNING`** if either parameter is invalid, or if one or more
tag sets are provided with the **`MongoClient::RP_PRIMARY`** read
preference mode.

### Examples

**Example \#1 <span
class="methodname">MongoCursor::setReadPreference</span> tag set array
syntax example**

``` php
<?php

$m = new MongoClient();
$cursor = $m->test->users->find();

// Prefer the nearest server in the "east" data center also used for reporting,
// but fall back to a server in the "west" data center
$cursor->setReadPreference(MongoClient::RP_NEAREST, array(
    array('dc' => 'east', 'use' => 'reporting'),
    array('dc' => 'west'),
));
?>
```

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoCursor::getReadPreference</span>
-   <span
    class="function">MongoCursorInterface::setReadPreference</span>

MongoCursor::skip
=================

Skips a number of results

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::skip</span> ( <span
class="methodparam"><span class="type">int</span> `$num`</span> )

### Parameters

`num`  
The number of results to skip.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### See Also

-   <span class="methodname">MongoCursor::limit</span>

MongoCursor::slaveOkay
======================

Sets whether this query can be done on a secondary \[deprecated\]

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::slaveOkay</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$okay`<span
class="initializer"> = **`TRUE`**</span></span> \] )

**Warning**

This method is deprecated since version 1.5.0. Instead, please use <span
class="methodname">MongoCursor::setReadPreference</span> and
<a href="/book/mongo.html#Read%20Preferences" class="xref"></a>.

Calling this will make the driver route reads to secondaries if:

-   <span class="simpara"> You are using a replica set, and </span>
-   <span class="simpara"> You created a <span
    class="classname">MongoClient</span> instance using the option
    *"replicaSet" =\> "setName"*, and </span>
-   <span class="simpara"> There is a healthy secondary that can be
    reached by the driver. </span>

You can check which server was used for this query by calling <span
class="function">MongoCursor::info</span> after running the query. It's
*server* field will show which server the query was sent to.

Note that you should use this function even if you do not use the
automatic routing to secondaries. If you connect directly to a secondary
in a replica set, you still need to call this function, which basically
tells the database that you are aware that you might be getting older
data and you're okay with that. If you do not call this, you'll get "not
master" errors when you try to query.

This method will override the static class variable
`MongoCursor::$slaveOkay`. It will also override <span
class="function">Mongo::setSlaveOkay</span>, <span
class="function">MongoDB::setSlaveOkay</span> and <span
class="function">MongoCollection::setSlaveOkay</span>.

### Parameters

`okay`  
If it is okay to query the secondary.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### Examples

**Example \#1 <span class="function">MongoCursor::slaveOkay</span>
example**

``` php
<?php

MongoCursor::$slaveOkay = false;

// cannot query secondary
$cursor = $collection->find();

// can query secondary
$cursor = $collection->find()->slaveOkay();

MongoCursor::$slaveOkay = true;

// can query secondary
$cursor = $collection->find();

// cannot query secondary
$cursor = $collection->find()->slaveOkay(false);

?>
```

### See Also

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <span class="methodname">MongoCursor::setReadPreference</span>
-   <span class="methodname">MongoCursor::getReadPreference</span>

### Changelog

| Version          | Description                                                                                                                                                                      |
|------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.5.0 | This method has been deprecated in favour of <span class="methodname">MongoCursor::setReadPreference</span> and <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>. |

MongoCursor::snapshot
=====================

Use snapshot mode for the query

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::snapshot</span> ( <span
class="methodparam">void</span> )

Use snapshot mode for the query. Snapshot mode ensures that a document
will not be returned more than once because an intervening write
operation results in a move of the document. Documents inserted or
deleted during the lifetime of the cursor may or may not be returned,
irrespective of snapshot mode.

Queries with short responses (less than 1MB) are always effectively
snapshotted.

Snapshot mode may not be used with sorting, explicit hints, or queries
on sharded collections.

### Parameters

This function has no parameters.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/operator/meta/snapshot/" class="link external">» $snapshot operator</a>.

MongoCursor::sort
=================

Sorts the results by given fields

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::sort</span> ( <span
class="methodparam"><span class="type">array</span> `$fields`</span> )

### Parameters

`fields`  
An array of fields by which to sort. Each element in the array has as
key the field name, and as value either *1* for ascending sort, or *-1*
for descending sort.

Each result is first sorted on the first field in the array, then (if it
exists) on the second field in the array, etc. This means that the order
of the fields in the `fields` array is important. See also the examples
section.

### Return Values

Returns the same cursor that this method was called on.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### Examples

**Example \#1 <span class="function">MongoCursor::sort</span> example**

``` php
<?php
// Sort on field x, ascending
$cursor->sort(array('x' => 1));

// The order in the associative array is important. For instance, these two
// examples will yield different results:

// Sort on date ascending and age descending
$cursor->sort(array('date' => 1, 'age' => -1));

// Sort on age descending and date ascending
$cursor->sort(array('age' => -1, 'date' => 1));
?>
```

MongoCursor::tailable
=====================

Sets whether this cursor will be left open after fetching the last
results

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::tailable</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$tail`<span
class="initializer"> = **`TRUE`**</span></span> \] )

Mongo has a feature known as tailable cursors which are similar to the
Unix "tail -f" command.

Tailable means cursor is not closed when the last data is retrieved.
Rather, the cursor marks the final object's position. you can resume
using the cursor later, from where it was located, if more data were
received.

Like any "latent cursor", the cursor may become invalid at some point --
for example if that final object it references were deleted. Thus, you
should be prepared to requery if the cursor is <span
class="function">MongoCursor::dead</span>.

### Parameters

`tail`  
If the cursor should be tailable.

### Return Values

Returns this cursor.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if this
cursor has started iterating.

### Examples

**Example \#1 <span class="function">MongoCursor::tailable</span>
example**

``` php
<?php

$cursor = $collection->find()->tailable();

$results = array();

while (1) {
    if (!$cursor->hasNext()) {
        // we've read all the results, exit
        if ($cursor->dead()) {
            break;
        }
        // read all results so far, wait for more
        sleep(10);
    }
    else {
        $results[] = $cursor->getNext();
    }
}

?>
```

### See Also

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/tutorial/create-tailable-cursor/" class="link external">» tailable cursors</a>.

-   <span class="function">MongoCursor::awaitData</span>

MongoCursor::timeout
====================

Sets a client-side timeout for this query

### Description

<span class="modifier">public</span> <span
class="type">MongoCursor</span> <span
class="methodname">MongoCursor::timeout</span> ( <span
class="methodparam"><span class="type">int</span> `$ms`</span> )

A timeout can be set at any time and will affect subsequent queries on
the cursor, including fetching more results from the database.

### Parameters

`ms`  
The number of milliseconds for the cursor to wait for a response. Use
*-1* to wait forever. By default, the cursor will wait `30000`
milliseconds (30 seconds).

### Return Values

This cursor.

### Errors/Exceptions

Causes methods that fetch results to throw a <span
class="classname">MongoCursorTimeoutException</span> if the query takes
longer than the specified number of milliseconds.

### Examples

**Example \#1 <span class="function">MongoCursor::timeout</span>
example**

In the following example, the driver will wait forever for the initial
database response, and then wait 100ms for subsequent responses.

``` php
<?php

$cursor = $collection->find();
$cursor->timeout(-1);

/* $cursor->hasNext() executes the query. An infinite timeout has been set, so
 * the driver will wait as long as necessary for a response.
 */
while ($cursor->hasNext()) {
    $cursor->timeout(100);

    /* A timeout has now been set, so if the cursor needs to get more results
     * from the database, it will only wait 100ms for a response.
     */
    try {
        print_r($cursor->getNext());
    } catch (MongoCursorTimeoutException $e) {
        echo "query took too long!";
    }
}

?>
```

### Notes

**Warning**

This does not cause the MongoDB server to cancel long-running
operations; it only instructs the driver to stop waiting for a response
and throw a <span class="classname">MongoCursorTimeoutException</span>
after a set time. If you need to specify a server-side timeout for a
query, consider using <span
class="methodname">MongoCursor::maxTimeMS</span>.

### See Also

-   <span class="methodname">MongoCursorInterface::timeout</span>
-   The *socketTimeoutMS* option for <span
    class="function">MongoClient::\_\_construct</span>

MongoCursor::valid
==================

Checks if the cursor is reading a valid result

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCursor::valid</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the current result is not null, and **`FALSE`** otherwise.

### See Also

-   <span class="methodname">Iterator::valid</span>

Introduction
------------

Interface for cursors, which can be used to iterate through results of a
database query or command. This interface is implemented by the <span
class="classname">MongoCursor</span> and <span
class="classname">MongoCommandCursor</span> classes.

> **Note**: <span class="simpara"> Similar to <span
> class="classname">Traversable</span>, this interface cannot be
> implemented in PHP scripts. </span>

Class synopsis
--------------

**MongoCursorInterface**

<span class="ooclass"> class **MongoCursorInterface** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Iterator**
</span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">MongoCursorInterface</span> <span
class="methodname">batchSize</span> ( <span class="methodparam"><span
class="type">int</span> `$batchSize`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">dead</span> ( <span class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">getReadPreference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">info</span> ( <span class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">MongoCursorInterface</span> <span
class="methodname">setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">MongoCursorInterface</span> <span
class="methodname">timeout</span> ( <span class="methodparam"><span
class="type">int</span> `$ms`</span> )

/\* Inherited methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">mixed</span> <span
class="methodname">Iterator::current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">scalar</span> <span
class="methodname">Iterator::key</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Iterator::next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">Iterator::rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Iterator::valid</span> ( <span
class="methodparam">void</span> )

}

MongoCursorInterface::batchSize
===============================

Limits the number of elements returned in one batch

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">MongoCursorInterface</span> <span
class="methodname">MongoCursorInterface::batchSize</span> ( <span
class="methodparam"><span class="type">int</span> `$batchSize`</span> )

A cursor typically fetches a batch of result objects and stores them
locally. This method sets the batch size value to configure the amount
of documents retrieved from the server in one round trip.

### Parameters

`batchSize`  
The number of results to return per batch.

### Return Values

Returns this cursor.

MongoCursorInterface::dead
==========================

Checks if there are results that have not yet been sent from the
database

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">MongoCursorInterface::dead</span> ( <span
class="methodparam">void</span> )

This method checks whether the cursor has been exhausted and the
database has no more results to send to the client. A cursor being
"dead" does not necessarily mean that there are no more results
available for iteration.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if there are more results that have not yet been sent
to the client, and **`FALSE`** otherwise.

MongoCursorInterface::getReadPreference
=======================================

Get the read preference for this query

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">MongoCursorInterface::getReadPreference</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the read preference. The array
contains the values *type* for the string read preference mode
(corresponding to the <span class="classname">MongoClient</span>
constants), and *tagsets* containing a list of all tag set criteria. If
no tag sets were specified, *tagsets* will not be present in the array.

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span
    class="function">MongoCursorInterface::setReadPreference</span>

MongoCursorInterface::info
==========================

Gets information about the cursor's creation and iteration

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">array</span> <span
class="methodname">MongoCursorInterface::info</span> ( <span
class="methodparam">void</span> )

Returns information about the cursor's creation and iteration. This can
be called before or after the cursor has started iterating.

### Parameters

This function has no parameters.

### Return Values

Returns the namespace, batch size, limit, skip, flags, query, and
projected fields for this cursor. If the cursor has started iterating,
additional information about iteration and the connection will be
included.

MongoCursorInterface::setReadPreference
=======================================

Set the read preference for this query

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">MongoCursorInterface</span> <span
class="methodname">MongoCursorInterface::setReadPreference</span> (
<span class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

### Parameters

`read_preference`  
The read preference mode: **`MongoClient::RP_PRIMARY`**,
**`MongoClient::RP_PRIMARY_PREFERRED`**,
**`MongoClient::RP_SECONDARY`**,
**`MongoClient::RP_SECONDARY_PREFERRED`**, or
**`MongoClient::RP_NEAREST`**.

`tags`  
An array of zero or more tag sets, where each tag set is itself an array
of criteria used to match tags on replica set members.

### Return Values

Returns this cursor.

### Errors/Exceptions

Emits **`E_WARNING`** if either parameter is invalid, or if one or more
tag sets are provided with the **`MongoClient::RP_PRIMARY`** read
preference mode.

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span
    class="function">MongoCursorInterface::getReadPreference</span>

MongoCursorInterface::timeout
=============================

Sets a client-side timeout for this query

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span
class="type">MongoCursorInterface</span> <span
class="methodname">MongoCursorInterface::timeout</span> ( <span
class="methodparam"><span class="type">int</span> `$ms`</span> )

A timeout can be set at any time and will affect subsequent data
retrieval associated with this cursor, including fetching more results
from the database.

### Parameters

`ms`  
The number of milliseconds for the cursor to wait for a response. Use
*-1* to wait forever. By default, the cursor will wait `30000`
milliseconds (30 seconds).

### Return Values

Returns this cursor.

### Errors/Exceptions

Causes methods that fetch results to throw a <span
class="classname">MongoCursorTimeoutException</span> if the data fetch
takes longer than the specified number of milliseconds.

### See Also

-   The *socketTimeoutMS* option for <span
    class="function">MongoClient::\_\_construct</span>

Introduction
------------

A command cursor is similar to a <span
class="classname">MongoCursor</span> except that you use it for
iterating through the results of a database command instead of a normal
query. Command cursors are useful for iterating over large result sets
that might exceed the document size limit (currently 16MB) of a single
<span class="function">MongoDB::command</span> response.

While you can create command cursors using <span
class="function">MongoCommandCursor::\_\_construct</span> or the <span
class="function">MongoCommandCursor::createFromDocument</span> factory
method, you will generally want to use command-specific helpers such as
<span class="function">MongoCollection::aggregateCursor</span>.

Note that the cursor does not "contain" the database command's results;
it just manages iteration through them. Thus, if you print a cursor
(f.e. with <span class="function">var\_dump</span> or <span
class="function">print\_r</span>), you will see the cursor object but
not the result documents.

Cursor Stages
-------------

A <span class="classname">MongoCommandCursor</span> has two "life
stages": pre- and post- command. When a cursor is created, it has not
yet contacted the database, so it is in its pre-command state. When the
client first attempts to get a result (by calling <span
class="function">MongoCommandCursor::rewind</span>, directly or
indirectly), the cursor moves into the post-command state.

The command cursor's batch size and socket timeout may be configured in
both the pre- and post- command states.

**Example \#1 Adding options to <span
class="classname">MongoCommandCursor</span>**

``` php
<?php

$cursor = new MongoCommandCursor(...);

$cursor = $cursor->batchSize( 4 );

foreach ($cursor as $result) {
    var_dump($result);
}
?>
```

Class synopsis
--------------

**MongoCommandCursor**

<span class="ooclass"> class **MongoCommandCursor** </span> <span
class="oointerface">implements <span
class="interfacename">MongoCursorInterface</span> </span> <span
class="oointerface">, <span class="interfacename">Iterator</span>
</span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">batchSize</span> ( <span class="methodparam"><span
class="type">int</span> `$batchSize`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoClient</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$ns`</span> , <span
class="methodparam"><span class="type">array</span> `$command`<span
class="initializer"> = array()</span></span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">createFromDocument</span> ( <span
class="methodparam"><span class="type">MongoClient</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$hash`</span> , <span
class="methodparam"><span class="type">array</span> `$document`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">dead</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getReadPreference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">info</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">key</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">next</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">rewind</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

<span class="modifier">public</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">timeout</span> ( <span class="methodparam"><span
class="type">int</span> `$ms`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">valid</span> ( <span
class="methodparam">void</span> )

}

See Also
--------

-   <span class="methodname">MongoDB::command</span>
-   <span class="methodname">MongoCollection::aggregateCursor</span>

MongoCommandCursor::batchSize
=============================

Limits the number of elements returned in one batch

### Description

<span class="modifier">public</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">MongoCommandCursor::batchSize</span> ( <span
class="methodparam"><span class="type">int</span> `$batchSize`</span> )

A cursor typically fetches a batch of result objects and store them
locally. This method sets the batchSize value to configure the amount of
documents retrieved from the server in one round trip.

### Parameters

`batchSize`  
The number of results to return per batch. Each batch requires a
round-trip to the server.

This cannot override MongoDB's limit on the amount of data it will
return to the client (i.e., if you set batch size to 1,000,000,000,
MongoDB will still only return 4-16MB of results per batch).

### Return Values

Returns this cursor.

### Examples

**Example \#1 <span
class="function">MongoCommandCursor::batchSize</span>**

``` php
<?php
$commandCursor->batchSize(20);
?>
```

### See Also

-   <span class="methodname">MongoCursorInterface::batchSize</span>

MongoCommandCursor::\_\_construct
=================================

Create a new command cursor

### Description

<span class="modifier">public</span> <span
class="methodname">MongoCommandCursor::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoClient</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$ns`</span> , <span
class="methodparam"><span class="type">array</span> `$command`<span
class="initializer"> = array()</span></span> )

Generally, you should not have to construct a <span
class="classname">MongoCommandCursor</span> manually, as there are
helper functions such as <span
class="methodname">MongoCollection::aggregateCursor</span> and <span
class="methodname">MongoCollection::parallelCollectionScan</span>;
however, if the server introduces new commands that can return cursors,
this constructor will be useful in the absence of specific helper
methods. You may also consider using <span
class="methodname">MongoCommandCursor::createFromDocument</span>.

### Parameters

`connection`  
Database connection.

`ns`  
Full name of the database and collection (e.g. *"test.foo"*)

`command`  
Database command.

### Return Values

Returns the new cursor.

### Examples

**Example \#1 <span class="classname">MongoCommandCursor</span>
example**

``` php
<?php
$m = new MongoClient;

// Define the aggregation pipeline
$pipeline = [
    [ '$group' => [
        '_id' => '$country_code',
        'timezones' => [ '$addToSet' => '$timezone' ]
    ] ],
    [ '$sort' => [ '_id' => 1 ] ],
];

// Construct a MongoCommandCursor object
$cursor = new MongoCommandCursor(
    $m, // MongoClient object
    'demo.cities', // namespace
    [
        'aggregate' => 'cities',
        'pipeline' => $pipeline,
        'cursor' => [ 'batchSize' => 0 ],
    ]
);

foreach($cursor as $result) {
   …
}
?>
```

### See Also

-   <span class="function">MongoCommandCursor::createFromDocument</span>
-   <span class="function">MongoCollection::aggregateCursor</span>
-   <span
    class="function">MongoCollection::parallelCollectionScan</span>

MongoCommandCursor::createFromDocument
======================================

Create a new command cursor from an existing command response document

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">MongoCommandCursor::createFromDocument</span> ( <span
class="methodparam"><span class="type">MongoClient</span>
`$connection`</span> , <span class="methodparam"><span
class="type">string</span> `$hash`</span> , <span
class="methodparam"><span class="type">array</span> `$document`</span> )

Use this method if you have a raw command result with cursor information
in it. Note that cursors created with this method cannot be iterated
multiple times, as they will lack the original command necessary for
re-execution.

### Parameters

`connection`  
Database connection.

`hash`  
The connection hash, as obtained through the third by-reference argument
to <span class="methodname">MongoDB::command</span>.

`document`  
Document with cursor information in it. This document needs to contain
the *id*, *ns* and *firstBatch* fields. Such a document is obtained by
calling the <span class="methodname">MongoDB::command</span> with
appropriate arguments to return a cursor, and not just an inline result.
See the example below.

### Return Values

Returns the new cursor.

### Examples

**Example \#1 <span
class="function">MongoCommandCursor::createFromDocument</span>**

``` php
<?php
$m = new MongoClient;
$d = $m->demo;

// Define the aggregation pipeline
$pipeline = [
    [ '$group' => [
        '_id' => '$country_code',
        'timezones' => [ '$addToSet' => '$timezone' ]
    ] ],
    [ '$sort' => [ '_id' => 1 ] ],
];

// Execute the command. The "cursor" option instructs the server to return
// cursor information in the response instead of inline results.
$r = $d->command(
    [
        'aggregate' => 'cities',
        'pipeline' => $pipeline,
        'cursor' => [ 'batchSize' => 1 ],
    ],
    null,
    $hash
);

// Show result and hash
var_dump( $r, $hash );

// Construct the command cursor
$cursor = MongoCommandCursor::createFromDocument( $m, $hash, $r );
?>
```

The above example will output something similar to:

    array(2) {
      ["cursor"]=>
      array(3) {
        ["id"]=>
        object(MongoInt64)#5 (1) {
          ["value"]=>
          string(12) "392143983421"
        }
        ["ns"]=>
        string(11) "demo.cities"
        ["firstBatch"]=>
        array(1) {
          [0]=>
          array(2) {
            ["_id"]=>
            string(2) "AD"
            ["timezones"]=>
            array(1) {
              [0]=>
              string(14) "Europe/Andorra"
            }
          }
        }
      }
      ["ok"]=>
      float(1)
    }
    string(25) "localhost:27017;-;.;17617"

As you can see, the returned cursor information has the *id*, *ns* and
*firstBatch* fields.

### See Also

-   <span class="function">MongoCommandCursor::\_\_construct</span>

MongoCommandCursor::current
===========================

Returns the current element

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCommandCursor::current</span> ( <span
class="methodparam">void</span> )

This returns **`NULL`** until <span
class="function">MongoCommandCursor::rewind</span> is called.

### Parameters

This function has no parameters.

### Return Values

The current result document as an associative array. **`NULL`** will be
returned if there is no result.

### See Also

-   <span class="methodname">Iterator::current</span>

MongoCommandCursor::dead
========================

Checks if there are results that have not yet been sent from the
database

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCommandCursor::dead</span> ( <span
class="methodparam">void</span> )

This method checks whether the <span
class="classname">MongoCommandCursor</span> cursor has been exhausted
and the database has no more results to send to the client. A cursor
being "dead" does not necessarily mean that there are no more results
available for iteration.

### Parameters

This function has no parameters.

### Return Values

Returns **`TRUE`** if there are more results that have not yet been sent
to the client, and **`FALSE`** otherwise.

### See Also

-   <span class="methodname">MongoCursorInterface::dead</span>

MongoCommandCursor::getReadPreference
=====================================

Get the read preference for this command

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCommandCursor::getReadPreference</span> (
<span class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This function returns an array describing the read preference. The array
contains the values *type* for the string read preference mode
(corresponding to the <span class="classname">MongoClient</span>
constants), and *tagsets* containing a list of all tag set criteria. If
no tag sets were specified, *tagsets* will not be present in the array.

### Examples

**Example \#1 <span
class="methodname">MongoCommandCursor::getReadPreference</span> return
value example**

``` php
<?php

$m = new MongoClient('mongodb://rs1.example.com:27017', array('replicaSet' => 'myReplSetName'));
$collection = $m->selectCollection('test', 'people');

// If a MongoCommandCursor is constructed directly, it will inherit the read
// preference of the MongoClient instance passed to its constructor; however,
// MongoCollection::aggregateCursor() will have the MongoCommandCursor inherit
// the collection's read preference.
$collection->setReadPreference(MongoClient::RP_SECONDARY);

$cursor = $collection->aggregateCursor( [
    [ '$group' => [ '_id' => '$name', 'points' => [ '$sum' => '$points' ] ] ],
    [ '$sort' => [ 'points' => -1 ] ],
] );

var_dump($cursor->getReadPreference());

?>
```

The above example will output:

    array(1) {
      ["type"]=>
      string(9) "secondary"
    }

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoCommandCursor::setReadPreference</span>
-   <span
    class="function">MongoCursorInterface::getReadPreference</span>

MongoCommandCursor::info
========================

Gets information about the cursor's creation and iteration

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCommandCursor::info</span> ( <span
class="methodparam">void</span> )

This can be called before or after the cursor has started iterating.

### Parameters

This function has no parameters.

### Return Values

Returns the namespace, batch size, limit, skip, flags, query, and
projected fields for this cursor. If the cursor has started iterating,
additional information about iteration and the connection will be
included.

### Examples

**Example \#1 <span class="function">MongoCommandCursor::info</span>
example**

``` php
<?php
$m = new MongoClient();

$cursor = new MongoCommandCursor(
    $m, // MongoClient object
    'demo.cities', // namespace
    [
        'aggregate' => 'cities',
        'pipeline' => [ [ '$match' => [ '_id' => [ '$exists' => true ] ] ] ],
        'cursor' => [ 'batchSize' => 1 ],
    ]
);

echo "Before iteration started:\n";
var_dump($cursor->info());

echo "\nAfter iteration started:\n";
$cursor->rewind();
var_dump($cursor->info());

?>
```

The above example will output something similar to:

    Before iteration started:
    array(8) {
      ["ns"]=>
      string(11) "demo.cities"
      ["limit"]=>
      int(0)
      ["batchSize"]=>
      int(0)
      ["skip"]=>
      int(0)
      ["flags"]=>
      int(0)
      ["query"]=>
      array(3) {
        ["aggregate"]=>
        string(6) "cities"
        ["pipeline"]=>
        array(1) {
          [0]=>
          array(1) {
            ["$match"]=>
            array(1) {
              ["_id"]=>
              array(1) {
                ["$exists"]=>
                bool(true)
              }
            }
          }
        }
        ["cursor"]=>
        array(1) {
          ["batchSize"]=>
          int(1)
        }
      }
      ["fields"]=>
      NULL
      ["started_iterating"]=>
      bool(false)
    }

    After iteration started:
    array(17) {
      ["ns"]=>
      string(11) "demo.cities"
      ["limit"]=>
      int(0)
      ["batchSize"]=>
      int(0)
      ["skip"]=>
      int(0)
      ["flags"]=>
      int(0)
      ["query"]=>
      array(3) {
        ["aggregate"]=>
        string(6) "cities"
        ["pipeline"]=>
        array(1) {
          [0]=>
          array(1) {
            ["$match"]=>
            array(1) {
              ["_id"]=>
              array(1) {
                ["$exists"]=>
                bool(true)
              }
            }
          }
        }
        ["cursor"]=>
        array(1) {
          ["batchSize"]=>
          int(1)
        }
      }
      ["fields"]=>
      NULL
      ["started_iterating"]=>
      bool(true)
      ["id"]=>
      int(185840310129)
      ["at"]=>
      int(0)
      ["numReturned"]=>
      int(0)
      ["server"]=>
      string(25) "localhost:27017;-;.;23991"
      ["host"]=>
      string(9) "localhost"
      ["port"]=>
      int(27017)
      ["connection_type_desc"]=>
      string(10) "STANDALONE"
      ["firstBatchAt"]=>
      int(0)
      ["firstBatchNumReturned"]=>
      int(1)
    }

### See Also

-   <span class="methodname">MongoCursorInterface::info</span>

MongoCommandCursor::key
=======================

Returns the current result's index within the result set

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoCommandCursor::key</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The current result's index within the result set.

### See Also

-   <span class="methodname">Iterator::key</span>

MongoCommandCursor::next
========================

Advances the cursor to the next result

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">MongoCommandCursor::next</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

**`NULL`**.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database and <span
class="classname">MongoCursorTimeoutException</span> if the timeout is
exceeded.

### See Also

-   <span class="methodname">Iterator::next</span>

MongoCommandCursor::rewind
==========================

Executes the command and resets the cursor to the start of the result
set

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoCommandCursor::rewind</span> ( <span
class="methodparam">void</span> )

If the cursor has already started iteration, the command will be
re-executed.

### Parameters

This function has no parameters.

### Return Values

The raw server result document.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
cannot reach the database and <span
class="classname">MongoCursorTimeoutException</span> if the timeout is
exceeded.

Throws <span class="classname">MongoCursorException</span> if the cursor
was created with <span
class="function">MongoCommandCursor::createFromDocument</span> and has
already started iteration. Such cursors cannot be iterated multiple
times, as they lack the original command necessary for re-execution.

### Examples

**Example \#1 <span class="function">MongoCommandCursor::rewind</span>**

``` php
<?php
$rawResult = $commandCursor->rewind();

// Command cursor is now reset to the start of the result set

var_dump($rawResult);
?>
```

The above example will output something similar to:

    array(2) {
      ["cursor"]=>
      array(3) {
        ["id"]=>
        object(MongoInt64)#5 (1) {
          ["value"]=>
          string(12) "310050110216"
        }
        ["ns"]=>
        string(9) "demo.test"
        ["firstBatch"]=>
        array(1) {
          [0]=>
          array(2) {
            ["_id"]=>
            object(MongoId)#6 (1) {
              ["$id"]=>
              string(24) "52f5691544670a8077b0dc51"
            }
            ["value"]=>
            string(2) "42"
          }
        }
      }
      ["ok"]=>
      float(1)
    }

### See Also

-   <span class="methodname">Iterator::rewind</span>

MongoCommandCursor::setReadPreference
=====================================

Set the read preference for this command

### Description

<span class="modifier">public</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">MongoCommandCursor::setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

### Parameters

`read_preference`  
The read preference mode: **`MongoClient::RP_PRIMARY`**,
**`MongoClient::RP_PRIMARY_PREFERRED`**,
**`MongoClient::RP_SECONDARY`**,
**`MongoClient::RP_SECONDARY_PREFERRED`**, or
**`MongoClient::RP_NEAREST`**.

`tags`  
An array of zero or more tag sets, where each tag set is itself an array
of criteria used to match tags on replica set members.

### Return Values

Returns this cursor.

### Errors/Exceptions

Emits **`E_WARNING`** if either parameter is invalid, or if one or more
tag sets are provided with the **`MongoClient::RP_PRIMARY`** read
preference mode.

### Examples

**Example \#1 <span
class="methodname">MongoCommandCursor::setReadPreference</span> tag set
array syntax example**

``` php
<?php

$m = new MongoClient('mongodb://rs1.example.com:27017', array('replicaSet' => 'myReplSetName'));
$collection = $m->selectCollection('test', 'people');

$cursor = $collection->aggregateCursor( [
    [ '$group' => [ '_id' => '$name', 'points' => [ '$sum' => '$points' ] ] ],
    [ '$sort' => [ 'points' => -1 ] ],
] );

// Prefer the nearest server in the "east" data center also used for reporting,
// but fall back to a server in the "west" data center
$cursor->setReadPreference(MongoClient::RP_NEAREST, [
    [ 'dc' => 'east', 'use' => 'reporting' ],
    [ 'dc' => 'west' ],
] );

foreach ($cursor as $person) {
    // ...
}

// If the read preference is changed, it will be used the next time the cursor
// is rewound and the command is re-executed.
$cursor->setReadPreference(MongoClient::RP_PRIMARY);

foreach ($cursor as $person) {
    // ...
}

?>
```

### See Also

-   The
    <a href="/book/mongo.html#Read%20Preferences" class="link">read preferences</a>
    documentation.
-   <span class="function">MongoCommandCursor::getReadPreference</span>
-   <span
    class="function">MongoCursorInterface::setReadPreference</span>

MongoCommandCursor::timeout
===========================

Sets a client-side timeout for this command

### Description

<span class="modifier">public</span> <span
class="type">MongoCommandCursor</span> <span
class="methodname">MongoCommandCursor::timeout</span> ( <span
class="methodparam"><span class="type">int</span> `$ms`</span> )

A timeout can be set at any time and will affect subsequent data
retrieval associated with this cursor, including fetching more results
from the database.

### Parameters

`ms`  
The number of milliseconds for the cursor to wait for a response. Use
*-1* to wait forever. By default, the cursor will wait `30000`
milliseconds (30 seconds).

### Return Values

This cursor.

### Errors/Exceptions

Causes methods that fetch results to throw a <span
class="classname">MongoCursorTimeoutException</span> if the data fetch
takes longer than the specified number of milliseconds.

### Examples

**Example \#1 <span class="function">MongoCommandCursor::timeout</span>
example**

In the following example, the driver will wait for 60 seconds for the
first response from the aggregate command. It will also wait for 60
seconds each time the server needs to be polled for more information.

``` php
<?php

$m = new MongoClient;
$col = $m->database->collection;

$pipeline = [ … ];

$cursor = $col->aggregateCursor( $pipeline );
$cursor->timeout( 60000 ); // for 60 seconds

foreach ( $cursor as $result ) {
   …
}

?>
```

### Notes

**Warning**

This does not cause the MongoDB server to cancel long-running
operations; it only instructs the driver to stop waiting for a response
and throw a <span class="classname">MongoCursorTimeoutException</span>
after a set time. If you need to specify a server-side timeout for a
command, considering passing the *maxTimeMS* option to <span
class="methodname">MongoCollection::aggregateCursor</span>.

### See Also

-   <span class="function">MongoCollection::aggregateCursor</span>
-   <span class="methodname">MongoCursorInterface::timeout</span>
-   The *socketTimeoutMS* option for <span
    class="function">MongoClient::\_\_construct</span>

MongoCommandCursor::valid
=========================

Checks if the cursor is reading a valid result

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoCommandCursor::valid</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

**`TRUE`** if the current result is not null, and **`FALSE`** otherwise.

### See Also

-   <span class="methodname">Iterator::valid</span>

Types
=====

**Table of Contents**

-   [MongoId](/book/mongo.html#MongoId) — The MongoId class
    -   [MongoId::\_\_construct](/book/mongo.html#MongoId::__construct)
        — Creates a new id
    -   [MongoId::getHostname](/book/mongo.html#MongoId::getHostname) —
        Gets the hostname being used for this machine's ids
    -   [MongoId::getInc](/book/mongo.html#MongoId::getInc) — Gets the
        incremented value to create this id
    -   [MongoId::getPID](/book/mongo.html#MongoId::getPID) — Gets the
        process ID
    -   [MongoId::getTimestamp](/book/mongo.html#MongoId::getTimestamp)
        — Gets the number of seconds since the epoch that this id was
        created
    -   [MongoId::isValid](/book/mongo.html#MongoId::isValid) — Check if
        a value is a valid ObjectId
    -   [MongoId::\_\_set\_state](/book/mongo.html#MongoId::__set_state)
        — Create a dummy MongoId
    -   [MongoId::\_\_toString](/book/mongo.html#MongoId::__toString) —
        Returns a hexidecimal representation of this id
-   [MongoCode](/book/mongo.html#MongoCode) — The MongoCode class
    -   [MongoCode::\_\_construct](/book/mongo.html#MongoCode::__construct)
        — Creates a new code object
    -   [MongoCode::\_\_toString](/book/mongo.html#MongoCode::__toString)
        — Returns this code as a string
-   [MongoDate](/book/mongo.html#MongoDate) — The MongoDate class
    -   [MongoDate::\_\_construct](/book/mongo.html#MongoDate::__construct)
        — Creates a new date
    -   [MongoDate::toDateTime](/book/mongo.html#MongoDate::toDateTime)
        — Returns a DateTime object representing this date
    -   [MongoDate::\_\_toString](/book/mongo.html#MongoDate::__toString)
        — Returns a string representation of this date
-   [MongoRegex](/book/mongo.html#MongoRegex) — The MongoRegex class
    -   [MongoRegex::\_\_construct](/book/mongo.html#MongoRegex::__construct)
        — Creates a new regular expression
    -   [MongoRegex::\_\_toString](/book/mongo.html#MongoRegex::__toString)
        — A string representation of this regular expression
-   [MongoBinData](/book/mongo.html#MongoBinData) — The MongoBinData
    class
    -   [MongoBinData::\_\_construct](/book/mongo.html#MongoBinData::__construct)
        — Creates a new binary data object
    -   [MongoBinData::\_\_toString](/book/mongo.html#MongoBinData::__toString)
        — The string representation of this binary data object
-   [MongoInt32](/book/mongo.html#MongoInt32) — The MongoInt32 class
    -   [MongoInt32::\_\_construct](/book/mongo.html#MongoInt32::__construct)
        — Creates a new 32-bit integer
    -   [MongoInt32::\_\_toString](/book/mongo.html#MongoInt32::__toString)
        — Returns the string representation of this 32-bit integer
-   [MongoInt64](/book/mongo.html#MongoInt64) — The MongoInt64 class
    -   [MongoInt64::\_\_construct](/book/mongo.html#MongoInt64::__construct)
        — Creates a new 64-bit integer
    -   [MongoInt64::\_\_toString](/book/mongo.html#MongoInt64::__toString)
        — Returns the string representation of this 64-bit integer
-   [MongoDBRef](/book/mongo.html#MongoDBRef) — The MongoDBRef class
    -   [MongoDBRef::create](/book/mongo.html#MongoDBRef::create) —
        Creates a new database reference
    -   [MongoDBRef::get](/book/mongo.html#MongoDBRef::get) — Fetches
        the object pointed to by a reference
    -   [MongoDBRef::isRef](/book/mongo.html#MongoDBRef::isRef) — Checks
        if an array is a database reference
-   [MongoMinKey](/book/mongo.html#MongoMinKey) — The MongoMinKey class
-   [MongoMaxKey](/book/mongo.html#MongoMaxKey) — The MongoMaxKey class
-   [MongoTimestamp](/book/mongo.html#MongoTimestamp) — The
    MongoTimestamp class
    -   [MongoTimestamp::\_\_construct](/book/mongo.html#MongoTimestamp::__construct)
        — Creates a new timestamp
    -   [MongoTimestamp::\_\_toString](/book/mongo.html#MongoTimestamp::__toString)
        — Returns a string representation of this timestamp

MongoDB allows programmers to save and query for data expressed in all
of the basic PHP types, compound types (arrays, associative arrays, and
objects), and a half-dozen classes provided by the MongoDB PHP driver
(for regular expressions, dates, and other specialized applications).

Booleans and **`NULL`**
-----------------------

**`TRUE`**, **`FALSE`**, and **`NULL`** can be used as-is.

Numbers
-------

Numbers are distinct from strings in MongoDB: "123" does not match 123.
Thus, if you want to make sure numbers are sorted and matched correctly,
you must make sure that they are actually saved as numbers.

``` php
<?php

$doc = array("a" => 123, "b" => "123");
$collection->insert($doc);

$doc->find(array("a" => 123));   // matches
$doc->find(array("a" => "123")); // doesn't match
$doc->find(array("a" => 123.0)); // matches
$doc->find(array("b" => 123));   // doesn't match
$doc->find(array("b" => "123")); // matches

?>
```

As noted above, floating point numbers do compare with/match integer
numbers as one would expect.

Large Numbers
-------------

By default, on a 32-bit system, numbers are sent to the database as
32-bit integers. On a 64-bit system, they are sent as 64-bit integers.
For backwards compatibility, all systems deserialize 64-bit integers as
floating point numbers. Floating point numbers are not exact. If you
need exact values, you must tweak your
<a href="/book/mongo.html#Runtime%20Configuration" class="link">php.ini settings</a>.

On a 32-bit system, if *mongo.long\_as\_object* is set, 64-bit integers
will be returns as <span class="classname">MongoInt64</span> objects.
The integer will be stored in the *value* field with perfect precision
(as a string). You can also use <span
class="classname">MongoInt64</span> to save 64-bit integers on 32-bit
machines.

On 64-bit systems, you can either set *mongo.long\_as\_object* or set
*mongo.native\_long*. *mongo.native\_long* will return 64-bit integers
and "normal" PHP integers. You can use <span
class="classname">MongoInt32</span> to save 32-bit integers on 64-bit
machines.

You should set the *mongo.long\_as\_object* and *mongo.native\_long*
behavior that you plan to use, even if it is the default behavior (to
protect against future changes to the defaults).

See also:
<a href="/book/mongo.html#Runtime%20Configuration" class="link">php.ini Options</a>,
<span class="classname">MongoInt32</span>, <span
class="classname">MongoInt64</span>.

Strings
-------

Strings must be UTF-8. Non-UTF-8 strings must either be converted to
UTF-8 before being sent to the database or saved as binary data.

Regular expressions can be used to match strings, and are expressed
using the <span class="classname">MongoRegex</span> class.

Binary Data
-----------

Non-UTF-8 strings, images, and any other binary data should be sent to
the database using the <span class="classname">MongoBinData</span> type.

Dates
-----

Dates can be created using the <span class="classname">MongoDate</span>
class. They are stored as milliseconds since the epoch.

<span class="classname">MongoTimestamp</span> is not for saving dates or
timestamps, it is used internally by MongoDB. Unless you are creating a
tool that interacts with the internals of replication or sharding, you
should use <span class="classname">MongoDate</span>, *not* <span
class="classname">MongoTimestamp</span>.

Unique Ids
----------

The driver will automatically create an *\_id* field before inserting a
document (unless one is specified by the user). This field is an
instance of <span class="classname">MongoId</span> (called "ObjectId" in
most other languages).

These ids are 12 bytes long and composed of:

-   4 bytes of timestamp

    No two records can have the same id if they were inserted at
    different times.

-   3 bytes machine id

    No two records can have the same id if they were inserted on
    different machines

-   2 bytes thread id

    No two records can have the same id if they were inserted by
    different threads running on the same machine.

-   3 bytes incrementing value

    Each time an id is created, a global counter is incremented and used
    as the increment value of the next id.

Thus, no two records can have the same id unless a single process on a
single machine managed to insert 256^3 (over 16 million) documents in
one second, overflowing the increment field.

JavaScript
----------

MongoDB comes with a JavaScript engine, so you can embed JavaScript in
queries (using a $where clause), send it directly to the database to be
executed, and use it to perform aggregations.

For security, use <span class="classname">MongoCode</span>'s *scope*
field to use PHP variables in JavaScript. Code that does not require
external values can either use <span class="classname">MongoCode</span>
or just be a string. See the
<a href="/book/mongo.html#Security" class="link">section on security</a>
for more information about sending JavaScript to the database.

Arrays and Objects
------------------

Arrays and objects can also be saved to the database. An array with
ascending numeric keys will be saved as a an array, anything else will
be saved as an object.

``` php
<?php

// $scores will be saved as an array
$scores = array(98, 100, 73, 85);
$collection->insert(array("scores" => $scores));

// $scores will be saved as an object
$scores = array("quiz1" => 98, "midterm" => 100, "quiz2" => 73, "final" => 85);
$collection->insert(array("scores" => $scores));

?>
```

If you query for these objects using the database shell, they will look
like:

``` shell
> db.students.find()
{ "_id" : ObjectId("4b06beada9ad6390dab17c43"), "scores" : [ 98, 100, 73, 85 ] }
{ "_id" : ObjectId("4b06bebea9ad6390dab17c44"), "scores" : { "quiz1" : 98, "midterm" : 100, "quiz2" : 73, "final" : 85 } }
```

The database can also save arbitrary PHP objects (although they will be
returned as associative arrays). The fields are used for the key/value
pairs. For example, a blog post might look like:

``` php
<?php

  // the blog post class
  class Post {

  var $author;
  var $content;
  var $comments = array();
  var $date;

  public function __construct($author, $content) {
  $this->author = $author;
$this->content = $content;
    $this->date = new MongoDate();
  }

  public function setTitle($title) {
    $this->title = $title;
  }
}

// create a simple blog post and insert it into the database
$post1 = new Post("Adam", "This is a blog post");

$blog->insert($post1);


// there is nothing restricting the type of the "author" field, so we can make
// it a nested object
$author = array("name" => "Fred", "karma" => 42);
$post2 = new Post($author, "This is another blog post.");

// we create an extra field by setting the title
$post2->setTitle("Second Post");

$blog->insert($post2);

?>
```

From the database shell, this will look something like:

``` shell
> db.blog.find()
{ "_id" : ObjectId("4b06c263edb87a281e09dad8"), "author" : "Adam", "content" : "This is a blog post", "comments" : [ ], "date" : "Fri Nov 20 2009 11:22:59 GMT-0500 (EST)" }
{ "_id" : ObjectId("4b06c282edb87a281e09dad9"), "author" : { "name" : "Fred", "karma" : 42 }, "content" : "This is a blog post", "comments" : [ ], "date" : "Fri Nov 20 2009 11:23:30 GMT-0500 (EST)", "title" : "Second Post" }
```

The driver will not detect reference loops in arrays and objects. For
example, this will give a fatal error:

``` php
<?php

$collection->insert($GLOBALS);

?>
```

``` txt
Fatal error: Nesting level too deep - recursive dependency?
```

If you need to insert documents that may have recursive dependency, you
have to check for it yourself before passing it to the driver.

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\BSON\\ObjectId</span>

Introduction
------------

A unique identifier created for database objects. If an object is
inserted into the database without an \_id field, an \_id field will be
added to it with a <span class="classname">MongoId</span> instance as
its value. If the data has a naturally occuring unique field (e.g.
username or timestamp) it is fine to use this as the \_id field instead,
and it will not be replaced with a <span
class="classname">MongoId</span>.

Instances of the <span class="classname">MongoId</span> class fulfill
the role that autoincrementing does in a relational database: to provide
a unique key if the data does not naturally have one. Autoincrementing
does not work well with a sharded database, as it is difficult to
determine the next number in the sequence. This class fulfills the
constraints of quickly generating a value that is unique across shards.

Each MongoId is 12 bytes (making its string form 24 hexadecimal
characters). The first four bytes are a timestamp, the next three are a
hash of the client machine's hostname, the next two are the two least
significant bytes of the process id running the script, and the last
three bytes are an incrementing value.

<span class="classname">MongoId</span>s are serializable/unserializable.
Their serialized form is similar to their string form:

    C:7:"MongoId":24:{4af9f23d8ead0e1d32000000}

Class synopsis
--------------

**MongoId**

<span class="ooclass"> class **MongoId** </span> {

<span class="modifier">public</span> <span class="type">string</span>
`$$id` <span class="initializer"> = **`NULL`**</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string\|MongoId</span> `$id`<span
class="initializer"> = **`NULL`**</span></span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getHostname</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getInc</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getPID</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTimestamp</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">isValid</span> ( <span class="methodparam"><span
class="type">mixed</span> `$value`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">MongoId</span> <span
class="methodname">\_\_set\_state</span> ( <span
class="methodparam"><span class="type">array</span> `$props`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Fields
------

`$id`  
<span class="simpara"> This field contains the string representation of
this object. </span>

> **Note**: <span class="simpara"> The property name begins with a *$*
> character. It may be accessed using
> <a href="/language/types/string.html#language.types.string.parsing.complex" class="link">complex variable parsed syntax</a>
> (e.g. *$mongoId-\>{'$id'}*). </span>

See Also
--------

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/object-id/" class="link external">» ObjectIds</a>.

MongoId::\_\_construct
======================

Creates a new id

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\ObjectId::\_\_construct</span>

### Description

<span class="modifier">public</span> <span
class="methodname">MongoId::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string\|MongoId</span> `$id`<span
class="initializer"> = **`NULL`**</span></span> \] )

### Parameters

`id`  
A string (must be 24 hexadecimal characters) or a <span
class="classname">MongoId</span> instance.

### Return Values

Returns a new id.

### Changelog

| Version          | Description                                       |
|------------------|---------------------------------------------------|
| PECL mongo 1.4.0 | An exception is thrown when passed invalid string |

### Examples

**Example \#1 <span class="function">MongoId::\_\_construct</span>
example**

This example shows how to create a new id. This is seldom necessary, as
the driver adds an id to arrays automatically before storing them in the
database.

``` php
<?php

  $id1 = new MongoId();
  echo "$id1\n";

  $id2 = new MongoId();
  echo "$id2\n";

  ?>
```

The above example will output something similar to:

    49a7011a05c677b9a916612a
    49a702d5450046d3d515d10d

**Example \#2 Parameter example**

This example shows how to use a string parameter to initialize a MongoId
with a given value.

``` php
<?php
  $id1 = new MongoId();

  // create a new id from $id1
  $id2 = new MongoId("$id1");

  // show that $id1 and $id2 have the same hexidecimal value
  var_dump($id1 == $id2);
  ?>
```

The above example will output something similar to:

    bool(true)

### See Also

-   <span class="methodname">MongoId::\_\_toString</span>
-   <span class="methodname">MongoId::isvalid</span>

MongoId::getHostname
====================

Gets the hostname being used for this machine's ids

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">MongoId::getHostname</span> ( <span
class="methodparam">void</span> )

This returns the hostname <span class="classname">MongoId</span> is
using to generate unique ids. This should be the same value <span
class="function">gethostname</span> returns.

It is identical to the function:

``` php
<?php

public static function getHostname() {
    return gethostname();
}

?>
```

### Parameters

This function has no parameters.

### Return Values

Returns the hostname.

MongoId::getInc
===============

Gets the incremented value to create this id

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoId::getInc</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the incremented value used to create this <span
class="classname">MongoId</span>.

MongoId::getPID
===============

Gets the process ID

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoId::getPID</span> ( <span
class="methodparam">void</span> )

Extracts the pid from the Mongo ID

### Parameters

This function has no parameters.

### Return Values

Returns the PID of the <span class="classname">MongoId</span>.

MongoId::getTimestamp
=====================

Gets the number of seconds since the epoch that this id was created

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoId::getTimestamp</span> ( <span
class="methodparam">void</span> )

This returns the same thing as running <span
class="function">time</span> when the id is created.

### Parameters

This function has no parameters.

### Return Values

Returns the number of seconds since the epoch that this id was created.
There are only four bytes of timestamp stored, so <span
class="classname">MongoDate</span> is a better choice for storing exact
or wide-ranging times.

MongoId::isValid
================

Check if a value is a valid ObjectId

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">MongoId::isValid</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

This method may be used to check a variable before passing it as an
argument to <span class="function">MongoId::\_\_construct</span>.

### Parameters

`value`  
The value to check for validity.

### Return Values

Returns **`TRUE`** if `value` is a <span
class="classname">MongoId</span> instance or a string consisting of
exactly 24 hexadecimal characters; otherwise, **`FALSE`** is returned.

MongoId::\_\_set\_state
=======================

Create a dummy MongoId

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">MongoId</span> <span
class="methodname">MongoId::\_\_set\_state</span> ( <span
class="methodparam"><span class="type">array</span> `$props`</span> )

This function is only used by PHP internally, it shouldn't need to ever
be called by the user.

It is identical to the function:

``` php
<?php

public static function __set_state($props) {
    return new MongoId("000000000000000000000000");
}

?>
```

### Parameters

`props`  
Theoretically, an array of properties used to create the new id.
However, as MongoId instances have no properties, this is not used.

### Return Values

A new id with the value "000000000000000000000000".

MongoId::\_\_toString
=====================

Returns a hexidecimal representation of this id

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\ObjectId::\_\_toString</span>

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoId::\_\_toString</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This id.

### Examples

**Example \#1 <span class="function">MongoId::\_\_toString</span>
example**

``` php
<?php

$m = new MongoClient();
$collection = $m->selectDB("foo")->selectCollection("bar");

$collection->insert(array( "x" => "y" ));
$collection->insert(array( "x" => "y" ));

$cursor = $collection->find();
$r1 = $cursor->next();
$r2 = $cursor->next();

echo $r1["_id"] . "\n";
echo $r2["_id"] . "\n";

?>
```

The above example will output something similar to:

    49a7011a05c677b9a916612a
    49a702d5450046d3d515d10d

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\BSON\\JavaScript</span>

Introduction
------------

Represents JavaScript code for the database.

MongoCode objects are composed of two parts: a string of code and an
optional scope. The string of code must be valid JavaScript. The scope
is a associative array of variable name/value pairs.

Class synopsis
--------------

**MongoCode**

<span class="ooclass"> class **MongoCode** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$code`</span> \[,
<span class="methodparam"><span class="type">array</span> `$scope`<span
class="initializer"> = array()</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

MongoCode::\_\_construct
========================

Creates a new code object

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\JavaScript::\_\_construct</span>

### Description

<span class="modifier">public</span> <span
class="methodname">MongoCode::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$code`</span> \[,
<span class="methodparam"><span class="type">array</span> `$scope`<span
class="initializer"> = array()</span></span> \] )

### Parameters

`code`  
A string of code.

`scope`  
The scope to use for the code.

### Return Values

Returns a new code object.

### Examples

**Example \#1 <span class="methodname">MongoCode::\_\_construct</span>
example**

``` php
<?php

$code = new MongoCode('function() { '.
    'for(i=0;i<10;i++) {'.
        'db.foo.update({z : i}, {z : x});'.
    '}'.
    'return x-1;'.
 '}', array("x" => 4));
var_dump($code);

?>
```

The above example will output something similar to:

    object(MongoCode)#1 (2) {
      ["scope"]=>
      array(1) {
        ["x"]=>
        int(4)
      }
      ["code"]=>
      string(80) "function() { for(i=0;i<10;i++) { db.foo.update({z : i}, {z : x}); } return x-1; }"
    }

**Example \#2 Using <span class="classname">MongoCode</span> with
$where**

This example queries a collection for elements where the 'x' fields is
less than $y. Notice that PHP objects can be passed into the JavaScript
scope and that the JavaScript function returns a boolean.

``` php
<?php

$cursor = $collection->find(array('$where' => new MongoCode('function() { return this.x < y; }', array('y'=>$y))));

?>
```

MongoCode::\_\_toString
=======================

Returns this code as a string

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this method in the new extension.

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoCode::\_\_toString</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

This code, the scope is not returned.

### Examples

**Example \#1 <span class="function">MongoCode::\_\_toString</span>
example**

``` php
<?php

$code = new MongoCode('return x;', array("x"=>"hi"));
echo "$code\n";

$code = new MongoCode('function() { for(i=0;i<10;i++) { db.foo.update({x:i}, {x:i+1}); } }');
echo "$code\n";

?>
```

The above example will output something similar to:

    return x;
    function() { for(i=0;i<10;i++) { db.foo.update({x:i}, {x:i+1}); } }

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\BSON\\UTCDateTime</span>

Introduction
------------

Represent date objects for the database. This class should be used to
save dates to the database and to query for dates. For example:

**Example \#1 Storing dates with <span
class="classname">MongoDate</span>**

``` php
<?php

// save a date to the database
$collection->save(array("ts" => new MongoDate()));

$start = new MongoDate(strtotime("2010-01-15 00:00:00"));
$end = new MongoDate(strtotime("2010-01-30 00:00:00"));

// find dates between 1/15/2010 and 1/30/2010
$collection->find(array("ts" => array('$gt' => $start, '$lte' => $end)));

?>
```

MongoDB stores dates as milliseconds past the epoch. This means that
dates *do not* contain timezone information. Timezones must be stored in
a separate field if needed. Second, this means that any precision beyond
milliseconds will be lost when the document is sent to/from the
database.

Class synopsis
--------------

**MongoDate**

<span class="ooclass"> class **MongoDate** </span> {

/\* Fields \*/

<span class="modifier">public</span> <span class="type">int</span>
`$sec` ;

<span class="modifier">public</span> <span class="type">int</span>
`$usec` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$sec`<span
class="initializer"> = time()</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$usec`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">toDateTime</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

MongoDate::\_\_construct
========================

Creates a new date

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\UTCDateTime::\_\_construct</span>

### Description

<span class="modifier">public</span> <span
class="methodname">MongoDate::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$sec`<span
class="initializer"> = time()</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$usec`<span
class="initializer"> = 0</span></span> \]\] )

Creates a new date. If no parameters are given, the current time is
used.

### Parameters

`sec`  
Number of seconds since the epoch (i.e. 1 Jan 1970 00:00:00.000 UTC).

`usec`  
Microseconds. Please be aware though that MongoDB's resolution is
*milliseconds* and not microseconds, which means this value will be
truncated to millisecond resolution.

### Return Values

Returns this new date.

### Examples

**Example \#1 <span class="function">MongoDate::\_\_construct</span>
example**

This example demonstrates creating a new date with the current time and
a new date with a given time.

``` php
<?php

$d = new MongoDate();
echo "$d\n";
$d = new MongoDate(1234567890);
echo "$d\n";
$d = new MongoDate(strtotime("2009-05-01 00:00:01"));
echo "$d\n";

?>
```

The above example will output something similar to:

    0.23660600 1235685067
    0.00000000 1234567890
    0.00000000 1241150401

### See Also

-   <span class="methodname">MongoDate::\_\_toString</span>

MongoDate::toDateTime
=====================

Returns a DateTime object representing this date

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\UTCDateTime::toDateTime</span>

### Description

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">MongoDate::toDateTime</span> ( <span
class="methodparam">void</span> )

Returns the <span class="classname">DateTime</span> representation of
this date. The returned <span class="classname">DateTime</span> will use
the UTC time zone.

### Parameters

This function has no parameters.

### Return Values

This date as a <span class="classname">DateTime</span> object.

### Examples

**Example \#1 <span class="function">MongoDate::toDateTime</span>
example**

This example demonstrates creating a DateTime object from a MongoDate
object.

``` php
<?php
$d = new MongoDate(strtotime("2014-11-18 11:01:25"));
var_dump( $d->toDateTime() );
?>
```

The above example will output something similar to:

    class DateTime#2 (3) {
      public $date =>
      string(26) "2014-11-18 11:01:25.000000"
      public $timezone_type =>
      int(1)
      public $timezone =>
      string(6) "+00:00"
    }

MongoDate::\_\_toString
=======================

Returns a string representation of this date

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\UTCDateTime::\_\_toString</span>

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoDate::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns a string representation of this date, similar to the
representation returned by <span class="function">microtime</span>.

### Parameters

This function has no parameters.

### Return Values

This date.

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\BSON\\Regex</span>

Introduction
------------

This class can be used to create regular expressions. Typically, these
expressions will be used to query the database and find matching
strings. More unusually, they can be saved to the database and
retrieved.

Regular expressions consist of four parts. First a */* as starting
delimiter, then the pattern, another */* and finally a string containing
flags.

**Example \#1 Regular expression pattern**

    /pattern/flags

MongoDB recognizes six regular expression flags:

-   *i*: Case insensitive

-   *m*: Multiline

-   *x*: Can contain comments

-   *l*: locale

-   *s*: dotall, "." matches everything, including newlines

-   *u*: match unicode

Class synopsis
--------------

**MongoRegex**

<span class="ooclass"> class **MongoRegex** </span> {

/\* Fields \*/

<span class="modifier">public</span> <span class="type">string</span>
`$regex` ;

<span class="modifier">public</span> <span class="type">string</span>
`$flags` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$regex`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

MongoRegex::\_\_construct
=========================

Creates a new regular expression

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\Regex::\_\_construct</span>

### Description

<span class="modifier">public</span> <span
class="methodname">MongoRegex::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$regex`</span> )

Creates a new regular expression.

### Parameters

`regex`  
Regular expression string of the form */expr/flags*.

### Return Values

Returns a new regular expression.

### Examples

**Example \#1 <span class="function">MongoRegex::\_\_construct</span>
example**

This example uses a regular expression to query for all documents with a
username field starting (*^*) with an *l* and a vowel (*\[aeiouy\]*),
case-insensitive (*/i*).

``` php
<?php
$luke_search = new MongoRegex("/^l[aeiouy]/i");
$cursor = $collection->find(array("username" => $luke_search));
?>
```

### See Also

-   <span class="methodname">MongoRegex::\_\_toString</span>

MongoRegex::\_\_toString
========================

A string representation of this regular expression

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span class="methodname">MongoDB\\BSON\\Regex::\_\_toString</span>

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoRegex::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns a string representation of this regular expression.

### Parameters

This function has no parameters.

### Return Values

This regular expression in the form "/expr/flags".

### Examples

**Example \#1 <span class="function">MongoRegex::\_\_toString</span>
example**

``` php
<?php

$r = new MongoRegex( "/[a-fA-F0-9]{16}/g" );
echo $r->regex . "\n";
echo $r->flags . "\n";
echo "$r\n";

?>
```

The above example will output something similar to:

    [a-fA-F0-9]{16}
    g
    /[a-fA-F0-9]{16}/g

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\BSON\\Binary</span>

Introduction
------------

An object that can be used to store or retrieve binary data from the
database.

The maximum size of a single object that can be inserted into the
database is 16MB. For data that is larger than this (movies, music,
Henry Kissinger's autobiography), use <span
class="classname">MongoGridFS</span>. For data that is smaller than
16MB, you may find it easier to embed it within the document using <span
class="classname">MongoBinData</span>.

For example, to embed an image in a document, one could write:

``` php
<?php

$profile = array(
    "username" => "foobity",
    "pic" => new MongoBinData(file_get_contents("gravatar.jpg"), MongoBinData::GENERIC),
);

$users->save($profile);

?>
```

This class contains a `type` field, which currently gives no additional
functionality in the PHP driver or the database. There are seven
predefined types, which are defined as class constants below. For
backwards compatibility, the PHP driver uses
**`MongoBinData::BYTE_ARRAY`** as the default; however, this may change
to **`MongoBinData::GENERIC`** in the future. Users are encouraged to
specify a type in <span
class="function">MongoBinData::\_\_construct</span>.

Class synopsis
--------------

**MongoBinData**

<span class="ooclass"> class **MongoBinData** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`MongoBinData::GENERIC` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoBinData::FUNC` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoBinData::BYTE_ARRAY` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoBinData::UUID` <span class="initializer"> = 3</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoBinData::UUID_RFC4122` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoBinData::MD5` <span class="initializer"> = 5</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoBinData::CUSTOM` <span class="initializer"> = 128</span> ;

/\* Fields \*/

<span class="modifier">public</span> <span class="type">string</span>
`$bin` ;

<span class="modifier">public</span> <span class="type">int</span>
`$type` <span class="initializer"> = 2</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> \[,
<span class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = 0</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

Binary Data Types
-----------------

**`MongoBinData::GENERIC`**  
<span class="simpara"> Generic binary data. </span>

**`MongoBinData::FUNC`**  
<span class="simpara"> Function. </span>

**`MongoBinData::BYTE_ARRAY`**  
<span class="simpara"> Generic binary data (deprecated in favor of
**`MongoBinData::GENERIC`**). </span>

**`MongoBinData::UUID`**  
<span class="simpara"> Universally unique identifier (deprecated in
favor of **`MongoBinData::UUID_RFC4122`**). </span>

**`MongoBinData::UUID_RFC4122`**  
<span class="simpara"> Universally unique identifier (according to
<a href="http://www.faqs.org/rfcs/rfc4122" class="link external">» RFC 4122</a>).
</span>

**`MongoBinData::MD5`**  
<span class="simpara"> MD5. </span>

**`MongoBinData::CUSTOM`**  
<span class="simpara"> User-defined type. </span>

| Version | Description                                                                       |
|---------|-----------------------------------------------------------------------------------|
| 1.5.0   | Added **`MongoBinData::GENERIC`** and **`MongoBinData::UUID_RFC4122`** constants. |

MongoBinData::\_\_construct
===========================

Creates a new binary data object

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\Binary::\_\_construct</span>

### Description

<span class="modifier">public</span> <span
class="methodname">MongoBinData::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> \[,
<span class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = 0</span></span> \] )

Creates a new binary data object.

There are seven types of binary data currently recognized by the BSON
spec, which are defined as
<a href="/book/mongo.html#Binary%20Data%20Types" class="link">class constants</a>.
For backwards compatibility, the PHP driver uses
**`MongoBinData::BYTE_ARRAY`** as the default; however, this may change
to **`MongoBinData::GENERIC`** in the future. Users are encouraged to
specify a type instead of relying on the default.

### Parameters

`data`  
Binary data.

`type`  
Data type.

### Return Values

Returns a new binary data object.

### Changelog

| Version           | Description                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.5.0  | The default changed from *2* (**`MongoBinData::BYTE_ARRAY`**) to *0* (**`MongoBinData::GENERIC`**).                        |
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when the second argument is not used. The default value for `type` may change in the near future. |

MongoBinData::\_\_toString
==========================

The string representation of this binary data object

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span class="methodname">MongoDB\\BSON\\Binary::getData</span>

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoBinData::\_\_toString</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the string "\<Mongo Binary Data\>". To access the contents of a
<span class="classname">MongoBinData</span>, use the *bin* field.

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this class in the new extension.

Instead, the new extension chooses the appropriate database type
depending on the integer's value.

Introduction
------------

The class can be used to save 32-bit integers to the database on a
64-bit system.

Class synopsis
--------------

**MongoInt32**

<span class="ooclass"> class **MongoInt32** </span> {

/\* Fields \*/

<span class="modifier">public</span> <span class="type">string</span>
`$value` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Fields
------

`value`  
<span class="simpara"> This is the string value of the 32-bit number.
For instance, 123's value would be "123". </span>

MongoInt32::\_\_construct
=========================

Creates a new 32-bit integer

> **Note**:
>
> This extension that defines this class is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this class in the new extension.
>
> Instead, the new extension chooses the appropriate database type
> depending on the integer's value.

### Description

<span class="modifier">public</span> <span
class="methodname">MongoInt32::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Creates a new 32-bit number with the given value.

### Parameters

`value`  
A number.

### Return Values

Returns a new integer.

MongoInt32::\_\_toString
========================

Returns the string representation of this 32-bit integer

> **Note**:
>
> This extension that defines this class is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this class in the new extension.
>
> Instead, the new extension chooses the appropriate database type
> depending on the integer's value.

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoInt32::\_\_toString</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the string representation of this integer.

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this class in the new extension.

Instead, the new extension chooses the appropriate database type
depending on the integer's value.

Introduction
------------

The class can be used to save 64-bit integers to the database on a
32-bit system.

Class synopsis
--------------

**MongoInt64**

<span class="ooclass"> class **MongoInt64** </span> {

/\* Fields \*/

<span class="modifier">public</span> <span class="type">string</span>
`$value` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Fields
------

`value`  
<span class="simpara"> This is the string value of the 64-bit number.
For instance, 123's value would be "123". </span>

MongoInt64::\_\_construct
=========================

Creates a new 64-bit integer

> **Note**:
>
> This extension that defines this class is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this class in the new extension.
>
> Instead, the new extension chooses the appropriate database type
> depending on the integer's value.

### Description

<span class="modifier">public</span> <span
class="methodname">MongoInt64::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Creates a new 64-bit number with the given value.

### Parameters

`value`  
A number.

### Return Values

Returns a new integer.

MongoInt64::\_\_toString
========================

Returns the string representation of this 64-bit integer

> **Note**:
>
> This extension that defines this class is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this class in the new extension.
>
> Instead, the new extension chooses the appropriate database type
> depending on the integer's value.

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoInt64::\_\_toString</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the string representation of this integer.

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. There is no equivalent for this class in the new extension.

The concept of database references, and hence this class, has been
deprecated in the database.

Introduction
------------

This class can be used to create lightweight links between objects in
different collections.

*Motivation*: Suppose we need to refer to a document in another
collection. The easiest way is to create a field in the current
document. For example, if we had a "people" collection and an
"addresses" collection, we might want to create a link between each
person document and an address document:

**Example \#1 Linking documents**

``` php
<?php

$people = $db->people;
$addresses = $db->addresses;

$myAddress = array("line 1" => "123 Main Street", 
    "line 2" => null,
    "city" => "Springfield",
    "state" => "Vermont",
    "country" => "USA");

// save the address
$addresses->insert($myAddress);

// save a person with a reference to the address
$me = array("name" => "Fred", "address" => $myAddress['_id']);
$people->insert($me);

?>
```

Then, later on, we can find the person's address by querying the
"addresses" collection with the <span class="classname">MongoId</span>
we saved in the "people" collection.

Suppose now that we have a more general case, where we don't know which
collection (or even which database) contains the referenced document.
<span class="classname">MongoDBRef</span> is a good choice for this
case, as it is a common format that all of the drivers and the database
understand.

If each person had a list of things they liked which could come from
multiple collections, such as "hobbies", "sports", "books", etc., we
could use <span class="classname">MongoDBRef</span>s to keep track of
what "like" went with what collection:

**Example \#2 Creating MongoDBRef links**

``` php
<?php

$people = $db->selectCollection("people");

// model trains are in the "hobbies" collection
$trainRef = MongoDBRef::create("hobbies", $modelTrains['_id']);
// soccer is in the "sports" collection
$soccerRef = MongoDBRef::create("sports", $soccer['_id']);

// now we'll know what collections the items in the "likes" array came from when
// we retrieve this document
$people->insert(array("name" => "Fred", "likes" => array($trainRef, $soccerRef)));

?>
```

Database references can be thought of as hyperlinks: they give the
unique address of another document, but they do not load it or
automatically follow the link/reference.

A database reference is just a normal associative array, not an instance
of <span class="classname">MongoDBRef</span>, so this class is a little
different than the other data type classes. This class contains
exclusively static methods for manipulating database references.

Class synopsis
--------------

**MongoDBRef**

<span class="ooclass"> class **MongoDBRef** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">create</span> ( <span class="methodparam"><span
class="type">string</span> `$collection`</span> , <span
class="methodparam"><span class="type">mixed</span> `$id`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$database`</span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">get</span> ( <span class="methodparam"><span
class="type">MongoDB</span> `$db`</span> , <span
class="methodparam"><span class="type">array</span> `$ref`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">isRef</span> ( <span class="methodparam"><span
class="type">mixed</span> `$ref`</span> )

}

See Also
--------

MongoDB core docs on
<a href="https://docs.mongodb.com/manual/reference/database-references/" class="link external">» databases references</a>.

MongoDBRef::create
==================

Creates a new database reference

> **Note**:
>
> This extension that defines this class is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this class in the new extension.
>
> The concept of database references, and hence this class, has been
> deprecated.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">MongoDBRef::create</span> ( <span
class="methodparam"><span class="type">string</span>
`$collection`</span> , <span class="methodparam"><span
class="type">mixed</span> `$id`</span> \[, <span
class="methodparam"><span class="type">string</span> `$database`</span>
\] )

If no database is given, the current database is used.

### Parameters

`collection`  
Collection name (without the database name).

`id`  
The \_id field of the object to which to link.

`database`  
Database name.

### Return Values

Returns the reference.

### Examples

**Example \#1 <span class="function">MongoDBRef::create</span> example**

This creates a database reference to a document in the *addresses*
collection. The <span class="function">MongoCollection::getName</span>
function returns the name of the collection (not including the database
name).

``` php
<?php
$addresses = $db->addresses;
$people = $db->people;

// save $address so it has an _id
$addresses->insert($address);

// create a reference
$ref = MongoDBRef::create($addresses->getName(), $address['_id']);

// set the field in $person
$person['address'] = $ref;
$people->save($person);
?>
```

### See Also

-   <span class="methodname">MongoDB::createDBRef</span>
-   <span class="methodname">MongoCollection::createDBRef</span>

MongoDBRef::get
===============

Fetches the object pointed to by a reference

> **Note**:
>
> This extension that defines this class is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this class in the new extension.
>
> The concept of database references, and hence this class, has been
> deprecated.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">MongoDBRef::get</span> ( <span
class="methodparam"><span class="type">MongoDB</span> `$db`</span> ,
<span class="methodparam"><span class="type">array</span> `$ref`</span>
)

### Parameters

`db`  
Database to use.

`ref`  
Reference to fetch.

### Return Values

Returns the document to which the reference refers or **`NULL`** if the
document does not exist (the reference is broken).

### Examples

**Example \#1 <span class="function">MongoCollection::createDBRef</span>
example**

``` php
<?php

// get $person out of the db
$person = $people->findOne();

// dereference the address
$address = MongoDBRef::get($people->db, $person['address']);

?>
```

### See Also

-   <span class="methodname">MongoDB::getDBRef</span>
-   <span class="methodname">MongoCollection::getDBRef</span>

MongoDBRef::isRef
=================

Checks if an array is a database reference

> **Note**:
>
> This extension that defines this class is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. There is no equivalent for this class in the new extension.
>
> The concept of database references, and hence this class, has been
> deprecated.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">MongoDBRef::isRef</span> ( <span
class="methodparam"><span class="type">mixed</span> `$ref`</span> )

This method does not actually follow the reference, so it does not
determine if it is broken or not. It merely checks that `ref` is in
valid database reference format (in that it is an object or array with
$ref and $id fields).

### Parameters

`ref`  
Array or object to check.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\BSON\\MinKey</span>

Introduction
------------

<span class="classname">MongoMinKey</span> is an special type used by
the database that compares less than all other possible BSON values.
Thus, if a query is sorted by a given field in ascending order, any
document with a <span class="classname">MongoMinKey</span> as its value
will be returned first.

<span class="classname">MongoMinKey</span> has no associated fields,
methods, or constants. It is merely the "smallest" value that can be
represented in the database.

> **Note**: <span class="simpara"> <span
> class="classname">MongoMinKey</span> is used internally by MongoDB for
> indexing and sharding. There is generally no reason to use this class
> in an application. </span>

Class synopsis
--------------

**MongoMinKey**

<span class="ooclass"> class **MongoMinKey** </span> {

}

Using <span class="classname">MongoMinKey</span> as a value
-----------------------------------------------------------

``` php
<?php

$collection->insert(array("task" => "lunch", "doBy" => new MongoMinKey));
$collection->insert(array("task" => "staff meeting", "doBy" => new MongoDate(strtotime("+4 days"))));

$cursor = $collection->find()->sort(array("doBy" => 1));

?>
```

The cursor will return the lunch document followed by the staff meeting
document. The lunch document will always be returned first, regardless
of what else is added to the collection (unless other documents are
added with <span class="classname">MongoMinKey</span> in their "doBy"
field).

-   <span class="classname">MongoMaxKey</span>

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\BSON\\MaxKey</span>

Introduction
------------

<span class="classname">MongoMaxKey</span> is an special type used by
the database that compares greater than all other possible BSON values.
Thus, if a query is sorted by a given field in ascending order, any
document with a <span class="classname">MongoMaxKey</span> as its value
will be returned last.

<span class="classname">MongoMaxKey</span> has no associated fields,
methods, or constants. It is merely the "greatest" value that can be
represented in the database.

> **Note**: <span class="simpara"> <span
> class="classname">MongoMaxKey</span> is used internally by MongoDB for
> indexing and sharding. There is generally no reason to use this class
> in an application. </span>

Class synopsis
--------------

**MongoMaxKey**

<span class="ooclass"> class **MongoMaxKey** </span> {

}

Using <span class="classname">MongoMaxKey</span> as a value
-----------------------------------------------------------

``` php
<?php

$collection->insert(array("task" => "dishes", "doBy" => new MongoMaxKey));
$collection->insert(array("task" => "staff meeting", "doBy" => new MongoDate(strtotime("+4 days"))));

$cursor = $collection->find()->sort(array("doBy" => 1));

?>
```

The cursor will return the staff meeting document followed by the dishes
document. The dishes document will always be returned last, regardless
of what else is added to the collection (unless other documents are
added with <span class="classname">MongoMaxKey</span> in their "doBy"
field).

-   <span class="classname">MongoMinKey</span>

**Warning**

This extension that defines this class is deprecated. Instead, the
<a href="/set/mongodb.html" class="link">MongoDB</a> extension should be
used. Alternatives to this class include:

-   <span class="classname">MongoDB\\BSON\\Timestamp</span>

Introduction
------------

<span class="classname">MongoTimestamp</span> is an internal type used
by MongoDB for replication and sharding. It consists of a 4-byte
timestamp (i.e. seconds since the epoch) and a 4-byte increment. This
type is not intended for storing time or date values (e.g. a "createdAt"
field on a document).

> **Note**: <span class="simpara"> Unless you are writing an application
> that interacts with MongoDB's replication oplog or sharding internals:
> stop, go directly to <span class="classname">MongoDate</span>, do not
> pass go, and do not collect 200 dollars. This is not the class you are
> looking for. </span>

Class synopsis
--------------

**MongoTimestamp**

<span class="ooclass"> class **MongoTimestamp** </span> {

/\* Fields \*/

<span class="modifier">public</span> <span class="type">int</span>
`$sec` <span class="initializer"> = 0</span> ;

<span class="modifier">public</span> <span class="type">int</span>
`$inc` <span class="initializer"> = 0</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$sec`<span
class="initializer"> = time()</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$inc`</span> \]\] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">\_\_toString</span> ( <span
class="methodparam">void</span> )

}

MongoTimestamp::\_\_construct
=============================

Creates a new timestamp

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\Timestamp::\_\_construct</span>

### Description

<span class="modifier">public</span> <span
class="methodname">MongoTimestamp::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$sec`<span
class="initializer"> = time()</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$inc`</span> \]\] )

Creates a new timestamp. If no parameters are given, the current time is
used and the increment is automatically provided. The increment is set
to 0 when the module is loaded and is incremented every time this
constructor is called (without the $inc parameter passed in).

### Parameters

`sec`  
Number of seconds since the epoch (i.e. 1 Jan 1970 00:00:00.000 UTC).

`inc`  
Increment.

### Return Values

Returns this new timestamp.

### See Also

-   <span class="methodname">MongoTimestamp::\_\_toString</span>

MongoTimestamp::\_\_toString
============================

Returns a string representation of this timestamp

> **Note**:
>
> This extension that defines this method is deprecated. Instead, the
> <a href="/set/mongodb.html" class="link">MongoDB</a> extension should
> be used. Alternatives to this method include:
>
> -   <span
>     class="methodname">MongoDB\\BSON\\Timestamp::\_\_toString</span>

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoTimestamp::\_\_toString</span> ( <span
class="methodparam">void</span> )

Returns the "sec" field of this timestamp.

### Parameters

This function has no parameters.

### Return Values

The seconds since epoch represented by this timestamp.

GridFS Classes
==============

**Table of Contents**

-   [MongoGridFS](/book/mongo.html#MongoGridFS) — The MongoGridFS class
    -   [MongoGridFS::\_\_construct](/book/mongo.html#MongoGridFS::__construct)
        — Creates new file collections
    -   [MongoGridFS::delete](/book/mongo.html#MongoGridFS::delete) —
        Remove a file and its chunks from the database
    -   [MongoGridFS::drop](/book/mongo.html#MongoGridFS::drop) — Drops
        the files and chunks collections
    -   [MongoGridFS::find](/book/mongo.html#MongoGridFS::find) —
        Queries for files
    -   [MongoGridFS::findOne](/book/mongo.html#MongoGridFS::findOne) —
        Returns a single file matching the criteria
    -   [MongoGridFS::get](/book/mongo.html#MongoGridFS::get) — Retrieve
        a file from the database
    -   [MongoGridFS::put](/book/mongo.html#MongoGridFS::put) — Stores a
        file in the database
    -   [MongoGridFS::remove](/book/mongo.html#MongoGridFS::remove) —
        Remove files and their chunks from the database
    -   [MongoGridFS::storeBytes](/book/mongo.html#MongoGridFS::storeBytes)
        — Stores a string of bytes in the database
    -   [MongoGridFS::storeFile](/book/mongo.html#MongoGridFS::storeFile)
        — Stores a file in the database
    -   [MongoGridFS::storeUpload](/book/mongo.html#MongoGridFS::storeUpload)
        — Stores an uploaded file in the database
-   [MongoGridFSFile](/book/mongo.html#MongoGridFSFile) — The
    MongoGridFSFile class
    -   [MongoGridfsFile::\_\_construct](/book/mongo.html#MongoGridfsFile::__construct)
        — Create a new GridFS file
    -   [MongoGridFSFile::getBytes](/book/mongo.html#MongoGridFSFile::getBytes)
        — Returns this file's contents as a string of bytes
    -   [MongoGridFSFile::getFilename](/book/mongo.html#MongoGridFSFile::getFilename)
        — Returns this file's filename
    -   [MongoGridFSFile::getResource](/book/mongo.html#MongoGridFSFile::getResource)
        — Returns a resource that can be used to read the stored file
    -   [MongoGridFSFile::getSize](/book/mongo.html#MongoGridFSFile::getSize)
        — Returns this file's size
    -   [MongoGridFSFile::write](/book/mongo.html#MongoGridFSFile::write)
        — Writes this file to the filesystem
-   [MongoGridFSCursor](/book/mongo.html#MongoGridFSCursor) — The
    MongoGridFSCursor class
    -   [MongoGridFSCursor::\_\_construct](/book/mongo.html#MongoGridFSCursor::__construct)
        — Create a new cursor
    -   [MongoGridFSCursor::current](/book/mongo.html#MongoGridFSCursor::current)
        — Returns the current file
    -   [MongoGridFSCursor::getNext](/book/mongo.html#MongoGridFSCursor::getNext)
        — Return the next file to which this cursor points, and advance
        the cursor
    -   [MongoGridFSCursor::key](/book/mongo.html#MongoGridFSCursor::key)
        — Returns the current result's filename

Introduction
------------

Utilities for storing and retrieving files from the database.

GridFS is a storage specification all supported drivers implement.
Basically, it defines two collections: *files*, for file metadata, and
*chunks*, for file content. If the file is large, it will automatically
be split into smaller chunks and each chunk will be saved as a document
in the chunks collection.

Each document in the files collection contains the filename, upload
date, and md5 hash. It also contains a unique *\_id* field, which can be
used to query the chunks collection for the file's content. Each
document in the chunks collection contains a chunk of binary data, a
*files\_id* field that matches its file's *\_id*, and the position of
this chunk in the overall file.

For example, the files document is something like:

``` php
<?php
array("_id" => 123456789, "filename" => "foo.txt", "chunkSize" => 3, "length" => 12);
?>
```

and the chunks documents look like:

``` php
<?php
array("files_id" => 123456789, "n" => 0, "data" => new MongoBinData("abc"));
array("files_id" => 123456789, "n" => 1, "data" => new MongoBinData("def"));
array("files_id" => 123456789, "n" => 2, "data" => new MongoBinData("ghi"));
array("files_id" => 123456789, "n" => 3, "data" => new MongoBinData("jkl"));
?>
```

Of course, the default chunk size is thousands of bytes, but that makes
an unwieldy example.

Inter-Language Compatibility
----------------------------

You should be able to use any files created by MongoGridFS with any
other drivers, and vice versa. However, some drivers expect that all
metadata associated with a file be in a "metadata" field. If you're
going to be using other languages, it's a good idea to wrap info you
might want them to see in a "metadata" field. For example, instead of:

``` php
<?php

$grid->storeFile("somefile.txt", array("date" => new MongoDate()));

?>
```

use something like:

``` php
<?php

$grid->storeFile("somefile.txt", array("metadata" => array("date" => new MongoDate())));

?>
```

The <span class="classname">MongoGridFS</span> Family
-----------------------------------------------------

<span class="classname">MongoGridFS</span> represents the files and
chunks collections. <span class="classname">MongoGridFS</span> extends
MongoCollection, and an instance of <span
class="classname">MongoGridFS</span> has access to all of <span
class="classname">MongoCollection</span> methods, which act on the files
collection:

``` php
<?php

$grid = $db->getGridFS();
$grid->update(array("filename" => "foo"), $newObj); // update on the files collection

?>
```

Another example of manipulating metadata:

``` php
<?php

// save a file
$id = $grid->storeFile("game.tgz");
$game = $grid->findOne();

// add a downloads counter
$game->file['downloads'] = 0;
$grid->save($game->file);

// increment the counter
$grid->update(array("_id" => $id), array('$inc' => array("downloads" => 1)));

?>
```

You can also access the chunks collection from an instance of <span
class="classname">MongoGridFS</span>:

``` php
<?php

  $chunks = $grid->chunks; // $chunks is a normal MongoCollection
$chunks->insert(array("x" => 4));

?>
```

There are some methods for <span class="classname">MongoGridFS</span>
with the same name as <span class="classname">MongoCollection</span>
methods, that behave slightly differently. For example, <span
class="function">MongoGridFS::remove</span> will remove any objects that
match the criteria from the files collection and their content from the
chunks collection.

To store something new in GridFS, there are a couple options. If you
have a filename, you can say:

``` php
<?php

$grid->storeFile($filename, array("whatever" => "metadata", "you" => "want"));

?>
```

If you have a string of bytes that isn't a file, you can also store that
using <span class="function">MongoGridFS::storeBytes</span>:

``` php
<?php

$grid->storeBytes($bytes, array("whatever" => "metadata", "you" => "want"));

?>
```

Querying a <span class="classname">MongoGridFS</span> collection returns
a <span class="classname">MongoGridFSCursor</span>, which behaves like a
normal <span class="classname">MongoCursor</span> except that it returns
<span class="classname">MongoGridFSFiles</span> instead of associative
arrays.

<span class="classname">MongoGridFSFiles</span> can be written back to
disc using <span class="function">MongoGridFSFile::write</span> or
retrieved in memory using <span
class="function">MongoGridFSFile::getBytes</span>. There is currently no
method that automatically streams chunks, but it would be fairly easy to
write by querying the *$grid-\>chunks* collection.

<span class="classname">MongoGridFSFile</span> objects contain a field
file which contains any file metadata.

Class synopsis
--------------

**MongoGridFS**

<span class="ooclass"> <span class="modifier">extends</span> class
**MongoCollection** </span> {

/\* Fields \*/

<span class="modifier">public</span> <span
class="type">MongoCollection</span> `$chunks` <span class="initializer">
= **`NULL`**</span> ;

<span class="modifier">protected</span> <span class="type">string</span>
`$filesName` <span class="initializer"> = **`NULL`**</span> ;

<span class="modifier">protected</span> <span class="type">string</span>
`$chunksName` <span class="initializer"> = **`NULL`**</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoDB</span> `$db`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$prefix`<span class="initializer"> = "fs"</span></span> \[, <span
class="methodparam"><span class="type">mixed</span> `$chunks`<span
class="initializer"> = "fs"</span></span> \]\] )

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span class="methodname">delete</span> (
<span class="methodparam"><span class="type">mixed</span> `$id`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">drop</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoGridFSCursor</span> <span
class="methodname">find</span> (\[ <span class="methodparam"><span
class="type">array</span> `$query`<span class="initializer"> =
array()</span></span> \[, <span class="methodparam"><span
class="type">array</span> `$fields`<span class="initializer"> =
array()</span></span> \]\] )

<span class="modifier">public</span> <span
class="type">MongoGridFSFile</span> <span
class="methodname">findOne</span> (\[ <span class="methodparam"><span
class="type">mixed</span> `$query`<span class="initializer"> =
array()</span></span> \[, <span class="methodparam"><span
class="type">mixed</span> `$fields`<span class="initializer"> =
array()</span></span> \]\] )

<span class="modifier">public</span> <span
class="type">MongoGridFSFile</span> <span class="methodname">get</span>
( <span class="methodparam"><span class="type">mixed</span> `$id`</span>
)

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">put</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">array</span> `$metadata`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span class="methodname">remove</span>
(\[ <span class="methodparam"><span class="type">array</span>
`$criteria`<span class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">storeBytes</span> ( <span
class="methodparam"><span class="type">string</span> `$bytes`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$metadata`<span class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">storeFile</span> ( <span
class="methodparam"><span class="type">string\|resource</span>
`$filename`</span> \[, <span class="methodparam"><span
class="type">array</span> `$metadata`<span class="initializer"> =
array()</span></span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">storeUpload</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$metadata`</span> \] )

}

See Also
--------

-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/core/gridfs/" class="link external">» GridFS</a>
-   LightCube Solutions blog post on
    <a href="http://www.lightcubesolutions.com/blog/?p=209" class="link external">» saving user uploads</a>
-   LightCube Solutions blog post on
    <a href="http://www.lightcubesolutions.com/blog/?p=228" class="link external">» adding metadata to files</a>

MongoGridFS::\_\_construct
==========================

Creates new file collections

### Description

<span class="modifier">public</span> <span
class="methodname">MongoGridFS::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoDB</span> `$db`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$prefix`<span class="initializer"> = "fs"</span></span> \[, <span
class="methodparam"><span class="type">mixed</span> `$chunks`<span
class="initializer"> = "fs"</span></span> \]\] )

Files as stored across two collections, the first containing file meta
information, the second containing chunks of the actual file. By
default, fs.files and fs.chunks are the collection names used.

Use one argument to specify a prefix other than "fs":

``` description
$fs = new MongoGridFS($db, "myfiles");
```

uses myfiles.files and myfiles.chunks collections.

### Parameters

`db`  
Database.

`files`  
Optional collection name prefix.

MongoGridFS::delete
===================

Remove a file and its chunks from the database

### Description

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span
class="methodname">MongoGridFS::delete</span> ( <span
class="methodparam"><span class="type">mixed</span> `$id`</span> )

> **Note**:
>
> <span class="methodname">MongoGridFS::delete</span> is a convenience
> method for calling <span class="methodname">MongoGridFS::remove</span>
> with specific `criteria` and default `options` parameters.

### Parameters

`id`  
*\_id* of the file to remove.

### Return Values

Returns an array containing the status of the removal (with respect to
the *files* collection) if a
<a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
is applied. Otherwise, returns **`TRUE`**.

Fields in the status array are described in the documentation for <span
class="function">MongoCollection::insert</span>.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

MongoGridFS::drop
=================

Drops the files and chunks collections

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoGridFS::drop</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The database response.

MongoGridFS::find
=================

Queries for files

### Description

<span class="modifier">public</span> <span
class="type">MongoGridFSCursor</span> <span
class="methodname">MongoGridFS::find</span> (\[ <span
class="methodparam"><span class="type">array</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$fields`<span
class="initializer"> = array()</span></span> \]\] )

### Parameters

`query`  
The query.

`fields`  
Fields to return.

### Return Values

A <span class="classname">MongoGridFSCursor</span>.

MongoGridFS::findOne
====================

Returns a single file matching the criteria

### Description

<span class="modifier">public</span> <span
class="type">MongoGridFSFile</span> <span
class="methodname">MongoGridFS::findOne</span> (\[ <span
class="methodparam"><span class="type">mixed</span> `$query`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">mixed</span> `$fields`<span
class="initializer"> = array()</span></span> \]\] )

### Parameters

`query`  
The filename or criteria for which to search.

### Return Values

Returns a <span class="classname">MongoGridFSFile</span> or **`NULL`**.

### Examples

**Example \#1 <span class="methodname">MongoGridFS::findOne</span>
example**

Example demonstrating how to find a single file from the MongoGridFS.

``` php
<?php

$downloads = $mongo->my_db->getGridFS('downloads');

$downloads->storeFile('filename.tgz');

$download = $downloads->findOne('filename.tgz'); // instance of MongoGridFSFile

print_r($download);
?>
```

See <span class="classname">MongoGridFSFile</span> for more information
about how to work with files.

The above example will output something similar to:

    MongoGridFSFile Object
    (
        [file] => Array
            (
                [_id] => MongoId Object
                    (
                    )

                [filename] => filename.tgz
                [uploadDate] => MongoDate Object
                    (
                        [sec] => 1274288014
                        [usec] => 467000
                    )

                [chunkSize] => 262144
                [md5] => d41d8cd98f00b204e9800998ecf8427e
            )

        [gridfs:protected] => MongoGridFS Object
            (
                [chunks] => MongoCollection Object
                    (
                    )

                [filesName:protected] => downloads.files
                [chunksName:protected] => downloads.chunks
            )

    )

MongoGridFS::get
================

Retrieve a file from the database

### Description

<span class="modifier">public</span> <span
class="type">MongoGridFSFile</span> <span
class="methodname">MongoGridFS::get</span> ( <span
class="methodparam"><span class="type">mixed</span> `$id`</span> )

### Parameters

`id`  
*\_id* of the file to find.

### Return Values

Returns the file, if found, or **`NULL`**.

MongoGridFS::put
================

Stores a file in the database

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">MongoGridFS::put</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$metadata`<span class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

> **Note**:
>
> <span class="methodname">MongoGridFS::put</span> is an alias of <span
> class="methodname">MongoGridFS::storeFile</span>.

### Parameters

`filename`  
Name of the file to store.

`metadata`  
Other metadata fields to include in the file document.

> **Note**:
>
> These fields may also overwrite those that would be created
> automatically by the driver, as described in the MongoDB core
> documentation for the
> <a href="https://docs.mongodb.com/manual/core/gridfs/#the-files-collection" class="link external">» files collection</a>.
> Some practical use cases for this behavior would be to specify a
> custom *chunkSize* or *\_id* for the file.

`options`  
An array of options for the insert operations executed against the
*chunks* and *files* collections. See <span
class="function">MongoCollection::insert</span> for documentation on
these these options.

### Return Values

Returns the *\_id* of the saved file document. This will be a generated
<span class="classname">MongoId</span> unless an *\_id* was explicitly
specified in the `metadata` parameter.

### Errors/Exceptions

Throws <span class="classname">MongoGridFSException</span> if there is
an error reading `filename` or inserting into the *chunks* or *files*
collections.

### See Also

-   <span class="function">MongoGridFS::storeBytes</span>
-   <span class="function">MongoGridFS::storeFile</span>
-   <span class="function">MongoGridFS::storeUpload</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/core/gridfs/" class="link external">» GridFS</a>

MongoGridFS::remove
===================

Remove files and their chunks from the database

### Description

<span class="modifier">public</span> <span
class="type">bool\|array</span> <span
class="methodname">MongoGridFS::remove</span> (\[ <span
class="methodparam"><span class="type">array</span> `$criteria`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

### Parameters

`criteria`  
The filename or criteria for which to search.

`options`  
An array of options for the remove operations executed against the
*chunks* and *files* collections. See <span
class="function">MongoCollection::remove</span> for documentation on
these options.

### Return Values

Returns an array containing the status of the removal (with respect to
the *files* collection) if the *"w"* option is set. Otherwise, returns
**`TRUE`**.

Fields in the status array are described in the documentation for <span
class="function">MongoCollection::insert</span>.

### Errors/Exceptions

Throws <span class="classname">MongoCursorException</span> if the *"w"*
option is set and the write fails.

Throws <span class="classname">MongoCursorTimeoutException</span> if the
*"w"* option is set to a value greater than one and the operation takes
longer than `MongoCursor::$timeout` milliseconds to complete. This does
not kill the operation on the server, it is a client-side timeout. The
operation in `MongoCollection::$wtimeout` is milliseconds.

MongoGridFS::storeBytes
=======================

Stores a string of bytes in the database

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">MongoGridFS::storeBytes</span> ( <span
class="methodparam"><span class="type">string</span> `$bytes`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$metadata`<span class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \]\] )

### Parameters

`bytes`  
String of bytes to store.

`metadata`  
Other metadata fields to include in the file document.

> **Note**:
>
> These fields may also overwrite those that would be created
> automatically by the driver, as described in the MongoDB core
> documentation for the
> <a href="https://docs.mongodb.com/manual/core/gridfs/#the-files-collection" class="link external">» files collection</a>.
> Some practical use cases for this behavior would be to specify a
> custom *chunkSize* or *\_id* for the file.

`options`  
An array of options for the insert operations executed against the
*chunks* and *files* collections. See <span
class="function">MongoCollection::insert</span> for documentation on
these these options.

### Return Values

Returns the *\_id* of the saved file document. This will be a generated
<span class="classname">MongoId</span> unless an *\_id* was explicitly
specified in the `metadata` parameter.

### Errors/Exceptions

Throws <span class="classname">MongoGridFSException</span> if there is
an error inserting into the *chunks* or *files* collections.

### Examples

**Example \#1 <span class="function">MongoGridFS::storeBytes</span> with
additional metadata**

``` php
<?php
$m = new MongoClient();
$gridfs = $m->selectDB('test')->getGridFS();

$bytes = 'abcdefghijklmnopqrstuvwxyz';
$id = $gridfs->storeBytes($bytes, array('_id' => 'alphabet'));
$gridfsFile = $gridfs->get($id);

var_dump($gridfsFile->file);
?>
```

The above example will output something similar to:

    array(7) {
      ["_id"]=>
      string(8) "alphabet"
      ["uploadDate"]=>
      object(MongoDate)#7 (0) {
      }
      ["length"]=>
      int(26)
      ["chunkSize"]=>
      int(262144)
      ["md5"]=>
      string(32) "c3fcd3d76192e4007dfb496cca67e13b"
    }

### See Also

-   <span class="function">MongoGridFS::put</span>
-   <span class="function">MongoGridFS::storeFile</span>
-   <span class="function">MongoGridFS::storeUpload</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/core/gridfs/" class="link external">» GridFS</a>

MongoGridFS::storeFile
======================

Stores a file in the database

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">MongoGridFS::storeFile</span> ( <span
class="methodparam"><span class="type">string\|resource</span>
`$filename`</span> \[, <span class="methodparam"><span
class="type">array</span> `$metadata`<span class="initializer"> =
array()</span></span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
array()</span></span> \]\] )

### Parameters

`filename`  
Name of the file or a readable stream to store.

`metadata`  
Other metadata fields to include in the file document.

> **Note**:
>
> These fields may also overwrite those that would be created
> automatically by the driver, as described in the MongoDB core
> documentation for the
> <a href="https://docs.mongodb.com/manual/core/gridfs/#the-files-collection" class="link external">» files collection</a>.
> Some practical use cases for this behavior would be to specify a
> custom *chunkSize* or *\_id* for the file.

`options`  
An array of options for the insert operations executed against the
*chunks* and *files* collections. See <span
class="function">MongoCollection::insert</span> for documentation on
these these options.

### Return Values

Returns the *\_id* of the saved file document. This will be a generated
<span class="classname">MongoId</span> unless an *\_id* was explicitly
specified in the `metadata` parameter.

### Errors/Exceptions

Throws <span class="classname">MongoGridFSException</span> if there is
an error reading `filename` or inserting into the *chunks* or *files*
collections.

### Examples

**Example \#1 <span class="function">MongoGridFS::storeFile</span> with
additional metadata**

``` php
<?php
$m = new MongoClient();
$gridfs = $m->selectDB('test')->getGridFS();

$id = $gridfs->storeFile('example.txt', array('contentType' => 'plain/text'));
$gridfsFile = $gridfs->get($id);

var_dump($gridfsFile->file);
?>
```

The above example will output something similar to:

    array(7) {
      ["_id"]=>
      object(MongoId)#6 (0) {
      }
      ["contentType"]=>
      string(10) "plain/text"
      ["filename"]=>
      string(11) "example.txt"
      ["uploadDate"]=>
      object(MongoDate)#7 (0) {
      }
      ["length"]=>
      int(26)
      ["chunkSize"]=>
      int(262144)
      ["md5"]=>
      string(32) "c3fcd3d76192e4007dfb496cca67e13b"
    }

### See Also

-   <span class="function">MongoGridFS::put</span>
-   <span class="function">MongoGridFS::storeBytes</span>
-   <span class="function">MongoGridFS::storeUpload</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/core/gridfs/" class="link external">» GridFS</a>

MongoGridFS::storeUpload
========================

Stores an uploaded file in the database

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">MongoGridFS::storeUpload</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$metadata`</span> \] )

### Parameters

`name`  
The name of the uploaded file(s) to store. This should correspond to the
file field's *name* attribute in the HTML form.

`metadata`  
Other metadata fields to include in the file document.

> **Note**:
>
> These fields may also overwrite those that would be created
> automatically by the driver, as described in the MongoDB core
> documentation for the
> <a href="https://docs.mongodb.com/manual/core/gridfs/#the-files-collection" class="link external">» files collection</a>.
> Some practical use cases for this behavior would be to specify a
> custom *chunkSize* or *\_id* for the file.

> **Note**:
>
> The *filename* field will be populated with the client's filename
> (e.g. *$\_FILES\['foo'\]\['name'\]*).

### Return Values

Returns the *\_id* of the saved file document. This will be a generated
<span class="classname">MongoId</span> unless an *\_id* was explicitly
specified in the `metadata` parameter.

> **Note**:
>
> If
> <a href="/features/file-upload/multiple.html" class="link">multiple files are uploaded using the same field name</a>,
> this method will not return anything; however, the files themselves
> will still be processed.

### Errors/Exceptions

Throws <span class="classname">MongoGridFSException</span> if there is
an error reading the uploaded file(s) or inserting into the *chunks* or
*files* collections.

### Changelog

| Version          | Description                                                                                                                       |
|------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.2.5 | Changed second parameter to an array of metadata. Pre-1.2.5, the second parameter was an optional string overriding the filename. |

### Examples

**Example \#1 <span class="function">MongoGridFS::storeUpload</span>
HTML form example**

Suppose you have the following HTML form:

``` html
<form method="POST" enctype="multipart/form-data">
    <label for="username">Username:</label>
    <input type="text" name="username" id="username" />

    <label for="pic">Please upload a profile picture:</label>
    <input type="file" name="pic" id="pic" />

    <input type="submit" />
</form>
```

If you wanted to store the uploaded image in MongoDB, you could do the
following in the script handling the form submission:

``` php
<?php
$m = new MongoClient();
$gridfs = $m->selectDB('test')->getGridFS();

$gridfs->storeUpload('pic', array('username' => $_POST['username']));
?>
```

### See Also

-   <span class="function">MongoGridFS::put</span>
-   <span class="function">MongoGridFS::storeBytes</span>
-   <span class="function">MongoGridFS::storeFile</span>
-   MongoDB core docs on
    <a href="https://docs.mongodb.com/manual/core/gridfs/" class="link external">» GridFS</a>

Introduction
------------

A database file object.

Class synopsis
--------------

**MongoGridFSFile**

<span class="ooclass"> class **MongoGridFSFile** </span> {

/\* Fields \*/

<span class="modifier">public</span> <span class="type">array</span>
`$file` <span class="initializer"> = **`NULL`**</span> ;

<span class="modifier">protected</span> <span
class="type">MongoGridFS</span> `$gridfs` <span class="initializer"> =
**`NULL`**</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">MongoGridfsFile::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoGridFS</span>
`$gridfs`</span> , <span class="methodparam"><span
class="type">array</span> `$file`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getBytes</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getFilename</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">resource</span>
<span class="methodname">getResource</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">write</span> (\[ <span class="methodparam"><span
class="type">string</span> `$filename`<span class="initializer"> =
**`NULL`**</span></span> \] )

}

MongoGridfsFile::\_\_construct
==============================

Create a new GridFS file

### Description

<span class="modifier">public</span> <span
class="methodname">MongoGridfsFile::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoGridFS</span>
`$gridfs`</span> , <span class="methodparam"><span
class="type">array</span> `$file`</span> )

### Parameters

`gridfs`  
The parent MongoGridFS instance.

`file`  
A file from the database.

### Return Values

Returns a new MongoGridFSFile.

MongoGridFSFile::getBytes
=========================

Returns this file's contents as a string of bytes

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoGridFSFile::getBytes</span> ( <span
class="methodparam">void</span> )

Warning: this will load the file into memory. If the file is bigger than
your memory, this will cause problems!

### Parameters

This function has no parameters.

### Return Values

Returns a string of the bytes in the file.

### Examples

**Example \#1 <span class="methodname">MongoGridFSFile::getBytes</span>
example**

``` php
<?php

$images = $db->my_db->getGridFS('images');

$image = $images->findOne('jwage.png');

header('Content-type: image/png;');
echo $image->getBytes();
?>
```

MongoGridFSFile::getFilename
============================

Returns this file's filename

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoGridFSFile::getFilename</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the filename.

MongoGridFSFile::getResource
============================

Returns a resource that can be used to read the stored file

### Description

<span class="modifier">public</span> <span class="type">resource</span>
<span class="methodname">MongoGridFSFile::getResource</span> ( <span
class="methodparam">void</span> )

This method returns a stream resource that can be used with all file
functions in PHP that deal with reading files. The contents of the file
are pulled out of MongoDB on the fly, so that the whole file does not
have to be loaded into memory first.

At most two GridFSFile chunks will be loaded in memory.

### Parameters

This function has no parameters.

### Return Values

Returns a resource that can be used to read the file with

### Examples

**Example \#1 <span
class="methodname">MongoGridFSFile::getResource</span> example**

``` php
<?php
$m = new Mongo;
$images = $m->my_db->getGridFS('images');

$image = $images->findOne('mongo.png');

header('Content-type: image/png;');
$stream = $image->getResource();

while (!feof($stream)) {
    echo fread($stream, 8192);
}
?>
```

MongoGridFSFile::getSize
========================

Returns this file's size

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoGridFSFile::getSize</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns this file's size

MongoGridFSFile::write
======================

Writes this file to the filesystem

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">MongoGridFSFile::write</span> (\[ <span
class="methodparam"><span class="type">string</span> `$filename`<span
class="initializer"> = **`NULL`**</span></span> \] )

### Parameters

`filename`  
The location to which to write the file. If none is given, the stored
filename will be used.

### Return Values

Returns the number of bytes written.

### Examples

**Example \#1 <span class="methodname">MongoGridFSFile::write</span>
example**

``` php
<?php

$images = $db->my_db->getGridFS('images');

$image = $images->findOne('jwage.png');
$image->write('/path/to/write/jwage.png');
?>
```

Introduction
------------

Cursor for database file results.

Class synopsis
--------------

**MongoGridFSCursor**

<span class="ooclass"> <span class="modifier">extends</span> class
**MongoCursor** </span> {

/\* Fields \*/

<span class="modifier">protected</span> <span
class="type">MongoGridFS</span> `$gridfs` <span class="initializer"> =
**`NULL`**</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoGridFS</span>
`$gridfs`</span> , <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span> `$ns`</span> ,
<span class="methodparam"><span class="type">array</span>
`$query`</span> , <span class="methodparam"><span
class="type">array</span> `$fields`</span> )

<span class="modifier">public</span> <span
class="type">MongoGridFSFile</span> <span
class="methodname">current</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoGridFSFile</span> <span
class="methodname">getNext</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">key</span> ( <span
class="methodparam">void</span> )

}

MongoGridFSCursor::\_\_construct
================================

Create a new cursor

### Description

<span class="modifier">public</span> <span
class="methodname">MongoGridFSCursor::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoGridFS</span>
`$gridfs`</span> , <span class="methodparam"><span
class="type">resource</span> `$connection`</span> , <span
class="methodparam"><span class="type">string</span> `$ns`</span> ,
<span class="methodparam"><span class="type">array</span>
`$query`</span> , <span class="methodparam"><span
class="type">array</span> `$fields`</span> )

### Parameters

`gridfs`  
Related GridFS collection.

`connection`  
Database connection.

`ns`  
Full name of database and collection.

`query`  
Database query.

`fields`  
Fields to return.

### Return Values

Returns the new cursor.

MongoGridFSCursor::current
==========================

Returns the current file

### Description

<span class="modifier">public</span> <span
class="type">MongoGridFSFile</span> <span
class="methodname">MongoGridFSCursor::current</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The current file.

MongoGridFSCursor::getNext
==========================

Return the next file to which this cursor points, and advance the cursor

### Description

<span class="modifier">public</span> <span
class="type">MongoGridFSFile</span> <span
class="methodname">MongoGridFSCursor::getNext</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the next file.

MongoGridFSCursor::key
======================

Returns the current result's filename

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoGridFSCursor::key</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The current result's \_id as a string.

### Changelog

| Version          | Description                                                                                                              |
|------------------|--------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.3.0 | The document's *\_id* is returned as a string value, since the key should be unique. Pre-1.3.0, *filename* was returned. |

Batch Classes
=============

**Table of Contents**

-   [MongoWriteBatch](/book/mongo.html#MongoWriteBatch) — The
    MongoWriteBatch class
    -   [MongoWriteBatch::add](/book/mongo.html#MongoWriteBatch::add) —
        Adds a write operation to a batch
    -   [MongoWriteBatch::\_\_construct](/book/mongo.html#MongoWriteBatch::__construct)
        — Creates a new batch of write operations
    -   [MongoWriteBatch::execute](/book/mongo.html#MongoWriteBatch::execute)
        — Executes a batch of write operations
-   [MongoInsertBatch](/book/mongo.html#MongoInsertBatch) — The
    MongoInsertBatch class
    -   [MongoInsertBatch::\_\_construct](/book/mongo.html#MongoInsertBatch::__construct)
        — Description
-   [MongoUpdateBatch](/book/mongo.html#MongoUpdateBatch) — The
    MongoUpdateBatch class
    -   [MongoUpdateBatch::\_\_construct](/book/mongo.html#MongoUpdateBatch::__construct)
        — Description
-   [MongoDeleteBatch](/book/mongo.html#MongoDeleteBatch) — The
    MongoDeleteBatch class
    -   [MongoDeleteBatch::\_\_construct](/book/mongo.html#MongoDeleteBatch::__construct)
        — Description

Introduction
------------

MongoWriteBatch is the base class for the <span
class="classname">MongoInsertBatch</span>, <span
class="classname">MongoUpdateBatch</span> and <span
class="classname">MongoDeleteBatch</span> classes.

MongoWriteBatch allows you to "batch up" multiple operations (of same
type) and shipping them all to MongoDB at the same time. This can be
especially useful when operating on many documents at the same time to
reduce roundtrips.

Prior to version 1.5.0 of the driver it was possible to use <span
class="methodname">MongoCollection::batchInsert</span>, however, as of
1.5.0 that method is now discouraged.

Note: This class is only available when talking to MongoDB 2.6.0 (and
later) servers. It will throw <span
class="classname">MongoProtocolException</span> if attempting to use it
on older MongoDB servers.

Class synopsis
--------------

**MongoWriteBatch**

<span class="ooclass"> class **MongoWriteBatch** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`MongoWriteBatch::COMMAND_INSERT` <span class="initializer"> = 1</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`MongoWriteBatch::COMMAND_UPDATE` <span class="initializer"> = 2</span>
;

<span class="modifier">const</span> <span class="type">int</span>
`MongoWriteBatch::COMMAND_DELETE` <span class="initializer"> = 3</span>
;

/\* Methods \*/

<span class="modifier">protected</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoCollection</span>
`$collection`</span> \[, <span class="methodparam"><span
class="type">string</span> `$batch_type`</span> \[, <span
class="methodparam"><span class="type">array</span>
`$write_options`</span> \]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">array</span> `$item`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span class="methodname">execute</span>
( <span class="methodparam"><span class="type">array</span>
`$write_options`</span> )

}

MongoWriteBatch types
---------------------

**`MongoWriteBatch::COMMAND_INSERT`**  
Create an Insert Write Batch

**`MongoWriteBatch::COMMAND_UPDATE`**  
Create an Update Write Batch

**`MongoWriteBatch::COMMAND_DELETE`**  
Create an Delete Write Batch

Description
-----------

When executing a batch by calling <span
class="methodname">MongoWriteBatch::execute</span>, MongoWriteBatch will
send up to *maxWriteBatchSize* (defaults to 1000) documents or
*maxBsonObjectSize* (defaults to 16777216 bytes), whichever comes first.

> **Note**:
>
> Documents will never be partially transferred. When adding documents
> to the batch, that overflows the limit, a new batch will be created
> and the document put into the new batch.

Errors/Exceptions
-----------------

-   <span class="classname">Exception</span> on parameter parsing
    failures
-   <span class="classname">Exception</span> on argument validation
    errors (e.g. missing keys)
-   <span class="classname">MongoProtocolException</span> when talking
    to MongoDB server older then 2.6.0.
-   <span class="classname">MongoProtocolException</span> on socket
    errors.
-   <span class="classname">MongoWriteConcernException</span> when a
    write fails due to
    <a href="/book/mongo.html#Write%20Concerns" class="link">WriteConcerns</a>

Examples
--------

**Example \#1 <span class="classname">MongoWriteBatch</span> example**

Adding documents to a Insert batch and then execute it

``` php
<?php
$mc = new MongoClient("localhost");

$collection = $mc->selectCollection("test", "test");


$docs = array();
$docs[] = array("my" => "demo");
$docs[] = array("is" => "working");
$docs[] = array("pretty" => "well");

$batch = new MongoInsertBatch($collection);
foreach($docs as $document) {
    $batch->add($document);
}
$retval = $batch->execute(array("w" => 1));
var_dump($retval);
?>
```

The above example will output:

    array(2) {
      ["nInserted"]=>
      int(3)
      ["ok"]=>
      bool(true)
    }

MongoWriteBatch::add
====================

Adds a write operation to a batch

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoWriteBatch::add</span> ( <span
class="methodparam"><span class="type">array</span> `$item`</span> )

Adds a write operation to the batch.

If `$item` causes the batch to exceed the *maxWriteBatchSize* or
*maxBsonObjectSize* limits, the driver will internally split the batches
into multiple write commands upon calling <span
class="methodname">MongoWriteBatch::execute</span>.

### Parameters

`item`  
An array that describes a write operation. The structure of this value
depends on the batch's operation type.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Batch type</th>
<th>Argument expectation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><code>MongoWriteBatch::COMMAND_INSERT</code></strong></td>
<td><span class="simpara">The document to add.</span></td>
</tr>
<tr class="even">
<td><strong><code>MongoWriteBatch::COMMAND_UPDATE</code></strong></td>
<td><p>Raw update operation.</p>
<p>Required keys are <em>"q"</em> and <em>"u"</em>, which correspond to the <a href="/book/mongo.html#" class="link"><code class="parameter">$criteria</code></a> and <a href="/book/mongo.html#" class="link"><code class="parameter">$new_object</code></a> parameters of <span class="function">MongoCollection::update</span>, respectively.</p>
<p>Optional keys are <em>"multi"</em> and <em>"upsert"</em>, which correspond to the <a href="/book/mongo.html#" class="link"><em>"multiple"</em></a> and <a href="/book/mongo.html#" class="link"><em>"upsert"</em></a> options for <span class="function">MongoCollection::update</span>, respectively. If unspecified, both options default to <strong><code>FALSE</code></strong>.</p></td>
</tr>
<tr class="odd">
<td><strong><code>MongoWriteBatch::COMMAND_DELETE</code></strong></td>
<td><p>Raw delete operation.</p>
<p>Required keys are: <em>"q"</em> and <em>"limit"</em>, which correspond to the <a href="/book/mongo.html#" class="link"><code class="parameter">$criteria</code></a> parameter and <a href="/book/mongo.html#" class="link"><em>"justOne"</em></a> option of <span class="function">MongoCollection::remove</span>, respectively.</p>
<p>The <em>"limit"</em> option is an <span class="type">integer</span>; however, MongoDB only supports <em>0</em> (i.e. remove all matching documents) and <em>1</em> (i.e. remove at most one matching document) at this time.</p></td>
</tr>
</tbody>
</table>

### Return Values

Returns **`TRUE`** on success and throws an exception on failure.

### Errors/Exceptions

-   <span class="classname">Exception</span> on parameter parsing
    failures
-   <span class="classname">Exception</span> on argument validation
    errors (e.g. missing keys)

### Examples

**Example \#1 <span class="methodname">MongoWriteBatch::add</span>
example**

Batching up multiple insert operations

``` php
<?php
$mc = new MongoClient("localhost");
$collection = $mc->selectCollection("test", "test");


$docs = array();
$docs[] = array("my" => "demo");
$docs[] = array("is" => "working");
$docs[] = array("pretty" => "well");

$batch = new MongoInsertBatch($collection);
foreach($docs as $document) {
    $batch->add($document);
}
$batch->execute(array("w" => 1));
?>
```

**Example \#2 <span class="methodname">MongoWriteBatch::add</span>
example**

Batching up multiple update operations

``` php
<?php
$mc = new MongoClient("localhost");
$collection = $mc->selectCollection("test", "test");


$item1 = array(
    "q" => array("my" => "demo"),
    "u" => array('$set' => array("try" => 1)),
    "multi"  => false, /* default value */
    "upsert" => false, /* default value */
);
$item2 = array(
    "q" => array("is" => "working"),
    "u" => array('$set' => array("try" => 2)),
    "multi" => true,
);
$item3 = array(
    "q" => array("created" => "new-document"),
    "u" => array('$set' => array("try" => 3)),
    "upsert" => true,
);

$batch = new MongoUpdateBatch($collection);
$batch->add($item1);
$batch->add($item2);
$batch->add($item3);
$batch->execute(array("w" => 1));

?>
```

**Example \#3 <span class="methodname">MongoWriteBatch::add</span>
example**

Batching up multiple delete operations

``` php
<?php
$mc = new MongoClient("localhost");
$collection = $mc->selectCollection("test", "test");


$item1 = array(
    "q" => array("my" => "demo"),
    "limit" => 1,
);
$item2 = array(
    "q" => array("try" => 3),
    "limit" => 1,
);


$batch = new MongoDeleteBatch($collection);
$batch->add($item1);
$batch->add($item2);
$batch->execute(array("w" => 1));
?>
```

MongoWriteBatch::\_\_construct
==============================

Creates a new batch of write operations

### Description

<span class="modifier">protected</span> <span
class="methodname">MongoWriteBatch::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoCollection</span>
`$collection`</span> \[, <span class="methodparam"><span
class="type">string</span> `$batch_type`</span> \[, <span
class="methodparam"><span class="type">array</span>
`$write_options`</span> \]\] )

Constructs a new MongoWriteBatch.

> **Note**:
>
> This is a protected constructor. Please use one of the classes
> inheriting <span class="classname">MongoWriteBatch</span>.

### Parameters

`collection`  
The <span class="classname">MongoCollection</span> to execute the batch
on. Its
<a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
will be copied and used as the default write concern if none is given as
`$write_options` or during <span
class="methodname">MongoWriteBatch::execute</span>.

`batch_type`  
One of:

-   *0* - make an MongoWriteBatch::COMMAND\_INSERT batch
-   *1* - make an MongoWriteBatch::COMMAND\_UPDATE batch
-   *2* - make a MongoWriteBatch::COMMAND\_DELETE batch

`write_options`  
An array of Write Options.

| key             | value meaning                                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| w (int\|string) | <a href="/book/mongo.html#Write%20Concerns" class="link">Write concern</a> value                                                                                                                                                                                             |
| wtimeout (int)  | <a href="/book/mongo.html#Write%20Concerns" class="link">Maximum time to wait for replication</a>                                                                                                                                                                            |
| ordered         | Determines if MongoDB must apply this batch in order. Ordered writes execute serially (i.e. one at a time) and execution will stop after the first error. Unordered writes may execute in parallel and execution will not stop after the first error. Defaults to **`TRUE`** |
| j (bool)        | Wait for journaling on the primary. This value is discouraged, use WriteConcern instead                                                                                                                                                                                      |
| fsync (bool)    | Wait for fsync on the primary. This value is discouraged, use WriteConcern instead                                                                                                                                                                                           |

### Return Values

A new MongoWriteBatch of type `batch_type`.

### See Also

-   <span class="classname">MongoInsertBatch</span>
-   <span class="classname">MongoUpdateBatch</span>
-   <span class="classname">MongoDeleteBatch</span>

MongoWriteBatch::execute
========================

Executes a batch of write operations

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">MongoWriteBatch::execute</span> ( <span
class="methodparam"><span class="type">array</span>
`$write_options`</span> )

Executes the batch of write operations.

### Parameters

`write_options`  
See
<a href="/book/mongo.html#" class="link">MongoWriteBatch::__construct</a>.

### Return Values

Returns an array containing statistical information for the full batch.
If the batch had to be split into multiple batches, the return value
will aggregate the values from individual batches and return only the
totals.

If the batch was empty, an array containing only the 'ok' field is
returned (as **`TRUE`**) although nothing will be shipped over the wire
(NOOP).

| Array key | Value meaning                                    | Returned for batch type                |
|-----------|--------------------------------------------------|----------------------------------------|
| nInserted | Number of inserted documents                     | MongoWriteBatch::COMMAND\_INSERT batch |
| nMatched  | Number of documents matching the query criteria  | MongoWriteBatch::COMMAND\_UPDATE batch |
| nModified | Number of documents actually needed to be modied | MongoWriteBatch::COMMAND\_UPDATE batch |
| nUpserted | Number of upserted documents                     | MongoWriteBatch::COMMAND\_UPDATE batch |
| nRemoved  | Number of documents removed                      | MongoWriteBatch::COMMAND\_DELETE batch |
| ok        | Command success indicator                        | All                                    |

### Errors/Exceptions

A <span class="classname">MongoWriteConcernException</span> exception is
thrown on failure.

### Examples

**Example \#1 <span class="methodname">MongoWriteBatch::add</span>
example**

Batching up multiple insert operations

``` php
<?php
$mc = new MongoClient("localhost");
$collection = $mc->selectCollection("test", "test");


$docs = array();
$docs[] = array("my" => "demo");
$docs[] = array("is" => "working");
$docs[] = array("pretty" => "well");

$batch = new MongoInsertBatch($collection);
foreach($docs as $document) {
    $batch->add($document);
}
$retval = $batch->execute(array("w" => 1));
var_dump($retval);
?>
```

The above example will output:

    array(2) {
      ["nInserted"]=>
      int(3)
      ["ok"]=>
      bool(true)
    }

**Example \#2 <span class="methodname">MongoWriteBatch::add</span>
example**

Batching up multiple update operations

``` php
<?php
$mc = new MongoClient("localhost");
$collection = $mc->selectCollection("test", "test");


$item1 = array(
    "q" => array("my" => "demo"),
    "u" => array('$set' => array("try" => 1)),
    "multi"  => false, /* default value */
    "upsert" => false, /* default value */
);
$item2 = array(
    "q" => array("is" => "working"),
    "u" => array('$set' => array("try" => 2)),
    "multi" => true,
);
$item3 = array(
    "q" => array("created" => "new-document"),
    "u" => array('$set' => array("try" => 3)),
    "upsert" => true,
);

$batch = new MongoUpdateBatch($collection);
$batch->add($item1);
$batch->add($item2);
$batch->add($item3);
$retval = $batch->execute(array("w" => 1));
var_dump($retval);

?>
```

The above example will output:

    array(4) {
      ["nMatched"]=>
      int(18)
      ["nModified"]=>
      int(2)
      ["nUpserted"]=>
      int(0)
      ["ok"]=>
      bool(true)
    }

**Example \#3 <span class="methodname">MongoWriteBatch::add</span>
example**

Batching up multiple delete operations

``` php
<?php
$mc = new MongoClient("localhost");
$collection = $mc->selectCollection("test", "test");


$item1 = array(
    "q" => array("my" => "demo"),
    "limit" => 1,
);
$item2 = array(
    "q" => array("try" => 3),
    "limit" => 1,
);


$batch = new MongoDeleteBatch($collection);
$batch->add($item1);
$batch->add($item2);
$retval = $batch->execute(array("w" => 1));
var_dump($retval);
?>
```

The above example will output:

    array(2) {
      ["nRemoved"]=>
      int(1)
      ["ok"]=>
      bool(true)
    }

Introduction
------------

Constructs a batch of INSERT operations. See <span
class="classname">MongoWriteBatch</span>.

Class synopsis
--------------

**MongoInsertBatch**

<span class="ooclass"> class **MongoInsertBatch** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**MongoWriteBatch** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoCollection</span>
`$collection`</span> \[, <span class="methodparam"><span
class="type">array</span> `$write_options`</span> \] )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoWriteBatch::add</span> ( <span
class="methodparam"><span class="type">array</span> `$item`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">MongoWriteBatch::execute</span> ( <span
class="methodparam"><span class="type">array</span>
`$write_options`</span> )

}

MongoInsertBatch::\_\_construct
===============================

Description

### Description

<span class="modifier">public</span> <span
class="methodname">MongoInsertBatch::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoCollection</span>
`$collection`</span> \[, <span class="methodparam"><span
class="type">array</span> `$write_options`</span> \] )

Constructs a batch of INSERT operations. See <span
class="classname">MongoWriteBatch</span>.

### Parameters

`collection`  
The <span class="classname">MongoCollection</span> to execute the batch
on. Its
<a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
will be copied and used as the default write concern if none is given as
`$write_options` or during <span
class="methodname">MongoWriteBatch::execute</span>.

`write_options`  
An array of Write Options.

| key             | value meaning                                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| w (int\|string) | <a href="/book/mongo.html#Write%20Concerns" class="link">Write concern</a> value                                                                                                                                                                                             |
| wtimeout (int)  | <a href="/book/mongo.html#Write%20Concerns" class="link">Maximum time to wait for replication</a>                                                                                                                                                                            |
| ordered         | Determines if MongoDB must apply this batch in order. Ordered writes execute serially (i.e. one at a time) and execution will stop after the first error. Unordered writes may execute in parallel and execution will not stop after the first error. Defaults to **`TRUE`** |
| j (bool)        | Wait for journaling on the primary. This value is discouraged, use WriteConcern instead                                                                                                                                                                                      |
| fsync (bool)    | Wait for fsync on the primary. This value is discouraged, use WriteConcern instead                                                                                                                                                                                           |

### Return Values

A new MongoInsertBatch.

Introduction
------------

Constructs a batch of UPDATE operations. See <span
class="classname">MongoWriteBatch</span>.

Class synopsis
--------------

**MongoUpdateBatch**

<span class="ooclass"> class **MongoUpdateBatch** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**MongoWriteBatch** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoCollection</span>
`$collection`</span> \[, <span class="methodparam"><span
class="type">array</span> `$write_options`</span> \] )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoWriteBatch::add</span> ( <span
class="methodparam"><span class="type">array</span> `$item`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">MongoWriteBatch::execute</span> ( <span
class="methodparam"><span class="type">array</span>
`$write_options`</span> )

}

MongoUpdateBatch::\_\_construct
===============================

Description

### Description

<span class="modifier">public</span> <span
class="methodname">MongoUpdateBatch::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoCollection</span>
`$collection`</span> \[, <span class="methodparam"><span
class="type">array</span> `$write_options`</span> \] )

Constructs a batch of UPDATE operations. See <span
class="classname">MongoWriteBatch</span>.

### Parameters

`collection`  
The <span class="classname">MongoCollection</span> to execute the batch
on. Its
<a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
will be copied and used as the default write concern if none is given as
`$write_options` or during <span
class="methodname">MongoWriteBatch::execute</span>.

`write_options`  
An array of Write Options.

| key             | value meaning                                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| w (int\|string) | <a href="/book/mongo.html#Write%20Concerns" class="link">Write concern</a> value                                                                                                                                                                                             |
| wtimeout (int)  | <a href="/book/mongo.html#Write%20Concerns" class="link">Maximum time to wait for replication</a>                                                                                                                                                                            |
| ordered         | Determines if MongoDB must apply this batch in order. Ordered writes execute serially (i.e. one at a time) and execution will stop after the first error. Unordered writes may execute in parallel and execution will not stop after the first error. Defaults to **`TRUE`** |
| j (bool)        | Wait for journaling on the primary. This value is discouraged, use WriteConcern instead                                                                                                                                                                                      |
| fsync (bool)    | Wait for fsync on the primary. This value is discouraged, use WriteConcern instead                                                                                                                                                                                           |

### Return Values

A new MongoUpdateBatch.

Introduction
------------

Constructs a batch of DELETE operations. See <span
class="classname">MongoWriteBatch</span>.

Class synopsis
--------------

**MongoDeleteBatch**

<span class="ooclass"> class **MongoDeleteBatch** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**MongoWriteBatch** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoCollection</span>
`$collection`</span> \[, <span class="methodparam"><span
class="type">array</span> `$write_options`</span> \] )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoWriteBatch::add</span> ( <span
class="methodparam"><span class="type">array</span> `$item`</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">MongoWriteBatch::execute</span> ( <span
class="methodparam"><span class="type">array</span>
`$write_options`</span> )

}

MongoDeleteBatch::\_\_construct
===============================

Description

### Description

<span class="modifier">public</span> <span
class="methodname">MongoDeleteBatch::\_\_construct</span> ( <span
class="methodparam"><span class="type">MongoCollection</span>
`$collection`</span> \[, <span class="methodparam"><span
class="type">array</span> `$write_options`</span> \] )

Constructs a batch of DELETE operations. See <span
class="classname">MongoWriteBatch</span>.

### Parameters

`collection`  
The <span class="classname">MongoCollection</span> to execute the batch
on. Its
<a href="/book/mongo.html#Write%20Concerns" class="link">write concern</a>
will be copied and used as the default write concern if none is given as
`$write_options` or during <span
class="methodname">MongoWriteBatch::execute</span>.

`write_options`  
An array of Write Options.

| key             | value meaning                                                                                                                                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| w (int\|string) | <a href="/book/mongo.html#Write%20Concerns" class="link">Write concern</a> value                                                                                                                                                                                             |
| wtimeout (int)  | <a href="/book/mongo.html#Write%20Concerns" class="link">Maximum time to wait for replication</a>                                                                                                                                                                            |
| ordered         | Determines if MongoDB must apply this batch in order. Ordered writes execute serially (i.e. one at a time) and execution will stop after the first error. Unordered writes may execute in parallel and execution will not stop after the first error. Defaults to **`TRUE`** |
| j (bool)        | Wait for journaling on the primary. This value is discouraged, use WriteConcern instead                                                                                                                                                                                      |
| fsync (bool)    | Wait for fsync on the primary. This value is discouraged, use WriteConcern instead                                                                                                                                                                                           |

### Return Values

A new MongoDeleteBatch.

Miscellaneous
=============

**Table of Contents**

-   [MongoLog](/book/mongo.html#MongoLog) — The MongoLog class
    -   [MongoLog::getCallback](/book/mongo.html#MongoLog::getCallback)
        — Gets the previously set callback function
    -   [MongoLog::getLevel](/book/mongo.html#MongoLog::getLevel) — Gets
        the level(s) currently being logged
    -   [MongoLog::getModule](/book/mongo.html#MongoLog::getModule) —
        Gets the module(s) currently being logged
    -   [MongoLog::setCallback](/book/mongo.html#MongoLog::setCallback)
        — Sets a callback function to be invoked for events
    -   [MongoLog::setLevel](/book/mongo.html#MongoLog::setLevel) — Sets
        the level(s) to be logged
    -   [MongoLog::setModule](/book/mongo.html#MongoLog::setModule) —
        Sets the module(s) to be logged
-   [MongoPool](/book/mongo.html#MongoPool) — The MongoPool class
    -   [MongoPool::getSize](/book/mongo.html#MongoPool::getSize) — Get
        pool size for connection pools
    -   [MongoPool::info](/book/mongo.html#MongoPool::info) — Returns
        information about all connection pools
    -   [MongoPool::setSize](/book/mongo.html#MongoPool::setSize) — Set
        the size for future connection pools
-   [Mongo](/book/mongo.html#Mongo) — The Mongo class \[deprecated\]
    -   [Mongo::connectUtil](/book/mongo.html#Mongo::connectUtil) —
        Connects with a database server
    -   [Mongo::\_\_construct](/book/mongo.html#Mongo::__construct) —
        The \_\_construct purpose
    -   [Mongo::getPoolSize](/book/mongo.html#Mongo::getPoolSize) — Get
        pool size for connection pools
    -   [Mongo::getSlave](/book/mongo.html#Mongo::getSlave) — Returns
        the address being used by this for slaveOkay reads
    -   [Mongo::getSlaveOkay](/book/mongo.html#Mongo::getSlaveOkay) —
        Get slaveOkay setting for this connection
    -   [Mongo::poolDebug](/book/mongo.html#Mongo::poolDebug) — Returns
        information about all connection pools
    -   [Mongo::setPoolSize](/book/mongo.html#Mongo::setPoolSize) — Set
        the size for future connection pools
    -   [Mongo::setSlaveOkay](/book/mongo.html#Mongo::setSlaveOkay) —
        Change slaveOkay setting for this connection
    -   [Mongo::switchSlave](/book/mongo.html#Mongo::switchSlave) —
        Choose a new secondary for slaveOkay reads

Introduction
------------

Logging can be used to get detailed information about what the driver is
doing. Logging is disabled by default, but this class allows you to
activate specific levels of logging for various parts of the driver.
Some examples:

``` php
<?php

// print every log message possible
MongoLog::setLevel(MongoLog::ALL); // all log levels
MongoLog::setModule(MongoLog::ALL); // all parts of the driver

// print significant events about replica set failover
MongoLog::setLevel(MongoLog::INFO);
MongoLog::setModule(MongoLog::RS);

// print info- and diagnostic-level events for replica sets and connections
MongoLog::setLevel(MongoLog::INFO|MongoLog::FINE);
MongoLog::setModule(MongoLog::RS|MongoLog::CON);

?>
```

> **Note**:
>
> By default, MongoLog emits all log messages as PHP notices. Depending
> on the SAPI you use, messages may be sent to *stderr* (for CLI) or the
> web server's error log. If, after configuring MongoLog, log messages
> are not appearing as expected, ensure that the **`E_NOTICE`** bit is
> included in
> <a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
> and that
> <a href="/errorfunc/setup.html#" class="link">display_errors</a> is
> on.

Class synopsis
--------------

**MongoLog**

<span class="ooclass"> class **MongoLog** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::NONE` <span class="initializer"> = 0</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::ALL` <span class="initializer"> = 31</span> ;

level constants {

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::WARNING` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::INFO` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::FINE` <span class="initializer"> = 4</span> ;

module constants {

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::RS` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::POOL` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::CON` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::IO` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::SERVER` <span class="initializer"> = 8</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`MongoLog::PARSE` <span class="initializer"> = 16</span> ;

/\* Fields \*/

<span class="modifier">private</span> <span
class="modifier">static</span> <span class="type">int</span> `$callback`
;

<span class="modifier">private</span> <span
class="modifier">static</span> <span class="type">int</span> `$level` ;

<span class="modifier">private</span> <span
class="modifier">static</span> <span class="type">int</span> `$module` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">callable</span> <span
class="methodname">getCallback</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">getLevel</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">getModule</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">setCallback</span> ( <span class="methodparam"><span
class="type">callable</span> `$log_function`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">setLevel</span> ( <span class="methodparam"><span
class="type">int</span> `$level`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">setModule</span> ( <span class="methodparam"><span
class="type">int</span> `$module`</span> )

}

Predefined Constants
--------------------

MongoLog Constants
------------------

These constants can be used by both <span
class="function">MongoLog::setLevel</span> and <span
class="function">MongoLog::setModule</span>.

**`MongoLog::NONE`**  
<span class="simpara"> Log nothing. </span>

**`MongoLog::ALL`**  
<span class="simpara"> Log everything. </span>

MongoLog Level Constants
------------------------

These constants can be used by <span
class="function">MongoLog::setLevel</span>.

**`MongoLog::WARNING`**  
<span class="simpara"> Log events that are somewhat exceptional, but not
quite worthy of an actual exception (e.g. recoverable connection
errors). </span>

**`MongoLog::INFO`**  
<span class="simpara"> Log events that may be of interest to
administrators, but are not particularly noteworthy (e.g. option
parsing, authentication steps). </span>

**`MongoLog::FINE`**  
<span class="simpara"> Log most events that the driver performs (e.g.
server selection, socket communication). Depending on the module being
logged, this can be extremely noisy and is primarily useful for
debugging. </span>

MongoLog Module Constants
-------------------------

These constants can be used by <span
class="function">MongoLog::setModule</span>.

**`MongoLog::CON`**  
<span class="simpara"> Log connection activity. Creating new
connections, authentication, pinging, timeouts, etc. </span>

**`MongoLog::IO`**  
<span class="simpara"> Log traffic to/from the database. Unless your
program is trivial, this will create an enormous number of log messages.
</span>

**`MongoLog::PARSE`**  
<span class="simpara"> Log parsing of the connection string and options
when constructing <span class="classname">MongoClient</span>. </span>

**`MongoLog::POOL`**  
<span class="simpara"> Previously used to log connection pool activity.
This option is now a deprecated alias of **`MongoLog::RS`**. </span>

**`MongoLog::RS`**  
<span class="simpara"> Log replica set activity. Failovers, read
preference selection, etc. </span>

**`MongoLog::SERVER`**  
<span class="simpara"> Previously used to log server status changes.
This option is deprecated in favor of **`MongoLog::RS`**. </span>

Changelog
---------

| Version          | Description                                                                               |
|------------------|-------------------------------------------------------------------------------------------|
| PECL mongo 1.3.0 | Added **`MongoLog::CON`** and deprecated **`MongoLog::POOL`** and **`MongoLog::SERVER`**. |

MongoLog::getCallback
=====================

Gets the previously set callback function

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">callable</span> <span
class="methodname">MongoLog::getCallback</span> ( <span
class="methodparam">void</span> )

Retrieves the callback function.

### Parameters

This function has no parameters.

### Return Values

Returns the callback function, or **`FALSE`** if not set yet.

### Notes

**Caution**

This function is only available with PHP 5.3.0 and later.

MongoLog::getLevel
==================

Gets the level(s) currently being logged

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">MongoLog::getLevel</span> ( <span
class="methodparam">void</span> )

This function can be used to see which log levels are currently enabled.
The returned integer may be compared with the
<a href="/book/mongo.html#MongoLog%20Level%20Constants" class="link">MongoLog level constants</a>
using bitwise operators to check for specific log levels.

``` php
<?php

if (MongoLog::getLevel() & MongoLog::FINE) {
    echo "lots of logs\n";
}

if (MongoLog::getLevel() ^ MongoLog::NONE) {
    echo "logging, at least a little\n";
}

if (MongoLog::getLevel() == MongoLog::ALL) {
    echo "logging at the highest levels\n";
}

?>
```

### Parameters

This function has no parameters.

### Return Values

Returns the level(s) currently being logged.

MongoLog::getModule
===================

Gets the module(s) currently being logged

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">MongoLog::getModule</span> ( <span
class="methodparam">void</span> )

This function can be used to see which driver modules are currently
being logged. The returned integer may be compared with the
<a href="/book/mongo.html#MongoLog%20Module%20Constants" class="link">MongoLog module constants</a>
using bitwise operators to check if specific modules are being logged.

``` php
<?php

if (MongoLog::getModule() & MongoLog::RS) {
    echo "logging replica sets\n";
}

if (MongoLog::getModule() ^ MongoLog::NONE) {
    echo "logging something\n";
}

if ((MongoLog::getModule() & MongoLog::IO) == 0) {
    echo "not logging io\n";
}

?>
```

### Parameters

This function has no parameters.

### Return Values

Returns the module(s) currently being logged.

MongoLog::setCallback
=====================

Sets a callback function to be invoked for events

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">MongoLog::setCallback</span> ( <span
class="methodparam"><span class="type">callable</span>
`$log_function`</span> )

This function will set a callback function to be invoked for events in
lieu of emitting of PHP notice.

### Parameters

`log_function`  
The callback function to be invoked on events. It should have the
following prototype:

<span class="methodname"><span
class="replaceable">log\_function</span></span> ( <span
class="methodparam"><span class="type">int</span> `$module`</span> ,
<span class="methodparam"><span class="type">int</span> `$level`</span>
, <span class="methodparam"><span class="type">string</span>
`$message`</span> )

`module`  
<span class="simpara"> One of the
<a href="/book/mongo.html#MongoLog%20Module%20Constants" class="link">MongoLog module constants</a>.
</span>

`level`  
<span class="simpara"> One of the
<a href="/book/mongo.html#MongoLog%20Level%20Constants" class="link">MongoLog level constants</a>.
</span>

`message`  
<span class="simpara"> The log message itself. </span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="methodname">MongoLog::setCallback</span>
example**

``` php
<?php

function module2string($module)
{
    switch ($module) {
        case MongoLog::RS: return "REPLSET";
        case MongoLog::CON: return "CON";
        case MongoLog::IO: return "IO";
        case MongoLog::SERVER: return "SERVER";
        case MongoLog::PARSE: return "PARSE";
        default: return "UNKNOWN";
    }
}

function level2string($level)
{
    switch ($level) {
        case MongoLog::WARNING: return "WARN";
        case MongoLog::INFO: return "INFO";
        case MongoLog::FINE: return "FINE";
        default: return "UNKNOWN";
    }
}

function callback($module, $level, $message)
{
    echo date("Y-m-d H:i:s - ");
    printf("%s (%s): %s\n", module2string($module), level2string($level), $message);
}

MongoLog::setLevel(MongoLog::ALL);
MongoLog::setModule(MongoLog::ALL);

// We specify the function name here, but any callable (e.g. anonymous function) will work
MongoLog::setCallback("callback");

new MongoClient();
?>
```

The above example will output something similar to:

    2013-07-09 09:41:42 - PARSE (INFO): Parsing localhost:27017
    2013-07-09 09:41:42 - PARSE (INFO): - Found node: localhost:27017
    2013-07-09 09:41:42 - PARSE (INFO): - Connection type: STANDALONE
    2013-07-09 09:41:42 - CON (INFO): mongo_get_read_write_connection: finding a STANDALONE connection
    2013-07-09 09:41:42 - CON (INFO): connection_create: creating new connection for localhost:27017
    2013-07-09 09:41:42 - CON (INFO): stream_connect: Not establishing SSL for localhost:27017
    2013-07-09 09:41:42 - CON (INFO): get_server_flags: start
    2013-07-09 09:41:42 - CON (FINE): send_packet: read from header: 36
    2013-07-09 09:41:42 - CON (FINE): send_packet: data_size: 95
    2013-07-09 09:41:42 - CON (FINE): get_server_flags: setting maxBsonObjectSize to 16777216
    2013-07-09 09:41:42 - CON (FINE): get_server_flags: setting maxMessageSizeBytes to 48000000
    2013-07-09 09:41:42 - CON (INFO): is_ping: pinging localhost:27017;-;.;1543
    2013-07-09 09:41:42 - CON (FINE): send_packet: read from header: 36
    2013-07-09 09:41:42 - CON (FINE): send_packet: data_size: 17
    2013-07-09 09:41:42 - CON (INFO): is_ping: last pinged at 1373359302; time: 0ms
    2013-07-09 09:41:42 - REPLSET (FINE): finding candidate servers
    2013-07-09 09:41:42 - REPLSET (FINE): - all servers
    2013-07-09 09:41:42 - REPLSET (FINE): filter_connections: adding connections:
    2013-07-09 09:41:42 - REPLSET (FINE): - connection: type: STANDALONE, socket: 42, ping: 0, hash: localhost:27017;-;.;1543
    2013-07-09 09:41:42 - REPLSET (FINE): filter_connections: done
    2013-07-09 09:41:42 - REPLSET (FINE): limiting by seeded/discovered servers
    2013-07-09 09:41:42 - REPLSET (FINE): - connection: type: STANDALONE, socket: 42, ping: 0, hash: localhost:27017;-;.;1543
    2013-07-09 09:41:42 - REPLSET (FINE): limiting by seeded/discovered servers: done
    2013-07-09 09:41:42 - REPLSET (FINE): limiting by credentials
    2013-07-09 09:41:42 - REPLSET (FINE): - connection: type: STANDALONE, socket: 42, ping: 0, hash: localhost:27017;-;.;1543
    2013-07-09 09:41:42 - REPLSET (FINE): limiting by credentials: done
    2013-07-09 09:41:42 - REPLSET (FINE): sorting servers by priority and ping time
    2013-07-09 09:41:42 - REPLSET (FINE): - connection: type: STANDALONE, socket: 42, ping: 0, hash: localhost:27017;-;.;1543
    2013-07-09 09:41:42 - REPLSET (FINE): sorting servers: done
    2013-07-09 09:41:42 - REPLSET (FINE): selecting near servers
    2013-07-09 09:41:42 - REPLSET (FINE): selecting near servers: nearest is 0ms
    2013-07-09 09:41:42 - REPLSET (FINE): - connection: type: STANDALONE, socket: 42, ping: 0, hash: localhost:27017;-;.;1543
    2013-07-09 09:41:42 - REPLSET (FINE): selecting near server: done
    2013-07-09 09:41:42 - REPLSET (INFO): pick server: random element 0
    2013-07-09 09:41:42 - REPLSET (INFO): - connection: type: STANDALONE, socket: 42, ping: 0, hash: localhost:27017;-;.;1543

### Notes

**Caution**

This function is only available with PHP 5.3.0 and later.

MongoLog::setLevel
==================

Sets the level(s) to be logged

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">MongoLog::setLevel</span> ( <span
class="methodparam"><span class="type">int</span> `$level`</span> )

This function can be used to control logging verbosity and the types of
activities that should be logged. The
<a href="/book/mongo.html#MongoLog%20Level%20Constants" class="link">MongoLog level constants</a>
may be used with bitwise operators to specify multiple levels.

``` php
<?php

// first, specify a logging module
MongoLog::setModule(MongoLog::CON);

// log messages for every level
MongoLog::setLevel(MongoLog::ALL);

// log warning and info messages only
MongoLog::setLevel(MongoLog::WARNING|MongoLog::INFO);

// log everything except fine activity
MongoLog::setLevel(MongoLog::ALL & (~MongoLog::FINE));

?>
```

Note that you must also call <span
class="function">MongoLog::setModule</span> to specify which modules(s)
of the driver should log.

### Parameters

`level`  
The level(s) you would like to log.

MongoLog::setModule
===================

Sets the module(s) to be logged

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">void</span> <span
class="methodname">MongoLog::setModule</span> ( <span
class="methodparam"><span class="type">int</span> `$module`</span> )

This function can be used to set which driver modules should be logged.
The
<a href="/book/mongo.html#MongoLog%20Module%20Constants" class="link">MongoLog module constants</a>
may be used with bitwise operators to specify multiple modules.

``` php
<?php

// first, specify a logging level
MongoLog::setLevel(MongoLog::ALL);

// log replica set activity
MongoLog::setModule(MongoLog::RS);

// log replica sets and connection activity
MongoLog::setModule(MongoLog::RS|MongoLog::CON);

// log everything except IO activity
MongoLog::setModule(MongoLog::ALL & (~MongoLog::IO));

?>
```

Note that you must also call <span
class="function">MongoLog::setLevel</span> to enable logging.

### Parameters

`module`  
The module(s) you would like to log.

Introduction
------------

**Warning**

The current (1.3.0+) releases of the driver no longer implements
pooling. This class and its methods are therefore deprecated and should
not be used.

Class synopsis
--------------

**MongoPool**

<span class="ooclass"> class **MongoPool** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">getSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">info</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setSize</span> ( <span class="methodparam"><span
class="type">int</span> `$size`</span> )

}

Changelog
---------

| Version           | Description                                                                                                                                                                                              |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| PECL mongo 1.3.0  | This functionality has been removed and no longer does anything other than emit deprecation warnings. This class is only kept around for backwards compatibility and will be removed in the near future. |
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used.                                                                                                                                                                      |

MongoPool::getSize
==================

Get pool size for connection pools

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">MongoPool::getSize</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Returns the current pool size.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### Examples

**Example \#1 Changing pool size**

This returns the default pool size, sets a new pool size, then prints
the new pool size and the pool debugging information. Note that changing
the pool size only affects new connection pools, it does not change old
ones.

``` php
<?php

$connection = new Mongo("host1");

// pool size is -1
echo "pool size is: ".MongoPool::getSize()."\n";

echo "setting pool size to 200\n";

MongoPool::setSize(200);

// pool size is 200
echo "pool size is: ".MongoPool::getSize()."\n";

$conn2 = new Mongo("host2");

// remaining for host1 is -2
// remaining for host2 is 199
var_dump(Mongo::poolDebug());

?>
```

### See Also

-   <span class="function">MongoPool::setSize</span>
-   <span class="function">MongoPool::info</span>
-   The
    <a href="/book/mongo.html#Connecting" class="link">connection</a>
    documentation.

MongoPool::info
===============

Returns information about all connection pools

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoPool::info</span> ( <span
class="methodparam">void</span> )

Returns an array of information about all connection pools.

### Parameters

This function has no parameters.

### Return Values

Each connection pool has an identifier, which starts with the host. For
each pool, this function shows the following fields:

`in use`  
The number of connections currently being used by <span
class="classname">Mongo</span> instances.

`in pool`  
The number of connections currently in the pool (not being used).

`remaining`  
The number of connections that could be created by this pool. For
example, suppose a pool had 5 connections remaining and 3 connections in
the pool. We could create 8 new instances of <span
class="classname">MongoClient</span> before we exhausted this pool
(assuming no instances of <span class="classname">MongoClient</span>
went out of scope, returning their connections to the pool).

A negative number means that this pool will spawn unlimited connections.

Before a pool is created, you can change the max number of connections
by calling <span class="function">Mongo::setPoolSize</span>. Once a pool
is showing up in the output of this function, its size cannot be
changed.

`total`  
The total number of connections allowed for this pool. This should be
greater than or equal to "in use" + "in pool" (or -1).

`timeout`  
The socket timeout for connections in this pool. This is how long
connections in this pool will attempt to connect to a server before
giving up.

`waiting`  
If you have capped the pool size, workers requesting connections from
the pool may block until other workers return their connections. This
field shows how many milliseconds workers have blocked for connections
to be released. If this number keeps increasing, you may want to use
<span class="function">MongoPool::setSize</span> to add more connections
to your pool.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

MongoPool::setSize
==================

Set the size for future connection pools

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">MongoPool::setSize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

Sets the max number of connections new pools will be able to create.

### Parameters

`size`  
The max number of connections future pools will be able to create.
Negative numbers mean that the pool will spawn an infinite number of
connections.

### Return Values

Returns the former value of pool size.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### Examples

**Example \#1 <span class="function">Mongo::setPoolSize</span> example**

If you set the pool size to *n* and then create *n* connections,
attempting to create an *n+1*st connection will throw a <span
class="classname">MongoConnectionException</span>.

``` php
<?php

// only allow one connection to a server
MongoPool::setSize(1);

// creates one connection to localhost:27017
$m1 = new Mongo();

// attempt to create a second connection to localhost:27017
// only one connection is allowed, so this will throw an exception
$m2 = new Mongo();

?>
```

The above example will output something similar to:

    Fatal error: Uncaught exception 'MongoConnectionException' with message 'no more connections in pool' in /path/to/php/script.php:10
    Stack trace:
    #0 /path/to/php/script.php(10): Mongo->__construct()
    #1 {main}
      thrown in /path/to/php/script.php on line 10

### See Also

-   <span class="function">MongoPool::getSize</span>
-   <span class="function">MongoPool::info</span>
-   The
    <a href="/book/mongo.html#Connecting" class="link">connection</a>
    documentation.

Introduction
------------

A connection between PHP and MongoDB.

This class extends <span class="classname">MongoClient</span> and
provides access to several deprecated methods.

For backwards compatibility, it also defaults the *"w"* option of its
constructor argument to *0*, which does not require write operations to
be acknowledged by the server. See <span
class="function">MongoClient::\_\_construct</span> for more information.

**Warning**

This class has been *DEPRECATED* as of version 1.3.0. Relying on this
feature is highly discouraged. Please use <span
class="classname">MongoClient</span> instead.

Class synopsis
--------------

**Mongo**

<span class="ooclass"> class **Mongo** </span> <span class="ooclass">
<span class="modifier">extends</span> **MongoClient** </span> {

/\* Methods \*/

<span class="modifier">protected</span> <span class="type">bool</span>
<span class="methodname">connectUtil</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">getPoolSize</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getSlave</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">getSlaveOkay</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">poolDebug</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setPoolSize</span> ( <span class="methodparam"><span
class="type">int</span> `$size`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setSlaveOkay</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$ok`<span
class="initializer"> = **`TRUE`**</span></span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">switchSlave</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::close</span> (\[ <span
class="methodparam"><span class="type">boolean\|string</span>
`$connection`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::connect</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::dropDB</span> ( <span
class="methodparam"><span class="type">mixed</span> `$db`</span> )

<span class="modifier">public</span> <span class="type">MongoDB</span>
<span class="methodname">MongoClient::\_\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$dbname`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">MongoClient::getConnections</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::getHosts</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::getReadPreference</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::getWriteConcern</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::killCursor</span> ( <span
class="methodparam"><span class="type">string</span>
`$server_hash`</span> , <span class="methodparam"><span
class="type">int\|MongoInt64</span> `$id`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoClient::listDBs</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">MongoCollection</span> <span
class="methodname">MongoClient::selectCollection</span> ( <span
class="methodparam"><span class="type">string</span> `$db`</span> ,
<span class="methodparam"><span class="type">string</span>
`$collection`</span> )

<span class="modifier">public</span> <span class="type">MongoDB</span>
<span class="methodname">MongoClient::selectDB</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::setReadPreference</span> ( <span
class="methodparam"><span class="type">string</span>
`$read_preference`</span> \[, <span class="methodparam"><span
class="type">array</span> `$tags`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">MongoClient::setWriteConcern</span> ( <span
class="methodparam"><span class="type">mixed</span> `$w`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$wtimeout`</span> \] )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoClient::\_\_toString</span> ( <span
class="methodparam">void</span> )

}

Mongo::connectUtil
==================

Connects with a database server

### Description

<span class="modifier">protected</span> <span class="type">bool</span>
<span class="methodname">Mongo::connectUtil</span> ( <span
class="methodparam">void</span> )

**Warning**

This is an internal function that you should *never* call yourself.

### Parameters

This function has no parameters.

### Return Values

If the connection was successful.

### Errors/Exceptions

Throws <span class="classname">MongoConnectionException</span> if it
fails to connect to the databases.

Mongo::\_\_construct
====================

The \_\_construct purpose

### Description

<span class="modifier">public</span> <span
class="methodname">Mongo::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$server`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$options`</span> \]\] )

This method overwrites the <span class="classname">MongoClient</span>
constructor and turns off acknowledged writes.

Please see <span class="methodname">MongoClient::\_\_construct</span>
for description of the parameters.

### Return Values

**Warning**

Instanciating this class will emit **`E_DEPRECATED`** warning, and turn
off acknowledged writes.

Please use the <span class="classname">MongoClient</span> instead.

Mongo::getPoolSize
==================

Get pool size for connection pools

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">int</span> <span
class="methodname">Mongo::getPoolSize</span> ( <span
class="methodparam">void</span> )

**Warning**

This feature has been *DEPRECATED* as of version 1.2.3. Relying on this
feature is highly discouraged. Please use <span
class="function">MongoPool::getSize</span> instead.

### Parameters

This function has no parameters.

### Return Values

Returns the current pool size.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### Examples

**Example \#1 Changing pool size**

This returns the default pool size, sets a new pool size, then prints
the new pool size and the pool debugging information. Note that changing
the pool size only affects new connection pools, it does not change old
ones.

``` php
<?php

$connection = new Mongo("host1");

// pool size is -1
echo "pool size is: ".Mongo::getPoolSize()."\n";

echo "setting pool size to 200\n";

Mongo::setPoolSize(200);

// pool size is 200
echo "pool size is: ".Mongo::getPoolSize()."\n";

$conn2 = new Mongo("host2");

// remaining for host1 is -2
// remaining for host2 is 199
var_dump(Mongo::poolDebug());

?>
```

### See Also

-   <span class="function">Mongo::setPoolSize</span>
-   <span class="function">Mongo::poolDebug</span>
-   The
    <a href="/book/mongo.html#Connecting" class="link">connection</a>
    documentation.

Mongo::getSlave
===============

Returns the address being used by this for slaveOkay reads

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Mongo::getSlave</span> ( <span
class="methodparam">void</span> )

This finds the address of the secondary currently being used for reads.
It is a read-only method: it does not change anything about the internal
state of the object.

When you create a connection to the database, the driver will not
immediately decide on a secondary to use. Thus, after you connect, this
function will return **`NULL`** even if there are secondaries available.
When you first do a query with slaveOkay set, at that point the driver
will choose a secondary for this connection. At that point, this
function will return the chosen secondary.

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

This function has no parameters.

### Return Values

The address of the secondary this connection is using for reads.

This returns **`NULL`** if this is not connected to a replica set or not
yet initialized.

### Errors/Exceptions

Issues **`E_DEPRECATED`** warning

The returned results aren't really useful as the secondary selection
process is done on each query and database command execution.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### See Also

-   <span class="function">MongoCursor::info</span>

Mongo::getSlaveOkay
===================

Get slaveOkay setting for this connection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Mongo::getSlaveOkay</span> ( <span
class="methodparam">void</span> )

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

This function has no parameters.

### Return Values

Returns the value of slaveOkay for this instance.

### Errors/Exceptions

Issues **`E_DEPRECATED`** warning

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### See Also

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <span class="methodname">MongoClient::getReadPreference</span>

Mongo::poolDebug
================

Returns information about all connection pools

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Mongo::poolDebug</span> ( <span
class="methodparam">void</span> )

**Warning**

This feature has been *DEPRECATED* as of version 1.2.3. Relying on this
feature is highly discouraged. Please use <span
class="function">MongoPool::info</span> instead.

Returns an array of information about all connection pools.

### Parameters

This function has no parameters.

### Return Values

Each connection pool has an identifier, which starts with the host. For
each pool, this function shows the following fields:

`in use`  
The number of connections currently being used by <span
class="classname">MongoClient</span> instances.

`in pool`  
The number of connections currently in the pool (not being used).

`remaining`  
The number of connections that could be created by this pool. For
example, suppose a pool had 5 connections remaining and 3 connections in
the pool. We could create 8 new instances of <span
class="classname">MongoClient</span> before we exhausted this pool
(assuming no instances of <span class="classname">MongoClient</span>
went out of scope, returning their connections to the pool).

A negative number means that this pool will spawn unlimited connections.

Before a pool is created, you can change the max number of connections
by calling <span class="function">Mongo::setPoolSize</span>. Once a pool
is showing up in the output of this function, its size cannot be
changed.

`timeout`  
The socket timeout for connections in this pool. This is how long
connections in this pool will attempt to connect to a server before
giving up.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

Mongo::setPoolSize
==================

Set the size for future connection pools

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Mongo::setPoolSize</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> )

**Warning**

This method has been *DEPRECATED* as of version 1.2.3. Relying on this
feature is highly discouraged. Please use <span
class="function">MongoPool::setSize</span> instead.

Sets the max number of connections new pools will be able to create.

### Parameters

`size`  
The max number of connections future pools will be able to create.
Negative numbers mean that the pool will spawn an infinite number of
connections.

### Return Values

Returns the former value of pool size.

### Examples

**Example \#1 <span class="function">Mongo::setPoolSize</span> example**

If you set the pool size to *n* and then create *n* connections,
attempting to create an *n+1*st connection will throw a <span
class="classname">MongoConnectionException</span>.

``` php
<?php

// only allow one connection to a server
Mongo::setPoolSize(1);

// creates one connection to localhost:27017
$m1 = new Mongo();

// attempt to create a second connection to localhost:27017
// only one connection is allowed, so this will throw an exception
$m2 = new Mongo();

?>
```

The above example will output something similar to:

    Fatal error: Uncaught exception 'MongoConnectionException' with message 'no more connections in pool' in /path/to/php/script.php:10
    Stack trace:
    #0 /path/to/php/script.php(10): Mongo->__construct()
    #1 {main}
      thrown in /path/to/php/script.php on line 10

### See Also

-   <span class="function">Mongo::getPoolSize</span>
-   <span class="function">Mongo::poolDebug</span>
-   The
    <a href="/book/mongo.html#Connecting" class="link">connection</a>
    documentation.

Mongo::setSlaveOkay
===================

Change slaveOkay setting for this connection

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Mongo::setSlaveOkay</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$ok`<span
class="initializer"> = **`TRUE`**</span></span> \] )

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

`ok`  
If reads should be sent to secondary members of a replica set for all
possible queries using this <span class="classname">MongoClient</span>
instance.

### Return Values

Returns the former value of slaveOkay for this instance.

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### See Also

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>
-   <span class="methodname">MongoClient::setReadPreference</span>

Mongo::switchSlave
==================

Choose a new secondary for slaveOkay reads

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Mongo::switchSlave</span> ( <span
class="methodparam">void</span> )

This choses a random secondary for a connection to read from. It is
called automatically by the driver and should not need to be used. It
calls <span class="function">MongoClient::getHosts</span> (to refresh
the status of hosts) and <span class="function">Mongo::getSlave</span>
(to get the return value).

See
<a href="/book/mongo.html#Querying" class="link">the query section</a>
of this manual for information on distributing reads to secondaries.

### Parameters

This function has no parameters.

### Return Values

The address of the secondary this connection is using for reads. This
may be the same as the previous address as addresses are randomly
chosen. It may return only one address if only one secondary (or only
the primary) is available.

For example, if we had a three member replica set with a primary,
secondary, and arbiter this method would always return the address of
the secondary. If the secondary became unavailable, this method would
always return the address of the primary. If the primary also became
unavailable, this method would throw an exception, as an arbiter cannot
handle reads.

### Errors/Exceptions

Throws a <span class="classname">MongoException</span> (error code 15)
if it is called on a non-replica-set connection. It will also throw
<span class="classname">MongoException</span>s if it cannot find anyone
(primary or secondary) to read from (error code 16).

### Changelog

| Version           | Description                         |
|-------------------|-------------------------------------|
| PECL mongo 1.2.11 | Emits **`E_DEPRECATED`** when used. |

### See Also

-   <a href="/book/mongo.html#Read%20Preferences" class="xref"></a>

bson\_decode
============

Deserializes a BSON object into a PHP array

### Description

<span class="type">array</span> <span
class="methodname">bson\_decode</span> ( <span class="methodparam"><span
class="type">string</span> `$bson`</span> )

This function is very beta and entirely useless for 99% of users. It is
only useful if you're doing something weird, such as writing your own
driver on top of the PHP driver.

### Parameters

`bson`  
The BSON to be deserialized.

### Return Values

Returns the deserialized BSON object.

bson\_encode
============

Serializes a PHP variable into a BSON string

### Description

<span class="type">string</span> <span
class="methodname">bson\_encode</span> ( <span class="methodparam"><span
class="type">mixed</span> `$anything`</span> )

This function is very beta and entirely useless for 99% of users. It is
only useful if you're doing something weird, such as writing your own
driver on top of the PHP driver.

### Parameters

`anything`  
The variable to be serialized.

### Return Values

Returns the serialized string.

**Table of Contents**

-   [bson\_decode](/book/mongo.html#bson_decode) — Deserializes a BSON
    object into a PHP array
-   [bson\_encode](/book/mongo.html#bson_encode) — Serializes a PHP
    variable into a BSON string

Exceptions
==========

**Table of Contents**

-   [MongoException](/book/mongo.html#MongoException) — The
    MongoException class
-   [MongoResultException](/book/mongo.html#MongoResultException) — The
    MongoResultException class
    -   [MongoResultException::getDocument](/book/mongo.html#MongoResultException::getDocument)
        — Retrieve the full result document
-   [MongoCursorException](/book/mongo.html#MongoCursorException) — The
    MongoCursorException class
    -   [MongoCursorException::getHost](/book/mongo.html#MongoCursorException::getHost)
        — The hostname of the server that encountered the error
-   [MongoCursorTimeoutException](/book/mongo.html#MongoCursorTimeoutException)
    — The MongoCursorTimeoutException class
-   [MongoConnectionException](/book/mongo.html#MongoConnectionException)
    — The MongoConnectionException class
-   [MongoGridFSException](/book/mongo.html#MongoGridFSException) — The
    MongoGridFSException class
-   [MongoDuplicateKeyException](/book/mongo.html#MongoDuplicateKeyException)
    — The MongoDuplicateKeyException class
-   [MongoProtocolException](/book/mongo.html#MongoProtocolException) —
    The MongoProtocolException class
-   [MongoExecutionTimeoutException](/book/mongo.html#MongoExecutionTimeoutException)
    — The MongoExecutionTimeoutException class
-   [MongoWriteConcernException](/book/mongo.html#MongoWriteConcernException)
    — The MongoWriteConcernException class
    -   [MongoWriteConcernException::getDocument](/book/mongo.html#MongoWriteConcernException::getDocument)
        — Get the error document

VMWare Oddities
---------------

If you are running VMWare on Windows and are using CIFS, pausing the VM
will cause CIFS to go out of sync and cause weird errors on un-pausing
it ("The Mongo object has not been correctly initialized by its
constructor"). Permanently mounting the Windows shares will fix this and
you'll be able to pause and unpause at will.

To permanently mount the Windows shares, run:

``` shell
$ sudo update-rc.d -f umountnfs.sh remove
$ sudo update-rc.d umountnfs.sh stop 15 0 6 .
```

See
<a href="https://help.ubuntu.com/community/MountWindowsSharesPermanently" class="link external">» the Ubuntu docs</a>
for the most up-to-date instructions.

Introduction
------------

Default Mongo exception.

This covers a bunch of different error conditions that may eventually be
moved to more specific exceptions, but will always extend <span
class="classname">MongoException</span>.

-   *The MongoSomething object has not been correctly initialized by its
    constructor*

    Code: 0

    Probably your Mongo object is not connected to a database server.

-   *zero-length keys are not allowed, did you use $ with double
    quotes?*

    Code: 1

    You tried to save "" as a key. You generally should not do this. ""
    can mess up subobject access and is used by MongoDB internally.
    However, if you really want, you can set
    <a href="/book/mongo.html#" class="link">mongo.allow_empty_keys</a>
    to true in your php.ini file to override this sanity check. If you
    override this, it is highly recommended that you set error checking
    to strict to avoid string interpolation errors.

-   *'.' not allowed in key: \<key\>*

    Code: 2

    You attempted to write a key with '.' in it, which is prohibited.

-   *insert too large: \<size\>, max: \<max\>*

    Code: 3

    You're attempting to send too much data to the database at once: the
    database will only accept inserts up to a certain size (currently 16
    MB).

-   *no elements in doc*

    Code: 4

    You're attempting to save a document with no fields.

-   *size of BSON doc is \<size\> bytes, max \<max\>MB*

    Code: 5

    You're attempting to save a document that is larger than MongoDB can
    save.

-   *no documents given*

    Code: 6

    You're attempting to batch insert an empty array of documents.

-   *MongoCollection::group takes an array, object, or MongoCode key*

    Code: 7

    Wrong type parameter send to <span
    class="function">MongoCollection::group</span>.

-   *field names must be strings*

    Code: 8

    You should format field selectors as *array("field1" =\> 1, "field2"
    =\> 1, ..., "fieldN" =\> 1)*.

-   *invalid regex*

    Code: 9

    The regex passed to <span class="classname">MongoRegex</span> is not
    of the correct form.

-   *MongoDBRef::get: $ref field must be a string*

    Code: 10

-   *MongoDBRef::get: $db field must be a string*

    Code: 11

-   *non-utf8 string: \<str\>*

    Code: 12

    This error occurs if you attempt to send a non-utf8 string to the
    database. All strings going into the database should be UTF8. See
    php.ini options for the transition option of quieting this
    exception.

-   *mutex error: \<err\>*

    Code: 13

    The driver uses mutexes for synchronizing requests and responses in
    multithreaded environments. This is a fairly serious error and may
    not have a stack trace. It's unusual and should be reported to
    maintainers with any system information and steps to reproduce that
    you can provide.

-   *index name too long: \<len\>, max \<max\> characters*

    Code: 14

    Indexes with names longer than 128 characters cannot be created. If
    you get this error, you should use <span
    class="function">MongoCollection::ensureIndex</span>'s "name" option
    to create a shorter name for your index.

Class synopsis
--------------

**MongoException**

<span class="ooclass"> class **MongoException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

}

Introduction
------------

The MongoResultException is thrown by several command helpers (such as
<span class="methodname">MongoCollection::findAndModify</span>) in the
event of failure. The original result document is available through
<span class="methodname">MongoResultException::getDocument</span>.

Class synopsis
--------------

**MongoResultException**

<span class="ooclass"> class **MongoResultException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**MongoException** </span> {

/\* Properties \*/

<span class="modifier">public</span> `$document` ;

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getDocument</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`document`  
The raw result document as an array.

MongoResultException::getDocument
=================================

Retrieve the full result document

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoResultException::getDocument</span> (
<span class="methodparam">void</span> )

Retrieves the full error result document.

### Parameters

This function has no parameters.

### Return Values

The full result document as an array, including partial data if
available and additional keys.

### Examples

**Example \#1 <span
class="methodname">MongoResultException::getDocument</span> example**

``` php
<?php
$mc = new MongoClient("localhost");
$c = $mc->selectCollection("test", "test");

$c->insert(array(
     "name" => "Next promo",
     "inprogress" => false,
     "priority" => 0,
     "tasks" => array( "select product", "add inventory", "do placement"),
) );

$c->insert(array(
     "name" => "Biz report",
     "inprogress" => false,
     "priority" => 1,
     "tasks" => array( "run sales report", "email report" )
) );

$c->insert(array(
     "name" => "Biz report",
     "inprogress" => false,
     "priority" => 2,
     "tasks" => array( "run marketing report", "email report" )
    ),
    array("w" => true)
);

try {
    $retval = $c->findAndModify(
         array("inprogress" => false, "name" => "Biz report"),
         array('$set' => array('$set' => array('inprogress' => true, "started" => new MongoDate()))),
         null,
         array(
            "sort" => array("priority" => -1),
            "new" => true,
        )
    );
} catch(MongoResultException $e) {
    echo $e->getMessage(), "\n";
    $res = $e->getDocument();
    var_dump($res);
}
?>
```

The above examples will output something similar to:

    $set is not valid for storage.
    array(3) {
      ["lastErrorObject"]=>
      array(5) {
        ["connectionId"]=>
        int(6)
        ["err"]=>
        string(30) "$set is not valid for storage."
        ["code"]=>
        int(52)
        ["n"]=>
        int(0)
        ["ok"]=>
        float(1)
      }
      ["ok"]=>
      float(0)
      ["errmsg"]=>
      string(30) "$set is not valid for storage."
    }

Introduction
------------

Caused by accessing a cursor incorrectly or a error receiving a reply.
Note that this can be thrown by any database request that receives a
reply, not just queries. Writes, commands, and any other operation that
sends information to the database and waits for a response can throw a
<span class="classname">MongoCursorException</span>. The only exception
is *new MongoClient()* (creating a new connection), which will only
throw <span class="classname">MongoConnectionException</span>s.

This returns a specific error message to help diagnose the problem and a
numeric error code associated with the cause of the exception.

For example, suppose you tried to insert two documents with the same
\_id:

``` php
<?php

try {
    $collection->insert(array("_id" => 1), array("w" => 1));
    $collection->insert(array("_id" => 1), array("w" => 1));
}
catch (MongoCursorException $e) {
    echo "error message: ".$e->getMessage()."\n";
    echo "error code: ".$e->getCode()."\n";
}

?>
```

This would produce output like:

``` txt
error message: E11000 duplicate key error index: foo.bar.$_id_  dup key: { : 1 }
error code: 11000
```

Note that the MongoDB error code (11000) is used for the PHP error code.
The PHP driver uses the "native" error code wherever possible.

The following is a list of common errors, codes, and causes. Exact
errors are in italics, errors where the message can vary are described
in obliques.

-   *cannot modify cursor after beginning iteration*

    Code: 0

    You are calling a method that sets up the query after executing the
    query. Reset the cursor and try again.

    An example:

    ``` php
    <?php

    try {
        $cursor = $collection->find();
        var_dump($cursor->getNext());

        // getNext() queried the database, it's too late to set a limit
        $cursor->limit(1);
    }
    catch (MongoCursorException $e) {
        echo "error message: ".$e->getMessage()."\n";
        echo "error code: ".$e->getCode()."\n";
    }

    // this will work, though:
    $cursor->getNext();
    $cursor->reset();
    $cursor->limit(1);

    ?>
    ```

-   Get next batch send errors

    Code: 1

    Could not send the query to the database. Make sure the database is
    still up and the network is okay.

-   *cursor not found*

    Code: 2

    The driver was trying to fetch more results from the database, but
    the database did not have a record of the query. This usually means
    that the cursor timed out on the server side: after a few minutes of
    inactivity, the database will kill a cursor (see <span
    class="function">MongoCursor::immortal</span> for information on
    preventing this).

    An example:

    ``` php
    <?php

    try {
        $cursor = $collection->find();
        $cursor->getNext();

        // sleep for 15 minutes
        sleep(60*15);

        while ($cursor->hasNext()) {
            $cursor->getNext();
        }
    }
    catch (MongoCursorException $e) {
        echo "error message: ".$e->getMessage()."\n";
        echo "error code: ".$e->getCode()."\n";
    }

    ?>
    ```

-   *cursor-\>buf.pos is null*

    Code: 3

    This may indicate you are out of RAM or some other extraordinary
    circumstance.

-   *couldn't get response header*

    Code: 4

    A common error if the database or network goes down. This means that
    the driver couldn't get a response from the connection.

-   *no db response*

    Code: 5

    This may not even be an error, for example, the database command
    "shutdown" returns no response. However, if you were expecting a
    response, this means the database didn't give one.

-   *bad response length: %d, did the db assert?*

    Code: 6

    This means that the database said that its response was less than 0.
    This error probably indicates a network error or database
    corruption.

-   *incomplete header*

    Code: 7

    Highly unusual. Occurs if the database response started out
    correctly, but broke off in the middle. Probably indicates a network
    problem.

-   *incomplete response*

    Code: 8

    Highly unusual. Occurs if the database response started out
    correctly, but broke off in the middle. Probably indicates a network
    problem.

-   *couldn't find a response*

    Code: 9

    If the response was cached and now cannot be located.

-   *error getting socket*

    Code: 10

    The socket was closed or encountered an error. The driver should
    automatically reconnect (if possible) on the next operation.

-   *couldn't find reply, please try again*

    Code: 11

    The driver saves any database responses it cannot immediately match
    with a request. This exception occurs if the driver has already
    passed your request's response and cannot find your response in its
    cache.

-   *error getting database response: errstr*

    *WSA error getting database response: errstr*

    "errstr" is an io error reported directly from the C socket
    subsystem. On Windows, the error message is prefixed with "WSA".

-   *Timeout error*

    Code: 13

    If there was an error while waiting for a query to complete.

-   *couldn't send query: \<various\>*

    Code: 14

    C socket error on send.

-   *max number of retries exhausted, couldn't send query*

    Code: 19

    The driver will automatically retry "plain" queries (not commands) a
    couple of times if the first attempt failed for certain reasons.
    This is to cause fewer exceptions during replica set failover
    (although you will probably still have to deal with some) and gloss
    over transient network issues.

    This can also be caused by the driver not being able to reconnect at
    all to the database (if, for example, the database is unreachable).

    Version 1.2.2+.

Errors passed through by the database
-------------------------------------

Database errors should always trigger <span
class="classname">MongoCursorExceptions</span> on queries. Error
messages and codes are sent directly from the database and you should be
able to see matching errors in the database log.

A few common database errors are listed below:

-   *E11000 duplicate key error index: foo.bar.$X dup key: { /\* ... \*/
    }*

    Code: 11000

    Database error for duplicate keys.

-   *not master*

    Codes: 10107, 13435, and 10058

    Not master errors, piped through by the database. ach of these will
    cause the driver to disconnect and attempt to find a new primary.
    The actual error you get on failover may not be a "not master"
    error, depending on when the change in primary occurs.

Class synopsis
--------------

**MongoCursorException**

<span class="ooclass"> class **MongoCursorException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**MongoException** </span> {

}

MongoCursorException::getHost
=============================

The hostname of the server that encountered the error

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoCursorException::getHost</span> ( <span
class="methodparam">void</span> )

Returns the hostname of the server the query was sent too.

### Parameters

This function has no parameters.

### Return Values

Returns the hostname, or <span class="type">NULL</span> if the hostname
is unknown.

Introduction
------------

Caused by a query timing out. You can set the length of time to wait
before this exception is thrown by calling <span
class="function">MongoCursor::timeout</span> on the cursor or setting
*MongoCursor::$timeout*. The static variable is useful for queries such
as database commands and <span
class="function">MongoCollection::findOne</span>, both of which
implicitly use cursors.

Class synopsis
--------------

**MongoCursorTimeoutException**

<span class="ooclass"> class **MongoCursorTimeoutException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**MongoCursorException** </span> {

}

Introduction
------------

Thrown when the driver fails to connect to the database.

There are a number of possible error messages to help you diagnose the
connection problem. These are:

-   *No candidate servers found*

    Thrown when the driver cannot establish a connection to MongoDB
    (fulfilling the ReadPreferences, if specified).

-   *No server name given.*

    This error occurs if you pass in "" as the server name, probably
    because of an typo with string interpolation, e.g., "$servr" instead
    of "$server".

-   *failed to get host \[hostname\] or port \[portnum\] from
    \[server\].*

    This indicated that the server string was malformed. "\[hostname\]"
    and "\[portnum\]" will be as much as the driver could dicipher of
    it.

-   *Operation in progress*

    Connecting to the database timed out.

-   *Transport endpoint is not connected*

    Generally means that the connection string isn't correct, the driver
    couldn't even find the database server.

-   *couldn't determine master*

    No server in a replica set connection was identified as the primary.

-   *couldn't get host info for \[server\]*

    This indicated that DNS could not resolve the server address you
    gave. This could easily be caused by a typo, for example, "server"
    instead of "$server".

-   *Invalid Argument*

    This can be caused by attempting to connect to a machine that is up
    but that the database isn't actually running on. Make sure that
    you've started the database server before connecting.

-   *Permission denied*

    This means that the socket could not be opened due to permissions
    issues. On Red Hat variants, this can be caused by a default setting
    that does not allow Apache to create network connections. You can
    override this setting by running:

    ``` shell
    $ /usr/sbin/setsebool -P httpd_can_network_connect 1
    ```

    then restarting Apache.

If the error message is not listed above, it is probably an error from
the C socket, and you can search the web for its usual cause.

Class synopsis
--------------

**MongoConnectionException**

<span class="ooclass"> class **MongoConnectionException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**MongoException** </span> {

}

Introduction
------------

Thrown when there are errors reading or writing files to or from the
database.

Class synopsis
--------------

**MongoGridFSException**

<span class="ooclass"> class **MongoGridFSException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**MongoException** </span> {

}

Error codes
-----------

| Code | Message                                                                        | Reason                                                 |
|------|--------------------------------------------------------------------------------|--------------------------------------------------------|
| 3    | Could not open file `$filename`                                                | Attempting to store an invalid file, such as directory |
| 4    | File `$filename` is too large: `$filesize` bytes                               | Maximum filesize in GridFS is 4GB                      |
| 5    | could not find filehandle                                                      | Resource doesn't have a filehandle                     |
| 6    | no file is associate with this filehandle                                      | Resource isn't a file resource                         |
| 7    | error setting up file: `$filename`s                                            | Could not open file for reading                        |
| 9    | error reading file `$filename`s                                                | Failed reading file                                    |
| 10   | error reading filehandle                                                       | Failed reading from a resource                         |
| 11   | could not find uploaded file %s                                                | Filename doesn't seem to be uploaded file              |
| 12   | Couldn't find tmp\_name in the $\_FILES array. Are you sure the upload worked? | Uploaded filename probably failed                      |
| 13   | tmp\_name was not a string or an array                                         | Invalid filename given                                 |
| 14   | couldn't find file size                                                        | The `length` property is missing                       |
| 15   | Cannot find filename                                                           | No filename provided, and no `filename` property set   |
| 16   | could not open destination file %s                                             | Destination filename not writable                      |
| 17   | error reading chunk of file                                                    | Chunk corruption                                       |
| 18   | couldn't create a php\_stream                                                  | Couldn't create a stream resource                      |
| 19   | couldn't find `property`                                                       | Chunk corruption                                       |
| 20   | chunk `number` has wrong size (`size`) when the max is `maxchunksize`          | Chunk larger then expected                             |
| 21   | chunk has wrong format                                                         | Chunk corruption                                       |

Introduction
------------

Thrown when attempting to insert a document into a collection which
already contains the same values for the
<a href="/book/mongo.html#MongoCollection::ensureIndex" class="link">unique keys</a>.

Class synopsis
--------------

**MongoDuplicateKeyException**

<span class="ooclass"> class **MongoDuplicateKeyException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**MongoWriteConcernException** </span> {

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

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoWriteConcernException::getDocument</span>
( <span class="methodparam">void</span> )

}

Examples
--------

**Example \#1 Catching MongoDuplicateKeyException**

``` php
<?php
$mc = new MongoClient("localhost");

$c = $mc->selectCollection("test", "test");

$c->insert(array('_id' => 1));
try {
    $c->insert(array('_id' => 1));
} catch (MongoWriteConcernException $e) {
    echo $e->getMessage(), "\n";
}
?>
```

The above examples will output something similar to:

    localhost:27017: insertDocument :: caused by :: 11000 E11000 duplicate key error index: test.test.$_id_  dup key: { : 1 }

Introduction
------------

When talking to MongoDB 2.6.0, and later, certain operations (such as
writes) may throw MongoProtocolException when the response from the
server did not make sense - for example during network failure (we could
read the entire response) or data corruption.

This exception is also thrown when attempting to talk newer protocols
then the server supports, for example using the <span
class="classname">MongoWriteBatch</span> when talking to a MongoDB
server prior to 2.6.0.

Class synopsis
--------------

**MongoProtocolException**

<span class="ooclass"> class **MongoProtocolException** </span> <span
class="ooclass"> <span class="modifier">extends</span>
**MongoException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

}

Examples
--------

**Example \#2 Catching MongoProtocolException**

Running the following example against MongoDB prior to 2.6.0 will throw
an MongoProtocolException

``` php
<?php
$mc = new MongoClient("localhost");
$c = $mc->selectCollection("test", "test");

try {
    $batch = new MongoInsertBatch($c);
} catch(MongoProtocolException $e) {
    echo $e->getMessage();
}
?>
```

The above examples will output something similar to:

    Current primary does not have a Write API

Introduction
------------

Thrown when a operation times out server side (i.e. in MongoDB).

To configure the operation timeout threshold, use <span
class="methodname">MongoCursor::maxTimeMS</span> or the *"maxTimeMS"*
command option.

Class synopsis
--------------

**MongoExecutionTimeoutException**

<span class="ooclass"> class **MongoExecutionTimeoutException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**MongoException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

}

Introduction
------------

MongoWriteConcernException is thrown when a write fails. See
<a href="/book/mongo.html#Write%20Concerns" class="xref"></a> for how to
set failure thresholds.

Prior to MongoDB 2.6.0, the
<a href="https://docs.mongodb.com/manual/reference/command/getLastError" class="link external">» getLastError</a>
command would determine whether a write failed.

Class synopsis
--------------

**MongoWriteConcernException**

<span class="ooclass"> class **MongoWriteConcernException** </span>
<span class="ooclass"> <span class="modifier">extends</span>
**MongoCursorException** </span> {

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getDocument</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">MongoCursorException::getHost</span> ( <span
class="methodparam">void</span> )

}

MongoWriteConcernException::getDocument
=======================================

Get the error document

### Description

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">MongoWriteConcernException::getDocument</span>
( <span class="methodparam">void</span> )

Returns the actual response from the server that was interperated as an
error.

### Parameters

This function has no parameters.

### Return Values

A MongoDB document, if available, as an array.

Changelog
=========

The following changes have been made to classes/functions/methods of
this extension.

It supports all new features for MongoDB 2.6, including:

-   Aggregate can now return a cursor
-   Aggregation pipelines can now be explained
-   Possible to set maxTimeMS for commands and queries
-   Transparent support for the new command-based MongoDB write API
-   New MongoWriteBatch classes (using the new MongoDB write API)
-   Support for MongoDB Enterprise features (e.g. Kerberos, LDAP, X509)
-   Option to tune acceptable server latency for secondary reads
    (secondaryAcceptableLatencyMS)

With this release, some driver functionality which was previously
documented as deprecated will now formally raise deprecation notices.
This includes:

-   Instantiating the Mongo class
-   Calling MongoCursor::slaveOkay()
-   "wtimeout" and "safe" options for MongoCollection write operations
-   Manipulating public properties on core classes (such as
    $collection-\>w)

> **Note**:
>
> No previously deprecated features have been removed.

Changes in behaviour:

-   Setting the mongo.native\_long INI setting now raises an error on
    32-bit platforms, and now defaults to true for 64-bit platforms.

The 1.4 series introduced fundemental changes in how connections are
created to the MongoDB servers. The driver now utilizes PHP native
streams, so all normal PHP stream options apply. Furthermore, an
experimental Stream Context Support was added.

The 1.4.x series also added support for MongoDB 2.4.x.

The most important improvements however deal with the handling of
replica sets, especially nodes that timeout and nodes that are
unreachable for various reasons. Besides the improvements to replica set
handling, this release addresses issues with read preferences through
mongos nodes. It also adds support for SSL enabled connections as well
as journal and fsync connection string options.

The 1.3 series introduced several major changes to the extension such as
completely rewritten
<a href="/book/mongo.html#Connecting" class="link">connection handling</a>
(and removal of the pooling mechanism), support for
<a href="/book/mongo.html#Read%20Preferences" class="link">ReadPreferences</a>
and change the default
<a href="/book/mongo.html#Writes" class="link">WriteConcerns</a> to be
*acknowledged* by introducing a new class
<a href="/book/mongo.html#MongoClient" class="link">MongoClient</a>
which serves as a replacement class for the now deprecated <span
class="classname">Mongo</span> class.

The driver now also supports connecting to multiple mongos instances
(the Mongo Shard router) for loadbalancing.

Other enhancements include improved logging for easier connection
handling debugging with <span class="classname">MongoLog</span> and
support for the
<a href="https://docs.mongodb.com/manual/core/aggregation-pipeline/" class="link external">» Aggregation Framework</a>
via the <span class="methodname">MongoCollection::aggregate</span>
method.

Following is a list of all improvements to existing methods since their
inception.

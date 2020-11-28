Stomp Client
============

**Table of Contents**

-   [Introduction](/intro/stomp.html)
-   [Installing/Configuring](/stomp/setup.html)
    -   [Requirements](/stomp/setup.html#Requirements)
    -   [Installation](/stomp/setup.html#Installation)
    -   [Runtime
        Configuration](/stomp/setup.html#Runtime%20Configuration)
    -   [Resource Types](/stomp/setup.html#Resource%20Types)
-   [Examples](/stomp/examples.html)
-   [Stomp Functions](/ref/stomp.html)
    -   [stomp\_connect\_error](/ref/stomp.html#stomp_connect_error) —
        Returns a string description of the last connect error
    -   [stomp\_version](/ref/stomp.html#stomp_version) — Gets the
        current stomp extension version
-   [Stomp](/class/stomp.html) — The Stomp class
    -   [Stomp::abort](/class/stomp.html#Stomp::abort) — Rolls back a
        transaction in progress
    -   [Stomp::ack](/class/stomp.html#Stomp::ack) — Acknowledges
        consumption of a message
    -   [Stomp::begin](/class/stomp.html#Stomp::begin) — Starts a
        transaction
    -   [Stomp::commit](/class/stomp.html#Stomp::commit) — Commits a
        transaction in progress
    -   [Stomp::\_\_construct](/class/stomp.html#Stomp::__construct) —
        Opens a connection
    -   [Stomp::\_\_destruct](/class/stomp.html#Stomp::__destruct) —
        Closes stomp connection
    -   [Stomp::error](/class/stomp.html#Stomp::error) — Gets the last
        stomp error
    -   [Stomp::getReadTimeout](/class/stomp.html#Stomp::getReadTimeout)
        — Gets read timeout
    -   [Stomp::getSessionId](/class/stomp.html#Stomp::getSessionId) —
        Gets the current stomp session ID
    -   [Stomp::hasFrame](/class/stomp.html#Stomp::hasFrame) — Indicates
        whether or not there is a frame ready to read
    -   [Stomp::readFrame](/class/stomp.html#Stomp::readFrame) — Reads
        the next frame
    -   [Stomp::send](/class/stomp.html#Stomp::send) — Sends a message
    -   [Stomp::setReadTimeout](/class/stomp.html#Stomp::setReadTimeout)
        — Sets read timeout
    -   [Stomp::subscribe](/class/stomp.html#Stomp::subscribe) —
        Registers to listen to a given destination
    -   [Stomp::unsubscribe](/class/stomp.html#Stomp::unsubscribe) —
        Removes an existing subscription
-   [StompFrame](/class/stompframe.html) — The StompFrame class
    -   [StompFrame::\_\_construct](/class/stompframe.html#StompFrame::__construct)
        — Constructor
-   [StompException](/class/stompexception.html) — The StompException
    class
    -   [StompException::getDetails](/class/stompexception.html#StompException::getDetails)
        — Get exception details

Introduction
------------

Represents a connection between PHP and a Stomp compliant Message
Broker.

Class synopsis
--------------

**Stomp**

<span class="ooclass"> class **Stomp** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">abort</span> ( <span class="methodparam"><span
class="type">string</span> `$transaction_id`</span> \[, <span
class="methodparam"><span class="type">array</span> `$headers`</span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">ack</span> ( <span class="methodparam"><span
class="type">mixed</span> `$msg`</span> \[, <span
class="methodparam"><span class="type">array</span> `$headers`</span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">begin</span> ( <span class="methodparam"><span
class="type">string</span> `$transaction_id`</span> \[, <span
class="methodparam"><span class="type">array</span> `$headers`</span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">commit</span> ( <span class="methodparam"><span
class="type">string</span> `$transaction_id`</span> \[, <span
class="methodparam"><span class="type">array</span> `$headers`</span> \]
)

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$broker`<span
class="initializer"> =
ini\_get("stomp.default\_broker\_uri")</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$username`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$password`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \]\]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">error</span> ( <span class="methodparam">void</span>
)

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getReadTimeout</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getSessionId</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasFrame</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">stompframe</span> <span class="methodname">readFrame</span>
(\[ <span class="methodparam"><span class="type">string</span>
`$class_name`<span class="initializer"> = "stompFrame"</span></span> \]
)

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">send</span> ( <span class="methodparam"><span
class="type">string</span> `$destination`</span> , <span
class="methodparam"><span class="type">mixed</span> `$msg`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$headers`</span> \] )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">setReadTimeout</span> ( <span
class="methodparam"><span class="type">int</span> `$seconds`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$microseconds`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">subscribe</span> ( <span
class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">unsubscribe</span> ( <span
class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

}

Stomp::abort
============

stomp\_abort
============

Rolls back a transaction in progress

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::abort</span> ( <span
class="methodparam"><span class="type">string</span>
`$transaction_id`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_abort</span> ( <span class="methodparam"><span
class="type">resource</span> `$link`</span> , <span
class="methodparam"><span class="type">string</span>
`$transaction_id`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Rolls back a transaction in progress.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`transaction_id`  
The transaction to abort.

`headers`  
Associative array containing the additional headers (example: receipt).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

**Tip**

Stomp is inherently asynchronous. Synchronous communication can be
implemented adding a receipt header. This will cause methods to not
return anything until the server has acknowledged receipt of the message
or until read timeout was reached.

### Examples

**Example \#1 Object oriented style**

``` php
<?php

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

/* begin a transaction */
$stomp->begin('t1');

/* send a message to the queue */
$stomp->send('/queue/foo', 'bar', array('transaction' => 't1'));

/* rollback */
$stomp->abort('t1');

/* close connection */
unset($stomp);
?>
```

**Example \#2 Procedural style**

``` php
<?php

/* connection */
$link = stomp_connect('tcp://localhost:61613');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

/* begin a transaction */
stomp_begin($link, 't1');

/* send a message to the queue 'foo' */
stomp_send($link, '/queue/foo', 'bar', array('transaction' => 't1'));

/* rollback */
stomp_abort($link, 't1');

/* close connection */
stomp_close($link);

?>
```

Stomp::ack
==========

stomp\_ack
==========

Acknowledges consumption of a message

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::ack</span> ( <span
class="methodparam"><span class="type">mixed</span> `$msg`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$headers`</span> \] )

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_ack</span> ( <span class="methodparam"><span
class="type">resource</span> `$link`</span> , <span
class="methodparam"><span class="type">mixed</span> `$msg`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$headers`</span> \] )

Acknowledges consumption of a message from a subscription using client
acknowledgment.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`msg`  
The message/messageId to be acknowledged.

`headers`  
Associative array containing the additional headers (example: receipt).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> A transaction header may be specified, indicating that the message
> acknowledgment should be part of the named transaction.

**Tip**

Stomp is inherently asynchronous. Synchronous communication can be
implemented adding a receipt header. This will cause methods to not
return anything until the server has acknowledged receipt of the message
or until read timeout was reached.

### Examples

**Example \#1 Object oriented style**

``` php
<?php

$queue  = '/queue/foo';
$msg    = 'bar';

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

/* send a message to the queue 'foo' */
$stomp->send($queue, $msg);

/* subscribe to messages from the queue 'foo' */
$stomp->subscribe($queue);

/* read a frame */
$frame = $stomp->readFrame();

if ($frame->body === $msg) {
    /* acknowledge that the frame was received */
    $stomp->ack($frame);
}

/* remove the subscription */
$stomp->unsubscribe($queue);

/* close connection */
unset($stomp);

?>
```

**Example \#2 Procedural style**

``` php
<?php

$queue  = '/queue/foo';
$msg    = 'bar';

/* connection */
$link = stomp_connect('ssl://localhost:61612');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

/* begin a transaction */
stomp_begin($link, 't1');

/* send a message to the queue 'foo' */
stomp_send($link, $queue, $msg, array('transaction' => 't1'));

/* commit a transaction */
stomp_commit($link, 't1');

/* subscribe to messages from the queue 'foo' */
stomp_subscribe($link, $queue);

/* read a frame */
$frame = stomp_read_frame($link);

if ($frame['body'] === $msg) {
    /* acknowledge that the frame was received */
    stomp_ack($link, $frame['headers']['message-id']);
}

/* remove the subscription */
stomp_unsubscribe($link, $queue);

/* close connection */
stomp_close($link);

?>
```

Stomp::begin
============

stomp\_begin
============

Starts a transaction

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::begin</span> ( <span
class="methodparam"><span class="type">string</span>
`$transaction_id`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_begin</span> ( <span class="methodparam"><span
class="type">resource</span> `$link`</span> , <span
class="methodparam"><span class="type">string</span>
`$transaction_id`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Starts a transaction.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`transaction_id`  
The transaction id.

`headers`  
Associative array containing the additional headers (example: receipt).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

**Tip**

Stomp is inherently asynchronous. Synchronous communication can be
implemented adding a receipt header. This will cause methods to not
return anything until the server has acknowledged receipt of the message
or until read timeout was reached.

### Examples

See <span class="function">stomp\_commit</span> or <span
class="function">stomp\_abort</span>.

Stomp::commit
=============

stomp\_commit
=============

Commits a transaction in progress

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::commit</span> ( <span
class="methodparam"><span class="type">string</span>
`$transaction_id`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_commit</span> ( <span
class="methodparam"><span class="type">resource</span> `$link`</span> ,
<span class="methodparam"><span class="type">string</span>
`$transaction_id`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Commits a transaction in progress.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`transaction_id`  
The transaction id.

`headers`  
Associative array containing the additional headers (example: receipt).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

**Tip**

Stomp is inherently asynchronous. Synchronous communication can be
implemented adding a receipt header. This will cause methods to not
return anything until the server has acknowledged receipt of the message
or until read timeout was reached.

### Examples

**Example \#1 Object oriented style**

``` php
<?php

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

/* begin a transaction */
$stomp->begin('t1');

/* send a message to the queue */
$stomp->send('/queue/foo', 'bar', array('transaction' => 't1'));

/* commit */
$stomp->commit('t1');

/* close connection */
unset($stomp);

?>
```

**Example \#2 Procedural style**

``` php
<?php

/* connection */
$link = stomp_connect('tcp://localhost:61613');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

/* begin a transaction */
stomp_begin($link, 't1');

/* send a message to the queue 'foo' */
stomp_send($link, '/queue/foo', 'bar', array('transaction' => 't1'));

/* commit */
stomp_commit($link, 't1');

/* close connection */
stomp_close($link);

?>
```

Stomp::\_\_construct
====================

stomp\_connect
==============

Opens a connection

### Description

Object oriented style (constructor):

<span class="modifier">public</span> <span
class="methodname">Stomp::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$broker`<span
class="initializer"> =
ini\_get("stomp.default\_broker\_uri")</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$username`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$password`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \]\]\]\] )

Procedural style:

<span class="type">resource</span> <span
class="methodname">stomp\_connect</span> (\[ <span
class="methodparam"><span class="type">string</span> `$broker`<span
class="initializer"> =
ini\_get("stomp.default\_broker\_uri")</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$username`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$password`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \]\]\]\] )

Opens a connection to a stomp compliant Message Broker.

### Parameters

`broker`  
The broker URI

`username`  
The username.

`password`  
The password.

`headers`  
Associative array containing the additional headers (example: receipt).

### Return Values

> **Note**:
>
> A transaction header may be specified, indicating that the message
> acknowledgment should be part of the named transaction.

### Changelog

| Version          | Description                       |
|------------------|-----------------------------------|
| PECL stomp 1.0.1 | The `headers` parameter was added |

### Examples

**Example \#1 Object oriented style**

``` php
<?php

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

/* close connection */
unset($stomp);

?>
```

**Example \#2 Procedural style**

``` php
<?php

/* connection */
$link = stomp_connect('ssl://localhost:61612');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

/* close connection */
stomp_close($link);

?>
```

Stomp::\_\_destruct
===================

stomp\_close
============

Closes stomp connection

### Description

Object oriented style (destructor):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::\_\_destruct</span> ( <span
class="methodparam">void</span> )

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_close</span> ( <span class="methodparam"><span
class="type">resource</span> `$link`</span> )

Closes a previously opened connection.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

See <span class="function">stomp\_connect</span>.

Stomp::error
============

stomp\_error
============

Gets the last stomp error

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">Stomp::error</span> ( <span
class="methodparam">void</span> )

Procedural style:

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">stomp\_error</span> ( <span class="methodparam"><span
class="type">resource</span> `$link`</span> )

Gets the last stomp error.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

### Return Values

Returns an error string or **`FALSE`** if no error occurred.

### Examples

**Example \#1 Object oriented style**

``` php
<?php

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

var_dump($stomp->error());

if (!$stomp->abort('unknown-transaction', array('receipt' => 'foo'))) {
    var_dump($stomp->error());
}

/* close connection */
unset($stomp);

?>
```

The above example will output something similar to:

    bool(false)
    string(43) "Invalid transaction id: unknown-transaction"

**Example \#2 Procedural style**

``` php
<?php

/* connection */
$link = stomp_connect('ssl://localhost:61612');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

var_dump(stomp_error($link));

if (!stomp_abort($link, 'unknown-transaction', array('receipt' => 'foo'))) {
    var_dump(stomp_error($link));
}

/* close connection */
stomp_close($link);

?>
```

The above example will output something similar to:

    bool(false)
    string(43) "Invalid transaction id: unknown-transaction"

Stomp::getReadTimeout
=====================

stomp\_get\_read\_timeout
=========================

Gets read timeout

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">Stomp::getReadTimeout</span> ( <span
class="methodparam">void</span> )

Procedural style:

<span class="type">array</span> <span
class="methodname">stomp\_get\_read\_timeout</span> ( <span
class="methodparam"><span class="type">resource</span> `$link`</span> )

Gets read timeout

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

### Return Values

Returns an array with 2 elements: sec and usec.

### Examples

**Example \#1 Object oriented style**

``` php
<?php

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

var_dump($stomp->getReadTimeout());

/* close connection */
unset($stomp);

?>
```

The above example will output something similar to:

    array(2) {
      ["sec"]=>
      int(2)
      ["usec"]=>
      int(0)
    }

**Example \#2 Procedural style**

``` php
<?php

/* connection */
$link = stomp_connect('ssl://localhost:61612');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

var_dump(stomp_get_read_timeout($link));

/* close connection */
stomp_close($link);

?>
```

The above example will output something similar to:

    array(2) {
      ["sec"]=>
      int(2)
      ["usec"]=>
      int(0)
    }

Stomp::getSessionId
===================

stomp\_get\_session\_id
=======================

Gets the current stomp session ID

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">Stomp::getSessionId</span> ( <span
class="methodparam">void</span> )

Procedural style:

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">stomp\_get\_session\_id</span> ( <span
class="methodparam"><span class="type">resource</span> `$link`</span> )

Gets the current stomp session ID.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

### Return Values

<span class="type">string</span> session id on success or **`FALSE`** on
failure.

### Examples

**Example \#1 Object oriented style**

``` php
<?php

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

var_dump($stomp->getSessionId());

/* close connection */
unset($stomp);

?>
```

The above example will output something similar to:

    string(35) "ID:php.net-52873-1257291895530-4:14"

**Example \#2 Procedural style**

``` php
<?php

/* connection */
$link = stomp_connect('ssl://localhost:61612');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

var_dump(stomp_get_session_id($link));

/* close connection */
stomp_close($link);

?>
```

The above example will output something similar to:

    string(35) "ID:php.net-52873-1257291895530-4:14"

Stomp::hasFrame
===============

stomp\_has\_frame
=================

Indicates whether or not there is a frame ready to read

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::hasFrame</span> ( <span
class="methodparam">void</span> )

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_has\_frame</span> ( <span
class="methodparam"><span class="type">resource</span> `$link`</span> )

Indicates whether or not there is a frame ready to read.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

### Return Values

Returns **`TRUE`** if a frame is ready to read, or **`FALSE`**
otherwise.

Stomp::readFrame
================

stomp\_read\_frame
==================

Reads the next frame

### Description

Object oriented style (method):

<span class="modifier">public</span> <span
class="type">stompframe</span> <span
class="methodname">Stomp::readFrame</span> (\[ <span
class="methodparam"><span class="type">string</span> `$class_name`<span
class="initializer"> = "stompFrame"</span></span> \] )

Procedural style:

<span class="type">array</span> <span
class="methodname">stomp\_read\_frame</span> ( <span
class="methodparam"><span class="type">resource</span> `$link`</span> )

Reads the next frame. It is possible to instantiate an object of a
specific class, and pass parameters to that class's constructor.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`class_name`  
The name of the class to instantiate. If not specified, a stompFrame
object is returned.

### Return Values

> **Note**:
>
> A transaction header may be specified, indicating that the message
> acknowledgment should be part of the named transaction.

### Changelog

| Version     | Description                       |
|-------------|-----------------------------------|
| Stomp 0.4.0 | `class_name` parameter was added. |

### Examples

**Example \#1 Object oriented style**

``` php
<?php

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

/* subscribe to messages from the queue 'foo' */
$stomp->subscribe('/queue/foo');

/* read a frame */
var_dump($stomp->readFrame());

/* close connection */
unset($stomp);

?>
```

The above example will output something similar to:

    object(StompFrame)#2 (3) {
      ["command"]=>
      string(7) "MESSAGE"
      ["headers"]=>
      array(5) {
        ["message-id"]=>
        string(41) "ID:php.net-55293-1257226743606-4:2:-1:1:1"
        ["destination"]=>
        string(10) "/queue/foo"
        ["timestamp"]=>
        string(13) "1257226805828"
        ["expires"]=>
        string(1) "0"
        ["priority"]=>
        string(1) "0"
      }
      ["body"]=>
      string(3) "bar"
    }

**Example \#2 Procedural style**

``` php
<?php

/* connection */
$link = stomp_connect('ssl://localhost:61612');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

/* subscribe to messages from the queue 'foo' */
stomp_subscribe($link, '/queue/foo');

/* read a frame */
$frame = stomp_read_frame($link);

/* close connection */
stomp_close($link);

?>
```

The above example will output something similar to:

    array(3) {
      ["command"]=>
      string(7) "MESSAGE"
      ["body"]=>
      string(3) "bar"
      ["headers"]=>
      array(6) {
        ["transaction"]=>
        string(2) "t1"
        ["message-id"]=>
        string(41) "ID:php.net-55293-1257226743606-4:3:-1:1:1"
        ["destination"]=>
        string(10) "/queue/foo"
        ["timestamp"]=>
        string(13) "1257227037059"
        ["expires"]=>
        string(1) "0"
        ["priority"]=>
        string(1) "0"
      }
    }

Stomp::send
===========

stomp\_send
===========

Sends a message

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::send</span> ( <span
class="methodparam"><span class="type">string</span>
`$destination`</span> , <span class="methodparam"><span
class="type">mixed</span> `$msg`</span> \[, <span
class="methodparam"><span class="type">array</span> `$headers`</span> \]
)

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_send</span> ( <span class="methodparam"><span
class="type">resource</span> `$link`</span> , <span
class="methodparam"><span class="type">string</span>
`$destination`</span> , <span class="methodparam"><span
class="type">mixed</span> `$msg`</span> \[, <span
class="methodparam"><span class="type">array</span> `$headers`</span> \]
)

Sends a message to the Message Broker.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`destination`  
Where to send the message

`msg`  
Message to send.

`headers`  
Associative array containing the additional headers (example: receipt).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> A transaction header may be specified, indicating that the message
> acknowledgment should be part of the named transaction.

**Tip**

Stomp is inherently asynchronous. Synchronous communication can be
implemented adding a receipt header. This will cause methods to not
return anything until the server has acknowledged receipt of the message
or until read timeout was reached.

### Examples

See <span class="function">stomp\_ack</span>.

Stomp::setReadTimeout
=====================

stomp\_set\_read\_timeout
=========================

Sets read timeout

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">Stomp::setReadTimeout</span> ( <span
class="methodparam"><span class="type">int</span> `$seconds`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$microseconds`</span> \] )

Procedural style:

<span class="type">void</span> <span
class="methodname">stomp\_set\_read\_timeout</span> ( <span
class="methodparam"><span class="type">resource</span> `$link`</span> ,
<span class="methodparam"><span class="type">int</span>
`$seconds`</span> \[, <span class="methodparam"><span
class="type">int</span> `$microseconds`</span> \] )

Sets read timeout.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`seconds`  
The seconds part of the timeout to be set.

`microseconds`  
The microseconds part of the timeout to be set.

### Examples

**Example \#1 Object oriented style**

``` php
<?php

/* connection */
try {
    $stomp = new Stomp('tcp://localhost:61613');
} catch(StompException $e) {
    die('Connection failed: ' . $e->getMessage());
}

$stomp->setReadTimeout(10);
    
/* close connection */
unset($stomp);

?>
```

**Example \#2 Procedural style**

``` php
<?php

/* connection */
$link = stomp_connect('ssl://localhost:61612');

/* check connection */
if (!$link) {
    die('Connection failed: ' . stomp_connect_error());
}

stomp_set_read_timeout($link, 10);
    
/* close connection */
stomp_close($link);

?>
```

Stomp::subscribe
================

stomp\_subscribe
================

Registers to listen to a given destination

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::subscribe</span> ( <span
class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_subscribe</span> ( <span
class="methodparam"><span class="type">resource</span> `$link`</span> ,
<span class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Registers to listen to a given destination.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`destination`  
Destination to subscribe to.

`headers`  
Associative array containing the additional headers (example: receipt).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

**Tip**

Stomp is inherently asynchronous. Synchronous communication can be
implemented adding a receipt header. This will cause methods to not
return anything until the server has acknowledged receipt of the message
or until read timeout was reached.

### Examples

See <span class="function">stomp\_ack</span>.

Stomp::unsubscribe
==================

stomp\_unsubscribe
==================

Removes an existing subscription

### Description

Object oriented style (method):

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">Stomp::unsubscribe</span> ( <span
class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Procedural style:

<span class="type">bool</span> <span
class="methodname">stomp\_unsubscribe</span> ( <span
class="methodparam"><span class="type">resource</span> `$link`</span> ,
<span class="methodparam"><span class="type">string</span>
`$destination`</span> \[, <span class="methodparam"><span
class="type">array</span> `$headers`</span> \] )

Removes an existing subscription.

### Parameters

`link`  
Procedural style only: The stomp link identifier returned by <span
class="function">stomp\_connect</span>.

`destination`  
Subscription to remove.

`headers`  
Associative array containing the additional headers (example: receipt).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

**Tip**

Stomp is inherently asynchronous. Synchronous communication can be
implemented adding a receipt header. This will cause methods to not
return anything until the server has acknowledged receipt of the message
or until read timeout was reached.

### Examples

See <span class="function">stomp\_ack</span>.

Introduction
------------

Represents a message which was sent or received from a Stomp compliant
Message Broker.

Class synopsis
--------------

**StompFrame**

<span class="ooclass"> class **StompFrame** </span> {

/\* Properties \*/

<span class="modifier">public</span> `$command` ;

<span class="modifier">public</span> `$headers` ;

<span class="modifier">public</span> `$body` ;

/\* Methods \*/

<span class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$command`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$headers`</span> \[, <span class="methodparam"><span
class="type">string</span> `$body`</span> \]\]\] )

}

Properties
----------

`command`  
Frame command.

`headers`  
Frame headers (<span class="type">array</span>).

`body`  
Frame body.

StompFrame::\_\_construct
=========================

Constructor

### Description

<span class="methodname">StompFrame::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$command`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$headers`</span> \[, <span class="methodparam"><span
class="type">string</span> `$body`</span> \]\]\] )

Constructor.

### Parameters

`command`  
Frame command

`headers`  
Frame headers (<span class="type">array</span>).

`body`  
Frame body.

Introduction
------------

Represents an error raised by the stomp extension. See
<a href="/language/exceptions.html" class="link">Exceptions</a> for more
information about Exceptions in PHP.

Class synopsis
--------------

**StompException**

<span class="ooclass"> class **StompException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

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

/\* Methods \*/

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getDetails</span> ( <span
class="methodparam">void</span> )

}

StompException::getDetails
==========================

Get exception details

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">StompException::getDetails</span> ( <span
class="methodparam">void</span> )

Get exception details.

### Return Values

<span class="type">string</span> containing the error details.

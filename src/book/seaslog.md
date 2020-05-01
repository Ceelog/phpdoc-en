Seaslog
=======

**Table of Contents**

-   [Introduction](/intro/seaslog.html)
-   [Installing/Configuring](/seaslog/setup.html)
    -   [Requirements](/seaslog/setup.html#Requirements)
    -   [Installation](/seaslog/setup.html#Installation)
    -   [Runtime
        Configuration](/seaslog/setup.html#Runtime%20Configuration)
    -   [Resource Types](/seaslog/setup.html#Resource%20Types)
-   [Predefined Constants](/seaslog/constants.html)
-   [Examples](/seaslog/examples.html)
-   [Seaslog Functions](/ref/seaslog.html)
    -   [seaslog\_get\_author](/ref/seaslog.html#seaslog_get_author) —
        Get SeasLog author.
    -   [seaslog\_get\_version](/ref/seaslog.html#seaslog_get_version) —
        Get SeasLog version.
-   [SeasLog](/class/seaslog.html) — The SeasLog class
    -   [SeasLog::alert](/class/seaslog.html#SeasLog::alert) — Record
        alert log information
    -   [SeasLog::analyzerCount](/class/seaslog.html#SeasLog::analyzerCount)
        — Get log count by level, log\_path and key\_word
    -   [SeasLog::analyzerDetail](/class/seaslog.html#SeasLog::analyzerDetail)
        — Get log detail by level, log\_path, key\_word, start, limit,
        order
    -   [SeasLog::closeLoggerStream](/class/seaslog.html#SeasLog::closeLoggerStream)
        — Manually release stream flow from logger
    -   [SeasLog::\_\_construct](/class/seaslog.html#SeasLog::__construct)
        — Description
    -   [SeasLog::critical](/class/seaslog.html#SeasLog::critical) —
        Record critical log information
    -   [SeasLog::debug](/class/seaslog.html#SeasLog::debug) — Record
        debug log information
    -   [SeasLog::\_\_destruct](/class/seaslog.html#SeasLog::__destruct)
        — Description
    -   [SeasLog::emergency](/class/seaslog.html#SeasLog::emergency) —
        Record emergency log information
    -   [SeasLog::error](/class/seaslog.html#SeasLog::error) — Record
        error log information
    -   [SeasLog::flushBuffer](/class/seaslog.html#SeasLog::flushBuffer)
        — Flush logs buffer, dump to appender file, or send to remote
        api with tcp/udp
    -   [SeasLog::getBasePath](/class/seaslog.html#SeasLog::getBasePath)
        — Get SeasLog base path.
    -   [SeasLog::getBuffer](/class/seaslog.html#SeasLog::getBuffer) —
        Get the logs buffer in memory as array
    -   [SeasLog::getBufferEnabled](/class/seaslog.html#SeasLog::getBufferEnabled)
        — Determin if buffer enabled
    -   [SeasLog::getDatetimeFormat](/class/seaslog.html#SeasLog::getDatetimeFormat)
        — Get SeasLog datetime format style
    -   [SeasLog::getLastLogger](/class/seaslog.html#SeasLog::getLastLogger)
        — Get SeasLog last logger path
    -   [SeasLog::getRequestID](/class/seaslog.html#SeasLog::getRequestID)
        — Get SeasLog request\_id differentiated requests
    -   [SeasLog::getRequestVariable](/class/seaslog.html#SeasLog::getRequestVariable)
        — Get SeasLog request variable
    -   [SeasLog::info](/class/seaslog.html#SeasLog::info) — Record info
        log information
    -   [SeasLog::log](/class/seaslog.html#SeasLog::log) — The Common
        Record Log Function
    -   [SeasLog::notice](/class/seaslog.html#SeasLog::notice) — Record
        notice log information
    -   [SeasLog::setBasePath](/class/seaslog.html#SeasLog::setBasePath)
        — Set SeasLog base path
    -   [SeasLog::setDatetimeFormat](/class/seaslog.html#SeasLog::setDatetimeFormat)
        — Set SeasLog datetime format style
    -   [SeasLog::setLogger](/class/seaslog.html#SeasLog::setLogger) —
        Set SeasLog logger name
    -   [SeasLog::setRequestID](/class/seaslog.html#SeasLog::setRequestID)
        — Set SeasLog request\_id differentiated requests
    -   [SeasLog::setRequestVariable](/class/seaslog.html#SeasLog::setRequestVariable)
        — Manually set SeasLog request variable
    -   [SeasLog::warning](/class/seaslog.html#SeasLog::warning) —
        Record warning log information

Introduction
------------

Class synopsis
--------------

**SeasLog**

<span class="ooclass"> class **SeasLog** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">alert</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">array</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$logger`</span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">analyzerCount</span> ( <span
class="methodparam"><span class="type">string</span> `$level`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$log_path`</span> \[, <span class="methodparam"><span
class="type">string</span> `$key_word`</span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">analyzerDetail</span> ( <span
class="methodparam"><span class="type">string</span> `$level`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$log_path`</span> \[, <span class="methodparam"><span
class="type">string</span> `$key_word`</span> \[, <span
class="methodparam"><span class="type">int</span> `$start`</span> \[,
<span class="methodparam"><span class="type">int</span> `$limit`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$order`</span> \]\]\]\]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">closeLoggerStream</span> ( <span
class="methodparam"><span class="type">int</span> `$model`</span> ,
<span class="methodparam"><span class="type">string</span>
`$logger`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">critical</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">array</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$logger`</span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">debug</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">array</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$logger`</span> \]\] )

<span class="modifier">public</span> <span
class="methodname">\_\_destruct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">emergency</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">array</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$logger`</span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">error</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">array</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$logger`</span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">flushBuffer</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Seaslog::getBasePath</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getBuffer</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">getBufferEnabled</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getDatetimeFormat</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getLastLogger</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">getRequestID</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">getRequestVariable</span> ( <span
class="methodparam"><span class="type">int</span> `$key`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">info</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">array</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$logger`</span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">log</span> ( <span class="methodparam"><span
class="type">string</span> `$level`</span> \[, <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">notice</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">array</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$logger`</span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setBasePath</span> ( <span class="methodparam"><span
class="type">string</span> `$base_path`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setDatetimeFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setLogger</span> ( <span class="methodparam"><span
class="type">string</span> `$logger`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setRequestID</span> ( <span class="methodparam"><span
class="type">string</span> `$request_id`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">setRequestVariable</span> ( <span
class="methodparam"><span class="type">int</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">warning</span> ( <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type">array</span> `$content`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$logger`</span> \]\] )

}

SeasLog::alert
==============

Record alert log information

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::alert</span> ( <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\] )

Record alert log information.

> **Note**:
>
> "ALERT" - Action must be taken immediately. Immediate attention should
> be given to relevant personnel for emergency repairs.

### Parameters

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::alert</span> example**

``` php
<?php

var_dump(SeasLog::alert('log message'));

//with content
var_dump(SeasLog::alert('log message from {NAME}',array('NAME' => 'neeke')));

//with tmp logger
var_dump(SeasLog::alert('log message from {NAME}',array('NAME' => 'neeke'),'tmp_logger'));

var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    array(2) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(81) "2018-07-07 11:45:49 | ALERT | 73263 | 5b40376d1067c | 1530935149.68 | log message
    "
        [1]=>
        string(92) "2018-07-07 11:45:49 | ALERT | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:45:49 | ALERT | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::debug</span>
-   <span class="methodname">SeasLog::info</span>
-   <span class="methodname">SeasLog::notice</span>
-   <span class="methodname">SeasLog::warning</span>
-   <span class="methodname">SeasLog::error</span>
-   <span class="methodname">SeasLog::critical</span>
-   <span class="methodname">SeasLog::emergency</span>
-   <span class="methodname">SeasLog::log</span>

SeasLog::analyzerCount
======================

Get log count by level, log\_path and key\_word

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">SeasLog::analyzerCount</span> ( <span
class="methodparam"><span class="type">string</span> `$level`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$log_path`</span> \[, <span class="methodparam"><span
class="type">string</span> `$key_word`</span> \]\] )

\`SeasLog\` get count value of \`grep -ai '{level}' \| grep -aic
'{key\_word}'\` use system pipe and return to PHP (array or int).

### Parameters

`level`  
String. The log information level.

`log_path`  
String. The log information path.

`key_word`  
String. The search key word for log information.

### Return Values

If \`level\` is SEASLOG\_ALL or Empty, return all levels count as
\`array\`. If \`level\` is SEASLOG\_INFO or the other level, return
count as \`int\`.

### Examples

**Example \#1 <span class="function">SeasLog::analyzerCount</span>
example**

``` php
<?php

$countResult1 = SeasLog::analyzerCount();

//with `level`
$countResult2 = SeasLog::analyzerCount(SEASLOG_DEBUG);

//with `level` and `log_path`
$countResult3 = SeasLog::analyzerCount(SEASLOG_ERROR,date('Ymd',time()));

//with `level` and `key_word`
$countResult4 = SeasLog::analyzerCount(SEASLOG_DEBUG,NULL,'accessToken');

var_dump($countResult1,$countResult2,$countResult3,$countResult4);

?>
```

The above example will output something similar to:

    array(8) {
      ["DEBUG"]=>
      int(180)
      ["INFO"]=>
      int(214)
      ["NOTICE"]=>
      int(0)
      ["WARNING"]=>
      int(0)
      ["ERROR"]=>
      int(228)
      ["CRITICAL"]=>
      int(244)
      ["ALERT"]=>
      int(1)
      ["EMERGENCY"]=>
      int(0)
    }

    int(180)

    int(228)

    int(29)

### See Also

-   <span class="methodname">SeasLog::analyzerDetail</span>

SeasLog::analyzerDetail
=======================

Get log detail by level, log\_path, key\_word, start, limit, order

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">SeasLog::analyzerDetail</span> ( <span
class="methodparam"><span class="type">string</span> `$level`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$log_path`</span> \[, <span class="methodparam"><span
class="type">string</span> `$key_word`</span> \[, <span
class="methodparam"><span class="type">int</span> `$start`</span> \[,
<span class="methodparam"><span class="type">int</span> `$limit`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$order`</span> \]\]\]\]\] )

\`SeasLog\` get results of \`grep -ai '{level}' \| grep -ai
'{key\_word}' \| sed -n '{start},{limit}'p\` use system pipe and return
array to PHP.

### Parameters

`level`  
String. The log information level.

`log_path`  
String. The log information path.

`key_word`  
String. The search key word for log information.

`start`  
Int. Default is \`1\`.

`limit`  
Int. Default is \`20\`.

`order`  
Int. Default is
<a href="/seaslog/constants.html#" class="link">SEASLOG_DETAIL_ORDER_ASC</a>.
See also:

-   <a href="/seaslog/constants.html#" class="link">SEASLOG_DETAIL_ORDER_ASC</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_DETAIL_ORDER_DESC</a>

### Return Values

Return results as array.

> **Note**:
>
> When \`start\`,\`limit\` is not NULL and in Windows, SeasLog will
> threw exception with message 'Param start and limit don't support
> Windows'.

### Examples

**Example \#1 <span class="function">SeasLog::analyzerDetail</span>
example**

``` php
<?php

$result1 = SeasLog::analyzerDetail(SEASLOG_ERROR);

//with `logger` and `key_word`
$result2 = SeasLog::analyzerDetail(SEASLOG_ERROR,'test/logger/','neeke');

//with `start` and `limit`
$result3 = SeasLog::analyzerDetail(SEASLOG_ERROR,'test/logger/','neeke',1,2);

var_dump($result1,$result2,$result3);
?>
```

The above example will output something similar to:

    array(20) {
      [0]=>
      string(93) "2018-07-09 12:52:53 | ERROR | 12247 | 5b42ea2580e51 | 1531111973.528 | log message from neeke"
      [1]=>
      string(93) "2018-07-09 12:52:54 | ERROR | 12256 | 5b42ea26d6657 | 1531111974.878 | log message from neeke"
      [2]=>
      string(93) "2018-07-09 12:52:55 | ERROR | 12265 | 5b42ea277b8d4 | 1531111975.506 | log message from neeke"
      [3]=>
      string(104) "2018-07-09 12:52:55 | ERROR | 12274 | 5b42ea27db5dc | 1531111975.898 | log message from the other people"
    ...
    }

    array(3) {
      [0]=>
      string(93) "2018-07-09 12:52:53 | ERROR | 12247 | 5b42ea2580e51 | 1531111973.528 | log message from neeke"
      [1]=>
      string(93) "2018-07-09 12:52:54 | ERROR | 12256 | 5b42ea26d6657 | 1531111974.878 | log message from neeke"
      [2]=>
      string(93) "2018-07-09 12:52:55 | ERROR | 12265 | 5b42ea277b8d4 | 1531111975.506 | log message from neeke"
    }

    array(2) {
      [0]=>
      string(93) "2018-07-09 12:52:53 | ERROR | 12247 | 5b42ea2580e51 | 1531111973.528 | log message from neeke"
      [1]=>
      string(93) "2018-07-09 12:52:54 | ERROR | 12256 | 5b42ea26d6657 | 1531111974.878 | log message from neeke"
    }

### See Also

-   <span class="methodname">SeasLog::analyzerCount</span>

SeasLog::closeLoggerStream
==========================

Manually release stream flow from logger

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::closeLoggerStream</span> ( <span
class="methodparam"><span class="type">int</span> `$model`</span> ,
<span class="methodparam"><span class="type">string</span>
`$logger`</span> )

Manually release stream flow from logger. SeasLog caches the stream
handle opened by the log logger to save the overhead of creating a
stream. The handle will be automatically released at the end of the
request. If in CLI mode, the process will also automatically release
when it exits. Or you can use the following functions to manually
release(manually release function needs to update SeasLog 1.8.6 or
updated version).

### Parameters

`model`  
Constant int.

-   <a href="/seaslog/constants.html#" class="link">SEASLOG_CLOSE_LOGGER_STREAM_MOD_ALL</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_CLOSE_LOGGER_STREAM_MOD_ASSIGN</a>

`logger`  
The logger name.

### Return Values

Return TRUE on released stream flow success, FALSE on failure.

### Examples

**Example \#1 <span class="methodname">SeasLog::closeLoggerStream</span>
example**

``` php
<?php

var_dump(SeasLog::closeLoggerStream());
var_dump(SeasLog::closeLoggerStream(SEASLOG_CLOSE_LOGGER_STREAM_MOD_ALL));
var_dump(SeasLog::closeLoggerStream(SEASLOG_CLOSE_LOGGER_STREAM_MOD_ASSIGN, 'logger_name'));

?>
```

The above example will output something similar to:


    bool(true)
    bool(true)
    bool(true)

### See Also

-   <span class="methodname">SeasLog::setLogger</span>
-   <span class="methodname">SeasLog::getLastLogger</span>

SeasLog::\_\_construct
======================

Description

### Description

<span class="modifier">public</span> <span
class="methodname">SeasLog::\_\_construct</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Examples

**Example \#1 <span class="function">SeasLog::\_\_construct</span>
example**

``` php
<?php

/* ... */

?>
```

The above example will output something similar to:

    ...

SeasLog::critical
=================

Record critical log information

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::critical</span> ( <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\] )

Record critical log information.

> **Note**:
>
> "CRITICAL" - Critical conditions.Need to be repaired immediately, and
> the program component is unavailable.

### Parameters

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::critical</span> example**

``` php
<?php

var_dump(SeasLog::critical('log message'));

//with content
var_dump(SeasLog::critical('log message from {NAME}',array('NAME' => 'neeke')));

//with tmp logger
var_dump(SeasLog::critical('log message from {NAME}',array('NAME' => 'neeke'),'tmp_logger'));

var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    array(2) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(81) "2018-07-07 11:45:49 | CRITICAL | 73263 | 5b40376d1067c | 1530935149.68 | log message
    "
        [1]=>
        string(92) "2018-07-07 11:45:49 | CRITICAL | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:45:49 | CRITICAL | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::debug</span>
-   <span class="methodname">SeasLog::info</span>
-   <span class="methodname">SeasLog::notice</span>
-   <span class="methodname">SeasLog::warning</span>
-   <span class="methodname">SeasLog::error</span>
-   <span class="methodname">SeasLog::alert</span>
-   <span class="methodname">SeasLog::emergency</span>
-   <span class="methodname">SeasLog::log</span>

SeasLog::debug
==============

Record debug log information

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::debug</span> ( <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\] )

Record debug log information.

> **Note**:
>
> "DEBUG" - Detailed debug information.Fine-grained information events.

### Parameters

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::debug</span> example**

``` php
<?php

var_dump(SeasLog::debug('log message'));

//with content
var_dump(SeasLog::debug('log message from {NAME}',array('NAME' => 'neeke')));

//with tmp logger
var_dump(SeasLog::debug('log message from {NAME}',array('NAME' => 'neeke'),'tmp_logger'));

var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    array(2) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(81) "2018-07-07 11:45:49 | DEBUG | 73263 | 5b40376d1067c | 1530935149.68 | log message
    "
        [1]=>
        string(92) "2018-07-07 11:45:49 | DEBUG | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:45:49 | DEBUG | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::info</span>
-   <span class="methodname">SeasLog::notice</span>
-   <span class="methodname">SeasLog::warning</span>
-   <span class="methodname">SeasLog::error</span>
-   <span class="methodname">SeasLog::critical</span>
-   <span class="methodname">SeasLog::alert</span>
-   <span class="methodname">SeasLog::emergency</span>
-   <span class="methodname">SeasLog::log</span>

SeasLog::\_\_destruct
=====================

Description

### Description

<span class="modifier">public</span> <span
class="methodname">SeasLog::\_\_destruct</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

### Examples

**Example \#1 <span class="function">SeasLog::\_\_destruct</span>
example**

``` php
<?php

/* ... */

?>
```

The above example will output something similar to:

    ...

SeasLog::emergency
==================

Record emergency log information

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::emergency</span> ( <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\] )

Record emergency log information.

> **Note**:
>
> "EMERGENCY" - System is unusable.

### Parameters

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::emergency</span> example**

``` php
<?php

var_dump(SeasLog::emergency('log message'));

//with content
var_dump(SeasLog::emergency('log message from {NAME}',array('NAME' => 'neeke')));

//with tmp logger
var_dump(SeasLog::emergency('log message from {NAME}',array('NAME' => 'neeke'),'tmp_logger'));

var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    array(2) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(81) "2018-07-07 11:45:49 | EMERGENCY | 73263 | 5b40376d1067c | 1530935149.68 | log message
    "
        [1]=>
        string(92) "2018-07-07 11:45:49 | EMERGENCY | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:45:49 | EMERGENCY | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::debug</span>
-   <span class="methodname">SeasLog::info</span>
-   <span class="methodname">SeasLog::notice</span>
-   <span class="methodname">SeasLog::warning</span>
-   <span class="methodname">SeasLog::error</span>
-   <span class="methodname">SeasLog::critical</span>
-   <span class="methodname">SeasLog::alert</span>
-   <span class="methodname">SeasLog::log</span>

SeasLog::error
==============

Record error log information

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::error</span> ( <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\] )

Record error log information.

> **Note**:
>
> "ERROR" - Runtime errors that do not require immediate action but
> should typically.

### Parameters

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::error</span> example**

``` php
<?php

var_dump(SeasLog::error('log message'));

//with content
var_dump(SeasLog::error('log message from {NAME}',array('NAME' => 'neeke')));

//with tmp logger
var_dump(SeasLog::error('log message from {NAME}',array('NAME' => 'neeke'),'tmp_logger'));

var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    array(2) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(81) "2018-07-07 11:45:49 | ERROR | 73263 | 5b40376d1067c | 1530935149.68 | log message
    "
        [1]=>
        string(92) "2018-07-07 11:45:49 | ERROR | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:45:49 | ERROR | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::debug</span>
-   <span class="methodname">SeasLog::info</span>
-   <span class="methodname">SeasLog::notice</span>
-   <span class="methodname">SeasLog::warning</span>
-   <span class="methodname">SeasLog::critical</span>
-   <span class="methodname">SeasLog::alert</span>
-   <span class="methodname">SeasLog::emergency</span>
-   <span class="methodname">SeasLog::log</span>

SeasLog::flushBuffer
====================

Flush logs buffer, dump to appender file, or send to remote api with
tcp/udp

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::flushBuffer</span> ( <span
class="methodparam">void</span> )

Flush logs buffer by
<a href="/seaslog/setup.html#" class="link">seaslog.appender</a>: dump
to file, or send to remote api with tcp/udp.

> **Note**:
>
> See also:
> <a href="/seaslog/setup.html#" class="link">seaslog.appender_retry</a>
> <a href="/seaslog/setup.html#" class="link">seaslog.remote_host</a>
> <a href="/seaslog/setup.html#" class="link">seaslog.remote_port</a>

### Parameters

This function has no parameters.

### Return Values

Return TRUE on flush buffer success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::flushBuffer</span>
example**

``` php
<?php

SeasLog::info('info log');
SeasLog::debug('debug log');
var_dump(SeasLog::getBuffer());
var_dump(SeasLog::flushBuffer());
var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    array(1) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(79) "2018-07-07 10:47:58 | INFO | 71910 | 5b4029ded6009 | 1530931678.877 | info log
    "
        [1]=>
        string(81) "2018-07-07 10:47:58 | DEBUG | 71910 | 5b4029ded6009 | 1530931678.877 | debug log
    "
      }
    }
    bool(true)
    array(0) {
    }

### See Also

-   <a href="/seaslog/setup.html#" class="link">seaslog.use_buffer</a>
-   <a href="/seaslog/setup.html#" class="link">seaslog.buffer_size</a>
-   <a href="/seaslog/setup.html#" class="link">seaslog.buffer_disabled_in_cli</a>
-   <span class="methodname">SeasLog::getBufferEnabled</span>
-   <span class="methodname">SeasLog::getBuffer</span>

SeasLog::getBasePath
====================

Get SeasLog base path.

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">Seaslog::getBasePath</span> ( <span
class="methodparam">void</span> )

Use the Function <span class="methodname">SeasLog::getBasePath</span>
will get the value of
<a href="/seaslog/setup.html#" class="link">seaslog.default_basepath</a>
what configured in php.ini(seaslog.ini).

If you use <span class="methodname">Seaslog::setBasePath</span>, will
change the result.

### Parameters

This function has no parameters.

### Return Values

Return
<a href="/seaslog/setup.html#" class="link">seaslog.default_basepath</a>
as string.

### Examples

**Example \#1 <span class="methodname">SeasLog::getBasePath</span>
example**

``` php
<?php

var_dump(SeasLog::getBasePath());

?>
```

The above example will output something similar to:

    string(12) "/var/log/www"

SeasLog::getBuffer
==================

Get the logs buffer in memory as array

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">SeasLog::getBuffer</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

Return an array from logs buffer in memory.

### Examples

**Example \#1 <span class="function">SeasLog::getBuffer</span> example**

``` php
<?php

var_dump(SeasLog::info('info log'));
var_dump(SeasLog::debug('debug log'));
var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    array(1) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(79) "2018-07-07 10:43:32 | INFO | 71785 | 5b4028d4c58d5 | 1530931412.810 | info log
    "
        [1]=>
        string(81) "2018-07-07 10:43:32 | DEBUG | 71785 | 5b4028d4c58d5 | 1530931412.810 | debug log
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#" class="link">seaslog.use_buffer</a>
-   <a href="/seaslog/setup.html#" class="link">seaslog.buffer_size</a>
-   <a href="/seaslog/setup.html#" class="link">seaslog.buffer_disabled_in_cli</a>
-   <span class="methodname">SeasLog::getBufferEnabled</span>
-   <span class="methodname">SeasLog::flushBuffer</span>

SeasLog::getBufferEnabled
=========================

Determin if buffer enabled

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::getBufferEnabled</span> ( <span
class="methodparam">void</span> )

Result join
<a href="/seaslog/setup.html#" class="link">seaslog.use_buffer</a> and
<a href="/seaslog/setup.html#" class="link">seaslog.buffer_disabled_in_cli</a>.

### Parameters

This function has no parameters.

### Return Values

Return TRUE on
<a href="/seaslog/setup.html#" class="link">seaslog.use_buffer</a> is
true. If switch
<a href="/seaslog/setup.html#" class="link">seaslog.buffer_disabled_in_cli</a>
on, and running in cli, seaslog.use\_buffer setting will be discarded,
Seaslog write to the Data Store IMMEDIATELY.

### Examples

**Example \#1 <span class="function">SeasLog::getBufferEnabled</span>
example**

``` php
<?php

var_dump(SeasLog::getBufferEnabled());

?>
```

The above example will output something similar to:

    bool(false)

### See Also

-   <a href="/seaslog/setup.html#" class="link">seaslog.use_buffer</a>
-   <a href="/seaslog/setup.html#" class="link">seaslog.buffer_size</a>
-   <a href="/seaslog/setup.html#" class="link">seaslog.buffer_disabled_in_cli</a>
-   <span class="methodname">SeasLog::getBuffer</span>
-   <span class="methodname">SeasLog::flushBuffer</span>

SeasLog::getDatetimeFormat
==========================

Get SeasLog datetime format style

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">SeasLog::getDatetimeFormat</span> ( <span
class="methodparam">void</span> )

Get SeasLog datetime format style. Use the Function <span
class="methodname">SeasLog::getDatetimeFormat</span> will get the value
of
<a href="/seaslog/setup.html#" class="link">seaslog.default_datetime_format</a>
what configured in php.ini(seaslog.ini).

### Parameters

This function has no parameters.

### Return Values

Get SeasLog datetime format style of
<a href="/seaslog/setup.html#" class="link">seaslog.default_datetime_format</a>.
Use the Function <span
class="methodname">SeasLog::setDatetimeFormat</span> will change this
value.

### Examples

**Example \#1 <span class="function">SeasLog::getDatetimeFormat</span>
example**

``` php
<?php

var_dump(SeasLog::getDateTimeFormat());
var_dump(SeasLog::setDateTimeFormat('Ymd His'));
var_dump(SeasLog::getDateTimeFormat());

?>
```

The above example will output something similar to:

    string(11) "Y-m-d H:i:s"
    bool(true)
    string(7) "Ymd His"

### See Also

-   <span class="methodname">SeasLog::setDatetimeFormat</span>

SeasLog::getLastLogger
======================

Get SeasLog last logger path

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">SeasLog::getLastLogger</span> ( <span
class="methodparam">void</span> )

Use the Function <span class="methodname">SeasLog::getLastLogger</span>
will get the value of
<a href="/seaslog/setup.html#" class="link">seaslog.default_logger</a>
what configured in php.ini(seaslog.ini).

### Parameters

This function has no parameters.

### Return Values

Use the Function <span class="methodname">SeasLog::setLogger</span> will
change the value of function <span
class="methodname">SeasLog::getLastLogger</span>.

### Examples

**Example \#1 <span class="function">SeasLog::getLastLogger</span>
example**

``` php
<?php

var_dump(SeasLog::getLastLogger());
SeasLog::setLogger('theNewLogger');
var_dump(SeasLog::getLastLogger());
?>
```

The above example will output something similar to:

    string(7) "default"
    string(12) "theNewLogger"

### See Also

-   <span class="methodname">SeasLog::setLogger</span>

SeasLog::getRequestID
=====================

Get SeasLog request\_id differentiated requests

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">string</span> <span
class="methodname">SeasLog::getRequestID</span> ( <span
class="methodparam">void</span> )

To distinguish a single request, such as not invoking the <span
class="methodname">SeasLog::setRequestId</span> function， the unique
value generated by the built-in \`static char \*get\_uniqid ()\`
function is used when the request is initialized.

### Parameters

This function has no parameters.

### Return Values

Return string generated by the built-in \`static char \*get\_uniqid ()\`
function, or setted by <span
class="methodname">SeasLog::setRequestId</span> function.

### Examples

**Example \#1 <span class="function">SeasLog::getRequestID</span>
example**

``` php
<?php

var_dump(SeasLog::getRequestID());
var_dump(SeasLog::setRequestID('reqeust_id_test_'.time()))
var_dump(SeasLog::getRequestID());

?>
```

The above example will output something similar to:

    string(13) "5b3f21a209519"
    bool(true)
    string(26) "reqeust_id_test_1530864034"

### See Also

-   <span class="methodname">SeasLog::setRequestID</span>
-   The Variable \`%Q\` in
    <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">Seaslog Default Variable Table</a>.

SeasLog::getRequestVariable
===========================

Get SeasLog request variable

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::getRequestVariable</span> ( <span
class="methodparam"><span class="type">int</span> `$key`</span> )

Get SeasLog request variable.

### Parameters

`key`  
Constant int.

-   <a href="/seaslog/constants.html#" class="link">SEASLOG_REQUEST_VARIABLE_DOMAIN_PORT</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_REQUEST_VARIABLE_REQUEST_URI</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_REQUEST_VARIABLE_REQUEST_METHOD</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_REQUEST_VARIABLE_CLIENT_IP</a>

### Return Values

Return request variable value on set success.

### Examples

**Example \#1 <span
class="methodname">SeasLog::getRequestVariable</span> example**

``` php
<?php

$sDomainPort = 'domain:port';
$sRequestUri = 'uri';
$sRequestMethod = 'method';
$sClientIp = 'client_ip';

$iErrorKey = 1000;

$oSeasLog = new SeasLog();

var_dump($oSeasLog->setRequestVariable(SEASLOG_REQUEST_VARIABLE_DOMAIN_PORT, $sDomainPort));
var_dump($oSeasLog->setRequestVariable(SEASLOG_REQUEST_VARIABLE_REQUEST_URI, $sRequestUri));
var_dump($oSeasLog->setRequestVariable(SEASLOG_REQUEST_VARIABLE_REQUEST_METHOD, $sRequestMethod));
var_dump($oSeasLog->setRequestVariable(SEASLOG_REQUEST_VARIABLE_CLIENT_IP, $sClientIp));

var_dump($oSeasLog->setRequestVariable($iErrorKey,NULL));

var_dump($oSeasLog->getRequestVariable(SEASLOG_REQUEST_VARIABLE_DOMAIN_PORT) == $sDomainPort);
var_dump($oSeasLog->getRequestVariable(SEASLOG_REQUEST_VARIABLE_REQUEST_URI) == $sRequestUri);
var_dump($oSeasLog->getRequestVariable(SEASLOG_REQUEST_VARIABLE_REQUEST_METHOD) == $sRequestMethod);
var_dump($oSeasLog->getRequestVariable(SEASLOG_REQUEST_VARIABLE_CLIENT_IP) == $sClientIp);

var_dump($oSeasLog->getRequestVariable($iErrorKey));

?>
```

The above example will output something similar to:


    bool(true)
    bool(true)
    bool(true)
    bool(true)
    bool(false)
    bool(true)
    bool(true)
    bool(true)
    bool(true)
    bool(false)

### See Also

-   <span class="methodname">SeasLog::setRequestVariable</span>

SeasLog::info
=============

Record info log information

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::info</span> ( <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\] )

Record info log information.

> **Note**:
>
> "INFO" - Interesting events.Emphasizes the running process of the
> application.

### Parameters

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::info</span> example**

``` php
<?php

var_dump(SeasLog::info('log message'));

//with content
var_dump(SeasLog::info('log message from {NAME}',array('NAME' => 'neeke')));

//with tmp logger
var_dump(SeasLog::info('log message from {NAME}',array('NAME' => 'neeke'),'tmp_logger'));

var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    array(2) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(81) "2018-07-07 11:45:49 | INFO | 73263 | 5b40376d1067c | 1530935149.68 | log message
    "
        [1]=>
        string(92) "2018-07-07 11:45:49 | INFO | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:45:49 | INFO | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::debug</span>
-   <span class="methodname">SeasLog::notice</span>
-   <span class="methodname">SeasLog::warning</span>
-   <span class="methodname">SeasLog::error</span>
-   <span class="methodname">SeasLog::critical</span>
-   <span class="methodname">SeasLog::alert</span>
-   <span class="methodname">SeasLog::emergency</span>
-   <span class="methodname">SeasLog::log</span>

SeasLog::log
============

The Common Record Log Function

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::log</span> ( <span class="methodparam"><span
class="type">string</span> `$level`</span> \[, <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\]\] )

The Common Record Log Function.

### Parameters

`level`  
Can use level in:

-   <a href="/seaslog/constants.html#" class="link">SEASLOG_DEBUG</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_INFO</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_NOTICE</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_WARNING</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_ERROR</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_CRITICAL</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_ALERT</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_EMERGENCY</a>

Or you can create a new level self-help.

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::log</span> example**

``` php
<?php

var_dump(SeasLog::log(SEASLOG_INFO,'info log'));
var_dump(SeasLog::getBuffer());

//create a new level self-help.
var_dump(SeasLog::log('MySelfLevel','info log'));
var_dump(SeasLog::getBuffer());

//with `content`
var_dump(SeasLog::log('MySelfLevel','info log {NAME}',array('NAME' => 'neeke')));
var_dump(SeasLog::getBuffer());

//with `logger`
var_dump(SeasLog::log('MySelfLevel','info log {NAME}',array('NAME' => 'neeke'),'tmp_logger'));
var_dump(SeasLog::getBuffer());


?>
```

The above example will output something similar to:

    bool(true)
    array(1) {
      ["/var/log/www/default/20180707.log"]=>
      array(1) {
        [0]=>
        string(79) "2018-07-07 11:12:37 | INFO | 72427 | 5b402fa56a2ea | 1530933157.436 | info log
    "
      }
    }

    bool(true)
    array(1) {
      ["/var/log/www/default/20180707.log"]=>
      array(1) {
        [0]=>
        string(86) "2018-07-07 11:13:59 | MySelfLevel | 72470 | 5b402ff781c5e | 1530933239.532 | info log
    "
      }
    }

    bool(true)
    array(1) {
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:28:12 | MySelfLevel | 72833 | 5b40334ce6a2f | 1530934092.946 | info log neeke
    "
      }
    }

    bool(true)
    array(1) {
      ["/var/log/www/default/20180707.log"]=>
      array(1) {
        [0]=>
        string(86) "2018-07-07 11:20:12 | INFO | 72616 | 5b40316c3641e | 1530933612.222 | info log neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::debug</span>
-   <span class="methodname">SeasLog::info</span>
-   <span class="methodname">SeasLog::notice</span>
-   <span class="methodname">SeasLog::warning</span>
-   <span class="methodname">SeasLog::error</span>
-   <span class="methodname">SeasLog::critical</span>
-   <span class="methodname">SeasLog::alert</span>
-   <span class="methodname">SeasLog::emergency</span>

SeasLog::notice
===============

Record notice log information

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::notice</span> ( <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\] )

Record notice log information.

> **Note**:
>
> "NOTICE" - Normal but significant events.Information that is more
> important than the INFO level during execution.

### Parameters

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::notice</span> example**

``` php
<?php

var_dump(SeasLog::notice('log message'));

//with content
var_dump(SeasLog::notice('log message from {NAME}',array('NAME' => 'neeke')));

//with tmp logger
var_dump(SeasLog::notice('log message from {NAME}',array('NAME' => 'neeke'),'tmp_logger'));

var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    array(2) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(81) "2018-07-07 11:45:49 | NOTICE | 73263 | 5b40376d1067c | 1530935149.68 | log message
    "
        [1]=>
        string(92) "2018-07-07 11:45:49 | NOTICE | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:45:49 | NOTICE | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::debug</span>
-   <span class="methodname">SeasLog::info</span>
-   <span class="methodname">SeasLog::warning</span>
-   <span class="methodname">SeasLog::error</span>
-   <span class="methodname">SeasLog::critical</span>
-   <span class="methodname">SeasLog::alert</span>
-   <span class="methodname">SeasLog::emergency</span>
-   <span class="methodname">SeasLog::log</span>

SeasLog::setBasePath
====================

Set SeasLog base path

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::setBasePath</span> ( <span
class="methodparam"><span class="type">string</span> `$base_path`</span>
)

Set SeasLog base path.

### Parameters

`base_path`  
String.

### Return Values

Return TRUE on setted base path success, FALSE on failure.

### Examples

**Example \#1 <span class="methodname">SeasLog::setBasePath</span>
example**

``` php
<?php

/* ... */

?>
```

The above example will output something similar to:

    ...

SeasLog::setDatetimeFormat
==========================

Set SeasLog datetime format style

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::setDatetimeFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

Set SeasLog datetime format style.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`format`  
String. Such as \`Y-m-d H:i:s\` or \`Ymd His\`. See also first param
\`format\` at <span class="function">date</span>.

### Return Values

Return TRUE on setted datetime format success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::setDatetimeFormat</span>
example**

``` php
<?php

var_dump(SeasLog::setDateTimeFormat('Ymd His'));

?>
```

The above example will output something similar to:

    bool(true)

### See Also

-   <span class="methodname">SeasLog::getDateTimeFormat</span>

SeasLog::setLogger
==================

Set SeasLog logger name

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::setLogger</span> ( <span
class="methodparam"><span class="type">string</span> `$logger`</span> )

Use the Function <span class="methodname">SeasLog::setLogger</span> will
change the value of function <span
class="methodname">SeasLog::getLastLogger</span>. Than's mean, SeasLog
will record loginfo into the logger directory.

### Parameters

`logger`  
Logger name.

### Return Values

Return TRUE on created logger disectory success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::setLogger</span> example**

``` php
<?php

var_dump(SeasLog::setLogger('testModule/testLogger'));

?>
```

The above example will output something similar to:

    bool(true)

### See Also

-   <span class="methodname">SeasLog::getLastLogger</span>
-   <span class="methodname">SeasLog::closeLoggerStream</span>

SeasLog::setRequestID
=====================

Set SeasLog request\_id differentiated requests

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::setRequestID</span> ( <span
class="methodparam"><span class="type">string</span>
`$request_id`</span> )

To distinguish a single request, such as not invoking the <span
class="methodname">SeasLog::setRequestId</span> function， the unique
value generated by the built-in \`static char \*get\_uniqid ()\`
function is used when the request is initialized.

### Parameters

`request_id`  
String.

### Return Values

Return TRUE on set request\_id success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::setRequestID</span>
example**

``` php
<?php

var_dump(SeasLog::setRequestID(time() . rand()));

?>
```

The above example will output something similar to:

    bool(true)

### See Also

-   <span class="methodname">SeasLog::getRequestID</span>

SeasLog::setRequestVariable
===========================

Manually set SeasLog request variable

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::setRequestVariable</span> ( <span
class="methodparam"><span class="type">int</span> `$key`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

Manually set SeasLog request variable.

### Parameters

`key`  
Constant int.

-   <a href="/seaslog/constants.html#" class="link">SEASLOG_REQUEST_VARIABLE_DOMAIN_PORT</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_REQUEST_VARIABLE_REQUEST_URI</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_REQUEST_VARIABLE_REQUEST_METHOD</a>
-   <a href="/seaslog/constants.html#" class="link">SEASLOG_REQUEST_VARIABLE_CLIENT_IP</a>

`value`  
The request variable value.

### Return Values

Return TRUE on set success, FALSE on failure.

### Examples

**Example \#1 <span
class="methodname">SeasLog::setRequestVariable</span> example**

``` php
<?php

$sDomainPort = 'domain:port';
$sRequestUri = 'uri';
$sRequestMethod = 'method';
$sClientIp = 'client_ip';

$iErrorKey = 1000;

$oSeasLog = new SeasLog();

var_dump($oSeasLog->setRequestVariable(SEASLOG_REQUEST_VARIABLE_DOMAIN_PORT, $sDomainPort));
var_dump($oSeasLog->setRequestVariable(SEASLOG_REQUEST_VARIABLE_REQUEST_URI, $sRequestUri));
var_dump($oSeasLog->setRequestVariable(SEASLOG_REQUEST_VARIABLE_REQUEST_METHOD, $sRequestMethod));
var_dump($oSeasLog->setRequestVariable(SEASLOG_REQUEST_VARIABLE_CLIENT_IP, $sClientIp));

var_dump($oSeasLog->setRequestVariable($iErrorKey,NULL));

var_dump($oSeasLog->getRequestVariable(SEASLOG_REQUEST_VARIABLE_DOMAIN_PORT) == $sDomainPort);
var_dump($oSeasLog->getRequestVariable(SEASLOG_REQUEST_VARIABLE_REQUEST_URI) == $sRequestUri);
var_dump($oSeasLog->getRequestVariable(SEASLOG_REQUEST_VARIABLE_REQUEST_METHOD) == $sRequestMethod);
var_dump($oSeasLog->getRequestVariable(SEASLOG_REQUEST_VARIABLE_CLIENT_IP) == $sClientIp);

var_dump($oSeasLog->getRequestVariable($iErrorKey));

?>
```

The above example will output something similar to:


    bool(true)
    bool(true)
    bool(true)
    bool(true)
    bool(false)
    bool(true)
    bool(true)
    bool(true)
    bool(true)
    bool(false)

### See Also

-   <span class="methodname">SeasLog::getRequestVariable</span>

SeasLog::warning
================

Record warning log information

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">SeasLog::warning</span> ( <span
class="methodparam"><span class="type">string</span> `$message`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">string</span> `$logger`</span> \]\] )

Record warning log information.

> **Note**:
>
> "WARNING" - Exceptional occurrences that are not errors. Potentially
> aberrant information that needs attention and needs to be repaired.

### Parameters

`message`  
The log message.

`content`  
The \`message\` contain placeholders which implementors replace with
values from content array. Sush as \`message\` is \`log info from
{NAME}\` and \`content\` is \`array('NAME' =\> neeke)\`, the log
information will \`log info from neeke\`.

`logger`  
The \`logger\` cased by the third param would be used right this right
now, like a temp logger, when the function SeasLog::setLogger() called
in pre content. If \`logger\` NULL or "", SeasLog will use lastest
logger setted by <span class="methodname">SeasLog::setLogger</span>.

### Return Values

Return TRUE on record log information success, FALSE on failure.

### Examples

**Example \#1 <span class="function">SeasLog::warning</span> example**

``` php
<?php

var_dump(SeasLog::warning('log message'));

//with content
var_dump(SeasLog::warning('log message from {NAME}',array('NAME' => 'neeke')));

//with tmp logger
var_dump(SeasLog::warning('log message from {NAME}',array('NAME' => 'neeke'),'tmp_logger'));

var_dump(SeasLog::getBuffer());

?>
```

The above example will output something similar to:

    bool(true)
    bool(true)
    bool(true)
    array(2) {
      ["/var/log/www/default/20180707.log"]=>
      array(2) {
        [0]=>
        string(81) "2018-07-07 11:45:49 | WARNING | 73263 | 5b40376d1067c | 1530935149.68 | log message
    "
        [1]=>
        string(92) "2018-07-07 11:45:49 | WARNING | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
      ["/var/log/www/tmp_logger/20180707.log"]=>
      array(1) {
        [0]=>
        string(92) "2018-07-07 11:45:49 | WARNING | 73263 | 5b40376d1067c | 1530935149.68 | log message from neeke
    "
      }
    }

### See Also

-   <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a>
-   <span class="methodname">SeasLog::debug</span>
-   <span class="methodname">SeasLog::info</span>
-   <span class="methodname">SeasLog::notice</span>
-   <span class="methodname">SeasLog::error</span>
-   <span class="methodname">SeasLog::critical</span>
-   <span class="methodname">SeasLog::alert</span>
-   <span class="methodname">SeasLog::emergency</span>
-   <span class="methodname">SeasLog::log</span>

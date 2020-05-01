Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/seaslog/setup.html#Requirements)
-   [Installation](/seaslog/setup.html#Installation)
-   [Runtime Configuration](/seaslog/setup.html#Runtime%20Configuration)
-   [Resource Types](/seaslog/setup.html#Resource%20Types)

Requirements
------------

Installation
------------

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/seaslog" class="link external">» https://pecl.php.net/package/seaslog</a>

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                                                         | Default                          | Changeable       | Changelog |
|--------------------------------------------------------------------------------------------------------------|----------------------------------|------------------|-----------|
| <a href="/seaslog/setup.html#" class="link">seaslog.appender</a>                                             | 1                                | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.appender_retry</a>                                       | 0                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.level</a>                                                | 8                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.remote_host</a>                                          | 127.0.0.1                        | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.remote_port</a>                                          | 514                              | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.remote_timeout</a>                                       | 1                                | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.default_basepath</a>                                     | /var/log/www                     | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.default_logger</a>                                       | default                          | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#Seaslog%20Default%20Variable%20Table" class="link">seaslog.default_template</a> | %T \| %L \| %P \| %Q \| %t \| %M | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.default_datetime_format</a>                              | Y-m-d H:i:s                      | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.trace_error</a>                                          | 1                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.trace_exception</a>                                      | 0                                | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.trace_notice</a>                                         | 0                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.trace_warning</a>                                        | 0                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.use_buffer</a>                                           | 0                                | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.buffer_size</a>                                          | 0                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.buffer_disabled_in_cli</a>                               | 0                                | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.disting_type</a>                                         | 0                                | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.disting_folder</a>                                       | 1                                | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.disting_by_hour</a>                                      | 0                                | PHP\_INI\_SYSTEM |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.recall_depth</a>                                         | 0                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.trim_wrap</a>                                            | 0                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.ignore_warning</a>                                       | 1                                | PHP\_INI\_ALL    |           |
| <a href="/seaslog/setup.html#" class="link">seaslog.throw_exception</a>                                      | 1                                | PHP\_INI\_ALL    |           |

Here's a short explanation of the configuration directives.

`seaslog.appender` <span class="type">integer</span>  
Switch the Record Log Data Store. 1File 2TCP 3UDP (Switch default 1)

SeasLog will send log to tcp://remote\_host:remote\_port or
udp://remote\_host:remote\_port server, when *seaslog.appender*
configured to \`2 (TCP)\` or \`3 (UDP)\`.

When *SeasLog* send log to TCP/UDP，style follow RFC5424. The
\`{logInfo}\` affected by *seaslog.default\_template*.

    The log style finally formatted such as:
    <15>1 2017-08-27T01:24:59+08:00 vagrant-ubuntu-trusty test/logger[27171]: 2016-06-25 00:59:43 | DEBUG | 21423 | 599157af4e937 | 1466787583.322 | this is a neeke debug
    <14>1 2017-08-27T01:24:59+08:00 vagrant-ubuntu-trusty test/logger[27171]: 2016-06-25 00:59:43 | INFO | 21423 | 599157af4e937 | 1466787583.323 | this is a info log
    <13>1 2017-08-27T01:24:59+08:00 vagrant-ubuntu-trusty test/logger[27171]: 2016-06-25 00:59:43 | NOTICE | 21423 | 599157af4e937 | 1466787583.324 | this is a notice log
        

`seaslog.appender_retry` <span class="type">integer</span>  
Record Log Retry Count. Default 0 (Do Not Retry)

`seaslog.buffer_disabled_in_cli` <span class="type">integer</span>  
Disable buffer in cli. 1-Y 0-N(Default)

Switch the configure buffer\_disabled\_in\_cli on. The
buffer\_disabled\_in\_cli switch default off. If switch
buffer\_disabled\_in\_cli on, and running in cli, seaslog.use\_buffer
setting will be discarded, Seaslog write to the Data Store IMMEDIATELY.

`seaslog.buffer_size` <span class="type">integer</span>  
Configure the buffer\_size with 100. The buffer\_size default 0, it’s
meaning don’t use buffer. If buffer\_size \> 0,SeasLog will rewritten
down into the Data Store when the prerecorded log in memory count \>=
this buffer\_size,and then refresh the memory poll.

`seaslog.default_basepath` <span class="type">string</span>  
Default Log Base Path. Defult "/var/log/www".

`seaslog.default_datetime_format` <span class="type">string</span>  
The DateTime Style. Default "Y-m-d H:i:s".

`seaslog.default_logger` <span class="type">string</span>  
Default Logger Path. Default "default".

`seaslog.disting_by_hour` <span class="type">integer</span>  
Switch use the logger with hour. 1-Y 0-N(Default)

> **Note**:
>
> *seaslog.disting\_by\_hour = 1* Switch use Logger DisTing by hour.
> It’s meaning SeasLog will create the file each one hour.

`seaslog.disting_folder` <span class="type">integer</span>  
Switch use the logger with folder. 1-Y(Default) 0-N

> **Note**:
>
> *seaslog.disting\_folder = 1* Switch use Logger DisTing by folder,
> it’s meaning SeasLog will create the file deistic by folder, and when
> this configure close SeasLog will create file use underline connect
> Logger and Time like default\_20180211.log.

`seaslog.disting_type` <span class="type">integer</span>  
Switch use the logger with type. 1-Y 0-N(Default)

> **Note**:
>
> *seaslog.disting\_type = 1* Switch use Logger DisTing by type, it’s
> meaning SeasLog will create the file deistic info\\warn\\error and the
> other type.

`seaslog.ignore_warning` <span class="type">integer</span>  
Switch ignore SeasLog warning. 1-On(Default) 0-Off

> **Note**:
>
> *seaslog.ignore\_warning = 1* Open a warning to ignore SeasLog itself.
> When directory permissions or receive server ports are blocked, they
> are ignored; when closed, a warning is thrown.

`seaslog.level` <span class="type">integer</span>  
Record logger level. Default 8 (All of them). 0-EMERGENCY 1-ALERT
2-CRITICAL 3-ERROR 4-WARNING 5-NOTICE 6-INFO 7-DEBUG 8-ALL

> **Note**:
>
> Tips: The configuration item has changed since the 1.7.0 version.
> Before the 1.7.0 version, the smaller the value, the more logs are
> taken according to the level: 0-all 1-debug 2-info 3-notice 4-warning
> 5-error 6-critical 7-alert 8-emergency Before the 1.7.0 version,
> Default 0 (All of them).

`seaslog.recall_depth` <span class="type">integer</span>  
Log function recall depth.Will affected variable \`LineNo\` in \`%F\`.
Default 0

`seaslog.remote_host` <span class="type">string</span>  
If you use Record TCP or UDP, configure this remote ip. Default
"127.0.0.1"

`seaslog.remote_port` <span class="type">integer</span>  
If you use Record TCP or UDP, configure this remote port. Default 514

`seaslog.remote_timeout` <span class="type">integer</span>  
If you use Record TCP or UDP, configure this remote timeout. Default 1
second

`seaslog.throw_exception` <span class="type">integer</span>  
Switch throw SeasLog exception. 1-On(Default) 0-Off

> **Note**:
>
> *seaslog.throw\_exception = 1* Open an exception that throws the
> SeasLog to throw itself. When the directory authority or the receive
> server port is blocked, throw an exception; do not throw an exception
> when closed.

`seaslog.trace_error` <span class="type">integer</span>  
Automatic Record final error with default logger. 1-Y(Default) 0-N

`seaslog.trace_exception` <span class="type">integer</span>  
Automatic Record exception with default logger. 1-Y 0-N(Default)

`seaslog.trace_notice` <span class="type">integer</span>  
Automatic Record notice with default logger. 1-Y 0-N(Default)

`seaslog.trace_warning` <span class="type">integer</span>  
Automatic Record warning with default logger. 1-Y 0-N(Default)

`seaslog.trim_wrap` <span class="type">integer</span>  
Trim the \\n and \\r in log message. 1-On 0-Off(Default)

`seaslog.use_buffer` <span class="type">integer</span>  
Switch use the log buffer with memory. 1-Y 0-N(Default)

> **Note**:
>
> *seaslog.use\_buffer = 1* Switch the configure use\_buffer on. The
> use\_buffer switch default off. If switch use\_buffer on, SeasLog
> prerecord the log with memory, and them would be rewritten down into
> the Data Store by request shutdown or php process exit (PHP RSHUTDOWN
> or PHP MSHUTDOWN).

`seaslog.default_template` <span class="type">string</span>  
Default Log template. Default "%T \| %L \| %P \| %Q \| %t \| %M".

> **Note**:
>
> \`SeasLog\`The following default variables are provided, which can be
> used directly in the log template and replaced as a corresponding
> value when the log is eventually generated.
>
> Default log template is:\`seaslog.default\_template = "%T \| %L \| %P
> \| %Q \| %t \| %M"\`, that's mean,default log style is:\`{dateTime} \|
> {level} \| {pid} \| {uniqid} \| {timeStamp} \| {logInfo}\`
>
> If you custom log template, such as:\`seaslog.default\_template =
> "\[%T\]:%L %P %Q %t %M" \`, that's will mean,log style was custom
> as:\`\[{dateTime}\]:{level} {pid} {uniqid} {timeStamp} {logInfo}\`
>
> | Variable Name | Description                                                                                                                                                                                                                                     |
> |---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
> | %L            | Level.                                                                                                                                                                                                                                          |
> | %M            | Message.                                                                                                                                                                                                                                        |
> | %T            | DateTime. Such as\`2017-08-16 19:15:02\`,affected by \`seaslog.default\_datetime\_format\`.                                                                                                                                                     |
> | %t            | Timestamp. Such as\`1502882102.862\`,accurate to milliseconds.                                                                                                                                                                                  |
> | %Q            | RequestId. To distinguish a single request, such as not invoking the \`SeasLog::setRequestId($string)\` function, the unique value generated by the built-in \`static char \*get\_uniqid ()\` function is used when the request is initialized. |
> | %H            | HostName.                                                                                                                                                                                                                                       |
> | %P            | ProcessId.                                                                                                                                                                                                                                      |
> | %D            | Domain:Port. Such as\`www.cloudwise.com:80\`; When Cli, Such as \`cli\`.                                                                                                                                                                        |
> | %R            | Request URI. Such as\`/app/user/signin\`; When Cli it's the index script, Such as \`CliIndex.php\`.                                                                                                                                             |
> | %m            | Request Method. Such as\`Get\`; When Cli it's the command script, Such as \`/bin/bash\`.                                                                                                                                                        |
> | %I            | Client IP; When Cli it's \`local\`. Priority value: HTTP\_X\_REAL\_IP \> HTTP\_X\_FORWARDED\_FOR \> REMOTE\_ADDR                                                                                                                                |
> | %F            | FileName:LineNo. Such as \`UserService.php:118\`.                                                                                                                                                                                               |
> | %U            | MemoryUsage. byte. Call \`zend\_memory\_usage\`.                                                                                                                                                                                                |
> | %u            | PeakMemoryUsage. byte. Call \`zend\_memory\_peak\_usage\`.                                                                                                                                                                                      |
> | %C            | \`TODO\` Class::Action. Such as \`UserService::getUserInfo\`                                                                                                                                                                                    |

Resource Types
--------------

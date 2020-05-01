swoole\_async\_dns\_lookup
==========================

Async and non-blocking hostname to IP lookup

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_async\_dns\_lookup</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
, <span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

### Parameters

`hostname`  
The host name.

`callback`  
<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
, <span class="methodparam"><span class="type">string</span>
`$ip`</span> )

`hostname`  
The host name.

`IP`  
The IP address.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

swoole\_async\_read
===================

Read file stream asynchronously

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_async\_read</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">int</span> `$chunk_size`<span class="initializer"> =
65536</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$offset`<span class="initializer"> =
0</span></span> \]\] )

### Parameters

`filename`  
The filename of the file being read.

`callback`  
<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">string</span>
`$content`</span> )

`filename`  
The name of the file.

`content`  
The content readed from the file stream.

`chunk_size`  
The chunk length.

`offset`  
The offset.

### Return Values

Whether the read is succeed.

swoole\_async\_readfile
=======================

Read a file asynchronously

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_async\_readfile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">callable</span>
`$callback`</span> )

### Parameters

`filename`  
The filename of the file being read.

`callback`  
<span class="type">mixed</span> <span class="methodname"><span
class="replaceable">callback</span></span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">string</span>
`$content`</span> )

`filename`  
The name of the file.

`content`  
The content readed from the file.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

swoole\_async\_set
==================

Update the async I/O options

### Description

<span class="type">void</span> <span
class="methodname">swoole\_async\_set</span> ( <span
class="methodparam"><span class="type">array</span> `$settings`</span> )

### Parameters

`settings`  

swoole\_async\_write
====================

Write data to a file stream asynchronously

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_async\_write</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">string</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">integer</span> `$offset`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> \]\] )

### Parameters

`filename`  
The filename being written.

`content`  
The content writing to the file.

`offset`  
The offset.

`callback`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

swoole\_async\_writefile
========================

Write data to a file asynchronously

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_async\_writefile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">string</span>
`$content`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$callback`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \]\] )

### Parameters

`filename`  
The filename being written.

`content`  
The content writing to the file.

`callback`  

`flags`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

swoole\_client\_select
======================

Get the file description which are ready to read/write or error

### Description

<span class="type">int</span> <span
class="methodname">swoole\_client\_select</span> ( <span
class="methodparam"><span class="type">array</span>
`&$read_array`</span> , <span class="methodparam"><span
class="type">array</span> `&$write_array`</span> , <span
class="methodparam"><span class="type">array</span>
`&$error_array`</span> \[, <span class="methodparam"><span
class="type">float</span> `$timeout`<span class="initializer"> =
0.5</span></span> \] )

### Parameters

`read_array`  

`write_array`  

`error_array`  

`timeout`  

### Return Values

swoole\_cpu\_num
================

Get the number of CPU

### Description

<span class="type">int</span> <span
class="methodname">swoole\_cpu\_num</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The number of CPU.

swoole\_errno
=============

Get the error code of the latest system call

### Description

<span class="type">int</span> <span
class="methodname">swoole\_errno</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

swoole\_event\_add
==================

Add new callback functions of a socket into the EventLoop

### Description

<span class="type">int</span> <span
class="methodname">swoole\_event\_add</span> ( <span
class="methodparam"><span class="type">int</span> `$fd`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$read_callback`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$write_callback`</span> \[, <span
class="methodparam"><span class="type">int</span> `$events`<span
class="initializer"> = 0</span></span> \]\]\] )

### Parameters

`fd`  

`read_callback`  

`write_callback`  

`events`  

### Return Values

swoole\_event\_defer
====================

Add callback function to the next event loop

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_event\_defer</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

### Parameters

`callback`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

swoole\_event\_del
==================

Remove all event callback functions of a socket

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_event\_del</span> ( <span
class="methodparam"><span class="type">int</span> `$fd`</span> )

### Parameters

`fd`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

swoole\_event\_exit
===================

Exit the eventloop, only available at the client side

### Description

<span class="type">void</span> <span
class="methodname">swoole\_event\_exit</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

swoole\_event\_set
==================

Update the event callback functions of a socket

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_event\_set</span> ( <span
class="methodparam"><span class="type">int</span> `$fd`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$read_callback`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$write_callback`</span> \[, <span
class="methodparam"><span class="type">int</span> `$events`<span
class="initializer"> = 0</span></span> \]\]\] )

### Parameters

`fd`  

`read_callback`  

`write_callback`  

`events`  

### Return Values

swoole\_event\_wait
===================

Start the event loop

### Description

<span class="type">void</span> <span
class="methodname">swoole\_event\_wait</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

swoole\_event\_write
====================

Write data to a socket

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_event\_write</span> ( <span
class="methodparam"><span class="type">int</span> `$fd`</span> , <span
class="methodparam"><span class="type">string</span> `$data`</span> )

### Parameters

`fd`  

`data`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

swoole\_get\_local\_ip
======================

Get the IPv4 IP addresses of each NIC on the machine

### Description

<span class="type">array</span> <span
class="methodname">swoole\_get\_local\_ip</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

swoole\_last\_error
===================

Get the lastest error message

### Description

<span class="type">int</span> <span
class="methodname">swoole\_last\_error</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

swoole\_load\_module
====================

Load a swoole extension

### Description

<span class="type">mixed</span> <span
class="methodname">swoole\_load\_module</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

### Parameters

This function has no parameters.

### Return Values

swoole\_select
==============

Select the file descriptions which are ready to read/write or error in
the eventloop

### Description

<span class="type">int</span> <span
class="methodname">swoole\_select</span> ( <span
class="methodparam"><span class="type">array</span>
`&$read_array`</span> , <span class="methodparam"><span
class="type">array</span> `&$write_array`</span> , <span
class="methodparam"><span class="type">array</span>
`&$error_array`</span> \[, <span class="methodparam"><span
class="type">float</span> `$timeout`</span> \] )

### Parameters

`read_array`  

`write_array`  

`error_array`  

`timeout`  

### Return Values

swoole\_set\_process\_name
==========================

Set the process name

### Description

<span class="type">void</span> <span
class="methodname">swoole\_set\_process\_name</span> ( <span
class="methodparam"><span class="type">string</span>
`$process_name`</span> \[, <span class="methodparam"><span
class="type">int</span> `$size`<span class="initializer"> =
128</span></span> \] )

### Parameters

`process_name`  

### Return Values

swoole\_strerror
================

Convert the Errno into error messages

### Description

<span class="type">string</span> <span
class="methodname">swoole\_strerror</span> ( <span
class="methodparam"><span class="type">int</span> `$errno`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$error_type`<span class="initializer"> = 0</span></span> \] )

### Parameters

`errno`  

### Return Values

swoole\_timer\_after
====================

Trigger a one time callback function in the future

### Description

<span class="type">int</span> <span
class="methodname">swoole\_timer\_after</span> ( <span
class="methodparam"><span class="type">int</span> `$ms`</span> , <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$param`</span> \] )

### Parameters

`ms`  

`callback`  

`param`  

### Return Values

swoole\_timer\_exists
=====================

Check if a timer callback function is existed

### Description

<span class="type">bool</span> <span
class="methodname">swoole\_timer\_exists</span> ( <span
class="methodparam"><span class="type">int</span> `$timer_id`</span> )

### Parameters

`timer_id`  

### Return Values

swoole\_timer\_tick
===================

Trigger a timer tick callback function by time interval

### Description

<span class="type">int</span> <span
class="methodname">swoole\_timer\_tick</span> ( <span
class="methodparam"><span class="type">int</span> `$ms`</span> , <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$param`</span> \] )

### Parameters

`ms`  

`callback`  

### Return Values

swoole\_version
===============

Get the version of Swoole

### Description

<span class="type">string</span> <span
class="methodname">swoole\_version</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

The version of Swoole.

**Table of Contents**

-   [swoole\_async\_dns\_lookup](/ref/swoole-funcs.html#swoole_async_dns_lookup)
    — Async and non-blocking hostname to IP lookup
-   [swoole\_async\_read](/ref/swoole-funcs.html#swoole_async_read) —
    Read file stream asynchronously
-   [swoole\_async\_readfile](/ref/swoole-funcs.html#swoole_async_readfile)
    — Read a file asynchronously
-   [swoole\_async\_set](/ref/swoole-funcs.html#swoole_async_set) —
    Update the async I/O options
-   [swoole\_async\_write](/ref/swoole-funcs.html#swoole_async_write) —
    Write data to a file stream asynchronously
-   [swoole\_async\_writefile](/ref/swoole-funcs.html#swoole_async_writefile)
    — Write data to a file asynchronously
-   [swoole\_client\_select](/ref/swoole-funcs.html#swoole_client_select)
    — Get the file description which are ready to read/write or error
-   [swoole\_cpu\_num](/ref/swoole-funcs.html#swoole_cpu_num) — Get the
    number of CPU
-   [swoole\_errno](/ref/swoole-funcs.html#swoole_errno) — Get the error
    code of the latest system call
-   [swoole\_event\_add](/ref/swoole-funcs.html#swoole_event_add) — Add
    new callback functions of a socket into the EventLoop
-   [swoole\_event\_defer](/ref/swoole-funcs.html#swoole_event_defer) —
    Add callback function to the next event loop
-   [swoole\_event\_del](/ref/swoole-funcs.html#swoole_event_del) —
    Remove all event callback functions of a socket
-   [swoole\_event\_exit](/ref/swoole-funcs.html#swoole_event_exit) —
    Exit the eventloop, only available at the client side
-   [swoole\_event\_set](/ref/swoole-funcs.html#swoole_event_set) —
    Update the event callback functions of a socket
-   [swoole\_event\_wait](/ref/swoole-funcs.html#swoole_event_wait) —
    Start the event loop
-   [swoole\_event\_write](/ref/swoole-funcs.html#swoole_event_write) —
    Write data to a socket
-   [swoole\_get\_local\_ip](/ref/swoole-funcs.html#swoole_get_local_ip)
    — Get the IPv4 IP addresses of each NIC on the machine
-   [swoole\_last\_error](/ref/swoole-funcs.html#swoole_last_error) —
    Get the lastest error message
-   [swoole\_load\_module](/ref/swoole-funcs.html#swoole_load_module) —
    Load a swoole extension
-   [swoole\_select](/ref/swoole-funcs.html#swoole_select) — Select the
    file descriptions which are ready to read/write or error in the
    eventloop
-   [swoole\_set\_process\_name](/ref/swoole-funcs.html#swoole_set_process_name)
    — Set the process name
-   [swoole\_strerror](/ref/swoole-funcs.html#swoole_strerror) — Convert
    the Errno into error messages
-   [swoole\_timer\_after](/ref/swoole-funcs.html#swoole_timer_after) —
    Trigger a one time callback function in the future
-   [swoole\_timer\_exists](/ref/swoole-funcs.html#swoole_timer_exists)
    — Check if a timer callback function is existed
-   [swoole\_timer\_tick](/ref/swoole-funcs.html#swoole_timer_tick) —
    Trigger a timer tick callback function by time interval
-   [swoole\_version](/ref/swoole-funcs.html#swoole_version) — Get the
    version of Swoole

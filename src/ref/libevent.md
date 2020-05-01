event\_add
==========

Add an event to the set of monitored events

### Description

<span class="type">bool</span> <span
class="methodname">event\_add</span> ( <span class="methodparam"><span
class="type">resource</span> `$event`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = -1</span></span> \] )

<span class="function">event\_add</span> schedules the execution of the
`event` when the event specified in <span
class="function">event\_set</span> occurs or in at least the time
specified by the `timeout` argument. If `timeout` was not specified, not
timeout is set. The `event` must be already initalized by <span
class="function">event\_set</span> and <span
class="function">event\_base\_set</span> functions. If the `event`
already has a timeout set, it is replaced by the new one.

### Parameters

`event`  
Valid event resource.

`timeout`  
Optional timeout (in microseconds).

### Return Values

<span class="function">event\_add</span> returns **`TRUE`** on success
or **`FALSE`** on error.

event\_base\_free
=================

Destroy event base

### Description

<span class="type">void</span> <span
class="methodname">event\_base\_free</span> ( <span
class="methodparam"><span class="type">resource</span>
`$event_base`</span> )

Destroys the specified `event_base` and frees all the resources
associated. Note that it's not possible to destroy an event base with
events attached to it.

### Parameters

`event_base`  
Valid event base resource.

event\_base\_loop
=================

Handle events

### Description

<span class="type">int</span> <span
class="methodname">event\_base\_loop</span> ( <span
class="methodparam"><span class="type">resource</span>
`$event_base`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \] )

Starts event loop for the specified event base.

### Parameters

`event_base`  
Valid event base resource.

`flags`  
Optional parameter, which can take any combination of **`EVLOOP_ONCE`**
and **`EVLOOP_NONBLOCK`**.

### Return Values

<span class="function">event\_base\_loop</span> returns 0 on success, -1
on error and 1 if no events were registered.

event\_base\_loopbreak
======================

Abort event loop

### Description

<span class="type">bool</span> <span
class="methodname">event\_base\_loopbreak</span> ( <span
class="methodparam"><span class="type">resource</span>
`$event_base`</span> )

Abort the active event loop immediately. The behaviour is similar to
*break* statement.

### Parameters

`event_base`  
Valid event base resource.

### Return Values

<span class="function">event\_base\_loopbreak</span> returns **`TRUE`**
on success or **`FALSE`** on error.

event\_base\_loopexit
=====================

Exit loop after a time

### Description

<span class="type">bool</span> <span
class="methodname">event\_base\_loopexit</span> ( <span
class="methodparam"><span class="type">resource</span>
`$event_base`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timeout`<span class="initializer"> =
-1</span></span> \] )

The next event loop iteration after the given timer expires will
complete normally, then exit without blocking for events again.

### Parameters

`event_base`  
Valid event base resource.

`timeout`  
Optional timeout parameter (in microseconds).

### Return Values

<span class="function">event\_base\_loopexit</span> returns **`TRUE`**
on success or **`FALSE`** on error.

event\_base\_new
================

Create and initialize new event base

### Description

<span class="type">resource</span> <span
class="methodname">event\_base\_new</span> ( <span
class="methodparam">void</span> )

Returns new event base, which can be used later in <span
class="function">event\_base\_set</span>, <span
class="function">event\_base\_loop</span> and other functions.

### Parameters

This function has no parameters.

### Return Values

<span class="function">event\_base\_new</span> returns valid event base
resource on success or **`FALSE`** on error.

event\_base\_priority\_init
===========================

Set the number of event priority levels

### Description

<span class="type">bool</span> <span
class="methodname">event\_base\_priority\_init</span> ( <span
class="methodparam"><span class="type">resource</span>
`$event_base`</span> , <span class="methodparam"><span
class="type">int</span> `$npriorities`</span> )

Sets the number of different event priority levels.

By default all events are scheduled with the same priority
(`npriorities`/2). Using <span
class="function">event\_base\_priority\_init</span> you can change the
number of event priority levels and then set a desired priority for each
event.

### Parameters

`event_base`  
Valid event base resource.

`npriorities`  
The number of event priority levels.

### Return Values

<span class="function">event\_base\_priority\_init</span> returns
**`TRUE`** on success or **`FALSE`** on error.

event\_base\_reinit
===================

Reinitialize the event base after a fork

### Description

<span class="type">bool</span> <span
class="methodname">event\_base\_reinit</span> ( <span
class="methodparam"><span class="type">resource</span>
`$event_base`</span> )

Some event mechanisms do not survive across fork. The `event_base` needs
to be reinitialized with this function.

### Parameters

`event_base`  
Valid event base resource that needs to be re-initialized.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

event\_base\_set
================

Associate event base with an event

### Description

<span class="type">bool</span> <span
class="methodname">event\_base\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$event`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$event_base`</span> )

Associates the `event_base` with the `event`.

### Parameters

`event`  
Valid event resource.

`event_base`  
Valid event base resource.

### Return Values

<span class="function">event\_base\_set</span> returns **`TRUE`** on
success or **`FALSE`** on error.

event\_buffer\_base\_set
========================

Associate buffered event with an event base

### Description

<span class="type">bool</span> <span
class="methodname">event\_buffer\_base\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">resource</span>
`$event_base`</span> )

Assign the specified `bevent` to the `event_base`.

### Parameters

`bevent`  
Valid buffered event resource.

`event_base`  
Valid event base resource.

### Return Values

<span class="function">event\_buffer\_base\_set</span> returns
**`TRUE`** on success or **`FALSE`** on error.

event\_buffer\_disable
======================

Disable a buffered event

### Description

<span class="type">bool</span> <span
class="methodname">event\_buffer\_disable</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">int</span>
`$events`</span> )

Disables the specified buffered event.

### Parameters

`bevent`  
Valid buffered event resource.

`events`  
Any combination of **`EV_READ`** and **`EV_WRITE`**.

### Return Values

<span class="function">event\_buffer\_disable</span> returns **`TRUE`**
on success or **`FALSE`** on error.

event\_buffer\_enable
=====================

Enable a buffered event

### Description

<span class="type">bool</span> <span
class="methodname">event\_buffer\_enable</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">int</span>
`$events`</span> )

Enables the specified buffered event.

### Parameters

`bevent`  
Valid buffered event resource.

`events`  
Any combination of **`EV_READ`** and **`EV_WRITE`**.

### Return Values

<span class="function">event\_buffer\_enable</span> returns **`TRUE`**
on success or **`FALSE`** on error.

event\_buffer\_fd\_set
======================

Change a buffered event file descriptor

### Description

<span class="type">void</span> <span
class="methodname">event\_buffer\_fd\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">resource</span>
`$fd`</span> )

Changes the file descriptor on which the buffered event operates.

### Parameters

`bevent`  
Valid buffered event resource.

`fd`  
Valid PHP stream, must be castable to file descriptor.

event\_buffer\_free
===================

Destroy buffered event

### Description

<span class="type">void</span> <span
class="methodname">event\_buffer\_free</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
)

Destroys the specified buffered event and frees all the resources
associated.

### Parameters

`bevent`  
Valid buffered event resource.

event\_buffer\_new
==================

Create new buffered event

### Description

<span class="type">resource</span> <span
class="methodname">event\_buffer\_new</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$readcb`</span> , <span class="methodparam"><span
class="type">mixed</span> `$writecb`</span> , <span
class="methodparam"><span class="type">mixed</span> `$errorcb`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$arg`</span> \] )

Libevent provides an abstraction layer on top of the regular event API.
Using buffered event you don't need to deal with the I/O manually,
instead it provides input and output buffers that get filled and drained
automatically.

### Parameters

`stream`  
Valid PHP stream resource. Must be castable to file descriptor.

`readcb`  
Callback to invoke where there is data to read, or <span
class="type">NULL</span> if no callback is desired.

`writecb`  
Callback to invoke where the descriptor is ready for writing, or <span
class="type">NULL</span> if no callback is desired.

`errorcb`  
Callback to invoke where there is an error on the descriptor, cannot be
<span class="type">NULL</span>.

`arg`  
An argument that will be passed to each of the callbacks (optional).

### Return Values

<span class="function">event\_buffer\_new</span> returns new buffered
event resource on success or **`FALSE`** on error.

event\_buffer\_priority\_set
============================

Assign a priority to a buffered event

### Description

<span class="type">bool</span> <span
class="methodname">event\_buffer\_priority\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">int</span>
`$priority`</span> )

Assign a priority to the `bevent`.

### Parameters

`bevent`  
Valid buffered event resource.

`priority`  
Priority level. Cannot be less than zero and cannot exceed maximum
priority level of the event base (see <span
class="function">event\_base\_priority\_init</span>).

### Return Values

<span class="function">event\_buffer\_priority\_set</span> returns
**`TRUE`** on success or **`FALSE`** on error.

event\_buffer\_read
===================

Read data from a buffered event

### Description

<span class="type">string</span> <span
class="methodname">event\_buffer\_read</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">int</span>
`$data_size`</span> )

Reads data from the input buffer of the buffered event.

### Parameters

`bevent`  
Valid buffered event resource.

`data_size`  
Data size in bytes.

event\_buffer\_set\_callback
============================

Set or reset callbacks for a buffered event

### Description

<span class="type">bool</span> <span
class="methodname">event\_buffer\_set\_callback</span> ( <span
class="methodparam"><span class="type">resource</span> `$event`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$readcb`</span> , <span class="methodparam"><span
class="type">mixed</span> `$writecb`</span> , <span
class="methodparam"><span class="type">mixed</span> `$errorcb`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$arg`</span> \] )

Sets or changes existing callbacks for the buffered `event`.

### Parameters

`event`  
Valid buffered event resource.

`readcb`  
Callback to invoke where there is data to read, or <span
class="type">NULL</span> if no callback is desired.

`writecb`  
Callback to invoke where the descriptor is ready for writing, or <span
class="type">NULL</span> if no callback is desired.

`errorcb`  
Callback to invoke where there is an error on the descriptor, cannot be
<span class="type">NULL</span>.

`arg`  
An argument that will be passed to each of the callbacks (optional).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

event\_buffer\_timeout\_set
===========================

Set read and write timeouts for a buffered event

### Description

<span class="type">void</span> <span
class="methodname">event\_buffer\_timeout\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">int</span>
`$read_timeout`</span> , <span class="methodparam"><span
class="type">int</span> `$write_timeout`</span> )

Sets the read and write timeouts for the specified buffered event.

### Parameters

`bevent`  
Valid buffered event resource.

`read_timeout`  
Read timeout (in seconds).

`write_timeout`  
Write timeout (in seconds).

event\_buffer\_watermark\_set
=============================

Set the watermarks for read and write events

### Description

<span class="type">void</span> <span
class="methodname">event\_buffer\_watermark\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">int</span>
`$events`</span> , <span class="methodparam"><span
class="type">int</span> `$lowmark`</span> , <span
class="methodparam"><span class="type">int</span> `$highmark`</span> )

Sets the watermarks for read and write events. Libevent does not invoke
read callback unless there is at least `lowmark` bytes in the input
buffer; if the read buffer is beyond the `highmark`, reading is stopped.
On output, the write callback is invoked whenever the buffered data
falls below the `lowmark`.

### Parameters

`bevent`  
Valid buffered event resource.

`events`  
Any combination of **`EV_READ`** and **`EV_WRITE`**.

`lowmark`  
Low watermark.

`highmark`  
High watermark.

event\_buffer\_write
====================

Write data to a buffered event

### Description

<span class="type">bool</span> <span
class="methodname">event\_buffer\_write</span> ( <span
class="methodparam"><span class="type">resource</span> `$bevent`</span>
, <span class="methodparam"><span class="type">string</span>
`$data`</span> \[, <span class="methodparam"><span
class="type">int</span> `$data_size`<span class="initializer"> =
-1</span></span> \] )

Writes data to the specified buffered event. The data is appended to the
output buffer and written to the descriptor when it becomes available
for writing.

### Parameters

`bevent`  
Valid buffered event resource.

`data`  
The data to be written.

`data_size`  
Optional size parameter. <span
class="function">event\_buffer\_write</span> writes all the `data` by
default.

### Return Values

<span class="function">event\_buffer\_write</span> returns **`TRUE`** on
success or **`FALSE`** on error.

event\_del
==========

Remove an event from the set of monitored events

### Description

<span class="type">bool</span> <span
class="methodname">event\_del</span> ( <span class="methodparam"><span
class="type">resource</span> `$event`</span> )

Cancels the `event`.

### Parameters

`event`  
Valid event resource.

### Return Values

<span class="function">event\_del</span> returns **`TRUE`** on success
or **`FALSE`** on error.

event\_free
===========

Free event resource

### Description

<span class="type">void</span> <span
class="methodname">event\_free</span> ( <span class="methodparam"><span
class="type">resource</span> `$event`</span> )

Frees previously created event resource.

### Parameters

`event`  
Valid event resource.

event\_new
==========

Create new event

### Description

<span class="type">resource</span> <span
class="methodname">event\_new</span> ( <span
class="methodparam">void</span> )

Creates and returns a new event resource.

### Return Values

<span class="function">event\_new</span> returns a new event resource on
success or **`FALSE`** on error.

event\_priority\_set
====================

Assign a priority to an event

### Description

<span class="type">bool</span> <span
class="methodname">event\_priority\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$event`</span> ,
<span class="methodparam"><span class="type">int</span>
`$priority`</span> )

Assign a priority to the `event`.

### Parameters

`event`  
Valid event resource.

`priority`  
Priority level. Cannot be less than zero and cannot exceed maximum
priority level of the event base (see <span
class="function">event\_base\_priority\_init</span>).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

event\_set
==========

Prepare an event

### Description

<span class="type">bool</span> <span
class="methodname">event\_set</span> ( <span class="methodparam"><span
class="type">resource</span> `$event`</span> , <span
class="methodparam"><span class="type">mixed</span> `$fd`</span> , <span
class="methodparam"><span class="type">int</span> `$events`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$arg`</span> \] )

Prepares the event to be used in <span
class="function">event\_add</span>. The event is prepared to call the
function specified by the `callback` on the events specified in
parameter `events`, which is a set of the following flags:
**`EV_TIMEOUT`**, **`EV_SIGNAL`**, **`EV_READ`**, **`EV_WRITE`** and
**`EV_PERSIST`**.

If **`EV_SIGNAL`** bit is set in parameter `events`, the `fd` is
interpreted as signal number.

After initializing the event, use <span
class="function">event\_base\_set</span> to associate the event with its
event base.

In case of matching event, these three arguments are passed to the
`callback` function:

`fd`  
Signal number or resource indicating the stream.

`events`  
A flag indicating the event. Consists of the following flags:
**`EV_TIMEOUT`**, **`EV_SIGNAL`**, **`EV_READ`**, **`EV_WRITE`** and
**`EV_PERSIST`**.

`arg`  
Optional parameter, previously passed to <span
class="function">event\_set</span> as `arg`.

### Parameters

`event`  
Valid event resource.

`fd`  
Valid PHP stream resource. The stream must be castable to file
descriptor, so you most likely won't be able to use any of filtered
streams.

`events`  
A set of flags indicating the desired event, can be **`EV_READ`** and/or
**`EV_WRITE`**. The additional flag **`EV_PERSIST`** makes the event to
persist until <span class="function">event\_del</span> is called,
otherwise the callback is invoked only once.

`callback`  
Callback function to be called when the matching event occurs.

`arg`  
Optional callback parameter.

### Return Values

<span class="function">event\_set</span> returns **`TRUE`** on success
or **`FALSE`** on error.

### Changelog

| Version | Description                        |
|---------|------------------------------------|
| 0.0.4   | **`EV_SIGNAL`** support was added. |

event\_timer\_add
=================

Alias of <span class="function">event\_add</span>

### Description

This function is an alias of: <span class="function">event\_add</span>.

event\_timer\_del
=================

Alias of <span class="function">event\_del</span>

### Description

This function is an alias of: <span class="function">event\_del</span>.

event\_timer\_new
=================

Alias of <span class="function">event\_new</span>

### Description

This function is an alias of: <span class="function">event\_new</span>.

event\_timer\_set
=================

Prepare a timer event

### Description

<span class="type">bool</span> <span
class="methodname">event\_timer\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$event`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$arg`</span> \] )

Prepares the timer event to be used in <span
class="function">event\_add</span>. The event is prepared to call the
function specified by the `callback` when the event timeout elapses.

After initializing the event, use <span
class="function">event\_base\_set</span> to associate the event with its
event base.

In case of matching event, these three arguments are passed to the
`callback` function:

`fd`  
Signal number or resource indicating the stream.

`events`  
A flag indicating the event. This will always be **`EV_TIMEOUT`** for
timer events.

`arg`  
Optional parameter, previously passed to <span
class="function">event\_timer\_set</span> as `arg`.

### Parameters

`event`  
Valid event resource.

`callback`  
Callback function to be called when the matching event occurs.

`arg`  
Optional callback parameter.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

**Table of Contents**

-   [event\_add](/ref/libevent.html#event_add) — Add an event to the set
    of monitored events
-   [event\_base\_free](/ref/libevent.html#event_base_free) — Destroy
    event base
-   [event\_base\_loop](/ref/libevent.html#event_base_loop) — Handle
    events
-   [event\_base\_loopbreak](/ref/libevent.html#event_base_loopbreak) —
    Abort event loop
-   [event\_base\_loopexit](/ref/libevent.html#event_base_loopexit) —
    Exit loop after a time
-   [event\_base\_new](/ref/libevent.html#event_base_new) — Create and
    initialize new event base
-   [event\_base\_priority\_init](/ref/libevent.html#event_base_priority_init)
    — Set the number of event priority levels
-   [event\_base\_reinit](/ref/libevent.html#event_base_reinit) —
    Reinitialize the event base after a fork
-   [event\_base\_set](/ref/libevent.html#event_base_set) — Associate
    event base with an event
-   [event\_buffer\_base\_set](/ref/libevent.html#event_buffer_base_set)
    — Associate buffered event with an event base
-   [event\_buffer\_disable](/ref/libevent.html#event_buffer_disable) —
    Disable a buffered event
-   [event\_buffer\_enable](/ref/libevent.html#event_buffer_enable) —
    Enable a buffered event
-   [event\_buffer\_fd\_set](/ref/libevent.html#event_buffer_fd_set) —
    Change a buffered event file descriptor
-   [event\_buffer\_free](/ref/libevent.html#event_buffer_free) —
    Destroy buffered event
-   [event\_buffer\_new](/ref/libevent.html#event_buffer_new) — Create
    new buffered event
-   [event\_buffer\_priority\_set](/ref/libevent.html#event_buffer_priority_set)
    — Assign a priority to a buffered event
-   [event\_buffer\_read](/ref/libevent.html#event_buffer_read) — Read
    data from a buffered event
-   [event\_buffer\_set\_callback](/ref/libevent.html#event_buffer_set_callback)
    — Set or reset callbacks for a buffered event
-   [event\_buffer\_timeout\_set](/ref/libevent.html#event_buffer_timeout_set)
    — Set read and write timeouts for a buffered event
-   [event\_buffer\_watermark\_set](/ref/libevent.html#event_buffer_watermark_set)
    — Set the watermarks for read and write events
-   [event\_buffer\_write](/ref/libevent.html#event_buffer_write) —
    Write data to a buffered event
-   [event\_del](/ref/libevent.html#event_del) — Remove an event from
    the set of monitored events
-   [event\_free](/ref/libevent.html#event_free) — Free event resource
-   [event\_new](/ref/libevent.html#event_new) — Create new event
-   [event\_priority\_set](/ref/libevent.html#event_priority_set) —
    Assign a priority to an event
-   [event\_set](/ref/libevent.html#event_set) — Prepare an event
-   [event\_timer\_add](/ref/libevent.html#event_timer_add) — Alias of
    event\_add
-   [event\_timer\_del](/ref/libevent.html#event_timer_del) — Alias of
    event\_del
-   [event\_timer\_new](/ref/libevent.html#event_timer_new) — Alias of
    event\_new
-   [event\_timer\_set](/ref/libevent.html#event_timer_set) — Prepare a
    timer event

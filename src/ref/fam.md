fam\_cancel\_monitor
====================

Terminate monitoring

### Description

<span class="type">bool</span> <span
class="methodname">fam\_cancel\_monitor</span> ( <span
class="methodparam"><span class="type">resource</span> `$fam`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$fam_monitor`</span> )

Terminates monitoring on a resource.

In addition an **`FAMAcknowledge`** event occurs.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

`fam_monitor`  
A resource returned by one of the *fam\_monitor\_XXX* functions

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">fam\_monitor\_file</span>
-   <span class="function">fam\_monitor\_directory</span>
-   <span class="function">fam\_monitor\_collection</span>
-   <span class="function">fam\_suspend\_monitor</span>

fam\_close
==========

Close FAM connection

### Description

<span class="type">void</span> <span
class="methodname">fam\_close</span> ( <span class="methodparam"><span
class="type">resource</span> `$fam`</span> )

Closes a connection to the FAM service.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

### Return Values

No value is returned.

### See Also

-   <span class="function">fam\_monitor\_open</span>

fam\_monitor\_collection
========================

Monitor a collection of files in a directory for changes

### Description

<span class="type">resource</span> <span
class="methodname">fam\_monitor\_collection</span> ( <span
class="methodparam"><span class="type">resource</span> `$fam`</span> ,
<span class="methodparam"><span class="type">string</span>
`$dirname`</span> , <span class="methodparam"><span
class="type">int</span> `$depth`</span> , <span
class="methodparam"><span class="type">string</span> `$mask`</span> )

Requests monitoring for a collection of files within a directory.

A FAM event will be generated whenever the status of the files change.
The possible event codes are described in detail in the
<a href="/fam/constants.html" class="link">constants part</a> of this
section.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

`dirname`  
Directory path to the monitored files

`depth`  
The maximum search `depth` starting from this directory

`mask`  
A shell pattern `mask` restricting the file names to look for

### Return Values

Returns a monitoring resource or **`FALSE`** on errors.

### See Also

-   <span class="function">fam\_monitor\_file</span>
-   <span class="function">fam\_monitor\_directory</span>
-   <span class="function">fam\_cancel\_monitor</span>
-   <span class="function">fam\_suspend\_monitor</span>
-   <span class="function">fam\_resume\_monitor</span>

fam\_monitor\_directory
=======================

Monitor a directory for changes

### Description

<span class="type">resource</span> <span
class="methodname">fam\_monitor\_directory</span> ( <span
class="methodparam"><span class="type">resource</span> `$fam`</span> ,
<span class="methodparam"><span class="type">string</span>
`$dirname`</span> )

Requests monitoring for a directory and all contained files.

A FAM event will be generated whenever the status of the directory (i.e.
the result of function <span class="function">stat</span> on that
directory) or its content (i.e. the results of <span
class="function">readdir</span>) changes.

The possible event codes are described in detail in the
<a href="/fam/constants.html" class="link">constants part</a> of this
section.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

`dirname`  
Path to the monitored directory

### Return Values

Returns a monitoring resource or **`FALSE`** on errors.

### See Also

-   <span class="function">fam\_monitor\_file</span>
-   <span class="function">fam\_monitor\_collection</span>
-   <span class="function">fam\_cancel\_monitor</span>
-   <span class="function">fam\_suspend\_monitor</span>
-   <span class="function">fam\_resume\_monitor</span>

fam\_monitor\_file
==================

Monitor a regular file for changes

### Description

<span class="type">resource</span> <span
class="methodname">fam\_monitor\_file</span> ( <span
class="methodparam"><span class="type">resource</span> `$fam`</span> ,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Requests monitoring for a single file. A FAM event will be generated
whenever the file status changes (i.e. the result of function <span
class="function">stat</span> on that file).

The possible event codes are described in detail in the
<a href="/fam/constants.html" class="link">constants part</a> of this
section.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

`filename`  
Path to the monitored file

### Return Values

Returns a monitoring resource or **`FALSE`** on errors.

### See Also

-   <span class="function">fam\_monitor\_directory</span>
-   <span class="function">fam\_monitor\_collection</span>
-   <span class="function">fam\_cancel\_monitor</span>
-   <span class="function">fam\_suspend\_monitor</span>
-   <span class="function">fam\_resume\_monitor</span>

fam\_next\_event
================

Get next pending FAM event

### Description

<span class="type">array</span> <span
class="methodname">fam\_next\_event</span> ( <span
class="methodparam"><span class="type">resource</span> `$fam`</span> )

Returns the next pending FAM event.

The function will block until an event is available which can be checked
for using <span class="function">fam\_pending</span>.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

### Return Values

Returns an array that contains a FAM event code in the '*code*' element,
the path of the file this event applies to in the '*filename*' element
and optionally a hostname in the '*hostname*' element.

The possible event codes are described in detail in the
<a href="/fam/constants.html" class="link">constants part</a> of this
section.

### See Also

-   <span class="function">fam\_pending</span>

fam\_open
=========

Open connection to FAM daemon

### Description

<span class="type">resource</span> <span
class="methodname">fam\_open</span> (\[ <span class="methodparam"><span
class="type">string</span> `$appname`</span> \] )

Opens a connection to the FAM service daemon.

### Parameters

`appname`  
A string identifying the application for logging reasons

### Return Values

Returns a resource representing a connection to the FAM service on
success or **`FALSE`** on errors.

### See Also

-   <span class="function">fam\_close</span>

fam\_pending
============

Check for pending FAM events

### Description

<span class="type">int</span> <span
class="methodname">fam\_pending</span> ( <span class="methodparam"><span
class="type">resource</span> `$fam`</span> )

Checks for pending FAM events.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

### Return Values

Returns non-zero if events are available to be fetched using <span
class="function">fam\_next\_event</span>, zero otherwise.

### See Also

-   <span class="function">fam\_next\_event</span>

fam\_resume\_monitor
====================

Resume suspended monitoring

### Description

<span class="type">bool</span> <span
class="methodname">fam\_resume\_monitor</span> ( <span
class="methodparam"><span class="type">resource</span> `$fam`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$fam_monitor`</span> )

Resumes monitoring of a resource previously suspended using <span
class="function">fam\_suspend\_monitor</span>.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

`fam_monitor`  
A resource returned by one of the *fam\_monitor\_XXX* functions

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">fam\_suspend\_monitor</span>

fam\_suspend\_monitor
=====================

Temporarily suspend monitoring

### Description

<span class="type">bool</span> <span
class="methodname">fam\_suspend\_monitor</span> ( <span
class="methodparam"><span class="type">resource</span> `$fam`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$fam_monitor`</span> )

<span class="function">fam\_suspend\_monitor</span> temporarily suspend
monitoring of a resource.

Monitoring can later be continued using <span
class="function">fam\_resume\_monitor</span> without the need of
requesting a complete new monitor.

### Parameters

`fam`  
A resource representing a connection to the FAM service returned by
<span class="function">fam\_open</span>

`fam_monitor`  
A resource returned by one of the *fam\_monitor\_XXX* functions

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">fam\_cancel\_monitor</span>
-   <span class="function">fam\_resume\_monitor</span>

**Table of Contents**

-   [fam\_cancel\_monitor](/ref/fam.html#fam_cancel_monitor) — Terminate
    monitoring
-   [fam\_close](/ref/fam.html#fam_close) — Close FAM connection
-   [fam\_monitor\_collection](/ref/fam.html#fam_monitor_collection) —
    Monitor a collection of files in a directory for changes
-   [fam\_monitor\_directory](/ref/fam.html#fam_monitor_directory) —
    Monitor a directory for changes
-   [fam\_monitor\_file](/ref/fam.html#fam_monitor_file) — Monitor a
    regular file for changes
-   [fam\_next\_event](/ref/fam.html#fam_next_event) — Get next pending
    FAM event
-   [fam\_open](/ref/fam.html#fam_open) — Open connection to FAM daemon
-   [fam\_pending](/ref/fam.html#fam_pending) — Check for pending FAM
    events
-   [fam\_resume\_monitor](/ref/fam.html#fam_resume_monitor) — Resume
    suspended monitoring
-   [fam\_suspend\_monitor](/ref/fam.html#fam_suspend_monitor) —
    Temporarily suspend monitoring

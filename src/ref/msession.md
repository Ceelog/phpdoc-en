msession\_connect
=================

Connect to msession server

### Description

<span class="type">bool</span> <span
class="methodname">msession\_connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">string</span>
`$port`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_count
===============

Get session count

### Description

<span class="type">int</span> <span
class="methodname">msession\_count</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_create
================

Create a session

### Description

<span class="type">bool</span> <span
class="methodname">msession\_create</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$classname`</span> \[, <span class="methodparam"><span
class="type">string</span> `$data`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_destroy
=================

Destroy a session

### Description

<span class="type">bool</span> <span
class="methodname">msession\_destroy</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_disconnect
====================

Close connection to msession server

### Description

<span class="type">void</span> <span
class="methodname">msession\_disconnect</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_find
==============

Find all sessions with name and value

### Description

<span class="type">array</span> <span
class="methodname">msession\_find</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_get\_array
====================

Get array of msession variables

### Description

<span class="type">array</span> <span
class="methodname">msession\_get\_array</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_get\_data
===================

Get data session unstructured data

### Description

<span class="type">string</span> <span
class="methodname">msession\_get\_data</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_get
=============

Get value from session

### Description

<span class="type">string</span> <span
class="methodname">msession\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_inc
=============

Increment value in session

### Description

<span class="type">string</span> <span
class="methodname">msession\_inc</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_list
==============

List all sessions

### Description

<span class="type">array</span> <span
class="methodname">msession\_list</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_listvar
=================

List sessions with variable

### Description

<span class="type">array</span> <span
class="methodname">msession\_listvar</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Used for searching sessions with common attributes.

### Parameters

`name`  
The name being searched.

### Return Values

Returns an associative array of value/session for all sessions with a
variable named `name`.

msession\_lock
==============

Lock a session

### Description

<span class="type">int</span> <span
class="methodname">msession\_lock</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_plugin
================

Call an escape function within the msession personality plugin

### Description

<span class="type">string</span> <span
class="methodname">msession\_plugin</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> ,
<span class="methodparam"><span class="type">string</span> `$val`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$param`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_randstr
=================

Get random string

### Description

<span class="type">string</span> <span
class="methodname">msession\_randstr</span> ( <span
class="methodparam"><span class="type">int</span> `$param`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_set\_array
====================

Set msession variables from an array

### Description

<span class="type">void</span> <span
class="methodname">msession\_set\_array</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> ,
<span class="methodparam"><span class="type">array</span>
`$tuples`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_set\_data
===================

Set data session unstructured data

### Description

<span class="type">bool</span> <span
class="methodname">msession\_set\_data</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_set
=============

Set value in session

### Description

<span class="type">bool</span> <span
class="methodname">msession\_set</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_timeout
=================

Set/get session timeout

### Description

<span class="type">int</span> <span
class="methodname">msession\_timeout</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$param`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_uniq
==============

Get unique id

### Description

<span class="type">string</span> <span
class="methodname">msession\_uniq</span> ( <span
class="methodparam"><span class="type">int</span> `$param`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$classname`</span> \[, <span class="methodparam"><span
class="type">string</span> `$data`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

msession\_unlock
================

Unlock a session

### Description

<span class="type">int</span> <span
class="methodname">msession\_unlock</span> ( <span
class="methodparam"><span class="type">string</span> `$session`</span> ,
<span class="methodparam"><span class="type">int</span> `$key`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

**Table of Contents**

-   [msession\_connect](/ref/msession.html#msession_connect) — Connect
    to msession server
-   [msession\_count](/ref/msession.html#msession_count) — Get session
    count
-   [msession\_create](/ref/msession.html#msession_create) — Create a
    session
-   [msession\_destroy](/ref/msession.html#msession_destroy) — Destroy a
    session
-   [msession\_disconnect](/ref/msession.html#msession_disconnect) —
    Close connection to msession server
-   [msession\_find](/ref/msession.html#msession_find) — Find all
    sessions with name and value
-   [msession\_get\_array](/ref/msession.html#msession_get_array) — Get
    array of msession variables
-   [msession\_get\_data](/ref/msession.html#msession_get_data) — Get
    data session unstructured data
-   [msession\_get](/ref/msession.html#msession_get) — Get value from
    session
-   [msession\_inc](/ref/msession.html#msession_inc) — Increment value
    in session
-   [msession\_list](/ref/msession.html#msession_list) — List all
    sessions
-   [msession\_listvar](/ref/msession.html#msession_listvar) — List
    sessions with variable
-   [msession\_lock](/ref/msession.html#msession_lock) — Lock a session
-   [msession\_plugin](/ref/msession.html#msession_plugin) — Call an
    escape function within the msession personality plugin
-   [msession\_randstr](/ref/msession.html#msession_randstr) — Get
    random string
-   [msession\_set\_array](/ref/msession.html#msession_set_array) — Set
    msession variables from an array
-   [msession\_set\_data](/ref/msession.html#msession_set_data) — Set
    data session unstructured data
-   [msession\_set](/ref/msession.html#msession_set) — Set value in
    session
-   [msession\_timeout](/ref/msession.html#msession_timeout) — Set/get
    session timeout
-   [msession\_uniq](/ref/msession.html#msession_uniq) — Get unique id
-   [msession\_unlock](/ref/msession.html#msession_unlock) — Unlock a
    session

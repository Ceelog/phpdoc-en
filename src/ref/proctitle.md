setproctitle
============

Set the process title

### Description

<span class="type">void</span> <span
class="methodname">setproctitle</span> ( <span class="methodparam"><span
class="type">string</span> `$title`</span> )

Sets the process title of the current process.

### Parameters

`title`  
The title to use as the process title.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">setproctitle</span> example**

Running the example below will change the process title (visible with
*ps a* for example).

``` php
<?php
setproctitle("myscript");
?>
```

The above example will output something similar to:

    $ ps a
      PID TTY      STAT   TIME COMMAND
     1168 pts/3    S      0:00 myscript                                                                                                                         

### See Also

-   <span class="function">cli\_set\_process\_title</span>
-   <span class="function">pcntl\_fork</span>
-   <span class="function">setthreadtitle</span>

setthreadtitle
==============

Set the thread title

### Description

<span class="type">bool</span> <span
class="methodname">setthreadtitle</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> )

Sets the thread title.

### Parameters

`title`  
The title to use as the thread title.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">setthreadtitle</span> example**

Running the example below will change the thread title (visible with *ps
c* for example).

``` php
<?php
setthreadtitle("myscript");
?>
```

The above example will output something similar to:

    $ ps c
      PID TTY      STAT   TIME COMMAND
     1178 pts/3    S      0:00 myscript

### See Also

-   <span class="function">pcntl\_fork</span>
-   <span class="function">setproctitle</span>

**Table of Contents**

-   [setproctitle](/ref/proctitle.html#setproctitle) — Set the process
    title
-   [setthreadtitle](/ref/proctitle.html#setthreadtitle) — Set the
    thread title

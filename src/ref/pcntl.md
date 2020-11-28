A look at the section about
<a href="/ref/posix.html" class="link">POSIX functions</a> may be
useful.

pcntl\_alarm
============

Set an alarm clock for delivery of a signal

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_alarm</span> ( <span class="methodparam"><span
class="type">int</span> `$seconds`</span> )

Creates a timer that will send a **`SIGALRM`** signal to the process
after the given number of seconds. Any call to <span
class="function">pcntl\_alarm</span> will cancel any previously set
alarm.

### Parameters

`seconds`  
The number of seconds to wait. If `seconds` is zero, no new alarm is
created.

### Return Values

Returns the time in seconds that any previously scheduled alarm had
remaining before it was to be delivered, or *0* if there was no
previously scheduled alarm.

pcntl\_async\_signals
=====================

Enable/disable asynchronous signal handling or return the old setting

### Description

<span class="type">bool</span> <span
class="methodname">pcntl\_async\_signals</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$on`<span
class="initializer"> = **`NULL`**</span></span> \] )

If the `on` parameter is omitted, <span
class="function">pcntl\_async\_signals</span> returns whether
asynchronous signal handling is enabled. Otherwise, asynchronous signal
handling is enabled or disabled.

### Parameters

`on`  
Whether asynchronous signal handling should be enabled.

### Return Values

When used as getter (that is without the optional parameter) it returns
whether asynchronous signal handling is enabled. When used as setter
(that is with the optional parameter given), it returns whether
asynchronous signal handling was enabled *before* the function call.

### See Also

-   <a href="/control-structures/declare.html" class="link">declare</a>

pcntl\_errno
============

Alias of <span class="function">pcntl\_get\_last\_error</span>

### Description

This function is an alias of: <span
class="function">pcntl\_get\_last\_error</span>

pcntl\_exec
===========

Executes specified program in current process space

### Description

<span class="type"><span class="type">null</span><span
class="type">false</span></span> <span
class="methodname">pcntl\_exec</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> \[, <span
class="methodparam"><span class="type">array</span> `$args`</span> \[,
<span class="methodparam"><span class="type">array</span> `$envs`</span>
\]\] )

Executes the program with the given arguments.

### Parameters

`path`  
`path` must be the path to a binary executable or a script with a valid
path pointing to an executable in the shebang ( \#!/usr/local/bin/perl
for example) as the first line. See your system's man execve(2) page for
additional information.

`args`  
`args` is an array of argument strings passed to the program.

`envs`  
`envs` is an array of strings which are passed as environment to the
program. The array is in the format of name =\> value, the key being the
name of the environmental variable and the value being the value of that
variable.

### Return Values

Returns **`NULL`** on success or **`FALSE`** on failure.

pcntl\_fork
===========

Forks the currently running process

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_fork</span> ( <span
class="methodparam">void</span> )

The <span class="function">pcntl\_fork</span> function creates a child
process that differs from the parent process only in its PID and PPID.
Please see your system's fork(2) man page for specific details as to how
fork works on your system.

### Return Values

On success, the PID of the child process is returned in the parent's
thread of execution, and a 0 is returned in the child's thread of
execution. On failure, a -1 will be returned in the parent's context, no
child process will be created, and a PHP error is raised.

### Examples

**Example \#1 <span class="function">pcntl\_fork</span> example**

``` php
<?php

$pid = pcntl_fork();
if ($pid == -1) {
     die('could not fork');
} else if ($pid) {
     // we are the parent
     pcntl_wait($status); //Protect against Zombie children
} else {
     // we are the child
}

?>
```

### See Also

-   <span class="function">pcntl\_waitpid</span>
-   <span class="function">pcntl\_signal</span>
-   <span class="function">setproctitle</span>

pcntl\_get\_last\_error
=======================

Retrieve the error number set by the last pcntl function which failed

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_get\_last\_error</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Returns error code.

### See Also

-   <span class="function">pcntl\_strerror</span>

pcntl\_getpriority
==================

Get the priority of any process

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">pcntl\_getpriority</span> (\[ <span
class="methodparam"><span class="type">int</span> `$pid`<span
class="initializer"> = getmypid()</span></span> \[, <span
class="methodparam"><span class="type">int</span>
`$process_identifier`<span class="initializer"> =
PRIO\_PROCESS</span></span> \]\] )

<span class="function">pcntl\_getpriority</span> gets the priority of
`pid`. Because priority levels can differ between system types and
kernel versions, please see your system's getpriority(2) man page for
specific details.

### Parameters

`pid`  
If not specified, the pid of the current process is used.

`process_identifier`  
One of **`PRIO_PGRP`**, **`PRIO_USER`** or **`PRIO_PROCESS`**.

### Return Values

<span class="function">pcntl\_getpriority</span> returns the priority of
the process or **`FALSE`** on error. A lower numerical value causes more
favorable scheduling.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### See Also

-   <span class="function">pcntl\_setpriority</span>

pcntl\_setpriority
==================

Change the priority of any process

### Description

<span class="type">bool</span> <span
class="methodname">pcntl\_setpriority</span> ( <span
class="methodparam"><span class="type">int</span> `$priority`</span> \[,
<span class="methodparam"><span class="type">int</span> `$pid`<span
class="initializer"> = getmypid()</span></span> \[, <span
class="methodparam"><span class="type">int</span>
`$process_identifier`<span class="initializer"> =
PRIO\_PROCESS</span></span> \]\] )

<span class="function">pcntl\_setpriority</span> sets the priority of
`pid`.

### Parameters

`priority`  
`priority` is generally a value in the range *-20* to *20*. The default
priority is *0* while a lower numerical value causes more favorable
scheduling. Because priority levels can differ between system types and
kernel versions, please see your system's setpriority(2) man page for
specific details.

`pid`  
If not specified, the pid of the current process is used.

`process_identifier`  
One of **`PRIO_PGRP`**, **`PRIO_USER`** or **`PRIO_PROCESS`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">pcntl\_getpriority</span>

pcntl\_signal\_dispatch
=======================

Calls signal handlers for pending signals

### Description

<span class="type">bool</span> <span
class="methodname">pcntl\_signal\_dispatch</span> ( <span
class="methodparam">void</span> )

The <span class="function">pcntl\_signal\_dispatch</span> function calls
the signal handlers installed by <span
class="function">pcntl\_signal</span> for each pending signal.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pcntl\_signal\_dispatch</span>
example**

``` php
<?php
echo "Installing signal handler...\n";
pcntl_signal(SIGHUP,  function($signo) {
     echo "signal handler called\n";
});

echo "Generating signal SIGHUP to self...\n";
posix_kill(posix_getpid(), SIGHUP);

echo "Dispatching...\n";
pcntl_signal_dispatch();

echo "Done\n";

?>
```

The above example will output something similar to:

    Installing signal handler...
    Generating signal SIGHUP to self...
    Dispatching...
    signal handler called
    Done

### See Also

-   <span class="function">pcntl\_signal</span>
-   <span class="function">pcntl\_sigprocmask</span>
-   <span class="function">pcntl\_sigwaitinfo</span>
-   <span class="function">pcntl\_sigtimedwait</span>

pcntl\_signal\_get\_handler
===========================

Get the current handler for specified signal

### Description

<span class="type">mixed</span> <span
class="methodname">pcntl\_signal\_get\_handler</span> ( <span
class="methodparam"><span class="type">int</span> `$signo`</span> )

The <span class="function">pcntl\_signal\_get\_handler</span> function
will get the current handler for the specified `signo`.

### Parameters

`signo`  
The signal number.

### Return Values

This function may return an integer value that refers to **`SIG_DFL`**
or **`SIG_IGN`**. If you set a custom handler a string value containing
the function name is returned.

### Changelog

| Version | Description                                                               |
|---------|---------------------------------------------------------------------------|
| 7.1.0   | <span class="function">pcntl\_signal\_get\_handler</span> has been added. |

### Examples

**Example \#1 <span class="function">pcntl\_signal\_get\_handler</span>
example**

``` php
<?php
var_dump(pcntl_signal_get_handler(SIGUSR1)); // Outputs: int(0)

function pcntl_test($signo) {}
pcntl_signal(SIGUSR1, 'pcntl_test');
var_dump(pcntl_signal_get_handler(SIGUSR1)); // Outputs: string(10) "pcntl_test"

pcntl_signal(SIGUSR1, SIG_DFL);
var_dump(pcntl_signal_get_handler(SIGUSR1)); // Outputs: int(0)

pcntl_signal(SIGUSR1, SIG_IGN);
var_dump(pcntl_signal_get_handler(SIGUSR1)); // Outputs: int(1)
?>
```

### See Also

-   <span class="function">pcntl\_signal</span>

pcntl\_signal
=============

Installs a signal handler

### Description

<span class="type">bool</span> <span
class="methodname">pcntl\_signal</span> ( <span
class="methodparam"><span class="type">int</span> `$signo`</span> ,
<span class="methodparam"><span class="type"><span
class="type">callable</span><span class="type">int</span></span>
`$handler`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$restart_syscalls`<span class="initializer"> =
**`TRUE`**</span></span> \] )

The <span class="function">pcntl\_signal</span> function installs a new
signal handler or replaces the current signal handler for the signal
indicated by `signo`.

### Parameters

`signo`  
The signal number.

`handler`  
The signal handler. This may be either a <span
class="type">callable</span>, which will be invoked to handle the
signal, or either of the two global constants **`SIG_IGN`** or
**`SIG_DFL`**, which will ignore the signal or restore the default
signal handler respectively.

If a <span class="type">callable</span> is given, it must implement the
following signature:

<span class="type">void</span> <span class="methodname"><span
class="replaceable">handler</span></span> ( <span
class="methodparam"><span class="type">int</span> `$signo`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$signinfo`</span> )

`signo`  
<span class="simpara"> The signal being handled. </span>

`siginfo`  
<span class="simpara"> If operating systems supports siginfo\_t
structures, this will be an array of signal information dependent on the
signal. </span>

> **Note**:
>
> Note that when you set a handler to an object method, that object's
> reference count is increased which makes it persist until you either
> change the handler to something else, or your script ends.

`restart_syscalls`  
Specifies whether system call restarting should be used when this signal
arrives.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                                                                                 |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | As of PHP 7.1.0 the handler callback is given a second argument containing the signinfo of the specific signal. This data is only supplied if the operating system has the signinfo\_t structure. If the OS does not implement siginfo\_t NULL is supplied. |

### Examples

**Example \#1 <span class="function">pcntl\_signal</span> example**

``` php
<?php
// tick use required
declare(ticks = 1);

// signal handler function
function sig_handler($signo)
{

     switch ($signo) {
         case SIGTERM:
             // handle shutdown tasks
             exit;
             break;
         case SIGHUP:
             // handle restart tasks
             break;
         case SIGUSR1:
             echo "Caught SIGUSR1...\n";
             break;
         default:
             // handle all other signals
     }

}

echo "Installing signal handler...\n";

// setup signal handlers
pcntl_signal(SIGTERM, "sig_handler");
pcntl_signal(SIGHUP,  "sig_handler");
pcntl_signal(SIGUSR1, "sig_handler");

// or use an object
// pcntl_signal(SIGUSR1, array($obj, "do_something"));

echo"Generating signal SIGUSR1 to self...\n";

// send SIGUSR1 to current process id
// posix_* functions require the posix extension
posix_kill(posix_getpid(), SIGUSR1);

echo "Done\n";

?>
```

### Notes

<span class="function">pcntl\_signal</span> doesn't stack the signal
handlers, but replaces them.

### See Also

-   <span class="function">pcntl\_fork</span>
-   <span class="function">pcntl\_waitpid</span>

pcntl\_sigprocmask
==================

Sets and retrieves blocked signals

### Description

<span class="type">bool</span> <span
class="methodname">pcntl\_sigprocmask</span> ( <span
class="methodparam"><span class="type">int</span> `$how`</span> , <span
class="methodparam"><span class="type">array</span> `$set`</span> \[,
<span class="methodparam"><span class="type">array</span>
`&$oldset`</span> \] )

The <span class="function">pcntl\_sigprocmask</span> function adds,
removes or sets blocked signals, depending on the `how` parameter.

### Parameters

`how`  
Sets the behavior of <span class="function">pcntl\_sigprocmask</span>.
Possible values:

-   **`SIG_BLOCK`**: Add the signals to the currently blocked signals.
-   **`SIG_UNBLOCK`**: Remove the signals from the currently blocked
    signals.
-   **`SIG_SETMASK`**: Replace the currently blocked signals by the
    given list of signals.

`set`  
List of signals.

`oldset`  
The `oldset` parameter is set to an array containing the list of the
previously blocked signals.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">pcntl\_sigprocmask</span> example**

``` php
<?php
pcntl_sigprocmask(SIG_BLOCK, array(SIGHUP));
$oldset = array();
pcntl_sigprocmask(SIG_UNBLOCK, array(SIGHUP), $oldset);
?>
```

### See Also

-   <span class="function">pcntl\_sigwaitinfo</span>
-   <span class="function">pcntl\_sigtimedwait</span>

pcntl\_sigtimedwait
===================

Waits for signals, with a timeout

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_sigtimedwait</span> ( <span
class="methodparam"><span class="type">array</span> `$set`</span> \[,
<span class="methodparam"><span class="type">array</span>
`&$siginfo`</span> \[, <span class="methodparam"><span
class="type">int</span> `$seconds`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$nanoseconds`<span class="initializer"> =
0</span></span> \]\]\] )

The <span class="function">pcntl\_sigtimedwait</span> function operates
in exactly the same way as <span
class="function">pcntl\_sigwaitinfo</span> except that it takes two
additional parameters, `seconds` and `nanoseconds`, which enable an
upper bound to be placed on the time for which the script is suspended.

### Parameters

`set`  
Array of signals to wait for.

`siginfo`  
The `siginfo` is set to an array containing information about the
signal. See <span class="function">pcntl\_sigwaitinfo</span>.

`seconds`  
Timeout in seconds.

`nanoseconds`  
Timeout in nanoseconds.

### Return Values

On success, <span class="function">pcntl\_sigtimedwait</span> returns a
signal number.

### See Also

-   <span class="function">pcntl\_sigprocmask</span>
-   <span class="function">pcntl\_sigwaitinfo</span>

pcntl\_sigwaitinfo
==================

Waits for signals

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_sigwaitinfo</span> ( <span
class="methodparam"><span class="type">array</span> `$set`</span> \[,
<span class="methodparam"><span class="type">array</span>
`&$siginfo`</span> \] )

The <span class="function">pcntl\_sigwaitinfo</span> function suspends
execution of the calling script until one of the signals given in `set`
are delivered. If one of the signal is already pending (e.g. blocked by
<span class="function">pcntl\_sigprocmask</span>), <span
class="function">pcntl\_sigwaitinfo</span> will return immediately.

### Parameters

`set`  
Array of signals to wait for.

`siginfo`  
The `siginfo` parameter is set to an array containing information about
the signal.

The following elements are set for all signals:

-   signo: Signal number
-   errno: An error number
-   code: Signal code

The following elements may be set for the **`SIGCHLD`** signal:

-   status: Exit value or signal
-   utime: User time consumed
-   stime: System time consumed
-   pid: Sending process ID
-   uid: Real user ID of sending process

The following elements may be set for the **`SIGILL`**, **`SIGFPE`**,
**`SIGSEGV`** and **`SIGBUS`** signals:

-   addr: Memory location which caused fault

The following element may be set for the **`SIGPOLL`** signal:

-   band: Band event
-   fd: File descriptor number

### Return Values

On success, <span class="function">pcntl\_sigwaitinfo</span> returns a
signal number.

### Examples

**Example \#1 <span class="function">pcntl\_sigwaitinfo</span> example**

``` php
<?php
echo "Blocking SIGHUP signal\n";
pcntl_sigprocmask(SIG_BLOCK, array(SIGHUP));

echo "Sending SIGHUP to self\n";
posix_kill(posix_getpid(), SIGHUP);

echo "Waiting for signals\n";
$info = array();
pcntl_sigwaitinfo(array(SIGHUP), $info);
?>
```

### See Also

-   <span class="function">pcntl\_sigprocmask</span>
-   <span class="function">pcntl\_sigtimedwait</span>

pcntl\_strerror
===============

Retrieve the system error message associated with the given errno

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">pcntl\_strerror</span> ( <span
class="methodparam"><span class="type">int</span> `$errno`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`errno`  

### Return Values

Returns error description on success or **`FALSE`** on failure.

### See Also

-   <span class="function">pcntl\_get\_last\_error</span>

pcntl\_wait
===========

Waits on or returns the status of a forked child

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_wait</span> ( <span class="methodparam"><span
class="type">int</span> `&$status`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$rusage`</span>
\]\] )

The wait function suspends execution of the current process until a
child has exited, or until a signal is delivered whose action is to
terminate the current process or to call a signal handling function. If
a child has already exited by the time of the call (a so-called "zombie"
process), the function returns immediately. Any system resources used by
the child are freed. Please see your system's wait(2) man page for
specific details as to how wait works on your system.

> **Note**:
>
> This function is equivalent to calling <span
> class="function">pcntl\_waitpid</span> with a *-1* `pid` and no
> `options`.

### Parameters

`status`  
<span class="function">pcntl\_wait</span> will store status information
in the `status` parameter which can be evaluated using the following
functions: <span class="function">pcntl\_wifexited</span>, <span
class="function">pcntl\_wifstopped</span>, <span
class="function">pcntl\_wifsignaled</span>, <span
class="function">pcntl\_wexitstatus</span>, <span
class="function">pcntl\_wtermsig</span> and <span
class="function">pcntl\_wstopsig</span>.

`options`  
If wait3 is available on your system (mostly BSD-style systems), you can
provide the optional `options` parameter. If this parameter is not
provided, wait will be used for the system call. If wait3 is not
available, providing a value for `options        ` will have no effect.
The value of `options        ` is the value of zero or more of the
following two constants *OR*'ed together:

|             |                                                                                |
|-------------|--------------------------------------------------------------------------------|
| *WNOHANG*   | Return immediately if no child has exited.                                     |
| *WUNTRACED* | Return for children which are stopped, and whose status has not been reported. |

### Return Values

<span class="function">pcntl\_wait</span> returns the process ID of the
child which exited, -1 on error or zero if WNOHANG was provided as an
option (on wait3-available systems) and no child was available.

### See Also

-   <span class="function">pcntl\_fork</span>
-   <span class="function">pcntl\_signal</span>
-   <span class="function">pcntl\_wifexited</span>
-   <span class="function">pcntl\_wifstopped</span>
-   <span class="function">pcntl\_wifsignaled</span>
-   <span class="function">pcntl\_wexitstatus</span>
-   <span class="function">pcntl\_wtermsig</span>
-   <span class="function">pcntl\_wstopsig</span>
-   <span class="function">pcntl\_waitpid</span>

pcntl\_waitpid
==============

Waits on or returns the status of a forked child

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_waitpid</span> ( <span
class="methodparam"><span class="type">int</span> `$pid`</span> , <span
class="methodparam"><span class="type">int</span> `&$status`</span> \[,
<span class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$rusage`</span>
\]\] )

Suspends execution of the current process until a child as specified by
the `pid` argument has exited, or until a signal is delivered whose
action is to terminate the current process or to call a signal handling
function.

If a child as requested by `pid` has already exited by the time of the
call (a so-called "zombie" process), the function returns immediately.
Any system resources used by the child are freed. Please see your
system's waitpid(2) man page for specific details as to how waitpid
works on your system.

### Parameters

`pid`  
The value of `pid` can be one of the following:

|         |                                                                                            |
|---------|--------------------------------------------------------------------------------------------|
| *\< -1* | wait for any child process whose process group ID is equal to the absolute value of `pid`. |
| *-1*    | wait for any child process; this is the same behaviour that the wait function exhibits.    |
| *0*     | wait for any child process whose process group ID is equal to that of the calling process. |
| *\> 0*  | wait for the child whose process ID is equal to the value of `pid`.                        |

> **Note**:
>
> Specifying *-1* as the `pid` is equivalent to the functionality <span
> class="function">pcntl\_wait</span> provides (minus `options`).

`status`  
<span class="function">pcntl\_waitpid</span> will store status
information in the `status` parameter which can be evaluated using the
following functions: <span class="function">pcntl\_wifexited</span>,
<span class="function">pcntl\_wifstopped</span>, <span
class="function">pcntl\_wifsignaled</span>, <span
class="function">pcntl\_wexitstatus</span>, <span
class="function">pcntl\_wtermsig</span> and <span
class="function">pcntl\_wstopsig</span>.

`options`  
The value of `options` is the value of zero or more of the following two
global constants *OR*'ed together:

|             |                                                                                |
|-------------|--------------------------------------------------------------------------------|
| *WNOHANG*   | return immediately if no child has exited.                                     |
| *WUNTRACED* | return for children which are stopped, and whose status has not been reported. |

### Return Values

<span class="function">pcntl\_waitpid</span> returns the process ID of
the child which exited, -1 on error or zero if **`WNOHANG`** was used
and no child was available

### See Also

-   <span class="function">pcntl\_fork</span>
-   <span class="function">pcntl\_signal</span>
-   <span class="function">pcntl\_wifexited</span>
-   <span class="function">pcntl\_wifstopped</span>
-   <span class="function">pcntl\_wifsignaled</span>
-   <span class="function">pcntl\_wexitstatus</span>
-   <span class="function">pcntl\_wtermsig</span>
-   <span class="function">pcntl\_wstopsig</span>

pcntl\_wexitstatus
==================

Returns the return code of a terminated child

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_wexitstatus</span> ( <span
class="methodparam"><span class="type">int</span> `$status`</span> )

Returns the return code of a terminated child. This function is only
useful if <span class="function">pcntl\_wifexited</span> returned
**`TRUE`**.

### Parameters

`status`  
The `status` parameter is the status parameter supplied to a successful
call to <span class="function">pcntl\_waitpid</span>.

### Return Values

Returns the return code, as an integer.

### See Also

-   <span class="function">pcntl\_waitpid</span>
-   <span class="function">pcntl\_wifexited</span>

pcntl\_wifexited
================

Checks if status code represents a normal exit

### Description

<span class="type">bool</span> <span
class="methodname">pcntl\_wifexited</span> ( <span
class="methodparam"><span class="type">int</span> `$status`</span> )

Checks whether the child status code represents a normal exit.

### Parameters

`status`  
The `status` parameter is the status parameter supplied to a successful
call to <span class="function">pcntl\_waitpid</span>.

### Return Values

Returns **`TRUE`** if the child status code represents a normal exit,
**`FALSE`** otherwise.

### See Also

-   <span class="function">pcntl\_waitpid</span>
-   <span class="function">pcntl\_wexitstatus</span>

pcntl\_wifsignaled
==================

Checks whether the status code represents a termination due to a signal

### Description

<span class="type">bool</span> <span
class="methodname">pcntl\_wifsignaled</span> ( <span
class="methodparam"><span class="type">int</span> `$status`</span> )

Checks whether the child process exited because of a signal which was
not caught.

### Parameters

`status`  
The `status` parameter is the status parameter supplied to a successful
call to <span class="function">pcntl\_waitpid</span>.

### Return Values

Returns **`TRUE`** if the child process exited because of a signal which
was not caught, **`FALSE`** otherwise.

### See Also

-   <span class="function">pcntl\_waitpid</span>
-   <span class="function">pcntl\_signal</span>

pcntl\_wifstopped
=================

Checks whether the child process is currently stopped

### Description

<span class="type">bool</span> <span
class="methodname">pcntl\_wifstopped</span> ( <span
class="methodparam"><span class="type">int</span> `$status`</span> )

Checks whether the child process which caused the return is currently
stopped; this is only possible if the call to <span
class="function">pcntl\_waitpid</span> was done using the option
*WUNTRACED*.

### Parameters

`status`  
The `status` parameter is the status parameter supplied to a successful
call to <span class="function">pcntl\_waitpid</span>.

### Return Values

Returns **`TRUE`** if the child process which caused the return is
currently stopped, **`FALSE`** otherwise.

### See Also

-   <span class="function">pcntl\_waitpid</span>

pcntl\_wstopsig
===============

Returns the signal which caused the child to stop

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_wstopsig</span> ( <span
class="methodparam"><span class="type">int</span> `$status`</span> )

Returns the number of the signal which caused the child to stop. This
function is only useful if <span
class="function">pcntl\_wifstopped</span> returned **`TRUE`**.

### Parameters

`status`  
The `status` parameter is the status parameter supplied to a successful
call to <span class="function">pcntl\_waitpid</span>.

### Return Values

Returns the signal number.

### See Also

-   <span class="function">pcntl\_waitpid</span>
-   <span class="function">pcntl\_wifstopped</span>

pcntl\_wtermsig
===============

Returns the signal which caused the child to terminate

### Description

<span class="type">int</span> <span
class="methodname">pcntl\_wtermsig</span> ( <span
class="methodparam"><span class="type">int</span> `$status`</span> )

Returns the number of the signal that caused the child process to
terminate. This function is only useful if <span
class="function">pcntl\_wifsignaled</span> returned **`TRUE`**.

### Parameters

`status`  
The `status` parameter is the status parameter supplied to a successful
call to <span class="function">pcntl\_waitpid</span>.

### Return Values

Returns the signal number, as an integer.

### See Also

-   <span class="function">pcntl\_waitpid</span>
-   <span class="function">pcntl\_signal</span>
-   <span class="function">pcntl\_wifsignaled</span>

**Table of Contents**

-   [pcntl\_alarm](/ref/pcntl.html#pcntl_alarm) — Set an alarm clock for
    delivery of a signal
-   [pcntl\_async\_signals](/ref/pcntl.html#pcntl_async_signals) —
    Enable/disable asynchronous signal handling or return the old
    setting
-   [pcntl\_errno](/ref/pcntl.html#pcntl_errno) — Alias of
    pcntl\_get\_last\_error
-   [pcntl\_exec](/ref/pcntl.html#pcntl_exec) — Executes specified
    program in current process space
-   [pcntl\_fork](/ref/pcntl.html#pcntl_fork) — Forks the currently
    running process
-   [pcntl\_get\_last\_error](/ref/pcntl.html#pcntl_get_last_error) —
    Retrieve the error number set by the last pcntl function which
    failed
-   [pcntl\_getpriority](/ref/pcntl.html#pcntl_getpriority) — Get the
    priority of any process
-   [pcntl\_setpriority](/ref/pcntl.html#pcntl_setpriority) — Change the
    priority of any process
-   [pcntl\_signal\_dispatch](/ref/pcntl.html#pcntl_signal_dispatch) —
    Calls signal handlers for pending signals
-   [pcntl\_signal\_get\_handler](/ref/pcntl.html#pcntl_signal_get_handler)
    — Get the current handler for specified signal
-   [pcntl\_signal](/ref/pcntl.html#pcntl_signal) — Installs a signal
    handler
-   [pcntl\_sigprocmask](/ref/pcntl.html#pcntl_sigprocmask) — Sets and
    retrieves blocked signals
-   [pcntl\_sigtimedwait](/ref/pcntl.html#pcntl_sigtimedwait) — Waits
    for signals, with a timeout
-   [pcntl\_sigwaitinfo](/ref/pcntl.html#pcntl_sigwaitinfo) — Waits for
    signals
-   [pcntl\_strerror](/ref/pcntl.html#pcntl_strerror) — Retrieve the
    system error message associated with the given errno
-   [pcntl\_wait](/ref/pcntl.html#pcntl_wait) — Waits on or returns the
    status of a forked child
-   [pcntl\_waitpid](/ref/pcntl.html#pcntl_waitpid) — Waits on or
    returns the status of a forked child
-   [pcntl\_wexitstatus](/ref/pcntl.html#pcntl_wexitstatus) — Returns
    the return code of a terminated child
-   [pcntl\_wifexited](/ref/pcntl.html#pcntl_wifexited) — Checks if
    status code represents a normal exit
-   [pcntl\_wifsignaled](/ref/pcntl.html#pcntl_wifsignaled) — Checks
    whether the status code represents a termination due to a signal
-   [pcntl\_wifstopped](/ref/pcntl.html#pcntl_wifstopped) — Checks
    whether the child process is currently stopped
-   [pcntl\_wstopsig](/ref/pcntl.html#pcntl_wstopsig) — Returns the
    signal which caused the child to stop
-   [pcntl\_wtermsig](/ref/pcntl.html#pcntl_wtermsig) — Returns the
    signal which caused the child to terminate

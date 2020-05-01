Process Control
===============

**Table of Contents**

-   [Introduction](/intro/pcntl.html)
-   [Installing/Configuring](/pcntl/setup.html)
    -   [Requirements](/pcntl/setup.html#Requirements)
    -   [Installation](/pcntl/setup.html#Installation)
    -   [Runtime
        Configuration](/pcntl/setup.html#Runtime%20Configuration)
    -   [Resource Types](/pcntl/setup.html#Resource%20Types)
-   [Predefined Constants](/pcntl/constants.html)
-   [Examples](/pcntl/examples.html)
    -   [Basic usage](/pcntl/examples.html#Basic%20usage)
-   [PCNTL Functions](/ref/pcntl.html)
    -   [pcntl\_alarm](/ref/pcntl.html#pcntl_alarm) — Set an alarm clock
        for delivery of a signal
    -   [pcntl\_async\_signals](/ref/pcntl.html#pcntl_async_signals) —
        Enable/disable asynchronous signal handling or return the old
        setting
    -   [pcntl\_errno](/ref/pcntl.html#pcntl_errno) — Alias of
        pcntl\_get\_last\_error
    -   [pcntl\_exec](/ref/pcntl.html#pcntl_exec) — Executes specified
        program in current process space
    -   [pcntl\_fork](/ref/pcntl.html#pcntl_fork) — Forks the currently
        running process
    -   [pcntl\_get\_last\_error](/ref/pcntl.html#pcntl_get_last_error)
        — Retrieve the error number set by the last pcntl function which
        failed
    -   [pcntl\_getpriority](/ref/pcntl.html#pcntl_getpriority) — Get
        the priority of any process
    -   [pcntl\_setpriority](/ref/pcntl.html#pcntl_setpriority) — Change
        the priority of any process
    -   [pcntl\_signal\_dispatch](/ref/pcntl.html#pcntl_signal_dispatch)
        — Calls signal handlers for pending signals
    -   [pcntl\_signal\_get\_handler](/ref/pcntl.html#pcntl_signal_get_handler)
        — Get the current handler for specified signal
    -   [pcntl\_signal](/ref/pcntl.html#pcntl_signal) — Installs a
        signal handler
    -   [pcntl\_sigprocmask](/ref/pcntl.html#pcntl_sigprocmask) — Sets
        and retrieves blocked signals
    -   [pcntl\_sigtimedwait](/ref/pcntl.html#pcntl_sigtimedwait) —
        Waits for signals, with a timeout
    -   [pcntl\_sigwaitinfo](/ref/pcntl.html#pcntl_sigwaitinfo) — Waits
        for signals
    -   [pcntl\_strerror](/ref/pcntl.html#pcntl_strerror) — Retrieve the
        system error message associated with the given errno
    -   [pcntl\_wait](/ref/pcntl.html#pcntl_wait) — Waits on or returns
        the status of a forked child
    -   [pcntl\_waitpid](/ref/pcntl.html#pcntl_waitpid) — Waits on or
        returns the status of a forked child
    -   [pcntl\_wexitstatus](/ref/pcntl.html#pcntl_wexitstatus) —
        Returns the return code of a terminated child
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

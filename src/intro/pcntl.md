Process Control support in PHP implements the Unix style of process
creation, program execution, signal handling and process termination.
Process Control should not be enabled within a web server environment
and unexpected results may happen if any Process Control functions are
used within a web server environment.

This documentation is intended to explain the general usage of each of
the Process Control functions. For detailed information about Unix
process control you are encouraged to consult your systems documentation
including fork(2), waitpid(2) and signal(2) or a comprehensive reference
such as Advanced Programming in the UNIX Environment by W. Richard
Stevens (Addison-Wesley).

PCNTL now uses ticks as the signal handle callback mechanism, which is
much faster than the previous mechanism. This change follows the same
semantics as using "user ticks". You use the <span
class="function">declare</span> statement to specify the locations in
your program where callbacks are allowed to occur. This allows you to
minimize the overhead of handling asynchronous events. In the past,
compiling PHP with pcntl enabled would always incur this overhead,
whether or not your script actually used pcntl.

> **Note**: <span class="simpara">This extension is not available on
> Windows platforms.</span>

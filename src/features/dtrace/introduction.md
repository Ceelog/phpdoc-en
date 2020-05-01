Introduction to PHP and DTrace
------------------------------

DTrace is an always-available, low overhead, tracing framework available
on a number of platforms including Solaris, macOS, Oracle Linux and BSD.
DTrace can trace operating system behavior and user program execution.
It can display argument values and be used to infer performance
statistics. Probes are monitored by user created scripts written in the
DTrace D scripting language. This allows efficient analysis of data
points.

PHP probes that are not being actively monitored by a user's DTrace D
script do not contain instrumented code so there is no performance
degradation during normal application execution. Probes that are being
monitored incur an overhead low enough to generally allow DTrace
monitoring on live production systems.

PHP incorporates "User-level Statically Defined Tracing" (USDT) probes
that are triggered at runtime. For example, when a D script is
monitoring PHP's *function-entry* probe, then, every time a PHP script
function is called, this probe is fired and the associated D script
action code is executed. This action code could, for example, print
probe arguments such as the source file location of the PHP function. Or
the action could aggregate data such as the number of times each
function is called.

Only the PHP USDT probes are described here. Refer to external general
and operating system-specific DTrace literature to see how DTrace can be
used to trace arbitrary functions, and how it can be used to trace
operating system behavior. Note not all DTrace features are available in
all DTrace implementations.

DTrace static probes are included in PHP 5.4. Prior to this they were
available via a
<a href="https://pecl.php.net/" class="link external">» PECL</a>
extension, which is now obsolete.

The static DTrace probes in PHP can alternatively be used with the
SystemTap facility on some Linux distributions.

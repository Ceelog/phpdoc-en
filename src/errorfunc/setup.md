Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/errorfunc/setup.html#Requirements)
-   [Installation](/errorfunc/setup.html#Installation)
-   [Runtime
    Configuration](/errorfunc/setup.html#Runtime%20Configuration)
-   [Resource Types](/errorfunc/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                                                  | Default     | Changeable       | Changelog                   |
|-------------------------------------------------------------------------------------------------------|-------------|------------------|-----------------------------|
| <a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a> | NULL        | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">display_errors</a>                                      | "1"         | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">display_startup_errors</a>                              | "0"         | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">log_errors</a>                                          | "0"         | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">log_errors_max_len</a>                                  | "1024"      | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">ignore_repeated_errors</a>                              | "0"         | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">ignore_repeated_source</a>                              | "0"         | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">report_memleaks</a>                                     | "1"         | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">track_errors</a>                                        | "0"         | PHP\_INI\_ALL    | Deprecated as of PHP 7.2.0. |
| <a href="/errorfunc/setup.html#" class="link">html_errors</a>                                         | "1"         | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">xmlrpc_errors</a>                                       | "0"         | PHP\_INI\_SYSTEM |                             |
| <a href="/errorfunc/setup.html#" class="link">xmlrpc_error_number</a>                                 | "0"         | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">docref_root</a>                                         | ""          | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">docref_ext</a>                                          | ""          | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">error_prepend_string</a>                                | NULL        | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">error_append_string</a>                                 | NULL        | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">error_log</a>                                           | NULL        | PHP\_INI\_ALL    |                             |
| <a href="/errorfunc/setup.html#" class="link">syslog.facility</a>                                     | "LOG\_USER" | PHP\_INI\_SYSTEM | Available as of PHP 7.3.0.  |
| <a href="/errorfunc/setup.html#" class="link">syslog.filter</a>                                       | "no-ctrl"   | PHP\_INI\_ALL    | Available as of PHP 7.3.0.  |
| <a href="/errorfunc/setup.html#" class="link">syslog.ident</a>                                        | "php"       | PHP\_INI\_SYSTEM | Available as of PHP 7.3.0.  |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`error_reporting` <span class="type">integer</span>  
Set the error reporting level. The parameter is either an integer
representing a bit field, or named constants. The error\_reporting
levels and constants are described in
<a href="/errorfunc/constants.html" class="link">Predefined Constants</a>,
and in `php.ini`. To set at runtime, use the <span
class="function">error\_reporting</span> function. See also the
<a href="/errorfunc/setup.html#" class="link">display_errors</a>
directive.

PHP 5.3 or later, the default value is **`E_ALL`** & \~**`E_NOTICE`** &
\~**`E_STRICT`** & \~**`E_DEPRECATED`**. This setting does not show
**`E_NOTICE`**, **`E_STRICT`** and **`E_DEPRECATED`** level errors. You
may want to show them during development. Prior to PHP 5.3.0, the
default value is **`E_ALL`** & \~**`E_NOTICE`** & \~**`E_STRICT`**.

> **Note**:
>
> Enabling **`E_NOTICE`** during development has some benefits. For
> debugging purposes: NOTICE messages will warn you about possible bugs
> in your code. For example, use of unassigned values is warned. It is
> extremely useful to find typos and to save time for debugging. NOTICE
> messages will warn you about bad style. For example, *$arr\[item\]* is
> better to be written as *$arr\['item'\]* since PHP tries to treat
> *"item"* as constant. If it is not a constant, PHP assumes it is a
> string index for the array.

> **Note**:
>
> Prior to PHP 5.4.0 **`E_STRICT`** was not included within **`E_ALL`**,
> so you would have to explicitly enable this kind of error level in PHP
> \< 5.4.0. Enabling **`E_STRICT`** during development has some
> benefits. STRICT messages provide suggestions that can help ensure the
> best interoperability and forward compatibility of your code. These
> messages may include things such as calling non-static methods
> statically, defining properties in a compatible class definition while
> defined in a used trait, and prior to PHP 5.3 some deprecated features
> would issue **`E_STRICT`** errors such as assigning objects by
> reference upon instantiation.

> **Note**: **PHP Constants outside of PHP**  
>
> Using PHP Constants outside of PHP, like in `httpd.conf`, will have no
> useful meaning so in such cases the <span class="type">integer</span>
> values are required. And since error levels will be added over time,
> the maximum value (for **`E_ALL`**) will likely change. So in place of
> **`E_ALL`** consider using a larger value to cover all bit fields from
> now and well into the future, a numeric value like *2147483647*
> (includes all errors, not just **`E_ALL`**).

`display_errors` <span class="type">string</span>  
This determines whether errors should be printed to the screen as part
of the output or if they should be hidden from the user.

Value *"stderr"* sends the errors to *stderr* instead of *stdout*. The
value is available as of PHP 5.2.4. In earlier versions, this directive
was of type <span class="type">boolean</span>.

> **Note**:
>
> This is a feature to support your development and should never be used
> on production systems (e.g. systems connected to the internet).

> **Note**:
>
> Although display\_errors may be set at runtime (with <span
> class="function">ini\_set</span>), it won't have any effect if the
> script has fatal errors. This is because the desired runtime action
> does not get executed.

`display_startup_errors` <span class="type">boolean</span>  
Even when display\_errors is on, errors that occur during PHP's startup
sequence are not displayed. It's strongly recommended to keep
display\_startup\_errors off, except for debugging.

`log_errors` <span class="type">boolean</span>  
Tells whether script error messages should be logged to the server's
error log or
<a href="/errorfunc/setup.html#" class="link">error_log</a>. This option
is thus server-specific.

> **Note**:
>
> You're strongly advised to use error logging in place of error
> displaying on production web sites.

`log_errors_max_len` <span class="type">integer</span>  
Set the maximum length of log\_errors in bytes. In
<a href="/errorfunc/setup.html#" class="link">error_log</a> information
about the source is added. The default is 1024 and 0 allows to not apply
any maximum length at all. This length is applied to logged errors,
displayed errors and also to `$php_errormsg`, but not to explicitly
called functions such as <span class="function">error\_log</span>.

<span class="simpara">When an <span class="type">integer</span> is used,
the value is measured in bytes. Shorthand notation, as described in
<a href="/faq/using.html#faq.using.shorthandbytes" class="link">this FAQ</a>,
may also be used. </span>

`ignore_repeated_errors` <span class="type">boolean</span>  
Do not log repeated messages. Repeated errors must occur in the same
file on the same line unless
<a href="/errorfunc/setup.html#" class="link">ignore_repeated_source</a>
is set true.

`ignore_repeated_source` <span class="type">boolean</span>  
Ignore source of message when ignoring repeated messages. When this
setting is On you will not log errors with repeated messages from
different files or sourcelines.

`report_memleaks` <span class="type">boolean</span>  
If this parameter is set to On (the default), this parameter will show a
report of memory leaks detected by the Zend memory manager. This report
will be sent to stderr on Posix platforms. On Windows, it will be sent
to the debugger using OutputDebugString() and can be viewed with tools
like
<a href="http://technet.microsoft.com/en-us/sysinternals/bb896647" class="link external">» DbgView</a>.
This parameter only has effect in a debug build and if error\_reporting
includes **`E_WARNING`** in the allowed list.

`track_errors` <span class="type">boolean</span>  
If enabled, the last error message will always be present in the
variable `$php_errormsg`.

`html_errors` <span class="type">boolean</span>  
If enabled, error messages will include HTML tags. The format for HTML
errors produces clickable messages that direct the user to a page
describing the error or function in causing the error. These references
are affected by
<a href="/errorfunc/setup.html#" class="link">docref_root</a> and
<a href="/errorfunc/setup.html#" class="link">docref_ext</a>.

If disabled, error message will be solely plain text.

`xmlrpc_errors` <span class="type">boolean</span>  
If enabled, turns off normal error reporting and formats errors as
XML-RPC error message.

`xmlrpc_error_number` <span class="type">integer</span>  
Used as the value of the XML-RPC faultCode element.

`docref_root` <span class="type">string</span>  
The new error format contains a reference to a page describing the error
or function causing the error. In case of manual pages you can download
the manual in your language and set this ini directive to the URL of
your local copy. If your local copy of the manual can be reached by
*"/manual/"* you can simply use **`docref_root=/manual/`**. Additional
you have to set docref\_ext to match the fileextensions of your copy
**`docref_ext=.html`**. It is possible to use external references. For
example you can use **`docref_root=http://manual/en/`** or
**`docref_root="http://landonize.it/?how=url&theme=classic&filter=Landon       &url=http%3A%2F%2Fwww.php.net%2F"`**

Most of the time you want the docref\_root value to end with a slash
*"/"*. But see the second example above which does not have nor need it.

> **Note**:
>
> This is a feature to support your development since it makes it easy
> to lookup a function description. However it should never be used on
> production systems (e.g. systems connected to the internet).

`docref_ext` <span class="type">string</span>  
See <a href="/errorfunc/setup.html#" class="link">docref_root</a>.

> **Note**:
>
> The value of docref\_ext must begin with a dot *"."*.

`error_prepend_string` <span class="type">string</span>  
String to output before an error message.

`error_append_string` <span class="type">string</span>  
String to output after an error message.

`error_log` <span class="type">string</span>  
Name of the file where script errors should be logged. The file should
be writable by the web server's user. If the special value *syslog* is
used, the errors are sent to the system logger instead. On Unix, this
means syslog(3) and on Windows it means the event log. See also: <span
class="function">syslog</span>. If this directive is not set, errors are
sent to the SAPI error logger. For example, it is an error log in Apache
or *stderr* in CLI. See also <span class="function">error\_log</span>.

`syslog.facility` <span class="type">string</span>  
Specifies what type of program is logging the message. Only effective if
<a href="/errorfunc/setup.html#" class="link">error_log</a> is set to
"syslog".

`syslog.filter` <span class="type">string</span>  
Specifies the filter type to filter the logged messages. Allowed
characters are passed unmodified; all others are written in their
hexadecimal representation prefixed with *\\x*. There are three
supported filter types:

-   <span class="simpara">*all* – all characters</span>
-   <span class="simpara">*no-ctrl* – all characters except control
    characters</span>
-   <span class="simpara">*ascii* – all printable ASCII characters and
    *NL*</span>

Only effective if
<a href="/errorfunc/setup.html#" class="link">error_log</a> is set to
"syslog".

`syslog.ident` <span class="type">string</span>  
Specifies the ident string which is prepended to every message. Only
effective if <a href="/errorfunc/setup.html#" class="link">error_log</a>
is set to "syslog".

Resource Types
--------------

This extension has no resource types defined.

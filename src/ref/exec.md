Notes
-----

**Warning**

Open files with lock (especially open sessions) should be closed before
executing a program in the background.

See Also
--------

These functions are also closely related to the
<a href="/language/operators/execution.html" class="link">backtick operator</a>.

escapeshellarg
==============

Escape a string to be used as a shell argument

### Description

<span class="type">string</span> <span
class="methodname">escapeshellarg</span> ( <span
class="methodparam"><span class="type">string</span> `$arg`</span> )

<span class="function">escapeshellarg</span> adds single quotes around a
string and quotes/escapes any existing single quotes allowing you to
pass a string directly to a shell function and having it be treated as a
single safe argument. This function should be used to escape individual
arguments to shell functions coming from user input. The shell functions
include <span class="function">exec</span>, <span
class="function">system</span> and the
<a href="/language/operators/execution.html" class="link">backtick operator</a>.

On Windows, <span class="function">escapeshellarg</span> instead
replaces percent signs, exclamation marks (delayed variable
substitution) and double quotes with spaces and adds double quotes
around the string.

### Parameters

`arg`  
The argument that will be escaped.

### Return Values

The escaped string.

### Examples

**Example \#1 <span class="function">escapeshellarg</span> example**

``` php
<?php
system('ls '.escapeshellarg($dir));
?>
```

### See Also

-   <span class="function">escapeshellcmd</span>
-   <span class="function">exec</span>
-   <span class="function">popen</span>
-   <span class="function">system</span>
-   <a href="/language/operators/execution.html" class="link">backtick operator</a>

escapeshellcmd
==============

Escape shell metacharacters

### Description

<span class="type">string</span> <span
class="methodname">escapeshellcmd</span> ( <span
class="methodparam"><span class="type">string</span> `$command`</span> )

<span class="function">escapeshellcmd</span> escapes any characters in a
string that might be used to trick a shell command into executing
arbitrary commands. This function should be used to make sure that any
data coming from user input is escaped before this data is passed to the
<span class="function">exec</span> or <span
class="function">system</span> functions, or to the
<a href="/language/operators/execution.html" class="link">backtick operator</a>.

Following characters are preceded by a backslash:
*&\#;\`\|\*?\~\<\>^()\[\]{}$\\*, *\\x0A* and *\\xFF*. *'* and *"* are
escaped only if they are not paired. On Windows, all these characters
plus *%* and *!* are preceded by a caret (*^*).

### Parameters

`command`  
The command that will be escaped.

### Return Values

The escaped string.

### Examples

**Example \#1 <span class="function">escapeshellcmd</span> example**

``` php
<?php
// We allow arbitrary number of arguments intentionally here.
$command = './configure '.$_POST['configure_options'];

$escaped_command = escapeshellcmd($command);
 
system($escaped_command);
?>
```

**Warning**

<span class="function">escapeshellcmd</span> should be used on the whole
command string, and it still allows the attacker to pass arbitrary
number of arguments. For escaping a single argument <span
class="function">escapeshellarg</span> should be used instead.

### See Also

-   <span class="function">escapeshellarg</span>
-   <span class="function">exec</span>
-   <span class="function">popen</span>
-   <span class="function">system</span>
-   <a href="/language/operators/execution.html" class="link">backtick operator</a>

exec
====

Execute an external program

### Description

<span class="type">string</span> <span class="methodname">exec</span> (
<span class="methodparam"><span class="type">string</span>
`$command`</span> \[, <span class="methodparam"><span
class="type">array</span> `&$output`</span> \[, <span
class="methodparam"><span class="type">int</span> `&$return_var`</span>
\]\] )

<span class="function">exec</span> executes the given `command`.

### Parameters

`command`  
The command that will be executed.

`output`  
If the `output` argument is present, then the specified array will be
filled with every line of output from the command. Trailing whitespace,
such as *\\n*, is not included in this array. Note that if the array
already contains some elements, <span class="function">exec</span> will
append to the end of the array. If you do not want the function to
append elements, call <span class="function">unset</span> on the array
before passing it to <span class="function">exec</span>.

`return_var`  
If the `return_var` argument is present along with the `output`
argument, then the return status of the executed command will be written
to this variable.

### Return Values

The last line from the result of the command. If you need to execute a
command and have all the data from the command passed directly back
without any interference, use the <span class="function">passthru</span>
function.

To get the output of the executed command, be sure to set and use the
`output` parameter.

### Examples

**Example \#1 An <span class="function">exec</span> example**

``` php
<?php
// outputs the username that owns the running php/httpd process
// (on a system with the "whoami" executable in the path)
echo exec('whoami');
?>
```

### Notes

**Warning**

When allowing user-supplied data to be passed to this function, use
<span class="function">escapeshellarg</span> or <span
class="function">escapeshellcmd</span> to ensure that users cannot trick
the system into executing arbitrary commands.

> **Note**:
>
> If a program is started with this function, in order for it to
> continue running in the background, the output of the program must be
> redirected to a file or another output stream. Failing to do so will
> cause PHP to hang until the execution of the program ends.

> **Note**:
>
> On Windows <span class="function">exec</span> will first start cmd.exe
> to launch the command. If you want to start an external program
> without starting cmd.exe use <span class="function">proc\_open</span>
> with the `bypass_shell` option set.

### See Also

-   <span class="function">system</span>
-   <span class="function">passthru</span>
-   <span class="function">escapeshellcmd</span>
-   <span class="function">pcntl\_exec</span>
-   <a href="/language/operators/execution.html" class="link">backtick operator</a>

passthru
========

Execute an external program and display raw output

### Description

<span class="type">void</span> <span class="methodname">passthru</span>
( <span class="methodparam"><span class="type">string</span>
`$command`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$return_var`</span> \] )

The <span class="function">passthru</span> function is similar to the
<span class="function">exec</span> function in that it executes a
`command`. This function should be used in place of <span
class="function">exec</span> or <span class="function">system</span>
when the output from the Unix command is binary data which needs to be
passed directly back to the browser. A common use for this is to execute
something like the pbmplus utilities that can output an image stream
directly. By setting the Content-type to *image/gif* and then calling a
pbmplus program to output a gif, you can create PHP scripts that output
images directly.

### Parameters

`command`  
The command that will be executed.

`return_var`  
If the `return_var` argument is present, the return status of the Unix
command will be placed here.

### Return Values

No value is returned.

### Notes

**Warning**

When allowing user-supplied data to be passed to this function, use
<span class="function">escapeshellarg</span> or <span
class="function">escapeshellcmd</span> to ensure that users cannot trick
the system into executing arbitrary commands.

> **Note**:
>
> If a program is started with this function, in order for it to
> continue running in the background, the output of the program must be
> redirected to a file or another output stream. Failing to do so will
> cause PHP to hang until the execution of the program ends.

### See Also

-   <span class="function">exec</span>
-   <span class="function">system</span>
-   <span class="function">popen</span>
-   <span class="function">escapeshellcmd</span>
-   <a href="/language/operators/execution.html" class="link">backtick operator</a>

proc\_close
===========

Close a process opened by <span class="function">proc\_open</span> and
return the exit code of that process

### Description

<span class="type">int</span> <span
class="methodname">proc\_close</span> ( <span class="methodparam"><span
class="type">resource</span> `$process`</span> )

<span class="function">proc\_close</span> is similar to <span
class="function">pclose</span> except that it only works on processes
opened by <span class="function">proc\_open</span>. <span
class="function">proc\_close</span> waits for the process to terminate,
and returns its exit code. Open pipes to that process are closed when
this function is called, in order to avoid a deadlock - the child
process may not be able to exit while the pipes are open.

### Parameters

`process`  
The <span class="function">proc\_open</span> <span
class="type">resource</span> that will be closed.

### Return Values

Returns the termination status of the process that was run. In case of
an error then *-1* is returned.

> **Note**:
>
> If PHP has been compiled with --enable-sigchild, the return value of
> this function is undefined.

proc\_get\_status
=================

Get information about a process opened by <span
class="function">proc\_open</span>

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">proc\_get\_status</span> ( <span
class="methodparam"><span class="type">resource</span> `$process`</span>
)

<span class="function">proc\_get\_status</span> fetches data about a
process opened using <span class="function">proc\_open</span>.

### Parameters

`process`  
The <span class="function">proc\_open</span> <span
class="type">resource</span> that will be evaluated.

### Return Values

An <span class="type">array</span> of collected information on success,
and **`FALSE`** on failure. The returned array contains the following
elements:

| element  | type                             | description                                                                                                                                                               |
|----------|----------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| command  | <span class="type">string</span> | The command string that was passed to <span class="function">proc\_open</span>.                                                                                           |
| pid      | <span class="type">int</span>    | process id                                                                                                                                                                |
| running  | <span class="type">bool</span>   | **`TRUE`** if the process is still running, **`FALSE`** if it has terminated.                                                                                             |
| signaled | <span class="type">bool</span>   | **`TRUE`** if the child process has been terminated by an uncaught signal. Always set to **`FALSE`** on Windows.                                                          |
| stopped  | <span class="type">bool</span>   | **`TRUE`** if the child process has been stopped by a signal. Always set to **`FALSE`** on Windows.                                                                       |
| exitcode | <span class="type">int</span>    | The exit code returned by the process (which is only meaningful if *running* is **`FALSE`**). Only first call of this function return real value, next calls return *-1*. |
| termsig  | <span class="type">int</span>    | The number of the signal that caused the child process to terminate its execution (only meaningful if *signaled* is **`TRUE`**).                                          |
| stopsig  | <span class="type">int</span>    | The number of the signal that caused the child process to stop its execution (only meaningful if *stopped* is **`TRUE`**).                                                |

### See Also

-   <span class="function">proc\_open</span>

proc\_nice
==========

Change the priority of the current process

### Description

<span class="type">bool</span> <span
class="methodname">proc\_nice</span> ( <span class="methodparam"><span
class="type">int</span> `$increment`</span> )

<span class="function">proc\_nice</span> changes the priority of the
current process by the amount specified in `increment`. A positive
`increment` will lower the priority of the current process, whereas a
negative `increment` will raise the priority.

<span class="function">proc\_nice</span> is not related to <span
class="function">proc\_open</span> and its associated functions in any
way.

### Parameters

`increment`  
The new priority value, the value of this may differ on platforms.

On Unix, a low value, such as *-20* means high priority wheras a
positive value have a lower priority.

For Windows the `increment` parameter have the following meanings:

| Priority class        | Possible values                          |
|-----------------------|------------------------------------------|
| High priority         | `increment` *\< -9*                      |
| Above normal priority | `increment` *\< -4*                      |
| Normal priority       | `increment` *\< 5* & `increment` *\> -5* |
| Below normal priority | `increment` *\> 5*                       |
| Idle priority         | `increment` *\> 9*                       |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. If an error
occurs, like the user lacks permission to change the priority, an error
of level **`E_WARNING`** is also generated.

### Examples

**Example \#1 Using <span class="function">proc\_nice</span> to set the
process priority to high**

``` php
<?php
// Highest priority
proc_nice(-20);
?>
```

### Changelog

| Version | Description                                |
|---------|--------------------------------------------|
| 7.2.0   | This function is now available on Windows. |

### Notes

> **Note**: **Availability**  
>
> <span class="function">proc\_nice</span> will only exist if your
> system has 'nice' capabilities. 'nice' conforms to: SVr4, SVID EXT,
> AT&T, X/OPEN, BSD 4.3.

> **Note**: **Windows only**  
>
> <span class="function">proc\_nice</span> will change the *current*
> process priority, even if PHP was compiled using thread safety.

proc\_open
==========

Execute a command and open file pointers for input/output

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">proc\_open</span> ( <span class="methodparam"><span
class="type">mixed</span> `$cmd`</span> , <span
class="methodparam"><span class="type">array</span>
`$descriptorspec`</span> , <span class="methodparam"><span
class="type">array</span> `&$pipes`</span> \[, <span
class="methodparam"><span class="type">string</span> `$cwd`<span
class="initializer"> = **`NULL`**</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$env`<span
class="initializer"> = **`NULL`**</span></span> \[, <span
class="methodparam"><span class="type">array</span>
`$other_options`<span class="initializer"> = **`NULL`**</span></span>
\]\]\] )

<span class="function">proc\_open</span> is similar to <span
class="function">popen</span> but provides a much greater degree of
control over the program execution.

### Parameters

`cmd`  
The commandline to execute as <span class="type">string</span>. Special
characters have to be properly escaped, and proper quoting has to be
applied.

> **Note**: <span class="simpara"> On *Windows*, unless *bypass\_shell*
> is set to **`TRUE`** in `other_options`, the `cmd` is passed to
> **cmd.exe** (actually, *%ComSpec%*) with the */c* flag as *unquoted*
> string (i.e. exactly as has been given to <span
> class="function">proc\_open</span>). This can cause **cmd.exe** to
> remove enclosing quotes from `cmd` (for details see the **cmd.exe**
> documentation), resulting in unexpected, and potentially even
> dangerous behavior, because **cmd.exe** error messages may contain
> (parts of) the passed `cmd` (see example below). </span>

As of PHP 7.4.0, `cmd` may be passed as <span class="type">array</span>
of command parameters. In this case the process will be opened directly
(without going through a shell) and PHP will take care of any necessary
argument escaping.

> **Note**:
>
> On Windows, the argument escaping of the <span
> class="type">array</span> elements assumes that the command line
> parsing of the executed command is compatible with the parsing of
> command line arguments done by the VC runtime.

`descriptorspec`  
An indexed array where the key represents the descriptor number and the
value represents how PHP will pass that descriptor to the child process.
0 is stdin, 1 is stdout, while 2 is stderr.

Each element can be:

-   An array describing the pipe to pass to the process. The first
    element is the descriptor type and the second element is an option
    for the given type. Valid types are *pipe* (the second element is
    either *r* to pass the read end of the pipe to the process, or *w*
    to pass the write end) and *file* (the second element is a
    filename).
-   A stream resource representing a real file descriptor (e.g. opened
    file, a socket, **`STDIN`**).

The file descriptor numbers are not limited to 0, 1 and 2 - you may
specify any valid file descriptor number and it will be passed to the
child process. This allows your script to interoperate with other
scripts that run as "co-processes". In particular, this is useful for
passing passphrases to programs like PGP, GPG and openssl in a more
secure manner. It is also useful for reading status information provided
by those programs on auxiliary file descriptors.

`pipes`  
Will be set to an indexed array of file pointers that correspond to
PHP's end of any pipes that are created.

`cwd`  
The initial working dir for the command. This must be an *absolute*
directory path, or **`NULL`** if you want to use the default value (the
working dir of the current PHP process)

`env`  
An array with the environment variables for the command that will be
run, or **`NULL`** to use the same environment as the current PHP
process

`other_options`  
Allows you to specify additional options. Currently supported options
include:

-   *suppress\_errors* (windows only): suppresses errors generated by
    this function when it's set to **`TRUE`**
-   *bypass\_shell* (windows only): bypass *cmd.exe* shell when set to
    **`TRUE`**
-   *blocking\_pipes* (windows only): force blocking pipes when set to
    **`TRUE`**
-   *create\_process\_group* (windows only): allow the child process to
    handle *CTRL* events when set to **`TRUE`**
-   *create\_new\_console* (windows only): the new process has a new
    console, instead of inheriting its parent's console

### Return Values

Returns a resource representing the process, which should be freed using
<span class="function">proc\_close</span> when you are finished with it.
On failure returns **`FALSE`**.

### Changelog

| Version | Description                                                                                                 |
|---------|-------------------------------------------------------------------------------------------------------------|
| 7.4.4   | Added the *create\_new\_console* option to the `other_options` parameter.                                   |
| 7.4.0   | <span class="function">proc\_open</span> now also accepts an <span class="type">array</span> for the `cmd`. |
| 7.4.0   | Added the *create\_process\_group* option to the `other_options` parameter.                                 |

### Examples

**Example \#1 A <span class="function">proc\_open</span> example**

``` php
<?php
$descriptorspec = array(
   0 => array("pipe", "r"),  // stdin is a pipe that the child will read from
   1 => array("pipe", "w"),  // stdout is a pipe that the child will write to
   2 => array("file", "/tmp/error-output.txt", "a") // stderr is a file to write to
);

$cwd = '/tmp';
$env = array('some_option' => 'aeiou');

$process = proc_open('php', $descriptorspec, $pipes, $cwd, $env);

if (is_resource($process)) {
    // $pipes now looks like this:
    // 0 => writeable handle connected to child stdin
    // 1 => readable handle connected to child stdout
    // Any error output will be appended to /tmp/error-output.txt

    fwrite($pipes[0], '<?php print_r($_ENV); ?>');
    fclose($pipes[0]);

    echo stream_get_contents($pipes[1]);
    fclose($pipes[1]);

    // It is important that you close any pipes before calling
    // proc_close in order to avoid a deadlock
    $return_value = proc_close($process);

    echo "command returned $return_value\n";
}
?>
```

The above example will output something similar to:

    Array
    (
        [some_option] => aeiou
        [PWD] => /tmp
        [SHLVL] => 1
        [_] => /usr/local/bin/php
    )
    command returned 0

**Example \#2 <span class="function">proc\_open</span> quirk on
Windows**

While one may expect the following program to search the file
`filename.txt` for the text *search* and to print the results, it
behaves rather differently.

``` php
<?php
$descriptorspec = [STDIN, STDOUT, STDOUT];
$cmd = '"findstr" "search" "filename.txt"';
$proc = proc_open($cmd, $descriptorspec, $pipes);
proc_close($proc);
?>
```

The above example will output:

    'findstr" "search" "filename.txt' is not recognized as an internal or external command,
    operable program or batch file.

To work around that behavior, it is usually sufficient to enclose the
`cmd` in additional quotes:

``` php
$cmd = '""findstr" "search" "filename.txt""';
```

### Notes

> **Note**:
>
> Windows compatibility: Descriptors beyond 2 (stderr) are made
> available to the child process as inheritable handles, but since the
> Windows architecture does not associate file descriptor numbers with
> low-level handles, the child process does not (yet) have a means of
> accessing those handles. Stdin, stdout and stderr work as expected.

> **Note**:
>
> If you only need a uni-directional (one-way) process pipe, use <span
> class="function">popen</span> instead, as it is much easier to use.

### See Also

-   <span class="function">popen</span>
-   <span class="function">exec</span>
-   <span class="function">system</span>
-   <span class="function">passthru</span>
-   <span class="function">stream\_select</span>
-   The
    <a href="/language/operators/execution.html" class="link">backtick operator</a>

proc\_terminate
===============

Kills a process opened by proc\_open

### Description

<span class="type">bool</span> <span
class="methodname">proc\_terminate</span> ( <span
class="methodparam"><span class="type">resource</span> `$process`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$signal`<span class="initializer"> = 15</span></span> \] )

Signals a `process` (created using <span
class="function">proc\_open</span>) that it should terminate. <span
class="function">proc\_terminate</span> returns immediately and does not
wait for the process to terminate.

<span class="function">proc\_terminate</span> allows you terminate the
process and continue with other tasks. You may poll the process (to see
if it has stopped yet) by using the <span
class="function">proc\_get\_status</span> function.

### Parameters

`process`  
The <span class="function">proc\_open</span> <span
class="type">resource</span> that will be closed.

`signal`  
This optional parameter is only useful on POSIX operating systems; you
may specify a signal to send to the process using the *kill(2)* system
call. The default is *SIGTERM*.

### Return Values

Returns the termination status of the process that was run.

### See Also

-   <span class="function">proc\_open</span>
-   <span class="function">proc\_close</span>
-   <span class="function">proc\_get\_status</span>

shell\_exec
===========

Execute command via shell and return the complete output as a string

### Description

<span class="type"><span class="type">string</span><span
class="type">null</span></span> <span
class="methodname">shell\_exec</span> ( <span class="methodparam"><span
class="type">string</span> `$cmd`</span> )

This function is identical to the
<a href="/language/operators/execution.html" class="link">backtick operator</a>.

> **Note**:
>
> On Windows, the underlying pipe is opened in text mode which can cause
> the function to fail for binary output. Consider to use <span
> class="function">popen</span> instead for such cases.

### Parameters

`cmd`  
The command that will be executed.

### Return Values

The output from the executed command or **`NULL`** if an error occurred
or the command produces no output.

> **Note**:
>
> This function can return **`NULL`** both when an error occurs or the
> program produces no output. It is not possible to detect execution
> failures using this function. <span class="function">exec</span>
> should be used when access to the program exit code is required.

### Examples

**Example \#1 A <span class="function">shell\_exec</span> example**

``` php
<?php
$output = shell_exec('ls -lart');
echo "<pre>$output</pre>";
?>
```

### See Also

-   <span class="function">exec</span>
-   <span class="function">escapeshellcmd</span>

system
======

Execute an external program and display the output

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span class="methodname">system</span>
( <span class="methodparam"><span class="type">string</span>
`$command`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$return_var`</span> \] )

<span class="function">system</span> is just like the C version of the
function in that it executes the given `command` and outputs the result.

The <span class="function">system</span> call also tries to
automatically flush the web server's output buffer after each line of
output if PHP is running as a server module.

If you need to execute a command and have all the data from the command
passed directly back without any interference, use the <span
class="function">passthru</span> function.

### Parameters

`command`  
The command that will be executed.

`return_var`  
If the `return_var` argument is present, then the return status of the
executed command will be written to this variable.

### Return Values

Returns the last line of the command output on success, and **`FALSE`**
on failure.

### Examples

**Example \#1 <span class="function">system</span> example**

``` php
<?php
echo '<pre>';

// Outputs all the result of shellcommand "ls", and returns
// the last output line into $last_line. Stores the return value
// of the shell command in $retval.
$last_line = system('ls', $retval);

// Printing additional info
echo '
</pre>
<hr />Last line of the output: ' . $last_line . '
<hr />Return value: ' . $retval;
?>
```

### Notes

**Warning**

When allowing user-supplied data to be passed to this function, use
<span class="function">escapeshellarg</span> or <span
class="function">escapeshellcmd</span> to ensure that users cannot trick
the system into executing arbitrary commands.

> **Note**:
>
> If a program is started with this function, in order for it to
> continue running in the background, the output of the program must be
> redirected to a file or another output stream. Failing to do so will
> cause PHP to hang until the execution of the program ends.

### See Also

-   <span class="function">exec</span>
-   <span class="function">passthru</span>
-   <span class="function">popen</span>
-   <span class="function">escapeshellcmd</span>
-   <span class="function">pcntl\_exec</span>
-   <a href="/language/operators/execution.html" class="link">backtick operator</a>

**Table of Contents**

-   [escapeshellarg](/ref/exec.html#escapeshellarg) — Escape a string to
    be used as a shell argument
-   [escapeshellcmd](/ref/exec.html#escapeshellcmd) — Escape shell
    metacharacters
-   [exec](/ref/exec.html#exec) — Execute an external program
-   [passthru](/ref/exec.html#passthru) — Execute an external program
    and display raw output
-   [proc\_close](/ref/exec.html#proc_close) — Close a process opened by
    proc\_open and return the exit code of that process
-   [proc\_get\_status](/ref/exec.html#proc_get_status) — Get
    information about a process opened by proc\_open
-   [proc\_nice](/ref/exec.html#proc_nice) — Change the priority of the
    current process
-   [proc\_open](/ref/exec.html#proc_open) — Execute a command and open
    file pointers for input/output
-   [proc\_terminate](/ref/exec.html#proc_terminate) — Kills a process
    opened by proc\_open
-   [shell\_exec](/ref/exec.html#shell_exec) — Execute command via shell
    and return the complete output as a string
-   [system](/ref/exec.html#system) — Execute an external program and
    display the output

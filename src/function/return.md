return
------

*return* returns program control to the calling module. Execution
resumes at the expression following the called module's invocation.

If called from within a function, the *return* statement immediately
ends execution of the current function, and returns its argument as the
value of the function call. *return* also ends the execution of an <span
class="function">eval</span> statement or script file.

If called from the global scope, then execution of the current script
file is ended. If the current script file was <span
class="function">include</span>d or <span
class="function">require</span>d, then control is passed back to the
calling file. Furthermore, if the current script file was <span
class="function">include</span>d, then the value given to *return* will
be returned as the value of the <span class="function">include</span>
call. If *return* is called from within the main script file, then
script execution ends. If the current script file was named by the
<a href="/ini/core.html#ini.auto-prepend-file" class="link">auto_prepend_file</a>
or
<a href="/ini/core.html#ini.auto-append-file" class="link">auto_append_file</a>
configuration options in `php.ini`, then that script file's execution is
ended.

For more information, see
<a href="/functions/returning-values.html" class="link">Returning values</a>.

> **Note**: <span class="simpara"> Note that since *return* is a
> language construct and not a function, the parentheses surrounding its
> argument are not required and their use is discouraged. </span>

> **Note**: <span class="simpara"> If no parameter is supplied, then the
> parentheses must be omitted and **`NULL`** will be returned. Calling
> *return* with parentheses but with no arguments will result in a parse
> error. </span>

As of PHP 7.1.0, return statements without an argument trigger
**`E_COMPILE_ERROR`**, unless the return type is <span
class="type">void</span>, in which case return statements with an
argument trigger that error.

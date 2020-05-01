Using PHP and DTrace
--------------------

PHP can be configured with DTrace static probes on platforms that
support DTrace Dynamic Tracing.

### Configuring PHP for DTrace Static Probes

Refer to external platform specific documentation for enabling operating
system DTrace support. For example, on Oracle Linux boot a UEK3 kernel
and do:

``` php
# modprobe fasttrap
# chmod 666 /dev/dtrace/helper
```

Instead of using *chmod*, you could instead use an ACL package rule to
limit device access to a specific user.

Build PHP with the *--enable-dtrace* configuration parameter:

``` php
# ./configure --enable-dtrace ...
# make
# make install
```

This enables the static probes in core PHP. Any PHP extensions that
provide their own probes should be built separately as shared
extensions.

### DTrace Static Probes in Core PHP

| Probe Name            | Probe Description                                                                                                                                          | Probe Arguments                                                                                 |
|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|
| *request-startup*     | Fires when a request starts.                                                                                                                               | char \*`file`, char \*`request_uri`, char \*`request_method`                                    |
| *request-shutdown*    | Fires when a request shutdown.                                                                                                                             | char \*`file`, char \*`request_uri`, char \*`request_method`                                    |
| *compile-file-entry*  | Fires when the compilation of a script starts.                                                                                                             | char \*`compile_file`, char \*`compile_file_translated`                                         |
| *compile-file-return* | Fires when the compilation of a script finishes.                                                                                                           | char \*`compile_file`, char \*`compile_file_translated`                                         |
| *execute-entry*       | Fires when an opcode array is to be executed. For example, it fires on function calls, includes, and generator resumes.                                    | char \*`request_file`, int `lineno`                                                             |
| *execute-return*      | Fires after execution of an opcode array.                                                                                                                  | char \*`request_file`, int `lineno`                                                             |
| *function-entry*      | Fires when the PHP engine enters a PHP function or method call.                                                                                            | char \*`function_name`, char \*`request_file`, int `lineno`, char \*`classname`, char \*`scope` |
| *function-return*     | Fires when the PHP engine returns from a PHP function or method call.                                                                                      | char \*`function_name`, char \*`request_file`, int `lineno`, char \*`classname`, char \*`scope` |
| *exception-thrown*    | Fires when an exception is thrown.                                                                                                                         | char \*`classname`                                                                              |
| *exception-caught*    | Fires when an exception is caught.                                                                                                                         | char \*`classname`                                                                              |
| *error*               | Fires when an error occurs, regardless of the <a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a> level. | char \*`errormsg`, char \*`request_file`, int `lineno`                                          |

PHP extensions may also have additional static probes.

### Listing DTrace Static Probes in PHP

To list available probes, start a PHP process and then run:

    # dtrace -l

The output will be similar to:

       ID   PROVIDER            MODULE                          FUNCTION NAME
       [ . . . ]
        4   php15271               php               dtrace_compile_file compile-file-entry
        5   php15271               php               dtrace_compile_file compile-file-return
        6   php15271               php                        zend_error error
        7   php15271               php  ZEND_CATCH_SPEC_CONST_CV_HANDLER exception-caught
        8   php15271               php     zend_throw_exception_internal exception-thrown
        9   php15271               php                 dtrace_execute_ex execute-entry
       10   php15271               php           dtrace_execute_internal execute-entry
       11   php15271               php                 dtrace_execute_ex execute-return
       12   php15271               php           dtrace_execute_internal execute-return
       13   php15271               php                 dtrace_execute_ex function-entry
       14   php15271               php                 dtrace_execute_ex function-return
       15   php15271               php              php_request_shutdown request-shutdown
       16   php15271               php               php_request_startup request-startup

The Provider column values consist of *php* and the process id of the
currently running PHP process.

If the Apache web server is running, the module name might be, for
example, `libphp5.so`, and there would be multiple blocks of listings,
one per running Apache process.

The Function column refers to PHP's internal C implementation function
names where each provider is located.

If a PHP process is not running, then no PHP probes will be shown.

### DTrace with PHP Example

This example shows the basics of the DTrace D scripting language.

**Example \#1 `all_probes.d` for tracing all PHP Static Probes with
DTrace**

    #!/usr/sbin/dtrace -Zs

    #pragma D option quiet

    php*:::compile-file-entry
    {
        printf("PHP compile-file-entry\n");
        printf("  compile_file              %s\n", copyinstr(arg0));
        printf("  compile_file_translated   %s\n", copyinstr(arg1));
    }

    php*:::compile-file-return
    {
        printf("PHP compile-file-return\n");
        printf("  compile_file              %s\n", copyinstr(arg0));
        printf("  compile_file_translated   %s\n", copyinstr(arg1));
    }

    php*:::error
    {
        printf("PHP error\n");
        printf("  errormsg                  %s\n", copyinstr(arg0));
        printf("  request_file              %s\n", copyinstr(arg1));
        printf("  lineno                    %d\n", (int)arg2);
    }

    php*:::exception-caught
    {
        printf("PHP exception-caught\n");
        printf("  classname                 %s\n", copyinstr(arg0));
    }

    php*:::exception-thrown
    {
        printf("PHP exception-thrown\n");
        printf("  classname                 %s\n", copyinstr(arg0));
    }

    php*:::execute-entry
    {
        printf("PHP execute-entry\n");
        printf("  request_file              %s\n", copyinstr(arg0));
        printf("  lineno                    %d\n", (int)arg1);
    }

    php*:::execute-return
    {
        printf("PHP execute-return\n");
        printf("  request_file              %s\n", copyinstr(arg0));
        printf("  lineno                    %d\n", (int)arg1);
    }

    php*:::function-entry
    {
        printf("PHP function-entry\n");
        printf("  function_name             %s\n", copyinstr(arg0));
        printf("  request_file              %s\n", copyinstr(arg1));
        printf("  lineno                    %d\n", (int)arg2);
        printf("  classname                 %s\n", copyinstr(arg3));
        printf("  scope                     %s\n", copyinstr(arg4));
    }

    php*:::function-return
    {
        printf("PHP function-return\n");
        printf("  function_name             %s\n", copyinstr(arg0));
        printf("  request_file              %s\n", copyinstr(arg1));
        printf("  lineno                    %d\n", (int)arg2);
        printf("  classname                 %s\n", copyinstr(arg3));
        printf("  scope                     %s\n", copyinstr(arg4));
    }

    php*:::request-shutdown
    {
        printf("PHP request-shutdown\n");
        printf("  file                      %s\n", copyinstr(arg0));
        printf("  request_uri               %s\n", copyinstr(arg1));
        printf("  request_method            %s\n", copyinstr(arg2));
    }

    php*:::request-startup
    {
        printf("PHP request-startup\n");
        printf("  file                      %s\n", copyinstr(arg0));
        printf("  request_uri               %s\n", copyinstr(arg1));
        printf("  request_method            %s\n", copyinstr(arg2));
    }

This script uses the *-Z* option to `dtrace`, allowing it to be run when
there is no PHP process executing. If this option were omitted the
script would immediately terminate because it knows none of the probes
to be monitored are in existence.

The script traces all core PHP static probe points throughout the
duration of a running PHP script. Run the D script:

    # ./all_probes.d

Run a PHP script or application. The monitoring D script will output
each probe's arguments as it fires.

When monitoring is complete, the D script can be terminated with a *^C*.

On multi-CPU machines the probe ordering might not appear to be
sequential. This depends on which CPU was processing the probes, and how
threads migrate across CPUs. Displaying probe time stamps will help
reduce confusion, for example:

    php*:::function-entry
    {
          printf("%lld: PHP function-entry ", walltimestamp);
          [ . . .]
    }

### See Also

-   <a href="/book/oci8.html#OCI8%20and%20DTrace%20Dynamic%20Tracing" class="link">OCI8 and DTrace Dynamic Tracing</a>

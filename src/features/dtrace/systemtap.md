Using SystemTap with PHP DTrace Static Probes
---------------------------------------------

On some Linux distributions, the SystemTap tracing utility can be used
to trace PHP's static DTrace probes. This is available with PHP 5.4.20
and PHP 5.5.

### Installing PHP with SystemTap

Install the SystemTap SDT development package:

``` shell
# yum install systemtap-sdt-devel
```

Install PHP with the DTrace probes enabled:

``` shell
# ./configure --enable-dtrace ...
# make
```

### Listing Static Probes with SystemTap

The static probes in PHP can be listed using `stap`:

    # stap -l 'process.provider("php").mark("*")' -c 'sapi/cli/php -i'

This outputs:

    process("sapi/cli/php").provider("php").mark("compile__file__entry")
    process("sapi/cli/php").provider("php").mark("compile__file__return")
    process("sapi/cli/php").provider("php").mark("error")
    process("sapi/cli/php").provider("php").mark("exception__caught")
    process("sapi/cli/php").provider("php").mark("exception__thrown")
    process("sapi/cli/php").provider("php").mark("execute__entry")
    process("sapi/cli/php").provider("php").mark("execute__return")
    process("sapi/cli/php").provider("php").mark("function__entry")
    process("sapi/cli/php").provider("php").mark("function__return")
    process("sapi/cli/php").provider("php").mark("request__shutdown")
    process("sapi/cli/php").provider("php").mark("request__startup")

### SystemTap with PHP Example

**Example \#1 `all_probes.stp` for tracing all PHP Static Probes with
SystemTap**

``` shell
probe process("sapi/cli/php").provider("php").mark("compile__file__entry") {
    printf("Probe compile__file__entry\n");
    printf("  compile_file %s\n", user_string($arg1));
    printf("  compile_file_translated %s\n", user_string($arg2));
}
probe process("sapi/cli/php").provider("php").mark("compile__file__return") {
    printf("Probe compile__file__return\n");
    printf("  compile_file %s\n", user_string($arg1));
    printf("  compile_file_translated %s\n", user_string($arg2));
}
probe process("sapi/cli/php").provider("php").mark("error") {
    printf("Probe error\n");
    printf("  errormsg %s\n", user_string($arg1));
    printf("  request_file %s\n", user_string($arg2));
    printf("  lineno %d\n", $arg3);
}
probe process("sapi/cli/php").provider("php").mark("exception__caught") {
    printf("Probe exception__caught\n");
    printf("  classname %s\n", user_string($arg1));
}
probe process("sapi/cli/php").provider("php").mark("exception__thrown") {
    printf("Probe exception__thrown\n");
    printf("  classname %s\n", user_string($arg1));
}
probe process("sapi/cli/php").provider("php").mark("execute__entry") {
    printf("Probe execute__entry\n");
    printf("  request_file %s\n", user_string($arg1));
    printf("  lineno %d\n", $arg2);
}
probe process("sapi/cli/php").provider("php").mark("execute__return") {
    printf("Probe execute__return\n");
    printf("  request_file %s\n", user_string($arg1));
    printf("  lineno %d\n", $arg2);
}
probe process("sapi/cli/php").provider("php").mark("function__entry") {
    printf("Probe function__entry\n");
    printf("  function_name %s\n", user_string($arg1));
    printf("  request_file %s\n", user_string($arg2));
    printf("  lineno %d\n", $arg3);
    printf("  classname %s\n", user_string($arg4));
    printf("  scope %s\n", user_string($arg5));
}
probe process("sapi/cli/php").provider("php").mark("function__return") {
    printf("Probe function__return: %s\n", user_string($arg1));
    printf(" function_name %s\n", user_string($arg1));
    printf("  request_file %s\n", user_string($arg2));
    printf("  lineno %d\n", $arg3);
    printf("  classname %s\n", user_string($arg4));
    printf("  scope %s\n", user_string($arg5));
}
probe process("sapi/cli/php").provider("php").mark("request__shutdown") {
    printf("Probe request__shutdown\n");
    printf("  file %s\n", user_string($arg1));
    printf("  request_uri %s\n", user_string($arg2));
    printf("  request_method %s\n", user_string($arg3));
}
probe process("sapi/cli/php").provider("php").mark("request__startup") {
    printf("Probe request__startup\n");
    printf("  file %s\n", user_string($arg1));
    printf("  request_uri %s\n", user_string($arg2));
    printf("  request_method %s\n", user_string($arg3));
}
```

The above script will trace all core PHP static probe points throughout
the duration of a running PHP script:

    # stap -c 'sapi/cli/php test.php' all_probes.stp

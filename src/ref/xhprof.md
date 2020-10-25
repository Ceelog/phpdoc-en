xhprof\_disable
===============

Stops xhprof profiler

### Description

<span class="type">array</span> <span
class="methodname">xhprof\_disable</span> ( <span
class="methodparam">void</span> )

Stops the profiler, and returns xhprof data from the run.

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of xhprof data, from the run.

### Examples

**Example \#1 <span class="function">xhprof\_disable</span> example**

``` php
<?php
xhprof_enable();

$foo = strlen("foo bar");

$xhprof_data = xhprof_disable();

print_r($xhprof_data);
?>
```

The above example will output something similar to:

    Array
    (
        [main()==>strlen] => Array
            (
                [ct] => 1
                [wt] => 279
            )

        [main()==>xhprof_disable] => Array
            (
                [ct] => 1
                [wt] => 9
            )

        [main()] => Array
            (
                [ct] => 1
                [wt] => 610
            )

    )

xhprof\_enable
==============

Start xhprof profiler

### Description

<span class="type">void</span> <span
class="methodname">xhprof\_enable</span> (\[ <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$options`</span>
\]\] )

Start xhprof profiling.

### Parameters

`flags`  
Optional flags to add additional information to the profiling. See the
<a href="/xhprof/constants.html" class="link">XHprof constants</a> for
further information about these flags, e.g., **`XHPROF_FLAGS_MEMORY`**
to enable memory profiling.

`options`  
An <span class="type">array</span> of optional options, namely, the
'ignored\_functions' option to pass in functions to be ignored during
profiling.

### Return Values

**`NULL`**

### Changelog

| Version           | Description                                 |
|-------------------|---------------------------------------------|
| PECL xhprof 0.9.2 | The optional `options` parameter was added. |

### Examples

**Example \#1 <span class="function">xhprof\_enable</span> examples**

``` php
<?php
// 1. elapsed time + memory + CPU profiling; and ignore built-in (internal) functions
xhprof_enable(XHPROF_FLAGS_NO_BUILTINS | XHPROF_FLAGS_CPU | XHPROF_FLAGS_MEMORY);

// 2. elapsed time profiling; ignore call_user_func* during profiling
xhprof_enable(
    0,
    array('ignored_functions' =>  array('call_user_func',
                                        'call_user_func_array')));
                                       
// 3. elapsed time + memory profiling; ignore call_user_func* during profiling
xhprof_enable(
    XHPROF_FLAGS_MEMORY,
    array('ignored_functions' =>  array('call_user_func',
                                        'call_user_func_array')));
?>
```

### See Also

-   <span class="function">xhprof\_disable</span>
-   <span class="function">xhprof\_sample\_enable</span>
-   <span class="function">memory\_get\_usage</span>
-   <span class="function">getrusage</span>

xhprof\_sample\_disable
=======================

Stops xhprof sample profiler

### Description

<span class="type">array</span> <span
class="methodname">xhprof\_sample\_disable</span> ( <span
class="methodparam">void</span> )

Stops the sample mode xhprof profiler, and

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of xhprof sample data, from the run.

### Examples

**Example \#1 <span class="function">xhprof\_sample\_disable</span>
example**

``` php
<?php
xhprof_sample_enable();

for ($i = 0; $i <= 10000; $i++) {
    $a = strlen($i);
    $b = $i * $a;
    $c = rand();
}

$xhprof_data = xhprof_sample_disable();

print_r($xhprof_data);
?>
```

The above example will output something similar to:

    Array
    (
        [1272935300.800000] => main()
        [1272935300.900000] => main()
    )

xhprof\_sample\_enable
======================

Start XHProf profiling in sampling mode

### Description

<span class="type">void</span> <span
class="methodname">xhprof\_sample\_enable</span> ( <span
class="methodparam">void</span> )

Starts profiling in sample mode, which is a lighter weight version of
<span class="function">xhprof\_enable</span>. The sampling interval is
0.1 seconds, and samples record the full function call stack. The main
use case is when lower overhead is required when doing performance
monitoring and diagnostics.

### Parameters

This function has no parameters.

### Return Values

**`NULL`**

### See Also

-   <span class="function">xhprof\_sample\_disable</span>
-   <span class="function">xhprof\_enable</span>
-   <span class="function">memory\_get\_usage</span>
-   <span class="function">getrusage</span>

**Table of Contents**

-   [xhprof\_disable](/ref/xhprof.html#xhprof_disable) — Stops xhprof
    profiler
-   [xhprof\_enable](/ref/xhprof.html#xhprof_enable) — Start xhprof
    profiler
-   [xhprof\_sample\_disable](/ref/xhprof.html#xhprof_sample_disable) —
    Stops xhprof sample profiler
-   [xhprof\_sample\_enable](/ref/xhprof.html#xhprof_sample_enable) —
    Start XHProf profiling in sampling mode

Examples
========

**Example \#1 Xhprof example with the optional GUI**

This example starts and stops the profiler, then uses the bundled GUI
interface to save and parse the results. In other words, the code from
the extension itself ends at the call to <span
class="function">xhprof\_disable</span>.

``` php
<?php
xhprof_enable(XHPROF_FLAGS_CPU + XHPROF_FLAGS_MEMORY);

for ($i = 0; $i <= 1000; $i++) {
    $a = $i * $i;
}

$xhprof_data = xhprof_disable();

$XHPROF_ROOT = "/tools/xhprof/";
include_once $XHPROF_ROOT . "/xhprof_lib/utils/xhprof_lib.php";
include_once $XHPROF_ROOT . "/xhprof_lib/utils/xhprof_runs.php";

$xhprof_runs = new XHProfRuns_Default();
$run_id = $xhprof_runs->save_run($xhprof_data, "xhprof_testing");

echo "http://localhost/xhprof/xhprof_html/index.php?run={$run_id}&source=xhprof_testing\n";

?>
```

The above example will output something similar to:

    http://localhost/xhprof/xhprof_html/index.php?run=t11_4bdf44d21121f&source=xhprof_testing

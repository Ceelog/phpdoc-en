Examples
========

**Table of Contents**

-   [Basic usage](/swish/examples.html#Basic%20usage)

Basic usage
-----------

**Example \#1 Basic search query**

``` php
<?php

try {

    $swish = new Swish("index.swish-e");
    $results = $swish->query("test OR text");

    echo "Found ", $results->hits, " results\n";
    while ($result = $results->nextResult()) {
        var_dump($result);
        break; //break after the first result
    }

} catch (SwishException $e) {
    echo "Error: ", $e->getMessage(), "\n";
}

?>
```

The above example will output something similar to:

    Found 9 results
    object(SwishResult)#3 (8) {
      ["swishreccount"]=>
      int(1)
      ["swishrank"]=>
      int(1000)
      ["swishfilenum"]=>
      int(10)
      ["swishdbfile"]=>
      string(13) "index.swish-e"
      ["swishdocpath"]=>
      string(23) "README.SUBMITTING_PATCH"
      ["swishtitle"]=>
      NULL
      ["swishdocsize"]=>
      int(4557)
      ["swishlastmodified"]=>
      int(1072136752)
    }

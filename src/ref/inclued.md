inclued\_get\_data
==================

Get the inclued data

### Description

<span class="type">array</span> <span
class="methodname">inclued\_get\_data</span> ( <span
class="methodparam">void</span> )

Get the inclued data.

### Parameters

This function has no parameters.

### Return Values

The inclued data.

### Examples

**Example \#1 <span class="function">inclued\_get\_data</span> example**

See the
<a href="/inclued/examples.html#Example%20that%20implements%20inclued%20into%20an%20application" class="link">inclued examples</a>
section for ways to create graphs with this data.

``` php
<?php 
include 'x.php';

$clue = inclued_get_data();

print_r($clue);
?>
```

The above example will output something similar to:

    Array
    (
      [includes] => Array
        (
          [0] => Array
            (
              [operation] => include
              [op_type] => 2
              [filename] => x.php
              [opened_path] => /tmp/x.php
              [fromfile] => /tmp/z.php
              [fromline] => 2
            )
        )
    )

### See Also

-   <a href="/inclued/examples.html#Example%20that%20implements%20inclued%20into%20an%20application" class="link">inclued examples</a>
-   <span class="function">debug\_backtrace</span>
-   <span class="function">include</span>

**Table of Contents**

-   [inclued\_get\_data](/ref/inclued.html#inclued_get_data) — Get the
    inclued data

solr\_get\_version
==================

Returns the current version of the Apache Solr extension

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">solr\_get\_version</span> ( <span
class="methodparam">void</span> )

This function returns the current version of the extension as a string.

### Parameters

This function has no parameters.

### Return Values

It returns a string on success and **`FALSE`** on failure.

### Errors/Exceptions

This function throws no errors or exceptions.

### Examples

**Example \#1 <span class="function">solr\_get\_version</span> example**

``` php
<?php

$solr_version = solr_get_version();

print $solr_version;

?>
```

The above example will output something similar to:

    0.9.6

### See Also

-   <span class="function">SolrUtils::getSolrVersion</span>

**Table of Contents**

-   [solr\_get\_version](/ref/solr.html#solr_get_version) — Returns the
    current version of the Apache Solr extension

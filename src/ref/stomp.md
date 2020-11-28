stomp\_connect\_error
=====================

Returns a string description of the last connect error

### Description

<span class="type"><span class="type">string</span><span
class="type">null</span></span> <span
class="methodname">stomp\_connect\_error</span> ( <span
class="methodparam">void</span> )

Returns a string description of the last connect error.

### Parameters

This function has no parameters.

### Return Values

A string that describes the error, or **`NULL`** if no error occurred.

### Examples

**Example \#1 <span class="function">stomp\_connect\_error</span>
example**

``` php
<?php
$link = stomp_connect('http://localhost:61613');

if(!$link) {
    die('Connection failed: ' . stomp_connect_error());
}
?>
```

The above example will output something similar to:

    Connection failed: Invalid Broker URI scheme

stomp\_version
==============

Gets the current stomp extension version

### Description

<span class="type">string</span> <span
class="methodname">stomp\_version</span> ( <span
class="methodparam">void</span> )

Returns a string containing the version of the current stomp extension.

### Parameters

This function has no parameters.

### Return Values

It returns the current stomp extension version

### Examples

**Example \#1 <span class="function">stomp\_version</span> example**

``` php
<?php

var_dump(stomp_version());

?>
```

The above example will output something similar to:

    string(5) "0.2.0"

**Table of Contents**

-   [stomp\_connect\_error](/ref/stomp.html#stomp_connect_error) —
    Returns a string description of the last connect error
-   [stomp\_version](/ref/stomp.html#stomp_version) — Gets the current
    stomp extension version

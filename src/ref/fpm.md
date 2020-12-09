fastcgi\_finish\_request
========================

Flushes all response data to the client

### Description

<span class="type">bool</span> <span
class="methodname">fastcgi\_finish\_request</span> ( <span
class="methodparam">void</span> )

This function flushes all response data to the client and finishes the
request. This allows for time consuming tasks to be performed without
leaving the connection to the client open.

### Return Values

Returns **`true`** on success or **`false`** on failure.

**Table of Contents**

-   [fastcgi\_finish\_request](/ref/fpm.html#fastcgi_finish_request) —
    Flushes all response data to the client

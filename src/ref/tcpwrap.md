tcpwrap\_check
==============

Performs a tcpwrap check

### Description

<span class="type">bool</span> <span
class="methodname">tcpwrap\_check</span> ( <span
class="methodparam"><span class="type">string</span> `$daemon`</span> ,
<span class="methodparam"><span class="type">string</span>
`$address`</span> \[, <span class="methodparam"><span
class="type">string</span> `$user`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$nodns`<span
class="initializer"> = **`false`**</span></span> \]\] )

This function consults the `/etc/hosts.allow` and `/etc/hosts.deny`
files to check if access to service `daemon` should be granted or denied
for a client.

### Parameters

`daemon`  
The service name.

`address`  
The client remote address. Can be either an IP address or a domain name.

`user`  
An optional user name.

`nodns`  
If `address` looks like domain name then DNS is used to resolve it to IP
address; set `nodns` to **`true`** to avoid this.

### Return Values

This function returns **`true`** if access should be granted,
**`false`** otherwise.

### Examples

**Example \#1 Deny all connections from localhost**

If your `/etc/hosts.deny` file contains:

``` examples
php: 127.0.0.1
```

And your code looks like:

``` php
<?php
if (!tcpwrap_check('php', $_SERVER['REMOTE_ADDR'])) {
  die('You are not welcome here');
}
?>
```

### See Also

For more details please consult hosts\_access(3) man page.

**Table of Contents**

-   [tcpwrap\_check](/ref/tcpwrap.html#tcpwrap_check) — Performs a
    tcpwrap check

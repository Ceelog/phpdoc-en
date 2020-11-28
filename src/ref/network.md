checkdnsrr
==========

Check DNS records corresponding to a given Internet host name or IP
address

### Description

<span class="type">bool</span> <span
class="methodname">checkdnsrr</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> \[, <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = "MX"</span></span> \] )

Searches DNS for records of type `type` corresponding to `host`.

### Parameters

`host`  
`host` may either be the IP address in dotted-quad notation or the host
name.

`type`  
`type` may be any one of: A, MX, NS, SOA, PTR, CNAME, AAAA, A6, SRV,
NAPTR, TXT or ANY.

### Return Values

Returns **`TRUE`** if any records are found; returns **`FALSE`** if no
records were found or if an error occurred.

### Notes

> **Note**:
>
> For compatibility with Windows before this was implemented, then try
> the <a href="https://pear.php.net/" class="link external">» PEAR</a>
> class
> <a href="https://pear.php.net/package/Net_DNS" class="link external">» Net_DNS</a>.

### See Also

-   <span class="function">dns\_get\_record</span>
-   <span class="function">getmxrr</span>
-   <span class="function">gethostbyaddr</span>
-   <span class="function">gethostbyname</span>
-   <span class="function">gethostbynamel</span>
-   the named(8) manual page

closelog
========

Close connection to system logger

### Description

<span class="type">bool</span> <span class="methodname">closelog</span>
( <span class="methodparam">void</span> )

<span class="function">closelog</span> closes the descriptor being used
to write to the system logger. The use of <span
class="function">closelog</span> is optional.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">syslog</span>
-   <span class="function">openlog</span>

define\_syslog\_variables
=========================

Initializes all syslog related variables

### Description

<span class="type">void</span> <span
class="methodname">define\_syslog\_variables</span> ( <span
class="methodparam">void</span> )

Initializes all variables used in the syslog functions.

### Return Values

No value is returned.

| Variable        | Constant equal     | Meaning                   | Notes                                |
|-----------------|--------------------|---------------------------|--------------------------------------|
| `$LOG_EMERG`    | **`LOG_EMERG`**    | System is unusable        |                                      |
| `$LOG_ALERT`    | **`LOG_ALERT`**    | Immediate action required |                                      |
| `$LOG_CRIT`     | **`LOG_CRIT`**     | Critical conditions       |                                      |
| `$LOG_ERR`      | **`LOG_ERR`**      |                           |                                      |
| `$LOG_WARNING`  | **`LOG_WARNING`**  |                           |                                      |
| `$LOG_NOTICE`   | **`LOG_NOTICE`**   |                           |                                      |
| `$LOG_INFO`     | **`LOG_INFO`**     |                           |                                      |
| `$LOG_DEBUG`    | **`LOG_DEBUG`**    |                           |                                      |
| `$LOG_KERN`     | **`LOG_KERN`**     |                           |                                      |
| `$LOG_USER`     | **`LOG_USER`**     | Genetic user level        |                                      |
| `$LOG_MAIL`     | **`LOG_MAIL`**     | Log to email              |                                      |
| `$LOG_DAEMON`   | **`LOG_DAEMON`**   | Other system daemons      |                                      |
| `$LOG_AUTH`     | **`LOG_AUTH`**     |                           |                                      |
| `$LOG_SYSLOG`   | **`LOG_SYSLOG`**   |                           | Not available on Netware             |
| `$LOG_LPR`      | **`LOG_LPR`**      |                           |                                      |
| `$LOG_NEWS`     | **`LOG_NEWS`**     | Usenet new                | Not available on HP-UX               |
| `$LOG_CRON`     | **`LOG_CRON`**     |                           | Not available on all platforms       |
| `$LOG_AUTHPRIV` | **`LOG_AUTHPRIV`** |                           | Not available on AIX                 |
| `$LOG_LOCAL0`   | **`LOG_LOCAL0`**   |                           | Not available on Windows and Netware |
| `$LOG_LOCAL1`   | **`LOG_LOCAL1`**   |                           | Not available on Windows and Netware |
| `$LOG_LOCAL2`   | **`LOG_LOCAL2`**   |                           | Not available on Windows and Netware |
| `$LOG_LOCAL3`   | **`LOG_LOCAL3`**   |                           | Not available on Windows and Netware |
| `$LOG_LOCAL4`   | **`LOG_LOCAL4`**   |                           | Not available on Windows and Netware |
| `$LOG_LOCAL5`   | **`LOG_LOCAL5`**   |                           | Not available on Windows and Netware |
| `$LOG_LOCAL6`   | **`LOG_LOCAL6`**   |                           | Not available on Windows and Netware |
| `$LOG_LOCAL7`   | **`LOG_LOCAL7`**   |                           | Not available on Windows and Netware |
| `$LOG_PID`      | **`LOG_PID`**      |                           |                                      |
| `$LOG_CONS`     | **`LOG_CONS`**     |                           |                                      |
| `$LOG_ODELAY`   | **`LOG_ODELAY`**   |                           |                                      |
| `$LOG_NDELAY`   | **`LOG_NDELAY`**   |                           |                                      |
| `$LOG_NOWAIT`   | **`LOG_NOWAIT`**   |                           | Not available on BeOS                |
| `$LOG_PERROR`   | **`LOG_PERROR`**   |                           | Not available on AIX                 |

**Warning**

This function has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

### Examples

**Example \#1 <span class="function">define\_syslog\_variables</span>
example**

``` php
<?php
// Check if syslog variables already is defined
if(!get_cfg_var('define_syslog_variables'))
{
    define_syslog_variables();
}

// Open the log
openlog('', $LOG_ODELAY, $LOG_MAIL | $LOG_USER);

// Continue script ...
?>
```

### Changelog

| Version | Description                                       |
|---------|---------------------------------------------------|
| 5.4.0   | This function was removed from PHP.               |
| 5.3.0   | This function now throws an E\_DEPRECATED notice. |

### See Also

-   <span class="function">openlog</span>
-   <span class="function">syslog</span>
-   <span class="function">closelog</span>

dns\_check\_record
==================

Alias of <span class="function">checkdnsrr</span>

### Description

This function is an alias of: <span class="function">checkdnsrr</span>.

dns\_get\_mx
============

Alias of <span class="function">getmxrr</span>

### Description

This function is an alias of: <span class="function">getmxrr</span>.

dns\_get\_record
================

Fetch DNS Resource Records associated with a hostname

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">dns\_get\_record</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
\[, <span class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = DNS\_ANY</span></span> \[, <span
class="methodparam"><span class="type">array</span> `&$authns`</span>
\[, <span class="methodparam"><span class="type">array</span>
`&$addtl`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$raw`<span class="initializer"> =
**`FALSE`**</span></span> \]\]\]\] )

Fetch DNS Resource Records associated with the given `hostname`.

### Parameters

`hostname`  
`hostname` should be a valid DNS hostname such as "*www.example.com*".
Reverse lookups can be generated using *in-addr.arpa* notation, but
<span class="function">gethostbyaddr</span> is more suitable for the
majority of reverse lookups.

> **Note**:
>
> Per DNS standards, email addresses are given in *user.host* format
> (for example: *hostmaster.example.com* as opposed to
> *hostmaster@example.com*), be sure to check this value and modify if
> necessary before using it with a functions such as <span
> class="function">mail</span>.

`type`  
By default, <span class="function">dns\_get\_record</span> will search
for any resource records associated with `hostname`. To limit the query,
specify the optional `type` parameter. May be any one of the following:
**`DNS_A`**, **`DNS_CNAME`**, **`DNS_HINFO`**, **`DNS_CAA`**,
**`DNS_MX`**, **`DNS_NS`**, **`DNS_PTR`**, **`DNS_SOA`**, **`DNS_TXT`**,
**`DNS_AAAA`**, **`DNS_SRV`**, **`DNS_NAPTR`**, **`DNS_A6`**,
**`DNS_ALL`** or **`DNS_ANY`**.

> **Note**:
>
> Because of eccentricities in the performance of libresolv between
> platforms, **`DNS_ANY`** will not always return every record, the
> slower **`DNS_ALL`** will collect all records more reliably.

> **Note**:
>
> **`DNS_CAA`** is not supported on Windows.

`authns`  
Passed by reference and, if given, will be populated with Resource
Records for the *Authoritative Name Servers*.

`addtl`  
Passed by reference and, if given, will be populated with any
*Additional Records*.

`raw`  
The `type` will be interpreted as a raw DNS type ID (the *DNS\_\**
constants cannot be used). The return value will contain a *data* key,
which needs to be manually parsed.

### Return Values

This function returns an array of associative arrays, or **`FALSE`** on
failure. Each associative array contains *at minimum* the following
keys:

| Attribute | Meaning                                                                                                                                                                                                                       |
|-----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| host      | The record in the DNS namespace to which the rest of the associated data refers.                                                                                                                                              |
| class     | <span class="function">dns\_get\_record</span> only returns Internet class records and as such this parameter will always return *IN*.                                                                                        |
| type      | String containing the record type. Additional attributes will also be contained in the resulting array dependant on the value of type. See table below.                                                                       |
| ttl       | *"Time To Live"* remaining for this record. This will *not* equal the record's original ttl, but will rather equal the original ttl minus whatever length of time has passed since the authoritative name server was queried. |

| Type                | Extra Columns                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *A*                 | *ip*: An IPv4 addresses in dotted decimal notation.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| *MX*                | *pri*: Priority of mail exchanger. Lower numbers indicate greater priority. *target*: FQDN of the mail exchanger. See also <span class="function">dns\_get\_mx</span>.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| *CNAME*             | *target*: FQDN of location in DNS namespace to which the record is aliased.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| *NS*                | *target*: FQDN of the name server which is authoritative for this hostname.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| *PTR*               | *target*: Location within the DNS namespace to which this record points.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| *TXT*               | *txt*: Arbitrary string data associated with this record.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
| *HINFO*             | *cpu*: IANA number designating the CPU of the machine referenced by this record. *os*: IANA number designating the Operating System on the machine referenced by this record. See IANA's <a href="http://www.iana.org/assignments/operating-system-names" class="link external">» <em>Operating System Names</em></a> for the meaning of these values.                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| *CAA*               | *flags*: A one-byte bitfield; currently only bit 0 is defined, meaning 'critical'; other bits are reserved and should be ignored. *tag*: The CAA tag name (alphanumeric ASCII string). *value*: The CAA tag value (binary string, may use subformats). For additional information see: <a href="http://www.faqs.org/rfcs/rfc6844" class="link external">» RFC 6844</a>                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| *SOA*               | *mname*: FQDN of the machine from which the resource records originated. *rname*: Email address of the administrative contact for this domain. *serial*: Serial \# of this revision of the requested domain. *refresh*: Refresh interval (seconds) secondary name servers should use when updating remote copies of this domain. *retry*: Length of time (seconds) to wait after a failed refresh before making a second attempt. *expire*: Maximum length of time (seconds) a secondary DNS server should retain remote copies of the zone data without a successful refresh before discarding. *minimum-ttl*: Minimum length of time (seconds) a client can continue to use a DNS resolution before it should request a new resolution from the server. Can be overridden by individual resource records. |
| *AAAA*              | *ipv6*: IPv6 address                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| *A6*(PHP \>= 5.1.0) | *masklen*: Length (in bits) to inherit from the target specified by `chain`. *ipv6*: Address for this specific record to merge with `chain`. *chain*: Parent record to merge with `ipv6` data.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| *SRV*               | *pri*: (Priority) lowest priorities should be used first. *weight*: Ranking to weight which of commonly prioritized `targets` should be chosen at random. *target* and *port*: hostname and port where the requested service can be found. For additional information see: <a href="http://www.faqs.org/rfcs/rfc2782" class="link external">» RFC 2782</a>                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| *NAPTR*             | *order* and *pref*: Equivalent to `pri` and `weight` above. *flags*, *services*, *regex*, and *replacement*: Parameters as defined by <a href="http://www.faqs.org/rfcs/rfc2915" class="link external">» RFC 2915</a>.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |

### Changelog

| Version       | Description                        |
|---------------|------------------------------------|
| 7.0.16, 7.1.2 | Added support for CAA record type. |

### Examples

**Example \#1 Using <span class="function">dns\_get\_record</span>**

``` php
<?php
$result = dns_get_record("php.net");
print_r($result);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => Array
            (
                [host] => php.net
                [type] => MX
                [pri] => 5
                [target] => pair2.php.net
                [class] => IN
                [ttl] => 6765
            )

        [1] => Array
            (
                [host] => php.net
                [type] => A
                [ip] => 64.246.30.37
                [class] => IN
                [ttl] => 8125
            )

    )

**Example \#2 Using <span class="function">dns\_get\_record</span> and
DNS\_ANY**

Since it's very common to want the IP address of a mail server once the
MX record has been resolved, <span
class="function">dns\_get\_record</span> also returns an array in
`addtl` which contains associate records. `authns` is returned as well
containing a list of authoritative name servers.

``` php
<?php
/* Request "ANY" record for php.net,
   and create $authns and $addtl arrays
   containing list of name servers and
   any additional records which go with
   them */
$result = dns_get_record("php.net", DNS_ANY, $authns, $addtl);
echo "Result = ";
print_r($result);
echo "Auth NS = ";
print_r($authns);
echo "Additional = ";
print_r($addtl);
?>
```

The above example will output something similar to:

    Result = Array
    (
        [0] => Array
            (
                [host] => php.net
                [type] => MX
                [pri] => 5
                [target] => pair2.php.net
                [class] => IN
                [ttl] => 6765
            )

        [1] => Array
            (
                [host] => php.net
                [type] => A
                [ip] => 64.246.30.37
                [class] => IN
                [ttl] => 8125
            )

    )
    Auth NS = Array
    (
        [0] => Array
            (
                [host] => php.net
                [type] => NS
                [target] => remote1.easydns.com
                [class] => IN
                [ttl] => 10722
            )

        [1] => Array
            (
                [host] => php.net
                [type] => NS
                [target] => remote2.easydns.com
                [class] => IN
                [ttl] => 10722
            )

        [2] => Array
            (
                [host] => php.net
                [type] => NS
                [target] => ns1.easydns.com
                [class] => IN
                [ttl] => 10722
            )

        [3] => Array
            (
                [host] => php.net
                [type] => NS
                [target] => ns2.easydns.com
                [class] => IN
                [ttl] => 10722
            )

    )
    Additional = Array
    (
        [0] => Array
            (
                [host] => pair2.php.net
                [type] => A
                [ip] => 216.92.131.5
                [class] => IN
                [ttl] => 6766
            )

        [1] => Array
            (
                [host] => remote1.easydns.com
                [type] => A
                [ip] => 64.39.29.212
                [class] => IN
                [ttl] => 100384
            )

        [2] => Array
            (
                [host] => remote2.easydns.com
                [type] => A
                [ip] => 212.100.224.80
                [class] => IN
                [ttl] => 81241
            )

        [3] => Array
            (
                [host] => ns1.easydns.com
                [type] => A
                [ip] => 216.220.40.243
                [class] => IN
                [ttl] => 81241
            )

        [4] => Array
            (
                [host] => ns2.easydns.com
                [type] => A
                [ip] => 216.220.40.244
                [class] => IN
                [ttl] => 81241
            )

    )

### Notes

> **Note**:
>
> For compatibility with versions before PHP 5.3.0 on some operating
> systems, try the
> <a href="https://pear.php.net/" class="link external">» PEAR</a> class
> <a href="https://pear.php.net/package/Net_DNS" class="link external">» Net_DNS</a>.

### See Also

-   <span class="function">dns\_get\_mx</span>
-   <span class="function">dns\_check\_record</span>

fsockopen
=========

Open Internet or Unix domain socket connection

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">fsockopen</span> ( <span class="methodparam"><span
class="type">string</span> `$hostname`</span> \[, <span
class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `&$errno`</span> \[,
<span class="methodparam"><span class="type">string</span>
`&$errstr`</span> \[, <span class="methodparam"><span
class="type">float</span> `$timeout`<span class="initializer"> =
ini\_get("default\_socket\_timeout")</span></span> \]\]\]\] )

Initiates a socket connection to the resource specified by `hostname`.

PHP supports targets in the Internet and Unix domains as described in
<a href="/transports.html" class="xref">List of Supported Socket Transports</a>.
A list of supported transports can also be retrieved using <span
class="function">stream\_get\_transports</span>.

The socket will by default be opened in blocking mode. You can switch it
to non-blocking mode by using <span
class="function">stream\_set\_blocking</span>.

The function <span class="function">stream\_socket\_client</span> is
similar but provides a richer set of options, including non-blocking
connection and the ability to provide a stream context.

### Parameters

`hostname`  
If OpenSSL support
<a href="/openssl/setup.html#Installation" class="link">is installed</a>,
you may prefix the `hostname` with either *ssl://* or *tls://* to use an
SSL or TLS client connection over TCP/IP to connect to the remote host.

`port`  
The port number. This can be omitted and skipped with *-1* for
transports that do not use ports, such as *unix://*.

`errno`  
If provided, holds the system level error number that occurred in the
system-level *connect()* call.

If the value returned in `errno` is *0* and the function returned
**`FALSE`**, it is an indication that the error occurred before the
*connect()* call. This is most likely due to a problem initializing the
socket.

`errstr`  
The error message as a string.

`timeout`  
The connection timeout, in seconds.

> **Note**:
>
> If you need to set a timeout for reading/writing data over the socket,
> use <span class="function">stream\_set\_timeout</span>, as the
> `timeout` parameter to <span class="function">fsockopen</span> only
> applies while connecting the socket.

### Return Values

<span class="function">fsockopen</span> returns a file pointer which may
be used together with the other file functions (such as <span
class="function">fgets</span>, <span class="function">fgetss</span>,
<span class="function">fwrite</span>, <span
class="function">fclose</span>, and <span class="function">feof</span>).
If the call fails, it will return **`FALSE`**

### Errors/Exceptions

Throws **`E_WARNING`** if `hostname` is not a valid domain.

### Examples

**Example \#1 <span class="function">fsockopen</span> Example**

``` php
<?php
$fp = fsockopen("www.example.com", 80, $errno, $errstr, 30);
if (!$fp) {
    echo "$errstr ($errno)<br />\n";
} else {
    $out = "GET / HTTP/1.1\r\n";
    $out .= "Host: www.example.com\r\n";
    $out .= "Connection: Close\r\n\r\n";
    fwrite($fp, $out);
    while (!feof($fp)) {
        echo fgets($fp, 128);
    }
    fclose($fp);
}
?>
```

**Example \#2 Using UDP connection**

The example below shows how to retrieve the day and time from the UDP
service "daytime" (port 13) in your own machine.

``` php
<?php
$fp = fsockopen("udp://127.0.0.1", 13, $errno, $errstr);
if (!$fp) {
    echo "ERROR: $errno - $errstr<br />\n";
} else {
    fwrite($fp, "\n");
    echo fread($fp, 26);
    fclose($fp);
}
?>
```

### Notes

> **Note**:
>
> Depending on the environment, the Unix domain or the optional connect
> timeout may not be available.

**Warning**

UDP sockets will sometimes appear to have opened without an error, even
if the remote host is unreachable. The error will only become apparent
when you read or write data to/from the socket. The reason for this is
because UDP is a "connectionless" protocol, which means that the
operating system does not try to establish a link for the socket until
it actually needs to send or receive data.

> **Note**: <span class="simpara">When specifying a numerical IPv6
> address (e.g. *fe80::1*), you must enclose the IP in square
> brackets—for example, *tcp://\[fe80::1\]:80*.</span>

### See Also

-   <span class="function">pfsockopen</span>
-   <span class="function">stream\_socket\_client</span>
-   <span class="function">stream\_set\_blocking</span>
-   <span class="function">stream\_set\_timeout</span>
-   <span class="function">fgets</span>
-   <span class="function">fgetss</span>
-   <span class="function">fwrite</span>
-   <span class="function">fclose</span>
-   <span class="function">feof</span>
-   <span class="function">socket\_connect</span>
-   The <a href="/ref/curl.html" class="link">Curl extension</a>

gethostbyaddr
=============

Get the Internet host name corresponding to a given IP address

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">gethostbyaddr</span> ( <span
class="methodparam"><span class="type">string</span>
`$ip_address`</span> )

Returns the host name of the Internet host specified by `ip_address`.

### Parameters

`ip_address`  
The host IP address.

### Return Values

Returns the host name on success, the unmodified `ip_address` on
failure, or **`FALSE`** on malformed input.

### Examples

**Example \#1 A simple <span class="function">gethostbyaddr</span>
example**

``` php
<?php
$hostname = gethostbyaddr($_SERVER['REMOTE_ADDR']);

echo $hostname;
?>
```

### See Also

-   <span class="function">gethostbyname</span>
-   <span class="function">gethostbynamel</span>

gethostbyname
=============

Get the IPv4 address corresponding to a given Internet host name

### Description

<span class="type">string</span> <span
class="methodname">gethostbyname</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

Returns the IPv4 address of the Internet host specified by `hostname`.

### Parameters

`hostname`  
The host name.

### Return Values

Returns the IPv4 address or a string containing the unmodified
`hostname` on failure.

### Examples

**Example \#1 A simple <span class="function">gethostbyname</span>
example**

``` php
<?php
$ip = gethostbyname('www.example.com');

echo $ip;
?>
```

### See Also

-   <span class="function">gethostbyaddr</span>
-   <span class="function">gethostbynamel</span>
-   <span class="function">inet\_pton</span>
-   <span class="function">inet\_ntop</span>

gethostbynamel
==============

Get a list of IPv4 addresses corresponding to a given Internet host name

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">gethostbynamel</span> ( <span
class="methodparam"><span class="type">string</span> `$hostname`</span>
)

Returns a list of IPv4 addresses to which the Internet host specified by
`hostname` resolves.

### Parameters

`hostname`  
The host name.

### Return Values

Returns an array of IPv4 addresses or **`FALSE`** if `hostname` could
not be resolved.

### Examples

**Example \#1 <span class="function">gethostbynamel</span> example**

``` php
<?php
$hosts = gethostbynamel('www.example.com');
print_r($hosts);
?>
```

The above example will output:

    Array
    (
        [0] => 192.0.34.166
    )

### See Also

-   <span class="function">gethostbyname</span>
-   <span class="function">gethostbyaddr</span>
-   <span class="function">checkdnsrr</span>
-   <span class="function">getmxrr</span>
-   the *named(8)* manual page

gethostname
===========

Gets the host name

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">gethostname</span> ( <span
class="methodparam">void</span> )

<span class="function">gethostname</span> gets the standard host name
for the local machine.

### Return Values

Returns a string with the hostname on success, otherwise **`FALSE`** is
returned.

### Examples

**Example \#1 A simple <span class="function">gethostname</span>
example**

``` php
<?php
echo gethostname(); // may output e.g,: sandie

// Or, an option that also works before PHP 5.3
echo php_uname('n'); // may output e.g,: sandie
?>
```

### See Also

-   <span class="function">gethostbyname</span>
-   <span class="function">gethostbyaddr</span>
-   <span class="function">php\_uname</span>

getmxrr
=======

Get MX records corresponding to a given Internet host name

### Description

<span class="type">bool</span> <span class="methodname">getmxrr</span> (
<span class="methodparam"><span class="type">string</span>
`$hostname`</span> , <span class="methodparam"><span
class="type">array</span> `&$mxhosts`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$weight`</span> \]
)

Searches DNS for MX records corresponding to `hostname`.

### Parameters

`hostname`  
The Internet host name.

`mxhosts`  
A list of the MX records found is placed into the array `mxhosts`.

`weight`  
If the `weight` array is given, it will be filled with the weight
information gathered.

### Return Values

Returns **`TRUE`** if any records are found; returns **`FALSE`** if no
records were found or if an error occurred.

### Notes

> **Note**:
>
> This function should not be used for the purposes of address
> verification. Only the mailexchangers found in DNS are returned,
> however, according to
> <a href="http://www.faqs.org/rfcs/rfc2821" class="link external">» RFC 2821</a>
> when no mail exchangers are listed, `hostname` itself should be used
> as the only mail exchanger with a priority of *0*.

> **Note**:
>
> For compatibility with Windows before this was implemented, then try
> the <a href="https://pear.php.net/" class="link external">» PEAR</a>
> class
> <a href="https://pear.php.net/package/Net_DNS" class="link external">» Net_DNS</a>.

### See Also

-   <span class="function">checkdnsrr</span>
-   <span class="function">dns\_get\_record</span>
-   <span class="function">gethostbyname</span>
-   <span class="function">gethostbynamel</span>
-   <span class="function">gethostbyaddr</span>
-   the *named(8)* manual page

getprotobyname
==============

Get protocol number associated with protocol name

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">getprotobyname</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="function">getprotobyname</span> returns the protocol number
associated with the protocol `name` as per `/etc/protocols`.

### Parameters

`name`  
The protocol name.

### Return Values

Returns the protocol number, or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">getprotobyname</span> example**

``` php
<?php
$protocol = 'tcp';
$get_prot = getprotobyname($protocol);
if ($get_prot === FALSE) {
    echo 'Invalid Protocol';
} else {
    echo 'Protocol #' . $get_prot;
}
?>
```

### See Also

-   <span class="function">getprotobynumber</span>

getprotobynumber
================

Get protocol name associated with protocol number

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">getprotobynumber</span> ( <span
class="methodparam"><span class="type">int</span> `$number`</span> )

<span class="function">getprotobynumber</span> returns the protocol name
associated with protocol `number` as per `/etc/protocols`.

### Parameters

`number`  
The protocol number.

### Return Values

Returns the protocol name as a string, or **`FALSE`** on failure.

### See Also

-   <span class="function">getprotobyname</span>

getservbyname
=============

Get port number associated with an Internet service and protocol

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">getservbyname</span> ( <span
class="methodparam"><span class="type">string</span> `$service`</span> ,
<span class="methodparam"><span class="type">string</span>
`$protocol`</span> )

<span class="function">getservbyname</span> returns the Internet port
which corresponds to `service` for the specified `protocol` as per
`/etc/services`.

### Parameters

`service`  
The Internet service name, as a string.

`protocol`  
`protocol` is either *"tcp"* or *"udp"* (in lowercase).

### Return Values

Returns the port number, or **`FALSE`** if `service` or `protocol` is
not found.

### Examples

**Example \#1 <span class="function">getservbyname</span> example**

``` php
<?php
$services = array('http', 'ftp', 'ssh', 'telnet', 'imap',
'smtp', 'nicname', 'gopher', 'finger', 'pop3', 'www');

foreach ($services as $service) {
    $port = getservbyname($service, 'tcp');
    echo $service . ": " . $port . "<br />\n";
}
?>
```

### See Also

-   <span class="function">getservbyport</span>
-   <a href="http://www.iana.org/assignments/port-numbers" class="link external">» http://www.iana.org/assignments/port-numbers</a>
    for a complete list of port numbers.

getservbyport
=============

Get Internet service which corresponds to port and protocol

### Description

<span class="type">string</span> <span
class="methodname">getservbyport</span> ( <span
class="methodparam"><span class="type">int</span> `$port`</span> , <span
class="methodparam"><span class="type">string</span> `$protocol`</span>
)

<span class="function">getservbyport</span> returns the Internet service
associated with `port` for the specified `protocol` as per
`/etc/services`.

### Parameters

`port`  
The port number.

`protocol`  
`protocol` is either *"tcp"* or *"udp"* (in lowercase).

### Return Values

Returns the Internet service name as a string.

### See Also

-   <span class="function">getservbyname</span>

header\_register\_callback
==========================

Call a header function

### Description

<span class="type">bool</span> <span
class="methodname">header\_register\_callback</span> ( <span
class="methodparam"><span class="type">callable</span>
`$callback`</span> )

Registers a function that will be called when PHP starts sending output.

The `callback` is executed just after PHP prepares all headers to be
sent, and before any other output is sent, creating a window to
manipulate the outgoing headers before being sent.

### Parameters

`callback`  
Function called just before the headers are sent. It gets no parameters
and the return value is ignored.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">header\_register\_callback</span>
example**

``` php
<?php

header('Content-Type: text/plain');
header('X-Test: foo');

function foo() {
 foreach (headers_list() as $header) {
   if (strpos($header, 'X-Powered-By:') !== false) {
     header_remove('X-Powered-By');
   }
   header_remove('X-Test');
 }
}

$result = header_register_callback('foo');
echo "a";
?>
```

The above example will output something similar to:

    Content-Type: text/plain

    a

### Notes

<span class="function">header\_register\_callback</span> is executed
just as the headers are about to be sent out, so any output from this
function can break output.

> **Note**:
>
> Headers will only be accessible and output when a SAPI that supports
> them is in use.

### See Also

-   <span class="function">headers\_list</span>
-   <span class="function">header\_remove</span>
-   <span class="function">header</span>

header\_remove
==============

Remove previously set headers

### Description

<span class="type">void</span> <span
class="methodname">header\_remove</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

Removes an HTTP header previously set using <span
class="function">header</span>.

### Parameters

`name`  
The header name to be removed.

> **Note**: <span class="simpara"> This parameter is case-insensitive.
> </span>

### Return Values

No value is returned.

### Examples

**Example \#1 Unsetting specific header.**

``` php
<?php
header("X-Foo: Bar");
header("X-Bar: Baz");
header_remove("X-Foo"); 
?>
```

The above example will output something similar to:

    X-Bar: Baz

**Example \#2 Unsetting all previously set headers.**

``` php
<?php
header("X-Foo: Bar");
header("X-Bar: Baz");
header_remove(); 
?>
```

The above example will output something similar to:

### Notes

**Caution**

This function will remove *all* headers set by PHP, including cookies,
session and the *X-Powered-By* headers.

> **Note**:
>
> Headers will only be accessible and output when a SAPI that supports
> them is in use.

### See Also

-   <span class="function">header</span>
-   <span class="function">headers\_sent</span>

header
======

Send a raw HTTP header

### Description

<span class="type">void</span> <span class="methodname">header</span> (
<span class="methodparam"><span class="type">string</span>
`$header`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$replace`<span class="initializer"> =
**`TRUE`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$http_response_code`</span> \]\] )

<span class="function">header</span> is used to send a raw HTTP header.
See the
<a href="http://www.faqs.org/rfcs/rfc2616" class="link external">» HTTP/1.1 specification</a>
for more information on HTTP headers.

Remember that <span class="function">header</span> must be called before
any actual output is sent, either by normal HTML tags, blank lines in a
file, or from PHP. It is a very common error to read code with <span
class="function">include</span>, or <span
class="function">require</span>, functions, or another file access
function, and have spaces or empty lines that are output before <span
class="function">header</span> is called. The same problem exists when
using a single PHP/HTML file.

``` php
<html>
<?php
/* This will give an error. Note the output
 * above, which is before the header() call */
header('Location: http://www.example.com/');
exit;
?>
```

### Parameters

`header`  
The header string.

There are two special-case header calls. The first is a header that
starts with the string "*HTTP/*" (case is not significant), which will
be used to figure out the HTTP status code to send. For example, if you
have configured Apache to use a PHP script to handle requests for
missing files (using the *ErrorDocument* directive), you may want to
make sure that your script generates the proper status code.

``` php
<?php
header("HTTP/1.0 404 Not Found");
?>
```

The second special case is the "Location:" header. Not only does it send
this header back to the browser, but it also returns a *REDIRECT* (302)
status code to the browser unless the *201* or a *3xx* status code has
already been set.

``` php
<?php
header("Location: http://www.example.com/"); /* Redirect browser */

/* Make sure that code below does not get executed when we redirect. */
exit;
?>
```

`replace`  
The optional `replace` parameter indicates whether the header should
replace a previous similar header, or add a second header of the same
type. By default it will replace, but if you pass in **`FALSE`** as the
second argument you can force multiple headers of the same type. For
example:

``` php
<?php
header('WWW-Authenticate: Negotiate');
header('WWW-Authenticate: NTLM', false);
?>
```

`http_response_code`  
Forces the HTTP response code to the specified value. Note that this
parameter only has an effect if the `header` is not empty.

### Return Values

No value is returned.

### Examples

**Example \#1 Download dialog**

If you want the user to be prompted to save the data you are sending,
such as a generated PDF file, you can use the
<a href="http://www.faqs.org/rfcs/rfc2183" class="link external">» Content-Disposition</a>
header to supply a recommended filename and force the browser to display
the save dialog.

``` php
<?php
// We'll be outputting a PDF
header('Content-Type: application/pdf');

// It will be called downloaded.pdf
header('Content-Disposition: attachment; filename="downloaded.pdf"');

// The PDF source is in original.pdf
readfile('original.pdf');
?>
```

**Example \#2 Caching directives**

PHP scripts often generate dynamic content that must not be cached by
the client browser or any proxy caches between the server and the client
browser. Many proxies and clients can be forced to disable caching with:

``` php
<?php
header("Cache-Control: no-cache, must-revalidate"); // HTTP/1.1
header("Expires: Sat, 26 Jul 1997 05:00:00 GMT"); // Date in the past
?>
```

> **Note**:
>
> You may find that your pages aren't cached even if you don't output
> all of the headers above. There are a number of options that users may
> be able to set for their browser that change its default caching
> behavior. By sending the headers above, you should override any
> settings that may otherwise cause the output of your script to be
> cached.
>
> Additionally, <span class="function">session\_cache\_limiter</span>
> and the *session.cache\_limiter* configuration setting can be used to
> automatically generate the correct caching-related headers when
> sessions are being used.

### Notes

> **Note**:
>
> Headers will only be accessible and output when a SAPI that supports
> them is in use.

> **Note**:
>
> You can use output buffering to get around this problem, with the
> overhead of all of your output to the browser being buffered in the
> server until you send it. You can do this by calling <span
> class="function">ob\_start</span> and <span
> class="function">ob\_end\_flush</span> in your script, or setting the
> *output\_buffering* configuration directive on in your `php.ini` or
> server configuration files.

> **Note**:
>
> The HTTP status header line will always be the first sent to the
> client, regardless of the actual <span class="function">header</span>
> call being the first or not. The status may be overridden by calling
> <span class="function">header</span> with a new status line at any
> time unless the HTTP headers have already been sent.

> **Note**:
>
> There is a bug in Microsoft Internet Explorer 4.01 that prevents this
> from working. There is no workaround. There is also a bug in Microsoft
> Internet Explorer 5.5 that interferes with this, which can be resolved
> by upgrading to Service Pack 2 or later.

> **Note**:
>
> Most contemporary clients accept relative URIs as argument to
> <a href="http://tools.ietf.org/html/rfc7231#section-7.1.2" class="link external">» Location:</a>,
> but some older clients require an absolute URI including the scheme,
> hostname and absolute path. You can usually use
> `$_SERVER['HTTP_HOST']`, `$_SERVER['PHP_SELF']` and <span
> class="function">dirname</span> to make an absolute URI from a
> relative one yourself:
>
> ``` php
> <?php
> /* Redirect to a different page in the current directory that was requested */
> $host  = $_SERVER['HTTP_HOST'];
> $uri   = rtrim(dirname($_SERVER['PHP_SELF']), '/\\');
> $extra = 'mypage.php';
> header("Location: http://$host$uri/$extra");
> exit;
> ?>
> ```

> **Note**:
>
> Session ID is not passed with Location header even if
> <a href="/session/setup.html#" class="link">session.use_trans_sid</a>
> is enabled. It must by passed manually using **`SID`** constant.

### See Also

-   <span class="function">headers\_sent</span>
-   <span class="function">setcookie</span>
-   <span class="function">http\_response\_code</span>
-   <span class="function">header\_remove</span>
-   The section on
    <a href="/features/http-auth.html" class="link">HTTP authentication</a>

headers\_list
=============

Returns a list of response headers sent (or ready to send)

### Description

<span class="type">array</span> <span
class="methodname">headers\_list</span> ( <span
class="methodparam">void</span> )

<span class="function">headers\_list</span> will return a list of
headers to be sent to the browser / client. To determine whether or not
these headers have been sent yet, use <span
class="function">headers\_sent</span>.

### Return Values

Returns a numerically indexed array of headers.

### Examples

**Example \#1 Examples using <span
class="function">headers\_list</span>**

``` php
<?php

/* setcookie() will add a response header on its own */
setcookie('foo', 'bar');

/* Define a custom response header
   This will be ignored by most clients */
header("X-Sample-Test: foo");

/* Specify plain text content in our response */
header('Content-type: text/plain');

/* What headers are going to be sent? */
var_dump(headers_list());

?>
```

The above example will output:

    array(4) {
      [0]=>
      string(23) "X-Powered-By: PHP/5.1.3"
      [1]=>
      string(19) "Set-Cookie: foo=bar"
      [2]=>
      string(18) "X-Sample-Test: foo"
      [3]=>
      string(24) "Content-type: text/plain"
    }

### Notes

> **Note**:
>
> Headers will only be accessible and output when a SAPI that supports
> them is in use.

### See Also

-   <span class="function">headers\_sent</span>
-   <span class="function">header</span>
-   <span class="function">setcookie</span>
-   <span class="function">apache\_response\_headers</span>
-   <span class="function">http\_response\_code</span>

headers\_sent
=============

Checks if or where headers have been sent

### Description

<span class="type">bool</span> <span
class="methodname">headers\_sent</span> (\[ <span
class="methodparam"><span class="type">string</span> `&$file`</span> \[,
<span class="methodparam"><span class="type">int</span> `&$line`</span>
\]\] )

Checks if or where headers have been sent.

You can't add any more header lines using the <span
class="function">header</span> function once the header block has
already been sent. Using this function you can at least prevent getting
HTTP header related error messages. Another option is to use
<a href="/ref/outcontrol.html" class="link">Output Buffering</a>.

### Parameters

`file`  
If the optional `file` and `line` parameters are set, <span
class="function">headers\_sent</span> will put the PHP source file name
and line number where output started in the `file` and `line` variables.

`line`  
The line number where the output started.

### Return Values

<span class="function">headers\_sent</span> will return **`FALSE`** if
no HTTP headers have already been sent or **`TRUE`** otherwise.

### Examples

**Example \#1 Examples using <span
class="function">headers\_sent</span>**

``` php
<?php

// If no headers are sent, send one
if (!headers_sent()) {
    header('Location: http://www.example.com/');
    exit;
}

// An example using the optional file and line parameters
// Note that $filename and $linenum are passed in for later use.
// Do not assign them values beforehand.
if (!headers_sent($filename, $linenum)) {
    header('Location: http://www.example.com/');
    exit;

// You would most likely trigger an error here.
} else {

    echo "Headers already sent in $filename on line $linenum\n" .
          "Cannot redirect, for now please click this <a " .
          "href=\"http://www.example.com\">link</a> instead\n";
    exit;
}

?>
```

### Notes

> **Note**:
>
> Headers will only be accessible and output when a SAPI that supports
> them is in use.

### See Also

-   <span class="function">ob\_start</span>
-   <span class="function">trigger\_error</span>
-   <span class="function">headers\_list</span>
-   <span class="function">header</span> for a more detailed discussion
    of the matters involved.

http\_response\_code
====================

Get or Set the HTTP response code

### Description

<span class="type">mixed</span> <span
class="methodname">http\_response\_code</span> (\[ <span
class="methodparam"><span class="type">int</span>
`$response_code`</span> \] )

Gets or sets the HTTP response status code.

### Parameters

`response_code`  
The optional `response_code` will set the response code.

### Return Values

If `response_code` is provided, then the previous status code will be
returned. If `response_code` is not provided, then the current status
code will be returned. Both of these values will default to a *200*
status code if used in a web server environment.

**`FALSE`** will be returned if `response_code` is not provided and it
is not invoked in a web server environment (such as from a CLI
application). **`TRUE`** will be returned if `response_code` is provided
and it is not invoked in a web server environment (but only when no
previous response status has been set).

### Examples

**Example \#1 Using <span class="function">http\_response\_code</span>
in a web server environment**

``` php
<?php

// Get the current response code and set a new one
var_dump(http_response_code(404));

// Get the new response code
var_dump(http_response_code());
?>
```

The above example will output:

    int(200)
    int(404)

**Example \#2 Using <span class="function">http\_response\_code</span>
in a CLI environment**

``` php
<?php

// Get the current default response code
var_dump(http_response_code());

// Set a response code
var_dump(http_response_code(201));

// Get the new response code
var_dump(http_response_code());
?>
```

The above example will output:

    bool(false)
    bool(true)
    int(201)

### See Also

-   <span class="function">header</span>
-   <span class="function">headers\_list</span>

inet\_ntop
==========

Converts a packed internet address to a human readable representation

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">inet\_ntop</span> ( <span class="methodparam"><span
class="type">string</span> `$in_addr`</span> )

This function converts a 32bit IPv4, or 128bit IPv6 address (if PHP was
built with IPv6 support enabled) into an address family appropriate
string representation.

### Parameters

`in_addr`  
A 32bit IPv4, or 128bit IPv6 address.

### Return Values

Returns a string representation of the address or **`FALSE`** on
failure.

### Examples

**Example \#1 <span class="function">inet\_ntop</span> Example**

``` php
<?php
$packed = chr(127) . chr(0) . chr(0) . chr(1);
$expanded = inet_ntop($packed);

/* Outputs: 127.0.0.1 */
echo $expanded;

$packed = str_repeat(chr(0), 15) . chr(1);
$expanded = inet_ntop($packed);

/* Outputs: ::1 */
echo $expanded;
?>
```

### See Also

-   <span class="function">long2ip</span>
-   <span class="function">ip2long</span>
-   <span class="function">inet\_pton</span>

inet\_pton
==========

Converts a human readable IP address to its packed in\_addr
representation

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">inet\_pton</span> ( <span class="methodparam"><span
class="type">string</span> `$address`</span> )

This function converts a human readable IPv4 or IPv6 address (if PHP was
built with IPv6 support enabled) into an address family appropriate
32bit or 128bit binary structure.

### Parameters

`address`  
A human readable IPv4 or IPv6 address.

### Return Values

Returns the *in\_addr* representation of the given `address`, or
**`FALSE`** if a syntactically invalid `address` is given (for example,
an IPv4 address without dots or an IPv6 address without colons).

### Examples

**Example \#1 <span class="function">inet\_pton</span> Example**

``` php
<?php
$in_addr = inet_pton('127.0.0.1');
 
$in6_addr = inet_pton('::1');
?>
```

### See Also

-   <span class="function">ip2long</span>
-   <span class="function">long2ip</span>
-   <span class="function">inet\_ntop</span>

ip2long
=======

Converts a string containing an (IPv4) Internet Protocol dotted address
into a long integer

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span class="methodname">ip2long</span>
( <span class="methodparam"><span class="type">string</span>
`$ip_address`</span> )

The function <span class="function">ip2long</span> generates a long
integer representation of IPv4 Internet network address from its
Internet standard format (dotted string) representation.

<span class="function">ip2long</span> will also work with non-complete
IP addresses. Read
<a href="http://publibn.boulder.ibm.com/doc_link/en_US/a_doc_lib/libs/commtrf2/inet_addr.htm" class="link external">» http://publibn.boulder.ibm.com/doc_link/en_US/a_doc_lib/libs/commtrf2/inet_addr.htm</a>
for more info.

### Parameters

`ip_address`  
A standard format address.

### Return Values

Returns the long integer or **`FALSE`** if `ip_address` is invalid.

### Examples

**Example \#1 <span class="function">ip2long</span> Example**

``` php
<?php
$ip = gethostbyname('www.example.com');
$out = "The following URLs are equivalent:<br />\n";
$out .= 'http://www.example.com/, http://' . $ip . '/, and http://' . sprintf("%u", ip2long($ip)) . "/<br />\n";
echo $out;
?>
```

**Example \#2 Displaying an IP address**

This second example shows how to print a converted address with the
<span class="function">printf</span> function:

``` php
<?php
$ip   = gethostbyname('www.example.com');
$long = ip2long($ip);

if ($long == -1 || $long === FALSE) {
    echo 'Invalid IP, please try again';
} else {
    echo $ip   . "\n";            // 192.0.34.166
    echo $long . "\n";            // 3221234342 (-1073732954 on 32-bit systems, due to integer overflow)
    printf("%u\n", ip2long($ip)); // 3221234342
}
?>
```

### Notes

> **Note**:
>
> Because PHP's <span class="type">int</span> type is signed, and many
> IP addresses will result in negative integers on 32-bit architectures,
> you need to use the "%u" formatter of <span
> class="function">sprintf</span> or <span
> class="function">printf</span> to get the string representation of the
> unsigned IP address.

> **Note**:
>
> <span class="function">ip2long</span> will return **`FALSE`** for the
> IP *255.255.255.255* in PHP 5 \<= 5.0.2, and *-1* on 64-bits systems
> in PHP 5 \<=5.2.4. It was fixed in PHP 5.2.5 where it returns
> *4294967295*. 32-bit systems will return *-1* due to the integer value
> overflowing.

### See Also

-   <span class="function">long2ip</span>
-   <span class="function">sprintf</span>

long2ip
=======

Converts an long integer address into a string in (IPv4) Internet
standard dotted format

### Description

<span class="type">string</span> <span class="methodname">long2ip</span>
( <span class="methodparam"><span class="type">int</span>
`$proper_address`</span> )

The function <span class="function">long2ip</span> generates an Internet
address in dotted format (i.e.: aaa.bbb.ccc.ddd) from the long integer
representation.

### Parameters

`proper_address`  
A proper address representation in long integer.

### Return Values

Returns the Internet IP address as a string.

### Changelog

| Version | Description                                                                                                                     |
|---------|---------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | The parameter type of `proper_address` has been changed from <span class="type">string</span> to <span class="type">int</span>. |

### Notes

> **Note**:
>
> On 32-bit architectures, casting integer representations of IP
> addresses from <span class="type">string</span> to <span
> class="type">int</span> will not give correct results for numbers
> which exceed **`PHP_INT_MAX`**.

### See Also

-   <span class="function">ip2long</span>

openlog
=======

Open connection to system logger

### Description

<span class="type">bool</span> <span class="methodname">openlog</span> (
<span class="methodparam"><span class="type">string</span>
`$ident`</span> , <span class="methodparam"><span
class="type">int</span> `$option`</span> , <span
class="methodparam"><span class="type">int</span> `$facility`</span> )

<span class="function">openlog</span> opens a connection to the system
logger for a program.

The use of <span class="function">openlog</span> is optional. It will
automatically be called by <span class="function">syslog</span> if
necessary, in which case `ident` will default to **`FALSE`**.

### Parameters

`ident`  
The string `ident` is added to each message.

`option`  
The `option` argument is used to indicate what logging options will be
used when generating a log message.

| Constant         | Description                                                                                        |
|------------------|----------------------------------------------------------------------------------------------------|
| **`LOG_CONS`**   | if there is an error while sending data to the system logger, write directly to the system console |
| **`LOG_NDELAY`** | open the connection to the logger immediately                                                      |
| **`LOG_ODELAY`** | (default) delay opening the connection until the first message is logged                           |
| **`LOG_PERROR`** | print log message also to standard error                                                           |
| **`LOG_PID`**    | include PID with each message                                                                      |

You can use one or more of these options. When using multiple options
you need to *OR* them, i.e. to open the connection immediately, write to
the console and include the PID in each message, you will use:
*LOG\_CONS \| LOG\_NDELAY \| LOG\_PID*

`facility`  
The `facility` argument is used to specify what type of program is
logging the message. This allows you to specify (in your machine's
syslog configuration) how messages coming from different facilities will
be handled.

| Constant                              | Description                                                                                                |
|---------------------------------------|------------------------------------------------------------------------------------------------------------|
| **`LOG_AUTH`**                        | security/authorization messages (use **`LOG_AUTHPRIV`** instead in systems where that constant is defined) |
| **`LOG_AUTHPRIV`**                    | security/authorization messages (private)                                                                  |
| **`LOG_CRON`**                        | clock daemon (cron and at)                                                                                 |
| **`LOG_DAEMON`**                      | other system daemons                                                                                       |
| **`LOG_KERN`**                        | kernel messages                                                                                            |
| **`LOG_LOCAL0`** ... **`LOG_LOCAL7`** | reserved for local use, these are not available in Windows                                                 |
| **`LOG_LPR`**                         | line printer subsystem                                                                                     |
| **`LOG_MAIL`**                        | mail subsystem                                                                                             |
| **`LOG_NEWS`**                        | USENET news subsystem                                                                                      |
| **`LOG_SYSLOG`**                      | messages generated internally by syslogd                                                                   |
| **`LOG_USER`**                        | generic user-level messages                                                                                |
| **`LOG_UUCP`**                        | UUCP subsystem                                                                                             |

> **Note**:
>
> **`LOG_USER`** is the only valid log type under Windows operating
> systems

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">syslog</span>
-   <span class="function">closelog</span>

pfsockopen
==========

Open persistent Internet or Unix domain socket connection

### Description

<span class="type">resource</span> <span
class="methodname">pfsockopen</span> ( <span class="methodparam"><span
class="type">string</span> `$hostname`</span> \[, <span
class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `&$errno`</span> \[,
<span class="methodparam"><span class="type">string</span>
`&$errstr`</span> \[, <span class="methodparam"><span
class="type">float</span> `$timeout`<span class="initializer"> =
ini\_get("default\_socket\_timeout")</span></span> \]\]\]\] )

This function behaves exactly as <span class="function">fsockopen</span>
with the difference that the connection is not closed after the script
finishes. It is the persistent version of <span
class="function">fsockopen</span>.

### Parameters

For parameter information, see the <span
class="function">fsockopen</span> documentation.

### See Also

-   <span class="function">fsockopen</span>

setcookie
=========

Send a cookie

### Description

<span class="type">bool</span> <span class="methodname">setcookie</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$value`<span class="initializer"> =
""</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$expires`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$path`<span class="initializer"> =
""</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$domain`<span class="initializer"> =
""</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$secure`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$httponly`<span class="initializer"> =
**`FALSE`**</span></span> \]\]\]\]\]\] )

<span class="type">bool</span> <span class="methodname">setcookie</span>
( <span class="methodparam"><span class="type">string</span>
`$name`</span> \[, <span class="methodparam"><span
class="type">string</span> `$value`<span class="initializer"> =
""</span></span> \[, <span class="methodparam"><span
class="type">array</span> `$options`<span class="initializer"> =
\[\]</span></span> \]\] )

<span class="function">setcookie</span> defines a cookie to be sent
along with the rest of the HTTP headers. Like other headers, cookies
must be sent *before* any output from your script (this is a protocol
restriction). This requires that you place calls to this function prior
to any output, including *\<html\>* and *\<head\>* tags as well as any
whitespace.

Once the cookies have been set, they can be accessed on the next page
load with the `$_COOKIE` array. Cookie values may also exist in
`$_REQUEST`.

### Parameters

<a href="http://www.faqs.org/rfcs/rfc6265" class="link external">» RFC 6265</a>
provides the normative reference on how each <span
class="function">setcookie</span> parameter is interpreted.

`name`  
The name of the cookie.

`value`  
The value of the cookie. This value is stored on the clients computer;
do not store sensitive information. Assuming the `name` is
*'cookiename'*, this value is retrieved through `$_COOKIE['cookiename']`

`expires`  
The time the cookie expires. This is a Unix timestamp so is in number of
seconds since the epoch. In other words, you'll most likely set this
with the <span class="function">time</span> function plus the number of
seconds before you want it to expire. Or you might use <span
class="function">mktime</span>. *time()+60\*60\*24\*30* will set the
cookie to expire in 30 days. If set to 0, or omitted, the cookie will
expire at the end of the session (when the browser closes).

> **Note**:
>
> You may notice the `expires` parameter takes on a Unix timestamp, as
> opposed to the date format *Wdy, DD-Mon-YYYY HH:MM:SS GMT*, this is
> because PHP does this conversion internally.

`path`  
The path on the server in which the cookie will be available on. If set
to *'/'*, the cookie will be available within the entire `domain`. If
set to *'/foo/'*, the cookie will only be available within the */foo/*
directory and all sub-directories such as */foo/bar/* of `domain`. The
default value is the current directory that the cookie is being set in.

`domain`  
The (sub)domain that the cookie is available to. Setting this to a
subdomain (such as *'www.example.com'*) will make the cookie available
to that subdomain and all other sub-domains of it (i.e.
w2.www.example.com). To make the cookie available to the whole domain
(including all subdomains of it), simply set the value to the domain
name (*'example.com'*, in this case).

Older browsers still implementing the deprecated
<a href="http://www.faqs.org/rfcs/rfc2109" class="link external">» RFC 2109</a>
may require a leading *.* to match all subdomains.

`secure`  
Indicates that the cookie should only be transmitted over a secure HTTPS
connection from the client. When set to **`TRUE`**, the cookie will only
be set if a secure connection exists. On the server-side, it's on the
programmer to send this kind of cookie only on secure connection (e.g.
with respect to `$_SERVER["HTTPS"]`).

`httponly`  
When **`TRUE`** the cookie will be made accessible only through the HTTP
protocol. This means that the cookie won't be accessible by scripting
languages, such as JavaScript. It has been suggested that this setting
can effectively help to reduce identity theft through XSS attacks
(although it is not supported by all browsers), but that claim is often
disputed. **`TRUE`** or **`FALSE`**

`options`  
An associative <span class="type">array</span> which may have any of the
keys *expires*, *path*, *domain*, *secure*, *httponly* and *samesite*.
If any other key is present an error of level **`E_WARNING`** is
generated. The values have the same meaning as described for the
parameters with the same name. The value of the *samesite* element
should be either *None*, *Lax* or *Strict*. If any of the allowed
options are not given, their default values are the same as the default
values of the explicit parameters. If the *samesite* element is omitted,
no SameSite cookie attribute is set.

### Return Values

If output exists prior to calling this function, <span
class="function">setcookie</span> will fail and return **`FALSE`**. If
<span class="function">setcookie</span> successfully runs, it will
return **`TRUE`**. This does not indicate whether the user accepted the
cookie.

### Examples

Some examples follow how to send cookies:

**Example \#1 <span class="function">setcookie</span> send example**

``` php
<?php
$value = 'something from somewhere';

setcookie("TestCookie", $value);
setcookie("TestCookie", $value, time()+3600);  /* expire in 1 hour */
setcookie("TestCookie", $value, time()+3600, "/~rasmus/", "example.com", 1);
?>
```

Note that the value portion of the cookie will automatically be
urlencoded when you send the cookie, and when it is received, it is
automatically decoded and assigned to a variable by the same name as the
cookie name. If you don't want this, you can use <span
class="function">setrawcookie</span> instead. To see the contents of our
test cookie in a script, simply use one of the following examples:

``` php
<?php
// Print an individual cookie
echo $_COOKIE["TestCookie"];

// Another way to debug/test is to view all cookies
print_r($_COOKIE);
?>
```

**Example \#2 <span class="function">setcookie</span> delete example**

When deleting a cookie you should assure that the expiration date is in
the past, to trigger the removal mechanism in your browser. Examples
follow how to delete cookies sent in previous example:

``` php
<?php
// set the expiration date to one hour ago
setcookie("TestCookie", "", time() - 3600);
setcookie("TestCookie", "", time() - 3600, "/~rasmus/", "example.com", 1);
?>
```

**Example \#3 <span class="function">setcookie</span> and arrays**

You may also set array cookies by using array notation in the cookie
name. This has the effect of setting as many cookies as you have array
elements, but when the cookie is received by your script, the values are
all placed in an array with the cookie's name:

``` php
<?php
// set the cookies
setcookie("cookie[three]", "cookiethree");
setcookie("cookie[two]", "cookietwo");
setcookie("cookie[one]", "cookieone");

// after the page reloads, print them out
if (isset($_COOKIE['cookie'])) {
    foreach ($_COOKIE['cookie'] as $name => $value) {
        $name = htmlspecialchars($name);
        $value = htmlspecialchars($value);
        echo "$name : $value <br />\n";
    }
}
?>
```

The above example will output:

    three : cookiethree
    two : cookietwo
    one : cookieone

> **Note**: <span class="simpara"> Using separator characters such as
> *\[* and *\]* as part of the cookie name is not compliant to RFC 6265,
> section 4, but supposed to be supported by user agents according to
> RFC 6265, section 5. </span>

### Changelog

| Version | Description                                                                                                                                   |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | An alternative signature supporting an `options` array has been added. This signature supports also setting of the SameSite cookie attribute. |

### Notes

> **Note**:
>
> You can use output buffering to send output prior to the call of this
> function, with the overhead of all of your output to the browser being
> buffered in the server until you send it. You can do this by calling
> <span class="function">ob\_start</span> and <span
> class="function">ob\_end\_flush</span> in your script, or setting the
> *output\_buffering* configuration directive on in your `php.ini` or
> server configuration files.

> **Note**:
>
> If the PHP directive
> <a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
> is set to *on* then cookie values will also be made into variables. In
> our examples below, `$TestCookie` will exist. It's recommended to use
> `$_COOKIE`.

Common Pitfalls:

-   <span class="simpara"> Cookies will not become visible until the
    next loading of a page that the cookie should be visible for. To
    test if a cookie was successfully set, check for the cookie on a
    next loading page before the cookie expires. Expire time is set via
    the `expires` parameter. A nice way to debug the existence of
    cookies is by simply calling *print\_r($\_COOKIE);*. </span>
-   <span class="simpara"> Cookies must be deleted with the same
    parameters as they were set with. If the value argument is an empty
    string, or **`FALSE`**, and all other arguments match a previous
    call to setcookie, then the cookie with the specified name will be
    deleted from the remote client. This is internally achieved by
    setting value to 'deleted' and expiration time to one year in past.
    </span>
-   <span class="simpara"> Because setting a cookie with a value of
    **`FALSE`** will try to delete the cookie, you should not use
    boolean values. Instead, use *0* for **`FALSE`** and *1* for
    **`TRUE`**. </span>
-   <span class="simpara"> Cookies names can be set as array names and
    will be available to your PHP scripts as arrays but separate cookies
    are stored on the user's system. Consider <span
    class="function">explode</span> to set one cookie with multiple
    names and values. It is not recommended to use <span
    class="function">serialize</span> for this purpose, because it can
    result in security holes. </span>

Multiple calls to <span class="function">setcookie</span> are performed
in the order called.

### See Also

-   <span class="function">header</span>
-   <span class="function">setrawcookie</span>
-   <a href="/features/cookies.html" class="link">cookies section</a>
-   <a href="http://www.faqs.org/rfcs/rfc6265" class="link external">» RFC 6265</a>
-   <a href="http://www.faqs.org/rfcs/rfc2109" class="link external">» RFC 2109</a>

setrawcookie
============

Send a cookie without urlencoding the cookie value

### Description

<span class="type">bool</span> <span
class="methodname">setrawcookie</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">int</span> `$expires`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$path`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$secure`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$httponly`<span class="initializer"> =
**`FALSE`**</span></span> \]\]\]\]\]\] )

<span class="type">bool</span> <span
class="methodname">setrawcookie</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">string</span> `$value`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$options`<span class="initializer"> = \[\]</span></span> \]\] )

<span class="function">setrawcookie</span> is exactly the same as <span
class="function">setcookie</span> except that the cookie value will not
be automatically urlencoded when sent to the browser.

### Parameters

For parameter information, see the <span
class="function">setcookie</span> documentation.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                   |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | An alternative signature supporting an `options` array has been added. This signature supports also setting of the SameSite cookie attribute. |

### See Also

-   <span class="function">setcookie</span>

socket\_get\_status
===================

Alias of <span class="function">stream\_get\_meta\_data</span>

### Description

This function is an alias of: <span
class="function">stream\_get\_meta\_data</span>.

socket\_set\_blocking
=====================

Alias of <span class="function">stream\_set\_blocking</span>

### Description

This function is an alias of: <span
class="function">stream\_set\_blocking</span>.

socket\_set\_timeout
====================

Alias of <span class="function">stream\_set\_timeout</span>

### Description

This function is an alias of: <span
class="function">stream\_set\_timeout</span>.

syslog
======

Generate a system log message

### Description

<span class="type">bool</span> <span class="methodname">syslog</span> (
<span class="methodparam"><span class="type">int</span>
`$priority`</span> , <span class="methodparam"><span
class="type">string</span> `$message`</span> )

<span class="function">syslog</span> generates a log message that will
be distributed by the system logger.

For information on setting up a user defined log handler, see the <span
class="citerefentry"><span class="refentrytitle">syslog.conf</span>
<span class="manvolnum">(5)</span></span> Unix manual page. More
information on the syslog facilities and option can be found in the man
pages for <span class="citerefentry"><span
class="refentrytitle">syslog</span> <span
class="manvolnum">(3)</span></span> on Unix machines.

### Parameters

`priority`  
`priority` is a combination of the facility and the level. Possible
values are:

| Constant          | Description                        |
|-------------------|------------------------------------|
| **`LOG_EMERG`**   | system is unusable                 |
| **`LOG_ALERT`**   | action must be taken immediately   |
| **`LOG_CRIT`**    | critical conditions                |
| **`LOG_ERR`**     | error conditions                   |
| **`LOG_WARNING`** | warning conditions                 |
| **`LOG_NOTICE`**  | normal, but significant, condition |
| **`LOG_INFO`**    | informational message              |
| **`LOG_DEBUG`**   | debug-level message                |

`message`  
The message to send, except that the two characters *%m* will be
replaced by the error message string (strerror) corresponding to the
present value of <span class="errortype">errno</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Using <span class="function">syslog</span>**

``` php
<?php
// open syslog, include the process ID and also send
// the log to standard error, and use a user defined
// logging mechanism
openlog("myScriptLog", LOG_PID | LOG_PERROR, LOG_LOCAL0);

// some code

if (authorized_client()) {
    // do something
} else {
    // unauthorized client!
    // log the attempt
    $access = date("Y/m/d H:i:s");
    syslog(LOG_WARNING, "Unauthorized client: $access {$_SERVER['REMOTE_ADDR']} ({$_SERVER['HTTP_USER_AGENT']})");
}

closelog();
?>
```

### Notes

On Windows NT, the syslog service is emulated using the Event Log.

> **Note**:
>
> Use of *LOG\_LOCAL0* through *LOG\_LOCAL7* for the `facility`
> parameter of <span class="function">openlog</span> is not available in
> Windows.

### See Also

-   <span class="function">openlog</span>
-   <span class="function">closelog</span>

**Table of Contents**

-   [checkdnsrr](/ref/network.html#checkdnsrr) — Check DNS records
    corresponding to a given Internet host name or IP address
-   [closelog](/ref/network.html#closelog) — Close connection to system
    logger
-   [define\_syslog\_variables](/ref/network.html#define_syslog_variables)
    — Initializes all syslog related variables
-   [dns\_check\_record](/ref/network.html#dns_check_record) — Alias of
    checkdnsrr
-   [dns\_get\_mx](/ref/network.html#dns_get_mx) — Alias of getmxrr
-   [dns\_get\_record](/ref/network.html#dns_get_record) — Fetch DNS
    Resource Records associated with a hostname
-   [fsockopen](/ref/network.html#fsockopen) — Open Internet or Unix
    domain socket connection
-   [gethostbyaddr](/ref/network.html#gethostbyaddr) — Get the Internet
    host name corresponding to a given IP address
-   [gethostbyname](/ref/network.html#gethostbyname) — Get the IPv4
    address corresponding to a given Internet host name
-   [gethostbynamel](/ref/network.html#gethostbynamel) — Get a list of
    IPv4 addresses corresponding to a given Internet host name
-   [gethostname](/ref/network.html#gethostname) — Gets the host name
-   [getmxrr](/ref/network.html#getmxrr) — Get MX records corresponding
    to a given Internet host name
-   [getprotobyname](/ref/network.html#getprotobyname) — Get protocol
    number associated with protocol name
-   [getprotobynumber](/ref/network.html#getprotobynumber) — Get
    protocol name associated with protocol number
-   [getservbyname](/ref/network.html#getservbyname) — Get port number
    associated with an Internet service and protocol
-   [getservbyport](/ref/network.html#getservbyport) — Get Internet
    service which corresponds to port and protocol
-   [header\_register\_callback](/ref/network.html#header_register_callback)
    — Call a header function
-   [header\_remove](/ref/network.html#header_remove) — Remove
    previously set headers
-   [header](/ref/network.html#header) — Send a raw HTTP header
-   [headers\_list](/ref/network.html#headers_list) — Returns a list of
    response headers sent (or ready to send)
-   [headers\_sent](/ref/network.html#headers_sent) — Checks if or where
    headers have been sent
-   [http\_response\_code](/ref/network.html#http_response_code) — Get
    or Set the HTTP response code
-   [inet\_ntop](/ref/network.html#inet_ntop) — Converts a packed
    internet address to a human readable representation
-   [inet\_pton](/ref/network.html#inet_pton) — Converts a human
    readable IP address to its packed in\_addr representation
-   [ip2long](/ref/network.html#ip2long) — Converts a string containing
    an (IPv4) Internet Protocol dotted address into a long integer
-   [long2ip](/ref/network.html#long2ip) — Converts an long integer
    address into a string in (IPv4) Internet standard dotted format
-   [openlog](/ref/network.html#openlog) — Open connection to system
    logger
-   [pfsockopen](/ref/network.html#pfsockopen) — Open persistent
    Internet or Unix domain socket connection
-   [setcookie](/ref/network.html#setcookie) — Send a cookie
-   [setrawcookie](/ref/network.html#setrawcookie) — Send a cookie
    without urlencoding the cookie value
-   [socket\_get\_status](/ref/network.html#socket_get_status) — Alias
    of stream\_get\_meta\_data
-   [socket\_set\_blocking](/ref/network.html#socket_set_blocking) —
    Alias of stream\_set\_blocking
-   [socket\_set\_timeout](/ref/network.html#socket_set_timeout) — Alias
    of stream\_set\_timeout
-   [syslog](/ref/network.html#syslog) — Generate a system log message

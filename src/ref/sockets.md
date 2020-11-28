socket\_accept
==============

Accepts a connection on a socket

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">socket\_accept</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
)

After the socket `socket` has been created using <span
class="function">socket\_create</span>, bound to a name with <span
class="function">socket\_bind</span>, and told to listen for connections
with <span class="function">socket\_listen</span>, this function will
accept incoming connections on that socket. Once a successful connection
is made, a new socket resource is returned, which may be used for
communication. If there are multiple connections queued on the socket,
the first will be used. If there are no pending connections, <span
class="function">socket\_accept</span> will block until a connection
becomes present. If `socket` has been made non-blocking using <span
class="function">socket\_set\_blocking</span> or <span
class="function">socket\_set\_nonblock</span>, **`FALSE`** will be
returned.

The socket resource returned by <span
class="function">socket\_accept</span> may not be used to accept new
connections. The original listening socket `socket`, however, remains
open and may be reused.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span>.

### Return Values

Returns a new socket resource on success, or **`FALSE`** on error. The
actual error code can be retrieved by calling <span
class="function">socket\_last\_error</span>. This error code may be
passed to <span class="function">socket\_strerror</span> to get a
textual explanation of the error.

### See Also

-   <span class="function">socket\_connect</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_create</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_strerror</span>

socket\_addrinfo\_bind
======================

Create and bind to a socket from a given addrinfo

### Description

<span class="type"><span class="type">resource</span><span
class="type">null</span></span> <span
class="methodname">socket\_addrinfo\_bind</span> ( <span
class="methodparam"><span class="type">resource</span> `$addr`</span> )

Create a Socket resource, and bind it to the provided AddrInfo resource.
The return value of this function may be used with <span
class="function">socket\_listen</span>.

### Parameters

`addr`  
Resource created from <span
class="function">socket\_addrinfo\_lookup</span>.

### Return Values

Returns a Socket resource on success or **`NULL`** on failure.

### See Also

-   <span class="function">socket\_addrinfo\_connect</span>
-   <span class="function">socket\_addrinfo\_explain</span>
-   <span class="function">socket\_addrinfo\_lookup</span>
-   <span class="function">socket\_listen</span>

socket\_addrinfo\_connect
=========================

Create and connect to a socket from a given addrinfo

### Description

<span class="type"><span class="type">resource</span><span
class="type">null</span></span> <span
class="methodname">socket\_addrinfo\_connect</span> ( <span
class="methodparam"><span class="type">resource</span> `$addr`</span> )

Create a Socket resource, and connect it to the provided AddrInfo
resource. The return value of this function may be used with the rest of
the socket functions.

### Parameters

`addr`  
Resource created from <span
class="function">socket\_addrinfo\_lookup</span>

### Return Values

Returns a Socket resource on success or **`NULL`** on failure.

### See Also

-   <span class="function">socket\_addrinfo\_bind</span>
-   <span class="function">socket\_addrinfo\_explain</span>
-   <span class="function">socket\_addrinfo\_lookup</span>

socket\_addrinfo\_explain
=========================

Get information about addrinfo

### Description

<span class="type">array</span> <span
class="methodname">socket\_addrinfo\_explain</span> ( <span
class="methodparam"><span class="type">resource</span> `$addr`</span> )

<span class="function">socket\_addrinfo\_explain</span> exposed the
underlying *addrinfo* structure.

### Parameters

`addr`  
Resource created from <span
class="function">socket\_addrinfo\_lookup</span>

### Return Values

Returns an array containing the fields in the *addrinfo* structure.

### See Also

-   <span class="function">socket\_addrinfo\_bind</span>
-   <span class="function">socket\_addrinfo\_connect</span>
-   <span class="function">socket\_addrinfo\_lookup</span>

socket\_addrinfo\_lookup
========================

Get array with contents of getaddrinfo about the given hostname

### Description

<span class="type">array</span> <span
class="methodname">socket\_addrinfo\_lookup</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$service`</span> \[, <span class="methodparam"><span
class="type">array</span> `$hints`</span> \]\] )

Lookup different ways we can connect to `host`. The returned array
contains a set of resources that we can bind to using <span
class="function">socket\_addrinfo\_bind</span>.

### Parameters

`host`  
Hostname to search.

`service`  
The service to connect to. If service is a name, it is translated to the
corresponding port number.

`hints`  
Hints provide criteria for selecting addresses returned. You may specify
the hints as defined by getadrinfo.

### Return Values

Returns an array of AddrInfo resource handles that can be used with the
other socket\_addrinfo functions.

### See Also

-   <span class="function">socket\_addrinfo\_bind</span>
-   <span class="function">socket\_addrinfo\_connect</span>
-   <span class="function">socket\_addrinfo\_explain</span>

socket\_bind
============

Binds a name to a socket

### Description

<span class="type">bool</span> <span
class="methodname">socket\_bind</span> ( <span class="methodparam"><span
class="type">resource</span> `$socket`</span> , <span
class="methodparam"><span class="type">string</span> `$address`</span>
\[, <span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 0</span></span> \] )

Binds the name given in `address` to the socket described by `socket`.
This has to be done before a connection is be established using <span
class="function">socket\_connect</span> or <span
class="function">socket\_listen</span>.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span>.

`address`  
If the socket is of the **`AF_INET`** family, the `address` is an IP in
dotted-quad notation (e.g. *127.0.0.1*).

If the socket is of the **`AF_UNIX`** family, the `address` is the path
of a Unix-domain socket (e.g. `/tmp/my.sock`).

`port` (Optional)  
The `port` parameter is only used when binding an **`AF_INET`** socket,
and designates the port on which to listen for connections.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

The error code can be retrieved with <span
class="function">socket\_last\_error</span>. This code may be passed to
<span class="function">socket\_strerror</span> to get a textual
explanation of the error.

### Examples

**Example \#1 Using <span class="function">socket\_bind</span> to set
the source address**

``` php
<?php
// Create a new socket
$sock = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);

// An example list of IP addresses owned by the computer
$sourceips['kevin']    = '127.0.0.1';
$sourceips['madcoder'] = '127.0.0.2';

// Bind the source address
socket_bind($sock, $sourceips['madcoder']);

// Connect to destination address
socket_connect($sock, '127.0.0.1', 80);

// Write
$request = 'GET / HTTP/1.1' . "\r\n" .
           'Host: example.com' . "\r\n\r\n";
socket_write($sock, $request);

// Close
socket_close($sock);

?>
```

### Notes

> **Note**:
>
> This function must be used on the socket before <span
> class="function">socket\_connect</span>.

> **Note**:
>
> Windows 9x/ME compatibility note: <span
> class="function">socket\_last\_error</span> may return an invalid
> error code if trying to bind the socket to a wrong address that does
> not belong to your machine.

### See Also

-   <span class="function">socket\_connect</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_create</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_clear\_error
====================

Clears the error on the socket or the last error code

### Description

<span class="type">void</span> <span
class="methodname">socket\_clear\_error</span> (\[ <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
\] )

This function clears the error code on the given socket or the global
last socket error if no socket is specified.

This function allows explicitly resetting the error code value either of
a socket or of the extension global last error code. This may be useful
to detect within a part of the application if an error occurred or not.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span>.

### Return Values

No value is returned.

### See Also

-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_close
=============

Closes a socket resource

### Description

<span class="type">void</span> <span
class="methodname">socket\_close</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
)

<span class="function">socket\_close</span> closes the socket resource
given by `socket`. This function is specific to sockets and cannot be
used on any other type of resources.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

### Return Values

No value is returned.

### See Also

-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_create</span>
-   <span class="function">socket\_strerror</span>

socket\_cmsg\_space
===================

Calculate message buffer size

### Description

<span class="type">int</span> <span
class="methodname">socket\_cmsg\_space</span> ( <span
class="methodparam"><span class="type">int</span> `$level`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span>
\[, <span class="methodparam"><span class="type">int</span> `$n`<span
class="initializer"> = 0</span></span> \] )

Calculates the size of the buffer that should be allocated for receiving
the ancillary data.

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`level`  

`type`  

### Return Values

### See Also

-   <span class="function">socket\_recvmsg</span>
-   <span class="function">socket\_sendmsg</span>

socket\_connect
===============

Initiates a connection on a socket

### Description

<span class="type">bool</span> <span
class="methodname">socket\_connect</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">string</span>
`$address`</span> \[, <span class="methodparam"><span
class="type">int</span> `$port`<span class="initializer"> =
0</span></span> \] )

Initiate a connection to `address` using the socket resource `socket`,
which must be a valid socket resource created with <span
class="function">socket\_create</span>.

### Parameters

`socket`  

`address`  
The `address` parameter is either an IPv4 address in dotted-quad
notation (e.g. *127.0.0.1*) if `socket` is **`AF_INET`**, a valid IPv6
address (e.g. *::1*) if IPv6 support is enabled and `socket` is
**`AF_INET6`** or the pathname of a Unix domain socket, if the socket
family is **`AF_UNIX`**.

`port`  
The `port` parameter is only used and is mandatory when connecting to an
**`AF_INET`** or an **`AF_INET6`** socket, and designates the port on
the remote host to which a connection should be made.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The error code
can be retrieved with <span class="function">socket\_last\_error</span>.
This code may be passed to <span
class="function">socket\_strerror</span> to get a textual explanation of
the error.

> **Note**:
>
> If the socket is non-blocking then this function returns **`FALSE`**
> with an error *Operation now in progress*.

### See Also

-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_create</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_create\_listen
======================

Opens a socket on port to accept connections

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">socket\_create\_listen</span> ( <span
class="methodparam"><span class="type">int</span> `$port`</span> \[,
<span class="methodparam"><span class="type">int</span> `$backlog`<span
class="initializer"> = 128</span></span> \] )

<span class="function">socket\_create\_listen</span> creates a new
socket resource of type **`AF_INET`** listening on *all* local
interfaces on the given port waiting for new connections.

This function is meant to ease the task of creating a new socket which
only listens to accept new connections.

### Parameters

`port`  
The port on which to listen on all interfaces.

`backlog`  
The `backlog` parameter defines the maximum length the queue of pending
connections may grow to. **`SOMAXCONN`** may be passed as `backlog`
parameter, see <span class="function">socket\_listen</span> for more
information.

### Return Values

<span class="function">socket\_create\_listen</span> returns a new
socket resource on success or **`FALSE`** on error. The error code can
be retrieved with <span class="function">socket\_last\_error</span>.
This code may be passed to <span
class="function">socket\_strerror</span> to get a textual explanation of
the error.

### Notes

> **Note**:
>
> If you want to create a socket which only listens on a certain
> interface you need to use <span
> class="function">socket\_create</span>, <span
> class="function">socket\_bind</span> and <span
> class="function">socket\_listen</span>.

### See Also

-   <span class="function">socket\_create</span>
-   <span class="function">socket\_create\_pair</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_create\_pair
====================

Creates a pair of indistinguishable sockets and stores them in an array

### Description

<span class="type">bool</span> <span
class="methodname">socket\_create\_pair</span> ( <span
class="methodparam"><span class="type">int</span> `$domain`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> ,
<span class="methodparam"><span class="type">int</span>
`$protocol`</span> , <span class="methodparam"><span
class="type">array</span> `&$fd`</span> )

<span class="function">socket\_create\_pair</span> creates two connected
and indistinguishable sockets, and stores them in `fd`. This function is
commonly used in IPC (InterProcess Communication).

### Parameters

`domain`  
The `domain` parameter specifies the protocol family to be used by the
socket. See <span class="function">socket\_create</span> for the full
list.

`type`  
The `type` parameter selects the type of communication to be used by the
socket. See <span class="function">socket\_create</span> for the full
list.

`protocol`  
The `protocol` parameter sets the specific protocol within the specified
`domain` to be used when communicating on the returned socket. The
proper value can be retrieved by name by using <span
class="function">getprotobyname</span>. If the desired protocol is TCP,
or UDP the corresponding constants **`SOL_TCP`**, and **`SOL_UDP`** can
also be used.

See <span class="function">socket\_create</span> for the full list of
supported protocols.

`fd`  
Reference to an array in which the two socket resources will be
inserted.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">socket\_create\_pair</span>
example**

``` php
<?php
$sockets = array();

/* On Windows we need to use AF_INET */
$domain = (strtoupper(substr(PHP_OS, 0, 3)) == 'WIN' ? AF_INET : AF_UNIX);

/* Setup socket pair */
if (socket_create_pair($domain, SOCK_STREAM, 0, $sockets) === false) {
    echo "socket_create_pair failed. Reason: ".socket_strerror(socket_last_error());
}
/* Send and Receive Data */
if (socket_write($sockets[0], "ABCdef123\n", strlen("ABCdef123\n")) === false) {
    echo "socket_write() failed. Reason: ".socket_strerror(socket_last_error($sockets[0]));
}
if (($data = socket_read($sockets[1], strlen("ABCdef123\n"), PHP_BINARY_READ)) === false) {
    echo "socket_read() failed. Reason: ".socket_strerror(socket_last_error($sockets[1]));
}
var_dump($data);

/* Close sockets */
socket_close($sockets[0]);
socket_close($sockets[1]);
?>
```

**Example \#2 <span class="function">socket\_create\_pair</span> IPC
example**

``` php
<?php
$ary = array();
$strone = 'Message From Parent.';
$strtwo = 'Message From Child.';

if (socket_create_pair(AF_UNIX, SOCK_STREAM, 0, $ary) === false) {
    echo "socket_create_pair() failed. Reason: ".socket_strerror(socket_last_error());
}
$pid = pcntl_fork();
if ($pid == -1) {
    echo 'Could not fork Process.';
} elseif ($pid) {
    /*parent*/
    socket_close($ary[0]);
    if (socket_write($ary[1], $strone, strlen($strone)) === false) {
        echo "socket_write() failed. Reason: ".socket_strerror(socket_last_error($ary[1]));
    }
    if (socket_read($ary[1], strlen($strtwo), PHP_BINARY_READ) == $strtwo) {
        echo "Received $strtwo\n";
    }
    socket_close($ary[1]);
} else {
    /*child*/
    socket_close($ary[1]);
    if (socket_write($ary[0], $strtwo, strlen($strtwo)) === false) {
        echo "socket_write() failed. Reason: ".socket_strerror(socket_last_error($ary[0]));
    }
    if (socket_read($ary[0], strlen($strone), PHP_BINARY_READ) == $strone) {
        echo "Received $strone\n";
    }
    socket_close($ary[0]);
}
?>
```

### See Also

-   <span class="function">socket\_create</span>
-   <span class="function">socket\_create\_listen</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_create
==============

Create a socket (endpoint for communication)

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">socket\_create</span> ( <span
class="methodparam"><span class="type">int</span> `$domain`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> ,
<span class="methodparam"><span class="type">int</span>
`$protocol`</span> )

Creates and returns a socket resource, also referred to as an endpoint
of communication. A typical network connection is made up of 2 sockets,
one performing the role of the client, and another performing the role
of the server.

### Parameters

`domain`  
The `domain` parameter specifies the protocol family to be used by the
socket.

| Domain         | Description                                                                                                                     |
|----------------|---------------------------------------------------------------------------------------------------------------------------------|
| **`AF_INET`**  | IPv4 Internet based protocols. TCP and UDP are common protocols of this protocol family.                                        |
| **`AF_INET6`** | IPv6 Internet based protocols. TCP and UDP are common protocols of this protocol family.                                        |
| **`AF_UNIX`**  | Local communication protocol family. High efficiency and low overhead make it a great form of IPC (Interprocess Communication). |

`type`  
The `type` parameter selects the type of communication to be used by the
socket.

| Type                 | Description                                                                                                                                                                                          |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`SOCK_STREAM`**    | Provides sequenced, reliable, full-duplex, connection-based byte streams. An out-of-band data transmission mechanism may be supported. The TCP protocol is based on this socket type.                |
| **`SOCK_DGRAM`**     | Supports datagrams (connectionless, unreliable messages of a fixed maximum length). The UDP protocol is based on this socket type.                                                                   |
| **`SOCK_SEQPACKET`** | Provides a sequenced, reliable, two-way connection-based data transmission path for datagrams of fixed maximum length; a consumer is required to read an entire packet with each read call.          |
| **`SOCK_RAW`**       | Provides raw network protocol access. This special type of socket can be used to manually construct any type of protocol. A common use for this socket type is to perform ICMP requests (like ping). |
| **`SOCK_RDM`**       | Provides a reliable datagram layer that does not guarantee ordering. This is most likely not implemented on your operating system.                                                                   |

`protocol`  
The `protocol` parameter sets the specific protocol within the specified
`domain` to be used when communicating on the returned socket. The
proper value can be retrieved by name by using <span
class="function">getprotobyname</span>. If the desired protocol is TCP,
or UDP the corresponding constants **`SOL_TCP`**, and **`SOL_UDP`** can
also be used.

| Name | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| icmp | The Internet Control Message Protocol is used primarily by gateways and hosts to report errors in datagram communication. The "ping" command (present in most modern operating systems) is an example application of ICMP.                                                                                                                                                                                                                                                                                                                                                                                             |
| udp  | The User Datagram Protocol is a connectionless, unreliable, protocol with fixed record lengths. Due to these aspects, UDP requires a minimum amount of protocol overhead.                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| tcp  | The Transmission Control Protocol is a reliable, connection based, stream oriented, full duplex protocol. TCP guarantees that all data packets will be received in the order in which they were sent. If any packet is somehow lost during communication, TCP will automatically retransmit the packet until the destination host acknowledges that packet. For reliability and performance reasons, the TCP implementation itself decides the appropriate octet boundaries of the underlying datagram communication layer. Therefore, TCP applications must allow for the possibility of partial record transmission. |

### Return Values

<span class="function">socket\_create</span> returns a socket resource
on success, or **`FALSE`** on error. The actual error code can be
retrieved by calling <span class="function">socket\_last\_error</span>.
This error code may be passed to <span
class="function">socket\_strerror</span> to get a textual explanation of
the error.

### Errors/Exceptions

If an invalid `domain` or `type` is given, <span
class="function">socket\_create</span> defaults to **`AF_INET`** and
**`SOCK_STREAM`** respectively and additionally emits an **`E_WARNING`**
message.

### See Also

-   <span class="function">socket\_accept</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_connect</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_export\_stream
======================

Export a socket extension resource into a stream that encapsulates a
socket

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">socket\_export\_stream</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`socket`  

### Return Values

Return resource or **`FALSE`** on failure.

socket\_get\_option
===================

Gets socket options for the socket

### Description

<span class="type">mixed</span> <span
class="methodname">socket\_get\_option</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">int</span>
`$level`</span> , <span class="methodparam"><span
class="type">int</span> `$optname`</span> )

The <span class="function">socket\_get\_option</span> function retrieves
the value for the option specified by the `optname` parameter for the
specified `socket`.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

`level`  
The `level` parameter specifies the protocol level at which the option
resides. For example, to retrieve options at the socket level, a `level`
parameter of **`SOL_SOCKET`** would be used. Other levels, such as
**`TCP`**, can be used by specifying the protocol number of that level.
Protocol numbers can be found by using the <span
class="function">getprotobyname</span> function.

`optname`  
<table>
<caption><strong>Available Socket Options</strong></caption>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Option</th>
<th>Description</th>
<th>Type</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><strong><code>SO_DEBUG</code></strong></td>
<td>Reports whether debugging information is being recorded.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="even">
<td><strong><code>SO_BROADCAST</code></strong></td>
<td>Reports whether transmission of broadcast messages is supported.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="odd">
<td><strong><code>SO_REUSEADDR</code></strong></td>
<td>Reports whether local addresses can be reused.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="even">
<td><strong><code>SO_REUSEPORT</code></strong></td>
<td>Reports whether local ports can be reused.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="odd">
<td><strong><code>SO_KEEPALIVE</code></strong></td>
<td>Reports whether connections are kept active with periodic transmission of messages. If the connected socket fails to respond to these messages, the connection is broken and processes writing to that socket are notified with a SIGPIPE signal.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="even">
<td><strong><code>SO_LINGER</code></strong></td>
<td><p>Reports whether the <code class="parameter">socket</code> lingers on <span class="function">socket_close</span> if data is present. By default, when the socket is closed, it attempts to send all unsent data. In the case of a connection-oriented socket, <span class="function">socket_close</span> will wait for its peer to acknowledge the data.</p>
<p>If <var class="varname">l_onoff</var> is non-zero and <var class="varname">l_linger</var> is zero, all the unsent data will be discarded and RST (reset) is sent to the peer in the case of a connection-oriented socket.</p>
<p>On the other hand, if <var class="varname">l_onoff</var> is non-zero and <var class="varname">l_linger</var> is non-zero, <span class="function">socket_close</span> will block until all the data is sent or the time specified in <var class="varname">l_linger</var> elapses. If the socket is non-blocking, <span class="function">socket_close</span> will fail and return an error.</p></td>
<td><span class="type">array</span>. The array will contain two keys: <var class="varname">l_onoff</var> and <var class="varname">l_linger</var>.</td>
</tr>
<tr class="odd">
<td><strong><code>SO_OOBINLINE</code></strong></td>
<td>Reports whether the <code class="parameter">socket</code> leaves out-of-band data inline.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="even">
<td><strong><code>SO_SNDBUF</code></strong></td>
<td>Reports the size of the send buffer.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="odd">
<td><strong><code>SO_RCVBUF</code></strong></td>
<td>Reports the size of the receive buffer.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="even">
<td><strong><code>SO_ERROR</code></strong></td>
<td>Reports information about error status and clears it.</td>
<td><span class="type">int</span> (cannot be set by <span class="function">socket_set_option</span>)</td>
</tr>
<tr class="odd">
<td><strong><code>SO_TYPE</code></strong></td>
<td>Reports the <code class="parameter">socket</code> type (e.g. <strong><code>SOCK_STREAM</code></strong>).</td>
<td><span class="type">int</span> (cannot be set by <span class="function">socket_set_option</span>)</td>
</tr>
<tr class="even">
<td><strong><code>SO_DONTROUTE</code></strong></td>
<td>Reports whether outgoing messages bypass the standard routing facilities.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="odd">
<td><strong><code>SO_RCVLOWAT</code></strong></td>
<td>Reports the minimum number of bytes to process for <code class="parameter">socket</code> input operations.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="even">
<td><strong><code>SO_RCVTIMEO</code></strong></td>
<td>Reports the timeout value for input operations.</td>
<td><span class="type">array</span>. The array will contain two keys: <var class="varname">sec</var> which is the seconds part on the timeout value and <var class="varname">usec</var> which is the microsecond part of the timeout value.</td>
</tr>
<tr class="odd">
<td><strong><code>SO_SNDTIMEO</code></strong></td>
<td>Reports the timeout value specifying the amount of time that an output function blocks because flow control prevents data from being sent.</td>
<td><span class="type">array</span>. The array will contain two keys: <var class="varname">sec</var> which is the seconds part on the timeout value and <var class="varname">usec</var> which is the microsecond part of the timeout value.</td>
</tr>
<tr class="even">
<td><strong><code>SO_SNDLOWAT</code></strong></td>
<td>Reports the minimum number of bytes to process for <code class="parameter">socket</code> output operations.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="odd">
<td><strong><code>TCP_NODELAY</code></strong></td>
<td>Reports whether the Nagle TCP algorithm is disabled.</td>
<td><span class="type">int</span></td>
</tr>
<tr class="even">
<td><strong><code>MCAST_JOIN_GROUP</code></strong></td>
<td>Joins a multicast group. (added in PHP 5.4)</td>
<td><span class="type">array</span> with keys <em>"group"</em>, specifying a <span class="type">string</span> with an IPv4 or IPv6 multicast address and <em>"interface"</em>, specifying either an interface number (type <span class="type">int</span>) or a <em>string</em> with the interface name, like <em>"eth0"</em>. <em>0</em> can be specified to indicate the interface should be selected using routing rules. (can only be used in <span class="function">socket_set_option</span>)</td>
</tr>
<tr class="odd">
<td><strong><code>MCAST_LEAVE_GROUP</code></strong></td>
<td>Leaves a multicast group. (added in PHP 5.4)</td>
<td><span class="type">array</span>. See <strong><code>MCAST_JOIN_GROUP</code></strong> for more information. (can only be used in <span class="function">socket_set_option</span>)</td>
</tr>
<tr class="even">
<td><strong><code>MCAST_BLOCK_SOURCE</code></strong></td>
<td>Blocks packets arriving from a specific source to a specific multicast group, which must have been previously joined. (added in PHP 5.4)</td>
<td><span class="type">array</span> with the same keys as <strong><code>MCAST_JOIN_GROUP</code></strong>, plus one extra key, <em>source</em>, which maps to a <span class="type">string</span> specifying an IPv4 or IPv6 address of the source to be blocked. (can only be used in <span class="function">socket_set_option</span>)</td>
</tr>
<tr class="odd">
<td><strong><code>MCAST_UNBLOCK_SOURCE</code></strong></td>
<td>Unblocks (start receiving again) packets arriving from a specific source address to a specific multicast group, which must have been previously joined. (added in PHP 5.4)</td>
<td><span class="type">array</span> with the same format as <strong><code>MCAST_BLOCK_SOURCE</code></strong>. (can only be used in <span class="function">socket_set_option</span>)</td>
</tr>
<tr class="even">
<td><strong><code>MCAST_JOIN_SOURCE_GROUP</code></strong></td>
<td>Receive packets destined to a specific multicast group whose source address matches a specific value. (added in PHP 5.4)</td>
<td><span class="type">array</span> with the same format as <strong><code>MCAST_BLOCK_SOURCE</code></strong>. (can only be used in <span class="function">socket_set_option</span>)</td>
</tr>
<tr class="odd">
<td><strong><code>MCAST_LEAVE_SOURCE_GROUP</code></strong></td>
<td>Stop receiving packets destined to a specific multicast group whose source address matches a specific value. (added in PHP 5.4)</td>
<td><span class="type">array</span> with the same format as <strong><code>MCAST_BLOCK_SOURCE</code></strong>. (can only be used in <span class="function">socket_set_option</span>)</td>
</tr>
<tr class="even">
<td><strong><code>IP_MULTICAST_IF</code></strong></td>
<td>The outgoing interface for IPv4 multicast packets. (added in PHP 5.4)</td>
<td>Either <span class="type">int</span> specifying the interface number or a <span class="type">string</span> with an interface name, like <em>eth0</em>. The value <span class="type">0</span> can be used to indicate the routing table is to used in the interface selection. The function <span class="function">socket_get_option</span> returns an interface index. Note that, unlike the C API, this option does NOT take an IP address. This eliminates the interface difference between <strong><code>IP_MULTICAST_IF</code></strong> and <strong><code>IPV6_MULTICAST_IF</code></strong>.</td>
</tr>
<tr class="odd">
<td><strong><code>IPV6_MULTICAST_IF</code></strong></td>
<td>The outgoing interface for IPv6 multicast packets. (added in PHP 5.4)</td>
<td>The same as <strong><code>IP_MULTICAST_IF</code></strong>.</td>
</tr>
<tr class="even">
<td><strong><code>IP_MULTICAST_LOOP</code></strong></td>
<td>The multicast loopback policy for IPv4 packets, which determines whether multicast packets sent by this socket also reach receivers in the same host that have joined the same multicast group on the outgoing interface used by this socket. This is the case by default. (added in PHP 5.4)</td>
<td><span class="type">int</span> (either <em>0</em> or <em>1</em>). For <span class="function">socket_set_option</span> any value will be accepted and will be converted to a boolean following the usual PHP rules.</td>
</tr>
<tr class="odd">
<td><strong><code>IPV6_MULTICAST_LOOP</code></strong></td>
<td>Analogous to <strong><code>IP_MULTICAST_LOOP</code></strong>, but for IPv6. (added in PHP 5.4)</td>
<td><span class="type">int</span>. See <strong><code>IP_MULTICAST_LOOP</code></strong>.</td>
</tr>
<tr class="even">
<td><strong><code>IP_MULTICAST_TTL</code></strong></td>
<td>The time-to-live of outgoing IPv4 multicast packets. This should be a value between 0 (don't leave the interface) and 255. The default value is 1 (only the local network is reached). (added in PHP 5.4)</td>
<td><span class="type">int</span> between 0 and 255.</td>
</tr>
<tr class="odd">
<td><strong><code>IPV6_MULTICAST_HOPS</code></strong></td>
<td>Analogous to <strong><code>IP_MULTICAST_TTL</code></strong>, but for IPv6 packets. The value -1 is also accepted, meaning the route default should be used. (added in PHP 5.4)</td>
<td><span class="type">int</span> between -1 and 255.</td>
</tr>
</tbody>
</table>

### Return Values

Returns the value of the given option, or **`FALSE`** on errors.

### Examples

**Example \#1 <span class="function">socket\_get\_option</span>
example**

``` php
<?php
$socket = socket_create_listen(1223);

$linger = array('l_linger' => 1, 'l_onoff' => 1);
socket_set_option($socket, SOL_SOCKET, SO_LINGER, $linger);

var_dump(socket_get_option($socket, SOL_SOCKET, SO_REUSEADDR));
?>
```

### See Also

-   <span class="function">socket\_create\_listen</span>
-   <span class="function">socket\_set\_option</span>

socket\_getopt
==============

Alias of <span class="function">socket\_get\_option</span>

### Description

This function is an alias of: <span
class="function">socket\_get\_option</span>.

socket\_getpeername
===================

Queries the remote side of the given socket which may either result in
host/port or in a Unix filesystem path, dependent on its type

### Description

<span class="type">bool</span> <span
class="methodname">socket\_getpeername</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">string</span>
`&$address`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$port`</span> \] )

Queries the remote side of the given socket which may either result in
host/port or in a Unix filesystem path, dependent on its type.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

`address`  
If the given socket is of type **`AF_INET`** or **`AF_INET6`**, <span
class="function">socket\_getpeername</span> will return the peers
(remote) *IP address* in appropriate notation (e.g. *127.0.0.1* or
*fe80::1*) in the `address` parameter and, if the optional `port`
parameter is present, also the associated port.

If the given socket is of type **`AF_UNIX`**, <span
class="function">socket\_getpeername</span> will return the Unix
filesystem path (e.g. */var/run/daemon.sock*) in the `address`
parameter.

`port`  
If given, this will hold the port associated to `address`.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. <span
class="function">socket\_getpeername</span> may also return **`FALSE`**
if the socket type is not any of **`AF_INET`**, **`AF_INET6`**, or
**`AF_UNIX`**, in which case the last socket error code is *not*
updated.

### Notes

> **Note**:
>
> <span class="function">socket\_getpeername</span> should not be used
> with **`AF_UNIX`** sockets created with <span
> class="function">socket\_accept</span>. Only sockets created with
> <span class="function">socket\_connect</span> or a primary server
> socket following a call to <span class="function">socket\_bind</span>
> will return meaningful values.

> **Note**:
>
> For having <span class="function">socket\_getpeername</span> to return
> a meaningful value, the socket it is applied upon must of course be
> one for which the concept of "peer" makes sense.

### See Also

-   <span class="function">socket\_getsockname</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_getsockname
===================

Queries the local side of the given socket which may either result in
host/port or in a Unix filesystem path, dependent on its type

### Description

<span class="type">bool</span> <span
class="methodname">socket\_getsockname</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">string</span>
`&$addr`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$port`</span> \] )

> **Note**: <span class="simpara"> <span
> class="function">socket\_getsockname</span> should not be used with
> **`AF_UNIX`** sockets created with <span
> class="function">socket\_connect</span>. Only sockets created with
> <span class="function">socket\_accept</span> or a primary server
> socket following a call to <span class="function">socket\_bind</span>
> will return meaningful values. </span>

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

`addr`  
If the given socket is of type **`AF_INET`** or **`AF_INET6`**, <span
class="function">socket\_getsockname</span> will return the local *IP
address* in appropriate notation (e.g. *127.0.0.1* or *fe80::1*) in the
`address` parameter and, if the optional `port` parameter is present,
also the associated port.

If the given socket is of type **`AF_UNIX`**, <span
class="function">socket\_getsockname</span> will return the Unix
filesystem path (e.g. */var/run/daemon.sock*) in the `address`
parameter.

`port`  
If provided, this will hold the associated port.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. <span
class="function">socket\_getsockname</span> may also return **`FALSE`**
if the socket type is not any of **`AF_INET`**, **`AF_INET6`**, or
**`AF_UNIX`**, in which case the last socket error code is *not*
updated.

### See Also

-   <span class="function">socket\_getpeername</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_import\_stream
======================

Import a stream

### Description

<span class="type"><span class="type">resource</span><span
class="type">null</span><span class="type">false</span></span> <span
class="methodname">socket\_import\_stream</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
)

Imports a stream that encapsulates a socket into a socket extension
resource.

### Parameters

`stream`  
The stream resource to import.

### Return Values

Returns **`FALSE`** or **`NULL`** on failure.

### Examples

**Example \#1 <span class="function">socket\_import\_stream</span>
example**

``` php
<?php
$stream = stream_socket_server("udp://0.0.0.0:58380", $errno, $errstr, STREAM_SERVER_BIND); 
$sock   = socket_import_stream($stream);
?>
```

### See Also

-   <span class="function">stream\_socket\_server</span>

socket\_last\_error
===================

Returns the last error on the socket

### Description

<span class="type">int</span> <span
class="methodname">socket\_last\_error</span> (\[ <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
\] )

If a socket resource is passed to this function, the last error which
occurred on this particular socket is returned. If the socket resource
is omitted, the error code of the last failed socket function is
returned. The latter is particularly helpful for functions like <span
class="function">socket\_create</span> which don't return a socket on
failure and <span class="function">socket\_select</span> which can fail
for reasons not directly tied to a particular socket. The error code is
suitable to be fed to <span class="function">socket\_strerror</span>
which returns a string describing the given error code.

If no error had occurred, or the error had been cleared with <span
class="function">socket\_clear\_error</span>, the function returns *0*.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span>.

### Return Values

This function returns a socket error code.

### Examples

**Example \#1 <span class="function">socket\_last\_error</span>
example**

``` php
<?php
$socket = @socket_create(AF_INET, SOCK_STREAM, SOL_TCP);

if ($socket === false) {
    $errorcode = socket_last_error();
    $errormsg = socket_strerror($errorcode);
    
    die("Couldn't create socket: [$errorcode] $errormsg");
}
?>
```

### Notes

> **Note**:
>
> <span class="function">socket\_last\_error</span> does not clear the
> error code, use <span class="function">socket\_clear\_error</span> for
> this purpose.

socket\_listen
==============

Listens for a connection on a socket

### Description

<span class="type">bool</span> <span
class="methodname">socket\_listen</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$backlog`<span class="initializer"> = 0</span></span> \] )

After the socket `socket` has been created using <span
class="function">socket\_create</span> and bound to a name with <span
class="function">socket\_bind</span>, it may be told to listen for
incoming connections on `socket`.

<span class="function">socket\_listen</span> is applicable only to
sockets of type **`SOCK_STREAM`** or **`SOCK_SEQPACKET`**.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_addrinfo\_bind</span>

`backlog`  
A maximum of `backlog` incoming connections will be queued for
processing. If a connection request arrives with the queue full the
client may receive an error with an indication of *ECONNREFUSED*, or, if
the underlying protocol supports retransmission, the request may be
ignored so that retries may succeed.

> **Note**:
>
> The maximum number passed to the `backlog` parameter highly depends on
> the underlying platform. On Linux, it is silently truncated to
> **`SOMAXCONN`**. On win32, if passed **`SOMAXCONN`**, the underlying
> service provider responsible for the socket will set the backlog to a
> maximum *reasonable* value. There is no standard provision to find out
> the actual backlog value on this platform.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure. The error code
can be retrieved with <span class="function">socket\_last\_error</span>.
This code may be passed to <span
class="function">socket\_strerror</span> to get a textual explanation of
the error.

### See Also

-   <span class="function">socket\_accept</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_connect</span>
-   <span class="function">socket\_create</span>
-   <span class="function">socket\_strerror</span>
-   <span class="function">socket\_addrinfo\_bind</span>

socket\_read
============

Reads a maximum of length bytes from a socket

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">socket\_read</span> ( <span class="methodparam"><span
class="type">resource</span> `$socket`</span> , <span
class="methodparam"><span class="type">int</span> `$length`</span> \[,
<span class="methodparam"><span class="type">int</span> `$type`<span
class="initializer"> = PHP\_BINARY\_READ</span></span> \] )

The function <span class="function">socket\_read</span> reads from the
socket resource `socket` created by the <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span> functions.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

`length`  
The maximum number of bytes read is specified by the `length` parameter.
Otherwise you can use **`\r`**, **`\n`**, or **`\0`** to end reading
(depending on the `type` parameter, see below).

`type`  
Optional `type` parameter is a named constant:

-   <span class="simpara"> **`PHP_BINARY_READ`** (Default) - use the
    system *recv()* function. Safe for reading binary data. </span>
-   <span class="simpara"> **`PHP_NORMAL_READ`** - reading stops at
    *\\n* or *\\r*. </span>

### Return Values

<span class="function">socket\_read</span> returns the data as a string
on success, or **`FALSE`** on error (including if the remote host has
closed the connection). The error code can be retrieved with <span
class="function">socket\_last\_error</span>. This code may be passed to
<span class="function">socket\_strerror</span> to get a textual
representation of the error.

> **Note**:
>
> <span class="function">socket\_read</span> returns a zero length
> string ("") when there is no more data to read.

### See Also

-   <span class="function">socket\_accept</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_connect</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>
-   <span class="function">socket\_write</span>

socket\_recv
============

Receives data from a connected socket

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">socket\_recv</span> ( <span class="methodparam"><span
class="type">resource</span> `$socket`</span> , <span
class="methodparam"><span class="type">string</span> `&$buf`</span> ,
<span class="methodparam"><span class="type">int</span> `$len`</span> ,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
)

The <span class="function">socket\_recv</span> function receives `len`
bytes of data in `buf` from `socket`. <span
class="function">socket\_recv</span> can be used to gather data from
connected sockets. Additionally, one or more flags can be specified to
modify the behaviour of the function.

`buf` is passed by reference, so it must be specified as a variable in
the argument list. Data read from `socket` by <span
class="function">socket\_recv</span> will be returned in `buf`.

### Parameters

`socket`  
The `socket` must be a socket resource previously created by
socket\_create().

`buf`  
The data received will be fetched to the variable specified with `buf`.
If an error occurs, if the connection is reset, or if no data is
available, `buf` will be set to **`NULL`**.

`len`  
Up to `len` bytes will be fetched from remote host.

`flags`  
The value of `flags` can be any combination of the following flags,
joined with the binary OR (*\|*) operator.

| Flag               | Description                                                                                                                                |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| **`MSG_OOB`**      | Process out-of-band data.                                                                                                                  |
| **`MSG_PEEK`**     | Receive data from the beginning of the receive queue without removing it from the queue.                                                   |
| **`MSG_WAITALL`**  | Block until at least `len` are received. However, if a signal is caught or the remote host disconnects, the function may return less data. |
| **`MSG_DONTWAIT`** | With this flag set, the function returns even if it would normally have blocked.                                                           |

### Return Values

<span class="function">socket\_recv</span> returns the number of bytes
received, or **`FALSE`** if there was an error. The actual error code
can be retrieved by calling <span
class="function">socket\_last\_error</span>. This error code may be
passed to <span class="function">socket\_strerror</span> to get a
textual explanation of the error.

### Examples

**Example \#1 <span class="function">socket\_recv</span> example**

This example is a simple rewrite of the first example from
<a href="/sockets/examples.html" class="xref">Examples</a> to use <span
class="function">socket\_recv</span>.

``` php
<?php
error_reporting(E_ALL);

echo "<h2>TCP/IP Connection</h2>\n";

/* Get the port for the WWW service. */
$service_port = getservbyname('www', 'tcp');

/* Get the IP address for the target host. */
$address = gethostbyname('www.example.com');

/* Create a TCP/IP socket. */
$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);
if ($socket === false) {
    echo "socket_create() failed: reason: " . socket_strerror(socket_last_error()) . "\n";
} else {
    echo "OK.\n";
}

echo "Attempting to connect to '$address' on port '$service_port'...";
$result = socket_connect($socket, $address, $service_port);
if ($result === false) {
    echo "socket_connect() failed.\nReason: ($result) " . socket_strerror(socket_last_error($socket)) . "\n";
} else {
    echo "OK.\n";
}

$in = "HEAD / HTTP/1.1\r\n";
$in .= "Host: www.example.com\r\n";
$in .= "Connection: Close\r\n\r\n";
$out = '';

echo "Sending HTTP HEAD request...";
socket_write($socket, $in, strlen($in));
echo "OK.\n";

echo "Reading response:\n\n";
$buf = 'This is my buffer.';
if (false !== ($bytes = socket_recv($socket, $buf, 2048, MSG_WAITALL))) {
    echo "Read $bytes bytes from socket_recv(). Closing socket...";
} else {
    echo "socket_recv() failed; reason: " . socket_strerror(socket_last_error($socket)) . "\n";
}
socket_close($socket);

echo $buf . "\n";
echo "OK.\n\n";
?>
```

The above example will produce something like:

    <h2>TCP/IP Connection</h2>
    OK.
    Attempting to connect to '208.77.188.166' on port '80'...OK.
    Sending HTTP HEAD request...OK.
    Reading response:

    Read 123 bytes from socket_recv(). Closing socket...HTTP/1.1 200 OK
    Date: Mon, 14 Sep 2009 08:56:36 GMT
    Server: Apache/2.2.3 (Red Hat)
    Last-Modified: Tue, 15 Nov 2005 13:24:10 GMT
    ETag: "b80f4-1b6-80bfd280"
    Accept-Ranges: bytes
    Content-Length: 438
    Connection: close
    Content-Type: text/html; charset=UTF-8

    OK.

socket\_recvfrom
================

Receives data from a socket whether or not it is connection-oriented

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">socket\_recvfrom</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">string</span>
`&$buf`</span> , <span class="methodparam"><span class="type">int</span>
`$len`</span> , <span class="methodparam"><span class="type">int</span>
`$flags`</span> , <span class="methodparam"><span
class="type">string</span> `&$name`</span> \[, <span
class="methodparam"><span class="type">int</span> `&$port`</span> \] )

The <span class="function">socket\_recvfrom</span> function receives
`len` bytes of data in `buf` from `name` on port `port` (if the socket
is not of type **`AF_UNIX`**) using `socket`. <span
class="function">socket\_recvfrom</span> can be used to gather data from
both connected and unconnected sockets. Additionally, one or more flags
can be specified to modify the behaviour of the function.

The `name` and `port` must be passed by reference. If the socket is not
connection-oriented, `name` will be set to the internet protocol address
of the remote host or the path to the UNIX socket. If the socket is
connection-oriented, `name` is **`NULL`**. Additionally, the `port` will
contain the port of the remote host in the case of an unconnected
**`AF_INET`** or **`AF_INET6`** socket.

> **Note**: <span class="simpara">This function is binary-safe.</span>

### Parameters

`socket`  
The `socket` must be a socket resource previously created by
socket\_create().

`buf`  
The data received will be fetched to the variable specified with `buf`.

`len`  
Up to `len` bytes will be fetched from remote host.

`flags`  
The value of `flags` can be any combination of the following flags,
joined with the binary OR (*\|*) operator.

| Flag               | Description                                                                                                                                |
|--------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
| **`MSG_OOB`**      | Process out-of-band data.                                                                                                                  |
| **`MSG_PEEK`**     | Receive data from the beginning of the receive queue without removing it from the queue.                                                   |
| **`MSG_WAITALL`**  | Block until at least `len` are received. However, if a signal is caught or the remote host disconnects, the function may return less data. |
| **`MSG_DONTWAIT`** | With this flag set, the function returns even if it would normally have blocked.                                                           |

`name`  
If the socket is of the type **`AF_UNIX`** type, `name` is the path to
the file. Else, for unconnected sockets, `name` is the IP address of,
the remote host, or **`NULL`** if the socket is connection-oriented.

`port`  
This argument only applies to **`AF_INET`** and **`AF_INET6`** sockets,
and specifies the remote port from which the data is received. If the
socket is connection-oriented, `port` will be **`NULL`**.

### Return Values

<span class="function">socket\_recvfrom</span> returns the number of
bytes received, or **`FALSE`** if there was an error. The actual error
code can be retrieved by calling <span
class="function">socket\_last\_error</span>. This error code may be
passed to <span class="function">socket\_strerror</span> to get a
textual explanation of the error.

### Examples

**Example \#1 <span class="function">socket\_recvfrom</span> example**

``` php
<?php
error_reporting(E_ALL | E_STRICT);

$socket = socket_create(AF_INET, SOCK_DGRAM, SOL_UDP);
socket_bind($socket, '127.0.0.1', 1223);

$from = '';
$port = 0;
socket_recvfrom($socket, $buf, 12, 0, $from, $port);

echo "Received $buf from remote address $from and remote port $port" . PHP_EOL;
?>
```

This example will initiate a UDP socket on port 1223 of 127.0.0.1 and
print at most 12 characters received from a remote host.

### See Also

-   <span class="function">socket\_recv</span>
-   <span class="function">socket\_send</span>
-   <span class="function">socket\_sendto</span>
-   <span class="function">socket\_create</span>

socket\_recvmsg
===============

Read a message

### Description

<span class="type">int</span> <span
class="methodname">socket\_recvmsg</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">array</span>
`&$message`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`socket`  

`message`  

`flags`  

### Return Values

### See Also

-   <span class="function">socket\_sendmsg</span>
-   <span class="function">socket\_cmsg\_space</span>

socket\_select
==============

Runs the select() system call on the given arrays of sockets with a
specified timeout

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">socket\_select</span> ( <span
class="methodparam"><span class="type">array</span> `&$read`</span> ,
<span class="methodparam"><span class="type">array</span>
`&$write`</span> , <span class="methodparam"><span
class="type">array</span> `&$except`</span> , <span
class="methodparam"><span class="type">int</span> `$tv_sec`</span> \[,
<span class="methodparam"><span class="type">int</span> `$tv_usec`<span
class="initializer"> = 0</span></span> \] )

<span class="function">socket\_select</span> accepts arrays of sockets
and waits for them to change status. Those coming with BSD sockets
background will recognize that those socket resource arrays are in fact
the so-called file descriptor sets. Three independent arrays of socket
resources are watched.

### Parameters

`read`  
The sockets listed in the `read` array will be watched to see if
characters become available for reading (more precisely, to see if a
read will not block - in particular, a socket resource is also ready on
end-of-file, in which case a <span class="function">socket\_read</span>
will return a zero length string).

`write`  
The sockets listed in the `write` array will be watched to see if a
write will not block.

`except`  
The sockets listed in the `except` array will be watched for exceptions.

`tv_sec`  
The `tv_sec` and `tv_usec` together form the *timeout* parameter. The
*timeout* is an upper bound on the amount of time elapsed before <span
class="function">socket\_select</span> return. `tv_sec` may be zero ,
causing <span class="function">socket\_select</span> to return
immediately. This is useful for polling. If `tv_sec` is **`NULL`** (no
timeout), <span class="function">socket\_select</span> can block
indefinitely.

`tv_usec`  

**Warning**

On exit, the arrays are modified to indicate which socket resource
actually changed status.

You do not need to pass every array to <span
class="function">socket\_select</span>. You can leave it out and use an
empty array or **`NULL`** instead. Also do not forget that those arrays
are passed *by reference* and will be modified after <span
class="function">socket\_select</span> returns.

> **Note**:
>
> Due a limitation in the current Zend Engine it is not possible to pass
> a constant modifier like **`NULL`** directly as a parameter to a
> function which expects this parameter to be passed by reference.
> Instead use a temporary variable or an expression with the leftmost
> member being a temporary variable:
>
> **Example \#1 Using **`NULL`** with <span
> class="function">socket\_select</span>**
>
> ``` php
> <?php
> $e = NULL;
> socket_select($r, $w, $e, 0);
> ?>
> ```

### Return Values

On success <span class="function">socket\_select</span> returns the
number of socket resources contained in the modified arrays, which may
be zero if the timeout expires before anything interesting happens. On
error **`FALSE`** is returned. The error code can be retrieved with
<span class="function">socket\_last\_error</span>.

> **Note**:
>
> Be sure to use the *===* operator when checking for an error. Since
> the <span class="function">socket\_select</span> may return 0 the
> comparison with *==* would evaluate to **`TRUE`**:
>
> **Example \#2 Understanding <span
> class="function">socket\_select</span>'s result**
>
> ``` php
> <?php
> $e = NULL;
> if (false === socket_select($r, $w, $e, 0)) {
>     echo "socket_select() failed, reason: " .
>         socket_strerror(socket_last_error()) . "\n";
> }
> ?>
> ```

### Examples

**Example \#3 <span class="function">socket\_select</span> example**

``` php
<?php
/* Prepare the read array */
$read   = array($socket1, $socket2);
$write  = NULL;
$except = NULL;
$num_changed_sockets = socket_select($read, $write, $except, 0);

if ($num_changed_sockets === false) {
    /* Error handling */
} else if ($num_changed_sockets > 0) {
    /* At least at one of the sockets something interesting happened */
}
?>
```

### Notes

> **Note**:
>
> Be aware that some socket implementations need to be handled very
> carefully. A few basic rules:
>
> -   <span class="simpara"> You should always try to use <span
>     class="function">socket\_select</span> without timeout. Your
>     program should have nothing to do if there is no data available.
>     Code that depends on timeouts is not usually portable and
>     difficult to debug. </span>
> -   <span class="simpara"> No socket resource must be added to any set
>     if you do not intend to check its result after the <span
>     class="function">socket\_select</span> call, and respond
>     appropriately. After <span class="function">socket\_select</span>
>     returns, all socket resources in all arrays must be checked. Any
>     socket resource that is available for writing must be written to,
>     and any socket resource available for reading must be read from.
>     </span>
> -   <span class="simpara"> If you read/write to a socket returns in
>     the arrays be aware that they do not necessarily read/write the
>     full amount of data you have requested. Be prepared to even only
>     be able to read/write a single byte. </span>
> -   <span class="simpara"> It's common to most socket implementations
>     that the only exception caught with the `except` array is
>     out-of-bound data received on a socket. </span>

### See Also

-   <span class="function">socket\_read</span>
-   <span class="function">socket\_write</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_strerror</span>

socket\_send
============

Sends data to a connected socket

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">socket\_send</span> ( <span class="methodparam"><span
class="type">resource</span> `$socket`</span> , <span
class="methodparam"><span class="type">string</span> `$buf`</span> ,
<span class="methodparam"><span class="type">int</span> `$len`</span> ,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
)

The function <span class="function">socket\_send</span> sends `len`
bytes to the socket `socket` from `buf`.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

`buf`  
A buffer containing the data that will be sent to the remote host.

`len`  
The number of bytes that will be sent to the remote host from `buf`.

`flags`  
The value of `flags` can be any combination of the following flags,
joined with the binary OR (*\|*) operator.

|                     |                                                                                                                                                           |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`MSG_OOB`**       | Send OOB (out-of-band) data.                                                                                                                              |
| **`MSG_EOR`**       | Indicate a record mark. The sent data completes the record.                                                                                               |
| **`MSG_EOF`**       | Close the sender side of the socket and include an appropriate notification of this at the end of the sent data. The sent data completes the transaction. |
| **`MSG_DONTROUTE`** | Bypass routing, use direct interface.                                                                                                                     |

### Return Values

<span class="function">socket\_send</span> returns the number of bytes
sent, or **`FALSE`** on error.

### See Also

-   <span class="function">socket\_sendto</span>

socket\_sendmsg
===============

Send a message

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">socket\_sendmsg</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">array</span>
`$message`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`socket`  

`message`  

`flags`  

### Return Values

Returns the number of bytes sent, or **`FALSE`** on failure.

### See Also

-   <span class="function">socket\_recvmsg</span>
-   <span class="function">socket\_cmsg\_space</span>

socket\_sendto
==============

Sends a message to a socket, whether it is connected or not

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">socket\_sendto</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">string</span>
`$buf`</span> , <span class="methodparam"><span class="type">int</span>
`$len`</span> , <span class="methodparam"><span class="type">int</span>
`$flags`</span> , <span class="methodparam"><span
class="type">string</span> `$addr`</span> \[, <span
class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 0</span></span> \] )

The function <span class="function">socket\_sendto</span> sends `len`
bytes from `buf` through the socket `socket` to the `port` at the
address `addr`.

### Parameters

`socket`  
A valid socket resource created using <span
class="function">socket\_create</span>.

`buf`  
The sent data will be taken from buffer `buf`.

`len`  
`len` bytes from `buf` will be sent.

`flags`  
The value of `flags` can be any combination of the following flags,
joined with the binary OR (*\|*) operator.

|                     |                                                                                                                                                           |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`MSG_OOB`**       | Send OOB (out-of-band) data.                                                                                                                              |
| **`MSG_EOR`**       | Indicate a record mark. The sent data completes the record.                                                                                               |
| **`MSG_EOF`**       | Close the sender side of the socket and include an appropriate notification of this at the end of the sent data. The sent data completes the transaction. |
| **`MSG_DONTROUTE`** | Bypass routing, use direct interface.                                                                                                                     |

`addr`  
IP address of the remote host.

`port`  
`port` is the remote port number at which the data will be sent.

### Return Values

<span class="function">socket\_sendto</span> returns the number of bytes
sent to the remote host, or **`FALSE`** if an error occurred.

### Examples

**Example \#1 <span class="function">socket\_sendto</span> Example**

``` php
<?php
    $sock = socket_create(AF_INET, SOCK_DGRAM, SOL_UDP);

    $msg = "Ping !";
    $len = strlen($msg);

    socket_sendto($sock, $msg, $len, 0, '127.0.0.1', 1223);
    socket_close($sock);
?>
```

### See Also

-   <span class="function">socket\_send</span>

socket\_set\_block
==================

Sets blocking mode on a socket resource

### Description

<span class="type">bool</span> <span
class="methodname">socket\_set\_block</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
)

The <span class="function">socket\_set\_block</span> function removes
the **`O_NONBLOCK`** flag on the socket specified by the `socket`
parameter.

When an operation (e.g. receive, send, connect, accept, ...) is
performed on a blocking socket, the script will pause its execution
until it receives a signal or it can perform the operation.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">socket\_set\_block</span> example**

``` php
<?php
$socket = socket_create_listen(1223);
socket_set_block($socket);

socket_accept($socket);
?>
```

This example creates a listening socket on all interfaces on port 1223
and sets the socket to **`O_BLOCK`** mode. <span
class="function">socket\_accept</span> will hang until there is a
connection to accept.

### See Also

-   <span class="function">socket\_set\_nonblock</span>
-   <span class="function">socket\_set\_option</span>

socket\_set\_nonblock
=====================

Sets nonblocking mode for file descriptor fd

### Description

<span class="type">bool</span> <span
class="methodname">socket\_set\_nonblock</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
)

The <span class="function">socket\_set\_nonblock</span> function sets
the **`O_NONBLOCK`** flag on the socket specified by the `socket`
parameter.

When an operation (e.g. receive, send, connect, accept, ...) is
performed on a non-blocking socket, the script will not pause its
execution until it receives a signal or it can perform the operation.
Rather, if the operation would result in a block, the called function
will fail.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">socket\_set\_nonblock</span>
example**

``` php
<?php
$socket = socket_create_listen(1223);
socket_set_nonblock($socket);

socket_accept($socket);
?>
```

This example creates a listening socket on all interfaces on port 1223
and sets the socket to **`O_NONBLOCK`** mode. <span
class="function">socket\_accept</span> will immediately fail unless
there is a pending connection exactly at this moment.

### See Also

-   <span class="function">socket\_set\_block</span>
-   <span class="function">socket\_set\_option</span>
-   <span class="function">stream\_set\_blocking</span>

socket\_set\_option
===================

Sets socket options for the socket

### Description

<span class="type">bool</span> <span
class="methodname">socket\_set\_option</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">int</span>
`$level`</span> , <span class="methodparam"><span
class="type">int</span> `$optname`</span> , <span
class="methodparam"><span class="type">mixed</span> `$optval`</span> )

The <span class="function">socket\_set\_option</span> function sets the
option specified by the `optname` parameter, at the specified protocol
`level`, to the value pointed to by the `optval` parameter for the
`socket`.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span> or <span
class="function">socket\_accept</span>.

`level`  
The `level` parameter specifies the protocol level at which the option
resides. For example, to retrieve options at the socket level, a `level`
parameter of **`SOL_SOCKET`** would be used. Other levels, such as TCP,
can be used by specifying the protocol number of that level. Protocol
numbers can be found by using the <span
class="function">getprotobyname</span> function.

`optname`  
The available socket options are the same as those for the <span
class="function">socket\_get\_option</span> function.

`optval`  
The option value.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">socket\_set\_option</span>
example**

``` php
<?php
$socket = socket_create(AF_INET, SOCK_STREAM, SOL_TCP);

if (!is_resource($socket)) {
    echo 'Unable to create socket: '. socket_strerror(socket_last_error()) . PHP_EOL;
}

if (!socket_set_option($socket, SOL_SOCKET, SO_REUSEADDR, 1)) {
    echo 'Unable to set option on socket: '. socket_strerror(socket_last_error()) . PHP_EOL;
}

if (!socket_bind($socket, '127.0.0.1', 1223)) {
    echo 'Unable to bind socket: '. socket_strerror(socket_last_error()) . PHP_EOL;
}

$rval = socket_get_option($socket, SOL_SOCKET, SO_REUSEADDR);

if ($rval === false) {
    echo 'Unable to get socket option: '. socket_strerror(socket_last_error()) . PHP_EOL;
} else if ($rval !== 0) {
    echo 'SO_REUSEADDR is set on socket !' . PHP_EOL;
}
?>
```

### See Also

-   <span class="function">socket\_create</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_strerror</span>
-   <span class="function">socket\_last\_error</span>
-   <span class="function">socket\_get\_option</span>

socket\_setopt
==============

Alias of <span class="function">socket\_set\_option</span>

### Description

This function is an alias of: <span
class="function">socket\_set\_option</span>.

socket\_shutdown
================

Shuts down a socket for receiving, sending, or both

### Description

<span class="type">bool</span> <span
class="methodname">socket\_shutdown</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
\[, <span class="methodparam"><span class="type">int</span> `$how`<span
class="initializer"> = 2</span></span> \] )

The <span class="function">socket\_shutdown</span> function allows you
to stop incoming, outgoing or all data (the default) from being sent
through the `socket`

> **Note**:
>
> The associated buffer, or buffers, may or may not be emptied.

### Parameters

`socket`  
A valid socket resource created with <span
class="function">socket\_create</span>.

`how`  
The value of `how` can be one of the following:

|     |                                     |
|-----|-------------------------------------|
| *0* | Shutdown socket reading             |
| *1* | Shutdown socket writing             |
| *2* | Shutdown socket reading and writing |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

socket\_strerror
================

Return a string describing a socket error

### Description

<span class="type">string</span> <span
class="methodname">socket\_strerror</span> ( <span
class="methodparam"><span class="type">int</span> `$errno`</span> )

<span class="function">socket\_strerror</span> takes as its `errno`
parameter a socket error code as returned by <span
class="function">socket\_last\_error</span> and returns the
corresponding explanatory text.

> **Note**:
>
> Although the error messages generated by the socket extension are in
> English, the system messages retrieved with this function will appear
> depending on the current locale (**`LC_MESSAGES`**).

### Parameters

`errno`  
A valid socket error number, likely produced by <span
class="function">socket\_last\_error</span>.

### Return Values

Returns the error message associated with the `errno` parameter.

### Examples

**Example \#1 <span class="function">socket\_strerror</span> example**

``` php
<?php
if (false == ($socket = @socket_create(AF_INET, SOCK_STREAM, SOL_TCP))) {
   echo "socket_create() failed: reason: " . socket_strerror(socket_last_error()) . "\n";
}

if (false == (@socket_bind($socket, '127.0.0.1', 80))) {
   echo "socket_bind() failed: reason: " . socket_strerror(socket_last_error($socket)) . "\n";
}
?>
```

The expected output from the above example (assuming the script is not
run with root privileges):

    socket_bind() failed: reason: Permission denied

### See Also

-   <span class="function">socket\_accept</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_connect</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_create</span>

socket\_write
=============

Write to a socket

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">socket\_write</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">string</span>
`$buffer`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`<span class="initializer"> =
0</span></span> \] )

The function <span class="function">socket\_write</span> writes to the
`socket` from the given `buffer`.

### Parameters

`socket`  

`buffer`  
The buffer to be written.

`length`  
The optional parameter `length` can specify an alternate length of bytes
written to the socket. If this length is greater than the buffer length,
it is silently truncated to the length of the buffer.

### Return Values

Returns the number of bytes successfully written to the socket or
**`FALSE`** on failure. The error code can be retrieved with <span
class="function">socket\_last\_error</span>. This code may be passed to
<span class="function">socket\_strerror</span> to get a textual
explanation of the error.

> **Note**:
>
> It is perfectly valid for <span class="function">socket\_write</span>
> to return zero which means no bytes have been written. Be sure to use
> the *===* operator to check for **`FALSE`** in case of an error.

### Notes

> **Note**:
>
> <span class="function">socket\_write</span> does not necessarily write
> all bytes from the given buffer. It's valid that, depending on the
> network buffers etc., only a certain amount of data, even one byte, is
> written though your buffer is greater. You have to watch out so you
> don't unintentionally forget to transmit the rest of your data.

### See Also

-   <span class="function">socket\_accept</span>
-   <span class="function">socket\_bind</span>
-   <span class="function">socket\_connect</span>
-   <span class="function">socket\_listen</span>
-   <span class="function">socket\_read</span>
-   <span class="function">socket\_strerror</span>

socket\_wsaprotocol\_info\_export
=================================

Exports the WSAPROTOCOL\_INFO Structure

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">socket\_wsaprotocol\_info\_export</span> ( <span
class="methodparam"><span class="type">resource </span> `$socket`</span>
, <span class="methodparam"><span class="type">int </span>
`$target_pid`</span> )

Exports the *WSAPROTOCOL\_INFO* structure into shared memory and returns
an identifier to be used with <span
class="function">socket\_wsaprotocol\_info\_import</span>. The exported
ID is only valid for the given `target_pid`.

> **Note**: <span class="simpara"> This function is available only on
> Windows. </span>

### Parameters

`socket`  
A valid socket resource.

`target_pid`  
The ID of the process which will import the socket.

### Return Values

Returns an identifier to be used for the import, or **`FALSE`** on
failure

### See Also

-   <span class="function">socket\_wsaprotocol\_info\_import</span>
-   <span class="function">socket\_wsaprotocol\_info\_release</span>

socket\_wsaprotocol\_info\_import
=================================

Imports a Socket from another Process

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">socket\_wsaprotocol\_info\_import</span> ( <span
class="methodparam"><span class="type">string</span> `$info_id`</span> )

Imports a socket which has formerly been exported from another process.

> **Note**: <span class="simpara"> This function is available only on
> Windows. </span>

### Parameters

`info_id`  
The ID which has been returned by a former call to <span
class="function">socket\_wsaprotocol\_info\_export</span>.

### Return Values

Returns the socket resource, or **`FALSE`** on failure

### See Also

-   <span class="function">socket\_wsaprotocol\_info\_export</span>

socket\_wsaprotocol\_info\_release
==================================

Releases an exported WSAPROTOCOL\_INFO Structure

### Description

<span class="type">bool</span> <span
class="methodname">socket\_wsaprotocol\_info\_release</span> ( <span
class="methodparam"><span class="type">string</span> `$info_id`</span> )

Releases the shared memory corresponding to the given `info_id`.

> **Note**: <span class="simpara"> This function is available only on
> Windows. </span>

### Parameters

`info_id`  
The ID which has been returned by a former call to <span
class="function">socket\_wsaprotocol\_info\_export</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">socket\_wsaprotocol\_info\_export</span>

**Table of Contents**

-   [socket\_accept](/ref/sockets.html#socket_accept) — Accepts a
    connection on a socket
-   [socket\_addrinfo\_bind](/ref/sockets.html#socket_addrinfo_bind) —
    Create and bind to a socket from a given addrinfo
-   [socket\_addrinfo\_connect](/ref/sockets.html#socket_addrinfo_connect)
    — Create and connect to a socket from a given addrinfo
-   [socket\_addrinfo\_explain](/ref/sockets.html#socket_addrinfo_explain)
    — Get information about addrinfo
-   [socket\_addrinfo\_lookup](/ref/sockets.html#socket_addrinfo_lookup)
    — Get array with contents of getaddrinfo about the given hostname
-   [socket\_bind](/ref/sockets.html#socket_bind) — Binds a name to a
    socket
-   [socket\_clear\_error](/ref/sockets.html#socket_clear_error) —
    Clears the error on the socket or the last error code
-   [socket\_close](/ref/sockets.html#socket_close) — Closes a socket
    resource
-   [socket\_cmsg\_space](/ref/sockets.html#socket_cmsg_space) —
    Calculate message buffer size
-   [socket\_connect](/ref/sockets.html#socket_connect) — Initiates a
    connection on a socket
-   [socket\_create\_listen](/ref/sockets.html#socket_create_listen) —
    Opens a socket on port to accept connections
-   [socket\_create\_pair](/ref/sockets.html#socket_create_pair) —
    Creates a pair of indistinguishable sockets and stores them in an
    array
-   [socket\_create](/ref/sockets.html#socket_create) — Create a socket
    (endpoint for communication)
-   [socket\_export\_stream](/ref/sockets.html#socket_export_stream) —
    Export a socket extension resource into a stream that encapsulates a
    socket
-   [socket\_get\_option](/ref/sockets.html#socket_get_option) — Gets
    socket options for the socket
-   [socket\_getopt](/ref/sockets.html#socket_getopt) — Alias of
    socket\_get\_option
-   [socket\_getpeername](/ref/sockets.html#socket_getpeername) —
    Queries the remote side of the given socket which may either result
    in host/port or in a Unix filesystem path, dependent on its type
-   [socket\_getsockname](/ref/sockets.html#socket_getsockname) —
    Queries the local side of the given socket which may either result
    in host/port or in a Unix filesystem path, dependent on its type
-   [socket\_import\_stream](/ref/sockets.html#socket_import_stream) —
    Import a stream
-   [socket\_last\_error](/ref/sockets.html#socket_last_error) — Returns
    the last error on the socket
-   [socket\_listen](/ref/sockets.html#socket_listen) — Listens for a
    connection on a socket
-   [socket\_read](/ref/sockets.html#socket_read) — Reads a maximum of
    length bytes from a socket
-   [socket\_recv](/ref/sockets.html#socket_recv) — Receives data from a
    connected socket
-   [socket\_recvfrom](/ref/sockets.html#socket_recvfrom) — Receives
    data from a socket whether or not it is connection-oriented
-   [socket\_recvmsg](/ref/sockets.html#socket_recvmsg) — Read a message
-   [socket\_select](/ref/sockets.html#socket_select) — Runs the
    select() system call on the given arrays of sockets with a specified
    timeout
-   [socket\_send](/ref/sockets.html#socket_send) — Sends data to a
    connected socket
-   [socket\_sendmsg](/ref/sockets.html#socket_sendmsg) — Send a message
-   [socket\_sendto](/ref/sockets.html#socket_sendto) — Sends a message
    to a socket, whether it is connected or not
-   [socket\_set\_block](/ref/sockets.html#socket_set_block) — Sets
    blocking mode on a socket resource
-   [socket\_set\_nonblock](/ref/sockets.html#socket_set_nonblock) —
    Sets nonblocking mode for file descriptor fd
-   [socket\_set\_option](/ref/sockets.html#socket_set_option) — Sets
    socket options for the socket
-   [socket\_setopt](/ref/sockets.html#socket_setopt) — Alias of
    socket\_set\_option
-   [socket\_shutdown](/ref/sockets.html#socket_shutdown) — Shuts down a
    socket for receiving, sending, or both
-   [socket\_strerror](/ref/sockets.html#socket_strerror) — Return a
    string describing a socket error
-   [socket\_write](/ref/sockets.html#socket_write) — Write to a socket
-   [socket\_wsaprotocol\_info\_export](/ref/sockets.html#socket_wsaprotocol_info_export)
    — Exports the WSAPROTOCOL\_INFO Structure
-   [socket\_wsaprotocol\_info\_import](/ref/sockets.html#socket_wsaprotocol_info_import)
    — Imports a Socket from another Process
-   [socket\_wsaprotocol\_info\_release](/ref/sockets.html#socket_wsaprotocol_info_release)
    — Releases an exported WSAPROTOCOL\_INFO Structure

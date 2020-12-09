Sockets
=======

**Table of Contents**

-   [Introduction](/intro/sockets.html)
-   [Installing/Configuring](/sockets/setup.html)
    -   [Requirements](/sockets/setup.html#Requirements)
    -   [Installation](/sockets/setup.html#Installation)
    -   [Runtime
        Configuration](/sockets/setup.html#Runtime%20Configuration)
    -   [Resource Types](/sockets/setup.html#Resource%20Types)
-   [Predefined Constants](/sockets/constants.html)
-   [Examples](/sockets/examples.html)
-   [Socket Errors](/sockets/errors.html)
-   [Socket Functions](/ref/sockets.html)
    -   [socket\_accept](/ref/sockets.html#socket_accept) — Accepts a
        connection on a socket
    -   [socket\_addrinfo\_bind](/ref/sockets.html#socket_addrinfo_bind)
        — Create and bind to a socket from a given addrinfo
    -   [socket\_addrinfo\_connect](/ref/sockets.html#socket_addrinfo_connect)
        — Create and connect to a socket from a given addrinfo
    -   [socket\_addrinfo\_explain](/ref/sockets.html#socket_addrinfo_explain)
        — Get information about addrinfo
    -   [socket\_addrinfo\_lookup](/ref/sockets.html#socket_addrinfo_lookup)
        — Get array with contents of getaddrinfo about the given
        hostname
    -   [socket\_bind](/ref/sockets.html#socket_bind) — Binds a name to
        a socket
    -   [socket\_clear\_error](/ref/sockets.html#socket_clear_error) —
        Clears the error on the socket or the last error code
    -   [socket\_close](/ref/sockets.html#socket_close) — Closes a
        socket resource
    -   [socket\_cmsg\_space](/ref/sockets.html#socket_cmsg_space) —
        Calculate message buffer size
    -   [socket\_connect](/ref/sockets.html#socket_connect) — Initiates
        a connection on a socket
    -   [socket\_create\_listen](/ref/sockets.html#socket_create_listen)
        — Opens a socket on port to accept connections
    -   [socket\_create\_pair](/ref/sockets.html#socket_create_pair) —
        Creates a pair of indistinguishable sockets and stores them in
        an array
    -   [socket\_create](/ref/sockets.html#socket_create) — Create a
        socket (endpoint for communication)
    -   [socket\_export\_stream](/ref/sockets.html#socket_export_stream)
        — Export a socket extension resource into a stream that
        encapsulates a socket
    -   [socket\_get\_option](/ref/sockets.html#socket_get_option) —
        Gets socket options for the socket
    -   [socket\_getopt](/ref/sockets.html#socket_getopt) — Alias of
        socket\_get\_option
    -   [socket\_getpeername](/ref/sockets.html#socket_getpeername) —
        Queries the remote side of the given socket which may either
        result in host/port or in a Unix filesystem path, dependent on
        its type
    -   [socket\_getsockname](/ref/sockets.html#socket_getsockname) —
        Queries the local side of the given socket which may either
        result in host/port or in a Unix filesystem path, dependent on
        its type
    -   [socket\_import\_stream](/ref/sockets.html#socket_import_stream)
        — Import a stream
    -   [socket\_last\_error](/ref/sockets.html#socket_last_error) —
        Returns the last error on the socket
    -   [socket\_listen](/ref/sockets.html#socket_listen) — Listens for
        a connection on a socket
    -   [socket\_read](/ref/sockets.html#socket_read) — Reads a maximum
        of length bytes from a socket
    -   [socket\_recv](/ref/sockets.html#socket_recv) — Receives data
        from a connected socket
    -   [socket\_recvfrom](/ref/sockets.html#socket_recvfrom) — Receives
        data from a socket whether or not it is connection-oriented
    -   [socket\_recvmsg](/ref/sockets.html#socket_recvmsg) — Read a
        message
    -   [socket\_select](/ref/sockets.html#socket_select) — Runs the
        select() system call on the given arrays of sockets with a
        specified timeout
    -   [socket\_send](/ref/sockets.html#socket_send) — Sends data to a
        connected socket
    -   [socket\_sendmsg](/ref/sockets.html#socket_sendmsg) — Send a
        message
    -   [socket\_sendto](/ref/sockets.html#socket_sendto) — Sends a
        message to a socket, whether it is connected or not
    -   [socket\_set\_block](/ref/sockets.html#socket_set_block) — Sets
        blocking mode on a socket resource
    -   [socket\_set\_nonblock](/ref/sockets.html#socket_set_nonblock) —
        Sets nonblocking mode for file descriptor fd
    -   [socket\_set\_option](/ref/sockets.html#socket_set_option) —
        Sets socket options for the socket
    -   [socket\_setopt](/ref/sockets.html#socket_setopt) — Alias of
        socket\_set\_option
    -   [socket\_shutdown](/ref/sockets.html#socket_shutdown) — Shuts
        down a socket for receiving, sending, or both
    -   [socket\_strerror](/ref/sockets.html#socket_strerror) — Return a
        string describing a socket error
    -   [socket\_write](/ref/sockets.html#socket_write) — Write to a
        socket
    -   [socket\_wsaprotocol\_info\_export](/ref/sockets.html#socket_wsaprotocol_info_export)
        — Exports the WSAPROTOCOL\_INFO Structure
    -   [socket\_wsaprotocol\_info\_import](/ref/sockets.html#socket_wsaprotocol_info_import)
        — Imports a Socket from another Process
    -   [socket\_wsaprotocol\_info\_release](/ref/sockets.html#socket_wsaprotocol_info_release)
        — Releases an exported WSAPROTOCOL\_INFO Structure
-   [Socket](/class/socket.html) — The Socket class
-   [AddressInfo](/class/addressinfo.html) — The AddressInfo class

Introduction
------------

A fully opaque class which replaces *Socket* resources as of PHP 8.0.0.

Class synopsis
--------------

**Socket**

<span class="ooclass"> <span class="modifier">final</span> class
**Socket** </span> {

}

Introduction
------------

A fully opaque class which replaces *AddressInfo* resources as of PHP
8.0.0.

Class synopsis
--------------

**AddressInfo**

<span class="ooclass"> <span class="modifier">final</span> class
**AddressInfo** </span> {

}

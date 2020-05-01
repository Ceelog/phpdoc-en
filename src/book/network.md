Network
=======

**Table of Contents**

-   [Introduction](/intro/network.html)
-   [Installing/Configuring](/network/setup.html)
    -   [Requirements](/network/setup.html#Requirements)
    -   [Installation](/network/setup.html#Installation)
    -   [Runtime
        Configuration](/network/setup.html#Runtime%20Configuration)
    -   [Resource Types](/network/setup.html#Resource%20Types)
-   [Predefined Constants](/network/constants.html)
-   [Network Functions](/ref/network.html)
    -   [checkdnsrr](/ref/network.html#checkdnsrr) — Check DNS records
        corresponding to a given Internet host name or IP address
    -   [closelog](/ref/network.html#closelog) — Close connection to
        system logger
    -   [define\_syslog\_variables](/ref/network.html#define_syslog_variables)
        — Initializes all syslog related variables
    -   [dns\_check\_record](/ref/network.html#dns_check_record) — Alias
        of checkdnsrr
    -   [dns\_get\_mx](/ref/network.html#dns_get_mx) — Alias of getmxrr
    -   [dns\_get\_record](/ref/network.html#dns_get_record) — Fetch DNS
        Resource Records associated with a hostname
    -   [fsockopen](/ref/network.html#fsockopen) — Open Internet or Unix
        domain socket connection
    -   [gethostbyaddr](/ref/network.html#gethostbyaddr) — Get the
        Internet host name corresponding to a given IP address
    -   [gethostbyname](/ref/network.html#gethostbyname) — Get the IPv4
        address corresponding to a given Internet host name
    -   [gethostbynamel](/ref/network.html#gethostbynamel) — Get a list
        of IPv4 addresses corresponding to a given Internet host name
    -   [gethostname](/ref/network.html#gethostname) — Gets the host
        name
    -   [getmxrr](/ref/network.html#getmxrr) — Get MX records
        corresponding to a given Internet host name
    -   [getprotobyname](/ref/network.html#getprotobyname) — Get
        protocol number associated with protocol name
    -   [getprotobynumber](/ref/network.html#getprotobynumber) — Get
        protocol name associated with protocol number
    -   [getservbyname](/ref/network.html#getservbyname) — Get port
        number associated with an Internet service and protocol
    -   [getservbyport](/ref/network.html#getservbyport) — Get Internet
        service which corresponds to port and protocol
    -   [header\_register\_callback](/ref/network.html#header_register_callback)
        — Call a header function
    -   [header\_remove](/ref/network.html#header_remove) — Remove
        previously set headers
    -   [header](/ref/network.html#header) — Send a raw HTTP header
    -   [headers\_list](/ref/network.html#headers_list) — Returns a list
        of response headers sent (or ready to send)
    -   [headers\_sent](/ref/network.html#headers_sent) — Checks if or
        where headers have been sent
    -   [http\_response\_code](/ref/network.html#http_response_code) —
        Get or Set the HTTP response code
    -   [inet\_ntop](/ref/network.html#inet_ntop) — Converts a packed
        internet address to a human readable representation
    -   [inet\_pton](/ref/network.html#inet_pton) — Converts a human
        readable IP address to its packed in\_addr representation
    -   [ip2long](/ref/network.html#ip2long) — Converts a string
        containing an (IPv4) Internet Protocol dotted address into a
        long integer
    -   [long2ip](/ref/network.html#long2ip) — Converts an long integer
        address into a string in (IPv4) Internet standard dotted format
    -   [openlog](/ref/network.html#openlog) — Open connection to system
        logger
    -   [pfsockopen](/ref/network.html#pfsockopen) — Open persistent
        Internet or Unix domain socket connection
    -   [setcookie](/ref/network.html#setcookie) — Send a cookie
    -   [setrawcookie](/ref/network.html#setrawcookie) — Send a cookie
        without urlencoding the cookie value
    -   [socket\_get\_status](/ref/network.html#socket_get_status) —
        Alias of stream\_get\_meta\_data
    -   [socket\_set\_blocking](/ref/network.html#socket_set_blocking) —
        Alias of stream\_set\_blocking
    -   [socket\_set\_timeout](/ref/network.html#socket_set_timeout) —
        Alias of stream\_set\_timeout
    -   [syslog](/ref/network.html#syslog) — Generate a system log
        message

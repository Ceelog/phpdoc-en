Internet Domain: TCP, UDP, SSL, and TLS
---------------------------------------

*sslv2://* & *sslv3://* as of PHP 5.0.2

> **Note**: <span class="simpara"> If no transport is specified,
> *tcp://* will be assumed. </span>

-   <span class="simpara">*127.0.0.1*</span>
-   <span class="simpara">*fe80::1*</span>
-   <span class="simpara">*www.example.com*</span>
-   <span class="simpara">*tcp://127.0.0.1*</span>
-   <span class="simpara">*tcp://fe80::1*</span>
-   <span class="simpara">*tcp://www.example.com*</span>
-   <span class="simpara">*udp://www.example.com*</span>
-   <span class="simpara">*ssl://www.example.com*</span>
-   <span class="simpara">*sslv2://www.example.com*</span>
-   <span class="simpara">*sslv3://www.example.com*</span>
-   <span class="simpara">*tls://www.example.com*</span>

Internet Domain sockets expect a port number in addition to a target
address. In the case of <span class="function">fsockopen</span> this is
specified in a second parameter and therefore does not impact the
formatting of transport URL. With <span
class="function">stream\_socket\_client</span> and related functions as
with traditional URLs however, the port number is specified as a suffix
of the transport URL delimited by a colon.

-   <span class="simpara">*tcp://127.0.0.1:80*</span>
-   <span class="simpara">*tcp://\[fe80::1\]:80*</span>
-   <span class="simpara">*tcp://www.example.com:80*</span>

> **Note**: **IPv6 numeric addresses with port numbers**  
> <span class="simpara"> In the second example above, while the IPv4 and
> hostname examples are left untouched apart from the addition of their
> colon and portnumber, the IPv6 address is wrapped in square brackets:
> *\[fe80::1\]*. This is to distinguish between the colons used in an
> IPv6 address and the colon used to delimit the portnumber. </span>

The *ssl://* and *tls://* transports (available only when openssl
support is compiled into PHP) are extensions of the *tcp://* transport
which include SSL encryption.

*ssl://* will attempt to negotiate an SSL V2, or SSL V3 connection
depending on the capabilities and preferences of the remote host.
*sslv2://* and *sslv3://* will select the SSL V2 or SSL V3 protocol
explicitly.

Unix Domain: Unix and UDG
-------------------------

*unix://* and *udg://* (udg:// since PHP 5).

-   <span class="simpara">*unix:///tmp/mysock*</span>
-   <span class="simpara">*udg:///tmp/mysock*</span>

*unix://* provides access to a socket stream connection in the Unix
domain. *udg://* provides an alternate transport to a Unix domain socket
using the user datagram protocol.

Unix domain sockets, unlike Internet domain sockets, do not expect a
port number. In the case of <span class="function">fsockopen</span> the
`portno` parameter should be set to 0.

> **Note**: <span class="simpara"> Unix domain sockets are not supported
> on Windows. </span>

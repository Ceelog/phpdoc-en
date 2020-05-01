The socket extension implements a low-level interface to the socket
communication functions based on the popular BSD sockets, providing the
possibility to act as a socket server as well as a client.

For a more generic client-side socket interface, see <span
class="function">stream\_socket\_client</span>, <span
class="function">stream\_socket\_server</span>, <span
class="function">fsockopen</span>, and <span
class="function">pfsockopen</span>.

When using these functions, it is important to remember that while many
of them have identical names to their C counterparts, they often have
different declarations. Please be sure to read the descriptions to avoid
confusion.

Those unfamiliar with socket programming can find a lot of useful
material in the appropriate Unix man pages, and there is a great deal of
tutorial information on socket programming in C on the web, much of
which can be applied, with slight modifications, to socket programming
in PHP. The
<a href="http://www.unixguide.net/network/socketfaq/" class="link external">» Unix Socket FAQ</a>
might be a good start.

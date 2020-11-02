Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`AF_UNIX`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`AF_INET`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`AF_INET6`** (<span class="type">int</span>)  
<span class="simpara"> Only available if compiled with IPv6 support.
</span>

**`SOCK_STREAM`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCK_DGRAM`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCK_RAW`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCK_SEQPACKET`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCK_RDM`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`MSG_OOB`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`MSG_WAITALL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`MSG_PEEK`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`MSG_DONTROUTE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`MSG_EOR`** (<span class="type">int</span>)  
<span class="simpara"> Not available on Windows platforms. </span>

**`MSG_EOF`** (<span class="type">int</span>)  
<span class="simpara"> Not available on Windows platforms. </span>

**`SO_DEBUG`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_REUSEADDR`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_REUSEPORT`** (<span class="type">int</span>)  
<span class="simpara"> This constant is only available in PHP 5.4.10 or
later on platforms that support the **`SO_REUSEPORT`** socket option:
this includes macOS and FreeBSD, but does not include Linux or Windows.
</span>

**`SO_KEEPALIVE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_DONTROUTE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_LINGER`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_BROADCAST`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_OOBINLINE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_SNDBUF`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_RCVBUF`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_SNDLOWAT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_RCVLOWAT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_SNDTIMEO`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_RCVTIMEO`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_TYPE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SO_ERROR`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`TCP_NODELAY`** (<span class="type">int</span>)  
<span class="simpara"> Used to disable Nagle TCP algorithm. Added in PHP
5.2.7. </span>

**`SOL_SOCKET`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`PHP_NORMAL_READ`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`PHP_BINARY_READ`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOL_TCP`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOL_UDP`** (<span class="type">int</span>)  
<span class="simpara"> </span>

The following constants are defined under Windows and UNIX-like
platforms. Each constant is only defined if their equal is available on
the platform.

**`SOCKET_EINTR`** (<span class="type">int</span>)  
<span class="simpara"> Interrupted system call. </span>

**`SOCKET_EBADF`** (<span class="type">int</span>)  
<span class="simpara"> Bad file number. </span>

**`SOCKET_EACCES`** (<span class="type">int</span>)  
<span class="simpara"> Permission denied. </span>

**`SOCKET_EFAULT`** (<span class="type">int</span>)  
<span class="simpara"> Bad address. </span>

**`SOCKET_EINVAL`** (<span class="type">int</span>)  
<span class="simpara"> Invalid argument. </span>

**`SOCKET_EMFILE`** (<span class="type">int</span>)  
<span class="simpara"> Too many open files. </span>

**`SOCKET_ENAMETOOLONG`** (<span class="type">int</span>)  
<span class="simpara"> File name too long. </span>

**`SOCKET_ENOTEMPTY`** (<span class="type">int</span>)  
<span class="simpara"> Directory not empty. </span>

**`SOCKET_ELOOP`** (<span class="type">int</span>)  
<span class="simpara"> Too many symbolic links encountered. </span>

**`SOCKET_EWOULDBLOCK`** (<span class="type">int</span>)  
<span class="simpara"> Operation would block. </span>

**`SOCKET_EREMOTE`** (<span class="type">int</span>)  
<span class="simpara"> Object is remote. </span>

**`SOCKET_EUSERS`** (<span class="type">int</span>)  
<span class="simpara"> Too many users. </span>

**`SOCKET_ENOTSOCK`** (<span class="type">int</span>)  
<span class="simpara"> Socket operation on non-socket. </span>

**`SOCKET_EDESTADDRREQ`** (<span class="type">int</span>)  
<span class="simpara"> Destination address required. </span>

**`SOCKET_EMSGSIZE`** (<span class="type">int</span>)  
<span class="simpara"> Message too long. </span>

**`SOCKET_EPROTOTYPE`** (<span class="type">int</span>)  
<span class="simpara"> Protocol wrong type for socket. </span>

**`SOCKET_EPROTONOSUPPORT`** (<span class="type">int</span>)  
<span class="simpara"> Protocol not supported. </span>

**`SOCKET_ESOCKTNOSUPPORT`** (<span class="type">int</span>)  
<span class="simpara"> Socket type not supported. </span>

**`SOCKET_EOPNOTSUPP`** (<span class="type">int</span>)  
<span class="simpara"> Operation not supported on transport endpoint.
</span>

**`SOCKET_EPFNOSUPPORT`** (<span class="type">int</span>)  
<span class="simpara"> Protocol family not supported. </span>

**`SOCKET_EAFNOSUPPORT`** (<span class="type">int</span>)  
<span class="simpara"> Address family not supported by protocol. </span>

**`SOCKET_EADDRNOTAVAIL`** (<span class="type">int</span>)  
<span class="simpara"> Cannot assign requested address. </span>

**`SOCKET_ENETDOWN`** (<span class="type">int</span>)  
<span class="simpara"> Network is down. </span>

**`SOCKET_ENETUNREACH`** (<span class="type">int</span>)  
<span class="simpara"> Network is unreachable. </span>

**`SOCKET_ENETRESET`** (<span class="type">int</span>)  
<span class="simpara"> Network dropped connection because of reset.
</span>

**`SOCKET_ECONNABORTED`** (<span class="type">int</span>)  
<span class="simpara"> Software caused connection abort. </span>

**`SOCKET_ECONNRESET`** (<span class="type">int</span>)  
<span class="simpara"> Connection reset by peer. </span>

**`SOCKET_ENOBUFS`** (<span class="type">int</span>)  
<span class="simpara"> No buffer space available. </span>

**`SOCKET_EISCONN`** (<span class="type">int</span>)  
<span class="simpara"> Transport endpoint is already connected. </span>

**`SOCKET_ENOTCONN`** (<span class="type">int</span>)  
<span class="simpara"> Transport endpoint is not connected. </span>

**`SOCKET_ESHUTDOWN`** (<span class="type">int</span>)  
<span class="simpara"> Cannot send after transport endpoint shutdown.
</span>

**`SOCKET_ETIMEDOUT`** (<span class="type">int</span>)  
<span class="simpara"> Connection timed out. </span>

**`SOCKET_ECONNREFUSED`** (<span class="type">int</span>)  
<span class="simpara"> Connection refused. </span>

**`SOCKET_EHOSTDOWN`** (<span class="type">int</span>)  
<span class="simpara"> Host is down. </span>

**`SOCKET_EHOSTUNREACH`** (<span class="type">int</span>)  
<span class="simpara"> No route to host. </span>

**`SOCKET_EALREADY`** (<span class="type">int</span>)  
<span class="simpara"> Operation already in progress. </span>

**`SOCKET_EINPROGRESS`** (<span class="type">int</span>)  
<span class="simpara"> Operation now in progress. </span>

The following constants are only defined under Windows.

**`SOCKET_ENOPROTOOPT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_EADDRINUSE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_ETOOMYREFS`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_EPROCLIM`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_EDUOT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_ESTALE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_EDISCON`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_SYSNOTREADY`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_VERNOTSUPPORTED`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_NOTINITIALISED`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_HOST_NOT_FOUND`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_TRY_AGAIN`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_NO_RECOVERY`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_NO_DATA`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`SOCKET_NO_ADDRESS`** (<span class="type">int</span>)  
<span class="simpara"> </span>

The following constants are only available on UNIX-like platforms. Each
constant is only defined if their equal is available on the platform.

**`SOCKET_EPERM`** (<span class="type">int</span>)  
<span class="simpara"> Operation not permitted. </span>

**`SOCKET_ENOENT`** (<span class="type">int</span>)  
<span class="simpara"> No such file or directory. </span>

**`SOCKET_EIO`** (<span class="type">int</span>)  
<span class="simpara"> I/O error. </span>

**`SOCKET_ENXIO`** (<span class="type">int</span>)  
<span class="simpara"> No such device or address. </span>

**`SOCKET_E2BIG`** (<span class="type">int</span>)  
<span class="simpara"> Arg list too long. </span>

**`SOCKET_EAGAIN`** (<span class="type">int</span>)  
<span class="simpara"> Try again. </span>

**`SOCKET_ENOMEM`** (<span class="type">int</span>)  
<span class="simpara"> Out of memory. </span>

**`SOCKET_ENOTBLK`** (<span class="type">int</span>)  
<span class="simpara"> Block device required. </span>

**`SOCKET_EBUSY`** (<span class="type">int</span>)  
<span class="simpara"> Device or resource busy. </span>

**`SOCKET_EEXIST`** (<span class="type">int</span>)  
<span class="simpara"> File exists. </span>

**`SOCKET_EXDEV`** (<span class="type">int</span>)  
<span class="simpara"> Cross-device link. </span>

**`SOCKET_ENODEV`** (<span class="type">int</span>)  
<span class="simpara"> No such device. </span>

**`SOCKET_ENOTDIR`** (<span class="type">int</span>)  
<span class="simpara"> Not a directory. </span>

**`SOCKET_EISDIR`** (<span class="type">int</span>)  
<span class="simpara"> Is a directory. </span>

**`SOCKET_ENFILE`** (<span class="type">int</span>)  
<span class="simpara"> File table overflow. </span>

**`SOCKET_ENOTTY`** (<span class="type">int</span>)  
<span class="simpara"> Not a typewriter. </span>

**`SOCKET_ENOSPC`** (<span class="type">int</span>)  
<span class="simpara"> No space left on device. </span>

**`SOCKET_ESPIPE`** (<span class="type">int</span>)  
<span class="simpara"> Illegal seek. </span>

**`SOCKET_EROFS`** (<span class="type">int</span>)  
<span class="simpara"> Read-only file system. </span>

**`SOCKET_EMLINK`** (<span class="type">int</span>)  
<span class="simpara"> Too many links. </span>

**`SOCKET_EPIPE`** (<span class="type">int</span>)  
<span class="simpara"> Broken pipe. </span>

**`SOCKET_ENOLCK`** (<span class="type">int</span>)  
<span class="simpara"> No record locks available. </span>

**`SOCKET_ENOSYS`** (<span class="type">int</span>)  
<span class="simpara"> Function not implemented. </span>

**`SOCKET_ENOMSG`** (<span class="type">int</span>)  
<span class="simpara"> No message of desired type. </span>

**`SOCKET_EIDRM`** (<span class="type">int</span>)  
<span class="simpara"> Identifier removed. </span>

**`SOCKET_ECHRNG`** (<span class="type">int</span>)  
<span class="simpara"> Channel number out of range. </span>

**`SOCKET_EL2NSYNC`** (<span class="type">int</span>)  
<span class="simpara"> Level 2 not synchronized. </span>

**`SOCKET_EL3HLT`** (<span class="type">int</span>)  
<span class="simpara"> Level 3 halted. </span>

**`SOCKET_EL3RST`** (<span class="type">int</span>)  
<span class="simpara"> Level 3 reset. </span>

**`SOCKET_ELNRNG`** (<span class="type">int</span>)  
<span class="simpara"> Link number out of range. </span>

**`SOCKET_EUNATCH`** (<span class="type">int</span>)  
<span class="simpara"> Protocol driver not attached. </span>

**`SOCKET_ENOCSI`** (<span class="type">int</span>)  
<span class="simpara"> No CSI structure available. </span>

**`SOCKET_EL2HLT`** (<span class="type">int</span>)  
<span class="simpara"> Level 2 halted. </span>

**`SOCKET_EBADE`** (<span class="type">int</span>)  
<span class="simpara"> Invalid exchange. </span>

**`SOCKET_EBADR`** (<span class="type">int</span>)  
<span class="simpara"> Invalid request descriptor. </span>

**`SOCKET_EXFULL`** (<span class="type">int</span>)  
<span class="simpara"> Exchange full. </span>

**`SOCKET_ENOANO`** (<span class="type">int</span>)  
<span class="simpara"> No anode. </span>

**`SOCKET_EBADRQC`** (<span class="type">int</span>)  
<span class="simpara"> Invalid request code. </span>

**`SOCKET_EBADSLT`** (<span class="type">int</span>)  
<span class="simpara"> Invalid slot. </span>

**`SOCKET_ENOSTR`** (<span class="type">int</span>)  
<span class="simpara"> Device not a stream. </span>

**`SOCKET_ENODATA`** (<span class="type">int</span>)  
<span class="simpara"> No data available. </span>

**`SOCKET_ETIME`** (<span class="type">int</span>)  
<span class="simpara"> Timer expired. </span>

**`SOCKET_ENOSR`** (<span class="type">int</span>)  
<span class="simpara"> Out of streams resources. </span>

**`SOCKET_ENONET`** (<span class="type">int</span>)  
<span class="simpara"> Machine is not on the network. </span>

**`SOCKET_ENOLINK`** (<span class="type">int</span>)  
<span class="simpara"> Link has been severed. </span>

**`SOCKET_EADV`** (<span class="type">int</span>)  
<span class="simpara"> Advertise error. </span>

**`SOCKET_ESRMNT`** (<span class="type">int</span>)  
<span class="simpara"> Srmount error. </span>

**`SOCKET_ECOMM`** (<span class="type">int</span>)  
<span class="simpara"> Communication error on send. </span>

**`SOCKET_EPROTO`** (<span class="type">int</span>)  
<span class="simpara"> Protocol error. </span>

**`SOCKET_EMULTIHOP`** (<span class="type">int</span>)  
<span class="simpara"> Multihop attempted. </span>

**`SOCKET_EBADMSG`** (<span class="type">int</span>)  
<span class="simpara"> Not a data message. </span>

**`SOCKET_ENOTUNIQ`** (<span class="type">int</span>)  
<span class="simpara"> Name not unique on network. </span>

**`SOCKET_EBADFD`** (<span class="type">int</span>)  
<span class="simpara"> File descriptor in bad state. </span>

**`SOCKET_EREMCHG`** (<span class="type">int</span>)  
<span class="simpara"> Remote address changed. </span>

**`SOCKET_ERESTART`** (<span class="type">int</span>)  
<span class="simpara"> Interrupted system call should be restarted.
</span>

**`SOCKET_ESTRPIPE`** (<span class="type">int</span>)  
<span class="simpara"> Streams pipe error. </span>

**`SOCKET_EPROTOOPT`** (<span class="type">int</span>)  
<span class="simpara"> Protocol not available. </span>

**`SOCKET_ADDRINUSE`** (<span class="type">int</span>)  
<span class="simpara"> Address already in use. </span>

**`SOCKET_ETOOMANYREFS`** (<span class="type">int</span>)  
<span class="simpara"> Too many references: cannot splice. </span>

**`SOCKET_EISNAM`** (<span class="type">int</span>)  
<span class="simpara"> Is a named type file. </span>

**`SOCKET_EREMOTEIO`** (<span class="type">int</span>)  
<span class="simpara"> Remote I/O error. </span>

**`SOCKET_EDQUOT`** (<span class="type">int</span>)  
<span class="simpara"> Quota exceeded. </span>

**`SOCKET_ENOMEDIUM`** (<span class="type">int</span>)  
<span class="simpara"> No medium found. </span>

**`SOCKET_EMEDIUMTYPE`** (<span class="type">int</span>)  
<span class="simpara"> Wrong medium type. </span>

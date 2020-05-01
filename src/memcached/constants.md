Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`Memcached::OPT_COMPRESSION`**  
Enables or disables payload compression. When enabled, item values
longer than a certain threshold (currently 100 bytes) will be compressed
during storage and decompressed during retrieval transparently.

Type: *boolean*, default: **`TRUE`**.

**`Memcached::OPT_SERIALIZER`**  
Specifies the serializer to use for serializing non-scalar values. The
valid serializers are **`Memcached::SERIALIZER_PHP`** or
**`Memcached::SERIALIZER_IGBINARY`**. The latter is supported only when
memcached is configured with *--enable-memcached-igbinary* option and
the *igbinary* extension is loaded.

Type: *integer*, default: **`Memcached::SERIALIZER_PHP`**.

**`Memcached::SERIALIZER_PHP`**  
The default PHP serializer.

**`Memcached::SERIALIZER_IGBINARY`**  
The
<a href="https://github.com/igbinary/igbinary" class="link external">» igbinary</a>
serializer. Instead of textual representation it stores PHP data
structures in a compact binary form, resulting in space and time gains.

**`Memcached::SERIALIZER_JSON`**  
The JSON serializer. Requires PHP 5.2.10+.

**`Memcached::OPT_PREFIX_KEY`**  
This can be used to create a "domain" for your item keys. The value
specified here will be prefixed to each of the keys. It cannot be longer
than *128* characters and will reduce the maximum available key size.
The prefix is applied only to the item keys, not to the server keys.

Type: *string*, default: *""*.

**`Memcached::OPT_HASH`**  
Specifies the hashing algorithm used for the item keys. The valid values
are supplied via **`Memcached::HASH_*`** constants. Each hash algorithm
has its advantages and its disadvantages. Go with the default if you
don't know or don't care.

Type: *integer*, default: **`Memcached::HASH_DEFAULT`**

**`Memcached::HASH_DEFAULT`**  
The default (Jenkins one-at-a-time) item key hashing algorithm.

**`Memcached::HASH_MD5`**  
MD5 item key hashing algorithm.

**`Memcached::HASH_CRC`**  
CRC item key hashing algorithm.

**`Memcached::HASH_FNV1_64`**  
FNV1\_64 item key hashing algorithm.

**`Memcached::HASH_FNV1A_64`**  
FNV1\_64A item key hashing algorithm.

**`Memcached::HASH_FNV1_32`**  
FNV1\_32 item key hashing algorithm.

**`Memcached::HASH_FNV1A_32`**  
FNV1\_32A item key hashing algorithm.

**`Memcached::HASH_HSIEH`**  
Hsieh item key hashing algorithm.

**`Memcached::HASH_MURMUR`**  
Murmur item key hashing algorithm.

**`Memcached::OPT_DISTRIBUTION`**  
Specifies the method of distributing item keys to the servers. Currently
supported methods are modulo and consistent hashing. Consistent hashing
delivers better distribution and allows servers to be added to the
cluster with minimal cache losses.

Type: *integer*, default: **`Memcached::DISTRIBUTION_MODULA.`**

**`Memcached::DISTRIBUTION_MODULA`**  
Modulo-based key distribution algorithm.

**`Memcached::DISTRIBUTION_CONSISTENT`**  
Consistent hashing key distribution algorithm (based on libketama).

**`Memcached::OPT_LIBKETAMA_COMPATIBLE`**  
Enables or disables compatibility with libketama-like behavior. When
enabled, the item key hashing algorithm is set to MD5 and distribution
is set to be weighted consistent hashing distribution. This is useful
because other libketama-based clients (Python, Ruby, etc.) with the same
server configuration will be able to access the keys transparently.

> **Note**:
>
> It is highly recommended to enable this option if you want to use
> consistent hashing, and it may be enabled by default in future
> releases.

Type: *boolean*, default: **`FALSE`**.

**`Memcached::OPT_BUFFER_WRITES`**  
Enables or disables buffered I/O. Enabling buffered I/O causes storage
commands to "buffer" instead of being sent. Any action that retrieves
data causes this buffer to be sent to the remote connection. Quitting
the connection or closing down the connection will also cause the
buffered data to be pushed to the remote connection.

Type: *boolean*, default: **`FALSE`**.

**`Memcached::OPT_BINARY_PROTOCOL`**  
Enable the use of the binary protocol. Please note that you cannot
toggle this option on an open connection.

Type: *boolean*, default: **`FALSE`**.

**`Memcached::OPT_NO_BLOCK`**  
Enables or disables asynchronous I/O. This is the fastest transport
available for storage functions.

Type: *boolean*, default: **`FALSE`**.

**`Memcached::OPT_TCP_NODELAY`**  
Enables or disables the no-delay feature for connecting sockets (may be
faster in some environments).

Type: *boolean*, default: **`FALSE`**.

**`Memcached::OPT_SOCKET_SEND_SIZE`**  
The maximum socket send buffer in bytes.

Type: *integer*, default: varies by platform/kernel configuration.

**`Memcached::OPT_SOCKET_RECV_SIZE`**  
The maximum socket receive buffer in bytes.

Type: *integer*, default: varies by platform/kernel configuration.

**`Memcached::OPT_CONNECT_TIMEOUT`**  
In non-blocking mode this set the value of the timeout during socket
connection, in milliseconds.

Type: *integer*, default: *1000*.

**`Memcached::OPT_RETRY_TIMEOUT`**  
The amount of time, in seconds, to wait until retrying a failed
connection attempt.

Type: *integer*, default: *0*.

**`Memcached::OPT_SEND_TIMEOUT`**  
Socket sending timeout, in microseconds. In cases where you cannot use
non-blocking I/O this will allow you to still have timeouts on the
sending of data.

Type: *integer*, default: *0*.

**`Memcached::OPT_RECV_TIMEOUT`**  
Socket reading timeout, in microseconds. In cases where you cannot use
non-blocking I/O this will allow you to still have timeouts on the
reading of data.

Type: *integer*, default: *0*.

**`Memcached::OPT_POLL_TIMEOUT`**  
Timeout for connection polling, in milliseconds.

Type: *integer*, default: *1000*.

**`Memcached::OPT_CACHE_LOOKUPS`**  
Enables or disables caching of DNS lookups.

Type: *boolean*, default: **`FALSE`**.

**`Memcached::OPT_SERVER_FAILURE_LIMIT`**  
Specifies the failure limit for server connection attempts. The server
will be removed after this many continuous connection failures.

Type: *integer*, default: *0*.

**`Memcached::HAVE_IGBINARY`**  
Indicates whether igbinary serializer support is available.

Type: *boolean*.

**`Memcached::HAVE_JSON`**  
Indicates whether JSON serializer support is available.

Type: *boolean*.

**`Memcached::HAVE_MSGPACK`**  
Indicates whether msgpack serializer support is available.

Type: *boolean*.

Available as of Memcached 3.0.0.

**`Memcached::HAVE_SESSION`**  
Type: *boolean*.

Available as of Memcached 3.0.0.

**`Memcached::HAVE_SASL`**  
Type: *boolean*.

Available as of Memcached 3.0.0.

**`Memcached::GET_EXTENDED`**  
A flag for <span class="function">Memcached::get</span>, <span
class="function">Memcached::getMulti</span> and <span
class="function">Memcached::getMultiByKey</span> to ensure that the CAS
token values are returned as well.

Available as of Memcached 3.0.0.

**`Memcached::GET_PRESERVE_ORDER`**  
A flag for <span class="function">Memcached::getMulti</span> and <span
class="function">Memcached::getMultiByKey</span> to ensure that the keys
are returned in the same order as they were requested in. Non-existing
keys get a default value of NULL.

**`Memcached::RES_SUCCESS`**  
The operation was successful.

**`Memcached::RES_FAILURE`**  
The operation failed in some fashion.

**`Memcached::RES_HOST_LOOKUP_FAILURE`**  
DNS lookup failed.

**`Memcached::RES_UNKNOWN_READ_FAILURE`**  
Failed to read network data.

**`Memcached::RES_PROTOCOL_ERROR`**  
Bad command in memcached protocol.

**`Memcached::RES_CLIENT_ERROR`**  
Error on the client side.

**`Memcached::RES_SERVER_ERROR`**  
Error on the server side.

**`Memcached::RES_WRITE_FAILURE`**  
Failed to write network data.

**`Memcached::RES_DATA_EXISTS`**  
Failed to do compare-and-swap: item you are trying to store has been
modified since you last fetched it.

**`Memcached::RES_NOTSTORED`**  
Item was not stored: but not because of an error. This normally means
that either the condition for an "add" or a "replace" command wasn't
met, or that the item is in a delete queue.

**`Memcached::RES_NOTFOUND`**  
Item with this key was not found (with "get" operation or "cas"
operations).

**`Memcached::RES_PARTIAL_READ`**  
Partial network data read error.

**`Memcached::RES_SOME_ERRORS`**  
Some errors occurred during multi-get.

**`Memcached::RES_NO_SERVERS`**  
Server list is empty.

**`Memcached::RES_END`**  
End of result set.

**`Memcached::RES_ERRNO`**  
System error.

**`Memcached::RES_BUFFERED`**  
The operation was buffered.

**`Memcached::RES_TIMEOUT`**  
The operation timed out.

**`Memcached::RES_BAD_KEY_PROVIDED`**  
Bad key.

**`Memcached::RES_CONNECTION_SOCKET_CREATE_FAILURE`**  
Failed to create network socket.

**`Memcached::RES_PAYLOAD_FAILURE`**  
Payload failure: could not compress/decompress or serialize/unserialize
the value.

**`Memcached::RES_AUTH_PROBLEM`**  
Available as of Memcached 3.0.0.

**`Memcached::RES_AUTH_FAILURE`**  
Available as of Memcached 3.0.0.

**`Memcached::RES_AUTH_CONTINUE`**  
Available as of Memcached 3.0.0.

**`Memcached::RES_E2BIG`**  
Available as of Memcached 3.0.0.

**`Memcached::RES_KEY_TOO_BIG`**  
Available as of Memcached 3.0.0.

**`Memcached::RES_SERVER_TEMPORARILY_DISABLED`**  
Available as of Memcached 3.0.0.

**`Memcached::RES_SERVER_MEMORY_ALLOCATION_FAILURE`**  
Available as of Memcached 3.0.0.

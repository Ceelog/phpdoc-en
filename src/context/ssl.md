SSL context options
===================

SSL context option listing

### Description

Context options for *ssl://* and *tls://* transports.

### Options

`peer_name` <span class="type">string</span>  
Peer name to be used. If this value is not set, then the name is guessed
based on the hostname used when opening the stream.

`verify_peer` <span class="type">boolean</span>  
Require verification of SSL certificate used.

Defaults to **`TRUE`**.

`verify_peer_name` <span class="type">boolean</span>  
Require verification of peer name.

Defaults to **`TRUE`**.

`allow_self_signed` <span class="type">boolean</span>  
Allow self-signed certificates. Requires
<a href="/context/ssl.html#context.ssl.verify-peer" class="link"><code class="parameter">verify_peer</code></a>.

Defaults to **`FALSE`**

`cafile` <span class="type">string</span>  
Location of Certificate Authority file on local filesystem which should
be used with the *verify\_peer* context option to authenticate the
identity of the remote peer.

`capath` <span class="type">string</span>  
If *cafile* is not specified or if the certificate is not found there,
the directory pointed to by *capath* is searched for a suitable
certificate. *capath* must be a correctly hashed certificate directory.

`local_cert` <span class="type">string</span>  
Path to local certificate file on filesystem. It must be a PEM encoded
file which contains your certificate and private key. It can optionally
contain the certificate chain of issuers. The private key also may be
contained in a separate file specified by *local\_pk*.

`local_pk` <span class="type">string</span>  
Path to local private key file on filesystem in case of separate files
for certificate (*local\_cert*) and private key.

`passphrase` <span class="type">string</span>  
Passphrase with which your *local\_cert* file was encoded.

`CN_match` <span class="type">string</span>  
Common Name we are expecting. PHP will perform limited wildcard
matching. If the Common Name does not match this, the connection attempt
will fail.

`verify_depth` <span class="type">integer</span>  
Abort if the certificate chain is too deep.

Defaults to no verification.

`ciphers` <span class="type">string</span>  
Sets the list of available ciphers. The format of the string is
described in
<a href="https://www.openssl.org/docs/manmaster/man1/ciphers.html#CIPHER-LIST-FORMAT" class="link external">» ciphers(1)</a>.

Defaults to *DEFAULT*.

`capture_peer_cert` <span class="type">boolean</span>  
If set to **`TRUE`** a *peer\_certificate* context option will be
created containing the peer certificate.

`capture_peer_cert_chain` <span class="type">boolean</span>  
If set to **`TRUE`** a *peer\_certificate\_chain* context option will be
created containing the certificate chain.

`SNI_enabled` <span class="type">boolean</span>  
If set to **`TRUE`** server name indication will be enabled. Enabling
SNI allows multiple certificates on the same IP address.

`SNI_server_name` <span class="type">string</span>  
If set, then this value will be used as server name for server name
indication. If this value is not set, then the server name is guessed
based on the hostname used when opening the stream.

> **Note**: <span class="simpara"> This option is deprecated, in favour
> of `peer_name`, as of PHP 5.6.0. </span>

`disable_compression` <span class="type">boolean</span>  
If set, disable TLS compression. This can help mitigate the CRIME attack
vector.

`peer_fingerprint` <span class="type">string</span> \| <span class="type">array</span>  
Aborts when the remote certificate digest doesn't match the specified
hash.

When a <span class="type">string</span> is used, the length will
determine which hashing algorithm is applied, either "md5" (32) or
"sha1" (40).

When an <span class="type">array</span> is used, the keys indicate the
hashing algorithm name and each corresponding value is the expected
digest.

`security_level` <span class="type">integer</span>  
Sets the security level. If not specified the library default security
level is used. The security levels are described in
<a href="https://www.openssl.org/docs/man1.1.0/man3/SSL_CTX_get_security_level.html" class="link external">» SSL_CTX_get_security_level(3)</a>.

Available as of PHP 7.2.0 and OpenSSL 1.1.0.

### Changelog

| Version | Description                                          |
|---------|------------------------------------------------------|
| 7.2.0   | Added `security_levels`. Requires OpenSSL \>= 1.1.0. |

### Notes

> **Note**: <span class="simpara"> Because *ssl://* is the underlying
> transport for the
> <a href="/wrappers/http.html" class="link"><em>https://</em></a> and
> <a href="/wrappers/ftp.html" class="link"><em>ftps://</em></a>
> wrappers, any context options which apply to *ssl://* also apply to
> *https://* and *ftps://*. </span>

> **Note**: <span class="simpara"> For SNI (Server Name Indication) to
> be available, then PHP must be compiled with OpenSSL 0.9.8j or
> greater. Use the **`OPENSSL_TLSEXT_SERVER_NAME`** to determine whether
> SNI is supported. </span>

### See Also

-   <a href="/context/socket.html" class="xref">Socket context options</a>

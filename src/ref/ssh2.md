ssh2\_auth\_agent
=================

Authenticate over SSH using the ssh agent

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_auth\_agent</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
, <span class="methodparam"><span class="type">string</span>
`$username`</span> )

Authenticate over SSH using the ssh agent

> **Note**: <span class="simpara"> The <span
> class="function">ssh2\_auth\_agent</span> function will only be
> available when the ssh2 extension is compiled with libssh \>= 1.2.3.
> </span>

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`username`  
Remote user name.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Authenticating with a ssh agent**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);

if (ssh2_auth_agent($connection, 'username')) {
  echo "Authentication Successful!\n";
} else {
  die('Authentication Failed...');
}
?>
```

ssh2\_auth\_hostbased\_file
===========================

Authenticate using a public hostkey

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_auth\_hostbased\_file</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
, <span class="methodparam"><span class="type">string</span>
`$username`</span> , <span class="methodparam"><span
class="type">string</span> `$hostname`</span> , <span
class="methodparam"><span class="type">string</span>
`$pubkeyfile`</span> , <span class="methodparam"><span
class="type">string</span> `$privkeyfile`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$passphrase`</span> \[, <span class="methodparam"><span
class="type">string</span> `$local_username`</span> \]\] )

Authenticate using a public hostkey read from a file.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`username`  

`hostname`  

`pubkeyfile`  

`privkeyfile`  

`passphrase`  
If `privkeyfile` is encrypted (which it should be), the passphrase must
be provided.

`local_username`  
If `local_username` is omitted, then the value for `username` will be
used for it.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Authentication using a public hostkey**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22, array('hostkey'=>'ssh-rsa'));

if (ssh2_auth_hostbased_file($connection, 'remoteusername', 'myhost.example.com',
                             '/usr/local/etc/hostkey_rsa.pub',
                             '/usr/local/etc/hostkey_rsa', 'secret',
                             'localusername')) {
  echo "Public Key Hostbased Authentication Successful\n";
} else {
  die('Public Key Hostbased Authentication Failed');
}
?>
```

### Notes

> **Note**:
>
> <span class="function">ssh2\_auth\_hostbased\_file</span> requires
> libssh2 \>= 0.7 and PHP/SSH2 \>= 0.7

ssh2\_auth\_none
================

Authenticate as "none"

### Description

<span class="type">mixed</span> <span
class="methodname">ssh2\_auth\_none</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
, <span class="methodparam"><span class="type">string</span>
`$username`</span> )

Attempt "none" authentication which usually will (and should) fail. As
part of the failure, this function will return an array of accepted
authentication methods.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`username`  
Remote user name.

### Return Values

Returns **`true`** if the server does accept "none" as an authentication
method, or an array of accepted authentication methods on failure.

### Examples

**Example \#1 Retrieving a list of authentication methods**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);

$auth_methods = ssh2_auth_none($connection, 'user');

if (in_array('password', $auth_methods)) {
  echo "Server supports password based authentication\n";
}
?>
```

ssh2\_auth\_password
====================

Authenticate over SSH using a plain password

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_auth\_password</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
, <span class="methodparam"><span class="type">string</span>
`$username`</span> , <span class="methodparam"><span
class="type">string</span> `$password`</span> )

Authenticate over SSH using a plain password. Since version 0.12 this
function also supports keyboard\_interactive method.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`username`  
Remote user name.

`password`  
Password for `username`

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Authenticating with a password**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);

if (ssh2_auth_password($connection, 'username', 'secret')) {
  echo "Authentication Successful!\n";
} else {
  die('Authentication Failed...');
}
?>
```

ssh2\_auth\_pubkey\_file
========================

Authenticate using a public key

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_auth\_pubkey\_file</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
, <span class="methodparam"><span class="type">string</span>
`$username`</span> , <span class="methodparam"><span
class="type">string</span> `$pubkeyfile`</span> , <span
class="methodparam"><span class="type">string</span>
`$privkeyfile`</span> \[, <span class="methodparam"><span
class="type">string</span> `$passphrase`</span> \] )

Authenticate using a public key read from a file.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`username`  

`pubkeyfile`  
The public key file needs to be in OpenSSH's format. It should look
something like:

ssh-rsa AAAAB3NzaC1yc2EAAA....NX6sqSnHA8= rsa-key-20121110

`privkeyfile`  

`passphrase`  
If `privkeyfile` is encrypted (which it should be), the `passphrase`
must be provided.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Authentication using a public key**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22, array('hostkey'=>'ssh-rsa'));

if (ssh2_auth_pubkey_file($connection, 'username',
                          '/home/username/.ssh/id_rsa.pub',
                          '/home/username/.ssh/id_rsa', 'secret')) {
  echo "Public Key Authentication Successful\n";
} else {
  die('Public Key Authentication Failed');
}
?>
```

### Notes

> **Note**:
>
> The underlying libssh library doesn't support partial auths very
> cleanly That is, if you need to supply both a public key and a
> password it will appear as if this function has failed. In this
> particular case a failure from this call may just mean that auth
> hasn't been completed yet. You would need to ignore this failure and
> continue on and call <span
> class="function">ssh2\_auth\_password</span> in order to complete
> authentication.

ssh2\_connect
=============

Connect to an SSH server

### Description

<span class="type">resource</span> <span
class="methodname">ssh2\_connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 22</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$methods`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$callbacks`</span> \]\]\] )

Establish a connection to a remote SSH server.

Once connected, the client should verify the server's hostkey using
<span class="function">ssh2\_fingerprint</span>, then authenticate using
either password or public key.

### Parameters

`host`  

`port`  

`methods`  
`methods` may be an associative array with up to four parameters as
described below.

| Index              | Meaning                                                                                                                                            | Supported Values\*                                                                                    |
|--------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------|
| kex                | List of key exchange methods to advertise, comma separated in order of preference.                                                                 | *diffie-hellman-group1-sha1*, *diffie-hellman-group14-sha1*, and *diffie-hellman-group-exchange-sha1* |
| hostkey            | List of hostkey methods to advertise, comma separated in order of preference.                                                                      | *ssh-rsa* and *ssh-dss*                                                                               |
| client\_to\_server | Associative array containing crypt, compression, and message authentication code (MAC) method preferences for messages sent from client to server. |                                                                                                       |
| server\_to\_client | Associative array containing crypt, compression, and message authentication code (MAC) method preferences for messages sent from server to client. |                                                                                                       |

\* - Supported Values are dependent on methods supported by underlying
library. See
<a href="http://libssh2.org/" class="link external">» libssh2</a>
documentation for additional information.

| Index | Meaning                                                                           | Supported Values\*                                                                                                                            |
|-------|-----------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| crypt | List of crypto methods to advertise, comma separated in order of preference.      | *rijndael-cbc@lysator.liu.se*, *aes256-cbc*, *aes192-cbc*, *aes128-cbc*, *3des-cbc*, *blowfish-cbc*, *cast128-cbc*, *arcfour*, and *none\*\** |
| comp  | List of compression methods to advertise, comma separated in order of preference. | *zlib* and *none*                                                                                                                             |
| mac   | List of MAC methods to advertise, comma separated in order of preference.         | *hmac-sha1*, *hmac-sha1-96*, *hmac-ripemd160*, *hmac-ripemd160@openssh.com*, and *none\*\**                                                   |

> **Note**: **Crypt and MAC method "*none*"**  
>
> For security reasons, *none* is disabled by the underlying
> <a href="http://libssh2.org/" class="link external">» libssh2</a>
> library unless explicitly enabled during build time by using the
> appropriate ./configure options. See documentation for the underlying
> library for more information.

`callbacks`  
`callbacks` may be an associative array with any or all of the following
parameters.

| Index      | Meaning                                                                                                                                                                                                       | Prototype                                             |
|------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------|
| ignore     | Name of function to call when an **`SSH2_MSG_IGNORE`** packet is received                                                                                                                                     | void ignore\_cb($message)                             |
| debug      | Name of function to call when an **`SSH2_MSG_DEBUG`** packet is received                                                                                                                                      | void debug\_cb($message, $language, $always\_display) |
| macerror   | Name of function to call when a packet is received but the message authentication code failed. If the callback returns **`true`**, the mismatch will be ignored, otherwise the connection will be terminated. | bool macerror\_cb($packet)                            |
| disconnect | Name of function to call when an **`SSH2_MSG_DISCONNECT`** packet is received                                                                                                                                 | void disconnect\_cb($reason, $message, $language)     |

### Return Values

Returns a resource on success, or **`false`** on error.

### Examples

**Example \#1 <span class="function">ssh2\_connect</span> example**

Open a connection forcing 3des-cbc when sending packets, any strength
aes cipher when receiving packets, no compression in either direction,
and Group1 key exchange.

``` php
<?php
/* Notify the user if the server terminates the connection */
function my_ssh_disconnect($reason, $message, $language) {
  printf("Server disconnected with reason code [%d] and message: %s\n",
         $reason, $message);
}

$methods = array(
  'kex' => 'diffie-hellman-group1-sha1',
  'client_to_server' => array(
    'crypt' => '3des-cbc',
    'comp' => 'none'),
  'server_to_client' => array(
    'crypt' => 'aes256-cbc,aes192-cbc,aes128-cbc',
    'comp' => 'none'));

$callbacks = array('disconnect' => 'my_ssh_disconnect');

$connection = ssh2_connect('shell.example.com', 22, $methods, $callbacks);
if (!$connection) die('Connection failed');
?>
```

### See Also

-   <span class="function">ssh2\_fingerprint</span>
-   <span class="function">ssh2\_auth\_none</span>
-   <span class="function">ssh2\_auth\_password</span>
-   <span class="function">ssh2\_auth\_pubkey\_file</span>
-   <span class="function">ssh2\_disconnect</span>

ssh2\_disconnect
================

Close a connection to a remote SSH server

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_disconnect</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
)

Close a connection to a remote SSH server.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">ssh2\_connect</span>

ssh2\_exec
==========

Execute a command on a remote server

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">ssh2\_exec</span> ( <span class="methodparam"><span
class="type">resource</span> `$session`</span> , <span
class="methodparam"><span class="type">string</span> `$command`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$pty`</span> \[, <span class="methodparam"><span
class="type">array</span> `$env`</span> \[, <span
class="methodparam"><span class="type">int</span> `$width`<span
class="initializer"> = 80</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$height`<span
class="initializer"> = 25</span></span> \[, <span
class="methodparam"><span class="type">int</span>
`$width_height_type`<span class="initializer"> =
SSH2\_TERM\_UNIT\_CHARS</span></span> \]\]\]\]\] )

Execute a command at the remote end and allocate a channel for it.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`command`  

`pty`  

`env`  
`env` may be passed as an associative array of name/value pairs to set
in the target environment.

`width`  
Width of the virtual terminal.

`height`  
Height of the virtual terminal.

`width_height_type`  
`width_height_type` should be one of **`SSH2_TERM_UNIT_CHARS`** or
**`SSH2_TERM_UNIT_PIXELS`**.

### Return Values

Returns a stream on success or **`false`** on failure.

### Examples

**Example \#1 Executing a command**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');

$stream = ssh2_exec($connection, '/usr/local/bin/php -i');
?>
```

### See Also

-   <span class="function">ssh2\_connect</span>
-   <span class="function">ssh2\_shell</span>
-   <span class="function">ssh2\_tunnel</span>

ssh2\_fetch\_stream
===================

Fetch an extended data stream

### Description

<span class="type">resource</span> <span
class="methodname">ssh2\_fetch\_stream</span> ( <span
class="methodparam"><span class="type">resource</span> `$channel`</span>
, <span class="methodparam"><span class="type">int</span>
`$streamid`</span> )

Fetches an alternate substream associated with an SSH2 channel stream.
The SSH2 protocol currently defines only one substream, STDERR, which
has a substream ID of **`SSH2_STREAM_STDERR`** (defined as 1).

### Parameters

`channel`  

`streamid`  
An SSH2 channel stream.

### Return Values

Returns the requested stream resource.

### Examples

**Example \#1 Opening a shell and retrieving the stderr stream
associated with it**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');

$stdio_stream = ssh2_shell($connection);
$stderr_stream = ssh2_fetch_stream($stdio_stream, SSH2_STREAM_STDERR);
?>
```

### See Also

-   <span class="function">ssh2\_shell</span>
-   <span class="function">ssh2\_exec</span>
-   <span class="function">ssh2\_connect</span>

ssh2\_fingerprint
=================

Retrieve fingerprint of remote server

### Description

<span class="type">string</span> <span
class="methodname">ssh2\_fingerprint</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = SSH2\_FINGERPRINT\_MD5 \|
SSH2\_FINGERPRINT\_HEX</span></span> \] )

Returns a server hostkey hash from an active session.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`flags`  
`flags` may be either of **`SSH2_FINGERPRINT_MD5`** or
**`SSH2_FINGERPRINT_SHA1`** logically ORed with
**`SSH2_FINGERPRINT_HEX`** or **`SSH2_FINGERPRINT_RAW`**.

### Return Values

Returns the hostkey hash as a string.

### Examples

**Example \#1 Checking the fingerprint against a known value**

``` php
<?php
$known_host = '6F89C2F0A719B30CC38ABDF90755F2E4';

$connection = ssh2_connect('shell.example.com', 22);

$fingerprint = ssh2_fingerprint($connection,
               SSH2_FINGERPRINT_MD5 | SSH2_FINGERPRINT_HEX);

if ($fingerprint != $known_host) {
  die("HOSTKEY MISMATCH!\n" .
      "Possible Man-In-The-Middle Attack?");
}
?>
```

ssh2\_methods\_negotiated
=========================

Return list of negotiated methods

### Description

<span class="type">array</span> <span
class="methodname">ssh2\_methods\_negotiated</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
)

Returns list of negotiated methods.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

### Return Values

### Examples

**Example \#1 Determining what methods were negotiated**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
$methods = ssh2_methods_negotiated($connection);

echo "Encryption keys were negotiated using: {$methods['kex']}\n";
echo "Server identified using an {$methods['hostkey']} with ";
echo "fingerprint: " . ssh2_fingerprint($connection) . "\n";

echo "Client to Server packets will use methods:\n";
echo "\tCrypt: {$methods['client_to_server']['crypt']}\n";
echo "\tComp: {$methods['client_to_server']['comp']}\n";
echo "\tMAC: {$methods['client_to_server']['mac']}\n";

echo "Server to Client packets will use methods:\n";
echo "\tCrypt: {$methods['server_to_client']['crypt']}\n";
echo "\tComp: {$methods['server_to_client']['comp']}\n";
echo "\tMAC: {$methods['server_to_client']['mac']}\n";

?>
```

### See Also

-   <span class="function">ssh2\_connect</span>

ssh2\_publickey\_add
====================

Add an authorized publickey

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_publickey\_add</span> ( <span
class="methodparam"><span class="type">resource</span> `$pkey`</span> ,
<span class="methodparam"><span class="type">string</span>
`$algoname`</span> , <span class="methodparam"><span
class="type">string</span> `$blob`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$overwrite`<span
class="initializer"> = **`false`**</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$attributes`</span>
\]\] )

> **Note**: <span class="simpara">The public key subsystem is used for
> managing public keys on a server to which the client is *already*
> authenticated. To authenticate to a remote system using public key
> authentication, use the <span
> class="function">ssh2\_auth\_pubkey\_file</span> function
> instead.</span>

### Parameters

`pkey`  
Publickey Subsystem resource created by <span
class="function">ssh2\_publickey\_init</span>.

`algoname`  
Publickey algorithm (e.g.): ssh-dss, ssh-rsa

`blob`  
Publickey blob as raw binary data

`overwrite`  
If the specified key already exists, should it be overwritten?

`attributes`  
Associative array of attributes to assign to this public key. Refer to
ietf-secsh-publickey-subsystem for a list of supported attributes. To
mark an attribute as mandatory, precede its name with an asterisk. If
the server is unable to support an attribute marked mandatory, it will
abort the add process.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Adding a publickey with <span
class="function">ssh2\_publickey\_add</span>**

``` php
<?php
$ssh2 = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($ssh2, 'jdoe', 'password');
$pkey = ssh2_publickey_init($ssh2);

$keyblob = base64_decode('
AAAAB3NzaC1yc2EAAAABIwAAAIEA5HVt6VqSGd5PTrLRdjNONxXH1tVFGn0
Bd26BF0aCP9qyJRlvdJ3j4WBeX4ZmrveGrjMgkseSYc4xZ26sDHwfL351xj
zaLpipu\BGRrw17mWVBhuCExo476ri5tQFzbTc54VEHYckxQ16CjSTibI5X
69GmnYC9PNqEYq/1TP+HF10=');

ssh2_publickey_add($pkey, 'ssh-rsa', $keyblob, false, array('comment'=>"John's Key"));
?>
```

### See Also

-   <span class="function">ssh2\_publickey\_init</span>
-   <span class="function">ssh2\_publickey\_remove</span>
-   <span class="function">ssh2\_publickey\_list</span>

ssh2\_publickey\_init
=====================

Initialize Publickey subsystem

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">ssh2\_publickey\_init</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
)

Request the Publickey subsystem from an already connected SSH2 server.

The publickey subsystem allows an already connected and authenticated
client to manage the list of authorized public keys stored on the target
server in an implementation agnostic manner. If the remote server does
not support the publickey subsystem, the <span
class="function">ssh2\_publickey\_init</span> function will return
**`false`**.

### Parameters

`session`  

### Return Values

Returns an *SSH2 Publickey Subsystem* resource for use with all other
ssh2\_publickey\_\*() methods or **`false`** on failure.

### Notes

> **Note**: <span class="simpara">The public key subsystem is used for
> managing public keys on a server to which the client is *already*
> authenticated. To authenticate to a remote system using public key
> authentication, use the <span
> class="function">ssh2\_auth\_pubkey\_file</span> function
> instead.</span>

### See Also

-   <span class="function">ssh2\_publickey\_add</span>
-   <span class="function">ssh2\_publickey\_remove</span>
-   <span class="function">ssh2\_publickey\_list</span>

ssh2\_publickey\_list
=====================

List currently authorized publickeys

### Description

<span class="type">array</span> <span
class="methodname">ssh2\_publickey\_list</span> ( <span
class="methodparam"><span class="type">resource</span> `$pkey`</span> )

List currently authorized publickeys.

### Parameters

`pkey`  
Publickey Subsystem resource

### Return Values

Returns a numerically indexed array of keys, each of which is an
associative array containing: name, blob, and attrs elements.

| Array Key | Meaning                                                                                                                                                                      |
|-----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| name      | Name of algorithm used by this publickey, for example: *ssh-dss* or *ssh-rsa*.                                                                                               |
| blob      | Publickey blob as raw binary data.                                                                                                                                           |
| attrs     | Attributes assigned to this publickey. The most common attribute, and the only one supported by publickey version 1 servers, is *comment*, which may be any freeform string. |

### Examples

**Example \#1 Listing authorized keys with <span
class="function">ssh2\_publickey\_list</span>**

``` php
<?php
$ssh2 = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($ssh2, 'jdoe', 'secret');
$pkey = ssh2_publickey_init($ssh2);

$list = ssh2_publickey_list($pkey);

foreach($list as $key) {
  echo "Key: {$key['name']}\n";
  echo "Blob: " . chunk_split(base64_encode($key['blob']), 40, "\n") . "\n";
  echo "Comment: {$key['attrs']['comment']}\n\n";
}
?>
```

The above example will output:

    Key: ssh-rsa
    Blob: AAAAB3NzaC1yc2EAAAABIwAAAIEA5HVt6VqSGd5P
    TrLRdjNONxXH1tVFGn0Bd26BF0aCP9qyJRlvdJ3j
    4WBeX4ZmrveGrjMgkseSYc4xZ26sDHwfL351xjza
    Lpipu\BGRrw17mWVBhuCExo476ri5tQFzbTc54VE
    HYckxQ16CjSTibI5X69GmnYC9PNqEYq/1TP+HF10
    Comment: John's Key

    Key: ssh-rsa
    Blob: AAAAB3NzaHVt6VqSGd5C1yc2EAAAABIwA232dnJA
    AIEA5HVt6VqSGd5PTrLRdjNONxX/1TP+HF1HVt6V
    qSGd50H1tVFGn0BB3NzaC1yc2EAd26BF0aCP9qyJ
    RlvdJ3j4WBeX4ZmrveGrjMgkseSYc4xZ26HVt6Vq
    SGd5sDHwfL351xjzaLpipu\BGB3NzaC1yc2EA/1T
    Comment: Alice's Key

### Notes

> **Note**: <span class="simpara">The public key subsystem is used for
> managing public keys on a server to which the client is *already*
> authenticated. To authenticate to a remote system using public key
> authentication, use the <span
> class="function">ssh2\_auth\_pubkey\_file</span> function
> instead.</span>

### See Also

-   <span class="function">ssh2\_publickey\_init</span>
-   <span class="function">ssh2\_publickey\_add</span>
-   <span class="function">ssh2\_publickey\_remove</span>

ssh2\_publickey\_remove
=======================

Remove an authorized publickey

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_publickey\_remove</span> ( <span
class="methodparam"><span class="type">resource</span> `$pkey`</span> ,
<span class="methodparam"><span class="type">string</span>
`$algoname`</span> , <span class="methodparam"><span
class="type">string</span> `$blob`</span> )

Removes an authorized publickey.

### Parameters

`pkey`  
Publickey Subsystem Resource

`algoname`  
Publickey algorithm (e.g.): ssh-dss, ssh-rsa

`blob`  
Publickey blob as raw binary data

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Notes

> **Note**: <span class="simpara">The public key subsystem is used for
> managing public keys on a server to which the client is *already*
> authenticated. To authenticate to a remote system using public key
> authentication, use the <span
> class="function">ssh2\_auth\_pubkey\_file</span> function
> instead.</span>

### See Also

-   <span class="function">ssh2\_publickey\_init</span>
-   <span class="function">ssh2\_publickey\_add</span>
-   <span class="function">ssh2\_publickey\_list</span>

ssh2\_scp\_recv
===============

Request a file via SCP

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_scp\_recv</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
, <span class="methodparam"><span class="type">string</span>
`$remote_file`</span> , <span class="methodparam"><span
class="type">string</span> `$local_file`</span> )

Copy a file from the remote server to the local filesystem using the SCP
protocol.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`remote_file`  
Path to the remote file.

`local_file`  
Path to the local file.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Downloading a file via SCP**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');

ssh2_scp_recv($connection, '/remote/filename', '/local/filename');
?>
```

### See Also

-   <span class="function">ssh2\_scp\_send</span>
-   <span class="function">copy</span>

ssh2\_scp\_send
===============

Send a file via SCP

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_scp\_send</span> ( <span
class="methodparam"><span class="type">resource</span> `$session`</span>
, <span class="methodparam"><span class="type">string</span>
`$local_file`</span> , <span class="methodparam"><span
class="type">string</span> `$remote_file`</span> \[, <span
class="methodparam"><span class="type">int</span> `$create_mode`<span
class="initializer"> = 0644</span></span> \] )

Copy a file from the local filesystem to the remote server using the SCP
protocol.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`local_file`  
Path to the local file.

`remote_file`  
Path to the remote file.

`create_mode`  
The file will be created with the mode specified by `create_mode`.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Uploading a file via SCP**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');

ssh2_scp_send($connection, '/local/filename', '/remote/filename', 0644);
?>
```

### See Also

-   <span class="function">ssh2\_scp\_recv</span>
-   <span class="function">copy</span>

ssh2\_sftp\_chmod
=================

Changes file mode

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_sftp\_chmod</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">int</span> `$mode`</span> )

Attempts to change the mode of the specified file to that given in
`mode`.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`filename`  
Path to the file.

`mode`  
Permissions on the file. See the <span class="function">chmod</span> for
more details on this parameter.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Changing the mode of a file on a remote server**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');
$sftp = ssh2_sftp($connection);

ssh2_sftp_chmod($sftp, '/somedir/somefile', 0755);
?>
```

### See Also

-   <span class="function">chmod</span>
-   <span class="function">ssh2\_sftp</span>
-   <span class="function">ssh2\_connect</span>

ssh2\_sftp\_lstat
=================

Stat a symbolic link

### Description

<span class="type">array</span> <span
class="methodname">ssh2\_sftp\_lstat</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$path`</span> )

Stats a symbolic link on the remote filesystem *without* following the
link.

This function is similar to using the <span
class="function">lstat</span> function with the
<a href="/wrappers/ssh2.html" class="link">ssh2.sftp://</a> wrapper in
PHP 5 and returns the same values.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`path`  
Path to the remote symbolic link.

### Return Values

See the documentation for <span class="function">stat</span> for details
on the values which may be returned.

### Examples

**Example \#1 Stating a symbolic link via SFTP**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');

$sftp = ssh2_sftp($connection);
$statinfo = ssh2_sftp_lstat($sftp, '/path/to/symlink');

$filesize = $statinfo['size'];
$group = $statinfo['gid'];
$owner = $statinfo['uid'];
$atime = $statinfo['atime'];
$mtime = $statinfo['mtime'];
$mode = $statinfo['mode'];
?>
```

### See Also

-   <span class="function">ssh2\_sftp\_stat</span>
-   <span class="function">lstat</span>
-   <span class="function">stat</span>

ssh2\_sftp\_mkdir
=================

Create a directory

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_sftp\_mkdir</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$dirname`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
0777</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$recursive`<span class="initializer"> =
**`false`**</span></span> \]\] )

Creates a directory on the remote file server with permissions set to
`mode`.

This function is similar to using <span class="function">mkdir</span>
with the <a href="/wrappers/ssh2.html" class="link">ssh2.sftp://</a>
wrapper.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`dirname`  
Path of the new directory.

`mode`  
Permissions on the new directory.

`recursive`  
If `recursive` is **`true`** any parent directories required for
`dirname` will be automatically created as well.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Creating a directory on a remote server**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');
$sftp = ssh2_sftp($connection);

ssh2_sftp_mkdir($sftp, '/home/username/newdir');
/* Or:  mkdir("ssh2.sftp://$sftp/home/username/newdir"); */
?>
```

### See Also

-   <span class="function">mkdir</span>
-   <span class="function">ssh2\_sftp\_rmdir</span>

ssh2\_sftp\_readlink
====================

Return the target of a symbolic link

### Description

<span class="type">string</span> <span
class="methodname">ssh2\_sftp\_readlink</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$link`</span> )

Returns the target of a symbolic link.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`link`  
Path of the symbolic link.

### Return Values

Returns the target of the symbolic `link`.

### Examples

**Example \#1 Reading a symbolic link**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');
$sftp = ssh2_sftp($connection);

$target = ssh2_sftp_readlink($sftp, '/tmp/mysql.sock');
/* $target is now (e.g.): '/var/run/mysql.sock' */
?>
```

### See Also

-   <span class="function">readlink</span>
-   <span class="function">ssh2\_sftp\_symlink</span>

ssh2\_sftp\_realpath
====================

Resolve the realpath of a provided path string

### Description

<span class="type">string</span> <span
class="methodname">ssh2\_sftp\_realpath</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Translates `filename` into the effective real path on the remote
filesystem.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`filename`  

### Return Values

Returns the real path as a string.

### Examples

**Example \#1 Resolving a pathname**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');
$sftp = ssh2_sftp($connection);

$realpath = ssh2_sftp_realpath($sftp, '/home/username/../../../..//./usr/../etc/passwd');
/* $realpath is now: '/etc/passwd' */
?>
```

### See Also

-   <span class="function">realpath</span>
-   <span class="function">ssh2\_sftp\_symlink</span>
-   <span class="function">ssh2\_sftp\_readlink</span>

ssh2\_sftp\_rename
==================

Rename a remote file

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_sftp\_rename</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$from`</span> , <span class="methodparam"><span
class="type">string</span> `$to`</span> )

Renames a file on the remote filesystem.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`from`  
The current file that is being renamed.

`to`  
The new file name that replaces `from`.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Renaming a file via sftp**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');
$sftp = ssh2_sftp($connection);

ssh2_sftp_rename($sftp, '/home/username/oldname', '/home/username/newname');
?>
```

### See Also

-   <span class="function">rename</span>

ssh2\_sftp\_rmdir
=================

Remove a directory

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_sftp\_rmdir</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$dirname`</span> )

Removes a directory from the remote file server.

This function is similar to using <span class="function">rmdir</span>
with the <a href="/wrappers/ssh2.html" class="link">ssh2.sftp://</a>
wrapper.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`dirname`  

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Removing a directory on a remote server**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');
$sftp = ssh2_sftp($connection);

ssh2_sftp_rmdir($sftp, '/home/username/deltodel');
/* Or:  rmdir("ssh2.sftp://$sftp/home/username/dirtodel"); */
?>
```

### See Also

-   <span class="function">rmdir</span>
-   <span class="function">ssh2\_sftp\_mkdir</span>

ssh2\_sftp\_stat
================

Stat a file on a remote filesystem

### Description

<span class="type">array</span> <span
class="methodname">ssh2\_sftp\_stat</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$path`</span> )

Stats a file on the remote filesystem following any symbolic links.

This function is similar to using the <span class="function">stat</span>
function with the
<a href="/wrappers/ssh2.html" class="link">ssh2.sftp://</a> wrapper in
PHP 5 and returns the same values.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`path`  

### Return Values

See the documentation for <span class="function">stat</span> for details
on the values which may be returned.

### Examples

**Example \#1 Stating a file via SFTP**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');

$sftp = ssh2_sftp($connection);
$statinfo = ssh2_sftp_stat($sftp, '/path/to/file');

$filesize = $statinfo['size'];
$group = $statinfo['gid'];
$owner = $statinfo['uid'];
$atime = $statinfo['atime'];
$mtime = $statinfo['mtime'];
$mode = $statinfo['mode'];
?>
```

### See Also

-   <span class="function">ssh2\_sftp\_lstat</span>
-   <span class="function">lstat</span>
-   <span class="function">stat</span>

ssh2\_sftp\_symlink
===================

Create a symlink

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_sftp\_symlink</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$target`</span> , <span class="methodparam"><span
class="type">string</span> `$link`</span> )

Creates a symbolic link named `link` on the remote filesystem pointing
to `target`.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`target`  
Target of the symbolic link.

`link`  

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Creating a symbolic link**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');
$sftp = ssh2_sftp($connection);

ssh2_sftp_symlink($sftp, '/var/run/mysql.sock', '/tmp/mysql.sock');
?>
```

### See Also

-   <span class="function">ssh2\_sftp\_readlink</span>
-   <span class="function">symlink</span>

ssh2\_sftp\_unlink
==================

Delete a file

### Description

<span class="type">bool</span> <span
class="methodname">ssh2\_sftp\_unlink</span> ( <span
class="methodparam"><span class="type">resource</span> `$sftp`</span> ,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

Deletes a file on the remote filesystem.

### Parameters

`sftp`  
An SSH2 SFTP resource opened by <span
class="function">ssh2\_sftp</span>.

`filename`  

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Deleting a file**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');
$sftp = ssh2_sftp($connection);

ssh2_sftp_unlink($sftp, '/home/username/stale_file');
?>
```

### See Also

-   <span class="function">unlink</span>

ssh2\_sftp
==========

Initialize SFTP subsystem

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">ssh2\_sftp</span> ( <span class="methodparam"><span
class="type">resource</span> `$session`</span> )

Request the SFTP subsystem from an already connected SSH2 server.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

### Return Values

This method returns an *SSH2 SFTP* resource for use with all other
ssh2\_sftp\_\*() methods and the
<a href="/wrappers/ssh2.html" class="link">ssh2.sftp://</a> fopen
wrapper, or **`false`** on failure.

### Examples

**Example \#1 Opening a file via SFTP**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');

$sftp = ssh2_sftp($connection);

$stream = fopen('ssh2.sftp://' . intval($sftp) . '/path/to/file', 'r');
?>
```

### See Also

-   <span class="function">ssh2\_scp\_recv</span>
-   <span class="function">ssh2\_scp\_send</span>

ssh2\_shell
===========

Request an interactive shell

### Description

<span class="type">resource</span> <span
class="methodname">ssh2\_shell</span> ( <span class="methodparam"><span
class="type">resource</span> `$session`</span> \[, <span
class="methodparam"><span class="type">string</span> `$term_type`<span
class="initializer"> = "vanilla"</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$env`</span> \[,
<span class="methodparam"><span class="type">int</span> `$width`<span
class="initializer"> = 80</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$height`<span
class="initializer"> = 25</span></span> \[, <span
class="methodparam"><span class="type">int</span>
`$width_height_type`<span class="initializer"> =
SSH2\_TERM\_UNIT\_CHARS</span></span> \]\]\]\]\] )

Open a shell at the remote end and allocate a stream for it.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`term_type`  
`term_type` should correspond to one of the entries in the target
system's */etc/termcap* file.

`env`  
`env` may be passed as an associative array of name/value pairs to set
in the target environment.

`width`  
Width of the virtual terminal.

`height`  
Height of the virtual terminal.

`width_height_type`  
`width_height_type` should be one of **`SSH2_TERM_UNIT_CHARS`** or
**`SSH2_TERM_UNIT_PIXELS`**.

### Return Values

### Examples

**Example \#1 Requesting an interactive shell**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_password($connection, 'username', 'password');

$stream = ssh2_shell($connection, 'vt102', null, 80, 24, SSH2_TERM_UNIT_CHARS);
?>
```

### See Also

-   <span class="function">ssh2\_exec</span>
-   <span class="function">ssh2\_tunnel</span>
-   <span class="function">ssh2\_fetch\_stream</span>

ssh2\_tunnel
============

Open a tunnel through a remote server

### Description

<span class="type">resource</span> <span
class="methodname">ssh2\_tunnel</span> ( <span class="methodparam"><span
class="type">resource</span> `$session`</span> , <span
class="methodparam"><span class="type">string</span> `$host`</span> ,
<span class="methodparam"><span class="type">int</span> `$port`</span> )

Open a socket stream to an arbitrary host/port by way of the currently
connected SSH server.

### Parameters

`session`  
An SSH connection link identifier, obtained from a call to <span
class="function">ssh2\_connect</span>.

`host`  

`port`  

### Return Values

### Examples

**Example \#1 Opening a tunnel to an arbitrary host**

``` php
<?php
$connection = ssh2_connect('shell.example.com', 22);
ssh2_auth_pubkey_file($connection, 'username', 'id_dsa.pub', 'id_dsa');

$tunnel = ssh2_tunnel($connection, '10.0.0.101', 12345);
?>
```

### See Also

-   <span class="function">ssh2\_connect</span>
-   <span class="function">fsockopen</span>

**Table of Contents**

-   [ssh2\_auth\_agent](/ref/ssh2.html#ssh2_auth_agent) — Authenticate
    over SSH using the ssh agent
-   [ssh2\_auth\_hostbased\_file](/ref/ssh2.html#ssh2_auth_hostbased_file)
    — Authenticate using a public hostkey
-   [ssh2\_auth\_none](/ref/ssh2.html#ssh2_auth_none) — Authenticate as
    "none"
-   [ssh2\_auth\_password](/ref/ssh2.html#ssh2_auth_password) —
    Authenticate over SSH using a plain password
-   [ssh2\_auth\_pubkey\_file](/ref/ssh2.html#ssh2_auth_pubkey_file) —
    Authenticate using a public key
-   [ssh2\_connect](/ref/ssh2.html#ssh2_connect) — Connect to an SSH
    server
-   [ssh2\_disconnect](/ref/ssh2.html#ssh2_disconnect) — Close a
    connection to a remote SSH server
-   [ssh2\_exec](/ref/ssh2.html#ssh2_exec) — Execute a command on a
    remote server
-   [ssh2\_fetch\_stream](/ref/ssh2.html#ssh2_fetch_stream) — Fetch an
    extended data stream
-   [ssh2\_fingerprint](/ref/ssh2.html#ssh2_fingerprint) — Retrieve
    fingerprint of remote server
-   [ssh2\_methods\_negotiated](/ref/ssh2.html#ssh2_methods_negotiated)
    — Return list of negotiated methods
-   [ssh2\_publickey\_add](/ref/ssh2.html#ssh2_publickey_add) — Add an
    authorized publickey
-   [ssh2\_publickey\_init](/ref/ssh2.html#ssh2_publickey_init) —
    Initialize Publickey subsystem
-   [ssh2\_publickey\_list](/ref/ssh2.html#ssh2_publickey_list) — List
    currently authorized publickeys
-   [ssh2\_publickey\_remove](/ref/ssh2.html#ssh2_publickey_remove) —
    Remove an authorized publickey
-   [ssh2\_scp\_recv](/ref/ssh2.html#ssh2_scp_recv) — Request a file via
    SCP
-   [ssh2\_scp\_send](/ref/ssh2.html#ssh2_scp_send) — Send a file via
    SCP
-   [ssh2\_sftp\_chmod](/ref/ssh2.html#ssh2_sftp_chmod) — Changes file
    mode
-   [ssh2\_sftp\_lstat](/ref/ssh2.html#ssh2_sftp_lstat) — Stat a
    symbolic link
-   [ssh2\_sftp\_mkdir](/ref/ssh2.html#ssh2_sftp_mkdir) — Create a
    directory
-   [ssh2\_sftp\_readlink](/ref/ssh2.html#ssh2_sftp_readlink) — Return
    the target of a symbolic link
-   [ssh2\_sftp\_realpath](/ref/ssh2.html#ssh2_sftp_realpath) — Resolve
    the realpath of a provided path string
-   [ssh2\_sftp\_rename](/ref/ssh2.html#ssh2_sftp_rename) — Rename a
    remote file
-   [ssh2\_sftp\_rmdir](/ref/ssh2.html#ssh2_sftp_rmdir) — Remove a
    directory
-   [ssh2\_sftp\_stat](/ref/ssh2.html#ssh2_sftp_stat) — Stat a file on a
    remote filesystem
-   [ssh2\_sftp\_symlink](/ref/ssh2.html#ssh2_sftp_symlink) — Create a
    symlink
-   [ssh2\_sftp\_unlink](/ref/ssh2.html#ssh2_sftp_unlink) — Delete a
    file
-   [ssh2\_sftp](/ref/ssh2.html#ssh2_sftp) — Initialize SFTP subsystem
-   [ssh2\_shell](/ref/ssh2.html#ssh2_shell) — Request an interactive
    shell
-   [ssh2\_tunnel](/ref/ssh2.html#ssh2_tunnel) — Open a tunnel through a
    remote server

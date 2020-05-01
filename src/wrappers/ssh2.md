ssh2://
=======

Secure Shell 2

### Description

`ssh2.shell://` `ssh2.exec://` `ssh2.tunnel://` `ssh2.sftp://`
`ssh2.scp://` (PECL)

> **Note**: **This wrapper is not enabled by default**  
> <span class="simpara"> In order to use the `ssh2.*://` wrappers you
> must install the
> <a href="https://pecl.php.net/package/ssh2" class="link external">» SSH2</a>
> extension available from
> <a href="https://pecl.php.net/" class="link external">» PECL</a>.
> </span>

In addition to accepting traditional URI login details, the ssh2
wrappers will also reuse open connections by passing the connection
resource in the host portion of the URL.

### Usage

-   <span
    class="simpara">`ssh2.shell://user:pass@example.com:22/xterm`</span>
-   <span
    class="simpara">`ssh2.exec://user:pass@example.com:22/usr/local/bin/somecmd`</span>
-   <span
    class="simpara">`ssh2.tunnel://user:pass@example.com:22/192.168.0.1:14`</span>
-   <span
    class="simpara">`ssh2.sftp://user:pass@example.com:22/path/to/filename`</span>

### Options

| Attribute                                                                        | ssh2.shell | ssh2.exec | ssh2.tunnel | ssh2.sftp                      | ssh2.scp |
|----------------------------------------------------------------------------------|------------|-----------|-------------|--------------------------------|----------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a> | Yes        | Yes       | Yes         | Yes                            | Yes      |
| Allows Reading                                                                   | Yes        | Yes       | Yes         | Yes                            | Yes      |
| Allows Writing                                                                   | Yes        | Yes       | Yes         | Yes                            | No       |
| Allows Appending                                                                 | No         | No        | No          | Yes (When supported by server) | No       |
| Allows Simultaneous Reading and Writing                                          | Yes        | Yes       | Yes         | Yes                            | No       |
| Supports <span class="function">stat</span>                                      | No         | No        | No          | Yes                            | No       |
| Supports <span class="function">unlink</span>                                    | No         | No        | No          | Yes                            | No       |
| Supports <span class="function">rename</span>                                    | No         | No        | No          | Yes                            | No       |
| Supports <span class="function">mkdir</span>                                     | No         | No        | No          | Yes                            | No       |
| Supports <span class="function">rmdir</span>                                     | No         | No        | No          | Yes                            | No       |

| Name            | Usage                                                              | Default                    |
|-----------------|--------------------------------------------------------------------|----------------------------|
| *session*       | Preconnected ssh2 resource to be reused                            |                            |
| *sftp*          | Preallocated sftp resource to be reused                            |                            |
| *methods*       | Key exchange, hostkey, cipher, compression, and MAC methods to use |                            |
| *callbacks*     |                                                                    |                            |
| *username*      | Username to connect as                                             |                            |
| *password*      | Password to use with password authentication                       |                            |
| *pubkey\_file*  | Name of public key file to use for authentication                  |                            |
| *privkey\_file* | Name of private key file to use for authentication                 |                            |
| *env*           | Associate array of environment variables to set                    |                            |
| *term*          | Terminal emulation type to request when allocating a pty           |                            |
| *term\_width*   | Width of terminal requested when allocating a pty                  |                            |
| *term\_height*  | Height of terminal requested when allocating a pty                 |                            |
| *term\_units*   | Units to use with term\_width and term\_height                     | **`SSH2_TERM_UNIT_CHARS`** |

### Examples

**Example \#1 Opening a stream from an active connection**

``` php
<?php
$session = ssh2_connect('example.com', 22);
ssh2_auth_pubkey_file($session, 'username', '/home/username/.ssh/id_rsa.pub',
                                            '/home/username/.ssh/id_rsa', 'secret');
$stream = fopen("ssh2.tunnel://$session/remote.example.com:1234", 'r');
?>
```

**Example \#2 This `$session` variable must be kept available!**

In order to use the `ssh2.*://$session` wrappers you must keep the
`$session` resource variable. The code below will not have the desired
effect:

``` php
<?php
$session = ssh2_connect('example.com', 22);
ssh2_auth_pubkey_file($session, 'username', '/home/username/.ssh/id_rsa.pub',
                                            '/home/username/.ssh/id_rsa', 'secret');
$connection_string = "ssh2.sftp://$session/";
unset($session);
$stream = fopen($connection_string . "path/to/file", 'r');
?>
```

unset() closes the session, because `$connection_string` does not hold a
reference to the `$session` variable, just a string cast derived from
it. This also happens when the <span class="function">unset</span> is
implicit because of leaving scope (like in a function).

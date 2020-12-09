ftp\_alloc
==========

Allocates space for a file to be uploaded

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_alloc</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">int</span> `$filesize`</span> \[,
<span class="methodparam"><span class="type">string</span>
`&$result`</span> \] )

Sends an *ALLO* command to the remote FTP server to allocate space for a
file to be uploaded.

> **Note**:
>
> Many FTP servers do not support this command. These servers may return
> a failure code (**`false`**) indicating the command is not supported
> or a success code (**`true`**) to indicate that pre-allocation is not
> necessary and the client should continue as though the operation were
> successful. Because of this, it may be best to reserve this function
> for servers which explicitly require preallocation.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`filesize`  
The number of bytes to allocate.

`result`  
A textual representation of the servers response will be returned by
reference in `result` if a variable is provided.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ftp\_alloc</span> example**

``` php
<?php

$file = "/home/user/myfile";

// connect to the server
$conn_id = ftp_connect('ftp.example.com');
$login_result = ftp_login($conn_id, 'anonymous', 'user@example.com');

if (ftp_alloc($conn_id, filesize($file), $result)) {
  echo "Space successfully allocated on server.  Sending $file.\n";
  ftp_put($conn_id, '/incoming/myfile', $file, FTP_BINARY);
} else {
  echo "Unable to allocate space on server.  Server said: $result\n";
}

ftp_close($conn_id);

?>
```

### See Also

-   <span class="function">ftp\_put</span>
-   <span class="function">ftp\_fput</span>

ftp\_append
===========

Append the contents of a file to another file on the FTP server

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_append</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp`</span> , <span
class="methodparam"><span class="type">string</span>
`$remote_file`</span> , <span class="methodparam"><span
class="type">string</span> `$local_file`</span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`FTP_BINARY`**</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`ftp`  

`remote_file`  

`local_file`  

`mode`  

### Return Values

Returns **`true`** on success or **`false`** on failure.

ftp\_cdup
=========

Changes to the parent directory

### Description

<span class="type">bool</span> <span class="methodname">ftp\_cdup</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> )

Changes to the parent directory.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ftp\_cdup</span> example**

``` php
<?php
// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// change the current directory to html
ftp_chdir($conn_id, 'html');

echo ftp_pwd($conn_id); // /html 

// return to the parent directory
if (ftp_cdup($conn_id)) { 
  echo "cdup successful\n";
} else {
  echo "cdup not successful\n";
}

echo ftp_pwd($conn_id); // /

ftp_close($conn_id);
?>
```

### See Also

-   <span class="function">ftp\_chdir</span>
-   <span class="function">ftp\_pwd</span>

ftp\_chdir
==========

Changes the current directory on a FTP server

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_chdir</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

Changes the current directory to the specified one.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`directory`  
The target directory.

### Return Values

Returns **`true`** on success or **`false`** on failure. If changing
directory fails, PHP will also throw a warning.

### Examples

**Example \#1 <span class="function">ftp\_chdir</span> example**

``` php
<?php

// set up basic connection
$conn_id = ftp_connect($ftp_server); 

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass); 

// check connection
if ((!$conn_id) || (!$login_result)) {
    die("FTP connection has failed !");
}

echo "Current directory: " . ftp_pwd($conn_id) . "\n";

// try to change the directory to somedir
if (ftp_chdir($conn_id, "somedir")) {
    echo "Current directory is now: " . ftp_pwd($conn_id) . "\n";
} else { 
    echo "Couldn't change directory\n";
}

// close the connection
ftp_close($conn_id);
?>
```

### See Also

-   <span class="function">ftp\_cdup</span>
-   <span class="function">ftp\_pwd</span>

ftp\_chmod
==========

Set permissions on a file via FTP

### Description

<span class="type">int</span> <span class="methodname">ftp\_chmod</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">int</span> `$mode`</span> , <span class="methodparam"><span
class="type">string</span> `$filename`</span> )

Sets the permissions on the specified remote file to `mode`.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`mode`  
The new permissions, given as an *octal* value.

`filename`  
The remote file.

### Return Values

Returns the new file permissions on success or **`false`** on error.

### Examples

**Example \#1 <span class="function">ftp\_chmod</span> example**

``` php
<?php
$file = 'public_html/index.php';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// try to chmod $file to 644
if (ftp_chmod($conn_id, 0644, $file) !== false) {
 echo "$file chmoded successfully to 644\n";
} else {
 echo "could not chmod $file\n";
}

// close the connection
ftp_close($conn_id);
?>
```

### See Also

-   <span class="function">chmod</span>

ftp\_close
==========

Closes an FTP connection

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_close</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> )

<span class="function">ftp\_close</span> closes the given link
identifier and releases the <span class="type">resource</span>.

> **Note**:
>
> After calling this function, you can no longer use the FTP connection
> and must create a new one with <span
> class="function">ftp\_connect</span>.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ftp\_close</span> example**

``` php
<?php

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// print the current directory
echo ftp_pwd($conn_id); // /

// close this connection
ftp_close($conn_id);
?>
```

### See Also

-   <span class="function">ftp\_connect</span>

ftp\_connect
============

Opens an FTP connection

### Description

<span class="type">resource</span> <span
class="methodname">ftp\_connect</span> ( <span class="methodparam"><span
class="type">string</span> `$host`</span> \[, <span
class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 21</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 90</span></span> \]\] )

<span class="function">ftp\_connect</span> opens an FTP connection to
the specified `host`.

### Parameters

`host`  
The FTP server address. This parameter shouldn't have any trailing
slashes and shouldn't be prefixed with *ftp://*.

`port`  
This parameter specifies an alternate port to connect to. If it is
omitted or set to zero, then the default FTP port, 21, will be used.

`timeout`  
This parameter specifies the timeout in seconds for all subsequent
network operations. If omitted, the default value is 90 seconds. The
timeout can be changed and queried at any time with <span
class="function">ftp\_set\_option</span> and <span
class="function">ftp\_get\_option</span>.

### Return Values

Returns a FTP stream on success or **`false`** on error.

### Examples

**Example \#1 <span class="function">ftp\_connect</span> example**

``` php
<?php

$ftp_server = "ftp.example.com";

// set up a connection or die
$conn_id = ftp_connect($ftp_server) or die("Couldn't connect to $ftp_server"); 

?>
```

### See Also

-   <span class="function">ftp\_close</span>
-   <span class="function">ftp\_ssl\_connect</span>

ftp\_delete
===========

Deletes a file on the FTP server

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_delete</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$path`</span> )

<span class="function">ftp\_delete</span> deletes the file specified by
`path` from the FTP server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`path`  
The file to delete.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ftp\_delete</span> example**

``` php
<?php
$file = 'public_html/old.txt';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// try to delete $file
if (ftp_delete($conn_id, $file)) {
 echo "$file deleted successful\n";
} else {
 echo "could not delete $file\n";
}

// close the connection
ftp_close($conn_id);
?>
```

ftp\_exec
=========

Requests execution of a command on the FTP server

### Description

<span class="type">bool</span> <span class="methodname">ftp\_exec</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$command`</span> )

Sends a SITE EXEC `command` request to the FTP server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`command`  
The command to execute.

### Return Values

Returns **`true`** if the command was successful (server sent response
code: *200*); otherwise returns **`false`**.

### Examples

**Example \#1 <span class="function">ftp\_exec</span> example**

``` php
<?php

// variable initialization
$command = 'ls -al >files.txt';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// execute command
if (ftp_exec($conn_id, $command)) {
    echo "$command executed successfully\n";
} else {
    echo "could not execute $command\n";
}

// close the connection
ftp_close($conn_id);

?>
```

### See Also

-   <span class="function">ftp\_raw</span>

ftp\_fget
=========

Downloads a file from the FTP server and saves to an open file

### Description

<span class="type">bool</span> <span class="methodname">ftp\_fget</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">resource</span> `$handle`</span> , <span
class="methodparam"><span class="type">string</span>
`$remote_file`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
**`FTP_BINARY`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$resumepos`<span class="initializer"> =
0</span></span> \]\] )

<span class="function">ftp\_fget</span> retrieves `remote_file` from the
FTP server, and writes it to the given file pointer.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`handle`  
An open file pointer in which we store the data.

`remote_file`  
The remote file path.

`mode`  
The transfer mode. Must be either **`FTP_ASCII`** or **`FTP_BINARY`**.

`resumepos`  
The position in the remote file to start downloading from.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.3.0   | The `mode` parameter is now optional. Formerly it has been mandatory. |

### Examples

**Example \#1 <span class="function">ftp\_fget</span> example**

``` php
<?php

// path to remote file
$remote_file = 'somefile.txt';
$local_file = 'localfile.txt';

// open some file to write to
$handle = fopen($local_file, 'w');

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// try to download $remote_file and save it to $handle
if (ftp_fget($conn_id, $handle, $remote_file, FTP_ASCII, 0)) {
 echo "successfully written to $local_file\n";
} else {
 echo "There was a problem while downloading $remote_file to $local_file\n";
}

// close the connection and the file handler
ftp_close($conn_id);
fclose($handle);
?>
```

### See Also

-   <span class="function">ftp\_get</span>
-   <span class="function">ftp\_nb\_get</span>
-   <span class="function">ftp\_nb\_fget</span>

ftp\_fput
=========

Uploads from an open file to the FTP server

### Description

<span class="type">bool</span> <span class="methodname">ftp\_fput</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$remote_file`</span> , <span
class="methodparam"><span class="type">resource</span> `$handle`</span>
\[, <span class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`FTP_BINARY`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$startpos`<span
class="initializer"> = 0</span></span> \]\] )

<span class="function">ftp\_fput</span> uploads the data from a file
pointer to a remote file on the FTP server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`remote_file`  
The remote file path.

`handle`  
An open file pointer on the local file. Reading stops at end of file.

`mode`  
The transfer mode. Must be either **`FTP_ASCII`** or **`FTP_BINARY`**.

`startpos`  
The position in the remote file to start uploading to.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.3.0   | The `mode` parameter is now optional. Formerly it has been mandatory. |

### Examples

**Example \#1 <span class="function">ftp\_fput</span> example**

``` php
<?php

// open some file for reading
$file = 'somefile.txt';
$fp = fopen($file, 'r');

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// try to upload $file
if (ftp_fput($conn_id, $file, $fp, FTP_ASCII)) {
    echo "Successfully uploaded $file\n";
} else {
    echo "There was a problem while uploading $file\n";
}

// close the connection and the file handler
ftp_close($conn_id);
fclose($fp);

?>
```

### See Also

-   <span class="function">ftp\_put</span>
-   <span class="function">ftp\_nb\_fput</span>
-   <span class="function">ftp\_nb\_put</span>

ftp\_get\_option
================

Retrieves various runtime behaviours of the current FTP stream

### Description

<span class="type">mixed</span> <span
class="methodname">ftp\_get\_option</span> ( <span
class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">int</span> `$option`</span> )

This function returns the value for the requested `option` from the
specified FTP connection.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`option`  
Currently, the following options are supported:

|                       |                                                                  |
|-----------------------|------------------------------------------------------------------|
| **`FTP_TIMEOUT_SEC`** | Returns the current timeout used for network related operations. |
| **`FTP_AUTOSEEK`**    | Returns **`true`** if this option is on, **`false`** otherwise.  |

### Return Values

Returns the value on success or **`false`** if the given `option` is not
supported. In the latter case, a warning message is also thrown.

### Examples

**Example \#1 <span class="function">ftp\_get\_option</span> example**

``` php
<?php
// Get the timeout of the given FTP stream
$timeout = ftp_get_option($conn_id, FTP_TIMEOUT_SEC);
?>
```

### See Also

-   <span class="function">ftp\_set\_option</span>

ftp\_get
========

Downloads a file from the FTP server

### Description

<span class="type">bool</span> <span class="methodname">ftp\_get</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$local_file`</span> , <span
class="methodparam"><span class="type">string</span>
`$remote_file`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
**`FTP_BINARY`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$resumepos`<span class="initializer"> =
0</span></span> \]\] )

<span class="function">ftp\_get</span> retrieves a remote file from the
FTP server, and saves it into a local file.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`local_file`  
The local file path (will be overwritten if the file already exists).

`remote_file`  
The remote file path.

`mode`  
The transfer mode. Must be either **`FTP_ASCII`** or **`FTP_BINARY`**.

`resumepos`  
The position in the remote file to start downloading from.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.3.0   | The `mode` parameter is now optional. Formerly it has been mandatory. |

### Examples

**Example \#1 <span class="function">ftp\_get</span> example**

``` php
<?php

// define some variables
$local_file = 'local.zip';
$server_file = 'server.zip';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// try to download $server_file and save to $local_file
if (ftp_get($conn_id, $local_file, $server_file, FTP_BINARY)) {
    echo "Successfully written to $local_file\n";
} else {
    echo "There was a problem\n";
}

// close the connection
ftp_close($conn_id);

?>
```

### See Also

-   <span class="function">ftp\_pasv</span>
-   <span class="function">ftp\_fget</span>
-   <span class="function">ftp\_nb\_get</span>
-   <span class="function">ftp\_nb\_fget</span>

ftp\_login
==========

Logs in to an FTP connection

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_login</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$username`</span>
, <span class="methodparam"><span class="type">string</span>
`$password`</span> )

Logs in to the given FTP stream.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`username`  
The username (*USER*).

`password`  
The password (*PASS*).

### Return Values

Returns **`true`** on success or **`false`** on failure. If login fails,
PHP will also throw a warning.

### Examples

**Example \#1 <span class="function">ftp\_login</span> example**

``` php
<?php
                     
$ftp_server = "ftp.example.com";
$ftp_user = "foo";
$ftp_pass = "bar";

// set up a connection or die
$conn_id = ftp_connect($ftp_server) or die("Couldn't connect to $ftp_server"); 

// try to login
if (@ftp_login($conn_id, $ftp_user, $ftp_pass)) {
    echo "Connected as $ftp_user@$ftp_server\n";
} else {
    echo "Couldn't connect as $ftp_user\n";
}

// close the connection
ftp_close($conn_id);  
?>
```

ftp\_mdtm
=========

Returns the last modified time of the given file

### Description

<span class="type">int</span> <span class="methodname">ftp\_mdtm</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$remote_file`</span> )

<span class="function">ftp\_mdtm</span> gets the last modified time for
a remote file.

> **Note**:
>
> Not all servers support this feature!

> **Note**:
>
> <span class="function">ftp\_mdtm</span> does not work with
> directories.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`remote_file`  
The file from which to extract the last modification time.

### Return Values

Returns the last modified time as a Unix timestamp on success, or -1 on
error.

### Examples

**Example \#1 <span class="function">ftp\_mdtm</span> example**

``` php
<?php

$file = 'somefile.txt';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

//  get the last modified time
$buff = ftp_mdtm($conn_id, $file);

if ($buff != -1) {
    // somefile.txt was last modified on: March 26 2003 14:16:41.
    echo "$file was last modified on : " . date("F d Y H:i:s.", $buff);
} else {
    echo "Couldn't get mdtime";
}

// close the connection
ftp_close($conn_id);

?>
```

ftp\_mkdir
==========

Creates a directory

### Description

<span class="type">string</span> <span
class="methodname">ftp\_mkdir</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

Creates the specified `directory` on the FTP server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`directory`  
The name of the directory that will be created.

### Return Values

Returns the newly created directory name on success or **`false`** on
error.

### Examples

**Example \#1 <span class="function">ftp\_mkdir</span> example**

``` php
<?php

$dir = 'www';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// try to create the directory $dir
if (ftp_mkdir($conn_id, $dir)) {
 echo "successfully created $dir\n";
} else {
 echo "There was a problem while creating $dir\n";
}

// close the connection
ftp_close($conn_id);
?>
```

### See Also

-   <span class="function">ftp\_rmdir</span>

ftp\_mlsd
=========

Returns a list of files in the given directory

### Description

<span class="type">array</span> <span
class="methodname">ftp\_mlsd</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`directory`  
The directory to be listed.

### Return Values

Returns an array of arrays with file infos from the specified directory
on success or **`false`** on error.

### Examples

**Example \#1 <span class="function">ftp\_mlsd</span> example**

``` php
<?php

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// get contents of the current directory
$contents = ftp_mlsd($conn_id, ".");

// output $contents
var_dump($contents);

?>
```

The above example will output something similar to:

    array(5) {
      [0]=>
      array(8) {
        ["name"]=>
        string(1) "."
        ["modify"]=>
        string(14) "20171212154511"
        ["perm"]=>
        string(7) "flcdmpe"
        ["type"]=>
        string(4) "cdir"
        ["unique"]=>
        string(11) "811U5740002"
        ["UNIX.group"]=>
        string(2) "33"
        ["UNIX.mode"]=>
        string(4) "0755"
        ["UNIX.owner"]=>
        string(2) "33"
      }
      [1]=>
      array(8) {
        ["name"]=>
        string(2) ".."
        ["modify"]=>
        string(14) "20171212154511"
        ["perm"]=>
        string(7) "flcdmpe"
        ["type"]=>
        string(4) "pdir"
        ["unique"]=>
        string(11) "811U5740002"
        ["UNIX.group"]=>
        string(2) "33"
        ["UNIX.mode"]=>
        string(4) "0755"
        ["UNIX.owner"]=>
        string(2) "33"
      }
      [2]=>
      array(8) {
        ["name"]=>
        string(11) "public_html"
        ["modify"]=>
        string(14) "20171211171525"
        ["perm"]=>
        string(7) "flcdmpe"
        ["type"]=>
        string(3) "dir"
        ["unique"]=>
        string(11) "811U5740525"
        ["UNIX.group"]=>
        string(2) "33"
        ["UNIX.mode"]=>
        string(4) "0755"
        ["UNIX.owner"]=>
        string(2) "33"
      }
      [3]=>
      array(8) {
        ["name"]=>
        string(10) "public_ftp"
        ["modify"]=>
        string(14) "20171211174536"
        ["perm"]=>
        string(7) "flcdmpe"
        ["type"]=>
        string(3) "dir"
        ["unique"]=>
        string(11) "811U57405EE"
        ["UNIX.group"]=>
        string(2) "33"
        ["UNIX.mode"]=>
        string(4) "0755"
        ["UNIX.owner"]=>
        string(2) "33"
      }
      [4]=>
      array(8) {
        ["name"]=>
        string(3) "www"
        ["modify"]=>
        string(14) "www"
        ["perm"]=>
        string(7) "flcdmpe"
        ["type"]=>
        string(3) "dir"
        ["unique"]=>
        string(11) "811U5740780"
        ["UNIX.group"]=>
        string(2) "33"
        ["UNIX.mode"]=>
        string(4) "0755"
        ["UNIX.owner"]=>
        string(2) "33"
      }
    }

### See Also

-   <span class="function">ftp\_rawlist</span>
-   <span class="function">ftp\_nlist</span>

ftp\_nb\_continue
=================

Continues retrieving/sending a file (non-blocking)

### Description

<span class="type">int</span> <span
class="methodname">ftp\_nb\_continue</span> ( <span
class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> )

Continues retrieving/sending a file non-blocking.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

### Return Values

Returns **`FTP_FAILED`** or **`FTP_FINISHED`** or **`FTP_MOREDATA`**.

### Examples

**Example \#1 <span class="function">ftp\_nb\_continue</span> example**

``` php
<?php

// Initiate the download
$ret = ftp_nb_get($my_connection, "test", "README", FTP_BINARY);
while ($ret == FTP_MOREDATA) {

   // Continue downloading...
   $ret = ftp_nb_continue($my_connection);
}
if ($ret != FTP_FINISHED) {
   echo "There was an error downloading the file...";
   exit(1);
}
?>
```

ftp\_nb\_fget
=============

Retrieves a file from the FTP server and writes it to an open file
(non-blocking)

### Description

<span class="type">int</span> <span
class="methodname">ftp\_nb\_fget</span> ( <span
class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">resource</span> `$handle`</span> , <span
class="methodparam"><span class="type">string</span>
`$remote_file`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
**`FTP_BINARY`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$resumepos`<span class="initializer"> =
0</span></span> \]\] )

<span class="function">ftp\_nb\_fget</span> retrieves a remote file from
the FTP server.

The difference between this function and <span
class="function">ftp\_fget</span> is that this function retrieves the
file asynchronously, so your program can perform other operations while
the file is being downloaded.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`handle`  
An open file pointer in which we store the data.

`remote_file`  
The remote file path.

`mode`  
The transfer mode. Must be either **`FTP_ASCII`** or **`FTP_BINARY`**.

`resumepos`  
The position in the remote file to start downloading from.

### Return Values

Returns **`FTP_FAILED`** or **`FTP_FINISHED`** or **`FTP_MOREDATA`**.

### Changelog

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.3.0   | The `mode` parameter is now optional. Formerly it has been mandatory. |

### Examples

**Example \#1 <span class="function">ftp\_nb\_fget</span> example**

``` php
<?php

// open some file for reading
$file = 'index.php';
$fp = fopen($file, 'w');

$conn_id = ftp_connect($ftp_server);

$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// Initiate the download
$ret = ftp_nb_fget($conn_id, $fp, $file, FTP_BINARY);
while ($ret == FTP_MOREDATA) {

   // Do whatever you want
   echo ".";

   // Continue downloading...
   $ret = ftp_nb_continue($conn_id);
}
if ($ret != FTP_FINISHED) {
   echo "There was an error downloading the file...";
   exit(1);
}

// close filepointer
fclose($fp);
?>
```

### See Also

-   <span class="function">ftp\_nb\_get</span>
-   <span class="function">ftp\_nb\_continue</span>
-   <span class="function">ftp\_fget</span>
-   <span class="function">ftp\_get</span>

ftp\_nb\_fput
=============

Stores a file from an open file to the FTP server (non-blocking)

### Description

<span class="type">int</span> <span
class="methodname">ftp\_nb\_fput</span> ( <span
class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$remote_file`</span> , <span
class="methodparam"><span class="type">resource</span> `$handle`</span>
\[, <span class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`FTP_BINARY`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$startpos`<span
class="initializer"> = 0</span></span> \]\] )

<span class="function">ftp\_nb\_fput</span> uploads the data from a file
pointer to a remote file on the FTP server.

The difference between this function and the <span
class="function">ftp\_fput</span> is that this function uploads the file
asynchronously, so your program can perform other operations while the
file is being uploaded.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`remote_file`  
The remote file path.

`handle`  
An open file pointer on the local file. Reading stops at end of file.

`mode`  
The transfer mode. Must be either **`FTP_ASCII`** or **`FTP_BINARY`**.

`startpos`  
The position in the remote file to start uploading to.

### Return Values

Returns **`FTP_FAILED`** or **`FTP_FINISHED`** or **`FTP_MOREDATA`**.

### Changelog

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.3.0   | The `mode` parameter is now optional. Formerly it has been mandatory. |

### Examples

**Example \#1 <span class="function">ftp\_nb\_fput</span> example**

``` php
<?php

$file = 'index.php';

$fp = fopen($file, 'r');

$conn_id = ftp_connect($ftp_server);

$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// Initiate the upload
$ret = ftp_nb_fput($conn_id, $file, $fp, FTP_BINARY);
while ($ret == FTP_MOREDATA) {

   // Do whatever you want
   echo ".";

   // Continue upload...
   $ret = ftp_nb_continue($conn_id);
}
if ($ret != FTP_FINISHED) {
   echo "There was an error uploading the file...";
   exit(1);
}

fclose($fp);
?>
```

### See Also

-   <span class="function">ftp\_nb\_put</span>
-   <span class="function">ftp\_nb\_continue</span>
-   <span class="function">ftp\_put</span>
-   <span class="function">ftp\_fput</span>

ftp\_nb\_get
============

Retrieves a file from the FTP server and writes it to a local file
(non-blocking)

### Description

<span class="type">int</span> <span
class="methodname">ftp\_nb\_get</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span>
`$local_file`</span> , <span class="methodparam"><span
class="type">string</span> `$remote_file`</span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`FTP_BINARY`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$resumepos`<span
class="initializer"> = 0</span></span> \]\] )

<span class="function">ftp\_nb\_get</span> retrieves a remote file from
the FTP server, and saves it into a local file.

The difference between this function and <span
class="function">ftp\_get</span> is that this function retrieves the
file asynchronously, so your program can perform other operations while
the file is being downloaded.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`local_file`  
The local file path (will be overwritten if the file already exists).

`remote_file`  
The remote file path.

`mode`  
The transfer mode. Must be either **`FTP_ASCII`** or **`FTP_BINARY`**.

`resumepos`  
The position in the remote file to start downloading from.

### Return Values

Returns **`FTP_FAILED`** or **`FTP_FINISHED`** or **`FTP_MOREDATA`**.

### Changelog

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.3.0   | The `mode` parameter is now optional. Formerly it has been mandatory. |

### Examples

**Example \#1 <span class="function">ftp\_nb\_get</span> example**

``` php
<?php

// Initiate the download
$ret = ftp_nb_get($my_connection, "test", "README", FTP_BINARY);
while ($ret == FTP_MOREDATA) {
   
   // Do whatever you want
   echo ".";

   // Continue downloading...
   $ret = ftp_nb_continue($my_connection);
}
if ($ret != FTP_FINISHED) {
   echo "There was an error downloading the file...";
   exit(1);
}
?>
```

**Example \#2 Resuming a download with <span
class="function">ftp\_nb\_get</span>**

``` php
<?php

// Initiate 
$ret = ftp_nb_get($my_connection, "test", "README", FTP_BINARY, 
                      filesize("test"));
// OR: $ret = ftp_nb_get($my_connection, "test", "README", 
//                           FTP_BINARY, FTP_AUTORESUME);
while ($ret == FTP_MOREDATA) {
   
   // Do whatever you want
   echo ".";

   // Continue downloading...
   $ret = ftp_nb_continue($my_connection);
}
if ($ret != FTP_FINISHED) {
   echo "There was an error downloading the file...";
   exit(1);
}
?>
```

**Example \#3 Resuming a download at position 100 to a new file with
<span class="function">ftp\_nb\_get</span>**

``` php
<?php

// Disable Autoseek
ftp_set_option($my_connection, FTP_AUTOSEEK, false);

// Initiate
$ret = ftp_nb_get($my_connection, "newfile", "README", FTP_BINARY, 100);
while ($ret == FTP_MOREDATA) {

   /* ... */
   
   // Continue downloading...
   $ret = ftp_nb_continue($my_connection);
}
?>
```

In the example above, `newfile` is 100 bytes smaller than `README` on
the FTP server because we started reading at offset 100. If we didn't
disable **`FTP_AUTOSEEK`**, the first 100 bytes of `newfile` would be
*'\\0'*.

### See Also

-   <span class="function">ftp\_nb\_fget</span>
-   <span class="function">ftp\_nb\_continue</span>
-   <span class="function">ftp\_fget</span>
-   <span class="function">ftp\_get</span>

ftp\_nb\_put
============

Stores a file on the FTP server (non-blocking)

### Description

<span class="type">int</span> <span
class="methodname">ftp\_nb\_put</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span>
`$remote_file`</span> , <span class="methodparam"><span
class="type">string</span> `$local_file`</span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`FTP_BINARY`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$startpos`<span
class="initializer"> = 0</span></span> \]\] )

<span class="function">ftp\_nb\_put</span> stores a local file on the
FTP server.

The difference between this function and the <span
class="function">ftp\_put</span> is that this function uploads the file
asynchronously, so your program can perform other operations while the
file is being uploaded.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`remote_file`  
The remote file path.

`local_file`  
The local file path.

`mode`  
The transfer mode. Must be either **`FTP_ASCII`** or **`FTP_BINARY`**.

`startpos`  
The position in the remote file to start uploading to.

### Return Values

Returns **`FTP_FAILED`** or **`FTP_FINISHED`** or **`FTP_MOREDATA`**.

### Changelog

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.3.0   | The `mode` parameter is now optional. Formerly it has been mandatory. |

### Examples

**Example \#1 <span class="function">ftp\_nb\_put</span> example**

``` php
<?php

// Initiate the Upload
$ret = ftp_nb_put($my_connection, "test.remote", "test.local", FTP_BINARY);
while ($ret == FTP_MOREDATA) {
   
   // Do whatever you want
   echo ".";

   // Continue uploading...
   $ret = ftp_nb_continue($my_connection);
}
if ($ret != FTP_FINISHED) {
   echo "There was an error uploading the file...";
   exit(1);
}
?>
```

**Example \#2 Resuming an upload with <span
class="function">ftp\_nb\_put</span>**

``` php
<?php

// Initiate
$ret = ftp_nb_put($my_connection, "test.remote", "test.local", 
                      FTP_BINARY, ftp_size("test.remote"));
// OR: $ret = ftp_nb_put($my_connection, "test.remote", "test.local", 
//                           FTP_BINARY, FTP_AUTORESUME);

while ($ret == FTP_MOREDATA) {
   
   // Do whatever you want
   echo ".";

   // Continue uploading...
   $ret = ftp_nb_continue($my_connection);
}
if ($ret != FTP_FINISHED) {
   echo "There was an error uploading the file...";
   exit(1);
}
?>
```

### See Also

-   <span class="function">ftp\_nb\_fput</span>
-   <span class="function">ftp\_nb\_continue</span>
-   <span class="function">ftp\_put</span>
-   <span class="function">ftp\_fput</span>

ftp\_nlist
==========

Returns a list of files in the given directory

### Description

<span class="type">array</span> <span
class="methodname">ftp\_nlist</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`directory`  
The directory to be listed. This parameter can also include arguments,
eg. ftp\_nlist($conn\_id, "-la /your/dir"); Note that this parameter
isn't escaped so there may be some issues with filenames containing
spaces and other characters.

### Return Values

Returns an array of filenames from the specified directory on success or
**`false`** on error.

### Examples

**Example \#1 <span class="function">ftp\_nlist</span> example**

``` php
<?php

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// get contents of the current directory
$contents = ftp_nlist($conn_id, ".");

// output $contents
var_dump($contents);

?>
```

The above example will output something similar to:

    array(3) {
      [0]=>
      string(11) "public_html"
      [1]=>
      string(10) "public_ftp"
      [2]=>
      string(3) "www"

### See Also

-   <span class="function">ftp\_rawlist</span>
-   <span class="function">ftp\_mlsd</span>

ftp\_pasv
=========

Turns passive mode on or off

### Description

<span class="type">bool</span> <span class="methodname">ftp\_pasv</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">bool</span> `$pasv`</span> )

<span class="function">ftp\_pasv</span> turns on or off passive mode. In
passive mode, data connections are initiated by the client, rather than
by the server. It may be needed if the client is behind firewall.

Please note that <span class="function">ftp\_pasv</span> can only be
called after a successful login or otherwise it will fail.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`pasv`  
If **`true`**, the passive mode is turned on, else it's turned off.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ftp\_pasv</span> example**

``` php
<?php
$file = 'somefile.txt';
$remote_file = 'readme.txt';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// turn passive mode on
ftp_pasv($conn_id, true);

// upload a file
if (ftp_put($conn_id, $remote_file, $file, FTP_ASCII)) {
 echo "successfully uploaded $file\n";
} else {
 echo "There was a problem while uploading $file\n";
}

// close the connection
ftp_close($conn_id);
?>
```

ftp\_put
========

Uploads a file to the FTP server

### Description

<span class="type">bool</span> <span class="methodname">ftp\_put</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$remote_file`</span> , <span
class="methodparam"><span class="type">string</span>
`$local_file`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
**`FTP_BINARY`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$startpos`<span class="initializer"> =
0</span></span> \]\] )

<span class="function">ftp\_put</span> stores a local file on the FTP
server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`remote_file`  
The remote file path.

`local_file`  
The local file path.

`mode`  
The transfer mode. Must be either **`FTP_ASCII`** or **`FTP_BINARY`**.

`startpos`  
The position in the remote file to start uploading to.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                           |
|---------|-----------------------------------------------------------------------|
| 7.3.0   | The `mode` parameter is now optional. Formerly it has been mandatory. |

### Examples

**Example \#1 <span class="function">ftp\_put</span> example**

``` php
<?php
$file = 'somefile.txt';
$remote_file = 'readme.txt';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// upload a file
if (ftp_put($conn_id, $remote_file, $file, FTP_ASCII)) {
 echo "successfully uploaded $file\n";
} else {
 echo "There was a problem while uploading $file\n";
}

// close the connection
ftp_close($conn_id);
?>
```

### See Also

-   <span class="function">ftp\_pasv</span>
-   <span class="function">ftp\_fput</span>
-   <span class="function">ftp\_nb\_fput</span>
-   <span class="function">ftp\_nb\_put</span>

ftp\_pwd
========

Returns the current directory name

### Description

<span class="type">string</span> <span
class="methodname">ftp\_pwd</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> )

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

### Return Values

Returns the current directory name or **`false`** on error.

### Examples

**Example \#1 <span class="function">ftp\_pwd</span> example**

``` php
<?php

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// change directory to public_html
ftp_chdir($conn_id, 'public_html');

// print current directory
echo ftp_pwd($conn_id); // /public_html

// close the connection
ftp_close($conn_id);
?>
```

### See Also

-   <span class="function">ftp\_chdir</span>
-   <span class="function">ftp\_cdup</span>

ftp\_quit
=========

Alias of <span class="function">ftp\_close</span>

### Description

This function is an alias of: <span class="function">ftp\_close</span>.

ftp\_raw
========

Sends an arbitrary command to an FTP server

### Description

<span class="type">array</span> <span class="methodname">ftp\_raw</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$command`</span> )

Sends an arbitrary `command` to the FTP server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`command`  
The command to execute.

### Return Values

Returns the server's response as an array of strings. No parsing is
performed on the response string, nor does <span
class="function">ftp\_raw</span> determine if the command succeeded.

### Examples

**Example \#1 Using <span class="function">ftp\_raw</span> to login to
an FTP server manually.**

``` php
<?php
$fp = ftp_connect("ftp.example.com");

/* This is the same as: 
   ftp_login($fp, "joeblow", "secret"); */
ftp_raw($fp, "USER joeblow");
ftp_raw($fp, "PASS secret");
?>
```

### See Also

-   <span class="function">ftp\_exec</span>

ftp\_rawlist
============

Returns a detailed list of files in the given directory

### Description

<span class="type">array</span> <span
class="methodname">ftp\_rawlist</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$directory`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$recursive`<span class="initializer"> = **`false`**</span></span> \] )

<span class="function">ftp\_rawlist</span> executes the FTP **LIST**
command, and returns the result as an array.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`directory`  
The directory path. May include arguments for the **LIST** command.

`recursive`  
If set to **`true`**, the issued command will be **LIST -R**.

### Return Values

Returns an array where each element corresponds to one line of text.
Returns **`false`** when passed `directory` is invalid.

The output is not parsed in any way. The system type identifier returned
by <span class="function">ftp\_systype</span> can be used to determine
how the results should be interpreted.

### Examples

**Example \#1 <span class="function">ftp\_rawlist</span> example**

``` php
<?php

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// get the file list for /
$buff = ftp_rawlist($conn_id, '/');

// close the connection
ftp_close($conn_id);

// output the buffer
var_dump($buff);
?>
```

The above example will output something similar to:

    array(3) {
      [0]=>
      string(65) "drwxr-x---   3 vincent  vincent      4096 Jul 12 12:16 public_ftp"
      [1]=>
      string(66) "drwxr-x---  15 vincent  vincent      4096 Nov  3 21:31 public_html"
      [2]=>
      string(73) "lrwxrwxrwx   1 vincent  vincent        11 Jul 12 12:16 www -> public_html"
    }

### See Also

-   <span class="function">ftp\_nlist</span>
-   <span class="function">ftp\_mlsd</span>

ftp\_rename
===========

Renames a file or a directory on the FTP server

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_rename</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$oldname`</span> ,
<span class="methodparam"><span class="type">string</span>
`$newname`</span> )

<span class="function">ftp\_rename</span> renames a file or a directory
on the FTP server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`oldname`  
The old file/directory name.

`newname`  
The new name.

### Return Values

Returns **`true`** on success or **`false`** on failure. Upon failure
(such as attempting to rename a non-existent file), an *E\_WARNING*
error will be emitted.

### Examples

**Example \#1 <span class="function">ftp\_rename</span> example**

``` php
<?php
$old_file = 'somefile.txt.bak';
$new_file = 'somefile.txt';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// try to rename $old_file to $new_file
if (ftp_rename($conn_id, $old_file, $new_file)) {
 echo "successfully renamed $old_file to $new_file\n";
} else {
 echo "There was a problem while renaming $old_file to $new_file\n";
}

// close the connection
ftp_close($conn_id);
?>
```

ftp\_rmdir
==========

Removes a directory

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_rmdir</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> , <span
class="methodparam"><span class="type">string</span> `$directory`</span>
)

Removes the specified `directory` on the FTP server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`directory`  
The directory to delete. This must be either an absolute or relative
path to an empty directory.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">ftp\_rmdir</span> example**

``` php
<?php

$dir = 'www/';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// try to delete the directory $dir
if (ftp_rmdir($conn_id, $dir)) {
    echo "Successfully deleted $dir\n";
} else {
    echo "There was a problem while deleting $dir\n";
}

ftp_close($conn_id);

?>
```

### See Also

-   <span class="function">ftp\_mkdir</span>

ftp\_set\_option
================

Set miscellaneous runtime FTP options

### Description

<span class="type">bool</span> <span
class="methodname">ftp\_set\_option</span> ( <span
class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">int</span> `$option`</span> , <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

This function controls various runtime options for the specified FTP
stream.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`option`  
Currently, the following options are supported:

|                          |                                                                                                                                                                                                             |
|--------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`FTP_TIMEOUT_SEC`**    | Changes the timeout in seconds used for all network related functions. `value` must be an integer that is greater than 0. The default timeout is 90 seconds.                                                |
| **`FTP_AUTOSEEK`**       | When enabled, GET or PUT requests with a `resumepos` or `startpos` parameter will first seek to the requested position within the file. This is enabled by default.                                         |
| **`FTP_USEPASVADDRESS`** | When disabled, PHP will ignore the IP address returned by the FTP server in response to the PASV command and instead use the IP address that was supplied in the ftp\_connect(). `value` must be a boolean. |

`value`  
This parameter depends on which `option` is chosen to be altered.

### Return Values

Returns **`true`** if the option could be set; **`false`** if not. A
warning message will be thrown if the `option` is not supported or the
passed `value` doesn't match the expected value for the given `option`.

### Examples

**Example \#1 <span class="function">ftp\_set\_option</span> example**

``` php
<?php
// Set the network timeout to 10 seconds
ftp_set_option($conn_id, FTP_TIMEOUT_SEC, 10);
?>
```

### See Also

-   <span class="function">ftp\_get\_option</span>

ftp\_site
=========

Sends a SITE command to the server

### Description

<span class="type">bool</span> <span class="methodname">ftp\_site</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$command`</span> )

<span class="function">ftp\_site</span> sends the given *SITE* command
to the FTP server.

*SITE* commands are not standardized, and vary from server to server.
They are useful for handling such things as file permissions and group
membership.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`command`  
The SITE command. Note that this parameter isn't escaped so there may be
some issues with filenames containing spaces and other characters.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Sending a SITE command to an ftp server**

``` php
<?php
// Connect to FTP server
$conn = ftp_connect('ftp.example.com');
if (!$conn) die('Unable to connect to ftp.example.com');

// Login as "user" with password "pass"
if (!ftp_login($conn, 'user', 'pass')) die('Error logging into ftp.example.com');

// Issue: "SITE CHMOD 0600 /home/user/privatefile" command to ftp server
if (ftp_site($conn, 'CHMOD 0600 /home/user/privatefile')) {
   echo "Command executed successfully.\n";
} else {
   die('Command failed.');
}
?>
```

### See Also

-   <span class="function">ftp\_raw</span>

ftp\_size
=========

Returns the size of the given file

### Description

<span class="type">int</span> <span class="methodname">ftp\_size</span>
( <span class="methodparam"><span class="type">resource</span>
`$ftp_stream`</span> , <span class="methodparam"><span
class="type">string</span> `$remote_file`</span> )

<span class="function">ftp\_size</span> returns the size of the given
file in bytes.

> **Note**:
>
> Not all servers support this feature.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

`remote_file`  
The remote file.

### Return Values

Returns the file size on success, or -1 on error.

### Examples

**Example \#1 <span class="function">ftp\_size</span> example**

``` php
<?php

$file = 'somefile.txt';

// set up basic connection
$conn_id = ftp_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

// get the size of $file
$res = ftp_size($conn_id, $file);

if ($res != -1) {
    echo "size of $file is $res bytes";
} else {
    echo "couldn't get the size";
}

// close the connection
ftp_close($conn_id);

?>
```

### See Also

-   <span class="function">ftp\_rawlist</span>

ftp\_ssl\_connect
=================

Opens a Secure SSL-FTP connection

### Description

<span class="type">resource</span> <span
class="methodname">ftp\_ssl\_connect</span> ( <span
class="methodparam"><span class="type">string</span> `$host`</span> \[,
<span class="methodparam"><span class="type">int</span> `$port`<span
class="initializer"> = 21</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$timeout`<span
class="initializer"> = 90</span></span> \]\] )

<span class="function">ftp\_ssl\_connect</span> opens an *explicit*
SSL-FTP connection to the specified `host`. That implies that <span
class="function">ftp\_ssl\_connect</span> will succeed even if the
server is not configured for SSL-FTP, or its certificate is invalid.
Only when <span class="function">ftp\_login</span> is called, the client
will send the appropriate AUTH FTP command, so <span
class="function">ftp\_login</span> will fail in the mentioned cases.

> **Note**: **Why this function may not exist**  
>
> Before PHP 7.0.0, <span class="function">ftp\_ssl\_connect</span> was
> only available if both the ftp module and the
> <a href="/ref/openssl.html" class="link">OpenSSL</a> support have been
> built statically into php; this means that on Windows this function
> had been undefined in the official PHP builds. To have this function
> available on Windows, it had been necessary to compile own PHP
> binaries.

> **Note**:
>
> <span class="function">ftp\_ssl\_connect</span> is not intended for
> use with sFTP. To use sFTP with PHP, please see <span
> class="function">ssh2\_sftp</span>.

### Parameters

`host`  
The FTP server address. This parameter shouldn't have any trailing
slashes and shouldn't be prefixed with *ftp://*.

`port`  
This parameter specifies an alternate port to connect to. If it is
omitted or set to zero, then the default FTP port, 21, will be used.

`timeout`  
This parameter specifies the timeout for all subsequent network
operations. If omitted, the default value is 90 seconds. The timeout can
be changed and queried at any time with <span
class="function">ftp\_set\_option</span> and <span
class="function">ftp\_get\_option</span>.

### Return Values

Returns a SSL-FTP stream on success or **`false`** on error.

### Examples

**Example \#1 <span class="function">ftp\_ssl\_connect</span> example**

``` php
<?php

// set up basic ssl connection
$conn_id = ftp_ssl_connect($ftp_server);

// login with username and password
$login_result = ftp_login($conn_id, $ftp_user_name, $ftp_user_pass);

if (!$login_result) {
    // PHP will already have raised an E_WARNING level message in this case
    die("can't login");
}

echo ftp_pwd($conn_id); // /

// close the ssl connection
ftp_close($conn_id);
?>
```

### See Also

-   <span class="function">ftp\_connect</span>

ftp\_systype
============

Returns the system type identifier of the remote FTP server

### Description

<span class="type">string</span> <span
class="methodname">ftp\_systype</span> ( <span class="methodparam"><span
class="type">resource</span> `$ftp_stream`</span> )

Returns the system type identifier of the remote FTP server.

### Parameters

`ftp_stream`  
The link identifier of the FTP connection.

### Return Values

Returns the remote system type, or **`false`** on error.

### Examples

**Example \#1 <span class="function">ftp\_systype</span> example**

``` php
<?php

// ftp connection
$ftp = ftp_connect('ftp.example.com');
ftp_login($ftp, 'user', 'password');

// get the system type
if ($type = ftp_systype($ftp)) {
    echo "Example.com is powered by $type\n";
} else {
    echo "Couldn't get the systype";
}

?>
```

The above example will output something similar to:

    Example.com is powered by UNIX

**Table of Contents**

-   [ftp\_alloc](/ref/ftp.html#ftp_alloc) — Allocates space for a file
    to be uploaded
-   [ftp\_append](/ref/ftp.html#ftp_append) — Append the contents of a
    file to another file on the FTP server
-   [ftp\_cdup](/ref/ftp.html#ftp_cdup) — Changes to the parent
    directory
-   [ftp\_chdir](/ref/ftp.html#ftp_chdir) — Changes the current
    directory on a FTP server
-   [ftp\_chmod](/ref/ftp.html#ftp_chmod) — Set permissions on a file
    via FTP
-   [ftp\_close](/ref/ftp.html#ftp_close) — Closes an FTP connection
-   [ftp\_connect](/ref/ftp.html#ftp_connect) — Opens an FTP connection
-   [ftp\_delete](/ref/ftp.html#ftp_delete) — Deletes a file on the FTP
    server
-   [ftp\_exec](/ref/ftp.html#ftp_exec) — Requests execution of a
    command on the FTP server
-   [ftp\_fget](/ref/ftp.html#ftp_fget) — Downloads a file from the FTP
    server and saves to an open file
-   [ftp\_fput](/ref/ftp.html#ftp_fput) — Uploads from an open file to
    the FTP server
-   [ftp\_get\_option](/ref/ftp.html#ftp_get_option) — Retrieves various
    runtime behaviours of the current FTP stream
-   [ftp\_get](/ref/ftp.html#ftp_get) — Downloads a file from the FTP
    server
-   [ftp\_login](/ref/ftp.html#ftp_login) — Logs in to an FTP connection
-   [ftp\_mdtm](/ref/ftp.html#ftp_mdtm) — Returns the last modified time
    of the given file
-   [ftp\_mkdir](/ref/ftp.html#ftp_mkdir) — Creates a directory
-   [ftp\_mlsd](/ref/ftp.html#ftp_mlsd) — Returns a list of files in the
    given directory
-   [ftp\_nb\_continue](/ref/ftp.html#ftp_nb_continue) — Continues
    retrieving/sending a file (non-blocking)
-   [ftp\_nb\_fget](/ref/ftp.html#ftp_nb_fget) — Retrieves a file from
    the FTP server and writes it to an open file (non-blocking)
-   [ftp\_nb\_fput](/ref/ftp.html#ftp_nb_fput) — Stores a file from an
    open file to the FTP server (non-blocking)
-   [ftp\_nb\_get](/ref/ftp.html#ftp_nb_get) — Retrieves a file from the
    FTP server and writes it to a local file (non-blocking)
-   [ftp\_nb\_put](/ref/ftp.html#ftp_nb_put) — Stores a file on the FTP
    server (non-blocking)
-   [ftp\_nlist](/ref/ftp.html#ftp_nlist) — Returns a list of files in
    the given directory
-   [ftp\_pasv](/ref/ftp.html#ftp_pasv) — Turns passive mode on or off
-   [ftp\_put](/ref/ftp.html#ftp_put) — Uploads a file to the FTP server
-   [ftp\_pwd](/ref/ftp.html#ftp_pwd) — Returns the current directory
    name
-   [ftp\_quit](/ref/ftp.html#ftp_quit) — Alias of ftp\_close
-   [ftp\_raw](/ref/ftp.html#ftp_raw) — Sends an arbitrary command to an
    FTP server
-   [ftp\_rawlist](/ref/ftp.html#ftp_rawlist) — Returns a detailed list
    of files in the given directory
-   [ftp\_rename](/ref/ftp.html#ftp_rename) — Renames a file or a
    directory on the FTP server
-   [ftp\_rmdir](/ref/ftp.html#ftp_rmdir) — Removes a directory
-   [ftp\_set\_option](/ref/ftp.html#ftp_set_option) — Set miscellaneous
    runtime FTP options
-   [ftp\_site](/ref/ftp.html#ftp_site) — Sends a SITE command to the
    server
-   [ftp\_size](/ref/ftp.html#ftp_size) — Returns the size of the given
    file
-   [ftp\_ssl\_connect](/ref/ftp.html#ftp_ssl_connect) — Opens a Secure
    SSL-FTP connection
-   [ftp\_systype](/ref/ftp.html#ftp_systype) — Returns the system type
    identifier of the remote FTP server

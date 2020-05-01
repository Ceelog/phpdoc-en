ftp://
======

ftps://
=======

Accessing FTP(s) URLs

### Description

Allows read access to existing files and creation of new files via FTP.
If the server does not support passive mode ftp, the connection will
fail.

You can open files for either reading or writing, but not both
simultaneously. If the remote file already exists on the ftp server and
you attempt to open it for writing but have not specified the context
option *overwrite*, the connection will fail. If you need to overwrite
existing files over ftp, specify the *overwrite* option in the context
and open the file for writing. Alternatively, you can use the
<a href="/ref/ftp.html" class="link">FTP extension</a>.

If you have set the
<a href="/filesystem/setup.html#" class="link">from</a> directive in
`php.ini`, then this value will be sent as the anonymous FTP password.

### Usage

-   <span class="simpara">`ftp://example.com/pub/file.txt`</span>
-   <span
    class="simpara">`ftp://user:password@example.com/pub/file.txt`</span>
-   <span class="simpara">`ftps://example.com/pub/file.txt`</span>
-   <span
    class="simpara">`ftps://user:password@example.com/pub/file.txt`</span>

### Options

| Attribute                                                                        | Supported                                                                                                                                                                                                                                                                              |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a> | Yes                                                                                                                                                                                                                                                                                    |
| Allows Reading                                                                   | Yes                                                                                                                                                                                                                                                                                    |
| Allows Writing                                                                   | Yes (new files/existing files with `overwrite`)                                                                                                                                                                                                                                        |
| Allows Appending                                                                 | Yes                                                                                                                                                                                                                                                                                    |
| Allows Simultaneous Reading and Writing                                          | No                                                                                                                                                                                                                                                                                     |
| Supports <span class="function">stat</span>                                      | <span class="function">filesize</span>, <span class="function">filetype</span>, <span class="function">file\_exists</span>, <span class="function">is\_file</span>, and <span class="function">is\_dir</span> elements only. As of PHP 5.1.0: <span class="function">filemtime</span>. |
| Supports <span class="function">unlink</span>                                    | Yes                                                                                                                                                                                                                                                                                    |
| Supports <span class="function">rename</span>                                    | Yes                                                                                                                                                                                                                                                                                    |
| Supports <span class="function">mkdir</span>                                     | Yes                                                                                                                                                                                                                                                                                    |
| Supports <span class="function">rmdir</span>                                     | Yes                                                                                                                                                                                                                                                                                    |

### Notes

> **Note**:
>
> FTPS is only supported when the
> <a href="/book/openssl.html" class="link">openssl</a> extension is
> enabled.
>
> <span class="simpara"> If the server does not support SSL, then the
> connection falls back to regular unencrypted ftp. </span>

> **Note**: **Appending**  
> <span class="simpara"> Files may be appended via the *ftp://* URL
> wrapper. </span>

### See Also

-   <a href="/context/ftp.html" class="xref">FTP context options</a>

file://
=======

Accessing local filesystem

### Description

*Filesystem* is the default wrapper used with PHP and represents the
local filesystem. When a relative path is specified (a path which does
not begin with /, \\, \\\\, or a Windows drive letter) the path provided
will be applied against the current working directory. In many cases
this is the directory in which the script resides unless it has been
changed. Using the CLI sapi, this defaults to the directory from which
the script was called.

With some functions, such as <span class="function">fopen</span> and
<span class="function">file\_get\_contents</span>, *include\_path* may
be optionally searched for relative paths as well.

### Usage

-   <span class="simpara">`/path/to/file.ext`</span>
-   <span class="simpara">`relative/path/to/file.ext`</span>
-   <span class="simpara">`fileInCwd.ext`</span>
-   <span class="simpara">`C:/path/to/winfile.ext`</span>
-   <span class="simpara">`C:\path\to\winfile.ext`</span>
-   <span class="simpara">`\\smbserver\share\path\to\winfile.ext`</span>
-   <span class="simpara">`file:///path/to/file.ext`</span>

### Options

| Attribute                                                                        | Supported |
|----------------------------------------------------------------------------------|-----------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a> | No        |
| Allows Reading                                                                   | Yes       |
| Allows Writing                                                                   | Yes       |
| Allows Appending                                                                 | Yes       |
| Allows Simultaneous Reading and Writing                                          | Yes       |
| Supports <span class="function">stat</span>                                      | Yes       |
| Supports <span class="function">unlink</span>                                    | Yes       |
| Supports <span class="function">rename</span>                                    | Yes       |
| Supports <span class="function">mkdir</span>                                     | Yes       |
| Supports <span class="function">rmdir</span>                                     | Yes       |

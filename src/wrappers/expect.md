expect://
=========

Process Interaction Streams

### Description

Streams opened via the `expect://` wrapper provide access to process'es
stdio, stdout and stderr via PTY.

> **Note**: **This wrapper is not enabled by default**  
> <span class="simpara"> In order to use the `expect://` wrapper you
> must install the
> <a href="https://pecl.php.net/package/expect" class="link external">» Expect</a>
> extension available from
> <a href="https://pecl.php.net/" class="link external">» PECL</a>.
> </span>

`expect://` (PECL)

### Usage

-   <span class="simpara">`expect://command`</span>

### Options

| Attribute                                                                        | Supported |
|----------------------------------------------------------------------------------|-----------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a> | No        |
| Allows Reading                                                                   | Yes       |
| Allows Writing                                                                   | Yes       |
| Allows Appending                                                                 | Yes       |
| Allows Simultaneous Reading and Writing                                          | No        |
| Supports <span class="function">stat</span>                                      | No        |
| Supports <span class="function">unlink</span>                                    | No        |
| Supports <span class="function">rename</span>                                    | No        |
| Supports <span class="function">mkdir</span>                                     | No        |
| Supports <span class="function">rmdir</span>                                     | No        |

### Examples

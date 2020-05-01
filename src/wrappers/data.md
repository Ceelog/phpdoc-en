data://
=======

Data (RFC 2397)

### Description

The `data:`
(<a href="http://www.faqs.org/rfcs/rfc2397" class="link external">» RFC 2397</a>)
stream wrapper is available since PHP 5.2.0.

### Usage

-   <span class="simpara">`data://text/plain;base64,`</span>

### Options

| Attribute                                                                          | Supported |
|------------------------------------------------------------------------------------|-----------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a>   | No        |
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_include</a> | Yes       |
| Allows Reading                                                                     | Yes       |
| Allows Writing                                                                     | No        |
| Allows Appending                                                                   | No        |
| Allows Simultaneous Reading and Writing                                            | No        |
| Supports <span class="function">stat</span>                                        | No        |
| Supports <span class="function">unlink</span>                                      | No        |
| Supports <span class="function">rename</span>                                      | No        |
| Supports <span class="function">mkdir</span>                                       | No        |
| Supports <span class="function">rmdir</span>                                       | No        |

### Examples

**Example \#1 Print data:// contents**

``` php
<?php
// prints "I love PHP"
echo file_get_contents('data://text/plain;base64,SSBsb3ZlIFBIUAo=');
?>
```

**Example \#2 Fetch the media type**

``` php
<?php
$fp   = fopen('data://text/plain;base64,', 'r');
$meta = stream_get_meta_data($fp);

// prints "text/plain"
echo $meta['mediatype'];
?>
```

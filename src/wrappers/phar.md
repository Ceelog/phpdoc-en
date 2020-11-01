phar://
=======

PHP Archive

### Description

The `phar://` stream wrapper. See
<a href="/phar/using.html#Using%20Phar%20Archives:%20the%20phar%20stream%20wrapper" class="link">Phar stream wrapper</a>
for a detailed description.

### Usage

-   <span class="simpara">`phar://`</span>

### Options

| Attribute                                                                          | Supported |
|------------------------------------------------------------------------------------|-----------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a>   | No        |
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_include</a> | No        |
| Allows Reading                                                                     | Yes       |
| Allows Writing                                                                     | Yes       |
| Allows Appending                                                                   | No        |
| Allows Simultaneous Reading and Writing                                            | Yes       |
| Supports <span class="function">stat</span>                                        | Yes       |
| Supports <span class="function">unlink</span>                                      | Yes       |
| Supports <span class="function">rename</span>                                      | Yes       |
| Supports <span class="function">mkdir</span>                                       | Yes       |
| Supports <span class="function">rmdir</span>                                       | Yes       |

### See Also

-   <a href="/context/phar.html" class="xref">Phar context options</a>

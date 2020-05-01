zlib://
=======

bzip2://
========

zip://
======

Compression Streams

### Description

`compress.zlib://` and `compress.bzip2://`

`zlib:` works like <span class="function">gzopen</span>, except that the
stream can be used with <span class="function">fread</span> and the
other filesystem functions. This is deprecated due to ambiguities with
filenames containing ':' characters; use `compress.zlib://` instead.

`compress.zlib://` and `compress.bzip2://` are equivalent to <span
class="function">gzopen</span> and <span class="function">bzopen</span>
respectively, and operate even on systems that do not support
fopencookie.

<a href="/book/zip.html" class="link">ZIP extension</a> registers `zip:`
wrapper. As of PHP 7.2.0 and libzip 1.2.0+, support for the passwords
for encrypted archives were added, allowing passwords to be supplied by
stream contexts. Passwords can be set using the *'password'* stream
context option.

### Usage

-   <span class="simpara">`compress.zlib://file.gz`</span>
-   <span class="simpara">`compress.bzip2://file.bz2`</span>
-   <span class="simpara">`zip://archive.zip#dir/file.txt`</span>

### Options

| Attribute                                                                        | Supported                                                        |
|----------------------------------------------------------------------------------|------------------------------------------------------------------|
| Restricted by <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a> | No                                                               |
| Allows Reading                                                                   | Yes                                                              |
| Allows Writing                                                                   | Yes (except *zip://*)                                            |
| Allows Appending                                                                 | Yes (except *zip://*)                                            |
| Allows Simultaneous Reading and Writing                                          | No                                                               |
| Supports <span class="function">stat</span>                                      | No, use the normal *file://* wrapper to stat compressed files.   |
| Supports <span class="function">unlink</span>                                    | No, use the normal *file://* wrapper to unlink compressed files. |
| Supports <span class="function">rename</span>                                    | No                                                               |
| Supports <span class="function">mkdir</span>                                     | No                                                               |
| Supports <span class="function">rmdir</span>                                     | No                                                               |

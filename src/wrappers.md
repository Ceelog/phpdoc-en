PHP comes with many built-in wrappers for various URL-style protocols
for use with the filesystem functions such as <span
class="function">fopen</span>, <span class="function">copy</span>, <span
class="function">file\_exists</span> and <span
class="function">filesize</span>. In addition to these wrappers, it is
possible to register custom wrappers using the <span
class="function">stream\_wrapper\_register</span> function.

> **Note**: <span class="simpara"> The URL syntax used to describe a
> wrapper only supports the *scheme://...* syntax. The *scheme:/* and
> *scheme:* syntaxes are not supported. </span>

**Table of Contents**

-   [file://](/wrappers/file.html) — Accessing local filesystem
-   [http://](/wrappers/http.html) — Accessing HTTP(s) URLs
-   [ftp://](/wrappers/ftp.html) — Accessing FTP(s) URLs
-   [php://](/wrappers/php.html) — Accessing various I/O streams
-   [zlib://](/wrappers/compression.html) — Compression Streams
-   [data://](/wrappers/data.html) — Data (RFC 2397)
-   [glob://](/wrappers/glob.html) — Find pathnames matching pattern
-   [phar://](/wrappers/phar.html) — PHP Archive
-   [ssh2://](/wrappers/ssh2.html) — Secure Shell 2
-   [rar://](/wrappers/rar.html) — RAR
-   [ogg://](/wrappers/audio.html) — Audio streams
-   [expect://](/wrappers/expect.html) — Process Interaction Streams

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/zlib/setup.html#Requirements)
-   [Installation](/zlib/setup.html#Installation)
-   [Runtime Configuration](/zlib/setup.html#Runtime%20Configuration)
-   [Resource Types](/zlib/setup.html#Resource%20Types)

Requirements
------------

This module uses the functions of
<a href="http://www.zlib.net/" class="link external">» zlib</a> by
Jean-loup Gailly and Mark Adler. You have to use a zlib version \>=
1.0.9 with this module. As of PHP 5.4.0 you have to use zlib \>=
1.2.0.4.

Installation
------------

Zlib support in PHP is not enabled by default. You will need to
configure PHP **--with-zlib\[=DIR\]**

The Windows version of PHP has built-in support for this extension. You
do not need to load any additional extensions in order to use these
functions.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

The zlib extension offers the option to transparently compress your
pages on-the-fly, if the requesting browser supports this. Therefore
there are three options in the
<a href="/configuration/file.html" class="link">configuration file</a>
`php.ini`.

| Name                                                                       | Default | Changeable    | Changelog |
|----------------------------------------------------------------------------|---------|---------------|-----------|
| <a href="/zlib/setup.html#" class="link">zlib.output_compression</a>       | "0"     | PHP\_INI\_ALL |           |
| <a href="/zlib/setup.html#" class="link">zlib.output_compression_level</a> | "-1"    | PHP\_INI\_ALL |           |
| <a href="/zlib/setup.html#" class="link">zlib.output_handler</a>           | ""      | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`zlib.output_compression` <span class="type">boolean</span>/<span class="type">integer</span>  
Whether to transparently compress pages. If this option is set to "On"
in `php.ini` or the Apache configuration, pages are compressed if the
browser sends an "Accept-Encoding: gzip" or "deflate" header.
"Content-Encoding: gzip" (respectively "deflate") and "Vary:
Accept-Encoding" headers are added to the output. In runtime, it can be
set only before sending any output.

This option also accepts integer values instead of boolean "On"/"Off",
using this you can set the output buffer size (default is 4KB).

> **Note**:
>
> <a href="/outcontrol/setup.html#" class="link">output_handler</a> must
> be empty if this is set 'On' ! Instead you must use
> *zlib.output\_handler*.

`zlib.output_compression_level` <span class="type">integer</span>  
Compression level used for transparent output compression. Specify a
value between 0 (no compression) to 9 (most compression). The default
value, -1, lets the server decide which level to use.

`zlib.output_handler` <span class="type">string</span>  
You cannot specify additional output handlers if
zlib.output\_compression is activated here. This setting does the same
as <a href="/outcontrol/setup.html#" class="link">output_handler</a> but
in a different order.

Resource Types
--------------

This extension defines a file pointer resource returned by <span
class="function">gzopen</span>.

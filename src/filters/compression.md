Compression Filters
-------------------

While the
<a href="/wrappers/compression.html" class="link">Compression Wrappers</a>
provide a way of creating gzip and bz2 compatible files on the local
filesystem, they do not provide a means for generalized compression over
network streams, nor do they provide a means to begin with a
non-compressed stream and transition to a compressed one. For this, a
compression filter may be applied to any stream resource at any time.

> **Note**: <span class="simpara"> Compression filters do *not* generate
> headers and trailers used by command line utilities such as *gzip*.
> They only compress and decompress the payload portions of compressed
> data streams. </span>

zlib.deflate and zlib.inflate
-----------------------------

*zlib.deflate* (compression) and *zlib.inflate* (decompression) are
implementations of the compression methods described in
<a href="http://www.faqs.org/rfcs/rfc1951" class="link external">» RFC 1951</a>.
The *deflate* filter takes up to three parameters passed as an
associative array. `level` describes the compression strength to use
(1-9). Higher numbers will generally yield smaller payloads at the cost
of additional processing time. Two special compression levels also
exist: 0 (for no compression at all), and -1 (zlib internal default --
currently 6). `window` is the base-2 log of the compression loopback
window size. Higher values (up to 15 -- 32768 bytes) yield better
compression at a cost of memory, while lower values (down to 9 -- 512
bytes) yield worse compression in a smaller memory footprint. Default
`window` size is currently **`15`**. `memory` is a scale indicating how
much work memory should be allocated. Valid values range from 1 (minimal
allocation) to 9 (maximum allocation). This memory allocation affects
speed only and does not impact the size of the generated payload.

> **Note**: <span class="simpara"> Because compression level is the most
> commonly used parameter, it may be alternatively provided as a simple
> integer value (rather than an array element). </span>

zlib.\* compression filters are available if
<a href="/ref/zlib.html" class="link">zlib</a> support is enabled.

**Example \#1 *zlib.deflate* and *zlib.inflate***

``` php
<?php
$params = array('level' => 6, 'window' => 15, 'memory' => 9);

$original_text = "This is a test.\nThis is only a test.\nThis is not an important string.\n";
echo "The original text is " . strlen($original_text) . " characters long.\n";

$fp = fopen('test.deflated', 'w');
stream_filter_append($fp, 'zlib.deflate', STREAM_FILTER_WRITE, $params);
fwrite($fp, $original_text);
fclose($fp);

echo "The compressed file is " . filesize('test.deflated') . " bytes long.\n";
echo "The original text was:\n";
/* Use readfile and zlib.inflate to decompress on the fly */
readfile('php://filter/zlib.inflate/resource=test.deflated');

/* Generates output:

The original text is 70 characters long.
The compressed file is 56 bytes long.
The original text was:
This is a test.
This is only a test.
This is not an important string.

 */
?>
```

**Example \#2 *zlib.deflate* simple**

``` php
<?php
$original_text = "This is a test.\nThis is only a test.\nThis is not an important string.\n";
echo "The original text is " . strlen($original_text) . " characters long.\n";

$fp = fopen('test.deflated', 'w');
/* Here "6" indicates compression level 6 */
stream_filter_append($fp, 'zlib.deflate', STREAM_FILTER_WRITE, 6);
fwrite($fp, $original_text);
fclose($fp);

echo "The compressed file is " . filesize('test.deflated') . " bytes long.\n";

/* Generates output:

The original text is 70 characters long.
The compressed file is 56 bytes long.

 */
?>
```

bzip2.compress and bzip2.decompress
-----------------------------------

*bzip2.compress* and *bzip2.decompress* work in the same manner as the
zlib filters described above. The *bzip2.compress* filter accepts up to
two parameters given as elements of an associative array: `blocks` is an
integer value from 1 to 9 specifying the number of 100kbyte blocks of
memory to allocate for workspace. `work` is also an integer value
ranging from 0 to 250 indicating how much effort to expend using the
normal compression method before falling back on a slower, but more
reliable method. Tuning this parameter effects only compression speed.
Neither size of compressed output nor memory usage are changed by this
setting. A work factor of 0 instructs the bzip library to use an
internal default. The *bzip2.decompress* filter only accepts one
parameter, which can be passed as either an ordinary boolean value, or
as the `small` element of an associative array. `small`, when set to a
**`true`** value, instructs the bzip library to perform decompression in
a minimal memory footprint at the cost of speed.

bzip2.\* compression filters are available if
<a href="/ref/bzip2.html" class="link">bz2</a> support is enabled.

**Example \#3 *bzip2.compress* and *bzip2.decompress***

``` php
<?php
$param = array('blocks' => 9, 'work' => 0);

echo "The original file is " . filesize('LICENSE') . " bytes long.\n";

$fp = fopen('LICENSE.compressed', 'w');
stream_filter_append($fp, 'bzip2.compress', STREAM_FILTER_WRITE, $param);
fwrite($fp, file_get_contents('LICENSE'));
fclose($fp);

echo "The compressed file is " . filesize('LICENSE.compressed') . " bytes long.\n";

/* Generates output:

The original text is 3288 characters long.
The compressed file is 1488 bytes long.

 */
?>
```

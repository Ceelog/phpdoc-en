Conversion Filters
------------------

Like the string.\* filters, the convert.\* filters perform actions
similar to their names. For more information on a given filter, refer to
the manual page for the corresponding function.

convert.base64-encode and convert.base64-decode
-----------------------------------------------

Use of these filters are equivalent to processing all stream data
through the <span class="function">base64\_encode</span> and <span
class="function">base64\_decode</span> functions respectively.
*convert.base64-encode* supports parameters given as an associative
array. If `line-length` is given, the base64 output will be split into
chunks of `line-length` characters each. If `line-break-chars` is given,
each chunk will be delimited by the characters given. These parameters
give the same effect as using <span
class="function">base64\_encode</span> with <span
class="function">chunk\_split</span>.

**Example \#1 convert.base64-encode & convert.base64-decode**

``` php
<?php
$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'convert.base64-encode');
fwrite($fp, "This is a test.\n");
fclose($fp);
/* Outputs:  VGhpcyBpcyBhIHRlc3QuCg==  */

$param = array('line-length' => 8, 'line-break-chars' => "\r\n");
$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'convert.base64-encode', STREAM_FILTER_WRITE, $param);
fwrite($fp, "This is a test.\n");
fclose($fp);
/* Outputs:  VGhpcyBp
          :  cyBhIHRl
          :  c3QuCg==  */

$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'convert.base64-decode');
fwrite($fp, "VGhpcyBpcyBhIHRlc3QuCg==");
fclose($fp);
/* Outputs:  This is a test.  */
?>
```

convert.quoted-printable-encode and convert.quoted-printable-decode
-------------------------------------------------------------------

Use of the decode version of this filter is equivalent to processing all
stream data through the <span
class="function">quoted\_printable\_decode</span> functions. There is no
function equivalent to *convert.quoted-printable-encode*.
*convert.quoted-printable-encode* supports parameters given as an
associative array. In addition to the parameters supported by
*convert.base64-encode*, *convert.quoted-printable-encode* also supports
boolean arguments `binary` and `force-encode-first`.
*convert.base64-decode* only supports the `line-break-chars` parameter
as a type-hint for stripping from the encoded payload.

**Example \#2 convert.quoted-printable-encode &
convert.quoted-printable-decode**

``` php
<?php
$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'convert.quoted-printable-encode');
fwrite($fp, "This is a test.\n");
/* Outputs:  =This is a test.=0A  */
?>
```

convert.iconv.\*
----------------

The *convert.iconv.\** filters are available, if
<a href="/book/iconv.html" class="link">iconv</a> support is enabled,
and their use is equivalent to processing all stream data with <span
class="function">iconv</span>. These filters do not support parameters,
but instead expect the input and output encodings to be given as part of
the filter name, i.e. either as
*convert.iconv.\<input-encoding\>.\<output-encoding\>* or
*convert.iconv.\<input-encoding\>/\<output-encoding\>* (both notations
are semantically equivalent).

**Example \#3 convert.iconv.\***

``` php
<?php
$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'convert.iconv.utf-16le.utf-8');
fwrite($fp, "T\0h\0i\0s\0 \0i\0s\0 \0a\0 \0t\0e\0s\0t\0.\0\n\0");
fclose($fp);
/* Outputs: This is a test. */
?>
```

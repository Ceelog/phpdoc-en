See also
<a href="/ref/recode.html" class="link">GNU Recode functions</a>.

iconv\_get\_encoding
====================

Retrieve internal configuration variables of iconv extension

### Description

<span class="type">mixed</span> <span
class="methodname">iconv\_get\_encoding</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = "all"</span></span> \] )

Retrieve internal configuration variables of iconv extension.

### Parameters

`type`  
The value of the optional `type` can be:

-   all
-   input\_encoding
-   output\_encoding
-   internal\_encoding

### Return Values

Returns the current value of the internal configuration variable if
successful or **`FALSE`** on failure.

If `type` is omitted or set to "all", <span
class="function">iconv\_get\_encoding</span> returns an array that
stores all these variables.

### Examples

**Example \#1 <span class="function">iconv\_get\_encoding</span>
example**

``` php
<pre>
<?php
iconv_set_encoding("internal_encoding", "UTF-8");
iconv_set_encoding("output_encoding", "ISO-8859-1");
var_dump(iconv_get_encoding('all'));
?>
</pre>
```

The above example will output:

    Array
    (
        [input_encoding] => ISO-8859-1
        [output_encoding] => ISO-8859-1
        [internal_encoding] => UTF-8
    )

### See Also

-   <span class="function">iconv\_set\_encoding</span>
-   <span class="function">ob\_iconv\_handler</span>

iconv\_mime\_decode\_headers
============================

Decodes multiple *MIME* header fields at once

### Description

<span class="type">array</span> <span
class="methodname">iconv\_mime\_decode\_headers</span> ( <span
class="methodparam"><span class="type">string</span>
`$encoded_headers`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$charset`<span class="initializer"> =
ini\_get("iconv.internal\_encoding")</span></span> \]\] )

Decodes multiple *MIME* header fields at once.

### Parameters

`encoded_headers`  
The encoded headers, as a string.

`mode`  
`mode` determines the behaviour in the event <span
class="function">iconv\_mime\_decode\_headers</span> encounters a
malformed *MIME* header field. You can specify any combination of the
following bitmasks.

| Value | Constant                                 | Description                                                                                                                                                                                                                                                                                                                               |
|-------|------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | ICONV\_MIME\_DECODE\_STRICT              | If set, the given header is decoded in full conformance with the standards defined in <a href="http://www.faqs.org/rfcs/rfc2047" class="link external">» RFC2047</a>. This option is disabled by default because there are a lot of broken mail user agents that don't follow the specification and don't produce correct *MIME* headers. |
| 2     | ICONV\_MIME\_DECODE\_CONTINUE\_ON\_ERROR | If set, <span class="function">iconv\_mime\_decode\_headers</span> attempts to ignore any grammatical errors and continue to process a given header.                                                                                                                                                                                      |

`charset`  
The optional `charset` parameter specifies the character set to
represent the result by. If omitted,
<a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a>
will be used.

### Return Values

Returns an associative array that holds a whole set of *MIME* header
fields specified by `encoded_headers` on success, or **`FALSE`** if an
error occurs during the decoding.

Each key of the return value represents an individual field name and the
corresponding element represents a field value. If more than one field
of the same name are present, <span
class="function">iconv\_mime\_decode\_headers</span> automatically
incorporates them into a numerically indexed array in the order of
occurrence.

### Examples

**Example \#1 <span class="function">iconv\_mime\_decode\_headers</span>
example**

``` php
<?php
$headers_string = <<<EOF
Subject: =?UTF-8?B?UHLDvGZ1bmcgUHLDvGZ1bmc=?=
To: example@example.com
Date: Thu, 1 Jan 1970 00:00:00 +0000
Message-Id: <example@example.com>
Received: from localhost (localhost [127.0.0.1]) by localhost
    with SMTP id example for <example@example.com>;
    Thu, 1 Jan 1970 00:00:00 +0000 (UTC)
    (envelope-from example-return-0000-example=example.com@example.com)
Received: (qmail 0 invoked by uid 65534); 1 Thu 2003 00:00:00 +0000

EOF;

$headers =  iconv_mime_decode_headers($headers_string, 0, "ISO-8859-1");
print_r($headers);
?>
```

The above example will output:

    Array
    (
        [Subject] => Prüfung Prüfung
        [To] => example@example.com
        [Date] => Thu, 1 Jan 1970 00:00:00 +0000
        [Message-Id] => <example@example.com>
        [Received] => Array
            (
                [0] => from localhost (localhost [127.0.0.1]) by localhost with SMTP id example for <example@example.com>; Thu, 1 Jan 1970 00:00:00 +0000 (UTC) (envelope-from example-return-0000-example=example.com@example.com)
                [1] => (qmail 0 invoked by uid 65534); 1 Thu 2003 00:00:00 +0000
            )

    )

### See Also

-   <span class="function">iconv\_mime\_decode</span>
-   <span class="function">mb\_decode\_mimeheader</span>
-   <span class="function">imap\_mime\_header\_decode</span>
-   <span class="function">imap\_base64</span>
-   <span class="function">imap\_qprint</span>

iconv\_mime\_decode
===================

Decodes a *MIME* header field

### Description

<span class="type">string</span> <span
class="methodname">iconv\_mime\_decode</span> ( <span
class="methodparam"><span class="type">string</span>
`$encoded_header`</span> \[, <span class="methodparam"><span
class="type">int</span> `$mode`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$charset`<span class="initializer"> =
ini\_get("iconv.internal\_encoding")</span></span> \]\] )

Decodes a *MIME* header field.

### Parameters

`encoded_header`  
The encoded header, as a string.

`mode`  
`mode` determines the behaviour in the event <span
class="function">iconv\_mime\_decode</span> encounters a malformed
*MIME* header field. You can specify any combination of the following
bitmasks.

| Value | Constant                                 | Description                                                                                                                                                                                                                                                                                                                               |
|-------|------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1     | ICONV\_MIME\_DECODE\_STRICT              | If set, the given header is decoded in full conformance with the standards defined in <a href="http://www.faqs.org/rfcs/rfc2047" class="link external">» RFC2047</a>. This option is disabled by default because there are a lot of broken mail user agents that don't follow the specification and don't produce correct *MIME* headers. |
| 2     | ICONV\_MIME\_DECODE\_CONTINUE\_ON\_ERROR | If set, <span class="function">iconv\_mime\_decode\_headers</span> attempts to ignore any grammatical errors and continue to process a given header.                                                                                                                                                                                      |

`charset`  
The optional `charset` parameter specifies the character set to
represent the result by. If omitted,
<a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a>
will be used.

### Return Values

Returns a decoded *MIME* field on success, or **`FALSE`** if an error
occurs during the decoding.

### Examples

**Example \#1 <span class="function">iconv\_mime\_decode</span>
example**

``` php
<?php
// This yields "Subject: Prüfung Prüfung"
echo iconv_mime_decode("Subject: =?UTF-8?B?UHLDvGZ1bmcgUHLDvGZ1bmc=?=",
                       0, "ISO-8859-1");
?>
```

### See Also

-   <span class="function">iconv\_mime\_decode\_headers</span>
-   <span class="function">mb\_decode\_mimeheader</span>
-   <span class="function">imap\_mime\_header\_decode</span>
-   <span class="function">imap\_base64</span>
-   <span class="function">imap\_qprint</span>

iconv\_mime\_encode
===================

Composes a *MIME* header field

### Description

<span class="type">string</span> <span
class="methodname">iconv\_mime\_encode</span> ( <span
class="methodparam"><span class="type">string</span>
`$field_name`</span> , <span class="methodparam"><span
class="type">string</span> `$field_value`</span> \[, <span
class="methodparam"><span class="type">array</span> `$preferences`<span
class="initializer"> = **`NULL`**</span></span> \] )

Composes and returns a string that represents a valid *MIME* header
field, which looks like the following:

    Subject: =?ISO-8859-1?Q?Pr=FCfung_f=FCr?= Entwerfen von einer MIME kopfzeile

In the above example, "Subject" is the field name and the portion that
begins with "=?ISO-8859-1?..." is the field value.

### Parameters

`field_name`  
The field name.

`field_value`  
The field value.

`preferences`  
You can control the behaviour of <span
class="function">iconv\_mime\_encode</span> by specifying an associative
array that contains configuration items to the optional third parameter
`preferences`. The items supported by <span
class="function">iconv\_mime\_encode</span> are listed below. Note that
item names are treated case-sensitive.

| Item             | Type                              | Description                                                                                                                                                                                                                                                                                                                                                                          | Default value                                                                                | Example    |
|------------------|-----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------|------------|
| scheme           | <span class="type">string</span>  | Specifies the method to encode a field value by. The value of this item may be either "B" or "Q", where "B" stands for *base64* encoding scheme and "Q" stands for *quoted-printable* encoding scheme.                                                                                                                                                                               | B                                                                                            | B          |
| input-charset    | <span class="type">string</span>  | Specifies the character set in which the first parameter `field_name` and the second parameter `field_value` are presented. If not given, <span class="function">iconv\_mime\_encode</span> assumes those parameters are presented to it in the <a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a> ini setting.                            | <a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a> | ISO-8859-1 |
| output-charset   | <span class="type">string</span>  | Specifies the character set to use to compose the *MIME* header.                                                                                                                                                                                                                                                                                                                     | <a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a> | UTF-8      |
| line-length      | <span class="type">integer</span> | Specifies the maximum length of the header lines. The resulting header is "folded" to a set of multiple lines in case the resulting header field would be longer than the value of this parameter, according to <a href="http://www.faqs.org/rfcs/rfc2822" class="link external">» RFC2822 - Internet Message Format</a>. If not given, the length will be limited to 76 characters. | 76                                                                                           | 996        |
| line-break-chars | <span class="type">string</span>  | Specifies the sequence of characters to append to each line as an end-of-line sign when "folding" is performed on a long header field. If not given, this defaults to "\\r\\n" (*CR* *LF*). Note that this parameter is always treated as an ASCII string regardless of the value of *input-charset*.                                                                                | \\r\\n                                                                                       | \\n        |

### Return Values

Returns an encoded *MIME* field on success, or **`FALSE`** if an error
occurs during the encoding.

### Examples

**Example \#1 <span class="function">iconv\_mime\_encode</span>
example**

``` php
<?php
$preferences = array(
    "input-charset" => "ISO-8859-1",
    "output-charset" => "UTF-8",
    "line-length" => 76,
    "line-break-chars" => "\n"
);
$preferences["scheme"] = "Q";
// This yields "Subject: =?UTF-8?Q?Pr=C3=BCfung=20Pr=C3=BCfung?="
echo iconv_mime_encode("Subject", "Prüfung Prüfung", $preferences);

$preferences["scheme"] = "B";
// This yields "Subject: =?UTF-8?B?UHLDvGZ1bmcgUHLDvGZ1bmc=?="
echo iconv_mime_encode("Subject", "Prüfung Prüfung", $preferences);
?>
```

### See Also

-   <span class="function">imap\_binary</span>
-   <span class="function">mb\_encode\_mimeheader</span>
-   <span class="function">imap\_8bit</span>
-   <span class="function">quoted\_printable\_encode</span>

iconv\_set\_encoding
====================

Set current setting for character encoding conversion

### Description

<span class="type">bool</span> <span
class="methodname">iconv\_set\_encoding</span> ( <span
class="methodparam"><span class="type">string</span> `$type`</span> ,
<span class="methodparam"><span class="type">string</span>
`$charset`</span> )

Changes the value of the internal configuration variable specified by
`type` to `charset`.

### Parameters

`type`  
The value of `type` can be any one of these:

-   input\_encoding
-   output\_encoding
-   internal\_encoding

`charset`  
The character set.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">iconv\_set\_encoding</span>
example**

``` php
<?php
iconv_set_encoding("internal_encoding", "UTF-8");
iconv_set_encoding("output_encoding", "ISO-8859-1");
?>
```

### See Also

-   <span class="function">iconv\_get\_encoding</span>
-   <span class="function">ob\_iconv\_handler</span>

iconv\_strlen
=============

Returns the character count of string

### Description

<span class="type">int</span> <span
class="methodname">iconv\_strlen</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$charset`<span class="initializer"> =
ini\_get("iconv.internal\_encoding")</span></span> \] )

In contrast to <span class="function">strlen</span>, <span
class="function">iconv\_strlen</span> counts the occurrences of
characters in the given byte sequence `str` on the basis of the
specified character set, the result of which is not necessarily
identical to the length of the string in byte.

### Parameters

`str`  
The string.

`charset`  
If `charset` parameter is omitted, `str` is assumed to be encoded in
<a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a>.

### Return Values

Returns the character count of `str`, as an integer.

### See Also

-   <span class="function">grapheme\_strlen</span>
-   <span class="function">mb\_strlen</span>
-   <span class="function">strlen</span>

iconv\_strpos
=============

Finds position of first occurrence of a needle within a haystack

### Description

<span class="type">int</span> <span
class="methodname">iconv\_strpos</span> ( <span
class="methodparam"><span class="type">string</span> `$haystack`</span>
, <span class="methodparam"><span class="type">string</span>
`$needle`</span> \[, <span class="methodparam"><span
class="type">int</span> `$offset`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$charset`<span class="initializer"> =
ini\_get("iconv.internal\_encoding")</span></span> \]\] )

Finds position of first occurrence of a `needle` within a `haystack`.

In contrast to <span class="function">strpos</span>, the return value of
<span class="function">iconv\_strpos</span> is the number of characters
that appear before the needle, rather than the offset in bytes to the
position where the needle has been found. The characters are counted on
the basis of the specified character set `charset`.

### Parameters

`haystack`  
The entire string.

`needle`  
The searched substring.

`offset`  
The optional `offset` parameter specifies the position from which the
search should be performed. If the offset is negative, it is counted
from the end of the string.

`charset`  
If `charset` parameter is omitted, `string` are assumed to be encoded in
<a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a>.

If `haystack` or `needle` is not a string, it is converted to a string
and applied as the ordinal value of a character.

### Return Values

Returns the numeric position of the first occurrence of `needle` in
`haystack`.

If `needle` is not found, <span class="function">iconv\_strpos</span>
will return **`FALSE`**.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Changelog

| Version | Description                                    |
|---------|------------------------------------------------|
| 7.1.0   | Support for negative `offset`s has been added. |

### See Also

-   <span class="function">strpos</span>
-   <span class="function">iconv\_strrpos</span>
-   <span class="function">mb\_strpos</span>

iconv\_strrpos
==============

Finds the last occurrence of a needle within a haystack

### Description

<span class="type">int</span> <span
class="methodname">iconv\_strrpos</span> ( <span
class="methodparam"><span class="type">string</span> `$haystack`</span>
, <span class="methodparam"><span class="type">string</span>
`$needle`</span> \[, <span class="methodparam"><span
class="type">string</span> `$charset`<span class="initializer"> =
ini\_get("iconv.internal\_encoding")</span></span> \] )

Finds the last occurrence of a `needle` within a `haystack`.

In contrast to <span class="function">strrpos</span>, the return value
of <span class="function">iconv\_strrpos</span> is the number of
characters that appear before the needle, rather than the offset in
bytes to the position where the needle has been found. The characters
are counted on the basis of the specified character set `charset`.

### Parameters

`haystack`  
The entire string.

`needle`  
The searched substring.

`charset`  
If `charset` parameter is omitted, `string` are assumed to be encoded in
<a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a>.

If `haystack` or `needle` is not a string, it is converted to a string
and applied as the ordinal value of a character.

### Return Values

Returns the numeric position of the last occurrence of `needle` in
`haystack`.

If `needle` is not found, <span class="function">iconv\_strrpos</span>
will return **`FALSE`**.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### See Also

-   <span class="function">strrpos</span>
-   <span class="function">iconv\_strpos</span>
-   <span class="function">mb\_strrpos</span>

iconv\_substr
=============

Cut out part of a string

### Description

<span class="type">string</span> <span
class="methodname">iconv\_substr</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> ,
<span class="methodparam"><span class="type">int</span> `$offset`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$length`<span class="initializer"> = iconv\_strlen($str,
$charset)</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$charset`<span class="initializer"> =
ini\_get("iconv.internal\_encoding")</span></span> \]\] )

Cuts a portion of `str` specified by the `offset` and `length`
parameters.

### Parameters

`str`  
The original string.

`offset`  
If `offset` is non-negative, <span class="function">iconv\_substr</span>
cuts the portion out of `str` beginning at `offset`'th character,
counting from zero.

If `offset` is negative, <span class="function">iconv\_substr</span>
cuts out the portion beginning at the position, `offset` characters away
from the end of `str`.

`length`  
If `length` is given and is positive, the return value will contain at
most `length` characters of the portion that begins at `offset`
(depending on the length of `string`).

If negative `length` is passed, <span
class="function">iconv\_substr</span> cuts the portion out of `str` from
the `offset`'th character up to the character that is `length`
characters away from the end of the string. In case `offset` is also
negative, the start position is calculated beforehand according to the
rule explained above.

`charset`  
If `charset` parameter is omitted, `string` are assumed to be encoded in
<a href="/iconv/setup.html#Runtime%20Configuration" class="link">iconv.internal_encoding</a>.

Note that `offset` and `length` parameters are always deemed to
represent offsets that are calculated on the basis of the character set
determined by `charset`, whilst the counterpart <span
class="function">substr</span> always takes these for byte offsets.

### Return Values

Returns the portion of `str` specified by the `offset` and `length`
parameters.

If `str` is shorter than `offset` characters long, **`FALSE`** will be
returned. If `str` is exactly `offset` characters long, an empty string
will be returned.

### Changelog

| Version | Description                                                                                                                                    |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.0.11  | If `str` is equal to `offset` characters long, an empty string will be returned. Prior to this version, **`FALSE`** was returned in this case. |

### See Also

-   <span class="function">substr</span>
-   <span class="function">mb\_substr</span>
-   <span class="function">mb\_strcut</span>

iconv
=====

Convert string to requested character encoding

### Description

<span class="type">string</span> <span class="methodname">iconv</span> (
<span class="methodparam"><span class="type">string</span>
`$in_charset`</span> , <span class="methodparam"><span
class="type">string</span> `$out_charset`</span> , <span
class="methodparam"><span class="type">string</span> `$str`</span> )

Performs a character set conversion on the string `str` from
`in_charset` to `out_charset`.

### Parameters

`in_charset`  
The input charset.

`out_charset`  
The output charset.

If you append the string *//TRANSLIT* to `out_charset` transliteration
is activated. This means that when a character can't be represented in
the target charset, it can be approximated through one or several
similarly looking characters. If you append the string *//IGNORE*,
characters that cannot be represented in the target charset are silently
discarded. Otherwise, **`E_NOTICE`** is generated and the function will
return **`FALSE`**.

**Caution**
If and how *//TRANSLIT* works exactly depends on the system's iconv()
implementation (cf. **`ICONV_IMPL`**). Some implementations are known to
ignore *//TRANSLIT*, so the conversion is likely to fail for characters
which are illegal for the `out_charset`.

`str`  
The string to be converted.

### Return Values

Returns the converted string or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                              |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.4.0   | Since this version, the function returns **`FALSE`** on illegal characters, unless *//IGNORE* is specified in output charset. Before, it returned partial output string. |

### Examples

**Example \#1 <span class="function">iconv</span> example**

``` php
<?php
$text = "This is the Euro symbol '€'.";

echo 'Original : ', $text, PHP_EOL;
echo 'TRANSLIT : ', iconv("UTF-8", "ISO-8859-1//TRANSLIT", $text), PHP_EOL;
echo 'IGNORE   : ', iconv("UTF-8", "ISO-8859-1//IGNORE", $text), PHP_EOL;
echo 'Plain    : ', iconv("UTF-8", "ISO-8859-1", $text), PHP_EOL;

?>
```

The above example will output something similar to:

    Original : This is the Euro symbol '€'.
    TRANSLIT : This is the Euro symbol 'EUR'.
    IGNORE   : This is the Euro symbol ''.
    Plain    :
    Notice: iconv(): Detected an illegal character in input string in .\iconv-example.php on line 7

ob\_iconv\_handler
==================

Convert character encoding as output buffer handler

### Description

<span class="type">string</span> <span
class="methodname">ob\_iconv\_handler</span> ( <span
class="methodparam"><span class="type">string</span> `$contents`</span>
, <span class="methodparam"><span class="type">int</span>
`$status`</span> )

Converts the string encoded in `internal_encoding` to `output_encoding`.

`internal_encoding` and `output_encoding` should be defined in the
`php.ini` file or in <span class="function">iconv\_set\_encoding</span>.

### Parameters

See <span class="function">ob\_start</span> for information about this
handler parameters.

### Return Values

See <span class="function">ob\_start</span> for information about this
handler return values.

### Examples

**Example \#1 <span class="function">ob\_iconv\_handler</span>
example:**

``` php
<?php
iconv_set_encoding("internal_encoding", "UTF-8");
iconv_set_encoding("output_encoding", "ISO-8859-1");
ob_start("ob_iconv_handler"); // start output buffering
?>
```

### See Also

-   <span class="function">iconv\_get\_encoding</span>
-   <span class="function">iconv\_set\_encoding</span>
-   <a href="/ref/outcontrol.html" class="link">output-control functions</a>

**Table of Contents**

-   [iconv\_get\_encoding](/ref/iconv.html#iconv_get_encoding) —
    Retrieve internal configuration variables of iconv extension
-   [iconv\_mime\_decode\_headers](/ref/iconv.html#iconv_mime_decode_headers)
    — Decodes multiple MIME header fields at once
-   [iconv\_mime\_decode](/ref/iconv.html#iconv_mime_decode) — Decodes a
    MIME header field
-   [iconv\_mime\_encode](/ref/iconv.html#iconv_mime_encode) — Composes
    a MIME header field
-   [iconv\_set\_encoding](/ref/iconv.html#iconv_set_encoding) — Set
    current setting for character encoding conversion
-   [iconv\_strlen](/ref/iconv.html#iconv_strlen) — Returns the
    character count of string
-   [iconv\_strpos](/ref/iconv.html#iconv_strpos) — Finds position of
    first occurrence of a needle within a haystack
-   [iconv\_strrpos](/ref/iconv.html#iconv_strrpos) — Finds the last
    occurrence of a needle within a haystack
-   [iconv\_substr](/ref/iconv.html#iconv_substr) — Cut out part of a
    string
-   [iconv](/ref/iconv.html#iconv) — Convert string to requested
    character encoding
-   [ob\_iconv\_handler](/ref/iconv.html#ob_iconv_handler) — Convert
    character encoding as output buffer handler

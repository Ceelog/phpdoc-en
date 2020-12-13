Multibyte character encoding schemes and their related issues are fairly
complicated, and are beyond the scope of this documentation. Please
refer to the following URLs and other resources for further information
regarding these topics.

-   Unicode materials

    <a href="http://www.unicode.org/" class="link external">» http://www.unicode.org/</a>

-   Japanese/Korean/Chinese character information

    <a href="https://resources.oreilly.com/examples/9781565922242/blob/master/doc/cjk.inf" class="link external">» https://resources.oreilly.com/examples/9781565922242/blob/master/doc/cjk.inf</a>

mb\_check\_encoding
===================

Check if strings are valid for the specified encoding

### Description

<span class="type">bool</span> <span
class="methodname">mb\_check\_encoding</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$value`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \]\] )

Checks if the specified byte stream is valid for the specified encoding.
If `value` is of type <span class="type">array</span>, all keys and
values are validated recursively. It is useful to prevent so-called
"Invalid Encoding Attack".

### Parameters

`value`  
The byte stream or <span class="type">array</span> to check. If it is
omitted, this function checks all the input from the beginning of the
request.

`encoding`  
The expected encoding.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                                                                                                         |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `value` and `encoding` are nullable now.                                                                                                            |
| 7.2.0   | This function now also accepts an <span class="type">array</span> as `value`. Formerly, only <span class="type">string</span>s have been supported. |

mb\_chr
=======

Get a specific character

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span class="methodname">mb\_chr</span>
( <span class="methodparam"><span class="type">int</span>
`$codepoint`</span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`codepoint`  

`encoding`  

### Return Values

Returns a specific character or **`false`** on failure.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_ord</span>
-   <span class="function">chr</span>

mb\_convert\_case
=================

Perform case folding on a string

### Description

<span class="type">string</span> <span
class="methodname">mb\_convert\_case</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> ,
<span class="methodparam"><span class="type">int</span> `$mode`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Performs case folding on a <span class="type">string</span>, converted
in the way specified by `mode`.

### Parameters

`string`  
The <span class="type">string</span> being converted.

`mode`  
The mode of the conversion. It can be one of **`MB_CASE_UPPER`**,
**`MB_CASE_LOWER`**, **`MB_CASE_TITLE`**, **`MB_CASE_FOLD`**,
**`MB_CASE_UPPER_SIMPLE`**, **`MB_CASE_LOWER_SIMPLE`**,
**`MB_CASE_TITLE_SIMPLE`**, **`MB_CASE_FOLD_SIMPLE`**.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

A case folded version of `string` converted in the way specified by
`mode`.

### Unicode

By contrast to the standard case folding functions such as <span
class="function">strtolower</span> and <span
class="function">strtoupper</span>, case folding is performed on the
basis of the Unicode character properties. Thus the behaviour of this
function is not affected by locale settings and it can convert any
characters that have 'alphabetic' property, such as A-umlaut (Ä).

For more information about the Unicode properties, please see
<a href="http://www.unicode.org/unicode/reports/tr21/" class="link external">» http://www.unicode.org/unicode/reports/tr21/</a>.

### Changelog

| Version | Description                                                                                                                                                        |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | Added support for **`MB_CASE_FOLD`**, **`MB_CASE_UPPER_SIMPLE`**, **`MB_CASE_LOWER_SIMPLE`**, **`MB_CASE_TITLE_SIMPLE`**, and **`MB_CASE_FOLD_SIMPLE`** as `mode`. |

### Examples

**Example \#1 <span class="function">mb\_convert\_case</span> example**

``` php
<?php
$str = "mary had a Little lamb and she loved it so";
$str = mb_convert_case($str, MB_CASE_UPPER, "UTF-8");
echo $str; // Prints MARY HAD A LITTLE LAMB AND SHE LOVED IT SO
$str = mb_convert_case($str, MB_CASE_TITLE, "UTF-8");
echo $str; // Prints Mary Had A Little Lamb And She Loved It So
?>
```

**Example \#2 <span class="function">mb\_convert\_case</span> example
with non-Latin UTF-8 text**

``` php
<?php
$str = "Τάχιστη αλώπηξ βαφής ψημένη γη, δρασκελίζει υπέρ νωθρού κυνός";
$str = mb_convert_case($str, MB_CASE_UPPER, "UTF-8");
echo $str; // Prints ΤΆΧΙΣΤΗ ΑΛΏΠΗΞ ΒΑΦΉΣ ΨΗΜΈΝΗ ΓΗ, ΔΡΑΣΚΕΛΊΖΕΙ ΥΠΈΡ ΝΩΘΡΟΎ ΚΥΝΌΣ
$str = mb_convert_case($str, MB_CASE_TITLE, "UTF-8");
echo $str; // Prints Τάχιστη Αλώπηξ Βαφήσ Ψημένη Γη, Δρασκελίζει Υπέρ Νωθρού Κυνόσ
?>
```

### See Also

-   <span class="function">mb\_strtolower</span>
-   <span class="function">mb\_strtoupper</span>
-   <span class="function">strtolower</span>
-   <span class="function">strtoupper</span>
-   <span class="function">ucfirst</span>
-   <span class="function">ucwords</span>

mb\_convert\_encoding
=====================

Convert character encoding

### Description

<span class="type"><span class="type">array</span><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">mb\_convert\_encoding</span> ( <span
class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span></span>
`$string`</span> , <span class="methodparam"><span
class="type">string</span> `$to_encoding`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$from_encoding`<span
class="initializer"> = **`null`**</span></span> \] )

Converts the character encoding of `string` to `to_encoding` from
optionally `from_encoding`. If `string` is an <span
class="type">array</span>, all its <span class="type">string</span>
values will be converted recursively.

### Parameters

`string`  
The <span class="type">string</span> or <span class="type">array</span>
being encoded.

`to_encoding`  
The type of encoding that `string` is being converted to.

`from_encoding`  
Is specified by character code names before conversion. It is either an
<span class="type">array</span>, or a comma separated enumerated list.
If `from_encoding` is not specified, the internal encoding will be used.

See
<a href="/mbstring/supported-encodings.html" class="link">supported encodings</a>.

### Return Values

The encoded <span class="type">string</span> or <span
class="type">array</span> on success, or **`false`** on failure.

### Changelog

| Version | Description                                                                                                                                          |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `from_encoding` is nullable now.                                                                                                                     |
| 7.2.0   | This function now also accepts an <span class="type">array</span> as `string`. Formerly, only <span class="type">string</span>s have been supported. |

### Examples

**Example \#1 <span class="function">mb\_convert\_encoding</span>
example**

``` php
<?php
/* Convert internal character encoding to SJIS */
$str = mb_convert_encoding($str, "SJIS");

/* Convert EUC-JP to UTF-7 */
$str = mb_convert_encoding($str, "UTF-7", "EUC-JP");

/* Auto detect encoding from JIS, eucjp-win, sjis-win, then convert str to UCS-2LE */
$str = mb_convert_encoding($str, "UCS-2LE", "JIS, eucjp-win, sjis-win");

/* "auto" is expanded to "ASCII,JIS,UTF-8,EUC-JP,SJIS" */
$str = mb_convert_encoding($str, "EUC-JP", "auto");
?>
```

### See Also

-   <span class="function">mb\_detect\_order</span>

mb\_convert\_kana
=================

Convert "kana" one from another ("zen-kaku", "han-kaku" and more)

### Description

<span class="type">string</span> <span
class="methodname">mb\_convert\_kana</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$mode`<span class="initializer"> = "KV"</span></span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

Performs a "han-kaku" - "zen-kaku" conversion for <span
class="type">string</span> `string`. This function is only useful for
Japanese.

### Parameters

`string`  
The <span class="type">string</span> being converted.

`mode`  
The conversion option.

Specify with a combination of following options.

| Option | Meaning                                                                                                                                                       |
|--------|---------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *r*    | Convert "zen-kaku" alphabets to "han-kaku"                                                                                                                    |
| *R*    | Convert "han-kaku" alphabets to "zen-kaku"                                                                                                                    |
| *n*    | Convert "zen-kaku" numbers to "han-kaku"                                                                                                                      |
| *N*    | Convert "han-kaku" numbers to "zen-kaku"                                                                                                                      |
| *a*    | Convert "zen-kaku" alphabets and numbers to "han-kaku"                                                                                                        |
| *A*    | Convert "han-kaku" alphabets and numbers to "zen-kaku" (Characters included in "a", "A" options are U+0021 - U+007E excluding U+0022, U+0027, U+005C, U+007E) |
| *s*    | Convert "zen-kaku" space to "han-kaku" (U+3000 -\> U+0020)                                                                                                    |
| *S*    | Convert "han-kaku" space to "zen-kaku" (U+0020 -\> U+3000)                                                                                                    |
| *k*    | Convert "zen-kaku kata-kana" to "han-kaku kata-kana"                                                                                                          |
| *K*    | Convert "han-kaku kata-kana" to "zen-kaku kata-kana"                                                                                                          |
| *h*    | Convert "zen-kaku hira-gana" to "han-kaku kata-kana"                                                                                                          |
| *H*    | Convert "han-kaku kata-kana" to "zen-kaku hira-gana"                                                                                                          |
| *c*    | Convert "zen-kaku kata-kana" to "zen-kaku hira-gana"                                                                                                          |
| *C*    | Convert "zen-kaku hira-gana" to "zen-kaku kata-kana"                                                                                                          |
| *V*    | Collapse voiced sound notation and convert them into a character. Use with "K","H"                                                                            |

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

The converted <span class="type">string</span>.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### Examples

**Example \#1 <span class="function">mb\_convert\_kana</span> example**

``` php
<?php
/* Convert all "kana" to "zen-kaku" "kata-kana" */
$str = mb_convert_kana($str, "KVC");

/* Convert "han-kaku" "kata-kana" to "zen-kaku" "kata-kana" 
   and "zen-kaku" alphanumeric to "han-kaku" */
$str = mb_convert_kana($str, "KVa");
?>
```

mb\_convert\_variables
======================

Convert character code in variable(s)

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mb\_convert\_variables</span> ( <span
class="methodparam"><span class="type">string</span>
`$to_encoding`</span> , <span class="methodparam"><span
class="type"><span class="type">array</span><span
class="type">string</span></span> `$from_encoding`</span> , <span
class="methodparam"><span class="type">mixed</span> `&$var`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`&$vars`</span> )

Converts character encoding of variables `var` and `vars` in encoding
`from_encoding` to encoding `to_encoding`.

<span class="function">mb\_convert\_variables</span> join strings in
Array or Object to detect encoding, since encoding detection tends to
fail for short strings. Therefore, it is impossible to mix encoding in
single array or object.

### Parameters

`to_encoding`  
The encoding that the <span class="type">string</span> is being
converted to.

`from_encoding`  
`from_encoding` is specified as an <span class="type">array</span> or
comma separated <span class="type">string</span>, it tries to detect
encoding from `from-coding`. When `from_encoding` is omitted,
*detect\_order* is used.

`var`  
`var` is the reference to the variable being converted. String, Array
and Object are accepted. <span
class="function">mb\_convert\_variables</span> assumes all parameters
have the same encoding.

`vars`  
Additional `var`s.

### Return Values

The character encoding before conversion for success, or **`false`** for
failure.

### Examples

**Example \#1 <span class="function">mb\_convert\_variables</span>
example**

``` php
<?php
/* Convert variables $post1, $post2 to internal encoding */
$interenc = mb_internal_encoding();
$inputenc = mb_convert_variables($interenc, "ASCII,UTF-8,SJIS-win", $post1, $post2);
?>
```

mb\_decode\_mimeheader
======================

Decode string in MIME header field

### Description

<span class="type">string</span> <span
class="methodname">mb\_decode\_mimeheader</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> )

Decodes encoded-word <span class="type">string</span> `string` in MIME
header.

### Parameters

`string`  
The <span class="type">string</span> being decoded.

### Return Values

The decoded <span class="type">string</span> in internal character
encoding.

### See Also

-   <span class="function">mb\_encode\_mimeheader</span>

mb\_decode\_numericentity
=========================

Decode HTML numeric string reference to character

### Description

<span class="type">string</span> <span
class="methodname">mb\_decode\_numericentity</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> ,
<span class="methodparam"><span class="type">array</span> `$map`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Convert numeric string reference of <span class="type">string</span>
`string` in a specified block to character.

### Parameters

`string`  
The <span class="type">string</span> being decoded.

`map`  
`map` is an <span class="type">array</span> that specifies the code area
to convert.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

`is_hex`  
This parameter is not used.

### Return Values

The converted <span class="type">string</span>.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### Examples

**Example \#1 `map` example**

``` php
<?php
$convmap = array (
   int start_code1, int end_code1, int offset1, int mask1,
   int start_code2, int end_code2, int offset2, int mask2,
   ........
   int start_codeN, int end_codeN, int offsetN, int maskN );
// Specify Unicode value for start_codeN and end_codeN
// Add offsetN to value and take bit-wise 'AND' with maskN, 
// then convert value to numeric string reference.
?>
```

**Example \#2 `map` example escapes JavaScript string**

``` php
<?php
function escape_javascript_string($str) {
  $map = [
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,0,0, // 49
          0,0,0,0,0,0,0,0,1,1,
          1,1,1,1,1,0,0,0,0,0,
          0,0,0,0,0,0,0,0,0,0,
          0,0,0,0,0,0,0,0,0,0,
          0,1,1,1,1,1,1,0,0,0, // 99
          0,0,0,0,0,0,0,0,0,0,
          0,0,0,0,0,0,0,0,0,0,
          0,0,0,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1, // 149
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1, // 199
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1,
          1,1,1,1,1,1,1,1,1,1, // 249
          1,1,1,1,1,1,1, // 255
          ];
  // Char encoding is UTF-8
  $mblen = mb_strlen($str, 'UTF-8');
  $utf32 = bin2hex(mb_convert_encoding($str, 'UTF-32', 'UTF-8'));
  for ($i=0, $encoded=''; $i < $mblen; $i++) {
      $u = substr($utf32, $i*8, 8);
      $v = base_convert($u, 16, 10);
      if ($v < 256 && $map[$v]) {
        $encoded .= '\\x'.substr($u, 6,2);
      } else if ($v == 2028) {
        $encoded .= '\\u2028';
      } else if ($v == 2029) {
        $encoded .= '\\u2029';
      } else {
        $encoded .= mb_convert_encoding(hex2bin($u), 'UTF-8', 'UTF-32');
      }
   }
   return $encoded;
}
 
// Test data
$convmap = [ 0x0, 0xffff, 0, 0xffff ];
$msg = '';
for ($i=0; $i < 1000; $i++) {
  // chr() cannot generate correct UTF-8 data larger value than 128, use mb_decode_numericentity().
  $msg .= mb_decode_numericentity('&#'.$i.';', $convmap, 'UTF-8');
}
 
// var_dump($msg);
var_dump(escape_javascript_string($msg));
```

### See Also

-   <span class="function">mb\_encode\_numericentity</span>

mb\_detect\_encoding
====================

Detect character encoding

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mb\_detect\_encoding</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$encodings`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$strict`<span class="initializer"> =
**`false`**</span></span> \]\] )

Detects character encoding in <span class="type">string</span> `string`.

### Parameters

`string`  
The <span class="type">string</span> being detected.

`encodings`  
`encodings` is list of character encoding. Encoding order may be
specified by array or comma separated list string.

If `encodings` is omitted or **`null`**, detect\_order is used.

`strict`  
`strict` specifies whether to use the strict encoding detection or not.
Default is **`false`**.

### Return Values

The detected character encoding or **`false`** if the encoding cannot be
detected from the given string.

### Examples

**Example \#1 <span class="function">mb\_detect\_encoding</span>
example**

``` php
<?php
/* Detect character encoding with current detect_order */
echo mb_detect_encoding($str);

/* "auto" is expanded according to mbstring.language */
echo mb_detect_encoding($str, "auto");

/* Specify "encodings" parameter by list separated by comma */
echo mb_detect_encoding($str, "JIS, eucjp-win, sjis-win");

/* Use array to specify "encodings" parameter  */
$ary[] = "ASCII";
$ary[] = "JIS";
$ary[] = "EUC-JP";
echo mb_detect_encoding($str, $ary);
?>
```

### See Also

-   <span class="function">mb\_detect\_order</span>

mb\_detect\_order
=================

Set/Get character encoding detection order

### Description

<span class="type"><span class="type">array</span><span
class="type">bool</span></span> <span
class="methodname">mb\_detect\_order</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \] )

Sets the automatic character encoding detection order to `encoding`.

### Parameters

`encoding`  
`encoding` is an <span class="type">array</span> or comma separated list
of character encoding. See
<a href="/mbstring/supported-encodings.html" class="link">supported encodings</a>.

If `encoding` is omitted or **`null`**, it returns the current character
encoding detection order as array.

This setting affects <span class="function">mb\_detect\_encoding</span>
and <span class="function">mb\_send\_mail</span>.

*mbstring* currently implements the following encoding detection
filters. If there is an invalid byte sequence for the following
encodings, encoding detection will fail.

<span class="simpara"> *UTF-8*, *UTF-7*, *ASCII*, *EUC-JP*,*SJIS*,
*eucJP-win*, *SJIS-win*, *JIS*, *ISO-2022-JP* </span>

For *ISO-8859-\**, *mbstring* always detects as *ISO-8859-\**.

For *UTF-16*, *UTF-32*, *UCS2* and *UCS4*, encoding detection will fail
always.

### Return Values

When setting the encoding detection order, **`true`** is returned on
success or **`false`** on failure.

When getting the encoding detection order, an ordered array of the
encodings is returned.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### Examples

**Example \#1 <span class="function">mb\_detect\_order</span> examples**

``` php
<?php
/* Set detection order by enumerated list */
mb_detect_order("eucjp-win,sjis-win,UTF-8");

/* Set detection order by array */
$ary[] = "ASCII";
$ary[] = "JIS";
$ary[] = "EUC-JP";
mb_detect_order($ary);

/* Display current detection order */
echo implode(", ", mb_detect_order());
?>
```

**Example \#2 Example showing useless detect orders**

    ; Always detect as ISO-8859-1
    detect_order = ISO-8859-1, UTF-8

    ; Always detect as UTF-8, since ASCII/UTF-7 values are 
    ; valid for UTF-8
    detect_order = UTF-8, ASCII, UTF-7

### See Also

-   <span class="function">mb\_internal\_encoding</span>
-   <span class="function">mb\_http\_input</span>
-   <span class="function">mb\_http\_output</span>
-   <span class="function">mb\_send\_mail</span>

mb\_encode\_mimeheader
======================

Encode string for MIME header

### Description

<span class="type">string</span> <span
class="methodname">mb\_encode\_mimeheader</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$charset`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$transfer_encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$newline`<span class="initializer"> =
"\\r\\n"</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$indent`<span class="initializer"> =
0</span></span> \]\]\]\] )

Encodes a given <span class="type">string</span> `string` by the MIME
header encoding scheme.

### Parameters

`string`  
The <span class="type">string</span> being encoded. Its encoding should
be same as <span class="function">mb\_internal\_encoding</span>.

`charset`  
`charset` specifies the name of the character set in which `string` is
represented in. The default value is determined by the current NLS
setting (*mbstring.language*).

`transfer_encoding`  
`transfer_encoding` specifies the scheme of MIME encoding. It should be
either *"B"* (Base64) or *"Q"* (Quoted-Printable). Falls back to *"B"*
if not given.

`newline`  
`newline` specifies the EOL (end-of-line) marker with which <span
class="function">mb\_encode\_mimeheader</span> performs line-folding (a
<a href="http://www.faqs.org/rfcs/rfc2822" class="link external">» RFC</a>
term, the act of breaking a line longer than a certain length into
multiple lines. The length is currently hard-coded to 74 characters).
Falls back to *"\\r\\n"* (CRLF) if not given.

`indent`  
Indentation of the first line (number of characters in the header before
`string`).

### Return Values

A converted version of the <span class="type">string</span> represented
in ASCII.

### Changelog

| Version | Description                                         |
|---------|-----------------------------------------------------|
| 8.0.0   | `charset` and `transfer_encoding` are nullable now. |

### Examples

**Example \#1 <span class="function">mb\_encode\_mimeheader</span>
example**

``` php
<?php
$name = ""; // kanji
$mbox = "kru";
$doma = "gtinn.mon";
$addr = mb_encode_mimeheader($name, "UTF-7", "Q") . " <" . $mbox . "@" . $doma . ">";
echo $addr;
?>
```

### Notes

> **Note**:
>
> This function isn't designed to break lines at higher-level contextual
> break points (word boundaries, etc.). This behaviour may clutter up
> the original string with unexpected spaces.

### See Also

-   <span class="function">mb\_decode\_mimeheader</span>

mb\_encode\_numericentity
=========================

Encode character to HTML numeric string reference

### Description

<span class="type">string</span> <span
class="methodname">mb\_encode\_numericentity</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> ,
<span class="methodparam"><span class="type">array</span> `$map`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type">bool</span> `$hex`<span
class="initializer"> = **`false`**</span></span> \]\] )

Converts specified character codes in <span class="type">string</span>
`string` from character code to HTML numeric character reference.

### Parameters

`string`  
The <span class="type">string</span> being encoded.

`map`  
`map` is array specifies code area to convert.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

`hex`  
Whether the returned entity reference should be in hexadecimal notation
(otherwise it is in decimal notation).

### Return Values

The converted <span class="type">string</span>.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### Examples

**Example \#1 `map` example**

``` php
<?php
$convmap = array (
 int start_code1, int end_code1, int offset1, int mask1,
 int start_code2, int end_code2, int offset2, int mask2,
 ........
 int start_codeN, int end_codeN, int offsetN, int maskN );
// Specify Unicode value for start_codeN and end_codeN
// Add offsetN to value and take bit-wise 'AND' with maskN, then
// it converts value to numeric string reference.
?>
```

**Example \#2 <span class="function">mb\_encode\_numericentity</span>
example**

``` php
<?php
/* Convert Left side of ISO-8859-1 to HTML numeric character reference */
$convmap = array(0x80, 0xff, 0, 0xff);
$str = mb_encode_numericentity($str, $convmap, "ISO-8859-1");

/* Convert user defined SJIS-win code in block 95-104 to numeric
   string reference */
$convmap = array(
       0xe000, 0xe03e, 0x1040, 0xffff,
       0xe03f, 0xe0bb, 0x1041, 0xffff,
       0xe0bc, 0xe0fa, 0x1084, 0xffff,
       0xe0fb, 0xe177, 0x1085, 0xffff,
       0xe178, 0xe1b6, 0x10c8, 0xffff,
       0xe1b7, 0xe233, 0x10c9, 0xffff,
       0xe234, 0xe272, 0x110c, 0xffff,
       0xe273, 0xe2ef, 0x110d, 0xffff,
       0xe2f0, 0xe32e, 0x1150, 0xffff,
       0xe32f, 0xe3ab, 0x1151, 0xffff );
$str = mb_encode_numericentity($str, $convmap, "sjis-win");
?>
```

### See Also

-   <span class="function">mb\_decode\_numericentity</span>

mb\_encoding\_aliases
=====================

Get aliases of a known encoding type

### Description

<span class="type">array</span> <span
class="methodname">mb\_encoding\_aliases</span> ( <span
class="methodparam"><span class="type">string</span> `$encoding`</span>
)

Returns an array of aliases for a known `encoding` type.

### Parameters

`encoding`  
The encoding type being checked, for aliases.

### Return Values

Returns a numerically indexed array of encoding aliases on success, or
**`false`** on failure

### Errors/Exceptions

Emits an **`E_WARNING`** level error if `encoding` is unknown.

### Examples

**Example \#1 <span class="function">mb\_encoding\_aliases</span>
example**

``` php
<?php
$encoding        = 'ASCII';
$known_encodings = mb_list_encodings();

if (in_array($encoding, $known_encodings)) {

    $aliases = mb_encoding_aliases($encoding);
    print_r($aliases);

} else {

    echo "Unknown ($encoding) encoding.\n";

}
?>
```

The above example will output something similar to:

    Array
    (
        [0] => ANSI_X3.4-1968
        [1] => iso-ir-6
        [2] => ANSI_X3.4-1986
        [3] => ISO_646.irv:1991
        [4] => US-ASCII
        [5] => ISO646-US
        [6] => us
        [7] => IBM367
        [8] => cp367
        [9] => csASCII
    )

### See Also

-   <span class="function">mb\_list\_encodings</span>

mb\_ereg\_match
===============

Regular expression match for multibyte string

### Description

<span class="type">bool</span> <span
class="methodname">mb\_ereg\_match</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">string</span>
`$string`</span> \[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \] )

A regular expression match for a multibyte string

### Parameters

`pattern`  
The regular expression pattern.

`string`  
The <span class="type">string</span> being evaluated.

`options`  
The search option. See <span
class="function">mb\_regex\_set\_options</span> for explanation.

### Return Values

Returns **`true`** if `string` matches the regular expression `pattern`,
**`false`** if not.

### Changelog

| Version | Description                |
|---------|----------------------------|
| 8.0.0   | `options` is nullable now. |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg</span>

mb\_ereg\_replace\_callback
===========================

Perform a regular expression search and replace with multibyte support
using a callback

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span><span class="type">null</span></span> <span
class="methodname">mb\_ereg\_replace\_callback</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$callback`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \] )

Scans `string` for matches to `pattern`, then replaces the matched text
with the output of `callback` function.

The behavior of this function is almost identical to <span
class="function">mb\_ereg\_replace</span>, except for the fact that
instead of `replacement` parameter, one should specify a `callback`.

### Parameters

`pattern`  
The regular expression pattern.

Multibyte characters may be used in `pattern`.

`callback`  
A callback that will be called and passed an array of matched elements
in the `subject` string. The callback should return the replacement
string.

You'll often need the `callback` function for a <span
class="function">mb\_ereg\_replace\_callback</span> in just one place.
In this case you can use an
<a href="/functions/anonymous.html" class="link">anonymous function</a>
to declare the callback within the call to <span
class="function">mb\_ereg\_replace\_callback</span>. By doing it this
way you have all information for the call in one place and do not
clutter the function namespace with a callback function's name not used
anywhere else.

`string`  
The <span class="type">string</span> being checked.

`options`  
The search option. See <span
class="function">mb\_regex\_set\_options</span> for explanation.

### Return Values

The resultant <span class="type">string</span> on success, or
**`false`** on error. If `string` is not valid for the current encoding,
**`null`** is returned.

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### Changelog

| Version | Description                                                             |
|---------|-------------------------------------------------------------------------|
| 8.0.0   | `options` is nullable now.                                              |
| 7.1.0   | The function checks whether `string` is valid for the current encoding. |

### Examples

**Example \#1 <span class="function">mb\_ereg\_replace\_callback</span>
example**

``` php
<?php
// this text was used in 2002
// we want to get this up to date for 2003
$text = "April fools day is 04/01/2002\n";
$text.= "Last christmas was 12/24/2001\n";
// the callback function
function next_year($matches)
{
  // as usual: $matches[0] is the complete match
  // $matches[1] the match for the first subpattern
  // enclosed in '(...)' and so on
  return $matches[1].($matches[2]+1);
}
echo mb_ereg_replace_callback(
            "(\d{2}/\d{2}/)(\d{4})",
            "next_year",
            $text);

?>
```

The above example will output:

    April fools day is 04/01/2003
    Last christmas was 12/24/2002

**Example \#2 <span class="function">mb\_ereg\_replace\_callback</span>
using anonymous function supported in PHP 5.3.0 or later**

``` php
<?php
// this text was used in 2002
// we want to get this up to date for 2003
$text = "April fools day is 04/01/2002\n";
$text.= "Last christmas was 12/24/2001\n";

echo mb_ereg_replace_callback(
            "(\d{2}/\d{2}/)(\d{4})",
            function ($matches) {
               return $matches[1].($matches[2]+1);
            },
            $text);
?>
```

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_replace</span>
-   <a href="/functions/anonymous.html" class="link">Anonymous functions</a>

mb\_ereg\_replace
=================

Replace regular expression with multibyte support

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span><span class="type">null</span></span> <span
class="methodname">mb\_ereg\_replace</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">string</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \] )

Scans `string` for matches to `pattern`, then replaces the matched text
with `replacement`

### Parameters

`pattern`  
The regular expression pattern.

Multibyte characters may be used in `pattern`.

`replacement`  
The replacement text.

`string`  
The <span class="type">string</span> being checked.

`options`  
<span class="simpara"> The search option. See <span
class="function">mb\_regex\_set\_options</span> for explanation. </span>

### Return Values

The resultant <span class="type">string</span> on success, or
**`false`** on error. If `string` is not valid for the current encoding,
**`null`** is returned.

### Changelog

| Version | Description                                                             |
|---------|-------------------------------------------------------------------------|
| 8.0.0   | `options` is nullable now.                                              |
| 7.1.0   | The function checks whether `string` is valid for the current encoding. |
| 7.1.0   | The *e* modifier has been deprecated.                                   |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

**Warning**

Never use the *e* modifier when working on untrusted input. No automatic
escaping will happen (as known from <span
class="function">preg\_replace</span>). Not taking care of this will
most likely create remote code execution vulnerabilities in your
application.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_eregi\_replace</span>

mb\_ereg\_search\_getpos
========================

Returns start point for next regular expression match

### Description

<span class="type">int</span> <span
class="methodname">mb\_ereg\_search\_getpos</span> ( <span
class="methodparam">void</span> )

Returns the start point for the next regular expression match.

### Parameters

This function has no parameters.

### Return Values

<span class="function">mb\_ereg\_search\_getpos</span> returns the point
to start regular expression match for <span
class="function">mb\_ereg\_search</span>, <span
class="function">mb\_ereg\_search\_pos</span>, <span
class="function">mb\_ereg\_search\_regs</span>. The position is
represented by bytes from the head of string.

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_search\_setpos</span>

mb\_ereg\_search\_getregs
=========================

Retrieve the result from the last multibyte regular expression match

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">mb\_ereg\_search\_getregs</span> ( <span
class="methodparam">void</span> )

Retrieve the result from the last multibyte regular expression match

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> including the sub-string of matched
part by last <span class="function">mb\_ereg\_search</span>, <span
class="function">mb\_ereg\_search\_pos</span>, <span
class="function">mb\_ereg\_search\_regs</span>. If there are some
matches, the first element will have the matched sub-string, the second
element will have the first part grouped with brackets, the third
element will have the second part grouped with brackets, and so on. It
returns **`false`** on error.

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_search\_init</span>

mb\_ereg\_search\_init
======================

Setup string and regular expression for a multibyte regular expression
match

### Description

<span class="type">bool</span> <span
class="methodname">mb\_ereg\_search\_init</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$pattern`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \]\] )

<span class="function">mb\_ereg\_search\_init</span> sets `string` and
`pattern` for a multibyte regular expression. These values are used for
<span class="function">mb\_ereg\_search</span>, <span
class="function">mb\_ereg\_search\_pos</span>, and <span
class="function">mb\_ereg\_search\_regs</span>.

### Parameters

`string`  
The search string.

`pattern`  
The search pattern.

`options`  
The search option. See <span
class="function">mb\_regex\_set\_options</span> for explanation.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                               |
|---------|-------------------------------------------|
| 8.0.0   | `pattern` and `options` are nullable now. |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_search\_regs</span>

mb\_ereg\_search\_pos
=====================

Returns position and length of a matched part of the multibyte regular
expression for a predefined multibyte string

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">mb\_ereg\_search\_pos</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$pattern`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \]\] )

Returns position and length of a matched part of the multibyte regular
expression for a predefined multibyte string

The string for match is specified by <span
class="function">mb\_ereg\_search\_init</span>. If it is not specified,
the previous one will be used.

### Parameters

`pattern`  
The search pattern.

`options`  
The search option. See <span
class="function">mb\_regex\_set\_options</span> for explanation.

### Return Values

An <span class="type">array</span> containing two elements. The first
element is the offset, in bytes, where the match begins relative to the
start of the search string, and the second element is the length in
bytes of the match.

If an error occurs, **`false`** is returned.

### Changelog

| Version | Description                               |
|---------|-------------------------------------------|
| 8.0.0   | `pattern` and `options` are nullable now. |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_search\_init</span>

mb\_ereg\_search\_regs
======================

Returns the matched part of a multibyte regular expression

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">mb\_ereg\_search\_regs</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$pattern`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \]\] )

Returns the matched part of a multibyte regular expression.

### Parameters

`pattern`  
The search pattern.

`options`  
The search option. See <span
class="function">mb\_regex\_set\_options</span> for explanation.

### Return Values

<span class="function">mb\_ereg\_search\_regs</span> executes the
multibyte regular expression match, and if there are some matched part,
it returns an <span class="type">array</span> including substring of
matched part as first element, the first grouped part with brackets as
second element, the second grouped part as third element, and so on. It
returns **`false`** on error.

### Changelog

| Version | Description                               |
|---------|-------------------------------------------|
| 8.0.0   | `pattern` and `options` are nullable now. |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_search\_init</span>

mb\_ereg\_search\_setpos
========================

Set start point of next regular expression match

### Description

<span class="type">bool</span> <span
class="methodname">mb\_ereg\_search\_setpos</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> )

<span class="function">mb\_ereg\_search\_setpos</span> sets the starting
point of a match for <span class="function">mb\_ereg\_search</span>.

### Parameters

`offset`  
The position to set. If it is negative, it counts from the end of the
string.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                    |
|---------|------------------------------------------------|
| 7.1.0   | Support for negative `offset`s has been added. |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_search\_init</span>

mb\_ereg\_search
================

Multibyte regular expression match for predefined multibyte string

### Description

<span class="type">bool</span> <span
class="methodname">mb\_ereg\_search</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$pattern`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \]\] )

Performs a multibyte regular expression match for a predefined multibyte
string.

### Parameters

`pattern`  
The search pattern.

`options`  
The search option. See <span
class="function">mb\_regex\_set\_options</span> for explanation.

### Return Values

<span class="function">mb\_ereg\_search</span> returns **`true`** if the
multibyte string matches with the regular expression, or **`false`**
otherwise. The <span class="type">string</span> for matching is set by
<span class="function">mb\_ereg\_search\_init</span>. If `pattern` is
not specified, the previous one is used.

### Changelog

| Version | Description                               |
|---------|-------------------------------------------|
| 8.0.0   | `pattern` and `options` are nullable now. |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_search\_init</span>

mb\_ereg
========

Regular expression match with multibyte support

### Description

<span class="type">bool</span> <span class="methodname">mb\_ereg</span>
( <span class="methodparam"><span class="type">string</span>
`$pattern`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$matches`<span
class="initializer"> = **`null`**</span></span> \] )

Executes the regular expression match with multibyte support.

### Parameters

`pattern`  
The search pattern.

`string`  
The search <span class="type">string</span>.

`matches`  
If matches are found for parenthesized substrings of `pattern` and the
function is called with the third argument `matches`, the matches will
be stored in the elements of the array `matches`. If no matches are
found, `matches` is set to an empty array.

`$matches[1]` will contain the substring which starts at the first left
parenthesis; `$matches[2]` will contain the substring starting at the
second, and so on. `$matches[0]` will contain a copy of the complete
string matched.

### Return Values

Returns whether `pattern` matches `string`.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                         |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function returns **`true`** on success now. Previously, it returned the byte length of the matched string if a match for `pattern` was found in `string` and `matches` was passed. If the optional parameter `matches` was not passed or the length of the matched string was *0*, this function returned *1*. |
| 7.1.0   | <span class="function">mb\_ereg</span> will now set `matches` to an empty <span class="type">array</span>, if nothing matched. Formerly, `matches` was not modified in that case.                                                                                                                                   |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_eregi</span>

mb\_eregi\_replace
==================

Replace regular expression with multibyte support ignoring case

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span><span class="type">null</span></span> <span
class="methodname">mb\_eregi\_replace</span> ( <span
class="methodparam"><span class="type">string</span> `$pattern`</span> ,
<span class="methodparam"><span class="type">string</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \] )

Scans `string` for matches to `pattern`, then replaces the matched text
with `replacement`.

### Parameters

`pattern`  
The regular expression pattern. Multibyte characters may be used. The
case will be ignored.

`replacement`  
The replacement text.

`string`  
The searched <span class="type">string</span>.

`options`  
<span class="simpara"> The search option. See <span
class="function">mb\_regex\_set\_options</span> for explanation. </span>

### Return Values

The resultant <span class="type">string</span> or **`false`** on error.
If `string` is not valid for the current encoding, **`null`** is
returned.

### Changelog

| Version | Description                                                             |
|---------|-------------------------------------------------------------------------|
| 8.0.0   | `options` is nullable now.                                              |
| 7.1.0   | The function checks whether `string` is valid for the current encoding. |
| 7.1.0   | The *e* modifier has been deprecated.                                   |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

**Warning**

Never use the *e* modifier when working on untrusted input. No automatic
escaping will happen (as known from <span
class="function">preg\_replace</span>). Not taking care of this will
most likely create remote code execution vulnerabilities in your
application.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg\_replace</span>

mb\_eregi
=========

Regular expression match ignoring case with multibyte support

### Description

<span class="type">bool</span> <span class="methodname">mb\_eregi</span>
( <span class="methodparam"><span class="type">string</span>
`$pattern`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$matches`<span
class="initializer"> = **`null`**</span></span> \] )

Executes the case insensitive regular expression match with multibyte
support.

### Parameters

`pattern`  
The regular expression pattern.

`string`  
The <span class="type">string</span> being searched.

`matches`  
If matches are found for parenthesized substrings of `pattern` and the
function is called with the third argument `matches`, the matches will
be stored in the elements of the array `matches`. If no matches are
found, `matches` is set to an empty array.

`$matches[1]` will contain the substring which starts at the first left
parenthesis; `$matches[2]` will contain the substring starting at the
second, and so on. `$matches[0]` will contain a copy of the complete
string matched.

### Return Values

Returns whether `pattern` matches `string`.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                         |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function returns **`true`** on success now. Previously, it returned the byte length of the matched string if a match for `pattern` was found in `string` and `matches` was passed. If the optional parameter `matches` was not passed or the length of the matched string was *0*, this function returned *1*. |
| 7.1.0   | <span class="function">mb\_eregi</span> will now set `matches` to an empty <span class="type">array</span>, if nothing matched. Formerly, `matches` was not modified in that case.                                                                                                                                  |

### Notes

> **Note**:
>
> The internal encoding or the character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg</span>

mb\_get\_info
=============

Get internal settings of mbstring

### Description

<span class="type"><span class="type">array</span><span
class="type">string</span><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mb\_get\_info</span> (\[ <span
class="methodparam"><span class="type">string</span> `$type`<span
class="initializer"> = "all"</span></span> \] )

<span class="function">mb\_get\_info</span> returns the internal setting
parameters of mbstring.

### Parameters

`type`  
If `type` isn't specified or is specified to "all", an <span
class="type">array</span> having the elements "internal\_encoding",
"http\_output", "http\_input", "func\_overload", "mail\_charset",
"mail\_header\_encoding", "mail\_body\_encoding" will be returned.

If `type` is specified as "http\_output", "http\_input",
"internal\_encoding", "func\_overload", the specified setting parameter
will be returned.

### Return Values

An <span class="type">array</span> of type information if `type` is not
specified, otherwise a specific `type`, or **`false`** on failure.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_http\_output</span>

mb\_http\_input
===============

Detect HTTP input character encoding

### Description

<span class="type"><span class="type">array</span><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">mb\_http\_input</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$type`<span class="initializer"> = **`null`**</span></span> \] )

Detects the HTTP input character encoding.

### Parameters

`type`  
Input string specifies the input type. *"G"* for GET, *"P"* for POST,
*"C"* for COOKIE, *"S"* for string, *"L"* for list, and *"I"* for the
whole list (will return <span class="type">array</span>). If type is
omitted, it returns the last input type processed.

### Return Values

The character encoding name, as per the `type`, or an array of character
encoding names, if `type` is *"I"*. If <span
class="function">mb\_http\_input</span> does not process specified HTTP
input, it returns **`false`**.

### Changelog

| Version | Description             |
|---------|-------------------------|
| 8.0.0   | `type` is nullable now. |

### See Also

-   <span class="function">mb\_internal\_encoding</span>
-   <span class="function">mb\_http\_output</span>
-   <span class="function">mb\_detect\_order</span>

mb\_http\_output
================

Set/Get HTTP output character encoding

### Description

<span class="type"><span class="type">string</span><span
class="type">bool</span></span> <span
class="methodname">mb\_http\_output</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Set/Get the HTTP output character encoding. Output after this function
is called will be converted from the set internal encoding to
`encoding`.

### Parameters

`encoding`  
If `encoding` is set, <span class="function">mb\_http\_output</span>
sets the HTTP output character encoding to `encoding`.

If `encoding` is omitted, <span class="function">mb\_http\_output</span>
returns the current HTTP output character encoding.

### Return Values

If `encoding` is omitted, <span class="function">mb\_http\_output</span>
returns the current HTTP output character encoding. Otherwise, Returns
**`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_internal\_encoding</span>
-   <span class="function">mb\_http\_input</span>
-   <span class="function">mb\_detect\_order</span>

mb\_internal\_encoding
======================

Set/Get internal character encoding

### Description

<span class="type"><span class="type">string</span><span
class="type">bool</span></span> <span
class="methodname">mb\_internal\_encoding</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Set/Get the internal character encoding

### Parameters

`encoding`  
`encoding` is the character encoding name used for the HTTP input
character encoding conversion, HTTP output character encoding
conversion, and the default character encoding for string functions
defined by the mbstring module. You should notice that the internal
encoding is totally different from the one for multibyte regex.

### Return Values

If `encoding` is set, then Returns **`true`** on success or **`false`**
on failure. In this case, the character encoding for multibyte regex is
NOT changed. If `encoding` is omitted, then the current character
encoding name is returned.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### Examples

**Example \#1 <span class="function">mb\_internal\_encoding</span>
example**

``` php
<?php
/* Set internal character encoding to UTF-8 */
mb_internal_encoding("UTF-8");

/* Display current internal character encoding */
echo mb_internal_encoding();
?>
```

### See Also

-   <span class="function">mb\_http\_input</span>
-   <span class="function">mb\_http\_output</span>
-   <span class="function">mb\_detect\_order</span>
-   <span class="function">mb\_regex\_encoding</span>

mb\_language
============

Set/Get current language

### Description

<span class="type"><span class="type">string</span><span
class="type">bool</span></span> <span
class="methodname">mb\_language</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$language`<span class="initializer"> = **`null`**</span></span> \] )

Set/Get the current language.

### Parameters

`language`  
Used for encoding e-mail messages. The valid languages are listed in the
following table. <span class="function">mb\_send\_mail</span> uses this
setting to encode e-mail.

| Language                  | Charset     | Encoding         | Alias     |
|---------------------------|-------------|------------------|-----------|
| German/de                 | ISO-8859-15 | Quoted-Printable | Deutsch   |
| English/en                | ISO-8859-1  | Quoted-Printable |           |
| Armenian/hy               | ArmSCII-8   | Quoted-Printable |           |
| Japanese/ja               | ISO-2022-JP | BASE64           |           |
| Korean/ko                 | ISO-2022-KR | BASE64           |           |
| neutral                   | UTF-8       | BASE64           |           |
| Russian/ru                | KOI8-R      | Quoted-Printable |           |
| Turkish/tr                | ISO-8859-9  | Quoted-Printable |           |
| Ukrainian/ua              | KOI8-U      | Quoted-Printable |           |
| uni                       | UTF-8       | BASE64           | universal |
| Simplified Chinese/zh-cn  | HZ          | BASE64           |           |
| Traditional Chinese/zh-tw | BIG-5       | BASE64           |           |

### Return Values

If `language` is set and `language` is valid, it returns **`true`**.
Otherwise, it returns **`false`**. When `language` is omitted or
**`null`**, it returns the language name as a <span
class="type">string</span>.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `language` is nullable now. |

### See Also

-   <span class="function">mb\_send\_mail</span>

mb\_list\_encodings
===================

Returns an array of all supported encodings

### Description

<span class="type">array</span> <span
class="methodname">mb\_list\_encodings</span> ( <span
class="methodparam">void</span> )

Returns an array containing all supported encodings.

### Parameters

This function has no parameters.

### Return Values

Returns a numerically indexed array.

### Errors/Exceptions

This function does not emit any errors.

### Examples

**Example \#1 <span class="function">mb\_list\_encodings</span>
example**

``` php
<?php

print_r(mb_list_encodings());

?>
```

The above example will output something similar to:

    Array
    (
        [0] => pass
        [1] => auto
        [2] => wchar
        [3] => byte2be
        [4] => byte2le
        [5] => byte4be
        [6] => byte4le
        [7] => BASE64
        [8] => UUENCODE
        [9] => HTML-ENTITIES
        [10] => Quoted-Printable
        [11] => 7bit
        [12] => 8bit
        [13] => UCS-4
        [14] => UCS-4BE
        [15] => UCS-4LE
        [16] => UCS-2
        [17] => UCS-2BE
        [18] => UCS-2LE
        [19] => UTF-32
        [20] => UTF-32BE
        [21] => UTF-32LE
        [22] => UTF-16
        [23] => UTF-16BE
        [24] => UTF-16LE
        [25] => UTF-8
        [26] => UTF-7
        [27] => UTF7-IMAP
        [28] => ASCII
        [29] => EUC-JP
        [30] => SJIS
        [31] => eucJP-win
        [32] => SJIS-win
        [33] => JIS
        [34] => ISO-2022-JP
        [35] => Windows-1252
        [36] => ISO-8859-1
        [37] => ISO-8859-2
        [38] => ISO-8859-3
        [39] => ISO-8859-4
        [40] => ISO-8859-5
        [41] => ISO-8859-6
        [42] => ISO-8859-7
        [43] => ISO-8859-8
        [44] => ISO-8859-9
        [45] => ISO-8859-10
        [46] => ISO-8859-13
        [47] => ISO-8859-14
        [48] => ISO-8859-15
        [49] => EUC-CN
        [50] => CP936
        [51] => HZ
        [52] => EUC-TW
        [53] => BIG-5
        [54] => EUC-KR
        [55] => UHC
        [56] => ISO-2022-KR
        [57] => Windows-1251
        [58] => CP866
        [59] => KOI8-R
    )

mb\_ord
=======

Get code point of character

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span class="methodname">mb\_ord</span>
( <span class="methodparam"><span class="type">string</span>
`$string`</span> \[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`string`  

`encoding`  

### Return Values

Returns a code point of character or **`false`** on failure.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_chr</span>
-   <span class="function">ord</span>

mb\_output\_handler
===================

Callback function converts character encoding in output buffer

### Description

<span class="type">string</span> <span
class="methodname">mb\_output\_handler</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> ,
<span class="methodparam"><span class="type">int</span> `$status`</span>
)

<span class="function">mb\_output\_handler</span> is <span
class="function">ob\_start</span> callback function. <span
class="function">mb\_output\_handler</span> converts characters in the
output buffer from internal character encoding to HTTP output character
encoding.

### Parameters

`string`  
The contents of the output buffer.

`status`  
The status of the output buffer.

### Return Values

The converted <span class="type">string</span>.

### Examples

**Example \#1 <span class="function">mb\_output\_handler</span>
example**

``` php
<?php
mb_http_output("UTF-8");
ob_start("mb_output_handler");
?>
```

### Notes

> **Note**:
>
> If you want to output binary data, such as an image, a Content-Type:
> header must be set using <span class="function">header</span> before
> any binary data is sent to the client (e.g. header("Content-Type:
> image/png")). If Content-Type: header is sent, output character
> encoding conversion will not be performed.
>
> Note that if 'Content-Type: text/\*' is sent, the content body is
> regarded as text; conversion will take place.

### See Also

-   <span class="function">ob\_start</span>

mb\_parse\_str
==============

Parse GET/POST/COOKIE data and set global variable

### Description

<span class="type">bool</span> <span
class="methodname">mb\_parse\_str</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> ,
<span class="methodparam"><span class="type">array</span>
`&$result`</span> )

Parses GET/POST/COOKIE data and sets global variables. Since PHP does
not provide raw POST/COOKIE data, it can only be used for GET data for
now. It parses URL encoded data, detects encoding, converts coding to
internal encoding and set values to the `result` <span
class="type">array</span> or global variables.

### Parameters

`string`  
The URL encoded data.

`result`  
An <span class="type">array</span> containing decoded and character
encoded converted values.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                                                       |
|---------|---------------------------------------------------------------------------------------------------|
| 8.0.0   | The second parameter was no longer optional.                                                      |
| 7.2.0   | Calling <span class="function">mb\_parse\_str</span> without the second parameter was deprecated. |

### See Also

-   <span class="function">mb\_detect\_order</span>
-   <span class="function">mb\_internal\_encoding</span>

mb\_preferred\_mime\_name
=========================

Get MIME charset string

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mb\_preferred\_mime\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$encoding`</span>
)

Get a MIME charset <span class="type">string</span> for a specific
encoding.

### Parameters

`encoding`  
The encoding being checked.

### Return Values

The MIME *charset* <span class="type">string</span> for character
encoding `encoding`, or **`false`** if no charset is preferred for the
given `encoding`.

### Examples

**Example \#1 <span class="function">mb\_preferred\_mime\_name</span>
example**

``` php
<?php
$outputenc = "sjis-win";
mb_http_output($outputenc);
ob_start("mb_output_handler");
header("Content-Type: text/html; charset=" . mb_preferred_mime_name($outputenc));
?>
```

mb\_regex\_encoding
===================

Set/Get character encoding for multibyte regex

### Description

<span class="type"><span class="type">string</span><span
class="type">bool</span></span> <span
class="methodname">mb\_regex\_encoding</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Set/Get character encoding for a multibyte regex.

### Parameters

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

If `encoding` is set, then Returns **`true`** on success or **`false`**
on failure. In this case, the internal character encoding is NOT
changed. If `encoding` is omitted, then the current character encoding
name for a multibyte regex is returned.

### Changelog

| Version | Description                                                     |
|---------|-----------------------------------------------------------------|
| 8.0.0   | `encoding` is nullable now.                                     |
| 5.6.0   | Default encoding is changed to UTF-8. It was EUC-JP Previously. |

### See Also

-   <span class="function">mb\_internal\_encoding</span>
-   <span class="function">mb\_ereg</span>

mb\_regex\_set\_options
=======================

Set/Get the default options for mbregex functions

### Description

<span class="type">string</span> <span
class="methodname">mb\_regex\_set\_options</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$options`<span class="initializer"> = **`null`**</span></span> \] )

Sets the default options described by `options` for multibyte regex
functions.

### Parameters

`options`  
The options to set. This is a string where each character is an option.
To set a mode, the mode character must be the last one set, however
there can only be set one mode but multiple options.

| Option | Meaning                                           |
|--------|---------------------------------------------------|
| i      | Ambiguity match on                                |
| x      | Enables extended pattern form                     |
| m      | *'.'* matches with newlines                       |
| s      | *'^'* -\> *'\\A'*, *'$'* -\> *'\\Z'*              |
| p      | Same as both the *m* and *s* options              |
| l      | Finds longest matches                             |
| n      | Ignores empty matches                             |
| e      | <span class="function">eval</span> resulting code |

| Mode | Meaning                    |
|------|----------------------------|
| j    | Java (Sun java.util.regex) |
| u    | GNU regex                  |
| g    | grep                       |
| c    | Emacs                      |
| r    | Ruby                       |
| z    | Perl                       |
| b    | POSIX Basic regex          |
| d    | POSIX Extended regex       |

### Return Values

The previous options. If `options` is omitted or **`null`**, it returns
the <span class="type">string</span> that describes the current options.

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | If the parameter `options` is given and not **`null`**, the *previous* options are returned. Formerly, the *current* options have been returned. |
| 8.0.0   | `options` is nullable now.                                                                                                                       |

### See Also

-   <span class="function">mb\_split</span>
-   <span class="function">mb\_ereg</span>
-   <span class="function">mb\_eregi</span>

mb\_scrub
=========

Description

### Description

<span class="type">string</span> <span
class="methodname">mb\_scrub</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`string`  

`encoding`  

### Return Values

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

mb\_send\_mail
==============

Send encoded mail

### Description

<span class="type">bool</span> <span
class="methodname">mb\_send\_mail</span> ( <span
class="methodparam"><span class="type">string</span> `$to`</span> ,
<span class="methodparam"><span class="type">string</span>
`$subject`</span> , <span class="methodparam"><span
class="type">string</span> `$message`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span></span>
`$additional_headers`<span class="initializer"> = \[\]</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$additional_params`<span class="initializer"> =
**`null`**</span></span> \]\] )

Sends email. Headers and messages are converted and encoded according to
the <span class="function">mb\_language</span> setting. It's a wrapper
function for <span class="function">mail</span>, so see also <span
class="function">mail</span> for details.

### Parameters

`to`  
The mail addresses being sent to. Multiple recipients may be specified
by putting a comma between each address in `to`. This parameter is not
automatically encoded.

`subject`  
The subject of the mail.

`message`  
The message of the mail.

`additional_headers` (optional)  
<span class="type">String</span> or <span class="type">array</span> to
be inserted at the end of the email header.

This is typically used to add extra headers (From, Cc, and Bcc).
Multiple extra headers should be separated with a CRLF (\\r\\n).
Validate parameter not to be injected unwanted headers by attackers.

If an <span class="type">array</span> is passed, its keys are the header
names and its values are the respective header values.

> **Note**:
>
> When sending mail, the mail *must* contain a *From* header. This can
> be set with the `additional_headers` parameter, or a default can be
> set in `php.ini`.
>
> Failing to do this will result in an error message similar to
> *Warning: mail(): "sendmail\_from" not set in php.ini or custom
> "From:" header missing*. The *From* header sets also *Return-Path*
> under Windows.

> **Note**:
>
> If messages are not received, try using a LF (\\n) only. Some Unix
> mail transfer agents (most notably
> <a href="http://cr.yp.to/qmail.html" class="link external">» qmail</a>)
> replace LF by CRLF automatically (which leads to doubling CR if CRLF
> is used). This should be a last resort, as it does not comply with
> <a href="http://www.faqs.org/rfcs/rfc2822" class="link external">» RFC 2822</a>.

`additional_params`  
`additional_params` is a MTA command line parameter. It is useful when
setting the correct Return-Path header when using sendmail.

This parameter is escaped by <span
class="function">escapeshellcmd</span> internally to prevent command
execution. <span class="function">escapeshellcmd</span> prevents command
execution, but allows to add additional parameters. For security reason,
this parameter should be validated.

Since <span class="function">escapeshellcmd</span> is applied
automatically, some characters that are allowed as email addresses by
internet RFCs cannot be used. Programs that are required to use these
characters <span class="function">mail</span> cannot be used.

The user that the webserver runs as should be added as a trusted user to
the sendmail configuration to prevent a 'X-Warning' header from being
added to the message when the envelope sender (-f) is set using this
method. For sendmail users, this file is `/etc/mail/trusted-users`.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                                             |
|---------|-----------------------------------------------------------------------------------------|
| 8.0.0   | `additional_params` is nullable now.                                                    |
| 7.2.0   | The `additional_headers` parameter now also accepts an <span class="type">array</span>. |

### See Also

-   <span class="function">mail</span>
-   <span class="function">mb\_encode\_mimeheader</span>
-   <span class="function">mb\_language</span>

mb\_split
=========

Split multibyte string using regular expression

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">mb\_split</span> ( <span class="methodparam"><span
class="type">string</span> `$pattern`</span> , <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$limit`<span class="initializer"> = -1</span></span> \] )

Split a multibyte `string` using regular expression `pattern` and
returns the result as an <span class="type">array</span>.

### Parameters

`pattern`  
The regular expression pattern.

`string`  
The <span class="type">string</span> being split.

`limit`  
<span class="simpara"> If optional parameter `limit` is specified, it
will be split in `limit` elements as maximum. </span>

### Return Values

The result as an <span class="type">array</span>, or **`false`** on
failure.

### Notes

> **Note**:
>
> The character encoding specified by <span
> class="function">mb\_regex\_encoding</span> will be used as the
> character encoding for this function by default.

### See Also

-   <span class="function">mb\_regex\_encoding</span>
-   <span class="function">mb\_ereg</span>

mb\_str\_split
==============

Given a multibyte string, return an array of its characters

### Description

<span class="type">array</span> <span
class="methodname">mb\_str\_split</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$length`<span class="initializer"> = 1</span></span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

This function will return an array of strings, it is a version of <span
class="function">str\_split</span> with support for encodings of
variable character size as well as fixed-size encodings of 1,2 or 4 byte
characters. If the `length` parameter is specified, the string is broken
down into chunks of the specified length in characters (not bytes). The
`encoding` parameter can be optionally specified and it is good practice
to do so.

### Parameters

`string`  
The <span class="type">string</span> to split into characters or chunks.

`length`  
If specified, each element of the returned array will be composed of
multiple characters instead of a single character.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

A string specifying one of the supported encodings.

### Return Values

<span class="function">mb\_str\_split</span> returns an array of
strings.

### Changelog

| Version | Description                                             |
|---------|---------------------------------------------------------|
| 8.0.0   | `encoding` is nullable now.                             |
| 8.0.0   | This function no longer returns **`false`** on failure. |

### See Also

-   <span class="function">str\_split</span>

mb\_strcut
==========

Get part of string

### Description

<span class="type">string</span> <span
class="methodname">mb\_strcut</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> , <span
class="methodparam"><span class="type">int</span> `$start`</span> \[,
<span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">null</span></span>
`$length`<span class="initializer"> = **`null`**</span></span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

<span class="function">mb\_strcut</span> extracts a substring from a
string similarly to <span class="function">mb\_substr</span>, but
operates on bytes instead of characters. If the cut position happens to
be between two bytes of a multi-byte character, the cut is performed
starting from the first byte of that character. This is also the
difference to the <span class="function">substr</span> function, which
would simply cut the string between the bytes and thus result in a
malformed byte sequence.

### Parameters

`string`  
The <span class="type">string</span> being cut.

`start`  
If `start` is non-negative, the returned string will start at the
`start`'th *byte* position in `string`, counting from zero. For
instance, in the string '*abcdef*', the byte at position *0* is '*a*',
the byte at position *2* is '*c*', and so forth.

If `start` is negative, the returned string will start at the `start`'th
byte counting back from the end of `string`. However, if the magnitude
of a negative `start` is greater than the length of the string, the
returned portion will start from the beginning of `string`.

`length`  
Length in *bytes*. If omitted or *NULL* is passed, extract all bytes to
the end of the string.

If `length` is negative, the returned string will end at the `length`'th
byte counting back from the end of `string`. However, if the magnitude
of a negative `length` is greater than the number of characters after
the `start` position, an empty string will be returned.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

<span class="function">mb\_strcut</span> returns the portion of `string`
specified by the `start` and `length` parameters.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_substr</span>
-   <span class="function">mb\_internal\_encoding</span>

mb\_strimwidth
==============

Get truncated string with specified width

### Description

<span class="type">string</span> <span
class="methodname">mb\_strimwidth</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span> ,
<span class="methodparam"><span class="type">int</span> `$start`</span>
, <span class="methodparam"><span class="type">int</span>
`$width`</span> \[, <span class="methodparam"><span
class="type">string</span> `$trim_marker`<span class="initializer"> =
""</span></span> \[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

Truncates <span class="type">string</span> `string` to specified
`width`.

### Parameters

`string`  
The <span class="type">string</span> being decoded.

`start`  
The start position offset. Number of characters from the beginning of
string (first character is 0), or if start is negative, number of
characters from the end of the string.

`width`  
The width of the desired trim. Negative widths count from the end of the
string.

`trim_marker`  
A string that is added to the end of string when string is truncated.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

The truncated <span class="type">string</span>. If `trim_marker` is set,
`trim_marker` replaces the last chars to match the `width`.

### Changelog

| Version | Description                                                |
|---------|------------------------------------------------------------|
| 8.0.0   | `encoding` is nullable now.                                |
| 7.1.0   | Support for negative `start`s and `width`s has been added. |

### Examples

**Example \#1 <span class="function">mb\_strimwidth</span> example**

``` php
<?php
echo mb_strimwidth("Hello World", 0, 10, "...");
// output: "Hello W..."
?>
```

### See Also

-   <span class="function">mb\_strwidth</span>
-   <span class="function">mb\_internal\_encoding</span>

mb\_stripos
===========

Finds position of first occurrence of a string within another, case
insensitive

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mb\_stripos</span> ( <span class="methodparam"><span
class="type">string</span> `$haystack`</span> , <span
class="methodparam"><span class="type">string</span> `$needle`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$offset`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

<span class="function">mb\_stripos</span> returns the numeric position
of the first occurrence of `needle` in the `haystack` string. Unlike
<span class="function">mb\_strpos</span>, <span
class="function">mb\_stripos</span> is case-insensitive. If `needle` is
not found, it returns **`false`**.

### Parameters

`haystack`  
The string from which to get the position of the first occurrence of
`needle`

`needle`  
The string to find in `haystack`

`offset`  
The position in `haystack` to start searching. A negative offset counts
from the end of the string.

`encoding`  
Character encoding name to use. If it is omitted, internal character
encoding is used.

### Return Values

Return the numeric position of the first occurrence of `needle` in the
`haystack` string, or **`false`** if `needle` is not found.

### Changelog

| Version | Description                                    |
|---------|------------------------------------------------|
| 8.0.0   | `encoding` is nullable now.                    |
| 7.1.0   | Support for negative `offset`s has been added. |

### See Also

-   <span class="function">stripos</span>
-   <span class="function">strpos</span>
-   <span class="function">mb\_strpos</span>

mb\_stristr
===========

Finds first occurrence of a string within another, case insensitive

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mb\_stristr</span> ( <span class="methodparam"><span
class="type">string</span> `$haystack`</span> , <span
class="methodparam"><span class="type">string</span> `$needle`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$before_needle`<span class="initializer"> = **`false`**</span></span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

<span class="function">mb\_stristr</span> finds the first occurrence of
`needle` in `haystack` and returns the portion of `haystack`. Unlike
<span class="function">mb\_strstr</span>, <span
class="function">mb\_stristr</span> is case-insensitive. If `needle` is
not found, it returns **`false`**.

### Parameters

`haystack`  
The string from which to get the first occurrence of `needle`

`needle`  
The string to find in `haystack`

`before_needle`  
Determines which portion of `haystack` this function returns. If set to
**`true`**, it returns all of `haystack` from the beginning to the first
occurrence of `needle` (excluding needle). If set to **`false`**, it
returns all of `haystack` from the first occurrence of `needle` to the
end (including needle).

`encoding`  
Character encoding name to use. If it is omitted, internal character
encoding is used.

### Return Values

Returns the portion of `haystack`, or **`false`** if `needle` is not
found.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">stristr</span>
-   <span class="function">strstr</span>
-   <span class="function">mb\_strstr</span>

mb\_strlen
==========

Get string length

### Description

<span class="type">int</span> <span class="methodname">mb\_strlen</span>
( <span class="methodparam"><span class="type">string</span>
`$string`</span> \[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Gets the length of a <span class="type">string</span>.

### Parameters

`string`  
The <span class="type">string</span> being checked for length.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

Returns the number of characters in <span class="type">string</span>
`string` having character encoding `encoding`. A multi-byte character is
counted as 1.

### Errors/Exceptions

If the encoding is unknown, an error of level **`E_WARNING`** is
generated.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_internal\_encoding</span>
-   <span class="function">grapheme\_strlen</span>
-   <span class="function">iconv\_strlen</span>
-   <span class="function">strlen</span>

mb\_strpos
==========

Find position of first occurrence of string in a string

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mb\_strpos</span> ( <span class="methodparam"><span
class="type">string</span> `$haystack`</span> , <span
class="methodparam"><span class="type">string</span> `$needle`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$offset`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

Finds position of the first occurrence of a <span
class="type">string</span> in a <span class="type">string</span>.

Performs a multi-byte safe <span class="function">strpos</span>
operation based on number of characters. The first character's position
is 0, the second character position is 1, and so on.

### Parameters

`haystack`  
The <span class="type">string</span> being checked.

`needle`  
The string to find in `haystack`. In contrast with <span
class="function">strpos</span>, numeric values are not applied as the
ordinal value of a character.

`offset`  
The search offset. If it is not specified, 0 is used. A negative offset
counts from the end of the string.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

Returns the numeric position of the first occurrence of `needle` in the
`haystack` <span class="type">string</span>. If `needle` is not found,
it returns **`false`**.

### Changelog

| Version | Description                                    |
|---------|------------------------------------------------|
| 8.0.0   | `encoding` is nullable now.                    |
| 7.1.0   | Support for negative `offset`s has been added. |

### See Also

-   <span class="function">mb\_internal\_encoding</span>
-   <span class="function">strpos</span>

mb\_strrchr
===========

Finds the last occurrence of a character in a string within another

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mb\_strrchr</span> ( <span class="methodparam"><span
class="type">string</span> `$haystack`</span> , <span
class="methodparam"><span class="type">string</span> `$needle`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$before_needle`<span class="initializer"> = **`false`**</span></span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

<span class="function">mb\_strrchr</span> finds the last occurrence of
`needle` in `haystack` and returns the portion of `haystack`. If
`needle` is not found, it returns **`false`**.

### Parameters

`haystack`  
The string from which to get the last occurrence of `needle`

`needle`  
The string to find in `haystack`

`before_needle`  
Determines which portion of `haystack` this function returns. If set to
**`true`**, it returns all of `haystack` from the beginning to the last
occurrence of `needle`. If set to **`false`**, it returns all of
`haystack` from the last occurrence of `needle` to the end,

`encoding`  
Character encoding name to use. If it is omitted, internal character
encoding is used.

### Return Values

Returns the portion of `haystack`. or **`false`** if `needle` is not
found.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">strrchr</span>
-   <span class="function">mb\_strstr</span>
-   <span class="function">mb\_strrichr</span>

mb\_strrichr
============

Finds the last occurrence of a character in a string within another,
case insensitive

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mb\_strrichr</span> ( <span class="methodparam"><span
class="type">string</span> `$haystack`</span> , <span
class="methodparam"><span class="type">string</span> `$needle`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$before_needle`<span class="initializer"> = **`false`**</span></span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

<span class="function">mb\_strrichr</span> finds the last occurrence of
`needle` in `haystack` and returns the portion of `haystack`. Unlike
<span class="function">mb\_strrchr</span>, <span
class="function">mb\_strrichr</span> is case-insensitive. If `needle` is
not found, it returns **`false`**.

### Parameters

`haystack`  
The string from which to get the last occurrence of `needle`

`needle`  
The string to find in `haystack`

`before_needle`  
Determines which portion of `haystack` this function returns. If set to
**`true`**, it returns all of `haystack` from the beginning to the last
occurrence of `needle`. If set to **`false`**, it returns all of
`haystack` from the last occurrence of `needle` to the end,

`encoding`  
Character encoding name to use. If it is omitted, internal character
encoding is used.

### Return Values

Returns the portion of `haystack`. or **`false`** if `needle` is not
found.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_stristr</span>
-   <span class="function">mb\_strrchr</span>

mb\_strripos
============

Finds position of last occurrence of a string within another, case
insensitive

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mb\_strripos</span> ( <span class="methodparam"><span
class="type">string</span> `$haystack`</span> , <span
class="methodparam"><span class="type">string</span> `$needle`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$offset`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

<span class="function">mb\_strripos</span> performs multi-byte safe
<span class="function">strripos</span> operation based on number of
characters. `needle` position is counted from the beginning of
`haystack`. First character's position is 0. Second character position
is 1. Unlike <span class="function">mb\_strrpos</span>, <span
class="function">mb\_strripos</span> is case-insensitive.

### Parameters

`haystack`  
The string from which to get the position of the last occurrence of
`needle`

`needle`  
The string to find in `haystack`

`offset`  
The position in `haystack` to start searching

`encoding`  
Character encoding name to use. If it is omitted, internal character
encoding is used.

### Return Values

Return the numeric position of the last occurrence of `needle` in the
`haystack` string, or **`false`** if `needle` is not found.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">strripos</span>
-   <span class="function">strrpos</span>
-   <span class="function">mb\_strrpos</span>

mb\_strrpos
===========

Find position of last occurrence of a string in a string

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mb\_strrpos</span> ( <span class="methodparam"><span
class="type">string</span> `$haystack`</span> , <span
class="methodparam"><span class="type">string</span> `$needle`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$offset`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

Performs a multibyte safe <span class="function">strrpos</span>
operation based on the number of characters. `needle` position is
counted from the beginning of `haystack`. First character's position is
0. Second character position is 1.

### Parameters

`haystack`  
The <span class="type">string</span> being checked, for the last
occurrence of `needle`

`needle`  
The <span class="type">string</span> to find in `haystack`.

`offset`  
<span class="simpara"> May be specified to begin searching an arbitrary
number of characters into the <span class="type">string</span>. Negative
values will stop searching at an arbitrary point prior to the end of the
<span class="type">string</span>. </span>

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

Returns the numeric position of the last occurrence of `needle` in the
`haystack` <span class="type">string</span>. If `needle` is not found,
it returns **`false`**.

### Notes

> **Note**: <span class="simpara"> The `encoding` parameter was moved
> from the third position to the fourth in PHP 5.2.0. For backward
> compatibility, `encoding` can be specified as the third parameter, but
> doing so is deprecated and will be removed in the future. </span>

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_strpos</span>
-   <span class="function">mb\_internal\_encoding</span>
-   <span class="function">strrpos</span>

mb\_strstr
==========

Finds first occurrence of a string within another

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mb\_strstr</span> ( <span class="methodparam"><span
class="type">string</span> `$haystack`</span> , <span
class="methodparam"><span class="type">string</span> `$needle`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$before_needle`<span class="initializer"> = **`false`**</span></span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

<span class="function">mb\_strstr</span> finds the first occurrence of
`needle` in `haystack` and returns the portion of `haystack`. If
`needle` is not found, it returns **`false`**.

### Parameters

`haystack`  
The string from which to get the first occurrence of `needle`

`needle`  
The string to find in `haystack`

`before_needle`  
Determines which portion of `haystack` this function returns. If set to
**`true`**, it returns all of `haystack` from the beginning to the first
occurrence of `needle` (excluding needle). If set to **`false`**, it
returns all of `haystack` from the first occurrence of `needle` to the
end (including needle).

`encoding`  
Character encoding name to use. If it is omitted, internal character
encoding is used.

### Return Values

Returns the portion of `haystack`, or **`false`** if `needle` is not
found.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">stristr</span>
-   <span class="function">strstr</span>
-   <span class="function">mb\_stristr</span>

mb\_strtolower
==============

Make a string lowercase

### Description

<span class="type">string</span> <span
class="methodname">mb\_strtolower</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Returns `string` with all alphabetic characters converted to lowercase.

### Parameters

`string`  
The <span class="type">string</span> being lowercased.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

`string` with all alphabetic characters converted to lowercase.

### Unicode

For more information about the Unicode properties, please see
<a href="http://www.unicode.org/unicode/reports/tr21/" class="link external">» http://www.unicode.org/unicode/reports/tr21/</a>.

By contrast to <span class="function">strtolower</span>, 'alphabetic' is
determined by the Unicode character properties. Thus the behaviour of
this function is not affected by locale settings and it can convert any
characters that have 'alphabetic' property, such as A-umlaut (Ä).

### Examples

**Example \#1 <span class="function">mb\_strtolower</span> example**

``` php
<?php
$str = "Mary Had A Little Lamb and She LOVED It So";
$str = mb_strtolower($str);
echo $str; // Prints mary had a little lamb and she loved it so
?>
```

**Example \#2 <span class="function">mb\_strtolower</span> example with
non-Latin UTF-8 text**

``` php
<?php
$str = "Τάχιστη αλώπηξ βαφής ψημένη γη, δρασκελίζει υπέρ νωθρού κυνός";
$str = mb_strtolower($str, 'UTF-8');
echo $str; // Prints τάχιστη αλώπηξ βαφής ψημένη γη, δρασκελίζει υπέρ νωθρού κυνός
?>
```

### See Also

-   <span class="function">mb\_strtoupper</span>
-   <span class="function">mb\_convert\_case</span>
-   <span class="function">strtolower</span>

mb\_strtoupper
==============

Make a string uppercase

### Description

<span class="type">string</span> <span
class="methodname">mb\_strtoupper</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Returns `string` with all alphabetic characters converted to uppercase.

### Parameters

`string`  
The <span class="type">string</span> being uppercased.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

`string` with all alphabetic characters converted to uppercase.

### Unicode

For more information about the Unicode properties, please see
<a href="http://www.unicode.org/unicode/reports/tr21/" class="link external">» http://www.unicode.org/unicode/reports/tr21/</a>.

By contrast to <span class="function">strtoupper</span>, 'alphabetic' is
determined by the Unicode character properties. Thus the behaviour of
this function is not affected by locale settings and it can convert any
characters that have 'alphabetic' property, such as a-umlaut (ä).

### Examples

**Example \#1 <span class="function">mb\_strtoupper</span> example**

``` php
<?php
$str = "Mary Had A Little Lamb and She LOVED It So";
$str = mb_strtoupper($str);
echo $str; // Prints MARY HAD A LITTLE LAMB AND SHE LOVED IT SO
?>
```

**Example \#2 <span class="function">mb\_strtoupper</span> example with
non-Latin UTF-8 text**

``` php
<?php
$str = "Τάχιστη αλώπηξ βαφής ψημένη γη, δρασκελίζει υπέρ νωθρού κυνός";
$str = mb_strtoupper($str, 'UTF-8');
echo $str; // Prints ΤΆΧΙΣΤΗ ΑΛΏΠΗΞ ΒΑΦΉΣ ΨΗΜΈΝΗ ΓΗ, ΔΡΑΣΚΕΛΊΖΕΙ ΥΠΈΡ ΝΩΘΡΟΎ ΚΥΝΌΣ
?>
```

### See Also

-   <span class="function">mb\_strtolower</span>
-   <span class="function">mb\_convert\_case</span>
-   <span class="function">strtoupper</span>

mb\_strwidth
============

Return width of string

### Description

<span class="type">int</span> <span
class="methodname">mb\_strwidth</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Returns the width of <span class="type">string</span> `string`, where
halfwidth characters count as *1*, and fullwidth characters count as
*2*.

The fullwidth characters are: *U+1100*-*U+115F*, *U+11A3*-*U+11A7*,
*U+11FA*-*U+11FF*, *U+2329*-*U+232A*, *U+2E80*-*U+2E99*,
*U+2E9B*-*U+2EF3*, *U+2F00*-*U+2FD5*, *U+2FF0*-*U+2FFB*,
*U+3000*-*U+303E*, *U+3041*-*U+3096*, *U+3099*-*U+30FF*,
*U+3105*-*U+312D*, *U+3131*-*U+318E*, *U+3190*-*U+31BA*,
*U+31C0*-*U+31E3*, *U+31F0*-*U+321E*, *U+3220*-*U+3247*,
*U+3250*-*U+32FE*, *U+3300*-*U+4DBF*, *U+4E00*-*U+A48C*,
*U+A490*-*U+A4C6*, *U+A960*-*U+A97C*, *U+AC00*-*U+D7A3*,
*U+D7B0*-*U+D7C6*, *U+D7CB*-*U+D7FB*, *U+F900*-*U+FAFF*,
*U+FE10*-*U+FE19*, *U+FE30*-*U+FE52*, *U+FE54*-*U+FE66*,
*U+FE68*-*U+FE6B*, *U+FF01*-*U+FF60*, *U+FFE0*-*U+FFE6*,
*U+1B000*-*U+1B001*, *U+1F200*-*U+1F202*, *U+1F210*-*U+1F23A*,
*U+1F240*-*U+1F248*, *U+1F250*-*U+1F251*, *U+20000*-*U+2FFFD*,
*U+30000*-*U+3FFFD*. All other characters are halfwidth characters.

### Parameters

`string`  
The <span class="type">string</span> being decoded.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

The width of <span class="type">string</span> `string`.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_strimwidth</span>
-   <span class="function">mb\_internal\_encoding</span>

mb\_substitute\_character
=========================

Set/Get substitution character

### Description

<span class="type"><span class="type">string</span><span
class="type">int</span><span class="type">bool</span></span> <span
class="methodname">mb\_substitute\_character</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">int</span><span
class="type">null</span></span> `$substitute_character`<span
class="initializer"> = **`null`**</span></span> \] )

Specifies a substitution character when input character encoding is
invalid or character code does not exist in output character encoding.
Invalid characters may be substituted *"none"* (no output), <span
class="type">string</span> or <span class="type">int</span> value
(Unicode character code value).

This setting affects <span
class="function">mb\_convert\_encoding</span>, <span
class="function">mb\_convert\_variables</span>, <span
class="function">mb\_output\_handler</span>, and <span
class="function">mb\_send\_mail</span>.

### Parameters

`substitute_character`  
Specify the Unicode value as an <span class="type">int</span>, or as one
of the following <span class="type">string</span>s:

-   <span class="simpara"> *"none"*: no output </span>
-   <span class="simpara"> *"long"*: Output character code value
    (Example: *U+3000*, *JIS+7E7E*) </span>
-   <span class="simpara"> *"entity"*: Output character entity (Example:
    *&\#x200;*) </span>

### Return Values

If `substitute_character` is set, it returns **`true`** for success,
otherwise returns **`false`**. If `substitute_character` is not set, it
returns the current setting.

### Changelog

| Version | Description                                                                                                  |
|---------|--------------------------------------------------------------------------------------------------------------|
| 8.0.0   | Passing an empty string to `substitute_character` is no longer supported; *"none"* should be passed instead. |
| 8.0.0   | `encoding` is nullable now.                                                                                  |

### Examples

**Example \#1 <span class="function">mb\_substitute\_character</span>
example**

``` php
<?php
/* Set with Unicode U+3013 (GETA MARK) */
mb_substitute_character(0x3013);

/* Set hex format */
mb_substitute_character("long");

/* Display current setting */
echo mb_substitute_character();
?>
```

mb\_substr\_count
=================

Count the number of substring occurrences

### Description

<span class="type">int</span> <span
class="methodname">mb\_substr\_count</span> ( <span
class="methodparam"><span class="type">string</span> `$haystack`</span>
, <span class="methodparam"><span class="type">string</span>
`$needle`</span> \[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \] )

Counts the number of times the `needle` substring occurs in the
`haystack` <span class="type">string</span>.

### Parameters

`haystack`  
The <span class="type">string</span> being checked.

`needle`  
The <span class="type">string</span> being found.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

The number of times the `needle` substring occurs in the `haystack`
<span class="type">string</span>.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### Examples

**Example \#1 <span class="function">mb\_substr\_count</span> example**

``` php
<?php
echo mb_substr_count("This is a test", "is"); // prints out 2
?>
```

### See Also

-   <span class="function">mb\_strpos</span>
-   <span class="function">mb\_substr</span>
-   <span class="function">substr\_count</span>

mb\_substr
==========

Get part of string

### Description

<span class="type">string</span> <span
class="methodname">mb\_substr</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> , <span
class="methodparam"><span class="type">int</span> `$start`</span> \[,
<span class="methodparam"><span class="type"><span
class="type">int</span><span class="type">null</span></span>
`$length`<span class="initializer"> = **`null`**</span></span> \[, <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`null`**</span></span> \]\] )

Performs a multi-byte safe <span class="function">substr</span>
operation based on number of characters. Position is counted from the
beginning of `string`. First character's position is 0. Second character
position is 1, and so on.

### Parameters

`string`  
The <span class="type">string</span> to extract the substring from.

`start`  
If `start` is non-negative, the returned string will start at the
`start`'th position in `string`, counting from zero. For instance, in
the string '*abcdef*', the character at position *0* is '*a*', the
character at position *2* is '*c*', and so forth.

If `start` is negative, the returned string will start at the `start`'th
character from the end of `string`.

`length`  
Maximum number of characters to use from `string`. If omitted or *NULL*
is passed, extract all characters to the end of the string.

`encoding`  
The `encoding` parameter is the character encoding. If it is omitted or
**`null`**, the internal character encoding value will be used.

### Return Values

<span class="function">mb\_substr</span> returns the portion of `string`
specified by the `start` and `length` parameters.

### Changelog

| Version | Description                 |
|---------|-----------------------------|
| 8.0.0   | `encoding` is nullable now. |

### See Also

-   <span class="function">mb\_strcut</span>
-   <span class="function">mb\_internal\_encoding</span>

**Table of Contents**

-   [mb\_check\_encoding](/ref/mbstring.html#mb_check_encoding) — Check
    if strings are valid for the specified encoding
-   [mb\_chr](/ref/mbstring.html#mb_chr) — Get a specific character
-   [mb\_convert\_case](/ref/mbstring.html#mb_convert_case) — Perform
    case folding on a string
-   [mb\_convert\_encoding](/ref/mbstring.html#mb_convert_encoding) —
    Convert character encoding
-   [mb\_convert\_kana](/ref/mbstring.html#mb_convert_kana) — Convert
    "kana" one from another ("zen-kaku", "han-kaku" and more)
-   [mb\_convert\_variables](/ref/mbstring.html#mb_convert_variables) —
    Convert character code in variable(s)
-   [mb\_decode\_mimeheader](/ref/mbstring.html#mb_decode_mimeheader) —
    Decode string in MIME header field
-   [mb\_decode\_numericentity](/ref/mbstring.html#mb_decode_numericentity)
    — Decode HTML numeric string reference to character
-   [mb\_detect\_encoding](/ref/mbstring.html#mb_detect_encoding) —
    Detect character encoding
-   [mb\_detect\_order](/ref/mbstring.html#mb_detect_order) — Set/Get
    character encoding detection order
-   [mb\_encode\_mimeheader](/ref/mbstring.html#mb_encode_mimeheader) —
    Encode string for MIME header
-   [mb\_encode\_numericentity](/ref/mbstring.html#mb_encode_numericentity)
    — Encode character to HTML numeric string reference
-   [mb\_encoding\_aliases](/ref/mbstring.html#mb_encoding_aliases) —
    Get aliases of a known encoding type
-   [mb\_ereg\_match](/ref/mbstring.html#mb_ereg_match) — Regular
    expression match for multibyte string
-   [mb\_ereg\_replace\_callback](/ref/mbstring.html#mb_ereg_replace_callback)
    — Perform a regular expression search and replace with multibyte
    support using a callback
-   [mb\_ereg\_replace](/ref/mbstring.html#mb_ereg_replace) — Replace
    regular expression with multibyte support
-   [mb\_ereg\_search\_getpos](/ref/mbstring.html#mb_ereg_search_getpos)
    — Returns start point for next regular expression match
-   [mb\_ereg\_search\_getregs](/ref/mbstring.html#mb_ereg_search_getregs)
    — Retrieve the result from the last multibyte regular expression
    match
-   [mb\_ereg\_search\_init](/ref/mbstring.html#mb_ereg_search_init) —
    Setup string and regular expression for a multibyte regular
    expression match
-   [mb\_ereg\_search\_pos](/ref/mbstring.html#mb_ereg_search_pos) —
    Returns position and length of a matched part of the multibyte
    regular expression for a predefined multibyte string
-   [mb\_ereg\_search\_regs](/ref/mbstring.html#mb_ereg_search_regs) —
    Returns the matched part of a multibyte regular expression
-   [mb\_ereg\_search\_setpos](/ref/mbstring.html#mb_ereg_search_setpos)
    — Set start point of next regular expression match
-   [mb\_ereg\_search](/ref/mbstring.html#mb_ereg_search) — Multibyte
    regular expression match for predefined multibyte string
-   [mb\_ereg](/ref/mbstring.html#mb_ereg) — Regular expression match
    with multibyte support
-   [mb\_eregi\_replace](/ref/mbstring.html#mb_eregi_replace) — Replace
    regular expression with multibyte support ignoring case
-   [mb\_eregi](/ref/mbstring.html#mb_eregi) — Regular expression match
    ignoring case with multibyte support
-   [mb\_get\_info](/ref/mbstring.html#mb_get_info) — Get internal
    settings of mbstring
-   [mb\_http\_input](/ref/mbstring.html#mb_http_input) — Detect HTTP
    input character encoding
-   [mb\_http\_output](/ref/mbstring.html#mb_http_output) — Set/Get HTTP
    output character encoding
-   [mb\_internal\_encoding](/ref/mbstring.html#mb_internal_encoding) —
    Set/Get internal character encoding
-   [mb\_language](/ref/mbstring.html#mb_language) — Set/Get current
    language
-   [mb\_list\_encodings](/ref/mbstring.html#mb_list_encodings) —
    Returns an array of all supported encodings
-   [mb\_ord](/ref/mbstring.html#mb_ord) — Get code point of character
-   [mb\_output\_handler](/ref/mbstring.html#mb_output_handler) —
    Callback function converts character encoding in output buffer
-   [mb\_parse\_str](/ref/mbstring.html#mb_parse_str) — Parse
    GET/POST/COOKIE data and set global variable
-   [mb\_preferred\_mime\_name](/ref/mbstring.html#mb_preferred_mime_name)
    — Get MIME charset string
-   [mb\_regex\_encoding](/ref/mbstring.html#mb_regex_encoding) —
    Set/Get character encoding for multibyte regex
-   [mb\_regex\_set\_options](/ref/mbstring.html#mb_regex_set_options) —
    Set/Get the default options for mbregex functions
-   [mb\_scrub](/ref/mbstring.html#mb_scrub) — Description
-   [mb\_send\_mail](/ref/mbstring.html#mb_send_mail) — Send encoded
    mail
-   [mb\_split](/ref/mbstring.html#mb_split) — Split multibyte string
    using regular expression
-   [mb\_str\_split](/ref/mbstring.html#mb_str_split) — Given a
    multibyte string, return an array of its characters
-   [mb\_strcut](/ref/mbstring.html#mb_strcut) — Get part of string
-   [mb\_strimwidth](/ref/mbstring.html#mb_strimwidth) — Get truncated
    string with specified width
-   [mb\_stripos](/ref/mbstring.html#mb_stripos) — Finds position of
    first occurrence of a string within another, case insensitive
-   [mb\_stristr](/ref/mbstring.html#mb_stristr) — Finds first
    occurrence of a string within another, case insensitive
-   [mb\_strlen](/ref/mbstring.html#mb_strlen) — Get string length
-   [mb\_strpos](/ref/mbstring.html#mb_strpos) — Find position of first
    occurrence of string in a string
-   [mb\_strrchr](/ref/mbstring.html#mb_strrchr) — Finds the last
    occurrence of a character in a string within another
-   [mb\_strrichr](/ref/mbstring.html#mb_strrichr) — Finds the last
    occurrence of a character in a string within another, case
    insensitive
-   [mb\_strripos](/ref/mbstring.html#mb_strripos) — Finds position of
    last occurrence of a string within another, case insensitive
-   [mb\_strrpos](/ref/mbstring.html#mb_strrpos) — Find position of last
    occurrence of a string in a string
-   [mb\_strstr](/ref/mbstring.html#mb_strstr) — Finds first occurrence
    of a string within another
-   [mb\_strtolower](/ref/mbstring.html#mb_strtolower) — Make a string
    lowercase
-   [mb\_strtoupper](/ref/mbstring.html#mb_strtoupper) — Make a string
    uppercase
-   [mb\_strwidth](/ref/mbstring.html#mb_strwidth) — Return width of
    string
-   [mb\_substitute\_character](/ref/mbstring.html#mb_substitute_character)
    — Set/Get substitution character
-   [mb\_substr\_count](/ref/mbstring.html#mb_substr_count) — Count the
    number of substring occurrences
-   [mb\_substr](/ref/mbstring.html#mb_substr) — Get part of string

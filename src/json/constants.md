Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

The following constants indicate the type of error returned by <span
class="function">json\_last\_error</span> or stored as the `code` of a
<span class="classname">JsonException</span>.

**`JSON_ERROR_NONE`** (<span class="type">int</span>)  
<span class="simpara"> No error has occurred. Available as of PHP 5.3.0.
</span>

**`JSON_ERROR_DEPTH`** (<span class="type">int</span>)  
<span class="simpara"> The maximum stack depth has been exceeded.
Available as of PHP 5.3.0. </span>

**`JSON_ERROR_STATE_MISMATCH`** (<span class="type">int</span>)  
<span class="simpara"> Occurs with underflow or with the modes mismatch.
Available as of PHP 5.3.0. </span>

**`JSON_ERROR_CTRL_CHAR`** (<span class="type">int</span>)  
<span class="simpara"> Control character error, possibly incorrectly
encoded. Available as of PHP 5.3.0. </span>

**`JSON_ERROR_SYNTAX`** (<span class="type">int</span>)  
<span class="simpara"> Syntax error. Available as of PHP 5.3.0. </span>

**`JSON_ERROR_UTF8`** (<span class="type">int</span>)  
<span class="simpara"> Malformed UTF-8 characters, possibly incorrectly
encoded. Available as of PHP 5.3.3. </span>

**`JSON_ERROR_RECURSION`** (<span class="type">int</span>)  
<span class="simpara"> The object or array passed to <span
class="function">json\_encode</span> include recursive references and
cannot be encoded. If the **`JSON_PARTIAL_OUTPUT_ON_ERROR`** option was
given, **`null`** will be encoded in the place of the recursive
reference. Available as of PHP 5.5.0. </span>

**`JSON_ERROR_INF_OR_NAN`** (<span class="type">int</span>)  
<span class="simpara"> The value passed to <span
class="function">json\_encode</span> includes either
<a href="/language/types/float.html#language.types.float.nan" class="link"><strong><code>NAN</code></strong></a>
or
<a href="/ref/math.html#is_infinite" class="link"><strong><code>INF</code></strong></a>.
If the **`JSON_PARTIAL_OUTPUT_ON_ERROR`** option was given, *0* will be
encoded in the place of these special numbers. Available as of PHP
5.5.0. </span>

**`JSON_ERROR_UNSUPPORTED_TYPE`** (<span class="type">int</span>)  
<span class="simpara"> A value of an unsupported type was given to <span
class="function">json\_encode</span>, such as a
<a href="/language/types/resource.html" class="link">resource</a>. If
the **`JSON_PARTIAL_OUTPUT_ON_ERROR`** option was given, **`null`** will
be encoded in the place of the unsupported value. Available as of PHP
5.5.0. </span>

**`JSON_ERROR_INVALID_PROPERTY_NAME`** (<span class="type">int</span>)  
<span class="simpara"> A key starting with \\u0000 character was in the
string passed to <span class="function">json\_decode</span> when
decoding a JSON object into a PHP object. Available as of PHP 7.0.0.
</span>

**`JSON_ERROR_UTF16`** (<span class="type">int</span>)  
<span class="simpara"> Single unpaired UTF-16 surrogate in unicode
escape contained in the JSON string passed to <span
class="function">json\_decode</span>. Available as of PHP 7.0.0. </span>

The following constants can be combined to form options for <span
class="function">json\_decode</span>.

**`JSON_BIGINT_AS_STRING`** (<span class="type">int</span>)  
<span class="simpara"> Decodes large integers as their original string
value. Available as of PHP 5.4.0. </span>

**`JSON_OBJECT_AS_ARRAY`** (<span class="type">int</span>)  
<span class="simpara"> Decodes JSON objects as PHP array. This option
can be added automatically by calling <span
class="function">json\_decode</span> with the second parameter equal to
**`true`**. Available as of PHP 5.4.0. </span>

The following constants can be combined to form options for <span
class="function">json\_encode</span>.

**`JSON_HEX_TAG`** (<span class="type">int</span>)  
<span class="simpara"> All \< and \> are converted to \\u003C and
\\u003E. Available as of PHP 5.3.0. </span>

**`JSON_HEX_AMP`** (<span class="type">int</span>)  
<span class="simpara"> All & are converted to \\u0026. Available as of
PHP 5.3.0. </span>

**`JSON_HEX_APOS`** (<span class="type">int</span>)  
<span class="simpara"> All ' are converted to \\u0027. Available as of
PHP 5.3.0. </span>

**`JSON_HEX_QUOT`** (<span class="type">int</span>)  
<span class="simpara"> All " are converted to \\u0022. Available as of
PHP 5.3.0. </span>

**`JSON_FORCE_OBJECT`** (<span class="type">int</span>)  
<span class="simpara"> Outputs an object rather than an array when a
non-associative array is used. Especially useful when the recipient of
the output is expecting an object and the array is empty. Available as
of PHP 5.3.0. </span>

**`JSON_NUMERIC_CHECK`** (<span class="type">int</span>)  
<span class="simpara"> Encodes numeric strings as numbers. Available as
of PHP 5.3.3. </span>

**`JSON_PRETTY_PRINT`** (<span class="type">int</span>)  
<span class="simpara"> Use whitespace in returned data to format it.
Available as of PHP 5.4.0. </span>

**`JSON_UNESCAPED_SLASHES`** (<span class="type">int</span>)  
<span class="simpara"> Don't escape */*. Available as of PHP 5.4.0.
</span>

**`JSON_UNESCAPED_UNICODE`** (<span class="type">int</span>)  
<span class="simpara"> Encode multibyte Unicode characters literally
(default is to escape as \\uXXXX). Available as of PHP 5.4.0. </span>

**`JSON_PARTIAL_OUTPUT_ON_ERROR`** (<span class="type">int</span>)  
<span class="simpara"> Substitute some unencodable values instead of
failing. Available as of PHP 5.5.0. </span>

**`JSON_PRESERVE_ZERO_FRACTION`** (<span class="type">int</span>)  
<span class="simpara"> Ensures that <span class="type">float</span>
values are always encoded as a float value. Available as of PHP 5.6.6.
</span>

**`JSON_UNESCAPED_LINE_TERMINATORS`** (<span class="type">int</span>)  
<span class="simpara"> The line terminators are kept unescaped when
**`JSON_UNESCAPED_UNICODE`** is supplied. It uses the same behaviour as
it was before PHP 7.1 without this constant. Available as of PHP 7.1.0.
</span>

The following constants can be combined to form options for <span
class="function">json\_decode</span> and <span
class="function">json\_encode</span>.

**`JSON_INVALID_UTF8_IGNORE`** (<span class="type">int</span>)  
<span class="simpara"> Ignore invalid UTF-8 characters. Available as of
PHP 7.2.0. </span>

**`JSON_INVALID_UTF8_SUBSTITUTE`** (<span class="type">int</span>)  
<span class="simpara"> Convert invalid UTF-8 characters to \\0xfffd
(Unicode Character 'REPLACEMENT CHARACTER') Available as of PHP 7.2.0.
</span>

**`JSON_THROW_ON_ERROR`** (<span class="type">int</span>)  
<span class="simpara"> Throws <span
class="classname">JsonException</span> if an error occurs instead of
setting the global error state that is retrieved with <span
class="function">json\_last\_error</span> and <span
class="function">json\_last\_error\_msg</span>.
**`JSON_PARTIAL_OUTPUT_ON_ERROR`** takes precedence over
**`JSON_THROW_ON_ERROR`**. Available as of PHP 7.3.0. </span>

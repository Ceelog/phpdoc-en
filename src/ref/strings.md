For even more powerful string handling and manipulating functions take a
look at the
<a href="/ref/pcre.html" class="link">Perl compatible regular expression functions</a>.
For working with multibyte character encodings, take a look at the
<a href="/ref/mbstring.html" class="link">Multibyte String functions</a>.

addcslashes
===========

Quote string with slashes in a C style

### Description

<span class="type">string</span> <span
class="methodname">addcslashes</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> , <span
class="methodparam"><span class="type">string</span> `$charlist`</span>
)

Returns a string with backslashes before characters that are listed in
`charlist` parameter.

### Parameters

`str`  
The string to be escaped.

`charlist`  
A list of characters to be escaped. If `charlist` contains characters
*\\n*, *\\r* etc., they are converted in C-like style, while other
non-alphanumeric characters with ASCII codes lower than 32 and higher
than 126 converted to octal representation.

When you define a sequence of characters in the charlist argument make
sure that you know what characters come between the characters that you
set as the start and end of the range.

``` php
<?php
echo addcslashes('foo[ ]', 'A..z');
// output:  \f\o\o\[ \]
// All upper and lower-case letters will be escaped
// ... but so will the [\]^_`
?>
```

Also, if the first character in a range has a higher ASCII value than
the second character in the range, no range will be constructed. Only
the start, end and period characters will be escaped. Use the <span
class="function">ord</span> function to find the ASCII value for a
character.

``` php
<?php
echo addcslashes("zoo['.']", 'z..A');
// output:  \zoo['\.']
?>
```

Be careful if you choose to escape characters 0, a, b, f, n, r, t and v.
They will be converted to \\0, \\a, \\b, \\f, \\n, \\r, \\t and \\v, all
of which are predefined escape sequences in C. Many of these sequences
are also defined in other C-derived languages, including PHP, meaning
that you may not get the desired result if you use the output of <span
class="function">addcslashes</span> to generate code in those languages
with these characters defined in `charlist`.

### Return Values

Returns the escaped string.

### Examples

`charlist` like "\\0..\\37", which would escape all characters with
ASCII code between 0 and 31.

**Example \#1 <span class="function">addcslashes</span> example**

``` php
<?php
$escaped = addcslashes($not_escaped, "\0..\37!@\177..\377");
?>
```

### See Also

-   <span class="function">stripcslashes</span>
-   <span class="function">stripslashes</span>
-   <span class="function">addslashes</span>
-   <span class="function">htmlspecialchars</span>
-   <span class="function">quotemeta</span>

addslashes
==========

Quote string with slashes

### Description

<span class="type">string</span> <span
class="methodname">addslashes</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

Returns a string with backslashes added before characters that need to
be escaped. These characters are:

-   single quote (*'*)
-   double quote (*"*)
-   backslash (*\\*)
-   NUL (the NUL byte)

A use case of <span class="function">addslashes</span> is escaping the
aforementioned characters in a string that is to be evaluated by PHP:

``` php
<?php
$str = "O'Reilly?";
eval("echo '" . addslashes($str) . "';");
?>
```

Prior to PHP 5.4.0, the PHP directive
<a href="/info/setup.html#" class="link">magic_quotes_gpc</a> was *on*
by default and it essentially ran <span
class="function">addslashes</span> on all GET, POST and COOKIE data.
<span class="function">addslashes</span> must not be used on strings
that have already been escaped with
<a href="/info/setup.html#" class="link">magic_quotes_gpc</a>, as the
strings will be double escaped. <span
class="function">get\_magic\_quotes\_gpc</span> can be used to check if
<a href="/info/setup.html#" class="link">magic_quotes_gpc</a> is *on*.

The <span class="function">addslashes</span> is sometimes incorrectly
used to try to prevent
<a href="/security/database/sql-injection.html" class="link">SQL Injection</a>.
Instead, database-specific escaping functions and/or prepared statements
should be used.

### Parameters

`str`  
The string to be escaped.

### Return Values

Returns the escaped string.

### Examples

**Example \#1 An <span class="function">addslashes</span> example**

``` php
<?php
$str = "Is your name O'Reilly?";

// Outputs: Is your name O\'Reilly?
echo addslashes($str);
?>
```

### See Also

-   <span class="function">stripcslashes</span>
-   <span class="function">stripslashes</span>
-   <span class="function">addcslashes</span>
-   <span class="function">htmlspecialchars</span>
-   <span class="function">quotemeta</span>
-   <span class="function">get\_magic\_quotes\_gpc</span>

bin2hex
=======

Convert binary data into hexadecimal representation

### Description

<span class="type">string</span> <span class="methodname">bin2hex</span>
( <span class="methodparam"><span class="type">string</span>
`$str`</span> )

Returns an ASCII string containing the hexadecimal representation of
`str`. The conversion is done byte-wise with the high-nibble first.

### Parameters

`str`  
A string.

### Return Values

Returns the hexadecimal representation of the given string.

### See Also

-   <span class="function">hex2bin</span>
-   <span class="function">pack</span>

chop
====

Alias of <span class="function">rtrim</span>

### Description

This function is an alias of: <span class="function">rtrim</span>.

### Notes

> **Note**:
>
> <span class="function">chop</span> is different than the Perl *chop()*
> function, which removes the last character in the string.

chr
===

Generate a single-byte string from a number

### Description

<span class="type">string</span> <span class="methodname">chr</span> (
<span class="methodparam"><span class="type">int</span>
`$bytevalue`</span> )

Returns a one-character string containing the character specified by
interpreting `bytevalue` as an unsigned integer.

This can be used to create a one-character string in a single-byte
encoding such as ASCII, ISO-8859, or Windows 1252, by passing the
position of a desired character in the encoding's mapping table.
However, note that this function is not aware of any string encoding,
and in particular cannot be passed a Unicode code point value to
generate a string in a multibyte encoding like UTF-8 or UTF-16.

This function complements <span class="function">ord</span>.

### Parameters

`bytevalue`  
An integer between 0 and 255.

Values outside the valid range (0..255) will be bitwise and'ed with 255,
which is equivalent to the following algorithm:

``` php
while ($bytevalue < 0) {
    $bytevalue += 256;
}
$bytevalue %= 256;
```

### Return Values

A single-character string containing the specified byte.

### Examples

**Example \#1 <span class="function">chr</span> example**

``` php
<?php
// Assumes the string will be used as ASCII or an ASCII-compatible encoding

$str = "The string ends in escape: ";
$str .= chr(27); /* add an escape character at the end of $str */

/* Often this is more useful */

$str = sprintf("The string ends in escape: %c", 27);
?>
```

**Example \#2 Overflow behavior**

``` php
<?php
echo chr(-159), chr(833), PHP_EOL;
?>
```

The above example will output:

    aA

**Example \#3 Building a UTF-8 string from individual bytes**

``` php
<?php
$str = chr(240) . chr(159) . chr(144) . chr(152);
echo $str;
?>
```

The above example will output:

  
🐘  

### See Also

-   <span class="function">sprintf</span> with a format string of *%c*
-   <span class="function">ord</span>
-   An
    <a href="http://www.asciitable.com" class="link external">» ASCII-table</a>
-   <span class="function">mb\_chr</span>

chunk\_split
============

Split a string into smaller chunks

### Description

<span class="type">string</span> <span
class="methodname">chunk\_split</span> ( <span class="methodparam"><span
class="type">string</span> `$body`</span> \[, <span
class="methodparam"><span class="type">int</span> `$chunklen`<span
class="initializer"> = 76</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$end`<span
class="initializer"> = "\\r\\n"</span></span> \]\] )

Can be used to split a string into smaller chunks which is useful for
e.g. converting <span class="function">base64\_encode</span> output to
match RFC 2045 semantics. It inserts `end` every `chunklen` characters.

### Parameters

`body`  
The string to be chunked.

`chunklen`  
The chunk length.

`end`  
The line ending sequence.

### Return Values

Returns the chunked string.

### Examples

**Example \#1 <span class="function">chunk\_split</span> example**

``` php
<?php
// format $data using RFC 2045 semantics
$new_string = chunk_split(base64_encode($data));
?>
```

### See Also

-   <span class="function">str\_split</span>
-   <span class="function">explode</span>
-   <span class="function">split</span>
-   <span class="function">wordwrap</span>
-   <a href="http://www.faqs.org/rfcs/rfc2045" class="link external">» RFC 2045</a>

convert\_cyr\_string
====================

Convert from one Cyrillic character set to another

### Description

<span class="type">string</span> <span
class="methodname">convert\_cyr\_string</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> ,
<span class="methodparam"><span class="type">string</span>
`$from`</span> , <span class="methodparam"><span
class="type">string</span> `$to`</span> )

Converts from one Cyrillic character set to another.

### Parameters

`str`  
The string to be converted.

`from`  
The source Cyrillic character set, as a single character.

`to`  
The target Cyrillic character set, as a single character.

Supported characters are:

-   <span class="simpara"> k - koi8-r </span>
-   <span class="simpara"> w - windows-1251 </span>
-   <span class="simpara"> i - iso8859-5 </span>
-   <span class="simpara"> a - x-cp866 </span>
-   <span class="simpara"> d - x-cp866 </span>
-   <span class="simpara"> m - x-mac-cyrillic </span>

### Return Values

Returns the converted string.

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">mb\_convert\_encoding</span>
-   <span class="function">iconv</span>

convert\_uudecode
=================

Decode a uuencoded string

### Description

<span class="type">string</span> <span
class="methodname">convert\_uudecode</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

<span class="function">convert\_uudecode</span> decodes a uuencoded
string.

> **Note**: <span class="simpara"> <span
> class="function">convert\_uudecode</span> neither accepts the *begin*
> nor the *end* line, which are part of uuencoded *files*. </span>

### Parameters

`data`  
The uuencoded data.

### Return Values

Returns the decoded data as a string or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">convert\_uudecode</span> example**

``` php
<?php
echo convert_uudecode("+22!L;W9E(%!(4\"$`\n`");
?>
```

The above example will output:

    I love PHP!

### See Also

-   <span class="function">convert\_uuencode</span>

convert\_uuencode
=================

Uuencode a string

### Description

<span class="type">string</span> <span
class="methodname">convert\_uuencode</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

<span class="function">convert\_uuencode</span> encodes a string using
the uuencode algorithm.

Uuencode translates all strings (including binary data) into printable
characters, making them safe for network transmissions. Uuencoded data
is about 35% larger than the original.

> **Note**: <span class="simpara"> <span
> class="function">convert\_uuencode</span> neither produces the *begin*
> nor the *end* line, which are part of uuencoded *files*. </span>

### Parameters

`data`  
The data to be encoded.

### Return Values

Returns the uuencoded data or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">convert\_uuencode</span> example**

``` php
<?php
$some_string = "test\ntext text\r\n";

echo convert_uuencode($some_string);
?>
```

The above example will output:

    0=&5S=`IT97AT('1E>'0-"@``
    `

### See Also

-   <span class="function">convert\_uudecode</span>
-   <span class="function">base64\_encode</span>

count\_chars
============

Return information about characters used in a string

### Description

<span class="type">mixed</span> <span
class="methodname">count\_chars</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = 0</span></span> \] )

Counts the number of occurrences of every byte-value (0..255) in
`string` and returns it in various ways.

### Parameters

`string`  
The examined string.

`mode`  
See return values.

### Return Values

Depending on `mode` <span class="function">count\_chars</span> returns
one of the following:

-   <span class="simpara"> 0 - an array with the byte-value as key and
    the frequency of every byte as value. </span>
-   <span class="simpara"> 1 - same as 0 but only byte-values with a
    frequency greater than zero are listed. </span>
-   <span class="simpara"> 2 - same as 0 but only byte-values with a
    frequency equal to zero are listed. </span>
-   <span class="simpara"> 3 - a string containing all unique characters
    is returned. </span>
-   <span class="simpara"> 4 - a string containing all not used
    characters is returned. </span>

### Examples

**Example \#1 <span class="function">count\_chars</span> example**

``` php
<?php
$data = "Two Ts and one F.";

foreach (count_chars($data, 1) as $i => $val) {
   echo "There were $val instance(s) of \"" , chr($i) , "\" in the string.\n";
}
?>
```

The above example will output:

    There were 4 instance(s) of " " in the string.
    There were 1 instance(s) of "." in the string.
    There were 1 instance(s) of "F" in the string.
    There were 2 instance(s) of "T" in the string.
    There were 1 instance(s) of "a" in the string.
    There were 1 instance(s) of "d" in the string.
    There were 1 instance(s) of "e" in the string.
    There were 2 instance(s) of "n" in the string.
    There were 2 instance(s) of "o" in the string.
    There were 1 instance(s) of "s" in the string.
    There were 1 instance(s) of "w" in the string.

### See Also

-   <span class="function">strpos</span>
-   <span class="function">substr\_count</span>

crc32
=====

Calculates the crc32 polynomial of a string

### Description

<span class="type">int</span> <span class="methodname">crc32</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
)

Generates the cyclic redundancy checksum polynomial of 32-bit lengths of
the `str`. This is usually used to validate the integrity of data being
transmitted.

**Warning**

Because PHP's integer type is signed many crc32 checksums will result in
negative integers on 32bit platforms. On 64bit installations all <span
class="function">crc32</span> results will be positive integers though.

So you need to use the "%u" formatter of <span
class="function">sprintf</span> or <span class="function">printf</span>
to get the string representation of the unsigned <span
class="function">crc32</span> checksum in decimal format.

For a hexadecimal representation of the checksum you can either use the
"%x" formatter of <span class="function">sprintf</span> or <span
class="function">printf</span> or the <span
class="function">dechex</span> conversion functions, both of these also
take care of converting the <span class="function">crc32</span> result
to an unsigned integer.

Having 64bit installations also return negative integers for higher
result values was considered but would break the hexadecimal conversion
as negatives would get an extra 0xFFFFFFFF\#\#\#\#\#\#\#\# offset then.
As hexadecimal representation seems to be the most common use case we
decided to not break this even if it breaks direct decimal comparisons
in about 50% of the cases when moving from 32 to 64bits.

In retrospect having the function return an integer maybe wasn't the
best idea and returning a hex string representation right away (as e.g.
<span class="function">md5</span> does) might have been a better plan to
begin with.

For a more portable solution you may also consider the generic <span
class="function">hash</span>. `hash("crc32b", $str)` will return the
same string as `str_pad(dechex(crc32($str)), 8, '0', STR_PAD_LEFT)`.

### Parameters

`str`  
The data.

### Return Values

Returns the crc32 checksum of `str` as an integer.

### Examples

**Example \#1 Displaying a crc32 checksum**

This example shows how to print a converted checksum with the <span
class="function">printf</span> function:

``` php
<?php
$checksum = crc32("The quick brown fox jumped over the lazy dog.");
printf("%u\n", $checksum);
?>
```

### See Also

-   <span class="function">hash</span>
-   <span class="function">md5</span>
-   <span class="function">sha1</span>

crypt
=====

One-way string hashing

**Warning**

This function is not (yet) binary safe!

### Description

<span class="type">string</span> <span class="methodname">crypt</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$salt`</span> \] )

<span class="function">crypt</span> will return a hashed string using
the standard Unix DES-based algorithm or alternative algorithms that may
be available on the system.

The `salt` parameter is optional. However, <span
class="function">crypt</span> creates a weak hash without the `salt`.
PHP 5.6 or later raise an E\_NOTICE error without it. Make sure to
specify a strong enough salt for better security.

<span class="function">password\_hash</span> uses a strong hash,
generates a strong salt, and applies proper rounds automatically. <span
class="function">password\_hash</span> is a simple <span
class="function">crypt</span> wrapper and compatible with existing
password hashes. Use of <span class="function">password\_hash</span> is
encouraged.

Some operating systems support more than one type of hash. In fact,
sometimes the standard DES-based algorithm is replaced by an MD5-based
algorithm. The hash type is triggered by the salt argument. Prior to
5.3, PHP would determine the available algorithms at install-time based
on the system's crypt(). If no salt is provided, PHP will auto-generate
either a standard two character (DES) salt, or a twelve character (MD5),
depending on the availability of MD5 crypt(). PHP sets a constant named
**`CRYPT_SALT_LENGTH`** which indicates the longest valid salt allowed
by the available hashes.

The standard DES-based <span class="function">crypt</span> returns the
salt as the first two characters of the output. It also only uses the
first eight characters of `str`, so longer strings that start with the
same eight characters will generate the same result (when the same salt
is used).

On systems where the crypt() function supports multiple hash types, the
following constants are set to 0 or 1 depending on whether the given
type is available:

-   <span class="simpara"> **`CRYPT_STD_DES`** - Standard DES-based hash
    with a two character salt from the alphabet "./0-9A-Za-z". Using
    invalid characters in the salt will cause crypt() to fail. </span>
-   <span class="simpara"> **`CRYPT_EXT_DES`** - Extended DES-based
    hash. The "salt" is a 9-character string consisting of an underscore
    followed by 4 bytes of iteration count and 4 bytes of salt. These
    are encoded as printable characters, 6 bits per character, least
    significant character first. The values 0 to 63 are encoded as
    "./0-9A-Za-z". Using invalid characters in the salt will cause
    crypt() to fail. </span>
-   <span class="simpara"> **`CRYPT_MD5`** - MD5 hashing with a twelve
    character salt starting with $1$ </span>
-   <span class="simpara"> **`CRYPT_BLOWFISH`** - Blowfish hashing with
    a salt as follows: "$2a$", "$2x$" or "$2y$", a two digit cost
    parameter, "$", and 22 characters from the alphabet "./0-9A-Za-z".
    Using characters outside of this range in the salt will cause
    crypt() to return a zero-length string. The two digit cost parameter
    is the base-2 logarithm of the iteration count for the underlying
    Blowfish-based hashing algorithmeter and must be in range 04-31,
    values outside this range will cause crypt() to fail. Versions of
    PHP before 5.3.7 only support "$2a$" as the salt prefix: PHP 5.3.7
    introduced the new prefixes to fix a security weakness in the
    Blowfish implementation. Please refer to
    <a href="https://www.php.net/security/crypt_blowfish.php" class="link external">» this document</a>
    for full details of the security fix, but to summarise, developers
    targeting only PHP 5.3.7 and later should use "$2y$" in preference
    to "$2a$". </span>
-   <span class="simpara"> **`CRYPT_SHA256`** - SHA-256 hash with a
    sixteen character salt prefixed with $5$. If the salt string starts
    with 'rounds=\<N\>$', the numeric value of N is used to indicate how
    many times the hashing loop should be executed, much like the cost
    parameter on Blowfish. The default number of rounds is 5000, there
    is a minimum of 1000 and a maximum of 999,999,999. Any selection of
    N outside this range will be truncated to the nearest limit. </span>
-   <span class="simpara"> **`CRYPT_SHA512`** - SHA-512 hash with a
    sixteen character salt prefixed with $6$. If the salt string starts
    with 'rounds=\<N\>$', the numeric value of N is used to indicate how
    many times the hashing loop should be executed, much like the cost
    parameter on Blowfish. The default number of rounds is 5000, there
    is a minimum of 1000 and a maximum of 999,999,999. Any selection of
    N outside this range will be truncated to the nearest limit. </span>

> **Note**:
>
> As of PHP 5.3.0, PHP contains its own implementation and will use that
> if the system lacks of support for one or more of the algorithms.

### Parameters

`str`  
The string to be hashed.

**Caution**
Using the **`CRYPT_BLOWFISH`** algorithm, will result in the `str`
parameter being truncated to a maximum length of 72 characters.

`salt`  
An optional salt string to base the hashing on. If not provided, the
behaviour is defined by the algorithm implementation and can lead to
unexpected results.

### Return Values

Returns the hashed string or a string that is shorter than 13 characters
and is guaranteed to differ from the salt on failure.

**Warning**

When validating passwords, a string comparison function that isn't
vulnerable to timing attacks should be used to compare the output of
<span class="function">crypt</span> to the previously known hash. PHP
5.6 onwards provides <span class="function">hash\_equals</span> for this
purpose.

### Examples

**Example \#1 <span class="function">crypt</span> examples**

``` php
<?php
$hashed_password = crypt('mypassword'); // let the salt be automatically generated

/* You should pass the entire results of crypt() as the salt for comparing a
   password, to avoid problems when different hashing algorithms are used. (As
   it says above, standard DES-based password hashing uses a 2-character salt,
   but MD5-based hashing uses 12.) */
if (hash_equals($hashed_password, crypt($user_input, $hashed_password))) {
   echo "Password verified!";
}
?>
```

**Example \#2 Using <span class="function">crypt</span> with htpasswd**

``` php
<?php
// Set the password
$password = 'mypassword';

// Get the hash, letting the salt be automatically generated
$hash = crypt($password);
?>
```

**Example \#3 Using <span class="function">crypt</span> with different
hash types**

``` php
<?php
/* These salts are examples only, and should not be used verbatim in your code.
   You should generate a distinct, correctly-formatted salt for each password.
*/
if (CRYPT_STD_DES == 1) {
    echo 'Standard DES: ' . crypt('rasmuslerdorf', 'rl') . "\n";
}

if (CRYPT_EXT_DES == 1) {
    echo 'Extended DES: ' . crypt('rasmuslerdorf', '_J9..rasm') . "\n";
}

if (CRYPT_MD5 == 1) {
    echo 'MD5:          ' . crypt('rasmuslerdorf', '$1$rasmusle$') . "\n";
}

if (CRYPT_BLOWFISH == 1) {
    echo 'Blowfish:     ' . crypt('rasmuslerdorf', '$2a$07$usesomesillystringforsalt$') . "\n";
}

if (CRYPT_SHA256 == 1) {
    echo 'SHA-256:      ' . crypt('rasmuslerdorf', '$5$rounds=5000$usesomesillystringforsalt$') . "\n";
}

if (CRYPT_SHA512 == 1) {
    echo 'SHA-512:      ' . crypt('rasmuslerdorf', '$6$rounds=5000$usesomesillystringforsalt$') . "\n";
}
?>
```

The above example will output something similar to:

    Standard DES: rl.3StKT.4T8M
    Extended DES: _J9..rasmBYk8r9AiWNc
    MD5:          $1$rasmusle$rISCgZzpwk3UhDidwXvin0
    Blowfish:     $2a$07$usesomesillystringfore2uDLvp1Ii2e./U9C8sBjqp8I90dH6hi
    SHA-256:      $5$rounds=5000$usesomesillystri$KqJWpanXZHKq2BOB43TSaYhEWsQ1Lr5QNyPCDH/Tp.6
    SHA-512:      $6$rounds=5000$usesomesillystri$D4IrlXatmP7rx3P3InaxBeoomnAihCKRVQP22JZ6EY47Wc6BkroIuUUBOov1i.S5KPgErtP/EN5mcO.ChWQW21

### Notes

> **Note**: <span class="simpara"> There is no decrypt function, since
> <span class="function">crypt</span> uses a one-way algorithm. </span>

### See Also

-   <span class="function">hash\_equals</span>
-   <span class="function">password\_hash</span>
-   <span class="function">md5</span>
-   The <a href="/ref/mcrypt.html" class="link">Mcrypt</a> extension
-   The Unix man page for your crypt function for more information

echo
====

Output one or more strings

### Description

<span class="type">void</span> <span class="methodname">echo</span> (
<span class="methodparam"><span class="type">string</span>
`$arg1`</span> \[, <span class="methodparam"><span
class="type">string</span> `$...`</span> \] )

Outputs all parameters. No additional newline is appended.

*echo* is not actually a function (it is a language construct), so you
are not required to use parentheses with it. *echo* (unlike some other
language constructs) does not behave like a function, so it cannot
always be used in the context of a function. Additionally, if you want
to pass more than one parameter to *echo*, the parameters must not be
enclosed within parentheses.

*echo* also has a shortcut syntax, where you can immediately follow the
opening tag with an equals sign. Prior to PHP 5.4.0, this short syntax
only works with the
<a href="/ini/core.html#ini.short-open-tag" class="link">short_open_tag</a>
configuration setting enabled.

``` php
I have <?=$foo?> foo.
```

The major differences to *print* are that *echo* accepts an argument
list and doesn't have a return value.

### Parameters

`arg1`  
The parameter to output.

`...`  

### Return Values

No value is returned.

### Examples

**Example \#1 *echo* examples**

``` php
<?php
echo "Hello World";

// Strings can either be passed individually as multiple arguments or
// concatenated together and passed as a single argument
echo 'This ', 'string ', 'was ', 'made ', 'with multiple parameters.', chr(10);
echo 'This ' . 'string ' . 'was ' . 'made ' . 'with concatenation.' . "\n";

// Because echo does not behave like a function, the following code is invalid.
($some_var) ? echo 'true' : echo 'false';

// However, the following examples will work:
($some_var) ? print 'true' : print 'false'; // print is also a construct, but
                                            // it behaves like a function, so
                                            // it may be used in this context.

echo $some_var ? 'true': 'false'; // changing the statement around
?>
```

### Notes

> **Note**: <span class="simpara">Because this is a language construct
> and not a function, it cannot be called using
> <a href="/functions/variable-functions.html" class="link">variable functions</a>.</span>

**Tip**

A benefit to passing in multiple arguments over using concatenation in
<span class="function">echo</span> regards the precedence of the period
operator in PHP. If multiple arguments are passed in, then parentheses
will not be required to enforce precedence:

``` php
<?php
echo "Sum: ", 1 + 2;
echo "Hello ", isset($name) ? $name : "John Doe", "!";
```

With concatenation, the period operator has the same precedence as the
addition operator, and higher precedence than the ternary operator, so
parentheses must be used for the correct behaviour:

``` php
<?php
echo 'Sum: ' . (1 + 2);
echo 'Hello ' . (isset($name) ? $name : 'John Doe') . '!';
```

### See Also

-   <span class="function">print</span>
-   <span class="function">printf</span>
-   <span class="function">flush</span>
-   <a href="/language/types/string.html#language.types.string.syntax.heredoc" class="link">Heredoc syntax</a>

explode
=======

Split a string by a string

### Description

<span class="type">array</span> <span class="methodname">explode</span>
( <span class="methodparam"><span class="type">string</span>
`$delimiter`</span> , <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$limit`<span
class="initializer"> = PHP\_INT\_MAX</span></span> \] )

Returns an array of strings, each of which is a substring of `string`
formed by splitting it on boundaries formed by the string `delimiter`.

### Parameters

`delimiter`  
The boundary string.

`string`  
The input string.

`limit`  
If `limit` is set and positive, the returned array will contain a
maximum of `limit` elements with the last element containing the rest of
`string`.

If the `limit` parameter is negative, all components except the last
-`limit` are returned.

If the `limit` parameter is zero, then this is treated as 1.

> **Note**:
>
> Although <span class="function">implode</span> can, for historical
> reasons, accept its parameters in either order, <span
> class="function">explode</span> cannot. You must ensure that the
> `delimiter` argument comes before the `string` argument.

### Return Values

Returns an <span class="type">array</span> of <span
class="type">string</span>s created by splitting the `string` parameter
on boundaries formed by the `delimiter`.

If `delimiter` is an empty <span class="type">string</span> (""), <span
class="function">explode</span> will return **`FALSE`**. If `delimiter`
contains a value that is not contained in `string` and a negative
`limit` is used, then an empty <span class="type">array</span> will be
returned, otherwise an <span class="type">array</span> containing
`string` will be returned.

### Examples

**Example \#1 <span class="function">explode</span> examples**

``` php
<?php
// Example 1
$pizza  = "piece1 piece2 piece3 piece4 piece5 piece6";
$pieces = explode(" ", $pizza);
echo $pieces[0]; // piece1
echo $pieces[1]; // piece2

// Example 2
$data = "foo:*:1023:1000::/home/foo:/bin/sh";
list($user, $pass, $uid, $gid, $gecos, $home, $shell) = explode(":", $data);
echo $user; // foo
echo $pass; // *

?>
```

**Example \#2 <span class="function">explode</span> return examples**

``` php
<?php
/* 
   A string that doesn't contain the delimiter will simply
   return a one-length array of the original string.
*/
$input1 = "hello";
$input2 = "hello,there";
$input3 = ',';
var_dump( explode( ',', $input1 ) );
var_dump( explode( ',', $input2 ) );
var_dump( explode( ',', $input3 ) );

?>
```

The above example will output:

    array(1)
    (
        [0] => string(5) "hello"
    )
    array(2)
    (
        [0] => string(5) "hello"
        [1] => string(5) "there"
    )
    array(2)
    (
        [0] => string(0) ""
        [1] => string(0) ""
    )

**Example \#3 `limit` parameter examples**

``` php
<?php
$str = 'one|two|three|four';

// positive limit
print_r(explode('|', $str, 2));

// negative limit (since PHP 5.1)
print_r(explode('|', $str, -1));
?>
```

The above example will output:

    Array
    (
        [0] => one
        [1] => two|three|four
    )
    Array
    (
        [0] => one
        [1] => two
        [2] => three
    )

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">preg\_split</span>
-   <span class="function">str\_split</span>
-   <span class="function">mb\_split</span>
-   <span class="function">str\_word\_count</span>
-   <span class="function">strtok</span>
-   <span class="function">implode</span>

fprintf
=======

Write a formatted string to a stream

### Description

<span class="type">int</span> <span class="methodname">fprintf</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">string</span> `$format`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$...`</span> \] )

Write a string produced according to `format` to the stream resource
specified by `handle`.

### Parameters

`handle`  
A file system pointer <span class="type">resource</span> that is
typically created using <span class="function">fopen</span>.

`format`  
The format string is composed of zero or more directives: ordinary
characters (excluding *%*) that are copied directly to the result and
*conversion specifications*, each of which results in fetching its own
parameter.

A conversion specification follows this prototype:
*%\[argnum$\]\[flags\]\[width\]\[.precision\]specifier*.

##### Argnum

An integer followed by a dollar sign *$*, to specify which number
argument to treat in the conversion.

| Flag      | Description                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------|
| *-*       | Left-justify within the given field width; Right justification is the default                          |
| *+*       | Prefix positive numbers with a plus sign *+*; Default only negative are prefixed with a negative sign. |
|  (space)  | Pads the result with spaces. This is the default.                                                      |
| *0*       | Only left-pads numbers with zeros. With *s* specifiers this can also right-pad with zeros.             |
| *'*(char) | Pads the result with the character (char).                                                             |

##### Width

An integer that says how many characters (minimum) this conversion
should result in.

##### Precision

A period *.* followed by an integer who's meaning depends on the
specifier:

-   <span class="simpara"> For *e*, *E*, *f* and *F* specifiers: this is
    the number of digits to be printed after the decimal point (by
    default, this is 6). </span>
-   <span class="simpara"> For *g* and *G* specifiers: this is the
    maximum number of significant digits to be printed. </span>
-   <span class="simpara"> For *s* specifier: it acts as a cutoff point,
    setting a maximum character limit to the string. </span>

> **Note**: <span class="simpara"> If the period is specified without an
> explicit value for precision, 0 is assumed. </span>

> **Note**: <span class="simpara"> Attempting to use a position
> specifier greater than **`PHP_INT_MAX`** will generate warnings.
> </span>

<table>
<caption><strong>Specifiers</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>%</em></td>
<td>A literal percent character. No argument is required.</td>
</tr>
<tr class="even">
<td><em>b</em></td>
<td>The argument is treated as an integer and presented as a binary number.</td>
</tr>
<tr class="odd">
<td><em>c</em></td>
<td>The argument is treated as an integer and presented as the character with that ASCII.</td>
</tr>
<tr class="even">
<td><em>d</em></td>
<td>The argument is treated as an integer and presented as a (signed) decimal number.</td>
</tr>
<tr class="odd">
<td><em>e</em></td>
<td>The argument is treated as scientific notation (e.g. 1.2e+2). The precision specifier stands for the number of digits after the decimal point since PHP 5.2.1. In earlier versions, it was taken as number of significant digits (one less).</td>
</tr>
<tr class="even">
<td><em>E</em></td>
<td>Like the <em>e</em> specifier but uses uppercase letter (e.g. 1.2E+2).</td>
</tr>
<tr class="odd">
<td><em>f</em></td>
<td>The argument is treated as a float and presented as a floating-point number (locale aware).</td>
</tr>
<tr class="even">
<td><em>F</em></td>
<td>The argument is treated as a float and presented as a floating-point number (non-locale aware). Available as of PHP 5.0.3.</td>
</tr>
<tr class="odd">
<td><em>g</em></td>
<td><p>General format.</p>
<p>Let P equal the precision if nonzero, 6 if the precision is omitted, or 1 if the precision is zero. Then, if a conversion with style E would have an exponent of X:</p>
<p>If P &gt; X ≥ −4, the conversion is with style f and precision P − (X + 1). Otherwise, the conversion is with style e and precision P − 1.</p></td>
</tr>
<tr class="even">
<td><em>G</em></td>
<td>Like the <em>g</em> specifier but uses <em>E</em> and <em>f</em>.</td>
</tr>
<tr class="odd">
<td><em>o</em></td>
<td>The argument is treated as an integer and presented as an octal number.</td>
</tr>
<tr class="even">
<td><em>s</em></td>
<td>The argument is treated and presented as a string.</td>
</tr>
<tr class="odd">
<td><em>u</em></td>
<td>The argument is treated as an integer and presented as an unsigned decimal number.</td>
</tr>
<tr class="even">
<td><em>x</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with lowercase letters).</td>
</tr>
<tr class="odd">
<td><em>X</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with uppercase letters).</td>
</tr>
</tbody>
</table>

**Warning**
The *c* type specifier ignores padding and width

**Warning**
Attempting to use a combination of the string and width specifiers with
character sets that require more than one byte per character may result
in unexpected results

Variables will be co-erced to a suitable type for the specifier:

| Type      | Specifiers                        |
|-----------|-----------------------------------|
| *string*  | *s*                               |
| *integer* | *d*, *u*, *c*, *o*, *x*, *X*, *b* |
| *double*  | *g*, *G*, *e*, *E*, *f*, *F*      |

`...`  

### Return Values

Returns the length of the string written.

### Examples

**Example \#1 <span class="function">fprintf</span>: zero-padded
integers**

``` php
<?php
if (!($fp = fopen('date.txt', 'w'))) {
    return;
}

fprintf($fp, "%04d-%02d-%02d", $year, $month, $day);
// will write the formatted ISO date to date.txt
?>
```

**Example \#2 <span class="function">fprintf</span>: formatting
currency**

``` php
<?php
if (!($fp = fopen('currency.txt', 'w'))) {
    return;
}

$money1 = 68.75;
$money2 = 54.35;
$money = $money1 + $money2;
// echo $money will output "123.1";
$len = fprintf($fp, '%01.2f', $money);
// will write "123.10" to currency.txt

echo "wrote $len bytes to currency.txt";
// use the return value of fprintf to determine how many bytes we wrote
?>
```

### See Also

-   <span class="function">printf</span>
-   <span class="function">sprintf</span>
-   <span class="function">vprintf</span>
-   <span class="function">vsprintf</span>
-   <span class="function">vfprintf</span>
-   <span class="function">sscanf</span>
-   <span class="function">fscanf</span>
-   <span class="function">number\_format</span>
-   <span class="function">date</span>

get\_html\_translation\_table
=============================

Returns the translation table used by <span
class="function">htmlspecialchars</span> and <span
class="function">htmlentities</span>

### Description

<span class="type">array</span> <span
class="methodname">get\_html\_translation\_table</span> (\[ <span
class="methodparam"><span class="type">int</span> `$table`<span
class="initializer"> = HTML\_SPECIALCHARS</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = ENT\_COMPAT \| ENT\_HTML401</span></span> \[,
<span class="methodparam"><span class="type">string</span>
`$encoding`<span class="initializer"> = "UTF-8"</span></span> \]\]\] )

<span class="function">get\_html\_translation\_table</span> will return
the translation table that is used internally for <span
class="function">htmlspecialchars</span> and <span
class="function">htmlentities</span>.

> **Note**:
>
> Special characters can be encoded in several ways. E.g. *"* can be
> encoded as *&quot;*, *&\#34;* or *&\#x22*. <span
> class="function">get\_html\_translation\_table</span> returns only the
> form used by <span class="function">htmlspecialchars</span> and <span
> class="function">htmlentities</span>.

### Parameters

`table`  
Which table to return. Either **`HTML_ENTITIES`** or
**`HTML_SPECIALCHARS`**.

`flags`  
A bitmask of one or more of the following flags, which specify which
quotes the table will contain as well as which document type the table
is for. The default is *ENT\_COMPAT \| ENT\_HTML401*.

| Constant Name      | Description                                                                  |
|--------------------|------------------------------------------------------------------------------|
| **`ENT_COMPAT`**   | Table will contain entities for double-quotes, but not for single-quotes.    |
| **`ENT_QUOTES`**   | Table will contain entities for both double and single quotes.               |
| **`ENT_NOQUOTES`** | Table will neither contain entities for single quotes nor for double quotes. |
| **`ENT_HTML401`**  | Table for HTML 4.01.                                                         |
| **`ENT_XML1`**     | Table for XML 1.                                                             |
| **`ENT_XHTML`**    | Table for XHTML.                                                             |
| **`ENT_HTML5`**    | Table for HTML 5.                                                            |

`encoding`  
Encoding to use. If omitted, the default value for this argument is
ISO-8859-1 in versions of PHP prior to 5.4.0, and UTF-8 from PHP 5.4.0
onwards.

The following character sets are supported:

| Charset     | Aliases                      | Description                                                                                                                                                                                                                                                                                               |
|-------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ISO-8859-1  | ISO8859-1                    | Western European, Latin-1.                                                                                                                                                                                                                                                                                |
| ISO-8859-5  | ISO8859-5                    | Little used cyrillic charset (Latin/Cyrillic).                                                                                                                                                                                                                                                            |
| ISO-8859-15 | ISO8859-15                   | Western European, Latin-9. Adds the Euro sign, French and Finnish letters missing in Latin-1 (ISO-8859-1).                                                                                                                                                                                                |
| UTF-8       |                              | ASCII compatible multi-byte 8-bit Unicode.                                                                                                                                                                                                                                                                |
| cp866       | ibm866, 866                  | DOS-specific Cyrillic charset.                                                                                                                                                                                                                                                                            |
| cp1251      | Windows-1251, win-1251, 1251 | Windows-specific Cyrillic charset.                                                                                                                                                                                                                                                                        |
| cp1252      | Windows-1252, 1252           | Windows specific charset for Western European.                                                                                                                                                                                                                                                            |
| KOI8-R      | koi8-ru, koi8r               | Russian.                                                                                                                                                                                                                                                                                                  |
| BIG5        | 950                          | Traditional Chinese, mainly used in Taiwan.                                                                                                                                                                                                                                                               |
| GB2312      | 936                          | Simplified Chinese, national standard character set.                                                                                                                                                                                                                                                      |
| BIG5-HKSCS  |                              | Big5 with Hong Kong extensions, Traditional Chinese.                                                                                                                                                                                                                                                      |
| Shift\_JIS  | SJIS, SJIS-win, cp932, 932   | Japanese                                                                                                                                                                                                                                                                                                  |
| EUC-JP      | EUCJP, eucJP-win             | Japanese                                                                                                                                                                                                                                                                                                  |
| MacRoman    |                              | Charset that was used by Mac OS.                                                                                                                                                                                                                                                                          |
| *''*        |                              | An empty string activates detection from script encoding (Zend multibyte), <a href="/ini/core.html#ini.default-charset" class="link">default_charset</a> and current locale (see <span class="function">nl\_langinfo</span> and <span class="function">setlocale</span>), in this order. Not recommended. |

> **Note**: <span class="simpara"> Any other character sets are not
> recognized. The default encoding will be used instead and a warning
> will be emitted. </span>

### Return Values

Returns the translation table as an array, with the original characters
as keys and entities as values.

### Examples

**Example \#1 Translation Table Example**

``` php
<?php
var_dump(get_html_translation_table(HTML_ENTITIES, ENT_QUOTES | ENT_HTML5));
?>
```

The above example will output something similar to:

    array(1510) {
      ["
    "]=>
      string(9) "&NewLine;"
      ["!"]=>
      string(6) "&excl;"
      ["""]=>
      string(6) "&quot;"
      ["#"]=>
      string(5) "&num;"
      ["$"]=>
      string(8) "&dollar;"
      ["%"]=>
      string(8) "&percnt;"
      ["&"]=>
      string(5) "&amp;"
      ["'"]=>
      string(6) "&apos;"
      // ...
    }

### See Also

-   <span class="function">htmlspecialchars</span>
-   <span class="function">htmlentities</span>
-   <span class="function">html\_entity\_decode</span>

hebrev
======

Convert logical Hebrew text to visual text

### Description

<span class="type">string</span> <span class="methodname">hebrev</span>
( <span class="methodparam"><span class="type">string</span>
`$hebrew_text`</span> \[, <span class="methodparam"><span
class="type">int</span> `$max_chars_per_line`<span class="initializer">
= 0</span></span> \] )

Converts logical Hebrew text to visual text.

The function tries to avoid breaking words.

### Parameters

`hebrew_text`  
A Hebrew input string.

`max_chars_per_line`  
This optional parameter indicates maximum number of characters per line
that will be returned.

### Return Values

Returns the visual string.

### See Also

-   <span class="function">hebrevc</span>

hebrevc
=======

Convert logical Hebrew text to visual text with newline conversion

### Description

<span class="type">string</span> <span class="methodname">hebrevc</span>
( <span class="methodparam"><span class="type">string</span>
`$hebrew_text`</span> \[, <span class="methodparam"><span
class="type">int</span> `$max_chars_per_line`<span class="initializer">
= 0</span></span> \] )

This function is similar to <span class="function">hebrev</span> with
the difference that it converts newlines (\\n) to "\<br\>\\n".

The function tries to avoid breaking words.

### Parameters

`hebrew_text`  
A Hebrew input string.

`max_chars_per_line`  
This optional parameter indicates maximum number of characters per line
that will be returned.

### Return Values

Returns the visual string.

### See Also

-   <span class="function">hebrev</span>

hex2bin
=======

Decodes a hexadecimally encoded binary string

### Description

<span class="type">string</span> <span class="methodname">hex2bin</span>
( <span class="methodparam"><span class="type">string</span>
`$data`</span> )

Decodes a hexadecimally encoded binary string.

**Caution**

This function does *NOT* convert a hexadecimal number to a binary
number. This can be done using the <span
class="function">base\_convert</span> function.

### Parameters

`data`  
Hexadecimal representation of data.

### Return Values

Returns the binary representation of the given data or **`FALSE`** on
failure.

### Errors/Exceptions

If the hexadecimal input string is of odd length or invalid hexadecimal
string an **`E_WARNING`** level error is thrown.

### Examples

**Example \#1 <span class="function">hex2bin</span> example**

``` php
<?php
$hex = hex2bin("6578616d706c65206865782064617461");
var_dump($hex);
?>
```

The above example will output something similar to:

    string(16) "example hex data"

### See Also

-   <span class="function">bin2hex</span>
-   <span class="function">unpack</span>

html\_entity\_decode
====================

Convert HTML entities to their corresponding characters

### Description

<span class="type">string</span> <span
class="methodname">html\_entity\_decode</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = ENT\_COMPAT \|
ENT\_HTML401</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$encoding`<span class="initializer"> =
ini\_get("default\_charset")</span></span> \]\] )

<span class="function">html\_entity\_decode</span> is the opposite of
<span class="function">htmlentities</span> in that it converts HTML
entities in the `string` to their corresponding characters.

More precisely, this function decodes all the entities (including all
numeric entities) that a) are necessarily valid for the chosen document
type — i.e., for XML, this function does not decode named entities that
might be defined in some DTD — and b) whose character or characters are
in the coded character set associated with the chosen encoding and are
permitted in the chosen document type. All other entities are left as
is.

### Parameters

`string`  
The input string.

`flags`  
A bitmask of one or more of the following flags, which specify how to
handle quotes and which document type to use. The default is
*ENT\_COMPAT \| ENT\_HTML401*.

| Constant Name      | Description                                               |
|--------------------|-----------------------------------------------------------|
| **`ENT_COMPAT`**   | Will convert double-quotes and leave single-quotes alone. |
| **`ENT_QUOTES`**   | Will convert both double and single quotes.               |
| **`ENT_NOQUOTES`** | Will leave both double and single quotes unconverted.     |
| **`ENT_HTML401`**  | Handle code as HTML 4.01.                                 |
| **`ENT_XML1`**     | Handle code as XML 1.                                     |
| **`ENT_XHTML`**    | Handle code as XHTML.                                     |
| **`ENT_HTML5`**    | Handle code as HTML 5.                                    |

`encoding`  
An optional argument defining the encoding used when converting
characters.

If omitted, the default value of the `encoding` varies depending on the
PHP version in use. In PHP 5.6 and later, the
<a href="/ini/core.html#ini.default-charset" class="link">default_charset</a>
configuration option is used as the default value. PHP 5.4 and 5.5 will
use *UTF-8* as the default. Earlier versions of PHP use *ISO-8859-1*.

Although this argument is technically optional, you are highly
encouraged to specify the correct value for your code if you are using
PHP 5.5 or earlier, or if your
<a href="/ini/core.html#ini.default-charset" class="link">default_charset</a>
configuration option may be set incorrectly for the given input.

The following character sets are supported:

| Charset     | Aliases                      | Description                                                                                                                                                                                                                                                                                               |
|-------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ISO-8859-1  | ISO8859-1                    | Western European, Latin-1.                                                                                                                                                                                                                                                                                |
| ISO-8859-5  | ISO8859-5                    | Little used cyrillic charset (Latin/Cyrillic).                                                                                                                                                                                                                                                            |
| ISO-8859-15 | ISO8859-15                   | Western European, Latin-9. Adds the Euro sign, French and Finnish letters missing in Latin-1 (ISO-8859-1).                                                                                                                                                                                                |
| UTF-8       |                              | ASCII compatible multi-byte 8-bit Unicode.                                                                                                                                                                                                                                                                |
| cp866       | ibm866, 866                  | DOS-specific Cyrillic charset.                                                                                                                                                                                                                                                                            |
| cp1251      | Windows-1251, win-1251, 1251 | Windows-specific Cyrillic charset.                                                                                                                                                                                                                                                                        |
| cp1252      | Windows-1252, 1252           | Windows specific charset for Western European.                                                                                                                                                                                                                                                            |
| KOI8-R      | koi8-ru, koi8r               | Russian.                                                                                                                                                                                                                                                                                                  |
| BIG5        | 950                          | Traditional Chinese, mainly used in Taiwan.                                                                                                                                                                                                                                                               |
| GB2312      | 936                          | Simplified Chinese, national standard character set.                                                                                                                                                                                                                                                      |
| BIG5-HKSCS  |                              | Big5 with Hong Kong extensions, Traditional Chinese.                                                                                                                                                                                                                                                      |
| Shift\_JIS  | SJIS, SJIS-win, cp932, 932   | Japanese                                                                                                                                                                                                                                                                                                  |
| EUC-JP      | EUCJP, eucJP-win             | Japanese                                                                                                                                                                                                                                                                                                  |
| MacRoman    |                              | Charset that was used by Mac OS.                                                                                                                                                                                                                                                                          |
| *''*        |                              | An empty string activates detection from script encoding (Zend multibyte), <a href="/ini/core.html#ini.default-charset" class="link">default_charset</a> and current locale (see <span class="function">nl\_langinfo</span> and <span class="function">setlocale</span>), in this order. Not recommended. |

> **Note**: <span class="simpara"> Any other character sets are not
> recognized. The default encoding will be used instead and a warning
> will be emitted. </span>

### Return Values

Returns the decoded string.

### Examples

**Example \#1 Decoding HTML entities**

``` php
<?php
$orig = "I'll \"walk\" the <b>dog</b> now";

$a = htmlentities($orig);

$b = html_entity_decode($a);

echo $a; // I'll &quot;walk&quot; the &lt;b&gt;dog&lt;/b&gt; now

echo $b; // I'll "walk" the <b>dog</b> now
?>
```

### Notes

> **Note**:
>
> You might wonder why trim(html\_entity\_decode('&nbsp;')); doesn't
> reduce the string to an empty string, that's because the '&nbsp;'
> entity is not ASCII code 32 (which is stripped by <span
> class="function">trim</span>) but ASCII code 160 (0xa0) in the default
> ISO 8859-1 encoding.

### See Also

-   <span class="function">htmlentities</span>
-   <span class="function">htmlspecialchars</span>
-   <span class="function">get\_html\_translation\_table</span>
-   <span class="function">urldecode</span>

htmlentities
============

Convert all applicable characters to HTML entities

### Description

<span class="type">string</span> <span
class="methodname">htmlentities</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = ENT\_COMPAT \| ENT\_HTML401</span></span> \[,
<span class="methodparam"><span class="type">string</span>
`$encoding`<span class="initializer"> =
ini\_get("default\_charset")</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$double_encode`<span
class="initializer"> = **`TRUE`**</span></span> \]\]\] )

This function is identical to <span
class="function">htmlspecialchars</span> in all ways, except with <span
class="function">htmlentities</span>, all characters which have HTML
character entity equivalents are translated into these entities.

If you want to decode instead (the reverse) you can use <span
class="function">html\_entity\_decode</span>.

### Parameters

`string`  
The input string.

`flags`  
A bitmask of one or more of the following flags, which specify how to
handle quotes, invalid code unit sequences and the used document type.
The default is *ENT\_COMPAT \| ENT\_HTML401*.

| Constant Name        | Description                                                                                                                                                                                                                                                                         |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`ENT_COMPAT`**     | Will convert double-quotes and leave single-quotes alone.                                                                                                                                                                                                                           |
| **`ENT_QUOTES`**     | Will convert both double and single quotes.                                                                                                                                                                                                                                         |
| **`ENT_NOQUOTES`**   | Will leave both double and single quotes unconverted.                                                                                                                                                                                                                               |
| **`ENT_IGNORE`**     | Silently discard invalid code unit sequences instead of returning an empty string. Using this flag is discouraged as it <a href="http://unicode.org/reports/tr36/#Deletion_of_Noncharacters" class="link external">» may have security implications</a>.                            |
| **`ENT_SUBSTITUTE`** | Replace invalid code unit sequences with a Unicode Replacement Character U+FFFD (UTF-8) or &\#FFFD; (otherwise) instead of returning an empty string.                                                                                                                               |
| **`ENT_DISALLOWED`** | Replace invalid code points for the given document type with a Unicode Replacement Character U+FFFD (UTF-8) or &\#FFFD; (otherwise) instead of leaving them as is. This may be useful, for instance, to ensure the well-formedness of XML documents with embedded external content. |
| **`ENT_HTML401`**    | Handle code as HTML 4.01.                                                                                                                                                                                                                                                           |
| **`ENT_XML1`**       | Handle code as XML 1.                                                                                                                                                                                                                                                               |
| **`ENT_XHTML`**      | Handle code as XHTML.                                                                                                                                                                                                                                                               |
| **`ENT_HTML5`**      | Handle code as HTML 5.                                                                                                                                                                                                                                                              |

`encoding`  
An optional argument defining the encoding used when converting
characters.

If omitted, the default value of the `encoding` varies depending on the
PHP version in use. In PHP 5.6 and later, the
<a href="/ini/core.html#ini.default-charset" class="link">default_charset</a>
configuration option is used as the default value. PHP 5.4 and 5.5 will
use *UTF-8* as the default. Earlier versions of PHP use *ISO-8859-1*.

Although this argument is technically optional, you are highly
encouraged to specify the correct value for your code if you are using
PHP 5.5 or earlier, or if your
<a href="/ini/core.html#ini.default-charset" class="link">default_charset</a>
configuration option may be set incorrectly for the given input.

The following character sets are supported:

| Charset     | Aliases                      | Description                                                                                                                                                                                                                                                                                               |
|-------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ISO-8859-1  | ISO8859-1                    | Western European, Latin-1.                                                                                                                                                                                                                                                                                |
| ISO-8859-5  | ISO8859-5                    | Little used cyrillic charset (Latin/Cyrillic).                                                                                                                                                                                                                                                            |
| ISO-8859-15 | ISO8859-15                   | Western European, Latin-9. Adds the Euro sign, French and Finnish letters missing in Latin-1 (ISO-8859-1).                                                                                                                                                                                                |
| UTF-8       |                              | ASCII compatible multi-byte 8-bit Unicode.                                                                                                                                                                                                                                                                |
| cp866       | ibm866, 866                  | DOS-specific Cyrillic charset.                                                                                                                                                                                                                                                                            |
| cp1251      | Windows-1251, win-1251, 1251 | Windows-specific Cyrillic charset.                                                                                                                                                                                                                                                                        |
| cp1252      | Windows-1252, 1252           | Windows specific charset for Western European.                                                                                                                                                                                                                                                            |
| KOI8-R      | koi8-ru, koi8r               | Russian.                                                                                                                                                                                                                                                                                                  |
| BIG5        | 950                          | Traditional Chinese, mainly used in Taiwan.                                                                                                                                                                                                                                                               |
| GB2312      | 936                          | Simplified Chinese, national standard character set.                                                                                                                                                                                                                                                      |
| BIG5-HKSCS  |                              | Big5 with Hong Kong extensions, Traditional Chinese.                                                                                                                                                                                                                                                      |
| Shift\_JIS  | SJIS, SJIS-win, cp932, 932   | Japanese                                                                                                                                                                                                                                                                                                  |
| EUC-JP      | EUCJP, eucJP-win             | Japanese                                                                                                                                                                                                                                                                                                  |
| MacRoman    |                              | Charset that was used by Mac OS.                                                                                                                                                                                                                                                                          |
| *''*        |                              | An empty string activates detection from script encoding (Zend multibyte), <a href="/ini/core.html#ini.default-charset" class="link">default_charset</a> and current locale (see <span class="function">nl\_langinfo</span> and <span class="function">setlocale</span>), in this order. Not recommended. |

> **Note**: <span class="simpara"> Any other character sets are not
> recognized. The default encoding will be used instead and a warning
> will be emitted. </span>

`double_encode`  
When `double_encode` is turned off PHP will not encode existing html
entities. The default is to convert everything.

### Return Values

Returns the encoded string.

If the input `string` contains an invalid code unit sequence within the
given `encoding` an empty string will be returned, unless either the
**`ENT_IGNORE`** or **`ENT_SUBSTITUTE`** flags are set.

### Examples

**Example \#1 A <span class="function">htmlentities</span> example**

``` php
<?php
$str = "A 'quote' is <b>bold</b>";

// Outputs: A 'quote' is &lt;b&gt;bold&lt;/b&gt;
echo htmlentities($str);

// Outputs: A &#039;quote&#039; is &lt;b&gt;bold&lt;/b&gt;
echo htmlentities($str, ENT_QUOTES);
?>
```

**Example \#2 Usage of **`ENT_IGNORE`****

``` php
<?php
$str = "\x8F!!!";

// Outputs an empty string
echo htmlentities($str, ENT_QUOTES, "UTF-8");

// Outputs "!!!"
echo htmlentities($str, ENT_QUOTES | ENT_IGNORE, "UTF-8");
?>
```

### See Also

-   <span class="function">html\_entity\_decode</span>
-   <span class="function">get\_html\_translation\_table</span>
-   <span class="function">htmlspecialchars</span>
-   <span class="function">nl2br</span>
-   <span class="function">urlencode</span>

htmlspecialchars\_decode
========================

Convert special HTML entities back to characters

### Description

<span class="type">string</span> <span
class="methodname">htmlspecialchars\_decode</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = ENT\_COMPAT \|
ENT\_HTML401</span></span> \] )

This function is the opposite of <span
class="function">htmlspecialchars</span>. It converts special HTML
entities back to characters.

The converted entities are: *&amp;*, *&quot;* (when **`ENT_NOQUOTES`**
is not set), *&\#039;* (when **`ENT_QUOTES`** is set), *&lt;* and
*&gt;*.

### Parameters

`string`  
The string to decode.

`flags`  
A bitmask of one or more of the following flags, which specify how to
handle quotes and which document type to use. The default is
*ENT\_COMPAT \| ENT\_HTML401*.

| Constant Name      | Description                                               |
|--------------------|-----------------------------------------------------------|
| **`ENT_COMPAT`**   | Will convert double-quotes and leave single-quotes alone. |
| **`ENT_QUOTES`**   | Will convert both double and single quotes.               |
| **`ENT_NOQUOTES`** | Will leave both double and single quotes unconverted.     |
| **`ENT_HTML401`**  | Handle code as HTML 4.01.                                 |
| **`ENT_XML1`**     | Handle code as XML 1.                                     |
| **`ENT_XHTML`**    | Handle code as XHTML.                                     |
| **`ENT_HTML5`**    | Handle code as HTML 5.                                    |

### Return Values

Returns the decoded string.

### Examples

**Example \#1 A <span class="function">htmlspecialchars\_decode</span>
example**

``` php
<?php
$str = "<p>this -&gt; &quot;</p>\n";

echo htmlspecialchars_decode($str);

// note that here the quotes aren't converted
echo htmlspecialchars_decode($str, ENT_NOQUOTES);
?>
```

The above example will output:

    <p>this -> "</p>
    <p>this -> &quot;</p>

### See Also

-   <span class="function">htmlspecialchars</span>
-   <span class="function">html\_entity\_decode</span>
-   <span class="function">get\_html\_translation\_table</span>

htmlspecialchars
================

Convert special characters to HTML entities

### Description

<span class="type">string</span> <span
class="methodname">htmlspecialchars</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = ENT\_COMPAT \|
ENT\_HTML401</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$encoding`<span class="initializer"> =
ini\_get("default\_charset")</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$double_encode`<span
class="initializer"> = **`TRUE`**</span></span> \]\]\] )

Certain characters have special significance in HTML, and should be
represented by HTML entities if they are to preserve their meanings.
This function returns a string with these conversions made. If you
require all input substrings that have associated named entities to be
translated, use <span class="function">htmlentities</span> instead.

If the input string passed to this function and the final document share
the same character set, this function is sufficient to prepare input for
inclusion in most contexts of an HTML document. If, however, the input
can represent characters that are not coded in the final document
character set and you wish to retain those characters (as numeric or
named entities), both this function and <span
class="function">htmlentities</span> (which only encodes substrings that
have named entity equivalents) may be insufficient. You may have to use
<span class="function">mb\_encode\_numericentity</span> instead.

| Character           | Replacement                                                                                                                                   |
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| *&* (ampersand)     | *&amp;*                                                                                                                                       |
| *"* (double quote)  | *&quot;*, unless **`ENT_NOQUOTES`** is set                                                                                                    |
| *'* (single quote)  | *&\#039;* (for **`ENT_HTML401`**) or *&apos;* (for **`ENT_XML1`**, **`ENT_XHTML`** or **`ENT_HTML5`**), but only when **`ENT_QUOTES`** is set |
| *\<* (less than)    | *&lt;*                                                                                                                                        |
| *\>* (greater than) | *&gt;*                                                                                                                                        |

### Parameters

`string`  
The <span class="type">string</span> being converted.

`flags`  
A bitmask of one or more of the following flags, which specify how to
handle quotes, invalid code unit sequences and the used document type.
The default is *ENT\_COMPAT \| ENT\_HTML401*.

| Constant Name        | Description                                                                                                                                                                                                                                                                          |
|----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`ENT_COMPAT`**     | Will convert double-quotes and leave single-quotes alone.                                                                                                                                                                                                                            |
| **`ENT_QUOTES`**     | Will convert both double and single quotes.                                                                                                                                                                                                                                          |
| **`ENT_NOQUOTES`**   | Will leave both double and single quotes unconverted.                                                                                                                                                                                                                                |
| **`ENT_IGNORE`**     | Silently discard invalid code unit sequences instead of returning an empty string. Using this flag is discouraged as it <a href="http://unicode.org/reports/tr36/#Deletion_of_Noncharacters" class="link external">» may have security implications</a>.                             |
| **`ENT_SUBSTITUTE`** | Replace invalid code unit sequences with a Unicode Replacement Character U+FFFD (UTF-8) or &\#xFFFD; (otherwise) instead of returning an empty string.                                                                                                                               |
| **`ENT_DISALLOWED`** | Replace invalid code points for the given document type with a Unicode Replacement Character U+FFFD (UTF-8) or &\#xFFFD; (otherwise) instead of leaving them as is. This may be useful, for instance, to ensure the well-formedness of XML documents with embedded external content. |
| **`ENT_HTML401`**    | Handle code as HTML 4.01.                                                                                                                                                                                                                                                            |
| **`ENT_XML1`**       | Handle code as XML 1.                                                                                                                                                                                                                                                                |
| **`ENT_XHTML`**      | Handle code as XHTML.                                                                                                                                                                                                                                                                |
| **`ENT_HTML5`**      | Handle code as HTML 5.                                                                                                                                                                                                                                                               |

`encoding`  
An optional argument defining the encoding used when converting
characters.

If omitted, the default value of the `encoding` varies depending on the
PHP version in use. In PHP 5.6 and later, the
<a href="/ini/core.html#ini.default-charset" class="link">default_charset</a>
configuration option is used as the default value. PHP 5.4 and 5.5 will
use *UTF-8* as the default. Earlier versions of PHP use *ISO-8859-1*.

Although this argument is technically optional, you are highly
encouraged to specify the correct value for your code if you are using
PHP 5.5 or earlier, or if your
<a href="/ini/core.html#ini.default-charset" class="link">default_charset</a>
configuration option may be set incorrectly for the given input.

For the purposes of this function, the encodings *ISO-8859-1*,
*ISO-8859-15*, *UTF-8*, *cp866*, *cp1251*, *cp1252*, and *KOI8-R* are
effectively equivalent, provided the `string` itself is valid for the
encoding, as the characters affected by <span
class="function">htmlspecialchars</span> occupy the same positions in
all of these encodings.

The following character sets are supported:

| Charset     | Aliases                      | Description                                                                                                                                                                                                                                                                                               |
|-------------|------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ISO-8859-1  | ISO8859-1                    | Western European, Latin-1.                                                                                                                                                                                                                                                                                |
| ISO-8859-5  | ISO8859-5                    | Little used cyrillic charset (Latin/Cyrillic).                                                                                                                                                                                                                                                            |
| ISO-8859-15 | ISO8859-15                   | Western European, Latin-9. Adds the Euro sign, French and Finnish letters missing in Latin-1 (ISO-8859-1).                                                                                                                                                                                                |
| UTF-8       |                              | ASCII compatible multi-byte 8-bit Unicode.                                                                                                                                                                                                                                                                |
| cp866       | ibm866, 866                  | DOS-specific Cyrillic charset.                                                                                                                                                                                                                                                                            |
| cp1251      | Windows-1251, win-1251, 1251 | Windows-specific Cyrillic charset.                                                                                                                                                                                                                                                                        |
| cp1252      | Windows-1252, 1252           | Windows specific charset for Western European.                                                                                                                                                                                                                                                            |
| KOI8-R      | koi8-ru, koi8r               | Russian.                                                                                                                                                                                                                                                                                                  |
| BIG5        | 950                          | Traditional Chinese, mainly used in Taiwan.                                                                                                                                                                                                                                                               |
| GB2312      | 936                          | Simplified Chinese, national standard character set.                                                                                                                                                                                                                                                      |
| BIG5-HKSCS  |                              | Big5 with Hong Kong extensions, Traditional Chinese.                                                                                                                                                                                                                                                      |
| Shift\_JIS  | SJIS, SJIS-win, cp932, 932   | Japanese                                                                                                                                                                                                                                                                                                  |
| EUC-JP      | EUCJP, eucJP-win             | Japanese                                                                                                                                                                                                                                                                                                  |
| MacRoman    |                              | Charset that was used by Mac OS.                                                                                                                                                                                                                                                                          |
| *''*        |                              | An empty string activates detection from script encoding (Zend multibyte), <a href="/ini/core.html#ini.default-charset" class="link">default_charset</a> and current locale (see <span class="function">nl\_langinfo</span> and <span class="function">setlocale</span>), in this order. Not recommended. |

> **Note**: <span class="simpara"> Any other character sets are not
> recognized. The default encoding will be used instead and a warning
> will be emitted. </span>

`double_encode`  
When `double_encode` is turned off PHP will not encode existing html
entities, the default is to convert everything.

### Return Values

The converted <span class="type">string</span>.

If the input `string` contains an invalid code unit sequence within the
given `encoding` an empty string will be returned, unless either the
**`ENT_IGNORE`** or **`ENT_SUBSTITUTE`** flags are set.

### Examples

**Example \#1 <span class="function">htmlspecialchars</span> example**

``` php
<?php
$new = htmlspecialchars("<a href='test'>Test</a>", ENT_QUOTES);
echo $new; // &lt;a href=&#039;test&#039;&gt;Test&lt;/a&gt;
?>
```

### Notes

> **Note**:
>
> Note that this function does not translate anything beyond what is
> listed above. For full entity translation, see <span
> class="function">htmlentities</span>.

> **Note**:
>
> In case of an ambiguous `flags` value, the following rules apply:
>
> -   <span class="simpara"> When neither of **`ENT_COMPAT`**,
>     **`ENT_QUOTES`**, **`ENT_NOQUOTES`** is present, the default is
>     **`ENT_NOQUOTES`**. </span>
> -   <span class="simpara"> When more than one of **`ENT_COMPAT`**,
>     **`ENT_QUOTES`**, **`ENT_NOQUOTES`** is present, **`ENT_QUOTES`**
>     takes the highest precedence, followed by **`ENT_COMPAT`**.
>     </span>
> -   <span class="simpara"> When neither of **`ENT_HTML401`**,
>     **`ENT_HTML5`**, **`ENT_XHTML`**, **`ENT_XML1`** is present, the
>     default is **`ENT_HTML401`**. </span>
> -   <span class="simpara"> When more than one of **`ENT_HTML401`**,
>     **`ENT_HTML5`**, **`ENT_XHTML`**, **`ENT_XML1`** is present,
>     **`ENT_HTML5`** takes the highest precedence, followed by
>     **`ENT_XHTML`**, **`ENT_XML1`** and **`ENT_HTML401`**. </span>
> -   <span class="simpara"> When more than one of **`ENT_DISALLOWED`**,
>     **`ENT_IGNORE`**, **`ENT_SUBSTITUTE`** are present,
>     **`ENT_IGNORE`** takes the highest precedence, followed by
>     **`ENT_SUBSTITUTE`**. </span>

### See Also

-   <span class="function">get\_html\_translation\_table</span>
-   <span class="function">htmlspecialchars\_decode</span>
-   <span class="function">strip\_tags</span>
-   <span class="function">htmlentities</span>
-   <span class="function">nl2br</span>

implode
=======

Join array elements with a string

### Description

<span class="type">string</span> <span class="methodname">implode</span>
( <span class="methodparam"><span class="type">string</span>
`$glue`</span> , <span class="methodparam"><span
class="type">array</span> `$pieces`</span> )

<span class="type">string</span> <span class="methodname">implode</span>
( <span class="methodparam"><span class="type">array</span>
`$pieces`</span> )

Join array elements with a `glue` string.

> **Note**:
>
> <span class="function">implode</span> can, for historical reasons,
> accept its parameters in either order. For consistency with <span
> class="function">explode</span>, however, it is *deprecated* not to
> use the documented order of arguments.

### Parameters

`glue`  
Defaults to an empty string.

`pieces`  
The array of strings to implode.

### Return Values

Returns a string containing a string representation of all the array
elements in the same order, with the glue string between each element.

### Changelog

| Version | Description                                                                                                    |
|---------|----------------------------------------------------------------------------------------------------------------|
| 7.4.0   | Passing the `glue` after the `pieces` (i.e. not using the documented order of parameters) has been deprecated. |

### Examples

**Example \#1 <span class="function">implode</span> example**

``` php
<?php

$array = array('lastname', 'email', 'phone');
$comma_separated = implode(",", $array);

echo $comma_separated; // lastname,email,phone

// Empty string when using an empty array:
var_dump(implode('hello', array())); // string(0) ""

?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">explode</span>
-   <span class="function">preg\_split</span>
-   <span class="function">http\_build\_query</span>

join
====

Alias of <span class="function">implode</span>

### Description

This function is an alias of: <span class="function">implode</span>.

lcfirst
=======

Make a string's first character lowercase

### Description

<span class="type">string</span> <span class="methodname">lcfirst</span>
( <span class="methodparam"><span class="type">string</span>
`$str`</span> )

Returns a string with the first character of `str` lowercased if that
character is alphabetic.

Note that 'alphabetic' is determined by the current locale. For
instance, in the default "C" locale characters such as umlaut-a (ä) will
not be converted.

### Parameters

`str`  
The input string.

### Return Values

Returns the resulting string.

### Examples

**Example \#1 <span class="function">lcfirst</span> example**

``` php
<?php
$foo = 'HelloWorld';
$foo = lcfirst($foo);             // helloWorld

$bar = 'HELLO WORLD!';
$bar = lcfirst($bar);             // hELLO WORLD!
$bar = lcfirst(strtoupper($bar)); // hELLO WORLD!
?>
```

### See Also

-   <span class="function">ucfirst</span>
-   <span class="function">strtolower</span>
-   <span class="function">strtoupper</span>
-   <span class="function">ucwords</span>

levenshtein
===========

Calculate Levenshtein distance between two strings

### Description

<span class="type">int</span> <span
class="methodname">levenshtein</span> ( <span class="methodparam"><span
class="type">string</span> `$str1`</span> , <span
class="methodparam"><span class="type">string</span> `$str2`</span> )

<span class="type">int</span> <span
class="methodname">levenshtein</span> ( <span class="methodparam"><span
class="type">string</span> `$str1`</span> , <span
class="methodparam"><span class="type">string</span> `$str2`</span> ,
<span class="methodparam"><span class="type">int</span>
`$cost_ins`</span> , <span class="methodparam"><span
class="type">int</span> `$cost_rep`</span> , <span
class="methodparam"><span class="type">int</span> `$cost_del`</span> )

The Levenshtein distance is defined as the minimal number of characters
you have to replace, insert or delete to transform `str1` into `str2`.
The complexity of the algorithm is *O(m\*n)*, where *n* and *m* are the
length of `str1` and `str2` (rather good when compared to <span
class="function">similar\_text</span>, which is O(max(n,m)\*\*3), but
still expensive).

In its simplest form the function will take only the two strings as
parameter and will calculate just the number of insert, replace and
delete operations needed to transform `str1` into `str2`.

A second variant will take three additional parameters that define the
cost of insert, replace and delete operations. This is more general and
adaptive than variant one, but not as efficient.

### Parameters

`str1`  
One of the strings being evaluated for Levenshtein distance.

`str2`  
One of the strings being evaluated for Levenshtein distance.

`cost_ins`  
Defines the cost of insertion.

`cost_rep`  
Defines the cost of replacement.

`cost_del`  
Defines the cost of deletion.

### Return Values

This function returns the Levenshtein-Distance between the two argument
strings or -1, if one of the argument strings is longer than the limit
of 255 characters.

### Examples

**Example \#1 <span class="function">levenshtein</span> example**

``` php
<?php
// input misspelled word
$input = 'carrrot';

// array of words to check against
$words  = array('apple','pineapple','banana','orange',
                'radish','carrot','pea','bean','potato');

// no shortest distance found, yet
$shortest = -1;

// loop through words to find the closest
foreach ($words as $word) {

    // calculate the distance between the input word,
    // and the current word
    $lev = levenshtein($input, $word);

    // check for an exact match
    if ($lev == 0) {

        // closest word is this one (exact match)
        $closest = $word;
        $shortest = 0;

        // break out of the loop; we've found an exact match
        break;
    }

    // if this distance is less than the next found shortest
    // distance, OR if a next shortest word has not yet been found
    if ($lev <= $shortest || $shortest < 0) {
        // set the closest match, and shortest distance
        $closest  = $word;
        $shortest = $lev;
    }
}

echo "Input word: $input\n";
if ($shortest == 0) {
    echo "Exact match found: $closest\n";
} else {
    echo "Did you mean: $closest?\n";
}

?>
```

The above example will output:

    Input word: carrrot
    Did you mean: carrot?

### See Also

-   <span class="function">soundex</span>
-   <span class="function">similar\_text</span>
-   <span class="function">metaphone</span>

localeconv
==========

Get numeric formatting information

### Description

<span class="type">array</span> <span
class="methodname">localeconv</span> ( <span
class="methodparam">void</span> )

Returns an associative array containing localized numeric and monetary
formatting information.

### Return Values

<span class="function">localeconv</span> returns data based upon the
current locale as set by <span class="function">setlocale</span>. The
associative array that is returned contains the following fields:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Array element</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>decimal_point</td>
<td>Decimal point character</td>
</tr>
<tr class="even">
<td>thousands_sep</td>
<td>Thousands separator</td>
</tr>
<tr class="odd">
<td>grouping</td>
<td>Array containing numeric groupings</td>
</tr>
<tr class="even">
<td>int_curr_symbol</td>
<td>International currency symbol (i.e. USD)</td>
</tr>
<tr class="odd">
<td>currency_symbol</td>
<td>Local currency symbol (i.e. $)</td>
</tr>
<tr class="even">
<td>mon_decimal_point</td>
<td>Monetary decimal point character</td>
</tr>
<tr class="odd">
<td>mon_thousands_sep</td>
<td>Monetary thousands separator</td>
</tr>
<tr class="even">
<td>mon_grouping</td>
<td>Array containing monetary groupings</td>
</tr>
<tr class="odd">
<td>positive_sign</td>
<td>Sign for positive values</td>
</tr>
<tr class="even">
<td>negative_sign</td>
<td>Sign for negative values</td>
</tr>
<tr class="odd">
<td>int_frac_digits</td>
<td>International fractional digits</td>
</tr>
<tr class="even">
<td>frac_digits</td>
<td>Local fractional digits</td>
</tr>
<tr class="odd">
<td>p_cs_precedes</td>
<td><strong><code>TRUE</code></strong> if currency_symbol precedes a positive value, <strong><code>FALSE</code></strong> if it succeeds one</td>
</tr>
<tr class="even">
<td>p_sep_by_space</td>
<td><strong><code>TRUE</code></strong> if a space separates currency_symbol from a positive value, <strong><code>FALSE</code></strong> otherwise</td>
</tr>
<tr class="odd">
<td>n_cs_precedes</td>
<td><strong><code>TRUE</code></strong> if currency_symbol precedes a negative value, <strong><code>FALSE</code></strong> if it succeeds one</td>
</tr>
<tr class="even">
<td>n_sep_by_space</td>
<td><strong><code>TRUE</code></strong> if a space separates currency_symbol from a negative value, <strong><code>FALSE</code></strong> otherwise</td>
</tr>
<tr class="odd">
<td>p_sign_posn</td>
<td><ul>
<li>0 - Parentheses surround the quantity and currency_symbol</li>
<li>1 - The sign string precedes the quantity and currency_symbol</li>
<li>2 - The sign string succeeds the quantity and currency_symbol</li>
<li>3 - The sign string immediately precedes the currency_symbol</li>
<li>4 - The sign string immediately succeeds the currency_symbol</li>
</ul></td>
</tr>
<tr class="even">
<td>n_sign_posn</td>
<td><ul>
<li>0 - Parentheses surround the quantity and currency_symbol</li>
<li>1 - The sign string precedes the quantity and currency_symbol</li>
<li>2 - The sign string succeeds the quantity and currency_symbol</li>
<li>3 - The sign string immediately precedes the currency_symbol</li>
<li>4 - The sign string immediately succeeds the currency_symbol</li>
</ul></td>
</tr>
</tbody>
</table>

The *p\_sign\_posn*, and *n\_sign\_posn* contain a string of formatting
options. Each number representing one of the above listed conditions.

The grouping fields contain arrays that define the way numbers should be
grouped. For example, the monetary grouping field for the nl\_NL locale
(in UTF-8 mode with the euro sign), would contain a 2 item array with
the values 3 and 3. The higher the index in the array, the farther left
the grouping is. If an array element is equal to **`CHAR_MAX`**, no
further grouping is done. If an array element is equal to 0, the
previous element should be used.

### Examples

**Example \#1 <span class="function">localeconv</span> example**

``` php
<?php
if (false !== setlocale(LC_ALL, 'nl_NL.UTF-8@euro')) {
    $locale_info = localeconv();
    print_r($locale_info);
}
?>
```

The above example will output:

    Array
    (
        [decimal_point] => .
        [thousands_sep] =>
        [int_curr_symbol] => EUR
        [currency_symbol] => €
        [mon_decimal_point] => ,
        [mon_thousands_sep] =>
        [positive_sign] =>
        [negative_sign] => -
        [int_frac_digits] => 2
        [frac_digits] => 2
        [p_cs_precedes] => 1
        [p_sep_by_space] => 1
        [n_cs_precedes] => 1
        [n_sep_by_space] => 1
        [p_sign_posn] => 1
        [n_sign_posn] => 2
        [grouping] => Array
            (
            )

        [mon_grouping] => Array
            (
                [0] => 3
                [1] => 3
            )

    )

### See Also

-   <span class="function">setlocale</span>

ltrim
=====

Strip whitespace (or other characters) from the beginning of a string

### Description

<span class="type">string</span> <span class="methodname">ltrim</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$character_mask`</span> \] )

Strip whitespace (or other characters) from the beginning of a string.

### Parameters

`str`  
The input string.

`character_mask`  
You can also specify the characters you want to strip, by means of the
`character_mask` parameter. Simply list all characters that you want to
be stripped. With *..* you can specify a range of characters.

### Return Values

This function returns a string with whitespace stripped from the
beginning of `str`. Without the second parameter, <span
class="function">ltrim</span> will strip these characters:

-   <span class="simpara"> " " (ASCII *32* (*0x20*)), an ordinary space.
    </span>
-   <span class="simpara"> "\\t" (ASCII *9* (*0x09*)), a tab. </span>
-   <span class="simpara"> "\\n" (ASCII *10* (*0x0A*)), a new line (line
    feed). </span>
-   <span class="simpara"> "\\r" (ASCII *13* (*0x0D*)), a carriage
    return. </span>
-   <span class="simpara"> "\\0" (ASCII *0* (*0x00*)), the *NUL*-byte.
    </span>
-   <span class="simpara"> "\\x0B" (ASCII *11* (*0x0B*)), a vertical
    tab. </span>

### Examples

**Example \#1 Usage example of <span class="function">ltrim</span>**

``` php
<?php

$text = "\t\tThese are a few words :) ...  ";
$binary = "\x09Example string\x0A";
$hello  = "Hello World";
var_dump($text, $binary, $hello);

print "\n";


$trimmed = ltrim($text);
var_dump($trimmed);

$trimmed = ltrim($text, " \t.");
var_dump($trimmed);

$trimmed = ltrim($hello, "Hdle");
var_dump($trimmed);

// trim the ASCII control characters at the beginning of $binary
// (from 0 to 31 inclusive)
$clean = ltrim($binary, "\x00..\x1F");
var_dump($clean);

?>
```

The above example will output:

    string(32) "        These are a few words :) ...  "
    string(16) "    Example string
    "
    string(11) "Hello World"

    string(30) "These are a few words :) ...  "
    string(30) "These are a few words :) ...  "
    string(7) "o World"
    string(15) "Example string
    "

### See Also

-   <span class="function">trim</span>
-   <span class="function">rtrim</span>

md5\_file
=========

Calculates the md5 hash of a given file

### Description

<span class="type">string</span> <span
class="methodname">md5\_file</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$raw_output`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Calculates the MD5 hash of the file specified by the `filename`
parameter using the
<a href="http://www.faqs.org/rfcs/rfc1321" class="link external">» RSA Data Security, Inc. MD5 Message-Digest Algorithm</a>,
and returns that hash. The hash is a 32-character hexadecimal number.

### Parameters

`filename`  
The filename

`raw_output`  
When **`TRUE`**, returns the digest in raw binary format with a length
of 16.

### Return Values

Returns a string on success, **`FALSE`** otherwise.

### Examples

**Example \#1 Usage example of <span class="function">md5\_file</span>**

``` php
<?php
$file = 'php-5.3.0alpha2-Win32-VC9-x64.zip';

echo 'MD5 file hash of ' . $file . ': ' . md5_file($file);
?>
```

### See Also

-   <span class="function">md5</span>
-   <span class="function">sha1\_file</span>
-   <span class="function">crc32</span>

md5
===

Calculate the md5 hash of a string

**Warning**

It is not recommended to use this function to secure passwords, due to
the fast nature of this hashing algorithm. See the
<a href="/faq/passwords.html#faq.passwords.fasthash" class="link">Password Hashing FAQ</a>
for details and best practices.

### Description

<span class="type">string</span> <span class="methodname">md5</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$raw_output`<span class="initializer"> = **`FALSE`**</span></span> \] )

Calculates the MD5 hash of `str` using the
<a href="http://www.faqs.org/rfcs/rfc1321" class="link external">» RSA Data Security, Inc. MD5 Message-Digest Algorithm</a>,
and returns that hash.

### Parameters

`str`  
The string.

`raw_output`  
If the optional `raw_output` is set to **`TRUE`**, then the md5 digest
is instead returned in raw binary format with a length of 16.

### Return Values

Returns the hash as a 32-character hexadecimal number.

### Examples

**Example \#1 A <span class="function">md5</span> example**

``` php
<?php
$str = 'apple';

if (md5($str) === '1f3870be274f6c49b3e31a0c6728957f') {
    echo "Would you like a green or red apple?";
}
?>
```

### See Also

-   <span class="function">md5\_file</span>
-   <span class="function">sha1\_file</span>
-   <span class="function">crc32</span>
-   <span class="function">sha1</span>
-   <span class="function">hash</span>
-   <span class="function">crypt</span>
-   <span class="function">password\_hash</span>

metaphone
=========

Calculate the metaphone key of a string

### Description

<span class="type">string</span> <span
class="methodname">metaphone</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> \[, <span
class="methodparam"><span class="type">int</span> `$phonemes`<span
class="initializer"> = 0</span></span> \] )

Calculates the metaphone key of `str`.

Similar to <span class="function">soundex</span> metaphone creates the
same key for similar sounding words. It's more accurate than <span
class="function">soundex</span> as it knows the basic rules of English
pronunciation. The metaphone generated keys are of variable length.

Metaphone was developed by Lawrence Philips \<lphilips at verity dot
com\>. It is described in \["Practical Algorithms for Programmers",
Binstock & Rex, Addison Wesley, 1995\].

### Parameters

`str`  
The input string.

`phonemes`  
This parameter restricts the returned metaphone key to `phonemes`
characters in length. The default value of *0* means no restriction.

### Return Values

Returns the metaphone key as a string, or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">metaphone</span> basic example**

``` php
<?php
var_dump(metaphone('programming'));
var_dump(metaphone('programmer'));
?>
```

The above example will output something similar to:

    string(7) "PRKRMNK"
    string(6) "PRKRMR"

**Example \#2 Using the `phonemes` parameter**

``` php
<?php
var_dump(metaphone('programming', 5));
var_dump(metaphone('programmer', 5));
?>
```

The above example will output something similar to:

    string(5) "PRKRM"
    string(5) "PRKRM"

money\_format
=============

Formats a number as a currency string

**Warning**

This function has been *DEPRECATED* as of PHP 7.4.0. Relying on this
function is highly discouraged.

### Description

<span class="type">string</span> <span
class="methodname">money\_format</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> ,
<span class="methodparam"><span class="type">float</span>
`$number`</span> )

<span class="function">money\_format</span> returns a formatted version
of `number`. This function wraps the C library function <span
class="function">strfmon</span>, with the difference that this
implementation converts only one number at a time.

### Parameters

`format`  
The format specification consists of the following sequence:

-   a *%* character

-   optional flags

-   optional field width

-   optional left precision

-   optional right precision

-   a required conversion character

##### Flags

One or more of the optional flags below can be used:

*=*<span class="replaceable">f</span>  
The character *=* followed by a (single byte) character <span
class="replaceable">f</span> to be used as the numeric fill character.
The default fill character is space.

*^*  
Disable the use of grouping characters (as defined by the current
locale).

*+* or *(*  
Specify the formatting style for positive and negative numbers. If *+*
is used, the locale's equivalent for *+* and *-* will be used. If *(* is
used, negative amounts are enclosed in parenthesis. If no specification
is given, the default is *+*.

*!*  
Suppress the currency symbol from the output string.

*-*  
If present, it will make all fields left-justified (padded to the
right), as opposed to the default which is for the fields to be
right-justified (padded to the left).

##### Field width

<span class="replaceable">w</span>  
A decimal digit string specifying a minimum field width. Field will be
right-justified unless the flag *-* is used. Default value is 0 (zero).

##### Left precision

*\#*<span class="replaceable">n</span>  
The maximum number of digits (<span class="replaceable">n</span>)
expected to the left of the decimal character (e.g. the decimal point).
It is used usually to keep formatted output aligned in the same columns,
using the fill character if the number of digits is less than <span
class="replaceable">n</span>. If the number of actual digits is bigger
than <span class="replaceable">n</span>, then this specification is
ignored.

If grouping has not been suppressed using the *^* flag, grouping
separators will be inserted before the fill characters (if any) are
added. Grouping separators will not be applied to fill characters, even
if the fill character is a digit.

To ensure alignment, any characters appearing before or after the number
in the formatted output such as currency or sign symbols are padded as
necessary with space characters to make their positive and negative
formats an equal length.

##### Right precision

*.*<span class="replaceable">p</span>  
A period followed by the number of digits (<span
class="replaceable">p</span>) after the decimal character. If the value
of <span class="replaceable">p</span> is 0 (zero), the decimal character
and the digits to its right will be omitted. If no right precision is
included, the default will dictated by the current locale in use. The
amount being formatted is rounded to the specified number of digits
prior to formatting.

##### Conversion characters

*i*  
The number is formatted according to the locale's international currency
format (e.g. for the USA locale: USD 1,234.56).

*n*  
The number is formatted according to the locale's national currency
format (e.g. for the de\_DE locale: EU1.234,56).

*%*  
Returns the *%* character.

`number`  
The number to be formatted.

### Return Values

Returns the formatted string. Characters before and after the formatting
string will be returned unchanged. Non-numeric `number` causes returning
**`NULL`** and emitting **`E_WARNING`**.

### Changelog

| Version | Description                                                                                                      |
|---------|------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | This function has been deprecated. Instead, use <span class="methodname">NumberFormatter::formatCurrency</span>. |

### Notes

> **Note**:
>
> The function <span class="function">money\_format</span> is only
> defined if the system has strfmon capabilities. For example, Windows
> does not, so <span class="function">money\_format</span> is undefined
> in Windows.

> **Note**:
>
> The **`LC_MONETARY`** category of the locale settings, affects the
> behavior of this function. Use <span class="function">setlocale</span>
> to set to the appropriate default locale before using this function.

### Examples

**Example \#1 <span class="function">money\_format</span> Example**

We will use different locales and format specifications to illustrate
the use of this function.

``` php
<?php

$number = 1234.56;

// let's print the international format for the en_US locale
setlocale(LC_MONETARY, 'en_US');
echo money_format('%i', $number) . "\n";
// USD 1,234.56

// Italian national format with 2 decimals`
setlocale(LC_MONETARY, 'it_IT');
echo money_format('%.2n', $number) . "\n";
// Eu 1.234,56

// Using a negative number
$number = -1234.5672;

// US national format, using () for negative numbers
// and 10 digits for left precision
setlocale(LC_MONETARY, 'en_US');
echo money_format('%(#10n', $number) . "\n";
// ($        1,234.57)

// Similar format as above, adding the use of 2 digits of right
// precision and '*' as a fill character
echo money_format('%=*(#10.2n', $number) . "\n";
// ($********1,234.57)

// Let's justify to the left, with 14 positions of width, 8 digits of
// left precision, 2 of right precision, without the grouping character
// and using the international format for the de_DE locale.
setlocale(LC_MONETARY, 'de_DE');
echo money_format('%=*^-14#8.2i', 1234.56) . "\n";
// Eu 1234,56****

// Let's add some blurb before and after the conversion specification
setlocale(LC_MONETARY, 'en_GB');
$fmt = 'The final value is %i (after a 10%% discount)';
echo money_format($fmt, 1234.56) . "\n";
// The final value is  GBP 1,234.56 (after a 10% discount)

?>
```

### See Also

-   <span class="function">setlocale</span>
-   <span class="function">sscanf</span>
-   <span class="function">sprintf</span>
-   <span class="function">printf</span>
-   <span class="function">number\_format</span>

nl\_langinfo
============

Query language and locale information

### Description

<span class="type">string</span> <span
class="methodname">nl\_langinfo</span> ( <span class="methodparam"><span
class="type">int</span> `$item`</span> )

<span class="function">nl\_langinfo</span> is used to access individual
elements of the locale categories. Unlike <span
class="function">localeconv</span>, which returns all of the elements,
<span class="function">nl\_langinfo</span> allows you to select any
specific element.

### Parameters

`item`  
`item` may be an integer value of the element or the constant name of
the element. The following is a list of constant names for `item` that
may be used and their description. Some of these constants may not be
defined or hold no value for certain locales.

**nl\_langinfo Constants**

Constant

### Return Values

Returns the element as a string, or **`FALSE`** if `item` is not valid.

### Notes

> **Note**: <span class="simpara">This function is not implemented on
> Windows platforms.</span>

### See Also

-   <span class="function">setlocale</span>
-   <span class="function">localeconv</span>

nl2br
=====

Inserts HTML line breaks before all newlines in a string

### Description

<span class="type">string</span> <span class="methodname">nl2br</span> (
<span class="methodparam"><span class="type">string</span>
`$string`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$is_xhtml`<span class="initializer"> =
**`TRUE`**</span></span> \] )

Returns `string` with `<br />` or `<br>` inserted before all newlines
(*\\r\\n*, *\\n\\r*, *\\n* and *\\r*).

### Parameters

`string`  
The input string.

`is_xhtml`  
Whether to use XHTML compatible line breaks or not.

### Return Values

Returns the altered string.

### Examples

**Example \#1 Using <span class="function">nl2br</span>**

``` php
<?php
echo nl2br("foo isn't\n bar");
?>
```

The above example will output:

    foo isn't<br />
     bar

**Example \#2 Generating valid HTML markup using the `is_xhtml`
parameter**

``` php
<?php
echo nl2br("Welcome\r\nThis is my HTML document", false);
?>
```

The above example will output:

    Welcome<br>
    This is my HTML document

**Example \#3 Various newline separators**

``` php
<?php
$string = "This\r\nis\n\ra\nstring\r";
echo nl2br($string);
?>
```

The above example will output:

    This<br />
    is<br />
    a<br />
    string<br />

### See Also

-   <span class="function">htmlspecialchars</span>
-   <span class="function">htmlentities</span>
-   <span class="function">wordwrap</span>
-   <span class="function">str\_replace</span>

number\_format
==============

Format a number with grouped thousands

### Description

<span class="type">string</span> <span
class="methodname">number\_format</span> ( <span
class="methodparam"><span class="type">float</span> `$number`</span> \[,
<span class="methodparam"><span class="type">int</span> `$decimals`<span
class="initializer"> = 0</span></span> \] )

<span class="type">string</span> <span
class="methodname">number\_format</span> ( <span
class="methodparam"><span class="type">float</span> `$number`</span> ,
<span class="methodparam"><span class="type">int</span> `$decimals`<span
class="initializer"> = 0</span></span> , <span class="methodparam"><span
class="type">string</span> `$dec_point`<span class="initializer"> =
"."</span></span> , <span class="methodparam"><span
class="type">string</span> `$thousands_sep`<span class="initializer"> =
","</span></span> )

This function accepts either one, two, or four parameters (not three):

If only one parameter is given, `number` will be formatted without
decimals, but with a comma (",") between every group of thousands.

If two parameters are given, `number` will be formatted with `decimals`
decimals with a dot (".") in front, and a comma (",") between every
group of thousands.

If all four parameters are given, `number` will be formatted with
`decimals` decimals, `dec_point` instead of a dot (".") before the
decimals and `thousands_sep` instead of a comma (",") between every
group of thousands.

### Parameters

`number`  
The number being formatted.

`decimals`  
Sets the number of decimal points.

`dec_point`  
Sets the separator for the decimal point.

`thousands_sep`  
Sets the thousands separator.

### Return Values

A formatted version of `number`.

### Changelog

| Version | Description                                                                                                                                                                  |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="function">number\_format</span> was changed to not being able to return *-0*, previously *-0* could be returned for cases like where `number` would be *-0.01*. |

### Examples

**Example \#1 <span class="function">number\_format</span> Example**

For instance, French notation usually use two decimals, comma (',') as
decimal separator, and space (' ') as thousand separator. The following
example demonstrates various ways to format a number:

``` php
<?php

$number = 1234.56;

// english notation (default)
$english_format_number = number_format($number);
// 1,235

// French notation
$nombre_format_francais = number_format($number, 2, ',', ' ');
// 1 234,56

$number = 1234.5678;

// english notation without thousands separator
$english_format_number = number_format($number, 2, '.', '');
// 1234.57

?>
```

### See Also

-   <span class="function">money\_format</span>
-   <span class="function">sprintf</span>
-   <span class="function">printf</span>
-   <span class="function">sscanf</span>

ord
===

Convert the first byte of a string to a value between 0 and 255

### Description

<span class="type">int</span> <span class="methodname">ord</span> (
<span class="methodparam"><span class="type">string</span>
`$string`</span> )

Interprets the binary value of the first byte of `string` as an unsigned
integer between 0 and 255.

If the string is in a single-byte encoding, such as ASCII, ISO-8859, or
Windows 1252, this is equivalent to returning the position of a
character in the character set's mapping table. However, note that this
function is not aware of any string encoding, and in particular will
never identify a Unicode code point in a multi-byte encoding such as
UTF-8 or UTF-16.

This function complements <span class="function">chr</span>.

### Parameters

`string`  
A character.

### Return Values

An integer between 0 and 255.

### Examples

**Example \#1 <span class="function">ord</span> example**

``` php
<?php
$str = "\n";
if (ord($str) == 10) {
    echo "The first character of \$str is a line feed.\n";
}
?>
```

**Example \#2 Examining the individual bytes of a UTF-8 string**

``` php
<?php
declare(encoding='UTF-8');
$str = "🐘";
for ( $pos=0; $pos < strlen($str); $pos ++ ) {
 $byte = substr($str, $pos);
 echo 'Byte ' . $pos . ' of $str has value ' . ord($byte) . PHP_EOL;
}
?>
```

The above example will output:

  
Byte 0 of $str has value 240  
Byte 1 of $str has value 159  
Byte 2 of $str has value 144  
Byte 3 of $str has value 152  

### See Also

-   <span class="function">chr</span>
-   An
    <a href="http://www.asciitable.com" class="link external">» ASCII-table</a>
-   <span class="function">mb\_ord</span>

parse\_str
==========

Parses the string into variables

### Description

<span class="type">void</span> <span
class="methodname">parse\_str</span> ( <span class="methodparam"><span
class="type">string</span> `$encoded_string`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$result`</span> \]
)

Parses `encoded_string` as if it were the query string passed via a URL
and sets variables in the current scope (or in the array if `result` is
provided).

### Parameters

`encoded_string`  
The input string.

`result`  
If the second parameter `result` is present, variables are stored in
this variable as array elements instead.

**Warning**
Using this function without the `result` parameter is highly
*DISCOURAGED* and *DEPRECATED* as of PHP 7.2.

Dynamically setting variables in function's scope suffers from exactly
same problems as
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>.

Read section on security of
<a href="/security/globals.html" class="link">Using Register Globals</a>
explaining why it is dangerous.

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                                          |
|---------|----------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | Usage of <span class="function">parse\_str</span> without a second parameter now emits an **`E_DEPRECATED`** notice. |

### Examples

**Example \#1 Using <span class="function">parse\_str</span>**

``` php
<?php
$str = "first=value&arr[]=foo+bar&arr[]=baz";

// Recommended
parse_str($str, $output);
echo $output['first'];  // value
echo $output['arr'][0]; // foo bar
echo $output['arr'][1]; // baz

// DISCOURAGED
parse_str($str);
echo $first;  // value
echo $arr[0]; // foo bar
echo $arr[1]; // baz
?>
```

Because variables in PHP can't have dots and spaces in their names,
those are converted to underscores. Same applies to naming of respective
key names in case of using this function with `result` parameter.

**Example \#2 <span class="function">parse\_str</span> name mangling**

``` php
<?php
parse_str("My Value=Something");
echo $My_Value; // Something

parse_str("My Value=Something", $output);
echo $output['My_Value']; // Something
?>
```

### Notes

> **Note**:
>
> All variables created (or values returned into array if second
> parameter is set) are already <span
> class="function">urldecode</span>d.

> **Note**:
>
> To get the current *QUERY\_STRING*, you may use the variable
> `$_SERVER['QUERY_STRING']`. Also, you may want to read the section on
> <a href="/language/variables/external.html" class="link">variables from external sources</a>.

> **Note**:
>
> The <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>
> setting affects the output of this function, as <span
> class="function">parse\_str</span> uses the same mechanism that PHP
> uses to populate the `$_GET`, `$_POST`, etc. variables.

### See Also

-   <span class="function">parse\_url</span>
-   <span class="function">pathinfo</span>
-   <span class="function">http\_build\_query</span>
-   <span class="function">urldecode</span>

print
=====

Output a string

### Description

<span class="type">int</span> <span class="methodname">print</span> (
<span class="methodparam"><span class="type">string</span> `$arg`</span>
)

Outputs `arg`.

*print* is not actually a real function (it is a language construct) so
you are not required to use parentheses with its argument list.

The major differences to *echo* are that *print* only accepts a single
argument and always returns 1.

### Parameters

`arg`  
The input data.

### Return Values

Returns *1*, always.

### Examples

**Example \#1 *print* examples**

``` php
<?php
print("Hello World");

print "print() also works without parentheses.";

print "This spans
multiple lines. The newlines will be
output as well";

print "This spans\nmultiple lines. The newlines will be\noutput as well.";

print "escaping characters is done \"Like this\".";

// You can use variables inside a print statement
$foo = "foobar";
$bar = "barbaz";

print "foo is $foo"; // foo is foobar

// You can also use arrays
$bar = array("value" => "foo");

print "this is {$bar['value']} !"; // this is foo !

// Using single quotes will print the variable name, not the value
print 'foo is $foo'; // foo is $foo

// If you are not using any other characters, you can just print variables
print $foo;          // foobar

print <<<END
This uses the "here document" syntax to output
multiple lines with $variable interpolation. Note
that the here document terminator must appear on a
line with just a semicolon no extra whitespace!
END;
?>
```

### Notes

> **Note**: <span class="simpara">Because this is a language construct
> and not a function, it cannot be called using
> <a href="/functions/variable-functions.html" class="link">variable functions</a>.</span>

### See Also

-   <span class="function">echo</span>
-   <span class="function">printf</span>
-   <span class="function">flush</span>
-   <a href="/language/types/string.html#language.types.string.syntax.heredoc" class="link">Heredoc syntax</a>

printf
======

Output a formatted string

### Description

<span class="type">int</span> <span class="methodname">printf</span> (
<span class="methodparam"><span class="type">string</span>
`$format`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \] )

Produces output according to `format`.

### Parameters

`format`  
The format string is composed of zero or more directives: ordinary
characters (excluding *%*) that are copied directly to the result and
*conversion specifications*, each of which results in fetching its own
parameter.

A conversion specification follows this prototype:
*%\[argnum$\]\[flags\]\[width\]\[.precision\]specifier*.

##### Argnum

An integer followed by a dollar sign *$*, to specify which number
argument to treat in the conversion.

| Flag      | Description                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------|
| *-*       | Left-justify within the given field width; Right justification is the default                          |
| *+*       | Prefix positive numbers with a plus sign *+*; Default only negative are prefixed with a negative sign. |
|  (space)  | Pads the result with spaces. This is the default.                                                      |
| *0*       | Only left-pads numbers with zeros. With *s* specifiers this can also right-pad with zeros.             |
| *'*(char) | Pads the result with the character (char).                                                             |

##### Width

An integer that says how many characters (minimum) this conversion
should result in.

##### Precision

A period *.* followed by an integer who's meaning depends on the
specifier:

-   <span class="simpara"> For *e*, *E*, *f* and *F* specifiers: this is
    the number of digits to be printed after the decimal point (by
    default, this is 6). </span>
-   <span class="simpara"> For *g* and *G* specifiers: this is the
    maximum number of significant digits to be printed. </span>
-   <span class="simpara"> For *s* specifier: it acts as a cutoff point,
    setting a maximum character limit to the string. </span>

> **Note**: <span class="simpara"> If the period is specified without an
> explicit value for precision, 0 is assumed. </span>

> **Note**: <span class="simpara"> Attempting to use a position
> specifier greater than **`PHP_INT_MAX`** will generate warnings.
> </span>

<table>
<caption><strong>Specifiers</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>%</em></td>
<td>A literal percent character. No argument is required.</td>
</tr>
<tr class="even">
<td><em>b</em></td>
<td>The argument is treated as an integer and presented as a binary number.</td>
</tr>
<tr class="odd">
<td><em>c</em></td>
<td>The argument is treated as an integer and presented as the character with that ASCII.</td>
</tr>
<tr class="even">
<td><em>d</em></td>
<td>The argument is treated as an integer and presented as a (signed) decimal number.</td>
</tr>
<tr class="odd">
<td><em>e</em></td>
<td>The argument is treated as scientific notation (e.g. 1.2e+2). The precision specifier stands for the number of digits after the decimal point since PHP 5.2.1. In earlier versions, it was taken as number of significant digits (one less).</td>
</tr>
<tr class="even">
<td><em>E</em></td>
<td>Like the <em>e</em> specifier but uses uppercase letter (e.g. 1.2E+2).</td>
</tr>
<tr class="odd">
<td><em>f</em></td>
<td>The argument is treated as a float and presented as a floating-point number (locale aware).</td>
</tr>
<tr class="even">
<td><em>F</em></td>
<td>The argument is treated as a float and presented as a floating-point number (non-locale aware). Available as of PHP 5.0.3.</td>
</tr>
<tr class="odd">
<td><em>g</em></td>
<td><p>General format.</p>
<p>Let P equal the precision if nonzero, 6 if the precision is omitted, or 1 if the precision is zero. Then, if a conversion with style E would have an exponent of X:</p>
<p>If P &gt; X ≥ −4, the conversion is with style f and precision P − (X + 1). Otherwise, the conversion is with style e and precision P − 1.</p></td>
</tr>
<tr class="even">
<td><em>G</em></td>
<td>Like the <em>g</em> specifier but uses <em>E</em> and <em>f</em>.</td>
</tr>
<tr class="odd">
<td><em>o</em></td>
<td>The argument is treated as an integer and presented as an octal number.</td>
</tr>
<tr class="even">
<td><em>s</em></td>
<td>The argument is treated and presented as a string.</td>
</tr>
<tr class="odd">
<td><em>u</em></td>
<td>The argument is treated as an integer and presented as an unsigned decimal number.</td>
</tr>
<tr class="even">
<td><em>x</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with lowercase letters).</td>
</tr>
<tr class="odd">
<td><em>X</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with uppercase letters).</td>
</tr>
</tbody>
</table>

**Warning**
The *c* type specifier ignores padding and width

**Warning**
Attempting to use a combination of the string and width specifiers with
character sets that require more than one byte per character may result
in unexpected results

Variables will be co-erced to a suitable type for the specifier:

| Type      | Specifiers                        |
|-----------|-----------------------------------|
| *string*  | *s*                               |
| *integer* | *d*, *u*, *c*, *o*, *x*, *X*, *b* |
| *double*  | *g*, *G*, *e*, *E*, *f*, *F*      |

`...`  

### Return Values

Returns the length of the outputted string.

### Examples

**Example \#1 <span class="function">printf</span>: various examples**

``` php
<?php
$n =  43951789;
$u = -43951789;
$c = 65; // ASCII 65 is 'A'

// notice the double %%, this prints a literal '%' character
printf("%%b = '%b'\n", $n); // binary representation
printf("%%c = '%c'\n", $c); // print the ascii character, same as chr() function
printf("%%d = '%d'\n", $n); // standard integer representation
printf("%%e = '%e'\n", $n); // scientific notation
printf("%%u = '%u'\n", $n); // unsigned integer representation of a positive integer
printf("%%u = '%u'\n", $u); // unsigned integer representation of a negative integer
printf("%%f = '%f'\n", $n); // floating point representation
printf("%%o = '%o'\n", $n); // octal representation
printf("%%s = '%s'\n", $n); // string representation
printf("%%x = '%x'\n", $n); // hexadecimal representation (lower-case)
printf("%%X = '%X'\n", $n); // hexadecimal representation (upper-case)

printf("%%+d = '%+d'\n", $n); // sign specifier on a positive integer
printf("%%+d = '%+d'\n", $u); // sign specifier on a negative integer
?>
```

The above example will output:

    %b = '10100111101010011010101101'
    %c = 'A'
    %d = '43951789'
    %e = '4.39518e+7'
    %u = '43951789'
    %u = '4251015507'
    %f = '43951789.000000'
    %o = '247523255'
    %s = '43951789'
    %x = '29ea6ad'
    %X = '29EA6AD'
    %+d = '+43951789'
    %+d = '-43951789'

**Example \#2 <span class="function">printf</span>: string specifiers**

``` php
<?php
$s = 'monkey';
$t = 'many monkeys';

printf("[%s]\n",      $s); // standard string output
printf("[%10s]\n",    $s); // right-justification with spaces
printf("[%-10s]\n",   $s); // left-justification with spaces
printf("[%010s]\n",   $s); // zero-padding works on strings too
printf("[%'#10s]\n",  $s); // use the custom padding character '#'
printf("[%10.9s]\n", $t); // right-justification but with a cutoff of 8 characters
printf("[%-10.9s]\n", $t); // left-justification but with a cutoff of 8 characters
?>
```

The above example will output:

    [monkey]
    [    monkey]
    [monkey    ]
    [0000monkey]
    [####monkey]
    [ many monk]
    [many monk ]

### See Also

-   <span class="function">print</span>
-   <span class="function">sprintf</span>
-   <span class="function">fprintf</span>
-   <span class="function">vprintf</span>
-   <span class="function">vsprintf</span>
-   <span class="function">vfprintf</span>
-   <span class="function">sscanf</span>
-   <span class="function">fscanf</span>
-   <span class="function">number\_format</span>
-   <span class="function">date</span>
-   <span class="function">flush</span>

quoted\_printable\_decode
=========================

Convert a quoted-printable string to an 8 bit string

### Description

<span class="type">string</span> <span
class="methodname">quoted\_printable\_decode</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> )

This function returns an 8-bit binary string corresponding to the
decoded quoted printable string (according to
<a href="http://www.faqs.org/rfcs/rfc2045" class="link external">» RFC2045</a>,
section 6.7, not
<a href="http://www.faqs.org/rfcs/rfc2821" class="link external">» RFC2821</a>,
section 4.5.2, so additional periods are not stripped from the beginning
of line).

This function is similar to <span class="function">imap\_qprint</span>,
except this one does not require the IMAP module to work.

### Parameters

`str`  
The input string.

### Return Values

Returns the 8-bit binary string.

### See Also

-   <span class="function">quoted\_printable\_encode</span>

quoted\_printable\_encode
=========================

Convert a 8 bit string to a quoted-printable string

### Description

<span class="type">string</span> <span
class="methodname">quoted\_printable\_encode</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> )

Returns a quoted printable string created according to
<a href="http://www.faqs.org/rfcs/rfc2045" class="link external">» RFC2045</a>,
section 6.7.

This function is similar to <span class="function">imap\_8bit</span>,
except this one does not require the IMAP module to work.

### Parameters

`str`  
The input string.

### Return Values

Returns the encoded string.

### See Also

-   <span class="function">quoted\_printable\_decode</span>
-   <span class="function">iconv\_mime\_encode</span>

quotemeta
=========

Quote meta characters

### Description

<span class="type">string</span> <span
class="methodname">quotemeta</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

Returns a version of str with a backslash character (*\\*) before every
character that is among these:

. \\ + \* ? \[ ^ \] ( $ )

### Parameters

`str`  
The input string.

### Return Values

Returns the string with meta characters quoted, or **`FALSE`** if an
empty string is given as `str`.

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">addslashes</span>
-   <span class="function">addcslashes</span>
-   <span class="function">htmlentities</span>
-   <span class="function">htmlspecialchars</span>
-   <span class="function">nl2br</span>
-   <span class="function">stripslashes</span>
-   <span class="function">stripcslashes</span>
-   <span class="function">ereg</span>
-   <span class="function">preg\_quote</span>

rtrim
=====

Strip whitespace (or other characters) from the end of a string

### Description

<span class="type">string</span> <span class="methodname">rtrim</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$character_mask`</span> \] )

This function returns a string with whitespace (or other characters)
stripped from the end of `str`.

Without the second parameter, <span class="function">rtrim</span> will
strip these characters:

-   <span class="simpara"> " " (ASCII *32* (*0x20*)), an ordinary space.
    </span>
-   <span class="simpara"> "\\t" (ASCII *9* (*0x09*)), a tab. </span>
-   <span class="simpara"> "\\n" (ASCII *10* (*0x0A*)), a new line (line
    feed). </span>
-   <span class="simpara"> "\\r" (ASCII *13* (*0x0D*)), a carriage
    return. </span>
-   <span class="simpara"> "\\0" (ASCII *0* (*0x00*)), the *NULL*-byte.
    </span>
-   <span class="simpara"> "\\x0B" (ASCII *11* (*0x0B*)), a vertical
    tab. </span>

### Parameters

`str`  
The input string.

`character_mask`  
You can also specify the characters you want to strip, by means of the
`character_mask` parameter. Simply list all characters that you want to
be stripped. With *..* you can specify a range of characters.

### Return Values

Returns the modified string.

### Examples

**Example \#1 Usage example of <span class="function">rtrim</span>**

``` php
<?php

$text = "\t\tThese are a few words :) ...  ";
$binary = "\x09Example string\x0A";
$hello  = "Hello World";
var_dump($text, $binary, $hello);

print "\n";

$trimmed = rtrim($text);
var_dump($trimmed);

$trimmed = rtrim($text, " \t.");
var_dump($trimmed);

$trimmed = rtrim($hello, "Hdle");
var_dump($trimmed);

// trim the ASCII control characters at the end of $binary
// (from 0 to 31 inclusive)
$clean = rtrim($binary, "\x00..\x1F");
var_dump($clean);

?>
```

The above example will output:

    string(32) "        These are a few words :) ...  "
    string(16) "    Example string
    "
    string(11) "Hello World"

    string(30) "        These are a few words :) ..."
    string(26) "        These are a few words :)"
    string(9) "Hello Wor"
    string(15) "    Example string"

### See Also

-   <span class="function">trim</span>
-   <span class="function">ltrim</span>

setlocale
=========

Set locale information

### Description

<span class="type">string</span> <span
class="methodname">setlocale</span> ( <span class="methodparam"><span
class="type">int</span> `$category`</span> , <span
class="methodparam"><span class="type">string</span> `$locale`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$...`</span> \] )

<span class="type">string</span> <span
class="methodname">setlocale</span> ( <span class="methodparam"><span
class="type">int</span> `$category`</span> , <span
class="methodparam"><span class="type">array</span> `$locale`</span> )

Sets locale information.

**Warning**

The locale information is maintained per process, not per thread. If you
are running PHP on a multithreaded server API , you may experience
sudden changes in locale settings while a script is running, though the
script itself never called <span class="function">setlocale</span>. This
happens due to other scripts running in different threads of the same
process at the same time, changing the process-wide locale using <span
class="function">setlocale</span>. On Windows, locale information is
maintained per thread as of PHP 5.6.20 and PHP 7.0.5, respectively.

### Parameters

`category`  
`category` is a named constant specifying the category of the functions
affected by the locale setting:

-   <span class="simpara"> **`LC_ALL`** for all of the below </span>
-   <span class="simpara"> **`LC_COLLATE`** for string comparison, see
    <span class="function">strcoll</span> </span>
-   <span class="simpara"> **`LC_CTYPE`** for character classification
    and conversion, for example <span class="function">strtoupper</span>
    </span>
-   <span class="simpara"> **`LC_MONETARY`** for <span
    class="function">localeconv</span> </span>
-   <span class="simpara"> **`LC_NUMERIC`** for decimal separator (See
    also <span class="function">localeconv</span>) </span>
-   <span class="simpara"> **`LC_TIME`** for date and time formatting
    with <span class="function">strftime</span> </span>
-   <span class="simpara"> **`LC_MESSAGES`** for system responses
    (available if PHP was compiled with *libintl*) </span>

`locale`  
If `locale` is **`NULL`** or the empty string *""*, the locale names
will be set from the values of environment variables with the same names
as the above categories, or from "LANG".

If `locale` is *"0"*, the locale setting is not affected, only the
current setting is returned.

If `locale` is an array or followed by additional parameters then each
array element or parameter is tried to be set as new locale until
success. This is useful if a locale is known under different names on
different systems or for providing a fallback for a possibly not
available locale.

`...`  
(Optional string or array parameters to try as locale settings until
success.)

> **Note**:
>
> On Windows, setlocale(LC\_ALL, '') sets the locale names from the
> system's regional/language settings (accessible via Control Panel).

### Return Values

Returns the new current locale, or **`FALSE`** if the locale
functionality is not implemented on your platform, the specified locale
does not exist or the category name is invalid.

An invalid category name also causes a warning message. Category/locale
names can be found in
<a href="http://www.faqs.org/rfcs/rfc1766" class="link external">» RFC 1766</a>
and
<a href="http://www.loc.gov/standards/iso639-2/php/code_list.php" class="link external">» ISO 639</a>.
Different systems have different naming schemes for locales.

> **Note**:
>
> The return value of <span class="function">setlocale</span> depends on
> the system that PHP is running. It returns exactly what the system
> *setlocale* function returns.

### Examples

**Example \#1 <span class="function">setlocale</span> Examples**

``` php
<?php
/* Set locale to Dutch */
setlocale(LC_ALL, 'nl_NL');

/* Output: vrijdag 22 december 1978 */
echo strftime("%A %e %B %Y", mktime(0, 0, 0, 12, 22, 1978));

/* try different possible locale names for german */
$loc_de = setlocale(LC_ALL, 'de_DE@euro', 'de_DE', 'de', 'ge');
echo "Preferred locale for german on this system is '$loc_de'";
?>
```

**Example \#2 <span class="function">setlocale</span> Examples for
Windows**

``` php
<?php
/* Set locale to Dutch */
setlocale(LC_ALL, 'nld_nld');

/* Output: vrijdag 22 december 1978 */
echo strftime("%A %d %B %Y", mktime(0, 0, 0, 12, 22, 1978));

/* try different possible locale names for german */
$loc_de = setlocale(LC_ALL, 'de_DE@euro', 'de_DE', 'deu_deu');
echo "Preferred locale for german on this system is '$loc_de'";
?>
```

### Notes

**Tip**

Windows users will find useful information about `locale` strings at
Microsoft's MSDN website. Supported language strings can be found in the
<a href="http://msdn.microsoft.com/en-us/library/39cwe7zf%28v=vs.90%29.aspx" class="link external">» language strings documentation</a>
and supported country/region strings in the
<a href="http://msdn.microsoft.com/en-us/library/cdax410z%28v=vs.90%29.aspx" class="link external">» country/region strings documentation</a>.

sha1\_file
==========

Calculate the sha1 hash of a file

### Description

<span class="type">string</span> <span
class="methodname">sha1\_file</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$raw_output`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Calculates the sha1 hash of the file specified by `filename` using the
<a href="http://www.faqs.org/rfcs/rfc3174" class="link external">» US Secure Hash Algorithm 1</a>,
and returns that hash. The hash is a 40-character hexadecimal number.

### Parameters

`filename`  
The filename of the file to hash.

`raw_output`  
When **`TRUE`**, returns the digest in raw binary format with a length
of 20.

### Return Values

Returns a string on success, **`FALSE`** otherwise.

### Examples

**Example \#1 <span class="function">sha1\_file</span> example**

``` php
<?php
foreach(glob('/home/Kalle/myproject/*.php') as $ent)
{
    if(is_dir($ent))
    {
        continue;
    }

    echo $ent . ' (SHA1: ' . sha1_file($ent) . ')', PHP_EOL;
}
?>
```

### See Also

-   <span class="function">sha1</span>
-   <span class="function">md5\_file</span>
-   <span class="function">crc32</span>

sha1
====

Calculate the sha1 hash of a string

**Warning**

It is not recommended to use this function to secure passwords, due to
the fast nature of this hashing algorithm. See the
<a href="/faq/passwords.html#faq.passwords.fasthash" class="link">Password Hashing FAQ</a>
for details and best practices.

### Description

<span class="type">string</span> <span class="methodname">sha1</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$raw_output`<span class="initializer"> = **`FALSE`**</span></span> \] )

Calculates the sha1 hash of `str` using the
<a href="http://www.faqs.org/rfcs/rfc3174" class="link external">» US Secure Hash Algorithm 1</a>.

### Parameters

`str`  
The input string.

`raw_output`  
If the optional `raw_output` is set to **`TRUE`**, then the sha1 digest
is instead returned in raw binary format with a length of 20, otherwise
the returned value is a 40-character hexadecimal number.

### Return Values

Returns the sha1 hash as a string.

### Examples

**Example \#1 A <span class="function">sha1</span> example**

``` php
<?php
$str = 'apple';

if (sha1($str) === 'd0be2dc421be4fcd0172e5afceea3970e2f3d940') {
    echo "Would you like a green or red apple?";
}
?>
```

### See Also

-   <span class="function">sha1\_file</span>
-   <span class="function">crc32</span>
-   <span class="function">md5</span>
-   <span class="function">hash</span>
-   <span class="function">crypt</span>
-   <span class="function">password\_hash</span>

similar\_text
=============

Calculate the similarity between two strings

### Description

<span class="type">int</span> <span
class="methodname">similar\_text</span> ( <span
class="methodparam"><span class="type">string</span> `$first`</span> ,
<span class="methodparam"><span class="type">string</span>
`$second`</span> \[, <span class="methodparam"><span
class="type">float</span> `&$percent`</span> \] )

This calculates the similarity between two strings as described in
Programming Classics: Implementing the World's Best Algorithms by Oliver
(ISBN 0-131-00413-1). Note that this implementation does not use a stack
as in Oliver's pseudo code, but recursive calls which may or may not
speed up the whole process. Note also that the complexity of this
algorithm is O(N\*\*3) where N is the length of the longest string.

### Parameters

`first`  
The first string.

`second`  
The second string.

> **Note**:
>
> Swapping the `first` and `second` may yield a different result; see
> the example below.

`percent`  
By passing a reference as third argument, <span
class="function">similar\_text</span> will calculate the similarity in
percent, by dividing the result of <span
class="function">similar\_text</span> by the average of the lengths of
the given strings times *100*.

### Return Values

Returns the number of matching chars in both strings.

The number of matching characters is calculated by finding the longest
first common substring, and then doing this for the prefixes and the
suffixes, recursively. The lengths of all found common substrings are
added.

### Examples

**Example \#1 <span class="function">similar\_text</span> argument
swapping example**

This example shows that swapping the `first` and `second` argument may
yield different results.

``` php
<?php
$sim = similar_text('bafoobar', 'barfoo', $perc);
echo "similarity: $sim ($perc %)\n";
$sim = similar_text('barfoo', 'bafoobar', $perc);
echo "similarity: $sim ($perc %)\n";
```

The above example will output something similar to:

    similarity: 5 (71.428571428571 %)
    similarity: 3 (42.857142857143 %)

### See Also

-   <span class="function">levenshtein</span>
-   <span class="function">soundex</span>

soundex
=======

Calculate the soundex key of a string

### Description

<span class="type">string</span> <span class="methodname">soundex</span>
( <span class="methodparam"><span class="type">string</span>
`$str`</span> )

Calculates the soundex key of `str`.

Soundex keys have the property that words pronounced similarly produce
the same soundex key, and can thus be used to simplify searches in
databases where you know the pronunciation but not the spelling. This
soundex function returns a string 4 characters long, starting with a
letter.

This particular soundex function is one described by Donald Knuth in
"The Art Of Computer Programming, vol. 3: Sorting And Searching",
Addison-Wesley (1973), pp. 391-392.

### Parameters

`str`  
The input string.

### Return Values

Returns the soundex key as a <span class="type">string</span>, or
**`FALSE`** on failure.

### Examples

**Example \#1 Soundex Examples**

``` php
<?php
soundex("Euler")       == soundex("Ellery");    // E460
soundex("Gauss")       == soundex("Ghosh");     // G200
soundex("Hilbert")     == soundex("Heilbronn"); // H416
soundex("Knuth")       == soundex("Kant");      // K530
soundex("Lloyd")       == soundex("Ladd");      // L300
soundex("Lukasiewicz") == soundex("Lissajous"); // L222
?>
```

### See Also

-   <span class="function">levenshtein</span>
-   <span class="function">metaphone</span>
-   <span class="function">similar\_text</span>

sprintf
=======

Return a formatted string

### Description

<span class="type">string</span> <span class="methodname">sprintf</span>
( <span class="methodparam"><span class="type">string</span>
`$format`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \] )

Returns a string produced according to the formatting string `format`.

### Parameters

`format`  
The format string is composed of zero or more directives: ordinary
characters (excluding *%*) that are copied directly to the result and
*conversion specifications*, each of which results in fetching its own
parameter.

A conversion specification follows this prototype:
*%\[argnum$\]\[flags\]\[width\]\[.precision\]specifier*.

##### Argnum

An integer followed by a dollar sign *$*, to specify which number
argument to treat in the conversion.

| Flag      | Description                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------|
| *-*       | Left-justify within the given field width; Right justification is the default                          |
| *+*       | Prefix positive numbers with a plus sign *+*; Default only negative are prefixed with a negative sign. |
|  (space)  | Pads the result with spaces. This is the default.                                                      |
| *0*       | Only left-pads numbers with zeros. With *s* specifiers this can also right-pad with zeros.             |
| *'*(char) | Pads the result with the character (char).                                                             |

##### Width

An integer that says how many characters (minimum) this conversion
should result in.

##### Precision

A period *.* followed by an integer who's meaning depends on the
specifier:

-   <span class="simpara"> For *e*, *E*, *f* and *F* specifiers: this is
    the number of digits to be printed after the decimal point (by
    default, this is 6). </span>
-   <span class="simpara"> For *g* and *G* specifiers: this is the
    maximum number of significant digits to be printed. </span>
-   <span class="simpara"> For *s* specifier: it acts as a cutoff point,
    setting a maximum character limit to the string. </span>

> **Note**: <span class="simpara"> If the period is specified without an
> explicit value for precision, 0 is assumed. </span>

> **Note**: <span class="simpara"> Attempting to use a position
> specifier greater than **`PHP_INT_MAX`** will generate warnings.
> </span>

<table>
<caption><strong>Specifiers</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>%</em></td>
<td>A literal percent character. No argument is required.</td>
</tr>
<tr class="even">
<td><em>b</em></td>
<td>The argument is treated as an integer and presented as a binary number.</td>
</tr>
<tr class="odd">
<td><em>c</em></td>
<td>The argument is treated as an integer and presented as the character with that ASCII.</td>
</tr>
<tr class="even">
<td><em>d</em></td>
<td>The argument is treated as an integer and presented as a (signed) decimal number.</td>
</tr>
<tr class="odd">
<td><em>e</em></td>
<td>The argument is treated as scientific notation (e.g. 1.2e+2). The precision specifier stands for the number of digits after the decimal point since PHP 5.2.1. In earlier versions, it was taken as number of significant digits (one less).</td>
</tr>
<tr class="even">
<td><em>E</em></td>
<td>Like the <em>e</em> specifier but uses uppercase letter (e.g. 1.2E+2).</td>
</tr>
<tr class="odd">
<td><em>f</em></td>
<td>The argument is treated as a float and presented as a floating-point number (locale aware).</td>
</tr>
<tr class="even">
<td><em>F</em></td>
<td>The argument is treated as a float and presented as a floating-point number (non-locale aware). Available as of PHP 5.0.3.</td>
</tr>
<tr class="odd">
<td><em>g</em></td>
<td><p>General format.</p>
<p>Let P equal the precision if nonzero, 6 if the precision is omitted, or 1 if the precision is zero. Then, if a conversion with style E would have an exponent of X:</p>
<p>If P &gt; X ≥ −4, the conversion is with style f and precision P − (X + 1). Otherwise, the conversion is with style e and precision P − 1.</p></td>
</tr>
<tr class="even">
<td><em>G</em></td>
<td>Like the <em>g</em> specifier but uses <em>E</em> and <em>f</em>.</td>
</tr>
<tr class="odd">
<td><em>o</em></td>
<td>The argument is treated as an integer and presented as an octal number.</td>
</tr>
<tr class="even">
<td><em>s</em></td>
<td>The argument is treated and presented as a string.</td>
</tr>
<tr class="odd">
<td><em>u</em></td>
<td>The argument is treated as an integer and presented as an unsigned decimal number.</td>
</tr>
<tr class="even">
<td><em>x</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with lowercase letters).</td>
</tr>
<tr class="odd">
<td><em>X</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with uppercase letters).</td>
</tr>
</tbody>
</table>

**Warning**
The *c* type specifier ignores padding and width

**Warning**
Attempting to use a combination of the string and width specifiers with
character sets that require more than one byte per character may result
in unexpected results

Variables will be co-erced to a suitable type for the specifier:

| Type      | Specifiers                        |
|-----------|-----------------------------------|
| *string*  | *s*                               |
| *integer* | *d*, *u*, *c*, *o*, *x*, *X*, *b* |
| *double*  | *g*, *G*, *e*, *E*, *f*, *F*      |

`...`  

### Return Values

Returns a string produced according to the formatting string `format`,
or **`FALSE`** on failure.

### Examples

**Example \#1 Argument swapping**

The format string supports argument numbering/swapping.

``` php
<?php
$num = 5;
$location = 'tree';

$format = 'There are %d monkeys in the %s';
echo sprintf($format, $num, $location);
?>
```

The above example will output:

    There are 5 monkeys in the tree

However imagine we are creating a format string in a separate file,
commonly because we would like to internationalize it and we rewrite it
as:

``` php
<?php
$format = 'The %s contains %d monkeys';
echo sprintf($format, $num, $location);
?>
```

We now have a problem. The order of the placeholders in the format
string does not match the order of the arguments in the code. We would
like to leave the code as is and simply indicate in the format string
which arguments the placeholders refer to. We would write the format
string like this instead:

``` php
<?php
$format = 'The %2$s contains %1$d monkeys';
echo sprintf($format, $num, $location);
?>
```

An added benefit is that placeholders can be repeated without adding
more arguments in the code.

``` php
<?php
$format = 'The %2$s contains %1$d monkeys.
           That\'s a nice %2$s full of %1$d monkeys.';
echo sprintf($format, $num, $location);
?>
```

When using argument swapping, the *n$* *position specifier* must come
immediately after the percent sign (*%*), before any other specifiers,
as shown below.

**Example \#2 Specifying padding character**

``` php
<?php
echo sprintf("%'.9d\n", 123);
echo sprintf("%'.09d\n", 123);
?>
```

The above example will output:

    ......123
    000000123

**Example \#3 Position specifier with other specifiers**

``` php
<?php
$format = 'The %2$s contains %1$04d monkeys';
echo sprintf($format, $num, $location);
?>
```

The above example will output:

    The tree contains 0005 monkeys

**Example \#4 <span class="function">sprintf</span>: zero-padded
integers**

``` php
<?php
$isodate = sprintf("%04d-%02d-%02d", $year, $month, $day);
?>
```

**Example \#5 <span class="function">sprintf</span>: formatting
currency**

``` php
<?php
$money1 = 68.75;
$money2 = 54.35;
$money = $money1 + $money2;
echo $money;
echo "\n";
$formatted = sprintf("%01.2f", $money);
echo $formatted;
?>
```

The above example will output:

    123.1
    123.10

**Example \#6 <span class="function">sprintf</span>: scientific
notation**

``` php
<?php
$number = 362525200;

echo sprintf("%.3e", $number);
?>
```

The above example will output:

    3.625e+8

### See Also

-   <span class="function">printf</span>
-   <span class="function">fprintf</span>
-   <span class="function">vprintf</span>
-   <span class="function">vsprintf</span>
-   <span class="function">vfprintf</span>
-   <span class="function">sscanf</span>
-   <span class="function">fscanf</span>
-   <span class="function">number\_format</span>
-   <span class="function">date</span>

sscanf
======

Parses input from a string according to a format

### Description

<span class="type">mixed</span> <span class="methodname">sscanf</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
, <span class="methodparam"><span class="type">string</span>
`$format`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `&$...`</span> \] )

The function <span class="function">sscanf</span> is the input analog of
<span class="function">printf</span>. <span
class="function">sscanf</span> reads from the string `str` and
interprets it according to the specified `format`, which is described in
the documentation for <span class="function">sprintf</span>.

Any whitespace in the format string matches any whitespace in the input
string. This means that even a tab \\t in the format string can match a
single space character in the input string.

### Parameters

`str`  
The input <span class="type">string</span> being parsed.

`format`  
The interpreted format for `str`, which is described in the
documentation for <span class="function">sprintf</span> with following
differences:

-   Function is not locale-aware.
-   *F*, *g*, *G* and *b* are not supported.
-   *D* stands for decimal number.
-   *i* stands for integer with base detection.
-   *n* stands for number of characters processed so far.
-   *s* stops reading at any whitespace character.

`...`  
Optionally pass in variables by reference that will contain the parsed
values.

### Return Values

If only two parameters were passed to this function, the values parsed
will be returned as an array. Otherwise, if optional parameters are
passed, the function will return the number of assigned values. The
optional parameters must be passed by reference.

If there are more substrings expected in the `format` than there are
available within `str`, *-1* will be returned.

### Examples

**Example \#1 <span class="function">sscanf</span> Example**

``` php
<?php
// getting the serial number
list($serial) = sscanf("SN/2350001", "SN/%d");
// and the date of manufacturing
$mandate = "January 01 2000";
list($month, $day, $year) = sscanf($mandate, "%s %d %d");
echo "Item $serial was manufactured on: $year-" . substr($month, 0, 3) . "-$day\n";
?>
```

If optional parameters are passed, the function will return the number
of assigned values.

**Example \#2 <span class="function">sscanf</span> - using optional
parameters**

``` php
<?php
// get author info and generate DocBook entry
$auth = "24\tLewis Carroll";
$n = sscanf($auth, "%d\t%s %s", $id, $first, $last);
echo "<author id='$id'>
    <firstname>$first</firstname>
    <surname>$last</surname>
</author>\n";
?>
```

### See Also

-   <span class="function">printf</span>
-   <span class="function">sprintf</span>
-   <span class="function">fprintf</span>
-   <span class="function">vprintf</span>
-   <span class="function">vsprintf</span>
-   <span class="function">vfprintf</span>
-   <span class="function">fscanf</span>
-   <span class="function">number\_format</span>
-   <span class="function">date</span>

str\_getcsv
===========

Parse a CSV string into an array

### Description

<span class="type">array</span> <span
class="methodname">str\_getcsv</span> ( <span class="methodparam"><span
class="type">string</span> `$input`</span> \[, <span
class="methodparam"><span class="type">string</span> `$delimiter`<span
class="initializer"> = ","</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$enclosure`<span
class="initializer"> = '"'</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$escape`<span
class="initializer"> = "\\\\"</span></span> \]\]\] )

Parses a string input for fields in CSV format and returns an array
containing the fields read.

> **Note**:
>
> The locale settings are taken into account by this function. If
> *LC\_CTYPE* is e.g. *en\_US.UTF-8*, strings in one-byte encodings may
> be read wrongly by this function.

### Parameters

`input`  
The string to parse.

`delimiter`  
Set the field delimiter (one character only).

`enclosure`  
Set the field enclosure character (one character only).

`escape`  
Set the escape character (at most one character). Defaults as a
backslash (*\\*) An empty string (*""*) disables the proprietary escape
mechanism.

> **Note**: <span class="simpara"> Usually an `enclosure` character is
> escaped inside a field by doubling it; however, the `escape` character
> can be used as an alternative. So for the default parameter values
> *""* and *\\"* have the same meaning. Other than allowing to escape
> the `enclosure` character the `escape` character has no special
> meaning; it isn't even meant to escape itself. </span>

### Return Values

Returns an indexed array containing the fields read.

### Changelog

| Version | Description                                                                                                                                                                          |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | The `escape` parameter now interprets an empty string as signal to disable the proprietary escape mechanism. Formerly, an empty string was treated like the default parameter value. |

### See Also

-   <span class="function">fgetcsv</span>

str\_ireplace
=============

Case-insensitive version of <span class="function">str\_replace</span>

### Description

<span class="type">mixed</span> <span
class="methodname">str\_ireplace</span> ( <span
class="methodparam"><span class="type">mixed</span> `$search`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$replace`</span> , <span class="methodparam"><span
class="type">mixed</span> `$subject`</span> \[, <span
class="methodparam"><span class="type">int</span> `&$count`</span> \] )

This function returns a string or an array with all occurrences of
`search` in `subject` (ignoring case) replaced with the given `replace`
value. If you don't need fancy replacing rules, you should generally use
this function instead of <span class="function">preg\_replace</span>
with the *i* modifier.

### Parameters

If `search` and `replace` are arrays, then <span
class="function">str\_ireplace</span> takes a value from each array and
uses them to search and replace on `subject`. If `replace` has fewer
values than `search`, then an empty string is used for the rest of
replacement values. If `search` is an array and `replace` is a string,
then this replacement string is used for every value of `search`. The
converse would not make sense, though.

If `search` or `replace` are arrays, their elements are processed first
to last.

`search`  
The value being searched for, otherwise known as the *needle*. An array
may be used to designate multiple needles.

`replace`  
The replacement value that replaces found `search` values. An array may
be used to designate multiple replacements.

`subject`  
The string or array being searched and replaced on, otherwise known as
the *haystack*.

If `subject` is an array, then the search and replace is performed with
every entry of `subject`, and the return value is an array as well.

`count`  
If passed, this will be set to the number of replacements performed.

### Return Values

Returns a string or an array of replacements.

### Examples

**Example \#1 <span class="function">str\_ireplace</span> example**

``` php
<?php
$bodytag = str_ireplace("%body%", "black", "<body text=%BODY%>");
echo $bodytag; // <body text=black>
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

**Caution**

Because <span class="function">str\_ireplace</span> replaces left to
right, it might replace a previously inserted value when doing multiple
replacements. Example \#2 in the <span
class="function">str\_replace</span> documentation demonstrates how this
may affect you in practice.

### See Also

-   <span class="function">str\_replace</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">strtr</span>

str\_pad
========

Pad a string to a certain length with another string

### Description

<span class="type">string</span> <span
class="methodname">str\_pad</span> ( <span class="methodparam"><span
class="type">string</span> `$input`</span> , <span
class="methodparam"><span class="type">int</span> `$pad_length`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$pad_string`<span class="initializer"> = " "</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$pad_type`<span
class="initializer"> = STR\_PAD\_RIGHT</span></span> \]\] )

This function returns the `input` string padded on the left, the right,
or both sides to the specified padding length. If the optional argument
`pad_string` is not supplied, the `input` is padded with spaces,
otherwise it is padded with characters from `pad_string` up to the
limit.

### Parameters

`input`  
The input string.

`pad_length`  
If the value of `pad_length` is negative, less than, or equal to the
length of the input string, no padding takes place, and `input` will be
returned.

`pad_string`  
> **Note**:
>
> The `pad_string` may be truncated if the required number of padding
> characters can't be evenly divided by the `pad_string`'s length.

`pad_type`  
Optional argument `pad_type` can be **`STR_PAD_RIGHT`**,
**`STR_PAD_LEFT`**, or **`STR_PAD_BOTH`**. If `pad_type` is not
specified it is assumed to be **`STR_PAD_RIGHT`**.

### Return Values

Returns the padded string.

### Examples

**Example \#1 <span class="function">str\_pad</span> example**

``` php
<?php
$input = "Alien";
echo str_pad($input, 10);                      // produces "Alien     "
echo str_pad($input, 10, "-=", STR_PAD_LEFT);  // produces "-=-=-Alien"
echo str_pad($input, 10, "_", STR_PAD_BOTH);   // produces "__Alien___"
echo str_pad($input,  6, "___");               // produces "Alien_"
echo str_pad($input,  3, "*");                 // produces "Alien"
?>
```

str\_repeat
===========

Repeat a string

### Description

<span class="type">string</span> <span
class="methodname">str\_repeat</span> ( <span class="methodparam"><span
class="type">string</span> `$input`</span> , <span
class="methodparam"><span class="type">int</span> `$multiplier`</span> )

Returns `input` repeated `multiplier` times.

### Parameters

`input`  
The string to be repeated.

`multiplier`  
Number of time the `input` string should be repeated.

`multiplier` has to be greater than or equal to 0. If the `multiplier`
is set to 0, the function will return an empty string.

### Return Values

Returns the repeated string.

### Examples

**Example \#1 <span class="function">str\_repeat</span> example**

``` php
<?php
echo str_repeat("-=", 10);
?>
```

The above example will output:

    -=-=-=-=-=-=-=-=-=-=

### See Also

-   <a href="/control-structures/for.html" class="link">for</a>
-   <span class="function">str\_pad</span>
-   <span class="function">substr\_count</span>

str\_replace
============

Replace all occurrences of the search string with the replacement string

### Description

<span class="type">mixed</span> <span
class="methodname">str\_replace</span> ( <span class="methodparam"><span
class="type">mixed</span> `$search`</span> , <span
class="methodparam"><span class="type">mixed</span> `$replace`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$subject`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$count`</span> \] )

This function returns a string or an array with all occurrences of
`search` in `subject` replaced with the given `replace` value.

If you don't need fancy replacing rules (like regular expressions), you
should use this function instead of <span
class="function">preg\_replace</span>.

### Parameters

If `search` and `replace` are arrays, then <span
class="function">str\_replace</span> takes a value from each array and
uses them to search and replace on `subject`. If `replace` has fewer
values than `search`, then an empty string is used for the rest of
replacement values. If `search` is an array and `replace` is a string,
then this replacement string is used for every value of `search`. The
converse would not make sense, though.

If `search` or `replace` are arrays, their elements are processed first
to last.

`search`  
The value being searched for, otherwise known as the *needle*. An array
may be used to designate multiple needles.

`replace`  
The replacement value that replaces found `search` values. An array may
be used to designate multiple replacements.

`subject`  
The string or array being searched and replaced on, otherwise known as
the *haystack*.

If `subject` is an array, then the search and replace is performed with
every entry of `subject`, and the return value is an array as well.

`count`  
If passed, this will be set to the number of replacements performed.

### Return Values

This function returns a string or an array with the replaced values.

### Examples

**Example \#1 Basic <span class="function">str\_replace</span>
examples**

``` php
<?php
// Provides: <body text='black'>
$bodytag = str_replace("%body%", "black", "<body text='%body%'>");

// Provides: Hll Wrld f PHP
$vowels = array("a", "e", "i", "o", "u", "A", "E", "I", "O", "U");
$onlyconsonants = str_replace($vowels, "", "Hello World of PHP");

// Provides: You should eat pizza, beer, and ice cream every day
$phrase  = "You should eat fruits, vegetables, and fiber every day.";
$healthy = array("fruits", "vegetables", "fiber");
$yummy   = array("pizza", "beer", "ice cream");

$newphrase = str_replace($healthy, $yummy, $phrase);

// Provides: 2
$str = str_replace("ll", "", "good golly miss molly!", $count);
echo $count;
?>
```

**Example \#2 Examples of potential <span
class="function">str\_replace</span> gotchas**

``` php
<?php
// Order of replacement
$str     = "Line 1\nLine 2\rLine 3\r\nLine 4\n";
$order   = array("\r\n", "\n", "\r");
$replace = '<br />';

// Processes \r\n's first so they aren't converted twice.
$newstr = str_replace($order, $replace, $str);

// Outputs F because A is replaced with B, then B is replaced with C, and so on...
// Finally E is replaced with F, because of left to right replacements.
$search  = array('A', 'B', 'C', 'D', 'E');
$replace = array('B', 'C', 'D', 'E', 'F');
$subject = 'A';
echo str_replace($search, $replace, $subject);

// Outputs: apearpearle pear
// For the same reason mentioned above
$letters = array('a', 'p');
$fruit   = array('apple', 'pear');
$text    = 'a p';
$output  = str_replace($letters, $fruit, $text);
echo $output;
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

**Caution**

Because <span class="function">str\_replace</span> replaces left to
right, it might replace a previously inserted value when doing multiple
replacements. See also the examples in this document.

> **Note**:
>
> This function is case-sensitive. Use <span
> class="function">str\_ireplace</span> for case-insensitive replace.

### See Also

-   <span class="function">str\_ireplace</span>
-   <span class="function">substr\_replace</span>
-   <span class="function">preg\_replace</span>
-   <span class="function">strtr</span>

str\_rot13
==========

Perform the rot13 transform on a string

### Description

<span class="type">string</span> <span
class="methodname">str\_rot13</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

Performs the ROT13 encoding on the `str` argument and returns the
resulting string.

The ROT13 encoding simply shifts every letter by 13 places in the
alphabet while leaving non-alpha characters untouched. Encoding and
decoding are done by the same function, passing an encoded string as
argument will return the original version.

### Parameters

`str`  
The input string.

### Return Values

Returns the ROT13 version of the given string.

### Examples

**Example \#1 <span class="function">str\_rot13</span> example**

``` php
<?php

echo str_rot13('PHP 4.3.0'); // CUC 4.3.0

?>
```

str\_shuffle
============

Randomly shuffles a string

### Description

<span class="type">string</span> <span
class="methodname">str\_shuffle</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

<span class="function">str\_shuffle</span> shuffles a string. One
permutation of all possible is created.

**Caution**

This function does not generate cryptographically secure values, and
should not be used for cryptographic purposes. If you need a
cryptographically secure value, consider using <span
class="function">random\_int</span>, <span
class="function">random\_bytes</span>, or <span
class="function">openssl\_random\_pseudo\_bytes</span> instead.

### Parameters

`str`  
The input string.

### Return Values

Returns the shuffled string.

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                       |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | The internal randomization algorithm <a href="/migration71/incompatible.html#migration71.incompatible.rand-srand-aliases" class="link">has been changed</a> to use the <a href="http://www.math.sci.hiroshima-u.ac.jp/~m-mat/MT/emt.html" class="link external">» Mersenne Twister</a> Random Number Generator instead of the libc rand function. |

### Examples

**Example \#1 <span class="function">str\_shuffle</span> example**

``` php
<?php
$str = 'abcdef';
$shuffled = str_shuffle($str);

// This will echo something like: bfdaec
echo $shuffled;
?>
```

### See Also

-   <span class="function">shuffle</span>
-   <span class="function">rand</span>

str\_split
==========

Convert a string to an array

### Description

<span class="type">array</span> <span
class="methodname">str\_split</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type">int</span> `$split_length`<span
class="initializer"> = 1</span></span> \] )

Converts a string to an array.

### Parameters

`string`  
The input string.

`split_length`  
Maximum length of the chunk.

### Return Values

If the optional `split_length` parameter is specified, the returned
array will be broken down into chunks with each being `split_length` in
length, otherwise each chunk will be one character in length.

**`FALSE`** is returned if `split_length` is less than 1. If the
`split_length` length exceeds the length of `string`, the entire string
is returned as the first (and only) array element.

### Examples

**Example \#1 Example uses of <span class="function">str\_split</span>**

``` php
<?php

$str = "Hello Friend";

$arr1 = str_split($str);
$arr2 = str_split($str, 3);

print_r($arr1);
print_r($arr2);

?>
```

The above example will output:

    Array
    (
        [0] => H
        [1] => e
        [2] => l
        [3] => l
        [4] => o
        [5] =>
        [6] => F
        [7] => r
        [8] => i
        [9] => e
        [10] => n
        [11] => d
    )

    Array
    (
        [0] => Hel
        [1] => lo
        [2] => Fri
        [3] => end
    )

### Notes

> **Note**:
>
> <span class="function">str\_split</span> will split into bytes, rather
> than characters when dealing with a multi-byte encoded string.

### See Also

-   <span class="function">chunk\_split</span>
-   <span class="function">preg\_split</span>
-   <span class="function">explode</span>
-   <span class="function">count\_chars</span>
-   <span class="function">str\_word\_count</span>
-   <a href="/control-structures/for.html" class="link">for</a>

str\_word\_count
================

Return information about words used in a string

### Description

<span class="type">mixed</span> <span
class="methodname">str\_word\_count</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$format`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$charlist`</span>
\]\] )

Counts the number of words inside `string`. If the optional `format` is
not specified, then the return value will be an integer representing the
number of words found. In the event the `format` is specified, the
return value will be an array, content of which is dependent on the
`format`. The possible value for the `format` and the resultant outputs
are listed below.

For the purpose of this function, 'word' is defined as a locale
dependent string containing alphabetic characters, which also may
contain, but not start with "'" and "-" characters.

### Parameters

`string`  
The string

`format`  
Specify the return value of this function. The current supported values
are:

-   <span class="simpara"> 0 - returns the number of words found </span>
-   <span class="simpara"> 1 - returns an array containing all the words
    found inside the `string` </span>
-   <span class="simpara"> 2 - returns an associative array, where the
    key is the numeric position of the word inside the `string` and the
    value is the actual word itself </span>

`charlist`  
A list of additional characters which will be considered as 'word'

### Return Values

Returns an array or an integer, depending on the `format` chosen.

### Examples

**Example \#1 A <span class="function">str\_word\_count</span> example**

``` php
<?php

$str = "Hello fri3nd, you're
       looking          good today!";

print_r(str_word_count($str, 1));
print_r(str_word_count($str, 2));
print_r(str_word_count($str, 1, 'àáãç3'));

echo str_word_count($str);

?>
```

The above example will output:

    Array
    (
        [0] => Hello
        [1] => fri
        [2] => nd
        [3] => you're
        [4] => looking
        [5] => good
        [6] => today
    )

    Array
    (
        [0] => Hello
        [6] => fri
        [10] => nd
        [14] => you're
        [29] => looking
        [46] => good
        [51] => today
    )

    Array
    (
        [0] => Hello
        [1] => fri3nd
        [2] => you're
        [3] => looking
        [4] => good
        [5] => today
    )

    7

### See Also

-   <span class="function">explode</span>
-   <span class="function">preg\_split</span>
-   <span class="function">split</span>
-   <span class="function">count\_chars</span>
-   <span class="function">substr\_count</span>

strcasecmp
==========

Binary safe case-insensitive string comparison

### Description

<span class="type">int</span> <span class="methodname">strcasecmp</span>
( <span class="methodparam"><span class="type">string</span>
`$str1`</span> , <span class="methodparam"><span
class="type">string</span> `$str2`</span> )

Binary safe case-insensitive string comparison.

### Parameters

`str1`  
The first string

`str2`  
The second string

### Return Values

Returns \< 0 if `str1` is less than `str2`; \> 0 if `str1` is greater
than `str2`, and 0 if they are equal.

### Examples

**Example \#1 <span class="function">strcasecmp</span> example**

``` php
<?php
$var1 = "Hello";
$var2 = "hello";
if (strcasecmp($var1, $var2) == 0) {
    echo '$var1 is equal to $var2 in a case-insensitive string comparison';
}
?>
```

### See Also

-   <span class="function">strcmp</span>
-   <span class="function">preg\_match</span>
-   <span class="function">substr\_compare</span>
-   <span class="function">strncasecmp</span>
-   <span class="function">stristr</span>
-   <span class="function">substr</span>

strchr
======

Alias of <span class="function">strstr</span>

### Description

This function is an alias of: <span class="function">strstr</span>.

strcmp
======

Binary safe string comparison

### Description

<span class="type">int</span> <span class="methodname">strcmp</span> (
<span class="methodparam"><span class="type">string</span>
`$str1`</span> , <span class="methodparam"><span
class="type">string</span> `$str2`</span> )

Note that this comparison is case sensitive.

### Parameters

`str1`  
The first string.

`str2`  
The second string.

### Return Values

Returns \< 0 if `str1` is less than `str2`; \> 0 if `str1` is greater
than `str2`, and 0 if they are equal.

### Examples

**Example \#1 <span class="function">strcmp</span> example**

``` php
<?php
$var1 = "Hello";
$var2 = "hello";
if (strcmp($var1, $var2) !== 0) {
    echo '$var1 is not equal to $var2 in a case sensitive string comparison';
}
?>
```

### See Also

-   <span class="function">strcasecmp</span>
-   <span class="function">preg\_match</span>
-   <span class="function">substr\_compare</span>
-   <span class="function">strncmp</span>
-   <span class="function">strstr</span>
-   <span class="function">substr</span>

strcoll
=======

Locale based string comparison

### Description

<span class="type">int</span> <span class="methodname">strcoll</span> (
<span class="methodparam"><span class="type">string</span>
`$str1`</span> , <span class="methodparam"><span
class="type">string</span> `$str2`</span> )

Note that this comparison is case sensitive, and unlike <span
class="function">strcmp</span> this function is not binary safe.

<span class="function">strcoll</span> uses the current locale for doing
the comparisons. If the current locale is C or POSIX, this function is
equivalent to <span class="function">strcmp</span>.

### Parameters

`str1`  
The first string.

`str2`  
The second string.

### Return Values

Returns \< 0 if `str1` is less than `str2`; \> 0 if `str1` is greater
than `str2`, and 0 if they are equal.

### See Also

-   <span class="function">preg\_match</span>
-   <span class="function">strcmp</span>
-   <span class="function">strcasecmp</span>
-   <span class="function">substr</span>
-   <span class="function">stristr</span>
-   <span class="function">strncasecmp</span>
-   <span class="function">strncmp</span>
-   <span class="function">strstr</span>
-   <span class="function">setlocale</span>

strcspn
=======

Find length of initial segment not matching mask

### Description

<span class="type">int</span> <span class="methodname">strcspn</span> (
<span class="methodparam"><span class="type">string</span>
`$subject`</span> , <span class="methodparam"><span
class="type">string</span> `$mask`</span> \[, <span
class="methodparam"><span class="type">int</span> `$start`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`</span>
\]\] )

Returns the length of the initial segment of `subject` which does *not*
contain any of the characters in `mask`.

If `start` and `length` are omitted, then all of `subject` will be
examined. If they are included, then the effect will be the same as
calling *strcspn(substr($subject, $start, $length), $mask)* (see
<a href="/ref/strings.html#substr" class="xref"></a> for more
information).

### Parameters

`subject`  
The string to examine.

`mask`  
The string containing every disallowed character.

`start`  
The position in `subject` to start searching.

If `start` is given and is non-negative, then <span
class="function">strcspn</span> will begin examining `subject` at the
`start`'th position. For instance, in the string '*abcdef*', the
character at position *0* is '*a*', the character at position *2* is
'*c*', and so forth.

If `start` is given and is negative, then <span
class="function">strcspn</span> will begin examining `subject` at the
`start`'th position from the end of `subject`.

`length`  
The length of the segment from `subject` to examine.

If `length` is given and is non-negative, then `subject` will be
examined for `length` characters after the starting position.

If `length` is given and is negative, then `subject` will be examined
from the starting position up to `length` characters from the end of
`subject`.

### Return Values

Returns the length of the initial segment of `subject` which consists
entirely of characters *not* in `mask`.

> **Note**:
>
> When a `start` parameter is set, the returned length is counted
> starting from this position, not from the beginning of `subject`.

### Examples

**Example \#1 <span class="function">strcspn</span> example**

``` php
<?php
$a = strcspn('abcd',  'apple');
$b = strcspn('abcd',  'banana');
$c = strcspn('hello', 'l');
$d = strcspn('hello', 'world');
$e = strcspn('abcdhelloabcd', 'abcd', -9);
$f = strcspn('abcdhelloabcd', 'abcd', -9, -5);

var_dump($a);
var_dump($b);
var_dump($c);
var_dump($d);
var_dump($e);
var_dump($f);
?>
```

The above example will output:

    int(0)
    int(0)
    int(2)
    int(2)
    int(5)
    int(4)

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">strspn</span>

strip\_tags
===========

Strip HTML and PHP tags from a string

### Description

<span class="type">string</span> <span
class="methodname">strip\_tags</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$allowable_tags`</span> \] )

This function tries to return a string with all NULL bytes, HTML and PHP
tags stripped from a given `str`. It uses the same tag stripping state
machine as the <span class="function">fgetss</span> function.

### Parameters

`str`  
The input string.

`allowable_tags`  
You can use the optional second parameter to specify tags which should
not be stripped. These are either given as <span
class="type">string</span>, or as of PHP 7.4.0, as <span
class="type">array</span>. Refer to the example below regarding the
format of this parameter.

> **Note**:
>
> HTML comments and PHP tags are also stripped. This is hardcoded and
> can not be changed with `allowable_tags`.

> **Note**:
>
> In PHP 5.3.4 and later, self-closing XHTML tags are ignored and only
> non-self-closing tags should be used in `allowable_tags`. For example,
> to allow both *\<br\>* and *\<br/\>*, you should use:
>
> ``` php
> <?php
> strip_tags($input, '<br>');
> ?>
> ```

### Return Values

Returns the stripped string.

### Changelog

| Version | Description                                                                        |
|---------|------------------------------------------------------------------------------------|
| 7.4.0   | The `allowable_tags` now alternatively accepts an <span class="type">array</span>. |

### Examples

**Example \#1 <span class="function">strip\_tags</span> example**

``` php
<?php
$text = '<p>Test paragraph.</p><!-- Comment --> <a href="#fragment">Other text</a>';
echo strip_tags($text);
echo "\n";

// Allow <p> and <a>
echo strip_tags($text, '<p><a>');

// as of PHP 7.4.0 the line above can be written as:
// echo strip_tags($text, ['p', 'a']);
?>
```

The above example will output:

    Test paragraph. Other text
    <p>Test paragraph.</p> <a href="#fragment">Other text</a>

### Notes

**Warning**

This function should not be used to try to prevent XSS attacks. Use more
appropriate functions like <span
class="function">htmlspecialchars</span> or other means depending on the
context of the output.

**Warning**

Because <span class="function">strip\_tags</span> does not actually
validate the HTML, partial or broken tags can result in the removal of
more text/data than expected.

**Warning**

This function does not modify any attributes on the tags that you allow
using `allowable_tags`, including the *style* and *onmouseover*
attributes that a mischievous user may abuse when posting text that will
be shown to other users.

> **Note**:
>
> Tag names within the input HTML that are greater than 1023 bytes in
> length will be treated as though they are invalid, regardless of the
> `allowable_tags` parameter.

### See Also

-   <span class="function">htmlspecialchars</span>

stripcslashes
=============

Un-quote string quoted with <span class="function">addcslashes</span>

### Description

<span class="type">string</span> <span
class="methodname">stripcslashes</span> ( <span
class="methodparam"><span class="type">string</span> `$str`</span> )

Returns a string with backslashes stripped off. Recognizes C-like *\\n*,
*\\r* ..., octal and hexadecimal representation.

### Parameters

`str`  
The string to be unescaped.

### Return Values

Returns the unescaped string.

### See Also

-   <span class="function">addcslashes</span>

stripos
=======

Find the position of the first occurrence of a case-insensitive
substring in a string

### Description

<span class="type">int</span> <span class="methodname">stripos</span> (
<span class="methodparam"><span class="type">string</span>
`$haystack`</span> , <span class="methodparam"><span
class="type">mixed</span> `$needle`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 0</span></span> \] )

Find the numeric position of the first occurrence of `needle` in the
`haystack` string.

Unlike the <span class="function">strpos</span>, <span
class="function">stripos</span> is case-insensitive.

### Parameters

`haystack`  
The string to search in.

`needle`  
Note that the `needle` may be a string of one or more characters.

If `needle` is not a string, it is converted to an integer and applied
as the ordinal value of a character. This behavior is deprecated as of
PHP 7.3.0, and relying on it is highly discouraged. Depending on the
intended behavior, the `needle` should either be explicitly cast to
string, or an explicit call to <span class="function">chr</span> should
be performed.

`offset`  
If specified, search will start this number of characters counted from
the beginning of the string. If the offset is negative, the search will
start this number of characters counted from the end of the string.

### Return Values

Returns the position of where the needle exists relative to the
beginnning of the `haystack` string (independent of offset). Also note
that string positions start at 0, and not 1.

Returns **`FALSE`** if the needle was not found.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 7.3.0   | Passing an <span class="type">integer</span> as `needle` has been deprecated. |
| 7.1.0   | Support for negative `offset`s has been added.                                |

### Examples

**Example \#1 <span class="function">stripos</span> examples**

``` php
<?php
$findme    = 'a';
$mystring1 = 'xyz';
$mystring2 = 'ABC';

$pos1 = stripos($mystring1, $findme);
$pos2 = stripos($mystring2, $findme);

// Nope, 'a' is certainly not in 'xyz'
if ($pos1 === false) {
    echo "The string '$findme' was not found in the string '$mystring1'";
}

// Note our use of ===.  Simply == would not work as expected
// because the position of 'a' is the 0th (first) character.
if ($pos2 !== false) {
    echo "We found '$findme' in '$mystring2' at position $pos2";
}
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">mb\_stripos</span>
-   <span class="function">strpos</span>
-   <span class="function">strrpos</span>
-   <span class="function">strripos</span>
-   <span class="function">stristr</span>
-   <span class="function">substr</span>
-   <span class="function">str\_ireplace</span>

stripslashes
============

Un-quotes a quoted string

### Description

<span class="type">string</span> <span
class="methodname">stripslashes</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> )

Un-quotes a quoted string.

An example use of <span class="function">stripslashes</span> is when the
PHP directive
<a href="/info/setup.html#" class="link">magic_quotes_gpc</a> is *on*
(it was on by default before PHP 5.4), and you aren't inserting this
data into a place (such as a database) that requires escaping. For
example, if you're simply outputting data straight from an HTML form.

### Parameters

`str`  
The input string.

### Return Values

Returns a string with backslashes stripped off. (*\\'* becomes *'* and
so on.) Double backslashes (*\\\\*) are made into a single backslash
(*\\*).

### Examples

**Example \#1 A <span class="function">stripslashes</span> example**

``` php
<?php
$str = "Is your name O\'reilly?";

// Outputs: Is your name O'reilly?
echo stripslashes($str);
?>
```

> **Note**:
>
> <span class="function">stripslashes</span> is not recursive. If you
> want to apply this function to a multi-dimensional array, you need to
> use a recursive function.

**Example \#2 Using <span class="function">stripslashes</span> on an
array**

``` php
<?php
function stripslashes_deep($value)
{
    $value = is_array($value) ?
                array_map('stripslashes_deep', $value) :
                stripslashes($value);

    return $value;
}

// Example
$array = array("f\\'oo", "b\\'ar", array("fo\\'o", "b\\'ar"));
$array = stripslashes_deep($array);

// Output
print_r($array);
?>
```

The above example will output:

    Array
    (
        [0] => f'oo
        [1] => b'ar
        [2] => Array
            (
                [0] => fo'o
                [1] => b'ar
            )

    )

### See Also

-   <span class="function">addslashes</span>
-   <span class="function">get\_magic\_quotes\_gpc</span>

stristr
=======

Case-insensitive <span class="function">strstr</span>

### Description

<span class="type">string</span> <span class="methodname">stristr</span>
( <span class="methodparam"><span class="type">string</span>
`$haystack`</span> , <span class="methodparam"><span
class="type">mixed</span> `$needle`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$before_needle`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Returns all of `haystack` starting from and including the first
occurrence of `needle` to the end.

### Parameters

`haystack`  
The string to search in

`needle`  
If `needle` is not a string, it is converted to an integer and applied
as the ordinal value of a character. This behavior is deprecated as of
PHP 7.3.0, and relying on it is highly discouraged. Depending on the
intended behavior, the `needle` should either be explicitly cast to
string, or an explicit call to <span class="function">chr</span> should
be performed.

`before_needle`  
If **`TRUE`**, <span class="function">stristr</span> returns the part of
the `haystack` before the first occurrence of the `needle` (excluding
needle).

`needle` and `haystack` are examined in a case-insensitive manner.

### Return Values

Returns the matched substring. If `needle` is not found, returns
**`FALSE`**.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 7.3.0   | Passing an <span class="type">integer</span> as `needle` has been deprecated. |

### Examples

**Example \#1 <span class="function">stristr</span> example**

``` php
<?php
  $email = 'USER@EXAMPLE.com';
  echo stristr($email, 'e'); // outputs ER@EXAMPLE.com
  echo stristr($email, 'e', true); // As of PHP 5.3.0, outputs US
?>
```

**Example \#2 Testing if a string is found or not**

``` php
<?php
  $string = 'Hello World!';
  if(stristr($string, 'earth') === FALSE) {
    echo '"earth" not found in string';
  }
// outputs: "earth" not found in string
?>
```

**Example \#3 Using a non "string" needle**

``` php
<?php
  $string = 'APPLE';
  echo stristr($string, 97); // 97 = lowercase a
// outputs: APPLE
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">strstr</span>
-   <span class="function">strrchr</span>
-   <span class="function">stripos</span>
-   <span class="function">strpbrk</span>
-   <span class="function">preg\_match</span>

strlen
======

Get string length

### Description

<span class="type">int</span> <span class="methodname">strlen</span> (
<span class="methodparam"><span class="type">string</span>
`$string`</span> )

Returns the length of the given `string`.

### Parameters

`string`  
The <span class="type">string</span> being measured for length.

### Return Values

The length of the `string` on success, and *0* if the `string` is empty.

### Examples

**Example \#1 A <span class="function">strlen</span> example**

``` php
<?php
$str = 'abcdef';
echo strlen($str); // 6

$str = ' ab cd ';
echo strlen($str); // 7
?>
```

### Notes

> **Note**:
>
> <span class="function">strlen</span> returns the number of bytes
> rather than the number of characters in a string.

> **Note**:
>
> <span class="function">strlen</span> returns **`NULL`** when executed
> on arrays, and an **`E_WARNING`** level error is emitted.

### See Also

-   <span class="function">count</span>
-   <span class="function">grapheme\_strlen</span>
-   <span class="function">iconv\_strlen</span>
-   <span class="function">mb\_strlen</span>

strnatcasecmp
=============

Case insensitive string comparisons using a "natural order" algorithm

### Description

<span class="type">int</span> <span
class="methodname">strnatcasecmp</span> ( <span
class="methodparam"><span class="type">string</span> `$str1`</span> ,
<span class="methodparam"><span class="type">string</span>
`$str2`</span> )

This function implements a comparison algorithm that orders alphanumeric
strings in the way a human being would. The behaviour of this function
is similar to <span class="function">strnatcmp</span>, except that the
comparison is not case sensitive. For more information see: Martin
Pool's
<a href="http://sourcefrog.net/projects/natsort/" class="link external">» Natural Order String Comparison</a>
page.

### Parameters

`str1`  
The first string.

`str2`  
The second string.

### Return Values

Similar to other string comparison functions, this one returns \< 0 if
`str1` is less than `str2` \> 0 if `str1` is greater than `str2`, and 0
if they are equal.

### See Also

-   <span class="function">preg\_match</span>
-   <span class="function">strcmp</span>
-   <span class="function">strcasecmp</span>
-   <span class="function">substr</span>
-   <span class="function">stristr</span>
-   <span class="function">strncasecmp</span>
-   <span class="function">strncmp</span>
-   <span class="function">strstr</span>
-   <span class="function">setlocale</span>

strnatcmp
=========

String comparisons using a "natural order" algorithm

### Description

<span class="type">int</span> <span class="methodname">strnatcmp</span>
( <span class="methodparam"><span class="type">string</span>
`$str1`</span> , <span class="methodparam"><span
class="type">string</span> `$str2`</span> )

This function implements a comparison algorithm that orders alphanumeric
strings in the way a human being would, this is described as a "natural
ordering". Note that this comparison is case sensitive.

### Parameters

`str1`  
The first string.

`str2`  
The second string.

### Return Values

Similar to other string comparison functions, this one returns \< 0 if
`str1` is less than `str2`; \> 0 if `str1` is greater than `str2`, and 0
if they are equal.

### Examples

An example of the difference between this algorithm and the regular
computer string sorting algorithms (used in <span
class="function">strcmp</span>) can be seen below:

``` php
<?php
$arr1 = $arr2 = array("img12.png", "img10.png", "img2.png", "img1.png");
echo "Standard string comparison\n";
usort($arr1, "strcmp");
print_r($arr1);
echo "\nNatural order string comparison\n";
usort($arr2, "strnatcmp");
print_r($arr2);
?>
```

The above example will output:

    Standard string comparison
    Array
    (
        [0] => img1.png
        [1] => img10.png
        [2] => img12.png
        [3] => img2.png
    )

    Natural order string comparison
    Array
    (
        [0] => img1.png
        [1] => img2.png
        [2] => img10.png
        [3] => img12.png
    )

For more information see: Martin Pool's
<a href="http://sourcefrog.net/projects/natsort/" class="link external">» Natural Order String Comparison</a>
page.

### See Also

-   <span class="function">preg\_match</span>
-   <span class="function">strcasecmp</span>
-   <span class="function">substr</span>
-   <span class="function">stristr</span>
-   <span class="function">strcmp</span>
-   <span class="function">strncmp</span>
-   <span class="function">strncasecmp</span>
-   <span class="function">strnatcasecmp</span>
-   <span class="function">strstr</span>
-   <span class="function">natsort</span>
-   <span class="function">natcasesort</span>

strncasecmp
===========

Binary safe case-insensitive string comparison of the first n characters

### Description

<span class="type">int</span> <span
class="methodname">strncasecmp</span> ( <span class="methodparam"><span
class="type">string</span> `$str1`</span> , <span
class="methodparam"><span class="type">string</span> `$str2`</span> ,
<span class="methodparam"><span class="type">int</span> `$len`</span> )

This function is similar to <span class="function">strcasecmp</span>,
with the difference that you can specify the (upper limit of the) number
of characters from each string to be used in the comparison.

### Parameters

`str1`  
The first string.

`str2`  
The second string.

`len`  
The length of strings to be used in the comparison.

### Return Values

Returns \< 0 if `str1` is less than `str2`; \> 0 if `str1` is greater
than `str2`, and 0 if they are equal.

### See Also

-   <span class="function">strncmp</span>
-   <span class="function">preg\_match</span>
-   <span class="function">substr\_compare</span>
-   <span class="function">strcasecmp</span>
-   <span class="function">stristr</span>
-   <span class="function">substr</span>

strncmp
=======

Binary safe string comparison of the first n characters

### Description

<span class="type">int</span> <span class="methodname">strncmp</span> (
<span class="methodparam"><span class="type">string</span>
`$str1`</span> , <span class="methodparam"><span
class="type">string</span> `$str2`</span> , <span
class="methodparam"><span class="type">int</span> `$len`</span> )

This function is similar to <span class="function">strcmp</span>, with
the difference that you can specify the (upper limit of the) number of
characters from each string to be used in the comparison.

Note that this comparison is case sensitive.

### Parameters

`str1`  
The first string.

`str2`  
The second string.

`len`  
Number of characters to use in the comparison.

### Return Values

Returns \< 0 if `str1` is less than `str2`; \> 0 if `str1` is greater
than `str2`, and 0 if they are equal.

### See Also

-   <span class="function">strncasecmp</span>
-   <span class="function">preg\_match</span>
-   <span class="function">substr\_compare</span>
-   <span class="function">strcmp</span>
-   <span class="function">strstr</span>
-   <span class="function">substr</span>

strpbrk
=======

Search a string for any of a set of characters

### Description

<span class="type">string</span> <span class="methodname">strpbrk</span>
( <span class="methodparam"><span class="type">string</span>
`$haystack`</span> , <span class="methodparam"><span
class="type">string</span> `$char_list`</span> )

<span class="function">strpbrk</span> searches the `haystack` string for
a `char_list`.

### Parameters

`haystack`  
The string where `char_list` is looked for.

`char_list`  
This parameter is case sensitive.

### Return Values

Returns a string starting from the character found, or **`FALSE`** if it
is not found.

### Examples

**Example \#1 <span class="function">strpbrk</span> example**

``` php
<?php

$text = 'This is a Simple text.';

// this echoes "is is a Simple text." because 'i' is matched first
echo strpbrk($text, 'mi');

// this echoes "Simple text." because chars are case sensitive
echo strpbrk($text, 'S');
?>
```

### See Also

-   <span class="function">strpos</span>
-   <span class="function">strstr</span>
-   <span class="function">preg\_match</span>

strpos
======

Find the position of the first occurrence of a substring in a string

### Description

<span class="type">int</span> <span class="methodname">strpos</span> (
<span class="methodparam"><span class="type">string</span>
`$haystack`</span> , <span class="methodparam"><span
class="type">mixed</span> `$needle`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 0</span></span> \] )

Find the numeric position of the first occurrence of `needle` in the
`haystack` string.

### Parameters

`haystack`  
The string to search in.

`needle`  
If `needle` is not a string, it is converted to an integer and applied
as the ordinal value of a character. This behavior is deprecated as of
PHP 7.3.0, and relying on it is highly discouraged. Depending on the
intended behavior, the `needle` should either be explicitly cast to
string, or an explicit call to <span class="function">chr</span> should
be performed.

`offset`  
If specified, search will start this number of characters counted from
the beginning of the string. If the offset is negative, the search will
start this number of characters counted from the end of the string.

### Return Values

Returns the position of where the needle exists relative to the
beginning of the `haystack` string (independent of offset). Also note
that string positions start at 0, and not 1.

Returns **`FALSE`** if the needle was not found.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 7.3.0   | Passing an <span class="type">integer</span> as `needle` has been deprecated. |
| 7.1.0   | Support for negative `offset`s has been added.                                |

### Examples

**Example \#1 Using *===***

``` php
<?php
$mystring = 'abc';
$findme   = 'a';
$pos = strpos($mystring, $findme);

// Note our use of ===.  Simply == would not work as expected
// because the position of 'a' was the 0th (first) character.
if ($pos === false) {
    echo "The string '$findme' was not found in the string '$mystring'";
} else {
    echo "The string '$findme' was found in the string '$mystring'";
    echo " and exists at position $pos";
}
?>
```

**Example \#2 Using !==**

``` php
<?php
$mystring = 'abc';
$findme   = 'a';
$pos = strpos($mystring, $findme);

// The !== operator can also be used.  Using != would not work as expected
// because the position of 'a' is 0. The statement (0 != false) evaluates 
// to false.
if ($pos !== false) {
     echo "The string '$findme' was found in the string '$mystring'";
         echo " and exists at position $pos";
} else {
     echo "The string '$findme' was not found in the string '$mystring'";
}
?>
```

**Example \#3 Using an offset**

``` php
<?php
// We can search for the character, ignoring anything before the offset
$newstring = 'abcdef abcdef';
$pos = strpos($newstring, 'a', 1); // $pos = 7, not 0
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">stripos</span>
-   <span class="function">strrpos</span>
-   <span class="function">strripos</span>
-   <span class="function">strstr</span>
-   <span class="function">strpbrk</span>
-   <span class="function">substr</span>
-   <span class="function">preg\_match</span>

strrchr
=======

Find the last occurrence of a character in a string

### Description

<span class="type">string</span> <span class="methodname">strrchr</span>
( <span class="methodparam"><span class="type">string</span>
`$haystack`</span> , <span class="methodparam"><span
class="type">mixed</span> `$needle`</span> )

This function returns the portion of `haystack` which starts at the last
occurrence of `needle` and goes until the end of `haystack`.

### Parameters

`haystack`  
The string to search in

`needle`  
If `needle` contains more than one character, only the first is used.
This behavior is different from that of <span
class="function">strstr</span>.

If `needle` is not a string, it is converted to an integer and applied
as the ordinal value of a character. This behavior is deprecated as of
PHP 7.3.0, and relying on it is highly discouraged. Depending on the
intended behavior, the `needle` should either be explicitly cast to
string, or an explicit call to <span class="function">chr</span> should
be performed.

### Return Values

This function returns the portion of string, or **`FALSE`** if `needle`
is not found.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 7.3.0   | Passing an <span class="type">integer</span> as `needle` has been deprecated. |

### Examples

**Example \#1 <span class="function">strrchr</span> example**

``` php
<?php
// get last directory in $PATH
$dir = substr(strrchr($PATH, ":"), 1);

// get everything after last newline
$text = "Line 1\nLine 2\nLine 3";
$last = substr(strrchr($text, 10), 1 );
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">strstr</span>
-   <span class="function">strrpos</span>

strrev
======

Reverse a string

### Description

<span class="type">string</span> <span class="methodname">strrev</span>
( <span class="methodparam"><span class="type">string</span>
`$string`</span> )

Returns `string`, reversed.

### Parameters

`string`  
The string to be reversed.

### Return Values

Returns the reversed string.

### Examples

**Example \#1 Reversing a string with <span
class="function">strrev</span>**

``` php
<?php
echo strrev("Hello world!"); // outputs "!dlrow olleH"
?>
```

strripos
========

Find the position of the last occurrence of a case-insensitive substring
in a string

### Description

<span class="type">int</span> <span class="methodname">strripos</span> (
<span class="methodparam"><span class="type">string</span>
`$haystack`</span> , <span class="methodparam"><span
class="type">mixed</span> `$needle`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 0</span></span> \] )

Find the numeric position of the last occurrence of `needle` in the
`haystack` string.

Unlike the <span class="function">strrpos</span>, <span
class="function">strripos</span> is case-insensitive.

### Parameters

`haystack`  
The string to search in.

`needle`  
If `needle` is not a string, it is converted to an integer and applied
as the ordinal value of a character. This behavior is deprecated as of
PHP 7.3.0, and relying on it is highly discouraged. Depending on the
intended behavior, the `needle` should either be explicitly cast to
string, or an explicit call to <span class="function">chr</span> should
be performed.

`offset`  
If zero or positive, the search is performed left to right skipping the
first `offset` bytes of the `haystack`.

If negative, the search is performed right to left skipping the last
`offset` bytes of the `haystack` and searching for the first occurrence
of `needle`.

> **Note**:
>
> This is effectively looking for the last occurrence of `needle` before
> the last `offset` bytes.

### Return Values

Returns the position where the needle exists relative to the beginnning
of the `haystack` string (independent of search direction or offset).

> **Note**: <span class="simpara"> String positions start at 0, and not
> 1. </span>

Returns **`FALSE`** if the needle was not found.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 7.3.0   | Passing an <span class="type">integer</span> as `needle` has been deprecated. |

### Examples

**Example \#1 A simple <span class="function">strripos</span> example**

``` php
<?php
$haystack = 'ababcd';
$needle   = 'aB';

$pos      = strripos($haystack, $needle);

if ($pos === false) {
    echo "Sorry, we did not find ($needle) in ($haystack)";
} else {
    echo "Congratulations!\n";
    echo "We found the last ($needle) in ($haystack) at position ($pos)";
}
?>
```

The above example will output:

       Congratulations!
       We found the last (aB) in (ababcd) at position (2)

### See Also

-   <span class="function">strpos</span>
-   <span class="function">stripos</span>
-   <span class="function">strrpos</span>
-   <span class="function">strrchr</span>
-   <span class="function">stristr</span>
-   <span class="function">substr</span>

strrpos
=======

Find the position of the last occurrence of a substring in a string

### Description

<span class="type">int</span> <span class="methodname">strrpos</span> (
<span class="methodparam"><span class="type">string</span>
`$haystack`</span> , <span class="methodparam"><span
class="type">mixed</span> `$needle`</span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = 0</span></span> \] )

Find the numeric position of the last occurrence of `needle` in the
`haystack` string.

### Parameters

`haystack`  
The string to search in.

`needle`  
If `needle` is not a string, it is converted to an integer and applied
as the ordinal value of a character. This behavior is deprecated as of
PHP 7.3.0, and relying on it is highly discouraged. Depending on the
intended behavior, the `needle` should either be explicitly cast to
string, or an explicit call to <span class="function">chr</span> should
be performed.

`offset`  
If zero or positive, the search is performed left to right skipping the
first `offset` bytes of the `haystack`.

If negative, the search is performed right to left skipping the last
`offset` bytes of the `haystack` and searching for the first occurrence
of `needle`.

> **Note**:
>
> This is effectively looking for the last occurrence of `needle` before
> the last `offset` bytes.

### Return Values

Returns the position where the needle exists relative to the beginning
of the `haystack` string (independent of search direction or offset).

> **Note**: <span class="simpara"> String positions start at 0, and not
> 1. </span>

Returns **`FALSE`** if the needle was not found.

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 7.3.0   | Passing an <span class="type">integer</span> as `needle` has been deprecated. |

### Examples

**Example \#1 Checking if a needle is in the haystack**

It is easy to mistake the return values for "character found at position
0" and "character not found". Here's how to detect the difference:

``` php
<?php

$pos = strrpos($mystring, "b");
if ($pos === false) { // note: three equal signs
    // not found...
}

?>
```

**Example \#2 Searching with offsets**

``` php
<?php
$foo = "0123456789a123456789b123456789c";

// Looking for '0' from the 0th byte (from the beginning)
var_dump(strrpos($foo, '0', 0));

// Looking for '0' from the 1st byte (after byte "0")
var_dump(strrpos($foo, '0', 1));

// Looking for '7' from the 21th byte (after byte 20)
var_dump(strrpos($foo, '7', 20));

// Looking for '7' from the 29th byte (after byte 28)
var_dump(strrpos($foo, '7', 28));

// Looking for '7' right to left from the 5th byte from the end
var_dump(strrpos($foo, '7', -5));

// Looking for 'c' right to left from the 2nd byte from the end
var_dump(strrpos($foo, 'c', -2));

// Looking for '9c' right to left from the 2nd byte from the end
var_dump(strrpos($foo, '9c', -2));
?>
```

The above example will output:

    int(0)
    bool(false)
    int(27)
    bool(false)
    int(17)
    bool(false)
    int(29)

### See Also

-   <span class="function">strpos</span>
-   <span class="function">stripos</span>
-   <span class="function">strripos</span>
-   <span class="function">strrchr</span>
-   <span class="function">substr</span>

strspn
======

Finds the length of the initial segment of a string consisting entirely
of characters contained within a given mask

### Description

<span class="type">int</span> <span class="methodname">strspn</span> (
<span class="methodparam"><span class="type">string</span>
`$subject`</span> , <span class="methodparam"><span
class="type">string</span> `$mask`</span> \[, <span
class="methodparam"><span class="type">int</span> `$start`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`</span>
\]\] )

Finds the length of the initial segment of `subject` that contains
*only* characters from `mask`.

If `start` and `length` are omitted, then all of `subject` will be
examined. If they are included, then the effect will be the same as
calling *strspn(substr($subject, $start, $length), $mask)* (see
<a href="/ref/strings.html#substr" class="xref"></a> for more
information).

The line of code:

``` php
<?php
$var = strspn("42 is the answer to the 128th question.", "1234567890");
?>
```

will assign *2* to `$var`, because the string "42" is the initial
segment of `subject` that consists only of characters contained within
"1234567890".

### Parameters

`subject`  
The string to examine.

`mask`  
The list of allowable characters.

`start`  
The position in `subject` to start searching.

If `start` is given and is non-negative, then <span
class="function">strspn</span> will begin examining `subject` at the
`start`'th position. For instance, in the string '*abcdef*', the
character at position *0* is '*a*', the character at position *2* is
'*c*', and so forth.

If `start` is given and is negative, then <span
class="function">strspn</span> will begin examining `subject` at the
`start`'th position from the end of `subject`.

`length`  
The length of the segment from `subject` to examine.

If `length` is given and is non-negative, then `subject` will be
examined for `length` characters after the starting position.

If `length` is given and is negative, then `subject` will be examined
from the starting position up to `length` characters from the end of
`subject`.

### Return Values

Returns the length of the initial segment of `subject` which consists
entirely of characters in `mask`.

> **Note**:
>
> When a `start` parameter is set, the returned length is counted
> starting from this position, not from the beginning of `subject`.

### Examples

**Example \#1 <span class="function">strspn</span> example**

``` php
<?php
// subject does not start with any characters from mask
var_dump(strspn("foo", "o"));

// examine two characters from subject starting at offset 1
var_dump(strspn("foo", "o", 1, 2));

// examine one character from subject starting at offset 1
var_dump(strspn("foo", "o", 1, 1));
?>
```

The above example will output:

    int(0)
    int(2)
    int(1)

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">strcspn</span>

strstr
======

Find the first occurrence of a string

### Description

<span class="type">string</span> <span class="methodname">strstr</span>
( <span class="methodparam"><span class="type">string</span>
`$haystack`</span> , <span class="methodparam"><span
class="type">mixed</span> `$needle`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$before_needle`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Returns part of `haystack` string starting from and including the first
occurrence of `needle` to the end of `haystack`.

> **Note**:
>
> This function is case-sensitive. For case-insensitive searches, use
> <span class="function">stristr</span>.

> **Note**:
>
> If you only want to determine if a particular `needle` occurs within
> `haystack`, use the faster and less memory intensive function <span
> class="function">strpos</span> instead.

### Parameters

`haystack`  
The input string.

`needle`  
If `needle` is not a string, it is converted to an integer and applied
as the ordinal value of a character. This behavior is deprecated as of
PHP 7.3.0, and relying on it is highly discouraged. Depending on the
intended behavior, the `needle` should either be explicitly cast to
string, or an explicit call to <span class="function">chr</span> should
be performed.

`before_needle`  
If **`TRUE`**, <span class="function">strstr</span> returns the part of
the `haystack` before the first occurrence of the `needle` (excluding
the needle).

### Return Values

Returns the portion of string, or **`FALSE`** if `needle` is not found.

### Changelog

| Version | Description                                                                   |
|---------|-------------------------------------------------------------------------------|
| 7.3.0   | Passing an <span class="type">integer</span> as `needle` has been deprecated. |

### Examples

**Example \#1 <span class="function">strstr</span> example**

``` php
<?php
$email  = 'name@example.com';
$domain = strstr($email, '@');
echo $domain; // prints @example.com

$user = strstr($email, '@', true); // As of PHP 5.3.0
echo $user; // prints name
?>
```

### See Also

-   <span class="function">stristr</span>
-   <span class="function">strrchr</span>
-   <span class="function">strpos</span>
-   <span class="function">strpbrk</span>
-   <span class="function">preg\_match</span>

strtok
======

Tokenize string

### Description

<span class="type">string</span> <span class="methodname">strtok</span>
( <span class="methodparam"><span class="type">string</span>
`$str`</span> , <span class="methodparam"><span
class="type">string</span> `$token`</span> )

<span class="type">string</span> <span class="methodname">strtok</span>
( <span class="methodparam"><span class="type">string</span>
`$token`</span> )

<span class="function">strtok</span> splits a string (`str`) into
smaller strings (tokens), with each token being delimited by any
character from `token`. That is, if you have a string like "This is an
example string" you could tokenize this string into its individual words
by using the space character as the token.

Note that only the first call to strtok uses the string argument. Every
subsequent call to strtok only needs the token to use, as it keeps track
of where it is in the current string. To start over, or to tokenize a
new string you simply call strtok with the string argument again to
initialize it. Note that you may put multiple tokens in the token
parameter. The string will be tokenized when any one of the characters
in the argument is found.

### Parameters

`str`  
The <span class="type">string</span> being split up into smaller strings
(tokens).

`token`  
The delimiter used when splitting up `str`.

### Return Values

A <span class="type">string</span> token.

### Examples

**Example \#1 <span class="function">strtok</span> example**

``` php
<?php
$string = "This is\tan example\nstring";
/* Use tab and newline as tokenizing characters as well  */
$tok = strtok($string, " \n\t");

while ($tok !== false) {
    echo "Word=$tok<br />";
    $tok = strtok(" \n\t");
}
?>
```

**Example \#2 <span class="function">strtok</span> behavior on empty
part found**

``` php
<?php
$first_token  = strtok('/something', '/');
$second_token = strtok('/');
var_dump($first_token, $second_token);
?>
```

The above example will output:

        string(9) "something"
        bool(false)

### Notes

**Warning**

This function may return Boolean **`FALSE`**, but may also return a
non-Boolean value which evaluates to **`FALSE`**. Please read the
section on
<a href="/language/types/boolean.html" class="link">Booleans</a> for
more information. Use
<a href="/language/operators/comparison.html" class="link">the === operator</a>
for testing the return value of this function.

### See Also

-   <span class="function">split</span>
-   <span class="function">explode</span>

strtolower
==========

Make a string lowercase

### Description

<span class="type">string</span> <span
class="methodname">strtolower</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> )

Returns `string` with all alphabetic characters converted to lowercase.

Note that 'alphabetic' is determined by the current locale. This means
that e.g. in the default "C" locale, characters such as umlaut-A (Ä)
will not be converted.

### Parameters

`string`  
The input string.

### Return Values

Returns the lowercased string.

### Examples

**Example \#1 <span class="function">strtolower</span> example**

``` php
<?php
$str = "Mary Had A Little Lamb and She LOVED It So";
$str = strtolower($str);
echo $str; // Prints mary had a little lamb and she loved it so
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">strtoupper</span>
-   <span class="function">ucfirst</span>
-   <span class="function">ucwords</span>
-   <span class="function">mb\_strtolower</span>

strtoupper
==========

Make a string uppercase

### Description

<span class="type">string</span> <span
class="methodname">strtoupper</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> )

Returns `string` with all alphabetic characters converted to uppercase.

Note that 'alphabetic' is determined by the current locale. For
instance, in the default "C" locale characters such as umlaut-a (ä) will
not be converted.

### Parameters

`string`  
The input string.

### Return Values

Returns the uppercased string.

### Examples

**Example \#1 <span class="function">strtoupper</span> example**

``` php
<?php
$str = "Mary Had A Little Lamb and She LOVED It So";
$str = strtoupper($str);
echo $str; // Prints MARY HAD A LITTLE LAMB AND SHE LOVED IT SO
?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">strtolower</span>
-   <span class="function">ucfirst</span>
-   <span class="function">ucwords</span>
-   <span class="function">mb\_strtoupper</span>

strtr
=====

Translate characters or replace substrings

### Description

<span class="type">string</span> <span class="methodname">strtr</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
, <span class="methodparam"><span class="type">string</span>
`$from`</span> , <span class="methodparam"><span
class="type">string</span> `$to`</span> )

<span class="type">string</span> <span class="methodname">strtr</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
, <span class="methodparam"><span class="type">array</span>
`$replace_pairs`</span> )

If given three arguments, this function returns a copy of `str` where
all occurrences of each (single-byte) character in `from` have been
translated to the corresponding character in `to`, i.e., every
occurrence of *$from\[$n\]* has been replaced with *$to\[$n\]*, where
*$n* is a valid offset in both arguments.

If `from` and `to` have different lengths, the extra characters in the
longer of the two are ignored. The length of `str` will be the same as
the return value's.

If given two arguments, the second should be an <span
class="type">array</span> in the form *array('from' =\> 'to', ...)*. The
return value is a <span class="type">string</span> where all the
occurrences of the array keys have been replaced by the corresponding
values. The longest keys will be tried first. Once a substring has been
replaced, its new value will not be searched again.

In this case, the keys and the values may have any length, provided that
there is no empty key; additionally, the length of the return value may
differ from that of `str`. However, this function will be the most
efficient when all the keys have the same size.

### Parameters

`str`  
The <span class="type">string</span> being translated.

`from`  
The <span class="type">string</span> being translated to `to`.

`to`  
The <span class="type">string</span> replacing `from`.

`replace_pairs`  
The `replace_pairs` parameter may be used instead of `to` and `from`, in
which case it's an <span class="type">array</span> in the form
*array('from' =\> 'to', ...)*.

### Return Values

Returns the translated <span class="type">string</span>.

If `replace_pairs` contains a key which is an empty <span
class="type">string</span> (*""*), **`FALSE`** will be returned. If the
`str` is not a scalar then it is not typecasted into a string, instead a
warning is raised and **`NULL`** is returned.

### Examples

**Example \#1 <span class="function">strtr</span> example**

``` php
<?php
//In this form, strtr() does byte-by-byte translation
//Therefore, we are assuming a single-byte encoding here:
$addr = strtr($addr, "äåö", "aao");
?>
```

The next example shows the behavior of <span
class="function">strtr</span> when called with only two arguments. Note
the preference of the replacements (*"h"* is not picked because there
are longer matches) and how replaced text was not searched again.

**Example \#2 <span class="function">strtr</span> example with two
arguments**

``` php
<?php
$trans = array("h" => "-", "hello" => "hi", "hi" => "hello");
echo strtr("hi all, I said hello", $trans);
?>
```

The above example will output:

    hello all, I said hi

The two modes of behavior are substantially different. With three
arguments, <span class="function">strtr</span> will replace bytes; with
two, it may replace longer substrings.

**Example \#3 <span class="function">strtr</span> behavior comparison**

``` php
<?php
echo strtr("baab", "ab", "01"),"\n";

$trans = array("ab" => "01");
echo strtr("baab", $trans);
?>
```

The above example will output:

    1001
    ba01

### See Also

-   <span class="function">str\_replace</span>
-   <span class="function">preg\_replace</span>

substr\_compare
===============

Binary safe comparison of two strings from an offset, up to length
characters

### Description

<span class="type">int</span> <span
class="methodname">substr\_compare</span> ( <span
class="methodparam"><span class="type">string</span> `$main_str`</span>
, <span class="methodparam"><span class="type">string</span>
`$str`</span> , <span class="methodparam"><span class="type">int</span>
`$offset`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \[, <span
class="methodparam"><span class="type">bool</span>
`$case_insensitivity`<span class="initializer"> =
**`FALSE`**</span></span> \]\] )

<span class="function">substr\_compare</span> compares `main_str` from
position `offset` with `str` up to `length` characters.

### Parameters

`main_str`  
The main string being compared.

`str`  
The secondary string being compared.

`offset`  
The start position for the comparison. If negative, it starts counting
from the end of the string.

`length`  
The length of the comparison. The default value is the largest of the
length of the `str` compared to the length of `main_str` minus the
`offset`.

`case_insensitivity`  
If `case_insensitivity` is **`TRUE`**, comparison is case insensitive.

### Return Values

Returns \< 0 if `main_str` from position `offset` is less than `str`, \>
0 if it is greater than `str`, and 0 if they are equal. If `offset` is
equal to (prior to PHP 7.2.18, 7.3.5) or greater than the length of
`main_str`, or the `length` is set and is less than 0, (or, prior to PHP
5.5.11, less than 1) <span class="function">substr\_compare</span>
prints a warning and returns **`FALSE`**.

### Changelog

| Version       | Description                                            |
|---------------|--------------------------------------------------------|
| 7.2.18, 7.3.5 | `offset` may now be equal to the length of `main_str`. |

### Examples

**Example \#1 A <span class="function">substr\_compare</span> example**

``` php
<?php
echo substr_compare("abcde", "bc", 1, 2); // 0
echo substr_compare("abcde", "de", -2, 2); // 0
echo substr_compare("abcde", "bcg", 1, 2); // 0
echo substr_compare("abcde", "BC", 1, 2, true); // 0
echo substr_compare("abcde", "bc", 1, 3); // 1
echo substr_compare("abcde", "cd", 1, 2); // -1
echo substr_compare("abcde", "abc", 5, 1); // warning
?>
```

### See Also

-   <span class="function">strncmp</span>

substr\_count
=============

Count the number of substring occurrences

### Description

<span class="type">int</span> <span
class="methodname">substr\_count</span> ( <span
class="methodparam"><span class="type">string</span> `$haystack`</span>
, <span class="methodparam"><span class="type">string</span>
`$needle`</span> \[, <span class="methodparam"><span
class="type">int</span> `$offset`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$length`</span> \]\] )

<span class="function">substr\_count</span> returns the number of times
the `needle` substring occurs in the `haystack` string. Please note that
`needle` is case sensitive.

> **Note**:
>
> This function doesn't count overlapped substrings. See the example
> below!

### Parameters

`haystack`  
The string to search in

`needle`  
The substring to search for

`offset`  
The offset where to start counting. If the offset is negative, counting
starts from the end of the string.

`length`  
The maximum length after the specified offset to search for the
substring. It outputs a warning if the offset plus the length is greater
than the `haystack` length. A negative length counts from the end of
`haystack`.

### Return Values

This function returns an <span class="type">integer</span>.

### Changelog

| Version | Description                                                                                |
|---------|--------------------------------------------------------------------------------------------|
| 7.1.0   | Support for negative `offset`s and `length`s has been added. `length` may also be *0* now. |

### Examples

**Example \#1 A <span class="function">substr\_count</span> example**

``` php
<?php
$text = 'This is a test';
echo strlen($text); // 14

echo substr_count($text, 'is'); // 2

// the string is reduced to 's is a test', so it prints 1
echo substr_count($text, 'is', 3);

// the text is reduced to 's i', so it prints 0
echo substr_count($text, 'is', 3, 3);

// generates a warning because 5+10 > 14
echo substr_count($text, 'is', 5, 10);


// prints only 1, because it doesn't count overlapped substrings
$text2 = 'gcdgcdgcd';
echo substr_count($text2, 'gcdgcd');
?>
```

### See Also

-   <span class="function">count\_chars</span>
-   <span class="function">strpos</span>
-   <span class="function">substr</span>
-   <span class="function">strstr</span>

substr\_replace
===============

Replace text within a portion of a string

### Description

<span class="type">mixed</span> <span
class="methodname">substr\_replace</span> ( <span
class="methodparam"><span class="type">mixed</span> `$string`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$replacement`</span> , <span class="methodparam"><span
class="type">mixed</span> `$start`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$length`</span> \]
)

<span class="function">substr\_replace</span> replaces a copy of
`string` delimited by the `start` and (optionally) `length` parameters
with the string given in `replacement`.

### Parameters

`string`  
The input string.

An <span class="type">array</span> of <span class="type">string</span>s
can be provided, in which case the replacements will occur on each
string in turn. In this case, the `replacement`, `start` and `length`
parameters may be provided either as scalar values to be applied to each
input string in turn, or as <span class="type">array</span>s, in which
case the corresponding array element will be used for each input string.

`replacement`  
The replacement string.

`start`  
If `start` is non-negative, the replacing will begin at the `start`'th
offset into `string`.

If `start` is negative, the replacing will begin at the `start`'th
character from the end of `string`.

`length`  
If given and is positive, it represents the length of the portion of
`string` which is to be replaced. If it is negative, it represents the
number of characters from the end of `string` at which to stop
replacing. If it is not given, then it will default to strlen( `string`
); i.e. end the replacing at the end of `string`. Of course, if `length`
is zero then this function will have the effect of inserting
`replacement` into `string` at the given `start` offset.

### Return Values

The result string is returned. If `string` is an array then array is
returned.

### Examples

**Example \#1 Simple <span class="function">substr\_replace</span>
examples**

``` php
<?php
$var = 'ABCDEFGH:/MNRPQR/';
echo "Original: $var<hr />\n";

/* These two examples replace all of $var with 'bob'. */
echo substr_replace($var, 'bob', 0) . "<br />\n";
echo substr_replace($var, 'bob', 0, strlen($var)) . "<br />\n";

/* Insert 'bob' right at the beginning of $var. */
echo substr_replace($var, 'bob', 0, 0) . "<br />\n";

/* These next two replace 'MNRPQR' in $var with 'bob'. */
echo substr_replace($var, 'bob', 10, -1) . "<br />\n";
echo substr_replace($var, 'bob', -7, -1) . "<br />\n";

/* Delete 'MNRPQR' from $var. */
echo substr_replace($var, '', 10, -1) . "<br />\n";
?>
```

**Example \#2 Using <span class="function">substr\_replace</span> to
replace multiple strings at once**

``` php
<?php
$input = array('A: XXX', 'B: XXX', 'C: XXX');

// A simple case: replace XXX in each string with YYY.
echo implode('; ', substr_replace($input, 'YYY', 3, 3))."\n";

// A more complicated case where each replacement is different.
$replace = array('AAA', 'BBB', 'CCC');
echo implode('; ', substr_replace($input, $replace, 3, 3))."\n";

// Replace a different number of characters each time.
$length = array(1, 2, 3);
echo implode('; ', substr_replace($input, $replace, 3, $length))."\n";
?>
```

The above example will output:

    A: YYY; B: YYY; C: YYY
    A: AAA; B: BBB; C: CCC
    A: AAAXX; B: BBBX; C: CCC

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">str\_replace</span>
-   <span class="function">substr</span>
-   <a href="/language/types/string.html#language.types.string.substr" class="link">String access and modification by character</a>

substr
======

Return part of a string

### Description

<span class="type">string</span> <span class="methodname">substr</span>
( <span class="methodparam"><span class="type">string</span>
`$string`</span> , <span class="methodparam"><span
class="type">int</span> `$start`</span> \[, <span
class="methodparam"><span class="type">int</span> `$length`</span> \] )

Returns the portion of `string` specified by the `start` and `length`
parameters.

### Parameters

`string`  
The input string.

`start`  
If `start` is non-negative, the returned string will start at the
`start`'th position in `string`, counting from zero. For instance, in
the string '*abcdef*', the character at position *0* is '*a*', the
character at position *2* is '*c*', and so forth.

If `start` is negative, the returned string will start at the `start`'th
character from the end of `string`.

If `string` is less than `start` characters long, **`FALSE`** will be
returned.

**Example \#1 Using a negative `start`**

``` php
<?php
$rest = substr("abcdef", -1);    // returns "f"
$rest = substr("abcdef", -2);    // returns "ef"
$rest = substr("abcdef", -3, 1); // returns "d"
?>
```

`length`  
If `length` is given and is positive, the string returned will contain
at most `length` characters beginning from `start` (depending on the
length of `string`).

If `length` is given and is negative, then that many characters will be
omitted from the end of `string` (after the start position has been
calculated when a `start` is negative). If `start` denotes the position
of this truncation or beyond, **`FALSE`** will be returned.

If `length` is given and is *0*, **`FALSE`** or **`NULL`**, an empty
string will be returned.

If `length` is omitted, the substring starting from `start` until the
end of the string will be returned.

**Example \#2 Using a negative `length`**

``` php
<?php
$rest = substr("abcdef", 0, -1);  // returns "abcde"
$rest = substr("abcdef", 2, -1);  // returns "cde"
$rest = substr("abcdef", 4, -4);  // returns false
$rest = substr("abcdef", -3, -1); // returns "de"
?>
```

### Return Values

Returns the extracted part of `string`; or **`FALSE`** on failure, or an
empty string.

### Examples

**Example \#3 Basic <span class="function">substr</span> usage**

``` php
<?php
echo substr('abcdef', 1);     // bcdef
echo substr('abcdef', 1, 3);  // bcd
echo substr('abcdef', 0, 4);  // abcd
echo substr('abcdef', 0, 8);  // abcdef
echo substr('abcdef', -1, 1); // f

// Accessing single characters in a string
// can also be achieved using "square brackets"
$string = 'abcdef';
echo $string[0];                 // a
echo $string[3];                 // d
echo $string[strlen($string)-1]; // f

?>
```

**Example \#4 <span class="function">substr</span> casting behaviour**

``` php
<?php
class apple {
    public function __toString() {
        return "green";
    }
}

echo "1) ".var_export(substr("pear", 0, 2), true).PHP_EOL;
echo "2) ".var_export(substr(54321, 0, 2), true).PHP_EOL;
echo "3) ".var_export(substr(new apple(), 0, 2), true).PHP_EOL;
echo "4) ".var_export(substr(true, 0, 1), true).PHP_EOL;
echo "5) ".var_export(substr(false, 0, 1), true).PHP_EOL;
echo "6) ".var_export(substr("", 0, 1), true).PHP_EOL;
echo "7) ".var_export(substr(1.2e3, 0, 4), true).PHP_EOL;
?>
```

Output of the above example in PHP 7:

    1) 'pe'
    2) '54'
    3) 'gr'
    4) '1'
    5) ''
    6) ''
    7) '1200'

Output of the above example in PHP 5:

    1) 'pe'
    2) '54'
    3) 'gr'
    4) '1'
    5) false
    6) false
    7) '1200'

### Errors/Exceptions

Returns **`FALSE`** on error.

``` php
<?php
var_dump(substr('a', 2)); // bool(false)
?>
```

### See Also

-   <span class="function">strrchr</span>
-   <span class="function">substr\_replace</span>
-   <span class="function">preg\_match</span>
-   <span class="function">trim</span>
-   <span class="function">mb\_substr</span>
-   <span class="function">wordwrap</span>
-   <a href="/language/types/string.html#language.types.string.substr" class="link">String access and modification by character</a>

trim
====

Strip whitespace (or other characters) from the beginning and end of a
string

### Description

<span class="type">string</span> <span class="methodname">trim</span> (
<span class="methodparam"><span class="type">string</span> `$str`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$character_mask`<span class="initializer"> = "
\\t\\n\\r\\0\\x0B"</span></span> \] )

This function returns a string with whitespace stripped from the
beginning and end of `str`. Without the second parameter, <span
class="function">trim</span> will strip these characters:

-   <span class="simpara"> " " (ASCII *32* (*0x20*)), an ordinary space.
    </span>
-   <span class="simpara"> "\\t" (ASCII *9* (*0x09*)), a tab. </span>
-   <span class="simpara"> "\\n" (ASCII *10* (*0x0A*)), a new line (line
    feed). </span>
-   <span class="simpara"> "\\r" (ASCII *13* (*0x0D*)), a carriage
    return. </span>
-   <span class="simpara"> "\\0" (ASCII *0* (*0x00*)), the *NUL*-byte.
    </span>
-   <span class="simpara"> "\\x0B" (ASCII *11* (*0x0B*)), a vertical
    tab. </span>

### Parameters

`str`  
The <span class="type">string</span> that will be trimmed.

`character_mask`  
Optionally, the stripped characters can also be specified using the
`character_mask` parameter. Simply list all characters that you want to
be stripped. With *..* you can specify a range of characters.

### Return Values

The trimmed string.

### Examples

**Example \#1 Usage example of <span class="function">trim</span>**

``` php
<?php

$text   = "\t\tThese are a few words :) ...  ";
$binary = "\x09Example string\x0A";
$hello  = "Hello World";
var_dump($text, $binary, $hello);

print "\n";

$trimmed = trim($text);
var_dump($trimmed);

$trimmed = trim($text, " \t.");
var_dump($trimmed);

$trimmed = trim($hello, "Hdle");
var_dump($trimmed);

$trimmed = trim($hello, 'HdWr');
var_dump($trimmed);

// trim the ASCII control characters at the beginning and end of $binary
// (from 0 to 31 inclusive)
$clean = trim($binary, "\x00..\x1F");
var_dump($clean);

?>
```

The above example will output:

    string(32) "        These are a few words :) ...  "
    string(16) "    Example string
    "
    string(11) "Hello World"

    string(28) "These are a few words :) ..."
    string(24) "These are a few words :)"
    string(5) "o Wor"
    string(9) "ello Worl"
    string(14) "Example string"

**Example \#2 Trimming array values with <span
class="function">trim</span>**

``` php
<?php
function trim_value(&$value) 
{ 
    $value = trim($value); 
}

$fruit = array('apple','banana ', ' cranberry ');
var_dump($fruit);

array_walk($fruit, 'trim_value');
var_dump($fruit);

?>
```

The above example will output:

    array(3) {
      [0]=>
      string(5) "apple"
      [1]=>
      string(7) "banana "
      [2]=>
      string(11) " cranberry "
    }
    array(3) {
      [0]=>
      string(5) "apple"
      [1]=>
      string(6) "banana"
      [2]=>
      string(9) "cranberry"
    }

### Notes

> **Note**: **Possible gotcha: removing middle characters**  
>
> Because <span class="function">trim</span> trims characters from the
> beginning and end of a <span class="type">string</span>, it may be
> confusing when characters are (or are not) removed from the middle.
> *trim('abc', 'bad')* removes both 'a' and 'b' because it trims 'a'
> thus moving 'b' to the beginning to also be trimmed. So, this is why
> it "works" whereas *trim('abc', 'b')* seemingly does not.

### See Also

-   <span class="function">ltrim</span>
-   <span class="function">rtrim</span>
-   <span class="function">str\_replace</span>

ucfirst
=======

Make a string's first character uppercase

### Description

<span class="type">string</span> <span class="methodname">ucfirst</span>
( <span class="methodparam"><span class="type">string</span>
`$str`</span> )

Returns a string with the first character of `str` capitalized, if that
character is alphabetic.

Note that 'alphabetic' is determined by the current locale. For
instance, in the default "C" locale characters such as umlaut-a (ä) will
not be converted.

### Parameters

`str`  
The input string.

### Return Values

Returns the resulting string.

### Examples

**Example \#1 <span class="function">ucfirst</span> example**

``` php
<?php
$foo = 'hello world!';
$foo = ucfirst($foo);             // Hello world!

$bar = 'HELLO WORLD!';
$bar = ucfirst($bar);             // HELLO WORLD!
$bar = ucfirst(strtolower($bar)); // Hello world!
?>
```

### See Also

-   <span class="function">lcfirst</span>
-   <span class="function">strtolower</span>
-   <span class="function">strtoupper</span>
-   <span class="function">ucwords</span>

ucwords
=======

Uppercase the first character of each word in a string

### Description

<span class="type">string</span> <span class="methodname">ucwords</span>
( <span class="methodparam"><span class="type">string</span>
`$str`</span> \[, <span class="methodparam"> <span
class="type">string</span> `$delimiters`<span class="initializer"> = "
\\t\\r\\n\\f\\v"</span> </span> \] )

Returns a string with the first character of each word in `str`
capitalized, if that character is alphabetic.

The definition of a word is any string of characters that is immediately
after any character listed in the `delimiters` parameter (By default
these are: space, form-feed, newline, carriage return, horizontal tab,
and vertical tab).

### Parameters

`str`  
The input string.

`delimiters`  
The optional `delimiters` contains the word separator characters.

### Return Values

Returns the modified string.

### Examples

**Example \#1 <span class="function">ucwords</span> example**

``` php
<?php
$foo = 'hello world!';
$foo = ucwords($foo);             // Hello World!

$bar = 'HELLO WORLD!';
$bar = ucwords($bar);             // HELLO WORLD!
$bar = ucwords(strtolower($bar)); // Hello World!
?>
```

**Example \#2 <span class="function">ucwords</span> example with custom
delimiter**

``` php
<?php
$foo = 'hello|world!';
$bar = ucwords($foo);             // Hello|world!

$baz = ucwords($foo, "|");        // Hello|World!
?>
```

**Example \#3 <span class="function">ucwords</span> example with
additional delimiters**

``` php
<?php
$foo = "mike o'hara";
$bar = ucwords($foo);                 // Mike O'hara

$baz = ucwords($foo, " \t\r\n\f\v'"); // Mike O'Hara
?>
```

### Notes

> **Note**: <span class="simpara">This function is locale-aware and will
> handle input according to the currently set locale. However, it only
> works on single-byte character sets. If you need to use multibyte
> characters (most non-western-European languages) look at the
> <a href="/book/mbstring.html" class="link">multibyte</a> or
> <a href="/book/intl.html" class="link">intl</a> extensions
> instead.</span>

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">strtoupper</span>
-   <span class="function">strtolower</span>
-   <span class="function">ucfirst</span>
-   <span class="function">mb\_convert\_case</span>

vfprintf
========

Write a formatted string to a stream

### Description

<span class="type">int</span> <span class="methodname">vfprintf</span> (
<span class="methodparam"><span class="type">resource</span>
`$handle`</span> , <span class="methodparam"><span
class="type">string</span> `$format`</span> , <span
class="methodparam"><span class="type">array</span> `$args`</span> )

Write a string produced according to `format` to the stream resource
specified by `handle`.

Operates as <span class="function">fprintf</span> but accepts an array
of arguments, rather than a variable number of arguments.

### Parameters

`handle`  

`format`  
The format string is composed of zero or more directives: ordinary
characters (excluding *%*) that are copied directly to the result and
*conversion specifications*, each of which results in fetching its own
parameter.

A conversion specification follows this prototype:
*%\[argnum$\]\[flags\]\[width\]\[.precision\]specifier*.

##### Argnum

An integer followed by a dollar sign *$*, to specify which number
argument to treat in the conversion.

| Flag      | Description                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------|
| *-*       | Left-justify within the given field width; Right justification is the default                          |
| *+*       | Prefix positive numbers with a plus sign *+*; Default only negative are prefixed with a negative sign. |
|  (space)  | Pads the result with spaces. This is the default.                                                      |
| *0*       | Only left-pads numbers with zeros. With *s* specifiers this can also right-pad with zeros.             |
| *'*(char) | Pads the result with the character (char).                                                             |

##### Width

An integer that says how many characters (minimum) this conversion
should result in.

##### Precision

A period *.* followed by an integer who's meaning depends on the
specifier:

-   <span class="simpara"> For *e*, *E*, *f* and *F* specifiers: this is
    the number of digits to be printed after the decimal point (by
    default, this is 6). </span>
-   <span class="simpara"> For *g* and *G* specifiers: this is the
    maximum number of significant digits to be printed. </span>
-   <span class="simpara"> For *s* specifier: it acts as a cutoff point,
    setting a maximum character limit to the string. </span>

> **Note**: <span class="simpara"> If the period is specified without an
> explicit value for precision, 0 is assumed. </span>

> **Note**: <span class="simpara"> Attempting to use a position
> specifier greater than **`PHP_INT_MAX`** will generate warnings.
> </span>

<table>
<caption><strong>Specifiers</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>%</em></td>
<td>A literal percent character. No argument is required.</td>
</tr>
<tr class="even">
<td><em>b</em></td>
<td>The argument is treated as an integer and presented as a binary number.</td>
</tr>
<tr class="odd">
<td><em>c</em></td>
<td>The argument is treated as an integer and presented as the character with that ASCII.</td>
</tr>
<tr class="even">
<td><em>d</em></td>
<td>The argument is treated as an integer and presented as a (signed) decimal number.</td>
</tr>
<tr class="odd">
<td><em>e</em></td>
<td>The argument is treated as scientific notation (e.g. 1.2e+2). The precision specifier stands for the number of digits after the decimal point since PHP 5.2.1. In earlier versions, it was taken as number of significant digits (one less).</td>
</tr>
<tr class="even">
<td><em>E</em></td>
<td>Like the <em>e</em> specifier but uses uppercase letter (e.g. 1.2E+2).</td>
</tr>
<tr class="odd">
<td><em>f</em></td>
<td>The argument is treated as a float and presented as a floating-point number (locale aware).</td>
</tr>
<tr class="even">
<td><em>F</em></td>
<td>The argument is treated as a float and presented as a floating-point number (non-locale aware). Available as of PHP 5.0.3.</td>
</tr>
<tr class="odd">
<td><em>g</em></td>
<td><p>General format.</p>
<p>Let P equal the precision if nonzero, 6 if the precision is omitted, or 1 if the precision is zero. Then, if a conversion with style E would have an exponent of X:</p>
<p>If P &gt; X ≥ −4, the conversion is with style f and precision P − (X + 1). Otherwise, the conversion is with style e and precision P − 1.</p></td>
</tr>
<tr class="even">
<td><em>G</em></td>
<td>Like the <em>g</em> specifier but uses <em>E</em> and <em>f</em>.</td>
</tr>
<tr class="odd">
<td><em>o</em></td>
<td>The argument is treated as an integer and presented as an octal number.</td>
</tr>
<tr class="even">
<td><em>s</em></td>
<td>The argument is treated and presented as a string.</td>
</tr>
<tr class="odd">
<td><em>u</em></td>
<td>The argument is treated as an integer and presented as an unsigned decimal number.</td>
</tr>
<tr class="even">
<td><em>x</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with lowercase letters).</td>
</tr>
<tr class="odd">
<td><em>X</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with uppercase letters).</td>
</tr>
</tbody>
</table>

**Warning**
The *c* type specifier ignores padding and width

**Warning**
Attempting to use a combination of the string and width specifiers with
character sets that require more than one byte per character may result
in unexpected results

Variables will be co-erced to a suitable type for the specifier:

| Type      | Specifiers                        |
|-----------|-----------------------------------|
| *string*  | *s*                               |
| *integer* | *d*, *u*, *c*, *o*, *x*, *X*, *b* |
| *double*  | *g*, *G*, *e*, *E*, *f*, *F*      |

`args`  

### Return Values

Returns the length of the outputted string.

### Examples

**Example \#1 <span class="function">vfprintf</span>: zero-padded
integers**

``` php
<?php
if (!($fp = fopen('date.txt', 'w')))
    return;

vfprintf($fp, "%04d-%02d-%02d", array($year, $month, $day));
// will write the formatted ISO date to date.txt
?>
```

### See Also

-   <span class="function">printf</span>
-   <span class="function">sprintf</span>
-   <span class="function">fprintf</span>
-   <span class="function">vprintf</span>
-   <span class="function">vsprintf</span>
-   <span class="function">sscanf</span>
-   <span class="function">fscanf</span>
-   <span class="function">number\_format</span>
-   <span class="function">date</span>

vprintf
=======

Output a formatted string

### Description

<span class="type">int</span> <span class="methodname">vprintf</span> (
<span class="methodparam"><span class="type">string</span>
`$format`</span> , <span class="methodparam"><span
class="type">array</span> `$args`</span> )

Display array values as a formatted string according to `format` (which
is described in the documentation for <span
class="function">sprintf</span>).

Operates as <span class="function">printf</span> but accepts an array of
arguments, rather than a variable number of arguments.

### Parameters

`format`  
The format string is composed of zero or more directives: ordinary
characters (excluding *%*) that are copied directly to the result and
*conversion specifications*, each of which results in fetching its own
parameter.

A conversion specification follows this prototype:
*%\[argnum$\]\[flags\]\[width\]\[.precision\]specifier*.

##### Argnum

An integer followed by a dollar sign *$*, to specify which number
argument to treat in the conversion.

| Flag      | Description                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------|
| *-*       | Left-justify within the given field width; Right justification is the default                          |
| *+*       | Prefix positive numbers with a plus sign *+*; Default only negative are prefixed with a negative sign. |
|  (space)  | Pads the result with spaces. This is the default.                                                      |
| *0*       | Only left-pads numbers with zeros. With *s* specifiers this can also right-pad with zeros.             |
| *'*(char) | Pads the result with the character (char).                                                             |

##### Width

An integer that says how many characters (minimum) this conversion
should result in.

##### Precision

A period *.* followed by an integer who's meaning depends on the
specifier:

-   <span class="simpara"> For *e*, *E*, *f* and *F* specifiers: this is
    the number of digits to be printed after the decimal point (by
    default, this is 6). </span>
-   <span class="simpara"> For *g* and *G* specifiers: this is the
    maximum number of significant digits to be printed. </span>
-   <span class="simpara"> For *s* specifier: it acts as a cutoff point,
    setting a maximum character limit to the string. </span>

> **Note**: <span class="simpara"> If the period is specified without an
> explicit value for precision, 0 is assumed. </span>

> **Note**: <span class="simpara"> Attempting to use a position
> specifier greater than **`PHP_INT_MAX`** will generate warnings.
> </span>

<table>
<caption><strong>Specifiers</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>%</em></td>
<td>A literal percent character. No argument is required.</td>
</tr>
<tr class="even">
<td><em>b</em></td>
<td>The argument is treated as an integer and presented as a binary number.</td>
</tr>
<tr class="odd">
<td><em>c</em></td>
<td>The argument is treated as an integer and presented as the character with that ASCII.</td>
</tr>
<tr class="even">
<td><em>d</em></td>
<td>The argument is treated as an integer and presented as a (signed) decimal number.</td>
</tr>
<tr class="odd">
<td><em>e</em></td>
<td>The argument is treated as scientific notation (e.g. 1.2e+2). The precision specifier stands for the number of digits after the decimal point since PHP 5.2.1. In earlier versions, it was taken as number of significant digits (one less).</td>
</tr>
<tr class="even">
<td><em>E</em></td>
<td>Like the <em>e</em> specifier but uses uppercase letter (e.g. 1.2E+2).</td>
</tr>
<tr class="odd">
<td><em>f</em></td>
<td>The argument is treated as a float and presented as a floating-point number (locale aware).</td>
</tr>
<tr class="even">
<td><em>F</em></td>
<td>The argument is treated as a float and presented as a floating-point number (non-locale aware). Available as of PHP 5.0.3.</td>
</tr>
<tr class="odd">
<td><em>g</em></td>
<td><p>General format.</p>
<p>Let P equal the precision if nonzero, 6 if the precision is omitted, or 1 if the precision is zero. Then, if a conversion with style E would have an exponent of X:</p>
<p>If P &gt; X ≥ −4, the conversion is with style f and precision P − (X + 1). Otherwise, the conversion is with style e and precision P − 1.</p></td>
</tr>
<tr class="even">
<td><em>G</em></td>
<td>Like the <em>g</em> specifier but uses <em>E</em> and <em>f</em>.</td>
</tr>
<tr class="odd">
<td><em>o</em></td>
<td>The argument is treated as an integer and presented as an octal number.</td>
</tr>
<tr class="even">
<td><em>s</em></td>
<td>The argument is treated and presented as a string.</td>
</tr>
<tr class="odd">
<td><em>u</em></td>
<td>The argument is treated as an integer and presented as an unsigned decimal number.</td>
</tr>
<tr class="even">
<td><em>x</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with lowercase letters).</td>
</tr>
<tr class="odd">
<td><em>X</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with uppercase letters).</td>
</tr>
</tbody>
</table>

**Warning**
The *c* type specifier ignores padding and width

**Warning**
Attempting to use a combination of the string and width specifiers with
character sets that require more than one byte per character may result
in unexpected results

Variables will be co-erced to a suitable type for the specifier:

| Type      | Specifiers                        |
|-----------|-----------------------------------|
| *string*  | *s*                               |
| *integer* | *d*, *u*, *c*, *o*, *x*, *X*, *b* |
| *double*  | *g*, *G*, *e*, *E*, *f*, *F*      |

`args`  

### Return Values

Returns the length of the outputted string.

### Examples

**Example \#1 <span class="function">vprintf</span>: zero-padded
integers**

``` php
<?php
vprintf("%04d-%02d-%02d", explode('-', '1988-8-1'));
?>
```

The above example will output:

    1988-08-01

### See Also

-   <span class="function">printf</span>
-   <span class="function">sprintf</span>
-   <span class="function">fprintf</span>
-   <span class="function">vsprintf</span>
-   <span class="function">vfprintf</span>
-   <span class="function">sscanf</span>
-   <span class="function">fscanf</span>
-   <span class="function">number\_format</span>
-   <span class="function">date</span>

vsprintf
========

Return a formatted string

### Description

<span class="type">string</span> <span
class="methodname">vsprintf</span> ( <span class="methodparam"><span
class="type">string</span> `$format`</span> , <span
class="methodparam"><span class="type">array</span> `$args`</span> )

Operates as <span class="function">sprintf</span> but accepts an array
of arguments, rather than a variable number of arguments.

### Parameters

`format`  
The format string is composed of zero or more directives: ordinary
characters (excluding *%*) that are copied directly to the result and
*conversion specifications*, each of which results in fetching its own
parameter.

A conversion specification follows this prototype:
*%\[argnum$\]\[flags\]\[width\]\[.precision\]specifier*.

##### Argnum

An integer followed by a dollar sign *$*, to specify which number
argument to treat in the conversion.

| Flag      | Description                                                                                            |
|-----------|--------------------------------------------------------------------------------------------------------|
| *-*       | Left-justify within the given field width; Right justification is the default                          |
| *+*       | Prefix positive numbers with a plus sign *+*; Default only negative are prefixed with a negative sign. |
|  (space)  | Pads the result with spaces. This is the default.                                                      |
| *0*       | Only left-pads numbers with zeros. With *s* specifiers this can also right-pad with zeros.             |
| *'*(char) | Pads the result with the character (char).                                                             |

##### Width

An integer that says how many characters (minimum) this conversion
should result in.

##### Precision

A period *.* followed by an integer who's meaning depends on the
specifier:

-   <span class="simpara"> For *e*, *E*, *f* and *F* specifiers: this is
    the number of digits to be printed after the decimal point (by
    default, this is 6). </span>
-   <span class="simpara"> For *g* and *G* specifiers: this is the
    maximum number of significant digits to be printed. </span>
-   <span class="simpara"> For *s* specifier: it acts as a cutoff point,
    setting a maximum character limit to the string. </span>

> **Note**: <span class="simpara"> If the period is specified without an
> explicit value for precision, 0 is assumed. </span>

> **Note**: <span class="simpara"> Attempting to use a position
> specifier greater than **`PHP_INT_MAX`** will generate warnings.
> </span>

<table>
<caption><strong>Specifiers</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Specifier</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>%</em></td>
<td>A literal percent character. No argument is required.</td>
</tr>
<tr class="even">
<td><em>b</em></td>
<td>The argument is treated as an integer and presented as a binary number.</td>
</tr>
<tr class="odd">
<td><em>c</em></td>
<td>The argument is treated as an integer and presented as the character with that ASCII.</td>
</tr>
<tr class="even">
<td><em>d</em></td>
<td>The argument is treated as an integer and presented as a (signed) decimal number.</td>
</tr>
<tr class="odd">
<td><em>e</em></td>
<td>The argument is treated as scientific notation (e.g. 1.2e+2). The precision specifier stands for the number of digits after the decimal point since PHP 5.2.1. In earlier versions, it was taken as number of significant digits (one less).</td>
</tr>
<tr class="even">
<td><em>E</em></td>
<td>Like the <em>e</em> specifier but uses uppercase letter (e.g. 1.2E+2).</td>
</tr>
<tr class="odd">
<td><em>f</em></td>
<td>The argument is treated as a float and presented as a floating-point number (locale aware).</td>
</tr>
<tr class="even">
<td><em>F</em></td>
<td>The argument is treated as a float and presented as a floating-point number (non-locale aware). Available as of PHP 5.0.3.</td>
</tr>
<tr class="odd">
<td><em>g</em></td>
<td><p>General format.</p>
<p>Let P equal the precision if nonzero, 6 if the precision is omitted, or 1 if the precision is zero. Then, if a conversion with style E would have an exponent of X:</p>
<p>If P &gt; X ≥ −4, the conversion is with style f and precision P − (X + 1). Otherwise, the conversion is with style e and precision P − 1.</p></td>
</tr>
<tr class="even">
<td><em>G</em></td>
<td>Like the <em>g</em> specifier but uses <em>E</em> and <em>f</em>.</td>
</tr>
<tr class="odd">
<td><em>o</em></td>
<td>The argument is treated as an integer and presented as an octal number.</td>
</tr>
<tr class="even">
<td><em>s</em></td>
<td>The argument is treated and presented as a string.</td>
</tr>
<tr class="odd">
<td><em>u</em></td>
<td>The argument is treated as an integer and presented as an unsigned decimal number.</td>
</tr>
<tr class="even">
<td><em>x</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with lowercase letters).</td>
</tr>
<tr class="odd">
<td><em>X</em></td>
<td>The argument is treated as an integer and presented as a hexadecimal number (with uppercase letters).</td>
</tr>
</tbody>
</table>

**Warning**
The *c* type specifier ignores padding and width

**Warning**
Attempting to use a combination of the string and width specifiers with
character sets that require more than one byte per character may result
in unexpected results

Variables will be co-erced to a suitable type for the specifier:

| Type      | Specifiers                        |
|-----------|-----------------------------------|
| *string*  | *s*                               |
| *integer* | *d*, *u*, *c*, *o*, *x*, *X*, *b* |
| *double*  | *g*, *G*, *e*, *E*, *f*, *F*      |

`args`  

### Return Values

Return array values as a formatted string according to `format`, or
**`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">vsprintf</span>: zero-padded
integers**

``` php
<?php
print vsprintf("%04d-%02d-%02d", explode('-', '1988-8-1'));
?>
```

The above example will output:

    1988-08-01

### See Also

-   <span class="function">printf</span>
-   <span class="function">sprintf</span>
-   <span class="function">fprintf</span>
-   <span class="function">vprintf</span>
-   <span class="function">vfprintf</span>
-   <span class="function">sscanf</span>
-   <span class="function">fscanf</span>
-   <span class="function">number\_format</span>
-   <span class="function">date</span>

wordwrap
========

Wraps a string to a given number of characters

### Description

<span class="type">string</span> <span
class="methodname">wordwrap</span> ( <span class="methodparam"><span
class="type">string</span> `$str`</span> \[, <span
class="methodparam"><span class="type">int</span> `$width`<span
class="initializer"> = 75</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$break`<span
class="initializer"> = "\\n"</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$cut`<span
class="initializer"> = **`FALSE`**</span></span> \]\]\] )

Wraps a string to a given number of characters using a string break
character.

### Parameters

`str`  
The input string.

`width`  
The number of characters at which the string will be wrapped.

`break`  
The line is broken using the optional `break` parameter.

`cut`  
If the `cut` is set to **`TRUE`**, the string is always wrapped at or
before the specified `width`. So if you have a word that is larger than
the given width, it is broken apart. (See second example). When
**`FALSE`** the function does not split the word even if the `width` is
smaller than the word width.

### Return Values

Returns the given string wrapped at the specified length.

### Examples

**Example \#1 <span class="function">wordwrap</span> example**

``` php
<?php
$text = "The quick brown fox jumped over the lazy dog.";
$newtext = wordwrap($text, 20, "<br />\n");

echo $newtext;
?>
```

The above example will output:

    The quick brown fox<br />
    jumped over the lazy<br />
    dog.

**Example \#2 <span class="function">wordwrap</span> example**

``` php
<?php
$text = "A very long woooooooooooord.";
$newtext = wordwrap($text, 8, "\n", true);

echo "$newtext\n";
?>
```

The above example will output:

    A very
    long
    wooooooo
    ooooord.

**Example \#3 <span class="function">wordwrap</span> example**

``` php
<?php
$text = "A very long woooooooooooooooooord. and something";
$newtext = wordwrap($text, 8, "\n", false);

echo "$newtext\n";
?>
```

The above example will output:

    A very
    long
    woooooooooooooooooord.
    and
    something

### See Also

-   <span class="function">nl2br</span>
-   <span class="function">chunk\_split</span>

**Table of Contents**

-   [addcslashes](/ref/strings.html#addcslashes) — Quote string with
    slashes in a C style
-   [addslashes](/ref/strings.html#addslashes) — Quote string with
    slashes
-   [bin2hex](/ref/strings.html#bin2hex) — Convert binary data into
    hexadecimal representation
-   [chop](/ref/strings.html#chop) — Alias of rtrim
-   [chr](/ref/strings.html#chr) — Generate a single-byte string from a
    number
-   [chunk\_split](/ref/strings.html#chunk_split) — Split a string into
    smaller chunks
-   [convert\_cyr\_string](/ref/strings.html#convert_cyr_string) —
    Convert from one Cyrillic character set to another
-   [convert\_uudecode](/ref/strings.html#convert_uudecode) — Decode a
    uuencoded string
-   [convert\_uuencode](/ref/strings.html#convert_uuencode) — Uuencode a
    string
-   [count\_chars](/ref/strings.html#count_chars) — Return information
    about characters used in a string
-   [crc32](/ref/strings.html#crc32) — Calculates the crc32 polynomial
    of a string
-   [crypt](/ref/strings.html#crypt) — One-way string hashing
-   [echo](/ref/strings.html#echo) — Output one or more strings
-   [explode](/ref/strings.html#explode) — Split a string by a string
-   [fprintf](/ref/strings.html#fprintf) — Write a formatted string to a
    stream
-   [get\_html\_translation\_table](/ref/strings.html#get_html_translation_table)
    — Returns the translation table used by htmlspecialchars and
    htmlentities
-   [hebrev](/ref/strings.html#hebrev) — Convert logical Hebrew text to
    visual text
-   [hebrevc](/ref/strings.html#hebrevc) — Convert logical Hebrew text
    to visual text with newline conversion
-   [hex2bin](/ref/strings.html#hex2bin) — Decodes a hexadecimally
    encoded binary string
-   [html\_entity\_decode](/ref/strings.html#html_entity_decode) —
    Convert HTML entities to their corresponding characters
-   [htmlentities](/ref/strings.html#htmlentities) — Convert all
    applicable characters to HTML entities
-   [htmlspecialchars\_decode](/ref/strings.html#htmlspecialchars_decode)
    — Convert special HTML entities back to characters
-   [htmlspecialchars](/ref/strings.html#htmlspecialchars) — Convert
    special characters to HTML entities
-   [implode](/ref/strings.html#implode) — Join array elements with a
    string
-   [join](/ref/strings.html#join) — Alias of implode
-   [lcfirst](/ref/strings.html#lcfirst) — Make a string's first
    character lowercase
-   [levenshtein](/ref/strings.html#levenshtein) — Calculate Levenshtein
    distance between two strings
-   [localeconv](/ref/strings.html#localeconv) — Get numeric formatting
    information
-   [ltrim](/ref/strings.html#ltrim) — Strip whitespace (or other
    characters) from the beginning of a string
-   [md5\_file](/ref/strings.html#md5_file) — Calculates the md5 hash of
    a given file
-   [md5](/ref/strings.html#md5) — Calculate the md5 hash of a string
-   [metaphone](/ref/strings.html#metaphone) — Calculate the metaphone
    key of a string
-   [money\_format](/ref/strings.html#money_format) — Formats a number
    as a currency string
-   [nl\_langinfo](/ref/strings.html#nl_langinfo) — Query language and
    locale information
-   [nl2br](/ref/strings.html#nl2br) — Inserts HTML line breaks before
    all newlines in a string
-   [number\_format](/ref/strings.html#number_format) — Format a number
    with grouped thousands
-   [ord](/ref/strings.html#ord) — Convert the first byte of a string to
    a value between 0 and 255
-   [parse\_str](/ref/strings.html#parse_str) — Parses the string into
    variables
-   [print](/ref/strings.html#print) — Output a string
-   [printf](/ref/strings.html#printf) — Output a formatted string
-   [quoted\_printable\_decode](/ref/strings.html#quoted_printable_decode)
    — Convert a quoted-printable string to an 8 bit string
-   [quoted\_printable\_encode](/ref/strings.html#quoted_printable_encode)
    — Convert a 8 bit string to a quoted-printable string
-   [quotemeta](/ref/strings.html#quotemeta) — Quote meta characters
-   [rtrim](/ref/strings.html#rtrim) — Strip whitespace (or other
    characters) from the end of a string
-   [setlocale](/ref/strings.html#setlocale) — Set locale information
-   [sha1\_file](/ref/strings.html#sha1_file) — Calculate the sha1 hash
    of a file
-   [sha1](/ref/strings.html#sha1) — Calculate the sha1 hash of a string
-   [similar\_text](/ref/strings.html#similar_text) — Calculate the
    similarity between two strings
-   [soundex](/ref/strings.html#soundex) — Calculate the soundex key of
    a string
-   [sprintf](/ref/strings.html#sprintf) — Return a formatted string
-   [sscanf](/ref/strings.html#sscanf) — Parses input from a string
    according to a format
-   [str\_getcsv](/ref/strings.html#str_getcsv) — Parse a CSV string
    into an array
-   [str\_ireplace](/ref/strings.html#str_ireplace) — Case-insensitive
    version of str\_replace
-   [str\_pad](/ref/strings.html#str_pad) — Pad a string to a certain
    length with another string
-   [str\_repeat](/ref/strings.html#str_repeat) — Repeat a string
-   [str\_replace](/ref/strings.html#str_replace) — Replace all
    occurrences of the search string with the replacement string
-   [str\_rot13](/ref/strings.html#str_rot13) — Perform the rot13
    transform on a string
-   [str\_shuffle](/ref/strings.html#str_shuffle) — Randomly shuffles a
    string
-   [str\_split](/ref/strings.html#str_split) — Convert a string to an
    array
-   [str\_word\_count](/ref/strings.html#str_word_count) — Return
    information about words used in a string
-   [strcasecmp](/ref/strings.html#strcasecmp) — Binary safe
    case-insensitive string comparison
-   [strchr](/ref/strings.html#strchr) — Alias of strstr
-   [strcmp](/ref/strings.html#strcmp) — Binary safe string comparison
-   [strcoll](/ref/strings.html#strcoll) — Locale based string
    comparison
-   [strcspn](/ref/strings.html#strcspn) — Find length of initial
    segment not matching mask
-   [strip\_tags](/ref/strings.html#strip_tags) — Strip HTML and PHP
    tags from a string
-   [stripcslashes](/ref/strings.html#stripcslashes) — Un-quote string
    quoted with addcslashes
-   [stripos](/ref/strings.html#stripos) — Find the position of the
    first occurrence of a case-insensitive substring in a string
-   [stripslashes](/ref/strings.html#stripslashes) — Un-quotes a quoted
    string
-   [stristr](/ref/strings.html#stristr) — Case-insensitive strstr
-   [strlen](/ref/strings.html#strlen) — Get string length
-   [strnatcasecmp](/ref/strings.html#strnatcasecmp) — Case insensitive
    string comparisons using a "natural order" algorithm
-   [strnatcmp](/ref/strings.html#strnatcmp) — String comparisons using
    a "natural order" algorithm
-   [strncasecmp](/ref/strings.html#strncasecmp) — Binary safe
    case-insensitive string comparison of the first n characters
-   [strncmp](/ref/strings.html#strncmp) — Binary safe string comparison
    of the first n characters
-   [strpbrk](/ref/strings.html#strpbrk) — Search a string for any of a
    set of characters
-   [strpos](/ref/strings.html#strpos) — Find the position of the first
    occurrence of a substring in a string
-   [strrchr](/ref/strings.html#strrchr) — Find the last occurrence of a
    character in a string
-   [strrev](/ref/strings.html#strrev) — Reverse a string
-   [strripos](/ref/strings.html#strripos) — Find the position of the
    last occurrence of a case-insensitive substring in a string
-   [strrpos](/ref/strings.html#strrpos) — Find the position of the last
    occurrence of a substring in a string
-   [strspn](/ref/strings.html#strspn) — Finds the length of the initial
    segment of a string consisting entirely of characters contained
    within a given mask
-   [strstr](/ref/strings.html#strstr) — Find the first occurrence of a
    string
-   [strtok](/ref/strings.html#strtok) — Tokenize string
-   [strtolower](/ref/strings.html#strtolower) — Make a string lowercase
-   [strtoupper](/ref/strings.html#strtoupper) — Make a string uppercase
-   [strtr](/ref/strings.html#strtr) — Translate characters or replace
    substrings
-   [substr\_compare](/ref/strings.html#substr_compare) — Binary safe
    comparison of two strings from an offset, up to length characters
-   [substr\_count](/ref/strings.html#substr_count) — Count the number
    of substring occurrences
-   [substr\_replace](/ref/strings.html#substr_replace) — Replace text
    within a portion of a string
-   [substr](/ref/strings.html#substr) — Return part of a string
-   [trim](/ref/strings.html#trim) — Strip whitespace (or other
    characters) from the beginning and end of a string
-   [ucfirst](/ref/strings.html#ucfirst) — Make a string's first
    character uppercase
-   [ucwords](/ref/strings.html#ucwords) — Uppercase the first character
    of each word in a string
-   [vfprintf](/ref/strings.html#vfprintf) — Write a formatted string to
    a stream
-   [vprintf](/ref/strings.html#vprintf) — Output a formatted string
-   [vsprintf](/ref/strings.html#vsprintf) — Return a formatted string
-   [wordwrap](/ref/strings.html#wordwrap) — Wraps a string to a given
    number of characters

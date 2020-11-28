hash\_algos
===========

Return a list of registered hashing algorithms

### Description

<span class="type">array</span> <span
class="methodname">hash\_algos</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns a numerically indexed array containing the list of supported
hashing algorithms.

### Changelog

| Version | Description                                                                                   |
|---------|-----------------------------------------------------------------------------------------------|
| 7.4.0   | Support for crc32c has been added.                                                            |
| 7.1.0   | Support for sha512/224, sha512/256, sha3-224, sha3-256, sha3-384 and sha3-512 has been added. |

### Examples

**Example \#1 <span class="function">hash\_algos</span> example**

As of PHP 7.4.0, <span class="function">hash\_algos</span> will return
the following list of algorithm names.

``` php
<?php
print_r(hash_algos());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => md2
        [1] => md4
        [2] => md5
        [3] => sha1
        [4] => sha224
        [5] => sha256
        [6] => sha384
        [7] => sha512/224
        [8] => sha512/256
        [9] => sha512
        [10] => sha3-224
        [11] => sha3-256
        [12] => sha3-384
        [13] => sha3-512
        [14] => ripemd128
        [15] => ripemd160
        [16] => ripemd256
        [17] => ripemd320
        [18] => whirlpool
        [19] => tiger128,3
        [20] => tiger160,3
        [21] => tiger192,3
        [22] => tiger128,4
        [23] => tiger160,4
        [24] => tiger192,4
        [25] => snefru
        [26] => snefru256
        [27] => gost
        [28] => gost-crypto
        [29] => adler32
        [30] => crc32
        [31] => crc32b
        [32] => crc32c
        [33] => fnv132
        [34] => fnv1a32
        [35] => fnv164
        [36] => fnv1a64
        [37] => joaat
        [38] => haval128,3
        [39] => haval160,3
        [40] => haval192,3
        [41] => haval224,3
        [42] => haval256,3
        [43] => haval128,4
        [44] => haval160,4
        [45] => haval192,4
        [46] => haval224,4
        [47] => haval256,4
        [48] => haval128,5
        [49] => haval160,5
        [50] => haval192,5
        [51] => haval224,5
        [52] => haval256,5
    )

### See Also

-   <span class="function">hash\_hmac\_algos</span>

hash\_copy
==========

Copy hashing context

### Description

<span class="type">HashContext</span> <span
class="methodname">hash\_copy</span> ( <span class="methodparam"><span
class="type">HashContext</span> `$context`</span> )

### Parameters

`context`  
Hashing context returned by <span class="function">hash\_init</span>.

### Return Values

Returns a copy of Hashing Context.

### Changelog

| Version | Description                                                                       |
|---------|-----------------------------------------------------------------------------------|
| 7.2.0   | Accept and return <span class="classname">HashContext</span> instead of resource. |

### Examples

**Example \#1 <span class="function">hash\_copy</span> example**

``` php
<?php
$context = hash_init("md5");
hash_update($context, "data");

/* copy context to be able to continue using it */
$copy_context = hash_copy($context);

echo hash_final($context), "\n";

hash_update($copy_context, "data");
echo hash_final($copy_context), "\n";
?>
```

The above example will output:

    8d777f385d3dfec8815d20f7496026dc
    511ae0b1c13f95e5f08f1a0dd3da3d93

hash\_equals
============

Timing attack safe string comparison

### Description

<span class="type">bool</span> <span
class="methodname">hash\_equals</span> ( <span class="methodparam"><span
class="type">string</span> `$known_string`</span> , <span
class="methodparam"><span class="type">string</span>
`$user_string`</span> )

Compares two strings using the same time whether they're equal or not.

This function should be used to mitigate timing attacks; for instance,
when testing <span class="function">crypt</span> password hashes.

### Parameters

`known_string`  
The <span class="type">string</span> of known length to compare against

`user_string`  
The user-supplied string

### Return Values

Returns **`TRUE`** when the two strings are equal, **`FALSE`**
otherwise.

### Errors/Exceptions

Emits an **`E_WARNING`** message when either of the supplied parameters
is not a string.

### Examples

**Example \#1 <span class="function">hash\_equals</span> example**

``` php
<?php
$expected  = crypt('12345', '$2a$07$usesomesillystringforsalt$');
$correct   = crypt('12345', '$2a$07$usesomesillystringforsalt$');
$incorrect = crypt('apple', '$2a$07$usesomesillystringforsalt$');

var_dump(hash_equals($expected, $correct));
var_dump(hash_equals($expected, $incorrect));
?>
```

The above example will output:

    bool(true)
    bool(false)

### Notes

> **Note**:
>
> Both arguments must be of the same length to be compared successfully.
> When arguments of differing length are supplied, **`FALSE`** is
> returned immediately and the length of the known string may be leaked
> in case of a timing attack.

> **Note**:
>
> It is important to provide the user-supplied string as the second
> parameter, rather than the first.

hash\_file
==========

Generate a hash value using the contents of a given file

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">hash\_file</span> ( <span class="methodparam"><span
class="type">string</span> `$algo`</span> , <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$binary`<span class="initializer"> = **`FALSE`**</span></span> \] )

### Parameters

`algo`  
Name of selected hashing algorithm (i.e. "md5", "sha256", "haval160,4",
etc..). For a list of supported algorithms see <span
class="function">hash\_algos</span>.

`filename`  
URL describing location of file to be hashed; Supports fopen wrappers.

`binary`  
When set to **`TRUE`**, outputs raw binary data. **`FALSE`** outputs
lowercase hexits.

### Return Values

Returns a string containing the calculated message digest as lowercase
hexits unless `binary` is set to true in which case the raw binary
representation of the message digest is returned.

### Examples

**Example \#1 Using <span class="function">hash\_file</span>**

``` php
<?php
/* Create a file to calculate hash of */
file_put_contents('example.txt', 'The quick brown fox jumped over the lazy dog.');

echo hash_file('md5', 'example.txt');
?>
```

The above example will output:

    5c6ffbdd40d9556b73a21e63c3e0e904

### See Also

-   <span class="function">hash</span>
-   <span class="function">hash\_hmac\_file</span>
-   <span class="function">hash\_update\_file</span>
-   <span class="function">md5\_file</span>
-   <span class="function">sha1\_file</span>

hash\_final
===========

Finalize an incremental hash and return resulting digest

### Description

<span class="type">string</span> <span
class="methodname">hash\_final</span> ( <span class="methodparam"><span
class="type">HashContext</span> `$context`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$binary`<span
class="initializer"> = **`FALSE`**</span></span> \] )

### Parameters

`context`  
Hashing context returned by <span class="function">hash\_init</span>.

`binary`  
When set to **`TRUE`**, outputs raw binary data. **`FALSE`** outputs
lowercase hexits.

### Return Values

Returns a string containing the calculated message digest as lowercase
hexits unless `binary` is set to true in which case the raw binary
representation of the message digest is returned.

### Changelog

| Version | Description                                                            |
|---------|------------------------------------------------------------------------|
| 7.2.0   | Accept <span class="classname">HashContext</span> instead of resource. |

### Examples

**Example \#1 <span class="function">hash\_final</span> example**

``` php
<?php
$ctx = hash_init('sha1');
hash_update($ctx, 'The quick brown fox jumped over the lazy dog.');
echo hash_final($ctx);
?>
```

The above example will output:

    c0854fb9fb03c41cce3802cb0d220529e6eef94e

### See Also

-   <span class="function">hash\_init</span>
-   <span class="function">hash\_update</span>
-   <span class="function">hash\_update\_stream</span>
-   <span class="function">hash\_update\_file</span>

hash\_hkdf
==========

Generate a HKDF key derivation of a supplied key input

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">hash\_hkdf</span> ( <span class="methodparam"><span
class="type">string</span> `$algo`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> \[,
<span class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$info`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$salt`<span
class="initializer"> = ""</span></span> \]\]\] )

### Parameters

`algo`  
Name of selected hashing algorithm (i.e. "sha256", "sha512",
"haval160,4", etc..) See <span class="function">hash\_algos</span> for a
list of supported algorithms.

> **Note**:
>
> Non-cryptographic hash functions are not allowed.

`key`  
Input keying material (raw binary). Cannot be empty.

`length`  
Desired output length in bytes. Cannot be greater than 255 times the
chosen hash function size.

If `length` is *0*, the output length will default to the chosen hash
function size.

`info`  
Application/context-specific info string.

`salt`  
Salt to use during derivation.

While optional, adding random salt significantly improves the strength
of HKDF.

### Return Values

Returns a string containing a raw binary representation of the derived
key (also known as output keying material - OKM); or **`FALSE`** on
failure.

### Errors/Exceptions

An **`E_WARNING`** will be raised if `key` is empty, `algo` is
unknown/non-cryptographic, `length` is less than *0* or too large
(greater than 255 times the size of the hash function).

### Examples

**Example \#1 <span class="function">hash\_hkdf</span> example**

``` php
<?php
// Generate a random key, and salt to strengthen it during derivation.
$inputKey = random_bytes(32);
$salt = random_bytes(16);

// Derive a pair of separate keys, using the same input created above.
$encryptionKey = hash_hkdf('sha256', $inputKey, 32, 'aes-256-encryption', $salt);
$authenticationKey = hash_hkdf('sha256', $inputKey, 32, 'sha-256-authentication', $salt);

var_dump($encryptionKey !== $authenticationKey); // bool(true)
?>
```

The above example produces a pair of separate keys, suitable for
creation of an encrypt-then-HMAC construct, using AES-256 and SHA-256
for encryption and authentication respectively.

### See Also

-   <span class="function">hash\_pbkdf2</span>
-   <a href="http://www.faqs.org/rfcs/rfc5869" class="link external">» RFC 5869</a>
-   <a href="https://github.com/narfbg/hash_hkdf_compat" class="link external">» userland implementation</a>

hash\_hmac\_algos
=================

Return a list of registered hashing algorithms suitable for hash\_hmac

### Description

<span class="type">array</span> <span
class="methodname">hash\_hmac\_algos</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns a numerically indexed array containing the list of supported
hashing algorithms suitable for <span
class="function">hash\_hmac</span>.

### Examples

**Example \#1 <span class="function">hash\_hmac\_algos</span> example**

``` php
<?php
print_r(hash_hmac_algos());
```

The above example will output something similar to:

    Array
    (
        [0] => md2
        [1] => md4
        [2] => md5
        [3] => sha1
        [4] => sha224
        [5] => sha256
        [6] => sha384
        [7] => sha512/224
        [8] => sha512/256
        [9] => sha512
        [10] => sha3-224
        [11] => sha3-256
        [12] => sha3-384
        [13] => sha3-512
        [14] => ripemd128
        [15] => ripemd160
        [16] => ripemd256
        [17] => ripemd320
        [18] => whirlpool
        [19] => tiger128,3
        [20] => tiger160,3
        [21] => tiger192,3
        [22] => tiger128,4
        [23] => tiger160,4
        [24] => tiger192,4
        [25] => snefru
        [26] => snefru256
        [27] => gost
        [28] => gost-crypto
        [29] => haval128,3
        [30] => haval160,3
        [31] => haval192,3
        [32] => haval224,3
        [33] => haval256,3
        [34] => haval128,4
        [35] => haval160,4
        [36] => haval192,4
        [37] => haval224,4
        [38] => haval256,4
        [39] => haval128,5
        [40] => haval160,5
        [41] => haval192,5
        [42] => haval224,5
        [43] => haval256,5
    )

### Notes

> **Note**:
>
> Before PHP 7.2.0 the only means to get a list of supported hash
> algorithms has been to call <span class="function">hash\_algos</span>
> which also returns hash algorithms that are not suitable for <span
> class="function">hash\_hmac</span>.

### See Also

-   <span class="function">hash\_hmac</span>
-   <span class="function">hash\_algos</span>

hash\_hmac\_file
================

Generate a keyed hash value using the HMAC method and the contents of a
given file

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">hash\_hmac\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$algo`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$binary`<span
class="initializer"> = **`FALSE`**</span></span> \] )

### Parameters

`algo`  
Name of selected hashing algorithm (i.e. "md5", "sha256", "haval160,4",
etc..) See <span class="function">hash\_hmac\_algos</span> for a list of
supported algorithms.

`data`  
URL describing location of file to be hashed; Supports fopen wrappers.

`key`  
Shared secret key used for generating the HMAC variant of the message
digest.

`binary`  
When set to **`TRUE`**, outputs raw binary data. **`FALSE`** outputs
lowercase hexits.

### Return Values

Returns a string containing the calculated message digest as lowercase
hexits unless `binary` is set to true in which case the raw binary
representation of the message digest is returned. Returns **`FALSE`**
when `algo` is unknown or is a non-cryptographic hash function, or if
the file `data` cannot be read.

### Changelog

| Version | Description                                                                                                               |
|---------|---------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) was disabled. |

### Examples

**Example \#1 <span class="function">hash\_hmac\_file</span> example**

``` php
<?php
/* Create a file to calculate hash of */
file_put_contents('example.txt', 'The quick brown fox jumped over the lazy dog.');

echo hash_hmac_file('md5', 'example.txt', 'secret');
?>
```

The above example will output:

    7eb2b5c37443418fc77c136dd20e859c

### See Also

-   <span class="function">hash\_hmac\_algos</span>
-   <span class="function">hash\_hmac</span>
-   <span class="function">hash\_file</span>

hash\_hmac
==========

Generate a keyed hash value using the HMAC method

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">hash\_hmac</span> ( <span class="methodparam"><span
class="type">string</span> `$algo`</span> , <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span> `$key`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$binary`<span class="initializer"> = **`FALSE`**</span></span> \] )

### Parameters

`algo`  
Name of selected hashing algorithm (i.e. "md5", "sha256", "haval160,4",
etc..) See <span class="function">hash\_hmac\_algos</span> for a list of
supported algorithms.

`data`  
Message to be hashed.

`key`  
Shared secret key used for generating the HMAC variant of the message
digest.

`binary`  
When set to **`TRUE`**, outputs raw binary data. **`FALSE`** outputs
lowercase hexits.

### Return Values

Returns a string containing the calculated message digest as lowercase
hexits unless `binary` is set to true in which case the raw binary
representation of the message digest is returned. Returns **`FALSE`**
when `algo` is unknown or is a non-cryptographic hash function.

### Changelog

| Version | Description                                                                                                               |
|---------|---------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) was disabled. |

### Examples

**Example \#1 <span class="function">hash\_hmac</span> example**

``` php
<?php
echo hash_hmac('ripemd160', 'The quick brown fox jumped over the lazy dog.', 'secret');
?>
```

The above example will output:

    b8e7ae12510bdfb1812e463a7f086122cf37e4f7

### See Also

-   <span class="function">hash</span>
-   <span class="function">hash\_hmac\_algos</span>
-   <span class="function">hash\_init</span>
-   <span class="function">hash\_hmac\_file</span>

hash\_init
==========

Initialize an incremental hashing context

### Description

<span class="type">HashContext</span> <span
class="methodname">hash\_init</span> ( <span class="methodparam"><span
class="type">string</span> `$algo`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$key`<span
class="initializer"> = ""</span></span> \]\] )

### Parameters

`algo`  
Name of selected hashing algorithm (i.e. "md5", "sha256", "haval160,4",
etc..). For a list of supported algorithms see <span
class="function">hash\_algos</span>.

`flags`  
Optional settings for hash generation, currently supports only one
option: **`HASH_HMAC`**. When specified, the `key` *must* be specified.

`key`  
When **`HASH_HMAC`** is specified for `flags`, a shared secret key to be
used with the HMAC hashing method must be supplied in this parameter.

### Return Values

Returns a Hashing Context for use with <span
class="function">hash\_update</span>, <span
class="function">hash\_update\_stream</span>, <span
class="function">hash\_update\_file</span>, and <span
class="function">hash\_final</span>.

### Changelog

| Version | Description                                                                                                                                    |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) with **`HASH_HMAC`** was disabled. |
| 7.2.0   | Return <span class="classname">HashContext</span> instead of resource.                                                                         |

### Examples

**Example \#1 Incremental hashing example**

``` php
<?php
$ctx = hash_init('md5');
hash_update($ctx, 'The quick brown fox ');
hash_update($ctx, 'jumped over the lazy dog.');
echo hash_final($ctx);
?>
```

The above example will output:

    5c6ffbdd40d9556b73a21e63c3e0e904

### See Also

-   <span class="function">hash</span>
-   <span class="function">hash\_algos</span>
-   <span class="function">hash\_file</span>
-   <span class="function">hash\_hmac</span>
-   <span class="function">hash\_hmac\_file</span>

hash\_pbkdf2
============

Generate a PBKDF2 key derivation of a supplied password

### Description

<span class="type">string</span> <span
class="methodname">hash\_pbkdf2</span> ( <span class="methodparam"><span
class="type">string</span> `$algo`</span> , <span
class="methodparam"><span class="type">string</span> `$password`</span>
, <span class="methodparam"><span class="type">string</span>
`$salt`</span> , <span class="methodparam"><span class="type">int</span>
`$iterations`</span> \[, <span class="methodparam"><span
class="type">int</span> `$length`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$binary`<span class="initializer"> =
**`FALSE`**</span></span> \]\] )

### Parameters

`algo`  
Name of selected hashing algorithm (i.e. *md5*, *sha256*, *haval160,4*,
etc..) See <span class="function">hash\_algos</span> for a list of
supported algorithms.

`password`  
The password to use for the derivation.

`salt`  
The salt to use for the derivation. This value should be generated
randomly.

`iterations`  
The number of internal iterations to perform for the derivation.

`length`  
The length of the output string. If `binary` is **`TRUE`** this
corresponds to the byte-length of the derived key, if `binary` is
**`FALSE`** this corresponds to twice the byte-length of the derived key
(as every byte of the key is returned as two hexits).

If *0* is passed, the entire output of the supplied algorithm is used.

`binary`  
When set to **`TRUE`**, outputs raw binary data. **`FALSE`** outputs
lowercase hexits.

### Return Values

Returns a string containing the derived key as lowercase hexits unless
`binary` is set to **`TRUE`** in which case the raw binary
representation of the derived key is returned.

### Errors/Exceptions

An **`E_WARNING`** will be raised if the algorithm is unknown, the
`iterations` parameter is less than or equal to *0*, the `length` is
less than *0* or the `salt` is too long (greater than **`INT_MAX`** *-
4*).

### Changelog

| Version | Description                                                                                                               |
|---------|---------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | Usage of non-cryptographic hash functions (adler32, crc32, crc32b, fnv132, fnv1a32, fnv164, fnv1a64, joaat) was disabled. |

### Examples

**Example \#1 <span class="function">hash\_pbkdf2</span> example, basic
usage**

``` php
<?php
$password = "password";
$iterations = 1000;

// Generate a random IV using openssl_random_pseudo_bytes()
// random_bytes() or another suitable source of randomness
$salt = openssl_random_pseudo_bytes(16);

$hash = hash_pbkdf2("sha256", $password, $salt, $iterations, 20);
echo $hash;
?>
```

The above example will output something similar to:

    120fb6cffcf8b32c43e7

### Notes

**Caution**

The PBKDF2 method can be used for hashing passwords for storage.
However, it should be noted that <span
class="function">password\_hash</span> or <span
class="function">crypt</span> with **`CRYPT_BLOWFISH`** are better
suited for password storage.

### See Also

-   <span class="function">crypt</span>
-   <span class="function">password\_hash</span>
-   <span class="function">hash</span>
-   <span class="function">hash\_algos</span>
-   <span class="function">hash\_init</span>
-   <span class="function">hash\_hmac</span>
-   <span class="function">hash\_hmac\_file</span>
-   <span class="function">openssl\_pbkdf2</span>

hash\_update\_file
==================

Pump data into an active hashing context from a file

### Description

<span class="type">bool</span> <span
class="methodname">hash\_update\_file</span> ( <span
class="methodparam"><span class="type">HashContext</span>
`$context`</span> , <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">resource</span><span class="type">null</span></span>
`$stream_context`<span class="initializer"> = **`NULL`**</span></span>
\] )

### Parameters

`context`  
Hashing context returned by <span class="function">hash\_init</span>.

`filename`  
URL describing location of file to be hashed; Supports fopen wrappers.

`stream_context`  
Stream context as returned by <span
class="function">stream\_context\_create</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                            |
|---------|------------------------------------------------------------------------|
| 8.0.0   | `stream_context` is now nullable.                                      |
| 7.2.0   | Accept <span class="classname">HashContext</span> instead of resource. |

### See Also

-   <span class="function">hash\_init</span>
-   <span class="function">hash\_update</span>
-   <span class="function">hash\_update\_stream</span>
-   <span class="function">hash\_final</span>
-   <span class="function">hash</span>
-   <span class="function">hash\_file</span>

hash\_update\_stream
====================

Pump data into an active hashing context from an open stream

### Description

<span class="type">int</span> <span
class="methodname">hash\_update\_stream</span> ( <span
class="methodparam"><span class="type">HashContext</span>
`$context`</span> , <span class="methodparam"><span
class="type">resource</span> `$stream`</span> \[, <span
class="methodparam"><span class="type">int</span> `$length`<span
class="initializer"> = -1</span></span> \] )

### Parameters

`context`  
Hashing context returned by <span class="function">hash\_init</span>.

`stream`  
Open file handle as returned by any stream creation function.

`length`  
Maximum number of characters to copy from `stream` into the hashing
context.

### Return Values

Actual number of bytes added to the hashing context from `stream`.

### Changelog

| Version | Description                                                            |
|---------|------------------------------------------------------------------------|
| 7.2.0   | Accept <span class="classname">HashContext</span> instead of resource. |

### Examples

**Example \#1 <span class="function">hash\_update\_stream</span>
example**

``` php
<?php
$fp = tmpfile();
fwrite($fp, 'The quick brown fox jumped over the lazy dog.');
rewind($fp);

$ctx = hash_init('md5');
hash_update_stream($ctx, $fp);
echo hash_final($ctx);
?>
```

The above example will output:

    5c6ffbdd40d9556b73a21e63c3e0e904

### See Also

-   <span class="function">hash\_init</span>
-   <span class="function">hash\_update</span>
-   <span class="function">hash\_final</span>
-   <span class="function">hash</span>
-   <span class="function">hash\_file</span>

hash\_update
============

Pump data into an active hashing context

### Description

<span class="type">bool</span> <span
class="methodname">hash\_update</span> ( <span class="methodparam"><span
class="type">HashContext</span> `$context`</span> , <span
class="methodparam"><span class="type">string</span> `$data`</span> )

### Parameters

`context`  
Hashing context returned by <span class="function">hash\_init</span>.

`data`  
Message to be included in the hash digest.

### Return Values

Returns **`TRUE`**.

### Changelog

| Version | Description                                                            |
|---------|------------------------------------------------------------------------|
| 7.2.0   | Accept <span class="classname">HashContext</span> instead of resource. |

### See Also

-   <span class="function">hash\_init</span>
-   <span class="function">hash\_update\_file</span>
-   <span class="function">hash\_update\_stream</span>
-   <span class="function">hash\_final</span>

hash
====

Generate a hash value (message digest)

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span class="methodname">hash</span> (
<span class="methodparam"><span class="type">string</span>
`$algo`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$binary`<span
class="initializer"> = **`FALSE`**</span></span> \] )

### Parameters

`algo`  
Name of selected hashing algorithm (i.e. "md5", "sha256", "haval160,4",
etc..). For a list of supported algorithms see <span
class="function">hash\_algos</span>.

`data`  
Message to be hashed.

`binary`  
When set to **`TRUE`**, outputs raw binary data. **`FALSE`** outputs
lowercase hexits.

### Return Values

Returns a string containing the calculated message digest as lowercase
hexits unless `binary` is set to true in which case the raw binary
representation of the message digest is returned.

### Examples

**Example \#1 A <span class="function">hash</span> example**

``` php
<?php
echo hash('ripemd160', 'The quick brown fox jumped over the lazy dog.');
?>
```

The above example will output:

    ec457d0a974c48d5685a7efa03d137dc8bbde7e3

**Example \#2 Calculate pre PHP-5.4 tiger hashes with PHP-5.4 and
higher**

``` php
<?php
function old_tiger($data = "", $width=192, $rounds = 3) {
    return substr(
        implode(
            array_map(
                function ($h) {
                    return str_pad(bin2hex(strrev($h)), 16, "0");
                },
                str_split(hash("tiger192,$rounds", $data, true), 8)
            )
        ),
        0, 48-(192-$width)/4
    );
}
echo hash('tiger192,3', 'a-string'), PHP_EOL;
echo old_tiger('a-string'), PHP_EOL;
?>
```

Output of the above example in PHP 5.3:

    146a7492719b3564094efe7abbd40a7416fd900179d02773
    64359b7192746a14740ad4bb7afe4e097327d0790190fd16

Output of the above example in PHP 5.4:

    64359b7192746a14740ad4bb7afe4e097327d0790190fd16
    146a7492719b3564094efe7abbd40a7416fd900179d02773

### See Also

-   <span class="function">hash\_file</span>
-   <span class="function">hash\_hmac</span>
-   <span class="function">hash\_init</span>
-   <span class="function">md5</span>
-   <span class="function">sha1</span>

**Table of Contents**

-   [hash\_algos](/ref/hash.html#hash_algos) — Return a list of
    registered hashing algorithms
-   [hash\_copy](/ref/hash.html#hash_copy) — Copy hashing context
-   [hash\_equals](/ref/hash.html#hash_equals) — Timing attack safe
    string comparison
-   [hash\_file](/ref/hash.html#hash_file) — Generate a hash value using
    the contents of a given file
-   [hash\_final](/ref/hash.html#hash_final) — Finalize an incremental
    hash and return resulting digest
-   [hash\_hkdf](/ref/hash.html#hash_hkdf) — Generate a HKDF key
    derivation of a supplied key input
-   [hash\_hmac\_algos](/ref/hash.html#hash_hmac_algos) — Return a list
    of registered hashing algorithms suitable for hash\_hmac
-   [hash\_hmac\_file](/ref/hash.html#hash_hmac_file) — Generate a keyed
    hash value using the HMAC method and the contents of a given file
-   [hash\_hmac](/ref/hash.html#hash_hmac) — Generate a keyed hash value
    using the HMAC method
-   [hash\_init](/ref/hash.html#hash_init) — Initialize an incremental
    hashing context
-   [hash\_pbkdf2](/ref/hash.html#hash_pbkdf2) — Generate a PBKDF2 key
    derivation of a supplied password
-   [hash\_update\_file](/ref/hash.html#hash_update_file) — Pump data
    into an active hashing context from a file
-   [hash\_update\_stream](/ref/hash.html#hash_update_stream) — Pump
    data into an active hashing context from an open stream
-   [hash\_update](/ref/hash.html#hash_update) — Pump data into an
    active hashing context
-   [hash](/ref/hash.html#hash) — Generate a hash value (message digest)

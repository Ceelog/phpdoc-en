mcrypt\_cbc
===========

Encrypts/decrypts data in CBC mode

**Warning**

This function was *DEPRECATED* in PHP 5.5.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">mcrypt\_decrypt</span>
-   <span class="function">mcrypt\_encrypt</span>

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_cbc</span> ( <span class="methodparam"><span
class="type">int</span> `$cipher`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$mode`</span> \[, <span class="methodparam"><span
class="type">string</span> `$iv`</span> \] )

<span class="type">string</span> <span
class="methodname">mcrypt\_cbc</span> ( <span class="methodparam"><span
class="type">string</span> `$cipher`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$mode`</span> \[, <span class="methodparam"><span
class="type">string</span> `$iv`</span> \] )

The first prototype is when linked against libmcrypt 2.2.x, the second
when linked against libmcrypt 2.4.x or higher. The `mode` should be
either **`MCRYPT_ENCRYPT`** or **`MCRYPT_DECRYPT`**.

mcrypt\_cfb
===========

Encrypts/decrypts data in CFB mode

**Warning**

This function was *DEPRECATED* in PHP 5.5.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">mcrypt\_decrypt</span>
-   <span class="function">mcrypt\_encrypt</span>

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_cfb</span> ( <span class="methodparam"><span
class="type">int</span> `$cipher`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$mode`</span> , <span class="methodparam"><span
class="type">string</span> `$iv`</span> )

<span class="type">string</span> <span
class="methodname">mcrypt\_cfb</span> ( <span class="methodparam"><span
class="type">string</span> `$cipher`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$mode`</span> \[, <span class="methodparam"><span
class="type">string</span> `$iv`</span> \] )

The first prototype is when linked against libmcrypt 2.2.x, the second
when linked against libmcrypt 2.4.x or higher. The `mode` should be
either **`MCRYPT_ENCRYPT`** or **`MCRYPT_DECRYPT`**.

mcrypt\_create\_iv
==================

Creates an initialization vector (IV) from a random source

**Warning**

This function was *DEPRECATED* in PHP 7.1.0, and *REMOVED* in PHP 7.2.0.

Alternatives to this function include:

-   <span class="function">random\_bytes</span>

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_create\_iv</span> ( <span
class="methodparam"><span class="type">int</span> `$size`</span> \[,
<span class="methodparam"><span class="type">int</span> `$source`<span
class="initializer"> = MCRYPT\_DEV\_URANDOM</span></span> \] )

Creates an initialization vector (IV) from a random source.

The IV is only meant to give an alternative seed to the encryption
routines. This IV does not need to be secret at all, though it can be
desirable. You even can send it along with your ciphertext without
losing security.

### Parameters

`size`  
The size of the IV.

`source`  
The source of the IV. The source can be **`MCRYPT_RAND`** (system random
number generator), **`MCRYPT_DEV_RANDOM`** (read data from
`/dev/random`) and **`MCRYPT_DEV_URANDOM`** (read data from
`/dev/urandom`). Prior to 5.3.0, **`MCRYPT_RAND`** was the only one
supported on Windows.

Note that the default value of this parameter was
**`MCRYPT_DEV_RANDOM`** prior to PHP 5.6.0.

> **Note**: <span class="simpara"> Note that **`MCRYPT_DEV_RANDOM`** may
> block until more entropy is available. </span>

### Return Values

Returns the initialization vector, or **`false`** on error.

### Examples

**Example \#1 <span class="function">mcrypt\_create\_iv</span> Example**

``` php
<?php
    $size = mcrypt_get_iv_size(MCRYPT_CAST_256, MCRYPT_MODE_CFB);
    $iv = mcrypt_create_iv($size, MCRYPT_DEV_RANDOM);
?>
```

### See Also

-   <a href="http://www.ciphersbyritter.com/GLOSSARY.HTM#IV" class="link external">» http://www.ciphersbyritter.com/GLOSSARY.HTM#IV</a>
-   <a href="http://www.quadibloc.com/crypto/co0409.htm" class="link external">» http://www.quadibloc.com/crypto/co0409.htm</a>
-   Chapter 9.3 of Applied Cryptography by Schneier (ISBN 0-471-11709-9)
-   <span class="function">random\_bytes</span>

mcrypt\_decrypt
===============

Decrypts crypttext with given parameters

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mcrypt\_decrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$cipher`</span> ,
<span class="methodparam"><span class="type">string</span> `$key`</span>
, <span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span
class="type">string</span> `$mode`</span> \[, <span
class="methodparam"><span class="type">string</span> `$iv`</span> \] )

Decrypts the `data` and returns the unencrypted data.

### Parameters

`cipher`  
One of the **`MCRYPT_ciphername`** constants, or the name of the
algorithm as string.

`key`  
The key with which the data was encrypted. If the provided key size is
not supported by the cipher, the function will emit a warning and return
**`false`**

`data`  
The data that will be decrypted with the given `cipher` and `mode`. If
the size of the data is not n \* blocksize, the data will be padded with
'*\\0*'.

`mode`  
One of the **`MCRYPT_MODE_modename`** constants, or one of the following
strings: "ecb", "cbc", "cfb", "ofb", "nofb" or "stream".

`iv`  
Used for the initialization in CBC, CFB, OFB modes, and in some
algorithms in STREAM mode. If the provided IV size is not supported by
the chaining mode or no IV was provided, but the chaining mode requires
one, the function will emit a warning and return **`false`**.

### Return Values

Returns the decrypted data as a string or **`false`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                                                                                  |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.6.0   | Invalid `key` and `iv` sizes are no longer accepted. <span class="function">mcrypt\_decrypt</span> will now throw a warning and return **`false`** if the inputs are invalid. Previously keys and IVs were padded with '*\\0*' bytes to the next valid size. |

### See Also

-   <span class="function">mcrypt\_encrypt</span>

mcrypt\_ecb
===========

Deprecated: Encrypts/decrypts data in ECB mode

**Warning**

This function was *DEPRECATED* in PHP 5.5.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">mcrypt\_decrypt</span>
-   <span class="function">mcrypt\_encrypt</span>

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_ecb</span> ( <span class="methodparam"><span
class="type">int</span> `$cipher`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$mode`</span> )

<span class="type">string</span> <span
class="methodname">mcrypt\_ecb</span> ( <span class="methodparam"><span
class="type">string</span> `$cipher`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$mode`</span> \[, <span class="methodparam"><span
class="type">string</span> `$iv`</span> \] )

The first prototype is when linked against libmcrypt 2.2.x, the second
when linked against libmcrypt 2.4.x or higher. The `mode` should be
either **`MCRYPT_ENCRYPT`** or **`MCRYPT_DECRYPT`**.

mcrypt\_enc\_get\_algorithms\_name
==================================

Returns the name of the opened algorithm

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_enc\_get\_algorithms\_name</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

This function returns the name of the algorithm.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns the name of the opened algorithm as a string.

### Examples

**Example \#1 <span
class="function">mcrypt\_enc\_get\_algorithms\_name</span> example**

``` php
<?php
$td = mcrypt_module_open(MCRYPT_CAST_256, '', MCRYPT_MODE_CFB, '');
echo mcrypt_enc_get_algorithms_name($td). "\n";

$td = mcrypt_module_open('cast-256', '', MCRYPT_MODE_CFB, '');
echo mcrypt_enc_get_algorithms_name($td). "\n";
?>
```

The above example will output:

    CAST-256
    CAST-256

mcrypt\_enc\_get\_block\_size
=============================

Returns the blocksize of the opened algorithm

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">mcrypt\_enc\_get\_block\_size</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

Gets the blocksize of the opened algorithm.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns the block size of the specified algorithm in bytes.

mcrypt\_enc\_get\_iv\_size
==========================

Returns the size of the IV of the opened algorithm

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">mcrypt\_enc\_get\_iv\_size</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

This function returns the size of the IV of the algorithm specified by
the encryption descriptor in bytes. An IV is used in cbc, cfb and ofb
modes, and in some algorithms in stream mode.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns the size of the IV, or 0 if the IV is ignored by the algorithm.

mcrypt\_enc\_get\_key\_size
===========================

Returns the maximum supported keysize of the opened mode

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">mcrypt\_enc\_get\_key\_size</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

Gets the maximum supported key size of the algorithm in bytes.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns the maximum supported key size of the algorithm in bytes.

mcrypt\_enc\_get\_modes\_name
=============================

Returns the name of the opened mode

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_enc\_get\_modes\_name</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

This function returns the name of the mode.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns the name as a string.

### Examples

**Example \#1 <span
class="function">mcrypt\_enc\_get\_modes\_name</span> example**

``` php
<?php
$td = mcrypt_module_open (MCRYPT_CAST_256, '', MCRYPT_MODE_CFB, '');
echo mcrypt_enc_get_modes_name($td). "\n";

$td = mcrypt_module_open ('cast-256', '', 'ecb', '');
echo mcrypt_enc_get_modes_name($td). "\n";
?>
```

The above example will output:

    CFB
    ECB

mcrypt\_enc\_get\_supported\_key\_sizes
=======================================

Returns an array with the supported keysizes of the opened algorithm

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">array</span> <span
class="methodname">mcrypt\_enc\_get\_supported\_key\_sizes</span> (
<span class="methodparam"><span class="type">resource</span>
`$td`</span> )

Gets the supported key sizes of the opened algorithm.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns an array with the key sizes supported by the algorithm specified
by the encryption descriptor. If it returns an empty array then all key
sizes between 1 and <span
class="function">mcrypt\_enc\_get\_key\_size</span> are supported by the
algorithm.

### Examples

**Example \#1 <span
class="function">mcrypt\_enc\_get\_supported\_key\_sizes</span>
example**

``` php
<?php
    $td = mcrypt_module_open('rijndael-256', '', 'ecb', '');
    var_dump(mcrypt_enc_get_supported_key_sizes($td));
?>
```

The above example will output:

    array(3) {
      [0]=>
      int(16)
      [1]=>
      int(24)
      [2]=>
      int(32)
    }

mcrypt\_enc\_is\_block\_algorithm\_mode
=======================================

Checks whether the encryption of the opened mode works on blocks

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_enc\_is\_block\_algorithm\_mode</span> (
<span class="methodparam"><span class="type">resource</span>
`$td`</span> )

Tells whether the algorithm of the opened mode works on blocks (e.g.
**`false`** for stream, and **`true`** for cbc, cfb, ofb)..

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns **`true`** if the mode is for use with block algorithms,
otherwise it returns **`false`**.

mcrypt\_enc\_is\_block\_algorithm
=================================

Checks whether the algorithm of the opened mode is a block algorithm

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_enc\_is\_block\_algorithm</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

Tells whether the algorithm of the opened mode is a block algorithm.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns **`true`** if the algorithm is a block algorithm or **`false`**
if it is a stream one.

mcrypt\_enc\_is\_block\_mode
============================

Checks whether the opened mode outputs blocks

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_enc\_is\_block\_mode</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

Tells whether the opened mode outputs blocks (e.g. **`true`** for cbc
and ecb, and **`false`** for cfb and stream).

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns **`true`** if the mode outputs blocks of bytes, or **`false`**
if it outputs just bytes.

mcrypt\_enc\_self\_test
=======================

Runs a self test on the opened module

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">mcrypt\_enc\_self\_test</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

This function runs the self test on the algorithm specified by the
descriptor `td`.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns *0* on success and a negative <span class="type">int</span> on
failure.

mcrypt\_encrypt
===============

Encrypts plaintext with given parameters

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">mcrypt\_encrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$cipher`</span> ,
<span class="methodparam"><span class="type">string</span> `$key`</span>
, <span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span
class="type">string</span> `$mode`</span> \[, <span
class="methodparam"><span class="type">string</span> `$iv`</span> \] )

Encrypts the data and returns it.

### Parameters

`cipher`  
One of the **`MCRYPT_ciphername`** constants, or the name of the
algorithm as string.

`key`  
The key with which the data will be encrypted. If the provided key size
is not supported by the cipher, the function will emit a warning and
return **`false`**

`data`  
The data that will be encrypted with the given `cipher` and `mode`. If
the size of the data is not n \* blocksize, the data will be padded with
'*\\0*'.

The returned crypttext can be larger than the size of the data that was
given by `data`.

`mode`  
One of the **`MCRYPT_MODE_modename`** constants, or one of the following
strings: "ecb", "cbc", "cfb", "ofb", "nofb" or "stream".

`iv`  
Used for the initialization in CBC, CFB, OFB modes, and in some
algorithms in STREAM mode. If the provided IV size is not supported by
the chaining mode or no IV was provided, but the chaining mode requires
one, the function will emit a warning and return **`false`**.

### Return Values

Returns the encrypted data as a string or **`false`** on failure.

### Changelog

| Version | Description                                                                                                                                                                                                                                                  |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.6.0   | Invalid `key` and `iv` sizes are no longer accepted. <span class="function">mcrypt\_encrypt</span> will now throw a warning and return **`false`** if the inputs are invalid. Previously keys and IVs were padded with '*\\0*' bytes to the next valid size. |

### Examples

**Example \#1 <span class="function">mcrypt\_encrypt</span> Example**

``` php
<?php
    # --- ENCRYPTION ---

    # the key should be random binary, use scrypt, bcrypt or PBKDF2 to
    # convert a string into a key
    # key is specified using hexadecimal
    $key = pack('H*', "bcb04b7e103a0cd8b54763051cef08bc55abe029fdebae5e1d417e2ffb2a00a3");
    
    # show key size use either 16, 24 or 32 byte keys for AES-128, 192
    # and 256 respectively
    $key_size =  strlen($key);
    echo "Key size: " . $key_size . "\n";
    
    $plaintext = "This string was AES-256 / CBC / ZeroBytePadding encrypted.";

    # create a random IV to use with CBC encoding
    $iv_size = mcrypt_get_iv_size(MCRYPT_RIJNDAEL_128, MCRYPT_MODE_CBC);
    $iv = mcrypt_create_iv($iv_size, MCRYPT_RAND);
    
    # creates a cipher text compatible with AES (Rijndael block size = 128)
    # to keep the text confidential 
    # only suitable for encoded input that never ends with value 00h
    # (because of default zero padding)
    $ciphertext = mcrypt_encrypt(MCRYPT_RIJNDAEL_128, $key,
                                 $plaintext, MCRYPT_MODE_CBC, $iv);

    # prepend the IV for it to be available for decryption
    $ciphertext = $iv . $ciphertext;
    
    # encode the resulting cipher text so it can be represented by a string
    $ciphertext_base64 = base64_encode($ciphertext);

    echo  $ciphertext_base64 . "\n";

    # === WARNING ===

    # Resulting cipher text has no integrity or authenticity added
    # and is not protected against padding oracle attacks.
    
    # --- DECRYPTION ---
    
    $ciphertext_dec = base64_decode($ciphertext_base64);
    
    # retrieves the IV, iv_size should be created using mcrypt_get_iv_size()
    $iv_dec = substr($ciphertext_dec, 0, $iv_size);
    
    # retrieves the cipher text (everything except the $iv_size in the front)
    $ciphertext_dec = substr($ciphertext_dec, $iv_size);

    # may remove 00h valued characters from end of plain text
    $plaintext_dec = mcrypt_decrypt(MCRYPT_RIJNDAEL_128, $key,
                                    $ciphertext_dec, MCRYPT_MODE_CBC, $iv_dec);
    
    echo  $plaintext_dec . "\n";
?>
```

The above example will output:

    Key size: 32
    ENJW8mS2KaJoNB5E5CoSAAu0xARgsR1bdzFWpEn+poYw45q+73az5kYi4j+0haevext1dGrcW8Qi59txfCBV8BBj3bzRP3dFCp3CPQSJ8eU=
    This string was AES-256 / CBC / ZeroBytePadding encrypted.

### See Also

-   <span class="function">mcrypt\_decrypt</span>
-   <span class="function">mcrypt\_module\_open</span>

mcrypt\_generic\_deinit
=======================

This function deinitializes an encryption module

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_generic\_deinit</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

This function terminates encryption specified by the encryption
descriptor (`td`). It clears all buffers, but does not close the module.
You need to call <span class="function">mcrypt\_module\_close</span>
yourself. (But PHP does this for you at the end of the script.)

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">mcrypt\_module\_open</span>
-   <span class="function">mcrypt\_generic\_init</span>

mcrypt\_generic\_end
====================

This function terminates encryption

**Warning**

This function was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">mcrypt\_generic\_deinit</span>

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_generic\_end</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

**Warning**

<span class="function">mcrypt\_generic\_deinit</span> should be used
instead of this function, as it can cause crashes when used with <span
class="function">mcrypt\_module\_close</span> due to multiple buffer
frees.

This function terminates encryption specified by the encryption
descriptor (`td`). Actually it clears all buffers, and closes all the
modules used. Returns **`false`** on error, or **`true`** on success.

mcrypt\_generic\_init
=====================

This function initializes all buffers needed for encryption

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">mcrypt\_generic\_init</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> ,
<span class="methodparam"><span class="type">string</span> `$key`</span>
, <span class="methodparam"><span class="type">string</span>
`$iv`</span> )

You need to call this function before every call to <span
class="function">mcrypt\_generic</span> or <span
class="function">mdecrypt\_generic</span>.

### Parameters

`td`  
The encryption descriptor.

`key`  
The maximum length of the key should be the one obtained by calling
<span class="function">mcrypt\_enc\_get\_key\_size</span> and every
value smaller than this is legal.

`iv`  
The IV should normally have the size of the algorithms block size, but
you must obtain the size by calling <span
class="function">mcrypt\_enc\_get\_iv\_size</span>. IV is ignored in
ECB. IV MUST exist in CFB, CBC, STREAM, nOFB and OFB modes. It needs to
be random and unique (but not secret). The same IV must be used for
encryption/decryption. If you do not want to use it you should set it to
zeros, but this is not recommended.

### Return Values

The function returns a negative value on error: -3 when the key length
was incorrect, -4 when there was a memory allocation problem and any
other return value is an unknown error. If an error occurs a warning
will be displayed accordingly. **`false`** is returned if incorrect
parameters were passed.

### See Also

-   <span class="function">mcrypt\_module\_open</span>

mcrypt\_generic
===============

This function encrypts data

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_generic</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> )

This function encrypts data. The data is padded with "*\\0*" to make
sure the length of the data is n \* blocksize. This function returns the
encrypted data. Note that the length of the returned string can in fact
be longer than the input, due to the padding of the data.

If you want to store the encrypted data in a database make sure to store
the entire string as returned by mcrypt\_generic, or the string will not
entirely decrypt properly. If your original string is 10 characters long
and the block size is 8 (use <span
class="function">mcrypt\_enc\_get\_block\_size</span> to determine the
blocksize), you would need at least 16 characters in your database
field. Note the string returned by <span
class="function">mdecrypt\_generic</span> will be 16 characters as
well...use rtrim($str, "\\0") to remove the padding.

If you are for example storing the data in a MySQL database remember
that varchar fields automatically have trailing spaces removed during
insertion. As encrypted data can end in a space (ASCII 32), the data
will be damaged by this removal. Store data in a tinyblob/tinytext (or
larger) field instead.

### Parameters

`td`  
The encryption descriptor.

The encryption handle should always be initialized with <span
class="function">mcrypt\_generic\_init</span> with a key and an IV
before calling this function. Where the encryption is done, you should
free the encryption buffers by calling <span
class="function">mcrypt\_generic\_deinit</span>. See <span
class="function">mcrypt\_module\_open</span> for an example.

`data`  
The data to encrypt.

### Return Values

Returns the encrypted data.

### See Also

-   <span class="function">mdecrypt\_generic</span>
-   <span class="function">mcrypt\_generic\_init</span>
-   <span class="function">mcrypt\_generic\_deinit</span>

mcrypt\_get\_block\_size
========================

Gets the block size of the specified cipher

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mcrypt\_get\_block\_size</span> ( <span
class="methodparam"><span class="type">int</span> `$cipher`</span> )

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mcrypt\_get\_block\_size</span> ( <span
class="methodparam"><span class="type">string</span> `$cipher`</span> ,
<span class="methodparam"><span class="type">string</span>
`$mode`</span> )

The first prototype is when linked against libmcrypt 2.2.x, the second
when linked against libmcrypt 2.4.x or 2.5.x.

<span class="function">mcrypt\_get\_block\_size</span> is used to get
the size of a block of the specified `cipher` (in combination with an
encryption mode).

It is more useful to use the <span
class="function">mcrypt\_enc\_get\_block\_size</span> function as this
uses the resource returned by <span
class="function">mcrypt\_module\_open</span>.

### Parameters

`cipher`  
One of the **`MCRYPT_ciphername`** constants, or the name of the
algorithm as string.

`mode`  
One of the **`MCRYPT_MODE_modename`** constants, or one of the following
strings: "ecb", "cbc", "cfb", "ofb", "nofb" or "stream".

### Return Values

Returns the algorithm block size in bytes or **`false`** on failure.

### Examples

**Example \#1 <span class="function">mcrypt\_get\_block\_size</span>
example**

This example shows how to use this function when linked against
libmcrypt 2.4.x and 2.5.x.

``` php
<?php

echo mcrypt_get_block_size('tripledes', 'ecb'); // 8

?>
```

### See Also

-   <span class="function">mcrypt\_get\_key\_size</span>
-   <span class="function">mcrypt\_enc\_get\_block\_size</span>
-   <span class="function">mcrypt\_encrypt</span>

mcrypt\_get\_cipher\_name
=========================

Gets the name of the specified cipher

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_get\_cipher\_name</span> ( <span
class="methodparam"><span class="type">int</span> `$cipher`</span> )

<span class="type">string</span> <span
class="methodname">mcrypt\_get\_cipher\_name</span> ( <span
class="methodparam"><span class="type">string</span> `$cipher`</span> )

<span class="function">mcrypt\_get\_cipher\_name</span> is used to get
the name of the specified cipher.

<span class="function">mcrypt\_get\_cipher\_name</span> takes the cipher
number as an argument (libmcrypt 2.2.x) or takes the cipher name as an
argument (libmcrypt 2.4.x or higher) and returns the name of the cipher
or **`false`**, if the cipher does not exist.

### Parameters

`cipher`  
One of the **`MCRYPT_ciphername`** constants, or the name of the
algorithm as string.

### Return Values

This function returns the name of the cipher or **`false`** if the
cipher does not exist.

### Examples

**Example \#1 <span class="function">mcrypt\_get\_cipher\_name</span>
Example**

``` php
<?php
   $cipher = MCRYPT_TripleDES;

   echo mcrypt_get_cipher_name($cipher);
?>
```

The above example will output:

    3DES

mcrypt\_get\_iv\_size
=====================

Returns the size of the IV belonging to a specific cipher/mode
combination

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">mcrypt\_get\_iv\_size</span> ( <span
class="methodparam"><span class="type">string</span> `$cipher`</span> ,
<span class="methodparam"><span class="type">string</span>
`$mode`</span> )

Gets the size of the IV belonging to a specific `cipher`/`mode`
combination.

It is more useful to use the <span
class="function">mcrypt\_enc\_get\_iv\_size</span> function as this uses
the resource returned by <span
class="function">mcrypt\_module\_open</span>.

### Parameters

`cipher`  
One of the **`MCRYPT_ciphername`** constants, or the name of the
algorithm as string.

`mode`  
One of the **`MCRYPT_MODE_modename`** constants, or one of the following
strings: "ecb", "cbc", "cfb", "ofb", "nofb" or "stream".

The IV is ignored in ECB mode as this mode does not require it. You will
need to have the same IV (think: starting point) both at encryption and
decryption stages, otherwise your encryption will fail.

### Return Values

Returns the size of the Initialization Vector (IV) in bytes. On error
the function returns **`false`**. If the IV is ignored in the specified
cipher/mode combination zero is returned.

### Examples

**Example \#1 <span class="function">mcrypt\_get\_iv\_size</span>
Example**

``` php
<?php
    echo mcrypt_get_iv_size(MCRYPT_CAST_256, MCRYPT_MODE_CFB) . "\n";

    echo mcrypt_get_iv_size('des', 'ecb') . "\n";
?>
```

### See Also

-   <span class="function">mcrypt\_get\_block\_size</span>
-   <span class="function">mcrypt\_enc\_get\_iv\_size</span>
-   <span class="function">mcrypt\_create\_iv</span>

mcrypt\_get\_key\_size
======================

Gets the key size of the specified cipher

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mcrypt\_get\_key\_size</span> ( <span
class="methodparam"><span class="type">int</span> `$cipher`</span> )

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">mcrypt\_get\_key\_size</span> ( <span
class="methodparam"><span class="type">string</span> `$cipher`</span> ,
<span class="methodparam"><span class="type">string</span>
`$mode`</span> )

The first prototype is when linked against libmcrypt 2.2.x, the second
when linked against libmcrypt 2.4.x or 2.5.x.

<span class="function">mcrypt\_get\_key\_size</span> is used to get the
size of a key of the specified `cipher` (in combination with an
encryption mode).

It is more useful to use the <span
class="function">mcrypt\_enc\_get\_key\_size</span> function as this
uses the resource returned by <span
class="function">mcrypt\_module\_open</span>.

### Parameters

`cipher`  
One of the **`MCRYPT_ciphername`** constants, or the name of the
algorithm as string.

`mode`  
One of the **`MCRYPT_MODE_modename`** constants, or one of the following
strings: "ecb", "cbc", "cfb", "ofb", "nofb" or "stream".

### Return Values

Returns the maximum supported key size of the algorithm in bytes or
**`false`** on failure.

### Examples

**Example \#1 <span class="function">mcrypt\_get\_key\_size</span>
Example**

``` php
<?php
    echo mcrypt_get_key_size('tripledes', 'ecb');
?>
```

The example above shows how to use this function when linked against
libmcrypt 2.4.x or 2.5.x.

The above example will output:

    24

### See Also

-   <span class="function">mcrypt\_get\_block\_size</span>
-   <span class="function">mcrypt\_enc\_get\_key\_size</span>
-   <span class="function">mcrypt\_encrypt</span>

mcrypt\_list\_algorithms
========================

Gets an array of all supported ciphers

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">array</span> <span
class="methodname">mcrypt\_list\_algorithms</span> (\[ <span
class="methodparam"><span class="type">string</span> `$lib_dir`<span
class="initializer"> = ini\_get("mcrypt.algorithms\_dir")</span></span>
\] )

Gets the list of all supported algorithms in the `lib_dir` parameter.

### Parameters

`lib_dir`  
Specifies the directory where all algorithms are located. If not
specified, the value of the *mcrypt.algorithms\_dir* `php.ini` directive
is used.

### Return Values

Returns an array with all the supported algorithms.

### Examples

**Example \#1 <span class="function">mcrypt\_list\_algorithms</span>
Example**

``` php
<?php
$algorithms = mcrypt_list_algorithms();
print_r($algorithms);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => cast-128
        [1] => gost
        [2] => rijndael-128
        [3] => twofish
        [4] => arcfour
        [5] => cast-256
        [6] => loki97
        [7] => rijndael-192
        [8] => saferplus
        [9] => wake
        [10] => blowfish-compat
        [11] => des
        [12] => rijndael-256
        [13] => serpent
        [14] => xtea
        [15] => blowfish
        [16] => enigma
        [17] => rc2
        [18] => tripledes
    )

mcrypt\_list\_modes
===================

Gets an array of all supported modes

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">array</span> <span
class="methodname">mcrypt\_list\_modes</span> (\[ <span
class="methodparam"><span class="type">string</span> `$lib_dir`<span
class="initializer"> = ini\_get("mcrypt.modes\_dir")</span></span> \] )

Gets the list of all supported modes in the `lib_dir` parameter.

### Parameters

`lib_dir`  
Specifies the directory where all modes are located. If not specified,
the value of the *mcrypt.modes\_dir* `php.ini` directive is used.

### Return Values

Returns an array with all the supported modes.

### Examples

**Example \#1 <span class="function">mcrypt\_list\_modes</span>
Example**

``` php
<?php
    $modes = mcrypt_list_modes();

    foreach ($modes as $mode) {
        echo "$mode <br />\n";
    }
?>
```

The example above will produce a list with all supported algorithms in
the default mode directory. If it is not set with the
*mcrypt.modes\_dir* `php.ini` directive, the default directory of mcrypt
is used (which is `/usr/local/lib/libmcrypt`).

mcrypt\_module\_close
=====================

Closes the mcrypt module

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_module\_close</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> )

Closes the specified encryption handle.

### Parameters

`td`  
The encryption descriptor.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">mcrypt\_module\_open</span>

mcrypt\_module\_get\_algo\_block\_size
======================================

Returns the blocksize of the specified algorithm

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">mcrypt\_module\_get\_algo\_block\_size</span> ( <span
class="methodparam"><span class="type">string</span> `$algorithm`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$lib_dir`</span> \] )

Gets the blocksize of the specified algorithm.

### Parameters

`algorithm`  
The algorithm name.

`lib_dir`  
This optional parameter can contain the location where the mode module
is on the system.

### Return Values

Returns the block size of the algorithm specified in bytes.

mcrypt\_module\_get\_algo\_key\_size
====================================

Returns the maximum supported keysize of the opened mode

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">int</span> <span
class="methodname">mcrypt\_module\_get\_algo\_key\_size</span> ( <span
class="methodparam"><span class="type">string</span> `$algorithm`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$lib_dir`</span> \] )

Gets the maximum supported keysize of the opened mode.

### Parameters

`algorithm`  
The algorithm name.

`lib_dir`  
This optional parameter can contain the location where the mode module
is on the system.

### Return Values

This function returns the maximum supported key size of the algorithm
specified in bytes.

mcrypt\_module\_get\_supported\_key\_sizes
==========================================

Returns an array with the supported keysizes of the opened algorithm

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">array</span> <span
class="methodname">mcrypt\_module\_get\_supported\_key\_sizes</span> (
<span class="methodparam"><span class="type">string</span>
`$algorithm`</span> \[, <span class="methodparam"><span
class="type">string</span> `$lib_dir`</span> \] )

Returns an array with the key sizes supported by the specified
algorithm. If it returns an empty array then all key sizes between 1 and
<span class="function">mcrypt\_module\_get\_algo\_key\_size</span> are
supported by the algorithm.

### Parameters

`algorithm`  
The algorithm to be used.

`lib_dir`  
The optional `lib_dir` parameter can contain the location where the
algorithm module is on the system.

### Return Values

Returns an array with the key sizes supported by the specified
algorithm. If it returns an empty array then all key sizes between 1 and
<span class="function">mcrypt\_module\_get\_algo\_key\_size</span> are
supported by the algorithm.

### See Also

-   <span
    class="function">mcrypt\_enc\_get\_supported\_key\_sizes</span>

mcrypt\_module\_is\_block\_algorithm\_mode
==========================================

Returns if the specified module is a block algorithm or not

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_module\_is\_block\_algorithm\_mode</span> (
<span class="methodparam"><span class="type">string</span>
`$mode`</span> \[, <span class="methodparam"><span
class="type">string</span> `$lib_dir`</span> \] )

This function returns **`true`** if the mode is for use with block
algorithms, otherwise it returns **`false`**. (e.g. **`false`** for
stream, and **`true`** for cbc, cfb, ofb).

### Parameters

`mode`  
The mode to check.

`lib_dir`  
The optional `lib_dir` parameter can contain the location where the
algorithm module is on the system.

### Return Values

This function returns **`true`** if the mode is for use with block
algorithms, otherwise it returns **`false`**. (e.g. **`false`** for
stream, and **`true`** for cbc, cfb, ofb).

mcrypt\_module\_is\_block\_algorithm
====================================

This function checks whether the specified algorithm is a block
algorithm

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_module\_is\_block\_algorithm</span> ( <span
class="methodparam"><span class="type">string</span> `$algorithm`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$lib_dir`</span> \] )

This function returns **`true`** if the specified algorithm is a block
algorithm, or **`false`** if it is a stream one.

### Parameters

`algorithm`  
The algorithm to check.

`lib_dir`  
The optional `lib_dir` parameter can contain the location where the
algorithm module is on the system.

### Return Values

This function returns **`true`** if the specified algorithm is a block
algorithm, or **`false`** if it is a stream one.

mcrypt\_module\_is\_block\_mode
===============================

Returns if the specified mode outputs blocks or not

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_module\_is\_block\_mode</span> ( <span
class="methodparam"><span class="type">string</span> `$mode`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$lib_dir`</span> \] )

This function returns **`true`** if the mode outputs blocks of bytes or
**`false`** if it outputs just bytes. (e.g. **`true`** for cbc and ecb,
and **`false`** for cfb and stream).

### Parameters

`mode`  
One of the **`MCRYPT_MODE_modename`** constants, or one of the following
strings: "ecb", "cbc", "cfb", "ofb", "nofb" or "stream".

`lib_dir`  
The optional `lib_dir` parameter can contain the location where the
algorithm module is on the system.

### Return Values

This function returns **`true`** if the mode outputs blocks of bytes or
**`false`** if it outputs just bytes. (e.g. **`true`** for cbc and ecb,
and **`false`** for cfb and stream).

mcrypt\_module\_open
====================

Opens the module of the algorithm and the mode to be used

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">resource</span> <span
class="methodname">mcrypt\_module\_open</span> ( <span
class="methodparam"><span class="type">string</span> `$algorithm`</span>
, <span class="methodparam"><span class="type">string</span>
`$algorithm_directory`</span> , <span class="methodparam"><span
class="type">string</span> `$mode`</span> , <span
class="methodparam"><span class="type">string</span>
`$mode_directory`</span> )

This function opens the module of the algorithm and the mode to be used.
The name of the algorithm is specified in algorithm, e.g. *"twofish"* or
is one of the **`MCRYPT_ciphername`** constants. The module is closed by
calling <span class="function">mcrypt\_module\_close</span>.

### Parameters

`algorithm`  
One of the **`MCRYPT_ciphername`** constants, or the name of the
algorithm as string.

`algorithm_directory`  
The `algorithm_directory` parameter is used to locate the encryption
module. When you supply a directory name, it is used. When you set it to
an empty string (*""*), the value set by the *mcrypt.algorithms\_dir*
`php.ini` directive is used. When it is not set, the default directory
that is used is the one that was compiled into libmcrypt (usually
`/usr/local/lib/libmcrypt`).

`mode`  
One of the **`MCRYPT_MODE_modename`** constants, or one of the following
strings: "ecb", "cbc", "cfb", "ofb", "nofb" or "stream".

`mode_directory`  
The `mode_directory` parameter is used to locate the encryption module.
When you supply a directory name, it is used. When you set it to an
empty string (*""*), the value set by the *mcrypt.modes\_dir* `php.ini`
directive is used. When it is not set, the default directory that is
used is the one that was compiled-in into libmcrypt (usually
`/usr/local/lib/libmcrypt`).

### Return Values

Normally it returns an encryption descriptor, or **`false`** on error.

### Examples

**Example \#1 <span class="function">mcrypt\_module\_open</span>
Examples**

``` php
<?php
    $td = mcrypt_module_open(MCRYPT_DES, '',
        MCRYPT_MODE_ECB, '/usr/lib/mcrypt-modes');

    $td = mcrypt_module_open('rijndael-256', '', 'ofb', '');
?>
```

The first line in the example above will try to open the *DES* cipher
from the default directory and the *ECB* mode from the directory
`/usr/lib/mcrypt-modes`. The second example uses strings as name for the
cipher and mode, this only works when the extension is linked against
libmcrypt 2.4.x or 2.5.x.

**Example \#2 Using <span class="function">mcrypt\_module\_open</span>
in encryption**

``` php
<?php
    /* Open the cipher */
    $td = mcrypt_module_open('rijndael-256', '', 'ofb', '');

    /* Create the IV and determine the keysize length, use MCRYPT_RAND
     * on Windows instead */
    $iv = mcrypt_create_iv(mcrypt_enc_get_iv_size($td), MCRYPT_DEV_RANDOM);
    $ks = mcrypt_enc_get_key_size($td);

    /* Create key */
    $key = substr(md5('very secret key'), 0, $ks);

    /* Intialize encryption */
    mcrypt_generic_init($td, $key, $iv);

    /* Encrypt data */
    $encrypted = mcrypt_generic($td, 'This is very important data');

    /* Terminate encryption handler */
    mcrypt_generic_deinit($td);

    /* Initialize encryption module for decryption */
    mcrypt_generic_init($td, $key, $iv);

    /* Decrypt encrypted string */
    $decrypted = mdecrypt_generic($td, $encrypted);

    /* Terminate decryption handle and close module */
    mcrypt_generic_deinit($td);
    mcrypt_module_close($td);

    /* Show string */
    echo trim($decrypted) . "\n";
?>
```

### See Also

-   <span class="function">mcrypt\_module\_close</span>
-   <span class="function">mcrypt\_generic</span>
-   <span class="function">mdecrypt\_generic</span>
-   <span class="function">mcrypt\_generic\_init</span>
-   <span class="function">mcrypt\_generic\_deinit</span>

mcrypt\_module\_self\_test
==========================

This function runs a self test on the specified module

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">bool</span> <span
class="methodname">mcrypt\_module\_self\_test</span> ( <span
class="methodparam"><span class="type">string</span> `$algorithm`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$lib_dir`</span> \] )

This function runs the self test on the algorithm specified.

### Parameters

`algorithm`  
One of the **`MCRYPT_ciphername`** constants, or the name of the
algorithm as string.

`lib_dir`  
The optional `lib_dir` parameter can contain the location where the
algorithm module is on the system.

### Return Values

The function returns **`true`** if the self test succeeds, or
**`false`** when it fails.

### Examples

**Example \#1 <span class="function">mcrypt\_module\_self\_test</span>
example**

``` php
<?php
var_dump(mcrypt_module_self_test(MCRYPT_RIJNDAEL_128)) . "\n";
var_dump(mcrypt_module_self_test(MCRYPT_BOGUS_CYPHER));
?>
```

The above example will output:

    bool(true)
    bool(false)

mcrypt\_ofb
===========

Encrypts/decrypts data in OFB mode

**Warning**

This function was *DEPRECATED* in PHP 5.5.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this function include:

-   <span class="function">mcrypt\_decrypt</span>
-   <span class="function">mcrypt\_encrypt</span>

### Description

<span class="type">string</span> <span
class="methodname">mcrypt\_ofb</span> ( <span class="methodparam"><span
class="type">int</span> `$cipher`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$mode`</span> , <span class="methodparam"><span
class="type">string</span> `$iv`</span> )

<span class="type">string</span> <span
class="methodname">mcrypt\_ofb</span> ( <span class="methodparam"><span
class="type">string</span> `$cipher`</span> , <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span class="type">int</span>
`$mode`</span> \[, <span class="methodparam"><span
class="type">string</span> `$iv`</span> \] )

The first prototype is when linked against libmcrypt 2.2.x, the second
when linked against libmcrypt 2.4.x or higher. The `mode` should be
either **`MCRYPT_ENCRYPT`** or **`MCRYPT_DECRYPT`**.

mdecrypt\_generic
=================

Decrypts data

**Warning**

This function has been *DEPRECATED* as of PHP 7.1.0 and *REMOVED* as of
PHP 7.2.0. Relying on this function is highly discouraged.

### Description

<span class="type">string</span> <span
class="methodname">mdecrypt\_generic</span> ( <span
class="methodparam"><span class="type">resource</span> `$td`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> )

This function decrypts data. Note that the length of the returned string
can in fact be longer than the unencrypted string, due to the padding of
the data.

### Parameters

`td`  
An encryption descriptor returned by <span
class="function">mcrypt\_module\_open</span>

`data`  
Encrypted data.

### Examples

**Example \#1 <span class="function">mdecrypt\_generic</span> Example**

``` php
<?php
    /* Data */
    $key = 'this is a very long key, even too long for the cipher';
    $plain_text = 'very important data';

    /* Open module, and create IV */
    $td = mcrypt_module_open('des', '', 'ecb', '');
    $key = substr($key, 0, mcrypt_enc_get_key_size($td));
    $iv_size = mcrypt_enc_get_iv_size($td);
    $iv = mcrypt_create_iv($iv_size, MCRYPT_RAND);

    /* Initialize encryption handle */
    if (mcrypt_generic_init($td, $key, $iv) != -1) {

        /* Encrypt data */
        $c_t = mcrypt_generic($td, $plain_text);
        mcrypt_generic_deinit($td);

        /* Reinitialize buffers for decryption */
        mcrypt_generic_init($td, $key, $iv);
        $p_t = mdecrypt_generic($td, $c_t);

        /* Clean up */
        mcrypt_generic_deinit($td);
        mcrypt_module_close($td);
    }

    if (strncmp($p_t, $plain_text, strlen($plain_text)) == 0) {
        echo "ok\n";
    } else {
        echo "error\n";
    }
?>
```

The example above shows how to check if the data before the encryption
is the same as the data after the decryption. It is very important to
reinitialize the encryption buffer with <span
class="function">mcrypt\_generic\_init</span> before you try to decrypt
the data.

The decryption handle should always be initialized with <span
class="function">mcrypt\_generic\_init</span> with a key and an IV
before calling this function. Where the encryption is done, you should
free the encryption buffers by calling <span
class="function">mcrypt\_generic\_deinit</span>. See <span
class="function">mcrypt\_module\_open</span> for an example.

### See Also

-   <span class="function">mcrypt\_generic</span>
-   <span class="function">mcrypt\_generic\_init</span>
-   <span class="function">mcrypt\_generic\_deinit</span>

**Table of Contents**

-   [mcrypt\_cbc](/ref/mcrypt.html#mcrypt_cbc) — Encrypts/decrypts data
    in CBC mode
-   [mcrypt\_cfb](/ref/mcrypt.html#mcrypt_cfb) — Encrypts/decrypts data
    in CFB mode
-   [mcrypt\_create\_iv](/ref/mcrypt.html#mcrypt_create_iv) — Creates an
    initialization vector (IV) from a random source
-   [mcrypt\_decrypt](/ref/mcrypt.html#mcrypt_decrypt) — Decrypts
    crypttext with given parameters
-   [mcrypt\_ecb](/ref/mcrypt.html#mcrypt_ecb) — Deprecated:
    Encrypts/decrypts data in ECB mode
-   [mcrypt\_enc\_get\_algorithms\_name](/ref/mcrypt.html#mcrypt_enc_get_algorithms_name)
    — Returns the name of the opened algorithm
-   [mcrypt\_enc\_get\_block\_size](/ref/mcrypt.html#mcrypt_enc_get_block_size)
    — Returns the blocksize of the opened algorithm
-   [mcrypt\_enc\_get\_iv\_size](/ref/mcrypt.html#mcrypt_enc_get_iv_size)
    — Returns the size of the IV of the opened algorithm
-   [mcrypt\_enc\_get\_key\_size](/ref/mcrypt.html#mcrypt_enc_get_key_size)
    — Returns the maximum supported keysize of the opened mode
-   [mcrypt\_enc\_get\_modes\_name](/ref/mcrypt.html#mcrypt_enc_get_modes_name)
    — Returns the name of the opened mode
-   [mcrypt\_enc\_get\_supported\_key\_sizes](/ref/mcrypt.html#mcrypt_enc_get_supported_key_sizes)
    — Returns an array with the supported keysizes of the opened
    algorithm
-   [mcrypt\_enc\_is\_block\_algorithm\_mode](/ref/mcrypt.html#mcrypt_enc_is_block_algorithm_mode)
    — Checks whether the encryption of the opened mode works on blocks
-   [mcrypt\_enc\_is\_block\_algorithm](/ref/mcrypt.html#mcrypt_enc_is_block_algorithm)
    — Checks whether the algorithm of the opened mode is a block
    algorithm
-   [mcrypt\_enc\_is\_block\_mode](/ref/mcrypt.html#mcrypt_enc_is_block_mode)
    — Checks whether the opened mode outputs blocks
-   [mcrypt\_enc\_self\_test](/ref/mcrypt.html#mcrypt_enc_self_test) —
    Runs a self test on the opened module
-   [mcrypt\_encrypt](/ref/mcrypt.html#mcrypt_encrypt) — Encrypts
    plaintext with given parameters
-   [mcrypt\_generic\_deinit](/ref/mcrypt.html#mcrypt_generic_deinit) —
    This function deinitializes an encryption module
-   [mcrypt\_generic\_end](/ref/mcrypt.html#mcrypt_generic_end) — This
    function terminates encryption
-   [mcrypt\_generic\_init](/ref/mcrypt.html#mcrypt_generic_init) — This
    function initializes all buffers needed for encryption
-   [mcrypt\_generic](/ref/mcrypt.html#mcrypt_generic) — This function
    encrypts data
-   [mcrypt\_get\_block\_size](/ref/mcrypt.html#mcrypt_get_block_size) —
    Gets the block size of the specified cipher
-   [mcrypt\_get\_cipher\_name](/ref/mcrypt.html#mcrypt_get_cipher_name)
    — Gets the name of the specified cipher
-   [mcrypt\_get\_iv\_size](/ref/mcrypt.html#mcrypt_get_iv_size) —
    Returns the size of the IV belonging to a specific cipher/mode
    combination
-   [mcrypt\_get\_key\_size](/ref/mcrypt.html#mcrypt_get_key_size) —
    Gets the key size of the specified cipher
-   [mcrypt\_list\_algorithms](/ref/mcrypt.html#mcrypt_list_algorithms)
    — Gets an array of all supported ciphers
-   [mcrypt\_list\_modes](/ref/mcrypt.html#mcrypt_list_modes) — Gets an
    array of all supported modes
-   [mcrypt\_module\_close](/ref/mcrypt.html#mcrypt_module_close) —
    Closes the mcrypt module
-   [mcrypt\_module\_get\_algo\_block\_size](/ref/mcrypt.html#mcrypt_module_get_algo_block_size)
    — Returns the blocksize of the specified algorithm
-   [mcrypt\_module\_get\_algo\_key\_size](/ref/mcrypt.html#mcrypt_module_get_algo_key_size)
    — Returns the maximum supported keysize of the opened mode
-   [mcrypt\_module\_get\_supported\_key\_sizes](/ref/mcrypt.html#mcrypt_module_get_supported_key_sizes)
    — Returns an array with the supported keysizes of the opened
    algorithm
-   [mcrypt\_module\_is\_block\_algorithm\_mode](/ref/mcrypt.html#mcrypt_module_is_block_algorithm_mode)
    — Returns if the specified module is a block algorithm or not
-   [mcrypt\_module\_is\_block\_algorithm](/ref/mcrypt.html#mcrypt_module_is_block_algorithm)
    — This function checks whether the specified algorithm is a block
    algorithm
-   [mcrypt\_module\_is\_block\_mode](/ref/mcrypt.html#mcrypt_module_is_block_mode)
    — Returns if the specified mode outputs blocks or not
-   [mcrypt\_module\_open](/ref/mcrypt.html#mcrypt_module_open) — Opens
    the module of the algorithm and the mode to be used
-   [mcrypt\_module\_self\_test](/ref/mcrypt.html#mcrypt_module_self_test)
    — This function runs a self test on the specified module
-   [mcrypt\_ofb](/ref/mcrypt.html#mcrypt_ofb) — Encrypts/decrypts data
    in OFB mode
-   [mdecrypt\_generic](/ref/mcrypt.html#mdecrypt_generic) — Decrypts
    data

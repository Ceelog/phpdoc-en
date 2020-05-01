This extension makes use of the keyring of the current user. This
keyring is normally located in \~./.gnupg/. To specify a custom
location, store the path to the keyring in the environment variable
GNUPGHOME. See <a href="/ref/info.html#putenv" class="link">putenv</a>
for more information how to do this.

Some functions require the specification of a key. This specification
can be anything that refers to a unique key (userid, key-id,
fingerprint, ...). This documentation uses the fingerprint in all
examples.

> **Note**:
>
> As alternative to the explicitly documented functions using <span
> class="type">resource</span>s, you can also use an object-oriented
> style using <span class="classname">gnupg</span> objects.

gnupg\_adddecryptkey
====================

Add a key for decryption

### Description

<span class="type">bool</span> <span
class="methodname">gnupg\_adddecryptkey</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$fingerprint`</span> , <span
class="methodparam"><span class="type">string</span>
`$passphrase`</span> )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`fingerprint`  
The fingerprint key.

`passphrase`  
The pass phrase.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_adddecryptkey</span> example**

``` php
<?php
$res = gnupg_init();
gnupg_adddecryptkey($res,"8660281B6051D071D94B5B230549F9DC851566DC","test");
?>
```

**Example \#2 OO <span class="function">gnupg\_adddecryptkey</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> adddecryptkey("8660281B6051D071D94B5B230549F9DC851566DC","test");
?>
```

gnupg\_addencryptkey
====================

Add a key for encryption

### Description

<span class="type">bool</span> <span
class="methodname">gnupg\_addencryptkey</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$fingerprint`</span> )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`fingerprint`  
The fingerprint key.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_addencryptkey</span> example**

``` php
<?php
$res = gnupg_init();
gnupg_addencryptkey($res,"8660281B6051D071D94B5B230549F9DC851566DC");
?>
```

**Example \#2 OO <span class="function">gnupg\_addencryptkey</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> addencryptkey("8660281B6051D071D94B5B230549F9DC851566DC");
?>
```

gnupg\_addsignkey
=================

Add a key for signing

### Description

<span class="type">bool</span> <span
class="methodname">gnupg\_addsignkey</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$fingerprint`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$passphrase`</span> \] )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`fingerprint`  
The fingerprint key.

`passphrase`  
The pass phrase.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_addsignkey</span>
example**

``` php
<?php
$res = gnupg_init();
gnupg_addsignkey($res,"8660281B6051D071D94B5B230549F9DC851566DC","test");
?>
```

**Example \#2 OO <span class="function">gnupg\_addsignkey</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> addsignkey("8660281B6051D071D94B5B230549F9DC851566DC","test");
?>
```

gnupg\_cleardecryptkeys
=======================

Removes all keys which were set for decryption before

### Description

<span class="type">bool</span> <span
class="methodname">gnupg\_cleardecryptkeys</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_cleardecryptkeys</span> example**

``` php
<?php
$res = gnupg_init();
gnupg_cleardecryptkeys($res);
?>
```

**Example \#2 OO <span class="function">gnupg\_cleardecryptkeys</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> cleardecryptkeys();
?>
```

gnupg\_clearencryptkeys
=======================

Removes all keys which were set for encryption before

### Description

<span class="type">bool</span> <span
class="methodname">gnupg\_clearencryptkeys</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_clearencryptkeys</span> example**

``` php
<?php
$res = gnupg_init();
gnupg_clearencryptkeys($res);
?>
```

**Example \#2 OO <span class="function">gnupg\_clearencryptkeys</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> clearencryptkeys();
?>
```

gnupg\_clearsignkeys
====================

Removes all keys which were set for signing before

### Description

<span class="type">bool</span> <span
class="methodname">gnupg\_clearsignkeys</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_clearsignkeys</span> example**

``` php
<?php
$res = gnupg_init();
gnupg_clearsignkeys($res);
?>
```

**Example \#2 OO <span class="function">gnupg\_clearsignkeys</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> clearsignkeys();
?>
```

gnupg\_decrypt
==============

Decrypts a given text

### Description

<span class="type">string</span> <span
class="methodname">gnupg\_decrypt</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Decrypts the given text with the keys, which were set with
<a href="/ref/gnupg.html#gnupg_adddecryptkey" class="link">gnupg_adddecryptkey</a>
before.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`text`  
The text being decrypted.

### Return Values

On success, this function returns the decrypted text. On failure, this
function returns **`FALSE`**.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_decrypt</span>
example**

``` php
<?php
$res = gnupg_init();
gnupg_adddecryptkey($res,"8660281B6051D071D94B5B230549F9DC851566DC","test");
$plain = gnupg_decrypt($res,$encrypted_text);
echo $plain;
?>
```

**Example \#2 OO <span class="function">gnupg\_encrypt</span> example**

``` php
<?php
$gpg = new gnupg();
$gpg -> adddecryptkey("8660281B6051D071D94B5B230549F9DC851566DC","test");
$plain = $gpg -> decrypt($encrypted_text);
echo $plain;
?>
```

gnupg\_decryptverify
====================

Decrypts and verifies a given text

### Description

<span class="type">array</span> <span
class="methodname">gnupg\_decryptverify</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> , <span
class="methodparam"><span class="type">string</span>
`&$plaintext`</span> )

Decrypts and verifies a given text and returns information about the
signature.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`text`  
The text being decrypted.

`plaintext`  
The parameter `plaintext` gets filled with the decrypted text.

### Return Values

On success, this function returns information about the signature and
fills the `plaintext` parameter with the decrypted text. On failure,
this function returns **`FALSE`**.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_decryptverify</span> example**

``` php
<?php
$plaintext = "";
$res = gnupg_init();
gnupg_adddecryptkey($res,"8660281B6051D071D94B5B230549F9DC851566DC","test");
$info = gnupg_decryptverify($res,$text,$plaintext);
print_r($info);
?>
```

**Example \#2 OO <span class="function">gnupg\_decryptverify</span>
example**

``` php
<?php
$plaintext = "";
$gpg = new gnupg();
$gpg -> adddecryptkey("8660281B6051D071D94B5B230549F9DC851566DC","test");
$info = $gpg -> decryptverify($text,$plaintext);
print_r($info);
?>
```

gnupg\_encrypt
==============

Encrypts a given text

### Description

<span class="type">string</span> <span
class="methodname">gnupg\_encrypt</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$plaintext`</span> )

Encrypts the given `plaintext` with the keys, which were set with
<a href="/ref/gnupg.html#gnupg_addencryptkey" class="link">gnupg_addencryptkey</a>
before and returns the encrypted text.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`plaintext`  
The text being encrypted.

### Return Values

On success, this function returns the encrypted text. On failure, this
function returns **`FALSE`**.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_encrypt</span>
example**

``` php
<?php
$res = gnupg_init();
gnupg_addencryptkey($res,"8660281B6051D071D94B5B230549F9DC851566DC");
$enc = gnupg_encrypt($res, "just a test");
echo $enc;
?>
```

**Example \#2 OO <span class="function">gnupg\_encrypt</span> example**

``` php
<?php
$gpg = new gnupg();
$gpg -> addencryptkey("8660281B6051D071D94B5B230549F9DC851566DC");
$enc = $gpg -> encrypt("just a test");
echo $enc;
?>
```

gnupg\_encryptsign
==================

Encrypts and signs a given text

### Description

<span class="type">string</span> <span
class="methodname">gnupg\_encryptsign</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$plaintext`</span> )

Encrypts and signs the given `plaintext` with the keys, which were set
with
<a href="/ref/gnupg.html#gnupg_addsignkey" class="link">gnupg_addsignkey</a>
and
<a href="/ref/gnupg.html#gnupg_addencryptkey" class="link">gnupg_addencryptkey</a>
before and returns the encrypted and signed text.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`plaintext`  
The text being encrypted.

### Return Values

On success, this function returns the encrypted and signed text. On
failure, this function returns **`FALSE`**.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_encryptsign</span> example**

``` php
<?php
$res = gnupg_init();
gnupg_addencryptkey($res,"8660281B6051D071D94B5B230549F9DC851566DC");
gnupg_addsignkey($res,"8660281B6051D071D94B5B230549F9DC851566DC","test");
$enc = gnupg_encryptsign($res, "just a test");
echo $enc;
?>
```

**Example \#2 OO <span class="function">gnupg\_encryptsign</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> addencryptkey("8660281B6051D071D94B5B230549F9DC851566DC");
$gpg -> addsignkey("8660281B6051D071D94B5B230549F9DC851566DC","test");
$enc = $gpg -> encryptsign("just a test");
echo $enc;
?>
```

gnupg\_export
=============

Exports a key

### Description

<span class="type">string</span> <span
class="methodname">gnupg\_export</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$fingerprint`</span> )

Exports the key `fingerprint`.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`fingerprint`  
The fingerprint key.

### Return Values

On success, this function returns the keydata. On failure, this function
returns **`FALSE`**.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_export</span>
example**

``` php
<?php
$res = gnupg_init();
$export = gnupg_export($res,"8660281B6051D071D94B5B230549F9DC851566DC");
echo $export;
?>
```

**Example \#2 OO <span class="function">gnupg\_export</span> example**

``` php
<?php
$gpg = new gnupg();
$export = $gpg -> export("8660281B6051D071D94B5B230549F9DC851566DC");
?>
```

gnupg\_geterror
===============

Returns the errortext, if a function fails

### Description

<span class="type">string</span> <span
class="methodname">gnupg\_geterror</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

### Return Values

Returns an errortext, if an error has occurred, otherwise **`FALSE`**.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_geterror</span>
example**

``` php
<?php
$res = gnupg_init();
echo gnupg_geterror($res);
?>
```

**Example \#2 OO <span class="function">gnupg\_geterror</span> example**

``` php
<?php
$gpg = new gnupg();
echo $gpg -> geterror();
?>
```

gnupg\_getprotocol
==================

Returns the currently active protocol for all operations

### Description

<span class="type">int</span> <span
class="methodname">gnupg\_getprotocol</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

### Return Values

Returns the currently active protocol, which can be one of
**`GNUPG_PROTOCOL_OpenPGP`** or **`GNUPG_PROTOCOL_CMS`**.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_getprotocol</span> example**

``` php
<?php
$res = gnupg_init();
echo gnupg_getprotocol($res);
?>
```

**Example \#2 OO <span class="function">gnupg\_getprotocol</span>
example**

``` php
<?php
$gpg = new gnupg();
echo $gpg -> getprotocol();
?>
```

gnupg\_import
=============

Imports a key

### Description

<span class="type">array</span> <span
class="methodname">gnupg\_import</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$keydata`</span> )

Imports the key `keydata` and returns an array with information about
the importprocess.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`keydata`  
The data key that is being imported.

### Return Values

On success, this function returns and info-array about the
importprocess. On failure, this function returns **`FALSE`**.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_import</span>
example**

``` php
<?php
$res = gnupg_init();
$info = gnupg_import($res,$keydata);
print_r($info);
?>
```

**Example \#2 OO <span class="function">gnupg\_import</span> example**

``` php
<?php
$gpg = new gnupg();
$info = $gpg -> import($keydata);
print_r($info);
?>
```

gnupg\_init
===========

Initialize a connection

### Description

<span class="type">resource</span> <span
class="methodname">gnupg\_init</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

### Return Values

A GnuPG <span class="type">resource</span> connection used by other
GnuPG functions.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_init</span>
example**

``` php
<?php
$res = gnupg_init();
?>
```

**Example \#2 OO gnupg initializer example**

``` php
<?php
$gpg = new gnupg();
?>
```

gnupg\_keyinfo
==============

Returns an array with information about all keys that matches the given
pattern

### Description

<span class="type">array</span> <span
class="methodname">gnupg\_keyinfo</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$pattern`</span> )

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`pattern`  
The pattern being checked against the keys.

### Return Values

Returns an array with information about all keys that matches the given
pattern or **`FALSE`**, if an error has occurred.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_keyinfo</span>
example**

``` php
<?php
$res = gnupg_init();
$info = gnupg_keyinfo($res, 'test');
print_r($info);
?>
```

**Example \#2 OO <span class="function">gnupg\_keyinfo</span> example**

``` php
<?php
$gpg = new gnupg();
$info = $gpg -> keyinfo("test");
print_r($info);
?>
```

gnupg\_setarmor
===============

Toggle armored output

### Description

<span class="type">bool</span> <span
class="methodname">gnupg\_setarmor</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">int</span> `$armor`</span> )

Toggle the armored output.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`armor`  
Pass a non-zero integer-value to this function to enable armored-output
(default). Pass 0 to disable armored output.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_setarmor</span>
example**

``` php
<?php
$res = gnupg_init();
gnupg_setarmor($res,1); // enable armored output;
gnupg_setarmor($res,0); // disable armored output;
?>
```

**Example \#2 OO <span class="function">gnupg\_setarmor</span> example**

``` php
<?php
$gpg = new gnupg();
$gpg -> setarmor(1); // enable armored output;
$gpg -> setarmor(0); // disable armored output;
?>
```

gnupg\_seterrormode
===================

Sets the mode for error\_reporting

### Description

<span class="type">void</span> <span
class="methodname">gnupg\_seterrormode</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">int</span> `$errormode`</span> )

Sets the mode for
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`errormode`  
The error mode.

`errormode` takes a constant indicating what type of error\_reporting
should be used. The possible values are **`GNUPG_ERROR_WARNING`**,
**`GNUPG_ERROR_EXCEPTION`** and **`GNUPG_ERROR_SILENT`**. By default
**`GNUPG_ERROR_SILENT`** is used.

### Return Values

No value is returned.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_seterrormode</span> example**

``` php
<?php
$res = gnupg_init();
gnupg_seterrormode($res,GNUPG_ERROR_WARNING); // raise a PHP-Warning in case of an error
?>
```

**Example \#2 OO <span class="function">gnupg\_seterrormode</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> seterrormode(gnupg::ERROR_EXCEPTION); // throw an exception in case of an error
?>
```

gnupg\_setsignmode
==================

Sets the mode for signing

### Description

<span class="type">bool</span> <span
class="methodname">gnupg\_setsignmode</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">int</span> `$signmode`</span> )

Sets the mode for signing.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`sigmode`  
The mode for signing.

`signmode` takes a constant indicating what type of signature should be
produced. The possible values are **`GNUPG_SIG_MODE_NORMAL`**,
**`GNUPG_SIG_MODE_DETACH`** and **`GNUPG_SIG_MODE_CLEAR`**. By default
**`GNUPG_SIG_MODE_CLEAR`** is used.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Procedural <span
class="function">gnupg\_setsignmode</span> example**

``` php
<?php
$res = gnupg_init();
gnupg_setsignmode($res,GNUPG_SIG_MODE_DETACH); // produce a detached signature
?>
```

**Example \#2 OO <span class="function">gnupg\_setsignmode</span>
example**

``` php
<?php
$gpg = new gnupg();
$gpg -> setsignmode(gnupg::SIG_MODE_DETACH); // produce a detached signature
?>
```

gnupg\_sign
===========

Signs a given text

### Description

<span class="type">string</span> <span
class="methodname">gnupg\_sign</span> ( <span class="methodparam"><span
class="type">resource</span> `$identifier`</span> , <span
class="methodparam"><span class="type">string</span> `$plaintext`</span>
)

Signs the given `plaintext` with the keys, which were set with
<a href="/ref/gnupg.html#gnupg_addsignkey" class="link">gnupg_addsignkey</a>
before and returns the signed text or the signature, depending on what
was set with
<a href="/ref/gnupg.html#gnupg_setsignmode" class="link">gnupg_setsignmode</a>.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`plaintext`  
The plain text being signed.

### Return Values

On success, this function returns the signed text or the signature. On
failure, this function returns **`FALSE`**.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_sign</span>
example**

``` php
<?php
$res = gnupg_init();
gnupg_addsignkey($res,"8660281B6051D071D94B5B230549F9DC851566DC","test");
$signed = gnupg_sign($res, "just a test");
echo $signed;
?>
```

**Example \#2 OO <span class="function">gnupg\_sign</span> example**

``` php
<?php
$gpg = new gnupg();
$gpg->addsignkey("8660281B6051D071D94B5B230549F9DC851566DC","test");
$signed = $gpg->sign("just a test");
echo $signed;
?>
```

gnupg\_verify
=============

Verifies a signed text

### Description

<span class="type">array</span> <span
class="methodname">gnupg\_verify</span> ( <span
class="methodparam"><span class="type">resource</span>
`$identifier`</span> , <span class="methodparam"><span
class="type">string</span> `$signed_text`</span> , <span
class="methodparam"><span class="type">string</span> `$signature`</span>
\[, <span class="methodparam"><span class="type">string</span>
`&$plaintext`</span> \] )

Verifies the given `signed_text` and returns information about the
signature.

### Parameters

`identifier`  
The gnupg identifier, from a call to <span
class="function">gnupg\_init</span> or <span
class="classname">gnupg</span>.

`signed_text`  
The signed text.

`signature`  
The signature. To verify a clearsigned text, set signature to
**`FALSE`**.

`plaintext`  
The plain text. If this optional parameter is passed, it is filled with
the plain text.

### Return Values

On success, this function returns information about the signature. On
failure, this function returns **`FALSE`**.

### Examples

**Example \#1 Procedural <span class="function">gnupg\_verify</span>
example**

``` php
<?php
$plaintext = "";
$res = gnupg_init();
// clearsigned
$info = gnupg_verify($res,$signed_text,false,$plaintext);
print_r($info);
// detached signature
$info = gnupg_verify($res,$signed_text,$signature);
print_r($info);
?>
```

**Example \#2 OO <span class="function">gnupg\_verify</span> example**

``` php
<?php
$plaintext = "";
$gpg = new gnupg();
// clearsigned
$info = $gpg -> verify($signed_text,false,$plaintext);
print_r($info);
// detached signature
$info = $gpg -> verify($signed_text,$signature);
print_r($info);
?>
```

**Table of Contents**

-   [gnupg\_adddecryptkey](/ref/gnupg.html#gnupg_adddecryptkey) — Add a
    key for decryption
-   [gnupg\_addencryptkey](/ref/gnupg.html#gnupg_addencryptkey) — Add a
    key for encryption
-   [gnupg\_addsignkey](/ref/gnupg.html#gnupg_addsignkey) — Add a key
    for signing
-   [gnupg\_cleardecryptkeys](/ref/gnupg.html#gnupg_cleardecryptkeys) —
    Removes all keys which were set for decryption before
-   [gnupg\_clearencryptkeys](/ref/gnupg.html#gnupg_clearencryptkeys) —
    Removes all keys which were set for encryption before
-   [gnupg\_clearsignkeys](/ref/gnupg.html#gnupg_clearsignkeys) —
    Removes all keys which were set for signing before
-   [gnupg\_decrypt](/ref/gnupg.html#gnupg_decrypt) — Decrypts a given
    text
-   [gnupg\_decryptverify](/ref/gnupg.html#gnupg_decryptverify) —
    Decrypts and verifies a given text
-   [gnupg\_encrypt](/ref/gnupg.html#gnupg_encrypt) — Encrypts a given
    text
-   [gnupg\_encryptsign](/ref/gnupg.html#gnupg_encryptsign) — Encrypts
    and signs a given text
-   [gnupg\_export](/ref/gnupg.html#gnupg_export) — Exports a key
-   [gnupg\_geterror](/ref/gnupg.html#gnupg_geterror) — Returns the
    errortext, if a function fails
-   [gnupg\_getprotocol](/ref/gnupg.html#gnupg_getprotocol) — Returns
    the currently active protocol for all operations
-   [gnupg\_import](/ref/gnupg.html#gnupg_import) — Imports a key
-   [gnupg\_init](/ref/gnupg.html#gnupg_init) — Initialize a connection
-   [gnupg\_keyinfo](/ref/gnupg.html#gnupg_keyinfo) — Returns an array
    with information about all keys that matches the given pattern
-   [gnupg\_setarmor](/ref/gnupg.html#gnupg_setarmor) — Toggle armored
    output
-   [gnupg\_seterrormode](/ref/gnupg.html#gnupg_seterrormode) — Sets the
    mode for error\_reporting
-   [gnupg\_setsignmode](/ref/gnupg.html#gnupg_setsignmode) — Sets the
    mode for signing
-   [gnupg\_sign](/ref/gnupg.html#gnupg_sign) — Signs a given text
-   [gnupg\_verify](/ref/gnupg.html#gnupg_verify) — Verifies a signed
    text

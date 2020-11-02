Predefined Constants
====================

**Table of Contents**

-   [Purpose checking
    flags](/openssl/constants.html#Purpose%20checking%20flags)
-   [Padding flags for asymmetric
    encryption](/openssl/constants.html#Padding%20flags%20for%20asymmetric%20encryption)
-   [Key types](/openssl/constants.html#Key%20types)
-   [PKCS7
    Flags/Constants](/openssl/constants.html#PKCS7%20Flags/Constants)
-   [Signature
    Algorithms](/openssl/constants.html#Signature%20Algorithms)
-   [Ciphers](/openssl/constants.html#Ciphers)
-   [Version constants](/openssl/constants.html#Version%20constants)
-   [Server Name Indication
    constants](/openssl/constants.html#Server%20Name%20Indication%20constants)
-   [Other Constants](/openssl/constants.html#Other%20Constants)

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

Purpose checking flags
----------------------

**`X509_PURPOSE_SSL_CLIENT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`X509_PURPOSE_SSL_SERVER`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`X509_PURPOSE_NS_SSL_SERVER`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`X509_PURPOSE_SMIME_SIGN`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`X509_PURPOSE_SMIME_ENCRYPT`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`X509_PURPOSE_CRL_SIGN`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`X509_PURPOSE_ANY`** (<span class="type">int</span>)  
<span class="simpara"> </span>

Padding flags for asymmetric encryption
---------------------------------------

**`OPENSSL_PKCS1_PADDING`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_SSLV23_PADDING`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_NO_PADDING`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_PKCS1_OAEP_PADDING`** (<span class="type">int</span>)  
<span class="simpara"> </span>

Key types
---------

**`OPENSSL_KEYTYPE_RSA`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_KEYTYPE_DSA`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_KEYTYPE_DH`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_KEYTYPE_EC`** (<span class="type">int</span>)  
<span class="simpara"> This constant is only available when PHP is
compiled with OpenSSL 0.9.8+. Added in PHP 5.2.0. </span>

PKCS7 Flags/Constants
---------------------

The S/MIME functions make use of flags which are specified using a
bitfield which can include one or more of the following values:

| Constant             | Description                                                                                                                                                                                                                                                                                                                                                                                           |
|----------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`PKCS7_TEXT`**     | Adds text/plain content type headers to encrypted/signed message. If decrypting or verifying, it strips those headers from the output - if the decrypted or verified message is not of MIME type text/plain then an error will occur.                                                                                                                                                                 |
| **`PKCS7_BINARY`**   | Normally the input message is converted to "canonical" format which is effectively using *CR* and *LF* as end of line: as required by the S/MIME specification. When this option is present, no translation occurs. This is useful when handling binary data which may not be in MIME format.                                                                                                         |
| **`PKCS7_NOINTERN`** | When verifying a message, certificates (if any) included in the message are normally searched for the signing certificate. With this option only the certificates specified in the `extracerts` parameter of <span class="function">openssl\_pkcs7\_verify</span> are used. The supplied certificates can still be used as untrusted CAs however.                                                     |
| **`PKCS7_NOVERIFY`** | Do not verify the signers certificate of a signed message.                                                                                                                                                                                                                                                                                                                                            |
| **`PKCS7_NOCHAIN`**  | Do not chain verification of signers certificates: that is don't use the certificates in the signed message as untrusted CAs.                                                                                                                                                                                                                                                                         |
| **`PKCS7_NOCERTS`**  | When signing a message the signer's certificate is normally included - with this option it is excluded. This will reduce the size of the signed message but the verifier must have a copy of the signers certificate available locally (passed using the `extracerts` to <span class="function">openssl\_pkcs7\_verify</span> for example).                                                           |
| **`PKCS7_NOATTR`**   | Normally when a message is signed, a set of attributes are included which include the signing time and the supported symmetric algorithms. With this option they are not included.                                                                                                                                                                                                                    |
| **`PKCS7_DETACHED`** | When signing a message, use cleartext signing with the MIME type *"multipart/signed"*. This is the default if you do not specify any `flags` to <span class="function">openssl\_pkcs7\_sign</span>. If you turn this option off, the message will be signed using opaque signing, which is more resistant to translation by mail relays but cannot be read by mail agents that do not support S/MIME. |
| **`PKCS7_NOSIGS`**   | Don't try and verify the signatures on a message                                                                                                                                                                                                                                                                                                                                                      |

Signature Algorithms
--------------------

**`OPENSSL_ALGO_DSS1`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_ALGO_SHA1`** (<span class="type">int</span>)  
<span class="simpara"> Used as default algorithm by <span
class="function">openssl\_sign</span> and <span
class="function">openssl\_verify</span>. </span>

**`OPENSSL_ALGO_SHA224`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.4.8. </span>

**`OPENSSL_ALGO_SHA256`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.4.8. </span>

**`OPENSSL_ALGO_SHA384`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.4.8. </span>

**`OPENSSL_ALGO_SHA512`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.4.8. </span>

**`OPENSSL_ALGO_RMD160`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.4.8. </span>

**`OPENSSL_ALGO_MD5`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_ALGO_MD4`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_ALGO_MD2`** (<span class="type">int</span>)  
<span class="simpara"> As of PHP 5.2.13 and PHP 5.3.2, this constant is
only available if PHP is compiled with MD2 support. This requires
passing in the -DHAVE\_OPENSSL\_MD2\_H CFLAG when compiling PHP, and
enable-md2 when compiling OpenSSL 1.0.0+. </span>

Ciphers
-------

**`OPENSSL_CIPHER_RC2_40`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_CIPHER_RC2_128`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_CIPHER_RC2_64`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_CIPHER_DES`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`OPENSSL_CIPHER_3DES`** (<span class="type">int</span>)  
<span class="simpara"> </span>

<!-- -->

**`OPENSSL_CIPHER_AES_128_CBC`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.4.0. </span>

**`OPENSSL_CIPHER_AES_192_CBC`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.4.0. </span>

**`OPENSSL_CIPHER_AES_256_CBC`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.4.0. </span>

Version constants
-----------------

**`OPENSSL_VERSION_TEXT`** (<span class="type">string</span>)  
<span class="simpara"> Added in PHP 5.2.0. </span>

**`OPENSSL_VERSION_NUMBER`** (<span class="type">int</span>)  
<span class="simpara"> Added in PHP 5.2.0. </span>

Server Name Indication constants
--------------------------------

**`OPENSSL_TLSEXT_SERVER_NAME`** (<span class="type">string</span>)  
<span class="simpara"> Whether SNI support is available or not. </span>

> **Note**:
>
> This constant was added in 5.3.2 and requires PHP to be built with
> OpenSSL 0.9.8j or greater.

Other Constants
---------------

**`OPENSSL_ZERO_PADDING`** (<span class="type">bool</span>)  
<span class="simpara"> By default encryption operations are padded using
standard block padding and the padding is checked and removed when
decrypting. If **`OPENSSL_ZERO_PADDING`** is set in the <span
class="function">openssl\_encrypt</span> or <span
class="function">openssl\_decrypt</span> `options` then no padding is
performed, the total amount of data encrypted or decrypted must then be
a multiple of the block size or an error will occur. </span>

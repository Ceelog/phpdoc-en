**Warning**

This feature was *DEPRECATED* in PHP 7.1.0, and *REMOVED* in PHP 7.2.0.

Alternatives to this feature include:

-   <a href="/book/sodium.html" class="link">Sodium</a> (available as of
    PHP 7.2.0)
-   <a href="/book/openssl.html" class="link">OpenSSL</a>

> **Note**:
>
> This extension has been moved to the
> <a href="https://pecl.php.net/" class="link external">» PECL</a>
> repository and is no longer bundled with PHP as of PHP 7.2.0.

This is an interface to the mcrypt library, which supports a wide
variety of block algorithms such as DES, TripleDES, Blowfish (default),
3-WAY, SAFER-SK64, SAFER-SK128, TWOFISH, TEA, RC2 and GOST in CBC, OFB,
CFB and ECB cipher modes. Additionally, it supports RC6 and IDEA which
are considered "non-free". CFB/OFB are 8bit by default.

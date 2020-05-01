Mcrypt ciphers
==============

Here is a list of ciphers which are currently supported by the mcrypt
extension. For a complete list of supported ciphers, see the defines at
the end of `mcrypt.h`. The general rule with the mcrypt-2.2.x API is
that you can access the cipher from PHP with MCRYPT\_ciphername. With
the libmcrypt-2.4.x and libmcrypt-2.5.x API these constants also work,
but it is possible to specify the name of the cipher as a string with a
call to <span class="function">mcrypt\_module\_open</span>.

-   <span class="simpara">MCRYPT\_3DES</span>
-   <span class="simpara">MCRYPT\_ARCFOUR\_IV (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_ARCFOUR (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_BLOWFISH</span>
-   <span class="simpara">MCRYPT\_CAST\_128</span>
-   <span class="simpara">MCRYPT\_CAST\_256</span>
-   <span class="simpara">MCRYPT\_CRYPT</span>
-   <span class="simpara">MCRYPT\_DES</span>
-   <span class="simpara">MCRYPT\_DES\_COMPAT (libmcrypt 2.2.x
    only)</span>
-   <span class="simpara">MCRYPT\_ENIGMA (libmcrypt \> 2.4.x only, alias
    for MCRYPT\_CRYPT)</span>
-   <span class="simpara">MCRYPT\_GOST</span>
-   <span class="simpara">MCRYPT\_IDEA (non-free)</span>
-   <span class="simpara">MCRYPT\_LOKI97 (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_MARS (libmcrypt \> 2.4.x only,
    non-free)</span>
-   <span class="simpara">MCRYPT\_PANAMA (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_RIJNDAEL\_128 (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_RIJNDAEL\_192 (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_RIJNDAEL\_256 (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_RC2</span>
-   <span class="simpara">MCRYPT\_RC4 (libmcrypt 2.2.x only)</span>
-   <span class="simpara">MCRYPT\_RC6 (libmcrypt \> 2.4.x only)</span>
-   <span class="simpara">MCRYPT\_RC6\_128 (libmcrypt 2.2.x only)</span>
-   <span class="simpara">MCRYPT\_RC6\_192 (libmcrypt 2.2.x only)</span>
-   <span class="simpara">MCRYPT\_RC6\_256 (libmcrypt 2.2.x only)</span>
-   <span class="simpara">MCRYPT\_SAFER64</span>
-   <span class="simpara">MCRYPT\_SAFER128</span>
-   <span class="simpara">MCRYPT\_SAFERPLUS (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_SERPENT(libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_SERPENT\_128 (libmcrypt 2.2.x
    only)</span>
-   <span class="simpara">MCRYPT\_SERPENT\_192 (libmcrypt 2.2.x
    only)</span>
-   <span class="simpara">MCRYPT\_SERPENT\_256 (libmcrypt 2.2.x
    only)</span>
-   <span class="simpara">MCRYPT\_SKIPJACK (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_TEAN (libmcrypt 2.2.x only)</span>
-   <span class="simpara">MCRYPT\_THREEWAY</span>
-   <span class="simpara">MCRYPT\_TRIPLEDES (libmcrypt \> 2.4.x
    only)</span>
-   <span class="simpara">MCRYPT\_TWOFISH (for older mcrypt 2.x
    versions, or mcrypt \> 2.4.x )</span>
-   <span class="simpara">MCRYPT\_TWOFISH128 (TWOFISHxxx are available
    in newer 2.x versions, but not in the 2.4.x versions)</span>
-   <span class="simpara">MCRYPT\_TWOFISH192</span>
-   <span class="simpara">MCRYPT\_TWOFISH256</span>
-   <span class="simpara">MCRYPT\_WAKE (libmcrypt \> 2.4.x only)</span>
-   <span class="simpara">MCRYPT\_XTEA (libmcrypt \> 2.4.x only)</span>

You must (in **`CFB`** and **`OFB`** mode) or can (in **`CBC`** mode)
supply an initialization vector (IV) to the respective cipher function.
The IV must be unique and must be the same when decrypting/encrypting.
With data which is stored encrypted, you can take the output of a
function of the index under which the data is stored (e.g. the MD5 key
of the filename). Alternatively, you can transmit the IV together with
the encrypted data (see chapter 9.3 of Applied Cryptography by Schneier
(ISBN 0-471-11709-9) for a discussion of this topic).

Examples
========

Mcrypt can be used to encrypt and decrypt using the above mentioned
ciphers. If you linked against *libmcrypt-2.2.x*, the four important
mcrypt commands (<span class="function">mcrypt\_cfb</span>, <span
class="function">mcrypt\_cbc</span>, <span
class="function">mcrypt\_ecb</span>, and <span
class="function">mcrypt\_ofb</span>) can operate in both modes which are
named **`MCRYPT_ENCRYPT`** and **`MCRYPT_DECRYPT`**, respectively.

If you linked against libmcrypt 2.4.x or 2.5.x, these functions are
still available, but it is recommended that you use the advanced
functions.

**Example \#1 Encrypt an input value with *AES* with a 256-bit key under
2.4.x and higher in *CBC* mode**

``` php
<?php
    $key = hash('sha256', 'this is a secret key', true);
    $input = "Let us meet at 9 o'clock at the secret place.";
    
    $td = mcrypt_module_open('rijndael-128', '', 'cbc', '');
    $iv = mcrypt_create_iv(mcrypt_enc_get_iv_size($td), MCRYPT_DEV_URANDOM);
    mcrypt_generic_init($td, $key, $iv);
    $encrypted_data = mcrypt_generic($td, $input);
    mcrypt_generic_deinit($td);
    mcrypt_module_close($td);
?>
```

This example will give you the encrypted data as a string in
*$encrypted\_data*. For a full example see <span
class="function">mcrypt\_module\_open</span>.

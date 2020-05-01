Examples
========

**Table of Contents**

-   [Clearsign text](/gnupg/examples.html#Clearsign%20text)

Clearsign text
--------------

This example will clearsign a given text.

**Example \#1 gnupg clearsign example (procedural)**

``` php
<?php
// init gnupg
$res = gnupg_init();
// not really needed. Clearsign is default
gnupg_setsignmode($res,GNUPG_SIG_MODE_CLEAR);
// add key with passphrase 'test' for signing
gnupg_addsignkey($res,"8660281B6051D071D94B5B230549F9DC851566DC","test");
// sign
$signed = gnupg_sign($res,"just a test");
echo $signed;
?>
```

**Example \#2 gnupg clearsign example (OO)**

``` php
<?php
// new class
$gnupg = new gnupg();
// not really needed. Clearsign is default
$gnupg->setsignmode(gnupg::SIG_MODE_CLEAR);
// add key with passphrase 'test' for signing
$gnupg->addsignkey("8660281B6051D071D94B5B230549F9DC851566DC","test");
// sign
$signed = $gnupg->sign("just a test");
echo $signed;
?>
```

**Example \#3 keylistiterator**

This extension also comes with an Iterator for your keyring.

``` php
<?php
// create a new iterator for listing all public keys that matches 'example'
$iterator = new gnupg_keylistiterator("example");
foreach($iterator as $fingerprint => $userid){
    echo $fingerprint." -> ".$userid."\n";
}
?>
```

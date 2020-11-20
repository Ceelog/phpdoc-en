Encryption Filters
------------------

Encryption filters are especially useful for file/stream encryption.

mcrypt.\* and mdecrypt.\*
-------------------------

**Warning**

This feature has been *DEPRECATED* as of PHP 7.1.0. Relying on this
feature is highly discouraged.

*mcrypt.\** and *mdecrypt.\** provide symmetric encryption and
decryption using libmcrypt. Both sets of filters support the same
algorithms available to
<a href="/ref/mcrypt.html" class="link">mcrypt extension</a> in the form
of *mcrypt.ciphername* where `ciphername` is the name of the cipher as
it would be passed to <span
class="function">mcrypt\_module\_open</span>. The following five filter
parameters are also available:

| Parameter       | Required? | Default                            | Sample Values                                                  |
|-----------------|-----------|------------------------------------|----------------------------------------------------------------|
| mode            | Optional  | cbc                                | cbc, cfb, ecb, nofb, ofb, stream                               |
| algorithms\_dir | Optional  | ini\_get('mcrypt.algorithms\_dir') | Location of algorithms modules                                 |
| modes\_dir      | Optional  | ini\_get('mcrypt.modes\_dir')      | Location of modes modules                                      |
| iv              | Required  | N/A                                | Typically 8, 16, or 32 bytes of binary data. Depends on cipher |
| key             | Required  | N/A                                | Typically 8, 16, or 32 bytes of binary data. Depends on cipher |

**Example \#1 Encrypt/Decrypt with Blowfish**

``` php
<?php
//$key assumed to be previously generated
$iv_size = mcrypt_get_iv_size(MCRYPT_BLOWFISH, MCRYPT_MODE_CBC);
$iv = mcrypt_create_iv($iv_size, MCRYPT_DEV_URANDOM);
$fp = fopen('encrypted-file.enc', 'wb');
fwrite($fp, $iv);
$opts = array('mode'=>'cbc','iv'=>$iv, 'key'=>$key);
stream_filter_append($fp, 'mcrypt.blowfish', STREAM_FILTER_WRITE, $opts);
fwrite($fp, 'message to encrypt');
fclose($fp);

//decrypt...
$fp = fopen('encrypted-file.enc', 'rb');
$iv = fread($fp, $iv_size = mcrypt_get_iv_size(MCRYPT_BLOWFISH, MCRYPT_MODE_CBC));
$opts = array('mode'=>'cbc','iv'=>$iv, 'key'=>$key)
stream_filter_append($fp, 'mdecrypt.blowfish', STREAM_FILTER_READ, $opts);
$data = rtrim(stream_get_contents($fp));//trims off null padding
fclose($fp);
echo $data;
?>
```

**Example \#2 Encrypt file using AES-128 CBC with SHA256 HMAC**

``` php
<?php
AES_CBC::encryptFile($password, "plaintext.txt", "encrypted.enc");
AES_CBC::decryptFile($password, "encrypted.enc", "decrypted.txt");

class AES_CBC
{
   protected static $KEY_SIZES = array('AES-128'=>16,'AES-192'=>24,'AES-256'=>32);
   protected static function key_size() { return self::$KEY_SIZES['AES-128']; } //default AES-128
   public static function encryptFile($password, $input_stream, $aes_filename){
      $iv_size = mcrypt_get_iv_size(MCRYPT_RIJNDAEL_128, MCRYPT_MODE_CBC);
      $fin = fopen($input_stream, "rb");
      $fc = fopen($aes_filename, "wb+");
      if (!empty($fin) && !empty($fc)) {
         fwrite($fc, str_repeat("_", 32) );//placeholder, SHA256 HMAC will go here later
         fwrite($fc, $hmac_salt = mcrypt_create_iv($iv_size, MCRYPT_DEV_URANDOM));
         fwrite($fc, $esalt = mcrypt_create_iv($iv_size, MCRYPT_DEV_URANDOM));
         fwrite($fc, $iv = mcrypt_create_iv($iv_size, MCRYPT_DEV_URANDOM));
         $ekey = hash_pbkdf2("sha256", $password, $esalt, $it=1000, self::key_size(), $raw=true);
         $opts = array('mode'=>'cbc', 'iv'=>$iv, 'key'=>$ekey);
         stream_filter_append($fc, 'mcrypt.rijndael-128', STREAM_FILTER_WRITE, $opts);
         $infilesize = 0;
         while (!feof($fin)) {
            $block = fread($fin, 8192);
            $infilesize+=strlen($block);
            fwrite($fc, $block);
         }
         $block_size = mcrypt_get_block_size(MCRYPT_RIJNDAEL_128, MCRYPT_MODE_CBC);
         $padding = $block_size - ($infilesize % $block_size);//$padding is a number from 1-16
         fwrite($fc, str_repeat(chr($padding), $padding) );//perform PKCS7 padding
         fclose($fin);
         fclose($fc);
         $hmac_raw = self::calculate_hmac_after_32bytes($password, $hmac_salt, $aes_filename);
         $fc = fopen($aes_filename, "rb+");
         fwrite($fc, $hmac_raw);//overwrite placeholder
         fclose($fc);
      }
   }
   public static function decryptFile($password, $aes_filename, $out_stream) {
      $iv_size = mcrypt_get_iv_size(MCRYPT_RIJNDAEL_128, MCRYPT_MODE_CBC);
      $hmac_raw = file_get_contents($aes_filename, false, NULL,  0, 32);
      $hmac_salt = file_get_contents($aes_filename, false, NULL, 32, $iv_size);
      $hmac_calc = self::calculate_hmac_after_32bytes($password, $hmac_salt, $aes_filename);
      $fc = fopen($aes_filename, "rb");
      $fout = fopen($out_stream, 'wb');
      if (!empty($fout) && !empty($fc) && self::hash_equals($hmac_raw,$hmac_calc)) {
         fread($fc, 32+$iv_size);//skip sha256 hmac and salt
         $esalt = fread($fc, $iv_size);
         $iv    = fread($fc, $iv_size);
         $ekey = hash_pbkdf2("sha256", $password, $esalt, $it=1000, self::key_size(), $raw=true);
         $opts = array('mode'=>'cbc', 'iv'=>$iv, 'key'=>$ekey);
         stream_filter_append($fc, 'mdecrypt.rijndael-128', STREAM_FILTER_READ, $opts);
         while (!feof($fc)) {
            $block = fread($fc, 8192);
            if (feof($fc)) {
               $padding = ord($block[strlen($block) - 1]);//assume PKCS7 padding
               $block = substr($block, 0, 0-$padding);
            }
            fwrite($fout, $block);
         }
         fclose($fout);
         fclose($fc);
      }
   }
   private static function hash_equals($str1, $str2) {
      if(strlen($str1) == strlen($str2)) {
         $res = $str1 ^ $str2;
         for($ret=0,$i = strlen($res) - 1; $i >= 0; $i--) $ret |= ord($res[$i]);
         return !$ret;
      }
      return false;
   }
   private static function calculate_hmac_after_32bytes($password, $hsalt, $filename) {
      static $init=0;
      $init or $init = stream_filter_register("user-filter.skipfirst32bytes", "FileSkip32Bytes");
      $stream = 'php://filter/read=user-filter.skipfirst32bytes/resource=' . $filename;
      $hkey = hash_pbkdf2("sha256", $password, $hsalt, $iterations=1000, 24, $raw=true);
      return hash_hmac_file('sha256', $stream, $hkey, $raw=true);
   }
}
class FileSkip32Bytes extends php_user_filter
{
   private $skipped=0;
   function filter($in, $out, &$consumed, $closing)  {
      while ($bucket = stream_bucket_make_writeable($in)) {
         $outlen = $bucket->datalen;
         if ($this->skipped<32){
            $outlen = min($bucket->datalen,32-$this->skipped);
            $bucket->data = substr($bucket->data, $outlen);
            $bucket->datalen = $bucket->datalen-$outlen;
            $this->skipped+=$outlen;
         }
         $consumed += $outlen;
         stream_bucket_append($out, $bucket);
      }
      return PSFS_PASS_ON;
   }
}
class AES_128_CBC extends AES_CBC {
   protected static function key_size() { return self::$KEY_SIZES['AES-128']; }
}
class AES_192_CBC extends AES_CBC {
   protected static function key_size() { return self::$KEY_SIZES['AES-192']; }
}
class AES_256_CBC extends AES_CBC {
   protected static function key_size() { return self::$KEY_SIZES['AES-256']; }
}
```

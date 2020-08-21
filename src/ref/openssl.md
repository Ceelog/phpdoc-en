openssl\_cipher\_iv\_length
===========================

Gets the cipher iv length

### Description

<span class="type">int</span> <span
class="methodname">openssl\_cipher\_iv\_length</span> ( <span
class="methodparam"><span class="type">string</span> `$method`</span> )

Gets the cipher initialization vector (iv) length.

### Parameters

`method`  
The cipher method, see <span
class="function">openssl\_get\_cipher\_methods</span> for a list of
potential values.

### Return Values

Returns the cipher length on success, or **`FALSE`** on failure.

### Errors/Exceptions

Emits an **`E_WARNING`** level error when the cipher algorithm is
unknown.

### Examples

**Example \#1 <span class="function">openssl\_cipher\_iv\_length</span>
example**

``` php
<?php
$method = 'AES-128-CBC';
$ivlen = openssl_cipher_iv_length($method);

echo $ivlen;
?>
```

The above example will output something similar to:

    16

openssl\_csr\_export\_to\_file
==============================

Exports a CSR to a file

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_csr\_export\_to\_file</span> ( <span
class="methodparam"><span class="type">mixed</span> `$csr`</span> ,
<span class="methodparam"><span class="type">string</span>
`$outfilename`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$notext`<span class="initializer"> =
**`TRUE`**</span></span> \] )

<span class="function">openssl\_csr\_export\_to\_file</span> takes the
Certificate Signing Request represented by `csr` and saves it in PEM
format into the file named by `outfilename`.

### Parameters

`csr`  
See <a href="/openssl/certparams.html" class="link">CSR parameters</a>
for a list of valid values.

`outfilename`  
Path to the output file.

`notext`  
The optional parameter `notext` affects the verbosity of the output; if
it is **`FALSE`**, then additional human-readable information is
included in the output. The default value of `notext` is **`TRUE`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 openssl\_csr\_export\_to\_file() example**

``` php
<?php
$subject = array(
    "commonName" => "example.com",
);
$private_key = openssl_pkey_new(array(
    "private_key_bits" => 2048,
    "private_key_type" => OPENSSL_KEYTYPE_RSA,
));
$csr = openssl_csr_new($subject, $private_key, array('digest_alg' => 'sha384') );
openssl_pkey_export_to_file($private_key, 'example-priv.key');
// Along with the subject, the CSR contains the public key corresponding to the private key
openssl_csr_export_to_file($csr, 'example-csr.pem');
?>
```

### See Also

-   <span class="function">openssl\_csr\_export</span>
-   <span class="function">openssl\_csr\_new</span>
-   <span class="function">openssl\_csr\_sign</span>

openssl\_csr\_export
====================

Exports a CSR as a string

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_csr\_export</span> ( <span
class="methodparam"><span class="type">mixed</span> `$csr`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$out`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$notext`<span class="initializer"> =
**`TRUE`**</span></span> \] )

<span class="function">openssl\_csr\_export</span> takes the Certificate
Signing Request represented by `csr` and stores it in PEM format in
`out`, which is passed by reference.

### Parameters

`csr`  
See <a href="/openssl/certparams.html" class="link">CSR parameters</a>
for a list of valid values.

`out`  
on success, this string will contain the PEM encoded CSR

`notext`  
The optional parameter `notext` affects the verbosity of the output; if
it is **`FALSE`**, then additional human-readable information is
included in the output. The default value of `notext` is **`TRUE`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 openssl\_csr\_export() example**

``` php
<?php
$subject = array(
    "commonName" => "example.com",
);
$private_key = openssl_pkey_new(array(
    "private_key_bits" => 2048,
    "private_key_type" => OPENSSL_KEYTYPE_RSA,
));
$configargs = array(
    'digest_alg' => 'sha256WithRSAEncryption'
);
$csr = openssl_csr_new($subject, $private_key, $configargs);
openssl_csr_export($csr, $csr_string);
echo $csr_string;
?>
```

### See Also

-   <span class="function">openssl\_csr\_export\_to\_file</span>
-   <span class="function">openssl\_csr\_new</span>
-   <span class="function">openssl\_csr\_sign</span>

openssl\_csr\_get\_public\_key
==============================

Returns the public key of a CSR

### Description

<span class="type">resource</span> <span
class="methodname">openssl\_csr\_get\_public\_key</span> ( <span
class="methodparam"><span class="type">mixed</span> `$csr`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$use_shortnames`<span class="initializer"> = **`TRUE`**</span></span>
\] )

<span class="function">openssl\_csr\_get\_public\_key</span> extracts
the public key from `csr` and prepares it for use by other functions.

### Parameters

`csr`  
See <a href="/openssl/certparams.html" class="link">CSR parameters</a>
for a list of valid values.

`use_shortnames`  
**Warning**
This parameter is ignored

### Return Values

Returns a positive key resource identifier on success, or FALSE on
error.

### Examples

**Example \#1 openssl\_csr\_get\_public\_key() example**

``` php
<?php
$subject = array(
    "commonName" => "example.com",
);
$private_key = openssl_pkey_new(array(
    "private_key_bits" => 2048,
    "private_key_type" => OPENSSL_KEYTYPE_RSA,
));
$csr = openssl_csr_new($subject, $private_key, array('digest_alg' => 'sha256') );
$public_key = openssl_csr_get_public_key($csr);
$info = openssl_pkey_get_details($public_key);
echo $info['key'];
?>
```

### See Also

-   <span class="function">openssl\_csr\_get\_subject</span>
-   <span class="function">openssl\_csr\_new</span>
-   <span class="function">openssl\_pkey\_get\_details</span>
-   <span class="function">openssl\_pkey\_export\_to\_file</span>
-   <span class="function">openssl\_pkey\_export</span>

openssl\_csr\_get\_subject
==========================

Returns the subject of a CSR

### Description

<span class="type">array</span> <span
class="methodname">openssl\_csr\_get\_subject</span> ( <span
class="methodparam"><span class="type">mixed</span> `$csr`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`$use_shortnames`<span class="initializer"> = **`TRUE`**</span></span>
\] )

<span class="function">openssl\_csr\_get\_subject</span> returns subject
distinguished name information encoded in the `csr` including fields
commonName (CN), organizationName (O), countryName (C) etc.

### Parameters

`csr`  
See <a href="/openssl/certparams.html" class="link">CSR parameters</a>
for a list of valid values.

`use_shortnames`  
`shortnames` controls how the data is indexed in the array - if
`shortnames` is **`TRUE`** (the default) then fields will be indexed
with the short name form, otherwise, the long name form will be used -
e.g.: CN is the shortname form of commonName.

### Return Values

Returns an associative array with subject description, or **`FALSE`** on
failure.

### Examples

**Example \#1 openssl\_csr\_get\_subject() example**

``` php
<?php
$subject = array(
    "countryName" => "CA",
    "stateOrProvinceName" => "Alberta",
    "localityName" => "Calgary",
    "organizationName" => "XYZ Widgets Inc",
    "organizationalUnitName" => "PHP Documentation Team",
    "commonName" => "Wez Furlong",
    "emailAddress" => "wez@example.com",
);
$private_key = openssl_pkey_new(array(
    "private_key_bits" => 2048,
    "private_key_type" => OPENSSL_KEYTYPE_RSA,
));
$configargs = array(
    'digest_alg' => 'sha512WithRSAEncryption'
);
$csr = openssl_csr_new($subject, $privkey, $configargs);
print_r(openssl_csr_get_subject($csr));
?>
```

The above example will output something similar to:

    Array
    (
        [C] => CA
        [ST] => Alberta
        [L] => Calgary
        [O] => XYZ Widgets Inc
        [OU] => PHP Documentation Team
        [CN] => Wez Furlong
        [emailAddress] => wez@example.com
    )

### See Also

-   <span class="function">openssl\_csr\_new</span>
-   <span class="function">openssl\_csr\_get\_public\_key</span>
-   <span class="function">openssl\_x509\_parse</span>

openssl\_csr\_new
=================

Generates a CSR

### Description

<span class="type">mixed</span> <span
class="methodname">openssl\_csr\_new</span> ( <span
class="methodparam"><span class="type">array</span> `$dn`</span> , <span
class="methodparam"><span class="type">resource</span>
`&$privkey`</span> \[, <span class="methodparam"><span
class="type">array</span> `$configargs`</span> \[, <span
class="methodparam"><span class="type">array</span>
`$extraattribs`</span> \]\] )

<span class="function">openssl\_csr\_new</span> generates a new CSR
(Certificate Signing Request) based on the information provided by `dn`.

> **Note**: <span class="simpara"> You need to have a valid
> `openssl.cnf` installed for this function to operate correctly. See
> the notes under
> <a href="/openssl/setup.html#Installation" class="link">the installation section</a>
> for more information. </span>

### Parameters

`dn`  
The Distinguished Name or subject fields to be used in the certificate.

`privkey`  
`privkey` should be set to a private key that was previously generated
by <span class="function">openssl\_pkey\_new</span> (or otherwise
obtained from the other openssl\_pkey family of functions). The
corresponding public portion of the key will be used to sign the CSR.

`configargs`  
By default, the information in your system *openssl.conf* is used to
initialize the request; you can specify a configuration file section by
setting the *config\_section\_section* key of `configargs`. You can also
specify an alternative openssl configuration file by setting the value
of the *config* key to the path of the file you want to use. The
following keys, if present in `configargs` behave as their equivalents
in the *openssl.conf*, as listed in the table below.

| `configargs` key     | type                              | *openssl.conf* equivalent | description                                                                                                                                                                                                                 |
|----------------------|-----------------------------------|---------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| digest\_alg          | <span class="type">string</span>  | default\_md               | Digest method or signature hash, usually one of <span class="function">openssl\_get\_md\_methods</span>                                                                                                                     |
| x509\_extensions     | <span class="type">string</span>  | x509\_extensions          | Selects which extensions should be used when creating an x509 certificate                                                                                                                                                   |
| req\_extensions      | <span class="type">string</span>  | req\_extensions           | Selects which extensions should be used when creating a CSR                                                                                                                                                                 |
| private\_key\_bits   | <span class="type">integer</span> | default\_bits             | Specifies how many bits should be used to generate a private key                                                                                                                                                            |
| private\_key\_type   | <span class="type">integer</span> | none                      | Specifies the type of private key to create. This can be one of **`OPENSSL_KEYTYPE_DSA`**, **`OPENSSL_KEYTYPE_DH`**, **`OPENSSL_KEYTYPE_RSA`** or **`OPENSSL_KEYTYPE_EC`**. The default value is **`OPENSSL_KEYTYPE_RSA`**. |
| encrypt\_key         | <span class="type">boolean</span> | encrypt\_key              | Should an exported key (with passphrase) be encrypted?                                                                                                                                                                      |
| encrypt\_key\_cipher | <span class="type">integer</span> | none                      | One of <a href="/openssl/constants.html#Ciphers" class="link">cipher constants</a>.                                                                                                                                         |
| curve\_name          | <span class="type">string</span>  | none                      | One of <span class="function">openssl\_get\_curve\_names</span>.                                                                                                                                                            |
| config               | <span class="type">string</span>  | N/A                       | Path to your own alternative openssl.conf file.                                                                                                                                                                             |

`extraattribs`  
`extraattribs` is used to specify additional configuration options for
the CSR. Both `dn` and `extraattribs` are associative arrays whose keys
are converted to OIDs and applied to the relevant part of the request.

### Return Values

Returns the CSR or **`FALSE`** on failure.

### Changelog

| Version | Description                                   |
|---------|-----------------------------------------------|
| 7.1.0   | `configargs` now also supports *curve\_name*. |

### Examples

**Example \#1 Creating a self-signed certificate**

``` php
<?php
// for SSL server certificates the commonName is the domain name to be secured
// for S/MIME email certificates the commonName is the owner of the email address
// location and identification fields refer to the owner of domain or email subject to be secured
$dn = array(
    "countryName" => "GB",
    "stateOrProvinceName" => "Somerset",
    "localityName" => "Glastonbury",
    "organizationName" => "The Brain Room Limited",
    "organizationalUnitName" => "PHP Documentation Team",
    "commonName" => "Wez Furlong",
    "emailAddress" => "wez@example.com"
);

// Generate a new private (and public) key pair
$privkey = openssl_pkey_new(array(
    "private_key_bits" => 2048,
    "private_key_type" => OPENSSL_KEYTYPE_RSA,
));

// Generate a certificate signing request
$csr = openssl_csr_new($dn, $privkey, array('digest_alg' => 'sha256'));

// Generate a self-signed cert, valid for 365 days
$x509 = openssl_csr_sign($csr, null, $privkey, $days=365, array('digest_alg' => 'sha256'));

// Save your private key, CSR and self-signed cert for later use
openssl_csr_export($csr, $csrout) and var_dump($csrout);
openssl_x509_export($x509, $certout) and var_dump($certout);
openssl_pkey_export($privkey, $pkeyout, "mypassword") and var_dump($pkeyout);

// Show any errors that occurred here
while (($e = openssl_error_string()) !== false) {
    echo $e . "\n";
}
?>
```

**Example \#2 Creating a self-signed ECC certificate (as of PHP 7.1.0)**

``` php
<?php
$subject = array(
    "commonName" => "docs.php.net",
);

// Generate a new private (and public) key pair
$private_key = openssl_pkey_new(array(
    "private_key_type" => OPENSSL_KEYTYPE_EC,
    "curve_name" => 'prime256v1',
));

// Generate a certificate signing request
$csr = openssl_csr_new($subject, $private_key, array('digest_alg' => 'sha384'));

// Generate self-signed EC cert
$x509 = openssl_csr_sign($csr, null, $private_key, $days=365, array('digest_alg' => 'sha384'));
openssl_x509_export_to_file($x509, 'ecc-cert.pem');
openssl_pkey_export_to_file($private_key, 'ecc-private.key');
?>
```

### See Also

-   <span class="function">openssl\_csr\_sign</span>

openssl\_csr\_sign
==================

Sign a CSR with another certificate (or itself) and generate a
certificate

### Description

<span class="type">resource</span> <span
class="methodname">openssl\_csr\_sign</span> ( <span
class="methodparam"><span class="type">mixed</span> `$csr`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$cacert`</span> , <span class="methodparam"><span
class="type">mixed</span> `$priv_key`</span> , <span
class="methodparam"><span class="type">int</span> `$days`</span> \[,
<span class="methodparam"><span class="type">array</span>
`$configargs`</span> \[, <span class="methodparam"><span
class="type">int</span> `$serial`<span class="initializer"> =
0</span></span> \]\] )

<span class="function">openssl\_csr\_sign</span> generates an x509
certificate resource from the given CSR.

> **Note**: <span class="simpara"> You need to have a valid
> `openssl.cnf` installed for this function to operate correctly. See
> the notes under
> <a href="/openssl/setup.html#Installation" class="link">the installation section</a>
> for more information. </span>

### Parameters

`csr`  
A CSR previously generated by <span
class="function">openssl\_csr\_new</span>. It can also be the path to a
PEM encoded CSR when specified as `file://path/to/csr` or an exported
string generated by <span class="function">openssl\_csr\_export</span>.

`cacert`  
The generated certificate will be signed by `cacert`. If `cacert` is
**`NULL`**, the generated certificate will be a self-signed certificate.

`priv_key`  
`priv_key` is the private key that corresponds to `cacert`.

`days`  
`days` specifies the length of time for which the generated certificate
will be valid, in days.

`configargs`  
You can finetune the CSR signing by `configargs`. See <span
class="function">openssl\_csr\_new</span> for more information about
`configargs`.

`serial`  
An optional the serial number of issued certificate. If not specified it
will default to 0.

### Return Values

Returns an x509 certificate resource on success, **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">openssl\_csr\_sign</span> example -
signing a CSR (how to implement your own CA)**

``` php
<?php
// Let's assume that this script is set to receive a CSR that has
// been pasted into a textarea from another page
$csrdata = $_POST["CSR"];

// We will sign the request using our own "certificate authority"
// certificate.  You can use any certificate to sign another, but
// the process is worthless unless the signing certificate is trusted
// by the software/users that will deal with the newly signed certificate

// We need our CA cert and its private key
$cacert = "file://path/to/ca.crt";
$privkey = array("file://path/to/ca.key", "your_ca_key_passphrase");

$usercert = openssl_csr_sign($csrdata, $cacert, $privkey, 365, array('digest_alg'=>'sha256') );

// Now display the generated certificate so that the user can
// copy and paste it into their local configuration (such as a file
// to hold the certificate for their SSL server)
openssl_x509_export($usercert, $certout);
echo $certout;

// Show any errors that occurred here
while (($e = openssl_error_string()) !== false) {
    echo $e . "\n";
}
?>
```

openssl\_decrypt
================

Decrypts data

### Description

<span class="type">string</span> <span
class="methodname">openssl\_decrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`$method`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$iv`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$tag`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$aad`<span
class="initializer"> = ""</span></span> \]\]\]\] )

Takes a raw or base64 encoded string and decrypts it using a given
method and key.

### Parameters

`data`  
The encrypted message to be decrypted.

`method`  
The cipher method. For a list of available cipher methods, use <span
class="function">openssl\_get\_cipher\_methods</span>.

`key`  
The key.

`options`  
`options` can be one of **`OPENSSL_RAW_DATA`**,
**`OPENSSL_ZERO_PADDING`**.

`iv`  
A non-NULL Initialization Vector.

`tag`  
The authentication tag in AEAD cipher mode. If it is incorrect, the
authentication fails and the function returns **`FALSE`**.

**Caution**
The length of the `tag` is not checked by the function. It is the
caller's responsibility to ensure that the length of the tag matches the
length of the tag retrieved when <span
class="function">openssl\_encrypt</span> has been called. Otherwise the
decryption may succeed if the given tag only matches the start of the
proper tag.

`aad`  
Additional authentication data.

### Return Values

The decrypted string on success or **`FALSE`** on failure.

### Errors/Exceptions

Emits an **`E_WARNING`** level error if an unknown cipher algorithm is
passed via the `method` parameter.

Emits an **`E_WARNING`** level error if an empty value is passed in via
the `iv` parameter.

### Changelog

| Version | Description                                |
|---------|--------------------------------------------|
| 7.1.0   | The `tag` and `aad` parameters were added. |
| 5.4.0   | The `raw_output` was changed to `options`. |
| 5.3.3   | The `iv` parameter was added.              |

### See Also

-   <span class="function">openssl\_encrypt</span>

openssl\_dh\_compute\_key
=========================

Computes shared secret for public value of remote DH public key and
local DH key

### Description

<span class="type">string</span> <span
class="methodname">openssl\_dh\_compute\_key</span> ( <span
class="methodparam"><span class="type">string</span> `$pub_key`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$dh_key`</span> )

The shared secret returned by <span
class="function">openssl\_dh\_compute\_key</span> is often used as an
encryption key to secretly communicate with a remote party. This is
known as the Diffie-Hellman key exchange.

### Parameters

`pub_key`  
DH Public key of the remote party.

`dh_key`  
A local DH private key, corresponding to the public key to be shared
with the remote party.

### Return Values

Returns shared secret on success or **`FALSE`** on failure.

### Examples

**Example \#1 Compute a shared secret**

First generate a public/private DH keypair locally, and have the remote
party do the same. We need to use the *openssl* command-line utility.

``` shell
# generate private/public key keypair
openssl dhparam -out dhparam.pem 2048
openssl genpkey -paramfile dhparam.pem -out privatekey.pem

# extract public key only
openssl pkey -in privatekey.pem -pubout -out publickey.pem
```

Next, send your public key to the remote party. Use the *openssl pkey*
command to view the public key you will be sent from the remote party.

``` shell
openssl pkey -pubin -in remotepublickey.pem -text -noout
```

The above example will output something similar to:

    PKCS#3 DH Public-Key: (2048 bit)
        public-key:
            67:e5:e5:fa:e0:7b:0f:96:2c:dc:96:44:5f:50:02:
            9e:8d:c2:6c:04:68:b0:d1:1d:75:66:fc:63:f5:e3:
            42:30:b8:96:c1:45:cc:08:60:b4:21:3b:dd:ee:66:
            88:db:77:d9:1e:11:89:d4:5c:f2:7a:f2:f1:fe:1c:
            77:9d:6f:13:b8:b2:56:00:ef:cb:3b:60:79:74:02:
            98:f5:f9:8e:3e:b5:62:08:de:ca:8c:c3:40:4a:80:
            79:d5:43:06:17:a8:19:56:af:cc:95:5e:e2:32:2d:
            d2:14:7b:76:5a:9a:f1:3c:76:76:35:cc:7b:c1:a5:
            f4:39:e5:b6:ca:71:3f:7c:3f:97:e5:ab:86:c1:cd:
            0e:e6:ee:04:c9:e6:2d:80:7e:59:c0:49:eb:b6:64:
            4f:a8:f9:bb:a3:87:b3:3d:76:01:9e:2b:16:94:a4:
            37:30:fb:35:e2:63:be:23:90:b9:ef:3f:46:46:04:
            94:8f:60:79:7a:51:55:d6:1a:1d:f5:d9:7f:4a:3e:
            aa:ac:b0:d0:82:cc:c2:e0:94:e0:54:c1:17:83:0b:
            74:08:4d:5a:79:ae:ff:7f:1c:04:ab:23:39:4a:ae:
            87:83:55:43:ab:7a:7c:04:9d:20:80:bb:af:5f:16:
            a3:e3:20:b9:21:47:8c:f8:7f:a8:60:80:9e:61:77:
            36
     [...abbreviated...]

Use this public key as a parameter to <span
class="function">openssl\_dh\_compute\_key</span> in order to compute
the shared secret.

``` php
<?php
$remote_public_key = '67e5e5fae07b0f962cdc96445f50029e8dc26c0468b0d11d7566fc63f5e34230b896c145cc0860b4213bddee6688db77d91e1189d45cf27af2f1fe1c779d6f13b8b25600efcb3b6079740298f5f98e3eb56208deca8cc3404a8079d5430617a81956afcc955ee2322dd2147b765a9af13c767635cc7bc1a5f439e5b6ca713f7c3f97e5ab86c1cd0ee6ee04c9e62d807e59c049ebb6644fa8f9bba387b33d76019e2b1694a43730fb35e263be2390b9ef3f464604948f60797a5155d61a1df5d97f4a3eaaacb0d082ccc2e094e054c117830b74084d5a79aeff7f1c04ab23394aae87835543ab7a7c049d2080bbaf5f16a3e320b921478cf87fa860809e617736';

$local_priv_key = openssl_pkey_get_private('file://privatekey.pem');

$shared_secret = openssl_dh_compute_key(hex2bin($remote_public_key), $local_priv_key);
echo bin2hex($shared_secret)."\n";
?>
```

**Example \#2 Generate a DH public/private keypair in php**

First, generate the DH prime number

``` shell
openssl dhparam -out dhparam.pem 2048
openssl dh -in dhparam.pem -noout  -text
```

The above example will output something similar to:

        PKCS#3 DH Parameters: (2048 bit)
            prime:
                00:a3:25:1e:73:3f:44:b9:2b:ee:f4:9d:9f:37:6a:
                4b:fd:1d:bd:f4:af:da:c8:10:77:59:41:c6:5f:73:
                d2:88:29:39:cd:1c:5f:c3:9f:0f:22:d2:9c:20:c1:
                e4:c0:18:03:b8:b6:d8:da:ad:3b:39:a6:da:8e:fe:
                12:30:e9:03:5d:22:ba:ef:18:d2:7b:69:f9:5b:cb:
                78:c6:0c:8c:6b:f2:49:92:c2:49:e0:45:77:72:b3:
                55:36:30:f2:40:17:89:18:50:03:fa:2d:54:7a:7f:
                34:4c:73:32:b6:88:14:51:14:be:80:57:95:e6:a3:
                f6:51:ff:17:47:4f:15:d6:0e:6c:47:53:72:2c:2a:
                4c:21:cb:7d:f3:49:97:c9:47:5e:40:33:7b:99:52:
                7e:7a:f3:52:27:80:de:1b:26:6b:40:bb:14:11:0b:
                fb:e6:d8:2f:cf:a0:06:2f:96:b9:1c:0b:b4:cb:d3:
                a6:62:9c:48:67:f6:81:f2:c6:ff:45:03:0a:9d:67:
                9d:ce:27:d9:6b:48:5d:ca:fb:c2:5d:84:9b:8b:cb:
                40:c7:a4:0c:8a:6e:f4:ab:ba:b6:10:c3:b8:25:4d:
                cf:60:96:f4:db:e8:00:1c:58:47:7a:fb:51:86:d1:
                22:d7:4e:94:31:7a:d5:da:3d:53:de:da:bb:64:8d:
                62:6b
            generator: 2 (0x2)

Prime and generator values ares passed as p and g into <span
class="function">openssl\_pkey\_new</span>

``` php
<?php
$configargs = array();
$configargs['p'] = hex2bin('00a3251e733f44b92beef49d9f376a4bfd1dbdf4afdac810775941c65f73d2882939cd1c5fc39f0f22d29c20c1e4c01803b8b6d8daad3b39a6da8efe1230e9035d22baef18d27b69f95bcb78c60c8c6bf24992c249e0457772b3553630f2401789185003fa2d547a7f344c7332b688145114be805795e6a3f651ff17474f15d60e6c4753722c2a4c21cb7df34997c9475e40337b99527e7af3522780de1b266b40bb14110bfbe6d82fcfa0062f96b91c0bb4cbd3a6629c4867f681f2c6ff45030a9d679dce27d96b485dcafbc25d849b8bcb40c7a40c8a6ef4abbab610c3b8254dcf6096f4dbe8001c58477afb5186d122d74e94317ad5da3d53dedabb648d626b');
$configargs['g'] = hex2bin('02');
$private_key = openssl_pkey_new(array('dh' => $configargs));
openssl_pkey_export_to_file($private_key,'privatekey.pem',$passphrase='y0urp@s5phr@se');

$details = openssl_pkey_get_details($private_key);
$local_pub_key = $details['dh']['pub_key'];
echo bin2hex($local_pub_key)."\n";//you can send your public key to the remote party

$details = openssl_pkey_get_details(openssl_pkey_get_public("file://remotepublickey.pem"));
$remote_public_key = $details['dh']['pub_key'];
$shared_secret = openssl_dh_compute_key($remote_public_key, $private_key);
echo bin2hex($shared_secret)."\n";
?>
```

### See Also

-   <span class="function">openssl\_pkey\_new</span>
-   <span class="function">openssl\_pkey\_get\_details</span>
-   <span class="function">openssl\_pkey\_get\_private</span>
-   <span class="function">openssl\_pkey\_get\_public</span>

openssl\_digest
===============

Computes a digest

### Description

<span class="type">string</span> <span
class="methodname">openssl\_digest</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`$method`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$raw_output`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Computes a digest hash value for the given data using a given method,
and returns a raw or binhex encoded string.

### Parameters

`data`  
The data.

`method`  
The digest method to use, e.g. "sha256", see <span
class="function">openssl\_get\_md\_methods</span> for a list of
available digest methods.

`raw_output`  
Setting to **`TRUE`** will return as raw output data, otherwise the
return value is binhex encoded.

### Return Values

Returns the digested hash value on success or **`FALSE`** on failure.

### Errors/Exceptions

Emits an **`E_WARNING`** level error if an unknown signature algorithm
is passed via the `method` parameter.

### See Also

-   <span class="function">openssl\_get\_md\_methods</span>

openssl\_encrypt
================

Encrypts data

### Description

<span class="type">string</span> <span
class="methodname">openssl\_encrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`$method`</span> , <span class="methodparam"><span
class="type">string</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$options`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$iv`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">string</span> `&$tag`<span
class="initializer"> = NULL</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$aad`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$tag_length`<span
class="initializer"> = 16</span></span> \]\]\]\]\] )

Encrypts given data with given method and key, returns a raw or base64
encoded string

### Parameters

`data`  
The plaintext message data to be encrypted.

`method`  
The cipher method. For a list of available cipher methods, use <span
class="function">openssl\_get\_cipher\_methods</span>.

`key`  
The key.

`options`  
`options` is a bitwise disjunction of the flags **`OPENSSL_RAW_DATA`**
and **`OPENSSL_ZERO_PADDING`**.

`iv`  
A non-NULL Initialization Vector.

`tag`  
The authentication tag passed by reference when using AEAD cipher mode
(GCM or CCM).

`aad`  
Additional authentication data.

`tag_length`  
The length of the authentication `tag`. Its value can be between 4 and
16 for GCM mode.

### Return Values

Returns the encrypted string on success or **`FALSE`** on failure.

### Errors/Exceptions

Emits an **`E_WARNING`** level error if an unknown cipher algorithm is
passed in via the `method` parameter.

Emits an **`E_WARNING`** level error if an empty value is passed in via
the `iv` parameter.

### Changelog

| Version | Description                                              |
|---------|----------------------------------------------------------|
| 7.1.0   | The `tag`, `aad` and `tag_length` parameters were added. |
| 5.4.0   | The `raw_output` was changed to `options`.               |
| 5.3.3   | The `iv` parameter was added.                            |

### Examples

**Example \#1 AES Authenticated Encryption in GCM mode example for PHP
7.1+**

``` php
<?php
//$key should have been previously generated in a cryptographically safe way, like openssl_random_pseudo_bytes
$plaintext = "message to be encrypted";
$cipher = "aes-128-gcm";
if (in_array($cipher, openssl_get_cipher_methods()))
{
    $ivlen = openssl_cipher_iv_length($cipher);
    $iv = openssl_random_pseudo_bytes($ivlen);
    $ciphertext = openssl_encrypt($plaintext, $cipher, $key, $options=0, $iv, $tag);
    //store $cipher, $iv, and $tag for decryption later
    $original_plaintext = openssl_decrypt($ciphertext, $cipher, $key, $options=0, $iv, $tag);
    echo $original_plaintext."\n";
}
?>
```

**Example \#2 AES Authenticated Encryption example for PHP 5.6+**

``` php
<?php
//$key previously generated safely, ie: openssl_random_pseudo_bytes
$plaintext = "message to be encrypted";
$ivlen = openssl_cipher_iv_length($cipher="AES-128-CBC");
$iv = openssl_random_pseudo_bytes($ivlen);
$ciphertext_raw = openssl_encrypt($plaintext, $cipher, $key, $options=OPENSSL_RAW_DATA, $iv);
$hmac = hash_hmac('sha256', $ciphertext_raw, $key, $as_binary=true);
$ciphertext = base64_encode( $iv.$hmac.$ciphertext_raw );

//decrypt later....
$c = base64_decode($ciphertext);
$ivlen = openssl_cipher_iv_length($cipher="AES-128-CBC");
$iv = substr($c, 0, $ivlen);
$hmac = substr($c, $ivlen, $sha2len=32);
$ciphertext_raw = substr($c, $ivlen+$sha2len);
$original_plaintext = openssl_decrypt($ciphertext_raw, $cipher, $key, $options=OPENSSL_RAW_DATA, $iv);
$calcmac = hash_hmac('sha256', $ciphertext_raw, $key, $as_binary=true);
if (hash_equals($hmac, $calcmac))//PHP 5.6+ timing attack safe comparison
{
    echo $original_plaintext."\n";
}
?>
```

### See Also

-   <span class="function">openssl\_decrypt</span>

openssl\_error\_string
======================

Return openSSL error message

### Description

<span class="type">string</span> <span
class="methodname">openssl\_error\_string</span> ( <span
class="methodparam">void</span> )

<span class="function">openssl\_error\_string</span> returns the last
error from the openSSL library. Error messages are queued, so this
function should be called multiple times to collect all of the
information. The last error will be the most recent one.

### Return Values

Returns an error message string, or **`FALSE`** if there are no more
error messages to return.

### Examples

**Example \#1 <span class="function">openssl\_error\_string</span>
example**

``` php
<?php
// lets assume you just called an openssl function that failed
while ($msg = openssl_error_string())
    echo $msg . "<br />\n";
?>
```

openssl\_free\_key
==================

Free key resource

### Description

<span class="type">void</span> <span
class="methodname">openssl\_free\_key</span> ( <span
class="methodparam"><span class="type">resource</span>
`$key_identifier`</span> )

<span class="function">openssl\_free\_key</span> frees the key
associated with the specified `key_identifier` from memory.

### Parameters

`key_identifier`  

### Return Values

No value is returned.

openssl\_get\_cert\_locations
=============================

Retrieve the available certificate locations

### Description

<span class="type">array</span> <span
class="methodname">openssl\_get\_cert\_locations</span> ( <span
class="methodparam">void</span> )

<span class="function">openssl\_get\_cert\_locations</span> returns an
array with information about the available certificate locations that
will be searched for SSL certificates.

### Parameters

This function has no parameters.

### Return Values

Returns an array with the available certificate locations.

### Examples

**Example \#1 <span
class="function">openssl\_get\_cert\_locations</span> example**

``` php
<?php
var_dump(openssl_get_cert_locations());
?>
```

The above example will output:

    array(8) {
      ["default_cert_file"]=>
      string(21) "/usr/lib/ssl/cert.pem"
      ["default_cert_file_env"]=>
      string(13) "SSL_CERT_FILE"
      ["default_cert_dir"]=>
      string(18) "/usr/lib/ssl/certs"
      ["default_cert_dir_env"]=>
      string(12) "SSL_CERT_DIR"
      ["default_private_dir"]=>
      string(20) "/usr/lib/ssl/private"
      ["default_default_cert_area"]=>
      string(12) "/usr/lib/ssl"
      ["ini_cafile"]=>
      string(0) ""
      ["ini_capath"]=>
      string(0) ""
    }

openssl\_get\_cipher\_methods
=============================

Gets available cipher methods

### Description

<span class="type">array</span> <span
class="methodname">openssl\_get\_cipher\_methods</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$aliases`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Gets a list of available cipher methods.

### Parameters

`aliases`  
Set to **`TRUE`** if cipher aliases should be included within the
returned <span class="type">array</span>.

### Return Values

An <span class="type">array</span> of available cipher methods.

### Examples

**Example \#1 <span
class="function">openssl\_get\_cipher\_methods</span> example**

Shows how the available ciphers might look, and also which aliases might
be available.

``` php
<?php
$ciphers             = openssl_get_cipher_methods();
$ciphers_and_aliases = openssl_get_cipher_methods(true);
$cipher_aliases      = array_diff($ciphers_and_aliases, $ciphers);

//ECB mode should be avoided
$ciphers = array_filter( $ciphers, function($n) { return stripos($n,"ecb")===FALSE; } );

//At least as early as Aug 2016, Openssl declared the following weak: RC2, RC4, DES, 3DES, MD5 based
$ciphers = array_filter( $ciphers, function($c) { return stripos($c,"des")===FALSE; } );
$ciphers = array_filter( $ciphers, function($c) { return stripos($c,"rc2")===FALSE; } );
$ciphers = array_filter( $ciphers, function($c) { return stripos($c,"rc4")===FALSE; } );
$ciphers = array_filter( $ciphers, function($c) { return stripos($c,"md5")===FALSE; } );
$cipher_aliases = array_filter($cipher_aliases,function($c) { return stripos($c,"des")===FALSE; } );
$cipher_aliases = array_filter($cipher_aliases,function($c) { return stripos($c,"rc2")===FALSE; } );

print_r($ciphers);
print_r($cipher_aliases);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => AES-128-CBC
        [1] => AES-128-CFB
        [2] => AES-128-CFB1
        [3] => AES-128-CFB8
        [5] => AES-128-OFB
        [6] => AES-192-CBC
        [7] => AES-192-CFB
        [8] => AES-192-CFB1
        [9] => AES-192-CFB8
        [11] => AES-192-OFB
        [12] => AES-256-CBC
        [13] => AES-256-CFB
        [14] => AES-256-CFB1
        [15] => AES-256-CFB8
        [17] => AES-256-OFB
        [18] => BF-CBC
        [19] => BF-CFB
        [21] => BF-OFB
        [22] => CAST5-CBC
        [23] => CAST5-CFB
        [25] => CAST5-OFB
        [41] => IDEA-CBC
        [42] => IDEA-CFB
        [44] => IDEA-OFB
        [53] => aes-128-cbc
        [54] => aes-128-cfb
        [55] => aes-128-cfb1
        [56] => aes-128-cfb8
        [58] => aes-128-ofb
        [59] => aes-192-cbc
        [60] => aes-192-cfb
        [61] => aes-192-cfb1
        [62] => aes-192-cfb8
        [64] => aes-192-ofb
        [65] => aes-256-cbc
        [66] => aes-256-cfb
        [67] => aes-256-cfb1
        [68] => aes-256-cfb8
        [70] => aes-256-ofb
        [71] => bf-cbc
        [72] => bf-cfb
        [74] => bf-ofb
        [75] => cast5-cbc
        [76] => cast5-cfb
        [78] => cast5-ofb
        [94] => idea-cbc
        [95] => idea-cfb
        [97] => idea-ofb
    )
    Array
    (
        [18] => AES128
        [19] => AES192
        [20] => AES256
        [21] => BF
        [26] => CAST
        [27] => CAST-cbc
        [50] => IDEA
        [82] => aes128
        [83] => aes192
        [84] => aes256
        [85] => bf
        [90] => blowfish
        [91] => cast
        [92] => cast-cbc
        [115] => idea
    )

### See Also

-   <span class="function">openssl\_get\_md\_methods</span>

openssl\_get\_curve\_names
==========================

Gets list of available curve names for ECC

### Description

<span class="type">array</span> <span
class="methodname">openssl\_get\_curve\_names</span> ( <span
class="methodparam">void</span> )

Gets the list of available curve names for use in Elliptic curve
cryptography (ECC) for public/private key operations. The two most
widely standardized/supported curves are *prime256v1* (NIST P-256) and
*secp384r1* (NIST P-384).

| AES Symmetric Keysize (Bits) | RSA and DSA Keysize (Bits) | ECC Keysize (Bits) |
|------------------------------|----------------------------|--------------------|
| 80                           | 1024                       | 160                |
| 112                          | 2048                       | 224                |
| 128                          | 3072                       | 256                |
| 192                          | 7680                       | 384                |
| 256                          | 15360                      | 512                |

<a href="http://dx.doi.org/10.6028/NIST.SP.800-57pt1r4" class="link external">» NIST recommends using ECC curves with at least 256 bits</a>.

### Parameters

This function has no parameters.

### Return Values

An <span class="type">array</span> of available curve names.

### Examples

**Example \#1 <span class="function">openssl\_get\_curve\_names</span>
example**

``` php
<?php
$curve_names = openssl_get_curve_names();
print_r($curve_names);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => secp112r1
        [1] => secp112r2
        [2] => secp128r1
        [3] => secp128r2
        [4] => secp160k1
        [5] => secp160r1
        [6] => secp160r2
        [7] => secp192k1
        [8] => secp224k1
        [9] => secp224r1
        [10] => secp256k1
        [11] => secp384r1
        [12] => secp521r1
        [13] => prime192v1
        [14] => prime192v2
        [15] => prime192v3
        [16] => prime239v1
        [17] => prime239v2
        [18] => prime239v3
        [19] => prime256v1
        [20] => sect113r1
        [21] => sect113r2
        [22] => sect131r1
        [23] => sect131r2
        [24] => sect163k1
        [25] => sect163r1
        [26] => sect163r2
        [27] => sect193r1
        [28] => sect193r2
        [29] => sect233k1
        [30] => sect233r1
        [31] => sect239k1
        [32] => sect283k1
        [33] => sect283r1
        [34] => sect409k1
        [35] => sect409r1
        [36] => sect571k1
        [37] => sect571r1
        [38] => c2pnb163v1
        [39] => c2pnb163v2
        [40] => c2pnb163v3
        [41] => c2pnb176v1
        [42] => c2tnb191v1
        [43] => c2tnb191v2
        [44] => c2tnb191v3
        [45] => c2pnb208w1
        [46] => c2tnb239v1
        [47] => c2tnb239v2
        [48] => c2tnb239v3
        [49] => c2pnb272w1
        [50] => c2pnb304w1
        [51] => c2tnb359v1
        [52] => c2pnb368w1
        [53] => c2tnb431r1
        [54] => wap-wsg-idm-ecid-wtls1
        [55] => wap-wsg-idm-ecid-wtls3
        [56] => wap-wsg-idm-ecid-wtls4
        [57] => wap-wsg-idm-ecid-wtls5
        [58] => wap-wsg-idm-ecid-wtls6
        [59] => wap-wsg-idm-ecid-wtls7
        [60] => wap-wsg-idm-ecid-wtls8
        [61] => wap-wsg-idm-ecid-wtls9
        [62] => wap-wsg-idm-ecid-wtls10
        [63] => wap-wsg-idm-ecid-wtls11
        [64] => wap-wsg-idm-ecid-wtls12
        [65] => Oakley-EC2N-3
        [66] => Oakley-EC2N-4
        [67] => brainpoolP160r1
        [68] => brainpoolP160t1
        [69] => brainpoolP192r1
        [70] => brainpoolP192t1
        [71] => brainpoolP224r1
        [72] => brainpoolP224t1
        [73] => brainpoolP256r1
        [74] => brainpoolP256t1
        [75] => brainpoolP320r1
        [76] => brainpoolP320t1
        [77] => brainpoolP384r1
        [78] => brainpoolP384t1
        [79] => brainpoolP512r1
        [80] => brainpoolP512t1
    )

openssl\_get\_md\_methods
=========================

Gets available digest methods

### Description

<span class="type">array</span> <span
class="methodname">openssl\_get\_md\_methods</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$aliases`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Gets a list of available digest methods.

### Parameters

`aliases`  
Set to **`TRUE`** if digest aliases should be included within the
returned <span class="type">array</span>.

### Return Values

An <span class="type">array</span> of available digest methods.

### Examples

**Example \#1 <span class="function">openssl\_get\_md\_methods</span>
example**

Shows how the available digests might look, and also which aliases might
be available.

``` php
<?php
$digests             = openssl_get_md_methods();
$digests_and_aliases = openssl_get_md_methods(true);
$digest_aliases      = array_diff($digests_and_aliases, $digests);

print_r($digests);

print_r($digest_aliases);

?>
```

The above example will output something similar to:

    Array
    (
        [0] => DSA
        [1] => DSA-SHA
        [2] => MD2
        [3] => MD4
        [4] => MD5
        [5] => RIPEMD160
        [6] => SHA
        [7] => SHA1
        [8] => SHA224
        [9] => SHA256
        [10] => SHA384
        [11] => SHA512
        [12] => dsaEncryption
        [13] => dsaWithSHA
        [14] => ecdsa-with-SHA1
        [15] => md2
        [16] => md4
        [17] => md5
        [18] => ripemd160
        [19] => sha
        [20] => sha1
        [21] => sha224
        [22] => sha256
        [23] => sha384
        [24] => sha512
    )
    Array
    (
        [2] => DSA-SHA1
        [3] => DSA-SHA1-old
        [4] => DSS1
        [9] => RSA-MD2
        [10] => RSA-MD4
        [11] => RSA-MD5
        [12] => RSA-RIPEMD160
        [13] => RSA-SHA
        [14] => RSA-SHA1
        [15] => RSA-SHA1-2
        [16] => RSA-SHA224
        [17] => RSA-SHA256
        [18] => RSA-SHA384
        [19] => RSA-SHA512
        [28] => dsaWithSHA1
        [29] => dss1
        [32] => md2WithRSAEncryption
        [34] => md4WithRSAEncryption
        [36] => md5WithRSAEncryption
        [37] => ripemd
        [39] => ripemd160WithRSA
        [40] => rmd160
        [43] => sha1WithRSAEncryption
        [45] => sha224WithRSAEncryption
        [47] => sha256WithRSAEncryption
        [49] => sha384WithRSAEncryption
        [51] => sha512WithRSAEncryption
        [52] => shaWithRSAEncryption
        [53] => ssl2-md5
        [54] => ssl3-md5
        [55] => ssl3-sha1
    )

### See Also

-   <span class="function">openssl\_digest</span>
-   <span class="function">openssl\_get\_cipher\_methods</span>

openssl\_get\_privatekey
========================

Alias of <span class="function">openssl\_pkey\_get\_private</span>

### Description

This function is an alias of: <span
class="function">openssl\_pkey\_get\_private</span>.

openssl\_get\_publickey
=======================

Alias of <span class="function">openssl\_pkey\_get\_public</span>

### Description

This function is an alias of: <span
class="function">openssl\_pkey\_get\_public</span>.

openssl\_open
=============

Open sealed data

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_open</span> ( <span
class="methodparam"><span class="type">string</span>
`$sealed_data`</span> , <span class="methodparam"><span
class="type">string</span> `&$open_data`</span> , <span
class="methodparam"><span class="type">string</span> `$env_key`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$priv_key_id`</span> \[, <span class="methodparam"><span
class="type">string</span> `$method`<span class="initializer"> =
"RC4"</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$iv`</span> \]\] )

<span class="function">openssl\_open</span> opens (decrypts)
`sealed_data` using the private key associated with the key identifier
`priv_key_id` and the envelope key `env_key`, and fills `open_data` with
the decrypted data. The envelope key is generated when the data are
sealed and can only be used by one specific private key. See <span
class="function">openssl\_seal</span> for more information.

### Parameters

`sealed_data`  

`open_data`  
If the call is successful the opened data is returned in this parameter.

`env_key`  

`priv_key_id`  

`method`  
The cipher method.

`iv`  
The initialization vector.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                  |
|---------|------------------------------|
| 7.0.0   | The `iv` has been added.     |
| 5.3.0   | The `method` has been added. |

### Examples

**Example \#1 <span class="function">openssl\_open</span> example**

``` php
<?php
// $sealed and $env_key are assumed to contain the sealed data
// and our envelope key, both given to us by the sealer.

// fetch private key from file and ready it
$fp = fopen("/src/openssl-0.9.6/demos/sign/key.pem", "r");
$priv_key = fread($fp, 8192);
fclose($fp);
$pkeyid = openssl_get_privatekey($priv_key);

// decrypt the data and store it in $open
if (openssl_open($sealed, $open, $env_key, $pkeyid)) {
    echo "here is the opened data: ", $open;
} else {
    echo "failed to open data";
}

// free the private key from memory
openssl_free_key($pkeyid);
?>
```

### See Also

-   <span class="function">openssl\_seal</span>

openssl\_pbkdf2
===============

Generates a PKCS5 v2 PBKDF2 string

### Description

<span class="type">string</span> <span
class="methodname">openssl\_pbkdf2</span> ( <span
class="methodparam"><span class="type">string</span> `$password`</span>
, <span class="methodparam"><span class="type">string</span>
`$salt`</span> , <span class="methodparam"><span class="type">int</span>
`$key_length`</span> , <span class="methodparam"><span
class="type">int</span> `$iterations`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$digest_algorithm`<span class="initializer"> = "sha1"</span></span> \]
)

<span class="function">openssl\_pbkdf2</span> computes PBKDF2
(Password-Based Key Derivation Function 2), a key derivation function
defined in PKCS5 v2.

### Parameters

`password`  
Password from which the derived key is generated.

`salt`  
PBKDF2 recommends a crytographic salt of at least 64 bits (8 bytes).

`key_length`  
Length of desired output key.

`iterations`  
The number of iterations desired.
<a href="https://pages.nist.gov/800-63-3/sp800-63b.html#sec5" class="link external">» NIST recommends at least 10,000</a>.

`digest_algorithm`  
Optional hash or digest algorithm from <span
class="function">openssl\_get\_md\_methods</span>. Defaults to SHA-1.

### Return Values

Returns raw binary string or **`FALSE`** on failure.

### Examples

**Example \#1 openssl\_pbkdf2() example**

``` php
<?php
$password = 'yOuR-pAs5w0rd-hERe';
$salt = openssl_random_pseudo_bytes(12);
$keyLength = 40;
$iterations = 10000;
$generated_key = openssl_pbkdf2($password, $salt, $keyLength, $iterations, 'sha256');
echo bin2hex($generated_key)."\n";
echo base64_encode($generated_key)."\n";
?>
```

### See Also

-   <span class="function">hash\_pbkdf2</span>
-   <span class="function">openssl\_get\_md\_methods</span>

openssl\_pkcs12\_export\_to\_file
=================================

Exports a PKCS\#12 Compatible Certificate Store File

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkcs12\_export\_to\_file</span> ( <span
class="methodparam"><span class="type">mixed</span> `$x509`</span> ,
<span class="methodparam"><span class="type">string</span>
`$filename`</span> , <span class="methodparam"><span
class="type">mixed</span> `$priv_key`</span> , <span
class="methodparam"><span class="type">string</span> `$pass`</span> \[,
<span class="methodparam"><span class="type">array</span> `$args`</span>
\] )

<span class="function">openssl\_pkcs12\_export\_to\_file</span> stores
`x509` into a file named by `filename` in a PKCS\#12 file format.

### Parameters

`x509`  
See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

`filename`  
Path to the output file.

`priv_key`  
Private key component of PKCS\#12 file. See
<a href="/openssl/certparams.html" class="link">Public/Private Key parameters</a>
for a list of valid values.

`pass`  
Encryption password for unlocking the PKCS\#12 file.

`args`  
Optional array, other keys will be ignored.

| Key              | Description                                                                              |
|------------------|------------------------------------------------------------------------------------------|
| *"extracerts"*   | array of extra certificates or a single certificate to be included in the PKCS\#12 file. |
| *"friendlyname"* | string to be used for the supplied certificate and key                                   |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

openssl\_pkcs12\_export
=======================

Exports a PKCS\#12 Compatible Certificate Store File to variable

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkcs12\_export</span> ( <span
class="methodparam"><span class="type">mixed</span> `$x509`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$out`</span> , <span class="methodparam"><span
class="type">mixed</span> `$priv_key`</span> , <span
class="methodparam"><span class="type">string</span> `$pass`</span> \[,
<span class="methodparam"><span class="type">array</span> `$args`</span>
\] )

<span class="function">openssl\_pkcs12\_export</span> stores `x509` into
a string named by `out` in a PKCS\#12 file format.

### Parameters

`x509`  
See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

`out`  
On success, this will hold the PKCS\#12.

`priv_key`  
Private key component of PKCS\#12 file. See
<a href="/openssl/certparams.html" class="link">Public/Private Key parameters</a>
for a list of valid values.

`pass`  
Encryption password for unlocking the PKCS\#12 file.

`args`  
Optional array, other keys will be ignored.

| Key              | Description                                                                              |
|------------------|------------------------------------------------------------------------------------------|
| *"extracerts"*   | array of extra certificates or a single certificate to be included in the PKCS\#12 file. |
| *"friendlyname"* | string to be used for the supplied certificate and key                                   |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

openssl\_pkcs12\_read
=====================

Parse a PKCS\#12 Certificate Store into an array

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkcs12\_read</span> ( <span
class="methodparam"><span class="type">string</span> `$pkcs12`</span> ,
<span class="methodparam"><span class="type">array</span>
`&$certs`</span> , <span class="methodparam"><span
class="type">string</span> `$pass`</span> )

<span class="function">openssl\_pkcs12\_read</span> parses the PKCS\#12
certificate store supplied by `pkcs12` into a array named `certs`.

### Parameters

`pkcs12`  
The certificate store contents, not its file name.

`certs`  
On success, this will hold the Certificate Store Data.

`pass`  
Encryption password for unlocking the PKCS\#12 file.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">openssl\_pkcs12\_read</span>
example**

``` php
<?php
if (!$cert_store = file_get_contents("/certs/file.p12")) {
    echo "Error: Unable to read the cert file\n";
    exit;
}

if (openssl_pkcs12_read($cert_store, $cert_info, "my_secret_pass")) {
    echo "Certificate Information\n";
    print_r($cert_info);
} else {
    echo "Error: Unable to read the cert store.\n";
    exit;
}
?>
```

openssl\_pkcs7\_decrypt
=======================

Decrypts an S/MIME encrypted message

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkcs7\_decrypt</span> ( <span
class="methodparam"><span class="type">string</span>
`$infilename`</span> , <span class="methodparam"><span
class="type">string</span> `$outfilename`</span> , <span
class="methodparam"><span class="type">mixed</span> `$recipcert`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$recipkey`</span> \] )

Decrypts the S/MIME encrypted message contained in the file specified by
`infilename` using the certificate and its associated private key
specified by `recipcert` and `recipkey`.

### Parameters

`infilename`  

`outfilename`  
The decrypted message is written to the file specified by `outfilename`.

`recipcert`  

`recipkey`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">openssl\_pkcs7\_decrypt</span>
example**

``` php
<?php
// $cert and $key are assumed to contain your personal certificate and private
// key pair, and that you are the recipient of an S/MIME message
$infilename = "encrypted.msg";  // this file holds your encrypted message
$outfilename = "decrypted.msg"; // make sure you can write to this file

if (openssl_pkcs7_decrypt($infilename, $outfilename, $cert, $key)) {
    echo "decrypted!";
} else {
    echo "failed to decrypt!";
}
?>
```

openssl\_pkcs7\_encrypt
=======================

Encrypt an S/MIME message

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkcs7\_encrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$infile`</span> ,
<span class="methodparam"><span class="type">string</span>
`$outfile`</span> , <span class="methodparam"><span
class="type">mixed</span> `$recipcerts`</span> , <span
class="methodparam"><span class="type">array</span> `$headers`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$cipherid`<span
class="initializer"> = OPENSSL\_CIPHER\_RC2\_40</span></span> \]\] )

<span class="function">openssl\_pkcs7\_encrypt</span> takes the contents
of the file named `infile` and encrypts them using an RC2 40-bit cipher
so that they can only be read by the intended recipients specified by
`recipcerts`.

### Parameters

`infile`  

`outfile`  

`recipcerts`  
Either a lone X.509 certificate, or an array of X.509 certificates.

`headers`  
`headers` is an array of headers that will be prepended to the data
after it has been encrypted.

`headers` can be either an associative array keyed by header name, or an
indexed array, where each element contains a single header line.

`flags`  
`flags` can be used to specify options that affect the encoding
process - see
<a href="/openssl/constants.html#PKCS7%20Flags/Constants" class="link">PKCS7 constants</a>.

`cipherid`  
One of
<a href="/openssl/constants.html#Ciphers" class="link">cipher constants</a>.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">openssl\_pkcs7\_encrypt</span>
example**

``` php
<?php
// the message you want to encrypt and send to your secret agent
// in the field, known as nighthawk.  You have his certificate
// in the file nighthawk.pem
$data = <<<EOD
Nighthawk,

Top secret, for your eyes only!

The enemy is closing in! Meet me at the cafe at 8.30am
to collect your forged passport!

HQ
EOD;

// load key
$key = file_get_contents("nighthawk.pem");

// save message to file
$fp = fopen("msg.txt", "w");
fwrite($fp, $data);
fclose($fp);

// encrypt it
if (openssl_pkcs7_encrypt("msg.txt", "enc.txt", $key,
    array("To" => "nighthawk@example.com", // keyed syntax
          "From: HQ <hq@example.com>", // indexed syntax
          "Subject" => "Eyes only"))) {
    // message encrypted - send it!
    exec(ini_get("sendmail_path") . " < enc.txt");
}
?>
```

openssl\_pkcs7\_read
====================

Export the PKCS7 file to an array of PEM certificates

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkcs7\_read</span> ( <span
class="methodparam"><span class="type">string</span>
`$infilename`</span> , <span class="methodparam"><span
class="type">array</span> `&$certs`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`infilename`  

`certs`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

openssl\_pkcs7\_sign
====================

Sign an S/MIME message

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkcs7\_sign</span> ( <span
class="methodparam"><span class="type">string</span>
`$infilename`</span> , <span class="methodparam"><span
class="type">string</span> `$outfilename`</span> , <span
class="methodparam"><span class="type">mixed</span> `$signcert`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$privkey`</span> , <span class="methodparam"><span
class="type">array</span> `$headers`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = PKCS7\_DETACHED</span></span> \[, <span
class="methodparam"><span class="type">string</span>
`$extracerts`</span> \]\] )

<span class="function">openssl\_pkcs7\_sign</span> takes the contents of
the file named `infilename` and signs them using the certificate and its
matching private key specified by `signcert` and `privkey` parameters.

### Parameters

`infilename`  
The input file you are intending to digitally sign.

`outfilename`  
The file which the digital signature will be written to.

`signcert`  
The X.509 certificate used to digitally sign infilename. See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

`privkey`  
`privkey` is the private key corresponding to signcert. See
<a href="/openssl/certparams.html" class="link">Public/Private Key parameters</a>
for a list of valid values.

`headers`  
`headers` is an array of headers that will be prepended to the data
after it has been signed (see <span
class="function">openssl\_pkcs7\_encrypt</span> for more information
about the format of this parameter).

`flags`  
`flags` can be used to alter the output - see
<a href="/openssl/constants.html#PKCS7%20Flags/Constants" class="link">PKCS7 constants</a>.

`extracerts`  
`extracerts` specifies the name of a file containing a bunch of extra
certificates to include in the signature which can for example be used
to help the recipient to verify the certificate that you used.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">openssl\_pkcs7\_sign</span>
example**

``` php
<?php
// the message you want to sign so that recipient can be sure it was you that
// sent it
$data = <<<EOD

You have my authorization to spend $10,000 on dinner expenses.

The CEO
EOD;
// save message to file
$fp = fopen("msg.txt", "w");
fwrite($fp, $data);
fclose($fp);
// encrypt it
if (openssl_pkcs7_sign("msg.txt", "signed.txt", "file://mycert.pem",
    array("file://mycert.pem", "mypassphrase"),
    array("To" => "joes@example.com", // keyed syntax
          "From: HQ <ceo@example.com>", // indexed syntax
          "Subject" => "Eyes only")
    )) {
    // message signed - send it!
    exec(ini_get("sendmail_path") . " < signed.txt");
}
?>
```

openssl\_pkcs7\_verify
======================

Verifies the signature of an S/MIME signed message

### Description

<span class="type">mixed</span> <span
class="methodname">openssl\_pkcs7\_verify</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
, <span class="methodparam"><span class="type">int</span>
`$flags`</span> \[, <span class="methodparam"><span
class="type">string</span> `$outfilename`</span> \[, <span
class="methodparam"><span class="type">array</span> `$cainfo`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$extracerts`</span> \[, <span class="methodparam"><span
class="type">string</span> `$content`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$p7bfilename`</span> \]\]\]\]\] )

<span class="function">openssl\_pkcs7\_verify</span> reads the S/MIME
message contained in the given file and examines the digital signature.

### Parameters

`filename`  
Path to the message.

`flags`  
`flags` can be used to affect how the signature is verified - see
<a href="/openssl/constants.html#PKCS7%20Flags/Constants" class="link">PKCS7 constants</a>
for more information.

`outfilename`  
If the `outfilename` is specified, it should be a string holding the
name of a file into which the certificates of the persons that signed
the messages will be stored in PEM format.

`cainfo`  
If the `cainfo` is specified, it should hold information about the
trusted CA certificates to use in the verification process - see
<a href="/openssl/cert/verification.html" class="link">certificate verification</a>
for more information about this parameter.

`extracerts`  
If the `extracerts` is specified, it is the filename of a file
containing a bunch of certificates to use as untrusted CAs.

`content`  
You can specify a filename with `content` that will be filled with the
verified data, but with the signature information stripped.

`p7bfilename`  

### Return Values

Returns **`TRUE`** if the signature is verified, **`FALSE`** if it is
not correct (the message has been tampered with, or the signing
certificate is invalid), or -1 on error.

### Changelog

| Version | Description                            |
|---------|----------------------------------------|
| 7.2.0   | The `p7bfilename` parameter was added. |
| 5.1.0   | The `content` parameter was added.     |

### Notes

> **Note**: <span class="simpara"> As specified in RFC 2045, lines may
> not be longer than 76 characters in the `filename` parameter. </span>

openssl\_pkey\_export\_to\_file
===============================

Gets an exportable representation of a key into a file

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkey\_export\_to\_file</span> ( <span
class="methodparam"><span class="type">mixed</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`$outfilename`</span> \[, <span class="methodparam"><span
class="type">string</span> `$passphrase`</span> \[, <span
class="methodparam"><span class="type">array</span> `$configargs`</span>
\]\] )

<span class="function">openssl\_pkey\_export\_to\_file</span> saves an
ascii-armoured (PEM encoded) rendition of `key` into the file named by
`outfilename`.

> **Note**: <span class="simpara"> You need to have a valid
> `openssl.cnf` installed for this function to operate correctly. See
> the notes under
> <a href="/openssl/setup.html#Installation" class="link">the installation section</a>
> for more information. </span>

### Parameters

`key`  

`outfilename`  
Path to the output file.

`passphrase`  
The key can be optionally protected by a `passphrase`.

`configargs`  
`configargs` can be used to fine-tune the export process by specifying
and/or overriding options for the openssl configuration file. See <span
class="function">openssl\_csr\_new</span> for more information about
`configargs`.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

openssl\_pkey\_export
=====================

Gets an exportable representation of a key into a string

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_pkey\_export</span> ( <span
class="methodparam"><span class="type">mixed</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$out`</span> \[, <span class="methodparam"><span
class="type">string</span> `$passphrase`</span> \[, <span
class="methodparam"><span class="type">array</span> `$configargs`</span>
\]\] )

<span class="function">openssl\_pkey\_export</span> exports `key` as a
PEM encoded string and stores it into `out` (which is passed by
reference).

> **Note**: <span class="simpara"> You need to have a valid
> `openssl.cnf` installed for this function to operate correctly. See
> the notes under
> <a href="/openssl/setup.html#Installation" class="link">the installation section</a>
> for more information. </span>

### Parameters

`key`  

`out`  

`passphrase`  
The key is optionally protected by `passphrase`.

`configargs`  
`configargs` can be used to fine-tune the export process by specifying
and/or overriding options for the openssl configuration file. See <span
class="function">openssl\_csr\_new</span> for more information about
`configargs`.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

openssl\_pkey\_free
===================

Frees a private key

### Description

<span class="type">void</span> <span
class="methodname">openssl\_pkey\_free</span> ( <span
class="methodparam"><span class="type">resource</span> `$key`</span> )

This function frees a private key created by <span
class="function">openssl\_pkey\_new</span>.

### Parameters

`key`  
Resource holding the key.

### Return Values

No value is returned.

openssl\_pkey\_get\_details
===========================

Returns an array with the key details

### Description

<span class="type">array</span> <span
class="methodname">openssl\_pkey\_get\_details</span> ( <span
class="methodparam"><span class="type">resource</span> `$key`</span> )

This function returns the key details (bits, key, type).

### Parameters

`key`  
Resource holding the key.

### Return Values

Returns an array with the key details in success or **`FALSE`** in
failure. Returned array has indexes *bits* (number of bits), *key*
(string representation of the public key) and *type* (type of the key
which is one of **`OPENSSL_KEYTYPE_RSA`**, **`OPENSSL_KEYTYPE_DSA`**,
**`OPENSSL_KEYTYPE_DH`**, **`OPENSSL_KEYTYPE_EC`** or -1 meaning
unknown).

Depending on the key type used, additional details may be returned. Note
that some elements may not always be available.

-   <span class="simpara"> **`OPENSSL_KEYTYPE_RSA`**, an additional
    array key named *"rsa"*, containing the key data is returned.
    </span>
    | Key      | Description                       |
    |----------|-----------------------------------|
    | *"n"*    | modulus                           |
    | *"e"*    | public exponent                   |
    | *"d"*    | private exponent                  |
    | *"p"*    | prime 1                           |
    | *"q"*    | prime 2                           |
    | *"dmp1"* | exponent1, d mod (p-1)            |
    | *"dmq1"* | exponent2, d mod (q-1)            |
    | *"iqmp"* | coefficient, (inverse of q) mod p |
-   <span class="simpara"> **`OPENSSL_KEYTYPE_DSA`**, an additional
    array key named *"dsa"*, containing the key data is returned.
    </span>
    | Key           | Description                         |
    |---------------|-------------------------------------|
    | *"p"*         | prime number (public)               |
    | *"q"*         | 160-bit subprime, q \| p-1 (public) |
    | *"g"*         | generator of subgroup (public)      |
    | *"priv\_key"* | private key x                       |
    | *"pub\_key"*  | public key y = g^x                  |
-   <span class="simpara"> **`OPENSSL_KEYTYPE_DH`**, an additional array
    key named *"dh"*, containing the key data is returned. </span>
    | Key           | Description                |
    |---------------|----------------------------|
    | *"p"*         | prime number (shared)      |
    | *"g"*         | generator of Z\_p (shared) |
    | *"priv\_key"* | private DH value x         |
    | *"pub\_key"*  | public DH value g^x        |
-   <span class="simpara"> **`OPENSSL_KEYTYPE_EC`**, an additional array
    key named *"ec"*, containing the key data is returned. </span>
    | Key             | Description                                                                 |
    |-----------------|-----------------------------------------------------------------------------|
    | *"curve\_name"* | name of curve, see <span class="function">openssl\_get\_curve\_names</span> |
    | *"curve\_oid"*  | ASN1 Object identifier (OID) for EC curve.                                  |
    | *"x"*           | x coordinate (public)                                                       |
    | *"y"*           | y coordinate (public)                                                       |
    | *"d"*           | private key                                                                 |

openssl\_pkey\_get\_private
===========================

Get a private key

### Description

<span class="type">resource</span> <span
class="methodname">openssl\_pkey\_get\_private</span> ( <span
class="methodparam"><span class="type">mixed</span> `$key`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$passphrase`<span class="initializer"> = ""</span></span> \] )

<span class="function">openssl\_pkey\_get\_private</span> parses `key`
and prepares it for use by other functions.

### Parameters

`key`  
`key` can be one of the following:

1.  <span class="simpara">a string having the format
    `file://path/to/file.pem`. The named file must contain a PEM encoded
    certificate/private key (it may contain both). </span>
2.  <span class="simpara">A PEM formatted private key.</span>

`passphrase`  
The optional parameter `passphrase` must be used if the specified key is
encrypted (protected by a passphrase).

### Return Values

Returns a positive key resource identifier on success, or **`FALSE`** on
error.

openssl\_pkey\_get\_public
==========================

Extract public key from certificate and prepare it for use

### Description

<span class="type">resource</span> <span
class="methodname">openssl\_pkey\_get\_public</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$certificate`</span> )

<span class="function">openssl\_pkey\_get\_public</span> extracts the
public key from `certificate` and prepares it for use by other
functions.

### Parameters

`certificate`  
`certificate` can be one of the following:

1.  <span class="simpara">an X.509 certificate resource</span>
2.  <span class="simpara">a string having the format
    `file://path/to/file.pem`. The named file must contain a PEM encoded
    certificate/public key (it may contain both). </span>
3.  <span class="simpara">A PEM formatted public key.</span>

### Return Values

Returns a positive key resource identifier on success, or **`FALSE`** on
error.

openssl\_pkey\_new
==================

Generates a new private key

### Description

<span class="type">resource</span> <span
class="methodname">openssl\_pkey\_new</span> (\[ <span
class="methodparam"><span class="type">array</span> `$configargs`</span>
\] )

<span class="function">openssl\_pkey\_new</span> generates a new private
and public key pair. The public component of the key can be obtained
using <span class="function">openssl\_pkey\_get\_public</span>.

> **Note**: <span class="simpara"> You need to have a valid
> `openssl.cnf` installed for this function to operate correctly. See
> the notes under
> <a href="/openssl/setup.html#Installation" class="link">the installation section</a>
> for more information. </span>

### Parameters

`configargs`  
You can finetune the key generation (such as specifying the number of
bits) using `configargs`. See <span
class="function">openssl\_csr\_new</span> for more information about
`configargs`.

### Return Values

Returns a resource identifier for the pkey on success, or **`FALSE`** on
error.

### Changelog

| Version | Description                                                                 |
|---------|-----------------------------------------------------------------------------|
| 7.1.0   | The `curve_name` configarg was added to make it possible to create EC keys. |

openssl\_private\_decrypt
=========================

Decrypts data with private key

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_private\_decrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$decrypted`</span> , <span class="methodparam"><span
class="type">mixed</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$padding`<span
class="initializer"> = OPENSSL\_PKCS1\_PADDING</span></span> \] )

<span class="function">openssl\_private\_decrypt</span> decrypts `data`
that was previously encrypted via <span
class="function">openssl\_public\_encrypt</span> and stores the result
into `decrypted`.

You can use this function e.g. to decrypt data which is supposed to only
be available to you.

### Parameters

`data`  

`decrypted`  

`key`  
`key` must be the private key corresponding that was used to encrypt the
data.

`padding`  
`padding` can be one of **`OPENSSL_PKCS1_PADDING`**,
**`OPENSSL_SSLV23_PADDING`**, **`OPENSSL_PKCS1_OAEP_PADDING`**,
**`OPENSSL_NO_PADDING`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openssl\_public\_encrypt</span>
-   <span class="function">openssl\_public\_decrypt</span>

openssl\_private\_encrypt
=========================

Encrypts data with private key

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_private\_encrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$crypted`</span> , <span class="methodparam"><span
class="type">mixed</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$padding`<span
class="initializer"> = OPENSSL\_PKCS1\_PADDING</span></span> \] )

<span class="function">openssl\_private\_encrypt</span> encrypts `data`
with private `key` and stores the result into `crypted`. Encrypted data
can be decrypted via <span
class="function">openssl\_public\_decrypt</span>.

This function can be used e.g. to sign data (or its hash) to prove that
it is not written by someone else.

### Parameters

`data`  

`crypted`  

`key`  

`padding`  
`padding` can be one of **`OPENSSL_PKCS1_PADDING`**,
**`OPENSSL_NO_PADDING`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openssl\_public\_encrypt</span>
-   <span class="function">openssl\_public\_decrypt</span>

openssl\_public\_decrypt
========================

Decrypts data with public key

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_public\_decrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$decrypted`</span> , <span class="methodparam"><span
class="type">mixed</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$padding`<span
class="initializer"> = OPENSSL\_PKCS1\_PADDING</span></span> \] )

<span class="function">openssl\_public\_decrypt</span> decrypts `data`
that was previous encrypted via <span
class="function">openssl\_private\_encrypt</span> and stores the result
into `decrypted`.

You can use this function e.g. to check if the message was written by
the owner of the private key.

### Parameters

`data`  

`decrypted`  

`key`  
`key` must be the public key corresponding that was used to encrypt the
data.

`padding`  
`padding` can be one of **`OPENSSL_PKCS1_PADDING`**,
**`OPENSSL_NO_PADDING`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openssl\_private\_encrypt</span>
-   <span class="function">openssl\_private\_decrypt</span>

openssl\_public\_encrypt
========================

Encrypts data with public key

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_public\_encrypt</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$crypted`</span> , <span class="methodparam"><span
class="type">mixed</span> `$key`</span> \[, <span
class="methodparam"><span class="type">int</span> `$padding`<span
class="initializer"> = OPENSSL\_PKCS1\_PADDING</span></span> \] )

<span class="function">openssl\_public\_encrypt</span> encrypts `data`
with public `key` and stores the result into `crypted`. Encrypted data
can be decrypted via <span
class="function">openssl\_private\_decrypt</span>.

This function can be used e.g. to encrypt message which can be then read
only by owner of the private key. It can be also used to store secure
data in database.

### Parameters

`data`  

`crypted`  
This will hold the result of the encryption.

`key`  
The public key.

`padding`  
`padding` can be one of **`OPENSSL_PKCS1_PADDING`**,
**`OPENSSL_SSLV23_PADDING`**, **`OPENSSL_PKCS1_OAEP_PADDING`**,
**`OPENSSL_NO_PADDING`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">openssl\_private\_encrypt</span>
-   <span class="function">openssl\_private\_decrypt</span>

openssl\_random\_pseudo\_bytes
==============================

Generate a pseudo-random string of bytes

### Description

<span class="type">string</span> <span
class="methodname">openssl\_random\_pseudo\_bytes</span> ( <span
class="methodparam"><span class="type">int</span> `$length`</span> \[,
<span class="methodparam"><span class="type">bool</span>
`&$crypto_strong`</span> \] )

Generates a <span class="type">string</span> of pseudo-random bytes,
with the number of bytes determined by the `length` parameter.

It also indicates if a cryptographically strong algorithm was used to
produce the pseudo-random bytes, and does this via the optional
`crypto_strong` parameter. It's rare for this to be **`FALSE`**, but
some systems may be broken or old.

### Parameters

`length`  
The length of the desired string of bytes. Must be a positive integer.
PHP will try to cast this parameter to a non-null integer to use it.

`crypto_strong`  
If passed into the function, this will hold a <span
class="type">boolean</span> value that determines if the algorithm used
was "cryptographically strong", e.g., safe for usage with GPG,
passwords, etc. **`TRUE`** if it did, otherwise **`FALSE`**

### Return Values

Returns the generated <span class="type">string</span> of bytes on
success, or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="function">openssl\_random\_pseudo\_bytes</span> example**

``` php
<?php
for ($i = 1; $i <= 4; $i++) {
    $bytes = openssl_random_pseudo_bytes($i, $cstrong);
    $hex   = bin2hex($bytes);

    echo "Lengths: Bytes: $i and Hex: " . strlen($hex) . PHP_EOL;
    var_dump($hex);
    var_dump($cstrong);
    echo PHP_EOL;
}
?>
```

The above example will output something similar to:

    Lengths: Bytes: 1 and Hex: 2
    string(2) "42"
    bool(true)

    Lengths: Bytes: 2 and Hex: 4
    string(4) "dc6e"
    bool(true)

    Lengths: Bytes: 3 and Hex: 6
    string(6) "288591"
    bool(true)

    Lengths: Bytes: 4 and Hex: 8
    string(8) "ab86d144"
    bool(true)

### See Also

-   <span class="function">random\_bytes</span>
-   <span class="function">bin2hex</span>
-   <span class="function">crypt</span>
-   <span class="function">mt\_rand</span>
-   <span class="function">uniqid</span>

openssl\_seal
=============

Seal (encrypt) data

### Description

<span class="type">int</span> <span
class="methodname">openssl\_seal</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$sealed_data`</span> , <span class="methodparam"><span
class="type">array</span> `&$env_keys`</span> , <span
class="methodparam"><span class="type">array</span>
`$pub_key_ids`</span> \[, <span class="methodparam"><span
class="type">string</span> `$method`<span class="initializer"> =
"RC4"</span></span> \[, <span class="methodparam"><span
class="type">string</span> `&$iv`</span> \]\] )

<span class="function">openssl\_seal</span> seals (encrypts) `data` by
using the given `method` with a randomly generated secret key. The key
is encrypted with each of the public keys associated with the
identifiers in `pub_key_ids` and each encrypted key is returned in
`env_keys`. This means that one can send sealed data to multiple
recipients (provided one has obtained their public keys). Each recipient
must receive both the sealed data and the envelope key that was
encrypted with the recipient's public key.

### Parameters

`data`  
The data to seal.

`sealed_data`  
The sealed data.

`env_keys`  
Array of encrypted keys.

`pub_key_ids`  
Array of public key resource identifiers.

`method`  
The cipher method.

`iv`  
The initialization vector.

### Return Values

Returns the length of the sealed data on success, or **`FALSE`** on
error. If successful the sealed data is returned in `sealed_data`, and
the envelope keys in `env_keys`.

### Changelog

| Version | Description                  |
|---------|------------------------------|
| 7.0.0   | The `iv` has been added.     |
| 5.3.0   | The `method` has been added. |

### Examples

**Example \#1 <span class="function">openssl\_seal</span> example**

``` php
<?php
// $data is assumed to contain the data to be sealed

// fetch public keys for our recipients, and ready them
$fp = fopen("/src/openssl-0.9.6/demos/maurice/cert.pem", "r");
$cert = fread($fp, 8192);
fclose($fp);
$pk1 = openssl_get_publickey($cert);
// Repeat for second recipient
$fp = fopen("/src/openssl-0.9.6/demos/sign/cert.pem", "r");
$cert = fread($fp, 8192);
fclose($fp);
$pk2 = openssl_get_publickey($cert);

// seal message, only owners of $pk1 and $pk2 can decrypt $sealed with keys
// $ekeys[0] and $ekeys[1] respectively.
openssl_seal($data, $sealed, $ekeys, array($pk1, $pk2));

// free the keys from memory
openssl_free_key($pk1);
openssl_free_key($pk2);
?>
```

### See Also

-   <span class="function">openssl\_open</span>

openssl\_sign
=============

Generate signature

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_sign</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$signature`</span> , <span class="methodparam"><span
class="type">mixed</span> `$priv_key_id`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$signature_alg`<span class="initializer"> =
OPENSSL\_ALGO\_SHA1</span></span> \] )

<span class="function">openssl\_sign</span> computes a signature for the
specified `data` by generating a cryptographic digital signature using
the private key associated with `priv_key_id`. Note that the data itself
is not encrypted.

### Parameters

`data`  
The string of data you wish to sign

`signature`  
If the call was successful the signature is returned in `signature`.

`priv_key_id`  
<span class="type">resource</span> - a key, returned by <span
class="function">openssl\_get\_privatekey</span>

<span class="type">string</span> - a PEM formatted key

`signature_alg`  
<span class="type">int</span> - one of these
<a href="/openssl/constants.html#Signature%20Algorithms" class="link">Signature Algorithms</a>.

<span class="type">string</span> - a valid string returned by <span
class="function">openssl\_get\_md\_methods</span> example,
"sha256WithRSAEncryption" or "sha384".

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">openssl\_sign</span> example**

``` php
<?php
// $data is assumed to contain the data to be signed

// fetch private key from file and ready it
$pkeyid = openssl_pkey_get_private("file://src/openssl-0.9.6/demos/sign/key.pem");

// compute signature
openssl_sign($data, $signature, $pkeyid);

// free the key from memory
openssl_free_key($pkeyid);
?>
```

**Example \#2 <span class="function">openssl\_sign</span> example**

``` php
<?php
//data you want to sign
$data = 'my data';

//create new private and public key
$new_key_pair = openssl_pkey_new(array(
    "private_key_bits" => 2048,
    "private_key_type" => OPENSSL_KEYTYPE_RSA,
));
openssl_pkey_export($new_key_pair, $private_key_pem);

$details = openssl_pkey_get_details($new_key_pair);
$public_key_pem = $details['key'];

//create signature
openssl_sign($data, $signature, $private_key_pem, OPENSSL_ALGO_SHA256);

//save for later
file_put_contents('private_key.pem', $private_key_pem);
file_put_contents('public_key.pem', $public_key_pem);
file_put_contents('signature.dat', $signature);

//verify signature
$r = openssl_verify($data, $signature, $public_key_pem, "sha256WithRSAEncryption");
var_dump($r);
?>
```

### See Also

-   <span class="function">openssl\_verify</span>

openssl\_spki\_export\_challenge
================================

Exports the challenge associated with a signed public key and challenge

### Description

<span class="type">string</span> <span
class="methodname">openssl\_spki\_export\_challenge</span> ( <span
class="methodparam"><span class="type">string</span> `&$spkac`</span> )

Exports challenge from encoded signed public key and challenge

### Parameters

`spkac`  
Expects a valid signed public key and challenge

### Return Values

Returns the associated challenge string or NULL on failure.

### Errors/Exceptions

Emits an **`E_WARNING`** level error if an invalid argument is passed
via the `spkac` parameter.

### Examples

**Example \#1 <span
class="function">openssl\_spki\_export\_challenge</span> example**

Extracts the associated challenge string or NULL on failure.

``` php
<?php
$pkey = openssl_pkey_new('secret password');
$spkac = openssl_spki_new($pkey, 'challenge string');
$challenge = openssl_spki_export_challenge(preg_replace('/SPKAC=/', '', $spkac));
?>
```

**Example \#2 <span
class="function">openssl\_spki\_export\_challenge</span> example from
\<keygen\>**

Extracts the associated challenge string issued from the \<keygen\>
element

``` php
<?php
$challenge = openssl_spki_export_challenge(preg_replace('/SPKAC=/', '', $_POST['spkac']));
?>
<keygen name="spkac" challenge="challenge string" keytype="RSA">
```

### See Also

-   <span class="function">openssl\_spki\_new</span>
-   <span class="function">openssl\_spki\_verify</span>
-   <span class="function">openssl\_spki\_export</span>
-   <span class="function">openssl\_get\_md\_methods</span>
-   <span class="function">openssl\_csr\_new</span>
-   <span class="function">openssl\_csr\_sign</span>

openssl\_spki\_export
=====================

Exports a valid PEM formatted public key signed public key and challenge

### Description

<span class="type">string</span> <span
class="methodname">openssl\_spki\_export</span> ( <span
class="methodparam"><span class="type">string</span> `&$spkac`</span> )

Exports PEM formatted public key from encoded signed public key and
challenge

### Parameters

`spkac`  
Expects a valid signed public key and challenge

### Return Values

Returns the associated PEM formatted public key or NULL on failure.

### Errors/Exceptions

Emits an **`E_WARNING`** level error if an invalid argument is passed
via the `spkac` parameter.

### Examples

**Example \#1 <span class="function">openssl\_spki\_export</span>
example**

Extracts the associated PEM formatted public key or NULL on failure.

``` php
<?php
$pkey = openssl_pkey_new('secret password');
$spkac = openssl_spki_new($pkey, 'challenge string');
$pubKey = openssl_spki_export(preg_replace('/SPKAC=/', '', $spkac));

if ($pubKey) {
    echo $pubKey;
}
?>
```

**Example \#2 <span class="function">openssl\_spki\_export</span>
example from \<keygen\>**

Extracts the associated PEM formatted public key issued from the
\<keygen\> element

``` php
<?php
$spkac = openssl_spki_export(preg_replace('/SPKAC=/', '', $_POST['spkac']));
if ($spkac != NULL) {
    echo $spkac;
} else {
    echo "Extraction of pub key failed";
}
?>
<keygen name="spkac" challenge="challenge string" keytype="RSA">
```

### See Also

-   <span class="function">openssl\_spki\_new</span>
-   <span class="function">openssl\_spki\_verify</span>
-   <span class="function">openssl\_spki\_export\_challenge</span>
-   <span class="function">openssl\_get\_md\_methods</span>
-   <span class="function">openssl\_csr\_new</span>
-   <span class="function">openssl\_csr\_sign</span>

openssl\_spki\_new
==================

Generate a new signed public key and challenge

### Description

<span class="type">string</span> <span
class="methodname">openssl\_spki\_new</span> ( <span
class="methodparam"><span class="type">resource</span>
`&$privkey`</span> , <span class="methodparam"><span
class="type">string</span> `&$challenge`</span> \[, <span
class="methodparam"><span class="type">int</span> `$algorithm`<span
class="initializer"> = 0</span></span> \] )

Generates a signed public key and challenge using specified hashing
algorithm

### Parameters

`privkey`  
`privkey` should be set to a private key that was previously generated
by <span class="function">openssl\_pkey\_new</span> (or otherwise
obtained from the other openssl\_pkey family of functions). The
corresponding public portion of the key will be used to sign the CSR.

`challenge`  
The challenge associated to associate with the SPKAC

`algorithm`  
The digest algorithm. See openssl\_get\_md\_method().

### Return Values

Returns a signed public key and challenge string or NULL on failure.

### Errors/Exceptions

Emits an **`E_WARNING`** level error if an unknown signature algorithm
is passed via the `algorithm` parameter.

### Examples

**Example \#1 <span class="function">openssl\_spki\_new</span> example**

Generate a new SPKAC with the default digest (MD5)

``` php
<?php
$pkey = openssl_pkey_new('secret password');
$spkac = openssl_spki_new($pkey, 'testing');

if ($spkac !== NULL) {
    echo $spkac;
} else {
    echo "SPKAC generation failed";
}
?>
```

The above example will output something similar to:

    MIICRzCCAS8wggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDM3V3sS4o4
    mB9dczziRnjGAmSp+JwPrHoYMAFGvDNmZGyiWfU586X4BKs++BAj7e/FsAfno0Hd
    hN9FwpCNFSox30L03nQvLYJE7f/WqigwBeMRT7Op/xvFks4sT70xP2HRYv4KqP9a
    WRcKU6cFH8VxhFhqM2txEIxZKdFLaL28yT7bEDmcglf4JLDdgNMb9rET1dkgtKE6
    dOaJHPGjf1uvnOH4YwkQr7n4sLUR3Kdbh0ZJAFuQVDZulo+LLzxBBkqJJcB6FhF+
    oXCdHTKZnqAhpWDz+NXYytAmevab6IYm5TWPWsJUv1YKJA5lg2mXbbloIZlN9Mgc
    i9fi03bdw+crAgMBAAEWB3Rlc3RpbmcwDQYJKoZIhvcNAQEEBQADggEBALyUvP/o
    pPSoWBlorFyZ2RnGwKf9qMpE0q2IJP7G3oDR4LyK/m933DUiZ+YnqThrH/CWb4Ek
    y5I3OCyl3S4wCuU1ibZZwDVwYShr5ELp0J9PEf7qMQZOhNsizoC7k+Czb2xB6hYW
    sKfsfTKm3cXBtH3fdgc/Z1Z7VSWnAzYo38snqm72NTf5yFRnrQdphNNXi+kn1zHA
    lxXRyFDXHOcYsOnwAWfyXFA4QDHQ0ezz0UoCY8gJXovcZb4GRYqOLUAsF2HcNboy
    29WN8VqE29sL9QxVZFlwMcqyoLcNnyw38GvNvAGqSvzzbnEFP2MAQXJVe0H0hdp/
    MML5G2iNVgNozAo=

### See Also

-   <span class="function">openssl\_spki\_verify</span>
-   <span class="function">openssl\_spki\_export\_challenge</span>
-   <span class="function">openssl\_spki\_export</span>
-   <span class="function">openssl\_get\_md\_methods</span>
-   <span class="function">openssl\_csr\_new</span>
-   <span class="function">openssl\_csr\_sign</span>

openssl\_spki\_verify
=====================

Verifies a signed public key and challenge

### Description

<span class="type">string</span> <span
class="methodname">openssl\_spki\_verify</span> ( <span
class="methodparam"><span class="type">string</span> `&$spkac`</span> )

Validates the supplied signed public key and challenge

### Parameters

`spkac`  
Expects a valid signed public key and challenge

### Return Values

Returns a boolean on success or failure.

### Errors/Exceptions

Emits an **`E_WARNING`** level error if an invalid argument is passed
via the `spkac` parameter.

### Examples

**Example \#1 <span class="function">openssl\_spki\_verify</span>
example**

Validates an existing signed public key and challenge

``` php
<?php
$pkey = openssl_pkey_new('secret password');
$spkac = openssl_spki_new($pkey, 'challenge string');

if (openssl_spki_verify(preg_replace('/SPKAC=/', '', $spkac))) {
    echo $spkac;
} else {
    echo "SPKAC validation failed";
}
?>
```

**Example \#2 <span class="function">openssl\_spki\_verify</span>
example from \<keygen\>**

Validates an existing signed public key and challenge issued from the
\<keygen\> element

``` php
<?php
if (openssl_spki_verify(preg_replace('/SPKAC=/', '', $_POST['spkac']))) {
    echo $spkac;
} else {
    echo "SPKAC validation failed";
}
?>
<keygen name="spkac" challenge="challenge string" keytype="RSA">
```

### See Also

-   <span class="function">openssl\_spki\_new</span>
-   <span class="function">openssl\_spki\_export\_challenge</span>
-   <span class="function">openssl\_spki\_export</span>
-   <span class="function">openssl\_get\_md\_methods</span>
-   <span class="function">openssl\_csr\_new</span>
-   <span class="function">openssl\_csr\_sign</span>

openssl\_verify
===============

Verify signature

### Description

<span class="type">int</span> <span
class="methodname">openssl\_verify</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">string</span>
`$signature`</span> , <span class="methodparam"><span
class="type">mixed</span> `$pub_key_id`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$signature_alg`<span class="initializer"> =
OPENSSL\_ALGO\_SHA1</span></span> \] )

<span class="function">openssl\_verify</span> verifies that the
`signature` is correct for the specified `data` using the public key
associated with `pub_key_id`. This must be the public key corresponding
to the private key used for signing.

### Parameters

`data`  
The string of data used to generate the signature previously

`signature`  
A raw binary string, generated by <span
class="function">openssl\_sign</span> or similar means

`pub_key_id`  
<span class="type">resource</span> - a key, returned by <span
class="function">openssl\_get\_publickey</span>

<span class="type">string</span> - a PEM formatted key, example,
"-----BEGIN PUBLIC KEY----- MIIBCgK..."

`signature_alg`  
<span class="type">int</span> - one of these
<a href="/openssl/constants.html#Signature%20Algorithms" class="link">Signature Algorithms</a>.

<span class="type">string</span> - a valid string returned by <span
class="function">openssl\_get\_md\_methods</span> example,
"sha1WithRSAEncryption" or "sha512".

### Return Values

Returns 1 if the signature is correct, 0 if it is incorrect, and -1 on
error.

### Changelog

| Version | Description                              |
|---------|------------------------------------------|
| 5.2.0   | The `signature_alg` parameter was added. |

### Examples

**Example \#1 <span class="function">openssl\_verify</span> example**

``` php
<?php
// $data and $signature are assumed to contain the data and the signature

// fetch public key from certificate and ready it
$pubkeyid = openssl_pkey_get_public("file://src/openssl-0.9.6/demos/sign/cert.pem");

// state whether signature is okay or not
$ok = openssl_verify($data, $signature, $pubkeyid);
if ($ok == 1) {
    echo "good";
} elseif ($ok == 0) {
    echo "bad";
} else {
    echo "ugly, error checking signature";
}
// free the key from memory
openssl_free_key($pubkeyid);
?>
```

**Example \#2 <span class="function">openssl\_verify</span> example**

``` php
<?php
//data you want to sign
$data = 'my data';

//create new private and public key
$private_key_res = openssl_pkey_new(array(
    "private_key_bits" => 2048,
    "private_key_type" => OPENSSL_KEYTYPE_RSA,
));
$details = openssl_pkey_get_details($private_key_res);
$public_key_res = openssl_pkey_get_public($details['key']);

//create signature
openssl_sign($data, $signature, $private_key_res, "sha256WithRSAEncryption");

//verify signature
$ok = openssl_verify($data, $signature, $public_key_res, OPENSSL_ALGO_SHA256);
if ($ok == 1) {
    echo "valid";
} elseif ($ok == 0) {
    echo "invalid";
} else {
    echo "error: ".openssl_error_string();
}
?>
```

### See Also

-   <span class="function">openssl\_sign</span>

openssl\_x509\_check\_private\_key
==================================

Checks if a private key corresponds to a certificate

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_x509\_check\_private\_key</span> ( <span
class="methodparam"><span class="type">mixed</span> `$cert`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$key`</span>
)

Checks whether the given `key` is the private key that corresponds to
`cert`.

**Warning**

The function does not check if `key` is indeed a private key or not. It
merely compares the public materials (e.g. exponent and modulus of an
RSA key) and/or key parameters (e.g. EC params of an EC key) of a key
pair.

This means, for example, that a public key could be given for `key` and
the function may return **`TRUE`**.

### Parameters

`cert`  
The certificate.

`key`  
The private key.

### Return Values

Returns **`TRUE`** if `key` is the private key that corresponds to
`cert`, or **`FALSE`** otherwise.

openssl\_x509\_checkpurpose
===========================

Verifies if a certificate can be used for a particular purpose

### Description

<span class="type">int</span> <span
class="methodname">openssl\_x509\_checkpurpose</span> ( <span
class="methodparam"><span class="type">mixed</span> `$x509cert`</span> ,
<span class="methodparam"><span class="type">int</span>
`$purpose`</span> \[, <span class="methodparam"><span
class="type">array</span> `$cainfo`<span class="initializer"> =
array()</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$untrustedfile`</span> \]\] )

<span class="function">openssl\_x509\_checkpurpose</span> examines a
certificate to see if it can be used for the specified `purpose`.

### Parameters

`x509cert`  
The examined certificate.

`purpose`  
| Constant                       | Description                                                           |
|--------------------------------|-----------------------------------------------------------------------|
| X509\_PURPOSE\_SSL\_CLIENT     | Can the certificate be used for the client side of an SSL connection? |
| X509\_PURPOSE\_SSL\_SERVER     | Can the certificate be used for the server side of an SSL connection? |
| X509\_PURPOSE\_NS\_SSL\_SERVER | Can the cert be used for Netscape SSL server?                         |
| X509\_PURPOSE\_SMIME\_SIGN     | Can the cert be used to sign S/MIME email?                            |
| X509\_PURPOSE\_SMIME\_ENCRYPT  | Can the cert be used to encrypt S/MIME email?                         |
| X509\_PURPOSE\_CRL\_SIGN       | Can the cert be used to sign a certificate revocation list (CRL)?     |
| X509\_PURPOSE\_ANY             | Can the cert be used for Any/All purposes?                            |

These options are not bitfields - you may specify one only!

`cainfo`  
`cainfo` should be an array of trusted CA files/dirs as described in
<a href="/openssl/cert/verification.html" class="link">Certificate Verification</a>.

`untrustedfile`  
If specified, this should be the name of a PEM encoded file holding
certificates that can be used to help verify the certificate, although
no trust is placed in the certificates that come from that file.

### Return Values

Returns **`TRUE`** if the certificate can be used for the intended
purpose, **`FALSE`** if it cannot, or -1 on error.

openssl\_x509\_export\_to\_file
===============================

Exports a certificate to file

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_x509\_export\_to\_file</span> ( <span
class="methodparam"><span class="type">mixed</span> `$x509`</span> ,
<span class="methodparam"><span class="type">string</span>
`$outfilename`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$notext`<span class="initializer"> =
**`TRUE`**</span></span> \] )

<span class="function">openssl\_x509\_export\_to\_file</span> stores
`x509` into a file named by `outfilename` in a PEM encoded format.

### Parameters

`x509`  
See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

`outfilename`  
Path to the output file.

`notext`  
The optional parameter `notext` affects the verbosity of the output; if
it is **`FALSE`**, then additional human-readable information is
included in the output. The default value of `notext` is **`TRUE`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

openssl\_x509\_export
=====================

Exports a certificate as a string

### Description

<span class="type">bool</span> <span
class="methodname">openssl\_x509\_export</span> ( <span
class="methodparam"><span class="type">mixed</span> `$x509`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$output`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$notext`<span class="initializer"> =
**`TRUE`**</span></span> \] )

<span class="function">openssl\_x509\_export</span> stores `x509` into a
string named by `output` in a PEM encoded format.

### Parameters

`x509`  
See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

`output`  
On success, this will hold the PEM.

`notext`  
The optional parameter `notext` affects the verbosity of the output; if
it is **`FALSE`**, then additional human-readable information is
included in the output. The default value of `notext` is **`TRUE`**.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

openssl\_x509\_fingerprint
==========================

Calculates the fingerprint, or digest, of a given X.509 certificate

### Description

<span class="type">string</span> <span
class="methodname">openssl\_x509\_fingerprint</span> ( <span
class="methodparam"><span class="type">mixed</span> `$x509`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$hash_algorithm`<span class="initializer"> = "sha1"</span></span> \[,
<span class="methodparam"><span class="type">bool</span>
`$raw_output`<span class="initializer"> = **`FALSE`**</span></span> \]\]
)

<span class="function">openssl\_x509\_fingerprint</span> returns the
digest of `x509` as a string.

### Parameters

`x509`  
See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

`hash_algorithm`  
The digest method or hash algorithm to use, e.g. "sha256", one of <span
class="function">openssl\_get\_md\_methods</span>.

`raw_output`  
When set to **`TRUE`**, outputs raw binary data. **`FALSE`** outputs
lowercase hexits.

### Return Values

Returns a string containing the calculated certificate fingerprint as
lowercase hexits unless `raw_output` is set to **`TRUE`** in which case
the raw binary representation of the message digest is returned.

Returns **`FALSE`** on failure.

openssl\_x509\_free
===================

Free certificate resource

### Description

<span class="type">void</span> <span
class="methodname">openssl\_x509\_free</span> ( <span
class="methodparam"><span class="type">resource</span>
`$x509cert`</span> )

<span class="function">openssl\_x509\_free</span> frees the certificate
associated with the specified `x509cert` resource from memory.

### Parameters

`x509cert`  

### Return Values

No value is returned.

openssl\_x509\_parse
====================

Parse an X509 certificate and return the information as an array

### Description

<span class="type">array</span> <span
class="methodname">openssl\_x509\_parse</span> ( <span
class="methodparam"><span class="type">mixed</span> `$x509cert`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$shortnames`<span class="initializer"> = **`TRUE`**</span></span> \] )

<span class="function">openssl\_x509\_parse</span> returns information
about the supplied `x509cert`, including fields such as subject name,
issuer name, purposes, valid from and valid to dates etc.

### Parameters

`x509cert`  
X509 certificate. See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

`shortnames`  
`shortnames` controls how the data is indexed in the array - if
`shortnames` is **`TRUE`** (the default) then fields will be indexed
with the short name form, otherwise, the long name form will be used -
e.g.: CN is the shortname form of commonName.

### Return Values

*The structure of the returned data is (deliberately) not yet
documented, as it is still subject to change.*

openssl\_x509\_read
===================

Parse an X.509 certificate and return a resource identifier for it

### Description

<span class="type">resource</span> <span
class="methodname">openssl\_x509\_read</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$x509certdata`</span> )

<span class="function">openssl\_x509\_read</span> parses the certificate
supplied by `x509certdata` and returns a resource identifier for it.

### Parameters

`x509certdata`  
X509 certificate. See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

### Return Values

Returns a resource identifier on success or **`FALSE`** on failure.

openssl\_x509\_verify
=====================

Verifies digital signature of x509 certificate against a public key

### Description

<span class="type">int</span> <span
class="methodname">openssl\_x509\_verify</span> ( <span
class="methodparam"><span class="type">mixed</span> `$x509`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$pub_key_id`</span> )

<span class="function">openssl\_x509\_verify</span> verifies that the
`x509` certificate was signed by the private key corresponding to public
key `pub_key_id`.

### Parameters

`x509`  
See
<a href="/openssl/certparams.html" class="link">Key/Certificate parameters</a>
for a list of valid values.

`pub_key_id`  
<span class="type">resource</span> - a key, returned by <span
class="function">openssl\_get\_publickey</span>

<span class="type">string</span> - a PEM formatted key, example,
"-----BEGIN PUBLIC KEY----- MIIBCgK..."

### Return Values

Returns 1 if the signature is correct, 0 if it is incorrect, and -1 on
error.

### Examples

**Example \#1 <span class="function">openssl\_x509\_verify</span>
example**

``` php
<?php
$hostname = "news.php.net";
$ssloptions = array(
    "capture_peer_cert" => true, 
    "capture_peer_cert_chain" => true, 
    "allow_self_signed"=> false, 
    "CN_match" => $hostname,
    "verify_peer" => true,
    "SNI_enabled" => true,
    "SNI_server_name" => $hostname,
);
 
$ctx = stream_context_create( array("ssl" => $ssloptions) );
$result = stream_socket_client("ssl://$hostname:443", $errno, $errstr, 30, STREAM_CLIENT_CONNECT, $ctx);
$cont = stream_context_get_params($result);
$x509 = $cont["options"]["ssl"]["peer_certificate"];
$certparsed = openssl_x509_parse($x509);

foreach($cont["options"]["ssl"]["peer_certificate_chain"] as $chaincert)
{
    $chainparsed = openssl_x509_parse($chaincert);
    $chain_public_key = openssl_get_publickey($chaincert);
    $r = openssl_x509_verify($x509, $chain_public_key);   
    if ($r==1)
    {
        echo $certparsed['subject']['CN'];
        echo " was digitally signed by ";
        echo $chainparsed['subject']['CN']."\n";
    }
}
?>
```

### See Also

-   <span class="function">openssl\_verify</span>
-   <span class="function">openssl\_get\_publickey</span>

**Table of Contents**

-   [openssl\_cipher\_iv\_length](/ref/openssl.html#openssl_cipher_iv_length)
    — Gets the cipher iv length
-   [openssl\_csr\_export\_to\_file](/ref/openssl.html#openssl_csr_export_to_file)
    — Exports a CSR to a file
-   [openssl\_csr\_export](/ref/openssl.html#openssl_csr_export) —
    Exports a CSR as a string
-   [openssl\_csr\_get\_public\_key](/ref/openssl.html#openssl_csr_get_public_key)
    — Returns the public key of a CSR
-   [openssl\_csr\_get\_subject](/ref/openssl.html#openssl_csr_get_subject)
    — Returns the subject of a CSR
-   [openssl\_csr\_new](/ref/openssl.html#openssl_csr_new) — Generates a
    CSR
-   [openssl\_csr\_sign](/ref/openssl.html#openssl_csr_sign) — Sign a
    CSR with another certificate (or itself) and generate a certificate
-   [openssl\_decrypt](/ref/openssl.html#openssl_decrypt) — Decrypts
    data
-   [openssl\_dh\_compute\_key](/ref/openssl.html#openssl_dh_compute_key)
    — Computes shared secret for public value of remote DH public key
    and local DH key
-   [openssl\_digest](/ref/openssl.html#openssl_digest) — Computes a
    digest
-   [openssl\_encrypt](/ref/openssl.html#openssl_encrypt) — Encrypts
    data
-   [openssl\_error\_string](/ref/openssl.html#openssl_error_string) —
    Return openSSL error message
-   [openssl\_free\_key](/ref/openssl.html#openssl_free_key) — Free key
    resource
-   [openssl\_get\_cert\_locations](/ref/openssl.html#openssl_get_cert_locations)
    — Retrieve the available certificate locations
-   [openssl\_get\_cipher\_methods](/ref/openssl.html#openssl_get_cipher_methods)
    — Gets available cipher methods
-   [openssl\_get\_curve\_names](/ref/openssl.html#openssl_get_curve_names)
    — Gets list of available curve names for ECC
-   [openssl\_get\_md\_methods](/ref/openssl.html#openssl_get_md_methods)
    — Gets available digest methods
-   [openssl\_get\_privatekey](/ref/openssl.html#openssl_get_privatekey)
    — Alias of openssl\_pkey\_get\_private
-   [openssl\_get\_publickey](/ref/openssl.html#openssl_get_publickey) —
    Alias of openssl\_pkey\_get\_public
-   [openssl\_open](/ref/openssl.html#openssl_open) — Open sealed data
-   [openssl\_pbkdf2](/ref/openssl.html#openssl_pbkdf2) — Generates a
    PKCS5 v2 PBKDF2 string
-   [openssl\_pkcs12\_export\_to\_file](/ref/openssl.html#openssl_pkcs12_export_to_file)
    — Exports a PKCS\#12 Compatible Certificate Store File
-   [openssl\_pkcs12\_export](/ref/openssl.html#openssl_pkcs12_export) —
    Exports a PKCS\#12 Compatible Certificate Store File to variable
-   [openssl\_pkcs12\_read](/ref/openssl.html#openssl_pkcs12_read) —
    Parse a PKCS\#12 Certificate Store into an array
-   [openssl\_pkcs7\_decrypt](/ref/openssl.html#openssl_pkcs7_decrypt) —
    Decrypts an S/MIME encrypted message
-   [openssl\_pkcs7\_encrypt](/ref/openssl.html#openssl_pkcs7_encrypt) —
    Encrypt an S/MIME message
-   [openssl\_pkcs7\_read](/ref/openssl.html#openssl_pkcs7_read) —
    Export the PKCS7 file to an array of PEM certificates
-   [openssl\_pkcs7\_sign](/ref/openssl.html#openssl_pkcs7_sign) — Sign
    an S/MIME message
-   [openssl\_pkcs7\_verify](/ref/openssl.html#openssl_pkcs7_verify) —
    Verifies the signature of an S/MIME signed message
-   [openssl\_pkey\_export\_to\_file](/ref/openssl.html#openssl_pkey_export_to_file)
    — Gets an exportable representation of a key into a file
-   [openssl\_pkey\_export](/ref/openssl.html#openssl_pkey_export) —
    Gets an exportable representation of a key into a string
-   [openssl\_pkey\_free](/ref/openssl.html#openssl_pkey_free) — Frees a
    private key
-   [openssl\_pkey\_get\_details](/ref/openssl.html#openssl_pkey_get_details)
    — Returns an array with the key details
-   [openssl\_pkey\_get\_private](/ref/openssl.html#openssl_pkey_get_private)
    — Get a private key
-   [openssl\_pkey\_get\_public](/ref/openssl.html#openssl_pkey_get_public)
    — Extract public key from certificate and prepare it for use
-   [openssl\_pkey\_new](/ref/openssl.html#openssl_pkey_new) — Generates
    a new private key
-   [openssl\_private\_decrypt](/ref/openssl.html#openssl_private_decrypt)
    — Decrypts data with private key
-   [openssl\_private\_encrypt](/ref/openssl.html#openssl_private_encrypt)
    — Encrypts data with private key
-   [openssl\_public\_decrypt](/ref/openssl.html#openssl_public_decrypt)
    — Decrypts data with public key
-   [openssl\_public\_encrypt](/ref/openssl.html#openssl_public_encrypt)
    — Encrypts data with public key
-   [openssl\_random\_pseudo\_bytes](/ref/openssl.html#openssl_random_pseudo_bytes)
    — Generate a pseudo-random string of bytes
-   [openssl\_seal](/ref/openssl.html#openssl_seal) — Seal (encrypt)
    data
-   [openssl\_sign](/ref/openssl.html#openssl_sign) — Generate signature
-   [openssl\_spki\_export\_challenge](/ref/openssl.html#openssl_spki_export_challenge)
    — Exports the challenge associated with a signed public key and
    challenge
-   [openssl\_spki\_export](/ref/openssl.html#openssl_spki_export) —
    Exports a valid PEM formatted public key signed public key and
    challenge
-   [openssl\_spki\_new](/ref/openssl.html#openssl_spki_new) — Generate
    a new signed public key and challenge
-   [openssl\_spki\_verify](/ref/openssl.html#openssl_spki_verify) —
    Verifies a signed public key and challenge
-   [openssl\_verify](/ref/openssl.html#openssl_verify) — Verify
    signature
-   [openssl\_x509\_check\_private\_key](/ref/openssl.html#openssl_x509_check_private_key)
    — Checks if a private key corresponds to a certificate
-   [openssl\_x509\_checkpurpose](/ref/openssl.html#openssl_x509_checkpurpose)
    — Verifies if a certificate can be used for a particular purpose
-   [openssl\_x509\_export\_to\_file](/ref/openssl.html#openssl_x509_export_to_file)
    — Exports a certificate to file
-   [openssl\_x509\_export](/ref/openssl.html#openssl_x509_export) —
    Exports a certificate as a string
-   [openssl\_x509\_fingerprint](/ref/openssl.html#openssl_x509_fingerprint)
    — Calculates the fingerprint, or digest, of a given X.509
    certificate
-   [openssl\_x509\_free](/ref/openssl.html#openssl_x509_free) — Free
    certificate resource
-   [openssl\_x509\_parse](/ref/openssl.html#openssl_x509_parse) — Parse
    an X509 certificate and return the information as an array
-   [openssl\_x509\_read](/ref/openssl.html#openssl_x509_read) — Parse
    an X.509 certificate and return a resource identifier for it
-   [openssl\_x509\_verify](/ref/openssl.html#openssl_x509_verify) —
    Verifies digital signature of x509 certificate against a public key

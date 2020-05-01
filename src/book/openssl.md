OpenSSL
=======

**Table of Contents**

-   [Introduction](/intro/openssl.html)
-   [Installing/Configuring](/openssl/setup.html)
    -   [Requirements](/openssl/setup.html#Requirements)
    -   [Installation](/openssl/setup.html#Installation)
    -   [Runtime
        Configuration](/openssl/setup.html#Runtime%20Configuration)
    -   [Resource Types](/openssl/setup.html#Resource%20Types)
-   [Predefined Constants](/openssl/constants.html)
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
-   [Key/Certificate parameters](/openssl/certparams.html)
-   [Certificate Verification](/openssl/cert/verification.html)
-   [OpenSSL Functions](/ref/openssl.html)
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
    -   [openssl\_csr\_new](/ref/openssl.html#openssl_csr_new) —
        Generates a CSR
    -   [openssl\_csr\_sign](/ref/openssl.html#openssl_csr_sign) — Sign
        a CSR with another certificate (or itself) and generate a
        certificate
    -   [openssl\_decrypt](/ref/openssl.html#openssl_decrypt) — Decrypts
        data
    -   [openssl\_dh\_compute\_key](/ref/openssl.html#openssl_dh_compute_key)
        — Computes shared secret for public value of remote DH public
        key and local DH key
    -   [openssl\_digest](/ref/openssl.html#openssl_digest) — Computes a
        digest
    -   [openssl\_encrypt](/ref/openssl.html#openssl_encrypt) — Encrypts
        data
    -   [openssl\_error\_string](/ref/openssl.html#openssl_error_string)
        — Return openSSL error message
    -   [openssl\_free\_key](/ref/openssl.html#openssl_free_key) — Free
        key resource
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
    -   [openssl\_get\_publickey](/ref/openssl.html#openssl_get_publickey)
        — Alias of openssl\_pkey\_get\_public
    -   [openssl\_open](/ref/openssl.html#openssl_open) — Open sealed
        data
    -   [openssl\_pbkdf2](/ref/openssl.html#openssl_pbkdf2) — Generates
        a PKCS5 v2 PBKDF2 string
    -   [openssl\_pkcs12\_export\_to\_file](/ref/openssl.html#openssl_pkcs12_export_to_file)
        — Exports a PKCS\#12 Compatible Certificate Store File
    -   [openssl\_pkcs12\_export](/ref/openssl.html#openssl_pkcs12_export)
        — Exports a PKCS\#12 Compatible Certificate Store File to
        variable
    -   [openssl\_pkcs12\_read](/ref/openssl.html#openssl_pkcs12_read) —
        Parse a PKCS\#12 Certificate Store into an array
    -   [openssl\_pkcs7\_decrypt](/ref/openssl.html#openssl_pkcs7_decrypt)
        — Decrypts an S/MIME encrypted message
    -   [openssl\_pkcs7\_encrypt](/ref/openssl.html#openssl_pkcs7_encrypt)
        — Encrypt an S/MIME message
    -   [openssl\_pkcs7\_read](/ref/openssl.html#openssl_pkcs7_read) —
        Export the PKCS7 file to an array of PEM certificates
    -   [openssl\_pkcs7\_sign](/ref/openssl.html#openssl_pkcs7_sign) —
        Sign an S/MIME message
    -   [openssl\_pkcs7\_verify](/ref/openssl.html#openssl_pkcs7_verify)
        — Verifies the signature of an S/MIME signed message
    -   [openssl\_pkey\_export\_to\_file](/ref/openssl.html#openssl_pkey_export_to_file)
        — Gets an exportable representation of a key into a file
    -   [openssl\_pkey\_export](/ref/openssl.html#openssl_pkey_export) —
        Gets an exportable representation of a key into a string
    -   [openssl\_pkey\_free](/ref/openssl.html#openssl_pkey_free) —
        Frees a private key
    -   [openssl\_pkey\_get\_details](/ref/openssl.html#openssl_pkey_get_details)
        — Returns an array with the key details
    -   [openssl\_pkey\_get\_private](/ref/openssl.html#openssl_pkey_get_private)
        — Get a private key
    -   [openssl\_pkey\_get\_public](/ref/openssl.html#openssl_pkey_get_public)
        — Extract public key from certificate and prepare it for use
    -   [openssl\_pkey\_new](/ref/openssl.html#openssl_pkey_new) —
        Generates a new private key
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
    -   [openssl\_sign](/ref/openssl.html#openssl_sign) — Generate
        signature
    -   [openssl\_spki\_export\_challenge](/ref/openssl.html#openssl_spki_export_challenge)
        — Exports the challenge associated with a signed public key and
        challenge
    -   [openssl\_spki\_export](/ref/openssl.html#openssl_spki_export) —
        Exports a valid PEM formatted public key signed public key and
        challenge
    -   [openssl\_spki\_new](/ref/openssl.html#openssl_spki_new) —
        Generate a new signed public key and challenge
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
    -   [openssl\_x509\_free](/ref/openssl.html#openssl_x509_free) —
        Free certificate resource
    -   [openssl\_x509\_parse](/ref/openssl.html#openssl_x509_parse) —
        Parse an X509 certificate and return the information as an array
    -   [openssl\_x509\_read](/ref/openssl.html#openssl_x509_read) —
        Parse an X.509 certificate and return a resource identifier for
        it
    -   [openssl\_x509\_verify](/ref/openssl.html#openssl_x509_verify) —
        Verifies digital signature of x509 certificate against a public
        key

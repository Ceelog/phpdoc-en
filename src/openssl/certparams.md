Key/Certificate parameters
==========================

Quite a few of the openssl functions require a key or a certificate
parameter. Following methods may be used to get them:

-   Certificates

    1.  <span class="simpara"> An X.509 resource returned from <span
        class="function">openssl\_x509\_read</span> </span>
    2.  <span class="simpara">A string having the format
        `file://path/to/cert.pem`; the named file must contain a PEM
        encoded certificate </span>
    3.  <span class="simpara"> A string containing the content of a
        certificate, PEM encoded, may start with -----BEGIN
        CERTIFICATE----- </span>

-   Certificate Signing Requests (CSRs)

    1.  <span class="simpara"> A CSR resource returned from <span
        class="function">openssl\_csr\_new</span> </span>
    2.  <span class="simpara">A string having the format
        `file://path/to/csr.pem`; the named file must contain a PEM
        encoded CSR </span>
    3.  <span class="simpara"> A string containing the content of a CSR,
        PEM encoded, may start with -----BEGIN CERTIFICATE REQUEST-----
        </span>

-   Public/Private Keys

    1.  <span class="simpara">A key resource returned from <span
        class="function">openssl\_get\_publickey</span> or <span
        class="function">openssl\_get\_privatekey</span> </span>
    2.  <span class="simpara">For public keys only: an X.509
        resource</span>
    3.  <span class="simpara">A string having the format
        `file://path/to/file.pem` - the named file must contain a PEM
        encoded certificate/private key (it may contain both) </span>
    4.  <span class="simpara"> A string containing the content of a
        certificate/key, PEM encoded, may start with -----BEGIN PUBLIC
        KEY----- </span>
    5.  <span class="simpara"> For private keys, you may also use the
        syntax *array($key, $passphrase)* where `$key` represents a key
        specified using the file:// or textual content notation above,
        and `$passphrase` represents a string containing the passphrase
        for that private key </span>

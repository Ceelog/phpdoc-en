Certificate Verification
========================

When calling a function that will verify a signature/certificate, the
`cainfo` parameter is an array containing file and directory names that
specify the locations of trusted CA files. If a directory is specified,
then it must be a correctly formed hashed directory as the **openssl**
command would use.

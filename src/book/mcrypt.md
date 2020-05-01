Mcrypt
======

**Table of Contents**

-   [Introduction](/intro/mcrypt.html)
-   [Installing/Configuring](/mcrypt/setup.html)
    -   [Requirements](/mcrypt/setup.html#Requirements)
    -   [Installation](/mcrypt/setup.html#Installation)
    -   [Runtime
        Configuration](/mcrypt/setup.html#Runtime%20Configuration)
    -   [Resource Types](/mcrypt/setup.html#Resource%20Types)
-   [Predefined Constants](/mcrypt/constants.html)
-   [Mcrypt ciphers](/mcrypt/ciphers.html)
-   [Examples](/mcrypt/examples.html)
-   [Mcrypt Functions](/ref/mcrypt.html)
    -   [mcrypt\_cbc](/ref/mcrypt.html#mcrypt_cbc) — Encrypts/decrypts
        data in CBC mode
    -   [mcrypt\_cfb](/ref/mcrypt.html#mcrypt_cfb) — Encrypts/decrypts
        data in CFB mode
    -   [mcrypt\_create\_iv](/ref/mcrypt.html#mcrypt_create_iv) —
        Creates an initialization vector (IV) from a random source
    -   [mcrypt\_decrypt](/ref/mcrypt.html#mcrypt_decrypt) — Decrypts
        crypttext with given parameters
    -   [mcrypt\_ecb](/ref/mcrypt.html#mcrypt_ecb) — Deprecated:
        Encrypts/decrypts data in ECB mode
    -   [mcrypt\_enc\_get\_algorithms\_name](/ref/mcrypt.html#mcrypt_enc_get_algorithms_name)
        — Returns the name of the opened algorithm
    -   [mcrypt\_enc\_get\_block\_size](/ref/mcrypt.html#mcrypt_enc_get_block_size)
        — Returns the blocksize of the opened algorithm
    -   [mcrypt\_enc\_get\_iv\_size](/ref/mcrypt.html#mcrypt_enc_get_iv_size)
        — Returns the size of the IV of the opened algorithm
    -   [mcrypt\_enc\_get\_key\_size](/ref/mcrypt.html#mcrypt_enc_get_key_size)
        — Returns the maximum supported keysize of the opened mode
    -   [mcrypt\_enc\_get\_modes\_name](/ref/mcrypt.html#mcrypt_enc_get_modes_name)
        — Returns the name of the opened mode
    -   [mcrypt\_enc\_get\_supported\_key\_sizes](/ref/mcrypt.html#mcrypt_enc_get_supported_key_sizes)
        — Returns an array with the supported keysizes of the opened
        algorithm
    -   [mcrypt\_enc\_is\_block\_algorithm\_mode](/ref/mcrypt.html#mcrypt_enc_is_block_algorithm_mode)
        — Checks whether the encryption of the opened mode works on
        blocks
    -   [mcrypt\_enc\_is\_block\_algorithm](/ref/mcrypt.html#mcrypt_enc_is_block_algorithm)
        — Checks whether the algorithm of the opened mode is a block
        algorithm
    -   [mcrypt\_enc\_is\_block\_mode](/ref/mcrypt.html#mcrypt_enc_is_block_mode)
        — Checks whether the opened mode outputs blocks
    -   [mcrypt\_enc\_self\_test](/ref/mcrypt.html#mcrypt_enc_self_test)
        — Runs a self test on the opened module
    -   [mcrypt\_encrypt](/ref/mcrypt.html#mcrypt_encrypt) — Encrypts
        plaintext with given parameters
    -   [mcrypt\_generic\_deinit](/ref/mcrypt.html#mcrypt_generic_deinit)
        — This function deinitializes an encryption module
    -   [mcrypt\_generic\_end](/ref/mcrypt.html#mcrypt_generic_end) —
        This function terminates encryption
    -   [mcrypt\_generic\_init](/ref/mcrypt.html#mcrypt_generic_init) —
        This function initializes all buffers needed for encryption
    -   [mcrypt\_generic](/ref/mcrypt.html#mcrypt_generic) — This
        function encrypts data
    -   [mcrypt\_get\_block\_size](/ref/mcrypt.html#mcrypt_get_block_size)
        — Gets the block size of the specified cipher
    -   [mcrypt\_get\_cipher\_name](/ref/mcrypt.html#mcrypt_get_cipher_name)
        — Gets the name of the specified cipher
    -   [mcrypt\_get\_iv\_size](/ref/mcrypt.html#mcrypt_get_iv_size) —
        Returns the size of the IV belonging to a specific cipher/mode
        combination
    -   [mcrypt\_get\_key\_size](/ref/mcrypt.html#mcrypt_get_key_size) —
        Gets the key size of the specified cipher
    -   [mcrypt\_list\_algorithms](/ref/mcrypt.html#mcrypt_list_algorithms)
        — Gets an array of all supported ciphers
    -   [mcrypt\_list\_modes](/ref/mcrypt.html#mcrypt_list_modes) — Gets
        an array of all supported modes
    -   [mcrypt\_module\_close](/ref/mcrypt.html#mcrypt_module_close) —
        Closes the mcrypt module
    -   [mcrypt\_module\_get\_algo\_block\_size](/ref/mcrypt.html#mcrypt_module_get_algo_block_size)
        — Returns the blocksize of the specified algorithm
    -   [mcrypt\_module\_get\_algo\_key\_size](/ref/mcrypt.html#mcrypt_module_get_algo_key_size)
        — Returns the maximum supported keysize of the opened mode
    -   [mcrypt\_module\_get\_supported\_key\_sizes](/ref/mcrypt.html#mcrypt_module_get_supported_key_sizes)
        — Returns an array with the supported keysizes of the opened
        algorithm
    -   [mcrypt\_module\_is\_block\_algorithm\_mode](/ref/mcrypt.html#mcrypt_module_is_block_algorithm_mode)
        — Returns if the specified module is a block algorithm or not
    -   [mcrypt\_module\_is\_block\_algorithm](/ref/mcrypt.html#mcrypt_module_is_block_algorithm)
        — This function checks whether the specified algorithm is a
        block algorithm
    -   [mcrypt\_module\_is\_block\_mode](/ref/mcrypt.html#mcrypt_module_is_block_mode)
        — Returns if the specified mode outputs blocks or not
    -   [mcrypt\_module\_open](/ref/mcrypt.html#mcrypt_module_open) —
        Opens the module of the algorithm and the mode to be used
    -   [mcrypt\_module\_self\_test](/ref/mcrypt.html#mcrypt_module_self_test)
        — This function runs a self test on the specified module
    -   [mcrypt\_ofb](/ref/mcrypt.html#mcrypt_ofb) — Encrypts/decrypts
        data in OFB mode
    -   [mdecrypt\_generic](/ref/mcrypt.html#mdecrypt_generic) —
        Decrypts data

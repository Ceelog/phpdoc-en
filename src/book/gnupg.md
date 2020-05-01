GNU Privacy Guard
=================

**Table of Contents**

-   [Introduction](/intro/gnupg.html)
-   [Installing/Configuring](/gnupg/setup.html)
    -   [Requirements](/gnupg/setup.html#Requirements)
    -   [Installation](/gnupg/setup.html#Installation)
    -   [Runtime
        Configuration](/gnupg/setup.html#Runtime%20Configuration)
    -   [Resource Types](/gnupg/setup.html#Resource%20Types)
-   [Predefined Constants](/gnupg/constants.html)
-   [Examples](/gnupg/examples.html)
    -   [Clearsign text](/gnupg/examples.html#Clearsign%20text)
-   [GnuPG Functions](/ref/gnupg.html)
    -   [gnupg\_adddecryptkey](/ref/gnupg.html#gnupg_adddecryptkey) —
        Add a key for decryption
    -   [gnupg\_addencryptkey](/ref/gnupg.html#gnupg_addencryptkey) —
        Add a key for encryption
    -   [gnupg\_addsignkey](/ref/gnupg.html#gnupg_addsignkey) — Add a
        key for signing
    -   [gnupg\_cleardecryptkeys](/ref/gnupg.html#gnupg_cleardecryptkeys)
        — Removes all keys which were set for decryption before
    -   [gnupg\_clearencryptkeys](/ref/gnupg.html#gnupg_clearencryptkeys)
        — Removes all keys which were set for encryption before
    -   [gnupg\_clearsignkeys](/ref/gnupg.html#gnupg_clearsignkeys) —
        Removes all keys which were set for signing before
    -   [gnupg\_decrypt](/ref/gnupg.html#gnupg_decrypt) — Decrypts a
        given text
    -   [gnupg\_decryptverify](/ref/gnupg.html#gnupg_decryptverify) —
        Decrypts and verifies a given text
    -   [gnupg\_encrypt](/ref/gnupg.html#gnupg_encrypt) — Encrypts a
        given text
    -   [gnupg\_encryptsign](/ref/gnupg.html#gnupg_encryptsign) —
        Encrypts and signs a given text
    -   [gnupg\_export](/ref/gnupg.html#gnupg_export) — Exports a key
    -   [gnupg\_geterror](/ref/gnupg.html#gnupg_geterror) — Returns the
        errortext, if a function fails
    -   [gnupg\_getprotocol](/ref/gnupg.html#gnupg_getprotocol) —
        Returns the currently active protocol for all operations
    -   [gnupg\_import](/ref/gnupg.html#gnupg_import) — Imports a key
    -   [gnupg\_init](/ref/gnupg.html#gnupg_init) — Initialize a
        connection
    -   [gnupg\_keyinfo](/ref/gnupg.html#gnupg_keyinfo) — Returns an
        array with information about all keys that matches the given
        pattern
    -   [gnupg\_setarmor](/ref/gnupg.html#gnupg_setarmor) — Toggle
        armored output
    -   [gnupg\_seterrormode](/ref/gnupg.html#gnupg_seterrormode) — Sets
        the mode for error\_reporting
    -   [gnupg\_setsignmode](/ref/gnupg.html#gnupg_setsignmode) — Sets
        the mode for signing
    -   [gnupg\_sign](/ref/gnupg.html#gnupg_sign) — Signs a given text
    -   [gnupg\_verify](/ref/gnupg.html#gnupg_verify) — Verifies a
        signed text

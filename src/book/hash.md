HASH Message Digest Framework
=============================

**Table of Contents**

-   [Introduction](/intro/hash.html)
-   [Installing/Configuring](/hash/setup.html)
    -   [Requirements](/hash/setup.html#Requirements)
    -   [Installation](/hash/setup.html#Installation)
    -   [Runtime
        Configuration](/hash/setup.html#Runtime%20Configuration)
    -   [Resource Types](/hash/setup.html#Resource%20Types)
-   [Predefined Constants](/hash/constants.html)
-   [HashContext](/class/hashcontext.html) — The HashContext class
    -   [HashContext::\_\_construct](/class/hashcontext.html#HashContext::__construct)
        — Private constructor to disallow direct instantiation
-   [Hash Functions](/ref/hash.html)
    -   [hash\_algos](/ref/hash.html#hash_algos) — Return a list of
        registered hashing algorithms
    -   [hash\_copy](/ref/hash.html#hash_copy) — Copy hashing context
    -   [hash\_equals](/ref/hash.html#hash_equals) — Timing attack safe
        string comparison
    -   [hash\_file](/ref/hash.html#hash_file) — Generate a hash value
        using the contents of a given file
    -   [hash\_final](/ref/hash.html#hash_final) — Finalize an
        incremental hash and return resulting digest
    -   [hash\_hkdf](/ref/hash.html#hash_hkdf) — Generate a HKDF key
        derivation of a supplied key input
    -   [hash\_hmac\_algos](/ref/hash.html#hash_hmac_algos) — Return a
        list of registered hashing algorithms suitable for hash\_hmac
    -   [hash\_hmac\_file](/ref/hash.html#hash_hmac_file) — Generate a
        keyed hash value using the HMAC method and the contents of a
        given file
    -   [hash\_hmac](/ref/hash.html#hash_hmac) — Generate a keyed hash
        value using the HMAC method
    -   [hash\_init](/ref/hash.html#hash_init) — Initialize an
        incremental hashing context
    -   [hash\_pbkdf2](/ref/hash.html#hash_pbkdf2) — Generate a PBKDF2
        key derivation of a supplied password
    -   [hash\_update\_file](/ref/hash.html#hash_update_file) — Pump
        data into an active hashing context from a file
    -   [hash\_update\_stream](/ref/hash.html#hash_update_stream) — Pump
        data into an active hashing context from an open stream
    -   [hash\_update](/ref/hash.html#hash_update) — Pump data into an
        active hashing context
    -   [hash](/ref/hash.html#hash) — Generate a hash value (message
        digest)

Introduction
------------

Class synopsis
--------------

**HashContext**

<span class="ooclass"> class **HashContext** </span> {

/\* Methods \*/

<span class="modifier">private</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

}

HashContext::\_\_construct
==========================

Private constructor to disallow direct instantiation

### Description

<span class="modifier">private</span> <span
class="methodname">HashContext::\_\_construct</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

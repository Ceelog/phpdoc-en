Zlib Compression
================

**Table of Contents**

-   [Introduction](/intro/zlib.html)
-   [Installing/Configuring](/zlib/setup.html)
    -   [Requirements](/zlib/setup.html#Requirements)
    -   [Installation](/zlib/setup.html#Installation)
    -   [Runtime
        Configuration](/zlib/setup.html#Runtime%20Configuration)
    -   [Resource Types](/zlib/setup.html#Resource%20Types)
-   [Predefined Constants](/zlib/constants.html)
-   [Examples](/zlib/examples.html)
-   [Zlib Functions](/ref/zlib.html)
    -   [deflate\_add](/ref/zlib.html#deflate_add) — Incrementally
        deflate data
    -   [deflate\_init](/ref/zlib.html#deflate_init) — Initialize an
        incremental deflate context
    -   [gzclose](/ref/zlib.html#gzclose) — Close an open gz-file
        pointer
    -   [gzcompress](/ref/zlib.html#gzcompress) — Compress a string
    -   [gzdecode](/ref/zlib.html#gzdecode) — Decodes a gzip compressed
        string
    -   [gzdeflate](/ref/zlib.html#gzdeflate) — Deflate a string
    -   [gzencode](/ref/zlib.html#gzencode) — Create a gzip compressed
        string
    -   [gzeof](/ref/zlib.html#gzeof) — Test for EOF on a gz-file
        pointer
    -   [gzfile](/ref/zlib.html#gzfile) — Read entire gz-file into an
        array
    -   [gzgetc](/ref/zlib.html#gzgetc) — Get character from gz-file
        pointer
    -   [gzgets](/ref/zlib.html#gzgets) — Get line from file pointer
    -   [gzgetss](/ref/zlib.html#gzgetss) — Get line from gz-file
        pointer and strip HTML tags
    -   [gzinflate](/ref/zlib.html#gzinflate) — Inflate a deflated
        string
    -   [gzopen](/ref/zlib.html#gzopen) — Open gz-file
    -   [gzpassthru](/ref/zlib.html#gzpassthru) — Output all remaining
        data on a gz-file pointer
    -   [gzputs](/ref/zlib.html#gzputs) — Alias of gzwrite
    -   [gzread](/ref/zlib.html#gzread) — Binary-safe gz-file read
    -   [gzrewind](/ref/zlib.html#gzrewind) — Rewind the position of a
        gz-file pointer
    -   [gzseek](/ref/zlib.html#gzseek) — Seek on a gz-file pointer
    -   [gztell](/ref/zlib.html#gztell) — Tell gz-file pointer
        read/write position
    -   [gzuncompress](/ref/zlib.html#gzuncompress) — Uncompress a
        compressed string
    -   [gzwrite](/ref/zlib.html#gzwrite) — Binary-safe gz-file write
    -   [inflate\_add](/ref/zlib.html#inflate_add) — Incrementally
        inflate encoded data
    -   [inflate\_get\_read\_len](/ref/zlib.html#inflate_get_read_len) —
        Get number of bytes read so far
    -   [inflate\_get\_status](/ref/zlib.html#inflate_get_status) — Get
        decompression status
    -   [inflate\_init](/ref/zlib.html#inflate_init) — Initialize an
        incremental inflate context
    -   [readgzfile](/ref/zlib.html#readgzfile) — Output a gz-file
    -   [zlib\_decode](/ref/zlib.html#zlib_decode) — Uncompress any
        raw/gzip/zlib encoded data
    -   [zlib\_encode](/ref/zlib.html#zlib_encode) — Compress data with
        the specified encoding
    -   [zlib\_get\_coding\_type](/ref/zlib.html#zlib_get_coding_type) —
        Returns the coding type used for output compression
-   [DeflateContext](/class/deflatecontext.html) — The DeflateContext
    class
-   [InflateContext](/class/inflatecontext.html) — The InflateContext
    class

Introduction
------------

A fully opaque class which replaces *zlib.deflate* resources as of PHP
8.0.0.

Class synopsis
--------------

**DeflateContext**

<span class="ooclass"> <span class="modifier">final</span> class
**DeflateContext** </span> {

}

Introduction
------------

A fully opaque class which replaces *zlib.inflate* resources as of PHP
8.0.0.

Class synopsis
--------------

**InflateContext**

<span class="ooclass"> <span class="modifier">final</span> class
**InflateContext** </span> {

}

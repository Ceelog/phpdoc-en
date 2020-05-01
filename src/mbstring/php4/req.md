PHP Character Encoding Requirements
===================================

Encodings of the following types are safely used with PHP.

-   A singlebyte encoding,

    -   <span class="simpara"> which has ASCII-compatible (ISO646
        compatible) mappings for the characters in range of *00h* to
        *7fh*. </span>

-   A multibyte encoding,

    -   <span class="simpara"> which has ASCII-compatible mappings for
        the characters in range of *00h* to *7fh*. </span>
    -   <span class="simpara"> which don't use ISO2022 escape sequences.
        </span>
    -   <span class="simpara"> which don't use a value from *00h* to
        *7fh* in any of the compounded bytes that represents a single
        character. </span>

These are examples of character encodings that are unlikely to work with
PHP.

    JIS, SJIS, ISO-2022-JP, BIG-5

Although PHP scripts written in any of those encodings might not work,
especially in the case where encoded strings appear as identifiers or
literals in the script, you can almost avoid using these encodings by
setting up the *mbstring*'s transparent encoding filter function for
incoming HTTP queries.

> **Note**:
>
> It's highly discouraged to use SJIS, BIG5, CP936, CP949 and GB18030
> for the internal encoding unless you are familiar with the parser, the
> scanner and the character encoding.

> **Note**:
>
> If you are connecting to a database with PHP, it is recommended that
> you use the same character encoding for both the database and the
> *internal encoding* for ease of use and better performance.
>
> If you are using PostgreSQL, the character encoding used in the
> database and the one used in PHP may differ as it supports automatic
> character set conversion between the backend and the frontend.

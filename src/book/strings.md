Strings
=======

**Table of Contents**

-   [Introduction](/intro/strings.html)
-   [Installing/Configuring](/strings/setup.html)
    -   [Requirements](/strings/setup.html#Requirements)
    -   [Installation](/strings/setup.html#Installation)
    -   [Runtime
        Configuration](/strings/setup.html#Runtime%20Configuration)
    -   [Resource Types](/strings/setup.html#Resource%20Types)
-   [Predefined Constants](/string/constants.html)
-   [String Functions](/ref/strings.html)
    -   [addcslashes](/ref/strings.html#addcslashes) — Quote string with
        slashes in a C style
    -   [addslashes](/ref/strings.html#addslashes) — Quote string with
        slashes
    -   [bin2hex](/ref/strings.html#bin2hex) — Convert binary data into
        hexadecimal representation
    -   [chop](/ref/strings.html#chop) — Alias of rtrim
    -   [chr](/ref/strings.html#chr) — Generate a single-byte string
        from a number
    -   [chunk\_split](/ref/strings.html#chunk_split) — Split a string
        into smaller chunks
    -   [convert\_cyr\_string](/ref/strings.html#convert_cyr_string) —
        Convert from one Cyrillic character set to another
    -   [convert\_uudecode](/ref/strings.html#convert_uudecode) — Decode
        a uuencoded string
    -   [convert\_uuencode](/ref/strings.html#convert_uuencode) —
        Uuencode a string
    -   [count\_chars](/ref/strings.html#count_chars) — Return
        information about characters used in a string
    -   [crc32](/ref/strings.html#crc32) — Calculates the crc32
        polynomial of a string
    -   [crypt](/ref/strings.html#crypt) — One-way string hashing
    -   [echo](/ref/strings.html#echo) — Output one or more strings
    -   [explode](/ref/strings.html#explode) — Split a string by a
        string
    -   [fprintf](/ref/strings.html#fprintf) — Write a formatted string
        to a stream
    -   [get\_html\_translation\_table](/ref/strings.html#get_html_translation_table)
        — Returns the translation table used by htmlspecialchars and
        htmlentities
    -   [hebrev](/ref/strings.html#hebrev) — Convert logical Hebrew text
        to visual text
    -   [hebrevc](/ref/strings.html#hebrevc) — Convert logical Hebrew
        text to visual text with newline conversion
    -   [hex2bin](/ref/strings.html#hex2bin) — Decodes a hexadecimally
        encoded binary string
    -   [html\_entity\_decode](/ref/strings.html#html_entity_decode) —
        Convert HTML entities to their corresponding characters
    -   [htmlentities](/ref/strings.html#htmlentities) — Convert all
        applicable characters to HTML entities
    -   [htmlspecialchars\_decode](/ref/strings.html#htmlspecialchars_decode)
        — Convert special HTML entities back to characters
    -   [htmlspecialchars](/ref/strings.html#htmlspecialchars) — Convert
        special characters to HTML entities
    -   [implode](/ref/strings.html#implode) — Join array elements with
        a string
    -   [join](/ref/strings.html#join) — Alias of implode
    -   [lcfirst](/ref/strings.html#lcfirst) — Make a string's first
        character lowercase
    -   [levenshtein](/ref/strings.html#levenshtein) — Calculate
        Levenshtein distance between two strings
    -   [localeconv](/ref/strings.html#localeconv) — Get numeric
        formatting information
    -   [ltrim](/ref/strings.html#ltrim) — Strip whitespace (or other
        characters) from the beginning of a string
    -   [md5\_file](/ref/strings.html#md5_file) — Calculates the md5
        hash of a given file
    -   [md5](/ref/strings.html#md5) — Calculate the md5 hash of a
        string
    -   [metaphone](/ref/strings.html#metaphone) — Calculate the
        metaphone key of a string
    -   [money\_format](/ref/strings.html#money_format) — Formats a
        number as a currency string
    -   [nl\_langinfo](/ref/strings.html#nl_langinfo) — Query language
        and locale information
    -   [nl2br](/ref/strings.html#nl2br) — Inserts HTML line breaks
        before all newlines in a string
    -   [number\_format](/ref/strings.html#number_format) — Format a
        number with grouped thousands
    -   [ord](/ref/strings.html#ord) — Convert the first byte of a
        string to a value between 0 and 255
    -   [parse\_str](/ref/strings.html#parse_str) — Parses the string
        into variables
    -   [print](/ref/strings.html#print) — Output a string
    -   [printf](/ref/strings.html#printf) — Output a formatted string
    -   [quoted\_printable\_decode](/ref/strings.html#quoted_printable_decode)
        — Convert a quoted-printable string to an 8 bit string
    -   [quoted\_printable\_encode](/ref/strings.html#quoted_printable_encode)
        — Convert a 8 bit string to a quoted-printable string
    -   [quotemeta](/ref/strings.html#quotemeta) — Quote meta characters
    -   [rtrim](/ref/strings.html#rtrim) — Strip whitespace (or other
        characters) from the end of a string
    -   [setlocale](/ref/strings.html#setlocale) — Set locale
        information
    -   [sha1\_file](/ref/strings.html#sha1_file) — Calculate the sha1
        hash of a file
    -   [sha1](/ref/strings.html#sha1) — Calculate the sha1 hash of a
        string
    -   [similar\_text](/ref/strings.html#similar_text) — Calculate the
        similarity between two strings
    -   [soundex](/ref/strings.html#soundex) — Calculate the soundex key
        of a string
    -   [sprintf](/ref/strings.html#sprintf) — Return a formatted string
    -   [sscanf](/ref/strings.html#sscanf) — Parses input from a string
        according to a format
    -   [str\_getcsv](/ref/strings.html#str_getcsv) — Parse a CSV string
        into an array
    -   [str\_ireplace](/ref/strings.html#str_ireplace) —
        Case-insensitive version of str\_replace
    -   [str\_pad](/ref/strings.html#str_pad) — Pad a string to a
        certain length with another string
    -   [str\_repeat](/ref/strings.html#str_repeat) — Repeat a string
    -   [str\_replace](/ref/strings.html#str_replace) — Replace all
        occurrences of the search string with the replacement string
    -   [str\_rot13](/ref/strings.html#str_rot13) — Perform the rot13
        transform on a string
    -   [str\_shuffle](/ref/strings.html#str_shuffle) — Randomly
        shuffles a string
    -   [str\_split](/ref/strings.html#str_split) — Convert a string to
        an array
    -   [str\_word\_count](/ref/strings.html#str_word_count) — Return
        information about words used in a string
    -   [strcasecmp](/ref/strings.html#strcasecmp) — Binary safe
        case-insensitive string comparison
    -   [strchr](/ref/strings.html#strchr) — Alias of strstr
    -   [strcmp](/ref/strings.html#strcmp) — Binary safe string
        comparison
    -   [strcoll](/ref/strings.html#strcoll) — Locale based string
        comparison
    -   [strcspn](/ref/strings.html#strcspn) — Find length of initial
        segment not matching mask
    -   [strip\_tags](/ref/strings.html#strip_tags) — Strip HTML and PHP
        tags from a string
    -   [stripcslashes](/ref/strings.html#stripcslashes) — Un-quote
        string quoted with addcslashes
    -   [stripos](/ref/strings.html#stripos) — Find the position of the
        first occurrence of a case-insensitive substring in a string
    -   [stripslashes](/ref/strings.html#stripslashes) — Un-quotes a
        quoted string
    -   [stristr](/ref/strings.html#stristr) — Case-insensitive strstr
    -   [strlen](/ref/strings.html#strlen) — Get string length
    -   [strnatcasecmp](/ref/strings.html#strnatcasecmp) — Case
        insensitive string comparisons using a "natural order" algorithm
    -   [strnatcmp](/ref/strings.html#strnatcmp) — String comparisons
        using a "natural order" algorithm
    -   [strncasecmp](/ref/strings.html#strncasecmp) — Binary safe
        case-insensitive string comparison of the first n characters
    -   [strncmp](/ref/strings.html#strncmp) — Binary safe string
        comparison of the first n characters
    -   [strpbrk](/ref/strings.html#strpbrk) — Search a string for any
        of a set of characters
    -   [strpos](/ref/strings.html#strpos) — Find the position of the
        first occurrence of a substring in a string
    -   [strrchr](/ref/strings.html#strrchr) — Find the last occurrence
        of a character in a string
    -   [strrev](/ref/strings.html#strrev) — Reverse a string
    -   [strripos](/ref/strings.html#strripos) — Find the position of
        the last occurrence of a case-insensitive substring in a string
    -   [strrpos](/ref/strings.html#strrpos) — Find the position of the
        last occurrence of a substring in a string
    -   [strspn](/ref/strings.html#strspn) — Finds the length of the
        initial segment of a string consisting entirely of characters
        contained within a given mask
    -   [strstr](/ref/strings.html#strstr) — Find the first occurrence
        of a string
    -   [strtok](/ref/strings.html#strtok) — Tokenize string
    -   [strtolower](/ref/strings.html#strtolower) — Make a string
        lowercase
    -   [strtoupper](/ref/strings.html#strtoupper) — Make a string
        uppercase
    -   [strtr](/ref/strings.html#strtr) — Translate characters or
        replace substrings
    -   [substr\_compare](/ref/strings.html#substr_compare) — Binary
        safe comparison of two strings from an offset, up to length
        characters
    -   [substr\_count](/ref/strings.html#substr_count) — Count the
        number of substring occurrences
    -   [substr\_replace](/ref/strings.html#substr_replace) — Replace
        text within a portion of a string
    -   [substr](/ref/strings.html#substr) — Return part of a string
    -   [trim](/ref/strings.html#trim) — Strip whitespace (or other
        characters) from the beginning and end of a string
    -   [ucfirst](/ref/strings.html#ucfirst) — Make a string's first
        character uppercase
    -   [ucwords](/ref/strings.html#ucwords) — Uppercase the first
        character of each word in a string
    -   [vfprintf](/ref/strings.html#vfprintf) — Write a formatted
        string to a stream
    -   [vprintf](/ref/strings.html#vprintf) — Output a formatted string
    -   [vsprintf](/ref/strings.html#vsprintf) — Return a formatted
        string
    -   [wordwrap](/ref/strings.html#wordwrap) — Wraps a string to a
        given number of characters
-   [Changelog](/changelog/strings.html)

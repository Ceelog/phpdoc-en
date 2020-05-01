Multibyte String
================

**Table of Contents**

-   [Introduction](/intro/mbstring.html)
-   [Installing/Configuring](/mbstring/setup.html)
    -   [Requirements](/mbstring/setup.html#Requirements)
    -   [Installation](/mbstring/setup.html#Installation)
    -   [Runtime
        Configuration](/mbstring/setup.html#Runtime%20Configuration)
    -   [Resource Types](/mbstring/setup.html#Resource%20Types)
-   [Predefined Constants](/mbstring/constants.html)
-   [Summaries of supported encodings](/mbstring/encodings.html)
-   [Basics of Japanese multi-byte encodings](/mbstring/ja-basic.html)
-   [HTTP Input and Output](/mbstring/http.html)
-   [Supported Character Encodings](/mbstring/supported-encodings.html)
-   [Function Overloading Feature](/mbstring/overload.html)
-   [PHP Character Encoding Requirements](/mbstring/php4/req.html)
-   [Multibyte String Functions](/ref/mbstring.html)
    -   [mb\_check\_encoding](/ref/mbstring.html#mb_check_encoding) —
        Check if strings are valid for the specified encoding
    -   [mb\_chr](/ref/mbstring.html#mb_chr) — Get a specific character
    -   [mb\_convert\_case](/ref/mbstring.html#mb_convert_case) —
        Perform case folding on a string
    -   [mb\_convert\_encoding](/ref/mbstring.html#mb_convert_encoding)
        — Convert character encoding
    -   [mb\_convert\_kana](/ref/mbstring.html#mb_convert_kana) —
        Convert "kana" one from another ("zen-kaku", "han-kaku" and
        more)
    -   [mb\_convert\_variables](/ref/mbstring.html#mb_convert_variables)
        — Convert character code in variable(s)
    -   [mb\_decode\_mimeheader](/ref/mbstring.html#mb_decode_mimeheader)
        — Decode string in MIME header field
    -   [mb\_decode\_numericentity](/ref/mbstring.html#mb_decode_numericentity)
        — Decode HTML numeric string reference to character
    -   [mb\_detect\_encoding](/ref/mbstring.html#mb_detect_encoding) —
        Detect character encoding
    -   [mb\_detect\_order](/ref/mbstring.html#mb_detect_order) —
        Set/Get character encoding detection order
    -   [mb\_encode\_mimeheader](/ref/mbstring.html#mb_encode_mimeheader)
        — Encode string for MIME header
    -   [mb\_encode\_numericentity](/ref/mbstring.html#mb_encode_numericentity)
        — Encode character to HTML numeric string reference
    -   [mb\_encoding\_aliases](/ref/mbstring.html#mb_encoding_aliases)
        — Get aliases of a known encoding type
    -   [mb\_ereg\_match](/ref/mbstring.html#mb_ereg_match) — Regular
        expression match for multibyte string
    -   [mb\_ereg\_replace\_callback](/ref/mbstring.html#mb_ereg_replace_callback)
        — Perform a regular expression search and replace with multibyte
        support using a callback
    -   [mb\_ereg\_replace](/ref/mbstring.html#mb_ereg_replace) —
        Replace regular expression with multibyte support
    -   [mb\_ereg\_search\_getpos](/ref/mbstring.html#mb_ereg_search_getpos)
        — Returns start point for next regular expression match
    -   [mb\_ereg\_search\_getregs](/ref/mbstring.html#mb_ereg_search_getregs)
        — Retrieve the result from the last multibyte regular expression
        match
    -   [mb\_ereg\_search\_init](/ref/mbstring.html#mb_ereg_search_init)
        — Setup string and regular expression for a multibyte regular
        expression match
    -   [mb\_ereg\_search\_pos](/ref/mbstring.html#mb_ereg_search_pos) —
        Returns position and length of a matched part of the multibyte
        regular expression for a predefined multibyte string
    -   [mb\_ereg\_search\_regs](/ref/mbstring.html#mb_ereg_search_regs)
        — Returns the matched part of a multibyte regular expression
    -   [mb\_ereg\_search\_setpos](/ref/mbstring.html#mb_ereg_search_setpos)
        — Set start point of next regular expression match
    -   [mb\_ereg\_search](/ref/mbstring.html#mb_ereg_search) —
        Multibyte regular expression match for predefined multibyte
        string
    -   [mb\_ereg](/ref/mbstring.html#mb_ereg) — Regular expression
        match with multibyte support
    -   [mb\_eregi\_replace](/ref/mbstring.html#mb_eregi_replace) —
        Replace regular expression with multibyte support ignoring case
    -   [mb\_eregi](/ref/mbstring.html#mb_eregi) — Regular expression
        match ignoring case with multibyte support
    -   [mb\_get\_info](/ref/mbstring.html#mb_get_info) — Get internal
        settings of mbstring
    -   [mb\_http\_input](/ref/mbstring.html#mb_http_input) — Detect
        HTTP input character encoding
    -   [mb\_http\_output](/ref/mbstring.html#mb_http_output) — Set/Get
        HTTP output character encoding
    -   [mb\_internal\_encoding](/ref/mbstring.html#mb_internal_encoding)
        — Set/Get internal character encoding
    -   [mb\_language](/ref/mbstring.html#mb_language) — Set/Get current
        language
    -   [mb\_list\_encodings](/ref/mbstring.html#mb_list_encodings) —
        Returns an array of all supported encodings
    -   [mb\_ord](/ref/mbstring.html#mb_ord) — Get code point of
        character
    -   [mb\_output\_handler](/ref/mbstring.html#mb_output_handler) —
        Callback function converts character encoding in output buffer
    -   [mb\_parse\_str](/ref/mbstring.html#mb_parse_str) — Parse
        GET/POST/COOKIE data and set global variable
    -   [mb\_preferred\_mime\_name](/ref/mbstring.html#mb_preferred_mime_name)
        — Get MIME charset string
    -   [mb\_regex\_encoding](/ref/mbstring.html#mb_regex_encoding) —
        Set/Get character encoding for multibyte regex
    -   [mb\_regex\_set\_options](/ref/mbstring.html#mb_regex_set_options)
        — Set/Get the default options for mbregex functions
    -   [mb\_scrub](/ref/mbstring.html#mb_scrub) — Description
    -   [mb\_send\_mail](/ref/mbstring.html#mb_send_mail) — Send encoded
        mail
    -   [mb\_split](/ref/mbstring.html#mb_split) — Split multibyte
        string using regular expression
    -   [mb\_str\_split](/ref/mbstring.html#mb_str_split) — Given a
        multibyte string, return an array of its characters
    -   [mb\_strcut](/ref/mbstring.html#mb_strcut) — Get part of string
    -   [mb\_strimwidth](/ref/mbstring.html#mb_strimwidth) — Get
        truncated string with specified width
    -   [mb\_stripos](/ref/mbstring.html#mb_stripos) — Finds position of
        first occurrence of a string within another, case insensitive
    -   [mb\_stristr](/ref/mbstring.html#mb_stristr) — Finds first
        occurrence of a string within another, case insensitive
    -   [mb\_strlen](/ref/mbstring.html#mb_strlen) — Get string length
    -   [mb\_strpos](/ref/mbstring.html#mb_strpos) — Find position of
        first occurrence of string in a string
    -   [mb\_strrchr](/ref/mbstring.html#mb_strrchr) — Finds the last
        occurrence of a character in a string within another
    -   [mb\_strrichr](/ref/mbstring.html#mb_strrichr) — Finds the last
        occurrence of a character in a string within another, case
        insensitive
    -   [mb\_strripos](/ref/mbstring.html#mb_strripos) — Finds position
        of last occurrence of a string within another, case insensitive
    -   [mb\_strrpos](/ref/mbstring.html#mb_strrpos) — Find position of
        last occurrence of a string in a string
    -   [mb\_strstr](/ref/mbstring.html#mb_strstr) — Finds first
        occurrence of a string within another
    -   [mb\_strtolower](/ref/mbstring.html#mb_strtolower) — Make a
        string lowercase
    -   [mb\_strtoupper](/ref/mbstring.html#mb_strtoupper) — Make a
        string uppercase
    -   [mb\_strwidth](/ref/mbstring.html#mb_strwidth) — Return width of
        string
    -   [mb\_substitute\_character](/ref/mbstring.html#mb_substitute_character)
        — Set/Get substitution character
    -   [mb\_substr\_count](/ref/mbstring.html#mb_substr_count) — Count
        the number of substring occurrences
    -   [mb\_substr](/ref/mbstring.html#mb_substr) — Get part of string

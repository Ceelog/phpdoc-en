Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/mbstring/setup.html#Requirements)
-   [Installation](/mbstring/setup.html#Installation)
-   [Runtime
    Configuration](/mbstring/setup.html#Runtime%20Configuration)
-   [Resource Types](/mbstring/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

*mbstring* is a non-default extension. This means it is not enabled by
default. You must explicitly enable the module with the *configure*
option. See the <a href="/install.html" class="link">Install</a> section
for details.

The following configure options are related to the *mbstring* module.

-   **--enable-mbstring**: Enable *mbstring* functions. This option is
    required to use *mbstring* functions.

    <span class="productname">libmbfl</span> is necessary for
    *mbstring*. <span class="productname">libmbfl</span> is bundled with
    *mbstring*. Before PHP 7.3.0, if <span
    class="productname">libmbfl</span> is already installed on the
    system, **--with-libmbfl\[=DIR\]** can be specified to use the
    installed library.

-   **--disable-mbregex**: Disable regular expression functions with
    multibyte character support.

    <span class="productname">Oniguruma</span> is necessary for the
    regular expression functions with multibyte character support. <span
    class="productname">Oniguruma</span> is bundled with *mbstring*. As
    of PHP 5.4.0, if <span class="productname">Oniguruma</span> is
    already installed on the system, **--with-onig\[=DIR\]** can be
    specified to use the installed library. As of PHP 7.4.0
    **--with-onig** has been removed and pkg-config is now used to
    detect the libonig library.

    As of PHP 5.4.0 it is possible to disable the multibyte regex
    backtrack check by specifying **--disable-mbregex-backtrack**.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                                 | Default                             | Changeable       | Changelog                                                                                                                  |
|--------------------------------------------------------------------------------------|-------------------------------------|------------------|----------------------------------------------------------------------------------------------------------------------------|
| <a href="/mbstring/setup.html#" class="link">mbstring.language</a>                   | "neutral"                           | PHP\_INI\_ALL    | PHP\_INI\_PERDIR in PHP \<= 5.2.6.                                                                                         |
| <a href="/mbstring/setup.html#" class="link">mbstring.detect_order</a>               | NULL                                | PHP\_INI\_ALL    |                                                                                                                            |
| <a href="/mbstring/setup.html#" class="link">mbstring.http_input</a>                 | "pass"                              | PHP\_INI\_ALL    | Deprecated in PHP 5.6.0.                                                                                                   |
| <a href="/mbstring/setup.html#" class="link">mbstring.http_output</a>                | "pass"                              | PHP\_INI\_ALL    | Deprecated in PHP 5.6.0.                                                                                                   |
| <a href="/mbstring/setup.html#" class="link">mbstring.internal_encoding</a>          | NULL                                | PHP\_INI\_ALL    | Deprecated in PHP 5.6.0.                                                                                                   |
| mbstring.script\_encoding                                                            | NULL                                | PHP\_INI\_ALL    | Removed in PHP 5.4.0. Use <a href="/ini/core.html#ini.zend.script-encoding" class="link">zend.script_encoding</a> instead. |
| <a href="/mbstring/setup.html#" class="link">mbstring.substitute_character</a>       | NULL                                | PHP\_INI\_ALL    |                                                                                                                            |
| <a href="/mbstring/setup.html#" class="link">mbstring.func_overload</a>              | "0"                                 | PHP\_INI\_SYSTEM | PHP\_INI\_PERDIR in PHP \<= 5.2.6. Deprecated in PHP 7.2.0.                                                                |
| <a href="/mbstring/setup.html#" class="link">mbstring.encoding_translation</a>       | "0"                                 | PHP\_INI\_PERDIR |                                                                                                                            |
| <a href="/mbstring/setup.html#" class="link">mbstring.http_output_conv_mimetypes</a> | "^(text/\|application/xhtml\\+xml)" | PHP\_INI\_ALL    | Available as of PHP 5.3.0.                                                                                                 |
| <a href="/mbstring/setup.html#" class="link">mbstring.strict_detection</a>           | "0"                                 | PHP\_INI\_ALL    | Available as of PHP 5.1.2.                                                                                                 |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`mbstring.language` <span class="type">string</span>  
The default national language setting (NLS) used in mbstring. Note that
this option automagically defines *mbstring.internal\_encoding* and
*mbstring.internal\_encoding* should be placed after *mbstring.language*
in `php.ini`

`mbstring.encoding_translation` <span class="type">boolean</span>  
Enables the transparent character encoding filter for the incoming HTTP
queries, which performs detection and conversion of the input encoding
to the internal character encoding.

`mbstring.internal_encoding` <span class="type">string</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.6.0. Relying on this
feature is highly discouraged.

Defines the default internal character encoding.

PHP 5.6 and later users should leave this empty and set
<a href="/ini/core.html#ini.default-charset" class="link"><code class="parameter">default_charset</code></a>
instead.

`mbstring.http_input` <span class="type">string</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.6.0. Relying on this
feature is highly discouraged.

Defines the default HTTP input character encoding.

PHP 5.6 and later users should leave this empty and set
<a href="/ini/core.html#ini.default-charset" class="link"><code class="parameter">default_charset</code></a>
instead.

`mbstring.http_output` <span class="type">string</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.6.0. Relying on this
feature is highly discouraged.

Defines the default HTTP output character encoding (output will be
converted from the internal encoding to the HTTP output encoding upon
output).

PHP 5.6 and later users should leave this empty and set
<a href="/ini/core.html#ini.default-charset" class="link"><code class="parameter">default_charset</code></a>
instead.

`mbstring.detect_order` <span class="type">string</span>  
Defines default character code detection order. See also <span
class="function">mb\_detect\_order</span>.

`mbstring.substitute_character` <span class="type">string</span>  
Defines character to substitute for invalid character encoding. See
<span class="function">mb\_substitute\_character</span> for supported
values.

`mbstring.func_overload` <span class="type">string</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 7.2.0. Relying on this
feature is highly discouraged.

Overloads a set of single byte functions by the mbstring counterparts.
See
<a href="/mbstring/overload.html" class="link">Function overloading</a>
for more information.

This setting can only be changed from the `php.ini` file.

`mbstring.http_output_conv_mimetypes` <span class="type">string</span>  

`mbstring.strict_detection` <span class="type">boolean</span>  
Enables the strict encoding detection.

According to the
<a href="http://www.w3.org/TR/REC-html40/interact/forms.html#adef-accept-charset" class="link external">» HTML 4.01 specification</a>,
Web browsers are allowed to encode a form being submitted with a
character encoding different from the one used for the page. See <span
class="function">mb\_http\_input</span> to detect character encoding
used by browsers.

Although popular browsers are capable of giving a reasonably accurate
guess to the character encoding of a given HTML document, it would be
better to set the *charset* parameter in the *Content-Type* HTTP header
to the appropriate value by <span class="function">header</span> or
<a href="/ini/core.html#ini.sect.data-handling" class="link">default_charset</a>
ini setting.

**Example \#1 `php.ini` setting examples**

    ; Set default language
    mbstring.language        = Neutral; Set default language to Neutral(UTF-8) (default)
    mbstring.language        = English; Set default language to English 
    mbstring.language        = Japanese; Set default language to Japanese

    ;; Set default internal encoding
    ;; Note: Make sure to use character encoding works with PHP
    mbstring.internal_encoding    = UTF-8  ; Set internal encoding to UTF-8

    ;; HTTP input encoding translation is enabled.
    mbstring.encoding_translation = On

    ;; Set default HTTP input character encoding
    ;; Note: Script cannot change http_input setting.
    mbstring.http_input           = pass    ; No conversion. 
    mbstring.http_input           = auto    ; Set HTTP input to auto
                                    ; "auto" is expanded according to mbstring.language
    mbstring.http_input           = SJIS    ; Set HTTP input to SJIS
    mbstring.http_input           = UTF-8,SJIS,EUC-JP ; Specify order

    ;; Set default HTTP output character encoding 
    mbstring.http_output          = pass    ; No conversion
    mbstring.http_output          = UTF-8   ; Set HTTP output encoding to UTF-8

    ;; Set default character encoding detection order
    mbstring.detect_order         = auto    ; Set detect order to auto
    mbstring.detect_order         = ASCII,JIS,UTF-8,SJIS,EUC-JP ; Specify order

    ;; Set default substitute character
    mbstring.substitute_character = 12307   ; Specify Unicode value
    mbstring.substitute_character = none    ; Do not print character
    mbstring.substitute_character = long    ; Long Example: U+3000,JIS+7E7E

**Example \#2 `php.ini` setting for *EUC-JP* users**

    ;; Disable Output Buffering
    output_buffering      = Off

    ;; Set HTTP header charset
    default_charset       = EUC-JP    

    ;; Set default language to Japanese
    mbstring.language = Japanese

    ;; HTTP input encoding translation is enabled.
    mbstring.encoding_translation = On

    ;; Set HTTP input encoding conversion to auto
    mbstring.http_input   = auto 

    ;; Convert HTTP output to EUC-JP
    mbstring.http_output  = EUC-JP    

    ;; Set internal encoding to EUC-JP
    mbstring.internal_encoding = EUC-JP    

    ;; Do not print invalid characters
    mbstring.substitute_character = none   

**Example \#3 `php.ini` setting for *SJIS* users**

    ;; Enable Output Buffering
    output_buffering     = On

    ;; Set mb_output_handler to enable output conversion
    output_handler       = mb_output_handler

    ;; Set HTTP header charset
    default_charset      = Shift_JIS

    ;; Set default language to Japanese
    mbstring.language = Japanese

    ;; Set http input encoding conversion to auto
    mbstring.http_input  = auto 

    ;; Convert to SJIS
    mbstring.http_output = SJIS    

    ;; Set internal encoding to EUC-JP
    mbstring.internal_encoding = EUC-JP    

    ;; Do not print invalid characters
    mbstring.substitute_character = none   

Resource Types
--------------

This extension has no resource types defined.

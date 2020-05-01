Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/exif/setup.html#Requirements)
-   [Installation](/exif/setup.html#Installation)
-   [Runtime Configuration](/exif/setup.html#Runtime%20Configuration)
-   [Resource Types](/exif/setup.html#Resource%20Types)

Requirements
------------

Your PHP must be compiled in with *--enable-exif*. To enable multibyte
support in EXIF tags, the
<a href="/ref/mbstring.html" class="link">mbstring</a> extension must be
enabled by compiling PHP with *--enable-mbstring*. PHP does not require
any additional library for the exif module.

Windows only: The <a href="/ref/mbstring.html" class="link">mbstring</a>
extension must always be enabled. Note that
<a href="/ref/mbstring.html" class="link">mbstring</a> extension must be
loaded prior to EXIF in `php.ini`.

Installation
------------

To enable exif-support configure PHP with **--enable-exif**

Windows users must enable both the `php_mbstring.dll` and `php_exif.dll`
DLL's in `php.ini`. The `php_mbstring.dll` DLL must be loaded *before*
the `php_exif.dll` DLL so adjust your `php.ini` accordingly.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

Exif supports automatically conversion for Unicode and JIS character
encodings of user comments when module
<a href="/ref/mbstring.html" class="link">mbstring</a> is available.
This is done by first decoding the comment using the specified
characterset. The result is then encoded with another characterset which
should match your *HTTP* output.

| Name                                                                      | Default       | Changeable    | Changelog |
|---------------------------------------------------------------------------|---------------|---------------|-----------|
| <a href="/exif/setup.html#" class="link">exif.encode_unicode</a>          | "ISO-8859-15" | PHP\_INI\_ALL |           |
| <a href="/exif/setup.html#" class="link">exif.decode_unicode_motorola</a> | "UCS-2BE"     | PHP\_INI\_ALL |           |
| <a href="/exif/setup.html#" class="link">exif.decode_unicode_intel</a>    | "UCS-2LE"     | PHP\_INI\_ALL |           |
| <a href="/exif/setup.html#" class="link">exif.encode_jis</a>              | ""            | PHP\_INI\_ALL |           |
| <a href="/exif/setup.html#" class="link">exif.decode_jis_motorola</a>     | "JIS"         | PHP\_INI\_ALL |           |
| <a href="/exif/setup.html#" class="link">exif.decode_jis_intel</a>        | "JIS"         | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`exif.encode_unicode` <span class="type">string</span>  
*exif.encode\_unicode* defines the characterset UNICODE user comments
are handled. This defaults to ISO-8859-15 which should work for most non
Asian countries. The setting can be empty or must be an encoding
supported by mbstring. If it is empty the current internal encoding of
mbstring is used.

`exif.decode_unicode_motorola` <span class="type">string</span>  
*exif.decode\_unicode\_motorola* defines the image internal characterset
for Unicode encoded user comments if image is in motorola byte order
(big-endian). This setting cannot be empty but you can specify a list of
encodings supported by mbstring. The default is UCS-2BE.

`exif.decode_unicode_intel` <span class="type">string</span>  
*exif.decode\_unicode\_intel* defines the image internal characterset
for Unicode encoded user comments if image is in intel byte order
(little-endian). This setting cannot be empty but you can specify a list
of encodings supported by mbstring. The default is UCS-2LE.

`exif.encode_jis` <span class="type">string</span>  
*exif.encode\_jis* defines the characterset JIS user comments are
handled. This defaults to an empty value which forces the functions to
use the current internal encoding of mbstring.

`exif.decode_jis_motorola` <span class="type">string</span>  
*exif.decode\_jis\_motorola* defines the image internal characterset for
JIS encoded user comments if image is in motorola byte order
(big-endian). This setting cannot be empty but you can specify a list of
encodings supported by mbstring. The default is JIS.

`exif.decode_jis_intel` <span class="type">string</span>  
*exif.decode\_jis\_intel* defines the image internal characterset for
JIS encoded user comments if image is in intel byte order
(little-endian). This setting cannot be empty but you can specify a list
of encodings supported by mbstring. The default is JIS.

Resource Types
--------------

This extension has no resource types defined.

Supported Character Encodings
=============================

Currently the following character encodings are supported by the
*mbstring* module. Any of those Character encodings can be specified in
the *encoding* parameter of *mbstring* functions.

The following character encodings are supported in this PHP extension:

-   <span class="simpara">UCS-4\*</span>
-   <span class="simpara">UCS-4BE</span>
-   <span class="simpara">UCS-4LE\*</span>
-   <span class="simpara">UCS-2</span>
-   <span class="simpara">UCS-2BE</span>
-   <span class="simpara">UCS-2LE</span>
-   <span class="simpara">UTF-32\*</span>
-   <span class="simpara">UTF-32BE\*</span>
-   <span class="simpara">UTF-32LE\*</span>
-   <span class="simpara">UTF-16\*</span>
-   <span class="simpara">UTF-16BE\*</span>
-   <span class="simpara">UTF-16LE\*</span>
-   <span class="simpara">UTF-7</span>
-   <span class="simpara">UTF7-IMAP</span>
-   <span class="simpara">UTF-8\*</span>
-   <span class="simpara">ASCII\*</span>
-   <span class="simpara">EUC-JP\*</span>
-   <span class="simpara">SJIS\*</span>
-   <span class="simpara">eucJP-win\*</span>
-   <span class="simpara">SJIS-win\*</span>
-   <span class="simpara">ISO-2022-JP</span>
-   <span class="simpara">ISO-2022-JP-MS</span>
-   <span class="simpara">CP932</span>
-   <span class="simpara">CP51932</span>
-   <span class="simpara">SJIS-mac\*\* (alias: MacJapanese)</span>
-   <span class="simpara">SJIS-Mobile\#DOCOMO\*\* (alias:
    SJIS-DOCOMO)</span>
-   <span class="simpara">SJIS-Mobile\#KDDI\*\* (alias:
    SJIS-KDDI)</span>
-   <span class="simpara">SJIS-Mobile\#SOFTBANK\*\* (alias:
    SJIS-SOFTBANK)</span>
-   <span class="simpara">UTF-8-Mobile\#DOCOMO\*\* (alias:
    UTF-8-DOCOMO)</span>
-   <span class="simpara">UTF-8-Mobile\#KDDI-A\*\*</span>
-   <span class="simpara">UTF-8-Mobile\#KDDI-B\*\* (alias:
    UTF-8-KDDI)</span>
-   <span class="simpara">UTF-8-Mobile\#SOFTBANK\*\* (alias:
    UTF-8-SOFTBANK)</span>
-   <span class="simpara">ISO-2022-JP-MOBILE\#KDDI\*\* (alias:
    ISO-2022-JP-KDDI)</span>
-   <span class="simpara">JIS</span>
-   <span class="simpara">JIS-ms</span>
-   <span class="simpara">CP50220</span>
-   <span class="simpara">CP50220raw</span>
-   <span class="simpara">CP50221</span>
-   <span class="simpara">CP50222</span>
-   <span class="simpara">ISO-8859-1\*</span>
-   <span class="simpara">ISO-8859-2\*</span>
-   <span class="simpara">ISO-8859-3\*</span>
-   <span class="simpara">ISO-8859-4\*</span>
-   <span class="simpara">ISO-8859-5\*</span>
-   <span class="simpara">ISO-8859-6\*</span>
-   <span class="simpara">ISO-8859-7\*</span>
-   <span class="simpara">ISO-8859-8\*</span>
-   <span class="simpara">ISO-8859-9\*</span>
-   <span class="simpara">ISO-8859-10\*</span>
-   <span class="simpara">ISO-8859-13\*</span>
-   <span class="simpara">ISO-8859-14\*</span>
-   <span class="simpara">ISO-8859-15\*</span>
-   <span class="simpara">ISO-8859-16\*</span>
-   <span class="simpara">byte2be</span>
-   <span class="simpara">byte2le</span>
-   <span class="simpara">byte4be</span>
-   <span class="simpara">byte4le</span>
-   <span class="simpara">BASE64</span>
-   <span class="simpara">HTML-ENTITIES (alias: HTML)</span>
-   <span class="simpara">7bit</span>
-   <span class="simpara">8bit</span>
-   <span class="simpara">EUC-CN\*</span>
-   <span class="simpara">CP936</span>
-   <span class="simpara">GB18030\*\*</span>
-   <span class="simpara">HZ</span>
-   <span class="simpara">EUC-TW\*</span>
-   <span class="simpara">CP950</span>
-   <span class="simpara">BIG-5\*</span>
-   <span class="simpara">EUC-KR\*</span>
-   <span class="simpara">UHC (alias: CP949)</span>
-   <span class="simpara">ISO-2022-KR</span>
-   <span class="simpara">Windows-1251 (alias: CP1251)</span>
-   <span class="simpara">Windows-1252 (alias: CP1252)</span>
-   <span class="simpara">CP866 (alias: IBM866)</span>
-   <span class="simpara">KOI8-R\*</span>
-   <span class="simpara">KOI8-U\*</span>
-   <span class="simpara">ArmSCII-8 (alias: ArmSCII8)</span>

\* denotes encodings usable also in regular expressions.

\*\* denotes encodings available since PHP 5.4.0.

Any `php.ini` entry which accepts an encoding name can also use the
values "*auto*" and "*pass*". *mbstring* functions which accept an
encoding name can also use the value "*auto*".

If "*pass*" is set, no character encoding conversion is performed.

If "*auto*" is set, it is expanded to the list of encodings defined per
the
<a href="/mbstring/setup.html#Runtime%20Configuration" class="link">NLS</a>.
For instance, if the NLS is set to *Japanese*, the value is assumed to
be "*ASCII,JIS,UTF-8,EUC-JP,SJIS*".

See also <span class="function">mb\_detect\_order</span>

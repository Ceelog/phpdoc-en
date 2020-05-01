Character Encoding
==================

PHP's XML extension supports the
<a href="http://www.unicode.org/" class="link external">» Unicode</a>
character set through different <span class="glossterm">character
encoding</span>s. There are two types of character encodings, <span
class="glossterm">source encoding</span> and <span
class="glossterm">target encoding</span>. PHP's internal representation
of the document is always encoded with *UTF-8*.

Source encoding is done when an XML document is
<a href="/ref/xml.html#xml_parse" class="link">parsed</a>. Upon
<a href="/ref/xml.html#xml_parser_create" class="link">creating an XML parser</a>,
a source encoding can be specified (this encoding can not be changed
later in the XML parser's lifetime). The supported source encodings are
*ISO-8859-1*, *US-ASCII* and *UTF-8*. The former two are single-byte
encodings, which means that each character is represented by a single
byte. *UTF-8* can encode characters composed by a variable number of
bits (up to 21) in one to four bytes. The default source encoding used
by PHP is *ISO-8859-1*.

Target encoding is done when PHP passes data to XML handler functions.
When an XML parser is created, the target encoding is set to the same as
the source encoding, but this may be changed at any point. The target
encoding will affect character data as well as tag names and processing
instruction targets.

If the XML parser encounters characters outside the range that its
source encoding is capable of representing, it will return an error.

If PHP encounters characters in the parsed XML document that can not be
represented in the chosen target encoding, the problem characters will
be "demoted". Currently, this means that such characters are replaced by
a question mark.

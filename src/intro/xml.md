XML (eXtensible Markup Language) is a data format for structured
document interchange on the Web. It is a standard defined by The World
Wide Web consortium (W3C). Information about XML and related
technologies can be found at
<a href="http://www.w3.org/XML/" class="link external">» http://www.w3.org/XML/</a>.

This PHP extension implements support for James Clark's <span
class="productname">expat</span> in PHP. This toolkit lets you parse,
but not validate, XML documents. It supports three source
<a href="/xml/encoding.html" class="link">character encodings</a> also
provided by PHP: *US-ASCII*, *ISO-8859-1* and *UTF-8*. *UTF-16* is not
supported.

This extension lets you
<a href="/ref/xml.html#xml_parser_create" class="link">create XML parsers</a>
and then define *handlers* for different XML events. Each XML parser
also has a few
<a href="/ref/xml.html#xml_parser_set_option" class="link">parameters</a>
you can adjust.

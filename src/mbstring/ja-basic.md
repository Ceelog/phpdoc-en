Basics of Japanese multi-byte encodings
=======================================

Japanese characters can only be represented by multibyte encodings, and
multiple encoding standards are used depending on platform and text
purpose. To make matters worse, these encoding standards differ slightly
from one another. In order to create a web application which would be
usable in a Japanese environment, a developer has to keep these
complexities in mind to ensure that the proper character encodings are
used.

-   <span class="simpara">Storage for a character can be up to six
    bytes</span>
-   <span class="simpara"> Most Japanese multibyte characters appear
    twice as wide as single-byte characters. These characters are called
    "zen-kaku" in Japanese, which means "full width". Other, narrower,
    characters are called "han-kaku", which means "half width". The
    graphical properties of the characters, however, depends upon the
    type faces used to display them. </span>
-   <span class="simpara"> Some character encodings use shift(escape)
    sequences defined in ISO-2022 to switch the code map of the specific
    code area (*00h* to *7fh*). </span>
-   <span class="simpara"> ISO-2022-JP should be used in SMTP/NNTP, and
    headers and entities should be reencoded as per RFC requirements.
    Although those are not requisites, it's still a good idea because
    several popular user agents cannot recognize any other encoding
    methods. </span>
-   <span class="simpara"> Web pages created for mobile phone services
    such as
    <a href="http://www.nttdocomo.com/services/imode/" class="link external">» i-mode</a>
    or
    <a href="http://www.au.kddi.com/english/service/ezweb/index.html" class="link external">» EZweb</a>
    are supposed to use Shift\_JIS. </span>
-   <span class="simpara"> As of PHP 5.4.0, the pictogram characters
    used for mobile phone service such as
    <a href="http://www.nttdocomo.com/services/imode/" class="link external">» i-mode</a>
    or
    <a href="http://www.au.kddi.com/english/service/ezweb/index.html" class="link external">» EZweb</a>
    are supported. </span>

This module contains an interface to iconv character set conversion
facility. With this module, you can turn a string represented by a local
character set into the one represented by another character set, which
may be the Unicode character set. Supported character sets depend on the
iconv implementation of your system. Note that the iconv function on
some systems may not work as you expect. In such case, it'd be a good
idea to install the
<a href="http://www.gnu.org/software/libiconv/" class="link external">» GNU libiconv</a>
library. It will most likely end up with more consistent results.

This extension comes with various utility functions that help you to
write multilingual scripts. Let's have a look at the following sections
to explore the new features.

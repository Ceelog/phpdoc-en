List of Available Filters
=========================

**Table of Contents**

-   [String Filters](/filters/string.html)
-   [Conversion Filters](/filters/convert.html)
-   [Compression Filters](/filters/compression.html)
-   [Encryption Filters](/filters/encryption.html)

The following is a list of a few built-in stream filters for use with
<span class="function">stream\_filter\_append</span>. Your version of
PHP may have more filters (or fewer) than those listed here.

It is worth noting a slight asymmetry between <span
class="function">stream\_filter\_append</span> and <span
class="function">stream\_filter\_prepend</span>. Every PHP stream
contains a small *read buffer* where it stores blocks of data retrieved
from the filesystem or other resource in order to process data in the
most efficient manner. As soon as data is pulled from the resource into
the stream's internal buffer, it is immediately processed through any
attached filters whether the PHP application is actually ready for the
data or not. If data is sitting in the read buffer when a filter is
*appended*, this data will be immediately processed through that filter
making the fact that it was sitting in the buffer seem transparent.
However, if data is sitting in the read buffer when a filter is
*prepended*, this data will *NOT* be processed through that filter. It
will instead wait until the next block of data is retrieved from the
resource.

For a list of filters installed in your version of PHP use <span
class="function">stream\_get\_filters</span>.

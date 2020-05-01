How we generate the formats
---------------------------

This manual is written in XML using the
<a href="http://www.oasis-open.org/docbook/xml/" class="link external">» DocBook XML DTD</a>,
using
<a href="https://wiki.php.net/doc/phd/" class="link external">» PhD</a>
(The \[PH\]P based \[D\]ocBook renderer) for maintenance and formatting.

Using XML as a source format gives the ability to generate many output
formats from the source files, while only maintaining one source
document for all formats. The tool used for formatting the online manual
is
<a href="https://wiki.php.net/doc/phd/" class="link external">» PhD</a>.
We use
<a href="http://msdn.microsoft.com/library/en-us/htmlhelp/html/vsconhh1start.asp" class="link external">» Microsoft HTML Help Workshop</a>
to generate the <span class="productname">Windows HTML Help</span>
format of the manual, and of course PHP itself to do some additional
conversions and formatting.

The PHP manual is generated in various languages and formats, see
<a href="https://www.php.net/docs.php" class="link external">» https://www.php.net/docs.php</a>
for additional details. The XML source code may be downloaded from SVN
and viewed at
<a href="https://svn.php.net/viewvc/" class="link external">» https://svn.php.net/viewvc/</a>.
The documentation is stored in the *phpdoc* module.

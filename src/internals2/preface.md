This section of the manual is written for the `Hacker`: someone thinking
about getting their hands dirty, someone who wants an understanding of
internals in order to advance their PHP skills, or maybe someone looking
to write the next best extension. Whatever the reason, this section will
seek to provide a good understanding of the internals of PHP, how to
write extensions, how to understand existing code containing mystical
macros. All of the important internal functionality is documented here,
enough anyway to convince you to read the source.

Out of necessity, this section assumes the reader has a working
knowledge of the C programming language, and associated tools, like
compilers and terminal emulators and the like. You don't need to be the
next Alan Turing, but a working knowledge is none the less essential for
this section to be of any use. With just that working knowledge, this
section should be enough to get you well on the way to earning the title
`Hacker`, and you do have to earn it.

The documentation in this section is current as of PHP 5.3.3, deviations
in API functionality are duly noted in the appropriate sections.

**Warning**

This documentation is still under development. The original Zend
documentation is preserved in its entirety in the
<a href="/internals2/ze1.html" class="link">Zend Engine 1</a> section
for those who need it before this documentation is completed.

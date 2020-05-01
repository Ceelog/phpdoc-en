**Warning**

This feature was *DEPRECATED* in PHP 5.3.0, and *REMOVED* in PHP 7.0.0.

Alternatives to this feature include:

-   <a href="/book/pcre.html" class="link">PCRE</a> (for full regular
    expression support)
-   <span class="function">fnmatch</span> (for simpler shell style
    wildcard pattern matching)

**Tip**

PHP also supports regular expressions using a Perl-compatible syntax
using the <a href="/book/pcre.html" class="link">PCRE functions</a>.
Those functions support non-greedy matching, assertions, conditional
subpatterns, and a number of other features not supported by the
POSIX-extended regular expression syntax.

**Warning**

These regular expression functions are not binary-safe. The
<a href="/book/pcre.html" class="link">PCRE functions</a> are.

Regular expressions are used for complex string manipulation. PHP uses
the POSIX extended regular expressions as defined by POSIX 1003.2. For a
full description of POSIX regular expressions see the
<a href="http://www.tin.org/bin/man.cgi?section=7&amp;topic=regex" class="link external">» regex man pages</a>
included in the regex directory in the PHP distribution. It's in manpage
format, so you'll want to do something along the lines of **man
/usr/local/src/regex/regex.7** in order to read it.

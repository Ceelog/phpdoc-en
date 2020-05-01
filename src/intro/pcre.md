The syntax for patterns used in these functions closely resembles Perl.
The expression must be enclosed in the delimiters, a forward slash (/),
for example. Delimiters can be any non-alphanumeric, non-whitespace
ASCII character except the backslash (\\) and the null byte. If the
delimiter character has to be used in the expression itself, it needs to
be escaped by backslash. Perl-style (), {}, \[\], and \<\> matching
delimiters may also be used. See
<a href="/pcre/pattern.html#PCRE%20regex%20syntax" class="link">Pattern Syntax</a>
for detailed explanation.

The ending delimiter may be followed by various modifiers that affect
the matching. See
<a href="/pcre/pattern.html#Possible%20modifiers%20in%20regex%20patterns" class="link">Pattern Modifiers</a>.

PHP also supports regular expressions using a POSIX-extended syntax
using the
<a href="/book/regex.html" class="link">POSIX-extended regex functions</a>.

> **Note**:
>
> This extension maintains a global per-thread cache of compiled regular
> expressions (up to 4096).

**Warning**

You should be aware of some limitations of PCRE. Read
<a href="http://www.pcre.org/pcre.txt" class="link external">» http://www.pcre.org/pcre.txt</a>
for more info.

The PCRE library is a set of functions that implement regular expression
pattern matching using the same syntax and semantics as Perl 5, with
just a few differences (see below). The current implementation
corresponds to Perl 5.005.

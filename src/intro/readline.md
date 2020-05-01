The readline functions implement an interface to the GNU Readline
library. These are functions that provide editable command lines. An
example being the way Bash allows you to use the arrow keys to insert
characters or scroll through command history. Because of the interactive
nature of this library, it will be of little use for writing Web
applications, but may be useful when writing scripts used from a
<a href="/features/commandline.html" class="link">command line</a>.

As of PHP 7.1.0 this extension is supported on Windows.

**Caution**

The readline extension is not thread-safe! Thus, the usage of it with
any true thread safe SAPI (like Apache mod\_winnt) is strongly
discouraged.

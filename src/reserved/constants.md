Predefined Constants
--------------------

### Core Predefined Constants

These constants are defined by the PHP core. This includes PHP, the Zend
engine, and SAPI modules.

**`PHP_VERSION`** (<span class="type">string</span>)  
<span class="simpara"> The current PHP version as a string in
"major.minor.release\[extra\]" notation. </span>

**`PHP_MAJOR_VERSION`** (<span class="type">int</span>)  
<span class="simpara"> The current PHP "major" version as an integer
(e.g., int(5) from version "5.2.7-extra"). Available since PHP 5.2.7.
</span>

**`PHP_MINOR_VERSION`** (<span class="type">int</span>)  
<span class="simpara"> The current PHP "minor" version as an integer
(e.g., int(2) from version "5.2.7-extra"). Available since PHP 5.2.7.
</span>

**`PHP_RELEASE_VERSION`** (<span class="type">int</span>)  
<span class="simpara"> The current PHP "release" version as an integer
(e.g., int(7) from version "5.2.7-extra"). Available since PHP 5.2.7.
</span>

**`PHP_VERSION_ID`** (<span class="type">int</span>)  
<span class="simpara"> The current PHP version as an integer, useful for
version comparisons (e.g., int(50207) from version "5.2.7-extra").
Available since PHP 5.2.7. </span>

**`PHP_EXTRA_VERSION`** (<span class="type">string</span>)  
<span class="simpara"> The current PHP "extra" version as a string
(e.g., '-extra' from version "5.2.7-extra"). Often used by distribution
vendors to indicate a package version. Available since PHP 5.2.7.
</span>

**`PHP_ZTS`** (<span class="type">int</span>)  
<span class="simpara"> Available since PHP 5.2.7. </span>

**`PHP_DEBUG`** (<span class="type">int</span>)  
<span class="simpara"> Available since PHP 5.2.7. </span>

**`PHP_MAXPATHLEN`** (<span class="type">int</span>)  
<span class="simpara"> The maximum length of filenames (including path)
supported by this build of PHP. Available since PHP 5.3.0. </span>

**`PHP_OS`** (<span class="type">string</span>)  
<span class="simpara"> The operating system PHP was built for. </span>

**`PHP_OS_FAMILY`** (<span class="type">string</span>)  
<span class="simpara"> The operating system family PHP was built for.
One of *'Windows'*, *'BSD'*, *'Darwin'*, *'Solaris'*, *'Linux'* or
*'Unknown'*. Available as of PHP 7.2.0. </span>

**`PHP_SAPI`** (<span class="type">string</span>)  
<span class="simpara"> The Server API for this build of PHP. See also
<span class="function">php\_sapi\_name</span>. </span>

**`PHP_EOL`** (<span class="type">string</span>)  
<span class="simpara"> The correct 'End Of Line' symbol for this
platform. Available since PHP 5.0.2 </span>

**`PHP_INT_MAX`** (<span class="type">int</span>)  
<span class="simpara"> The largest integer supported in this build of
PHP. Usually int(2147483647) in 32 bit systems and
int(9223372036854775807) in 64 bit systems. Available since PHP 5.0.5
</span>

**`PHP_INT_MIN`** (<span class="type">int</span>)  
<span class="simpara"> The smallest integer supported in this build of
PHP. Usually int(-2147483648) in 32 bit systems and
int(-9223372036854775808) in 64 bit systems. Available since PHP 7.0.0.
Usually, PHP\_INT\_MIN === \~PHP\_INT\_MAX. </span>

**`PHP_INT_SIZE`** (<span class="type">int</span>)  
<span class="simpara"> The size of an integer in bytes in this build of
PHP. Available since PHP 5.0.5 </span>

**`PHP_FLOAT_DIG`** (<span class="type">int</span>)  
<span class="simpara"> Number of decimal digits that can be rounded into
a float and back without precision loss. Available as of PHP 7.2.0.
</span>

**`PHP_FLOAT_EPSILON`** (<span class="type">float</span>)  
<span class="simpara"> Smallest representable positive number x, so that
*x + 1.0 != 1.0*. Available as of PHP 7.2.0. </span>

**`PHP_FLOAT_MIN`** (<span class="type">float</span>)  
<span class="simpara"> Smallest representable *positive* floating point
number. If you need the smallest representable *negative* floating point
number, use *- PHP\_FLOAT\_MAX*. Available as of PHP 7.2.0. </span>

**`PHP_FLOAT_MAX`** (<span class="type">float</span>)  
<span class="simpara"> Largest representable floating point number.
Available as of PHP 7.2.0. </span>

**`DEFAULT_INCLUDE_PATH`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PEAR_INSTALL_DIR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PEAR_EXTENSION_DIR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PHP_EXTENSION_DIR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PHP_PREFIX`** (<span class="type">string</span>)  
<span class="simpara"> The value "--prefix" was set to at configure.
</span>

**`PHP_BINDIR`** (<span class="type">string</span>)  
<span class="simpara"> Specifies where the binaries were installed into.
</span>

**`PHP_BINARY`** (<span class="type">string</span>)  
<span class="simpara"> Specifies the PHP binary path during script
execution. Available since PHP 5.4. </span>

**`PHP_MANDIR`** (<span class="type">string</span>)  
<span class="simpara"> Specifies where the manpages were installed into.
Available since PHP 5.3.7. </span>

**`PHP_LIBDIR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PHP_DATADIR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PHP_SYSCONFDIR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PHP_LOCALSTATEDIR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PHP_CONFIG_FILE_PATH`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PHP_CONFIG_FILE_SCAN_DIR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`PHP_SHLIB_SUFFIX`** (<span class="type">string</span>)  
<span class="simpara"> The build-platform's shared library suffix, such
as "so" (most Unixes) or "dll" (Windows). </span>

**`PHP_FD_SETSIZE`** (<span class="type">string</span>)  
<span class="simpara"> The maximum number of file descriptors for select
system calls. Available as of PHP 7.1.0. </span>

**`E_ERROR`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_WARNING`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_PARSE`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_NOTICE`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_CORE_ERROR`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_CORE_WARNING`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_COMPILE_ERROR`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_COMPILE_WARNING`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_USER_ERROR`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_USER_WARNING`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_USER_NOTICE`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_RECOVERABLE_ERROR`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>.
Available since PHP 5.2.0 </span>

**`E_DEPRECATED`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>.
Available since PHP 5.3.0 </span>

**`E_USER_DEPRECATED`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>.
Available since PHP 5.3.0 </span>

**`E_ALL`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`E_STRICT`** (<span class="type">int</span>)  
<span class="simpara">
<a href="/errorfunc/constants.html" class="link">Error reporting constant</a>
</span>

**`__COMPILER_HALT_OFFSET__`** (<span class="type">int</span>)  
<span class="simpara"> Available since PHP 5.1.0 </span>

**`true`** (<span class="type">bool</span>)  
<span class="simpara"> See
<a href="/language/types/boolean.html" class="link">Booleans</a>.
</span>

**`false`** (<span class="type">bool</span>)  
<span class="simpara"> See
<a href="/language/types/boolean.html" class="link">Booleans</a>.
</span>

**`null`** (<span class="type">null</span>)  
<span class="simpara"> See
<a href="/language/types/null.html" class="link">Null</a>. </span>

**`PHP_WINDOWS_EVENT_CTRL_C`** (<span class="type">int</span>)  
<span class="simpara"> A Windows *CTRL+C* event. Available as of PHP
7.4.0 (Windows only). </span>

**`PHP_WINDOWS_EVENT_CTRL_BREAK`** (<span class="type">int</span>)  
<span class="simpara"> A Windows *CTRL+BREAK* event. Available as of PHP
7.4.0 (Windows only). </span>

See also:
<a href="/language/constants/predefined.html" class="link">Magic constants</a>.

### Standard Predefined Constants

All constants from
<a href="/extensions/membership.html#extensions.membership.core" class="link">core extensions</a>
are defined in PHP by default.

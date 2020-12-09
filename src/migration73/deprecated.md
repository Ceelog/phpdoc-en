Deprecated Features
-------------------

### PHP Core

#### Case-Insensitive Constants

The declaration of case-insensitive constants has been deprecated.
Passing **`true`** as the third argument to <span
class="function">define</span> will now generate a deprecation warning.
The use of case-insensitive constants with a case that differs from the
declaration is also deprecated.

#### Namespaced assert()

Declaring a function called *assert()* inside a namespace is deprecated.
The <span class="function">assert</span> function is subject to special
handling by the engine, which may lead to inconsistent behavior when
defining a namespaced function with the same name.

#### Searching Strings for non-string Needle

Passing a non-string needle to string search functions is deprecated. In
the future the needle will be interpreted as a string instead of an
ASCII codepoint. Depending on the intended behavior, you should either
explicitly cast the needle to string or perform an explicit call to
<span class="function">chr</span>. The following functions are affected:

-   <span class="simpara"><span class="function">strpos</span></span>
-   <span class="simpara"><span class="function">strrpos</span></span>
-   <span class="simpara"><span class="function">stripos</span></span>
-   <span class="simpara"><span class="function">strripos</span></span>
-   <span class="simpara"><span class="function">strstr</span></span>
-   <span class="simpara"><span class="function">strchr</span></span>
-   <span class="simpara"><span class="function">strrchr</span></span>
-   <span class="simpara"><span class="function">stristr</span></span>

#### Strip-Tags Streaming

The <span class="function">fgetss</span> function and the
<a href="/filters/string.html" class="link">string.strip_tags stream filter</a>
have been deprecated. This also affects the <span
class="methodname">SplFileObject::fgetss</span> method and <span
class="function">gzgetss</span> function.

### Data Filtering

The explicit usage of the constants **`FILTER_FLAG_SCHEME_REQUIRED`**
and **`FILTER_FLAG_HOST_REQUIRED`** is now deprecated; both are implied
for **`FILTER_VALIDATE_URL`** anyway.

### Image Processing and GD

<span class="function">image2wbmp</span> has been deprecated.

### Internationalization Functions

Usage of the **`Normalizer::NONE`** form throws a deprecation warning,
if PHP is linked with ICU ≥ 56.

### Multibyte String

The following undocumented *mbereg\_\*()* aliases have been deprecated.
Use the corresponding *mb\_ereg\_\*()* variants instead.

-   <span class="simpara"><span
    class="function">mbregex\_encoding</span></span>
-   <span class="simpara"><span class="function">mbereg</span></span>
-   <span class="simpara"><span class="function">mberegi</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_replace</span></span>
-   <span class="simpara"><span
    class="function">mberegi\_replace</span></span>
-   <span class="simpara"><span class="function">mbsplit</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_match</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_search</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_search\_pos</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_search\_regs</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_search\_init</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_search\_getregs</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_search\_getpos</span></span>
-   <span class="simpara"><span
    class="function">mbereg\_search\_setpos</span></span>

### ODBC and DB2 Functions (PDO\_ODBC)

The
<a href="/book/pdo.html#" class="link">pdo_odbc.db2_instance_name</a>
ini setting has been formally deprecated. It is deprecated in the
documentation as of PHP 5.1.1.

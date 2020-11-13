Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/iconv/setup.html#Requirements)
-   [Installation](/iconv/setup.html#Installation)
-   [Runtime Configuration](/iconv/setup.html#Runtime%20Configuration)
-   [Resource Types](/iconv/setup.html#Resource%20Types)

Requirements
------------

You will need nothing if the system you are using is one of the recent
POSIX-compliant systems because standard C libraries that are supplied
in them must provide iconv facility. Otherwise, you have to get the
<a href="http://www.gnu.org/software/libiconv/" class="link external">» libiconv</a>
library installed in your system.

Installation
------------

This extension is enabled by default, although it may be disabled by
compiling with **--without-iconv**.

The optional **--with-iconv\[=DIR\]** directive is used to specify the
location of *iconv* on the system that PHP is being compiled on,
otherwise only the default locations are scanned.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                  | Default | Changeable    | Changelog                |
|-----------------------------------------------------------------------|---------|---------------|--------------------------|
| <a href="/iconv/setup.html#" class="link">iconv.input_encoding</a>    | ""      | PHP\_INI\_ALL | Deprecated in PHP 5.6.0. |
| <a href="/iconv/setup.html#" class="link">iconv.output_encoding</a>   | ""      | PHP\_INI\_ALL | Deprecated in PHP 5.6.0. |
| <a href="/iconv/setup.html#" class="link">iconv.internal_encoding</a> | ""      | PHP\_INI\_ALL | Deprecated in PHP 5.6.0. |

Here's a short explanation of the configuration directives.

**Warning**

Some systems (like IBM AIX) use "ISO8859-1" instead of "ISO-8859-1" so
this value has to be used in configuration options and function
parameters.

`iconv.input_encoding` <span class="type">string</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.6.0. Relying on this
feature is highly discouraged.

PHP 5.6 and later users should leave this empty and set
<a href="/ini/core.html#ini.input-encoding" class="link">input_encoding</a>
instead.

`iconv.output_encoding` <span class="type">string</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.6.0. Relying on this
feature is highly discouraged.

PHP 5.6 and later users should leave this empty and set
<a href="/ini/core.html#ini.output-encoding" class="link">output_encoding</a>
instead.

`iconv.internal_encoding` <span class="type">string</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.6.0. Relying on this
feature is highly discouraged.

PHP 5.6 and later users should leave this empty and set
<a href="/ini/core.html#ini.default-charset" class="link"><code class="parameter">default_charset</code></a>
instead.

Resource Types
--------------

This extension has no resource types defined.

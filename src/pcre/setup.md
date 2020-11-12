Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/pcre/setup.html#Requirements)
-   [Installation](/pcre/setup.html#Installation)
-   [Runtime Configuration](/pcre/setup.html#Runtime%20Configuration)
-   [Resource Types](/pcre/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

The PCRE extension is a core PHP extension, so it is always enabled. By
default, this extension is compiled using the bundled PCRE library.
Alternatively, an external PCRE library can be used by passing in the
**--with-pcre-regex=DIR** configuration option where *DIR* is the
location of PCRE's include and library files. It is recommended to use
PCRE 8.10 or newer; as of PHP 7.3.0, PCRE2 is required.

PCRE's just-in-time compilation is supported by default, which can be
disabled with the **--without-pcre-jit** configuration option as of PHP
7.0.12.

The Windows version of PHP has built-in support for this extension. You
do not need to load any additional extensions in order to use these
functions.

PCRE is an active project and as it changes so does the PHP
functionality that relies upon it. It is possible that certain parts of
the PHP documentation is outdated, in that it may not cover the newest
features that PCRE provides. For a list of changes, see the
<a href="http://www.pcre.org/original/changelog.txt" class="link external">» PCRE library changelog</a>
and also the following bundled PCRE history:

| PHP Version   | Updated PCRE Version | Notes                                                                                                                      |
|---------------|----------------------|----------------------------------------------------------------------------------------------------------------------------|
| 7.4.12, 8.0.0 | 10.35                |                                                                                                                            |
| 7.4.6         | 10.34                |                                                                                                                            |
| 7.4.0         | 10.33                |                                                                                                                            |
| 7.3.0         | 10.32                |                                                                                                                            |
| 7.2.0         | 8.41                 |                                                                                                                            |
| 7.0.3         | 8.38                 | See CVE-2015-8383, CVE-2015-8386, CVE-2015-8387, CVE-2015-8389, CVE-2015-8390, CVE-2015-8391, CVE-2015-8393, CVE-2015-8394 |
| 7.0.0         | 8.37                 | See CVE-2015-2325, CVE-2015-2326                                                                                           |

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                              | Default   | Changeable    | Changelog                  |
|-------------------------------------------------------------------|-----------|---------------|----------------------------|
| <a href="/pcre/setup.html#" class="link">pcre.backtrack_limit</a> | "1000000" | PHP\_INI\_ALL | Available since PHP 5.2.0. |
| <a href="/pcre/setup.html#" class="link">pcre.recursion_limit</a> | "100000"  | PHP\_INI\_ALL | Available since PHP 5.2.0. |
| <a href="/pcre/setup.html#" class="link">pcre.jit</a>             | "1"       | PHP\_INI\_ALL | Available since PHP 7.0.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`pcre.backtrack_limit` <span class="type">int</span>  
PCRE's backtracking limit. Defaults to 100000 for PHP \< 5.3.7.

`pcre.recursion_limit` <span class="type">int</span>  
PCRE's recursion limit. Please note that if you set this value to a high
number you may consume all the available process stack and eventually
crash PHP (due to reaching the stack size limit imposed by the Operating
System).

`pcre.jit` <span class="type">bool</span>  
Whether PCRE's just-in-time compilation is going to be used.

Resource Types
--------------

This extension has no resource types defined.

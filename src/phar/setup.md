Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/phar/setup.html#Requirements)
-   [Installation](/phar/setup.html#Installation)
-   [Runtime Configuration](/phar/setup.html#Runtime%20Configuration)
-   [Resource Types](/phar/setup.html#Resource%20Types)

Requirements
------------

Phar requires PHP 5.2.0 or newer. Additional features require the
<a href="/book/spl.html" class="link">SPL</a> extension in order to take
advantage of iteration and array access to a Phar's file contents. The
*phar* stream does not require any additional extensions to function.

You may optionally wish to enable the
<a href="/book/zlib.html" class="link">zlib</a> and
<a href="/book/bzip2.html" class="link">bzip2</a> extensions to take
advantage of compressed phar support. In addition, to take advantage of
OpenSSL signing, the
<a href="/book/openssl.html" class="link">OpenSSL</a> extension must be
enabled.

Note that a bug in the
<a href="/filters/compression.html" class="link">zlib.deflate</a> stream
filter fixed in PHP version 5.2.6 and newer may cause truncation of gzip
and bzip2-compressed phar archives.

PHP 5.3 configured with *--enable-zend-multibyte* makes
<a href="/book/phar.html" class="link">phar</a> dependant on the ini
option *detect\_unicode*.

Installation
------------

The Phar extension is bundled with PHP as of PHP version 5.3.0, and
enabled by default. To disable Phar support, use **--disable-phar**.

Phar may be installed via the PECL extension with previous PHP versions,
and the
<a href="https://pecl.php.net/package/phar" class="link external">» Phar PECL page</a>
contains further information and history.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                           | Default | Changeable       | Changelog |
|----------------------------------------------------------------|---------|------------------|-----------|
| <a href="/phar/setup.html#" class="link">phar.readonly</a>     | "1"     | PHP\_INI\_ALL    |           |
| <a href="/phar/setup.html#" class="link">phar.require_hash</a> | "1"     | PHP\_INI\_ALL    |           |
| <a href="/phar/setup.html#" class="link">phar.cache_list</a>   | ""      | PHP\_INI\_SYSTEM |           |

Here's a short explanation of the configuration directives.

`phar.readonly` <span class="type">bool</span>  
This option disables creation or modification of Phar archives using the
*phar* stream or <span class="classname">Phar</span> object's write
support. This setting should always be enabled on production machines,
as the phar extension's convenient write support could allow
straightforward creation of a php-based virus when coupled with other
common security vulnerabilities.

> **Note**:
>
> This setting can only be unset in php.ini due to security reasons. If
> *phar.readonly* is disabled in php.ini, the user may enable
> *phar.readonly* in a script or disable it later. If *phar.readonly* is
> enabled in php.ini, a script may harmlessly "re-enable" the INI
> variable, but may not disable it.

`phar.require_hash` <span class="type">bool</span>  
This option will force all opened Phar archives to contain some kind of
signature (currently MD5, SHA1, SHA256 and SHA512 are supported), and
will refuse to process any Phar archive that does not contain a
signature.

> **Note**:
>
> This setting can only be unset in php.ini due to security reasons. If
> *phar.require\_hash* is disabled in php.ini, the user may enable
> *phar.require\_hash* in a script or disable it later. If
> *phar.require\_hash* is enabled in php.ini, a script may harmlessly
> "re-enable" the INI variable, but may not disable it.
>
> This setting does not affect reading plain tar files with the <span
> class="classname">PharData</span> class.

`phar.cache_list` <span class="type">string</span>  
Allows mapping phar archives to be pre-parsed at web server startup,
providing a performance improvement that brings running files out of a
phar archive very close to the speed of running those files from a
traditional disk-based installation.

**Example \#1 phar.cache\_list usage example**

    in php.ini (windows):
    phar.cache_list =C:\path\to\phar1.phar;C:\path\to\phar2.phar
    in php.ini (unix):
    phar.cache_list =/path/to/phar1.phar:/path/to/phar2.phar

Resource Types
--------------

The Phar extension provides the *phar* stream, which allows accessing
files contained within a phar transparently. See also the
<a href="/phar/fileformat.html" class="link">description of the Phar file format</a>.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/session/setup.html#Requirements)
-   [Installation](/session/setup.html#Installation)
-   [Runtime Configuration](/session/setup.html#Runtime%20Configuration)
-   [Resource Types](/session/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

> **Note**:
>
> Optionally you can use shared memory allocation (mm), developed by
> Ralf S. Engelschall, for session storage. You have to download
> <a href="http://www.ossp.org/pkg/lib/mm/" class="link external">» mm</a>
> and install it. This option is not available for Windows platforms.
> Note that the session storage module for mm does not guarantee that
> concurrent accesses to the same session are properly locked. It might
> be more appropriate to use a shared memory based filesystem (such as
> tmpfs on Solaris/Linux, or `/dev/md` on BSD) to store sessions in
> files, because they are properly locked. Session data is stored in
> memory thus web server restart deletes it.

Installation
------------

Session support is enabled in PHP by default. If you would not like to
build your PHP with session support, you should specify the
**--disable-session** option to configure. To use shared memory
allocation (mm) for session storage configure PHP **--with-mm\[=DIR\]**
.

The Windows version of PHP has built-in support for this extension. You
do not need to load any additional extensions in order to use these
functions.

> **Note**:
>
> By default, all data related to a particular session will be stored in
> a file in the directory specified by the session.save\_path INI
> option. A file for each session (regardless of if any data is
> associated with that session) will be created. This is due to the fact
> that a session is opened (a file is created) but no data is even
> written to that file. Note that this behavior is a side-effect of the
> limitations of working with the file system and it is possible that a
> custom session handler (such as one which uses a database) does not
> keep track of sessions which store no data.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                             | Default                            | Changeable       | Changelog                                               |
|----------------------------------------------------------------------------------|------------------------------------|------------------|---------------------------------------------------------|
| <a href="/session/setup.html#" class="link">session.save_path</a>                | ""                                 | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.name</a>                     | "PHPSESSID"                        | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.save_handler</a>             | "files"                            | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.auto_start</a>               | "0"                                | PHP\_INI\_PERDIR |                                                         |
| <a href="/session/setup.html#" class="link">session.gc_probability</a>           | "1"                                | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.gc_divisor</a>               | "100"                              | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.gc_maxlifetime</a>           | "1440"                             | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.serialize_handler</a>        | "php"                              | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.cookie_lifetime</a>          | "0"                                | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.cookie_path</a>              | "/"                                | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.cookie_domain</a>            | ""                                 | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.cookie_secure</a>            | ""                                 | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.cookie_httponly</a>          | ""                                 | PHP\_INI\_ALL    | Available since PHP 5.2.0.                              |
| <a href="/session/setup.html#" class="link">session.cookie_samesite</a>          | ""                                 | PHP\_INI\_ALL    | Available since PHP 7.3.0.                              |
| <a href="/session/setup.html#" class="link">session.use_strict_mode</a>          | "0"                                | PHP\_INI\_ALL    | Available since PHP 5.5.2.                              |
| <a href="/session/setup.html#" class="link">session.use_cookies</a>              | "1"                                | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.use_only_cookies</a>         | "1"                                | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.referer_check</a>            | ""                                 | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.cache_limiter</a>            | "nocache"                          | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.cache_expire</a>             | "180"                              | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.use_trans_sid</a>            | "0"                                | PHP\_INI\_ALL    |                                                         |
| <a href="/session/setup.html#" class="link">session.trans_sid_tags</a>           | "a=href,area=href,frame=src,form=" | PHP\_INI\_ALL    | Available since PHP 7.1.0.                              |
| <a href="/session/setup.html#" class="link">session.trans_sid_hosts</a>          | *$\_SERVER\['HTTP\_HOST'\]*        | PHP\_INI\_ALL    | Available since PHP 7.1.0.                              |
| <a href="/session/setup.html#" class="link">session.sid_length</a>               | "32"                               | PHP\_INI\_ALL    | Available since PHP 7.1.0.                              |
| <a href="/session/setup.html#" class="link">session.sid_bits_per_character</a>   | "4"                                | PHP\_INI\_ALL    | Available since PHP 7.1.0.                              |
| <a href="/session/setup.html#" class="link">session.upload_progress.enabled</a>  | "1"                                | PHP\_INI\_PERDIR | Available since PHP 5.4.0.                              |
| <a href="/session/setup.html#" class="link">session.upload_progress.cleanup</a>  | "1"                                | PHP\_INI\_PERDIR | Available since PHP 5.4.0.                              |
| <a href="/session/setup.html#" class="link">session.upload_progress.prefix</a>   | "upload\_progress\_"               | PHP\_INI\_PERDIR | Available since PHP 5.4.0.                              |
| <a href="/session/setup.html#" class="link">session.upload_progress.name</a>     | "PHP\_SESSION\_UPLOAD\_PROGRESS"   | PHP\_INI\_PERDIR | Available since PHP 5.4.0.                              |
| <a href="/session/setup.html#" class="link">session.upload_progress.freq</a>     | "1%"                               | PHP\_INI\_PERDIR | Available since PHP 5.4.0.                              |
| <a href="/session/setup.html#" class="link">session.upload_progress.min_freq</a> | "1"                                | PHP\_INI\_PERDIR | Available since PHP 5.4.0.                              |
| <a href="/session/setup.html#" class="link">session.lazy_write</a>               | "1"                                | PHP\_INI\_ALL    | Available since PHP 7.0.0.                              |
| <a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a>             | "a=href,area=href,frame=src,form=" | PHP\_INI\_ALL    | Since PHP 7.1.0, this INI is no longer used by session. |
| <a href="/session/setup.html#" class="link">session.hash_function</a>            | "0"                                | PHP\_INI\_ALL    | Removed in PHP 7.1.0.                                   |
| <a href="/session/setup.html#" class="link">session.hash_bits_per_character</a>  | "4"                                | PHP\_INI\_ALL    | Removed in PHP 7.1.0.                                   |
| <a href="/session/setup.html#" class="link">session.entropy_file</a>             | ""                                 | PHP\_INI\_ALL    | Removed in PHP 7.1.0.                                   |
| <a href="/session/setup.html#" class="link">session.entropy_length</a>           | "0"                                | PHP\_INI\_ALL    | Removed in PHP 7.1.0                                    |
| <a href="/session/setup.html#" class="link">session.bug_compat_42</a>            | "1"                                | PHP\_INI\_ALL    | Removed in PHP 5.4.0.                                   |
| <a href="/session/setup.html#" class="link">session.bug_compat_warn</a>          | "1"                                | PHP\_INI\_ALL    | Removed in PHP 5.4.0.                                   |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

The session management system supports a number of configuration options
which you can place in your `php.ini` file. We will give a short
overview.

`session.save_handler` <span class="type">string</span>  
<span class="simpara"> *session.save\_handler* defines the name of the
handler which is used for storing and retrieving data associated with a
session. Defaults to *files*. Note that individual extensions may
register their own *save\_handler*s; registered handlers can be obtained
on a per-installation basis by referring to <span
class="function">phpinfo</span>. See also <span
class="function">session\_set\_save\_handler</span>. </span>

`session.save_path` <span class="type">string</span>  
<span class="simpara"> *session.save\_path* defines the argument which
is passed to the save handler. If you choose the default files handler,
this is the path where the files are created. See also <span
class="function">session\_save\_path</span>. </span>

There is an optional *N* argument to this directive that determines the
number of directory levels your session files will be spread around in.
For example, setting to *'5;/tmp'* may end up creating a session file
and location like
*/tmp/4/b/1/e/3/sess\_4b1e384ad74619bd212e236e52a5a174If* . In order to
use *N* you must create all of these directories before use. A small
shell script exists in `ext/session` to do this, it's called
`mod_files.sh`, with a Windows version called `mod_files.bat`. Also note
that if *N* is used and greater than 0 then automatic garbage collection
will not be performed, see a copy of `php.ini` for further information.
Also, if you use *N*, be sure to surround *session.save\_path* in
"quotes" because the separator (*;*) is also used for comments in
`php.ini`.

The file storage module creates files using mode 600 by default. This
default can be changed with the optional *MODE* argument: *N;MODE;/path*
where *MODE* is the octal representation of the mode. Setting *MODE*
does not affect the process umask.

**Warning**
If this is set to a world-readable directory, such as `/tmp` (the
default), other users on the server may be able to hijack sessions by
getting the list of files in that directory.

**Caution**
When using the optional directory level argument *N*, as described
above, note that using a value higher than 1 or 2 is inappropriate for
most sites due to the large number of directories required: for example,
a value of 3 implies that *(2 \*\* session.sid\_bits\_per\_character)
\*\* 3* directories exist on the filesystem, which can result in a lot
of wasted space and inodes.

Only use *N* greater than 2 if you are absolutely certain that your site
is large enough to require it.

`session.name` <span class="type">string</span>  
<span class="simpara"> *session.name* specifies the name of the session
which is used as cookie name. It should only contain alphanumeric
characters. Defaults to *PHPSESSID*. See also <span
class="function">session\_name</span>. </span>

`session.auto_start` <span class="type">bool</span>  
<span class="simpara"> *session.auto\_start* specifies whether the
session module starts a session automatically on request startup.
Defaults to *0* (disabled). </span>

`session.serialize_handler` <span class="type">string</span>  
<span class="simpara"> *session.serialize\_handler* defines the name of
the handler which is used to serialize/deserialize data. PHP serialize
format (name *php\_serialize*), PHP internal formats (name *php* and
*php\_binary*) and WDDX are supported (name *wddx*). WDDX is only
available, if PHP is compiled with
<a href="/ref/wddx.html" class="link">WDDX support</a>. *php\_serialize*
is available from PHP 5.5.4. *php\_serialize* uses plain
serialize/unserialize function internally and does not have limitations
that *php* and *php\_binary* have. Older serialize handlers cannot store
numeric index nor string index contains special characters (*\|* and
*!*) in $\_SESSION. Use *php\_serialize* to avoid numeric index or
special character errors at script shutdown. Defaults to *php*. </span>

`session.gc_probability` <span class="type">int</span>  
<span class="simpara"> *session.gc\_probability* in conjunction with
*session.gc\_divisor* is used to manage probability that the gc (garbage
collection) routine is started. Defaults to *1*. See
<a href="/session/setup.html#" class="link">session.gc_divisor</a> for
details. </span>

`session.gc_divisor` <span class="type">int</span>  
<span class="simpara"> *session.gc\_divisor* coupled with
*session.gc\_probability* defines the probability that the gc (garbage
collection) process is started on every session initialization. The
probability is calculated by using gc\_probability/gc\_divisor, e.g.
1/100 means there is a 1% chance that the GC process starts on each
request. *session.gc\_divisor* defaults to *100*. </span>

`session.gc_maxlifetime` <span class="type">int</span>  
<span class="simpara"> *session.gc\_maxlifetime* specifies the number of
seconds after which data will be seen as 'garbage' and potentially
cleaned up. Garbage collection may occur during session start (depending
on
<a href="/session/setup.html#" class="link">session.gc_probability</a>
and <a href="/session/setup.html#" class="link">session.gc_divisor</a>).
</span>

> **Note**: <span class="simpara"> If different scripts have different
> values of *session.gc\_maxlifetime* but share the same place for
> storing the session data then the script with the minimum value will
> be cleaning the data. In this case, use this directive together with
> <a href="/session/setup.html#" class="link">session.save_path</a>.
> </span>

`session.referer_check` <span class="type">string</span>  
<span class="simpara"> *session.referer\_check* contains the substring
you want to check each HTTP Referer for. If the Referer was sent by the
client and the substring was not found, the embedded session id will be
marked as invalid. Defaults to the empty string. </span>

`session.entropy_file` <span class="type">string</span>  
<span class="simpara"> *session.entropy\_file* gives a path to an
external resource (file) which will be used as an additional entropy
source in the session id creation process. Examples are */dev/random* or
*/dev/urandom* which are available on many Unix systems. </span> <span
class="simpara"> This feature is supported on Windows since PHP 5.3.3.
Setting *session.entropy\_length* to a non zero value will make PHP use
the Windows Random API as entropy source. </span>

> **Note**: <span class="simpara"> Removed in PHP 7.1.0. </span> <span
> class="simpara"> As of PHP 5.4.0 *session.entropy\_file* defaults to
> */dev/urandom* or */dev/arandom* if it is available. In PHP 5.3.0 this
> directive is left empty by default. </span>

`session.entropy_length` <span class="type">int</span>  
<span class="simpara"> *session.entropy\_length* specifies the number of
bytes which will be read from the file specified above. Defaults to
*32*. </span> <span class="simpara"> Removed in PHP 7.1.0. </span>

`session.use_strict_mode` <span class="type">bool</span>  
<span class="simpara"> *session.use\_strict\_mode* specifies whether the
module will use strict session id mode. If this mode is enabled, the
module does not accept uninitialized session IDs. If an uninitialized
session ID is sent from the browser, a new session ID is sent to the
browser. Applications are protected from session fixation via session
adoption with strict mode. Defaults to *0* (disabled). </span>

> **Note**: <span class="simpara"> Enabling *session.use\_strict\_mode*
> is mandatory for general session security. All sites are advised to
> enable this. See <span class="function">session\_create\_id</span>
> example code for more details. </span>

**Warning**
If a custom session handler registered via <span
class="function">session\_set\_save\_handler</span> does not implement
<span
class="methodname">SessionUpdateTimestampHandlerInterface::validateId</span>,
nor supplies the `validate_sid` callback, respectively, strict session
ID mode is effectively disabled, regardless of the value of this
directive. Particularly note that <span
class="classname">SessionHandler</span> does *not* implement <span
class="methodname">SessionHandler::validateId</span>.

`session.use_cookies` <span class="type">bool</span>  
<span class="simpara"> *session.use\_cookies* specifies whether the
module will use cookies to store the session id on the client side.
Defaults to *1* (enabled). </span>

`session.use_only_cookies` <span class="type">bool</span>  
<span class="simpara"> *session.use\_only\_cookies* specifies whether
the module will *only* use cookies to store the session id on the client
side. Enabling this setting prevents attacks involved passing session
ids in URLs. Defaults to *1* (enabled) since PHP 5.3.0. </span>

`session.cookie_lifetime` <span class="type">int</span>  
<span class="simpara"> *session.cookie\_lifetime* specifies the lifetime
of the cookie in seconds which is sent to the browser. The value 0 means
"until the browser is closed." Defaults to *0*. See also <span
class="function">session\_get\_cookie\_params</span> and <span
class="function">session\_set\_cookie\_params</span>. </span>

> **Note**: <span class="simpara"> The expiration timestamp is set
> relative to the server time, which is not necessarily the same as the
> time in the client's browser. </span>

`session.cookie_path` <span class="type">string</span>  
<span class="simpara"> *session.cookie\_path* specifies path to set in
the session cookie. Defaults to */*. See also <span
class="function">session\_get\_cookie\_params</span> and <span
class="function">session\_set\_cookie\_params</span>. </span>

`session.cookie_domain` <span class="type">string</span>  
<span class="simpara"> *session.cookie\_domain* specifies the domain to
set in the session cookie. Default is none at all meaning the host name
of the server which generated the cookie according to cookies
specification. See also <span
class="function">session\_get\_cookie\_params</span> and <span
class="function">session\_set\_cookie\_params</span>. </span>

`session.cookie_secure` <span class="type">bool</span>  
<span class="simpara"> *session.cookie\_secure* specifies whether
cookies should only be sent over secure connections. Defaults to *off*.
See also <span class="function">session\_get\_cookie\_params</span> and
<span class="function">session\_set\_cookie\_params</span>. </span>

`session.cookie_httponly` <span class="type">bool</span>  
<span class="simpara"> Marks the cookie as accessible only through the
HTTP protocol. This means that the cookie won't be accessible by
scripting languages, such as JavaScript. This setting can effectively
help to reduce identity theft through XSS attacks (although it is not
supported by all browsers). </span>

`session.cookie_samesite` <span class="type">string</span>  
<span class="simpara"> Allows servers to assert that a cookie ought not
to be sent along with cross-site requests. This assertion allows user
agents to mitigate the risk of cross-origin information leakage, and
provides some protection against cross-site request forgery attacks.
Note that this is not supported by all browsers. An empty value means
that no SameSite cookie attribute will be set. *Lax* and *Strict* mean
that the cookie will not be sent cross-domain for POST requests; *Lax*
will sent the cookie for cross-domain GET requests, while *Strict* will
not. </span>

`session.cache_limiter` <span class="type">string</span>  
<span class="simpara"> *session.cache\_limiter* specifies the cache
control method used for session pages. It may be one of the following
values: *nocache*, *private*, *private\_no\_expire*, or *public*.
Defaults to *nocache*. See also the <span
class="function">session\_cache\_limiter</span> documentation for
information about what these values mean. </span>

`session.cache_expire` <span class="type">int</span>  
<span class="simpara"> *session.cache\_expire* specifies time-to-live
for cached session pages in minutes, this has no effect for nocache
limiter. Defaults to *180*. See also <span
class="function">session\_cache\_expire</span>. </span>

`session.use_trans_sid` <span class="type">bool</span>  
<span class="simpara"> *session.use\_trans\_sid* whether transparent sid
support is enabled or not. Defaults to *0* (disabled). </span>

> **Note**: <span class="simpara"> URL based session management has
> additional security risks compared to cookie based session management.
> Users may send a URL that contains an active session ID to their
> friends by email or users may save a URL that contains a session ID to
> their bookmarks and access your site with the same session ID always,
> for example. </span> <span class="simpara"> Since PHP 7.1.0, full URL
> path, e.g. https://php.net/, is handled by trans sid feature. Previous
> PHP handled relative URL path only. Rewrite target hosts are defined
> by
> <a href="/session/setup.html#" class="link">session.trans_sid_hosts</a>.
> </span>

`session.trans_sid_tags` <span class="type">string</span>  
<span class="simpara"> *session.trans\_sid\_tags* specifies which HTML
tags are rewritten to include session id when transparent sid support is
enabled. Defaults to *a=href,area=href,frame=src,input=src,form=*
</span> <span class="simpara"> *form* is special tag. *\<input
hidden="session\_id" name="session\_name"\>* is added as form variable.
</span>

> **Note**: <span class="simpara"> Before PHP 7.1.0,
> <a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a>
> was used for this purpose. Since PHP 7.1.0, *fieldset* is no longer
> considered as special tag. </span>

`session.trans_sid_hosts` <span class="type">string</span>  
<span class="simpara"> *session.trans\_sid\_hosts* specifies which hosts
are rewritten to include session id when transparent sid support is
enabled. Defaults to *$\_SERVER\['HTTP\_HOST'\]* Multiple hosts can be
specified by ",", no space is allowed between hosts. e.g.
*php.net,wiki.php.net,bugs.php.net* </span>

`session.bug_compat_42` <span class="type">bool</span>  
<span class="simpara"> PHP versions 4.2.3 and lower have an undocumented
feature/bug that allows you to initialize a session variable in the
global scope, albeit
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
is disabled. PHP 4.3.0 and later will warn you, if this feature is used,
and if
<a href="/session/setup.html#" class="link">session.bug_compat_warn</a>
is also enabled. This feature/bug can be disabled by disabling this
directive. </span>

> **Note**: <span class="simpara"> Removed in PHP 5.4.0. </span>

`session.bug_compat_warn` <span class="type">bool</span>  
<span class="simpara"> PHP versions 4.2.3 and lower have an undocumented
feature/bug that allows you to initialize a session variable in the
global scope, albeit
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
is disabled. PHP 4.3.0 and later will warn you, if this feature is used
by enabling both
<a href="/session/setup.html#" class="link">session.bug_compat_42</a>
and
<a href="/session/setup.html#" class="link">session.bug_compat_warn</a>.
</span>

> **Note**: <span class="simpara"> Removed in PHP 5.4.0. </span>

`session.sid_length` <span class="type">int</span>  
<span class="simpara"> *session.sid\_length* allows you to specify the
length of session ID string. Session ID length can be between 22 to 256.
</span> <span class="simpara"> The default is 32. If you need
compatibility you may specify 32, 40, etc. Longer session ID is harder
to guess. At least 32 chars are recommended. </span>

**Tip**
Compatibility Note: Use 32 instead of *session.hash\_function*=0 (MD5)
and *session.hash\_bits\_per\_character*=4, *session.hash\_function*=1
(SHA1) and *session.hash\_bits\_per\_character*=6. Use 26 instead of
*session.hash\_function*=0 (MD5) and
*session.hash\_bits\_per\_character*=5. Use 22 instead of
*session.hash\_function*=0 (MD5) and
*session.hash\_bits\_per\_character*=6. You must configure INI values to
have at least 128 bits in session ID. Do not forget to set an
appropriate value for *session.sid\_bits\_per\_character*, otherwise you
will have weaker session ID.

> **Note**: <span class="simpara"> This setting is introduced in PHP
> 7.1.0. </span>

`session.sid_bits_per_character` <span class="type">int</span>  
<span class="simpara"> *session.sid\_per\_character* allows you to
specify the number of bits in encoded session ID character. The possible
values are '4' (0-9, a-f), '5' (0-9, a-v), and '6' (0-9, a-z, A-Z, "-",
","). </span> <span class="simpara"> The default is 4. The more bits
results in stronger session ID. 5 is recommended value for most
environments. </span>

> **Note**: <span class="simpara"> This setting is introduced in PHP
> 7.1.0. </span>

`session.hash_function` <span class="type">mixed</span>  
<span class="simpara"> *session.hash\_function* allows you to specify
the hash algorithm used to generate the session IDs. '0' means MD5 (128
bits) and '1' means SHA-1 (160 bits). </span>

Since PHP 5.3.0 it is also possible to specify any of the algorithms
provided by the <a href="/ref/hash.html" class="link">hash extension</a>
(if it is available), like *sha512* or *whirlpool*. A complete list of
supported algorithms can be obtained with the <span
class="function">hash\_algos</span> function.

> **Note**: <span class="simpara"> This setting was introduced in PHP 5.
> Removed in PHP 7.1.0. </span>

`session.hash_bits_per_character` <span class="type">int</span>  
<span class="simpara"> *session.hash\_bits\_per\_character* allows you
to define how many bits are stored in each character when converting the
binary hash data to something readable. The possible values are '4'
(0-9, a-f), '5' (0-9, a-v), and '6' (0-9, a-z, A-Z, "-", ","). </span>

> **Note**: <span class="simpara"> Removed in PHP 7.1.0. </span>

`session.upload_progress.enabled` <span class="type">bool</span>  
<span class="simpara"> Enables upload progress tracking, populating the
`$_SESSION` variable. Defaults to 1, enabled. </span>

`session.upload_progress.cleanup` <span class="type">bool</span>  
<span class="simpara"> Cleanup the progress information as soon as all
POST data has been read (i.e. upload completed). Defaults to 1, enabled.
</span>

> **Note**: <span class="simpara"> It is highly recommended to keep this
> feature enabled. </span>

`session.upload_progress.prefix` <span class="type">string</span>  
<span class="simpara"> A prefix used for the upload progress key in the
`$_SESSION`. This key will be concatenated with the value of
*$\_POST\[ini\_get("session.upload\_progress.name")\]* to provide a
unique index. </span> <span class="simpara"> Defaults to
"upload\_progress\_". </span>

`session.upload_progress.name` <span class="type">string</span>  
<span class="simpara"> The name of the key to be used in `$_SESSION`
storing the progress information. See also
<a href="/session/setup.html#" class="link">session.upload_progress.prefix</a>.
</span> <span class="simpara"> If
*$\_POST\[ini\_get("session.upload\_progress.name")\]* is not passed or
available, upload progressing will not be recorded. </span> <span
class="simpara"> Defaults to "PHP\_SESSION\_UPLOAD\_PROGRESS". </span>

`session.upload_progress.freq` <span class="type">mixed</span>  
<span class="simpara"> Defines how often the upload progress information
should be updated. This can be defined in bytes (i.e. "update progress
information after every 100 bytes"), or in percentages (i.e. "update
progress information after receiving every 1% of the whole filesize").
</span> <span class="simpara"> Defaults to "1%". </span>

`session.upload_progress.min_freq` <span class="type">int</span>  
<span class="simpara"> The minimum delay between updates, in seconds.
Defaults to "1" (one second). </span>

`session.lazy_write` <span class="type">bool</span>  
<span class="simpara"> *session.lazy\_write*, when set to 1, means that
session data is only rewritten if it changes. Defaults to 1, enabled.
</span>

The
<a href="/ini/core.html#ini.register-globals" class="link"><em>register_globals</em></a>
configuration settings influence how the session variables get stored
and restored.

Upload progress will not be registered unless
session.upload\_progress.enabled is enabled, and the
$\_POST\[ini\_get("session.upload\_progress.name")\] variable is set.
See
<a href="/session/upload-progress.html" class="link">Session Upload Progress</a>
for more details on this functionality.

Resource Types
--------------

This extension has no resource types defined.

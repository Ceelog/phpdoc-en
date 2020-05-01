Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/filesystem/setup.html#Requirements)
-   [Installation](/filesystem/setup.html#Installation)
-   [Runtime
    Configuration](/filesystem/setup.html#Runtime%20Configuration)
-   [Resource Types](/filesystem/setup.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

There is no installation needed to use these functions; they are part of
the PHP core.

Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                                                                        | Default | Changeable       | Changelog                                              |
|-----------------------------------------------------------------------------|---------|------------------|--------------------------------------------------------|
| <a href="/filesystem/setup.html#" class="link">allow_url_fopen</a>          | "1"     | PHP\_INI\_SYSTEM |                                                        |
| <a href="/filesystem/setup.html#" class="link">allow_url_include</a>        | "0"     | PHP\_INI\_SYSTEM | Available since PHP 5.2.0. Deprecated as of PHP 7.4.0. |
| <a href="/filesystem/setup.html#" class="link">user_agent</a>               | NULL    | PHP\_INI\_ALL    |                                                        |
| <a href="/filesystem/setup.html#" class="link">default_socket_timeout</a>   | "60"    | PHP\_INI\_ALL    |                                                        |
| <a href="/filesystem/setup.html#" class="link">from</a>                     | ""      | PHP\_INI\_ALL    |                                                        |
| <a href="/filesystem/setup.html#" class="link">auto_detect_line_endings</a> | "0"     | PHP\_INI\_ALL    |                                                        |
| <a href="/filesystem/setup.html#" class="link">sys_temp_dir</a>             | ""      | PHP\_INI\_SYSTEM | Available since PHP 5.5.0.                             |

Here's a short explanation of the configuration directives.

`allow_url_fopen` <span class="type">boolean</span>  
This option enables the URL-aware fopen wrappers that enable accessing
URL object like files. Default wrappers are provided for the access of
<a href="/features/remote-files.html" class="link">remote files</a>
using the ftp or http protocol, some extensions like
<a href="/ref/zlib.html" class="link">zlib</a> may register additional
wrappers.

`allow_url_include` <span class="type">boolean</span>  
This option allows the use of URL-aware fopen wrappers with the
following functions: <span class="function">include</span>, <span
class="function">include\_once</span>, <span
class="function">require</span>, <span
class="function">require\_once</span>.

> **Note**:
>
> This setting requires allow\_url\_fopen to be on.

`user_agent` <span class="type">string</span>  
Define the user agent for PHP to send.

`default_socket_timeout` <span class="type">integer</span>  
Default timeout (in seconds) for socket based streams.

`from` <span class="type">string</span>  
The email address to be used on unauthenticated FTP connections and as
the value of From header for HTTP connections, when using the ftp and
http wrappers, respectively.

`auto_detect_line_endings` <span class="type">boolean</span>  
When turned on, PHP will examine the data read by <span
class="function">fgets</span> and <span class="function">file</span> to
see if it is using Unix, MS-Dos or Macintosh line-ending conventions.

This enables PHP to interoperate with Macintosh systems, but defaults to
Off, as there is a very small performance penalty when detecting the EOL
conventions for the first line, and also because people using
carriage-returns as item separators under Unix systems would experience
non-backwards-compatible behaviour.

`sys_temp_dir` <span class="type">string</span>  

Resource Types
--------------

The file system uses *streams* as their resource type. Streams are
documented in its own reference chapter,
<a href="/book/stream.html" class="link">Streams</a>.

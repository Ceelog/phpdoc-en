Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/info/setup.html#Requirements)
-   [Installation](/info/setup.html#Installation)
-   [Runtime Configuration](/info/setup.html#Runtime%20Configuration)
-   [Resource Types](/info/setup.html#Resource%20Types)

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

| Name                                                                 | Default | Changeable       | Changelog                                                            |
|----------------------------------------------------------------------|---------|------------------|----------------------------------------------------------------------|
| <a href="/info/setup.html#" class="link">assert.active</a>           | "1"     | PHP\_INI\_ALL    |                                                                      |
| <a href="/info/setup.html#" class="link">assert.bail</a>             | "0"     | PHP\_INI\_ALL    |                                                                      |
| <a href="/info/setup.html#" class="link">assert.warning</a>          | "1"     | PHP\_INI\_ALL    |                                                                      |
| <a href="/info/setup.html#" class="link">assert.callback</a>         | NULL    | PHP\_INI\_ALL    |                                                                      |
| <a href="/info/setup.html#" class="link">assert.quiet_eval</a>       | "0"     | PHP\_INI\_ALL    |                                                                      |
| <a href="/info/setup.html#" class="link">assert.exception</a>        | "0"     | PHP\_INI\_ALL    | Available as of PHP 7.0.0.                                           |
| <a href="/info/setup.html#" class="link">enable_dl</a>               | "1"     | PHP\_INI\_SYSTEM | This deprecated feature *will* certainly be *removed* in the future. |
| <a href="/info/setup.html#" class="link">max_execution_time</a>      | "30"    | PHP\_INI\_ALL    |                                                                      |
| <a href="/info/setup.html#" class="link">max_input_time</a>          | "-1"    | PHP\_INI\_PERDIR |                                                                      |
| <a href="/info/setup.html#" class="link">max_input_nesting_level</a> | "64"    | PHP\_INI\_PERDIR | Available as of PHP 5.2.3.                                           |
| <a href="/info/setup.html#" class="link">max_input_vars</a>          | 1000    | PHP\_INI\_PERDIR | Available as of PHP 5.3.9.                                           |
| <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>        | "1"     | PHP\_INI\_PERDIR | Removed in PHP 5.4.0.                                                |
| <a href="/info/setup.html#" class="link">magic_quotes_runtime</a>    | "0"     | PHP\_INI\_ALL    | Removed in PHP 5.4.0.                                                |
| <a href="/info/setup.html#" class="link">zend.enable_gc</a>          | "1"     | PHP\_INI\_ALL    | Available as of PHP 5.3.0.                                           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`assert.active` <span class="type">bool</span>  
Enable <span class="function">assert</span> evaluation.

`assert.bail` <span class="type">bool</span>  
Terminate script execution on failed assertions.

`assert.warning` <span class="type">bool</span>  
Issue a PHP warning for each failed assertion.

`assert.callback` <span class="type">string</span>  
User function to call on failed assertions.

`assert.quiet_eval` <span class="type">bool</span>  
Use the current setting of <span
class="function">error\_reporting</span> during assertion expression
evaluation. If enabled, no errors are shown (implicit
error\_reporting(0)) while evaluation. If disabled, errors are shown
according to the settings of <span
class="function">error\_reporting</span>

`assert.exception` <span class="type">bool</span>  
Issue an <span class="classname">AssertionError</span> exception for the
failed assertion.

`enable_dl` <span class="type">bool</span>  
This directive is really only useful in the Apache module version of
PHP. You can turn dynamic loading of PHP extensions with <span
class="function">dl</span> on and off per virtual server or per
directory.

The main reason for turning dynamic loading off is security. With
dynamic loading, it's possible to ignore all
<a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
restrictions. The default is to allow dynamic loading.

`max_execution_time` <span class="type">int</span>  
This sets the maximum time in seconds a script is allowed to run before
it is terminated by the parser. This helps prevent poorly written
scripts from tying up the server. The default setting is *30*. When
running PHP from the
<a href="/features/commandline.html" class="link">command line</a> the
default setting is *0*.

On non Windows systems, the maximum execution time is not affected by
system calls, stream operations etc. Please see the <span
class="function">set\_time\_limit</span> function for more details.

Your web server can have other timeout configurations that may also
interrupt PHP execution. Apache has a *Timeout* directive and IIS has a
CGI timeout function. Both default to 300 seconds. See your web server
documentation for specific details.

`max_input_time` <span class="type">int</span>  
This sets the maximum time in seconds a script is allowed to parse input
data, like POST and GET. Timing begins at the moment PHP is invoked at
the server and ends when execution begins. The default setting is *-1*,
which means that
<a href="/info/setup.html#" class="link">max_execution_time</a> is used
instead. Set to *0* to allow unlimited time.

`max_input_nesting_level` <span class="type">int</span>  
Sets the max nesting depth of
<a href="/language/variables/external.html" class="link">input variables</a>
(i.e. `$_GET`, `$_POST`.)

`max_input_vars` <span class="type">int</span>  
How many
<a href="/language/variables/external.html" class="link">input variables</a>
may be accepted (limit is applied to $\_GET, $\_POST and $\_COOKIE
superglobal separately). Use of this directive mitigates the possibility
of denial of service attacks which use hash collisions. If there are
more input variables than specified by this directive, an
**`E_WARNING`** is issued, and further input variables are truncated
from the request.

`magic_quotes_gpc` <span class="type">bool</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

Sets the magic\_quotes state for GPC (Get/Post/Cookie) operations. When
magic\_quotes are on, all ' (single-quote), " (double quote), \\
(backslash) and NUL's are escaped with a backslash automatically.

See also <span class="function">get\_magic\_quotes\_gpc</span>

`magic_quotes_runtime` <span class="type">bool</span>  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

If `magic_quotes_runtime` is enabled, most functions that return data
from any sort of external source including databases and text files will
have quotes escaped with a backslash.

Functions affected by `magic_quotes_runtime` (does not include functions
from PECL):

-   <span class="function">get\_meta\_tags</span>
-   <span class="function">file\_get\_contents</span>
-   <span class="function">file</span>
-   <span class="function">fgets</span>
-   <span class="function">fwrite</span>
-   <span class="function">fread</span>
-   <span class="function">fputcsv</span>
-   <span class="function">stream\_socket\_recvfrom</span>
-   <span class="function">exec</span>
-   <span class="function">system</span>
-   <span class="function">passthru</span>
-   <span class="function">stream\_get\_contents</span>
-   <span class="function">bzread</span>
-   <span class="function">gzfile</span>
-   <span class="function">gzgets</span>
-   <span class="function">gzwrite</span>
-   <span class="function">gzread</span>
-   <span class="function">exif\_read\_data</span>
-   <span class="function">dba\_insert</span>
-   <span class="function">dba\_replace</span>
-   <span class="function">dba\_fetch</span>
-   <span class="function">ibase\_fetch\_row</span>
-   <span class="function">ibase\_fetch\_assoc</span>
-   <span class="function">ibase\_fetch\_object</span>
-   <span class="function">mssql\_fetch\_row</span>
-   <span class="function">mssql\_fetch\_object</span>
-   <span class="function">mssql\_fetch\_array</span>
-   <span class="function">mssql\_fetch\_assoc</span>
-   <span class="function">mysqli\_fetch\_row</span>
-   <span class="function">mysqli\_fetch\_array</span>
-   <span class="function">mysqli\_fetch\_assoc</span>
-   <span class="function">mysqli\_fetch\_object</span>
-   <span class="function">pg\_fetch\_row</span>
-   <span class="function">pg\_fetch\_assoc</span>
-   <span class="function">pg\_fetch\_array</span>
-   <span class="function">pg\_fetch\_object</span>
-   <span class="function">pg\_fetch\_all</span>
-   <span class="function">pg\_select</span>
-   <span class="function">sybase\_fetch\_object</span>
-   <span class="function">sybase\_fetch\_array</span>
-   <span class="function">sybase\_fetch\_assoc</span>
-   <span class="function">SplFileObject::fgets</span>
-   <span class="function">SplFileObject::fgetcsv</span>
-   <span class="function">SplFileObject::fwrite</span>

`zend.enable_gc` <span class="type">bool</span>  
Enables or disables the circular reference collector.

Resource Types
--------------

This extension has no resource types defined.

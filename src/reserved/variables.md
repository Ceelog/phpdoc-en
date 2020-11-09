PHP provides a large number of predefined variables to all scripts. The
variables represent everything from
<a href="/language/variables/external.html" class="link">external variables</a>
to built-in environment variables, last error messages to last retrieved
headers.

Superglobals
============

Superglobals are built-in variables that are always available in all
scopes

### Description

Several predefined variables in PHP are "superglobals", which means they
are available in all scopes throughout a script. There is no need to do
**global $variable;** to access them within functions or methods.

These superglobal variables are:

-   `$GLOBALS`
-   `$_SERVER`
-   `$_GET`
-   `$_POST`
-   `$_FILES`
-   `$_COOKIE`
-   `$_SESSION`
-   `$_REQUEST`
-   `$_ENV`

### Notes

> **Note**: **Variable availability**  
>
> By default, all of the superglobals are available but there are
> directives that affect this availability. For further information,
> refer to the documentation for
> <a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>.

> **Note**: **Variable variables**  
>
> Superglobals cannot be used as
> <a href="/language/variables/variable.html" class="link">variable variables</a>
> inside functions or class methods.

### See Also

-   <a href="/language/variables/scope.html" class="link">variable scope</a>
-   The
    <a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
    directive
-   <a href="/book/filter.html" class="link">The filter extension</a>

$GLOBALS
========

References all variables available in global scope

### Description

An associative <span class="type">array</span> containing references to
all variables which are currently defined in the global scope of the
script. The variable names are the keys of the array.

### Examples

**Example \#1 `$GLOBALS` example**

``` php
<?php
function test() {
    $foo = "local variable";

    echo '$foo in global scope: ' . $GLOBALS["foo"] . "\n";
    echo '$foo in current scope: ' . $foo . "\n";
}

$foo = "Example content";
test();
?>
```

The above example will output something similar to:

    $foo in global scope: Example content
    $foo in current scope: local variable

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

> **Note**: **Variable availability**  
>
> Unlike all of the other
> <a href="/language/variables/superglobals.html" class="link">superglobals</a>,
> `$GLOBALS` has essentially always been available in PHP.

$\_SERVER
=========

Server and execution environment information

### Description

`$_SERVER` is an array containing information such as headers, paths,
and script locations. The entries in this array are created by the web
server. There is no guarantee that every web server will provide any of
these; servers may omit some, or provide others not listed here. That
said, a large number of these variables are accounted for in the
<a href="http://www.faqs.org/rfcs/rfc3875" class="link external">» CGI/1.1 specification</a>,
so you should be able to expect those.

### Indices

You may or may not find any of the following elements in `$_SERVER`.
Note that few, if any, of these will be available (or indeed have any
meaning) if running PHP on the
<a href="/features/commandline.html" class="link">command line</a>.

'`PHP_SELF`'  
<span class="simpara"> The filename of the currently executing script,
relative to the document root. For instance, `$_SERVER['PHP_SELF']` in a
script at the address `http://example.com/foo/bar.php` would be
`/foo/bar.php`. The
<a href="/language/constants/predefined.html" class="link">__FILE__</a>
constant contains the full path and filename of the current (i.e.
included) file. </span> <span class="simpara"> If PHP is running as a
command-line processor this variable contains the script name. </span>

'<a href="/reserved/variables/argv.html" class="link">argv</a>'  
<span class="simpara"> Array of arguments passed to the script. When the
script is run on the command line, this gives C-style access to the
command line parameters. When called via the GET method, this will
contain the query string. </span>

'<a href="/reserved/variables/argc.html" class="link">argc</a>'  
<span class="simpara"> Contains the number of command line parameters
passed to the script (if run on the command line). </span>

'`GATEWAY_INTERFACE`'  
<span class="simpara"> What revision of the CGI specification the server
is using; e.g. '*CGI/1.1*'. </span>

'`SERVER_ADDR`'  
<span class="simpara"> The IP address of the server under which the
current script is executing. </span>

'`SERVER_NAME`'  
<span class="simpara"> The name of the server host under which the
current script is executing. If the script is running on a virtual host,
this will be the value defined for that virtual host. </span>

> **Note**: <span class="simpara"> Under Apache 2, you must set
> *UseCanonicalName = On* and *ServerName*. Otherwise, this value
> reflects the hostname supplied by the client, which can be spoofed. It
> is not safe to rely on this value in security-dependent contexts.
> </span>

'`SERVER_SOFTWARE`'  
<span class="simpara"> Server identification string, given in the
headers when responding to requests. </span>

'`SERVER_PROTOCOL`'  
<span class="simpara"> Name and revision of the information protocol via
which the page was requested; e.g. '*HTTP/1.0*'; </span>

'`REQUEST_METHOD`'  
<span class="simpara"> Which request method was used to access the page;
e.g. '*GET*', '*HEAD*', '*POST*', '*PUT*'. </span>

> **Note**:
>
> PHP script is terminated after sending headers (it means after
> producing any output without output buffering) if the request method
> was *HEAD*.

'`REQUEST_TIME`'  
<span class="simpara"> The timestamp of the start of the request.
</span>

'`REQUEST_TIME_FLOAT`'  
<span class="simpara"> The timestamp of the start of the request, with
microsecond precision. </span>

'`QUERY_STRING`'  
<span class="simpara"> The query string, if any, via which the page was
accessed. </span>

'`DOCUMENT_ROOT`'  
<span class="simpara"> The document root directory under which the
current script is executing, as defined in the server's configuration
file. </span>

'`HTTP_ACCEPT`'  
<span class="simpara"> Contents of the *Accept:* header from the current
request, if there is one. </span>

'`HTTP_ACCEPT_CHARSET`'  
<span class="simpara"> Contents of the *Accept-Charset:* header from the
current request, if there is one. Example: '*iso-8859-1,\*,utf-8*'.
</span>

'`HTTP_ACCEPT_ENCODING`'  
<span class="simpara"> Contents of the *Accept-Encoding:* header from
the current request, if there is one. Example: '*gzip*'. </span>

'`HTTP_ACCEPT_LANGUAGE`'  
<span class="simpara"> Contents of the *Accept-Language:* header from
the current request, if there is one. Example: '*en*'. </span>

'`HTTP_CONNECTION`'  
<span class="simpara"> Contents of the *Connection:* header from the
current request, if there is one. Example: '*Keep-Alive*'. </span>

'`HTTP_HOST`'  
<span class="simpara"> Contents of the *Host:* header from the current
request, if there is one. </span>

'`HTTP_REFERER`'  
<span class="simpara"> The address of the page (if any) which referred
the user agent to the current page. This is set by the user agent. Not
all user agents will set this, and some provide the ability to modify
`HTTP_REFERER` as a feature. In short, it cannot really be trusted.
</span>

'`HTTP_USER_AGENT`'  
<span class="simpara"> Contents of the *User-Agent:* header from the
current request, if there is one. This is a string denoting the user
agent being which is accessing the page. A typical example is: <span
class="computeroutput">Mozilla/4.5 \[en\] (X11; U; Linux 2.2.9
i586)</span>. Among other things, you can use this value with <span
class="function">get\_browser</span> to tailor your page's output to the
capabilities of the user agent. </span>

'`HTTPS`'  
<span class="simpara"> Set to a non-empty value if the script was
queried through the HTTPS protocol. </span>

'`REMOTE_ADDR`'  
<span class="simpara"> The IP address from which the user is viewing the
current page. </span>

'`REMOTE_HOST`'  
<span class="simpara"> The Host name from which the user is viewing the
current page. The reverse dns lookup is based on the `REMOTE_ADDR` of
the user. </span>

> **Note**: <span class="simpara"> Your web server must be configured to
> create this variable. For example in Apache you'll need
> *HostnameLookups On* inside `httpd.conf` for it to exist. See also
> <span class="function">gethostbyaddr</span>. </span>

'`REMOTE_PORT`'  
<span class="simpara"> The port being used on the user's machine to
communicate with the web server. </span>

'`REMOTE_USER`'  
<span class="simpara"> The authenticated user. </span>

'`REDIRECT_REMOTE_USER`'  
<span class="simpara"> The authenticated user if the request is
internally redirected. </span>

'`SCRIPT_FILENAME`'  
The absolute pathname of the currently executing script.

> **Note**:
>
> If a script is executed with the CLI, as a relative path, such as
> `file.php` or `../file.php`, `$_SERVER['SCRIPT_FILENAME']` will
> contain the relative path specified by the user.

'`SERVER_ADMIN`'  
<span class="simpara"> The value given to the SERVER\_ADMIN (for Apache)
directive in the web server configuration file. If the script is running
on a virtual host, this will be the value defined for that virtual host.
</span>

'`SERVER_PORT`'  
<span class="simpara"> The port on the server machine being used by the
web server for communication. For default setups, this will be '*80*';
using SSL, for instance, will change this to whatever your defined
secure HTTP port is. </span>

> **Note**: <span class="simpara"> Under the Apache 2, you must set
> *UseCanonicalName = On*, as well as *UseCanonicalPhysicalPort = On* in
> order to get the physical (real) port, otherwise, this value can be
> spoofed and it may or may not return the physical port value. It is
> not safe to rely on this value in security-dependent contexts. </span>

'`SERVER_SIGNATURE`'  
<span class="simpara"> String containing the server version and virtual
host name which are added to server-generated pages, if enabled. </span>

'`PATH_TRANSLATED`'  
<span class="simpara"> Filesystem- (not document root-) based path to
the current script, after the server has done any virtual-to-real
mapping. </span>

> **Note**: <span class="simpara"> Apache 2 users may use
> *AcceptPathInfo = On* inside `httpd.conf` to define `PATH_INFO`.
> </span>

'`SCRIPT_NAME`'  
<span class="simpara"> Contains the current script's path. This is
useful for pages which need to point to themselves. The
<a href="/language/constants/predefined.html" class="link">__FILE__</a>
constant contains the full path and filename of the current (i.e.
included) file. </span>

'`REQUEST_URI`'  
<span class="simpara"> The URI which was given in order to access this
page; for instance, '*/index.html*'. </span>

'`PHP_AUTH_DIGEST`'  
<span class="simpara"> When doing Digest HTTP authentication this
variable is set to the 'Authorization' header sent by the client (which
you should then use to make the appropriate validation). </span>

'`PHP_AUTH_USER`'  
<span class="simpara"> When doing HTTP authentication this variable is
set to the username provided by the user. </span>

'`PHP_AUTH_PW`'  
<span class="simpara"> When doing HTTP authentication this variable is
set to the password provided by the user. </span>

'`AUTH_TYPE`'  
<span class="simpara"> When doing HTTP authentication this variable is
set to the authentication type. </span>

'`PATH_INFO`'  
<span class="simpara"> Contains any client-provided pathname information
trailing the actual script filename but preceding the query string, if
available. For instance, if the current script was accessed via the URL
`http://www.example.com/php/path_info.php/some/stuff?foo=bar`, then
`$_SERVER['PATH_INFO']` would contain */some/stuff*. </span>

'`ORIG_PATH_INFO`'  
<span class="simpara"> Original version of '`PATH_INFO`' before
processed by PHP. </span>

### Examples

**Example \#2 `$_SERVER` example**

``` php
<?php
echo $_SERVER['SERVER_NAME'];
?>
```

The above example will output something similar to:

    www.example.com

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

### See Also

-   <a href="/book/filter.html" class="link">The filter extension</a>

$\_GET
======

HTTP GET variables

### Description

An associative array of variables passed to the current script via the
URL parameters (aka. query string). Note that the array is not only
populated for GET requests, but rather for all requests with a query
string.

### Examples

**Example \#3 `$_GET` example**

``` php
<?php
echo 'Hello ' . htmlspecialchars($_GET["name"]) . '!';
?>
```

Assuming the user entered http://example.com/?name=Hannes

The above example will output something similar to:

    Hello Hannes!

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

> **Note**:
>
> The GET variables are passed through <span
> class="function">urldecode</span>.

### See Also

-   <a href="/language/variables/external.html" class="link">Handling external variables</a>
-   <a href="/book/filter.html" class="link">The filter extension</a>

$\_POST
=======

HTTP POST variables

### Description

An associative array of variables passed to the current script via the
HTTP POST method when using *application/x-www-form-urlencoded* or
*multipart/form-data* as the HTTP Content-Type in the request.

### Examples

**Example \#4 `$_POST` example**

``` php
<?php
echo 'Hello ' . htmlspecialchars($_POST["name"]) . '!';
?>
```

Assuming the user POSTed name=Hannes

The above example will output something similar to:

    Hello Hannes!

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

### See Also

-   <a href="/language/variables/external.html" class="link">Handling external variables</a>
-   <a href="/book/filter.html" class="link">The filter extension</a>

$\_FILES
========

HTTP File Upload variables

### Description

An associative <span class="type">array</span> of items uploaded to the
current script via the HTTP POST method. The structure of this array is
outlined in the
<a href="/features/file-upload/post-method.html" class="link">POST method uploads</a>
section.

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

### See Also

-   <span class="function">move\_uploaded\_file</span>
-   <a href="/features/file-upload.html" class="link">Handling File Uploads</a>

$\_REQUEST
==========

HTTP Request variables

### Description

An associative <span class="type">array</span> that by default contains
the contents of `$_GET`, `$_POST` and `$_COOKIE`.

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

> **Note**:
>
> When running on the
> <a href="/features/commandline.html" class="link">command line</a> ,
> this will *not* include the
> <a href="/reserved/variables/argv.html" class="link">argv</a> and
> <a href="/reserved/variables/argc.html" class="link">argc</a> entries;
> these are present in the `$_SERVER` <span class="type">array</span>.

> **Note**:
>
> The variables in `$_REQUEST` are provided to the script via the GET,
> POST, and COOKIE input mechanisms and therefore could be modified by
> the remote user and cannot be trusted. The presence and order of
> variables listed in this array is defined according to the PHP
> <a href="/ini/core.html#ini.request-order" class="link">request_order</a>,
> and
> <a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
> configuration directives.

### See Also

-   <a href="/language/variables/external.html" class="link">Handling external variables</a>
-   <a href="/book/filter.html" class="link">The filter extension</a>

$\_SESSION
==========

Session variables

### Description

An associative array containing session variables available to the
current script. See the
<a href="/ref/session.html" class="link">Session functions</a>
documentation for more information on how this is used.

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

### See Also

-   <span class="function">session\_start</span>

$\_ENV
======

Environment variables

### Description

An associative <span class="type">array</span> of variables passed to
the current script via the environment method.

These variables are imported into PHP's global namespace from the
environment under which the PHP parser is running. Many are provided by
the shell under which PHP is running and different systems are likely
running different kinds of shells, a definitive list is impossible.
Please see your shell's documentation for a list of defined environment
variables.

Other environment variables include the CGI variables, placed there
regardless of whether PHP is running as a server module or CGI
processor.

### Examples

**Example \#5 `$_ENV` example**

``` php
<?php
echo 'My username is ' .$_ENV["USER"] . '!';
?>
```

Assuming "bjori" executes this script

The above example will output something similar to:

    My username is bjori!

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

### See Also

-   <span class="function">getenv</span>
-   <a href="/book/filter.html" class="link">The filter extension</a>

$\_COOKIE
=========

HTTP Cookies

### Description

An associative <span class="type">array</span> of variables passed to
the current script via HTTP Cookies.

### Examples

**Example \#6 `$_COOKIE` example**

``` php
<?php
echo 'Hello ' . htmlspecialchars($_COOKIE["name"]) . '!';
?>
```

Assuming the "name" cookie has been set earlier

The above example will output something similar to:

    Hello Hannes!

### Notes

> **Note**:
>
> This is a 'superglobal', or automatic global, variable. This simply
> means that it is available in all scopes throughout a script. There is
> no need to do **global $variable;** to access it within functions or
> methods.

### See Also

-   <span class="function">setcookie</span>
-   <a href="/language/variables/external.html" class="link">Handling external variables</a>
-   <a href="/book/filter.html" class="link">The filter extension</a>

$php\_errormsg
==============

The previous error message

**Warning**

This feature has been *DEPRECATED* as of PHP 7.2.0. Relying on this
feature is highly discouraged.

Use <span class="function">error\_get\_last</span> instead.

### Description

`$php_errormsg` is a variable containing the text of the last error
message generated by PHP. This variable will only be available within
the scope in which the error occurred, and only if the
<a href="/errorfunc/setup.html#" class="link">track_errors</a>
configuration option is turned on (it defaults to off).

**Warning**

If a user defined error handler (<span
class="function">set\_error\_handler</span>) is set `$php_errormsg` is
only set if the error handler returns **`FALSE`**.

### Changelog

| Version | Description                                                                                                                                |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | Directive <a href="/errorfunc/setup.html#" class="link">track_errors</a> which caused `$php_errormsg` to be available has been removed.    |
| 7.2.0   | Directive <a href="/errorfunc/setup.html#" class="link">track_errors</a> which caused `$php_errormsg` to be available has been deprecated. |

### Examples

**Example \#7 `$php_errormsg` example**

``` php
<?php
@strpos();
echo $php_errormsg;
?>
```

The above example will output something similar to:

    Wrong parameter count for strpos()

### See Also

-   <span class="function">error\_get\_last</span>

$http\_response\_header
=======================

HTTP response headers

### Description

The `$http_response_header` <span class="type">array</span> is similar
to the <span class="function">get\_headers</span> function. When using
the <a href="/wrappers/http.html" class="link">HTTP wrapper</a>,
`$http_response_header` will be populated with the HTTP response
headers. `$http_response_header` will be created in the
<a href="/language/variables/scope.html" class="link">local scope</a>.

### Examples

**Example \#8 `$http_response_header` example**

``` php
<?php
function get_contents() {
  file_get_contents("http://example.com");
  var_dump($http_response_header);
}
get_contents();
var_dump($http_response_header);
?>
```

The above example will output something similar to:

    array(9) {
      [0]=>
      string(15) "HTTP/1.1 200 OK"
      [1]=>
      string(35) "Date: Sat, 12 Apr 2008 17:30:38 GMT"
      [2]=>
      string(29) "Server: Apache/2.2.3 (CentOS)"
      [3]=>
      string(44) "Last-Modified: Tue, 15 Nov 2005 13:24:10 GMT"
      [4]=>
      string(27) "ETag: "280100-1b6-80bfd280""
      [5]=>
      string(20) "Accept-Ranges: bytes"
      [6]=>
      string(19) "Content-Length: 438"
      [7]=>
      string(17) "Connection: close"
      [8]=>
      string(38) "Content-Type: text/html; charset=UTF-8"
    }
    NULL

$argc
=====

The number of arguments passed to script

### Description

Contains the number of arguments passed to the current script when
running from the
<a href="/features/commandline.html" class="link">command line</a>.

> **Note**: <span class="simpara"> The script's filename is always
> passed as an argument to the script, therefore the minimum value of
> `$argc` is *1*. </span>

> **Note**: <span class="simpara"> This variable is not available when
> <a href="/ini/core.html#ini.register-argc-argv" class="link">register_argc_argv</a>
> is disabled. </span>

### Examples

**Example \#9 `$argc` example**

``` php
<?php
var_dump($argc);
?>
```

When executing the example with: php script.php arg1 arg2 arg3

The above example will output something similar to:

    int(4)

### Notes

> **Note**:
>
> This is also available as `$_SERVER['argc']`.

### See Also

-   <span class="function">getopt</span>
-   <a href="/reserved/variables/argv.html" class="link"><var class="varname">$argv</var></a>

$argv
=====

Array of arguments passed to script

### Description

Contains an <span class="type">array</span> of all the arguments passed
to the script when running from the
<a href="/features/commandline.html" class="link">command line</a>.

> **Note**: <span class="simpara"> The first argument `$argv[0]` is
> always the name that was used to run the script. </span>

> **Note**: <span class="simpara"> This variable is not available when
> <a href="/ini/core.html#ini.register-argc-argv" class="link">register_argc_argv</a>
> is disabled. </span>

### Examples

**Example \#10 `$argv` example**

``` php
<?php
var_dump($argv);
?>
```

When executing the example with: php script.php arg1 arg2 arg3

The above example will output something similar to:

    array(4) {
      [0]=>
      string(10) "script.php"
      [1]=>
      string(4) "arg1"
      [2]=>
      string(4) "arg2"
      [3]=>
      string(4) "arg3"
    }

### Notes

> **Note**:
>
> This is also available as `$_SERVER['argv']`.

### See Also

-   <span class="function">getopt</span>
-   <a href="/reserved/variables/argc.html" class="link"><var class="varname">$argc</var></a>

**Table of Contents**

-   [Superglobals](/language/variables/superglobals.html) — Superglobals
    are built-in variables that are always available in all scopes
-   [$GLOBALS](/reserved/variables/globals.html) — References all
    variables available in global scope
-   [$\_SERVER](/reserved/variables/server.html) — Server and execution
    environment information
-   [$\_GET](/reserved/variables/get.html) — HTTP GET variables
-   [$\_POST](/reserved/variables/post.html) — HTTP POST variables
-   [$\_FILES](/reserved/variables/files.html) — HTTP File Upload
    variables
-   [$\_REQUEST](/reserved/variables/request.html) — HTTP Request
    variables
-   [$\_SESSION](/reserved/variables/session.html) — Session variables
-   [$\_ENV](/reserved/variables/environment.html) — Environment
    variables
-   [$\_COOKIE](/reserved/variables/cookies.html) — HTTP Cookies
-   [$php\_errormsg](/reserved/variables/phperrormsg.html) — The
    previous error message
-   [$http\_response\_header](/reserved/variables/httpresponseheader.html)
    — HTTP response headers
-   [$argc](/reserved/variables/argc.html) — The number of arguments
    passed to script
-   [$argv](/reserved/variables/argv.html) — Array of arguments passed
    to script

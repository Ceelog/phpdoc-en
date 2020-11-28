apache\_child\_terminate
========================

Terminate apache process after this request

### Description

<span class="type">bool</span> <span
class="methodname">apache\_child\_terminate</span> ( <span
class="methodparam">void</span> )

<span class="function">apache\_child\_terminate</span> will register the
Apache process executing the current PHP request for termination once
execution of PHP code is completed. It may be used to terminate a
process after a script with high memory consumption has been run as
memory will usually only be freed internally but not given back to the
operating system.

Works in the Apache, FastCGI and
<a href="/book/nsapi.html" class="link">NSAPI server module</a> in
Netscape/iPlanet/SunONE webservers.

### Return Values

Returns **`TRUE`** if PHP is running as an Apache 1 module, the Apache
version is non-multithreaded, and the
<a href="/apache/setup.html#" class="link">child_terminate</a> PHP
directive is enabled (disabled by default). If these conditions are not
met, **`FALSE`** is returned and an error of level **`E_WARNING`** is
generated.

### Notes

> **Note**: <span class="simpara">This function is not implemented on
> Windows platforms.</span>

### See Also

-   <span class="function">exit</span>

apache\_get\_modules
====================

Get a list of loaded Apache modules

### Description

<span class="type">array</span> <span
class="methodname">apache\_get\_modules</span> ( <span
class="methodparam">void</span> )

Get a list of loaded Apache modules.

### Return Values

An <span class="type">array</span> of loaded Apache modules.

### Examples

**Example \#1 <span class="function">apache\_get\_modules</span>
example**

``` php
<?php
print_r(apache_get_modules());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => core
        [1] => http_core
        [2] => mod_so
        [3] => sapi_apache2
        [4] => mod_mime
        [5] => mod_rewrite
    )

apache\_get\_version
====================

Fetch Apache version

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">apache\_get\_version</span> ( <span
class="methodparam">void</span> )

Fetch the Apache version.

### Return Values

Returns the Apache version on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">apache\_get\_version</span>
example**

``` php
<?php
$version = apache_get_version();
echo "$version\n";
?>
```

The above example will output something similar to:

    Apache/1.3.29 (Unix) PHP/4.3.4 

### See Also

-   <span class="function">phpinfo</span>

apache\_getenv
==============

Get an Apache subprocess\_env variable

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">apache\_getenv</span> ( <span
class="methodparam"><span class="type">string</span> `$variable`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$walk_to_top`<span class="initializer"> = **`FALSE`**</span></span> \]
)

Retrieve an Apache environment variable specified by `variable`.

This function requires Apache 2 otherwise it's undefined.

### Parameters

`variable`  
The Apache environment variable

`walk_to_top`  
Whether to get the top-level variable available to all Apache layers.

### Return Values

The value of the Apache environment variable on success, or **`FALSE`**
on failure

### Examples

**Example \#1 <span class="function">apache\_getenv</span> example**

The example above shows how to retrieve the value of the Apache
environment variable `SERVER_ADDR`.

``` php
<?php
$ret = apache_getenv("SERVER_ADDR");
echo $ret;
?>
```

The above example will output something similar to:

    42.24.42.240

### See Also

-   <span class="function">apache\_setenv</span>
-   <span class="function">getenv</span>
-   <a href="/language/variables/superglobals.html" class="link">Superglobals</a>

apache\_lookup\_uri
===================

Perform a partial request for the specified URI and return all info
about it

### Description

<span class="type">object</span> <span
class="methodname">apache\_lookup\_uri</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

This performs a partial request for a URI. It goes just far enough to
obtain all the important information about the given resource.

This function is supported when PHP is installed as an Apache module or
by the <a href="/book/nsapi.html" class="link">NSAPI server module</a>
in Netscape/iPlanet/SunONE webservers.

### Parameters

`filename`  
The filename (URI) that's being requested.

### Return Values

An <span class="type">object</span> of related URI information. The
properties of this <span class="type">object</span> are:

-   status
-   the\_request
-   status\_line
-   method
-   content\_type
-   handler
-   uri
-   filename
-   path\_info
-   args
-   boundary
-   no\_cache
-   no\_local\_copy
-   allowed
-   send\_bodyct
-   bytes\_sent
-   byterange
-   clength
-   unparsed\_uri
-   mtime
-   request\_time

### Examples

**Example \#1 <span class="function">apache\_lookup\_uri</span>
example**

``` php
<?php
$info = apache_lookup_uri('index.php?var=value');
print_r($info);

if (file_exists($info->filename)) {
    echo 'file exists!';
}
?>
```

The above example will output something similar to:

    stdClass Object
    (
        [status] => 200
        [the_request] => GET /dir/file.php HTTP/1.1
        [method] => GET
        [mtime] => 0
        [clength] => 0
        [chunked] => 0
        [content_type] => application/x-httpd-php
        [no_cache] => 0
        [no_local_copy] => 1
        [unparsed_uri] => /dir/index.php?var=value
        [uri] => /dir/index.php
        [filename] => /home/htdocs/dir/index.php
        [args] => var=value
        [allowed] => 0
        [sent_bodyct] => 0
        [bytes_sent] => 0
        [request_time] => 1074282764
    )
    file exists!

apache\_note
============

Get and set apache request notes

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">apache\_note</span> ( <span class="methodparam"><span
class="type">string</span> `$note_name`</span> )

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">apache\_note</span> ( <span class="methodparam"><span
class="type">string</span> `$note_name`</span> , <span
class="methodparam"><span class="type">string</span>
`$note_value`</span> )

This function is a wrapper for Apache's *table\_get* and *table\_set*.
It edits the table of notes that exists during a request. The table's
purpose is to allow Apache modules to communicate.

The main use for <span class="function">apache\_note</span> is to pass
information from one module to another within the same request.

### Parameters

`note_name`  
The name of the note.

`note_value`  
The value of the note.

### Return Values

If called with one argument, it returns the current value of note
*note\_name*. If called with two arguments, it sets the value of note
*note\_name* to *note\_value* and returns the previous value of note
*note\_name*. If the note cannot be retrieved, **`FALSE`** is returned.

### Examples

**Example \#1 Passing information between PHP and Perl**

``` php
<?php

apache_note('name', 'Fredrik Ekengren');

// Call perl script
virtual("/perl/some_script.pl");

$result = apache_note("resultdata");
?>
```

``` perl
# Get Apache request object
my $r = Apache->request()->main();

# Get passed data
my $name = $r->notes('name');

# some processing

# Pass result back to PHP
$r->notes('resultdata', $result);
```

**Example \#2 Logging values in access.log**

``` php
<?php

apache_note('sessionID', session_id());

?>
```

``` apache
# "%{sessionID}n" can be used in the LogFormat directive
```

### See Also

-   <span class="function">virtual</span>

apache\_request\_headers
========================

Fetch all HTTP request headers

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">apache\_request\_headers</span> ( <span
class="methodparam">void</span> )

Fetches all HTTP request headers from the current request. Works in the
Apache, FastCGI, CLI, FPM and
<a href="/book/nsapi.html" class="link">NSAPI server module</a> in
Netscape/iPlanet/SunONE webservers.

### Return Values

An associative array of all the HTTP headers in the current request, or
**`FALSE`** on failure.

### Changelog

| Version | Description                                     |
|---------|-------------------------------------------------|
| 7.3.0   | This function became available in the FPM SAPI. |

### Examples

**Example \#1 <span class="function">apache\_request\_headers</span>
example**

``` php
<?php
$headers = apache_request_headers();

foreach ($headers as $header => $value) {
    echo "$header: $value <br />\n";
}
?>
```

The above example will output something similar to:

    Accept: */*
    Accept-Language: en-us
    Accept-Encoding: gzip, deflate
    User-Agent: Mozilla/4.0
    Host: www.example.com
    Connection: Keep-Alive

### Notes

> **Note**:
>
> You can also get at the value of the common CGI variables by reading
> them from the environment, which works whether or not you are using
> PHP as an <span class="productname">Apache</span> module. Use <span
> class="function">phpinfo</span> to see a list of all of the available
> <a href="/language/variables/predefined.html" class="link">environment variables</a>.

### See Also

-   <span class="function">apache\_response\_headers</span>

apache\_reset\_timeout
======================

Reset the Apache write timer

### Description

<span class="type">bool</span> <span
class="methodname">apache\_reset\_timeout</span> ( <span
class="methodparam">void</span> )

<span class="function">apache\_reset\_timeout</span> resets the Apache
write timer, which defaults to 300 seconds. With *set\_time\_limit(0);
ignore\_user\_abort(true)* and periodic <span
class="function">apache\_reset\_timeout</span> calls, Apache can
theoretically run forever.

This function requires Apache 1.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">set\_time\_limit</span>
-   <span class="function">ignore\_user\_abort</span>

apache\_response\_headers
=========================

Fetch all HTTP response headers

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">apache\_response\_headers</span> ( <span
class="methodparam">void</span> )

Fetch all HTTP response headers. Works in the Apache, FastCGI, CLI, FPM
and <a href="/book/nsapi.html" class="link">NSAPI server module</a> in
Netscape/iPlanet/SunONE webservers.

### Return Values

An array of all Apache response headers on success or **`FALSE`** on
failure.

### Examples

**Example \#1 <span class="function">apache\_response\_headers</span>
example**

``` php
<?php
print_r(apache_response_headers());
?>
```

The above example will output something similar to:

    Array
    (
        [Accept-Ranges] => bytes
        [X-Powered-By] => PHP/4.3.8
    )

### See Also

-   <span class="function">apache\_request\_headers</span>
-   <span class="function">headers\_sent</span>
-   <span class="function">headers\_list</span>

apache\_setenv
==============

Set an Apache subprocess\_env variable

### Description

<span class="type">bool</span> <span
class="methodname">apache\_setenv</span> ( <span
class="methodparam"><span class="type">string</span> `$variable`</span>
, <span class="methodparam"><span class="type">string</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$walk_to_top`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="function">apache\_setenv</span> sets the value of the
Apache environment variable specified by `variable`.

> **Note**:
>
> When setting an Apache environment variable, the corresponding
> `$_SERVER` variable is not changed.

### Parameters

`variable`  
The environment variable that's being set.

`value`  
The new `variable` value.

`walk_to_top`  
Whether to set the top-level variable available to all Apache layers.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Setting an Apache environment variable using <span
class="function">apache\_setenv</span>**

``` php
<?php
apache_setenv("EXAMPLE_VAR", "Example Value");
?>
```

### Notes

> **Note**:
>
> <span class="function">apache\_setenv</span> can be paired up with
> <span class="function">apache\_getenv</span> across separate pages or
> for setting variables to pass to Server Side Includes (.shtml) that
> have been included in PHP scripts.

### See Also

-   <span class="function">apache\_getenv</span>

getallheaders
=============

Fetch all HTTP request headers

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">getallheaders</span> ( <span
class="methodparam">void</span> )

Fetches all HTTP headers from the current request.

This function is an alias for <span
class="function">apache\_request\_headers</span>. Please read the <span
class="function">apache\_request\_headers</span> documentation for more
information on how this function works.

### Return Values

An associative array of all the HTTP headers in the current request, or
**`FALSE`** on failure.

### Changelog

| Version | Description                                     |
|---------|-------------------------------------------------|
| 7.3.0   | This function became available in the FPM SAPI. |

### Examples

**Example \#1 <span class="function">getallheaders</span> example**

``` php
<?php

foreach (getallheaders() as $name => $value) {
    echo "$name: $value\n";
}

?>
```

### See Also

-   <span class="function">apache\_response\_headers</span>

virtual
=======

Perform an Apache sub-request

### Description

<span class="type">bool</span> <span class="methodname">virtual</span> (
<span class="methodparam"><span class="type">string</span>
`$filename`</span> )

<span class="function">virtual</span> is an Apache-specific function
which is similar to *\<!--\#include virtual...--\>* in *mod\_include*.
It performs an Apache sub-request. It is useful for including CGI
scripts or `.shtml` files, or anything else that you would parse through
Apache. Note that for a CGI script, the script must generate valid CGI
headers. At the minimum that means it must generate a *Content-Type*
header.

To run the sub-request, all buffers are terminated and flushed to the
browser, pending headers are sent too.

This function is supported when PHP is installed as an Apache module or
by the <a href="/book/nsapi.html" class="link">NSAPI server module</a>
in Netscape/iPlanet/SunONE webservers.

### Parameters

`filename`  
The file that the virtual command will be performed on.

### Return Values

Performs the virtual command on success, or returns **`FALSE`** on
failure.

### Examples

See <span class="function">apache\_note</span> for an example.

### Notes

**Warning**

The query string can be passed to the included file but `$_GET` is
copied from the parent script and only `$_SERVER['QUERY_STRING']` is
filled with the passed query string. The query string may only be passed
when using Apache 2. The requested file will not be listed in the Apache
access log.

> **Note**:
>
> Environment variables set in the requested file are not visible to the
> calling script.

> **Note**:
>
> This function may be used on PHP files. However, it is typically
> better to use <span class="function">include</span> or <span
> class="function">require</span> for PHP files.

### See Also

-   <span class="function">apache\_note</span>

**Table of Contents**

-   [apache\_child\_terminate](/ref/apache.html#apache_child_terminate)
    — Terminate apache process after this request
-   [apache\_get\_modules](/ref/apache.html#apache_get_modules) — Get a
    list of loaded Apache modules
-   [apache\_get\_version](/ref/apache.html#apache_get_version) — Fetch
    Apache version
-   [apache\_getenv](/ref/apache.html#apache_getenv) — Get an Apache
    subprocess\_env variable
-   [apache\_lookup\_uri](/ref/apache.html#apache_lookup_uri) — Perform
    a partial request for the specified URI and return all info about it
-   [apache\_note](/ref/apache.html#apache_note) — Get and set apache
    request notes
-   [apache\_request\_headers](/ref/apache.html#apache_request_headers)
    — Fetch all HTTP request headers
-   [apache\_reset\_timeout](/ref/apache.html#apache_reset_timeout) —
    Reset the Apache write timer
-   [apache\_response\_headers](/ref/apache.html#apache_response_headers)
    — Fetch all HTTP response headers
-   [apache\_setenv](/ref/apache.html#apache_setenv) — Set an Apache
    subprocess\_env variable
-   [getallheaders](/ref/apache.html#getallheaders) — Fetch all HTTP
    request headers
-   [virtual](/ref/apache.html#virtual) — Perform an Apache sub-request

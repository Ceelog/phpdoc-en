stream\_bucket\_append
======================

Append bucket to brigade

### Description

<span class="type">void</span> <span
class="methodname">stream\_bucket\_append</span> ( <span
class="methodparam"><span class="type">resource</span> `$brigade`</span>
, <span class="methodparam"><span class="type">object</span>
`$bucket`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

stream\_bucket\_make\_writeable
===============================

Return a bucket object from the brigade for operating on

### Description

<span class="type">object</span> <span
class="methodname">stream\_bucket\_make\_writeable</span> ( <span
class="methodparam"><span class="type">resource</span> `$brigade`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

stream\_bucket\_new
===================

Create a new bucket for use on the current stream

### Description

<span class="type">object</span> <span
class="methodname">stream\_bucket\_new</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">string</span>
`$buffer`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

stream\_bucket\_prepend
=======================

Prepend bucket to brigade

### Description

<span class="type">void</span> <span
class="methodname">stream\_bucket\_prepend</span> ( <span
class="methodparam"><span class="type">resource</span> `$brigade`</span>
, <span class="methodparam"><span class="type">object</span>
`$bucket`</span> )

This function can be called to prepend a bucket to a bucket brigade. It
is typically called from <span
class="methodname">php\_user\_filter::filter</span>.

### Parameters

`brigade`  
`brigade` is a resource pointing to a *bucket brigade* which contains
one or more *bucket* objects.

`bucket`  
A bucket object.

### Return Values

No value is returned.

### Examples

**Example \#1 <span class="function">stream\_bucket\_prepend</span>
examples**

``` php
<?php

class foo extends php_user_filter {
  protected $calls = 0;
  public function filter($in, $out, &$consumed, $closing) {
    while ($bucket = stream_bucket_make_writeable($in)) {
      $consumed += $bucket->datalen;
      if ($this->calls++ == 2) {
        // This bucket will appear again before any other bucket.
        stream_bucket_prepend($in, $bucket);
      }
    }
    return PSFS_FEED_ME;
  }
}
stream_filter_register('test', 'foo');
print  file_get_contents('php://filter/read=test/resource=foo');
?>
```

stream\_context\_create
=======================

Creates a stream context

### Description

<span class="type">resource</span> <span
class="methodname">stream\_context\_create</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$params`</span> \]\] )

Creates and returns a stream context with any options supplied in
`options` preset.

### Parameters

`options`  
Must be an associative array of associative arrays in the format
*$arr\['wrapper'\]\['option'\] = $value*. Refer to
<a href="/context.html" class="link">context options</a> for a list of
available wrappers and options.

Default to an empty array.

`params`  
Must be an associative array in the format *$arr\['parameter'\] =
$value*. Refer to
<a href="/context/params.html" class="link">context parameters</a> for a
listing of standard stream parameters.

### Return Values

A stream context <span class="type">resource</span>.

### Examples

**Example \#1 Using <span
class="function">stream\_context\_create</span>**

``` php
<?php
$opts = array(
  'http'=>array(
    'method'=>"GET",
    'header'=>"Accept-language: en\r\n" .
              "Cookie: foo=bar\r\n"
  )
);

$context = stream_context_create($opts);

/* Sends an http request to www.example.com
   with additional headers shown above */
$fp = fopen('http://www.example.com', 'r', false, $context);
fpassthru($fp);
fclose($fp);
?>
```

### See Also

-   <span class="function">stream\_context\_set\_option</span>
-   Listing of supported wrappers
    (<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>)
-   Context options
    (<a href="/context.html" class="xref">Context options and parameters</a>)

stream\_context\_get\_default
=============================

Retrieve the default stream context

### Description

<span class="type">resource</span> <span
class="methodname">stream\_context\_get\_default</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`</span> \]
)

Returns the default stream context which is used whenever file
operations (<span class="function">fopen</span>, <span
class="function">file\_get\_contents</span>, etc...) are called without
a context parameter. Options for the default context can optionally be
specified with this function using the same syntax as <span
class="function">stream\_context\_create</span>.

### Parameters

`options`  
<span class="simpara"> `options` must be an associative array of
associative arrays in the format *$arr\['wrapper'\]\['option'\] =
$value*. </span>

> **Note**:
>
> As of PHP 5.3.0, the <span
> class="function">stream\_context\_set\_default</span> function can be
> used to set the default context.

### Return Values

A stream context <span class="type">resource</span>.

### Examples

**Example \#1 Using <span
class="function">stream\_context\_get\_default</span>**

``` php
<?php
$default_opts = array(
  'http'=>array(
    'method'=>"GET",
    'header'=>"Accept-language: en\r\n" .
              "Cookie: foo=bar",
    'proxy'=>"tcp://10.54.1.39:8000"
  )
);


$alternate_opts = array(
  'http'=>array(
    'method'=>"POST",
    'header'=>"Content-type: application/x-www-form-urlencoded\r\n" .
              "Content-length: " . strlen("baz=bomb"),
    'content'=>"baz=bomb"
  )
);

$default = stream_context_get_default($default_opts);
$alternate = stream_context_create($alternate_opts);

/* Sends a regular GET request to proxy server at 10.54.1.39
 * For www.example.com using context options specified in $default_opts
 */
readfile('http://www.example.com');

/* Sends a POST request directly to www.example.com
 * Using context options specified in $alternate_opts
 */
readfile('http://www.example.com', false, $alternate);

?>
```

### See Also

-   <span class="function">stream\_context\_create</span>
-   Listing of supported wrappers with context options
    (<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>).

stream\_context\_get\_options
=============================

Retrieve options for a stream/wrapper/context

### Description

<span class="type">array</span> <span
class="methodname">stream\_context\_get\_options</span> ( <span
class="methodparam"><span class="type">resource</span>
`$stream_or_context`</span> )

Returns an array of options on the specified stream or context.

### Parameters

`stream_or_context`  
The <span class="type">stream</span> or <span
class="type">context</span> to get options from

### Return Values

Returns an associative array with the options.

### Examples

**Example \#1 <span
class="function">stream\_context\_get\_options</span> example**

``` php
<?php
$params = array("method" => "POST");

stream_context_set_default(array("http" => $params));

var_dump(stream_context_get_options(stream_context_get_default()));

?>
```

The above example will output something similar to:

    array(1) {
      ["http"]=>
      array(1) {
        ["method"]=>
        string(4) "POST"
      }
    }

stream\_context\_get\_params
============================

Retrieves parameters from a context

### Description

<span class="type">array</span> <span
class="methodname">stream\_context\_get\_params</span> ( <span
class="methodparam"><span class="type">resource</span>
`$stream_or_context`</span> )

Retrieves parameter and options information from the stream or context.

### Parameters

`stream_or_context`  
A stream <span class="type">resource</span> or a
<a href="/context.html" class="link">context</a> <span
class="type">resource</span>

### Return Values

Returns an associate array containing all context options and
parameters.

### Examples

**Example \#1 <span class="function">stream\_context\_get\_params</span>
example**

Basic usage example

``` php
<?php
$ctx = stream_context_create();
$params = array("notification" => "stream_notification_callback");
stream_context_set_params($ctx, $params);

var_dump(stream_context_get_params($ctx));
?>
```

The above example will output something similar to:

    array(2) {
      ["notification"]=>
      string(28) "stream_notification_callback"
      ["options"]=>
      array(0) {
      }
    }

### See Also

-   <span class="function">stream\_context\_set\_option</span>
-   <span class="function">stream\_context\_set\_params</span>

stream\_context\_set\_default
=============================

Set the default stream context

### Description

<span class="type">resource</span> <span
class="methodname">stream\_context\_set\_default</span> ( <span
class="methodparam"><span class="type">array</span> `$options`</span> )

Set the default stream context which will be used whenever file
operations (<span class="function">fopen</span>, <span
class="function">file\_get\_contents</span>, etc...) are called without
a context parameter. Uses the same syntax as <span
class="function">stream\_context\_create</span>.

### Parameters

`options`  
The options to set for the default context.

> **Note**:
>
> `options` must be an associative array of associative arrays in the
> format *$arr\['wrapper'\]\['option'\] = $value*.

### Return Values

Returns the default stream context.

### Examples

**Example \#1 <span
class="function">stream\_context\_set\_default</span> example**

``` php
<?php
$default_opts = array(
  'http'=>array(
    'method'=>"GET",
    'header'=>"Accept-language: en\r\n" .
              "Cookie: foo=bar",
    'proxy'=>"tcp://10.54.1.39:8000"
  )
);

$default = stream_context_set_default($default_opts);

/* Sends a regular GET request to proxy server at 10.54.1.39
 * For www.example.com using context options specified in $default_opts
 */
readfile('http://www.example.com');
?>
```

### See Also

-   <span class="function">stream\_context\_create</span>
-   <span class="function">stream\_context\_get\_default</span>
-   Listing of supported wrappers with context options
    (<a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>).

stream\_context\_set\_option
============================

Sets an option for a stream/wrapper/context

### Description

<span class="type">bool</span> <span
class="methodname">stream\_context\_set\_option</span> ( <span
class="methodparam"><span class="type">resource</span>
`$stream_or_context`</span> , <span class="methodparam"><span
class="type">string</span> `$wrapper`</span> , <span
class="methodparam"><span class="type">string</span> `$option`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$value`</span> )

<span class="type">bool</span> <span
class="methodname">stream\_context\_set\_option</span> ( <span
class="methodparam"><span class="type">resource</span>
`$stream_or_context`</span> , <span class="methodparam"><span
class="type">array</span> `$options`</span> )

Sets an option on the specified context. `value` is set to `option` for
`wrapper`

### Parameters

`stream_or_context`  
The stream or context resource to apply the options to.

`options`  
The options to set for `stream_or_context`.

> **Note**:
>
> `options` must be an associative array of associative arrays in the
> format *$arr\['wrapper'\]\['option'\] = $value*.
>
> Refer to
> <a href="/context.html" class="link">context options and parameters</a>
> for a listing of stream options.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

stream\_context\_set\_params
============================

Set parameters for a stream/wrapper/context

### Description

<span class="type">bool</span> <span
class="methodname">stream\_context\_set\_params</span> ( <span
class="methodparam"><span class="type">resource</span>
`$stream_or_context`</span> , <span class="methodparam"><span
class="type">array</span> `$params`</span> )

Sets parameters on the specified context.

### Parameters

`stream_or_context`  
The stream or context to apply the parameters too.

`params`  
An array of parameters to set.

> **Note**:
>
> `params` should be an associative array of the structure:
> *$params\['paramname'\] = "paramvalue";*.

### Supported parameters

| Parameters     | Purpose                                                                                                                                                                                                                                            |
|----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *notification* | Name of user-defined callback function to be called whenever a stream triggers a notification. Only supported for <a href="/wrappers/http.html" class="link">http://</a> and <a href="/wrappers/ftp.html" class="link">ftp://</a> stream wrappers. |
| *options*      | Array of options as in <a href="/context.html" class="link">context options and parameters</a>.                                                                                                                                                    |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">stream\_notification\_callback</span>

stream\_copy\_to\_stream
========================

Copies data from one stream to another

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">stream\_copy\_to\_stream</span> ( <span
class="methodparam"><span class="type">resource</span> `$source`</span>
, <span class="methodparam"><span class="type">resource</span>
`$dest`</span> \[, <span class="methodparam"><span
class="type">int</span> `$maxlength`<span class="initializer"> =
-1</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$offset`<span class="initializer"> =
0</span></span> \]\] )

Makes a copy of up to `maxlength` bytes of data from the current
position (or from the `offset` position, if specified) in `source` to
`dest`. If `maxlength` is not specified, all remaining content in
`source` will be copied.

### Parameters

`source`  
The source stream

`dest`  
The destination stream

`maxlength`  
Maximum bytes to copy

`offset`  
The offset where to start to copy data

### Return Values

Returns the total count of bytes copied, or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">stream\_copy\_to\_stream</span>
example**

``` php
<?php
$src = fopen('http://www.example.com', 'r');
$dest1 = fopen('first1k.txt', 'w');
$dest2 = fopen('remainder.txt', 'w');

echo stream_copy_to_stream($src, $dest1, 1024) . " bytes copied to first1k.txt\n";
echo stream_copy_to_stream($src, $dest2) . " bytes copied to remainder.txt\n";

?>
```

### See Also

-   <span class="function">copy</span>

stream\_filter\_append
======================

Attach a filter to a stream

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">stream\_filter\_append</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">string</span>
`$filtername`</span> \[, <span class="methodparam"><span
class="type">int</span> `$read_write`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$params`</span>
\]\] )

Adds `filtername` to the list of filters attached to `stream`.

### Parameters

`stream`  
The target stream.

`filtername`  
The filter name.

`read_write`  
By default, <span class="function">stream\_filter\_append</span> will
attach the filter to the *read filter chain* if the file was opened for
reading (i.e. File Mode: *r*, and/or *+*). The filter will also be
attached to the *write filter chain* if the file was opened for writing
(i.e. File Mode: *w*, *a*, and/or *+*). **`STREAM_FILTER_READ`**,
**`STREAM_FILTER_WRITE`**, and/or **`STREAM_FILTER_ALL`** can also be
passed to the `read_write` parameter to override this behavior.

`params`  
This filter will be added with the specified `params` to the *end* of
the list and will therefore be called last during stream operations. To
add a filter to the beginning of the list, use <span
class="function">stream\_filter\_prepend</span>.

### Return Values

Returns a resource on success or **`FALSE`** on failure. The resource
can be used to refer to this filter instance during a call to <span
class="function">stream\_filter\_remove</span>.

**`FALSE`** is returned if `stream` is not a resource or if `filtername`
cannot be located.

### Examples

**Example \#1 Controlling where filters are applied**

``` php
<?php
/* Open a test file for reading and writing */
$fp = fopen('test.txt', 'w+');

/* Apply the ROT13 filter to the
 * write filter chain, but not the
 * read filter chain */
stream_filter_append($fp, "string.rot13", STREAM_FILTER_WRITE);

/* Write a simple string to the file
 * it will be ROT13 transformed on the
 * way out */
fwrite($fp, "This is a test\n");

/* Back up to the beginning of the file */
rewind($fp);

/* Read the contents of the file back out.
 * Had the filter been applied to the
 * read filter chain as well, we would see
 * the text ROT13ed back to its original state */
fpassthru($fp);

fclose($fp);

/* Expected Output
   ---------------

Guvf vf n grfg

 */
?>
```

### Notes

> **Note**: **When using custom (user) filters**  
> <span class="simpara"> <span
> class="function">stream\_filter\_register</span> must be called first
> in order to register the desired user filter to `filtername`. </span>

> **Note**: <span class="simpara"> Stream data is read from resources
> (both local and remote) in chunks, with any unconsumed data kept in
> internal buffers. When a new filter is appended to a stream, data in
> the internal buffers is processed through the new filter at that time.
> This differs from the behavior of <span
> class="function">stream\_filter\_prepend</span>. </span>

> **Note**: <span class="simpara"> When a filter is added for read and
> write, two instances of the filter are created. <span
> class="function">stream\_filter\_append</span> must be called twice
> with **`STREAM_FILTER_READ`** and **`STREAM_FILTER_WRITE`** to get
> both filter resources. </span>

### See Also

-   <span class="function">stream\_filter\_register</span>
-   <span class="function">stream\_filter\_prepend</span>
-   <span class="function">stream\_get\_filters</span>

stream\_filter\_prepend
=======================

Attach a filter to a stream

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">stream\_filter\_prepend</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">string</span>
`$filtername`</span> \[, <span class="methodparam"><span
class="type">int</span> `$read_write`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$params`</span>
\]\] )

Adds `filtername` to the list of filters attached to `stream`.

### Parameters

`stream`  
The target stream.

`filtername`  
The filter name.

`read_write`  
By default, <span class="function">stream\_filter\_prepend</span> will
attach the filter to the *read filter chain* if the file was opened for
reading (i.e. File Mode: *r*, and/or *+*). The filter will also be
attached to the *write filter chain* if the file was opened for writing
(i.e. File Mode: *w*, *a*, and/or *+*). **`STREAM_FILTER_READ`**,
**`STREAM_FILTER_WRITE`**, and/or **`STREAM_FILTER_ALL`** can also be
passed to the `read_write` parameter to override this behavior. See
<span class="function">stream\_filter\_append</span> for an example of
using this parameter.

`params`  
This filter will be added with the specified `params` to the *beginning*
of the list and will therefore be called first during stream operations.
To add a filter to the end of the list, use <span
class="function">stream\_filter\_append</span>.

### Return Values

Returns a resource on success or **`FALSE`** on failure. The resource
can be used to refer to this filter instance during a call to <span
class="function">stream\_filter\_remove</span>.

**`FALSE`** is returned if `stream` is not a resource or if `filtername`
cannot be located.

### Notes

> **Note**: **When using custom (user) filters**  
> <span class="simpara"> <span
> class="function">stream\_filter\_register</span> must be called first
> in order to register the desired user filter to `filtername`. </span>

> **Note**: <span class="simpara"> Stream data is read from resources
> (both local and remote) in chunks, with any unconsumed data kept in
> internal buffers. When a new filter is prepended to a stream, data in
> the internal buffers, which has already been processed through other
> filters will *not* be reprocessed through the new filter at that time.
> This differs from the behavior of <span
> class="function">stream\_filter\_append</span>. </span>

> **Note**: <span class="simpara"> When a filter is added for read and
> write, two instances of the filter are created. <span
> class="function">stream\_filter\_prepend</span> must be called twice
> with **`STREAM_FILTER_READ`** and **`STREAM_FILTER_WRITE`** to get
> both filter resources. </span>

### See Also

-   <span class="function">stream\_filter\_register</span>
-   <span class="function">stream\_filter\_append</span>

stream\_filter\_register
========================

Register a user defined stream filter

### Description

<span class="type">bool</span> <span
class="methodname">stream\_filter\_register</span> ( <span
class="methodparam"><span class="type">string</span>
`$filtername`</span> , <span class="methodparam"><span
class="type">string</span> `$classname`</span> )

<span class="function">stream\_filter\_register</span> allows you to
implement your own filter on any registered stream used with all the
other filesystem functions (such as <span class="function">fopen</span>,
<span class="function">fread</span> etc.).

### Parameters

`filtername`  
The filter name to be registered.

`classname`  
To implement a filter, you need to define a class as an extension of
<span class="classname">php\_user\_filter</span> with a number of member
functions. When performing read/write operations on the stream to which
your filter is attached, PHP will pass the data through your filter (and
any other filters attached to that stream) so that the data may be
modified as desired. You must implement the methods exactly as described
in <span class="classname">php\_user\_filter</span> - doing otherwise
will lead to undefined behaviour.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

<span class="function">stream\_filter\_register</span> will return
**`FALSE`** if the `filtername` is already defined.

### Examples

**Example \#1 Filter for capitalizing characters on `foo-bar.txt`
stream**

The example below implements a filter named *strtoupper* on the
`foo-bar.txt` stream which will capitalize all letter characters written
to/read from that stream.

``` php
<?php

/* Define our filter class */
class strtoupper_filter extends php_user_filter {
  function filter($in, $out, &$consumed, $closing)
  {
    while ($bucket = stream_bucket_make_writeable($in)) {
      $bucket->data = strtoupper($bucket->data);
      $consumed += $bucket->datalen;
      stream_bucket_append($out, $bucket);
    }
    return PSFS_PASS_ON;
  }
}

/* Register our filter with PHP */
stream_filter_register("strtoupper", "strtoupper_filter")
    or die("Failed to register filter");

$fp = fopen("foo-bar.txt", "w");

/* Attach the registered filter to the stream just opened */
stream_filter_append($fp, "strtoupper");

fwrite($fp, "Line1\n");
fwrite($fp, "Word - 2\n");
fwrite($fp, "Easy As 123\n");

fclose($fp);

/* Read the contents back out
 */
readfile("foo-bar.txt");

?>
```

The above example will output:

    LINE1
    WORD - 2
    EASY AS 123

**Example \#2 Registering a generic filter class to match multiple
filter names.**

``` php
<?php

/* Define our filter class */
class string_filter extends php_user_filter {
  var $mode;

  function filter($in, $out, &$consumed, $closing)
  {
    while ($bucket = stream_bucket_make_writeable($in)) {
      if ($this->mode == 1) {
        $bucket->data = strtoupper($bucket->data);
      } elseif ($this->mode == 0) {
        $bucket->data = strtolower($bucket->data);
      }

      $consumed += $bucket->datalen;
      stream_bucket_append($out, $bucket);
    }
    return PSFS_PASS_ON;
  }

  function onCreate()
  {
    if ($this->filtername == 'str.toupper') {
      $this->mode = 1;
    } elseif ($this->filtername == 'str.tolower') {
      $this->mode = 0;
    } else {
      /* Some other str.* filter was asked for,
         report failure so that PHP will keep looking */
      return false;
    }

    return true;
  }
}

/* Register our filter with PHP */
stream_filter_register("str.*", "string_filter")
    or die("Failed to register filter");

$fp = fopen("foo-bar.txt", "w");

/* Attach the registered filter to the stream just opened
   We could alternately bind to str.tolower here */
stream_filter_append($fp, "str.toupper");

fwrite($fp, "Line1\n");
fwrite($fp, "Word - 2\n");
fwrite($fp, "Easy As 123\n");

fclose($fp);

/* Read the contents back out
 */
readfile("foo-bar.txt");
?>
```

The above example will output:

    LINE1
    WORD - 2
    EASY AS 123

### See Also

-   <span class="function">stream\_wrapper\_register</span>
-   <span class="function">stream\_filter\_append</span>
-   <span class="function">stream\_filter\_prepend</span>

stream\_filter\_remove
======================

Remove a filter from a stream

### Description

<span class="type">bool</span> <span
class="methodname">stream\_filter\_remove</span> ( <span
class="methodparam"><span class="type">resource</span>
`$stream_filter`</span> )

Removes a stream filter previously added to a stream with <span
class="function">stream\_filter\_prepend</span> or <span
class="function">stream\_filter\_append</span>. Any data remaining in
the filter's internal buffer will be flushed through to the next filter
before removing it.

### Parameters

`stream_filter`  
The stream filter to be removed.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Dynamically refiltering a stream**

``` php
<?php
/* Open a test file for reading and writing */
$fp = fopen("test.txt", "rw");

$rot13_filter = stream_filter_append($fp, "string.rot13", STREAM_FILTER_WRITE);
fwrite($fp, "This is ");
stream_filter_remove($rot13_filter);
fwrite($fp, "a test\n");

rewind($fp);
fpassthru($fp);
fclose($fp);

?>
```

The above example will output:

    Guvf vf a test

### See Also

-   <span class="function">stream\_filter\_register</span>
-   <span class="function">stream\_filter\_append</span>
-   <span class="function">stream\_filter\_prepend</span>

stream\_get\_contents
=====================

Reads remainder of a stream into a string

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">stream\_get\_contents</span> ( <span
class="methodparam"><span class="type">resource</span> `$handle`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$maxlength`<span class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$offset`<span
class="initializer"> = -1</span></span> \]\] )

Identical to <span class="function">file\_get\_contents</span>, except
that <span class="function">stream\_get\_contents</span> operates on an
already open stream resource and returns the remaining contents in a
string, up to `maxlength` bytes and starting at the specified `offset`.

### Parameters

`handle` (<span class="type">resource</span>)  
A stream resource (e.g. returned from <span
class="function">fopen</span>)

`maxlength` (<span class="type">int</span>)  
The maximum bytes to read. Defaults to -1 (read all the remaining
buffer).

`offset` (<span class="type">int</span>)  
Seek to the specified offset before reading. If this number is negative,
no seeking will occur and reading will start from the current position.

### Return Values

Returns a string or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">stream\_get\_contents</span>
example**

``` php
<?php

if ($stream = fopen('http://www.example.com', 'r')) {
    // print all the page starting at the offset 10
    echo stream_get_contents($stream, -1, 10);

    fclose($stream);
}


if ($stream = fopen('http://www.example.net', 'r')) {
    // print the first 5 bytes
    echo stream_get_contents($stream, 5);

    fclose($stream);
}

?>
```

### Notes

> **Note**: <span class="simpara">This function is binary-safe.</span>

### See Also

-   <span class="function">fgets</span>
-   <span class="function">fread</span>
-   <span class="function">fpassthru</span>

stream\_get\_filters
====================

Retrieve list of registered filters

### Description

<span class="type">array</span> <span
class="methodname">stream\_get\_filters</span> ( <span
class="methodparam">void</span> )

Retrieve the list of registered filters on the running system.

### Return Values

Returns an indexed array containing the name of all stream filters
available.

### Examples

**Example \#1 Using <span class="function">stream\_get\_filters</span>**

``` php
<?php
$streamlist = stream_get_filters();
print_r($streamlist);
?>
```

The above example will output something similar to:

    Array (
      [0] => string.rot13
      [1] => string.toupper
      [2] => string.tolower
      [3] => string.base64
      [4] => string.quoted-printable
    )

### See Also

-   <span class="function">stream\_filter\_register</span>
-   <span class="function">stream\_get\_wrappers</span>

stream\_get\_line
=================

Gets line from stream resource up to a given delimiter

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">stream\_get\_line</span> ( <span
class="methodparam"><span class="type">resource</span> `$handle`</span>
, <span class="methodparam"><span class="type">int</span>
`$length`</span> \[, <span class="methodparam"><span
class="type">string</span> `$ending`</span> \] )

Gets a line from the given handle.

Reading ends when `length` bytes have been read, when the string
specified by `ending` is found (which is *not* included in the return
value), or on EOF (whichever comes first).

This function is nearly identical to <span class="function">fgets</span>
except in that it allows end of line delimiters other than the standard
\\n, \\r, and \\r\\n, and does *not* return the delimiter itself.

### Parameters

`handle`  
A valid file handle.

`length`  
The number of bytes to read from the handle.

`ending`  
An optional string delimiter.

### Return Values

Returns a string of up to `length` bytes read from the file pointed to
by `handle`.

If an error occurs, returns **`FALSE`**.

### See Also

-   <span class="function">fread</span>
-   <span class="function">fgets</span>
-   <span class="function">fgetc</span>

stream\_get\_meta\_data
=======================

Retrieves header/meta data from streams/file pointers

### Description

<span class="type">array</span> <span
class="methodname">stream\_get\_meta\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
)

Returns information about an existing `stream`.

### Parameters

`stream`  
The stream can be any stream created by <span
class="function">fopen</span>, <span class="function">fsockopen</span>
and <span class="function">pfsockopen</span>.

### Return Values

The result array contains the following items:

-   *timed\_out* (bool) - **`TRUE`** if the stream timed out while
    waiting for data on the last call to <span
    class="function">fread</span> or <span
    class="function">fgets</span>.

-   *blocked* (bool) - **`TRUE`** if the stream is in blocking IO mode.
    See <span class="function">stream\_set\_blocking</span>.

-   *eof* (bool) - **`TRUE`** if the stream has reached end-of-file.
    Note that for socket streams this member can be **`TRUE`** even when
    *unread\_bytes* is non-zero. To determine if there is more data to
    be read, use <span class="function">feof</span> instead of reading
    this item.

-   *unread\_bytes* (int) - the number of bytes currently contained in
    the PHP's own internal buffer.

    > **Note**: <span class="simpara"> You shouldn't use this value in a
    > script. </span>

-   *stream\_type* (string) - a label describing the underlying
    implementation of the stream.

-   *wrapper\_type* (string) - a label describing the protocol wrapper
    implementation layered over the stream. See
    <a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
    for more information about wrappers.

-   *wrapper\_data* (mixed) - wrapper specific data attached to this
    stream. See
    <a href="/wrappers.html" class="xref">Supported Protocols and Wrappers</a>
    for more information about wrappers and their wrapper data.

-   *mode* (string) - the type of access required for this stream (see
    Table 1 of the
    <a href="/ref/filesystem.html#fopen" class="link">fopen()</a>
    reference)

-   *seekable* (bool) - whether the current stream can be seeked.

-   *uri* (string) - the URI/filename associated with this stream.

### Examples

**Example \#1 <span class="function">stream\_get\_meta\_data</span>
example**

``` php
<?php
$url = 'http://www.example.com/';

if (!$fp = fopen($url, 'r')) {
    trigger_error("Unable to open URL ($url)", E_USER_ERROR);
}

$meta = stream_get_meta_data($fp);

print_r($meta);

fclose($fp);
?>
```

The above example will output something similar to:

    Array
    (
        [wrapper_data] => Array
            (
                [0] => HTTP/1.1 200 OK
                [1] => Server: Apache/2.2.3 (Red Hat)
                [2] => Last-Modified: Tue, 15 Nov 2005 13:24:10 GMT
                [3] => ETag: "b300b4-1b6-4059a80bfd280"
                [4] => Accept-Ranges: bytes
                [5] => Content-Type: text/html; charset=UTF-8
                [6] => Set-Cookie: FOO=BAR; expires=Fri, 21-Dec-2012 12:00:00 GMT; path=/; domain=.example.com
                [6] => Connection: close     
                [7] => Date: Fri, 16 Oct 2009 12:00:00 GMT
                [8] => Age: 1164   
                [9] => Content-Length: 438
            )

        [wrapper_type] => http
        [stream_type] => tcp_socket/ssl
        [mode] => r
        [unread_bytes] => 438
        [seekable] => 
        [uri] => http://www.example.com/
        [timed_out] => 
        [blocked] => 1
        [eof] => 
    )

### Notes

> **Note**:
>
> This function does NOT work on sockets created by the
> <a href="/ref/sockets.html" class="link">Socket extension</a>.

### See Also

-   <span class="function">get\_headers</span>
-   <a href="/reserved/variables/httpresponseheader.html" class="link">$http_response_header</a>

stream\_get\_transports
=======================

Retrieve list of registered socket transports

### Description

<span class="type">array</span> <span
class="methodname">stream\_get\_transports</span> ( <span
class="methodparam">void</span> )

Returns an indexed array containing the name of all socket transports
available on the running system.

### Return Values

Returns an indexed array of socket transports names.

### Examples

**Example \#1 Using <span
class="function">stream\_get\_transports</span>**

``` php
<?php
$xportlist = stream_get_transports();
print_r($xportlist);
?>
```

The above example will output something similar to:

    Array (
      [0] => tcp
      [1] => udp
      [2] => unix
      [3] => udg
    )

### See Also

-   <span class="function">stream\_get\_filters</span>
-   <span class="function">stream\_get\_wrappers</span>

stream\_get\_wrappers
=====================

Retrieve list of registered streams

### Description

<span class="type">array</span> <span
class="methodname">stream\_get\_wrappers</span> ( <span
class="methodparam">void</span> )

Retrieve list of registered streams available on the running system.

### Return Values

Returns an indexed array containing the name of all stream wrappers
available on the running system.

### Examples

**Example \#1 <span class="function">stream\_get\_wrappers</span>
example**

``` php
<?php
print_r(stream_get_wrappers());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => php
        [1] => file
        [2] => http
        [3] => ftp
        [4] => compress.bzip2
        [5] => compress.zlib
    )

**Example \#2 Checking for the existence of a stream wrapper**

``` php
<?php
// check for the existence of the bzip2 stream wrapper
if (in_array('compress.bzip2', stream_get_wrappers())) {
    echo 'compress.bzip2:// support enabled.';
} else {
    echo 'compress.bzip2:// support not enabled.';
}
?>
```

### See Also

-   <span class="function">stream\_wrapper\_register</span>

stream\_is\_local
=================

Checks if a stream is a local stream

### Description

<span class="type">bool</span> <span
class="methodname">stream\_is\_local</span> ( <span
class="methodparam"><span class="type">mixed</span>
`$stream_or_url`</span> )

Checks if a stream, or a URL, is a local one or not.

### Parameters

`stream_or_url`  
The stream <span class="type">resource</span> or URL to check.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">stream\_is\_local</span> example**

Basic usage example.

``` php
<?php
var_dump(stream_is_local("http://example.com"));
var_dump(stream_is_local("/etc"));
?>
```

The above example will output something similar to:

    bool(false)
    bool(true)

stream\_isatty
==============

Check if a stream is a TTY

### Description

<span class="type">bool</span> <span
class="methodname">stream\_isatty</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
)

Determines if stream `stream` refers to a valid terminal type device.
This is a more portable version of <span
class="function">posix\_isatty</span>, since it works on Windows systems
too.

### Parameters

`stream`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">stream\_isatty</span> example**

This command can be used to determine if a standard output / standard
error stream is redirected to a file.

``` sh
php -r "var_export(stream_isatty(STDERR));"
```

The above example will output something similar to:

  
true  

``` sh
php -r "var_export(stream_isatty(STDERR));" 2>output.txt
```

The above example will output something similar to:

  
false  

stream\_notification\_callback
==============================

A callback function for the *notification* context parameter

### Description

<span class="type">void</span> <span class="methodname"><span
class="replaceable">stream\_notification\_callback</span></span> ( <span
class="methodparam"><span class="type">int</span>
`$notification_code`</span> , <span class="methodparam"><span
class="type">int</span> `$severity`</span> , <span
class="methodparam"><span class="type">string</span> `$message`</span> ,
<span class="methodparam"><span class="type">int</span>
`$message_code`</span> , <span class="methodparam"><span
class="type">int</span> `$bytes_transferred`</span> , <span
class="methodparam"><span class="type">int</span> `$bytes_max`</span> )

A <span class="type">callable</span> function, used by the
<a href="/context/params.html#context.params.notification" class="link">notification context parameter</a>,
called during an event.

> **Note**:
>
> This is *not* a real function, only a prototype of how the function
> should be.

### Parameters

`notification_code`  
One of the **`STREAM_NOTIFY_*`** notification constants.

`severity`  
One of the **`STREAM_NOTIFY_SEVERITY_*`** notification constants.

`message`  
Passed if a descriptive message is available for the event.

`message_code`  
Passed if a descriptive message code is available for the event.

The meaning of this value is dependent on the specific wrapper in use.

`bytes_transferred`  
If applicable, the `bytes_transferred` will be populated.

`bytes_max`  
If applicable, the `bytes_max` will be populated.

### Return Values

No value is returned.

### Examples

**Example \#1 <span
class="function">stream\_notification\_callback</span> example**

``` php
<?php
function stream_notification_callback($notification_code, $severity, $message, $message_code, $bytes_transferred, $bytes_max) {

    switch($notification_code) {
        case STREAM_NOTIFY_RESOLVE:
        case STREAM_NOTIFY_AUTH_REQUIRED:
        case STREAM_NOTIFY_COMPLETED:
        case STREAM_NOTIFY_FAILURE:
        case STREAM_NOTIFY_AUTH_RESULT:
            var_dump($notification_code, $severity, $message, $message_code, $bytes_transferred, $bytes_max);
            /* Ignore */
            break;

        case STREAM_NOTIFY_REDIRECTED:
            echo "Being redirected to: ", $message;
            break;

        case STREAM_NOTIFY_CONNECT:
            echo "Connected...";
            break;

        case STREAM_NOTIFY_FILE_SIZE_IS:
            echo "Got the filesize: ", $bytes_max;
            break;

        case STREAM_NOTIFY_MIME_TYPE_IS:
            echo "Found the mime-type: ", $message;
            break;

        case STREAM_NOTIFY_PROGRESS:
            echo "Made some progress, downloaded ", $bytes_transferred, " so far";
            break;
    }
    echo "\n";
}

$ctx = stream_context_create();
stream_context_set_params($ctx, array("notification" => "stream_notification_callback"));

file_get_contents("http://php.net/contact", false, $ctx);
?>
```

The above example will output something similar to:

    Connected...
    Found the mime-type: text/html; charset=utf-8
    Being redirected to: http://no.php.net/contact
    Connected...
    Got the filesize: 0
    Found the mime-type: text/html; charset=utf-8
    Being redirected to: http://no.php.net/contact.php
    Connected...
    Got the filesize: 4589
    Found the mime-type: text/html;charset=utf-8
    Made some progress, downloaded 0 so far
    Made some progress, downloaded 0 so far
    Made some progress, downloaded 0 so far
    Made some progress, downloaded 1440 so far
    Made some progress, downloaded 2880 so far
    Made some progress, downloaded 4320 so far
    Made some progress, downloaded 5760 so far
    Made some progress, downloaded 6381 so far
    Made some progress, downloaded 7002 so far

**Example \#2 Simple progressbar for commandline download client**

``` php
<?php
function usage($argv) {
    echo "Usage:\n";
    printf("\tphp %s <http://example.com/file> <localfile>\n", $argv[0]);
    exit(1);
}

function stream_notification_callback($notification_code, $severity, $message, $message_code, $bytes_transferred, $bytes_max) {
    static $filesize = null;

    switch($notification_code) {
    case STREAM_NOTIFY_RESOLVE:
    case STREAM_NOTIFY_AUTH_REQUIRED:
    case STREAM_NOTIFY_COMPLETED:
    case STREAM_NOTIFY_FAILURE:
    case STREAM_NOTIFY_AUTH_RESULT:
        /* Ignore */
        break;

    case STREAM_NOTIFY_REDIRECTED:
        echo "Being redirected to: ", $message, "\n";
        break;

    case STREAM_NOTIFY_CONNECT:
        echo "Connected...\n";
        break;

    case STREAM_NOTIFY_FILE_SIZE_IS:
        $filesize = $bytes_max;
        echo "Filesize: ", $filesize, "\n";
        break;

    case STREAM_NOTIFY_MIME_TYPE_IS:
        echo "Mime-type: ", $message, "\n";
        break;

    case STREAM_NOTIFY_PROGRESS:
        if ($bytes_transferred > 0) {
            if (!isset($filesize)) {
                printf("\rUnknown filesize.. %2d kb done..", $bytes_transferred/1024);
            } else {
                $length = (int)(($bytes_transferred/$filesize)*100);
                printf("\r[%-100s] %d%% (%2d/%2d kb)", str_repeat("=", $length). ">", $length, ($bytes_transferred/1024), $filesize/1024);
            }
        }
        break;
    }
}

isset($argv[1], $argv[2]) or usage($argv);

$ctx = stream_context_create();
stream_context_set_params($ctx, array("notification" => "stream_notification_callback"));

$fp = fopen($argv[1], "r", false, $ctx);
if (is_resource($fp) && file_put_contents($argv[2], $fp)) {
    echo "\nDone!\n";
    exit(0);
}

$err = error_get_last();
echo "\nErrrrrorr..\n", $err["message"], "\n";
exit(1);
?>
```

Executing the example above with: *php -n fetch.php
http://no2.php.net/get/php-5-LATEST.tar.bz2/from/this/mirror
php-latest.tar.bz2* will output something similar too:

    Connected...
    Mime-type: text/html; charset=utf-8
    Being redirected to: http://no2.php.net/distributions/php-5.2.5.tar.bz2
    Connected...
    Filesize: 7773024
    Mime-type: application/octet-stream
    [========================================>                                                           ] 40% (3076/7590 kb)

### See Also

-   <a href="/context/params.html" class="xref">Context parameters</a>

stream\_register\_wrapper
=========================

Alias of <span class="function">stream\_wrapper\_register</span>

### Description

This function is an alias of: <span
class="function">stream\_wrapper\_register</span>.

stream\_resolve\_include\_path
==============================

Resolve filename against the include path

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">stream\_resolve\_include\_path</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
)

Resolve `filename` against the include path according to the same rules
as <span class="function">fopen</span>/<span
class="function">include</span>.

### Parameters

`filename`  
The filename to resolve.

### Return Values

Returns a <span class="type">string</span> containing the resolved
absolute filename, or **`FALSE`** on failure.

### Examples

**Example \#1 <span
class="function">stream\_resolve\_include\_path</span> example**

Basic usage example.

``` php
<?php
var_dump(stream_resolve_include_path("test.php"));
?>
```

The above example will output something similar to:

    string(22) "/var/www/html/test.php"

stream\_select
==============

Runs the equivalent of the select() system call on the given arrays of
streams with a timeout specified by tv\_sec and tv\_usec

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">stream\_select</span> ( <span
class="methodparam"><span class="type">array</span> `&$read`</span> ,
<span class="methodparam"><span class="type">array</span>
`&$write`</span> , <span class="methodparam"><span
class="type">array</span> `&$except`</span> , <span
class="methodparam"><span class="type">int</span> `$tv_sec`</span> \[,
<span class="methodparam"><span class="type">int</span> `$tv_usec`<span
class="initializer"> = 0</span></span> \] )

The <span class="function">stream\_select</span> function accepts arrays
of streams and waits for them to change status. Its operation is
equivalent to that of the <span class="function">socket\_select</span>
function except in that it acts on streams.

### Parameters

`read`  
The streams listed in the `read` array will be watched to see if
characters become available for reading (more precisely, to see if a
read will not block - in particular, a stream resource is also ready on
end-of-file, in which case an <span class="function">fread</span> will
return a zero length string).

`write`  
The streams listed in the `write` array will be watched to see if a
write will not block.

`except`  
The streams listed in the `except` array will be watched for high
priority exceptional ("out-of-band") data arriving.

> **Note**:
>
> When <span class="function">stream\_select</span> returns, the arrays
> `read`, `write` and `except` are modified to indicate which stream
> resource(s) actually changed status. The original keys of the <span
> class="type">array</span>s are preserved.

`tv_sec`  
The `tv_sec` and `tv_usec` together form the *timeout* parameter,
`tv_sec` specifies the number of seconds while `tv_usec` the number of
microseconds. The `timeout` is an upper bound on the amount of time that
<span class="function">stream\_select</span> will wait before it
returns. If `tv_sec` and `tv_usec` are both set to *0*, <span
class="function">stream\_select</span> will not wait for data - instead
it will return immediately, indicating the current status of the
streams.

If `tv_sec` is **`NULL`** <span class="function">stream\_select</span>
can block indefinitely, returning only when an event on one of the
watched streams occurs (or if a signal interrupts the system call).

**Warning**
Using a timeout value of *0* allows you to instantaneously poll the
status of the streams, however, it is NOT a good idea to use a *0*
timeout value in a loop as it will cause your script to consume too much
CPU time.

It is much better to specify a timeout value of a few seconds, although
if you need to be checking and running other code concurrently, using a
timeout value of at least *200000* microseconds will help reduce the CPU
usage of your script.

Remember that the timeout value is the maximum time that will elapse;
<span class="function">stream\_select</span> will return as soon as the
requested streams are ready for use.

`tv_usec`  
See `tv_sec` description.

### Return Values

On success <span class="function">stream\_select</span> returns the
number of stream resources contained in the modified arrays, which may
be zero if the timeout expires before anything interesting happens. On
error **`FALSE`** is returned and a warning raised (this can happen if
the system call is interrupted by an incoming signal).

### Examples

**Example \#1 <span class="function">stream\_select</span> Example**

This example checks to see if data has arrived for reading on either
`$stream1` or `$stream2`. Since the timeout value is *0* it will return
immediately:

``` php
<?php
/* Prepare the read array */
$read   = array($stream1, $stream2);
$write  = NULL;
$except = NULL;
if (false === ($num_changed_streams = stream_select($read, $write, $except, 0))) {
    /* Error handling */
} elseif ($num_changed_streams > 0) {
    /* At least on one of the streams something interesting happened */
}
?>
```

### Notes

> **Note**:
>
> Due to a limitation in the current Zend Engine it is not possible to
> pass a constant modifier like **`NULL`** directly as a parameter to a
> function which expects this parameter to be passed by reference.
> Instead use a temporary variable or an expression with the leftmost
> member being a temporary variable:
>
> ``` php
> <?php
> $e = NULL;
> stream_select($r, $w, $e, 0);
> ?>
> ```

> **Note**:
>
> Be sure to use the *===* operator when checking for an error. Since
> the <span class="function">stream\_select</span> may return 0 the
> comparison with *==* would evaluate to **`TRUE`**:
>
> ``` php
> <?php
> $e = NULL;
> if (false === stream_select($r, $w, $e, 0)) {
>     echo "stream_select() failed\n";
> }
> ?>
> ```

> **Note**:
>
> If you read/write to a stream returned in the arrays be aware that
> they do not necessarily read/write the full amount of data you have
> requested. Be prepared to even only be able to read/write a single
> byte.

> **Note**:
>
> Some streams (like *zlib*) cannot be selected by this function.

> **Note**: **Windows compatibility**  
>
> Use of <span class="function">stream\_select</span> on file
> descriptors returned by <span class="function">proc\_open</span> will
> fail and return **`FALSE`** under Windows.
>
> **`STDIN`** from a console changes status as soon as *any* input
> events are available, but reading from the stream may still block.

### See Also

-   <span class="function">stream\_set\_blocking</span>

stream\_set\_blocking
=====================

Set blocking/non-blocking mode on a stream

### Description

<span class="type">bool</span> <span
class="methodname">stream\_set\_blocking</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">bool</span>
`$mode`</span> )

Sets blocking or non-blocking mode on a `stream`.

This function works for any stream that supports non-blocking mode
(currently, regular files and socket streams).

### Parameters

`stream`  
The stream.

`mode`  
If `mode` is **`FALSE`**, the given stream will be switched to
non-blocking mode, and if **`TRUE`**, it will be switched to blocking
mode. This affects calls like <span class="function">fgets</span> and
<span class="function">fread</span> that read from the stream. In
non-blocking mode an <span class="function">fgets</span> call will
always return right away while in blocking mode it will wait for data to
become available on the stream.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> This function was previously called as <span
> class="function">set\_socket\_blocking</span> and later <span
> class="function">socket\_set\_blocking</span> but this usage is
> deprecated.

> **Note**:
>
> On Windows, this has no affect on local files. Non-blocking IO for
> local files is not supported on Windows.

### See Also

-   <span class="function">stream\_select</span>

stream\_set\_chunk\_size
========================

Set the stream chunk size

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">stream\_set\_chunk\_size</span> ( <span
class="methodparam"><span class="type">resource</span> `$fp`</span> ,
<span class="methodparam"><span class="type">int</span>
`$chunk_size`</span> )

Set the stream chunk size.

### Parameters

`fp`  
The target stream.

`chunk_size`  
The desired new chunk size.

### Return Values

Returns the previous chunk size on success.

Will return **`FALSE`** if `chunk_size` is less than 1 or greater than
**`PHP_INT_MAX`**.

### Errors/Exceptions

Will emit an **`E_WARNING`** level error if `chunk_size` is less than 1
or greater than **`PHP_INT_MAX`**.

stream\_set\_read\_buffer
=========================

Set read file buffering on the given stream

### Description

<span class="type">int</span> <span
class="methodname">stream\_set\_read\_buffer</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">int</span>
`$buffer`</span> )

Sets the read buffer. It's the equivalent of <span
class="function">stream\_set\_write\_buffer</span>, but for read
operations.

### Parameters

`stream`  
The file pointer.

`buffer`  
The number of bytes to buffer. If `buffer` is 0 then read operations are
unbuffered. This ensures that all reads with <span
class="function">fread</span> are completed before other processes are
allowed to read from that input stream.

### Return Values

Returns 0 on success, or another value if the request cannot be honored.

### See Also

-   <span class="function">stream\_set\_write\_buffer</span>

stream\_set\_timeout
====================

Set timeout period on a stream

### Description

<span class="type">bool</span> <span
class="methodname">stream\_set\_timeout</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">int</span>
`$seconds`</span> \[, <span class="methodparam"><span
class="type">int</span> `$microseconds`<span class="initializer"> =
0</span></span> \] )

Sets the timeout value on `stream`, expressed in the sum of `seconds`
and `microseconds`.

When the stream times out, the 'timed\_out' key of the array returned by
<span class="function">stream\_get\_meta\_data</span> is set to
**`TRUE`**, although no error/warning is generated.

### Parameters

`stream`  
The target stream.

`seconds`  
The seconds part of the timeout to be set.

`microseconds`  
The microseconds part of the timeout to be set.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">stream\_set\_timeout</span>
example**

``` php
<?php
$fp = fsockopen("www.example.com", 80);
if (!$fp) {
    echo "Unable to open\n";
} else {

    fwrite($fp, "GET / HTTP/1.0\r\n\r\n");
    stream_set_timeout($fp, 2);
    $res = fread($fp, 2000);

    $info = stream_get_meta_data($fp);
    fclose($fp);

    if ($info['timed_out']) {
        echo 'Connection timed out!';
    } else {
        echo $res;
    }

}
?>
```

### Notes

> **Note**:
>
> This function doesn't work with advanced operations like <span
> class="function">stream\_socket\_recvfrom</span>, use <span
> class="function">stream\_select</span> with timeout parameter instead.

This function was previously called as <span
class="function">set\_socket\_timeout</span> and later <span
class="function">socket\_set\_timeout</span> but this usage is
deprecated.

### See Also

-   <span class="function">fsockopen</span>
-   <span class="function">fopen</span>

stream\_set\_write\_buffer
==========================

Sets write file buffering on the given stream

### Description

<span class="type">int</span> <span
class="methodname">stream\_set\_write\_buffer</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">int</span>
`$buffer`</span> )

Sets the buffering for write operations on the given `stream` to
`buffer` bytes.

### Parameters

`stream`  
The file pointer.

`buffer`  
The number of bytes to buffer. If `buffer` is 0 then write operations
are unbuffered. This ensures that all writes with <span
class="function">fwrite</span> are completed before other processes are
allowed to write to that output stream.

### Return Values

Returns 0 on success, or another value if the request cannot be honored.

### Examples

**Example \#1 <span class="function">stream\_set\_write\_buffer</span>
example**

The following example demonstrates how to use <span
class="function">stream\_set\_write\_buffer</span> to create an
unbuffered stream.

``` php
<?php
$fp = fopen($file, "w");
if ($fp) {
  if (stream_set_write_buffer($fp, 0) !== 0) {
      // changing the buffering failed
  }
  fwrite($fp, $output);
  fclose($fp);
}
?>
```

### See Also

-   <span class="function">fopen</span>
-   <span class="function">fwrite</span>

stream\_socket\_accept
======================

Accept a connection on a socket created by <span
class="function">stream\_socket\_server</span>

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">stream\_socket\_accept</span> ( <span
class="methodparam"><span class="type">resource</span>
`$server_socket`</span> \[, <span class="methodparam"><span
class="type">float</span> `$timeout`<span class="initializer"> =
ini\_get("default\_socket\_timeout")</span></span> \[, <span
class="methodparam"><span class="type">string</span> `&$peername`</span>
\]\] )

Accept a connection on a socket previously created by <span
class="function">stream\_socket\_server</span>.

### Parameters

`server_socket`  
The server socket to accept a connection from.

`timeout`  
Override the default socket accept timeout. Time should be given in
seconds.

`peername`  
Will be set to the name (address) of the client which connected, if
included and available from the selected transport.

> **Note**:
>
> Can also be determined later using <span
> class="function">stream\_socket\_get\_name</span>.

### Return Values

Returns a stream to the accepted socket connection or **`FALSE`** on
failure.

### Notes

**Warning**

This function should not be used with UDP server sockets. Instead, use
<span class="function">stream\_socket\_recvfrom</span> and <span
class="function">stream\_socket\_sendto</span>.

### See Also

-   <span class="function">stream\_socket\_server</span>
-   <span class="function">stream\_socket\_get\_name</span>
-   <span class="function">stream\_set\_blocking</span>
-   <span class="function">stream\_set\_timeout</span>
-   <span class="function">fgets</span>
-   <span class="function">fgetss</span>
-   <span class="function">fwrite</span>
-   <span class="function">fclose</span>
-   <span class="function">feof</span>
-   <a href="/ref/curl.html" class="xref">cURL Functions</a>

stream\_socket\_client
======================

Open Internet or Unix domain socket connection

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">stream\_socket\_client</span> ( <span
class="methodparam"><span class="type">string</span>
`$remote_socket`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$errno`</span> \[, <span
class="methodparam"><span class="type">string</span> `&$errstr`</span>
\[, <span class="methodparam"><span class="type">float</span>
`$timeout`<span class="initializer"> =
ini\_get("default\_socket\_timeout")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = STREAM\_CLIENT\_CONNECT</span></span> \[, <span
class="methodparam"><span class="type">resource</span> `$context`</span>
\]\]\]\]\] )

Initiates a stream or datagram connection to the destination specified
by `remote_socket`. The type of socket created is determined by the
transport specified using standard URL formatting: *transport://target*.
For Internet Domain sockets (AF\_INET) such as TCP and UDP, the *target*
portion of the `remote_socket` parameter should consist of a hostname or
IP address followed by a colon and a port number. For Unix domain
sockets, the `target` portion should point to the socket file on the
filesystem.

> **Note**:
>
> The stream will by default be opened in blocking mode. You can switch
> it to non-blocking mode by using <span
> class="function">stream\_set\_blocking</span>.

### Parameters

`remote_socket`  
Address to the socket to connect to.

`errno`  
Will be set to the system level error number if connection fails.

`errstr`  
Will be set to the system level error message if the connection fails.

`timeout`  
Number of seconds until the *connect()* system call should timeout.

> **Note**: <span class="simpara"> This parameter only applies when not
> making asynchronous connection attempts. </span>

> **Note**:
>
> To set a timeout for reading/writing data over the socket, use the
> <span class="function">stream\_set\_timeout</span>, as the `timeout`
> only applies while making connecting the socket.

`flags`  
Bitmask field which may be set to any combination of connection flags.
Currently the select of connection flags is limited to
**`STREAM_CLIENT_CONNECT`** (default), **`STREAM_CLIENT_ASYNC_CONNECT`**
and **`STREAM_CLIENT_PERSISTENT`**.

`context`  
A valid context resource created with <span
class="function">stream\_context\_create</span>.

### Return Values

On success a stream resource is returned which may be used together with
the other file functions (such as <span class="function">fgets</span>,
<span class="function">fgetss</span>, <span
class="function">fwrite</span>, <span class="function">fclose</span>,
and <span class="function">feof</span>), **`FALSE`** on failure.

### Errors/Exceptions

On failure the `errno` and `errstr` arguments will be populated with the
actual system level error that occurred in the system-level *connect()*
call. If the value returned in `errno` is *0* and the function returned
**`FALSE`**, it is an indication that the error occurred before the
*connect()* call. This is most likely due to a problem initializing the
socket. Note that the `errno` and `errstr` arguments will always be
passed by reference.

### Examples

**Example \#1 <span class="function">stream\_socket\_client</span>
example**

``` php
<?php
$fp = stream_socket_client("tcp://www.example.com:80", $errno, $errstr, 30);
if (!$fp) {
    echo "$errstr ($errno)<br />\n";
} else {
    fwrite($fp, "GET / HTTP/1.0\r\nHost: www.example.com\r\nAccept: */*\r\n\r\n");
    while (!feof($fp)) {
        echo fgets($fp, 1024);
    }
    fclose($fp);
}
?>
```

**Example \#2 Using UDP connection**

Retrieving the day and time from the UDP service "daytime" (port 13) on
localhost.

``` php
<?php
$fp = stream_socket_client("udp://127.0.0.1:13", $errno, $errstr);
if (!$fp) {
    echo "ERROR: $errno - $errstr<br />\n";
} else {
    fwrite($fp, "\n");
    echo fread($fp, 26);
    fclose($fp);
}
?>
```

### Notes

**Warning**

UDP sockets will sometimes appear to have opened without an error, even
if the remote host is unreachable. The error will only become apparent
when you read or write data to/from the socket. The reason for this is
because UDP is a "connectionless" protocol, which means that the
operating system does not try to establish a link for the socket until
it actually needs to send or receive data.

> **Note**: <span class="simpara">When specifying a numerical IPv6
> address (e.g. *fe80::1*), you must enclose the IP in square
> brackets—for example, *tcp://\[fe80::1\]:80*.</span>

> **Note**:
>
> Depending on the environment, the Unix domain or the optional connect
> timeout may not be available. A list of available transports can be
> retrieved using <span class="function">stream\_get\_transports</span>.
> See
> <a href="/transports.html" class="xref">List of Supported Socket Transports</a>
> for a list of built in transports.

### See Also

-   <span class="function">stream\_socket\_server</span>
-   <span class="function">stream\_set\_blocking</span>
-   <span class="function">stream\_set\_timeout</span>
-   <span class="function">stream\_select</span>
-   <span class="function">fgets</span>
-   <span class="function">fgetss</span>
-   <span class="function">fwrite</span>
-   <span class="function">fclose</span>
-   <span class="function">feof</span>
-   <a href="/ref/curl.html" class="xref">cURL Functions</a>

stream\_socket\_enable\_crypto
==============================

Turns encryption on/off on an already connected socket

### Description

<span class="type">mixed</span> <span
class="methodname">stream\_socket\_enable\_crypto</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">bool</span>
`$enable`</span> \[, <span class="methodparam"><span
class="type">int</span> `$crypto_type`</span> \[, <span
class="methodparam"><span class="type">resource</span>
`$session_stream`</span> \]\] )

Enable or disable encryption on the stream.

Once the crypto settings are established, cryptography can be turned on
and off dynamically by passing **`TRUE`** or **`FALSE`** in the `enable`
parameter.

### Parameters

`stream`  
The stream resource.

`enable`  
Enable/disable cryptography on the stream.

`crypto_type`  
Setup encryption on the stream. Valid methods are

-   <span class="simpara">**`STREAM_CRYPTO_METHOD_SSLv2_CLIENT`**</span>
-   <span class="simpara">**`STREAM_CRYPTO_METHOD_SSLv3_CLIENT`**</span>
-   <span
    class="simpara">**`STREAM_CRYPTO_METHOD_SSLv23_CLIENT`**</span>
-   <span class="simpara">**`STREAM_CRYPTO_METHOD_ANY_CLIENT`**</span>
-   <span class="simpara">**`STREAM_CRYPTO_METHOD_TLS_CLIENT`**</span>
-   <span
    class="simpara">**`STREAM_CRYPTO_METHOD_TLSv1_0_CLIENT`**</span>
-   <span
    class="simpara">**`STREAM_CRYPTO_METHOD_TLSv1_1_CLIENT`**</span>
-   <span
    class="simpara">**`STREAM_CRYPTO_METHOD_TLSv1_2_CLIENT`**</span>
-   <span class="simpara">**`STREAM_CRYPTO_METHOD_SSLv2_SERVER`**</span>
-   <span class="simpara">**`STREAM_CRYPTO_METHOD_SSLv3_SERVER`**</span>
-   <span
    class="simpara">**`STREAM_CRYPTO_METHOD_SSLv23_SERVER`**</span>
-   <span class="simpara">**`STREAM_CRYPTO_METHOD_ANY_SERVER`**</span>
-   <span class="simpara">**`STREAM_CRYPTO_METHOD_TLS_SERVER`**</span>
-   <span
    class="simpara">**`STREAM_CRYPTO_METHOD_TLSv1_0_SERVER`**</span>
-   <span
    class="simpara">**`STREAM_CRYPTO_METHOD_TLSv1_1_SERVER`**</span>
-   <span
    class="simpara">**`STREAM_CRYPTO_METHOD_TLSv1_2_SERVER`**</span>

If omitted, the *crypto\_method* context option on the stream's SSL
context will be used instead.

`session_stream`  
Seed the stream with settings from `session_stream`.

### Return Values

Returns **`TRUE`** on success, **`FALSE`** if negotiation has failed or
*0* if there isn't enough data and you should try again (only for
non-blocking sockets).

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                               |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 5.6.0   | Introduce **`STREAM_CRYPTO_METHOD_ANY_CLIENT`**, **`STREAM_CRYPTO_METHOD_TLSv1_0_CLIENT`**, **`STREAM_CRYPTO_METHOD_TLSv1_1_CLIENT`**, **`STREAM_CRYPTO_METHOD_TLSv1_2_CLIENT`**, **`STREAM_CRYPTO_METHOD_ANY_SERVER`**, **`STREAM_CRYPTO_METHOD_TLSv1_0_SERVER`**, **`STREAM_CRYPTO_METHOD_TLSv1_1_SERVER`**, **`STREAM_CRYPTO_METHOD_TLSv1_2_SERVER`**. |
| 5.6.0   | The `crypto_type` is now optional.                                                                                                                                                                                                                                                                                                                        |

### Examples

**Example \#1 <span
class="function">stream\_socket\_enable\_crypto</span> example**

``` php
<?php
$fp = stream_socket_client("tcp://myproto.example.com:31337", $errno, $errstr, 30);
if (!$fp) {
    die("Unable to connect: $errstr ($errno)");
}

/* Turn on encryption for login phase */
stream_socket_enable_crypto($fp, true, STREAM_CRYPTO_METHOD_SSLv23_CLIENT);
fwrite($fp, "USER god\r\n");
fwrite($fp, "PASS secret\r\n");

/* Turn off encryption for the rest */
stream_socket_enable_crypto($fp, false);

while ($motd = fgets($fp)) {
    echo $motd;
}

fclose($fp);
?>
```

The above example will output something similar to:

### See Also

-   <a href="/ref/openssl.html" class="xref">OpenSSL Functions</a>
-   <a href="/transports.html" class="xref">List of Supported Socket Transports</a>

stream\_socket\_get\_name
=========================

Retrieve the name of the local or remote sockets

### Description

<span class="type">string</span> <span
class="methodname">stream\_socket\_get\_name</span> ( <span
class="methodparam"><span class="type">resource</span> `$handle`</span>
, <span class="methodparam"><span class="type">bool</span>
`$want_peer`</span> )

Returns the local or remote name of a given socket connection.

### Parameters

`handle`  
The socket to get the name of.

`want_peer`  
If set to **`TRUE`** the *remote* socket name will be returned, if set
to **`FALSE`** the *local* socket name will be returned.

### Return Values

The name of the socket.

### See Also

-   <span class="function">stream\_socket\_accept</span>

stream\_socket\_pair
====================

Creates a pair of connected, indistinguishable socket streams

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">stream\_socket\_pair</span> ( <span
class="methodparam"><span class="type">int</span> `$domain`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> ,
<span class="methodparam"><span class="type">int</span>
`$protocol`</span> )

<span class="function">stream\_socket\_pair</span> creates a pair of
connected, indistinguishable socket streams. This function is commonly
used in IPC (Inter-Process Communication).

### Parameters

`domain`  
The protocol family to be used: **`STREAM_PF_INET`**,
**`STREAM_PF_INET6`** or **`STREAM_PF_UNIX`**

`type`  
The type of communication to be used: **`STREAM_SOCK_DGRAM`**,
**`STREAM_SOCK_RAW`**, **`STREAM_SOCK_RDM`**,
**`STREAM_SOCK_SEQPACKET`** or **`STREAM_SOCK_STREAM`**

`protocol`  
The protocol to be used: **`STREAM_IPPROTO_ICMP`**,
**`STREAM_IPPROTO_IP`**, **`STREAM_IPPROTO_RAW`**,
**`STREAM_IPPROTO_TCP`** or **`STREAM_IPPROTO_UDP`**

> **Note**: <span class="simpara"> Please consult the
> <a href="/stream/constants.html" class="link">Streams constant list</a>
> for further details on each constant. </span>

### Return Values

Returns an <span class="type">array</span> with the two socket resources
on success, or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">stream\_socket\_pair</span>
example**

This example shows the basic usage of <span
class="function">stream\_socket\_pair</span> in Inter-Process
Communication.

``` php
<?php

$sockets = stream_socket_pair(STREAM_PF_UNIX, STREAM_SOCK_STREAM, STREAM_IPPROTO_IP);
$pid     = pcntl_fork();

if ($pid == -1) {
     die('could not fork');

} else if ($pid) {
     /* parent */
    fclose($sockets[0]);

    fwrite($sockets[1], "child PID: $pid\n");
    echo fgets($sockets[1]);

    fclose($sockets[1]);

} else {
    /* child */
    fclose($sockets[1]);

    fwrite($sockets[0], "message from child\n");
    echo fgets($sockets[0]);

    fclose($sockets[0]);
}

?>
```

The above example will output something similar to:

    child PID: 1378
    message from child

stream\_socket\_recvfrom
========================

Receives data from a socket, connected or not

### Description

<span class="type">string</span> <span
class="methodname">stream\_socket\_recvfrom</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">int</span>
`$length`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">string</span> `&$address`</span> \]\] )

<span class="function">stream\_socket\_recvfrom</span> accepts data from
a remote socket up to `length` bytes.

### Parameters

`socket`  
The remote socket.

`length`  
The number of bytes to receive from the `socket`.

`flags`  
The value of `flags` can be any combination of the following:

|                   |                                                                                                                                                                                                         |
|-------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`STREAM_OOB`**  | Process OOB (*out-of-band*) data.                                                                                                                                                                       |
| **`STREAM_PEEK`** | Retrieve data from the socket, but do not consume the buffer. Subsequent calls to <span class="function">fread</span> or <span class="function">stream\_socket\_recvfrom</span> will see the same data. |

`address`  
If `address` is provided it will be populated with the address of the
remote socket.

### Return Values

Returns the read data, as a string

### Examples

**Example \#1 <span class="function">stream\_socket\_recvfrom</span>
example**

``` php
<?php
/* Open a server socket to port 1234 on localhost */
$server = stream_socket_server('tcp://127.0.0.1:1234');

/* Accept a connection */
$socket = stream_socket_accept($server);

/* Grab a packet (1500 is a typical MTU size) of OOB data */
echo "Received Out-Of-Band: '" . stream_socket_recvfrom($socket, 1500, STREAM_OOB) . "'\n";

/* Take a peek at the normal in-band data, but don't consume it. */
echo "Data: '" . stream_socket_recvfrom($socket, 1500, STREAM_PEEK) . "'\n";

/* Get the exact same packet again, but remove it from the buffer this time. */
echo "Data: '" . stream_socket_recvfrom($socket, 1500) . "'\n";

/* Close it up */
fclose($socket);
fclose($server);
?>
```

### Notes

> **Note**:
>
> If a message received is longer than the `length` parameter, excess
> bytes may be discarded depending on the type of socket the message is
> received from (such as UDP).

> **Note**:
>
> Calls to <span class="function">stream\_socket\_recvfrom</span> on
> socket-based streams, after calls to buffer-based stream functions
> (like <span class="function">fread</span> or <span
> class="function">stream\_get\_line</span>) read data directly from the
> socket and bypass the stream buffer.

### See Also

-   <span class="function">stream\_socket\_sendto</span>
-   <span class="function">stream\_socket\_client</span>
-   <span class="function">stream\_socket\_server</span>

stream\_socket\_sendto
======================

Sends a message to a socket, whether it is connected or not

### Description

<span class="type">int</span> <span
class="methodname">stream\_socket\_sendto</span> ( <span
class="methodparam"><span class="type">resource</span> `$socket`</span>
, <span class="methodparam"><span class="type">string</span>
`$data`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">string</span> `$address`</span> \]\] )

Sends the specified `data` through the `socket`.

### Parameters

`socket`  
The socket to send `data` to.

`data`  
The data to be sent.

`flags`  
The value of `flags` can be any combination of the following:

|                  |                                 |
|------------------|---------------------------------|
| **`STREAM_OOB`** | Process OOB (out-of-band) data. |

`address`  
The address specified when the socket stream was created will be used
unless an alternate address is specified in `address`.

If specified, it must be in dotted quad (or \[ipv6\]) format.

### Return Values

Returns a result code, as an integer.

### Examples

**Example \#1 <span class="function">stream\_socket\_sendto</span>
Example**

``` php
<?php
/* Open a socket to port 1234 on localhost */
$socket = stream_socket_client('tcp://127.0.0.1:1234');

/* Send ordinary data via ordinary channels. */
fwrite($socket, "Normal data transmit.");

/* Send more data out of band. */
stream_socket_sendto($socket, "Out of Band data.", STREAM_OOB);

/* Close it up */
fclose($socket);
?>
```

### See Also

-   <span class="function">stream\_socket\_recvfrom</span>
-   <span class="function">stream\_socket\_client</span>
-   <span class="function">stream\_socket\_server</span>

stream\_socket\_server
======================

Create an Internet or Unix domain server socket

### Description

<span class="type"><span class="type">resource</span><span
class="type">false</span></span> <span
class="methodname">stream\_socket\_server</span> ( <span
class="methodparam"><span class="type">string</span>
`$local_socket`</span> \[, <span class="methodparam"><span
class="type">int</span> `&$errno`</span> \[, <span
class="methodparam"><span class="type">string</span> `&$errstr`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`<span class="initializer"> = STREAM\_SERVER\_BIND \|
STREAM\_SERVER\_LISTEN</span></span> \[, <span class="methodparam"><span
class="type">resource</span> `$context`</span> \]\]\]\] )

Creates a stream or datagram socket on the specified `local_socket`.

This function only creates a socket, to begin accepting connections use
<span class="function">stream\_socket\_accept</span>.

### Parameters

`local_socket`  
The type of socket created is determined by the transport specified
using standard URL formatting: *transport://target*.

For Internet Domain sockets (**`AF_INET`**) such as TCP and UDP, the
*target* portion of the `remote_socket` parameter should consist of a
hostname or IP address followed by a colon and a port number. For Unix
domain sockets, the *target* portion should point to the socket file on
the filesystem.

Depending on the environment, Unix domain sockets may not be available.
A list of available transports can be retrieved using <span
class="function">stream\_get\_transports</span>. See
<a href="/transports.html" class="xref">List of Supported Socket Transports</a>
for a list of bulitin transports.

`errno`  
If the optional `errno` and `errstr` arguments are present they will be
set to indicate the actual system level error that occurred in the
system-level *socket()*, *bind()*, and *listen()* calls. If the value
returned in `errno` is *0* and the function returned **`FALSE`**, it is
an indication that the error occurred before the *bind()* call. This is
most likely due to a problem initializing the socket. Note that the
`errno` and `errstr` arguments will always be passed by reference.

`errstr`  
See `errno` description.

`flags`  
A bitmask field which may be set to any combination of socket creation
flags.

> **Note**:
>
> For UDP sockets, you must use **`STREAM_SERVER_BIND`** as the `flags`
> parameter.

`context`  

### Return Values

Returns the created stream, or **`FALSE`** on error.

### Examples

**Example \#1 Using TCP server sockets**

``` php
<?php
$socket = stream_socket_server("tcp://0.0.0.0:8000", $errno, $errstr);
if (!$socket) {
  echo "$errstr ($errno)<br />\n";
} else {
  while ($conn = stream_socket_accept($socket)) {
    fwrite($conn, 'The local time is ' . date('n/j/Y g:i a') . "\n");
    fclose($conn);
  }
  fclose($socket);
}
?>
```

The example below shows how to act as a time server which can respond to
time queries as shown in an example on <span
class="function">stream\_socket\_client</span>.

> **Note**: <span class="simpara"> Most systems require root access to
> create a server socket on a port below 1024. </span>

**Example \#2 Using UDP server sockets**

``` php
<?php
$socket = stream_socket_server("udp://127.0.0.1:1113", $errno, $errstr, STREAM_SERVER_BIND);
if (!$socket) {
    die("$errstr ($errno)");
}

do {
    $pkt = stream_socket_recvfrom($socket, 1, 0, $peer);
    echo "$peer\n";
    stream_socket_sendto($socket, date("D M j H:i:s Y\r\n"), 0, $peer);
} while ($pkt !== false);

?>
```

### Notes

> **Note**: <span class="simpara">When specifying a numerical IPv6
> address (e.g. *fe80::1*), you must enclose the IP in square
> brackets—for example, *tcp://\[fe80::1\]:80*.</span>

### See Also

-   <span class="function">stream\_socket\_client</span>
-   <span class="function">stream\_set\_blocking</span>
-   <span class="function">stream\_set\_timeout</span>
-   <span class="function">fgets</span>
-   <span class="function">fgetss</span>
-   <span class="function">fwrite</span>
-   <span class="function">fclose</span>
-   <span class="function">feof</span>
-   <a href="/ref/curl.html" class="link">Curl extension</a>

stream\_socket\_shutdown
========================

Shutdown a full-duplex connection

### Description

<span class="type">bool</span> <span
class="methodname">stream\_socket\_shutdown</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
, <span class="methodparam"><span class="type">int</span> `$how`</span>
)

Shutdowns (partially or not) a full-duplex connection.

> **Note**:
>
> The associated buffer, or buffers, may or may not be emptied.

### Parameters

`stream`  
An open stream (opened with <span
class="function">stream\_socket\_client</span>, for example)

`how`  
One of the following constants: **`STREAM_SHUT_RD`** (disable further
receptions), **`STREAM_SHUT_WR`** (disable further transmissions) or
**`STREAM_SHUT_RDWR`** (disable further receptions and transmissions).

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">stream\_socket\_shutdown</span>
example**

``` php
<?php

$server = stream_socket_server('tcp://127.0.0.1:1337');
$client = stream_socket_client('tcp://127.0.0.1:1337');

var_dump(fputs($client, "hello"));

stream_socket_shutdown($client, STREAM_SHUT_WR);
var_dump(fputs($client, "hello")); // doesn't work now

?>
```

The above example will output something similar to:

    int(5)

    Notice: fputs(): send of 5 bytes failed with errno=32 Broken pipe in test.php on line 9
    int(0)

### See Also

-   <span class="function">fclose</span>

stream\_supports\_lock
======================

Tells whether the stream supports locking

### Description

<span class="type">bool</span> <span
class="methodname">stream\_supports\_lock</span> ( <span
class="methodparam"><span class="type">resource</span> `$stream`</span>
)

Tells whether the stream supports locking through <span
class="function">flock</span>.

### Parameters

`stream`  
The stream to check.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">flock</span>

stream\_wrapper\_register
=========================

Register a URL wrapper implemented as a PHP class

### Description

<span class="type">bool</span> <span
class="methodname">stream\_wrapper\_register</span> ( <span
class="methodparam"><span class="type">string</span> `$protocol`</span>
, <span class="methodparam"><span class="type">string</span>
`$classname`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags` <span class="initializer"> =
0</span></span> \] )

Allows you to implement your own protocol handlers and streams for use
with all the other filesystem functions (such as <span
class="function">fopen</span>, <span class="function">fread</span>
etc.).

### Parameters

`protocol`  
The wrapper name to be registered.

`classname`  
The classname which implements the `protocol`.

`flags`  
Should be set to **`STREAM_IS_URL`** if `protocol` is a URL protocol.
Default is 0, local stream.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

<span class="function">stream\_wrapper\_register</span> will return
**`FALSE`** if the `protocol` already has a handler.

### Examples

**Example \#1 How to register a stream wrapper**

``` php
<?php
$existed = in_array("var", stream_get_wrappers());
if ($existed) {
    stream_wrapper_unregister("var");
}
stream_wrapper_register("var", "VariableStream");
$myvar = "";

$fp = fopen("var://myvar", "r+");

fwrite($fp, "line1\n");
fwrite($fp, "line2\n");
fwrite($fp, "line3\n");

rewind($fp);
while (!feof($fp)) {
    echo fgets($fp);
}
fclose($fp);
var_dump($myvar);

if ($existed) {
    stream_wrapper_restore("var");
}

?>
```

The above example will output:

    line1
    line2
    line3
    string(18) "line1
    line2
    line3
    "

### See Also

-   The
    <a href="/class/streamwrapper.html" class="xref">streamWrapper</a>
    prototype class
-   <a href="/stream/examples.html#Example%20class%20registered%20as%20stream%20wrapper" class="xref"></a>
-   <span class="function">stream\_wrapper\_unregister</span>
-   <span class="function">stream\_wrapper\_restore</span>
-   <span class="function">stream\_get\_wrappers</span>

stream\_wrapper\_restore
========================

Restores a previously unregistered built-in wrapper

### Description

<span class="type">bool</span> <span
class="methodname">stream\_wrapper\_restore</span> ( <span
class="methodparam"><span class="type">string</span> `$protocol`</span>
)

Restores a built-in wrapper previously unregistered with <span
class="function">stream\_wrapper\_unregister</span>.

### Parameters

`protocol`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

stream\_wrapper\_unregister
===========================

Unregister a URL wrapper

### Description

<span class="type">bool</span> <span
class="methodname">stream\_wrapper\_unregister</span> ( <span
class="methodparam"><span class="type">string</span> `$protocol`</span>
)

Allows you to disable an already defined stream wrapper. Once the
wrapper has been disabled you may override it with a user-defined
wrapper using <span class="function">stream\_wrapper\_register</span> or
reenable it later on with <span
class="function">stream\_wrapper\_restore</span>.

### Parameters

`protocol`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

**Table of Contents**

-   [stream\_bucket\_append](/ref/stream.html#stream_bucket_append) —
    Append bucket to brigade
-   [stream\_bucket\_make\_writeable](/ref/stream.html#stream_bucket_make_writeable)
    — Return a bucket object from the brigade for operating on
-   [stream\_bucket\_new](/ref/stream.html#stream_bucket_new) — Create a
    new bucket for use on the current stream
-   [stream\_bucket\_prepend](/ref/stream.html#stream_bucket_prepend) —
    Prepend bucket to brigade
-   [stream\_context\_create](/ref/stream.html#stream_context_create) —
    Creates a stream context
-   [stream\_context\_get\_default](/ref/stream.html#stream_context_get_default)
    — Retrieve the default stream context
-   [stream\_context\_get\_options](/ref/stream.html#stream_context_get_options)
    — Retrieve options for a stream/wrapper/context
-   [stream\_context\_get\_params](/ref/stream.html#stream_context_get_params)
    — Retrieves parameters from a context
-   [stream\_context\_set\_default](/ref/stream.html#stream_context_set_default)
    — Set the default stream context
-   [stream\_context\_set\_option](/ref/stream.html#stream_context_set_option)
    — Sets an option for a stream/wrapper/context
-   [stream\_context\_set\_params](/ref/stream.html#stream_context_set_params)
    — Set parameters for a stream/wrapper/context
-   [stream\_copy\_to\_stream](/ref/stream.html#stream_copy_to_stream) —
    Copies data from one stream to another
-   [stream\_filter\_append](/ref/stream.html#stream_filter_append) —
    Attach a filter to a stream
-   [stream\_filter\_prepend](/ref/stream.html#stream_filter_prepend) —
    Attach a filter to a stream
-   [stream\_filter\_register](/ref/stream.html#stream_filter_register)
    — Register a user defined stream filter
-   [stream\_filter\_remove](/ref/stream.html#stream_filter_remove) —
    Remove a filter from a stream
-   [stream\_get\_contents](/ref/stream.html#stream_get_contents) —
    Reads remainder of a stream into a string
-   [stream\_get\_filters](/ref/stream.html#stream_get_filters) —
    Retrieve list of registered filters
-   [stream\_get\_line](/ref/stream.html#stream_get_line) — Gets line
    from stream resource up to a given delimiter
-   [stream\_get\_meta\_data](/ref/stream.html#stream_get_meta_data) —
    Retrieves header/meta data from streams/file pointers
-   [stream\_get\_transports](/ref/stream.html#stream_get_transports) —
    Retrieve list of registered socket transports
-   [stream\_get\_wrappers](/ref/stream.html#stream_get_wrappers) —
    Retrieve list of registered streams
-   [stream\_is\_local](/ref/stream.html#stream_is_local) — Checks if a
    stream is a local stream
-   [stream\_isatty](/ref/stream.html#stream_isatty) — Check if a stream
    is a TTY
-   [stream\_notification\_callback](/ref/stream.html#stream_notification_callback)
    — A callback function for the notification context parameter
-   [stream\_register\_wrapper](/ref/stream.html#stream_register_wrapper)
    — Alias of stream\_wrapper\_register
-   [stream\_resolve\_include\_path](/ref/stream.html#stream_resolve_include_path)
    — Resolve filename against the include path
-   [stream\_select](/ref/stream.html#stream_select) — Runs the
    equivalent of the select() system call on the given arrays of
    streams with a timeout specified by tv\_sec and tv\_usec
-   [stream\_set\_blocking](/ref/stream.html#stream_set_blocking) — Set
    blocking/non-blocking mode on a stream
-   [stream\_set\_chunk\_size](/ref/stream.html#stream_set_chunk_size) —
    Set the stream chunk size
-   [stream\_set\_read\_buffer](/ref/stream.html#stream_set_read_buffer)
    — Set read file buffering on the given stream
-   [stream\_set\_timeout](/ref/stream.html#stream_set_timeout) — Set
    timeout period on a stream
-   [stream\_set\_write\_buffer](/ref/stream.html#stream_set_write_buffer)
    — Sets write file buffering on the given stream
-   [stream\_socket\_accept](/ref/stream.html#stream_socket_accept) —
    Accept a connection on a socket created by stream\_socket\_server
-   [stream\_socket\_client](/ref/stream.html#stream_socket_client) —
    Open Internet or Unix domain socket connection
-   [stream\_socket\_enable\_crypto](/ref/stream.html#stream_socket_enable_crypto)
    — Turns encryption on/off on an already connected socket
-   [stream\_socket\_get\_name](/ref/stream.html#stream_socket_get_name)
    — Retrieve the name of the local or remote sockets
-   [stream\_socket\_pair](/ref/stream.html#stream_socket_pair) —
    Creates a pair of connected, indistinguishable socket streams
-   [stream\_socket\_recvfrom](/ref/stream.html#stream_socket_recvfrom)
    — Receives data from a socket, connected or not
-   [stream\_socket\_sendto](/ref/stream.html#stream_socket_sendto) —
    Sends a message to a socket, whether it is connected or not
-   [stream\_socket\_server](/ref/stream.html#stream_socket_server) —
    Create an Internet or Unix domain server socket
-   [stream\_socket\_shutdown](/ref/stream.html#stream_socket_shutdown)
    — Shutdown a full-duplex connection
-   [stream\_supports\_lock](/ref/stream.html#stream_supports_lock) —
    Tells whether the stream supports locking
-   [stream\_wrapper\_register](/ref/stream.html#stream_wrapper_register)
    — Register a URL wrapper implemented as a PHP class
-   [stream\_wrapper\_restore](/ref/stream.html#stream_wrapper_restore)
    — Restores a previously unregistered built-in wrapper
-   [stream\_wrapper\_unregister](/ref/stream.html#stream_wrapper_unregister)
    — Unregister a URL wrapper

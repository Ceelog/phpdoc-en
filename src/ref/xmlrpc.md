xmlrpc\_decode\_request
=======================

Decodes XML into native PHP types

### Description

<span class="type">mixed</span> <span
class="methodname">xmlrpc\_decode\_request</span> ( <span
class="methodparam"><span class="type">string</span> `$xml`</span> ,
<span class="methodparam"><span class="type">string</span>
`&$method`</span> \[, <span class="methodparam"><span
class="type">string</span> `$encoding`</span> \] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_decode
==============

Decodes XML into native PHP types

### Description

<span class="type">mixed</span> <span
class="methodname">xmlrpc\_decode</span> ( <span
class="methodparam"><span class="type">string</span> `$xml`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$encoding`<span class="initializer"> = "iso-8859-1"</span></span> \] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`xml`  
XML response returned by XMLRPC method.

`encoding`  
Input encoding supported by iconv.

### Return Values

Returns either an array, or an integer, or a string, or a boolean
according to the response returned by the XMLRPC method.

### Examples

See example by <span class="function">xmlrpc\_encode\_request</span>.

### See Also

-   <span class="function">xmlrpc\_encode\_request</span>
-   <span class="function">xmlrpc\_is\_fault</span>

xmlrpc\_encode\_request
=======================

Generates XML for a method request

### Description

<span class="type">string</span> <span
class="methodname">xmlrpc\_encode\_request</span> ( <span
class="methodparam"><span class="type">string</span> `$method`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$params`</span> \[, <span class="methodparam"><span
class="type">array</span> `$output_options`</span> \] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`method`  
Name of the method to call.

`params`  
Method parameters compatible with method signature.

`output_options`  
Array specifying output options may contain (default values are
emphasised):

-   output\_type: php, *xml*

-   verbosity: no\_white\_space, newlines\_only, *pretty*

-   escaping: cdata, *non-ascii, non-print, markup* (may be a string
    with one value or an array with multiple values)

-   version: simple, *xmlrpc*, soap 1.1, auto

-   encoding: *iso-8859-1*, other character set supported by iconv

### Return Values

Returns a string containing the XML representation of the request.

### Examples

**Example \#1 XMLRPC client functions example**

``` php
<?php
$request = xmlrpc_encode_request("method", array(1, 2, 3));
$context = stream_context_create(array('http' => array(
    'method' => "POST",
    'header' => "Content-Type: text/xml",
    'content' => $request
)));
$file = file_get_contents("http://www.example.com/xmlrpc", false, $context);
$response = xmlrpc_decode($file);
if ($response && xmlrpc_is_fault($response)) {
    trigger_error("xmlrpc: $response[faultString] ($response[faultCode])");
} else {
    print_r($response);
}
?>
```

### See Also

-   <span class="function">stream\_context\_create</span>
-   <span class="function">file\_get\_contents</span>
-   <span class="function">xmlrpc\_decode</span>

xmlrpc\_encode
==============

Generates XML for a PHP value

### Description

<span class="type">string</span> <span
class="methodname">xmlrpc\_encode</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_get\_type
=================

Gets xmlrpc type for a PHP value

### Description

<span class="type">string</span> <span
class="methodname">xmlrpc\_get\_type</span> ( <span
class="methodparam"><span class="type">mixed</span> `$value`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

This function is especially useful for base64 and datetime strings.

### Parameters

`value`  
PHP value

### Return Values

Returns the XML-RPC type.

### Examples

**Example \#1 XML-RPC type example**

``` php
<?php
echo xmlrpc_get_type(null) . "\n"; // base64
echo xmlrpc_get_type(false) . "\n"; // boolean
echo xmlrpc_get_type(1) . "\n"; // int
echo xmlrpc_get_type(1.0) . "\n"; // double
echo xmlrpc_get_type("") . "\n"; // string
echo xmlrpc_get_type(array()) . "\n"; // array
echo xmlrpc_get_type(new stdClass) . "\n"; // array
echo xmlrpc_get_type(STDIN) . "\n"; // int
?>
```

### See Also

-   <span class="function">xmlrpc\_set\_type</span>

xmlrpc\_is\_fault
=================

Determines if an array value represents an XMLRPC fault

### Description

<span class="type">bool</span> <span
class="methodname">xmlrpc\_is\_fault</span> ( <span
class="methodparam"><span class="type">array</span> `$arg`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`arg`  
Array returned by <span class="function">xmlrpc\_decode</span>.

### Return Values

Returns **`true`** if the argument means fault, **`false`** otherwise.
Fault description is available in *$arg\["faultString"\]*, fault code is
in *$arg\["faultCode"\]*.

### Examples

See example by <span class="function">xmlrpc\_encode\_request</span>.

### See Also

-   <span class="function">xmlrpc\_decode</span>

xmlrpc\_parse\_method\_descriptions
===================================

Decodes XML into a list of method descriptions

### Description

<span class="type">array</span> <span
class="methodname">xmlrpc\_parse\_method\_descriptions</span> ( <span
class="methodparam"><span class="type">string</span> `$xml`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_server\_add\_introspection\_data
========================================

Adds introspection documentation

### Description

<span class="type">int</span> <span
class="methodname">xmlrpc\_server\_add\_introspection\_data</span> (
<span class="methodparam"><span class="type">resource</span>
`$server`</span> , <span class="methodparam"><span
class="type">array</span> `$desc`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_server\_call\_method
============================

Parses XML requests and call methods

### Description

<span class="type">string</span> <span
class="methodname">xmlrpc\_server\_call\_method</span> ( <span
class="methodparam"><span class="type">resource</span> `$server`</span>
, <span class="methodparam"><span class="type">string</span>
`$xml`</span> , <span class="methodparam"><span
class="type">mixed</span> `$user_data`</span> \[, <span
class="methodparam"><span class="type">array</span>
`$output_options`</span> \] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_server\_create
======================

Creates an xmlrpc server

### Description

<span class="type">resource</span> <span
class="methodname">xmlrpc\_server\_create</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_server\_destroy
=======================

Destroys server resources

### Description

<span class="type">bool</span> <span
class="methodname">xmlrpc\_server\_destroy</span> ( <span
class="methodparam"><span class="type">resource</span> `$server`</span>
)

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_server\_register\_introspection\_callback
=================================================

Register a PHP function to generate documentation

### Description

<span class="type">bool</span> <span
class="methodname">xmlrpc\_server\_register\_introspection\_callback</span>
( <span class="methodparam"><span class="type">resource</span>
`$server`</span> , <span class="methodparam"><span
class="type">string</span> `$function`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_server\_register\_method
================================

Register a PHP function to resource method matching method\_name

### Description

<span class="type">bool</span> <span
class="methodname">xmlrpc\_server\_register\_method</span> ( <span
class="methodparam"><span class="type">resource</span> `$server`</span>
, <span class="methodparam"><span class="type">string</span>
`$method_name`</span> , <span class="methodparam"><span
class="type">string</span> `$function`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

xmlrpc\_set\_type
=================

Sets xmlrpc type, base64 or datetime, for a PHP string value

### Description

<span class="type">bool</span> <span
class="methodname">xmlrpc\_set\_type</span> ( <span
class="methodparam"><span class="type">string</span> `&$value`</span> ,
<span class="methodparam"><span class="type">string</span>
`$type`</span> )

Sets xmlrpc type, base64 or datetime, for a PHP string value.

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`value`  
Value to set the type

`type`  
'base64' or 'datetime'

### Return Values

Returns **`true`** on success or **`false`** on failure. If successful,
`value` is converted to an object.

### Examples

**Example \#1 A <span class="function">xmlrpc\_set\_type</span>
example**

``` php
<?php

$params = date("Ymd\TH:i:s", time());
xmlrpc_set_type($params, 'datetime');
echo xmlrpc_encode($params);

?>
```

The above example will output something similar to:

    <?xml version="1.0" encoding="utf-8"?>
    <params>
    <param>
     <value>
      <dateTime.iso8601>20090322T23:43:03</dateTime.iso8601>
     </value>
    </param>
    </params>

### Errors/Exceptions

Issues E\_WARNING with type unsupported by XMLRPC.

**Table of Contents**

-   [xmlrpc\_decode\_request](/ref/xmlrpc.html#xmlrpc_decode_request) —
    Decodes XML into native PHP types
-   [xmlrpc\_decode](/ref/xmlrpc.html#xmlrpc_decode) — Decodes XML into
    native PHP types
-   [xmlrpc\_encode\_request](/ref/xmlrpc.html#xmlrpc_encode_request) —
    Generates XML for a method request
-   [xmlrpc\_encode](/ref/xmlrpc.html#xmlrpc_encode) — Generates XML for
    a PHP value
-   [xmlrpc\_get\_type](/ref/xmlrpc.html#xmlrpc_get_type) — Gets xmlrpc
    type for a PHP value
-   [xmlrpc\_is\_fault](/ref/xmlrpc.html#xmlrpc_is_fault) — Determines
    if an array value represents an XMLRPC fault
-   [xmlrpc\_parse\_method\_descriptions](/ref/xmlrpc.html#xmlrpc_parse_method_descriptions)
    — Decodes XML into a list of method descriptions
-   [xmlrpc\_server\_add\_introspection\_data](/ref/xmlrpc.html#xmlrpc_server_add_introspection_data)
    — Adds introspection documentation
-   [xmlrpc\_server\_call\_method](/ref/xmlrpc.html#xmlrpc_server_call_method)
    — Parses XML requests and call methods
-   [xmlrpc\_server\_create](/ref/xmlrpc.html#xmlrpc_server_create) —
    Creates an xmlrpc server
-   [xmlrpc\_server\_destroy](/ref/xmlrpc.html#xmlrpc_server_destroy) —
    Destroys server resources
-   [xmlrpc\_server\_register\_introspection\_callback](/ref/xmlrpc.html#xmlrpc_server_register_introspection_callback)
    — Register a PHP function to generate documentation
-   [xmlrpc\_server\_register\_method](/ref/xmlrpc.html#xmlrpc_server_register_method)
    — Register a PHP function to resource method matching method\_name
-   [xmlrpc\_set\_type](/ref/xmlrpc.html#xmlrpc_set_type) — Sets xmlrpc
    type, base64 or datetime, for a PHP string value

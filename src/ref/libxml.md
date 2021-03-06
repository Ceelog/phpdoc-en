libxml\_clear\_errors
=====================

Clear libxml error buffer

### Description

<span class="type">void</span> <span
class="methodname">libxml\_clear\_errors</span> ( <span
class="methodparam">void</span> )

<span class="function">libxml\_clear\_errors</span> clears the libxml
error buffer.

### Return Values

No value is returned.

### See Also

-   <span class="function">libxml\_get\_errors</span>
-   <span class="function">libxml\_get\_last\_error</span>

libxml\_disable\_entity\_loader
===============================

Disable the ability to load external entities

### Description

<span class="type">bool</span> <span
class="methodname">libxml\_disable\_entity\_loader</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$disable`<span
class="initializer"> = **`true`**</span></span> \] )

Disable/enable the ability to load external entities. Note that
disabling the loading of external entities may cause general issues with
loading XML documents. However, as of libxml 2.9.0 entity substitution
is disabled by default, so there is no need to disable the loading of
external entities.

### Parameters

`disable`  
Disable (**`true`**) or enable (**`false`**) libxml extensions (such as
<a href="/book/dom.html" class="xref">DOM</a>,
<a href="/book/xmlwriter.html" class="xref">XMLWriter</a> and
<a href="/book/xmlreader.html" class="xref">XMLReader</a>) to load
external entities.

### Return Values

Returns the previous value.

### See Also

-   <span class="function">libxml\_use\_internal\_errors</span>
-   <a href="/libxml/constants.html" class="link">The <strong><code>LIBXML_NONET</code></strong> constant</a>

libxml\_get\_errors
===================

Retrieve array of errors

### Description

<span class="type">array</span> <span
class="methodname">libxml\_get\_errors</span> ( <span
class="methodparam">void</span> )

Retrieve array of errors.

### Return Values

Returns an array with <span class="type">LibXMLError</span> objects if
there are any errors in the buffer, or an empty array otherwise.

### Examples

**Example \#1 A <span class="function">libxml\_get\_errors</span>
example**

This example demonstrates how to build a simple libxml error handler.

``` php
<?php

libxml_use_internal_errors(true);

$xmlstr = <<< XML
<?xml version='1.0' standalone='yes'?>
<movies>
 <movie>
  <titles>PHP: Behind the Parser</title>
 </movie>
</movies>
XML;

$doc = simplexml_load_string($xmlstr);
$xml = explode("\n", $xmlstr);

if ($doc === false) {
    $errors = libxml_get_errors();

    foreach ($errors as $error) {
        echo display_xml_error($error, $xml);
    }

    libxml_clear_errors();
}


function display_xml_error($error, $xml)
{
    $return  = $xml[$error->line - 1] . "\n";
    $return .= str_repeat('-', $error->column) . "^\n";

    switch ($error->level) {
        case LIBXML_ERR_WARNING:
            $return .= "Warning $error->code: ";
            break;
         case LIBXML_ERR_ERROR:
            $return .= "Error $error->code: ";
            break;
        case LIBXML_ERR_FATAL:
            $return .= "Fatal Error $error->code: ";
            break;
    }

    $return .= trim($error->message) .
               "\n  Line: $error->line" .
               "\n  Column: $error->column";

    if ($error->file) {
        $return .= "\n  File: $error->file";
    }

    return "$return\n\n--------------------------------------------\n\n";
}

?>
```

The above example will output:

      <titles>PHP: Behind the Parser</title>
    ----------------------------------------------^
    Fatal Error 76: Opening and ending tag mismatch: titles line 4 and title
      Line: 4
      Column: 46

    --------------------------------------------

### See Also

-   <span class="function">libxml\_get\_last\_error</span>
-   <span class="function">libxml\_clear\_errors</span>

libxml\_get\_last\_error
========================

Retrieve last error from libxml

### Description

<span class="type"><span class="type">LibXMLError</span><span
class="type">false</span></span> <span
class="methodname">libxml\_get\_last\_error</span> ( <span
class="methodparam">void</span> )

Retrieve last error from libxml.

### Return Values

Returns a <span class="type">LibXMLError</span> object if there is any
error in the buffer, **`false`** otherwise.

### See Also

-   <span class="function">libxml\_get\_errors</span>
-   <span class="function">libxml\_clear\_errors</span>

libxml\_set\_external\_entity\_loader
=====================================

Changes the default external entity loader

### Description

<span class="type">bool</span> <span
class="methodname">libxml\_set\_external\_entity\_loader</span> ( <span
class="methodparam"><span class="type"><span
class="type">callable</span><span class="type">null</span></span>
`$resolver_function`</span> )

Changes the default external entity loader.

### Parameters

`resolver_function`  
A <span class="type">callable</span> that takes three arguments. Two
strings, a public id and system id, and a context (an array with four
keys) as the third argument. This callback should return a resource, a
string from which a resource can be opened, or **`null`**.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span
class="function">libxml\_set\_external\_entity\_loader</span> example**

``` php
<?php
$xml = <<<XML
<!DOCTYPE foo PUBLIC "-//FOO/BAR" "http://example.com/foobar">
<foo>bar</foo>
XML;

$dtd = <<<DTD
<!ELEMENT foo (#PCDATA)>
DTD;

libxml_set_external_entity_loader(
    function ($public, $system, $context) use($dtd) {
        var_dump($public);
        var_dump($system);
        var_dump($context);
        $f = fopen("php://temp", "r+");
        fwrite($f, $dtd);
        rewind($f);
        return $f;
    }
);

$dd = new DOMDocument;
$r  = $dd->loadXML($xml);

var_dump($dd->validate());
?>
```

The above example will output:

    string(10) "-//FOO/BAR"
    string(25) "http://example.com/foobar"
    array(4) {
        ["directory"]    => NULL
        ["intSubName"]   => NULL
        ["extSubURI"]    => NULL
        ["extSubSystem"] => NULL
    }
    bool(true)

### See Also

-   <span class="function">libxml\_disable\_entity\_loader</span>

libxml\_set\_streams\_context
=============================

Set the streams context for the next libxml document load or write

### Description

<span class="type">void</span> <span
class="methodname">libxml\_set\_streams\_context</span> ( <span
class="methodparam"><span class="type">resource</span> `$context`</span>
)

Sets the streams context for the next libxml document load or write.

### Parameters

`context`  
The stream context resource (created with <span
class="function">stream\_context\_create</span>)

### Return Values

No value is returned.

### Examples

**Example \#1 A <span
class="function">libxml\_set\_streams\_context</span> example**

``` php
<?php

$opts = array(
    'http' => array(
        'user_agent' => 'PHP libxml agent',
    )
);

$context = stream_context_create($opts);
libxml_set_streams_context($context);

// request a file through HTTP
$doc = DOMDocument::load('http://www.example.com/file.xml');

?>
```

### See Also

-   <span class="function">stream\_context\_create</span>

libxml\_use\_internal\_errors
=============================

Disable libxml errors and allow user to fetch error information as
needed

### Description

<span class="type">bool</span> <span
class="methodname">libxml\_use\_internal\_errors</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">bool</span><span class="type">null</span></span>
`$use_errors`<span class="initializer"> = **`null`**</span></span> \] )

<span class="function">libxml\_use\_internal\_errors</span> allows you
to disable standard libxml errors and enable user error handling.

### Parameters

`use_errors`  
Enable (**`true`**) user error handling or disable (**`false`**) user
error handling. Disabling will also clear any existing libxml errors.

### Return Values

This function returns the previous value of `use_errors`.

### Changelog

| Version | Description                                                            |
|---------|------------------------------------------------------------------------|
| 8.0.0   | `use_errors` is nullable now. Previously, its default was **`false`**. |

### Examples

**Example \#1 A <span
class="function">libxml\_use\_internal\_errors</span> example**

This example demonstrates the basic usage of libxml errors and the value
returned by this function.

``` php
<?php

// enable user error handling
var_dump(libxml_use_internal_errors(true));

// load the document
$doc = new DOMDocument;

if (!$doc->load('file.xml')) {
    foreach (libxml_get_errors() as $error) {
        // handle errors here
    }

    libxml_clear_errors();
}

?>
```

The above example will output:

    bool(false)

### See Also

-   <span class="function">libxml\_clear\_errors</span>
-   <span class="function">libxml\_get\_errors</span>

**Table of Contents**

-   [libxml\_clear\_errors](/ref/libxml.html#libxml_clear_errors) —
    Clear libxml error buffer
-   [libxml\_disable\_entity\_loader](/ref/libxml.html#libxml_disable_entity_loader)
    — Disable the ability to load external entities
-   [libxml\_get\_errors](/ref/libxml.html#libxml_get_errors) — Retrieve
    array of errors
-   [libxml\_get\_last\_error](/ref/libxml.html#libxml_get_last_error) —
    Retrieve last error from libxml
-   [libxml\_set\_external\_entity\_loader](/ref/libxml.html#libxml_set_external_entity_loader)
    — Changes the default external entity loader
-   [libxml\_set\_streams\_context](/ref/libxml.html#libxml_set_streams_context)
    — Set the streams context for the next libxml document load or write
-   [libxml\_use\_internal\_errors](/ref/libxml.html#libxml_use_internal_errors)
    — Disable libxml errors and allow user to fetch error information as
    needed

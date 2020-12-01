utf8\_decode
============

Converts a string with ISO-8859-1 characters encoded with UTF-8 to
single-byte ISO-8859-1

### Description

<span class="type">string</span> <span
class="methodname">utf8\_decode</span> ( <span class="methodparam"><span
class="type">string</span> `$data`</span> )

This function converts the string `data` from the *UTF-8* encoding to
*ISO-8859-1*. Bytes in the string which are not valid *UTF-8*, and
*UTF-8* characters which do not exist in *ISO-8859-1* (that is,
characters above *U+00FF*) are replaced with *?*.

> **Note**:
>
> Many web pages marked as using the *ISO-8859-1* character encoding
> actually use the similar *Windows-1252* encoding, and web browsers
> will interpret *ISO-8859-1* web pages as *Windows-1252*.
> *Windows-1252* features additional printable characters, such as the
> Euro sign (*€*) and curly quotes (*“* *”*), instead of certain
> *ISO-8859-1* control characters. This function will not convert such
> *Windows-1252* characters correctly. Use a different function if
> *Windows-1252* conversion is required.

### Parameters

`data`  
A UTF-8 encoded string.

### Return Values

Returns the ISO-8859-1 translation of `data`.

### Changelog

| Version | Description                                                                                                                                    |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | This function has been moved to the core of PHP, and therefore lifting the requirement on the XML extension for this function to be available. |

### See Also

-   <span class="function">utf8\_encode</span> - Performs the reverse
    conversion
-   <span class="function">mb\_convert\_encoding</span> - Converts
    between various character encodings, including UTF-8, ISO-8859-1 and
    Windows-1252
-   <span class="function">iconv</span> - Converts between various
    character encodings
-   <span class="function">recode\_string</span> - Converts between
    various character encodings

utf8\_encode
============

Encodes an ISO-8859-1 string to UTF-8

### Description

<span class="type">string</span> <span
class="methodname">utf8\_encode</span> ( <span class="methodparam"><span
class="type">string</span> `$data`</span> )

This function converts the string `data` from the *ISO-8859-1* encoding
to *UTF-8*.

> **Note**:
>
> Many web pages marked as using the *ISO-8859-1* character encoding
> actually use the similar *Windows-1252* encoding, and web browsers
> will interpret *ISO-8859-1* web pages as *Windows-1252*.
> *Windows-1252* features additional printable characters, such as the
> Euro sign (*€*) and curly quotes (*“* *”*), instead of certain
> *ISO-8859-1* control characters. This function will not convert such
> *Windows-1252* characters correctly. Use a different function if
> *Windows-1252* conversion is required.

### Parameters

`data`  
An ISO-8859-1 string.

### Return Values

Returns the UTF-8 translation of `data`.

### Changelog

| Version | Description                                                                                                                                    |
|---------|------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | This function has been moved to the core of PHP, and therefore lifting the requirement on the XML extension for this function to be available. |

### See Also

-   <span class="function">utf8\_decode</span> - Performs the reverse
    conversion
-   <span class="function">mb\_convert\_encoding</span> - Converts
    between various character encodings, including UTF-8, ISO-8859-1 and
    Windows-1252
-   <span class="function">iconv</span> - Converts between various
    character encodings
-   <span class="function">recode\_string</span> - Converts between
    various character encodings

xml\_error\_string
==================

Get XML parser error string

### Description

<span class="type"><span class="type">string</span><span
class="type">null</span></span> <span
class="methodname">xml\_error\_string</span> ( <span
class="methodparam"><span class="type">int</span> `$error_code`</span> )

Gets the XML parser error string associated with the given `error_code`.

### Parameters

`error_code`  
An error code from <span class="function">xml\_get\_error\_code</span>.

### Return Values

Returns a string with a textual description of the error `error_code`,
or **`FALSE`** if no description was found.

### See Also

-   <span class="function">xml\_get\_error\_code</span>

xml\_get\_current\_byte\_index
==============================

Get current byte index for an XML parser

### Description

<span class="type">int</span> <span
class="methodname">xml\_get\_current\_byte\_index</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
)

Gets the current byte index of the given XML parser.

### Parameters

`parser`  
A reference to the XML parser to get byte index from.

### Return Values

This function returns **`FALSE`** if `parser` does not refer to a valid
parser, or else it returns which byte index the parser is currently at
in its data buffer (starting at 0).

### Notes

**Warning**

This function returns byte index according to UTF-8 encoded text
disregarding if input is in another encoding.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span class="function">xml\_get\_current\_column\_number</span>
-   <span class="function">xml\_get\_current\_line\_number</span>

xml\_get\_current\_column\_number
=================================

Get current column number for an XML parser

### Description

<span class="type">int</span> <span
class="methodname">xml\_get\_current\_column\_number</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
)

Gets the current column number of the given XML parser.

### Parameters

`parser`  
A reference to the XML parser to get column number from.

### Return Values

This function returns **`FALSE`** if `parser` does not refer to a valid
parser, or else it returns which column on the current line (as given by
<span class="function">xml\_get\_current\_line\_number</span>) the
parser is currently at.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span class="function">xml\_get\_current\_byte\_index</span>
-   <span class="function">xml\_get\_current\_line\_number</span>

xml\_get\_current\_line\_number
===============================

Get current line number for an XML parser

### Description

<span class="type">int</span> <span
class="methodname">xml\_get\_current\_line\_number</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
)

Gets the current line number for the given XML parser.

### Parameters

`parser`  
A reference to the XML parser to get line number from.

### Return Values

This function returns **`FALSE`** if `parser` does not refer to a valid
parser, or else it returns which line the parser is currently at in its
data buffer.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span class="function">xml\_get\_current\_column\_number</span>
-   <span class="function">xml\_get\_current\_byte\_index</span>

xml\_get\_error\_code
=====================

Get XML parser error code

### Description

<span class="type">int</span> <span
class="methodname">xml\_get\_error\_code</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
)

Gets the XML parser error code.

### Parameters

`parser`  
A reference to the XML parser to get error code from.

### Return Values

This function returns **`FALSE`** if `parser` does not refer to a valid
parser, or else it returns one of the error codes listed in the
<a href="/xml/error-codes.html" class="link">error codes section</a>.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span class="function">xml\_error\_string</span>

xml\_parse\_into\_struct
========================

Parse XML data into an array structure

### Description

<span class="type">int</span> <span
class="methodname">xml\_parse\_into\_struct</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">string</span>
`$data`</span> , <span class="methodparam"><span
class="type">array</span> `&$values`</span> \[, <span
class="methodparam"><span class="type">array</span> `&$index`<span
class="initializer"> = **`NULL`**</span></span> \] )

This function parses an XML string into 2 parallel array structures, one
(`index`) containing pointers to the location of the appropriate values
in the `values` array. These last two parameters must be passed by
reference.

### Parameters

`parser`  
A reference to the XML parser.

`data`  
A string containing the XML data.

`values`  
An array containing the values of the XML data

`index`  
An array containing pointers to the location of the appropriate values
in the $values.

### Return Values

<span class="function">xml\_parse\_into\_struct</span> returns 0 for
failure and 1 for success. This is not the same as **`FALSE`** and
**`TRUE`**, be careful with operators such as ===.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

Below is an example that illustrates the internal structure of the
arrays being generated by the function. We use a simple *note* tag
embedded inside a *para* tag, and then we parse this and print out the
structures generated:

**Example \#1 <span class="function">xml\_parse\_into\_struct</span>
example**

``` php
<?php
$simple = "<para><note>simple note</note></para>";
$p = xml_parser_create();
xml_parse_into_struct($p, $simple, $vals, $index);
xml_parser_free($p);
echo "Index array\n";
print_r($index);
echo "\nVals array\n";
print_r($vals);
?>
```

When we run that code, the output will be:

    Index array
    Array
    (
        [PARA] => Array
            (
                [0] => 0
                [1] => 2
            )

        [NOTE] => Array
            (
                [0] => 1
            )

    )

    Vals array
    Array
    (
        [0] => Array
            (
                [tag] => PARA
                [type] => open
                [level] => 1
            )

        [1] => Array
            (
                [tag] => NOTE
                [type] => complete
                [level] => 2
                [value] => simple note
            )

        [2] => Array
            (
                [tag] => PARA
                [type] => close
                [level] => 1
            )

    )

Event-driven parsing (based on the expat library) can get complicated
when you have an XML document that is complex. This function does not
produce a DOM style object, but it generates structures amenable of
being transversed in a tree fashion. Thus, we can create objects
representing the data in the XML file easily. Let's consider the
following XML file representing a small database of aminoacids
information:

**Example \#2 moldb.xml - small database of molecular information**

``` xml
<?xml version="1.0"?>
<moldb>

  <molecule>
      <name>Alanine</name>
      <symbol>ala</symbol>
      <code>A</code>
      <type>hydrophobic</type>
  </molecule>

  <molecule>
      <name>Lysine</name>
      <symbol>lys</symbol>
      <code>K</code>
      <type>charged</type>
  </molecule>

</moldb>
```

And some code to parse the document and generate the appropriate
objects:

**Example \#3 parsemoldb.php - parses moldb.xml into an array of
molecular objects**

``` php
<?php

class AminoAcid {
    var $name;  // aa name
    var $symbol;    // three letter symbol
    var $code;  // one letter code
    var $type;  // hydrophobic, charged or neutral
    
    function __construct ($aa) 
    {
        foreach ($aa as $k=>$v)
            $this->$k = $aa[$k];
    }
}

function readDatabase($filename) 
{
    // read the XML database of aminoacids
    $data = implode("", file($filename));
    $parser = xml_parser_create();
    xml_parser_set_option($parser, XML_OPTION_CASE_FOLDING, 0);
    xml_parser_set_option($parser, XML_OPTION_SKIP_WHITE, 1);
    xml_parse_into_struct($parser, $data, $values, $tags);
    xml_parser_free($parser);

    // loop through the structures
    foreach ($tags as $key=>$val) {
        if ($key == "molecule") {
            $molranges = $val;
            // each contiguous pair of array entries are the 
            // lower and upper range for each molecule definition
            for ($i=0; $i < count($molranges); $i+=2) {
                $offset = $molranges[$i] + 1;
                $len = $molranges[$i + 1] - $offset;
                $tdb[] = parseMol(array_slice($values, $offset, $len));
            }
        } else {
            continue;
        }
    }
    return $tdb;
}

function parseMol($mvalues) 
{
    for ($i=0; $i < count($mvalues); $i++) {
        $mol[$mvalues[$i]["tag"]] = $mvalues[$i]["value"];
    }
    return new AminoAcid($mol);
}

$db = readDatabase("moldb.xml");
echo "** Database of AminoAcid objects:\n";
print_r($db);

?>
```

After executing `parsemoldb.php`, the variable `$db` contains an array
of <span class="classname">AminoAcid</span> objects, and the output of
the script confirms that:

    ** Database of AminoAcid objects:
    Array
    (
        [0] => aminoacid Object
            (
                [name] => Alanine
                [symbol] => ala
                [code] => A
                [type] => hydrophobic
            )

        [1] => aminoacid Object
            (
                [name] => Lysine
                [symbol] => lys
                [code] => K
                [type] => charged
            )

    )

xml\_parse
==========

Start parsing an XML document

### Description

<span class="type">int</span> <span class="methodname">xml\_parse</span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$is_final`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="function">xml\_parse</span> parses an XML document. The
handlers for the configured events are called as many times as
necessary.

### Parameters

`parser`  
A reference to the XML parser to use.

`data`  
Chunk of data to parse. A document may be parsed piece-wise by calling
<span class="function">xml\_parse</span> several times with new data, as
long as the `is_final` parameter is set and **`TRUE`** when the last
data is parsed.

`is_final`  
If set and **`TRUE`**, `data` is the last piece of data sent in this
parse.

### Return Values

Returns 1 on success or 0 on failure.

For unsuccessful parses, error information can be retrieved with <span
class="function">xml\_get\_error\_code</span>, <span
class="function">xml\_error\_string</span>, <span
class="function">xml\_get\_current\_line\_number</span>, <span
class="function">xml\_get\_current\_column\_number</span> and <span
class="function">xml\_get\_current\_byte\_index</span>.

> **Note**:
>
> Some errors (such as entity errors) are reported at the end of the
> data, thus only if `is_final` is set and **`TRUE`**.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Chunked parsing of large XML documents**

This example shows how large XML documents can be read and parsed in
chunks, so that it not necessary to keep the whole document in memory.
Error handling is omitted for brevity.

``` php
<?php
$stream = fopen('large.xml', 'r');
$parser = xml_parser_create();
// set up the handlers here
while (($data = fread($stream, 16384))) {
    xml_parse($parser, $data); // parse the current chunk
}
xml_parse($parser, '', true); // finalize parsing
xml_parser_free($parser);
fclose($stream);
```

xml\_parser\_create\_ns
=======================

Create an XML parser with namespace support

### Description

<span class="type">XMLParser</span> <span
class="methodname">xml\_parser\_create\_ns</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`NULL`**</span></span> \[,
<span class="methodparam"><span class="type">string</span>
`$separator`<span class="initializer"> = ":"</span></span> \]\] )

<span class="function">xml\_parser\_create\_ns</span> creates a new XML
parser with XML namespace support and returns a <span
class="classname">XMLParser</span> instance to be used by the other XML
functions.

### Parameters

`encoding`  
The input encoding is automatically detected, so that the `encoding`
parameter specifies only the output encoding. In PHP 5.0.0 and 5.0.1,
the default output charset is ISO-8859-1, while in PHP 5.0.2 and upper
is UTF-8. The supported encodings are *ISO-8859-1*, *UTF-8* and
*US-ASCII*.

`separator`  
With a namespace aware parser tag parameters passed to the various
handler functions will consist of namespace and tag name separated by
the string specified in `separator`.

### Return Values

Returns a new <span class="classname">XMLParser</span> instance.

### Changelog

| Version | Description                                                                                                                                                               |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function returns an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was returned, or **`FALSE`** on failure. |
| 8.0.0   | `encoding` is nullable now.                                                                                                                                               |

### See Also

-   <span class="function">xml\_parser\_create</span>
-   <span class="function">xml\_parser\_free</span>

xml\_parser\_create
===================

Create an XML parser

### Description

<span class="type">XMLParser</span> <span
class="methodname">xml\_parser\_create</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$encoding`<span class="initializer"> = **`NULL`**</span></span> \] )

<span class="function">xml\_parser\_create</span> creates a new XML
parser and returns a <span class="classname">XMLParser</span> instance
to be used by the other XML functions.

### Parameters

`encoding`  
The optional `encoding` specifies the character encoding for the
input/output in PHP 4. Starting from PHP 5, the input encoding is
automatically detected, so that the `encoding` parameter specifies only
the output encoding. In PHP 4, the default output encoding is the same
as the input charset. If empty string is passed, the parser attempts to
identify which encoding the document is encoded in by looking at the
heading 3 or 4 bytes. In PHP 5.0.0 and 5.0.1, the default output charset
is ISO-8859-1, while in PHP 5.0.2 and upper is UTF-8. The supported
encodings are *ISO-8859-1*, *UTF-8* and *US-ASCII*.

### Return Values

Returns a new <span class="classname">XMLParser</span> instance.

### Changelog

| Version | Description                                                                                                                                                               |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | This function returns an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was returned, or **`FALSE`** on failure. |
| 8.0.0   | `encoding` is nullable now.                                                                                                                                               |

### See Also

-   <span class="function">xml\_parser\_create\_ns</span>
-   <span class="function">xml\_parser\_free</span>

xml\_parser\_free
=================

Free an XML parser

### Description

<span class="type">bool</span> <span
class="methodname">xml\_parser\_free</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
)

Frees the given XML `parser`.

**Caution**

In addition to calling <span class="function">xml\_parser\_free</span>
when the parsing is finished, prior to PHP 8.0.0, it was necessary to
also explicitly unset the reference to `parser` to avoid memory leaks,
if the parser resource is referenced from an object, and this object
references that parser resource.

### Parameters

`parser`  
<span class="simpara"> A reference to the XML parser to free. </span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

xml\_parser\_get\_option
========================

Get options from an XML parser

### Description

<span class="type"><span class="type">string</span><span
class="type">int</span></span> <span
class="methodname">xml\_parser\_get\_option</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">int</span>
`$option`</span> )

Gets an option value from an XML parser.

### Parameters

`parser`  
<span class="simpara"> A reference to the XML parser to get an option
from. </span>

`option`  
<span class="simpara"> Which option to fetch.
**`XML_OPTION_CASE_FOLDING`**, **`XML_OPTION_SKIP_TAGSTART`**,
**`XML_OPTION_SKIP_WHITE`** and **`XML_OPTION_TARGET_ENCODING`** are
available. See <span class="function">xml\_parser\_set\_option</span>
for their description. </span>

### Return Values

This function returns **`FALSE`** if `parser` does not refer to a valid
parser or if `option` isn't valid (generates also a **`E_WARNING`**).
Else the option's value is returned.

### Changelog

| Version               | Description                                                                                                                               |
|-----------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0                 | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |
| 7.1.24, 7.2.12, 7.3.0 | `options` now supports **`XML_OPTION_SKIP_TAGSTART`** and **`XML_OPTION_SKIP_WHITE`**.                                                    |

xml\_parser\_set\_option
========================

Set options in an XML parser

### Description

<span class="type">bool</span> <span
class="methodname">xml\_parser\_set\_option</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">int</span>
`$option`</span> , <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">int</span></span>
`$value`</span> )

Sets an option in an XML parser.

### Parameters

`parser`  
A reference to the XML parser to set an option in.

`option`  
Which option to set. See below.

The following options are available:

| Option constant                  | Data type | Description                                                                                                                                                                                                                                                                                 |
|----------------------------------|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **`XML_OPTION_CASE_FOLDING`**    | integer   | Controls whether <a href="/xml/case-folding.html" class="link">case-folding</a> is enabled for this XML parser. Enabled by default.                                                                                                                                                         |
| **`XML_OPTION_SKIP_TAGSTART`**   | integer   | Specify how many characters should be skipped in the beginning of a tag name.                                                                                                                                                                                                               |
| **`XML_OPTION_SKIP_WHITE`**      | integer   | Whether to skip values consisting of whitespace characters.                                                                                                                                                                                                                                 |
| **`XML_OPTION_TARGET_ENCODING`** | string    | Sets which <a href="/xml/encoding.html" class="link">target encoding</a> to use in this XML parser.By default, it is set to the same as the source encoding used by <span class="function">xml\_parser\_create</span>. Supported target encodings are *ISO-8859-1*, *US-ASCII* and *UTF-8*. |

`value`  
The option's new value.

### Return Values

This function returns **`FALSE`** if `parser` does not refer to a valid
parser, or if the option could not be set. Else the option is set and
**`TRUE`** is returned.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

xml\_set\_character\_data\_handler
==================================

Set up character data handler

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_character\_data\_handler</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">callable</span>
`$handler`</span> )

Sets the character data handler function for the XML parser `parser`.

### Parameters

`parser`  
A reference to the XML parser to set up character data handler function.

`handler`  
`handler` is a string containing the name of a function that must exist
when <span class="function">xml\_parse</span> is called for `parser`.

The function named by `handler` must accept two parameters:

<span class="methodname"><span class="replaceable">handler</span></span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`data`  
<span class="simpara"> The second parameter, `data`, contains the
character data as a string. </span>

Character data handler is called for every piece of a text in the XML
document. It can be called multiple times inside each fragment (e.g. for
non-ASCII strings).

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

xml\_set\_default\_handler
==========================

Set up default handler

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_default\_handler</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">callable</span>
`$handler`</span> )

Sets the default handler function for the XML parser `parser`.

### Parameters

`parser`  
A reference to the XML parser to set up default handler function.

`handler`  
`handler` is a string containing the name of a function that must exist
when <span class="function">xml\_parse</span> is called for `parser`.

The function named by `handler` must accept two parameters:

<span class="methodname"><span class="replaceable">handler</span></span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`data`  
<span class="simpara"> The second parameter, `data`, contains the
character data.This may be the XML declaration, document type
declaration, entities or other data for which no other handler exists.
</span>

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

xml\_set\_element\_handler
==========================

Set up start and end element handlers

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_element\_handler</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">callable</span>
`$start_handler`</span> , <span class="methodparam"><span
class="type">callable</span> `$end_handler`</span> )

Sets the element handler functions for the XML `parser`. `start_handler`
and `end_handler` are strings containing the names of functions that
must exist when <span class="function">xml\_parse</span> is called for
`parser`.

### Parameters

`parser`  
A reference to the XML parser to set up start and end element handler
functions.

`start_handler`  
The function named by `start_handler` must accept three parameters:

<span class="methodname"><span
class="replaceable">start\_element\_handler</span></span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">array</span> `$attribs`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`name`  
<span class="simpara"> The second parameter, `name`, contains the name
of the element for which this handler is called.If
<a href="/xml/case-folding.html" class="link">case-folding</a> is in
effect for this parser, the element name will be in uppercase letters.
</span>

`attribs`  
<span class="simpara"> The third parameter, `attribs`, contains an
associative array with the element's attributes (if any).The keys of
this array are the attribute names, the values are the attribute
values.Attribute names are
<a href="/xml/case-folding.html" class="link">case-folded</a> on the
same criteria as element names.Attribute values are *not* case-folded.
</span> <span class="simpara"> The original order of the attributes can
be retrieved by walking through `attribs` the normal way, using <span
class="function">each</span>.The first key in the array was the first
attribute, and so on. </span>

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

`end_handler`  
The function named by `end_handler` must accept two parameters:

<span class="methodname"><span
class="replaceable">end\_element\_handler</span></span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`name`  
<span class="simpara"> The second parameter, `name`, contains the name
of the element for which this handler is called.If
<a href="/xml/case-folding.html" class="link">case-folding</a> is in
effect for this parser, the element name will be in uppercase letters.
</span>

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

xml\_set\_end\_namespace\_decl\_handler
=======================================

Set up end namespace declaration handler

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_end\_namespace\_decl\_handler</span> (
<span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">callable</span> `$handler`</span> )

Set a handler to be called when leaving the scope of a namespace
declaration. This will be called, for each namespace declaration, after
the handler for the end tag of the element in which the namespace was
declared.

**Caution**

This event is not supported under libXML, so a registered handler
wouldn't be called.

### Parameters

`parser`  
A reference to the XML parser.

`handler`  
`handler` is a string containing the name of a function that must exist
when <span class="function">xml\_parse</span> is called for `parser`.

The function named by `handler` must accept two parameters, and should
return an integer value. If the value returned from the handler is
**`FALSE`** (which it will be if no value is returned), the XML parser
will stop parsing and <span
class="function">xml\_get\_error\_code</span> will return
**`XML_ERROR_EXTERNAL_ENTITY_HANDLING`**.

<span class="methodname"><span class="replaceable">handler</span></span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$prefix`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`prefix`  
<span class="simpara"> The prefix is a string used to reference the
namespace within an XML object. </span>

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span
    class="function">xml\_set\_start\_namespace\_decl\_handler</span>

xml\_set\_external\_entity\_ref\_handler
========================================

Set up external entity reference handler

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_external\_entity\_ref\_handler</span> (
<span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">callable</span> `$handler`</span> )

Sets the external entity reference handler function for the XML parser
`parser`.

### Parameters

`parser`  
A reference to the XML parser to set up external entity reference
handler function.

`handler`  
`handler` is a string containing the name of a function that must exist
when <span class="function">xml\_parse</span> is called for `parser`.

The function named by `handler` must accept five parameters, and should
return an integer value.If the value returned from the handler is
**`FALSE`** (which it will be if no value is returned), the XML parser
will stop parsing and <span
class="function">xml\_get\_error\_code</span> will return
**`XML_ERROR_EXTERNAL_ENTITY_HANDLING`**.

<span class="methodname"><span class="replaceable">handler</span></span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$open_entity_names`</span> , <span
class="methodparam"><span class="type">string</span> `$base`</span> ,
<span class="methodparam"><span class="type">string</span>
`$system_id`</span> , <span class="methodparam"><span
class="type">string</span> `$public_id`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`open_entity_names`  
<span class="simpara"> The second parameter, `open_entity_names`, is a
space-separated list of the names of the entities that are open for the
parse of this entity (including the name of the referenced entity).
</span>

`base`  
<span class="simpara"> This is the base for resolving the system
identifier (`system_id`) of the external entity.Currently this parameter
will always be set to an empty string. </span>

`system_id`  
<span class="simpara"> The fourth parameter, `system_id`, is the system
identifier as specified in the entity declaration. </span>

`public_id`  
<span class="simpara"> The fifth parameter, `public_id`, is the public
identifier as specified in the entity declaration, or an empty string if
none was specified; the whitespace in the public identifier will have
been normalized as required by the XML spec. </span>

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                                                     |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected.                                       |
| 7.3.0   | The return value of the `handler` is no longer ignored if the extension has been built against libxml. Formerly, the return value has been ignored, and parsing did never stop. |

xml\_set\_notation\_decl\_handler
=================================

Set up notation declaration handler

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_notation\_decl\_handler</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">callable</span>
`$handler`</span> )

Sets the notation declaration handler function for the XML parser
`parser`.

A notation declaration is part of the document's DTD and has the
following format:

``` xml
<!NOTATION <parameter>name</parameter>
{ <parameter>systemId</parameter> | <parameter>publicId</parameter>?>
```

See
<a href="http://www.w3.org/TR/1998/REC-xml-19980210#Notations" class="link external">» section 4.7 of the XML 1.0 spec</a>
for the definition of notation declarations.

### Parameters

`parser`  
A reference to the XML parser to set up notation declaration handler
function.

`handler`  
`handler` is a string containing the name of a function that must exist
when <span class="function">xml\_parse</span> is called for `parser`.

The function named by `handler` must accept five parameters:

<span class="methodname"><span class="replaceable">handler</span></span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$notation_name`</span> , <span
class="methodparam"><span class="type">string</span> `$base`</span> ,
<span class="methodparam"><span class="type">string</span>
`$system_id`</span> , <span class="methodparam"><span
class="type">string</span> `$public_id`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`notation_name`  
<span class="simpara"> This is the notation's `name`, as per the
notation format described above. </span>

`base`  
<span class="simpara"> This is the base for resolving the system
identifier (`system_id`) of the notation declaration. Currently this
parameter will always be set to an empty string. </span>

`system_id`  
<span class="simpara"> System identifier of the external notation
declaration. </span>

`public_id`  
<span class="simpara"> Public identifier of the external notation
declaration. </span>

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

xml\_set\_object
================

Use XML Parser within an object

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_object</span> ( <span
class="methodparam"><span class="type">XMLParser</span> `$parser`</span>
, <span class="methodparam"><span class="type">object</span>
`$object`</span> )

This function allows to use `parser` inside `object`. All callback
functions could be set with <span
class="function">xml\_set\_element\_handler</span> etc and assumed to be
methods of `object`.

### Parameters

`parser`  
A reference to the XML parser to use inside the object.

`object`  
The object where to use the XML parser.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 <span class="function">xml\_set\_object</span> example**

``` php
<?php
class XMLParser
{
    private $parser;

    function __construct() 
    {
        $this->parser = xml_parser_create();

        xml_set_object($this->parser, $this);
        xml_set_element_handler($this->parser, "tag_open", "tag_close");
        xml_set_character_data_handler($this->parser, "cdata");
    }

    function __destruct()
    {
        xml_parser_free($this->parser);
        unset($this->parser);
    }

    function parse($data) 
    {
        xml_parse($this->parser, $data);
    }

    function tag_open($parser, $tag, $attributes) 
    {
        var_dump($tag, $attributes); 
    }

    function cdata($parser, $cdata) 
    {
        var_dump($cdata);
    }

    function tag_close($parser, $tag) 
    {
        var_dump($tag);
    }
}

$xml_parser = new XMLParser();
$xml_parser->parse("<A ID='hallo'>PHP</A>");
?>
```

The above example will output:

    string(1) "A"
    array(1) {
      ["ID"]=>
      string(5) "hallo"
    }
    string(3) "PHP"
    string(1) "A"

xml\_set\_processing\_instruction\_handler
==========================================

Set up processing instruction (PI) handler

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_processing\_instruction\_handler</span> (
<span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">callable</span> `$handler`</span> )

Sets the processing instruction (PI) handler function for the XML parser
`parser`.

A processing instruction has the following format:

    <?

<span class="replaceable">target</span> <span
class="replaceable">data</span>

    ?>
        

You can put PHP code into such a tag, but be aware of one limitation: in
an XML PI, the PI end tag (*?\>*) can not be quoted, so this character
sequence should not appear in the PHP code you embed with PIs in XML
documents.If it does, the rest of the PHP code, as well as the "real" PI
end tag, will be treated as character data.

### Parameters

`parser`  
A reference to the XML parser to set up processing instruction (PI)
handler function.

`handler`  
`handler` is a string containing the name of a function that must exist
when <span class="function">xml\_parse</span> is called for `parser`.

The function named by `handler` must accept three parameters:

<span class="methodname"><span class="replaceable">handler</span></span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$target`</span> , <span
class="methodparam"><span class="type">string</span> `$data`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`target`  
<span class="simpara"> The second parameter, `target`, contains the PI
target. </span>

`data`  
<span class="simpara"> The third parameter, `data`, contains the PI
data. </span>

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

xml\_set\_start\_namespace\_decl\_handler
=========================================

Set up start namespace declaration handler

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_start\_namespace\_decl\_handler</span> (
<span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">callable</span> `$handler`</span> )

Set a handler to be called when a namespace is declared. Namespace
declarations occur inside start tags. But the namespace declaration
start handler is called before the start tag handler for each namespace
declared in that start tag.

### Parameters

`parser`  
A reference to the XML parser.

`handler`  
`handler` is a string containing the name of a function that must exist
when <span class="function">xml\_parse</span> is called for `parser`.

The function named by `handler` must accept three parameters, and should
return an integer value. If the value returned from the handler is
**`FALSE`** (which it will be if no value is returned), the XML parser
will stop parsing and <span
class="function">xml\_get\_error\_code</span> will return
**`XML_ERROR_EXTERNAL_ENTITY_HANDLING`**.

<span class="methodname"><span class="replaceable">handler</span></span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$prefix`</span> , <span
class="methodparam"><span class="type">string</span> `$uri`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`prefix`  
<span class="simpara"> The prefix is a string used to reference the
namespace within an XML object. </span>

`uri`  
<span class="simpara"> Uniform Resource Identifier (URI) of namespace.
</span>

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

### See Also

-   <span
    class="function">xml\_set\_end\_namespace\_decl\_handler</span>

xml\_set\_unparsed\_entity\_decl\_handler
=========================================

Set up unparsed entity declaration handler

### Description

<span class="type">bool</span> <span
class="methodname">xml\_set\_unparsed\_entity\_decl\_handler</span> (
<span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">callable</span> `$handler`</span> )

Sets the unparsed entity declaration handler function for the XML parser
`parser`.

The `handler` will be called if the XML parser encounters an external
entity declaration with an NDATA declaration, like the following:

``` xml
<!ENTITY <parameter>name</parameter> {<parameter>publicId</parameter> | <parameter>systemId</parameter>}
        NDATA <parameter>notationName</parameter>
```

See
<a href="http://www.w3.org/TR/1998/REC-xml-19980210#sec-external-ent" class="link external">» section 4.2.2 of the XML 1.0 spec</a>
for the definition of notation declared external entities.

### Parameters

`parser`  
A reference to the XML parser to set up unparsed entity declaration
handler function.

`handler`  
`handler` is a string containing the name of a function that must exist
when <span class="function">xml\_parse</span> is called for `parser`.

The function named by `handler` must accept six parameters:

<span class="methodname"><span class="replaceable">handler</span></span>
( <span class="methodparam"><span class="type">XMLParser</span>
`$parser`</span> , <span class="methodparam"><span
class="type">string</span> `$entity_name`</span> , <span
class="methodparam"><span class="type">string</span> `$base`</span> ,
<span class="methodparam"><span class="type">string</span>
`$system_id`</span> , <span class="methodparam"><span
class="type">string</span> `$public_id`</span> , <span
class="methodparam"><span class="type">string</span>
`$notation_name`</span> )

`parser`  
<span class="simpara"> The first parameter, <span
class="replaceable">parser</span>, is a reference to the XML parser
calling the handler. </span>

`entity_name`  
<span class="simpara"> The name of the entity that is about to be
defined. </span>

`base`  
<span class="simpara"> This is the base for resolving the system
identifier (`systemId`) of the external entity.Currently this parameter
will always be set to an empty string. </span>

`system_id`  
<span class="simpara"> System identifier for the external entity.
</span>

`public_id`  
<span class="simpara"> Public identifier for the external entity.
</span>

`notation_name`  
<span class="simpara"> Name of the notation of this entity (see <span
class="function">xml\_set\_notation\_decl\_handler</span>). </span>

If a handler function is set to an empty string, or **`FALSE`**, the
handler in question is disabled.

> **Note**: <span class="simpara">Instead of a function name, an array
> containing an object reference and a method name can also be
> supplied.</span>

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `parser` expects an <span class="classname">XMLParser</span> instance now; previously, a <span class="type">resource</span> was expected. |

**Table of Contents**

-   [utf8\_decode](/ref/xml.html#utf8_decode) — Converts a string with
    ISO-8859-1 characters encoded with UTF-8 to single-byte ISO-8859-1
-   [utf8\_encode](/ref/xml.html#utf8_encode) — Encodes an ISO-8859-1
    string to UTF-8
-   [xml\_error\_string](/ref/xml.html#xml_error_string) — Get XML
    parser error string
-   [xml\_get\_current\_byte\_index](/ref/xml.html#xml_get_current_byte_index)
    — Get current byte index for an XML parser
-   [xml\_get\_current\_column\_number](/ref/xml.html#xml_get_current_column_number)
    — Get current column number for an XML parser
-   [xml\_get\_current\_line\_number](/ref/xml.html#xml_get_current_line_number)
    — Get current line number for an XML parser
-   [xml\_get\_error\_code](/ref/xml.html#xml_get_error_code) — Get XML
    parser error code
-   [xml\_parse\_into\_struct](/ref/xml.html#xml_parse_into_struct) —
    Parse XML data into an array structure
-   [xml\_parse](/ref/xml.html#xml_parse) — Start parsing an XML
    document
-   [xml\_parser\_create\_ns](/ref/xml.html#xml_parser_create_ns) —
    Create an XML parser with namespace support
-   [xml\_parser\_create](/ref/xml.html#xml_parser_create) — Create an
    XML parser
-   [xml\_parser\_free](/ref/xml.html#xml_parser_free) — Free an XML
    parser
-   [xml\_parser\_get\_option](/ref/xml.html#xml_parser_get_option) —
    Get options from an XML parser
-   [xml\_parser\_set\_option](/ref/xml.html#xml_parser_set_option) —
    Set options in an XML parser
-   [xml\_set\_character\_data\_handler](/ref/xml.html#xml_set_character_data_handler)
    — Set up character data handler
-   [xml\_set\_default\_handler](/ref/xml.html#xml_set_default_handler)
    — Set up default handler
-   [xml\_set\_element\_handler](/ref/xml.html#xml_set_element_handler)
    — Set up start and end element handlers
-   [xml\_set\_end\_namespace\_decl\_handler](/ref/xml.html#xml_set_end_namespace_decl_handler)
    — Set up end namespace declaration handler
-   [xml\_set\_external\_entity\_ref\_handler](/ref/xml.html#xml_set_external_entity_ref_handler)
    — Set up external entity reference handler
-   [xml\_set\_notation\_decl\_handler](/ref/xml.html#xml_set_notation_decl_handler)
    — Set up notation declaration handler
-   [xml\_set\_object](/ref/xml.html#xml_set_object) — Use XML Parser
    within an object
-   [xml\_set\_processing\_instruction\_handler](/ref/xml.html#xml_set_processing_instruction_handler)
    — Set up processing instruction (PI) handler
-   [xml\_set\_start\_namespace\_decl\_handler](/ref/xml.html#xml_set_start_namespace_decl_handler)
    — Set up start namespace declaration handler
-   [xml\_set\_unparsed\_entity\_decl\_handler](/ref/xml.html#xml_set_unparsed_entity_decl_handler)
    — Set up unparsed entity declaration handler

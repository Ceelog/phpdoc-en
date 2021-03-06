Tidy
====

**Table of Contents**

-   [Introduction](/intro/tidy.html)
-   [Installing/Configuring](/tidy/setup.html)
    -   [Requirements](/tidy/setup.html#Requirements)
    -   [Installation](/tidy/setup.html#Installation)
    -   [Runtime
        Configuration](/tidy/setup.html#Runtime%20Configuration)
    -   [Resource Types](/tidy/setup.html#Resource%20Types)
-   [Predefined Constants](/tidy/constants.html)
-   [Examples](/tidy/examples.html)
    -   [Tidy example](/tidy/examples.html#Tidy%20example)
-   [tidy](/class/tidy.html) — The tidy class
    -   [tidy::body](/class/tidy.html#tidy::body) — Returns a tidyNode
        object starting from the \<body\> tag of the tidy parse tree
    -   [tidy::cleanRepair](/class/tidy.html#tidy::cleanRepair) —
        Execute configured cleanup and repair operations on parsed
        markup
    -   [tidy::\_\_construct](/class/tidy.html#tidy::__construct) —
        Constructs a new tidy object
    -   [tidy::diagnose](/class/tidy.html#tidy::diagnose) — Run
        configured diagnostics on parsed and repaired markup
    -   [tidy::$errorBuffer](/class/tidy.html#tidy::$errorBuffer) —
        Return warnings and errors which occurred parsing the specified
        document
    -   [tidy::getConfig](/class/tidy.html#tidy::getConfig) — Get
        current Tidy configuration
    -   [tidy::getHtmlVer](/class/tidy.html#tidy::getHtmlVer) — Get the
        Detected HTML version for the specified document
    -   [tidy::getOpt](/class/tidy.html#tidy::getOpt) — Returns the
        value of the specified configuration option for the tidy
        document
    -   [tidy::getOptDoc](/class/tidy.html#tidy::getOptDoc) — Returns
        the documentation for the given option name
    -   [tidy::getRelease](/class/tidy.html#tidy::getRelease) — Get
        release date (version) for Tidy library
    -   [tidy::getStatus](/class/tidy.html#tidy::getStatus) — Get status
        of specified document
    -   [tidy::head](/class/tidy.html#tidy::head) — Returns a tidyNode
        object starting from the \<head\> tag of the tidy parse tree
    -   [tidy::html](/class/tidy.html#tidy::html) — Returns a tidyNode
        object starting from the \<html\> tag of the tidy parse tree
    -   [tidy::isXhtml](/class/tidy.html#tidy::isXhtml) — Indicates if
        the document is a XHTML document
    -   [tidy::isXml](/class/tidy.html#tidy::isXml) — Indicates if the
        document is a generic (non HTML/XHTML) XML document
    -   [tidy::parseFile](/class/tidy.html#tidy::parseFile) — Parse
        markup in file or URI
    -   [tidy::parseString](/class/tidy.html#tidy::parseString) — Parse
        a document stored in a string
    -   [tidy::repairFile](/class/tidy.html#tidy::repairFile) — Repair a
        file and return it as a string
    -   [tidy::repairString](/class/tidy.html#tidy::repairString) —
        Repair a string using an optionally provided configuration file
    -   [tidy::root](/class/tidy.html#tidy::root) — Returns a tidyNode
        object representing the root of the tidy parse tree
-   [tidyNode](/class/tidynode.html) — The tidyNode class
    -   [tidyNode::\_\_construct](/class/tidynode.html#tidyNode::__construct)
        — Private constructor to disallow direct instantiation
    -   [tidyNode::getParent](/class/tidynode.html#tidyNode::getParent)
        — Returns the parent node of the current node
    -   [tidyNode::hasChildren](/class/tidynode.html#tidyNode::hasChildren)
        — Checks if a node has children
    -   [tidyNode::hasSiblings](/class/tidynode.html#tidyNode::hasSiblings)
        — Checks if a node has siblings
    -   [tidyNode::isAsp](/class/tidynode.html#tidyNode::isAsp) — Checks
        if this node is ASP
    -   [tidyNode::isComment](/class/tidynode.html#tidyNode::isComment)
        — Checks if a node represents a comment
    -   [tidyNode::isHtml](/class/tidynode.html#tidyNode::isHtml) —
        Checks if a node is an element node
    -   [tidyNode::isJste](/class/tidynode.html#tidyNode::isJste) —
        Checks if this node is JSTE
    -   [tidyNode::isPhp](/class/tidynode.html#tidyNode::isPhp) — Checks
        if a node is PHP
    -   [tidyNode::isText](/class/tidynode.html#tidyNode::isText) —
        Checks if a node represents text (no markup)
-   [Tidy Functions](/ref/tidy.html)
    -   [ob\_tidyhandler](/ref/tidy.html#ob_tidyhandler) — ob\_start
        callback function to repair the buffer
    -   [tidy\_access\_count](/ref/tidy.html#tidy_access_count) —
        Returns the Number of Tidy accessibility warnings encountered
        for specified document
    -   [tidy\_config\_count](/ref/tidy.html#tidy_config_count) —
        Returns the Number of Tidy configuration errors encountered for
        specified document
    -   [tidy\_error\_count](/ref/tidy.html#tidy_error_count) — Returns
        the Number of Tidy errors encountered for specified document
    -   [tidy\_get\_output](/ref/tidy.html#tidy_get_output) — Return a
        string representing the parsed tidy markup
    -   [tidy\_warning\_count](/ref/tidy.html#tidy_warning_count) —
        Returns the Number of Tidy warnings encountered for specified
        document

Introduction
------------

An HTML node in an HTML file, as detected by tidy.

Class synopsis
--------------

**tidy**

<span class="ooclass"> class **tidy** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span
class="type">string</span>`$tidy->errorBuffer`;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$filename`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$useIncludePath`<span class="initializer"> =
**`false`**</span></span> \]\]\]\] )

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">body</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">cleanRepair</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">diagnose</span> ( <span
class="methodparam">void</span> )

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">tidy\_get\_error\_buffer</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">getConfig</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getHtmlVer</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">int</span><span
class="type">bool</span></span> <span class="methodname">getOpt</span> (
<span class="methodparam"><span class="type">string</span>
`$option`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getOptDoc</span> ( <span class="methodparam"><span
class="type">string</span> `$option`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getRelease</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getStatus</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">head</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">html</span> ( <span class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isXhtml</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isXml</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">parseFile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$useIncludePath`<span class="initializer"> =
**`false`**</span></span> \]\]\] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">parseString</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">repairFile</span> ( <span class="methodparam"><span
class="type">string</span> `$filename`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$useIncludePath`<span class="initializer"> =
**`false`**</span></span> \]\]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">repairString</span> ( <span class="methodparam"><span
class="type">string</span> `$string`</span> \[, <span
class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">root</span> ( <span class="methodparam">void</span> )

}

tidy::body
==========

tidy\_get\_body
===============

Returns a <span class="classname">tidyNode</span> object starting from
the \<body\> tag of the tidy parse tree

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">tidy::body</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type"><span class="type">tidyNode</span><span
class="type">null</span></span> <span
class="methodname">tidy\_get\_body</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Returns a <span class="classname">tidyNode</span> object starting from
the \<body\> tag of the tidy parse tree.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns a <span class="classname">tidyNode</span> object starting from
the \<body\> tag of the tidy parse tree.

### Examples

**Example \#1 <span class="function">tidy::getBody</span> example**

``` php
<?php
$html = '
<html>
  <head>
    <title>test</title>
  </head>
  <body>
    <p>paragraph</p>
  </body>
</html>';

$tidy = tidy_parse_string($html);

$body = $tidy->Body();
echo $body->value;
?>
```

The above example will output:

    <body>
    <p>paragraph</p>
    </body>

### See Also

-   <span class="function">tidy::head</span>
-   <span class="function">tidy::html</span>

tidy::cleanRepair
=================

tidy\_clean\_repair
===================

Execute configured cleanup and repair operations on parsed markup

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidy::cleanRepair</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">bool</span> <span
class="methodname">tidy\_clean\_repair</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

This function cleans and repairs the given tidy `tidy`.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">tidy::cleanrepair</span> example**

``` php
<?php
$html = '<p>test</I>';

$tidy = tidy_parse_string($html);
$tidy->cleanRepair();

echo $tidy;
?>
```

The above example will output:

    <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 3.2//EN">
    <html>
    <head>
    <title></title>
    </head>
    <body>
    <p>test</p>
    </body>
    </html>

### See Also

-   <span class="function">tidy::repairFile</span>
-   <span class="function">tidy::repairString</span>

tidy::\_\_construct
===================

Constructs a new <span class="classname">tidy</span> object

### Description

<span class="modifier">public</span> <span
class="methodname">tidy::\_\_construct</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$filename`<span class="initializer"> = **`null`**</span></span> \[,
<span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$useIncludePath`<span class="initializer"> =
**`false`**</span></span> \]\]\]\] )

Constructs a new <span class="classname">tidy</span> object.

### Parameters

`filename`  
If the `filename` parameter is given, this function will also read that
file and initialize the object with the file, acting like <span
class="function">tidy\_parse\_file</span>.

`config`  
The config `config` can be passed either as an array or as a string. If
a string is passed, it is interpreted as the name of the configuration
file, otherwise, it is interpreted as the options themselves.

For an explanation about each option, visit
<a href="http://api.html-tidy.org/#quick-reference" class="link external">» http://api.html-tidy.org/#quick-reference</a>.

`encoding`  
The `encoding` parameter sets the encoding for input/output documents.
The possible values for encoding are: *ascii*, *latin0*, *latin1*,
*raw*, *utf8*, *iso2022*, *mac*, *win1252*, *ibm858*, *utf16*,
*utf16le*, *utf16be*, *big5*, and *shiftjis*.

`useIncludePath`  
Search for the file in the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>.

### Return Values

Returns the new <span class="classname">tidy</span> instance.

### Changelog

| Version | Description                                                             |
|---------|-------------------------------------------------------------------------|
| 8.0.0   | `filename`, `config`, `encoding` and `useIncludePath` are nullable now. |

### Examples

**Example \#1 <span class="function">tidy::\_\_construct</span>
example**

``` php
<?php

$html = <<< HTML

<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
<head><title>title</title></head>
<body>
<p>paragraph <bt />
text</p>
</body></html>

HTML;

$tidy = new tidy();
$tidy->ParseString($html);

$tidy->cleanRepair();

if ($tidy->errorBuffer) {
    echo "The following errors were detected:\n";
    echo $tidy->errorBuffer;
}

?>
```

The above example will output:

    The following errors were detected:
    line 8 column 14 - Error: <bt> is not recognized!
    line 8 column 14 - Warning: discarding unexpected <bt>

### See Also

-   <span class="function">tidy::parseFile</span>
-   <span class="function">tidy::parseString</span>

tidy::diagnose
==============

tidy\_diagnose
==============

Run configured diagnostics on parsed and repaired markup

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidy::diagnose</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">bool</span> <span
class="methodname">tidy\_diagnose</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Runs diagnostic tests on the given tidy `tidy`, adding some more
information about the document in the error buffer.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 <span class="function">tidy::diagnose</span> example**

``` php
<?php

$html = <<< HTML
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
"http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<p>paragraph</p>
HTML;

$tidy = tidy_parse_string($html);
$tidy->cleanRepair();

// note the difference between the two outputs
echo $tidy->errorBuffer . "\n";

$tidy->diagnose();
echo $tidy->errorBuffer;

?>
```

The above example will output:

    line 4 column 1 - Warning: <p> isn't allowed in <head> elements
    line 4 column 1 - Warning: inserting missing 'title' element
    line 4 column 1 - Warning: <p> isn't allowed in <head> elements
    line 4 column 1 - Warning: inserting missing 'title' element
    Info: Doctype given is "-//W3C//DTD XHTML 1.0 Strict//EN"
    Info: Document content looks like XHTML 1.0 Strict
    2 warnings, 0 errors were found!

### See Also

-   <span class="function">tidy::errorBuffer</span>

tidy::$errorBuffer
==================

tidy\_get\_error\_buffer
========================

Return warnings and errors which occurred parsing the specified document

### Description

Object oriented style (property):

<span class="modifier">public</span> <span
class="type">string</span>`$tidy->errorBuffer`;

Procedural style:

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">tidy\_get\_error\_buffer</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Returns warnings and errors which occurred parsing the specified
document.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns the error buffer as a string, or **`false`** if the buffer is
empty.

### Examples

**Example \#1 <span class="function">tidy\_get\_error\_buffer</span>
example**

``` php
<?php
$html = '<p>paragraph</p>';

$tidy = tidy_parse_string($html);

echo tidy_get_error_buffer($tidy);
/* or in OO: */
echo $tidy->errorBuffer;
?>
```

The above example will output:

    line 1 column 1 - Warning: missing <!DOCTYPE> declaration
    line 1 column 1 - Warning: inserting missing 'title' element

### See Also

-   <span class="function">tidy\_access\_count</span>
-   <span class="function">tidy\_error\_count</span>
-   <span class="function">tidy\_warning\_count</span>

tidy::getConfig
===============

tidy\_get\_config
=================

Get current Tidy configuration

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">array</span>
<span class="methodname">tidy::getConfig</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">array</span> <span
class="methodname">tidy\_get\_config</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Gets the list of the configuration options in use by the given tidy
`tidy`.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns an array of configuration options.

For an explanation about each option, visit
<a href="http://api.html-tidy.org/#quick-reference" class="link external">» http://api.html-tidy.org/#quick-reference</a>.

### Examples

**Example \#1 <span class="function">tidy::getConfig</span> example**

``` php
<?php
$html = '<p>test</p>';
$config = array('indent' => TRUE,
                'output-xhtml' => TRUE,
                'wrap' => 200);

$tidy = tidy_parse_string($html, $config);

print_r($tidy->getConfig());
?>
```

The above example will output:

    Array
    (
        [indent-spaces] => 2
        [wrap] => 200
        [tab-size] => 8
        [char-encoding] => 1
        [input-encoding] => 3
        [output-encoding] => 1
        [newline] => 1
        [doctype-mode] => 1
        [doctype] =>
        [repeated-attributes] => 1
        [alt-text] =>
        [slide-style] =>
        [error-file] =>
        [output-file] =>
        [write-back] =>
        [markup] => 1
        [show-warnings] => 1
        [quiet] =>
        [indent] => 1
        [hide-endtags] =>
        [input-xml] =>
        [output-xml] => 1
        [output-xhtml] => 1
        [output-html] =>
        [add-xml-decl] =>
        [uppercase-tags] =>
        [uppercase-attributes] =>
        [bare] =>
        [clean] =>
        [logical-emphasis] =>
        [drop-proprietary-attributes] =>
        [drop-font-tags] =>
        [drop-empty-paras] => 1
        [fix-bad-comments] => 1
        [break-before-br] =>
        [split] =>
        [numeric-entities] =>
        [quote-marks] =>
        [quote-nbsp] => 1
        [quote-ampersand] => 1
        [wrap-attributes] =>
        [wrap-script-literals] =>
        [wrap-sections] => 1
        [wrap-asp] => 1
        [wrap-jste] => 1
        [wrap-php] => 1
        [fix-backslash] => 1
        [indent-attributes] =>
        [assume-xml-procins] =>
        [add-xml-space] =>
        [enclose-text] =>
        [enclose-block-text] =>
        [keep-time] =>
        [word-2000] =>
        [tidy-mark] =>
        [gnu-emacs] =>
        [gnu-emacs-file] =>
        [literal-attributes] =>
        [show-body-only] =>
        [fix-uri] => 1
        [lower-literals] => 1
        [hide-comments] =>
        [indent-cdata] =>
        [force-output] => 1
        [show-errors] => 6
        [ascii-chars] => 1
        [join-classes] =>
        [join-styles] => 1
        [escape-cdata] =>
        [language] =>
        [ncr] => 1
        [output-bom] => 2
        [replace-color] =>
        [css-prefix] =>
        [new-inline-tags] =>
        [new-blocklevel-tags] =>
        [new-empty-tags] =>
        [new-pre-tags] =>
        [accessibility-check] => 0
        [vertical-space] =>
        [punctuation-wrap] =>
        [merge-divs] => 1
    )

### See Also

-   <span class="function">tidy\_reset\_config</span>
-   <span class="function">tidy\_save\_config</span>

tidy::getHtmlVer
================

tidy\_get\_html\_ver
====================

Get the Detected HTML version for the specified document

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">tidy::getHtmlVer</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">int</span> <span
class="methodname">tidy\_get\_html\_ver</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Returns the detected HTML version for the specified tidy `tidy`.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns the detected HTML version.

**Warning**

This function is not yet implemented in the Tidylib itself, so it always
return *0*.

tidy::getOpt
============

tidy\_getopt
============

Returns the value of the specified configuration option for the tidy
document

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">int</span><span
class="type">bool</span></span> <span
class="methodname">tidy::getOpt</span> ( <span class="methodparam"><span
class="type">string</span> `$option`</span> )

Procedural style

<span class="type"><span class="type">string</span><span
class="type">int</span><span class="type">bool</span></span> <span
class="methodname">tidy\_getopt</span> ( <span class="methodparam"><span
class="type">tidy</span> `$tidy`</span> , <span
class="methodparam"><span class="type">string</span> `$option`</span> )

Returns the value of the specified `option` for the specified tidy
`tidy`.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

`option`  
You will find a list with each configuration option and their types at:
<a href="http://api.html-tidy.org/#quick-reference" class="link external">» http://api.html-tidy.org/#quick-reference</a>.

### Return Values

Returns the value of the specified `option`. The return type depends on
the type of the specified one.

### Examples

**Example \#1 <span class="function">tidy\_getopt</span> example**

``` php
<?php

$html ='<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 3.2//EN">
<html><head><title>Title</title></head>
<body>

<p><img src="img.png"></p>

</body></html>';

$config = array('accessibility-check' => 3,
                'alt-text' => 'some text');

$tidy = new tidy();
$tidy->parseString($html, $config);


var_dump($tidy->getOpt('accessibility-check')); //integer
var_dump($tidy->getOpt('lower-literals')); //boolean
var_dump($tidy->getOpt('alt-text')); //string

?>
```

The above example will output:

    int(3)
    bool(true)
    string(9) "some text"

tidy::getOptDoc
===============

tidy\_get\_opt\_doc
===================

Returns the documentation for the given option name

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">tidy::getOptDoc</span> ( <span
class="methodparam"><span class="type">string</span> `$option`</span> )

Procedural style

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">tidy\_get\_opt\_doc</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> ,
<span class="methodparam"><span class="type">string</span>
`$option`</span> )

<span class="function">tidy\_get\_opt\_doc</span> returns the
documentation for the given option name.

> **Note**:
>
> You need at least libtidy from 25 April, 2005 for this function be
> available.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

`option`  
The option name

### Return Values

Returns a string if the option exists and has documentation available,
or **`false`** otherwise.

### Examples

**Example \#1 Print all options along with their documentation and
default value**

``` php
<?php

$tidy = new tidy;
$config = $tidy->getConfig();

ksort($config);

foreach ($config as $opt => $val) {

    if (!$doc = $tidy->getOptDoc($opt))
        $doc = 'no documentation available!';

    $val = ($tidy->getOpt($opt) === true)  ? 'true'  : $val;
    $val = ($tidy->getOpt($opt) === false) ? 'false' : $val;

    echo "<p><b>$opt</b> (default: '$val')<br />".
         "$doc</p><hr />\n";
}

?>
```

### See Also

-   <span class="function">tidy::getconfig</span>
-   <span class="function">tidy::getopt</span>

tidy::getRelease
================

tidy\_get\_release
==================

Get release date (version) for Tidy library

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">tidy::getRelease</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">string</span> <span
class="methodname">tidy\_get\_release</span> ( <span
class="methodparam">void</span> )

Gets the release date of the Tidy library.

### Return Values

Returns a string with the release date of the Tidy library, which may be
`'unknown'`.

tidy::getStatus
===============

tidy\_get\_status
=================

Get status of specified document

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">tidy::getStatus</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">int</span> <span
class="methodname">tidy\_get\_status</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Returns the status for the specified tidy `tidy`.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns 0 if no error/warning was raised, 1 for warnings or
accessibility errors, or 2 for errors.

### Examples

**Example \#1 <span class="function">tidy::getStatus</span> example**

``` php
<?php
$html = '<p>paragraph</i>';
$tidy = new tidy();
$tidy->parseString($html);

$tidy2 = new tidy();
$html2 = '<bogus>test</bogus>';
$tidy2->parseString($html2);

echo $tidy->getStatus(); //1

echo $tidy2->getStatus(); //2
?>
```

tidy::head
==========

tidy\_get\_head
===============

Returns a <span class="classname">tidyNode</span> object starting from
the \<head\> tag of the tidy parse tree

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">tidy::head</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type"><span class="type">tidyNode</span><span
class="type">null</span></span> <span
class="methodname">tidy\_get\_head</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Returns a <span class="classname">tidyNode</span> object starting from
the \<head\> tag of the tidy parse tree.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns the <span class="classname">tidyNode</span> object.

### Examples

**Example \#1 <span class="function">tidy::head</span> example**

``` php
<?php
$html = '
<html>
  <head>
    <title>test</title>
  </head>
  <body>
    <p>paragraph</p>
  </body>
</html>';

$tidy = tidy_parse_string($html);

$head = $tidy->head();
echo $head->value;
?>
```

The above example will output:

    <head>
    <title>test</title>
    </head>

### See Also

-   <span class="function">tidy::body</span>
-   <span class="function">tidy::html</span>

tidy::html
==========

tidy\_get\_html
===============

Returns a <span class="classname">tidyNode</span> object starting from
the \<html\> tag of the tidy parse tree

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">tidy::html</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type"><span class="type">tidyNode</span><span
class="type">null</span></span> <span
class="methodname">tidy\_get\_html</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Returns a <span class="classname">tidyNode</span> object starting from
the \<html\> tag of the tidy parse tree.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns the <span class="classname">tidyNode</span> object.

### Examples

**Example \#1 <span class="function">tidy::html</span> example**

``` php
<?php
$html = '
<html>
  <head>
    <title>test</title>
  </head>
  <body>
    <p>paragraph</p>
  </body>
</html>';

$tidy = tidy_parse_string($html);

$html = $tidy->html();
echo $html->value;
?>
```

The above example will output:

    <html>
    <head>
    <title>test</title>
    </head>
    <body>
    <p>paragraph</p>
    </body>
    </html>

### See Also

-   <span class="function">tidy::body</span>
-   <span class="function">tidy::head</span>

tidy::isXhtml
=============

tidy\_is\_xhtml
===============

Indicates if the document is a XHTML document

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidy::isXhtml</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">bool</span> <span
class="methodname">tidy\_is\_xhtml</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Tells if the document is a XHTML document.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

This function returns **`true`** if the specified tidy `tidy` is a XHTML
document, or **`false`** otherwise.

**Warning**

This function is not yet implemented in the Tidylib itself, so it always
return **`false`**.

tidy::isXml
===========

tidy\_is\_xml
=============

Indicates if the document is a generic (non HTML/XHTML) XML document

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidy::isXml</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">bool</span> <span
class="methodname">tidy\_is\_xml</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Tells if the document is a generic (non HTML/XHTML) XML document.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

This function returns **`true`** if the specified tidy `tidy` is a
generic XML document (non HTML/XHTML), or **`false`** otherwise.

**Warning**

This function is not yet implemented in the Tidylib itself, so it always
return **`false`**.

tidy::parseFile
===============

tidy\_parse\_file
=================

Parse markup in file or URI

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidy::parseFile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$useIncludePath`<span class="initializer"> =
**`false`**</span></span> \]\]\] )

Procedural style

<span class="type"><span class="type">tidy</span><span
class="type">false</span></span> <span
class="methodname">tidy\_parse\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$useIncludePath`<span class="initializer"> =
**`false`**</span></span> \]\]\] )

Parses the given file.

### Parameters

`filename`  
If the `filename` parameter is given, this function will also read that
file and initialize the object with the file, acting like <span
class="function">tidy\_parse\_file</span>.

`config`  
The config `config` can be passed either as an array or as a string. If
a string is passed, it is interpreted as the name of the configuration
file, otherwise, it is interpreted as the options themselves.

For an explanation about each option, see
<a href="http://api.html-tidy.org/#quick-reference" class="link external">» http://api.html-tidy.org/#quick-reference</a>.

`encoding`  
The `encoding` parameter sets the encoding for input/output documents.
The possible values for encoding are: *ascii*, *latin0*, *latin1*,
*raw*, *utf8*, *iso2022*, *mac*, *win1252*, *ibm858*, *utf16*,
*utf16le*, *utf16be*, *big5*, and *shiftjis*.

`useIncludePath`  
Search for the file in the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>.

### Return Values

<span class="methodname">tidy::parseFile</span> returns **`true`** on
success. <span class="function">tidy\_parse\_file</span> returns a new
<span class="classname">tidy</span> instance on success. Both, the
method and the function return **`false`** on failure.

### Changelog

| Version | Description                               |
|---------|-------------------------------------------|
| 8.0.0   | `config` and `encoding` are nullable now. |

### Examples

**Example \#1 <span class="function">tidy::parseFile</span> example**

``` php
<?php
$tidy = new tidy();
$tidy->parseFile('file.html');

$tidy->cleanRepair();

if(!empty($tidy->errorBuffer)) {
    echo "The following errors or warnings occurred:\n";
    echo $tidy->errorBuffer;
}
?>
```

### See Also

-   <span class="function">tidy::parsestring</span>
-   <span class="function">tidy::repairfile</span>
-   <span class="function">tidy::repairstring</span>

tidy::parseString
=================

tidy\_parse\_string
===================

Parse a document stored in a string

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidy::parseString</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \]\] )

Procedural style

<span class="type"><span class="type">tidy</span><span
class="type">false</span></span> <span
class="methodname">tidy\_parse\_string</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \]\] )

Parses a document stored in a string.

### Parameters

`string`  
The data to be parsed.

`config`  
The config `config` can be passed either as an array or as a string. If
a string is passed, it is interpreted as the name of the configuration
file, otherwise, it is interpreted as the options themselves.

For an explanation about each option, visit
<a href="http://api.html-tidy.org/#quick-reference" class="link external">» http://api.html-tidy.org/#quick-reference</a>.

`encoding`  
The `encoding` parameter sets the encoding for input/output documents.
The possible values for encoding are: *ascii*, *latin0*, *latin1*,
*raw*, *utf8*, *iso2022*, *mac*, *win1252*, *ibm858*, *utf16*,
*utf16le*, *utf16be*, *big5*, and *shiftjis*.

### Return Values

<span class="methodname">tidy::parseString</span> returns **`true`** on
success. <span class="function">tidy\_parse\_string</span> returns a new
<span class="classname">tidy</span> instance on success. Both, the
method and the function return **`false`** on failure.

### Changelog

| Version | Description                               |
|---------|-------------------------------------------|
| 8.0.0   | `config` and `encoding` are nullable now. |

### Examples

**Example \#1 <span class="function">tidy::parseString</span> example**

``` php
<?php
ob_start();
?>

<html>
  <head>
   <title>test</title>
  </head>
  <body>
   <p>error<br>another line</i>
  </body>
</html>

<?php

$buffer = ob_get_clean();
$config = array('indent' => TRUE,
                'output-xhtml' => TRUE,
                'wrap' => 200);

$tidy = tidy_parse_string($buffer, $config, 'UTF8');

$tidy->cleanRepair();
echo $tidy;
?>
```

The above example will output:

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
        "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml">
      <head>
        <title>
          test
        </title>
      </head>
      <body>
        <p>
          error<br />
          another line
        </p>
      </body>
    </html>

### See Also

-   <span class="function">tidy::parseFile</span>
-   <span class="function">tidy::repairFile</span>
-   <span class="function">tidy::repairString</span>

tidy::repairFile
================

tidy\_repair\_file
==================

Repair a file and return it as a string

### Description

Object oriented style

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">tidy::repairFile</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$useIncludePath`<span class="initializer"> =
**`false`**</span></span> \]\]\] )

Procedural style

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">tidy\_repair\_file</span> ( <span
class="methodparam"><span class="type">string</span> `$filename`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$useIncludePath`<span class="initializer"> =
**`false`**</span></span> \]\]\] )

Repairs the given file and returns it as a string.

### Parameters

`filename`  
The file to be repaired.

`config`  
The config `config` can be passed either as an array or as a string. If
a string is passed, it is interpreted as the name of the configuration
file, otherwise, it is interpreted as the options themselves.

Check http://tidy.sourceforge.net/docs/quickref.html for an explanation
about each option.

`encoding`  
The `encoding` parameter sets the encoding for input/output documents.
The possible values for encoding are: *ascii*, *latin0*, *latin1*,
*raw*, *utf8*, *iso2022*, *mac*, *win1252*, *ibm858*, *utf16*,
*utf16le*, *utf16be*, *big5*, and *shiftjis*.

`useIncludePath`  
Search for the file in the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>.

### Return Values

Returns the repaired contents as a string, or **`false`** on failure.

### Changelog

| Version | Description                                                              |
|---------|--------------------------------------------------------------------------|
| 8.0.0   | <span class="methodname">tidy::repairFile</span> is a static method now. |
| 8.0.0   | `config` and `encoding` are nullable now.                                |

### Examples

**Example \#1 <span class="function">tidy::repairFile</span> example**

``` php
<?php
$file = 'file.html';

$tidy = new tidy();
$repaired = $tidy->repairfile($file);
rename($file, $file . '.bak');

file_put_contents($file, $repaired);
?>
```

### See Also

-   <span class="function">tidy::parseFile</span>
-   <span class="function">tidy::parseString</span>
-   <span class="function">tidy::repairString</span>

tidy::repairString
==================

tidy\_repair\_string
====================

Repair a string using an optionally provided configuration file

### Description

Object oriented style

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">tidy::repairString</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \]\] )

Procedural style

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">tidy\_repair\_string</span> ( <span
class="methodparam"><span class="type">string</span> `$string`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$config`<span class="initializer"> =
**`null`**</span></span> \[, <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$encoding`<span class="initializer"> =
**`null`**</span></span> \]\] )

Repairs the given string.

### Parameters

`string`  
The data to be repaired.

`config`  
The config `config` can be passed either as an array or as a string. If
a string is passed, it is interpreted as the name of the configuration
file, otherwise, it is interpreted as the options themselves.

Check
<a href="http://api.html-tidy.org/#quick-reference" class="link external">» http://api.html-tidy.org/#quick-reference</a>
for an explanation about each option.

`encoding`  
The `encoding` parameter sets the encoding for input/output documents.
The possible values for encoding are: *ascii*, *latin0*, *latin1*,
*raw*, *utf8*, *iso2022*, *mac*, *win1252*, *ibm858*, *utf16*,
*utf16le*, *utf16be*, *big5*, and *shiftjis*.

### Return Values

Returns the repaired string, or **`false`** on failure.

### Changelog

| Version | Description                                                                |
|---------|----------------------------------------------------------------------------|
| 8.0.0   | <span class="methodname">tidy::repairString</span> is a static method now. |
| 8.0.0   | `config` and `encoding` are nullable now.                                  |
| 8.0.0   | This function no longer accepts the `useIncludePath` parameter.            |

### Examples

**Example \#1 <span class="function">tidy::repairString</span> example**

``` php
<?php
ob_start();
?>

<html>
  <head>
    <title>test</title>
  </head>
  <body>
    <p>error</i>
  </body>
</html>

<?php

$buffer = ob_get_clean();
$tidy = new tidy();
$clean = $tidy->repairString($buffer);

echo $clean;
?>
```

The above example will output:

    <!DOCTYPE html PUBLIC "-//W3C//DTD HTML 3.2//EN">
    <html>
    <head>
    <title>test</title>
    </head>
    <body>
    <p>error</p>
    </body>
    </html>

### See Also

-   <span class="function">tidy::parseFile</span>
-   <span class="function">tidy::parseString</span>
-   <span class="function">tidy::repairFile</span>

tidy::root
==========

tidy\_get\_root
===============

Returns a <span class="classname">tidyNode</span> object representing
the root of the tidy parse tree

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">tidy::root</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type"><span class="type">tidyNode</span><span
class="type">null</span></span> <span
class="methodname">tidy\_get\_root</span> ( <span
class="methodparam"><span class="type">tidy</span> `$tidy`</span> )

Returns a <span class="classname">tidyNode</span> object representing
the root of the tidy parse tree.

### Parameters

`tidy`  
The <span class="classname">Tidy</span> object.

### Return Values

Returns the <span class="classname">tidyNode</span> object.

### Examples

**Example \#1 <span class="function">tidy::root</span> example**

``` php
<?php

$html = <<< HTML
<html><body>

<p>paragraph</p>
<br/>

</body></html>
HTML;

$tidy = tidy_parse_string($html);
dump_nodes($tidy->root(), 1);


function dump_nodes($node, $indent) {

    if($node->hasChildren()) {
        foreach($node->child as $child) {
            echo str_repeat('.', $indent*2) . ($child->name ? $child->name : '"'.$child->value.'"'). "\n";

            dump_nodes($child, $indent+1);
        }
    }
}
?>
```

The above example will output:

    ..html
    ....head
    ......title
    ....body
    ......p
    ........"paragraph"
    ......br

Introduction
------------

An HTML node in an HTML file, as detected by tidy.

Class synopsis
--------------

<span class="modifier">final</span> **tidyNode**

<span class="ooclass"> class **tidyNode** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span
class="type">string</span>`$value`;

<span class="modifier">public</span> <span
class="type">string</span>`$name`;

<span class="modifier">public</span> <span
class="type">int</span>`$type`;

<span class="modifier">public</span> <span
class="type">int</span>`$line`;

<span class="modifier">public</span> <span
class="type">int</span>`$column`;

<span class="modifier">public</span> <span
class="type">bool</span>`$proprietary`;

<span class="modifier">public</span> <span class="type">int</span>`$id`;

<span class="modifier">public</span> <span
class="type">array</span>`$attribute`;

<span class="modifier">public</span> <span
class="type">array</span>`$child`;

/\* Methods \*/

<span class="modifier">private</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">getParent</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasChildren</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasSiblings</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isAsp</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isComment</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isHtml</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isJste</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isPhp</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">isText</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`value`  
The HTML representation of the node, including the surrounding tags.

`name`  
The name of the HTML node

`type`  
The type of the node (one of the
<a href="/tidy/constants.html#tidy%20nodetype%20constants" class="link">nodetype constants</a>,
e.g. **`TIDY_NODETYPE_PHP`**)

`line`  
The line number at which the tags is located in the file

`column`  
The column number at which the tags is located in the file

`proprietary`  
Indicates if the node is a proprietary tag

`id`  
The ID of the node (one of the
<a href="/tidy/constants.html#tidy%20tag%20constants" class="link">tag constants</a>,
e.g. **`TIDY_TAG_FRAME`**)

`attribute`  
An array of string, representing the attributes names (as keys) of the
current node.

`child`  
An array of <span class="classname">tidyNode</span>, representing the
children of the current node.

| Version | Description                                   |
|---------|-----------------------------------------------|
| 5.1.0   | `line`, `column` and `proprietary` were added |

tidyNode::\_\_construct
=======================

Private constructor to disallow direct instantiation

### Description

<span class="modifier">private</span> <span
class="methodname">tidyNode::\_\_construct</span> ( <span
class="methodparam">void</span> )

### Parameters

This function has no parameters.

tidyNode::getParent
===================

Returns the parent node of the current node

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">tidyNode</span><span class="type">null</span></span> <span
class="methodname">tidyNode::getParent</span> ( <span
class="methodparam">void</span> )

Returns the parent node of the current node.

### Return Values

Returns a <span class="type">tidyNode</span> if the node has a parent,
or **`null`** otherwise.

### Examples

**Example \#1 <span class="function">tidyNode::hasChildren</span>
example**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
 </head>
 <body>
 Hello World
 </body>
</html>

HTML;


$tidy = tidy_parse_string($html);
$num = 0;

$node = $tidy->html()->child[0]->child[0];

var_dump($node->getparent()->name);
?>
```

The above example will output:

    string(4) "head"

tidyNode::hasChildren
=====================

Checks if a node has children

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidyNode::hasChildren</span> ( <span
class="methodparam">void</span> )

Tells if the node has children.

### Return Values

Returns **`true`** if the node has children, **`false`** otherwise.

### Examples

**Example \#1 <span class="function">tidyNode::hasChildren</span>
example**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
</head>
<body>

<?php
  // PHP code
  echo 'hello world!';
?>

<%
  /* ASP code */
  response.write("Hello World!")
%>

<!-- Comments -->
Hello World
</body></html>
Outside HTML
HTML;


$tidy = tidy_parse_string($html);
$num = 0;

// the head tag
var_dump($tidy->html()->child[0]->hasChildren());

// the php inside the head tag
var_dump($tidy->html()->child[0]->child[0]->hasChildren());

?>
```

The above example will output:

    bool(true)
    bool(false)

tidyNode::hasSiblings
=====================

Checks if a node has siblings

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidyNode::hasSiblings</span> ( <span
class="methodparam">void</span> )

Tells if the node has siblings.

### Return Values

Returns **`true`** if the node has siblings, **`false`** otherwise.

### Examples

**Example \#1 <span class="function">tidyNode::hasSiblings</span>
example**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
</head>
<body>

<?php
  // PHP code
  echo 'hello world!';
?>

<%
  /* ASP code */
  response.write("Hello World!")
%>

<!-- Comments -->
Hello World
</body></html>
Outside HTML
HTML;


$tidy = tidy_parse_string($html);
$num = 0;

// the html tag
var_dump($tidy->html()->hasSiblings());

// the head tag
var_dump($tidy->html()->child[0]->hasSiblings());

?>
```

The above example will output:

    bool(false)
    bool(true)

tidyNode::isAsp
===============

Checks if this node is ASP

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidyNode::isAsp</span> ( <span
class="methodparam">void</span> )

Tells whether the current node is ASP.

### Return Values

Returns **`true`** if the node is ASP, **`false`** otherwise.

### Examples

**Example \#1 Extract ASP code from a mixed HTML document**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
</head>
<body>

<?php
  // PHP code
  echo 'hello world!';
?>

<%
  /* ASP code */
  response.write("Hello World!")
%>

<!-- Comments -->
Hello World
</body></html>
Outside HTML
HTML;


$tidy = tidy_parse_string($html);
$num = 0;

get_nodes($tidy->html());

function get_nodes($node) {

    // check if the current node is of requested type
    if($node->isAsp()) {
        echo "\n\n# asp node #" . ++$GLOBALS['num'] . "\n";
        echo $node->value;
    }

    // check if the current node has childrens
    if($node->hasChildren()) {
        foreach($node->child as $child) {
            get_nodes($child);
        }
    }
}

?>
```

The above example will output:

    # asp node #1
    <%
      /* ASP code */
      response.write("Hello World!")
    %>

tidyNode::isComment
===================

Checks if a node represents a comment

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidyNode::isComment</span> ( <span
class="methodparam">void</span> )

Tells if the node is a comment.

### Return Values

Returns **`true`** if the node is a comment, **`false`** otherwise.

### Examples

**Example \#1 Extract comments from a mixed HTML document**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
</head>
<body>

<?php
  // PHP code
  echo 'hello world!';
?>

<%
  /* ASP code */
  response.write("Hello World!")
%>

<!-- Comments -->
Hello World
</body></html>
Outside HTML
HTML;


$tidy = tidy_parse_string($html);
$num = 0;

get_nodes($tidy->html());

function get_nodes($node) {

    // check if the current node is of requested type
    if($node->isComment()) {
        echo "\n\n# comment node #" . ++$GLOBALS['num'] . "\n";
        echo $node->value;
    }

    // check if the current node has childrens
    if($node->hasChildren()) {
        foreach($node->child as $child) {
            get_nodes($child);
        }
    }
}

?>
```

The above example will output:

    # comment node #1
    <!-- Comments -->

tidyNode::isHtml
================

Checks if a node is an element node

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidyNode::isHtml</span> ( <span
class="methodparam">void</span> )

Tells if the node is an element node, but not the root node of the
document.

### Return Values

Returns **`true`** if the node is an element node, but not the root node
of the document, **`false`** otherwise.

### Changelog

| Version        | Description                                                                                                               |
|----------------|---------------------------------------------------------------------------------------------------------------------------|
| 7.3.24, 7.4.12 | This function has been fixed to have reasonable behavior. Previously, almost any node was reported as being an HTML node. |

### Examples

**Example \#1 Extract HTML code from a mixed HTML document**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
</head>
<body>

<?php
  // PHP code
  echo 'hello world!';
?>

<%
  /* ASP code */
  response.write("Hello World!")
%>

<!-- Comments -->
Hello World
</body></html>
Outside HTML
HTML;


$tidy = tidy_parse_string($html);
$num = 0;

get_nodes($tidy->html());

function get_nodes($node) {
    // check if the current node is of requested type
    if($node->isHtml()) {
        echo "\n\n# html node #" . ++$GLOBALS['num'] . "\n";
        echo $node->value;
    }

    // check if the current node has childrens
    if($node->hasChildren()) {
        foreach($node->child as $child) {
            get_nodes($child);
        }
    }
}

?>
```

The above example will output:

    # html node #1
    <html>
    <head>
    <?php echo '<title>title</title>'; ?><#
      /* JSTE code */
      alert('Hello World');
    #>
    <title></title>
    </head>
    <body>
    <?php
      // PHP code
      echo 'hello world!';
    ?><%
      /* ASP code */
      response.write("Hello World!")
    %><!-- Comments -->
    Hello WorldOutside HTML
    </body>
    </html>

    # html node #2
    <head>
    <?php echo '<title>title</title>'; ?><#
      /* JSTE code */
      alert('Hello World');
    #>
    <title></title>
    </head>


    # html node #3
    <title></title>


    # html node #4
    <body>
    <?php
      // PHP code
      echo 'hello world!';
    ?><%
      /* ASP code */
      response.write("Hello World!")
    %><!-- Comments -->
    Hello WorldOutside HTML
    </body>

tidyNode::isJste
================

Checks if this node is JSTE

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidyNode::isJste</span> ( <span
class="methodparam">void</span> )

Tells if the node is JSTE.

### Return Values

Returns **`true`** if the node is JSTE, **`false`** otherwise.

### Examples

**Example \#1 Extract JSTE code from a mixed HTML document**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
</head>
<body>

<?php
  // PHP code
  echo 'hello world!';
?>

<%
  /* ASP code */
  response.write("Hello World!")
%>

<!-- Comments -->
Hello World
</body></html>
Outside HTML
HTML;


$tidy = tidy_parse_string($html);
$num = 0;

get_nodes($tidy->html());

function get_nodes($node) {

    // check if the current node is of requested type
    if($node->isJste()) {
        echo "\n\n# jste node #" . ++$GLOBALS['num'] . "\n";
        echo $node->value;
    }

    // check if the current node has childrens
    if($node->hasChildren()) {
        foreach($node->child as $child) {
            get_nodes($child);
        }
    }
}

?>
```

The above example will output:

    # jste node #1
    <# 
      /* JSTE code */
      alert('Hello World'); 
    #>

tidyNode::isPhp
===============

Checks if a node is PHP

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidyNode::isPhp</span> ( <span
class="methodparam">void</span> )

Tells if the node is PHP.

### Return Values

Returns **`true`** if the current node is PHP code, **`false`**
otherwise.

### Examples

**Example \#1 Extract PHP code from a mixed HTML document**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
</head>
<body>

<?php
  // PHP code
  echo 'hello world!';
?>

<%
  /* ASP code */
  response.write("Hello World!")
%>

<!-- Comments -->
Hello World
</body></html>
Outside HTML
HTML;


$tidy = tidy_parse_string($html);
$num = 0;

get_nodes($tidy->html());

function get_nodes($node) {

    // check if the current node is of requested type
    if($node->isPhp()) {
        echo "\n\n# php node #" . ++$GLOBALS['num'] . "\n";
        echo $node->value;
    }

    // check if the current node has childrens
    if($node->hasChildren()) {
        foreach($node->child as $child) {
            get_nodes($child);
        }
    }
}

?>
```

The above example will output:

    # php node #1
    <?php echo '<title>title</title>'; ?>

    # php node #2
    <?php
      // PHP code
      echo 'hello world!';
    ?>

tidyNode::isText
================

Checks if a node represents text (no markup)

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">tidyNode::isText</span> ( <span
class="methodparam">void</span> )

Tells if the node represents a text (without any markup).

### Return Values

Returns **`true`** if the node represent a text, **`false`** otherwise.

### Examples

**Example \#1 Extract text from a mixed HTML document**

``` php
<?php

$html = <<< HTML
<html><head>
<?php echo '<title>title</title>'; ?>
<# 
  /* JSTE code */
  alert('Hello World'); 
#>
</head>
<body>

<?php
  // PHP code
  echo 'hello world!';
?>

<%
  /* ASP code */
  response.write("Hello World!")
%>

<!-- Comments -->
Hello World
</body></html>
Outside HTML
HTML;


$tidy = tidy_parse_string($html);
$num = 0;

get_nodes($tidy->html());

function get_nodes($node) {

    // check if the current node is of requested type
    if($node->isText()) {
        echo "\n\n# text node #" . ++$GLOBALS['num'] . "\n";
        echo $node->value;
    }

    // check if the current node has childrens
    if($node->hasChildren()) {
        foreach($node->child as $child) {
            get_nodes($child);
        }
    }
}

?>
```

The above example will output:

    # text node #1
    Hello World

    # text node #2
    Outside HTML

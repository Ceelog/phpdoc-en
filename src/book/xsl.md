XSL
===

**Table of Contents**

-   [Introduction](/intro/xsl.html)
-   [Installing/Configuring](/xsl/setup.html)
    -   [Requirements](/xsl/setup.html#Requirements)
    -   [Installation](/xsl/setup.html#Installation)
    -   [Runtime Configuration](/xsl/setup.html#Runtime%20Configuration)
    -   [Resource Types](/xsl/setup.html#Resource%20Types)
-   [Predefined Constants](/xsl/constants.html)
-   [Examples](/xsl/examples.html)
    -   [Example collection.xml and collection.xsl
        files](/xsl/examples.html#Example%20collection.xml%20and%20collection.xsl%20files)
    -   [Error handling with libxml error handling
        functions](/xsl/examples.html#Error%20handling%20with%20libxml%20error%20handling%20functions)
-   [XSLTProcessor](/class/xsltprocessor.html) — The XSLTProcessor class
    -   [XSLTProcessor::\_\_construct](/class/xsltprocessor.html#XSLTProcessor::__construct)
        — Creates a new XSLTProcessor object
    -   [XSLTProcessor::getParameter](/class/xsltprocessor.html#XSLTProcessor::getParameter)
        — Get value of a parameter
    -   [XSLTProcessor::getSecurityPrefs](/class/xsltprocessor.html#XSLTProcessor::getSecurityPrefs)
        — Get security preferences
    -   [XSLTProcessor::hasExsltSupport](/class/xsltprocessor.html#XSLTProcessor::hasExsltSupport)
        — Determine if PHP has EXSLT support
    -   [XSLTProcessor::importStylesheet](/class/xsltprocessor.html#XSLTProcessor::importStylesheet)
        — Import stylesheet
    -   [XSLTProcessor::registerPHPFunctions](/class/xsltprocessor.html#XSLTProcessor::registerPHPFunctions)
        — Enables the ability to use PHP functions as XSLT functions
    -   [XSLTProcessor::removeParameter](/class/xsltprocessor.html#XSLTProcessor::removeParameter)
        — Remove parameter
    -   [XSLTProcessor::setParameter](/class/xsltprocessor.html#XSLTProcessor::setParameter)
        — Set value for a parameter
    -   [XSLTProcessor::setProfiling](/class/xsltprocessor.html#XSLTProcessor::setProfiling)
        — Sets profiling output file
    -   [XSLTProcessor::setSecurityPrefs](/class/xsltprocessor.html#XSLTProcessor::setSecurityPrefs)
        — Set security preferences
    -   [XSLTProcessor::transformToDoc](/class/xsltprocessor.html#XSLTProcessor::transformToDoc)
        — Transform to a DOMDocument
    -   [XSLTProcessor::transformToUri](/class/xsltprocessor.html#XSLTProcessor::transformToUri)
        — Transform to URI
    -   [XSLTProcessor::transformToXml](/class/xsltprocessor.html#XSLTProcessor::transformToXml)
        — Transform to XML

Introduction
------------

Class synopsis
--------------

**XSLTProcessor**

<span class="ooclass"> class **XSLTProcessor** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">getParameter</span> ( <span class="methodparam"><span
class="type">string</span> `$namespace`</span> , <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getSecurityPrefs</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">hasExsltSupport</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">importStylesheet</span> ( <span
class="methodparam"><span class="type">object</span>
`$stylesheet`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">registerPHPFunctions</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$functions`<span class="initializer"> =
**`null`**</span></span> \] )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">removeParameter</span> ( <span
class="methodparam"><span class="type">string</span> `$namespace`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setParameter</span> ( <span
class="methodparam"><span class="type">string</span> `$namespace`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">setProfiling</span> ( <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$filename`</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">setSecurityPrefs</span> ( <span
class="methodparam"><span class="type">int</span> `$preferences`</span>
)

<span class="modifier">public</span> <span class="type"><span
class="type">DOMDocument</span><span class="type">false</span></span>
<span class="methodname">transformToDoc</span> ( <span
class="methodparam"><span class="type">object</span> `$document`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$returnClass`<span class="initializer"> = **`null`**</span></span> \] )

<span class="type">int</span> <span
class="methodname">transformToURI</span> ( <span
class="methodparam"><span class="type">DOMDocument</span> `$doc`</span>
, <span class="methodparam"><span class="type">string</span>
`$uri`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span><span
class="type">null</span></span> <span
class="methodname">transformToXml</span> ( <span
class="methodparam"><span class="type">object</span> `$document`</span>
)

}

XSLTProcessor::\_\_construct
============================

Creates a new XSLTProcessor object

### Description

<span class="methodname">XSLTProcessor::\_\_construct</span> ( <span
class="methodparam">void</span> )

Creates a new <span class="classname">XSLTProcessor</span> object.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Examples

**Example \#1 Creating an <span class="classname">XSLTProcessor</span>**

``` php
<?php

$xsldoc = new DOMDocument();
$xsldoc->load($xsl_filename);

$xmldoc = new DOMDocument();
$xmldoc->load($xml_filename);

$xsl = new XSLTProcessor();
$xsl->importStyleSheet($xsldoc);
echo $xsl->transformToXML($xmldoc);

?>
```

XSLTProcessor::getParameter
===========================

Get value of a parameter

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">XSLTProcessor::getParameter</span> ( <span
class="methodparam"><span class="type">string</span> `$namespace`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> )

Gets a parameter if previously set by <span
class="function">XSLTProcessor::setParameter</span>.

### Parameters

`namespace`  
The namespace URI of the XSLT parameter.

`name`  
The local name of the XSLT parameter.

### Return Values

The value of the parameter (as a string), or **`false`** if it's not
set.

### See Also

-   <span class="function">XSLTProcessor::setParameter</span>
-   <span class="function">XSLTProcessor::removeParameter</span>

XSLTProcessor::getSecurityPrefs
===============================

Get security preferences

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">XSLTProcessor::getSecurityPrefs</span> ( <span
class="methodparam">void</span> )

Gets the security preferences.

### Parameters

This function has no parameters.

### Return Values

A bitmask consisting of **`XSL_SECPREF_READ_FILE`**,
**`XSL_SECPREF_WRITE_FILE`**, **`XSL_SECPREF_CREATE_DIRECTORY`**,
**`XSL_SECPREF_READ_NETWORK`**, **`XSL_SECPREF_WRITE_NETWORK`**.

XSLTProcessor::hasExsltSupport
==============================

Determine if PHP has EXSLT support

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">XSLTProcessor::hasExsltSupport</span> ( <span
class="methodparam">void</span> )

This method determines if PHP was built with the
<a href="http://xmlsoft.org/XSLT/EXSLT/index.html" class="link external">» EXSLT library</a>.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Testing EXSLT support**

``` php
<?php

$proc = new XSLTProcessor;
if (!$proc->hasExsltSupport()) {
    die('EXSLT support not available');
}

// do EXSLT stuff here ..

?>
```

XSLTProcessor::importStylesheet
===============================

Import stylesheet

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">XSLTProcessor::importStylesheet</span> ( <span
class="methodparam"><span class="type">object</span>
`$stylesheet`</span> )

This method imports the stylesheet into the <span
class="classname">XSLTProcessor</span> for transformations.

### Parameters

`stylesheet`  
The imported style sheet as a <span class="classname">DOMDocument</span>
or <span class="classname">SimpleXMLElement</span> object.

### Return Values

Returns **`true`** on success or **`false`** on failure.

XSLTProcessor::registerPHPFunctions
===================================

Enables the ability to use PHP functions as XSLT functions

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">XSLTProcessor::registerPHPFunctions</span> (\[
<span class="methodparam"><span class="type"><span
class="type">array</span><span class="type">string</span><span
class="type">null</span></span> `$functions`<span class="initializer"> =
**`null`**</span></span> \] )

This method enables the ability to use PHP functions as XSLT functions
within XSL stylesheets.

### Parameters

`functions`  
Use this parameter to only allow certain functions to be called from
XSLT.

This parameter can be either a string (a function name) or an array of
functions.

### Return Values

No value is returned.

### Examples

**Example \#1 Simple PHP Function call from a stylesheet**

``` php
<?php
$xml = <<<EOB
<allusers>
 <user>
  <uid>bob</uid>
 </user>
 <user>
  <uid>joe</uid>
 </user>
</allusers>
EOB;
$xsl = <<<EOB
<?xml version="1.0" encoding="UTF-8"?>
<xsl:stylesheet version="1.0" 
     xmlns:xsl="http://www.w3.org/1999/XSL/Transform"
     xmlns:php="http://php.net/xsl">
<xsl:output method="html" encoding="utf-8" indent="yes"/>
 <xsl:template match="allusers">
  <html><body>
    <h2>Users</h2>
    <table>
    <xsl:for-each select="user">
      <tr><td>
        <xsl:value-of
             select="php:function('ucfirst',string(uid))"/>
      </td></tr>
    </xsl:for-each>
    </table>
  </body></html>
 </xsl:template>
</xsl:stylesheet>
EOB;
$xmldoc = DOMDocument::loadXML($xml);
$xsldoc = DOMDocument::loadXML($xsl);

$proc = new XSLTProcessor();
$proc->registerPHPFunctions();
$proc->importStyleSheet($xsldoc);
echo $proc->transformToXML($xmldoc);
?>
```

XSLTProcessor::removeParameter
==============================

Remove parameter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">XSLTProcessor::removeParameter</span> ( <span
class="methodparam"><span class="type">string</span> `$namespace`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> )

Removes a parameter, if set. This will make the processor use the
default value for the parameter as specified in the stylesheet.

### Parameters

`namespace`  
The namespace URI of the XSLT parameter.

`name`  
The local name of the XSLT parameter.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### See Also

-   <span class="function">XSLTProcessor::setParameter</span>
-   <span class="function">XSLTProcessor::getParameter</span>

XSLTProcessor::setParameter
===========================

Set value for a parameter

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">XSLTProcessor::setParameter</span> ( <span
class="methodparam"><span class="type">string</span> `$namespace`</span>
, <span class="methodparam"><span class="type">string</span>
`$name`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">XSLTProcessor::setParameter</span> ( <span
class="methodparam"><span class="type">string</span> `$namespace`</span>
, <span class="methodparam"><span class="type">array</span>
`$options`</span> )

Sets the value of one or more parameters to be used in subsequent
transformations with <span class="classname">XSLTProcessor</span>. If
the parameter doesn't exist in the stylesheet it will be ignored.

### Parameters

`namespace`  
The namespace URI of the XSLT parameter.

`name`  
The local name of the XSLT parameter.

`value`  
The new value of the XSLT parameter.

`options`  
An array of *name =\> value* pairs.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Changing the owner before the transformation**

``` php
<?php

$collections = array(
    'Marc Rutkowski' => 'marc',
    'Olivier Parmentier' => 'olivier'
);

$xsl = new DOMDocument;
$xsl->load('collection.xsl');

// Configure the transformer
$proc = new XSLTProcessor;
$proc->importStyleSheet($xsl); // attach the xsl rules

foreach ($collections as $name => $file) {
    // Load the XML source
    $xml = new DOMDocument;
    $xml->load('collection_' . $file . '.xml');

    $proc->setParameter('', 'owner', $name);
    $proc->transformToURI($xml, 'file:///tmp/' . $file . '.html');
}

?>
```

### See Also

-   <span class="function">XSLTProcessor::getParameter</span>
-   <span class="function">XSLTProcessor::removeParameter</span>

XSLTProcessor::setProfiling
===========================

Sets profiling output file

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">XSLTProcessor::setProfiling</span> ( <span
class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$filename`</span> )

Sets the file to output profiling information when processing a
stylesheet.

### Parameters

`filename`  
Path to the file to dump profiling information.

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Examples

**Example \#1 Example profiling output**

``` php
<?php
// Load the XML source
$xml = new DOMDocument;
$xml->load('collection.xml');

$xsl = new DOMDocument;
$xsl->load('collection.xsl');

// Configure the transformer
$proc = new XSLTProcessor;
$proc->setProfiling('profiling.txt');
$proc->importStyleSheet($xsl); // attach the xsl rules

echo trim($proc->transformToDoc($xml)->firstChild->wholeText);
?>
```

The above code will produce the following information in the profiling
file:

    number               match                name      mode  Calls Tot 100us Avg

        0                   cd                                    2      3      1
        1           collection                                    1      1      1

                             Total                                3      4

XSLTProcessor::setSecurityPrefs
===============================

Set security preferences

### Description

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">XSLTProcessor::setSecurityPrefs</span> ( <span
class="methodparam"><span class="type">int</span> `$preferences`</span>
)

Sets the security preferences.

### Parameters

`preferences`  
The new security preferences. The following constants can be ORed:
**`XSL_SECPREF_READ_FILE`**, **`XSL_SECPREF_WRITE_FILE`**,
**`XSL_SECPREF_CREATE_DIRECTORY`**, **`XSL_SECPREF_READ_NETWORK`**,
**`XSL_SECPREF_WRITE_NETWORK`**. Alternatively, **`XSL_SECPREF_NONE`**
or **`XSL_SECPREF_DEFAULT`** can be passed.

### Return Values

Returns the old security preferences.

XSLTProcessor::transformToDoc
=============================

Transform to a DOMDocument

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">DOMDocument</span><span class="type">false</span></span>
<span class="methodname">XSLTProcessor::transformToDoc</span> ( <span
class="methodparam"><span class="type">object</span> `$document`</span>
\[, <span class="methodparam"><span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$returnClass`<span class="initializer"> = **`null`**</span></span> \] )

Transforms the source node to a <span
class="classname">DOMDocument</span> applying the stylesheet given by
the <span class="function">XSLTProcessor::importStylesheet</span>
method.

### Parameters

`document`  
The node to be transformed.

### Return Values

The resulting <span class="classname">DOMDocument</span> or **`false`**
on error.

### Examples

**Example \#1 Transforming to a DOMDocument**

``` php
<?php

// Load the XML source
$xml = new DOMDocument;
$xml->load('collection.xml');

$xsl = new DOMDocument;
$xsl->load('collection.xsl');

// Configure the transformer
$proc = new XSLTProcessor;
$proc->importStyleSheet($xsl); // attach the xsl rules

echo trim($proc->transformToDoc($xml)->firstChild->wholeText);

?>
```

The above example will output:

    Hey! Welcome to Nicolas Eliaszewicz's sweet CD collection!

### See Also

-   <span class="function">XSLTProcessor::transformToUri</span>
-   <span class="function">XSLTProcessor::transformToXml</span>

XSLTProcessor::transformToUri
=============================

Transform to URI

### Description

<span class="type">int</span> <span
class="methodname">XSLTProcessor::transformToURI</span> ( <span
class="methodparam"><span class="type">DOMDocument</span> `$doc`</span>
, <span class="methodparam"><span class="type">string</span>
`$uri`</span> )

Transforms the source node to an URI applying the stylesheet given by
the <span class="function">XSLTProcessor::importStylesheet</span>
method.

### Parameters

`doc`  
The document to transform.

`uri`  
The target URI for the transformation.

### Return Values

Returns the number of bytes written or **`false`** if an error occurred.

### Examples

**Example \#1 Transforming to a HTML file**

``` php
<?php

// Load the XML source
$xml = new DOMDocument;
$xml->load('collection.xml');

$xsl = new DOMDocument;
$xsl->load('collection.xsl');

// Configure the transformer
$proc = new XSLTProcessor;
$proc->importStyleSheet($xsl); // attach the xsl rules

$proc->transformToURI($xml, 'file:///tmp/out.html');

?>
```

### See Also

-   <span class="function">XSLTProcessor::transformToDoc</span>
-   <span class="function">XSLTProcessor::transformToXml</span>

XSLTProcessor::transformToXml
=============================

Transform to XML

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span><span
class="type">null</span></span> <span
class="methodname">XSLTProcessor::transformToXml</span> ( <span
class="methodparam"><span class="type">object</span> `$document`</span>
)

Transforms the source node to a string applying the stylesheet given by
the <span class="function">xsltprocessor::importStylesheet</span>
method.

### Parameters

`document`  
The <span class="type">DOMDocument</span> or <span
class="type">SimpleXMLElement</span> object to be transformed.

### Return Values

The result of the transformation as a string or **`false`** on error.

### Examples

**Example \#1 Transforming to a string**

``` php
<?php

// Load the XML source
$xml = new DOMDocument;
$xml->load('collection.xml');

$xsl = new DOMDocument;
$xsl->load('collection.xsl');

// Configure the transformer
$proc = new XSLTProcessor;
$proc->importStyleSheet($xsl); // attach the xsl rules

echo $proc->transformToXML($xml);

?>
```

The above example will output:

    Hey! Welcome to Nicolas Eliaszewicz's sweet CD collection!

    <h1>Fight for your mind</h1><h2>by Ben Harper - 1995</h2><hr>
    <h1>Electric Ladyland</h1><h2>by Jimi Hendrix - 1997</h2><hr>

### See Also

-   <span class="function">XSLTProcessor::transformToDoc</span>
-   <span class="function">XSLTProcessor::transformToUri</span>

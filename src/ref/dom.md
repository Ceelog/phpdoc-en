dom\_import\_simplexml
======================

Gets a <span class="classname">DOMElement</span> object from a <span
class="classname">SimpleXMLElement</span> object

### Description

<span class="type">DOMElement</span> <span
class="methodname">dom\_import\_simplexml</span> ( <span
class="methodparam"><span class="type">SimpleXMLElement</span>
`$node`</span> )

This function takes the node `node` of class
<a href="/ref/simplexml.html" class="link">SimpleXML</a> and makes it
into a <span class="classname">DOMElement</span> node. This new object
can then be used as a native <span class="classname">DOMElement</span>
node.

### Parameters

`node`  
The <span class="classname">SimpleXMLElement</span> node.

### Return Values

The <span class="classname">DOMElement</span> node added or **`false`**
if any errors occur.

### Examples

**Example \#1 Import SimpleXML into DOM with <span
class="function">dom\_import\_simplexml</span>**

``` php
<?php

$sxe = simplexml_load_string('<books><book><title>blah</title></book></books>');

if ($sxe === false) {
    echo 'Error while parsing the document';
    exit;
}

$dom_sxe = dom_import_simplexml($sxe);
if (!$dom_sxe) {
    echo 'Error while converting XML';
    exit;
}

$dom = new DOMDocument('1.0');
$dom_sxe = $dom->importNode($dom_sxe, true);
$dom_sxe = $dom->appendChild($dom_sxe);

echo $dom->saveXML();

?>
```

### See Also

-   <span class="function">simplexml\_import\_dom</span>

**Table of Contents**

-   [dom\_import\_simplexml](/ref/dom.html#dom_import_simplexml) — Gets
    a DOMElement object from a SimpleXMLElement object

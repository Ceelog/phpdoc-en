CommonMark\\Parse
=================

Parsing

### Description

<span class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Parse</span> ( <span
class="methodparam"><span class="type">string</span> `$content`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`</span> \] )

Shall parse `content`

### Parameters

`content`  
markdown string

`options`  
A mask of:

**`CommonMark\Parser\Normal`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Parser\Normalize`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Parser\ValidateUTF8`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Parser\Smart`** (<span class="type">int</span>)  
<span class="simpara"> </span>

### Return Values

Shall return root CommonMark\\Node

CommonMark\\Render
==================

Rendering

### Description

<span class="type">string</span> <span
class="methodname">CommonMark\\Render</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$node`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`</span> \[, <span
class="methodparam"><span class="type">int</span> `$width`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`node`  

`options`  
A mask of:

**`CommonMark\Render\Normal`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\SourcePos`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\HardBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\Safe`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\NoBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

`width`  

### Return Values

CommonMark\\Render\\HTML
========================

Rendering

### Description

<span class="type">string</span> <span
class="methodname">CommonMark\\Render\\HTML</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$node`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`node`  

`options`  
A mask of:

**`CommonMark\Render\Normal`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\SourcePos`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\HardBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\Safe`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\NoBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

### Return Values

CommonMark\\Render\\Latex
=========================

Rendering

### Description

<span class="type">string</span> <span
class="methodname">CommonMark\\Render\\Latex</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$node`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`</span> \[, <span
class="methodparam"><span class="type">int</span> `$width`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`node`  

`options`  
A mask of:

**`CommonMark\Render\Normal`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\SourcePos`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\HardBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\Safe`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\NoBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

`width`  

### Return Values

CommonMark\\Render\\Man
=======================

Rendering

### Description

<span class="type">string</span> <span
class="methodname">CommonMark\\Render\\Man</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$node`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`</span> \[, <span
class="methodparam"><span class="type">int</span> `$width`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`node`  

`options`  
A mask of:

**`CommonMark\Render\Normal`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\SourcePos`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\HardBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\Safe`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\NoBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

`width`  

### Return Values

CommonMark\\Render\\XML
=======================

Rendering

### Description

<span class="type">string</span> <span
class="methodname">CommonMark\\Render\\XML</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$node`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`node`  

`options`  
A mask of:

**`CommonMark\Render\Normal`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\SourcePos`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\HardBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\Safe`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`CommonMark\Render\NoBreaks`** (<span class="type">int</span>)  
<span class="simpara"> </span>

### Return Values

**Table of Contents**

-   [CommonMark\\Parse](/ref/cmark.html#CommonMark\Parse) — Parsing
-   [CommonMark\\Render](/ref/cmark.html#CommonMark\Render) — Rendering
-   [CommonMark\\Render\\HTML](/ref/cmark.html#CommonMark\Render\HTML) —
    Rendering
-   [CommonMark\\Render\\Latex](/ref/cmark.html#CommonMark\Render\Latex)
    — Rendering
-   [CommonMark\\Render\\Man](/ref/cmark.html#CommonMark\Render\Man) —
    Rendering
-   [CommonMark\\Render\\XML](/ref/cmark.html#CommonMark\Render\XML) —
    Rendering

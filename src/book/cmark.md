CommonMark
==========

**Table of Contents**

-   [Introduction](/intro/cmark.html)
-   [Installing/Configuring](/cmark/setup.html)
    -   [Requirements](/cmark/setup.html#Requirements)
    -   [Installation](/cmark/setup.html#Installation)
-   [CommonMark\\Node\\Document](/class/commonmark-node-document.html) —
    Document concrete CommonMark\\Node
-   [CommonMark\\Node\\Heading](/class/commonmark-node-heading.html) —
    Heading concrete CommonMark\\Node
    -   [CommonMark\\Node\\Heading::\_\_construct](/class/commonmark-node-heading.html#CommonMark\Node\Heading::__construct)
        — Heading Construction
-   [CommonMark\\Node\\Paragraph](/class/commonmark-node-paragraph.html)
    — Paragraph concrete CommonMark\\Node
-   [CommonMark\\Node\\BlockQuote](/class/commonmark-node-blockquote.html)
    — BlockQuote concrete CommonMark\\Node
-   [CommonMark\\Node\\BulletList](/class/commonmark-node-bulletlist.html)
    — BulletList concrete CommonMark\\Node
    -   [CommonMark\\Node\\BulletList::\_\_construct](/class/commonmark-node-bulletlist.html#CommonMark\Node\BulletList::__construct)
        — BulletList Construction
-   [CommonMark\\Node\\OrderedList](/class/commonmark-node-orderedlist.html)
    — OrderedList concrete CommonMark\\Node
    -   [CommonMark\\Node\\OrderedList::\_\_construct](/class/commonmark-node-orderedlist.html#CommonMark\Node\OrderedList::__construct)
        — OrderedList Construction
-   [CommonMark\\Node\\Item](/class/commonmark-node-item.html) — Item
    concrete CommonMark\\Node
-   [CommonMark\\Node\\Text](/class/commonmark-node-text.html) — Text
    concrete CommonMark\\Node
    -   [CommonMark\\Node\\Text::\_\_construct](/class/commonmark-node-text.html#CommonMark\Node\Text::__construct)
        — Text Construction
-   [CommonMark\\Node\\Text\\Strong](/class/commonmark-node-text-strong.html)
    — Strong concrete CommonMark\\Node
-   [CommonMark\\Node\\Text\\Emphasis](/class/commonmark-node-text-emphasis.html)
    — Emphasis concrete CommonMark\\Node
-   [CommonMark\\Node\\ThematicBreak](/class/commonmark-node-thematicbreak.html)
    — ThematicBreak concrete CommonMark\\Node
-   [CommonMark\\Node\\SoftBreak](/class/commonmark-node-softbreak.html)
    — SoftBreak concrete CommonMark\\Node
-   [CommonMark\\Node\\LineBreak](/class/commonmark-node-linebreak.html)
    — LineBreak concrete CommonMark\\Node
-   [CommonMark\\Node\\Code](/class/commonmark-node-code.html) — Code
    concrete CommonMark\\Node
-   [CommonMark\\Node\\CodeBlock](/class/commonmark-node-codeblock.html)
    — CodeBlock concrete CommonMark\\Node
    -   [CommonMark\\Node\\CodeBlock::\_\_construct](/class/commonmark-node-codeblock.html#CommonMark\Node\CodeBlock::__construct)
        — CodeBlock Construction
-   [CommonMark\\Node\\HTMLBlock](/class/commonmark-node-htmlblock.html)
    — HTMLBlock concrete CommonMark\\Node
-   [CommonMark\\Node\\HTMLInline](/class/commonmark-node-htmlinline.html)
    — HTMLInline concrete CommonMark\\Node
-   [CommonMark\\Node\\Image](/class/commonmark-node-image.html) — Image
    concrete CommonMark\\Node
    -   [CommonMark\\Node\\Image::\_\_construct](/class/commonmark-node-image.html#CommonMark\Node\Image::__construct)
        — Image Construction
-   [CommonMark\\Node\\Link](/class/commonmark-node-link.html) — Link
    concrete CommonMark\\Node
    -   [CommonMark\\Node\\Link::\_\_construct](/class/commonmark-node-link.html#CommonMark\Node\Link::__construct)
        — Link Construction
-   [CommonMark\\Node\\CustomBlock](/class/commonmark-node-customblock.html)
    — CustomBlock concrete CommonMark\\Node
-   [CommonMark\\Node\\CustomInline](/class/commonmark-node-custominline.html)
    — CustomInline concrete CommonMark\\Node
-   [CommonMark\\Node](/class/commonmark-node.html) — Abstract
    CommonMark\\Node
    -   [CommonMark\\Node::appendChild](/class/commonmark-node.html#CommonMark\Node::appendChild)
        — AST Manipulation
    -   [CommonMark\\Node::prependChild](/class/commonmark-node.html#CommonMark\Node::prependChild)
        — AST Manipulation
    -   [CommonMark\\Node::insertAfter](/class/commonmark-node.html#CommonMark\Node::insertAfter)
        — AST Manipulation
    -   [CommonMark\\Node::insertBefore](/class/commonmark-node.html#CommonMark\Node::insertBefore)
        — AST Manipulation
    -   [CommonMark\\Node::replace](/class/commonmark-node.html#CommonMark\Node::replace)
        — AST Manipulation
    -   [CommonMark\\Node::unlink](/class/commonmark-node.html#CommonMark\Node::unlink)
        — AST Manipulation
    -   [CommonMark\\Node::accept](/class/commonmark-node.html#CommonMark\Node::accept)
        — Visitation
-   [CommonMark\\Interfaces\\IVisitor](/class/commonmark-interfaces-ivisitor.html)
    — The CommonMark\\Interfaces\\IVisitor interface
    -   [CommonMark\\Interfaces\\IVisitor::enter](/class/commonmark-interfaces-ivisitor.html#CommonMark\Interfaces\IVisitor::enter)
        — Visitation
    -   [CommonMark\\Interfaces\\IVisitor::leave](/class/commonmark-interfaces-ivisitor.html#CommonMark\Interfaces\IVisitor::leave)
        — Visitation
-   [CommonMark\\Interfaces\\IVisitable](/class/commonmark-interfaces-ivisitable.html)
    — The CommonMark\\Interfaces\\IVisitable interface
    -   [CommonMark\\Interfaces\\IVisitable::accept](/class/commonmark-interfaces-ivisitable.html#CommonMark\Interfaces\IVisitable::accept)
        — Visitation
-   [CommonMark\\Parser](/class/commonmark-parser.html) — The
    CommonMark\\Parser class
    -   [CommonMark\\Parser::\_\_construct](/class/commonmark-parser.html#CommonMark\Parser::__construct)
        — Parsing
    -   [CommonMark\\Parser::parse](/class/commonmark-parser.html#CommonMark\Parser::parse)
        — Parsing
    -   [CommonMark\\Parser::finish](/class/commonmark-parser.html#CommonMark\Parser::finish)
        — Parsing
-   [CommonMark\\CQL](/class/commonmark-cql.html) — The CommonMark\\CQL
    class
    -   [CommonMark\\CQL::\_\_construct](/class/commonmark-cql.html#CommonMark\CQL::__construct)
        — CQL Construction
    -   [CommonMark\\CQL::\_\_invoke](/class/commonmark-cql.html#CommonMark\CQL::__invoke)
        — CQL Execution
-   [CommonMark Functions](/ref/cmark.html)
    -   [CommonMark\\Parse](/ref/cmark.html#CommonMark\Parse) — Parsing
    -   [CommonMark\\Render](/ref/cmark.html#CommonMark\Render) —
        Rendering
    -   [CommonMark\\Render\\HTML](/ref/cmark.html#CommonMark\Render\HTML)
        — Rendering
    -   [CommonMark\\Render\\Latex](/ref/cmark.html#CommonMark\Render\Latex)
        — Rendering
    -   [CommonMark\\Render\\Man](/ref/cmark.html#CommonMark\Render\Man)
        — Rendering
    -   [CommonMark\\Render\\XML](/ref/cmark.html#CommonMark\Render\XML)
        — Rendering

Class synopsis
--------------

**CommonMark\\Node\\Document**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Document** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\Heading**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Heading** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">int</span>
`$level` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$level`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Node\\Heading::\_\_construct
========================================

Heading Construction

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Heading::\_\_construct</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Heading::\_\_construct</span> (
<span class="methodparam"><span class="type">int</span> `$level`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

Class synopsis
--------------

**CommonMark\\Node\\Paragraph**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Paragraph** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\BlockQuote**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\BlockQuote** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\BulletList**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\BulletList** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">bool</span>
`$tight` ;

<span class="modifier">public</span> <span class="type">int</span>
`$delimiter` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$tight`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$tight`</span> ,
<span class="methodparam"><span class="type">int</span>
`$delimiter`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Node\\BulletList::\_\_construct
===========================================

BulletList Construction

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\BulletList::\_\_construct</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\BulletList::\_\_construct</span> (
<span class="methodparam"><span class="type">int</span> `$tight`</span>
)

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\BulletList::\_\_construct</span> (
<span class="methodparam"><span class="type">int</span> `$tight`</span>
, <span class="methodparam"><span class="type">int</span>
`$delimiter`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

Class synopsis
--------------

**CommonMark\\Node\\OrderedList**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\OrderedList** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">bool</span>
`$tight` ;

<span class="modifier">public</span> <span class="type">int</span>
`$delimiter` ;

<span class="modifier">public</span> <span class="type">int</span>
`$start` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$tight`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$tight`</span> ,
<span class="methodparam"><span class="type">int</span>
`$delimiter`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">int</span> `$tight`</span> ,
<span class="methodparam"><span class="type">int</span>
`$delimiter`</span> , <span class="methodparam"><span
class="type">int</span> `$start`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Node\\OrderedList::\_\_construct
============================================

OrderedList Construction

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\OrderedList::\_\_construct</span> (
<span class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\OrderedList::\_\_construct</span> (
<span class="methodparam"><span class="type">int</span> `$tight`</span>
)

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\OrderedList::\_\_construct</span> (
<span class="methodparam"><span class="type">int</span> `$tight`</span>
, <span class="methodparam"><span class="type">int</span>
`$delimiter`</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\OrderedList::\_\_construct</span> (
<span class="methodparam"><span class="type">int</span> `$tight`</span>
, <span class="methodparam"><span class="type">int</span>
`$delimiter`</span> , <span class="methodparam"><span
class="type">int</span> `$start`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`tight`  

`delimiter`  

`start`  

Class synopsis
--------------

**CommonMark\\Node\\Item**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Item** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\Text**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Text** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$literal` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$literal`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Node\\Text::\_\_construct
=====================================

Text Construction

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$literal`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`literal`  

Class synopsis
--------------

**CommonMark\\Node\\Text\\Strong**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Text\\Strong** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\Text\\Emphasis**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Text\\Emphasis** </span> <span class="ooclass">
<span class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\ThematicBreak**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\ThematicBreak** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\SoftBreak**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\SoftBreak** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\LineBreak**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\LineBreak** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\Code**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Code** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node\\Text** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$literal` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$literal`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\CodeBlock**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\CodeBlock** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node\\Text** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$literal` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span> `$fence`
;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$literal`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$fence`</span> ,
<span class="methodparam"><span class="type">string</span>
`$literal`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Node\\CodeBlock::\_\_construct
==========================================

CodeBlock Construction

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\CodeBlock::\_\_construct</span> (
<span class="methodparam"><span class="type">string</span>
`$fence`</span> , <span class="methodparam"><span
class="type">string</span> `$literal`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`fence`  

`literal`  

Class synopsis
--------------

**CommonMark\\Node\\HTMLBlock**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\HTMLBlock** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node\\Text** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$literal` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$literal`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\HTMLInline**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\HTMLInline** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node\\Text** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$literal` ;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Text::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$literal`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\Image**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Image** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span> `$url` ;

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span> `$title`
;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> ,
<span class="methodparam"><span class="type">string</span>
`$title`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Node\\Image::\_\_construct
======================================

Image Construction

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Image::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Image::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Image::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> ,
<span class="methodparam"><span class="type">string</span>
`$title`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`url`  

`title`  

Class synopsis
--------------

**CommonMark\\Node\\Link**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\Link** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span> `$url` ;

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span> `$title`
;

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> ,
<span class="methodparam"><span class="type">string</span>
`$title`</span> )

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Node\\Link::\_\_construct
=====================================

Link Construction

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Link::\_\_construct</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Link::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> )

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Node\\Link::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$url`</span> ,
<span class="methodparam"><span class="type">string</span>
`$title`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`url`  

`title`  

Class synopsis
--------------

**CommonMark\\Node\\CustomBlock**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\CustomBlock** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$onEnter` ;

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$onLeave` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Class synopsis
--------------

**CommonMark\\Node\\CustomInline**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Node\\CustomInline** </span> <span class="ooclass"> <span
class="modifier">extends</span> **CommonMark\\Node** </span> <span
class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Inherited properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$onEnter` ;

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">null</span></span>
`$onLeave` ;

/\* Inherited methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

Introduction
------------

Represents an Abstract Node, this final abstract is not for direct use
by the programmer.

Class synopsis
--------------

**CommonMark\\Node**

<span class="ooclass"> <span class="modifier">final</span> <span
class="modifier">abstract</span> class **CommonMark\\Node** </span>
<span class="oointerface">implements <span
class="interfacename">CommonMark\\Interfaces\\IVisitable</span> </span>
<span class="oointerface">, <span
class="interfacename">Traversable</span> </span> {

/\* Properties \*/

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$parent`
;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$previous` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span> `$next` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$lastChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type"><span
class="type">Node</span><span class="type">null</span></span>
`$firstChild` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endLine` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$startColumn` ;

<span class="modifier">public</span> <span
class="modifier">readonly</span> <span class="type">int</span>
`$endColumn` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">appendChild</span> ( <span class="methodparam"><span
class="type">CommonMark\\Node</span> `$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">prependChild</span> ( <span class="methodparam"><span
class="type">CommonMark\\Node</span> `$child`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">insertAfter</span> ( <span class="methodparam"><span
class="type">CommonMark\\Node</span> `$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">insertBefore</span> ( <span class="methodparam"><span
class="type">CommonMark\\Node</span> `$sibling`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">replace</span> ( <span class="methodparam"><span
class="type">CommonMark\\Node</span> `$target`</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">unlink</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">accept</span> ( <span class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Node::appendChild
=============================

AST Manipulation

### Description

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::appendChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`child`  

### Return Values

CommonMark\\Node::prependChild
==============================

AST Manipulation

### Description

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::prependChild</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$child`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`child`  

### Return Values

CommonMark\\Node::insertAfter
=============================

AST Manipulation

### Description

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertAfter</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`sibling`  

### Return Values

CommonMark\\Node::insertBefore
==============================

AST Manipulation

### Description

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::insertBefore</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$sibling`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`sibling`  

### Return Values

CommonMark\\Node::replace
=========================

AST Manipulation

### Description

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Node::replace</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$target`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`target`  

### Return Values

CommonMark\\Node::unlink
========================

AST Manipulation

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::unlink</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

CommonMark\\Node::accept
========================

Visitation

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Node::accept</span> ( <span
class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

### Parameters

`visitor`  
An object implementing <span
class="classname">CommonMark\\Interfaces\\IVisitor</span>

### See Also

-   <a href="/class/commonmark-interfaces-ivisitor.html#CommonMark\Interfaces\IVisitor::enter" class="xref"></a>
-   <a href="/class/commonmark-interfaces-ivisitor.html#CommonMark\Interfaces\IVisitor::leave" class="xref"></a>

Introduction
------------

Class synopsis
--------------

**CommonMark\\Interfaces\\IVisitor**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Interfaces\\IVisitor** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`CommonMark\Interfaces\IVisitor::Done` ;

<span class="modifier">const</span> <span class="type">int</span>
`CommonMark\Interfaces\IVisitor::Enter` ;

<span class="modifier">const</span> <span class="type">int</span>
`CommonMark\Interfaces\IVisitor::Leave` ;

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">IVisitable</span><span
class="type">null</span></span> <span class="methodname">enter</span> (
<span class="methodparam"><span class="type">IVisitable</span>
`$visitable`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">IVisitable</span><span
class="type">null</span></span> <span class="methodname">leave</span> (
<span class="methodparam"><span class="type">IVisitable</span>
`$visitable`</span> )

}

CommonMark\\Interfaces\\IVisitor::enter
=======================================

Visitation

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">IVisitable</span><span
class="type">null</span></span> <span
class="methodname">CommonMark\\Interfaces\\IVisitor::enter</span> (
<span class="methodparam"><span class="type">IVisitable</span>
`$visitable`</span> )

### Parameters

`visitable`  
The current <span
class="classname">CommonMark\\Interfaces\\IVisitable</span> being
entered

### Return Values

Returning `CommonMark\Interfaces\IVisitor::Done` will cause the backing
iterator to exit.

Returning `CommonMark\Interfaces\IVisitor::Enter` will reset the backing
iterator at entering the current <span
class="classname">IVisitable</span>

Returning `CommonMark\Interfaces\IVisitor::Leave` will reset the backing
iterator at exiting the current <span
class="classname">IVisitable</span>

Returning an <span class="classname">IVisitable</span> will reset the
backing iterator at entering the given <span
class="classname">IVisitable</span>

Returning nothing will allow the backing iterator to continue

### See Also

-   <a href="/class/commonmark-interfaces-ivisitable.html#CommonMark\Interfaces\IVisitable::accept" class="xref"></a>

CommonMark\\Interfaces\\IVisitor::leave
=======================================

Visitation

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">IVisitable</span><span
class="type">null</span></span> <span
class="methodname">CommonMark\\Interfaces\\IVisitor::leave</span> (
<span class="methodparam"><span class="type">IVisitable</span>
`$visitable`</span> )

### Parameters

`visitable`  
The current <span
class="classname">CommonMark\\Interfaces\\IVisitable</span> being exited

### Return Values

Returning `CommonMark\Interfaces\IVisitor::Done` will cause the backing
iterator to exit.

Returning `CommonMark\Interfaces\IVisitor::Enter` will reset the backing
iterator at entering the current <span
class="classname">IVisitable</span>

Returning `CommonMark\Interfaces\IVisitor::Leave` will reset the backing
iterator at exiting the current <span
class="classname">IVisitable</span>

Returning an <span class="classname">IVisitable</span> will reset the
backing iterator at exiting the given <span
class="classname">IVisitable</span>

Returning nothing will allow the backing iterator to continue

### See Also

-   <a href="/class/commonmark-interfaces-ivisitable.html#CommonMark\Interfaces\IVisitable::accept" class="xref"></a>

Introduction
------------

Class synopsis
--------------

**CommonMark\\Interfaces\\IVisitable**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Interfaces\\IVisitable** </span> {

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">accept</span> ( <span class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

}

CommonMark\\Interfaces\\IVisitable::accept
==========================================

Visitation

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">void</span> <span
class="methodname">CommonMark\\Interfaces\\IVisitable::accept</span> (
<span class="methodparam"><span
class="type">CommonMark\\Interfaces\\IVisitor</span> `$visitor`</span> )

### Parameters

`visitor`  
An object implementing <span
class="classname">CommonMark\\Interfaces\\IVisitor</span>

### See Also

-   <a href="/class/commonmark-interfaces-ivisitor.html#CommonMark\Interfaces\IVisitor::enter" class="xref"></a>
-   <a href="/class/commonmark-interfaces-ivisitor.html#CommonMark\Interfaces\IVisitor::leave" class="xref"></a>

Introduction
------------

Provides an incremental parser as an alternative to the simple Parsing
API function

Class synopsis
--------------

**CommonMark\\Parser**

<span class="ooclass"> <span class="modifier">final</span> class
**CommonMark\\Parser** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`</span> \] )

/\* Methods \*/

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">parse</span> ( <span class="methodparam"><span
class="type">string</span> `$buffer`</span> )

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">finish</span> ( <span class="methodparam">void</span>
)

}

CommonMark\\Parser::\_\_construct
=================================

Parsing

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\Parser::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">int</span> `$options`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

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

CommonMark\\Parser::parse
=========================

Parsing

### Description

<span class="modifier">public</span> <span class="type">void</span>
<span class="methodname">CommonMark\\Parser::parse</span> ( <span
class="methodparam"><span class="type">string</span> `$buffer`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`buffer`  

### Return Values

CommonMark\\Parser::finish
==========================

Parsing

### Description

<span class="modifier">public</span> <span
class="type">CommonMark\\Node</span> <span
class="methodname">CommonMark\\Parser::finish</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

Introduction
------------

CommonMark Query Language is a DSL for describing how to travel through
a CommonMark Node tree implemented as a parser and compiler for a small
set of instructions, and a virtual machine for executing those
instructions.

##### Paths:

In it's most simplistic form, a CQL query combines the following paths
and */* to describe how to travel through a tree:

-   firstChild
-   lastChild
-   previous
-   next
-   parent

For example, */firstChild/lastChild* would travel to the last child node
of the first child node.

##### Loops

CQL can be instructed to loop, for example through the children of, or
siblings to a particular node, by using the path *children*, or
*siblings*. For example, */firstChild/children* will travel to all the
children of the first child node.

##### Subqueries

CQL can be instructed how to travel by using a subquery like
*\[/firstChild\]*. For example, */firstChild/children\[/firstChild\]*
will travel to the first child node of all the children of the first
child node.

##### Loop Constraints

While looping, CQL can be instructed to constrict the travelled path to
nodes of particular type. For example */children(BlockQuote)* will
travel to the children of a node where the type is *BlockQuote*. The
following types are recognized (case insensitively):

-   BlockQuote
-   List
-   Item
-   CodeBlock
-   HtmlBlock
-   CustomBlock
-   Paragraph
-   Heading
-   ThematicBreak
-   Text
-   SoftBreak
-   LineBreak
-   Code
-   HtmlInline
-   CustomInline
-   Emphasis
-   Strong
-   Link
-   Image

Types may be used as a union, for example */children(BlockQuote\|List)*
will travel to the children of a node where the type is *BlockQuote* or
*List*. Types, or unions of types, may be also negated. For example
*/children(\~BlockQuote)* will travel to the children of a node where
the type is not *BlockQuote*, and */children(\~BlockQuote\|Paragraph)*
will travel to the children of a node where the type is not *BlockQuote*
or *Paragraph*

##### Path Constraints

CQL can be instructed to create a loop to travel to a node of a
particular type, at a particular path. For example,
*/firstChild(BlockQuote)* will travel to the first child node where the
type is *BlockQuote*. Note that like other loops for *children* and
*siblings*, this kind of path can only be followed by a subquery.

##### Implementation Notes

While CQL has been implemented as part of the PHP CommonMark extension,
it stands separately from PHP and does not use PHP's virtual machine or
internal representation of values.

Class synopsis
--------------

**CommonMark\\CQL**

<span class="ooclass"> class **CommonMark\\CQL** </span> {

/\* Constructor \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_invoke</span> ( <span class="methodparam"><span
class="type">CommonMark\\Node</span> `$root`</span> , <span
class="methodparam"><span class="type">callable</span> `$handler`</span>
)

}

CommonMark\\CQL::\_\_construct
==============================

CQL Construction

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\CQL::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$query`</span> )

### Parameters

`query`  
a CQL string

CommonMark\\CQL::\_\_invoke
===========================

CQL Execution

### Description

<span class="modifier">public</span> <span
class="methodname">CommonMark\\CQL::\_\_invoke</span> ( <span
class="methodparam"><span class="type">CommonMark\\Node</span>
`$root`</span> , <span class="methodparam"><span
class="type">callable</span> `$handler`</span> )

Shall invoke the current CQL function on the given `root`, executing the
given `handler` on entry to a <span class="type">CommonMark\\Node</span>

### Parameters

`root`  
the root node of a tree

`handler`  
should have the prototype:

<span class="type"><span class="type">bool</span><span
class="type">null</span></span> <span class="methodname">handler</span>
( <span class="methodparam"><span class="type">CommonMark\\Node</span>
`$root`</span> , <span class="methodparam"><span
class="type">CommonMark\\Node</span> `$entering`</span> )

-   Should `handler` fail to return (void), or return <span
    class="type">null</span>, CQL will continue executing
-   Should the handler return a truthy value, CQL will continue
    executing.
-   Should the handler return a falsy value, CQL will stop executing

Introduction
------------

Represents a single counter object.

Class synopsis
--------------

**Counter**

<span class="ooclass"> class **Counter**</span> {

<span class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$initial_value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \]\] )

<span class="type">int</span> <span class="methodname">getValue</span> (
<span class="methodparam">void</span> )

<span class="methodname">bumpValue</span> ( <span
class="methodparam"><span class="type">int</span> `$offset`</span> )

<span class="type">void</span> <span
class="methodname">resetValue</span> ( <span
class="methodparam">void</span> )

<span class="type">mixed</span> <span class="methodname">getMeta</span>
( <span class="methodparam"><span class="type">int</span>
`$attribute`</span> )

<span class="modifier">static</span> <span class="type">Counter</span>
<span class="methodname">getNamed</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">static</span> <span class="type">void</span>
<span class="methodname">setCounterClass</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

}

**Table of Contents**

-   [Counter::\_\_construct](/internals2/counter/counter-class/construct.html)
    — Creates an instance of a Counter which maintains a single numeric
    value
-   [Counter::getValue](/internals2/counter/counter-class/getvalue.html)
    — Get the current value of a counter
-   [Counter::bumpValue](/internals2/counter/counter-class/bumpvalue.html)
    — Change the current value of a counter
-   [Counter::resetValue](/internals2/counter/counter-class/resetvalue.html)
    — Reset the current value of a counter
-   [Counter::getMeta](/internals2/counter/counter-class/getmeta.html) —
    Return a piece of metainformation about a counter
-   [Counter::getNamed](/internals2/counter/counter-class/getnamed.html)
    — Retrieve an existing named counter
-   [Counter::setCounterClass](/internals2/counter/counter-class/setcounterclass.html)
    — Set the class returned by Counter::getNamed

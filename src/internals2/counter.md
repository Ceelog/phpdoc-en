The "counter" Extension - A Continuing Example
==============================================

**Table of Contents**

-   [Installing/Configuring](/internals2/counter/setup.html)
    -   [Introduction](/internals2/counter/intro.html)
    -   [Runtime Configuration](/internals2/counter/ini.html)
    -   [Resource Types](/internals2/counter/resources.html)
-   [Predefined Constants](/internals2/counter/constants.html)
-   [Examples](/internals2/counter/examples.html)
    -   [Basic interface](/internals2/counter/examples/basic.html)
    -   [Extended interface](/internals2/counter/examples/extended.html)
    -   [Objective
        interface](/internals2/counter/examples/objective.html)
-   [Counter](/internals2/counter/counter-class.html) — The Counter
    class
    -   [Counter::\_\_construct](/internals2/counter/counter-class/construct.html)
        — Creates an instance of a Counter which maintains a single
        numeric value
    -   [Counter::getValue](/internals2/counter/counter-class/getvalue.html)
        — Get the current value of a counter
    -   [Counter::bumpValue](/internals2/counter/counter-class/bumpvalue.html)
        — Change the current value of a counter
    -   [Counter::resetValue](/internals2/counter/counter-class/resetvalue.html)
        — Reset the current value of a counter
    -   [Counter::getMeta](/internals2/counter/counter-class/getmeta.html)
        — Return a piece of metainformation about a counter
    -   [Counter::getNamed](/internals2/counter/counter-class/getnamed.html)
        — Retrieve an existing named counter
    -   [Counter::setCounterClass](/internals2/counter/counter-class/setcounterclass.html)
        — Set the class returned by Counter::getNamed
-   [Basic](/internals2/counter/basic-interface.html) — The basic
    interface
    -   [counter\_get](/internals2/counter/function/counter-get.html) —
        Get the current value of the basic counter
    -   [counter\_bump](/internals2/counter/function/counter-bump.html)
        — Update the current value of the basic counter
    -   [counter\_reset](/internals2/counter/function/counter-reset.html)
        — Reset the current value of the basic counter
-   [Extended](/internals2/counter/extended-interface.html) — The
    extended interface
    -   [counter\_create](/internals2/counter/function/counter-create.html)
        — Creates a counter which maintains a single numeric value
    -   [counter\_get\_value](/internals2/counter/function/counter-get-value.html)
        — Get the current value of a counter resource
    -   [counter\_bump\_value](/internals2/counter/function/counter-bump-value.html)
        — Change the current value of a counter resource
    -   [counter\_reset\_value](/internals2/counter/function/counter-reset-value.html)
        — Reset the current value of a counter resource
    -   [counter\_get\_meta](/internals2/counter/function/counter-get-meta.html)
        — Return a piece of metainformation about a counter resource
    -   [counter\_get\_named](/internals2/counter/function/counter-get-named.html)
        — Retrieve an existing named counter as a resource

Throughout this Zend documentation, references are made to an example
module in order to illustrate various concepts. The "counter" extension
is this example, a fictional yet functional Zend module which strives to
use as much of the Zend API as is reasonably possible. This short
chapter describes the userland interface to the completed extension.

> **Note**: <span class="simpara"> "counter" serves no practical purpose
> whatsoever, as the functionality it provides is far more effectively
> implemented by appropriate userland code. </span>

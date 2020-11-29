V8 Javascript Engine Integration
================================

**Table of Contents**

-   [Introduction](/intro/v8js.html)
-   [Installing/Configuring](/v8js/setup.html)
    -   [Requirements](/v8js/setup.html#Requirements)
    -   [Installation](/v8js/setup.html#Installation)
    -   [Runtime
        Configuration](/v8js/setup.html#Runtime%20Configuration)
    -   [Resource Types](/v8js/setup.html#Resource%20Types)
-   [Examples](/v8js/examples.html)
-   [V8Js](/class/v8js.html) — The V8Js class
    -   [V8Js::\_\_construct](/class/v8js.html#V8Js::__construct) —
        Construct a new V8Js object
    -   [V8Js::executeString](/class/v8js.html#V8Js::executeString) —
        Execute a string as Javascript code
    -   [V8Js::getExtensions](/class/v8js.html#V8Js::getExtensions) —
        Return an array of registered extensions
    -   [V8Js::getPendingException](/class/v8js.html#V8Js::getPendingException)
        — Return pending uncaught Javascript exception
    -   [V8Js::registerExtension](/class/v8js.html#V8Js::registerExtension)
        — Register Javascript extensions for V8Js
-   [V8JsException](/class/v8jsexception.html) — The V8JsException class
    -   [V8JsException::getJsFileName](/class/v8jsexception.html#V8JsException::getJsFileName)
        — The getJsFileName purpose
    -   [V8JsException::getJsLineNumber](/class/v8jsexception.html#V8JsException::getJsLineNumber)
        — The getJsLineNumber purpose
    -   [V8JsException::getJsSourceLine](/class/v8jsexception.html#V8JsException::getJsSourceLine)
        — The getJsSourceLine purpose
    -   [V8JsException::getJsTrace](/class/v8jsexception.html#V8JsException::getJsTrace)
        — The getJsTrace purpose

Introduction
------------

This is the core class for V8Js extension. Each instance created from
this class has own context in which all JavaScript is compiled and
executed.

See <span class="function">V8Js::\_\_construct</span> for more
information.

Class synopsis
--------------

**V8Js**

<span class="ooclass"> class **V8Js** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`V8Js::V8_VERSION` ;

<span class="modifier">const</span> <span class="type">int</span>
`V8Js::FLAG_NONE` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`V8Js::FLAG_FORCE_ARRAY` <span class="initializer"> = 2</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$object_name`<span
class="initializer"> = "PHP"</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$variables`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$extensions`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$report_uncaught_exceptions`<span class="initializer"> =
**`TRUE`**</span></span> \]\]\]\] )

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">executeString</span> ( <span
class="methodparam"><span class="type">string</span> `$script`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$identifier`<span class="initializer"> =
"V8Js::executeString()"</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = **`V8Js::FLAG_NONE`**</span></span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getExtensions</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">V8JsException</span> <span
class="methodname">getPendingException</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">registerExtension</span> ( <span
class="methodparam"><span class="type">string</span>
`$extension_name`</span> , <span class="methodparam"><span
class="type">string</span> `$script`</span> \[, <span
class="methodparam"><span class="type">array</span> `$dependencies`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$auto_enable`<span
class="initializer"> = **`FALSE`**</span></span> \]\] )

}

Predefined Constants
--------------------

**`V8Js::V8_VERSION`**  
The V8 Javascript Engine version.

**`V8Js::FLAG_NONE`**  
No flags.

**`V8Js::FLAG_FORCE_ARRAY`**  
Forces all JS objects to be associative arrays in PHP.

V8Js::\_\_construct
===================

Construct a new <span class="classname">V8Js</span> object

### Description

<span class="modifier">public</span> <span
class="methodname">V8Js::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$object_name`<span
class="initializer"> = "PHP"</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$variables`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">array</span> `$extensions`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">bool</span>
`$report_uncaught_exceptions`<span class="initializer"> =
**`TRUE`**</span></span> \]\]\]\] )

Constructs a new <span class="classname">V8Js</span> object.

### Parameters

`object_name`  
The name of the object passed to Javascript.

`variables`  
Map of PHP variables that will be available in Javascript. Must be an
associative <span class="type">array</span> in format
*array("name-for-js" =\> "name-of-php-variable")*. Defaults to empty
array.

`extensions`  
List of extensions registered using <span
class="function">V8Js::registerExtension</span> which should be
available in the Javascript context of the created <span
class="classname">V8Js</span> object.

> **Note**:
>
> Extensions registered to be enabled automatically do not need to be
> listed in this array. Also if an extension has dependencies, those
> dependencies can be omitted as well. Defaults to empty array.

`report_uncaught_exceptions`  
Controls whether uncaught Javascript exceptions are reported immediately
or not. Defaults to **`TRUE`**. If set to **`FALSE`** the uncaught
exception can be accessed using <span
class="function">V8Js::getPendingException</span>.

### Return Values

Returns a new V8Js context object.

V8Js::executeString
===================

Execute a string as Javascript code

### Description

<span class="modifier">public</span> <span class="type">mixed</span>
<span class="methodname">V8Js::executeString</span> ( <span
class="methodparam"><span class="type">string</span> `$script`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$identifier`<span class="initializer"> =
"V8Js::executeString()"</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = **`V8Js::FLAG_NONE`**</span></span> \]\] )

Compiles and executes the string passed with `script` as Javascript
code.

### Parameters

`script`  
The code string to be executed.

`identifier`  
Identifier string for the executed code. Used for debugging.

`flags`  
Execution flags. This value must be one of the *V8Js::FLAG\_\**
constants, defaulting to **`V8Js::FLAG_NONE`**.

-   **`V8Js::FLAG_NONE`**: no flags

-   **`V8Js::FLAG_FORCE_ARRAY`**: forces all Javascript objects passed
    to PHP to be associative arrays

### Return Values

Returns the last variable instantiated in the Javascript code converted
to matching PHP variable type.

V8Js::getExtensions
===================

Return an array of registered extensions

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">V8Js::getExtensions</span> ( <span
class="methodparam">void</span> )

This function returns array of Javascript extensions registered using
<span class="function">V8Js::registerExtension</span>.

### Parameters

This function has no parameters.

### Return Values

Returns an array of registered extensions or an empty array if there are
none.

V8Js::getPendingException
=========================

Return pending uncaught Javascript exception

### Description

<span class="modifier">public</span> <span
class="type">V8JsException</span> <span
class="methodname">V8Js::getPendingException</span> ( <span
class="methodparam">void</span> )

Returns any pending uncaught Javascript exception as <span
class="classname">V8JsException</span> left from earlier <span
class="function">V8Js::executeString</span> call(s).

### Parameters

This function has no parameters.

### Return Values

Either <span class="classname">V8JsException</span> or **`NULL`**.

V8Js::registerExtension
=======================

Register Javascript extensions for V8Js

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">V8Js::registerExtension</span> ( <span
class="methodparam"><span class="type">string</span>
`$extension_name`</span> , <span class="methodparam"><span
class="type">string</span> `$script`</span> \[, <span
class="methodparam"><span class="type">array</span> `$dependencies`<span
class="initializer"> = array()</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$auto_enable`<span
class="initializer"> = **`FALSE`**</span></span> \]\] )

Registers passed Javascript `script` as extension to be used in <span
class="classname">V8Js</span> contexts.

### Parameters

`extension_name`  
Name of the extension to be registered.

`script`  
The Javascript code to be registered.

`dependencies`  
Array of extension names the extension to be registered depends on. Any
such extension is enabled automatically when this extension is loaded.

> **Note**:
>
> All extensions, including the dependencies, must be registered before
> any <span class="classname">V8Js</span> are created which use them.

`auto_enable`  
If set to **`TRUE`**, the extension will be enabled automatically in all
<span class="classname">V8Js</span> contexts.

### Return Values

Returns **`TRUE`** if extension was registered successfully, **`FALSE`**
otherwise.

Introduction
------------

Class synopsis
--------------

**V8JsException**

<span class="ooclass"> class **V8JsException** </span> <span
class="ooclass"> <span class="modifier">extends</span> **Exception**
</span> {

/\* Properties \*/

<span class="modifier">protected</span> `$JsFileName` ;

<span class="modifier">protected</span> `$JsLineNumber` ;

<span class="modifier">protected</span> `$JsSourceLine` ;

<span class="modifier">protected</span> `$JsTrace` ;

/\* Inherited properties \*/

<span class="modifier">protected</span> <span class="type">string</span>
`$message` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$code` ;

<span class="modifier">protected</span> <span class="type">string</span>
`$file` ;

<span class="modifier">protected</span> <span class="type">int</span>
`$line` ;

/\* Methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">getJsFileName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">getJsLineNumber</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">getJsSourceLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">getJsTrace</span> ( <span
class="methodparam">void</span> )

/\* Inherited methods \*/

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getMessage</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">Throwable</span> <span
class="methodname">Exception::getPrevious</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">mixed</span> <span
class="methodname">Exception::getCode</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getFile</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">Exception::getLine</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">array</span> <span
class="methodname">Exception::getTrace</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">Exception::getTraceAsString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">Exception::\_\_toString</span> ( <span
class="methodparam">void</span> )

<span class="modifier">final</span> <span
class="modifier">private</span> <span class="type">void</span> <span
class="methodname">Exception::\_\_clone</span> ( <span
class="methodparam">void</span> )

}

Properties
----------

`JsFileName`  

`JsLineNumber`  

`JsSourceLine`  

`JsTrace`  

V8JsException::getJsFileName
============================

The getJsFileName purpose

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">V8JsException::getJsFileName</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

V8JsException::getJsLineNumber
==============================

The getJsLineNumber purpose

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">int</span> <span
class="methodname">V8JsException::getJsLineNumber</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

V8JsException::getJsSourceLine
==============================

The getJsSourceLine purpose

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">V8JsException::getJsSourceLine</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

V8JsException::getJsTrace
=========================

The getJsTrace purpose

### Description

<span class="modifier">final</span> <span class="modifier">public</span>
<span class="type">string</span> <span
class="methodname">V8JsException::getJsTrace</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

This function has no parameters.

### Return Values

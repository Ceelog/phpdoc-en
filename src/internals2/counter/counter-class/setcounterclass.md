Counter::setCounterClass
========================

Set the class returned by <span
class="methodname">Counter::getNamed</span>

### Description

<span class="modifier">static</span> <span class="type">void</span>
<span class="methodname">Counter::setCounterClass</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="function">Counter::setCounterClass</span> changes the class
of objects returned by <span class="function">Counter::getNamed</span>.
The class being set must not have a public constructor and must be a
subclass of <span class="classname">Counter</span>. If these conditions
are not met, a fatal error is raised. This is a static function.

### Parameters

`name`  
<span class="simpara"> The name of the class to use. </span>

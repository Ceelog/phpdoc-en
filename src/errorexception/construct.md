ErrorException::\_\_construct
=============================

Constructs the exception

### Description

<span class="modifier">public</span> <span
class="methodname">ErrorException::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$message`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$code`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$severity`<span
class="initializer"> = E\_ERROR</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$filename`<span
class="initializer"> = \_\_FILE\_\_</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$lineno`<span
class="initializer"> = \_\_LINE\_\_</span></span> \[, <span
class="methodparam"><span class="type">Exception</span> `$previous`<span
class="initializer"> = **`NULL`**</span></span> \]\]\]\]\]\] )

Constructs the Exception.

### Parameters

`message`  
The Exception message to throw.

`code`  
The Exception code.

`severity`  
The severity level of the exception.

> **Note**:
>
> While the severity can be any <span class="type">integer</span> value,
> it is intended that the
> <a href="/errorfunc/constants.html" class="link">error constants</a>
> be used.

`filename`  
The filename where the exception is thrown.

`lineno`  
The line number where the exception is thrown.

`previous`  
The previous exception used for the exception chaining.

Error::\_\_construct
====================

Construct the error object

### Description

<span class="modifier">public</span> <span
class="methodname">Error::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$message`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$code`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">Throwable</span> `$previous`<span
class="initializer"> = **`null`**</span></span> \]\]\] )

Constructs the Error.

### Parameters

`message`  
The error message.

`code`  
The error code.

`previous`  
The previous throwable used for the exception chaining.

### Notes

> **Note**:
>
> The `message` is *NOT* binary safe.

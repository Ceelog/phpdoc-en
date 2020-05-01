Exception::\_\_construct
========================

Construct the exception

### Description

<span class="modifier">public</span> <span
class="methodname">Exception::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$message`<span
class="initializer"> = ""</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$code`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">Throwable</span> `$previous`<span
class="initializer"> = **`NULL`**</span></span> \]\]\] )

Constructs the Exception.

### Parameters

`message`  
The Exception message to throw.

`code`  
The Exception code.

`previous`  
The previous exception used for the exception chaining.

> **Note**: <span class="simpara"> Calling the constructor of class
> Exception from a subclass ignores the default arguments, if the
> properties $code and $message are already set. </span>

### Changelog

| Version | Description                                                                  |
|---------|------------------------------------------------------------------------------|
| 7.0.0   | The `previous` parameter is now of type <span class="type">Throwable</span>. |
| 5.3.0   | The `previous` parameter was added.                                          |

### Notes

> **Note**:
>
> The `message` is *NOT* binary safe.

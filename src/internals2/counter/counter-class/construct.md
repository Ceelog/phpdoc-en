Counter::\_\_construct
======================

Creates an instance of a Counter which maintains a single numeric value

### Description

<span class="methodname">Counter::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$initial_value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \]\] )

Creates an instance of a Counter which maintains a single numeric value.

### Parameters

name  
<span class="simpara"> The new counter's name. </span>

initial\_value  
<span class="simpara"> The initial value of the counter. Defaults to
zero (0). </span>

flags  
<span class="simpara"> Flags for the new counter, chosen from the
*COUNTER\_FLAG\_\** constants. </span>

### Return Values

Returns a Counter object on success.

### Errors/Exceptions

<span class="function">Counter::\_\_construct</span> throws an Exception
if something goes wrong.

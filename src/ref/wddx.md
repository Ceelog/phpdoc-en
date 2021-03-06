wddx\_add\_vars
===============

Add variables to a WDDX packet with the specified ID

**Warning**

This function was *REMOVED* in PHP 7.4.0.

### Description

<span class="type">bool</span> <span
class="methodname">wddx\_add\_vars</span> ( <span
class="methodparam"><span class="type">resource</span>
`$packet_id`</span> , <span class="methodparam"><span
class="type">mixed</span> `$var_name`</span> , <span
class="methodparam"><span class="type">mixed</span> `$var_names`</span>
)

Serializes the passed variables and add the result to the given packet.

### Parameters

This function takes a variable number of parameters.

`packet_id`  
A WDDX packet, returned by <span
class="function">wddx\_packet\_start</span>.

`var_name`  
Can be either a string naming a variable or an array containing strings
naming the variables or another array, etc.

`var_names`  

### Return Values

Returns **`true`** on success or **`false`** on failure.

wddx\_deserialize
=================

Unserializes a WDDX packet

**Warning**

This function was *REMOVED* in PHP 7.4.0.

### Description

<span class="type">mixed</span> <span
class="methodname">wddx\_deserialize</span> ( <span
class="methodparam"><span class="type">string</span> `$packet`</span> )

Unserializes a WDDX `packet`.

**Warning**

Do not pass untrusted user input to <span
class="function">wddx\_deserialize</span>. Unserialization can result in
code being loaded and executed due to object instantiation and
autoloading, and a malicious user may be able to exploit this. Use a
safe, standard data interchange format such as JSON (via <span
class="function">json\_decode</span> and <span
class="function">json\_encode</span>) if you need to pass serialized
data to the user.

### Parameters

`packet`  
A WDDX packet, as a string or stream.

### Return Values

Returns the deserialized value which can be a string, a number or an
array. Note that structures are deserialized into associative arrays.

wddx\_packet\_end
=================

Ends a WDDX packet with the specified ID

**Warning**

This function was *REMOVED* in PHP 7.4.0.

### Description

<span class="type">string</span> <span
class="methodname">wddx\_packet\_end</span> ( <span
class="methodparam"><span class="type">resource</span>
`$packet_id`</span> )

Ends and returns the given WDDX packet.

### Parameters

`packet_id`  
A WDDX packet, returned by <span
class="function">wddx\_packet\_start</span>.

### Return Values

Returns the string containing the WDDX packet.

wddx\_packet\_start
===================

Starts a new WDDX packet with structure inside it

**Warning**

This function was *REMOVED* in PHP 7.4.0.

### Description

<span class="type">resource</span> <span
class="methodname">wddx\_packet\_start</span> (\[ <span
class="methodparam"><span class="type">string</span> `$comment`</span>
\] )

Start a new WDDX packet for incremental addition of variables. It
automatically creates a structure definition inside the packet to
contain the variables.

### Parameters

`comment`  
An optional comment string.

### Return Values

Returns a packet ID for use in later functions, or **`false`** on error.

wddx\_serialize\_value
======================

Serialize a single value into a WDDX packet

**Warning**

This function was *REMOVED* in PHP 7.4.0.

### Description

<span class="type">string</span> <span
class="methodname">wddx\_serialize\_value</span> ( <span
class="methodparam"><span class="type">mixed</span> `$var`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$comment`</span> \] )

Creates a WDDX packet from a single given value.

### Parameters

`var`  
The value to be serialized

`comment`  
An optional comment string that appears in the packet header.

### Return Values

Returns the WDDX packet, or **`false`** on error.

wddx\_serialize\_vars
=====================

Serialize variables into a WDDX packet

**Warning**

This function was *REMOVED* in PHP 7.4.0.

### Description

<span class="type">string</span> <span
class="methodname">wddx\_serialize\_vars</span> ( <span
class="methodparam"><span class="type">mixed</span> `$var_name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$var_names`</span> )

Creates a WDDX packet with a structure that contains the serialized
representation of the passed variables.

### Parameters

This function takes a variable number of parameters.

`var_name`  
Can be either a string naming a variable or an array containing strings
naming the variables or another array, etc.

`var_names`  

### Return Values

Returns the WDDX packet, or **`false`** on error.

### Examples

**Example \#1 <span class="function">wddx\_serialize\_vars</span>
example**

``` php
<?php
$a = 1;
$b = 5.5;
$c = array("blue", "orange", "violet");
$d = "colors";

$clvars = array("c", "d");
echo wddx_serialize_vars("a", "b", $clvars);
?>
```

The above example will output:

    <wddxPacket version='1.0'><header/><data><struct><var name='a'><number>1</number></var>
    <var name='b'><number>5.5</number></var><var name='c'><array length='3'>
    <string>blue</string><string>orange</string><string>violet</string></array></var>
    <var name='d'><string>colors</string></var></struct></data></wddxPacket>

**Table of Contents**

-   [wddx\_add\_vars](/ref/wddx.html#wddx_add_vars) — Add variables to a
    WDDX packet with the specified ID
-   [wddx\_deserialize](/ref/wddx.html#wddx_deserialize) — Unserializes
    a WDDX packet
-   [wddx\_packet\_end](/ref/wddx.html#wddx_packet_end) — Ends a WDDX
    packet with the specified ID
-   [wddx\_packet\_start](/ref/wddx.html#wddx_packet_start) — Starts a
    new WDDX packet with structure inside it
-   [wddx\_serialize\_value](/ref/wddx.html#wddx_serialize_value) —
    Serialize a single value into a WDDX packet
-   [wddx\_serialize\_vars](/ref/wddx.html#wddx_serialize_vars) —
    Serialize variables into a WDDX packet

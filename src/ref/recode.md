recode\_file
============

Recode from file to file according to recode request

### Description

<span class="type">bool</span> <span
class="methodname">recode\_file</span> ( <span class="methodparam"><span
class="type">string</span> `$request`</span> , <span
class="methodparam"><span class="type">resource</span> `$input`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$output`</span> )

Recode the file referenced by file handle `input` into the file
referenced by file handle `output` according to the recode `request`.

### Parameters

`request`  
The desired recode request type

`input`  
A local file handle <span class="type">resource</span> for the `input`

`output`  
A local file handle <span class="type">resource</span> for the `output`

### Return Values

Returns **`FALSE`**, if unable to comply, **`TRUE`** otherwise.

### Examples

**Example \#1 Basic <span class="function">recode\_file</span> example**

``` php
<?php
$input = fopen('input.txt', 'r');
$output = fopen('output.txt', 'w');
recode_file("us..flat", $input, $output);
?>
```

### Notes

This function does not currently process file handles referencing remote
files (URLs). Both file handles must refer to local files.

### See Also

-   <span class="function">fopen</span>

recode\_string
==============

Recode a string according to a recode request

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">recode\_string</span> ( <span
class="methodparam"><span class="type">string</span> `$request`</span> ,
<span class="methodparam"><span class="type">string</span>
`$string`</span> )

Recode the string `string` according to the recode request `request`.

### Parameters

`request`  
The desired recode request type

`string`  
The <span class="type">string</span> to be recoded

### Return Values

Returns the recoded <span class="type">string</span> or **`FALSE`**, if
unable to perform the recode request.

### Examples

**Example \#1 Basic <span class="function">recode\_string</span>
example**

``` php
<?php
echo recode_string("us..flat", "The following character has a diacritical mark: á");
?>
```

### Notes

A simple recode request may be "lat1..iso646-de".

### See Also

-   The GNU Recode documentation of your installation for detailed
    instructions about recode requests.

recode
======

Alias of <span class="function">recode\_string</span>

### Description

This function is an alias of: <span
class="function">recode\_string</span>.

**Table of Contents**

-   [recode\_file](/ref/recode.html#recode_file) — Recode from file to
    file according to recode request
-   [recode\_string](/ref/recode.html#recode_string) — Recode a string
    according to a recode request
-   [recode](/ref/recode.html#recode) — Alias of recode\_string

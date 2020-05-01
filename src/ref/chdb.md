chdb\_create
============

Creates a chdb file

### Description

<span class="type">bool</span> <span
class="methodname">chdb\_create</span> ( <span class="methodparam"><span
class="type">string</span> `$pathname`</span> , <span
class="methodparam"><span class="type">array</span> `$data`</span> )

<span class="function">chdb\_create</span> creates a chdb file
containing the specified key-value pairs.

> **Note**:
>
> chdb files are not portable across little-endian and big-endian
> environments. Except for that, they are portable across different
> architectures. Also compatibility across different versions of chdb is
> not guaranteed.

### Parameters

`pathname`  
The name of the file to create.

If a file with the same name already exists, it is overwritten.

`data`  
An array containing the key-value pairs to store in the chdb file.

Keys and values are converted to strings before being written to the
file, as chdb only support the string type. Note that binary strings are
supported as well, both as keys and values.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Errors/Exceptions

Throws an exception in case the chdb file hasn't been successfully
created.

### Examples

**Example \#1 <span class="function">chdb\_create</span> example**

``` php
<?php

$data = array(
    'key1' => 'value1',
    'key2' => 'value2',
    // ...
);
chdb_create('data.chdb', $data);

?>
```

The above example will generate a chdb file named *data.chdb* and
containing the key-value pairs defined in `$data`.

**Table of Contents**

-   [chdb\_create](/ref/chdb.html#chdb_create) — Creates a chdb file

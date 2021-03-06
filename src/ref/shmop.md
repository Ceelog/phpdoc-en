shmop\_close
============

Close shared memory block

### Description

<span class="type">void</span> <span
class="methodname">shmop\_close</span> ( <span class="methodparam"><span
class="type">Shmop</span> `$shmop`</span> )

<span class="function">shmop\_close</span> is used to close a shared
memory block.

### Parameters

`shmop`  
The shared memory block resource created by <span
class="function">shmop\_open</span>

### Return Values

No value is returned.

### Changelog

| Version | Description                                                                                                                         |
|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `shmop` expects a <span class="classname">Shmop</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Closing shared memory block**

``` php
<?php
shmop_close($shm_id);
?>
```

This example will close shared memory block identified by *$shm\_id*.

### See Also

-   <span class="function">shmop\_open</span>

shmop\_delete
=============

Delete shared memory block

### Description

<span class="type">bool</span> <span
class="methodname">shmop\_delete</span> ( <span
class="methodparam"><span class="type">Shmop</span> `$shmop`</span> )

<span class="function">shmop\_delete</span> is used to delete a shared
memory block.

### Parameters

`shmop`  
The shared memory block resource created by <span
class="function">shmop\_open</span>

### Return Values

Returns **`true`** on success or **`false`** on failure.

### Changelog

| Version | Description                                                                                                                         |
|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `shmop` expects a <span class="classname">Shmop</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Deleting shared memory block**

``` php
<?php
shmop_delete($shm_id);
?>
```

This example will delete shared memory block identified by *$shm\_id*.

shmop\_open
===========

Create or open shared memory block

### Description

<span class="type"><span class="type">Shmop</span><span
class="type">false</span></span> <span
class="methodname">shmop\_open</span> ( <span class="methodparam"><span
class="type">int</span> `$key`</span> , <span class="methodparam"><span
class="type">string</span> `$mode`</span> , <span
class="methodparam"><span class="type">int</span> `$permissions`</span>
, <span class="methodparam"><span class="type">int</span> `$size`</span>
)

<span class="function">shmop\_open</span> can create or open a shared
memory block.

### Parameters

`key`  
System's id for the shared memory block. Can be passed as a decimal or
hex.

`mode`  
The flags that you can use:

-   <span class="simpara"> "a" for access (sets SHM\_RDONLY for shmat)
    use this flag when you need to open an existing shared memory
    segment for read only </span>
-   <span class="simpara"> "c" for create (sets IPC\_CREATE) use this
    flag when you need to create a new shared memory segment or if a
    segment with the same key exists, try to open it for read and write
    </span>
-   <span class="simpara"> "w" for read & write access use this flag
    when you need to read and write to a shared memory segment, use this
    flag in most cases. </span>
-   <span class="simpara"> "n" create a new memory segment (sets
    IPC\_CREATE\|IPC\_EXCL) use this flag when you want to create a new
    shared memory segment but if one already exists with the same flag,
    fail. This is useful for security purposes, using this you can
    prevent race condition exploits. </span>

`permissions`  
The permissions that you wish to assign to your memory segment, those
are the same as permission for a file. Permissions need to be passed in
octal form, like for example *0644*

`size`  
The size of the shared memory block you wish to create in bytes

> **Note**:
>
> Note: the 3rd and 4th should be entered as 0 if you are opening an
> existing memory segment.

### Return Values

On success <span class="function">shmop\_open</span> will return a <span
class="classname">Shmop</span> instance that you can use to access the
shared memory segment you've created. **`false`** is returned on
failure.

### Changelog

| Version | Description                                                                                                                                            |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | On success, this function returns an <span class="classname">Shmop</span> instance now; previously, a <span class="type">resource</span> was returned. |

### Examples

**Example \#1 Create a new shared memory block**

``` php
<?php
$shm_key = ftok(__FILE__, 't');
$shm_id = shmop_open($shm_key, "c", 0644, 100);
?>
```

This example opened a shared memory block with a system id returned by
<span class="function">ftok</span>.

### See Also

-   <span class="function">shmop\_close</span>
-   <span class="function">shmop\_delete</span>

shmop\_read
===========

Read data from shared memory block

### Description

<span class="type">string</span> <span
class="methodname">shmop\_read</span> ( <span class="methodparam"><span
class="type">Shmop</span> `$shmop`</span> , <span
class="methodparam"><span class="type">int</span> `$offset`</span> ,
<span class="methodparam"><span class="type">int</span> `$size`</span> )

<span class="function">shmop\_read</span> will read a string from shared
memory block.

### Parameters

`shmop`  
The shared memory block identifier created by <span
class="function">shmop\_open</span>

`offset`  
Offset from which to start reading

`size`  
The number of bytes to read. *0* reads `shmop_size($shmid) - $start`
bytes.

### Return Values

Returns the data or **`false`** on failure.

### Changelog

| Version | Description                                                                                                                         |
|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `shmop` expects a <span class="classname">Shmop</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Reading shared memory block**

``` php
<?php
$shm_data = shmop_read($shm_id, 0, 50);
?>
```

This example will read 50 bytes from shared memory block and place the
data inside *$shm\_data*.

### See Also

-   <span class="function">shmop\_write</span>

shmop\_size
===========

Get size of shared memory block

### Description

<span class="type">int</span> <span
class="methodname">shmop\_size</span> ( <span class="methodparam"><span
class="type">Shmop</span> `$shmop`</span> )

<span class="function">shmop\_size</span> is used to get the size, in
bytes of the shared memory block.

### Parameters

`shmop`  
The shared memory block identifier created by <span
class="function">shmop\_open</span>

### Return Values

Returns an int, which represents the number of bytes the shared memory
block occupies.

### Changelog

| Version | Description                                                                                                                         |
|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | `shmop` expects a <span class="classname">Shmop</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Getting the size of the shared memory block**

``` php
<?php
$shm_size = shmop_size($shm_id);
?>
```

This example will put the size of shared memory block identified by
*$shm\_id* into *$shm\_size*.

shmop\_write
============

Write data into shared memory block

### Description

<span class="type">int</span> <span
class="methodname">shmop\_write</span> ( <span class="methodparam"><span
class="type">Shmop</span> `$shmop`</span> , <span
class="methodparam"><span class="type">string</span> `$data`</span> ,
<span class="methodparam"><span class="type">int</span> `$offset`</span>
)

<span class="function">shmop\_write</span> will write a string into
shared memory block.

### Parameters

`shmop`  
The shared memory block identifier created by <span
class="function">shmop\_open</span>

`data`  
A string to write into shared memory block

`offset`  
Specifies where to start writing data inside the shared memory segment.

### Return Values

The size of the written `data`.

### Changelog

| Version | Description                                                                                                                         |
|---------|-------------------------------------------------------------------------------------------------------------------------------------|
| 8.0.0   | Prior to PHP 8.0.0, **`false`** was returned on failure.                                                                            |
| 8.0.0   | `shmop` expects a <span class="classname">Shmop</span> instance now; previously, a <span class="type">resource</span> was expected. |

### Examples

**Example \#1 Writing to shared memory block**

``` php
<?php
$shm_bytes_written = shmop_write($shm_id, $my_string, 0);
?>
```

This example will write data inside *$my\_string* into shared memory
block, *$shm\_bytes\_written* will contain the number of bytes written.

### See Also

-   <span class="function">shmop\_read</span>

**Table of Contents**

-   [shmop\_close](/ref/shmop.html#shmop_close) — Close shared memory
    block
-   [shmop\_delete](/ref/shmop.html#shmop_delete) — Delete shared memory
    block
-   [shmop\_open](/ref/shmop.html#shmop_open) — Create or open shared
    memory block
-   [shmop\_read](/ref/shmop.html#shmop_read) — Read data from shared
    memory block
-   [shmop\_size](/ref/shmop.html#shmop_size) — Get size of shared
    memory block
-   [shmop\_write](/ref/shmop.html#shmop_write) — Write data into shared
    memory block

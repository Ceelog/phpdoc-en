Examples
========

This example opens a temporary file and writes a test string to it, then
prints out the contents of the file.

**Example \#1 Small bzip2 Example**

``` php
<?php

$filename = "/tmp/testfile.bz2";
$str = "This is a test string.\n";

// open file for writing
$bz = bzopen($filename, "w");

// write string to file
bzwrite($bz, $str);

// close file
bzclose($bz);

// open file for reading
$bz = bzopen($filename, "r");

// read 10 characters
echo bzread($bz, 10);

// output until end of the file (or the next 1024 char) and close it.  
echo bzread($bz);

bzclose($bz);

?>
```

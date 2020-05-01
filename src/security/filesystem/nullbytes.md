Null bytes related issues
-------------------------

As PHP uses the underlying C functions for filesystem related
operations, it may handle null bytes in a quite unexpected way. As null
bytes denote the end of a string in C, strings containing them won't be
considered entirely but rather only until a null byte occurs. The
following example shows a vulnerable code that demonstrates this
problem:

**Example \#1 Script vulnerable to null bytes**

``` php
<?php
$file = $_GET['file']; // "../../etc/passwd\0"
if (file_exists('/home/wwwrun/'.$file.'.php')) {
    // file_exists will return true as the file /home/wwwrun/../../etc/passwd exists
    include '/home/wwwrun/'.$file.'.php';
    // the file /etc/passwd will be included
}
?>
```

Therefore, any tainted string that is used in a filesystem operation
should always be validated properly. Here is a better version of the
previous example:

**Example \#2 Correctly validating the input**

``` php
<?php
$file = $_GET['file']; 

// Whitelisting possible values
switch ($file) {
    case 'main':
    case 'foo':
    case 'bar':
        include '/home/wwwrun/include/'.$file.'.php';
        break;
    default:
        include '/home/wwwrun/include/main.php';
}
?>
```

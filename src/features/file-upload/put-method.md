PUT method support
------------------

PHP provides support for the HTTP PUT method used by some clients to
store files on a server. PUT requests are much simpler than a file
upload using POST requests and they look something like this:

``` HTTP
PUT /path/filename.html HTTP/1.1
```

This would normally mean that the remote client would like to save the
content that follows as: `/path/filename.html` in your web tree. It is
obviously not a good idea for Apache or PHP to automatically let
everybody overwrite any files in your web tree. So, to handle such a
request you have to first tell your web server that you want a certain
PHP script to handle the request. In Apache you do this with the
*Script* directive. It can be placed almost anywhere in your Apache
configuration file. A common place is inside a *\<Directory\>* block or
perhaps inside a *\<VirtualHost\>* block. A line like this would do the
trick:

    Script PUT /put.php

This tells Apache to send all PUT requests for URIs that match the
context in which you put this line to the `put.php` script. This
assumes, of course, that you have PHP enabled for the `.php` extension
and PHP is active. The destination resource for all PUT requests to this
script has to be the script itself, not a filename the uploaded file
should have.

With PHP you would then do something like the following in your put.php.
This would copy the contents of the uploaded file to the file
`myputfile.ext` on the server. You would probably want to perform some
checks and/or authenticate the user before performing this file copy.

**Example \#1 Saving HTTP PUT files**

``` php
<?php
/* PUT data comes in on the stdin stream */
$putdata = fopen("php://input", "r");

/* Open a file for writing */
$fp = fopen("myputfile.ext", "w");

/* Read the data 1 KB at a time
   and write to the file */
while ($data = fread($putdata, 1024))
  fwrite($fp, $data);

/* Close the streams */
fclose($fp);
fclose($putdata);
?>
```

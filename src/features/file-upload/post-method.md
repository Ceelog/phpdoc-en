POST method uploads
-------------------

This feature lets people upload both text and binary files. With PHP's
authentication and file manipulation functions, you have full control
over who is allowed to upload and what is to be done with the file once
it has been uploaded.

PHP is capable of receiving file uploads from any RFC-1867 compliant
browser.

> **Note**: **Related Configurations Note**  
>
> See also the
> <a href="/ini/core.html#ini.file-uploads" class="link">file_uploads</a>,
> <a href="/ini/core.html#ini.upload-max-filesize" class="link">upload_max_filesize</a>,
> <a href="/ini/core.html#ini.upload-tmp-dir" class="link">upload_tmp_dir</a>,
> <a href="/ini/core.html#ini.post-max-size" class="link">post_max_size</a>
> and <a href="/info/setup.html#" class="link">max_input_time</a>
> directives in `php.ini`

PHP also supports PUT-method file uploads as used by <span
class="productname">Netscape Composer</span> and W3C's <span
class="productname">Amaya</span> clients. See the
<a href="/features/file-upload/put-method.html" class="link">PUT Method Support</a>
for more details.

**Example \#1 File Upload Form**

A file upload screen can be built by creating a special form which looks
something like this:

``` html
<!-- The data encoding type, enctype, MUST be specified as below -->
<form enctype="multipart/form-data" action="__URL__" method="POST">
    <!-- MAX_FILE_SIZE must precede the file input field -->
    <input type="hidden" name="MAX_FILE_SIZE" value="30000" />
    <!-- Name of input element determines name in $_FILES array -->
    Send this file: <input name="userfile" type="file" />
    <input type="submit" value="Send File" />
</form>
```

The *\_\_URL\_\_* in the above example should be replaced, and point to
a PHP file.

The *MAX\_FILE\_SIZE* hidden field (measured in bytes) must precede the
file input field, and its value is the maximum filesize accepted by PHP.
This form element should always be used as it saves users the trouble of
waiting for a big file being transferred only to find that it was too
large and the transfer failed. Keep in mind: fooling this setting on the
browser side is quite easy, so never rely on files with a greater size
being blocked by this feature. It is merely a convenience feature for
users on the client side of the application. The PHP settings (on the
server side) for maximum-size, however, cannot be fooled.

> **Note**:
>
> Be sure your file upload form has attribute
> *enctype="multipart/form-data"* otherwise the file upload will not
> work.

The global `$_FILES` will contain all the uploaded file information. Its
contents from the example form is as follows. Note that this assumes the
use of the file upload name *userfile*, as used in the example script
above. This can be any name.

`$_FILES['userfile']['name']`  
The original name of the file on the client machine.

`$_FILES['userfile']['type']`  
The mime type of the file, if the browser provided this information. An
example would be *"image/gif"*. This mime type is however not checked on
the PHP side and therefore don't take its value for granted.

`$_FILES['userfile']['size']`  
The size, in bytes, of the uploaded file.

`$_FILES['userfile']['tmp_name']`  
The temporary filename of the file in which the uploaded file was stored
on the server.

`$_FILES['userfile']['error']`  
The
<a href="/features/file-upload/errors.html" class="link">error code</a>
associated with this file upload.

Files will, by default be stored in the server's default temporary
directory, unless another location has been given with the
<a href="/ini/core.html#ini.upload-tmp-dir" class="link">upload_tmp_dir</a>
directive in `php.ini`. The server's default directory can be changed by
setting the environment variable `TMPDIR` in the environment in which
PHP runs. Setting it using <span class="function">putenv</span> from
within a PHP script will not work. This environment variable can also be
used to make sure that other operations are working on uploaded files,
as well.

**Example \#2 Validating file uploads**

See also the function entries for <span
class="function">is\_uploaded\_file</span> and <span
class="function">move\_uploaded\_file</span> for further information.
The following example will process the file upload that came from a
form.

``` php
<?php
$uploaddir = '/var/www/uploads/';
$uploadfile = $uploaddir . basename($_FILES['userfile']['name']);

echo '<pre>';
if (move_uploaded_file($_FILES['userfile']['tmp_name'], $uploadfile)) {
    echo "File is valid, and was successfully uploaded.\n";
} else {
    echo "Possible file upload attack!\n";
}

echo 'Here is some more debugging info:';
print_r($_FILES);

print "</pre>";

?>
```

The PHP script which receives the uploaded file should implement
whatever logic is necessary for determining what should be done with the
uploaded file. You can, for example, use the
`$_FILES['userfile']['size']` variable to throw away any files that are
either too small or too big. You could use the
`$_FILES['userfile']['type']` variable to throw away any files that
didn't match a certain type criteria, but use this only as first of a
series of checks, because this value is completely under the control of
the client and not checked on the PHP side. Also, you could use
`$_FILES['userfile']['error']` and plan your logic according to the
<a href="/features/file-upload/errors.html" class="link">error codes</a>.
Whatever the logic, you should either delete the file from the temporary
directory or move it elsewhere.

If no file is selected for upload in your form, PHP will return
`$_FILES['userfile']['size']` as 0, and
`$_FILES['userfile']['tmp_name']` as none.

The file will be deleted from the temporary directory at the end of the
request if it has not been moved away or renamed.

**Example \#3 Uploading array of files**

PHP supports
<a href="/faq/html.html#faq.html.arrays" class="link">HTML array feature</a>
even with files.

``` html
<form action="" method="post" enctype="multipart/form-data">
<p>Pictures:
<input type="file" name="pictures[]" />
<input type="file" name="pictures[]" />
<input type="file" name="pictures[]" />
<input type="submit" value="Send" />
</p>
</form>
```

``` php
<?php
foreach ($_FILES["pictures"]["error"] as $key => $error) {
    if ($error == UPLOAD_ERR_OK) {
        $tmp_name = $_FILES["pictures"]["tmp_name"][$key];
        // basename() may prevent filesystem traversal attacks;
        // further validation/sanitation of the filename may be appropriate
        $name = basename($_FILES["pictures"]["name"][$key]);
        move_uploaded_file($tmp_name, "data/$name");
    }
}
?>
```

File upload progress bar can be implemented using
<a href="/session/upload-progress.html" class="link">Session Upload Progress</a>.

Error Messages Explained
------------------------

PHP returns an appropriate error code along with the file array. The
error code can be found in the *error* segment of the file array that is
created during the file upload by PHP. In other words, the error might
be found in `$_FILES['userfile']['error']`.

**`UPLOAD_ERR_OK`**  
Value: 0; There is no error, the file uploaded with success.

**`UPLOAD_ERR_INI_SIZE`**  
Value: 1; The uploaded file exceeds the
<a href="/ini/core.html#ini.upload-max-filesize" class="link">upload_max_filesize</a>
directive in `php.ini`.

**`UPLOAD_ERR_FORM_SIZE`**  
Value: 2; The uploaded file exceeds the *MAX\_FILE\_SIZE* directive that
was specified in the HTML form.

**`UPLOAD_ERR_PARTIAL`**  
Value: 3; The uploaded file was only partially uploaded.

**`UPLOAD_ERR_NO_FILE`**  
Value: 4; No file was uploaded.

**`UPLOAD_ERR_NO_TMP_DIR`**  
Value: 6; Missing a temporary folder. Introduced in PHP 5.0.3.

**`UPLOAD_ERR_CANT_WRITE`**  
Value: 7; Failed to write file to disk. Introduced in PHP 5.1.0.

**`UPLOAD_ERR_EXTENSION`**  
Value: 8; A PHP extension stopped the file upload. PHP does not provide
a way to ascertain which extension caused the file upload to stop;
examining the list of loaded extensions with <span
class="function">phpinfo</span> may help. Introduced in PHP 5.2.0.

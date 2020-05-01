Uploading multiple files
------------------------

Multiple files can be uploaded using different *name* for *input*.

It is also possible to upload multiple files simultaneously and have the
information organized automatically in arrays for you. To do so, you
need to use the same array submission syntax in the HTML form as you do
with multiple selects and checkboxes:

**Example \#1 Uploading multiple files**

``` html
<form action="file-upload.php" method="post" enctype="multipart/form-data">
  Send these files:<br />
  <input name="userfile[]" type="file" /><br />
  <input name="userfile[]" type="file" /><br />
  <input type="submit" value="Send files" />
</form>
```

When the above form is submitted, the arrays `$_FILES['userfile']`,
`$_FILES['userfile']['name']`, and `$_FILES['userfile']['size']` will be
initialized. When
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
is on, globals for uploaded files are also initialized. Each of these
will be a numerically indexed array of the appropriate values for the
submitted files.

For instance, assume that the filenames `/home/test/review.html` and
`/home/test/xwp.out` are submitted. In this case,
`$_FILES['userfile']['name'][0]` would contain the value `review.html`,
and `$_FILES['userfile']['name'][1]` would contain the value `xwp.out`.
Similarly, `$_FILES['userfile']['size'][0]` would contain
`review.html`'s file size, and so forth.

`$_FILES['userfile']['name'][0]`, `$_FILES['userfile']['tmp_name'][0]`,
`$_FILES['userfile']['size'][0]`, and `$_FILES['userfile']['type'][0]`
are also set.

**Warning**

As of PHP 5.2.12, the
<a href="/ini/core.html#ini.max-file-uploads" class="link">max_file_uploads</a>
configuration setting acts as a limit on the number of files that can be
uploaded in one request. You will need to ensure that your form does not
try to upload more files in one request than this limit.

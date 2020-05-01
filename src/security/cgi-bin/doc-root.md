Case 3: setting doc\_root or user\_dir
--------------------------------------

To include active content, like scripts and executables, in the web
server document directories is sometimes considered an insecure
practice. If, because of some configuration mistake, the scripts are not
executed but displayed as regular HTML documents, this may result in
leakage of intellectual property or security information like passwords.
Therefore many sysadmins will prefer setting up another directory
structure for scripts that are accessible only through the PHP CGI, and
therefore always interpreted and not displayed as such.

Also if the method for making sure the requests are not redirected, as
described in the previous section, is not available, it is necessary to
set up a script doc\_root that is different from web document root.

You can set the PHP script document root by the configuration directive
<a href="/ini/core.html#ini.doc-root" class="link">doc_root</a> in the
<a href="/configuration/file.html" class="link">configuration file</a>,
or you can set the environment variable `PHP_DOCUMENT_ROOT`. If it is
set, the CGI version of PHP will always construct the file name to open
with this `doc_root` and the path information in the request, so you can
be sure no script is executed outside this directory (except for
`user_dir` below).

Another option usable here is
<a href="/ini/core.html#ini.user-dir" class="link">user_dir</a>. When
user\_dir is unset, only thing controlling the opened file name is
`doc_root`. Opening a URL like `http://my.host/~user/doc.php` does not
result in opening a file under users home directory, but a file called
`~user/doc.php` under doc\_root (yes, a directory name starting with a
tilde \[*\~*\]).

If user\_dir is set to for example `public_php`, a request like
`http://my.host/~user/doc.php` will open a file called `doc.php` under
the directory named `public_php` under the home directory of the user.
If the home of the user is `/home/user`, the file executed is
`/home/user/public_php/doc.php`.

`user_dir` expansion happens regardless of the `doc_root` setting, so
you can control the document root and user directory access separately.

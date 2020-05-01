Case 1: only public files served
--------------------------------

If your server does not have any content that is not restricted by
password or ip based access control, there is no need for these
configuration options. If your web server does not allow you to do
redirects, or the server does not have a way to communicate to the PHP
binary that the request is a safely redirected request, you can specify
the option
<a href="/configure/about.html#configure.enable-force-cgi-redirect" class="link">--enable-force-cgi-redirect</a>
to the configure script. You still have to make sure your PHP scripts do
not rely on one or another way of calling the script, neither by
directly `http://my.host/cgi-bin/php/dir/script.php` nor by redirection
`http://my.host/dir/script.php`.

Redirection can be configured in Apache by using AddHandler and Action
directives (see below).

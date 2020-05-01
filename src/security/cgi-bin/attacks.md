Possible attacks
----------------

Using PHP as a CGI binary is an option for setups that for some reason
do not wish to integrate PHP as a module into server software (like
Apache), or will use PHP with different kinds of CGI wrappers to create
safe chroot and setuid environments for scripts. This setup usually
involves installing executable PHP binary to the web server cgi-bin
directory. CERT advisory
<a href="http://www.cert.org/advisories/CA-1996-11.html" class="link external">» CA-96.11</a>
recommends against placing any interpreters into cgi-bin. Even if the
PHP binary can be used as a standalone interpreter, PHP is designed to
prevent the attacks this setup makes possible:

-   <span class="simpara"> Accessing system files:
    `http://my.host/cgi-bin/php?/etc/passwd` </span> <span
    class="simpara"> The query information in a URL after the question
    mark (?) is passed as command line arguments to the interpreter by
    the CGI interface. Usually interpreters open and execute the file
    specified as the first argument on the command line. </span> <span
    class="simpara"> When invoked as a CGI binary, PHP refuses to
    interpret the command line arguments. </span>
-   <span class="simpara"> Accessing any web document on server:
    `http://my.host/cgi-bin/php/secret/doc.html` </span> <span
    class="simpara"> The path information part of the URL after the PHP
    binary name, `/secret/doc.html` is conventionally used to specify
    the name of the file to be opened and interpreted by the CGI
    program. Usually some web server configuration directives (Apache:
    Action) are used to redirect requests to documents like
    `http://my.host/secret/script.php` to the PHP interpreter. With this
    setup, the web server first checks the access permissions to the
    directory `/secret`, and after that creates the redirected request
    `http://my.host/cgi-bin/php/secret/script.php`. Unfortunately, if
    the request is originally given in this form, no access checks are
    made by web server for file `/secret/script.php`, but only for the
    `/cgi-bin/php` file. This way any user able to access `/cgi-bin/php`
    is able to access any protected document on the web server. </span>
    <span class="simpara"> In PHP, runtime configuration directives
    <a href="/ini/core.html#ini.cgi.force-redirect" class="link">cgi.force_redirect</a>,
    <a href="/ini/core.html#ini.doc-root" class="link">doc_root</a> and
    <a href="/ini/core.html#ini.user-dir" class="link">user_dir</a> can
    be used to prevent this attack, if the server document tree has any
    directories with access restrictions. See below for full the
    explanation of the different combinations. </span>

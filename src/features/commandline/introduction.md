Introduction
------------

The main focus of CLI SAPI is for developing shell applications with
PHP. There are quite a few differences between the CLI SAPI and other
SAPIs which are explained in this chapter. It is worth mentioning that
CLI and CGI are different SAPIs although they do share many of the same
behaviors.

The CLI SAPI is enabled by default using **--enable-cli**, but may be
disabled using the **--disable-cli** option when running
**./configure**.

The name, location and existence of the CLI/CGI binaries will differ
depending on how PHP is installed on your system. By default when
executing **make**, both the CGI and CLI are built and placed as
`sapi/cgi/php-cgi` and `sapi/cli/php` respectively, in your PHP source
directory. You will note that both are named `php`. What happens during
**make install** depends on your configure line. If a module SAPI is
chosen during configure, such as apxs, or the **--disable-cgi** option
is used, the CLI is copied to `{PREFIX}/bin/php` during **make install**
otherwise the CGI is placed there. So, for example, if **--with-apxs**
is in your configure line then the CLI is copied to
`{PREFIX}/bin/php    ` during **make install**. If you want to override
the installation of the CGI binary, use **make install-cli** after
**make install**. Alternatively you can specify **--disable-cgi** in
your configure line.

> **Note**:
>
> Because both **--enable-cli** and **--enable-cgi** are enabled by
> default, simply having **--enable-cli** in your configure line does
> not necessarily mean the CLI will be copied as `{PREFIX}/bin/php`
> during **make install**.

As of PHP 5, the CLI binary is distributed in the main folder as
`    php.exe` on Windows. The CGI version is distributed as
`php-cgi.exe`. Additionally, a `    php-win.exe` is distributed if PHP
is configured using **--enable-cli-win32**. This does the same as the
CLI version, except that it doesn't output anything and thus provides no
console.

> **Note**: **What SAPI do I have?**  
>
> From a shell, typing **php -v** will tell you whether `php` is CGI or
> CLI. See also the function <span
> class="function">php\_sapi\_name</span> and the constant
> **`PHP_SAPI`**.

> **Note**:
>
> A Unix *man*ual page is available by typing **man php** in the shell
> environment.

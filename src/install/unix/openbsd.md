OpenBSD installation notes
--------------------------

This section contains notes and hints specific to installing PHP on
<a href="http://www.openbsd.org/" class="link external">» OpenBSD 5.8</a>.

### Using Binary Packages

Using binary packages to install PHP on OpenBSD is the recommended and
simplest method. The core package has been separated from the various
modules, and each can be installed and removed independently from the
others. The files you need can be found on your OpenBSD CD or on the FTP
site.

The main package you need to install is `php`, which contains the basic
engine (plus gettext and iconv). Next, take a look at the module
packages, such as `php-mysql` or `php-imap`. You need to use the
**phpxs** command to activate and deactivate these modules in your
`php.ini`.

**Example \#1 OpenBSD Package Install Example**

``` shell
# pkg_add php
# pkg_add php-fpm
# pkg_add php-mysql
  (install the PEAR libraries)
# pkg_add pear

Follow the instructions shown with each package!

  (to remove packages)
# pkg_delete php
# pkg_delete php-fpm
# pkg_delete php-mysql
# pkg_delete pear
```

Read the
<a href="http://www.openbsd.org/cgi-bin/man.cgi?query=packages" class="link external">» packages(7)</a>
manual page for more information about binary packages on OpenBSD.

### Using Ports

You can also compile up PHP from source using the
<a href="http://www.openbsd.org/faq/ports/ports.html" class="link external">» ports tree</a>.
However, this is only recommended for users familiar with OpenBSD. The
PHP 4 port is split into two sub-directories: core and extensions. The
extensions directory generates sub-packages for all of the supported PHP
modules. If you find you do not want to create some of these modules,
use the **no\_\*** FLAVOR. For example, to skip building the imap
module, set the FLAVOR to **no\_imap**.

### Common Problems

-   <span class="simpara">Apache and Nginx are no longer the default
    server on OpenBSD, but they can both be easily found in ports and
    packages. The new default server is also called 'httpd'. </span>
-   <span class="simpara">The default install of httpd runs inside a
    <a href="http://www.openbsd.org/cgi-bin/man.cgi?query=chroot" class="link external">» chroot(2) jail</a>,
    which will restrict PHP scripts to accessing files under `/var/www`.
    You will therefore need to create a `/var/www/tmp` directory for PHP
    session files to be stored, or use an alternative session backend.
    In addition, database sockets need to be placed inside the jail or
    listen on the `localhost` interface. If you use network functions,
    some files from `/etc` such as `/etc/resolv.conf` and
    `/etc/services` will need to be moved into `/var/www/etc`. The
    OpenBSD PEAR package automatically installs into the correct chroot
    directories. </span>
-   <span class="simpara"> The OpenBSD 5.7+ package for the
    <a href="http://www.libgd.org/" class="link external">» gd</a>
    extension requires XFree86 to be installed. This can be added
    post-installation (See OpenBSD FAQ\#4) by adding the `xbase.tgz`
    file set. </span>

### Older Releases

Older releases of OpenBSD used the FLAVORS system to compile up a
statically linked PHP. Since it is hard to generate binary packages
using this method, it is now deprecated. You can still use the old
stable ports trees if you wish, but they are unsupported by the OpenBSD
team. If you have any comments about this, the current maintainer for
the port is Anil Madhavapeddy (avsm at openbsd dot org).

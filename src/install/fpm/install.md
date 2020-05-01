Installation
------------

### Compiling from sources

In order to enable FPM in your PHP build you need to add *--enable-fpm*
to your configure line.

There are several other FPM-specific configure options (all of them
optional):

-   *--with-fpm-user* - set FPM user (default - nobody).

-   *--with-fpm-group* - set FPM group (default - nobody).

-   *--with-fpm-systemd* - Activate systemd integration (default - no).

-   *--with-fpm-acl* - Use POSIX Access Control Lists (default - no).
    Since PHP 5.6.5.

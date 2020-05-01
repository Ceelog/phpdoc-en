Apache 2.x on Unix systems
--------------------------

This section contains notes and hints specific to Apache 2.x installs of
PHP on Unix systems.

**Warning**

We do not recommend using a threaded MPM in production with Apache 2.
Use the prefork MPM, which is the default MPM with Apache 2.0 and 2.2.
For information on why, read the related FAQ entry on using
<a href="/faq/installation.html#faq.installation.apache2" class="link">Apache2 with a threaded MPM</a>

The
<a href="http://httpd.apache.org/docs/current/" class="link external">» Apache Documentation</a>
is the most authoritative source of information on the Apache 2.x
server. More information about installation options for Apache may be
found there.

The most recent version of Apache HTTP Server may be obtained from
<a href="http://httpd.apache.org/" class="link external">» Apache download site</a>,
and a fitting PHP version from the above mentioned places. This quick
guide covers only the basics to get started with Apache 2.x and PHP. For
more information read the
<a href="http://httpd.apache.org/docs/current/" class="link external">» Apache Documentation</a>.
The version numbers have been omitted here, to ensure the instructions
are not incorrect. In the examples below, 'NN' should be replaced with
the specific version of Apache being used.

There are currently two versions of Apache 2.x - there's 2.4 and 2.2.
While there are various reasons for choosing each, 2.4 is the current
latest version, and the one that is recommended, if that option is
available to you. However, the instructions here will work for either
2.4 or 2.2. Note that Apache httpd 2.2 is officially End Of Life, and no
new development or patches are being issued for it.

1.  Obtain the Apache HTTP server from the location listed above, and
    unpack it:

        tar -xzf httpd-2.x.NN.tar.gz

2.  Likewise, obtain and unpack the PHP source:

        tar -xzf php-NN.tar.gz

3.  Build and install Apache. Consult the Apache install documentation
    for more details on building Apache.

        cd httpd-2_x_NN
        ./configure --enable-so
        make
        make install

4.  Now you have Apache 2.x.NN available under /usr/local/apache2,
    configured with loadable module support and the standard MPM
    prefork. To test the installation use your normal procedure for
    starting the Apache server, e.g.:

        /usr/local/apache2/bin/apachectl start

    and stop the server to go on with the configuration for PHP:

        /usr/local/apache2/bin/apachectl stop

5.  Now, configure and build PHP. This is where you customize PHP with
    various options, like which extensions will be enabled. Run
    ./configure --help for a list of available options. In our example
    we'll do a simple configure with Apache 2 and MySQL support.

    If you built Apache from source, as described above, the below
    example will match your path for apxs, but if you installed Apache
    some other way, you'll need to adjust the path to apxs accordingly.
    Note that some distros may rename apxs to apxs2.

        cd ../php-NN
        ./configure --with-apxs2=/usr/local/apache2/bin/apxs --with-mysql
        make
        make install

    If you decide to change your configure options after installation,
    you'll need to re-run the configure, make, and make install steps.
    You only need to restart apache for the new module to take effect. A
    recompile of Apache is not needed.

    Note that unless told otherwise, 'make install' will also install
    PEAR, various PHP tools such as phpize, install the PHP CLI, and
    more.

6.  Setup your php.ini

        cp php.ini-development /usr/local/lib/php.ini

    You may edit your .ini file to set PHP options. If you prefer having
    php.ini in another location, use --with-config-file-path=/some/path
    in step 5.

    If you instead choose php.ini-production, be certain to read the
    list of changes within, as they affect how PHP behaves.

7.  Edit your httpd.conf to load the PHP module. The path on the right
    hand side of the LoadModule statement must point to the path of the
    PHP module on your system. The make install from above may have
    already added this for you, but be sure to check.

    For PHP 7:

    ``` apache-conf
    LoadModule php7_module modules/libphp7.so
    ```

    For PHP 5:

    ``` apache-conf
    LoadModule php5_module modules/libphp5.so
    ```

8.  Tell Apache to parse certain extensions as PHP. For example, let's
    have Apache parse .php files as PHP. Instead of only using the
    Apache AddType directive, we want to avoid potentially dangerous
    uploads and created files such as exploit.php.jpg from being
    executed as PHP. Using this example, you could have any extension(s)
    parse as PHP by simply adding them. We'll add .php to demonstrate.

    ``` apache-conf
    <FilesMatch \.php$>
        SetHandler application/x-httpd-php
    </FilesMatch>
    ```

    Or, if we wanted to allow .php, .php2, .php3, .php4, .php5, .php6,
    and .phtml files to be executed as PHP, but nothing else, we'd use
    this:

    ``` apache-conf
    <FilesMatch "\.ph(p[2-6]?|tml)$">
        SetHandler application/x-httpd-php
    </FilesMatch>
    ```

    And to allow .phps files to be handled by the php source filter, and
    displayed as syntax-highlighted source code, use this:

    ``` apache-conf
    <FilesMatch "\.phps$">
        SetHandler application/x-httpd-php-source
    </FilesMatch>
    ```

    mod\_rewrite may be used To allow any arbitrary .php file to be
    displayed as syntax-highlighted source code, without having to
    rename or copy it to a .phps file:

    ``` apache-conf
    RewriteEngine On
    RewriteRule (.*\.php)s$ $1 [H=application/x-httpd-php-source]
    ```

    The php source filter should not be enabled on production systems,
    where it may expose confidential or otherwise sensitive information
    embedded in source code.

9.  Use your normal procedure for starting the Apache server, e.g.:

        /usr/local/apache2/bin/apachectl start

    OR

        service httpd restart

Following the steps above you will have a running Apache2 web server
with support for PHP as a *SAPI* module. Of course there are many more
configuration options available Apache and PHP. For more information
type **./configure --help** in the corresponding source tree.

Apache may be built multithreaded by selecting the `worker` MPM, rather
than the standard `prefork` MPM, when Apache is built. This is done by
adding the following option to the argument passed to ./configure, in
step 3 above:

    --with-mpm=worker

This should not be undertaken without being aware of the consequences of
this decision, and having at least a fair understanding of the
implications. The Apache documentation regarding
<a href="http://httpd.apache.org/docs/current/mpm.html" class="link external">» MPM-Modules</a>
discusses MPMs in a great deal more detail.

> **Note**:
>
> The
> <a href="/faq/installation.html#faq.installation.apache.multiviews" class="link">Apache MultiViews FAQ</a>
> discusses using multiviews with PHP.

> **Note**:
>
> To build a multithreaded version of Apache, the target system must
> support threads. In this case, PHP should also be built with
> experimental Zend Thread Safety (ZTS). Under this configuration, not
> all extensions will be available. The recommended setup is to build
> Apache with the default `prefork` MPM-Module.

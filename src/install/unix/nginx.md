Nginx 1.4.x on Unix systems
---------------------------

This documentation will cover installing and configuring PHP with
PHP-FPM for a Nginx 1.4.x HTTP server.

This guide will assume that you have built Nginx from source and
therefore all binaries and configuration files are located at
*/usr/local/nginx*. If this is not the case and you have obtained Nginx
through other means then please refer to the
<a href="http://wiki.nginx.org/Main" class="link external">» Nginx Wiki</a>
in order to translate this manual to your setup.

This guide will cover the basics of configuring an Nginx server to
process PHP applications and serve them on port 80, it is recommended
that you study the Nginx and PHP-FPM documentation if you wish to
optimise your setup past the scope of this documentation.

Please note that throughout this documentation version numbers have been
replaced with an 'x' to ensure this documentation stays correct in the
future, please replace these as necessary with the corresponding version
numbers.

1.  It is recommended that you visit the Nginx Wiki
    <a href="http://wiki.nginx.org/Install" class="link external">» install</a>
    page in order to obtain and install Nginx on your system.

2.  Obtain and unpack the PHP source:

        tar zxf php-x.x.x

3.  Configure and build PHP. This is where you customize PHP with
    various options, like which extensions will be enabled. Run
    ./configure --help for a list of available options. In our example
    we'll do a simple configure with PHP-FPM and MySQLi support.

        cd ../php-x.x.x
        ./configure --enable-fpm --with-mysqli
        make
        sudo make install

4.  Obtain and move configuration files to their correct locations

        cp php.ini-development /usr/local/php/php.ini
        cp /usr/local/etc/php-fpm.d/www.conf.default /usr/local/etc/php-fpm.d/www.conf
        cp sapi/fpm/php-fpm /usr/local/bin

5.  It is important that we prevent Nginx from passing requests to the
    PHP-FPM backend if the file does not exists, allowing us to prevent
    arbitrarily script injection.

    We can fix this by setting the
    <a href="/ini/core.html#ini.cgi.fix-pathinfo" class="link">cgi.fix_pathinfo</a>
    directive to *0* within our php.ini file.

    Load up php.ini:

        vim /usr/local/php/php.ini

    Locate *cgi.fix\_pathinfo=* and modify it as follows:

        cgi.fix_pathinfo=0

6.  php-fpm.conf must be modified to specify that php-fpm must run as
    the user www-data and the group www-data before we can start the
    service:

        vim /usr/local/etc/php-fpm.d/www.conf

    Find and modify the following:

        ; Unix user/group of processes
        ; Note: The user is mandatory. If the group is not set, the default user's group
        ;       will be used.
        user = www-data
        group = www-data

    The php-fpm service can now be started:

        /usr/local/bin/php-fpm

    This guide will not configure php-fpm any further, if you are
    interested in further configuring php-fpm then please consult the
    documentation.

7.  Nginx must now be configured to support the processing of PHP
    applications:

        vim /usr/local/nginx/conf/nginx.conf

    Modify the default location block to be aware it must attempt to
    serve .php files:

    ``` nginx-conf
    location / {
        root   html;
        index  index.php index.html index.htm;
    }
    ```

    The next step is to ensure that .php files are passed to the PHP-FPM
    backend. Below the commented default PHP location block, enter the
    following:

    ``` nginx-conf
    location ~* \.php$ {
        fastcgi_index   index.php;
        fastcgi_pass    127.0.0.1:9000;
        include         fastcgi_params;
        fastcgi_param   SCRIPT_FILENAME    $document_root$fastcgi_script_name;
        fastcgi_param   SCRIPT_NAME        $fastcgi_script_name;
    }
    ```

    Restart Nginx.

        sudo /usr/local/nginx/sbin/nginx -s stop
        sudo /usr/local/nginx/sbin/nginx

8.  Create a test file

        rm /usr/local/nginx/html/index.html
        echo "<?php phpinfo(); ?>" >> /usr/local/nginx/html/index.php

    Now navigate to http://localhost. The phpinfo() should now be shown.

Following the steps above you will have a running Nginx web server with
support for PHP as an *FPM* *SAPI* module. Of course there are many more
configuration options available for Nginx and PHP. For more information
type **./configure --help** in the corresponding source tree.

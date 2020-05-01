Apache 1.3.x on Unix systems
----------------------------

This section contains notes and hints specific to Apache installs of PHP
on Unix platforms. We also have
<a href="/install/unix/apache2.html" class="link">instructions and notes for Apache 2 on a separate page</a>.

You can select arguments to add to the **configure** on line 10 below
from the
<a href="/configure/about.html" class="link">list of core configure options</a>
and from extension specific options described at the respective places
in the manual. The version numbers have been omitted here, to ensure the
instructions are not incorrect. You will need to replace the 'xxx' here
with the correct values from your files.

**Example \#1 Installation Instructions (Apache Shared Module Version)
for PHP**

    1.  gunzip apache_xxx.tar.gz
    2.  tar -xvf apache_xxx.tar
    3.  gunzip php-xxx.tar.gz
    4.  tar -xvf php-xxx.tar
    5.  cd apache_xxx
    6.  ./configure --prefix=/www --enable-module=so
    7.  make
    8.  make install
    9.  cd ../php-xxx

    10. Now, configure your PHP.  This is where you customize your PHP
        with various options, like which extensions will be enabled.  Do a
        ./configure --help for a list of available options.  In our example
        we'll do a simple configure with Apache 1 and MySQL support.  Your
        path to apxs may differ from our example.

          ./configure --with-mysql --with-apxs=/www/bin/apxs

    11. make
    12. make install

        If you decide to change your configure options after installation,
        you only need to repeat the last three steps. You only need to 
        restart apache for the new module to take effect. A recompile of
        Apache is not needed.
      
        Note that unless told otherwise, 'make install' will also install PEAR,
        various PHP tools such as phpize, install the PHP CLI, and more.

    13. Setup your php.ini file:

          cp php.ini-development /usr/local/lib/php.ini

        You may edit your .ini file to set PHP options.  If you prefer your
        php.ini in another location, use --with-config-file-path=/some/path in
        step 10. 
        
        If you instead choose php.ini-production, be certain to read the list
        of changes within, as they affect how PHP behaves.

    14. Edit your httpd.conf to load the PHP module.  The path on the right hand
        side of the LoadModule statement must point to the path of the PHP
        module on your system.  The make install from above may have already
        added this for you, but be sure to check.

          LoadModule php5_module libexec/libphp5.so
          
    15. And in the AddModule section of httpd.conf, somewhere under the
        ClearModuleList, add this:
        
          AddModule mod_php5.c

    16. Tell Apache to parse certain extensions as PHP.  For example,
        let's have Apache parse the .php extension as PHP.  You could
        have any extension(s) parse as PHP by simply adding more, with
        each separated by a space.  We'll add .phtml to demonstrate.

          AddType application/x-httpd-php .php .phtml

        It's also common to setup the .phps extension to show highlighted PHP
        source, this can be done with:
        
          AddType application/x-httpd-php-source .phps

    17. Use your normal procedure for starting the Apache server. (You must
        stop and restart the server, not just cause the server to reload by
        using a HUP or USR1 signal.)

Alternatively, to install PHP as a static object:

**Example \#2 Installation Instructions (Static Module Installation for
Apache) for PHP**

    1.  gunzip -c apache_1.3.x.tar.gz | tar xf -
    2.  cd apache_1.3.x
    3.  ./configure
    4.  cd ..

    5.  gunzip -c php-5.x.y.tar.gz | tar xf -
    6.  cd php-5.x.y
    7.  ./configure --with-mysql --with-apache=../apache_1.3.x
    8.  make
    9.  make install

    10. cd ../apache_1.3.x

    11. ./configure --prefix=/www --activate-module=src/modules/php5/libphp5.a
        (The above line is correct! Yes, we know libphp5.a does not exist at this
        stage. It isn't supposed to. It will be created.)

    12. make
        (you should now have an httpd binary which you can copy to your Apache bin dir if
        it is your first install then you need to "make install" as well)

    13. cd ../php-5.x.y
    14. cp php.ini-development /usr/local/lib/php.ini

    15. You can edit /usr/local/lib/php.ini file to set PHP options.
        Edit your httpd.conf or srm.conf file and add:
        AddType application/x-httpd-php .php

Depending on your Apache install and Unix variant, there are many
possible ways to stop and restart the server. Below are some typical
lines used in restarting the server, for different apache/unix
installations. You should replace */path/to/* with the path to these
applications on your systems.

**Example \#3 Example commands for restarting Apache**

``` shell
1. Several Linux and SysV variants:
/etc/rc.d/init.d/httpd restart

2. Using apachectl scripts:
/path/to/apachectl stop
/path/to/apachectl start

3. httpdctl and httpsdctl (Using OpenSSL), similar to apachectl:
/path/to/httpsdctl stop
/path/to/httpsdctl start

4. Using mod_ssl, or another SSL server, you may want to manually
stop and start:
/path/to/apachectl stop
/path/to/apachectl startssl
```

The locations of the apachectl and http(s)dctl binaries often vary. If
your system has *locate*, *whereis* or *which* commands, these can
assist you in finding your server control programs.

Different examples of compiling PHP for apache are as follows:

``` shell
./configure --with-apxs --with-pgsql
```

This will create a `libphp5.so` shared library that is loaded into
Apache using a LoadModule line in Apache's `httpd.conf` file. The
PostgreSQL support is embedded into this library.

``` shell
./configure --with-apxs --with-pgsql=shared
```

This will create a `libphp5.so` shared library for Apache, but it will
also create a `pgsql.so` shared library that is loaded into PHP either
by using the extension directive in `php.ini` file or by loading it
explicitly in a script using the <span class="function">dl</span>
function.

``` shell
./configure --with-apache=/path/to/apache_source --with-pgsql
```

This will create a `libmodphp5.a` library, a `mod_php5.c` and some
accompanying files and copy this into the *src/modules/php5* directory
in the Apache source tree. Then you compile Apache using
*--activate-module=src/modules/php5/libphp5.a* and the Apache build
system will create `libphp5.a` and link it statically into the `httpd`
binary. The PostgreSQL support is included directly into this `httpd`
binary, so the final result here is a single `httpd` binary that
includes all of Apache and all of PHP.

``` shell
./configure --with-apache=/path/to/apache_source --with-pgsql=shared
```

Same as before, except instead of including PostgreSQL support directly
into the final `httpd` you will get a `pgsql.so` shared library that you
can load into PHP from either the `php.ini` file or directly using <span
class="function">dl</span>.

When choosing to build PHP in different ways, you should consider the
advantages and drawbacks of each method. Building as a shared object
will mean that you can compile apache separately, and don't have to
recompile everything as you add to, or change, PHP. Building PHP into
apache (static method) means that PHP will load and run faster. For more
information, see the Apache
<a href="http://httpd.apache.org/docs/current/dso.html" class="link external">» web page on DSO support</a>.

> **Note**:
>
> Apache's default `httpd.conf` currently ships with a section that
> looks like this:
>
> ``` apache-conf
> User nobody
> Group "#-1"
> ```
>
> Unless you change that to "Group nogroup" or something like that
> ("Group daemon" is also very common) PHP will not be able to open
> files.

> **Note**:
>
> Make sure you specify the installed version of apxs when using
> **--with-apxs=/path/to/apxs**. You must NOT use the apxs version that
> is in the apache sources but the one that is actually installed on
> your system.

Using the bundled PHP
---------------------

PHP has come standard with Macs since Mac OS X version 10.0.0. Enabling
PHP with the default web server requires uncommenting a few lines in the
Apache configuration file `httpd.conf` whereas the CGI and/or CLI are
enabled by default (easily accessible via the Terminal program).

Enabling PHP using the instructions below is meant for quickly setting
up a local development environment. It's *highly recommended* to always
upgrade PHP to the newest version. Like most live software, newer
versions are created to fix bugs and add features and PHP being is no
different. See the appropriate macOS installation documentation for
further details. The following instructions are geared towards a
beginner with details provided for getting a default setup to work. All
users are encouraged to compile, or install a new packaged version.

The standard installation type is using mod\_php, and enabling the
bundled mod\_php on macOS for the Apache web server (the default web
server, that is accessible via System Preferences) involves the
following steps:

1.  <span class="simpara"> Locate and open the Apache configuration
    file. By default, the location is as follows:
    `/private/etc/apache2/httpd.conf` </span> <span class="simpara">
    Using *Finder* or *Spotlight* to find this file may prove difficult
    as by default it's private and owned by the *root* user. </span>

    > **Note**: <span class="simpara"> One way to open this is by using
    > a Unix based text editor in the Terminal, for example *nano*, and
    > because the file is owned by *root* we'll use the *sudo* command
    > to open it (as *root*) so for example type the following into the
    > *Terminal* Application (after, it will prompt for a password):
    > *sudo nano /private/etc/apache2/httpd.conf* </span> <span
    > class="simpara"> Noteworthy nano commands: *^w* (search), *^o*
    > (save), and *^x* (exit) where *^* represents the Ctrl key. </span>

    > **Note**: <span class="simpara"> Versions of Mac OS X prior to
    > 10.5 were bundled with older versions of PHP and Apache. As such,
    > the Apache configuration file on legacy machines may be
    > `/etc/httpd/httpd.conf`. </span>

2.  With a text editor, uncomment the lines (by removing the \#) that
    look similar to the following (these two lines are often not
    together, locate them both in the file):

        # LoadModule php5_module libexec/httpd/libphp5.so

        # AddModule mod_php5.c

    Notice the location/path. When building PHP in the future, the above
    files should be replaced or commented out.

3.  Be sure the desired extensions will parse as PHP (examples: .php
    .html and .inc)

    Due to the following statement already existing in `httpd.conf` (as
    of Mac Panther), once PHP is enabled the `.php` files will
    automatically parse as PHP.

        <IfModule mod_php5.c>
            # If php is turned on, we respect .php and .phps files.
            AddType application/x-httpd-php .php
            AddType application/x-httpd-php-source .phps

            # Since most users will want index.php to work we
            # also automatically enable index.php
            <IfModule mod_dir.c>
                DirectoryIndex index.html index.php
            </IfModule>
        </IfModule>

    > **Note**:
    >
    > Before Mac OS X 10.5 (Leopard), PHP 4 was bundled instead of PHP 5
    > in which case the above instructions will differ slightly by
    > changing 5's to 4's.

4.  <span class="simpara"> Be sure the DirectoryIndex loads the desired
    default index file </span> <span class="simpara"> This is also set
    in `httpd.conf`. Typically `index.php` and `index.html` are used. By
    default `index.php` is enabled because it's also in the PHP check
    shown above. Adjust accordingly. </span>

5.  <span class="simpara"> Set the `php.ini` location or use the default
    </span> <span class="simpara"> A typical default location on macOS
    is `/usr/local/php/php.ini` and a call to <span
    class="function">phpinfo</span> will reveal this information. If a
    `php.ini` is not used, PHP will use all default values. See also the
    related FAQ on
    <a href="/faq/installation.html#faq.installation.phpini" class="link">finding php.ini</a>.
    </span>

6.  <span class="simpara"> Locate or set the *DocumentRoot* </span>
    <span class="simpara"> This is the root directory for all the web
    files. Files in this directory are served from the web server so the
    PHP files will parse as PHP before outputting them to the browser. A
    typical default path is `/Library/WebServer/Documents` but this can
    be set to anything in `httpd.conf`. Alternatively, the default
    `DocumentRoot` for individual users is `/Users/yourusername/Sites`
    </span>

7.  <span class="simpara"> Create a <span
    class="function">phpinfo</span> file </span>

    The <span class="function">phpinfo</span> function will display
    information about PHP. Consider creating a file in the DocumentRoot
    with the following PHP code:

    ``` php
    <?php phpinfo(); ?>
    ```

8.  <span class="simpara"> Restart Apache, and load the PHP file created
    above </span>

    To restart, either execute *sudo apachectl graceful* in the shell or
    stop/start the "Personal Web Server" option in the macOS System
    Preferences. By default, loading local files in the browser will
    have an URL like so: `http://localhost/info.php` Or using the
    DocumentRoot in the user directory is another option and would end
    up looking like: `http://localhost/~yourusername/info.php`

The CLI (or CGI in older versions) is appropriately named `php` and
likely exists as `/usr/bin/php`. Open up the terminal, read the
<a href="/features/commandline.html" class="link">command line section</a>
of the PHP manual, and execute *php -v* to check the PHP version of this
PHP binary. A call to <span class="function">phpinfo</span> will also
reveal this information.

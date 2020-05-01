Migrating Configuration Files
-----------------------------

Since the ISAPI modules changed their names, from php4xxx to php5xxx,
you need to make some changes in the configuration files. There were
also changes in the CLI and CGI filenames. Please refer to the
<a href="/migration5/cli-cgi.html" class="link">corresponding section</a>
for more information.

Migrating the Apache configuration is extremely easy. See the example
below to check the change you need to do:

**Example \#1 Migrating Apache configuration files for PHP 5**

``` apache-conf
# change this line:    
LoadModule php4_module /php/sapi/php4apache2.dll

# with this one:
LoadModule php5_module /php/php5apache2.dll
```

If your web server is running PHP in CGI mode, you should note that the
CGI version has changed its name from `php.exe` to `php-cgi.exe`. In
Apache, you should do something like this:

**Example \#2 Migrating Apache configuration files for PHP 5, CGI mode**

``` apache-conf
# change this line:    
Action application/x-httpd-php "/php/php.exe" 

# with this one:
Action application/x-httpd-php "/php/php-cgi.exe"
```

In other web servers you need to change either the CGI or the ISAPI
module filenames.

Hiding PHP
==========

In general, security by obscurity is one of the weakest forms of
security. But in some cases, every little bit of extra security is
desirable.

A few simple techniques can help to hide PHP, possibly slowing down an
attacker who is attempting to discover weaknesses in your system. By
setting expose\_php to *off* in your `php.ini` file, you reduce the
amount of information available to them.

Another tactic is to configure web servers such as apache to parse
different filetypes through PHP, either with an `.htaccess` directive,
or in the apache configuration file itself. You can then use misleading
file extensions:

**Example \#1 Hiding PHP as another language**

``` apache-conf
# Make PHP code look like other code types
AddType application/x-httpd-php .asp .py .pl
```

Or obscure it completely:

**Example \#2 Using unknown types for PHP extensions**

``` apache-conf
# Make PHP code look like unknown types
AddType application/x-httpd-php .bop .foo .133t
```

Or hide it as HTML code, which has a slight performance hit because all
HTML will be parsed through the PHP engine:

**Example \#3 Using HTML types for PHP extensions**

``` apache-conf
# Make all PHP code look like HTML
AddType application/x-httpd-php .htm .html
```

For this to work effectively, you must rename your PHP files with the
above extensions. While it is a form of security through obscurity, it's
a minor preventative measure with few drawbacks.

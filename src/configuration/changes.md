How to change configuration settings
------------------------------------

### Running PHP as an Apache module

When using PHP as an Apache module, you can also change the
configuration settings using directives in Apache configuration files
(e.g. `httpd.conf`) and `.htaccess` files. You will need "AllowOverride
Options" or "AllowOverride All" privileges to do so.

There are several Apache directives that allow you to change the PHP
configuration from within the Apache configuration files. For a listing
of which directives are **`PHP_INI_ALL`**, **`PHP_INI_PERDIR`**, or
**`PHP_INI_SYSTEM`**, have a look at the
<a href="/ini/list.html" class="link">List of php.ini directives</a>
appendix.

`php_value` `name` `value`  
Sets the value of the specified directive. Can be used only with
**`PHP_INI_ALL`** and **`PHP_INI_PERDIR`** type directives. To clear a
previously set value use *none* as the value.

> **Note**: <span class="simpara"> Don't use `php_value` to set boolean
> values. `php_flag` (see below) should be used instead. </span>

`php_flag` `name` `on|off`  
Used to set a boolean configuration directive. Can be used only with
**`PHP_INI_ALL`** and **`PHP_INI_PERDIR`** type directives.

`php_admin_value` `name` `value`  
Sets the value of the specified directive. This *can not be used* in
`.htaccess` files. Any directive type set with `php_admin_value` can not
be overridden by `.htaccess` or <span class="function">ini\_set</span>.
To clear a previously set value use *none* as the value.

`php_admin_flag` `name` `on|off`  
Used to set a boolean configuration directive. This *can not be used* in
`.htaccess` files. Any directive type set with `php_admin_flag` can not
be overridden by `.htaccess` or <span class="function">ini\_set</span>.

**Example \#1 Apache configuration example**

``` ini
<IfModule mod_php5.c>
  php_value include_path ".:/usr/local/lib/php"
  php_admin_flag engine on
</IfModule>
<IfModule mod_php4.c>
  php_value include_path ".:/usr/local/lib/php"
  php_admin_flag engine on
</IfModule>
```

**Caution**

PHP constants do not exist outside of PHP. For example, in `httpd.conf`
you can not use PHP constants such as **`E_ALL`** or **`E_NOTICE`** to
set the
<a href="/errorfunc/setup.html#PHP%20Constants%20outside%20of%20PHP" class="link">error_reporting</a>
directive as they will have no meaning and will evaluate to *0*. Use the
associated bitmask values instead. These constants can be used in
`php.ini`

### Changing PHP configuration via the Windows registry

When running PHP on Windows, the configuration values can be modified on
a per-directory basis using the Windows registry. The configuration
values are stored in the registry key *HKLM\\SOFTWARE\\PHP\\Per
Directory Values*, in the sub-keys corresponding to the path names. For
example, configuration values for the directory *c:\\inetpub\\wwwroot*
would be stored in the key *HKLM\\SOFTWARE\\PHP\\Per Directory
Values\\c\\inetpub\\wwwroot*. The settings for the directory would be
active for any script running from this directory or any subdirectory of
it. The values under the key should have the name of the PHP
configuration directive and the string value. PHP constants in the
values are not parsed. However, only configuration values changeable in
**`PHP_INI_USER`** can be set this way, **`PHP_INI_PERDIR`** values can
not, because these configuration values are re-read for each request.

### Other interfaces to PHP

Regardless of how you run PHP, you can change certain values at runtime
of your scripts through <span class="function">ini\_set</span>. See the
documentation on the <span class="function">ini\_set</span> page for
more information.

If you are interested in a complete list of configuration settings on
your system with their current values, you can execute the <span
class="function">phpinfo</span> function, and review the resulting page.
You can also access the values of individual configuration directives at
runtime using <span class="function">ini\_get</span> or <span
class="function">get\_cfg\_var</span>.

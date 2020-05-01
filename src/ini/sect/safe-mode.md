Security and Safe Mode
----------------------

| Name                                                                                                              | Default             | Changeable       | Changelog             |
|-------------------------------------------------------------------------------------------------------------------|---------------------|------------------|-----------------------|
| <a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe_mode</a>                                       | "0"                 | PHP\_INI\_SYSTEM | Removed in PHP 5.4.0. |
| <a href="/ini/sect/safe-mode.html#ini.safe-mode-gid" class="link">safe_mode_gid</a>                               | "0"                 | PHP\_INI\_SYSTEM | Removed in PHP 5.4.0. |
| <a href="/ini/sect/safe-mode.html#ini.safe-mode-include-dir" class="link">safe_mode_include_dir</a>               | NULL                | PHP\_INI\_SYSTEM | Removed in PHP 5.4.0. |
| <a href="/ini/sect/safe-mode.html#ini.safe-mode-exec-dir" class="link">safe_mode_exec_dir</a>                     | ""                  | PHP\_INI\_SYSTEM | Removed in PHP 5.4.0. |
| <a href="/ini/sect/safe-mode.html#ini.safe-mode-allowed-env-vars" class="link">safe_mode_allowed_env_vars</a>     | "PHP\_"             | PHP\_INI\_SYSTEM | Removed in PHP 5.4.0. |
| <a href="/ini/sect/safe-mode.html#ini.safe-mode-protected-env-vars" class="link">safe_mode_protected_env_vars</a> | "LD\_LIBRARY\_PATH" | PHP\_INI\_SYSTEM | Removed in PHP 5.4.0. |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

Here's a short explanation of the configuration directives.

`safe_mode` <span class="type">boolean</span>  
Whether to enable PHP's safe mode. If PHP is compiled with
*--enable-safe-mode* then defaults to On, otherwise Off.

**Warning**
This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

`safe_mode_gid` <span class="type">boolean</span>  
By default, Safe Mode does a UID compare check when opening files. If
you want to relax this to a GID compare, then turn on safe\_mode\_gid.
Whether to use *UID* (**`FALSE`**) or *GID* (**`TRUE`**) checking upon
file access.

`safe_mode_include_dir` <span class="type">string</span>  
*UID*/*GID* checks are bypassed when including files from this directory
and its subdirectories (directory must also be in
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
or full path must including).

<span class="simpara"> This directive can take a colon (semi-colon on
Windows) separated path in a fashion similar to the
<a href="/ini/core.html#ini.include-path" class="link">include_path</a>
directive, rather than just a single directory. </span> <span
class="simpara"> The restriction specified is actually a prefix, not a
directory name. This means that "*safe\_mode\_include\_dir = /dir/incl*"
also allows access to "*/dir/include*" and "*/dir/incls*" if they exist.
When you want to restrict access to only the specified directory, end
with a slash. For example: "*safe\_mode\_include\_dir = /dir/incl/*"
</span> <span class="simpara"> If the value of this directive is empty,
no files with different *UID*/*GID* can be included. </span>

`safe_mode_exec_dir` <span class="type">string</span>  
If PHP is used in safe mode, <span class="function">system</span> and
the other
<a href="/ref/exec.html" class="link">functions executing system programs</a>
refuse to start programs that are not in this directory. You have to use
*/* as directory separator on all environments including Windows.

`safe_mode_allowed_env_vars` <span class="type">string</span>  
Setting certain environment variables may be a potential security
breach. This directive contains a comma-delimited list of prefixes. In
Safe Mode, the user may only alter environment variables whose names
begin with the prefixes supplied here. By default, users will only be
able to set environment variables that begin with *PHP\_* (e.g.
*PHP\_FOO=BAR*).

> **Note**:
>
> If this directive is empty, PHP will let the user modify ANY
> environment variable!

`safe_mode_protected_env_vars` <span class="type">string</span>  
This directive contains a comma-delimited list of environment variables
that the end user won't be able to change using <span
class="function">putenv</span>. These variables will be protected even
if safe\_mode\_allowed\_env\_vars is set to allow to change them.

See also:
<a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>,
<a href="/ini/core.html#ini.disable-functions" class="link">disable_functions</a>,
<a href="/ini/core.html#ini.disable-classes" class="link">disable_classes</a>,
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>,
<a href="/errorfunc/setup.html#" class="link">display_errors</a>, and
<a href="/errorfunc/setup.html#" class="link">log_errors</a>.

When
<a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe_mode</a>
is on, PHP checks to see if the owner of the current script matches the
owner of the file to be operated on by a file function or its directory.
For example:

``` ls
-rw-rw-r--    1 rasmus   rasmus       33 Jul  1 19:20 script.php 
-rw-r--r--    1 root     root       1116 May 26 18:01 /etc/passwd
```

Running `script.php`:

``` php
<?php
 readfile('/etc/passwd'); 
?>
```

results in this error when safe mode is enabled:

    Warning: SAFE MODE Restriction in effect. The script whose uid is 500 is not 
    allowed to access /etc/passwd owned by uid 0 in /docroot/script.php on line 2

However, there may be environments where a strict *UID* check is not
appropriate and a relaxed *GID* check is sufficient. This is supported
by means of the
<a href="/ini/sect/safe-mode.html#ini.safe-mode-gid" class="link">safe_mode_gid</a>
switch. Setting it to *On* performs the relaxed *GID* checking, setting
it to *Off* (the default) performs *UID* checking.

If instead of
<a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe_mode</a>,
you set an
<a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
directory then all file operations will be limited to files under the
specified directory. For example (Apache `httpd.conf` example):

``` ini
<Directory /docroot>
  php_admin_value open_basedir /docroot 
</Directory>
```

If you run the same `script.php` with this
<a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
setting then this is the result:

    Warning: open_basedir restriction in effect. File is in wrong directory in 
    /docroot/script.php on line 2 

You can also disable individual functions. Note that the
<a href="/ini/core.html#ini.disable-functions" class="link">disable_functions</a>
directive can not be used outside of the `php.ini` file which means that
you cannot disable functions on a per-virtualhost or per-directory basis
in your `httpd.conf` file. If we add this to our `php.ini` file:

``` ini
disable_functions = readfile,system
```

Then we get this output:

    Warning: readfile() has been disabled for security reasons in 
    /docroot/script.php on line 2 

**Warning**

These PHP restrictions are not valid in executed binaries, of course.

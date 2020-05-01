Disabling Magic Quotes
----------------------

The <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>
directive may only be disabled at the system level, and not at runtime.
In otherwords, use of <span class="function">ini\_set</span> is not an
option.

**Example \#1 Disabling magic quotes server side**

An example that sets the value of these directives to *Off* in
`php.ini`. For additional details, read the manual section titled
<a href="/configuration/changes.html" class="link">How to change configuration settings</a>.

    ; Magic quotes
    ;

    ; Magic quotes for incoming GET/POST/Cookie data.
    magic_quotes_gpc = Off

    ; Magic quotes for runtime-generated data, e.g. data from SQL, from exec(), etc.
    magic_quotes_runtime = Off

    ; Use Sybase-style magic quotes (escape ' with '' instead of \').
    magic_quotes_sybase = Off

If access to the server configuration is unavailable, use of `.htaccess`
is also an option. For example:

    php_flag magic_quotes_gpc Off

In the interest of writing portable code (code that works in any
environment), like if setting at the server level is not possible,
here's an example to disable
<a href="/info/setup.html#" class="link">magic_quotes_gpc</a> at
runtime. This method is inefficient so it's preferred to instead set the
appropriate directives elsewhere.

**Example \#2 Disabling magic quotes at runtime**

``` php
<?php
if (get_magic_quotes_gpc()) {
    $process = array(&$_GET, &$_POST, &$_COOKIE, &$_REQUEST);
    while (list($key, $val) = each($process)) {
        foreach ($val as $k => $v) {
            unset($process[$key][$k]);
            if (is_array($v)) {
                $process[$key][stripslashes($k)] = $v;
                $process[] = &$process[$key][stripslashes($k)];
            } else {
                $process[$key][stripslashes($k)] = stripslashes($v);
            }
        }
    }
    unset($process);
}
?>
```

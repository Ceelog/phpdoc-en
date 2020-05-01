CLI and CGI
-----------

In PHP 5 there were some changes in CLI and CGI filenames. In PHP 5, the
CGI version was renamed to `php-cgi.exe` (previously `php.exe`) and the
CLI version now sits in the main directory (previously `cli/php.exe`).

In PHP 5 it was also introduced a new mode: `php-win.exe`. This is equal
to the CLI version, except that php-win doesn't output anything and thus
provides no console (no "dos box" appears on the screen). This behavior
is similar to php-gtk.

In PHP 5, the CLI version will always populate the global `$argv` and
`$argc` variables regardless of any `php.ini` directive setting. Even
having
<a href="/ini/core.html#ini.register-argc-argv" class="link">register_argc_argv</a>
set to *off* will have no affect in CLI.

See also the
<a href="/features/commandline.html" class="link">command line reference</a>.

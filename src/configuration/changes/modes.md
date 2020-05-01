Where a configuration setting may be set
----------------------------------------

These modes determine when and where a PHP directive may or may not be
set, and each directive within the manual refers to one of these modes.
For example, some settings may be set within a PHP script using <span
class="function">ini\_set</span>, whereas others may require `php.ini`
or `httpd.conf`.

For example, the
<a href="/outcontrol/setup.html#" class="link">output_buffering</a>
setting is *PHP\_INI\_PERDIR* therefore it may not be set using <span
class="function">ini\_set</span>. However, the
<a href="/errorfunc/setup.html#" class="link">display_errors</a>
directive is *PHP\_INI\_ALL* therefore it may be set anywhere, including
with <span class="function">ini\_set</span>.

| Mode               | Meaning                                                                                                                                                                                                                                             |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| *PHP\_INI\_USER*   | Entry can be set in user scripts (like with <span class="function">ini\_set</span>) or in the <a href="/configuration/changes.html#configuration.changes.windows" class="link">Windows registry</a>. Since PHP 5.3, entry can be set in `.user.ini` |
| *PHP\_INI\_PERDIR* | Entry can be set in `php.ini`, `.htaccess`, `httpd.conf` or `.user.ini` (since PHP 5.3)                                                                                                                                                             |
| *PHP\_INI\_SYSTEM* | Entry can be set in `php.ini` or `httpd.conf`                                                                                                                                                                                                       |
| *PHP\_INI\_ALL*    | Entry can be set anywhere                                                                                                                                                                                                                           |

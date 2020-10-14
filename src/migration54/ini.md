Changes to INI file handling
----------------------------

The following `php.ini` directives have been removed:

-   <span class="simpara">
    <a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
    and
    <a href="/ini/core.html#ini.register-long-arrays" class="link">register_long_arrays</a>
    </span>
-   <span class="simpara">
    <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>,
    <a href="/info/setup.html#" class="link">magic_quotes_runtime</a>,
    and magic\_quotes\_sybase </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.allow-call-time-pass-reference" class="link">allow_call_time_pass_reference</a>
    </span>
-   <span class="simpara">
    <a href="/network/setup.html#" class="link">define_syslog_variables</a>
    </span>
-   <span class="simpara">
    <a href="/misc/setup.html#" class="link">highlight.bg</a> </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">session.bug_compat_42</a>
    and
    <a href="/session/setup.html#" class="link">session.bug_compat_warn</a>
    </span>
-   <span class="simpara"> mbstring.script\_encoding </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.y2k-compliance" class="link">y2k_compliance</a>
    </span>
-   <span class="simpara"> safe\_mode, safe\_mode\_gid,
    safe\_mode\_include\_dir, safe\_mode\_exec\_dir,
    safe\_mode\_allowed\_env\_vars, and safe\_mode\_protected\_env\_vars
    </span>

The following `php.ini` directives have been added:

-   <span class="simpara">
    <a href="/readline/setup.html#" class="link">cli.pager</a> and
    <a href="/readline/setup.html#" class="link">cli.prompt</a> for CLI
    SAPI using readline in interactive mode. </span>
-   <span class="simpara">
    <a href="/features/commandline/ini.html#ini.cli-server.color" class="link">cli_server.color</a>
    to enable the built-in development web server to use ANSI color
    coding in terminal output. </span>
-   <span class="simpara">
    <a href="/info/setup.html#" class="link">max_input_vars</a> -
    specifies how many GET/POST/COOKIE input variables may be accepted.
    </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.zend.multibyte" class="link">zend.multibyte</a> -
    to control the new multibyte support. </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.zend.script-encoding" class="link">zend.script_encoding</a> -
    This value will be used unless a "declare(encoding=...)" directive
    appears at the top of the script. </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.zend.signal-check" class="link">zend.signal_check</a> -
    to check for replaced signal handlers on shutdown. </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">session.upload_progress.enabled</a>,
    <a href="/session/setup.html#" class="link">session.upload_progress.cleanup</a>,
    <a href="/session/setup.html#" class="link">session.upload_progress.prefix</a>,
    <a href="/session/setup.html#" class="link">session.upload_progress.name</a>,
    <a href="/session/setup.html#" class="link">session.upload_progress.freq</a>,
    <a href="/session/setup.html#" class="link">session.upload_progress.min_freq</a>
    </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.enable-post-data-reading" class="link">enable_post_data_reading</a> -
    When it's disabled, the POST data is not read (and processed)
    </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.windows-show-crt-warning" class="link">windows_show_crt_warning</a> -
    This directive shows the Windows CRT warnings when enabled. These
    warnings were displayed by default until now. </span>

The following `php.ini` directives have been changed:

-   <span class="simpara">
    <a href="/session/setup.html#" class="link">session.entropy_file</a>
    now defaults to /dev/random or /dev/urandom depending on what has
    been guessed at compile time. </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">session.entropy_length</a>
    now defaults to 32. </span>

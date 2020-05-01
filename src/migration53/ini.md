Changes to INI file handling
----------------------------

PHP 5.3.0 has significantly improved performance and parsing of INI
files, and adds several new syntax features.

-   <span class="simpara"> The standard `php.ini` files have been
    re-organized and renamed. *php.ini-development* contains settings
    recommended for use in development environments.
    *php.ini-production* contains settings recommended for use in
    production environments. </span>
-   <span class="simpara"> There is now support for two special
    sections: *\[PATH=/opt/httpd/www.example.com/\]* and
    *\[HOST=www.example.com\]*. Directives set in these sections cannot
    be overridden by user-defined INI files or at runtime. More
    information about these sections can be found
    <a href="/ini/sections.html" class="link">here</a>. </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.zend-extension-debug" class="link">zend_extension_debug</a>,
    <a href="/ini/core.html#ini.zend-extension-debug-ts" class="link">zend_extension_debug_ts</a>
    and
    <a href="/ini/core.html#ini.zend-extension-ts" class="link">zend_extension_ts</a>
    have been removed. Use the
    <a href="/ini/core.html#ini.zend-extension" class="link">zend_extension</a>
    directive to load all Zend Extensions. </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.zend.ze1-compatibility-mode" class="link">zend.ze1_compatibility_mode</a>
    has been removed. If this INI directive is set to On, an
    **`E_ERROR`** error is emitted at startup. </span>
-   <span class="simpara"> It is now possible to use the full path to
    load modules using the
    <a href="/ini/core.html#ini.extension" class="link">extension</a>
    directive. </span>
-   <span class="simpara"> *"ini-variables"* can now be used almost
    anywhere in a `php.ini` file. </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.open-basedir" class="link">open_basedir</a>
    restrictions may now be tighted at runtime, and the directive is now
    PHP\_INI\_ALL. </span>
-   <span class="simpara"> It is now possible to use alphanumeric or
    variable indices in INI option arrays. </span>
-   <span class="simpara"> <span class="function">get\_cfg\_var</span>
    is now able to return "array" INI options. </span>
-   <span class="simpara"> Two new mail directives:
    <a href="/mail/setup.html#" class="link">mail.add_x_header</a> and
    <a href="/mail/setup.html#" class="link">mail.log</a>, have been
    added. </span>

The following new ini directives have been added:

-   <span class="simpara"> *user\_ini.filename* and
    *user\_ini.cache\_ttl* have been added to control the use of
    <a href="/configuration/file/per-user.html" class="link">user INI files</a>.
    </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.exit-on-timeout" class="link">exit_on_timeout</a>
    has been added to force Apache 1.x children to exit if a PHP
    execution timeout occurs. </span>
-   <span class="simpara"> Added
    *mbstring.http\_output\_conv\_mimetype*. This directive specifies
    the regex pattern of content types for which <span
    class="function">mb\_output\_handler</span> is activated. </span>
-   <span class="simpara"> Added
    <a href="/ini/core.html#ini.request-order" class="link">request_order</a>.
    Allows controlling which external variables will be available in
    `$_REQUEST`. </span>

The following ini directives have new default values:

-   <span class="simpara">
    <a href="/session/setup.html#" class="link">session.use_only_cookies</a>
    is now set to *"1"* (enabled) by default. </span>
-   <span class="simpara">
    <a href="/book/oci8.html#" class="link">oci8.default_prefetch</a>
    has changed from *"10"* to *"100"*. </span>

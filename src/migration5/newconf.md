New Directives
--------------

There were some new `php.ini` directives introduced in PHP 5. Here is a
list of them:

-   <span class="simpara">
    <a href="/mail/setup.html#" class="link">mail.force_extra_parameters</a>
    - Force the addition of the specified parameters to be passed as
    extra parameters to the sendmail binary. These parameters will
    always replace the value of the 5th parameter to <span
    class="function">mail</span>, even in safe mode </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.register-long-arrays" class="link">register_long_arrays</a>
    - allow/disallow PHP to register the deprecated long `$HTTP_*_VARS`
    </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">session.hash_function</a>
    - select a hash function (MD5 or SHA-1) </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">session.hash_bits_per_character</a> -
    define how many bits are stored in each character when converting
    the binary hash data to something readable (from 4 to 6) </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.zend.ze1-compatibility-mode" class="link">zend.ze1_compatibility_mode</a> -
    Enable compatibility mode with Zend Engine 1 (PHP 4) </span>

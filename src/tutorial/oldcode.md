Now that PHP has grown to be a popular scripting language, there are a
lot of public repositories and libraries containing code you can reuse.
The PHP developers have largely tried to preserve backwards
compatibility, so a script written for an older version will run
(ideally) without changes in a newer version of PHP. In practice, some
changes will usually be needed.

Two of the most important recent changes that affect old code are:

-   <span class="simpara"> The old `$HTTP_*_VARS` arrays are not
    available as of PHP 5.4.0. The following
    <a href="/language/variables/superglobals.html" class="link">superglobal arrays</a>
    were introduced in PHP
    <a href="https://www.php.net/releases/4_1_0.php" class="link external">» 4.1.0</a>.
    They are: `$_GET`, `$_POST`, `$_COOKIE`, `$_SERVER`, `$_FILES`,
    `$_ENV`, `$_REQUEST`, and `$_SESSION`. </span>
-   <span class="simpara"> External variables are no longer registered
    in the global scope by default. In other words, as of PHP
    <a href="https://www.php.net/releases/4_2_0.php" class="link external">» 4.2.0</a>
    the PHP directive
    <a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
    is *off* by default in `php.ini`. The preferred method of accessing
    these values is via the superglobal arrays mentioned above. Older
    scripts, books, and tutorials may rely on this directive being *on*.
    If it were *on*, for example, one could use `$id` from the URL
    *http://www.example.com/foo.php?id=42*. Whether on or off,
    `$_GET['id']` is available. </span>

For more details on these changes, see the section on
<a href="/language/variables/predefined.html" class="link">predefined variables</a>
and links therein.

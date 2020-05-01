Cookies
=======

PHP transparently supports HTTP cookies. Cookies are a mechanism for
storing data in the remote browser and thus tracking or identifying
return users. You can set cookies using the <span
class="function">setcookie</span> or <span
class="function">setrawcookie</span> function. Cookies are part of the
HTTP header, so <span class="function">setcookie</span> must be called
before any output is sent to the browser. This is the same limitation
that <span class="function">header</span> has. You can use the
<a href="/ref/outcontrol.html" class="link">output buffering functions</a>
to delay the script output until you have decided whether or not to set
any cookies or send any headers.

Any cookies sent to server from the client will automatically be
included into a `$_COOKIE` auto-global array if
<a href="/ini/core.html#ini.variables-order" class="link">variables_order</a>
contains "C". If you wish to assign multiple values to a single cookie,
just add *\[\]* to the cookie name.

On older PHP systems (5.3 or earlier),
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
may be enabled, which may cause undesirable and insecure operation. If
this is enabled, cookies will be registered as global variables.

For more details, including notes on browser bugs, see the <span
class="function">setcookie</span> and <span
class="function">setrawcookie</span> function.

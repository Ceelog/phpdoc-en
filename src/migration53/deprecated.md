Deprecated features in PHP 5.3.x
--------------------------------

PHP 5.3.0 introduces two new error levels: **`E_DEPRECATED`** and
**`E_USER_DEPRECATED`**. The **`E_DEPRECATED`** error level is used to
indicate that a function or feature has been deprecated. The
**`E_USER_DEPRECATED`** level is intended for indicating deprecated
features in user code, similarly to the **`E_USER_ERROR`** and
**`E_USER_WARNING`** levels.

The following is a list of deprecated INI directives. Use of any of
these INI directives will cause an **`E_DEPRECATED`** error to be thrown
at startup.

-   <span class="simpara">
    <a href="/network/setup.html#" class="link">define_syslog_variables</a>
    </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
    </span>
-   <span class="simpara">
    <a href="/ini/core.html#ini.register-long-arrays" class="link">register_long_arrays</a>
    </span>
-   <span class="simpara">
    <a href="/ini/sect/safe-mode.html#ini.safe-mode" class="link">safe_mode</a>
    </span>
-   <span class="simpara">
    <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>
    </span>
-   <span class="simpara">
    <a href="/info/setup.html#" class="link">magic_quotes_runtime</a>
    </span>
-   <span class="simpara">
    <a href="/book/sybase.html#" class="link">magic_quotes_sybase</a>
    </span>
-   <span class="simpara"> Comments starting with '\#' are now
    deprecated in .INI files. </span>

Deprecated functions:

-   <span class="simpara"> <span
    class="function">call\_user\_method</span> (use <span
    class="function">call\_user\_func</span> instead) </span>
-   <span class="simpara"> <span
    class="function">call\_user\_method\_array</span> (use <span
    class="function">call\_user\_func\_array</span> instead) </span>
-   <span class="simpara"> <span
    class="function">define\_syslog\_variables</span> </span>
-   <span class="simpara"> <span class="function">dl</span> </span>
-   <span class="simpara"> <span class="function">ereg</span> (use <span
    class="function">preg\_match</span> instead) </span>
-   <span class="simpara"> <span class="function">ereg\_replace</span>
    (use <span class="function">preg\_replace</span> instead) </span>
-   <span class="simpara"> <span class="function">eregi</span> (use
    <span class="function">preg\_match</span> with the *'i'* modifier
    instead) </span>
-   <span class="simpara"> <span class="function">eregi\_replace</span>
    (use <span class="function">preg\_replace</span> with the *'i'*
    modifier instead) </span>
-   <span class="simpara"> <span
    class="function">mcrypt\_generic\_end</span> </span>
-   <span class="simpara"> <span
    class="function">set\_magic\_quotes\_runtime</span> and its alias,
    <span class="function">magic\_quotes\_runtime</span> </span>
-   <span class="simpara"> <span
    class="function">session\_register</span> (use the `$_SESSION`
    superglobal instead) </span>
-   <span class="simpara"> <span
    class="function">session\_unregister</span> (use the `$_SESSION`
    superglobal instead) </span>
-   <span class="simpara"> <span
    class="function">session\_is\_registered</span> (use the `$_SESSION`
    superglobal instead) </span>
-   <span class="simpara"> <span
    class="function">set\_socket\_blocking</span> (use <span
    class="function">stream\_set\_blocking</span> instead) </span>
-   <span class="simpara"> <span class="function">split</span> (use
    <span class="function">preg\_split</span> instead) </span>
-   <span class="simpara"> <span class="function">spliti</span> (use
    <span class="function">preg\_split</span> with the *'i'* modifier
    instead) </span>
-   <span class="simpara"> <span class="function">sql\_regcase</span>
    </span>
-   <span class="simpara"> <span
    class="function">mysql\_db\_query</span> (use <span
    class="function">mysql\_select\_db</span> and <span
    class="function">mysql\_query</span> instead) </span>
-   <span class="simpara"> <span
    class="function">mysql\_escape\_string</span> (use <span
    class="function">mysql\_real\_escape\_string</span> instead) </span>
-   <span class="simpara"> Passing locale category names as strings is
    now deprecated. Use the LC\_\* family of constants instead. </span>
-   <span class="simpara"> The `is_dst` parameter to <span
    class="function">mktime</span>. Use the new timezone handling
    functions instead. </span>

Deprecated features:

-   <span class="simpara"> Assigning the return value of
    <a href="/language/oop5/basic.html#language.oop5.basic.new" class="link">new</a>
    by reference is now deprecated. </span>
-   <span class="simpara"> Call-time pass-by-reference is now
    deprecated. </span>

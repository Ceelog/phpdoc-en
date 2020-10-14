Backward Incompatible Changes
-----------------------------

Although most existing PHP 5 code should work without changes, please
take note of some backward incompatible changes:

-   <span class="simpara"> Safe mode is no longer supported. Any
    applications that rely on safe mode may need adjustment, in terms of
    security. </span>
-   <span class="simpara">
    <a href="/security/magicquotes.html" class="link">Magic quotes</a>
    has been removed. Applications relying on this feature may need to
    be updated, to avoid security issues. </span> <span class="simpara">
    <span class="function">get\_magic\_quotes\_gpc</span> and <span
    class="function">get\_magic\_quotes\_runtime</span> now always
    return **`FALSE`**. <span
    class="function">set\_magic\_quotes\_runtime</span> raises an
    **`E_CORE_ERROR`** level error on trying to enable
    <a href="/security/magicquotes.html" class="link">Magic quotes</a>.
    </span>
-   <span class="simpara"> The
    <a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
    and
    <a href="/ini/core.html#ini.register-long-arrays" class="link">register_long_arrays</a>
    `php.ini` directives have been removed. </span>
-   <span class="simpara"> The mbstring.script\_encoding directive has
    been removed. Use
    <a href="/ini/core.html#ini.zend.script-encoding" class="link">zend.script_encoding</a>
    instead. </span>
-   <span class="simpara">
    <a href="/language/references/pass.html" class="link">Call-time pass by reference</a>
    has been removed. </span>
-   <span class="simpara"> The
    <a href="/control-structures/break.html" class="link">break</a> and
    <a href="/control-structures/continue.html" class="link">continue</a>
    statements no longer accept variable arguments (e.g., *break 1 +
    foo() \* $bar;*). Static arguments still work, such as *break 2;*.
    As a side effect of this change *break 0;* and *continue 0;* are no
    longer allowed. </span>
-   <span class="simpara"> The default character set for <span
    class="function">htmlspecialchars</span>, <span
    class="function">htmlentities</span> and <span
    class="function">html\_entity\_decode</span> is now *UTF-8*, instead
    of *ISO-8859-1*. Note that changing your output charset via the
    <a href="/ini/core.html#ini.default-charset" class="link">default_charset</a>
    configuration setting does not affect htmlspecialchars/htmlentities
    unless you are passing "" (an empty string) as the encoding
    parameter to your <span
    class="function">htmlspecialchars</span>/<span
    class="function">htmlentities</span>/<span
    class="function">html\_entity\_decode</span> calls. Generally we do
    not recommend doing this because you should be able to change your
    output charset without affecting the runtime charset used by these
    functions. The safest approach is to explicitly set the charset on
    each call to <span class="function">htmlspecialchars</span>, <span
    class="function">htmlentities</span> and <span
    class="function">html\_entity\_decode</span>. </span>
-   <span class="simpara"> In the
    <a href="/book/datetime.html" class="link">date and time extension</a>,
    the timezone can no longer be set using the TZ environment variable.
    Instead you have to specify a timezone using the
    <a href="/datetime/setup.html#" class="link">date.timezone</a>
    `php.ini` option or <span
    class="function">date\_default\_timezone\_set</span> function. PHP
    will no longer attempt to guess the timezone, and will instead fall
    back to "UTC" and issue a **`E_WARNING`**. </span>
-   <span class="simpara"> Non-numeric string offsets - e.g.
    *$a\['foo'\]* where $a is a string - now return false on <span
    class="function">isset</span> and true on <span
    class="function">empty</span>, and produce a **`E_WARNING`** if you
    try to use them. Offsets of types double, bool and null produce a
    **`E_NOTICE`**. Numeric strings (e.g. *$a\['2'\]*) still work as
    before. Note that offsets like *'12.3'* and *'5 foobar'* are
    considered non-numeric and produce a **`E_WARNING`**, but are
    converted to 12 and 5 respectively, for backward compatibility
    reasons. </span> <span class="simpara"> Note: Following code returns
    different result. </span> <span class="simpara">
    $str='abc';var\_dump(isset($str\['x'\])); // false for PHP 5.4 or
    later, but true for 5.3 or less </span>
-   <span class="simpara"> Converting an array to a string will now
    generate an **`E_NOTICE`** level error, but the result of the cast
    will still be the string *"Array"*. </span>
-   <span class="simpara"> Turning **`NULL`**, **`FALSE`**, or an empty
    string into an object by adding a property will now emit an
    **`E_WARNING`** level error, instead of **`E_STRICT`**. </span>
-   <span class="simpara"> Parameter names that shadow super globals now
    cause a fatal error. This prohibits code like *function foo($\_GET,
    $\_POST) {}*. </span>
-   <span class="simpara"> The Salsa10 and Salsa20
    <a href="/book/hash.html" class="link">hash algorithms</a> have been
    removed. </span>
-   <span class="simpara"> The Tiger
    <a href="/book/hash.html" class="link">hash algorithm</a> now uses
    big-endian byte ordering. Please follow
    <a href="/ref/hash.html#Calculate%20pre%20PHP-5.4%20tiger%20hashes%20with%20PHP-5.4%20and%20higher" class="link">this example</a>
    to write code that is compatible with both PHP 5.3 and 5.4. </span>
-   <span class="simpara"> <span class="function">array\_combine</span>
    now returns *array()* instead of **`FALSE`** when two empty arrays
    are provided as parameters. </span>
-   <span class="simpara"> If you use <span
    class="function">htmlentities</span> with asian character sets, it
    works like <span class="function">htmlspecialchars</span> - this has
    always been the case in previous versions of PHP, but now an
    **`E_STRICT`** level error is emitted. </span>
-   <span class="simpara"> The third parameter of <span
    class="function">ob\_start</span> has changed from <span
    class="type">boolean</span> `erase` to <span
    class="type">integer</span> `flags`. Note that code that explicitly
    set `erase` to **`FALSE`** will no longer behave as expected in PHP
    5.4: please follow
    <a href="/ref/outcontrol.html#Creating%20an%20uneraseable%20output%20buffer%20in%20a%20way%20compatible%20with%20both%20PHP%205.3%20and%205.4" class="link">this example</a>
    to write code that is compatible with PHP 5.3 and 5.4. </span>

The following keywords are now
<a href="/reserved.html" class="link">reserved</a>, and may not be used
as names by functions, classes, etc.

-   <span class="simpara">
    <a href="/language/oop5/traits.html" class="link">trait</a> </span>
-   <span class="simpara">
    <a href="/language/types/callable.html" class="link">callable</a>
    </span>
-   <span class="simpara">
    <a href="/language/oop5/traits.html" class="link">insteadof</a>
    </span>

The following functions have been removed from PHP:

-   <span class="simpara"> <span
    class="function">define\_syslog\_variables</span> </span>
-   <span class="simpara"> <span
    class="function">import\_request\_variables</span> </span>
-   <span class="simpara"> <span
    class="function">session\_is\_registered</span>, <span
    class="function">session\_register</span> and <span
    class="function">session\_unregister</span>. </span>
-   <span class="simpara"> The aliases <span
    class="function">mysqli\_bind\_param</span>, <span
    class="function">mysqli\_bind\_result</span>, <span
    class="function">mysqli\_client\_encoding</span>, <span
    class="function">mysqli\_fetch</span>, <span
    class="function">mysqli\_param\_count</span>, <span
    class="function">mysqli\_get\_metadata</span>, <span
    class="function">mysqli\_send\_long\_data</span>,
    mysqli::client\_encoding() and mysqli\_stmt::stmt(). </span>

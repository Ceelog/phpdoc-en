What are Magic Quotes
---------------------

**Warning**

This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

When on, all *'* (single-quote), *"* (double quote), *\\* (backslash)
and *NULL* characters are escaped with a backslash automatically. This
is identical to what <span class="function">addslashes</span> does.

There are three magic quote directives:

-   <span class="simpara">
    <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>
    </span> <span class="simpara"> Affects HTTP Request data (GET, POST,
    and COOKIE). Cannot be set at runtime, and defaults to *on* in PHP.
    </span> <span class="simpara"> See also <span
    class="function">get\_magic\_quotes\_gpc</span>. </span>
-   <span class="simpara">
    <a href="/info/setup.html#" class="link">magic_quotes_runtime</a>
    </span> <span class="simpara"> If enabled, most functions that
    return data from an external source, including databases and text
    files, will have quotes escaped with a backslash. Can be set at
    runtime, and defaults to *off* in PHP. </span> <span
    class="simpara"> See also <span
    class="function">set\_magic\_quotes\_runtime</span> and <span
    class="function">get\_magic\_quotes\_runtime</span>. </span>
-   <span class="simpara"> magic\_quotes\_sybase </span> <span
    class="simpara"> If enabled, a single-quote is escaped with a
    single-quote instead of a backslash. If on, it completely overrides
    <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>.
    Having both directives enabled means only single quotes are escaped
    as *''*. Double quotes, backslashes and NULL's will remain untouched
    and unescaped. </span> <span class="simpara"> See also <span
    class="function">ini\_get</span> for retrieving its value. </span>

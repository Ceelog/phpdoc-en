Deprecated features in PHP 5.6.x
--------------------------------

### Calls from incompatible context

Methods called from an incompatible context are now deprecated, and will
generate **`E_DEPRECATED`** errors when invoked instead of
**`E_STRICT`**. Support for these calls will be removed in a future
version of PHP.

An example of such a call is:

``` php
<?php
class A {
    function f() { echo get_class($this); }
}

class B {
    function f() { A::f(); }
}

(new B)->f();
?>
```

The above example will output:

    Deprecated: Non-static method A::f() should not be called statically, assuming $this from incompatible context in - on line 7
    B

### `$HTTP_RAW_POST_DATA` and <a href="/ini/core.html#ini.always-populate-raw-post-data" class="link">always_populate_raw_post_data</a>

<a href="/ini/core.html#ini.always-populate-raw-post-data" class="link">always_populate_raw_post_data</a>
will now generate an **`E_DEPRECATED`** error when `$HTTP_RAW_POST_DATA`
is populated. New code should use
<a href="/wrappers/php.html#wrappers.php.input" class="link"><em>php://input</em></a>
instead of `$HTTP_RAW_POST_DATA`, which will be removed in a future
release. You can opt in for the new behaviour (in which
`$HTTP_RAW_POST_DATA` is never defined hence no **`E_DEPRECATED`** error
will be generated) by setting
<a href="/ini/core.html#ini.always-populate-raw-post-data" class="link">always_populate_raw_post_data</a>
to *-1*.

### <a href="/book/iconv.html" class="link">iconv</a> and <a href="/book/mbstring.html" class="link">mbstring</a> encoding settings

The <a href="/book/iconv.html" class="link">iconv</a> and
<a href="/book/mbstring.html" class="link">mbstring</a> configuration
options related to encoding have been deprecated in favour of
<a href="/ini/core.html#ini.default-charset" class="link"><code class="parameter">default_charset</code></a>.
The deprecated options are:

-   <span class="simpara">
    <a href="/iconv/setup.html#" class="link"><code class="parameter">iconv.input_encoding</code></a>
    </span>
-   <span class="simpara">
    <a href="/iconv/setup.html#" class="link"><code class="parameter">iconv.output_encoding</code></a>
    </span>
-   <span class="simpara">
    <a href="/iconv/setup.html#" class="link"><code class="parameter">iconv.internal_encoding</code></a>
    </span>
-   <span class="simpara">
    <a href="/mbstring/setup.html#" class="link"><code class="parameter">mbstring.http_input</code></a>
    </span>
-   <span class="simpara">
    <a href="/mbstring/setup.html#" class="link"><code class="parameter">mbstring.http_output</code></a>
    </span>
-   <span class="simpara">
    <a href="/mbstring/setup.html#" class="link"><code class="parameter">mbstring.internal_encoding</code></a>
    </span>

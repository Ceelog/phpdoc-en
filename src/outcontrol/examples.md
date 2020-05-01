Examples
========

**Table of Contents**

-   [Basic usage](/outcontrol/examples.html#Basic%20usage)
-   [Output rewrite
    usage](/outcontrol/examples.html#Output%20rewrite%20usage)

Basic usage
-----------

**Example \#1 Output Control example**

``` php
<?php

ob_start();
echo "Hello\n";

setcookie("cookiename", "cookiedata");

ob_end_flush();

?>
```

In the above example, the output from <span class="function">echo</span>
would be stored in the output buffer until <span
class="function">ob\_end\_flush</span> was called. In the mean time, the
call to <span class="function">setcookie</span> successfully stored a
cookie without causing an error. (Headers cannot normally be sent to the
browser after data has already been sent.)

Output rewrite usage
--------------------

Since PHP 7.1.0, <span
class="function">output\_add\_rewrite\_var</span>, <span
class="function">output\_reset\_rewrite\_vars</span> use dedicated
output buffer. i.e. It does not use
<a href="/session/setup.html#" class="link">trans sid</a> output buffer.

**Example \#1 Output rewrite example**

``` php
<?php
// This code works with PHP 7.1.0, 7.0.10, 5.6.25 and up.

// HTTP_HOST is default target host. Set manually to make sample code works.
$_SERVER['HTTP_HOST'] = 'php.net';

// Output rewriter only rewrite form. Add a=href.
// Tags can be specified tag_name=url_attr, e.g. img=src,iframe=src
// No space allowed between settings.
// Form tag is special tag that add hidden input.
ini_set('url_rewriter.tags','a=href,form=');
var_dump(ini_get('url_rewriter.tags'));

// This is added to URL and form
output_add_rewrite_var('test', 'value');
?>
<a href="//php.net/index.php?bug=1234">bug1234</a>
<form action="https://php.net/?bug=1234&edit=1" action="post">
 <input type="text" name="title" />
</form>
```

The above example will output:

    <a href="//php.net/?bug=1234&test=value">bug1234</a>
    <form action="https://php.net/?bug=1234&edit=1" method="post"><input type="hidden" name="test" value="value" />
     <input type="text" name="title" />
    </form>

Since PHP 7.1.0, output rewrite functions have it's own INI settings,
<a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a> and
<a href="/outcontrol/setup.html#" class="link">url_rewriter.hosts</a>.

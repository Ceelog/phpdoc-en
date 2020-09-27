Using PHP
=========

This section gathers many common errors that you may face while writing
PHP scripts.

1.  [I cannot remember the parameter order of PHP functions, are they
    random?](#faq.using.parameterorder)
2.  [I would like to write a generic PHP script that can handle data
    coming from any form. How do I know which POST method variables are
    available?](#faq.using.anyform)
3.  [I need to convert all single-quotes (') to a backslash followed by
    a single-quote (\\'). How can I do this with a regular expression?
    I'd also like to convert " to \\" and \\ to
    \\\\.](#faq.using.addslashes)
4.  [All my " turn into \\" and my ' turn into \\', how do I get rid of
    all these unwanted backslashes? How and why did they get
    there?](#faq.using.stripslashes)
5.  [How does the PHP directive register\_globals affect
    me?](#faq.register-globals)
6.  [When I do the following, the output is printed in the wrong order:
    \<?php function myfunc($argument) { echo $argument + 10; } $variable
    = 10; echo "myfunc($variable) = " . myfunc($variable); ?\> what's
    going on?](#faq.using.wrong-order)
7.  [Hey, what happened to my newlines? \<pre\> \<?php echo "This should
    be the first line."; ?\> \<?php echo "This should show up after the
    new line above."; ?\> \</pre\>](#faq.using.newlines)
8.  [I get the message 'Warning: Cannot send session cookie - headers
    already sent...' or 'Cannot add header information - headers already
    sent...'.](#faq.using.headers-sent)
9.  [I need to access information in the request header directly. How
    can I do this?](#faq.using.header)
10. [When I try to use authentication with IIS I get 'No Input file
    specified'.](#faq.using.authentication)
11. [Windows: I can't access files shared on another computer using
    IIS](#faq.using.iis.sharing)
12. [How am I supposed to mix XML and PHP? It complains about my \<?xml
    tags!](#faq.using.mixml)
13. [Where can I find a complete list of variables are available to me
    in PHP?](#faq.using.variables)
14. [How can I generate PDF files without using the non-free and
    commercial libraries like PDFLib? I'd like something that's free and
    doesn't require external PDF libraries.](#faq.using.freepdf)
15. [I'm trying to access one of the standard CGI variables (such as
    $DOCUMENT\_ROOT or $HTTP\_REFERER) in a user-defined function, and
    it can't seem to find it. What's wrong?](#faq.using.cgi-vars)
16. [A few PHP directives may also take on shorthand byte values, as
    opposed to only integer byte values. What are all the available
    shorthand byte options?](#faq.using.shorthandbytes)
17. [Windows: I keep getting connection timeouts when using localhost,
    whereas "127.0.0.1" works?](#faq.using.windowslocalhostissue)

**I cannot remember the parameter order of PHP functions, are they random?**  
PHP is a glue that brings together hundreds of external libraries, so
sometimes this gets messy. However, a simple rule of thumb is as
follows:

<a href="/book/array.html" class="link">Array function</a> parameters
are ordered as "*needle, haystack*" whereas
<a href="/book/strings.html" class="link">String functions</a> are the
opposite, so "*haystack, needle*".

<!-- -->

**I would like to write a generic PHP script that can handle data coming from any form. How do I know which POST method variables are available?**  
PHP offers many
<a href="/language/variables/predefined.html" class="link">predefined variables</a>,
like the superglobal `       $_POST`. You may loop through `$_POST` as
it's an associate array of all POSTed values. For example, let's simply
loop through it with
<a href="/control-structures/foreach.html" class="link">foreach</a>,
check for <span class="function">empty</span> values, and print them
out.

``` php
<?php
$empty = $post = array();
foreach ($_POST as $varname => $varvalue) {
    if (empty($varvalue)) {
        $empty[$varname] = $varvalue;
    } else {
        $post[$varname] = $varvalue;
    }
}

print "<pre>";
if (empty($empty)) {
    print "None of the POSTed values are empty, posted:\n";
    var_dump($post);
} else {
    print "We have " . count($empty) . " empty values\n";
    print "Posted:\n"; var_dump($post);
    print "Empty:\n";  var_dump($empty);
    exit;
}
?>
```

<!-- -->

**I need to convert all single-quotes (') to a backslash followed by a single-quote (\\'). How can I do this with a regular expression? I'd also like to convert " to \\" and \\ to \\\\.**  
Assuming this is for a database, use the escaping mechanism that comes
with the database. For example, use <span
class="function">mysql\_real\_escape\_string</span> with MySQL and <span
class="function">pg\_escape\_string</span> with PostgreSQL. There is
also the generic <span class="function">addslashes</span> and <span
class="function">stripslashes</span> functions, that are more common
with older PHP code.

> **Note**: **directive note: magic\_quotes\_gpc**  
>
> The <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>
> directive defaults to *on*. It essentially runs <span
> class="function">addslashes</span> on all GET, POST, and COOKIE data.
> <span class="function">stripslashes</span> may be used to remove them.

<!-- -->

**All my " turn into \\" and my ' turn into \\', how do I get rid of all these unwanted backslashes? How and why did they get there?**  
Most likely the backslashes magically exist because the PHP directive
<a href="/info/setup.html#" class="link">magic_quotes_gpc</a> is on.
This is an old feature of PHP, and should be disabled and not relied
upon. Also, the PHP function <span class="function">stripslashes</span>
may be used to strip the backslashes from the <span
class="type">string</span>.

> **Note**: **directive note: magic\_quotes\_gpc**  
>
> The <a href="/info/setup.html#" class="link">magic_quotes_gpc</a>
> directive defaults to *on*. It essentially runs <span
> class="function">addslashes</span> on all GET, POST, and COOKIE data.
> <span class="function">stripslashes</span> may be used to remove them.

<!-- -->

**How does the PHP directive register\_globals affect me?**  
**Warning**
This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

First, an explanation about what this ini setting does. Let's say the
following URL is used: *http://example.com/foo.php?animal=cat* and in
`foo.php` we might have the following PHP code:

``` php
<?php
// Using $_GET here is preferred
echo $_GET['animal'];

// For $animal to exist, register_globals must be on
// DO NOT DO THIS
echo $animal;

// This applies to all variables, so $_SERVER too
echo $_SERVER['PHP_SELF'];

// Again, for $PHP_SELF to exist, register_globals must be on
// DO NOT DO THIS
echo $PHP_SELF;
?>
```

The code above demonstrates how register\_globals creates a lot of
variables. For years this type of coding has been frowned upon, and for
years it's been disabled by default. So although most web hosts disable
register\_globals, there are still outdated articles, tutorials, and
books that require it to be on. Plan accordingly.

See also the following resources for additional information:

-   The
    <a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
    directive
-   The
    <a href="/security/globals.html" class="link">security chapter about register globals</a>
-   <a href="/language/variables/external.html" class="link">Handling external variables</a>
-   Use
    <a href="/language/variables/superglobals.html" class="link">superglobals</a>
    instead

> **Note**:
>
> In the example above, we used an URL that contained a QUERY\_STRING.
> Passing information like this is done through a GET HTTP Request, so
> this is why the superglobal `$_GET` was used.

**When I do the following, the output is printed in the wrong order:**

``` php
<?php
function myfunc($argument)
{
    echo $argument + 10;
}
$variable = 10;
echo "myfunc($variable) = " . myfunc($variable);
?>
```

what's going on?

To be able to use the results of your function in an expression (such as
concatenating it with other strings in the example above), you need to
<span class="function">return</span> the value, not <span
class="function">echo</span> it.

**Hey, what happened to my newlines?**

``` php
<pre>
<?php echo "This should be the first line."; ?>
<?php echo "This should show up after the new line above."; ?>
</pre>
```

In PHP, the ending for a block of code is either "?\>" or "?\>\\n"
(where \\n means a newline). So in the example above, the echoed
sentences will be on one line, because PHP omits the newlines after the
block ending. This means that you need to insert an extra newline after
each block of PHP code to make it print out one newline.

Why does PHP do this? Because when formatting normal HTML, this usually
makes your life easier because you don't want that newline, but you'd
have to create extremely long lines or otherwise make the raw page
source unreadable to achieve that effect.

**I get the message 'Warning: Cannot send session cookie - headers already sent...' or 'Cannot add header information - headers already sent...'.**  
The functions <span class="function">header</span>, <span
class="function">setcookie</span>, and the
<a href="/ref/session.html" class="link">session functions</a> need to
add headers to the output stream but headers can only be sent before all
other content. There can be no output before using these functions,
output such as HTML. The function <span
class="function">headers\_sent</span> will check if your script has
already sent headers and see also the
<a href="/ref/outcontrol.html" class="link">Output Control functions</a>.

<!-- -->

**I need to access information in the request header directly. How can I do this?**  
The <span class="function">getallheaders</span> function will do this if
you are running PHP as an Apache module. So, the following bit of code
will show you all the request headers:

``` php
<?php
$headers = getallheaders();
foreach ($headers as $name => $content) {
    echo "headers[$name] = $content<br />\n";
}
?>
```

See also <span class="function">apache\_lookup\_uri</span>, <span
class="function">apache\_response\_headers</span>, and <span
class="function">fsockopen</span>

<!-- -->

**When I try to use authentication with IIS I get 'No Input file specified'.**  
The security model of IIS is at fault here. This is a problem common to
all CGI programs running under IIS. A workaround is to create a plain
HTML file (not parsed by PHP) as the entry page into an authenticated
directory. Then use a META tag to redirect to the PHP page, or have a
link to the PHP page. PHP will then recognize the authentication
correctly. This should not affect other NT web servers. For more
information, see:
<a href="http://support.microsoft.com/kb/q160422/" class="link external">» http://support.microsoft.com/kb/q160422/</a>
and the manual section on
<a href="/features/http-auth.html" class="link">HTTP Authentication</a>
.

<!-- -->

**Windows: I can't access files shared on another computer using IIS**  
You have to change the *Go to Internet Information Services*. Locate
your PHP file and go to its properties. Go to the *File Security* tab,
*Edit -\< Anonymous access and authentication control*.

You can fix the problem either by unticking *Anonymous Access* and
leaving *Integrated Window Authentication* ticked, or, by ticking
*Anonymous Access* and editing the user as he may not have the access
right.

<!-- -->

**How am I supposed to mix XML and PHP? It complains about my \<?xml tags!**  
In order to embed \<?xml straight into your PHP code, you'll have to
turn off short tags by having the PHP directive
<a href="/ini/core.html#ini.short-open-tag" class="link">short_open_tags</a>
set to *0*. You cannot set this directive with <span
class="function">ini\_set</span>. Regardless of
<a href="/ini/core.html#ini.short-open-tag" class="link">short_open_tags</a>
being on or off, you can do something like: *\<?php echo '\<?xml'; ?\>*.
The default for this directive is *On*.

<!-- -->

**Where can I find a complete list of variables are available to me in PHP?**  
Read the manual page on
<a href="/language/variables/predefined.html" class="link">predefined variables</a>
as it includes a partial list of predefined variables available to your
script. A complete list of available variables (and much more
information) can be seen by calling the <span
class="function">phpinfo</span> function. Be sure to read the manual
section on
<a href="/language/variables/external.html" class="link">variables from outside of PHP</a>
as it describes common scenarios for external variables, like from a
HTML form, a Cookie, and the URL.

> **Note**: **register\_globals: important note**  
>
> As of PHP 4.2.0, the default value for the PHP directive
> <a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
> is *off*. The PHP community discourages developers from relying on
> this directive, and encourages the use of other means, such as the
> <a href="/language/variables/predefined.html" class="link">superglobals</a>.

<!-- -->

**How can I generate PDF files without using the non-free and commercial libraries like <a href="/ref/pdf.html" class="link">PDFLib</a>? I'd like something that's free and doesn't require external PDF libraries.**  
There are a few alternatives written in PHP such as
<a href="http://www.fpdf.org/" class="link external">» FPDF</a> and
<a href="http://www.tcpdf.org/" class="link external">» TCPDF</a>.

<!-- -->

**I'm trying to access one of the standard CGI variables (such as `$DOCUMENT_ROOT` or `$HTTP_REFERER`) in a user-defined function, and it can't seem to find it. What's wrong?**  
It's important to realize that the PHP directive
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
also affects server and environment variables. When register\_globals =
off (the default is off since PHP 4.2.0), `$DOCUMENT_ROOT` will not
exist. Instead, use `$_SERVER['DOCUMENT_ROOT']       `. If
register\_globals = on then the variables `$DOCUMENT_ROOT` and
`$GLOBALS['DOCUMENT_ROOT']` will also exist.

If you're sure register\_globals = on and wonder why `$DOCUMENT_ROOT`
isn't available inside functions, it's because these are like any other
variables and would require *global $DOCUMENT\_ROOT* inside the
function. See also the manual page on
<a href="/language/variables/scope.html" class="link">variable scope</a>.
It's preferred to code with register\_globals = off.

<!-- -->

**A few PHP directives may also take on shorthand byte values, as opposed to only <span class="type">integer</span> byte values. What are all the available shorthand byte options?**  
The available options are K (for Kilobytes), M (for Megabytes) and G
(for Gigabytes; available since PHP 5.1.0), and are all
case-insensitive. Anything else assumes bytes. *1M* equals one Megabyte
or *1048576* bytes. *1K* equals one Kilobyte or *1024* bytes. These
shorthand notations may be used in `php.ini` and in the <span
class="function">ini\_set</span> function. Note that the numeric value
is cast to <span class="type">integer</span>; for instance, *0.5M* is
interpreted as *0*.

> **Note**: **kilobyte versus kibibyte**  
>
> The PHP notation describes one kilobyte as equalling 1024 bytes,
> whereas the IEC standard considers this to be a kibibyte instead.
> Summary: k and K = 1024 bytes.

<!-- -->

**Windows: I keep getting connection timeouts when using *localhost*, whereas *"127.0.0.1"* works?**  
Prior to PHP 5.3.4, there was a bug in the network resolving code inside
PHP that caused *localhost* in all stream related situations to fail if
IPv6 was enabled. To work around this issue you can either use
*"127.0.0.1"* or disable IPv6 resolving in the `hosts` file.

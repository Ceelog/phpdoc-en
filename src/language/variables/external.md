Variables From External Sources
-------------------------------

### HTML Forms (GET and POST)

When a form is submitted to a PHP script, the information from that form
is automatically made available to the script. There are few ways to
access this information, for example:

**Example \#1 A simple HTML form**

``` html
<form action="foo.php" method="post">
    Name:  <input type="text" name="username" /><br />
    Email: <input type="text" name="email" /><br />
    <input type="submit" name="submit" value="Submit me!" />
</form>
```

There are only two ways to access data from your HTML forms. Currently
available methods are listed below:

**Example \#2 Accessing data from a simple POST HTML form**

``` php
<?php
echo $_POST['username'];
echo $_REQUEST['username'];
?>
```

Using a GET form is similar except you'll use the appropriate GET
predefined variable instead. GET also applies to the *QUERY\_STRING*
(the information after the '?' in a URL). So, for example,
*http://www.example.com/test.php?id=3* contains GET data which is
accessible with `$_GET['id']`. See also `$_REQUEST`.

> **Note**:
>
> Dots and spaces in variable names are converted to underscores. For
> example *\<input name="a.b" /\>* becomes *$\_REQUEST\["a\_b"\]*.

PHP also understands arrays in the context of form variables (see the
<a href="/faq/html.html" class="link">related faq</a>). You may, for
example, group related variables together, or use this feature to
retrieve values from a multiple select input. For example, let's post a
form to itself and upon submission display the data:

**Example \#3 More complex form variables**

``` php
<?php
if ($_POST) {
    echo '<pre>';
    echo htmlspecialchars(print_r($_POST, true));
    echo '</pre>';
}
?>
<form action="" method="post">
    Name:  <input type="text" name="personal[name]" /><br />
    Email: <input type="text" name="personal[email]" /><br />
    Beer: <br />
    <select multiple name="beer[]">
        <option value="warthog">Warthog</option>
        <option value="guinness">Guinness</option>
        <option value="stuttgarter">Stuttgarter Schwabenbräu</option>
    </select><br />
    <input type="submit" value="submit me!" />
</form>
```

> **Note**: <span class="simpara"> If an external variable name begins
> with a valid array syntax, trailing characters are silently ignored.
> For example, *\<input name="foo\[bar\]baz"\>* becomes
> *$\_REQUEST\['foo'\]\['bar'\]*. </span>

#### IMAGE SUBMIT variable names

When submitting a form, it is possible to use an image instead of the
standard submit button with a tag like:

``` html
<input type="image" src="image.gif" name="sub" />
```

When the user clicks somewhere on the image, the accompanying form will
be transmitted to the server with two additional variables, `sub_x` and
`sub_y`. These contain the coordinates of the user click within the
image. The experienced may note that the actual variable names sent by
the browser contains a period rather than an underscore, but PHP
converts the period to an underscore automatically.

### HTTP Cookies

PHP transparently supports HTTP cookies as defined by
<a href="http://www.faqs.org/rfcs/rfc6265" class="link external">» RFC 6265</a>.
Cookies are a mechanism for storing data in the remote browser and thus
tracking or identifying return users. You can set cookies using the
<span class="function">setcookie</span> function. Cookies are part of
the HTTP header, so the SetCookie function must be called before any
output is sent to the browser. This is the same restriction as for the
<span class="function">header</span> function. Cookie data is then
available in the appropriate cookie data arrays, such as `$_COOKIE` as
well as in `$_REQUEST`. See the <span class="function">setcookie</span>
manual page for more details and examples.

> **Note**: <span class="simpara"> As of PHP 7.2.34, 7.3.23 and 7.4.11,
> respectively, the *names* of incoming cookies are no longer
> url-decoded for security reasons. </span>

If you wish to assign multiple values to a single cookie variable, you
may assign it as an array. For example:

``` php
<?php
  setcookie("MyCookie[foo]", 'Testing 1', time()+3600);
  setcookie("MyCookie[bar]", 'Testing 2', time()+3600);
?>
```

That will create two separate cookies although `MyCookie` will now be a
single array in your script. If you want to set just one cookie with
multiple values, consider using <span class="function">serialize</span>
or <span class="function">explode</span> on the value first.

Note that a cookie will replace a previous cookie by the same name in
your browser unless the path or domain is different. So, for a shopping
cart application you may want to keep a counter and pass this along.
i.e.

**Example \#4 A <span class="function">setcookie</span> example**

``` php
<?php
if (isset($_COOKIE['count'])) {
    $count = $_COOKIE['count'] + 1;
} else {
    $count = 1;
}
setcookie('count', $count, time()+3600);
setcookie("Cart[$count]", $item, time()+3600);
?>
```

### Dots in incoming variable names

Typically, PHP does not alter the names of variables when they are
passed into a script. However, it should be noted that the dot (period,
full stop) is not a valid character in a PHP variable name. For the
reason, look at it:

``` php
<?php
$varname.ext;  /* invalid variable name */
?>
```

Now, what the parser sees is a variable named `$varname`, followed by
the string concatenation operator, followed by the barestring (i.e.
unquoted string which doesn't match any known key or reserved words)
'ext'. Obviously, this doesn't have the intended result.

For this reason, it is important to note that PHP will automatically
replace any dots in incoming variable names with underscores.

### Determining variable types

Because PHP determines the types of variables and converts them
(generally) as needed, it is not always obvious what type a given
variable is at any one time. PHP includes several functions which find
out what type a variable is, such as: <span
class="function">gettype</span>, <span
class="function">is\_array</span>, <span
class="function">is\_float</span>, <span
class="function">is\_int</span>, <span
class="function">is\_object</span>, and <span
class="function">is\_string</span>. See also the chapter on
<a href="/language/types.html" class="link">Types</a>.

HTTP being a text protocol, most, if not all, content that comes in
<a href="/language/variables/superglobals.html" class="link">Superglobal arrays</a>,
like `$_POST` and `$_GET` will remain as strings. PHP will not try to
convert values to a specific type. In the example below, `$_GET["var1"]`
will contain the string "null" and `$_GET["var2"]`, the string "123".

    /index.php?var1=null&var2=123

### Changelog

| Version                | Description                                                                     |
|------------------------|---------------------------------------------------------------------------------|
| 7.2.34, 7.3.23, 7.4.11 | The *names* of incoming cookies are no longer url-decoded for security reasons. |

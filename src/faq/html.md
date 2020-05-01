PHP and HTML
============

PHP and HTML interact a lot: PHP can generate HTML, and HTML can pass
information to PHP. Before reading these faqs, it's important you learn
how to retrieve
<a href="/language/variables/external.html" class="link">variables from external sources</a>.
The manual page on this topic includes many examples as well.

1.  [What encoding/decoding do I need when I pass a value through a
    form/URL?](#faq.html.encoding)
2.  [I'm trying to use an \<input type="image"\> tag, but the $foo.x and
    $foo.y variables aren't available. $\_GET\['foo.x'\] isn't existing
    either. Where are they?](#faq.html.form-image)
3.  [How do I create arrays in a HTML \<form\>?](#faq.html.arrays)
4.  [How do I get all the results from a select multiple HTML
    tag?](#faq.html.select-multiple)
5.  [How can I pass a variable from Javascript to
    PHP?](#faq.html.javascript-variable)

**What encoding/decoding do I need when I pass a value through a form/URL?**  
There are several stages for which encoding is important. Assuming that
you have a <span class="type">string</span> `$data`, which contains the
string you want to pass on in a non-encoded way, these are the relevant
stages:

-   HTML interpretation. In order to specify a random string, you *must*
    include it in double quotes, and <span
    class="function">htmlspecialchars</span> the whole value.

-   URL: A URL consists of several parts. If you want your data to be
    interpreted as one item, you *must* encode it with <span
    class="function">urlencode</span>.

**Example \#1 A hidden HTML form element**

``` php
<?php
    echo '<input type="hidden" value="' . htmlspecialchars($data) . '" />'."\n";
?>
```

> **Note**: <span class="simpara"> It is wrong to <span
> class="function">urlencode</span> `$data`, because it's the browsers
> responsibility to <span class="function">urlencode</span> the data.
> All popular browsers do that correctly. Note that this will happen
> regardless of the method (i.e., GET or POST). You'll only notice this
> in case of GET request though, because POST requests are usually
> hidden. </span>

**Example \#2 Data to be edited by the user**

``` php
<?php
    echo "<textarea name='mydata'>\n";
    echo htmlspecialchars($data)."\n";
    echo "</textarea>";
?>
```

> **Note**: <span class="simpara"> The data is shown in the browser as
> intended, because the browser will interpret the HTML escaped symbols.
> </span> <span class="simpara"> Upon submitting, either via GET or
> POST, the data will be urlencoded by the browser for transferring, and
> directly urldecoded by PHP. So in the end, you don't need to do any
> urlencoding/urldecoding yourself, everything is handled automagically.
> </span>

**Example \#3 In a URL**

``` php
<?php
    echo '<a href="' . htmlspecialchars("/nextpage.php?stage=23&data=" .
        urlencode($data)) . '">'."\n";
?>
```

> **Note**: <span class="simpara"> In fact you are faking a HTML GET
> request, therefore it's necessary to manually <span
> class="function">urlencode</span> the data. </span>

> **Note**: <span class="simpara"> You need to <span
> class="function">htmlspecialchars</span> the whole URL, because the
> URL occurs as value of an HTML-attribute. In this case, the browser
> will first un-<span class="function">htmlspecialchars</span> the
> value, and then pass the URL on. PHP will understand the URL
> correctly, because you <span class="function">urlencode</span>d the
> data. </span> <span class="simpara"> You'll notice that the *&* in the
> URL is replaced by *&amp;*. Although most browsers will recover if you
> forget this, this isn't always possible. So even if your URL is not
> dynamic, you *need* to <span class="function">htmlspecialchars</span>
> the URL. </span>

<!-- -->

**I'm trying to use an \<input type="image"\> tag, but the `$foo.x` and `$foo.y` variables aren't available. `$_GET['foo.x']` isn't existing either. Where are they?**  
When submitting a form, it is possible to use an image instead of the
standard submit button with a tag like:

``` html
<input type="image" src="image.gif" name="foo" />
```

When the user clicks somewhere on the image, the accompanying form will
be transmitted to the server with two additional variables: `foo.x` and
`foo.y`.

Because `foo.x` and `foo.y` would make invalid variable names in PHP,
they are automagically converted to `foo_x` and `foo_y`. That is, the
periods are replaced with underscores. So, you'd access these variables
like any other described within the section on retrieving
<a href="/language/variables/external.html" class="link">variables from external sources</a>.
For example, `$_GET['foo_x']`.

> **Note**:
>
> Spaces in request variable names are converted to underscores.

<!-- -->

**How do I create arrays in a HTML \<form\>?**  
To get your \<form\> result sent as an
<a href="/language/types/array.html" class="link">array</a> to your PHP
script you name the \<input\>, \<select\> or \<textarea\> elements like
this:

``` html
<input name="MyArray[]" />
<input name="MyArray[]" />
<input name="MyArray[]" />
<input name="MyArray[]" />
```

Notice the square brackets after the variable name, that's what makes it
an array. You can group the elements into different arrays by assigning
the same name to different elements:

``` html
<input name="MyArray[]" />
<input name="MyArray[]" />
<input name="MyOtherArray[]" />
<input name="MyOtherArray[]" />
```

This produces two arrays, MyArray and MyOtherArray, that gets sent to
the PHP script. It's also possible to assign specific keys to your
arrays:

``` html
<input name="AnotherArray[]" />
<input name="AnotherArray[]" />
<input name="AnotherArray[email]" />
<input name="AnotherArray[phone]" />
```

The AnotherArray array will now contain the keys 0, 1, email and phone.

> **Note**:
>
> Specifying array keys is optional in HTML. If you do not specify the
> keys, the array gets filled in the order the elements appear in the
> form. Our first example will contain keys 0, 1, 2 and 3.

See also <a href="/ref/array.html" class="link">Array Functions</a> and
<a href="/language/variables/external.html" class="link">Variables From External Sources</a>.

<!-- -->

**How do I get all the results from a select multiple HTML tag?**  
The select multiple tag in an HTML construct allows users to select
multiple items from a list. These items are then passed to the action
handler for the form. The problem is that they are all passed with the
same widget name. I.e.

``` html
<select name="var" multiple="yes">
```

Each selected option will arrive at the action handler as:

    var=option1
    var=option2
    var=option3
          

Each option will overwrite the contents of the previous `$var` variable.
The solution is to use PHP's "array from form element" feature. The
following should be used:

``` html
<select name="var[]" multiple="yes">
```

This tells PHP to treat `$var` as an array and each assignment of a
value to var\[\] adds an item to the array. The first item becomes
`$var[0]`, the next `$var[1]`, etc. The <span
class="function">count</span> function can be used to determine how many
options were selected, and the <span class="function">sort</span>
function can be used to sort the option array if necessary.

Note that if you are using JavaScript the *\[\]* on the element name
might cause you problems when you try to refer to the element by name.
Use it's numerical form element ID instead, or enclose the variable name
in single quotes and use that as the index to the elements array, for
example:

    variable = document.forms[0].elements['var[]'];
          

<!-- -->

**How can I pass a variable from Javascript to PHP?**  
Since Javascript is (usually) a client-side technology, and PHP is
(usually) a server-side technology, and since HTTP is a "stateless"
protocol, the two languages cannot directly share variables.

It is, however, possible to pass variables between the two. One way of
accomplishing this is to generate Javascript code with PHP, and have the
browser refresh itself, passing specific variables back to the PHP
script. The example below shows precisely how to do this -- it allows
PHP code to capture screen height and width, something that is normally
only possible on the client side.

**Example \#4 Generating Javascript with PHP**

``` php
<?php
if (isset($_GET['width']) AND isset($_GET['height'])) {
  // output the geometry variables
  echo "Screen width is: ". $_GET['width'] ."<br />\n";
  echo "Screen height is: ". $_GET['height'] ."<br />\n";
} else {
  // pass the geometry variables
  // (preserve the original query string
  //   -- post variables will need to handled differently)

  echo "<script language='javascript'>\n";
  echo "  location.href=\"${_SERVER['SCRIPT_NAME']}?${_SERVER['QUERY_STRING']}"
            . "&width=\" + screen.width + \"&height=\" + screen.height;\n";
  echo "</script>\n";
  exit();
}
?>
```

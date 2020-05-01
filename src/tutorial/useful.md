Let us do something more useful now. We are going to check what sort of
browser the visitor is using. For that, we check the user agent string
the browser sends as part of the HTTP request. This information is
stored in a
<a href="/language/variables.html" class="link">variable</a>. Variables
always start with a dollar-sign in PHP. The variable we are interested
in right now is `$_SERVER['HTTP_USER_AGENT']`.

> **Note**:
>
> `$_SERVER` is a special reserved PHP variable that contains all web
> server information. It is known as a superglobal. See the related
> manual page on
> <a href="/language/variables/superglobals.html" class="link">superglobals</a>
> for more information. These special variables were introduced in PHP
> <a href="https://www.php.net/releases/4_1_0.php" class="link external">» 4.1.0</a>.
> Before this time, we used the older `$HTTP_*_VARS` arrays instead,
> such as `$HTTP_SERVER_VARS`. As of PHP 5.4.0 these older variables
> have been removed. (See also the note on
> <a href="/tutorial/oldcode.html" class="link">old code</a>.)

To display this variable, you can simply do:

**Example \#1 Printing a variable (Array element)**

``` php
<?php
echo $_SERVER['HTTP_USER_AGENT'];
?>
```

A sample output of this script may be:

  
Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)  

There are many <a href="/language/types.html" class="link">types</a> of
variables available in PHP. In the above example we printed an
<a href="/language/types/array.html" class="link">Array</a> element.
Arrays can be very useful.

`$_SERVER` is just one variable that PHP automatically makes available
to you. A list can be seen in the
<a href="/reserved/variables.html" class="link">Reserved Variables</a>
section of the manual or you can get a complete list of them by looking
at the output of the <span class="function">phpinfo</span> function used
in the example in the previous section.

You can put multiple PHP statements inside a PHP tag and create little
blocks of code that do more than just a single echo. For example, if you
want to check for Internet Explorer you can do this:

**Example \#2 Example using
<a href="/language/control-structures.html" class="link">control structures</a>
and <a href="/language/functions.html" class="link">functions</a>**

``` php
<?php
if (strpos($_SERVER['HTTP_USER_AGENT'], 'MSIE') !== FALSE) {
    echo 'You are using Internet Explorer.<br />';
}
?>
```

A sample output of this script may be:

    You are using Internet Explorer.<br />

Here we introduce a couple of new concepts. We have an
<a href="/control-structures/if.html" class="link">if</a> statement. If
you are familiar with the basic syntax used by the C language, this
should look logical to you. Otherwise, you should probably pick up an
introductory PHP book and read the first couple of chapters, or read the
<a href="/langref.html" class="link">Language Reference</a> part of the
manual.

The second concept we introduced was the <span
class="function">strpos</span> function call. <span
class="function">strpos</span> is a function built into PHP which
searches a string for another string. In this case we are looking for
*'MSIE'* (so-called needle) inside `$_SERVER['HTTP_USER_AGENT']`
(so-called haystack). If the needle is found inside the haystack, the
function returns the position of the needle relative to the start of the
haystack. Otherwise, it returns **`FALSE`**. If it does not return
**`FALSE`**, the
<a href="/control-structures/if.html" class="link">if</a> expression
evaluates to **`TRUE`** and the code within its {braces} is executed.
Otherwise, the code is not run. Feel free to create similar examples,
with <a href="/control-structures/if.html" class="link">if</a>,
<a href="/control-structures/else.html" class="link">else</a>, and other
functions such as <span class="function">strtoupper</span> and <span
class="function">strlen</span>. Each related manual page contains
examples too. If you are unsure how to use functions, you will want to
read both the manual page on
<a href="/about/prototypes.html" class="link">how to read a function definition</a>
and the section about
<a href="/language/functions.html" class="link">PHP functions</a>.

We can take this a step further and show how you can jump in and out of
PHP mode even in the middle of a PHP block:

**Example \#3 Mixing both HTML and PHP modes**

``` php
<?php
if (strpos($_SERVER['HTTP_USER_AGENT'], 'MSIE') !== FALSE) {
?>
<h3>strpos() must have returned non-false</h3>
<p>You are using Internet Explorer</p>
<?php
} else {
?>
<h3>strpos() must have returned false</h3>
<p>You are not using Internet Explorer</p>
<?php
}
?>
```

A sample output of this script may be:

    <h3>strpos() must have returned non-false</h3>
    <p>You are using Internet Explorer</p>

Instead of using a PHP echo statement to output something, we jumped out
of PHP mode and just sent straight HTML. The important and powerful
point to note here is that the logical flow of the script remains
intact. Only one of the HTML blocks will end up getting sent to the
viewer depending on the result of <span class="function">strpos</span>.
In other words, it depends on whether the string *MSIE* was found or
not.

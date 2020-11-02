One of the most powerful features of PHP is the way it handles HTML
forms. The basic concept that is important to understand is that any
form element will automatically be available to your PHP scripts. Please
read the manual section on
<a href="/language/variables/external.html" class="link">Variables from external sources</a>
for more information and examples on using forms with PHP. Here is an
example HTML form:

**Example \#1 A simple HTML form**

``` html
<form action="action.php" method="post">
 <p>Your name: <input type="text" name="name" /></p>
 <p>Your age: <input type="text" name="age" /></p>
 <p><input type="submit" /></p>
</form>
```

There is nothing special about this form. It is a straight HTML form
with no special tags of any kind. When the user fills in this form and
hits the submit button, the `action.php` page is called. In this file
you would write something like this:

**Example \#2 Printing data from our form**

``` php
Hi <?php echo htmlspecialchars($_POST['name']); ?>.
You are <?php echo (int)$_POST['age']; ?> years old.
```

A sample output of this script may be:

    Hi Joe. You are 22 years old.

Apart from the <span class="function">htmlspecialchars</span> and
*(int)* parts, it should be obvious what this does. <span
class="function">htmlspecialchars</span> makes sure any characters that
are special in html are properly encoded so people can't inject HTML
tags or Javascript into your page. For the age field, since we know it
is a number, we can just
<a href="/language/types/type-juggling.html#language.types.typecasting" class="link">convert</a>
it to an <span class="type">int</span> which will automatically get rid
of any stray characters. You can also have PHP do this for you
automatically by using the
<a href="/ref/filter.html" class="link">filter</a> extension. The
`$_POST['name']` and `$_POST['age']` variables are automatically set for
you by PHP. Earlier we used the `$_SERVER` superglobal; above we just
introduced the `$_POST` superglobal which contains all POST data. Notice
how the *method* of our form is POST. If we used the method *GET* then
our form information would live in the `$_GET` superglobal instead. You
may also use the `$_REQUEST` superglobal, if you do not care about the
source of your request data. It contains the merged information of GET,
POST and COOKIE data.

You can also deal with XForms input in PHP, although you will find
yourself comfortable with the well supported HTML forms for quite some
time. While working with XForms is not for beginners, you might be
interested in them. We also have a
<a href="/features/xforms.html" class="link">short introduction to handling data received from XForms</a>
in our features section.

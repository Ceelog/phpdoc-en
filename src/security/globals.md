Using Register Globals
======================

**Warning**

This feature has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

Perhaps the most controversial change in PHP is when the default value
for the PHP directive
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
went from ON to OFF in PHP
<a href="https://www.php.net/releases/4_2_0.php" class="link external">» 4.2.0</a>.
Reliance on this directive was quite common and many people didn't even
know it existed and assumed it's just how PHP works. This page will
explain how one can write insecure code with this directive but keep in
mind that the directive itself isn't insecure but rather it's the misuse
of it.

When on, register\_globals will inject your scripts with all sorts of
variables, like request variables from HTML forms. This coupled with the
fact that PHP doesn't require variable initialization means writing
insecure code is that much easier. It was a difficult decision, but the
PHP community decided to disable this directive by default. When on,
people use variables yet really don't know for sure where they come from
and can only assume. Internal variables that are defined in the script
itself get mixed up with request data sent by users and disabling
register\_globals changes this. Let's demonstrate with an example misuse
of register\_globals:

**Example \#1 Example misuse with register\_globals = on**

``` php
<?php
// define $authorized = true only if user is authenticated
if (authenticated_user()) {
    $authorized = true;
}

// Because we didn't first initialize $authorized as false, this might be
// defined through register_globals, like from GET auth.php?authorized=1
// So, anyone can be seen as authenticated!
if ($authorized) {
    include "/highly/sensitive/data.php";
}
?>
```

When register\_globals = on, our logic above may be compromised. When
off, `$authorized` can't be set via request so it'll be fine, although
it really is generally a good programming practice to initialize
variables first. For example, in our example above we might have first
done *$authorized = false*. Doing this first means our above code would
work with register\_globals on or off as users by default would be
unauthorized.

Another example is that of
<a href="/ref/session.html" class="link">sessions</a>. When
register\_globals = on, we could also use `$username` in our example
below but again you must realize that `$username` could also come from
other means, such as GET (through the URL).

**Example \#2 Example use of sessions with register\_globals on or off**

``` php
<?php
// We wouldn't know where $username came from but do know $_SESSION is
// for session data
if (isset($_SESSION['username'])) {

    echo "Hello <b>{$_SESSION['username']}</b>";

} else {

    echo "Hello <b>Guest</b><br />";
    echo "Would you like to login?";

}
?>
```

It's even possible to take preventative measures to warn when forging is
being attempted. If you know ahead of time exactly where a variable
should be coming from, you can check to see if the submitted data is
coming from an inappropriate kind of submission. While it doesn't
guarantee that data has not been forged, it does require an attacker to
guess the right kind of forging. If you don't care where the request
data comes from, you can use `$_REQUEST` as it contains a mix of GET,
POST and COOKIE data. See also the manual section on using
<a href="/language/variables/external.html" class="link">variables from external sources</a>.

**Example \#3 Detecting simple variable poisoning**

``` php
<?php
if (isset($_COOKIE['MAGIC_COOKIE'])) {

    // MAGIC_COOKIE comes from a cookie.
    // Be sure to validate the cookie data!

} elseif (isset($_GET['MAGIC_COOKIE']) || isset($_POST['MAGIC_COOKIE'])) {

   mail("admin@example.com", "Possible breakin attempt", $_SERVER['REMOTE_ADDR']);
   echo "Security violation, admin has been alerted.";
   exit;

} else {

   // MAGIC_COOKIE isn't set through this REQUEST

}
?>
```

Of course, simply turning off register\_globals does not mean your code
is secure. For every piece of data that is submitted, it should also be
checked in other ways. Always validate your user data and initialize
your variables! To check for uninitialized variables you may turn up
<span class="function">error\_reporting</span> to show **`E_NOTICE`**
level errors.

For information about emulating register\_globals being On or Off, see
this
<a href="/faq/misc.html#faq.misc.registerglobals" class="link">FAQ</a>.

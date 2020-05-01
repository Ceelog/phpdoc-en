Examples
========

**Table of Contents**

-   [Basic usage](/session/examples.html#Basic%20usage)
-   [Passing the Session
    ID](/session/examples.html#Passing%20the%20Session%20ID)
-   [Custom Session
    Handlers](/session/examples.html#Custom%20Session%20Handlers)

Basic usage
-----------

Sessions are a simple way to store data for individual users against a
unique session ID. This can be used to persist state information between
page requests. Session IDs are normally sent to the browser via session
cookies and the ID is used to retrieve existing session data. The
absence of an ID or session cookie lets PHP know to create a new
session, and generate a new session ID.

Sessions follow a simple workflow. When a session is started, PHP will
either retrieve an existing session using the ID passed (usually from a
session cookie) or if no session is passed it will create a new session.
PHP will populate the `$_SESSION` superglobal with any session data
after the session has started. When PHP shuts down, it will
automatically take the contents of the `$_SESSION` superglobal,
serialize it, and send it for storage using the session save handler.

By default, PHP uses the internal `files` save handler which is set by
<a href="/session/setup.html#" class="link">session.save_handler</a>.
This saves session data on the server at the location specified by the
<a href="/session/setup.html#" class="link">session.save_path</a>
configuration directive.

Sessions can be started manually using the <span
class="function">session\_start</span> function. If the
<a href="/session/setup.html#" class="link">session.auto_start</a>
directive is set to `1`, a session will automatically start on request
startup.

Sessions normally shutdown automatically when PHP is finished executing
a script, but can be manually shutdown using the <span
class="function">session\_write\_close</span> function.

**Example \#1 Registering a variable with `$_SESSION`.**

``` php
<?php
session_start();
if (!isset($_SESSION['count'])) {
  $_SESSION['count'] = 0;
} else {
  $_SESSION['count']++;
}
?>
```

**Example \#2 Unregistering a variable with `$_SESSION`.**

``` php
<?php
session_start();
unset($_SESSION['count']);
?>
```

**Caution**

Do NOT unset the whole `$_SESSION` with *unset($\_SESSION)* as this will
disable the registering of session variables through the `$_SESSION`
superglobal.

**Warning**

You can't use references in session variables as there is no feasible
way to restore a reference to another variable.

**Warning**

register\_globals will overwrite variables in the global scope whose
names are shared with session variables. Please see
<a href="/security/globals.html" class="link">Using Register Globals</a>
for details.

> **Note**:
>
> File based sessions (the default in PHP) lock the session file once a
> session is opened via <span class="function">session\_start</span> or
> implicitly via
> <a href="/session/setup.html#" class="link">session.auto_start</a>.
> Once locked, no other script can access the same session file until it
> has been closed by the first script terminating or calling <span
> class="function">session\_write\_close</span>.
>
> This is most likely to be an issue on Web sites that use AJAX heavily
> and have multiple concurrent requests. The easiest way to deal with it
> is to call <span class="function">session\_write\_close</span> as soon
> as any required changes to the session have been made, preferably
> early in the script. Alternatively, a different session backend that
> does support concurrency could be used.

Passing the Session ID
----------------------

There are two methods to propagate a session id:

-   <span class="simpara"> Cookies </span>
-   <span class="simpara"> URL parameter </span>

The session module supports both methods. Cookies are optimal, but
because they are not always available, we also provide an alternative
way. The second method embeds the session id directly into URLs.

PHP is capable of transforming links transparently. If the run-time
option *session.use\_trans\_sid* is enabled, relative URIs will be
changed to contain the session id automatically.

> **Note**:
>
> The
> <a href="/ini/core.html#ini.arg-separator.output" class="link">arg_separator.output</a>
> `php.ini` directive allows to customize the argument separator. For
> full XHTML conformance, specify &amp; there.

Alternatively, you can use the constant **`SID`** which is defined if
the session started. If the client did not send an appropriate session
cookie, it has the form *session\_name=session\_id*. Otherwise, it
expands to an empty string. Thus, you can embed it unconditionally into
URLs.

The following example demonstrates how to register a variable, and how
to link correctly to another page using **`SID`**.

**Example \#1 Counting the number of hits of a single user**

``` php
<?php

session_start();

if (empty($_SESSION['count'])) {
   $_SESSION['count'] = 1;
} else {
   $_SESSION['count']++;
}
?>

<p>
Hello visitor, you have seen this page <?php echo $_SESSION['count']; ?> times.
</p>

<p>
To continue, <a href="nextpage.php?<?php echo htmlspecialchars(SID); ?>">click
here</a>.
</p>
```

The <span class="function">htmlspecialchars</span> may be used when
printing the **`SID`** in order to prevent XSS related attacks.

Printing the **`SID`**, like shown above, is not necessary if
<a href="/session/setup.html#" class="link">--enable-trans-sid</a> was
used to compile PHP.

> **Note**:
>
> Non-relative URLs are assumed to point to external sites and hence
> don't append the **`SID`**, as it would be a security risk to leak the
> **`SID`** to a different server.

Custom Session Handlers
-----------------------

To implement database storage, or any other storage method, you will
need to use <span class="function">session\_set\_save\_handler</span> to
create a set of user-level storage functions. As of PHP 5.4.0 you may
create session handlers using the <span
class="classname">SessionHandlerInterface</span> or extend internal PHP
handlers by inheriting from <span
class="classname">SessionHandler</span>.

The callbacks specified in <span
class="function">session\_set\_save\_handler</span> are methods called
by PHP during the life-cycle of a session: `open`, `read`, `write` and
`close` and for the housekeeping tasks: `destroy` for deleting a session
and `gc` for periodic garbage collection.

Therefore, PHP always requires session save handlers. The default is
usually the internal 'files' save handler. A custom save handler can be
set using <span class="function">session\_set\_save\_handler</span>.
Alternative internal save handlers are also provided by PHP extensions,
such as `sqlite`, `memcache` and `memcached` and can be set with
<a href="/session/setup.html#" class="link">session.save_handler</a>.

When the session starts, PHP will internally call the `open` handler
followed by the `read` callback which should return an encoded string
exactly as it was originally passed for storage. Once the `read`
callback returns the encoded string, PHP will decode it and then
populate the resulting array into the `$_SESSION` superglobal.

When PHP shuts down (or when <span
class="function">session\_write\_close</span> is called), PHP will
internally encode the `$_SESSION` superglobal and pass this along with
the session ID to the `write` callback. After the `write` callback has
finished, PHP will internally invoke the `close` callback handler.

When a session is specifically destroyed, PHP will call the `destroy`
handler with the session ID.

PHP will call the `gc` callback from time to time to expire any session
records according to the set max lifetime of a session. This routine
should delete all records from persistent storage which were last
accessed longer than the `$lifetime`.

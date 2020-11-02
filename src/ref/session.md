session\_abort
==============

Discard session array changes and finish session

### Description

<span class="type">bool</span> <span
class="methodname">session\_abort</span> ( <span
class="methodparam">void</span> )

<span class="function">session\_abort</span> finishes session without
saving data. Thus the original values in session data are kept.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                   |
|---------|-------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The return type of this function is <span class="type">bool</span> now. Formerly, it has been <span class="type">void</span>. |

### See Also

-   `$_SESSION`
-   The
    <a href="/session/setup.html#" class="link">session.auto_start</a>
    configuration directive
-   <span class="function">session\_start</span>
-   <span class="function">session\_reset</span>
-   <span class="function">session\_commit</span>

session\_cache\_expire
======================

Get and/or set current cache expire

### Description

<span class="type">int</span> <span
class="methodname">session\_cache\_expire</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$new_cache_expire`</span> \] )

<span class="function">session\_cache\_expire</span> returns the current
setting of *session.cache\_expire*.

The cache expire is reset to the default value of 180 stored in
<a href="/session/setup.html#" class="link">session.cache_expire</a> at
request startup time. Thus, you need to call <span
class="function">session\_cache\_expire</span> for every request (and
before <span class="function">session\_start</span> is called).

### Parameters

`new_cache_expire`  
If `new_cache_expire` is given, the current cache expire is replaced
with `new_cache_expire`.

> **Note**: <span class="simpara"> Setting `new_cache_expire` is of
> value only, if *session.cache\_limiter* is set to a value *different*
> from *nocache*. </span>

### Return Values

Returns the current setting of *session.cache\_expire*. The value
returned should be read in minutes, defaults to 180.

### Examples

**Example \#1 <span class="function">session\_cache\_expire</span>
example**

``` php
<?php

/* set the cache limiter to 'private' */

session_cache_limiter('private');
$cache_limiter = session_cache_limiter();

/* set the cache expire to 30 minutes */
session_cache_expire(30);
$cache_expire = session_cache_expire();

/* start the session */

session_start();

echo "The cache limiter is now set to $cache_limiter<br />";
echo "The cached session pages expire after $cache_expire minutes";
?>
```

### See Also

-   <a href="/session/setup.html#" class="link">session.cache_expire</a>
-   <a href="/session/setup.html#" class="link">session.cache_limiter</a>
-   <span class="function">session\_cache\_limiter</span>

session\_cache\_limiter
=======================

Get and/or set the current cache limiter

### Description

<span class="type">string</span> <span
class="methodname">session\_cache\_limiter</span> (\[ <span
class="methodparam"><span class="type">string</span>
`$cache_limiter`</span> \] )

<span class="function">session\_cache\_limiter</span> returns the name
of the current cache limiter.

The cache limiter defines which cache control HTTP headers are sent to
the client. These headers determine the rules by which the page content
may be cached by the client and intermediate proxies. Setting the cache
limiter to *nocache* disallows any client/proxy caching. A value of
*public* permits caching by proxies and the client, whereas *private*
disallows caching by proxies and permits the client to cache the
contents.

In *private* mode, the Expire header sent to the client may cause
confusion for some browsers, including <span
class="productname">Mozilla</span>. You can avoid this problem by using
*private\_no\_expire* mode. The *Expire* header is never sent to the
client in this mode.

Setting the cache limiter to *''* will turn off automatic sending of
cache headers entirely.

The cache limiter is reset to the default value stored in
<a href="/session/setup.html#" class="link">session.cache_limiter</a> at
request startup time. Thus, you need to call <span
class="function">session\_cache\_limiter</span> for every request (and
before <span class="function">session\_start</span> is called).

### Parameters

`cache_limiter`  
If `cache_limiter` is specified, the name of the current cache limiter
is changed to the new value.

<table>
<caption><strong>Possible values</strong></caption>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Value</th>
<th>Headers sent</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><em>public</em></td>
<td><div class="example-contents">
<div class="headercode">
<pre class="header"><code>Expires: (sometime in the future, according session.cache_expire)
Cache-Control: public, max-age=(sometime in the future, according to session.cache_expire)
Last-Modified: (the timestamp of when the session was last saved)</code></pre>
</div>
</div></td>
</tr>
<tr class="even">
<td><em>private_no_expire</em></td>
<td><div class="example-contents">
<div class="headercode">
<pre class="header"><code>Cache-Control: private, max-age=(session.cache_expire in the future), pre-check=(session.cache_expire in the future)
Last-Modified: (the timestamp of when the session was last saved)</code></pre>
</div>
</div></td>
</tr>
<tr class="odd">
<td><em>private</em></td>
<td><div class="example-contents">
<div class="headercode">
<pre class="header"><code>Expires: Thu, 19 Nov 1981 08:52:00 GMT
Cache-Control: private, max-age=(session.cache_expire in the future), pre-check=(session.cache_expire in the future)
Last-Modified: (the timestamp of when the session was last saved)</code></pre>
</div>
</div></td>
</tr>
<tr class="even">
<td><em>nocache</em></td>
<td><div class="example-contents">
<div class="headercode">
<pre class="header"><code>Expires: Thu, 19 Nov 1981 08:52:00 GMT
Cache-Control: no-store, no-cache, must-revalidate, post-check=0, pre-check=0
Pragma: no-cache</code></pre>
</div>
</div></td>
</tr>
</tbody>
</table>

### Return Values

Returns the name of the current cache limiter.

### Examples

**Example \#1 <span class="function">session\_cache\_limiter</span>
example**

``` php
<?php

/* set the cache limiter to 'private' */

session_cache_limiter('private');
$cache_limiter = session_cache_limiter();

echo "The cache limiter is now set to $cache_limiter<br />";
?>
```

### See Also

-   <a href="/session/setup.html#" class="link">session.cache_limiter</a>

session\_commit
===============

Alias of <span class="function">session\_write\_close</span>

### Description

This function is an alias of: <span
class="function">session\_write\_close</span>.

session\_create\_id
===================

Create new session id

### Description

<span class="type">string</span> <span
class="methodname">session\_create\_id</span> (\[ <span
class="methodparam"><span class="type">string</span> `$prefix`</span> \]
)

<span class="function">session\_create\_id</span> is used to create new
session id for the current session. It returns collision free session
id.

If session is not active, collision check is omitted.

Session ID is created according to php.ini settings.

It is important to use the same user ID of your web server for GC task
script. Otherwise, you may have permission problems especially with
files save handler.

### Parameters

`prefix`  
If `prefix` is specified, new session id is prefixed by `prefix`. Not
all characters are allowed within the session id. Characters in the
range *a-z A-Z 0-9 , (comma) and - (minus)* are allowed.

### Return Values

<span class="function">session\_create\_id</span> returns new collision
free session id for the current session. If it is used without active
session, it omits collision check.

### Examples

**Example \#1 <span class="function">session\_create\_id</span> example
with <span class="function">session\_regenerate\_id</span>**

``` php
<?php
// My session start function support timestamp management
function my_session_start() {
    session_start();
    // Do not allow to use too old session ID
    if (!empty($_SESSION['deleted_time']) && $_SESSION['deleted_time'] < time() - 180) {
        session_destroy();
        session_start();
    }
}

// My session regenerate id function
function my_session_regenerate_id() {
    // Call session_create_id() while session is active to 
    // make sure collision free.
    if (session_status() != PHP_SESSION_ACTIVE) {
        session_start();
    }
    // WARNING: Never use confidential strings for prefix!
    $newid = session_create_id('myprefix-');
    // Set deleted timestamp. Session data must not be deleted immediately for reasons.
    $_SESSION['deleted_time'] = time();
    // Finish session
    session_commit();
    // Make sure to accept user defined session ID
    // NOTE: You must enable use_strict_mode for normal operations.
    ini_set('session.use_strict_mode', 0);
    // Set new custom session ID
    session_id($newid);
    // Start with custom session ID
    session_start();
}

// Make sure use_strict_mode is enabled.
// use_strict_mode is mandatory for security reasons.
ini_set('session.use_strict_mode', 1);
my_session_start();

// Session ID must be regenerated when
//  - User logged in
//  - User logged out
//  - Certain period has passed
my_session_regenerate_id();

// Write useful codes
?>
```

### See Also

-   <span class="function">session\_regenerate\_id</span>
-   <span class="function">session\_start</span>
-   <a href="/session/setup.html#" class="link">session.use_strict_mode</a>
-   <span class="methodname">SessionHandler::create\_sid</span>

session\_decode
===============

Decodes session data from a session encoded string

### Description

<span class="type">bool</span> <span
class="methodname">session\_decode</span> ( <span
class="methodparam"><span class="type">string</span> `$data`</span> )

<span class="function">session\_decode</span> decodes the serialized
session data provided in `$data`, and populates the $\_SESSION
superglobal with the result.

By default, the unserialization method used is internal to PHP, and is
not the same as <span class="function">unserialize</span>. The
serialization method can be set using
<a href="/session/setup.html#" class="link">session.serialize_handler</a>.

### Parameters

`data`  
The encoded data to be stored.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">session\_encode</span>
-   <a href="/session/setup.html#" class="link">session.serialize_handler</a>

session\_destroy
================

Destroys all data registered to a session

### Description

<span class="type">bool</span> <span
class="methodname">session\_destroy</span> ( <span
class="methodparam">void</span> )

<span class="function">session\_destroy</span> destroys all of the data
associated with the current session. It does not unset any of the global
variables associated with the session, or unset the session cookie. To
use the session variables again, <span
class="function">session\_start</span> has to be called.

> **Note**: <span class="simpara"> You do not have to call <span
> class="function">session\_destroy</span> from usual code. Cleanup
> $\_SESSION array rather than destroying session data. </span>

In order to kill the session altogether, the session ID must also be
unset. If a cookie is used to propagate the session ID (default
behavior), then the session cookie must be deleted. <span
class="function">setcookie</span> may be used for that.

When
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
is enabled. You do not have to remove obsolete session ID cookie because
session module will not accept session ID cookie when there is no data
associated to the session ID and set new session ID cookie. Enabling
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
is recommended for all sites.

**Warning**

Immediate session deletion may cause unwanted results. When there is
concurrent requests, other connections may see sudden session data loss.
e.g. Requests from JavaScript and/or requests from URL links.

Although current session module does not accept empty session ID cookie,
but immediate session deletion may result in empty session ID cookie due
to client(browser) side race condition. This will result that the client
creates many session ID needlessly.

To avoid these, you must set deletion time-stamp to $\_SESSION and
reject access while later. Or make sure your application does not have
concurrent requests. This applies to <span
class="function">session\_regenerate\_id</span> also.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Destroying a session with `$_SESSION`**

``` php
<?php
// Initialize the session.
// If you are using session_name("something"), don't forget it now!
session_start();

// Unset all of the session variables.
$_SESSION = array();

// If it's desired to kill the session, also delete the session cookie.
// Note: This will destroy the session, and not just the session data!
if (ini_get("session.use_cookies")) {
    $params = session_get_cookie_params();
    setcookie(session_name(), '', time() - 42000,
        $params["path"], $params["domain"],
        $params["secure"], $params["httponly"]
    );
}

// Finally, destroy the session.
session_destroy();
?>
```

### Notes

> **Note**:
>
> Only use <span class="function">session\_unset</span> for older
> deprecated code that does not use `$_SESSION`.

### See Also

-   <a href="/session/setup.html#" class="link">session.use_strict_mode</a>
-   <span class="function">session\_reset</span>
-   <span class="function">session\_regenerate\_id</span>
-   <span class="function">unset</span>
-   <span class="function">setcookie</span>

session\_encode
===============

Encodes the current session data as a session encoded string

### Description

<span class="type">string</span> <span
class="methodname">session\_encode</span> ( <span
class="methodparam">void</span> )

<span class="function">session\_encode</span> returns a serialized
string of the contents of the current session data stored in the
$\_SESSION superglobal.

By default, the serialization method used is internal to PHP, and is not
the same as <span class="function">serialize</span>. The serialization
method can be set using
<a href="/session/setup.html#" class="link">session.serialize_handler</a>.

### Return Values

Returns the contents of the current session encoded.

### Notes

**Warning**

Must call <span class="function">session\_start</span> before using
<span class="function">session\_encode</span>.

### See Also

-   <span class="function">session\_decode</span>
-   <a href="/session/setup.html#" class="link">session.serialize_handler</a>

session\_gc
===========

Perform session data garbage collection

### Description

<span class="type">int</span> <span
class="methodname">session\_gc</span> ( <span
class="methodparam">void</span> )

<span class="function">session\_gc</span> is used to perform session
data GC(garbage collection). PHP does probability based session GC by
default.

Probability based GC works somewhat but it has few problems. 1) Low
traffic sites' session data may not be deleted within the preferred
duration. 2) High traffic sites' GC may be too frequent GC. 3) GC is
performed on the user's request and the user will experience a GC delay.

Therefore, it is recommended to execute GC periodically for production
systems using, e.g., "cron" for UNIX-like systems. Make sure to disable
probability based GC by setting
<a href="/session/setup.html#" class="link">session.gc_probability</a>
to 0.

### Return Values

<span class="function">session\_gc</span> returns number of deleted
session data for success, **`FALSE`** for failure.

Old save handlers do not return number of deleted session data, but only
success/failure flag. If this is the case, number of deleted session
data became 1 regardless of actually deleted data.

### Examples

**Example \#1 <span class="function">session\_gc</span> example for task
managers like cron**

``` php
<?php
// Note: This script should be executed by the same user of web server process.

// Need active session to initialize session data storage access.
session_start();

// Executes GC immediately
session_gc();

// Clean up session ID created by session_gc()
session_destroy();
?>
```

**Example \#2 <span class="function">session\_gc</span> example for user
accessible script**

``` php
<?php
// Note: session_gc() is recommended to be used by task manager script, but
// it may be used as follows.

// Used for last GC time check
$gc_time = '/tmp/php_session_last_gc';
$gc_period = 1800;

session_start();
// Execute GC only when GC period elapsed. 
// i.e. Calling session_gc() every request is waste of resources. 
if (file_exists($gc_time)) {
    if (filemtime($gc_time) < time() - $gc_period) {
        session_gc();
        touch($gc_time);
    }
} else {
    touch($gc_time);
}
?>
```

### See Also

-   <span class="function">session\_start</span>
-   <span class="function">session\_destroy</span>
-   <a href="/session/setup.html#" class="link">session.gc_probability</a>

session\_get\_cookie\_params
============================

Get the session cookie parameters

### Description

<span class="type">array</span> <span
class="methodname">session\_get\_cookie\_params</span> ( <span
class="methodparam">void</span> )

Gets the session cookie parameters.

### Return Values

Returns an array with the current session cookie information, the array
contains the following items:

-   <span class="simpara">
    <a href="/session/setup.html#" class="link">"lifetime"</a> - The
    lifetime of the cookie in seconds. </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">"path"</a> - The path
    where information is stored. </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">"domain"</a> - The
    domain of the cookie. </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">"secure"</a> - The
    cookie should only be sent over secure connections. </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">"httponly"</a> - The
    cookie can only be accessed through the HTTP protocol. </span>
-   <span class="simpara">
    <a href="/session/setup.html#" class="link">"samesite"</a> -
    Controls the cross-domain sending of the cookie. </span>

### Changelog

| Version | Description                                           |
|---------|-------------------------------------------------------|
| 7.3.0   | The "samesite" entry was added in the returned array. |

### See Also

-   <a href="/session/setup.html#" class="link">session.cookie_lifetime</a>
-   <a href="/session/setup.html#" class="link">session.cookie_path</a>
-   <a href="/session/setup.html#" class="link">session.cookie_domain</a>
-   <a href="/session/setup.html#" class="link">session.cookie_secure</a>
-   <a href="/session/setup.html#" class="link">session.cookie_httponly</a>
-   <a href="/session/setup.html#" class="link">session.cookie_samesite</a>
-   <span class="function">session\_set\_cookie\_params</span>

session\_id
===========

Get and/or set the current session id

### Description

<span class="type">string</span> <span
class="methodname">session\_id</span> (\[ <span
class="methodparam"><span class="type">string</span> `$id`</span> \] )

<span class="function">session\_id</span> is used to get or set the
session id for the current session.

The constant **`SID`** can also be used to retrieve the current name and
session id as a string suitable for adding to URLs. See also
<a href="/ref/session.html" class="link">Session handling</a>.

### Parameters

`id`  
If `id` is specified, it will replace the current session id. <span
class="function">session\_id</span> needs to be called before <span
class="function">session\_start</span> for that purpose. Depending on
the session handler, not all characters are allowed within the session
id. For example, the file session handler only allows characters in the
range *a-z A-Z 0-9 , (comma) and - (minus)*!

> **Note**: <span class="simpara"> When using session cookies,
> specifying an `id` for <span class="function">session\_id</span> will
> always send a new cookie when <span
> class="function">session\_start</span> is called, regardless if the
> current session id is identical to the one being set. </span>

### Return Values

<span class="function">session\_id</span> returns the session id for the
current session or the empty string (*""*) if there is no current
session (no current session id exists).

### See Also

-   <span class="function">session\_regenerate\_id</span>
-   <span class="function">session\_start</span>
-   <span class="function">session\_set\_save\_handler</span>
-   <a href="/session/setup.html#" class="link">session.save_handler</a>

session\_is\_registered
=======================

Find out whether a global variable is registered in a session

### Description

<span class="type">bool</span> <span
class="methodname">session\_is\_registered</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

Finds out whether a global variable is registered in a session.

**Warning**

This function has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

### Parameters

`name`  
The variable name.

### Return Values

<span class="function">session\_is\_registered</span> returns **`TRUE`**
if there is a global variable with the name `name` registered in the
current session, **`FALSE`** otherwise.

### Notes

> **Note**:
>
> If `$_SESSION` is used, use <span class="function">isset</span> to
> check a variable is registered in `$_SESSION`.

**Caution**

If you are using `$_SESSION` (or `$HTTP_SESSION_VARS`), do not use <span
class="function">session\_register</span>, <span
class="function">session\_is\_registered</span> and <span
class="function">session\_unregister</span>.

session\_module\_name
=====================

Get and/or set the current session module

### Description

<span class="type">string</span> <span
class="methodname">session\_module\_name</span> (\[ <span
class="methodparam"><span class="type">string</span> `$module`</span> \]
)

<span class="function">session\_module\_name</span> gets the name of the
current session module, which is also known as
<a href="/session/setup.html#" class="link">session.save_handler</a>.

### Parameters

`module`  
If `module` is specified, that module will be used instead. Passing
*"user"* to this parameter is forbidden. Instead <span
class="function">session\_set\_save\_handler</span> has to be called to
set a user defined session handler.

### Return Values

Returns the name of the current session module.

### Changelog

| Version | Description                                                                                                  |
|---------|--------------------------------------------------------------------------------------------------------------|
| 7.2.0   | It is now explicitly forbidden to set the module name to *"user"*. Formerly, this has been silently ignored. |

session\_name
=============

Get and/or set the current session name

### Description

<span class="type">string</span> <span
class="methodname">session\_name</span> (\[ <span
class="methodparam"><span class="type">string</span> `$name`</span> \] )

<span class="function">session\_name</span> returns the name of the
current session. If `name` is given, <span
class="function">session\_name</span> will update the session name and
return the *old* session name.

If a new session `name` is supplied, <span
class="function">session\_name</span> modifies the HTTP cookie (and
output content when *session.transid* is enabled). Once the HTTP cookie
is sent, <span class="function">session\_name</span> raises error. <span
class="function">session\_name</span> must be called before <span
class="function">session\_start</span> for the session to work properly.

The session name is reset to the default value stored in *session.name*
at request startup time. Thus, you need to call <span
class="function">session\_name</span> for every request (and before
<span class="function">session\_start</span> is called).

### Parameters

`name`  
The session name references the name of the session, which is used in
cookies and URLs (e.g. *PHPSESSID*). It should contain only alphanumeric
characters; it should be short and descriptive (i.e. for users with
enabled cookie warnings). If `name` is specified, the name of the
current session is changed to its value.

**Warning**
The session name can't consist of digits only, at least one letter must
be present. Otherwise a new session id is generated every time.

### Return Values

Returns the name of the current session. If `name` is given and function
updates the session name, name of the *old* session is returned.

### Examples

**Example \#1 <span class="function">session\_name</span> example**

``` php
<?php

/* set the session name to WebsiteID */

$previous_name = session_name("WebsiteID");

echo "The previous session name was $previous_name<br />";
?>
```

### Changelog

| Version | Description                                                                                                                                                                                                                                                                                                                                 |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | <span class="function">session\_name</span> checks session status, previously it only checked cookie status. Therefore, older <span class="function">session\_name</span> allows to call <span class="function">session\_name</span> after <span class="function">session\_start</span> which may crash PHP and may result in misbehaviors. |

### See Also

-   The <a href="/session/setup.html#" class="link">session.name</a>
    configuration directive

session\_regenerate\_id
=======================

Update the current session id with a newly generated one

### Description

<span class="type">bool</span> <span
class="methodname">session\_regenerate\_id</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$delete_old_session`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="function">session\_regenerate\_id</span> will replace the
current session id with a new one, and keep the current session
information.

When
<a href="/session/setup.html#" class="link">session.use_trans_sid</a> is
enabled, output must be started after <span
class="function">session\_regenerate\_id</span> call. Otherwise, old
session ID is used.

**Warning**

Currently, session\_regenerate\_id does not handle an unstable network
well, e.g. Mobile and WiFi network. Therefore, you may experience a lost
session by calling session\_regenerate\_id.

You should not destroy old session data immediately, but should use
destroy time-stamp and control access to old session ID. Otherwise,
concurrent access to page may result in inconsistent state, or you may
have lost session, or it may cause client(browser) side race condition
and may create many session ID needlessly. Immediate session data
deletion disables session hijack attack detection and prevention also.

### Parameters

`delete_old_session`  
Whether to delete the old associated session file or not. You should not
delete old session if you need to avoid races caused by deletion or
detect/avoid session hijack attacks.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">session\_regenerate\_id</span>
example**

``` php
<?php
// NOTE: This code is not fully working code, but an example!

session_start();

// Check destroyed time-stamp
if (isset($_SESSION['destroyed'])
    && $_SESSION['destroyed'] < time() - 300) {
    // Should not happen usually. This could be attack or due to unstable network.
    // Remove all authentication status of this users session.
    remove_all_authentication_flag_from_active_sessions($_SESSION['userid']);
    throw(new DestroyedSessionAccessException);
}

$old_sessionid = session_id();

// Set destroyed timestamp
$_SESSION['destroyed'] = time(); // Since PHP 7.0.0 and up, session_regenerate_id() saves old session data

// Simply calling session_regenerate_id() may result in lost session, etc.
// See next example.
session_regenerate_id();

// New session does not need destroyed timestamp
unset($_SESSION['destroyed']);

$new_sessionid = session_id();

echo "Old Session: $old_sessionid<br />";
echo "New Session: $new_sessionid<br />";

print_r($_SESSION);
?>
```

Current session module does not handle unstable network well. You should
manage session ID to avoid lost session by session\_regenerate\_id.

**Example \#2 Avoiding lost session by <span
class="function">session\_regenerate\_id</span>**

``` php
<?php
// NOTE: This code is not fully working code, but an example!
// my_session_start() and my_session_regenerate_id() avoid lost sessions by
// unstable network. In addition, this code may prevent exploiting stolen
// session by attackers.

function my_session_start() {
    session_start();
    if (isset($_SESSION['destroyed'])) {
       if ($_SESSION['destroyed'] < time()-300) {
           // Should not happen usually. This could be attack or due to unstable network.
           // Remove all authentication status of this users session.
           remove_all_authentication_flag_from_active_sessions($_SESSION['userid']);
           throw(new DestroyedSessionAccessException);
       }
       if (isset($_SESSION['new_session_id'])) {
           // Not fully expired yet. Could be lost cookie by unstable network.
           // Try again to set proper session ID cookie.
           // NOTE: Do not try to set session ID again if you would like to remove
           // authentication flag.
           session_commit();
           session_id($_SESSION['new_session_id']);
           // New session ID should exist
           session_start();
           return;
       }
   }
}

function my_session_regenerate_id() {
    // New session ID is required to set proper session ID
    // when session ID is not set due to unstable network.
    $new_session_id = session_create_id();
    $_SESSION['new_session_id'] = $new_session_id;
    
    // Set destroy timestamp
    $_SESSION['destroyed'] = time();
    
    // Write and close current session;
    session_commit();

    // Start session with new session ID
    session_id($new_session_id);
    ini_set('session.use_strict_mode', 0);
    session_start();
    ini_set('session.use_strict_mode', 1);
    
    // New session does not need them
    unset($_SESSION['destroyed']);
    unset($_SESSION['new_session_id']);
}
?>
```

### See Also

-   <span class="function">session\_id</span>
-   <span class="function">session\_create\_id</span>
-   <span class="function">session\_start</span>
-   <span class="function">session\_destroy</span>
-   <span class="function">session\_reset</span>
-   <span class="function">session\_name</span>

session\_register\_shutdown
===========================

Session shutdown function

### Description

<span class="type">void</span> <span
class="methodname">session\_register\_shutdown</span> ( <span
class="methodparam">void</span> )

Registers <span class="function">session\_write\_close</span> as a
shutdown function.

### Parameters

This function has no parameters.

### Return Values

No value is returned.

### Errors/Exceptions

Emits **`E_WARNING`** if registering the shutdown function fails.

session\_register
=================

Register one or more global variables with the current session

### Description

<span class="type">bool</span> <span
class="methodname">session\_register</span> ( <span
class="methodparam"><span class="type">mixed</span> `$name`</span> ,
<span class="methodparam"><span class="type">mixed</span>
`$names`</span> )

<span class="function">session\_register</span> accepts a variable
number of arguments, any of which can be either a string holding the
name of a variable or an array consisting of variable names or other
arrays. For each name, <span class="function">session\_register</span>
registers the global variable with that name in the current session.

You can also create a session variable by simply setting the appropriate
member of the `$_SESSION` array.

``` php
<?php
// Use of session_register() is deprecated
$barney = "A big purple dinosaur.";
session_register("barney");

// Use of $_SESSION is preferred
$_SESSION["zim"] = "An invader from another planet.";
?>
```

If <span class="function">session\_start</span> was not called before
this function is called, an implicit call to <span
class="function">session\_start</span> with no parameters will be made.
`$_SESSION` does not mimic this behavior and requires <span
class="function">session\_start</span> before use.

**Warning**

This function has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

### Parameters

`name`  
A string holding the name of a variable or an array consisting of
variable names or other arrays.

`names`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

**Caution**

If you want your script to work regardless of
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>,
you need to instead use the `$_SESSION` array as `$_SESSION` entries are
automatically registered. If your script uses <span
class="function">session\_register</span>, it will not work in
environments where the PHP directive
<a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
is disabled.

> **Note**: **register\_globals: important note**  
>
> As of PHP 4.2.0, the default value for the PHP directive
> <a href="/ini/core.html#ini.register-globals" class="link">register_globals</a>
> is *off*. The PHP community discourages developers from relying on
> this directive, and encourages the use of other means, such as the
> <a href="/language/variables/predefined.html" class="link">superglobals</a>.

**Caution**

This registers a *global* variable. If you want to register a session
variable from within a function, you need to make sure to make it global
using the
<a href="/language/variables/scope.html" class="link"><strong>global</strong></a>
keyword or the `$GLOBALS[]` array, or use the special session arrays as
noted below.

**Caution**

If you are using `$_SESSION`, do not use <span
class="function">session\_register</span>, <span
class="function">session\_is\_registered</span>, and <span
class="function">session\_unregister</span>.

> **Note**:
>
> It is currently impossible to register resource variables in a
> session. For example, you cannot create a connection to a database and
> store the connection id as a session variable and expect the
> connection to still be valid the next time the session is restored.
> PHP functions that return a resource are identified by having a return
> type of *resource* in their function definition. A list of functions
> that return resources are available in the
> <a href="/resource.html" class="link">resource types</a> appendix.
>
> If `$_SESSION` is used, assign values to `$_SESSION`. For example:
> $\_SESSION\['var'\] = 'ABC';

### See Also

-   <span class="function">session\_is\_registered</span>
-   <span class="function">session\_unregister</span>
-   `$_SESSION`

session\_reset
==============

Re-initialize session array with original values

### Description

<span class="type">bool</span> <span
class="methodname">session\_reset</span> ( <span
class="methodparam">void</span> )

<span class="function">session\_reset</span> reinitializes a session
with original values stored in session storage. This function requires
an active session and discards changes in $\_SESSION.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                   |
|---------|-------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The return type of this function is <span class="type">bool</span> now. Formerly, it has been <span class="type">void</span>. |

### See Also

-   `$_SESSION`
-   The
    <a href="/session/setup.html#" class="link">session.auto_start</a>
    configuration directive
-   <span class="function">session\_start</span>
-   <span class="function">session\_abort</span>
-   <span class="function">session\_commit</span>

session\_save\_path
===================

Get and/or set the current session save path

### Description

<span class="type">string</span> <span
class="methodname">session\_save\_path</span> (\[ <span
class="methodparam"><span class="type">string</span> `$path`</span> \] )

<span class="function">session\_save\_path</span> returns the path of
the current directory used to save session data.

### Parameters

`path`  
Session data path. If specified, the path to which data is saved will be
changed. <span class="function">session\_save\_path</span> needs to be
called before <span class="function">session\_start</span> for that
purpose.

> **Note**:
>
> On some operating systems, you may want to specify a path on a
> filesystem that handles lots of small files efficiently. For example,
> on Linux, reiserfs may provide better performance than ext2fs.

### Return Values

Returns the path of the current directory used for data storage.

### See Also

-   The
    <a href="/session/setup.html#" class="link">session.save_path</a>
    configuration directive

session\_set\_cookie\_params
============================

Set the session cookie parameters

### Description

<span class="type">bool</span> <span
class="methodname">session\_set\_cookie\_params</span> ( <span
class="methodparam"><span class="type">int</span> `$lifetime`</span> \[,
<span class="methodparam"><span class="type">string</span>
`$path`</span> \[, <span class="methodparam"><span
class="type">string</span> `$domain`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$secure`<span
class="initializer"> = **`FALSE`**</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$httponly`<span
class="initializer"> = **`FALSE`**</span></span> \]\]\]\] )

<span class="type">bool</span> <span
class="methodname">session\_set\_cookie\_params</span> ( <span
class="methodparam"><span class="type">array</span> `$options`</span> )

Set cookie parameters defined in the `php.ini` file. The effect of this
function only lasts for the duration of the script. Thus, you need to
call <span class="function">session\_set\_cookie\_params</span> for
every request and before <span class="function">session\_start</span> is
called.

This function updates the runtime ini values of the corresponding PHP
ini configuration keys which can be retrieved with the <span
class="function">ini\_get</span>.

### Parameters

`lifetime`  
<a href="/session/setup.html#" class="link">Lifetime</a> of the session
cookie, defined in seconds.

`path`  
<a href="/session/setup.html#" class="link">Path</a> on the domain where
the cookie will work. Use a single slash ('/') for all paths on the
domain.

`domain`  
Cookie <a href="/session/setup.html#" class="link">domain</a>, for
example 'www.php.net'. To make cookies visible on all subdomains then
the domain must be prefixed with a dot like '.php.net'.

`secure`  
If **`TRUE`** cookie will only be sent over
<a href="/session/setup.html#" class="link">secure</a> connections.

`httponly`  
If set to **`TRUE`** then PHP will attempt to send the
<a href="/session/setup.html#" class="link">httponly</a> flag when
setting the session cookie.

`options`  
An associative <span class="type">array</span> which may have any of the
keys *lifetime*, *path*, *domain*, *secure*, *httponly* and *samesite*.
The values have the same meaning as described for the parameters with
the same name. The value of the *samesite* element should be either
*Lax* or *Strict*. If any of the allowed options are not given, their
default values are the same as the default values of the explicit
parameters. If the *samesite* element is omitted, no SameSite cookie
attribute is set.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                                   |
|---------|-----------------------------------------------------------------------------------------------------------------------------------------------|
| 7.3.0   | An alternative signature supporting an `options` array has been added. This signature supports also setting of the SameSite cookie attribute. |
| 7.2.0   | Returns **`TRUE`** on success or **`FALSE`** on failure. Formerly the function returned <span class="type">void</span>.                       |

### See Also

-   <a href="/session/setup.html#" class="link">session.cookie_lifetime</a>
-   <a href="/session/setup.html#" class="link">session.cookie_path</a>
-   <a href="/session/setup.html#" class="link">session.cookie_domain</a>
-   <a href="/session/setup.html#" class="link">session.cookie_secure</a>
-   <a href="/session/setup.html#" class="link">session.cookie_httponly</a>
-   <a href="/session/setup.html#" class="link">session.cookie_samesite</a>
-   <span class="function">session\_get\_cookie\_params</span>

session\_set\_save\_handler
===========================

Sets user-level session storage functions

### Description

<span class="type">bool</span> <span
class="methodname">session\_set\_save\_handler</span> ( <span
class="methodparam"><span class="type">callable</span> `$open`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$close`</span> , <span class="methodparam"><span
class="type">callable</span> `$read`</span> , <span
class="methodparam"><span class="type">callable</span> `$write`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$destroy`</span> , <span class="methodparam"><span
class="type">callable</span> `$gc`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$create_sid`</span> \[, <span class="methodparam"><span
class="type">callable</span> `$validate_sid`</span> \[, <span
class="methodparam"><span class="type">callable</span>
`$update_timestamp`</span> \]\]\] )

Since PHP 5.4 it is possible to register the following prototype:

<span class="type">bool</span> <span
class="methodname">session\_set\_save\_handler</span> ( <span
class="methodparam"><span class="type">object</span>
`$sessionhandler`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$register_shutdown`<span class="initializer">
= **`TRUE`**</span></span> \] )

<span class="function">session\_set\_save\_handler</span> sets the
user-level session storage functions which are used for storing and
retrieving data associated with a session. This is most useful when a
storage method other than those supplied by PHP sessions is preferred,
e.g. storing the session data in a local database.

### Parameters

This function has two prototypes.

`sessionhandler`  
An instance of a class implementing <span
class="interfacename">SessionHandlerInterface</span>, and optionally
<span class="interfacename">SessionIdInterface</span> and/or <span
class="interfacename">SessionUpdateTimestampHandlerInterface</span>,
such as <span class="classname">SessionHandler</span>, to register as
the session handler. Since PHP 5.4 only.

`register_shutdown`  
Register <span class="function">session\_write\_close</span> as a <span
class="function">register\_shutdown\_function</span> function.

or

`open`  
A callable with the following signature:

<span class="type">bool</span> <span class="methodname"><span
class="replaceable">open</span></span> ( <span class="methodparam"><span
class="type">string</span> `$savePath`</span> , <span
class="methodparam"><span class="type">string</span>
`$sessionName`</span> )

The open callback works like a constructor in classes and is executed
when the session is being opened. It is the first callback function
executed when the session is started automatically or manually with
<span class="function">session\_start</span>. Return value is **`TRUE`**
for success, **`FALSE`** for failure.

`close`  
A callable with the following signature:

<span class="type">bool</span> <span class="methodname"><span
class="replaceable">close</span></span> ( <span
class="methodparam">void</span> )

The close callback works like a destructor in classes and is executed
after the session write callback has been called. It is also invoked
when <span class="function">session\_write\_close</span> is called.
Return value should be **`TRUE`** for success, **`FALSE`** for failure.

`read`  
A callable with the following signature:

<span class="type">bool</span> <span class="methodname"><span
class="replaceable">read</span></span> ( <span class="methodparam"><span
class="type">string</span> `$sessionId`</span> )

The `read` callback must always return a session encoded (serialized)
string, or an empty string if there is no data to read.

This callback is called internally by PHP when the session starts or
when <span class="function">session\_start</span> is called. Before this
callback is invoked PHP will invoke the `open` callback.

The value this callback returns must be in exactly the same serialized
format that was originally passed for storage to the `write` callback.
The value returned will be unserialized automatically by PHP and used to
populate the `$_SESSION` superglobal. While the data looks similar to
<span class="function">serialize</span> please note it is a different
format which is specified in the
<a href="/session/setup.html#" class="link">session.serialize_handler</a>
ini setting.

`write`  
A callable with the following signature:

<span class="type">bool</span> <span class="methodname"><span
class="replaceable">write</span></span> ( <span
class="methodparam"><span class="type">string</span> `$sessionId`</span>
, <span class="methodparam"><span class="type">string</span>
`$data`</span> )

The `write` callback is called when the session needs to be saved and
closed. This callback receives the current session ID a serialized
version the `$_SESSION` superglobal. The serialization method used
internally by PHP is specified in the
<a href="/session/setup.html#" class="link">session.serialize_handler</a>
ini setting.

The serialized session data passed to this callback should be stored
against the passed session ID. When retrieving this data, the `read`
callback must return the exact value that was originally passed to the
`write` callback.

This callback is invoked when PHP shuts down or explicitly when <span
class="function">session\_write\_close</span> is called. Note that after
executing this function PHP will internally execute the `close`
callback.

> **Note**:
>
> The "write" handler is not executed until after the output stream is
> closed. Thus, output from debugging statements in the "write" handler
> will never be seen in the browser. If debugging output is necessary,
> it is suggested that the debug output be written to a file instead.

`destroy`  
A callable with the following signature:

<span class="type">bool</span> <span class="methodname"><span
class="replaceable">destroy</span></span> ( <span
class="methodparam"><span class="type">string</span> `$sessionId`</span>
)

This callback is executed when a session is destroyed with <span
class="function">session\_destroy</span> or with <span
class="function">session\_regenerate\_id</span> with the destroy
parameter set to **`TRUE`**. Return value should be **`TRUE`** for
success, **`FALSE`** for failure.

`gc`  
A callable with the following signature:

<span class="type">bool</span> <span class="methodname"><span
class="replaceable">gc</span></span> ( <span class="methodparam"><span
class="type">int</span> `$lifetime`</span> )

The garbage collector callback is invoked internally by PHP periodically
in order to purge old session data. The frequency is controlled by
<a href="/session/setup.html#" class="link">session.gc_probability</a>
and <a href="/session/setup.html#" class="link">session.gc_divisor</a>.
The value of lifetime which is passed to this callback can be set in
<a href="/session/setup.html#" class="link">session.gc_maxlifetime</a>.
Return value should be **`TRUE`** for success, **`FALSE`** for failure.

`create_sid`  
A callable with the following signature:

<span class="type">string</span> <span class="methodname"><span
class="replaceable">create\_sid</span></span> ( <span
class="methodparam">void</span> )

This callback is executed when a new session ID is required. No
parameters are provided, and the return value should be a string that is
a valid session ID for your handler.

`validate_sid`  
A callable with the following signature:

<span class="type">bool</span> <span class="methodname"><span
class="replaceable">validate\_sid</span></span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> )

This callback is executed when a session is to be started, a session ID
is supplied and
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
is enabled. The `key` is the session ID to validate. A session ID is
valid, if a session with that ID already exists. The return value should
be **`TRUE`** for success, **`FALSE`** for failure.

`update_timestamp`  
A callable with the following signature:

<span class="type">string</span> <span class="methodname"><span
class="replaceable">update\_timestamp</span></span> ( <span
class="methodparam"><span class="type">string</span> `$key`</span> ,
<span class="methodparam"><span class="type">string</span> `$val`</span>
)

This callback is executed when a session is updated. `key` is the
session ID, `val` is the session data. The return value should be
**`TRUE`** for success, **`FALSE`** for failure.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Examples

**Example \#1 Custom session handler: see full code in <span
class="classname">SessionHandlerInterface</span> synopsis.**

The following code is for PHP version 5.4.0 and above. We just show the
invocation here, the full example can be seen in the <span
class="classname">SessionHandlerInterface</span> synopsis linked above.

Note we use the OOP prototype with <span
class="function">session\_set\_save\_handler</span> and register the
shutdown function using the function's parameter flag. This is generally
advised when registering objects as session save handlers.

``` php
<?php
class MySessionHandler implements SessionHandlerInterface
{
    // implement interfaces here
}

$handler = new MySessionHandler();
session_set_save_handler($handler, true);
session_start();

// proceed to set and retrieve values by key from $_SESSION
```

**Example \#2 Custom session save handler using objects**

The following code is for PHP versions less than 5.4.0.

The following example provides file based session storage similar to the
PHP sessions default save handler `files`. This example could easily be
extended to cover database storage using your favorite PHP supported
database engine.

Note we additionally register the shutdown function <span
class="function">session\_write\_close</span> using <span
class="function">register\_shutdown\_function</span> under PHP less than
5.4.0. This is generally advised when registering objects as session
save handlers under PHP less than 5.4.0.

``` php
<?php
class FileSessionHandler
{
    private $savePath;

    function open($savePath, $sessionName)
    {
        $this->savePath = $savePath;
        if (!is_dir($this->savePath)) {
            mkdir($this->savePath, 0777);
        }

        return true;
    }

    function close()
    {
        return true;
    }

    function read($id)
    {
        return (string)@file_get_contents("$this->savePath/sess_$id");
    }

    function write($id, $data)
    {
        return file_put_contents("$this->savePath/sess_$id", $data) === false ? false : true;
    }

    function destroy($id)
    {
        $file = "$this->savePath/sess_$id";
        if (file_exists($file)) {
            unlink($file);
        }

        return true;
    }

    function gc($maxlifetime)
    {
        foreach (glob("$this->savePath/sess_*") as $file) {
            if (filemtime($file) + $maxlifetime < time() && file_exists($file)) {
                unlink($file);
            }
        }

        return true;
    }
}

$handler = new FileSessionHandler();
session_set_save_handler(
    array($handler, 'open'),
    array($handler, 'close'),
    array($handler, 'read'),
    array($handler, 'write'),
    array($handler, 'destroy'),
    array($handler, 'gc')
    );

// the following prevents unexpected effects when using objects as save handlers
register_shutdown_function('session_write_close');

session_start();
// proceed to set and retrieve values by key from $_SESSION
```

### Notes

**Warning**

When using objects as session save handlers, it is important to register
the shutdown function with PHP to avoid unexpected side-effects from the
way PHP internally destroys objects on shutdown and may prevent the
`write` and `close` from being called. Typically you should register
`'session_write_close'` using the <span
class="function">register\_shutdown\_function</span> function.

As of PHP 5.4.0 you can use <span
class="function">session\_register\_shutdown</span> or simply use the
'register shutdown' flag when invoking <span
class="function">session\_set\_save\_handler</span> using the OOP method
and passing an instance that implements <span
class="classname">SessionHandlerInterface</span>.

**Warning**

As of PHP 5.0.5 the `write` and `close` handlers are called after object
destruction and therefore cannot use objects or throw exceptions.
Exceptions are not able to be caught since will not be caught nor will
any exception trace be displayed and the execution will just cease
unexpectedly. The object destructors can however use sessions.

It is possible to call <span
class="function">session\_write\_close</span> from the destructor to
solve this chicken and egg problem but the most reliable way is to
register the shutdown function as described above.

**Warning**

Current working directory is changed with some SAPIs if session is
closed in the script termination. It is possible to close the session
earlier with <span class="function">session\_write\_close</span>.

### See Also

-   The
    <a href="/session/setup.html#" class="link">session.save_handler</a>
    configuration directive
-   The
    <a href="/session/setup.html#" class="link">session.serialize_handler</a>
    configuration directive.
-   The <span class="function">register\_shutdown\_function</span>
-   The <span class="function">session\_register\_shutdown</span> for
    PHP 5.4.0+
-   Refer to
    <a href="https://github.com/php/php-src/blob/master/ext/session/tests/save_handler.inc" class="link external">» save_handler.inc</a>
    for a full procedural reference implementation

session\_start
==============

Start new or resume existing session

### Description

<span class="type">bool</span> <span
class="methodname">session\_start</span> (\[ <span
class="methodparam"><span class="type">array</span> `$options`<span
class="initializer"> = array()</span></span> \] )

<span class="function">session\_start</span> creates a session or
resumes the current one based on a session identifier passed via a GET
or POST request, or passed via a cookie.

When <span class="function">session\_start</span> is called or when a
session auto starts, PHP will call the open and read session save
handlers. These will either be a built-in save handler provided by
default or by PHP extensions (such as SQLite or Memcached); or can be
custom handler as defined by <span
class="function">session\_set\_save\_handler</span>. The read callback
will retrieve any existing session data (stored in a special serialized
format) and will be unserialized and used to automatically populate the
$\_SESSION superglobal when the read callback returns the saved session
data back to PHP session handling.

To use a named session, call <span class="function">session\_name</span>
before calling <span class="function">session\_start</span>.

When
<a href="/session/setup.html#" class="link">session.use_trans_sid</a> is
enabled, the <span class="function">session\_start</span> function will
register an internal output handler for URL rewriting.

If a user uses *ob\_gzhandler* or similar with <span
class="function">ob\_start</span>, the function order is important for
proper output. For example, *ob\_gzhandler* must be registered before
starting the session.

### Parameters

`options`  
If provided, this is an associative array of options that will override
the currently set
<a href="/session/setup.html#Runtime%20Configuration" class="link">session configuration directives</a>.
The keys should not include the *session.* prefix.

In addition to the normal set of configuration directives, a
*read\_and\_close* option may also be provided. If set to **`TRUE`**,
this will result in the session being closed immediately after being
read, thereby avoiding unnecessary locking if the session data won't be
changed.

### Return Values

This function returns **`TRUE`** if a session was successfully started,
otherwise **`FALSE`**.

### Changelog

| Version | Description                                                                                                                                     |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.1.0   | <span class="function">session\_start</span> now returns **`FALSE`** and no longer initializes `$_SESSION` when it failed to start the session. |

### Examples

#### A basic session example

**Example \#1 `page1.php`**

``` php
<?php
// page1.php

session_start();

echo 'Welcome to page #1';

$_SESSION['favcolor'] = 'green';
$_SESSION['animal']   = 'cat';
$_SESSION['time']     = time();

// Works if session cookie was accepted
echo '<br /><a href="page2.php">page 2</a>';

// Or maybe pass along the session id, if needed
echo '<br /><a href="page2.php?' . SID . '">page 2</a>';
?>
```

After viewing `page1.php`, the second page `page2.php` will magically
contain the session data. Read the
<a href="/ref/session.html" class="link">session reference</a> for
information on
<a href="/session/examples.html#Passing%20the%20Session%20ID" class="link">propagating session ids</a>
as it, for example, explains what the constant **`SID`** is all about.

**Example \#2 `page2.php`**

``` php
<?php
// page2.php

session_start();

echo 'Welcome to page #2<br />';

echo $_SESSION['favcolor']; // green
echo $_SESSION['animal'];   // cat
echo date('Y m d H:i:s', $_SESSION['time']);

// You may want to use SID here, like we did in page1.php
echo '<br /><a href="page1.php">page 1</a>';
?>
```

#### Providing options to <span class="function">session\_start</span>

**Example \#3 Overriding the cookie lifetime**

``` php
<?php
// This sends a persistent cookie that lasts a day.
session_start([
    'cookie_lifetime' => 86400,
]);
?>
```

**Example \#4 Reading the session and closing it**

``` php
<?php
// If we know we don't need to change anything in the
// session, we can just read and close rightaway to avoid
// locking the session file and blocking other pages
session_start([
    'cookie_lifetime' => 86400,
    'read_and_close'  => true,
]);
```

### Notes

> **Note**:
>
> To use cookie-based sessions, <span
> class="function">session\_start</span> must be called before
> outputting anything to the browser.

> **Note**:
>
> Use of
> <a href="/zlib/setup.html#" class="link">zlib.output_compression</a>
> is recommended instead of <span class="function">ob\_gzhandler</span>

> **Note**:
>
> This function sends out several HTTP headers depending on the
> configuration. See <span
> class="function">session\_cache\_limiter</span> to customize these
> headers.

### See Also

-   `$_SESSION`
-   The
    <a href="/session/setup.html#" class="link">session.auto_start</a>
    configuration directive
-   <span class="function">session\_id</span>

session\_status
===============

Returns the current session status

### Description

<span class="type">int</span> <span
class="methodname">session\_status</span> ( <span
class="methodparam">void</span> )

<span class="function">session\_status</span> is used to return the
current session status.

### Return Values

-   <span class="simpara">**`PHP_SESSION_DISABLED`** if sessions are
    disabled.</span>
-   <span class="simpara">**`PHP_SESSION_NONE`** if sessions are
    enabled, but none exists.</span>
-   <span class="simpara">**`PHP_SESSION_ACTIVE`** if sessions are
    enabled, and one exists.</span>

### See Also

-   <span class="function">session\_start</span>

session\_unregister
===================

Unregister a global variable from the current session

### Description

<span class="type">bool</span> <span
class="methodname">session\_unregister</span> ( <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="function">session\_unregister</span> unregisters the global
variable named `name` from the current session.

**Warning**

This function has been *DEPRECATED* as of PHP 5.3.0 and *REMOVED* as of
PHP 5.4.0.

### Parameters

`name`  
The variable name.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Notes

> **Note**:
>
> If `$_SESSION` is used, use <span class="function">unset</span> to
> unregister a session variable. Do not <span
> class="function">unset</span> `$_SESSION` itself as this will disable
> the special function of the `$_SESSION` superglobal.

**Caution**

This function does not unset the corresponding global variable for
`name`, it only prevents the variable from being saved as part of the
session. You must call <span class="function">unset</span> to remove the
corresponding global variable.

**Caution**

If you are using `$_SESSION` (or `$HTTP_SESSION_VARS`), do not use <span
class="function">session\_register</span>, <span
class="function">session\_is\_registered</span> and <span
class="function">session\_unregister</span>.

session\_unset
==============

Free all session variables

### Description

<span class="type">bool</span> <span
class="methodname">session\_unset</span> ( <span
class="methodparam">void</span> )

The <span class="function">session\_unset</span> function frees all
session variables currently registered.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                   |
|---------|-------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The return type of this function is <span class="type">bool</span> now. Formerly, it has been <span class="type">void</span>. |

### Notes

> **Note**:
>
> If `$_SESSION` is used, use <span class="function">unset</span> to
> unregister a session variable, i.e. *unset
> ($\_SESSION\['varname'\]);*.

**Caution**

Do NOT unset the whole `$_SESSION` with *unset($\_SESSION)* as this will
disable the registering of session variables through the `$_SESSION`
superglobal.

> **Note**:
>
> Only use <span class="function">session\_unset</span> for older
> deprecated code that does not use `$_SESSION`.

session\_write\_close
=====================

Write session data and end session

### Description

<span class="type">bool</span> <span
class="methodname">session\_write\_close</span> ( <span
class="methodparam">void</span> )

End the current session and store session data.

Session data is usually stored after your script terminated without the
need to call <span class="function">session\_write\_close</span>, but as
session data is locked to prevent concurrent writes only one script may
operate on a session at any time. When using framesets together with
sessions you will experience the frames loading one by one due to this
locking. You can reduce the time needed to load all the frames by ending
the session as soon as all changes to session variables are done.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### Changelog

| Version | Description                                                                                                                   |
|---------|-------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The return type of this function is <span class="type">bool</span> now. Formerly, it has been <span class="type">void</span>. |

### See Also

-   The <span class="function">session\_register\_shutdown</span>

**Table of Contents**

-   [session\_abort](/ref/session.html#session_abort) — Discard session
    array changes and finish session
-   [session\_cache\_expire](/ref/session.html#session_cache_expire) —
    Get and/or set current cache expire
-   [session\_cache\_limiter](/ref/session.html#session_cache_limiter) —
    Get and/or set the current cache limiter
-   [session\_commit](/ref/session.html#session_commit) — Alias of
    session\_write\_close
-   [session\_create\_id](/ref/session.html#session_create_id) — Create
    new session id
-   [session\_decode](/ref/session.html#session_decode) — Decodes
    session data from a session encoded string
-   [session\_destroy](/ref/session.html#session_destroy) — Destroys all
    data registered to a session
-   [session\_encode](/ref/session.html#session_encode) — Encodes the
    current session data as a session encoded string
-   [session\_gc](/ref/session.html#session_gc) — Perform session data
    garbage collection
-   [session\_get\_cookie\_params](/ref/session.html#session_get_cookie_params)
    — Get the session cookie parameters
-   [session\_id](/ref/session.html#session_id) — Get and/or set the
    current session id
-   [session\_is\_registered](/ref/session.html#session_is_registered) —
    Find out whether a global variable is registered in a session
-   [session\_module\_name](/ref/session.html#session_module_name) — Get
    and/or set the current session module
-   [session\_name](/ref/session.html#session_name) — Get and/or set the
    current session name
-   [session\_regenerate\_id](/ref/session.html#session_regenerate_id) —
    Update the current session id with a newly generated one
-   [session\_register\_shutdown](/ref/session.html#session_register_shutdown)
    — Session shutdown function
-   [session\_register](/ref/session.html#session_register) — Register
    one or more global variables with the current session
-   [session\_reset](/ref/session.html#session_reset) — Re-initialize
    session array with original values
-   [session\_save\_path](/ref/session.html#session_save_path) — Get
    and/or set the current session save path
-   [session\_set\_cookie\_params](/ref/session.html#session_set_cookie_params)
    — Set the session cookie parameters
-   [session\_set\_save\_handler](/ref/session.html#session_set_save_handler)
    — Sets user-level session storage functions
-   [session\_start](/ref/session.html#session_start) — Start new or
    resume existing session
-   [session\_status](/ref/session.html#session_status) — Returns the
    current session status
-   [session\_unregister](/ref/session.html#session_unregister) —
    Unregister a global variable from the current session
-   [session\_unset](/ref/session.html#session_unset) — Free all session
    variables
-   [session\_write\_close](/ref/session.html#session_write_close) —
    Write session data and end session

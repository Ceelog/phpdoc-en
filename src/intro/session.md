Session support in PHP consists of a way to preserve certain data across
subsequent accesses.

A visitor accessing your web site is assigned a unique id, the so-called
session id. This is either stored in a cookie on the user side or is
propagated in the URL.

The session support allows you to store data between requests in the
`$_SESSION` superglobal array. When a visitor accesses your site, PHP
will check automatically (if
<a href="/session/setup.html#" class="link">session.auto_start</a> is
set to 1) or on your request (explicitly through <span
class="function">session\_start</span>) whether a specific session id
has been sent with the request. If this is the case, the prior saved
environment is recreated.

**Caution**

If you turn on
<a href="/session/setup.html#" class="link">session.auto_start</a> then
the only way to put objects into your sessions is to load its class
definition using
<a href="/ini/core.html#ini.auto-prepend-file" class="link">auto_prepend_file</a>
in which you load the class definition else you will have to <span
class="function">serialize</span> your object and <span
class="function">unserialize</span> it afterwards.

`$_SESSION` (and all registered variables) are serialized internally by
PHP using the serialization handler specified by the
<a href="/session/setup.html#" class="link">session.serialize_handler</a>
ini setting, after the request finishes. Registered variables which are
undefined are marked as being not defined. On subsequent accesses, these
are not defined by the session module unless the user defines them
later.

**Warning**

Because session data is serialized, <span class="type">resource</span>
variables cannot be stored in the session.

Serialize handlers (*php* and *php\_binary*) inherit register\_globals
limitations. Therefore, numeric index or string index contains special
characters (*\|* and *!*) cannot be used. Using these will end up with
errors at script shutdown. *php\_serialize* does not have such
limitations.

> **Note**:
>
> Please note when working with sessions that a record of a session is
> not created until a variable has been registered using the <span
> class="function">session\_register</span> function or by adding a new
> key to the `$_SESSION` superglobal array. This holds true regardless
> of if a session has been started using the <span
> class="function">session\_start</span> function.

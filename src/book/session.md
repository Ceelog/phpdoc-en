Session Handling
================

**Table of Contents**

-   [Introduction](/intro/session.html)
-   [Installing/Configuring](/session/setup.html)
    -   [Requirements](/session/setup.html#Requirements)
    -   [Installation](/session/setup.html#Installation)
    -   [Runtime
        Configuration](/session/setup.html#Runtime%20Configuration)
    -   [Resource Types](/session/setup.html#Resource%20Types)
-   [Predefined Constants](/session/constants.html)
-   [Examples](/session/examples.html)
    -   [Basic usage](/session/examples.html#Basic%20usage)
    -   [Passing the Session
        ID](/session/examples.html#Passing%20the%20Session%20ID)
    -   [Custom Session
        Handlers](/session/examples.html#Custom%20Session%20Handlers)
-   [Session Upload Progress](/session/upload-progress.html)
-   [Sessions and Security](/session/security.html)
    -   [Session Management
        Basics](/session/security.html#Session%20Management%20Basics)
    -   [Securing Session INI
        Settings](/session/security.html#Securing%20Session%20INI%20Settings)
-   [Session Functions](/ref/session.html)
    -   [session\_abort](/ref/session.html#session_abort) — Discard
        session array changes and finish session
    -   [session\_cache\_expire](/ref/session.html#session_cache_expire)
        — Get and/or set current cache expire
    -   [session\_cache\_limiter](/ref/session.html#session_cache_limiter)
        — Get and/or set the current cache limiter
    -   [session\_commit](/ref/session.html#session_commit) — Alias of
        session\_write\_close
    -   [session\_create\_id](/ref/session.html#session_create_id) —
        Create new session id
    -   [session\_decode](/ref/session.html#session_decode) — Decodes
        session data from a session encoded string
    -   [session\_destroy](/ref/session.html#session_destroy) — Destroys
        all data registered to a session
    -   [session\_encode](/ref/session.html#session_encode) — Encodes
        the current session data as a session encoded string
    -   [session\_gc](/ref/session.html#session_gc) — Perform session
        data garbage collection
    -   [session\_get\_cookie\_params](/ref/session.html#session_get_cookie_params)
        — Get the session cookie parameters
    -   [session\_id](/ref/session.html#session_id) — Get and/or set the
        current session id
    -   [session\_is\_registered](/ref/session.html#session_is_registered)
        — Find out whether a global variable is registered in a session
    -   [session\_module\_name](/ref/session.html#session_module_name) —
        Get and/or set the current session module
    -   [session\_name](/ref/session.html#session_name) — Get and/or set
        the current session name
    -   [session\_regenerate\_id](/ref/session.html#session_regenerate_id)
        — Update the current session id with a newly generated one
    -   [session\_register\_shutdown](/ref/session.html#session_register_shutdown)
        — Session shutdown function
    -   [session\_register](/ref/session.html#session_register) —
        Register one or more global variables with the current session
    -   [session\_reset](/ref/session.html#session_reset) —
        Re-initialize session array with original values
    -   [session\_save\_path](/ref/session.html#session_save_path) — Get
        and/or set the current session save path
    -   [session\_set\_cookie\_params](/ref/session.html#session_set_cookie_params)
        — Set the session cookie parameters
    -   [session\_set\_save\_handler](/ref/session.html#session_set_save_handler)
        — Sets user-level session storage functions
    -   [session\_start](/ref/session.html#session_start) — Start new or
        resume existing session
    -   [session\_status](/ref/session.html#session_status) — Returns
        the current session status
    -   [session\_unregister](/ref/session.html#session_unregister) —
        Unregister a global variable from the current session
    -   [session\_unset](/ref/session.html#session_unset) — Free all
        session variables
    -   [session\_write\_close](/ref/session.html#session_write_close) —
        Write session data and end session
-   [SessionHandler](/class/sessionhandler.html) — The SessionHandler
    class
    -   [SessionHandler::close](/class/sessionhandler.html#SessionHandler::close)
        — Close the session
    -   [SessionHandler::create\_sid](/class/sessionhandler.html#SessionHandler::create_sid)
        — Return a new session ID
    -   [SessionHandler::destroy](/class/sessionhandler.html#SessionHandler::destroy)
        — Destroy a session
    -   [SessionHandler::gc](/class/sessionhandler.html#SessionHandler::gc)
        — Cleanup old sessions
    -   [SessionHandler::open](/class/sessionhandler.html#SessionHandler::open)
        — Initialize session
    -   [SessionHandler::read](/class/sessionhandler.html#SessionHandler::read)
        — Read session data
    -   [SessionHandler::write](/class/sessionhandler.html#SessionHandler::write)
        — Write session data
-   [SessionHandlerInterface](/class/sessionhandlerinterface.html) — The
    SessionHandlerInterface class
    -   [SessionHandlerInterface::close](/class/sessionhandlerinterface.html#SessionHandlerInterface::close)
        — Close the session
    -   [SessionHandlerInterface::destroy](/class/sessionhandlerinterface.html#SessionHandlerInterface::destroy)
        — Destroy a session
    -   [SessionHandlerInterface::gc](/class/sessionhandlerinterface.html#SessionHandlerInterface::gc)
        — Cleanup old sessions
    -   [SessionHandlerInterface::open](/class/sessionhandlerinterface.html#SessionHandlerInterface::open)
        — Initialize session
    -   [SessionHandlerInterface::read](/class/sessionhandlerinterface.html#SessionHandlerInterface::read)
        — Read session data
    -   [SessionHandlerInterface::write](/class/sessionhandlerinterface.html#SessionHandlerInterface::write)
        — Write session data
-   [SessionIdInterface](/class/sessionidinterface.html) — The
    SessionIdInterface interface
    -   [SessionIdInterface::create\_sid](/class/sessionidinterface.html#SessionIdInterface::create_sid)
        — Create session ID
-   [SessionUpdateTimestampHandlerInterface](/class/sessionupdatetimestamphandlerinterface.html)
    — The SessionUpdateTimestampHandlerInterface interface
    -   [SessionUpdateTimestampHandlerInterface::updateTimestamp](/class/sessionupdatetimestamphandlerinterface.html#SessionUpdateTimestampHandlerInterface::updateTimestamp)
        — Update timestamp
    -   [SessionUpdateTimestampHandlerInterface::validateId](/class/sessionupdatetimestamphandlerinterface.html#SessionUpdateTimestampHandlerInterface::validateId)
        — Validate ID

Introduction
------------

<span class="classname">SessionHandler</span> is a special class that
can be used to expose the current internal PHP session save handler by
inheritance. There are seven methods which wrap the seven internal
session save handler callbacks (`open`, `close`, `read`, `write`,
`destroy`, `gc` and `create_sid`). By default, this class will wrap
whatever internal save handler is set as defined by the
<a href="/session/setup.html#" class="link">session.save_handler</a>
configuration directive which is usually `files` by default. Other
internal session save handlers are provided by PHP extensions such as
SQLite (as `sqlite`), Memcache (as `memcache`), and Memcached (as
`memcached`).

When a plain instance of <span class="classname">SessionHandler</span>
is set as the save handler using <span
class="function">session\_set\_save\_handler</span> it will wrap the
current save handlers. A class extending from <span
class="classname">SessionHandler</span> allows you to override the
methods or intercept or filter them by calls the parent class methods
which ultimately wrap the internal PHP session handlers.

This allows you, for example, to intercept the `read` and `write`
methods to encrypt/decrypt the session data and then pass the result to
and from the parent class. Alternatively one might chose to entirely
override a method like the garbage collection callback `gc`.

Because the <span class="classname">SessionHandler</span> wraps the
current internal save handler methods, the above example of encryption
can be applied to any internal save handler without having to know the
internals of the handlers.

To use this class, first set the save handler you wish to expose using
<a href="/session/setup.html#" class="link">session.save_handler</a> and
then pass an instance of <span class="classname">SessionHandler</span>
or one extending it to <span
class="function">session\_set\_save\_handler</span>.

Please note the callback methods of this class are designed to be called
internally by PHP and are not meant to be called from user-space code.
The return values are equally processed internally by PHP. For more
information on the session workflow, please refer <span
class="function">session\_set\_save\_handler</span>.

Class synopsis
--------------

**SessionHandler**

<span class="ooclass"> class **SessionHandler** </span> <span
class="oointerface">implements <span
class="interfacename">SessionHandlerInterface</span></span> <span
class="oointerface">, <span
class="interfacename">SessionIdInterface</span></span> {

/\* Methods \*/

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">close</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">create\_sid</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">destroy</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">bool</span></span> <span
class="methodname">gc</span> ( <span class="methodparam"><span
class="type">int</span> `$max_lifetime`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">open</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> , <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">read</span> ( <span class="methodparam"><span
class="type">string</span> `$id`</span> )

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">write</span> ( <span class="methodparam"><span
class="type">string</span> `$id`</span> , <span
class="methodparam"><span class="type">string</span> `$data`</span> )

}

**Warning**

This class is designed to expose the current internal PHP session save
handler, if you want to write your own custom save handlers, please
implement the <span class="classname">SessionHandlerInterface</span>
interface instead of extending from <span
class="classname">SessionHandler</span>.

Changelog
---------

| Version | Description                                                      |
|---------|------------------------------------------------------------------|
| 5.5.1   | Added <span class="function">SessionHandler::create\_sid</span>. |

**Example \#1 Using <span class="classname">SessionHandler</span> to add
encryption to internal PHP save handlers.**

``` php
<?php

 /**
  * decrypt AES 256
  *
  * @param data $edata
  * @param string $password
  * @return decrypted data
  */
function decrypt($edata, $password) {
    $data = base64_decode($edata);
    $salt = substr($data, 0, 16);
    $ct = substr($data, 16);

    $rounds = 3; // depends on key length
    $data00 = $password.$salt;
    $hash = array();
    $hash[0] = hash('sha256', $data00, true);
    $result = $hash[0];
    for ($i = 1; $i < $rounds; $i++) {
        $hash[$i] = hash('sha256', $hash[$i - 1].$data00, true);
        $result .= $hash[$i];
    }
    $key = substr($result, 0, 32);
    $iv  = substr($result, 32,16);

    return openssl_decrypt($ct, 'AES-256-CBC', $key, true, $iv);
  }

/**
 * crypt AES 256
 *
 * @param data $data
 * @param string $password
 * @return base64 encrypted data
 */
function encrypt($data, $password) {
    // Set a random salt
    $salt = openssl_random_pseudo_bytes(16);

    $salted = '';
    $dx = '';
    // Salt the key(32) and iv(16) = 48
    while (strlen($salted) < 48) {
      $dx = hash('sha256', $dx.$password.$salt, true);
      $salted .= $dx;
    }

    $key = substr($salted, 0, 32);
    $iv  = substr($salted, 32,16);

    $encrypted_data = openssl_encrypt($data, 'AES-256-CBC', $key, true, $iv);
    return base64_encode($salt . $encrypted_data);
}

class EncryptedSessionHandler extends SessionHandler
{
    private $key;

    public function __construct($key)
    {
        $this->key = $key;
    }

    public function read($id)
    {
        $data = parent::read($id);

        if (!$data) {
            return "";
        } else {
            return decrypt($data, $this->key);
        }
    }

    public function write($id, $data)
    {
        $data = encrypt($data, $this->key);

        return parent::write($id, $data);
    }
}

// we'll intercept the native 'files' handler, but will equally work
// with other internal native handlers like 'sqlite', 'memcache' or 'memcached'
// which are provided by PHP extensions.
ini_set('session.save_handler', 'files');

$key = 'secret_string';
$handler = new EncryptedSessionHandler($key);
session_set_save_handler($handler, true);
session_start();

// proceed to set and retrieve values by key from $_SESSION
```

> **Note**:
>
> Since this class' methods are designed to be called internally by PHP
> as part of the normal session workflow, child class calls to parent
> methods (i.e. the actual internal native handlers) will return
> **`FALSE`** unless the session has actually been started (either
> automatically, or by explicit <span
> class="function">session\_start</span>. This is important to consider
> when writing unit tests where the class methods might be invoked
> manually.

SessionHandler::close
=====================

Close the session

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SessionHandler::close</span> ( <span
class="methodparam">void</span> )

Closes the current session. This method is automatically executed
internally by PHP when closing the session, or explicitly via <span
class="function">session\_write\_close</span> (which first calls the
<span class="function">SessionHandler::write</span>).

This method wraps the internal PHP save handler defined in the
<a href="/session/setup.html#" class="link">session.save_handler</a> ini
setting that was set before this handler was activated by <span
class="function">session\_set\_save\_handler</span>.

If this class is extended by inheritiance, calling the parent `close`
method will invoke the wrapper for this method and therefore invoke the
associated internal callback. This allows the method to be overridden
and or intercepted.

For more information on what this method is expected to do, please refer
to the documentation at <span
class="function">SessionHandlerInterface::close</span>.

### Parameters

This function has no parameters.

### Return Values

The return value (usually **`TRUE`** on success, **`FALSE`** on
failure). Note this value is returned internally to PHP for processing.

SessionHandler::create\_sid
===========================

Return a new session ID

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SessionHandler::create\_sid</span> ( <span
class="methodparam">void</span> )

Generates and returns a new session ID.

### Return Values

A session ID valid for the default session handler.

### See Also

-   <span class="function">session\_id</span>
-   <span class="function">session\_create\_id</span>

SessionHandler::destroy
=======================

Destroy a session

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SessionHandler::destroy</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> )

Destroys a session. Called internally by PHP with <span
class="function">session\_regenerate\_id</span> (assuming the `$destroy`
is set to **`TRUE`**, by <span class="function">session\_destroy</span>
or when <span class="function">session\_decode</span> fails.

This method wraps the internal PHP save handler defined in the
<a href="/session/setup.html#" class="link">session.save_handler</a> ini
setting that was set before this handler was set by <span
class="function">session\_set\_save\_handler</span>.

If this class is extended by inheritiance, calling the parent `destroy`
method will invoke the wrapper for this method and therefore invoke the
associated internal callback. This allows this method to be overridden
and or intercepted and filtered.

For more information on what this method is expected to do, please refer
to the documentation at <span
class="function">SessionHandlerInterface::destroy</span>.

### Parameters

`id`  
The session ID being destroyed.

### Return Values

The return value (usually **`TRUE`** on success, **`FALSE`** on
failure). Note this value is returned internally to PHP for processing.

SessionHandler::gc
==================

Cleanup old sessions

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">bool</span></span> <span
class="methodname">SessionHandler::gc</span> ( <span
class="methodparam"><span class="type">int</span> `$max_lifetime`</span>
)

Cleans up expired sessions. Called randomly by PHP internally when a
session starts or when <span class="function">session\_start</span> is
invoked. The frequency this is called is based on the
<a href="/session/setup.html#" class="link">session.gc_divisor</a> and
<a href="/session/setup.html#" class="link">session.gc_probability</a>
configuration directives.

This method wraps the internal PHP save handler defined in the
<a href="/session/setup.html#" class="link">session.save_handler</a> ini
setting that was set before this handler was set by <span
class="function">session\_set\_save\_handler</span>.

If this class is extended by inheritiance, calling the parent `gc`
method will invoke the wrapper for this method and therefore invoke the
associated internal callback. This allows this method to be overridden
and or intercepted and filtered.

For more information on what this method is expected to do, please refer
to the documentation at <span
class="function">SessionHandlerInterface::gc</span>.

### Parameters

`max_lifetime`  
Sessions that have not updated for the last `max_lifetime` seconds will
be removed.

### Return Values

Returns the number of deleted sessions on success, or **`FALSE`** on
failure. Note this value is returned internally to PHP for processing.

### Changelog

| Version | Description                                                         |
|---------|---------------------------------------------------------------------|
| 7.1.0   | Prior to this version, the function returned **`TRUE`** on success. |

SessionHandler::open
====================

Initialize session

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SessionHandler::open</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

Create new session, or re-initialize existing session. Called internally
by PHP when a session starts either automatically or when <span
class="function">session\_start</span> is invoked.

This method wraps the internal PHP save handler defined in the
<a href="/session/setup.html#" class="link">session.save_handler</a> ini
setting that was set before this handler was set by <span
class="function">session\_set\_save\_handler</span>.

If this class is extended by inheritiance, calling the parent `open`
method will invoke the wrapper for this method and therefore invoke the
associated internal callback. This allows this method to be overridden
and or intercepted and filtered.

For more information on what this method is expected to do, please refer
to the documentation at <span
class="function">SessionHandlerInterface::open</span>.

### Parameters

`path`  
The path where to store/retrieve the session.

`name`  
The session name.

### Return Values

The return value (usually **`TRUE`** on success, **`FALSE`** on
failure). Note this value is returned internally to PHP for processing.

### See Also

-   The
    <a href="/session/setup.html#" class="link">session.auto-start</a>
    configuration directive.

SessionHandler::read
====================

Read session data

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">SessionHandler::read</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> )

Reads the session data from the session storage, and returns the result
back to PHP for internal processing. This method is called automatically
by PHP when a session is started (either automatically or explicitly
with <span class="function">session\_start</span> and is preceded by an
internal call to the <span class="function">SessionHandler::open</span>.

This method wraps the internal PHP save handler defined in the
<a href="/session/setup.html#" class="link">session.save_handler</a> ini
setting that was set before this handler was set by <span
class="function">session\_set\_save\_handler</span>.

If this class is extended by inheritance, calling the parent `read`
method will invoke the wrapper for this method and therefore invoke the
associated internal callback. This allows the method to be overridden
and or intercepted and filtered (for example, decrypting `$data` value
returned by the parent `read` method).

For more information on what this method is expected to do, please refer
to the documentation at <span
class="function">SessionHandlerInterface::read</span>.

### Parameters

`id`  
The session id to read data for.

### Return Values

Returns an encoded string of the read data. If nothing was read, it must
return an empty string. Note this value is returned internally to PHP
for processing.

### See Also

-   The
    <a href="/session/setup.html#" class="link">session.serialize_handler</a>
    configuration directive.

SessionHandler::write
=====================

Write session data

### Description

<span class="modifier">public</span> <span class="type">bool</span>
<span class="methodname">SessionHandler::write</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> )

Writes the session data to the session storage. Called by normal PHP
shutdown, by <span class="function">session\_write\_close</span>, or
when <span class="function">session\_register\_shutdown</span> fails.
PHP will call <span class="function">SessionHandler::close</span>
immediately after this method returns.

This method wraps the internal PHP save handler defined in the
<a href="/session/setup.html#" class="link">session.save_handler</a> ini
setting that was set before this handler was set by <span
class="function">session\_set\_save\_handler</span>.

If this class is extended by inheritiance, calling the parent `write`
method will invoke the wrapper for this method and therefore invoke the
associated internal callback. This allows this method to be overridden
and or intercepted and filtered (for example, encrypting the `$data`
value before sending it to the parent `write` method).

For more information on what this method is expected to do, please refer
to the documentation at <span
class="function">SessionHandlerInterface::write</span>.

### Parameters

`id`  
The session id.

`data`  
The encoded session data. This data is the result of the PHP internally
encoding the `$_SESSION` superglobal to a serialized string and passing
it as this parameter. Please note sessions use an alternative
serialization method.

### Return Values

The return value (usually **`TRUE`** on success, **`FALSE`** on
failure). Note this value is returned internally to PHP for processing.

### See Also

-   The
    <a href="/session/setup.html#" class="link">session.serialize_handler</a>
    configuration directive.

Introduction
------------

<span class="classname">SessionHandlerInterface</span> is an interface
which defines the minimal prototype for creating a custom session
handler. In order to pass a custom session handler to <span
class="function">session\_set\_save\_handler</span> using its OOP
invocation, the class can implement this interface.

Please note the callback methods of this class are designed to be called
internally by PHP and are not meant to be called from user-space code.

Class synopsis
--------------

**SessionHandlerInterface**

<span class="ooclass"> class **SessionHandlerInterface** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">close</span> ( <span class="methodparam">void</span>
)

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">destroy</span> ( <span class="methodparam"><span
class="type">string</span> `$id`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">bool</span></span> <span
class="methodname">gc</span> ( <span class="methodparam"><span
class="type">int</span> `$max_lifetime`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">open</span> ( <span class="methodparam"><span
class="type">string</span> `$path`</span> , <span
class="methodparam"><span class="type">string</span> `$name`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">read</span> ( <span class="methodparam"><span
class="type">string</span> `$id`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">write</span> ( <span class="methodparam"><span
class="type">string</span> `$id`</span> , <span
class="methodparam"><span class="type">string</span> `$data`</span> )

}

**Example \#1 Example using <span
class="classname">SessionHandlerInterface</span>**

The following example provides file based session storage similar to the
PHP sessions default save handler `files`. This example could easily be
extended to cover database storage using your favorite PHP supported
database engine.

Note we use the OOP prototype with <span
class="function">session\_set\_save\_handler</span> and register the
shutdown function using the function's parameter flag. This is generally
advised when registering objects as session save handlers.

**Caution**

For brevity, this example omits input validation. However, the *$id*
parameters are actually user supplied values which require proper
validation/sanitization to avoid vulnerabilities, such as path traversal
issues. *So do not use this example unmodified in production
environments.*

``` php
<?php
class MySessionHandler implements SessionHandlerInterface
{
    private $savePath;

    public function open($savePath, $sessionName)
    {
        $this->savePath = $savePath;
        if (!is_dir($this->savePath)) {
            mkdir($this->savePath, 0777);
        }

        return true;
    }

    public function close()
    {
        return true;
    }

    public function read($id)
    {
        return (string)@file_get_contents("$this->savePath/sess_$id");
    }

    public function write($id, $data)
    {
        return file_put_contents("$this->savePath/sess_$id", $data) === false ? false : true;
    }

    public function destroy($id)
    {
        $file = "$this->savePath/sess_$id";
        if (file_exists($file)) {
            unlink($file);
        }

        return true;
    }

    public function gc($maxlifetime)
    {
        foreach (glob("$this->savePath/sess_*") as $file) {
            if (filemtime($file) + $maxlifetime < time() && file_exists($file)) {
                unlink($file);
            }
        }

        return true;
    }
}

$handler = new MySessionHandler();
session_set_save_handler($handler, true);
session_start();

// proceed to set and retrieve values by key from $_SESSION
```

SessionHandlerInterface::close
==============================

Close the session

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">SessionHandlerInterface::close</span> ( <span
class="methodparam">void</span> )

Closes the current session. This function is automatically executed when
closing the session, or explicitly via <span
class="function">session\_write\_close</span>.

### Parameters

This function has no parameters.

### Return Values

The return value (usually **`TRUE`** on success, **`FALSE`** on
failure). Note this value is returned internally to PHP for processing.

SessionHandlerInterface::destroy
================================

Destroy a session

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">SessionHandlerInterface::destroy</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> )

Destroys a session. Called by <span
class="function">session\_regenerate\_id</span> (with $destroy =
**`TRUE`**), <span class="function">session\_destroy</span> and when
<span class="function">session\_decode</span> fails.

### Parameters

`id`  
The session ID being destroyed.

### Return Values

The return value (usually **`TRUE`** on success, **`FALSE`** on
failure). Note this value is returned internally to PHP for processing.

SessionHandlerInterface::gc
===========================

Cleanup old sessions

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">bool</span></span> <span
class="methodname">SessionHandlerInterface::gc</span> ( <span
class="methodparam"><span class="type">int</span> `$max_lifetime`</span>
)

Cleans up expired sessions. Called by <span
class="function">session\_start</span>, based on
<a href="/session/setup.html#" class="link">session.gc_divisor</a>,
<a href="/session/setup.html#" class="link">session.gc_probability</a>
and
<a href="/session/setup.html#" class="link">session.gc_maxlifetime</a>
settings.

### Parameters

`max_lifetime`  
Sessions that have not updated for the last `max_lifetime` seconds will
be removed.

### Return Values

Returns the number of deleted sessions on success, or **`FALSE`** on
failure. Note this value is returned internally to PHP for processing.

### Changelog

| Version | Description                                                         |
|---------|---------------------------------------------------------------------|
| 7.1.0   | Prior to this version, the function returned **`TRUE`** on success. |

SessionHandlerInterface::open
=============================

Initialize session

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">SessionHandlerInterface::open</span> ( <span
class="methodparam"><span class="type">string</span> `$path`</span> ,
<span class="methodparam"><span class="type">string</span>
`$name`</span> )

Re-initialize existing session, or creates a new one. Called when a
session starts or when <span class="function">session\_start</span> is
invoked.

### Parameters

`path`  
The path where to store/retrieve the session.

`name`  
The session name.

### Return Values

The return value (usually **`TRUE`** on success, **`FALSE`** on
failure). Note this value is returned internally to PHP for processing.

### See Also

-   <span class="function">session\_name</span>
-   The
    <a href="/session/setup.html#" class="link">session.auto-start</a>
    configuration directive.

SessionHandlerInterface::read
=============================

Read session data

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">SessionHandlerInterface::read</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> )

Reads the session data from the session storage, and returns the
results. Called right after the session starts or when <span
class="function">session\_start</span> is called. Please note that
before this method is called <span
class="function">SessionHandlerInterface::open</span> is invoked.

This method is called by PHP itself when the session is started. This
method should retrieve the session data from storage by the session ID
provided. The string returned by this method must be in the same
serialized format as when originally passed to the <span
class="function">SessionHandlerInterface::write</span> If the record was
not found, return an empty string.

The data returned by this method will be decoded internally by PHP using
the unserialization method specified in
<a href="/session/setup.html#" class="link">session.serialize_handler</a>.
The resulting data will be used to populate the `$_SESSION` superglobal.

Note that the serialization scheme is not the same as <span
class="function">unserialize</span> and can be accessed by <span
class="function">session\_decode</span>.

### Parameters

`id`  
The session id.

### Return Values

Returns an encoded string of the read data. If nothing was read, it must
return an empty string. Note this value is returned internally to PHP
for processing.

### See Also

-   The
    <a href="/session/setup.html#" class="link">session.serialize_handler</a>
    configuration directive.

SessionHandlerInterface::write
==============================

Write session data

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">SessionHandlerInterface::write</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> )

Writes the session data to the session storage. Called by <span
class="function">session\_write\_close</span>, when <span
class="function">session\_register\_shutdown</span> fails, or during a
normal shutdown. Note: <span
class="function">SessionHandlerInterface::close</span> is called
immediately after this function.

PHP will call this method when the session is ready to be saved and
closed. It encodes the session data from the `$_SESSION` superglobal to
a serialized string and passes this along with the session ID to this
method for storage. The serialization method used is specified in the
<a href="/session/setup.html#" class="link">session.serialize_handler</a>
setting.

Note this method is normally called by PHP after the output buffers have
been closed unless explicitly called by <span
class="function">session\_write\_close</span>

### Parameters

`id`  
The session id.

`data`  
The encoded session data. This data is the result of the PHP internally
encoding the `$_SESSION` superglobal to a serialized string and passing
it as this parameter. Please note sessions use an alternative
serialization method.

### Return Values

The return value (usually **`TRUE`** on success, **`FALSE`** on
failure). Note this value is returned internally to PHP for processing.

### See Also

-   The
    <a href="/session/setup.html#" class="link">session.serialize_handler</a>
    configuration directive.

Introduction
------------

<span class="classname">SessionIdInterface</span> is an interface which
defines optional methods for creating a custom session handler. In order
to pass a custom session handler to <span
class="function">session\_set\_save\_handler</span> using its OOP
invocation, the class can implement this interface.

Note that the callback methods of classes implementing this interface
are designed to be called internally by PHP and are not meant to be
called from user-space code.

Class synopsis
--------------

**SessionIdInterface**

<span class="ooclass"> class **SessionIdInterface** </span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">create\_sid</span> ( <span
class="methodparam">void</span> )

}

SessionIdInterface::create\_sid
===============================

Create session ID

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">string</span> <span
class="methodname">SessionIdInterface::create\_sid</span> ( <span
class="methodparam">void</span> )

Creates a new session ID.This function is automatically executed when a
new session ID needs to be created.

### Parameters

This function has no parameters.

### Return Values

The new session ID. Note that this value is returned internally to PHP
for processing.

### See Also

-   <span class="methodname">SessionHandler::create\_sid</span>

Introduction
------------

<span class="classname">SessionUpdateTimestampHandlerInterface</span> is
an interface which defines optional methods for creating a custom
session handler. In order to pass a custom session handler to <span
class="function">session\_set\_save\_handler</span> using its OOP
invocation, the class can implement this interface.

Note that the callback methods of classes implementing this interface
are designed to be called internally by PHP and are not meant to be
called from user-space code.

Class synopsis
--------------

**SessionUpdateTimestampHandlerInterface**

<span class="ooclass"> class **SessionUpdateTimestampHandlerInterface**
</span> {

/\* Methods \*/

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">updateTimestamp</span> ( <span
class="methodparam"><span class="type">string</span> `$id`</span> ,
<span class="methodparam"><span class="type">string</span>
`$data`</span> )

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">validateId</span> ( <span class="methodparam"><span
class="type">string</span> `$id`</span> )

}

SessionUpdateTimestampHandlerInterface::updateTimestamp
=======================================================

Update timestamp

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">SessionUpdateTimestampHandlerInterface::updateTimestamp</span>
( <span class="methodparam"><span class="type">string</span>
`$id`</span> , <span class="methodparam"><span
class="type">string</span> `$data`</span> )

Updates the last modification timestamp of the session. This function is
automatically executed when a session is updated.

### Parameters

`id`  
The session ID.

`data`  
The session data.

### Return Values

Returns **`TRUE`** if the timestamp was updated, **`FALSE`** otherwise.
Note that this value is returned internally to PHP for processing.

SessionUpdateTimestampHandlerInterface::validateId
==================================================

Validate ID

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">SessionUpdateTimestampHandlerInterface::validateId</span>
( <span class="methodparam"><span class="type">string</span>
`$id`</span> )

Validates a given session ID. A session ID is valid, if a session with
that ID already exists. This function is automatically executed when a
session is to be started, a session ID is supplied and
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
is enabled.

### Parameters

`id`  
The session ID.

### Return Values

Returns **`TRUE`** for valid ID, **`FALSE`** otherwise. Note that this
value is returned internally to PHP for processing.

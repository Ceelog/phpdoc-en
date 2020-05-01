Sessions and Security
=====================

**Table of Contents**

-   [Session Management
    Basics](/session/security.html#Session%20Management%20Basics)
-   [Securing Session INI
    Settings](/session/security.html#Securing%20Session%20INI%20Settings)

External links:
<a href="http://www.acros.si/papers/session_fixation.pdf" class="link external">» Session fixation</a>

HTTP session management represents the core of web security. All
possible mitigation measures SHOULD be adopted to ensure sessions are
secured. Developers should also enable/use applicable security measures.

Session Management Basics
-------------------------

### Session Security

The session module can not guarantee that the information stored in a
session is only viewed by the user who created the session. Additional
measures are needed to protect the confidentiality of the session,
depending on the value associated with it.

The importance of the data carried in the session needs to be assessed
and further protection may be deployed; this typically comes at a price,
such as reduced convenience for the user. For example, to protect users
from a simple social engineering tactic, *session.use\_only\_cookies*
needs to be enabled. In that case, cookies must be enabled
unconditionally on the client side, or sessions will not work.

There are several ways to leak an existing session ID to third parties.
E.g. JavaScript injections, session IDs in URLs, packet sniffing,
physical access to the device, etc. A leaked session ID enables the
third party to access all resources associated with a specific ID.
First, URLs carrying session IDs. If there are links to an external site
or resource, the URL including the session ID might be stored in the
external site's referrer logs. Second, a more active attacker might
listen to network traffic. If it is unencrypted, session IDs will flow
in plain text over the network. The solution is to implement SSL/TLS on
the server and make it mandatory for users. HSTS should be used for
improved security.

> **Note**: <span class="simpara"> Even HTTPS can not protect
> confidential data at all times. For example the CRIME and Beast
> vulnerabilities may enable an attacker to read the data. Also, note
> that many networks employ HTTPS MITM proxies for audit purposes.
> Attackers may also set up such a proxy. </span>

### Nonadaptive Session Management

PHP's session manager is adaptive by default currently. An adaptive
session manager bears additional risks.

As of PHP 5.5.2,
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
is available. When it is enabled, and the session save handler supports
it, an uninitialized session ID is rejected and a new one is created.
This prevents an attack that forces users to use a known session ID. An
attacker may paste links or send emails that contains the session ID.
E.g. *http://example.com/page.php?PHPSESSID=123456789* if
<a href="/session/setup.html#" class="link">session.use_trans_sid</a> is
enabled, the victim will start a session using the session ID provided
by the attacker.
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
mitigate this risk.

**Warning**

User defined save handlers can also support strict session mode by
implementing session ID validation. All user defined save handlers
should implement session ID validation.

The session ID cookie may be set with the domain, path, httponly, secure
and, as of PHP 7.3, SameSite attributes. There is precedence defined by
browsers. By using the precedence, an attacker can set session ID that
could be used permanently. Use of
<a href="/session/setup.html#" class="link">session.use_only_cookies</a>
will not solve this issue.
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
mitigates this risk. With
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>=On,
the uninitialized session ID will be refused.

> **Note**: <span class="simpara"> Even though
> <a href="/session/setup.html#" class="link">session.use_strict_mode</a>
> mitigates the risk of adaptive session management, an attacker can
> force users to use an initialized session ID which has been created by
> an attacker. E.g. JavaScript injection. This attack can be mitigated
> by this manual's recommendations. </span> <span class="simpara"> By
> following this manual, developers should enable,
> <a href="/session/setup.html#" class="link">session.use_strict_mode</a>,
> use timestamp based session management, and regenerate session IDs
> using <span class="function">session\_regenerate\_id</span> with
> recommended procedures. If developers follow all of the above, an
> attacker generated session ID will eventually be deleted. </span>
> <span class="simpara"> When an access to an obsolete session occurs,
> developers should save all active session data of the user. As this
> information will be relevant for an ensuing investigation. The user
> should be forcefully logged out of all sessions, i.e. require them to
> reauthenticate. This prevents attackers from abusing stolen sessions.
> </span>

**Warning**

Access to an obsolete session does not necessarily suggest an attack. An
unstable network and/or immediate deletion of the active session will
result in legitimate users using obsolete sessions.

As of PHP 7.1.0, <span class="function">session\_create\_id</span> has
been added. This function may be operated to access all active sessions
of a user efficiently by prefixing the session IDs with the user ID.
Enabling
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
is vital with this setup. Otherwise, malicious users can set malicious
session ID for other users.

> **Note**: <span class="simpara"> Users prior to PHP 7.1.0 SHOULD use
> CSPRNG, e.g. /dev/urandom, or <span
> class="function">random\_bytes</span> and hash functions to generate a
> new session ID. <span class="function">session\_create\_id</span> has
> collision detection and generates a session ID according to the
> session's INI settings. Use of <span
> class="function">session\_create\_id</span> is preferred. </span>

### Session ID Regeneration

<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
is a good mitigation, however not sufficient. Developers must equally
use <span class="function">session\_regenerate\_id</span> for session
security.

Session ID regeneration reduces the risk of stolen session IDs, thus
<span class="function">session\_regenerate\_id</span> must be called
periodically. E.g. Regenerate the session ID every 15 minutes for
security sensitive content. Even in the case that a session ID is
stolen, both the legitimate user's and the attacker's session will
expire. In other words access by the user or the attacker will generate
an obsolete session access error.

Session IDs *must* be regenerated when user privileges are elevated,
such as after authenticating. <span
class="function">session\_regenerate\_id</span> must be called prior to
setting the authentication information to $\_SESSION. (As of PHP 7.0.0,
<span class="function">session\_regenerate\_id</span> saves the current
session data automatically in order to save timestamp/etc. to the
current session.) Ensure only the new session contains the authenticated
flag.

Developers *must not* rely on session ID expiration by
<a href="/session/setup.html#" class="link">session.gc_maxlifetime</a>.
Attackers may access a victim's session ID periodically to prevent its
expiration and keep exploiting it, including an authenticated session.

Instead, developers must implement timestamp based session data
management.

**Warning**

Although the session manager can manage timestamps transparently, this
feature is not implemented. Old session data must be kept until GC.
Simultaneously, developers must assure themselves obsolete session data
is removed. However, developers must not remove active session data
immediately. I.e. *session\_regenerate\_id(true);* and <span
class="function">session\_destroy</span> must never be called together
for an active session. This may sound contradictory, but this is a
mandatory requirement.

<span class="function">session\_regenerate\_id</span> does *not* delete
outdated sessions by default. Obsolete authenticated sessions may be
present for use. Developers must prevent outdated sessions to be
consumed by anyone. They must prohibit access to obsolete session data
by themselves using timestamps.

**Warning**

The sudden removal of an active session produces undesirable side
effects. Sessions can vanish when there are concurrent connections to
the web application and/or the network is unstable.

Potential malicious access is undetectable with the sudden removal of
active sessions.

Instead of deleting outdated sessions immediately, developers must set a
short-term expiration time (timestamp) in $\_SESSION, and prohibit
access to the session data by themselves.

Developers must not prohibit access to old session data immediately
after <span class="function">session\_regenerate\_id</span>. It must be
prohibited at a later stage. E.g. a few seconds later for stable
networks, like a wired network, and a few minutes later for unstable
networks such as cell phones or Wi-Fi.

If a user accesses an obsolete session (expired session), access to it
should be denied. It is also recommended to remove the authenticated
status from all of the user's sessions to as it is likely to represent
an attack.

Proper use of
<a href="/session/setup.html#" class="link">session.use_only_cookies</a>
and <span class="function">session\_regenerate\_id</span> can cause
personal DoS with undeletable cookies set by attackers. In this case,
developers may invite users to remove cookies and advise them they may
be affected by a security issue. Attackers may set malicious cookies via
a vulnerable web application, an exposed/vicious browser plugin, a
physically compromised device, etc.

**Warning**

Do not misunderstand the DoS risk. *use\_strict\_mode=On* is mandatory
for general session ID security! All sites are advised to enable
*use\_strict\_mode*.

DoS can only happen when the account is under attack. A JavaScript
injection vulnerability in an application represents the most common
cause.

### Session Data Deletion

Obsolete session data must be inaccessible and deleted. The current
session module does not handle this well.

Obsolete session data should be removed as soon as possible. However,
active sessions must not be removed instantly. To satisfy those
requirements, developers must implement timestamp based session data
management by themselves.

Set and manage expiration timestamp in $\_SESSION. Prohibit access to
outdated session data. When access to obsolete session data is detected,
it is advised to remove all authenticated status from the user's
sessions and force them to re-authenticate. Access to obsolete session
data can represent an attack. To achieve this, developers must keep
track of all active sessions of every user.

> **Note**: <span class="simpara"> Access to an obsolete session can
> also happen because of an unstable network and/or concurrent access to
> the web site. E.g the server tried to set a new session ID via a
> cookie, but the Set-Cookie packet may not have reached the client due
> to loss of connection. One connection may issue a new session ID by
> <span class="function">session\_regenerate\_id</span>, but another
> concurrent connection may not have received the new session ID yet.
> Therefore, developers must prohibit access to obsolete session at a
> later stage. I.e. timestamp based session management is mandatory.
> </span>

In summary, session data must not be destroyed with <span
class="function">session\_regenerate\_id</span> nor <span
class="function">session\_destroy</span>, but timestamps must be used to
control access to session data. Let <span
class="function">session\_gc</span> remove obsolete data from the
session data storage.

### Session and Locking

Session data is locked to avoid race conditions by default. Locking is
mandatory to keep session data consistent across requests.

However, session-locking can be abused by attackers to perform DoS
attacks. To mitigate the risk of a DoS attack by session-locking,
minimize locks. Use read only sessions when session data does not need
to be updated. Use the 'read\_and\_close' option with <span
class="function">session\_start</span>.
*session\_start(\['read\_and\_close'=\>1\]);* Close the session as soon
as possible after updating $\_SESSION by using <span
class="function">session\_commit</span>.

The current session module does *not* detect any modification of
$\_SESSION when the session is inactive. It is the developer's
responsibility not to modify $\_SESSION when the session is inactive.

### Active Sessions

Developers should keep track of all active sessions for every user. And
notify them of how many active sessions, from which IP (and area), how
long it has been active, etc. PHP does not keep track of these.
Developers are supposed to do so.

Various ways to implement this exist. One possible implementation is
setting up a database that keeps track of the required data and stores
any relevant information. Since session data is GCed, developers must
take care of the GCed data to maintain the active session database
consistency.

One of the simplest implementations is "User ID prefixed session ID" and
store the required information in $\_SESSION. Many databases posses good
performance for selecting string prefix. Developers MAY use <span
class="function">session\_regenerate\_id</span> and <span
class="function">session\_create\_id</span> for this.

**Warning**

Never employ confidential data as a prefix. If the user ID is
confidential, consider using <span class="function">hash\_hmac</span>.

**Warning**

Enabling
<a href="/session/setup.html#" class="link">session.use_strict_mode</a>
is mandatory for this setup. Ensure it is enabled. Otherwise the active
session database can be compromised.

Timestamp based session management is mandatory to detect access to
obsolete sessions. When access to an obsolete session is detected,
authentication flags should be removed from all active sessions of the
user. This prevents attackers to keep exploiting stolen sessions.

### Session and Auto-login

Developers must not use long life session IDs for auto-login because it
increases the risk of stolen sessions. An auto-login feature should be
implemented by the developer.

Use a secure one time hash key as an auto-login key using <span
class="function">setcookie</span>. Use a secure hash stronger than
SHA-2. E.g. SHA-256 or greater with random data from <span
class="function">random\_bytes</span> or /dev/urandom.

If the user is unauthenticated, check whether the one-time auto-login
key is valid or not. In the case it is valid, authenticate the user and
set a new secure one-time hash key. An auto-login key must only be used
once, i.e. never reuse an auto-login key, always generate a new one.

An auto-login key is a long life authentication key, it should be
protected as much as possible. Use path/httponly/secure/SameSite cookie
attributes to secure it. I.e. never transmit the auto-login key unless
required.

Developer must implement the features that disables auto-login and
removes unneeded auto-login key cookie.

### CSRF (Cross-Site Request Forgeries) attacks

Sessions and authentication do not protect against CSRF attacks.
Developers must implement CSRF protection by themselves.

<span class="function">output\_add\_rewrite\_var</span> can be used for
CSRF protection. Refer to the manual page for more details.

> **Note**: <span class="simpara"> PHP prior to 7.2.0 uses the same
> output buffer and INI setting as trans sid. Therefore, use of <span
> class="function">output\_add\_rewrite\_var</span> with PHP prior to
> version 7.2.0 is not advised. </span>

Most web application frameworks support CSRF protection. Refer to the
web application framework manual for more details.

As of PHP 7.3 the SameSite attribute for the session cookie can be set.
This is an additional measure which can mitigate CSRF vulnerabilities.

Securing Session INI Settings
-----------------------------

By securing session related INI settings, developers can improve session
security. Some important INI settings do not have any recommended
settings. Developers are responsible for hardening session settings.

-   <a href="/session/setup.html#" class="link">session.cookie_lifetime</a>=0

    *0* possesses a particular meaning. It informs browsers not to store
    the cookie to permanent storage. Therefore, when the browser is
    terminated, the session ID cookie is deleted immediately. If
    developers set this other than 0, it may allow other users to use
    the session ID. Most applications should use "*0*" for this.

    If an auto-login feature is required, developers must implement
    their own secure auto-login feature. Do not use long life session
    IDs for this. More information can be found above in the relevant
    section.

-   <a href="/session/setup.html#" class="link">session.use_cookies</a>=On

    <a href="/session/setup.html#" class="link">session.use_only_cookies</a>=On

    Although HTTP cookies suffer some problems, cookies remain the
    preferred way to manage session IDs. Only use cookies for session ID
    management when it is possible. Most applications should use a
    cookie for the session ID.

    If *session.use\_only\_cookies*=Off, the session module will use the
    session ID values set by GET/POST/URL provided the session ID cookie
    is uninitialized.

-   <a href="/session/setup.html#" class="link">session.use_strict_mode</a>=On

    Although, enabling *session.use\_strict\_mode* is mandatory for
    secure sessions. It is disabled by default.

    This prevents the session module to use an uninitialized session ID.
    Put differently, the session module only accepts valid session IDs
    generated by the session module. It rejects any session ID supplied
    by users.

    Due to the cookie specification, attackers are capable to place non
    removable session ID cookies by locally setting a cookie database or
    JavaScript injections. *session.use\_strict\_mode* can prevent an
    attacker initialized session ID of being used.

    > **Note**:
    >
    > Attackers may initialize a session ID with their device and may
    > set the session ID of the victim. They must keep the session ID
    > active to abuse. Attackers require additional steps to perform an
    > attack in this scenario. Therefore, *session.use\_strict\_mode*
    > works as a mitigation.

-   <a href="/session/setup.html#" class="link">session.cookie_httponly</a>=On

    Refuses access to the session cookie from JavaScript. This setting
    prevents cookies snatched by a JavaScript injection.

    It is possible to use a session ID as a CSRF token, but this is not
    recommended. For example, HTML sources may be saved and sent to
    other users. Developers should not write session IDs in web pages
    for better security. Almost all applications must use the httponly
    attribute for the session ID cookie.

    > **Note**:
    >
    > The CSRF token should be renewed periodically just like the
    > session ID.

-   <a href="/session/setup.html#" class="link">session.cookie_secure</a>=On

    Allow access to the session ID cookie only when the protocol is
    HTTPS. If a website is only accessible via HTTPS, it should enable
    this setting.

    HSTS should be considered for websites accessible only via HTTPS.

-   <a href="/session/setup.html#" class="link">session.cookie_samesite</a>="Lax"
    or
    <a href="/session/setup.html#" class="link">session.cookie_samesite</a>="Strict"

    As of PHP 7.3 the *"SameSite"* attribute can be set for the session
    ID cookie. This attribute is a way to mitigate CSRF (Cross Site
    Request Forgery) attacks.

    The difference between Lax and Strict is the accessibility of the
    cookie in requests originating from another registrable domain
    employing the HTTP GET method. Cookies using Lax will be accessible
    in a GET request originated from another registrable domain, whereas
    cookies using Strict will not.

-   <a href="/session/setup.html#" class="link">session.gc_maxlifetime</a>=\[choose
    smallest possible\]

    *session.gc\_maxlifetime* is a setting for deleting obsolete session
    ID. Reliance on this setting is *not* recommended. Developers should
    manage the lifetime of sessions with a timestamp by themselves.

    Session GC (garbage collection) is best performed by using <span
    class="function">session\_gc</span>. The <span
    class="function">session\_gc</span> function should be executed by a
    task managers. E.g. cron on UNIX like systems.

    GC is performed by probability by default. This setting does *not*
    guarantee that an outdated session is deleted. Although developers
    cannot rely on this setting, specifying it to the smallest possible
    value is recommended. Adjusting
    <a href="/session/setup.html#" class="link">session.gc_probability</a>
    and
    <a href="/session/setup.html#" class="link">session.gc_divisor</a>
    so that obsolete sessions are deleted at an appropriate frequency.
    If an auto-login feature is required, developers must implement
    their own secure auto-login feature, see above for more information.
    Never use long life session ID for this feature.

    > **Note**:
    >
    > Some session save handler modules do not use this setting for
    > probability based expiration. E.g. memcached, memcache. Refer to
    > the session save handler documentation for details.

-   <a href="/session/setup.html#" class="link">session.use_trans_sid</a>=Off

    Use of a transparent session ID management is not prohibited.
    Developers may employ it when it is required. However, disabling
    transparent session ID management improves the general session ID
    security by eliminating the possibility of a session ID injection
    and/or leak.

    > **Note**:
    >
    > Session ID may leak from bookmarked URLs, e-mailed URLs, saved
    > HTML source, etc.

-   <a href="/session/setup.html#" class="link">session.trans_sid_tags</a>=\[limited
    tags\]

    (PHP 7.1.0 \>=) Developers should not rewrite unneeded HTML tags.
    Default value should be sufficient for most usages. Older PHP
    versions use
    <a href="/outcontrol/setup.html#" class="link">url_rewriter.tags</a>
    instead.

-   <a href="/session/setup.html#" class="link">session.trans_sid_hosts</a>=\[limited
    hosts\]

    (PHP 7.1.0 \>=) This INI defines whitelist hosts that allows trans
    sid rewrite. Never add untrusted hosts. Session module only allows
    *$\_SERVER\['HTTP\_HOST'\]* when this setting is empty.

-   <a href="/session/setup.html#" class="link">session.referer_check</a>=\[originating
    URL\]

    When
    <a href="/session/setup.html#" class="link">session.use_trans_sid</a>
    is enabled. It reduces the risk of session ID injection. If a
    website is http://example.com/, set http://example.com/ to it. Note
    that with HTTPS browsers will not send the referrer header. Browsers
    may not send the referrer header by configuration. Therefore, this
    setting is not a reliable security measure. Use of this setting is
    recommended.

-   <a href="/session/setup.html#" class="link">session.cache_limiter</a>=nocache

    Ensure HTTP content are uncached for authenticated sessions. Allow
    caching only when the content is not private. Otherwise, content may
    be exposed. "private" may be employed if HTTP content does not
    include security sensitive data. Note that "private" may transmit
    private data cached by shared clients. "public" must only be used
    when HTTP content does not contain any private data at all.

-   <a href="/session/setup.html#" class="link">session.sid_length</a>="48"

    (PHP 7.1.0 \>=) Longer session IDs results in stronger session IDs.
    Developers should consider a session ID length of 32 characters or
    more. At least 26 characters are required when
    <a href="/session/setup.html#" class="link">session.sid_bits_per_character</a>="5".

-   <a href="/session/setup.html#" class="link">session.sid_bits_per_character</a>="6"

    (PHP 7.1.0 \>=) The more bits there are in a session ID character,
    the stronger the session ID generated by the session module is for
    an identical session ID length.

-   <a href="/session/setup.html#" class="link">session.hash_function</a>="sha256"

    (PHP 7.1.0 \<) A stronger hash function will generate a stronger
    session ID. Although hash collision is unlikely even with the MD5
    hashing algorithm, developers should use SHA-2 or a stronger hashing
    algorithm like sha384 and sha512. Developers must ensure they feed a
    long enough <a href="/session/setup.html#" class="link">entropy</a>
    for the hashing function used.

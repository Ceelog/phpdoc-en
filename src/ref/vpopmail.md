vpopmail\_add\_alias\_domain\_ex
================================

Add alias to an existing virtual domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_add\_alias\_domain\_ex</span> ( <span
class="methodparam"><span class="type">string</span> `$olddomain`</span>
, <span class="methodparam"><span class="type">string</span>
`$newdomain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_add\_alias\_domain
============================

Add an alias for a virtual domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_add\_alias\_domain</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> ,
<span class="methodparam"><span class="type">string</span>
`$aliasdomain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_add\_domain\_ex
=========================

Add a new virtual domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_add\_domain\_ex</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> ,
<span class="methodparam"><span class="type">string</span>
`$passwd`</span> \[, <span class="methodparam"><span
class="type">string</span> `$quota`</span> \[, <span
class="methodparam"><span class="type">string</span> `$bounce`</span>
\[, <span class="methodparam"><span class="type">bool</span>
`$apop`</span> \]\]\] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_add\_domain
=====================

Add a new virtual domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_add\_domain</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> ,
<span class="methodparam"><span class="type">string</span> `$dir`</span>
, <span class="methodparam"><span class="type">int</span> `$uid`</span>
, <span class="methodparam"><span class="type">int</span> `$gid`</span>
)

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_add\_user
===================

Add a new user to the specified virtual domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_add\_user</span> ( <span
class="methodparam"><span class="type">string</span> `$user`</span> ,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$password`</span> \[, <span
class="methodparam"><span class="type">string</span> `$gecos`</span> \[,
<span class="methodparam"><span class="type">bool</span> `$apop`</span>
\]\] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_alias\_add
====================

Insert a virtual alias

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_alias\_add</span> ( <span
class="methodparam"><span class="type">string</span> `$user`</span> ,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$alias`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_alias\_del\_domain
============================

Deletes all virtual aliases of a domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_alias\_del\_domain</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_alias\_del
====================

Deletes all virtual aliases of a user

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_alias\_del</span> ( <span
class="methodparam"><span class="type">string</span> `$user`</span> ,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_alias\_get\_all
=========================

Get all lines of an alias for a domain

### Description

<span class="type">array</span> <span
class="methodname">vpopmail\_alias\_get\_all</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_alias\_get
====================

Get all lines of an alias for a domain

### Description

<span class="type">array</span> <span
class="methodname">vpopmail\_alias\_get</span> ( <span
class="methodparam"><span class="type">string</span> `$alias`</span> ,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_auth\_user
====================

Attempt to validate a username/domain/password

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_auth\_user</span> ( <span
class="methodparam"><span class="type">string</span> `$user`</span> ,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$password`</span> \[, <span
class="methodparam"><span class="type">string</span> `$apop`</span> \] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_del\_domain\_ex
=========================

Delete a virtual domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_del\_domain\_ex</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_del\_domain
=====================

Delete a virtual domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_del\_domain</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_del\_user
===================

Delete a user from a virtual domain

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_del\_user</span> ( <span
class="methodparam"><span class="type">string</span> `$user`</span> ,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_error
===============

Get text message for last vpopmail error

### Description

<span class="type">string</span> <span
class="methodname">vpopmail\_error</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_passwd
================

Change a virtual user's password

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_passwd</span> ( <span
class="methodparam"><span class="type">string</span> `$user`</span> ,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$password`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$apop`</span> \] )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

vpopmail\_set\_user\_quota
==========================

Sets a virtual user's quota

### Description

<span class="type">bool</span> <span
class="methodname">vpopmail\_set\_user\_quota</span> ( <span
class="methodparam"><span class="type">string</span> `$user`</span> ,
<span class="methodparam"><span class="type">string</span>
`$domain`</span> , <span class="methodparam"><span
class="type">string</span> `$quota`</span> )

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

**Warning**

This function is currently not documented; only its argument list is
available.

**Table of Contents**

-   [vpopmail\_add\_alias\_domain\_ex](/ref/vpopmail.html#vpopmail_add_alias_domain_ex)
    — Add alias to an existing virtual domain
-   [vpopmail\_add\_alias\_domain](/ref/vpopmail.html#vpopmail_add_alias_domain)
    — Add an alias for a virtual domain
-   [vpopmail\_add\_domain\_ex](/ref/vpopmail.html#vpopmail_add_domain_ex)
    — Add a new virtual domain
-   [vpopmail\_add\_domain](/ref/vpopmail.html#vpopmail_add_domain) —
    Add a new virtual domain
-   [vpopmail\_add\_user](/ref/vpopmail.html#vpopmail_add_user) — Add a
    new user to the specified virtual domain
-   [vpopmail\_alias\_add](/ref/vpopmail.html#vpopmail_alias_add) —
    Insert a virtual alias
-   [vpopmail\_alias\_del\_domain](/ref/vpopmail.html#vpopmail_alias_del_domain)
    — Deletes all virtual aliases of a domain
-   [vpopmail\_alias\_del](/ref/vpopmail.html#vpopmail_alias_del) —
    Deletes all virtual aliases of a user
-   [vpopmail\_alias\_get\_all](/ref/vpopmail.html#vpopmail_alias_get_all)
    — Get all lines of an alias for a domain
-   [vpopmail\_alias\_get](/ref/vpopmail.html#vpopmail_alias_get) — Get
    all lines of an alias for a domain
-   [vpopmail\_auth\_user](/ref/vpopmail.html#vpopmail_auth_user) —
    Attempt to validate a username/domain/password
-   [vpopmail\_del\_domain\_ex](/ref/vpopmail.html#vpopmail_del_domain_ex)
    — Delete a virtual domain
-   [vpopmail\_del\_domain](/ref/vpopmail.html#vpopmail_del_domain) —
    Delete a virtual domain
-   [vpopmail\_del\_user](/ref/vpopmail.html#vpopmail_del_user) — Delete
    a user from a virtual domain
-   [vpopmail\_error](/ref/vpopmail.html#vpopmail_error) — Get text
    message for last vpopmail error
-   [vpopmail\_passwd](/ref/vpopmail.html#vpopmail_passwd) — Change a
    virtual user's password
-   [vpopmail\_set\_user\_quota](/ref/vpopmail.html#vpopmail_set_user_quota)
    — Sets a virtual user's quota

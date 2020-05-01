I have at the moment not very much time to further develop this
extension. I will implement more and more features in the near future.

If you have comments, bug fixes, enhancements or want to help developing
this, you can drop me a mail at
<a href="mailto:yohgaki@php.net" class="link external">» yohgaki@php.net</a>.
Any help is very welcome.

session\_pgsql\_add\_error
==========================

Increments error counts and sets last error message

### Description

<span class="type">bool</span> <span
class="methodname">session\_pgsql\_add\_error</span> ( <span
class="methodparam"><span class="type">int</span> `$error_level`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$error_message`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`error_level`  

`error_message`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">session\_pgsql\_get\_error</span>

session\_pgsql\_get\_error
==========================

Returns number of errors and last error message

### Description

<span class="type">array</span> <span
class="methodname">session\_pgsql\_get\_error</span> (\[ <span
class="methodparam"><span class="type">bool</span>
`$with_error_message`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Get the number of errors and optional the error messages.

### Parameters

`with_error_message`  
Set to **`TRUE`** the literal error message for each error is also
returned.

### Return Values

The number of errors are returned as <span class="type">array</span>.

### See Also

-   <span class="function">session\_pgsql\_add\_error</span>

session\_pgsql\_get\_field
==========================

Get custom field value

### Description

<span class="type">string</span> <span
class="methodname">session\_pgsql\_get\_field</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### See Also

-   <span class="function">session\_pgsql\_set\_field</span>

session\_pgsql\_reset
=====================

Reset connection to session database servers

### Description

<span class="type">bool</span> <span
class="methodname">session\_pgsql\_reset</span> ( <span
class="methodparam">void</span> )

Reset the connection to the session database servers.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

session\_pgsql\_set\_field
==========================

Set custom field value

### Description

<span class="type">bool</span> <span
class="methodname">session\_pgsql\_set\_field</span> ( <span
class="methodparam"><span class="type">string</span> `$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`value`  

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">session\_pgsql\_get\_field</span>

session\_pgsql\_status
======================

Get current save handler status

### Description

<span class="type">array</span> <span
class="methodname">session\_pgsql\_status</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

**Table of Contents**

-   [session\_pgsql\_add\_error](/ref/session-pgsql.html#session_pgsql_add_error)
    — Increments error counts and sets last error message
-   [session\_pgsql\_get\_error](/ref/session-pgsql.html#session_pgsql_get_error)
    — Returns number of errors and last error message
-   [session\_pgsql\_get\_field](/ref/session-pgsql.html#session_pgsql_get_field)
    — Get custom field value
-   [session\_pgsql\_reset](/ref/session-pgsql.html#session_pgsql_reset)
    — Reset connection to session database servers
-   [session\_pgsql\_set\_field](/ref/session-pgsql.html#session_pgsql_set_field)
    — Set custom field value
-   [session\_pgsql\_status](/ref/session-pgsql.html#session_pgsql_status)
    — Get current save handler status

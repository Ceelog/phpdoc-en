crack\_check
============

Performs an obscure check with the given password

### Description

<span class="type">bool</span> <span
class="methodname">crack\_check</span> ( <span class="methodparam"><span
class="type">resource</span> `$dictionary`</span> , <span
class="methodparam"><span class="type">string</span> `$password`</span>
)

<span class="type">bool</span> <span
class="methodname">crack\_check</span> ( <span class="methodparam"><span
class="type">string</span> `$password`</span> , <span
class="methodparam"><span class="type">string</span> `$username`<span
class="initializer"> = ""</span></span> , <span
class="methodparam"><span class="type">string</span> `$gecos`<span
class="initializer"> = ""</span></span> , <span
class="methodparam"><span class="type">resource</span>
`$dictionary`<span class="initializer"> = **`NULL`**</span></span> )

Performs an obscure check with the given password on the specified
dictionary. The alternative signature also takes into account the
username and the GECOS information.

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`dictionary`  
The crack lib dictionary. If not specified, the last opened dictionary
is used.

`password`  
The password to be checked.

`username`  
The username of the account with the password.

`gecos`  
The GECOS information associated with the user account.

### Return Values

Returns **`TRUE`** if `password` is strong, or **`FALSE`** otherwise.

### Changelog

| Version | Description                                                                                  |
|---------|----------------------------------------------------------------------------------------------|
| 0.3     | The `username`, `gecos` and `dictionary` parameters were added to the alternative signature. |

crack\_closedict
================

Closes an open CrackLib dictionary

### Description

<span class="type">bool</span> <span
class="methodname">crack\_closedict</span> (\[ <span
class="methodparam"><span class="type">resource</span>
`$dictionary`</span> \] )

<span class="function">crack\_closedict</span> closes the specified
`dictionary` identifier.

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Parameters

`dictionary`  
The dictionary to close. If not specified, the current dictionary is
closed.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">crack\_opendict</span>

crack\_getlastmessage
=====================

Returns the message from the last obscure check

### Description

<span class="type">string</span> <span
class="methodname">crack\_getlastmessage</span> ( <span
class="methodparam">void</span> )

<span class="function">crack\_getlastmessage</span> returns the message
from the last obscure check.

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

### Return Values

The message from the last obscure check or **`FALSE`** if there was no
obscure checks made so far.

The returned message is one of:

-   <span class="simpara"> *it's WAY too short* </span>
-   <span class="simpara"> *it is too short* </span>
-   <span class="simpara"> *it does not contain enough DIFFERENT
    characters* </span>
-   <span class="simpara"> *it is all whitespace* </span>
-   <span class="simpara"> *it is too simplistic/systematic* </span>
-   <span class="simpara"> *it looks like a National Insurance number.*
    </span>
-   <span class="simpara"> *it is based on a dictionary word* </span>
-   <span class="simpara"> *it is based on a (reversed) dictionary word*
    </span>
-   <span class="simpara"> *strong password* </span>

### See Also

-   <span class="function">crack\_check</span>

crack\_opendict
===============

Opens a new CrackLib dictionary

### Description

<span class="type">resource</span> <span
class="methodname">crack\_opendict</span> ( <span
class="methodparam"><span class="type">string</span>
`$dictionary`</span> )

<span class="function">crack\_opendict</span> opens the specified
CrackLib `dictionary` for use with <span
class="function">crack\_check</span>.

**Warning**

This function is *EXPERIMENTAL*. The behaviour of this function, its
name, and surrounding documentation may change without notice in a
future release of PHP. This function should be used at your own risk.

> **Note**:
>
> Only one dictionary may be open at a time.

### Parameters

`dictionary`  
The path to the Cracklib dictionary.

### Return Values

Returns a dictionary resource identifier on success or **`FALSE`** on
failure.

### See Also

-   <span class="function">crack\_check</span>
-   <span class="function">crack\_closedict</span>

**Table of Contents**

-   [crack\_check](/ref/crack.html#crack_check) — Performs an obscure
    check with the given password
-   [crack\_closedict](/ref/crack.html#crack_closedict) — Closes an open
    CrackLib dictionary
-   [crack\_getlastmessage](/ref/crack.html#crack_getlastmessage) —
    Returns the message from the last obscure check
-   [crack\_opendict](/ref/crack.html#crack_opendict) — Opens a new
    CrackLib dictionary

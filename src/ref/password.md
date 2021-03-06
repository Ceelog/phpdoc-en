password\_algos
===============

Get available password hashing algorithm IDs

### Description

<span class="type">array</span> <span
class="methodname">password\_algos</span> ( <span
class="methodparam">void</span> )

Returns a complete list of all registered password hashing algorithm IDs
as an <span class="type">array</span> of <span
class="type">string</span>s.

### Parameters

This function has no parameters.

### Return Values

Returns the available password hashing algorithm IDs.

### Examples

**Example \#1 Basic <span class="function">password</span> usage**

``` php
<?php
print_r(password_algos());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => 2y
        [1] => argon2i
        [2] => argon2id
    )

password\_get\_info
===================

Returns information about the given hash

### Description

<span class="type">array</span> <span
class="methodname">password\_get\_info</span> ( <span
class="methodparam"><span class="type">string</span> `$hash`</span> )

When passed in a valid hash created by an algorithm supported by <span
class="function">password\_hash</span>, this function will return an
array of information about that hash.

### Parameters

`hash`  
A hash created by <span class="function">password\_hash</span>.

### Return Values

Returns an associative array with three elements:

-   <span class="simpara"> *algo*, which will match a
    <a href="/password/constants.html" class="link">password algorithm constant</a>
    </span>
-   <span class="simpara"> *algoName*, which has the human readable name
    of the algorithm </span>
-   <span class="simpara"> *options*, which includes the options
    provided when calling <span class="function">password\_hash</span>
    </span>

password\_hash
==============

Creates a password hash

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">password\_hash</span> ( <span
class="methodparam"><span class="type">string</span> `$password`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$algo`</span> \[, <span class="methodparam"><span
class="type">array</span> `$options`</span> \] )

<span class="function">password\_hash</span> creates a new password hash
using a strong one-way hashing algorithm. <span
class="function">password\_hash</span> is compatible with <span
class="function">crypt</span>. Therefore, password hashes created by
<span class="function">crypt</span> can be used with <span
class="function">password\_hash</span>.

The following algorithms are currently supported:

-   <span class="simpara"> **`PASSWORD_DEFAULT`** - Use the bcrypt
    algorithm (default as of PHP 5.5.0). Note that this constant is
    designed to change over time as new and stronger algorithms are
    added to PHP. For that reason, the length of the result from using
    this identifier can change over time. Therefore, it is recommended
    to store the result in a database column that can expand beyond 60
    characters (255 characters would be a good choice). </span>
-   <span class="simpara"> **`PASSWORD_BCRYPT`** - Use the
    **`CRYPT_BLOWFISH`** algorithm to create the hash. This will produce
    a standard <span class="function">crypt</span> compatible hash using
    the "$2y$" identifier. The result will always be a 60 character
    string, or **`false`** on failure. </span>
-   <span class="simpara"> **`PASSWORD_ARGON2I`** - Use the Argon2i
    hashing algorithm to create the hash. This algorithm is only
    available if PHP has been compiled with Argon2 support. </span>
-   <span class="simpara"> **`PASSWORD_ARGON2ID`** - Use the Argon2id
    hashing algorithm to create the hash. This algorithm is only
    available if PHP has been compiled with Argon2 support. </span>

Supported options for **`PASSWORD_BCRYPT`**:

-   *salt* (<span class="type">string</span>) - to manually provide a
    salt to use when hashing the password. Note that this will override
    and prevent a salt from being automatically generated.

    If omitted, a random salt will be generated by <span
    class="function">password\_hash</span> for each password hashed.
    This is the intended mode of operation.

    **Warning**
    The salt option has been deprecated as of PHP 7.0.0. It is now
    preferred to simply use the salt that is generated by default.

-   *cost* (<span class="type">int</span>) - which denotes the
    algorithmic cost that should be used. Examples of these values can
    be found on the <span class="function">crypt</span> page.

    If omitted, a default value of *10* will be used. This is a good
    baseline cost, but you may want to consider increasing it depending
    on your hardware.

Supported options for **`PASSWORD_ARGON2I`** and
**`PASSWORD_ARGON2ID`**:

-   *memory\_cost* (<span class="type">int</span>) - Maximum memory (in
    kibibytes) that may be used to compute the Argon2 hash. Defaults to
    **`PASSWORD_ARGON2_DEFAULT_MEMORY_COST`**.

-   *time\_cost* (<span class="type">int</span>) - Maximum amount of
    time it may take to compute the Argon2 hash. Defaults to
    **`PASSWORD_ARGON2_DEFAULT_TIME_COST`**.

-   *threads* (<span class="type">int</span>) - Number of threads to use
    for computing the Argon2 hash. Defaults to
    **`PASSWORD_ARGON2_DEFAULT_THREADS`**.

### Parameters

`password`  
The user's password.

**Caution**
Using the **`PASSWORD_BCRYPT`** as the algorithm, will result in the
`password` parameter being truncated to a maximum length of 72
characters.

`algo`  
A
<a href="/password/constants.html" class="link">password algorithm constant</a>
denoting the algorithm to use when hashing the password.

`options`  
An associative array containing options. See the
<a href="/password/constants.html" class="link">password algorithm constants</a>
for documentation on the supported options for each algorithm.

If omitted, a random salt will be created and the default cost will be
used.

### Return Values

Returns the hashed password, or **`false`** on failure.

The used algorithm, cost and salt are returned as part of the hash.
Therefore, all information that's needed to verify the hash is included
in it. This allows the <span class="function">password\_verify</span>
function to verify the hash without needing separate storage for the
salt or algorithm information.

### Changelog

| Version | Description                                                                                                                                       |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | The `algo` parameter expects a <span class="type">string</span> now, but still accepts <span class="type">int</span>s for backward compatibility. |
| 7.3.0   | Support for Argon2id passwords using **`PASSWORD_ARGON2ID`** was added.                                                                           |
| 7.2.0   | Support for Argon2i passwords using **`PASSWORD_ARGON2I`** was added.                                                                             |

### Examples

**Example \#1 <span class="function">password\_hash</span> example**

``` php
<?php
/**
 * We just want to hash our password using the current DEFAULT algorithm.
 * This is presently BCRYPT, and will produce a 60 character result.
 *
 * Beware that DEFAULT may change over time, so you would want to prepare
 * By allowing your storage to expand past 60 characters (255 would be good)
 */
echo password_hash("rasmuslerdorf", PASSWORD_DEFAULT);
?>
```

The above example will output something similar to:

    $2y$10$.vGA1O9wmRjrwAVXD98HNOgsNpDczlqm3Jq7KnEd1rVAGv3Fykk1a

**Example \#2 <span class="function">password\_hash</span> example
setting cost manually**

``` php
<?php
/**
 * In this case, we want to increase the default cost for BCRYPT to 12.
 * Note that we also switched to BCRYPT, which will always be 60 characters.
 */
$options = [
    'cost' => 12,
];
echo password_hash("rasmuslerdorf", PASSWORD_BCRYPT, $options);
?>
```

The above example will output something similar to:

    $2y$12$QjSH496pcT5CEbzjD/vtVeH03tfHKFy36d4J0Ltp3lRtee9HDxY3K

**Example \#3 <span class="function">password\_hash</span> example
finding a good cost**

``` php
<?php
/**
 * This code will benchmark your server to determine how high of a cost you can
 * afford. You want to set the highest cost that you can without slowing down
 * you server too much. 8-10 is a good baseline, and more is good if your servers
 * are fast enough. The code below aims for ≤ 50 milliseconds stretching time,
 * which is a good baseline for systems handling interactive logins.
 */
$timeTarget = 0.05; // 50 milliseconds 

$cost = 8;
do {
    $cost++;
    $start = microtime(true);
    password_hash("test", PASSWORD_BCRYPT, ["cost" => $cost]);
    $end = microtime(true);
} while (($end - $start) < $timeTarget);

echo "Appropriate Cost Found: " . $cost;
?>
```

The above example will output something similar to:

    Appropriate Cost Found: 10

**Example \#4 <span class="function">password\_hash</span> example using
Argon2i**

``` php
<?php
echo 'Argon2i hash: ' . password_hash('rasmuslerdorf', PASSWORD_ARGON2I);
?>
```

The above example will output something similar to:

    Argon2i hash: $argon2i$v=19$m=1024,t=2,p=2$YzJBSzV4TUhkMzc3d3laeg$zqU/1IN0/AogfP4cmSJI1vc8lpXRW9/S0sYY2i2jHT0

### Notes

**Caution**

It is strongly recommended that you do not generate your own salt for
this function. It will create a secure salt automatically for you if you
do not specify one.

As noted above, providing the *salt* option in PHP 7.0 will generate a
deprecation warning. Support for providing a salt manually may be
removed in a future PHP release.

> **Note**:
>
> It is recommended that you test this function on your servers, and
> adjust the cost parameter so that execution of the function takes less
> than 100 milliseconds on interactive systems. The script in the above
> example will help you choose a good cost value for your hardware.

> **Note**: <span class="simpara"> Updates to supported algorithms by
> this function (or changes to the default one) must follow the
> following rules: </span>
>
> -   <span class="simpara"> Any new algorithm must be in core for at
>     least 1 full release of PHP prior to becoming default. So if, for
>     example, a new algorithm is added in 7.5.5, it would not be
>     eligible for default until 7.7 (since 7.6 would be the first full
>     release). But if a different algorithm was added in 7.6.0, it
>     would also be eligible for default at 7.7.0. </span>
> -   <span class="simpara"> The default should only change in a full
>     release (7.3.0, 8.0.0, etc) and not in a revision release. The
>     only exception to this is in an emergency when a critical security
>     flaw is found in the current default. </span>

### See Also

-   <span class="function">password\_verify</span>
-   <span class="function">crypt</span>
-   <a href="https://github.com/ircmaxell/password_compat" class="link external">» userland implementation</a>
-   <span class="function">sodium\_crypto\_pwhash\_str</span>

password\_needs\_rehash
=======================

Checks if the given hash matches the given options

### Description

<span class="type">bool</span> <span
class="methodname">password\_needs\_rehash</span> ( <span
class="methodparam"><span class="type">string</span> `$hash`</span> ,
<span class="methodparam"><span class="type">mixed</span> `$algo`</span>
\[, <span class="methodparam"><span class="type">array</span>
`$options`</span> \] )

This function checks to see if the supplied hash implements the
algorithm and options provided. If not, it is assumed that the hash
needs to be rehashed.

### Parameters

`hash`  
A hash created by <span class="function">password\_hash</span>.

`algo`  
A
<a href="/password/constants.html" class="link">password algorithm constant</a>
denoting the algorithm to use when hashing the password.

`options`  
An associative array containing options. See the
<a href="/password/constants.html" class="link">password algorithm constants</a>
for documentation on the supported options for each algorithm.

### Return Values

Returns **`true`** if the hash should be rehashed to match the given
`algo` and `options`, or **`false`** otherwise.

### Changelog

| Version | Description                                                                                                                                       |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | The `algo` parameter expects a <span class="type">string</span> now, but still accepts <span class="type">int</span>s for backward compatibility. |

### Examples

**Example \#1 Usage of <span
class="function">password\_needs\_rehash</span>**

``` php
<?php

$password = 'rasmuslerdorf';
$hash = '$2y$10$YCFsG6elYca568hBi2pZ0.3LDL5wjgxct1N8w/oLR/jfHsiQwCqTS';

// The cost parameter can change over time as hardware improves
$options = array('cost' => 11);

// Verify stored hash against plain-text password
if (password_verify($password, $hash)) {
    // Check if a newer hashing algorithm is available
    // or the cost has changed
    if (password_needs_rehash($hash, PASSWORD_DEFAULT, $options)) {
        // If so, create a new hash, and replace the old one
        $newHash = password_hash($password, PASSWORD_DEFAULT, $options);
    }

    // Log user in
}
?>
```

password\_verify
================

Verifies that a password matches a hash

### Description

<span class="type">bool</span> <span
class="methodname">password\_verify</span> ( <span
class="methodparam"><span class="type">string</span> `$password`</span>
, <span class="methodparam"><span class="type">string</span>
`$hash`</span> )

Verifies that the given hash matches the given password.

Note that <span class="function">password\_hash</span> returns the
algorithm, cost and salt as part of the returned hash. Therefore, all
information that's needed to verify the hash is included in it. This
allows the verify function to verify the hash without needing separate
storage for the salt or algorithm information.

This function is safe against timing attacks.

### Parameters

`password`  
The user's password.

`hash`  
A hash created by <span class="function">password\_hash</span>.

### Return Values

Returns **`true`** if the password and hash match, or **`false`**
otherwise.

### Examples

**Example \#1 <span class="function">password\_verify</span> example**

``` php
<?php
// See the password_hash() example to see where this came from.
$hash = '$2y$07$BCryptRequires22Chrcte/VlQH0piJtjXl.0t1XkA8pw9dMXTpOq';

if (password_verify('rasmuslerdorf', $hash)) {
    echo 'Password is valid!';
} else {
    echo 'Invalid password.';
}
?>
```

The above example will output:

    Password is valid!

### See Also

-   <span class="function">password\_hash</span>
-   <a href="https://github.com/ircmaxell/password_compat" class="link external">» userland implementation</a>
-   <span class="function">sodium\_crypto\_pwhash\_str\_verify</span>

**Table of Contents**

-   [password\_algos](/ref/password.html#password_algos) — Get available
    password hashing algorithm IDs
-   [password\_get\_info](/ref/password.html#password_get_info) —
    Returns information about the given hash
-   [password\_hash](/ref/password.html#password_hash) — Creates a
    password hash
-   [password\_needs\_rehash](/ref/password.html#password_needs_rehash)
    — Checks if the given hash matches the given options
-   [password\_verify](/ref/password.html#password_verify) — Verifies
    that a password matches a hash

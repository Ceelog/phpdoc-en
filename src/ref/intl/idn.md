idn\_to\_ascii
==============

Convert domain name to IDNA ASCII form

### Description

Procedural style

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">idn\_to\_ascii</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = IDNA\_DEFAULT</span></span> \[,
<span class="methodparam"><span class="type">int</span> `$variant`<span
class="initializer"> = INTL\_IDNA\_VARIANT\_UTS46</span></span> \[,
<span class="methodparam"><span class="type">array</span>
`&$idna_info`</span> \]\]\] )

This function converts a Unicode domain name to an IDNA ASCII-compatible
format.

### Parameters

`domain`  
The domain to convert, which must be UTF-8 encoded.

`options`  
Conversion options - combination of IDNA\_\* constants (except
IDNA\_ERROR\_\* constants).

`variant`  
Either **`INTL_IDNA_VARIANT_2003`** (deprecated as of PHP 7.2.0) for
IDNA 2003 or **`INTL_IDNA_VARIANT_UTS46`** (only available as of ICU
4.6) for UTS \#46.

`idna_info`  
This parameter can be used only if **`INTL_IDNA_VARIANT_UTS46`** was
used for `variant`. In that case, it will be filled with an array with
the keys *'result'*, the possibly illegal result of the transformation,
*'isTransitionalDifferent'*, a boolean indicating whether the usage of
the transitional mechanisms of UTS \#46 either has or would have changed
the result and *'errors'*, which is an <span class="type">int</span>
representing a bitset of the error constants IDNA\_ERROR\_\*.

### Return Values

The domain name encoded in ASCII-compatible form, or **`false`** on
failure

### Changelog

| Version | Description                                                                                                                 |
|---------|-----------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | The default value of `variant` is now **`INTL_IDNA_VARIANT_UTS46`** instead of the deprecated **`INTL_IDNA_VARIANT_2003`**. |
| 7.2.0   | **`INTL_IDNA_VARIANT_2003`** has been deprecated; use **`INTL_IDNA_VARIANT_UTS46`** instead.                                |

### Examples

**Example \#1 <span class="function">idn\_to\_ascii</span> example**

``` php
<?php

echo idn_to_ascii('täst.de'); 

?>
```

The above example will output:

    xn--tst-qla.de

### See Also

-   <span class="function">idn\_to\_utf8</span>

idn\_to\_utf8
=============

Convert domain name from IDNA ASCII to Unicode

### Description

Procedural style

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">idn\_to\_utf8</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`<span class="initializer"> = IDNA\_DEFAULT</span></span> \[,
<span class="methodparam"><span class="type">int</span> `$variant`<span
class="initializer"> = INTL\_IDNA\_VARIANT\_UTS46</span></span> \[,
<span class="methodparam"><span class="type">array</span>
`&$idna_info`</span> \]\]\] )

This function converts a Unicode domain name from an IDNA
ASCII-compatible format to plain Unicode, encoded in UTF-8.

### Parameters

`domain`  
Domain to convert in an IDNA ASCII-compatible format.

`options`  
Conversion options - combination of IDNA\_\* constants (except
IDNA\_ERROR\_\* constants).

`variant`  
Either **`INTL_IDNA_VARIANT_2003`** (deprecated as of PHP 7.2.0) for
IDNA 2003 or **`INTL_IDNA_VARIANT_UTS46`** (only available as of ICU
4.6) for UTS \#46.

`idna_info`  
This parameter can be used only if **`INTL_IDNA_VARIANT_UTS46`** was
used for `variant`. In that case, it will be filled with an array with
the keys *'result'*, the possibly illegal result of the transformation,
*'isTransitionalDifferent'*, a boolean indicating whether the usage of
the transitional mechanisms of UTS \#46 either has or would have changed
the result and *'errors'*, which is an <span class="type">int</span>
representing a bitset of the error constants IDNA\_ERROR\_\*.

### Return Values

The domain name in Unicode, encoded in UTF-8, or **`false`** on failure

### Changelog

| Version | Description                                                                                                                 |
|---------|-----------------------------------------------------------------------------------------------------------------------------|
| 7.4.0   | The default value of `variant` is now **`INTL_IDNA_VARIANT_UTS46`** instead of the deprecated **`INTL_IDNA_VARIANT_2003`**. |
| 7.2.0   | **`INTL_IDNA_VARIANT_2003`** has been deprecated; use **`INTL_IDNA_VARIANT_UTS46`** instead.                                |

### Examples

**Example \#1 <span class="function">idn\_to\_utf8</span> example**

``` php
<?php

echo idn_to_utf8('xn--tst-qla.de'); 

?>
```

The above example will output:

    täst.de

### See Also

-   <span class="function">idn\_to\_ascii</span>

**Table of Contents**

-   [idn\_to\_ascii](/ref/intl/idn.html#idn_to_ascii) — Convert domain
    name to IDNA ASCII form
-   [idn\_to\_utf8](/ref/intl/idn.html#idn_to_utf8) — Convert domain
    name from IDNA ASCII to Unicode

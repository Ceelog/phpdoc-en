bind\_textdomain\_codeset
=========================

Specify the character encoding in which the messages from the DOMAIN
message catalog will be returned

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">bind\_textdomain\_codeset</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> ,
<span class="methodparam"><span class="type">string</span>
`$codeset`</span> )

With <span class="function">bind\_textdomain\_codeset</span>, you can
set in which encoding will be messages from `domain` returned by <span
class="function">gettext</span> and similar functions.

### Parameters

`domain`  
The domain

`codeset`  
The code set

### Return Values

A <span class="type">string</span> on success.

bindtextdomain
==============

Sets the path for a domain

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">bindtextdomain</span> ( <span
class="methodparam"><span class="type">string</span> `$domain`</span> ,
<span class="methodparam"><span class="type">string</span>
`$directory`</span> )

The <span class="function">bindtextdomain</span> function sets the path
for a domain.

### Parameters

`domain`  
The domain

`directory`  
The directory path

### Return Values

The full pathname for the `domain` currently being set.

### Examples

**Example \#1 <span class="function">bindtextdomain</span> example**

``` php
<?php

$domain = 'myapp';
echo bindtextdomain($domain, '/usr/share/myapp/locale');

?>
```

The above example will output:

    /usr/share/myapp/locale

dcgettext
=========

Overrides the domain for a single lookup

### Description

<span class="type">string</span> <span
class="methodname">dcgettext</span> ( <span class="methodparam"><span
class="type">string</span> `$domain`</span> , <span
class="methodparam"><span class="type">string</span> `$message`</span> ,
<span class="methodparam"><span class="type">int</span>
`$category`</span> )

This function allows you to override the current domain for a single
message lookup.

### Parameters

`domain`  
The domain

`message`  
The message

`category`  
The category

### Return Values

A <span class="type">string</span> on success.

### See Also

-   <span class="function">gettext</span>

dcngettext
==========

Plural version of dcgettext

### Description

<span class="type">string</span> <span
class="methodname">dcngettext</span> ( <span class="methodparam"><span
class="type">string</span> `$domain`</span> , <span
class="methodparam"><span class="type">string</span> `$singular`</span>
, <span class="methodparam"><span class="type">string</span>
`$plural`</span> , <span class="methodparam"><span
class="type">int</span> `$count`</span> , <span
class="methodparam"><span class="type">int</span> `$category`</span> )

This function allows you to override the current domain for a single
plural message lookup.

### Parameters

`domain`  
The domain

`singular`  

`plural`  

`count`  

`category`  

### Return Values

A <span class="type">string</span> on success.

### See Also

-   <span class="function">ngettext</span>

dgettext
========

Override the current domain

### Description

<span class="type">string</span> <span
class="methodname">dgettext</span> ( <span class="methodparam"><span
class="type">string</span> `$domain`</span> , <span
class="methodparam"><span class="type">string</span> `$message`</span> )

The <span class="function">dgettext</span> function allows you to
override the current `domain` for a single message lookup.

### Parameters

`domain`  
The domain

`message`  
The message

### Return Values

A <span class="type">string</span> on success.

### See Also

-   <span class="function">gettext</span>

dngettext
=========

Plural version of dgettext

### Description

<span class="type">string</span> <span
class="methodname">dngettext</span> ( <span class="methodparam"><span
class="type">string</span> `$domain`</span> , <span
class="methodparam"><span class="type">string</span> `$singular`</span>
, <span class="methodparam"><span class="type">string</span>
`$plural`</span> , <span class="methodparam"><span
class="type">int</span> `$count`</span> )

The <span class="function">dngettext</span> function allows you to
override the current `domain` for a single plural message lookup.

### Parameters

`domain`  
The domain

`singular`  

`plural`  

`count`  

### Return Values

A <span class="type">string</span> on success.

### See Also

-   <span class="function">ngettext</span>

gettext
=======

Lookup a message in the current domain

### Description

<span class="type">string</span> <span class="methodname">gettext</span>
( <span class="methodparam"><span class="type">string</span>
`$message`</span> )

Looks up a message in the current domain.

### Parameters

`message`  
The message being translated.

### Return Values

Returns a translated <span class="type">string</span> if one is found in
the translation table, or the submitted message if not found.

### Examples

**Example \#1 <span class="function">gettext</span>-check**

``` php
<?php
// Set language to German
putenv('LC_ALL=de_DE');
setlocale(LC_ALL, 'de_DE');

// Specify location of translation tables
bindtextdomain("myPHPApp", "./locale");

// Choose domain
textdomain("myPHPApp");

// Translation is looking for in ./locale/de_DE/LC_MESSAGES/myPHPApp.mo now

// Print a test message
echo gettext("Welcome to My PHP Application");

// Or use the alias _() for gettext()
echo _("Have a nice day");
?>
```

### Notes

> **Note**:
>
> You may use the underscore character '\_' as an alias to this
> function.

> **Note**:
>
> Setting a language isn't enough for some systems and the <span
> class="function">putenv</span> should be used to define the current
> locale.

### See Also

-   <span class="function">setlocale</span>

ngettext
========

Plural version of gettext

### Description

<span class="type">string</span> <span
class="methodname">ngettext</span> ( <span class="methodparam"><span
class="type">string</span> `$singular`</span> , <span
class="methodparam"><span class="type">string</span> `$plural`</span> ,
<span class="methodparam"><span class="type">int</span> `$count`</span>
)

The plural version of <span class="function">gettext</span>. Some
languages have more than one form for plural messages dependent on the
count.

### Parameters

`singular`  
The singular message ID.

`plural`  
The plural message ID.

`count`  
The number (e.g. item count) to determine the translation for the
respective grammatical number.

### Return Values

Returns correct plural form of message identified by `singular` and
`plural` for count `count`.

### Examples

**Example \#1 <span class="function">ngettext</span> example**

``` php
<?php

setlocale(LC_ALL, 'cs_CZ');
printf(ngettext("%d window", "%d windows", 1), 1); // 1 okno
printf(ngettext("%d window", "%d windows", 2), 2); // 2 okna
printf(ngettext("%d window", "%d windows", 5), 5); // 5 oken

?>
```

textdomain
==========

Sets the default domain

### Description

<span class="type">string</span> <span
class="methodname">textdomain</span> ( <span class="methodparam"><span
class="type"><span class="type">string</span><span
class="type">null</span></span> `$domain`</span> )

This function sets the domain to search within when calls are made to
<span class="function">gettext</span>, usually the named after an
application.

### Parameters

`domain`  
The new message domain, or **`NULL`** to get the current setting without
changing it

### Return Values

If successful, this function returns the current message domain, after
possibly changing it.

**Table of Contents**

-   [bind\_textdomain\_codeset](/ref/gettext.html#bind_textdomain_codeset)
    — Specify the character encoding in which the messages from the
    DOMAIN message catalog will be returned
-   [bindtextdomain](/ref/gettext.html#bindtextdomain) — Sets the path
    for a domain
-   [dcgettext](/ref/gettext.html#dcgettext) — Overrides the domain for
    a single lookup
-   [dcngettext](/ref/gettext.html#dcngettext) — Plural version of
    dcgettext
-   [dgettext](/ref/gettext.html#dgettext) — Override the current domain
-   [dngettext](/ref/gettext.html#dngettext) — Plural version of
    dgettext
-   [gettext](/ref/gettext.html#gettext) — Lookup a message in the
    current domain
-   [ngettext](/ref/gettext.html#ngettext) — Plural version of gettext
-   [textdomain](/ref/gettext.html#textdomain) — Sets the default domain

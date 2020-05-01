Yaconf
======

**Table of Contents**

-   [Introduction](/intro/yaconf.html)
-   [Installing/Configuring](/yaconf/setup.html)
    -   [Requirements](/yaconf/setup.html#Requirements)
    -   [Installation](/yaconf/setup.html#Installation)
    -   [Runtime
        Configuration](/yaconf/setup.html#Runtime%20Configuration)
    -   [Resource Types](/yaconf/setup.html#Resource%20Types)
-   [Predefined Constants](/yaconf/constants.html)
-   [Yaconf](/class/yaconf.html) — The Yaconf class
    -   [Yaconf::get](/class/yaconf.html#Yaconf::get) — Retrieve a item
    -   [Yaconf::has](/class/yaconf.html#Yaconf::has) — Determine if a
        item exists

Introduction
------------

Yaconf is a configurations container, it parses INIT files, stores the
result in PHP when PHP is started, the result lives with the whole PHP
lifecycle.

Class synopsis
--------------

**Yaconf**

<span class="ooclass"> class **Yaconf** </span> {

/\* Methods \*/

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">get</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$default_value`<span class="initializer"> = NULL</span></span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">has</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

}

Yaconf::get
===========

Retrieve a item

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">mixed</span> <span
class="methodname">Yaconf::get</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> \[, <span
class="methodparam"><span class="type">mixed</span>
`$default_value`<span class="initializer"> = NULL</span></span> \] )

### Parameters

`name`  
Configuration key, the key looks like "filename.key", or
"filename.sectionName,key".

`default_value`  
if the key doesn't exists, Yaconf::get will return this as result.

### Return Values

Returns configuration result(string or array) if the key exists, return
default\_value if not.

### Examples

**Example \#1 <span class="function">INI</span>example**

``` ini
;filenmame foo.ini, placed in directory which is yaconf.directoy
[SectionA]
;key value pair
key=val
;hash[a]=val
hash.a=val
;arr[0]=val
arr.0=val
;or
arr[]=val

;SectionB inherits SectionA
[SectionB:SectionA]
;override configuration key in SectionA
key=new_val
```

The above example will output something similar to:

    php7 -r 'var_dump(Yaconf::get("foo.SectionA.key"));'
    //string(3) "val"

    php7 -r 'var_dump(Yaconf::get("foo.SectionB.key"));'
    //string(7) "new_val"

    php7 -r 'var_dump(Yaconf::get("foo")["SectionA"]["hash"]);'
    //array(1)

Yaconf::has
===========

Determine if a item exists

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">bool</span> <span
class="methodname">Yaconf::has</span> ( <span class="methodparam"><span
class="type">string</span> `$name`</span> )

### Parameters

`name`  

### Return Values

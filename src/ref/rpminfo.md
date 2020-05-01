rpmaddtag
=========

Add tag retrieved in query

### Description

<span class="type">bool</span> <span class="methodname">rpmaddtag</span>
( <span class="methodparam"><span class="type">int</span> `$tag`</span>
)

Add an additional retrieved tag in subsequent queries.

### Parameters

`tag`  
One of RPMTAG\_\* constant, see the
<a href="/rpminfo/constants.html" class="link">rpminfo constants</a>
page.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

### See Also

-   <span class="function">rpminfo</span>
-   <span class="function">rpmdbinfo</span>
-   <span class="function">rpmdbsearch</span>

rpmdbinfo
=========

Get information from installed RPM

### Description

<span class="type">array</span> <span
class="methodname">rpmdbinfo</span> ( <span class="methodparam"><span
class="type">string</span> `$nevr`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$full`<span
class="initializer"> = **`FALSE`**</span></span> \] )

Retrieve information about an installed package, from the system RPM
database.

### Parameters

`nevr`  
Name with optional epoch, version and release.

`full`  
If **`TRUE`** all information headers for the file are retrieved, else
only a minimal set.

### Return Values

An <span class="type">array</span> of <span class="type">array</span> of
information or NULL on error.

### See Also

-   <span class="function">rpmaddtag</span>

### Examples

**Example \#1 A <span class="function">rpmdbinfo</span> example**

``` php
<?php
rpmaddtag(RPMTAG_INSTALLTIME);
$info = rpmdbinfo("php-pecl-rpminfo");
print_r($info);
?>
```

The above example will output:

    Array
    (
        [0] => Array
            (
                [Name] => php-pecl-rpminfo
                [Version] => 0.4.2
                [Release] => 1.fc31
                [Summary] => RPM information
                [Installtime] => 1586244687
                [Arch] => x86_64
            )
    )

rpmdbsearch
===========

Search RPM packages

### Description

<span class="type">array</span> <span
class="methodname">rpmdbsearch</span> ( <span class="methodparam"><span
class="type">string</span> `$pattern`</span> \[, <span
class="methodparam"><span class="type">int</span> `$rpmtag`<span
class="initializer"> = RPMTAG\_NAME</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$rpmmire`<span
class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">bool</span> `$full`<span
class="initializer"> = **`FALSE`**</span></span> \]\]\] )

Search packages in the system RPM database.

### Parameters

`pattern`  
Value to search for.

`rpmtag`  
Search criterion, one of RPMTAG\_\* constant, see the
<a href="/rpminfo/constants.html" class="link">rpminfo constants</a>
page.

`rpmmire`  
Pattern type, one of RPMMIRE\_\* constant, see the
<a href="/rpminfo/constants.html" class="link">rpminfo constants</a>
page. When \< 0 the criterion must equals the value, and database index
is used if possible.

`full`  
If **`TRUE`** all information headers for the file are retrieved, else
only a minimal set.

### Return Values

An <span class="type">array</span> of <span class="type">array</span> of
information or NULL on error.

### See Also

-   <span class="function">rpmaddtag</span>

### Examples

**Example \#1 Searching for the package owning a file**

``` php
<?php
$info = rpmdbsearch("/usr/bin/php", RPMTAG_INSTFILENAMES);
print_r($info);
?>
```

The above example will output:

    Array
    (
        [0] => Array
            (
                [Name] => php-cli
                [Version] => 7.4.4
                [Release] => 1.fc32
                [Summary] => Command-line interface for PHP
                [Arch] => x86_64
            )

    )

rpminfo
=======

Get information from a RPM file

### Description

<span class="type">array</span> <span class="methodname">rpminfo</span>
( <span class="methodparam"><span class="type">string</span>
`$path`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$full`<span class="initializer"> =
**`FALSE`**</span></span> \[, <span class="methodparam"><span
class="type">string</span> `&$error`</span> \]\] )

Retrieve information about a local file, a RPM package.

### Parameters

`path`  
Path of the RPM file.

`full`  
If **`TRUE`** all information headers for the file are retrieved, else
only a minimal set.

`error`  
If provided, will receive the possible error message, and will avoid a
runtime warning.

### Return Values

An <span class="type">array</span> of information or NULL on error.

### See Also

-   <span class="function">rpmaddtag</span>

### Examples

**Example \#1 A <span class="function">rpminfo</span> example**

``` php
<?php
rpmaddtag(RPMTAG_BUILDTIME);
$info = rpminfo("./php-pecl-rpminfo-0.4.2-1.el8.remi.7.4.x86_64.rpm");
print_r($info);
?>
```

The above example will output:

    Array
    (
        [Name] => php-pecl-rpminfo
        [Version] => 0.4.2
        [Release] => 1.el8
        [Summary] => RPM information
        [Buildtime] => 1586244821
        [Arch] => x86_64
    )

rpmvercmp
=========

RPM version comparison

### Description

<span class="type">int</span> <span class="methodname">rpmvercmp</span>
( <span class="methodparam"><span class="type">string</span>
`$evr1`</span> , <span class="methodparam"><span
class="type">string</span> `$evr2`</span> )

Compare 2 RPM versions.

### Parameters

`evr1`  
First epoch:version-release string

`evr2`  
Second epoch:version-release string

### Return Values

Returns \< 0 if evr1 is less than evr2, \> 0 if evr1 is greater than
evr2, and 0 if they are equal.

**Table of Contents**

-   [rpmaddtag](/ref/rpminfo.html#rpmaddtag) — Add tag retrieved in
    query
-   [rpmdbinfo](/ref/rpminfo.html#rpmdbinfo) — Get information from
    installed RPM
-   [rpmdbsearch](/ref/rpminfo.html#rpmdbsearch) — Search RPM packages
-   [rpminfo](/ref/rpminfo.html#rpminfo) — Get information from a RPM
    file
-   [rpmvercmp](/ref/rpminfo.html#rpmvercmp) — RPM version comparison

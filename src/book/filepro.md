filePro
=======

**Table of Contents**

-   [Introduction](/book/filepro.html#Introduction)
-   [Installing/Configuring](/book/filepro.html#Installing/Configuring)
    -   [Requirements](/book/filepro.html#Requirements)
    -   [Installation](/book/filepro.html#Installation)
    -   [Runtime
        Configuration](/book/filepro.html#Runtime%20Configuration)
    -   [Resource Types](/book/filepro.html#Resource%20Types)
-   [Predefined Constants](/book/filepro.html#Predefined%20Constants)
-   [filePro Functions](/book/filepro.html#filePro%20Functions)
    -   [filepro\_fieldcount](/book/filepro.html#filepro_fieldcount) —
        Find out how many fields are in a filePro database
    -   [filepro\_fieldname](/book/filepro.html#filepro_fieldname) —
        Gets the name of a field
    -   [filepro\_fieldtype](/book/filepro.html#filepro_fieldtype) —
        Gets the type of a field
    -   [filepro\_fieldwidth](/book/filepro.html#filepro_fieldwidth) —
        Gets the width of a field
    -   [filepro\_retrieve](/book/filepro.html#filepro_retrieve) —
        Retrieves data from a filePro database
    -   [filepro\_rowcount](/book/filepro.html#filepro_rowcount) — Find
        out how many rows are in a filePro database
    -   [filepro](/book/filepro.html#filepro) — Read and verify the map
        file

These functions allow read-only access to data stored in filePro
databases.

filePro is a registered trademark of fP Technologies, Inc. You can find
more information about filePro at
<a href="http://www.fptech.com/" class="link external">» http://www.fptech.com/</a>.

> **Note**:
>
> This extension has been moved to the
> <a href="https://pecl.php.net/" class="link external">» PECL</a>
> repository and is no longer bundled with PHP as of PHP 5.2.0.

Installing/Configuring
======================

**Table of Contents**

-   [Requirements](/book/filepro.html#Requirements)
-   [Installation](/book/filepro.html#Installation)
-   [Runtime Configuration](/book/filepro.html#Runtime%20Configuration)
-   [Resource Types](/book/filepro.html#Resource%20Types)

Requirements
------------

No external libraries are needed to build this extension.

Installation
------------

This extension has been moved to the
<a href="https://pecl.php.net/" class="link external">» PECL</a>
repository and is no longer bundled with PHP as of PHP 5.2.0

Information for installing this PECL extension may be found in the
manual chapter titled
<a href="/install/pecl.html" class="link">Installation of PECL extensions</a>.
Additional information such as new releases, downloads, source files,
maintainer information, and a CHANGELOG, can be located here:
<a href="https://pecl.php.net/package/filepro" class="link external">» https://pecl.php.net/package/filepro</a>.

Runtime Configuration
---------------------

This extension has no configuration directives defined in `php.ini`.

Resource Types
--------------

This extension has no resource types defined.

Predefined Constants
====================

This extension has no constants defined.

filepro\_fieldcount
===================

Find out how many fields are in a filePro database

### Description

<span class="type">int</span> <span
class="methodname">filepro\_fieldcount</span> ( <span
class="methodparam">void</span> )

Returns the number of fields (columns) in the opened filePro database.

### Return Values

Returns the number of fields in the opened filePro database, or
**`FALSE`** on errors.

### See Also

-   <span class="function">filepro</span>

filepro\_fieldname
==================

Gets the name of a field

### Description

<span class="type">string</span> <span
class="methodname">filepro\_fieldname</span> ( <span
class="methodparam"><span class="type">int</span> `$field_number`</span>
)

Returns the name of the field corresponding to `field_number`.

### Parameters

`field_number`  
The field number.

### Return Values

Returns the name of the field as a string, or **`FALSE`** on errors.

filepro\_fieldtype
==================

Gets the type of a field

### Description

<span class="type">string</span> <span
class="methodname">filepro\_fieldtype</span> ( <span
class="methodparam"><span class="type">int</span> `$field_number`</span>
)

Returns the edit type of the field corresponding to `field_number`.

### Parameters

`field_number`  
The field number.

### Return Values

Returns the edit type of the field as a string, or **`FALSE`** on
errors.

filepro\_fieldwidth
===================

Gets the width of a field

### Description

<span class="type">int</span> <span
class="methodname">filepro\_fieldwidth</span> ( <span
class="methodparam"><span class="type">int</span> `$field_number`</span>
)

Returns the width of the field corresponding to `field_number`.

### Parameters

`field_number`  
The field number.

### Return Values

Returns the width of the field as a integer, or **`FALSE`** on errors.

filepro\_retrieve
=================

Retrieves data from a filePro database

### Description

<span class="type">string</span> <span
class="methodname">filepro\_retrieve</span> ( <span
class="methodparam"><span class="type">int</span> `$row_number`</span> ,
<span class="methodparam"><span class="type">int</span>
`$field_number`</span> )

Returns the data from the specified location in the database.

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the files or directories being operated
> upon have the same UID (owner) as the script that is being
> executed.</span>

### Parameters

`row_number`  
The row number. Must be between zero and the total number of rows minus
one (0..<span class="function">filepro\_rowcount</span> - 1)

`field_number`  
The field number. Accepts values between zero and the total number of
fields minus one (0..<span class="function">filepro\_fieldcount</span> -
1)

### Return Values

Returns the specified data, or **`FALSE`** on errors.

filepro\_rowcount
=================

Find out how many rows are in a filePro database

### Description

<span class="type">int</span> <span
class="methodname">filepro\_rowcount</span> ( <span
class="methodparam">void</span> )

Returns the number of rows in the opened filePro database.

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the files or directories being operated
> upon have the same UID (owner) as the script that is being
> executed.</span>

### Return Values

Returns the number of rows in the opened filePro database, or
**`FALSE`** on errors.

### See Also

-   <span class="function">filepro</span>

filepro
=======

Read and verify the map file

### Description

<span class="type">bool</span> <span class="methodname">filepro</span> (
<span class="methodparam"><span class="type">string</span>
`$directory`</span> )

This reads and verifies the map file, storing the field count and info.

No locking is done, so you should avoid modifying your filePro database
while it may be opened in PHP.

> **Note**: <span class="simpara">When
> <a href="/features/safe-mode.html" class="link">safe mode</a> is
> enabled, PHP checks whether the files or directories being operated
> upon have the same UID (owner) as the script that is being
> executed.</span>

### Parameters

`directory`  
The map directory.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

**Table of Contents**

-   [filepro\_fieldcount](/book/filepro.html#filepro_fieldcount) — Find
    out how many fields are in a filePro database
-   [filepro\_fieldname](/book/filepro.html#filepro_fieldname) — Gets
    the name of a field
-   [filepro\_fieldtype](/book/filepro.html#filepro_fieldtype) — Gets
    the type of a field
-   [filepro\_fieldwidth](/book/filepro.html#filepro_fieldwidth) — Gets
    the width of a field
-   [filepro\_retrieve](/book/filepro.html#filepro_retrieve) — Retrieves
    data from a filePro database
-   [filepro\_rowcount](/book/filepro.html#filepro_rowcount) — Find out
    how many rows are in a filePro database
-   [filepro](/book/filepro.html#filepro) — Read and verify the map file

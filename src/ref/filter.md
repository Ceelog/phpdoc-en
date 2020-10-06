filter\_has\_var
================

Checks if variable of specified type exists

### Description

<span class="type">bool</span> <span
class="methodname">filter\_has\_var</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">string</span>
`$variable_name`</span> )

### Parameters

`type`  
One of **`INPUT_GET`**, **`INPUT_POST`**, **`INPUT_COOKIE`**,
**`INPUT_SERVER`**, or **`INPUT_ENV`**.

`variable_name`  
Name of a variable to check.

### Return Values

Returns **`TRUE`** on success or **`FALSE`** on failure.

filter\_id
==========

Returns the filter ID belonging to a named filter

### Description

<span class="type">int</span> <span class="methodname">filter\_id</span>
( <span class="methodparam"><span class="type">string</span>
`$filtername`</span> )

### Parameters

`filtername`  
Name of a filter to get.

### Return Values

ID of a filter on success or **`FALSE`** if filter doesn't exist.

### See Also

-   <span class="function">filter\_list</span>

filter\_input\_array
====================

Gets external variables and optionally filters them

### Description

<span class="type">mixed</span> <span
class="methodname">filter\_input\_array</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> \[,
<span class="methodparam"><span class="type">mixed</span>
`$definition`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$add_empty`<span class="initializer"> =
**`TRUE`**</span></span> \]\] )

This function is useful for retrieving many values without repetitively
calling <span class="function">filter\_input</span>.

### Parameters

`type`  
One of **`INPUT_GET`**, **`INPUT_POST`**, **`INPUT_COOKIE`**,
**`INPUT_SERVER`**, or **`INPUT_ENV`**.

`definition`  
An array defining the arguments. A valid key is a <span
class="type">string</span> containing a variable name and a valid value
is either a <a href="/filter/filters.html" class="link">filter type</a>,
or an <span class="type">array</span> optionally specifying the filter,
flags and options. If the value is an array, valid keys are *filter*
which specifies the
<a href="/filter/filters.html" class="link">filter type</a>, *flags*
which specifies any flags that apply to the filter, and *options* which
specifies any options that apply to the filter. See the example below
for a better understanding.

This parameter can be also an integer holding a
<a href="/filter/constants.html" class="link">filter constant</a>. Then
all values in the input array are filtered by this filter.

`add_empty`  
Add missing keys as **`NULL`** to the return value.

### Return Values

An array containing the values of the requested variables on success. If
the input array designated by `type` is not populated, the function
returns **`NULL`** if the **`FILTER_NULL_ON_FAILURE`** flag is not
given, or **`FALSE`** otherwise. For other failures, **`FALSE`** is
returned.

An array value will be **`FALSE`** if the filter fails, or **`NULL`** if
the variable is not set. Or if the flag **`FILTER_NULL_ON_FAILURE`** is
used, it returns **`FALSE`** if the variable is not set and **`NULL`**
if the filter fails. If the `add_empty` parameter is **`FALSE`**, no
array element will be added for unset variables.

### Examples

**Example \#1 A <span class="function">filter\_input\_array</span>
example**

``` php
<?php
error_reporting(E_ALL | E_STRICT);
/* data actually came from POST
$_POST = array(
    'product_id' => 'libgd<script>',
    'component'  => array('10'),
    'version'    => '2.0.33',
    'testarray'  => array('2', '23', '10', '12'),
    'testscalar' => '2',
);
*/

$args = array(
    'product_id'   => FILTER_SANITIZE_ENCODED,
    'component'    => array('filter'    => FILTER_VALIDATE_INT,
                            'flags'     => FILTER_REQUIRE_ARRAY, 
                            'options'   => array('min_range' => 1, 'max_range' => 10)
                           ),
    'version'      => FILTER_SANITIZE_ENCODED,
    'doesnotexist' => FILTER_VALIDATE_INT,
    'testscalar'   => array(
                            'filter' => FILTER_VALIDATE_INT,
                            'flags'  => FILTER_REQUIRE_SCALAR,
                           ),
    'testarray'    => array(
                            'filter' => FILTER_VALIDATE_INT,
                            'flags'  => FILTER_REQUIRE_ARRAY,
                           )

);

$myinputs = filter_input_array(INPUT_POST, $args);

var_dump($myinputs);
echo "\n";
?>
```

The above example will output:

    array(6) {
      ["product_id"]=>
      string(17) "libgd%3Cscript%3E"
      ["component"]=>
      array(1) {
        [0]=>
        int(10)
      }
      ["version"]=>
      string(6) "2.0.33"
      ["doesnotexist"]=>
      NULL
      ["testscalar"]=>
      int(2)
      ["testarray"]=>
      array(4) {
        [0]=>
        int(2)
        [1]=>
        int(23)
        [2]=>
        int(10)
        [3]=>
        int(12)
      }
    }

### Notes

> **Note**:
>
> There is no *REQUEST\_TIME* key in **`INPUT_SERVER`** array because it
> is inserted into the `$_SERVER` later.

### See Also

-   <span class="function">filter\_input</span>
-   <span class="function">filter\_var\_array</span>
-   <a href="/filter/filters.html" class="xref">Types of filters</a>

filter\_input
=============

Gets a specific external variable by name and optionally filters it

### Description

<span class="type">mixed</span> <span
class="methodname">filter\_input</span> ( <span
class="methodparam"><span class="type">int</span> `$type`</span> , <span
class="methodparam"><span class="type">string</span>
`$variable_name`</span> \[, <span class="methodparam"><span
class="type">int</span> `$filter`<span class="initializer"> =
FILTER\_DEFAULT</span></span> \[, <span class="methodparam"><span
class="type">mixed</span> `$options`</span> \]\] )

### Parameters

`type`  
One of **`INPUT_GET`**, **`INPUT_POST`**, **`INPUT_COOKIE`**,
**`INPUT_SERVER`**, or **`INPUT_ENV`**.

`variable_name`  
Name of a variable to get.

`filter`  
The ID of the filter to apply. The
<a href="/filter/filters.html" class="xref">Types of filters</a> manual
page lists the available filters.

If omitted, **`FILTER_DEFAULT`** will be used, which is equivalent to
<a href="/filter/filters.html#Sanitize%20filters" class="link"><strong><code>FILTER_UNSAFE_RAW</code></strong></a>.
This will result in no filtering taking place by default.

`options`  
Associative array of options or bitwise disjunction of flags. If filter
accepts options, flags can be provided in "flags" field of array.

### Return Values

Value of the requested variable on success, **`FALSE`** if the filter
fails, or **`NULL`** if the `variable_name` variable is not set. If the
flag **`FILTER_NULL_ON_FAILURE`** is used, it returns **`FALSE`** if the
variable is not set and **`NULL`** if the filter fails.

### Examples

**Example \#1 A <span class="function">filter\_input</span> example**

``` php
<?php
$search_html = filter_input(INPUT_GET, 'search', FILTER_SANITIZE_SPECIAL_CHARS);
$search_url = filter_input(INPUT_GET, 'search', FILTER_SANITIZE_ENCODED);
echo "You have searched for $search_html.\n";
echo "<a href='?search=$search_url'>Search again.</a>";
?>
```

The above example will output something similar to:

    You have searched for Me &#38; son.
    <a href='?search=Me%20%26%20son'>Search again.</a>

### See Also

-   <span class="function">filter\_var</span>
-   <span class="function">filter\_input\_array</span>
-   <span class="function">filter\_var\_array</span>
-   <a href="/filter/filters.html" class="xref">Types of filters</a>

filter\_list
============

Returns a list of all supported filters

### Description

<span class="type">array</span> <span
class="methodname">filter\_list</span> ( <span
class="methodparam">void</span> )

### Return Values

Returns an array of names of all supported filters, empty array if there
are no such filters. Indexes of this array are not filter IDs, they can
be obtained with <span class="function">filter\_id</span> from a name
instead.

### Examples

**Example \#1 A <span class="function">filter\_list</span> example**

``` php
<?php
print_r(filter_list());
?>
```

The above example will output something similar to:

    Array
    (
        [0] => int
        [1] => boolean
        [2] => float
        [3] => validate_regexp
        [4] => validate_url
        [5] => validate_email
        [6] => validate_ip
        [7] => string
        [8] => stripped
        [9] => encoded
        [10] => special_chars
        [11] => unsafe_raw
        [12] => email
        [13] => url
        [14] => number_int
        [15] => number_float
        [16] => magic_quotes
        [17] => callback
    )

filter\_var\_array
==================

Gets multiple variables and optionally filters them

### Description

<span class="type">mixed</span> <span
class="methodname">filter\_var\_array</span> ( <span
class="methodparam"><span class="type">array</span> `$data`</span> \[,
<span class="methodparam"><span class="type">mixed</span>
`$definition`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$add_empty`<span class="initializer"> =
**`TRUE`**</span></span> \]\] )

This function is useful for retrieving many values without repetitively
calling <span class="function">filter\_var</span>.

### Parameters

`data`  
An array with string keys containing the data to filter.

`definition`  
An array defining the arguments. A valid key is a <span
class="type">string</span> containing a variable name and a valid value
is either a <a href="/filter/filters.html" class="link">filter type</a>,
or an <span class="type">array</span> optionally specifying the filter,
flags and options. If the value is an array, valid keys are *filter*
which specifies the
<a href="/filter/filters.html" class="link">filter type</a>, *flags*
which specifies any flags that apply to the filter, and *options* which
specifies any options that apply to the filter. See the example below
for a better understanding.

This parameter can be also an integer holding a
<a href="/filter/constants.html" class="link">filter constant</a>. Then
all values in the input array are filtered by this filter.

`add_empty`  
Add missing keys as **`NULL`** to the return value.

### Return Values

An array containing the values of the requested variables on success, or
**`FALSE`** on failure. An array value will be **`FALSE`** if the filter
fails, or **`NULL`** if the variable is not set.

### Examples

**Example \#1 A <span class="function">filter\_var\_array</span>
example**

``` php
<?php
error_reporting(E_ALL | E_STRICT);
$data = array(
    'product_id'    => 'libgd<script>',
    'component'     => '10',
    'versions'      => '2.0.33',
    'testscalar'    => array('2', '23', '10', '12'),
    'testarray'     => '2',
);

$args = array(
    'product_id'   => FILTER_SANITIZE_ENCODED,
    'component'    => array('filter'    => FILTER_VALIDATE_INT,
                            'flags'     => FILTER_FORCE_ARRAY, 
                            'options'   => array('min_range' => 1, 'max_range' => 10)
                           ),
    'versions'     => FILTER_SANITIZE_ENCODED,
    'doesnotexist' => FILTER_VALIDATE_INT,
    'testscalar'   => array(
                            'filter' => FILTER_VALIDATE_INT,
                            'flags'  => FILTER_REQUIRE_SCALAR,
                           ),
    'testarray'    => array(
                            'filter' => FILTER_VALIDATE_INT,
                            'flags'  => FILTER_FORCE_ARRAY,
                           )

);

$myinputs = filter_var_array($data, $args);

var_dump($myinputs);
echo "\n";
?>
```

The above example will output:

    array(6) {
      ["product_id"]=>
      string(17) "libgd%3Cscript%3E"
      ["component"]=>
      array(1) {
        [0]=>
        int(10)
      }
      ["versions"]=>
      string(6) "2.0.33"
      ["doesnotexist"]=>
      NULL
      ["testscalar"]=>
      bool(false)
      ["testarray"]=>
      array(1) {
        [0]=>
        int(2)
      }
    }

### See Also

-   <span class="function">filter\_input\_array</span>
-   <span class="function">filter\_var</span>
-   <span class="function">filter\_input</span>
-   <a href="/filter/filters.html" class="xref">Types of filters</a>

filter\_var
===========

Filters a variable with a specified filter

### Description

<span class="type">mixed</span> <span
class="methodname">filter\_var</span> ( <span class="methodparam"><span
class="type">mixed</span> `$variable`</span> \[, <span
class="methodparam"><span class="type">int</span> `$filter`<span
class="initializer"> = FILTER\_DEFAULT</span></span> \[, <span
class="methodparam"><span class="type">mixed</span> `$options`</span>
\]\] )

### Parameters

`variable`  
Value to filter. Note that scalar values are
<a href="/language/types/string.html#language.types.string.casting" class="link">converted to string</a>
internally before they are filtered.

`filter`  
The ID of the filter to apply. The
<a href="/filter/filters.html" class="xref">Types of filters</a> manual
page lists the available filters.

If omitted, **`FILTER_DEFAULT`** will be used, which is equivalent to
<a href="/filter/filters.html#Sanitize%20filters" class="link"><strong><code>FILTER_UNSAFE_RAW</code></strong></a>.
This will result in no filtering taking place by default.

`options`  
Associative array of options or bitwise disjunction of flags. If filter
accepts options, flags can be provided in "flags" field of array. For
the "callback" filter, <span class="type">callable</span> type should be
passed. The callback must accept one argument, the value to be filtered,
and return the value after filtering/sanitizing it.

``` php
<?php
// for filters that accept options, use this format
$options = array(
    'options' => array(
        'default' => 3, // value to return if the filter fails
        // other options here
        'min_range' => 0
    ),
    'flags' => FILTER_FLAG_ALLOW_OCTAL,
);
$var = filter_var('0755', FILTER_VALIDATE_INT, $options);

// for filters that only accept flags, you can pass them directly
$var = filter_var('oops', FILTER_VALIDATE_BOOLEAN, FILTER_NULL_ON_FAILURE);

// for filters that only accept flags, you can also pass as an array
$var = filter_var('oops', FILTER_VALIDATE_BOOLEAN,
                  array('flags' => FILTER_NULL_ON_FAILURE));

// callback validate filter
function foo($value)
{
    // Expected format: Surname, GivenNames
    if (strpos($value, ", ") === false) return false;
    list($surname, $givennames) = explode(", ", $value, 2);
    $empty = (empty($surname) || empty($givennames));
    $notstrings = (!is_string($surname) || !is_string($givennames));
    if ($empty || $notstrings) {
        return false;
    } else {
        return $value;
    }
}
$var = filter_var('Doe, Jane Sue', FILTER_CALLBACK, array('options' => 'foo'));
?>
```

### Return Values

Returns the filtered data, or **`FALSE`** if the filter fails.

### Examples

**Example \#1 A <span class="function">filter\_var</span> example**

``` php
<?php
var_dump(filter_var('bob@example.com', FILTER_VALIDATE_EMAIL));
var_dump(filter_var('http://example.com', FILTER_VALIDATE_URL, FILTER_FLAG_PATH_REQUIRED));
?>
```

The above example will output:

    string(15) "bob@example.com"
    bool(false)

### See Also

-   <span class="function">filter\_var\_array</span>
-   <span class="function">filter\_input</span>
-   <span class="function">filter\_input\_array</span>
-   <a href="/filter/filters.html" class="xref">Types of filters</a>

**Table of Contents**

-   [filter\_has\_var](/ref/filter.html#filter_has_var) — Checks if
    variable of specified type exists
-   [filter\_id](/ref/filter.html#filter_id) — Returns the filter ID
    belonging to a named filter
-   [filter\_input\_array](/ref/filter.html#filter_input_array) — Gets
    external variables and optionally filters them
-   [filter\_input](/ref/filter.html#filter_input) — Gets a specific
    external variable by name and optionally filters it
-   [filter\_list](/ref/filter.html#filter_list) — Returns a list of all
    supported filters
-   [filter\_var\_array](/ref/filter.html#filter_var_array) — Gets
    multiple variables and optionally filters them
-   [filter\_var](/ref/filter.html#filter_var) — Filters a variable with
    a specified filter

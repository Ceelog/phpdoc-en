checkdate
=========

Validate a Gregorian date

### Description

<span class="type">bool</span> <span class="methodname">checkdate</span>
( <span class="methodparam"><span class="type">int</span>
`$month`</span> , <span class="methodparam"><span
class="type">int</span> `$day`</span> , <span class="methodparam"><span
class="type">int</span> `$year`</span> )

Checks the validity of the date formed by the arguments. A date is
considered valid if each parameter is properly defined.

### Parameters

`month`  
The month is between 1 and 12 inclusive.

`day`  
The day is within the allowed number of days for the given `month`. Leap
`year`s are taken into consideration.

`year`  
The year is between 1 and 32767 inclusive.

### Return Values

Returns **`TRUE`** if the date given is valid; otherwise returns
**`FALSE`**.

### Examples

**Example \#1 <span class="function">checkdate</span> example**

``` php
<?php
var_dump(checkdate(12, 31, 2000));
var_dump(checkdate(2, 29, 2001));
?>
```

The above example will output:

    bool(true)
    bool(false)

### See Also

-   <span class="function">mktime</span>
-   <span class="function">strtotime</span>

date\_add
=========

Alias of <span class="methodname">DateTime::add</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::add</span>

date\_create\_from\_format
==========================

Alias of <span class="methodname">DateTime::createFromFormat</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::createFromFormat</span>

date\_create\_immutable\_from\_format
=====================================

Alias of <span
class="methodname">DateTimeImmutable::createFromFormat</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeImmutable::createFromFormat</span>

date\_create\_immutable
=======================

Alias of <span
class="methodname">DateTimeImmutable::\_\_construct</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeImmutable::\_\_construct</span>

date\_create
============

Alias of <span class="methodname">DateTime::\_\_construct</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::\_\_construct</span>

date\_date\_set
===============

Alias of <span class="methodname">DateTime::setDate</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::setDate</span>

date\_default\_timezone\_get
============================

Gets the default timezone used by all date/time functions in a script

### Description

<span class="type">string</span> <span
class="methodname">date\_default\_timezone\_get</span> ( <span
class="methodparam">void</span> )

In order of preference, this function returns the default timezone by:

-   Reading the timezone set using the <span
    class="function">date\_default\_timezone\_set</span> function (if
    any)

-   Prior to PHP 5.4.0 *only*: Reading the `TZ` environment variable (if
    non empty)

-   Reading the value of the
    <a href="/datetime/setup.html#" class="link">date.timezone</a> ini
    option (if set)

-   Prior to PHP 5.4.0 *only*: Querying the host operating system (if
    supported and allowed by the OS). This uses an algorithm that has to
    *guess* the timezone. This is by no means going to work correctly
    for every situation. A warning is shown when this stage is reached.
    Do not rely on it to be guessed correctly, and set
    <a href="/datetime/setup.html#" class="link">date.timezone</a> to
    the correct timezone instead.

If none of the above succeed, <span
class="methodname">date\_default\_timezone\_get</span> will return a
default timezone of *UTC*.

### Return Values

Returns a <span class="type">string</span>.

### Examples

**Example \#1 Getting the default timezone**

``` php
<?php
date_default_timezone_set('Europe/London');

if (date_default_timezone_get()) {
    echo 'date_default_timezone_set: ' . date_default_timezone_get() . '<br />';
}

if (ini_get('date.timezone')) {
    echo 'date.timezone: ' . ini_get('date.timezone');
}

?>
```

The above example will output something similar to:

    date_default_timezone_set: Europe/London
    date.timezone: Europe/London

**Example \#2 Getting the abbreviation of a timezone**

``` php
<?php
date_default_timezone_set('America/Los_Angeles');
echo date_default_timezone_get() . ' => ' . date('e') . ' => ' . date('T');
?>
```

The above example will output:

    America/Los_Angeles => America/Los_Angeles => PST

### See Also

-   <span class="function">date\_default\_timezone\_set</span>
-   <a href="/timezones.html" class="xref">List of Supported Timezones</a>

date\_default\_timezone\_set
============================

Sets the default timezone used by all date/time functions in a script

### Description

<span class="type">bool</span> <span
class="methodname">date\_default\_timezone\_set</span> ( <span
class="methodparam"><span class="type">string</span>
`$timezoneID`</span> )

<span class="function">date\_default\_timezone\_set</span> sets the
default timezone used by all date/time functions.

> **Note**:
>
> Since PHP 5.1.0 (when the date/time functions were rewritten), every
> call to a date/time function will generate a **`E_NOTICE`** if the
> timezone isn't valid, and/or a **`E_WARNING`** message if using the
> system settings or the `TZ` environment variable.

Instead of using this function to set the default timezone in your
script, you can also use the INI setting
<a href="/datetime/setup.html#" class="link">date.timezone</a> to set
the default timezone.

### Parameters

`timezoneID`  
The timezone identifier, like *UTC*, *Africa/Lagos*, *Asia/Hong\_Kong*,
or *Europe/Lisbon*. The list of valid identifiers is available in the
<a href="/timezones.html" class="xref">List of Supported Timezones</a>.

### Return Values

This function returns **`FALSE`** if the `timezoneID` isn't valid, or
**`TRUE`** otherwise.

### Examples

**Example \#1 Getting the default timezone**

``` php
<?php
date_default_timezone_set('America/Los_Angeles');

$script_tz = date_default_timezone_get();

if (strcmp($script_tz, ini_get('date.timezone'))){
    echo 'Script timezone differs from ini-set timezone.';
} else {
    echo 'Script timezone and ini-set timezone match.';
}
?>
```

### See Also

-   <span class="function">date\_default\_timezone\_get</span>
-   <a href="/timezones.html" class="xref">List of Supported Timezones</a>

date\_diff
==========

Alias of <span class="methodname">DateTime::diff</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::diff</span>

date\_format
============

Alias of <span class="methodname">DateTime::format</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::format</span>

date\_get\_last\_errors
=======================

Alias of <span class="methodname">DateTime::getLastErrors</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::getLastErrors</span>

date\_interval\_create\_from\_date\_string
==========================================

Alias of <span
class="methodname">DateInterval::createFromDateString</span>

### Description

This function is an alias of: <span
class="methodname">DateInterval::createFromDateString</span>

date\_interval\_format
======================

Alias of <span class="methodname">DateInterval::format</span>

### Description

This function is an alias of: <span
class="methodname">DateInterval::format</span>

date\_isodate\_set
==================

Alias of <span class="methodname">DateTime::setISODate</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::setISODate</span>

date\_modify
============

Alias of <span class="methodname">DateTime::modify</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::modify</span>

date\_offset\_get
=================

Alias of <span class="methodname">DateTime::getOffset</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::getOffset</span>

date\_parse\_from\_format
=========================

Get info about given date formatted according to the specified format

### Description

<span class="type">array</span> <span
class="methodname">date\_parse\_from\_format</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> ,
<span class="methodparam"><span class="type">string</span>
`$datetime`</span> )

Returns associative array with detailed info about given date/time.

### Parameters

`format`  
Format accepted by <span
class="function">DateTime::createFromFormat</span>.

`datetime`  
String representing the date/time.

### Return Values

Returns associative array with detailed info about given date/time.

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The *zone* element of the returned array represents seconds instead of minutes now, and its sign is inverted. For instance *-120* is now *7200*. |

### Examples

**Example \#1 <span class="function">date\_parse\_from\_format</span>
example**

``` php
<?php
$date = "6.1.2009 13:00+01:00";
print_r(date_parse_from_format("j.n.Y H:iP", $date));
?>
```

The above example will output:

    Array
    (
        [year] => 2009
        [month] => 1
        [day] => 6
        [hour] => 13
        [minute] => 0
        [second] => 0
        [fraction] => 
        [warning_count] => 0
        [warnings] => Array
            (
            )

        [error_count] => 0
        [errors] => Array
            (
            )

        [is_localtime] => 1
        [zone_type] => 1
        [zone] => 3600
        [is_dst] => 
    )

### See Also

-   <span class="function">DateTime::createFromFormat</span>
-   <span class="function">checkdate</span>

date\_parse
===========

Returns associative array with detailed info about given date/time

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">date\_parse</span> ( <span class="methodparam"><span
class="type">string</span> `$datetime`</span> )

### Parameters

`datetime`  
Date/time in format accepted by <span
class="function">DateTimeImmutable::\_\_construct</span>.

### Return Values

Returns <span class="type">array</span> with information about the
parsed date/time on success or **`FALSE`** on failure.

### Errors/Exceptions

In case the date/time format has an error, the element 'errors' will
contains the error messages.

### Changelog

| Version | Description                                                                                                                                      |
|---------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The *zone* element of the returned array represents seconds instead of minutes now, and its sign is inverted. For instance *-120* is now *7200*. |

### Examples

**Example \#1 A <span class="function">date\_parse</span> example**

``` php
<?php
print_r(date_parse("2006-12-12 10:00:00.5"));
?>
```

The above example will output:

    Array
    (
        [year] => 2006
        [month] => 12
        [day] => 12
        [hour] => 10
        [minute] => 0
        [second] => 0
        [fraction] => 0.5
        [warning_count] => 0
        [warnings] => Array()
        [error_count] => 0
        [errors] => Array()
        [is_localtime] => 
    )

<a href="/datetime/formats.html#Relative%20Formats" class="link">Relative formats</a>
do not influence the values parsed from absolute formats, but are parsed
into the "relative" element.

**Example \#2 <span class="function">date\_parse</span> with relative
formats**

``` php
<?php
print_r(date_parse("2006-12-12 10:00:00.5 +1 week +1 hour"));
?>
```

The above example will output:

    Array
    (
        [year] => 2006
        [month] => 12
        [day] => 12
        [hour] => 10
        [minute] => 0
        [second] => 0
        [fraction] => 0.5
        [warning_count] => 0
        [warnings] => Array
            (
            )

        [error_count] => 0
        [errors] => Array
            (
            )

        [is_localtime] =>
        [relative] => Array
            (
                [year] => 0
                [month] => 0
                [day] => 7
                [hour] => 1
                [minute] => 0
                [second] => 0
            )

    )

### See Also

-   <span class="function">checkdate</span>
-   <span class="function">getdate</span>

date\_sub
=========

Alias of <span class="methodname">DateTime::sub</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::sub</span>

date\_sun\_info
===============

Returns an array with information about sunset/sunrise and twilight
begin/end

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">date\_sun\_info</span> ( <span
class="methodparam"><span class="type">int</span> `$timestamp`</span> ,
<span class="methodparam"><span class="type">float</span>
`$latitude`</span> , <span class="methodparam"><span
class="type">float</span> `$longitude`</span> )

### Parameters

`timestamp`  
Unix timestamp.

`latitude`  
Latitude in degrees.

`longitude`  
Longitude in degrees.

### Return Values

Returns array on success or **`FALSE`** on failure. The structure of the
array is detailed in the following list:

*sunrise*  
<span class="simpara"> The timestamp of the sunrise (zenith angle =
90°35'). </span>

*sunset*  
<span class="simpara"> The timestamp of the sunset (zenith angle =
90°35'). </span>

*transit*  
<span class="simpara"> The timestamp when the sun is at its zenith, i.e.
has reached its topmost point. </span>

*civil\_twilight\_begin*  
<span class="simpara"> The start of the civil dawn (zenith angle = 96°).
It ends at *sunrise*. </span>

*civil\_twilight\_end*  
<span class="simpara"> The end of the civil dusk (zenith angle = 96°).
It starts at *sunset*. </span>

*nautical\_twilight\_begin*  
<span class="simpara"> The start of the nautical dawn (zenith angle =
102°). It ends at *civil\_twilight\_begin*. </span>

*nautical\_twilight\_end*  
<span class="simpara"> The end of the nautical dusk (zenith angle =
102°). It starts at *civil\_twilight\_end*. </span>

*astronomical\_twilight\_begin*  
<span class="simpara"> The start of the astronomical dawn (zenith angle
= 108°). It ends at *nautical\_twilight\_begin*. </span>

*astronomical\_twilight\_end*  
<span class="simpara"> The end of the astronomical dusk (zenith angle =
108°). It starts at *nautical\_twilight\_end*. </span>

The values of the array elements are either UNIX timestamps, **`FALSE`**
if the sun is below the respective zenith for the whole day, or
**`TRUE`** if the sun is above the respective zenith for the whole day.

### Examples

**Example \#1 A <span class="function">date\_sun\_info</span> example**

``` php
<?php
$sun_info = date_sun_info(strtotime("2006-12-12"), 31.7667, 35.2333);
foreach ($sun_info as $key => $val) {
    echo "$key: " . date("H:i:s", $val) . "\n";
}
?>
```

The above example will output:

    sunrise: 05:52:11
    sunset: 15:41:21
    transit: 10:46:46
    civil_twilight_begin: 05:24:08
    civil_twilight_end: 16:09:24
    nautical_twilight_begin: 04:52:25
    nautical_twilight_end: 16:41:06
    astronomical_twilight_begin: 04:21:32
    astronomical_twilight_end: 17:12:00

**Example \#2 Polar night**

``` php
<?php
var_dump(date_sun_info(strtotime("2017-12-21"), 90, 0));
?>
```

The above example will output:

    array(9) {
      ["sunrise"]=>
      bool(false)
      ["sunset"]=>
      bool(false)
      ["transit"]=>
      int(1513857490)
      ["civil_twilight_begin"]=>
      bool(false)
      ["civil_twilight_end"]=>
      bool(false)
      ["nautical_twilight_begin"]=>
      bool(false)
      ["nautical_twilight_end"]=>
      bool(false)
      ["astronomical_twilight_begin"]=>
      bool(false)
      ["astronomical_twilight_end"]=>
      bool(false)
    }

**Example \#3 Midnight sun**

``` php
<?php
var_dump(date_sun_info(strtotime("2017-06-21"), 90, 0));
?>
```

The above example will output:

    array(9) {
      ["sunrise"]=>
      bool(true)
      ["sunset"]=>
      bool(true)
      ["transit"]=>
      int(1498046510)
      ["civil_twilight_begin"]=>
      bool(true)
      ["civil_twilight_end"]=>
      bool(true)
      ["nautical_twilight_begin"]=>
      bool(true)
      ["nautical_twilight_end"]=>
      bool(true)
      ["astronomical_twilight_begin"]=>
      bool(true)
      ["astronomical_twilight_end"]=>
      bool(true)
    }

### See Also

-   <span class="function">date\_sunrise</span>
-   <span class="function">date\_sunset</span>

date\_sunrise
=============

Returns time of sunrise for a given day and location

### Description

<span class="type">mixed</span> <span
class="methodname">date\_sunrise</span> ( <span
class="methodparam"><span class="type">int</span> `$timestamp`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$returnFormat`<span class="initializer"> =
SUNFUNCS\_RET\_STRING</span></span> \[, <span class="methodparam"><span
class="type">float</span> `$latitude`<span class="initializer"> =
ini\_get("date.default\_latitude")</span></span> \[, <span
class="methodparam"><span class="type">float</span> `$longitude`<span
class="initializer"> = ini\_get("date.default\_longitude")</span></span>
\[, <span class="methodparam"><span class="type">float</span>
`$zenith`<span class="initializer"> =
ini\_get("date.sunrise\_zenith")</span></span> \[, <span
class="methodparam"><span class="type">float</span> `$utcOffset`<span
class="initializer"> = 0</span></span> \]\]\]\]\] )

<span class="function">date\_sunrise</span> returns the sunrise time for
a given day (specified as a `timestamp`) and location.

### Parameters

`timestamp`  
The `timestamp` of the day from which the sunrise time is taken.

`returnFormat`  
| constant                 | description                                                     | example     |
|--------------------------|-----------------------------------------------------------------|-------------|
| SUNFUNCS\_RET\_STRING    | returns the result as <span class="type">string</span>          | 16:46       |
| SUNFUNCS\_RET\_DOUBLE    | returns the result as <span class="type">float</span>           | 16.78243132 |
| SUNFUNCS\_RET\_TIMESTAMP | returns the result as <span class="type">int</span> (timestamp) | 1095034606  |

`latitude`  
Defaults to North, pass in a negative value for South. See also:
<a href="/datetime/setup.html#" class="link">date.default_latitude</a>

`longitude`  
Defaults to East, pass in a negative value for West. See also:
<a href="/datetime/setup.html#" class="link">date.default_longitude</a>

`zenith`  
`zenith` is the angle between the center of the sun and a line
perpendicular to earth's surface. It defaults to
<a href="/datetime/setup.html#" class="link">date.sunrise_zenith</a>

| Angle  | Description                                                                                    |
|--------|------------------------------------------------------------------------------------------------|
| 90°50' | Sunrise: the point where the sun becomes visible.                                              |
| 96°    | Civil twilight: conventionally used to signify the start of dawn.                              |
| 102°   | Nautical twilight: the point at which the horizon starts being visible at sea.                 |
| 108°   | Astronomical twilight: the point at which the sun starts being the source of any illumination. |

`utcOffset`  
Specified in hours. The `utcOffset` is ignored, if `returnFormat` is
**`SUNFUNCS_RET_TIMESTAMP`**.

### Return Values

Returns the sunrise time in a specified `returnFormat` on success or
**`FALSE`** on failure. One potential reason for failure is that the sun
does not rise at all, which happens inside the polar circles for part of
the year.

### Errors/Exceptions

Every call to a date/time function will generate a **`E_NOTICE`** if the
time zone is not valid, and/or a **`E_STRICT`** or **`E_WARNING`**
message if using the system settings or the `TZ` environment variable.
See also <span class="function">date\_default\_timezone\_set</span>

### Examples

**Example \#1 <span class="function">date\_sunrise</span> example**

``` php
<?php

/* calculate the sunrise time for Lisbon, Portugal
Latitude: 38.4 North
Longitude: 9 West
Zenith ~= 90
offset: +1 GMT
*/

echo date("D M d Y"). ', sunrise time : ' .date_sunrise(time(), SUNFUNCS_RET_STRING, 38.4, -9, 90, 1);

?>
```

The above example will output something similar to:

    Mon Dec 20 2004, sunrise time : 08:54

**Example \#2 No sunrise**

``` php
<?php
$solstice = strtotime('2017-12-21');
var_dump(date_sunrise($solstice, SUNFUNCS_RET_STRING, 69.245833, -53.537222));
?>
```

The above example will output:

    bool(false)

### See Also

-   <span class="function">date\_sunset</span>
-   <span class="function">date\_sun\_info</span>

date\_sunset
============

Returns time of sunset for a given day and location

### Description

<span class="type">mixed</span> <span
class="methodname">date\_sunset</span> ( <span class="methodparam"><span
class="type">int</span> `$timestamp`</span> \[, <span
class="methodparam"><span class="type">int</span> `$returnFormat`<span
class="initializer"> = SUNFUNCS\_RET\_STRING</span></span> \[, <span
class="methodparam"><span class="type">float</span> `$latitude`<span
class="initializer"> = ini\_get("date.default\_latitude")</span></span>
\[, <span class="methodparam"><span class="type">float</span>
`$longitude`<span class="initializer"> =
ini\_get("date.default\_longitude")</span></span> \[, <span
class="methodparam"><span class="type">float</span> `$zenith`<span
class="initializer"> = ini\_get("date.sunset\_zenith")</span></span> \[,
<span class="methodparam"><span class="type">float</span>
`$utcOffset`<span class="initializer"> = 0</span></span> \]\]\]\]\] )

<span class="function">date\_sunset</span> returns the sunset time for a
given day (specified as a `timestamp`) and location.

### Parameters

`timestamp`  
The `timestamp` of the day from which the sunset time is taken.

`returnFormat`  
| constant                 | description                                                     | example     |
|--------------------------|-----------------------------------------------------------------|-------------|
| SUNFUNCS\_RET\_STRING    | returns the result as <span class="type">string</span>          | 16:46       |
| SUNFUNCS\_RET\_DOUBLE    | returns the result as <span class="type">float</span>           | 16.78243132 |
| SUNFUNCS\_RET\_TIMESTAMP | returns the result as <span class="type">int</span> (timestamp) | 1095034606  |

`latitude`  
Defaults to North, pass in a negative value for South. See also:
<a href="/datetime/setup.html#" class="link">date.default_latitude</a>

`longitude`  
Defaults to East, pass in a negative value for West. See also:
<a href="/datetime/setup.html#" class="link">date.default_longitude</a>

`zenith`  
`zenith` is the angle between the center of the sun and a line
perpendicular to earth's surface. It defaults to
<a href="/datetime/setup.html#" class="link">date.sunset_zenith</a>

| Angle  | Description                                                                                  |
|--------|----------------------------------------------------------------------------------------------|
| 90°50' | Sunset: the point where the sun becomes invisible.                                           |
| 96°    | Civil twilight: conventionally used to signify the end of dusk.                              |
| 102°   | Nautical twilight: the point at which the horizon ends being visible at sea.                 |
| 108°   | Astronomical twilight: the point at which the sun ends being the source of any illumination. |

`utcOffset`  
Specified in hours. The `utcOffset` is ignored, if `returnFormat` is
**`SUNFUNCS_RET_TIMESTAMP`**.

### Errors/Exceptions

Every call to a date/time function will generate a **`E_NOTICE`** if the
time zone is not valid, and/or a **`E_STRICT`** or **`E_WARNING`**
message if using the system settings or the `TZ` environment variable.
See also <span class="function">date\_default\_timezone\_set</span>

### Return Values

Returns the sunset time in a specified `returnFormat` on success or
**`FALSE`** on failure. One potential reason for failure is that the sun
does not set at all, which happens inside the polar circles for part of
the year.

### Examples

**Example \#1 <span class="function">date\_sunset</span> example**

``` php
<?php

/* calculate the sunset time for Lisbon, Portugal
Latitude: 38.4 North
Longitude: 9 West
Zenith ~= 90
offset: +1 GMT
*/

echo date("D M d Y"). ', sunset time : ' .date_sunset(time(), SUNFUNCS_RET_STRING, 38.4, -9, 90, 1);

?>
```

The above example will output something similar to:

    Mon Dec 20 2004, sunset time : 18:13

**Example \#2 No sunset**

``` php
<?php
$solstice = strtotime('2017-12-21');
var_dump(date_sunset($solstice, SUNFUNCS_RET_STRING, 69.245833, -53.537222));
?>
```

The above example will output:

    bool(false)

### See Also

-   <span class="function">date\_sunrise</span>
-   <span class="function">date\_sun\_info</span>

date\_time\_set
===============

Alias of <span class="methodname">DateTime::setTime</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::setTime</span>

date\_timestamp\_get
====================

Alias of <span class="methodname">DateTime::getTimestamp</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::getTimestamp</span>

date\_timestamp\_set
====================

Alias of <span class="methodname">DateTime::setTimestamp</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::setTimestamp</span>

date\_timezone\_get
===================

Alias of <span class="methodname">DateTime::getTimezone</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::getTimezone</span>

date\_timezone\_set
===================

Alias of <span class="methodname">DateTime::setTimezone</span>

### Description

This function is an alias of: <span
class="methodname">DateTime::setTimezone</span>

date
====

Format a local time/date

### Description

<span class="type">string</span> <span class="methodname">date</span> (
<span class="methodparam"><span class="type">string</span>
`$format`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timestamp`<span class="initializer"> =
time()</span></span> \] )

Returns a string formatted according to the given format string using
the given integer `timestamp` or the current time if no timestamp is
given. In other words, `timestamp` is optional and defaults to the value
of <span class="function">time</span>.

### Parameters

`format`  
Format accepted by <span
class="function">DateTimeInterface::format</span>.

`timestamp`  
The optional `timestamp` parameter is an <span class="type">int</span>
Unix timestamp that defaults to the current local time if a `timestamp`
is not given. In other words, it defaults to the value of <span
class="function">time</span>.

### Return Values

Returns a formatted date string. If a non-numeric value is used for
`timestamp`, **`FALSE`** is returned and an **`E_WARNING`** level error
is emitted.

### Errors/Exceptions

Every call to a date/time function will generate a **`E_NOTICE`** if the
time zone is not valid, and/or a **`E_STRICT`** or **`E_WARNING`**
message if using the system settings or the `TZ` environment variable.
See also <span class="function">date\_default\_timezone\_set</span>

### Examples

**Example \#1 <span class="function">date</span> examples**

``` php
<?php
// set the default timezone to use. Available since PHP 5.1
date_default_timezone_set('UTC');


// Prints something like: Monday
echo date("l");

// Prints something like: Monday 8th of August 2005 03:12:46 PM
echo date('l jS \of F Y h:i:s A');

// Prints: July 1, 2000 is on a Saturday
echo "July 1, 2000 is on a " . date("l", mktime(0, 0, 0, 7, 1, 2000));

/* use the constants in the format parameter */
// prints something like: Wed, 25 Sep 2013 15:28:57 -0700
echo date(DATE_RFC2822);

// prints something like: 2000-07-01T00:00:00+00:00
echo date(DATE_ATOM, mktime(0, 0, 0, 7, 1, 2000));
?>
```

You can prevent a recognized character in the format string from being
expanded by escaping it with a preceding backslash. If the character
with a backslash is already a special sequence, you may need to also
escape the backslash.

**Example \#2 Escaping characters in <span
class="function">date</span>**

``` php
<?php
// prints something like: Wednesday the 15th
echo date('l \t\h\e jS');
?>
```

It is possible to use <span class="function">date</span> and <span
class="function">mktime</span> together to find dates in the future or
the past.

**Example \#3 <span class="function">date</span> and <span
class="function">mktime</span> example**

``` php
<?php
$tomorrow  = mktime(0, 0, 0, date("m")  , date("d")+1, date("Y"));
$lastmonth = mktime(0, 0, 0, date("m")-1, date("d"),   date("Y"));
$nextyear  = mktime(0, 0, 0, date("m"),   date("d"),   date("Y")+1);
?>
```

> **Note**:
>
> This can be more reliable than simply adding or subtracting the number
> of seconds in a day or month to a timestamp because of daylight saving
> time.

Some examples of <span class="function">date</span> formatting. Note
that you should escape any other characters, as any which currently have
a special meaning will produce undesirable results, and other characters
may be assigned meaning in future PHP versions. When escaping, be sure
to use single quotes to prevent characters like \\n from becoming
newlines.

**Example \#4 <span class="function">date</span> Formatting**

``` php
<?php
// Assuming today is March 10th, 2001, 5:16:18 pm, and that we are in the
// Mountain Standard Time (MST) Time Zone

$today = date("F j, Y, g:i a");                 // March 10, 2001, 5:16 pm
$today = date("m.d.y");                         // 03.10.01
$today = date("j, n, Y");                       // 10, 3, 2001
$today = date("Ymd");                           // 20010310
$today = date('h-i-s, j-m-y, it is w Day');     // 05-16-18, 10-03-01, 1631 1618 6 Satpm01
$today = date('\i\t \i\s \t\h\e jS \d\a\y.');   // it is the 10th day.
$today = date("D M j G:i:s T Y");               // Sat Mar 10 17:16:18 MST 2001
$today = date('H:m:s \m \i\s\ \m\o\n\t\h');     // 17:03:18 m is month
$today = date("H:i:s");                         // 17:16:18
$today = date("Y-m-d H:i:s");                   // 2001-03-10 17:16:18 (the MySQL DATETIME format)
?>
```

To format dates in other languages, you should use the <span
class="function">setlocale</span> and <span
class="function">strftime</span> functions instead of <span
class="function">date</span>.

### Notes

> **Note**:
>
> To generate a timestamp from a string representation of the date, you
> may be able to use <span class="function">strtotime</span>.
> Additionally, some databases have functions to convert their date
> formats into timestamps (such as MySQL's
> <a href="http://dev.mysql.com/doc/mysql/en/date-and-time-functions.html" class="link external">» UNIX_TIMESTAMP</a>
> function).

**Tip**

Timestamp of the start of the request is available in
`$_SERVER['REQUEST_TIME']` since PHP 5.1.

### See Also

-   <span class="function">gmdate</span>
-   <span class="function">idate</span>
-   <span class="function">getdate</span>
-   <span class="function">getlastmod</span>
-   <span class="function">mktime</span>
-   <span class="function">strftime</span>
-   <span class="function">time</span>
-   <span class="function">DateTimeImmutable::\_\_construct</span>
-   <a href="/class/datetimeinterface.html#Predefined%20Constants" class="link">Predefined DateTime Constants</a>

getdate
=======

Get date/time information

### Description

<span class="type">array</span> <span class="methodname">getdate</span>
(\[ <span class="methodparam"><span class="type">int</span>
`$timestamp`<span class="initializer"> = time()</span></span> \] )

Returns an associative <span class="type">array</span> containing the
date information of the `timestamp`, or the current local time if no
`timestamp` is given.

### Parameters

`timestamp`  
The optional `timestamp` parameter is an <span class="type">int</span>
Unix timestamp that defaults to the current local time if a `timestamp`
is not given. In other words, it defaults to the value of <span
class="function">time</span>.

### Return Values

Returns an associative <span class="type">array</span> of information
related to the `timestamp`. Elements from the returned associative array
are as follows:

| Key         | Description                                                                                                                                        | Example returned values                                         |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| *"seconds"* | Numeric representation of seconds                                                                                                                  | *0* to *59*                                                     |
| *"minutes"* | Numeric representation of minutes                                                                                                                  | *0* to *59*                                                     |
| *"hours"*   | Numeric representation of hours                                                                                                                    | *0* to *23*                                                     |
| *"mday"*    | Numeric representation of the day of the month                                                                                                     | *1* to *31*                                                     |
| *"wday"*    | Numeric representation of the day of the week                                                                                                      | *0* (for Sunday) through *6* (for Saturday)                     |
| *"mon"*     | Numeric representation of a month                                                                                                                  | *1* through *12*                                                |
| *"year"*    | A full numeric representation of a year, 4 digits                                                                                                  | Examples: *1999* or *2003*                                      |
| *"yday"*    | Numeric representation of the day of the year                                                                                                      | *0* through *365*                                               |
| *"weekday"* | A full textual representation of the day of the week                                                                                               | *Sunday* through *Saturday*                                     |
| *"month"*   | A full textual representation of a month, such as January or March                                                                                 | *January* through *December*                                    |
| *0*         | Seconds since the Unix Epoch, similar to the values returned by <span class="function">time</span> and used by <span class="function">date</span>. | System Dependent, typically *-2147483648* through *2147483647*. |

### Examples

**Example \#1 <span class="function">getdate</span> example**

``` php
<?php
$today = getdate();
print_r($today);
?>
```

The above example will output something similar to:

    Array
    (
        [seconds] => 40
        [minutes] => 58
        [hours]   => 21
        [mday]    => 17
        [wday]    => 2
        [mon]     => 6
        [year]    => 2003
        [yday]    => 167
        [weekday] => Tuesday
        [month]   => June
        [0]       => 1055901520
    )

### See Also

-   <span class="function">date</span>
-   <span class="function">idate</span>
-   <span class="function">localtime</span>
-   <span class="function">time</span>
-   <span class="function">setlocale</span>

gettimeofday
============

Get current time

### Description

<span class="type">mixed</span> <span
class="methodname">gettimeofday</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$returnFloat`<span
class="initializer"> = **`FALSE`**</span></span> \] )

This is an interface to gettimeofday(2). It returns an associative array
containing the data returned from the system call.

### Parameters

`returnFloat`  
When set to **`TRUE`**, a float instead of an array is returned.

### Return Values

By default an <span class="type">array</span> is returned. If
`returnFloat` is set, then a <span class="type">float</span> is
returned.

Array keys:

-   <span class="simpara"> "sec" - seconds since the Unix Epoch </span>
-   <span class="simpara"> "usec" - microseconds </span>
-   <span class="simpara"> "minuteswest" - minutes west of Greenwich
    </span>
-   <span class="simpara"> "dsttime" - type of dst correction </span>

### Examples

**Example \#1 <span class="function">gettimeofday</span> example**

``` php
<?php
print_r(gettimeofday());

echo gettimeofday(true);
?>
```

The above example will output something similar to:

    Array
    (
        [sec] => 1073504408
        [usec] => 238215
        [minuteswest] => 0
        [dsttime] => 1
    )

    1073504408.23910

gmdate
======

Format a GMT/UTC date/time

### Description

<span class="type">string</span> <span class="methodname">gmdate</span>
( <span class="methodparam"><span class="type">string</span>
`$format`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timestamp`<span class="initializer"> =
time()</span></span> \] )

Identical to the <span class="function">date</span> function except that
the time returned is Greenwich Mean Time (GMT).

### Parameters

`format`  
The format of the outputted date <span class="type">string</span>. See
the formatting options for the <span class="function">date</span>
function.

`timestamp`  
The optional `timestamp` parameter is an <span class="type">int</span>
Unix timestamp that defaults to the current local time if a `timestamp`
is not given. In other words, it defaults to the value of <span
class="function">time</span>.

### Return Values

Returns a formatted date string. If a non-numeric value is used for
`timestamp`, **`FALSE`** is returned and an **`E_WARNING`** level error
is emitted.

### Examples

**Example \#1 <span class="function">gmdate</span> example**

When run in Finland (GMT +0200), the first line below prints "Jan 01
1998 00:00:00", while the second prints "Dec 31 1997 22:00:00".

``` php
<?php
echo date("M d Y H:i:s", mktime(0, 0, 0, 1, 1, 1998));
echo gmdate("M d Y H:i:s", mktime(0, 0, 0, 1, 1, 1998));
?>
```

### See Also

-   <span class="function">date</span>
-   <span class="function">mktime</span>
-   <span class="function">gmmktime</span>
-   <span class="function">strftime</span>

gmmktime
========

Get Unix timestamp for a GMT date

### Description

<span class="type">int</span> <span class="methodname">gmmktime</span>
(\[ <span class="methodparam"><span class="type">int</span> `$hour`<span
class="initializer"> = gmdate("H")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$minute`<span
class="initializer"> = gmdate("i")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$second`<span
class="initializer"> = gmdate("s")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$month`<span
class="initializer"> = gmdate("n")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$day`<span
class="initializer"> = gmdate("j")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$year`<span
class="initializer"> = gmdate("Y")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$isDST`<span
class="initializer"> = -1</span></span> \]\]\]\]\]\]\] )

Identical to <span class="function">mktime</span> except the passed
parameters represents a GMT date. <span class="function">gmmktime</span>
internally uses <span class="function">mktime</span> so only times valid
in derived local time can be used.

Like <span class="function">mktime</span>, arguments may be left out in
order from right to left, with any omitted arguments being set to the
current corresponding GMT value.

### Parameters

`hour`  
The number of the hour relative to the start of the day determined by
`month`, `day` and `year`. Negative values reference the hour before
midnight of the day in question. Values greater than 23 reference the
appropriate hour in the following day(s).

`minute`  
The number of the minute relative to the start of the `hour`. Negative
values reference the minute in the previous hour. Values greater than 59
reference the appropriate minute in the following hour(s).

`second`  
The number of seconds relative to the start of the `minute`. Negative
values reference the second in the previous minute. Values greater than
59 reference the appropriate second in the following minute(s).

`month`  
The number of the month relative to the end of the previous year. Values
1 to 12 reference the normal calendar months of the year in question.
Values less than 1 (including negative values) reference the months in
the previous year in reverse order, so 0 is December, -1 is November,
etc. Values greater than 12 reference the appropriate month in the
following year(s).

`day`  
The number of the day relative to the end of the previous month. Values
1 to 28, 29, 30 or 31 (depending upon the month) reference the normal
days in the relevant month. Values less than 1 (including negative
values) reference the days in the previous month, so 0 is the last day
of the previous month, -1 is the day before that, etc. Values greater
than the number of days in the relevant month reference the appropriate
day in the following month(s).

`year`  
The year

`isDST`  
Parameters always represent a GMT date so `isDST` doesn't influence the
result.

> **Note**:
>
> This parameter has been removed in PHP 7.0.0.

### Return Values

Returns a <span class="type">int</span> Unix timestamp.

### Examples

**Example \#1 <span class="function">gmmktime</span> basic example**

``` php
<?php
// Prints: July 1, 2000 is on a Saturday
echo "July 1, 2000 is on a " . date("l", gmmktime(0, 0, 0, 7, 1, 2000));
?>
```

### See Also

-   <span class="function">mktime</span>
-   <span class="function">date</span>
-   <span class="function">time</span>

gmstrftime
==========

Format a GMT/UTC time/date according to locale settings

### Description

<span class="type">string</span> <span
class="methodname">gmstrftime</span> ( <span class="methodparam"><span
class="type">string</span> `$format`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timestamp`<span
class="initializer"> = time()</span></span> \] )

Behaves the same as <span class="function">strftime</span> except that
the time returned is Greenwich Mean Time (GMT). For example, when run in
Eastern Standard Time (GMT -0500), the first line below prints "Dec 31
1998 20:00:00", while the second prints "Jan 01 1999 01:00:00".

### Parameters

`format`  
See description in <span class="function">strftime</span>.

`timestamp`  
The optional `timestamp` parameter is an <span class="type">int</span>
Unix timestamp that defaults to the current local time if a `timestamp`
is not given. In other words, it defaults to the value of <span
class="function">time</span>.

### Return Values

Returns a string formatted according to the given format string using
the given `timestamp` or the current local time if no timestamp is
given. Month and weekday names and other language dependent strings
respect the current locale set with <span
class="function">setlocale</span>.

### Examples

**Example \#1 <span class="function">gmstrftime</span> example**

``` php
<?php
setlocale(LC_TIME, 'en_US');
echo strftime("%b %d %Y %H:%M:%S", mktime(20, 0, 0, 12, 31, 98)) . "\n";
echo gmstrftime("%b %d %Y %H:%M:%S", mktime(20, 0, 0, 12, 31, 98)) . "\n";
?>
```

### See Also

-   <span class="function">strftime</span>

idate
=====

Format a local time/date as integer

### Description

<span class="type">int</span> <span class="methodname">idate</span> (
<span class="methodparam"><span class="type">string</span>
`$format`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timestamp`<span class="initializer"> =
time()</span></span> \] )

Returns a number formatted according to the given format string using
the given integer `timestamp` or the current local time if no timestamp
is given. In other words, `timestamp` is optional and defaults to the
value of <span class="function">time</span>.

Unlike the function <span class="function">date</span>, <span
class="function">idate</span> accepts just one char in the `format`
parameter.

### Parameters

`format`  
| `format` character | Description                                                                                                         |
|--------------------|---------------------------------------------------------------------------------------------------------------------|
| *B*                | Swatch Beat/Internet Time                                                                                           |
| *d*                | Day of the month                                                                                                    |
| *h*                | Hour (12 hour format)                                                                                               |
| *H*                | Hour (24 hour format)                                                                                               |
| *i*                | Minutes                                                                                                             |
| *I* (uppercase i)  | returns *1* if DST is activated, *0* otherwise                                                                      |
| *L* (uppercase l)  | returns *1* for leap year, *0* otherwise                                                                            |
| *m*                | Month number                                                                                                        |
| *s*                | Seconds                                                                                                             |
| *t*                | Days in current month                                                                                               |
| *U*                | Seconds since the Unix Epoch - January 1 1970 00:00:00 UTC - this is the same as <span class="function">time</span> |
| *w*                | Day of the week (*0* on Sunday)                                                                                     |
| *W*                | ISO-8601 week number of year, weeks starting on Monday                                                              |
| *y*                | Year (1 or 2 digits - check note below)                                                                             |
| *Y*                | Year (4 digits)                                                                                                     |
| *z*                | Day of the year                                                                                                     |
| *Z*                | Timezone offset in seconds                                                                                          |

`timestamp`  
The optional `timestamp` parameter is an <span class="type">int</span>
Unix timestamp that defaults to the current local time if a `timestamp`
is not given. In other words, it defaults to the value of <span
class="function">time</span>.

### Return Values

Returns an <span class="type">int</span>.

As <span class="function">idate</span> always returns an <span
class="type">int</span> and as they can't start with a "0", <span
class="function">idate</span> may return fewer digits than you would
expect. See the example below.

### Errors/Exceptions

Every call to a date/time function will generate a **`E_NOTICE`** if the
time zone is not valid, and/or a **`E_STRICT`** or **`E_WARNING`**
message if using the system settings or the `TZ` environment variable.
See also <span class="function">date\_default\_timezone\_set</span>

### Examples

**Example \#1 <span class="function">idate</span> example**

``` php
<?php
$timestamp = strtotime('1st January 2004'); //1072915200

// this prints the year in a two digit format
// however, as this would start with a "0", it
// only prints "4"
echo idate('y', $timestamp);
?>
```

### See Also

-   <span class="function">date</span>
-   <span class="function">getdate</span>
-   <span class="function">time</span>

localtime
=========

Get the local time

### Description

<span class="type">array</span> <span
class="methodname">localtime</span> (\[ <span class="methodparam"><span
class="type">int</span> `$timestamp`<span class="initializer"> =
time()</span></span> \[, <span class="methodparam"><span
class="type">bool</span> `$associative`<span class="initializer"> =
**`FALSE`**</span></span> \]\] )

The <span class="function">localtime</span> function returns an array
identical to that of the structure returned by the C function call.

### Parameters

`timestamp`  
The optional `timestamp` parameter is an <span class="type">int</span>
Unix timestamp that defaults to the current local time if a `timestamp`
is not given. In other words, it defaults to the value of <span
class="function">time</span>.

`associative`  
If set to **`FALSE`** or not supplied then the array is returned as a
regular, numerically indexed array. If the argument is set to **`TRUE`**
then <span class="function">localtime</span> returns an associative
array containing all the different elements of the structure returned by
the C function call to localtime. The names of the different keys of the
associative array are as follows:

-   <span class="simpara"> "tm\_sec" - seconds, *0* to *59* </span>
-   <span class="simpara"> "tm\_min" - minutes, *0* to *59* </span>
-   <span class="simpara"> "tm\_hour" - hours, *0* to *23* </span>
-   <span class="simpara"> "tm\_mday" - day of the month, *1* to *31*
    </span>
-   <span class="simpara"> "tm\_mon" - month of the year, *0* (Jan) to
    *11* (Dec) </span>
-   <span class="simpara"> "tm\_year" - years since 1900 </span>
-   <span class="simpara"> "tm\_wday" - day of the week, *0* (Sun) to
    *6* (Sat) </span>
-   <span class="simpara"> "tm\_yday" - day of the year, *0* to *365*
    </span>
-   <span class="simpara"> "tm\_isdst" - is daylight savings time in
    effect? </span> <span class="simpara"> Positive if yes, *0* if not,
    negative if unknown. </span>

### Errors/Exceptions

Every call to a date/time function will generate a **`E_NOTICE`** if the
time zone is not valid, and/or a **`E_STRICT`** or **`E_WARNING`**
message if using the system settings or the `TZ` environment variable.
See also <span class="function">date\_default\_timezone\_set</span>

### Examples

**Example \#1 <span class="function">localtime</span> example**

``` php
<?php
$localtime = localtime();
$localtime_assoc = localtime(time(), true);
print_r($localtime);
print_r($localtime_assoc);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => 24
        [1] => 3
        [2] => 19
        [3] => 3
        [4] => 3
        [5] => 105
        [6] => 0
        [7] => 92
        [8] => 1
    )

    Array
    (
        [tm_sec] => 24
        [tm_min] => 3
        [tm_hour] => 19
        [tm_mday] => 3
        [tm_mon] => 3
        [tm_year] => 105
        [tm_wday] => 0
        [tm_yday] => 92
        [tm_isdst] => 1
    )

### See Also

-   <span class="function">getdate</span>

microtime
=========

Return current Unix timestamp with microseconds

### Description

<span class="type">mixed</span> <span
class="methodname">microtime</span> (\[ <span class="methodparam"><span
class="type">bool</span> `$getAsFloat`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="function">microtime</span> returns the current Unix
timestamp with microseconds. This function is only available on
operating systems that support the gettimeofday() system call.

For performance measurements, using <span class="function">hrtime</span>
is recommended.

### Parameters

`getAsFloat`  
If used and set to **`TRUE`**, <span class="function">microtime</span>
will return a <span class="type">float</span> instead of a <span
class="type">string</span>, as described in the return values section
below.

### Return Values

By default, <span class="function">microtime</span> returns a <span
class="type">string</span> in the form "msec sec", where *sec* is the
number of seconds since the Unix epoch (0:00:00 January 1,1970 GMT), and
*msec* measures microseconds that have elapsed since *sec* and is also
expressed in seconds.

If `getAsFloat` is set to **`TRUE`**, then <span
class="function">microtime</span> returns a <span
class="type">float</span>, which represents the current time in seconds
since the Unix epoch accurate to the nearest microsecond.

### Examples

**Example \#1 Timing script execution with <span
class="function">microtime</span>**

``` php
<?php
/**
 * Simple function to replicate PHP 5 behaviour
 */
function microtime_float()
{
    list($usec, $sec) = explode(" ", microtime());
    return ((float)$usec + (float)$sec);
}

$time_start = microtime_float();

// Sleep for a while
usleep(100);

$time_end = microtime_float();
$time = $time_end - $time_start;

echo "Did nothing in $time seconds\n";
?>
```

**Example \#2 Timing script execution in PHP 5**

``` php
<?php
$time_start = microtime(true);

// Sleep for a while
usleep(100);

$time_end = microtime(true);
$time = $time_end - $time_start;

echo "Did nothing in $time seconds\n";
?>
```

**Example \#3 <span class="function">microtime</span> and
*REQUEST\_TIME\_FLOAT* (as of PHP 5.4.0)**

``` php
<?php
// Randomize sleeping time
usleep(mt_rand(100, 10000));

// As of PHP 5.4.0, REQUEST_TIME_FLOAT is available in the $_SERVER superglobal array.
// It contains the timestamp of the start of the request with microsecond precision.
$time = microtime(true) - $_SERVER["REQUEST_TIME_FLOAT"];

echo "Did nothing in $time seconds\n";
?>
```

### See Also

-   <span class="function">time</span>
-   <span class="function">hrtime</span>

mktime
======

Get Unix timestamp for a date

### Description

<span class="type">int</span> <span class="methodname">mktime</span> (\[
<span class="methodparam"><span class="type">int</span> `$hour`<span
class="initializer"> = date("H")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$minute`<span
class="initializer"> = date("i")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$second`<span
class="initializer"> = date("s")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$month`<span
class="initializer"> = date("n")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$day`<span
class="initializer"> = date("j")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$year`<span
class="initializer"> = date("Y")</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$isDST`<span
class="initializer"> = -1</span></span> \]\]\]\]\]\]\] )

Returns the Unix timestamp corresponding to the arguments given. This
timestamp is a long integer containing the number of seconds between the
Unix Epoch (January 1 1970 00:00:00 GMT) and the time specified.

Arguments may be left out in order from right to left; any arguments
thus omitted will be set to the current value according to the local
date and time.

### Notes

> **Note**:
>
> As of PHP 5.1, when called with no arguments, <span
> class="function">mktime</span> throws an **`E_STRICT`** notice: use
> the <span class="function">time</span> function instead.

### Parameters

`hour`  
The number of the hour relative to the start of the day determined by
`month`, `day` and `year`. Negative values reference the hour before
midnight of the day in question. Values greater than 23 reference the
appropriate hour in the following day(s).

`minute`  
The number of the minute relative to the start of the `hour`. Negative
values reference the minute in the previous hour. Values greater than 59
reference the appropriate minute in the following hour(s).

`second`  
The number of seconds relative to the start of the `minute`. Negative
values reference the second in the previous minute. Values greater than
59 reference the appropriate second in the following minute(s).

`month`  
The number of the month relative to the end of the previous year. Values
1 to 12 reference the normal calendar months of the year in question.
Values less than 1 (including negative values) reference the months in
the previous year in reverse order, so 0 is December, -1 is November,
etc. Values greater than 12 reference the appropriate month in the
following year(s).

`day`  
The number of the day relative to the end of the previous month. Values
1 to 28, 29, 30 or 31 (depending upon the month) reference the normal
days in the relevant month. Values less than 1 (including negative
values) reference the days in the previous month, so 0 is the last day
of the previous month, -1 is the day before that, etc. Values greater
than the number of days in the relevant month reference the appropriate
day in the following month(s).

`year`  
The number of the year, may be a two or four digit value, with values
between 0-69 mapping to 2000-2069 and 70-100 to 1970-2000. On systems
where time\_t is a 32bit signed integer, as most common today, the valid
range for `year` is somewhere between 1901 and 2038. However, before PHP
5.1.0 this range was limited from 1970 to 2038 on some systems (e.g.
Windows).

`isDST`  
This parameter can be set to 1 if the time is during daylight savings
time (DST), 0 if it is not, or -1 (the default) if it is unknown whether
the time is within daylight savings time or not. If it's unknown, PHP
tries to figure it out itself. This can cause unexpected (but not
incorrect) results. Some times are invalid if DST is enabled on the
system PHP is running on or `isDST` is set to 1. If DST is enabled in
e.g. 2:00, all times between 2:00 and 3:00 are invalid and <span
class="function">mktime</span> returns an undefined (usually negative)
value. Some systems (e.g. Solaris 8) enable DST at midnight so time 0:30
of the day when DST is enabled is evaluated as 23:30 of the previous
day.

> **Note**:
>
> As of PHP 5.1.0, this parameter became deprecated. As a result, the
> new timezone handling features should be used instead.

> **Note**:
>
> This parameter has been removed in PHP 7.0.0.

### Return Values

<span class="function">mktime</span> returns the Unix timestamp of the
arguments given. If the arguments are invalid, the function returns
**`FALSE`**.

### Errors/Exceptions

Every call to a date/time function will generate a **`E_NOTICE`** if the
time zone is not valid, and/or a **`E_STRICT`** or **`E_WARNING`**
message if using the system settings or the `TZ` environment variable.
See also <span class="function">date\_default\_timezone\_set</span>

### Examples

**Example \#1 <span class="function">mktime</span> basic example**

``` php
<?php
// Set the default timezone to use. Available as of PHP 5.1
date_default_timezone_set('UTC');

// Prints: July 1, 2000 is on a Saturday
echo "July 1, 2000 is on a " . date("l", mktime(0, 0, 0, 7, 1, 2000));

// Prints something like: 2006-04-05T01:02:03+00:00
echo date('c', mktime(1, 2, 3, 4, 5, 2006));
?>
```

**Example \#2 <span class="function">mktime</span> example**

<span class="function">mktime</span> is useful for doing date arithmetic
and validation, as it will automatically calculate the correct value for
out-of-range input. For example, each of the following lines produces
the string "Jan-01-1998".

``` php
<?php
echo date("M-d-Y", mktime(0, 0, 0, 12, 32, 1997));
echo date("M-d-Y", mktime(0, 0, 0, 13, 1, 1997));
echo date("M-d-Y", mktime(0, 0, 0, 1, 1, 1998));
echo date("M-d-Y", mktime(0, 0, 0, 1, 1, 98));
?>
```

**Example \#3 Last day of a month**

The last day of any given month can be expressed as the "0" day of the
next month, not the -1 day. Both of the following examples will produce
the string "The last day in Feb 2000 is: 29".

``` php
<?php
$lastday = mktime(0, 0, 0, 3, 0, 2000);
echo strftime("Last day in Feb 2000 is: %d", $lastday);
$lastday = mktime(0, 0, 0, 4, -31, 2000);
echo strftime("Last day in Feb 2000 is: %d", $lastday);
?>
```

### Notes

**Caution**

Before PHP 5.1.0, negative timestamps were not supported under any known
version of Windows and some other systems as well. Therefore the range
of valid years was limited to 1970 through 2038.

### See Also

-   <span class="function">checkdate</span>
-   <span class="function">gmmktime</span>
-   <span class="function">date</span>
-   <span class="function">time</span>

strftime
========

Format a local time/date according to locale settings

### Description

<span class="type">string</span> <span
class="methodname">strftime</span> ( <span class="methodparam"><span
class="type">string</span> `$format`</span> \[, <span
class="methodparam"><span class="type">int</span> `$timestamp`<span
class="initializer"> = time()</span></span> \] )

Format the time and/or date according to locale settings. Month and
weekday names and other language-dependent strings respect the current
locale set with <span class="function">setlocale</span>.

Not all conversion specifiers may be supported by your C library, in
which case they will not be supported by PHP's <span
class="function">strftime</span>. Additionally, not all platforms
support negative timestamps, so your date range may be limited to no
earlier than the Unix epoch. This means that %e, %T, %R and, %D (and
possibly others) - as well as dates prior to *Jan 1, 1970* - will not
work on Windows, some Linux distributions, and a few other operating
systems. For Windows systems, a complete overview of supported
conversion specifiers can be found at
<a href="http://msdn.microsoft.com/en-us/library/fe06s4ak.aspx" class="link external">» MSDN</a>.

### Parameters

`format`  
|        `format`        | Description                                                                                                                                             | Example returned values                                                |
|:----------------------:|---------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------|
|          *Day*         | ---                                                                                                                                                     | ---                                                                    |
|          *%a*          | An abbreviated textual representation of the day                                                                                                        | *Sun* through *Sat*                                                    |
|          *%A*          | A full textual representation of the day                                                                                                                | *Sunday* through *Saturday*                                            |
|          *%d*          | Two-digit day of the month (with leading zeros)                                                                                                         | *01* to *31*                                                           |
|          *%e*          | Day of the month, with a space preceding single digits. Not implemented as described on Windows. See below for more information.                        | *1* to *31*                                                            |
|          *%j*          | Day of the year, 3 digits with leading zeros                                                                                                            | *001* to *366*                                                         |
|          *%u*          | ISO-8601 numeric representation of the day of the week                                                                                                  | *1* (for Monday) through *7* (for Sunday)                              |
|          *%w*          | Numeric representation of the day of the week                                                                                                           | *0* (for Sunday) through *6* (for Saturday)                            |
|         *Week*         | ---                                                                                                                                                     | ---                                                                    |
|          *%U*          | Week number of the given year, starting with the first Sunday as the first week                                                                         | *13* (for the 13th full week of the year)                              |
|          *%V*          | ISO-8601:1988 week number of the given year, starting with the first week of the year with at least 4 weekdays, with Monday being the start of the week | *01* through *53* (where 53 accounts for an overlapping week)          |
|          *%W*          | A numeric representation of the week of the year, starting with the first Monday as the first week                                                      | *46* (for the 46th week of the year beginning with a Monday)           |
|         *Month*        | ---                                                                                                                                                     | ---                                                                    |
|          *%b*          | Abbreviated month name, based on the locale                                                                                                             | *Jan* through *Dec*                                                    |
|          *%B*          | Full month name, based on the locale                                                                                                                    | *January* through *December*                                           |
|          *%h*          | Abbreviated month name, based on the locale (an alias of %b)                                                                                            | *Jan* through *Dec*                                                    |
|          *%m*          | Two digit representation of the month                                                                                                                   | *01* (for January) through *12* (for December)                         |
|         *Year*         | ---                                                                                                                                                     | ---                                                                    |
|          *%C*          | Two digit representation of the century (year divided by 100, truncated to an integer)                                                                  | *19* for the 20th Century                                              |
|          *%g*          | Two digit representation of the year going by ISO-8601:1988 standards (see %V)                                                                          | Example: *09* for the week of January 6, 2009                          |
|          *%G*          | The full four-digit version of %g                                                                                                                       | Example: *2008* for the week of January 3, 2009                        |
|          *%y*          | Two digit representation of the year                                                                                                                    | Example: *09* for 2009, *79* for 1979                                  |
|          *%Y*          | Four digit representation for the year                                                                                                                  | Example: *2038*                                                        |
|         *Time*         | ---                                                                                                                                                     | ---                                                                    |
|          *%H*          | Two digit representation of the hour in 24-hour format                                                                                                  | *00* through *23*                                                      |
|          *%k*          | Hour in 24-hour format, with a space preceding single digits                                                                                            | *0* through *23*                                                       |
|          *%I*          | Two digit representation of the hour in 12-hour format                                                                                                  | *01* through *12*                                                      |
|  *%l (lower-case 'L')* | Hour in 12-hour format, with a space preceding single digits                                                                                            | *1* through *12*                                                       |
|          *%M*          | Two digit representation of the minute                                                                                                                  | *00* through *59*                                                      |
|          *%p*          | UPPER-CASE 'AM' or 'PM' based on the given time                                                                                                         | Example: *AM* for 00:31, *PM* for 22:23                                |
|          *%P*          | lower-case 'am' or 'pm' based on the given time                                                                                                         | Example: *am* for 00:31, *pm* for 22:23                                |
|          *%r*          | Same as "%I:%M:%S %p"                                                                                                                                   | Example: *09:34:17 PM* for 21:34:17                                    |
|          *%R*          | Same as "%H:%M"                                                                                                                                         | Example: *00:35* for 12:35 AM, *16:44* for 4:44 PM                     |
|          *%S*          | Two digit representation of the second                                                                                                                  | *00* through *59*                                                      |
|          *%T*          | Same as "%H:%M:%S"                                                                                                                                      | Example: *21:34:17* for 09:34:17 PM                                    |
|          *%X*          | Preferred time representation based on locale, without the date                                                                                         | Example: *03:59:16* or *15:59:16*                                      |
|          *%z*          | The time zone offset. Not implemented as described on Windows. See below for more information.                                                          | Example: *-0500* for US Eastern Time                                   |
|          *%Z*          | The time zone abbreviation. Not implemented as described on Windows. See below for more information.                                                    | Example: *EST* for Eastern Time                                        |
| *Time and Date Stamps* | ---                                                                                                                                                     | ---                                                                    |
|          *%c*          | Preferred date and time stamp based on locale                                                                                                           | Example: *Tue Feb 5 00:45:10 2009* for February 5, 2009 at 12:45:10 AM |
|          *%D*          | Same as "%m/%d/%y"                                                                                                                                      | Example: *02/05/09* for February 5, 2009                               |
|          *%F*          | Same as "%Y-%m-%d" (commonly used in database datestamps)                                                                                               | Example: *2009-02-05* for February 5, 2009                             |
|          *%s*          | Unix Epoch Time timestamp (same as the <span class="function">time</span> function)                                                                     | Example: *305815200* for September 10, 1979 08:40:00 AM                |
|          *%x*          | Preferred date representation based on locale, without the time                                                                                         | Example: *02/05/09* for February 5, 2009                               |
|     *Miscellaneous*    | ---                                                                                                                                                     | ---                                                                    |
|          *%n*          | A newline character ("\\n")                                                                                                                             | ---                                                                    |
|          *%t*          | A Tab character ("\\t")                                                                                                                                 | ---                                                                    |
|          *%%*          | A literal percentage character ("%")                                                                                                                    | ---                                                                    |

Maximum length of this parameter is 1023 characters.

**Warning**
Contrary to ISO-9899:1999, Sun Solaris starts with Sunday as 1. As a
result, *%u* may not function as described in this manual.

**Warning**
*Windows only:*

The *%e* modifier is not supported in the Windows implementation of this
function. To achieve this value, the *%\#d* modifier can be used
instead. The example below illustrates how to write a cross platform
compatible function.

The *%z* and *%Z* modifiers both return the time zone name instead of
the offset or abbreviation.

**Warning**
*macOS only:* The *%P* modifier is not supported in the macOS
implementation of this function.

`timestamp`  
The optional `timestamp` parameter is an <span class="type">int</span>
Unix timestamp that defaults to the current local time if a `timestamp`
is not given. In other words, it defaults to the value of <span
class="function">time</span>.

### Return Values

Returns a string formatted according `format` using the given
`timestamp` or the current local time if no timestamp is given. Month
and weekday names and other language-dependent strings respect the
current locale set with <span class="function">setlocale</span>.

### Errors/Exceptions

Every call to a date/time function will generate a **`E_NOTICE`** if the
time zone is not valid, and/or a **`E_STRICT`** or **`E_WARNING`**
message if using the system settings or the `TZ` environment variable.
See also <span class="function">date\_default\_timezone\_set</span>

As the output is dependent upon the underlying C library, some
conversion specifiers are not supported. On Windows, supplying unknown
conversion specifiers will result in 5 **`E_WARNING`** messages and
return **`FALSE`**. On other operating systems you may not get any
**`E_WARNING`** messages and the output may contain the conversion
specifiers unconverted.

### Examples

This example will work if you have the respective locales installed in
your system.

**Example \#1 <span class="function">strftime</span> locale examples**

``` php
<?php
setlocale(LC_TIME, "C");
echo strftime("%A");
setlocale(LC_TIME, "fi_FI");
echo strftime(" in Finnish is %A,");
setlocale(LC_TIME, "fr_FR");
echo strftime(" in French %A and");
setlocale(LC_TIME, "de_DE");
echo strftime(" in German %A.\n");
?>
```

**Example \#2 ISO 8601:1988 week number example**

``` php
<?php
/*     December 2002 / January 2003
ISOWk  M   Tu  W   Thu F   Sa  Su
----- ----------------------------
51     16  17  18  19  20  21  22
52     23  24  25  26  27  28  29
1      30  31   1   2   3   4   5
2       6   7   8   9  10  11  12
3      13  14  15  16  17  18  19   */

// Outputs: 12/28/2002 - %V,%G,%Y = 52,2002,2002
echo "12/28/2002 - %V,%G,%Y = " . strftime("%V,%G,%Y", strtotime("12/28/2002")) . "\n";

// Outputs: 12/30/2002 - %V,%G,%Y = 1,2003,2002
echo "12/30/2002 - %V,%G,%Y = " . strftime("%V,%G,%Y", strtotime("12/30/2002")) . "\n";

// Outputs: 1/3/2003 - %V,%G,%Y = 1,2003,2003
echo "1/3/2003 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("1/3/2003")) . "\n";

// Outputs: 1/10/2003 - %V,%G,%Y = 2,2003,2003
echo "1/10/2003 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("1/10/2003")) . "\n";



/*     December 2004 / January 2005
ISOWk  M   Tu  W   Thu F   Sa  Su
----- ----------------------------
51     13  14  15  16  17  18  19
52     20  21  22  23  24  25  26
53     27  28  29  30  31   1   2
1       3   4   5   6   7   8   9
2      10  11  12  13  14  15  16   */

// Outputs: 12/23/2004 - %V,%G,%Y = 52,2004,2004
echo "12/23/2004 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("12/23/2004")) . "\n";

// Outputs: 12/31/2004 - %V,%G,%Y = 53,2004,2004
echo "12/31/2004 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("12/31/2004")) . "\n";

// Outputs: 1/2/2005 - %V,%G,%Y = 53,2004,2005
echo "1/2/2005 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("1/2/2005")) . "\n";

// Outputs: 1/3/2005 - %V,%G,%Y = 1,2005,2005
echo "1/3/2005 - %V,%G,%Y = " . strftime("%V,%G,%Y",strtotime("1/3/2005")) . "\n";

?>
```

**Example \#3 Cross platform compatible example using the *%e*
modifier**

``` php
<?php

// Jan 1: results in: '%e%1%' (%%, e, %%, %e, %%)
$format = '%%e%%%e%%';

// Check for Windows to find and replace the %e 
// modifier correctly
if (strtoupper(substr(PHP_OS, 0, 3)) == 'WIN') {
    $format = preg_replace('#(?<!%)((?:%%)*)%e#', '\1%#d', $format);
}

echo strftime($format);
?>
```

**Example \#4 Display all known and unknown formats.**

``` php
<?php
// Describe the formats.
$strftimeFormats = array(
    'A' => 'A full textual representation of the day',
    'B' => 'Full month name, based on the locale',
    'C' => 'Two digit representation of the century (year divided by 100, truncated to an integer)',
    'D' => 'Same as "%m/%d/%y"',
    'E' => '',
    'F' => 'Same as "%Y-%m-%d"',
    'G' => 'The full four-digit version of %g',
    'H' => 'Two digit representation of the hour in 24-hour format',
    'I' => 'Two digit representation of the hour in 12-hour format',
    'J' => '',
    'K' => '',
    'L' => '',
    'M' => 'Two digit representation of the minute',
    'N' => '',
    'O' => '',
    'P' => 'lower-case "am" or "pm" based on the given time',
    'Q' => '',
    'R' => 'Same as "%H:%M"',
    'S' => 'Two digit representation of the second',
    'T' => 'Same as "%H:%M:%S"',
    'U' => 'Week number of the given year, starting with the first Sunday as the first week',
    'V' => 'ISO-8601:1988 week number of the given year, starting with the first week of the year with at least 4 weekdays, with Monday being the start of the week',
    'W' => 'A numeric representation of the week of the year, starting with the first Monday as the first week',
    'X' => 'Preferred time representation based on locale, without the date',
    'Y' => 'Four digit representation for the year',
    'Z' => 'The time zone offset/abbreviation option NOT given by %z (depends on operating system)',
    'a' => 'An abbreviated textual representation of the day',
    'b' => 'Abbreviated month name, based on the locale',
    'c' => 'Preferred date and time stamp based on local',
    'd' => 'Two-digit day of the month (with leading zeros)',
    'e' => 'Day of the month, with a space preceding single digits',
    'f' => '',
    'g' => 'Two digit representation of the year going by ISO-8601:1988 standards (see %V)',
    'h' => 'Abbreviated month name, based on the locale (an alias of %b)',
    'i' => '',
    'j' => 'Day of the year, 3 digits with leading zeros',
    'k' => 'Hour in 24-hour format, with a space preceding single digits',
    'l' => 'Hour in 12-hour format, with a space preceding single digits',
    'm' => 'Two digit representation of the month',
    'n' => 'A newline character ("\n")',
    'o' => '',
    'p' => 'UPPER-CASE "AM" or "PM" based on the given time',
    'q' => '',
    'r' => 'Same as "%I:%M:%S %p"',
    's' => 'Unix Epoch Time timestamp',
    't' => 'A Tab character ("\t")',
    'u' => 'ISO-8601 numeric representation of the day of the week',
    'v' => '',
    'w' => 'Numeric representation of the day of the week',
    'x' => 'Preferred date representation based on locale, without the time',
    'y' => 'Two digit representation of the year',
    'z' => 'Either the time zone offset from UTC or the abbreviation (depends on operating system)',
    '%' => 'A literal percentage character ("%")',
);

// Results.
$strftimeValues = array();

// Evaluate the formats whilst suppressing any errors.
foreach($strftimeFormats as $format => $description){
    if (False !== ($value = @strftime("%{$format}"))){
        $strftimeValues[$format] = $value;
    }
}

// Find the longest value.
$maxValueLength = 2 + max(array_map('strlen', $strftimeValues));

// Report known formats.
foreach($strftimeValues as $format => $value){
    echo "Known format   : '{$format}' = ", str_pad("'{$value}'", $maxValueLength), " ( {$strftimeFormats[$format]} )\n";
}

// Report unknown formats.
foreach(array_diff_key($strftimeFormats, $strftimeValues) as $format => $description){
    echo "Unknown format : '{$format}'   ", str_pad(' ', $maxValueLength), ($description ? " ( {$description} )" : ''), "\n";
}
?>
```

The above example will output something similar to:

    Known format   : 'A' = 'Friday'            ( A full textual representation of the day )
    Known format   : 'B' = 'December'          ( Full month name, based on the locale )
    Known format   : 'H' = '11'                ( Two digit representation of the hour in 24-hour format )
    Known format   : 'I' = '11'                ( Two digit representation of the hour in 12-hour format )
    Known format   : 'M' = '24'                ( Two digit representation of the minute )
    Known format   : 'S' = '44'                ( Two digit representation of the second )
    Known format   : 'U' = '48'                ( Week number of the given year, starting with the first Sunday as the first week )
    Known format   : 'W' = '48'                ( A numeric representation of the week of the year, starting with the first Monday as the first week )
    Known format   : 'X' = '11:24:44'          ( Preferred time representation based on locale, without the date )
    Known format   : 'Y' = '2010'              ( Four digit representation for the year )
    Known format   : 'Z' = 'GMT Standard Time' ( The time zone offset/abbreviation option NOT given by %z (depends on operating system) )
    Known format   : 'a' = 'Fri'               ( An abbreviated textual representation of the day )
    Known format   : 'b' = 'Dec'               ( Abbreviated month name, based on the locale )
    Known format   : 'c' = '12/03/10 11:24:44' ( Preferred date and time stamp based on local )
    Known format   : 'd' = '03'                ( Two-digit day of the month (with leading zeros) )
    Known format   : 'j' = '337'               ( Day of the year, 3 digits with leading zeros )
    Known format   : 'm' = '12'                ( Two digit representation of the month )
    Known format   : 'p' = 'AM'                ( UPPER-CASE "AM" or "PM" based on the given time )
    Known format   : 'w' = '5'                 ( Numeric representation of the day of the week )
    Known format   : 'x' = '12/03/10'          ( Preferred date representation based on locale, without the time )
    Known format   : 'y' = '10'                ( Two digit representation of the year )
    Known format   : 'z' = 'GMT Standard Time' ( Either the time zone offset from UTC or the abbreviation (depends on operating system) )
    Known format   : '%' = '%'                 ( A literal percentage character ("%") )
    Unknown format : 'C'                       ( Two digit representation of the century (year divided by 100, truncated to an integer) )
    Unknown format : 'D'                       ( Same as "%m/%d/%y" )
    Unknown format : 'E'
    Unknown format : 'F'                       ( Same as "%Y-%m-%d" )
    Unknown format : 'G'                       ( The full four-digit version of %g )
    Unknown format : 'J'
    Unknown format : 'K'
    Unknown format : 'L'
    Unknown format : 'N'
    Unknown format : 'O'
    Unknown format : 'P'                       ( lower-case "am" or "pm" based on the given time )
    Unknown format : 'Q'
    Unknown format : 'R'                       ( Same as "%H:%M" )
    Unknown format : 'T'                       ( Same as "%H:%M:%S" )
    Unknown format : 'V'                       ( ISO-8601:1988 week number of the given year, starting with the first week of the year with at least 4 weekdays, with Monday being the start of the week )
    Unknown format : 'e'                       ( Day of the month, with a space preceding single digits )
    Unknown format : 'f'
    Unknown format : 'g'                       ( Two digit representation of the year going by ISO-8601:1988 standards (see %V) )
    Unknown format : 'h'                       ( Abbreviated month name, based on the locale (an alias of %b) )
    Unknown format : 'i'
    Unknown format : 'k'                       ( Hour in 24-hour format, with a space preceding single digits )
    Unknown format : 'l'                       ( Hour in 12-hour format, with a space preceding single digits )
    Unknown format : 'n'                       ( A newline character ("\n") )
    Unknown format : 'o'
    Unknown format : 'q'
    Unknown format : 'r'                       ( Same as "%I:%M:%S %p" )
    Unknown format : 's'                       ( Unix Epoch Time timestamp )
    Unknown format : 't'                       ( A Tab character ("\t") )
    Unknown format : 'u'                       ( ISO-8601 numeric representation of the day of the week )
    Unknown format : 'v'

### Notes

> **Note**: <span class="simpara"> %G and %V, which are based on ISO
> 8601:1988 week numbers can give unexpected (albeit correct) results if
> the numbering system is not thoroughly understood. See %V examples in
> this manual page. </span>

### See Also

-   <a href="http://strftime.net/" class="link external">» Online strftime() format design tool</a>
-   <span class="function">setlocale</span>
-   <span class="function">mktime</span>
-   <span class="function">strptime</span>
-   <span class="function">gmstrftime</span>
-   <a href="http://www.opengroup.org/onlinepubs/007908799/xsh/strftime.html" class="link external">» Open Group specification of <span class="function">strftime</span></a>

strptime
========

Parse a time/date generated with <span class="function">strftime</span>

### Description

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">strptime</span> ( <span class="methodparam"><span
class="type">string</span> `$date`</span> , <span
class="methodparam"><span class="type">string</span> `$format`</span> )

<span class="function">strptime</span> returns an array with the `date`
parsed, or **`FALSE`** on error.

Month and weekday names and other language dependent strings respect the
current locale set with <span class="function">setlocale</span>
(**`LC_TIME`**).

### Parameters

`date` (<span class="type">string</span>)  
The string to parse (e.g. returned from <span
class="function">strftime</span>).

`format` (<span class="type">string</span>)  
The format used in `date` (e.g. the same as used in <span
class="function">strftime</span>). Note that some of the format options
available to <span class="function">strftime</span> may not have any
effect within <span class="function">strptime</span>; the exact subset
that are supported will vary based on the operating system and C library
in use.

For more information about the format options, read the <span
class="function">strftime</span> page.

### Return Values

Returns an array or **`FALSE`** on failure.

| parameters   | Description                                                           |
|--------------|-----------------------------------------------------------------------|
| *"tm\_sec"*  | Seconds after the minute (0-61)                                       |
| *"tm\_min"*  | Minutes after the hour (0-59)                                         |
| *"tm\_hour"* | Hour since midnight (0-23)                                            |
| *"tm\_mday"* | Day of the month (1-31)                                               |
| *"tm\_mon"*  | Months since January (0-11)                                           |
| *"tm\_year"* | Years since 1900                                                      |
| *"tm\_wday"* | Days since Sunday (0-6)                                               |
| *"tm\_yday"* | Days since January 1 (0-365)                                          |
| *"unparsed"* | the `date` part which was not recognized using the specified `format` |

### Examples

**Example \#1 <span class="function">strptime</span> example**

``` php
<?php
$format = '%d/%m/%Y %H:%M:%S';
$strf = strftime($format);

echo "$strf\n";

print_r(strptime($strf, $format));
?>
```

The above example will output something similar to:

    03/10/2004 15:54:19

    Array
    (
        [tm_sec] => 19
        [tm_min] => 54
        [tm_hour] => 15
        [tm_mday] => 3
        [tm_mon] => 9
        [tm_year] => 104
        [tm_wday] => 0
        [tm_yday] => 276
        [unparsed] =>
    )

### Notes

> **Note**: <span class="simpara">This function is not implemented on
> Windows platforms.</span>

> **Note**:
>
> Internally, this function calls the *strptime()* function provided by
> the system's C library. This function can exhibit noticeably different
> behaviour across different operating systems. The use of <span
> class="function">date\_parse\_from\_format</span>, which does not
> suffer from these issues, is recommended on PHP 5.3.0 and later.

> **Note**:
>
> *"tm\_sec"* includes any leap seconds (currently upto 2 a year). For
> more information on leap seconds, see the
> <a href="http://en.wikipedia.org/wiki/Leap_second" class="link external">» Wikipedia article on leap seconds</a>.

> **Note**:
>
> Prior to PHP 5.2.0, this function could return undefined behaviour.
> Notably, the *"tm\_sec"*, *"tm\_min"* and *"tm\_hour"* entries would
> return undefined values.

### See Also

-   <span class="function">checkdate</span>
-   <span class="function">strftime</span>
-   <span class="function">date\_parse\_from\_format</span>
-   <span class="function">DateTime::createFromFormat</span>

strtotime
=========

Parse about any English textual datetime description into a Unix
timestamp

### Description

<span class="type">int</span> <span class="methodname">strtotime</span>
( <span class="methodparam"><span class="type">string</span>
`$datetime`</span> \[, <span class="methodparam"><span
class="type">int</span> `$now`<span class="initializer"> =
time()</span></span> \] )

The function expects to be given a string containing an English date
format and will try to parse that format into a Unix timestamp (the
number of seconds since January 1 1970 00:00:00 UTC), relative to the
timestamp given in `now`, or the current time if `now` is not supplied.

**Warning**

The Unix timestamp that this function returns does not contain
information about time zones. In order to do calculations with date/time
information, you should use the more capable <span
class="classname">DateTimeImmutable</span>.

Each parameter of this function uses the default time zone unless a time
zone is specified in that parameter. Be careful not to use different
time zones in each parameter unless that is intended. See <span
class="function">date\_default\_timezone\_get</span> on the various ways
to define the default time zone.

### Parameters

`datetime`  
A date/time string. Valid formats are explained in
<a href="/datetime/formats.html" class="link">Date and Time Formats</a>.

`now`  
The timestamp which is used as a base for the calculation of relative
dates.

### Return Values

Returns a timestamp on success, **`FALSE`** otherwise.

### Errors/Exceptions

Every call to a date/time function will generate a **`E_NOTICE`** if the
time zone is not valid, and/or a **`E_STRICT`** or **`E_WARNING`**
message if using the system settings or the `TZ` environment variable.
See also <span class="function">date\_default\_timezone\_set</span>

### Examples

**Example \#1 A <span class="function">strtotime</span> example**

``` php
<?php
echo strtotime("now"), "\n";
echo strtotime("10 September 2000"), "\n";
echo strtotime("+1 day"), "\n";
echo strtotime("+1 week"), "\n";
echo strtotime("+1 week 2 days 4 hours 2 seconds"), "\n";
echo strtotime("next Thursday"), "\n";
echo strtotime("last Monday"), "\n";
?>
```

**Example \#2 Checking for failure**

``` php
<?php
$str = 'Not Good';

// previous to PHP 5.1.0 you would compare with -1, instead of false
if (($timestamp = strtotime($str)) === false) {
    echo "The string ($str) is bogus";
} else {
    echo "$str == " . date('l dS \o\f F Y h:i:s A', $timestamp);
}
?>
```

### Notes

> **Note**:
>
> If the number of the year is specified in a two digit format, the
> values between 00-69 are mapped to 2000-2069 and 70-99 to 1970-1999.
> See the notes below for possible differences on 32bit systems
> (possible dates might end on 2038-01-19 03:14:07).

> **Note**:
>
> The valid range of a timestamp is typically from Fri, 13 Dec 1901
> 20:45:54 UTC to Tue, 19 Jan 2038 03:14:07 UTC. (These are the dates
> that correspond to the minimum and maximum values for a 32-bit signed
> integer.)
>
> Prior to PHP 5.1.0, not all platforms support negative timestamps,
> therefore your date range may be limited to no earlier than the Unix
> epoch. This means that e.g. dates prior to Jan 1, 1970 will not work
> on Windows, some Linux distributions, and a few other operating
> systems.
>
> For 64-bit versions of PHP, the valid range of a timestamp is
> effectively infinite, as 64 bits can represent approximately 293
> billion years in either direction.

> **Note**:
>
> Dates in the *m/d/y* or *d-m-y* formats are disambiguated by looking
> at the separator between the various components: if the separator is a
> slash (*/*), then the American *m/d/y* is assumed; whereas if the
> separator is a dash (*-*) or a dot (*.*), then the European *d-m-y*
> format is assumed. If, however, the year is given in a two digit
> format and the separator is a dash (*-*), the date string is parsed as
> *y-m-d*.
>
> To avoid potential ambiguity, it's best to use ISO 8601 (*YYYY-MM-DD*)
> dates or <span class="methodname">DateTime::createFromFormat</span>
> when possible.

> **Note**:
>
> Using this function for mathematical operations is not advisable. It
> is better to use <span class="methodname">DateTime::add</span> and
> <span class="methodname">DateTime::sub</span> in PHP 5.3 and later, or
> <span class="methodname">DateTime::modify</span> in PHP 5.2.

### See Also

-   <a href="/datetime/formats.html" class="link">Date and Time Formats</a>
-   <span class="methodname">DateTime::createFromFormat</span>
-   <span class="function">checkdate</span>
-   <span class="function">strptime</span>

time
====

Return current Unix timestamp

### Description

<span class="type">int</span> <span class="methodname">time</span> (
<span class="methodparam">void</span> )

Returns the current time measured in the number of seconds since the
Unix Epoch (January 1 1970 00:00:00 GMT).

### Examples

**Example \#1 <span class="function">time</span> example**

``` php
<?php
$nextWeek = time() + (7 * 24 * 60 * 60);
                   // 7 days; 24 hours; 60 mins; 60 secs
echo 'Now:       '. date('Y-m-d') ."\n";
echo 'Next Week: '. date('Y-m-d', $nextWeek) ."\n";
// or using strtotime():
echo 'Next Week: '. date('Y-m-d', strtotime('+1 week')) ."\n";
?>
```

The above example will output something similar to:

    Now:       2005-03-30
    Next Week: 2005-04-06
    Next Week: 2005-04-06

### Notes

**Tip**

Timestamp of the start of the request is available in
`$_SERVER['REQUEST_TIME']` since PHP 5.1.

### See Also

-   <span class="function">date</span>
-   <span class="function">microtime</span>

timezone\_abbreviations\_list
=============================

Alias of <span class="methodname">DateTimeZone::listAbbreviations</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeZone::listAbbreviations</span>

timezone\_identifiers\_list
===========================

Alias of <span class="methodname">DateTimeZone::listIdentifiers</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeZone::listIdentifiers</span>

timezone\_location\_get
=======================

Alias of <span class="methodname">DateTimeZone::getLocation</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeZone::getLocation</span>

timezone\_name\_from\_abbr
==========================

Returns the timezone name from abbreviation

### Description

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">timezone\_name\_from\_abbr</span> ( <span
class="methodparam"><span class="type">string</span> `$abbr`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$utcOffset`<span class="initializer"> = -1</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$isDST`<span
class="initializer"> = -1</span></span> \]\] )

### Parameters

`abbr`  
Time zone abbreviation.

`utcOffset`  
Offset from GMT in seconds. Defaults to -1 which means that first found
time zone corresponding to `abbr` is returned. Otherwise exact offset is
searched and only if not found then the first time zone with any offset
is returned.

`isDST`  
Daylight saving time indicator. Defaults to -1, which means that whether
the time zone has daylight saving or not is not taken into consideration
when searching. If this is set to 1, then the `utcOffset` is assumed to
be an offset with daylight saving in effect; if 0, then `utcOffset` is
assumed to be an offset without daylight saving in effect. If `abbr`
doesn't exist then the time zone is searched solely by the `utcOffset`
and `isDST`.

### Return Values

Returns time zone name on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span class="function">timezone\_name\_from\_abbr</span>
example**

``` php
<?php
echo timezone_name_from_abbr("CET") . "\n";
echo timezone_name_from_abbr("", 3600, 0) . "\n";
?>
```

The above example will output something similar to:

    Europe/Berlin
    Europe/Paris

### See Also

-   <span class="function">timezone\_abbreviations\_list</span>

timezone\_name\_get
===================

Alias of <span class="methodname">DateTimeZone::getName</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeZone::getName</span>

timezone\_offset\_get
=====================

Alias of <span class="methodname">DateTimeZone::getOffset</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeZone::getOffset</span>

timezone\_open
==============

Alias of <span class="methodname">DateTimeZone::\_\_construct</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeZone::\_\_construct</span>

timezone\_transitions\_get
==========================

Alias of <span class="methodname">DateTimeZone::getTransitions</span>

### Description

This function is an alias of: <span
class="methodname">DateTimeZone::getTransitions</span>

timezone\_version\_get
======================

Gets the version of the timezonedb

### Description

<span class="type">string</span> <span
class="methodname">timezone\_version\_get</span> ( <span
class="methodparam">void</span> )

Returns the current version of the timezonedb.

### Return Values

Returns a <span class="type">string</span>.

### Examples

**Example \#1 Getting the timezonedb version**

``` php
<?php
echo timezone_version_get();
?>
```

The above example will output something similar to:

    2009.7

### See Also

-   <a href="/timezones.html" class="link">List of Supported Timezones</a>

**Table of Contents**

-   [checkdate](/ref/datetime.html#checkdate) — Validate a Gregorian
    date
-   [date\_add](/ref/datetime.html#date_add) — Alias of DateTime::add
-   [date\_create\_from\_format](/ref/datetime.html#date_create_from_format)
    — Alias of DateTime::createFromFormat
-   [date\_create\_immutable\_from\_format](/ref/datetime.html#date_create_immutable_from_format)
    — Alias of DateTimeImmutable::createFromFormat
-   [date\_create\_immutable](/ref/datetime.html#date_create_immutable)
    — Alias of DateTimeImmutable::\_\_construct
-   [date\_create](/ref/datetime.html#date_create) — Alias of
    DateTime::\_\_construct
-   [date\_date\_set](/ref/datetime.html#date_date_set) — Alias of
    DateTime::setDate
-   [date\_default\_timezone\_get](/ref/datetime.html#date_default_timezone_get)
    — Gets the default timezone used by all date/time functions in a
    script
-   [date\_default\_timezone\_set](/ref/datetime.html#date_default_timezone_set)
    — Sets the default timezone used by all date/time functions in a
    script
-   [date\_diff](/ref/datetime.html#date_diff) — Alias of DateTime::diff
-   [date\_format](/ref/datetime.html#date_format) — Alias of
    DateTime::format
-   [date\_get\_last\_errors](/ref/datetime.html#date_get_last_errors) —
    Alias of DateTime::getLastErrors
-   [date\_interval\_create\_from\_date\_string](/ref/datetime.html#date_interval_create_from_date_string)
    — Alias of DateInterval::createFromDateString
-   [date\_interval\_format](/ref/datetime.html#date_interval_format) —
    Alias of DateInterval::format
-   [date\_isodate\_set](/ref/datetime.html#date_isodate_set) — Alias of
    DateTime::setISODate
-   [date\_modify](/ref/datetime.html#date_modify) — Alias of
    DateTime::modify
-   [date\_offset\_get](/ref/datetime.html#date_offset_get) — Alias of
    DateTime::getOffset
-   [date\_parse\_from\_format](/ref/datetime.html#date_parse_from_format)
    — Get info about given date formatted according to the specified
    format
-   [date\_parse](/ref/datetime.html#date_parse) — Returns associative
    array with detailed info about given date/time
-   [date\_sub](/ref/datetime.html#date_sub) — Alias of DateTime::sub
-   [date\_sun\_info](/ref/datetime.html#date_sun_info) — Returns an
    array with information about sunset/sunrise and twilight begin/end
-   [date\_sunrise](/ref/datetime.html#date_sunrise) — Returns time of
    sunrise for a given day and location
-   [date\_sunset](/ref/datetime.html#date_sunset) — Returns time of
    sunset for a given day and location
-   [date\_time\_set](/ref/datetime.html#date_time_set) — Alias of
    DateTime::setTime
-   [date\_timestamp\_get](/ref/datetime.html#date_timestamp_get) —
    Alias of DateTime::getTimestamp
-   [date\_timestamp\_set](/ref/datetime.html#date_timestamp_set) —
    Alias of DateTime::setTimestamp
-   [date\_timezone\_get](/ref/datetime.html#date_timezone_get) — Alias
    of DateTime::getTimezone
-   [date\_timezone\_set](/ref/datetime.html#date_timezone_set) — Alias
    of DateTime::setTimezone
-   [date](/ref/datetime.html#date) — Format a local time/date
-   [getdate](/ref/datetime.html#getdate) — Get date/time information
-   [gettimeofday](/ref/datetime.html#gettimeofday) — Get current time
-   [gmdate](/ref/datetime.html#gmdate) — Format a GMT/UTC date/time
-   [gmmktime](/ref/datetime.html#gmmktime) — Get Unix timestamp for a
    GMT date
-   [gmstrftime](/ref/datetime.html#gmstrftime) — Format a GMT/UTC
    time/date according to locale settings
-   [idate](/ref/datetime.html#idate) — Format a local time/date as
    integer
-   [localtime](/ref/datetime.html#localtime) — Get the local time
-   [microtime](/ref/datetime.html#microtime) — Return current Unix
    timestamp with microseconds
-   [mktime](/ref/datetime.html#mktime) — Get Unix timestamp for a date
-   [strftime](/ref/datetime.html#strftime) — Format a local time/date
    according to locale settings
-   [strptime](/ref/datetime.html#strptime) — Parse a time/date
    generated with strftime
-   [strtotime](/ref/datetime.html#strtotime) — Parse about any English
    textual datetime description into a Unix timestamp
-   [time](/ref/datetime.html#time) — Return current Unix timestamp
-   [timezone\_abbreviations\_list](/ref/datetime.html#timezone_abbreviations_list)
    — Alias of DateTimeZone::listAbbreviations
-   [timezone\_identifiers\_list](/ref/datetime.html#timezone_identifiers_list)
    — Alias of DateTimeZone::listIdentifiers
-   [timezone\_location\_get](/ref/datetime.html#timezone_location_get)
    — Alias of DateTimeZone::getLocation
-   [timezone\_name\_from\_abbr](/ref/datetime.html#timezone_name_from_abbr)
    — Returns the timezone name from abbreviation
-   [timezone\_name\_get](/ref/datetime.html#timezone_name_get) — Alias
    of DateTimeZone::getName
-   [timezone\_offset\_get](/ref/datetime.html#timezone_offset_get) —
    Alias of DateTimeZone::getOffset
-   [timezone\_open](/ref/datetime.html#timezone_open) — Alias of
    DateTimeZone::\_\_construct
-   [timezone\_transitions\_get](/ref/datetime.html#timezone_transitions_get)
    — Alias of DateTimeZone::getTransitions
-   [timezone\_version\_get](/ref/datetime.html#timezone_version_get) —
    Gets the version of the timezonedb

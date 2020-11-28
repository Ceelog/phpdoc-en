Date and Time
=============

**Table of Contents**

-   [Introduction](/intro/datetime.html)
-   [Installing/Configuring](/datetime/setup.html)
    -   [Requirements](/datetime/setup.html#Requirements)
    -   [Installation](/datetime/setup.html#Installation)
    -   [Runtime
        Configuration](/datetime/setup.html#Runtime%20Configuration)
    -   [Resource Types](/datetime/setup.html#Resource%20Types)
-   [Predefined Constants](/datetime/constants.html)
-   [Examples](/datetime/examples.html)
    -   [Date/Time
        Arithmetic](/datetime/examples.html#Date/Time%20Arithmetic)
-   [DateTime](/class/datetime.html) — The DateTime class
    -   [DateTime::add](/class/datetime.html#DateTime::add) — Adds an
        amount of days, months, years, hours, minutes and seconds to a
        DateTime object
    -   [DateTime::\_\_construct](/class/datetime.html#DateTime::__construct)
        — Returns new DateTime object
    -   [DateTime::createFromFormat](/class/datetime.html#DateTime::createFromFormat)
        — Parses a time string according to a specified format
    -   [DateTime::createFromImmutable](/class/datetime.html#DateTime::createFromImmutable)
        — Returns new DateTime object encapsulating the given
        DateTimeImmutable object
    -   [DateTime::getLastErrors](/class/datetime.html#DateTime::getLastErrors)
        — Returns the warnings and errors
    -   [DateTime::modify](/class/datetime.html#DateTime::modify) —
        Alters the timestamp
    -   [DateTime::\_\_set\_state](/class/datetime.html#DateTime::__set_state)
        — The \_\_set\_state handler
    -   [DateTime::setDate](/class/datetime.html#DateTime::setDate) —
        Sets the date
    -   [DateTime::setISODate](/class/datetime.html#DateTime::setISODate)
        — Sets the ISO date
    -   [DateTime::setTime](/class/datetime.html#DateTime::setTime) —
        Sets the time
    -   [DateTime::setTimestamp](/class/datetime.html#DateTime::setTimestamp)
        — Sets the date and time based on an Unix timestamp
    -   [DateTime::setTimezone](/class/datetime.html#DateTime::setTimezone)
        — Sets the time zone for the DateTime object
    -   [DateTime::sub](/class/datetime.html#DateTime::sub) — Subtracts
        an amount of days, months, years, hours, minutes and seconds
        from a DateTime object
-   [DateTimeImmutable](/class/datetimeimmutable.html) — The
    DateTimeImmutable class
    -   [DateTimeImmutable::add](/class/datetimeimmutable.html#DateTimeImmutable::add)
        — Adds an amount of days, months, years, hours, minutes and
        seconds
    -   [DateTimeImmutable::\_\_construct](/class/datetimeimmutable.html#DateTimeImmutable::__construct)
        — Returns new DateTimeImmutable object
    -   [DateTimeImmutable::createFromFormat](/class/datetimeimmutable.html#DateTimeImmutable::createFromFormat)
        — Parses a time string according to a specified format
    -   [DateTimeImmutable::createFromMutable](/class/datetimeimmutable.html#DateTimeImmutable::createFromMutable)
        — Returns new DateTimeImmutable object encapsulating the given
        DateTime object
    -   [DateTimeImmutable::getLastErrors](/class/datetimeimmutable.html#DateTimeImmutable::getLastErrors)
        — Returns the warnings and errors
    -   [DateTimeImmutable::modify](/class/datetimeimmutable.html#DateTimeImmutable::modify)
        — Creates a new object with modified timestamp
    -   [DateTimeImmutable::\_\_set\_state](/class/datetimeimmutable.html#DateTimeImmutable::__set_state)
        — The \_\_set\_state handler
    -   [DateTimeImmutable::setDate](/class/datetimeimmutable.html#DateTimeImmutable::setDate)
        — Sets the date
    -   [DateTimeImmutable::setISODate](/class/datetimeimmutable.html#DateTimeImmutable::setISODate)
        — Sets the ISO date
    -   [DateTimeImmutable::setTime](/class/datetimeimmutable.html#DateTimeImmutable::setTime)
        — Sets the time
    -   [DateTimeImmutable::setTimestamp](/class/datetimeimmutable.html#DateTimeImmutable::setTimestamp)
        — Sets the date and time based on a Unix timestamp
    -   [DateTimeImmutable::setTimezone](/class/datetimeimmutable.html#DateTimeImmutable::setTimezone)
        — Sets the time zone
    -   [DateTimeImmutable::sub](/class/datetimeimmutable.html#DateTimeImmutable::sub)
        — Subtracts an amount of days, months, years, hours, minutes and
        seconds
-   [DateTimeInterface](/class/datetimeinterface.html) — The
    DateTimeInterface interface
    -   [DateTime::diff](/class/datetimeinterface.html#DateTime::diff) —
        Returns the difference between two DateTime objects
    -   [DateTime::format](/class/datetimeinterface.html#DateTime::format)
        — Returns date formatted according to given format
    -   [DateTime::getOffset](/class/datetimeinterface.html#DateTime::getOffset)
        — Returns the timezone offset
    -   [DateTime::getTimestamp](/class/datetimeinterface.html#DateTime::getTimestamp)
        — Gets the Unix timestamp
    -   [DateTime::getTimezone](/class/datetimeinterface.html#DateTime::getTimezone)
        — Return time zone relative to given DateTime
    -   [DateTime::\_\_wakeup](/class/datetimeinterface.html#DateTime::__wakeup)
        — The \_\_wakeup handler
-   [DateTimeZone](/class/datetimezone.html) — The DateTimeZone class
    -   [DateTimeZone::\_\_construct](/class/datetimezone.html#DateTimeZone::__construct)
        — Creates new DateTimeZone object
    -   [DateTimeZone::getLocation](/class/datetimezone.html#DateTimeZone::getLocation)
        — Returns location information for a timezone
    -   [DateTimeZone::getName](/class/datetimezone.html#DateTimeZone::getName)
        — Returns the name of the timezone
    -   [DateTimeZone::getOffset](/class/datetimezone.html#DateTimeZone::getOffset)
        — Returns the timezone offset from GMT
    -   [DateTimeZone::getTransitions](/class/datetimezone.html#DateTimeZone::getTransitions)
        — Returns all transitions for the timezone
    -   [DateTimeZone::listAbbreviations](/class/datetimezone.html#DateTimeZone::listAbbreviations)
        — Returns associative array containing dst, offset and the
        timezone name
    -   [DateTimeZone::listIdentifiers](/class/datetimezone.html#DateTimeZone::listIdentifiers)
        — Returns a numerically indexed array containing all defined
        timezone identifiers
-   [DateInterval](/class/dateinterval.html) — The DateInterval class
    -   [DateInterval::\_\_construct](/class/dateinterval.html#DateInterval::__construct)
        — Creates a new DateInterval object
    -   [DateInterval::createFromDateString](/class/dateinterval.html#DateInterval::createFromDateString)
        — Sets up a DateInterval from the relative parts of the string
    -   [DateInterval::format](/class/dateinterval.html#DateInterval::format)
        — Formats the interval
-   [DatePeriod](/class/dateperiod.html) — The DatePeriod class
    -   [DatePeriod::\_\_construct](/class/dateperiod.html#DatePeriod::__construct)
        — Creates a new DatePeriod object
    -   [DatePeriod::getDateInterval](/class/dateperiod.html#DatePeriod::getDateInterval)
        — Gets the interval
    -   [DatePeriod::getEndDate](/class/dateperiod.html#DatePeriod::getEndDate)
        — Gets the end date
    -   [DatePeriod::getRecurrences](/class/dateperiod.html#DatePeriod::getRecurrences)
        — Gets the number of recurrences
    -   [DatePeriod::getStartDate](/class/dateperiod.html#DatePeriod::getStartDate)
        — Gets the start date
-   [Date/Time Functions](/ref/datetime.html)
    -   [checkdate](/ref/datetime.html#checkdate) — Validate a Gregorian
        date
    -   [date\_add](/ref/datetime.html#date_add) — Alias of
        DateTime::add
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
    -   [date\_diff](/ref/datetime.html#date_diff) — Alias of
        DateTime::diff
    -   [date\_format](/ref/datetime.html#date_format) — Alias of
        DateTime::format
    -   [date\_get\_last\_errors](/ref/datetime.html#date_get_last_errors)
        — Alias of DateTime::getLastErrors
    -   [date\_interval\_create\_from\_date\_string](/ref/datetime.html#date_interval_create_from_date_string)
        — Alias of DateInterval::createFromDateString
    -   [date\_interval\_format](/ref/datetime.html#date_interval_format)
        — Alias of DateInterval::format
    -   [date\_isodate\_set](/ref/datetime.html#date_isodate_set) —
        Alias of DateTime::setISODate
    -   [date\_modify](/ref/datetime.html#date_modify) — Alias of
        DateTime::modify
    -   [date\_offset\_get](/ref/datetime.html#date_offset_get) — Alias
        of DateTime::getOffset
    -   [date\_parse\_from\_format](/ref/datetime.html#date_parse_from_format)
        — Get info about given date formatted according to the specified
        format
    -   [date\_parse](/ref/datetime.html#date_parse) — Returns
        associative array with detailed info about given date/time
    -   [date\_sub](/ref/datetime.html#date_sub) — Alias of
        DateTime::sub
    -   [date\_sun\_info](/ref/datetime.html#date_sun_info) — Returns an
        array with information about sunset/sunrise and twilight
        begin/end
    -   [date\_sunrise](/ref/datetime.html#date_sunrise) — Returns time
        of sunrise for a given day and location
    -   [date\_sunset](/ref/datetime.html#date_sunset) — Returns time of
        sunset for a given day and location
    -   [date\_time\_set](/ref/datetime.html#date_time_set) — Alias of
        DateTime::setTime
    -   [date\_timestamp\_get](/ref/datetime.html#date_timestamp_get) —
        Alias of DateTime::getTimestamp
    -   [date\_timestamp\_set](/ref/datetime.html#date_timestamp_set) —
        Alias of DateTime::setTimestamp
    -   [date\_timezone\_get](/ref/datetime.html#date_timezone_get) —
        Alias of DateTime::getTimezone
    -   [date\_timezone\_set](/ref/datetime.html#date_timezone_set) —
        Alias of DateTime::setTimezone
    -   [date](/ref/datetime.html#date) — Format a local time/date
    -   [getdate](/ref/datetime.html#getdate) — Get date/time
        information
    -   [gettimeofday](/ref/datetime.html#gettimeofday) — Get current
        time
    -   [gmdate](/ref/datetime.html#gmdate) — Format a GMT/UTC date/time
    -   [gmmktime](/ref/datetime.html#gmmktime) — Get Unix timestamp for
        a GMT date
    -   [gmstrftime](/ref/datetime.html#gmstrftime) — Format a GMT/UTC
        time/date according to locale settings
    -   [idate](/ref/datetime.html#idate) — Format a local time/date as
        integer
    -   [localtime](/ref/datetime.html#localtime) — Get the local time
    -   [microtime](/ref/datetime.html#microtime) — Return current Unix
        timestamp with microseconds
    -   [mktime](/ref/datetime.html#mktime) — Get Unix timestamp for a
        date
    -   [strftime](/ref/datetime.html#strftime) — Format a local
        time/date according to locale settings
    -   [strptime](/ref/datetime.html#strptime) — Parse a time/date
        generated with strftime
    -   [strtotime](/ref/datetime.html#strtotime) — Parse about any
        English textual datetime description into a Unix timestamp
    -   [time](/ref/datetime.html#time) — Return current Unix timestamp
    -   [timezone\_abbreviations\_list](/ref/datetime.html#timezone_abbreviations_list)
        — Alias of DateTimeZone::listAbbreviations
    -   [timezone\_identifiers\_list](/ref/datetime.html#timezone_identifiers_list)
        — Alias of DateTimeZone::listIdentifiers
    -   [timezone\_location\_get](/ref/datetime.html#timezone_location_get)
        — Alias of DateTimeZone::getLocation
    -   [timezone\_name\_from\_abbr](/ref/datetime.html#timezone_name_from_abbr)
        — Returns the timezone name from abbreviation
    -   [timezone\_name\_get](/ref/datetime.html#timezone_name_get) —
        Alias of DateTimeZone::getName
    -   [timezone\_offset\_get](/ref/datetime.html#timezone_offset_get)
        — Alias of DateTimeZone::getOffset
    -   [timezone\_open](/ref/datetime.html#timezone_open) — Alias of
        DateTimeZone::\_\_construct
    -   [timezone\_transitions\_get](/ref/datetime.html#timezone_transitions_get)
        — Alias of DateTimeZone::getTransitions
    -   [timezone\_version\_get](/ref/datetime.html#timezone_version_get)
        — Gets the version of the timezonedb
-   [Supported Date and Time Formats](/datetime/formats.html)
    -   [Time Formats](/datetime/formats.html#Time%20Formats)
    -   [Date Formats](/datetime/formats.html#Date%20Formats)
    -   [Compound Formats](/datetime/formats.html#Compound%20Formats)
    -   [Relative Formats](/datetime/formats.html#Relative%20Formats)
-   [List of Supported Timezones](/timezones.html)
    -   [Africa](/timezones.html#Africa)
    -   [America](/timezones.html#America)
    -   [Antarctica](/timezones.html#Antarctica)
    -   [Arctic](/timezones.html#Arctic)
    -   [Asia](/timezones.html#Asia)
    -   [Atlantic](/timezones.html#Atlantic)
    -   [Australia](/timezones.html#Australia)
    -   [Europe](/timezones.html#Europe)
    -   [Indian](/timezones.html#Indian)
    -   [Pacific](/timezones.html#Pacific)
    -   [Others](/timezones.html#Others)

Introduction
------------

This class behaves the same as <span
class="classname">DateTimeImmutable</span> except objects are modified
itself when modification methods such as <span
class="function">DateTime::modify</span> are called.

Class synopsis
--------------

**DateTime**

<span class="ooclass"> class **DateTime** </span> <span
class="oointerface">implements <span
class="interfacename">DateTimeInterface</span> </span> {

/\* Inherited constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::ATOM` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::COOKIE` <span class="initializer"> = "l, d-M-Y H:i:s
T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::ISO8601` <span class="initializer"> =
"Y-m-d\\TH:i:sO"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC822` <span class="initializer"> = "D, d M y H:i:s
O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC850` <span class="initializer"> = "l, d-M-y H:i:s
T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC1036` <span class="initializer"> = "D, d M y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC1123` <span class="initializer"> = "D, d M Y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC7231` <span class="initializer"> = "D, d M Y
H:i:s \\G\\M\\T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC2822` <span class="initializer"> = "D, d M Y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC3339` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC3339_EXTENDED` <span class="initializer"> =
"Y-m-d\\TH:i:s.vP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RSS` <span class="initializer"> = "D, d M Y H:i:s
O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::W3C` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$datetime`<span
class="initializer"> = "now"</span></span> \[, <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`<span class="initializer"> = **`NULL`**</span></span> \]\] )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">add</span> ( <span class="methodparam"><span
class="type">DateInterval</span> `$interval`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">DateTime</span><span class="type">false</span></span> <span
class="methodname">createFromFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> ,
<span class="methodparam"><span class="type">string</span>
`$datetime`</span> \[, <span class="methodparam"><span
class="type">DateTimeZone</span> `$timezone`</span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">DateTime</span> <span
class="methodname">createFromImmutable</span> ( <span
class="methodparam"><span class="type">DateTimeImmutable</span>
`$object`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getLastErrors</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">modify</span> ( <span class="methodparam"><span
class="type">string</span> `$modifier`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">DateTime</span> <span
class="methodname">\_\_set\_state</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">setDate</span> ( <span
class="methodparam"><span class="type">int</span> `$year`</span> , <span
class="methodparam"><span class="type">int</span> `$month`</span> ,
<span class="methodparam"><span class="type">int</span> `$day`</span> )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">setISODate</span> ( <span
class="methodparam"><span class="type">int</span> `$year`</span> , <span
class="methodparam"><span class="type">int</span> `$week`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$dayOfWeek`<span class="initializer"> = 1</span></span> \] )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">setTime</span> ( <span
class="methodparam"><span class="type">int</span> `$hour`</span> , <span
class="methodparam"><span class="type">int</span> `$minute`</span> \[,
<span class="methodparam"><span class="type">int</span> `$second`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$microsecond`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">setTimestamp</span> ( <span
class="methodparam"><span class="type">int</span> `$timestamp`</span> )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">setTimezone</span> ( <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`</span> )

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">sub</span> ( <span class="methodparam"><span
class="type">DateInterval</span> `$interval`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateInterval</span><span class="type">false</span></span>
<span class="methodname">diff</span> ( <span class="methodparam"><span
class="type">DateTimeInterface</span> `$targetObject`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$absolute`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">format</span> ( <span class="methodparam"><span
class="type">string</span> `$format`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">getOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTimestamp</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeZone</span><span class="type">false</span></span>
<span class="methodname">getTimezone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_wakeup</span> ( <span
class="methodparam">void</span> )

}

Changelog
---------

| Version | Description                                                                                                                                                                                                               |
|---------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The class constants of <span class="classname">DateTime</span> are now defined on <span class="classname">DateTimeInterface</span>.                                                                                       |
| 7.0.0   | Added constants: <a href="/class/datetimeinterface.html#" class="link">DATE_RFC3339_EXTENDED</a> and <a href="/class/datetimeinterface.html#" class="link">DateTime::RFC3339_EXTENDED</a>.                                |
| 5.5.0   | The class now implements <span class="classname">DateTimeInterface</span>.                                                                                                                                                |
| 5.4.24  | The COOKIE constant was changed to reflect RFC 1036 using a four digit year rather than a two digit year (RFC 850) as prior versions.                                                                                     |
| 5.2.2   | DateTime object comparison with the <a href="/language/operators/comparison.html" class="link">comparison operators</a> changed to work as expected. Previously, all DateTime objects were considered equal (using *==*). |

DateTime::add
=============

date\_add
=========

Adds an amount of days, months, years, hours, minutes and seconds to a
DateTime object

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">DateTime::add</span> ( <span
class="methodparam"><span class="type">DateInterval</span>
`$interval`</span> )

Procedural style

<span class="type">DateTime</span> <span
class="methodname">date\_add</span> ( <span class="methodparam"><span
class="type">DateTime</span> `$object`</span> , <span
class="methodparam"><span class="type">DateInterval</span>
`$interval`</span> )

Adds the specified <span class="classname">DateInterval</span> object to
the specified <span class="classname">DateTime</span> object.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`interval`  
A <span class="classname">DateInterval</span> object

### Return Values

Returns the <span class="classname">DateTime</span> object for method
chaining or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::add</span> example**

Object oriented style

``` php
<?php
$date = new DateTime('2000-01-01');
$date->add(new DateInterval('P10D'));
echo $date->format('Y-m-d') . "\n";
?>
```

Procedural style

``` php
<?php
$date = date_create('2000-01-01');
date_add($date, date_interval_create_from_date_string('10 days'));
echo date_format($date, 'Y-m-d');
?>
```

The above examples will output:

    2000-01-11

**Example \#2 Further <span class="function">DateTime::add</span>
examples**

``` php
<?php
$date = new DateTime('2000-01-01');
$date->add(new DateInterval('PT10H30S'));
echo $date->format('Y-m-d H:i:s') . "\n";

$date = new DateTime('2000-01-01');
$date->add(new DateInterval('P7Y5M4DT4H3M2S'));
echo $date->format('Y-m-d H:i:s') . "\n";
?>
```

The above example will output:

    2000-01-01 10:00:30
    2007-06-05 04:03:02

**Example \#3 Beware when adding months**

``` php
<?php
$date = new DateTime('2000-12-31');
$interval = new DateInterval('P1M');

$date->add($interval);
echo $date->format('Y-m-d') . "\n";

$date->add($interval);
echo $date->format('Y-m-d') . "\n";
?>
```

The above example will output:

    2001-01-31
    2001-03-03

### Notes

<span class="function">DateTime::modify</span> is an alternative when
using PHP 5.2.

### See Also

-   <span class="function">DateTime::sub</span>
-   <span class="function">DateTime::diff</span>
-   <span class="function">DateTime::modify</span>

DateTime::\_\_construct
=======================

date\_create
============

Returns new DateTime object

### Description

Object oriented style

<span class="modifier">public</span> <span
class="methodname">DateTime::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$datetime`<span
class="initializer"> = "now"</span></span> \[, <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`<span class="initializer"> = **`NULL`**</span></span> \]\] )

Procedural style

<span class="type"><span class="type">DateTime</span><span
class="type">false</span></span> <span
class="methodname">date\_create</span> (\[ <span
class="methodparam"><span class="type">string</span> `$datetime`<span
class="initializer"> = "now"</span></span> \[, <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`<span class="initializer"> = **`NULL`**</span></span> \]\] )

Returns new DateTime object.

### Parameters

`datetime`  
A date/time string. Valid formats are explained in
<a href="/datetime/formats.html" class="link">Date and Time Formats</a>.

Enter *"now"* here to obtain the current time when using the `$timezone`
parameter.

`timezone`  
A <span class="classname">DateTimeZone</span> object representing the
timezone of `$datetime`.

If `$timezone` is omitted, the current timezone will be used.

> **Note**:
>
> The `$timezone` parameter and the current timezone are ignored when
> the `$datetime` parameter either is a UNIX timestamp (e.g.
> *@946684800*) or specifies a timezone (e.g.
> *2010-01-28T15:00:00+02:00*).

### Return Values

Returns a new DateTime instance. Procedural style returns **`FALSE`** on
failure.

### Errors/Exceptions

Emits <span class="classname">Exception</span> in case of an error.

### Changelog

| Version | Description                                                              |
|---------|--------------------------------------------------------------------------|
| 7.1.0   | From now on microseconds are filled with actual value. Not with '00000'. |

### Examples

**Example \#1 <span class="function">DateTime::\_\_construct</span>
example**

Object oriented style

``` php
<?php
try {
    $date = new DateTime('2000-01-01');
} catch (Exception $e) {
    echo $e->getMessage();
    exit(1);
}

echo $date->format('Y-m-d');
?>
```

Procedural style

``` php
<?php
$date = date_create('2000-01-01');
if (!$date) {
    $e = date_get_last_errors();
    foreach ($e['errors'] as $error) {
        echo "$error\n";
    }
    exit(1);
}

echo date_format($date, 'Y-m-d');
?>
```

The above examples will output:

    2000-01-01

**Example \#2 Intricacies of <span
class="function">DateTime::\_\_construct</span>**

``` php
<?php
// Specified date/time in your computer's time zone.
$date = new DateTime('2000-01-01');
echo $date->format('Y-m-d H:i:sP') . "\n";

// Specified date/time in the specified time zone.
$date = new DateTime('2000-01-01', new DateTimeZone('Pacific/Nauru'));
echo $date->format('Y-m-d H:i:sP') . "\n";

// Current date/time in your computer's time zone.
$date = new DateTime();
echo $date->format('Y-m-d H:i:sP') . "\n";

// Current date/time in the specified time zone.
$date = new DateTime(null, new DateTimeZone('Pacific/Nauru'));
echo $date->format('Y-m-d H:i:sP') . "\n";

// Using a UNIX timestamp.  Notice the result is in the UTC time zone.
$date = new DateTime('@946684800');
echo $date->format('Y-m-d H:i:sP') . "\n";

// Non-existent values roll over.
$date = new DateTime('2000-02-30');
echo $date->format('Y-m-d H:i:sP') . "\n";
?>
```

The above example will output something similar to:

    2000-01-01 00:00:00-05:00
    2000-01-01 00:00:00+12:00
    2010-04-24 10:24:16-04:00
    2010-04-25 02:24:16+12:00
    2000-01-01 00:00:00+00:00
    2000-03-01 00:00:00-05:00

### See Also

-   <span class="function">DateTime::createFromFormat</span>
-   <span class="function">DateTimeZone::\_\_construct</span>
-   <a href="/datetime/formats.html" class="link">Date and Time Formats</a>
-   <a href="/datetime/setup.html#" class="link">date.timezone</a> ini
    setting
-   <span class="function">date\_default\_timezone\_set</span>
-   <span class="function">DateTime::getLastErrors</span>
-   <span class="function">checkdate</span>

DateTime::createFromFormat
==========================

date\_create\_from\_format
==========================

Parses a time string according to a specified format

### Description

Object oriented style

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">DateTime</span><span class="type">false</span></span> <span
class="methodname">DateTime::createFromFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> ,
<span class="methodparam"><span class="type">string</span>
`$datetime`</span> \[, <span class="methodparam"><span
class="type">DateTimeZone</span> `$timezone`</span> \] )

Procedural style

<span class="type"><span class="type">DateTime</span><span
class="type">false</span></span> <span
class="methodname">date\_create\_from\_format</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> ,
<span class="methodparam"><span class="type">string</span>
`$datetime`</span> \[, <span class="methodparam"><span
class="type">DateTimeZone</span> `$timezone`</span> \] )

Returns a new DateTime object representing the date and time specified
by the `datetime` string, which was formatted in the given `format`.

### Parameters

`format`  
The format that the passed in <span class="type">string</span> should be
in. See the formatting options below. In most cases, the same letters as
for the <span class="function">date</span> can be used.

|            `format` character            | Description                                                                                                                                      | Example parsable values                                                                                                                        |
|:----------------------------------------:|--------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
|                   *Day*                  | ---                                                                                                                                              | ---                                                                                                                                            |
|                *d* and *j*               | Day of the month, 2 digits with or without leading zeros                                                                                         | *01* to *31* or *1* to *31*                                                                                                                    |
|                *D* and *l*               | A textual representation of a day                                                                                                                | *Mon* through *Sun* or *Sunday* through *Saturday*                                                                                             |
|                    *S*                   | English ordinal suffix for the day of the month, 2 characters. It's ignored while processing.                                                    | *st*, *nd*, *rd* or *th*.                                                                                                                      |
|                    *z*                   | The day of the year (starting from 0)                                                                                                            | *0* through *365*                                                                                                                              |
|                  *Month*                 | ---                                                                                                                                              | ---                                                                                                                                            |
|                *F* and *M*               | A textual representation of a month, such as January or Sept                                                                                     | *January* through *December* or *Jan* through *Dec*                                                                                            |
|                *m* and *n*               | Numeric representation of a month, with or without leading zeros                                                                                 | *01* through *12* or *1* through *12*                                                                                                          |
|                  *Year*                  | ---                                                                                                                                              | ---                                                                                                                                            |
|                    *Y*                   | A full numeric representation of a year, 4 digits                                                                                                | Examples: *1999* or *2003*                                                                                                                     |
|                    *y*                   | A two digit representation of a year (which is assumed to be in the range 1970-2069, inclusive)                                                  | Examples: *99* or *03* (which will be interpreted as *1999* and *2003*, respectively)                                                          |
|                  *Time*                  | ---                                                                                                                                              | ---                                                                                                                                            |
|                *a* and *A*               | Ante meridiem and Post meridiem                                                                                                                  | *am* or *pm*                                                                                                                                   |
|                *g* and *h*               | 12-hour format of an hour with or without leading zero                                                                                           | *1* through *12* or *01* through *12*                                                                                                          |
|                *G* and *H*               | 24-hour format of an hour with or without leading zeros                                                                                          | *0* through *23* or *00* through *23*                                                                                                          |
|                    *i*                   | Minutes with leading zeros                                                                                                                       | *00* to *59*                                                                                                                                   |
|                    *s*                   | Seconds, with leading zeros                                                                                                                      | *00* through *59*                                                                                                                              |
|                    *v*                   | Milliseconds (up to three digits)                                                                                                                | Example: *12*, *345*                                                                                                                           |
|                    *u*                   | Microseconds (up to six digits)                                                                                                                  | Example: *45*, *654321*                                                                                                                        |
|                *Timezone*                | ---                                                                                                                                              | ---                                                                                                                                            |
|           *e*, *O*, *P* and *T*          | Timezone identifier, or difference to UTC in hours, or difference to UTC with colon between hours and minutes, or timezone abbreviation          | Examples: *UTC*, *GMT*, *Atlantic/Azores* or *+0200* or *+02:00* or *EST*, *MDT*                                                               |
|             *Full Date/Time*             | ---                                                                                                                                              | ---                                                                                                                                            |
|                    *U*                   | Seconds since the Unix Epoch (January 1 1970 00:00:00 GMT)                                                                                       | Example: *1292177455*                                                                                                                          |
|        *Whitespace and Separators*       | ---                                                                                                                                              | ---                                                                                                                                            |
|                  (space)                 | One space or one tab                                                                                                                             | Example:                                                                                                                                       |
|                   *\#*                   | One of the following separation symbol: *;*, *:*, */*, *.*, *,*, *-*, *(* or *)*                                                                 | Example: */*                                                                                                                                   |
| *;*, *:*, */*, *.*, *,*, *-*, *(* or *)* | The specified character.                                                                                                                         | Example: *-*                                                                                                                                   |
|                    *?*                   | A random byte                                                                                                                                    | Example: *^* (Be aware that for UTF-8 characters you might need more than one *?*. In this case, using *\** is probably what you want instead) |
|                   *\**                   | Random bytes until the next separator or digit                                                                                                   | Example: *\** in *Y-\*-d* with the string *2009-aWord-08* will match *aWord*                                                                   |
|                    *!*                   | Resets all fields (year, month, day, hour, minute, second, fraction and timezone information) to the Unix Epoch                                  | Without *!,* all fields will be set to the current date and time.                                                                              |
|                   *\|*                   | Resets all fields (year, month, day, hour, minute, second, fraction and timezone information) to the Unix Epoch if they have not been parsed yet | *Y-m-d\|* will set the year, month and day to the information found in the string to parse, and sets the hour, minute and second to 0.         |
|                    *+*                   | If this format specifier is present, trailing data in the string will not cause an error, but a warning instead                                  | Use <span class="methodname">DateTime::getLastErrors</span> to find out whether trailing data was present.                                     |

Unrecognized characters in the format string will cause the parsing to
fail and an error message is appended to the returned structure. You can
query error messages with <span
class="methodname">DateTime::getLastErrors</span>.

To include literal characters in `format`, you have to escape them with
a backslash (*\\*).

If `format` does not contain the character *!* then portions of the
generated time which are not specified in `format` will be set to the
current system time.

If `format` contains the character *!*, then portions of the generated
time not provided in `format`, as well as values to the left-hand side
of the *!*, will be set to corresponding values from the Unix epoch.

The Unix epoch is 1970-01-01 00:00:00 UTC.

`datetime`  
String representing the time.

`timezone`  
A <span class="classname">DateTimeZone</span> object representing the
desired time zone.

If `timezone` is omitted and `datetime` contains no timezone, the
current timezone will be used.

> **Note**:
>
> The `timezone` parameter and the current timezone are ignored when the
> `datetime` parameter either contains a UNIX timestamp (e.g.
> *946684800*) or specifies a timezone (e.g.
> *2010-01-28T15:00:00+02:00*).

### Return Values

Returns a new DateTime instance or **`FALSE`** on failure.

### Changelog

| Version | Description                                |
|---------|--------------------------------------------|
| 7.3.0   | The *v* `format` specifier has been added. |

### Examples

**Example \#1 <span class="function">DateTime::createFromFormat</span>
example**

Object oriented style

``` php
<?php
$date = DateTime::createFromFormat('j-M-Y', '15-Feb-2009');
echo $date->format('Y-m-d');
?>
```

Procedural style

``` php
<?php
$date = date_create_from_format('j-M-Y', '15-Feb-2009');
echo date_format($date, 'Y-m-d');
?>
```

The above examples will output:

    2009-02-15

**Example \#2 Intricacies of <span
class="function">DateTime::createFromFormat</span>**

``` php
<?php
echo 'Current time: ' . date('Y-m-d H:i:s') . "\n";

$format = 'Y-m-d';
$date = DateTime::createFromFormat($format, '2009-02-15');
echo "Format: $format; " . $date->format('Y-m-d H:i:s') . "\n";

$format = 'Y-m-d H:i:s';
$date = DateTime::createFromFormat($format, '2009-02-15 15:16:17');
echo "Format: $format; " . $date->format('Y-m-d H:i:s') . "\n";

$format = 'Y-m-!d H:i:s';
$date = DateTime::createFromFormat($format, '2009-02-15 15:16:17');
echo "Format: $format; " . $date->format('Y-m-d H:i:s') . "\n";

$format = '!d';
$date = DateTime::createFromFormat($format, '15');
echo "Format: $format; " . $date->format('Y-m-d H:i:s') . "\n";
?>
```

The above example will output something similar to:

    Current time: 2010-04-23 10:29:35
    Format: Y-m-d; 2009-02-15 10:29:35
    Format: Y-m-d H:i:s; 2009-02-15 15:16:17
    Format: Y-m-!d H:i:s; 1970-01-15 15:16:17
    Format: !d; 1970-01-15 00:00:00

**Example \#3 Format string with literal characters**

``` php
<?php
echo DateTime::createFromFormat('H\h i\m s\s','23h 15m 03s')->format('H:i:s');
?>
```

The above example will output something similar to:

    23:15:03

### See Also

-   <span class="function">DateTime::\_\_construct</span>
-   <span class="function">DateTime::getLastErrors</span>
-   <span class="function">checkdate</span>
-   <span class="function">strptime</span>

DateTime::createFromImmutable
=============================

Returns new DateTime object encapsulating the given DateTimeImmutable
object

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">DateTime</span> <span
class="methodname">DateTime::createFromImmutable</span> ( <span
class="methodparam"><span class="type">DateTimeImmutable</span>
`$object`</span> )

### Parameters

`object`  
The immutable <span class="classname">DateTimeImmutable</span> object
that needs to be converted to a mutable version. This object is not
modified, but instead a new <span class="classname">DateTime</span>
object is created containing the same date, time, and timezone
information.

### Examples

**Example \#1 Creating a mutable date time object**

``` php
<?php
$date = new DateTimeImmutable("2014-06-20 11:45 Europe/London");

$mutable = DateTime::createFromImmutable( $date );
?>
```

### Return Values

Returns a new <span class="classname">DateTime</span> instance.

DateTime::getLastErrors
=======================

date\_get\_last\_errors
=======================

Returns the warnings and errors

### Description

Object oriented style

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">DateTime::getLastErrors</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">array</span> <span
class="methodname">date\_get\_last\_errors</span> ( <span
class="methodparam">void</span> )

Returns an array of warnings and errors found while parsing a date/time
string.

### Parameters

This function has no parameters.

### Return Values

Returns array containing info about warnings and errors.

### Examples

**Example \#1 <span class="function">DateTime::getLastErrors</span>
example**

Object oriented style

``` php
<?php
try {
    $date = new DateTime('asdfasdf');
} catch (Exception $e) {
    // For demonstration purposes only...
    print_r(DateTime::getLastErrors());

    // The real object oriented way to do this is
    // echo $e->getMessage();
}
?>
```

Procedural style

``` php
<?php
$date = date_create('asdfasdf');
print_r(date_get_last_errors());
?>
```

The above examples will output:

    Array
    (
       [warning_count] => 1
       [warnings] => Array
           (
               [6] => Double timezone specification
           )

       [error_count] => 1
       [errors] => Array
           (
               [0] => The timezone could not be found in the database
           )

    )

The indexes 6, and 0 in the example output refer to the character index
in the string where the error occurred.

DateTime::modify
================

date\_modify
============

Alters the timestamp

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">DateTime::modify</span> ( <span
class="methodparam"><span class="type">string</span> `$modifier`</span>
)

Procedural style

<span class="type">DateTime</span> <span
class="methodname">date\_modify</span> ( <span class="methodparam"><span
class="type">DateTime</span> `$object`</span> , <span
class="methodparam"><span class="type">string</span> `$modifier`</span>
)

Alter the timestamp of a DateTime object by incrementing or decrementing
in a format accepted by <span
class="function">DateTimeImmutable::\_\_construct</span>.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`modifier`  
A date/time string. Valid formats are explained in
<a href="/datetime/formats.html" class="link">Date and Time Formats</a>.

### Return Values

Returns the <span class="classname">DateTime</span> object for method
chaining or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::modify</span> example**

Object oriented style

``` php
<?php
$date = new DateTime('2006-12-12');
$date->modify('+1 day');
echo $date->format('Y-m-d');
?>
```

Procedural style

``` php
<?php
$date = date_create('2006-12-12');
date_modify($date, '+1 day');
echo date_format($date, 'Y-m-d');
?>
```

The above examples will output:

    2006-12-13

**Example \#2 Beware when adding or subtracting months**

``` php
<?php
$date = new DateTime('2000-12-31');

$date->modify('+1 month');
echo $date->format('Y-m-d') . "\n";

$date->modify('+1 month');
echo $date->format('Y-m-d') . "\n";
?>
```

The above example will output:

    2001-01-31
    2001-03-03

### See Also

-   <span class="function">strtotime</span>
-   <span class="function">DateTime::add</span>
-   <span class="function">DateTime::sub</span>
-   <span class="function">DateTime::setDate</span>
-   <span class="function">DateTime::setISODate</span>
-   <span class="function">DateTime::setTime</span>
-   <span class="function">DateTime::setTimestamp</span>

DateTime::\_\_set\_state
========================

The \_\_set\_state handler

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">DateTime</span> <span
class="methodname">DateTime::\_\_set\_state</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

The
<a href="/language/oop5/magic.html#object.set-state" class="link">__set_state()</a>
handler.

### Parameters

`array`  
Initialization array.

### Return Values

Returns a new instance of a DateTime object.

DateTime::setDate
=================

date\_date\_set
===============

Sets the date

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">DateTime::setDate</span> ( <span
class="methodparam"><span class="type">int</span> `$year`</span> , <span
class="methodparam"><span class="type">int</span> `$month`</span> ,
<span class="methodparam"><span class="type">int</span> `$day`</span> )

Procedural style

<span class="type">DateTime</span> <span
class="methodname">date\_date\_set</span> ( <span
class="methodparam"><span class="type">DateTime</span> `$object`</span>
, <span class="methodparam"><span class="type">int</span> `$year`</span>
, <span class="methodparam"><span class="type">int</span>
`$month`</span> , <span class="methodparam"><span
class="type">int</span> `$day`</span> )

Resets the current date of the DateTime object to a different date.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`year`  
Year of the date.

`month`  
Month of the date.

`day`  
Day of the date.

### Return Values

Returns the <span class="classname">DateTime</span> object for method
chaining or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::setDate</span> example**

Object oriented style

``` php
<?php
$date = new DateTime();
$date->setDate(2001, 2, 3);
echo $date->format('Y-m-d');
?>
```

Procedural style

``` php
<?php
$date = date_create();
date_date_set($date, 2001, 2, 3);
echo date_format($date, 'Y-m-d');
?>
```

The above examples will output:

    2001-02-03

**Example \#2 Values exceeding ranges are added to their parent values**

``` php
<?php
$date = new DateTime();

$date->setDate(2001, 2, 28);
echo $date->format('Y-m-d') . "\n";

$date->setDate(2001, 2, 29);
echo $date->format('Y-m-d') . "\n";

$date->setDate(2001, 14, 3);
echo $date->format('Y-m-d') . "\n";
?>
```

The above example will output:

    2001-02-28
    2001-03-01
    2002-02-03

### See Also

-   <span class="function">DateTime::setISODate</span>
-   <span class="function">DateTime::setTime</span>

DateTime::setISODate
====================

date\_isodate\_set
==================

Sets the ISO date

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">DateTime::setISODate</span> ( <span
class="methodparam"><span class="type">int</span> `$year`</span> , <span
class="methodparam"><span class="type">int</span> `$week`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$dayOfWeek`<span class="initializer"> = 1</span></span> \] )

Procedural style

<span class="type">DateTime</span> <span
class="methodname">date\_isodate\_set</span> ( <span
class="methodparam"><span class="type">DateTime</span> `$object`</span>
, <span class="methodparam"><span class="type">int</span> `$year`</span>
, <span class="methodparam"><span class="type">int</span> `$week`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$dayOfWeek`<span class="initializer"> = 1</span></span> \] )

Set a date according to the ISO 8601 standard - using weeks and day
offsets rather than specific dates.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`year`  
Year of the date.

`week`  
Week of the date.

`dayOfWeek`  
Offset from the first day of the week.

### Return Values

Returns the <span class="classname">DateTime</span> object for method
chaining or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::setISODate</span>
example**

Object oriented style

``` php
<?php
$date = new DateTime();

$date->setISODate(2008, 2);
echo $date->format('Y-m-d') . "\n";

$date->setISODate(2008, 2, 7);
echo $date->format('Y-m-d') . "\n";
?>
```

Procedural style

``` php
<?php
$date = date_create();

date_isodate_set($date, 2008, 2);
echo date_format($date, 'Y-m-d') . "\n";

date_isodate_set($date, 2008, 2, 7);
echo date_format($date, 'Y-m-d') . "\n";
?>
```

The above examples will output:

    2008-01-07
    2008-01-13

**Example \#2 Values exceeding ranges are added to their parent values**

``` php
<?php
$date = new DateTime();

$date->setISODate(2008, 2, 7);
echo $date->format('Y-m-d') . "\n";

$date->setISODate(2008, 2, 8);
echo $date->format('Y-m-d') . "\n";

$date->setISODate(2008, 53, 7);
echo $date->format('Y-m-d') . "\n";
?>
```

The above example will output:

    2008-01-13
    2008-01-14
    2009-01-04

**Example \#3 Finding the month a week is in**

``` php
<?php
$date = new DateTime();
$date->setISODate(2008, 14);
echo $date->format('n');
?>
```

The above examples will output:

    3

### See Also

-   <span class="function">DateTime::setDate</span>
-   <span class="function">DateTime::setTime</span>

DateTime::setTime
=================

date\_time\_set
===============

Sets the time

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">DateTime::setTime</span> ( <span
class="methodparam"><span class="type">int</span> `$hour`</span> , <span
class="methodparam"><span class="type">int</span> `$minute`</span> \[,
<span class="methodparam"><span class="type">int</span> `$second`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$microsecond`<span
class="initializer"> = 0</span></span> \]\] )

Procedural style

<span class="type">DateTime</span> <span
class="methodname">date\_time\_set</span> ( <span
class="methodparam"><span class="type">DateTime</span> `$object`</span>
, <span class="methodparam"><span class="type">int</span> `$hour`</span>
, <span class="methodparam"><span class="type">int</span>
`$minute`</span> \[, <span class="methodparam"><span
class="type">int</span> `$second`<span class="initializer"> =
0</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$microsecond`<span class="initializer"> =
0</span></span> \]\] )

Resets the current time of the DateTime object to a different time.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`hour`  
Hour of the time.

`minute`  
Minute of the time.

`second`  
Second of the time.

`microsecond`  
Microsecond of the time.

### Return Values

Returns the <span class="classname">DateTime</span> object for method
chaining or **`FALSE`** on failure.

### Changelog

| Version | Description                            |
|---------|----------------------------------------|
| 7.1.0   | The `microsecond` parameter was added. |

### Examples

**Example \#1 <span class="function">DateTime::setTime</span> example**

Object oriented style

``` php
<?php
$date = new DateTime('2001-01-01');

$date->setTime(14, 55);
echo $date->format('Y-m-d H:i:s') . "\n";

$date->setTime(14, 55, 24);
echo $date->format('Y-m-d H:i:s') . "\n";
?>
```

Procedural style

``` php
<?php
$date = date_create('2001-01-01');

date_time_set($date, 14, 55);
echo date_format($date, 'Y-m-d H:i:s') . "\n";

date_time_set($date, 14, 55, 24);
echo date_format($date, 'Y-m-d H:i:s') . "\n";
?>
```

The above examples will output something similar to:

    2001-01-01 14:55:00
    2001-01-01 14:55:24

**Example \#2 Values exceeding ranges are added to their parent values**

``` php
<?php
$date = new DateTime('2001-01-01');

$date->setTime(14, 55, 24);
echo $date->format('Y-m-d H:i:s') . "\n";

$date->setTime(14, 55, 65);
echo $date->format('Y-m-d H:i:s') . "\n";

$date->setTime(14, 65, 24);
echo $date->format('Y-m-d H:i:s') . "\n";

$date->setTime(25, 55, 24);
echo $date->format('Y-m-d H:i:s') . "\n";
?>
```

The above example will output:

    2001-01-01 14:55:24
    2001-01-01 14:56:05
    2001-01-01 15:05:24
    2001-01-02 01:55:24

### See Also

-   <span class="function">DateTime::setDate</span>
-   <span class="function">DateTime::setISODate</span>

DateTime::setTimestamp
======================

date\_timestamp\_set
====================

Sets the date and time based on an Unix timestamp

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">DateTime::setTimestamp</span> ( <span
class="methodparam"><span class="type">int</span> `$timestamp`</span> )

Procedural style

<span class="type">DateTime</span> <span
class="methodname">date\_timestamp\_set</span> ( <span
class="methodparam"><span class="type">DateTime</span> `$object`</span>
, <span class="methodparam"><span class="type">int</span>
`$timestamp`</span> )

Sets the date and time based on an Unix timestamp.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`timestamp`  
Unix timestamp representing the date.

### Return Values

Returns the <span class="classname">DateTime</span> object for method
chaining or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::setTimestamp</span>
example**

Object oriented style

``` php
<?php
$date = new DateTime();
echo $date->format('U = Y-m-d H:i:s') . "\n";

$date->setTimestamp(1171502725);
echo $date->format('U = Y-m-d H:i:s') . "\n";
?>
```

Procedural style

``` php
<?php
$date = date_create();
echo date_format($date, 'U = Y-m-d H:i:s') . "\n";

date_timestamp_set($date, 1171502725);
echo date_format($date, 'U = Y-m-d H:i:s') . "\n";
?>
```

The above examples will output something similar to:

    1272508903 = 2010-04-28 22:41:43
    1171502725 = 2007-02-14 20:25:25

### Notes

Using the Unix timestamp format to construct a new <span
class="type">DateTime</span> object is an alternative when using PHP
5.2, as shown in the example below.

**Example \#2 <span class="function">DateTime::setTimestamp</span>
alternative in PHP 5.2**

``` php
<?php
$ts = 1171502725;
$date = new DateTime("@$ts");
echo $date->format('U = Y-m-d H:i:s') . "\n";
?>
```

The above example will output something similar to:

    1171502725 = 2007-02-14 20:25:25

### See Also

-   <span class="function">DateTime::getTimestamp</span>

DateTime::setTimezone
=====================

date\_timezone\_set
===================

Sets the time zone for the DateTime object

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">DateTime::setTimezone</span> ( <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`</span> )

Procedural style

<span class="type">DateTime</span> <span
class="methodname">date\_timezone\_set</span> ( <span
class="methodparam"><span class="type">DateTime</span> `$object`</span>
, <span class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`</span> )

Sets a new timezone for a <span class="classname">DateTime</span> <span
class="type">object</span>.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`timezone`  
A <span class="classname">DateTimeZone</span> object representing the
desired time zone.

### Return Values

Returns the <span class="classname">DateTime</span> object for method
chaining or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::setTimeZone</span>
example**

Object oriented style

``` php
<?php
$date = new DateTime('2000-01-01', new DateTimeZone('Pacific/Nauru'));
echo $date->format('Y-m-d H:i:sP') . "\n";

$date->setTimezone(new DateTimeZone('Pacific/Chatham'));
echo $date->format('Y-m-d H:i:sP') . "\n";
?>
```

Procedural style

``` php
<?php
$date = date_create('2000-01-01', timezone_open('Pacific/Nauru'));
echo date_format($date, 'Y-m-d H:i:sP') . "\n";

date_timezone_set($date, timezone_open('Pacific/Chatham'));
echo date_format($date, 'Y-m-d H:i:sP') . "\n";
?>
```

The above examples will output:

    2000-01-01 00:00:00+12:00
    2000-01-01 01:45:00+13:45

### See Also

-   <span class="function">DateTime::getTimezone</span>
-   <span class="function">DateTimeZone::\_\_construct</span>

DateTime::sub
=============

date\_sub
=========

Subtracts an amount of days, months, years, hours, minutes and seconds
from a DateTime object

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">DateTime</span>
<span class="methodname">DateTime::sub</span> ( <span
class="methodparam"><span class="type">DateInterval</span>
`$interval`</span> )

Procedural style

<span class="type">DateTime</span> <span
class="methodname">date\_sub</span> ( <span class="methodparam"><span
class="type">DateTime</span> `$object`</span> , <span
class="methodparam"><span class="type">DateInterval</span>
`$interval`</span> )

Subtracts the specified <span class="classname">DateInterval</span>
object from the specified DateTime object.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`interval`  
A <span class="classname">DateInterval</span> object

### Return Values

Returns the <span class="classname">DateTime</span> object for method
chaining or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::sub</span> example**

Object oriented style

``` php
<?php
$date = new DateTime('2000-01-20');
$date->sub(new DateInterval('P10D'));
echo $date->format('Y-m-d') . "\n";
?>
```

Procedural style

``` php
<?php
$date = date_create('2000-01-20');
date_sub($date, date_interval_create_from_date_string('10 days'));
echo date_format($date, 'Y-m-d');
?>
```

The above examples will output:

    2000-01-10

**Example \#2 Further <span class="function">DateTime::sub</span>
examples**

``` php
<?php
$date = new DateTime('2000-01-20');
$date->sub(new DateInterval('PT10H30S'));
echo $date->format('Y-m-d H:i:s') . "\n";

$date = new DateTime('2000-01-20');
$date->sub(new DateInterval('P7Y5M4DT4H3M2S'));
echo $date->format('Y-m-d H:i:s') . "\n";
?>
```

The above example will output:

    2000-01-19 13:59:30
    1992-08-15 19:56:58

**Example \#3 Beware when subtracting months**

``` php
<?php
$date = new DateTime('2001-04-30');
$interval = new DateInterval('P1M');

$date->sub($interval);
echo $date->format('Y-m-d') . "\n";

$date->sub($interval);
echo $date->format('Y-m-d') . "\n";
?>
```

The above example will output:

    2001-03-30
    2001-03-02

### Notes

<span class="function">DateTime::modify</span> is an alternative when
using PHP 5.2.

### See Also

-   <span class="function">DateTime::add</span>
-   <span class="function">DateTime::diff</span>
-   <span class="function">DateTime::modify</span>

Introduction
------------

Representation of date and time.

Class synopsis
--------------

**DateTimeImmutable**

<span class="ooclass"> class **DateTimeImmutable** </span> <span
class="oointerface">implements <span
class="interfacename">DateTimeInterface</span> </span> {

/\* Inherited constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::ATOM` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::COOKIE` <span class="initializer"> = "l, d-M-Y H:i:s
T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::ISO8601` <span class="initializer"> =
"Y-m-d\\TH:i:sO"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC822` <span class="initializer"> = "D, d M y H:i:s
O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC850` <span class="initializer"> = "l, d-M-y H:i:s
T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC1036` <span class="initializer"> = "D, d M y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC1123` <span class="initializer"> = "D, d M Y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC7231` <span class="initializer"> = "D, d M Y
H:i:s \\G\\M\\T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC2822` <span class="initializer"> = "D, d M Y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC3339` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC3339_EXTENDED` <span class="initializer"> =
"Y-m-d\\TH:i:s.vP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RSS` <span class="initializer"> = "D, d M Y H:i:s
O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::W3C` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$datetime`<span
class="initializer"> = "now"</span></span> \[, <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`<span class="initializer"> = **`NULL`**</span></span> \]\] )

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">add</span> ( <span class="methodparam"><span
class="type">DateInterval</span> `$interval`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">createFromFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> ,
<span class="methodparam"><span class="type">string</span>
`$datetime`</span> \[, <span class="methodparam"><span
class="type">DateTimeZone</span> `$timezone`</span> \] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">createFromMutable</span> ( <span
class="methodparam"><span class="type">DateTime</span> `$object`</span>
)

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">getLastErrors</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeImmutable</span><span
class="type">false</span></span> <span class="methodname">modify</span>
( <span class="methodparam"><span class="type">string</span>
`$modifier`</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">\_\_set\_state</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">setDate</span> ( <span class="methodparam"><span
class="type">int</span> `$year`</span> , <span class="methodparam"><span
class="type">int</span> `$month`</span> , <span
class="methodparam"><span class="type">int</span> `$day`</span> )

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">setISODate</span> ( <span class="methodparam"><span
class="type">int</span> `$year`</span> , <span class="methodparam"><span
class="type">int</span> `$week`</span> \[, <span
class="methodparam"><span class="type">int</span> `$day`<span
class="initializer"> = 1</span></span> \] )

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">setTime</span> ( <span class="methodparam"><span
class="type">int</span> `$hour`</span> , <span class="methodparam"><span
class="type">int</span> `$minute`</span> \[, <span
class="methodparam"><span class="type">int</span> `$second`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$microsecond`<span
class="initializer"> = 0</span></span> \]\] )

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">setTimestamp</span> ( <span class="methodparam"><span
class="type">int</span> `$timestamp`</span> )

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">setTimezone</span> ( <span class="methodparam"><span
class="type">DateTimeZone</span> `$timezone`</span> )

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">sub</span> ( <span class="methodparam"><span
class="type">DateInterval</span> `$interval`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateInterval</span><span class="type">false</span></span>
<span class="methodname">diff</span> ( <span class="methodparam"><span
class="type">DateTimeInterface</span> `$targetObject`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$absolute`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">format</span> ( <span class="methodparam"><span
class="type">string</span> `$format`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">getOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTimestamp</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeZone</span><span class="type">false</span></span>
<span class="methodname">getTimezone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_wakeup</span> ( <span
class="methodparam">void</span> )

}

DateTimeImmutable::add
======================

Adds an amount of days, months, years, hours, minutes and seconds

### Description

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::add</span> ( <span
class="methodparam"><span class="type">DateInterval</span>
`$interval`</span> )

Like <span class="methodname">DateTime::add</span> but works with <span
class="classname">DateTimeImmutable</span>.

DateTimeImmutable::\_\_construct
================================

date\_create\_immutable
=======================

Returns new DateTimeImmutable object

### Description

Object oriented style

<span class="modifier">public</span> <span
class="methodname">DateTimeImmutable::\_\_construct</span> (\[ <span
class="methodparam"><span class="type">string</span> `$datetime`<span
class="initializer"> = "now"</span></span> \[, <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`<span class="initializer"> = **`NULL`**</span></span> \]\] )

Procedural style

<span class="type">DateTimeImmutable</span> <span
class="methodname">date\_create\_immutable</span> (\[ <span
class="methodparam"><span class="type">string</span> `$datetime`<span
class="initializer"> = "now"</span></span> \[, <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`<span class="initializer"> = **`NULL`**</span></span> \]\] )

Like <span class="methodname">DateTime::\_\_construct</span> but works
with <span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::createFromFormat
===================================

date\_create\_immutable\_from\_format
=====================================

Parses a time string according to a specified format

### Description

Object oriented style

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::createFromFormat</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> ,
<span class="methodparam"><span class="type">string</span>
`$datetime`</span> \[, <span class="methodparam"><span
class="type">DateTimeZone</span> `$timezone`</span> \] )

Procedural style

<span class="type">DateTimeImmutable</span> <span
class="methodname">date\_create\_immutable\_from\_format</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> ,
<span class="methodparam"><span class="type">string</span>
`$datetime`</span> \[, <span class="methodparam"><span
class="type">DateTimeZone</span> `$timezone`</span> \] )

Like <span class="methodname">DateTime::createFromFormat</span> but
works with <span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::createFromMutable
====================================

Returns new DateTimeImmutable object encapsulating the given DateTime
object

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::createFromMutable</span> ( <span
class="methodparam"><span class="type">DateTime</span> `$object`</span>
)

### Parameters

`object`  
The mutable <span class="classname">DateTime</span> object that you want
to convert to an immutable version. This object is not modified, but
instead a new <span class="classname">DateTimeImmutable</span> object is
created containing the same date time and timezone information.

### Examples

**Example \#1 Creating an immutable date time object**

``` php
<?php
$date = new DateTime("2014-06-20 11:45 Europe/London");

$immutable = DateTimeImmutable::createFromMutable( $date );
?>
```

### Return Values

Returns a new <span class="classname">DateTimeImmutable</span> instance.

DateTimeImmutable::getLastErrors
================================

Returns the warnings and errors

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">array</span> <span
class="methodname">DateTimeImmutable::getLastErrors</span> ( <span
class="methodparam">void</span> )

Like <span class="methodname">DateTime::getLastErrors</span> but works
with <span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::modify
=========================

Creates a new object with modified timestamp

### Description

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeImmutable</span><span
class="type">false</span></span> <span
class="methodname">DateTimeImmutable::modify</span> ( <span
class="methodparam"><span class="type">string</span> `$modifier`</span>
)

Creates a new <span class="type">DateTimeImmutable</span> object with
modified timestamp. The original object is not modified.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>. The function
modifies this object.

`modifier`  
A date/time string. Valid formats are explained in
<a href="/datetime/formats.html" class="link">Date and Time Formats</a>.

### Return Values

Returns the newly created object or **`FALSE`** on failure.

DateTimeImmutable::\_\_set\_state
=================================

The \_\_set\_state handler

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::\_\_set\_state</span> ( <span
class="methodparam"><span class="type">array</span> `$array`</span> )

Like <span class="methodname">DateTime::\_\_set\_state</span> but works
with <span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::setDate
==========================

Sets the date

### Description

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::setDate</span> ( <span
class="methodparam"><span class="type">int</span> `$year`</span> , <span
class="methodparam"><span class="type">int</span> `$month`</span> ,
<span class="methodparam"><span class="type">int</span> `$day`</span> )

Like <span class="methodname">DateTime::setDate</span> but works with
<span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::setISODate
=============================

Sets the ISO date

### Description

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::setISODate</span> ( <span
class="methodparam"><span class="type">int</span> `$year`</span> , <span
class="methodparam"><span class="type">int</span> `$week`</span> \[,
<span class="methodparam"><span class="type">int</span> `$day`<span
class="initializer"> = 1</span></span> \] )

Like <span class="methodname">DateTime::setISODate</span> but works with
<span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::setTime
==========================

Sets the time

### Description

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::setTime</span> ( <span
class="methodparam"><span class="type">int</span> `$hour`</span> , <span
class="methodparam"><span class="type">int</span> `$minute`</span> \[,
<span class="methodparam"><span class="type">int</span> `$second`<span
class="initializer"> = 0</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$microsecond`<span
class="initializer"> = 0</span></span> \]\] )

Like <span class="methodname">DateTime::setTime</span> but works with
<span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::setTimestamp
===============================

Sets the date and time based on a Unix timestamp

### Description

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::setTimestamp</span> ( <span
class="methodparam"><span class="type">int</span> `$timestamp`</span> )

Like <span class="methodname">DateTime::setTimestamp</span> but works
with <span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::setTimezone
==============================

Sets the time zone

### Description

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::setTimezone</span> ( <span
class="methodparam"><span class="type">DateTimeZone</span>
`$timezone`</span> )

Like <span class="methodname">DateTime::setTimezone</span> but works
with <span class="classname">DateTimeImmutable</span>.

DateTimeImmutable::sub
======================

Subtracts an amount of days, months, years, hours, minutes and seconds

### Description

<span class="modifier">public</span> <span
class="type">DateTimeImmutable</span> <span
class="methodname">DateTimeImmutable::sub</span> ( <span
class="methodparam"><span class="type">DateInterval</span>
`$interval`</span> )

Like <span class="methodname">DateTime::sub</span> but works with <span
class="classname">DateTimeImmutable</span>.

Introduction
------------

DateTimeInterface is meant so that both DateTime and DateTimeImmutable
can be type hinted for. It is not possible to implement this interface
with userland classes.

Class synopsis
--------------

**DateTimeInterface**

<span class="ooclass"> class **DateTimeInterface** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::ATOM` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::COOKIE` <span class="initializer"> = "l, d-M-Y H:i:s
T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::ISO8601` <span class="initializer"> =
"Y-m-d\\TH:i:sO"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC822` <span class="initializer"> = "D, d M y H:i:s
O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC850` <span class="initializer"> = "l, d-M-y H:i:s
T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC1036` <span class="initializer"> = "D, d M y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC1123` <span class="initializer"> = "D, d M Y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC7231` <span class="initializer"> = "D, d M Y
H:i:s \\G\\M\\T"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC2822` <span class="initializer"> = "D, d M Y
H:i:s O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC3339` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RFC3339_EXTENDED` <span class="initializer"> =
"Y-m-d\\TH:i:s.vP"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::RSS` <span class="initializer"> = "D, d M Y H:i:s
O"</span> ;

<span class="modifier">const</span> <span class="type">string</span>
`DateTimeInterface::W3C` <span class="initializer"> =
"Y-m-d\\TH:i:sP"</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span class="type"><span
class="type">DateInterval</span><span class="type">false</span></span>
<span class="methodname">diff</span> ( <span class="methodparam"><span
class="type">DateTimeInterface</span> `$targetObject`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$absolute`<span
class="initializer"> = **`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">format</span> ( <span class="methodparam"><span
class="type">string</span> `$format`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">getOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getTimestamp</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeZone</span><span class="type">false</span></span>
<span class="methodname">getTimezone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">\_\_wakeup</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`DateTimeInterface::ATOM`**  
**`DATE_ATOM`**  
<span class="simpara"> Atom (example: 2005-08-15T15:52:01+00:00) </span>

**`DateTimeInterface::COOKIE`**  
**`DATE_COOKIE`**  
<span class="simpara"> HTTP Cookies (example: Monday, 15-Aug-2005
15:52:01 UTC) </span>

**`DateTimeInterface::ISO8601`**  
**`DATE_ISO8601`**  
<span class="simpara"> ISO-8601 (example: 2005-08-15T15:52:01+0000)
</span>

> **Note**: <span class="simpara"> This format is not compatible with
> ISO-8601, but is left this way for backward compatibility reasons. Use
> **`DateTime::ATOM`** or **`DATE_ATOM`** for compatibility with
> ISO-8601 instead. </span>

**`DateTimeInterface::RFC822`**  
**`DATE_RFC822`**  
<span class="simpara"> RFC 822 (example: Mon, 15 Aug 05 15:52:01 +0000)
</span>

**`DateTimeInterface::RFC850`**  
**`DATE_RFC850`**  
<span class="simpara"> RFC 850 (example: Monday, 15-Aug-05 15:52:01 UTC)
</span>

**`DateTimeInterface::RFC1036`**  
**`DATE_RFC1036`**  
<span class="simpara"> RFC 1036 (example: Mon, 15 Aug 05 15:52:01 +0000)
</span>

**`DateTimeInterface::RFC1123`**  
**`DATE_RFC1123`**  
<span class="simpara"> RFC 1123 (example: Mon, 15 Aug 2005 15:52:01
+0000) </span>

**`DateTimeInterface::RFC7231`**  
**`DATE_RFC7231`**  
<span class="simpara"> RFC 7231 (since PHP 7.0.19 and 7.1.5) (example:
Sat, 30 Apr 2016 17:52:13 GMT) </span>

**`DateTimeInterface::RFC2822`**  
**`DATE_RFC2822`**  
<span class="simpara"> RFC 2822 (example: Mon, 15 Aug 2005 15:52:01
+0000) </span>

**`DateTimeInterface::RFC3339`**  
**`DATE_RFC3339`**  
<span class="simpara"> Same as **`DATE_ATOM`** (since PHP 5.1.3) </span>

**`DateTimeInterface::RFC3339_EXTENDED`**  
**`DATE_RFC3339_EXTENDED`**  
<span class="simpara"> RFC 3339 EXTENDED format (since PHP 7.0.0)
(example: 2005-08-15T15:52:01.000+00:00) </span>

**`DateTimeInterface::RSS`**  
**`DATE_RSS`**  
<span class="simpara"> RSS (example: Mon, 15 Aug 2005 15:52:01 +0000)
</span>

**`DateTimeInterface::W3C`**  
**`DATE_W3C`**  
<span class="simpara"> World Wide Web Consortium (example:
2005-08-15T15:52:01+00:00) </span>

Changelog
---------

| Version | Description                                                                                                                                                                               |
|---------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 7.2.0   | The class constants of <span class="classname">DateTime</span> are now defined on <span class="classname">DateTimeInterface</span>.                                                       |
| 5.5.8   | Trying to implement <span class="classname">DateTimeInterface</span> raises a fatal error now. Formerly implementing the interface didn't raise an error, but the behavior was erroneous. |

DateTime::diff
==============

DateTimeImmutable::diff
=======================

DateTimeInterface::diff
=======================

date\_diff
==========

Returns the difference between two DateTime objects

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">DateInterval</span><span class="type">false</span></span>
<span class="methodname">DateTime::diff</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$targetObject`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$absolute`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">DateInterval</span><span class="type">false</span></span>
<span class="methodname">DateTimeImmutable::diff</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$targetObject`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$absolute`<span class="initializer"> =
**`FALSE`**</span></span> \] )

<span class="modifier">public</span> <span class="type"><span
class="type">DateInterval</span><span class="type">false</span></span>
<span class="methodname">DateTimeInterface::diff</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$targetObject`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$absolute`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Procedural style

<span class="type"><span class="type">DateInterval</span><span
class="type">false</span></span> <span
class="methodname">date\_diff</span> ( <span class="methodparam"><span
class="type">DateTimeInterface</span> `$originObject`</span> , <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$targetObject`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$absolute`<span class="initializer"> =
**`FALSE`**</span></span> \] )

Returns the difference between two <span
class="classname">DateTimeInterface</span> objects.

### Parameters

`datetime`  
The date to compare to.

`absolute`  
Should the interval be forced to be positive?

### Return Values

The <span class="classname">DateInterval</span> object represents the
difference between the two dates or **`FALSE`** on failure.

The return value more specifically represents the interval to apply to
the original object (`$this` or `$originObject`) to arrive at the
`$targetObject`. This process is not always reversible.

### Examples

**Example \#1 <span class="function">DateTime::diff</span> example**

Object oriented style

``` php
<?php
$origin = new DateTime('2009-10-11');
$target = new DateTime('2009-10-13');
$interval = $origin->diff($target);
echo $interval->format('%R%a days');
?>
```

Procedural style

``` php
<?php
$origin = date_create('2009-10-11');
$target = date_create('2009-10-13');
$interval = date_diff($origin, $target);
echo $interval->format('%R%a days');
?>
```

The above examples will output:

    +2 days

**Example \#2 <span class="classname">DateTime</span> object
comparison**

> **Note**:
>
> As of PHP 5.2.2, DateTime objects can be compared using
> <a href="/language/operators/comparison.html" class="link">comparison operators</a>.

``` php
<?php
$date1 = new DateTime("now");
$date2 = new DateTime("tomorrow");

var_dump($date1 == $date2);
var_dump($date1 < $date2);
var_dump($date1 > $date2);
?>
```

The above example will output:

    bool(false)
    bool(true)
    bool(false)

### See Also

-   <span class="function">DateInterval::format</span>
-   <span class="function">DateTime::add</span>
-   <span class="function">DateTime::sub</span>

DateTime::format
================

DateTimeImmutable::format
=========================

DateTimeInterface::format
=========================

date\_format
============

Returns date formatted according to given format

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">DateTime::format</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">DateTimeImmutable::format</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">string</span><span class="type">false</span></span> <span
class="methodname">DateTimeInterface::format</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

Procedural style

<span class="type"><span class="type">string</span><span
class="type">false</span></span> <span
class="methodname">date\_format</span> ( <span class="methodparam"><span
class="type">DateTimeInterface</span> `$object`</span> , <span
class="methodparam"><span class="type">string</span> `$format`</span> )

Returns date formatted according to given format.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>

`format`  
The format of the outputted date <span class="type">string</span>. See
the formatting options below. There are also several
<a href="/class/datetimeinterface.html#Predefined%20Constants" class="link">predefined date constants</a>
that may be used instead, so for example **`DATE_RSS`** contains the
format string *'D, d M Y H:i:s'*.

|  `format` character | Description                                                                                                                                                                                                                                                                                                      | Example returned values                       |
|:-------------------:|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
|        *Day*        | ---                                                                                                                                                                                                                                                                                                              | ---                                           |
|         *d*         | Day of the month, 2 digits with leading zeros                                                                                                                                                                                                                                                                    | *01* to *31*                                  |
|         *D*         | A textual representation of a day, three letters                                                                                                                                                                                                                                                                 | *Mon* through *Sun*                           |
|         *j*         | Day of the month without leading zeros                                                                                                                                                                                                                                                                           | *1* to *31*                                   |
| *l* (lowercase 'L') | A full textual representation of the day of the week                                                                                                                                                                                                                                                             | *Sunday* through *Saturday*                   |
|         *N*         | ISO-8601 numeric representation of the day of the week                                                                                                                                                                                                                                                           | *1* (for Monday) through *7* (for Sunday)     |
|         *S*         | English ordinal suffix for the day of the month, 2 characters                                                                                                                                                                                                                                                    | *st*, *nd*, *rd* or *th*. Works well with *j* |
|         *w*         | Numeric representation of the day of the week                                                                                                                                                                                                                                                                    | *0* (for Sunday) through *6* (for Saturday)   |
|         *z*         | The day of the year (starting from 0)                                                                                                                                                                                                                                                                            | *0* through *365*                             |
|        *Week*       | ---                                                                                                                                                                                                                                                                                                              | ---                                           |
|         *W*         | ISO-8601 week number of year, weeks starting on Monday                                                                                                                                                                                                                                                           | Example: *42* (the 42nd week in the year)     |
|       *Month*       | ---                                                                                                                                                                                                                                                                                                              | ---                                           |
|         *F*         | A full textual representation of a month, such as January or March                                                                                                                                                                                                                                               | *January* through *December*                  |
|         *m*         | Numeric representation of a month, with leading zeros                                                                                                                                                                                                                                                            | *01* through *12*                             |
|         *M*         | A short textual representation of a month, three letters                                                                                                                                                                                                                                                         | *Jan* through *Dec*                           |
|         *n*         | Numeric representation of a month, without leading zeros                                                                                                                                                                                                                                                         | *1* through *12*                              |
|         *t*         | Number of days in the given month                                                                                                                                                                                                                                                                                | *28* through *31*                             |
|        *Year*       | ---                                                                                                                                                                                                                                                                                                              | ---                                           |
|         *L*         | Whether it's a leap year                                                                                                                                                                                                                                                                                         | *1* if it is a leap year, *0* otherwise.      |
|         *o*         | ISO-8601 week-numbering year. This has the same value as *Y*, except that if the ISO week number (*W*) belongs to the previous or next year, that year is used instead.                                                                                                                                          | Examples: *1999* or *2003*                    |
|         *Y*         | A full numeric representation of a year, 4 digits                                                                                                                                                                                                                                                                | Examples: *1999* or *2003*                    |
|         *y*         | A two digit representation of a year                                                                                                                                                                                                                                                                             | Examples: *99* or *03*                        |
|        *Time*       | ---                                                                                                                                                                                                                                                                                                              | ---                                           |
|         *a*         | Lowercase Ante meridiem and Post meridiem                                                                                                                                                                                                                                                                        | *am* or *pm*                                  |
|         *A*         | Uppercase Ante meridiem and Post meridiem                                                                                                                                                                                                                                                                        | *AM* or *PM*                                  |
|         *B*         | Swatch Internet time                                                                                                                                                                                                                                                                                             | *000* through *999*                           |
|         *g*         | 12-hour format of an hour without leading zeros                                                                                                                                                                                                                                                                  | *1* through *12*                              |
|         *G*         | 24-hour format of an hour without leading zeros                                                                                                                                                                                                                                                                  | *0* through *23*                              |
|         *h*         | 12-hour format of an hour with leading zeros                                                                                                                                                                                                                                                                     | *01* through *12*                             |
|         *H*         | 24-hour format of an hour with leading zeros                                                                                                                                                                                                                                                                     | *00* through *23*                             |
|         *i*         | Minutes with leading zeros                                                                                                                                                                                                                                                                                       | *00* to *59*                                  |
|         *s*         | Seconds with leading zeros                                                                                                                                                                                                                                                                                       | *00* through *59*                             |
|         *u*         | Microseconds. Note that <span class="function">date</span> will always generate *000000* since it takes an <span class="type">int</span> parameter, whereas <span class="methodname">DateTime::format</span> does support microseconds if <span class="classname">DateTime</span> was created with microseconds. | Example: *654321*                             |
|         *v*         | Milliseconds (added in PHP 7.0.0). Same note applies as for *u*.                                                                                                                                                                                                                                                 | Example: *654*                                |
|      *Timezone*     | ---                                                                                                                                                                                                                                                                                                              | ---                                           |
|         *e*         | Timezone identifier                                                                                                                                                                                                                                                                                              | Examples: *UTC*, *GMT*, *Atlantic/Azores*     |
|   *I* (capital i)   | Whether or not the date is in daylight saving time                                                                                                                                                                                                                                                               | *1* if Daylight Saving Time, *0* otherwise.   |
|         *O*         | Difference to Greenwich time (GMT) without colon between hours and minutes                                                                                                                                                                                                                                       | Example: *+0200*                              |
|         *P*         | Difference to Greenwich time (GMT) with colon between hours and minutes                                                                                                                                                                                                                                          | Example: *+02:00*                             |
|         *p*         | The same as *P*, but returns *Z* instead of *+00:00*                                                                                                                                                                                                                                                             | Example: *+02:00*                             |
|         *T*         | Timezone abbreviation                                                                                                                                                                                                                                                                                            | Examples: *EST*, *MDT* ...                    |
|         *Z*         | Timezone offset in seconds. The offset for timezones west of UTC is always negative, and for those east of UTC is always positive.                                                                                                                                                                               | *-43200* through *50400*                      |
|   *Full Date/Time*  | ---                                                                                                                                                                                                                                                                                                              | ---                                           |
|         *c*         | ISO 8601 date                                                                                                                                                                                                                                                                                                    | 2004-02-12T15:19:21+00:00                     |
|         *r*         | <a href="http://www.faqs.org/rfcs/rfc2822" class="link external">» RFC 2822</a> formatted date                                                                                                                                                                                                                   | Example: *Thu, 21 Dec 2000 16:01:07 +0200*    |
|         *U*         | Seconds since the Unix Epoch (January 1 1970 00:00:00 GMT)                                                                                                                                                                                                                                                       | See also <span class="function">time</span>   |

Unrecognized characters in the format string will be printed as-is. The
*Z* format will always return *0* when using <span
class="function">gmdate</span>.

> **Note**:
>
> Since this function only accepts <span class="type">int</span>
> timestamps the *u* format character is only useful when using the
> <span class="function">date\_format</span> function with user based
> timestamps created with <span class="function">date\_create</span>.

### Return Values

Returns the formatted date string on success or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::format</span> example**

Object oriented style

``` php
<?php
$date = new DateTime('2000-01-01');
echo $date->format('Y-m-d H:i:s');
?>
```

Procedural style

``` php
<?php
$date = date_create('2000-01-01');
echo date_format($date, 'Y-m-d H:i:s');
?>
```

The above example will output:

    2000-01-01 00:00:00

### Notes

This method does not use locales. All output is in English.

### See Also

-   <span class="function">date</span>

DateTime::getOffset
===================

DateTimeImmutable::getOffset
============================

DateTimeInterface::getOffset
============================

date\_offset\_get
=================

Returns the timezone offset

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">DateTime::getOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">DateTimeImmutable::getOffset</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">DateTimeInterface::getOffset</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">date\_offset\_get</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$object`</span> )

Returns the timezone offset.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>

### Return Values

Returns the timezone offset in seconds from UTC on success or
**`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::getOffset</span>
example**

Object oriented style

``` php
<?php
$winter = new DateTime('2010-12-21', new DateTimeZone('America/New_York'));
$summer = new DateTime('2008-06-21', new DateTimeZone('America/New_York'));

echo $winter->getOffset() . "\n";
echo $summer->getOffset() . "\n";
?>
```

Procedural style

``` php
<?php
$winter = date_create('2010-12-21', timezone_open('America/New_York'));
$summer = date_create('2008-06-21', timezone_open('America/New_York'));

echo date_offset_get($winter) . "\n";
echo date_offset_get($summer) . "\n";
?>
```

The above examples will output:

    -18000
    -14400

Note: -18000 = -5 hours, -14400 = -4 hours.

DateTime::getTimestamp
======================

DateTimeImmutable::getTimestamp
===============================

DateTimeInterface::getTimestamp
===============================

date\_timestamp\_get
====================

Gets the Unix timestamp

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">DateTime::getTimestamp</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">DateTimeImmutable::getTimestamp</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">DateTimeInterface::getTimestamp</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">int</span> <span
class="methodname">date\_timestamp\_get</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$object`</span> )

Gets the Unix timestamp.

### Parameters

This function has no parameters.

### Return Values

Returns the Unix timestamp representing the date.

### Examples

**Example \#1 <span class="function">DateTime::getTimestamp</span>
example**

Object oriented style

``` php
<?php
$date = new DateTime();
echo $date->getTimestamp();
?>
```

Procedural style

``` php
<?php
$date = date_create();
echo date_timestamp_get($date);
?>
```

The above examples will output something similar to:

    1272509157

### Notes

Using *U* as the parameter to <span
class="function">DateTime::format</span> is an alternative when using
PHP 5.2.

### See Also

-   <span class="function">DateTime::setTimestamp</span>
-   <span class="function">DateTime::format</span>

DateTime::getTimezone
=====================

DateTimeImmutable::getTimezone
==============================

DateTimeInterface::getTimezone
==============================

date\_timezone\_get
===================

Return time zone relative to given DateTime

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeZone</span><span class="type">false</span></span>
<span class="methodname">DateTime::getTimezone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeZone</span><span class="type">false</span></span>
<span class="methodname">DateTimeImmutable::getTimezone</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeZone</span><span class="type">false</span></span>
<span class="methodname">DateTimeInterface::getTimezone</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type"><span class="type">DateTimeZone</span><span
class="type">false</span></span> <span
class="methodname">date\_timezone\_get</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$object`</span> )

Return time zone relative to given DateTime.

### Parameters

`object`  
Procedural style only: A <span class="classname">DateTime</span> object
returned by <span class="function">date\_create</span>

### Return Values

Returns a <span class="classname">DateTimeZone</span> object on success
or **`FALSE`** on failure.

### Examples

**Example \#1 <span class="function">DateTime::getTimezone</span>
example**

Object oriented style

``` php
<?php
$date = new DateTime(null, new DateTimeZone('Europe/London'));
$tz = $date->getTimezone();
echo $tz->getName();
?>
```

Procedural style

``` php
<?php
$date = date_create(null, timezone_open('Europe/London'));
$tz = date_timezone_get($date);
echo timezone_name_get($tz);
?>
```

The above examples will output:

    Europe/London

### See Also

-   <span class="function">DateTime::setTimezone</span>

DateTime::\_\_wakeup
====================

DateTimeImmutable::\_\_wakeup
=============================

DateTimeInterface::\_\_wakeup
=============================

The \_\_wakeup handler

### Description

<span class="modifier">public</span> <span
class="methodname">DateTime::\_\_wakeup</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">DateTimeImmutable::\_\_wakeup</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="methodname">DateTimeInterface::\_\_wakeup</span> ( <span
class="methodparam">void</span> )

The
<a href="/language/oop5/magic.html#object.wakeup" class="link">__wakeup()</a>
handler.

### Parameters

This function has no parameters.

### Return Values

Initializes a DateTime object.

Introduction
------------

Representation of time zone.

Class synopsis
--------------

**DateTimeZone**

<span class="ooclass"> class **DateTimeZone** </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::AFRICA` <span class="initializer"> = 1</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::AMERICA` <span class="initializer"> = 2</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::ANTARCTICA` <span class="initializer"> = 4</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::ARCTIC` <span class="initializer"> = 8</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::ASIA` <span class="initializer"> = 16</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::ATLANTIC` <span class="initializer"> = 32</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::AUSTRALIA` <span class="initializer"> = 64</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::EUROPE` <span class="initializer"> = 128</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::INDIAN` <span class="initializer"> = 256</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::PACIFIC` <span class="initializer"> = 512</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::UTC` <span class="initializer"> = 1024</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::ALL` <span class="initializer"> = 2047</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::ALL_WITH_BC` <span class="initializer"> = 4095</span> ;

<span class="modifier">const</span> <span class="type">int</span>
`DateTimeZone::PER_COUNTRY` <span class="initializer"> = 4096</span> ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$timezone`</span>
)

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">getLocation</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">getName</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">getOffset</span> ( <span class="methodparam"><span
class="type">DateTimeInterface</span> `$datetime`</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">getTransitions</span> (\[ <span
class="methodparam"><span class="type">int</span> `$timestampBegin`<span
class="initializer"> = **`PHP_INT_MIN`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$timestampEnd`<span
class="initializer"> = **`PHP_INT_MAX`**</span></span> \]\] )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">listAbbreviations</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">listIdentifiers</span> (\[ <span
class="methodparam"><span class="type">int</span> `$timezoneGroup`<span
class="initializer"> = DateTimeZone::ALL</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$countryCode`<span
class="initializer"> = **`NULL`**</span></span> \]\] )

}

Predefined Constants
--------------------

**`DateTimeZone::AFRICA`**  
Africa time zones.

**`DateTimeZone::AMERICA`**  
America time zones.

**`DateTimeZone::ANTARCTICA`**  
Antarctica time zones.

**`DateTimeZone::ARCTIC`**  
Arctic time zones.

**`DateTimeZone::ASIA`**  
Asia time zones.

**`DateTimeZone::ATLANTIC`**  
Atlantic time zones.

**`DateTimeZone::AUSTRALIA`**  
Australia time zones.

**`DateTimeZone::EUROPE`**  
Europe time zones.

**`DateTimeZone::INDIAN`**  
Indian time zones.

**`DateTimeZone::PACIFIC`**  
Pacific time zones.

**`DateTimeZone::UTC`**  
UTC time zones.

**`DateTimeZone::ALL`**  
All time zones.

**`DateTimeZone::ALL_WITH_BC`**  
All time zones including backwards compatible.

**`DateTimeZone::PER_COUNTRY`**  
Time zones per country.

DateTimeZone::\_\_construct
===========================

timezone\_open
==============

Creates new DateTimeZone object

### Description

Object oriented style

<span class="modifier">public</span> <span
class="methodname">DateTimeZone::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$timezone`</span>
)

Procedural style

<span class="type"><span class="type">DateTimeZone</span><span
class="type">false</span></span> <span
class="methodname">timezone\_open</span> ( <span
class="methodparam"><span class="type">string</span> `$timezone`</span>
)

Creates new DateTimeZone object.

### Parameters

`timezone`  
One of the supported
<a href="/timezones.html" class="link">timezone names</a> or an offset
value (+0200).

### Return Values

Returns <span class="classname">DateTimeZone</span> on success.
Procedural style returns **`FALSE`** on failure.

### Errors/Exceptions

This method throws <span class="classname">Exception</span> if the
timezone supplied is not recognised as a valid timezone.

### Changelog

| Version | Description                                     |
|---------|-------------------------------------------------|
| 5.5.10  | The `timezone` parameter accepts offset values. |

### Examples

**Example \#1 Catching errors when instantiating <span
class="classname">DateTimeZone</span>**

``` php
<?php
// Error handling by catching exceptions
$timezones = array('Europe/London', 'Mars/Phobos', 'Jupiter/Europa');

foreach ($timezones as $tz) {
    try {
        $mars = new DateTimeZone($tz);
    } catch(Exception $e) {
        echo $e->getMessage() . '<br />';
    }
}
?>
```

The above example will output:

    DateTimeZone::__construct() [datetimezone.--construct]: Unknown or bad timezone (Mars/Phobos)
    DateTimeZone::__construct() [datetimezone.--construct]: Unknown or bad timezone (Jupiter/Europa)

DateTimeZone::getLocation
=========================

timezone\_location\_get
=======================

Returns location information for a timezone

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">DateTimeZone::getLocation</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">timezone\_location\_get</span> ( <span
class="methodparam"><span class="type">DateTimeZone</span>
`$object`</span> )

Returns location information for a timezone, including country code,
latitude/longitude and comments.

### Parameters

` object`  
Procedural style only: A <span class="classname">DateTimeZone</span>
object returned by <span class="function">timezone\_open</span>

### Return Values

Array containing location information about timezone or **`FALSE`** on
failure.

### Examples

**Example \#1 <span class="function">DateTimeZone::getLocation</span>
example**

``` php
<?php
$tz = new DateTimeZone("Europe/Prague");
print_r($tz->getLocation());
print_r(timezone_location_get($tz));
?>
```

The above example will output:

    Array
    (
        [country_code] => CZ
        [latitude] => 50.08333
        [longitude] => 14.43333
        [comments] => 
    )
    Array
    (
        [country_code] => CZ
        [latitude] => 50.08333
        [longitude] => 14.43333
        [comments] => 
    )

DateTimeZone::getName
=====================

timezone\_name\_get
===================

Returns the name of the timezone

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">DateTimeZone::getName</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type">string</span> <span
class="methodname">timezone\_name\_get</span> ( <span
class="methodparam"><span class="type">DateTimeZone</span>
`$object`</span> )

Returns the name of the timezone.

### Parameters

`object`  
The <span class="classname">DateTimeZone</span> for which to get a name.

### Return Values

One of the timezone names in the
<a href="/timezones.html" class="link">list of timezones</a>.

DateTimeZone::getOffset
=======================

timezone\_offset\_get
=====================

Returns the timezone offset from GMT

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">int</span><span class="type">false</span></span> <span
class="methodname">DateTimeZone::getOffset</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$datetime`</span> )

Procedural style

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">timezone\_offset\_get</span> ( <span
class="methodparam"><span class="type">DateTimeZone</span>
`$object`</span> , <span class="methodparam"><span
class="type">DateTimeInterface</span> `$datetime`</span> )

This function returns the offset to GMT for the date/time specified in
the `datetime` parameter. The GMT offset is calculated with the timezone
information contained in the DateTimeZone object being used.

### Parameters

` object`  
Procedural style only: A <span class="classname">DateTimeZone</span>
object returned by <span class="function">timezone\_open</span>

`datetime`  
DateTime that contains the date/time to compute the offset from.

### Return Values

Returns time zone offset in seconds on success or **`FALSE`** on
failure.

### Changelog

| Version       | Description                                                                                                                           |
|---------------|---------------------------------------------------------------------------------------------------------------------------------------|
| 5.5.19, 5.6.3 | `datetime` type changed to <span class="interfacename">DateTimeInterface</span>. Previously, <span class="classname">DateTime</span>. |

### Examples

**Example \#1 <span class="function">DateTimeZone::getOffset</span>
examples**

``` php
<?php
// Create two timezone objects, one for Taipei (Taiwan) and one for
// Tokyo (Japan)
$dateTimeZoneTaipei = new DateTimeZone("Asia/Taipei");
$dateTimeZoneJapan = new DateTimeZone("Asia/Tokyo");

// Create two DateTime objects that will contain the same Unix timestamp, but
// have different timezones attached to them.
$dateTimeTaipei = new DateTime("now", $dateTimeZoneTaipei);
$dateTimeJapan = new DateTime("now", $dateTimeZoneJapan);

// Calculate the GMT offset for the date/time contained in the $dateTimeTaipei
// object, but using the timezone rules as defined for Tokyo
// ($dateTimeZoneJapan).
$timeOffset = $dateTimeZoneJapan->getOffset($dateTimeTaipei);

// Should show int(32400) (for dates after Sat Sep 8 01:00:00 1951 JST).
var_dump($timeOffset);
?>
```

DateTimeZone::getTransitions
============================

timezone\_transitions\_get
==========================

Returns all transitions for the timezone

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">DateTimeZone::getTransitions</span> (\[ <span
class="methodparam"><span class="type">int</span> `$timestampBegin`<span
class="initializer"> = **`PHP_INT_MIN`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$timestampEnd`<span
class="initializer"> = **`PHP_INT_MAX`**</span></span> \]\] )

Procedural style

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">timezone\_transitions\_get</span> ( <span
class="methodparam"><span class="type">DateTimeZone</span>
`$object`</span> \[, <span class="methodparam"><span
class="type">int</span> `$timestampBegin`<span class="initializer"> =
**`PHP_INT_MIN`**</span></span> \[, <span class="methodparam"><span
class="type">int</span> `$timestampEnd`<span class="initializer"> =
**`PHP_INT_MAX`**</span></span> \]\] )

### Parameters

` object`  
Procedural style only: A <span class="classname">DateTimeZone</span>
object returned by <span class="function">timezone\_open</span>

`timestampBegin`  
Begin timestamp.

`timestampEnd`  
End timestamp.

### Return Values

Returns a numerically indexed array of transition arrays on success, or
**`FALSE`** on failure.

| Key      | Type                             | Description                                  |
|----------|----------------------------------|----------------------------------------------|
| *ts*     | <span class="type">int</span>    | Unix timestamp                               |
| *time*   | <span class="type">string</span> | **`DateTimeInterface::ISO8601`** time string |
| *offset* | <span class="type">int</span>    | Offset to UTC in seconds                     |
| *isdst*  | <span class="type">bool</span>   | Whether daylight saving time is active       |
| *abbr*   | <span class="type">string</span> | Timezone abbreviation                        |

### Examples

**Example \#1 A <span class="function">timezone\_transitions\_get</span>
example**

``` php
<?php
$timezone = new DateTimeZone("Europe/London");
$transitions = $timezone->getTransitions();
print_r(array_slice($transitions, 0, 3));
?>
```

The above example will output something similar to:

    Array
    (
        [0] => Array
            (
                [ts] => -9223372036854775808
                [time] => -292277022657-01-27T08:29:52+0000
                [offset] => 3600
                [isdst] => 1
                [abbr] => BST
            )

        [1] => Array
            (
                [ts] => -1691964000
                [time] => 1916-05-21T02:00:00+0000
                [offset] => 3600
                [isdst] => 1
                [abbr] => BST
            )

        [2] => Array
            (
                [ts] => -1680472800
                [time] => 1916-10-01T02:00:00+0000
                [offset] => 0
                [isdst] => 
                [abbr] => GMT
            )

    )

DateTimeZone::listAbbreviations
===============================

timezone\_abbreviations\_list
=============================

Returns associative array containing dst, offset and the timezone name

### Description

Object oriented style

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">DateTimeZone::listAbbreviations</span> ( <span
class="methodparam">void</span> )

Procedural style

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">timezone\_abbreviations\_list</span> ( <span
class="methodparam">void</span> )

> **Note**:
>
> The data for this function are precompiled for performance reasons,
> and are not updated when using a newer
> <a href="https://pecl.php.net/package/timezonedb" class="link external">» timezonedb</a>.

### Return Values

Returns array on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span
class="function">timezone\_abbreviations\_list</span> example**

``` php
<?php
$timezone_abbreviations = DateTimeZone::listAbbreviations();
print_r($timezone_abbreviations["acst"]);
?>
```

The above example will output something similar to:

    Array
    (
        [0] => Array
            (
                [dst] => 1
                [offset] => -14400
                [timezone_id] => America/Porto_Acre
            )

        [1] => Array
            (
                [dst] => 1
                [offset] => -14400
                [timezone_id] => America/Eirunepe
            )

        [2] => Array
            (
                [dst] => 1
                [offset] => -14400
                [timezone_id] => America/Rio_Branco
            )

        [3] => Array
            (
                [dst] => 1
                [offset] => -14400
                [timezone_id] => Brazil/Acre
            )

    )

### See Also

-   <span class="function">timezone\_identifiers\_list</span>

DateTimeZone::listIdentifiers
=============================

timezone\_identifiers\_list
===========================

Returns a numerically indexed array containing all defined timezone
identifiers

### Description

Object oriented style

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type"><span
class="type">array</span><span class="type">false</span></span> <span
class="methodname">DateTimeZone::listIdentifiers</span> (\[ <span
class="methodparam"><span class="type">int</span> `$timezoneGroup`<span
class="initializer"> = DateTimeZone::ALL</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$countryCode`<span
class="initializer"> = **`NULL`**</span></span> \]\] )

Procedural style

<span class="type"><span class="type">array</span><span
class="type">false</span></span> <span
class="methodname">timezone\_identifiers\_list</span> (\[ <span
class="methodparam"><span class="type">int</span> `$timezoneGroup`<span
class="initializer"> = DateTimeZone::ALL</span></span> \[, <span
class="methodparam"><span class="type">string</span> `$countryCode`<span
class="initializer"> = **`NULL`**</span></span> \]\] )

### Parameters

`timezoneGroup`  
One of the <span class="classname">DateTimeZone</span> class constants
(or a combination).

`countryCode`  
A two-letter ISO 3166-1 compatible country code.

> **Note**: <span class="simpara"> This option is only used when
> `timezoneGroup` is set to **`DateTimeZone::PER_COUNTRY`**. </span>

### Return Values

Returns array on success or **`FALSE`** on failure.

### Examples

**Example \#1 A <span
class="function">timezone\_identifiers\_list</span> example**

``` php
<?php
$timezone_identifiers = DateTimeZone::listIdentifiers();
for ($i=0; $i < 5; $i++) {
    echo "$timezone_identifiers[$i]\n";
}
?>
```

The above example will output something similar to:

    Africa/Abidjan
    Africa/Accra
    Africa/Addis_Ababa
    Africa/Algiers
    Africa/Asmara

### See Also

-   <span class="function">timezone\_abbreviations\_list</span>

Introduction
------------

Represents a date interval.

A date interval stores either a fixed amount of time (in years, months,
days, hours etc) or a relative time string in the format that <span
class="classname">DateTime</span>'s constructor supports.

More specifically, the information in an object of the <span
class="classname">DateInterval</span> class is an instruction to get
from one date/time to another date/time. This process is not always
reversible.

A common way to create a <span class="classname">DateInterval</span>
object is by calculating the difference between two date/time objects
through <span class="function">DateTimeInterface::diff</span>.

Class synopsis
--------------

**DateInterval**

<span class="ooclass"> class **DateInterval** </span> {

/\* Properties \*/

<span class="modifier">public</span> <span class="type">int</span> `$y`
;

<span class="modifier">public</span> <span class="type">int</span> `$m`
;

<span class="modifier">public</span> <span class="type">int</span> `$d`
;

<span class="modifier">public</span> <span class="type">int</span> `$h`
;

<span class="modifier">public</span> <span class="type">int</span> `$i`
;

<span class="modifier">public</span> <span class="type">int</span> `$s`
;

<span class="modifier">public</span> <span class="type">float</span>
`$f` ;

<span class="modifier">public</span> <span class="type">int</span>
`$invert` ;

<span class="modifier">public</span> <span class="type">mixed</span>
`$days` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$duration`</span>
)

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">DateInterval</span>
<span class="methodname">createFromDateString</span> ( <span
class="methodparam"><span class="type">string</span> `$datetime`</span>
)

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">format</span> ( <span class="methodparam"><span
class="type">string</span> `$format`</span> )

}

Properties
----------

`y`  
Number of years.

`m`  
Number of months.

`d`  
Number of days.

`h`  
Number of hours.

`i`  
Number of minutes.

`s`  
Number of seconds.

`f`  
Number of microseconds, as a fraction of a second.

`invert`  
Is *1* if the interval represents a negative time period and *0*
otherwise. See <span class="methodname">DateInterval::format</span>.

`days`  
If the DateInterval object was created by <span
class="function">DateTime::diff</span>, then this is the total number of
days between the start and end dates. Otherwise, `days` will be
**`FALSE`**.

Before PHP 5.4.20/5.5.4 instead of **`FALSE`** you will receive -99999
upon accessing the property.

Changelog
---------

| Version | Description                 |
|---------|-----------------------------|
| 7.1.0   | The `f` property was added. |

DateInterval::\_\_construct
===========================

Creates a new DateInterval object

### Description

<span class="modifier">public</span> <span
class="methodname">DateInterval::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$duration`</span>
)

Creates a new DateInterval object.

### Parameters

`duration`  
An interval specification.

The format starts with the letter *P*, for “period.” Each duration
period is represented by an integer value followed by a period
designator. If the duration contains time elements, that portion of the
specification is preceded by the letter *T*.

| Period Designator | Description                                                            |
|-------------------|------------------------------------------------------------------------|
| *Y*               | years                                                                  |
| *M*               | months                                                                 |
| *D*               | days                                                                   |
| *W*               | weeks. These get converted into days, so can not be combined with *D*. |
| *H*               | hours                                                                  |
| *M*               | minutes                                                                |
| *S*               | seconds                                                                |

Here are some simple examples. Two days is *P2D*. Two seconds is *PT2S*.
Six years and five minutes is *P6YT5M*.

> **Note**:
>
> The unit types must be entered from the largest scale unit on the left
> to the smallest scale unit on the right. So years before months,
> months before days, days before minutes, etc. Thus one year and four
> days must be represented as *P1Y4D*, not *P4D1Y*.

The specification can also be represented as a date time. A sample of
one year and four days would be *P0001-00-04T00:00:00*. But the values
in this format can not exceed a given period's roll-over-point (e.g.
*25* hours is invalid).

These formats are based on the
<a href="http://en.wikipedia.org/wiki/Iso8601#Durations" class="link external">» ISO 8601 duration specification</a>.

### Errors/Exceptions

Throws an <span class="classname">Exception</span> when the `duration`
cannot be parsed as an interval.

### Examples

**Example \#1 <span class="classname">DateInterval</span> example**

``` php
<?php

$interval = new DateInterval('P2Y4DT6H8M');
var_dump($interval);

?>
```

The above example will output:

    object(DateInterval)#1 (8) {
      ["y"]=>
      int(2)
      ["m"]=>
      int(0)
      ["d"]=>
      int(4)
      ["h"]=>
      int(6)
      ["i"]=>
      int(8)
      ["s"]=>
      int(0)
      ["invert"]=>
      int(0)
      ["days"]=>
      bool(false)
    }

### See Also

-   <span class="function">DateInterval::format</span>
-   <span class="function">DateTime::add</span>
-   <span class="function">DateTime::sub</span>
-   <span class="function">DateTime::diff</span>

DateInterval::createFromDateString
==================================

Sets up a DateInterval from the relative parts of the string

### Description

<span class="modifier">public</span> <span
class="modifier">static</span> <span class="type">DateInterval</span>
<span class="methodname">DateInterval::createFromDateString</span> (
<span class="methodparam"><span class="type">string</span>
`$datetime`</span> )

Uses the normal date parsers and sets up a DateInterval from the
relative parts of the parsed string.

### Parameters

`datetime`  
A date with relative parts. Specifically, the
<a href="/datetime/formats.html#Relative%20Formats" class="link">relative formats</a>
supported by the parser used for <span class="function">strtotime</span>
and <span class="classname">DateTime</span> will be used to construct
the DateInterval.

### Examples

**Example \#1 Parsing valid date intervals**

``` php
<?php
// Each set of intervals is equal.
$i = new DateInterval('P1D');
$i = DateInterval::createFromDateString('1 day');

$i = new DateInterval('P2W');
$i = DateInterval::createFromDateString('2 weeks');

$i = new DateInterval('P3M');
$i = DateInterval::createFromDateString('3 months');

$i = new DateInterval('P4Y');
$i = DateInterval::createFromDateString('4 years');

$i = new DateInterval('P1Y1D');
$i = DateInterval::createFromDateString('1 year + 1 day');

$i = new DateInterval('P1DT12H');
$i = DateInterval::createFromDateString('1 day + 12 hours');

$i = new DateInterval('PT3600S');
$i = DateInterval::createFromDateString('3600 seconds');
?>
```

### Return Values

Returns a new <span class="classname">DateInterval</span> instance.

DateInterval::format
====================

Formats the interval

### Description

<span class="modifier">public</span> <span class="type">string</span>
<span class="methodname">DateInterval::format</span> ( <span
class="methodparam"><span class="type">string</span> `$format`</span> )

Formats the interval.

### Parameters

`format`  
| `format` character | Description                                                                                                   | Example values               |
|--------------------|---------------------------------------------------------------------------------------------------------------|------------------------------|
| *%*                | Literal *%*                                                                                                   | *%*                          |
| *Y*                | Years, numeric, at least 2 digits with leading 0                                                              | *01*, *03*                   |
| *y*                | Years, numeric                                                                                                | *1*, *3*                     |
| *M*                | Months, numeric, at least 2 digits with leading 0                                                             | *01*, *03*, *12*             |
| *m*                | Months, numeric                                                                                               | *1*, *3*, *12*               |
| *D*                | Days, numeric, at least 2 digits with leading 0                                                               | *01*, *03*, *31*             |
| *d*                | Days, numeric                                                                                                 | *1*, *3*, *31*               |
| *a*                | Total number of days as a result of a <span class="methodname">DateTime::diff</span> or *(unknown)* otherwise | *4*, *18*, *8123*            |
| *H*                | Hours, numeric, at least 2 digits with leading 0                                                              | *01*, *03*, *23*             |
| *h*                | Hours, numeric                                                                                                | *1*, *3*, *23*               |
| *I*                | Minutes, numeric, at least 2 digits with leading 0                                                            | *01*, *03*, *59*             |
| *i*                | Minutes, numeric                                                                                              | *1*, *3*, *59*               |
| *S*                | Seconds, numeric, at least 2 digits with leading 0                                                            | *01*, *03*, *57*             |
| *s*                | Seconds, numeric                                                                                              | *1*, *3*, *57*               |
| *F*                | Microseconds, numeric, at least 6 digits with leading 0                                                       | *007701*, *052738*, *428291* |
| *f*                | Microseconds, numeric                                                                                         | *7701*, *52738*, *428291*    |
| *R*                | Sign "*-*" when negative, "*+*" when positive                                                                 | *-*, *+*                     |
| *r*                | Sign "*-*" when negative, empty when positive                                                                 | *-*,                         |

### Return Values

Returns the formatted interval.

### Notes

> **Note**:
>
> The <span class="methodname">DateInterval::format</span> method does
> not recalculate carry over points in time strings nor in date
> segments. This is expected because it is not possible to overflow
> values like *"32 days"* which could be interpreted as anything from
> *"1 month and 4 days"* to *"1 month and 1 day"*.

### Changelog

| Version | Description                                   |
|---------|-----------------------------------------------|
| 7.1.0   | The *F* and *f* format characters were added. |

### Examples

**Example \#1 <span class="classname">DateInterval</span> example**

``` php
<?php

$interval = new DateInterval('P2Y4DT6H8M');
echo $interval->format('%d days');

?>
```

The above example will output:

    4 days

**Example \#2 <span class="classname">DateInterval</span> and carry over
points**

``` php
<?php

$interval = new DateInterval('P32D');
echo $interval->format('%d days');

?>
```

The above example will output:

    32 days

**Example \#3 <span class="classname">DateInterval</span> and <span
class="methodname">DateTime::diff</span> with the %a and %d modifiers**

``` php
<?php

$january = new DateTime('2010-01-01');
$february = new DateTime('2010-02-01');
$interval = $february->diff($january);

// %a will output the total number of days.
echo $interval->format('%a total days')."\n";

// While %d will only output the number of days not already covered by the
// month.
echo $interval->format('%m month, %d days');

?>
```

The above example will output:

    31 total days
    1 month, 0 days

### See Also

-   <span class="methodname">DateTime::diff</span>

Introduction
------------

Represents a date period.

A date period allows iteration over a set of dates and times, recurring
at regular intervals, over a given period.

Class synopsis
--------------

**DatePeriod**

<span class="ooclass"> class **DatePeriod** </span> <span
class="oointerface">implements <span
class="interfacename">Traversable</span> </span> {

/\* Constants \*/

<span class="modifier">const</span> <span class="type">int</span>
`DatePeriod::EXCLUDE_START_DATE` <span class="initializer"> = 1</span> ;

/\* Properties \*/

<span class="modifier">public</span> <span class="type">int</span>
`$recurrences` ;

<span class="modifier">public</span> <span class="type">bool</span>
`$include_start_date` ;

<span class="modifier">public</span> <span
class="type">DateTimeInterface</span> `$start` ;

<span class="modifier">public</span> <span
class="type">DateTimeInterface</span> `$current` ;

<span class="modifier">public</span> <span
class="type">DateTimeInterface</span> `$end` ;

<span class="modifier">public</span> <span
class="type">DateInterval</span> `$interval` ;

/\* Methods \*/

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$start`</span> , <span class="methodparam"><span
class="type">DateInterval</span> `$interval`</span> , <span
class="methodparam"><span class="type">int</span> `$recurrences`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$start`</span> , <span class="methodparam"><span
class="type">DateInterval</span> `$interval`</span> , <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$end`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`</span> \] )

<span class="modifier">public</span> <span
class="methodname">\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$isostr`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`</span> \] )

<span class="modifier">public</span> <span
class="type">DateInterval</span> <span
class="methodname">getDateInterval</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeInterface</span><span
class="type">null</span></span> <span
class="methodname">getEndDate</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">getRecurrences</span> ( <span
class="methodparam">void</span> )

<span class="modifier">public</span> <span
class="type">DateTimeInterface</span> <span
class="methodname">getStartDate</span> ( <span
class="methodparam">void</span> )

}

Predefined Constants
--------------------

**`DatePeriod::EXCLUDE_START_DATE`**  
Exclude start date, used in <span
class="function">DatePeriod::\_\_construct</span>.

Properties
----------

`recurrences`  
The number of recurrences, if the <span
class="classname">DatePeriod</span> instance had been created by
explicitly passing *$recurrences*. See also <span
class="methodname">DatePeriod::getRecurrences</span>.

`include_start_date`  
Whether to include the start date in the set of recurring dates or not.

`start`  
The start date of the period.

`current`  
During iteration this will contain the current date within the period.

`end`  
The end date of the period.

`interval`  
An ISO 8601 repeating interval specification.

Changelog
---------

| Version        | Description                                                                                                            |
|----------------|------------------------------------------------------------------------------------------------------------------------|
| 5.3.27, 5.4.17 | The public properties `recurrences`, `include_start_date`, `start`, `current`, `end` and `interval` have been exposed. |

DatePeriod::\_\_construct
=========================

Creates a new DatePeriod object

### Description

<span class="modifier">public</span> <span
class="methodname">DatePeriod::\_\_construct</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$start`</span> , <span class="methodparam"><span
class="type">DateInterval</span> `$interval`</span> , <span
class="methodparam"><span class="type">int</span> `$recurrences`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`</span> \] )

<span class="modifier">public</span> <span
class="methodname">DatePeriod::\_\_construct</span> ( <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$start`</span> , <span class="methodparam"><span
class="type">DateInterval</span> `$interval`</span> , <span
class="methodparam"><span class="type">DateTimeInterface</span>
`$end`</span> \[, <span class="methodparam"><span
class="type">int</span> `$options`</span> \] )

<span class="modifier">public</span> <span
class="methodname">DatePeriod::\_\_construct</span> ( <span
class="methodparam"><span class="type">string</span> `$isostr`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$options`</span> \] )

Creates a new DatePeriod object.

### Parameters

`start`  
The start date of the period.

`interval`  
The interval between recurrences within the period.

`recurrences`  
The number of recurrences.

`end`  
The end date of the period.

`isostr`  
An ISO 8601 repeating interval specification.

`options`  
Can be set to **`DatePeriod::EXCLUDE_START_DATE`** to exclude the start
date from the set of recurring dates within the period.

### Changelog

| Version | Description                                                                                                                        |
|---------|------------------------------------------------------------------------------------------------------------------------------------|
| 5.5.8   | `end` type changed to <span class="interfacename">DateTimeInterface</span>. Previously, <span class="classname">DateTime</span>.   |
| 5.5.0   | `start` type changed to <span class="interfacename">DateTimeInterface</span>. Previously, <span class="classname">DateTime</span>. |

### Examples

**Example \#1 DatePeriod example**

``` php
<?php
$start = new DateTime('2012-07-01');
$interval = new DateInterval('P7D');
$end = new DateTime('2012-07-31');
$recurrences = 4;
$iso = 'R4/2012-07-01T00:00:00Z/P7D';

// All of these periods are equivalent.
$period = new DatePeriod($start, $interval, $recurrences);
$period = new DatePeriod($start, $interval, $end);
$period = new DatePeriod($iso);

// By iterating over the DatePeriod object, all of the
// recurring dates within that period are printed.
foreach ($period as $date) {
    echo $date->format('Y-m-d')."\n";
}
?>
```

The above example will output:

    2012-07-01
    2012-07-08
    2012-07-15
    2012-07-22
    2012-07-29

**Example \#2 DatePeriod example with
**`DatePeriod::EXCLUDE_START_DATE`****

``` php
<?php
$start = new DateTime('2012-07-01');
$interval = new DateInterval('P7D');
$end = new DateTime('2012-07-31');

$period = new DatePeriod($start, $interval, $end,
                         DatePeriod::EXCLUDE_START_DATE);

// By iterating over the DatePeriod object, all of the
// recurring dates within that period are printed.
// Note that, in this case, 2012-07-01 is not printed.
foreach ($period as $date) {
    echo $date->format('Y-m-d')."\n";
}
?>
```

The above example will output:

    2012-07-08
    2012-07-15
    2012-07-22
    2012-07-29

### Notes

Unbound numbers of repetitions as specified by ISO 8601 section 4.5
"Recurring time interval" are not supported, i.e. neither passing
*"R/..."* as `isostr` nor passing **`NULL`** as `end` would work.

DatePeriod::getDateInterval
===========================

Gets the interval

### Description

Object oriented style

<span class="modifier">public</span> <span
class="type">DateInterval</span> <span
class="methodname">DatePeriod::getDateInterval</span> ( <span
class="methodparam">void</span> )

Gets a <span class="classname">DateInterval</span> <span
class="type">object</span> representing the interval used for the
period.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="classname">DateInterval</span> <span
class="type">object</span>

### Examples

**Example \#1 <span
class="methodname">DatePeriod::getDateInterval</span> example**

``` php
<?php
$period = new DatePeriod('R7/2016-05-16T00:00:00Z/P1D');
$interval = $period->getDateInterval();
echo $interval->format('%d day');
?>
```

The above example will output:

    1 day

### See Also

-   <span class="methodname">DatePeriod::getStartDate</span>
-   <span class="methodname">DatePeriod::getEndDate</span>

DatePeriod::getEndDate
======================

Gets the end date

### Description

Object oriented style

<span class="modifier">public</span> <span class="type"><span
class="type">DateTimeInterface</span><span
class="type">null</span></span> <span
class="methodname">DatePeriod::getEndDate</span> ( <span
class="methodparam">void</span> )

Gets the end date of the period.

### Parameters

This function has no parameters.

### Return Values

Returns **`NULL`** if the <span class="classname">DatePeriod</span> does
not have an end date. For example, when initialized with the
`recurrences` parameter, or the `isostr` parameter without an end date.

Returns a <span class="classname">DateTimeImmutable</span> <span
class="type">object</span> when the <span
class="classname">DatePeriod</span> is initialized with a <span
class="classname">DateTimeImmutable</span> <span
class="type">object</span> as the `end` parameter.

Returns a <span class="classname">DateTime</span> <span
class="type">object</span> otherwise.

### Examples

**Example \#1 <span class="methodname">DatePeriod::getEndDate</span>
example**

``` php
<?php
$period = new DatePeriod(
    new DateTime('2016-05-16T00:00:00Z'),
    new DateInterval('P1D'),
    new DateTime('2016-05-20T00:00:00Z')
);
$start = $period->getEndDate();
echo $start->format(DateTime::ISO8601);
?>
```

The above examples will output:

    2016-05-20T00:00:00+0000

**Example \#2 <span class="methodname">DatePeriod::getEndDate</span>
without an end date**

``` php
<?php
$period = new DatePeriod(
    new DateTime('2016-05-16T00:00:00Z'),
    new DateInterval('P1D'),
    7
);
var_dump($period->getEndDate());
?>
```

The above example will output:

    NULL

### See Also

-   <span class="methodname">DatePeriod::getStartDate</span>
-   <span class="methodname">DatePeriod::getDateInterval</span>

DatePeriod::getRecurrences
==========================

Gets the number of recurrences

### Description

Object oriented style

<span class="modifier">public</span> <span class="type">int</span> <span
class="methodname">DatePeriod::getRecurrences</span> ( <span
class="methodparam">void</span> )

Get the number of recurrences.

### Parameters

This function has no parameters.

### Return Values

Returns the number of recurrences.

### See Also

-   <a href="/class/dateperiod.html#" class="link">DatePeriod::$recurrences</a>

DatePeriod::getStartDate
========================

Gets the start date

### Description

Object oriented style

<span class="modifier">public</span> <span
class="type">DateTimeInterface</span> <span
class="methodname">DatePeriod::getStartDate</span> ( <span
class="methodparam">void</span> )

Gets the start date of the period.

### Parameters

This function has no parameters.

### Return Values

Returns a <span class="classname">DateTimeImmutable</span> <span
class="type">object</span> when the <span
class="classname">DatePeriod</span> is initialized with a <span
class="classname">DateTimeImmutable</span> <span
class="type">object</span> as the `start` parameter.

Returns a <span class="classname">DateTime</span> <span
class="type">object</span> otherwise.

### Examples

**Example \#1 <span class="methodname">DatePeriod::getStartDate</span>
example**

``` php
<?php
$period = new DatePeriod('R7/2016-05-16T00:00:00Z/P1D');
$start = $period->getStartDate();
echo $start->format(DateTime::ISO8601);
?>
```

The above example will output:

    2016-05-16T00:00:00+0000

### See Also

-   <span class="methodname">DatePeriod::getEndDate</span>
-   <span class="methodname">DatePeriod::getDateInterval</span>

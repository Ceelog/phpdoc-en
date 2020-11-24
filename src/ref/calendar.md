cal\_days\_in\_month
====================

Return the number of days in a month for a given year and calendar

### Description

<span class="type">int</span> <span
class="methodname">cal\_days\_in\_month</span> ( <span
class="methodparam"><span class="type">int</span> `$calendar`</span> ,
<span class="methodparam"><span class="type">int</span> `$month`</span>
, <span class="methodparam"><span class="type">int</span> `$year`</span>
)

This function will return the number of days in the `month` of `year`
for the specified `calendar`.

### Parameters

`calendar`  
Calendar to use for calculation

`month`  
Month in the selected calendar

`year`  
Year in the selected calendar

### Return Values

The length in days of the selected month in the given calendar

### Examples

**Example \#1 <span class="function">cal\_days\_in\_month</span>
example**

``` php
<?php
$number = cal_days_in_month(CAL_GREGORIAN, 8, 2003); // 31
echo "There were {$number} days in August 2003";
?>
```

cal\_from\_jd
=============

Converts from Julian Day Count to a supported calendar

### Description

<span class="type">array</span> <span
class="methodname">cal\_from\_jd</span> ( <span
class="methodparam"><span class="type">int</span> `$julian_day`</span> ,
<span class="methodparam"><span class="type">int</span>
`$calendar`</span> )

<span class="function">cal\_from\_jd</span> converts the Julian day
given in `julian_day` into a date of the specified `calendar`. Supported
`calendar` values are **`CAL_GREGORIAN`**, **`CAL_JULIAN`**,
**`CAL_JEWISH`** and **`CAL_FRENCH`**.

### Parameters

`julian_day`  
Julian day as integer

`calendar`  
Calendar to convert to

### Return Values

Returns an array containing calendar information like month, day, year,
day of week (*dow*), abbreviated and full names of weekday and month and
the date in string form "month/day/year". The day of week ranges from
*0* (Sunday) to *6* (Saturday).

### Examples

**Example \#1 <span class="function">cal\_from\_jd</span> example**

``` php
<?php
$today = unixtojd(mktime(0, 0, 0, 8, 16, 2003));
print_r(cal_from_jd($today, CAL_GREGORIAN));
?>
```

The above example will output:

    Array
    (
        [date] => 8/16/2003
        [month] => 8
        [day] => 16
        [year] => 2003
        [dow] => 6
        [abbrevdayname] => Sat
        [dayname] => Saturday
        [abbrevmonth] => Aug
        [monthname] => August
    )

### See Also

-   <span class="function">cal\_to\_jd</span>
-   <span class="function">jdtofrench</span>
-   <span class="function">jdtogregorian</span>
-   <span class="function">jdtojewish</span>
-   <span class="function">jdtojulian</span>
-   <span class="function">jdtounix</span>

cal\_info
=========

Returns information about a particular calendar

### Description

<span class="type">array</span> <span
class="methodname">cal\_info</span> (\[ <span class="methodparam"><span
class="type">int</span> `$calendar`<span class="initializer"> =
-1</span></span> \] )

<span class="function">cal\_info</span> returns information on the
specified `calendar`.

Calendar information is returned as an array containing the elements
*calname*, *calsymbol*, *month*, *abbrevmonth* and *maxdaysinmonth*. The
names of the different calendars which can be used as `calendar` are as
follows:

-   <span class="simpara"> 0 or **`CAL_GREGORIAN`** - Gregorian Calendar
    </span>
-   <span class="simpara"> 1 or **`CAL_JULIAN`** - Julian Calendar
    </span>
-   <span class="simpara"> 2 or **`CAL_JEWISH`** - Jewish Calendar
    </span>
-   <span class="simpara"> 3 or **`CAL_FRENCH`** - French Revolutionary
    Calendar </span>

If no `calendar` is specified information on all supported calendars is
returned as an array.

### Parameters

`calendar`  
Calendar to return information for. If no calendar is specified
information about all calendars is returned.

### Return Values

### Examples

**Example \#1 <span class="function">cal\_info</span> example**

``` php
<?php
$info = cal_info(0);
print_r($info);
?>
```

The above example will output:

    Array
    (
        [months] => Array
            (
                [1] => January
                [2] => February
                [3] => March
                [4] => April
                [5] => May
                [6] => June
                [7] => July
                [8] => August
                [9] => September
                [10] => October
                [11] => November
                [12] => December
            )

        [abbrevmonths] => Array
            (
                [1] => Jan
                [2] => Feb
                [3] => Mar
                [4] => Apr
                [5] => May
                [6] => Jun
                [7] => Jul
                [8] => Aug
                [9] => Sep
                [10] => Oct
                [11] => Nov
                [12] => Dec
            )

        [maxdaysinmonth] => 31
        [calname] => Gregorian
        [calsymbol] => CAL_GREGORIAN
    )

cal\_to\_jd
===========

Converts from a supported calendar to Julian Day Count

### Description

<span class="type">int</span> <span
class="methodname">cal\_to\_jd</span> ( <span class="methodparam"><span
class="type">int</span> `$calendar`</span> , <span
class="methodparam"><span class="type">int</span> `$month`</span> ,
<span class="methodparam"><span class="type">int</span> `$day`</span> ,
<span class="methodparam"><span class="type">int</span> `$year`</span> )

<span class="function">cal\_to\_jd</span> calculates the Julian day
count for a date in the specified `calendar`. Supported `calendar`s are
**`CAL_GREGORIAN`**, **`CAL_JULIAN`**, **`CAL_JEWISH`** and
**`CAL_FRENCH`**.

### Parameters

`calendar`  
Calendar to convert from, one of **`CAL_GREGORIAN`**, **`CAL_JULIAN`**,
**`CAL_JEWISH`** or **`CAL_FRENCH`**.

`month`  
The month as a number, the valid range depends on the `calendar`

`day`  
The day as a number, the valid range depends on the `calendar`

`year`  
The year as a number, the valid range depends on the `calendar`

### Return Values

A Julian Day number.

### See Also

-   <span class="function">cal\_from\_jd</span>
-   <span class="function">frenchtojd</span>
-   <span class="function">gregoriantojd</span>
-   <span class="function">jewishtojd</span>
-   <span class="function">juliantojd</span>
-   <span class="function">unixtojd</span>

easter\_date
============

Get Unix timestamp for midnight on Easter of a given year

### Description

<span class="type">int</span> <span
class="methodname">easter\_date</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">int</span><span class="type">null</span></span>
`$year`<span class="initializer"> = **`NULL`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`CAL_EASTER_DEFAULT`**</span></span> \]\] )

Returns the Unix timestamp corresponding to midnight on Easter of the
given year.

**Warning**

This function will generate a warning if the year is outside of the
range for Unix timestamps (i.e. typically before 1970 or after 2037 on
32bit systems).

The date of Easter Day was defined by the Council of Nicaea in AD325 as
the Sunday after the first full moon which falls on or after the Spring
Equinox. The Equinox is assumed to always fall on 21st March, so the
calculation reduces to determining the date of the full moon and the
date of the following Sunday. The algorithm used here was introduced
around the year 532 by Dionysius Exiguus. Under the Julian Calendar (for
years before 1753) a simple 19-year cycle is used to track the phases of
the Moon. Under the Gregorian Calendar (for years after 1753 - devised
by Clavius and Lilius, and introduced by Pope Gregory XIII in October
1582, and into Britain and its then colonies in September 1752) two
correction factors are added to make the cycle more accurate.

### Parameters

`year`  
The year as a number between 1970 an 2037. If omitted or **`NULL`**,
defaults to the current year according to the local time.

`mode`  
Allows Easter dates to be calculated based on the Julian calendar when
set to **`CAL_EASTER_ALWAYS_JULIAN`**. See also
<a href="/calendar/constants.html" class="link">calendar constants</a>.

### Return Values

The easter date as a unix timestamp.

### Changelog

| Version | Description             |
|---------|-------------------------|
| 8.0.0   | `year` is nullable now. |

### Examples

**Example \#1 <span class="function">easter\_date</span> example**

``` php
<?php

echo date("M-d-Y", easter_date(1999));        // Apr-04-1999
echo date("M-d-Y", easter_date(2000));        // Apr-23-2000
echo date("M-d-Y", easter_date(2001));        // Apr-15-2001

?>
```

### Notes

> **Note**:
>
> <span class="function">easter\_date</span> relies on your system's C
> library time functions, rather than using PHP's internal date and time
> functions. As a consequence, <span
> class="function">easter\_date</span> uses the *TZ* environment
> variable to determine the time zone it should operate in, rather than
> using PHP's
> <a href="/datetime/setup.html#" class="link">default time zone</a>,
> which may result in unexpected behaviour when using this function in
> conjunction with other date functions in PHP.
>
> As a workaround, you can use the <span
> class="function">easter\_days</span> with <span
> class="classname">DateTime</span> and <span
> class="classname">DateInterval</span> to calculate the start of Easter
> in your PHP time zone as follows:
>
> ``` php
> <?php
> function get_easter_datetime($year) {
>     $base = new DateTime("$year-03-21");
>     $days = easter_days($year);
>
>     return $base->add(new DateInterval("P{$days}D"));
> }
>
> foreach (range(2012, 2015) as $year) {
>     printf("Easter in %d is on %s\n",
>            $year,
>            get_easter_datetime($year)->format('F j'));
> }
> ?>
> ```
>
> The above example will output:
>
>     Easter in 2012 is on April 8
>     Easter in 2013 is on March 31
>     Easter in 2014 is on April 20
>     Easter in 2015 is on April 5

### See Also

-   <span class="function">easter\_days</span> for calculating Easter
    before 1970 or after 2037

easter\_days
============

Get number of days after March 21 on which Easter falls for a given year

### Description

<span class="type">int</span> <span
class="methodname">easter\_days</span> (\[ <span
class="methodparam"><span class="type"><span
class="type">int</span><span class="type">null</span></span>
`$year`<span class="initializer"> = **`NULL`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`CAL_EASTER_DEFAULT`**</span></span> \]\] )

Returns the number of days after March 21 on which Easter falls for a
given year. If no year is specified, the current year is assumed.

This function can be used instead of <span
class="function">easter\_date</span> to calculate Easter for years which
fall outside the range of Unix timestamps (i.e. before 1970 or after
2037).

The date of Easter Day was defined by the Council of Nicaea in AD325 as
the Sunday after the first full moon which falls on or after the Spring
Equinox. The Equinox is assumed to always fall on 21st March, so the
calculation reduces to determining the date of the full moon and the
date of the following Sunday. The algorithm used here was introduced
around the year 532 by Dionysius Exiguus. Under the Julian Calendar (for
years before 1753) a simple 19-year cycle is used to track the phases of
the Moon. Under the Gregorian Calendar (for years after 1753 - devised
by Clavius and Lilius, and introduced by Pope Gregory XIII in October
1582, and into Britain and its then colonies in September 1752) two
correction factors are added to make the cycle more accurate.

### Parameters

`year`  
The year as a positive number. If omitted or **`NULL`**, defaults to the
current year according to the local time.

`mode`  
Allows Easter dates to be calculated based on the Gregorian calendar
during the years 1582 - 1752 when set to **`CAL_EASTER_ROMAN`**. See the
<a href="/calendar/constants.html" class="link">calendar constants</a>
for more valid constants.

### Return Values

The number of days after March 21st that the Easter Sunday is in the
given `year`.

### Changelog

| Version | Description             |
|---------|-------------------------|
| 8.0.0   | `year` is nullable now. |

### Examples

**Example \#1 <span class="function">easter\_days</span> example**

``` php
<?php

echo easter_days(1999);        // 14, i.e. April 4
echo easter_days(1492);        // 32, i.e. April 22
echo easter_days(1913);        //  2, i.e. March 23

?>
```

### See Also

-   <span class="function">easter\_date</span>

frenchtojd
==========

Converts a date from the French Republican Calendar to a Julian Day
Count

### Description

<span class="type">int</span> <span class="methodname">frenchtojd</span>
( <span class="methodparam"><span class="type">int</span>
`$month`</span> , <span class="methodparam"><span
class="type">int</span> `$day`</span> , <span class="methodparam"><span
class="type">int</span> `$year`</span> )

Converts a date from the French Republican Calendar to a Julian Day
Count.

These routines only convert dates in years 1 through 14 (Gregorian dates
22 September 1792 through 22 September 1806). This more than covers the
period when the calendar was in use.

### Parameters

`month`  
The month as a number from 1 (for Vendémiaire) to 13 (for the period of
5-6 days at the end of each year)

`day`  
The day as a number from 1 to 30

`year`  
The year as a number between 1 and 14

### Return Values

The julian day for the given french revolution date as an integer.

### See Also

-   <span class="function">jdtofrench</span>
-   <span class="function">cal\_to\_jd</span>

gregoriantojd
=============

Converts a Gregorian date to Julian Day Count

### Description

<span class="type">int</span> <span
class="methodname">gregoriantojd</span> ( <span
class="methodparam"><span class="type">int</span> `$month`</span> ,
<span class="methodparam"><span class="type">int</span> `$day`</span> ,
<span class="methodparam"><span class="type">int</span> `$year`</span> )

The valid range for the Gregorian calendar is from November 25, 4714
B.C. to at least December 31, 9999 A.D.

Although this function can handle dates all the way back to 4714 B.C.,
such use may not be meaningful. The Gregorian calendar was not
instituted until October 15, 1582 (or October 5, 1582 in the Julian
calendar). Some countries did not accept it until much later. For
example, Britain converted in 1752, The USSR in 1918 and Greece in 1923.
Most European countries used the Julian calendar prior to the Gregorian.

### Parameters

`month`  
The month as a number from 1 (for January) to 12 (for December)

`day`  
The day as a number from 1 to 31. If the month has less days then given,
overflow occurs; see the example below.

`year`  
The year as a number between -4714 and 9999. Negative numbers mean years
B.C., positive numbers mean years A.D. Note that there is no year *0*;
December 31, 1 B.C. is immediately followed by January 1, 1 A.D.

### Return Values

The julian day for the given gregorian date as an integer. Dates outside
the valid range return *0*.

### Examples

**Example \#1 Calendar functions**

``` php
<?php
$jd = gregoriantojd(10, 11, 1970);
echo "$jd\n";
$gregorian = jdtogregorian($jd);
echo "$gregorian\n";
?>
```

The above example will output:

    2440871
    10/11/1970

**Example \#2 Overflow behavior**

``` php
<?php
echo gregoriantojd(2, 31, 2018), PHP_EOL,
     gregoriantojd(3,  3, 2018), PHP_EOL;
?>
```

The above example will output:

    2458181
    2458181

### See Also

-   <span class="function">jdtogregorian</span>
-   <span class="function">cal\_to\_jd</span>

jddayofweek
===========

Returns the day of the week

### Description

<span class="type"><span class="type">int</span><span
class="type">string</span></span> <span
class="methodname">jddayofweek</span> ( <span class="methodparam"><span
class="type">int</span> `$julian_day`</span> \[, <span
class="methodparam"><span class="type">int</span> `$mode`<span
class="initializer"> = **`CAL_DOW_DAYNO`**</span></span> \] )

Returns the day of the week. Can return a string or an integer depending
on the mode.

### Parameters

`julian_day`  
A julian day number as integer

`mode`  
| Mode        | Meaning                                                                    |
|-------------|----------------------------------------------------------------------------|
| 0 (Default) | Return the day number as an int (0=Sunday, 1=Monday, etc)                  |
| 1           | Returns string containing the day of week (English-Gregorian)              |
| 2           | Return a string containing the abbreviated day of week (English-Gregorian) |

### Return Values

The gregorian weekday as either an integer or string.

jdmonthname
===========

Returns a month name

### Description

<span class="type">string</span> <span
class="methodname">jdmonthname</span> ( <span class="methodparam"><span
class="type">int</span> `$julian_day`</span> , <span
class="methodparam"><span class="type">int</span> `$mode`</span> )

Returns a string containing a month name. `mode` tells this function
which calendar to convert the Julian Day Count to, and what type of
month names are to be returned.

| Mode                            | Meaning                 | Values                                                                                                                         |
|---------------------------------|-------------------------|--------------------------------------------------------------------------------------------------------------------------------|
| **`CAL_MONTH_GREGORIAN_SHORT`** | Gregorian - abbreviated | Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec                                                                     |
| **`CAL_MONTH_GREGORIAN_LONG`**  | Gregorian               | January, February, March, April, May, June, July, August, September, October, November, December                               |
| **`CAL_MONTH_JULIAN_SHORT`**    | Julian - abbreviated    | Jan, Feb, Mar, Apr, May, Jun, Jul, Aug, Sep, Oct, Nov, Dec                                                                     |
| **`CAL_MONTH_JULIAN_LONG`**     | Julian                  | January, February, March, April, May, June, July, August, September, October, November, December                               |
| **`CAL_MONTH_JEWISH`**          | Jewish                  | Tishri, Heshvan, Kislev, Tevet, Shevat, AdarI, AdarII, Nisan, Iyyar, Sivan, Tammuz, Av, Elul                                   |
| **`CAL_MONTH_FRENCH`**          | French Republican       | Vendemiaire, Brumaire, Frimaire, Nivose, Pluviose, Ventose, Germinal, Floreal, Prairial, Messidor, Thermidor, Fructidor, Extra |

### Parameters

`jday`  
The Julian Day to operate on

`mode`  
The calendar mode (see table above).

### Return Values

The month name for the given Julian Day and `mode`.

jdtofrench
==========

Converts a Julian Day Count to the French Republican Calendar

### Description

<span class="type">string</span> <span
class="methodname">jdtofrench</span> ( <span class="methodparam"><span
class="type">int</span> `$julian_day`</span> )

Converts a Julian Day Count to the French Republican Calendar.

### Parameters

`julianday`  
A julian day number as integer

### Return Values

The french revolution date as a string in the form "month/day/year"

### See Also

-   <span class="function">frenchtojd</span>
-   <span class="function">cal\_from\_jd</span>

jdtogregorian
=============

Converts Julian Day Count to Gregorian date

### Description

<span class="type">string</span> <span
class="methodname">jdtogregorian</span> ( <span
class="methodparam"><span class="type">int</span> `$julian_day`</span> )

Converts Julian Day Count to a string containing the Gregorian date in
the format of "month/day/year".

### Parameters

`julian_day`  
A julian day number as integer

### Return Values

The gregorian date as a string in the form "month/day/year"

### See Also

-   <span class="function">gregoriantojd</span>
-   <span class="function">cal\_from\_jd</span>

jdtojewish
==========

Converts a Julian day count to a Jewish calendar date

### Description

<span class="type">string</span> <span
class="methodname">jdtojewish</span> ( <span class="methodparam"><span
class="type">int</span> `$julian_day`</span> \[, <span
class="methodparam"><span class="type">bool</span> `$hebrew`<span
class="initializer"> = **`FALSE`**</span></span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`<span
class="initializer"> = 0</span></span> \]\] )

Converts a Julian Day Count to the Jewish Calendar.

### Parameters

`julianday`  
A julian day number as integer

`hebrew`  
If the `hebrew` parameter is set to **`TRUE`**, the `flags` parameter is
used for Hebrew, ISO-8859-8 encoded string based, output format.

`flags`  
A bitmask which may consist of **`CAL_JEWISH_ADD_ALAFIM_GERESH`**,
**`CAL_JEWISH_ADD_ALAFIM`** and **`CAL_JEWISH_ADD_GERESHAYIM`**.

### Return Values

The Jewish date as a string in the form "month/day/year", or an
ISO-8859-8 encoded Hebrew date string, according to the `hebrew`
parameter.

### Examples

**Example \#1 <span class="function">jdtojewish</span> Example**

``` php
<?php
$jd = gregoriantojd(10, 8, 2002);
echo jdtojewish($jd, true), PHP_EOL,
     jdtojewish($jd, true, CAL_JEWISH_ADD_GERESHAYIM), PHP_EOL,
     jdtojewish($jd, true, CAL_JEWISH_ADD_ALAFIM), PHP_EOL,
     jdtojewish($jd, true,CAL_JEWISH_ADD_ALAFIM_GERESH), PHP_EOL;
?>
```

The above example will output:

    ב חשון התשסג
    ב' חשון התשס"ג
    ב חשון ה אלפים תשסג
    ב חשון ה'תשסג

### See Also

-   <span class="function">jewishtojd</span>
-   <span class="function">cal\_from\_jd</span>

jdtojulian
==========

Converts a Julian Day Count to a Julian Calendar Date

### Description

<span class="type">string</span> <span
class="methodname">jdtojulian</span> ( <span class="methodparam"><span
class="type">int</span> `$julian_day`</span> )

Converts Julian Day Count to a string containing the Julian Calendar
Date in the format of "month/day/year".

### Parameters

`julian_day`  
A julian day number as integer

### Return Values

The julian date as a string in the form "month/day/year"

### See Also

-   <span class="function">juliantojd</span>
-   <span class="function">cal\_from\_jd</span>

jdtounix
========

Convert Julian Day to Unix timestamp

### Description

<span class="type">int</span> <span class="methodname">jdtounix</span> (
<span class="methodparam"><span class="type">int</span>
`$julian_day`</span> )

This function will return a Unix timestamp corresponding to the Julian
Day given in `julian_day`. The time returned is UTC.

### Parameters

`julian_day`  
A julian day number between *2440588* and *106751993607888* on 64bit
systems, or between *2440588* and *2465443* on 32bit systems.

### Return Values

The unix timestamp for the start (midnight, not noon) of the given
Julian day

### Errors/Exceptions

If `julian_day` is outside of the allowed range, a <span
class="classname">ValueError</span> is thrown.

### Changelog

| Version        | Description                                                                                                             |
|----------------|-------------------------------------------------------------------------------------------------------------------------|
| 8.0.0          | This function no longer returns **`FALSE`** on failure, but raises a <span class="classname">ValueError</span> instead. |
| 7.3.24, 7.4.12 | The upper limit of `julian_day` has been extended. Previously, it was *2465342* regardless of the architecture.         |

### See Also

-   <span class="function">unixtojd</span>

jewishtojd
==========

Converts a date in the Jewish Calendar to Julian Day Count

### Description

<span class="type">int</span> <span class="methodname">jewishtojd</span>
( <span class="methodparam"><span class="type">int</span>
`$month`</span> , <span class="methodparam"><span
class="type">int</span> `$day`</span> , <span class="methodparam"><span
class="type">int</span> `$year`</span> )

Although this function can handle dates all the way back to the year 1
(3761 B.C.), such use may not be meaningful. The Jewish calendar has
been in use for several thousand years, but in the early days there was
no formula to determine the start of a month. A new month was started
when the new moon was first observed.

### Parameters

`month`  
The month as a number from *1* to *13*, where *1* means *Tishri*, *13*
means *Elul*, and *6* *and* *7* mean *Adar* in regular years, but *Adar
I* and *Adar II*, respectively, in leap years.

`day`  
The day as a number from *1* to *30*. If the month has only 29 days, the
first day of the following month is assumed.

`year`  
The year as a number between 1 and 9999

### Return Values

The julian day for the given jewish date as an integer.

### See Also

-   <span class="function">jdtojewish</span>
-   <span class="function">cal\_to\_jd</span>

juliantojd
==========

Converts a Julian Calendar date to Julian Day Count

### Description

<span class="type">int</span> <span class="methodname">juliantojd</span>
( <span class="methodparam"><span class="type">int</span>
`$month`</span> , <span class="methodparam"><span
class="type">int</span> `$day`</span> , <span class="methodparam"><span
class="type">int</span> `$year`</span> )

Valid Range for Julian Calendar 4713 B.C. to 9999 A.D.

Although this function can handle dates all the way back to 4713 B.C.,
such use may not be meaningful. The calendar was created in 46 B.C., but
the details did not stabilize until at least 8 A.D., and perhaps as late
at the 4th century. Also, the beginning of a year varied from one
culture to another - not all accepted January as the first month.

**Caution**

Remember, the current calendar system being used worldwide is the
Gregorian calendar. <span class="function">gregoriantojd</span> can be
used to convert such dates to their Julian Day count.

### Parameters

`month`  
The month as a number from 1 (for January) to 12 (for December)

`day`  
The day as a number from 1 to 31

`year`  
The year as a number between -4713 and 9999

### Return Values

The julian day for the given julian date as an integer.

### See Also

-   <span class="function">jdtojulian</span>
-   <span class="function">cal\_to\_jd</span>

unixtojd
========

Convert Unix timestamp to Julian Day

### Description

<span class="type"><span class="type">int</span><span
class="type">false</span></span> <span
class="methodname">unixtojd</span> (\[ <span class="methodparam"><span
class="type"><span class="type">int</span><span
class="type">null</span></span> `$timestamp`<span class="initializer"> =
**`NULL`**</span></span> \] )

Return the Julian Day for a Unix `timestamp` (seconds since 1.1.1970),
or for the current day if no `timestamp` is given. Either way, the time
is regarded as local time (not UTC).

### Parameters

`timestamp`  
A unix timestamp to convert.

### Return Values

A julian day number as integer, or **`FALSE`** on failure.

### Changelog

| Version | Description                  |
|---------|------------------------------|
| 8.0.0   | `timestamp` is nullable now. |

### See Also

-   <span class="function">jdtounix</span>

**Table of Contents**

-   [cal\_days\_in\_month](/ref/calendar.html#cal_days_in_month) —
    Return the number of days in a month for a given year and calendar
-   [cal\_from\_jd](/ref/calendar.html#cal_from_jd) — Converts from
    Julian Day Count to a supported calendar
-   [cal\_info](/ref/calendar.html#cal_info) — Returns information about
    a particular calendar
-   [cal\_to\_jd](/ref/calendar.html#cal_to_jd) — Converts from a
    supported calendar to Julian Day Count
-   [easter\_date](/ref/calendar.html#easter_date) — Get Unix timestamp
    for midnight on Easter of a given year
-   [easter\_days](/ref/calendar.html#easter_days) — Get number of days
    after March 21 on which Easter falls for a given year
-   [frenchtojd](/ref/calendar.html#frenchtojd) — Converts a date from
    the French Republican Calendar to a Julian Day Count
-   [gregoriantojd](/ref/calendar.html#gregoriantojd) — Converts a
    Gregorian date to Julian Day Count
-   [jddayofweek](/ref/calendar.html#jddayofweek) — Returns the day of
    the week
-   [jdmonthname](/ref/calendar.html#jdmonthname) — Returns a month name
-   [jdtofrench](/ref/calendar.html#jdtofrench) — Converts a Julian Day
    Count to the French Republican Calendar
-   [jdtogregorian](/ref/calendar.html#jdtogregorian) — Converts Julian
    Day Count to Gregorian date
-   [jdtojewish](/ref/calendar.html#jdtojewish) — Converts a Julian day
    count to a Jewish calendar date
-   [jdtojulian](/ref/calendar.html#jdtojulian) — Converts a Julian Day
    Count to a Julian Calendar Date
-   [jdtounix](/ref/calendar.html#jdtounix) — Convert Julian Day to Unix
    timestamp
-   [jewishtojd](/ref/calendar.html#jewishtojd) — Converts a date in the
    Jewish Calendar to Julian Day Count
-   [juliantojd](/ref/calendar.html#juliantojd) — Converts a Julian
    Calendar date to Julian Day Count
-   [unixtojd](/ref/calendar.html#unixtojd) — Convert Unix timestamp to
    Julian Day

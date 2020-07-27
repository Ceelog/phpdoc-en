These functions allow you to get the date and time from the server where
your PHP scripts are running. You can use these functions to format the
date and time in many different ways.

The date and time information is internally stored as a 64-bit number so
all conceivably useful dates (including negative years) are supported.
The range is from about 292 billion years in the past to the same in the
future.

> **Note**: <span class="simpara"> Please keep in mind that these
> functions are dependent on the locale settings of your server. Make
> sure to take daylight saving time (use e.g. *$date =
> $date-\>modify('+7 days')* and not *$date += 7\*24\*60\*60*) and leap
> years into consideration when working with these functions. </span>

> **Note**: <span class="simpara"> The timezones referenced in this
> section can be found in the
> <a href="/timezones.html" class="xref">List of Supported Timezones</a>.
> </span>

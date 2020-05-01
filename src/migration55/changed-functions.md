Changed Functions
-----------------

### PHP Core

-   <span class="simpara"> <span
    class="function">set\_error\_handler</span> can now be called with
    **`NULL`** as an argument to reset the error handler. </span>
-   <span class="simpara"> When called with **`NULL`**, <span
    class="function">set\_error\_handler</span> and <span
    class="function">set\_exception\_handler</span> now return the
    previous error or exception handler, respectively. </span>
-   <span class="simpara"> <span class="function">json\_encode</span>
    now accepts `depth` parameter. </span>
-   <span class="simpara"> The behaviour of <span
    class="function">pack</span> and <span
    class="function">unpack</span> with the "a" and "A" format codes has
    changed.
    <a href="/migration55/incompatible.html#migration55.incompatible.pack" class="link">Detailed notes on these changes are available.</a>
    </span>

### <a href="/book/intl.html" class="link">intl</a>

-   <span class="simpara"> <span
    class="methodname">MessageFormatter::format</span> and related
    functions now accept named arguments and mixed numeric and named
    arguments when PHP is linked to ICU 4.8 or later. </span>
-   <span class="simpara"> <span
    class="methodname">MessageFormatter::format</span> and related
    functions no longer error when an insufficient number of arguments
    have been provided. Instead, the placeholders will not be
    substituted. </span>
-   <span class="simpara"> <span
    class="methodname">MessageFormatter::format</span> and <span
    class="methodname">MessageFormatter::parse</span> are no longer
    limited to second precision when dealing with times. </span>
-   <span class="simpara"> <span
    class="methodname">IntlDateFormatter::\_\_construct</span> and <span
    class="function">datefmt\_create</span> now accept <span
    class="classname">IntlTimeZone</span> and <span
    class="classname">DateTimeZone</span> objects for the `timezone`
    argument, and <span class="classname">IntlCalendar</span> objects
    for the `calendar` argument. Furthermore, if the time zone is
    omitted and the `calendar` doesn't specify a time zone, PHP's
    default time zone from <span
    class="function">date\_default\_timezone\_get</span> is now used
    instead of the default ICU time zone. </span>
-   <span class="simpara"> <span
    class="methodname">IntlDateFormatter::getCalendar</span> and <span
    class="function">datefmt\_get\_calendar</span> return false if the
    <span class="classname">IntlDateFormatter</span> object was created
    with an <span class="classname">IntlCalendar</span> instance instead
    of one of the <span class="classname">IntlDateFormatter</span>
    constants. </span>
-   <span class="simpara"> <span
    class="methodname">IntlDateFormatter::setCalendar</span> and <span
    class="function">datefmt\_set\_calendar</span> now accept <span
    class="classname">IntlCalendar</span> objects in addition to the
    <span class="classname">IntlDateFormatter</span> constants. </span>
-   <span class="simpara"> <span
    class="methodname">IntlDateFormatter::format</span> and <span
    class="function">datefmt\_format</span> now accept <span
    class="classname">IntlCalendar</span> objects. </span>

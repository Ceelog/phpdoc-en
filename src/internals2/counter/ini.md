Runtime Configuration
---------------------

The behaviour of these functions is affected by settings in `php.ini`.

| Name                   | Default                      | Changeable    | Changelog |
|------------------------|------------------------------|---------------|-----------|
| counter.reset\_time    | COUNTER\_RESET\_PER\_REQUEST | PHP\_INI\_ALL |           |
| counter.save\_path     | ""                           | PHP\_INI\_ALL |           |
| counter.initial\_value | "0"                          | PHP\_INI\_ALL |           |

For further details and definitions of the PHP\_INI\_\* modes, see the
<a href="/configuration/changes/modes.html" class="xref">Where a configuration setting may be set</a>.

`counter.reset_time` <span class="type">integer</span>  
<span class="simpara"> `counter.reset_time` tells "counter" to reset the
counter used by the basic interface. It may be any of the
**`COUNTER_RESET_*`** constants (see below). </span>

`counter.save_path` <span class="type">string</span>  
<span class="simpara"> Tells "counter" where to save data that has to
persist between invocations of PHP (i.e. any counter that has
COUNTER\_RESET\_NEVER or COUNTER\_FLAG\_SAVE). A file will be created at
this path, which must be readable and writable to whatever user PHP is
running as. </span>

`counter.initial_value` <span class="type">integer</span>  
<span class="simpara"> Sets the initial value of the counter used by the
basic interface whenever it is reset. </span>

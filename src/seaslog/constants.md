Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`SEASLOG_VERSION`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`SEASLOG_AUTHOR`** (<span class="type">string</span>)  
<span class="simpara"> </span>

**`SEASLOG_ALL`** (<span class="type">string</span>)  
<span class="simpara"> "ALL" </span>

**`SEASLOG_DEBUG`** (<span class="type">string</span>)  
<span class="simpara"> "DEBUG" - Detailed debug information.Fine-grained
information events. </span>

**`SEASLOG_INFO`** (<span class="type">string</span>)  
<span class="simpara"> "INFO" - Interesting events.Emphasizes the
running process of the application. </span>

**`SEASLOG_NOTICE`** (<span class="type">string</span>)  
<span class="simpara"> "NOTICE" - Normal but significant
events.Information that is more important than the INFO level during
execution. </span>

**`SEASLOG_WARNING`** (<span class="type">string</span>)  
<span class="simpara"> "WARNING" - Exceptional occurrences that are not
errors.Potentially aberrant information that needs attention and needs
to be repaired. </span>

**`SEASLOG_ERROR`** (<span class="type">string</span>)  
<span class="simpara"> "ERROR" - Runtime errors that do not require
immediate action but should typically. </span>

**`SEASLOG_CRITICAL`** (<span class="type">string</span>)  
<span class="simpara"> "CRITICAL" - Critical conditions.Need to be
repaired immediately, and the program component is unavailable. </span>

**`SEASLOG_ALERT`** (<span class="type">string</span>)  
<span class="simpara"> "ALERT" - Action must be taken
immediately.Immediate attention should be given to relevant personnel
for emergency repairs. </span>

**`SEASLOG_EMERGENCY`** (<span class="type">string</span>)  
<span class="simpara"> "EMERGENCY" - System is unusable. </span>

**`SEASLOG_DETAIL_ORDER_ASC`** (<span class="type">integer</span>)  
<span class="simpara"> 1 </span>

**`SEASLOG_DETAIL_ORDER_DESC`** (<span class="type">integer</span>)  
<span class="simpara"> 2 </span>

**`SEASLOG_APPENDER_FILE`** (<span class="type">integer</span>)  
<span class="simpara"> 1 </span>

**`SEASLOG_APPENDER_TCP`** (<span class="type">integer</span>)  
<span class="simpara"> 2 </span>

**`SEASLOG_APPENDER_UDP`** (<span class="type">integer</span>)  
<span class="simpara"> 3 </span>

**`SEASLOG_CLOSE_LOGGER_STREAM_MOD_ALL`** (<span class="type">integer</span>)  
<span class="simpara"> 1 </span>

**`SEASLOG_CLOSE_LOGGER_STREAM_MOD_ASSIGN`** (<span class="type">integer</span>)  
<span class="simpara"> 2 </span>

**`SEASLOG_REQUEST_VARIABLE_DOMAIN_PORT`** (<span class="type">integer</span>)  
<span class="simpara"> 1 </span>

**`SEASLOG_REQUEST_VARIABLE_REQUEST_URI`** (<span class="type">integer</span>)  
<span class="simpara"> 2 </span>

**`SEASLOG_REQUEST_VARIABLE_REQUEST_METHOD`** (<span class="type">integer</span>)  
<span class="simpara"> 3 </span>

**`SEASLOG_REQUEST_VARIABLE_CLIENT_IP`** (<span class="type">integer</span>)  
<span class="simpara"> 4 </span>

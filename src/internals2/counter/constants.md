Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`COUNTER_FLAG_PERSIST`** (<span class="type">integer</span>)  
<span class="simpara"> A counter with this flag will be created as a
persistent resource. </span>

**`COUNTER_FLAG_SAVE`** (<span class="type">integer</span>)  
<span class="simpara"> A counter with this flag will be saved between
invocations of PHP. </span>

**`COUNTER_FLAG_NO_OVERWRITE`** (<span class="type">integer</span>)  
<span class="simpara"> This flag causes <span
class="function">counter\_create</span> to avoid overwriting an existing
named counter with a new one. </span>

**`COUNTER_META_NAME`** (<span class="type">string</span>)  
<span class="simpara"> Pass this constant to get the name of a counter
resource or object. </span>

**`COUNTER_META_IS_PERISTENT`** (<span class="type">string</span>)  
<span class="simpara"> Pass this constant to determine whether a counter
resource or object is persistent (has the **`COUNTER_FLAG_PERSIST`**
flag). </span>

**`COUNTER_RESET_NEVER`** (<span class="type">integer</span>)  
<span class="simpara"> The counter will never be reset. </span>

**`COUNTER_RESET_PER_LOAD`** (<span class="type">integer</span>)  
<span class="simpara"> The counter will be reset on each invocation of
PHP. </span>

**`COUNTER_RESET_PER_REQUEST`** (<span class="type">integer</span>)  
<span class="simpara"> The counter will be reset on each request.
</span>

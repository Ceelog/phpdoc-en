Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`EXP_GLOB`** (<span class="type">int</span>)  
<span class="simpara"> Indicates that the pattern is a glob-style string
pattern. </span>

**`EXP_EXACT`** (<span class="type">int</span>)  
<span class="simpara"> Indicates that the pattern is an exact string.
</span>

**`EXP_REGEXP`** (<span class="type">int</span>)  
<span class="simpara"> Indicates that the pattern is a regexp-style
string pattern. </span>

**`EXP_EOF`** (<span class="type">int</span>)  
<span class="simpara"> Value, returned by <span
class="function">expect\_expectl</span>, when EOF is reached. </span>

**`EXP_TIMEOUT`** (<span class="type">int</span>)  
<span class="simpara"> Value, returned by <span
class="function">expect\_expectl</span> upon timeout of seconds,
specified in value of
<a href="/expect/setup.html#" class="link">expect.timeout</a> </span>

**`EXP_FULLBUFFER`** (<span class="type">int</span>)  
<span class="simpara"> Value, returned by <span
class="function">expect\_expectl</span> if no pattern have been matched.
</span>

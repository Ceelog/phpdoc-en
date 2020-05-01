Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`SID`** (<span class="type">string</span>)  
<span class="simpara"> Constant containing either the session name and
session ID in the form of *"name=ID"* or empty string if session ID was
set in an appropriate session cookie. This is the same id as the one
returned by <span class="function">session\_id</span>. </span>

**`PHP_SESSION_DISABLED`** (<span class="type">int</span>)  
<span class="simpara"> Since PHP 5.4.0. Return value of <span
class="function">session\_status</span> if sessions are disabled.
</span>

**`PHP_SESSION_NONE`** (<span class="type">int</span>)  
<span class="simpara"> Since PHP 5.4.0. Return value of <span
class="function">session\_status</span> if sessions are enabled, but no
session exists. </span>

**`PHP_SESSION_ACTIVE`** (<span class="type">int</span>)  
<span class="simpara"> Since PHP 5.4.0. Return value of <span
class="function">session\_status</span> if sessions are enabled, and a
session exists. </span>

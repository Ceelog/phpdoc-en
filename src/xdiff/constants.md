Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`XDIFF_PATCH_NORMAL`** (<span class="type">integer</span>)  
<span class="simpara"> This flag indicates that <span
class="function">xdiff\_string\_patch</span> and <span
class="function">xdiff\_file\_patch</span> functions should create
result by applying patch to original content thus creating newer version
of file. This is the default mode of operation. </span>

**`XDIFF_PATCH_REVERSE`** (<span class="type">integer</span>)  
<span class="simpara"> This flag indicated that <span
class="function">xdiff\_string\_patch</span> and <span
class="function">xdiff\_file\_patch</span> functions should create
result by reversing patch changed from newer content thus creating
original version. </span>

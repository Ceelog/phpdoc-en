Predefined Constants
====================

The constants below are defined by this extension, and will only be
available when the extension has either been compiled into PHP or
dynamically loaded at runtime.

**`MB_OVERLOAD_MAIL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`MB_OVERLOAD_STRING`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`MB_OVERLOAD_REGEX`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`MB_CASE_UPPER`** (<span class="type">int</span>)  
<span class="simpara"> Performs a full upper-case folding. This may
change the length of the string. This is the mode used by
mb\_strtoupper(). </span>

**`MB_CASE_LOWER`** (<span class="type">int</span>)  
<span class="simpara"> Performs a full lower-case folding. This may
change the length of the string. This is the mode used by
mb\_strtolower(). </span>

**`MB_CASE_TITLE`** (<span class="type">int</span>)  
<span class="simpara"> Performs a full title-case conversion based on
the Cased and CaseIgnorable derived Unicode properties. In particular
this improves handling of quotes and apostrophes. This may change the
length of the string. </span>

**`MB_CASE_FOLD`** (<span class="type">int</span>)  
<span class="simpara"> Performs a full case fold conversion which
removes case distinctions present in the string. This is used for
caseless matching. This may change the length of the string. Available
since PHP 7.3. </span>

**`MB_CASE_LOWER_SIMPLE`** (<span class="type">int</span>)  
<span class="simpara"> Performs a simple lower-case fold conversion.
This does not change the length of the string. Available as of PHP 7.3.
</span>

**`MB_CASE_UPPER_SIMPLE`** (<span class="type">int</span>)  
<span class="simpara"> Performs simple upper-case fold conversion. This
does not change the length of the string. Available as of PHP 7.3.
</span>

**`MB_CASE_TITLE_SIMPLE`** (<span class="type">int</span>)  
<span class="simpara"> Performs simple title-case fold conversion. This
does not change the length of the string. Available as of PHP 7.3.
</span>

**`MB_CASE_FOLD_SIMPLE`** (<span class="type">int</span>)  
<span class="simpara"> Performs a simple case fold conversion which
removes case distinctions present in the string. This is used for
caseless matching. This does not change the length of the string. Used
by case-insensitive operations internally by the MBString extension.
Available as of PHP 7.3. </span>

**`MB_ONIGURUMA_VERSION`** (<span class="type">string</span>)  
<span class="simpara"> The Oniguruma version, e.g. *6.9.4*. Available as
of PHP 7.4. </span>

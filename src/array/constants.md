Predefined Constants
====================

The constants below are always available as part of the PHP core.

**`CASE_LOWER`** (<span class="type">int</span>)  
<span class="simpara"> **`CASE_LOWER`** is used with <span
class="function">array\_change\_key\_case</span> and is used to convert
array keys to lower case. This is also the default case for <span
class="function">array\_change\_key\_case</span>. </span>

**`CASE_UPPER`** (<span class="type">int</span>)  
<span class="simpara"> **`CASE_UPPER`** is used with <span
class="function">array\_change\_key\_case</span> and is used to convert
array keys to upper case. </span>

Sorting order flags:

**`SORT_ASC`** (<span class="type">int</span>)  
<span class="simpara"> **`SORT_ASC`** is used with <span
class="function">array\_multisort</span> to sort in ascending order.
</span>

**`SORT_DESC`** (<span class="type">int</span>)  
<span class="simpara"> **`SORT_DESC`** is used with <span
class="function">array\_multisort</span> to sort in descending order.
</span>

Sorting type flags: used by various sort functions

**`SORT_REGULAR`** (<span class="type">int</span>)  
<span class="simpara"> **`SORT_REGULAR`** is used to compare items
normally. </span>

**`SORT_NUMERIC`** (<span class="type">int</span>)  
<span class="simpara"> **`SORT_NUMERIC`** is used to compare items
numerically. </span>

**`SORT_STRING`** (<span class="type">int</span>)  
<span class="simpara"> **`SORT_STRING`** is used to compare items as
strings. </span>

**`SORT_LOCALE_STRING`** (<span class="type">int</span>)  
<span class="simpara"> **`SORT_LOCALE_STRING`** is used to compare items
as strings, based on the current locale. Added in PHP 5.0.2. </span>

**`SORT_NATURAL`** (<span class="type">int</span>)  
<span class="simpara"> **`SORT_NATURAL`** is used to compare items as
strings using "natural ordering" like <span
class="function">natsort</span>. Added in PHP 5.4.0. </span>

**`SORT_FLAG_CASE`** (<span class="type">int</span>)  
<span class="simpara"> **`SORT_FLAG_CASE`** can be combined (bitwise OR)
with **`SORT_STRING`** or **`SORT_NATURAL`** to sort strings
case-insensitively. Added in PHP 5.4.0. </span>

Filter flags:

**`ARRAY_FILTER_USE_KEY`** (<span class="type">int</span>)  
<span class="simpara"> **`ARRAY_FILTER_USE_KEY`** is used with <span
class="function">array\_filter</span> to pass each key as the first
argument to the given callback function. Added in PHP 5.6.0. </span>

**`ARRAY_FILTER_USE_BOTH`** (<span class="type">int</span>)  
<span class="simpara"> **`ARRAY_FILTER_USE_BOTH`** is used with <span
class="function">array\_filter</span> to pass both value and key to the
given callback function. Added in PHP 5.6.0. </span>

<!-- -->

**`COUNT_NORMAL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`COUNT_RECURSIVE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`EXTR_OVERWRITE`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`EXTR_SKIP`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`EXTR_PREFIX_SAME`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`EXTR_PREFIX_ALL`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`EXTR_PREFIX_INVALID`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`EXTR_PREFIX_IF_EXISTS`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`EXTR_IF_EXISTS`** (<span class="type">int</span>)  
<span class="simpara"> </span>

**`EXTR_REFS`** (<span class="type">int</span>)  
<span class="simpara"> </span>

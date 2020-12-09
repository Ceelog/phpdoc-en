Iterator::valid
===============

Checks if current position is valid

### Description

<span class="modifier">abstract</span> <span
class="modifier">public</span> <span class="type">bool</span> <span
class="methodname">Iterator::valid</span> ( <span
class="methodparam">void</span> )

This method is called after <span
class="methodname">Iterator::rewind</span> and <span
class="methodname">Iterator::next</span> to check if the current
position is valid.

### Parameters

This function has no parameters.

### Return Values

The return value will be casted to <span class="type">bool</span> and
then evaluated. Returns **`true`** on success or **`false`** on failure.

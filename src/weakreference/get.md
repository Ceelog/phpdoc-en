WeakReference::get
==================

Get a weakly referenced Object

### Description

<span class="modifier">public</span> <span class="type">?object</span>
<span class="methodname">WeakReference::get</span> ( <span
class="methodparam">void</span> )

Gets a weakly referenced object. If the object has already been
destroyed, **`NULL`** is returned.

### Parameters

This function has no parameters.

### Return Values

Returns the referenced <span class="type">object</span>, or **`NULL`**
if the object has been destroyed.

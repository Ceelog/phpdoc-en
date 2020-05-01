newt\_bell
==========

Send a beep to the terminal

### Description

<span class="type">void</span> <span
class="methodname">newt\_bell</span> ( <span
class="methodparam">void</span> )

This function sends a beep to the terminal.

> **Note**:
>
> Depending on the terminal's settings, this beep may or may not be
> audible.

### Return Values

No value is returned.

newt\_button\_bar
=================

This function returns a grid containing the buttons created

### Description

<span class="type">resource</span> <span
class="methodname">newt\_button\_bar</span> ( <span
class="methodparam"><span class="type">array</span> `&$buttons`</span> )

This function returns a grid containing the buttons created.

### Parameters

`buttons`  

### Return Values

Returns grid containing the buttons created.

newt\_button
============

Create a new button

### Description

<span class="type">resource</span> <span
class="methodname">newt\_button</span> ( <span class="methodparam"><span
class="type">int</span> `$left`</span> , <span class="methodparam"><span
class="type">int</span> `$top`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> )

Creates a new button.

### Parameters

`left`  
X-coordinate of the button.

`top`  
Y-coordinate of the button.

`text`  
The text which should be displayed in the button.

### Return Values

Returns a resource link to the created button component, or **`FALSE`**
on error.

### Examples

**Example \#1 A <span class="function">newt\_button</span> example**

``` php
<?php

$form = newt_form();

$ok_button = newt_button(5, 12, "Run Tool");
    
newt_form_add_component($form, $ok_button);

?>
```

### See Also

-   <span class="function">newt\_button\_bar</span>

newt\_centered\_window
======================

Open a centered window of the specified size

### Description

<span class="type">int</span> <span
class="methodname">newt\_centered\_window</span> ( <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$title`</span> \] )

Open a centered window of the specified size.

### Parameters

`width`  
Window width

`height`  
Window height

`title`  
Window title

### Return Values

Undefined value.

### See Also

-   <span class="function">newt\_pop\_window</span>
-   <span class="function">newt\_open\_window</span>

newt\_checkbox\_get\_value
==========================

Retreives value of checkox resource

### Description

<span class="type">string</span> <span
class="methodname">newt\_checkbox\_get\_value</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkbox`</span> )

This function returns the character in the sequence which indicates the
current value of the checkbox.

### Parameters

`checkbox`  

### Return Values

Returns character indicating the value of the checkbox.

newt\_checkbox\_set\_flags
==========================

Configures checkbox resource

### Description

<span class="type">void</span> <span
class="methodname">newt\_checkbox\_set\_flags</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkbox`</span> , <span class="methodparam"><span
class="type">int</span> `$flags`</span> , <span
class="methodparam"><span class="type">int</span> `$sense`</span> )

This function allows to set various flags on checkbox resource.

### Parameters

`checkbox`  

`flags`  

`sense`  

### Return Values

No value is returned.

newt\_checkbox\_set\_value
==========================

Sets the value of the checkbox

### Description

<span class="type">void</span> <span
class="methodname">newt\_checkbox\_set\_value</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkbox`</span> , <span class="methodparam"><span
class="type">string</span> `$value`</span> )

This function allows to set the current value of the checkbox resource.

### Parameters

`checkbox`  

`value`  

### Return Values

No value is returned.

newt\_checkbox\_tree\_add\_item
===============================

Adds new item to the checkbox tree

### Description

<span class="type">void</span> <span
class="methodname">newt\_checkbox\_tree\_add\_item</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> , <span
class="methodparam"><span class="type">mixed</span> `$data`</span> ,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
, <span class="methodparam"><span class="type">int</span>
`$index`</span> \[, <span class="methodparam"><span
class="type">int</span> `$...`</span> \] )

This function allows to add new item to the checkbox tree.

### Parameters

`checkboxtree`  

`text`  

`data`  

`flags`  

`index`  

### Return Values

No value is returned.

newt\_checkbox\_tree\_find\_item
================================

Finds an item in the checkbox tree

### Description

<span class="type">array</span> <span
class="methodname">newt\_checkbox\_tree\_find\_item</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> )

Finds an item in the checkbox tree by item's data.

### Parameters

`checkboxtree`  

`data`  

### Return Values

Returns checkbox tree item resource, or **`NULL`** if it wasn't found.

newt\_checkbox\_tree\_get\_current
==================================

Returns checkbox tree selected item

### Description

<span class="type">mixed</span> <span
class="methodname">newt\_checkbox\_tree\_get\_current</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> )

This method returns checkbox tree selected tem.

### Parameters

`checkboxtree`  

### Return Values

Returns current (selected) checkbox tree item.

newt\_checkbox\_tree\_get\_entry\_value
=======================================

### Description

<span class="type">string</span> <span
class="methodname">newt\_checkbox\_tree\_get\_entry\_value</span> (
<span class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`checkboxtree`  

`data`  

### Return Values

newt\_checkbox\_tree\_get\_multi\_selection
===========================================

### Description

<span class="type">array</span> <span
class="methodname">newt\_checkbox\_tree\_get\_multi\_selection</span> (
<span class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> , <span class="methodparam"><span
class="type">string</span> `$seqnum`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`checkboxtree`  

`seqnum`  

### Return Values

newt\_checkbox\_tree\_get\_selection
====================================

### Description

<span class="type">array</span> <span
class="methodname">newt\_checkbox\_tree\_get\_selection</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`checkboxtree`  

### Return Values

newt\_checkbox\_tree\_multi
===========================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_checkbox\_tree\_multi</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> ,
<span class="methodparam"><span class="type">string</span> `$seq`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`height`  

`seq`  

`flags`  

### Return Values

newt\_checkbox\_tree\_set\_current
==================================

### Description

<span class="type">void</span> <span
class="methodname">newt\_checkbox\_tree\_set\_current</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`checkboxtree`  

`data`  

### Return Values

No value is returned.

newt\_checkbox\_tree\_set\_entry\_value
=======================================

### Description

<span class="type">void</span> <span
class="methodname">newt\_checkbox\_tree\_set\_entry\_value</span> (
<span class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> , <span
class="methodparam"><span class="type">string</span> `$value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`checkboxtree`  

`data`  

`value`  

### Return Values

No value is returned.

newt\_checkbox\_tree\_set\_entry
================================

### Description

<span class="type">void</span> <span
class="methodname">newt\_checkbox\_tree\_set\_entry</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkboxtree`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`checkboxtree`  

`data`  

`text`  

### Return Values

No value is returned.

newt\_checkbox\_tree\_set\_width
================================

### Description

<span class="type">void</span> <span
class="methodname">newt\_checkbox\_tree\_set\_width</span> ( <span
class="methodparam"><span class="type">resource</span>
`$checkbox_tree`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`checkbox_tree`  

`width`  

### Return Values

No value is returned.

newt\_checkbox\_tree
====================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_checkbox\_tree</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`height`  

`flags`  

### Return Values

newt\_checkbox
==============

### Description

<span class="type">resource</span> <span
class="methodname">newt\_checkbox</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> ,
<span class="methodparam"><span class="type">string</span>
`$def_value`</span> \[, <span class="methodparam"><span
class="type">string</span> `$seq`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`text`  

`def_value`  

`seq`  

### Return Values

newt\_clear\_key\_buffer
========================

Discards the contents of the terminal's input buffer without waiting for
additional input

### Description

<span class="type">void</span> <span
class="methodname">newt\_clear\_key\_buffer</span> ( <span
class="methodparam">void</span> )

Discards the contents of the terminal's input buffer without waiting for
additional input.

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_wait\_for\_key</span>

newt\_cls
=========

### Description

<span class="type">void</span> <span class="methodname">newt\_cls</span>
( <span class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

### Return Values

No value is returned.

newt\_compact\_button
=====================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_compact\_button</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`text`  

### Return Values

newt\_component\_add\_callback
==============================

### Description

<span class="type">void</span> <span
class="methodname">newt\_component\_add\_callback</span> ( <span
class="methodparam"><span class="type">resource</span>
`$component`</span> , <span class="methodparam"><span
class="type">mixed</span> `$func_name`</span> , <span
class="methodparam"><span class="type">mixed</span> `$data`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`component`  

`func_name`  

`data`  

### Return Values

No value is returned.

newt\_component\_takes\_focus
=============================

### Description

<span class="type">void</span> <span
class="methodname">newt\_component\_takes\_focus</span> ( <span
class="methodparam"><span class="type">resource</span>
`$component`</span> , <span class="methodparam"><span
class="type">bool</span> `$takes_focus`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`component`  

`takes_focus`  

### Return Values

No value is returned.

newt\_create\_grid
==================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_create\_grid</span> ( <span
class="methodparam"><span class="type">int</span> `$cols`</span> , <span
class="methodparam"><span class="type">int</span> `$rows`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`cols`  

`rows`  

### Return Values

newt\_cursor\_off
=================

### Description

<span class="type">void</span> <span
class="methodname">newt\_cursor\_off</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

### Return Values

No value is returned.

newt\_cursor\_on
================

### Description

<span class="type">void</span> <span
class="methodname">newt\_cursor\_on</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Return Values

No value is returned.

newt\_delay
===========

### Description

<span class="type">void</span> <span
class="methodname">newt\_delay</span> ( <span class="methodparam"><span
class="type">int</span> `$microseconds`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`microseconds`  

### Return Values

No value is returned.

newt\_draw\_form
================

### Description

<span class="type">void</span> <span
class="methodname">newt\_draw\_form</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`form`  

### Return Values

No value is returned.

newt\_draw\_root\_text
======================

Displays the string text at the position indicated

### Description

<span class="type">void</span> <span
class="methodname">newt\_draw\_root\_text</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> )

Displays the string text at the position indicated.

### Parameters

`left`  
Column number

> **Note**:
>
> If left is negative, the position is measured from the opposite side
> of the screen.

`top`  
Line number

> **Note**:
>
> If top is negative, the position is measured from the opposite side of
> the screen.

`text`  
Text to display.

### Return Values

No value is returned.

### Examples

**Example \#1 A <span class="function">newt\_draw\_root\_text</span>
example**

This code demonstrates drawing of titles in the both corners of the
screen.

``` php
<?php
 newt_init();
 newt_cls();

 newt_draw_root_text (2, 0, "Some root text");
 newt_refresh();
 sleep(1);

 newt_draw_root_text (-30, 0, "Root text in the other corner");
 newt_refresh();
 sleep(1);

 newt_finished();
?>
```

### See Also

-   <span class="function">newt\_push\_help\_line</span>
-   <span class="function">newt\_pop\_help\_line</span>

newt\_entry\_get\_value
=======================

### Description

<span class="type">string</span> <span
class="methodname">newt\_entry\_get\_value</span> ( <span
class="methodparam"><span class="type">resource</span> `$entry`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`entry`  

### Return Values

newt\_entry\_set\_filter
========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_entry\_set\_filter</span> ( <span
class="methodparam"><span class="type">resource</span> `$entry`</span> ,
<span class="methodparam"><span class="type">callable</span>
`$filter`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`entry`  

`filter`  

`data`  

### Return Values

No value is returned.

newt\_entry\_set\_flags
=======================

### Description

<span class="type">void</span> <span
class="methodname">newt\_entry\_set\_flags</span> ( <span
class="methodparam"><span class="type">resource</span> `$entry`</span> ,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
, <span class="methodparam"><span class="type">int</span>
`$sense`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`entry`  

`flags`  

`sense`  

### Return Values

No value is returned.

newt\_entry\_set
================

### Description

<span class="type">void</span> <span
class="methodname">newt\_entry\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$entry`</span> ,
<span class="methodparam"><span class="type">string</span>
`$value`</span> \[, <span class="methodparam"><span
class="type">bool</span> `$cursor_at_end`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`entry`  

`value`  

`cursor_at_end`  

### Return Values

No value is returned.

newt\_entry
===========

### Description

<span class="type">resource</span> <span
class="methodname">newt\_entry</span> ( <span class="methodparam"><span
class="type">int</span> `$left`</span> , <span class="methodparam"><span
class="type">int</span> `$top`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> \[, <span
class="methodparam"><span class="type">string</span>
`$init_value`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`width`  

`init_value`  

`flags`  

### Return Values

newt\_finished
==============

Uninitializes newt interface

### Description

<span class="type">int</span> <span
class="methodname">newt\_finished</span> ( <span
class="methodparam">void</span> )

Uninitializes newt interface. This function be called, when program is
ready to exit.

### Return Values

Returns 1 on success, 0 on failure.

### See Also

-   <span class="function">newt\_init</span>

newt\_form\_add\_component
==========================

Adds a single component to the form

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_add\_component</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$component`</span> )

Adds a single component to the `form`.

### Parameters

`form`  
Form to which component will be added

`component`  
Component to add to the form

### Return Values

No value is returned.

### Examples

**Example \#1 A <span class="function">newt\_form\_add\_component</span>
example**

``` php
<?php
$form = newt_form();

$options = array("Authentication configuration", "Firewall configuration",
"Mouse configuration", "Network configuration", "Printer configuration",
"System services");

$list = newt_listbox(3, 2, 10);

foreach ($options as $l_item) {
    newt_listbox_add_entry($list, $l_item, $l_item);
}

newt_form_add_component($form, $list);
?>
```

### See Also

-   <span class="function">newt\_form\_add\_components</span>

newt\_form\_add\_components
===========================

Add several components to the form

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_add\_components</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> ,
<span class="methodparam"><span class="type">array</span>
`$components`</span> )

Adds several components to the `form`.

### Parameters

`form`  
Form to which components will be added

`components`  
Array of components to add to the form

### Return Values

No value is returned.

### Examples

**Example \#1 A <span
class="function">newt\_form\_add\_components</span> example**

``` php
<?php
$form = newt_form();

$b1 = newt_button(5, 12, "Run Tool");
$b2 = newt_button(21, 12, "Quit");

newt_form_add_components($form, array($b1, $b2));
?>
```

### See Also

-   <span class="function">newt\_form\_add\_component</span>

newt\_form\_add\_hot\_key
=========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_add\_hot\_key</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> ,
<span class="methodparam"><span class="type">int</span> `$key`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`form`  

`key`  

### Return Values

No value is returned.

newt\_form\_destroy
===================

Destroys a form

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_destroy</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> )

This function frees the memory resources used by the form and all of the
components which have been added to the form (including those components
which are on subforms). Once a form has been destroyed, none of the
form's components can be used.

### Parameters

`form`  
Form component, which is going to be destroyed

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_form\_run</span>
-   <span class="function">newt\_run\_form</span>

newt\_form\_get\_current
========================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_form\_get\_current</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`form`  

### Return Values

newt\_form\_run
===============

Runs a form

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_run</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> ,
<span class="methodparam"><span class="type">array</span>
`&$exit_struct`</span> )

This function runs the form passed to it.

### Parameters

`form`  
Form component

`exit_struct`  
Array, used for returning information after running the form component.
Keys and values are described in the following table:

| Index Key | Value Type | Description                                                                                                                                              |
|-----------|------------|----------------------------------------------------------------------------------------------------------------------------------------------------------|
| reason    | integer    | The reason, why the form has been exited. Possible values are defined <a href="/newt/constants.html#Newt%20form%20exit%20reasons" class="link">here</a>. |
| watch     | resource   | Resource link, specified in <span class="function">newt\_form\_watch\_fd</span>                                                                          |
| key       | integer    | Hotkey                                                                                                                                                   |
| component | resource   | Component, which caused the form to exit                                                                                                                 |

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_run\_form</span>

newt\_form\_set\_background
===========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_set\_background</span> ( <span
class="methodparam"><span class="type">resource</span> `$from`</span> ,
<span class="methodparam"><span class="type">int</span>
`$background`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`from`  

`background`  

### Return Values

No value is returned.

newt\_form\_set\_height
=======================

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_set\_height</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`form`  

`height`  

### Return Values

No value is returned.

newt\_form\_set\_size
=====================

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_set\_size</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`form`  

### Return Values

No value is returned.

newt\_form\_set\_timer
======================

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_set\_timer</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> ,
<span class="methodparam"><span class="type">int</span>
`$milliseconds`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`form`  

`milliseconds`  

### Return Values

No value is returned.

newt\_form\_set\_width
======================

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_set\_width</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> ,
<span class="methodparam"><span class="type">int</span> `$width`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`form`  

`width`  

### Return Values

No value is returned.

newt\_form\_watch\_fd
=====================

### Description

<span class="type">void</span> <span
class="methodname">newt\_form\_watch\_fd</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$stream`</span> \[, <span class="methodparam"><span
class="type">int</span> `$flags`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`form`  

`stream`  

`flags`  

### Return Values

No value is returned.

newt\_form
==========

Create a form

### Description

<span class="type">resource</span> <span
class="methodname">newt\_form</span> (\[ <span class="methodparam"><span
class="type">resource</span> `$vert_bar`</span> \[, <span
class="methodparam"><span class="type">string</span> `$help`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\]\]\] )

Create a new form.

### Parameters

`vert_bar`  
Vertical scrollbar which should be associated with the form

`help`  
Help text string

`flags`  
Various flags

### Return Values

Returns a resource link to the created form component, or **`FALSE`** on
error.

### Examples

**Example \#1 A <span class="function">newt\_form</span> example**

Displays a single button "Quit", which closes the application once it's
pressed.

``` php
<?php
newt_init();
newt_cls();

$myform = newt_form();
$button = newt_button (5, 12, "Quit");

newt_form_add_component ($myform, $button);
newt_refresh ();
newt_run_form ($myform);

newt_finished ();
newt_form_destroy ($myform);
?>
```

### See Also

-   <span class="function">newt\_form\_run</span>
-   <span class="function">newt\_run\_form</span>
-   <span class="function">newt\_form\_add\_component</span>
-   <span class="function">newt\_form\_add\_components</span>
-   <span class="function">newt\_form\_destroy</span>

newt\_get\_screen\_size
=======================

Fills in the passed references with the current size of the terminal

### Description

<span class="type">void</span> <span
class="methodname">newt\_get\_screen\_size</span> ( <span
class="methodparam"><span class="type">int</span> `&$cols`</span> ,
<span class="methodparam"><span class="type">int</span> `&$rows`</span>
)

Fills in the passed references with the current size of the terminal.

### Parameters

`cols`  
Number of columns in the terminal

`rows`  
Number of rows in the terminal

### Return Values

No value is returned.

### Examples

**Example \#1 A <span class="function">newt\_get\_screen\_size</span>
example**

This code prints out the screen size of your terminal.

``` php
<?php
 newt_init();
 newt_get_screen_size (&$cols, &$rows);
 newt_finished();

 print "Your terminal size is: {$cols}x{$rows}\n";
?>
```

The above example will output:

    Your terminal size is: 138x47

newt\_grid\_add\_components\_to\_form
=====================================

### Description

<span class="type">void</span> <span
class="methodname">newt\_grid\_add\_components\_to\_form</span> ( <span
class="methodparam"><span class="type">resource</span> `$grid`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$form`</span> , <span class="methodparam"><span
class="type">bool</span> `$recurse`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`grid`  

`form`  

`recurse`  

### Return Values

No value is returned.

newt\_grid\_basic\_window
=========================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_grid\_basic\_window</span> ( <span
class="methodparam"><span class="type">resource</span> `$text`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$middle`</span> , <span class="methodparam"><span
class="type">resource</span> `$buttons`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`text`  

`middle`  

`buttons`  

### Return Values

newt\_grid\_free
================

### Description

<span class="type">void</span> <span
class="methodname">newt\_grid\_free</span> ( <span
class="methodparam"><span class="type">resource</span> `$grid`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$recurse`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`grid`  

`recurse`  

### Return Values

No value is returned.

newt\_grid\_get\_size
=====================

### Description

<span class="type">void</span> <span
class="methodname">newt\_grid\_get\_size</span> ( <span
class="methodparam"><span class="type">resouce</span> `$grid`</span> ,
<span class="methodparam"><span class="type">int</span> `&$width`</span>
, <span class="methodparam"><span class="type">int</span>
`&$height`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`grid`  

`width`  

`height`  

### Return Values

No value is returned.

newt\_grid\_h\_close\_stacked
=============================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_grid\_h\_close\_stacked</span> ( <span
class="methodparam"><span class="type">int</span>
`$element1_type`</span> , <span class="methodparam"><span
class="type">resource</span> `$element1`</span> \[, <span
class="methodparam"><span class="type">int</span> `$...`</span> \[,
<span class="methodparam"><span class="type">resource</span>
`$...`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`element1_type`  

`element1`  

### Return Values

newt\_grid\_h\_stacked
======================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_grid\_h\_stacked</span> ( <span
class="methodparam"><span class="type">int</span>
`$element1_type`</span> , <span class="methodparam"><span
class="type">resource</span> `$element1`</span> \[, <span
class="methodparam"><span class="type">int</span> `$...`</span> \[,
<span class="methodparam"><span class="type">resource</span>
`$...`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`element1_type`  

`element1`  

### Return Values

newt\_grid\_place
=================

### Description

<span class="type">void</span> <span
class="methodname">newt\_grid\_place</span> ( <span
class="methodparam"><span class="type">resource</span> `$grid`</span> ,
<span class="methodparam"><span class="type">int</span> `$left`</span> ,
<span class="methodparam"><span class="type">int</span> `$top`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`grid`  

`left`  

`top`  

### Return Values

No value is returned.

newt\_grid\_set\_field
======================

### Description

<span class="type">void</span> <span
class="methodname">newt\_grid\_set\_field</span> ( <span
class="methodparam"><span class="type">resource</span> `$grid`</span> ,
<span class="methodparam"><span class="type">int</span> `$col`</span> ,
<span class="methodparam"><span class="type">int</span> `$row`</span> ,
<span class="methodparam"><span class="type">int</span> `$type`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$val`</span> , <span class="methodparam"><span class="type">int</span>
`$pad_left`</span> , <span class="methodparam"><span
class="type">int</span> `$pad_top`</span> , <span
class="methodparam"><span class="type">int</span> `$pad_right`</span> ,
<span class="methodparam"><span class="type">int</span>
`$pad_bottom`</span> , <span class="methodparam"><span
class="type">int</span> `$anchor`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`grid`  

`col`  

`row`  

`type`  

`val`  

`pad_left`  

`pad_top`  

`pad_right`  

`pad_bottom`  

`anchor`  

`flags`  

### Return Values

No value is returned.

newt\_grid\_simple\_window
==========================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_grid\_simple\_window</span> ( <span
class="methodparam"><span class="type">resource</span> `$text`</span> ,
<span class="methodparam"><span class="type">resource</span>
`$middle`</span> , <span class="methodparam"><span
class="type">resource</span> `$buttons`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`text`  

`middle`  

`buttons`  

### Return Values

newt\_grid\_v\_close\_stacked
=============================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_grid\_v\_close\_stacked</span> ( <span
class="methodparam"><span class="type">int</span>
`$element1_type`</span> , <span class="methodparam"><span
class="type">resource</span> `$element1`</span> \[, <span
class="methodparam"><span class="type">int</span> `$...`</span> \[,
<span class="methodparam"><span class="type">resource</span>
`$...`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`element1_type`  

`element1`  

### Return Values

newt\_grid\_v\_stacked
======================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_grid\_v\_stacked</span> ( <span
class="methodparam"><span class="type">int</span>
`$element1_type`</span> , <span class="methodparam"><span
class="type">resource</span> `$element1`</span> \[, <span
class="methodparam"><span class="type">int</span> `$...`</span> \[,
<span class="methodparam"><span class="type">resource</span>
`$...`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`element1_type`  

`element1`  

### Return Values

newt\_grid\_wrapped\_window\_at
===============================

### Description

<span class="type">void</span> <span
class="methodname">newt\_grid\_wrapped\_window\_at</span> ( <span
class="methodparam"><span class="type">resource</span> `$grid`</span> ,
<span class="methodparam"><span class="type">string</span>
`$title`</span> , <span class="methodparam"><span
class="type">int</span> `$left`</span> , <span class="methodparam"><span
class="type">int</span> `$top`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`grid`  

`title`  

`left`  

`top`  

### Return Values

No value is returned.

newt\_grid\_wrapped\_window
===========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_grid\_wrapped\_window</span> ( <span
class="methodparam"><span class="type">resource</span> `$grid`</span> ,
<span class="methodparam"><span class="type">string</span>
`$title`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`grid`  

`title`  

### Return Values

No value is returned.

newt\_init
==========

Initialize newt

### Description

<span class="type">int</span> <span class="methodname">newt\_init</span>
( <span class="methodparam">void</span> )

Initializes the newt interface. This function must be called before any
other newt function.

### Return Values

Returns 1 on success, 0 on failure.

### See Also

-   <span class="function">newt\_finished</span>

newt\_label\_set\_text
======================

### Description

<span class="type">void</span> <span
class="methodname">newt\_label\_set\_text</span> ( <span
class="methodparam"><span class="type">resource</span> `$label`</span> ,
<span class="methodparam"><span class="type">string</span>
`$text`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`label`  

`text`  

### Return Values

No value is returned.

newt\_label
===========

### Description

<span class="type">resource</span> <span
class="methodname">newt\_label</span> ( <span class="methodparam"><span
class="type">int</span> `$left`</span> , <span class="methodparam"><span
class="type">int</span> `$top`</span> , <span class="methodparam"><span
class="type">string</span> `$text`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`text`  

### Return Values

newt\_listbox\_append\_entry
============================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_append\_entry</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">string</span>
`$text`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`text`  

`data`  

### Return Values

No value is returned.

newt\_listbox\_clear\_selection
===============================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_clear\_selection</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

### Return Values

No value is returned.

newt\_listbox\_clear
====================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_clear</span> ( <span
class="methodparam"><span class="type">resource</span> `$listobx`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listobx`  

### Return Values

No value is returned.

newt\_listbox\_delete\_entry
============================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_delete\_entry</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$key`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`key`  

### Return Values

No value is returned.

newt\_listbox\_get\_current
===========================

### Description

<span class="type">string</span> <span
class="methodname">newt\_listbox\_get\_current</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

### Return Values

newt\_listbox\_get\_selection
=============================

### Description

<span class="type">array</span> <span
class="methodname">newt\_listbox\_get\_selection</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

### Return Values

newt\_listbox\_insert\_entry
============================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_insert\_entry</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">string</span>
`$text`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> , <span
class="methodparam"><span class="type">mixed</span> `$key`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`text`  

`data`  

`key`  

### Return Values

No value is returned.

newt\_listbox\_item\_count
==========================

### Description

<span class="type">int</span> <span
class="methodname">newt\_listbox\_item\_count</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

### Return Values

newt\_listbox\_select\_item
===========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_select\_item</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$key`</span> , <span class="methodparam"><span class="type">int</span>
`$sense`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`key`  

`sense`  

### Return Values

No value is returned.

newt\_listbox\_set\_current\_by\_key
====================================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_set\_current\_by\_key</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$key`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`key`  

### Return Values

No value is returned.

newt\_listbox\_set\_current
===========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_set\_current</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">int</span> `$num`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`num`  

### Return Values

No value is returned.

newt\_listbox\_set\_data
========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_set\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">int</span> `$num`</span>
, <span class="methodparam"><span class="type">mixed</span>
`$data`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`num`  

`data`  

### Return Values

No value is returned.

newt\_listbox\_set\_entry
=========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_set\_entry</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">int</span> `$num`</span>
, <span class="methodparam"><span class="type">string</span>
`$text`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`num`  

`text`  

### Return Values

No value is returned.

newt\_listbox\_set\_width
=========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listbox\_set\_width</span> ( <span
class="methodparam"><span class="type">resource</span> `$listbox`</span>
, <span class="methodparam"><span class="type">int</span>
`$width`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`listbox`  

`width`  

### Return Values

No value is returned.

newt\_listbox
=============

### Description

<span class="type">resource</span> <span
class="methodname">newt\_listbox</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`height`  

`flags`  

### Return Values

newt\_listitem\_get\_data
=========================

### Description

<span class="type">mixed</span> <span
class="methodname">newt\_listitem\_get\_data</span> ( <span
class="methodparam"><span class="type">resource</span> `$item`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`item`  

### Return Values

newt\_listitem\_set
===================

### Description

<span class="type">void</span> <span
class="methodname">newt\_listitem\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$item`</span> ,
<span class="methodparam"><span class="type">string</span>
`$text`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`item`  

`text`  

### Return Values

No value is returned.

newt\_listitem
==============

### Description

<span class="type">resource</span> <span
class="methodname">newt\_listitem</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$is_default`</span> , <span class="methodparam"><span
class="type">resouce</span> `$prev_item`</span> , <span
class="methodparam"><span class="type">mixed</span> `$data`</span> \[,
<span class="methodparam"><span class="type">int</span> `$flags`</span>
\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`text`  

`is_default`  

`prev_item`  

`data`  

`flags`  

### Return Values

newt\_open\_window
==================

Open a window of the specified size and position

### Description

<span class="type">int</span> <span
class="methodname">newt\_open\_window</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$title`</span> \] )

Open a window of the specified size and position.

### Parameters

`left`  
Location of the upper left-hand corner of the window (column number)

`top`  
Location of the upper left-hand corner of the window (row number)

`width`  
Window width

`height`  
Window height

`title`  
Window title

### Return Values

Returns 1 on success, 0 on failure.

### See Also

-   <span class="function">newt\_pop\_window</span>
-   <span class="function">newt\_centered\_window</span>

newt\_pop\_help\_line
=====================

Replaces the current help line with the one from the stack

### Description

<span class="type">void</span> <span
class="methodname">newt\_pop\_help\_line</span> ( <span
class="methodparam">void</span> )

Replaces the current help line with the one from the stack.

> **Note**:
>
> It's important not to call to <span
> class="function">newt\_pop\_help\_line</span> more than <span
> class="function">newt\_push\_help\_line</span>.

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_push\_help\_line</span>

newt\_pop\_window
=================

Removes the top window from the display

### Description

<span class="type">void</span> <span
class="methodname">newt\_pop\_window</span> ( <span
class="methodparam">void</span> )

Removes the top window from the display, and redraws the display areas
which the window overwrote.

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_open\_window</span>
-   <span class="function">newt\_centered\_window</span>

newt\_push\_help\_line
======================

Saves the current help line on a stack, and displays the new line

### Description

<span class="type">void</span> <span
class="methodname">newt\_push\_help\_line</span> (\[ <span
class="methodparam"><span class="type">string</span> `$text`</span> \] )

Saves the current help line on a stack, and displays the new line.

### Parameters

`text`  
New help text message

> **Note**:
>
> If not specified, the help line is cleared.

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_pop\_help\_line</span>

newt\_radio\_get\_current
=========================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_radio\_get\_current</span> ( <span
class="methodparam"><span class="type">resource</span>
`$set_member`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`set_member`  

### Return Values

newt\_radiobutton
=================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_radiobutton</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">string</span> `$text`</span> ,
<span class="methodparam"><span class="type">bool</span>
`$is_default`</span> \[, <span class="methodparam"><span
class="type">resource</span> `$prev_button`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`text`  

`is_default`  

`prev_button`  

### Return Values

newt\_redraw\_help\_line
========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_redraw\_help\_line</span> ( <span
class="methodparam">void</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

### Return Values

No value is returned.

newt\_reflow\_text
==================

### Description

<span class="type">string</span> <span
class="methodname">newt\_reflow\_text</span> ( <span
class="methodparam"><span class="type">string</span> `$text`</span> ,
<span class="methodparam"><span class="type">int</span> `$width`</span>
, <span class="methodparam"><span class="type">int</span>
`$flex_down`</span> , <span class="methodparam"><span
class="type">int</span> `$flex_up`</span> , <span
class="methodparam"><span class="type">int</span>
`&$actual_width`</span> , <span class="methodparam"><span
class="type">int</span> `&$actual_height`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`text`  

`width`  

`flex_down`  

`flex_up`  

`actual_width`  

`actual_height`  

### Return Values

newt\_refresh
=============

Updates modified portions of the screen

### Description

<span class="type">void</span> <span
class="methodname">newt\_refresh</span> ( <span
class="methodparam">void</span> )

To increase performance, newt only updates the display when it needs to,
not when the program tells it to write to the terminal. Applications can
force newt to immediately update modified portions of the screen by
calling this function.

### Return Values

No value is returned.

newt\_resize\_screen
====================

### Description

<span class="type">void</span> <span
class="methodname">newt\_resize\_screen</span> (\[ <span
class="methodparam"><span class="type">bool</span> `$redraw`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`redraw`  

### Return Values

No value is returned.

newt\_resume
============

Resume using the newt interface after calling <span
class="function">newt\_suspend</span>

### Description

<span class="type">void</span> <span
class="methodname">newt\_resume</span> ( <span
class="methodparam">void</span> )

Resume using the newt interface after calling <span
class="function">newt\_suspend</span>.

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_suspend</span>

newt\_run\_form
===============

Runs a form

### Description

<span class="type">resource</span> <span
class="methodname">newt\_run\_form</span> ( <span
class="methodparam"><span class="type">resource</span> `$form`</span> )

This function runs the form passed to it.

### Parameters

`form`  
Form component

### Return Values

The component which caused the form to stop running.

> **Note**:
>
> Notice that this function doesn't fit in with newt's normal naming
> convention. It is an older interface which will not work for all
> forms. It was left in newt only for legacy applications. It is a
> simpler interface than the new <span
> class="function">newt\_form\_run</span> though, and is still used
> quite often as a result. When an application is done with a form, it
> destroys the form and all of the components the form contains.

### See Also

-   <span class="function">newt\_form\_run</span>
-   <span class="function">newt\_form\_destroy</span>

newt\_scale\_set
================

### Description

<span class="type">void</span> <span
class="methodname">newt\_scale\_set</span> ( <span
class="methodparam"><span class="type">resource</span> `$scale`</span> ,
<span class="methodparam"><span class="type">int</span> `$amount`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`scale`  

`amount`  

### Return Values

No value is returned.

newt\_scale
===========

### Description

<span class="type">resource</span> <span
class="methodname">newt\_scale</span> ( <span class="methodparam"><span
class="type">int</span> `$left`</span> , <span class="methodparam"><span
class="type">int</span> `$top`</span> , <span class="methodparam"><span
class="type">int</span> `$width`</span> , <span
class="methodparam"><span class="type">int</span> `$full_value`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`width`  

`full_value`  

### Return Values

newt\_scrollbar\_set
====================

### Description

<span class="type">void</span> <span
class="methodname">newt\_scrollbar\_set</span> ( <span
class="methodparam"><span class="type">resource</span>
`$scrollbar`</span> , <span class="methodparam"><span
class="type">int</span> `$where`</span> , <span
class="methodparam"><span class="type">int</span> `$total`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`scrollbar`  

`where`  

`total`  

### Return Values

No value is returned.

newt\_set\_help\_callback
=========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_set\_help\_callback</span> ( <span
class="methodparam"><span class="type">mixed</span> `$function`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`function`  

### Return Values

No value is returned.

newt\_set\_suspend\_callback
============================

Set a callback function which gets invoked when user presses the suspend
key

### Description

<span class="type">void</span> <span
class="methodname">newt\_set\_suspend\_callback</span> ( <span
class="methodparam"><span class="type">callable</span>
`$function`</span> , <span class="methodparam"><span
class="type">mixed</span> `$data`</span> )

Set a callback function which gets invoked when user presses the suspend
key (normally ^Z). If no suspend callback is registered, the suspend
keystroke is ignored.

### Parameters

`function`  
A callback function, which accepts one argument: data

`data`  
This data is been passed to the callback function

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_suspend</span>
-   <span class="function">newt\_resume</span>

newt\_suspend
=============

Tells newt to return the terminal to its initial state

### Description

<span class="type">void</span> <span
class="methodname">newt\_suspend</span> ( <span
class="methodparam">void</span> )

Tells newt to return the terminal to its initial state. Once this is
done, the application can suspend itself (by sending itself a SIGTSTP,
fork a child program, or do whatever else it likes).

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_resume</span>

newt\_textbox\_get\_num\_lines
==============================

### Description

<span class="type">int</span> <span
class="methodname">newt\_textbox\_get\_num\_lines</span> ( <span
class="methodparam"><span class="type">resource</span> `$textbox`</span>
)

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`textbox`  

### Return Values

newt\_textbox\_reflowed
=======================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_textbox\_reflowed</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">char</span> `$*text`</span> ,
<span class="methodparam"><span class="type">int</span> `$width`</span>
, <span class="methodparam"><span class="type">int</span>
`$flex_down`</span> , <span class="methodparam"><span
class="type">int</span> `$flex_up`</span> \[, <span
class="methodparam"><span class="type">int</span> `$flags`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`*text`  

`width`  

`flex_down`  

`flex_up`  

`flags`  

### Return Values

newt\_textbox\_set\_height
==========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_textbox\_set\_height</span> ( <span
class="methodparam"><span class="type">resource</span> `$textbox`</span>
, <span class="methodparam"><span class="type">int</span>
`$height`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`textbox`  

`height`  

### Return Values

No value is returned.

newt\_textbox\_set\_text
========================

### Description

<span class="type">void</span> <span
class="methodname">newt\_textbox\_set\_text</span> ( <span
class="methodparam"><span class="type">resource</span> `$textbox`</span>
, <span class="methodparam"><span class="type">string</span>
`$text`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`textbox`  

`text`  

### Return Values

No value is returned.

newt\_textbox
=============

### Description

<span class="type">resource</span> <span
class="methodname">newt\_textbox</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">int</span> `$width`</span> ,
<span class="methodparam"><span class="type">int</span> `$height`</span>
\[, <span class="methodparam"><span class="type">int</span>
`$flags`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`width`  

`height`  

`flags`  

### Return Values

newt\_vertical\_scrollbar
=========================

### Description

<span class="type">resource</span> <span
class="methodname">newt\_vertical\_scrollbar</span> ( <span
class="methodparam"><span class="type">int</span> `$left`</span> , <span
class="methodparam"><span class="type">int</span> `$top`</span> , <span
class="methodparam"><span class="type">int</span> `$height`</span> \[,
<span class="methodparam"><span class="type">int</span>
`$normal_colorset`</span> \[, <span class="methodparam"><span
class="type">int</span> `$thumb_colorset`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`left`  

`top`  

`height`  

`normal_colorset`  

`thumb_colorset`  

### Return Values

newt\_wait\_for\_key
====================

Doesn't return until a key has been pressed

### Description

<span class="type">void</span> <span
class="methodname">newt\_wait\_for\_key</span> ( <span
class="methodparam">void</span> )

This function doesn't return until a key has been pressed. The keystroke
is then ignored. If a key is already in the terminal's buffer, this
function discards a keystroke and returns immediately.

### Return Values

No value is returned.

### See Also

-   <span class="function">newt\_clear\_key\_buffer</span>

newt\_win\_choice
=================

### Description

<span class="type">int</span> <span
class="methodname">newt\_win\_choice</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">string</span>
`$button1_text`</span> , <span class="methodparam"><span
class="type">string</span> `$button2_text`</span> , <span
class="methodparam"><span class="type">string</span> `$format`</span>
\[, <span class="methodparam"><span class="type">mixed</span>
`$args`</span> \[, <span class="methodparam"><span
class="type">mixed</span> `$...`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`title`  

`button1_text`  

`button2_text`  

`format`  

`args`  

### Return Values

newt\_win\_entries
==================

### Description

<span class="type">int</span> <span
class="methodname">newt\_win\_entries</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">string</span>
`$text`</span> , <span class="methodparam"><span class="type">int</span>
`$suggested_width`</span> , <span class="methodparam"><span
class="type">int</span> `$flex_down`</span> , <span
class="methodparam"><span class="type">int</span> `$flex_up`</span> ,
<span class="methodparam"><span class="type">int</span>
`$data_width`</span> , <span class="methodparam"><span
class="type">array</span> `&$items`</span> , <span
class="methodparam"><span class="type">string</span> `$button1`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$...`</span> \] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`title`  

`text`  

`suggested_width`  

`flex_down`  

`flex_up`  

`data_width`  

`items`  

`button1`  

`button2`  

### Return Values

### Examples

**Example \#1 A <span class="function">newt\_win\_entries</span>
example**

``` php
<?php

newt_init();
newt_cls();

$entries[] = array('text' => 'First name:', 'value' => &$f_name);
$entries[] = array('text' => 'Last name:',  'value' => &$l_name);

$rc = newt_win_entries("User information", "Please enter your credentials:", 50, 7, 7, 30, $entries, "Ok", "Back");
newt_finished ();

if ($rc != 2) {
    echo "Your name is: $f_name $l_name\n";
}
?>
```

newt\_win\_menu
===============

### Description

<span class="type">int</span> <span
class="methodname">newt\_win\_menu</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">string</span>
`$text`</span> , <span class="methodparam"><span class="type">int</span>
`$suggestedWidth`</span> , <span class="methodparam"><span
class="type">int</span> `$flexDown`</span> , <span
class="methodparam"><span class="type">int</span> `$flexUp`</span> ,
<span class="methodparam"><span class="type">int</span>
`$maxListHeight`</span> , <span class="methodparam"><span
class="type">array</span> `$items`</span> , <span
class="methodparam"><span class="type">int</span> `&$listItem`</span>
\[, <span class="methodparam"><span class="type">string</span>
`$button1`</span> \[, <span class="methodparam"><span
class="type">string</span> `$...`</span> \]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`title`  

`text`  

`suggestedWidth`  

`flexDown`  

`flexUp`  

`maxListHeight`  

`items`  

`listItem`  

`button1`  

### Return Values

No value is returned.

newt\_win\_message
==================

### Description

<span class="type">void</span> <span
class="methodname">newt\_win\_message</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">string</span>
`$button_text`</span> , <span class="methodparam"><span
class="type">string</span> `$format`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$args`</span> \[,
<span class="methodparam"><span class="type">mixed</span> `$...`</span>
\]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`title`  

`button_text`  

`format`  

`args`  

### Return Values

No value is returned.

newt\_win\_messagev
===================

### Description

<span class="type">void</span> <span
class="methodname">newt\_win\_messagev</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">string</span>
`$button_text`</span> , <span class="methodparam"><span
class="type">string</span> `$format`</span> , <span
class="methodparam"><span class="type">array</span> `$args`</span> )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`title`  

`button_text`  

`format`  

`args`  

### Return Values

No value is returned.

newt\_win\_ternary
==================

### Description

<span class="type">int</span> <span
class="methodname">newt\_win\_ternary</span> ( <span
class="methodparam"><span class="type">string</span> `$title`</span> ,
<span class="methodparam"><span class="type">string</span>
`$button1_text`</span> , <span class="methodparam"><span
class="type">string</span> `$button2_text`</span> , <span
class="methodparam"><span class="type">string</span>
`$button3_text`</span> , <span class="methodparam"><span
class="type">string</span> `$format`</span> \[, <span
class="methodparam"><span class="type">mixed</span> `$args`</span> \[,
<span class="methodparam"><span class="type">mixed</span> `$...`</span>
\]\] )

**Warning**

This function is currently not documented; only its argument list is
available.

### Parameters

`title`  
Its description

`button1_text`  
Its description

`button2_text`  
Its description

`button3_text`  
Its description

`format`  
Its description

`args`  
Its description

### Return Values

What the function returns, first on success, then on failure. See also
the &return.success; entity

**Table of Contents**

-   [newt\_bell](/ref/newt.html#newt_bell) — Send a beep to the terminal
-   [newt\_button\_bar](/ref/newt.html#newt_button_bar) — This function
    returns a grid containing the buttons created
-   [newt\_button](/ref/newt.html#newt_button) — Create a new button
-   [newt\_centered\_window](/ref/newt.html#newt_centered_window) — Open
    a centered window of the specified size
-   [newt\_checkbox\_get\_value](/ref/newt.html#newt_checkbox_get_value)
    — Retreives value of checkox resource
-   [newt\_checkbox\_set\_flags](/ref/newt.html#newt_checkbox_set_flags)
    — Configures checkbox resource
-   [newt\_checkbox\_set\_value](/ref/newt.html#newt_checkbox_set_value)
    — Sets the value of the checkbox
-   [newt\_checkbox\_tree\_add\_item](/ref/newt.html#newt_checkbox_tree_add_item)
    — Adds new item to the checkbox tree
-   [newt\_checkbox\_tree\_find\_item](/ref/newt.html#newt_checkbox_tree_find_item)
    — Finds an item in the checkbox tree
-   [newt\_checkbox\_tree\_get\_current](/ref/newt.html#newt_checkbox_tree_get_current)
    — Returns checkbox tree selected item
-   [newt\_checkbox\_tree\_get\_entry\_value](/ref/newt.html#newt_checkbox_tree_get_entry_value)
    — Description
-   [newt\_checkbox\_tree\_get\_multi\_selection](/ref/newt.html#newt_checkbox_tree_get_multi_selection)
    — Description
-   [newt\_checkbox\_tree\_get\_selection](/ref/newt.html#newt_checkbox_tree_get_selection)
    — Description
-   [newt\_checkbox\_tree\_multi](/ref/newt.html#newt_checkbox_tree_multi)
    — Description
-   [newt\_checkbox\_tree\_set\_current](/ref/newt.html#newt_checkbox_tree_set_current)
    — Description
-   [newt\_checkbox\_tree\_set\_entry\_value](/ref/newt.html#newt_checkbox_tree_set_entry_value)
    — Description
-   [newt\_checkbox\_tree\_set\_entry](/ref/newt.html#newt_checkbox_tree_set_entry)
    — Description
-   [newt\_checkbox\_tree\_set\_width](/ref/newt.html#newt_checkbox_tree_set_width)
    — Description
-   [newt\_checkbox\_tree](/ref/newt.html#newt_checkbox_tree) —
    Description
-   [newt\_checkbox](/ref/newt.html#newt_checkbox) — Description
-   [newt\_clear\_key\_buffer](/ref/newt.html#newt_clear_key_buffer) —
    Discards the contents of the terminal's input buffer without waiting
    for additional input
-   [newt\_cls](/ref/newt.html#newt_cls) — Description
-   [newt\_compact\_button](/ref/newt.html#newt_compact_button) —
    Description
-   [newt\_component\_add\_callback](/ref/newt.html#newt_component_add_callback)
    — Description
-   [newt\_component\_takes\_focus](/ref/newt.html#newt_component_takes_focus)
    — Description
-   [newt\_create\_grid](/ref/newt.html#newt_create_grid) — Description
-   [newt\_cursor\_off](/ref/newt.html#newt_cursor_off) — Description
-   [newt\_cursor\_on](/ref/newt.html#newt_cursor_on) — Description
-   [newt\_delay](/ref/newt.html#newt_delay) — Description
-   [newt\_draw\_form](/ref/newt.html#newt_draw_form) — Description
-   [newt\_draw\_root\_text](/ref/newt.html#newt_draw_root_text) —
    Displays the string text at the position indicated
-   [newt\_entry\_get\_value](/ref/newt.html#newt_entry_get_value) —
    Description
-   [newt\_entry\_set\_filter](/ref/newt.html#newt_entry_set_filter) —
    Description
-   [newt\_entry\_set\_flags](/ref/newt.html#newt_entry_set_flags) —
    Description
-   [newt\_entry\_set](/ref/newt.html#newt_entry_set) — Description
-   [newt\_entry](/ref/newt.html#newt_entry) — Description
-   [newt\_finished](/ref/newt.html#newt_finished) — Uninitializes newt
    interface
-   [newt\_form\_add\_component](/ref/newt.html#newt_form_add_component)
    — Adds a single component to the form
-   [newt\_form\_add\_components](/ref/newt.html#newt_form_add_components)
    — Add several components to the form
-   [newt\_form\_add\_hot\_key](/ref/newt.html#newt_form_add_hot_key) —
    Description
-   [newt\_form\_destroy](/ref/newt.html#newt_form_destroy) — Destroys a
    form
-   [newt\_form\_get\_current](/ref/newt.html#newt_form_get_current) —
    Description
-   [newt\_form\_run](/ref/newt.html#newt_form_run) — Runs a form
-   [newt\_form\_set\_background](/ref/newt.html#newt_form_set_background)
    — Description
-   [newt\_form\_set\_height](/ref/newt.html#newt_form_set_height) —
    Description
-   [newt\_form\_set\_size](/ref/newt.html#newt_form_set_size) —
    Description
-   [newt\_form\_set\_timer](/ref/newt.html#newt_form_set_timer) —
    Description
-   [newt\_form\_set\_width](/ref/newt.html#newt_form_set_width) —
    Description
-   [newt\_form\_watch\_fd](/ref/newt.html#newt_form_watch_fd) —
    Description
-   [newt\_form](/ref/newt.html#newt_form) — Create a form
-   [newt\_get\_screen\_size](/ref/newt.html#newt_get_screen_size) —
    Fills in the passed references with the current size of the terminal
-   [newt\_grid\_add\_components\_to\_form](/ref/newt.html#newt_grid_add_components_to_form)
    — Description
-   [newt\_grid\_basic\_window](/ref/newt.html#newt_grid_basic_window) —
    Description
-   [newt\_grid\_free](/ref/newt.html#newt_grid_free) — Description
-   [newt\_grid\_get\_size](/ref/newt.html#newt_grid_get_size) —
    Description
-   [newt\_grid\_h\_close\_stacked](/ref/newt.html#newt_grid_h_close_stacked)
    — Description
-   [newt\_grid\_h\_stacked](/ref/newt.html#newt_grid_h_stacked) —
    Description
-   [newt\_grid\_place](/ref/newt.html#newt_grid_place) — Description
-   [newt\_grid\_set\_field](/ref/newt.html#newt_grid_set_field) —
    Description
-   [newt\_grid\_simple\_window](/ref/newt.html#newt_grid_simple_window)
    — Description
-   [newt\_grid\_v\_close\_stacked](/ref/newt.html#newt_grid_v_close_stacked)
    — Description
-   [newt\_grid\_v\_stacked](/ref/newt.html#newt_grid_v_stacked) —
    Description
-   [newt\_grid\_wrapped\_window\_at](/ref/newt.html#newt_grid_wrapped_window_at)
    — Description
-   [newt\_grid\_wrapped\_window](/ref/newt.html#newt_grid_wrapped_window)
    — Description
-   [newt\_init](/ref/newt.html#newt_init) — Initialize newt
-   [newt\_label\_set\_text](/ref/newt.html#newt_label_set_text) —
    Description
-   [newt\_label](/ref/newt.html#newt_label) — Description
-   [newt\_listbox\_append\_entry](/ref/newt.html#newt_listbox_append_entry)
    — Description
-   [newt\_listbox\_clear\_selection](/ref/newt.html#newt_listbox_clear_selection)
    — Description
-   [newt\_listbox\_clear](/ref/newt.html#newt_listbox_clear) —
    Description
-   [newt\_listbox\_delete\_entry](/ref/newt.html#newt_listbox_delete_entry)
    — Description
-   [newt\_listbox\_get\_current](/ref/newt.html#newt_listbox_get_current)
    — Description
-   [newt\_listbox\_get\_selection](/ref/newt.html#newt_listbox_get_selection)
    — Description
-   [newt\_listbox\_insert\_entry](/ref/newt.html#newt_listbox_insert_entry)
    — Description
-   [newt\_listbox\_item\_count](/ref/newt.html#newt_listbox_item_count)
    — Description
-   [newt\_listbox\_select\_item](/ref/newt.html#newt_listbox_select_item)
    — Description
-   [newt\_listbox\_set\_current\_by\_key](/ref/newt.html#newt_listbox_set_current_by_key)
    — Description
-   [newt\_listbox\_set\_current](/ref/newt.html#newt_listbox_set_current)
    — Description
-   [newt\_listbox\_set\_data](/ref/newt.html#newt_listbox_set_data) —
    Description
-   [newt\_listbox\_set\_entry](/ref/newt.html#newt_listbox_set_entry) —
    Description
-   [newt\_listbox\_set\_width](/ref/newt.html#newt_listbox_set_width) —
    Description
-   [newt\_listbox](/ref/newt.html#newt_listbox) — Description
-   [newt\_listitem\_get\_data](/ref/newt.html#newt_listitem_get_data) —
    Description
-   [newt\_listitem\_set](/ref/newt.html#newt_listitem_set) —
    Description
-   [newt\_listitem](/ref/newt.html#newt_listitem) — Description
-   [newt\_open\_window](/ref/newt.html#newt_open_window) — Open a
    window of the specified size and position
-   [newt\_pop\_help\_line](/ref/newt.html#newt_pop_help_line) —
    Replaces the current help line with the one from the stack
-   [newt\_pop\_window](/ref/newt.html#newt_pop_window) — Removes the
    top window from the display
-   [newt\_push\_help\_line](/ref/newt.html#newt_push_help_line) — Saves
    the current help line on a stack, and displays the new line
-   [newt\_radio\_get\_current](/ref/newt.html#newt_radio_get_current) —
    Description
-   [newt\_radiobutton](/ref/newt.html#newt_radiobutton) — Description
-   [newt\_redraw\_help\_line](/ref/newt.html#newt_redraw_help_line) —
    Description
-   [newt\_reflow\_text](/ref/newt.html#newt_reflow_text) — Description
-   [newt\_refresh](/ref/newt.html#newt_refresh) — Updates modified
    portions of the screen
-   [newt\_resize\_screen](/ref/newt.html#newt_resize_screen) —
    Description
-   [newt\_resume](/ref/newt.html#newt_resume) — Resume using the newt
    interface after calling newt\_suspend
-   [newt\_run\_form](/ref/newt.html#newt_run_form) — Runs a form
-   [newt\_scale\_set](/ref/newt.html#newt_scale_set) — Description
-   [newt\_scale](/ref/newt.html#newt_scale) — Description
-   [newt\_scrollbar\_set](/ref/newt.html#newt_scrollbar_set) —
    Description
-   [newt\_set\_help\_callback](/ref/newt.html#newt_set_help_callback) —
    Description
-   [newt\_set\_suspend\_callback](/ref/newt.html#newt_set_suspend_callback)
    — Set a callback function which gets invoked when user presses the
    suspend key
-   [newt\_suspend](/ref/newt.html#newt_suspend) — Tells newt to return
    the terminal to its initial state
-   [newt\_textbox\_get\_num\_lines](/ref/newt.html#newt_textbox_get_num_lines)
    — Description
-   [newt\_textbox\_reflowed](/ref/newt.html#newt_textbox_reflowed) —
    Description
-   [newt\_textbox\_set\_height](/ref/newt.html#newt_textbox_set_height)
    — Description
-   [newt\_textbox\_set\_text](/ref/newt.html#newt_textbox_set_text) —
    Description
-   [newt\_textbox](/ref/newt.html#newt_textbox) — Description
-   [newt\_vertical\_scrollbar](/ref/newt.html#newt_vertical_scrollbar)
    — Description
-   [newt\_wait\_for\_key](/ref/newt.html#newt_wait_for_key) — Doesn't
    return until a key has been pressed
-   [newt\_win\_choice](/ref/newt.html#newt_win_choice) — Description
-   [newt\_win\_entries](/ref/newt.html#newt_win_entries) — Description
-   [newt\_win\_menu](/ref/newt.html#newt_win_menu) — Description
-   [newt\_win\_message](/ref/newt.html#newt_win_message) — Description
-   [newt\_win\_messagev](/ref/newt.html#newt_win_messagev) —
    Description
-   [newt\_win\_ternary](/ref/newt.html#newt_win_ternary) — Description

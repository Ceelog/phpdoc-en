String Filters
--------------

Each of these filters does precisely what their name implies and
correspond to the behavior of a built-in php string handling function.
For more information on a given filter, refer to the manual page for the
corresponding function.

string.rot13
------------

Use of this filter is equivalent to processing all stream data through
the <span class="function">str\_rot13</span> function.

**Example \#1 string.rot13**

``` php
<?php
$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'string.rot13');
fwrite($fp, "This is a test.\n");
/* Outputs:  Guvf vf n grfg.   */
?>
```

string.toupper
--------------

Use of this filter is equivalent to processing all stream data through
the <span class="function">strtoupper</span> function.

**Example \#2 string.toupper**

``` php
<?php
$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'string.toupper');
fwrite($fp, "This is a test.\n");
/* Outputs:  THIS IS A TEST.   */
?>
```

string.tolower
--------------

Use of this filter is equivalent to processing all stream data through
the <span class="function">strtolower</span> function.

**Example \#3 string.tolower**

``` php
<?php
$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'string.tolower');
fwrite($fp, "This is a test.\n");
/* Outputs:  this is a test.   */
?>
```

string.strip\_tags
------------------

Use of this filter is equivalent to processing all stream data through
the <span class="function">strip\_tags</span> function. It accepts
parameters in one of two forms: Either as a string containing a list of
tags similar to the second parameter of the <span
class="function">strip\_tags</span> function, or as an array of tag
names.

**Warning**

This feature has been *DEPRECATED* as of PHP 7.3.0. Relying on this
feature is highly discouraged.

**Example \#4 string.strip\_tags**

``` php
<?php
$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'string.strip_tags', STREAM_FILTER_WRITE, "<b><i><u>");
fwrite($fp, "<b>bolded text</b> enlarged to a <h1>level 1 heading</h1>\n");
fclose($fp);
/* Outputs:  <b>bolded text</b> enlarged to a level 1 heading   */

$fp = fopen('php://output', 'w');
stream_filter_append($fp, 'string.strip_tags', STREAM_FILTER_WRITE, array('b','i','u'));
fwrite($fp, "<b>bolded text</b> enlarged to a <h1>level 1 heading</h1>\n");
fclose($fp);
/* Outputs:  <b>bolded text</b> enlarged to a level 1 heading   */
?>
```

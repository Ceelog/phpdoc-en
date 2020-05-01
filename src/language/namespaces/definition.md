Defining namespaces
-------------------

Although any valid PHP code can be contained within a namespace, only
the following types of code are affected by namespaces: classes
(including abstracts and traits), interfaces, functions and constants.

Namespaces are declared using the *namespace* keyword. A file containing
a namespace must declare the namespace at the top of the file before any
other code - with one exception: the
<a href="/control-structures/declare.html" class="xref">declare</a>
keyword.

**Example \#1 Declaring a single namespace**

``` php
<?php
namespace MyProject;

const CONNECT_OK = 1;
class Connection { /* ... */ }
function connect() { /* ... */ }

?>
```

> **Note**: <span class="simpara"> Fully qualified names (i.e. names
> starting with a backslash) are not allowed in namespace declarations,
> because such constructs are interpreted as relative namespace
> expressions. </span>

The only code construct allowed before a namespace declaration is the
*declare* statement, for defining encoding of a source file. In
addition, no non-PHP code may precede a namespace declaration, including
extra whitespace:

**Example \#2 Declaring a single namespace**

``` php
<html>
<?php
namespace MyProject; // fatal error - namespace must be the first statement in the script
?>
```

In addition, unlike any other PHP construct, the same namespace may be
defined in multiple files, allowing splitting up of a namespace's
contents across the filesystem.

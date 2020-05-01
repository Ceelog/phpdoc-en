namespace keyword and \_\_NAMESPACE\_\_ constant
------------------------------------------------

PHP supports two ways of abstractly accessing elements within the
current namespace, the **`__NAMESPACE__`** magic constant, and the
*namespace* keyword.

The value of **`__NAMESPACE__`** is a string that contains the current
namespace name. In global, un-namespaced code, it contains an empty
string.

**Example \#1 \_\_NAMESPACE\_\_ example, namespaced code**

``` php
<?php
namespace MyProject;

echo '"', __NAMESPACE__, '"'; // outputs "MyProject"
?>
```

**Example \#2 \_\_NAMESPACE\_\_ example, global code**

``` php
<?php

echo '"', __NAMESPACE__, '"'; // outputs ""
?>
```

The **`__NAMESPACE__`** constant is useful for dynamically constructing
names, for instance:

**Example \#3 using \_\_NAMESPACE\_\_ for dynamic name construction**

``` php
<?php
namespace MyProject;

function get($classname)
{
    $a = __NAMESPACE__ . '\\' . $classname;
    return new $a;
}
?>
```

The *namespace* keyword can be used to explicitly request an element
from the current namespace or a sub-namespace. It is the namespace
equivalent of the *self* operator for classes.

**Example \#4 the namespace operator, inside a namespace**

``` php
<?php
namespace MyProject;

use blah\blah as mine; // see "Using namespaces: Aliasing/Importing"

blah\mine(); // calls function MyProject\blah\mine()
namespace\blah\mine(); // calls function MyProject\blah\mine()

namespace\func(); // calls function MyProject\func()
namespace\sub\func(); // calls function MyProject\sub\func()
namespace\cname::method(); // calls static method "method" of class MyProject\cname
$a = new namespace\sub\cname(); // instantiates object of class MyProject\sub\cname
$b = namespace\CONSTANT; // assigns value of constant MyProject\CONSTANT to $b
?>
```

**Example \#5 the namespace operator, in global code**

``` php
<?php

namespace\func(); // calls function func()
namespace\sub\func(); // calls function sub\func()
namespace\cname::method(); // calls static method "method" of class cname
$a = new namespace\sub\cname(); // instantiates object of class sub\cname
$b = namespace\CONSTANT; // assigns value of constant CONSTANT to $b
?>
```

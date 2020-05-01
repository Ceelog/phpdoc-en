Declaring sub-namespaces
------------------------

Much like directories and files, PHP namespaces also contain the ability
to specify a hierarchy of namespace names. Thus, a namespace name can be
defined with sub-levels:

**Example \#1 Declaring a single namespace with hierarchy**

``` php
<?php
namespace MyProject\Sub\Level;

const CONNECT_OK = 1;
class Connection { /* ... */ }
function connect() { /* ... */  }

?>
```

The above example creates constant *MyProject\\Sub\\Level\\CONNECT\_OK*,
class *MyProject\\Sub\\Level\\Connection* and function
*MyProject\\Sub\\Level\\connect*.

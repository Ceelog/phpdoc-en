Tips
----

In order to write future-proof code, it is recommended that you don't
place many variables, functions or classes in the global namespace. This
will prevent naming conflicts with 3rd party code as well as possible
future additions to the language.

One common way to prevent naming conflicts of functions and classes is
to add them to their own dedicated
<a href="/language/namespaces.html" class="link">namespace</a>.

``` php
<?php

namespace MyProject;

function my_function() {
    return true;
}

\MyProject\my_function();
```

This still needs you to keep track of already used namespaces, but once
you have decided on a namespace you will be using you can add all
functions and classes to it without having to think about conflicts
again.

It is considered best practice to limit the number of variables added to
the global scope in order to prevent naming conflicts with 3rd party
code.

> **Note**: **Variable scoping**  
>
> Because of PHP's
> <a href="/language/variables/scope.html" class="link">scoping rules</a>
> variables defined inside functions and methods are not in the global
> scope and as such cannot conflict with other variables defined in the
> global scope.

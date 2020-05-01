Autoloading Classes
-------------------

Many developers writing object-oriented applications create one PHP
source file per class definition. One of the biggest annoyances is
having to write a long list of needed includes at the beginning of each
script (one for each class).

In PHP 5, this is no longer necessary. The <span
class="function">spl\_autoload\_register</span> function registers any
number of autoloaders, enabling for classes and interfaces to be
automatically loaded if they are currently not defined. By registering
autoloaders, PHP is given a last chance to load the class or interface
before it fails with an error.

**Tip**

Although the <span class="function">\_\_autoload</span> function can
also be used for autoloading classes and interfaces, it's preferred to
use the <span class="function">spl\_autoload\_register</span> function.
This is because it is a more flexible alternative (enabling for any
number of autoloaders to be specified in the application, such as in
third party libraries). For this reason, using <span
class="function">\_\_autoload</span> is discouraged and deprecated as of
PHP 7.2.0.

> **Note**:
>
> Prior to PHP 5.3, exceptions thrown in the <span
> class="function">\_\_autoload</span> function could not be caught in
> the <a href="/language/exceptions.html" class="link">catch</a> block
> and would result in a fatal error. From PHP 5.3 and upwards, this is
> possible provided that if a custom exception is thrown, then the
> custom exception class is available. The <span
> class="function">\_\_autoload</span> function may be used recursively
> to autoload the custom exception class.

> **Note**:
>
> Autoloading is not available if using PHP in CLI
> <a href="/features/commandline.html" class="link">interactive mode</a>.

> **Note**:
>
> If the class name is used e.g. in <span
> class="function">call\_user\_func</span> then it can contain some
> dangerous characters such as *../*. It is recommended to not use the
> user-input in such functions or at least verify the input in <span
> class="function">\_\_autoload</span>.

**Example \#1 Autoload example**

This example attempts to load the classes *MyClass1* and *MyClass2* from
the files `MyClass1.php` and `MyClass2.php` respectively.

``` php
<?php
spl_autoload_register(function ($class_name) {
    include $class_name . '.php';
});

$obj  = new MyClass1();
$obj2 = new MyClass2(); 
?>
```

**Example \#2 Autoload other example**

This example attempts to load the interface *ITest*.

``` php
<?php

spl_autoload_register(function ($name) {
    var_dump($name);
});

class Foo implements ITest {
}

/*
string(5) "ITest"

Fatal error: Interface 'ITest' not found in ...
*/
?>
```

**Example \#3 Autoloading with exception handling for 5.3.0+**

This example throws an exception and demonstrates the try/catch block.

``` php
<?php
spl_autoload_register(function ($name) {
    echo "Want to load $name.\n";
    throw new Exception("Unable to load $name.");
});

try {
    $obj = new NonLoadableClass();
} catch (Exception $e) {
    echo $e->getMessage(), "\n";
}
?>
```

The above example will output:

    Want to load NonLoadableClass.
    Unable to load NonLoadableClass.

**Example \#4 Autoloading with exception handling for 5.3.0+ - Missing
custom exception**

This example throws an exception for a non-loadable, custom exception.

``` php
<?php
spl_autoload_register(function ($name) {
    echo "Want to load $name.\n";
    throw new MissingException("Unable to load $name.");
});

try {
    $obj = new NonLoadableClass();
} catch (Exception $e) {
    echo $e->getMessage(), "\n";
}
?>
```

The above example will output:

    Want to load NonLoadableClass.
    Want to load MissingException.

    Fatal error: Class 'MissingException' not found in testMissingException.php on line 4

-   <span class="function">unserialize</span>
-   <a href="/var/setup.html#" class="link">unserialize_callback_func</a>
-   <span class="function">spl\_autoload\_register</span>
-   <span class="function">spl\_autoload</span>
-   <span class="function">\_\_autoload</span>

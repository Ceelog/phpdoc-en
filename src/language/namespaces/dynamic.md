Namespaces and dynamic language features
----------------------------------------

PHP's implementation of namespaces is influenced by its dynamic nature
as a programming language. Thus, to convert code like the following
example into namespaced code:

**Example \#1 Dynamically accessing elements**

example1.php:

``` php
<?php
class classname
{
    function __construct()
    {
        echo __METHOD__,"\n";
    }
}
function funcname()
{
    echo __FUNCTION__,"\n";
}
const constname = "global";

$a = 'classname';
$obj = new $a; // prints classname::__construct
$b = 'funcname';
$b(); // prints funcname
echo constant('constname'), "\n"; // prints global
?>
```

One must use the fully qualified name (class name with namespace
prefix). Note that because there is no difference between a qualified
and a fully qualified Name inside a dynamic class name, function name,
or constant name, the leading backslash is not necessary.

**Example \#2 Dynamically accessing namespaced elements**

``` php
<?php
namespace namespacename;
class classname
{
    function __construct()
    {
        echo __METHOD__,"\n";
    }
}
function funcname()
{
    echo __FUNCTION__,"\n";
}
const constname = "namespaced";

/* note that if using double quotes, "\\namespacename\\classname" must be used */
$a = '\namespacename\classname';
$obj = new $a; // prints namespacename\classname::__construct
$a = 'namespacename\classname';
$obj = new $a; // also prints namespacename\classname::__construct
$b = 'namespacename\funcname';
$b(); // prints namespacename\funcname
$b = '\namespacename\funcname';
$b(); // also prints namespacename\funcname
echo constant('\namespacename\constname'), "\n"; // prints namespaced
echo constant('namespacename\constname'), "\n"; // also prints namespaced
?>
```

Be sure to read the
<a href="/language/namespaces/faq.html#language.namespaces.faq.quote" class="link">note about escaping namespace names in strings</a>.

Using namespaces: Basics
------------------------

Before discussing the use of namespaces, it is important to understand
how PHP knows which namespaced element your code is requesting. A simple
analogy can be made between PHP namespaces and a filesystem. There are
three ways to access a file in a file system:

1.  <span class="simpara"> Relative file name like *foo.txt*. This
    resolves to *currentdirectory/foo.txt* where currentdirectory is the
    directory currently occupied. So if the current directory is
    */home/foo*, the name resolves to */home/foo/foo.txt*. </span>
2.  <span class="simpara"> Relative path name like
    *subdirectory/foo.txt*. This resolves to
    *currentdirectory/subdirectory/foo.txt*. </span>
3.  <span class="simpara"> Absolute path name like */main/foo.txt*. This
    resolves to */main/foo.txt*. </span>

The same principle can be applied to namespaced elements in PHP. For
example, a class name can be referred to in three ways:

1.  <span class="simpara"> Unqualified name, or an unprefixed class name
    like *$a = new foo();* or *foo::staticmethod();*. If the current
    namespace is *currentnamespace*, this resolves to
    *currentnamespace\\foo*. If the code is global, non-namespaced code,
    this resolves to *foo*. </span> <span class="simpara"> One caveat:
    unqualified names for functions and constants will resolve to global
    functions and constants if the namespaced function or constant is
    not defined. See
    <a href="/language/namespaces/fallback.html" class="link">Using namespaces: fallback to global function/constant</a>
    for details. </span>
2.  <span class="simpara"> Qualified name, or a prefixed class name like
    *$a = new subnamespace\\foo();* or
    *subnamespace\\foo::staticmethod();*. If the current namespace is
    *currentnamespace*, this resolves to
    *currentnamespace\\subnamespace\\foo*. If the code is global,
    non-namespaced code, this resolves to *subnamespace\\foo*. </span>
3.  <span class="simpara"> Fully qualified name, or a prefixed name with
    global prefix operator like *$a = new \\currentnamespace\\foo();* or
    *\\currentnamespace\\foo::staticmethod();*. This always resolves to
    the literal name specified in the code, *currentnamespace\\foo*.
    </span>

Here is an example of the three kinds of syntax in actual code:

file1.php

``` php
<?php
namespace Foo\Bar\subnamespace;

const FOO = 1;
function foo() {}
class foo
{
    static function staticmethod() {}
}
?>
```

file2.php

``` php
<?php
namespace Foo\Bar;
include 'file1.php';

const FOO = 2;
function foo() {}
class foo
{
    static function staticmethod() {}
}

/* Unqualified name */
foo(); // resolves to function Foo\Bar\foo
foo::staticmethod(); // resolves to class Foo\Bar\foo, method staticmethod
echo FOO; // resolves to constant Foo\Bar\FOO

/* Qualified name */
subnamespace\foo(); // resolves to function Foo\Bar\subnamespace\foo
subnamespace\foo::staticmethod(); // resolves to class Foo\Bar\subnamespace\foo,
                                  // method staticmethod
echo subnamespace\FOO; // resolves to constant Foo\Bar\subnamespace\FOO
                                  
/* Fully qualified name */
\Foo\Bar\foo(); // resolves to function Foo\Bar\foo
\Foo\Bar\foo::staticmethod(); // resolves to class Foo\Bar\foo, method staticmethod
echo \Foo\Bar\FOO; // resolves to constant Foo\Bar\FOO
?>
```

Note that to access any global class, function or constant, a fully
qualified name can be used, such as <span
class="function">\\strlen</span> or <span
class="classname">\\Exception</span> or *\\INI\_ALL*.

**Example \#1 Accessing global classes, functions and constants from
within a namespace**

``` php
<?php
namespace Foo;

function strlen() {}
const INI_ALL = 3;
class Exception {}

$a = \strlen('hi'); // calls global function strlen
$b = \INI_ALL; // accesses global constant INI_ALL
$c = new \Exception('error'); // instantiates global class Exception
?>
```

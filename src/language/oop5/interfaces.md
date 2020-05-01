Object Interfaces
-----------------

Object interfaces allow you to create code which specifies which methods
a class must implement, without having to define how these methods are
implemented.

Interfaces are defined in the same way as a class, but with the
*interface* keyword replacing the *class* keyword and without any of the
methods having their contents defined.

All methods declared in an interface must be public; this is the nature
of an interface.

Note that it is possible to declare a
<a href="/language/oop5/decon.html#language.oop5.decon.constructor" class="link">constructor</a>
in an interface, which can be useful in some contexts, e.g. for use by
factories.

### *implements*

To implement an interface, the *implements* operator is used. All
methods in the interface must be implemented within a class; failure to
do so will result in a fatal error. Classes may implement more than one
interface if desired by separating each interface with a comma.

> **Note**:
>
> Prior to PHP 5.3.9, a class could not implement two interfaces that
> specified a method with the same name, since it would cause ambiguity.
> More recent versions of PHP allow this as long as the duplicate
> methods have the same signature.

> **Note**:
>
> Interfaces can be extended like classes using the
> <a href="/language/oop5/inheritance.html" class="link">extends</a>
> operator.

> **Note**:
>
> The class implementing the interface must use a method signatures
> which is compatible with LSP (Liskov Substitution Principle). Not
> doing so will result in a fatal error.

### *Constants*

It's possible for interfaces to have constants. Interface constants work
exactly like
<a href="/language/oop5/constants.html" class="link">class constants</a>
except they cannot be overridden by a class/interface that inherits
them.

### Examples

**Example \#1 Interface example**

``` php
<?php

// Declare the interface 'iTemplate'
interface iTemplate
{
    public function setVariable($name, $var);
    public function getHtml($template);
}

// Implement the interface
// This will work
class Template implements iTemplate
{
    private $vars = array();
  
    public function setVariable($name, $var)
    {
        $this->vars[$name] = $var;
    }
  
    public function getHtml($template)
    {
        foreach($this->vars as $name => $value) {
            $template = str_replace('{' . $name . '}', $value, $template);
        }
 
        return $template;
    }
}

// This will not work
// Fatal error: Class BadTemplate contains 1 abstract methods
// and must therefore be declared abstract (iTemplate::getHtml)
class BadTemplate implements iTemplate
{
    private $vars = array();
  
    public function setVariable($name, $var)
    {
        $this->vars[$name] = $var;
    }
}
?>
```

**Example \#2 Extendable Interfaces**

``` php
<?php
interface a
{
    public function foo();
}

interface b extends a
{
    public function baz(Baz $baz);
}

// This will work
class c implements b
{
    public function foo()
    {
    }

    public function baz(Baz $baz)
    {
    }
}

// This will not work and result in a fatal error
class d implements b
{
    public function foo()
    {
    }

    public function baz(Foo $foo)
    {
    }
}
?>
```

**Example \#3 Multiple interface inheritance**

``` php
<?php
interface a
{
    public function foo();
}

interface b
{
    public function bar();
}

interface c extends a, b
{
    public function baz();
}

class d implements c
{
    public function foo()
    {
    }

    public function bar()
    {
    }

    public function baz()
    {
    }
}
?>
```

**Example \#4 Interfaces with constants**

``` php
<?php
interface a
{
    const b = 'Interface constant';
}

// Prints: Interface constant
echo a::b;


// This will however not work because it's not allowed to 
// override constants.
class b implements a
{
    const b = 'Class constant';
}
?>
```

An interface, together with type-hinting, provides a good way to make
sure that a particular object contains particular methods. See
<a href="/language/operators/type.html" class="link">instanceof</a>
operator and
<a href="/language/oop5/typehinting.html" class="link">type hinting</a>.

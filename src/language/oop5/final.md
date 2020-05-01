Final Keyword
-------------

PHP 5 introduces the final keyword, which prevents child classes from
overriding a method by prefixing the definition with *final*. If the
class itself is being defined final then it cannot be extended.

**Example \#1 Final methods example**

``` php
<?php
class BaseClass {
   public function test() {
       echo "BaseClass::test() called\n";
   }
   
   final public function moreTesting() {
       echo "BaseClass::moreTesting() called\n";
   }
}

class ChildClass extends BaseClass {
   public function moreTesting() {
       echo "ChildClass::moreTesting() called\n";
   }
}
// Results in Fatal error: Cannot override final method BaseClass::moreTesting()
?>
```

**Example \#2 Final class example**

``` php
<?php
final class BaseClass {
   public function test() {
       echo "BaseClass::test() called\n";
   }

   // Here it doesn't matter if you specify the function as final or not
   final public function moreTesting() {
       echo "BaseClass::moreTesting() called\n";
   }
}

class ChildClass extends BaseClass {
}
// Results in Fatal error: Class ChildClass may not inherit from final class (BaseClass)
?>
```

> **Note**: <span class="simpara"> Properties and constants cannot be
> declared final, only classes and methods may be declared as final.
> </span>

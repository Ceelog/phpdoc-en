Late Static Bindings
--------------------

As of PHP 5.3.0, PHP implements a feature called late static bindings
which can be used to reference the called class in a context of static
inheritance.

More precisely, late static bindings work by storing the class named in
the last "non-forwarding call". In case of static method calls, this is
the class explicitly named (usually the one on the left of the
<a href="/language/oop5/paamayim-nekudotayim.html" class="link"><em>::</em></a>
operator); in case of non static method calls, it is the class of the
object. A "forwarding call" is a static one that is introduced by
*self::*, *parent::*, *static::*, or, if going up in the class
hierarchy, <span class="function">forward\_static\_call</span>. The
function <span class="function">get\_called\_class</span> can be used to
retrieve a string with the name of the called class and *static::*
introduces its scope.

This feature was named "late static bindings" with an internal
perspective in mind. "Late binding" comes from the fact that *static::*
will not be resolved using the class where the method is defined but it
will rather be computed using runtime information. It was also called a
"static binding" as it can be used for (but is not limited to) static
method calls.

### Limitations of *self::*

Static references to the current class like *self::* or *\_\_CLASS\_\_*
are resolved using the class in which the function belongs, as in where
it was defined:

**Example \#1 *self::* usage**

``` php
<?php
class A {
    public static function who() {
        echo __CLASS__;
    }
    public static function test() {
        self::who();
    }
}

class B extends A {
    public static function who() {
        echo __CLASS__;
    }
}

B::test();
?>
```

The above example will output:

    A

### Late Static Bindings' usage

Late static bindings tries to solve that limitation by introducing a
keyword that references the class that was initially called at runtime.
Basically, a keyword that would allow you to reference *B* from *test()*
in the previous example. It was decided not to introduce a new keyword
but rather use *static* that was already reserved.

**Example \#2 *static::* simple usage**

``` php
<?php
class A {
    public static function who() {
        echo __CLASS__;
    }
    public static function test() {
        static::who(); // Here comes Late Static Bindings
    }
}

class B extends A {
    public static function who() {
        echo __CLASS__;
    }
}

B::test();
?>
```

The above example will output:

    B

> **Note**:
>
> In non-static contexts, the called class will be the class of the
> object instance. Since *$this-\>* will try to call private methods
> from the same scope, using *static::* may give different results.
> Another difference is that *static::* can only refer to static
> properties.

**Example \#3 *static::* usage in a non-static context**

``` php
<?php
class A {
    private function foo() {
        echo "success!\n";
    }
    public function test() {
        $this->foo();
        static::foo();
    }
}

class B extends A {
   /* foo() will be copied to B, hence its scope will still be A and
    * the call be successful */
}

class C extends A {
    private function foo() {
        /* original method is replaced; the scope of the new one is C */
    }
}

$b = new B();
$b->test();
$c = new C();
$c->test();   //fails
?>
```

The above example will output:

    success!
    success!
    success!


    Fatal error:  Call to private method C::foo() from context 'A' in /tmp/test.php on line 9

> **Note**:
>
> Late static bindings' resolution will stop at a fully resolved static
> call with no fallback. On the other hand, static calls using keywords
> like *parent::* or *self::* will forward the calling information.
>
> **Example \#4 Forwarding and non-forwarding calls**
>
> ``` php
> <?php
> class A {
>     public static function foo() {
>         static::who();
>     }
>
>     public static function who() {
>         echo __CLASS__."\n";
>     }
> }
>
> class B extends A {
>     public static function test() {
>         A::foo();
>         parent::foo();
>         self::foo();
>     }
>
>     public static function who() {
>         echo __CLASS__."\n";
>     }
> }
> class C extends B {
>     public static function who() {
>         echo __CLASS__."\n";
>     }
> }
>
> C::test();
> ?>
> ```
>
> The above example will output:
>
>     A
>     C
>     C

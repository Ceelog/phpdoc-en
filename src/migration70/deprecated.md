Deprecated features in PHP 7.0.x
--------------------------------

### PHP 4 style constructors

PHP 4 style constructors (methods that have the same name as the class
they are defined in) are deprecated, and will be removed in the future.
PHP 7 will emit **`E_DEPRECATED`** if a PHP 4 constructor is the only
constructor defined within a class. Classes that implement a <span
class="function">\_\_construct</span> method are unaffected.

``` php
<?php
class foo {
    function foo() {
        echo 'I am the constructor';
    }
}
?>
```

The above example will output:

    Deprecated: Methods with the same name as their class will not be constructors in a future version of PHP; foo has a deprecated constructor in example.php on line 3

### Static calls to non-static methods

<a href="/language/oop5/static.html" class="link">Static</a> calls to
methods that are not declared **static** are deprecated, and may be
removed in the future.

``` php
<?php
class foo {
    function bar() {
        echo 'I am not static!';
    }
}

foo::bar();
?>
```

The above example will output:

    Deprecated: Non-static method foo::bar() should not be called statically in - on line 8
    I am not static!

### <span class="function">password\_hash</span> salt option

The salt option for the <span class="function">password\_hash</span>
function has been deprecated to prevent developers from generating their
own (usually insecure) salts. The function itself generates a
cryptographically secure salt when no salt is provided by the developer
- therefore custom salt generation should not be needed.

### *capture\_session\_meta* SSL context option

The *capture\_session\_meta* SSL context option has been deprecated. SSL
metadata is now available through the <span
class="function">stream\_get\_meta\_data</span> function.

### <a href="/book/ldap.html" class="link">LDAP</a> deprecations

The following function has been deprecated:

-   <span class="simpara"> <span class="function">ldap\_sort</span>
    </span>

Extending
=========

If you want to create specialized versions of the built-in classes (say,
for creating colorized HTML when being exported, having easy-access
member variables instead of methods or having utility methods), you may
go ahead and extend them.

**Example \#1 Extending the built-in classes**

``` php
<?php
/**
 * My Reflection_Method class
 */
class My_Reflection_Method extends ReflectionMethod
{
    public $visibility = array();

    public function __construct($o, $m)
    {
        parent::__construct($o, $m);
        $this->visibility = Reflection::getModifierNames($this->getModifiers());
    }
}

/**
 * Demo class #1
 *
 */
class T {
    protected function x() {}
}

/**
 * Demo class #2
 *
 */
class U extends T {
    function x() {}
}

// Print out information
var_dump(new My_Reflection_Method('U', 'x'));
?>
```

The above example will output something similar to:

    object(My_Reflection_Method)#1 (3) {
      ["visibility"]=>
      array(1) {
        [0]=>
        string(6) "public"
      }
      ["name"]=>
      string(1) "x"
      ["class"]=>
      string(1) "U"
    }

**Caution**

If you're overwriting the constructor, remember to call the parent's
constructor before any code you insert. Failing to do so will result in
the following: *Fatal error: Internal error: Failed to retrieve the
reflection object*

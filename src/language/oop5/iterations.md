Object Iteration
----------------

PHP 5 provides a way for objects to be defined so it is possible to
iterate through a list of items, with, for example a
<a href="/control-structures/foreach.html" class="link">foreach</a>
statement. By default, all
<a href="/language/oop5/visibility.html" class="link">visible</a>
properties will be used for the iteration.

**Example \#1 Simple Object Iteration**

``` php
<?php
class MyClass
{
    public $var1 = 'value 1';
    public $var2 = 'value 2';
    public $var3 = 'value 3';

    protected $protected = 'protected var';
    private   $private   = 'private var';

    function iterateVisible() {
       echo "MyClass::iterateVisible:\n";
       foreach ($this as $key => $value) {
           print "$key => $value\n";
       }
    }
}

$class = new MyClass();

foreach($class as $key => $value) {
    print "$key => $value\n";
}
echo "\n";


$class->iterateVisible();

?>
```

The above example will output:

    var1 => value 1
    var2 => value 2
    var3 => value 3

    MyClass::iterateVisible:
    var1 => value 1
    var2 => value 2
    var3 => value 3
    protected => protected var
    private => private var

As the output shows, the
<a href="/control-structures/foreach.html" class="link">foreach</a>
iterated through all of the
<a href="/language/oop5/visibility.html" class="link">visible</a>
properties that could be accessed.

To take it a step further, the <span
class="interfacename">Iterator</span>
<a href="/language/oop5/interfaces.html" class="link">interface</a> may
be implemented. This allows the object to dictate how it will be
iterated and what values will be available on each iteration.

**Example \#2 Object Iteration implementing Iterator**

``` php
<?php
class MyIterator implements Iterator
{
    private $var = array();

    public function __construct($array)
    {
        if (is_array($array)) {
            $this->var = $array;
        }
    }

    public function rewind()
    {
        echo "rewinding\n";
        reset($this->var);
    }
  
    public function current()
    {
        $var = current($this->var);
        echo "current: $var\n";
        return $var;
    }
  
    public function key() 
    {
        $var = key($this->var);
        echo "key: $var\n";
        return $var;
    }
  
    public function next() 
    {
        $var = next($this->var);
        echo "next: $var\n";
        return $var;
    }
  
    public function valid()
    {
        $key = key($this->var);
        $var = ($key !== NULL && $key !== FALSE);
        echo "valid: $var\n";
        return $var;
    }

}

$values = array(1,2,3);
$it = new MyIterator($values);

foreach ($it as $a => $b) {
    print "$a: $b\n";
}
?>
```

The above example will output:

    rewinding
    valid: 1
    current: 1
    key: 0
    0: 1
    next: 2
    valid: 1
    current: 2
    key: 1
    1: 2
    next: 3
    valid: 1
    current: 3
    key: 2
    2: 3
    next:
    valid: 

The <span class="interfacename">IteratorAggregate</span>
<a href="/language/oop5/interfaces.html" class="link">interface</a> can
be used as an alternative to implementing all of the <span
class="interfacename">Iterator</span> methods. <span
class="interfacename">IteratorAggregate</span> only requires the
implementation of a single method, <span
class="methodname">IteratorAggregate::getIterator</span>, which should
return an instance of a class implementing <span
class="interfacename">Iterator</span>.

**Example \#3 Object Iteration implementing IteratorAggregate**

``` php
<?php
class MyCollection implements IteratorAggregate
{
    private $items = array();
    private $count = 0;

    // Required definition of interface IteratorAggregate
    public function getIterator() {
        return new MyIterator($this->items);
    }

    public function add($value) {
        $this->items[$this->count++] = $value;
    }
}

$coll = new MyCollection();
$coll->add('value 1');
$coll->add('value 2');
$coll->add('value 3');

foreach ($coll as $key => $val) {
    echo "key/value: [$key -> $val]\n\n";
}
?>
```

The above example will output:

    rewinding
    current: value 1
    valid: 1
    current: value 1
    key: 0
    key/value: [0 -> value 1]

    next: value 2
    current: value 2
    valid: 1
    current: value 2
    key: 1
    key/value: [1 -> value 2]

    next: value 3
    current: value 3
    valid: 1
    current: value 3
    key: 2
    key/value: [2 -> value 3]

    next:
    current:
    valid:

> **Note**:
>
> For more examples of iterators, see the
> <a href="/spl/iterators.html" class="link">SPL Extension</a>.

> **Note**:
>
> Users of PHP 5.5 and later may also want to investigate
> <a href="/language/generators.html" class="link">generators</a>, which
> provide an alternative way of defining iterators.
